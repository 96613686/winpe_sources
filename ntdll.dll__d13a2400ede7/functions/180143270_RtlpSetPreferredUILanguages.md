# RtlpSetPreferredUILanguages

- ea: `0x180143270`
- end: `0x180143df4`
- name: `RtlpSetPreferredUILanguages`
- size: `2948`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180142c30`

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
- `0x180071890`
- `0x1800c4700`
- `0x1800da250`
- `0x1800da890`
- `0x1800da950`
- `0x1800ec4f0`
- `0x1801422f0`
- `0x180142418`
- `0x180142484`
- `0x1801425f0`
- `0x180142bb0`
- `0x180142c30`
- `0x1801430fc`
- `0x180143270`
- `0x18014d174`
- `0x18015ecc0`
- `0x18015f6d0`
- `0x180160a90`
- `0x180161650`
- `0x180162810`
- `0x180164280`

## string_xrefs

- `0x1801438da`: `\Registry\Machine\System\CurrentControlSet\Control\NLS\Language`
- `0x180143913`: `InstallLanguageFallback`
- `0x180143ba5`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`
- `0x180143a88`: `LanguageConfigurationPending`
- `0x180143c18`: `LanguageConfiguration`

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
      Buffer = &dword_18018B03C;
      v59.Buffer = (wchar_t *)&dword_18018B03C;
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
0x180143270  mov     [rsp-8+arg_18], rbx; RtlpSetPreferredUILanguages
0x180143275  push    rbp
0x180143276  push    rsi
0x180143277  push    rdi
0x180143278  push    r12
0x18014327a  push    r13
0x18014327c  push    r14
0x18014327e  push    r15
0x180143280  lea     rbp, [rsp-20h]
0x180143285  sub     rsp, 120h
0x18014328c  mov     rax, cs:__security_cookie
0x180143293  xor     rax, rsp
0x180143296  mov     [rbp+50h+var_38], rax
0x18014329a  xor     ebx, ebx
0x18014329c  mov     [rbp+50h+var_60], r8
0x1801432a0  mov     [rbp+50h+var_90], rbx
0x1801432a4  xorps   xmm0, xmm0
0x1801432a7  mov     [rbp+50h+var_98], rbx
0x1801432ab  xorps   xmm1, xmm1
0x1801432ae  mov     [rbp+50h+var_A0], rbx
0x1801432b2  mov     edi, ecx
0x1801432b4  mov     [rbp+50h+Handle], rbx
0x1801432b8  mov     rsi, rdx
0x1801432bb  mov     [rbp+50h+var_CC], ebx
0x1801432be  mov     r12d, ebx
0x1801432c1  mov     [rsp+150h+var_E4], ebx
0x1801432c5  mov     r14d, ebx
0x1801432c8  mov     [rbp+50h+var_C8], ebx
0x1801432cb  mov     r13d, ebx
0x1801432ce  mov     [rsp+150h+var_118], ebx
0x1801432d2  mov     r15d, ebx
0x1801432d5  mov     [rsp+150h+var_114], bx
0x1801432da  mov     ecx, ebx
0x1801432dc  mov     [rsp+150h+var_F4], ebx
0x1801432e0  mov     [rsp+150h+var_10C], bx
0x1801432e5  mov     [rsp+150h+var_F0], rbx
0x1801432ea  mov     [rbp+50h+var_78], rbx
0x1801432ee  mov     [rsp+150h+var_E8], bx
0x1801432f3  mov     [rbp+50h+var_70], rbx
0x1801432f7  movups  [rbp+50h+var_58], xmm0
0x1801432fb  movups  [rbp+50h+var_58+0Ch], xmm0
0x1801432ff  movups  xmmword ptr [rsp+150h+var_108.Length], xmm0
0x180143304  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm1
0x180143308  movups  [rsp+150h+var_E0], xmm0
0x18014330d  test    r8, r8
0x180143310  jnz     short loc_18014331C
0x180143312  mov     ebx, 0C000000Dh
0x180143317  jmp     loc_180143DAE
0x18014331c  test    edi, edi
0x18014331e  mov     eax, 4808h
0x180143323  cmovnz  eax, edi
0x180143326  mov     edi, eax
0x180143328  test    eax, 0FFFF0363h
0x18014332d  jnz     short loc_180143312
0x18014332f  bt      eax, 0Ah
0x180143333  jnb     short loc_180143341
0x180143335  test    rsi, rsi
0x180143338  jz      short loc_180143312
0x18014333a  test    eax, 0FFFFFBF3h
0x18014333f  jnz     short loc_180143312
0x180143341  bt      edi, 0Fh
0x180143345  jnb     short loc_180143354
0x180143347  test    rsi, rsi
0x18014334a  jz      short loc_180143312
0x18014334c  test    edi, 0FFFF6773h
0x180143352  jnz     short loc_180143312
0x180143354  mov     ecx, edi
0x180143356  and     ecx, 0Ch
0x180143359  cmp     ecx, 0Ch
0x18014335c  jnz     short loc_180143368
0x18014335e  mov     ebx, 0C000000Dh
0x180143363  jmp     loc_180143DA9
0x180143368  mov     edx, 1800h
0x18014336d  and     eax, edx
0x18014336f  cmp     eax, edx
0x180143371  jz      short loc_18014335E
0x180143373  test    dil, 10h
0x180143377  jz      short loc_180143381
0x180143379  test    edi, 7080h
0x18014337f  jnz     short loc_18014335E
0x180143381  mov     edx, edi
0x180143383  or      edx, 8
0x180143386  test    ecx, ecx
0x180143388  cmovnz  edx, edi
0x18014338b  mov     ecx, edx
0x18014338d  bts     ecx, 0Eh
0x180143391  test    edx, 0E410h
0x180143397  cmovnz  ecx, edx
0x18014339a  mov     edi, ecx
0x18014339c  bts     edi, 0Bh
0x1801433a0  test    ecx, 1C00h
0x1801433a6  cmovnz  edi, ecx
0x1801433a9  lea     rcx, [rsp+150h+var_F0]
0x1801433ae  test    dil, dil
0x1801433b1  jns     short loc_1801433BA
0x1801433b3  call    RtlpInitializeLangRegistryInfo
0x1801433b8  jmp     short loc_1801433BF
0x1801433ba  call    RtlpCreateProcessRegistryInfo
0x1801433bf  mov     ebx, eax
0x1801433c1  xor     eax, eax
0x1801433c3  test    ebx, ebx
0x1801433c5  js      loc_180143DCA
0x1801433cb  mov     [rbp+50h+var_A8], rax
0x1801433cf  mov     [rsp+150h+var_120], rax
0x1801433d4  mov     [rbp+50h+var_68], rax
0x1801433d8  test    rsi, rsi
0x1801433db  jz      loc_18014395E
0x1801433e1  mov     r14d, edi
0x1801433e4  mov     rcx, rsi
0x1801433e7  and     r14d, 4
0x1801433eb  jz      short loc_180143463
0x1801433ed  lea     edx, [rax+4]
0x1801433f0  call    RtlpCheckMuiMultiStringSafe
0x1801433f5  test    eax, eax
0x1801433f7  jns     short loc_18014340F
0x1801433f9  lea     r8, aRtlpsetpreferr_0; "RtlpSetPreferredUILanguages"
0x180143400  mov     rdx, rsi
0x180143403  lea     rcx, aAssertFailedIn; "*** ASSERT FAILED: Input parameter: %s,"...
0x18014340a  call    DbgPrint
0x18014340f  bt      edi, 0Ah
0x180143413  jnb     loc_180143512
0x180143419  lea     rcx, [rsp+150h+var_E8]
0x18014341e  call    NtQueryInstallUILanguage
0x180143423  mov     ebx, eax
0x180143425  test    eax, eax
0x180143427  js      loc_180143D35
0x18014342d  mov     rcx, gs:60h
0x180143436  mov     edx, 8
0x18014343b  mov     r8d, 20Ah
0x180143441  mov     rcx, [rcx+30h]
0x180143445  call    RtlAllocateHeap_0
0x18014344a  mov     [rbp+50h+var_68], rax
0x18014344e  mov     r12, rax
0x180143451  test    rax, rax
0x180143454  jnz     short loc_18014346A
0x180143456  mov     ebx, 0C0000017h
0x18014345b  mov     r12, r13
0x18014345e  jmp     loc_180143D35
0x180143463  mov     edx, 55h ; 'U'
0x180143468  jmp     short loc_1801433F0
0x18014346a  movzx   ecx, [rsp+150h+var_E8]
0x18014346f  lea     rdx, [rsp+150h+var_108]
0x180143474  mov     [rsp+150h+var_108.Buffer], r12
0x180143479  mov     dword ptr [rsp+150h+var_108.Length], 0AA0000h
0x180143481  call    RtlLCIDToCultureName
0x180143486  test    al, al
0x180143488  jnz     short loc_180143494
0x18014348a  mov     ebx, 0C000000Dh
0x18014348f  jmp     loc_180143CFE
0x180143494  movzx   r15d, [rsp+150h+var_108.Length]
0x18014349a  shr     r15, 1
0x18014349d  test    r14d, r14d
0x1801434a0  jz      short loc_1801434C2
0x1801434a2  lea     rdx, [rbp+50h+var_78]
0x1801434a6  mov     rcx, rsi; SourceString
0x1801434a9  call    RtlpConvertLCIDsToCultureNames
0x1801434ae  mov     ebx, eax
0x1801434b0  test    eax, eax
0x1801434b2  js      loc_180143CD5
0x1801434b8  mov     rsi, [rbp+50h+var_78]
0x1801434bc  and     edi, 0FFFFFFFBh
0x1801434bf  or      edi, 8
0x1801434c2  xor     r8d, r8d
0x1801434c5  lea     rdx, [rsp+150h+var_114]
0x1801434ca  mov     rcx, rsi
0x1801434cd  call    RtlpGetMultiStringLength
0x1801434d2  mov     ebx, eax
0x1801434d4  test    eax, eax
0x1801434d6  js      loc_180143CD5
0x1801434dc  movzx   r8d, [rsp+150h+var_114]
0x1801434e2  lea     rcx, [r15+1]
0x1801434e6  inc     r8d
0x1801434e9  lea     rcx, [r12+rcx*2]; void *
0x1801434ed  add     r8, r8; Size
0x1801434f0  mov     rdx, rsi; Src
0x1801434f3  call    memmove
0x1801434f8  mov     rcx, [rsp+150h+var_F0]
0x1801434fd  mov     rdx, r12
0x180143500  call    RtlpAutoCompleteLanguageFallback
0x180143505  mov     ebx, eax
0x180143507  test    eax, eax
0x180143509  js      loc_180143CD5
0x18014350f  mov     rsi, r12
0x180143512  lea     r8, [rsp+150h+var_118]
0x180143517  mov     rcx, rsi
0x18014351a  lea     rdx, [rsp+150h+var_E0]
0x18014351f  call    RtlpGetMultiStringLength
0x180143524  mov     ebx, eax
0x180143526  test    eax, eax
0x180143528  js      loc_180143CD5
0x18014352e  movzx   r13d, word ptr [rsp+150h+var_E0]
0x180143534  mov     ecx, 2
0x180143539  mov     r14d, [rsp+150h+var_118]
0x18014353e  add     r13w, r13w
0x180143542  mov     [rbp+50h+var_D0], r13d
0x180143546  mov     r12, rsi
0x180143549  mov     word ptr [rsp+150h+var_E0], r13w
0x18014354f  add     r13w, cx
0x180143553  mov     qword ptr [rsp+150h+var_E0+8], rsi
0x180143558  lea     eax, [r14-1]
0x18014355c  mov     word ptr [rsp+150h+var_E0+2], r13w
0x180143562  cmp     eax, ecx
0x180143564  ja      loc_18014376E
0x18014356a  mov     rcx, gs:60h
0x180143573  mov     edx, 8
0x180143578  mov     r8d, 0AAh
0x18014357e  mov     rcx, [rcx+30h]
0x180143582  call    RtlAllocateHeap_0
0x180143587  mov     r9, rax
0x18014358a  mov     [rsp+150h+var_120], rax
0x18014358f  xor     eax, eax
0x180143591  test    r9, r9
0x180143594  jnz     short loc_1801435A3
0x180143596  mov     ebx, 0C0000017h
0x18014359b  mov     r13, r9
0x18014359e  jmp     loc_180143CD5
0x1801435a3  mov     r15, rax
0x1801435a6  mov     [rsp+150h+var_110], eax
0x1801435aa  mov     r8d, eax
0x1801435ad  mov     rcx, rsi
0x1801435b0  mov     eax, edi
0x1801435b2  and     eax, 4
0x1801435b5  mov     [rbp+50h+var_88], eax
0x1801435b8  mov     [rsp+150h+var_F8], r8d
0x1801435bd  mov     [rbp+50h+var_80], rcx
0x1801435c1  cmp     r8d, r14d
0x1801435c4  jnb     loc_180143778
0x1801435ca  mov     rdx, rcx; SourceString
0x1801435cd  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x1801435d1  test    eax, eax
0x1801435d3  jz      short loc_180143651
0x1801435d5  call    RtlInitUnicodeString
0x1801435da  lea     r8, [rsp+150h+var_F4]
0x1801435df  mov     edx, 10h
0x1801435e4  lea     rcx, [rbp+50h+DestinationString]
0x1801435e8  call    RtlUnicodeStringToInteger
0x1801435ed  test    eax, eax
0x1801435ef  js      loc_18014376E
0x1801435f5  mov     r14d, [rsp+150h+var_F4]
0x1801435fa  lea     eax, [r14-1000h]
0x180143601  test    eax, 0FFFFFBFFh
0x180143606  jz      loc_18014376E
0x18014360c  mov     rax, [rsp+150h+var_120]
0x180143611  lea     rdx, [rbp+50h+DestinationString]
0x180143615  mov     ecx, r14d
0x180143618  mov     [rbp+50h+DestinationString.Buffer], rax
0x18014361c  mov     dword ptr [rbp+50h+DestinationString.Length], 0AA0000h
0x180143623  call    RtlLCIDToCultureName
0x180143628  xor     ecx, ecx
0x18014362a  test    al, al
0x18014362c  jz      loc_18014376E
0x180143632  mov     rdx, [rbp+50h+DestinationString.Buffer]
0x180143636  or      rax, 0FFFFFFFFFFFFFFFFh
0x18014363a  inc     rax
0x18014363d  cmp     [rdx+rax*2], cx
0x180143641  jnz     short loc_18014363A
0x180143643  mov     ecx, [rsp+150h+var_110]
0x180143647  inc     ecx
0x180143649  add     ecx, eax
0x18014364b  mov     [rsp+150h+var_110], ecx
0x18014364f  jmp     short loc_180143687
0x180143651  call    RtlInitUnicodeString
0x180143656  lea     rdx, [rsp+150h+var_F4]
0x18014365b  lea     rcx, [rbp+50h+DestinationString]
0x18014365f  call    RtlCultureNameToLCID
0x180143664  test    al, al
0x180143666  jz      loc_18014376E
0x18014366c  mov     r14d, [rsp+150h+var_F4]
0x180143671  lea     eax, [r14-1000h]
0x180143678  test    eax, 0FFFFFBFFh
0x18014367d  jz      loc_18014376E
0x180143683  mov     rdx, [rbp+50h+DestinationString.Buffer]
0x180143687  mov     r8d, [rsp+150h+var_F8]
0x18014368c  mov     eax, r8d
0x18014368f  test    r8d, r8d
0x180143692  jz      short loc_180143707
0x180143694  sub     eax, 1
0x180143697  jz      short loc_1801436CF
0x180143699  cmp     eax, 1
0x18014369c  jnz     loc_180143737
0x1801436a2  lea     rax, [rsp+150h+var_114]
0x1801436a7  mov     rcx, [rsp+150h+var_F0]
0x1801436ac  lea     r9, [rbp+50h+var_58]
0x1801436b0  movzx   r8d, r14w
0x1801436b4  mov     [rsp+150h+var_130], rax
0x1801436b9  mov     rdx, r15
0x1801436bc  call    RtlpMuiRegGetFallbackInstalledLanguageInfoByLangId
0x1801436c1  test    eax, eax
0x1801436c3  js      loc_18014376E
0x1801436c9  lea     r15, [rbp+50h+var_58]
0x1801436cd  jmp     short loc_180143732
0x1801436cf  bt      edi, 0Bh
0x1801436d3  jb      loc_18014376E
0x1801436d9  test    dil, 10h
0x1801436dd  jnz     loc_18014376E
0x1801436e3  test    byte ptr [r15], 1
0x1801436e7  jnz     loc_18014376E
0x1801436ed  test    byte ptr [r15], 2
0x1801436f1  jnz     short loc_1801436A2
0x1801436f3  test    byte ptr [r15], 4
  ... truncated ...
```
