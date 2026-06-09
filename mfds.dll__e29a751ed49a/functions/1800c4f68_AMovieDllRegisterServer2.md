# AMovieDllRegisterServer2

- ea: `0x1800c4f68`
- end: `0x1800c515b`
- name: `AMovieDllRegisterServer2`
- size: `499`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007b2a0`
- `0x18007b310`

## callees

- `0x180074160`
- `0x1800c4f04`
- `0x1800c4f68`
- `0x1800c5164`
- `0x1800c541c`
- `0x1800c6b00`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4fb3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c5072`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c50a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c5072`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c50a2`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800c5110`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800c5110`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c511c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c511c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c5036`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c5036`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800c4fa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800c4fa3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c5007`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c5007`

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
          v6 = qword_1800EA020[5 * v5];
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
        while ( (int)v5 < 4 );
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
0x1800c4f68  push    rbp
0x1800c4f6a  push    rbx
0x1800c4f6b  push    rsi
0x1800c4f6c  push    rdi
0x1800c4f6d  lea     rbp, [rsp-278h]
0x1800c4f75  sub     rsp, 378h
0x1800c4f7c  mov     rax, cs:__security_cookie
0x1800c4f83  xor     rax, rsp
0x1800c4f86  mov     [rbp+290h+var_30], rax
0x1800c4f8d  mov     esi, ecx
0x1800c4f8f  lea     rdx, [rsp+390h+Filename]; lpFilename
0x1800c4f94  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x1800c4f9b  mov     ebx, 104h
0x1800c4fa0  mov     r8d, ebx; nSize
0x1800c4fa3  call    cs:__imp_GetModuleFileNameA
0x1800c4faa  nop     dword ptr [rax+rax+00h]
0x1800c4faf  test    eax, eax
0x1800c4fb1  jnz     short loc_1800C4FC9
0x1800c4fb3  call    cs:__imp_GetLastError
0x1800c4fba  nop     dword ptr [rax+rax+00h]
0x1800c4fbf  or      eax, 80070000h
0x1800c4fc4  jmp     loc_1800C513F
0x1800c4fc9  lea     r8, [rsp+390h+var_360]; unsigned __int64 *
0x1800c4fce  mov     [rsp+390h+var_360], 0
0x1800c4fd7  lea     rcx, [rsp+390h+Filename]; char *
0x1800c4fdc  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800c4fe1  test    eax, eax
0x1800c4fe3  js      loc_1800C513F
0x1800c4fe9  mov     r9d, dword ptr [rsp+390h+var_360]
0x1800c4fee  lea     rax, [rbp+290h+WideCharStr]
0x1800c4ff2  inc     r9d; cbMultiByte
0x1800c4ff5  mov     [rsp+390h+cchWideChar], ebx; cchWideChar
0x1800c4ff9  lea     r8, [rsp+390h+Filename]; lpMultiByteStr
0x1800c4ffe  mov     [rsp+390h+lpWideCharStr], rax; lpWideCharStr
0x1800c5003  xor     edx, edx; dwFlags
0x1800c5005  xor     ecx, ecx; CodePage
0x1800c5007  call    cs:__imp_MultiByteToWideChar
0x1800c500e  nop     dword ptr [rax+rax+00h]
0x1800c5013  test    esi, esi
0x1800c5015  jz      short loc_1800C502F
0x1800c5017  mov     edx, 1
0x1800c501c  lea     rcx, [rbp+290h+WideCharStr]
0x1800c5020  call    RegisterAllServers
0x1800c5025  mov     ebx, eax
0x1800c5027  test    eax, eax
0x1800c5029  js      loc_1800C513D
0x1800c502f  mov     edx, 2; dwCoInit
0x1800c5034  xor     ecx, ecx; pvReserved
0x1800c5036  call    cs:__imp_CoInitializeEx
0x1800c503d  nop     dword ptr [rax+rax+00h]
0x1800c5042  xor     edx, edx; pUnkOuter
0x1800c5044  mov     [rsp+390h+ppv], 0
0x1800c504d  lea     rax, [rsp+390h+ppv]
0x1800c5052  mov     [rsp+390h+var_360], 0
0x1800c505b  lea     r9, IID_IFilterMapper2; riid
0x1800c5062  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x1800c5067  lea     rcx, CLSID_FilterMapper2; rclsid
0x1800c506e  lea     r8d, [rdx+1]; dwClsContext
0x1800c5072  call    cs:__imp_CoCreateInstance
0x1800c5079  nop     dword ptr [rax+rax+00h]
0x1800c507e  mov     ebx, eax
0x1800c5080  test    eax, eax
0x1800c5082  jns     short loc_1800C50B4
0x1800c5084  xor     edx, edx; pUnkOuter
0x1800c5086  lea     rax, [rsp+390h+var_360]
0x1800c508b  lea     r9, IID_IFilterMapper; riid
0x1800c5092  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x1800c5097  lea     rcx, CLSID_FilterMapper; rclsid
0x1800c509e  lea     r8d, [rdx+1]; dwClsContext
0x1800c50a2  call    cs:__imp_CoCreateInstance
0x1800c50a9  nop     dword ptr [rax+rax+00h]
0x1800c50ae  mov     ebx, eax
0x1800c50b0  test    eax, eax
0x1800c50b2  js      short loc_1800C5110
0x1800c50b4  xor     edi, edi
0x1800c50b6  lea     rcx, [rdi+rdi*4]
0x1800c50ba  lea     rax, qword_1800EA020
0x1800c50c1  mov     rcx, [rax+rcx*8]
0x1800c50c5  test    rcx, rcx
0x1800c50c8  jz      short loc_1800C50EA
0x1800c50ca  mov     rdx, [rsp+390h+ppv]
0x1800c50cf  mov     r8d, esi
0x1800c50d2  test    rdx, rdx
0x1800c50d5  jz      short loc_1800C50DE
0x1800c50d7  call    AMovieSetupRegisterFilter2
0x1800c50dc  jmp     short loc_1800C50E8
0x1800c50de  mov     rdx, [rsp+390h+var_360]
0x1800c50e3  call    AMovieSetupRegisterFilter
0x1800c50e8  mov     ebx, eax
0x1800c50ea  test    ebx, ebx
0x1800c50ec  js      short loc_1800C50F5
0x1800c50ee  inc     edi
0x1800c50f0  cmp     edi, 4
0x1800c50f3  jl      short loc_1800C50B6
0x1800c50f5  mov     rcx, [rsp+390h+ppv]
0x1800c50fa  test    rcx, rcx
0x1800c50fd  jnz     short loc_1800C5104
0x1800c50ff  mov     rcx, [rsp+390h+var_360]
0x1800c5104  mov     rax, [rcx]
0x1800c5107  mov     rax, [rax+10h]
0x1800c510b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5110  call    cs:__imp_CoFreeUnusedLibraries
0x1800c5117  nop     dword ptr [rax+rax+00h]
0x1800c511c  call    cs:__imp_CoUninitialize
0x1800c5123  nop     dword ptr [rax+rax+00h]
0x1800c5128  test    ebx, ebx
0x1800c512a  js      short loc_1800C513D
0x1800c512c  test    esi, esi
0x1800c512e  jnz     short loc_1800C513D
0x1800c5130  xor     edx, edx
0x1800c5132  lea     rcx, [rbp+290h+WideCharStr]
0x1800c5136  call    RegisterAllServers
0x1800c513b  mov     ebx, eax
0x1800c513d  mov     eax, ebx
0x1800c513f  mov     rcx, [rbp+290h+var_30]
0x1800c5146  xor     rcx, rsp; StackCookie
0x1800c5149  call    __security_check_cookie
0x1800c514e  add     rsp, 378h
0x1800c5155  pop     rdi
0x1800c5156  pop     rsi
0x1800c5157  pop     rbx
0x1800c5158  pop     rbp
0x1800c5159  retn
```
