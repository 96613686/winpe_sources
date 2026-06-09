# PrjfMergeEnumerationResults

- ea: `0x140025a78`
- end: `0x14002609c`
- name: `PrjfMergeEnumerationResults`
- size: `1572`
- prototype: `__int64 __fastcall(__int64, __int64 *, int, unsigned int, __int64, char, _DWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140024b24`

## callees

- `0x14000b1d0`
- `0x14000d128`
- `0x140024ad8`
- `0x1400258f8`
- `0x140025944`
- `0x140025a78`
- `0x1400287d4`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140025db4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140025db4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025cea`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d15`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d37`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d59`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d6f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d91`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025cea`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d15`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d37`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d59`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d6f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025d91`

## pseudocode

```c
__int64 __fastcall PrjfMergeEnumerationResults(
        __int64 a1,
        __int64 *a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        char a6,
        _DWORD *a7,
        _QWORD *a8,
        _DWORD *a9)
{
  unsigned int v9; // r13d
  int v10; // r11d
  int v11; // r14d
  int v12; // r10d
  int v13; // esi
  int v14; // r15d
  __int64 i; // rcx
  int v16; // eax
  __int64 *v18; // rax
  unsigned int v19; // esi
  int v20; // r12d
  __int64 v21; // r14
  __int64 v22; // rsi
  int v23; // eax
  int CurrentEntryFileName; // r15d
  int v25; // eax
  const UNICODE_STRING *v26; // rdx
  LONG v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // r15d
  int *CurrentEnumEntryFromContext; // rax
  int v32; // r9d
  bool v33; // r8
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // esi
  unsigned int *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v42; // [rsp+64h] [rbp-A4h]
  int v43; // [rsp+68h] [rbp-A0h]
  int v44; // [rsp+6Ch] [rbp-9Ch]
  WCHAR *v45; // [rsp+70h] [rbp-98h] BYREF
  unsigned int *v46; // [rsp+78h] [rbp-90h]
  UNICODE_STRING String2; // [rsp+80h] [rbp-88h] BYREF
  __int64 v48; // [rsp+90h] [rbp-78h]
  __int64 v49; // [rsp+98h] [rbp-70h] BYREF
  UNICODE_STRING String1; // [rsp+A0h] [rbp-68h] BYREF
  WCHAR *v51; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int *v52; // [rsp+B8h] [rbp-50h] BYREF
  __int64 *v53; // [rsp+C0h] [rbp-48h]
  char v54; // [rsp+110h] [rbp+8h]
  __int64 *v55; // [rsp+118h] [rbp+10h]
  int v56; // [rsp+120h] [rbp+18h]
  unsigned int v57; // [rsp+128h] [rbp+20h]

  v57 = a4;
  v56 = a3;
  v55 = a2;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v41 = 0;
  v52 = 0;
  v49 = 0;
  *a9 = 0;
  *a7 = 0;
  for ( i = *a2; (__int64 *)i != a2; i = *(_QWORD *)i )
  {
    ++v10;
    v16 = *(_DWORD *)(i + 20);
    switch ( v16 )
    {
      case -2147483642:
        ++v11;
        break;
      case -1073741809:
        ++v12;
        break;
      case -2147483643:
        ++v13;
        break;
      default:
        if ( v16 < 0 )
        {
          v14 = 1;
          v9 = *(_DWORD *)(i + 20);
          goto LABEL_13;
        }
        break;
    }
  }
LABEL_13:
  if ( v14 )
    return v9;
  if ( v12 == v10 )
    return 3221225487LL;
  if ( v12 + v11 == v10 )
    return 2147483654LL;
  if ( v13 )
  {
    if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE2(xmmword_14001A3D0) & 4;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        530,
        (_DWORD)a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        18,
        23,
        (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
        16,
        5);
    }
    *a7 = 0;
    return 3221225487LL;
  }
  v18 = a2;
  v53 = a2;
  v19 = 0;
  v42 = 0;
  v43 = 0;
  v46 = 0;
  v20 = 0;
  v44 = 0;
  v54 = 1;
LABEL_24:
  if ( v19 < a4 )
  {
    v21 = 0;
    v48 = 0;
    v22 = *v18;
    if ( (__int64 *)*v18 == a2 )
      goto LABEL_49;
    while ( 1 )
    {
      v23 = *(_DWORD *)(v22 + 20);
      if ( v23 == -2147483642 || v23 == -1073741809 )
        goto LABEL_47;
      if ( !v21 )
        goto LABEL_46;
      v45 = 0;
      v51 = 0;
      String1 = 0;
      String2 = 0;
      CurrentEntryFileName = PrjfGetCurrentEntryFileName(v21, (__int64 *)&v45);
      v25 = PrjfGetCurrentEntryFileName(v22, (__int64 *)&v51);
      if ( CurrentEntryFileName )
        break;
LABEL_47:
      v22 = *(_QWORD *)v22;
      if ( (__int64 *)v22 == v55 )
      {
        v20 = v44;
LABEL_49:
        if ( !v21 )
          goto LABEL_82;
        v30 = PrjfGetCurrentEntryFileName(v21, &v49);
        LODWORD(v45) = v30;
        CurrentEnumEntryFromContext = PrjfGetCurrentEnumEntryFromContext(v21, 0, 0, 0);
        if ( !CurrentEnumEntryFromContext )
          goto LABEL_61;
        v33 = 0;
        if ( *(_DWORD *)(v21 + 44) == 33 )
        {
          v33 = CurrentEnumEntryFromContext[2] == -1610612702;
        }
        else if ( *(_DWORD *)(v21 + 44) == 60
               || *(_DWORD *)(v21 + 44) == 63
               || *(_DWORD *)(v21 + 44) == 78
               || *(_DWORD *)(v21 + 44) == 79
               || (unsigned int)(*(_DWORD *)(v21 + 44) - 80) <= 1 )
        {
          v33 = CurrentEnumEntryFromContext[17] == -1610612702;
        }
        if ( v33 )
        {
          PrjfAdvanceToNextEnumEntry(v21);
          *a8 = v49;
          *a9 = v30;
          a2 = v55;
          v19 = v42;
          v18 = v53;
          a4 = v57;
        }
        else
        {
LABEL_61:
          LOBYTE(v32) = v54;
          v34 = PrjfTranslateCurrentEnumEntry(
                  v57 - v42,
                  v21,
                  v56,
                  v32,
                  v57 - v42,
                  a5 + v42,
                  a6,
                  (__int64)&v52,
                  (__int64)&v41);
          v9 = v34;
          if ( v34 == -2147483643 )
          {
            if ( !v54 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v36, v35);
            v20 = v41;
            if ( !v41 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v36, v35);
            goto LABEL_82;
          }
          if ( v34 < 0 )
            return v9;
          v37 = v41;
          if ( !v41 )
            goto LABEL_82;
          if ( v20 )
          {
            if ( v54 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v36, v35);
            v43 += (v20 + 7) & 0xFFFFFFF8;
          }
          v38 = v46;
          if ( v46 )
          {
            if ( v54 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v36, v35);
              v38 = v46;
            }
            if ( *v38 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v36, v35);
            *v46 = (v20 + 7) & 0xFFFFFFF8;
            if ( (v9 & 0x80000000) != 0 )
              return v9;
          }
          v54 = 0;
          v20 = v37;
          v44 = v37;
          v46 = v52;
          v19 = ((v37 + 7) & 0xFFFFFFF8) + v42;
          v42 = v19;
          if ( !PrjfAdvanceToNextEnumEntry(v21) && !PrjfAdvanceToNextEnumEntry(v21) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v40, v39);
          *a8 = v49;
          *a9 = v30;
          a2 = v55;
          v18 = v53;
          a4 = v57;
          if ( (*(_BYTE *)(v21 + 40) & 2) != 0 )
            goto LABEL_82;
        }
        goto LABEL_24;
      }
    }
    if ( !v25 )
    {
LABEL_46:
      v48 = v22;
      v21 = v22;
      goto LABEL_47;
    }
    String1.MaximumLength = CurrentEntryFileName;
    String1.Length = CurrentEntryFileName;
    String1.Buffer = v45;
    String2.MaximumLength = v25;
    String2.Length = v25;
    String2.Buffer = v51;
    if ( RtlEqualUnicodeString(&String1, &::String2, 1u) )
    {
      v26 = &::String2;
LABEL_36:
      v27 = (RtlEqualUnicodeString(&String2, v26, 1u) != 0) - 1;
      goto LABEL_41;
    }
    if ( RtlEqualUnicodeString(&String1, &stru_140015520, 1u) )
    {
      if ( !RtlEqualUnicodeString(&String2, &::String2, 1u) )
      {
        v26 = &stru_140015520;
        goto LABEL_36;
      }
    }
    else if ( !RtlEqualUnicodeString(&String2, &::String2, 1u) && !RtlEqualUnicodeString(&String2, &stru_140015520, 1u) )
    {
      v27 = RtlCompareUnicodeString(&String1, &String2, 1u);
      goto LABEL_41;
    }
    v27 = 1;
LABEL_41:
    if ( v27 <= 0 )
    {
      if ( !v27 && !PrjfAdvanceToNextEnumEntry(v22) && !PrjfAdvanceToNextEnumEntry(v22) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v29, v28);
      goto LABEL_47;
    }
    goto LABEL_46;
  }
LABEL_82:
  *a7 = v20 + v43;
  return v9;
}

```

## disassembly

```asm
0x140025a78  mov     rax, rsp
0x140025a7b  mov     [rax+20h], r9d
0x140025a7f  mov     [rax+18h], r8d
0x140025a83  mov     [rax+10h], rdx
0x140025a87  mov     [rax+8], rcx
0x140025a8b  push    rsi
0x140025a8c  push    rdi
0x140025a8d  push    r12
0x140025a8f  push    r13
0x140025a91  push    r14
0x140025a93  push    r15
0x140025a95  sub     rsp, 0D8h
0x140025a9c  xor     r13d, r13d
0x140025a9f  xor     r11d, r11d
0x140025aa2  xor     r14d, r14d
0x140025aa5  xor     r10d, r10d
0x140025aa8  xor     esi, esi
0x140025aaa  xor     r15d, r15d
0x140025aad  mov     [rsp+108h+var_A8], esi
0x140025ab1  mov     [rax-50h], rsi
0x140025ab5  mov     [rax-70h], rsi
0x140025ab9  mov     rax, [rsp+108h+arg_40]
0x140025ac1  mov     [rax], esi
0x140025ac3  mov     r12, [rsp+108h+arg_30]
0x140025acb  mov     [r12], esi
0x140025acf  mov     rcx, [rdx]
0x140025ad2  lea     edi, [rsi+1]
0x140025ad5  jmp     short loc_140025B07
0x140025ad7  add     r11d, edi
0x140025ada  mov     eax, [rcx+14h]
0x140025add  cmp     eax, 80000006h
0x140025ae2  jnz     short loc_140025AE9
0x140025ae4  add     r14d, edi
0x140025ae7  jmp     short loc_140025B04
0x140025ae9  cmp     eax, 0C000000Fh
0x140025aee  jnz     short loc_140025AF5
0x140025af0  add     r10d, edi
0x140025af3  jmp     short loc_140025B04
0x140025af5  cmp     eax, 80000005h
0x140025afa  jnz     short loc_140025B00
0x140025afc  add     esi, edi
0x140025afe  jmp     short loc_140025B04
0x140025b00  test    eax, eax
0x140025b02  js      short loc_140025B0E
0x140025b04  mov     rcx, [rcx]
0x140025b07  cmp     rcx, rdx
0x140025b0a  jnz     short loc_140025AD7
0x140025b0c  jmp     short loc_140025B14
0x140025b0e  mov     r15d, edi
0x140025b11  mov     r13d, eax
0x140025b14  test    r15d, r15d
0x140025b17  jnz     loc_140026086
0x140025b1d  cmp     r10d, r11d
0x140025b20  jnz     short loc_140025B2C
0x140025b22  mov     eax, 0C000000Fh
0x140025b27  jmp     loc_140026089
0x140025b2c  lea     ecx, [r10+r14]
0x140025b30  cmp     ecx, r11d
0x140025b33  jnz     short loc_140025B3F
0x140025b35  mov     eax, 80000006h
0x140025b3a  jmp     loc_140026089
0x140025b3f  test    esi, esi
0x140025b41  jz      loc_140025BC7
0x140025b47  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140025b4d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025b54  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025b5b  setnz   r8b
0x140025b5f  and     dl, 4
0x140025b62  jnz     short loc_140025B69
0x140025b64  test    r8b, r8b
0x140025b67  jz      short loc_140025BBA
0x140025b69  mov     ecx, 212h
0x140025b6e  mov     [rsp+108h+var_B8], 80000005h
0x140025b76  mov     [rsp+108h+var_C0], 0B10h
0x140025b7e  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140025b85  mov     [rsp+108h+var_C8], rax
0x140025b8a  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140025b91  mov     [rsp+108h+var_D0], rax
0x140025b96  mov     [rsp+108h+var_D8], 17h
0x140025b9d  mov     dword ptr [rsp+108h+var_E0], 12h
0x140025ba5  mov     byte ptr [rsp+108h+var_E8], 2
0x140025baa  mov     r9, cs:WPP_GLOBAL_Control
0x140025bb1  mov     r9, [r9+40h]
0x140025bb5  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140025bba  mov     dword ptr [r12], 0
0x140025bc2  jmp     loc_140025B22
0x140025bc7  mov     rax, rdx
0x140025bca  mov     [rsp+108h+var_48], rdx
0x140025bd2  xor     esi, esi
0x140025bd4  mov     [rsp+108h+var_A4], esi
0x140025bd8  mov     [rsp+108h+var_A0], esi
0x140025bdc  xor     ecx, ecx
0x140025bde  mov     [rsp+108h+var_90], rcx
0x140025be3  xor     r12d, r12d
0x140025be6  mov     [rsp+108h+var_9C], r12d
0x140025beb  mov     [rsp+108h+arg_0], dil
0x140025bf3  cmp     esi, r9d
0x140025bf6  jnb     loc_140026075
0x140025bfc  xor     r14d, r14d
0x140025bff  mov     [rsp+108h+var_78], r14
0x140025c07  mov     rsi, [rax]
0x140025c0a  cmp     rsi, rdx
0x140025c0d  jz      loc_140025E05
0x140025c13  mov     r12, [rsp+108h+arg_8]
0x140025c1b  mov     eax, [rsi+14h]
0x140025c1e  cmp     eax, 80000006h
0x140025c23  jz      loc_140025DF4
0x140025c29  cmp     eax, 0C000000Fh
0x140025c2e  jz      loc_140025DF4
0x140025c34  test    r14, r14
0x140025c37  jz      loc_140025DE9
0x140025c3d  mov     [rsp+108h+var_98], 0
0x140025c46  mov     [rsp+108h+var_58], 0
0x140025c52  xorps   xmm0, xmm0
0x140025c55  movups  xmmword ptr [rsp+108h+String1.Length], xmm0
0x140025c5d  xorps   xmm1, xmm1
0x140025c60  movups  xmmword ptr [rsp+108h+String2.Length], xmm1
0x140025c68  lea     rdx, [rsp+108h+var_98]
0x140025c6d  mov     rcx, r14
0x140025c70  call    PrjfGetCurrentEntryFileName
0x140025c75  mov     r15d, eax
0x140025c78  lea     rdx, [rsp+108h+var_58]
0x140025c80  mov     rcx, rsi
0x140025c83  call    PrjfGetCurrentEntryFileName
0x140025c88  test    r15d, r15d
0x140025c8b  jz      loc_140025DF4
0x140025c91  test    eax, eax
0x140025c93  jz      loc_140025DE9
0x140025c99  mov     [rsp+108h+String1.MaximumLength], r15w
0x140025ca2  mov     [rsp+108h+String1.Length], r15w
0x140025cab  mov     rcx, [rsp+108h+var_98]
0x140025cb0  mov     [rsp+108h+String1.Buffer], rcx
0x140025cb8  mov     [rsp+108h+String2.MaximumLength], ax
0x140025cc0  mov     [rsp+108h+String2.Length], ax
0x140025cc8  mov     rax, [rsp+108h+var_58]
0x140025cd0  mov     [rsp+108h+String2.Buffer], rax
0x140025cd8  mov     r8b, dil; CaseInSensitive
0x140025cdb  lea     rdx, String2; String2
0x140025ce2  lea     rcx, [rsp+108h+String1]; String1
0x140025cea  call    cs:__imp_RtlEqualUnicodeString
0x140025cf1  nop     dword ptr [rax+rax+00h]
0x140025cf6  mov     r8b, dil; CaseInSensitive
0x140025cf9  test    al, al
0x140025cfb  jz      short loc_140025D06
0x140025cfd  lea     rdx, String2
0x140025d04  jmp     short loc_140025D51
0x140025d06  lea     rdx, stru_140015520; String2
0x140025d0d  lea     rcx, [rsp+108h+String1]; String1
0x140025d15  call    cs:__imp_RtlEqualUnicodeString
0x140025d1c  nop     dword ptr [rax+rax+00h]
0x140025d21  mov     r8b, dil; CaseInSensitive
0x140025d24  lea     rdx, String2; String2
0x140025d2b  lea     rcx, [rsp+108h+String2]; String1
0x140025d33  test    al, al
0x140025d35  jz      short loc_140025D6F
0x140025d37  call    cs:__imp_RtlEqualUnicodeString
0x140025d3e  nop     dword ptr [rax+rax+00h]
0x140025d43  test    al, al
0x140025d45  jnz     short loc_140025DC2
0x140025d47  mov     r8b, dil; CaseInSensitive
0x140025d4a  lea     rdx, stru_140015520; String2
0x140025d51  lea     rcx, [rsp+108h+String2]; String1
0x140025d59  call    cs:__imp_RtlEqualUnicodeString
0x140025d60  nop     dword ptr [rax+rax+00h]
0x140025d65  neg     al
0x140025d67  sbb     eax, eax
0x140025d69  neg     eax
0x140025d6b  sub     eax, edi
0x140025d6d  jmp     short loc_140025DC4
0x140025d6f  call    cs:__imp_RtlEqualUnicodeString
0x140025d76  nop     dword ptr [rax+rax+00h]
0x140025d7b  test    al, al
0x140025d7d  jnz     short loc_140025DC2
0x140025d7f  mov     r8b, dil; CaseInSensitive
0x140025d82  lea     rdx, stru_140015520; String2
0x140025d89  lea     rcx, [rsp+108h+String2]; String1
0x140025d91  call    cs:__imp_RtlEqualUnicodeString
0x140025d98  nop     dword ptr [rax+rax+00h]
0x140025d9d  test    al, al
0x140025d9f  jnz     short loc_140025DC2
0x140025da1  mov     r8b, dil; CaseInSensitive
0x140025da4  lea     rdx, [rsp+108h+String2]; String2
0x140025dac  lea     rcx, [rsp+108h+String1]; String1
0x140025db4  call    cs:__imp_RtlCompareUnicodeString
0x140025dbb  nop     dword ptr [rax+rax+00h]
0x140025dc0  jmp     short loc_140025DC4
0x140025dc2  mov     eax, edi
0x140025dc4  test    eax, eax
0x140025dc6  jg      short loc_140025DE9
0x140025dc8  jnz     short loc_140025DF4
0x140025dca  mov     rcx, rsi
0x140025dcd  call    PrjfAdvanceToNextEnumEntry
0x140025dd2  test    al, al
0x140025dd4  jnz     short loc_140025DF4
0x140025dd6  mov     rcx, rsi
0x140025dd9  call    PrjfAdvanceToNextEnumEntry
0x140025dde  test    al, al
0x140025de0  jnz     short loc_140025DF4
0x140025de2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140025de7  jmp     short loc_140025DF4
0x140025de9  mov     [rsp+108h+var_78], rsi
0x140025df1  mov     r14, rsi
0x140025df4  mov     rsi, [rsi]
0x140025df7  cmp     rsi, r12
0x140025dfa  jnz     loc_140025C1B
0x140025e00  mov     r12d, [rsp+108h+var_9C]
0x140025e05  test    r14, r14
0x140025e08  jz      loc_140026075
0x140025e0e  lea     rdx, [rsp+108h+var_70]
0x140025e16  mov     rcx, r14
0x140025e19  call    PrjfGetCurrentEntryFileName
0x140025e1e  mov     r15d, eax
0x140025e21  mov     dword ptr [rsp+108h+var_98], eax
0x140025e25  xor     r9d, r9d
0x140025e28  xor     r8d, r8d
0x140025e2b  xor     edx, edx
0x140025e2d  mov     rcx, r14
0x140025e30  call    PrjfGetCurrentEnumEntryFromContext
0x140025e35  test    rax, rax
0x140025e38  jz      loc_140025ED0
0x140025e3e  xor     r8b, r8b
0x140025e41  mov     edx, [r14+2Ch]
0x140025e45  sub     edx, 21h ; '!'
0x140025e48  jz      short loc_140025E75
0x140025e4a  sub     edx, 1Bh
0x140025e4d  jz      short loc_140025E68
0x140025e4f  sub     edx, 3
0x140025e52  jz      short loc_140025E68
0x140025e54  sub     edx, 0Fh
0x140025e57  jz      short loc_140025E68
0x140025e59  sub     edx, 1
0x140025e5c  jz      short loc_140025E68
0x140025e5e  sub     edx, 1
0x140025e61  jz      short loc_140025E68
0x140025e63  cmp     edx, 1
0x140025e66  jnz     short loc_140025E84
0x140025e68  cmp     dword ptr [rax+44h], 0A0000022h
0x140025e6f  setz    r8b
0x140025e73  jmp     short loc_140025E84
0x140025e75  movzx   r8d, r8b
0x140025e79  cmp     dword ptr [rax+8], 0A0000022h
0x140025e80  cmovz   r8d, edi
0x140025e84  test    r8b, r8b
0x140025e87  jz      short loc_140025ED0
0x140025e89  mov     rcx, r14
0x140025e8c  call    PrjfAdvanceToNextEnumEntry
0x140025e91  mov     rax, [rsp+108h+var_70]
0x140025e99  mov     rcx, [rsp+108h+arg_38]
0x140025ea1  mov     [rcx], rax
0x140025ea4  mov     rax, [rsp+108h+arg_40]
0x140025eac  mov     [rax], r15d
0x140025eaf  mov     rdx, [rsp+108h+arg_8]
0x140025eb7  mov     esi, [rsp+108h+var_A4]
0x140025ebb  mov     rax, [rsp+108h+var_48]
0x140025ec3  mov     r9d, [rsp+108h+arg_18]
0x140025ecb  jmp     loc_140025BF3
0x140025ed0  mov     eax, [rsp+108h+var_A4]
0x140025ed4  mov     edx, eax
0x140025ed6  add     rdx, [rsp+108h+arg_20]
0x140025ede  mov     ecx, [rsp+108h+arg_18]
0x140025ee5  sub     ecx, eax
0x140025ee7  lea     rax, [rsp+108h+var_A8]
0x140025eec  mov     [rsp+108h+var_C8], rax
0x140025ef1  lea     rax, [rsp+108h+var_50]
0x140025ef9  mov     [rsp+108h+var_D0], rax
0x140025efe  mov     al, [rsp+108h+arg_28]
0x140025f05  mov     byte ptr [rsp+108h+var_D8], al
0x140025f09  mov     [rsp+108h+var_E0], rdx
0x140025f0e  mov     [rsp+108h+var_E8], ecx
0x140025f12  mov     sil, [rsp+108h+arg_0]
0x140025f1a  mov     r9b, sil
0x140025f1d  mov     r8d, [rsp+108h+arg_10]
0x140025f25  mov     rdx, r14
0x140025f28  call    PrjfTranslateCurrentEnumEntry
0x140025f2d  mov     r13d, eax
0x140025f30  cmp     eax, 80000005h
0x140025f35  jnz     short loc_140025F59
0x140025f37  test    sil, sil
0x140025f3a  jnz     short loc_140025F41
0x140025f3c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140025f41  mov     r12d, [rsp+108h+var_A8]
0x140025f46  test    r12d, r12d
0x140025f49  jnz     loc_140026075
0x140025f4f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140025f54  jmp     loc_140026075
0x140025f59  test    eax, eax
0x140025f5b  js      loc_140026086
0x140025f61  mov     esi, [rsp+108h+var_A8]
0x140025f65  test    esi, esi
0x140025f67  jz      loc_140026075
0x140025f6d  test    r12d, r12d
0x140025f70  jz      short loc_140025F8D
0x140025f72  cmp     [rsp+108h+arg_0], 0
0x140025f7a  jz      short loc_140025F81
0x140025f7c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140025f81  lea     eax, [r12+7]
0x140025f86  and     eax, 0FFFFFFF8h
0x140025f89  add     [rsp+108h+var_A0], eax
0x140025f8d  mov     rax, [rsp+108h+var_90]
0x140025f92  test    rax, rax
  ... truncated ...
```
