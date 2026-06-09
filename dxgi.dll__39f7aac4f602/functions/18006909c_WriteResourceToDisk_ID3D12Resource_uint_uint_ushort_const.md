# WriteResourceToDisk(ID3D12Resource *,uint,uint,ushort const *)

- ea: `0x18006909c`
- end: `0x18006973c`
- name: `?WriteResourceToDisk@@YAJPEAUID3D12Resource@@IIPEBG@Z`
- size: `1696`
- prototype: `__int64 __fastcall(struct ID3D12Resource *, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b73cc`

## callees

- `0x180067d2c`
- `0x18006909c`
- `0x180069744`
- `0x180069768`
- `0x1800697a8`
- `0x1800697c8`
- `0x1800697e8`
- `0x18006989c`
- `0x18006996c`
- `0x180069980`
- `0x180069998`
- `0x180075fa0`
- `0x180076f20`
- `0x1800b500c`
- `0x1800bd240`
- `0x1800bd30c`
- `0x1800bd31c`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsftime` at `0x18006943a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsftime` at `0x18006943a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180069364`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180069364`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006954c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069598`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800695e7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069638`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006954c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069598`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800695e7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069638`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800694f7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800694f7`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x180069383`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x180069383`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRStrIW` at `0x1800693bf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRStrIW` at `0x1800693bf`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180069314`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180069314`

## string_xrefs

- `0x18006939e`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x18006955b`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x180069680`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800696a6`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x180069704`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x1800696e4`: `WriteResourceToDisk`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteResourceToDisk(
        struct ID3D12Resource *a1,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  unsigned int LastError; // ebx
  __int64 v9; // rdx
  char v10; // di
  DWORD v11; // r12d
  DWORD v12; // r14d
  unsigned __int64 v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // r8
  DWORD ModuleFileNameW; // eax
  const char *v17; // r9
  HRESULT v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  PWSTR v21; // rax
  __int64 v22; // r8
  struct tm *v23; // rax
  __int64 v24; // r8
  const WCHAR *v25; // rcx
  const char *v26; // r9
  __int64 v27; // rax
  const char *v28; // r9
  __int64 v29; // rdx
  char *v30; // rdi
  unsigned int i; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR ppszPath; // [rsp+58h] [rbp-A8h] BYREF
  time_t Time; // [rsp+60h] [rbp-A0h] BYREF
  LPCVOID lpBuffer; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v40[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[16]; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v43; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v44; // [rsp+B0h] [rbp-50h]
  __int16 Buffer; // [rsp+B8h] [rbp-48h] BYREF
  int v46; // [rsp+BAh] [rbp-46h]
  int v47; // [rsp+BEh] [rbp-42h]
  int v48; // [rsp+C2h] [rbp-3Eh]
  _DWORD v49[10]; // [rsp+D0h] [rbp-30h] BYREF
  int v50; // [rsp+F8h] [rbp-8h]
  int v51; // [rsp+FCh] [rbp-4h]
  int v52; // [rsp+100h] [rbp+0h]
  int v53; // [rsp+104h] [rbp+4h]
  _BYTE v54[16]; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v55; // [rsp+150h] [rbp+50h]
  unsigned int v56; // [rsp+158h] [rbp+58h]
  int v57; // [rsp+160h] [rbp+60h]
  int v58; // [rsp+16Ch] [rbp+6Ch]
  wchar_t Filename[200]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  if ( !a1 )
  {
    LastError = -2147024809;
    v9 = 192;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)LastError,
      dwCreationDisposition);
    return LastError;
  }
  ((void (__fastcall *)(struct ID3D12Resource *, _BYTE *))a1->lpVtbl->GetDesc)(a1, v54);
  if ( a2 > v55 )
  {
    LastError = -2147024809;
    v9 = 194;
    goto LABEL_77;
  }
  if ( a3 > v56 )
  {
    LastError = -2147024809;
    v9 = 195;
    goto LABEL_77;
  }
  v10 = 0;
  if ( v57 != 24 && v57 != 28 && v57 != 29 )
  {
    if ( v57 != 87 && v57 != 91 )
    {
      LastError = -2147024809;
      v9 = 220;
      goto LABEL_77;
    }
    v10 = 1;
  }
  lpBuffer = 0;
  v36 = 8;
  if ( v58 != 1
    || ((int (__fastcall *)(struct ID3D12Resource *, __int64 *, int *, LPCVOID *))a1->lpVtbl->GetPrivateData)(
         a1,
         DIRECTSR_EXT_CPUVA,
         &v36,
         &lpBuffer) < 0 )
  {
    if ( *(&g_AutoSRConfig + 6) )
      DebugPrint("%s: arbitrary resources not supported yet", "WriteResourceToDisk");
    LastError = -2147467263;
    v9 = 246;
    goto LABEL_77;
  }
  NumberOfBytesWritten = 0;
  v36 = 4;
  LastError = ((__int64 (__fastcall *)(struct ID3D12Resource *, __int64 *, int *, DWORD *))a1->lpVtbl->GetPrivateData)(
                a1,
                DIRECTSR_EXT_PITCH_ALIGNMENT,
                &v36,
                &NumberOfBytesWritten);
  if ( (LastError & 0x80000000) != 0 )
  {
    v9 = 238;
    goto LABEL_77;
  }
  v11 = ~(NumberOfBytesWritten - 1) & (NumberOfBytesWritten - 1 + 4 * v55);
  if ( !v11 || (v12 = 4 * a2) == 0 )
  {
    LastError = -2147418113;
    v9 = 249;
    goto LABEL_77;
  }
  v47 = 0;
  memset_0(v49, 0, 0x6Cu);
  Buffer = 19778;
  v46 = 4 * a2 * a3 + 122;
  v48 = 122;
  v49[0] = 108;
  v49[1] = a2;
  v49[2] = -a3;
  v49[3] = 2097153;
  v49[6] = 3780;
  v49[7] = 3780;
  v49[4] = 3;
  v49[5] = 4 * a2 * a3;
  if ( v57 == 24 )
  {
    v50 = 1023;
    v51 = 1047552;
    v52 = 1072693248;
    v53 = -1073741824;
  }
  else
  {
    v51 = 65280;
    v53 = -16777216;
    if ( v10 )
    {
      v50 = 16711680;
      v52 = 255;
    }
    else
    {
      v50 = 255;
      v52 = 16711680;
    }
  }
  *(_OWORD *)lpFileName = 0;
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct_empty(lpFileName);
  v13 = v43;
  if ( v43 <= 0x104 && v44 <= 0x103 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(lpFileName, 260 - v43);
    v43 = v13;
  }
  ppszPath = 0;
  v14 = -1;
  if ( SHGetKnownFolderPath(&FOLDERID_Pictures, 0, 0, &ppszPath) >= 0 )
  {
    v15 = -1;
    do
      ++v15;
    while ( ppszPath[v15] );
    std::wstring::_Append<unsigned short>(lpFileName);
    std::wstring::_Append<unsigned short>(lpFileName);
  }
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0xC8u);
  if ( !ModuleFileNameW || ModuleFileNameW == 200 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x149,
                  (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
                  v17);
    goto LABEL_71;
  }
  v18 = PathCchRemoveExtension(Filename, 0xC8u);
  LastError = v18;
  if ( v18 < 0 )
  {
    v19 = (unsigned int)v18;
    v20 = 330;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
      (const char *)v19,
      dwCreationDisposition);
LABEL_71:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    goto LABEL_72;
  }
  v21 = StrRStrIW(Filename, 0, L"\\");
  if ( !v21 )
  {
    LastError = -2147418113;
    v19 = 2147549183LL;
    v20 = 332;
    goto LABEL_36;
  }
  v22 = -1;
  do
    ++v22;
  while ( v21[v22 + 1] );
  std::wstring::_Append<unsigned short>(lpFileName);
  std::wstring::_Append<unsigned short>(lpFileName);
  Time = 0;
  time(&Time);
  v23 = localtime(&Time);
  if ( !wcsftime(Filename, 0xC8u, L"%y%m%d-%H%M%S", v23) )
  {
    LastError = -2147467259;
    v19 = 2147500037LL;
    v20 = 341;
    goto LABEL_36;
  }
  v24 = -1;
  do
    ++v24;
  while ( Filename[v24] );
  std::wstring::_Append<unsigned short>(lpFileName);
  std::wstring::_Append<unsigned short>(lpFileName);
  do
    ++v14;
  while ( a4[v14] );
  std::wstring::_Append<unsigned short>(lpFileName);
  std::wstring::_Append<unsigned short>(lpFileName);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  v25 = (const WCHAR *)lpFileName;
  if ( v44 > 7 )
    v25 = lpFileName[0];
  hFile = CreateFileW(v25, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x167,
                  (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
                  v26);
    goto LABEL_69;
  }
  v27 = lambda_8ea903bb4baaaddbccd7f9cae0e2e31e_::_lambda_8ea903bb4baaaddbccd7f9cae0e2e31e_(v41, &hFile, lpFileName);
  wil::scope_exit__lambda_8ea903bb4baaaddbccd7f9cae0e2e31e___(v40, v27);
  NumberOfBytesWritten = 0;
  if ( WriteFile(hFile, &Buffer, 0xEu, &NumberOfBytesWritten, 0) )
  {
    if ( WriteFile(hFile, v49, 0x6Cu, &NumberOfBytesWritten, 0) )
    {
      v30 = (char *)lpBuffer;
      if ( v11 == v12 )
      {
        if ( *(&g_AutoSRConfig + 6) )
          DebugPrint("  Writing entire resource (%d bytes)", v12 * a3);
        if ( !WriteFile(hFile, v30, v12 * a3, &NumberOfBytesWritten, 0) )
        {
          v29 = 382;
          goto LABEL_52;
        }
      }
      else
      {
        if ( *(&g_AutoSRConfig + 6) )
          DebugPrint("  Writing resource row by row (%d row width, %d pitch)", v12, v11);
        for ( i = 0; i < a3; ++i )
        {
          if ( !WriteFile(hFile, &v30[v11 * i], v12, &NumberOfBytesWritten, 0) )
          {
            v29 = 392;
            goto LABEL_52;
          }
        }
      }
      v40[16] = 0;
      wil::details::lambda_call__lambda_8ea903bb4baaaddbccd7f9cae0e2e31e___::_lambda_call__lambda_8ea903bb4baaaddbccd7f9cae0e2e31e___(v40);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      std::wstring::_Tidy_deallocate(lpFileName);
      return 0;
    }
    v29 = 374;
  }
  else
  {
    v29 = 373;
  }
LABEL_52:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v29,
                (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
                v28);
  wil::details::lambda_call__lambda_8ea903bb4baaaddbccd7f9cae0e2e31e___::_lambda_call__lambda_8ea903bb4baaaddbccd7f9cae0e2e31e___(v40);
LABEL_69:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
LABEL_72:
  std::wstring::_Tidy_deallocate(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x18006909c  push    rbp
0x18006909e  push    rbx
0x18006909f  push    rsi
0x1800690a0  push    rdi
0x1800690a1  push    r12
0x1800690a3  push    r13
0x1800690a5  push    r14
0x1800690a7  push    r15
0x1800690a9  lea     rbp, [rsp-228h]
0x1800690b1  sub     rsp, 328h
0x1800690b8  mov     rax, cs:__security_cookie
0x1800690bf  xor     rax, rsp
0x1800690c2  mov     [rbp+260h+var_50], rax
0x1800690c9  mov     r13, r9
0x1800690cc  mov     esi, r8d
0x1800690cf  mov     r15d, edx
0x1800690d2  mov     rbx, rcx
0x1800690d5  xor     r14d, r14d
0x1800690d8  test    rcx, rcx
0x1800690db  jnz     short loc_1800690EC
0x1800690dd  mov     ebx, 80070057h
0x1800690e2  mov     edx, 0C0h
0x1800690e7  jmp     loc_180069701
0x1800690ec  mov     rax, [rcx]
0x1800690ef  lea     rdx, [rbp+260h+var_220]
0x1800690f3  mov     rax, [rax+50h]
0x1800690f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690fc  cmp     r15d, [rbp+260h+var_210]
0x180069100  jbe     short loc_180069111
0x180069102  mov     ebx, 80070057h
0x180069107  mov     edx, 0C2h
0x18006910c  jmp     loc_180069701
0x180069111  cmp     esi, [rbp+260h+var_208]
0x180069114  jbe     short loc_180069125
0x180069116  mov     ebx, 80070057h
0x18006911b  mov     edx, 0C3h
0x180069120  jmp     loc_180069701
0x180069125  mov     dil, r14b
0x180069128  mov     ecx, [rbp+260h+var_200]
0x18006912b  mov     eax, 1
0x180069130  sub     ecx, 18h
0x180069133  jz      short loc_18006915A
0x180069135  sub     ecx, 4
0x180069138  jz      short loc_18006915A
0x18006913a  sub     ecx, eax
0x18006913c  jz      short loc_18006915A
0x18006913e  sub     ecx, 3Ah ; ':'
0x180069141  jz      short loc_180069157
0x180069143  cmp     ecx, 4
0x180069146  jz      short loc_180069157
0x180069148  mov     ebx, 80070057h
0x18006914d  mov     edx, 0DCh
0x180069152  jmp     loc_180069701
0x180069157  mov     dil, al
0x18006915a  mov     [rsp+360h+lpBuffer], r14
0x18006915f  mov     [rsp+360h+var_310], 8
0x180069167  cmp     [rbp+260h+var_1F4], eax
0x18006916a  jnz     loc_1800696DB
0x180069170  mov     rax, [rbx]
0x180069173  lea     r9, [rsp+360h+lpBuffer]
0x180069178  lea     r8, [rsp+360h+var_310]
0x18006917d  lea     rdx, DIRECTSR_EXT_CPUVA
0x180069184  mov     rcx, rbx
0x180069187  mov     rax, [rax+18h]
0x18006918b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069190  test    eax, eax
0x180069192  js      loc_1800696DB
0x180069198  mov     [rsp+360h+NumberOfBytesWritten], r14d
0x18006919d  mov     [rsp+360h+var_310], 4
0x1800691a5  mov     rax, [rbx]
0x1800691a8  lea     r9, [rsp+360h+NumberOfBytesWritten]
0x1800691ad  lea     r8, [rsp+360h+var_310]
0x1800691b2  lea     rdx, DIRECTSR_EXT_PITCH_ALIGNMENT
0x1800691b9  mov     rcx, rbx
0x1800691bc  mov     rax, [rax+18h]
0x1800691c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691c5  mov     ebx, eax
0x1800691c7  test    eax, eax
0x1800691c9  jns     short loc_1800691D5
0x1800691cb  mov     edx, 0EEh
0x1800691d0  jmp     loc_180069701
0x1800691d5  mov     ecx, [rsp+360h+NumberOfBytesWritten]
0x1800691d9  dec     ecx
0x1800691db  mov     eax, [rbp+260h+var_210]
0x1800691de  lea     r12d, [rcx+rax*4]
0x1800691e2  not     ecx
0x1800691e4  and     r12d, ecx
0x1800691e7  jz      loc_1800696CF
0x1800691ed  lea     r14d, ds:0[r15*4]
0x1800691f5  test    r14d, r14d
0x1800691f8  jz      loc_1800696CF
0x1800691fe  mov     [rbp+260h+var_2A2], 0
0x180069205  mov     ebx, 6Ch ; 'l'
0x18006920a  mov     r8d, ebx; Size
0x18006920d  xor     edx, edx; Val
0x18006920f  lea     rcx, [rbp+260h+var_290]; void *
0x180069213  call    memset_0
0x180069218  mov     eax, esi
0x18006921a  imul    eax, r15d
0x18006921e  lea     ecx, ds:0[rax*4]
0x180069225  mov     eax, 4D42h
0x18006922a  mov     [rbp+260h+Buffer], ax
0x18006922e  lea     eax, [rcx+7Ah]
0x180069231  mov     [rbp+260h+var_2A6], eax
0x180069234  mov     [rbp+260h+var_29E], 7Ah ; 'z'
0x18006923b  mov     [rbp+260h+var_290], ebx
0x18006923e  mov     [rbp+260h+var_28C], r15d
0x180069242  mov     eax, esi
0x180069244  neg     eax
0x180069246  mov     [rbp+260h+var_288], eax
0x180069249  mov     [rbp+260h+var_284], 200001h
0x180069250  mov     eax, 0EC4h
0x180069255  mov     [rbp+260h+var_278], eax
0x180069258  mov     [rbp+260h+var_274], eax
0x18006925b  mov     [rbp+260h+var_280], 3
0x180069262  mov     [rbp+260h+var_27C], ecx
0x180069265  xor     r15d, r15d
0x180069268  cmp     [rbp+260h+var_200], 18h
0x18006926c  jnz     short loc_18006928C
0x18006926e  mov     [rbp+260h+var_268], 3FFh
0x180069275  mov     [rbp+260h+var_264], 0FFC00h
0x18006927c  mov     [rbp+260h+var_260], 3FF00000h
0x180069283  mov     [rbp+260h+var_25C], 0C0000000h
0x18006928a  jmp     short loc_1800692BD
0x18006928c  mov     [rbp+260h+var_264], 0FF00h
0x180069293  mov     [rbp+260h+var_25C], 0FF000000h
0x18006929a  test    dil, dil
0x18006929d  jz      short loc_1800692AF
0x18006929f  mov     [rbp+260h+var_268], 0FF0000h
0x1800692a6  mov     [rbp+260h+var_260], 0FFh
0x1800692ad  jmp     short loc_1800692BD
0x1800692af  mov     [rbp+260h+var_268], 0FFh
0x1800692b6  mov     [rbp+260h+var_260], 0FF0000h
0x1800692bd  xorps   xmm0, xmm0
0x1800692c0  movups  xmmword ptr [rbp+260h+lpFileName], xmm0
0x1800692c4  mov     [rbp+260h+var_2B8], r15
0x1800692c8  mov     [rbp+260h+var_2B0], r15
0x1800692cc  lea     rcx, [rbp+260h+lpFileName]
0x1800692d0  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800692d5  nop
0x1800692d6  mov     rbx, [rbp+260h+var_2B8]
0x1800692da  mov     edx, 104h
0x1800692df  cmp     rbx, rdx
0x1800692e2  ja      short loc_1800692FE
0x1800692e4  cmp     [rbp+260h+var_2B0], 103h
0x1800692ec  ja      short loc_1800692FE
0x1800692ee  sub     rdx, rbx
0x1800692f1  lea     rcx, [rbp+260h+lpFileName]
0x1800692f5  call    ??$_Reallocate_grow_by@V_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(unsigned __int64,_lambda_7f96eb1dcf99da5daec8c2467d2d5499_)
0x1800692fa  mov     [rbp+260h+var_2B8], rbx
0x1800692fe  mov     [rsp+360h+ppszPath], r15
0x180069303  lea     r9, [rsp+360h+ppszPath]; ppszPath
0x180069308  xor     r8d, r8d; hToken
0x18006930b  xor     edx, edx; dwFlags
0x18006930d  lea     rcx, FOLDERID_Pictures; rfid
0x180069314  call    cs:__imp_SHGetKnownFolderPath
0x18006931a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006931e  test    eax, eax
0x180069320  js      short loc_180069353
0x180069322  mov     rdx, [rsp+360h+ppszPath]
0x180069327  mov     r8, rdi
0x18006932a  inc     r8
0x18006932d  cmp     [rdx+r8*2], r15w
0x180069332  jnz     short loc_18006932A
0x180069334  lea     rcx, [rbp+260h+lpFileName]; Src
0x180069338  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18006933d  mov     r8d, 1
0x180069343  lea     rdx, pszSrch; "\\"
0x18006934a  lea     rcx, [rbp+260h+lpFileName]; Src
0x18006934e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180069353  mov     ebx, 0C8h
0x180069358  mov     r8d, ebx; nSize
0x18006935b  lea     rdx, [rbp+260h+Filename]; lpFilename
0x180069362  xor     ecx, ecx; hModule
0x180069364  call    cs:__imp_GetModuleFileNameW
0x18006936a  test    eax, eax
0x18006936c  jz      loc_18006969F
0x180069372  cmp     eax, ebx
0x180069374  jz      loc_18006969F
0x18006937a  mov     edx, ebx; cchPath
0x18006937c  lea     rcx, [rbp+260h+Filename]; pszPath
0x180069383  call    cs:__imp_PathCchRemoveExtension
0x180069389  mov     ebx, eax
0x18006938b  test    eax, eax
0x18006938d  jns     short loc_1800693AF
0x18006938f  mov     r9d, eax; char *
0x180069392  mov     edx, 14Ah; void *
0x180069397  mov     rcx, [rbp+268h]; this
0x18006939e  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800693a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800693aa  jmp     loc_1800696B9
0x1800693af  lea     r8, pszSrch; "\\"
0x1800693b6  xor     edx, edx; pszLast
0x1800693b8  lea     rcx, [rbp+260h+Filename]; pszSource
0x1800693bf  call    cs:__imp_StrRStrIW
0x1800693c5  test    rax, rax
0x1800693c8  jnz     short loc_1800693D9
0x1800693ca  mov     ebx, 8000FFFFh
0x1800693cf  mov     r9d, ebx
0x1800693d2  mov     edx, 14Ch
0x1800693d7  jmp     short loc_180069397
0x1800693d9  lea     rdx, [rax+2]
0x1800693dd  mov     r8, rdi
0x1800693e0  inc     r8
0x1800693e3  cmp     [rdx+r8*2], r15w
0x1800693e8  jnz     short loc_1800693E0
0x1800693ea  lea     rcx, [rbp+260h+lpFileName]; Src
0x1800693ee  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800693f3  mov     ebx, 1
0x1800693f8  mov     r8d, ebx
0x1800693fb  lea     rdx, asc_1800D9E64; "_"
0x180069402  lea     rcx, [rbp+260h+lpFileName]; Src
0x180069406  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18006940b  mov     [rsp+360h+Time], r15
0x180069410  lea     rcx, [rsp+360h+Time]; Time
0x180069415  call    time
0x18006941a  lea     rcx, [rsp+360h+Time]; Time
0x18006941f  call    localtime
0x180069424  mov     r9, rax; Tm
0x180069427  lea     r8, aYMDHMS; "%y%m%d-%H%M%S"
0x18006942e  mov     edx, 0C8h; SizeInWords
0x180069433  lea     rcx, [rbp+260h+Filename]; Buffer
0x18006943a  call    cs:__imp_wcsftime
0x180069440  test    rax, rax
0x180069443  jnz     short loc_180069457
0x180069445  mov     ebx, 80004005h
0x18006944a  mov     r9d, ebx
0x18006944d  mov     edx, 155h
0x180069452  jmp     loc_180069397
0x180069457  lea     rax, [rbp+260h+Filename]
0x18006945e  mov     r8, rdi
0x180069461  inc     r8
0x180069464  cmp     [rax+r8*2], r15w
0x180069469  jnz     short loc_180069461
0x18006946b  lea     rdx, [rbp+260h+Filename]
0x180069472  lea     rcx, [rbp+260h+lpFileName]; Src
0x180069476  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18006947b  mov     r8, rbx
0x18006947e  lea     rdx, asc_1800D9E64; "_"
0x180069485  lea     rcx, [rbp+260h+lpFileName]; Src
0x180069489  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18006948e  inc     rdi
0x180069491  cmp     [r13+rdi*2+0], r15w
0x180069497  jnz     short loc_18006948E
0x180069499  mov     r8, rdi
0x18006949c  mov     rdx, r13
0x18006949f  lea     rcx, [rbp+260h+lpFileName]; Src
0x1800694a3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800694a8  mov     r8d, 4
0x1800694ae  lea     rdx, aBmp; ".bmp"
0x1800694b5  lea     rcx, [rbp+260h+lpFileName]; Src
0x1800694b9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800694be  nop
0x1800694bf  lea     rcx, [rsp+360h+ppszPath]
0x1800694c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800694c9  lea     rcx, [rbp+260h+lpFileName]
0x1800694cd  cmp     [rbp+260h+var_2B0], 7
0x1800694d2  cmova   rcx, [rbp+260h+lpFileName]; lpFileName
0x1800694d7  mov     [rsp+360h+hTemplateFile], r15; hTemplateFile
0x1800694dc  mov     [rsp+360h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800694e4  mov     [rsp+360h+dwCreationDisposition], 2; dwCreationDisposition
0x1800694ec  xor     r9d, r9d; lpSecurityAttributes
0x1800694ef  xor     r8d, r8d; dwShareMode
0x1800694f2  mov     edx, 40000000h; dwDesiredAccess
0x1800694f7  call    cs:__imp_CreateFileW
0x1800694fd  mov     [rsp+360h+hFile], rax
0x180069502  dec     rax
0x180069505  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180069509  ja      loc_180069679
0x18006950f  lea     r8, [rbp+260h+lpFileName]
0x180069513  lea     rdx, [rsp+360h+hFile]
0x180069518  lea     rcx, [rbp+260h+var_2D8]
0x18006951c  call    _lambda_8ea903bb4baaaddbccd7f9cae0e2e31e____lambda_8ea903bb4baaaddbccd7f9cae0e2e31e_
0x180069521  mov     rdx, rax
0x180069524  lea     rcx, [rsp+360h+var_2F0]
0x180069529  call    wil__scope_exit__lambda_8ea903bb4baaaddbccd7f9cae0e2e31e___
0x18006952e  mov     [rsp+360h+NumberOfBytesWritten], r15d
0x180069533  mov     qword ptr [rsp+360h+dwCreationDisposition], r15; lpOverlapped
0x180069538  lea     r9, [rsp+360h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006953d  mov     r8d, 0Eh; nNumberOfBytesToWrite
0x180069543  lea     rdx, [rbp+260h+Buffer]; lpBuffer
0x180069547  mov     rcx, [rsp+360h+hFile]; hFile
0x18006954c  call    cs:__imp_WriteFile
0x180069552  test    eax, eax
0x180069554  jnz     short loc_18006957F
0x180069556  mov     edx, 175h; void *
0x18006955b  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180069562  mov     rcx, [rbp+268h]; this
0x180069569  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006956e  mov     ebx, eax
0x180069570  lea     rcx, [rsp+360h+var_2F0]
0x180069575  call    wil__details__lambda_call__lambda_8ea903bb4baaaddbccd7f9cae0e2e31e______lambda_call__lambda_8ea903bb4baaaddbccd7f9cae0e2e31e___
0x18006957a  jmp     loc_180069693
0x18006957f  mov     qword ptr [rsp+360h+dwCreationDisposition], r15; lpOverlapped
0x180069584  lea     r9, [rsp+360h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180069589  mov     r8d, 6Ch ; 'l'; nNumberOfBytesToWrite
0x18006958f  lea     rdx, [rbp+260h+var_290]; lpBuffer
0x180069593  mov     rcx, [rsp+360h+hFile]; hFile
0x180069598  call    cs:__imp_WriteFile
0x18006959e  test    eax, eax
  ... truncated ...
```
