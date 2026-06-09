# CDplAccount::SaveMetadata(HKEY__ *,int,unsigned __int64)

- ea: `0x1800a7244`
- end: `0x1800a7d34`
- name: `?SaveMetadata@CDplAccount@@AEAAJPEAUHKEY__@@H_K@Z`
- size: `2800`
- prototype: `int(CDplAccount *__hidden this, HKEY, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bbae0`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800961b0`
- `0x18009a5a8`
- `0x1800a7244`
- `0x1800d5af8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7573`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a75cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a760c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7770`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a783e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7aaa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7afc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7c91`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7573`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a75cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a760c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7770`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a783e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7aaa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7afc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7c91`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a753b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a76f1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a773d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a77c2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a780b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7a83`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7b52`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7ba1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7c11`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7c5c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a753b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a76f1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a773d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a77c2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a780b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7a83`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7b52`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7ba1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7c11`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800a7c5c`

## string_xrefs

- `0x1800a79f6`: `CreateTime`

## pseudocode

```c
__int64 __fastcall CDplAccount::SaveMetadata(CDplAccount *this, HKEY a2, int a3, __int64 a4)
{
  unsigned __int16 *v7; // r14
  int v8; // ecx
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  LSTATUS v15; // eax
  int v16; // ecx
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  CDplAccount *i; // r12
  int v21; // edx
  bool v22; // cf
  LSTATUS v23; // eax
  int v24; // ecx
  LSTATUS v25; // eax
  LSTATUS v26; // eax
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  LSTATUS v29; // eax
  int v30; // ecx
  const unsigned __int16 *v31; // rdx
  int v32; // ecx
  const unsigned __int16 *v33; // rdx
  LSTATUS v34; // eax
  LSTATUS v35; // eax
  LSTATUS v36; // eax
  LSTATUS v37; // eax
  LSTATUS v38; // eax
  LSTATUS v39; // eax
  _DWORD *v40; // rdi
  LSTATUS v41; // eax
  LSTATUS v42; // eax
  char lpData; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v45[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v46; // [rsp+90h] [rbp+40h] BYREF
  __int64 Data; // [rsp+A8h] [rbp+58h] BYREF

  Data = a4;
  v46 = 0;
  v7 = 0;
  v45[0] = 0;
  if ( g_DplDbgBreakEnabled )
    __int2c();
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 36, 22);
  if ( *((_QWORD *)this + 8) )
  {
    fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 33);
    v10 = CDplService::RegSetStringValue(a2, v9, L"PrimaryIdentity", *((const unsigned __int16 **)this + 8));
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                36,
                33) < 0 )
      goto LABEL_129;
  }
  if ( *((_QWORD *)this + 10) )
  {
    fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 45);
    v10 = CDplService::RegSetStringValue(a2, v11, L"AppId", *((const unsigned __int16 **)this + 10));
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                36,
                45) < 0 )
      goto LABEL_129;
  }
  else if ( a3 )
  {
    v17 = RegDeleteValueW(a2, L"AppId");
    v10 = v17;
    if ( (v17 & 0xFFFFFFFD) != 0 )
    {
      if ( v17 > 0 )
        v10 = (unsigned __int16)v17 | 0x80070000;
      lpData = 53;
      goto LABEL_22;
    }
  }
  if ( *((_QWORD *)this + 9) )
  {
    fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 66);
    v10 = CDplService::RegSetStringValue(a2, v12, L"SecondaryIdentities", *((const unsigned __int16 **)this + 9));
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                36,
                66) < 0 )
      goto LABEL_129;
  }
  if ( *((_QWORD *)this + 22) )
  {
    fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 78);
    v10 = CDplService::RegSetStringValue(a2, v13, L"RecoveryAccountHash", *((const unsigned __int16 **)this + 22));
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                36,
                78) < 0 )
      goto LABEL_129;
  }
  else if ( a3 )
  {
    v18 = RegDeleteValueW(a2, L"RecoveryAccountHash");
    v10 = v18;
    if ( (v18 & 0xFFFFFFFD) != 0 )
    {
      if ( v18 > 0 )
        v10 = (unsigned __int16)v18 | 0x80070000;
      lpData = 86;
      goto LABEL_22;
    }
  }
  if ( *((_QWORD *)this + 23) )
  {
    fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 99);
    v10 = CDplService::RegSetStringValue(a2, v14, L"RecoveryPolicyHash", *((const unsigned __int16 **)this + 23));
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                36,
                99) < 0 )
      goto LABEL_129;
  }
  else if ( a3 )
  {
    v19 = RegDeleteValueW(a2, L"RecoveryPolicyHash");
    v10 = v19;
    if ( (v19 & 0xFFFFFFFD) != 0 )
    {
      if ( v19 > 0 )
        v10 = (unsigned __int16)v19 | 0x80070000;
      lpData = 107;
      goto LABEL_22;
    }
  }
  v15 = RegSetKeyValueW(a2, 0, L"Lsn", 0xBu, &Data, 8u);
  v10 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    lpData = 124;
    goto LABEL_22;
  }
  v46 = 0;
  for ( i = (CDplAccount *)*((_QWORD *)this + 13); i != (CDplAccount *)((char *)this + 104); i = *(CDplAccount **)i )
  {
    fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 135);
    v21 = -1;
    v22 = v46 + 1 < v46;
    if ( v46 + 1 >= v46 )
      v21 = v46 + 1;
    v46 = v21;
    v10 = v22 ? 0x80070216 : 0;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                36,
                135) < 0 )
      goto LABEL_129;
  }
  v23 = RegSetKeyValueW(a2, 0, L"KeySetCount", 4u, &v46, 4u);
  v10 = v23;
  if ( v23 )
  {
    if ( v23 > 0 )
      v10 = (unsigned __int16)v23 | 0x80070000;
    lpData = -109;
    goto LABEL_22;
  }
  if ( *((_DWORD *)this + 34) )
  {
    v25 = RegSetKeyValueW(a2, 0, L"DplEnabled", 4u, (char *)this + 136, 4u);
    v10 = v25;
    if ( v25 )
    {
      if ( v25 > 0 )
        v10 = (unsigned __int16)v25 | 0x80070000;
      lpData = -91;
      goto LABEL_22;
    }
  }
  else if ( a3 )
  {
    v26 = RegDeleteValueW(a2, L"DplEnabled");
    v10 = v26;
    if ( (v26 & 0xFFFFFFFD) != 0 )
    {
      if ( v26 > 0 )
        v10 = (unsigned __int16)v26 | 0x80070000;
      lpData = -82;
      goto LABEL_22;
    }
  }
  if ( *((_DWORD *)this + 36) )
  {
    v27 = RegSetKeyValueW(a2, 0, L"Revoked", 4u, (char *)this + 144, 4u);
    v10 = v27;
    if ( v27 )
    {
      if ( v27 > 0 )
        v10 = (unsigned __int16)v27 | 0x80070000;
      lpData = -63;
      goto LABEL_22;
    }
    if ( *((_DWORD *)this + 37) )
    {
      v28 = RegSetKeyValueW(a2, 0, L"RevokeReason", 4u, (char *)this + 148, 4u);
      v10 = v28;
      if ( v28 )
      {
        if ( v28 > 0 )
          v10 = (unsigned __int16)v28 | 0x80070000;
        lpData = -49;
        goto LABEL_22;
      }
    }
  }
  else if ( a3 )
  {
    v29 = RegDeleteValueW(a2, L"Revoked");
    v10 = v29;
    if ( (v29 & 0xFFFFFFFD) != 0 )
    {
      if ( v29 > 0 )
        v10 = (unsigned __int16)v29 | 0x80070000;
      lpData = -39;
      goto LABEL_22;
    }
  }
  if ( *((_QWORD *)this + 2) )
  {
    fnEfsLogTrace1Strings(v24, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 232);
    v10 = CDplService::UtcTimestampToLocalTimeString(*((_QWORD *)this + 2), v45);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                36,
                232) < 0 )
    {
LABEL_128:
      v7 = v45[0];
      goto LABEL_129;
    }
    fnEfsLogTrace1Strings(v30, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 237);
    v7 = v45[0];
    v10 = CDplService::RegSetStringValue(a2, v31, L"RevokeTime", v45[0]);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                36,
                237) < 0 )
      goto LABEL_129;
    if ( v7 )
      DplibMemFree(v7);
    v45[0] = 0;
  }
  else if ( a3 )
  {
    v35 = RegDeleteValueW(a2, L"RevokeTime");
    v10 = v35;
    if ( (v35 & 0xFFFFFFFD) != 0 )
    {
      if ( v35 > 0 )
        v10 = (unsigned __int16)v35 | 0x80070000;
      lpData = -9;
      goto LABEL_22;
    }
  }
  fnEfsLogTrace1Strings(v24, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 251);
  v10 = CDplService::UtcTimestampToLocalTimeString(*((_QWORD *)this + 1), v45);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v10,
              36,
              251) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v32, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 36, 0);
  v7 = v45[0];
  v10 = CDplService::RegSetStringValue(a2, v33, L"CreateTime", v45[0]);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v10,
              36,
              0) < 0 )
    goto LABEL_129;
  if ( v7 )
    DplibMemFree(v7);
  v7 = 0;
  if ( *((_DWORD *)this + 48) == -1 )
  {
    if ( a3 )
    {
      v36 = RegDeleteValueW(a2, L"RecoveryAccountVersion");
      if ( (v36 & 0xFFFFFFFD) != 0 )
      {
        if ( v36 > 0 )
          v10 = (unsigned __int16)v36 | 0x80070000;
        else
          v10 = v36;
        lpData = 24;
        goto LABEL_22;
      }
    }
  }
  else
  {
    v34 = RegSetKeyValueW(a2, 0, L"RecoveryAccountVersion", 4u, (char *)this + 192, 4u);
    if ( v34 )
    {
      if ( v34 > 0 )
        v10 = (unsigned __int16)v34 | 0x80070000;
      else
        v10 = v34;
      lpData = 15;
LABEL_22:
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v10, 36, lpData);
      goto LABEL_129;
    }
  }
  if ( *((_DWORD *)this + 50) )
  {
    v37 = RegSetKeyValueW(a2, 0, L"RetrievedFromCloud", 4u, (char *)this + 200, 4u);
    if ( v37 )
    {
      if ( v37 > 0 )
        v10 = (unsigned __int16)v37 | 0x80070000;
      else
        v10 = v37;
      lpData = 45;
      goto LABEL_22;
    }
  }
  if ( *((_DWORD *)this + 51) )
  {
    v38 = RegSetKeyValueW(a2, 0, L"ConsumerCredential", 4u, (char *)this + 204, 4u);
    if ( v38 )
    {
      if ( v38 > 0 )
        v10 = (unsigned __int16)v38 | 0x80070000;
      else
        v10 = v38;
      lpData = 65;
      goto LABEL_22;
    }
  }
  if ( (*((_DWORD *)this + 51) != 0) != (*((_DWORD *)this + 52) != -1) )
  {
    v10 = -2147418113;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 36, 69);
    goto LABEL_129;
  }
  if ( *((_DWORD *)this + 52) != -1 )
  {
    v39 = RegSetKeyValueW(a2, 0, L"ConsumerCredentialLevel", 4u, (char *)this + 208, 4u);
    if ( v39 )
    {
      if ( v39 > 0 )
        v10 = (unsigned __int16)v39 | 0x80070000;
      else
        v10 = v39;
      lpData = 87;
      goto LABEL_22;
    }
  }
  v40 = (_DWORD *)((char *)this + 140);
  if ( *v40 )
  {
    v41 = RegSetKeyValueW(a2, 0, L"CDplEnforced", 4u, v40, 4u);
    if ( !v41 )
      goto LABEL_129;
    if ( v41 > 0 )
      v10 = (unsigned __int16)v41 | 0x80070000;
    else
      v10 = v41;
    lpData = 106;
    goto LABEL_22;
  }
  if ( a3 )
  {
    v42 = RegDeleteValueW(a2, L"CDplEnforced");
    if ( (v42 & 0xFFFFFFFD) != 0 )
    {
      if ( v42 > 0 )
        v10 = (unsigned __int16)v42 | 0x80070000;
      else
        v10 = v42;
      lpData = 115;
      goto LABEL_22;
    }
  }
LABEL_129:
  if ( v7 )
    DplibMemFree(v7);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v10,
    36,
    123);
  return v10;
}

```

## disassembly

```asm
0x1800a7244  mov     [rsp-38h+arg_8], rbx
0x1800a7249  mov     [rsp-38h+Data], r9
0x1800a724e  push    rbp
0x1800a724f  push    rsi
0x1800a7250  push    rdi
0x1800a7251  push    r12
0x1800a7253  push    r13
0x1800a7255  push    r14
0x1800a7257  push    r15
0x1800a7259  mov     rbp, rsp
0x1800a725c  sub     rsp, 50h
0x1800a7260  xor     r13d, r13d
0x1800a7263  mov     r15d, r8d
0x1800a7266  cmp     cs:?g_DplDbgBreakEnabled@@3IA, r13d; uint g_DplDbgBreakEnabled
0x1800a726d  mov     rsi, rdx
0x1800a7270  mov     rdi, rcx
0x1800a7273  mov     [rbp+arg_0], r13d
0x1800a7277  mov     r14d, r13d
0x1800a727a  mov     [rbp+var_10], r13
0x1800a727e  jz      short loc_1800A7282
0x1800a7280  int     2Ch; Windows NT - assertion failure
0x1800a7282  mov     r9d, 24h ; '$'
0x1800a7288  mov     dword ptr [rsp+50h+lpData], 216h
0x1800a7290  lea     r8, sourceString
0x1800a7297  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800a729e  call    fnEfsLogTrace1Strings
0x1800a72a3  cmp     [rdi+40h], r13
0x1800a72a7  jz      short loc_1800A731C
0x1800a72a9  mov     r12d, 221h
0x1800a72af  lea     r8, sourceString
0x1800a72b6  mov     r9d, 24h ; '$'
0x1800a72bc  mov     dword ptr [rsp+50h+lpData], r12d
0x1800a72c1  lea     rdx, EFS_TRACE_START_EVENT
0x1800a72c8  call    fnEfsLogTrace1Strings
0x1800a72cd  mov     r9, [rdi+40h]; unsigned __int16 *
0x1800a72d1  lea     r8, aPrimaryidentit; "PrimaryIdentity"
0x1800a72d8  mov     rcx, rsi; hKey
0x1800a72db  call    ?RegSetStringValue@CDplService@@SAJPEAUHKEY__@@PEBG11@Z; CDplService::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800a72e0  mov     rcx, cs:g_hPublisher
0x1800a72e7  lea     r9, sourceString
0x1800a72ee  mov     [rsp+50h+var_20], r12d
0x1800a72f3  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a72fa  mov     [rsp+50h+cbData], 24h ; '$'
0x1800a7302  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a7309  mov     dword ptr [rsp+50h+lpData], eax
0x1800a730d  mov     ebx, eax
0x1800a730f  call    fnEfsLogTrace1String1Dword
0x1800a7314  test    eax, eax
0x1800a7316  js      loc_1800A7CD8
0x1800a731c  cmp     [rdi+50h], r13
0x1800a7320  jz      loc_1800A7560
0x1800a7326  mov     r12d, 22Dh
0x1800a732c  lea     r8, sourceString
0x1800a7333  mov     r9d, 24h ; '$'
0x1800a7339  mov     dword ptr [rsp+50h+lpData], r12d
0x1800a733e  lea     rdx, EFS_TRACE_START_EVENT
0x1800a7345  call    fnEfsLogTrace1Strings
0x1800a734a  mov     r9, [rdi+50h]; unsigned __int16 *
0x1800a734e  lea     r8, aAppid; "AppId"
0x1800a7355  mov     rcx, rsi; hKey
0x1800a7358  call    ?RegSetStringValue@CDplService@@SAJPEAUHKEY__@@PEBG11@Z; CDplService::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800a735d  mov     rcx, cs:g_hPublisher
0x1800a7364  lea     r9, sourceString
0x1800a736b  mov     [rsp+50h+var_20], r12d
0x1800a7370  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a7377  mov     [rsp+50h+cbData], 24h ; '$'
0x1800a737f  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a7386  mov     dword ptr [rsp+50h+lpData], eax
0x1800a738a  mov     ebx, eax
0x1800a738c  call    fnEfsLogTrace1String1Dword
0x1800a7391  test    eax, eax
0x1800a7393  js      loc_1800A7CD8
0x1800a7399  cmp     [rdi+48h], r13
0x1800a739d  jz      short loc_1800A7412
0x1800a739f  mov     r12d, 242h
0x1800a73a5  lea     r8, sourceString
0x1800a73ac  mov     r9d, 24h ; '$'
0x1800a73b2  mov     dword ptr [rsp+50h+lpData], r12d
0x1800a73b7  lea     rdx, EFS_TRACE_START_EVENT
0x1800a73be  call    fnEfsLogTrace1Strings
0x1800a73c3  mov     r9, [rdi+48h]; unsigned __int16 *
0x1800a73c7  lea     r8, aSecondaryident; "SecondaryIdentities"
0x1800a73ce  mov     rcx, rsi; hKey
0x1800a73d1  call    ?RegSetStringValue@CDplService@@SAJPEAUHKEY__@@PEBG11@Z; CDplService::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800a73d6  mov     rcx, cs:g_hPublisher
0x1800a73dd  lea     r9, sourceString
0x1800a73e4  mov     [rsp+50h+var_20], r12d
0x1800a73e9  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a73f0  mov     [rsp+50h+cbData], 24h ; '$'
0x1800a73f8  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a73ff  mov     dword ptr [rsp+50h+lpData], eax
0x1800a7403  mov     ebx, eax
0x1800a7405  call    fnEfsLogTrace1String1Dword
0x1800a740a  test    eax, eax
0x1800a740c  js      loc_1800A7CD8
0x1800a7412  cmp     [rdi+0B0h], r13
0x1800a7419  jz      loc_1800A75BC
0x1800a741f  mov     r12d, 24Eh
0x1800a7425  lea     r8, sourceString
0x1800a742c  mov     r9d, 24h ; '$'
0x1800a7432  mov     dword ptr [rsp+50h+lpData], r12d
0x1800a7437  lea     rdx, EFS_TRACE_START_EVENT
0x1800a743e  call    fnEfsLogTrace1Strings
0x1800a7443  mov     r9, [rdi+0B0h]; unsigned __int16 *
0x1800a744a  lea     r8, aRecoveryaccoun; "RecoveryAccountHash"
0x1800a7451  mov     rcx, rsi; hKey
0x1800a7454  call    ?RegSetStringValue@CDplService@@SAJPEAUHKEY__@@PEBG11@Z; CDplService::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800a7459  mov     rcx, cs:g_hPublisher
0x1800a7460  lea     r9, sourceString
0x1800a7467  mov     [rsp+50h+var_20], r12d
0x1800a746c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a7473  mov     [rsp+50h+cbData], 24h ; '$'
0x1800a747b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a7482  mov     dword ptr [rsp+50h+lpData], eax
0x1800a7486  mov     ebx, eax
0x1800a7488  call    fnEfsLogTrace1String1Dword
0x1800a748d  test    eax, eax
0x1800a748f  js      loc_1800A7CD8
0x1800a7495  cmp     [rdi+0B8h], r13
0x1800a749c  jz      loc_1800A75F9
0x1800a74a2  mov     r12d, 263h
0x1800a74a8  lea     r8, sourceString
0x1800a74af  mov     r9d, 24h ; '$'
0x1800a74b5  mov     dword ptr [rsp+50h+lpData], r12d
0x1800a74ba  lea     rdx, EFS_TRACE_START_EVENT
0x1800a74c1  call    fnEfsLogTrace1Strings
0x1800a74c6  mov     r9, [rdi+0B8h]; unsigned __int16 *
0x1800a74cd  lea     r8, aRecoverypolicy; "RecoveryPolicyHash"
0x1800a74d4  mov     rcx, rsi; hKey
0x1800a74d7  call    ?RegSetStringValue@CDplService@@SAJPEAUHKEY__@@PEBG11@Z; CDplService::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800a74dc  mov     rcx, cs:g_hPublisher
0x1800a74e3  lea     r9, sourceString
0x1800a74ea  mov     [rsp+50h+var_20], r12d
0x1800a74ef  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a74f6  mov     [rsp+50h+cbData], 24h ; '$'
0x1800a74fe  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a7505  mov     dword ptr [rsp+50h+lpData], eax
0x1800a7509  mov     ebx, eax
0x1800a750b  call    fnEfsLogTrace1String1Dword
0x1800a7510  test    eax, eax
0x1800a7512  js      loc_1800A7CD8
0x1800a7518  lea     rax, [rbp+Data]
0x1800a751c  mov     [rsp+50h+cbData], 8; cbData
0x1800a7524  mov     r9d, 0Bh; dwType
0x1800a752a  mov     [rsp+50h+lpData], rax; lpData
0x1800a752f  lea     r8, aLsn; "Lsn"
0x1800a7536  xor     edx, edx; lpSubKey
0x1800a7538  mov     rcx, rsi; hKey
0x1800a753b  call    cs:__imp_RegSetKeyValueW
0x1800a7541  mov     ebx, eax
0x1800a7543  test    eax, eax
0x1800a7545  jz      loc_1800A7639
0x1800a754b  jle     short loc_1800A7556
0x1800a754d  movzx   ebx, ax
0x1800a7550  or      ebx, 80070000h
0x1800a7556  mov     dword ptr [rsp+50h+lpData], 27Ch
0x1800a755e  jmp     short loc_1800A759B
0x1800a7560  test    r15d, r15d
0x1800a7563  jz      loc_1800A7399
0x1800a7569  lea     rdx, aAppid; "AppId"
0x1800a7570  mov     rcx, rsi; hKey
0x1800a7573  call    cs:__imp_RegDeleteValueW
0x1800a7579  mov     ebx, eax
0x1800a757b  test    eax, 0FFFFFFFDh
0x1800a7580  jz      loc_1800A7399
0x1800a7586  test    eax, eax
0x1800a7588  jle     short loc_1800A7593
0x1800a758a  movzx   ebx, ax
0x1800a758d  or      ebx, 80070000h
0x1800a7593  mov     dword ptr [rsp+50h+lpData], 235h
0x1800a759b  mov     r8d, ebx
0x1800a759e  mov     rcx, cs:g_hPublisher
0x1800a75a5  lea     rdx, EFS_TRACE_ERROR
0x1800a75ac  mov     r9d, 24h ; '$'
0x1800a75b2  call    fnEfsLogTrace1
0x1800a75b7  jmp     loc_1800A7CD8
0x1800a75bc  test    r15d, r15d
0x1800a75bf  jz      loc_1800A7495
0x1800a75c5  lea     rdx, aRecoveryaccoun; "RecoveryAccountHash"
0x1800a75cc  mov     rcx, rsi; hKey
0x1800a75cf  call    cs:__imp_RegDeleteValueW
0x1800a75d5  mov     ebx, eax
0x1800a75d7  test    eax, 0FFFFFFFDh
0x1800a75dc  jz      loc_1800A7495
0x1800a75e2  test    eax, eax
0x1800a75e4  jle     short loc_1800A75EF
0x1800a75e6  movzx   ebx, ax
0x1800a75e9  or      ebx, 80070000h
0x1800a75ef  mov     dword ptr [rsp+50h+lpData], 256h
0x1800a75f7  jmp     short loc_1800A759B
0x1800a75f9  test    r15d, r15d
0x1800a75fc  jz      loc_1800A7518
0x1800a7602  lea     rdx, aRecoverypolicy; "RecoveryPolicyHash"
0x1800a7609  mov     rcx, rsi; hKey
0x1800a760c  call    cs:__imp_RegDeleteValueW
0x1800a7612  mov     ebx, eax
0x1800a7614  test    eax, 0FFFFFFFDh
0x1800a7619  jz      loc_1800A7518
0x1800a761f  test    eax, eax
0x1800a7621  jle     short loc_1800A762C
0x1800a7623  movzx   ebx, ax
0x1800a7626  or      ebx, 80070000h
0x1800a762c  mov     dword ptr [rsp+50h+lpData], 26Bh
0x1800a7634  jmp     loc_1800A759B
0x1800a7639  mov     [rbp+arg_0], r13d
0x1800a763d  lea     r13, [rdi+68h]
0x1800a7641  mov     r12, [r13+0]
0x1800a7645  cmp     r12, r13
0x1800a7648  jz      loc_1800A76CE
0x1800a764e  mov     r9d, 24h ; '$'
0x1800a7654  mov     dword ptr [rsp+50h+lpData], 287h
0x1800a765c  lea     r8, sourceString
0x1800a7663  lea     rdx, EFS_TRACE_START_EVENT
0x1800a766a  call    fnEfsLogTrace1Strings
0x1800a766f  mov     ecx, [rbp+arg_0]
0x1800a7672  lea     r9, sourceString
0x1800a7679  or      edx, 0FFFFFFFFh
0x1800a767c  mov     [rsp+50h+var_20], 287h
0x1800a7684  mov     [rsp+50h+cbData], 24h ; '$'
0x1800a768c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a7693  lea     eax, [rcx+1]
0x1800a7696  cmp     eax, ecx
0x1800a7698  mov     rcx, cs:g_hPublisher
0x1800a769f  cmovnb  edx, eax
0x1800a76a2  sbb     ebx, ebx
0x1800a76a4  mov     [rbp+arg_0], edx
0x1800a76a7  and     ebx, 80070216h
0x1800a76ad  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800a76b4  mov     dword ptr [rsp+50h+lpData], ebx
0x1800a76b8  call    fnEfsLogTrace1String1Dword
0x1800a76bd  test    eax, eax
0x1800a76bf  js      loc_1800A7CD8
0x1800a76c5  mov     r12, [r12]
0x1800a76c9  jmp     loc_1800A7645
0x1800a76ce  mov     r12d, 4
0x1800a76d4  lea     rax, [rbp+arg_0]
0x1800a76d8  mov     [rsp+50h+cbData], r12d; cbData
0x1800a76dd  lea     r8, aKeysetcount; "KeySetCount"
0x1800a76e4  mov     r9d, r12d; dwType
0x1800a76e7  mov     [rsp+50h+lpData], rax; lpData
0x1800a76ec  xor     edx, edx; lpSubKey
0x1800a76ee  mov     rcx, rsi; hKey
0x1800a76f1  call    cs:__imp_RegSetKeyValueW
0x1800a76f7  xor     r13d, r13d
0x1800a76fa  mov     ebx, eax
0x1800a76fc  test    eax, eax
0x1800a76fe  jz      short loc_1800A7718
0x1800a7700  jle     short loc_1800A770B
0x1800a7702  movzx   ebx, ax
0x1800a7705  or      ebx, 80070000h
0x1800a770b  mov     dword ptr [rsp+50h+lpData], 293h
0x1800a7713  jmp     loc_1800A759B
0x1800a7718  lea     rax, [rdi+88h]
0x1800a771f  cmp     [rax], r13d
0x1800a7722  jz      short loc_1800A7761
0x1800a7724  mov     [rsp+50h+cbData], r12d; cbData
0x1800a7729  lea     r8, aDplenabled; "DplEnabled"
0x1800a7730  mov     r9d, r12d; dwType
0x1800a7733  mov     [rsp+50h+lpData], rax; lpData
0x1800a7738  xor     edx, edx; lpSubKey
0x1800a773a  mov     rcx, rsi; hKey
0x1800a773d  call    cs:__imp_RegSetKeyValueW
0x1800a7743  mov     ebx, eax
0x1800a7745  test    eax, eax
0x1800a7747  jz      short loc_1800A7799
0x1800a7749  jle     short loc_1800A7754
0x1800a774b  movzx   ebx, ax
0x1800a774e  or      ebx, 80070000h
0x1800a7754  mov     dword ptr [rsp+50h+lpData], 2A5h
0x1800a775c  jmp     loc_1800A759B
0x1800a7761  test    r15d, r15d
0x1800a7764  jz      short loc_1800A7799
0x1800a7766  lea     rdx, aDplenabled; "DplEnabled"
0x1800a776d  mov     rcx, rsi; hKey
0x1800a7770  call    cs:__imp_RegDeleteValueW
0x1800a7776  mov     ebx, eax
0x1800a7778  test    eax, 0FFFFFFFDh
0x1800a777d  jz      short loc_1800A7799
0x1800a777f  test    eax, eax
0x1800a7781  jle     short loc_1800A778C
0x1800a7783  movzx   ebx, ax
0x1800a7786  or      ebx, 80070000h
0x1800a778c  mov     dword ptr [rsp+50h+lpData], 2AEh
0x1800a7794  jmp     loc_1800A759B
0x1800a7799  lea     rax, [rdi+90h]
0x1800a77a0  cmp     [rax], r13d
0x1800a77a3  jz      loc_1800A782F
0x1800a77a9  mov     [rsp+50h+cbData], r12d; cbData
0x1800a77ae  lea     r8, aRevoked; "Revoked"
0x1800a77b5  mov     r9d, r12d; dwType
0x1800a77b8  mov     [rsp+50h+lpData], rax; lpData
0x1800a77bd  xor     edx, edx; lpSubKey
0x1800a77bf  mov     rcx, rsi; hKey
0x1800a77c2  call    cs:__imp_RegSetKeyValueW
0x1800a77c8  mov     ebx, eax
0x1800a77ca  test    eax, eax
0x1800a77cc  jz      short loc_1800A77E6
0x1800a77ce  jle     short loc_1800A77D9
0x1800a77d0  movzx   ebx, ax
0x1800a77d3  or      ebx, 80070000h
  ... truncated ...
```
