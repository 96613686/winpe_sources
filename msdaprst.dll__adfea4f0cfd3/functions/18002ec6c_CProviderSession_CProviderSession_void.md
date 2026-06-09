# CProviderSession::~CProviderSession(void)

- ea: `0x18002ec6c`
- end: `0x18002ecf2`
- name: `??1CProviderSession@@QEAA@XZ`
- size: `134`
- prototype: `void __fastcall(CProviderSession *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180021794`
- `0x18003012e`

## callees

- `0x18002ec6c`
- `0x180031010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002ecd1`
- `MSDART!MPDeleteCriticalSection` at `0x18002ecd1`
- `MSDART!MPDeleteCriticalSection` at `0x18002ece6`

## pseudocode

```c
void __fastcall CProviderSession::~CProviderSession(CProviderSession *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CProviderDSO::`vftable'{for `IPersist'};
  *((_QWORD *)this + 1) = &CProviderSession::`vftable'{for `IGetDataSource'};
  *((_QWORD *)this + 2) = &IUpdateInfo::`vftable';
  *((_QWORD *)this + 3) = &CProviderDSO::`vftable'{for `ISupportErrorInfo'};
  v2 = *((_QWORD *)this + 9);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
    *((_QWORD *)this + 9) = 0;
  }
  MPDeleteCriticalSection((char *)this + 48);
  MPDeleteCriticalSection((char *)this + 40);
}

```

## disassembly

```asm
0x18002ec6c  push    rbx
0x18002ec6e  sub     rsp, 20h
0x18002ec72  mov     rbx, rcx
0x18002ec75  lea     rax, ??_7CProviderDSO@@6BIPersist@@@; const CProviderDSO::`vftable'{for `IPersist'}
0x18002ec7c  mov     [rcx], rax
0x18002ec7f  lea     rax, ??_7CProviderSession@@6BIGetDataSource@@@; const CProviderSession::`vftable'{for `IGetDataSource'}
0x18002ec86  mov     [rcx+8], rax
0x18002ec8a  lea     rax, ??_7IUpdateInfo@@6B@; const IUpdateInfo::`vftable'
0x18002ec91  mov     [rcx+10h], rax
0x18002ec95  lea     rax, ??_7CProviderDSO@@6BISupportErrorInfo@@@; const CProviderDSO::`vftable'{for `ISupportErrorInfo'}
0x18002ec9c  mov     [rcx+18h], rax
0x18002eca0  mov     rcx, [rcx+48h]
0x18002eca4  test    rcx, rcx
0x18002eca7  jz      short loc_18002ECCD
0x18002eca9  mov     rax, [rcx]
0x18002ecac  mov     rax, [rax+18h]
0x18002ecb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecb5  mov     rcx, [rbx+48h]
0x18002ecb9  mov     rax, [rcx]
0x18002ecbc  mov     rax, [rax+10h]
0x18002ecc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecc5  mov     qword ptr [rbx+48h], 0
0x18002eccd  lea     rcx, [rbx+30h]
0x18002ecd1  call    cs:__imp_MPDeleteCriticalSection
0x18002ecd8  nop     dword ptr [rax+rax+00h]
0x18002ecdd  lea     rcx, [rbx+28h]
0x18002ece1  add     rsp, 20h
0x18002ece5  pop     rbx
0x18002ece6  jmp     cs:__imp_MPDeleteCriticalSection
```
