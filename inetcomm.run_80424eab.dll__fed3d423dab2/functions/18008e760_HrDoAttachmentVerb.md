# HrDoAttachmentVerb

- ea: `0x18008e760`
- end: `0x18008ea67`
- name: `HrDoAttachmentVerb`
- size: `775`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x18008f9dc`
- `0x18009034c`

## callees

- `0x180002098`
- `0x1800055bc`
- `0x18008df54`
- `0x18008dfb8`
- `0x18008e760`
- `0x18008ef30`
- `0x1800cacb8`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18008e8a9`
- `SHLWAPI!PathFindExtensionW` at `0x18008e8a9`
- `SHLWAPI!PathQuoteSpacesW` at `0x18008e8fe`
- `SHLWAPI!PathQuoteSpacesW` at `0x18008e8fe`
- `SHLWAPI!AssocQueryKeyW` at `0x18008e8c4`
- `SHLWAPI!AssocQueryKeyW` at `0x18008e8c4`
- `ADVAPI32!RegCloseKey` at `0x18008e8dd`
- `ADVAPI32!RegCloseKey` at `0x18008e8dd`
- `USER32!LoadStringW` at `0x18008e938`
- `USER32!LoadStringW` at `0x18008e938`
- `SHELL32!ShellExecuteExW` at `0x18008e909`
- `SHELL32!ShellExecuteExW` at `0x18008e909`

## string_xrefs

- `0x18008e8d4`: `OpenAs`

## pseudocode

```c
__int64 __fastcall HrDoAttachmentVerb(HWND a1, int a2, struct IMimeMessage *a3, __int64 a4, int a5, int a6)
{
  int TempFile; // edi
  unsigned __int64 v12; // rax
  const WCHAR *ExtensionW; // rax
  const WCHAR *lpVerb; // rax
  const wchar_t *v15; // r8
  void *v16; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR sz[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[512]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v16 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( a2 == 3 )
    return 2147500033LL;
  if ( !a4 )
    return 2147942487LL;
  if ( a2 == 1 )
  {
    TempFile = HrSaveAttachmentAs(a1, (__int64)a3, a4, a5);
    goto LABEL_37;
  }
  if ( a6 || *(_QWORD *)(a4 + 1584) )
  {
    LoadStringW(g_hLocRes, 0x57Au, Buffer, 512);
    TempFile = CreateAttachmentServices(Buffer, &IID_IAttachmentExecute, &v16);
    if ( TempFile < 0 )
      goto LABEL_37;
    TempFile = HrGetTempFile(a3, (struct ATTACHDATA_tag *)a4);
    if ( TempFile < 0 )
      goto LABEL_37;
    if ( a2 )
    {
      if ( a2 != 2 )
        goto LABEL_37;
      if ( (*(int (__fastcall **)(void *, __int64))(*(_QWORD *)v16 + 40LL))(v16, a4) < 0 )
        goto LABEL_37;
      if ( a5 )
      {
        TempFile = (*(__int64 (__fastcall **)(void *, const wchar_t *))(*(_QWORD *)v16 + 64LL))(v16, L"about:internet");
        if ( TempFile < 0 )
          goto LABEL_37;
      }
      v15 = L"print";
    }
    else
    {
      if ( (*(int (__fastcall **)(void *, __int64))(*(_QWORD *)v16 + 40LL))(v16, a4) < 0 )
        goto LABEL_37;
      if ( a5 )
      {
        TempFile = (*(__int64 (__fastcall **)(void *, const wchar_t *))(*(_QWORD *)v16 + 64LL))(v16, L"about:internet");
        if ( TempFile < 0 )
          goto LABEL_37;
      }
      v15 = L"open";
    }
    if ( (*(int (__fastcall **)(void *, HWND, const wchar_t *, __int64))(*(_QWORD *)v16 + 96LL))(
           v16,
           a1,
           v15,
           a4 + 1568) < 0 )
      HrCleanTempFile((LPCWSTR)a4);
    TempFile = 0;
    goto LABEL_37;
  }
  memset_0(sz, 0, 0x208u);
  hKey = 0;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  pExecInfo.cbSize = 112;
  pExecInfo.fMask = 64;
  pExecInfo.hwnd = a1;
  pExecInfo.nShow = 1;
  TempFile = HrGetTempFile(a3, (struct ATTACHDATA_tag *)a4);
  if ( TempFile >= 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a4 + 2 * v12) );
    if ( v12 > 0x103 )
    {
      TempFile = -2147467259;
      goto LABEL_37;
    }
    StringCchCopyW(sz, 0x103u, (const unsigned __int16 *)a4);
    sz[259] = 0;
    pExecInfo.lpFile = sz;
    if ( a2 )
    {
      lpVerb = L"Print";
      if ( a2 != 2 )
        lpVerb = pExecInfo.lpVerb;
    }
    else
    {
      ExtensionW = PathFindExtensionW((LPCWSTR)a4);
      AssocQueryKeyW(0, ASSOCKEY_CLASS, ExtensionW, 0, &hKey);
      if ( hKey )
      {
        RegCloseKey(hKey);
LABEL_21:
        PathQuoteSpacesW(sz);
        ShellExecuteExW(&pExecInfo);
        *(_QWORD *)(a4 + 1568) = pExecInfo.hProcess;
        goto LABEL_37;
      }
      lpVerb = L"OpenAs";
    }
    pExecInfo.lpVerb = lpVerb;
    goto LABEL_21;
  }
LABEL_37:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v16);
  return (unsigned int)TempFile;
}

```

## disassembly

```asm
0x18008e760  push    rbp
0x18008e762  push    rbx
0x18008e763  push    rsi
0x18008e764  push    rdi
0x18008e765  push    r12
0x18008e767  push    r14
0x18008e769  push    r15
0x18008e76b  lea     rbp, [rsp-5D0h]
0x18008e773  sub     rsp, 6D0h
0x18008e77a  mov     rax, cs:__security_cookie
0x18008e781  xor     rax, rsp
0x18008e784  mov     [rbp+600h+var_40], rax
0x18008e78b  mov     r14, r8
0x18008e78e  mov     esi, edx
0x18008e790  mov     r15, rcx
0x18008e793  xor     r12d, r12d
0x18008e796  xor     edx, edx; Val
0x18008e798  mov     [rsp+700h+var_6D0], r12
0x18008e79d  mov     r8d, 400h; Size
0x18008e7a3  lea     rcx, [rbp+600h+Buffer]; void *
0x18008e7aa  mov     rbx, r9
0x18008e7ad  call    memset_0
0x18008e7b2  cmp     esi, 3
0x18008e7b5  jnz     short loc_18008E7C1
0x18008e7b7  mov     eax, 80004001h
0x18008e7bc  jmp     loc_18008EA46
0x18008e7c1  test    rbx, rbx
0x18008e7c4  jnz     short loc_18008E7D0
0x18008e7c6  mov     eax, 80070057h
0x18008e7cb  jmp     loc_18008EA46
0x18008e7d0  cmp     esi, 1
0x18008e7d3  jnz     short loc_18008E7F1
0x18008e7d5  mov     r9d, [rbp+600h+arg_20]
0x18008e7dc  mov     r8, rbx
0x18008e7df  mov     rdx, r14
0x18008e7e2  mov     rcx, r15
0x18008e7e5  call    HrSaveAttachmentAs
0x18008e7ea  mov     edi, eax
0x18008e7ec  jmp     loc_18008EA3A
0x18008e7f1  cmp     [rbp+600h+arg_28], r12d
0x18008e7f8  jnz     loc_18008E91F
0x18008e7fe  cmp     [rbx+630h], r12
0x18008e805  jnz     loc_18008E91F
0x18008e80b  xor     edx, edx; Val
0x18008e80d  lea     rcx, [rbp+600h+sz]; void *
0x18008e811  mov     r8d, 208h; Size
0x18008e817  call    memset_0
0x18008e81c  mov     edi, 70h ; 'p'
0x18008e821  mov     [rsp+700h+hKey], r12
0x18008e826  mov     r8d, edi; Size
0x18008e829  lea     rcx, [rsp+700h+pExecInfo]; void *
0x18008e82e  xor     edx, edx; Val
0x18008e830  call    memset_0
0x18008e835  mov     rdx, rbx; struct ATTACHDATA_tag *
0x18008e838  mov     [rsp+700h+pExecInfo.cbSize], edi
0x18008e83c  mov     rcx, r14; struct IMimeMessage *
0x18008e83f  mov     [rsp+700h+pExecInfo.fMask], 40h ; '@'
0x18008e847  mov     [rsp+700h+pExecInfo.hwnd], r15
0x18008e84c  mov     [rsp+700h+pExecInfo.nShow], 1
0x18008e854  call    ?HrGetTempFile@@YAJPEAUIMimeMessage@@PEAUATTACHDATA_tag@@@Z; HrGetTempFile(IMimeMessage *,ATTACHDATA_tag *)
0x18008e859  mov     edi, eax
0x18008e85b  test    eax, eax
0x18008e85d  js      loc_18008EA3A
0x18008e863  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008e867  inc     rax
0x18008e86a  cmp     [rbx+rax*2], r12w
0x18008e86f  jnz     short loc_18008E867
0x18008e871  mov     edx, 103h; unsigned __int64
0x18008e876  cmp     rax, rdx
0x18008e879  jbe     short loc_18008E885
0x18008e87b  mov     edi, 80004005h
0x18008e880  jmp     loc_18008EA3A
0x18008e885  mov     r8, rbx; unsigned __int16 *
0x18008e888  lea     rcx, [rbp+600h+sz]; unsigned __int16 *
0x18008e88c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008e891  mov     [rbp+600h+var_44A], r12w
0x18008e899  lea     rax, [rbp+600h+sz]
0x18008e89d  mov     [rsp+700h+pExecInfo.lpFile], rax
0x18008e8a2  test    esi, esi
0x18008e8a4  jnz     short loc_18008E8E5
0x18008e8a6  mov     rcx, rbx; pszPath
0x18008e8a9  call    cs:__imp_PathFindExtensionW
0x18008e8af  lea     rcx, [rsp+700h+hKey]
0x18008e8b4  xor     r9d, r9d; pszExtra
0x18008e8b7  mov     [rsp+700h+phkeyOut], rcx; phkeyOut
0x18008e8bc  lea     edx, [rsi+3]; key
0x18008e8bf  xor     ecx, ecx; flags
0x18008e8c1  mov     r8, rax; pszAssoc
0x18008e8c4  call    cs:__imp_AssocQueryKeyW
0x18008e8ca  mov     rcx, [rsp+700h+hKey]; hKey
0x18008e8cf  test    rcx, rcx
0x18008e8d2  jnz     short loc_18008E8DD
0x18008e8d4  lea     rax, aOpenas; "OpenAs"
0x18008e8db  jmp     short loc_18008E8F5
0x18008e8dd  call    cs:__imp_RegCloseKey
0x18008e8e3  jmp     short loc_18008E8FA
0x18008e8e5  cmp     esi, 2
0x18008e8e8  lea     rax, aPrint; "Print"
0x18008e8ef  cmovnz  rax, [rsp+700h+pExecInfo.lpVerb]
0x18008e8f5  mov     [rsp+700h+pExecInfo.lpVerb], rax
0x18008e8fa  lea     rcx, [rbp+600h+sz]; lpsz
0x18008e8fe  call    cs:__imp_PathQuoteSpacesW
0x18008e904  lea     rcx, [rsp+700h+pExecInfo]; pExecInfo
0x18008e909  call    cs:__imp_ShellExecuteExW
0x18008e90f  mov     rax, [rbp+600h+pExecInfo.hProcess]
0x18008e913  mov     [rbx+620h], rax
0x18008e91a  jmp     loc_18008EA3A
0x18008e91f  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18008e926  lea     r8, [rbp+600h+Buffer]; lpBuffer
0x18008e92d  mov     r9d, 200h; cchBufferMax
0x18008e933  mov     edx, 57Ah; uID
0x18008e938  call    cs:__imp_LoadStringW
0x18008e93e  lea     r8, [rsp+700h+var_6D0]; void **
0x18008e943  lea     rdx, IID_IAttachmentExecute; struct _GUID *
0x18008e94a  lea     rcx, [rbp+600h+Buffer]; unsigned __int16 *
0x18008e951  call    ?CreateAttachmentServices@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateAttachmentServices(ushort const *,_GUID const &,void * *)
0x18008e956  mov     edi, eax
0x18008e958  test    eax, eax
0x18008e95a  js      loc_18008EA3A
0x18008e960  mov     rdx, rbx; struct ATTACHDATA_tag *
0x18008e963  mov     rcx, r14; struct IMimeMessage *
0x18008e966  call    ?HrGetTempFile@@YAJPEAUIMimeMessage@@PEAUATTACHDATA_tag@@@Z; HrGetTempFile(IMimeMessage *,ATTACHDATA_tag *)
0x18008e96b  mov     edi, eax
0x18008e96d  test    eax, eax
0x18008e96f  js      loc_18008EA3A
0x18008e975  test    esi, esi
0x18008e977  jnz     short loc_18008E9C5
0x18008e979  mov     rcx, [rsp+700h+var_6D0]
0x18008e97e  mov     rdx, rbx
0x18008e981  mov     rax, [rcx]
0x18008e984  mov     rax, [rax+28h]
0x18008e988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e98d  test    eax, eax
0x18008e98f  js      loc_18008EA3A
0x18008e995  cmp     [rbp+600h+arg_20], r12d
0x18008e99c  jz      short loc_18008E9BC
0x18008e99e  mov     rcx, [rsp+700h+var_6D0]
0x18008e9a3  lea     rdx, aAboutInternet; "about:internet"
0x18008e9aa  mov     rax, [rcx]
0x18008e9ad  mov     rax, [rax+40h]
0x18008e9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9b6  mov     edi, eax
0x18008e9b8  test    eax, eax
0x18008e9ba  js      short loc_18008EA3A
0x18008e9bc  lea     r8, aOpen; "open"
0x18008e9c3  jmp     short loc_18008EA10
0x18008e9c5  cmp     esi, 2
0x18008e9c8  jnz     short loc_18008EA3A
0x18008e9ca  mov     rcx, [rsp+700h+var_6D0]
0x18008e9cf  mov     rdx, rbx
0x18008e9d2  mov     rax, [rcx]
0x18008e9d5  mov     rax, [rax+28h]
0x18008e9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9de  test    eax, eax
0x18008e9e0  js      short loc_18008EA3A
0x18008e9e2  cmp     [rbp+600h+arg_20], r12d
0x18008e9e9  jz      short loc_18008EA09
0x18008e9eb  mov     rcx, [rsp+700h+var_6D0]
0x18008e9f0  lea     rdx, aAboutInternet; "about:internet"
0x18008e9f7  mov     rax, [rcx]
0x18008e9fa  mov     rax, [rax+40h]
0x18008e9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea03  mov     edi, eax
0x18008ea05  test    eax, eax
0x18008ea07  js      short loc_18008EA3A
0x18008ea09  lea     r8, aPrint_0; "print"
0x18008ea10  mov     rcx, [rsp+700h+var_6D0]
0x18008ea15  lea     r9, [rbx+620h]
0x18008ea1c  mov     rdx, r15
0x18008ea1f  mov     rax, [rcx]
0x18008ea22  mov     rax, [rax+60h]
0x18008ea26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea2b  test    eax, eax
0x18008ea2d  jns     short loc_18008EA37
0x18008ea2f  mov     rcx, rbx; lpFileName
0x18008ea32  call    ?HrCleanTempFile@@YAJPEAUATTACHDATA_tag@@@Z; HrCleanTempFile(ATTACHDATA_tag *)
0x18008ea37  mov     edi, r12d
0x18008ea3a  lea     rcx, [rsp+700h+var_6D0]
0x18008ea3f  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18008ea44  mov     eax, edi
0x18008ea46  mov     rcx, [rbp+600h+var_40]
0x18008ea4d  xor     rcx, rsp; StackCookie
0x18008ea50  call    __security_check_cookie
0x18008ea55  add     rsp, 6D0h
0x18008ea5c  pop     r15
0x18008ea5e  pop     r14
0x18008ea60  pop     r12
0x18008ea62  pop     rdi
0x18008ea63  pop     rsi
0x18008ea64  pop     rbx
0x18008ea65  pop     rbp
0x18008ea66  retn
```
