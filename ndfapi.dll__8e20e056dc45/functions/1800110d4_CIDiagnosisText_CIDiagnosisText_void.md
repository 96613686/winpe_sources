# CIDiagnosisText::~CIDiagnosisText(void)

- ea: `0x1800110d4`
- end: `0x18001112d`
- name: `??1CIDiagnosisText@@QEAA@XZ`
- size: `89`
- prototype: `void __fastcall(CIDiagnosisText *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800113f0`

## callees

- `0x1800110d4`
- `0x18001d808`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011121`
- `KERNEL32!DeleteCriticalSection` at `0x180011121`
- `ole32!CoTaskMemFree` at `0x1800110eb`
- `ole32!CoTaskMemFree` at `0x1800110f5`
- `ole32!CoTaskMemFree` at `0x1800110eb`
- `ole32!CoTaskMemFree` at `0x1800110f5`

## pseudocode

```c
void __fastcall CIDiagnosisText::~CIDiagnosisText(CIDiagnosisText *this)
{
  *(_QWORD *)this = &CIDiagnosisText::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 8));
  CoTaskMemFree(*((LPVOID *)this + 9));
  FreeDiagnosisParameters(*((struct DiagnosisTextParser::DiagnosisParameter **)this + 10), *((_DWORD *)this + 22));
  FreeDiagnosisParameters(*((struct DiagnosisTextParser::DiagnosisParameter **)this + 12), *((_DWORD *)this + 26));
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x1800110d4  push    rbx
0x1800110d6  sub     rsp, 20h
0x1800110da  lea     rax, ??_7CIDiagnosisText@@6B@; const CIDiagnosisText::`vftable'
0x1800110e1  mov     rbx, rcx
0x1800110e4  mov     [rcx], rax
0x1800110e7  mov     rcx, [rcx+40h]; pv
0x1800110eb  call    cs:__imp_CoTaskMemFree
0x1800110f1  mov     rcx, [rbx+48h]; pv
0x1800110f5  call    cs:__imp_CoTaskMemFree
0x1800110fb  mov     edx, [rbx+58h]; unsigned int
0x1800110fe  mov     rcx, [rbx+50h]; struct DiagnosisTextParser::DiagnosisParameter *
0x180011102  call    ?FreeDiagnosisParameters@@YAXPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z; FreeDiagnosisParameters(DiagnosisTextParser::DiagnosisParameter *,ulong)
0x180011107  mov     edx, [rbx+68h]; unsigned int
0x18001110a  mov     rcx, [rbx+60h]; struct DiagnosisTextParser::DiagnosisParameter *
0x18001110e  call    ?FreeDiagnosisParameters@@YAXPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z; FreeDiagnosisParameters(DiagnosisTextParser::DiagnosisParameter *,ulong)
0x180011113  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011117  cmp     byte ptr [rcx+28h], 0
0x18001111b  jz      short loc_180011127
0x18001111d  mov     byte ptr [rcx+28h], 0
0x180011121  call    cs:__imp_DeleteCriticalSection
0x180011127  add     rsp, 20h
0x18001112b  pop     rbx
0x18001112c  retn
```
