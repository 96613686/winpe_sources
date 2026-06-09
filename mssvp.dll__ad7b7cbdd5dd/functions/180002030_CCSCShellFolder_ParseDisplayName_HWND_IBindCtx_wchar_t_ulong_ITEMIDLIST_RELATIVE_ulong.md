# CCSCShellFolder::ParseDisplayName(HWND__ *,IBindCtx *,wchar_t *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180002030`
- end: `0x180002798`
- name: `?ParseDisplayName@CCSCShellFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEA_WPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `1896`
- prototype: `__int64 __fastcall(CCSCShellFolder *__hidden this, HWND, struct IBindCtx *, wchar_t *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002030`
- `0x180003da4`
- `0x180003df0`
- `0x180004100`
- `0x180004120`
- `0x180004890`
- `0x180005210`
- `0x18000557c`
- `0x180006270`
- `0x180006dcc`
- `0x180014bcc`
- `0x180015014`
- `0x180016360`
- `0x180038ab0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002430`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002430`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180002372`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180002372`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002492`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002618`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002492`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002227`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800021dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800021dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800021c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800021c9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000214c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002177`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000214c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002177`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002528`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000257c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800025f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002653`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800026cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002528`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000257c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800025f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002653`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800026cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002285`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000235e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002411`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000235e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002411`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002221`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000226e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002221`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000226e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800022ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800022ae`

## string_xrefs

- `0x1800024cc`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCSCShellFolder::ParseDisplayName(
        CCSCShellFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        wchar_t *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  struct IBindCtx *v8; // r15
  unsigned int *v9; // r12
  __int64 v10; // rdi
  __int64 v11; // rax
  signed int Error; // r14d
  __int64 v14; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  PSID *v17; // r15
  __int64 v18; // r12
  __int64 v19; // rax
  const wchar_t *v20; // rcx
  __int64 v21; // r8
  WCHAR *v22; // r9
  wchar_t v23; // dx
  int v24; // edx
  WCHAR *v25; // rcx
  int v26; // eax
  __int64 v27; // r11
  WCHAR *v28; // rax
  const wchar_t *v29; // r8
  wchar_t *i; // rdx
  wchar_t v31; // ax
  wchar_t *v32; // rcx
  __int64 v33; // rax
  CPidlMgr *v34; // rsi
  const wchar_t *v35; // rdx
  CCSCShellFolder *v36; // rcx
  int v37; // r9d
  struct _ITEMIDLIST_RELATIVE *ItemIdList; // rax
  int v39; // eax
  unsigned int lpString2; // [rsp+20h] [rbp-E0h]
  DWORD ReturnLength[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct IBindCtx *v42; // [rsp+38h] [rbp-C8h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v45; // [rsp+60h] [rbp-A0h]
  CCSCShellFolder *v46; // [rsp+68h] [rbp-98h]
  PROPVARIANT v47[4]; // [rsp+70h] [rbp-90h] BYREF
  void **v48; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR lpBuffer; // [rsp+98h] [rbp-68h]
  int cchBufferMax[2]; // [rsp+A0h] [rbp-60h]
  wchar_t v51[196]; // [rsp+A8h] [rbp-58h] BYREF
  void **v52; // [rsp+230h] [rbp+130h] BYREF
  wchar_t *v53; // [rsp+238h] [rbp+138h]
  __int64 v54; // [rsp+240h] [rbp+140h]
  wchar_t v55[196]; // [rsp+248h] [rbp+148h] BYREF
  WCHAR Buffer[1024]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v57[2048]; // [rsp+BD0h] [rbp+AD0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1418h] [rbp+1318h]

  v8 = a3;
  v42 = a3;
  v46 = this;
  v9 = a7;
  v45 = a7;
  if ( a6 && a4 )
  {
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    if ( !(_DWORD)v11 )
      return 2147942487LL;
    Error = 0;
    *a6 = 0;
    if ( a5 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a4[v14] );
      *a5 = v14;
    }
    v53 = v55;
    v54 = 193;
    v55[0] = 0;
    v52 = &TLMString<192,64,32767>::`vftable';
    lpBuffer = v51;
    *(_QWORD *)cchBufferMax = 193;
    v51[0] = 0;
    v48 = &TLMString<192,64,32767>::`vftable';
    if ( CompareStringW(0x7Fu, 1u, a4, -1, L"*", -1) != 2 && CompareStringW(0x7Fu, 1u, a4, -1, L"csc://", -1) != 2 )
    {
      Error = -2147467259;
      ((void (__fastcall *)(void ***, wchar_t *, _QWORD, __int64))v52[4])(&v52, a4, 0, 0xFFFFFFFFLL);
      goto LABEL_87;
    }
    memset_0(Buffer, 0, sizeof(Buffer));
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) && (Error = ResultFromLastError(), Error < 0)
      || !TokenHandle )
    {
LABEL_58:
      if ( Error < 0 )
        goto LABEL_87;
      CLMString::operator=(&v52, L"csc://");
      ((void (__fastcall *)(void ***, WCHAR *, _QWORD, __int64))v52[4])(&v52, Buffer, HIDWORD(v54), 0xFFFFFFFFLL);
      if ( !LoadStringW(hInstance, 0x70u, lpBuffer, cchBufferMax[0]) )
        Error = -2147467259;
      v33 = -1;
      do
        ++v33;
      while ( lpBuffer[v33] );
      if ( (unsigned int)v33 >= cchBufferMax[0] )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
          (const char *)0xCE,
          lpString2);
      cchBufferMax[1] = v33;
      lpBuffer[(unsigned int)v33] = 0;
      if ( Error < 0 )
        goto LABEL_87;
      CComPropVariant::CComPropVariant((CComPropVariant *)&pvar, v53);
      v34 = (CCSCShellFolder *)((char *)v46 + 80);
      Error = CPidlMgr::SetProperty((CCSCShellFolder *)((char *)v46 + 80), &PKEY_ParsingPath, &pvar);
      PropVariantClear((PROPVARIANT *)&pvar);
      if ( Error < 0 )
        goto LABEL_87;
      CComPropVariant::CComPropVariant((CComPropVariant *)&pvar, lpBuffer);
      Error = CPidlMgr::SetProperty(v34, &PKEY_ItemPathDisplay, &pvar);
      if ( Error >= 0 )
        Error = CPidlMgr::SetProperty(v34, &PKEY_ItemNameDisplay, &pvar);
      PropVariantClear((PROPVARIANT *)&pvar);
      if ( Error < 0 )
        goto LABEL_87;
      ReturnLength[0] = 0;
      Error = CCSCShellFolder::CheckPolicy(v36, v35, (int *)ReturnLength, v37, lpString2);
      if ( Error < 0 )
        goto LABEL_87;
      if ( !ReturnLength[0] )
        goto LABEL_91;
      memset(&pvar, 0, sizeof(pvar));
      pvar.vt = 19;
      pvar.lVal = 0x8000;
      Error = CPidlMgr::SetProperty(v34, &PKEY_SFGAOFlags, &pvar);
      PropVariantClear((PROPVARIANT *)&pvar);
      if ( Error >= 0 )
      {
        if ( !LoadStringW(hInstance, 0xD8u, Buffer, 2048) )
        {
          Error = -2147418113;
          goto LABEL_87;
        }
        CComPropVariant::CComPropVariant((CComPropVariant *)v47, Buffer);
        Error = CPidlMgr::SetProperty(v34, &PKEY_TooltipText, (struct tagPROPVARIANT *)v47);
        PropVariantClear(v47);
        if ( Error >= 0 )
        {
LABEL_91:
          if ( !v8 )
            goto LABEL_79;
          v42 = 0;
          if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, struct IBindCtx **))v8->lpVtbl->GetObjectParam)(
                 v8,
                 L"Search Control Panel Folders",
                 &v42) >= 0 )
          {
            memset(&pvar, 0, sizeof(pvar));
            pvar.vt = 11;
            pvar.lVal = -1;
            Error = CPidlMgr::SetProperty(v34, &PKEY_AllowFolderEnum, &pvar);
            PropVariantClear((PROPVARIANT *)&pvar);
          }
          ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&v42);
          if ( Error >= 0 )
          {
LABEL_79:
            ItemIdList = CPidlMgr::GetItemIdList(v34);
            *a6 = ItemIdList;
            if ( ItemIdList )
            {
              do
                ++v10;
              while ( a4[v10] );
              if ( v9 )
              {
                v39 = 0;
                if ( a4[v10 - 1] == 47 )
                  v39 = 0x20000000;
                *v9 = v39;
              }
            }
            else
            {
              Error = -2147024882;
            }
          }
        }
      }
LABEL_87:
      v48 = &TLMString<192,64,32767>::`vftable';
      CLMString::DeleteBuf((CLMString *)&v48, v51);
      v48 = &CLMString::`vftable';
      v52 = &TLMString<192,64,32767>::`vftable';
      CLMString::DeleteBuf((CLMString *)&v52, v55);
      return (unsigned int)Error;
    }
    ReturnLength[0] = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, ReturnLength);
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v17 = (PSID *)malloc(ReturnLength[0]);
      if ( !v17 )
      {
        Error = -2147024882;
        goto LABEL_24;
      }
    }
    else
    {
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
      else
        Error = LastError;
      v17 = 0;
      if ( Error < 0 )
        goto LABEL_24;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v17, ReturnLength[0], ReturnLength) )
      Error = ResultFromLastError();
LABEL_24:
    CloseHandle(TokenHandle);
    if ( Error < 0 )
    {
      if ( v17 )
LABEL_56:
        free(v17);
    }
    else if ( v17 )
    {
      *(_QWORD *)ReturnLength = 0;
      if ( ConvertSidToStringSidW(*v17, (LPWSTR *)ReturnLength) )
      {
        v18 = 2147483646;
        v19 = 2147483646;
        v20 = L"{";
        v21 = 1024;
        v22 = Buffer;
        do
        {
          if ( !v19 )
            break;
          v23 = *v20;
          if ( !*v20 )
            break;
          ++v20;
          *v22++ = v23;
          --v19;
          --v21;
        }
        while ( v21 );
        Error = -2147024774;
        v24 = -2147024774;
        if ( v21 )
          v24 = 0;
        v25 = v22 - 1;
        if ( v21 )
          v25 = v22;
        *v25 = 0;
        if ( v21 )
        {
          v26 = StringCchCatW(Buffer, 0x400u, *(const wchar_t **)ReturnLength);
          if ( v26 < 0 )
          {
            Error = v26;
            LocalFree(*(HLOCAL *)ReturnLength);
            v9 = v45;
          }
          else
          {
            v28 = Buffer;
            while ( *v28 )
            {
              ++v28;
              if ( !--v27 )
              {
                Error = -2147024809;
                LocalFree(*(HLOCAL *)ReturnLength);
                v9 = v45;
                goto LABEL_56;
              }
            }
            v29 = L"}";
            for ( i = (wchar_t *)&v57[-2 * v27]; v27; --v27 )
            {
              if ( !v18 )
                break;
              v31 = *v29;
              if ( !*v29 )
                break;
              ++v29;
              *i++ = v31;
              --v18;
            }
            v32 = i - 1;
            if ( v27 )
              v32 = i;
            *v32 = 0;
            if ( v27 )
              Error = 0;
            LocalFree(*(HLOCAL *)ReturnLength);
            v9 = v45;
          }
        }
        else
        {
          Error = v24;
          LocalFree(*(HLOCAL *)ReturnLength);
          v9 = v45;
        }
      }
      else
      {
        Error = ResultFromLastError();
      }
      goto LABEL_56;
    }
    v8 = v42;
    goto LABEL_58;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180002030  mov     [rsp-8+arg_8], rbx
0x180002035  push    rbp
0x180002036  push    rsi
0x180002037  push    rdi
0x180002038  push    r12
0x18000203a  push    r13
0x18000203c  push    r14
0x18000203e  push    r15
0x180002040  lea     rbp, [rsp-12E0h]
0x180002048  mov     eax, 13E0h
0x18000204d  call    _alloca_probe
0x180002052  sub     rsp, rax
0x180002055  mov     rax, cs:__security_cookie
0x18000205c  xor     rax, rsp
0x18000205f  mov     [rbp+1310h+var_40], rax
0x180002066  mov     rbx, r9
0x180002069  mov     r15, r8
0x18000206c  mov     [rsp+1410h+var_13D8], r8
0x180002071  mov     [rsp+1410h+var_13A8], rcx
0x180002076  mov     rdx, [rbp+1310h+arg_20]
0x18000207d  mov     r13, [rbp+1310h+arg_28]
0x180002084  mov     r12, [rbp+1310h+arg_30]
0x18000208b  mov     [rsp+1410h+var_13B0], r12
0x180002090  test    r13, r13
0x180002093  jz      loc_180002769
0x180002099  test    rbx, rbx
0x18000209c  jz      loc_180002769
0x1800020a2  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800020a9  mov     rax, rdi
0x1800020ac  nop     dword ptr [rax+00h]
0x1800020b0  inc     rax
0x1800020b3  cmp     word ptr [r9+rax*2], 0
0x1800020b9  jnz     short loc_1800020B0
0x1800020bb  test    eax, eax
0x1800020bd  jnz     short loc_1800020C9
0x1800020bf  mov     eax, 80070057h
0x1800020c4  jmp     loc_18000276E
0x1800020c9  xor     r14d, r14d
0x1800020cc  mov     [r13+0], r14
0x1800020d0  test    rdx, rdx
0x1800020d3  jz      short loc_1800020E4
0x1800020d5  mov     rax, rdi
0x1800020d8  inc     rax
0x1800020db  cmp     [r9+rax*2], r14w
0x1800020e0  jnz     short loc_1800020D8
0x1800020e2  mov     [rdx], eax
0x1800020e4  lea     rax, [rbp+1310h+var_11C8]
0x1800020eb  mov     [rbp+1310h+var_11D8], rax
0x1800020f2  mov     [rbp+1310h+var_11D0], 0C1h
0x1800020fd  mov     [rbp+1310h+var_11C8], r14w
0x180002105  lea     rcx, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x18000210c  mov     [rbp+1310h+var_11E0], rcx
0x180002113  lea     rax, [rbp+1310h+var_1368]
0x180002117  mov     [rbp+1310h+lpBuffer], rax
0x18000211b  mov     qword ptr [rbp+1310h+cchBufferMax], 0C1h
0x180002123  mov     [rbp+1310h+var_1368], r14w
0x180002128  mov     [rbp+1310h+var_1380], rcx
0x18000212c  mov     [rsp+1410h+cchCount2], edi; cchCount2
0x180002130  lea     rax, String2; "*"
0x180002137  mov     [rsp+1410h+lpString2], rax; lpString2
0x18000213c  mov     r9d, edi; cchCount1
0x18000213f  mov     r8, rbx; lpString1
0x180002142  mov     edx, 1; dwCmpFlags
0x180002147  mov     ecx, 7Fh; Locale
0x18000214c  call    cs:__imp_CompareStringW
0x180002152  lea     rsi, aCsc; "csc://"
0x180002159  cmp     eax, 2
0x18000215c  jz      short loc_1800021B0
0x18000215e  mov     [rsp+1410h+cchCount2], edi; cchCount2
0x180002162  mov     [rsp+1410h+lpString2], rsi; lpString2
0x180002167  mov     r9d, edi; cchCount1
0x18000216a  mov     r8, rbx; lpString1
0x18000216d  mov     edx, 1; dwCmpFlags
0x180002172  mov     ecx, 7Fh; Locale
0x180002177  call    cs:__imp_CompareStringW
0x18000217d  cmp     eax, 2
0x180002180  jz      short loc_1800021B0
0x180002182  mov     r14d, 80004005h
0x180002188  mov     rax, [rbp+1310h+var_11E0]
0x18000218f  mov     r9d, 0FFFFFFFFh
0x180002195  xor     r8d, r8d
0x180002198  mov     rdx, rbx
0x18000219b  lea     rcx, [rbp+1310h+var_11E0]
0x1800021a2  mov     rax, [rax+20h]
0x1800021a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ab  jmp     loc_180002726
0x1800021b0  xor     edx, edx; Val
0x1800021b2  mov     r8d, 800h; Size
0x1800021b8  lea     rcx, [rbp+1310h+Buffer]; void *
0x1800021bf  call    memset_0
0x1800021c4  mov     [rsp+1410h+TokenHandle], r14
0x1800021c9  call    cs:__imp_GetCurrentProcess
0x1800021cf  mov     rcx, rax; ProcessHandle
0x1800021d2  lea     r8, [rsp+1410h+TokenHandle]; TokenHandle
0x1800021d7  mov     edx, 8; DesiredAccess
0x1800021dc  call    cs:__imp_OpenProcessToken
0x1800021e2  test    eax, eax
0x1800021e4  jnz     short loc_1800021F6
0x1800021e6  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800021eb  mov     r14d, eax
0x1800021ee  test    eax, eax
0x1800021f0  js      loc_18000243B
0x1800021f6  mov     rcx, [rsp+1410h+TokenHandle]; TokenHandle
0x1800021fb  test    rcx, rcx
0x1800021fe  jz      loc_18000243B
0x180002204  mov     [rsp+1410h+ReturnLength], 0
0x18000220c  lea     rax, [rsp+1410h+ReturnLength]
0x180002211  mov     [rsp+1410h+lpString2], rax; ReturnLength
0x180002216  xor     r9d, r9d; TokenInformationLength
0x180002219  xor     r8d, r8d; TokenInformation
0x18000221c  mov     edx, 1; TokenInformationClass
0x180002221  call    cs:__imp_GetTokenInformation
0x180002227  call    cs:__imp_GetLastError
0x18000222d  cmp     eax, 7Ah ; 'z'
0x180002230  jz      loc_18000236E
0x180002236  test    eax, eax
0x180002238  jg      short loc_18000223F
0x18000223a  mov     r14d, eax
0x18000223d  jmp     short loc_18000224A
0x18000223f  movzx   r14d, ax
0x180002243  or      r14d, 80070000h
0x18000224a  xor     r15d, r15d
0x18000224d  test    r14d, r14d
0x180002250  js      short loc_180002280
0x180002252  lea     rax, [rsp+1410h+ReturnLength]
0x180002257  mov     [rsp+1410h+lpString2], rax; int
0x18000225c  mov     r9d, [rsp+1410h+ReturnLength]; TokenInformationLength
0x180002261  mov     r8, r15; TokenInformation
0x180002264  mov     edx, 1; TokenInformationClass
0x180002269  mov     rcx, [rsp+1410h+TokenHandle]; TokenHandle
0x18000226e  call    cs:__imp_GetTokenInformation
0x180002274  test    eax, eax
0x180002276  jnz     short loc_180002280
0x180002278  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000227d  mov     r14d, eax
0x180002280  mov     rcx, [rsp+1410h+TokenHandle]; hObject
0x180002285  call    cs:__imp_CloseHandle
0x18000228b  test    r14d, r14d
0x18000228e  js      loc_180002428
0x180002294  test    r15, r15
0x180002297  jz      loc_180002436
0x18000229d  mov     qword ptr [rsp+1410h+ReturnLength], 0
0x1800022a6  lea     rdx, [rsp+1410h+ReturnLength]; StringSid
0x1800022ab  mov     rcx, [r15]; Sid
0x1800022ae  call    cs:__imp_ConvertSidToStringSidW
0x1800022b4  test    eax, eax
0x1800022b6  jz      loc_18000241E
0x1800022bc  mov     r12d, 7FFFFFFEh
0x1800022c2  mov     eax, r12d
0x1800022c5  lea     rcx, asc_180042E10; "{"
0x1800022cc  mov     r11d, 400h
0x1800022d2  mov     r8d, r11d
0x1800022d5  lea     r9, [rbp+1310h+Buffer]
0x1800022dc  test    rax, rax
0x1800022df  jz      short loc_1800022FE
0x1800022e1  movzx   edx, word ptr [rcx]
0x1800022e4  test    dx, dx
0x1800022e7  jz      short loc_1800022FE
0x1800022e9  add     rcx, 2
0x1800022ed  mov     [r9], dx
0x1800022f1  add     r9, 2
0x1800022f5  dec     rax
0x1800022f8  sub     r8, 1
0x1800022fc  jnz     short loc_1800022DC
0x1800022fe  mov     r14d, 8007007Ah
0x180002304  mov     edx, r14d
0x180002307  xor     eax, eax
0x180002309  test    r8, r8
0x18000230c  cmovnz  edx, eax
0x18000230f  lea     rcx, [r9-2]
0x180002313  cmovnz  rcx, r9
0x180002317  mov     [rcx], ax
0x18000231a  jz      loc_180002409
0x180002320  mov     r8, qword ptr [rsp+1410h+ReturnLength]; wchar_t *
0x180002325  mov     rdx, r11; unsigned __int64
0x180002328  lea     rcx, [rbp+1310h+Buffer]; wchar_t *
0x18000232f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180002334  test    eax, eax
0x180002336  js      loc_1800023F4
0x18000233c  lea     rax, [rbp+1310h+Buffer]
0x180002343  cmp     word ptr [rax], 0
0x180002347  jz      short loc_18000238F
0x180002349  add     rax, 2
0x18000234d  sub     r11, 1
0x180002351  jnz     short loc_180002343
0x180002353  mov     r14d, 80070057h
0x180002359  mov     rcx, qword ptr [rsp+1410h+ReturnLength]; hMem
0x18000235e  call    cs:__imp_LocalFree
0x180002364  mov     r12, [rsp+1410h+var_13B0]
0x180002369  jmp     loc_18000242D
0x18000236e  mov     ecx, [rsp+1410h+ReturnLength]; Size
0x180002372  call    cs:__imp_malloc
0x180002378  mov     r15, rax
0x18000237b  test    rax, rax
0x18000237e  jnz     loc_180002252
0x180002384  mov     r14d, 8007000Eh
0x18000238a  jmp     loc_180002280
0x18000238f  lea     r8, asc_180042DC8; "}"
0x180002396  lea     rax, [r11+r11]
0x18000239a  lea     rdx, [rbp+1310h+var_840]
0x1800023a1  sub     rdx, rax
0x1800023a4  test    r11, r11
0x1800023a7  jz      short loc_1800023CB
0x1800023a9  test    r12, r12
0x1800023ac  jz      short loc_1800023CB
0x1800023ae  movzx   eax, word ptr [r8]
0x1800023b2  test    ax, ax
0x1800023b5  jz      short loc_1800023CB
0x1800023b7  add     r8, 2
0x1800023bb  mov     [rdx], ax
0x1800023be  add     rdx, 2
0x1800023c2  dec     r12
0x1800023c5  sub     r11, 1
0x1800023c9  jnz     short loc_1800023A9
0x1800023cb  lea     rcx, [rdx-2]
0x1800023cf  test    r11, r11
0x1800023d2  cmovnz  rcx, rdx
0x1800023d6  xor     eax, eax
0x1800023d8  mov     [rcx], ax
0x1800023db  test    r11, r11
0x1800023de  cmovnz  r14d, eax
0x1800023e2  mov     rcx, qword ptr [rsp+1410h+ReturnLength]; hMem
0x1800023e7  call    cs:__imp_LocalFree
0x1800023ed  mov     r12, [rsp+1410h+var_13B0]
0x1800023f2  jmp     short loc_18000242D
0x1800023f4  mov     r14d, eax
0x1800023f7  mov     rcx, qword ptr [rsp+1410h+ReturnLength]; hMem
0x1800023fc  call    cs:__imp_LocalFree
0x180002402  mov     r12, [rsp+1410h+var_13B0]
0x180002407  jmp     short loc_18000242D
0x180002409  mov     r14d, edx
0x18000240c  mov     rcx, qword ptr [rsp+1410h+ReturnLength]; hMem
0x180002411  call    cs:__imp_LocalFree
0x180002417  mov     r12, [rsp+1410h+var_13B0]
0x18000241c  jmp     short loc_18000242D
0x18000241e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180002423  mov     r14d, eax
0x180002426  jmp     short loc_18000242D
0x180002428  test    r15, r15
0x18000242b  jz      short loc_180002436
0x18000242d  mov     rcx, r15; Block
0x180002430  call    cs:__imp_free
0x180002436  mov     r15, [rsp+1410h+var_13D8]
0x18000243b  test    r14d, r14d
0x18000243e  js      loc_180002726
0x180002444  mov     rdx, rsi
0x180002447  lea     rcx, [rbp+1310h+var_11E0]
0x18000244e  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180002453  mov     rax, [rbp+1310h+var_11E0]
0x18000245a  mov     r9d, 0FFFFFFFFh
0x180002460  mov     r8d, dword ptr [rbp+1310h+var_11D0+4]
0x180002467  lea     rdx, [rbp+1310h+Buffer]
0x18000246e  lea     rcx, [rbp+1310h+var_11E0]
0x180002475  mov     rax, [rax+20h]
0x180002479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000247e  mov     r9d, [rbp+1310h+cchBufferMax]; cchBufferMax
0x180002482  mov     r8, [rbp+1310h+lpBuffer]; lpBuffer
0x180002486  mov     edx, 70h ; 'p'; uID
0x18000248b  mov     rcx, cs:hInstance; hInstance
0x180002492  call    cs:__imp_LoadStringW
0x180002498  test    eax, eax
0x18000249a  jnz     short loc_1800024A2
0x18000249c  mov     r14d, 80004005h
0x1800024a2  mov     rdx, [rbp+1310h+lpBuffer]
0x1800024a6  mov     rax, rdi
0x1800024a9  nop     dword ptr [rax+00000000h]
0x1800024b0  inc     rax
0x1800024b3  cmp     word ptr [rdx+rax*2], 0
0x1800024b8  jnz     short loc_1800024B0
0x1800024ba  cmp     eax, [rbp+1310h+cchBufferMax]
0x1800024bd  jb      short loc_1800024DE
0x1800024bf  mov     rcx, [rbp+1318h]; this
0x1800024c6  mov     r9d, 0CEh; char *
0x1800024cc  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800024d3  mov     edx, 0FEh; void *
0x1800024d8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800024de  mov     [rbp+1310h+cchBufferMax+4], eax
0x1800024e1  mov     ecx, eax
0x1800024e3  xor     eax, eax
0x1800024e5  mov     [rdx+rcx*2], ax
0x1800024e9  test    r14d, r14d
0x1800024ec  js      loc_180002726
0x1800024f2  mov     rdx, [rbp+1310h+var_11D8]; wchar_t *
0x1800024f9  lea     rcx, [rsp+1410h+pvar]; this
0x1800024fe  call    ??0CComPropVariant@@QEAA@PEB_W@Z; CComPropVariant::CComPropVariant(wchar_t const *)
0x180002503  mov     rsi, [rsp+1410h+var_13A8]
0x180002508  add     rsi, 50h ; 'P'
0x18000250c  lea     r8, [rsp+1410h+pvar]; struct tagPROPVARIANT *
0x180002511  lea     rdx, PKEY_ParsingPath; struct _tagpropertykey *
0x180002518  mov     rcx, rsi; this
0x18000251b  call    ?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z; CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)
0x180002520  mov     r14d, eax
0x180002523  lea     rcx, [rsp+1410h+pvar]; pvar
0x180002528  call    cs:__imp_PropVariantClear
0x18000252e  test    r14d, r14d
0x180002531  js      loc_180002726
0x180002537  mov     rdx, [rbp+1310h+lpBuffer]; wchar_t *
0x18000253b  lea     rcx, [rsp+1410h+pvar]; this
0x180002540  call    ??0CComPropVariant@@QEAA@PEB_W@Z; CComPropVariant::CComPropVariant(wchar_t const *)
0x180002545  lea     r8, [rsp+1410h+pvar]; struct tagPROPVARIANT *
  ... truncated ...
```
