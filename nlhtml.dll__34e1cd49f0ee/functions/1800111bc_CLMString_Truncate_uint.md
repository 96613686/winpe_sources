# CLMString::Truncate(uint)

- ea: `0x1800111bc`
- end: `0x1800111fc`
- name: `?Truncate@CLMString@@QEAAXI@Z`
- size: `64`
- prototype: `void __fastcall(CLMString *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bea0`
- `0x18000c5f0`
- `0x180011170`
- `0x18001f904`

## callees

- `0x1800111bc`
- `0x180020834`

## string_xrefs

- `0x1800111e5`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
void __fastcall CLMString::Truncate(CLMString *this, unsigned int a2)
{
  __int64 v2; // rax
  unsigned int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > *((_DWORD *)this + 4) - 1 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      v3);
  v2 = *((_QWORD *)this + 1);
  *((_DWORD *)this + 5) = a2;
  *(_WORD *)(v2 + 2LL * a2) = 0;
}

```

## disassembly

```asm
0x1800111bc  sub     rsp, 28h
0x1800111c0  mov     eax, [rcx+10h]
0x1800111c3  mov     r8, rcx
0x1800111c6  dec     eax
0x1800111c8  cmp     edx, eax
0x1800111ca  ja      short loc_1800111E0
0x1800111cc  mov     rax, [r8+8]
0x1800111d0  mov     [rcx+14h], edx
0x1800111d3  mov     ecx, edx
0x1800111d5  xor     edx, edx
0x1800111d7  mov     [rax+rcx*2], dx
0x1800111db  add     rsp, 28h
0x1800111df  retn
0x1800111e0  mov     rcx, [rsp+28h]; this
0x1800111e5  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800111ec  mov     r9d, 0CEh; char *
0x1800111f2  lea     edx, [r9+6Dh]; void *
0x1800111f6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
