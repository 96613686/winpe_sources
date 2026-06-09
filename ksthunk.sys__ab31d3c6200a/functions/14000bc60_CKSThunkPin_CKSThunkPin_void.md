# CKSThunkPin::~CKSThunkPin(void)

- ea: `0x14000bc60`
- end: `0x14000bcb8`
- name: `??1CKSThunkPin@@EEAA@XZ`
- size: `88`
- prototype: `void __fastcall(CKSThunkPin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002b60`

## callees

- `0x14000183c`
- `0x1400041f0`
- `0x14000bc60`

## pseudocode

```c
void __fastcall CKSThunkPin::~CKSThunkPin(CKSThunkPin *this)
{
  __int64 v2; // rcx
  KSPIN_LOCK *v3; // rcx

  *(_QWORD *)this = &CKSThunkPin::`vftable'{for `CKernelFilterFile'};
  *((_QWORD *)this + 5) = &CKSThunkPin::`vftable'{for `CKSAutomationThunk'};
  v2 = *((_QWORD *)this + 13);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 13) = 0;
  }
  v3 = (KSPIN_LOCK *)*((_QWORD *)this + 4);
  *(_QWORD *)this = &CKernelFilterFile::`vftable';
  CKernelFilterDevice::NotifyDestroyFile(v3, this);
}

```

## disassembly

```asm
0x14000bc60  push    rbx
0x14000bc62  sub     rsp, 20h
0x14000bc66  lea     rax, ??_7CKSThunkPin@@6BCKernelFilterFile@@@; const CKSThunkPin::`vftable'{for `CKernelFilterFile'}
0x14000bc6d  mov     rbx, rcx
0x14000bc70  mov     [rcx], rax
0x14000bc73  lea     rax, ??_7CKSThunkPin@@6BCKSAutomationThunk@@@; const CKSThunkPin::`vftable'{for `CKSAutomationThunk'}
0x14000bc7a  mov     [rcx+28h], rax
0x14000bc7e  mov     rcx, [rcx+68h]
0x14000bc82  test    rcx, rcx
0x14000bc85  jz      short loc_14000BC9B
0x14000bc87  mov     rax, [rcx]
0x14000bc8a  mov     rax, [rax+10h]
0x14000bc8e  call    _guard_dispatch_icall
0x14000bc93  mov     qword ptr [rbx+68h], 0
0x14000bc9b  mov     rcx, [rbx+20h]; this
0x14000bc9f  lea     rax, ??_7CKernelFilterFile@@6B@; const CKernelFilterFile::`vftable'
0x14000bca6  mov     rdx, rbx; struct CKernelFilterFile *
0x14000bca9  mov     [rbx], rax
0x14000bcac  call    ?NotifyDestroyFile@CKernelFilterDevice@@QEAAJPEAVCKernelFilterFile@@@Z; CKernelFilterDevice::NotifyDestroyFile(CKernelFilterFile *)
0x14000bcb1  add     rsp, 20h
0x14000bcb5  pop     rbx
0x14000bcb6  retn
```
