# CdpServerIoctl

- ea: `0x1400095c0`
- end: `0x14000974c`
- name: `CdpServerIoctl`
- size: `396`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400095c0`
- `0x14000a390`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400095ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400095ef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009653`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400096d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400096f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009653`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400096d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400096f5`
- `ntoskrnl!IofCompleteRequest` at `0x14000966f`
- `ntoskrnl!IofCompleteRequest` at `0x14000971f`
- `ntoskrnl!IofCompleteRequest` at `0x14000966f`
- `ntoskrnl!IofCompleteRequest` at `0x14000971f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140009600`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140009600`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009647`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400096c5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400096e9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140009647`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400096c5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400096e9`

## pseudocode

```c
__int64 __fastcall CdpServerIoctl(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rsi
  unsigned int IoIrp; // edi

  if ( *(_DWORD *)(*(_QWORD *)(a2 + 184) + 24LL) == 5242886 )
  {
    v3 = (_QWORD *)(a1 + 64);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(*v3, 0);
    if ( *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL) < 0x28u )
    {
      IoIrp = -1073741789;
    }
    else if ( *((_BYTE *)v3 + 8) )
    {
      if ( (_QWORD *)v3[3] != v3 + 3 )
      {
        IoIrp = CdpCompleteReadIoIrp((__int64)v3, (IRP *)a2, 0);
        ExReleasePushLockExclusiveEx(*v3, 0);
        KeLeaveCriticalRegion();
        if ( (IoIrp & 0x80000000) == 0 )
          return IoIrp;
LABEL_6:
        *(_DWORD *)(a2 + 48) = IoIrp;
        *(_QWORD *)(a2 + 56) = 0;
        IofCompleteRequest((PIRP)a2, 0);
        return IoIrp;
      }
      *(_QWORD *)(a2 + 120) = v3;
      _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)&CdpCancelReadIoIrp);
      if ( !*(_BYTE *)(a2 + 68) || !_InterlockedExchange64((volatile __int64 *)(a2 + 104), 0) )
      {
        v3[2] = a2;
        IoIrp = 259;
        *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
        ExReleasePushLockExclusiveEx(*v3, 0);
        KeLeaveCriticalRegion();
        return IoIrp;
      }
      IoIrp = -1073741536;
    }
    else
    {
      IoIrp = -1073741648;
    }
    ExReleasePushLockExclusiveEx(*v3, 0);
    KeLeaveCriticalRegion();
    goto LABEL_6;
  }
  *(_DWORD *)(a2 + 48) = -1073741808;
  *(_QWORD *)(a2 + 56) = 0;
  IofCompleteRequest((PIRP)a2, 0);
  return 3221225488LL;
}

```

## disassembly

```asm
0x1400095c0  mov     [rsp+arg_10], rbx
0x1400095c5  push    rbp
0x1400095c6  sub     rsp, 20h
0x1400095ca  mov     rax, [rdx+0B8h]
0x1400095d1  mov     rbx, rdx
0x1400095d4  cmp     dword ptr [rax+18h], 500006h
0x1400095db  jnz     loc_14000970D
0x1400095e1  mov     [rsp+28h+arg_0], rsi
0x1400095e6  lea     rsi, [rcx+40h]
0x1400095ea  mov     [rsp+28h+arg_8], rdi
0x1400095ef  call    cs:__imp_KeEnterCriticalRegion
0x1400095f6  nop     dword ptr [rax+rax+00h]
0x1400095fb  mov     rcx, [rsi]
0x1400095fe  xor     edx, edx
0x140009600  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140009607  nop     dword ptr [rax+rax+00h]
0x14000960c  mov     rax, [rbx+0B8h]
0x140009613  xor     ebp, ebp
0x140009615  cmp     dword ptr [rax+8], 28h ; '('
0x140009619  jb      loc_140009706
0x14000961f  cmp     [rsi+8], bpl
0x140009623  jz      loc_1400096DF
0x140009629  lea     rax, [rsi+18h]
0x14000962d  cmp     [rax], rax
0x140009630  jz      short loc_140009693
0x140009632  xor     r8d, r8d
0x140009635  mov     rdx, rbx
0x140009638  mov     rcx, rsi
0x14000963b  call    CdpCompleteReadIoIrp
0x140009640  mov     edi, eax
0x140009642  mov     rcx, [rsi]
0x140009645  xor     edx, edx
0x140009647  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000964e  nop     dword ptr [rax+rax+00h]
0x140009653  call    cs:__imp_KeLeaveCriticalRegion
0x14000965a  nop     dword ptr [rax+rax+00h]
0x14000965f  test    edi, edi
0x140009661  jns     short loc_14000967B
0x140009663  xor     edx, edx; PriorityBoost
0x140009665  mov     [rbx+30h], edi
0x140009668  mov     rcx, rbx; Irp
0x14000966b  mov     [rbx+38h], rbp
0x14000966f  call    cs:__imp_IofCompleteRequest
0x140009676  nop     dword ptr [rax+rax+00h]
0x14000967b  mov     rsi, [rsp+28h+arg_0]
0x140009680  mov     eax, edi
0x140009682  mov     rdi, [rsp+28h+arg_8]
0x140009687  mov     rbx, [rsp+28h+arg_10]
0x14000968c  add     rsp, 20h
0x140009690  pop     rbp
0x140009691  retn
0x140009693  mov     [rbx+78h], rsi
0x140009697  lea     rax, CdpCancelReadIoIrp
0x14000969e  xchg    rax, [rbx+68h]
0x1400096a2  cmp     [rbx+44h], bpl
0x1400096a6  jnz     loc_140009735
0x1400096ac  mov     [rsi+10h], rbx
0x1400096b0  xor     edx, edx
0x1400096b2  mov     rcx, [rbx+0B8h]
0x1400096b9  mov     edi, 103h
0x1400096be  or      byte ptr [rcx+3], 1
0x1400096c2  mov     rcx, [rsi]
0x1400096c5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400096cc  nop     dword ptr [rax+rax+00h]
0x1400096d1  call    cs:__imp_KeLeaveCriticalRegion
0x1400096d8  nop     dword ptr [rax+rax+00h]
0x1400096dd  jmp     short loc_14000967B
0x1400096df  mov     edi, 0C00000B0h
0x1400096e4  mov     rcx, [rsi]
0x1400096e7  xor     edx, edx
0x1400096e9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400096f0  nop     dword ptr [rax+rax+00h]
0x1400096f5  call    cs:__imp_KeLeaveCriticalRegion
0x1400096fc  nop     dword ptr [rax+rax+00h]
0x140009701  jmp     loc_140009663
0x140009706  mov     edi, 0C0000023h
0x14000970b  jmp     short loc_1400096E4
0x14000970d  xor     ebp, ebp
0x14000970f  mov     dword ptr [rdx+30h], 0C0000010h
0x140009716  mov     [rdx+38h], rbp
0x14000971a  mov     rcx, rbx; Irp
0x14000971d  xor     edx, edx; PriorityBoost
0x14000971f  call    cs:__imp_IofCompleteRequest
0x140009726  nop     dword ptr [rax+rax+00h]
0x14000972b  mov     eax, 0C0000010h
0x140009730  jmp     loc_140009687
0x140009735  mov     rax, rbp
0x140009738  xchg    rax, [rbx+68h]
0x14000973c  test    rax, rax
0x14000973f  jz      loc_1400096AC
0x140009745  mov     edi, 0C0000120h
0x14000974a  jmp     short loc_1400096E4
```
