# CShellMessageHandler::_ReadFolderData(IPropertyStore *)

- ea: `0x1800039fc`
- end: `0x180003f88`
- name: `?_ReadFolderData@CShellMessageHandler@@AEAAJPEAUIPropertyStore@@@Z`
- size: `1420`
- prototype: `__int64 __fastcall(CShellMessageHandler *__hidden this, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800026fc`

## callees

- `0x1800039fc`
- `0x180003f90`
- `0x180004030`
- `0x180004d60`
- `0x180004f40`
- `0x180004fc0`
- `0x18001e5e0`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003b5e`
- `msvcrt!memcpy_s` at `0x180003db2`
- `msvcrt!memcpy_s` at `0x180003eb3`
- `msvcrt!memcpy_s` at `0x180003b5e`
- `msvcrt!memcpy_s` at `0x180003db2`
- `msvcrt!memcpy_s` at `0x180003eb3`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180003ab6`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180003ab6`
- `SHLWAPI!PathAppendW` at `0x180003cc9`
- `SHLWAPI!PathAppendW` at `0x180003cc9`
- `ole32!CoTaskMemAlloc` at `0x180003b3e`
- `ole32!CoTaskMemAlloc` at `0x180003d92`
- `ole32!CoTaskMemAlloc` at `0x180003e97`
- `ole32!CoTaskMemAlloc` at `0x180003b3e`
- `ole32!CoTaskMemAlloc` at `0x180003d92`
- `ole32!CoTaskMemAlloc` at `0x180003e97`
- `ole32!PropVariantClear` at `0x180003bd2`
- `ole32!PropVariantClear` at `0x180003de9`
- `ole32!PropVariantClear` at `0x180003ee6`
- `ole32!PropVariantClear` at `0x180003f25`
- `ole32!PropVariantClear` at `0x180003bd2`
- `ole32!PropVariantClear` at `0x180003de9`
- `ole32!PropVariantClear` at `0x180003ee6`
- `ole32!PropVariantClear` at `0x180003f25`

## pseudocode

```c
__int64 __fastcall CShellMessageHandler::_ReadFolderData(CShellMessageHandler *this, struct IPropertyStore *a2)
{
  const WCHAR *v4; // r12
  _WORD *v5; // r14
  const WCHAR *v6; // rax
  __int64 v7; // r13
  WCHAR *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  WCHAR *v11; // rcx
  HRESULT v12; // ebx
  size_t v13; // rdx
  __int64 v14; // r15
  __int64 v15; // rax
  __int64 v16; // rbx
  void *v17; // rax
  struct IPropertyStoreVtbl *lpVtbl; // rax
  unsigned __int64 v19; // r8
  unsigned int v20; // edi
  WCHAR *v21; // rsi
  const WCHAR *v22; // rax
  WCHAR *v23; // rdx
  __int64 v24; // r8
  WCHAR *v25; // rcx
  int v26; // eax
  int v27; // eax
  const WCHAR *v28; // rbx
  __int64 v29; // rax
  __int64 v30; // r13
  void *v31; // rax
  struct IPropertyStore *v32; // r13
  __int64 v33; // r15
  void *v34; // rax
  ULONG v35; // [rsp+20h] [rbp-E0h]
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  void *v37; // [rsp+38h] [rbp-C8h]
  __int64 v38; // [rsp+40h] [rbp-C0h]
  int v39; // [rsp+48h] [rbp-B8h]
  PROPVARIANT pvar; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v41; // [rsp+68h] [rbp-98h] BYREF
  PROPVARIANT v42; // [rsp+70h] [rbp-90h] BYREF
  PROPVARIANT pszMore; // [rsp+88h] [rbp-78h] BYREF
  struct IPropertyStore *v44; // [rsp+A0h] [rbp-60h]
  WCHAR pszPath[264]; // [rsp+B0h] [rbp-50h] BYREF

  v44 = a2;
  if ( !a2 )
    return 2147500035LL;
  v4 = &cchOriginalDestLength;
  v5 = 0;
  v6 = &cchOriginalDestLength;
  v41 = 0;
  if ( *((_DWORD *)this + 12) )
    v6 = (const WCHAR *)*((_QWORD *)this + 7);
  v7 = 260;
  v8 = pszPath;
  v9 = 260;
  v10 = 2147483646;
  do
  {
    if ( !v10 )
      break;
    if ( !*v6 )
      break;
    *v8++ = *v6++;
    --v10;
    --v9;
  }
  while ( v9 );
  v11 = v8 - 1;
  v12 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v11 = v8;
  *v11 = 0;
  if ( v9 )
  {
    PathRemoveFileSpecW(pszPath);
    PathIsUnc2(L"winmail.fol");
    v12 = PathCchCombineEx(pszPath, v13, pszPath, L"winmail.fol", v35);
    if ( v12 < 0 )
      return (unsigned int)v12;
    LoadFolderDisplayNameFromFile(pszPath, &v41);
    v5 = v41;
  }
  if ( v12 >= 0 )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( v5 )
    {
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( v5[v15] );
      v16 = 2 * v15 + 2;
      v17 = CoTaskMemAlloc(v16);
      pvar.hVal.QuadPart = (LONGLONG)v17;
      if ( v17 )
      {
        memcpy_s(v17, v16, v5, v16);
        pvar.vt = 31;
        v12 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a2->lpVtbl->SetValue)(
                a2,
                &PKEY_ItemFolderNameDisplay,
                &pvar);
        if ( v12 >= 0 )
        {
          v12 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a2->lpVtbl->SetValue)(
                  a2,
                  &PKEY_ItemFolderPathDisplay,
                  &pvar);
          if ( v12 >= 0 )
            v12 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a2->lpVtbl->SetValue)(
                    a2,
                    &PKEY_ItemFolderPathDisplayNarrow,
                    &pvar);
        }
        PropVariantClear(&pvar);
        if ( v12 < 0 )
          goto LABEL_72;
        lpVtbl = a2->lpVtbl;
        memset(&pszMore, 0, sizeof(pszMore));
        v12 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))lpVtbl->GetValue)(
                a2,
                &PKEY_ItemNameDisplay,
                &pszMore);
        if ( v12 < 0 )
          goto LABEL_72;
        if ( pszMore.vt != 31 )
          goto LABEL_68;
        v38 = 0;
        v37 = 0;
        v39 = 0;
        v36 = 0;
        v19 = -1;
        do
          ++v19;
        while ( v5[v19] );
        v12 = STRW::Append((STRW *)&v36, v5, v19);
        if ( v12 < 0 )
          goto LABEL_67;
        v20 = v36;
        v21 = (WCHAR *)v37;
        v22 = (const WCHAR *)v37;
        if ( !v36 )
          v22 = &cchOriginalDestLength;
        v23 = pszPath;
        v24 = 2147483646;
        do
        {
          if ( !v24 )
            break;
          if ( !*v22 )
            break;
          *v23++ = *v22++;
          --v24;
          --v7;
        }
        while ( v7 );
        v25 = v23 - 1;
        v12 = v7 == 0 ? 0x8007007A : 0;
        if ( v7 )
          v25 = v23;
        *v25 = 0;
        if ( v7 )
        {
          if ( !PathAppendW(pszPath, pszMore.bstrVal) )
          {
LABEL_41:
            if ( !v20 || v21[v20 - 1] != 92 )
            {
              v12 = STRW::Append((STRW *)&v36, L"\\");
              if ( v12 < 0 )
                goto LABEL_67;
            }
            v27 = STRW::Append((STRW *)&v36, pszMore.bstrVal);
            v21 = (WCHAR *)v37;
            v12 = v27;
            v20 = v36;
LABEL_45:
            if ( v12 >= 0 )
            {
              memset(&v42, 0, sizeof(v42));
              if ( v20 )
              {
                v28 = v21;
                if ( !v21 )
                {
                  v12 = -2147024809;
                  goto LABEL_67;
                }
              }
              else
              {
                v28 = &cchOriginalDestLength;
              }
              v29 = -1;
              do
                ++v29;
              while ( v28[v29] );
              v30 = 2 * v29 + 2;
              v31 = CoTaskMemAlloc(v30);
              v42.hVal.QuadPart = (LONGLONG)v31;
              if ( !v31 )
              {
                v12 = -2147024882;
                goto LABEL_67;
              }
              memcpy_s(v31, v30, v28, v30);
              v32 = v44;
              v42.vt = 31;
              v12 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v44->lpVtbl->SetValue)(
                      v44,
                      &PKEY_ItemPathDisplay,
                      &v42);
              PropVariantClear(&v42);
              if ( v12 < 0 )
                goto LABEL_67;
              memset_0(v21, 0, 2LL * v20);
              v36 = 0;
              v12 = STRW::Append((STRW *)&v36, pszMore.bstrVal);
              if ( v12 < 0 )
                goto LABEL_67;
              v12 = STRW::Append((STRW *)&v36, L" (");
              if ( v12 < 0 )
                goto LABEL_67;
              v12 = STRW::Append((STRW *)&v36, v5);
              if ( v12 < 0 )
                goto LABEL_67;
              v12 = STRW::Append((STRW *)&v36, L")");
              if ( v12 < 0 )
                goto LABEL_67;
              if ( v36 && (v4 = (const WCHAR *)v37) == 0 )
              {
                v12 = -2147024809;
              }
              else
              {
                do
                  ++v14;
                while ( v4[v14] );
                v33 = 2 * v14 + 2;
                v34 = CoTaskMemAlloc(v33);
                pvar.hVal.QuadPart = (LONGLONG)v34;
                if ( v34 )
                {
                  memcpy_s(v34, v33, v4, v33);
                  pvar.vt = 31;
                  v12 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v32->lpVtbl->SetValue)(
                          v32,
                          &PKEY_ItemPathDisplayNarrow,
                          &pvar);
                  PropVariantClear(&pvar);
                  goto LABEL_67;
                }
                v12 = -2147024882;
              }
              memset(&pvar, 0, sizeof(pvar));
            }
LABEL_67:
            STRW::~STRW((STRW *)&v36);
LABEL_68:
            PropVariantClear(&pszMore);
            goto LABEL_72;
          }
          memset_0(v21, 0, 2LL * v20);
          v36 = 0;
          v26 = STRW::Append((STRW *)&v36, pszPath);
          v21 = (WCHAR *)v37;
          v12 = v26;
          v20 = v36;
        }
        if ( v12 != -2147467259 )
          goto LABEL_45;
        goto LABEL_41;
      }
      v12 = -2147024882;
    }
    else
    {
      v12 = -2147024809;
    }
    memset(&pvar, 0, sizeof(pvar));
LABEL_72:
    if ( v5 )
      ((void (__fastcall *)(LPMALLOC, _WORD *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v5);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800039fc  push    rbp
0x1800039fe  push    rbx
0x1800039ff  push    rsi
0x180003a00  push    rdi
0x180003a01  push    r12
0x180003a03  push    r13
0x180003a05  push    r14
0x180003a07  push    r15
0x180003a09  lea     rbp, [rsp-1D8h]
0x180003a11  sub     rsp, 2D8h
0x180003a18  mov     rax, cs:__security_cookie
0x180003a1f  xor     rax, rsp
0x180003a22  mov     [rbp+210h+var_50], rax
0x180003a29  xor     esi, esi
0x180003a2b  mov     [rbp+210h+var_270], rdx
0x180003a2f  mov     rdi, rdx
0x180003a32  test    rdx, rdx
0x180003a35  jnz     short loc_180003A41
0x180003a37  mov     eax, 80004003h
0x180003a3c  jmp     loc_180003F65
0x180003a41  lea     r12, cchOriginalDestLength
0x180003a48  mov     r14, rsi
0x180003a4b  mov     rax, r12
0x180003a4e  mov     [rsp+310h+var_2A8], rsi
0x180003a53  cmp     [rcx+30h], esi
0x180003a56  jz      short loc_180003A5C
0x180003a58  mov     rax, [rcx+38h]
0x180003a5c  mov     r13d, 104h
0x180003a62  lea     r8, [rbp+210h+pszPath]
0x180003a66  mov     edx, r13d
0x180003a69  mov     ecx, 7FFFFFFEh
0x180003a6e  test    rcx, rcx
0x180003a71  jz      short loc_180003A92
0x180003a73  movzx   r9d, word ptr [rax]
0x180003a77  test    r9w, r9w
0x180003a7b  jz      short loc_180003A92
0x180003a7d  mov     [r8], r9w
0x180003a81  add     rax, 2
0x180003a85  add     r8, 2
0x180003a89  dec     rcx
0x180003a8c  sub     rdx, 1
0x180003a90  jnz     short loc_180003A6E
0x180003a92  mov     rax, rdx
0x180003a95  lea     rcx, [r8-2]
0x180003a99  neg     rax
0x180003a9c  sbb     ebx, ebx
0x180003a9e  not     ebx
0x180003aa0  and     ebx, 8007007Ah
0x180003aa6  test    rdx, rdx
0x180003aa9  cmovnz  rcx, r8
0x180003aad  mov     [rcx], si
0x180003ab0  jz      short loc_180003B02
0x180003ab2  lea     rcx, [rbp+210h+pszPath]; pszPath
0x180003ab6  call    cs:__imp_PathRemoveFileSpecW
0x180003abc  lea     r8, IsBackslash
0x180003ac3  xor     edx, edx
0x180003ac5  lea     rcx, pszMore; "winmail.fol"
0x180003acc  call    PathIsUnc2
0x180003ad1  lea     r9, pszMore; "winmail.fol"
0x180003ad8  lea     r8, [rbp+210h+pszPath]; pszPathIn
0x180003adc  lea     rcx, [rbp+210h+pszPath]; pszPathOut
0x180003ae0  call    PathCchCombineEx
0x180003ae5  mov     ebx, eax
0x180003ae7  test    eax, eax
0x180003ae9  js      loc_180003F63
0x180003aef  lea     rdx, [rsp+310h+var_2A8]
0x180003af4  lea     rcx, [rbp+210h+pszPath]
0x180003af8  call    LoadFolderDisplayNameFromFile
0x180003afd  mov     r14, [rsp+310h+var_2A8]
0x180003b02  test    ebx, ebx
0x180003b04  js      loc_180003F63
0x180003b0a  xor     eax, eax
0x180003b0c  xorps   xmm0, xmm0
0x180003b0f  mov     qword ptr [rsp+310h+pvar+10h], rax
0x180003b14  movups  xmmword ptr [rsp+310h+pvar], xmm0
0x180003b19  test    r14, r14
0x180003b1c  jz      loc_180003F34
0x180003b22  or      r15, 0FFFFFFFFFFFFFFFFh
0x180003b26  mov     rax, r15
0x180003b29  inc     rax
0x180003b2c  cmp     [r14+rax*2], si
0x180003b31  jnz     short loc_180003B29
0x180003b33  lea     rbx, ds:2[rax*2]
0x180003b3b  mov     rcx, rbx; cb
0x180003b3e  call    cs:__imp_CoTaskMemAlloc
0x180003b44  mov     qword ptr [rsp+310h+pvar+8], rax
0x180003b49  test    rax, rax
0x180003b4c  jz      loc_180003F2D
0x180003b52  mov     r9, rbx; SourceSize
0x180003b55  mov     r8, r14; Source
0x180003b58  mov     rdx, rbx; DestinationSize
0x180003b5b  mov     rcx, rax; Destination
0x180003b5e  call    cs:__imp_memcpy_s
0x180003b64  mov     eax, 1Fh
0x180003b69  lea     r8, [rsp+310h+pvar]
0x180003b6e  mov     word ptr [rsp+310h+pvar], ax
0x180003b73  lea     rdx, PKEY_ItemFolderNameDisplay
0x180003b7a  mov     rax, [rdi]
0x180003b7d  mov     rcx, rdi
0x180003b80  mov     rax, [rax+30h]
0x180003b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b89  mov     ebx, eax
0x180003b8b  test    eax, eax
0x180003b8d  js      short loc_180003BCD
0x180003b8f  mov     rax, [rdi]
0x180003b92  lea     r8, [rsp+310h+pvar]
0x180003b97  lea     rdx, PKEY_ItemFolderPathDisplay
0x180003b9e  mov     rcx, rdi
0x180003ba1  mov     rax, [rax+30h]
0x180003ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003baa  mov     ebx, eax
0x180003bac  test    eax, eax
0x180003bae  js      short loc_180003BCD
0x180003bb0  mov     rax, [rdi]
0x180003bb3  lea     r8, [rsp+310h+pvar]
0x180003bb8  lea     rdx, PKEY_ItemFolderPathDisplayNarrow
0x180003bbf  mov     rcx, rdi
0x180003bc2  mov     rax, [rax+30h]
0x180003bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bcb  mov     ebx, eax
0x180003bcd  lea     rcx, [rsp+310h+pvar]; pvar
0x180003bd2  call    cs:__imp_PropVariantClear
0x180003bd8  test    ebx, ebx
0x180003bda  js      loc_180003F48
0x180003be0  xor     eax, eax
0x180003be2  lea     r8, [rbp+210h+pszMore]
0x180003be6  mov     [rbp+210h+var_278], rax
0x180003bea  lea     rdx, PKEY_ItemNameDisplay
0x180003bf1  mov     rax, [rdi]
0x180003bf4  xorps   xmm0, xmm0
0x180003bf7  mov     rcx, rdi
0x180003bfa  movups  xmmword ptr [rbp+210h+pszMore], xmm0
0x180003bfe  mov     rax, [rax+28h]
0x180003c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c07  mov     ebx, eax
0x180003c09  test    eax, eax
0x180003c0b  js      loc_180003F48
0x180003c11  mov     eax, 1Fh
0x180003c16  cmp     word ptr [rbp+210h+pszMore], ax
0x180003c1a  jnz     loc_180003F21
0x180003c20  xor     eax, eax
0x180003c22  mov     [rsp+310h+var_2D0], rsi
0x180003c27  mov     [rsp+310h+var_2D8], rsi
0x180003c2c  mov     edi, eax
0x180003c2e  mov     [rsp+310h+var_2C8], eax
0x180003c32  mov     [rsp+310h+var_2E0], eax
0x180003c36  test    r14, r14
0x180003c39  jz      short loc_180003C6F
0x180003c3b  mov     r8, r15
0x180003c3e  inc     r8; unsigned __int64
0x180003c41  cmp     [r14+r8*2], si
0x180003c46  jnz     short loc_180003C3E
0x180003c48  mov     rdx, r14; unsigned __int16 *
0x180003c4b  lea     rcx, [rsp+310h+var_2E0]; this
0x180003c50  call    ?Append@STRW@@QEAAJPEBG_K@Z; STRW::Append(ushort const *,unsigned __int64)
0x180003c55  mov     ebx, eax
0x180003c57  test    eax, eax
0x180003c59  js      loc_180003F17
0x180003c5f  mov     edi, [rsp+310h+var_2E0]
0x180003c63  mov     rsi, [rsp+310h+var_2D8]
0x180003c68  mov     rax, rsi
0x180003c6b  test    edi, edi
0x180003c6d  jnz     short loc_180003C72
0x180003c6f  mov     rax, r12
0x180003c72  lea     rdx, [rbp+210h+pszPath]
0x180003c76  mov     r8d, 7FFFFFFEh
0x180003c7c  xor     r9d, r9d
0x180003c7f  test    r8, r8
0x180003c82  jz      short loc_180003CA0
0x180003c84  movzx   ecx, word ptr [rax]
0x180003c87  test    cx, cx
0x180003c8a  jz      short loc_180003CA0
0x180003c8c  mov     [rdx], cx
0x180003c8f  add     rax, 2
0x180003c93  add     rdx, 2
0x180003c97  dec     r8
0x180003c9a  sub     r13, 1
0x180003c9e  jnz     short loc_180003C7F
0x180003ca0  mov     rax, r13
0x180003ca3  lea     rcx, [rdx-2]
0x180003ca7  neg     rax
0x180003caa  sbb     ebx, ebx
0x180003cac  not     ebx
0x180003cae  and     ebx, 8007007Ah
0x180003cb4  test    r13, r13
0x180003cb7  cmovnz  rcx, rdx
0x180003cbb  mov     [rcx], r9w
0x180003cbf  jz      short loc_180003D04
0x180003cc1  mov     rdx, [rbp+210h+pszMore+8]; pszMore
0x180003cc5  lea     rcx, [rbp+210h+pszPath]; pszPath
0x180003cc9  call    cs:__imp_PathAppendW
0x180003ccf  test    eax, eax
0x180003cd1  jz      short loc_180003D0C
0x180003cd3  mov     r8d, edi
0x180003cd6  xor     edx, edx; Val
0x180003cd8  add     r8, r8; Size
0x180003cdb  mov     rcx, rsi; void *
0x180003cde  call    memset_0
0x180003ce3  lea     rdx, [rbp+210h+pszPath]; unsigned __int16 *
0x180003ce7  mov     [rsp+310h+var_2E0], 0
0x180003cef  lea     rcx, [rsp+310h+var_2E0]; this
0x180003cf4  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180003cf9  mov     rsi, [rsp+310h+var_2D8]
0x180003cfe  mov     ebx, eax
0x180003d00  mov     edi, [rsp+310h+var_2E0]
0x180003d04  cmp     ebx, 80004005h
0x180003d0a  jnz     short loc_180003D4E
0x180003d0c  test    edi, edi
0x180003d0e  jz      short loc_180003D1A
0x180003d10  lea     eax, [rdi-1]
0x180003d13  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x180003d18  jz      short loc_180003D35
0x180003d1a  lea     rdx, Control; "\\"
0x180003d21  lea     rcx, [rsp+310h+var_2E0]; this
0x180003d26  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180003d2b  mov     ebx, eax
0x180003d2d  test    eax, eax
0x180003d2f  js      loc_180003F17
0x180003d35  mov     rdx, [rbp+210h+pszMore+8]; unsigned __int16 *
0x180003d39  lea     rcx, [rsp+310h+var_2E0]; this
0x180003d3e  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180003d43  mov     rsi, [rsp+310h+var_2D8]
0x180003d48  mov     ebx, eax
0x180003d4a  mov     edi, [rsp+310h+var_2E0]
0x180003d4e  xor     ecx, ecx
0x180003d50  test    ebx, ebx
0x180003d52  js      loc_180003F17
0x180003d58  xor     eax, eax
0x180003d5a  xorps   xmm0, xmm0
0x180003d5d  mov     qword ptr [rbp+210h+var_2A0+10h], rax
0x180003d61  movups  xmmword ptr [rsp+310h+var_2A0], xmm0
0x180003d66  test    edi, edi
0x180003d68  jnz     short loc_180003D6F
0x180003d6a  mov     rbx, r12
0x180003d6d  jmp     short loc_180003D7B
0x180003d6f  mov     rbx, rsi
0x180003d72  test    rsi, rsi
0x180003d75  jz      loc_180003F12
0x180003d7b  mov     rax, r15
0x180003d7e  inc     rax
0x180003d81  cmp     [rbx+rax*2], cx
0x180003d85  jnz     short loc_180003D7E
0x180003d87  lea     r13, ds:2[rax*2]
0x180003d8f  mov     rcx, r13; cb
0x180003d92  call    cs:__imp_CoTaskMemAlloc
0x180003d98  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x180003d9d  test    rax, rax
0x180003da0  jz      loc_180003F0B
0x180003da6  mov     r9, r13; SourceSize
0x180003da9  mov     r8, rbx; Source
0x180003dac  mov     rdx, r13; DestinationSize
0x180003daf  mov     rcx, rax; Destination
0x180003db2  call    cs:__imp_memcpy_s
0x180003db8  mov     r13, [rbp+210h+var_270]
0x180003dbc  lea     r8, [rsp+310h+var_2A0]
0x180003dc1  mov     eax, 1Fh
0x180003dc6  lea     rdx, PKEY_ItemPathDisplay
0x180003dcd  mov     word ptr [rsp+310h+var_2A0], ax
0x180003dd2  mov     rcx, r13
0x180003dd5  mov     rax, [r13+0]
0x180003dd9  mov     rax, [rax+30h]
0x180003ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de2  lea     rcx, [rsp+310h+var_2A0]; pvar
0x180003de7  mov     ebx, eax
0x180003de9  call    cs:__imp_PropVariantClear
0x180003def  test    ebx, ebx
0x180003df1  js      loc_180003F17
0x180003df7  mov     r8d, edi
0x180003dfa  xor     edx, edx; Val
0x180003dfc  add     r8, r8; Size
0x180003dff  mov     rcx, rsi; void *
0x180003e02  call    memset_0
0x180003e07  mov     rdx, [rbp+210h+pszMore+8]; unsigned __int16 *
0x180003e0b  lea     rcx, [rsp+310h+var_2E0]; this
0x180003e10  xor     esi, esi
0x180003e12  mov     [rsp+310h+var_2E0], esi
0x180003e16  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180003e1b  mov     ebx, eax
0x180003e1d  test    eax, eax
0x180003e1f  js      loc_180003F17
0x180003e25  lea     rdx, asc_1800D8284; " ("
0x180003e2c  lea     rcx, [rsp+310h+var_2E0]; this
0x180003e31  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180003e36  mov     ebx, eax
0x180003e38  test    eax, eax
0x180003e3a  js      loc_180003F17
0x180003e40  mov     rdx, r14; unsigned __int16 *
0x180003e43  lea     rcx, [rsp+310h+var_2E0]; this
0x180003e48  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180003e4d  mov     ebx, eax
0x180003e4f  test    eax, eax
0x180003e51  js      loc_180003F17
0x180003e57  lea     rdx, asc_1800D8280; ")"
0x180003e5e  lea     rcx, [rsp+310h+var_2E0]; this
0x180003e63  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180003e68  mov     ebx, eax
0x180003e6a  test    eax, eax
0x180003e6c  js      loc_180003F17
0x180003e72  cmp     [rsp+310h+var_2E0], esi
0x180003e76  jz      short loc_180003E82
  ... truncated ...
```
