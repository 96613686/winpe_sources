# GetAutoJoinDomainConfiguration(ushort * *,ushort * *,ushort * *,_DSR_INSTANCE *)

- ea: `0x18006d100`
- end: `0x18006d4af`
- name: `?GetAutoJoinDomainConfiguration@@YAJPEAPEAG00PEAW4_DSR_INSTANCE@@@Z`
- size: `943`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, enum _DSR_INSTANCE *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004b240`
- `0x18006850c`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x18000bac0`
- `0x18000fc20`
- `0x180012948`
- `0x180030828`
- `0x180041124`
- `0x180043ef8`
- `0x18006d100`
- `0x18006dcfc`
- `0x18006e318`
- `0x18008c864`
- `0x18008cadc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18006d3ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18006d3ac`

## string_xrefs

- `0x18006d2a7`: `WriteDsRegDiscAdrsAndEntDrsFailureEvent: failed with error code: 0x%08x.`
- `0x18006d180`: `GetAutoJoinDomainConfiguration`
- `0x18006d1b1`: `GetAutoJoinDomainConfiguration`
- `0x18006d1fd`: `GetAutoJoinDomainConfiguration`
- `0x18006d2e4`: `GetAutoJoinDomainConfiguration`
- `0x18006d325`: `GetAutoJoinDomainConfiguration`
- `0x18006d3d7`: `GetAutoJoinDomainConfiguration`
- `0x18006d40c`: `GetAutoJoinDomainConfiguration`
- `0x18006d489`: `GetAutoJoinDomainConfiguration`
- `0x18006d3d0`: `CopyStringSafeW`
- `0x18006d405`: `CopyStringSafeW`
- `0x18006d18a`: `%s: Read tenant values from registry, name: %s, ID: %s.`
- `0x18006d1b8`: `%s: Found Enterprise DRS values from registry, name: %s`
- `0x18006d235`: `%s: Read registration values from AD. tenantName: %s; tenantID: %s; enterpriseDrs: %s.`

## pseudocode

```c
__int64 __fastcall GetAutoJoinDomainConfiguration(
        unsigned __int16 **a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        enum _DSR_INSTANCE *a4)
{
  unsigned __int16 *v6; // r15
  int AadTenantDetailsFromRegistry; // eax
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rsi
  int EnterpriseDrsDetailsFromRegistry; // eax
  unsigned __int16 *v11; // r14
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int RegistrationDetailsFromAD; // eax
  const WCHAR *v15; // r8
  unsigned int v16; // eax
  int v17; // eax
  int v18; // eax
  char v19; // dl
  __int16 v20; // r8
  int v21; // r9d
  int v22; // eax
  int v23; // eax
  int v24; // ecx
  wchar_t v26; // [rsp+20h] [rbp-38h]
  long double v27; // [rsp+28h] [rbp-30h]
  void *Block; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 *v29; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 *v30[3]; // [rsp+40h] [rbp-18h] BYREF
  int v32; // [rsp+A8h] [rbp+50h] BYREF
  unsigned __int16 **v33; // [rsp+B0h] [rbp+58h]
  unsigned __int16 *Source; // [rsp+B8h] [rbp+60h] BYREF

  v33 = a3;
  v29 = 0;
  v6 = 0;
  v32 = 0;
  Source = 0;
  v30[0] = 0;
  Block = 0;
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *(_DWORD *)a4 = 0;
  AadTenantDetailsFromRegistry = GetAadTenantDetailsFromRegistry(&Source, (unsigned __int16 **)&Block);
  v8 = Source;
  v9 = (unsigned __int16 *)Block;
  if ( AadTenantDetailsFromRegistry >= 0 && AadTenantDetailsFromRegistry != 1 )
    Logger::TraceInformation(
      L"%s: Read tenant values from registry, name: %s, ID: %s.",
      L"GetAutoJoinDomainConfiguration",
      Block,
      Source);
  EnterpriseDrsDetailsFromRegistry = GetEnterpriseDrsDetailsFromRegistry(v30);
  v11 = v30[0];
  v12 = EnterpriseDrsDetailsFromRegistry;
  if ( EnterpriseDrsDetailsFromRegistry < 0 || EnterpriseDrsDetailsFromRegistry == 1 )
    v12 = 0;
  else
    Logger::TraceInformation(
      L"%s: Found Enterprise DRS values from registry, name: %s",
      L"GetAutoJoinDomainConfiguration",
      v30[0]);
  if ( ((unsigned int)IsEmptyString(v9) || (unsigned int)IsEmptyString(v8)) && (unsigned int)IsEmptyString(v11) )
  {
    RegistrationDetailsFromAD = GetRegistrationDetailsFromAD(&Source, (unsigned __int16 **)&Block, v30);
    v12 = RegistrationDetailsFromAD;
    if ( RegistrationDetailsFromAD < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"GetAutoJoinDomainConfiguration",
        L"GetRegistrationDetailsFromAD",
        (unsigned int)RegistrationDetailsFromAD);
      v11 = v30[0];
LABEL_21:
      v8 = Source;
      v9 = (unsigned __int16 *)Block;
      goto LABEL_59;
    }
    v8 = Source;
    v9 = (unsigned __int16 *)Block;
    v11 = v30[0];
    v26 = (wchar_t)v30[0];
    Logger::TraceInformation(
      L"%s: Read registration values from AD. tenantName: %s; tenantID: %s; enterpriseDrs: %s.",
      L"GetAutoJoinDomainConfiguration",
      Block,
      Source);
  }
  if ( v9 || v8 )
  {
    if ( v11 )
    {
      v12 = -2145648611;
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
      {
        v15 = &cchOriginalDestLength;
        if ( v9 )
          v15 = v9;
        v16 = McTemplateU0zz_EventWriteTransfer(v13, DsRegAdrsAndEnterpriseDrsDiscoveredFailureEvent, v15, v11);
        if ( v16 )
          Logger::TraceError(L"WriteDsRegDiscAdrsAndEntDrsFailureEvent: failed with error code: 0x%08x.", v16);
      }
      goto LABEL_59;
    }
    if ( v9 )
    {
      v17 = StringStartsOrEndsWithOneOf(v9, L" ", &v32);
      v12 = v17;
      if ( v17 < 0 )
      {
LABEL_33:
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"GetAutoJoinDomainConfiguration",
          L"StringStartsOrEndsWithChar",
          (unsigned int)v17);
        goto LABEL_59;
      }
      if ( v32 )
      {
        v18 = StringTrimChars(v9, L" ", &v29);
        v12 = v18;
        if ( v18 < 0 )
        {
LABEL_36:
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"GetAutoJoinDomainConfiguration",
            L"StringTrimChars",
            (unsigned int)v18);
          v6 = v29;
          goto LABEL_59;
        }
        operator delete(v9);
        v9 = v29;
        Block = v29;
        v29 = 0;
      }
    }
    if ( v8 )
    {
      v17 = StringStartsOrEndsWithOneOf(v8, L" \"{}\n\r\t", &v32);
      v12 = v17;
      if ( v17 < 0 )
        goto LABEL_33;
      if ( v32 )
      {
        v18 = StringTrimChars(v8, L" \"{}\n\r\t", &v29);
        v12 = v18;
        if ( v18 < 0 )
          goto LABEL_36;
        operator delete(v8);
        v8 = v29;
        v6 = 0;
        Source = v29;
      }
      o((wchar_t)v8, v19, v20, v21, v26, v27);
    }
  }
  if ( v11 )
  {
    v22 = CopyStringSafeW(L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e", &Source);
    v12 = v22;
    if ( v22 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"GetAutoJoinDomainConfiguration",
        L"CopyStringSafeW",
        (unsigned int)v22);
      v8 = Source;
      goto LABEL_59;
    }
    v23 = CopyStringSafeW(v11, (unsigned __int16 **)&Block);
    v12 = v23;
    if ( v23 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"GetAutoJoinDomainConfiguration",
        L"CopyStringSafeW",
        (unsigned int)v23);
      goto LABEL_21;
    }
    v8 = Source;
    v24 = 1;
    v9 = (unsigned __int16 *)Block;
  }
  else
  {
    v24 = 0;
  }
  if ( a1 )
  {
    *a1 = v8;
    v8 = 0;
  }
  if ( a2 )
  {
    *a2 = v9;
    v9 = 0;
  }
  if ( v33 )
  {
    *v33 = v11;
    v11 = 0;
  }
  if ( a4 )
    *(_DWORD *)a4 = v24;
LABEL_59:
  operator delete(v8);
  operator delete(v9);
  operator delete(v11);
  operator delete(v6);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"GetAutoJoinDomainConfiguration", v12);
  return v12;
}

```

## disassembly

```asm
0x18006d100  mov     [rsp-40h+arg_10], r8
0x18006d105  mov     [rsp-40h+arg_0], rcx
0x18006d10a  push    rbp
0x18006d10b  push    rbx
0x18006d10c  push    rsi
0x18006d10d  push    rdi
0x18006d10e  push    r12
0x18006d110  push    r13
0x18006d112  push    r14
0x18006d114  push    r15
0x18006d116  mov     rbp, rsp
0x18006d119  sub     rsp, 58h
0x18006d11d  mov     r13, rdx
0x18006d120  mov     r12, r9
0x18006d123  xor     edx, edx
0x18006d125  mov     rax, r8
0x18006d128  mov     [rbp+var_20], rdx
0x18006d12c  mov     r15d, edx
0x18006d12f  mov     [rbp+arg_8], edx
0x18006d132  mov     [rbp+Source], rdx
0x18006d136  mov     [rbp+var_18], rdx
0x18006d13a  mov     [rbp+Block], rdx
0x18006d13e  test    rcx, rcx
0x18006d141  jz      short loc_18006D146
0x18006d143  mov     [rcx], rdx
0x18006d146  test    r13, r13
0x18006d149  jz      short loc_18006D14F
0x18006d14b  mov     [r13+0], rdx
0x18006d14f  test    rax, rax
0x18006d152  jz      short loc_18006D157
0x18006d154  mov     [r8], rdx
0x18006d157  test    r12, r12
0x18006d15a  jz      short loc_18006D15F
0x18006d15c  mov     [r9], edx
0x18006d15f  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18006d163  lea     rcx, [rbp+Source]; unsigned __int16 **
0x18006d167  call    ?GetAadTenantDetailsFromRegistry@@YAJPEAPEAG0@Z; GetAadTenantDetailsFromRegistry(ushort * *,ushort * *)
0x18006d16c  mov     rdi, [rbp+Source]
0x18006d170  mov     rsi, [rbp+Block]
0x18006d174  test    eax, eax
0x18006d176  js      short loc_18006D196
0x18006d178  cmp     eax, 1
0x18006d17b  jz      short loc_18006D196
0x18006d17d  mov     r9, rdi
0x18006d180  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18006d187  mov     r8, rsi
0x18006d18a  lea     rcx, aSReadTenantVal; "%s: Read tenant values from registry, n"...
0x18006d191  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18006d196  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x18006d19a  call    ?GetEnterpriseDrsDetailsFromRegistry@@YAJPEAPEAG@Z; GetEnterpriseDrsDetailsFromRegistry(ushort * *)
0x18006d19f  mov     r14, [rbp+var_18]
0x18006d1a3  mov     ebx, eax
0x18006d1a5  test    eax, eax
0x18006d1a7  js      short loc_18006D1C6
0x18006d1a9  cmp     eax, 1
0x18006d1ac  jz      short loc_18006D1C6
0x18006d1ae  mov     r8, r14
0x18006d1b1  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18006d1b8  lea     rcx, aSFoundEnterpri; "%s: Found Enterprise DRS values from re"...
0x18006d1bf  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18006d1c4  jmp     short loc_18006D1C8
0x18006d1c6  xor     ebx, ebx
0x18006d1c8  mov     rcx, rsi; unsigned __int16 *
0x18006d1cb  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18006d1d0  test    eax, eax
0x18006d1d2  jnz     short loc_18006D1E0
0x18006d1d4  mov     rcx, rdi; unsigned __int16 *
0x18006d1d7  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18006d1dc  test    eax, eax
0x18006d1de  jz      short loc_18006D254
0x18006d1e0  mov     rcx, r14; unsigned __int16 *
0x18006d1e3  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18006d1e8  test    eax, eax
0x18006d1ea  jz      short loc_18006D254
0x18006d1ec  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18006d1f0  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18006d1f4  lea     rcx, [rbp+Source]; unsigned __int16 **
0x18006d1f8  call    ?GetRegistrationDetailsFromAD@@YAJPEAPEAG00@Z; GetRegistrationDetailsFromAD(ushort * *,ushort * *,ushort * *)
0x18006d1fd  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18006d204  mov     ebx, eax
0x18006d206  test    eax, eax
0x18006d208  jns     short loc_18006D231
0x18006d20a  mov     r9d, eax
0x18006d20d  lea     r8, aGetregistratio; "GetRegistrationDetailsFromAD"
0x18006d214  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006d21b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d220  mov     r14, [rbp+var_18]
0x18006d224  mov     rdi, [rbp+Source]
0x18006d228  mov     rsi, [rbp+Block]
0x18006d22c  jmp     loc_18006D466
0x18006d231  mov     rdi, [rbp+Source]
0x18006d235  lea     rcx, aSReadRegistrat; "%s: Read registration values from AD. t"...
0x18006d23c  mov     rsi, [rbp+Block]
0x18006d240  mov     r9, rdi
0x18006d243  mov     r14, [rbp+var_18]
0x18006d247  mov     r8, rsi
0x18006d24a  mov     [rsp+58h+var_38], r14
0x18006d24f  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18006d254  test    rsi, rsi
0x18006d257  jnz     short loc_18006D262
0x18006d259  test    rdi, rdi
0x18006d25c  jz      loc_18006D3B2
0x18006d262  test    r14, r14
0x18006d265  jz      short loc_18006D2B8
0x18006d267  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18006d26e  mov     ebx, 801C001Dh
0x18006d273  jz      loc_18006D466
0x18006d279  lea     r8, cchOriginalDestLength
0x18006d280  test    r14, r14
0x18006d283  mov     r9, r8
0x18006d286  lea     rdx, DsRegAdrsAndEnterpriseDrsDiscoveredFailureEvent
0x18006d28d  cmovnz  r9, r14
0x18006d291  test    rsi, rsi
0x18006d294  cmovnz  r8, rsi
0x18006d298  call    McTemplateU0zz_EventWriteTransfer
0x18006d29d  test    eax, eax
0x18006d29f  jz      loc_18006D466
0x18006d2a5  mov     edx, eax
0x18006d2a7  lea     rcx, aWritedsregdisc; "WriteDsRegDiscAdrsAndEntDrsFailureEvent"...
0x18006d2ae  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d2b3  jmp     loc_18006D466
0x18006d2b8  test    rsi, rsi
0x18006d2bb  jz      loc_18006D355
0x18006d2c1  lea     r8, [rbp+arg_8]; int *
0x18006d2c5  mov     rcx, rsi; unsigned __int16 *
0x18006d2c8  lea     rdx, asc_1800C6B90; " "
0x18006d2cf  call    ?StringStartsOrEndsWithOneOf@@YAJPEBG0PEAH@Z; StringStartsOrEndsWithOneOf(ushort const *,ushort const *,int *)
0x18006d2d4  mov     ebx, eax
0x18006d2d6  test    eax, eax
0x18006d2d8  jns     short loc_18006D2FC
0x18006d2da  mov     r9d, eax
0x18006d2dd  lea     r8, aStringstartsor; "StringStartsOrEndsWithChar"
0x18006d2e4  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18006d2eb  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006d2f2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d2f7  jmp     loc_18006D466
0x18006d2fc  cmp     [rbp+arg_8], r15d
0x18006d300  jz      short loc_18006D355
0x18006d302  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18006d306  mov     rcx, rsi; Source
0x18006d309  lea     rdx, asc_1800C6B90; " "
0x18006d310  call    ?StringTrimChars@@YAJPEBG0PEAPEAG@Z; StringTrimChars(ushort const *,ushort const *,ushort * *)
0x18006d315  mov     ebx, eax
0x18006d317  test    eax, eax
0x18006d319  jns     short loc_18006D341
0x18006d31b  mov     r9d, eax
0x18006d31e  lea     r8, aStringtrimchar; "StringTrimChars"
0x18006d325  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18006d32c  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006d333  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d338  mov     r15, [rbp+var_20]
0x18006d33c  jmp     loc_18006D466
0x18006d341  mov     rcx, rsi; Block
0x18006d344  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006d349  mov     rsi, [rbp+var_20]
0x18006d34d  mov     [rbp+Block], rsi
0x18006d351  mov     [rbp+var_20], r15
0x18006d355  test    rdi, rdi
0x18006d358  jz      short loc_18006D3B2
0x18006d35a  lea     r8, [rbp+arg_8]; int *
0x18006d35e  mov     rcx, rdi; unsigned __int16 *
0x18006d361  lea     rdx, asc_1800EED50; " \"{}\n\r\t"
0x18006d368  call    ?StringStartsOrEndsWithOneOf@@YAJPEBG0PEAH@Z; StringStartsOrEndsWithOneOf(ushort const *,ushort const *,int *)
0x18006d36d  mov     ebx, eax
0x18006d36f  test    eax, eax
0x18006d371  js      loc_18006D2DA
0x18006d377  cmp     [rbp+arg_8], 0
0x18006d37b  jz      short loc_18006D3A9
0x18006d37d  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18006d381  mov     rcx, rdi; Source
0x18006d384  lea     rdx, asc_1800EED50; " \"{}\n\r\t"
0x18006d38b  call    ?StringTrimChars@@YAJPEBG0PEAPEAG@Z; StringTrimChars(ushort const *,ushort const *,ushort * *)
0x18006d390  mov     ebx, eax
0x18006d392  test    eax, eax
0x18006d394  js      short loc_18006D31B
0x18006d396  mov     rcx, rdi; Block
0x18006d399  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006d39e  mov     rdi, [rbp+var_20]
0x18006d3a2  xor     r15d, r15d
0x18006d3a5  mov     [rbp+Source], rdi
0x18006d3a9  mov     rcx, rdi
0x18006d3ac  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18006d3b2  test    r14, r14
0x18006d3b5  jz      short loc_18006D433
0x18006d3b7  lea     rdx, [rbp+Source]; unsigned __int16 **
0x18006d3bb  lea     rcx, a383a38895bc947; "383a3889-5bc9-47a3-846c-2b70f0b7fe0e"
0x18006d3c2  call    ?CopyStringSafeW@@YAJPEBGPEAPEAG@Z; CopyStringSafeW(ushort const *,ushort * *)
0x18006d3c7  mov     ebx, eax
0x18006d3c9  test    eax, eax
0x18006d3cb  jns     short loc_18006D3F0
0x18006d3cd  mov     r9d, eax
0x18006d3d0  lea     r8, aCopystringsafe; "CopyStringSafeW"
0x18006d3d7  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18006d3de  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006d3e5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d3ea  mov     rdi, [rbp+Source]
0x18006d3ee  jmp     short loc_18006D466
0x18006d3f0  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18006d3f4  mov     rcx, r14; Source
0x18006d3f7  call    ?CopyStringSafeW@@YAJPEBGPEAPEAG@Z; CopyStringSafeW(ushort const *,ushort * *)
0x18006d3fc  mov     ebx, eax
0x18006d3fe  test    eax, eax
0x18006d400  jns     short loc_18006D424
0x18006d402  mov     r9d, eax
0x18006d405  lea     r8, aCopystringsafe; "CopyStringSafeW"
0x18006d40c  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18006d413  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006d41a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006d41f  jmp     loc_18006D224
0x18006d424  mov     rdi, [rbp+Source]
0x18006d428  mov     ecx, 1
0x18006d42d  mov     rsi, [rbp+Block]
0x18006d431  jmp     short loc_18006D435
0x18006d433  xor     ecx, ecx
0x18006d435  mov     rax, [rbp+arg_0]
0x18006d439  test    rax, rax
0x18006d43c  jz      short loc_18006D443
0x18006d43e  mov     [rax], rdi
0x18006d441  xor     edi, edi
0x18006d443  test    r13, r13
0x18006d446  jz      short loc_18006D44E
0x18006d448  mov     [r13+0], rsi
0x18006d44c  xor     esi, esi
0x18006d44e  mov     rax, [rbp+arg_10]
0x18006d452  test    rax, rax
0x18006d455  jz      short loc_18006D45D
0x18006d457  mov     [rax], r14
0x18006d45a  xor     r14d, r14d
0x18006d45d  test    r12, r12
0x18006d460  jz      short loc_18006D466
0x18006d462  mov     [r12], ecx
0x18006d466  mov     rcx, rdi; Block
0x18006d469  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006d46e  mov     rcx, rsi; Block
0x18006d471  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006d476  mov     rcx, r14; Block
0x18006d479  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006d47e  mov     rcx, r15; Block
0x18006d481  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006d486  mov     r8d, ebx
0x18006d489  lea     rdx, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x18006d490  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18006d497  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18006d49c  mov     eax, ebx
0x18006d49e  add     rsp, 58h
0x18006d4a2  pop     r15
0x18006d4a4  pop     r14
0x18006d4a6  pop     r13
0x18006d4a8  pop     r12
0x18006d4aa  pop     rdi
0x18006d4ab  pop     rsi
0x18006d4ac  pop     rbx
0x18006d4ad  pop     rbp
0x18006d4ae  retn
```
