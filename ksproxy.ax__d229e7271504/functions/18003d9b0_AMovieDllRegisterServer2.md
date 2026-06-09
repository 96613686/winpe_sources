# AMovieDllRegisterServer2

- ea: `0x18003d9b0`
- end: `0x18003dba3`
- name: `AMovieDllRegisterServer2`
- size: `499`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025840`
- `0x180025850`

## callees

- `0x18001f620`
- `0x18003d94c`
- `0x18003d9b0`
- `0x18003dbac`
- `0x18003de64`
- `0x18003fd30`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003d9fb`
- `KERNEL32!GetLastError` at `0x18003d9fb`
- `KERNEL32!GetModuleFileNameA` at `0x18003d9eb`
- `KERNEL32!GetModuleFileNameA` at `0x18003d9eb`
- `KERNEL32!MultiByteToWideChar` at `0x18003da4f`
- `KERNEL32!MultiByteToWideChar` at `0x18003da4f`
- `ole32!CoUninitialize` at `0x18003db64`
- `ole32!CoUninitialize` at `0x18003db64`
- `ole32!CoFreeUnusedLibraries` at `0x18003db58`
- `ole32!CoFreeUnusedLibraries` at `0x18003db58`
- `ole32!CoInitializeEx` at `0x18003da7e`
- `ole32!CoInitializeEx` at `0x18003da7e`
- `ole32!CoCreateInstance` at `0x18003daba`
- `ole32!CoCreateInstance` at `0x18003daea`
- `ole32!CoCreateInstance` at `0x18003daba`
- `ole32!CoCreateInstance` at `0x18003daea`

## pseudocode

```c
__int64 __fastcall AMovieDllRegisterServer2(unsigned int a1)
{
  __int64 v2; // rdx
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
          v6 = qword_180051020[5 * v5];
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
        while ( (int)v5 < 8 );
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
0x18003d9b0  push    rbp
0x18003d9b2  push    rbx
0x18003d9b3  push    rsi
0x18003d9b4  push    rdi
0x18003d9b5  lea     rbp, [rsp-278h]
0x18003d9bd  sub     rsp, 378h
0x18003d9c4  mov     rax, cs:__security_cookie
0x18003d9cb  xor     rax, rsp
0x18003d9ce  mov     [rbp+290h+var_30], rax
0x18003d9d5  mov     esi, ecx
0x18003d9d7  lea     rdx, [rsp+390h+Filename]; lpFilename
0x18003d9dc  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18003d9e3  mov     ebx, 104h
0x18003d9e8  mov     r8d, ebx; nSize
0x18003d9eb  call    cs:__imp_GetModuleFileNameA
0x18003d9f2  nop     dword ptr [rax+rax+00h]
0x18003d9f7  test    eax, eax
0x18003d9f9  jnz     short loc_18003DA11
0x18003d9fb  call    cs:__imp_GetLastError
0x18003da02  nop     dword ptr [rax+rax+00h]
0x18003da07  or      eax, 80070000h
0x18003da0c  jmp     loc_18003DB87
0x18003da11  lea     r8, [rsp+390h+var_360]; unsigned __int64 *
0x18003da16  mov     [rsp+390h+var_360], 0
0x18003da1f  lea     rcx, [rsp+390h+Filename]; char *
0x18003da24  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18003da29  test    eax, eax
0x18003da2b  js      loc_18003DB87
0x18003da31  mov     r9d, dword ptr [rsp+390h+var_360]
0x18003da36  lea     rax, [rbp+290h+WideCharStr]
0x18003da3a  inc     r9d; cbMultiByte
0x18003da3d  mov     [rsp+390h+cchWideChar], ebx; cchWideChar
0x18003da41  lea     r8, [rsp+390h+Filename]; lpMultiByteStr
0x18003da46  mov     [rsp+390h+lpWideCharStr], rax; lpWideCharStr
0x18003da4b  xor     edx, edx; dwFlags
0x18003da4d  xor     ecx, ecx; CodePage
0x18003da4f  call    cs:__imp_MultiByteToWideChar
0x18003da56  nop     dword ptr [rax+rax+00h]
0x18003da5b  test    esi, esi
0x18003da5d  jz      short loc_18003DA77
0x18003da5f  mov     edx, 1
0x18003da64  lea     rcx, [rbp+290h+WideCharStr]
0x18003da68  call    RegisterAllServers
0x18003da6d  mov     ebx, eax
0x18003da6f  test    eax, eax
0x18003da71  js      loc_18003DB85
0x18003da77  mov     edx, 2; dwCoInit
0x18003da7c  xor     ecx, ecx; pvReserved
0x18003da7e  call    cs:__imp_CoInitializeEx
0x18003da85  nop     dword ptr [rax+rax+00h]
0x18003da8a  xor     edx, edx; pUnkOuter
0x18003da8c  mov     [rsp+390h+ppv], 0
0x18003da95  lea     rax, [rsp+390h+ppv]
0x18003da9a  mov     [rsp+390h+var_360], 0
0x18003daa3  lea     r9, IID_IFilterMapper2; riid
0x18003daaa  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x18003daaf  lea     rcx, CLSID_FilterMapper2; rclsid
0x18003dab6  lea     r8d, [rdx+1]; dwClsContext
0x18003daba  call    cs:__imp_CoCreateInstance
0x18003dac1  nop     dword ptr [rax+rax+00h]
0x18003dac6  mov     ebx, eax
0x18003dac8  test    eax, eax
0x18003daca  jns     short loc_18003DAFC
0x18003dacc  xor     edx, edx; pUnkOuter
0x18003dace  lea     rax, [rsp+390h+var_360]
0x18003dad3  lea     r9, IID_IFilterMapper; riid
0x18003dada  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x18003dadf  lea     rcx, CLSID_FilterMapper; rclsid
0x18003dae6  lea     r8d, [rdx+1]; dwClsContext
0x18003daea  call    cs:__imp_CoCreateInstance
0x18003daf1  nop     dword ptr [rax+rax+00h]
0x18003daf6  mov     ebx, eax
0x18003daf8  test    eax, eax
0x18003dafa  js      short loc_18003DB58
0x18003dafc  xor     edi, edi
0x18003dafe  lea     rcx, [rdi+rdi*4]
0x18003db02  lea     rax, qword_180051020
0x18003db09  mov     rcx, [rax+rcx*8]
0x18003db0d  test    rcx, rcx
0x18003db10  jz      short loc_18003DB32
0x18003db12  mov     rdx, [rsp+390h+ppv]
0x18003db17  mov     r8d, esi
0x18003db1a  test    rdx, rdx
0x18003db1d  jz      short loc_18003DB26
0x18003db1f  call    AMovieSetupRegisterFilter2
0x18003db24  jmp     short loc_18003DB30
0x18003db26  mov     rdx, [rsp+390h+var_360]
0x18003db2b  call    AMovieSetupRegisterFilter
0x18003db30  mov     ebx, eax
0x18003db32  test    ebx, ebx
0x18003db34  js      short loc_18003DB3D
0x18003db36  inc     edi
0x18003db38  cmp     edi, 8
0x18003db3b  jl      short loc_18003DAFE
0x18003db3d  mov     rcx, [rsp+390h+ppv]
0x18003db42  test    rcx, rcx
0x18003db45  jnz     short loc_18003DB4C
0x18003db47  mov     rcx, [rsp+390h+var_360]
0x18003db4c  mov     rax, [rcx]
0x18003db4f  mov     rax, [rax+10h]
0x18003db53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db58  call    cs:__imp_CoFreeUnusedLibraries
0x18003db5f  nop     dword ptr [rax+rax+00h]
0x18003db64  call    cs:__imp_CoUninitialize
0x18003db6b  nop     dword ptr [rax+rax+00h]
0x18003db70  test    ebx, ebx
0x18003db72  js      short loc_18003DB85
0x18003db74  test    esi, esi
0x18003db76  jnz     short loc_18003DB85
0x18003db78  xor     edx, edx
0x18003db7a  lea     rcx, [rbp+290h+WideCharStr]
0x18003db7e  call    RegisterAllServers
0x18003db83  mov     ebx, eax
0x18003db85  mov     eax, ebx
0x18003db87  mov     rcx, [rbp+290h+var_30]
0x18003db8e  xor     rcx, rsp; StackCookie
0x18003db91  call    __security_check_cookie
0x18003db96  add     rsp, 378h
0x18003db9d  pop     rdi
0x18003db9e  pop     rsi
0x18003db9f  pop     rbx
0x18003dba0  pop     rbp
0x18003dba1  retn
```
