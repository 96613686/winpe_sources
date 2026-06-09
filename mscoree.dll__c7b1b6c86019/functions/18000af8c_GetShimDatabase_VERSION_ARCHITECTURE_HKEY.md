# GetShimDatabase(VERSION_ARCHITECTURE,HKEY__ * *)

- ea: `0x18000af8c`
- end: `0x18000b1bd`
- name: `?GetShimDatabase@@YAJW4VERSION_ARCHITECTURE@@PEAPEAUHKEY__@@@Z`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ac2c`

## callees

- `0x180003070`
- `0x180003ed0`
- `0x18000abd0`
- `0x18000aea8`
- `0x18000af8c`
- `0x18000b1c4`
- `0x18000b1f0`
- `0x180033604`
- `0x180041ac0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000b09d`
- `ADVAPI32!RegEnumKeyExW` at `0x18000b09d`

## string_xrefs

- `0x18000b16f`: `Unable to open shim database version registry key - %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetShimDatabase(unsigned int a1, __int64 a2)
{
  __int64 *v4; // rax
  int RegistryKey; // ebx
  WCHAR *v6; // rdi
  WCHAR *ConfigString; // rax
  DWORD v8; // esi
  DWORD i; // edx
  WCHAR *v10; // rax
  int v11; // r8d
  int v12; // ecx
  unsigned int v13; // eax
  WCHAR *v14; // rdx
  int v15; // ecx
  int v16; // eax
  WCHAR *v17; // rcx
  DWORD cchName[2]; // [rsp+40h] [rbp-69h] BYREF
  WCHAR *v20; // [rsp+48h] [rbp-61h] BYREF
  int v21; // [rsp+50h] [rbp-59h]
  HKEY hKey; // [rsp+58h] [rbp-51h] BYREF
  int v23; // [rsp+60h] [rbp-49h]
  WCHAR Name[28]; // [rsp+68h] [rbp-41h] BYREF
  __int16 v25; // [rsp+A0h] [rbp-9h] BYREF

  hKey = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  v25 = 0;
  Name[0] = 0;
  v4 = (__int64 *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                    &hKey,
                    cchName);
  RegistryKey = GetRegistryKey(
                  HKEY_LOCAL_MACHINE,
                  (__int64)L"Software\\Microsoft\\.NETFramework\\Policy\\AppPatch",
                  *v4,
                  a1);
  if ( **(_QWORD **)cchName )
    *(_DWORD *)(*(_QWORD *)cchName + 8LL) = 1;
  if ( !RegistryKey )
  {
    v6 = (WCHAR *)&v25;
    ConfigString = GetConfigString(L"ShimDatabaseVersion", 0, 0);
    v20 = ConfigString;
    if ( ConfigString )
    {
      v21 = 1;
      v17 = ConfigString;
    }
    else
    {
      v8 = 0;
      for ( i = 0; ; i = v8 )
      {
        cchName[0] = 25;
        v13 = RegEnumKeyExW(hKey, i, Name, cchName, 0, 0, 0, 0);
        RegistryKey = v13;
        if ( v13 )
          break;
        if ( !*v6 )
          goto LABEL_11;
        v10 = Name;
        do
        {
          v11 = *(WCHAR *)((char *)v10 + (char *)v6 - (char *)Name);
          v12 = *v10 - v11;
          if ( v12 )
            break;
          ++v10;
        }
        while ( v11 );
        if ( v12 > 0 )
LABEL_11:
          v6 = Name;
        ++v8;
      }
      if ( v13 != 259 )
      {
        ReportAppCompatError((wchar_t *)L"Error enumerating shim databases - %d", v13);
        if ( RegistryKey > 0 )
          RegistryKey = (unsigned __int16)RegistryKey | 0x80070000;
        goto LABEL_34;
      }
      if ( !*v6 )
        goto LABEL_26;
      v14 = v6;
      v15 = 0;
      do
      {
        if ( !*v14 )
          break;
        v16 = v15 + 1;
        if ( *v14 != 46 )
          v16 = v15;
        v15 = v16;
        ++v14;
      }
      while ( v16 <= 3 );
      if ( v15 != 3 )
      {
LABEL_26:
        ReportAppCompatError((wchar_t *)L"Error parsing shim database version - %s", v6);
        goto LABEL_27;
      }
      RegistryKey = VerifyRuntimeVersionIsOnMachine(v6, a1);
      if ( RegistryKey < 0 )
        goto LABEL_34;
      ConfigString = v6;
      v20 = v6;
      v21 = 0;
      v17 = v6;
    }
    if ( v17 )
    {
      RegistryKey = GetRegistryKey(hKey, (__int64)ConfigString, a2, a1);
      if ( RegistryKey )
        ReportAppCompatError((wchar_t *)L"Unable to open shim database version registry key - %s", v6);
      else
        RegistryKey = 0;
      goto LABEL_34;
    }
    ReportAppCompatError((wchar_t *)L"Unable to find a shim database version");
LABEL_27:
    RegistryKey = -2147467259;
  }
LABEL_34:
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v20);
  Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&hKey);
  return (unsigned int)RegistryKey;
}

```

## disassembly

```asm
0x18000af8c  mov     [rsp-8+arg_10], rbx
0x18000af91  mov     [rsp-8+arg_18], rsi
0x18000af96  push    rbp
0x18000af97  push    rdi
0x18000af98  push    r12
0x18000af9a  push    r14
0x18000af9c  push    r15
0x18000af9e  lea     rbp, [rsp-37h]
0x18000afa3  sub     rsp, 0E0h
0x18000afaa  mov     rax, cs:__security_cookie
0x18000afb1  xor     rax, rsp
0x18000afb4  mov     [rbp+57h+var_28], rax
0x18000afb8  mov     r15, rdx
0x18000afbb  mov     r14d, ecx
0x18000afbe  xor     r12d, r12d
0x18000afc1  mov     [rbp+57h+hKey], r12
0x18000afc5  mov     [rbp+57h+var_A0], r12d
0x18000afc9  mov     [rbp+57h+var_B8], r12
0x18000afcd  mov     [rbp+57h+var_B0], r12d
0x18000afd1  mov     [rbp+57h+var_60], r12w
0x18000afd6  mov     [rbp+57h+Name], r12w
0x18000afdb  lea     rdx, [rbp+57h+cchName]
0x18000afdf  lea     rcx, [rbp+57h+hKey]
0x18000afe3  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x18000afe8  mov     r9d, r14d
0x18000afeb  mov     r8, [rax]
0x18000afee  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\.NETFramework\\Pol"...
0x18000aff5  mov     rcx, 0FFFFFFFF80000002h
0x18000affc  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEAGPEAPEAU1@W4VERSION_ARCHITECTURE@@@Z; GetRegistryKey(HKEY__ *,ushort *,HKEY__ * *,VERSION_ARCHITECTURE)
0x18000b001  mov     ebx, eax
0x18000b003  mov     rax, qword ptr [rbp+57h+cchName]
0x18000b007  cmp     [rax], r12
0x18000b00a  jz      short loc_18000B013
0x18000b00c  mov     dword ptr [rax+8], 1
0x18000b013  test    ebx, ebx
0x18000b015  jnz     loc_18000B180
0x18000b01b  lea     rdi, [rbp+57h+var_60]
0x18000b01f  xor     r8d, r8d
0x18000b022  xor     edx, edx
0x18000b024  lea     rcx, aShimdatabaseve; "ShimDatabaseVersion"
0x18000b02b  call    ?GetConfigString@@YAPEAGPEBGHW4VERSION_ARCHITECTURE@@@Z; GetConfigString(ushort const *,int,VERSION_ARCHITECTURE)
0x18000b030  mov     [rbp+57h+var_B8], rax
0x18000b034  test    rax, rax
0x18000b037  jnz     loc_18000B137
0x18000b03d  mov     esi, r12d
0x18000b040  xor     edx, edx
0x18000b042  jmp     short loc_18000B076
0x18000b044  cmp     [rdi], r12w
0x18000b048  jz      short loc_18000B06E
0x18000b04a  lea     rax, [rbp+57h+Name]
0x18000b04e  mov     rdx, rdi
0x18000b051  sub     rdx, rax
0x18000b054  movzx   ecx, word ptr [rax]
0x18000b057  movzx   r8d, word ptr [rax+rdx]
0x18000b05c  sub     ecx, r8d
0x18000b05f  jnz     short loc_18000B06A
0x18000b061  add     rax, 2
0x18000b065  test    r8d, r8d
0x18000b068  jnz     short loc_18000B054
0x18000b06a  test    ecx, ecx
0x18000b06c  jle     short loc_18000B072
0x18000b06e  lea     rdi, [rbp+57h+Name]
0x18000b072  inc     esi
0x18000b074  mov     edx, esi; dwIndex
0x18000b076  mov     [rsp+100h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000b07b  mov     [rsp+100h+lpcchClass], r12; lpcchClass
0x18000b080  mov     [rsp+100h+lpClass], r12; lpClass
0x18000b085  mov     [rsp+100h+lpReserved], r12; lpReserved
0x18000b08a  mov     [rbp+57h+cchName], 19h
0x18000b091  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000b095  lea     r8, [rbp+57h+Name]; lpName
0x18000b099  mov     rcx, [rbp+57h+hKey]; hKey
0x18000b09d  call    cs:__imp_RegEnumKeyExW
0x18000b0a3  test    eax, eax
0x18000b0a5  mov     ebx, eax
0x18000b0a7  jz      short loc_18000B044
0x18000b0a9  cmp     eax, 103h
0x18000b0ae  jz      short loc_18000B0D4
0x18000b0b0  mov     edx, eax
0x18000b0b2  lea     rcx, aErrorEnumerati_0; "Error enumerating shim databases - %d"
0x18000b0b9  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x18000b0be  test    ebx, ebx
0x18000b0c0  jle     loc_18000B180
0x18000b0c6  movzx   ebx, bx
0x18000b0c9  or      ebx, 80070000h
0x18000b0cf  jmp     loc_18000B180
0x18000b0d4  cmp     [rdi], r12w
0x18000b0d8  jz      short loc_18000B121
0x18000b0da  mov     rdx, rdi
0x18000b0dd  mov     ecx, r12d
0x18000b0e0  cmp     [rdx], r12w
0x18000b0e4  jz      short loc_18000B0FB
0x18000b0e6  lea     eax, [rcx+1]
0x18000b0e9  cmp     word ptr [rdx], 2Eh ; '.'
0x18000b0ed  cmovnz  eax, ecx
0x18000b0f0  mov     ecx, eax
0x18000b0f2  add     rdx, 2
0x18000b0f6  cmp     eax, 3
0x18000b0f9  jle     short loc_18000B0E0
0x18000b0fb  cmp     ecx, 3
0x18000b0fe  jnz     short loc_18000B121
0x18000b100  mov     edx, r14d
0x18000b103  mov     rcx, rdi
0x18000b106  call    ?VerifyRuntimeVersionIsOnMachine@@YAJPEAGW4VERSION_ARCHITECTURE@@@Z; VerifyRuntimeVersionIsOnMachine(ushort *,VERSION_ARCHITECTURE)
0x18000b10b  mov     ebx, eax
0x18000b10d  test    eax, eax
0x18000b10f  js      short loc_18000B180
0x18000b111  mov     rax, rdi
0x18000b114  mov     [rbp+57h+var_B8], rax
0x18000b118  mov     [rbp+57h+var_B0], r12d
0x18000b11c  mov     rcx, rdi
0x18000b11f  jmp     short loc_18000B141
0x18000b121  mov     rdx, rdi
0x18000b124  lea     rcx, aErrorParsingSh; "Error parsing shim database version - %"...
0x18000b12b  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x18000b130  mov     ebx, 80004005h
0x18000b135  jmp     short loc_18000B180
0x18000b137  mov     [rbp+57h+var_B0], 1
0x18000b13e  mov     rcx, rax
0x18000b141  test    rcx, rcx
0x18000b144  jnz     short loc_18000B154
0x18000b146  lea     rcx, aUnableToFindAS; "Unable to find a shim database version"
0x18000b14d  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x18000b152  jmp     short loc_18000B130
0x18000b154  mov     r9d, r14d
0x18000b157  mov     r8, r15
0x18000b15a  mov     rdx, rax
0x18000b15d  mov     rcx, [rbp+57h+hKey]
0x18000b161  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEAGPEAPEAU1@W4VERSION_ARCHITECTURE@@@Z; GetRegistryKey(HKEY__ *,ushort *,HKEY__ * *,VERSION_ARCHITECTURE)
0x18000b166  mov     ebx, eax
0x18000b168  test    eax, eax
0x18000b16a  jz      short loc_18000B17D
0x18000b16c  mov     rdx, rdi
0x18000b16f  lea     rcx, aUnableToOpenSh; "Unable to open shim database version re"...
0x18000b176  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x18000b17b  jmp     short loc_18000B180
0x18000b17d  mov     ebx, r12d
0x18000b180  lea     rcx, [rbp+57h+var_B8]
0x18000b184  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18000b189  nop
0x18000b18a  lea     rcx, [rbp+57h+hKey]
0x18000b18e  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x18000b193  mov     eax, ebx
0x18000b195  mov     rcx, [rbp+57h+var_28]
0x18000b199  xor     rcx, rsp; StackCookie
0x18000b19c  call    __security_check_cookie
0x18000b1a1  lea     r11, [rsp+100h+var_20]
0x18000b1a9  mov     rbx, [r11+40h]
0x18000b1ad  mov     rsi, [r11+48h]
0x18000b1b1  mov     rsp, r11
0x18000b1b4  pop     r15
0x18000b1b6  pop     r14
0x18000b1b8  pop     r12
0x18000b1ba  pop     rdi
0x18000b1bb  pop     rbp
0x18000b1bc  retn
```
