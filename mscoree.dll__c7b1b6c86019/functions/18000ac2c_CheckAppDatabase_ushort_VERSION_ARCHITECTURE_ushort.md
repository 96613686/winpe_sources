# CheckAppDatabase(ushort *,VERSION_ARCHITECTURE,ushort * *)

- ea: `0x18000ac2c`
- end: `0x18000aea2`
- name: `?CheckAppDatabase@@YAJPEAGW4VERSION_ARCHITECTURE@@PEAPEAG@Z`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009af4`

## callees

- `0x18000aa50`
- `0x18000abd0`
- `0x18000ac2c`
- `0x18000aea8`
- `0x18000aee8`
- `0x18000af8c`
- `0x18000b1c4`
- `0x18000b1f0`
- `0x1800324d8`
- `0x1800325d4`
- `0x180033304`
- `0x180041ac0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000ad27`
- `ADVAPI32!RegEnumKeyExW` at `0x18000ad27`

## string_xrefs

- `0x18000ad90`: `Registry Keys`
- `0x18000ade0`: `Unable to read runtime version for %s - Error %d`
- `0x18000adec`: `Unable to open key %s - Error %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CheckAppDatabase(unsigned __int16 *a1, unsigned int a2, BYTE **a3)
{
  _QWORD *v5; // rax
  unsigned int ShimDatabase; // edi
  __int64 *v7; // rax
  DWORD i; // edi
  unsigned int v9; // eax
  __int64 *v10; // rax
  unsigned int RegistryKey; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v15; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+68h] [rbp-98h]
  HKEY v19; // [rsp+70h] [rbp-90h] BYREF
  int v20; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v21; // [rsp+80h] [rbp-80h] BYREF
  __int64 v22; // [rsp+88h] [rbp-78h]
  WCHAR Name[40]; // [rsp+F0h] [rbp-10h] BYREF

  if ( !a1 || !*a1 )
    return 1;
  v19 = 0;
  v20 = 0;
  hKey = 0;
  v18 = 0;
  cchName = 40;
  ApplicationIdentity::ApplicationIdentity((ApplicationIdentity *)&v21, a1);
  v5 = (_QWORD *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                   &v19,
                   &v14);
  ShimDatabase = GetShimDatabase(a2, *v5);
  if ( *(_QWORD *)v14 )
    *(_DWORD *)(v14 + 8) = 1;
  if ( ShimDatabase )
    goto LABEL_22;
  v7 = (__int64 *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                    &hKey,
                    &v14);
  ShimDatabase = GetRegistryKey(v19, v22, *v7, 0);
  if ( *(_QWORD *)v14 )
    *(_DWORD *)(v14 + 8) = 1;
  if ( ShimDatabase )
  {
LABEL_22:
    ApplicationIdentity::~ApplicationIdentity((ApplicationIdentity *)&v21);
    Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&hKey);
    Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&v19);
    return ShimDatabase;
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      v9 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v9 )
        break;
      v15 = 0;
      v16 = 0;
      v10 = (__int64 *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                         &v15,
                         &v14);
      RegistryKey = GetRegistryKey(hKey, (__int64)Name, *v10, 0);
      if ( *(_QWORD *)v14 )
        *(_DWORD *)(v14 + 8) = 1;
      if ( RegistryKey )
      {
        ReportAppCompatError((wchar_t *)L"Unable to open key %s - Error %x", Name, RegistryKey);
      }
      else if ( !(unsigned int)DoesThisAppMatch(&v21, v15)
             && !(unsigned int)HaveRelatedData(
                                 v15,
                                 L"Registry Keys",
                                 (int (*)(HKEY, struct ApplicationIdentity *))DoesThisRegKeyMatch,
                                 (struct ApplicationIdentity *)&v21)
             && !(unsigned int)HaveRelatedData(
                                 v15,
                                 L"Relative Files",
                                 (int (*)(HKEY, struct ApplicationIdentity *))DoesThisFileMatch,
                                 (struct ApplicationIdentity *)&v21) )
      {
        if ( !(unsigned int)GetRegistryStringValue(v15, L"Target Version", a3) )
        {
          Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&v15);
          ShimDatabase = 0;
          goto LABEL_22;
        }
        ReportAppCompatError(L"Unable to read runtime version for %s - Error %d", Name, 0);
      }
      cchName = 40;
      Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&v15);
    }
    if ( v9 != 259 )
      ReportAppCompatError((wchar_t *)L"Error enumerating app keys for %s - Error %d", v22, v9);
    ApplicationIdentity::~ApplicationIdentity((ApplicationIdentity *)&v21);
    Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&hKey);
    Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&v19);
    return 1;
  }
}

```

## disassembly

```asm
0x18000ac2c  push    rbp
0x18000ac2e  push    rbx
0x18000ac2f  push    rsi
0x18000ac30  push    rdi
0x18000ac31  push    r14
0x18000ac33  lea     rbp, [rsp-50h]
0x18000ac38  sub     rsp, 150h
0x18000ac3f  mov     rax, cs:__security_cookie
0x18000ac46  xor     rax, rsp
0x18000ac49  mov     [rbp+70h+var_30], rax
0x18000ac4d  mov     rsi, r8
0x18000ac50  mov     ebx, edx
0x18000ac52  xor     r14d, r14d
0x18000ac55  test    rcx, rcx
0x18000ac58  jz      loc_18000AE83
0x18000ac5e  cmp     [rcx], r14w
0x18000ac62  jz      loc_18000AE83
0x18000ac68  mov     [rsp+170h+var_100], r14
0x18000ac6d  mov     [rsp+170h+var_F8], r14d
0x18000ac72  mov     [rsp+170h+hKey], r14
0x18000ac77  mov     [rsp+170h+var_108], r14d
0x18000ac7c  mov     [rsp+170h+cchName], 28h ; '('
0x18000ac84  mov     rdx, rcx; unsigned __int16 *
0x18000ac87  lea     rcx, [rbp+70h+var_F0]; this
0x18000ac8b  call    ??0ApplicationIdentity@@QEAA@PEAG@Z; ApplicationIdentity::ApplicationIdentity(ushort *)
0x18000ac90  nop
0x18000ac91  lea     rdx, [rsp+170h+var_128]
0x18000ac96  lea     rcx, [rsp+170h+var_100]
0x18000ac9b  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x18000aca0  nop
0x18000aca1  mov     rdx, [rax]
0x18000aca4  mov     ecx, ebx
0x18000aca6  call    ?GetShimDatabase@@YAJW4VERSION_ARCHITECTURE@@PEAPEAUHKEY__@@@Z; GetShimDatabase(VERSION_ARCHITECTURE,HKEY__ * *)
0x18000acab  mov     edi, eax
0x18000acad  mov     rax, [rsp+170h+var_128]
0x18000acb2  lea     ebx, [r14+1]
0x18000acb6  cmp     [rax], r14
0x18000acb9  jz      short loc_18000ACBE
0x18000acbb  mov     [rax+8], ebx
0x18000acbe  test    edi, edi
0x18000acc0  jnz     loc_18000AE22
0x18000acc6  lea     rdx, [rsp+170h+var_128]
0x18000accb  lea     rcx, [rsp+170h+hKey]
0x18000acd0  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x18000acd5  xor     r9d, r9d
0x18000acd8  mov     r8, [rax]
0x18000acdb  mov     rdx, [rbp+70h+var_E8]
0x18000acdf  mov     rcx, [rsp+170h+var_100]
0x18000ace4  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEAGPEAPEAU1@W4VERSION_ARCHITECTURE@@@Z; GetRegistryKey(HKEY__ *,ushort *,HKEY__ * *,VERSION_ARCHITECTURE)
0x18000ace9  mov     edi, eax
0x18000aceb  mov     rax, [rsp+170h+var_128]
0x18000acf0  cmp     [rax], r14
0x18000acf3  jz      short loc_18000ACF8
0x18000acf5  mov     [rax+8], ebx
0x18000acf8  test    edi, edi
0x18000acfa  jnz     loc_18000AE22
0x18000ad00  mov     edi, r14d
0x18000ad03  mov     [rsp+170h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000ad08  mov     [rsp+170h+lpcchClass], r14; lpcchClass
0x18000ad0d  mov     [rsp+170h+lpClass], r14; lpClass
0x18000ad12  mov     [rsp+170h+lpReserved], r14; lpReserved
0x18000ad17  lea     r9, [rsp+170h+cchName]; lpcchName
0x18000ad1c  lea     r8, [rbp+70h+Name]; lpName
0x18000ad20  mov     edx, edi; dwIndex
0x18000ad22  mov     rcx, [rsp+170h+hKey]; hKey
0x18000ad27  call    cs:__imp_RegEnumKeyExW
0x18000ad2d  test    eax, eax
0x18000ad2f  jnz     loc_18000AE45
0x18000ad35  mov     [rsp+170h+var_120], r14
0x18000ad3a  mov     [rsp+170h+var_118], r14d
0x18000ad3f  lea     rdx, [rsp+170h+var_128]
0x18000ad44  lea     rcx, [rsp+170h+var_120]
0x18000ad49  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x18000ad4e  xor     r9d, r9d
0x18000ad51  mov     r8, [rax]
0x18000ad54  lea     rdx, [rbp+70h+Name]
0x18000ad58  mov     rcx, [rsp+170h+hKey]
0x18000ad5d  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEAGPEAPEAU1@W4VERSION_ARCHITECTURE@@@Z; GetRegistryKey(HKEY__ *,ushort *,HKEY__ * *,VERSION_ARCHITECTURE)
0x18000ad62  mov     rcx, [rsp+170h+var_128]
0x18000ad67  cmp     [rcx], r14
0x18000ad6a  jz      short loc_18000AD6F
0x18000ad6c  mov     [rcx+8], ebx
0x18000ad6f  test    eax, eax
0x18000ad71  jnz     short loc_18000ADE9
0x18000ad73  mov     rdx, [rsp+170h+var_120]; hKey
0x18000ad78  lea     rcx, [rbp+70h+var_F0]; this
0x18000ad7c  call    ?DoesThisAppMatch@@YAJPEAVApplicationIdentity@@PEAUHKEY__@@@Z; DoesThisAppMatch(ApplicationIdentity *,HKEY__ *)
0x18000ad81  test    eax, eax
0x18000ad83  jnz     short loc_18000ADFC
0x18000ad85  lea     r9, [rbp+70h+var_F0]; struct ApplicationIdentity *
0x18000ad89  lea     r8, ?DoesThisRegKeyMatch@@YAHPEAUHKEY__@@PEAVApplicationIdentity@@@Z; int (*)(HKEY, struct ApplicationIdentity *)
0x18000ad90  lea     rdx, aRegistryKeys; "Registry Keys"
0x18000ad97  mov     rcx, [rsp+170h+var_120]; HKEY
0x18000ad9c  call    ?HaveRelatedData@@YAJPEAUHKEY__@@PEAGP6AH0PEAVApplicationIdentity@@@Z2@Z; HaveRelatedData(HKEY__ *,ushort *,int (*)(HKEY__ *,ApplicationIdentity *),ApplicationIdentity *)
0x18000ada1  test    eax, eax
0x18000ada3  jnz     short loc_18000ADFC
0x18000ada5  lea     r9, [rbp+70h+var_F0]; struct ApplicationIdentity *
0x18000ada9  lea     r8, ?DoesThisFileMatch@@YAHPEAUHKEY__@@PEAVApplicationIdentity@@@Z; int (*)(HKEY, struct ApplicationIdentity *)
0x18000adb0  lea     rdx, aRelativeFiles; "Relative Files"
0x18000adb7  mov     rcx, [rsp+170h+var_120]; HKEY
0x18000adbc  call    ?HaveRelatedData@@YAJPEAUHKEY__@@PEAGP6AH0PEAVApplicationIdentity@@@Z2@Z; HaveRelatedData(HKEY__ *,ushort *,int (*)(HKEY__ *,ApplicationIdentity *),ApplicationIdentity *)
0x18000adc1  test    eax, eax
0x18000adc3  jnz     short loc_18000ADFC
0x18000adc5  mov     r8, rsi; unsigned __int16 **
0x18000adc8  lea     rdx, aTargetVersion; "Target Version"
0x18000adcf  mov     rcx, [rsp+170h+var_120]; hKey
0x18000add4  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort *,ushort * *)
0x18000add9  test    eax, eax
0x18000addb  jz      short loc_18000AE15
0x18000addd  xor     r8d, r8d
0x18000ade0  lea     rcx, aUnableToReadRu; "Unable to read runtime version for %s -"...
0x18000ade7  jmp     short loc_18000ADF3
0x18000ade9  mov     r8d, eax
0x18000adec  lea     rcx, aUnableToOpenKe; "Unable to open key %s - Error %x"
0x18000adf3  lea     rdx, [rbp+70h+Name]
0x18000adf7  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x18000adfc  add     edi, ebx
0x18000adfe  mov     [rsp+170h+cchName], 28h ; '('
0x18000ae06  lea     rcx, [rsp+170h+var_120]
0x18000ae0b  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x18000ae10  jmp     loc_18000AD03
0x18000ae15  lea     rcx, [rsp+170h+var_120]
0x18000ae1a  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x18000ae1f  mov     edi, r14d
0x18000ae22  lea     rcx, [rbp+70h+var_F0]; this
0x18000ae26  call    ??1ApplicationIdentity@@QEAA@XZ; ApplicationIdentity::~ApplicationIdentity(void)
0x18000ae2b  nop
0x18000ae2c  lea     rcx, [rsp+170h+hKey]
0x18000ae31  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x18000ae36  nop
0x18000ae37  lea     rcx, [rsp+170h+var_100]
0x18000ae3c  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x18000ae41  mov     eax, edi
0x18000ae43  jmp     short loc_18000AE88
0x18000ae45  cmp     eax, 103h
0x18000ae4a  jz      short loc_18000AE60
0x18000ae4c  mov     r8d, eax
0x18000ae4f  mov     rdx, [rbp+70h+var_E8]
0x18000ae53  lea     rcx, aErrorEnumerati; "Error enumerating app keys for %s - Err"...
0x18000ae5a  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x18000ae5f  nop
0x18000ae60  lea     rcx, [rbp+70h+var_F0]; this
0x18000ae64  call    ??1ApplicationIdentity@@QEAA@XZ; ApplicationIdentity::~ApplicationIdentity(void)
0x18000ae69  nop
0x18000ae6a  lea     rcx, [rsp+170h+hKey]
0x18000ae6f  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x18000ae74  nop
0x18000ae75  lea     rcx, [rsp+170h+var_100]
0x18000ae7a  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x18000ae7f  mov     eax, ebx
0x18000ae81  jmp     short loc_18000AE88
0x18000ae83  mov     eax, 1
0x18000ae88  mov     rcx, [rbp+70h+var_30]
0x18000ae8c  xor     rcx, rsp; StackCookie
0x18000ae8f  call    __security_check_cookie
0x18000ae94  add     rsp, 150h
0x18000ae9b  pop     r14
0x18000ae9d  pop     rdi
0x18000ae9e  pop     rsi
0x18000ae9f  pop     rbx
0x18000aea0  pop     rbp
0x18000aea1  retn
```
