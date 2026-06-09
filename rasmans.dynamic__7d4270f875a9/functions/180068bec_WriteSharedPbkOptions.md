# WriteSharedPbkOptions

- ea: `0x180068bec`
- end: `0x180069076`
- name: `WriteSharedPbkOptions`
- size: `1162`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, LPCCH, HANDLE hToken)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800482c0`

## callees

- `0x180005bfc`
- `0x180005cf8`
- `0x18005ef68`
- `0x180060fa8`
- `0x180066fc0`
- `0x180068800`
- `0x180068b34`
- `0x180068bec`
- `0x18006a4bc`
- `0x18006d1f0`
- `0x180080430`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ff6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180068e87`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180068e87`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180068fe6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180068fe6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180068fa3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180068fa3`

## pseudocode

```c
__int64 __fastcall WriteSharedPbkOptions(LPCCH lpMultiByteStr, LPCCH a2, HANDLE hToken, __int64 a4)
{
  struct _LIST_ENTRY *v8; // rbx
  __int64 v9; // rcx
  LPCCH v10; // rax
  __int64 v12; // rcx
  LPCCH v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rsi
  struct _LIST_ENTRY *v16; // rcx
  unsigned int updated; // ebx
  __int64 v18; // rdx
  DWORD LastError; // eax
  struct _LIST_ENTRY *v20; // rcx
  __int64 v21; // rdx
  unsigned int PbkAndEntryName; // eax
  struct _LIST_ENTRY *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  HGLOBAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v28[3]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h]
  WCHAR v30[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[524]; // [rsp+84h] [rbp-7Ch] BYREF
  WCHAR WideCharStr[2]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v33[524]; // [rsp+294h] [rbp+194h] BYREF

  if ( lpMultiByteStr && a2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_ssq(
        WPP_GLOBAL_Control[1].Flink,
        (_DWORD)a2,
        (_DWORD)hToken,
        (_DWORD)lpMultiByteStr,
        (__int64)a2,
        (char)hToken);
LABEL_11:
      v8 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 25, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, hToken);
      goto LABEL_11;
    }
  }
  v29 = 0;
  memset(v28, 0, sizeof(v28));
  v27 = 0;
  *(_DWORD *)WideCharStr = 0;
  memset_0(v33, 0, 0x204u);
  *(_DWORD *)v30 = 0;
  memset_0(v31, 0, 0x1FEu);
  hMem = 0;
  if ( !lpMultiByteStr )
  {
LABEL_23:
    if ( !a2 )
      goto LABEL_27;
    v12 = 1537;
    v13 = a2;
    while ( *v13 )
    {
      ++v13;
      if ( !--v12 )
        goto LABEL_27;
    }
    if ( !*a2 )
    {
LABEL_27:
      if ( v8 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v8[1].Blink) & 0x1000) == 0
        || BYTE1(v8[1].Blink) < 2u )
      {
        return 87;
      }
      v14 = 27;
LABEL_31:
      WPP_SF_d(v8[1].Flink, v14, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, 87);
      return 87;
    }
    if ( !a4 )
    {
      if ( v8 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v8[1].Blink) & 0x1000) == 0
        || BYTE1(v8[1].Blink) < 2u )
      {
        return 87;
      }
      v14 = 28;
      goto LABEL_31;
    }
    if ( lpMultiByteStr )
      StrncpyAtoW(WideCharStr, lpMultiByteStr);
    StrncpyAtoW(v30, a2);
    v15 = -(__int64)lpMultiByteStr;
    if ( !(unsigned int)IsExistingEntry((unsigned __int64)WideCharStr & -(__int64)(v15 != 0), v30) )
    {
      v16 = WPP_GLOBAL_Control;
      updated = 623;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        return updated;
      }
      v18 = 29;
LABEL_46:
      WPP_SF_d(v16[1].Flink, v18, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, updated);
      return updated;
    }
    RasUpdatePbkIpv6Info((unsigned __int64)WideCharStr & -(__int64)(v15 != 0), v30, a4);
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastError = GetLastError();
      updated = LastError;
      if ( !LastError )
        goto LABEL_80;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_80;
      }
      v21 = 30;
LABEL_79:
      WPP_SF_d(v20[1].Flink, v21, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, LastError);
LABEL_80:
      ClosePhonebookFile(v28);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
      {
        return updated;
      }
      v18 = 35;
      goto LABEL_46;
    }
    PbkAndEntryName = GetPbkAndEntryName(WideCharStr, (__int64)&v27);
    updated = PbkAndEntryName;
    if ( PbkAndEntryName )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_73;
      }
      v24 = 31;
    }
    else
    {
      if ( DWORD2(v28[0]) || (unsigned int)FIsUserAdminOrNCO() )
        goto LABEL_73;
      PbkAndEntryName = GetLUAPhonebookPath(WideCharStr, (__int64 *)&hMem);
      updated = PbkAndEntryName;
      if ( !PbkAndEntryName )
      {
        updated = RasUpdatePbkIpv6Info(hMem, v30, a4);
        GlobalFree(hMem);
        if ( !updated )
          goto LABEL_73;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_73;
        }
        v24 = 33;
        v25 = updated;
        goto LABEL_72;
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_73;
      }
      v24 = 32;
    }
    v25 = PbkAndEntryName;
LABEL_72:
    WPP_SF_d(v23[1].Flink, v24, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v25);
LABEL_73:
    if ( RevertToSelf() )
      goto LABEL_80;
    LastError = GetLastError();
    updated = LastError;
    if ( !LastError )
      goto LABEL_80;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_80;
    }
    v21 = 34;
    goto LABEL_79;
  }
  v9 = 261;
  v10 = lpMultiByteStr;
  while ( *v10 )
  {
    ++v10;
    if ( !--v9 )
      goto LABEL_18;
  }
  if ( *lpMultiByteStr )
    goto LABEL_23;
LABEL_18:
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v8[1].Blink) & 0x1000) != 0
    && BYTE1(v8[1].Blink) >= 2u )
  {
    WPP_SF_d(v8[1].Flink, 26, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, 621);
  }
  return 621;
}

```

## disassembly

```asm
0x180068bec  push    rbp
0x180068bee  push    rbx
0x180068bef  push    rsi
0x180068bf0  push    rdi
0x180068bf1  push    r12
0x180068bf3  push    r14
0x180068bf5  push    r15
0x180068bf7  lea     rbp, [rsp-3B0h]
0x180068bff  sub     rsp, 4B0h
0x180068c06  mov     rax, cs:__security_cookie
0x180068c0d  xor     rax, rsp
0x180068c10  mov     [rbp+3E0h+var_40], rax
0x180068c17  mov     r12, r9
0x180068c1a  mov     r15, r8
0x180068c1d  mov     r14, rdx
0x180068c20  mov     rsi, rcx
0x180068c23  mov     eax, 1000h
0x180068c28  test    rcx, rcx
0x180068c2b  jz      short loc_180068C68
0x180068c2d  test    rdx, rdx
0x180068c30  jz      short loc_180068C68
0x180068c32  mov     rbx, cs:WPP_GLOBAL_Control
0x180068c39  lea     rdi, WPP_GLOBAL_Control
0x180068c40  cmp     rbx, rdi
0x180068c43  jz      short loc_180068CA5
0x180068c45  test    [rbx+1Ch], eax
0x180068c48  jz      short loc_180068CA5
0x180068c4a  cmp     byte ptr [rbx+19h], 6
0x180068c4e  jb      short loc_180068CA5
0x180068c50  mov     r9, rcx
0x180068c53  mov     [rsp+4E0h+var_4B8], r8
0x180068c58  mov     rcx, [rbx+10h]
0x180068c5c  mov     [rsp+4E0h+var_4C0], rdx
0x180068c61  call    WPP_SF_ssq
0x180068c66  jmp     short loc_180068C9E
0x180068c68  mov     rbx, cs:WPP_GLOBAL_Control
0x180068c6f  lea     rdi, WPP_GLOBAL_Control
0x180068c76  cmp     rbx, rdi
0x180068c79  jz      short loc_180068CA5
0x180068c7b  test    [rbx+1Ch], eax
0x180068c7e  jz      short loc_180068CA5
0x180068c80  cmp     byte ptr [rbx+19h], 6
0x180068c84  jb      short loc_180068CA5
0x180068c86  mov     rcx, [rbx+10h]
0x180068c8a  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180068c91  mov     edx, 19h
0x180068c96  mov     r9, r15
0x180068c99  call    WPP_SF_q
0x180068c9e  mov     rbx, cs:WPP_GLOBAL_Control
0x180068ca5  xorps   xmm0, xmm0
0x180068ca8  lea     rcx, [rbp+3E0h+var_24C]; void *
0x180068caf  xor     eax, eax
0x180068cb1  xor     edx, edx; Val
0x180068cb3  mov     r8d, 204h; Size
0x180068cb9  mov     [rsp+4E0h+var_470], rax
0x180068cbe  movups  [rsp+4E0h+var_4A0], xmm0
0x180068cc3  mov     [rsp+4E0h+var_4A8], rax
0x180068cc8  movups  [rsp+4E0h+var_490], xmm0
0x180068ccd  mov     dword ptr [rbp+3E0h+WideCharStr], eax
0x180068cd3  movups  [rsp+4E0h+var_480], xmm0
0x180068cd8  call    memset_0
0x180068cdd  xor     edx, edx; Val
0x180068cdf  mov     dword ptr [rbp+3E0h+var_460], 0
0x180068ce6  mov     r8d, 1FEh; Size
0x180068cec  lea     rcx, [rbp+3E0h+var_45C]; void *
0x180068cf0  call    memset_0
0x180068cf5  mov     [rsp+4E0h+hMem], 0
0x180068cfe  test    rsi, rsi
0x180068d01  jz      short loc_180068D55
0x180068d03  mov     ecx, 105h
0x180068d08  mov     rax, rsi
0x180068d0b  cmp     byte ptr [rax], 0
0x180068d0e  jz      short loc_180068D1B
0x180068d10  inc     rax
0x180068d13  sub     rcx, 1
0x180068d17  jnz     short loc_180068D0B
0x180068d19  jmp     short loc_180068D20
0x180068d1b  cmp     byte ptr [rsi], 0
0x180068d1e  jnz     short loc_180068D55
0x180068d20  mov     esi, 26Dh
0x180068d25  cmp     rbx, rdi
0x180068d28  jz      short loc_180068D51
0x180068d2a  test    dword ptr [rbx+1Ch], 1000h
0x180068d31  jz      short loc_180068D51
0x180068d33  cmp     byte ptr [rbx+19h], 2
0x180068d37  jb      short loc_180068D51
0x180068d39  mov     rcx, [rbx+10h]
0x180068d3d  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180068d44  mov     edx, 1Ah
0x180068d49  mov     r9d, esi
0x180068d4c  call    WPP_SF_d
0x180068d51  mov     eax, esi
0x180068d53  jmp     short loc_180068DA4
0x180068d55  test    r14, r14
0x180068d58  jz      short loc_180068D70
0x180068d5a  mov     ecx, 601h
0x180068d5f  mov     rax, r14
0x180068d62  cmp     byte ptr [rax], 0
0x180068d65  jz      short loc_180068DC6
0x180068d67  inc     rax
0x180068d6a  sub     rcx, 1
0x180068d6e  jnz     short loc_180068D62
0x180068d70  cmp     rbx, rdi
0x180068d73  jz      short loc_180068D9F
0x180068d75  test    dword ptr [rbx+1Ch], 1000h
0x180068d7c  jz      short loc_180068D9F
0x180068d7e  cmp     byte ptr [rbx+19h], 2
0x180068d82  jb      short loc_180068D9F
0x180068d84  mov     edx, 1Bh
0x180068d89  mov     rcx, [rbx+10h]
0x180068d8d  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180068d94  mov     r9d, 57h ; 'W'
0x180068d9a  call    WPP_SF_d
0x180068d9f  mov     eax, 57h ; 'W'
0x180068da4  mov     rcx, [rbp+3E0h+var_40]
0x180068dab  xor     rcx, rsp; StackCookie
0x180068dae  call    __security_check_cookie
0x180068db3  add     rsp, 4B0h
0x180068dba  pop     r15
0x180068dbc  pop     r14
0x180068dbe  pop     r12
0x180068dc0  pop     rdi
0x180068dc1  pop     rsi
0x180068dc2  pop     rbx
0x180068dc3  pop     rbp
0x180068dc4  retn
0x180068dc6  cmp     byte ptr [r14], 0
0x180068dca  jz      short loc_180068D70
0x180068dcc  test    r12, r12
0x180068dcf  jnz     short loc_180068DEC
0x180068dd1  cmp     rbx, rdi
0x180068dd4  jz      short loc_180068D9F
0x180068dd6  test    dword ptr [rbx+1Ch], 1000h
0x180068ddd  jz      short loc_180068D9F
0x180068ddf  cmp     byte ptr [rbx+19h], 2
0x180068de3  jb      short loc_180068D9F
0x180068de5  lea     edx, [r12+1Ch]
0x180068dea  jmp     short loc_180068D89
0x180068dec  test    rsi, rsi
0x180068def  jz      short loc_180068E06
0x180068df1  mov     r8d, 104h
0x180068df7  lea     rcx, [rbp+3E0h+WideCharStr]; lpWideCharStr
0x180068dfe  mov     rdx, rsi; lpMultiByteStr
0x180068e01  call    StrncpyAtoW
0x180068e06  mov     r8d, 101h
0x180068e0c  lea     rcx, [rbp+3E0h+var_460]; lpWideCharStr
0x180068e10  mov     rdx, r14; lpMultiByteStr
0x180068e13  call    StrncpyAtoW
0x180068e18  lea     rax, [rbp+3E0h+WideCharStr]
0x180068e1f  neg     rsi
0x180068e22  lea     rdx, [rbp+3E0h+var_460]
0x180068e26  sbb     rbx, rbx
0x180068e29  and     rbx, rax
0x180068e2c  mov     rcx, rbx
0x180068e2f  call    IsExistingEntry
0x180068e34  test    eax, eax
0x180068e36  jnz     short loc_180068E75
0x180068e38  mov     rcx, cs:WPP_GLOBAL_Control
0x180068e3f  mov     ebx, 26Fh
0x180068e44  cmp     rcx, rdi
0x180068e47  jz      short loc_180068E6E
0x180068e49  test    dword ptr [rcx+1Ch], 1000h
0x180068e50  jz      short loc_180068E6E
0x180068e52  cmp     byte ptr [rcx+19h], 2
0x180068e56  jb      short loc_180068E6E
0x180068e58  lea     edx, [rax+1Dh]
0x180068e5b  mov     rcx, [rcx+10h]
0x180068e5f  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180068e66  mov     r9d, ebx
0x180068e69  call    WPP_SF_d
0x180068e6e  mov     eax, ebx
0x180068e70  jmp     loc_180068DA4
0x180068e75  mov     r8, r12
0x180068e78  lea     rdx, [rbp+3E0h+var_460]
0x180068e7c  mov     rcx, rbx
0x180068e7f  call    RasUpdatePbkIpv6Info
0x180068e84  mov     rcx, r15; hToken
0x180068e87  call    cs:__imp_ImpersonateLoggedOnUser
0x180068e8e  nop     dword ptr [rax+rax+00h]
0x180068e93  test    eax, eax
0x180068e95  jnz     short loc_180068EDE
0x180068e97  call    cs:__imp_GetLastError
0x180068e9e  nop     dword ptr [rax+rax+00h]
0x180068ea3  mov     ebx, eax
0x180068ea5  test    eax, eax
0x180068ea7  jz      loc_18006903B
0x180068ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180068eb4  cmp     rcx, rdi
0x180068eb7  jz      loc_18006903B
0x180068ebd  test    dword ptr [rcx+1Ch], 1000h
0x180068ec4  jz      loc_18006903B
0x180068eca  cmp     byte ptr [rcx+19h], 2
0x180068ece  jb      loc_18006903B
0x180068ed4  mov     edx, 1Eh
0x180068ed9  jmp     loc_180069028
0x180068ede  lea     rax, [rsp+4E0h+var_4A8]
0x180068ee3  xor     r8d, r8d
0x180068ee6  lea     r9, [rsp+4E0h+var_4A0]
0x180068eeb  mov     [rsp+4E0h+var_4C0], rax
0x180068ef0  lea     rdx, [rbp+3E0h+var_460]
0x180068ef4  lea     rcx, [rbp+3E0h+WideCharStr]
0x180068efb  call    GetPbkAndEntryName
0x180068f00  mov     ebx, eax
0x180068f02  test    eax, eax
0x180068f04  jz      short loc_180068F3A
0x180068f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180068f0d  cmp     rcx, rdi
0x180068f10  jz      loc_180068FE6
0x180068f16  test    dword ptr [rcx+1Ch], 1000h
0x180068f1d  jz      loc_180068FE6
0x180068f23  cmp     byte ptr [rcx+19h], 2
0x180068f27  jb      loc_180068FE6
0x180068f2d  mov     edx, 1Fh
0x180068f32  mov     r9d, eax
0x180068f35  jmp     loc_180068FD6
0x180068f3a  cmp     dword ptr [rsp+4E0h+var_4A0+8], 0
0x180068f3f  jnz     loc_180068FE6
0x180068f45  call    FIsUserAdminOrNCO
0x180068f4a  test    eax, eax
0x180068f4c  jnz     loc_180068FE6
0x180068f52  lea     rdx, [rsp+4E0h+hMem]
0x180068f57  lea     rcx, [rbp+3E0h+WideCharStr]; lpFileName
0x180068f5e  call    GetLUAPhonebookPath
0x180068f63  mov     ebx, eax
0x180068f65  test    eax, eax
0x180068f67  jz      short loc_180068F8B
0x180068f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180068f70  cmp     rcx, rdi
0x180068f73  jz      short loc_180068FE6
0x180068f75  test    dword ptr [rcx+1Ch], 1000h
0x180068f7c  jz      short loc_180068FE6
0x180068f7e  cmp     byte ptr [rcx+19h], 2
0x180068f82  jb      short loc_180068FE6
0x180068f84  mov     edx, 20h ; ' '
0x180068f89  jmp     short loc_180068F32
0x180068f8b  mov     rcx, [rsp+4E0h+hMem]
0x180068f90  lea     rdx, [rbp+3E0h+var_460]
0x180068f94  mov     r8, r12
0x180068f97  call    RasUpdatePbkIpv6Info
0x180068f9c  mov     rcx, [rsp+4E0h+hMem]; hMem
0x180068fa1  mov     ebx, eax
0x180068fa3  call    cs:__imp_GlobalFree
0x180068faa  nop     dword ptr [rax+rax+00h]
0x180068faf  test    ebx, ebx
0x180068fb1  jz      short loc_180068FE6
0x180068fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180068fba  cmp     rcx, rdi
0x180068fbd  jz      short loc_180068FE6
0x180068fbf  test    dword ptr [rcx+1Ch], 1000h
0x180068fc6  jz      short loc_180068FE6
0x180068fc8  cmp     byte ptr [rcx+19h], 2
0x180068fcc  jb      short loc_180068FE6
0x180068fce  mov     edx, 21h ; '!'
0x180068fd3  mov     r9d, ebx
0x180068fd6  mov     rcx, [rcx+10h]
0x180068fda  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180068fe1  call    WPP_SF_d
0x180068fe6  call    cs:__imp_RevertToSelf
0x180068fed  nop     dword ptr [rax+rax+00h]
0x180068ff2  test    eax, eax
0x180068ff4  jnz     short loc_18006903B
0x180068ff6  call    cs:__imp_GetLastError
0x180068ffd  nop     dword ptr [rax+rax+00h]
0x180069002  mov     ebx, eax
0x180069004  test    eax, eax
0x180069006  jz      short loc_18006903B
0x180069008  mov     rcx, cs:WPP_GLOBAL_Control
0x18006900f  cmp     rcx, rdi
0x180069012  jz      short loc_18006903B
0x180069014  test    dword ptr [rcx+1Ch], 1000h
0x18006901b  jz      short loc_18006903B
0x18006901d  cmp     byte ptr [rcx+19h], 2
0x180069021  jb      short loc_18006903B
0x180069023  mov     edx, 22h ; '"'
0x180069028  mov     rcx, [rcx+10h]
0x18006902c  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180069033  mov     r9d, eax
0x180069036  call    WPP_SF_d
0x18006903b  lea     rcx, [rsp+4E0h+var_4A0]
0x180069040  call    ClosePhonebookFile
0x180069045  mov     rcx, cs:WPP_GLOBAL_Control
0x18006904c  cmp     rcx, rdi
0x18006904f  jz      loc_180068E6E
0x180069055  test    dword ptr [rcx+1Ch], 1000h
0x18006905c  jz      loc_180068E6E
0x180069062  cmp     byte ptr [rcx+19h], 6
0x180069066  jb      loc_180068E6E
0x18006906c  mov     edx, 23h ; '#'
0x180069071  jmp     loc_180068E5B
```
