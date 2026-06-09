# SaveCredentialsInCredMan

- ea: `0x180055360`
- end: `0x180055c7a`
- name: `SaveCredentialsInCredMan`
- size: `2330`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180052b1c`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000bf74`
- `0x18003b72c`
- `0x180040998`
- `0x18004236c`
- `0x180049c18`
- `0x1800548f0`
- `0x180055360`
- `0x180055c80`
- `0x1800e8e96`

## import_xrefs

- `msvcrt!strpbrk` at `0x180055929`
- `msvcrt!strpbrk` at `0x180055929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005589d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005589d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800555b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055baa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055c11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055c24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800555b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055baa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055c11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055c24`
- `api-ms-win-security-credentials-l1-1-0!CredReadA` at `0x1800556f4`
- `api-ms-win-security-credentials-l1-1-0!CredReadA` at `0x1800556f4`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180055ad2`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180055ae9`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180055ad2`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180055ae9`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x180055afb`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x180055afb`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180055b87`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180055b87`

## pseudocode

```c
__int64 __fastcall SaveCredentialsInCredMan(__int64 a1)
{
  struct _LIST_ENTRY *v2; // rbx
  __int64 v3; // rsi
  unsigned int v4; // edi
  __int64 v5; // r12
  HLOCAL *v6; // r15
  STRSAFE_LPSTR v7; // r14
  bool v8; // zf
  __int64 v9; // rdx
  __int64 UserData; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  _BYTE *v14; // rax
  __int64 v15; // rax
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rbx
  __int64 LastError; // r9
  __int64 v20; // rdx
  unsigned int refreshed; // eax
  CHAR *v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // r9
  _OWORD *v25; // rcx
  STRSAFE_LPSTR v26; // rax
  __int64 v27; // rdx
  __int128 v28; // xmm1
  unsigned int v29; // eax
  struct _CREDENTIALA *v30; // rax
  DWORD v31; // eax
  _BYTE *v32; // rax
  __int64 v33; // rcx
  _BYTE *v34; // rax
  __int64 v35; // rdx
  DATA_BLOB pDataIn; // [rsp+30h] [rbp-49h] BYREF
  struct _CREDENTIALA v38; // [rsp+40h] [rbp-39h] BYREF
  int v39; // [rsp+E0h] [rbp+67h] BYREF
  STRSAFE_LPSTR pszDest; // [rsp+E8h] [rbp+6Fh]
  __int64 v41; // [rsp+F0h] [rbp+77h]
  PCREDENTIALA Credential; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 111, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  v4 = 0;
  v5 = 80;
  memset_0(&v38, 0, sizeof(v38));
  v6 = 0;
  v7 = 0;
  *(_QWORD *)(&pDataIn.cbData + 1) = 0;
  v8 = (*(_BYTE *)(a1 + 112) & 0x20) == 0;
  *(_QWORD *)&pDataIn.cbData = 0;
  v41 = 0;
  pszDest = 0;
  v39 = 0;
  Credential = 0;
  if ( v8 )
  {
    if ( (*(_DWORD *)(a1 + 168) & 8) == 0 )
    {
      if ( v2 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v4;
      if ( (HIDWORD(v2[1].Blink) & 0x2000) == 0 || BYTE1(v2[1].Blink) < 4u )
        goto LABEL_151;
      v9 = 113;
      goto LABEL_10;
    }
    UserData = GetUserData(a1 + 32, 6);
    v12 = 3112;
    if ( UserData )
    {
      if ( *(_DWORD *)(UserData + 20) >= 0xC28u )
        v3 = UserData + 24;
      if ( !*(_QWORD *)(a1 + 920) )
        goto LABEL_39;
    }
    else if ( !*(_QWORD *)(a1 + 920) )
    {
      v4 = 1168;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        v7 = 0;
        goto LABEL_136;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 114, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 1168);
      goto LABEL_11;
    }
    if ( v3 && *(_DWORD *)(v3 + 4) )
    {
      v13 = 2048;
      v14 = (_BYTE *)(v3 + 8);
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
      *(_DWORD *)(v3 + 4) = 0;
    }
    SetUserData(a1 + 32, 6, *(_QWORD *)(a1 + 920), 3112);
    v15 = GetUserData(a1 + 32, 6);
    if ( !v15 )
    {
      v16 = 1168;
      v4 = 1168;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_136;
      }
      v17 = 115;
      goto LABEL_37;
    }
    v3 = v15 + 24;
    LocalFree(*(HLOCAL *)(a1 + 920));
    *(_QWORD *)(a1 + 920) = 0;
LABEL_39:
    if ( !v3 )
    {
      v16 = 1168;
      v4 = 1168;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_136;
      }
      v17 = 116;
      goto LABEL_37;
    }
    if ( (*(_BYTE *)v3 & 8) != 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 117, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
      }
      v16 = SaveCredentialsInCredManW(v3, &v39, v11, v12);
      v4 = v16;
      if ( v16 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_136;
        }
        v17 = 118;
        goto LABEL_37;
      }
      LODWORD(v7) = v39;
    }
    if ( (*(_DWORD *)v3 & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 119, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
      }
      v18 = *(_QWORD *)(a1 + 16);
      if ( !(_DWORD)v7 )
      {
        if ( CredReadA("*Session", 3u, 0, &Credential) )
        {
          if ( Credential && SLOBYTE(Credential->Flags) < 0 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 120, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
            }
            goto LABEL_87;
          }
        }
        else
        {
          LastError = GetLastError();
          if ( (_DWORD)LastError == 1168 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 121, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
            }
          }
          else if ( (_DWORD)LastError
                 && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 122, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, LastError);
          }
        }
        if ( (*(_BYTE *)v3 & 8) != 0 )
          v20 = v3 + 2056;
        else
          v20 = 0;
        refreshed = RefreshKerbScCreds(a1, v20);
        v4 = refreshed;
        if ( refreshed )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 123, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, refreshed);
          }
          v4 = 0;
        }
      }
LABEL_87:
      if ( !FindConnection(v18) )
      {
        v4 = 668;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 124, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 668);
          v2 = WPP_GLOBAL_Control;
        }
        v3 = 0;
        goto LABEL_12;
      }
      goto LABEL_134;
    }
    if ( (*(_DWORD *)v3 & 0xC) == 4 )
    {
      pszDest = (STRSAFE_LPSTR)LocalAlloc(0x40u, 0x100u);
      v7 = pszDest;
      if ( !pszDest )
      {
        v16 = GetLastError();
        v4 = v16;
        if ( v16 )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_136;
          }
          v17 = 125;
LABEL_37:
          WPP_SF_d(v2[1].Flink, v17, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v16);
          v2 = WPP_GLOBAL_Control;
          goto LABEL_136;
        }
LABEL_133:
        v2 = WPP_GLOBAL_Control;
        goto LABEL_136;
      }
      if ( !*(_BYTE *)(v3 + 2568) || strpbrk((const char *)(v3 + 2056), "@\\") )
      {
        v22 = pszDest;
        v25 = (_OWORD *)(v3 + 2056);
        v26 = pszDest;
        v27 = 2;
        do
        {
          *(_OWORD *)v26 = *v25;
          *((_OWORD *)v26 + 1) = v25[1];
          *((_OWORD *)v26 + 2) = v25[2];
          *((_OWORD *)v26 + 3) = v25[3];
          *((_OWORD *)v26 + 4) = v25[4];
          *((_OWORD *)v26 + 5) = v25[5];
          *((_OWORD *)v26 + 6) = v25[6];
          v28 = v25[7];
          v25 += 8;
          *((_OWORD *)v26 + 7) = v28;
          v26 += 128;
          --v27;
        }
        while ( v27 );
      }
      else
      {
        v22 = pszDest;
        if ( StringCchPrintfA(pszDest, 0x100u, "%s\\%s", (const char *)(v3 + 2568), (const char *)(v3 + 2056)) )
        {
          v4 = 122;
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_109;
          }
          v23 = 126;
          v24 = 122;
LABEL_107:
          WPP_SF_d(v2[1].Flink, v23, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v24);
          goto LABEL_108;
        }
      }
      pDataIn.cbData = *(_DWORD *)(v3 + 4);
      pDataIn.pbData = (BYTE *)(v3 + 8);
      v29 = DecodeData(&pDataIn);
      v4 = v29;
      if ( v29 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          v6 = (HLOCAL *)v41;
          goto LABEL_109;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 127, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v29);
        v6 = (HLOCAL *)v41;
LABEL_108:
        v2 = WPP_GLOBAL_Control;
LABEL_109:
        v7 = pszDest;
        goto LABEL_136;
      }
      v30 = &v38;
      do
      {
        LOBYTE(v30->Flags) = 0;
        v30 = (struct _CREDENTIALA *)((char *)v30 + 1);
        --v5;
      }
      while ( v5 );
      v6 = (HLOCAL *)v41;
      v38.Persist = 1;
      v38.Type = 2;
      v38.UserName = v22;
      if ( v41 )
        v38.CredentialBlobSize = *(_DWORD *)v41;
      else
        v38.CredentialBlobSize = 0;
      if ( v41 )
        v38.CredentialBlob = *(LPBYTE *)(v41 + 8);
      else
        v38.CredentialBlob = 0;
      v38.TargetName = (LPSTR)"*Session";
      CredDeleteA("*Session", 3u, 0);
      CredDeleteA(v38.TargetName, 2u, 0);
      if ( !CredWriteA(&v38, 0) )
      {
        v31 = GetLastError();
        v4 = v31;
        if ( !v31 )
        {
          v7 = pszDest;
          goto LABEL_133;
        }
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_109;
        }
        v23 = 128;
        v24 = v31;
        goto LABEL_107;
      }
    }
LABEL_134:
    *(_DWORD *)(a1 + 112) |= 0x20u;
    goto LABEL_108;
  }
  if ( v2 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v4;
  if ( (HIDWORD(v2[1].Blink) & 0x2000) != 0 && BYTE1(v2[1].Blink) >= 4u )
  {
    v9 = 112;
LABEL_10:
    WPP_SF_(v2[1].Flink, v9, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
LABEL_11:
    v2 = WPP_GLOBAL_Control;
LABEL_12:
    v7 = 0;
LABEL_136:
    if ( Credential )
    {
      CredFree(Credential);
      v2 = WPP_GLOBAL_Control;
      Credential = 0;
    }
    if ( v7 )
    {
      LocalFree(v7);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v3 && *(_DWORD *)(v3 + 4) )
    {
      v32 = (_BYTE *)(v3 + 8);
      v33 = 2048;
      do
      {
        *v32++ = 0;
        --v33;
      }
      while ( v33 );
      *(_DWORD *)(v3 + 4) = 0;
      v2 = WPP_GLOBAL_Control;
    }
    if ( v6 )
    {
      v34 = v6[1];
      if ( v34 )
      {
        v35 = *(unsigned int *)v6;
        if ( *(_DWORD *)v6 )
        {
          do
          {
            *v34++ = 0;
            --v35;
          }
          while ( v35 );
        }
        LocalFree(v6[1]);
        v6[1] = 0;
      }
      LocalFree(v6);
      v2 = WPP_GLOBAL_Control;
    }
  }
LABEL_151:
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v2[1].Blink) & 0x2000) != 0
    && BYTE1(v2[1].Blink) >= 6u )
  {
    WPP_SF_d(v2[1].Flink, 129, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180055360  push    rbp
0x180055362  push    rbx
0x180055363  push    rsi
0x180055364  push    rdi
0x180055365  push    r12
0x180055367  push    r13
0x180055369  push    r14
0x18005536b  push    r15
0x18005536d  lea     rbp, [rsp-1Fh]
0x180055372  sub     rsp, 98h
0x180055379  mov     r13, rcx
0x18005537c  mov     rbx, cs:WPP_GLOBAL_Control
0x180055383  lea     rax, WPP_GLOBAL_Control
0x18005538a  cmp     rbx, rax
0x18005538d  jz      short loc_1800553BA
0x18005538f  test    dword ptr [rbx+1Ch], 2000h
0x180055396  jz      short loc_1800553BA
0x180055398  cmp     byte ptr [rbx+19h], 6
0x18005539c  jb      short loc_1800553BA
0x18005539e  mov     rcx, [rbx+10h]
0x1800553a2  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800553a9  mov     edx, 6Fh ; 'o'
0x1800553ae  call    WPP_SF_
0x1800553b3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800553ba  xor     esi, esi
0x1800553bc  lea     rcx, [rbp+57h+var_90]; void *
0x1800553c0  xor     edx, edx; Val
0x1800553c2  xor     edi, edi
0x1800553c4  lea     r12d, [rsi+50h]
0x1800553c8  mov     r8d, r12d; Size
0x1800553cb  call    memset_0
0x1800553d0  xor     eax, eax
0x1800553d2  xor     r15d, r15d
0x1800553d5  xor     r14d, r14d
0x1800553d8  mov     qword ptr [rbp+57h+pDataIn+4], rax
0x1800553dc  test    byte ptr [r13+70h], 20h
0x1800553e1  mov     [rbp-49h], rax
0x1800553e5  mov     [rbp+57h+arg_10], r15
0x1800553e9  mov     [rbp+57h+pszDest], rax
0x1800553ed  mov     [rbp+57h+arg_0], r14d
0x1800553f1  mov     [rbp+57h+Credential], rax
0x1800553f5  jz      short loc_180055440
0x1800553f7  lea     r12, WPP_GLOBAL_Control
0x1800553fe  cmp     rbx, r12
0x180055401  jz      loc_180055C63
0x180055407  test    dword ptr [rbx+1Ch], 2000h
0x18005540e  jz      loc_180055C37
0x180055414  cmp     byte ptr [rbx+19h], 4
0x180055418  jb      loc_180055C37
0x18005541e  lea     edx, [rsi+70h]
0x180055421  mov     rcx, [rbx+10h]
0x180055425  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005542c  call    WPP_SF_
0x180055431  mov     rbx, cs:WPP_GLOBAL_Control
0x180055438  mov     r14, rsi
0x18005543b  jmp     loc_180055B7E
0x180055440  mov     eax, [r13+0A8h]
0x180055447  test    al, 8
0x180055449  jnz     short loc_180055479
0x18005544b  lea     r12, WPP_GLOBAL_Control
0x180055452  cmp     rbx, r12
0x180055455  jz      loc_180055C63
0x18005545b  test    dword ptr [rbx+1Ch], 2000h
0x180055462  jz      loc_180055C37
0x180055468  cmp     byte ptr [rbx+19h], 4
0x18005546c  jb      loc_180055C37
0x180055472  mov     edx, 71h ; 'q'
0x180055477  jmp     short loc_180055421
0x180055479  lea     rbx, [r13+20h]
0x18005547d  mov     edx, 6
0x180055482  mov     rcx, rbx
0x180055485  call    GetUserData
0x18005548a  xor     ecx, ecx
0x18005548c  mov     r9d, 0C28h
0x180055492  test    rax, rax
0x180055495  jnz     short loc_1800554F0
0x180055497  cmp     [r13+398h], rcx
0x18005549e  jnz     short loc_180055507
0x1800554a0  mov     eax, 490h
0x1800554a5  mov     edi, eax
0x1800554a7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800554ae  lea     r12, WPP_GLOBAL_Control
0x1800554b5  cmp     rbx, r12
0x1800554b8  jz      loc_180055B7B
0x1800554be  test    dword ptr [rbx+1Ch], 2000h
0x1800554c5  jz      loc_180055B7B
0x1800554cb  cmp     byte ptr [rbx+19h], 2
0x1800554cf  jb      loc_180055B7B
0x1800554d5  lea     edx, [rcx+72h]
0x1800554d8  mov     r9d, eax
0x1800554db  mov     rcx, [rbx+10h]
0x1800554df  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800554e6  call    WPP_SF_d
0x1800554eb  jmp     loc_180055431
0x1800554f0  cmp     [rax+14h], r9d
0x1800554f4  jb      short loc_1800554FA
0x1800554f6  lea     rsi, [rax+18h]
0x1800554fa  cmp     [r13+398h], rcx
0x180055501  jz      loc_1800555C7
0x180055507  test    rsi, rsi
0x18005550a  jz      short loc_180055528
0x18005550c  cmp     [rsi+4], ecx
0x18005550f  jbe     short loc_180055528
0x180055511  mov     edx, 800h
0x180055516  lea     rax, [rsi+8]
0x18005551a  mov     [rax], cl
0x18005551c  inc     rax
0x18005551f  sub     rdx, 1
0x180055523  jnz     short loc_18005551A
0x180055525  mov     [rsi+4], ecx
0x180055528  mov     r8, [r13+398h]
0x18005552f  mov     edx, 6
0x180055534  mov     rcx, rbx
0x180055537  call    SetUserData
0x18005553c  mov     edx, 6
0x180055541  mov     rcx, rbx
0x180055544  call    GetUserData
0x180055549  test    rax, rax
0x18005554c  jnz     short loc_1800555A7
0x18005554e  mov     eax, 490h
0x180055553  mov     edi, eax
0x180055555  mov     rbx, cs:WPP_GLOBAL_Control
0x18005555c  lea     r12, WPP_GLOBAL_Control
0x180055563  cmp     rbx, r12
0x180055566  jz      loc_180055B7E
0x18005556c  test    dword ptr [rbx+1Ch], 2000h
0x180055573  jz      loc_180055B7E
0x180055579  cmp     byte ptr [rbx+19h], 2
0x18005557d  jb      loc_180055B7E
0x180055583  mov     edx, 73h ; 's'
0x180055588  mov     rcx, [rbx+10h]
0x18005558c  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180055593  mov     r9d, eax
0x180055596  call    WPP_SF_d
0x18005559b  mov     rbx, cs:WPP_GLOBAL_Control
0x1800555a2  jmp     loc_180055B7E
0x1800555a7  mov     rcx, [r13+398h]; hMem
0x1800555ae  lea     rsi, [rax+18h]
0x1800555b2  call    cs:__imp_LocalFree
0x1800555b9  nop     dword ptr [rax+rax+00h]
0x1800555be  xor     ecx, ecx
0x1800555c0  mov     [r13+398h], rcx
0x1800555c7  test    rsi, rsi
0x1800555ca  jnz     short loc_180055606
0x1800555cc  mov     eax, 490h
0x1800555d1  mov     edi, eax
0x1800555d3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800555da  lea     r12, WPP_GLOBAL_Control
0x1800555e1  cmp     rbx, r12
0x1800555e4  jz      loc_180055B7E
0x1800555ea  test    dword ptr [rbx+1Ch], 2000h
0x1800555f1  jz      loc_180055B7E
0x1800555f7  cmp     byte ptr [rbx+19h], 2
0x1800555fb  jb      loc_180055B7E
0x180055601  lea     edx, [rsi+74h]
0x180055604  jmp     short loc_180055588
0x180055606  test    byte ptr [rsi], 8
0x180055609  jz      loc_180055694
0x18005560f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055616  lea     rax, WPP_GLOBAL_Control
0x18005561d  cmp     rcx, rax
0x180055620  jz      short loc_180055646
0x180055622  test    dword ptr [rcx+1Ch], 2000h
0x180055629  jz      short loc_180055646
0x18005562b  cmp     byte ptr [rcx+19h], 5
0x18005562f  jb      short loc_180055646
0x180055631  mov     rcx, [rcx+10h]
0x180055635  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005563c  mov     edx, 75h ; 'u'
0x180055641  call    WPP_SF_
0x180055646  lea     rdx, [rbp+57h+arg_0]
0x18005564a  mov     rcx, rsi
0x18005564d  call    SaveCredentialsInCredManW
0x180055652  mov     edi, eax
0x180055654  test    eax, eax
0x180055656  jz      short loc_180055690
0x180055658  mov     rbx, cs:WPP_GLOBAL_Control
0x18005565f  lea     r12, WPP_GLOBAL_Control
0x180055666  cmp     rbx, r12
0x180055669  jz      loc_180055B7E
0x18005566f  test    dword ptr [rbx+1Ch], 2000h
0x180055676  jz      loc_180055B7E
0x18005567c  cmp     byte ptr [rbx+19h], 2
0x180055680  jb      loc_180055B7E
0x180055686  mov     edx, 76h ; 'v'
0x18005568b  jmp     loc_180055588
0x180055690  mov     r14d, [rbp+57h+arg_0]
0x180055694  mov     eax, [rsi]
0x180055696  test    al, 2
0x180055698  jz      loc_180055889
0x18005569e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800556a5  lea     r12, WPP_GLOBAL_Control
0x1800556ac  cmp     rcx, r12
0x1800556af  jz      short loc_1800556D5
0x1800556b1  test    dword ptr [rcx+1Ch], 2000h
0x1800556b8  jz      short loc_1800556D5
0x1800556ba  cmp     byte ptr [rcx+19h], 5
0x1800556be  jb      short loc_1800556D5
0x1800556c0  mov     rcx, [rcx+10h]
0x1800556c4  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800556cb  mov     edx, 77h ; 'w'
0x1800556d0  call    WPP_SF_
0x1800556d5  mov     rbx, [r13+10h]
0x1800556d9  test    r14d, r14d
0x1800556dc  jnz     loc_180055834
0x1800556e2  lea     r9, [rbp+57h+Credential]; Credential
0x1800556e6  xor     r8d, r8d; Flags
0x1800556e9  lea     edx, [r14+3]; Type
0x1800556ed  lea     rcx, aSession_0; "*Session"
0x1800556f4  call    cs:__imp_CredReadA
0x1800556fb  nop     dword ptr [rax+rax+00h]
0x180055700  cmp     eax, 1
0x180055703  jnz     short loc_180055761
0x180055705  mov     rax, [rbp+57h+Credential]
0x180055709  test    rax, rax
0x18005570c  jz      loc_1800557E1
0x180055712  mov     r14d, 80h
0x180055718  test    [rax], r14b
0x18005571b  jz      loc_1800557E1
0x180055721  mov     rcx, cs:WPP_GLOBAL_Control
0x180055728  cmp     rcx, r12
0x18005572b  jz      loc_180055834
0x180055731  test    dword ptr [rcx+1Ch], 2000h
0x180055738  jz      loc_180055834
0x18005573e  cmp     byte ptr [rcx+19h], 4
0x180055742  jb      loc_180055834
0x180055748  mov     rcx, [rcx+10h]
0x18005574c  lea     edx, [r14-8]
0x180055750  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180055757  call    WPP_SF_
0x18005575c  jmp     loc_180055834
0x180055761  call    cs:__imp_GetLastError
0x180055768  nop     dword ptr [rax+rax+00h]
0x18005576d  mov     r9d, eax
0x180055770  mov     eax, 490h
0x180055775  cmp     r9d, eax
0x180055778  jnz     short loc_1800557AC
0x18005577a  mov     rcx, cs:WPP_GLOBAL_Control
0x180055781  cmp     rcx, r12
0x180055784  jz      short loc_1800557E1
0x180055786  test    dword ptr [rcx+1Ch], 2000h
0x18005578d  jz      short loc_1800557E1
0x18005578f  cmp     byte ptr [rcx+19h], 4
0x180055793  jb      short loc_1800557E1
0x180055795  mov     rcx, [rcx+10h]
0x180055799  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800557a0  mov     edx, 79h ; 'y'
0x1800557a5  call    WPP_SF_
0x1800557aa  jmp     short loc_1800557E1
0x1800557ac  test    r9d, r9d
0x1800557af  jz      short loc_1800557E1
0x1800557b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800557b8  cmp     rcx, r12
0x1800557bb  jz      short loc_1800557E1
0x1800557bd  test    dword ptr [rcx+1Ch], 2000h
0x1800557c4  jz      short loc_1800557E1
0x1800557c6  cmp     byte ptr [rcx+19h], 2
0x1800557ca  jb      short loc_1800557E1
0x1800557cc  mov     rcx, [rcx+10h]
0x1800557d0  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800557d7  mov     edx, 7Ah ; 'z'
0x1800557dc  call    WPP_SF_d
0x1800557e1  test    byte ptr [rsi], 8
0x1800557e4  jz      short loc_1800557EF
0x1800557e6  lea     rdx, [rsi+808h]
0x1800557ed  jmp     short loc_1800557F1
0x1800557ef  xor     edx, edx
0x1800557f1  mov     rcx, r13
0x1800557f4  call    RefreshKerbScCreds
0x1800557f9  mov     edi, eax
0x1800557fb  test    eax, eax
0x1800557fd  jz      short loc_180055834
0x1800557ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180055806  cmp     rcx, r12
0x180055809  jz      short loc_180055832
0x18005580b  test    dword ptr [rcx+1Ch], 2000h
0x180055812  jz      short loc_180055832
0x180055814  cmp     byte ptr [rcx+19h], 2
0x180055818  jb      short loc_180055832
0x18005581a  mov     rcx, [rcx+10h]
0x18005581e  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180055825  mov     edx, 7Bh ; '{'
0x18005582a  mov     r9d, eax
0x18005582d  call    WPP_SF_d
0x180055832  xor     edi, edi
0x180055834  mov     rcx, rbx
0x180055837  call    FindConnection
0x18005583c  test    rax, rax
0x18005583f  jnz     loc_180055B71
0x180055845  mov     edi, 29Ch
0x18005584a  mov     rbx, cs:WPP_GLOBAL_Control
0x180055851  cmp     rbx, r12
0x180055854  jz      short loc_180055882
0x180055856  test    dword ptr [rbx+1Ch], 2000h
0x18005585d  jz      short loc_180055882
0x18005585f  cmp     byte ptr [rbx+19h], 2
0x180055863  jb      short loc_180055882
0x180055865  mov     rcx, [rbx+10h]
0x180055869  lea     edx, [rax+7Ch]
0x18005586c  mov     r9d, edi
  ... truncated ...
```
