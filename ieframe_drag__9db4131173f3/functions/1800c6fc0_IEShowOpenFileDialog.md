# IEShowOpenFileDialog

- ea: `0x1800c6fc0`
- end: `0x1800c7395`
- name: `IEShowOpenFileDialog`
- size: `981`
- prototype: `HRESULT __stdcall(HWND hwnd, LPWSTR lpwstrFileName, DWORD cchMaxFileName, LPCWSTR lpwstrInitialDir, LPCWSTR lpwstrFilter, LPCWSTR lpwstrDefExt, DWORD dwFilterIndex, DWORD dwFlags, HANDLE *phFile)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180011230`
- `0x180090198`
- `0x1800c5d04`
- `0x1800c5df0`
- `0x1800c6168`
- `0x1800c6fc0`
- `0x180441ce8`
- `0x180441ff4`
- `0x18054e286`
- `0x180550010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800c7349`
- `KERNEL32!CreateFileW` at `0x1800c7349`
- `KERNEL32!LocalFree` at `0x1800c72b8`
- `KERNEL32!LocalFree` at `0x1800c72b8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800c70c0`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x1800c70c0`
- `USER32!EnableWindow` at `0x1800c70e9`
- `USER32!EnableWindow` at `0x1800c717f`
- `USER32!EnableWindow` at `0x1800c71c2`
- `USER32!EnableWindow` at `0x1800c723b`
- `USER32!EnableWindow` at `0x1800c70e9`
- `USER32!EnableWindow` at `0x1800c717f`
- `USER32!EnableWindow` at `0x1800c71c2`
- `USER32!EnableWindow` at `0x1800c723b`
- `USER32!GetAncestor` at `0x1800c702e`
- `USER32!GetAncestor` at `0x1800c70d6`
- `USER32!GetAncestor` at `0x1800c71af`
- `USER32!GetAncestor` at `0x1800c702e`
- `USER32!GetAncestor` at `0x1800c70d6`
- `USER32!GetAncestor` at `0x1800c71af`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800c7060`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800c7060`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800c7277`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800c7290`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800c729f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800c72aa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800c7277`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800c7290`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800c729f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800c72aa`

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
0x1800c6fc0  mov     rax, rsp
0x1800c6fc3  mov     [rax+10h], rbx
0x1800c6fc7  mov     [rax+20h], r9
0x1800c6fcb  mov     [rax+18h], r8d
0x1800c6fcf  mov     [rax+8], rcx
0x1800c6fd3  push    rbp
0x1800c6fd4  push    rsi
0x1800c6fd5  push    rdi
0x1800c6fd6  push    r12
0x1800c6fd8  push    r13
0x1800c6fda  push    r14
0x1800c6fdc  push    r15
0x1800c6fde  lea     rbp, [rax-78h]
0x1800c6fe2  sub     rsp, 140h
0x1800c6fe9  mov     rsi, r9
0x1800c6fec  mov     r15d, r8d
0x1800c6fef  mov     r13, rdx
0x1800c6ff2  mov     rbx, rcx
0x1800c6ff5  call    ?IsValidIEProcess@@YAHXZ; IsValidIEProcess(void)
0x1800c6ffa  test    eax, eax
0x1800c6ffc  jnz     short loc_1800C7008
0x1800c6ffe  mov     ebx, 80004001h
0x1800c7003  jmp     loc_1800C7378
0x1800c7008  mov     r14, [rbp+70h+phFile]
0x1800c700f  test    r14, r14
0x1800c7012  jz      loc_1800C7373
0x1800c7018  test    r13, r13
0x1800c701b  jz      loc_1800C7373
0x1800c7021  xor     edi, edi
0x1800c7023  test    rbx, rbx
0x1800c7026  jz      short loc_1800C7046
0x1800c7028  lea     edx, [rdi+2]; gaFlags
0x1800c702b  mov     rcx, rbx; hwnd
0x1800c702e  call    cs:__imp_GetAncestor
0x1800c7034  mov     rdi, rax
0x1800c7037  test    rax, rax
0x1800c703a  jnz     short loc_1800C7046
0x1800c703c  mov     ebx, 80070005h
0x1800c7041  jmp     loc_1800C7378
0x1800c7046  mov     r12d, [rbp+70h+dwFlags]
0x1800c704d  mov     ecx, 20000003h
0x1800c7052  and     r12d, 2B76008h
0x1800c7059  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800c7060  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800c7066  test    al, al
0x1800c7068  jz      loc_1800C72CD
0x1800c706e  xorps   xmm0, xmm0
0x1800c7071  lea     rcx, [rsp+170h+var_118+8]
0x1800c7076  xorps   xmm1, xmm1
0x1800c7079  xor     esi, esi
0x1800c707b  movdqu  [rsp+170h+var_118+8], xmm0
0x1800c7081  mov     [rbp+70h+var_F0], esi
0x1800c7084  movdqu  xmmword ptr [rsp+170h+var_108+8], xmm1
0x1800c708a  mov     [rbp+70h+var_E8], rsi
0x1800c708e  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x1800c7093  mov     edx, 80000000h
0x1800c7098  mov     ebx, eax
0x1800c709a  lea     ecx, [rax+rdx]
0x1800c709d  test    edx, ecx
0x1800c709f  jnz     short loc_1800C70AC
0x1800c70a1  cmp     eax, 800401F1h
0x1800c70a6  jnz     loc_1800C72BE
0x1800c70ac  mov     rcx, [rbp+70h+lpwstrFilter]; pszSrch
0x1800c70b3  mov     r15, rsi
0x1800c70b6  mov     [rsp+170h+pv], rsi
0x1800c70bb  test    rcx, rcx
0x1800c70be  jz      short loc_1800C70C9
0x1800c70c0  call    cs:__imp_StrDupW
0x1800c70c6  mov     r15, rax
0x1800c70c9  test    rdi, rdi
0x1800c70cc  jz      short loc_1800C70EF
0x1800c70ce  mov     edx, 2; gaFlags
0x1800c70d3  mov     rcx, rdi; hwnd
0x1800c70d6  call    cs:__imp_GetAncestor
0x1800c70dc  mov     rsi, rax
0x1800c70df  test    rax, rax
0x1800c70e2  jz      short loc_1800C70EF
0x1800c70e4  xor     edx, edx; bEnable
0x1800c70e6  mov     rcx, rax; hWnd
0x1800c70e9  call    cs:__imp_EnableWindow
0x1800c70ef  test    ebx, ebx
0x1800c70f1  js      short loc_1800C7172
0x1800c70f3  mov     rcx, qword ptr [rsp+170h+var_108+10h]
0x1800c70f8  mov     r9d, r12d
0x1800c70fb  mov     r8d, [rbp+70h+dwFilterIndex]
0x1800c7102  mov     rdx, [rcx]
0x1800c7105  mov     rax, [rdx+788h]
0x1800c710c  mov     rdx, [rbp+70h+lpwstrDefExt]
0x1800c7113  mov     [rsp+40h], rdx
0x1800c7118  mov     rdx, [rbp+70h+arg_18]
0x1800c711f  mov     [rsp+170h+var_138], 0
0x1800c7128  mov     [rsp+170h+hTemplateFile], rdx
0x1800c712d  mov     rdx, rdi
0x1800c7130  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], r13
0x1800c7135  mov     qword ptr [rsp+170h+dwCreationDisposition], r15
0x1800c713a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c713f  mov     ebx, eax
0x1800c7141  test    eax, eax
0x1800c7143  js      short loc_1800C7172
0x1800c7145  xor     edx, edx
0x1800c7147  lea     rcx, [rsp+170h+var_118+8]
0x1800c714c  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x1800c7151  mov     ebx, eax
0x1800c7153  test    eax, eax
0x1800c7155  js      short loc_1800C7172
0x1800c7157  mov     rcx, qword ptr [rsp+170h+var_108+10h]
0x1800c715c  lea     rdx, [rsp+170h+pv]
0x1800c7161  mov     rax, [rcx]
0x1800c7164  mov     rax, [rax+790h]
0x1800c716b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7170  mov     ebx, eax
0x1800c7172  test    rsi, rsi
0x1800c7175  jz      short loc_1800C7185
0x1800c7177  mov     edx, 1; bEnable
0x1800c717c  mov     rcx, rsi; hWnd
0x1800c717f  call    cs:__imp_EnableWindow
0x1800c7185  test    ebx, ebx
0x1800c7187  js      loc_1800C72B0
0x1800c718d  cmp     [rsp+170h+pv], 0
0x1800c7193  jz      loc_1800C72B0
0x1800c7199  xor     esi, esi
0x1800c719b  mov     qword ptr [rsp+170h+var_118], 0
0x1800c71a4  test    rdi, rdi
0x1800c71a7  jz      short loc_1800C71C8
0x1800c71a9  lea     edx, [rsi+2]; gaFlags
0x1800c71ac  mov     rcx, rdi; hwnd
0x1800c71af  call    cs:__imp_GetAncestor
0x1800c71b5  mov     rsi, rax
0x1800c71b8  test    rax, rax
0x1800c71bb  jz      short loc_1800C71C8
0x1800c71bd  xor     edx, edx; bEnable
0x1800c71bf  mov     rcx, rax; hWnd
0x1800c71c2  call    cs:__imp_EnableWindow
0x1800c71c8  mov     r8, [rsp+170h+pv]
0x1800c71cd  mov     rcx, qword ptr [rsp+170h+var_108+10h]
0x1800c71d2  mov     r9, [r8+8]
0x1800c71d6  mov     rdx, [rcx]
0x1800c71d9  mov     r8, [r8+10h]
0x1800c71dd  mov     rax, [rdx+858h]
0x1800c71e4  mov     edx, [r9]
0x1800c71e7  mov     r9, [r9+8]
0x1800c71eb  mov     [rsp+170h+dwCreationDisposition], edx
0x1800c71ef  mov     rdx, [rbp+70h+arg_0]
0x1800c71f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c71fb  mov     ebx, eax
0x1800c71fd  test    eax, eax
0x1800c71ff  js      short loc_1800C722E
0x1800c7201  xor     edx, edx
0x1800c7203  lea     rcx, [rsp+170h+var_118+8]
0x1800c7208  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x1800c720d  mov     ebx, eax
0x1800c720f  test    eax, eax
0x1800c7211  js      short loc_1800C722E
0x1800c7213  mov     rcx, qword ptr [rsp+170h+var_108+10h]
0x1800c7218  lea     rdx, [rsp+170h+var_118]
0x1800c721d  mov     rax, [rcx]
0x1800c7220  mov     rax, [rax+860h]
0x1800c7227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c722c  mov     ebx, eax
0x1800c722e  test    rsi, rsi
0x1800c7231  jz      short loc_1800C7241
0x1800c7233  mov     edx, 1; bEnable
0x1800c7238  mov     rcx, rsi; hWnd
0x1800c723b  call    cs:__imp_EnableWindow
0x1800c7241  mov     rax, qword ptr [rsp+170h+var_118]
0x1800c7246  mov     [r14], rax
0x1800c7249  test    ebx, ebx
0x1800c724b  js      short loc_1800C7264
0x1800c724d  mov     r8, [rsp+170h+pv]
0x1800c7252  mov     rcx, r13; unsigned __int16 *
0x1800c7255  mov     edx, dword ptr [rbp+70h+arg_10]; unsigned __int64
0x1800c725b  mov     r8, [r8+10h]; unsigned __int16 *
0x1800c725f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c7264  mov     rcx, [rsp+170h+pv]
0x1800c7269  xor     esi, esi
0x1800c726b  mov     rdi, [rcx+8]
0x1800c726f  cmp     [rcx], esi
0x1800c7271  jbe     short loc_1800C728C
0x1800c7273  mov     rcx, [rdi+8]; pv
0x1800c7277  call    cs:__imp_CoTaskMemFree
0x1800c727d  mov     rcx, [rsp+170h+pv]
0x1800c7282  lea     rdi, [rdi+10h]
0x1800c7286  inc     esi
0x1800c7288  cmp     esi, [rcx]
0x1800c728a  jb      short loc_1800C7273
0x1800c728c  mov     rcx, [rcx+8]; pv
0x1800c7290  call    cs:__imp_CoTaskMemFree
0x1800c7296  mov     rcx, [rsp+170h+pv]
0x1800c729b  mov     rcx, [rcx+10h]; pv
0x1800c729f  call    cs:__imp_CoTaskMemFree
0x1800c72a5  mov     rcx, [rsp+170h+pv]; pv
0x1800c72aa  call    cs:__imp_CoTaskMemFree
0x1800c72b0  test    r15, r15
0x1800c72b3  jz      short loc_1800C72BE
0x1800c72b5  mov     rcx, r15; hMem
0x1800c72b8  call    cs:__imp_LocalFree
0x1800c72be  lea     rcx, [rsp+170h+var_118+8]
0x1800c72c3  call    ??1?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBrokerNoFrameAffinity@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAA@XZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(void)
0x1800c72c8  jmp     loc_1800C7378
0x1800c72cd  mov     ebx, 98h
0x1800c72d2  lea     rcx, [rbp+70h+var_D0]; void *
0x1800c72d6  mov     r8d, ebx; Size
0x1800c72d9  xor     edx, edx; Val
0x1800c72db  call    memset_0
0x1800c72e0  mov     rax, [rbp+70h+lpwstrFilter]
0x1800c72e7  lea     rcx, [rbp+70h+var_D0]; LPOPENFILENAMEW
0x1800c72eb  mov     [rbp+70h+var_D0.lpstrFilter], rax
0x1800c72ef  mov     rax, [rbp+70h+lpwstrDefExt]
0x1800c72f6  mov     [rbp+70h+var_D0.lpstrDefExt], rax
0x1800c72fa  mov     eax, [rbp+70h+dwFilterIndex]
0x1800c7300  mov     [rbp+70h+var_D0.nFilterIndex], eax
0x1800c7303  mov     [rbp+70h+var_D0.lStructSize], ebx
0x1800c7306  mov     [rbp+70h+var_D0.hwndOwner], rdi
0x1800c730a  mov     [rbp+70h+var_D0.lpstrFile], r13
0x1800c730e  mov     [rbp+70h+var_D0.nMaxFile], r15d
0x1800c7312  mov     [rbp+70h+var_D0.lpstrInitialDir], rsi
0x1800c7316  mov     [rbp+70h+var_D0.Flags], r12d
0x1800c731a  call    GetOpenFileNameW
0x1800c731f  test    eax, eax
0x1800c7321  jz      short loc_1800C7354
0x1800c7323  xor     ebx, ebx
0x1800c7325  xor     r9d, r9d; lpSecurityAttributes
0x1800c7328  mov     [rsp+170h+hTemplateFile], rbx; hTemplateFile
0x1800c732d  mov     edx, 80000000h; dwDesiredAccess
0x1800c7332  mov     [rsp+170h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c733a  mov     rcx, r13; lpFileName
0x1800c733d  mov     [rsp+170h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c7345  lea     r8d, [rbx+1]; dwShareMode
0x1800c7349  call    cs:__imp_CreateFileW
0x1800c734f  mov     [r14], rax
0x1800c7352  jmp     short loc_1800C7378
0x1800c7354  call    CommDlgExtendedError
0x1800c7359  mov     ebx, 1
0x1800c735e  test    eax, eax
0x1800c7360  jz      short loc_1800C7378
0x1800c7362  jg      short loc_1800C7368
0x1800c7364  mov     ebx, eax
0x1800c7366  jmp     short loc_1800C7378
0x1800c7368  movzx   ebx, ax
0x1800c736b  or      ebx, 80070000h
0x1800c7371  jmp     short loc_1800C7378
0x1800c7373  mov     ebx, 80070057h
0x1800c7378  mov     eax, ebx
0x1800c737a  mov     rbx, [rsp+170h+arg_8]
0x1800c7382  add     rsp, 140h
0x1800c7389  pop     r15
0x1800c738b  pop     r14
0x1800c738d  pop     r13
0x1800c738f  pop     r12
0x1800c7391  pop     rdi
0x1800c7392  pop     rsi
0x1800c7393  pop     rbp
0x1800c7394  retn
```
