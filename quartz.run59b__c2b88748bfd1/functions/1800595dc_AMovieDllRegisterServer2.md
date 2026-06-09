# AMovieDllRegisterServer2

- ea: `0x1800595dc`
- end: `0x1800597cf`
- name: `AMovieDllRegisterServer2`
- size: `499`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800580c0`
- `0x1800582b0`
- `0x1800f4be0`

## callees

- `0x1800388a0`
- `0x180059578`
- `0x1800595dc`
- `0x1800597d8`
- `0x180059a90`
- `0x18005bf50`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180059627`
- `KERNEL32!GetLastError` at `0x180059627`
- `KERNEL32!MultiByteToWideChar` at `0x18005967b`
- `KERNEL32!MultiByteToWideChar` at `0x18005967b`
- `KERNEL32!GetModuleFileNameA` at `0x180059617`
- `KERNEL32!GetModuleFileNameA` at `0x180059617`
- `ole32!CoUninitialize` at `0x180059790`
- `ole32!CoUninitialize` at `0x180059790`
- `ole32!CoFreeUnusedLibraries` at `0x180059784`
- `ole32!CoFreeUnusedLibraries` at `0x180059784`
- `ole32!CoInitializeEx` at `0x1800596aa`
- `ole32!CoInitializeEx` at `0x1800596aa`
- `ole32!CoCreateInstance` at `0x1800596e6`
- `ole32!CoCreateInstance` at `0x180059716`
- `ole32!CoCreateInstance` at `0x1800596e6`
- `ole32!CoCreateInstance` at `0x180059716`

## pseudocode

```c
__int64 __fastcall AMovieDllRegisterServer2(unsigned int a1)
{
  unsigned __int64 v2; // rdx
  __int64 result; // rax
  HRESULT v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // rcx
  HRESULT v7; // eax
  LPVOID v8; // rcx
  LPVOID v9; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  CHAR Filename[272]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+150h] [rbp+50h] BYREF

  if ( !GetModuleFileNameA(g_hInst, Filename, 0x104u) )
    return GetLastError() | 0x80070000;
  v9 = 0;
  result = StringCchLengthA(Filename, v2, (unsigned __int64 *)&v9);
  if ( (int)result >= 0 )
  {
    MultiByteToWideChar(0, 0, Filename, (_DWORD)v9 + 1, WideCharStr, 260);
    if ( !a1 || (v4 = RegisterAllServers(WideCharStr, 1), v4 >= 0) )
    {
      CoInitializeEx(0, 2u);
      ppv = 0;
      v9 = 0;
      v4 = CoCreateInstance(&CLSID_FilterMapper2, 0, 1u, &IID_IFilterMapper2, &ppv);
      if ( v4 >= 0 || (v4 = CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &v9), v4 >= 0) )
      {
        v5 = 0;
        do
        {
          v6 = qword_18019A080[5 * v5];
          if ( v6 )
          {
            if ( ppv )
              v7 = AMovieSetupRegisterFilter2(v6, ppv, a1);
            else
              v7 = AMovieSetupRegisterFilter(v6, v9, a1);
            v4 = v7;
          }
          if ( v4 < 0 )
            break;
          v5 = (unsigned int)(v5 + 1);
        }
        while ( (int)v5 < 53 );
        v8 = ppv;
        if ( !ppv )
          v8 = v9;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
      }
      CoFreeUnusedLibraries();
      CoUninitialize();
      if ( v4 >= 0 && !a1 )
        return (unsigned int)RegisterAllServers(WideCharStr, 0);
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800595dc  push    rbp
0x1800595de  push    rbx
0x1800595df  push    rsi
0x1800595e0  push    rdi
0x1800595e1  lea     rbp, [rsp-278h]
0x1800595e9  sub     rsp, 378h
0x1800595f0  mov     rax, cs:__security_cookie
0x1800595f7  xor     rax, rsp
0x1800595fa  mov     [rbp+290h+var_30], rax
0x180059601  mov     esi, ecx
0x180059603  lea     rdx, [rsp+390h+Filename]; lpFilename
0x180059608  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18005960f  mov     ebx, 104h
0x180059614  mov     r8d, ebx; nSize
0x180059617  call    cs:__imp_GetModuleFileNameA
0x18005961e  nop     dword ptr [rax+rax+00h]
0x180059623  test    eax, eax
0x180059625  jnz     short loc_18005963D
0x180059627  call    cs:__imp_GetLastError
0x18005962e  nop     dword ptr [rax+rax+00h]
0x180059633  or      eax, 80070000h
0x180059638  jmp     loc_1800597B3
0x18005963d  lea     r8, [rsp+390h+var_360]; unsigned __int64 *
0x180059642  mov     [rsp+390h+var_360], 0
0x18005964b  lea     rcx, [rsp+390h+Filename]; char *
0x180059650  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180059655  test    eax, eax
0x180059657  js      loc_1800597B3
0x18005965d  mov     r9d, dword ptr [rsp+390h+var_360]
0x180059662  lea     rax, [rbp+290h+WideCharStr]
0x180059666  inc     r9d; cbMultiByte
0x180059669  mov     [rsp+390h+cchWideChar], ebx; cchWideChar
0x18005966d  lea     r8, [rsp+390h+Filename]; lpMultiByteStr
0x180059672  mov     [rsp+390h+lpWideCharStr], rax; lpWideCharStr
0x180059677  xor     edx, edx; dwFlags
0x180059679  xor     ecx, ecx; CodePage
0x18005967b  call    cs:__imp_MultiByteToWideChar
0x180059682  nop     dword ptr [rax+rax+00h]
0x180059687  test    esi, esi
0x180059689  jz      short loc_1800596A3
0x18005968b  mov     edx, 1
0x180059690  lea     rcx, [rbp+290h+WideCharStr]
0x180059694  call    RegisterAllServers
0x180059699  mov     ebx, eax
0x18005969b  test    eax, eax
0x18005969d  js      loc_1800597B1
0x1800596a3  mov     edx, 2; dwCoInit
0x1800596a8  xor     ecx, ecx; pvReserved
0x1800596aa  call    cs:__imp_CoInitializeEx
0x1800596b1  nop     dword ptr [rax+rax+00h]
0x1800596b6  xor     edx, edx; pUnkOuter
0x1800596b8  mov     [rsp+390h+ppv], 0
0x1800596c1  lea     rax, [rsp+390h+ppv]
0x1800596c6  mov     [rsp+390h+var_360], 0
0x1800596cf  lea     r9, IID_IFilterMapper2; riid
0x1800596d6  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x1800596db  lea     rcx, CLSID_FilterMapper2; rclsid
0x1800596e2  lea     r8d, [rdx+1]; dwClsContext
0x1800596e6  call    cs:__imp_CoCreateInstance
0x1800596ed  nop     dword ptr [rax+rax+00h]
0x1800596f2  mov     ebx, eax
0x1800596f4  test    eax, eax
0x1800596f6  jns     short loc_180059728
0x1800596f8  xor     edx, edx; pUnkOuter
0x1800596fa  lea     rax, [rsp+390h+var_360]
0x1800596ff  lea     r9, IID_IFilterMapper; riid
0x180059706  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x18005970b  lea     rcx, CLSID_FilterMapper; rclsid
0x180059712  lea     r8d, [rdx+1]; dwClsContext
0x180059716  call    cs:__imp_CoCreateInstance
0x18005971d  nop     dword ptr [rax+rax+00h]
0x180059722  mov     ebx, eax
0x180059724  test    eax, eax
0x180059726  js      short loc_180059784
0x180059728  xor     edi, edi
0x18005972a  lea     rcx, [rdi+rdi*4]
0x18005972e  lea     rax, qword_18019A080
0x180059735  mov     rcx, [rax+rcx*8]
0x180059739  test    rcx, rcx
0x18005973c  jz      short loc_18005975E
0x18005973e  mov     rdx, [rsp+390h+ppv]
0x180059743  mov     r8d, esi
0x180059746  test    rdx, rdx
0x180059749  jz      short loc_180059752
0x18005974b  call    AMovieSetupRegisterFilter2
0x180059750  jmp     short loc_18005975C
0x180059752  mov     rdx, [rsp+390h+var_360]
0x180059757  call    AMovieSetupRegisterFilter
0x18005975c  mov     ebx, eax
0x18005975e  test    ebx, ebx
0x180059760  js      short loc_180059769
0x180059762  inc     edi
0x180059764  cmp     edi, 35h ; '5'
0x180059767  jl      short loc_18005972A
0x180059769  mov     rcx, [rsp+390h+ppv]
0x18005976e  test    rcx, rcx
0x180059771  jnz     short loc_180059778
0x180059773  mov     rcx, [rsp+390h+var_360]
0x180059778  mov     rax, [rcx]
0x18005977b  mov     rax, [rax+10h]
0x18005977f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059784  call    cs:__imp_CoFreeUnusedLibraries
0x18005978b  nop     dword ptr [rax+rax+00h]
0x180059790  call    cs:__imp_CoUninitialize
0x180059797  nop     dword ptr [rax+rax+00h]
0x18005979c  test    ebx, ebx
0x18005979e  js      short loc_1800597B1
0x1800597a0  test    esi, esi
0x1800597a2  jnz     short loc_1800597B1
0x1800597a4  xor     edx, edx
0x1800597a6  lea     rcx, [rbp+290h+WideCharStr]
0x1800597aa  call    RegisterAllServers
0x1800597af  mov     ebx, eax
0x1800597b1  mov     eax, ebx
0x1800597b3  mov     rcx, [rbp+290h+var_30]
0x1800597ba  xor     rcx, rsp; StackCookie
0x1800597bd  call    __security_check_cookie
0x1800597c2  add     rsp, 378h
0x1800597c9  pop     rdi
0x1800597ca  pop     rsi
0x1800597cb  pop     rbx
0x1800597cc  pop     rbp
0x1800597cd  retn
```
