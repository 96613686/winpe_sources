# CActiveUrlRequest::_HrInitializeNeedFile(CMessageTree *,HBODY__ *)

- ea: `0x1800375f4`
- end: `0x1800377c0`
- name: `?_HrInitializeNeedFile@CActiveUrlRequest@@AEAAJPEAVCMessageTree@@PEAUHBODY__@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(CActiveUrlRequest *__hidden this, struct CMessageTree *, struct HBODY__ *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800236b0`
- `0x180036028`

## callees

- `0x180002098`
- `0x1800375f4`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!CreateTempFileW` at `0x1800376ba`
- `MSOERT2!CreateTempFileW` at `0x1800376ba`
- `MSOERT2!AppendTempFileList` at `0x180037780`
- `MSOERT2!AppendTempFileList` at `0x180037780`
- `SHLWAPI!PathCreateFromUrlW` at `0x18003769c`
- `SHLWAPI!PathCreateFromUrlW` at `0x18003769c`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800376db`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800376db`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18003775a`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18003775a`
- `KERNEL32!RemoveDirectoryW` at `0x1800376ea`
- `KERNEL32!RemoveDirectoryW` at `0x1800376ea`
- `KERNEL32!DeleteFileW` at `0x1800376d0`
- `KERNEL32!DeleteFileW` at `0x1800376d0`
- `KERNEL32!CompareStringW` at `0x18003767c`
- `KERNEL32!CompareStringW` at `0x18003767c`

## pseudocode

```c
__int64 __fastcall CActiveUrlRequest::_HrInitializeNeedFile(
        CActiveUrlRequest *this,
        struct CMessageTree *a2,
        struct HBODY__ *a3)
{
  int appended; // ebx
  const WCHAR *v5; // r8
  WCHAR *v6; // rcx
  IUnknown *v8; // rcx
  HRESULT Service; // ebx
  __int64 v10; // rcx
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcchPath; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvOut[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[520]; // [rsp+50h] [rbp-B0h] BYREF

  appended = 0;
  pszPath[0] = 0;
  lpFileName = 0;
  if ( (*((_BYTE *)this + 112) & 4) == 0 )
    return (unsigned int)appended;
  if ( !*((_QWORD *)this + 8) )
    return (unsigned int)-2147418113;
  v5 = (const WCHAR *)*((_QWORD *)this + 12);
  pcchPath = 520;
  if ( !v5
    || CompareStringW(0x7Fu, 1u, v5, 4, L"cid:", 4) == 2
    || PathCreateFromUrlW(*((PCWSTR *)this + 12), pszPath, &pcchPath, 0) < 0 )
  {
    v6 = 0;
  }
  else
  {
    v6 = pszPath;
  }
  appended = CreateTempFileW(v6, 0, &lpFileName, (char *)this + 120);
  if ( appended < 0 )
    goto LABEL_9;
  v8 = (IUnknown *)*((_QWORD *)this + 8);
  ppvOut[0] = 0;
  Service = IUnknown_QueryService(v8, &CLSID_MimeEdit, &GUID_00000109_0000_0000_c000_000000000046, ppvOut);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(ppvOut);
  appended = AppendTempFileList((char *)this + 128, lpFileName, Service >= 0);
  if ( appended < 0 )
    goto LABEL_9;
  v10 = *((_QWORD *)this + 8);
  if ( !v10 )
  {
    appended = -2147418113;
LABEL_9:
    if ( !lpFileName )
      return (unsigned int)appended;
    DeleteFileW(lpFileName);
    if ( PathRemoveFileSpecW((LPWSTR)lpFileName) )
      RemoveDirectoryW(lpFileName);
    goto LABEL_12;
  }
  (*(void (__fastcall **)(__int64, __int64, LPCWSTR))(*(_QWORD *)v10 + 32LL))(v10, 14, lpFileName);
  appended = 0;
LABEL_12:
  if ( lpFileName )
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800375f4  mov     [rsp-8+arg_8], rbx
0x1800375f9  mov     [rsp-8+arg_10], rdi
0x1800375fe  push    rbp
0x1800375ff  lea     rbp, [rsp-370h]
0x180037607  sub     rsp, 470h
0x18003760e  mov     rax, cs:__security_cookie
0x180037615  xor     rax, rsp
0x180037618  mov     [rbp+370h+var_10], rax
0x18003761f  xor     eax, eax
0x180037621  xor     ebx, ebx
0x180037623  mov     rdi, rcx
0x180037626  mov     [rsp+470h+pszPath], ax
0x18003762b  mov     [rsp+470h+lpFileName], rax
0x180037630  lea     r9d, [rbx+4]; cchCount1
0x180037634  test    [rcx+70h], r9b
0x180037638  jz      loc_18003770D
0x18003763e  cmp     [rcx+40h], rax
0x180037642  jnz     short loc_18003764E
0x180037644  mov     ebx, 8000FFFFh
0x180037649  jmp     loc_18003770D
0x18003764e  mov     r8, [rcx+60h]; lpString1
0x180037652  mov     [rsp+470h+pcchPath], 208h
0x18003765a  test    r8, r8
0x18003765d  jz      loc_180037733
0x180037663  mov     edx, 1; dwCmpFlags
0x180037668  mov     [rsp+470h+cchCount2], r9d; cchCount2
0x18003766d  lea     rax, aCid_0; "cid:"
0x180037674  mov     [rsp+470h+lpString2], rax; lpString2
0x180037679  lea     ecx, [rdx+7Eh]; Locale
0x18003767c  call    cs:__imp_CompareStringW
0x180037682  cmp     eax, 2
0x180037685  jz      loc_180037733
0x18003768b  mov     rcx, [rdi+60h]; pszUrl
0x18003768f  lea     r8, [rsp+470h+pcchPath]; pcchPath
0x180037694  xor     r9d, r9d; dwFlags
0x180037697  lea     rdx, [rsp+470h+pszPath]; pszPath
0x18003769c  call    cs:__imp_PathCreateFromUrlW
0x1800376a2  test    eax, eax
0x1800376a4  js      loc_180037733
0x1800376aa  lea     rcx, [rsp+470h+pszPath]
0x1800376af  lea     r9, [rdi+78h]
0x1800376b3  xor     edx, edx
0x1800376b5  lea     r8, [rsp+470h+lpFileName]
0x1800376ba  call    cs:__imp_CreateTempFileW
0x1800376c0  mov     ebx, eax
0x1800376c2  test    eax, eax
0x1800376c4  jns     short loc_18003773A
0x1800376c6  mov     rcx, [rsp+470h+lpFileName]; lpFileName
0x1800376cb  test    rcx, rcx
0x1800376ce  jz      short loc_18003770D
0x1800376d0  call    cs:__imp_DeleteFileW
0x1800376d6  mov     rcx, [rsp+470h+lpFileName]; pszPath
0x1800376db  call    cs:__imp_PathRemoveFileSpecW
0x1800376e1  test    eax, eax
0x1800376e3  jz      short loc_1800376F0
0x1800376e5  mov     rcx, [rsp+470h+lpFileName]; lpPathName
0x1800376ea  call    cs:__imp_RemoveDirectoryW
0x1800376f0  mov     rdx, [rsp+470h+lpFileName]
0x1800376f5  test    rdx, rdx
0x1800376f8  jz      short loc_18003770D
0x1800376fa  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180037701  mov     rax, [rcx]
0x180037704  mov     rax, [rax+28h]
0x180037708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003770d  mov     eax, ebx
0x18003770f  mov     rcx, [rbp+370h+var_10]
0x180037716  xor     rcx, rsp; StackCookie
0x180037719  call    __security_check_cookie
0x18003771e  lea     r11, [rsp+470h+var_s0]
0x180037726  mov     rbx, [r11+18h]
0x18003772a  mov     rdi, [r11+20h]
0x18003772e  mov     rsp, r11
0x180037731  pop     rbp
0x180037732  retn
0x180037733  xor     ecx, ecx
0x180037735  jmp     loc_1800376AF
0x18003773a  mov     rcx, [rdi+40h]; punk
0x18003773e  lea     r9, [rsp+470h+ppvOut]; ppvOut
0x180037743  lea     r8, _GUID_00000109_0000_0000_c000_000000000046; riid
0x18003774a  mov     [rsp+470h+ppvOut], 0
0x180037753  lea     rdx, CLSID_MimeEdit; guidService
0x18003775a  call    cs:__imp_IUnknown_QueryService
0x180037760  lea     rcx, [rsp+470h+ppvOut]
0x180037765  mov     ebx, eax
0x180037767  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003776c  mov     rdx, [rsp+470h+lpFileName]
0x180037771  lea     rcx, [rdi+80h]
0x180037778  not     ebx
0x18003777a  shr     ebx, 1Fh
0x18003777d  mov     r8d, ebx
0x180037780  call    cs:__imp_AppendTempFileList
0x180037786  mov     ebx, eax
0x180037788  test    eax, eax
0x18003778a  js      loc_1800376C6
0x180037790  mov     rcx, [rdi+40h]
0x180037794  test    rcx, rcx
0x180037797  jnz     short loc_1800377A3
0x180037799  mov     ebx, 8000FFFFh
0x18003779e  jmp     loc_1800376C6
0x1800377a3  mov     rax, [rcx]
0x1800377a6  mov     edx, 0Eh
0x1800377ab  mov     r8, [rsp+470h+lpFileName]
0x1800377b0  mov     rax, [rax+20h]
0x1800377b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377b9  xor     ebx, ebx
0x1800377bb  jmp     loc_1800376F0
```
