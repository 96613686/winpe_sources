# ApplyPerConnectionProxySettings

- ea: `0x1800825cc`
- end: `0x180082a7a`
- name: `ApplyPerConnectionProxySettings`
- size: `1198`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180036f2c`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x1800825cc`
- `0x1800b0370`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18008282f`
- `msvcrt!wcscat_s` at `0x18008282f`
- `msvcrt!wcscpy_s` at `0x180082815`
- `msvcrt!wcscpy_s` at `0x180082815`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180082880`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180082880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180082866`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180082866`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800827b6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800827b6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180082a29`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180082a29`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008292d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008292d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800829a6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800829a6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800828e8`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800828e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008288a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800828f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800829b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008288a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800828f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800829b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800829f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082a0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800829f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082a0c`

## pseudocode

```c
__int64 __fastcall ApplyPerConnectionProxySettings(__int64 a1)
{
  _QWORD *v2; // r10
  wchar_t *v3; // r15
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // r8d
  unsigned int v9; // edi
  unsigned __int16 *v10; // r14
  __int64 v11; // rdx
  unsigned __int16 *v12; // rbp
  unsigned __int16 *v13; // rbx
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  rsize_t v17; // rbx
  wchar_t *v18; // rax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v21; // eax
  void *TokenHandle; // [rsp+80h] [rbp+8h] BYREF
  void *DuplicateTokenHandle; // [rsp+88h] [rbp+10h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  DuplicateTokenHandle = 0;
  v3 = 0;
  TokenHandle = 0;
  if ( a1 )
  {
    v7 = *(_QWORD *)(a1 + 1584);
    v8 = *(_DWORD *)(v7 + 560);
    if ( !v8 && !*(_DWORD *)(v7 + 820) )
    {
      if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x800) != 0 && *((_BYTE *)v2 + 25) >= 5u )
      {
        WPP_SF_(v2[2], 330, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        v2 = WPP_GLOBAL_Control;
      }
      v4 = 0;
      goto LABEL_69;
    }
    v4 = 0;
    v9 = (v8 == 0) | 8;
    if ( (v8 & 1) == 0 )
      v9 = v8 == 0;
    if ( (v8 & 2) != 0 )
    {
      v10 = *(unsigned __int16 **)(v7 + 576);
      if ( !v10 )
      {
        if ( v2 == &WPP_GLOBAL_Control )
          return v4;
        if ( (*((_DWORD *)v2 + 7) & 0x800) == 0 || *((_BYTE *)v2 + 25) < 5u )
          goto LABEL_81;
        v11 = 331;
LABEL_26:
        WPP_SF_(v2[2], v11, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        goto LABEL_68;
      }
      v9 |= 3u;
    }
    else
    {
      v10 = 0;
    }
    v12 = 0;
    if ( (v8 & 4) != 0 )
    {
      v12 = *(unsigned __int16 **)(v7 + 568);
      if ( !v12 )
      {
        if ( v2 == &WPP_GLOBAL_Control )
          return v4;
        if ( (*((_DWORD *)v2 + 7) & 0x800) == 0 || *((_BYTE *)v2 + 25) < 5u )
          goto LABEL_81;
        v11 = 332;
        goto LABEL_26;
      }
      v9 |= 4u;
    }
    v13 = *(unsigned __int16 **)(v7 + 584);
    v14 = *(_DWORD *)(v7 + 592);
    if ( v13 )
    {
      if ( v14 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v13[v15] );
        v16 = (unsigned int)(v15 + 10);
        v17 = (unsigned int)v16;
        v18 = (wchar_t *)GlobalAlloc(0x40u, 2 * v16);
        v3 = v18;
        if ( !v18 )
        {
          v6 = 8;
          v4 = 8;
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_69;
          }
          v5 = 333;
          goto LABEL_10;
        }
        wcscpy_s(v18, v17, L"<local>;");
        wcscat_s(v3, v17, *(const wchar_t **)(*(_QWORD *)(a1 + 1584) + 584LL));
        v13 = v3;
      }
    }
    else
    {
      v13 = (unsigned __int16 *)((unsigned __int64)L"<local>" & -(__int64)(v14 != 0));
    }
    if ( *(_DWORD *)(a1 + 5620) && NtCurrentTeb()->IsImpersonating )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 6u, 1, &TokenHandle) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( !LastError )
          goto LABEL_68;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_69;
        }
        v5 = 334;
        goto LABEL_55;
      }
      if ( !DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( !LastError )
          goto LABEL_68;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_69;
        }
        v5 = 335;
        goto LABEL_55;
      }
      RevertToSelf();
    }
    LastError = RasSetPerConnectionProxy((unsigned __int16 *)(a1 + 1604), v10, v13, v12, v9, 0, *(_DWORD *)(a1 + 5620));
    v4 = LastError;
    if ( !LastError )
      goto LABEL_68;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v5 = 336;
LABEL_55:
    v6 = LastError;
    goto LABEL_10;
  }
  v4 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_DWORD *)v2 + 7) & 0x800) != 0 && *((_BYTE *)v2 + 25) >= 2u )
  {
    v5 = 329;
    v6 = 87;
LABEL_10:
    WPP_SF_d(v2[2], v5, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v6);
LABEL_68:
    v2 = WPP_GLOBAL_Control;
LABEL_69:
    if ( DuplicateTokenHandle )
    {
      if ( !ImpersonateLoggedOnUser(DuplicateTokenHandle) )
      {
        v21 = GetLastError();
        if ( v21 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 337, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v21);
          }
        }
      }
      CloseHandle(DuplicateTokenHandle);
      v2 = WPP_GLOBAL_Control;
    }
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      v2 = WPP_GLOBAL_Control;
      TokenHandle = 0;
    }
    if ( v3 )
    {
      GlobalFree(v3);
      v2 = WPP_GLOBAL_Control;
    }
  }
LABEL_81:
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x800) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 338, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800825cc  mov     [rsp+arg_10], rbx
0x1800825d1  push    rbp
0x1800825d2  push    rsi
0x1800825d3  push    rdi
0x1800825d4  push    r12
0x1800825d6  push    r13
0x1800825d8  push    r14
0x1800825da  push    r15
0x1800825dc  sub     rsp, 40h
0x1800825e0  mov     rsi, rcx
0x1800825e3  mov     r10, cs:WPP_GLOBAL_Control
0x1800825ea  lea     rbp, WPP_GLOBAL_Control
0x1800825f1  lea     r11, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800825f8  mov     r13d, 800h
0x1800825fe  cmp     r10, rbp
0x180082601  jz      short loc_18008262F
0x180082603  test    [r10+1Ch], r13d
0x180082607  jz      short loc_18008262F
0x180082609  cmp     byte ptr [r10+19h], 6
0x18008260e  jb      short loc_18008262F
0x180082610  mov     rcx, [r10+10h]
0x180082614  mov     edx, 148h
0x180082619  mov     r8, r11
0x18008261c  call    WPP_SF_
0x180082621  mov     r10, cs:WPP_GLOBAL_Control
0x180082628  lea     r11, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008262f  xor     r12d, r12d
0x180082632  mov     [rsp+78h+DuplicateTokenHandle], r12
0x18008263a  mov     r15d, r12d
0x18008263d  mov     [rsp+78h+TokenHandle], r12
0x180082645  test    rsi, rsi
0x180082648  jnz     short loc_180082684
0x18008264a  lea     ebx, [rsi+57h]
0x18008264d  cmp     r10, rbp
0x180082650  jz      loc_180082A60
0x180082656  test    [r10+1Ch], r13d
0x18008265a  jz      loc_180082A36
0x180082660  cmp     byte ptr [r10+19h], 2
0x180082665  jb      loc_180082A36
0x18008266b  mov     edx, 149h
0x180082670  mov     r9d, ebx
0x180082673  mov     r8, r11
0x180082676  mov     rcx, [r10+10h]
0x18008267a  call    WPP_SF_d
0x18008267f  jmp     loc_180082992
0x180082684  mov     rdx, [rsi+630h]
0x18008268b  mov     r8d, [rdx+230h]
0x180082692  test    r8d, r8d
0x180082695  jnz     short loc_1800826D2
0x180082697  cmp     [rdx+334h], r12d
0x18008269e  jnz     short loc_1800826D2
0x1800826a0  cmp     r10, rbp
0x1800826a3  jz      short loc_1800826CA
0x1800826a5  test    [r10+1Ch], r13d
0x1800826a9  jz      short loc_1800826CA
0x1800826ab  cmp     byte ptr [r10+19h], 5
0x1800826b0  jb      short loc_1800826CA
0x1800826b2  mov     rcx, [r10+10h]
0x1800826b6  mov     edx, 14Ah
0x1800826bb  mov     r8, r11
0x1800826be  call    WPP_SF_
0x1800826c3  mov     r10, cs:WPP_GLOBAL_Control
0x1800826ca  mov     ebx, r12d
0x1800826cd  jmp     loc_180082999
0x1800826d2  test    r8d, r8d
0x1800826d5  mov     ecx, r12d
0x1800826d8  mov     ebx, r12d
0x1800826db  setz    cl
0x1800826de  mov     edi, ecx
0x1800826e0  or      edi, 8
0x1800826e3  test    r8b, 1
0x1800826e7  cmovz   edi, ecx
0x1800826ea  test    r8b, 2
0x1800826ee  jz      short loc_180082735
0x1800826f0  mov     r14, [rdx+240h]
0x1800826f7  test    r14, r14
0x1800826fa  jnz     short loc_180082730
0x1800826fc  cmp     r10, rbp
0x1800826ff  jz      loc_180082A60
0x180082705  test    [r10+1Ch], r13d
0x180082709  jz      loc_180082A36
0x18008270f  cmp     byte ptr [r10+19h], 5
0x180082714  jb      loc_180082A36
0x18008271a  mov     edx, 14Bh
0x18008271f  mov     rcx, [r10+10h]
0x180082723  mov     r8, r11
0x180082726  call    WPP_SF_
0x18008272b  jmp     loc_180082992
0x180082730  or      edi, 3
0x180082733  jmp     short loc_180082738
0x180082735  mov     r14, r12
0x180082738  mov     rbp, r12
0x18008273b  test    r8b, 4
0x18008273f  jz      short loc_18008277C
0x180082741  mov     rbp, [rdx+238h]
0x180082748  test    rbp, rbp
0x18008274b  jnz     short loc_180082779
0x18008274d  lea     rbp, WPP_GLOBAL_Control
0x180082754  cmp     r10, rbp
0x180082757  jz      loc_180082A60
0x18008275d  test    [r10+1Ch], r13d
0x180082761  jz      loc_180082A36
0x180082767  cmp     byte ptr [r10+19h], 5
0x18008276c  jb      loc_180082A36
0x180082772  mov     edx, 14Ch
0x180082777  jmp     short loc_18008271F
0x180082779  or      edi, 4
0x18008277c  mov     rbx, [rdx+248h]
0x180082783  mov     eax, [rdx+250h]
0x180082789  test    rbx, rbx
0x18008278c  jz      loc_18008283A
0x180082792  test    eax, eax
0x180082794  jz      loc_180082849
0x18008279a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008279e  inc     rax
0x1800827a1  cmp     [rbx+rax*2], r12w
0x1800827a6  jnz     short loc_18008279E
0x1800827a8  add     eax, 0Ah
0x1800827ab  mov     ecx, 40h ; '@'; uFlags
0x1800827b0  mov     ebx, eax
0x1800827b2  lea     rdx, [rax+rax]; dwBytes
0x1800827b6  call    cs:__imp_GlobalAlloc
0x1800827bc  mov     r15, rax
0x1800827bf  test    rax, rax
0x1800827c2  jnz     short loc_180082808
0x1800827c4  lea     r9d, [rax+8]
0x1800827c8  mov     ebx, r9d
0x1800827cb  mov     r10, cs:WPP_GLOBAL_Control
0x1800827d2  lea     rbp, WPP_GLOBAL_Control
0x1800827d9  cmp     r10, rbp
0x1800827dc  jz      loc_180082999
0x1800827e2  test    [r10+1Ch], r13d
0x1800827e6  jz      loc_180082999
0x1800827ec  cmp     byte ptr [r10+19h], 2
0x1800827f1  jb      loc_180082999
0x1800827f7  mov     edx, 14Dh
0x1800827fc  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180082803  jmp     loc_180082676
0x180082808  lea     r8, aLocal; "<local>;"
0x18008280f  mov     rdx, rbx; SizeInWords
0x180082812  mov     rcx, r15; Destination
0x180082815  call    cs:__imp_wcscpy_s
0x18008281b  mov     r8, [rsi+630h]
0x180082822  mov     rdx, rbx; SizeInWords
0x180082825  mov     rcx, r15; Destination
0x180082828  mov     r8, [r8+248h]; Source
0x18008282f  call    cs:__imp_wcscat_s
0x180082835  mov     rbx, r15
0x180082838  jmp     short loc_180082849
0x18008283a  neg     eax
0x18008283c  lea     rax, aLocal_0; "<local>"
0x180082843  sbb     rbx, rbx
0x180082846  and     rbx, rax
0x180082849  cmp     [rsi+15F4h], r12d
0x180082850  jz      loc_180082933
0x180082856  mov     eax, gs:179Ch
0x18008285e  test    eax, eax
0x180082860  jz      loc_180082933
0x180082866  call    cs:__imp_GetCurrentThread
0x18008286c  mov     edx, 6; DesiredAccess
0x180082871  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180082879  mov     rcx, rax; ThreadHandle
0x18008287c  lea     r8d, [rdx-5]; OpenAsSelf
0x180082880  call    cs:__imp_OpenThreadToken
0x180082886  test    eax, eax
0x180082888  jnz     short loc_1800828D3
0x18008288a  call    cs:__imp_GetLastError
0x180082890  mov     ebx, eax
0x180082892  test    eax, eax
0x180082894  jz      loc_18008298B
0x18008289a  mov     r10, cs:WPP_GLOBAL_Control
0x1800828a1  lea     rbp, WPP_GLOBAL_Control
0x1800828a8  cmp     r10, rbp
0x1800828ab  jz      loc_180082999
0x1800828b1  test    [r10+1Ch], r13d
0x1800828b5  jz      loc_180082999
0x1800828bb  cmp     byte ptr [r10+19h], 2
0x1800828c0  jb      loc_180082999
0x1800828c6  mov     edx, 14Eh
0x1800828cb  mov     r9d, eax
0x1800828ce  jmp     loc_1800827FC
0x1800828d3  mov     rcx, [rsp+78h+TokenHandle]; ExistingTokenHandle
0x1800828db  lea     r8, [rsp+78h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800828e3  mov     edx, 2; ImpersonationLevel
0x1800828e8  call    cs:__imp_DuplicateToken
0x1800828ee  test    eax, eax
0x1800828f0  jnz     short loc_18008292D
0x1800828f2  call    cs:__imp_GetLastError
0x1800828f8  mov     ebx, eax
0x1800828fa  test    eax, eax
0x1800828fc  jz      loc_18008298B
0x180082902  mov     r10, cs:WPP_GLOBAL_Control
0x180082909  lea     rbp, WPP_GLOBAL_Control
0x180082910  cmp     r10, rbp
0x180082913  jz      loc_180082999
0x180082919  test    [r10+1Ch], r13d
0x18008291d  jz      short loc_180082999
0x18008291f  cmp     byte ptr [r10+19h], 2
0x180082924  jb      short loc_180082999
0x180082926  mov     edx, 14Fh
0x18008292b  jmp     short loc_1800828CB
0x18008292d  call    cs:__imp_RevertToSelf
0x180082933  mov     eax, [rsi+15F4h]
0x180082939  lea     rcx, [rsi+644h]; unsigned __int16 *
0x180082940  mov     [rsp+78h+SessionId], eax; SessionId
0x180082944  mov     r9, rbp; unsigned __int16 *
0x180082947  mov     [rsp+78h+var_50], r12d; unsigned int
0x18008294c  mov     r8, rbx; unsigned __int16 *
0x18008294f  mov     rdx, r14; unsigned __int16 *
0x180082952  mov     [rsp+78h+var_58], edi; unsigned int
0x180082956  call    RasSetPerConnectionProxy
0x18008295b  mov     ebx, eax
0x18008295d  test    eax, eax
0x18008295f  jz      short loc_18008298B
0x180082961  mov     r10, cs:WPP_GLOBAL_Control
0x180082968  lea     rbp, WPP_GLOBAL_Control
0x18008296f  cmp     r10, rbp
0x180082972  jz      short loc_180082999
0x180082974  test    [r10+1Ch], r13d
0x180082978  jz      short loc_180082999
0x18008297a  cmp     byte ptr [r10+19h], 2
0x18008297f  jb      short loc_180082999
0x180082981  mov     edx, 150h
0x180082986  jmp     loc_1800828CB
0x18008298b  lea     rbp, WPP_GLOBAL_Control
0x180082992  mov     r10, cs:WPP_GLOBAL_Control
0x180082999  mov     rcx, [rsp+78h+DuplicateTokenHandle]; hToken
0x1800829a1  test    rcx, rcx
0x1800829a4  jz      short loc_1800829FF
0x1800829a6  call    cs:__imp_ImpersonateLoggedOnUser
0x1800829ac  test    eax, eax
0x1800829ae  jnz     short loc_1800829EA
0x1800829b0  call    cs:__imp_GetLastError
0x1800829b6  test    eax, eax
0x1800829b8  jz      short loc_1800829EA
0x1800829ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800829c1  cmp     rcx, rbp
0x1800829c4  jz      short loc_1800829EA
0x1800829c6  test    [rcx+1Ch], r13d
0x1800829ca  jz      short loc_1800829EA
0x1800829cc  cmp     byte ptr [rcx+19h], 2
0x1800829d0  jb      short loc_1800829EA
0x1800829d2  mov     rcx, [rcx+10h]
0x1800829d6  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800829dd  mov     edx, 151h
0x1800829e2  mov     r9d, eax
0x1800829e5  call    WPP_SF_d
0x1800829ea  mov     rcx, [rsp+78h+DuplicateTokenHandle]; hObject
0x1800829f2  call    cs:__imp_CloseHandle
0x1800829f8  mov     r10, cs:WPP_GLOBAL_Control
0x1800829ff  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x180082a07  test    rcx, rcx
0x180082a0a  jz      short loc_180082A21
0x180082a0c  call    cs:__imp_CloseHandle
0x180082a12  mov     r10, cs:WPP_GLOBAL_Control
0x180082a19  mov     [rsp+78h+TokenHandle], r12
0x180082a21  test    r15, r15
0x180082a24  jz      short loc_180082A36
0x180082a26  mov     rcx, r15; hMem
0x180082a29  call    cs:__imp_GlobalFree
0x180082a2f  mov     r10, cs:WPP_GLOBAL_Control
0x180082a36  cmp     r10, rbp
0x180082a39  jz      short loc_180082A60
0x180082a3b  test    [r10+1Ch], r13d
0x180082a3f  jz      short loc_180082A60
0x180082a41  cmp     byte ptr [r10+19h], 6
0x180082a46  jb      short loc_180082A60
0x180082a48  mov     rcx, [r10+10h]
0x180082a4c  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180082a53  mov     edx, 152h
0x180082a58  mov     r9d, ebx
0x180082a5b  call    WPP_SF_d
0x180082a60  mov     eax, ebx
0x180082a62  mov     rbx, [rsp+78h+arg_10]
0x180082a6a  add     rsp, 40h
0x180082a6e  pop     r15
0x180082a70  pop     r14
0x180082a72  pop     r13
0x180082a74  pop     r12
0x180082a76  pop     rdi
0x180082a77  pop     rsi
0x180082a78  pop     rbp
0x180082a79  retn
```
