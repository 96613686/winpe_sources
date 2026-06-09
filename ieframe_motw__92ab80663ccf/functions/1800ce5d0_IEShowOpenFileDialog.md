# IEShowOpenFileDialog

- ea: `0x1800ce5d0`
- end: `0x1800cea00`
- name: `IEShowOpenFileDialog`
- size: `1072`
- prototype: `HRESULT __stdcall(HWND hwnd, LPWSTR lpwstrFileName, DWORD cchMaxFileName, LPCWSTR lpwstrInitialDir, LPCWSTR lpwstrFilter, LPCWSTR lpwstrDefExt, DWORD dwFilterIndex, DWORD dwFlags, HANDLE *phFile)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800144d0`
- `0x180097218`
- `0x1800cd150`
- `0x1800cd2a4`
- `0x1800cd638`
- `0x1800ce5d0`
- `0x18047c8e4`
- `0x18047cbfc`
- `0x180591ef6`
- `0x180594010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800ce9ad`
- `KERNEL32!CreateFileW` at `0x1800ce9ad`
- `KERNEL32!LocalFree` at `0x1800ce916`
- `KERNEL32!LocalFree` at `0x1800ce916`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800ce6dc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800ce6dc`
- `USER32!EnableWindow` at `0x1800ce711`
- `USER32!EnableWindow` at `0x1800ce7ad`
- `USER32!EnableWindow` at `0x1800ce7fc`
- `USER32!EnableWindow` at `0x1800ce87b`
- `USER32!EnableWindow` at `0x1800ce711`
- `USER32!EnableWindow` at `0x1800ce7ad`
- `USER32!EnableWindow` at `0x1800ce7fc`
- `USER32!EnableWindow` at `0x1800ce87b`
- `USER32!GetAncestor` at `0x1800ce63e`
- `USER32!GetAncestor` at `0x1800ce6f8`
- `USER32!GetAncestor` at `0x1800ce7e3`
- `USER32!GetAncestor` at `0x1800ce63e`
- `USER32!GetAncestor` at `0x1800ce6f8`
- `USER32!GetAncestor` at `0x1800ce7e3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ce676`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ce676`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800ce8bd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800ce8dc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800ce8f1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800ce902`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800ce8bd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800ce8dc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800ce8f1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800ce902`

## pseudocode

```c
HRESULT __stdcall IEShowOpenFileDialog(
        HWND hwnd,
        LPWSTR lpwstrFileName,
        DWORD cchMaxFileName,
        LPCWSTR lpwstrInitialDir,
        LPCWSTR lpwstrFilter,
        LPCWSTR lpwstrDefExt,
        DWORD dwFilterIndex,
        DWORD dwFlags,
        HANDLE *phFile)
{
  HRESULT v13; // ebx
  HWND Ancestor; // rdi
  HWND v15; // rsi
  HRESULT v16; // eax
  PWSTR v17; // r15
  HWND v18; // rax
  HWND v19; // rsi
  HWND v20; // rax
  LPVOID *v21; // rcx
  unsigned int v22; // esi
  __int64 i; // rdi
  HRESULT v24; // eax
  LPVOID pv; // [rsp+58h] [rbp-B0h] BYREF
  void *v27; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v28; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+78h] [rbp-90h]
  int v30; // [rsp+88h] [rbp-80h]
  __int64 v31; // [rsp+90h] [rbp-78h]
  tagOFNW v32; // [rsp+A8h] [rbp-60h] BYREF

  if ( !(unsigned int)IsValidIEProcess() )
    return -2147467263;
  if ( !phFile || !lpwstrFileName )
    return -2147024809;
  Ancestor = 0;
  if ( hwnd )
  {
    Ancestor = GetAncestor(hwnd, 2u);
    if ( !Ancestor )
      return -2147024891;
  }
  *phFile = (HANDLE)-1LL;
  if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
  {
    v15 = 0;
    v28 = 0;
    v30 = 0;
    v29 = 0;
    v31 = 0;
    v16 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(&v28);
    v13 = v16;
    if ( (int)(v16 + 0x80000000) < 0 || v16 == -2147221007 )
    {
      v17 = 0;
      pv = 0;
      if ( lpwstrFilter )
        v17 = StrDupW(lpwstrFilter);
      if ( Ancestor )
      {
        v18 = GetAncestor(Ancestor, 2u);
        v15 = v18;
        if ( v18 )
          EnableWindow(v18, 0);
      }
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, HWND, _QWORD, _QWORD, PWSTR, LPWSTR, LPCWSTR, _QWORD, LPCWSTR))(**((_QWORD **)&v29 + 1) + 1928LL))(
                *((_QWORD *)&v29 + 1),
                Ancestor,
                dwFilterIndex,
                dwFlags & 0x2B76008,
                v17,
                lpwstrFileName,
                lpwstrInitialDir,
                0,
                lpwstrDefExt);
        if ( v13 >= 0 )
        {
          v13 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(
                  &v28,
                  0);
          if ( v13 >= 0 )
            v13 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)&v29 + 1) + 1936LL))(
                    *((_QWORD *)&v29 + 1),
                    &pv);
        }
      }
      if ( v15 )
        EnableWindow(v15, 1);
      if ( v13 >= 0 && pv )
      {
        v19 = 0;
        v27 = 0;
        if ( Ancestor )
        {
          v20 = GetAncestor(Ancestor, 2u);
          v19 = v20;
          if ( v20 )
            EnableWindow(v20, 0);
        }
        v13 = (*(__int64 (__fastcall **)(_QWORD, HWND, _QWORD, _QWORD, _DWORD))(**((_QWORD **)&v29 + 1) + 2136LL))(
                *((_QWORD *)&v29 + 1),
                hwnd,
                *((_QWORD *)pv + 2),
                *(_QWORD *)(*((_QWORD *)pv + 1) + 8LL),
                **((_DWORD **)pv + 1));
        if ( v13 >= 0 )
        {
          v13 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(
                  &v28,
                  0);
          if ( v13 >= 0 )
            v13 = (*(__int64 (__fastcall **)(_QWORD, void **))(**((_QWORD **)&v29 + 1) + 2144LL))(
                    *((_QWORD *)&v29 + 1),
                    &v27);
        }
        if ( v19 )
          EnableWindow(v19, 1);
        *phFile = v27;
        if ( v13 >= 0 )
          StringCchCopyW(lpwstrFileName, cchMaxFileName, *((const unsigned __int16 **)pv + 2));
        v21 = (LPVOID *)pv;
        v22 = 0;
        for ( i = *((_QWORD *)pv + 1); v22 < *(_DWORD *)pv; ++v22 )
        {
          CoTaskMemFree(*(LPVOID *)(i + 8));
          v21 = (LPVOID *)pv;
          i += 16;
        }
        CoTaskMemFree(v21[1]);
        CoTaskMemFree(*((LPVOID *)pv + 2));
        CoTaskMemFree(pv);
      }
      if ( v17 )
        LocalFree(v17);
    }
    CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(&v28);
  }
  else
  {
    memset_0(&v32, 0, sizeof(v32));
    v32.lpstrFilter = lpwstrFilter;
    v32.lpstrDefExt = lpwstrDefExt;
    v32.nFilterIndex = dwFilterIndex;
    v32.lStructSize = 152;
    v32.hwndOwner = Ancestor;
    v32.lpstrFile = lpwstrFileName;
    v32.nMaxFile = cchMaxFileName;
    v32.lpstrInitialDir = lpwstrInitialDir;
    v32.Flags = dwFlags & 0x2B76008;
    if ( GetOpenFileNameW(&v32) )
    {
      v13 = 0;
      *phFile = CreateFileW(lpwstrFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    }
    else
    {
      v24 = CommDlgExtendedError();
      v13 = 1;
      if ( v24 )
      {
        if ( v24 > 0 )
          return (unsigned __int16)v24 | 0x80070000;
        else
          return v24;
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1800ce5d0  mov     rax, rsp
0x1800ce5d3  mov     [rax+10h], rbx
0x1800ce5d7  mov     [rax+20h], r9
0x1800ce5db  mov     [rax+18h], r8d
0x1800ce5df  mov     [rax+8], rcx
0x1800ce5e3  push    rbp
0x1800ce5e4  push    rsi
0x1800ce5e5  push    rdi
0x1800ce5e6  push    r12
0x1800ce5e8  push    r13
0x1800ce5ea  push    r14
0x1800ce5ec  push    r15
0x1800ce5ee  lea     rbp, [rax-78h]
0x1800ce5f2  sub     rsp, 140h
0x1800ce5f9  mov     rsi, r9
0x1800ce5fc  mov     r15d, r8d
0x1800ce5ff  mov     r13, rdx
0x1800ce602  mov     rbx, rcx
0x1800ce605  call    ?IsValidIEProcess@@YAHXZ; IsValidIEProcess(void)
0x1800ce60a  test    eax, eax
0x1800ce60c  jnz     short loc_1800CE618
0x1800ce60e  mov     ebx, 80004001h
0x1800ce613  jmp     loc_1800CE9E2
0x1800ce618  mov     r14, [rbp+70h+phFile]
0x1800ce61f  test    r14, r14
0x1800ce622  jz      loc_1800CE9DD
0x1800ce628  test    r13, r13
0x1800ce62b  jz      loc_1800CE9DD
0x1800ce631  xor     edi, edi
0x1800ce633  test    rbx, rbx
0x1800ce636  jz      short loc_1800CE65C
0x1800ce638  lea     edx, [rdi+2]; gaFlags
0x1800ce63b  mov     rcx, rbx; hwnd
0x1800ce63e  call    cs:__imp_GetAncestor
0x1800ce645  nop     dword ptr [rax+rax+00h]
0x1800ce64a  mov     rdi, rax
0x1800ce64d  test    rax, rax
0x1800ce650  jnz     short loc_1800CE65C
0x1800ce652  mov     ebx, 80070005h
0x1800ce657  jmp     loc_1800CE9E2
0x1800ce65c  mov     r12d, [rbp+70h+dwFlags]
0x1800ce663  mov     ecx, 20000003h
0x1800ce668  and     r12d, 2B76008h
0x1800ce66f  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800ce676  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ce67d  nop     dword ptr [rax+rax+00h]
0x1800ce682  test    al, al
0x1800ce684  jz      loc_1800CE931
0x1800ce68a  xorps   xmm0, xmm0
0x1800ce68d  lea     rcx, [rsp+170h+var_118+8]
0x1800ce692  xorps   xmm1, xmm1
0x1800ce695  xor     esi, esi
0x1800ce697  movdqu  [rsp+170h+var_118+8], xmm0
0x1800ce69d  mov     [rbp+70h+var_F0], esi
0x1800ce6a0  movdqu  xmmword ptr [rsp+170h+var_108+8], xmm1
0x1800ce6a6  mov     [rbp+70h+var_E8], rsi
0x1800ce6aa  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x1800ce6af  mov     edx, 80000000h
0x1800ce6b4  mov     ebx, eax
0x1800ce6b6  lea     ecx, [rax+rdx]
0x1800ce6b9  test    edx, ecx
0x1800ce6bb  jnz     short loc_1800CE6C8
0x1800ce6bd  cmp     eax, 800401F1h
0x1800ce6c2  jnz     loc_1800CE922
0x1800ce6c8  mov     rcx, [rbp+70h+lpwstrFilter]; pszSrch
0x1800ce6cf  mov     r15, rsi
0x1800ce6d2  mov     [rsp+170h+pv], rsi
0x1800ce6d7  test    rcx, rcx
0x1800ce6da  jz      short loc_1800CE6EB
0x1800ce6dc  call    cs:__imp_StrDupW
0x1800ce6e3  nop     dword ptr [rax+rax+00h]
0x1800ce6e8  mov     r15, rax
0x1800ce6eb  test    rdi, rdi
0x1800ce6ee  jz      short loc_1800CE71D
0x1800ce6f0  mov     edx, 2; gaFlags
0x1800ce6f5  mov     rcx, rdi; hwnd
0x1800ce6f8  call    cs:__imp_GetAncestor
0x1800ce6ff  nop     dword ptr [rax+rax+00h]
0x1800ce704  mov     rsi, rax
0x1800ce707  test    rax, rax
0x1800ce70a  jz      short loc_1800CE71D
0x1800ce70c  xor     edx, edx; bEnable
0x1800ce70e  mov     rcx, rax; hWnd
0x1800ce711  call    cs:__imp_EnableWindow
0x1800ce718  nop     dword ptr [rax+rax+00h]
0x1800ce71d  test    ebx, ebx
0x1800ce71f  js      short loc_1800CE7A0
0x1800ce721  mov     rcx, qword ptr [rsp+170h+var_108+10h]
0x1800ce726  mov     r9d, r12d
0x1800ce729  mov     r8d, [rbp+70h+dwFilterIndex]
0x1800ce730  mov     rdx, [rcx]
0x1800ce733  mov     rax, [rdx+788h]
0x1800ce73a  mov     rdx, [rbp+70h+lpwstrDefExt]
0x1800ce741  mov     [rsp+40h], rdx
0x1800ce746  mov     rdx, [rbp+70h+arg_18]
0x1800ce74d  mov     [rsp+170h+var_138], 0
0x1800ce756  mov     [rsp+170h+hTemplateFile], rdx
0x1800ce75b  mov     rdx, rdi
0x1800ce75e  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], r13
0x1800ce763  mov     qword ptr [rsp+170h+dwCreationDisposition], r15
0x1800ce768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce76d  mov     ebx, eax
0x1800ce76f  test    eax, eax
0x1800ce771  js      short loc_1800CE7A0
0x1800ce773  xor     edx, edx
0x1800ce775  lea     rcx, [rsp+170h+var_118+8]
0x1800ce77a  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x1800ce77f  mov     ebx, eax
0x1800ce781  test    eax, eax
0x1800ce783  js      short loc_1800CE7A0
0x1800ce785  mov     rcx, qword ptr [rsp+170h+var_108+10h]
0x1800ce78a  lea     rdx, [rsp+170h+pv]
0x1800ce78f  mov     rax, [rcx]
0x1800ce792  mov     rax, [rax+790h]
0x1800ce799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce79e  mov     ebx, eax
0x1800ce7a0  test    rsi, rsi
0x1800ce7a3  jz      short loc_1800CE7B9
0x1800ce7a5  mov     edx, 1; bEnable
0x1800ce7aa  mov     rcx, rsi; hWnd
0x1800ce7ad  call    cs:__imp_EnableWindow
0x1800ce7b4  nop     dword ptr [rax+rax+00h]
0x1800ce7b9  test    ebx, ebx
0x1800ce7bb  js      loc_1800CE90E
0x1800ce7c1  cmp     [rsp+170h+pv], 0
0x1800ce7c7  jz      loc_1800CE90E
0x1800ce7cd  xor     esi, esi
0x1800ce7cf  mov     qword ptr [rsp+170h+var_118], 0
0x1800ce7d8  test    rdi, rdi
0x1800ce7db  jz      short loc_1800CE808
0x1800ce7dd  lea     edx, [rsi+2]; gaFlags
0x1800ce7e0  mov     rcx, rdi; hwnd
0x1800ce7e3  call    cs:__imp_GetAncestor
0x1800ce7ea  nop     dword ptr [rax+rax+00h]
0x1800ce7ef  mov     rsi, rax
0x1800ce7f2  test    rax, rax
0x1800ce7f5  jz      short loc_1800CE808
0x1800ce7f7  xor     edx, edx; bEnable
0x1800ce7f9  mov     rcx, rax; hWnd
0x1800ce7fc  call    cs:__imp_EnableWindow
0x1800ce803  nop     dword ptr [rax+rax+00h]
0x1800ce808  mov     r8, [rsp+170h+pv]
0x1800ce80d  mov     rcx, qword ptr [rsp+170h+var_108+10h]
0x1800ce812  mov     r9, [r8+8]
0x1800ce816  mov     rdx, [rcx]
0x1800ce819  mov     r8, [r8+10h]
0x1800ce81d  mov     rax, [rdx+858h]
0x1800ce824  mov     edx, [r9]
0x1800ce827  mov     r9, [r9+8]
0x1800ce82b  mov     [rsp+170h+dwCreationDisposition], edx
0x1800ce82f  mov     rdx, [rbp+70h+arg_0]
0x1800ce836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce83b  mov     ebx, eax
0x1800ce83d  test    eax, eax
0x1800ce83f  js      short loc_1800CE86E
0x1800ce841  xor     edx, edx
0x1800ce843  lea     rcx, [rsp+170h+var_118+8]
0x1800ce848  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x1800ce84d  mov     ebx, eax
0x1800ce84f  test    eax, eax
0x1800ce851  js      short loc_1800CE86E
0x1800ce853  mov     rcx, qword ptr [rsp+170h+var_108+10h]
0x1800ce858  lea     rdx, [rsp+170h+var_118]
0x1800ce85d  mov     rax, [rcx]
0x1800ce860  mov     rax, [rax+860h]
0x1800ce867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce86c  mov     ebx, eax
0x1800ce86e  test    rsi, rsi
0x1800ce871  jz      short loc_1800CE887
0x1800ce873  mov     edx, 1; bEnable
0x1800ce878  mov     rcx, rsi; hWnd
0x1800ce87b  call    cs:__imp_EnableWindow
0x1800ce882  nop     dword ptr [rax+rax+00h]
0x1800ce887  mov     rax, qword ptr [rsp+170h+var_118]
0x1800ce88c  mov     [r14], rax
0x1800ce88f  test    ebx, ebx
0x1800ce891  js      short loc_1800CE8AA
0x1800ce893  mov     r8, [rsp+170h+pv]
0x1800ce898  mov     rcx, r13; unsigned __int16 *
0x1800ce89b  mov     edx, dword ptr [rbp+70h+arg_10]; unsigned __int64
0x1800ce8a1  mov     r8, [r8+10h]; unsigned __int16 *
0x1800ce8a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ce8aa  mov     rcx, [rsp+170h+pv]
0x1800ce8af  xor     esi, esi
0x1800ce8b1  mov     rdi, [rcx+8]
0x1800ce8b5  cmp     [rcx], esi
0x1800ce8b7  jbe     short loc_1800CE8D8
0x1800ce8b9  mov     rcx, [rdi+8]; pv
0x1800ce8bd  call    cs:__imp_CoTaskMemFree
0x1800ce8c4  nop     dword ptr [rax+rax+00h]
0x1800ce8c9  mov     rcx, [rsp+170h+pv]
0x1800ce8ce  lea     rdi, [rdi+10h]
0x1800ce8d2  inc     esi
0x1800ce8d4  cmp     esi, [rcx]
0x1800ce8d6  jb      short loc_1800CE8B9
0x1800ce8d8  mov     rcx, [rcx+8]; pv
0x1800ce8dc  call    cs:__imp_CoTaskMemFree
0x1800ce8e3  nop     dword ptr [rax+rax+00h]
0x1800ce8e8  mov     rcx, [rsp+170h+pv]
0x1800ce8ed  mov     rcx, [rcx+10h]; pv
0x1800ce8f1  call    cs:__imp_CoTaskMemFree
0x1800ce8f8  nop     dword ptr [rax+rax+00h]
0x1800ce8fd  mov     rcx, [rsp+170h+pv]; pv
0x1800ce902  call    cs:__imp_CoTaskMemFree
0x1800ce909  nop     dword ptr [rax+rax+00h]
0x1800ce90e  test    r15, r15
0x1800ce911  jz      short loc_1800CE922
0x1800ce913  mov     rcx, r15; hMem
0x1800ce916  call    cs:__imp_LocalFree
0x1800ce91d  nop     dword ptr [rax+rax+00h]
0x1800ce922  lea     rcx, [rsp+170h+var_118+8]
0x1800ce927  call    ??1?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBrokerNoFrameAffinity@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAA@XZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(void)
0x1800ce92c  jmp     loc_1800CE9E2
0x1800ce931  mov     ebx, 98h
0x1800ce936  lea     rcx, [rbp+70h+var_D0]; void *
0x1800ce93a  mov     r8d, ebx; Size
0x1800ce93d  xor     edx, edx; Val
0x1800ce93f  call    memset_0
0x1800ce944  mov     rax, [rbp+70h+lpwstrFilter]
0x1800ce94b  lea     rcx, [rbp+70h+var_D0]; LPOPENFILENAMEW
0x1800ce94f  mov     [rbp+70h+var_D0.lpstrFilter], rax
0x1800ce953  mov     rax, [rbp+70h+lpwstrDefExt]
0x1800ce95a  mov     [rbp+70h+var_D0.lpstrDefExt], rax
0x1800ce95e  mov     eax, [rbp+70h+dwFilterIndex]
0x1800ce964  mov     [rbp+70h+var_D0.nFilterIndex], eax
0x1800ce967  mov     [rbp+70h+var_D0.lStructSize], ebx
0x1800ce96a  mov     [rbp+70h+var_D0.hwndOwner], rdi
0x1800ce96e  mov     [rbp+70h+var_D0.lpstrFile], r13
0x1800ce972  mov     [rbp+70h+var_D0.nMaxFile], r15d
0x1800ce976  mov     [rbp+70h+var_D0.lpstrInitialDir], rsi
0x1800ce97a  mov     [rbp+70h+var_D0.Flags], r12d
0x1800ce97e  call    GetOpenFileNameW
0x1800ce983  test    eax, eax
0x1800ce985  jz      short loc_1800CE9BE
0x1800ce987  xor     ebx, ebx
0x1800ce989  xor     r9d, r9d; lpSecurityAttributes
0x1800ce98c  mov     [rsp+170h+hTemplateFile], rbx; hTemplateFile
0x1800ce991  mov     edx, 80000000h; dwDesiredAccess
0x1800ce996  mov     [rsp+170h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ce99e  mov     rcx, r13; lpFileName
0x1800ce9a1  mov     [rsp+170h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ce9a9  lea     r8d, [rbx+1]; dwShareMode
0x1800ce9ad  call    cs:__imp_CreateFileW
0x1800ce9b4  nop     dword ptr [rax+rax+00h]
0x1800ce9b9  mov     [r14], rax
0x1800ce9bc  jmp     short loc_1800CE9E2
0x1800ce9be  call    CommDlgExtendedError
0x1800ce9c3  mov     ebx, 1
0x1800ce9c8  test    eax, eax
0x1800ce9ca  jz      short loc_1800CE9E2
0x1800ce9cc  jg      short loc_1800CE9D2
0x1800ce9ce  mov     ebx, eax
0x1800ce9d0  jmp     short loc_1800CE9E2
0x1800ce9d2  movzx   ebx, ax
0x1800ce9d5  or      ebx, 80070000h
0x1800ce9db  jmp     short loc_1800CE9E2
0x1800ce9dd  mov     ebx, 80070057h
0x1800ce9e2  mov     eax, ebx
0x1800ce9e4  mov     rbx, [rsp+170h+arg_8]
0x1800ce9ec  add     rsp, 140h
0x1800ce9f3  pop     r15
0x1800ce9f5  pop     r14
0x1800ce9f7  pop     r13
0x1800ce9f9  pop     r12
0x1800ce9fb  pop     rdi
0x1800ce9fc  pop     rsi
0x1800ce9fd  pop     rbp
0x1800ce9fe  retn
```
