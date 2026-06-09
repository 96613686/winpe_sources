# CLMString::GrowInConstructor(uint)

- ea: `0x180013484`
- end: `0x1800134f9`
- name: `?GrowInConstructor@CLMString@@IEAAXI@Z`
- size: `117`
- prototype: `void __fastcall(CLMString *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800064c4`
- `0x180011564`

## callees

- `0x180013484`
- `0x180013500`
- `0x180020834`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800134a4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800134a4`

## string_xrefs

- `0x1800134b8`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x1800134e1`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall CLMString::GrowInConstructor(CLMString *this, unsigned int a2)
{
  unsigned __int64 v3; // rax
  void *v5; // rax
  unsigned int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = 2LL * a2;
  if ( v3 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070216LL,
      v6);
  v5 = malloc((unsigned int)v3);
  *((_QWORD *)this + 1) = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0xCE,
      v6);
  *((_DWORD *)this + 4) = a2;
}

```

## disassembly

```asm
0x180013484  mov     [rsp+arg_0], rbx
0x180013489  push    rdi; int
0x18001348a  sub     rsp, 20h
0x18001348e  mov     eax, edx
0x180013490  mov     rbx, rcx
0x180013493  add     rax, rax
0x180013496  mov     edi, edx
0x180013498  mov     ecx, 0FFFFFFFFh
0x18001349d  cmp     rax, rcx
0x1800134a0  ja      short loc_1800134DC
0x1800134a2  mov     ecx, eax; Size
0x1800134a4  call    cs:__imp_malloc
0x1800134aa  mov     [rbx+8], rax
0x1800134ae  test    rax, rax
0x1800134b1  jnz     short loc_1800134CE
0x1800134b3  mov     rcx, [rsp+28h]; this
0x1800134b8  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800134bf  mov     r9d, 0CEh; char *
0x1800134c5  lea     edx, [rax+28h]; void *
0x1800134c8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800134ce  mov     [rbx+10h], edi
0x1800134d1  mov     rbx, [rsp+28h+arg_0]
0x1800134d6  add     rsp, 20h
0x1800134da  pop     rdi
0x1800134db  retn
0x1800134dc  mov     rcx, [rsp+28h]; this
0x1800134e1  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800134e8  mov     r9d, 80070216h; char *
0x1800134ee  mov     edx, 23h ; '#'; void *
0x1800134f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
