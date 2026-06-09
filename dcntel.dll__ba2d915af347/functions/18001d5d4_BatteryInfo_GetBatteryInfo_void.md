# BatteryInfo::GetBatteryInfo(void)

- ea: `0x18001d5d4`
- end: `0x18001da09`
- name: `?GetBatteryInfo@BatteryInfo@@AEBAAEAU_BATTERY_INFO_2@@XZ`
- size: `1077`
- prototype: `struct _BATTERY_INFO_2 *__fastcall(BatteryInfo *__hidden this)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001d4f0`
- `0x18001da10`
- `0x18001da30`
- `0x18001da50`

## callees

- `0x180008dc0`
- `0x180009260`
- `0x1800092e0`
- `0x180009448`
- `0x180014f2c`
- `0x180016748`
- `0x18001c194`
- `0x18001d5d4`
- `0x18001dab0`
- `0x18001dad0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18001dd1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d690`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9ef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d882`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d882`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x18001d98f`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x18001d98f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001d7ff`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001d84b`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001d7ff`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001d84b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001d6c8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001d6c8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18001d6f8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18001d6f8`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18001d737`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18001d737`

## string_xrefs

- `0x18001d689`: `devobj.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct _BATTERY_INFO_2 *__fastcall BatteryInfo::GetBatteryInfo(BatteryInfo *this)
{
  __int64 v1; // rdi
  int v2; // eax
  __int64 DeviceInfoList; // rax
  __int64 v4; // rbx
  unsigned int v5; // r14d
  _DWORD *v7; // rbx
  const WCHAR *v8; // rsi
  HANDLE FileW; // rax
  CBatteryInfo *v10; // rcx
  signed int v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  signed int LastError; // eax
  int v15; // edx
  unsigned int v16; // r8d
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  unsigned __int64 v20; // [rsp+40h] [rbp-79h] BYREF
  void **v21; // [rsp+48h] [rbp-71h] BYREF
  void *v22; // [rsp+50h] [rbp-69h]
  void **v23; // [rsp+58h] [rbp-61h] BYREF
  __int64 v24; // [rsp+60h] [rbp-59h]
  _DWORD *v25; // [rsp+68h] [rbp-51h]
  const int *v26; // [rsp+70h] [rbp-49h] BYREF
  HMODULE Library; // [rsp+78h] [rbp-41h]
  _OWORD OutputBuffer[2]; // [rsp+80h] [rbp-39h] BYREF
  int v29; // [rsp+A0h] [rbp-19h] BYREF
  int v30; // [rsp+A4h] [rbp-15h]
  int v31; // [rsp+A8h] [rbp-11h]
  int v32; // [rsp+ACh] [rbp-Dh]
  __int128 v33; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v34; // [rsp+C0h] [rbp+7h]
  __int64 v35; // [rsp+C8h] [rbp+Fh]

  v1 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + *(unsigned int *)&tls_index);
  v2 = *(_DWORD *)(v1 + 320);
  if ( (v2 & 1) == 0 )
  {
    *(_DWORD *)(v1 + 320) = v2 | 1;
    *(_DWORD *)(v1 + 328) = -1;
    *(_DWORD *)(v1 + 332) = -1;
    *(_DWORD *)(v1 + 336) = -1;
    *(_DWORD *)(v1 + 340) = -1;
    *(_OWORD *)(v1 + 344) = 0;
    *(_QWORD *)(v1 + 360) = 0;
    *(_QWORD *)(v1 + 368) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v1 + 344), L"#", 1u);
    _tlregdtor(BatteryInfo::GetBatteryInfo_::_2_::_dynamic_atexit_destructor_for__result__);
  }
  if ( !*(_BYTE *)(v1 + 308) )
  {
    *(_BYTE *)(v1 + 308) = 1;
    v26 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    Library = LoadLibraryExW(L"devobj.dll", 0, 0x800u);
    memset(OutputBuffer, 0, sizeof(OutputBuffer));
    if ( Library )
    {
      DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
      v4 = DeviceInfoList;
      if ( DeviceInfoList != -1 && (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_BATTERY, 0, 18, 0, 0) )
      {
        v23 = &Microsoft::WRL::Wrappers::HandleT<DeviceInfoHandleTraits>::`vftable';
        v24 = v4;
        LODWORD(OutputBuffer[0]) = 32;
        v5 = 0;
        while ( 1 )
        {
          if ( (unsigned int)DevObjEnumDeviceInterfaces(v4, 0, &GUID_DEVCLASS_BATTERY, v5, OutputBuffer) )
          {
            LODWORD(v20) = 0;
            v7 = 0;
            v25 = 0;
            v8 = 0;
            if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v24, OutputBuffer, 0, 0, &v20, 0) )
            {
              if ( GetLastError() != 122 )
                goto LABEL_28;
              v7 = operator new[]((unsigned int)v20);
              v25 = v7;
              *v7 = 8;
              if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v24, OutputBuffer, v7, (unsigned int)v20, &v20, 0) )
              {
LABEL_27:
                operator delete(v7);
                goto LABEL_28;
              }
              v8 = (const WCHAR *)v7;
            }
            FileW = CreateFileW(v8 + 2, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
            v21 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
            v22 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              v21 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
            }
            else
            {
              v29 = -1;
              v30 = -1;
              v31 = -1;
              v32 = -1;
              v33 = 0;
              v34 = 0;
              v35 = 0;
              std::wstring::_Construct<1,unsigned short const *>((char **)&v33, L"#", 1u);
              if ( CBatteryInfo::TryGetBatteryInfo(v10, v22, (struct _BATTERY_INFO *)&v29) )
              {
                *(_DWORD *)(v1 + 328) = v29;
                *(_DWORD *)(v1 + 332) = v30;
                *(_DWORD *)(v1 + 336) = v31;
                *(_DWORD *)(v1 + 340) = v32;
                std::wstring::operator=(v1 + 344, &v33);
              }
              std::wstring::~wstring((char **)&v33);
              v21 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
              if ( v22 != (void *)-1LL )
              {
                if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v21) )
                  goto LABEL_38;
                v22 = (void *)-1LL;
              }
            }
            if ( v8 )
              goto LABEL_27;
          }
          else if ( GetLastError() == 259 )
          {
            goto LABEL_10;
          }
LABEL_28:
          if ( ++v5 >= 0xA )
          {
LABEL_10:
            v23 = &Microsoft::WRL::Wrappers::HandleT<DeviceInfoHandleTraits>::`vftable';
            if ( v24 == -1
              || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<DeviceInfoHandleTraits>::InternalClose(&v23) )
            {
              break;
            }
LABEL_35:
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v15, v16);
LABEL_38:
            v17 = GetLastError();
            if ( v17 > 0 )
              v17 = (unsigned __int16)v17 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
            JUMPOUT(0x18001DA08LL);
          }
          v4 = v24;
        }
      }
    }
    else if ( !CallNtPowerInformation(SystemBatteryState, 0, 0, OutputBuffer, 0x20u) )
    {
      *(_DWORD *)(v1 + 328) = -1;
      *(_DWORD *)(v1 + 332) = HIDWORD(OutputBuffer[0]);
      *(_DWORD *)(v1 + 336) = DWORD2(OutputBuffer[0]);
      *(_DWORD *)(v1 + 340) = -1;
    }
    v26 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( Library && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v26) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
      goto LABEL_35;
    }
  }
  return (struct _BATTERY_INFO_2 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + *(unsigned int *)&tls_index)
                                  + 328LL);
}

```

## disassembly

```asm
0x18001d5d4  push    rbp
0x18001d5d6  push    rbx
0x18001d5d7  push    rsi
0x18001d5d8  push    rdi
0x18001d5d9  push    r12
0x18001d5db  push    r13
0x18001d5dd  push    r14
0x18001d5df  lea     rbp, [rsp-27h]
0x18001d5e4  sub     rsp, 0E0h
0x18001d5eb  mov     rax, cs:__security_cookie
0x18001d5f2  xor     rax, rsp
0x18001d5f5  mov     [rbp+57h+var_40], rax
0x18001d5f9  mov     ecx, cs:_tls_index
0x18001d5ff  mov     rax, gs:58h
0x18001d608  mov     rdi, [rax+rcx*8]
0x18001d60c  mov     ecx, 140h
0x18001d611  mov     eax, [rcx+rdi]
0x18001d614  mov     r14d, 148h
0x18001d61a  or      r13d, 0FFFFFFFFh
0x18001d61e  xor     r12d, r12d
0x18001d621  test    al, 1
0x18001d623  jnz     short loc_18001D66E
0x18001d625  or      eax, 1
0x18001d628  mov     [rcx+rdi], eax
0x18001d62b  lea     rax, [rdi+r14]
0x18001d62f  mov     [rax], r13d
0x18001d632  mov     [rax+4], r13d
0x18001d636  mov     [rax+8], r13d
0x18001d63a  mov     [rax+0Ch], r13d
0x18001d63e  lea     rcx, [rax+10h]
0x18001d642  xorps   xmm0, xmm0
0x18001d645  movups  xmmword ptr [rcx], xmm0
0x18001d648  mov     [rcx+10h], r12
0x18001d64c  mov     [rcx+18h], r12
0x18001d650  lea     r8d, [r12+1]
0x18001d655  lea     rdx, asc_1801B4764; "#"
0x18001d65c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d661  lea     rcx, _BatteryInfo__GetBatteryInfo____2____dynamic_atexit_destructor_for__result__
0x18001d668  call    __tlregdtor
0x18001d66d  nop
0x18001d66e  mov     eax, 134h
0x18001d673  cmp     [rax+rdi], r12b
0x18001d677  jnz     loc_18001D7A1
0x18001d67d  mov     byte ptr [rax+rdi], 1
0x18001d681  xor     edx, edx; hFile
0x18001d683  mov     r8d, 800h; dwFlags
0x18001d689  lea     rcx, LibFileName; "devobj.dll"
0x18001d690  call    cs:__imp_LoadLibraryExW
0x18001d696  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18001d69d  mov     [rbp+57h+var_A0], rsi
0x18001d6a1  mov     [rbp+57h+var_98], rax
0x18001d6a5  xorps   xmm0, xmm0
0x18001d6a8  xor     edx, edx; InputBuffer
0x18001d6aa  movups  [rbp+57h+OutputBuffer], xmm0
0x18001d6ae  movups  [rbp+57h+var_80], xmm0
0x18001d6b2  test    rax, rax
0x18001d6b5  jz      loc_18001D97C
0x18001d6bb  mov     qword ptr [rsp+110h+dwCreationDisposition], r12
0x18001d6c0  xor     r9d, r9d
0x18001d6c3  xor     r8d, r8d
0x18001d6c6  xor     ecx, ecx
0x18001d6c8  call    cs:__imp_DevObjCreateDeviceInfoList
0x18001d6ce  mov     rbx, rax
0x18001d6d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d6d5  jz      loc_18001D786
0x18001d6db  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r12
0x18001d6e0  mov     qword ptr [rsp+110h+dwCreationDisposition], r12
0x18001d6e5  mov     r9d, 12h
0x18001d6eb  xor     r8d, r8d
0x18001d6ee  lea     rdx, GUID_DEVCLASS_BATTERY
0x18001d6f5  mov     rcx, rax
0x18001d6f8  call    cs:__imp_DevObjGetClassDevs
0x18001d6fe  test    eax, eax
0x18001d700  jz      loc_18001D786
0x18001d706  lea     rax, ??_7?$HandleT@UDeviceInfoHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<DeviceInfoHandleTraits>::`vftable'
0x18001d70d  mov     [rbp+57h+var_B8], rax
0x18001d711  mov     [rbp+57h+var_B0], rbx
0x18001d715  mov     dword ptr [rbp+57h+OutputBuffer], 20h ; ' '
0x18001d71c  mov     r14d, r12d
0x18001d71f  lea     rax, [rbp+57h+OutputBuffer]
0x18001d723  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18001d728  mov     r9d, r14d
0x18001d72b  lea     r8, GUID_DEVCLASS_BATTERY
0x18001d732  xor     edx, edx
0x18001d734  mov     rcx, rbx
0x18001d737  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18001d73d  test    eax, eax
0x18001d73f  jnz     loc_18001D7D5
0x18001d745  call    cs:__imp_GetLastError
0x18001d74b  cmp     eax, 103h
0x18001d750  jnz     loc_18001D966
0x18001d756  lea     rax, ??_7?$HandleT@UDeviceInfoHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<DeviceInfoHandleTraits>::`vftable'
0x18001d75d  mov     [rbp+57h+var_B8], rax
0x18001d761  cmp     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFFh
0x18001d766  jz      short loc_18001D779
0x18001d768  lea     rcx, [rbp+57h+var_B8]
0x18001d76c  call    ?InternalClose@?$HandleT@UDeviceInfoHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<DeviceInfoHandleTraits>::InternalClose(void)
0x18001d771  test    al, al
0x18001d773  jz      loc_18001D9D5
0x18001d779  mov     r14d, 148h
0x18001d77f  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18001d786  mov     [rbp+57h+var_A0], rsi
0x18001d78a  cmp     [rbp+57h+var_98], r12
0x18001d78e  jz      short loc_18001D7A1
0x18001d790  lea     rcx, [rbp+57h+var_A0]
0x18001d794  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18001d799  test    al, al
0x18001d79b  jz      loc_18001D9BB
0x18001d7a1  mov     edx, cs:_tls_index
0x18001d7a7  mov     rcx, gs:58h
0x18001d7b0  mov     eax, r14d
0x18001d7b3  add     rax, [rcx+rdx*8]
0x18001d7b7  mov     rcx, [rbp+57h+var_40]
0x18001d7bb  xor     rcx, rsp; StackCookie
0x18001d7be  call    __security_check_cookie
0x18001d7c3  add     rsp, 0E0h
0x18001d7ca  pop     r14
0x18001d7cc  pop     r13
0x18001d7ce  pop     r12
0x18001d7d0  pop     rdi
0x18001d7d1  pop     rsi
0x18001d7d2  pop     rbx
0x18001d7d3  pop     rbp
0x18001d7d4  retn
0x18001d7d5  mov     dword ptr [rbp+57h+var_D0], r12d
0x18001d7d9  mov     rbx, r12
0x18001d7dc  mov     [rbp+57h+var_A8], rbx
0x18001d7e0  mov     rsi, r12
0x18001d7e3  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r12
0x18001d7e8  lea     rax, [rbp+57h+var_D0]
0x18001d7ec  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18001d7f1  xor     r9d, r9d
0x18001d7f4  xor     r8d, r8d
0x18001d7f7  lea     rdx, [rbp+57h+OutputBuffer]
0x18001d7fb  mov     rcx, [rbp+57h+var_B0]
0x18001d7ff  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18001d805  test    eax, eax
0x18001d807  jnz     short loc_18001D85D
0x18001d809  call    cs:__imp_GetLastError
0x18001d80f  cmp     eax, 7Ah ; 'z'
0x18001d812  jz      short loc_18001D819
0x18001d814  jmp     loc_18001D966
0x18001d819  mov     ecx, dword ptr [rbp+57h+var_D0]; unsigned __int64
0x18001d81c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d821  mov     rbx, rax
0x18001d824  mov     [rbp+57h+var_A8], rax
0x18001d828  mov     dword ptr [rax], 8
0x18001d82e  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r12
0x18001d833  lea     rax, [rbp+57h+var_D0]
0x18001d837  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18001d83c  mov     r9d, dword ptr [rbp+57h+var_D0]
0x18001d840  mov     r8, rbx
0x18001d843  lea     rdx, [rbp+57h+OutputBuffer]
0x18001d847  mov     rcx, [rbp+57h+var_B0]
0x18001d84b  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18001d851  test    eax, eax
0x18001d853  jnz     short loc_18001D85A
0x18001d855  jmp     loc_18001D959
0x18001d85a  mov     rsi, rbx
0x18001d85d  lea     rcx, [rsi+4]; lpFileName
0x18001d861  mov     [rsp+110h+hTemplateFile], r12; hTemplateFile
0x18001d866  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001d86e  mov     eax, 3
0x18001d873  mov     [rsp+110h+dwCreationDisposition], eax; dwCreationDisposition
0x18001d877  xor     r9d, r9d; lpSecurityAttributes
0x18001d87a  mov     r8d, eax; dwShareMode
0x18001d87d  mov     edx, 0C0000000h; dwDesiredAccess
0x18001d882  call    cs:__imp_CreateFileW
0x18001d888  lea     rcx, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x18001d88f  mov     [rbp+57h+var_C8], rcx
0x18001d893  mov     [rbp+57h+var_C0], rax
0x18001d897  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d89b  jz      loc_18001D950
0x18001d8a1  mov     [rbp+57h+var_70], r13d
0x18001d8a5  mov     [rbp+57h+var_6C], r13d
0x18001d8a9  mov     [rbp+57h+var_68], r13d
0x18001d8ad  mov     [rbp+57h+var_64], r13d
0x18001d8b1  xorps   xmm0, xmm0
0x18001d8b4  movups  [rbp+57h+var_60], xmm0
0x18001d8b8  mov     [rbp+57h+var_50], r12
0x18001d8bc  mov     [rbp+57h+var_48], r12
0x18001d8c0  mov     r8d, 1
0x18001d8c6  lea     rdx, asc_1801B4764; "#"
0x18001d8cd  lea     rcx, [rbp+57h+var_60]
0x18001d8d1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d8d6  nop
0x18001d8d7  lea     r8, [rbp+57h+var_70]; struct _BATTERY_INFO *
0x18001d8db  mov     rdx, [rbp+57h+var_C0]; void *
0x18001d8df  call    ?TryGetBatteryInfo@CBatteryInfo@@AEBA_NPEAXAEAU_BATTERY_INFO@@@Z; CBatteryInfo::TryGetBatteryInfo(void *,_BATTERY_INFO &)
0x18001d8e4  test    al, al
0x18001d8e6  jz      short loc_18001D919
0x18001d8e8  mov     ecx, 148h
0x18001d8ed  mov     eax, [rbp+57h+var_70]
0x18001d8f0  mov     [rcx+rdi], eax
0x18001d8f3  mov     eax, [rbp+57h+var_6C]
0x18001d8f6  mov     [rcx+rdi+4], eax
0x18001d8fa  mov     eax, [rbp+57h+var_68]
0x18001d8fd  mov     [rcx+rdi+8], eax
0x18001d901  mov     eax, [rbp+57h+var_64]
0x18001d904  mov     [rcx+rdi+0Ch], eax
0x18001d908  add     rcx, 10h
0x18001d90c  add     rcx, rdi
0x18001d90f  lea     rdx, [rbp+57h+var_60]
0x18001d913  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001d918  nop
0x18001d919  lea     rcx, [rbp+57h+var_60]
0x18001d91d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d922  nop
0x18001d923  lea     rax, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x18001d92a  mov     [rbp+57h+var_C8], rax
0x18001d92e  cmp     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFFh
0x18001d933  jz      short loc_18001D954
0x18001d935  lea     rcx, [rbp+57h+var_C8]
0x18001d939  call    ?InternalClose@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(void)
0x18001d93e  test    al, al
0x18001d940  jz      loc_18001D9EF
0x18001d946  mov     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFFh
0x18001d94e  jmp     short loc_18001D954
0x18001d950  mov     [rbp+57h+var_C8], rcx
0x18001d954  test    rsi, rsi
0x18001d957  jz      short loc_18001D966
0x18001d959  mov     edx, 8
0x18001d95e  mov     rcx, rbx; Block
0x18001d961  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d966  inc     r14d
0x18001d969  cmp     r14d, 0Ah
0x18001d96d  jnb     loc_18001D756
0x18001d973  mov     rbx, [rbp+57h+var_B0]
0x18001d977  jmp     loc_18001D71F
0x18001d97c  mov     [rsp+110h+dwCreationDisposition], 20h ; ' '; OutputBufferLength
0x18001d984  lea     r9, [rbp+57h+OutputBuffer]; OutputBuffer
0x18001d988  xor     r8d, r8d; InputBufferLength
0x18001d98b  lea     ecx, [r8+5]; InformationLevel
0x18001d98f  call    cs:__imp_CallNtPowerInformation
0x18001d995  test    eax, eax
0x18001d997  jnz     loc_18001D786
0x18001d99d  mov     [rdi+r14], r13d
0x18001d9a1  mov     eax, dword ptr [rbp+57h+OutputBuffer+0Ch]
0x18001d9a4  mov     [rdi+r14+4], eax
0x18001d9a9  mov     eax, dword ptr [rbp+57h+OutputBuffer+8]
0x18001d9ac  mov     [rdi+r14+8], eax
0x18001d9b1  mov     [rdi+r14+0Ch], r13d
0x18001d9b6  jmp     loc_18001D786
0x18001d9bb  call    cs:__imp_GetLastError
0x18001d9c1  test    eax, eax
0x18001d9c3  jle     short loc_18001D9CD
0x18001d9c5  movzx   eax, ax
0x18001d9c8  or      eax, 80070000h
0x18001d9cd  mov     ecx, eax; this
0x18001d9cf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001d9d4  nop
0x18001d9d5  call    cs:__imp_GetLastError
0x18001d9db  test    eax, eax
0x18001d9dd  jle     short loc_18001D9E7
0x18001d9df  movzx   eax, ax
0x18001d9e2  or      eax, 80070000h
0x18001d9e7  mov     ecx, eax; this
0x18001d9e9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001d9ee  nop
0x18001d9ef  call    cs:__imp_GetLastError
0x18001d9f5  test    eax, eax
0x18001d9f7  jle     short loc_18001DA01
0x18001d9f9  movzx   eax, ax
0x18001d9fc  or      eax, 80070000h
0x18001da01  mov     ecx, eax; this
0x18001da03  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
