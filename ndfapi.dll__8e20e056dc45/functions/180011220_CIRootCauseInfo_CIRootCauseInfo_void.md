# CIRootCauseInfo::~CIRootCauseInfo(void)

- ea: `0x180011220`
- end: `0x18001126e`
- name: `??1CIRootCauseInfo@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CIRootCauseInfo *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800115b0`

## callees

- `0x180011220`
- `0x18001d688`
- `0x180021010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011261`
- `KERNEL32!DeleteCriticalSection` at `0x180011261`

## pseudocode

```c
void __fastcall CIRootCauseInfo::~CIRootCauseInfo(CIRootCauseInfo *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CIRootCauseInfo::`vftable';
  DiagnosisTextParser::~DiagnosisTextParser((CIRootCauseInfo *)((char *)this + 88));
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180011220  push    rbx
0x180011222  sub     rsp, 20h
0x180011226  mov     rbx, rcx
0x180011229  lea     rax, ??_7CIRootCauseInfo@@6B@; const CIRootCauseInfo::`vftable'
0x180011230  mov     [rcx], rax
0x180011233  add     rcx, 58h ; 'X'; this
0x180011237  call    ??1DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::~DiagnosisTextParser(void)
0x18001123c  nop
0x18001123d  mov     rcx, [rbx+40h]
0x180011241  test    rcx, rcx
0x180011244  jz      short loc_180011253
0x180011246  mov     rax, [rcx]
0x180011249  mov     rax, [rax+10h]
0x18001124d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011252  nop
0x180011253  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011257  cmp     byte ptr [rcx+28h], 0
0x18001125b  jz      short loc_180011268
0x18001125d  mov     byte ptr [rcx+28h], 0
0x180011261  call    cs:__imp_DeleteCriticalSection
0x180011267  nop
0x180011268  add     rsp, 20h
0x18001126c  pop     rbx
0x18001126d  retn
```
