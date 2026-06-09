# MachineInfo::DoesSensorExist<Windows::Devices::Sensors::ICompassStatics,Windows::Devices::Sensors::ICompass>(ushort const *)

- ea: `0x18003439c`
- end: `0x180034665`
- name: `??$DoesSensorExist@UICompassStatics@Sensors@Devices@Windows@@UICompass@234@@MachineInfo@@CAHPEBG@Z`
- size: `713`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003af50`

## callees

- `0x180008dc0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002a690`
- `0x18003439c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034426`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034426`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800344d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800344d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003464b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003464b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003448c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800345d3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003448c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800345d3`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003444d`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003444d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180034569`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180034569`

## string_xrefs

- `0x1800344ce`: `WindowsCreateStringReference`
- `0x18003441f`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x1800344f4`: `Windows.Devices.Sensors.Compass`
- `0x18003452a`: `Windows.Devices.Sensors.Compass`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MachineInfo::DoesSensorExist<Windows::Devices::Sensors::ICompassStatics,Windows::Devices::Sensors::ICompass>(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3)
{
  int v3; // ebx
  unsigned int v4; // esi
  __int64 v5; // rdx
  const unsigned __int16 *v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  FARPROC ProcAddress; // r10
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rcx
  signed int v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  signed int LastError; // eax
  int v19; // edx
  unsigned int v20; // r8d
  __int64 v21; // [rsp+30h] [rbp-39h] BYREF
  __int64 v22; // [rsp+38h] [rbp-31h] BYREF
  const int *v23; // [rsp+40h] [rbp-29h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-21h]
  int v25; // [rsp+50h] [rbp-19h]
  __int64 v26; // [rsp+58h] [rbp-11h] BYREF
  __int64 v27; // [rsp+60h] [rbp-9h] BYREF
  __int128 v28; // [rsp+68h] [rbp-1h]

  v26 = 0;
  v27 = 0;
  v28 = 0;
  v22 = 0;
  v21 = 0;
  v3 = -2147221008;
  v25 = -2147221008;
  if ( !IsWindowsVersionOrGreater(6u, 2u, a3) )
    return 0;
  v4 = 0;
  v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  if ( hModule )
  {
    v7 = RoInitialize(1);
    if ( v7 < 0 )
    {
      if ( v7 == -2147417850 )
      {
LABEL_11:
        ProcAddress = GetProcAddress(hModule, "WindowsCreateStringReference");
        if ( ProcAddress )
        {
          v12 = 0x7FFFFFFF;
          v6 = L"Windows.Devices.Sensors.Compass";
          do
          {
            if ( !*v6 )
              break;
            ++v6;
            --v12;
          }
          while ( v12 );
          v5 = (0x7FFFFFFF - v12) & ((unsigned __int128)-(__int128)(unsigned __int64)v12 >> 64);
          if ( v12 )
          {
            if ( ((int (__fastcall *)(const unsigned __int16 *, __int64, __int64 *, __int64 *))ProcAddress)(
                   L"Windows.Devices.Sensors.Compass",
                   v5,
                   &v27,
                   &v26) >= 0
              && (int)RoGetActivationFactory(v26, &GUID_9abc97df_56ec_4c25_b54d_40a68bb5b269, &v22) >= 0 )
            {
              if ( v22 )
              {
                (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v21);
                if ( v21 )
                  v4 = 1;
              }
            }
          }
        }
        goto LABEL_21;
      }
    }
    else
    {
      v3 = v7;
      v25 = v7;
    }
    if ( v7 < 0 )
    {
      v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v23) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v19, v20);
        JUMPOUT(0x180034664LL);
      }
      hModule = 0;
      if ( v3 >= 0 )
        RoUninitialize(v9, v8);
      return 0;
    }
    goto LABEL_11;
  }
LABEL_21:
  v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v23) )
    {
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
      __debugbreak();
    }
    hModule = 0;
  }
  if ( v3 >= 0 )
    RoUninitialize(v6, v5);
  v13 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 16LL))(v13, v5);
  }
  v14 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return v4;
}

```

## disassembly

```asm
0x18003439c  push    rbp
0x18003439e  push    rbx
0x18003439f  push    rsi
0x1800343a0  push    rdi
0x1800343a1  push    r12
0x1800343a3  push    r13
0x1800343a5  push    r14
0x1800343a7  push    r15
0x1800343a9  lea     rbp, [rsp-1Fh]
0x1800343ae  sub     rsp, 88h
0x1800343b5  mov     rax, cs:__security_cookie
0x1800343bc  xor     rax, rsp
0x1800343bf  mov     [rbp+57h+var_48], rax
0x1800343c3  xor     r15d, r15d
0x1800343c6  mov     [rbp+57h+var_68], r15
0x1800343ca  mov     [rbp+57h+var_60], r15
0x1800343ce  xorps   xmm0, xmm0
0x1800343d1  movups  [rbp+57h+var_58], xmm0
0x1800343d5  mov     [rbp+57h+var_88], r15
0x1800343d9  mov     [rbp+57h+var_90], r15
0x1800343dd  mov     ebx, 800401F0h
0x1800343e2  mov     [rbp+57h+var_70], ebx
0x1800343e5  lea     edx, [r15+2]; unsigned __int16
0x1800343e9  lea     ecx, [rdx+4]; unsigned __int16
0x1800343ec  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800343f1  test    al, al
0x1800343f3  jnz     short loc_180034414
0x1800343f5  mov     rcx, [rbp+57h+var_90]
0x1800343f9  test    rcx, rcx
0x1800343fc  jz      short loc_18003440F
0x1800343fe  mov     [rbp+57h+var_90], r15
0x180034402  mov     rax, [rcx]
0x180034405  mov     rax, [rax+10h]
0x180034409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003440e  nop
0x18003440f  jmp     loc_1800344AD
0x180034414  mov     esi, r15d
0x180034417  xor     edx, edx; hFile
0x180034419  mov     r8d, 800h; dwFlags
0x18003441f  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x180034426  call    cs:__imp_LoadLibraryExW
0x18003442c  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180034433  mov     [rbp+57h+var_80], r12
0x180034437  mov     [rbp+57h+hModule], rax
0x18003443b  test    rax, rax
0x18003443e  jz      loc_1800345B4
0x180034444  mov     r13d, 1
0x18003444a  mov     ecx, r13d
0x18003444d  call    cs:__imp_RoInitialize
0x180034453  test    eax, eax
0x180034455  js      short loc_18003445E
0x180034457  mov     ebx, eax
0x180034459  mov     [rbp+57h+var_70], eax
0x18003445c  jmp     short loc_180034465
0x18003445e  cmp     eax, 80010106h
0x180034463  jz      short loc_1800344CE
0x180034465  test    eax, eax
0x180034467  jns     short loc_1800344CE
0x180034469  mov     [rbp+57h+var_80], r12
0x18003446d  cmp     [rbp+57h+hModule], r15
0x180034471  jz      short loc_180034488
0x180034473  lea     rcx, [rbp+57h+var_80]
0x180034477  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003447c  test    al, al
0x18003447e  jz      loc_18003464B
0x180034484  mov     [rbp+57h+hModule], r15
0x180034488  test    ebx, ebx
0x18003448a  js      short loc_180034493
0x18003448c  call    cs:__imp_RoUninitialize
0x180034492  nop
0x180034493  mov     rcx, [rbp+57h+var_90]
0x180034497  test    rcx, rcx
0x18003449a  jz      short loc_1800344AD
0x18003449c  mov     [rbp+57h+var_90], r15
0x1800344a0  mov     rax, [rcx]
0x1800344a3  mov     rax, [rax+10h]
0x1800344a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344ac  nop
0x1800344ad  mov     rcx, [rbp+57h+var_88]
0x1800344b1  test    rcx, rcx
0x1800344b4  jz      short loc_1800344C7
0x1800344b6  mov     [rbp+57h+var_88], r15
0x1800344ba  mov     rax, [rcx]
0x1800344bd  mov     rax, [rax+10h]
0x1800344c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344c6  nop
0x1800344c7  xor     eax, eax
0x1800344c9  jmp     loc_180034610
0x1800344ce  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x1800344d5  mov     rcx, [rbp+57h+hModule]; hModule
0x1800344d9  call    cs:__imp_GetProcAddress
0x1800344df  mov     r10, rax
0x1800344e2  test    rax, rax
0x1800344e5  jz      loc_1800345B4
0x1800344eb  mov     r9d, 7FFFFFFFh
0x1800344f1  mov     r8d, r9d
0x1800344f4  lea     rcx, ?RuntimeClass_Windows_Devices_Sensors_Compass@@3QBGB; "Windows.Devices.Sensors.Compass"
0x1800344fb  cmp     [rcx], r15w
0x1800344ff  jz      short loc_18003450A
0x180034501  add     rcx, 2
0x180034505  sub     r8, r13
0x180034508  jnz     short loc_1800344FB
0x18003450a  mov     rax, r8
0x18003450d  sub     r9, r8
0x180034510  neg     rax
0x180034513  sbb     rdx, rdx
0x180034516  and     rdx, r9
0x180034519  test    r8, r8
0x18003451c  jz      loc_1800345B4
0x180034522  lea     r9, [rbp+57h+var_68]
0x180034526  lea     r8, [rbp+57h+var_60]
0x18003452a  lea     rcx, ?RuntimeClass_Windows_Devices_Sensors_Compass@@3QBGB; "Windows.Devices.Sensors.Compass"
0x180034531  mov     rax, r10
0x180034534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034539  test    eax, eax
0x18003453b  js      short loc_1800345B4
0x18003453d  mov     rdi, [rbp+57h+var_68]
0x180034541  mov     rcx, [rbp+57h+var_88]
0x180034545  test    rcx, rcx
0x180034548  jz      short loc_18003455B
0x18003454a  mov     [rbp+57h+var_88], r15
0x18003454e  mov     rax, [rcx]
0x180034551  mov     rax, [rax+10h]
0x180034555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003455a  nop
0x18003455b  lea     r8, [rbp+57h+var_88]
0x18003455f  lea     rdx, _GUID_9abc97df_56ec_4c25_b54d_40a68bb5b269
0x180034566  mov     rcx, rdi
0x180034569  call    cs:__imp_RoGetActivationFactory
0x18003456f  test    eax, eax
0x180034571  js      short loc_1800345B4
0x180034573  mov     rdi, [rbp+57h+var_88]
0x180034577  test    rdi, rdi
0x18003457a  jz      short loc_1800345B4
0x18003457c  mov     rax, [rdi]
0x18003457f  mov     r14, [rax+30h]
0x180034583  mov     rcx, [rbp+57h+var_90]
0x180034587  test    rcx, rcx
0x18003458a  jz      short loc_18003459D
0x18003458c  mov     [rbp+57h+var_90], r15
0x180034590  mov     rdx, [rcx]
0x180034593  mov     rax, [rdx+10h]
0x180034597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003459c  nop
0x18003459d  lea     rdx, [rbp+57h+var_90]
0x1800345a1  mov     rcx, rdi
0x1800345a4  mov     rax, r14
0x1800345a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800345ac  cmp     [rbp+57h+var_90], r15
0x1800345b0  cmovnz  esi, r13d
0x1800345b4  mov     [rbp+57h+var_80], r12
0x1800345b8  cmp     [rbp+57h+hModule], r15
0x1800345bc  jz      short loc_1800345CF
0x1800345be  lea     rcx, [rbp+57h+var_80]
0x1800345c2  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800345c7  test    al, al
0x1800345c9  jz      short loc_180034630
0x1800345cb  mov     [rbp+57h+hModule], r15
0x1800345cf  test    ebx, ebx
0x1800345d1  js      short loc_1800345DA
0x1800345d3  call    cs:__imp_RoUninitialize
0x1800345d9  nop
0x1800345da  mov     rcx, [rbp+57h+var_90]
0x1800345de  test    rcx, rcx
0x1800345e1  jz      short loc_1800345F4
0x1800345e3  mov     [rbp+57h+var_90], r15
0x1800345e7  mov     rax, [rcx]
0x1800345ea  mov     rax, [rax+10h]
0x1800345ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800345f3  nop
0x1800345f4  mov     rcx, [rbp+57h+var_88]
0x1800345f8  test    rcx, rcx
0x1800345fb  jz      short loc_18003460E
0x1800345fd  mov     [rbp+57h+var_88], r15
0x180034601  mov     rdx, [rcx]
0x180034604  mov     rax, [rdx+10h]
0x180034608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003460d  nop
0x18003460e  mov     eax, esi
0x180034610  mov     rcx, [rbp+57h+var_48]
0x180034614  xor     rcx, rsp; StackCookie
0x180034617  call    __security_check_cookie
0x18003461c  add     rsp, 88h
0x180034623  pop     r15
0x180034625  pop     r14
0x180034627  pop     r13
0x180034629  pop     r12
0x18003462b  pop     rdi
0x18003462c  pop     rsi
0x18003462d  pop     rbx
0x18003462e  pop     rbp
0x18003462f  retn
0x180034630  call    cs:__imp_GetLastError
0x180034636  nop
0x180034637  test    eax, eax
0x180034639  jle     short loc_180034643
0x18003463b  movzx   eax, ax
0x18003463e  or      eax, 80070000h
0x180034643  mov     ecx, eax; this
0x180034645  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003464a  int     3; Trap to Debugger
0x18003464b  call    cs:__imp_GetLastError
0x180034651  test    eax, eax
0x180034653  jle     short loc_18003465D
0x180034655  movzx   eax, ax
0x180034658  or      eax, 80070000h
0x18003465d  mov     ecx, eax; this
0x18003465f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
