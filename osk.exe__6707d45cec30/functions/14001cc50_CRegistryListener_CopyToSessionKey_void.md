# CRegistryListener::_CopyToSessionKey(void)

- ea: `0x14001cc50`
- end: `0x14001cf67`
- name: `?_CopyToSessionKey@CRegistryListener@@AEAAXXZ`
- size: `791`
- prototype: `void __fastcall(CRegistryListener *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001c940`
- `0x14001d1d0`

## callees

- `0x140005c90`
- `0x140007e90`
- `0x140009524`
- `0x140009f28`
- `0x140013a34`
- `0x1400170d8`
- `0x14001c448`
- `0x14001c494`
- `0x14001caa4`
- `0x14001cc50`
- `0x140025d70`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14001cece`
- `ADVAPI32!RegSetValueExW` at `0x14001cece`
- `ADVAPI32!RegEnumValueW` at `0x14001ce41`
- `ADVAPI32!RegEnumValueW` at `0x14001cea7`
- `ADVAPI32!RegEnumValueW` at `0x14001ce41`
- `ADVAPI32!RegEnumValueW` at `0x14001cea7`
- `msvcrt!free` at `0x14001cee7`
- `msvcrt!free` at `0x14001cefc`
- `msvcrt!free` at `0x14001cf17`
- `msvcrt!free` at `0x14001cee7`
- `msvcrt!free` at `0x14001cefc`
- `msvcrt!free` at `0x14001cf17`

## string_xrefs

- `0x14001cc98`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x14001cd05`: `%s\ATConfig`
- `0x14001cd6d`: `%s\ATConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRegistryListener::_CopyToSessionKey(LPCWSTR *this)
{
  unsigned int v2; // r11d
  BYTE *v3; // rbx
  unsigned __int16 *v4; // rcx
  unsigned __int64 v5; // rdx
  const WCHAR *v6; // rbx
  unsigned __int16 *v7; // r9
  DWORD i; // esi
  BYTE *v9; // rdi
  LSTATUS v10; // eax
  LPBYTE v11; // rcx
  LPBYTE lpData; // [rsp+30h] [rbp-D0h]
  DWORD Type[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchValueName; // [rsp+58h] [rbp-A8h] BYREF
  LPBYTE v17; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey[3]; // [rsp+68h] [rbp-98h] BYREF
  HKEY v19[3]; // [rsp+80h] [rbp-80h] BYREF
  HKEY v20[3]; // [rsp+98h] [rbp-68h] BYREF
  HKEY v21[4]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[264]; // [rsp+D0h] [rbp-30h] BYREF

  memset(v19, 0, sizeof(v19));
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)v19,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\",
                       0x20019u) )
    goto LABEL_28;
  memset(hKey, 0, sizeof(hKey));
  if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v19[0], this[8], 0x20019u) )
    goto LABEL_27;
  CATUtils::SessionKeyString((__int64)&v15);
  v17 = 0;
  *(_QWORD *)Type = 0;
  if ( (int)StringCchLengthW(L"%s\\ATConfig", 0x7FFFFFFFu, (unsigned __int64 *)&v17) < 0 )
    goto LABEL_26;
  if ( (int)StringCchLengthW(v15, v2, (unsigned __int64 *)Type) < 0 )
    goto LABEL_26;
  v3 = &v17[*(_QWORD *)Type];
  if ( &v17[*(_QWORD *)Type] < v17 )
    goto LABEL_26;
  *(_QWORD *)Type = 0;
  if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(Type, v3) )
  {
    v4 = *(unsigned __int16 **)Type;
    goto LABEL_25;
  }
  v5 = (unsigned __int64)v3;
  v6 = *(const WCHAR **)Type;
  if ( (int)StringCchPrintfW(*(unsigned __int16 **)Type, v5, L"%s\\ATConfig", v15) < 0 )
    goto LABEL_24;
  memset(v21, 0, 24);
  memset(v20, 0, sizeof(v20));
  if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v20, HKEY_LOCAL_MACHINE, v6, 0x2001Fu)
    || (unsigned int)ATL::CRegKey::Create((ATL::CRegKey *)v21, v20[0], this[8], v7, 1u, 0x2001Fu, (HKEY)lpData, Type) )
  {
    goto LABEL_23;
  }
  for ( i = 0; ; ++i )
  {
    cchValueName = 260;
    Type[0] = 0;
    cbData = 0;
    v9 = 0;
    v17 = 0;
    v10 = RegEnumValueW(hKey[0], i, ValueName, &cchValueName, 0, Type, 0, &cbData);
    if ( v10 && v10 != 234 )
      goto LABEL_17;
    if ( !(unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(&v17, cbData) )
      break;
    cchValueName = 260;
    v9 = v17;
    v10 = RegEnumValueW(hKey[0], i, ValueName, &cchValueName, 0, Type, v17, &cbData);
    if ( !v10 )
    {
      RegSetValueExW(v21[0], ValueName, 0, Type[0], v9, cbData);
      goto LABEL_19;
    }
LABEL_17:
    if ( v10 == 259 || i > 0x64 )
    {
      v11 = v9;
      goto LABEL_22;
    }
LABEL_19:
    free(v9);
  }
  v11 = v17;
LABEL_22:
  free(v11);
LABEL_23:
  ATL::CRegKey::Close((ATL::CRegKey *)v20);
  ATL::CRegKey::Close((ATL::CRegKey *)v21);
LABEL_24:
  v4 = (unsigned __int16 *)v6;
LABEL_25:
  free(v4);
LABEL_26:
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 12));
LABEL_27:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_28:
  ATL::CRegKey::Close((ATL::CRegKey *)v19);
}

```

## disassembly

```asm
0x14001cc50  mov     [rsp-8+arg_8], rbx
0x14001cc55  mov     [rsp-8+arg_10], rsi
0x14001cc5a  push    rbp
0x14001cc5b  push    rdi
0x14001cc5c  push    r14
0x14001cc5e  lea     rbp, [rsp-1F0h]
0x14001cc66  sub     rsp, 2F0h
0x14001cc6d  mov     rax, cs:__security_cookie
0x14001cc74  xor     rax, rsp
0x14001cc77  mov     [rbp+200h+var_20], rax
0x14001cc7e  mov     rdi, rcx
0x14001cc81  xor     r14d, r14d
0x14001cc84  mov     [rbp+200h+var_280], r14
0x14001cc88  mov     [rbp+200h+var_278], r14
0x14001cc8c  mov     [rbp+200h+var_270], r14
0x14001cc90  mov     ebx, 20019h
0x14001cc95  mov     r9d, ebx; unsigned int
0x14001cc98  lea     r8, aSoftwareMicros_15; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001cc9f  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14001cca6  lea     rcx, [rbp+200h+var_280]; this
0x14001ccaa  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001ccaf  test    eax, eax
0x14001ccb1  jnz     loc_14001CF37
0x14001ccb7  mov     [rsp+300h+hKey], r14
0x14001ccbc  mov     [rsp+300h+var_290], r14
0x14001ccc1  mov     [rsp+300h+var_288], r14
0x14001ccc6  mov     r9d, ebx; unsigned int
0x14001ccc9  mov     r8, [rdi+40h]; lpSubKey
0x14001cccd  mov     rdx, [rbp+200h+var_280]; hKey
0x14001ccd1  lea     rcx, [rsp+300h+hKey]; this
0x14001ccd6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001ccdb  test    eax, eax
0x14001ccdd  jnz     loc_14001CF2C
0x14001cce3  lea     rcx, [rsp+300h+var_2B0]
0x14001cce8  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14001cced  mov     [rsp+300h+var_2A0], r14
0x14001ccf2  mov     qword ptr [rsp+300h+Type], r14
0x14001ccf7  lea     r8, [rsp+300h+var_2A0]; unsigned __int64 *
0x14001ccfc  mov     r11d, 7FFFFFFFh
0x14001cd02  mov     edx, r11d; unsigned __int64
0x14001cd05  lea     rcx, aSAtconfig; "%s\\ATConfig"
0x14001cd0c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001cd11  test    eax, eax
0x14001cd13  js      loc_14001CF1D
0x14001cd19  lea     r8, [rsp+300h+Type]; unsigned __int64 *
0x14001cd1e  mov     edx, r11d; unsigned __int64
0x14001cd21  mov     rcx, [rsp+300h+var_2B0]; unsigned __int16 *
0x14001cd26  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001cd2b  test    eax, eax
0x14001cd2d  js      loc_14001CF1D
0x14001cd33  mov     rbx, qword ptr [rsp+300h+Type]
0x14001cd38  add     rbx, [rsp+300h+var_2A0]
0x14001cd3d  cmp     rbx, [rsp+300h+var_2A0]
0x14001cd42  jb      loc_14001CF1D
0x14001cd48  mov     qword ptr [rsp+300h+Type], r14
0x14001cd4d  mov     rdx, rbx
0x14001cd50  lea     rcx, [rsp+300h+Type]
0x14001cd55  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001cd5a  test    al, al
0x14001cd5c  jnz     short loc_14001CD68
0x14001cd5e  mov     rcx, qword ptr [rsp+300h+Type]
0x14001cd63  jmp     loc_14001CF17
0x14001cd68  mov     r9, [rsp+300h+var_2B0]
0x14001cd6d  lea     r8, aSAtconfig; "%s\\ATConfig"
0x14001cd74  mov     rdx, rbx; unsigned __int64
0x14001cd77  mov     rbx, qword ptr [rsp+300h+Type]
0x14001cd7c  mov     rcx, rbx; unsigned __int16 *
0x14001cd7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001cd84  test    eax, eax
0x14001cd86  js      loc_14001CF14
0x14001cd8c  mov     [rbp+200h+var_250], r14
0x14001cd90  mov     [rbp+200h+var_248], r14
0x14001cd94  mov     [rbp+200h+var_240], r14
0x14001cd98  mov     [rbp+200h+var_268], r14
0x14001cd9c  mov     [rbp+200h+var_260], r14
0x14001cda0  mov     [rbp+200h+var_258], r14
0x14001cda4  mov     esi, 2001Fh
0x14001cda9  mov     r9d, esi; unsigned int
0x14001cdac  mov     r8, rbx; lpSubKey
0x14001cdaf  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14001cdb6  lea     rcx, [rbp+200h+var_268]; this
0x14001cdba  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001cdbf  test    eax, eax
0x14001cdc1  jnz     loc_14001CF02
0x14001cdc7  lea     rax, [rsp+300h+Type]
0x14001cdcc  mov     [rsp+300h+lpcbData], rax; unsigned int *
0x14001cdd1  mov     dword ptr [rsp+300h+lpType], esi; REGSAM
0x14001cdd5  mov     dword ptr [rsp+300h+lpReserved], 1; DWORD
0x14001cddd  mov     r8, [rdi+40h]; lpSubKey
0x14001cde1  mov     rdx, [rbp+200h+var_268]; hKey
0x14001cde5  lea     rcx, [rbp+200h+var_250]; this
0x14001cde9  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14001cdee  test    eax, eax
0x14001cdf0  jnz     loc_14001CF02
0x14001cdf6  mov     esi, r14d
0x14001cdf9  mov     [rsp+300h+cchValueName], 104h
0x14001ce01  mov     [rsp+300h+Type], r14d
0x14001ce06  mov     [rsp+300h+cbData], r14d
0x14001ce0b  mov     rdi, r14
0x14001ce0e  mov     [rsp+300h+var_2A0], r14
0x14001ce13  lea     rax, [rsp+300h+cbData]
0x14001ce18  mov     [rsp+300h+lpcbData], rax; lpcbData
0x14001ce1d  mov     [rsp+300h+lpData], r14; lpData
0x14001ce22  lea     rax, [rsp+300h+Type]
0x14001ce27  mov     [rsp+300h+lpType], rax; lpType
0x14001ce2c  mov     [rsp+300h+lpReserved], r14; lpReserved
0x14001ce31  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x14001ce36  lea     r8, [rbp+200h+ValueName]; lpValueName
0x14001ce3a  mov     edx, esi; dwIndex
0x14001ce3c  mov     rcx, [rsp+300h+hKey]; hKey
0x14001ce41  call    cs:__imp_RegEnumValueW
0x14001ce47  test    eax, eax
0x14001ce49  jz      short loc_14001CE56
0x14001ce4b  cmp     eax, 0EAh
0x14001ce50  jnz     loc_14001CED6
0x14001ce56  mov     edx, [rsp+300h+cbData]
0x14001ce5a  lea     rcx, [rsp+300h+var_2A0]
0x14001ce5f  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001ce64  test    al, al
0x14001ce66  jz      loc_14001CEF7
0x14001ce6c  mov     [rsp+300h+cchValueName], 104h
0x14001ce74  lea     rax, [rsp+300h+cbData]
0x14001ce79  mov     [rsp+300h+lpcbData], rax; lpcbData
0x14001ce7e  mov     rdi, [rsp+300h+var_2A0]
0x14001ce83  mov     [rsp+300h+lpData], rdi; lpData
0x14001ce88  lea     rax, [rsp+300h+Type]
0x14001ce8d  mov     [rsp+300h+lpType], rax; lpType
0x14001ce92  mov     [rsp+300h+lpReserved], r14; lpReserved
0x14001ce97  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x14001ce9c  lea     r8, [rbp+200h+ValueName]; lpValueName
0x14001cea0  mov     edx, esi; dwIndex
0x14001cea2  mov     rcx, [rsp+300h+hKey]; hKey
0x14001cea7  call    cs:__imp_RegEnumValueW
0x14001cead  test    eax, eax
0x14001ceaf  jnz     short loc_14001CED6
0x14001ceb1  mov     eax, [rsp+300h+cbData]
0x14001ceb5  mov     dword ptr [rsp+300h+lpType], eax; cbData
0x14001ceb9  mov     [rsp+300h+lpReserved], rdi; lpData
0x14001cebe  mov     r9d, [rsp+300h+Type]; dwType
0x14001cec3  xor     r8d, r8d; Reserved
0x14001cec6  lea     rdx, [rbp+200h+ValueName]; lpValueName
0x14001ceca  mov     rcx, [rbp+200h+var_250]; hKey
0x14001cece  call    cs:__imp_RegSetValueExW
0x14001ced4  jmp     short loc_14001CEE2
0x14001ced6  cmp     eax, 103h
0x14001cedb  jz      short loc_14001CEF2
0x14001cedd  cmp     esi, 64h ; 'd'
0x14001cee0  ja      short loc_14001CEF2
0x14001cee2  inc     esi
0x14001cee4  mov     rcx, rdi; Block
0x14001cee7  call    cs:__imp_free
0x14001ceed  jmp     loc_14001CDF9
0x14001cef2  mov     rcx, rdi
0x14001cef5  jmp     short loc_14001CEFC
0x14001cef7  mov     rcx, [rsp+300h+var_2A0]; Block
0x14001cefc  call    cs:__imp_free
0x14001cf02  lea     rcx, [rbp+200h+var_268]; this
0x14001cf06  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001cf0b  lea     rcx, [rbp+200h+var_250]; this
0x14001cf0f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001cf14  mov     rcx, rbx; Block
0x14001cf17  call    cs:__imp_free
0x14001cf1d  mov     rcx, [rsp+300h+var_2B0]
0x14001cf22  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001cf26  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001cf2b  nop
0x14001cf2c  lea     rcx, [rsp+300h+hKey]; this
0x14001cf31  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001cf36  nop
0x14001cf37  lea     rcx, [rbp+200h+var_280]; this
0x14001cf3b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001cf40  mov     rcx, [rbp+200h+var_20]
0x14001cf47  xor     rcx, rsp; StackCookie
0x14001cf4a  call    __security_check_cookie
0x14001cf4f  lea     r11, [rsp+300h+var_10]
0x14001cf57  mov     rbx, [r11+28h]
0x14001cf5b  mov     rsi, [r11+30h]
0x14001cf5f  mov     rsp, r11
0x14001cf62  pop     r14
0x14001cf64  pop     rdi
0x14001cf65  pop     rbp
0x14001cf66  retn
```
