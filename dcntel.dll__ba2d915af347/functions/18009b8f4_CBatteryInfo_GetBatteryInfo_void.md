# CBatteryInfo::GetBatteryInfo(void)

- ea: `0x18009b8f4`
- end: `0x18009bd29`
- name: `?GetBatteryInfo@CBatteryInfo@@AEBAAEAU_BATTERY_INFO@@XZ`
- size: `1077`
- prototype: `struct _BATTERY_INFO *__fastcall(CBatteryInfo *__hidden this)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18009b810`
- `0x18009bd30`
- `0x18009bd50`
- `0x18009bd70`

## callees

- `0x180008dc0`
- `0x180009260`
- `0x1800092e0`
- `0x180009448`
- `0x180014f2c`
- `0x180016748`
- `0x18001c194`
- `0x18001dab0`
- `0x18001dad0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18001dd1c`
- `0x18009b8f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009b9b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009b9b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ba65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bb29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bcdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bcf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bd0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ba65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bb29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bcdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bcf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bd0f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009bba2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009bba2`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x18009bcaf`
- `api-ms-win-power-base-l1-1-0!CallNtPowerInformation` at `0x18009bcaf`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18009bb1f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18009bb6b`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18009bb1f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18009bb6b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18009b9e8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18009b9e8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18009ba18`
- `DEVOBJ!DevObjGetClassDevs` at `0x18009ba18`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18009ba57`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18009ba57`

## string_xrefs

- `0x18009b9a9`: `devobj.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct _BATTERY_INFO *__fastcall CBatteryInfo::GetBatteryInfo(CBatteryInfo *this)
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
  v2 = *(_DWORD *)(v1 + 696);
  if ( (v2 & 1) == 0 )
  {
    *(_DWORD *)(v1 + 696) = v2 | 1;
    *(_DWORD *)(v1 + 704) = -1;
    *(_DWORD *)(v1 + 708) = -1;
    *(_DWORD *)(v1 + 712) = -1;
    *(_DWORD *)(v1 + 716) = -1;
    *(_OWORD *)(v1 + 720) = 0;
    *(_QWORD *)(v1 + 736) = 0;
    *(_QWORD *)(v1 + 744) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v1 + 720), L"#", 1u);
    _tlregdtor(CBatteryInfo::GetBatteryInfo_::_2_::_dynamic_atexit_destructor_for__result__);
  }
  if ( !*(_BYTE *)(v1 + 313) )
  {
    *(_BYTE *)(v1 + 313) = 1;
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
                *(_DWORD *)(v1 + 704) = v29;
                *(_DWORD *)(v1 + 708) = v30;
                *(_DWORD *)(v1 + 712) = v31;
                *(_DWORD *)(v1 + 716) = v32;
                std::wstring::operator=(v1 + 720, &v33);
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
            JUMPOUT(0x18009BD28LL);
          }
          v4 = v24;
        }
      }
    }
    else if ( !CallNtPowerInformation(SystemBatteryState, 0, 0, OutputBuffer, 0x20u) )
    {
      *(_DWORD *)(v1 + 704) = -1;
      *(_DWORD *)(v1 + 708) = HIDWORD(OutputBuffer[0]);
      *(_DWORD *)(v1 + 712) = DWORD2(OutputBuffer[0]);
      *(_DWORD *)(v1 + 716) = -1;
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
  return (struct _BATTERY_INFO *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + *(unsigned int *)&tls_index)
                                + 704LL);
}

```

## disassembly

```asm
0x18009b8f4  push    rbp
0x18009b8f6  push    rbx
0x18009b8f7  push    rsi
0x18009b8f8  push    rdi
0x18009b8f9  push    r12
0x18009b8fb  push    r13
0x18009b8fd  push    r14
0x18009b8ff  lea     rbp, [rsp-27h]
0x18009b904  sub     rsp, 0E0h
0x18009b90b  mov     rax, cs:__security_cookie
0x18009b912  xor     rax, rsp
0x18009b915  mov     [rbp+57h+var_40], rax
0x18009b919  mov     ecx, cs:_tls_index
0x18009b91f  mov     rax, gs:58h
0x18009b928  mov     rdi, [rax+rcx*8]
0x18009b92c  mov     ecx, 2B8h
0x18009b931  mov     eax, [rcx+rdi]
0x18009b934  mov     r14d, 2C0h
0x18009b93a  or      r13d, 0FFFFFFFFh
0x18009b93e  xor     r12d, r12d
0x18009b941  test    al, 1
0x18009b943  jnz     short loc_18009B98E
0x18009b945  or      eax, 1
0x18009b948  mov     [rcx+rdi], eax
0x18009b94b  lea     rax, [rdi+r14]
0x18009b94f  mov     [rax], r13d
0x18009b952  mov     [rax+4], r13d
0x18009b956  mov     [rax+8], r13d
0x18009b95a  mov     [rax+0Ch], r13d
0x18009b95e  lea     rcx, [rax+10h]
0x18009b962  xorps   xmm0, xmm0
0x18009b965  movups  xmmword ptr [rcx], xmm0
0x18009b968  mov     [rcx+10h], r12
0x18009b96c  mov     [rcx+18h], r12
0x18009b970  lea     r8d, [r12+1]
0x18009b975  lea     rdx, asc_1801B4764; "#"
0x18009b97c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009b981  lea     rcx, _CBatteryInfo__GetBatteryInfo____2____dynamic_atexit_destructor_for__result__
0x18009b988  call    __tlregdtor
0x18009b98d  nop
0x18009b98e  mov     eax, 139h
0x18009b993  cmp     [rax+rdi], r12b
0x18009b997  jnz     loc_18009BAC1
0x18009b99d  mov     byte ptr [rax+rdi], 1
0x18009b9a1  xor     edx, edx; hFile
0x18009b9a3  mov     r8d, 800h; dwFlags
0x18009b9a9  lea     rcx, LibFileName; "devobj.dll"
0x18009b9b0  call    cs:__imp_LoadLibraryExW
0x18009b9b6  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18009b9bd  mov     [rbp+57h+var_A0], rsi
0x18009b9c1  mov     [rbp+57h+var_98], rax
0x18009b9c5  xorps   xmm0, xmm0
0x18009b9c8  xor     edx, edx; InputBuffer
0x18009b9ca  movups  [rbp+57h+OutputBuffer], xmm0
0x18009b9ce  movups  [rbp+57h+var_80], xmm0
0x18009b9d2  test    rax, rax
0x18009b9d5  jz      loc_18009BC9C
0x18009b9db  mov     qword ptr [rsp+110h+dwCreationDisposition], r12
0x18009b9e0  xor     r9d, r9d
0x18009b9e3  xor     r8d, r8d
0x18009b9e6  xor     ecx, ecx
0x18009b9e8  call    cs:__imp_DevObjCreateDeviceInfoList
0x18009b9ee  mov     rbx, rax
0x18009b9f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009b9f5  jz      loc_18009BAA6
0x18009b9fb  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r12
0x18009ba00  mov     qword ptr [rsp+110h+dwCreationDisposition], r12
0x18009ba05  mov     r9d, 12h
0x18009ba0b  xor     r8d, r8d
0x18009ba0e  lea     rdx, GUID_DEVCLASS_BATTERY
0x18009ba15  mov     rcx, rax
0x18009ba18  call    cs:__imp_DevObjGetClassDevs
0x18009ba1e  test    eax, eax
0x18009ba20  jz      loc_18009BAA6
0x18009ba26  lea     rax, ??_7?$HandleT@UDeviceInfoHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<DeviceInfoHandleTraits>::`vftable'
0x18009ba2d  mov     [rbp+57h+var_B8], rax
0x18009ba31  mov     [rbp+57h+var_B0], rbx
0x18009ba35  mov     dword ptr [rbp+57h+OutputBuffer], 20h ; ' '
0x18009ba3c  mov     r14d, r12d
0x18009ba3f  lea     rax, [rbp+57h+OutputBuffer]
0x18009ba43  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18009ba48  mov     r9d, r14d
0x18009ba4b  lea     r8, GUID_DEVCLASS_BATTERY
0x18009ba52  xor     edx, edx
0x18009ba54  mov     rcx, rbx
0x18009ba57  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18009ba5d  test    eax, eax
0x18009ba5f  jnz     loc_18009BAF5
0x18009ba65  call    cs:__imp_GetLastError
0x18009ba6b  cmp     eax, 103h
0x18009ba70  jnz     loc_18009BC86
0x18009ba76  lea     rax, ??_7?$HandleT@UDeviceInfoHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<DeviceInfoHandleTraits>::`vftable'
0x18009ba7d  mov     [rbp+57h+var_B8], rax
0x18009ba81  cmp     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFFh
0x18009ba86  jz      short loc_18009BA99
0x18009ba88  lea     rcx, [rbp+57h+var_B8]
0x18009ba8c  call    ?InternalClose@?$HandleT@UDeviceInfoHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<DeviceInfoHandleTraits>::InternalClose(void)
0x18009ba91  test    al, al
0x18009ba93  jz      loc_18009BCF5
0x18009ba99  mov     r14d, 2C0h
0x18009ba9f  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18009baa6  mov     [rbp+57h+var_A0], rsi
0x18009baaa  cmp     [rbp+57h+var_98], r12
0x18009baae  jz      short loc_18009BAC1
0x18009bab0  lea     rcx, [rbp+57h+var_A0]
0x18009bab4  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18009bab9  test    al, al
0x18009babb  jz      loc_18009BCDB
0x18009bac1  mov     edx, cs:_tls_index
0x18009bac7  mov     rcx, gs:58h
0x18009bad0  mov     eax, r14d
0x18009bad3  add     rax, [rcx+rdx*8]
0x18009bad7  mov     rcx, [rbp+57h+var_40]
0x18009badb  xor     rcx, rsp; StackCookie
0x18009bade  call    __security_check_cookie
0x18009bae3  add     rsp, 0E0h
0x18009baea  pop     r14
0x18009baec  pop     r13
0x18009baee  pop     r12
0x18009baf0  pop     rdi
0x18009baf1  pop     rsi
0x18009baf2  pop     rbx
0x18009baf3  pop     rbp
0x18009baf4  retn
0x18009baf5  mov     dword ptr [rbp+57h+var_D0], r12d
0x18009baf9  mov     rbx, r12
0x18009bafc  mov     [rbp+57h+var_A8], rbx
0x18009bb00  mov     rsi, r12
0x18009bb03  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r12
0x18009bb08  lea     rax, [rbp+57h+var_D0]
0x18009bb0c  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18009bb11  xor     r9d, r9d
0x18009bb14  xor     r8d, r8d
0x18009bb17  lea     rdx, [rbp+57h+OutputBuffer]
0x18009bb1b  mov     rcx, [rbp+57h+var_B0]
0x18009bb1f  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18009bb25  test    eax, eax
0x18009bb27  jnz     short loc_18009BB7D
0x18009bb29  call    cs:__imp_GetLastError
0x18009bb2f  cmp     eax, 7Ah ; 'z'
0x18009bb32  jz      short loc_18009BB39
0x18009bb34  jmp     loc_18009BC86
0x18009bb39  mov     ecx, dword ptr [rbp+57h+var_D0]; unsigned __int64
0x18009bb3c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009bb41  mov     rbx, rax
0x18009bb44  mov     [rbp+57h+var_A8], rax
0x18009bb48  mov     dword ptr [rax], 8
0x18009bb4e  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r12
0x18009bb53  lea     rax, [rbp+57h+var_D0]
0x18009bb57  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18009bb5c  mov     r9d, dword ptr [rbp+57h+var_D0]
0x18009bb60  mov     r8, rbx
0x18009bb63  lea     rdx, [rbp+57h+OutputBuffer]
0x18009bb67  mov     rcx, [rbp+57h+var_B0]
0x18009bb6b  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18009bb71  test    eax, eax
0x18009bb73  jnz     short loc_18009BB7A
0x18009bb75  jmp     loc_18009BC79
0x18009bb7a  mov     rsi, rbx
0x18009bb7d  lea     rcx, [rsi+4]; lpFileName
0x18009bb81  mov     [rsp+110h+hTemplateFile], r12; hTemplateFile
0x18009bb86  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009bb8e  mov     eax, 3
0x18009bb93  mov     [rsp+110h+dwCreationDisposition], eax; dwCreationDisposition
0x18009bb97  xor     r9d, r9d; lpSecurityAttributes
0x18009bb9a  mov     r8d, eax; dwShareMode
0x18009bb9d  mov     edx, 0C0000000h; dwDesiredAccess
0x18009bba2  call    cs:__imp_CreateFileW
0x18009bba8  lea     rcx, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x18009bbaf  mov     [rbp+57h+var_C8], rcx
0x18009bbb3  mov     [rbp+57h+var_C0], rax
0x18009bbb7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009bbbb  jz      loc_18009BC70
0x18009bbc1  mov     [rbp+57h+var_70], r13d
0x18009bbc5  mov     [rbp+57h+var_6C], r13d
0x18009bbc9  mov     [rbp+57h+var_68], r13d
0x18009bbcd  mov     [rbp+57h+var_64], r13d
0x18009bbd1  xorps   xmm0, xmm0
0x18009bbd4  movups  [rbp+57h+var_60], xmm0
0x18009bbd8  mov     [rbp+57h+var_50], r12
0x18009bbdc  mov     [rbp+57h+var_48], r12
0x18009bbe0  mov     r8d, 1
0x18009bbe6  lea     rdx, asc_1801B4764; "#"
0x18009bbed  lea     rcx, [rbp+57h+var_60]
0x18009bbf1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009bbf6  nop
0x18009bbf7  lea     r8, [rbp+57h+var_70]; struct _BATTERY_INFO *
0x18009bbfb  mov     rdx, [rbp+57h+var_C0]; void *
0x18009bbff  call    ?TryGetBatteryInfo@CBatteryInfo@@AEBA_NPEAXAEAU_BATTERY_INFO@@@Z; CBatteryInfo::TryGetBatteryInfo(void *,_BATTERY_INFO &)
0x18009bc04  test    al, al
0x18009bc06  jz      short loc_18009BC39
0x18009bc08  mov     ecx, 2C0h
0x18009bc0d  mov     eax, [rbp+57h+var_70]
0x18009bc10  mov     [rcx+rdi], eax
0x18009bc13  mov     eax, [rbp+57h+var_6C]
0x18009bc16  mov     [rcx+rdi+4], eax
0x18009bc1a  mov     eax, [rbp+57h+var_68]
0x18009bc1d  mov     [rcx+rdi+8], eax
0x18009bc21  mov     eax, [rbp+57h+var_64]
0x18009bc24  mov     [rcx+rdi+0Ch], eax
0x18009bc28  add     rcx, 10h
0x18009bc2c  add     rcx, rdi
0x18009bc2f  lea     rdx, [rbp+57h+var_60]
0x18009bc33  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18009bc38  nop
0x18009bc39  lea     rcx, [rbp+57h+var_60]
0x18009bc3d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009bc42  nop
0x18009bc43  lea     rax, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x18009bc4a  mov     [rbp+57h+var_C8], rax
0x18009bc4e  cmp     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFFh
0x18009bc53  jz      short loc_18009BC74
0x18009bc55  lea     rcx, [rbp+57h+var_C8]
0x18009bc59  call    ?InternalClose@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(void)
0x18009bc5e  test    al, al
0x18009bc60  jz      loc_18009BD0F
0x18009bc66  mov     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFFh
0x18009bc6e  jmp     short loc_18009BC74
0x18009bc70  mov     [rbp+57h+var_C8], rcx
0x18009bc74  test    rsi, rsi
0x18009bc77  jz      short loc_18009BC86
0x18009bc79  mov     edx, 8
0x18009bc7e  mov     rcx, rbx; Block
0x18009bc81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009bc86  inc     r14d
0x18009bc89  cmp     r14d, 0Ah
0x18009bc8d  jnb     loc_18009BA76
0x18009bc93  mov     rbx, [rbp+57h+var_B0]
0x18009bc97  jmp     loc_18009BA3F
0x18009bc9c  mov     [rsp+110h+dwCreationDisposition], 20h ; ' '; OutputBufferLength
0x18009bca4  lea     r9, [rbp+57h+OutputBuffer]; OutputBuffer
0x18009bca8  xor     r8d, r8d; InputBufferLength
0x18009bcab  lea     ecx, [r8+5]; InformationLevel
0x18009bcaf  call    cs:__imp_CallNtPowerInformation
0x18009bcb5  test    eax, eax
0x18009bcb7  jnz     loc_18009BAA6
0x18009bcbd  mov     [rdi+r14], r13d
0x18009bcc1  mov     eax, dword ptr [rbp+57h+OutputBuffer+0Ch]
0x18009bcc4  mov     [rdi+r14+4], eax
0x18009bcc9  mov     eax, dword ptr [rbp+57h+OutputBuffer+8]
0x18009bccc  mov     [rdi+r14+8], eax
0x18009bcd1  mov     [rdi+r14+0Ch], r13d
0x18009bcd6  jmp     loc_18009BAA6
0x18009bcdb  call    cs:__imp_GetLastError
0x18009bce1  test    eax, eax
0x18009bce3  jle     short loc_18009BCED
0x18009bce5  movzx   eax, ax
0x18009bce8  or      eax, 80070000h
0x18009bced  mov     ecx, eax; this
0x18009bcef  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18009bcf4  nop
0x18009bcf5  call    cs:__imp_GetLastError
0x18009bcfb  test    eax, eax
0x18009bcfd  jle     short loc_18009BD07
0x18009bcff  movzx   eax, ax
0x18009bd02  or      eax, 80070000h
0x18009bd07  mov     ecx, eax; this
0x18009bd09  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18009bd0e  nop
0x18009bd0f  call    cs:__imp_GetLastError
0x18009bd15  test    eax, eax
0x18009bd17  jle     short loc_18009BD21
0x18009bd19  movzx   eax, ax
0x18009bd1c  or      eax, 80070000h
0x18009bd21  mov     ecx, eax; this
0x18009bd23  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
