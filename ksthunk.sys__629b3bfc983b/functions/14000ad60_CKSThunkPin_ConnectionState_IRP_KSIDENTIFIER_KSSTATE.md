# CKSThunkPin::ConnectionState(_IRP *,KSIDENTIFIER *,KSSTATE *)

- ea: `0x14000ad60`
- end: `0x14000ae0c`
- name: `?ConnectionState@CKSThunkPin@@UEAAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAW4KSSTATE@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(CKSThunkPin *this, struct _IRP *, struct KSIDENTIFIER *, enum KSSTATE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14000a5e0`
- `0x14000ad60`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000ad9a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ad9a`
- `ntoskrnl!KeReleaseMutex` at `0x14000adee`
- `ntoskrnl!KeReleaseMutex` at `0x14000adee`

## pseudocode

```c
__int64 __fastcall CKSThunkPin::ConnectionState(
        CKSThunkPin *this,
        struct _IRP *a2,
        struct KSIDENTIFIER *a3,
        enum KSSTATE *a4)
{
  int v7; // esi
  CKernelFilterDevice *v8; // rcx
  __int64 v9; // r14
  char v10; // r12
  char v11; // r8

  v7 = -1073741275;
  if ( (a3->Flags & 2) != 0 )
  {
    KeWaitForSingleObject((char *)this + 8, Executive, 0, 0, 0);
    v8 = (CKernelFilterDevice *)*((_QWORD *)this - 1);
    v9 = *((_QWORD *)v8 + 7);
    v10 = *(_BYTE *)(v9 + 76);
    v7 = CKernelFilterDevice::SynchronousForwardIrp(v8, a2);
    if ( v7 >= 0 )
    {
      if ( !*((_DWORD *)this + 18) )
      {
        if ( *a4 )
        {
          v11 = *(_BYTE *)(v9 + 76);
          if ( v10 != v11 )
            *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this - 1) + 40LL) + 76LL) = v11 + 1;
        }
      }
      *((enum KSSTATE *)this + 18) = *a4;
    }
    KeReleaseMutex((PRKMUTEX)((char *)this + 8), 0);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000ad60  push    rbx
0x14000ad62  push    rbp
0x14000ad63  push    rsi
0x14000ad64  push    rdi
0x14000ad65  push    r12
0x14000ad67  push    r14
0x14000ad69  push    r15
0x14000ad6b  sub     rsp, 30h
0x14000ad6f  mov     eax, [r8+14h]
0x14000ad73  mov     rdi, r9
0x14000ad76  mov     r15, rdx
0x14000ad79  mov     rbx, rcx
0x14000ad7c  mov     esi, 0C0000225h
0x14000ad81  test    al, 2
0x14000ad83  jz      short loc_14000ADFA
0x14000ad85  xor     r9d, r9d; Alertable
0x14000ad88  mov     [rsp+68h+Timeout], 0; Timeout
0x14000ad91  xor     r8d, r8d; WaitMode
0x14000ad94  xor     edx, edx; WaitReason
0x14000ad96  add     rcx, 8; Object
0x14000ad9a  call    cs:__imp_KeWaitForSingleObject
0x14000ada1  nop     dword ptr [rax+rax+00h]
0x14000ada6  mov     rcx, [rbx-8]; this
0x14000adaa  mov     rdx, r15; struct _IRP *
0x14000adad  mov     r14, [rcx+38h]
0x14000adb1  mov     r12b, [r14+4Ch]
0x14000adb5  call    ?SynchronousForwardIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@@Z; CKernelFilterDevice::SynchronousForwardIrp(_IRP *)
0x14000adba  mov     esi, eax
0x14000adbc  test    eax, eax
0x14000adbe  js      short loc_14000ADE8
0x14000adc0  cmp     dword ptr [rbx+48h], 0
0x14000adc4  jnz     short loc_14000ADE3
0x14000adc6  cmp     dword ptr [rdi], 0
0x14000adc9  jz      short loc_14000ADE3
0x14000adcb  mov     r8b, [r14+4Ch]
0x14000adcf  cmp     r12b, r8b
0x14000add2  jz      short loc_14000ADE3
0x14000add4  mov     rax, [rbx-8]
0x14000add8  inc     r8b
0x14000addb  mov     rdx, [rax+28h]
0x14000addf  mov     [rdx+4Ch], r8b
0x14000ade3  mov     eax, [rdi]
0x14000ade5  mov     [rbx+48h], eax
0x14000ade8  xor     edx, edx; Wait
0x14000adea  lea     rcx, [rbx+8]; Mutex
0x14000adee  call    cs:__imp_KeReleaseMutex
0x14000adf5  nop     dword ptr [rax+rax+00h]
0x14000adfa  mov     eax, esi
0x14000adfc  add     rsp, 30h
0x14000ae00  pop     r15
0x14000ae02  pop     r14
0x14000ae04  pop     r12
0x14000ae06  pop     rdi
0x14000ae07  pop     rsi
0x14000ae08  pop     rbp
0x14000ae09  pop     rbx
0x14000ae0a  retn
```
