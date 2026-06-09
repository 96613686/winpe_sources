# AMovieDllRegisterServer2

- ea: `0x1800028b0`
- end: `0x180002ad7`
- name: `AMovieDllRegisterServer2`
- size: `551`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001ee0`
- `0x1800020a0`

## callees

- `0x180001460`
- `0x1800028b0`
- `0x180002ae0`
- `0x180002ba4`
- `0x180002eb4`
- `0x180006cb4`
- `0x18001f010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180002960`
- `KERNEL32!MultiByteToWideChar` at `0x180002960`
- `KERNEL32!GetLastError` at `0x1800028f7`
- `KERNEL32!GetLastError` at `0x1800028f7`
- `KERNEL32!GetModuleFileNameA` at `0x1800028ed`
- `KERNEL32!GetModuleFileNameA` at `0x1800028ed`
- `ole32!CoUninitialize` at `0x180002a7f`
- `ole32!CoUninitialize` at `0x180002a7f`
- `ole32!CoFreeUnusedLibraries` at `0x180002a79`
- `ole32!CoFreeUnusedLibraries` at `0x180002a79`
- `ole32!CoCreateInstance` at `0x1800029ed`
- `ole32!CoCreateInstance` at `0x180002a17`
- `ole32!CoCreateInstance` at `0x1800029ed`
- `ole32!CoCreateInstance` at `0x180002a17`
- `ole32!CoInitializeEx` at `0x1800029b7`
- `ole32!CoInitializeEx` at `0x1800029b7`

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
        if ( (int)v5 >= 5 )
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
        while ( (int)v8 < 5 );
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
        while ( (int)v12 < 5 );
      }
    }
    return (unsigned int)Instance;
  }
  return result;
}

```

## disassembly

```asm
0x1800028b0  push    rbp
0x1800028b2  push    rbx
0x1800028b3  push    rsi
0x1800028b4  push    rdi
0x1800028b5  push    r12
0x1800028b7  lea     rbp, [rsp-280h]
0x1800028bf  sub     rsp, 380h
0x1800028c6  mov     rax, cs:__security_cookie
0x1800028cd  xor     rax, rsp
0x1800028d0  mov     [rbp+2A0h+var_30], rax
0x1800028d7  mov     esi, ecx
0x1800028d9  lea     rdx, [rsp+3A0h+Filename]; lpFilename
0x1800028de  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x1800028e5  mov     ebx, 104h
0x1800028ea  mov     r8d, ebx; nSize
0x1800028ed  call    cs:__imp_GetModuleFileNameA
0x1800028f3  test    eax, eax
0x1800028f5  jnz     short loc_180002907
0x1800028f7  call    cs:__imp_GetLastError
0x1800028fd  or      eax, 80070000h
0x180002902  jmp     loc_180002ABA
0x180002907  mov     r8, rbx
0x18000290a  lea     rax, [rsp+3A0h+Filename]
0x18000290f  cmp     byte ptr [rax], 0
0x180002912  jz      short loc_18000291D
0x180002914  inc     rax
0x180002917  sub     r8, 1
0x18000291b  jnz     short loc_18000290F
0x18000291d  mov     rax, r8
0x180002920  mov     rdx, rbx
0x180002923  neg     rax
0x180002926  mov     rcx, r8
0x180002929  sbb     eax, eax
0x18000292b  sub     rdx, r8
0x18000292e  not     eax
0x180002930  and     eax, 80070057h
0x180002935  neg     rcx
0x180002938  sbb     r9, r9
0x18000293b  and     r9, rdx
0x18000293e  test    r8, r8
0x180002941  jz      loc_180002ABA
0x180002947  lea     rax, [rbp+2A0h+WideCharStr]
0x18000294b  mov     [rsp+3A0h+cchWideChar], ebx; cchWideChar
0x18000294f  inc     r9d; cbMultiByte
0x180002952  mov     [rsp+3A0h+lpWideCharStr], rax; lpWideCharStr
0x180002957  lea     r8, [rsp+3A0h+Filename]; lpMultiByteStr
0x18000295c  xor     edx, edx; dwFlags
0x18000295e  xor     ecx, ecx; CodePage
0x180002960  call    cs:__imp_MultiByteToWideChar
0x180002966  lea     r12, ?g_Templates@@3PAVCFactoryTemplate@@A; CFactoryTemplate near * g_Templates
0x18000296d  test    esi, esi
0x18000296f  jz      short loc_1800029B0
0x180002971  xor     edi, edi
0x180002973  lea     rdx, [rdi+rdi*4]
0x180002977  mov     rax, [r12+rdx*8+8]
0x18000297c  lea     r8, [rbp+2A0h+WideCharStr]
0x180002980  mov     rdx, [r12+rdx*8]
0x180002984  lea     rcx, [rsp+3A0h+var_360]
0x180002989  movups  xmm0, xmmword ptr [rax]
0x18000298c  movdqu  xmmword ptr [rsp+3A0h+var_360], xmm0
0x180002992  call    AMovieSetupRegisterServer
0x180002997  mov     ebx, eax
0x180002999  test    eax, eax
0x18000299b  js      loc_180002AB8
0x1800029a1  inc     edi
0x1800029a3  cmp     edi, 5
0x1800029a6  jl      short loc_180002973
0x1800029a8  test    eax, eax
0x1800029aa  js      loc_180002AB8
0x1800029b0  mov     edx, 2; dwCoInit
0x1800029b5  xor     ecx, ecx; pvReserved
0x1800029b7  call    cs:__imp_CoInitializeEx
0x1800029bd  xor     edx, edx; pUnkOuter
0x1800029bf  mov     [rsp+3A0h+ppv], 0
0x1800029c8  lea     rax, [rsp+3A0h+ppv]
0x1800029cd  mov     [rsp+3A0h+var_360], 0
0x1800029d6  lea     r9, IID_IFilterMapper2; riid
0x1800029dd  mov     [rsp+3A0h+lpWideCharStr], rax; ppv
0x1800029e2  lea     rcx, CLSID_FilterMapper2; rclsid
0x1800029e9  lea     r8d, [rdx+1]; dwClsContext
0x1800029ed  call    cs:__imp_CoCreateInstance
0x1800029f3  mov     ebx, eax
0x1800029f5  test    eax, eax
0x1800029f7  jns     short loc_180002A23
0x1800029f9  xor     edx, edx; pUnkOuter
0x1800029fb  lea     rax, [rsp+3A0h+var_360]
0x180002a00  lea     r9, IID_IFilterMapper; riid
0x180002a07  mov     [rsp+3A0h+lpWideCharStr], rax; ppv
0x180002a0c  lea     rcx, CLSID_FilterMapper; rclsid
0x180002a13  lea     r8d, [rdx+1]; dwClsContext
0x180002a17  call    cs:__imp_CoCreateInstance
0x180002a1d  mov     ebx, eax
0x180002a1f  test    eax, eax
0x180002a21  js      short loc_180002A79
0x180002a23  xor     edi, edi
0x180002a25  lea     rcx, [rdi+rdi*4]
0x180002a29  mov     rcx, [r12+rcx*8+20h]
0x180002a2e  test    rcx, rcx
0x180002a31  jz      short loc_180002A53
0x180002a33  mov     rdx, [rsp+3A0h+ppv]
0x180002a38  mov     r8d, esi
0x180002a3b  test    rdx, rdx
0x180002a3e  jz      short loc_180002A47
0x180002a40  call    AMovieSetupRegisterFilter2
0x180002a45  jmp     short loc_180002A51
0x180002a47  mov     rdx, [rsp+3A0h+var_360]
0x180002a4c  call    AMovieSetupRegisterFilter
0x180002a51  mov     ebx, eax
0x180002a53  test    ebx, ebx
0x180002a55  js      short loc_180002A5E
0x180002a57  inc     edi
0x180002a59  cmp     edi, 5
0x180002a5c  jl      short loc_180002A25
0x180002a5e  mov     rcx, [rsp+3A0h+ppv]
0x180002a63  test    rcx, rcx
0x180002a66  jnz     short loc_180002A6D
0x180002a68  mov     rcx, [rsp+3A0h+var_360]
0x180002a6d  mov     rax, [rcx]
0x180002a70  mov     rax, [rax+10h]
0x180002a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a79  call    cs:__imp_CoFreeUnusedLibraries
0x180002a7f  call    cs:__imp_CoUninitialize
0x180002a85  test    ebx, ebx
0x180002a87  js      short loc_180002AB8
0x180002a89  test    esi, esi
0x180002a8b  jnz     short loc_180002AB8
0x180002a8d  xor     edi, edi
0x180002a8f  lea     rax, [rdi+rdi*4]
0x180002a93  mov     rax, [r12+rax*8+8]
0x180002a98  lea     rcx, [rsp+3A0h+var_360]
0x180002a9d  movups  xmm0, xmmword ptr [rax]
0x180002aa0  movdqu  xmmword ptr [rsp+3A0h+var_360], xmm0
0x180002aa6  call    AMovieSetupUnregisterServer
0x180002aab  mov     ebx, eax
0x180002aad  test    eax, eax
0x180002aaf  js      short loc_180002AB8
0x180002ab1  inc     edi
0x180002ab3  cmp     edi, 5
0x180002ab6  jl      short loc_180002A8F
0x180002ab8  mov     eax, ebx
0x180002aba  mov     rcx, [rbp+2A0h+var_30]
0x180002ac1  xor     rcx, rsp; StackCookie
0x180002ac4  call    __security_check_cookie
0x180002ac9  add     rsp, 380h
0x180002ad0  pop     r12
0x180002ad2  pop     rdi
0x180002ad3  pop     rsi
0x180002ad4  pop     rbx
0x180002ad5  pop     rbp
0x180002ad6  retn
```
