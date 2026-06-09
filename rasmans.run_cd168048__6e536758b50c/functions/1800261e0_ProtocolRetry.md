# ProtocolRetry

- ea: `0x1800261e0`
- end: `0x180026970`
- name: `ProtocolRetry`
- size: `1936`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037cb0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x1800179d8`
- `0x18001975c`
- `0x1800261e0`
- `0x18003cc9c`
- `0x18004236c`
- `0x1800b1d2c`
- `0x1800e8e96`
- `0x1800e8ea2`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026610`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800268c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800268c9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026369`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026403`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800264f4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026794`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026369`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026403`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800264f4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026794`

## pseudocode

```c
void __fastcall ProtocolRetry(__int64 a1, __int64 a2, __int64 a3)
{
  struct _LIST_ENTRY *v5; // rcx
  int v6; // r15d
  __int64 v7; // r13
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  DWORD LastError; // eax
  _OWORD *v12; // rbx
  __int64 v13; // rcx
  CHAR *v14; // rax
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  DWORD v22; // eax
  __int64 v23; // rdx
  CHAR *v24; // rax
  _OWORD *v25; // rcx
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int64 v33; // rcx
  CHAR *v34; // rax
  DWORD CurrentProcessId; // eax
  unsigned int EntryDialParams; // eax
  struct _LIST_ENTRY *v37; // rcx
  __int64 v38; // rdx
  __int64 UserData; // rax
  DWORD v40; // eax
  __int64 v41; // rcx
  WCHAR *v42; // rax
  __int64 v43; // rax
  __int64 (__fastcall *v44)(__int64); // rax
  unsigned int *v45; // rax
  __int64 v46; // rcx
  _BYTE *i; // rax
  _BYTE *v48; // rax
  int v49[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v50[1034]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[275]; // [rsp+45Ah] [rbp+35Ah] BYREF
  CHAR MultiByteStr[16]; // [rsp+680h] [rbp+580h] BYREF
  CHAR v53[272]; // [rsp+690h] [rbp+590h] BYREF
  CHAR lpMultiByteStr[272]; // [rsp+7A0h] [rbp+6A0h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 900, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = 1;
  v7 = 514;
  if ( !a1 )
  {
    v8 = 615;
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 2u )
    {
      v9 = 901;
LABEL_10:
      v10 = v8;
LABEL_11:
      WPP_SF_d(v5[1].Flink, v9, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v10);
      goto LABEL_90;
    }
    goto LABEL_90;
  }
  if ( *(_DWORD *)(a1 + 28) == 2 )
  {
    if ( *(_DWORD *)(a1 + 1360) == 3 )
    {
      *(_QWORD *)(a3 + 1088) = *(_QWORD *)(a1 + 1272);
      goto LABEL_81;
    }
    *(_OWORD *)MultiByteStr = 0;
    memset_0(lpMultiByteStr, 0, 0x101u);
    memset_0(v53, 0, 0x101u);
    if ( !WideCharToMultiByte(0, 0x400u, (LPCWCH)(a3 + 1052), -1, MultiByteStr, 16, 0, 0) )
    {
      LastError = GetLastError();
      v8 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_90;
      }
      v9 = 903;
      goto LABEL_24;
    }
    *(_OWORD *)(a3 + 1052) = *(_OWORD *)MultiByteStr;
    v12 = (_OWORD *)(a3 + 24);
    if ( !WideCharToMultiByte(0, 0x400u, (LPCWCH)(a3 + 24), -1, lpMultiByteStr, 257, 0, 0) )
    {
      LastError = GetLastError();
      v8 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_90;
      }
      v9 = 904;
      goto LABEL_24;
    }
    v13 = 2;
    v14 = lpMultiByteStr;
    do
    {
      v15 = *((_OWORD *)v14 + 1);
      *v12 = *(_OWORD *)v14;
      v16 = *((_OWORD *)v14 + 2);
      v12[1] = v15;
      v17 = *((_OWORD *)v14 + 3);
      v12[2] = v16;
      v18 = *((_OWORD *)v14 + 4);
      v12[3] = v17;
      v19 = *((_OWORD *)v14 + 5);
      v12[4] = v18;
      v20 = *((_OWORD *)v14 + 6);
      v12[5] = v19;
      v21 = *((_OWORD *)v14 + 7);
      v14 += 128;
      v12[6] = v20;
      v12[7] = v21;
      v12 += 8;
      --v13;
    }
    while ( v13 );
    v6 = 0;
    *(_BYTE *)v12 = *v14;
    if ( *(_QWORD *)(a1 + 1248) )
    {
      LastError = DecryptPassword(a1, a3 + 538);
      v8 = LastError;
      if ( LastError )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_90;
        }
        v9 = 906;
LABEL_24:
        v10 = LastError;
        goto LABEL_11;
      }
    }
    else
    {
      if ( WideCharToMultiByte(0, 0x400u, (LPCWCH)(a3 + 538), -1, v53, 257, 0, 0) )
      {
        v23 = 2;
        v24 = v53;
        v8 = 0;
        v25 = (_OWORD *)(a3 + 538);
        do
        {
          v26 = *((_OWORD *)v24 + 1);
          *v25 = *(_OWORD *)v24;
          v27 = *((_OWORD *)v24 + 2);
          v25[1] = v26;
          v28 = *((_OWORD *)v24 + 3);
          v25[2] = v27;
          v29 = *((_OWORD *)v24 + 4);
          v25[3] = v28;
          v30 = *((_OWORD *)v24 + 5);
          v25[4] = v29;
          v31 = *((_OWORD *)v24 + 6);
          v25[5] = v30;
          v32 = *((_OWORD *)v24 + 7);
          v24 += 128;
          v25[6] = v31;
          v25[7] = v32;
          v25 += 8;
          --v23;
        }
        while ( v23 );
        *(_BYTE *)v25 = *v24;
      }
      else
      {
        v22 = GetLastError();
        v8 = v22;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 905, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v22);
        }
      }
      v33 = 257;
      v34 = v53;
      do
      {
        *v34++ = 0;
        --v33;
      }
      while ( v33 );
      v6 = 1;
      if ( v8 )
        goto LABEL_90;
    }
    if ( !strcmp_0((const char *)(a3 + 538), "****************") )
    {
      v6 = 0;
      if ( g_fInProc )
      {
        memset_0(v50, 0, 0x630u);
        v49[0] = -2147483646;
        UserData = GetUserData(a1 + 1080, 9);
        if ( !UserData )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 908, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
          }
          goto LABEL_80;
        }
        EntryDialParams = GetEntryDialParams(0, *(unsigned int *)(UserData + 24), v49, v50, 1);
        if ( !EntryDialParams && (v49[0] & 2) != 0 )
        {
          if ( WideCharToMultiByte(0, 0x400u, WideCharStr, -1, (LPSTR)(a3 + 538), 257, 0, 0) )
          {
            v6 = 1;
          }
          else
          {
            v40 = GetLastError();
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 910, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v40);
            }
          }
          v41 = 514;
          v42 = WideCharStr;
          do
          {
            *(_BYTE *)v42 = 0;
            v42 = (WCHAR *)((char *)v42 + 1);
            --v41;
          }
          while ( v41 );
          if ( (v49[0] & 0x40) != 0 )
          {
            v43 = *(_QWORD *)(a1 + 1064);
            if ( v43 )
              *(_DWORD *)(v43 + 112) |= 2u;
          }
          goto LABEL_80;
        }
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v38 = 909;
LABEL_79:
          WPP_SF_d(v37[1].Flink, v38, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, EntryDialParams);
        }
      }
      else
      {
        CurrentProcessId = GetCurrentProcessId();
        EntryDialParams = DwGetPasswordA(a1, a3 + 538, CurrentProcessId);
        if ( EntryDialParams )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_80;
          }
          v38 = 907;
          goto LABEL_79;
        }
        v6 = 1;
      }
    }
LABEL_80:
    DwCacheCredMgrCredentials(a3, a1);
LABEL_81:
    v44 = (__int64 (__fastcall *)(__int64))qword_18010B098[8 * (__int64)*(int *)(a1 + 1360)];
    if ( v44 )
    {
      v8 = v44(a3);
      if ( v8 )
      {
        if ( *(_DWORD *)(a1 + 1360) == 3 )
        {
          v45 = *(unsigned int **)(a1 + 1272);
          if ( v45 )
          {
            v46 = *v45;
            for ( i = v45 + 1; v46; --v46 )
              *i++ = 0;
            LocalFree(*(HLOCAL *)(a1 + 1272));
          }
        }
      }
      *(_QWORD *)(a1 + 1272) = 0;
    }
    else
    {
      v8 = 839;
    }
    goto LABEL_90;
  }
  v8 = 619;
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v5[1].Blink) & 0x2000) != 0
    && BYTE1(v5[1].Blink) >= 2u )
  {
    v9 = 902;
    goto LABEL_10;
  }
LABEL_90:
  *(_QWORD *)(a3 + 1088) = 0;
  if ( v6 )
  {
    v48 = (_BYTE *)(a3 + 538);
    do
    {
      *v48++ = 0;
      --v7;
    }
    while ( v7 );
  }
  *(_DWORD *)a3 = v8;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 911, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v8);
  }
}

```

## disassembly

```asm
0x1800261e0  mov     [rsp-8+arg_8], rbx
0x1800261e5  mov     [rsp-8+arg_18], rsi
0x1800261ea  push    rbp
0x1800261eb  push    r12
0x1800261ed  push    r13
0x1800261ef  push    r14
0x1800261f1  push    r15
0x1800261f3  lea     rbp, [rsp-7C0h]
0x1800261fb  sub     rsp, 8C0h
0x180026202  mov     rax, cs:__security_cookie
0x180026209  xor     rax, rsp
0x18002620c  mov     [rbp+7E0h+var_30], rax
0x180026213  mov     r12, r8
0x180026216  mov     rsi, rcx
0x180026219  mov     rcx, cs:WPP_GLOBAL_Control
0x180026220  lea     rdx, WPP_GLOBAL_Control
0x180026227  mov     r14d, 2000h
0x18002622d  cmp     rcx, rdx
0x180026230  jz      short loc_180026261
0x180026232  test    [rcx+1Ch], r14d
0x180026236  jz      short loc_180026261
0x180026238  cmp     byte ptr [rcx+19h], 6
0x18002623c  jb      short loc_180026261
0x18002623e  mov     rcx, [rcx+10h]
0x180026242  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180026249  mov     edx, 384h
0x18002624e  call    WPP_SF_
0x180026253  mov     rcx, cs:WPP_GLOBAL_Control
0x18002625a  lea     rdx, WPP_GLOBAL_Control
0x180026261  mov     r15d, 1
0x180026267  mov     r13d, 202h
0x18002626d  test    rsi, rsi
0x180026270  jnz     short loc_1800262B0
0x180026272  lea     ebx, [r13+65h]
0x180026276  cmp     rcx, rdx
0x180026279  jz      loc_1800268E7
0x18002627f  test    [rcx+1Ch], r14d
0x180026283  jz      loc_1800268E7
0x180026289  cmp     byte ptr [rcx+19h], 2
0x18002628d  jb      loc_1800268E7
0x180026293  mov     edx, 385h
0x180026298  mov     r9d, ebx
0x18002629b  mov     rcx, [rcx+10h]
0x18002629f  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800262a6  call    WPP_SF_d
0x1800262ab  jmp     loc_1800268E0
0x1800262b0  cmp     dword ptr [rsi+1Ch], 2
0x1800262b4  jz      short loc_1800262DF
0x1800262b6  mov     ebx, 26Bh
0x1800262bb  cmp     rcx, rdx
0x1800262be  jz      loc_1800268E7
0x1800262c4  test    [rcx+1Ch], r14d
0x1800262c8  jz      loc_1800268E7
0x1800262ce  cmp     byte ptr [rcx+19h], 2
0x1800262d2  jb      loc_1800268E7
0x1800262d8  mov     edx, 386h
0x1800262dd  jmp     short loc_180026298
0x1800262df  cmp     dword ptr [rsi+550h], 3
0x1800262e6  jnz     short loc_1800262FC
0x1800262e8  mov     rax, [rsi+4F8h]
0x1800262ef  mov     [r12+440h], rax
0x1800262f7  jmp     loc_180026866
0x1800262fc  xorps   xmm0, xmm0
0x1800262ff  lea     rcx, [rbp+7E0h+var_140]; void *
0x180026306  mov     ebx, 101h
0x18002630b  xor     edx, edx; Val
0x18002630d  mov     r8d, ebx; Size
0x180026310  movups  xmmword ptr [rbp+7E0h+MultiByteStr], xmm0
0x180026317  call    memset_0
0x18002631c  mov     r8d, ebx; Size
0x18002631f  lea     rcx, [rbp+7E0h+var_250]; void *
0x180026326  xor     edx, edx; Val
0x180026328  call    memset_0
0x18002632d  mov     [rsp+8E0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180026336  lea     rax, [rbp+7E0h+MultiByteStr]
0x18002633d  mov     [rsp+8E0h+lpDefaultChar], 0; lpDefaultChar
0x180026346  lea     rbx, [r12+41Ch]
0x18002634e  mov     [rsp+8E0h+cbMultiByte], 10h; cbMultiByte
0x180026356  mov     r8, rbx; lpWideCharStr
0x180026359  or      r9d, 0FFFFFFFFh; cchWideChar
0x18002635d  mov     [rsp+8E0h+lpMultiByteStr], rax; lpMultiByteStr
0x180026362  mov     edx, 400h; dwFlags
0x180026367  xor     ecx, ecx; CodePage
0x180026369  call    cs:__imp_WideCharToMultiByte
0x180026370  nop     dword ptr [rax+rax+00h]
0x180026375  test    eax, eax
0x180026377  jnz     short loc_1800263BF
0x180026379  call    cs:__imp_GetLastError
0x180026380  nop     dword ptr [rax+rax+00h]
0x180026385  mov     ebx, eax
0x180026387  mov     rcx, cs:WPP_GLOBAL_Control
0x18002638e  lea     rdx, WPP_GLOBAL_Control
0x180026395  cmp     rcx, rdx
0x180026398  jz      loc_1800268E7
0x18002639e  test    [rcx+1Ch], r14d
0x1800263a2  jz      loc_1800268E7
0x1800263a8  cmp     byte ptr [rcx+19h], 2
0x1800263ac  jb      loc_1800268E7
0x1800263b2  mov     edx, 387h
0x1800263b7  mov     r9d, eax
0x1800263ba  jmp     loc_18002629B
0x1800263bf  movups  xmm0, xmmword ptr [rbp+7E0h+MultiByteStr]
0x1800263c6  mov     [rsp+8E0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800263cf  lea     rax, [rbp+7E0h+var_140]
0x1800263d6  mov     [rsp+8E0h+lpDefaultChar], 0; lpDefaultChar
0x1800263df  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800263e3  movdqu  xmmword ptr [rbx], xmm0
0x1800263e7  lea     rbx, [r12+18h]
0x1800263ec  mov     [rsp+8E0h+cbMultiByte], 101h; cbMultiByte
0x1800263f4  mov     r8, rbx; lpWideCharStr
0x1800263f7  mov     [rsp+8E0h+lpMultiByteStr], rax; lpMultiByteStr
0x1800263fc  mov     edx, 400h; dwFlags
0x180026401  xor     ecx, ecx; CodePage
0x180026403  call    cs:__imp_WideCharToMultiByte
0x18002640a  nop     dword ptr [rax+rax+00h]
0x18002640f  test    eax, eax
0x180026411  jnz     short loc_180026456
0x180026413  call    cs:__imp_GetLastError
0x18002641a  nop     dword ptr [rax+rax+00h]
0x18002641f  mov     ebx, eax
0x180026421  mov     rcx, cs:WPP_GLOBAL_Control
0x180026428  lea     rdx, WPP_GLOBAL_Control
0x18002642f  cmp     rcx, rdx
0x180026432  jz      loc_1800268E7
0x180026438  test    [rcx+1Ch], r14d
0x18002643c  jz      loc_1800268E7
0x180026442  cmp     byte ptr [rcx+19h], 2
0x180026446  jb      loc_1800268E7
0x18002644c  mov     edx, 388h
0x180026451  jmp     loc_1800263B7
0x180026456  mov     ecx, 2
0x18002645b  lea     rax, [rbp+7E0h+var_140]
0x180026462  lea     edx, [rcx+7Eh]
0x180026465  movups  xmm0, xmmword ptr [rax]
0x180026468  movups  xmm1, xmmword ptr [rax+10h]
0x18002646c  movups  xmmword ptr [rbx], xmm0
0x18002646f  movups  xmm0, xmmword ptr [rax+20h]
0x180026473  movups  xmmword ptr [rbx+10h], xmm1
0x180026477  movups  xmm1, xmmword ptr [rax+30h]
0x18002647b  movups  xmmword ptr [rbx+20h], xmm0
0x18002647f  movups  xmm0, xmmword ptr [rax+40h]
0x180026483  movups  xmmword ptr [rbx+30h], xmm1
0x180026487  movups  xmm1, xmmword ptr [rax+50h]
0x18002648b  movups  xmmword ptr [rbx+40h], xmm0
0x18002648f  movups  xmm0, xmmword ptr [rax+60h]
0x180026493  movups  xmmword ptr [rbx+50h], xmm1
0x180026497  movups  xmm1, xmmword ptr [rax+70h]
0x18002649b  add     rax, rdx
0x18002649e  movups  xmmword ptr [rbx+60h], xmm0
0x1800264a2  movups  xmmword ptr [rbx+70h], xmm1
0x1800264a6  add     rbx, rdx
0x1800264a9  sub     rcx, r15; CodePage
0x1800264ac  jnz     short loc_180026465
0x1800264ae  mov     al, [rax]
0x1800264b0  lea     r14, [r12+21Ah]
0x1800264b8  xor     r15d, r15d
0x1800264bb  mov     [rbx], al
0x1800264bd  cmp     [rsi+4E0h], r15
0x1800264c4  jnz     loc_18002666A
0x1800264ca  mov     [rsp+8E0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800264cf  lea     rax, [rbp+7E0h+var_250]
0x1800264d6  mov     [rsp+8E0h+lpDefaultChar], r15; lpDefaultChar
0x1800264db  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800264df  mov     [rsp+8E0h+cbMultiByte], 101h; cbMultiByte
0x1800264e7  mov     r8, r14; lpWideCharStr
0x1800264ea  mov     edx, 400h; dwFlags
0x1800264ef  mov     [rsp+8E0h+lpMultiByteStr], rax; lpMultiByteStr
0x1800264f4  call    cs:__imp_WideCharToMultiByte
0x1800264fb  nop     dword ptr [rax+rax+00h]
0x180026500  test    eax, eax
0x180026502  jnz     short loc_18002655A
0x180026504  call    cs:__imp_GetLastError
0x18002650b  nop     dword ptr [rax+rax+00h]
0x180026510  mov     ebx, eax
0x180026512  mov     rcx, cs:WPP_GLOBAL_Control
0x180026519  lea     rdx, WPP_GLOBAL_Control
0x180026520  cmp     rcx, rdx
0x180026523  jz      loc_1800265C5
0x180026529  test    dword ptr [rcx+1Ch], 2000h
0x180026530  jz      loc_1800265C5
0x180026536  cmp     byte ptr [rcx+19h], 2
0x18002653a  jb      loc_1800265C5
0x180026540  mov     rcx, [rcx+10h]
0x180026544  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18002654b  mov     edx, 389h
0x180026550  mov     r9d, eax
0x180026553  call    WPP_SF_d
0x180026558  jmp     short loc_1800265BE
0x18002655a  mov     edx, 2
0x18002655f  lea     rax, [rbp+7E0h+var_250]
0x180026566  mov     ebx, r15d
0x180026569  mov     rcx, r14
0x18002656c  lea     r8d, [rdx+7Eh]
0x180026570  movups  xmm0, xmmword ptr [rax]
0x180026573  movups  xmm1, xmmword ptr [rax+10h]
0x180026577  movups  xmmword ptr [rcx], xmm0
0x18002657a  movups  xmm0, xmmword ptr [rax+20h]
0x18002657e  movups  xmmword ptr [rcx+10h], xmm1
0x180026582  movups  xmm1, xmmword ptr [rax+30h]
0x180026586  movups  xmmword ptr [rcx+20h], xmm0
0x18002658a  movups  xmm0, xmmword ptr [rax+40h]
0x18002658e  movups  xmmword ptr [rcx+30h], xmm1
0x180026592  movups  xmm1, xmmword ptr [rax+50h]
0x180026596  movups  xmmword ptr [rcx+40h], xmm0
0x18002659a  movups  xmm0, xmmword ptr [rax+60h]
0x18002659e  movups  xmmword ptr [rcx+50h], xmm1
0x1800265a2  movups  xmm1, xmmword ptr [rax+70h]
0x1800265a6  add     rax, r8
0x1800265a9  movups  xmmword ptr [rcx+60h], xmm0
0x1800265ad  movups  xmmword ptr [rcx+70h], xmm1
0x1800265b1  add     rcx, r8
0x1800265b4  sub     rdx, 1
0x1800265b8  jnz     short loc_180026570
0x1800265ba  mov     al, [rax]
0x1800265bc  mov     [rcx], al
0x1800265be  lea     rdx, WPP_GLOBAL_Control
0x1800265c5  mov     ecx, 101h
0x1800265ca  lea     rax, [rbp+7E0h+var_250]
0x1800265d1  mov     [rax], r15b
0x1800265d4  inc     rax
0x1800265d7  sub     rcx, 1
0x1800265db  jnz     short loc_1800265D1
0x1800265dd  lea     r15d, [rcx+1]
0x1800265e1  test    ebx, ebx
0x1800265e3  jnz     loc_1800268E7
0x1800265e9  lea     rdx, Str2; "****************"
0x1800265f0  mov     rcx, r14; Str1
0x1800265f3  call    strcmp_0
0x1800265f8  test    eax, eax
0x1800265fa  jnz     loc_18002685B
0x180026600  xor     r15d, r15d
0x180026603  cmp     cs:g_fInProc, r15d
0x18002660a  jnz     loc_1800266C2
0x180026610  call    cs:__imp_GetCurrentProcessId
0x180026617  nop     dword ptr [rax+rax+00h]
0x18002661c  mov     rdx, r14
0x18002661f  mov     rcx, rsi
0x180026622  mov     r8d, eax
0x180026625  call    DwGetPasswordA
0x18002662a  test    eax, eax
0x18002662c  jz      loc_1800266B7
0x180026632  mov     rcx, cs:WPP_GLOBAL_Control
0x180026639  lea     rdx, WPP_GLOBAL_Control
0x180026640  cmp     rcx, rdx
0x180026643  jz      loc_18002685B
0x180026649  test    dword ptr [rcx+1Ch], 2000h
0x180026650  jz      loc_18002685B
0x180026656  cmp     byte ptr [rcx+19h], 2
0x18002665a  jb      loc_18002685B
0x180026660  mov     edx, 38Bh
0x180026665  jmp     loc_180026848
0x18002666a  mov     rdx, r14
0x18002666d  mov     rcx, rsi
0x180026670  call    DecryptPassword
0x180026675  mov     ebx, eax
0x180026677  test    eax, eax
0x180026679  jz      loc_1800265E9
0x18002667f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026686  lea     rdx, WPP_GLOBAL_Control
0x18002668d  cmp     rcx, rdx
0x180026690  jz      loc_1800268E7
0x180026696  test    dword ptr [rcx+1Ch], 2000h
0x18002669d  jz      loc_1800268E7
0x1800266a3  cmp     byte ptr [rcx+19h], 2
0x1800266a7  jb      loc_1800268E7
0x1800266ad  mov     edx, 38Ah
0x1800266b2  jmp     loc_1800263B7
0x1800266b7  mov     r15d, 1
0x1800266bd  jmp     loc_18002685B
0x1800266c2  xor     edx, edx; Val
0x1800266c4  lea     rcx, [rsp+8E0h+var_890]; void *
0x1800266c9  mov     r8d, 630h; Size
0x1800266cf  call    memset_0
0x1800266d4  lea     rcx, [rsi+438h]
0x1800266db  mov     [rsp+8E0h+var_8A0], 80000002h
0x1800266e3  mov     edx, 9
0x1800266e8  call    GetUserData
0x1800266ed  test    rax, rax
0x1800266f0  jnz     short loc_18002673A
0x1800266f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266f9  lea     rdx, WPP_GLOBAL_Control
0x180026700  cmp     rcx, rdx
0x180026703  jz      loc_18002685B
0x180026709  test    dword ptr [rcx+1Ch], 2000h
0x180026710  jz      loc_18002685B
0x180026716  cmp     byte ptr [rcx+19h], 2
0x18002671a  jb      loc_18002685B
0x180026720  mov     rcx, [rcx+10h]
0x180026724  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18002672b  mov     edx, 38Ch
0x180026730  call    WPP_SF_
0x180026735  jmp     loc_18002685B
0x18002673a  mov     edx, [rax+18h]
0x18002673d  lea     r9, [rsp+8E0h+var_890]
0x180026742  lea     r8, [rsp+8E0h+var_8A0]
0x180026747  mov     dword ptr [rsp+8E0h+lpMultiByteStr], 1
0x18002674f  xor     ecx, ecx
0x180026751  call    GetEntryDialParams
0x180026756  test    eax, eax
0x180026758  jnz     loc_180026821
  ... truncated ...
```
