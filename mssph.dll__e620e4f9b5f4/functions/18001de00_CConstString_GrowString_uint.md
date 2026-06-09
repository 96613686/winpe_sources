# CConstString::GrowString(uint)

- ea: `0x18001de00`
- end: `0x18001de21`
- name: `?GrowString@CConstString@@UEAAXI@Z`
- size: `33`
- prototype: `void __fastcall __noreturn(CConstString *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001e194`

## string_xrefs

- `0x18001de09`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
void __fastcall __noreturn CConstString::GrowString(CConstString *this)
{
  unsigned int v1; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::in1diag3::Throw_Win32(
    retaddr,
    (void *)0x459,
    (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
    (const char *)0xCE,
    v1);
}

```

## disassembly

```asm
0x18001de00  sub     rsp, 28h
0x18001de04  mov     rcx, [rsp+28h]; this
0x18001de09  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18001de10  mov     r9d, 0CEh; char *
0x18001de16  mov     edx, 459h; void *
0x18001de1b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
