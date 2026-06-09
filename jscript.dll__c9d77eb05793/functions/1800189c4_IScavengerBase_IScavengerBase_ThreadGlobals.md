# IScavengerBase::IScavengerBase(ThreadGlobals *)

- ea: `0x1800189c4`
- end: `0x180018a16`
- name: `??0IScavengerBase@@QEAA@PEAVThreadGlobals@@@Z`
- size: `82`
- prototype: `IScavengerBase *__fastcall(IScavengerBase *__hidden this, struct ThreadGlobals *)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180014b50`
- `0x180018514`
- `0x180018650`
- `0x18001879c`
- `0x18004501c`
- `0x180046cf8`
- `0x1800480b0`
- `0x180049484`
- `0x180049758`
- `0x180049eec`
- `0x18004a2f4`
- `0x18004b12c`
- `0x18004b34c`
- `0x18004bd30`
- `0x18004ce64`
- `0x180056a24`
- `0x18007ca50`
- `0x18007e2a4`

## callees

- `0x1800189c4`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800189f2`
- `KERNEL32!TlsGetValue` at `0x1800189f2`

## pseudocode

```c
IScavengerBase *__fastcall IScavengerBase::IScavengerBase(IScavengerBase *this, struct ThreadGlobals *a2)
{
  struct ThreadGlobals *Value; // rax

  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &IScavengerBase::`vftable';
  *((_QWORD *)this + 3) = 0;
  if ( a2 || (Value = (struct ThreadGlobals *)TlsGetValue(g_luTls), (a2 = Value) != 0) )
    Value = (struct ThreadGlobals *)*((_QWORD *)a2 + 4);
  *((_QWORD *)this + 1) = Value;
  _InterlockedIncrement((volatile signed __int32 *)Value);
  return this;
}

```

## disassembly

```asm
0x1800189c4  push    rbx
0x1800189c6  sub     rsp, 20h
0x1800189ca  mov     qword ptr [rcx+10h], 0
0x1800189d2  lea     rax, ??_7IScavengerBase@@6B@; const IScavengerBase::`vftable'
0x1800189d9  mov     [rcx], rax
0x1800189dc  mov     rbx, rcx
0x1800189df  mov     qword ptr [rcx+18h], 0
0x1800189e7  test    rdx, rdx
0x1800189ea  jnz     short loc_180018A00
0x1800189ec  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800189f2  call    cs:__imp_TlsGetValue
0x1800189f8  mov     rdx, rax
0x1800189fb  test    rax, rax
0x1800189fe  jz      short loc_180018A14
0x180018a00  mov     rax, [rdx+20h]
0x180018a04  mov     [rbx+8], rax
0x180018a08  lock inc dword ptr [rax]
0x180018a0b  mov     rax, rbx
0x180018a0e  add     rsp, 20h
0x180018a12  pop     rbx
0x180018a13  retn
0x180018a14  jmp     short loc_180018A04
```
