# IScavengerBase::IScavengerBase(ThreadGlobals *)

- ea: `0x180015894`
- end: `0x1800158ed`
- name: `??0IScavengerBase@@QEAA@PEAVThreadGlobals@@@Z`
- size: `89`
- prototype: `IScavengerBase *__fastcall(IScavengerBase *__hidden this, struct ThreadGlobals *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042f0`
- `0x180006b60`
- `0x1800153d4`
- `0x180015514`
- `0x180015660`
- `0x180045cac`
- `0x18004a184`
- `0x18004a434`
- `0x18004ab00`
- `0x18004b044`
- `0x18004be5c`
- `0x18004c050`
- `0x18004c980`
- `0x18004dcd4`
- `0x18005792c`
- `0x18007e2d0`
- `0x18007fc18`

## callees

- `0x180015894`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800158c2`
- `KERNEL32!TlsGetValue` at `0x1800158c2`

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
0x180015894  push    rbx
0x180015896  sub     rsp, 20h
0x18001589a  mov     qword ptr [rcx+10h], 0
0x1800158a2  lea     rax, ??_7IScavengerBase@@6B@; const IScavengerBase::`vftable'
0x1800158a9  mov     [rcx], rax
0x1800158ac  mov     rbx, rcx
0x1800158af  mov     qword ptr [rcx+18h], 0
0x1800158b7  test    rdx, rdx
0x1800158ba  jnz     short loc_1800158D6
0x1800158bc  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800158c2  call    cs:__imp_TlsGetValue
0x1800158c9  nop     dword ptr [rax+rax+00h]
0x1800158ce  mov     rdx, rax
0x1800158d1  test    rax, rax
0x1800158d4  jz      short loc_1800158EB
0x1800158d6  mov     rax, [rdx+20h]
0x1800158da  mov     [rbx+8], rax
0x1800158de  lock inc dword ptr [rax]
0x1800158e1  mov     rax, rbx
0x1800158e4  add     rsp, 20h
0x1800158e8  pop     rbx
0x1800158e9  retn
0x1800158eb  jmp     short loc_1800158DA
```
