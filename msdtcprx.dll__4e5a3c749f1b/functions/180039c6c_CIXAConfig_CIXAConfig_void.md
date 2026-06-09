# CIXAConfig::~CIXAConfig(void)

- ea: `0x180039c6c`
- end: `0x180039d5c`
- name: `??1CIXAConfig@@QEAA@XZ`
- size: `240`
- prototype: `void __fastcall(CIXAConfig *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180023dec`
- `0x1800827c4`

## callees

- `0x18000f0e0`
- `0x180012954`
- `0x18001d178`
- `0x180039c6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039d05`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039d42`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039d05`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039cb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039c9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039cb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CIXAConfig::~CIXAConfig(CIXAConfig *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &CIXAConfig::`vftable'{for `IXAConfig'};
  *((_QWORD *)this + 1) = &CIXAConfig::`vftable'{for `IRMHelper'};
  v2 = (void *)*((_QWORD *)this + 40);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 40) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 41);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 41) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 5) = 0;
  }
  *((_QWORD *)this + 36) = &UTStaticList<CPartnerPair *>::`vftable';
  *((_QWORD *)this + 32) = &UTStaticList<CPartnerPair *>::`vftable';
  *((_QWORD *)this + 25) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  *((_QWORD *)this + 21) = &UTList<CXaTransaction *>::`vftable';
  UTList<CNameObject *>::RemoveAll();
  *((_QWORD *)this + 17) = &UTList<CXaTransaction *>::`vftable';
  UTList<CNameObject *>::RemoveAll();
  *((_QWORD *)this + 10) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  UTSemReadWrite::~UTSemReadWrite((CIXAConfig *)((char *)this + 48));
}

```

## disassembly

```asm
0x180039c6c  mov     [rsp+arg_0], rbx
0x180039c71  push    rdi
0x180039c72  sub     rsp, 20h
0x180039c76  mov     rbx, rcx
0x180039c79  lea     rax, ??_7CIXAConfig@@6BIXAConfig@@@; const CIXAConfig::`vftable'{for `IXAConfig'}
0x180039c80  mov     [rcx], rax
0x180039c83  lea     rax, ??_7CIXAConfig@@6BIRMHelper@@@; const CIXAConfig::`vftable'{for `IRMHelper'}
0x180039c8a  mov     [rcx+8], rax
0x180039c8e  mov     rcx, [rcx+140h]; hObject
0x180039c95  xor     edi, edi
0x180039c97  test    rcx, rcx
0x180039c9a  jz      short loc_180039CA9
0x180039c9c  call    cs:__imp_CloseHandle
0x180039ca2  mov     [rbx+140h], rdi
0x180039ca9  mov     rcx, [rbx+148h]; hObject
0x180039cb0  test    rcx, rcx
0x180039cb3  jz      short loc_180039CC2
0x180039cb5  call    cs:__imp_CloseHandle
0x180039cbb  mov     [rbx+148h], rdi
0x180039cc2  mov     rcx, [rbx+28h]; Block
0x180039cc6  test    rcx, rcx
0x180039cc9  jz      short loc_180039CD4
0x180039ccb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039cd0  mov     [rbx+28h], rdi
0x180039cd4  lea     rax, ??_7?$UTStaticList@PEAVCPartnerPair@@@@6B@; const UTStaticList<CPartnerPair *>::`vftable'
0x180039cdb  mov     [rbx+120h], rax
0x180039ce2  lea     rax, ??_7?$UTStaticList@PEAVCPartnerPair@@@@6B@; const UTStaticList<CPartnerPair *>::`vftable'
0x180039ce9  mov     [rbx+100h], rax
0x180039cf0  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x180039cf7  mov     [rbx+0C8h], rdi
0x180039cfe  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x180039d05  call    cs:__imp_DeleteCriticalSection
0x180039d0b  nop
0x180039d0c  lea     rcx, [rbx+0A8h]
0x180039d13  lea     rax, ??_7?$UTList@PEAVCXaTransaction@@@@6B@; const UTList<CXaTransaction *>::`vftable'
0x180039d1a  mov     [rcx], rax
0x180039d1d  call    ?RemoveAll@?$UTList@PEAVCNameObject@@@@UEAAXXZ; UTList<CNameObject *>::RemoveAll(void)
0x180039d22  nop
0x180039d23  lea     rcx, [rbx+88h]
0x180039d2a  lea     rax, ??_7?$UTList@PEAVCXaTransaction@@@@6B@; const UTList<CXaTransaction *>::`vftable'
0x180039d31  mov     [rcx], rax
0x180039d34  call    ?RemoveAll@?$UTList@PEAVCNameObject@@@@UEAAXXZ; UTList<CNameObject *>::RemoveAll(void)
0x180039d39  nop
0x180039d3a  mov     [rbx+50h], rdi
0x180039d3e  lea     rcx, [rbx+58h]; lpCriticalSection
0x180039d42  call    cs:__imp_DeleteCriticalSection
0x180039d48  nop
0x180039d49  lea     rcx, [rbx+30h]; this
0x180039d4d  mov     rbx, [rsp+28h+arg_0]
0x180039d52  add     rsp, 20h
0x180039d56  pop     rdi
0x180039d57  jmp     ??1UTSemReadWrite@@QEAA@XZ; UTSemReadWrite::~UTSemReadWrite(void)
```
