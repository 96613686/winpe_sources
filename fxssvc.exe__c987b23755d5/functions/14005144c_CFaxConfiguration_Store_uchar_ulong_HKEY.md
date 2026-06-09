# CFaxConfiguration::Store(uchar *,ulong,HKEY__ *)

- ea: `0x14005144c`
- end: `0x14005186e`
- name: `?Store@CFaxConfiguration@@AEBAKPEAEKPEAUHKEY__@@@Z`
- size: `1058`
- prototype: `unsigned int(CFaxConfiguration *__hidden this, unsigned __int8 *, unsigned int, HKEY)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140051380`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14005144c`
- `0x14005198c`
- `0x140065dbc`
- `0x140066770`
- `0x14006fa88`
- `0x1400709fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400514ef`
- `KERNEL32!GetLastError` at `0x1400515a0`
- `KERNEL32!GetLastError` at `0x1400515f4`
- `KERNEL32!GetLastError` at `0x140051648`
- `KERNEL32!GetLastError` at `0x14005169c`
- `KERNEL32!GetLastError` at `0x1400516f0`
- `KERNEL32!GetLastError` at `0x1400517d4`
- `KERNEL32!GetLastError` at `0x140051819`
- `KERNEL32!GetLastError` at `0x1400514ef`
- `KERNEL32!GetLastError` at `0x1400515a0`
- `KERNEL32!GetLastError` at `0x1400515f4`
- `KERNEL32!GetLastError` at `0x140051648`
- `KERNEL32!GetLastError` at `0x14005169c`
- `KERNEL32!GetLastError` at `0x1400516f0`
- `KERNEL32!GetLastError` at `0x1400517d4`
- `KERNEL32!GetLastError` at `0x140051819`

## string_xrefs

- `0x1400517c1`: `AutoCreateAccountOnConnect`
- `0x1400517f9`: `AutoCreateAccountOnConnect`
- `0x140051806`: `IncomingFaxesArePublic`
- `0x14005183e`: `IncomingFaxesArePublic`

## pseudocode

```c
__int64 __fastcall CFaxConfiguration::Store(CFaxConfiguration *this, unsigned __int8 *a2, unsigned int a3, HKEY a4)
{
  void *v7; // rbp
  CMapDeviceId *v8; // rcx
  unsigned int v9; // ebx
  DWORD LastError; // eax
  CMapDeviceId *v11; // rcx
  int v12; // edx
  const WCHAR *v13; // r9
  const WCHAR *v14; // rcx
  __int64 v15; // rax
  const BYTE *v16; // r9
  CFaxConfiguration *v17; // rcx
  unsigned int v18; // eax
  _DWORD v20[26]; // [rsp+30h] [rbp-68h] BYREF

  v7 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( v8 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v8 + 2), 30, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids, a3);
    v9 = 668;
    goto LABEL_65;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"UseArchive", *((_DWORD *)a2 + 1)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 20;
    v13 = L"UseArchive";
    goto LABEL_64;
  }
  v14 = (const WCHAR *)*((_QWORD *)a2 + 1);
  if ( v14 )
  {
    v15 = ContractEnvironmentString(v14);
    v7 = (void *)v15;
    if ( !v15 )
    {
      v9 = 0;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids);
      }
      goto LABEL_65;
    }
    v16 = (const BYTE *)v15;
  }
  else
  {
    v16 = (const BYTE *)&Class;
  }
  if ( !(unsigned int)SetRegistryStringValue(a4, 1u, L"ArchiveFolder", v16) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 22;
    v13 = L"ArchiveFolder";
    goto LABEL_64;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"SizeQuotaWarn", *((_DWORD *)a2 + 4)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 23;
    v13 = L"SizeQuotaWarn";
    goto LABEL_64;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"HighWatermark", *((_DWORD *)a2 + 5)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 24;
    v13 = L"HighWatermark";
    goto LABEL_64;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"LowWatermark", *((_DWORD *)a2 + 6)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 25;
    v13 = L"LowWatermark";
    goto LABEL_64;
  }
  if ( !(unsigned int)SetRegistryDword(a4, L"ArchiveAgeLimit", *((_DWORD *)a2 + 7)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v12 = 26;
    v13 = L"ArchiveAgeLimit";
    goto LABEL_64;
  }
  v20[1] = *((_DWORD *)a2 + 17);
  v20[2] = *((_DWORD *)a2 + 13);
  v20[3] = *((_DWORD *)a2 + 11);
  v20[4] = *((_DWORD *)a2 + 12);
  v20[5] = *((_DWORD *)a2 + 14);
  v20[6] = *((_DWORD *)a2 + 15);
  v20[7] = *((_DWORD *)a2 + 10);
  v20[8] = *((_DWORD *)a2 + 16);
  v20[0] = 36;
  v18 = CFaxConfiguration::StoreOutboxSettings(v17, a4, (struct _FAX_OUTBOX_CONFIG *const)v20);
  v9 = v18;
  if ( !v18 )
  {
    if ( (unsigned int)SetRegistryDword(a4, L"AutoCreateAccountOnConnect", *((_DWORD *)a2 + 19)) )
    {
      if ( (unsigned int)SetRegistryDword(a4, L"IncomingFaxesArePublic", *((_DWORD *)a2 + 20)) )
        goto LABEL_65;
      LastError = GetLastError();
      v9 = LastError;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v12 = 29;
      v13 = L"IncomingFaxesArePublic";
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v12 = 28;
      v13 = L"AutoCreateAccountOnConnect";
    }
LABEL_64:
    WPP_SF_Sd(
      *((_QWORD *)v11 + 2),
      v12,
      (unsigned int)WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids,
      (_DWORD)v13,
      LastError);
    goto LABEL_65;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids, v18);
  }
LABEL_65:
  pMemFree(v7);
  return v9;
}

```

## disassembly

```asm
0x14005144c  push    rbx
0x14005144e  push    rbp
0x14005144f  push    rsi
0x140051450  push    rdi
0x140051451  push    r12
0x140051453  push    r14
0x140051455  push    r15
0x140051457  sub     rsp, 60h
0x14005145b  mov     rsi, r9
0x14005145e  mov     ebx, r8d
0x140051461  mov     rdi, rdx
0x140051464  xor     ebp, ebp
0x140051466  mov     rcx, cs:WPP_GLOBAL_Control
0x14005146d  lea     r15, WPP_GLOBAL_Control
0x140051474  lea     r12, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x14005147b  mov     r14b, 4
0x14005147e  cmp     rcx, r15
0x140051481  jz      short loc_1400514A5
0x140051483  test    [rcx+1Ch], r14b
0x140051487  jz      short loc_1400514A5
0x140051489  cmp     byte ptr [rcx+19h], 5
0x14005148d  jb      short loc_1400514A5
0x14005148f  mov     rcx, [rcx+10h]
0x140051493  lea     edx, [rbp+13h]
0x140051496  mov     r8, r12
0x140051499  call    WPP_SF_
0x14005149e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400514a5  test    ebx, ebx
0x1400514a7  jz      short loc_1400514D8
0x1400514a9  cmp     rcx, r15
0x1400514ac  jz      short loc_1400514CE
0x1400514ae  test    [rcx+1Ch], r14b
0x1400514b2  jz      short loc_1400514CE
0x1400514b4  cmp     byte ptr [rcx+19h], 2
0x1400514b8  jb      short loc_1400514CE
0x1400514ba  mov     rcx, [rcx+10h]
0x1400514be  mov     edx, 1Eh
0x1400514c3  mov     r9d, ebx
0x1400514c6  mov     r8, r12
0x1400514c9  call    WPP_SF_d
0x1400514ce  mov     ebx, 29Ch
0x1400514d3  jmp     loc_140051855
0x1400514d8  mov     r8d, [rdi+4]
0x1400514dc  lea     rdx, aUsearchive; "UseArchive"
0x1400514e3  mov     rcx, rsi
0x1400514e6  call    SetRegistryDword
0x1400514eb  test    eax, eax
0x1400514ed  jnz     short loc_14005152C
0x1400514ef  call    cs:__imp_GetLastError
0x1400514f5  mov     ebx, eax
0x1400514f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400514fe  cmp     rcx, r15
0x140051501  jz      loc_140051855
0x140051507  test    [rcx+1Ch], r14b
0x14005150b  jz      loc_140051855
0x140051511  cmp     byte ptr [rcx+19h], 2
0x140051515  jb      loc_140051855
0x14005151b  mov     edx, 14h
0x140051520  lea     r9, aUsearchive; "UseArchive"
0x140051527  jmp     loc_140051845
0x14005152c  mov     rcx, [rdi+8]; lpString2
0x140051530  test    rcx, rcx
0x140051533  jz      short loc_140051581
0x140051535  call    ContractEnvironmentString
0x14005153a  mov     rbp, rax
0x14005153d  test    rax, rax
0x140051540  jnz     short loc_14005157C
0x140051542  xor     ebx, ebx
0x140051544  mov     rcx, cs:WPP_GLOBAL_Control
0x14005154b  cmp     rcx, r15
0x14005154e  jz      loc_140051855
0x140051554  test    [rcx+1Ch], r14b
0x140051558  jz      loc_140051855
0x14005155e  cmp     byte ptr [rcx+19h], 2
0x140051562  jb      loc_140051855
0x140051568  mov     rcx, [rcx+10h]
0x14005156c  lea     edx, [rax+15h]
0x14005156f  mov     r8, r12
0x140051572  call    WPP_SF_
0x140051577  jmp     loc_140051855
0x14005157c  mov     r9, rax
0x14005157f  jmp     short loc_140051588
0x140051581  lea     r9, Class; unsigned __int16 *
0x140051588  lea     r8, aArchivefolder; "ArchiveFolder"
0x14005158f  mov     edx, 1; unsigned int
0x140051594  mov     rcx, rsi; HKEY
0x140051597  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x14005159c  test    eax, eax
0x14005159e  jnz     short loc_1400515DD
0x1400515a0  call    cs:__imp_GetLastError
0x1400515a6  mov     ebx, eax
0x1400515a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400515af  cmp     rcx, r15
0x1400515b2  jz      loc_140051855
0x1400515b8  test    [rcx+1Ch], r14b
0x1400515bc  jz      loc_140051855
0x1400515c2  cmp     byte ptr [rcx+19h], 2
0x1400515c6  jb      loc_140051855
0x1400515cc  mov     edx, 16h
0x1400515d1  lea     r9, aArchivefolder; "ArchiveFolder"
0x1400515d8  jmp     loc_140051845
0x1400515dd  mov     r8d, [rdi+10h]
0x1400515e1  lea     rdx, aSizequotawarn; "SizeQuotaWarn"
0x1400515e8  mov     rcx, rsi
0x1400515eb  call    SetRegistryDword
0x1400515f0  test    eax, eax
0x1400515f2  jnz     short loc_140051631
0x1400515f4  call    cs:__imp_GetLastError
0x1400515fa  mov     ebx, eax
0x1400515fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140051603  cmp     rcx, r15
0x140051606  jz      loc_140051855
0x14005160c  test    [rcx+1Ch], r14b
0x140051610  jz      loc_140051855
0x140051616  cmp     byte ptr [rcx+19h], 2
0x14005161a  jb      loc_140051855
0x140051620  mov     edx, 17h
0x140051625  lea     r9, aSizequotawarn; "SizeQuotaWarn"
0x14005162c  jmp     loc_140051845
0x140051631  mov     r8d, [rdi+14h]
0x140051635  lea     rdx, aHighwatermark; "HighWatermark"
0x14005163c  mov     rcx, rsi
0x14005163f  call    SetRegistryDword
0x140051644  test    eax, eax
0x140051646  jnz     short loc_140051685
0x140051648  call    cs:__imp_GetLastError
0x14005164e  mov     ebx, eax
0x140051650  mov     rcx, cs:WPP_GLOBAL_Control
0x140051657  cmp     rcx, r15
0x14005165a  jz      loc_140051855
0x140051660  test    [rcx+1Ch], r14b
0x140051664  jz      loc_140051855
0x14005166a  cmp     byte ptr [rcx+19h], 2
0x14005166e  jb      loc_140051855
0x140051674  mov     edx, 18h
0x140051679  lea     r9, aHighwatermark; "HighWatermark"
0x140051680  jmp     loc_140051845
0x140051685  mov     r8d, [rdi+18h]
0x140051689  lea     rdx, aLowwatermark; "LowWatermark"
0x140051690  mov     rcx, rsi
0x140051693  call    SetRegistryDword
0x140051698  test    eax, eax
0x14005169a  jnz     short loc_1400516D9
0x14005169c  call    cs:__imp_GetLastError
0x1400516a2  mov     ebx, eax
0x1400516a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400516ab  cmp     rcx, r15
0x1400516ae  jz      loc_140051855
0x1400516b4  test    [rcx+1Ch], r14b
0x1400516b8  jz      loc_140051855
0x1400516be  cmp     byte ptr [rcx+19h], 2
0x1400516c2  jb      loc_140051855
0x1400516c8  mov     edx, 19h
0x1400516cd  lea     r9, aLowwatermark; "LowWatermark"
0x1400516d4  jmp     loc_140051845
0x1400516d9  mov     r8d, [rdi+1Ch]
0x1400516dd  lea     rdx, aArchiveagelimi; "ArchiveAgeLimit"
0x1400516e4  mov     rcx, rsi
0x1400516e7  call    SetRegistryDword
0x1400516ec  test    eax, eax
0x1400516ee  jnz     short loc_14005172D
0x1400516f0  call    cs:__imp_GetLastError
0x1400516f6  mov     ebx, eax
0x1400516f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400516ff  cmp     rcx, r15
0x140051702  jz      loc_140051855
0x140051708  test    [rcx+1Ch], r14b
0x14005170c  jz      loc_140051855
0x140051712  cmp     byte ptr [rcx+19h], 2
0x140051716  jb      loc_140051855
0x14005171c  mov     edx, 1Ah
0x140051721  lea     r9, aArchiveagelimi; "ArchiveAgeLimit"
0x140051728  jmp     loc_140051845
0x14005172d  mov     eax, [rdi+44h]
0x140051730  lea     r8, [rsp+98h+var_68]; struct _FAX_OUTBOX_CONFIG *
0x140051735  mov     [rsp+98h+var_64], eax
0x140051739  mov     rdx, rsi; HKEY
0x14005173c  mov     eax, [rdi+34h]
0x14005173f  mov     [rsp+98h+var_60], eax
0x140051743  mov     eax, [rdi+2Ch]
0x140051746  mov     [rsp+98h+var_5C], eax
0x14005174a  mov     eax, [rdi+30h]
0x14005174d  mov     [rsp+98h+var_58], eax
0x140051751  mov     eax, [rdi+38h]
0x140051754  mov     [rsp+98h+var_54], eax
0x140051758  mov     eax, [rdi+3Ch]
0x14005175b  mov     [rsp+98h+var_50], eax
0x14005175f  mov     eax, [rdi+28h]
0x140051762  mov     [rsp+98h+var_4C], eax
0x140051766  mov     eax, [rdi+40h]
0x140051769  mov     [rsp+98h+var_48], eax
0x14005176d  mov     [rsp+98h+var_68], 24h ; '$'
0x140051775  call    ?StoreOutboxSettings@CFaxConfiguration@@AEBAKPEAUHKEY__@@QEAU_FAX_OUTBOX_CONFIG@@@Z; CFaxConfiguration::StoreOutboxSettings(HKEY__ *,_FAX_OUTBOX_CONFIG * const)
0x14005177a  mov     ebx, eax
0x14005177c  test    eax, eax
0x14005177e  jz      short loc_1400517BD
0x140051780  mov     rcx, cs:WPP_GLOBAL_Control
0x140051787  cmp     rcx, r15
0x14005178a  jz      loc_140051855
0x140051790  test    [rcx+1Ch], r14b
0x140051794  jz      loc_140051855
0x14005179a  cmp     byte ptr [rcx+19h], 2
0x14005179e  jb      loc_140051855
0x1400517a4  mov     rcx, [rcx+10h]
0x1400517a8  mov     edx, 1Bh
0x1400517ad  mov     r9d, eax
0x1400517b0  mov     r8, r12
0x1400517b3  call    WPP_SF_d
0x1400517b8  jmp     loc_140051855
0x1400517bd  mov     r8d, [rdi+4Ch]
0x1400517c1  lea     rdx, aAutocreateacco; "AutoCreateAccountOnConnect"
0x1400517c8  mov     rcx, rsi
0x1400517cb  call    SetRegistryDword
0x1400517d0  test    eax, eax
0x1400517d2  jnz     short loc_140051802
0x1400517d4  call    cs:__imp_GetLastError
0x1400517da  mov     ebx, eax
0x1400517dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400517e3  cmp     rcx, r15
0x1400517e6  jz      short loc_140051855
0x1400517e8  test    [rcx+1Ch], r14b
0x1400517ec  jz      short loc_140051855
0x1400517ee  cmp     byte ptr [rcx+19h], 2
0x1400517f2  jb      short loc_140051855
0x1400517f4  mov     edx, 1Ch
0x1400517f9  lea     r9, aAutocreateacco; "AutoCreateAccountOnConnect"
0x140051800  jmp     short loc_140051845
0x140051802  mov     r8d, [rdi+50h]
0x140051806  lea     rdx, aIncomingfaxesa; "IncomingFaxesArePublic"
0x14005180d  mov     rcx, rsi
0x140051810  call    SetRegistryDword
0x140051815  test    eax, eax
0x140051817  jnz     short loc_140051855
0x140051819  call    cs:__imp_GetLastError
0x14005181f  mov     ebx, eax
0x140051821  mov     rcx, cs:WPP_GLOBAL_Control
0x140051828  cmp     rcx, r15
0x14005182b  jz      short loc_140051855
0x14005182d  test    [rcx+1Ch], r14b
0x140051831  jz      short loc_140051855
0x140051833  cmp     byte ptr [rcx+19h], 2
0x140051837  jb      short loc_140051855
0x140051839  mov     edx, 1Dh
0x14005183e  lea     r9, aIncomingfaxesa; "IncomingFaxesArePublic"
0x140051845  mov     rcx, [rcx+10h]
0x140051849  mov     r8, r12
0x14005184c  mov     [rsp+98h+var_78], eax
0x140051850  call    WPP_SF_Sd
0x140051855  mov     rcx, rbp; lpMem
0x140051858  call    pMemFree
0x14005185d  mov     eax, ebx
0x14005185f  add     rsp, 60h
0x140051863  pop     r15
0x140051865  pop     r14
0x140051867  pop     r12
0x140051869  pop     rdi
0x14005186a  pop     rsi
0x14005186b  pop     rbp
0x14005186c  pop     rbx
0x14005186d  retn
```
