# CKernelFilterDevice::DispatchWrite(_IRP *,_IRP_STATUS,long *)

- ea: `0x140001760`
- end: `0x1400017b5`
- name: `?DispatchWrite@CKernelFilterDevice@@MEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140001760`
- `0x1400017bc`
- `0x140003770`

## pseudocode

```c
__int64 __fastcall CKernelFilterDevice::DispatchWrite(
        CKernelFilterDevice *a1,
        struct _IRP *a2,
        unsigned int a3,
        __int64 a4)
{
  struct CKernelFilterFile *v7; // rax

  v7 = CKernelFilterDevice::FileObjectToFilterFile(a1, a2);
  if ( v7 )
    return (*(__int64 (__fastcall **)(struct CKernelFilterFile *, struct _IRP *, _QWORD, __int64))(*(_QWORD *)v7 + 32LL))(
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
0x140001760  mov     [rsp+arg_0], rbx
0x140001765  mov     [rsp+arg_8], rsi
0x14000176a  push    rdi
0x14000176b  sub     rsp, 30h
0x14000176f  mov     rdi, r9
0x140001772  mov     esi, r8d
0x140001775  mov     rbx, rdx
0x140001778  call    ?FileObjectToFilterFile@CKernelFilterDevice@@QEAAPEAVCKernelFilterFile@@PEAU_IRP@@@Z; CKernelFilterDevice::FileObjectToFilterFile(_IRP *)
0x14000177d  mov     r10, rax
0x140001780  test    rax, rax
0x140001783  jz      short loc_14000179F
0x140001785  mov     rcx, [rax]
0x140001788  mov     r9, rdi
0x14000178b  mov     r8d, esi
0x14000178e  mov     rdx, rbx
0x140001791  mov     rax, [rcx+20h]
0x140001795  mov     rcx, r10
0x140001798  call    _guard_dispatch_icall
0x14000179d  jmp     short loc_1400017A4
0x14000179f  mov     eax, 1
0x1400017a4  mov     rbx, [rsp+38h+arg_0]
0x1400017a9  mov     rsi, [rsp+38h+arg_8]
0x1400017ae  add     rsp, 30h
0x1400017b2  pop     rdi
0x1400017b3  retn
```
