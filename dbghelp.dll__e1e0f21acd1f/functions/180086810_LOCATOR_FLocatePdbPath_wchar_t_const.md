# LOCATOR::FLocatePdbPath(wchar_t const *)

- ea: `0x180086810`
- end: `0x180086bba`
- name: `?FLocatePdbPath@LOCATOR@@AEAA_NPEB_W@Z`
- size: `938`
- prototype: `bool __fastcall(LOCATOR *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180086180`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x180086810`
- `0x180086bc0`
- `0x180087080`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180086b8b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180086b8b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180086a16`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180086a30`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180086a52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180086a16`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180086a30`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180086a52`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180086900`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180086900`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180086a6b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180086a6b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18008688c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800868a3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180086918`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180086930`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18008688c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800868a3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180086918`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180086930`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086866`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086ac1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086ae8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086b1c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086866`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086ac1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086ae8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086b1c`

## string_xrefs

- `0x180086a48`: `CACHE*`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall LOCATOR::FLocatePdbPath(LOCATOR *this, const wchar_t *a2)
{
  const wchar_t *v2; // rdi
  __int64 v4; // r12
  __int64 v5; // rcx
  __int64 v6; // rax
  unsigned __int64 v7; // r13
  unsigned __int64 v8; // rax
  wchar_t *v9; // rbx
  bool v11; // bp
  wchar_t *v12; // rsi
  wchar_t v13; // ax
  bool v14; // bp
  int v15; // r15d
  void *v16; // rcx
  __int16 v17; // ax
  unsigned __int64 v18; // r15
  int v19; // esi
  _WORD v20[8]; // [rsp+60h] [rbp-A58h] BYREF
  _BYTE v21[1536]; // [rsp+70h] [rbp-A48h] BYREF
  wchar_t Filename[256]; // [rsp+670h] [rbp-448h] BYREF
  wchar_t Ext[256]; // [rsp+870h] [rbp-248h] BYREF

  v2 = a2;
  if ( !a2 )
    return 0;
  _o_wcscpy_s(v20, 776, L"symbols\\");
  if ( *((_QWORD *)this + 413) )
  {
    _o_wcscat_s(v21, 768);
    _o_wcscat_s(v21, 768);
    v4 = -1;
    do
      ++v4;
    while ( v20[v4] );
  }
  else
  {
    v4 = 0;
  }
  _wsplitpath_s(*((const wchar_t **)this + 425), 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
  _o_wcscat_s(v20, 776);
  _o_wcscat_s(v20, 776);
  v5 = -1;
  do
    ++v5;
  while ( v20[v5] );
  v6 = -1;
  do
    ++v6;
  while ( v2[v6] );
  v7 = v5 + v6 + 2;
  v8 = 2 * v7;
  if ( !is_mul_ok(v7, 2u) )
    v8 = -1;
  v9 = (wchar_t *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
  {
    *(_DWORD *)this = 2;
    *((_WORD *)this + 2) = 0;
    return 0;
  }
  v11 = 0;
  if ( !*v2 )
    goto LABEL_44;
  do
  {
    v12 = v9;
    v13 = *v2;
    do
    {
      ++v2;
      if ( v13 == 59 )
        break;
      *v12++ = v13;
      v13 = *v2;
    }
    while ( *v2 );
    if ( v12 != v9 )
    {
      *v12 = 0;
      v14 = !(unsigned int)_o__wcsnicmp(v9, L"SRV*", 4) || !(unsigned int)_o__wcsnicmp(v9, L"SYMSRV*", 7);
      v15 = _o__wcsnicmp(v9, L"CACHE*", 6);
      if ( !v15 )
      {
        v16 = (void *)*((_QWORD *)this + 429);
        if ( v16 )
        {
          free(v16);
          *((_QWORD *)this + 429) = 0;
        }
      }
      if ( v14 || !v15 )
      {
        v11 = LOCATOR::FLocatePdbSymsrv(this, v9);
        if ( v11 )
          break;
        if ( *((_WORD *)this + 1684) == 20557 )
        {
          v19 = *((_DWORD *)this + 848);
          *((_DWORD *)this + 848) = -1;
          v11 = LOCATOR::FLocatePdbSymsrv(this, v9);
          if ( v11 )
            break;
          *((_DWORD *)this + 848) = v19;
        }
        if ( !v15 )
          *((_QWORD *)this + 429) = _o__wcsdup(v9 + 6);
        continue;
      }
      v17 = *(v12 - 1);
      if ( v17 != 92 && v17 != 47 )
        *v12++ = 92;
      v18 = v7 - (v12 - v9);
      _o_wcscpy_s(v12, v18, v20);
      v11 = LOCATOR::FOpenValidate4(this, v9);
      if ( v11 )
        break;
      _o_wcscpy_s(v12, v18, v21);
      v11 = LOCATOR::FOpenValidate4(this, v9);
      if ( v11 )
        break;
      if ( v4 )
      {
        _o_wcscpy_s(v12, v18, &v20[v4]);
        v11 = LOCATOR::FOpenValidate4(this, v9);
        if ( v11 )
          break;
      }
    }
LABEL_44:
    ;
  }
  while ( *v2 );
  PSGSI1::EnumPubsByAddr::release((PSGSI1::EnumPubsByAddr *)v9);
  return v11;
}

```

## disassembly

```asm
0x180086810  push    rbp
0x180086812  push    rsi
0x180086813  push    rdi
0x180086814  push    r12
0x180086816  push    r13
0x180086818  push    r14
0x18008681a  push    r15
0x18008681c  sub     rsp, 0A80h
0x180086823  mov     [rsp+0AB8h+var_A68], 0FFFFFFFFFFFFFFFEh
0x18008682c  mov     [rsp+0AB8h+arg_10], rbx
0x180086834  mov     rax, cs:__security_cookie
0x18008683b  xor     rax, rsp
0x18008683e  mov     [rsp+0AB8h+var_48], rax
0x180086846  mov     rdi, rdx
0x180086849  mov     r14, rcx
0x18008684c  test    rdx, rdx
0x18008684f  jz      loc_180086996
0x180086855  lea     r8, aSymbols_1; "symbols\\"
0x18008685c  mov     edx, 308h
0x180086861  lea     rcx, [rsp+0AB8h+var_A58]
0x180086866  call    cs:__imp__o_wcscpy_s
0x18008686c  mov     r8, [r14+0CE8h]
0x180086873  xor     r15d, r15d
0x180086876  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18008687d  test    r8, r8
0x180086880  jz      short loc_1800868BD
0x180086882  mov     edx, 300h
0x180086887  lea     rcx, [rsp+0AB8h+var_A48]
0x18008688c  call    cs:__imp__o_wcscat_s
0x180086892  lea     r8, asc_180249970; "\\"
0x180086899  mov     edx, 300h
0x18008689e  lea     rcx, [rsp+0AB8h+var_A48]
0x1800868a3  call    cs:__imp__o_wcscat_s
0x1800868a9  lea     rax, [rsp+0AB8h+var_A58]
0x1800868ae  mov     r12, rbx
0x1800868b1  inc     r12
0x1800868b4  cmp     [rax+r12*2], r15w
0x1800868b9  jnz     short loc_1800868B1
0x1800868bb  jmp     short loc_1800868C0
0x1800868bd  mov     r12, r15
0x1800868c0  mov     [rsp+0AB8h+ExtCount], 100h; ExtCount
0x1800868c9  lea     rax, [rsp+0AB8h+var_248]
0x1800868d1  mov     [rsp+0AB8h+Ext], rax; Ext
0x1800868d6  mov     [rsp+0AB8h+FilenameCount], 100h; FilenameCount
0x1800868df  lea     rax, [rsp+0AB8h+var_448]
0x1800868e7  mov     [rsp+0AB8h+Filename], rax; Filename
0x1800868ec  mov     [rsp+0AB8h+DirCount], r15; DirCount
0x1800868f1  xor     r9d, r9d; Dir
0x1800868f4  xor     r8d, r8d; DriveCount
0x1800868f7  xor     edx, edx; Drive
0x1800868f9  mov     rcx, [r14+0D48h]; FullPath
0x180086900  call    cs:__imp__wsplitpath_s
0x180086906  lea     r8, [rsp+0AB8h+var_448]
0x18008690e  mov     edx, 308h
0x180086913  lea     rcx, [rsp+0AB8h+var_A58]
0x180086918  call    cs:__imp__o_wcscat_s
0x18008691e  lea     r8, [rsp+0AB8h+var_248]
0x180086926  mov     edx, 308h
0x18008692b  lea     rcx, [rsp+0AB8h+var_A58]
0x180086930  call    cs:__imp__o_wcscat_s
0x180086936  lea     rax, [rsp+0AB8h+var_A58]
0x18008693b  mov     rcx, rbx
0x18008693e  xchg    ax, ax
0x180086940  inc     rcx
0x180086943  cmp     [rax+rcx*2], r15w
0x180086948  jnz     short loc_180086940
0x18008694a  mov     rax, rbx
0x18008694d  nop     dword ptr [rax]
0x180086950  lea     rax, [rax+1]
0x180086954  cmp     [rdi+rax*2], r15w
0x180086959  jnz     short loc_180086950
0x18008695b  lea     r13, [rax+2]
0x18008695f  add     r13, rcx
0x180086962  mov     eax, 2
0x180086967  mul     r13
0x18008696a  cmovb   rax, rbx
0x18008696e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180086975  mov     rcx, rax; unsigned __int64
0x180086978  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008697d  mov     rbx, rax
0x180086980  mov     [rsp+0AB8h+var_A60], rax
0x180086985  test    rax, rax
0x180086988  jnz     short loc_1800869C3
0x18008698a  mov     dword ptr [r14], 2
0x180086991  mov     [r14+4], r15w
0x180086996  xor     al, al
0x180086998  mov     rcx, [rsp+0AB8h+var_48]
0x1800869a0  xor     rcx, rsp; StackCookie
0x1800869a3  call    __security_check_cookie
0x1800869a8  mov     rbx, [rsp+0AB8h+arg_10]
0x1800869b0  add     rsp, 0A80h
0x1800869b7  pop     r15
0x1800869b9  pop     r14
0x1800869bb  pop     r13
0x1800869bd  pop     r12
0x1800869bf  pop     rdi
0x1800869c0  pop     rsi
0x1800869c1  pop     rbp
0x1800869c2  retn
0x1800869c3  xor     bpl, bpl
0x1800869c6  movzx   eax, word ptr [rdi]
0x1800869c9  test    ax, ax
0x1800869cc  jz      loc_180086B9B
0x1800869d2  mov     rsi, rbx
0x1800869d5  movzx   eax, word ptr [rdi]
0x1800869d8  nop     dword ptr [rax+rax+00000000h]
0x1800869e0  add     rdi, 2
0x1800869e4  cmp     ax, 3Bh ; ';'
0x1800869e8  jz      short loc_1800869F9
0x1800869ea  mov     [rsi], ax
0x1800869ed  add     rsi, 2
0x1800869f1  movzx   eax, word ptr [rdi]
0x1800869f4  test    ax, ax
0x1800869f7  jnz     short loc_1800869E0
0x1800869f9  cmp     rsi, rbx
0x1800869fc  jz      loc_180086B9B
0x180086a02  mov     [rsi], r15w
0x180086a06  mov     r8d, 4
0x180086a0c  lea     rdx, aSrv_2; "SRV*"
0x180086a13  mov     rcx, rbx
0x180086a16  call    cs:__imp__o__wcsnicmp
0x180086a1c  test    eax, eax
0x180086a1e  jz      short loc_180086A3F
0x180086a20  mov     r8d, 7
0x180086a26  lea     rdx, aSymsrv_0; "SYMSRV*"
0x180086a2d  mov     rcx, rbx
0x180086a30  call    cs:__imp__o__wcsnicmp
0x180086a36  test    eax, eax
0x180086a38  jz      short loc_180086A3F
0x180086a3a  xor     bpl, bpl
0x180086a3d  jmp     short loc_180086A42
0x180086a3f  mov     bpl, 1
0x180086a42  mov     r8d, 6
0x180086a48  lea     rdx, aCache; "CACHE*"
0x180086a4f  mov     rcx, rbx
0x180086a52  call    cs:__imp__o__wcsnicmp
0x180086a58  mov     r15d, eax
0x180086a5b  test    eax, eax
0x180086a5d  jnz     short loc_180086A7C
0x180086a5f  mov     rcx, [r14+0D68h]; Block
0x180086a66  test    rcx, rcx
0x180086a69  jz      short loc_180086A7C
0x180086a6b  call    cs:__imp_free
0x180086a71  mov     qword ptr [r14+0D68h], 0
0x180086a7c  test    bpl, bpl
0x180086a7f  jnz     loc_180086B36
0x180086a85  test    r15d, r15d
0x180086a88  jz      loc_180086B36
0x180086a8e  movzx   eax, word ptr [rsi-2]
0x180086a92  cmp     ax, 5Ch ; '\'
0x180086a96  jz      short loc_180086AA7
0x180086a98  cmp     ax, 2Fh ; '/'
0x180086a9c  jz      short loc_180086AA7
0x180086a9e  mov     word ptr [rsi], 5Ch ; '\'
0x180086aa3  add     rsi, 2
0x180086aa7  mov     rax, rsi
0x180086aaa  sub     rax, rbx
0x180086aad  sar     rax, 1
0x180086ab0  mov     r15, r13
0x180086ab3  sub     r15, rax
0x180086ab6  lea     r8, [rsp+0AB8h+var_A58]
0x180086abb  mov     rdx, r15
0x180086abe  mov     rcx, rsi
0x180086ac1  call    cs:__imp__o_wcscpy_s
0x180086ac7  mov     rdx, rbx; wchar_t *
0x180086aca  mov     rcx, r14; this
0x180086acd  call    ?FOpenValidate4@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FOpenValidate4(wchar_t const *)
0x180086ad2  movzx   ebp, al
0x180086ad5  test    al, al
0x180086ad7  jnz     loc_180086BA7
0x180086add  lea     r8, [rsp+0AB8h+var_A48]
0x180086ae2  mov     rdx, r15
0x180086ae5  mov     rcx, rsi
0x180086ae8  call    cs:__imp__o_wcscpy_s
0x180086aee  mov     rdx, rbx; wchar_t *
0x180086af1  mov     rcx, r14; this
0x180086af4  call    ?FOpenValidate4@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FOpenValidate4(wchar_t const *)
0x180086af9  movzx   ebp, al
0x180086afc  test    al, al
0x180086afe  jnz     loc_180086BA7
0x180086b04  test    r12, r12
0x180086b07  jz      loc_180086B98
0x180086b0d  lea     r8, [rsp+0AB8h+var_A58]
0x180086b12  lea     r8, [r8+r12*2]
0x180086b16  mov     rdx, r15
0x180086b19  mov     rcx, rsi
0x180086b1c  call    cs:__imp__o_wcscpy_s
0x180086b22  mov     rdx, rbx; wchar_t *
0x180086b25  mov     rcx, r14; this
0x180086b28  call    ?FOpenValidate4@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FOpenValidate4(wchar_t const *)
0x180086b2d  movzx   ebp, al
0x180086b30  test    al, al
0x180086b32  jnz     short loc_180086BA7
0x180086b34  jmp     short loc_180086B98
0x180086b36  mov     rdx, rbx; wchar_t *
0x180086b39  mov     rcx, r14; this
0x180086b3c  call    ?FLocatePdbSymsrv@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocatePdbSymsrv(wchar_t const *)
0x180086b41  movzx   ebp, al
0x180086b44  test    al, al
0x180086b46  jnz     short loc_180086BA7
0x180086b48  mov     ecx, 504Dh
0x180086b4d  cmp     [r14+0D28h], cx
0x180086b55  jnz     short loc_180086B82
0x180086b57  mov     esi, [r14+0D40h]
0x180086b5e  mov     dword ptr [r14+0D40h], 0FFFFFFFFh
0x180086b69  mov     rdx, rbx; wchar_t *
0x180086b6c  mov     rcx, r14; this
0x180086b6f  call    ?FLocatePdbSymsrv@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocatePdbSymsrv(wchar_t const *)
0x180086b74  movzx   ebp, al
0x180086b77  test    al, al
0x180086b79  jnz     short loc_180086BA7
0x180086b7b  mov     [r14+0D40h], esi
0x180086b82  test    r15d, r15d
0x180086b85  jnz     short loc_180086B98
0x180086b87  lea     rcx, [rbx+0Ch]
0x180086b8b  call    cs:__imp__o__wcsdup
0x180086b91  mov     [r14+0D68h], rax
0x180086b98  xor     r15d, r15d
0x180086b9b  movzx   eax, word ptr [rdi]
0x180086b9e  test    ax, ax
0x180086ba1  jnz     loc_1800869D2
0x180086ba7  mov     rcx, rbx; this
0x180086baa  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180086baf  test    bpl, bpl
0x180086bb2  setnz   al
0x180086bb5  jmp     loc_180086998
```
