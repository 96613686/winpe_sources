# TeredoDestroyPrimarySocket

- ea: `0x18001d650`
- end: `0x18001d795`
- name: `TeredoDestroyPrimarySocket`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001bf60`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x18001c850`
- `0x18001d650`
- `0x18001d79c`
- `0x18001ddc4`
- `0x1800340c0`
- `0x18003d388`
- `0x180042388`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d772`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d772`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001d688`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001d688`
- `WS2_32!__imp_closesocket` at `0x18001d720`
- `WS2_32!__imp_closesocket` at `0x18001d720`
- `WS2_32!__imp_ntohs` at `0x18001d66f`
- `WS2_32!__imp_ntohs` at `0x18001d66f`

## string_xrefs

- `0x18001d6ee`: `Successully deleted UPnP port mapping for %u`
- `0x18001d706`: `Failed to delete UPnP port mapping for %u: 0x%x`

## pseudocode

```c
void __fastcall TeredoDestroyPrimarySocket(_QWORD *a1)
{
  __int64 v1; // rdi
  __int64 v3; // rbp
  u_short v4; // ax
  struct _TP_IO *v5; // rcx
  unsigned int v6; // r14d
  int v7; // eax
  void *v8; // rcx

  v1 = *a1;
  v3 = *(_QWORD *)(*a1 + 2760LL);
  v4 = ntohs(*(_WORD *)(*a1 + 2662LL));
  v5 = (struct _TP_IO *)a1[2];
  v6 = v4;
  if ( v5 )
  {
    CloseThreadpoolIo(v5);
    a1[2] = 0;
  }
  if ( a1[3] != -1 )
  {
    if ( *(_DWORD *)(v3 + 19368) )
    {
      TeredoDeregisterPortMapping();
    }
    else
    {
      if ( *(_BYTE *)(v3 + 19372) )
      {
        TeredoFwRegisterUPnPFirewallExceptions(v5, v1 + 2664, v1 + 3428);
        v7 = TeredoUPnPRemovePortMapping((struct in_addr *)(v1 + 2664));
        if ( v7 < 0 )
        {
          EventWriteError0(0x100000, L"Failed to delete UPnP port mapping for %u: 0x%x", v6, (unsigned int)v7);
        }
        else
        {
          EventWrite0(0x100000, L"Successully deleted UPnP port mapping for %u", v6);
          *(_BYTE *)(v3 + 19372) = 0;
        }
      }
      TeredoUPnPReleaseCachedObjects();
      TeredoFwUnregisterUPnPFirewallExceptions();
    }
    closesocket(a1[3]);
    a1[3] = -1;
  }
  if ( *(_QWORD *)(v1 + 2600) )
  {
    _InterlockedExchange((volatile __int32 *)(v1 + 2608), 2);
    TpclUnregisterWait(*(PTP_WAIT *)(v1 + 2600), 1, 1u);
    *(_QWORD *)(v1 + 2600) = 0;
  }
  v8 = *(void **)(v1 + 2592);
  if ( v8 )
  {
    CloseHandle(v8);
    *(_QWORD *)(v1 + 2592) = 0;
  }
}

```

## disassembly

```asm
0x18001d650  push    rbx
0x18001d652  push    rbp
0x18001d653  push    rsi
0x18001d654  push    rdi
0x18001d655  push    r14
0x18001d657  sub     rsp, 20h
0x18001d65b  mov     rdi, [rcx]
0x18001d65e  mov     rsi, rcx
0x18001d661  movzx   ecx, word ptr [rdi+0A66h]; netshort
0x18001d668  mov     rbp, [rdi+0AC8h]
0x18001d66f  call    cs:__imp_ntohs
0x18001d676  nop     dword ptr [rax+rax+00h]
0x18001d67b  mov     rcx, [rsi+10h]; pio
0x18001d67f  movzx   r14d, ax
0x18001d683  test    rcx, rcx
0x18001d686  jz      short loc_18001D69C
0x18001d688  call    cs:__imp_CloseThreadpoolIo
0x18001d68f  nop     dword ptr [rax+rax+00h]
0x18001d694  mov     qword ptr [rsi+10h], 0
0x18001d69c  cmp     qword ptr [rsi+18h], 0FFFFFFFFFFFFFFFFh
0x18001d6a1  jz      loc_18001D734
0x18001d6a7  cmp     dword ptr [rbp+4BA8h], 0
0x18001d6ae  jz      short loc_18001D6B7
0x18001d6b0  call    TeredoDeregisterPortMapping
0x18001d6b5  jmp     short loc_18001D71C
0x18001d6b7  cmp     byte ptr [rbp+4BACh], 0
0x18001d6be  jz      short loc_18001D712
0x18001d6c0  lea     rbx, [rdi+0A68h]
0x18001d6c7  mov     rdx, rbx
0x18001d6ca  lea     r8, [rdi+0D64h]
0x18001d6d1  call    TeredoFwRegisterUPnPFirewallExceptions
0x18001d6d6  movzx   edx, r14w
0x18001d6da  mov     rcx, rbx; struct in_addr *
0x18001d6dd  call    TeredoUPnPRemovePortMapping
0x18001d6e2  mov     r8d, r14d
0x18001d6e5  mov     ecx, 100000h
0x18001d6ea  test    eax, eax
0x18001d6ec  js      short loc_18001D703
0x18001d6ee  lea     rdx, aSuccessullyDel; "Successully deleted UPnP port mapping f"...
0x18001d6f5  call    EventWrite0
0x18001d6fa  mov     byte ptr [rbp+4BACh], 0
0x18001d701  jmp     short loc_18001D712
0x18001d703  mov     r9d, eax
0x18001d706  lea     rdx, aFailedToDelete; "Failed to delete UPnP port mapping for "...
0x18001d70d  call    EventWriteError0
0x18001d712  call    TeredoUPnPReleaseCachedObjects
0x18001d717  call    TeredoFwUnregisterUPnPFirewallExceptions
0x18001d71c  mov     rcx, [rsi+18h]; s
0x18001d720  call    cs:__imp_closesocket
0x18001d727  nop     dword ptr [rax+rax+00h]
0x18001d72c  mov     qword ptr [rsi+18h], 0FFFFFFFFFFFFFFFFh
0x18001d734  cmp     qword ptr [rdi+0A28h], 0
0x18001d73c  jz      short loc_18001D766
0x18001d73e  mov     eax, 2
0x18001d743  mov     r8b, 1
0x18001d746  xchg    eax, [rdi+0A30h]
0x18001d74c  mov     rcx, [rdi+0A28h]; pwa
0x18001d753  mov     dl, r8b
0x18001d756  call    TpclUnregisterWait
0x18001d75b  mov     qword ptr [rdi+0A28h], 0
0x18001d766  mov     rcx, [rdi+0A20h]; hObject
0x18001d76d  test    rcx, rcx
0x18001d770  jz      short loc_18001D789
0x18001d772  call    cs:__imp_CloseHandle
0x18001d779  nop     dword ptr [rax+rax+00h]
0x18001d77e  mov     qword ptr [rdi+0A20h], 0
0x18001d789  add     rsp, 20h
0x18001d78d  pop     r14
0x18001d78f  pop     rdi
0x18001d790  pop     rsi
0x18001d791  pop     rbp
0x18001d792  pop     rbx
0x18001d793  retn
```
