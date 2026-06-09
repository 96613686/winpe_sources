# CProviderDSO::~CProviderDSO(void)

- ea: `0x18002de30`
- end: `0x18002de9f`
- name: `??1CProviderDSO@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(CProviderDSO *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180013f2c`
- `0x18002fc41`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002de7e`
- `MSDART!MPDeleteCriticalSection` at `0x18002de7e`
- `MSDART!MPDeleteCriticalSection` at `0x18002de93`

## pseudocode

```c
void __fastcall CProviderDSO::~CProviderDSO(CProviderDSO *this)
{
  *(_QWORD *)this = &CProviderDSO::`vftable'{for `IDSOCallBack'};
  *((_QWORD *)this + 1) = &CProviderDSO::`vftable'{for `IPersist'};
  *((_QWORD *)this + 2) = &CProviderDSO::`vftable'{for `IDBInitialize'};
  *((_QWORD *)this + 3) = &CProviderDSO::`vftable'{for `IDBProperties'};
  *((_QWORD *)this + 4) = &CProviderDSO::`vftable'{for `IPersist'};
  *((_QWORD *)this + 5) = &CProviderDSO::`vftable'{for `ISupportErrorInfo'};
  MPDeleteCriticalSection((char *)this + 72);
  MPDeleteCriticalSection((char *)this + 56);
}

```

## disassembly

```asm
0x18002de30  push    rbx
0x18002de32  sub     rsp, 20h
0x18002de36  lea     rax, ??_7CProviderDSO@@6BIDSOCallBack@@@; const CProviderDSO::`vftable'{for `IDSOCallBack'}
0x18002de3d  mov     rbx, rcx
0x18002de40  mov     [rcx], rax
0x18002de43  lea     rax, ??_7CProviderDSO@@6BIPersist@@@; const CProviderDSO::`vftable'{for `IPersist'}
0x18002de4a  mov     [rcx+8], rax
0x18002de4e  lea     rax, ??_7CProviderDSO@@6BIDBInitialize@@@; const CProviderDSO::`vftable'{for `IDBInitialize'}
0x18002de55  mov     [rcx+10h], rax
0x18002de59  lea     rax, ??_7CProviderDSO@@6BIDBProperties@@@; const CProviderDSO::`vftable'{for `IDBProperties'}
0x18002de60  mov     [rcx+18h], rax
0x18002de64  lea     rax, ??_7CProviderDSO@@6BIPersist@@@; const CProviderDSO::`vftable'{for `IPersist'}
0x18002de6b  mov     [rcx+20h], rax
0x18002de6f  lea     rax, ??_7CProviderDSO@@6BISupportErrorInfo@@@; const CProviderDSO::`vftable'{for `ISupportErrorInfo'}
0x18002de76  mov     [rcx+28h], rax
0x18002de7a  add     rcx, 48h ; 'H'
0x18002de7e  call    cs:__imp_MPDeleteCriticalSection
0x18002de85  nop     dword ptr [rax+rax+00h]
0x18002de8a  lea     rcx, [rbx+38h]
0x18002de8e  add     rsp, 20h
0x18002de92  pop     rbx
0x18002de93  jmp     cs:__imp_MPDeleteCriticalSection
```
