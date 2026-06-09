# CLogScript::CLogScript(void)

- ea: `0x18000849c`
- end: `0x180008548`
- name: `??0CLogScript@@QEAA@XZ`
- size: `172`
- prototype: `CLogScript *__fastcall(CLogScript *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000373c`
- `0x18000744c`
- `0x18000bed8`

## callees

- `0x18000894c`

## import_xrefs

- `IisRTL!??0STR@@QEAA@XZ` at `0x1800084db`
- `IisRTL!??0STR@@QEAA@XZ` at `0x1800084f3`
- `IisRTL!??0STR@@QEAA@XZ` at `0x1800084db`
- `IisRTL!??0STR@@QEAA@XZ` at `0x1800084f3`
- `IisRTL!IISInitializeCriticalSection` at `0x180008512`
- `IisRTL!IISInitializeCriticalSection` at `0x180008512`
- `KERNEL32!EnterCriticalSection` at `0x1800084ac`
- `KERNEL32!EnterCriticalSection` at `0x1800084ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800084bf`
- `KERNEL32!LeaveCriticalSection` at `0x1800084bf`
- `OLEAUT32!__imp_SysAllocString` at `0x180008532`
- `OLEAUT32!__imp_SysAllocString` at `0x180008532`

## pseudocode

```c
CLogScript *__fastcall CLogScript::CLogScript(CLogScript *this)
{
  CLogScript *v2; // rcx

  EnterCriticalSection(&CriticalSection);
  ++dword_180017138;
  LeaveCriticalSection(&CriticalSection);
  *((_QWORD *)this + 6) = 0;
  *(_QWORD *)this = &CLogScript::`vftable';
  STR::STR((CLogScript *)((char *)this + 56));
  *((_QWORD *)this + 135) = 0;
  STR::STR((CLogScript *)((char *)this + 1088));
  *((_QWORD *)this + 143) = 0;
  *((_DWORD *)this + 288) = 0;
  IISInitializeCriticalSection((char *)this + 8);
  *((_DWORD *)this + 68) = 0;
  CLogScript::ResetInetLogLine(v2, (CLogScript *)((char *)this + 112));
  *((_QWORD *)this + 145) = SysAllocString(L"-");
  return this;
}

```

## disassembly

```asm
0x18000849c  push    rbx
0x18000849e  sub     rsp, 20h
0x1800084a2  mov     rbx, rcx
0x1800084a5  lea     rcx, CriticalSection; lpCriticalSection
0x1800084ac  call    cs:__imp_EnterCriticalSection
0x1800084b2  inc     cs:dword_180017138
0x1800084b8  lea     rcx, CriticalSection; lpCriticalSection
0x1800084bf  call    cs:__imp_LeaveCriticalSection
0x1800084c5  lea     rax, ??_7CLogScript@@6B@; const CLogScript::`vftable'
0x1800084cc  mov     qword ptr [rbx+30h], 0
0x1800084d4  lea     rcx, [rbx+38h]
0x1800084d8  mov     [rbx], rax
0x1800084db  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x1800084e1  lea     rcx, [rbx+440h]
0x1800084e8  mov     qword ptr [rbx+438h], 0
0x1800084f3  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x1800084f9  lea     rcx, [rbx+8]
0x1800084fd  mov     qword ptr [rbx+478h], 0
0x180008508  mov     dword ptr [rbx+480h], 0
0x180008512  call    cs:__imp_IISInitializeCriticalSection
0x180008518  lea     rdx, [rbx+70h]; struct _INETLOGLINE *
0x18000851c  mov     dword ptr [rdx+0A0h], 0
0x180008526  call    ?ResetInetLogLine@CLogScript@@AEAAXAEAU_INETLOGLINE@@@Z; CLogScript::ResetInetLogLine(_INETLOGLINE &)
0x18000852b  lea     rcx, psz; "-"
0x180008532  call    cs:__imp_SysAllocString
0x180008538  mov     [rbx+488h], rax
0x18000853f  mov     rax, rbx
0x180008542  add     rsp, 20h
0x180008546  pop     rbx
0x180008547  retn
```
