# RtlpSetPreferredUILanguages

- ea: `0x1801428e0`
- end: `0x180143464`
- name: `RtlpSetPreferredUILanguages`
- size: `2948`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801422a0`

## callees

- `0x180007060`
- `0x180008040`
- `0x180009d60`
- `0x18000aab0`
- `0x18000b730`
- `0x18000c7b0`
- `0x180011c70`
- `0x18001861c`
- `0x18001b984`
- `0x180054eb0`
- `0x1800c0420`
- `0x1800d97d0`
- `0x1800d9e10`
- `0x1800d9ed0`
- `0x1800eba10`
- `0x180141960`
- `0x180141a88`
- `0x180141af4`
- `0x180141c60`
- `0x180142220`
- `0x1801422a0`
- `0x18014276c`
- `0x1801428e0`
- `0x18014c814`
- `0x18015e4b0`
- `0x18015eec0`
- `0x180160280`
- `0x180160e40`
- `0x180162000`
- `0x180163a80`

## string_xrefs

- `0x180142f4a`: `\Registry\Machine\System\CurrentControlSet\Control\NLS\Language`
- `0x180142f83`: `InstallLanguageFallback`
- `0x180143215`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`
- `0x1801430f8`: `LanguageConfigurationPending`
- `0x180143288`: `LanguageConfiguration`

## pseudocode

```c
__int64 __fastcall RtlpSetPreferredUILanguages(int a1, const char *a2, _DWORD *a3)
{
  const char *v4; // rsi
  __int64 v5; // r12
  unsigned int v6; // r14d
  wchar_t *v7; // r13
  unsigned int v8; // r15d
  __int64 v9; // rcx
  int InstallUILanguage; // ebx
  int v11; // eax
  __int16 v12; // dx
  __int16 v13; // cx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  wchar_t *Heap_0; // rax
  wchar_t *v18; // r12
  unsigned __int64 v19; // r15
  unsigned int v20; // r14d
  int *Buffer; // r12
  unsigned __int16 MaximumLength; // r13
  _BYTE *v23; // r15
  unsigned int v24; // r8d
  const WCHAR *v25; // rcx
  int v26; // eax
  unsigned __int16 v27; // r14
  __int64 v28; // rax
  __int64 v29; // r8
  _WORD *v30; // rax
  __int64 v31; // r14
  __int64 v32; // rax
  unsigned int v33; // eax
  __int64 v34; // r8
  _WORD *v35; // r14
  unsigned int j; // r15d
  __int64 v37; // rcx
  __int64 v38; // rax
  __int16 v39; // r14
  __int64 v40; // rdx
  __int64 v41; // rcx
  HANDLE v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const char *v45; // rcx
  __int64 v46; // rax
  wchar_t *v48; // [rsp+30h] [rbp-D0h]
  unsigned int v49; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v50[2]; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v51; // [rsp+40h] [rbp-C0h]
  _WORD v52[2]; // [rsp+44h] [rbp-BCh] BYREF
  UNICODE_STRING v53; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v54; // [rsp+58h] [rbp-A8h]
  unsigned int v55; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v57[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v58; // [rsp+6Ch] [rbp-94h]
  UNICODE_STRING v59; // [rsp+70h] [rbp-90h] BYREF
  int Length; // [rsp+80h] [rbp-80h]
  unsigned int v61; // [rsp+84h] [rbp-7Ch]
  unsigned int v62; // [rsp+88h] [rbp-78h]
  UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  HANDLE Handle; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h]
  HANDLE v66; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE v67; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE v68; // [rsp+C0h] [rbp-40h] BYREF
  int i; // [rsp+C8h] [rbp-38h]
  const WCHAR *v70; // [rsp+D0h] [rbp-30h]
  const char *v71; // [rsp+D8h] [rbp-28h]
  __int64 v72; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v73; // [rsp+E8h] [rbp-18h]
  _DWORD *v74; // [rsp+F0h] [rbp-10h]
  _OWORD v75[2]; // [rsp+F8h] [rbp-8h] BYREF

  v74 = a3;
  v68 = 0;
  v67 = 0;
  v66 = 0;
  Handle = 0;
  v4 = a2;
  v61 = 0;
  v5 = 0;
  v58 = 0;
  v6 = 0;
  v62 = 0;
  v7 = 0;
  v49 = 0;
  v8 = 0;
  v50[0] = 0;
  v9 = 0;
  v55 = 0;
  v52[0] = 0;
  v56 = 0;
  v71 = 0;
  v57[0] = 0;
  v72 = 0;
  memset(v75, 0, 28);
  v53 = 0;
  DestinationString = 0;
  v59 = 0;
  if ( !a3 )
    goto LABEL_2;
  v11 = 18440;
  if ( a1 )
    v11 = a1;
  if ( (LOBYTE(a1) = v11, (v11 & 0xFFFF0363) != 0)
    || (v11 & 0x400) != 0 && (!a2 || (v11 & 0xFFFFFBF3) != 0)
    || (v11 & 0x8000) != 0 && (!a2 || (v11 & 0xFFFF6773) != 0) )
  {
LABEL_2:
    InstallUILanguage = -1073741811;
    goto LABEL_181;
  }
  if ( (v11 & 0xC) == 0xC || (v11 & 0x1800) == 0x1800 || (v11 & 0x10) != 0 && (v11 & 0x7080) != 0 )
  {
    InstallUILanguage = -1073741811;
LABEL_180:
    v9 = v56;
LABEL_181:
    if ( (a1 & 0x80u) != 0 && v9 )
      RtlpMuiFreeLangRegistryInfo();
    *v74 = v5 + v6 + (_DWORD)v7;
    return (unsigned int)InstallUILanguage;
  }
  v12 = v11 | 8;
  if ( (v11 & 0xC) != 0 )
    v12 = v11;
  v13 = v12 | 0x4000;
  if ( (v12 & 0xE410) != 0 )
    v13 = v12;
  LOWORD(a1) = v13 | 0x800;
  if ( (v13 & 0x1C00) != 0 )
    LOWORD(a1) = v13;
  if ( (a1 & 0x80u) == 0 )
    v14 = RtlpCreateProcessRegistryInfo(&v56);
  else
    v14 = RtlpInitializeLangRegistryInfo(&v56);
  InstallUILanguage = v14;
  if ( v14 >= 0 )
  {
    v65 = 0;
    v48 = 0;
    v73 = 0;
    if ( !v4 )
    {
      MaximumLength = 4;
      *(_DWORD *)&v59.Length = 262146;
      Buffer = &dword_18018AC4C;
      v59.Buffer = (wchar_t *)&dword_18018AC4C;
      v39 = 2;
      goto LABEL_107;
    }
    if ( (a1 & 4) != 0 )
      v16 = 4;
    else
      v16 = 85;
    if ( (int)RtlpCheckMuiMultiStringSafe(v4, v16) < 0 )
      DbgPrint(
        "*** ASSERT FAILED: Input parameter: %s, for function: %s is not a valid multi-string!\n",
        v4,
        "RtlpSetPreferredUILanguages");
    if ( (a1 & 0x400) != 0 )
    {
      InstallUILanguage = NtQueryInstallUILanguage(v57);
      if ( InstallUILanguage < 0 )
      {
LABEL_169:
        if ( Handle )
        {
          NtClose(Handle);
          Handle = 0;
        }
        if ( v66 )
        {
          NtClose(v66);
          v66 = 0;
        }
        if ( v67 )
        {
          NtClose(v67);
          v67 = 0;
        }
        if ( v68 )
        {
          NtClose(v68);
          v68 = 0;
        }
        if ( v5 )
          RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v5);
        LODWORD(v7) = v62;
        LODWORD(v5) = v61;
        v6 = v58;
        goto LABEL_180;
      }
      Heap_0 = (wchar_t *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 522);
      v73 = Heap_0;
      v18 = Heap_0;
      if ( !Heap_0 )
      {
        InstallUILanguage = -1073741801;
        v5 = 0;
        goto LABEL_169;
      }
      v53.Buffer = Heap_0;
      *(_DWORD *)&v53.Length = 11141120;
      if ( !(unsigned __int8)RtlLCIDToCultureName(v57[0], &v53) )
      {
        InstallUILanguage = -1073741811;
LABEL_165:
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v18);
LABEL_166:
        if ( v7 )
          RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v7);
        v5 = v65;
        goto LABEL_169;
      }
      v19 = (unsigned __int64)v53.Length >> 1;
      if ( (a1 & 4) != 0 )
      {
        InstallUILanguage = RtlpConvertLCIDsToCultureNames((PCWSTR)v4);
        if ( InstallUILanguage < 0 )
          goto LABEL_162;
        v4 = v71;
        LOWORD(a1) = a1 & 0xFFF3 | 8;
      }
      InstallUILanguage = RtlpGetMultiStringLength(v4, v50, 0);
      if ( InstallUILanguage < 0
        || (memmove(&v18[v19 + 1], v4, 2LL * ((unsigned int)v50[0] + 1)),
            InstallUILanguage = RtlpAutoCompleteLanguageFallback(v56, v18),
            InstallUILanguage < 0) )
      {
LABEL_162:
        if ( v71 )
          RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v71);
        v18 = v73;
        if ( !v73 )
          goto LABEL_166;
        goto LABEL_165;
      }
      v4 = (const char *)v18;
    }
    InstallUILanguage = RtlpGetMultiStringLength(v4, &v59, &v49);
    if ( InstallUILanguage < 0 )
      goto LABEL_162;
    v20 = v49;
    Buffer = (int *)v4;
    v59.Length *= 2;
    Length = v59.Length;
    MaximumLength = v59.Length + 2;
    v59.Buffer = (wchar_t *)v4;
    v59.MaximumLength = v59.Length + 2;
    if ( v49 - 1 > 2 )
      goto LABEL_83;
    v48 = (wchar_t *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 170);
    if ( !v48 )
    {
      InstallUILanguage = -1073741801;
      v7 = 0;
      goto LABEL_162;
    }
    v23 = 0;
    v51 = 0;
    v24 = 0;
    v25 = (const WCHAR *)v4;
    v26 = a1 & 4;
    for ( i = v26; ; v26 = i )
    {
      v54 = v24;
      v70 = v25;
      if ( v24 >= v20 )
      {
        if ( !v26 || (a1 & 0x10) != 0 )
          goto LABEL_106;
        v33 = v51 + 1;
        v51 = v33;
        if ( v33 <= 0xFFFF )
        {
          v34 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 2LL * v33);
          v65 = v34;
          if ( !v34 )
          {
LABEL_88:
            InstallUILanguage = -1073741670;
            goto LABEL_161;
          }
          Buffer = (int *)v34;
          v59.Buffer = (wchar_t *)v34;
          Length = (unsigned __int16)(2 * v51);
          MaximumLength = 2 * v51;
          v59.Length = 2 * v51;
          v35 = (_WORD *)v34;
          v59.MaximumLength = 2 * v51;
          for ( j = 0; j < v49; ++j )
          {
            RtlInitUnicodeString(&DestinationString, (PCWSTR)v4);
            if ( (int)RtlUnicodeStringToInteger(&DestinationString, 16, &v55) < 0 )
              goto LABEL_83;
            DestinationString.Buffer = v48;
            *(_DWORD *)&DestinationString.Length = 11141120;
            if ( !(unsigned __int8)RtlLCIDToCultureName(v55, &DestinationString) )
              goto LABEL_83;
            if ( (int)RtlStringCchCatW(v35, v51, DestinationString.Buffer) < 0 )
              goto LABEL_88;
            v15 = -1;
            v37 = -1;
            do
              ++v37;
            while ( v35[v37] );
            v51 += -1 - v37;
            if ( v35 )
              v35 += v37 + 1;
            else
              v35 = 0;
            if ( v4 )
            {
              v38 = -1;
              do
                ++v38;
              while ( *(_WORD *)&v4[2 * v38] );
              v4 += 2 * v38 + 2;
            }
            else
            {
              v4 = 0;
            }
          }
          v4 = (const char *)Buffer;
          *v35 = 0;
LABEL_106:
          v8 = v49;
          v39 = Length;
LABEL_107:
          if ( (a1 & 0x400) != 0 )
          {
            RtlInitUnicodeString(&v53, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\NLS\\Language");
            InstallUILanguage = LdrpCreateKey((unsigned int)&v53, 0, 0, 131078, (__int64)&v72);
            if ( InstallUILanguage >= 0 )
            {
              RtlInitUnicodeString(&v53, L"InstallLanguageFallback");
              v40 = -1;
              do
                ++v40;
              while ( *((_WORD *)Buffer + v40) );
              v59.MaximumLength = -2 - 2 * v40 + MaximumLength;
              v41 = Buffer ? (__int64)Buffer + 2 * v40 + 2 : 0LL;
              v59.Buffer = (wchar_t *)v41;
              InstallUILanguage = RtlpGetMultiStringLength(v41, &v59, &v49);
              if ( InstallUILanguage >= 0 )
              {
                v39 = v59.Length;
                Buffer = (int *)v59.Buffer;
                InstallUILanguage = ZwSetValueKey(v72, &v53, 0, 7, v59.Buffer, 2 * (unsigned int)v59.Length);
                if ( InstallUILanguage >= 0 )
                {
                  v8 = v49;
                  MaximumLength = v59.MaximumLength;
                  v62 = v49;
                  goto LABEL_118;
                }
              }
            }
LABEL_161:
            v7 = v48;
            goto LABEL_162;
          }
LABEL_118:
          if ( (a1 & 0x10) != 0 )
          {
            InstallUILanguage = RtlpSetInstallLanguage(a1, (const WCHAR *)v4);
            if ( InstallUILanguage < 0 )
              goto LABEL_161;
            v62 = v8;
          }
          if ( (a1 & 0x4000) == 0 )
            goto LABEL_136;
          InstallUILanguage = OpenGlobalizationUserSettingsKey(0x2000000, v15, &v68);
          if ( InstallUILanguage < 0 )
            goto LABEL_161;
          RtlInitUnicodeString(&v53, L"Control Panel\\Desktop");
          InstallUILanguage = LdrpOpenKey(&v53, v68, 983103, &v66);
          if ( InstallUILanguage < 0 )
            goto LABEL_161;
          if ( (a1 & 0x800) != 0 )
          {
            RtlInitUnicodeString(&v53, L"PreferredUILanguagesPending");
            v42 = v66;
            goto LABEL_134;
          }
          if ( v8 >= 2 )
          {
            RtlInitUnicodeString(&v53, L"LanguageConfigurationPending");
            InstallUILanguage = LdrpCreateKey((unsigned int)&v53, (_DWORD)v66, 0, 983103, (__int64)&Handle);
            if ( InstallUILanguage < 0 )
              goto LABEL_161;
            RtlInitUnicodeString(&v53, (PCWSTR)v4);
            if ( v4 )
            {
              v43 = -1;
              do
                ++v43;
              while ( *(_WORD *)&v4[2 * v43] );
              Buffer = (int *)&v4[2 * v43 + 2];
              v59.Buffer = (wchar_t *)Buffer;
            }
            else
            {
              Buffer = 0;
              v59.Buffer = 0;
            }
            MaximumLength -= v53.MaximumLength;
            v42 = Handle;
            v59.MaximumLength = MaximumLength;
            v59.Length = v39 - v53.MaximumLength;
LABEL_134:
            InstallUILanguage = ZwSetValueKey(v42, &v53, 0, 7, Buffer, MaximumLength);
            if ( InstallUILanguage < 0 )
              goto LABEL_161;
            v61 = v8;
LABEL_136:
            if ( Handle )
            {
              NtClose(Handle);
              Handle = 0;
            }
            if ( (a1 & 0x8000) != 0 && (a1 & 0x800) != 0 )
            {
              DestinationString = v59;
              InstallUILanguage = RtlpSetMachineUILanguagesImmediate(&DestinationString);
              v58 = v8;
            }
            if ( (a1 & 0x2000) == 0 && ((a1 & 0x8000) == 0 || (a1 & 0x1000) == 0) )
            {
              if ( InstallUILanguage < 0 )
                goto LABEL_161;
LABEL_158:
              if ( (a1 & 0xE410) != 0 )
              {
                ZwGetMUIRegistryInfo(8, 0, 0);
                if ( (a1 & 0x8410) != 0 )
                  RtlUpdateProcessRegistryInfo();
              }
              goto LABEL_161;
            }
            RtlInitUnicodeString(&v53, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings");
            InstallUILanguage = LdrpCreateKey((unsigned int)&v53, 0, 0, 983103, (__int64)&v67);
            if ( InstallUILanguage < 0 )
              goto LABEL_161;
            if ( (a1 & 0x800) != 0 )
            {
              RtlInitUnicodeString(&v53, L"PreferredUILanguages");
              v44 = ZwSetValueKey(v67, &v53, 0, 7, Buffer, MaximumLength);
LABEL_156:
              InstallUILanguage = v44;
              if ( v44 < 0 )
                goto LABEL_161;
              v58 = v8;
              goto LABEL_158;
            }
            if ( v8 >= 2 )
            {
              RtlInitUnicodeString(&v53, L"LanguageConfiguration");
              InstallUILanguage = LdrpCreateKey((unsigned int)&v53, (_DWORD)v67, 0, 983103, (__int64)&Handle);
              if ( InstallUILanguage < 0 )
                goto LABEL_161;
              RtlInitUnicodeString(&v53, (PCWSTR)v4);
              v45 = 0;
              if ( v4 )
              {
                v46 = -1;
                do
                  ++v46;
                while ( *(_WORD *)&v4[2 * v46] );
                v45 = &v4[2 * v46 + 2];
              }
              v44 = ZwSetValueKey(Handle, &v53, 0, 7, v45, (unsigned __int16)(MaximumLength - v53.MaximumLength));
              goto LABEL_156;
            }
          }
        }
LABEL_83:
        InstallUILanguage = -1073741811;
        goto LABEL_161;
      }
      if ( v26 )
      {
        RtlInitUnicodeString(&DestinationString, v25);
        if ( (int)RtlUnicodeStringToInteger(&DestinationString, 16, &v55) < 0 )
          goto LABEL_83;
        v27 = v55;
        if ( ((v55 - 4096) & 0xFFFFFBFF) == 0 )
          goto LABEL_83;
        DestinationString.Buffer = v48;
        *(_DWORD *)&DestinationString.Length = 11141120;
        if ( !(unsigned __int8)RtlLCIDToCultureName(v55, &DestinationString) )
          goto LABEL_83;
        v15 = (__int64)DestinationString.Buffer;
        v28 = -1;
        do
          ++v28;
        while ( DestinationString.Buffer[v28] );
        v51 += v28 + 1;
      }
      else
      {
        RtlInitUnicodeString(&DestinationString, v25);
        if ( !(unsigned __int8)RtlCultureNameToLCID(&DestinationString, &v55) )
          goto LABEL_83;
        v27 = v55;
        if ( ((v55 - 4096) & 0xFFFFFBFF) == 0 )
          goto LABEL_83;
        v15 = (__int64)DestinationString.Buffer;
      }
      v29 = v54;
      switch ( v54 )
      {
        case 0u:
          v31 = v56;
          LOBYTE(v29) = 1;
          if ( (int)RtlpMuiRegGetInstalledLanguageIndexByName(v56, v15, v29, v52) < 0 )
            goto LABEL_83;
          v23 = (_BYTE *)(*(_QWORD *)(*(_QWORD *)(v31 + 24) + 16LL) + 28LL * v52[0]);
          goto LABEL_76;
        case 1u:
          if ( (a1 & 0x800) != 0 || (a1 & 0x10) != 0 || (*v23 & 1) != 0 )
            goto LABEL_83;
          if ( (*v23 & 2) == 0 )
          {
            if ( (*v23 & 4) == 0 || v49 > 2 )
              goto LABEL_83;
            v30 = v52;
            goto LABEL_65;
          }
          break;
        case 2u:
          break;
        default:
          goto LABEL_77;
      }
      v30 = v50;
LABEL_65:
      if ( (int)RtlpMuiRegGetFallbackInstalledLanguageInfoByLangId(
                  v56,
                  (_DWORD)v23,
                  v27,
                  (unsigned int)v75,
                  (__int64)v30) < 0 )
        goto LABEL_83;
      v23 = v75;
LABEL_76:
      LODWORD(v29) = v54;
LABEL_77:
      if ( v70 )
      {
        v32 = -1;
        v15 = 0;
        do
          ++v32;
        while ( v70[v32] );
        v25 = &v70[v32 + 1];
      }
      else
      {
        v25 = 0;
      }
      v20 = v49;
      v24 = v29 + 1;
    }
  }
  return (unsigned int)InstallUILanguage;
}

```

## disassembly

```asm
0x1801428e0  mov     [rsp-8+arg_18], rbx; RtlpSetPreferredUILanguages
0x1801428e5  push    rbp
0x1801428e6  push    rsi
0x1801428e7  push    rdi
0x1801428e8  push    r12
0x1801428ea  push    r13
0x1801428ec  push    r14
0x1801428ee  push    r15
0x1801428f0  lea     rbp, [rsp-20h]
0x1801428f5  sub     rsp, 120h
0x1801428fc  mov     rax, cs:__security_cookie
0x180142903  xor     rax, rsp
0x180142906  mov     [rbp+50h+var_38], rax
0x18014290a  xor     ebx, ebx
0x18014290c  mov     [rbp+50h+var_60], r8
0x180142910  mov     [rbp+50h+var_90], rbx
0x180142914  xorps   xmm0, xmm0
0x180142917  mov     [rbp+50h+var_98], rbx
0x18014291b  xorps   xmm1, xmm1
0x18014291e  mov     [rbp+50h+var_A0], rbx
0x180142922  mov     edi, ecx
0x180142924  mov     [rbp+50h+Handle], rbx
0x180142928  mov     rsi, rdx
0x18014292b  mov     [rbp+50h+var_CC], ebx
0x18014292e  mov     r12d, ebx
0x180142931  mov     [rsp+150h+var_E4], ebx
0x180142935  mov     r14d, ebx
0x180142938  mov     [rbp+50h+var_C8], ebx
0x18014293b  mov     r13d, ebx
0x18014293e  mov     [rsp+150h+var_118], ebx
0x180142942  mov     r15d, ebx
0x180142945  mov     [rsp+150h+var_114], bx
0x18014294a  mov     ecx, ebx
0x18014294c  mov     [rsp+150h+var_F4], ebx
0x180142950  mov     [rsp+150h+var_10C], bx
0x180142955  mov     [rsp+150h+var_F0], rbx
0x18014295a  mov     [rbp+50h+var_78], rbx
0x18014295e  mov     [rsp+150h+var_E8], bx
0x180142963  mov     [rbp+50h+var_70], rbx
0x180142967  movups  [rbp+50h+var_58], xmm0
0x18014296b  movups  [rbp+50h+var_58+0Ch], xmm0
0x18014296f  movups  xmmword ptr [rsp+150h+var_108.Length], xmm0
0x180142974  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm1
0x180142978  movups  [rsp+150h+var_E0], xmm0
0x18014297d  test    r8, r8
0x180142980  jnz     short loc_18014298C
0x180142982  mov     ebx, 0C000000Dh
0x180142987  jmp     loc_18014341E
0x18014298c  test    edi, edi
0x18014298e  mov     eax, 4808h
0x180142993  cmovnz  eax, edi
0x180142996  mov     edi, eax
0x180142998  test    eax, 0FFFF0363h
0x18014299d  jnz     short loc_180142982
0x18014299f  bt      eax, 0Ah
0x1801429a3  jnb     short loc_1801429B1
0x1801429a5  test    rsi, rsi
0x1801429a8  jz      short loc_180142982
0x1801429aa  test    eax, 0FFFFFBF3h
0x1801429af  jnz     short loc_180142982
0x1801429b1  bt      edi, 0Fh
0x1801429b5  jnb     short loc_1801429C4
0x1801429b7  test    rsi, rsi
0x1801429ba  jz      short loc_180142982
0x1801429bc  test    edi, 0FFFF6773h
0x1801429c2  jnz     short loc_180142982
0x1801429c4  mov     ecx, edi
0x1801429c6  and     ecx, 0Ch
0x1801429c9  cmp     ecx, 0Ch
0x1801429cc  jnz     short loc_1801429D8
0x1801429ce  mov     ebx, 0C000000Dh
0x1801429d3  jmp     loc_180143419
0x1801429d8  mov     edx, 1800h
0x1801429dd  and     eax, edx
0x1801429df  cmp     eax, edx
0x1801429e1  jz      short loc_1801429CE
0x1801429e3  test    dil, 10h
0x1801429e7  jz      short loc_1801429F1
0x1801429e9  test    edi, 7080h
0x1801429ef  jnz     short loc_1801429CE
0x1801429f1  mov     edx, edi
0x1801429f3  or      edx, 8
0x1801429f6  test    ecx, ecx
0x1801429f8  cmovnz  edx, edi
0x1801429fb  mov     ecx, edx
0x1801429fd  bts     ecx, 0Eh
0x180142a01  test    edx, 0E410h
0x180142a07  cmovnz  ecx, edx
0x180142a0a  mov     edi, ecx
0x180142a0c  bts     edi, 0Bh
0x180142a10  test    ecx, 1C00h
0x180142a16  cmovnz  edi, ecx
0x180142a19  lea     rcx, [rsp+150h+var_F0]
0x180142a1e  test    dil, dil
0x180142a21  jns     short loc_180142A2A
0x180142a23  call    RtlpInitializeLangRegistryInfo
0x180142a28  jmp     short loc_180142A2F
0x180142a2a  call    RtlpCreateProcessRegistryInfo
0x180142a2f  mov     ebx, eax
0x180142a31  xor     eax, eax
0x180142a33  test    ebx, ebx
0x180142a35  js      loc_18014343A
0x180142a3b  mov     [rbp+50h+var_A8], rax
0x180142a3f  mov     [rsp+150h+var_120], rax
0x180142a44  mov     [rbp+50h+var_68], rax
0x180142a48  test    rsi, rsi
0x180142a4b  jz      loc_180142FCE
0x180142a51  mov     r14d, edi
0x180142a54  mov     rcx, rsi
0x180142a57  and     r14d, 4
0x180142a5b  jz      short loc_180142AD3
0x180142a5d  lea     edx, [rax+4]
0x180142a60  call    RtlpCheckMuiMultiStringSafe
0x180142a65  test    eax, eax
0x180142a67  jns     short loc_180142A7F
0x180142a69  lea     r8, aRtlpsetpreferr_0; "RtlpSetPreferredUILanguages"
0x180142a70  mov     rdx, rsi
0x180142a73  lea     rcx, aAssertFailedIn; "*** ASSERT FAILED: Input parameter: %s,"...
0x180142a7a  call    DbgPrint
0x180142a7f  bt      edi, 0Ah
0x180142a83  jnb     loc_180142B82
0x180142a89  lea     rcx, [rsp+150h+var_E8]
0x180142a8e  call    NtQueryInstallUILanguage
0x180142a93  mov     ebx, eax
0x180142a95  test    eax, eax
0x180142a97  js      loc_1801433A5
0x180142a9d  mov     rcx, gs:60h
0x180142aa6  mov     edx, 8
0x180142aab  mov     r8d, 20Ah
0x180142ab1  mov     rcx, [rcx+30h]
0x180142ab5  call    RtlAllocateHeap_0
0x180142aba  mov     [rbp+50h+var_68], rax
0x180142abe  mov     r12, rax
0x180142ac1  test    rax, rax
0x180142ac4  jnz     short loc_180142ADA
0x180142ac6  mov     ebx, 0C0000017h
0x180142acb  mov     r12, r13
0x180142ace  jmp     loc_1801433A5
0x180142ad3  mov     edx, 55h ; 'U'
0x180142ad8  jmp     short loc_180142A60
0x180142ada  movzx   ecx, [rsp+150h+var_E8]
0x180142adf  lea     rdx, [rsp+150h+var_108]
0x180142ae4  mov     [rsp+150h+var_108.Buffer], r12
0x180142ae9  mov     dword ptr [rsp+150h+var_108.Length], 0AA0000h
0x180142af1  call    RtlLCIDToCultureName
0x180142af6  test    al, al
0x180142af8  jnz     short loc_180142B04
0x180142afa  mov     ebx, 0C000000Dh
0x180142aff  jmp     loc_18014336E
0x180142b04  movzx   r15d, [rsp+150h+var_108.Length]
0x180142b0a  shr     r15, 1
0x180142b0d  test    r14d, r14d
0x180142b10  jz      short loc_180142B32
0x180142b12  lea     rdx, [rbp+50h+var_78]
0x180142b16  mov     rcx, rsi; SourceString
0x180142b19  call    RtlpConvertLCIDsToCultureNames
0x180142b1e  mov     ebx, eax
0x180142b20  test    eax, eax
0x180142b22  js      loc_180143345
0x180142b28  mov     rsi, [rbp+50h+var_78]
0x180142b2c  and     edi, 0FFFFFFFBh
0x180142b2f  or      edi, 8
0x180142b32  xor     r8d, r8d
0x180142b35  lea     rdx, [rsp+150h+var_114]
0x180142b3a  mov     rcx, rsi
0x180142b3d  call    RtlpGetMultiStringLength
0x180142b42  mov     ebx, eax
0x180142b44  test    eax, eax
0x180142b46  js      loc_180143345
0x180142b4c  movzx   r8d, [rsp+150h+var_114]
0x180142b52  lea     rcx, [r15+1]
0x180142b56  inc     r8d
0x180142b59  lea     rcx, [r12+rcx*2]; void *
0x180142b5d  add     r8, r8; Size
0x180142b60  mov     rdx, rsi; Src
0x180142b63  call    memmove
0x180142b68  mov     rcx, [rsp+150h+var_F0]
0x180142b6d  mov     rdx, r12
0x180142b70  call    RtlpAutoCompleteLanguageFallback
0x180142b75  mov     ebx, eax
0x180142b77  test    eax, eax
0x180142b79  js      loc_180143345
0x180142b7f  mov     rsi, r12
0x180142b82  lea     r8, [rsp+150h+var_118]
0x180142b87  mov     rcx, rsi
0x180142b8a  lea     rdx, [rsp+150h+var_E0]
0x180142b8f  call    RtlpGetMultiStringLength
0x180142b94  mov     ebx, eax
0x180142b96  test    eax, eax
0x180142b98  js      loc_180143345
0x180142b9e  movzx   r13d, word ptr [rsp+150h+var_E0]
0x180142ba4  mov     ecx, 2
0x180142ba9  mov     r14d, [rsp+150h+var_118]
0x180142bae  add     r13w, r13w
0x180142bb2  mov     [rbp+50h+var_D0], r13d
0x180142bb6  mov     r12, rsi
0x180142bb9  mov     word ptr [rsp+150h+var_E0], r13w
0x180142bbf  add     r13w, cx
0x180142bc3  mov     qword ptr [rsp+150h+var_E0+8], rsi
0x180142bc8  lea     eax, [r14-1]
0x180142bcc  mov     word ptr [rsp+150h+var_E0+2], r13w
0x180142bd2  cmp     eax, ecx
0x180142bd4  ja      loc_180142DDE
0x180142bda  mov     rcx, gs:60h
0x180142be3  mov     edx, 8
0x180142be8  mov     r8d, 0AAh
0x180142bee  mov     rcx, [rcx+30h]
0x180142bf2  call    RtlAllocateHeap_0
0x180142bf7  mov     r9, rax
0x180142bfa  mov     [rsp+150h+var_120], rax
0x180142bff  xor     eax, eax
0x180142c01  test    r9, r9
0x180142c04  jnz     short loc_180142C13
0x180142c06  mov     ebx, 0C0000017h
0x180142c0b  mov     r13, r9
0x180142c0e  jmp     loc_180143345
0x180142c13  mov     r15, rax
0x180142c16  mov     [rsp+150h+var_110], eax
0x180142c1a  mov     r8d, eax
0x180142c1d  mov     rcx, rsi
0x180142c20  mov     eax, edi
0x180142c22  and     eax, 4
0x180142c25  mov     [rbp+50h+var_88], eax
0x180142c28  mov     [rsp+150h+var_F8], r8d
0x180142c2d  mov     [rbp+50h+var_80], rcx
0x180142c31  cmp     r8d, r14d
0x180142c34  jnb     loc_180142DE8
0x180142c3a  mov     rdx, rcx; SourceString
0x180142c3d  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x180142c41  test    eax, eax
0x180142c43  jz      short loc_180142CC1
0x180142c45  call    RtlInitUnicodeString
0x180142c4a  lea     r8, [rsp+150h+var_F4]
0x180142c4f  mov     edx, 10h
0x180142c54  lea     rcx, [rbp+50h+DestinationString]
0x180142c58  call    RtlUnicodeStringToInteger
0x180142c5d  test    eax, eax
0x180142c5f  js      loc_180142DDE
0x180142c65  mov     r14d, [rsp+150h+var_F4]
0x180142c6a  lea     eax, [r14-1000h]
0x180142c71  test    eax, 0FFFFFBFFh
0x180142c76  jz      loc_180142DDE
0x180142c7c  mov     rax, [rsp+150h+var_120]
0x180142c81  lea     rdx, [rbp+50h+DestinationString]
0x180142c85  mov     ecx, r14d
0x180142c88  mov     [rbp+50h+DestinationString.Buffer], rax
0x180142c8c  mov     dword ptr [rbp+50h+DestinationString.Length], 0AA0000h
0x180142c93  call    RtlLCIDToCultureName
0x180142c98  xor     ecx, ecx
0x180142c9a  test    al, al
0x180142c9c  jz      loc_180142DDE
0x180142ca2  mov     rdx, [rbp+50h+DestinationString.Buffer]
0x180142ca6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180142caa  inc     rax
0x180142cad  cmp     [rdx+rax*2], cx
0x180142cb1  jnz     short loc_180142CAA
0x180142cb3  mov     ecx, [rsp+150h+var_110]
0x180142cb7  inc     ecx
0x180142cb9  add     ecx, eax
0x180142cbb  mov     [rsp+150h+var_110], ecx
0x180142cbf  jmp     short loc_180142CF7
0x180142cc1  call    RtlInitUnicodeString
0x180142cc6  lea     rdx, [rsp+150h+var_F4]
0x180142ccb  lea     rcx, [rbp+50h+DestinationString]
0x180142ccf  call    RtlCultureNameToLCID
0x180142cd4  test    al, al
0x180142cd6  jz      loc_180142DDE
0x180142cdc  mov     r14d, [rsp+150h+var_F4]
0x180142ce1  lea     eax, [r14-1000h]
0x180142ce8  test    eax, 0FFFFFBFFh
0x180142ced  jz      loc_180142DDE
0x180142cf3  mov     rdx, [rbp+50h+DestinationString.Buffer]
0x180142cf7  mov     r8d, [rsp+150h+var_F8]
0x180142cfc  mov     eax, r8d
0x180142cff  test    r8d, r8d
0x180142d02  jz      short loc_180142D77
0x180142d04  sub     eax, 1
0x180142d07  jz      short loc_180142D3F
0x180142d09  cmp     eax, 1
0x180142d0c  jnz     loc_180142DA7
0x180142d12  lea     rax, [rsp+150h+var_114]
0x180142d17  mov     rcx, [rsp+150h+var_F0]
0x180142d1c  lea     r9, [rbp+50h+var_58]
0x180142d20  movzx   r8d, r14w
0x180142d24  mov     [rsp+150h+var_130], rax
0x180142d29  mov     rdx, r15
0x180142d2c  call    RtlpMuiRegGetFallbackInstalledLanguageInfoByLangId
0x180142d31  test    eax, eax
0x180142d33  js      loc_180142DDE
0x180142d39  lea     r15, [rbp+50h+var_58]
0x180142d3d  jmp     short loc_180142DA2
0x180142d3f  bt      edi, 0Bh
0x180142d43  jb      loc_180142DDE
0x180142d49  test    dil, 10h
0x180142d4d  jnz     loc_180142DDE
0x180142d53  test    byte ptr [r15], 1
0x180142d57  jnz     loc_180142DDE
0x180142d5d  test    byte ptr [r15], 2
0x180142d61  jnz     short loc_180142D12
0x180142d63  test    byte ptr [r15], 4
  ... truncated ...
```
