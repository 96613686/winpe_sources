# CLMString::GrowInConstructor(uint)

- ea: `0x18000c680`
- end: `0x18000c6f5`
- name: `?GrowInConstructor@CLMString@@IEAAXI@Z`
- size: `117`
- prototype: `void __fastcall(CLMString *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003970`
- `0x180004f60`
- `0x1800071c0`
- `0x1800098f0`
- `0x18000ada0`
- `0x18000bf0c`

## callees

- `0x18000c680`
- `0x18000e7fc`
- `0x18001e194`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c6a0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c6a0`

## string_xrefs

- `0x18000c6b4`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x18000c6dd`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

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
0x18000c680  mov     [rsp+arg_0], rbx
0x18000c685  push    rdi; int
0x18000c686  sub     rsp, 20h
0x18000c68a  mov     eax, edx
0x18000c68c  mov     rbx, rcx
0x18000c68f  add     rax, rax
0x18000c692  mov     edi, edx
0x18000c694  mov     ecx, 0FFFFFFFFh
0x18000c699  cmp     rax, rcx
0x18000c69c  ja      short loc_18000C6D8
0x18000c69e  mov     ecx, eax; Size
0x18000c6a0  call    cs:__imp_malloc
0x18000c6a6  mov     [rbx+8], rax
0x18000c6aa  test    rax, rax
0x18000c6ad  jnz     short loc_18000C6CA
0x18000c6af  mov     rcx, [rsp+28h]; this
0x18000c6b4  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000c6bb  mov     r9d, 0CEh; char *
0x18000c6c1  lea     edx, [rax+28h]; void *
0x18000c6c4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000c6ca  mov     [rbx+10h], edi
0x18000c6cd  mov     rbx, [rsp+28h+arg_0]
0x18000c6d2  add     rsp, 20h
0x18000c6d6  pop     rdi
0x18000c6d7  retn
0x18000c6d8  mov     rcx, [rsp+28h]; this
0x18000c6dd  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000c6e4  mov     r9d, 80070216h; char *
0x18000c6ea  mov     edx, 23h ; '#'; void *
0x18000c6ef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
