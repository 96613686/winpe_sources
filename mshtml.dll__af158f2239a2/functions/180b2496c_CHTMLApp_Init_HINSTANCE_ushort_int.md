# CHTMLApp::Init(HINSTANCE__ *,ushort *,int)

- ea: `0x180b2496c`
- end: `0x180b24d80`
- name: `?Init@CHTMLApp@@QEAAJPEAUHINSTANCE__@@PEAGH@Z`
- size: `1044`
- prototype: `__int64 __fastcall(CHTMLApp *__hidden this, HINSTANCE, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180b23d00`

## callees

- `0x18003dcd8`
- `0x180040330`
- `0x1801bf344`
- `0x1801bf528`
- `0x1801c0acc`
- `0x1801c0b08`
- `0x180200040`
- `0x18043c328`
- `0x180b24580`
- `0x180b2496c`
- `0x180b255f0`
- `0x180b27f10`
- `0x1810c2d3a`
- `0x1810d1010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180b24bcb`
- `msvcrt!wcsstr` at `0x180b24bcb`
- `KERNEL32!CompareStringW` at `0x180b24aa0`
- `KERNEL32!CompareStringW` at `0x180b24b5e`
- `KERNEL32!CompareStringW` at `0x180b24aa0`
- `KERNEL32!CompareStringW` at `0x180b24b5e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathGetArgsW` at `0x180b24b93`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathGetArgsW` at `0x180b24b93`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x180b24c67`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x180b24c67`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x180b24c70`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathUnquoteSpacesW` at `0x180b24c70`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterClassObject` at `0x180b24b2d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRegisterClassObject` at `0x180b24b2d`
- `ole32!OleInitialize` at `0x180b249c5`
- `ole32!OleInitialize` at `0x180b249c5`
- `SHLWAPI!PathRemoveArgsW` at `0x180b24c14`
- `SHLWAPI!PathRemoveArgsW` at `0x180b24c14`
- `urlmon!CreateURLMonikerEx` at `0x180b24c91`
- `urlmon!CreateURLMonikerEx` at `0x180b24c91`

## pseudocode

```c
__int64 __fastcall CHTMLApp::Init(CHTMLApp *this, HINSTANCE a2, unsigned __int16 *a3, int a4)
{
  struct IUnknown *v4; // r14
  HRESULT v5; // eax
  CHTMLApp *v6; // rcx
  unsigned int AppWindow; // ebx
  bool v8; // zf
  const WCHAR *v9; // r8
  const WCHAR *lpString2; // r9
  WCHAR v11; // cx
  unsigned __int16 v12; // r10
  WCHAR v13; // dx
  int v14; // eax
  const WCHAR *v15; // r8
  const WCHAR *i; // r9
  int v17; // eax
  WCHAR v18; // cx
  unsigned __int16 v19; // r10
  WCHAR v20; // dx
  int v21; // eax
  int v22; // eax
  WCHAR *v23; // rsi
  const wchar_t *ArgsW; // rax
  const wchar_t *v25; // rbx
  char v26; // di
  wchar_t *v27; // rax
  const unsigned __int16 *v28; // rdi
  __int64 v29; // rdx
  struct IMoniker *v30; // r8
  __int64 v31; // rax
  void *v32; // rdi
  int v33; // eax
  void *v34; // r8
  unsigned __int16 v36; // [rsp+30h] [rbp-28h] BYREF
  void *v37; // [rsp+38h] [rbp-20h] BYREF
  LPMONIKER ppmk; // [rsp+40h] [rbp-18h] BYREF
  LPCWSTR pszPath[2]; // [rsp+48h] [rbp-10h] BYREF

  qword_18158C930 = a2;
  v4 = 0;
  dword_18158CA04 = a4;
  ppmk = 0;
  CStr::Set((CStr *)&qword_18158CA20, a3);
  v5 = OleInitialize(0);
  AppWindow = v5;
  v8 = v5 == 0;
  if ( v5 >= 0 )
  {
    dword_18158CA30 |= 1u;
    v8 = v5 == 0;
  }
  if ( !v8 )
    goto LABEL_65;
  AppWindow = CHTMLApp::CreateAppWindow(v6);
  if ( AppWindow )
    goto LABEL_65;
  v9 = (const WCHAR *)qword_18158CA20;
  if ( !qword_18158CA20 )
    goto LABEL_18;
  for ( lpString2 = L"/Embedding"; ; ++lpString2 )
  {
    v13 = *v9;
    if ( !*v9 )
    {
      v14 = -(*lpString2 != 0);
      goto LABEL_17;
    }
    v11 = *lpString2;
    if ( v13 != *lpString2 )
      break;
LABEL_14:
    ++v9;
  }
  v12 = v11 - 65;
  if ( (unsigned __int16)(v13 - 65) > 0x19u )
  {
    if ( v12 > 0x19u )
      goto LABEL_20;
  }
  else
  {
    v13 += 32;
    if ( v12 > 0x19u )
      goto LABEL_13;
  }
  v11 += 32;
LABEL_13:
  if ( v13 == v11 )
    goto LABEL_14;
LABEL_20:
  if ( ((v13 | v11) & 0xFF80) == 0 )
    goto LABEL_18;
  v17 = CompareStringW(0x409u, 0x30001u, v9, -1, lpString2, -1);
  if ( v17 <= 0 )
    goto LABEL_18;
  v14 = v17 - 2;
LABEL_17:
  if ( !v14 )
    goto LABEL_34;
LABEL_18:
  v15 = (const WCHAR *)qword_18158CA20;
  if ( !qword_18158CA20 )
  {
LABEL_38:
    pszPath[0] = 0;
    CStr::Set((CStr *)pszPath, (const struct CStr *)&qword_18158CA20);
    v23 = (WCHAR *)pszPath[0];
    if ( !pszPath[0] )
    {
      AppWindow = -2147467259;
      goto LABEL_56;
    }
    ArgsW = PathGetArgsW(pszPath[0]);
    v25 = ArgsW;
    v26 = 0;
    if ( ArgsW )
    {
      if ( !wcsncmp_0(ArgsW, L"{1E460BD7-F1C3-4B2E-88BF-4E770A288AF5}", 0x26u) )
      {
        v25 += 38;
        v27 = wcsstr(v25, L"{1E460BD7-F1C3-4B2E-88BF-4E770A288AF5}");
        if ( v27 )
        {
          v28 = v25;
          *v27 = 0;
          v25 = v27 + 38;
        }
        else
        {
          v28 = 0;
        }
        if ( v28 && *v28 )
        {
          CStr::Set((CStr *)&qword_18158CA20, v28);
          CStr::Append((CStr *)&qword_18158CA20, v25);
LABEL_55:
          AppWindow = CreateURLMonikerEx(0, v28, &ppmk, 1u);
LABEL_56:
          CStr::_Free((CStr *)pszPath);
          if ( !AppWindow )
          {
            if ( ShouldBlockHTA(ppmk, v29, v30) )
            {
              AppWindow = -2147467260;
            }
            else
            {
              v37 = 0;
              v31 = MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 32);
              v32 = (void *)v31;
              if ( v31 )
              {
                *(_DWORD *)(v31 + 16) = 0;
                *(_QWORD *)v31 = &CServerObject::`vftable'{for `IPersistMoniker'};
                *(_QWORD *)(v31 + 8) = &CServerObject::`vftable'{for `IOleObject'};
                *(_QWORD *)(v31 + 24) = &theApp;
                v33 = CServerObject::QueryInterface((CServerObject *)v31, &IID_IPersistMoniker, &v37);
                AppWindow = v33;
                if ( v33 >= 0 )
                {
                  v4 = (struct IUnknown *)v37;
                  if ( !v33 )
                    AppWindow = (*(__int64 (__fastcall **)(void *, __int64, LPMONIKER))(*(_QWORD *)v37 + 40LL))(
                                  v37,
                                  1,
                                  ppmk);
                }
                else
                {
                  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v32, v34);
                  v4 = (struct IUnknown *)v37;
                }
              }
              else
              {
                AppWindow = -2147024882;
              }
            }
          }
          goto LABEL_65;
        }
        v26 = 0;
      }
      else
      {
        v26 = 1;
      }
    }
    PathRemoveArgsW(v23);
    v37 = 0;
    CStr::Set((CStr *)&v37, v23);
    if ( v25 )
    {
      if ( v26 )
      {
        v36 = 32;
        CStr::Append((CStr *)&v37, &v36, 1u);
      }
      CStr::Append((CStr *)&v37, v25);
    }
    CStr::Set((CStr *)&qword_18158CA20, (const struct CStr *)&v37);
    PathRemoveBlanksW(v23);
    PathUnquoteSpacesW(v23);
    CStr::_Free((CStr *)&v37);
    v28 = v23;
    goto LABEL_55;
  }
  for ( i = L"-Embedding"; ; ++i )
  {
    v20 = *v15;
    if ( !*v15 )
    {
      v21 = -(*i != 0);
      goto LABEL_33;
    }
    v18 = *i;
    if ( v20 != *i )
      break;
LABEL_30:
    ++v15;
  }
  v19 = v18 - 65;
  if ( (unsigned __int16)(v20 - 65) > 0x19u )
  {
    if ( v19 > 0x19u )
      goto LABEL_35;
  }
  else
  {
    v20 += 32;
    if ( v19 > 0x19u )
      goto LABEL_29;
  }
  v18 += 32;
LABEL_29:
  if ( v20 == v18 )
    goto LABEL_30;
LABEL_35:
  if ( ((v20 | v18) & 0xFF80) == 0 )
    goto LABEL_38;
  v22 = CompareStringW(0x409u, 0x30001u, v15, -1, i, -1);
  if ( v22 <= 0 )
    goto LABEL_38;
  v21 = v22 - 2;
LABEL_33:
  if ( v21 )
    goto LABEL_38;
LABEL_34:
  CStr::_Free((CStr *)&qword_18158CA20);
  qword_18158CA20 = 0;
  CoRegisterClassObject(&CLSID_HTMLApplication, &pUnk, 4u, 0, &dwRegister);
LABEL_65:
  ReleaseInterface((struct IUnknown *)ppmk);
  ReleaseInterface(v4);
  return AppWindow;
}

```

## disassembly

```asm
0x180b2496c  mov     rax, rsp
0x180b2496f  mov     [rax+20h], r9d
0x180b24973  mov     [rax+18h], r8
0x180b24977  mov     [rax+10h], rdx
0x180b2497b  mov     [rax+8], rcx
0x180b2497f  push    rbp
0x180b24980  push    rbx
0x180b24981  push    rsi
0x180b24982  push    rdi
0x180b24983  push    r12
0x180b24985  push    r13
0x180b24987  push    r14
0x180b24989  push    r15
0x180b2498b  mov     rbp, rsp
0x180b2498e  sub     rsp, 58h
0x180b24992  mov     rax, [rbp+arg_8]
0x180b24996  lea     r12, qword_18158CA20
0x180b2499d  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x180b249a1  xor     r15d, r15d
0x180b249a4  mov     cs:qword_18158C930, rax
0x180b249ab  mov     rcx, r12; this
0x180b249ae  mov     eax, [rbp+arg_18]
0x180b249b1  mov     r14d, r15d
0x180b249b4  mov     cs:dword_18158CA04, eax
0x180b249ba  mov     [rbp+ppmk], r15
0x180b249be  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x180b249c3  xor     ecx, ecx; pvReserved
0x180b249c5  call    cs:__imp_OleInitialize
0x180b249cb  mov     ebx, eax
0x180b249cd  test    eax, eax
0x180b249cf  js      short loc_180B249DA
0x180b249d1  or      cs:dword_18158CA30, 1
0x180b249d8  test    eax, eax
0x180b249da  jnz     loc_180B24D5C
0x180b249e0  call    ?CreateAppWindow@CHTMLApp@@QEAAJXZ; CHTMLApp::CreateAppWindow(void)
0x180b249e5  mov     ebx, eax
0x180b249e7  test    eax, eax
0x180b249e9  jnz     loc_180B24D5C
0x180b249ef  mov     r8, cs:qword_18158CA20
0x180b249f6  lea     r13d, [rax+20h]
0x180b249fa  or      esi, 0FFFFFFFFh
0x180b249fd  mov     di, 19h
0x180b24a01  test    r8, r8
0x180b24a04  jz      short loc_180B24A61
0x180b24a06  lea     r9, aEmbedding_0; "/Embedding"
0x180b24a0d  jmp     short loc_180B24A47
0x180b24a0f  movzx   ecx, word ptr [r9]
0x180b24a13  cmp     dx, cx
0x180b24a16  jz      short loc_180B24A3F
0x180b24a18  lea     eax, [rdx-41h]
0x180b24a1b  lea     r10d, [rcx-41h]
0x180b24a1f  cmp     ax, di
0x180b24a22  ja      short loc_180B24A30
0x180b24a24  add     dx, r13w
0x180b24a28  cmp     r10w, di
0x180b24a2c  ja      short loc_180B24A3A
0x180b24a2e  jmp     short loc_180B24A36
0x180b24a30  cmp     r10w, di
0x180b24a34  ja      short loc_180B24A7A
0x180b24a36  add     cx, r13w
0x180b24a3a  cmp     dx, cx
0x180b24a3d  jnz     short loc_180B24A7A
0x180b24a3f  add     r8, 2; lpString1
0x180b24a43  add     r9, 2
0x180b24a47  movzx   edx, word ptr [r8]
0x180b24a4b  test    dx, dx
0x180b24a4e  jnz     short loc_180B24A0F
0x180b24a50  movzx   eax, word ptr [r9]
0x180b24a54  neg     ax
0x180b24a57  sbb     eax, eax
0x180b24a59  test    eax, eax
0x180b24a5b  jz      loc_180B24AFD
0x180b24a61  mov     r8, cs:qword_18158CA20
0x180b24a68  test    r8, r8
0x180b24a6b  jz      loc_180B24B6D
0x180b24a71  lea     r9, aEmbedding; "-Embedding"
0x180b24a78  jmp     short loc_180B24AE7
0x180b24a7a  movzx   ecx, cx
0x180b24a7d  movzx   eax, dx
0x180b24a80  or      ecx, eax
0x180b24a82  test    ecx, 0FFFFFF80h
0x180b24a88  jz      short loc_180B24A61
0x180b24a8a  mov     [rsp+58h+cchCount2], esi; cchCount2
0x180b24a8e  mov     edx, 30001h; dwCmpFlags
0x180b24a93  mov     [rsp+58h+lpString2], r9; lpString2
0x180b24a98  mov     ecx, 409h; Locale
0x180b24a9d  mov     r9d, esi; cchCount1
0x180b24aa0  call    cs:__imp_CompareStringW
0x180b24aa6  test    eax, eax
0x180b24aa8  jle     short loc_180B24A61
0x180b24aaa  add     eax, 0FFFFFFFEh
0x180b24aad  jmp     short loc_180B24A59
0x180b24aaf  movzx   ecx, word ptr [r9]
0x180b24ab3  cmp     dx, cx
0x180b24ab6  jz      short loc_180B24ADF
0x180b24ab8  lea     eax, [rdx-41h]
0x180b24abb  lea     r10d, [rcx-41h]
0x180b24abf  cmp     ax, di
0x180b24ac2  ja      short loc_180B24AD0
0x180b24ac4  add     dx, r13w
0x180b24ac8  cmp     r10w, di
0x180b24acc  ja      short loc_180B24ADA
0x180b24ace  jmp     short loc_180B24AD6
0x180b24ad0  cmp     r10w, di
0x180b24ad4  ja      short loc_180B24B38
0x180b24ad6  add     cx, r13w
0x180b24ada  cmp     dx, cx
0x180b24add  jnz     short loc_180B24B38
0x180b24adf  add     r8, 2; lpString1
0x180b24ae3  add     r9, 2
0x180b24ae7  movzx   edx, word ptr [r8]
0x180b24aeb  test    dx, dx
0x180b24aee  jnz     short loc_180B24AAF
0x180b24af0  movzx   eax, word ptr [r9]
0x180b24af4  neg     ax
0x180b24af7  sbb     eax, eax
0x180b24af9  test    eax, eax
0x180b24afb  jnz     short loc_180B24B6D
0x180b24afd  mov     rcx, r12; this
0x180b24b00  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180b24b05  xor     r9d, r9d; flags
0x180b24b08  mov     cs:qword_18158CA20, r15
0x180b24b0f  lea     rax, dwRegister
0x180b24b16  lea     rdx, pUnk; pUnk
0x180b24b1d  mov     [rsp+58h+lpString2], rax; lpdwRegister
0x180b24b22  lea     rcx, CLSID_HTMLApplication; rclsid
0x180b24b29  lea     r8d, [r9+4]; dwClsContext
0x180b24b2d  call    cs:__imp_CoRegisterClassObject
0x180b24b33  jmp     loc_180B24D5C
0x180b24b38  movzx   ecx, cx
0x180b24b3b  movzx   eax, dx
0x180b24b3e  or      ecx, eax
0x180b24b40  test    ecx, 0FFFFFF80h
0x180b24b46  jz      short loc_180B24B6D
0x180b24b48  mov     [rsp+58h+cchCount2], esi; cchCount2
0x180b24b4c  mov     edx, 30001h; dwCmpFlags
0x180b24b51  mov     [rsp+58h+lpString2], r9; lpString2
0x180b24b56  mov     ecx, 409h; Locale
0x180b24b5b  mov     r9d, esi; cchCount1
0x180b24b5e  call    cs:__imp_CompareStringW
0x180b24b64  test    eax, eax
0x180b24b66  jle     short loc_180B24B6D
0x180b24b68  add     eax, 0FFFFFFFEh
0x180b24b6b  jmp     short loc_180B24AF9
0x180b24b6d  mov     rdx, r12; struct CStr *
0x180b24b70  mov     [rbp+pszPath], r15
0x180b24b74  lea     rcx, [rbp+pszPath]; this
0x180b24b78  call    ?Set@CStr@@QEAAJAEBV1@@Z; CStr::Set(CStr const &)
0x180b24b7d  mov     rsi, [rbp+pszPath]
0x180b24b81  test    rsi, rsi
0x180b24b84  jnz     short loc_180B24B90
0x180b24b86  mov     ebx, 80004005h
0x180b24b8b  jmp     loc_180B24C99
0x180b24b90  mov     rcx, rsi; pszPath
0x180b24b93  call    cs:__imp_PathGetArgsW
0x180b24b99  mov     rbx, rax
0x180b24b9c  mov     dil, r15b
0x180b24b9f  test    rax, rax
0x180b24ba2  jz      short loc_180B24C11
0x180b24ba4  mov     r8d, 26h ; '&'; MaxCount
0x180b24baa  lea     rdx, a1e460bd7F1c34b; "{1E460BD7-F1C3-4B2E-88BF-4E770A288AF5}"
0x180b24bb1  mov     rcx, rax; String1
0x180b24bb4  call    wcsncmp_0
0x180b24bb9  test    eax, eax
0x180b24bbb  jnz     short loc_180B24C0E
0x180b24bbd  add     rbx, 4Ch ; 'L'
0x180b24bc1  lea     rdx, a1e460bd7F1c34b; "{1E460BD7-F1C3-4B2E-88BF-4E770A288AF5}"
0x180b24bc8  mov     rcx, rbx; Str
0x180b24bcb  call    cs:__imp_wcsstr
0x180b24bd1  test    rax, rax
0x180b24bd4  jz      short loc_180B24BE3
0x180b24bd6  mov     rdi, rbx
0x180b24bd9  mov     [rax], r15w
0x180b24bdd  lea     rbx, [rax+4Ch]
0x180b24be1  jmp     short loc_180B24BE6
0x180b24be3  mov     rdi, r15
0x180b24be6  test    rdi, rdi
0x180b24be9  jz      short loc_180B24C09
0x180b24beb  cmp     [rdi], r15w
0x180b24bef  jz      short loc_180B24C09
0x180b24bf1  mov     rdx, rdi; unsigned __int16 *
0x180b24bf4  mov     rcx, r12; this
0x180b24bf7  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x180b24bfc  mov     rdx, rbx; unsigned __int16 *
0x180b24bff  mov     rcx, r12; this
0x180b24c02  call    ?Append@CStr@@QEAAJPEBG@Z; CStr::Append(ushort const *)
0x180b24c07  jmp     short loc_180B24C82
0x180b24c09  mov     dil, r15b
0x180b24c0c  jmp     short loc_180B24C11
0x180b24c0e  mov     dil, 1
0x180b24c11  mov     rcx, rsi; pszPath
0x180b24c14  call    cs:__imp_PathRemoveArgsW
0x180b24c1a  mov     rdx, rsi; unsigned __int16 *
0x180b24c1d  mov     [rbp+var_20], r15
0x180b24c21  lea     rcx, [rbp+var_20]; this
0x180b24c25  call    ?Set@CStr@@QEAAJPEBG@Z; CStr::Set(ushort const *)
0x180b24c2a  test    rbx, rbx
0x180b24c2d  jz      short loc_180B24C58
0x180b24c2f  test    dil, dil
0x180b24c32  jz      short loc_180B24C4C
0x180b24c34  mov     r8d, 1; unsigned int
0x180b24c3a  mov     [rbp+var_28], r13w
0x180b24c3f  lea     rdx, [rbp+var_28]; unsigned __int16 *
0x180b24c43  lea     rcx, [rbp+var_20]; this
0x180b24c47  call    ?Append@CStr@@QEAAJPEBGI@Z; CStr::Append(ushort const *,uint)
0x180b24c4c  mov     rdx, rbx; unsigned __int16 *
0x180b24c4f  lea     rcx, [rbp+var_20]; this
0x180b24c53  call    ?Append@CStr@@QEAAJPEBG@Z; CStr::Append(ushort const *)
0x180b24c58  lea     rdx, [rbp+var_20]; struct CStr *
0x180b24c5c  mov     rcx, r12; this
0x180b24c5f  call    ?Set@CStr@@QEAAJAEBV1@@Z; CStr::Set(CStr const &)
0x180b24c64  mov     rcx, rsi; pszPath
0x180b24c67  call    cs:__imp_PathRemoveBlanksW
0x180b24c6d  mov     rcx, rsi; lpsz
0x180b24c70  call    cs:__imp_PathUnquoteSpacesW
0x180b24c76  lea     rcx, [rbp+var_20]; this
0x180b24c7a  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180b24c7f  mov     rdi, rsi
0x180b24c82  mov     r9d, 1; dwFlags
0x180b24c88  lea     r8, [rbp+ppmk]; ppmk
0x180b24c8c  mov     rdx, rdi; szURL
0x180b24c8f  xor     ecx, ecx; pMkCtx
0x180b24c91  call    cs:__imp_CreateURLMonikerEx
0x180b24c97  mov     ebx, eax
0x180b24c99  lea     rcx, [rbp+pszPath]; this
0x180b24c9d  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180b24ca2  test    ebx, ebx
0x180b24ca4  jnz     loc_180B24D5C
0x180b24caa  mov     rcx, [rbp+ppmk]; struct IMoniker *
0x180b24cae  call    ?ShouldBlockHTA@@YAHPEAUIMoniker@@@Z; ShouldBlockHTA(IMoniker *)
0x180b24cb3  test    eax, eax
0x180b24cb5  jz      short loc_180B24CC1
0x180b24cb7  mov     ebx, 80004004h
0x180b24cbc  jmp     loc_180B24D5C
0x180b24cc1  mov     rcx, cs:g_hProcessHeap
0x180b24cc8  mov     rdx, r13
0x180b24ccb  mov     [rbp+var_20], r15
0x180b24ccf  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180b24cd4  mov     rdi, rax
0x180b24cd7  test    rax, rax
0x180b24cda  jz      short loc_180B24D57
0x180b24cdc  lea     rax, ??_7CServerObject@@6BIPersistMoniker@@@; const CServerObject::`vftable'{for `IPersistMoniker'}
0x180b24ce3  mov     [rdi+10h], r15d
0x180b24ce7  mov     [rdi], rax
0x180b24cea  lea     r8, [rbp+var_20]; void **
0x180b24cee  lea     rax, ??_7CServerObject@@6BIOleObject@@@; const CServerObject::`vftable'{for `IOleObject'}
0x180b24cf5  mov     rcx, rdi; this
0x180b24cf8  mov     [rdi+8], rax
0x180b24cfc  lea     rdx, IID_IPersistMoniker; struct _GUID *
0x180b24d03  lea     rax, ?theApp@@3VCHTMLApp@@A; CHTMLApp theApp
0x180b24d0a  mov     [rdi+18h], rax
0x180b24d0e  call    ?QueryInterface@CServerObject@@UEAAJAEBU_GUID@@PEAPEAX@Z; CServerObject::QueryInterface(_GUID const &,void * *)
0x180b24d13  mov     ebx, eax
0x180b24d15  test    eax, eax
0x180b24d17  jns     short loc_180B24D2E
0x180b24d19  mov     rcx, cs:g_hProcessHeap; this
0x180b24d20  mov     rdx, rdi; void *
0x180b24d23  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180b24d28  mov     r14, [rbp+var_20]
0x180b24d2c  jmp     short loc_180B24D5C
0x180b24d2e  mov     r14, [rbp+var_20]
0x180b24d32  jnz     short loc_180B24D5C
0x180b24d34  mov     rax, [r14]
0x180b24d37  xor     r9d, r9d
0x180b24d3a  mov     r8, [rbp+ppmk]
0x180b24d3e  mov     rcx, r14
0x180b24d41  mov     dword ptr [rsp+58h+lpString2], r15d
0x180b24d46  mov     rax, [rax+28h]
0x180b24d4a  lea     edx, [r9+1]
0x180b24d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180b24d53  mov     ebx, eax
0x180b24d55  jmp     short loc_180B24D5C
0x180b24d57  mov     ebx, 8007000Eh
0x180b24d5c  mov     rcx, [rbp+ppmk]; struct IUnknown *
0x180b24d60  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180b24d65  mov     rcx, r14; struct IUnknown *
0x180b24d68  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180b24d6d  mov     eax, ebx
0x180b24d6f  add     rsp, 58h
0x180b24d73  pop     r15
0x180b24d75  pop     r14
0x180b24d77  pop     r13
0x180b24d79  pop     r12
0x180b24d7b  pop     rdi
0x180b24d7c  pop     rsi
0x180b24d7d  pop     rbx
0x180b24d7e  pop     rbp
0x180b24d7f  retn
```
