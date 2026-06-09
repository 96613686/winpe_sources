# CKernelFilterDevice::DispatchRead(_IRP *,_IRP_STATUS,long *)

- ea: `0x140001700`
- end: `0x140001755`
- name: `?DispatchRead@CKernelFilterDevice@@MEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140001700`
- `0x1400017bc`
- `0x140003770`

## pseudocode

```c
__int64 __fastcall CKernelFilterDevice::DispatchRead(
        CKernelFilterDevice *a1,
        struct _IRP *a2,
        unsigned int a3,
        __int64 a4)
{
  struct CKernelFilterFile *v7; // rax

  v7 = CKernelFilterDevice::FileObjectToFilterFile(a1, a2);
  if ( v7 )
    return (*(__int64 (__fastcall **)(struct CKernelFilterFile *, struct _IRP *, _QWORD, __int64))(*(_QWORD *)v7 + 24LL))(
             v7,
             a2,
             a3,
             a4);
  else
    return 1;
}

```

## disassembly

```asm
0x140001700  mov     [rsp+arg_0], rbx
0x140001705  mov     [rsp+arg_8], rsi
0x14000170a  push    rdi
0x14000170b  sub     rsp, 30h
0x14000170f  mov     rdi, r9
0x140001712  mov     esi, r8d
0x140001715  mov     rbx, rdx
0x140001718  call    ?FileObjectToFilterFile@CKernelFilterDevice@@QEAAPEAVCKernelFilterFile@@PEAU_IRP@@@Z; CKernelFilterDevice::FileObjectToFilterFile(_IRP *)
0x14000171d  mov     r10, rax
0x140001720  test    rax, rax
0x140001723  jz      short loc_14000173F
0x140001725  mov     rcx, [rax]
0x140001728  mov     r9, rdi
0x14000172b  mov     r8d, esi
0x14000172e  mov     rdx, rbx
0x140001731  mov     rax, [rcx+18h]
0x140001735  mov     rcx, r10
0x140001738  call    _guard_dispatch_icall
0x14000173d  jmp     short loc_140001744
0x14000173f  mov     eax, 1
0x140001744  mov     rbx, [rsp+38h+arg_0]
0x140001749  mov     rsi, [rsp+38h+arg_8]
0x14000174e  add     rsp, 30h
0x140001752  pop     rdi
0x140001753  retn
```
