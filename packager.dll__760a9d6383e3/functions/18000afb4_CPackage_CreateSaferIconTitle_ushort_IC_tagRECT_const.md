# CPackage::_CreateSaferIconTitle(ushort *,_IC *,tagRECT const *)

- ea: `0x18000afb4`
- end: `0x18000b321`
- name: `?_CreateSaferIconTitle@CPackage@@IEAAXPEAGPEAU_IC@@PEBUtagRECT@@@Z`
- size: `877`
- prototype: `void __fastcall(CPackage *this, CPackage *, const WCHAR *, const struct tagRECT *)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180008c8c`
- `0x18000a474`
- `0x18000a624`
- `0x18000baa0`
- `0x18000bbc0`

## callees

- `0x1800041d4`
- `0x18000afb4`
- `0x18000b94c`
- `0x18000cbf0`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18000b121`
- `SHLWAPI!PathFindExtensionW` at `0x18000b134`
- `SHLWAPI!PathFindExtensionW` at `0x18000b121`
- `SHLWAPI!PathFindExtensionW` at `0x18000b134`
- `SHLWAPI!PathRemoveBlanksW` at `0x18000b195`
- `SHLWAPI!PathRemoveBlanksW` at `0x18000b195`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b015`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b030`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b1c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b015`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b030`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000b1c5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b0c0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b1ee`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b0c0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b1ee`
- `KERNEL32!lstrcmpiW` at `0x18000b174`
- `KERNEL32!lstrcmpiW` at `0x18000b174`

## pseudocode

```c
void __fastcall CPackage::_CreateSaferIconTitle(
        CPackage *this,
        CPackage *a2,
        const WCHAR *a3,
        const struct tagRECT *a4)
{
  __int64 v7; // r15
  unsigned __int16 *v8; // r12
  __int64 v9; // r14
  __int64 v10; // rax
  WCHAR *v11; // rcx
  WCHAR *v12; // rdx
  WCHAR *v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rax
  const unsigned __int16 *v16; // r13
  int v17; // r15d
  LPWSTR ExtensionW; // r12
  CPackage *v19; // rcx
  __int64 v20; // rax
  const unsigned __int16 *v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rax
  const unsigned __int16 *v24; // r8
  CPackage *v25; // rax
  __int64 v26; // r14
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rax
  const WCHAR *lpString2; // [rsp+48h] [rbp-B8h]
  va_list Arguments[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h]
  WCHAR Source[20]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[80]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszPath[264]; // [rsp+130h] [rbp+30h] BYREF

  if ( *((_DWORD *)this + 26) != 1 )
  {
    v15 = *((_QWORD *)this + 14);
    if ( !v15 || !*(_WORD *)(v15 + 72) )
    {
      v26 = 2147483646;
      v27 = (unsigned __int16 *)(a3 + 264);
      v14 = 260;
      do
      {
        if ( !v26 )
          break;
        if ( !*v27 )
          break;
        *(_WORD *)a2 = *v27++;
        a2 = (CPackage *)((char *)a2 + 2);
        --v26;
        --v14;
      }
      while ( v14 );
      goto LABEL_41;
    }
    v16 = a3 + 264;
    lpString2 = PathFindExtensionW(a3 + 264);
    v17 = 80;
    ExtensionW = PathFindExtensionW((LPCWSTR)(*((_QWORD *)this + 14) + 72LL));
    while ( ExtensionW && lpString2 && *ExtensionW && lstrcmpiW(ExtensionW, lpString2) )
    {
      StringCchCopyW(pszPath, (unsigned int)v17, v16);
      PathRemoveBlanksW(pszPath);
      Arguments[0] = (va_list)pszPath;
      Arguments[1] = (va_list)ExtensionW;
      v32 = 0;
      LoadStringW(g_hinst, 0xBC2u, Source, 20);
      if ( !FormatMessageW(0x2400u, Source, 0, 0, (LPWSTR)a2, 0x104u, Arguments) )
      {
        v20 = 2147483646;
        v21 = v16;
        v22 = 260;
        v19 = a2;
        do
        {
          if ( !v20 )
            break;
          if ( !*v21 )
            break;
          *(_WORD *)v19 = *v21++;
          v19 = (CPackage *)((char *)v19 + 2);
          --v20;
          --v22;
        }
        while ( v22 );
LABEL_30:
        v25 = (CPackage *)((char *)v19 - 2);
        if ( v22 )
          v25 = v19;
        *(_WORD *)v25 = 0;
      }
      if ( a4 )
      {
        *(_OWORD *)Arguments = 0;
        CPackage::_IconCalcSize(v19, (struct tagRECT *)Arguments, (const unsigned __int16 *)a2);
        if ( SLODWORD(Arguments[1]) >= a4->right )
        {
          v17 = 2 * v17 / 3;
          if ( v17 >= 2 )
            continue;
        }
      }
      return;
    }
    v23 = 2147483646;
    v24 = v16;
    v22 = 260;
    v19 = a2;
    do
    {
      if ( !v23 )
        break;
      if ( !*v24 )
        break;
      *(_WORD *)v19 = *v24++;
      v19 = (CPackage *)((char *)v19 + 2);
      --v23;
      --v22;
    }
    while ( v22 );
    goto LABEL_30;
  }
  v7 = 80;
  LoadStringW(g_hinst, 0xBC6u, Buffer, 80);
  LoadStringW(g_hinst, 0xBC7u, Source, 20);
  v8 = (unsigned __int16 *)(a3 + 264);
  v9 = 2147483646;
  v10 = 2147483646;
  v11 = pszPath;
  v12 = (WCHAR *)(a3 + 264);
  do
  {
    if ( !v10 )
      break;
    if ( !*v12 )
      break;
    *v11++ = *v12++;
    --v10;
    --v7;
  }
  while ( v7 );
  v13 = v11 - 1;
  v32 = 0;
  v14 = 260;
  if ( v7 )
    v13 = v11;
  *v13 = 0;
  Arguments[0] = (va_list)pszPath;
  Arguments[1] = (va_list)Buffer;
  if ( !FormatMessageW(0x2400u, Source, 0, 0, (LPWSTR)a2, 0x104u, Arguments) )
  {
    do
    {
      if ( !v9 )
        break;
      if ( !*v8 )
        break;
      *(_WORD *)a2 = *v8++;
      a2 = (CPackage *)((char *)a2 + 2);
      --v9;
      --v14;
    }
    while ( v14 );
LABEL_41:
    v28 = (unsigned __int16 *)((char *)a2 - 2);
    if ( v14 )
      v28 = (unsigned __int16 *)a2;
    *v28 = 0;
  }
}

```

## disassembly

```asm
0x18000afb4  mov     [rsp-8+arg_18], rbx
0x18000afb9  push    rbp
0x18000afba  push    rsi
0x18000afbb  push    rdi
0x18000afbc  push    r12
0x18000afbe  push    r13
0x18000afc0  push    r14
0x18000afc2  push    r15
0x18000afc4  lea     rbp, [rsp-250h]
0x18000afcc  sub     rsp, 350h
0x18000afd3  mov     rax, cs:__security_cookie
0x18000afda  xor     rax, rsp
0x18000afdd  mov     [rbp+280h+var_40], rax
0x18000afe4  cmp     dword ptr [rcx+68h], 1
0x18000afe8  mov     r13, r8
0x18000afeb  mov     [rsp+380h+var_340], r9
0x18000aff0  mov     rdi, rdx
0x18000aff3  mov     rsi, rcx
0x18000aff6  jnz     loc_18000B0FE
0x18000affc  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b003  lea     r8, [rbp+280h+Buffer]; lpBuffer
0x18000b007  mov     r15d, 50h ; 'P'
0x18000b00d  mov     edx, 0BC6h; uID
0x18000b012  mov     r9d, r15d; cchBufferMax
0x18000b015  call    cs:__imp_LoadStringW
0x18000b01b  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b022  lea     r9d, [r15-3Ch]; cchBufferMax
0x18000b026  lea     r8, [rsp+380h+Source]; lpBuffer
0x18000b02b  mov     edx, 0BC7h; uID
0x18000b030  call    cs:__imp_LoadStringW
0x18000b036  lea     r12, [r13+210h]
0x18000b03d  mov     r14d, 7FFFFFFEh
0x18000b043  mov     eax, r14d
0x18000b046  lea     rcx, [rbp+280h+pszPath]
0x18000b04a  mov     rdx, r12
0x18000b04d  xor     ebx, ebx
0x18000b04f  test    rax, rax
0x18000b052  jz      short loc_18000B073
0x18000b054  movzx   r8d, word ptr [rdx]
0x18000b058  test    r8w, r8w
0x18000b05c  jz      short loc_18000B073
0x18000b05e  mov     [rcx], r8w
0x18000b062  add     rdx, 2
0x18000b066  add     rcx, 2
0x18000b06a  dec     rax
0x18000b06d  sub     r15, 1
0x18000b071  jnz     short loc_18000B04F
0x18000b073  lea     rax, [rcx-2]
0x18000b077  mov     [rsp+380h+var_320], rbx
0x18000b07c  test    r15, r15
0x18000b07f  lea     rdx, [rsp+380h+Source]; lpSource
0x18000b084  mov     esi, 104h
0x18000b089  cmovnz  rax, rcx
0x18000b08d  xor     r9d, r9d; dwLanguageId
0x18000b090  xor     r8d, r8d; dwMessageId
0x18000b093  mov     ecx, 2400h; dwFlags
0x18000b098  mov     [rax], bx
0x18000b09b  lea     rax, [rbp+280h+pszPath]
0x18000b09f  mov     [rsp+380h+var_330], rax
0x18000b0a4  lea     rax, [rbp+280h+Buffer]
0x18000b0a8  mov     [rsp+380h+var_330+8], rax
0x18000b0ad  lea     rax, [rsp+380h+var_330]
0x18000b0b2  mov     [rsp+380h+Arguments], rax; Arguments
0x18000b0b7  mov     [rsp+380h+nSize], esi; nSize
0x18000b0bb  mov     [rsp+380h+lpBuffer], rdi; lpBuffer
0x18000b0c0  call    cs:__imp_FormatMessageW
0x18000b0c6  test    eax, eax
0x18000b0c8  jnz     loc_18000B2F7
0x18000b0ce  test    r14, r14
0x18000b0d1  jz      loc_18000B2E9
0x18000b0d7  movzx   eax, word ptr [r12]
0x18000b0dc  test    ax, ax
0x18000b0df  jz      loc_18000B2E9
0x18000b0e5  mov     [rdi], ax
0x18000b0e8  add     r12, 2
0x18000b0ec  add     rdi, 2
0x18000b0f0  dec     r14
0x18000b0f3  sub     rsi, 1
0x18000b0f7  jnz     short loc_18000B0CE
0x18000b0f9  jmp     loc_18000B2E9
0x18000b0fe  mov     rax, [rcx+70h]
0x18000b102  xor     ebx, ebx
0x18000b104  test    rax, rax
0x18000b107  jz      loc_18000B2B6
0x18000b10d  cmp     [rax+48h], bx
0x18000b111  jz      loc_18000B2B6
0x18000b117  add     r13, 210h
0x18000b11e  mov     rcx, r13; pszPath
0x18000b121  call    cs:__imp_PathFindExtensionW
0x18000b127  mov     rcx, [rsi+70h]
0x18000b12b  add     rcx, 48h ; 'H'; pszPath
0x18000b12f  mov     [rsp+380h+lpString2], rax
0x18000b134  call    cs:__imp_PathFindExtensionW
0x18000b13a  mov     esi, 104h
0x18000b13f  lea     r15d, [rbx+50h]
0x18000b143  mov     r12, rax
0x18000b146  mov     r14d, 7FFFFFFEh
0x18000b14c  test    r12, r12
0x18000b14f  jz      loc_18000B22A
0x18000b155  mov     rax, [rsp+380h+lpString2]
0x18000b15a  test    rax, rax
0x18000b15d  jz      loc_18000B22A
0x18000b163  cmp     [r12], bx
0x18000b168  jz      loc_18000B22A
0x18000b16e  mov     rdx, rax; lpString2
0x18000b171  mov     rcx, r12; lpString1
0x18000b174  call    cs:__imp_lstrcmpiW
0x18000b17a  test    eax, eax
0x18000b17c  jz      loc_18000B22A
0x18000b182  mov     edx, r15d; unsigned __int64
0x18000b185  lea     rcx, [rbp+280h+pszPath]; unsigned __int16 *
0x18000b189  mov     r8, r13; unsigned __int16 *
0x18000b18c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b191  lea     rcx, [rbp+280h+pszPath]; pszPath
0x18000b195  call    cs:__imp_PathRemoveBlanksW
0x18000b19b  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b1a2  lea     rax, [rbp+280h+pszPath]
0x18000b1a6  mov     r9d, 14h; cchBufferMax
0x18000b1ac  mov     [rsp+380h+var_330], rax
0x18000b1b1  lea     r8, [rsp+380h+Source]; lpBuffer
0x18000b1b6  mov     [rsp+380h+var_330+8], r12
0x18000b1bb  mov     edx, 0BC2h; uID
0x18000b1c0  mov     [rsp+380h+var_320], rbx
0x18000b1c5  call    cs:__imp_LoadStringW
0x18000b1cb  lea     rax, [rsp+380h+var_330]
0x18000b1d0  xor     r9d, r9d; dwLanguageId
0x18000b1d3  mov     [rsp+380h+Arguments], rax; Arguments
0x18000b1d8  lea     rdx, [rsp+380h+Source]; lpSource
0x18000b1dd  mov     [rsp+380h+nSize], esi; nSize
0x18000b1e1  xor     r8d, r8d; dwMessageId
0x18000b1e4  mov     ecx, 2400h; dwFlags
0x18000b1e9  mov     [rsp+380h+lpBuffer], rdi; lpBuffer
0x18000b1ee  call    cs:__imp_FormatMessageW
0x18000b1f4  test    eax, eax
0x18000b1f6  jnz     short loc_18000B268
0x18000b1f8  mov     rax, r14
0x18000b1fb  mov     r8, r13
0x18000b1fe  mov     rdx, rsi
0x18000b201  mov     rcx, rdi
0x18000b204  test    rax, rax
0x18000b207  jz      short loc_18000B25A
0x18000b209  movzx   r9d, word ptr [r8]
0x18000b20d  test    r9w, r9w
0x18000b211  jz      short loc_18000B25A
0x18000b213  mov     [rcx], r9w
0x18000b217  add     r8, 2
0x18000b21b  add     rcx, 2
0x18000b21f  dec     rax
0x18000b222  sub     rdx, 1
0x18000b226  jnz     short loc_18000B204
0x18000b228  jmp     short loc_18000B25A
0x18000b22a  mov     rax, r14
0x18000b22d  mov     r8, r13
0x18000b230  mov     rdx, rsi
0x18000b233  mov     rcx, rdi
0x18000b236  test    rax, rax
0x18000b239  jz      short loc_18000B25A
0x18000b23b  movzx   r9d, word ptr [r8]
0x18000b23f  test    r9w, r9w
0x18000b243  jz      short loc_18000B25A
0x18000b245  mov     [rcx], r9w
0x18000b249  add     r8, 2
0x18000b24d  add     rcx, 2; this
0x18000b251  dec     rax
0x18000b254  sub     rdx, 1
0x18000b258  jnz     short loc_18000B236
0x18000b25a  test    rdx, rdx
0x18000b25d  lea     rax, [rcx-2]
0x18000b261  cmovnz  rax, rcx
0x18000b265  mov     [rax], bx
0x18000b268  cmp     [rsp+380h+var_340], rbx
0x18000b26d  jz      loc_18000B2F7
0x18000b273  xorps   xmm0, xmm0
0x18000b276  lea     rdx, [rsp+380h+var_330]; struct tagRECT *
0x18000b27b  mov     r8, rdi; unsigned __int16 *
0x18000b27e  movups  xmmword ptr [rsp+380h+var_330], xmm0
0x18000b283  call    ?_IconCalcSize@CPackage@@IEAAHPEAUtagRECT@@PEBG@Z; CPackage::_IconCalcSize(tagRECT *,ushort const *)
0x18000b288  mov     rcx, [rsp+380h+var_340]
0x18000b28d  mov     eax, [rcx+8]
0x18000b290  cmp     dword ptr [rsp+380h+var_330+8], eax
0x18000b294  jl      short loc_18000B2F7
0x18000b296  lea     ecx, [r15+r15]
0x18000b29a  mov     eax, 55555556h
0x18000b29f  imul    ecx
0x18000b2a1  mov     eax, edx
0x18000b2a3  shr     eax, 1Fh
0x18000b2a6  add     edx, eax
0x18000b2a8  mov     r15d, edx
0x18000b2ab  cmp     edx, 2
0x18000b2ae  jge     loc_18000B14C
0x18000b2b4  jmp     short loc_18000B2F7
0x18000b2b6  mov     r14d, 7FFFFFFEh
0x18000b2bc  lea     rax, [r8+210h]
0x18000b2c3  mov     esi, 104h
0x18000b2c8  test    r14, r14
0x18000b2cb  jz      short loc_18000B2E9
0x18000b2cd  movzx   ecx, word ptr [rax]
0x18000b2d0  test    cx, cx
0x18000b2d3  jz      short loc_18000B2E9
0x18000b2d5  mov     [rdi], cx
0x18000b2d8  add     rax, 2
0x18000b2dc  add     rdi, 2
0x18000b2e0  dec     r14
0x18000b2e3  sub     rsi, 1
0x18000b2e7  jnz     short loc_18000B2C8
0x18000b2e9  test    rsi, rsi
0x18000b2ec  lea     rax, [rdi-2]
0x18000b2f0  cmovnz  rax, rdi
0x18000b2f4  mov     [rax], bx
0x18000b2f7  mov     rcx, [rbp+280h+var_40]
0x18000b2fe  xor     rcx, rsp; StackCookie
0x18000b301  call    __security_check_cookie
0x18000b306  mov     rbx, [rsp+380h+arg_18]
0x18000b30e  add     rsp, 350h
0x18000b315  pop     r15
0x18000b317  pop     r14
0x18000b319  pop     r13
0x18000b31b  pop     r12
0x18000b31d  pop     rdi
0x18000b31e  pop     rsi
0x18000b31f  pop     rbp
0x18000b320  retn
```
