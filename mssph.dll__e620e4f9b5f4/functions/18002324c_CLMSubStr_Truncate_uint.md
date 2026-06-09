# CLMSubStr::Truncate(uint)

- ea: `0x18002324c`
- end: `0x18002327a`
- name: `?Truncate@CLMSubStr@@QEAAXI@Z`
- size: `46`
- prototype: `void __fastcall(CLMSubStr *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003110`
- `0x180009680`

## callees

- `0x18001e194`
- `0x18002324c`

## string_xrefs

- `0x18002325a`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
void __fastcall CLMSubStr::Truncate(CLMSubStr *this, unsigned int a2)
{
  unsigned int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > *((_DWORD *)this + 1) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x390,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      v2);
  *((_DWORD *)this + 1) = a2;
}

```

## disassembly

```asm
0x18002324c  sub     rsp, 28h
0x180023250  cmp     edx, [rcx+4]
0x180023253  jbe     short loc_180023272
0x180023255  mov     rcx, [rsp+28h]; this
0x18002325a  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180023261  mov     r9d, 0CEh; char *
0x180023267  mov     edx, 390h; void *
0x18002326c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180023272  mov     [rcx+4], edx
0x180023275  add     rsp, 28h
0x180023279  retn
```
