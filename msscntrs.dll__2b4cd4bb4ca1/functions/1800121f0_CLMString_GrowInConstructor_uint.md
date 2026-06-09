# CLMString::GrowInConstructor(uint)

- ea: `0x1800121f0`
- end: `0x180012261`
- name: `?GrowInConstructor@CLMString@@IEAAXI@Z`
- size: `113`
- prototype: `void __fastcall(CLMString *this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800120e4`

## callees

- `0x1800041ac`
- `0x1800121f0`
- `0x1800123bc`
- `0x1800123dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180012210`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180012210`

## string_xrefs

- `0x18001224f`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall CLMString::GrowInConstructor(CLMString *this, unsigned int a2)
{
  unsigned __int64 v3; // rax
  void *v5; // rax
  const char *v6; // r9
  unsigned int v7; // eax
  unsigned int v8; // r8d
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = 2LL * a2;
  if ( v3 > 0xFFFFFFFF )
  {
    v7 = wil::verify_hresult<long>(2147942934LL);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x23, v8, (const char *)v7, v9);
  }
  v5 = malloc((unsigned int)v3);
  *((_QWORD *)this + 1) = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      v6,
      v9);
  *((_DWORD *)this + 4) = a2;
}

```

## disassembly

```asm
0x1800121f0  mov     [rsp+arg_0], rbx
0x1800121f5  push    rdi; unsigned int
0x1800121f6  sub     rsp, 20h
0x1800121fa  mov     eax, edx
0x1800121fc  mov     rbx, rcx
0x1800121ff  add     rax, rax
0x180012202  mov     edi, edx
0x180012204  mov     ecx, 0FFFFFFFFh
0x180012209  cmp     rax, rcx
0x18001220c  ja      short loc_18001222D
0x18001220e  mov     ecx, eax; Size
0x180012210  call    cs:__imp_malloc
0x180012216  mov     [rbx+8], rax
0x18001221a  test    rax, rax
0x18001221d  jz      short loc_18001224A
0x18001221f  mov     [rbx+10h], edi
0x180012222  mov     rbx, [rsp+28h+arg_0]
0x180012227  add     rsp, 20h
0x18001222b  pop     rdi
0x18001222c  retn
0x18001222d  mov     ecx, 80070216h
0x180012232  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180012237  mov     rcx, [rsp+28h]; this
0x18001223c  mov     r9d, eax; char *
0x18001223f  mov     edx, 23h ; '#'; void *
0x180012244  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001224a  mov     rcx, [rsp+28h]; this
0x18001224f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x180012256  mov     edx, 28h ; '('; void *
0x18001225b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
