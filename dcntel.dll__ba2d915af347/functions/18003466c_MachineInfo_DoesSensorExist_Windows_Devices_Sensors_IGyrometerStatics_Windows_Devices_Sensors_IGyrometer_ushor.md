# MachineInfo::DoesSensorExist<Windows::Devices::Sensors::IGyrometerStatics,Windows::Devices::Sensors::IGyrometer>(ushort const *)

- ea: `0x18003466c`
- end: `0x180034935`
- name: `??$DoesSensorExist@UIGyrometerStatics@Sensors@Devices@Windows@@UIGyrometer@234@@MachineInfo@@CAHPEBG@Z`
- size: `713`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003af40`

## callees

- `0x180008dc0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002a690`
- `0x18003466c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800346f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800346f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800347a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800347a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003491b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003491b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003475c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800348a3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003475c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800348a3`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003471d`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003471d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180034839`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180034839`

## string_xrefs

- `0x18003479e`: `WindowsCreateStringReference`
- `0x1800346ef`: `api-ms-win-core-winrt-string-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall MachineInfo::DoesSensorExist<Windows::Devices::Sensors::IGyrometerStatics,Windows::Devices::Sensors::IGyrometer>(
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
          v6 = L"Windows.Devices.Sensors.Gyrometer";
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
                   L"Windows.Devices.Sensors.Gyrometer",
                   v5,
                   &v27,
                   &v26) >= 0
              && (int)RoGetActivationFactory(v26, &GUID_83b6e7c9_e49d_4b39_86e6_cd554be4c5c1, &v22) >= 0 )
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
        JUMPOUT(0x180034934LL);
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
0x18003466c  push    rbp
0x18003466e  push    rbx
0x18003466f  push    rsi
0x180034670  push    rdi
0x180034671  push    r12
0x180034673  push    r13
0x180034675  push    r14
0x180034677  push    r15
0x180034679  lea     rbp, [rsp-1Fh]
0x18003467e  sub     rsp, 88h
0x180034685  mov     rax, cs:__security_cookie
0x18003468c  xor     rax, rsp
0x18003468f  mov     [rbp+57h+var_48], rax
0x180034693  xor     r15d, r15d
0x180034696  mov     [rbp+57h+var_68], r15
0x18003469a  mov     [rbp+57h+var_60], r15
0x18003469e  xorps   xmm0, xmm0
0x1800346a1  movups  [rbp+57h+var_58], xmm0
0x1800346a5  mov     [rbp+57h+var_88], r15
0x1800346a9  mov     [rbp+57h+var_90], r15
0x1800346ad  mov     ebx, 800401F0h
0x1800346b2  mov     [rbp+57h+var_70], ebx
0x1800346b5  lea     edx, [r15+2]; unsigned __int16
0x1800346b9  lea     ecx, [rdx+4]; unsigned __int16
0x1800346bc  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800346c1  test    al, al
0x1800346c3  jnz     short loc_1800346E4
0x1800346c5  mov     rcx, [rbp+57h+var_90]
0x1800346c9  test    rcx, rcx
0x1800346cc  jz      short loc_1800346DF
0x1800346ce  mov     [rbp+57h+var_90], r15
0x1800346d2  mov     rax, [rcx]
0x1800346d5  mov     rax, [rax+10h]
0x1800346d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346de  nop
0x1800346df  jmp     loc_18003477D
0x1800346e4  mov     esi, r15d
0x1800346e7  xor     edx, edx; hFile
0x1800346e9  mov     r8d, 800h; dwFlags
0x1800346ef  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800346f6  call    cs:__imp_LoadLibraryExW
0x1800346fc  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180034703  mov     [rbp+57h+var_80], r12
0x180034707  mov     [rbp+57h+hModule], rax
0x18003470b  test    rax, rax
0x18003470e  jz      loc_180034884
0x180034714  mov     r13d, 1
0x18003471a  mov     ecx, r13d
0x18003471d  call    cs:__imp_RoInitialize
0x180034723  test    eax, eax
0x180034725  js      short loc_18003472E
0x180034727  mov     ebx, eax
0x180034729  mov     [rbp+57h+var_70], eax
0x18003472c  jmp     short loc_180034735
0x18003472e  cmp     eax, 80010106h
0x180034733  jz      short loc_18003479E
0x180034735  test    eax, eax
0x180034737  jns     short loc_18003479E
0x180034739  mov     [rbp+57h+var_80], r12
0x18003473d  cmp     [rbp+57h+hModule], r15
0x180034741  jz      short loc_180034758
0x180034743  lea     rcx, [rbp+57h+var_80]
0x180034747  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003474c  test    al, al
0x18003474e  jz      loc_18003491B
0x180034754  mov     [rbp+57h+hModule], r15
0x180034758  test    ebx, ebx
0x18003475a  js      short loc_180034763
0x18003475c  call    cs:__imp_RoUninitialize
0x180034762  nop
0x180034763  mov     rcx, [rbp+57h+var_90]
0x180034767  test    rcx, rcx
0x18003476a  jz      short loc_18003477D
0x18003476c  mov     [rbp+57h+var_90], r15
0x180034770  mov     rax, [rcx]
0x180034773  mov     rax, [rax+10h]
0x180034777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003477c  nop
0x18003477d  mov     rcx, [rbp+57h+var_88]
0x180034781  test    rcx, rcx
0x180034784  jz      short loc_180034797
0x180034786  mov     [rbp+57h+var_88], r15
0x18003478a  mov     rax, [rcx]
0x18003478d  mov     rax, [rax+10h]
0x180034791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034796  nop
0x180034797  xor     eax, eax
0x180034799  jmp     loc_1800348E0
0x18003479e  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x1800347a5  mov     rcx, [rbp+57h+hModule]; hModule
0x1800347a9  call    cs:__imp_GetProcAddress
0x1800347af  mov     r10, rax
0x1800347b2  test    rax, rax
0x1800347b5  jz      loc_180034884
0x1800347bb  mov     r9d, 7FFFFFFFh
0x1800347c1  mov     r8d, r9d
0x1800347c4  lea     rcx, ?RuntimeClass_Windows_Devices_Sensors_Gyrometer@@3QBGB; "Windows.Devices.Sensors.Gyrometer"
0x1800347cb  cmp     [rcx], r15w
0x1800347cf  jz      short loc_1800347DA
0x1800347d1  add     rcx, 2
0x1800347d5  sub     r8, r13
0x1800347d8  jnz     short loc_1800347CB
0x1800347da  mov     rax, r8
0x1800347dd  sub     r9, r8
0x1800347e0  neg     rax
0x1800347e3  sbb     rdx, rdx
0x1800347e6  and     rdx, r9
0x1800347e9  test    r8, r8
0x1800347ec  jz      loc_180034884
0x1800347f2  lea     r9, [rbp+57h+var_68]
0x1800347f6  lea     r8, [rbp+57h+var_60]
0x1800347fa  lea     rcx, ?RuntimeClass_Windows_Devices_Sensors_Gyrometer@@3QBGB; "Windows.Devices.Sensors.Gyrometer"
0x180034801  mov     rax, r10
0x180034804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034809  test    eax, eax
0x18003480b  js      short loc_180034884
0x18003480d  mov     rdi, [rbp+57h+var_68]
0x180034811  mov     rcx, [rbp+57h+var_88]
0x180034815  test    rcx, rcx
0x180034818  jz      short loc_18003482B
0x18003481a  mov     [rbp+57h+var_88], r15
0x18003481e  mov     rax, [rcx]
0x180034821  mov     rax, [rax+10h]
0x180034825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003482a  nop
0x18003482b  lea     r8, [rbp+57h+var_88]
0x18003482f  lea     rdx, _GUID_83b6e7c9_e49d_4b39_86e6_cd554be4c5c1
0x180034836  mov     rcx, rdi
0x180034839  call    cs:__imp_RoGetActivationFactory
0x18003483f  test    eax, eax
0x180034841  js      short loc_180034884
0x180034843  mov     rdi, [rbp+57h+var_88]
0x180034847  test    rdi, rdi
0x18003484a  jz      short loc_180034884
0x18003484c  mov     rax, [rdi]
0x18003484f  mov     r14, [rax+30h]
0x180034853  mov     rcx, [rbp+57h+var_90]
0x180034857  test    rcx, rcx
0x18003485a  jz      short loc_18003486D
0x18003485c  mov     [rbp+57h+var_90], r15
0x180034860  mov     rdx, [rcx]
0x180034863  mov     rax, [rdx+10h]
0x180034867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003486c  nop
0x18003486d  lea     rdx, [rbp+57h+var_90]
0x180034871  mov     rcx, rdi
0x180034874  mov     rax, r14
0x180034877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003487c  cmp     [rbp+57h+var_90], r15
0x180034880  cmovnz  esi, r13d
0x180034884  mov     [rbp+57h+var_80], r12
0x180034888  cmp     [rbp+57h+hModule], r15
0x18003488c  jz      short loc_18003489F
0x18003488e  lea     rcx, [rbp+57h+var_80]
0x180034892  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180034897  test    al, al
0x180034899  jz      short loc_180034900
0x18003489b  mov     [rbp+57h+hModule], r15
0x18003489f  test    ebx, ebx
0x1800348a1  js      short loc_1800348AA
0x1800348a3  call    cs:__imp_RoUninitialize
0x1800348a9  nop
0x1800348aa  mov     rcx, [rbp+57h+var_90]
0x1800348ae  test    rcx, rcx
0x1800348b1  jz      short loc_1800348C4
0x1800348b3  mov     [rbp+57h+var_90], r15
0x1800348b7  mov     rax, [rcx]
0x1800348ba  mov     rax, [rax+10h]
0x1800348be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348c3  nop
0x1800348c4  mov     rcx, [rbp+57h+var_88]
0x1800348c8  test    rcx, rcx
0x1800348cb  jz      short loc_1800348DE
0x1800348cd  mov     [rbp+57h+var_88], r15
0x1800348d1  mov     rdx, [rcx]
0x1800348d4  mov     rax, [rdx+10h]
0x1800348d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348dd  nop
0x1800348de  mov     eax, esi
0x1800348e0  mov     rcx, [rbp+57h+var_48]
0x1800348e4  xor     rcx, rsp; StackCookie
0x1800348e7  call    __security_check_cookie
0x1800348ec  add     rsp, 88h
0x1800348f3  pop     r15
0x1800348f5  pop     r14
0x1800348f7  pop     r13
0x1800348f9  pop     r12
0x1800348fb  pop     rdi
0x1800348fc  pop     rsi
0x1800348fd  pop     rbx
0x1800348fe  pop     rbp
0x1800348ff  retn
0x180034900  call    cs:__imp_GetLastError
0x180034906  nop
0x180034907  test    eax, eax
0x180034909  jle     short loc_180034913
0x18003490b  movzx   eax, ax
0x18003490e  or      eax, 80070000h
0x180034913  mov     ecx, eax; this
0x180034915  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003491a  int     3; Trap to Debugger
0x18003491b  call    cs:__imp_GetLastError
0x180034921  test    eax, eax
0x180034923  jle     short loc_18003492D
0x180034925  movzx   eax, ax
0x180034928  or      eax, 80070000h
0x18003492d  mov     ecx, eax; this
0x18003492f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
