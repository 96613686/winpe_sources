# WritePhonebookFile

- ea: `0x18007b698`
- end: `0x18007bd60`
- name: `WritePhonebookFile`
- size: `1736`
- prototype: `__int64 __fastcall(_QWORD *, _WORD *)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005e408`
- `0x1800650a8`
- `0x180067814`
- `0x180068070`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e5f0`
- `0x18005c020`
- `0x180065c34`
- `0x180067814`
- `0x18006d96c`
- `0x180079ee4`
- `0x18007b698`
- `0x18007f200`
- `0x1800817e0`
- `0x180089e30`
- `0x1800905ac`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ba5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ba5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007bb1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18007bb1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ba4d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ba4d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007b8f3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007b8f3`

## string_xrefs

- `0x18007bc74`: `ProfileDelete`
- `0x18007bc82`: `ProfileCreate`

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
    v16 = ModifyEntryListInRegistry(a1, &v28);
  else
    v16 = ModifyEntryList(a1, &v28);
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
        || *(_DWORD *)(v21 + 36) && !rasWriteFile(v21) )
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
0x18007b698  mov     [rsp-38h+arg_10], rbx
0x18007b69d  push    rbp
0x18007b69e  push    rsi
0x18007b69f  push    rdi
0x18007b6a0  push    r12
0x18007b6a2  push    r13
0x18007b6a4  push    r14
0x18007b6a6  push    r15
0x18007b6a8  mov     rbp, rsp
0x18007b6ab  sub     rsp, 40h
0x18007b6af  mov     rax, cs:__security_cookie
0x18007b6b6  xor     rax, rsp
0x18007b6b9  mov     [rbp+var_8], rax
0x18007b6bd  xor     edi, edi
0x18007b6bf  mov     r12, rdx
0x18007b6c2  mov     r15, rcx
0x18007b6c5  test    rdx, rdx
0x18007b6c8  jz      short loc_18007B703
0x18007b6ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b6d1  lea     rbx, WPP_GLOBAL_Control
0x18007b6d8  cmp     rcx, rbx
0x18007b6db  jz      short loc_18007B737
0x18007b6dd  test    byte ptr [rcx+1Ch], 80h
0x18007b6e1  jz      short loc_18007B737
0x18007b6e3  cmp     byte ptr [rcx+19h], 6
0x18007b6e7  jb      short loc_18007B737
0x18007b6e9  mov     rcx, [rcx+10h]
0x18007b6ed  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007b6f4  mov     edx, 314h
0x18007b6f9  mov     r9, r12
0x18007b6fc  call    WPP_SF_S
0x18007b701  jmp     short loc_18007B737
0x18007b703  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b70a  lea     rbx, WPP_GLOBAL_Control
0x18007b711  cmp     rcx, rbx
0x18007b714  jz      short loc_18007B737
0x18007b716  test    byte ptr [rcx+1Ch], 80h
0x18007b71a  jz      short loc_18007B737
0x18007b71c  cmp     byte ptr [rcx+19h], 6
0x18007b720  jb      short loc_18007B737
0x18007b722  mov     rcx, [rcx+10h]
0x18007b726  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007b72d  mov     edx, 315h
0x18007b732  call    WPP_SF_
0x18007b737  mov     [rbp+var_20], edi
0x18007b73a  call    LockDownPolicyExists
0x18007b73f  mov     esi, 5
0x18007b744  test    eax, eax
0x18007b746  jz      short loc_18007B7AA
0x18007b748  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b74f  cmp     rcx, rbx
0x18007b752  jz      loc_18007B966
0x18007b758  test    byte ptr [rcx+1Ch], 80h
0x18007b75c  jz      short loc_18007B783
0x18007b75e  cmp     byte ptr [rcx+19h], 2
0x18007b762  jb      short loc_18007B783
0x18007b764  mov     rcx, [rcx+10h]
0x18007b768  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007b76f  mov     edx, 316h
0x18007b774  mov     r9d, esi
0x18007b777  call    WPP_SF_d
0x18007b77c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b783  cmp     rcx, rbx
0x18007b786  jz      loc_18007B966
0x18007b78c  test    byte ptr [rcx+1Ch], 80h
0x18007b790  jz      loc_18007B966
0x18007b796  cmp     byte ptr [rcx+19h], 6
0x18007b79a  jb      loc_18007B966
0x18007b7a0  mov     edx, 317h
0x18007b7a5  jmp     loc_18007B953
0x18007b7aa  test    r15, r15
0x18007b7ad  jz      loc_18007BCDD
0x18007b7b3  mov     rax, [r15+10h]
0x18007b7b7  test    rax, rax
0x18007b7ba  jz      loc_18007BCDD
0x18007b7c0  test    r12, r12
0x18007b7c3  jz      short loc_18007B838
0x18007b7c5  cmp     [r12], di
0x18007b7ca  jnz     short loc_18007B838
0x18007b7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b7d3  mov     edi, 57h ; 'W'
0x18007b7d8  cmp     rcx, rbx
0x18007b7db  jz      short loc_18007B831
0x18007b7dd  test    byte ptr [rcx+1Ch], 80h
0x18007b7e1  jz      short loc_18007B808
0x18007b7e3  cmp     byte ptr [rcx+19h], 2
0x18007b7e7  jb      short loc_18007B808
0x18007b7e9  mov     rcx, [rcx+10h]
0x18007b7ed  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007b7f4  mov     edx, 31Ah
0x18007b7f9  mov     r9d, edi
0x18007b7fc  call    WPP_SF_d
0x18007b801  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b808  cmp     rcx, rbx
0x18007b80b  jz      short loc_18007B831
0x18007b80d  test    byte ptr [rcx+1Ch], 80h
0x18007b811  jz      short loc_18007B831
0x18007b813  cmp     byte ptr [rcx+19h], 6
0x18007b817  jb      short loc_18007B831
0x18007b819  mov     edx, 31Bh
0x18007b81e  mov     rcx, [rcx+10h]
0x18007b822  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007b829  mov     r9d, edi
0x18007b82c  call    WPP_SF_d
0x18007b831  mov     eax, edi
0x18007b833  jmp     loc_18007BD3C
0x18007b838  test    dword ptr [r15+20h], 900h
0x18007b840  jnz     short loc_18007B86D
0x18007b842  mov     rax, [rax]
0x18007b845  jmp     short loc_18007B868
0x18007b847  mov     rcx, [rax+10h]
0x18007b84b  test    rcx, rcx
0x18007b84e  jz      loc_18007B906
0x18007b854  cmp     [rcx+214h], edi
0x18007b85a  jz      short loc_18007B864
0x18007b85c  cmp     [rcx+224h], edi
0x18007b862  jnz     short loc_18007B8D1
0x18007b864  mov     rax, [rax+8]
0x18007b868  test    rax, rax
0x18007b86b  jnz     short loc_18007B847
0x18007b86d  test    r12, r12
0x18007b870  jz      loc_18007B97B
0x18007b876  mov     rcx, [r15+10h]
0x18007b87a  mov     rdx, r12
0x18007b87d  call    EntryNodeFromName
0x18007b882  test    rax, rax
0x18007b885  jnz     loc_18007B96D
0x18007b88b  mov     edi, 26Fh
0x18007b890  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b897  cmp     rcx, rbx
0x18007b89a  jz      loc_18007BC51
0x18007b8a0  test    byte ptr [rcx+1Ch], 80h
0x18007b8a4  jz      loc_18007BC51
0x18007b8aa  cmp     byte ptr [rcx+19h], 2
0x18007b8ae  jb      loc_18007BC51
0x18007b8b4  mov     edx, 31Eh
0x18007b8b9  mov     rcx, [rcx+10h]
0x18007b8bd  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007b8c4  mov     r9d, edi
0x18007b8c7  call    WPP_SF_d
0x18007b8cc  jmp     loc_18007BC4A
0x18007b8d1  lea     r8, [rbp+IsMember]; IsMember
0x18007b8d5  mov     [rbp+IsMember], edi
0x18007b8d8  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18007b8dc  mov     [rbp+SidToCheck], 101h
0x18007b8e3  xor     ecx, ecx; TokenHandle
0x18007b8e5  mov     [rbp+var_14], 5000000h
0x18007b8ec  mov     [rbp+var_10], 12h
0x18007b8f3  call    cs:__imp_CheckTokenMembership
0x18007b8f9  test    eax, eax
0x18007b8fb  jz      short loc_18007B906
0x18007b8fd  cmp     [rbp+IsMember], edi
0x18007b900  jnz     loc_18007B86D
0x18007b906  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b90d  cmp     rcx, rbx
0x18007b910  jz      short loc_18007B966
0x18007b912  test    byte ptr [rcx+1Ch], 80h
0x18007b916  jz      short loc_18007B93D
0x18007b918  cmp     byte ptr [rcx+19h], 2
0x18007b91c  jb      short loc_18007B93D
0x18007b91e  mov     rcx, [rcx+10h]
0x18007b922  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007b929  mov     edx, 31Ch
0x18007b92e  mov     r9d, esi
0x18007b931  call    WPP_SF_d
0x18007b936  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b93d  cmp     rcx, rbx
0x18007b940  jz      short loc_18007B966
0x18007b942  test    byte ptr [rcx+1Ch], 80h
0x18007b946  jz      short loc_18007B966
0x18007b948  cmp     byte ptr [rcx+19h], 6
0x18007b94c  jb      short loc_18007B966
0x18007b94e  mov     edx, 31Dh
0x18007b953  mov     rcx, [rcx+10h]
0x18007b957  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007b95e  mov     r9d, esi
0x18007b961  call    WPP_SF_d
0x18007b966  mov     eax, esi
0x18007b968  jmp     loc_18007BD3C
0x18007b96d  mov     rax, [rax+10h]
0x18007b971  mov     dword ptr [rax+21Ch], 1
0x18007b97b  call    IsRegistryWrite
0x18007b980  lea     rdx, [rbp+var_20]
0x18007b984  mov     r14d, eax
0x18007b987  mov     rcx, r15
0x18007b98a  test    eax, eax
0x18007b98c  jz      short loc_18007B995
0x18007b98e  call    ModifyEntryListInRegistry
0x18007b993  jmp     short loc_18007B99A
0x18007b995  call    ModifyEntryList
0x18007b99a  mov     edi, eax
0x18007b99c  test    eax, eax
0x18007b99e  jz      short loc_18007B9CE
0x18007b9a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b9a7  cmp     rcx, rbx
0x18007b9aa  jz      loc_18007BC51
0x18007b9b0  test    byte ptr [rcx+1Ch], 80h
0x18007b9b4  jz      loc_18007BC51
0x18007b9ba  cmp     byte ptr [rcx+19h], 2
0x18007b9be  jb      loc_18007BC51
0x18007b9c4  mov     edx, 31Fh
0x18007b9c9  jmp     loc_18007B8B9
0x18007b9ce  test    r14d, r14d
0x18007b9d1  jnz     loc_18007BB9C
0x18007b9d7  mov     rax, [r15+30h]
0x18007b9db  test    rax, rax
0x18007b9de  jz      loc_18007BB9C
0x18007b9e4  mov     r13, [rax]
0x18007b9e7  test    r13, r13
0x18007b9ea  jz      loc_18007BB9C
0x18007b9f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b9f7  mov     r14, [r13+10h]
0x18007b9fb  test    r14, r14
0x18007b9fe  jnz     short loc_18007BA37
0x18007ba00  cmp     rcx, rbx
0x18007ba03  jz      loc_18007BB27
0x18007ba09  test    byte ptr [rcx+1Ch], 80h
0x18007ba0d  jz      loc_18007BB27
0x18007ba13  cmp     byte ptr [rcx+19h], 2
0x18007ba17  jb      loc_18007BB27
0x18007ba1d  mov     rcx, [rcx+10h]
0x18007ba21  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007ba28  mov     edx, 320h
0x18007ba2d  call    WPP_SF_
0x18007ba32  jmp     loc_18007BB20
0x18007ba37  mov     rax, cs:g_hmutexPb
0x18007ba3e  test    rax, rax
0x18007ba41  jz      loc_18007BB40
0x18007ba47  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007ba4a  mov     rcx, rax; hHandle
0x18007ba4d  call    cs:__imp_WaitForSingleObject
0x18007ba53  mov     edi, eax
0x18007ba55  test    eax, 0FFFFFF7Fh
0x18007ba5a  jz      short loc_18007BAA2
0x18007ba5c  call    cs:__imp_GetLastError
0x18007ba62  mov     edi, eax
0x18007ba64  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ba6b  cmp     rcx, rbx
0x18007ba6e  jz      loc_18007BB27
0x18007ba74  test    byte ptr [rcx+1Ch], 80h
0x18007ba78  jz      loc_18007BB27
0x18007ba7e  cmp     byte ptr [rcx+19h], 2
0x18007ba82  jb      loc_18007BB27
0x18007ba88  mov     rcx, [rcx+10h]
0x18007ba8c  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007ba93  mov     edx, 324h
0x18007ba98  mov     r9d, eax
0x18007ba9b  call    WPP_SF_d
0x18007baa0  jmp     short loc_18007BB20
0x18007baa2  cmp     dword ptr [r14], 1F3h
0x18007baa9  ja      short loc_18007BADC
0x18007baab  movsxd  rax, dword ptr [r14]
0x18007baae  lea     rcx, gpRasfiles
0x18007bab5  mov     rcx, [rcx+rax*8]
0x18007bab9  test    rcx, rcx
0x18007babc  jz      short loc_18007BADC
0x18007babe  test    byte ptr [rcx+20h], 4
0x18007bac2  jnz     short loc_18007BADC
0x18007bac4  cmp     byte ptr [rcx+23Ch], 0
0x18007bacb  jnz     short loc_18007BADC
0x18007bacd  cmp     dword ptr [rcx+24h], 0
0x18007bad1  jz      short loc_18007BB13
0x18007bad3  call    rasWriteFile
0x18007bad8  test    eax, eax
0x18007bada  jnz     short loc_18007BB13
0x18007badc  mov     eax, 270h
0x18007bae1  mov     edi, eax
0x18007bae3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007baea  cmp     rcx, rbx
0x18007baed  jz      short loc_18007BB13
0x18007baef  test    byte ptr [rcx+1Ch], 80h
0x18007baf3  jz      short loc_18007BB13
0x18007baf5  cmp     byte ptr [rcx+19h], 2
0x18007baf9  jb      short loc_18007BB13
0x18007bafb  mov     rcx, [rcx+10h]
0x18007baff  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007bb06  mov     edx, 323h
0x18007bb0b  mov     r9d, eax
0x18007bb0e  call    WPP_SF_d
0x18007bb13  mov     rcx, cs:g_hmutexPb; hMutex
0x18007bb1a  call    cs:__imp_ReleaseMutex
0x18007bb20  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bb27  mov     r13, [r13+8]
0x18007bb2b  mov     eax, edi
0x18007bb2d  test    r13, r13
0x18007bb30  jnz     loc_18007B9F7
0x18007bb36  test    eax, eax
0x18007bb38  jnz     loc_18007BC51
0x18007bb3e  jmp     short loc_18007BBA3
0x18007bb40  cmp     rcx, rbx
0x18007bb43  jz      short loc_18007BB70
0x18007bb45  test    byte ptr [rcx+1Ch], 80h
0x18007bb49  jz      short loc_18007BB70
0x18007bb4b  cmp     byte ptr [rcx+19h], 2
0x18007bb4f  jb      short loc_18007BB70
0x18007bb51  mov     rcx, [rcx+10h]
0x18007bb55  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007bb5c  mov     edx, 321h
0x18007bb61  mov     r9d, edi
0x18007bb64  call    WPP_SF_d
  ... truncated ...
```
