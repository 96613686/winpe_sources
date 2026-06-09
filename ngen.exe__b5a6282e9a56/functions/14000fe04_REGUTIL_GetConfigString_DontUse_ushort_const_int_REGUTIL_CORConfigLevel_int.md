# REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)

- ea: `0x14000fe04`
- end: `0x140010174`
- name: `?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z`
- size: `880`
- prototype: `unsigned __int16 *__fastcall(wchar_t *, int, char, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008ed0`
- `0x14000a610`
- `0x140010454`

## callees

- `0x14000a0d4`
- `0x14000edb8`
- `0x14000fad4`
- `0x14000fe04`
- `0x140010174`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000fea6`
- `KERNEL32!HeapFree` at `0x14000fea6`
- `KERNEL32!GetProcessHeap` at `0x14000fe91`
- `KERNEL32!GetProcessHeap` at `0x14000fe91`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ff13`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ffc6`
- `ADVAPI32!RegOpenKeyExW` at `0x140010075`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ff13`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ffc6`
- `ADVAPI32!RegOpenKeyExW` at `0x140010075`
- `ADVAPI32!RegCloseKey` at `0x14001011e`
- `ADVAPI32!RegCloseKey` at `0x140010132`
- `ADVAPI32!RegCloseKey` at `0x140010146`
- `ADVAPI32!RegCloseKey` at `0x14001011e`
- `ADVAPI32!RegCloseKey` at `0x140010132`
- `ADVAPI32!RegCloseKey` at `0x140010146`
- `ADVAPI32!RegQueryValueExW` at `0x14000ff54`
- `ADVAPI32!RegQueryValueExW` at `0x14001000a`
- `ADVAPI32!RegQueryValueExW` at `0x14001009b`
- `ADVAPI32!RegQueryValueExW` at `0x140010105`
- `ADVAPI32!RegQueryValueExW` at `0x14000ff54`
- `ADVAPI32!RegQueryValueExW` at `0x14001000a`
- `ADVAPI32!RegQueryValueExW` at `0x14001009b`
- `ADVAPI32!RegQueryValueExW` at `0x140010105`

## pseudocode

```c
unsigned __int16 *__fastcall REGUTIL::GetConfigString_DontUse_(wchar_t *a1, int a2, char a3, int a4)
{
  unsigned __int16 *v7; // rbx
  unsigned __int16 *String; // rax
  HANDLE ProcessHeap; // rax
  PHKEY *v10; // rax
  bool v11; // cl
  const struct NoThrow *v12; // rdx
  unsigned __int16 *v13; // rax
  HKEY v14; // rcx
  PHKEY *v15; // rax
  bool v16; // cl
  const struct NoThrow *v17; // rdx
  unsigned __int16 *v18; // rax
  PHKEY *v19; // rax
  const struct NoThrow *v20; // rdx
  char v21; // cl
  unsigned __int16 *v22; // rax
  DWORD Type; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-40h]
  int v27; // [rsp+48h] [rbp-38h]
  HKEY v28; // [rsp+50h] [rbp-30h] BYREF
  int v29; // [rsp+58h] [rbp-28h]
  HKEY v30; // [rsp+60h] [rbp-20h] BYREF
  int v31; // [rsp+68h] [rbp-18h]
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF
  int v33; // [rsp+78h] [rbp-8h]
  DWORD cbData; // [rsp+C0h] [rbp+40h] BYREF

  hKey = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v29 = 0;
  v7 = 0;
  v26 = 0;
  v27 = 0;
  if ( (a3 & 1) != 0 )
  {
    String = REGUTIL::EnvGetString(a1, a2);
    v7 = String;
    v26 = String;
    if ( String )
    {
      v27 = 1;
      if ( *String )
      {
LABEL_37:
        v27 = 0;
        goto LABEL_39;
      }
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v7);
      v27 = 0;
      v7 = 0;
      v26 = 0;
    }
  }
  if ( (a3 & 0xE) != 0 && (!a4 || (unsigned int)REGUTIL::RegCacheValueNameSeenPerhaps(a1)) )
  {
    if ( (a3 & 2) != 0 )
    {
      v10 = (PHKEY *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                       (__int64)&hKey,
                       &v25);
      v11 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, *v10) == 0;
      if ( *(_QWORD *)v25 )
        *(_DWORD *)(v25 + 8) = 1;
      if ( v11 && !RegQueryValueExW(hKey, a1, 0, &Type, 0, &cbData) && Type == 1 )
      {
        v13 = (unsigned __int16 *)operator new[](cbData, v12);
        v7 = v13;
        v26 = v13;
        if ( !v13 )
          goto LABEL_39;
        *v13 = 0;
        v14 = hKey;
        goto LABEL_36;
      }
    }
    if ( (a3 & 4) != 0 )
    {
      v15 = (PHKEY *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                       (__int64)&v30,
                       &v25);
      v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, *v15) == 0;
      if ( *(_QWORD *)v25 )
        *(_DWORD *)(v25 + 8) = 1;
      if ( v16 && !RegQueryValueExW(v30, a1, 0, &Type, 0, &cbData) && Type == 1 )
      {
        v18 = (unsigned __int16 *)operator new[](cbData, v17);
        v7 = v18;
        v26 = v18;
        if ( !v18 )
          goto LABEL_39;
        *v18 = 0;
        v14 = v30;
        goto LABEL_36;
      }
    }
    if ( (a3 & 8) != 0 )
    {
      v19 = (PHKEY *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                       (__int64)&v28,
                       &v25);
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fusion", 0, 0x20019u, *v19)
        || RegQueryValueExW(v28, a1, 0, &Type, 0, &cbData)
        || (v21 = 1, Type != 1) )
      {
        v21 = 0;
      }
      if ( *(_QWORD *)v25 )
        *(_DWORD *)(v25 + 8) = 1;
      if ( v21 )
      {
        v22 = (unsigned __int16 *)operator new[](cbData, v20);
        v7 = v22;
        v26 = v22;
        if ( v22 )
        {
          *v22 = 0;
          v14 = v28;
LABEL_36:
          v27 = 1;
          RegQueryValueExW(v14, a1, 0, 0, (LPBYTE)v7, &cbData);
          goto LABEL_37;
        }
      }
    }
    v7 = 0;
  }
LABEL_39:
  if ( v29 )
  {
    RegCloseKey(v28);
    v29 = 0;
  }
  if ( v31 )
  {
    RegCloseKey(v30);
    v31 = 0;
  }
  if ( v33 )
  {
    RegCloseKey(hKey);
    v33 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x14000fe04  mov     [rsp-28h+arg_0], rbx
0x14000fe09  mov     [rsp-28h+arg_8], rsi
0x14000fe0e  mov     [rsp-28h+arg_18], rdi
0x14000fe13  push    rbp
0x14000fe14  push    r12
0x14000fe16  push    r13
0x14000fe18  push    r14
0x14000fe1a  push    r15
0x14000fe1c  mov     rbp, rsp
0x14000fe1f  sub     rsp, 80h
0x14000fe26  mov     r15d, r9d
0x14000fe29  mov     r14d, r8d
0x14000fe2c  mov     rsi, rcx
0x14000fe2f  xor     r12d, r12d
0x14000fe32  mov     edi, r12d
0x14000fe35  mov     [rbp+var_50], r12d
0x14000fe39  mov     [rbp+hKey], r12
0x14000fe3d  mov     [rbp+var_8], r12d
0x14000fe41  mov     [rbp+var_20], r12
0x14000fe45  mov     [rbp+var_18], r12d
0x14000fe49  mov     [rbp+var_30], r12
0x14000fe4d  mov     [rbp+var_28], r12d
0x14000fe51  mov     ebx, r12d
0x14000fe54  mov     [rbp+var_40], rbx
0x14000fe58  mov     [rbp+var_38], r12d
0x14000fe5c  lea     r13d, [r12+1]
0x14000fe61  test    r13b, r8b
0x14000fe64  jz      short loc_14000FEB7
0x14000fe66  call    ?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z; REGUTIL::EnvGetString(ushort const *,int)
0x14000fe6b  mov     rbx, rax
0x14000fe6e  mov     [rbp+var_40], rax
0x14000fe72  test    rax, rax
0x14000fe75  jz      short loc_14000FEB7
0x14000fe77  mov     [rbp+var_38], r13d
0x14000fe7b  cmp     [rax], r12w
0x14000fe7f  jnz     loc_14001010B
0x14000fe85  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000fe8c  test    rax, rax
0x14000fe8f  jnz     short loc_14000FE9E
0x14000fe91  call    cs:__imp_GetProcessHeap
0x14000fe97  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000fe9e  mov     r8, rbx; lpMem
0x14000fea1  xor     edx, edx; dwFlags
0x14000fea3  mov     rcx, rax; hHeap
0x14000fea6  call    cs:__imp_HeapFree
0x14000feac  mov     [rbp+var_38], r12d
0x14000feb0  mov     rbx, r12
0x14000feb3  mov     [rbp+var_40], rbx
0x14000feb7  test    r14b, 0Eh
0x14000febb  jz      loc_140010114
0x14000fec1  test    r15d, r15d
0x14000fec4  jz      short loc_14000FED6
0x14000fec6  mov     rcx, rsi; unsigned __int16 *
0x14000fec9  call    ?RegCacheValueNameSeenPerhaps@REGUTIL@@CAHPEBG@Z; REGUTIL::RegCacheValueNameSeenPerhaps(ushort const *)
0x14000fece  test    eax, eax
0x14000fed0  jz      loc_140010114
0x14000fed6  mov     ebx, 20019h
0x14000fedb  test    r14b, 2
0x14000fedf  jz      loc_14000FF89
0x14000fee5  lea     rdx, [rbp+var_48]
0x14000fee9  lea     rcx, [rbp+hKey]
0x14000feed  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x14000fef2  nop
0x14000fef3  mov     [rbp+var_50], r13d
0x14000fef7  mov     rax, [rax]
0x14000fefa  mov     [rsp+80h+phkResult], rax; phkResult
0x14000feff  mov     r9d, ebx; samDesired
0x14000ff02  xor     r8d, r8d; ulOptions
0x14000ff05  lea     rdx, SubKey; "Software\\Microsoft\\.NETFramework"
0x14000ff0c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000ff13  call    cs:__imp_RegOpenKeyExW
0x14000ff19  test    eax, eax
0x14000ff1b  setz    cl
0x14000ff1e  mov     edi, r13d
0x14000ff21  and     edi, 0FFFFFFFEh
0x14000ff24  mov     [rbp+var_50], edi
0x14000ff27  mov     rax, [rbp+var_48]
0x14000ff2b  cmp     [rax], r12
0x14000ff2e  jz      short loc_14000FF34
0x14000ff30  mov     [rax+8], r13d
0x14000ff34  test    cl, cl
0x14000ff36  jz      short loc_14000FF89
0x14000ff38  lea     rax, [rbp+cbData]
0x14000ff3c  mov     [rsp+80h+lpcbData], rax; lpcbData
0x14000ff41  mov     [rsp+80h+phkResult], r12; lpData
0x14000ff46  lea     r9, [rbp+Type]; lpType
0x14000ff4a  xor     r8d, r8d; lpReserved
0x14000ff4d  mov     rdx, rsi; lpValueName
0x14000ff50  mov     rcx, [rbp+hKey]; hKey
0x14000ff54  call    cs:__imp_RegQueryValueExW
0x14000ff5a  test    eax, eax
0x14000ff5c  jnz     short loc_14000FF89
0x14000ff5e  cmp     [rbp+Type], r13d
0x14000ff62  jnz     short loc_14000FF89
0x14000ff64  mov     ecx, [rbp+cbData]; dwBytes
0x14000ff67  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x14000ff6c  mov     rbx, rax
0x14000ff6f  mov     [rbp+var_40], rax
0x14000ff73  test    rax, rax
0x14000ff76  jz      loc_140010114
0x14000ff7c  mov     [rax], r12w
0x14000ff80  mov     rcx, [rbp+hKey]
0x14000ff84  jmp     loc_1400100EA
0x14000ff89  mov     r15, 0FFFFFFFF80000002h
0x14000ff90  test    r14b, 4
0x14000ff94  jz      loc_14001003F
0x14000ff9a  lea     rdx, [rbp+var_48]
0x14000ff9e  lea     rcx, [rbp+var_20]
0x14000ffa2  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x14000ffa7  nop
0x14000ffa8  or      edi, 2
0x14000ffab  mov     [rbp+var_50], edi
0x14000ffae  mov     rax, [rax]
0x14000ffb1  mov     [rsp+80h+phkResult], rax; phkResult
0x14000ffb6  mov     r9d, ebx; samDesired
0x14000ffb9  xor     r8d, r8d; ulOptions
0x14000ffbc  lea     rdx, SubKey; "Software\\Microsoft\\.NETFramework"
0x14000ffc3  mov     rcx, r15; hKey
0x14000ffc6  call    cs:__imp_RegOpenKeyExW
0x14000ffcc  test    eax, eax
0x14000ffce  setz    cl
0x14000ffd1  test    dil, 2
0x14000ffd5  jz      short loc_14000FFEA
0x14000ffd7  and     edi, 0FFFFFFFDh
0x14000ffda  mov     [rbp+var_50], edi
0x14000ffdd  mov     rax, [rbp+var_48]
0x14000ffe1  cmp     [rax], r12
0x14000ffe4  jz      short loc_14000FFEA
0x14000ffe6  mov     [rax+8], r13d
0x14000ffea  test    cl, cl
0x14000ffec  jz      short loc_14001003F
0x14000ffee  lea     rax, [rbp+cbData]
0x14000fff2  mov     [rsp+80h+lpcbData], rax; lpcbData
0x14000fff7  mov     [rsp+80h+phkResult], r12; lpData
0x14000fffc  lea     r9, [rbp+Type]; lpType
0x140010000  xor     r8d, r8d; lpReserved
0x140010003  mov     rdx, rsi; lpValueName
0x140010006  mov     rcx, [rbp+var_20]; hKey
0x14001000a  call    cs:__imp_RegQueryValueExW
0x140010010  test    eax, eax
0x140010012  jnz     short loc_14001003F
0x140010014  cmp     [rbp+Type], r13d
0x140010018  jnz     short loc_14001003F
0x14001001a  mov     ecx, [rbp+cbData]; dwBytes
0x14001001d  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x140010022  mov     rbx, rax
0x140010025  mov     [rbp+var_40], rax
0x140010029  test    rax, rax
0x14001002c  jz      loc_140010114
0x140010032  mov     [rax], r12w
0x140010036  mov     rcx, [rbp+var_20]
0x14001003a  jmp     loc_1400100EA
0x14001003f  test    r14b, 8
0x140010043  jz      loc_140010111
0x140010049  lea     rdx, [rbp+var_48]
0x14001004d  lea     rcx, [rbp+var_30]
0x140010051  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x140010056  nop
0x140010057  or      edi, 4
0x14001005a  mov     [rbp+var_50], edi
0x14001005d  mov     rax, [rax]
0x140010060  mov     [rsp+80h+phkResult], rax; phkResult
0x140010065  mov     r9d, ebx; samDesired
0x140010068  xor     r8d, r8d; ulOptions
0x14001006b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fusion"
0x140010072  mov     rcx, r15; hKey
0x140010075  call    cs:__imp_RegOpenKeyExW
0x14001007b  test    eax, eax
0x14001007d  jnz     short loc_1400100AE
0x14001007f  lea     rax, [rbp+cbData]
0x140010083  mov     [rsp+80h+lpcbData], rax; lpcbData
0x140010088  mov     [rsp+80h+phkResult], r12; lpData
0x14001008d  lea     r9, [rbp+Type]; lpType
0x140010091  xor     r8d, r8d; lpReserved
0x140010094  mov     rdx, rsi; lpValueName
0x140010097  mov     rcx, [rbp+var_30]; hKey
0x14001009b  call    cs:__imp_RegQueryValueExW
0x1400100a1  test    eax, eax
0x1400100a3  jnz     short loc_1400100AE
0x1400100a5  cmp     [rbp+Type], r13d
0x1400100a9  mov     cl, r13b
0x1400100ac  jz      short loc_1400100B1
0x1400100ae  mov     cl, r12b
0x1400100b1  test    dil, 4
0x1400100b5  jz      short loc_1400100CA
0x1400100b7  and     edi, 0FFFFFFFBh
0x1400100ba  mov     [rbp+var_50], edi
0x1400100bd  mov     rax, [rbp+var_48]
0x1400100c1  cmp     [rax], r12
0x1400100c4  jz      short loc_1400100CA
0x1400100c6  mov     [rax+8], r13d
0x1400100ca  test    cl, cl
0x1400100cc  jz      short loc_140010111
0x1400100ce  mov     ecx, [rbp+cbData]; dwBytes
0x1400100d1  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x1400100d6  mov     rbx, rax
0x1400100d9  mov     [rbp+var_40], rax
0x1400100dd  test    rax, rax
0x1400100e0  jz      short loc_140010111
0x1400100e2  mov     [rax], r12w
0x1400100e6  mov     rcx, [rbp+var_30]; hKey
0x1400100ea  lea     rax, [rbp+cbData]
0x1400100ee  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1400100f3  xor     r9d, r9d; lpType
0x1400100f6  mov     [rbp+var_38], r13d
0x1400100fa  mov     [rsp+80h+phkResult], rbx; lpData
0x1400100ff  xor     r8d, r8d; lpReserved
0x140010102  mov     rdx, rsi; lpValueName
0x140010105  call    cs:__imp_RegQueryValueExW
0x14001010b  mov     [rbp+var_38], r12d
0x14001010f  jmp     short loc_140010114
0x140010111  mov     rbx, r12
0x140010114  cmp     [rbp+var_28], r12d
0x140010118  jz      short loc_140010128
0x14001011a  mov     rcx, [rbp+var_30]; hKey
0x14001011e  call    cs:__imp_RegCloseKey
0x140010124  mov     [rbp+var_28], r12d
0x140010128  cmp     [rbp+var_18], r12d
0x14001012c  jz      short loc_14001013C
0x14001012e  mov     rcx, [rbp+var_20]; hKey
0x140010132  call    cs:__imp_RegCloseKey
0x140010138  mov     [rbp+var_18], r12d
0x14001013c  cmp     [rbp+var_8], r12d
0x140010140  jz      short loc_140010150
0x140010142  mov     rcx, [rbp+hKey]; hKey
0x140010146  call    cs:__imp_RegCloseKey
0x14001014c  mov     [rbp+var_8], r12d
0x140010150  mov     rax, rbx
0x140010153  lea     r11, [rsp+80h+var_s0]
0x14001015b  mov     rbx, [r11+30h]
0x14001015f  mov     rsi, [r11+38h]
0x140010163  mov     rdi, [r11+48h]
0x140010167  mov     rsp, r11
0x14001016a  pop     r15
0x14001016c  pop     r14
0x14001016e  pop     r13
0x140010170  pop     r12
0x140010172  pop     rbp
0x140010173  retn
```
