# CDisplayInfo::CDisplayInfoInternal::enumMonitorCallback(HMONITOR__ *,HDC__ *,tagRECT *)

- ea: `0x1800217f4`
- end: `0x180021b5c`
- name: `?enumMonitorCallback@CDisplayInfoInternal@CDisplayInfo@@AEAAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@@Z`
- size: `872`
- prototype: `int(CDisplayInfo::CDisplayInfoInternal *__hidden this, HMONITOR, HDC, struct tagRECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021b70`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x18001daf0`
- `0x18001dcc8`
- `0x1800209bc`
- `0x1800210d0`
- `0x1800217f4`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002184d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800218d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002184d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800218d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800218f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002196d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800218f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002196d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b42`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateDCW` at `0x18002198d`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateDCW` at `0x18002198d`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800219b3`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800219cc`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800219e0`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800219f2`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800219b3`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800219cc`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800219e0`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800219f2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x180021869`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x180021869`

## string_xrefs

- `0x180021846`: `gdi32.dll`
- `0x1800218c9`: `api-ms-win-shcore-scaling-l1-1-1.dll`
- `0x180021963`: `CreateDCW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDisplayInfo::CDisplayInfoInternal::enumMonitorCallback(
        CDisplayInfo::CDisplayInfoInternal *this,
        HMONITOR a2,
        HDC a3,
        struct tagRECT *a4)
{
  HMODULE Library; // rax
  DisplayInfo::CDisplayInfoInternal *v7; // rcx
  FARPROC ProcAddress; // rax
  int (__fastcall *v9)(HMONITOR, __int64, char *, char *); // rdi
  int *v10; // rsi
  int *v11; // rdi
  HMODULE v12; // r8
  HDC DCW; // rax
  int v14; // eax
  int v15; // eax
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  signed int LastError; // eax
  int v21; // edx
  unsigned int v22; // r8d
  signed int v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  signed int v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  signed int v29; // eax
  int v30; // edx
  unsigned int v31; // r8d
  const int *v32; // [rsp+30h] [rbp-79h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-71h]
  void **v34; // [rsp+40h] [rbp-69h] BYREF
  HDC hdc; // [rsp+48h] [rbp-61h]
  const int *v36; // [rsp+50h] [rbp-59h] BYREF
  HMODULE v37; // [rsp+58h] [rbp-51h]
  tagMONITORINFO mi; // [rsp+60h] [rbp-49h] BYREF
  WCHAR pwszDevice[36]; // [rsp+88h] [rbp-21h] BYREF

  memset_0(&mi.rcMonitor, 0, 0x64u);
  mi.cbSize = 104;
  v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = LoadLibraryExW(L"gdi32.dll", 0, 0x800u);
  if ( !GetMonitorInfoW(a2, &mi) )
  {
    v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v32) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v21, v22);
      __debugbreak();
    }
    return 1;
  }
  if ( (mi.dwFlags & 1) == 0 )
  {
    v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( !hModule || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v32) )
      return 1;
    v23 = GetLastError();
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
    goto LABEL_49;
  }
  Library = LoadLibraryExW(L"api-ms-win-shcore-scaling-l1-1-1.dll", 0, 0x800u);
  v36 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v37 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetDpiForMonitor");
    v9 = (int (__fastcall *)(HMONITOR, __int64, char *, char *))ProcAddress;
    if ( ProcAddress )
    {
      if ( ((int (__fastcall *)(HMONITOR, _QWORD, CDisplayInfo::CDisplayInfoInternal *, char *))ProcAddress)(
             a2,
             0,
             this,
             (char *)this + 4) < 0 )
      {
        *((_DWORD *)this + 1) = -1;
        *(_DWORD *)this = -1;
      }
      if ( v9(a2, 2, (char *)this + 8, (char *)this + 12) < 0 )
      {
        *((_DWORD *)this + 3) = -1;
        *((_DWORD *)this + 2) = -1;
      }
    }
  }
  v10 = (int *)((char *)this + 20);
  v11 = (int *)((char *)this + 16);
  DisplayInfo::CDisplayInfoInternal::GetActualResolution(v7, (int *)this + 4, (int *)this + 5);
  v12 = hModule;
  if ( hModule )
  {
    if ( GetProcAddress(hModule, "CreateDCW") )
    {
      DCW = CreateDCW(L"DISPLAY", pwszDevice, 0, 0);
      v34 = &Microsoft::WRL::Wrappers::HandleT<DisplayContextTraits>::`vftable';
      hdc = DCW;
      if ( DCW )
      {
        if ( *v11 == -1 )
        {
          *v11 = GetDeviceCaps(DCW, 8);
          DCW = hdc;
        }
        if ( *v10 == -1 )
        {
          *v10 = GetDeviceCaps(DCW, 10);
          DCW = hdc;
        }
        *((_DWORD *)this + 6) = GetDeviceCaps(DCW, 4);
        *((_DWORD *)this + 7) = GetDeviceCaps(hdc, 6);
        DCW = hdc;
      }
      v34 = &Microsoft::WRL::Wrappers::HandleT<DisplayContextTraits>::`vftable';
      if ( DCW )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<DisplayContextTraits>::InternalClose(&v34) )
        {
LABEL_49:
          v26 = GetLastError();
          if ( v26 > 0 )
            v26 = (unsigned __int16)v26 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
LABEL_52:
          v29 = GetLastError();
          if ( v29 > 0 )
            v29 = (unsigned __int16)v29 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v31);
          JUMPOUT(0x180021B5BLL);
        }
      }
    }
    v12 = hModule;
  }
  if ( *((_DWORD *)this + 6) == -1 || *((_DWORD *)this + 7) == -1 )
  {
    if ( *v11 != -1 )
    {
      v14 = *((_DWORD *)this + 2);
      if ( v14 != -1 )
        *((_DWORD *)this + 6) = 254 * *v11 / (unsigned int)(10 * v14);
    }
    if ( *v10 != -1 )
    {
      v15 = *((_DWORD *)this + 3);
      if ( v15 != -1 )
        *((_DWORD *)this + 7) = 254 * *v10 / (unsigned int)(10 * v15);
    }
  }
  v36 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v37 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v36) )
      goto LABEL_52;
    v37 = 0;
    v12 = hModule;
  }
  v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v12 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v32) )
  {
    v17 = GetLastError();
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
    __debugbreak();
  }
  return 1;
}

```

## disassembly

```asm
0x1800217f4  mov     [rsp-8+arg_10], rbx
0x1800217f9  mov     [rsp-8+arg_18], rsi
0x1800217fe  push    rbp
0x1800217ff  push    rdi
0x180021800  push    r13
0x180021802  push    r14
0x180021804  push    r15
0x180021806  lea     rbp, [rsp-37h]
0x18002180b  sub     rsp, 0E0h
0x180021812  mov     rax, cs:__security_cookie
0x180021819  xor     rax, rsp
0x18002181c  mov     [rbp+57h+var_30], rax
0x180021820  mov     r15, rdx
0x180021823  mov     rbx, rcx
0x180021826  xor     edx, edx; Val
0x180021828  lea     r8d, [rdx+64h]; Size
0x18002182c  lea     rcx, [rbp+57h+mi.rcMonitor]; void *
0x180021830  call    memset_0
0x180021835  mov     [rbp+57h+mi.cbSize], 68h ; 'h'
0x18002183c  mov     esi, 800h
0x180021841  mov     r8d, esi; dwFlags
0x180021844  xor     edx, edx; hFile
0x180021846  lea     rcx, aGdi32Dll; "gdi32.dll"
0x18002184d  call    cs:__imp_LoadLibraryExW
0x180021853  lea     rdi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18002185a  mov     [rbp+57h+var_D0], rdi
0x18002185e  mov     [rbp+57h+hModule], rax
0x180021862  lea     rdx, [rbp+57h+mi]; lpmi
0x180021866  mov     rcx, r15; hMonitor
0x180021869  call    cs:__imp_GetMonitorInfoW
0x18002186f  test    eax, eax
0x180021871  jnz     short loc_180021898
0x180021873  mov     [rbp+57h+var_D0], rdi
0x180021877  cmp     [rbp+57h+hModule], 0
0x18002187c  jz      loc_180021AAC
0x180021882  lea     rcx, [rbp+57h+var_D0]
0x180021886  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18002188b  test    al, al
0x18002188d  jz      loc_180021AF3
0x180021893  jmp     loc_180021AAC
0x180021898  mov     eax, [rbp+57h+mi.dwFlags]
0x18002189b  test    al, 1
0x18002189d  jnz     short loc_1800218C4
0x18002189f  mov     [rbp+57h+var_D0], rdi
0x1800218a3  cmp     [rbp+57h+hModule], 0
0x1800218a8  jz      loc_180021AAC
0x1800218ae  lea     rcx, [rbp+57h+var_D0]
0x1800218b2  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800218b7  test    al, al
0x1800218b9  jz      loc_180021B0D
0x1800218bf  jmp     loc_180021AAC
0x1800218c4  mov     r8d, esi; dwFlags
0x1800218c7  xor     edx, edx; hFile
0x1800218c9  lea     rcx, aApiMsWinShcore_0; "api-ms-win-shcore-scaling-l1-1-1.dll"
0x1800218d0  call    cs:__imp_LoadLibraryExW
0x1800218d6  mov     [rbp+57h+var_B0], rdi
0x1800218da  mov     [rbp+57h+var_A8], rax
0x1800218de  or      r13d, 0FFFFFFFFh
0x1800218e2  test    rax, rax
0x1800218e5  jz      short loc_18002193F
0x1800218e7  lea     rdx, aGetdpiformonit; "GetDpiForMonitor"
0x1800218ee  mov     rcx, rax; hModule
0x1800218f1  call    cs:__imp_GetProcAddress
0x1800218f7  mov     rdi, rax
0x1800218fa  test    rax, rax
0x1800218fd  jz      short loc_18002193F
0x1800218ff  lea     r9, [rbx+4]
0x180021903  mov     r8, rbx
0x180021906  xor     edx, edx
0x180021908  mov     rcx, r15
0x18002190b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021910  test    eax, eax
0x180021912  jns     short loc_18002191B
0x180021914  mov     [rbx+4], r13d
0x180021918  mov     [rbx], r13d
0x18002191b  lea     r9, [rbx+0Ch]
0x18002191f  lea     r8, [rbx+8]
0x180021923  mov     edx, 2
0x180021928  mov     rcx, r15
0x18002192b  mov     rax, rdi
0x18002192e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021933  test    eax, eax
0x180021935  jns     short loc_18002193F
0x180021937  mov     [rbx+0Ch], r13d
0x18002193b  mov     [rbx+8], r13d
0x18002193f  lea     rsi, [rbx+14h]
0x180021943  lea     rdi, [rbx+10h]
0x180021947  mov     r8, rsi; int *
0x18002194a  mov     rdx, rdi; int *
0x18002194d  call    ?GetActualResolution@CDisplayInfoInternal@DisplayInfo@@AEAAXPEAH0@Z; DisplayInfo::CDisplayInfoInternal::GetActualResolution(int *,int *)
0x180021952  or      r14d, 0FFFFFFFFh
0x180021956  mov     r8, [rbp+57h+hModule]
0x18002195a  test    r8, r8
0x18002195d  jz      loc_180021A1D
0x180021963  lea     rdx, aCreatedcw_0; "CreateDCW"
0x18002196a  mov     rcx, r8; hModule
0x18002196d  call    cs:__imp_GetProcAddress
0x180021973  test    rax, rax
0x180021976  jz      loc_180021A19
0x18002197c  xor     r9d, r9d; pdm
0x18002197f  xor     r8d, r8d; pszPort
0x180021982  lea     rdx, [rbp+57h+pwszDevice]; pwszDevice
0x180021986  lea     rcx, pwszDriver; "DISPLAY"
0x18002198d  call    cs:__imp_CreateDCW
0x180021993  lea     r15, ??_7?$HandleT@UDisplayContextTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<DisplayContextTraits>::`vftable'
0x18002199a  mov     [rbp+57h+var_C0], r15
0x18002199e  mov     [rbp+57h+hdc], rax
0x1800219a2  test    rax, rax
0x1800219a5  jz      short loc_1800219FF
0x1800219a7  cmp     [rdi], r14d
0x1800219aa  jnz     short loc_1800219BF
0x1800219ac  lea     edx, [r14+9]; index
0x1800219b0  mov     rcx, rax; hdc
0x1800219b3  call    cs:__imp_GetDeviceCaps
0x1800219b9  mov     [rdi], eax
0x1800219bb  mov     rax, [rbp+57h+hdc]
0x1800219bf  cmp     [rsi], r14d
0x1800219c2  jnz     short loc_1800219D8
0x1800219c4  mov     edx, 0Ah; index
0x1800219c9  mov     rcx, rax; hdc
0x1800219cc  call    cs:__imp_GetDeviceCaps
0x1800219d2  mov     [rsi], eax
0x1800219d4  mov     rax, [rbp+57h+hdc]
0x1800219d8  mov     edx, 4; index
0x1800219dd  mov     rcx, rax; hdc
0x1800219e0  call    cs:__imp_GetDeviceCaps
0x1800219e6  mov     [rbx+18h], eax
0x1800219e9  mov     edx, 6; index
0x1800219ee  mov     rcx, [rbp+57h+hdc]; hdc
0x1800219f2  call    cs:__imp_GetDeviceCaps
0x1800219f8  mov     [rbx+1Ch], eax
0x1800219fb  mov     rax, [rbp+57h+hdc]
0x1800219ff  mov     [rbp+57h+var_C0], r15
0x180021a03  test    rax, rax
0x180021a06  jz      short loc_180021A19
0x180021a08  lea     rcx, [rbp+57h+var_C0]
0x180021a0c  call    ?InternalClose@?$HandleT@UDisplayContextTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<DisplayContextTraits>::InternalClose(void)
0x180021a11  test    al, al
0x180021a13  jz      loc_180021B27
0x180021a19  mov     r8, [rbp+57h+hModule]
0x180021a1d  cmp     [rbx+18h], r14d
0x180021a21  jz      short loc_180021A29
0x180021a23  cmp     [rbx+1Ch], r14d
0x180021a27  jnz     short loc_180021A67
0x180021a29  cmp     [rdi], r14d
0x180021a2c  jz      short loc_180021A48
0x180021a2e  mov     eax, [rbx+8]
0x180021a31  cmp     eax, r13d
0x180021a34  jz      short loc_180021A48
0x180021a36  lea     ecx, [rax+rax*4]
0x180021a39  add     ecx, ecx
0x180021a3b  imul    eax, [rdi], 0FEh
0x180021a41  xor     edx, edx
0x180021a43  div     ecx
0x180021a45  mov     [rbx+18h], eax
0x180021a48  cmp     [rsi], r14d
0x180021a4b  jz      short loc_180021A67
0x180021a4d  mov     eax, [rbx+0Ch]
0x180021a50  cmp     eax, r13d
0x180021a53  jz      short loc_180021A67
0x180021a55  lea     ecx, [rax+rax*4]
0x180021a58  add     ecx, ecx
0x180021a5a  imul    eax, [rsi], 0FEh
0x180021a60  xor     edx, edx
0x180021a62  div     ecx
0x180021a64  mov     [rbx+1Ch], eax
0x180021a67  lea     rbx, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180021a6e  mov     [rbp+57h+var_B0], rbx
0x180021a72  cmp     [rbp+57h+var_A8], 0
0x180021a77  jz      short loc_180021A96
0x180021a79  lea     rcx, [rbp+57h+var_B0]
0x180021a7d  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180021a82  test    al, al
0x180021a84  jz      loc_180021B42
0x180021a8a  mov     [rbp+57h+var_A8], 0
0x180021a92  mov     r8, [rbp+57h+hModule]
0x180021a96  mov     [rbp+57h+var_D0], rbx
0x180021a9a  test    r8, r8
0x180021a9d  jz      short loc_180021AAC
0x180021a9f  lea     rcx, [rbp+57h+var_D0]
0x180021aa3  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180021aa8  test    al, al
0x180021aaa  jz      short loc_180021AD9
0x180021aac  mov     eax, 1
0x180021ab1  mov     rcx, [rbp+57h+var_30]
0x180021ab5  xor     rcx, rsp; StackCookie
0x180021ab8  call    __security_check_cookie
0x180021abd  lea     r11, [rsp+100h+var_20]
0x180021ac5  mov     rbx, [r11+40h]
0x180021ac9  mov     rsi, [r11+48h]
0x180021acd  mov     rsp, r11
0x180021ad0  pop     r15
0x180021ad2  pop     r14
0x180021ad4  pop     r13
0x180021ad6  pop     rdi
0x180021ad7  pop     rbp
0x180021ad8  retn
0x180021ad9  call    cs:__imp_GetLastError
0x180021adf  test    eax, eax
0x180021ae1  jle     short loc_180021AEB
0x180021ae3  movzx   eax, ax
0x180021ae6  or      eax, 80070000h
0x180021aeb  mov     ecx, eax; this
0x180021aed  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180021af2  int     3; Trap to Debugger
0x180021af3  call    cs:__imp_GetLastError
0x180021af9  test    eax, eax
0x180021afb  jle     short loc_180021B05
0x180021afd  movzx   eax, ax
0x180021b00  or      eax, 80070000h
0x180021b05  mov     ecx, eax; this
0x180021b07  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180021b0c  int     3; Trap to Debugger
0x180021b0d  call    cs:__imp_GetLastError
0x180021b13  test    eax, eax
0x180021b15  jle     short loc_180021B1F
0x180021b17  movzx   eax, ax
0x180021b1a  or      eax, 80070000h
0x180021b1f  mov     ecx, eax; this
0x180021b21  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180021b26  nop
0x180021b27  call    cs:__imp_GetLastError
0x180021b2d  nop
0x180021b2e  test    eax, eax
0x180021b30  jle     short loc_180021B3A
0x180021b32  movzx   eax, ax
0x180021b35  or      eax, 80070000h
0x180021b3a  mov     ecx, eax; this
0x180021b3c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180021b41  nop
0x180021b42  call    cs:__imp_GetLastError
0x180021b48  test    eax, eax
0x180021b4a  jle     short loc_180021B54
0x180021b4c  movzx   eax, ax
0x180021b4f  or      eax, 80070000h
0x180021b54  mov     ecx, eax; this
0x180021b56  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
