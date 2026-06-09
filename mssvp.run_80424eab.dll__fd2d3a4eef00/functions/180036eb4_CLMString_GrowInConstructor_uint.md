# CLMString::GrowInConstructor(uint)

- ea: `0x180036eb4`
- end: `0x180036f29`
- name: `?GrowInConstructor@CLMString@@IEAAXI@Z`
- size: `117`
- prototype: `void(CLMString *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180036d48`

## callees

- `0x180011cdc`
- `0x180016360`
- `0x180036eb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036ed4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036ed4`

## string_xrefs

- `0x180036ee8`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180036f11`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

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
0x180036eb4  mov     [rsp+arg_0], rbx
0x180036eb9  push    rdi; int
0x180036eba  sub     rsp, 20h
0x180036ebe  mov     eax, edx
0x180036ec0  mov     rbx, rcx
0x180036ec3  add     rax, rax
0x180036ec6  mov     edi, edx
0x180036ec8  mov     ecx, 0FFFFFFFFh
0x180036ecd  cmp     rax, rcx
0x180036ed0  ja      short loc_180036F0C
0x180036ed2  mov     ecx, eax; Size
0x180036ed4  call    cs:__imp_malloc
0x180036eda  mov     [rbx+8], rax
0x180036ede  test    rax, rax
0x180036ee1  jnz     short loc_180036EFE
0x180036ee3  mov     rcx, [rsp+28h]; this
0x180036ee8  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036eef  mov     r9d, 0CEh; char *
0x180036ef5  lea     edx, [rax+28h]; void *
0x180036ef8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180036efe  mov     [rbx+10h], edi
0x180036f01  mov     rbx, [rsp+28h+arg_0]
0x180036f06  add     rsp, 20h
0x180036f0a  pop     rdi
0x180036f0b  retn
0x180036f0c  mov     rcx, [rsp+28h]; this
0x180036f11  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036f18  mov     r9d, 80070216h; char *
0x180036f1e  mov     edx, 23h ; '#'; void *
0x180036f23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
