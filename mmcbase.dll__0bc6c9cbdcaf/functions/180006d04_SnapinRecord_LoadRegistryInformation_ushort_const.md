# SnapinRecord::LoadRegistryInformation(ushort const *)

- ea: `0x180006d04`
- end: `0x180007156`
- name: `?LoadRegistryInformation@SnapinRecord@@AEAAJPEBG@Z`
- size: `1106`
- prototype: `__int64 __fastcall(SnapinRecord *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011290`

## callees

- `0x1800064b4`
- `0x180006730`
- `0x180006d04`
- `0x18000715c`
- `0x180007310`
- `0x18000cfbc`
- `0x180010d70`
- `0x180012154`
- `0x18001b522`
- `0x18001b550`
- `0x18001d010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180006d68`
- `msvcrt!_wcsnicmp` at `0x180006d68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006dfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006dfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006fa8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007119`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006fa8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007119`

## pseudocode

```c
__int64 __fastcall SnapinRecord::LoadRegistryInformation(SnapinRecord *this, const unsigned __int16 *a2)
{
  int v4; // eax
  signed int v5; // ebx
  LPCWSTR v6; // r15
  LSTATUS v7; // eax
  int ValueW; // eax
  int COMRegistrationInformation; // eax
  HKEY hKey; // [rsp+30h] [rbp-59h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-51h] BYREF
  void **v13; // [rsp+40h] [rbp-49h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-41h]
  __int64 v15; // [rsp+50h] [rbp-39h]
  int v16; // [rsp+58h] [rbp-31h]
  unsigned __int16 v17[32]; // [rsp+60h] [rbp-29h] BYREF

  hKey = 0;
  v13 = &CStr::`vftable';
  lpSubKey = (LPCWSTR)&CStr::s_rgwchEmptyStringBuffer;
  v15 = 0;
  v16 = 0;
  if ( !_wcsnicmp(a2, L"FX:", 3u) )
    *((_DWORD *)this + 459) |= 6u;
  v4 = CStr::Format((CStr *)&v13, L"%s\\%s", L"Software\\Microsoft\\MMC\\SnapIns", a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = lpSubKey;
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
    v5 = v7;
    if ( !v7 )
      goto LABEL_14;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          18,
          (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
          (_DWORD)v6,
          v5);
    }
    else
    {
LABEL_14:
      ValueW = SnapinRecord::RegGetValueW(this, hKey, L"NameString", (unsigned __int16 *)this + 4, 0x80u, 0);
      if ( ValueW < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
      {
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          19,
          (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
          (_DWORD)v6,
          ValueW);
      }
      memset_0(v17, 0, sizeof(v17));
      SnapinRecord::RegGetValueW(this, hKey, L"DisableWatson", v17, 0x20u, 8u);
      phkResult = 0;
      if ( !RegOpenKeyExW(hKey, L"ForceWER", 0, 0x20019u, &phkResult) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids, v6);
        RegCloseKey(phkResult);
        *((_DWORD *)this + 459) |= 0x10u;
      }
      phkResult = 0;
      if ( !RegOpenKeyExW(hKey, L"StandAlone", 0, 0x20019u, &phkResult) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids, v6);
        RegCloseKey(phkResult);
        *((_DWORD *)this + 459) |= 1u;
      }
      if ( (*(unsigned __int8 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 56LL))(this) )
      {
        SnapinRecord::RegGetValueW(this, hKey, L"Type", (unsigned __int16 *)this + 404, 0x80u, 0);
        SnapinRecord::RegGetValueW(this, hKey, L"ApplicationBase", (unsigned __int16 *)this + 276, 0x80u, 0);
        SnapinRecord::RegGetValueW(this, hKey, L"AssemblyName", (unsigned __int16 *)this + 660, 0x80u, 0);
        SnapinRecord::RegGetValueW(this, hKey, L"FxVersion", (unsigned __int16 *)this + 148, 0x80u, 0);
        SnapinRecord::RegGetValueW(this, hKey, L"ModuleName", (unsigned __int16 *)this + 532, 0x80u, 0);
        SnapinRecord::RegGetValueW(this, hKey, L"RuntimeVersion", (unsigned __int16 *)this + 788, 0x80u, 0);
        if ( !*((_WORD *)this + 788) )
          StringCchCopyW((unsigned __int16 *)this + 788, 0x80u, L"Unknown");
      }
      else
      {
        COMRegistrationInformation = SnapinRecord::GetCOMRegistrationInformation(this, a2);
        if ( COMRegistrationInformation < 0
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
        {
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            22,
            (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
            (_DWORD)a2,
            COMRegistrationInformation);
        }
      }
      v5 = 0;
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      17,
      (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
      (_DWORD)a2,
      v4);
  }
  if ( hKey )
    RegCloseKey(hKey);
  v13 = &CStr::`vftable';
  CStr::Empty((CStr *)&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006d04  mov     [rsp-8+arg_10], rbx
0x180006d09  push    rbp
0x180006d0a  push    rsi
0x180006d0b  push    rdi
0x180006d0c  push    r12
0x180006d0e  push    r13
0x180006d10  push    r14
0x180006d12  push    r15
0x180006d14  lea     rbp, [rsp-27h]
0x180006d19  sub     rsp, 0B0h
0x180006d20  mov     rax, cs:__security_cookie
0x180006d27  xor     rax, rsp
0x180006d2a  mov     [rbp+57h+var_40], rax
0x180006d2e  mov     r14, rdx
0x180006d31  mov     rdi, rcx
0x180006d34  xor     r12d, r12d
0x180006d37  mov     [rbp+57h+hKey], r12
0x180006d3b  lea     r15, ??_7CStr@@6B@; const CStr::`vftable'
0x180006d42  mov     [rbp+57h+var_A0], r15
0x180006d46  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180006d4d  mov     [rbp+57h+lpSubKey], rax
0x180006d51  mov     [rbp+57h+var_90], r12
0x180006d55  mov     [rbp+57h+var_88], r12d
0x180006d59  lea     r8d, [r12+3]; MaxCount
0x180006d5e  lea     rdx, ?s_szFXPrefix@SnapinRecord@@0QBGB; "FX:"
0x180006d65  mov     rcx, r14; String1
0x180006d68  call    cs:__imp__wcsnicmp
0x180006d6e  test    eax, eax
0x180006d70  jnz     short loc_180006D79
0x180006d72  or      dword ptr [rdi+72Ch], 6
0x180006d79  mov     r9, r14
0x180006d7c  lea     r8, aSoftwareMicros; "Software\\Microsoft\\MMC\\SnapIns"
0x180006d83  lea     rdx, aSS; "%s\\%s"
0x180006d8a  lea     rcx, [rbp+57h+var_A0]; this
0x180006d8e  call    ?Format@CStr@@QEAAJPEBGZZ; CStr::Format(ushort const *,...)
0x180006d93  mov     ebx, eax
0x180006d95  test    eax, eax
0x180006d97  jns     short loc_180006DDB
0x180006d99  lea     rsi, WPP_GLOBAL_Control
0x180006da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006da7  cmp     rcx, rsi
0x180006daa  jz      loc_180007110
0x180006db0  cmp     byte ptr [rcx+19h], 2
0x180006db4  jb      loc_180007110
0x180006dba  mov     edx, 11h
0x180006dbf  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180006dc3  mov     r9, r14
0x180006dc6  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180006dcd  mov     rcx, [rcx+10h]
0x180006dd1  call    WPP_SF_Sd
0x180006dd6  jmp     loc_180007110
0x180006ddb  mov     r15, [rbp+57h+lpSubKey]
0x180006ddf  lea     rax, [rbp+57h+hKey]
0x180006de3  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180006de8  mov     r9d, 20019h; samDesired
0x180006dee  xor     r8d, r8d; ulOptions
0x180006df1  mov     rdx, r15; lpSubKey
0x180006df4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006dfb  call    cs:__imp_RegOpenKeyExW
0x180006e01  mov     ebx, eax
0x180006e03  test    eax, eax
0x180006e05  jz      short loc_180006E58
0x180006e07  jle     short loc_180006E12
0x180006e09  movzx   ebx, ax
0x180006e0c  or      ebx, 80070000h
0x180006e12  test    ebx, ebx
0x180006e14  jns     short loc_180006E58
0x180006e16  lea     rsi, WPP_GLOBAL_Control
0x180006e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e24  cmp     rcx, rsi
0x180006e27  jz      loc_180007109
0x180006e2d  cmp     byte ptr [rcx+19h], 2
0x180006e31  jb      loc_180007109
0x180006e37  mov     edx, 12h
0x180006e3c  mov     dword ptr [rsp+0E0h+phkResult], ebx
0x180006e40  mov     r9, r15
0x180006e43  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180006e4a  mov     rcx, [rcx+10h]
0x180006e4e  call    WPP_SF_Sd
0x180006e53  jmp     loc_180007109
0x180006e58  lea     r9, [rdi+8]; unsigned __int16 *
0x180006e5c  mov     [rsp+0E0h+var_B8], r12d; unsigned int
0x180006e61  mov     r13d, 80h
0x180006e67  mov     [rsp+0E0h+phkResult], r13; unsigned __int64
0x180006e6c  lea     r8, aNamestring; "NameString"
0x180006e73  mov     rdx, [rbp+57h+hKey]; HKEY
0x180006e77  mov     rcx, rdi; this
0x180006e7a  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x180006e7f  lea     rsi, WPP_GLOBAL_Control
0x180006e86  test    eax, eax
0x180006e88  jns     short loc_180006EB7
0x180006e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e91  cmp     rcx, rsi
0x180006e94  jz      short loc_180006EB7
0x180006e96  cmp     byte ptr [rcx+19h], 3
0x180006e9a  jb      short loc_180006EB7
0x180006e9c  lea     edx, [r13-6Dh]
0x180006ea0  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180006ea4  mov     r9, r15
0x180006ea7  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180006eae  mov     rcx, [rcx+10h]
0x180006eb2  call    WPP_SF_Sd
0x180006eb7  xor     edx, edx; Val
0x180006eb9  lea     r8d, [rdx+40h]; Size
0x180006ebd  lea     rcx, [rbp+57h+var_80]; void *
0x180006ec1  call    memset_0
0x180006ec6  mov     [rsp+0E0h+var_B8], 8; unsigned int
0x180006ece  mov     [rsp+0E0h+phkResult], 20h ; ' '; unsigned __int64
0x180006ed7  lea     r9, [rbp+57h+var_80]; unsigned __int16 *
0x180006edb  lea     r8, ValueName; "DisableWatson"
0x180006ee2  mov     rdx, [rbp+57h+hKey]; HKEY
0x180006ee6  mov     rcx, rdi; this
0x180006ee9  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x180006eee  mov     [rbp+57h+var_A8], r12
0x180006ef2  lea     rax, [rbp+57h+var_A8]
0x180006ef6  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180006efb  mov     ebx, 20019h
0x180006f00  mov     r9d, ebx; samDesired
0x180006f03  xor     r8d, r8d; ulOptions
0x180006f06  lea     rdx, SubKey; "ForceWER"
0x180006f0d  mov     rcx, [rbp+57h+hKey]; hKey
0x180006f11  call    cs:__imp_RegOpenKeyExW
0x180006f17  test    eax, eax
0x180006f19  jnz     short loc_180006F54
0x180006f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f22  cmp     rcx, rsi
0x180006f25  jz      short loc_180006F43
0x180006f27  cmp     byte ptr [rcx+19h], 5
0x180006f2b  jb      short loc_180006F43
0x180006f2d  lea     edx, [rax+14h]
0x180006f30  mov     r9, r15
0x180006f33  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180006f3a  mov     rcx, [rcx+10h]
0x180006f3e  call    WPP_SF_S
0x180006f43  mov     rcx, [rbp+57h+var_A8]; hKey
0x180006f47  call    cs:__imp_RegCloseKey
0x180006f4d  or      dword ptr [rdi+72Ch], 10h
0x180006f54  mov     [rbp+57h+var_A8], r12
0x180006f58  lea     rax, [rbp+57h+var_A8]
0x180006f5c  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180006f61  mov     r9d, ebx; samDesired
0x180006f64  xor     r8d, r8d; ulOptions
0x180006f67  lea     rdx, aStandalone_0; "StandAlone"
0x180006f6e  mov     rcx, [rbp+57h+hKey]; hKey
0x180006f72  call    cs:__imp_RegOpenKeyExW
0x180006f78  test    eax, eax
0x180006f7a  jnz     short loc_180006FB5
0x180006f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f83  cmp     rcx, rsi
0x180006f86  jz      short loc_180006FA4
0x180006f88  cmp     byte ptr [rcx+19h], 4
0x180006f8c  jb      short loc_180006FA4
0x180006f8e  lea     edx, [rax+15h]
0x180006f91  mov     r9, r15
0x180006f94  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180006f9b  mov     rcx, [rcx+10h]
0x180006f9f  call    WPP_SF_S
0x180006fa4  mov     rcx, [rbp+57h+var_A8]; hKey
0x180006fa8  call    cs:__imp_RegCloseKey
0x180006fae  or      dword ptr [rdi+72Ch], 1
0x180006fb5  mov     rax, [rdi]
0x180006fb8  mov     rcx, rdi
0x180006fbb  mov     rax, [rax+38h]
0x180006fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc4  mov     rcx, rdi; this
0x180006fc7  test    al, al
0x180006fc9  jnz     short loc_180007016
0x180006fcb  mov     rdx, r14; unsigned __int16 *
0x180006fce  call    ?GetCOMRegistrationInformation@SnapinRecord@@AEAAJPEBG@Z; SnapinRecord::GetCOMRegistrationInformation(ushort const *)
0x180006fd3  test    eax, eax
0x180006fd5  jns     loc_180007106
0x180006fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fe2  cmp     rcx, rsi
0x180006fe5  jz      loc_180007106
0x180006feb  cmp     byte ptr [rcx+19h], 3
0x180006fef  jb      loc_180007106
0x180006ff5  mov     edx, 16h
0x180006ffa  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180006ffe  mov     r9, r14
0x180007001  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180007008  mov     rcx, [rcx+10h]
0x18000700c  call    WPP_SF_Sd
0x180007011  jmp     loc_180007106
0x180007016  lea     r9, [rdi+328h]; unsigned __int16 *
0x18000701d  mov     [rsp+0E0h+var_B8], r12d; unsigned int
0x180007022  mov     [rsp+0E0h+phkResult], r13; unsigned __int64
0x180007027  lea     r8, aType; "Type"
0x18000702e  mov     rdx, [rbp+57h+hKey]; HKEY
0x180007032  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x180007037  lea     r9, [rdi+228h]; unsigned __int16 *
0x18000703e  mov     [rsp+0E0h+var_B8], r12d; unsigned int
0x180007043  mov     [rsp+0E0h+phkResult], r13; unsigned __int64
0x180007048  lea     r8, aApplicationbas; "ApplicationBase"
0x18000704f  mov     rdx, [rbp+57h+hKey]; HKEY
0x180007053  mov     rcx, rdi; this
0x180007056  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x18000705b  lea     r9, [rdi+528h]; unsigned __int16 *
0x180007062  mov     [rsp+0E0h+var_B8], r12d; unsigned int
0x180007067  mov     [rsp+0E0h+phkResult], r13; unsigned __int64
0x18000706c  lea     r8, aAssemblyname; "AssemblyName"
0x180007073  mov     rdx, [rbp+57h+hKey]; HKEY
0x180007077  mov     rcx, rdi; this
0x18000707a  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x18000707f  lea     r9, [rdi+128h]; unsigned __int16 *
0x180007086  mov     [rsp+0E0h+var_B8], r12d; unsigned int
0x18000708b  mov     [rsp+0E0h+phkResult], r13; unsigned __int64
0x180007090  lea     r8, aFxversion; "FxVersion"
0x180007097  mov     rdx, [rbp+57h+hKey]; HKEY
0x18000709b  mov     rcx, rdi; this
0x18000709e  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x1800070a3  lea     r9, [rdi+428h]; unsigned __int16 *
0x1800070aa  mov     [rsp+0E0h+var_B8], r12d; unsigned int
0x1800070af  mov     [rsp+0E0h+phkResult], r13; unsigned __int64
0x1800070b4  lea     r8, aModulename; "ModuleName"
0x1800070bb  mov     rdx, [rbp+57h+hKey]; HKEY
0x1800070bf  mov     rcx, rdi; this
0x1800070c2  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x1800070c7  lea     rbx, [rdi+628h]
0x1800070ce  mov     [rsp+0E0h+var_B8], r12d; unsigned int
0x1800070d3  mov     [rsp+0E0h+phkResult], r13; unsigned __int64
0x1800070d8  mov     r9, rbx; unsigned __int16 *
0x1800070db  lea     r8, aRuntimeversion; "RuntimeVersion"
0x1800070e2  mov     rdx, [rbp+57h+hKey]; HKEY
0x1800070e6  mov     rcx, rdi; this
0x1800070e9  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x1800070ee  cmp     [rbx], r12w
0x1800070f2  jnz     short loc_180007106
0x1800070f4  lea     r8, ?s_szUnknown@SnapinRecord@@0QBGB; "Unknown"
0x1800070fb  mov     rdx, r13; unsigned __int64
0x1800070fe  mov     rcx, rbx; unsigned __int16 *
0x180007101  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007106  mov     ebx, r12d
0x180007109  lea     r15, ??_7CStr@@6B@; const CStr::`vftable'
0x180007110  mov     rcx, [rbp+57h+hKey]; hKey
0x180007114  test    rcx, rcx
0x180007117  jz      short loc_180007120
0x180007119  call    cs:__imp_RegCloseKey
0x18000711f  nop
0x180007120  mov     [rbp+57h+var_A0], r15
0x180007124  lea     rcx, [rbp+57h+var_A0]; this
0x180007128  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18000712d  mov     eax, ebx
0x18000712f  mov     rcx, [rbp+57h+var_40]
0x180007133  xor     rcx, rsp; StackCookie
0x180007136  call    __security_check_cookie
0x18000713b  mov     rbx, [rsp+0E0h+arg_10]
0x180007143  add     rsp, 0B0h
0x18000714a  pop     r15
0x18000714c  pop     r14
0x18000714e  pop     r13
0x180007150  pop     r12
0x180007152  pop     rdi
0x180007153  pop     rsi
0x180007154  pop     rbp
0x180007155  retn
```
