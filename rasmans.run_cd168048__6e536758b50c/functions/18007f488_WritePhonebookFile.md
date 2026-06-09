# WritePhonebookFile

- ea: `0x18007f488`
- end: `0x18007fb6c`
- name: `WritePhonebookFile`
- size: `1764`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800615c0`
- `0x180068800`
- `0x18006b0b4`
- `0x18006b964`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000ebe8`
- `0x18005ef68`
- `0x1800693d8`
- `0x18006b0b4`
- `0x1800714c0`
- `0x18007dc10`
- `0x18007f488`
- `0x180083300`
- `0x180085b1c`
- `0x18008e3fc`
- `0x180095000`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f858`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007f91f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007f91f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007f843`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007f843`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007f6e3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007f6e3`

## string_xrefs

- `0x18007fa7f`: `ProfileDelete`
- `0x18007fa8d`: `ProfileCreate`

## pseudocode

```c
__int64 __fastcall WritePhonebookFile(_QWORD *a1, _WORD *a2)
{
  struct _LIST_ENTRY *v4; // rcx
  __int64 v5; // rdx
  __int64 *v6; // rax
  struct _LIST_ENTRY *v7; // rcx
  DWORD v8; // edi
  __int64 v9; // rdx
  __int64 i; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // r14d
  DWORD v16; // eax
  __int64 *v17; // rax
  __int64 v18; // r13
  unsigned int *v19; // r14
  DWORD LastError; // eax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 *v23; // rsi
  __int64 v24; // rsi
  _DWORD *v25; // rcx
  const wchar_t *v26; // r8
  struct _LIST_ENTRY *v27; // rcx
  unsigned int v28; // [rsp+20h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+24h] [rbp-1Ch] BYREF
  _DWORD SidToCheck[4]; // [rsp+28h] [rbp-18h] BYREF

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 788, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
         && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
         && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 789, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  }
  v28 = 0;
  if ( (unsigned int)LockDownPolicyExists() )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return 5;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 790, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 5);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v4[1].Blink) >= 0 || BYTE1(v4[1].Blink) < 6u )
      return 5;
    v5 = 791;
LABEL_57:
    WPP_SF_d(v4[1].Flink, v5, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 5);
    return 5;
  }
  if ( !a1 || (v6 = (__int64 *)a1[2]) == 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 792, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
        v27 = WPP_GLOBAL_Control;
      }
      if ( v27 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v27[1].Blink) < 0 && BYTE1(v27[1].Blink) >= 6u )
        WPP_SF_d(v27[1].Flink, 793, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
    }
    return 0;
  }
  if ( a2 && !*a2 )
  {
    v7 = WPP_GLOBAL_Control;
    v8 = 87;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 794, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 87);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v7[1].Blink) < 0 && BYTE1(v7[1].Blink) >= 6u )
      {
        v9 = 795;
        goto LABEL_31;
      }
    }
    return v8;
  }
  if ( (a1[4] & 0x900) == 0 )
  {
    for ( i = *v6; ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
        goto LABEL_40;
      v12 = *(_QWORD *)(i + 16);
      if ( !v12 )
        goto LABEL_49;
      if ( *(_DWORD *)(v12 + 532) && *(_DWORD *)(v12 + 548) )
        break;
    }
    IsMember = 0;
    SidToCheck[0] = 257;
    SidToCheck[1] = 83886080;
    SidToCheck[2] = 18;
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) || !IsMember )
    {
LABEL_49:
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return 5;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 796, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 5);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v4[1].Blink) >= 0 || BYTE1(v4[1].Blink) < 6u )
        return 5;
      v5 = 797;
      goto LABEL_57;
    }
  }
LABEL_40:
  if ( a2 )
  {
    v13 = EntryNodeFromName(a1[2], a2);
    if ( !v13 )
    {
      v8 = 623;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_127;
      }
      v14 = 798;
LABEL_46:
      WPP_SF_d(v7[1].Flink, v14, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v8);
LABEL_126:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_127;
    }
    *(_DWORD *)(*(_QWORD *)(v13 + 16) + 540LL) = 1;
  }
  v15 = IsRegistryWrite();
  if ( v15 )
    v16 = ModifyEntryListInRegistry((__int64)a1, &v28);
  else
    v16 = ModifyEntryList((__int64)a1, &v28);
  v8 = v16;
  if ( v16 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_127;
    }
    v14 = 799;
    goto LABEL_46;
  }
  if ( v15 || (v17 = (__int64 *)a1[6]) == 0 || (v18 = *v17) == 0 )
  {
    v7 = WPP_GLOBAL_Control;
LABEL_107:
    if ( *((_DWORD *)a1 + 2) )
      goto LABEL_120;
    if ( a2 )
    {
      if ( !(unsigned int)FIsUserAdminOrNCO() )
      {
LABEL_114:
        v7 = WPP_GLOBAL_Control;
        goto LABEL_115;
      }
      DeleteAllHiddenProfile((wchar_t *)*a1);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 805, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
        goto LABEL_114;
      }
    }
LABEL_115:
    if ( !*((_DWORD *)a1 + 2) )
    {
      if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v7[1].Blink) >= 0 || BYTE1(v7[1].Blink) < 5u )
        goto LABEL_127;
      v22 = 806;
LABEL_125:
      WPP_SF_d(v7[1].Flink, v22, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v28);
      goto LABEL_126;
    }
LABEL_120:
    if ( *((_DWORD *)a1 + 2) != 1
      || v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(v7[1].Blink) >= 0
      || BYTE1(v7[1].Blink) < 5u )
    {
      goto LABEL_127;
    }
    v22 = 807;
    goto LABEL_125;
  }
  v7 = WPP_GLOBAL_Control;
  while ( 1 )
  {
    v19 = *(unsigned int **)(v18 + 16);
    if ( v19 )
      break;
    if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v7[1].Blink) >= 0 || BYTE1(v7[1].Blink) < 2u )
      goto LABEL_95;
    WPP_SF_(v7[1].Flink, 800, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
LABEL_94:
    v7 = WPP_GLOBAL_Control;
LABEL_95:
    v18 = *(_QWORD *)(v18 + 8);
    if ( !v18 )
    {
      if ( v8 )
        goto LABEL_127;
      goto LABEL_107;
    }
  }
  if ( g_hmutexPb )
  {
    v8 = WaitForSingleObject(g_hmutexPb, 0xFFFFFFFF);
    if ( (v8 & 0xFFFFFF7F) != 0 )
    {
      LastError = GetLastError();
      v8 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_95;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 804, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
    }
    else
    {
      if ( *v19 > 0x1F3
        || (v21 = gpRasfiles[*v19]) == 0
        || (*(_BYTE *)(v21 + 32) & 4) != 0
        || *(_BYTE *)(v21 + 572)
        || *(_DWORD *)(v21 + 36) && !(unsigned int)rasWriteFile() )
      {
        v8 = 624;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 803, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 624);
        }
      }
      ReleaseMutex(g_hmutexPb);
    }
    goto LABEL_94;
  }
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v7[1].Blink) < 0 && BYTE1(v7[1].Blink) >= 2u )
  {
    WPP_SF_d(v7[1].Flink, 801, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v8);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = 624;
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v7[1].Blink) < 0 && BYTE1(v7[1].Blink) >= 2u )
  {
    v14 = 802;
    goto LABEL_46;
  }
LABEL_127:
  v23 = (__int64 *)a1[2];
  if ( v23 )
  {
    v24 = *v23;
    if ( v24 )
    {
      while ( 2 )
      {
        v25 = *(_DWORD **)(v24 + 16);
        if ( v25 )
        {
          if ( v25[135] )
          {
            v26 = L"ProfileDelete";
            goto LABEL_136;
          }
          if ( *v25 == -1 )
          {
            v26 = L"ProfileCreate";
            goto LABEL_136;
          }
          if ( v25[133] )
          {
            v26 = L"ProfileModify";
LABEL_136:
            TelemetryEventWritePhonebookEntry(v25, *a1, v26, v8);
          }
        }
        v24 = *(_QWORD *)(v24 + 8);
        if ( !v24 )
        {
          v7 = WPP_GLOBAL_Control;
          break;
        }
        continue;
      }
    }
  }
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v7[1].Blink) < 0 && BYTE1(v7[1].Blink) >= 6u )
  {
    v9 = 808;
LABEL_31:
    WPP_SF_d(v7[1].Flink, v9, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x18007f488  mov     [rsp-38h+arg_10], rbx
0x18007f48d  push    rbp
0x18007f48e  push    rsi
0x18007f48f  push    rdi
0x18007f490  push    r12
0x18007f492  push    r13
0x18007f494  push    r14
0x18007f496  push    r15
0x18007f498  mov     rbp, rsp
0x18007f49b  sub     rsp, 40h
0x18007f49f  mov     rax, cs:__security_cookie
0x18007f4a6  xor     rax, rsp
0x18007f4a9  mov     [rbp+var_8], rax
0x18007f4ad  xor     edi, edi
0x18007f4af  mov     r12, rdx
0x18007f4b2  mov     r15, rcx
0x18007f4b5  test    rdx, rdx
0x18007f4b8  jz      short loc_18007F4F3
0x18007f4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f4c1  lea     rbx, WPP_GLOBAL_Control
0x18007f4c8  cmp     rcx, rbx
0x18007f4cb  jz      short loc_18007F527
0x18007f4cd  test    byte ptr [rcx+1Ch], 80h
0x18007f4d1  jz      short loc_18007F527
0x18007f4d3  cmp     byte ptr [rcx+19h], 6
0x18007f4d7  jb      short loc_18007F527
0x18007f4d9  mov     rcx, [rcx+10h]
0x18007f4dd  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f4e4  mov     edx, 314h
0x18007f4e9  mov     r9, r12
0x18007f4ec  call    WPP_SF_S
0x18007f4f1  jmp     short loc_18007F527
0x18007f4f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f4fa  lea     rbx, WPP_GLOBAL_Control
0x18007f501  cmp     rcx, rbx
0x18007f504  jz      short loc_18007F527
0x18007f506  test    byte ptr [rcx+1Ch], 80h
0x18007f50a  jz      short loc_18007F527
0x18007f50c  cmp     byte ptr [rcx+19h], 6
0x18007f510  jb      short loc_18007F527
0x18007f512  mov     rcx, [rcx+10h]
0x18007f516  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f51d  mov     edx, 315h
0x18007f522  call    WPP_SF_
0x18007f527  mov     [rbp+var_20], edi
0x18007f52a  call    LockDownPolicyExists
0x18007f52f  mov     esi, 5
0x18007f534  test    eax, eax
0x18007f536  jz      short loc_18007F59A
0x18007f538  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f53f  cmp     rcx, rbx
0x18007f542  jz      loc_18007F75C
0x18007f548  test    byte ptr [rcx+1Ch], 80h
0x18007f54c  jz      short loc_18007F573
0x18007f54e  cmp     byte ptr [rcx+19h], 2
0x18007f552  jb      short loc_18007F573
0x18007f554  mov     rcx, [rcx+10h]
0x18007f558  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f55f  mov     edx, 316h
0x18007f564  mov     r9d, esi
0x18007f567  call    WPP_SF_d
0x18007f56c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f573  cmp     rcx, rbx
0x18007f576  jz      loc_18007F75C
0x18007f57c  test    byte ptr [rcx+1Ch], 80h
0x18007f580  jz      loc_18007F75C
0x18007f586  cmp     byte ptr [rcx+19h], 6
0x18007f58a  jb      loc_18007F75C
0x18007f590  mov     edx, 317h
0x18007f595  jmp     loc_18007F749
0x18007f59a  test    r15, r15
0x18007f59d  jz      loc_18007FAE8
0x18007f5a3  mov     rax, [r15+10h]
0x18007f5a7  test    rax, rax
0x18007f5aa  jz      loc_18007FAE8
0x18007f5b0  test    r12, r12
0x18007f5b3  jz      short loc_18007F628
0x18007f5b5  cmp     [r12], di
0x18007f5ba  jnz     short loc_18007F628
0x18007f5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f5c3  mov     edi, 57h ; 'W'
0x18007f5c8  cmp     rcx, rbx
0x18007f5cb  jz      short loc_18007F621
0x18007f5cd  test    byte ptr [rcx+1Ch], 80h
0x18007f5d1  jz      short loc_18007F5F8
0x18007f5d3  cmp     byte ptr [rcx+19h], 2
0x18007f5d7  jb      short loc_18007F5F8
0x18007f5d9  mov     rcx, [rcx+10h]
0x18007f5dd  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f5e4  mov     edx, 31Ah
0x18007f5e9  mov     r9d, edi
0x18007f5ec  call    WPP_SF_d
0x18007f5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f5f8  cmp     rcx, rbx
0x18007f5fb  jz      short loc_18007F621
0x18007f5fd  test    byte ptr [rcx+1Ch], 80h
0x18007f601  jz      short loc_18007F621
0x18007f603  cmp     byte ptr [rcx+19h], 6
0x18007f607  jb      short loc_18007F621
0x18007f609  mov     edx, 31Bh
0x18007f60e  mov     rcx, [rcx+10h]
0x18007f612  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f619  mov     r9d, edi
0x18007f61c  call    WPP_SF_d
0x18007f621  mov     eax, edi
0x18007f623  jmp     loc_18007FB47
0x18007f628  test    dword ptr [r15+20h], 900h
0x18007f630  jnz     short loc_18007F65D
0x18007f632  mov     rax, [rax]
0x18007f635  jmp     short loc_18007F658
0x18007f637  mov     rcx, [rax+10h]
0x18007f63b  test    rcx, rcx
0x18007f63e  jz      loc_18007F6FC
0x18007f644  cmp     [rcx+214h], edi
0x18007f64a  jz      short loc_18007F654
0x18007f64c  cmp     [rcx+224h], edi
0x18007f652  jnz     short loc_18007F6C1
0x18007f654  mov     rax, [rax+8]
0x18007f658  test    rax, rax
0x18007f65b  jnz     short loc_18007F637
0x18007f65d  test    r12, r12
0x18007f660  jz      loc_18007F771
0x18007f666  mov     rcx, [r15+10h]
0x18007f66a  mov     rdx, r12
0x18007f66d  call    EntryNodeFromName
0x18007f672  test    rax, rax
0x18007f675  jnz     loc_18007F763
0x18007f67b  mov     edi, 26Fh
0x18007f680  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f687  cmp     rcx, rbx
0x18007f68a  jz      loc_18007FA5C
0x18007f690  test    byte ptr [rcx+1Ch], 80h
0x18007f694  jz      loc_18007FA5C
0x18007f69a  cmp     byte ptr [rcx+19h], 2
0x18007f69e  jb      loc_18007FA5C
0x18007f6a4  mov     edx, 31Eh
0x18007f6a9  mov     rcx, [rcx+10h]
0x18007f6ad  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f6b4  mov     r9d, edi
0x18007f6b7  call    WPP_SF_d
0x18007f6bc  jmp     loc_18007FA55
0x18007f6c1  lea     r8, [rbp+IsMember]; IsMember
0x18007f6c5  mov     [rbp+IsMember], edi
0x18007f6c8  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18007f6cc  mov     [rbp+SidToCheck], 101h
0x18007f6d3  xor     ecx, ecx; TokenHandle
0x18007f6d5  mov     [rbp+var_14], 5000000h
0x18007f6dc  mov     [rbp+var_10], 12h
0x18007f6e3  call    cs:__imp_CheckTokenMembership
0x18007f6ea  nop     dword ptr [rax+rax+00h]
0x18007f6ef  test    eax, eax
0x18007f6f1  jz      short loc_18007F6FC
0x18007f6f3  cmp     [rbp+IsMember], edi
0x18007f6f6  jnz     loc_18007F65D
0x18007f6fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f703  cmp     rcx, rbx
0x18007f706  jz      short loc_18007F75C
0x18007f708  test    byte ptr [rcx+1Ch], 80h
0x18007f70c  jz      short loc_18007F733
0x18007f70e  cmp     byte ptr [rcx+19h], 2
0x18007f712  jb      short loc_18007F733
0x18007f714  mov     rcx, [rcx+10h]
0x18007f718  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f71f  mov     edx, 31Ch
0x18007f724  mov     r9d, esi
0x18007f727  call    WPP_SF_d
0x18007f72c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f733  cmp     rcx, rbx
0x18007f736  jz      short loc_18007F75C
0x18007f738  test    byte ptr [rcx+1Ch], 80h
0x18007f73c  jz      short loc_18007F75C
0x18007f73e  cmp     byte ptr [rcx+19h], 6
0x18007f742  jb      short loc_18007F75C
0x18007f744  mov     edx, 31Dh
0x18007f749  mov     rcx, [rcx+10h]
0x18007f74d  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f754  mov     r9d, esi
0x18007f757  call    WPP_SF_d
0x18007f75c  mov     eax, esi
0x18007f75e  jmp     loc_18007FB47
0x18007f763  mov     rax, [rax+10h]
0x18007f767  mov     dword ptr [rax+21Ch], 1
0x18007f771  call    IsRegistryWrite
0x18007f776  lea     rdx, [rbp+var_20]
0x18007f77a  mov     r14d, eax
0x18007f77d  mov     rcx, r15
0x18007f780  test    eax, eax
0x18007f782  jz      short loc_18007F78B
0x18007f784  call    ModifyEntryListInRegistry
0x18007f789  jmp     short loc_18007F790
0x18007f78b  call    ModifyEntryList
0x18007f790  mov     edi, eax
0x18007f792  test    eax, eax
0x18007f794  jz      short loc_18007F7C4
0x18007f796  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f79d  cmp     rcx, rbx
0x18007f7a0  jz      loc_18007FA5C
0x18007f7a6  test    byte ptr [rcx+1Ch], 80h
0x18007f7aa  jz      loc_18007FA5C
0x18007f7b0  cmp     byte ptr [rcx+19h], 2
0x18007f7b4  jb      loc_18007FA5C
0x18007f7ba  mov     edx, 31Fh
0x18007f7bf  jmp     loc_18007F6A9
0x18007f7c4  test    r14d, r14d
0x18007f7c7  jnz     loc_18007F9A7
0x18007f7cd  mov     rax, [r15+30h]
0x18007f7d1  test    rax, rax
0x18007f7d4  jz      loc_18007F9A7
0x18007f7da  mov     r13, [rax]
0x18007f7dd  test    r13, r13
0x18007f7e0  jz      loc_18007F9A7
0x18007f7e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f7ed  mov     r14, [r13+10h]
0x18007f7f1  test    r14, r14
0x18007f7f4  jnz     short loc_18007F82D
0x18007f7f6  cmp     rcx, rbx
0x18007f7f9  jz      loc_18007F932
0x18007f7ff  test    byte ptr [rcx+1Ch], 80h
0x18007f803  jz      loc_18007F932
0x18007f809  cmp     byte ptr [rcx+19h], 2
0x18007f80d  jb      loc_18007F932
0x18007f813  mov     rcx, [rcx+10h]
0x18007f817  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f81e  mov     edx, 320h
0x18007f823  call    WPP_SF_
0x18007f828  jmp     loc_18007F92B
0x18007f82d  mov     rax, cs:g_hmutexPb
0x18007f834  test    rax, rax
0x18007f837  jz      loc_18007F94B
0x18007f83d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007f840  mov     rcx, rax; hHandle
0x18007f843  call    cs:__imp_WaitForSingleObject
0x18007f84a  nop     dword ptr [rax+rax+00h]
0x18007f84f  mov     edi, eax
0x18007f851  test    eax, 0FFFFFF7Fh
0x18007f856  jz      short loc_18007F8A7
0x18007f858  call    cs:__imp_GetLastError
0x18007f85f  nop     dword ptr [rax+rax+00h]
0x18007f864  mov     edi, eax
0x18007f866  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f86d  cmp     rcx, rbx
0x18007f870  jz      loc_18007F932
0x18007f876  test    byte ptr [rcx+1Ch], 80h
0x18007f87a  jz      loc_18007F932
0x18007f880  cmp     byte ptr [rcx+19h], 2
0x18007f884  jb      loc_18007F932
0x18007f88a  mov     rcx, [rcx+10h]
0x18007f88e  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f895  mov     edx, 324h
0x18007f89a  mov     r9d, eax
0x18007f89d  call    WPP_SF_d
0x18007f8a2  jmp     loc_18007F92B
0x18007f8a7  cmp     dword ptr [r14], 1F3h
0x18007f8ae  ja      short loc_18007F8E1
0x18007f8b0  movsxd  rax, dword ptr [r14]
0x18007f8b3  lea     rcx, gpRasfiles
0x18007f8ba  mov     rcx, [rcx+rax*8]
0x18007f8be  test    rcx, rcx
0x18007f8c1  jz      short loc_18007F8E1
0x18007f8c3  test    byte ptr [rcx+20h], 4
0x18007f8c7  jnz     short loc_18007F8E1
0x18007f8c9  cmp     byte ptr [rcx+23Ch], 0
0x18007f8d0  jnz     short loc_18007F8E1
0x18007f8d2  cmp     dword ptr [rcx+24h], 0
0x18007f8d6  jz      short loc_18007F918
0x18007f8d8  call    rasWriteFile
0x18007f8dd  test    eax, eax
0x18007f8df  jnz     short loc_18007F918
0x18007f8e1  mov     eax, 270h
0x18007f8e6  mov     edi, eax
0x18007f8e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f8ef  cmp     rcx, rbx
0x18007f8f2  jz      short loc_18007F918
0x18007f8f4  test    byte ptr [rcx+1Ch], 80h
0x18007f8f8  jz      short loc_18007F918
0x18007f8fa  cmp     byte ptr [rcx+19h], 2
0x18007f8fe  jb      short loc_18007F918
0x18007f900  mov     rcx, [rcx+10h]
0x18007f904  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007f90b  mov     edx, 323h
0x18007f910  mov     r9d, eax
0x18007f913  call    WPP_SF_d
0x18007f918  mov     rcx, cs:g_hmutexPb; hMutex
0x18007f91f  call    cs:__imp_ReleaseMutex
0x18007f926  nop     dword ptr [rax+rax+00h]
0x18007f92b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f932  mov     r13, [r13+8]
0x18007f936  mov     eax, edi
0x18007f938  test    r13, r13
0x18007f93b  jnz     loc_18007F7ED
0x18007f941  test    eax, eax
0x18007f943  jnz     loc_18007FA5C
0x18007f949  jmp     short loc_18007F9AE
0x18007f94b  cmp     rcx, rbx
0x18007f94e  jz      short loc_18007F97B
0x18007f950  test    byte ptr [rcx+1Ch], 80h
0x18007f954  jz      short loc_18007F97B
0x18007f956  cmp     byte ptr [rcx+19h], 2
0x18007f95a  jb      short loc_18007F97B
0x18007f95c  mov     rcx, [rcx+10h]
  ... truncated ...
```
