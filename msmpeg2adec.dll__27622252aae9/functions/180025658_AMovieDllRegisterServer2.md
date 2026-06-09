# AMovieDllRegisterServer2

- ea: `0x180025658`
- end: `0x1800258b1`
- name: `AMovieDllRegisterServer2`
- size: `601`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180018b70`
- `0x180018dc0`

## callees

- `0x1800017b0`
- `0x180025658`
- `0x1800258b8`
- `0x180025980`
- `0x180025ccc`
- `0x180028934`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180025695`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180025695`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800257ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800257dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800257ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800257dd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180025771`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180025771`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180025846`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180025846`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180025852`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180025852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256a5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025714`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025714`

## pseudocode

```c
__int64 __fastcall AMovieDllRegisterServer2(unsigned int a1)
{
  __int64 result; // rax
  __int64 v3; // r8
  CHAR *v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rdx
  int Instance; // ebx
  __int64 v8; // rdi
  __int64 v9; // rcx
  int v10; // eax
  LPVOID v11; // rcx
  __int64 v12; // rdi
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR Filename[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+160h] [rbp+60h] BYREF

  if ( !GetModuleFileNameA(g_hInst, Filename, 0x104u) )
    return GetLastError() | 0x80070000;
  v3 = 260;
  v4 = Filename;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  result = v3 == 0 ? 0x80070057 : 0;
  if ( v3 )
  {
    MultiByteToWideChar(0, 0, Filename, v3 != 0 ? 260 - v3 + 1 : 1, WideCharStr, 260);
    if ( a1 )
    {
      v5 = 0;
      while ( 1 )
      {
        v6 = (__int64)*(&g_Templates + 5 * v5);
        *(_OWORD *)v14 = *(_OWORD *)*(&g_Templates + 5 * v5 + 1);
        Instance = AMovieSetupRegisterServer((const GUID *)v14, v6, (__int64)WideCharStr);
        if ( Instance < 0 )
          break;
        v5 = (unsigned int)(v5 + 1);
        if ( (int)v5 >= 1 )
          goto LABEL_11;
      }
    }
    else
    {
LABEL_11:
      CoInitializeEx(0, 2u);
      ppv = 0;
      v14[0] = 0;
      Instance = CoCreateInstance(&CLSID_FilterMapper2, 0, 1u, &IID_IFilterMapper2, &ppv);
      if ( Instance >= 0
        || (Instance = CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, v14), Instance >= 0) )
      {
        v8 = 0;
        do
        {
          v9 = (__int64)*(&g_Templates + 5 * v8 + 4);
          if ( v9 )
          {
            if ( ppv )
              v10 = AMovieSetupRegisterFilter2(v9, ppv, a1);
            else
              v10 = AMovieSetupRegisterFilter(v9, v14[0], a1);
            Instance = v10;
          }
          if ( Instance < 0 )
            break;
          v8 = (unsigned int)(v8 + 1);
        }
        while ( (int)v8 < 1 );
        v11 = ppv;
        if ( !ppv )
          v11 = v14[0];
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
      }
      CoFreeUnusedLibraries();
      CoUninitialize();
      if ( Instance >= 0 && !a1 )
      {
        v12 = 0;
        do
        {
          *(_OWORD *)v14 = *(_OWORD *)*(&g_Templates + 5 * v12 + 1);
          Instance = AMovieSetupUnregisterServer(v14);
          if ( Instance < 0 )
            break;
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (int)v12 < 1 );
      }
    }
    return (unsigned int)Instance;
  }
  return result;
}

```

## disassembly

```asm
0x180025658  push    rbp
0x18002565a  push    rbx
0x18002565b  push    rsi
0x18002565c  push    rdi
0x18002565d  push    r12
0x18002565f  lea     rbp, [rsp-280h]
0x180025667  sub     rsp, 380h
0x18002566e  mov     rax, cs:__security_cookie
0x180025675  xor     rax, rsp
0x180025678  mov     [rbp+2A0h+var_30], rax
0x18002567f  mov     esi, ecx
0x180025681  lea     rdx, [rsp+3A0h+Filename]; lpFilename
0x180025686  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18002568d  mov     ebx, 104h
0x180025692  mov     r8d, ebx; nSize
0x180025695  call    cs:__imp_GetModuleFileNameA
0x18002569c  nop     dword ptr [rax+rax+00h]
0x1800256a1  test    eax, eax
0x1800256a3  jnz     short loc_1800256BB
0x1800256a5  call    cs:__imp_GetLastError
0x1800256ac  nop     dword ptr [rax+rax+00h]
0x1800256b1  or      eax, 80070000h
0x1800256b6  jmp     loc_180025893
0x1800256bb  mov     r8, rbx
0x1800256be  lea     rax, [rsp+3A0h+Filename]
0x1800256c3  cmp     byte ptr [rax], 0
0x1800256c6  jz      short loc_1800256D1
0x1800256c8  inc     rax
0x1800256cb  sub     r8, 1
0x1800256cf  jnz     short loc_1800256C3
0x1800256d1  mov     rax, r8
0x1800256d4  mov     rdx, rbx
0x1800256d7  neg     rax
0x1800256da  mov     rcx, r8
0x1800256dd  sbb     eax, eax
0x1800256df  sub     rdx, r8
0x1800256e2  not     eax
0x1800256e4  and     eax, 80070057h
0x1800256e9  neg     rcx
0x1800256ec  sbb     r9, r9
0x1800256ef  and     r9, rdx
0x1800256f2  test    r8, r8
0x1800256f5  jz      loc_180025893
0x1800256fb  lea     rax, [rbp+2A0h+WideCharStr]
0x1800256ff  mov     [rsp+3A0h+cchWideChar], ebx; cchWideChar
0x180025703  inc     r9d; cbMultiByte
0x180025706  mov     [rsp+3A0h+lpWideCharStr], rax; lpWideCharStr
0x18002570b  lea     r8, [rsp+3A0h+Filename]; lpMultiByteStr
0x180025710  xor     edx, edx; dwFlags
0x180025712  xor     ecx, ecx; CodePage
0x180025714  call    cs:__imp_MultiByteToWideChar
0x18002571b  nop     dword ptr [rax+rax+00h]
0x180025720  lea     r12, ?g_Templates@@3PAVCFactoryTemplate@@A; CFactoryTemplate near * g_Templates
0x180025727  test    esi, esi
0x180025729  jz      short loc_18002576A
0x18002572b  xor     edi, edi
0x18002572d  lea     rdx, [rdi+rdi*4]
0x180025731  mov     rax, [r12+rdx*8+8]
0x180025736  lea     r8, [rbp+2A0h+WideCharStr]
0x18002573a  mov     rdx, [r12+rdx*8]
0x18002573e  lea     rcx, [rsp+3A0h+var_360]
0x180025743  movups  xmm0, xmmword ptr [rax]
0x180025746  movdqu  xmmword ptr [rsp+3A0h+var_360], xmm0
0x18002574c  call    AMovieSetupRegisterServer
0x180025751  mov     ebx, eax
0x180025753  test    eax, eax
0x180025755  js      loc_180025891
0x18002575b  inc     edi
0x18002575d  cmp     edi, 1
0x180025760  jl      short loc_18002572D
0x180025762  test    eax, eax
0x180025764  js      loc_180025891
0x18002576a  mov     edx, 2; dwCoInit
0x18002576f  xor     ecx, ecx; pvReserved
0x180025771  call    cs:__imp_CoInitializeEx
0x180025778  nop     dword ptr [rax+rax+00h]
0x18002577d  xor     edx, edx; pUnkOuter
0x18002577f  mov     [rsp+3A0h+ppv], 0
0x180025788  lea     rax, [rsp+3A0h+ppv]
0x18002578d  mov     [rsp+3A0h+var_360], 0
0x180025796  lea     r9, IID_IFilterMapper2; riid
0x18002579d  mov     [rsp+3A0h+lpWideCharStr], rax; ppv
0x1800257a2  lea     rcx, CLSID_FilterMapper2; rclsid
0x1800257a9  lea     r8d, [rdx+1]; dwClsContext
0x1800257ad  call    cs:__imp_CoCreateInstance
0x1800257b4  nop     dword ptr [rax+rax+00h]
0x1800257b9  mov     ebx, eax
0x1800257bb  test    eax, eax
0x1800257bd  jns     short loc_1800257EF
0x1800257bf  xor     edx, edx; pUnkOuter
0x1800257c1  lea     rax, [rsp+3A0h+var_360]
0x1800257c6  lea     r9, IID_IFilterMapper; riid
0x1800257cd  mov     [rsp+3A0h+lpWideCharStr], rax; ppv
0x1800257d2  lea     rcx, CLSID_FilterMapper; rclsid
0x1800257d9  lea     r8d, [rdx+1]; dwClsContext
0x1800257dd  call    cs:__imp_CoCreateInstance
0x1800257e4  nop     dword ptr [rax+rax+00h]
0x1800257e9  mov     ebx, eax
0x1800257eb  test    eax, eax
0x1800257ed  js      short loc_180025846
0x1800257ef  xor     edi, edi
0x1800257f1  lea     rcx, [rdi+rdi*4]
0x1800257f5  mov     rcx, [r12+rcx*8+20h]
0x1800257fa  test    rcx, rcx
0x1800257fd  jz      short loc_18002581F
0x1800257ff  mov     rdx, [rsp+3A0h+ppv]
0x180025804  mov     r8d, esi
0x180025807  test    rdx, rdx
0x18002580a  jz      short loc_180025813
0x18002580c  call    AMovieSetupRegisterFilter2
0x180025811  jmp     short loc_18002581D
0x180025813  mov     rdx, [rsp+3A0h+var_360]
0x180025818  call    AMovieSetupRegisterFilter
0x18002581d  mov     ebx, eax
0x18002581f  test    ebx, ebx
0x180025821  js      short loc_18002582A
0x180025823  inc     edi
0x180025825  cmp     edi, 1
0x180025828  jl      short loc_1800257F1
0x18002582a  mov     rcx, [rsp+3A0h+ppv]
0x18002582f  test    rcx, rcx
0x180025832  jnz     short loc_180025839
0x180025834  mov     rcx, [rsp+3A0h+var_360]
0x180025839  mov     rax, [rcx]
0x18002583c  mov     rax, [rax+10h]
0x180025840  call    cs:__guard_dispatch_icall_fptr
0x180025846  call    cs:__imp_CoFreeUnusedLibraries
0x18002584d  nop     dword ptr [rax+rax+00h]
0x180025852  call    cs:__imp_CoUninitialize
0x180025859  nop     dword ptr [rax+rax+00h]
0x18002585e  test    ebx, ebx
0x180025860  js      short loc_180025891
0x180025862  test    esi, esi
0x180025864  jnz     short loc_180025891
0x180025866  xor     edi, edi
0x180025868  lea     rax, [rdi+rdi*4]
0x18002586c  mov     rax, [r12+rax*8+8]
0x180025871  lea     rcx, [rsp+3A0h+var_360]
0x180025876  movups  xmm0, xmmword ptr [rax]
0x180025879  movdqu  xmmword ptr [rsp+3A0h+var_360], xmm0
0x18002587f  call    AMovieSetupUnregisterServer
0x180025884  mov     ebx, eax
0x180025886  test    eax, eax
0x180025888  js      short loc_180025891
0x18002588a  inc     edi
0x18002588c  cmp     edi, 1
0x18002588f  jl      short loc_180025868
0x180025891  mov     eax, ebx
0x180025893  mov     rcx, [rbp+2A0h+var_30]
0x18002589a  xor     rcx, rsp; StackCookie
0x18002589d  call    __security_check_cookie
0x1800258a2  add     rsp, 380h
0x1800258a9  pop     r12
0x1800258ab  pop     rdi
0x1800258ac  pop     rsi
0x1800258ad  pop     rbx
0x1800258ae  pop     rbp
0x1800258af  retn
```
