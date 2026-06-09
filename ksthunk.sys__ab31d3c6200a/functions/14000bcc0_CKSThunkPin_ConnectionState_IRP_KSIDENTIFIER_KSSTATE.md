# CKSThunkPin::ConnectionState(_IRP *,KSIDENTIFIER *,KSSTATE *)

- ea: `0x14000bcc0`
- end: `0x14000bd6c`
- name: `?ConnectionState@CKSThunkPin@@UEAAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAW4KSSTATE@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(CKSThunkPin *this, struct _IRP *, struct KSIDENTIFIER *, enum KSSTATE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14000b5e0`
- `0x14000bcc0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000bcfa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000bcfa`
- `ntoskrnl!KeReleaseMutex` at `0x14000bd4e`
- `ntoskrnl!KeReleaseMutex` at `0x14000bd4e`

## pseudocode

```c
__int64 __fastcall CKSThunkPin::ConnectionState(
        CKSThunkPin *this,
        struct _IRP *a2,
        struct KSIDENTIFIER *a3,
        enum KSSTATE *a4)
{
  int v7; // esi
  __int64 v8; // rcx
  __int64 v9; // r14
  char v10; // r12
  char v11; // r8

  v7 = -1073741275;
  if ( (a3->Flags & 2) != 0 )
  {
    KeWaitForSingleObject((char *)this + 8, Executive, 0, 0, 0);
    v8 = *((_QWORD *)this - 1);
    v9 = *(_QWORD *)(v8 + 56);
    v10 = *(_BYTE *)(v9 + 76);
    v7 = CKernelFilterDevice::SynchronousForwardIrp((PDEVICE_OBJECT *)v8, a2);
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
0x14000bcc0  push    rbx
0x14000bcc2  push    rbp
0x14000bcc3  push    rsi
0x14000bcc4  push    rdi
0x14000bcc5  push    r12
0x14000bcc7  push    r14
0x14000bcc9  push    r15
0x14000bccb  sub     rsp, 30h
0x14000bccf  mov     eax, [r8+14h]
0x14000bcd3  mov     rdi, r9
0x14000bcd6  mov     r15, rdx
0x14000bcd9  mov     rbx, rcx
0x14000bcdc  mov     esi, 0C0000225h
0x14000bce1  test    al, 2
0x14000bce3  jz      short loc_14000BD5A
0x14000bce5  xor     r9d, r9d; Alertable
0x14000bce8  mov     [rsp+68h+Timeout], 0; Timeout
0x14000bcf1  xor     r8d, r8d; WaitMode
0x14000bcf4  xor     edx, edx; WaitReason
0x14000bcf6  add     rcx, 8; Object
0x14000bcfa  call    cs:__imp_KeWaitForSingleObject
0x14000bd01  nop     dword ptr [rax+rax+00h]
0x14000bd06  mov     rcx, [rbx-8]; this
0x14000bd0a  mov     rdx, r15; struct _IRP *
0x14000bd0d  mov     r14, [rcx+38h]
0x14000bd11  mov     r12b, [r14+4Ch]
0x14000bd15  call    ?SynchronousForwardIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@@Z; CKernelFilterDevice::SynchronousForwardIrp(_IRP *)
0x14000bd1a  mov     esi, eax
0x14000bd1c  test    eax, eax
0x14000bd1e  js      short loc_14000BD48
0x14000bd20  cmp     dword ptr [rbx+48h], 0
0x14000bd24  jnz     short loc_14000BD43
0x14000bd26  cmp     dword ptr [rdi], 0
0x14000bd29  jz      short loc_14000BD43
0x14000bd2b  mov     r8b, [r14+4Ch]
0x14000bd2f  cmp     r12b, r8b
0x14000bd32  jz      short loc_14000BD43
0x14000bd34  mov     rax, [rbx-8]
0x14000bd38  inc     r8b
0x14000bd3b  mov     rdx, [rax+28h]
0x14000bd3f  mov     [rdx+4Ch], r8b
0x14000bd43  mov     eax, [rdi]
0x14000bd45  mov     [rbx+48h], eax
0x14000bd48  xor     edx, edx; Wait
0x14000bd4a  lea     rcx, [rbx+8]; Mutex
0x14000bd4e  call    cs:__imp_KeReleaseMutex
0x14000bd55  nop     dword ptr [rax+rax+00h]
0x14000bd5a  mov     eax, esi
0x14000bd5c  add     rsp, 30h
0x14000bd60  pop     r15
0x14000bd62  pop     r14
0x14000bd64  pop     r12
0x14000bd66  pop     rdi
0x14000bd67  pop     rsi
0x14000bd68  pop     rbp
0x14000bd69  pop     rbx
0x14000bd6a  retn
```
