# AMovieDllRegisterServer2(x)

- ea: `0x1002f5a5`
- end: `0x1002f730`
- name: `_AMovieDllRegisterServer2@4`
- size: `395`
- prototype: `signed int __usercall@<eax>(int@<ecx>, unsigned int@<esi>)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x10008150`
- `0x10008160`

## callees

- `0x1002d510`
- `0x1002f03d`
- `0x1002f4c5`
- `0x1002f547`
- `0x1002f5a5`
- `0x1003341a`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1002f5db`
- `KERNEL32!GetLastError` at `0x1002f5db`
- `KERNEL32!GetModuleFileNameA` at `0x1002f5d1`
- `KERNEL32!GetModuleFileNameA` at `0x1002f5d1`
- `KERNEL32!MultiByteToWideChar` at `0x1002f627`
- `KERNEL32!MultiByteToWideChar` at `0x1002f627`
- `ole32!CoUninitialize` at `0x1002f702`
- `ole32!CoUninitialize` at `0x1002f702`
- `ole32!CoFreeUnusedLibraries` at `0x1002f6fc`
- `ole32!CoFreeUnusedLibraries` at `0x1002f6fc`
- `ole32!CoInitializeEx` at `0x1002f64c`
- `ole32!CoInitializeEx` at `0x1002f64c`
- `ole32!CoCreateInstance` at `0x1002f672`
- `ole32!CoCreateInstance` at `0x1002f692`
- `ole32!CoCreateInstance` at `0x1002f672`
- `ole32!CoCreateInstance` at `0x1002f692`

## pseudocode

```c
signed int __usercall AMovieDllRegisterServer2@<eax>(int a1@<ecx>, unsigned int a2@<esi>)
{
  signed int result; // eax
  int v4; // esi
  HRESULT v5; // edi
  _DWORD *v6; // ecx
  int v7; // eax
  unsigned int *v9; // [esp+0h] [ebp-320h]
  LPVOID ppv; // [esp+8h] [ebp-318h] BYREF
  LPVOID v11; // [esp+Ch] [ebp-314h] BYREF
  WCHAR WideCharStr[260]; // [esp+10h] [ebp-310h] BYREF
  CHAR Filename[260]; // [esp+218h] [ebp-108h] BYREF

  if ( !GetModuleFileNameA(g_hInst, Filename, 0x104u) )
    return GetLastError() | 0x80070000;
  v4 = 0;
  v11 = 0;
  result = StringCchLengthA(Filename, (char *)&v11, a2, v9);
  if ( result >= 0 )
  {
    MultiByteToWideChar(0, 0, Filename, (int)v11 + 1, WideCharStr, 260);
    if ( !a1 || (v5 = RegisterAllServers((int)WideCharStr, 1), v5 >= 0) )
    {
      CoInitializeEx(0, 2u);
      ppv = 0;
      v11 = 0;
      v5 = CoCreateInstance(&CLSID_FilterMapper2, 0, 1u, &IID_IFilterMapper2, &ppv);
      if ( v5 >= 0 || (v5 = CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &v11), v5 >= 0) )
      {
        do
        {
          v6 = (_DWORD *)dword_1003D010[5 * v4];
          if ( v6 )
          {
            if ( ppv )
              v7 = AMovieSetupRegisterFilter2(v6, (int *)ppv, a1);
            else
              v7 = AMovieSetupRegisterFilter(a1);
            v5 = v7;
          }
          if ( v5 < 0 )
            break;
          ++v4;
        }
        while ( v4 < 8 );
        if ( ppv )
          (*(void (__thiscall **)(_DWORD, LPVOID))(*(_DWORD *)ppv + 8))(*(_DWORD *)(*(_DWORD *)ppv + 8), ppv);
        else
          (*(void (__thiscall **)(_DWORD, LPVOID))(*(_DWORD *)v11 + 8))(*(_DWORD *)(*(_DWORD *)v11 + 8), v11);
      }
      CoFreeUnusedLibraries();
      CoUninitialize();
      if ( v5 >= 0 && !a1 )
        return RegisterAllServers((int)WideCharStr, 0);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1002f5a5  mov     edi, edi
0x1002f5a7  push    ebp
0x1002f5a8  mov     ebp, esp
0x1002f5aa  sub     esp, 318h
0x1002f5b0  mov     eax, ___security_cookie
0x1002f5b5  xor     eax, ebp
0x1002f5b7  mov     [ebp+var_4], eax
0x1002f5ba  push    ebx
0x1002f5bb  push    edi; unsigned int *
0x1002f5bc  mov     edi, 104h
0x1002f5c1  lea     eax, [ebp+Filename]
0x1002f5c7  push    edi; nSize
0x1002f5c8  push    eax; lpFilename
0x1002f5c9  push    ?g_hInst@@3PAUHINSTANCE__@@A; hModule
0x1002f5cf  mov     ebx, ecx
0x1002f5d1  call    ds:__imp__GetModuleFileNameA@12; GetModuleFileNameA(x,x,x)
0x1002f5d7  test    eax, eax
0x1002f5d9  jnz     short loc_1002F5EB
0x1002f5db  call    ds:__imp__GetLastError@0; GetLastError()
0x1002f5e1  or      eax, 80070000h
0x1002f5e6  jmp     loc_1002F722
0x1002f5eb  push    esi; unsigned int
0x1002f5ec  lea     eax, [ebp+var_314]
0x1002f5f2  xor     esi, esi
0x1002f5f4  push    eax; char *
0x1002f5f5  lea     ecx, [ebp+Filename]
0x1002f5fb  mov     [ebp+var_314], esi
0x1002f601  call    ?StringCchLengthA@@YGJPBDIPAI@Z; StringCchLengthA(char const *,uint,uint *)
0x1002f606  test    eax, eax
0x1002f608  js      loc_1002F721
0x1002f60e  push    edi; cchWideChar
0x1002f60f  lea     eax, [ebp+WideCharStr]
0x1002f615  push    eax; lpWideCharStr
0x1002f616  mov     eax, [ebp+var_314]
0x1002f61c  inc     eax
0x1002f61d  push    eax; cbMultiByte
0x1002f61e  lea     eax, [ebp+Filename]
0x1002f624  push    eax; lpMultiByteStr
0x1002f625  push    esi; dwFlags
0x1002f626  push    esi; CodePage
0x1002f627  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x1002f62d  test    ebx, ebx
0x1002f62f  jz      short loc_1002F649
0x1002f631  xor     edx, edx
0x1002f633  lea     ecx, [ebp+WideCharStr]
0x1002f639  inc     edx
0x1002f63a  call    _RegisterAllServers@8; RegisterAllServers(x,x)
0x1002f63f  mov     edi, eax
0x1002f641  test    edi, edi
0x1002f643  js      loc_1002F71F
0x1002f649  push    2; dwCoInit
0x1002f64b  push    esi; pvReserved
0x1002f64c  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x1002f652  lea     eax, [ebp+ppv]
0x1002f658  mov     [ebp+ppv], esi
0x1002f65e  push    eax; ppv
0x1002f65f  push    offset _IID_IFilterMapper2; riid
0x1002f664  push    1; dwClsContext
0x1002f666  push    esi; pUnkOuter
0x1002f667  push    offset _CLSID_FilterMapper2; rclsid
0x1002f66c  mov     [ebp+var_314], esi
0x1002f672  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1002f678  mov     edi, eax
0x1002f67a  test    edi, edi
0x1002f67c  jns     short loc_1002F69E
0x1002f67e  lea     eax, [ebp+var_314]
0x1002f684  push    eax; ppv
0x1002f685  push    offset _IID_IFilterMapper; riid
0x1002f68a  push    1; dwClsContext
0x1002f68c  push    esi; pUnkOuter
0x1002f68d  push    offset _CLSID_FilterMapper; rclsid
0x1002f692  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1002f698  mov     edi, eax
0x1002f69a  test    edi, edi
0x1002f69c  js      short loc_1002F6FC
0x1002f69e  imul    eax, esi, 14h
0x1002f6a1  mov     ecx, dword_1003D010[eax]
0x1002f6a7  test    ecx, ecx
0x1002f6a9  jz      short loc_1002F6CA
0x1002f6ab  mov     edx, [ebp+ppv]
0x1002f6b1  push    ebx
0x1002f6b2  test    edx, edx
0x1002f6b4  jz      short loc_1002F6BD
0x1002f6b6  call    _AMovieSetupRegisterFilter2@12; AMovieSetupRegisterFilter2(x,x,x)
0x1002f6bb  jmp     short loc_1002F6C8
0x1002f6bd  mov     edx, [ebp+var_314]
0x1002f6c3  call    _AMovieSetupRegisterFilter@12; AMovieSetupRegisterFilter(x,x,x)
0x1002f6c8  mov     edi, eax
0x1002f6ca  test    edi, edi
0x1002f6cc  js      short loc_1002F6D4
0x1002f6ce  inc     esi
0x1002f6cf  cmp     esi, 8
0x1002f6d2  jl      short loc_1002F69E
0x1002f6d4  mov     ecx, [ebp+ppv]
0x1002f6da  test    ecx, ecx
0x1002f6dc  jz      short loc_1002F6E6
0x1002f6de  mov     eax, [ecx]
0x1002f6e0  push    ecx
0x1002f6e1  mov     esi, [eax+8]
0x1002f6e4  jmp     short loc_1002F6F2
0x1002f6e6  mov     eax, [ebp+var_314]
0x1002f6ec  push    eax
0x1002f6ed  mov     ecx, [eax]
0x1002f6ef  mov     esi, [ecx+8]
0x1002f6f2  mov     ecx, esi; this
0x1002f6f4  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002f6fa  call    esi
0x1002f6fc  call    ds:__imp__CoFreeUnusedLibraries@0; CoFreeUnusedLibraries()
0x1002f702  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x1002f708  test    edi, edi
0x1002f70a  js      short loc_1002F71F
0x1002f70c  test    ebx, ebx
0x1002f70e  jnz     short loc_1002F71F
0x1002f710  xor     edx, edx
0x1002f712  lea     ecx, [ebp+WideCharStr]
0x1002f718  call    _RegisterAllServers@8; RegisterAllServers(x,x)
0x1002f71d  mov     edi, eax
0x1002f71f  mov     eax, edi
0x1002f721  pop     esi
0x1002f722  mov     ecx, [ebp+var_4]
0x1002f725  pop     edi
0x1002f726  xor     ecx, ebp; StackCookie
0x1002f728  pop     ebx
0x1002f729  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002f72e  leave
0x1002f72f  retn
```
