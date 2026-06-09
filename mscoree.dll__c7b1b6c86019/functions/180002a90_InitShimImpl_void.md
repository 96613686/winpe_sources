# InitShimImpl(void)

- ea: `0x180002a90`
- end: `0x180002d8e`
- name: `?InitShimImpl@@YAXXZ`
- size: `766`
- prototype: `void(void)`
- caller_count: `36`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001010`
- `0x180001140`
- `0x180001280`
- `0x1800013b0`
- `0x1800014c0`
- `0x180001630`
- `0x180001740`
- `0x1800018c0`
- `0x180001a90`
- `0x180001c10`
- `0x180006370`
- `0x180006530`
- `0x1800066d0`
- `0x180006900`
- `0x180006a00`
- `0x180006bb0`
- `0x180006ed0`
- `0x180006ff0`
- `0x180007110`
- `0x1800071c0`
- `0x180007200`
- `0x180007480`
- `0x180007580`
- `0x1800076b0`
- `0x1800077c0`
- `0x1800078c0`
- `0x1800079f8`
- `0x180007b40`
- `0x180007c30`
- `0x180007d80`
- `0x180007ea0`
- `0x180007fa0`
- `0x1800080a0`
- `0x1800081b0`
- `0x180008370`
- `0x180008c60`

## callees

- `0x180002710`
- `0x180002a90`
- `0x180002f30`
- `0x180003070`
- `0x180003840`
- `0x180004660`
- `0x180008a2c`
- `0x18000c1a8`
- `0x180041ac0`
- `0x180045020`
- `0x180045030`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002bf3`
- `KERNEL32!EnterCriticalSection` at `0x180002cef`
- `KERNEL32!EnterCriticalSection` at `0x180002bf3`
- `KERNEL32!EnterCriticalSection` at `0x180002cef`
- `KERNEL32!LeaveCriticalSection` at `0x180002c67`
- `KERNEL32!LeaveCriticalSection` at `0x180002d06`
- `KERNEL32!LeaveCriticalSection` at `0x180002c67`
- `KERNEL32!LeaveCriticalSection` at `0x180002d06`
- `KERNEL32!GetProcAddress` at `0x180002b94`
- `KERNEL32!GetProcAddress` at `0x180002ba7`
- `KERNEL32!GetProcAddress` at `0x180002bba`
- `KERNEL32!GetProcAddress` at `0x180002bde`
- `KERNEL32!GetProcAddress` at `0x180002b94`
- `KERNEL32!GetProcAddress` at `0x180002ba7`
- `KERNEL32!GetProcAddress` at `0x180002bba`
- `KERNEL32!GetProcAddress` at `0x180002bde`
- `KERNEL32!FreeLibrary` at `0x180002ce2`
- `KERNEL32!FreeLibrary` at `0x180002d3e`
- `KERNEL32!FreeLibrary` at `0x180002ce2`
- `KERNEL32!FreeLibrary` at `0x180002d3e`
- `KERNEL32!FindFirstFileW` at `0x180002b27`
- `KERNEL32!FindFirstFileW` at `0x180002b27`
- `KERNEL32!FindClose` at `0x180002b5a`
- `KERNEL32!FindClose` at `0x180002b5a`

## string_xrefs

- `0x180002af4`: `mscoreei.dll`
- `0x180002b68`: `mscoreei.dll`
- `0x180002d6e`: `mscoreei.dll`
- `0x180002bcc`: `OnShimDllMainCalled`
- `0x180002c3c`: `mscoreei.dll`
- `0x180002d56`: `mscoreei.dll`

## pseudocode

```c
void __fastcall InitShimImpl(__int64 a1, int (*a2)(unsigned __int16 *, void *))
{
  int LatestVersion; // eax
  wchar_t *v3; // rbx
  int v4; // esi
  HANDLE FirstFileW; // rax
  __int64 v6; // r8
  HMODULE v7; // rdi
  FARPROC ProcAddress; // rbp
  FARPROC v9; // r12
  FARPROC v10; // r14
  FARPROC v11; // rax
  int (*v12)(void *, unsigned int, void *); // r15
  HMODULE hModule; // [rsp+20h] [rbp-4B8h] BYREF
  wchar_t *v14; // [rsp+28h] [rbp-4B0h] BYREF
  int v15; // [rsp+30h] [rbp-4A8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-498h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp-248h] BYREF

  v14 = 0;
  v15 = 0;
  LatestVersion = FindLatestVersion(&v14, a2);
  v3 = v14;
  if ( v14 )
  {
    v4 = 1;
    v15 = 1;
  }
  else
  {
    v4 = v15;
  }
  if ( LatestVersion < 0
    || (hModule = 0, (int)GetShimDllPathName((wchar_t *)L"mscoreei.dll", v14, FileName) < 0)
    || (memset_thunk_772440563353939046(&FindFileData, 0, 0x250u),
        FirstFileW = FindFirstFileW(FileName, &FindFileData),
        FirstFileW == (HANDLE)-1LL) )
  {
    UpdateShimImplStatus(3, L"mscoreei.dll");
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v14);
    return;
  }
  FindClose(FirstFileW);
  if ( (int)LoadLibraryShim_0((wchar_t *)L"mscoreei.dll", v3, v6, &hModule) >= 0 )
  {
    v7 = hModule;
    if ( hModule )
    {
      ProcAddress = GetProcAddress(hModule, "RegisterShimImplCallback");
      v9 = GetProcAddress(v7, "RegisterShimImplCleanupCallback");
      v10 = GetProcAddress(v7, "SetShellShimInstance");
      if ( ProcAddress || v9 )
      {
        v11 = GetProcAddress(v7, "OnShimDllMainCalled");
        LODWORD(hModule) = 0;
        v12 = (int (*)(void *, unsigned int, void *))v11;
        EnterCriticalSection(&g_csInitShim);
        if ( (_DWORD)g_shimImplStatus )
        {
          LODWORD(hModule) = 1;
        }
        else
        {
          if ( v10 )
            ((void (__fastcall *)(HINSTANCE))v10)(g_hThisInst);
          if ( ProcAddress )
            ((void (__fastcall *)(void (*)(void), void (__fastcall *)(unsigned __int16 *)))ProcAddress)(
              OnShimImplCleanup,
              OnShimImplSetGlobalVersion);
          else
            ((void (__fastcall *)(void (*)(void)))v9)(OnShimImplCleanup);
          wcscpy_s(g_wszShimImplDllPath, 0x104u, FileName);
          g_lpOnShimDllMainCalledProc = v12;
          g_hShimImplInst = v7;
          LODWORD(g_shimImplStatus) = 2;
        }
        LeaveCriticalSection(&g_csInitShim);
        if ( (_DWORD)hModule )
          FreeLibrary(v7);
        goto LABEL_17;
      }
      FreeLibrary(v7);
    }
  }
  EnterCriticalSection(&g_csInitShim);
  if ( !(_DWORD)g_shimImplStatus )
  {
    wcscpy_s(g_wszShimImplDllPath, 0x104u, FileName);
    LODWORD(g_shimImplStatus) = 1;
  }
  LeaveCriticalSection(&g_csInitShim);
LABEL_17:
  if ( v4 )
    operator delete(v3);
}

```

## disassembly

```asm
0x180002a90  push    rbx
0x180002a92  push    rsi
0x180002a93  push    r13
0x180002a95  sub     rsp, 4C0h
0x180002a9c  mov     rax, cs:__security_cookie
0x180002aa3  xor     rax, rsp
0x180002aa6  mov     [rsp+4D8h+var_38], rax
0x180002aae  xor     r13d, r13d
0x180002ab1  lea     rcx, [rsp+4D8h+var_4B0]; unsigned __int16 **
0x180002ab6  mov     [rsp+4D8h+var_4B0], r13
0x180002abb  mov     [rsp+4D8h+var_4A8], r13d
0x180002ac0  call    ?FindLatestVersion@@YAJPEAPEAGP6AHPEAGPEAX@Z@Z; FindLatestVersion(ushort * *,int (*)(ushort *,void *))
0x180002ac5  mov     rbx, [rsp+4D8h+var_4B0]
0x180002aca  test    rbx, rbx
0x180002acd  jz      loc_180002D11
0x180002ad3  mov     esi, 1
0x180002ad8  mov     [rsp+4D8h+var_4A8], esi
0x180002adc  test    eax, eax
0x180002ade  js      loc_180002D6E
0x180002ae4  lea     r8, [rsp+4D8h+FileName]; void *
0x180002aec  mov     [rsp+4D8h+hModule], r13
0x180002af1  mov     rdx, rbx; wchar_t *
0x180002af4  lea     rcx, aMscoreeiDll; "mscoreei.dll"
0x180002afb  call    GetShimDllPathName
0x180002b00  test    eax, eax
0x180002b02  js      loc_180002D6E
0x180002b08  xor     edx, edx; Val
0x180002b0a  lea     rcx, [rsp+4D8h+FindFileData]; void *
0x180002b0f  mov     r8d, 250h; Size
0x180002b15  call    memset$thunk$772440563353939046
0x180002b1a  lea     rdx, [rsp+4D8h+FindFileData]; lpFindFileData
0x180002b1f  lea     rcx, [rsp+4D8h+FileName]; lpFileName
0x180002b27  call    cs:__imp_FindFirstFileW
0x180002b2d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002b31  jz      loc_180002D6E
0x180002b37  mov     [rsp+4D8h+arg_0], rbp
0x180002b3f  mov     rcx, rax; hFindFile
0x180002b42  mov     [rsp+4D8h+arg_8], rdi
0x180002b4a  mov     [rsp+4D8h+arg_10], r12
0x180002b52  mov     [rsp+4D8h+var_20], r14
0x180002b5a  call    cs:__imp_FindClose
0x180002b60  lea     r9, [rsp+4D8h+hModule]
0x180002b65  mov     rdx, rbx; wchar_t *
0x180002b68  lea     rcx, aMscoreeiDll; "mscoreei.dll"
0x180002b6f  call    LoadLibraryShim_0
0x180002b74  test    eax, eax
0x180002b76  js      loc_180002CE8
0x180002b7c  mov     rdi, [rsp+4D8h+hModule]
0x180002b81  test    rdi, rdi
0x180002b84  jz      loc_180002CE8
0x180002b8a  lea     rdx, aRegistershimim; "RegisterShimImplCallback"
0x180002b91  mov     rcx, rdi; hModule
0x180002b94  call    cs:__imp_GetProcAddress
0x180002b9a  lea     rdx, aRegistershimim_0; "RegisterShimImplCleanupCallback"
0x180002ba1  mov     rcx, rdi; hModule
0x180002ba4  mov     rbp, rax
0x180002ba7  call    cs:__imp_GetProcAddress
0x180002bad  lea     rdx, aSetshellshimin; "SetShellShimInstance"
0x180002bb4  mov     rcx, rdi; hModule
0x180002bb7  mov     r12, rax
0x180002bba  call    cs:__imp_GetProcAddress
0x180002bc0  mov     r14, rax
0x180002bc3  test    rbp, rbp
0x180002bc6  jz      loc_180002CD6
0x180002bcc  lea     rdx, aOnshimdllmainc; "OnShimDllMainCalled"
0x180002bd3  mov     [rsp+4D8h+var_28], r15
0x180002bdb  mov     rcx, rdi; hModule
0x180002bde  call    cs:__imp_GetProcAddress
0x180002be4  lea     rcx, ?g_csInitShim@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002beb  mov     dword ptr [rsp+4D8h+hModule], r13d
0x180002bf0  mov     r15, rax
0x180002bf3  call    cs:__imp_EnterCriticalSection
0x180002bf9  mov     ecx, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180002bff  test    ecx, ecx
0x180002c01  jnz     loc_180002D1A
0x180002c07  test    r14, r14
0x180002c0a  jnz     loc_180002D27
0x180002c10  lea     rcx, ?OnShimImplCleanup@@YAXXZ; OnShimImplCleanup(void)
0x180002c17  test    rbp, rbp
0x180002c1a  jz      loc_180002CC9
0x180002c20  lea     rdx, ?OnShimImplSetGlobalVersion@@YAXPEAG@Z; OnShimImplSetGlobalVersion(ushort *)
0x180002c27  mov     rax, rbp
0x180002c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2f  lea     r8, [rsp+4D8h+FileName]; Source
0x180002c37  mov     edx, 104h; SizeInWords
0x180002c3c  lea     rcx, ?g_wszShimImplDllPath@@3PAGA; "mscoreei.dll"
0x180002c43  call    wcscpy_s
0x180002c48  mov     cs:?g_lpOnShimDllMainCalledProc@@3R6AHPEAXK0@ZEA, r15; int (*g_lpOnShimDllMainCalledProc)(void *,ulong,void *)
0x180002c4f  mov     cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hShimImplInst
0x180002c56  mov     cs:?g_shimImplStatus@@3W4ShimImplStatus@@C, 2; ShimImplStatus volatile g_shimImplStatus
0x180002c60  lea     rcx, ?g_csInitShim@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002c67  call    cs:__imp_LeaveCriticalSection
0x180002c6d  mov     eax, dword ptr [rsp+4D8h+hModule]
0x180002c71  mov     r15, [rsp+4D8h+var_28]
0x180002c79  test    eax, eax
0x180002c7b  jnz     loc_180002D3B
0x180002c81  test    esi, esi
0x180002c83  jz      short loc_180002C8D
0x180002c85  mov     rcx, rbx; void *
0x180002c88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c8d  mov     r12, [rsp+4D8h+arg_10]
0x180002c95  mov     rdi, [rsp+4D8h+arg_8]
0x180002c9d  mov     rbp, [rsp+4D8h+arg_0]
0x180002ca5  mov     r14, [rsp+4D8h+var_20]
0x180002cad  mov     rcx, [rsp+4D8h+var_38]
0x180002cb5  xor     rcx, rsp; StackCookie
0x180002cb8  call    __security_check_cookie
0x180002cbd  add     rsp, 4C0h
0x180002cc4  pop     r13
0x180002cc6  pop     rsi
0x180002cc7  pop     rbx
0x180002cc8  retn
0x180002cc9  mov     rax, r12
0x180002ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd1  jmp     loc_180002C2F
0x180002cd6  test    r12, r12
0x180002cd9  jnz     loc_180002BCC
0x180002cdf  mov     rcx, rdi; hLibModule
0x180002ce2  call    cs:__imp_FreeLibrary
0x180002ce8  lea     rcx, ?g_csInitShim@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002cef  call    cs:__imp_EnterCriticalSection
0x180002cf5  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180002cfb  test    eax, eax
0x180002cfd  jz      short loc_180002D49
0x180002cff  lea     rcx, ?g_csInitShim@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002d06  call    cs:__imp_LeaveCriticalSection
0x180002d0c  jmp     loc_180002C81
0x180002d11  mov     esi, [rsp+4D8h+var_4A8]
0x180002d15  jmp     loc_180002ADC
0x180002d1a  mov     dword ptr [rsp+4D8h+hModule], 1
0x180002d22  jmp     loc_180002C60
0x180002d27  mov     rcx, cs:?g_hThisInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hThisInst
0x180002d2e  mov     rax, r14
0x180002d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d36  jmp     loc_180002C10
0x180002d3b  mov     rcx, rdi; hLibModule
0x180002d3e  call    cs:__imp_FreeLibrary
0x180002d44  jmp     loc_180002C81
0x180002d49  lea     r8, [rsp+4D8h+FileName]; Source
0x180002d51  mov     edx, 104h; SizeInWords
0x180002d56  lea     rcx, ?g_wszShimImplDllPath@@3PAGA; "mscoreei.dll"
0x180002d5d  call    wcscpy_s
0x180002d62  mov     cs:?g_shimImplStatus@@3W4ShimImplStatus@@C, 1; ShimImplStatus volatile g_shimImplStatus
0x180002d6c  jmp     short loc_180002CFF
0x180002d6e  lea     rdx, aMscoreeiDll; "mscoreei.dll"
0x180002d75  mov     ecx, 3
0x180002d7a  call    ?UpdateShimImplStatus@@YAXW4ShimImplStatus@@PEAG@Z; UpdateShimImplStatus(ShimImplStatus,ushort *)
0x180002d7f  lea     rcx, [rsp+4D8h+var_4B0]
0x180002d84  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180002d89  jmp     loc_180002CAD
```
