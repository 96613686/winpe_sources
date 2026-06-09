# NameCracker::processSID(ushort const *,ushort const *,DS_NAME_FORMAT &,ushort * *)

- ea: `0x1800228f8`
- end: `0x180022a31`
- name: `?processSID@NameCracker@@AEAAKPEBG0AEAW4DS_NAME_FORMAT@@PEAPEAG@Z`
- size: `313`
- prototype: `unsigned int __fastcall(NameCracker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, enum DS_NAME_FORMAT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180022520`

## callees

- `0x18000342c`
- `0x180021dc8`
- `0x180022438`
- `0x1800228f8`
- `0x18002825c`

## import_xrefs

- `msvcrt!free` at `0x18002298e`
- `msvcrt!free` at `0x180022a1c`
- `msvcrt!free` at `0x18002298e`
- `msvcrt!free` at `0x180022a1c`

## pseudocode

```c
__int64 __fastcall NameCracker::processSID(
        NameCracker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        enum DS_NAME_FORMAT *a4,
        unsigned __int16 **a5)
{
  unsigned int v8; // r14d
  unsigned __int128 v9; // rax
  wchar_t *v10; // rbx
  unsigned int v11; // ebp
  __int64 v12; // rcx
  unsigned __int128 v13; // rax
  unsigned __int16 *v14; // r10
  unsigned int v15; // edi
  const unsigned __int16 *v16; // rax
  int v17; // eax
  union _LARGE_INTEGER v18; // [rsp+30h] [rbp-48h] BYREF

  v18.QuadPart = 0;
  if ( !NameCracker::convertSid2Puid(this, a2, &v18) )
    return 0;
  *a4 = -17;
  if ( a3 )
  {
    v10 = 0;
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    v8 = v12 + 18;
  }
  else
  {
    IASGetDnsDomainName(0);
    v8 = 18;
    v9 = 1 * (unsigned __int128)2u;
    if ( !is_mul_ok(1u, 2u) )
      *(_QWORD *)&v9 = -1;
    v10 = (wchar_t *)operator new[](v9, *((const struct std::nothrow_t **)&v9 + 1));
    v11 = IASGetDnsDomainName(v10);
    if ( v11 )
    {
      free(v10);
      return v11;
    }
  }
  v13 = v8 * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v8, 2u) )
    *(_QWORD *)&v13 = -1;
  v14 = (unsigned __int16 *)operator new[](v13, *((const struct std::nothrow_t **)&v13 + 1));
  *a5 = v14;
  if ( v14 )
  {
    v16 = v10;
    if ( a3 )
      v16 = a3;
    v17 = StringCchPrintfW(v14, v8, L"%08X%08X@%s", (unsigned int)v18.HighPart, v18.LowPart, v16);
    v15 = (unsigned __int16)v17;
    if ( v17 >= 0 )
      v15 = 0;
  }
  else
  {
    v15 = 122;
  }
  free(v10);
  return v15;
}

```

## disassembly

```asm
0x1800228f8  mov     [rsp+arg_0], rcx
0x1800228fd  push    rbx
0x1800228fe  push    rbp
0x1800228ff  push    rsi
0x180022900  push    rdi
0x180022901  push    r14
0x180022903  push    r15
0x180022905  sub     rsp, 48h
0x180022909  mov     rdi, r8
0x18002290c  xor     r15d, r15d
0x18002290f  lea     r8, [rsp+78h+var_48]; union _LARGE_INTEGER *
0x180022914  mov     qword ptr [rsp+78h+var_48], r15
0x180022919  mov     rbx, r9
0x18002291c  call    ?convertSid2Puid@NameCracker@@AEAA_NPEBGAEAT_LARGE_INTEGER@@@Z; NameCracker::convertSid2Puid(ushort const *,_LARGE_INTEGER &)
0x180022921  test    al, al
0x180022923  jnz     short loc_18002292C
0x180022925  xor     eax, eax
0x180022927  jmp     loc_180022A24
0x18002292c  mov     dword ptr [rbx], 0FFFFFFEFh
0x180022932  test    rdi, rdi
0x180022935  jnz     short loc_18002299B
0x180022937  lea     rdx, [rsp+78h+arg_0]
0x18002293f  mov     dword ptr [rsp+78h+arg_0], r15d
0x180022947  xor     ecx, ecx; pszDest
0x180022949  call    IASGetDnsDomainName
0x18002294e  mov     eax, dword ptr [rsp+78h+arg_0]
0x180022955  lea     rsi, [rdi-1]
0x180022959  lea     ecx, [rax+1]
0x18002295c  lea     r14d, [rax+12h]
0x180022960  lea     eax, [rdi+2]
0x180022963  mul     rcx
0x180022966  cmovb   rax, rsi
0x18002296a  mov     rcx, rax; Size
0x18002296d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180022972  lea     rdx, [rsp+78h+arg_0]
0x18002297a  mov     rcx, rax; pszDest
0x18002297d  mov     rbx, rax
0x180022980  call    IASGetDnsDomainName
0x180022985  mov     ebp, eax
0x180022987  test    eax, eax
0x180022989  jz      short loc_1800229B3
0x18002298b  mov     rcx, rbx; Block
0x18002298e  call    cs:__imp_free
0x180022994  mov     eax, ebp
0x180022996  jmp     loc_180022A24
0x18002299b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002299f  mov     rbx, r15
0x1800229a2  mov     rcx, rsi
0x1800229a5  inc     rcx
0x1800229a8  cmp     [rdi+rcx*2], r15w
0x1800229ad  jnz     short loc_1800229A5
0x1800229af  lea     r14d, [rcx+12h]
0x1800229b3  mov     ebp, r14d
0x1800229b6  mov     eax, 2
0x1800229bb  mul     rbp
0x1800229be  cmovb   rax, rsi
0x1800229c2  mov     rcx, rax; Size
0x1800229c5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800229ca  mov     rcx, [rsp+78h+arg_20]
0x1800229d2  mov     r10, rax
0x1800229d5  mov     [rcx], rax
0x1800229d8  test    rax, rax
0x1800229db  jnz     short loc_1800229E2
0x1800229dd  lea     edi, [rax+7Ah]
0x1800229e0  jmp     short loc_180022A19
0x1800229e2  mov     r9d, dword ptr [rsp+78h+var_48+4]
0x1800229e7  lea     r8, a08x08xS; "%08X%08X@%s"
0x1800229ee  test    rdi, rdi
0x1800229f1  mov     rax, rbx
0x1800229f4  mov     rdx, rbp; unsigned __int64
0x1800229f7  mov     rcx, r10; unsigned __int16 *
0x1800229fa  cmovnz  rax, rdi
0x1800229fe  mov     [rsp+78h+var_50], rax
0x180022a03  mov     eax, dword ptr [rsp+78h+var_48]
0x180022a07  mov     [rsp+78h+var_58], eax
0x180022a0b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022a10  test    eax, eax
0x180022a12  movzx   edi, ax
0x180022a15  cmovns  edi, r15d
0x180022a19  mov     rcx, rbx; Block
0x180022a1c  call    cs:__imp_free
0x180022a22  mov     eax, edi
0x180022a24  add     rsp, 48h
0x180022a28  pop     r15
0x180022a2a  pop     r14
0x180022a2c  pop     rdi
0x180022a2d  pop     rsi
0x180022a2e  pop     rbp
0x180022a2f  pop     rbx
0x180022a30  retn
```
