# _anonymous_namespace_::DfspCreateSyncCheckSearchFilter

- ea: `0x14004110c`
- end: `0x1400411e4`
- name: `_anonymous_namespace_::DfspCreateSyncCheckSearchFilter`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14003f344`
- `0x140043534`

## callees

- `0x1400011d0`
- `0x140005b28`
- `0x14000aed8`
- `0x14004110c`

## import_xrefs

- `msvcrt!_wcstoui64` at `0x140041128`
- `msvcrt!_wcstoui64` at `0x140041128`

## string_xrefs

- `0x14004116a`: `(|(objectClass=msDFS-Namespacev2)(objectClass=msDFS-Linkv2)(objectClass=msDFS-DeletedLinkv2))`

## pseudocode

```c
unsigned __int16 *__fastcall anonymous_namespace_::DfspCreateSyncCheckSearchFilter(const wchar_t *a1)
{
  __int64 v2; // rbx
  unsigned __int64 v3; // rsi
  unsigned __int64 v4; // rbx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi

  v2 = -1;
  v3 = _wcstoui64(a1, 0, 0) + 1;
  do
    ++v2;
  while ( a1[v2] );
  v4 = v2 + 112;
  v5 = (unsigned __int16 *)operator new(saturated_mul(v4, 2u));
  v6 = v5;
  if ( v5 )
    StringCchPrintfW(
      v5,
      v4,
      L"(&%s(uSNChanged>=%I64u))",
      L"(|(objectClass=msDFS-Namespacev2)(objectClass=msDFS-Linkv2)(objectClass=msDFS-DeletedLinkv2))",
      v3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x200) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_S(*((_QWORD *)pWppControl + 2), 85, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x14004110c  mov     [rsp+arg_0], rbx
0x140041111  mov     [rsp+arg_8], rbp
0x140041116  mov     [rsp+arg_10], rsi
0x14004111b  push    rdi
0x14004111c  sub     rsp, 30h
0x140041120  xor     r8d, r8d; Radix
0x140041123  xor     edx, edx; EndPtr
0x140041125  mov     rdi, rcx
0x140041128  call    cs:__imp__wcstoui64
0x14004112f  nop     dword ptr [rax+rax+00h]
0x140041134  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140041138  mov     rbx, rcx
0x14004113b  xor     ebp, ebp
0x14004113d  lea     rsi, [rax+1]
0x140041141  inc     rbx
0x140041144  cmp     [rdi+rbx*2], bp
0x140041148  jnz     short loc_140041141
0x14004114a  add     rbx, 70h ; 'p'
0x14004114e  mov     eax, 2
0x140041153  mul     rbx
0x140041156  cmovo   rax, rcx
0x14004115a  mov     rcx, rax; Size
0x14004115d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140041162  mov     rdi, rax
0x140041165  test    rax, rax
0x140041168  jz      short loc_140041188
0x14004116a  lea     r9, aObjectclassMsd_1; "(|(objectClass=msDFS-Namespacev2)(objec"...
0x140041171  mov     [rsp+38h+var_18], rsi
0x140041176  lea     r8, aSUsnchangedI64; "(&%s(uSNChanged>=%I64u))"
0x14004117d  mov     rdx, rbx; unsigned __int64
0x140041180  mov     rcx, rax; unsigned __int16 *
0x140041183  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140041188  lea     rax, WPP_GLOBAL_Control
0x14004118f  cmp     cs:WPP_GLOBAL_Control, rax
0x140041196  jz      short loc_1400411CB
0x140041198  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14004119f  test    rcx, rcx
0x1400411a2  jz      short loc_1400411CB
0x1400411a4  test    dword ptr [rcx+1Ch], 200h
0x1400411ab  jz      short loc_1400411CB
0x1400411ad  cmp     byte ptr [rcx+19h], 3
0x1400411b1  jb      short loc_1400411CB
0x1400411b3  mov     rcx, [rcx+10h]
0x1400411b7  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x1400411be  mov     edx, 55h ; 'U'
0x1400411c3  mov     r9, rdi
0x1400411c6  call    WPP_SF_S
0x1400411cb  mov     rbx, [rsp+38h+arg_0]
0x1400411d0  mov     rax, rdi
0x1400411d3  mov     rbp, [rsp+38h+arg_8]
0x1400411d8  mov     rsi, [rsp+38h+arg_10]
0x1400411dd  add     rsp, 30h
0x1400411e1  pop     rdi
0x1400411e2  retn
```
