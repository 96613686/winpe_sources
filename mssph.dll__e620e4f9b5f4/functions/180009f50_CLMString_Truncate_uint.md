# CLMString::Truncate(uint)

- ea: `0x180009f50`
- end: `0x180009f8e`
- name: `?Truncate@CLMString@@QEAAXI@Z`
- size: `62`
- prototype: `void __fastcall(CLMString *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003060`
- `0x18001d570`
- `0x18001d650`

## callees

- `0x180009f50`
- `0x18001e194`

## string_xrefs

- `0x180009f76`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

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
0x180009f50  sub     rsp, 28h
0x180009f54  mov     eax, [rcx+10h]
0x180009f57  dec     eax
0x180009f59  cmp     edx, eax
0x180009f5b  ja      short loc_180009F71
0x180009f5d  mov     rax, [rcx+8]
0x180009f61  mov     [rcx+14h], edx
0x180009f64  xor     ecx, ecx
0x180009f66  mov     edx, edx
0x180009f68  mov     [rax+rdx*2], cx
0x180009f6c  add     rsp, 28h
0x180009f70  retn
0x180009f71  mov     rcx, [rsp+28h]; this
0x180009f76  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180009f7d  mov     r9d, 0CEh; char *
0x180009f83  mov     edx, 13Bh; void *
0x180009f88  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
