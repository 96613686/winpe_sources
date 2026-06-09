# RtlpSetInstallLanguage

- ea: `0x180142c30`
- end: `0x1801430f3`
- name: `RtlpSetInstallLanguage`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180143270`

## callees

- `0x180009d60`
- `0x18000b730`
- `0x180011c70`
- `0x180071890`
- `0x1800c4700`
- `0x1800da250`
- `0x1800dbb98`
- `0x180111684`
- `0x180142804`
- `0x180142968`
- `0x180142b2c`
- `0x180142c30`
- `0x180143270`
- `0x18015ecc0`
- `0x180160650`
- `0x1801606b0`
- `0x1801608b0`
- `0x180160c30`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x180142fce`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings\LanguageConfiguration`
- `0x180143022`: `Control Panel\Desktop\MuiCached`
- `0x180142f1b`: `\Registry\Machine\System\CurrentControlSet\Control\NLS\Language`
- `0x180142f44`: `InstallLanguageFallback`
- `0x180142f77`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`
- `0x18014306c`: `MachineLanguageConfiguration`

## pseudocode

```c
__int64 __fastcall RtlpSetInstallLanguage(char a1, const WCHAR *a2)
{
  WCHAR *v2; // rdi
  int InstalledLanguageType; // ebx
  char v4; // r14
  char v5; // r15
  _BYTE *v6; // rdi
  __int64 v7; // rdx
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v10; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v13; // [rsp+68h] [rbp-98h] BYREF
  int v14; // [rsp+70h] [rbp-90h] BYREF
  __int64 v15; // [rsp+78h] [rbp-88h] BYREF
  HANDLE v16; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING v17; // [rsp+88h] [rbp-78h] BYREF
  _BYTE *v18; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SourceString[88]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v21[176]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v22[352]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v23[528]; // [rsp+370h] [rbp+270h] BYREF

  Handle = 0;
  v16 = 0;
  v10 = 0;
  v2 = (WCHAR *)a2;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v18 = 0;
  v17 = 0;
  DestinationString = 0;
  v11 = 0;
  if ( !a2 )
    return (unsigned int)-1073741811;
  if ( (a1 & 4) != 0 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    InstalledLanguageType = RtlUnicodeStringToLcid(&DestinationString, &v10);
    if ( InstalledLanguageType < 0 )
      return (unsigned int)InstalledLanguageType;
    v17.Buffer = SourceString;
    v17.MaximumLength = 172;
    if ( !(unsigned __int8)RtlLCIDToCultureName(v10, &v17) )
      return (unsigned int)-1073741811;
    v2 = SourceString;
  }
  else
  {
    if ( (a1 & 8) == 0 )
      return (unsigned int)-1073741811;
    RtlInitUnicodeString(&v17, a2);
    if ( !(unsigned __int8)RtlCultureNameToLCID(&v17, &v10) )
      return (unsigned int)-1073741811;
  }
  InstalledLanguageType = RtlpCreateProcessRegistryInfo(&v13);
  if ( InstalledLanguageType < 0 )
    return (unsigned int)InstalledLanguageType;
  if ( !v13 )
    return (unsigned int)-1073741823;
  InstalledLanguageType = RtlpGetInstalledLanguageType(v13, v2, &v14, &v15);
  if ( InstalledLanguageType < 0 )
    return (unsigned int)InstalledLanguageType;
  v4 = 0;
  v5 = 0;
  if ( v14 == 1 )
  {
LABEL_23:
    RtlInitUnicodeString(&v17, v2);
    if ( (unsigned __int8)RtlCultureNameToLCID(&v17, &v10) )
    {
      InstalledLanguageType = NtFlushInstallUILanguage((unsigned __int16)v10, 0);
      if ( InstalledLanguageType >= 0 )
      {
        if ( v4 )
        {
          RtlpSetPreferredUILanguages(1032, v23, &v12);
        }
        else
        {
          RtlInitUnicodeString(&v11, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\NLS\\Language");
          if ( (int)LdrpOpenKey(&v11, 0, 983103, &Handle) >= 0 )
          {
            RtlInitUnicodeString(&v11, L"InstallLanguageFallback");
            ZwDeleteValueKey(Handle, &v11);
            NtClose(Handle);
          }
        }
        if ( v5 )
        {
          RtlpSetPreferredUILanguages(32776, v21, &v12);
          RtlpSetPreferredUILanguages(36872, v22, &v12);
        }
        else
        {
          RtlInitUnicodeString(&v11, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings");
          if ( (int)LdrpOpenKey(&v11, 0, 983103, &Handle) >= 0 )
          {
            RtlInitUnicodeString(&v11, L"PreferredUILanguages");
            ZwDeleteValueKey(Handle, &v11);
            NtClose(Handle);
            RtlInitUnicodeString(
              &v11,
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings\\LanguageConfiguration");
            if ( (int)LdrpOpenKey(&v11, 0, 983103, &Handle) >= 0 )
            {
              NtDeleteKey(Handle);
              NtClose(Handle);
            }
            if ( (int)OpenGlobalizationUserSettingsKey(0x2000000, v7, &Handle) >= 0 )
            {
              RtlInitUnicodeString(&v11, L"Control Panel\\Desktop\\MuiCached");
              if ( (int)LdrpOpenKey(&v11, Handle, 983103, &v16) >= 0 )
              {
                RtlInitUnicodeString(&v11, L"MachinePreferredUILanguages");
                ZwDeleteValueKey(v16, &v11);
                RtlInitUnicodeString(&v11, L"MachineLanguageConfiguration");
                ZwDeleteValueKey(v16, &v11);
                NtClose(v16);
              }
              NtClose(Handle);
            }
          }
        }
      }
      else if ( (unsigned int)NtIsUILanguageComitted() )
      {
        return (unsigned int)-1073741790;
      }
      return (unsigned int)InstalledLanguageType;
    }
    return (unsigned int)-1073741811;
  }
  if ( v14 == 2 )
  {
    v4 = 1;
    InstalledLanguageType = RtlpGetCompleteLanguageFallback(v13, v15, 0, (unsigned int)v23, 258);
    if ( InstalledLanguageType < 0 )
      return (unsigned int)InstalledLanguageType;
    goto LABEL_23;
  }
  if ( v14 != 4 )
    return (unsigned int)-1073741811;
  memset_thunk_772440563353939046(v21, 0, 0xACu);
  RtlStringCchCopyW(v21, 85, v2);
  memset_thunk_772440563353939046(SourceString, 0, 0xACu);
  InstalledLanguageType = RtlpGetDefaultLanguageBaseOrParent(
                            v13,
                            v15,
                            (unsigned int)&v18,
                            (unsigned int)SourceString,
                            85,
                            0,
                            0);
  if ( InstalledLanguageType >= 0 )
  {
    v6 = v18;
    if ( !v18 )
      return (unsigned int)-1073741637;
    InstalledLanguageType = RtlpGetCompleteLanguageFallback(v13, v15, (unsigned int)v21, (unsigned int)v22, 172);
    if ( InstalledLanguageType >= 0 )
    {
      if ( (*v6 & 2) == 0
        || (v4 = 1,
            InstalledLanguageType = RtlpGetCompleteLanguageFallback(v13, (_DWORD)v6, 0, (unsigned int)v23, 258),
            InstalledLanguageType >= 0) )
      {
        v5 = 1;
        v2 = SourceString;
        goto LABEL_23;
      }
    }
  }
  return (unsigned int)InstalledLanguageType;
}

```

## disassembly

```asm
0x180142c30  push    rbp
0x180142c32  push    rbx
0x180142c33  push    rdi
0x180142c34  push    r13
0x180142c36  push    r14
0x180142c38  push    r15
0x180142c3a  lea     rbp, [rsp-498h]
0x180142c42  sub     rsp, 598h
0x180142c49  mov     rax, cs:__security_cookie
0x180142c50  xor     rax, rsp
0x180142c53  mov     [rbp+4C0h+var_40], rax
0x180142c5a  mov     [rsp+5C0h+Handle], 0
0x180142c63  xorps   xmm0, xmm0
0x180142c66  mov     [rbp+4C0h+var_540], 0
0x180142c6e  xorps   xmm1, xmm1
0x180142c71  mov     [rsp+5C0h+var_578], 0
0x180142c79  mov     rdi, rdx
0x180142c7c  mov     [rsp+5C0h+var_560], 0
0x180142c84  mov     [rsp+5C0h+var_550], 0
0x180142c8c  mov     [rsp+5C0h+var_558], 0
0x180142c95  mov     [rsp+5C0h+var_548], 0
0x180142c9e  mov     [rbp+4C0h+var_528], 0
0x180142ca6  movups  xmmword ptr [rbp+4C0h+var_538.Length], xmm0
0x180142caa  movups  xmmword ptr [rbp+4C0h+DestinationString.Length], xmm1
0x180142cae  movups  xmmword ptr [rsp+5C0h+var_570.Length], xmm0
0x180142cb3  test    rdx, rdx
0x180142cb6  jz      loc_1801430CB
0x180142cbc  mov     r13d, 0ACh
0x180142cc2  test    cl, 4
0x180142cc5  jz      short loc_180142D10
0x180142cc7  lea     rcx, [rbp+4C0h+DestinationString]; DestinationString
0x180142ccb  call    RtlInitUnicodeString
0x180142cd0  lea     rdx, [rsp+5C0h+var_578]
0x180142cd5  lea     rcx, [rbp+4C0h+DestinationString]
0x180142cd9  call    RtlUnicodeStringToLcid
0x180142cde  mov     ebx, eax
0x180142ce0  test    eax, eax
0x180142ce2  js      loc_1801430D0
0x180142ce8  mov     ecx, [rsp+5C0h+var_578]
0x180142cec  lea     rax, [rbp+4C0h+SourceString]
0x180142cf0  lea     rdx, [rbp+4C0h+var_538]
0x180142cf4  mov     [rbp+4C0h+var_538.Buffer], rax
0x180142cf8  mov     [rbp+4C0h+var_538.MaximumLength], r13w
0x180142cfd  call    RtlLCIDToCultureName
0x180142d02  test    al, al
0x180142d04  jz      loc_1801430CB
0x180142d0a  lea     rdi, [rbp+4C0h+SourceString]
0x180142d0e  jmp     short loc_180142D38
0x180142d10  test    cl, 8
0x180142d13  jz      loc_1801430CB
0x180142d19  lea     rcx, [rbp+4C0h+var_538]; DestinationString
0x180142d1d  call    RtlInitUnicodeString
0x180142d22  lea     rdx, [rsp+5C0h+var_578]
0x180142d27  lea     rcx, [rbp+4C0h+var_538]
0x180142d2b  call    RtlCultureNameToLCID
0x180142d30  test    al, al
0x180142d32  jz      loc_1801430CB
0x180142d38  lea     rcx, [rsp+5C0h+var_558]
0x180142d3d  call    RtlpCreateProcessRegistryInfo
0x180142d42  mov     ebx, eax
0x180142d44  test    eax, eax
0x180142d46  js      loc_1801430D0
0x180142d4c  cmp     [rsp+5C0h+var_558], 0
0x180142d52  jnz     short loc_180142D5E
0x180142d54  mov     ebx, 0C0000001h
0x180142d59  jmp     loc_1801430D0
0x180142d5e  mov     rcx, [rsp+5C0h+var_558]
0x180142d63  lea     r9, [rsp+5C0h+var_548]
0x180142d68  lea     r8, [rsp+5C0h+var_550]
0x180142d6d  mov     rdx, rdi
0x180142d70  call    RtlpGetInstalledLanguageType
0x180142d75  mov     ebx, eax
0x180142d77  test    eax, eax
0x180142d79  js      loc_1801430D0
0x180142d7f  mov     eax, [rsp+5C0h+var_550]
0x180142d83  xor     r14b, r14b
0x180142d86  xor     r15b, r15b
0x180142d89  sub     eax, 1
0x180142d8c  jz      loc_180142EAE
0x180142d92  sub     eax, 1
0x180142d95  jz      loc_180142E80
0x180142d9b  cmp     eax, 2
0x180142d9e  jnz     loc_1801430CB
0x180142da4  mov     r8, r13; Size
0x180142da7  lea     rcx, [rbp+4C0h+var_460]; void *
0x180142dab  xor     edx, edx; Val
0x180142dad  call    memset$thunk$772440563353939046
0x180142db2  mov     ebx, 55h ; 'U'
0x180142db7  lea     rcx, [rbp+4C0h+var_460]
0x180142dbb  mov     edx, ebx
0x180142dbd  mov     r8, rdi
0x180142dc0  call    RtlStringCchCopyW
0x180142dc5  mov     r8, r13; Size
0x180142dc8  lea     rcx, [rbp+4C0h+SourceString]; void *
0x180142dcc  xor     edx, edx; Val
0x180142dce  call    memset$thunk$772440563353939046
0x180142dd3  mov     rdx, [rsp+5C0h+var_548]
0x180142dd8  lea     r9, [rbp+4C0h+SourceString]
0x180142ddc  mov     rcx, [rsp+5C0h+var_558]
0x180142de1  lea     r8, [rbp+4C0h+var_528]
0x180142de5  mov     [rsp+5C0h+var_590], 0
0x180142dee  mov     [rsp+5C0h+var_598], 0
0x180142df7  mov     [rsp+5C0h+var_5A0], ebx
0x180142dfb  call    RtlpGetDefaultLanguageBaseOrParent
0x180142e00  mov     ebx, eax
0x180142e02  test    eax, eax
0x180142e04  js      loc_1801430D0
0x180142e0a  mov     rdi, [rbp+4C0h+var_528]
0x180142e0e  test    rdi, rdi
0x180142e11  jnz     short loc_180142E1D
0x180142e13  mov     ebx, 0C00000BBh
0x180142e18  jmp     loc_1801430D0
0x180142e1d  mov     rdx, [rsp+5C0h+var_548]
0x180142e22  lea     r9, [rbp+4C0h+var_3B0]
0x180142e29  mov     rcx, [rsp+5C0h+var_558]
0x180142e2e  lea     r8, [rbp+4C0h+var_460]
0x180142e32  mov     [rsp+5C0h+var_5A0], r13d
0x180142e37  call    RtlpGetCompleteLanguageFallback
0x180142e3c  mov     ebx, eax
0x180142e3e  test    eax, eax
0x180142e40  js      loc_1801430D0
0x180142e46  test    byte ptr [rdi], 2
0x180142e49  jz      short loc_180142E77
0x180142e4b  mov     rcx, [rsp+5C0h+var_558]
0x180142e50  lea     r9, [rbp+4C0h+var_250]
0x180142e57  xor     r8d, r8d
0x180142e5a  mov     [rsp+5C0h+var_5A0], 102h
0x180142e62  mov     rdx, rdi
0x180142e65  mov     r14b, 1
0x180142e68  call    RtlpGetCompleteLanguageFallback
0x180142e6d  mov     ebx, eax
0x180142e6f  test    eax, eax
0x180142e71  js      loc_1801430D0
0x180142e77  mov     r15b, 1
0x180142e7a  lea     rdi, [rbp+4C0h+SourceString]
0x180142e7e  jmp     short loc_180142EAE
0x180142e80  mov     rdx, [rsp+5C0h+var_548]
0x180142e85  lea     r9, [rbp+4C0h+var_250]
0x180142e8c  mov     rcx, [rsp+5C0h+var_558]
0x180142e91  xor     r8d, r8d
0x180142e94  mov     r14b, 1
0x180142e97  mov     [rsp+5C0h+var_5A0], 102h
0x180142e9f  call    RtlpGetCompleteLanguageFallback
0x180142ea4  mov     ebx, eax
0x180142ea6  test    eax, eax
0x180142ea8  js      loc_1801430D0
0x180142eae  mov     rdx, rdi; SourceString
0x180142eb1  lea     rcx, [rbp+4C0h+var_538]; DestinationString
0x180142eb5  call    RtlInitUnicodeString
0x180142eba  lea     rdx, [rsp+5C0h+var_578]
0x180142ebf  lea     rcx, [rbp+4C0h+var_538]
0x180142ec3  call    RtlCultureNameToLCID
0x180142ec8  test    al, al
0x180142eca  jz      loc_1801430CB
0x180142ed0  movzx   ecx, word ptr [rsp+5C0h+var_578]
0x180142ed5  xor     edx, edx
0x180142ed7  call    NtFlushInstallUILanguage
0x180142edc  mov     ebx, eax
0x180142ede  test    eax, eax
0x180142ee0  jns     short loc_180142EF9
0x180142ee2  call    NtIsUILanguageComitted
0x180142ee7  test    eax, eax
0x180142ee9  jz      loc_1801430D0
0x180142eef  mov     ebx, 0C0000022h
0x180142ef4  jmp     loc_1801430D0
0x180142ef9  mov     edi, 0F003Fh
0x180142efe  test    r14b, r14b
0x180142f01  jz      short loc_180142F1B
0x180142f03  lea     r8, [rsp+5C0h+var_560]
0x180142f08  mov     ecx, 408h
0x180142f0d  lea     rdx, [rbp+4C0h+var_250]
0x180142f14  call    RtlpSetPreferredUILanguages
0x180142f19  jmp     short loc_180142F6E
0x180142f1b  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x180142f22  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x180142f27  call    RtlInitUnicodeString
0x180142f2c  lea     r9, [rsp+5C0h+Handle]
0x180142f31  mov     r8d, edi
0x180142f34  xor     edx, edx
0x180142f36  lea     rcx, [rsp+5C0h+var_570]
0x180142f3b  call    LdrpOpenKey
0x180142f40  test    eax, eax
0x180142f42  js      short loc_180142F6E
0x180142f44  lea     rdx, aInstalllanguag; "InstallLanguageFallback"
0x180142f4b  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x180142f50  call    RtlInitUnicodeString
0x180142f55  mov     rcx, [rsp+5C0h+Handle]
0x180142f5a  lea     rdx, [rsp+5C0h+var_570]
0x180142f5f  call    ZwDeleteValueKey
0x180142f64  mov     rcx, [rsp+5C0h+Handle]; Handle
0x180142f69  call    NtClose
0x180142f6e  test    r15b, r15b
0x180142f71  jnz     loc_1801430A0
0x180142f77  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x180142f7e  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x180142f83  call    RtlInitUnicodeString
0x180142f88  lea     r9, [rsp+5C0h+Handle]
0x180142f8d  mov     r8d, edi
0x180142f90  xor     edx, edx
0x180142f92  lea     rcx, [rsp+5C0h+var_570]
0x180142f97  call    LdrpOpenKey
0x180142f9c  test    eax, eax
0x180142f9e  js      loc_1801430D0
0x180142fa4  lea     rdx, aPreferreduilan; "PreferredUILanguages"
0x180142fab  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x180142fb0  call    RtlInitUnicodeString
0x180142fb5  mov     rcx, [rsp+5C0h+Handle]
0x180142fba  lea     rdx, [rsp+5C0h+var_570]
0x180142fbf  call    ZwDeleteValueKey
0x180142fc4  mov     rcx, [rsp+5C0h+Handle]; Handle
0x180142fc9  call    NtClose
0x180142fce  lea     rdx, aRegistryMachin_32; "\\Registry\\Machine\\System\\CurrentCon"...
0x180142fd5  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x180142fda  call    RtlInitUnicodeString
0x180142fdf  lea     r9, [rsp+5C0h+Handle]
0x180142fe4  mov     r8d, edi
0x180142fe7  xor     edx, edx
0x180142fe9  lea     rcx, [rsp+5C0h+var_570]
0x180142fee  call    LdrpOpenKey
0x180142ff3  test    eax, eax
0x180142ff5  js      short loc_18014300B
0x180142ff7  mov     rcx, [rsp+5C0h+Handle]
0x180142ffc  call    NtDeleteKey
0x180143001  mov     rcx, [rsp+5C0h+Handle]; Handle
0x180143006  call    NtClose
0x18014300b  lea     r8, [rsp+5C0h+Handle]
0x180143010  mov     ecx, 2000000h
0x180143015  call    OpenGlobalizationUserSettingsKey
0x18014301a  test    eax, eax
0x18014301c  js      loc_1801430D0
0x180143022  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\MuiCached"
0x180143029  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x18014302e  call    RtlInitUnicodeString
0x180143033  mov     rdx, [rsp+5C0h+Handle]
0x180143038  lea     r9, [rbp+4C0h+var_540]
0x18014303c  mov     r8d, edi
0x18014303f  lea     rcx, [rsp+5C0h+var_570]
0x180143044  call    LdrpOpenKey
0x180143049  test    eax, eax
0x18014304b  js      short loc_180143094
0x18014304d  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x180143054  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x180143059  call    RtlInitUnicodeString
0x18014305e  mov     rcx, [rbp+4C0h+var_540]
0x180143062  lea     rdx, [rsp+5C0h+var_570]
0x180143067  call    ZwDeleteValueKey
0x18014306c  lea     rdx, aMachinelanguag; "MachineLanguageConfiguration"
0x180143073  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x180143078  call    RtlInitUnicodeString
0x18014307d  mov     rcx, [rbp+4C0h+var_540]
0x180143081  lea     rdx, [rsp+5C0h+var_570]
0x180143086  call    ZwDeleteValueKey
0x18014308b  mov     rcx, [rbp+4C0h+var_540]; Handle
0x18014308f  call    NtClose
0x180143094  mov     rcx, [rsp+5C0h+Handle]; Handle
0x180143099  call    NtClose
0x18014309e  jmp     short loc_1801430D0
0x1801430a0  lea     r8, [rsp+5C0h+var_560]
0x1801430a5  mov     ecx, 8008h
0x1801430aa  lea     rdx, [rbp+4C0h+var_460]
0x1801430ae  call    RtlpSetPreferredUILanguages
0x1801430b3  lea     r8, [rsp+5C0h+var_560]
0x1801430b8  mov     ecx, 9008h
0x1801430bd  lea     rdx, [rbp+4C0h+var_3B0]
0x1801430c4  call    RtlpSetPreferredUILanguages
0x1801430c9  jmp     short loc_1801430D0
0x1801430cb  mov     ebx, 0C000000Dh
0x1801430d0  mov     eax, ebx
0x1801430d2  mov     rcx, [rbp+4C0h+var_40]
0x1801430d9  xor     rcx, rsp; StackCookie
0x1801430dc  call    __security_check_cookie
0x1801430e1  add     rsp, 598h
0x1801430e8  pop     r15
0x1801430ea  pop     r14
0x1801430ec  pop     r13
0x1801430ee  pop     rdi
0x1801430ef  pop     rbx
0x1801430f0  pop     rbp
0x1801430f1  retn
```
