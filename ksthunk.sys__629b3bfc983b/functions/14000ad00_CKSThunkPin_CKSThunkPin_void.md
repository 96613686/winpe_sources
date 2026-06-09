# CKSThunkPin::~CKSThunkPin(void)

- ea: `0x14000ad00`
- end: `0x14000ad58`
- name: `??1CKSThunkPin@@EEAA@XZ`
- size: `88`
- prototype: `void __fastcall(CKSThunkPin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002260`

## callees

- `0x14000183c`
- `0x140003770`
- `0x14000ad00`

## pseudocode

```c
void __fastcall CKSThunkPin::~CKSThunkPin(CKSThunkPin *this)
{
  __int64 v2; // rcx
  CKernelFilterDevice *v3; // rcx

  *(_QWORD *)this = &CKSThunkPin::`vftable'{for `CKernelFilterFile'};
  *((_QWORD *)this + 5) = &CKSThunkPin::`vftable'{for `CKSAutomationThunk'};
  v2 = *((_QWORD *)this + 13);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 13) = 0;
  }
  v3 = (CKernelFilterDevice *)*((_QWORD *)this + 4);
  *(_QWORD *)this = &CKernelFilterFile::`vftable';
  CKernelFilterDevice::NotifyDestroyFile(v3, this);
}

```

## disassembly

```asm
0x14000ad00  push    rbx
0x14000ad02  sub     rsp, 20h
0x14000ad06  lea     rax, ??_7CKSThunkPin@@6BCKernelFilterFile@@@; const CKSThunkPin::`vftable'{for `CKernelFilterFile'}
0x14000ad0d  mov     rbx, rcx
0x14000ad10  mov     [rcx], rax
0x14000ad13  lea     rax, ??_7CKSThunkPin@@6BCKSAutomationThunk@@@; const CKSThunkPin::`vftable'{for `CKSAutomationThunk'}
0x14000ad1a  mov     [rcx+28h], rax
0x14000ad1e  mov     rcx, [rcx+68h]
0x14000ad22  test    rcx, rcx
0x14000ad25  jz      short loc_14000AD3B
0x14000ad27  mov     rax, [rcx]
0x14000ad2a  mov     rax, [rax+10h]
0x14000ad2e  call    _guard_dispatch_icall
0x14000ad33  mov     qword ptr [rbx+68h], 0
0x14000ad3b  mov     rcx, [rbx+20h]; this
0x14000ad3f  lea     rax, ??_7CKernelFilterFile@@6B@; const CKernelFilterFile::`vftable'
0x14000ad46  mov     rdx, rbx; struct CKernelFilterFile *
0x14000ad49  mov     [rbx], rax
0x14000ad4c  call    ?NotifyDestroyFile@CKernelFilterDevice@@QEAAJPEAVCKernelFilterFile@@@Z; CKernelFilterDevice::NotifyDestroyFile(CKernelFilterFile *)
0x14000ad51  add     rsp, 20h
0x14000ad55  pop     rbx
0x14000ad56  retn
```
