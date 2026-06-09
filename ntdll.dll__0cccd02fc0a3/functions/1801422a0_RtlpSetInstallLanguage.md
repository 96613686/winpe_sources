# RtlpSetInstallLanguage

- ea: `0x1801422a0`
- end: `0x180142763`
- name: `RtlpSetInstallLanguage`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801428e0`

## callees

- `0x180009d60`
- `0x18000b730`
- `0x180011c70`
- `0x180054eb0`
- `0x1800c0420`
- `0x1800d97d0`
- `0x1800db118`
- `0x180110324`
- `0x180141e74`
- `0x180141fd8`
- `0x18014219c`
- `0x1801422a0`
- `0x1801428e0`
- `0x18015e4b0`
- `0x18015fe40`
- `0x18015fea0`
- `0x1801600a0`
- `0x180160420`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x18014263e`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings\LanguageConfiguration`
- `0x180142692`: `Control Panel\Desktop\MuiCached`
- `0x18014258b`: `\Registry\Machine\System\CurrentControlSet\Control\NLS\Language`
- `0x1801425b4`: `InstallLanguageFallback`
- `0x1801425e7`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`
- `0x1801426dc`: `MachineLanguageConfiguration`

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
0x1801422a0  push    rbp
0x1801422a2  push    rbx
0x1801422a3  push    rdi
0x1801422a4  push    r13
0x1801422a6  push    r14
0x1801422a8  push    r15
0x1801422aa  lea     rbp, [rsp-498h]
0x1801422b2  sub     rsp, 598h
0x1801422b9  mov     rax, cs:__security_cookie
0x1801422c0  xor     rax, rsp
0x1801422c3  mov     [rbp+4C0h+var_40], rax
0x1801422ca  mov     [rsp+5C0h+Handle], 0
0x1801422d3  xorps   xmm0, xmm0
0x1801422d6  mov     [rbp+4C0h+var_540], 0
0x1801422de  xorps   xmm1, xmm1
0x1801422e1  mov     [rsp+5C0h+var_578], 0
0x1801422e9  mov     rdi, rdx
0x1801422ec  mov     [rsp+5C0h+var_560], 0
0x1801422f4  mov     [rsp+5C0h+var_550], 0
0x1801422fc  mov     [rsp+5C0h+var_558], 0
0x180142305  mov     [rsp+5C0h+var_548], 0
0x18014230e  mov     [rbp+4C0h+var_528], 0
0x180142316  movups  xmmword ptr [rbp+4C0h+var_538.Length], xmm0
0x18014231a  movups  xmmword ptr [rbp+4C0h+DestinationString.Length], xmm1
0x18014231e  movups  xmmword ptr [rsp+5C0h+var_570.Length], xmm0
0x180142323  test    rdx, rdx
0x180142326  jz      loc_18014273B
0x18014232c  mov     r13d, 0ACh
0x180142332  test    cl, 4
0x180142335  jz      short loc_180142380
0x180142337  lea     rcx, [rbp+4C0h+DestinationString]; DestinationString
0x18014233b  call    RtlInitUnicodeString
0x180142340  lea     rdx, [rsp+5C0h+var_578]
0x180142345  lea     rcx, [rbp+4C0h+DestinationString]
0x180142349  call    RtlUnicodeStringToLcid
0x18014234e  mov     ebx, eax
0x180142350  test    eax, eax
0x180142352  js      loc_180142740
0x180142358  mov     ecx, [rsp+5C0h+var_578]
0x18014235c  lea     rax, [rbp+4C0h+SourceString]
0x180142360  lea     rdx, [rbp+4C0h+var_538]
0x180142364  mov     [rbp+4C0h+var_538.Buffer], rax
0x180142368  mov     [rbp+4C0h+var_538.MaximumLength], r13w
0x18014236d  call    RtlLCIDToCultureName
0x180142372  test    al, al
0x180142374  jz      loc_18014273B
0x18014237a  lea     rdi, [rbp+4C0h+SourceString]
0x18014237e  jmp     short loc_1801423A8
0x180142380  test    cl, 8
0x180142383  jz      loc_18014273B
0x180142389  lea     rcx, [rbp+4C0h+var_538]; DestinationString
0x18014238d  call    RtlInitUnicodeString
0x180142392  lea     rdx, [rsp+5C0h+var_578]
0x180142397  lea     rcx, [rbp+4C0h+var_538]
0x18014239b  call    RtlCultureNameToLCID
0x1801423a0  test    al, al
0x1801423a2  jz      loc_18014273B
0x1801423a8  lea     rcx, [rsp+5C0h+var_558]
0x1801423ad  call    RtlpCreateProcessRegistryInfo
0x1801423b2  mov     ebx, eax
0x1801423b4  test    eax, eax
0x1801423b6  js      loc_180142740
0x1801423bc  cmp     [rsp+5C0h+var_558], 0
0x1801423c2  jnz     short loc_1801423CE
0x1801423c4  mov     ebx, 0C0000001h
0x1801423c9  jmp     loc_180142740
0x1801423ce  mov     rcx, [rsp+5C0h+var_558]
0x1801423d3  lea     r9, [rsp+5C0h+var_548]
0x1801423d8  lea     r8, [rsp+5C0h+var_550]
0x1801423dd  mov     rdx, rdi
0x1801423e0  call    RtlpGetInstalledLanguageType
0x1801423e5  mov     ebx, eax
0x1801423e7  test    eax, eax
0x1801423e9  js      loc_180142740
0x1801423ef  mov     eax, [rsp+5C0h+var_550]
0x1801423f3  xor     r14b, r14b
0x1801423f6  xor     r15b, r15b
0x1801423f9  sub     eax, 1
0x1801423fc  jz      loc_18014251E
0x180142402  sub     eax, 1
0x180142405  jz      loc_1801424F0
0x18014240b  cmp     eax, 2
0x18014240e  jnz     loc_18014273B
0x180142414  mov     r8, r13; Size
0x180142417  lea     rcx, [rbp+4C0h+var_460]; void *
0x18014241b  xor     edx, edx; Val
0x18014241d  call    memset$thunk$772440563353939046
0x180142422  mov     ebx, 55h ; 'U'
0x180142427  lea     rcx, [rbp+4C0h+var_460]
0x18014242b  mov     edx, ebx
0x18014242d  mov     r8, rdi
0x180142430  call    RtlStringCchCopyW
0x180142435  mov     r8, r13; Size
0x180142438  lea     rcx, [rbp+4C0h+SourceString]; void *
0x18014243c  xor     edx, edx; Val
0x18014243e  call    memset$thunk$772440563353939046
0x180142443  mov     rdx, [rsp+5C0h+var_548]
0x180142448  lea     r9, [rbp+4C0h+SourceString]
0x18014244c  mov     rcx, [rsp+5C0h+var_558]
0x180142451  lea     r8, [rbp+4C0h+var_528]
0x180142455  mov     [rsp+5C0h+var_590], 0
0x18014245e  mov     [rsp+5C0h+var_598], 0
0x180142467  mov     [rsp+5C0h+var_5A0], ebx
0x18014246b  call    RtlpGetDefaultLanguageBaseOrParent
0x180142470  mov     ebx, eax
0x180142472  test    eax, eax
0x180142474  js      loc_180142740
0x18014247a  mov     rdi, [rbp+4C0h+var_528]
0x18014247e  test    rdi, rdi
0x180142481  jnz     short loc_18014248D
0x180142483  mov     ebx, 0C00000BBh
0x180142488  jmp     loc_180142740
0x18014248d  mov     rdx, [rsp+5C0h+var_548]
0x180142492  lea     r9, [rbp+4C0h+var_3B0]
0x180142499  mov     rcx, [rsp+5C0h+var_558]
0x18014249e  lea     r8, [rbp+4C0h+var_460]
0x1801424a2  mov     [rsp+5C0h+var_5A0], r13d
0x1801424a7  call    RtlpGetCompleteLanguageFallback
0x1801424ac  mov     ebx, eax
0x1801424ae  test    eax, eax
0x1801424b0  js      loc_180142740
0x1801424b6  test    byte ptr [rdi], 2
0x1801424b9  jz      short loc_1801424E7
0x1801424bb  mov     rcx, [rsp+5C0h+var_558]
0x1801424c0  lea     r9, [rbp+4C0h+var_250]
0x1801424c7  xor     r8d, r8d
0x1801424ca  mov     [rsp+5C0h+var_5A0], 102h
0x1801424d2  mov     rdx, rdi
0x1801424d5  mov     r14b, 1
0x1801424d8  call    RtlpGetCompleteLanguageFallback
0x1801424dd  mov     ebx, eax
0x1801424df  test    eax, eax
0x1801424e1  js      loc_180142740
0x1801424e7  mov     r15b, 1
0x1801424ea  lea     rdi, [rbp+4C0h+SourceString]
0x1801424ee  jmp     short loc_18014251E
0x1801424f0  mov     rdx, [rsp+5C0h+var_548]
0x1801424f5  lea     r9, [rbp+4C0h+var_250]
0x1801424fc  mov     rcx, [rsp+5C0h+var_558]
0x180142501  xor     r8d, r8d
0x180142504  mov     r14b, 1
0x180142507  mov     [rsp+5C0h+var_5A0], 102h
0x18014250f  call    RtlpGetCompleteLanguageFallback
0x180142514  mov     ebx, eax
0x180142516  test    eax, eax
0x180142518  js      loc_180142740
0x18014251e  mov     rdx, rdi; SourceString
0x180142521  lea     rcx, [rbp+4C0h+var_538]; DestinationString
0x180142525  call    RtlInitUnicodeString
0x18014252a  lea     rdx, [rsp+5C0h+var_578]
0x18014252f  lea     rcx, [rbp+4C0h+var_538]
0x180142533  call    RtlCultureNameToLCID
0x180142538  test    al, al
0x18014253a  jz      loc_18014273B
0x180142540  movzx   ecx, word ptr [rsp+5C0h+var_578]
0x180142545  xor     edx, edx
0x180142547  call    NtFlushInstallUILanguage
0x18014254c  mov     ebx, eax
0x18014254e  test    eax, eax
0x180142550  jns     short loc_180142569
0x180142552  call    NtIsUILanguageComitted
0x180142557  test    eax, eax
0x180142559  jz      loc_180142740
0x18014255f  mov     ebx, 0C0000022h
0x180142564  jmp     loc_180142740
0x180142569  mov     edi, 0F003Fh
0x18014256e  test    r14b, r14b
0x180142571  jz      short loc_18014258B
0x180142573  lea     r8, [rsp+5C0h+var_560]
0x180142578  mov     ecx, 408h
0x18014257d  lea     rdx, [rbp+4C0h+var_250]
0x180142584  call    RtlpSetPreferredUILanguages
0x180142589  jmp     short loc_1801425DE
0x18014258b  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x180142592  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x180142597  call    RtlInitUnicodeString
0x18014259c  lea     r9, [rsp+5C0h+Handle]
0x1801425a1  mov     r8d, edi
0x1801425a4  xor     edx, edx
0x1801425a6  lea     rcx, [rsp+5C0h+var_570]
0x1801425ab  call    LdrpOpenKey
0x1801425b0  test    eax, eax
0x1801425b2  js      short loc_1801425DE
0x1801425b4  lea     rdx, aInstalllanguag; "InstallLanguageFallback"
0x1801425bb  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x1801425c0  call    RtlInitUnicodeString
0x1801425c5  mov     rcx, [rsp+5C0h+Handle]
0x1801425ca  lea     rdx, [rsp+5C0h+var_570]
0x1801425cf  call    ZwDeleteValueKey
0x1801425d4  mov     rcx, [rsp+5C0h+Handle]; Handle
0x1801425d9  call    NtClose
0x1801425de  test    r15b, r15b
0x1801425e1  jnz     loc_180142710
0x1801425e7  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x1801425ee  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x1801425f3  call    RtlInitUnicodeString
0x1801425f8  lea     r9, [rsp+5C0h+Handle]
0x1801425fd  mov     r8d, edi
0x180142600  xor     edx, edx
0x180142602  lea     rcx, [rsp+5C0h+var_570]
0x180142607  call    LdrpOpenKey
0x18014260c  test    eax, eax
0x18014260e  js      loc_180142740
0x180142614  lea     rdx, aPreferreduilan; "PreferredUILanguages"
0x18014261b  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x180142620  call    RtlInitUnicodeString
0x180142625  mov     rcx, [rsp+5C0h+Handle]
0x18014262a  lea     rdx, [rsp+5C0h+var_570]
0x18014262f  call    ZwDeleteValueKey
0x180142634  mov     rcx, [rsp+5C0h+Handle]; Handle
0x180142639  call    NtClose
0x18014263e  lea     rdx, aRegistryMachin_32; "\\Registry\\Machine\\System\\CurrentCon"...
0x180142645  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x18014264a  call    RtlInitUnicodeString
0x18014264f  lea     r9, [rsp+5C0h+Handle]
0x180142654  mov     r8d, edi
0x180142657  xor     edx, edx
0x180142659  lea     rcx, [rsp+5C0h+var_570]
0x18014265e  call    LdrpOpenKey
0x180142663  test    eax, eax
0x180142665  js      short loc_18014267B
0x180142667  mov     rcx, [rsp+5C0h+Handle]
0x18014266c  call    NtDeleteKey
0x180142671  mov     rcx, [rsp+5C0h+Handle]; Handle
0x180142676  call    NtClose
0x18014267b  lea     r8, [rsp+5C0h+Handle]
0x180142680  mov     ecx, 2000000h
0x180142685  call    OpenGlobalizationUserSettingsKey
0x18014268a  test    eax, eax
0x18014268c  js      loc_180142740
0x180142692  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\MuiCached"
0x180142699  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x18014269e  call    RtlInitUnicodeString
0x1801426a3  mov     rdx, [rsp+5C0h+Handle]
0x1801426a8  lea     r9, [rbp+4C0h+var_540]
0x1801426ac  mov     r8d, edi
0x1801426af  lea     rcx, [rsp+5C0h+var_570]
0x1801426b4  call    LdrpOpenKey
0x1801426b9  test    eax, eax
0x1801426bb  js      short loc_180142704
0x1801426bd  lea     rdx, aMachinepreferr; "MachinePreferredUILanguages"
0x1801426c4  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x1801426c9  call    RtlInitUnicodeString
0x1801426ce  mov     rcx, [rbp+4C0h+var_540]
0x1801426d2  lea     rdx, [rsp+5C0h+var_570]
0x1801426d7  call    ZwDeleteValueKey
0x1801426dc  lea     rdx, aMachinelanguag; "MachineLanguageConfiguration"
0x1801426e3  lea     rcx, [rsp+5C0h+var_570]; DestinationString
0x1801426e8  call    RtlInitUnicodeString
0x1801426ed  mov     rcx, [rbp+4C0h+var_540]
0x1801426f1  lea     rdx, [rsp+5C0h+var_570]
0x1801426f6  call    ZwDeleteValueKey
0x1801426fb  mov     rcx, [rbp+4C0h+var_540]; Handle
0x1801426ff  call    NtClose
0x180142704  mov     rcx, [rsp+5C0h+Handle]; Handle
0x180142709  call    NtClose
0x18014270e  jmp     short loc_180142740
0x180142710  lea     r8, [rsp+5C0h+var_560]
0x180142715  mov     ecx, 8008h
0x18014271a  lea     rdx, [rbp+4C0h+var_460]
0x18014271e  call    RtlpSetPreferredUILanguages
0x180142723  lea     r8, [rsp+5C0h+var_560]
0x180142728  mov     ecx, 9008h
0x18014272d  lea     rdx, [rbp+4C0h+var_3B0]
0x180142734  call    RtlpSetPreferredUILanguages
0x180142739  jmp     short loc_180142740
0x18014273b  mov     ebx, 0C000000Dh
0x180142740  mov     eax, ebx
0x180142742  mov     rcx, [rbp+4C0h+var_40]
0x180142749  xor     rcx, rsp; StackCookie
0x18014274c  call    __security_check_cookie
0x180142751  add     rsp, 598h
0x180142758  pop     r15
0x18014275a  pop     r14
0x18014275c  pop     r13
0x18014275e  pop     rdi
0x18014275f  pop     rbx
0x180142760  pop     rbp
0x180142761  retn
```
