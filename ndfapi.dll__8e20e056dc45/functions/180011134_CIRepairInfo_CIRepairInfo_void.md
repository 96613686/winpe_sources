# CIRepairInfo::~CIRepairInfo(void)

- ea: `0x180011134`
- end: `0x180011182`
- name: `??1CIRepairInfo@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CIRepairInfo *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180011490`

## callees

- `0x180011134`
- `0x18001d688`
- `0x180021010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011175`
- `KERNEL32!DeleteCriticalSection` at `0x180011175`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CIRepairInfo::~CIRepairInfo(CIRepairInfo *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CIRepairInfo::`vftable';
  DiagnosisTextParser::~DiagnosisTextParser((CIRepairInfo *)((char *)this + 96));
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
0x180011134  push    rbx
0x180011136  sub     rsp, 20h
0x18001113a  mov     rbx, rcx
0x18001113d  lea     rax, ??_7CIRepairInfo@@6B@; const CIRepairInfo::`vftable'
0x180011144  mov     [rcx], rax
0x180011147  add     rcx, 60h ; '`'; this
0x18001114b  call    ??1DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::~DiagnosisTextParser(void)
0x180011150  nop
0x180011151  mov     rcx, [rbx+40h]
0x180011155  test    rcx, rcx
0x180011158  jz      short loc_180011167
0x18001115a  mov     rax, [rcx]
0x18001115d  mov     rax, [rax+10h]
0x180011161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011166  nop
0x180011167  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001116b  cmp     byte ptr [rcx+28h], 0
0x18001116f  jz      short loc_18001117C
0x180011171  mov     byte ptr [rcx+28h], 0
0x180011175  call    cs:__imp_DeleteCriticalSection
0x18001117b  nop
0x18001117c  add     rsp, 20h
0x180011180  pop     rbx
0x180011181  retn
```
