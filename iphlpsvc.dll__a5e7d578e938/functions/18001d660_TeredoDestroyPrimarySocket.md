# TeredoDestroyPrimarySocket

- ea: `0x18001d660`
- end: `0x18001d7a5`
- name: `TeredoDestroyPrimarySocket`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001bf70`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x18001c860`
- `0x18001d660`
- `0x18001d7ac`
- `0x18001ddd4`
- `0x1800340d0`
- `0x18003d398`
- `0x180042348`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d782`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001d698`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001d698`
- `WS2_32!__imp_closesocket` at `0x18001d730`
- `WS2_32!__imp_closesocket` at `0x18001d730`
- `WS2_32!__imp_ntohs` at `0x18001d67f`
- `WS2_32!__imp_ntohs` at `0x18001d67f`

## string_xrefs

- `0x18001d6fe`: `Successully deleted UPnP port mapping for %u`
- `0x18001d716`: `Failed to delete UPnP port mapping for %u: 0x%x`

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
0x18001d660  push    rbx
0x18001d662  push    rbp
0x18001d663  push    rsi
0x18001d664  push    rdi
0x18001d665  push    r14
0x18001d667  sub     rsp, 20h
0x18001d66b  mov     rdi, [rcx]
0x18001d66e  mov     rsi, rcx
0x18001d671  movzx   ecx, word ptr [rdi+0A66h]; netshort
0x18001d678  mov     rbp, [rdi+0AC8h]
0x18001d67f  call    cs:__imp_ntohs
0x18001d686  nop     dword ptr [rax+rax+00h]
0x18001d68b  mov     rcx, [rsi+10h]; pio
0x18001d68f  movzx   r14d, ax
0x18001d693  test    rcx, rcx
0x18001d696  jz      short loc_18001D6AC
0x18001d698  call    cs:__imp_CloseThreadpoolIo
0x18001d69f  nop     dword ptr [rax+rax+00h]
0x18001d6a4  mov     qword ptr [rsi+10h], 0
0x18001d6ac  cmp     qword ptr [rsi+18h], 0FFFFFFFFFFFFFFFFh
0x18001d6b1  jz      loc_18001D744
0x18001d6b7  cmp     dword ptr [rbp+4BA8h], 0
0x18001d6be  jz      short loc_18001D6C7
0x18001d6c0  call    TeredoDeregisterPortMapping
0x18001d6c5  jmp     short loc_18001D72C
0x18001d6c7  cmp     byte ptr [rbp+4BACh], 0
0x18001d6ce  jz      short loc_18001D722
0x18001d6d0  lea     rbx, [rdi+0A68h]
0x18001d6d7  mov     rdx, rbx
0x18001d6da  lea     r8, [rdi+0D64h]
0x18001d6e1  call    TeredoFwRegisterUPnPFirewallExceptions
0x18001d6e6  movzx   edx, r14w
0x18001d6ea  mov     rcx, rbx; struct in_addr *
0x18001d6ed  call    TeredoUPnPRemovePortMapping
0x18001d6f2  mov     r8d, r14d
0x18001d6f5  mov     ecx, 100000h
0x18001d6fa  test    eax, eax
0x18001d6fc  js      short loc_18001D713
0x18001d6fe  lea     rdx, aSuccessullyDel; "Successully deleted UPnP port mapping f"...
0x18001d705  call    EventWrite0
0x18001d70a  mov     byte ptr [rbp+4BACh], 0
0x18001d711  jmp     short loc_18001D722
0x18001d713  mov     r9d, eax
0x18001d716  lea     rdx, aFailedToDelete; "Failed to delete UPnP port mapping for "...
0x18001d71d  call    EventWriteError0
0x18001d722  call    TeredoUPnPReleaseCachedObjects
0x18001d727  call    TeredoFwUnregisterUPnPFirewallExceptions
0x18001d72c  mov     rcx, [rsi+18h]; s
0x18001d730  call    cs:__imp_closesocket
0x18001d737  nop     dword ptr [rax+rax+00h]
0x18001d73c  mov     qword ptr [rsi+18h], 0FFFFFFFFFFFFFFFFh
0x18001d744  cmp     qword ptr [rdi+0A28h], 0
0x18001d74c  jz      short loc_18001D776
0x18001d74e  mov     eax, 2
0x18001d753  mov     r8b, 1
0x18001d756  xchg    eax, [rdi+0A30h]
0x18001d75c  mov     rcx, [rdi+0A28h]; pwa
0x18001d763  mov     dl, r8b
0x18001d766  call    TpclUnregisterWait
0x18001d76b  mov     qword ptr [rdi+0A28h], 0
0x18001d776  mov     rcx, [rdi+0A20h]; hObject
0x18001d77d  test    rcx, rcx
0x18001d780  jz      short loc_18001D799
0x18001d782  call    cs:__imp_CloseHandle
0x18001d789  nop     dword ptr [rax+rax+00h]
0x18001d78e  mov     qword ptr [rdi+0A20h], 0
0x18001d799  add     rsp, 20h
0x18001d79d  pop     r14
0x18001d79f  pop     rdi
0x18001d7a0  pop     rsi
0x18001d7a1  pop     rbp
0x18001d7a2  pop     rbx
0x18001d7a3  retn
```
