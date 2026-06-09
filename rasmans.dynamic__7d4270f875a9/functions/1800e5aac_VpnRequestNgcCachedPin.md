# VpnRequestNgcCachedPin

- ea: `0x1800e5aac`
- end: `0x1800e5f8e`
- name: `VpnRequestNgcCachedPin`
- size: `1250`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005b06c`

## callees

- `0x180005bfc`
- `0x180005cf8`
- `0x1800ab634`
- `0x1800e3ca0`
- `0x1800e5aac`
- `0x1800e8e96`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e5c6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e5c6b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e5c89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e5c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5e2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5d92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5e2b`
- `RPCRT4!RpcImpersonateClient` at `0x1800e5c3b`
- `RPCRT4!RpcImpersonateClient` at `0x1800e5c3b`
- `RPCRT4!RpcRevertToSelf` at `0x1800e5cec`
- `RPCRT4!RpcRevertToSelf` at `0x1800e5d10`
- `RPCRT4!RpcRevertToSelf` at `0x1800e5cec`
- `RPCRT4!RpcRevertToSelf` at `0x1800e5d10`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e5bf3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e5bf3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e5cdb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e5d02`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e5cdb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e5d02`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800e5d80`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800e5e19`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800e5d80`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800e5e19`
- `ncrypt!NCryptGetProperty` at `0x1800e5d41`
- `ncrypt!NCryptGetProperty` at `0x1800e5ec7`
- `ncrypt!NCryptGetProperty` at `0x1800e5d41`
- `ncrypt!NCryptGetProperty` at `0x1800e5ec7`
- `ncrypt!NCryptSetProperty` at `0x1800e5e76`
- `ncrypt!NCryptSetProperty` at `0x1800e5e76`

## string_xrefs

- `0x1800e5d2a`: `PinCacheApplicationTicket`
- `0x1800e5eb0`: `PinCacheApplicationTicket`
- `0x1800e5d77`: `%windir%\System32\lsass.exe`
- `0x1800e5e0f`: `%windir%\System32\lsass.exe`
- `0x1800e5e6f`: `PinCacheApplicationImage`

## pseudocode

```c
__int64 __fastcall VpnRequestNgcCachedPin(__int64 a1, NCRYPT_HANDLE a2, void *a3, __int64 *a4, NCRYPT_HANDLE **a5)
{
  __int64 v9; // r15
  unsigned int v10; // ebx
  SECURITY_STATUS Property; // esi
  void *v12; // r12
  NCRYPT_HANDLE *v13; // r14
  DWORD LastError; // edi
  struct _LIST_ENTRY *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  HANDLE CurrentThread; // rax
  struct _LIST_ENTRY *v19; // rcx
  __int64 v20; // rdx
  DWORD v21; // ebx
  DWORD v22; // ebp
  size_t v23; // rbx
  void *v24; // rax
  DWORD v25; // ebx
  DWORD cbOutput; // [rsp+30h] [rbp-58h] BYREF
  DWORD pcbResult[21]; // [rsp+34h] [rbp-54h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 37, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, a3);
  }
  cbOutput = 0;
  pcbResult[0] = 0;
  *a4 = 0;
  *a5 = 0;
  v9 = VpnAlloc(112);
  if ( v9 )
  {
    Property = 0;
    v12 = 0;
    v13 = (NCRYPT_HANDLE *)VpnAlloc(112);
    if ( !v13 )
    {
      LastError = 14;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
LABEL_53:
        v10 = LastError;
        *a4 = v9;
        if ( v13 )
          *a5 = v13;
        if ( Property < 0 && !LastError )
        {
          v10 = (unsigned __int16)Property;
          if ( (Property & 0x1FFF0000) != 0x70000 )
            v10 = 13;
        }
        if ( v12 )
          MprCommonFree(v12);
        goto LABEL_61;
      }
      v16 = 39;
      goto LABEL_11;
    }
    memset_0((void *)v9, 0, 0x70u);
    cbOutput = 90;
    *(_QWORD *)(v9 + 96) = a1;
    memset_0(v13, 0, 0x70u);
    pcbResult[0] = 90;
    v13[12] = a2;
    if ( a3 )
    {
      LastError = 0;
      if ( !ImpersonateLoggedOnUser(a3) )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_53;
          v16 = 40;
          goto LABEL_18;
        }
      }
    }
    else
    {
      LastError = RpcImpersonateClient(0);
      if ( LastError )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_53;
        v16 = 41;
        goto LABEL_18;
      }
    }
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, (PHANDLE)(v9 + 104)) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 42, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, LastError);
        if ( a3 )
          RevertToSelf();
        else
          RpcRevertToSelf();
        goto LABEL_53;
      }
    }
    if ( a3 )
      RevertToSelf();
    else
      RpcRevertToSelf();
    Property = NCryptGetProperty(
                 *(_QWORD *)(v9 + 96),
                 L"PinCacheApplicationTicket",
                 (PBYTE)v9,
                 cbOutput,
                 &cbOutput,
                 0x40u);
    if ( Property < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_53;
      v20 = 43;
LABEL_52:
      WPP_SF_d(v19[1].Flink, v20, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, (unsigned int)Property);
      goto LABEL_53;
    }
    v21 = ExpandEnvironmentStringsW(L"%windir%\\System32\\lsass.exe", 0, 0);
    if ( v21 || (LastError = GetLastError()) == 0 )
    {
      v22 = v21 + 1;
      v23 = 2LL * (v21 + 1);
      v24 = (void *)VpnAlloc(v23);
      v12 = v24;
      if ( !v24 )
      {
        LastError = 14;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_53;
        v16 = 45;
LABEL_11:
        v17 = 14;
LABEL_12:
        WPP_SF_d(v15[1].Flink, v16, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v17);
        goto LABEL_53;
      }
      memset_0(v24, 0, v23);
      v25 = ExpandEnvironmentStringsW(L"%windir%\\System32\\lsass.exe", (LPWSTR)v12, v22);
      if ( v25 || (LastError = GetLastError()) == 0 )
      {
        Property = NCryptSetProperty(v13[12], L"PinCacheApplicationImage", (PBYTE)v12, 2 * v25, 0);
        if ( Property >= 0 )
        {
          Property = NCryptGetProperty(
                       v13[12],
                       L"PinCacheApplicationTicket",
                       (PBYTE)v13,
                       pcbResult[0],
                       pcbResult,
                       0x40u);
          if ( Property >= 0 )
            goto LABEL_53;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_53;
          v20 = 48;
        }
        else
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_53;
          v20 = 47;
        }
        goto LABEL_52;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_53;
      v16 = 46;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_53;
      v16 = 44;
    }
LABEL_18:
    v17 = LastError;
    goto LABEL_12;
  }
  v10 = 14;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v10;
  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 38, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, 14);
LABEL_61:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 49, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x1800e5aac  mov     [rsp+arg_18], r9
0x1800e5ab1  push    rbx
0x1800e5ab2  push    rbp
0x1800e5ab3  push    rsi
0x1800e5ab4  push    rdi
0x1800e5ab5  push    r12
0x1800e5ab7  push    r13
0x1800e5ab9  push    r14
0x1800e5abb  push    r15
0x1800e5abd  sub     rsp, 48h
0x1800e5ac1  mov     rsi, r9
0x1800e5ac4  mov     rbp, r8
0x1800e5ac7  mov     rbx, rdx
0x1800e5aca  mov     rdi, rcx
0x1800e5acd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5ad4  lea     rax, WPP_GLOBAL_Control
0x1800e5adb  cmp     rcx, rax
0x1800e5ade  jz      short loc_1800E5B04
0x1800e5ae0  test    byte ptr [rcx+1Ch], 80h
0x1800e5ae4  jz      short loc_1800E5B04
0x1800e5ae6  cmp     byte ptr [rcx+19h], 6
0x1800e5aea  jb      short loc_1800E5B04
0x1800e5aec  mov     rcx, [rcx+10h]
0x1800e5af0  mov     r9, r8
0x1800e5af3  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e5afa  mov     edx, 25h ; '%'
0x1800e5aff  call    WPP_SF_q
0x1800e5b04  mov     r13, [rsp+88h+arg_20]
0x1800e5b0c  xor     r14d, r14d
0x1800e5b0f  mov     [rsp+88h+cbOutput], r14d
0x1800e5b14  mov     [rsp+88h+var_54], r14d
0x1800e5b19  mov     [rsi], r14
0x1800e5b1c  lea     ecx, [r14+70h]
0x1800e5b20  mov     [r13+0], r14
0x1800e5b24  call    VpnAlloc
0x1800e5b29  mov     r15, rax
0x1800e5b2c  test    rax, rax
0x1800e5b2f  jnz     short loc_1800E5B66
0x1800e5b31  lea     ebx, [rax+0Eh]
0x1800e5b34  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5b3b  lea     rax, WPP_GLOBAL_Control
0x1800e5b42  cmp     rcx, rax
0x1800e5b45  jz      loc_1800E5F7A
0x1800e5b4b  mov     rcx, [rcx+10h]
0x1800e5b4f  lea     edx, [rbx+18h]
0x1800e5b52  mov     r9d, ebx
0x1800e5b55  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e5b5c  call    WPP_SF_d
0x1800e5b61  jmp     loc_1800E5F43
0x1800e5b66  mov     ecx, 70h ; 'p'
0x1800e5b6b  mov     esi, r14d
0x1800e5b6e  mov     r12, r14
0x1800e5b71  call    VpnAlloc
0x1800e5b76  mov     r14, rax
0x1800e5b79  test    rax, rax
0x1800e5b7c  jnz     short loc_1800E5BB5
0x1800e5b7e  lea     ebx, [rax+0Eh]
0x1800e5b81  mov     edi, ebx
0x1800e5b83  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5b8a  lea     rax, WPP_GLOBAL_Control
0x1800e5b91  cmp     rcx, rax
0x1800e5b94  jz      loc_1800E5F04
0x1800e5b9a  lea     edx, [rbx+19h]
0x1800e5b9d  mov     r9d, ebx
0x1800e5ba0  mov     rcx, [rcx+10h]
0x1800e5ba4  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e5bab  call    WPP_SF_d
0x1800e5bb0  jmp     loc_1800E5F04
0x1800e5bb5  xor     edx, edx; Val
0x1800e5bb7  mov     rcx, r15; void *
0x1800e5bba  lea     r8d, [rdx+70h]; Size
0x1800e5bbe  call    memset_0
0x1800e5bc3  xor     edx, edx; Val
0x1800e5bc5  mov     [rsp+88h+cbOutput], 5Ah ; 'Z'
0x1800e5bcd  mov     rcx, r14; void *
0x1800e5bd0  mov     [r15+60h], rdi
0x1800e5bd4  lea     r8d, [rdx+70h]; Size
0x1800e5bd8  call    memset_0
0x1800e5bdd  mov     [rsp+88h+var_54], 5Ah ; 'Z'
0x1800e5be5  mov     [r14+60h], rbx
0x1800e5be9  test    rbp, rbp
0x1800e5bec  jz      short loc_1800E5C39
0x1800e5bee  mov     rcx, rbp; hToken
0x1800e5bf1  xor     edi, edi
0x1800e5bf3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800e5bfa  nop     dword ptr [rax+rax+00h]
0x1800e5bff  test    eax, eax
0x1800e5c01  jnz     short loc_1800E5C6B
0x1800e5c03  call    cs:__imp_GetLastError
0x1800e5c0a  nop     dword ptr [rax+rax+00h]
0x1800e5c0f  mov     edi, eax
0x1800e5c11  test    eax, eax
0x1800e5c13  jz      short loc_1800E5C6B
0x1800e5c15  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5c1c  lea     rax, WPP_GLOBAL_Control
0x1800e5c23  cmp     rcx, rax
0x1800e5c26  jz      loc_1800E5F04
0x1800e5c2c  mov     edx, 28h ; '('
0x1800e5c31  mov     r9d, edi
0x1800e5c34  jmp     loc_1800E5BA0
0x1800e5c39  xor     ecx, ecx; BindingHandle
0x1800e5c3b  call    cs:__imp_RpcImpersonateClient
0x1800e5c42  nop     dword ptr [rax+rax+00h]
0x1800e5c47  mov     edi, eax
0x1800e5c49  test    eax, eax
0x1800e5c4b  jz      short loc_1800E5C6B
0x1800e5c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5c54  lea     rax, WPP_GLOBAL_Control
0x1800e5c5b  cmp     rcx, rax
0x1800e5c5e  jz      loc_1800E5F04
0x1800e5c64  mov     edx, 29h ; ')'
0x1800e5c69  jmp     short loc_1800E5C31
0x1800e5c6b  call    cs:__imp_GetCurrentThread
0x1800e5c72  nop     dword ptr [rax+rax+00h]
0x1800e5c77  lea     r9, [r15+68h]; TokenHandle
0x1800e5c7b  mov     edx, 0F01FFh; DesiredAccess
0x1800e5c80  mov     rcx, rax; ThreadHandle
0x1800e5c83  mov     r8d, 1; OpenAsSelf
0x1800e5c89  call    cs:__imp_OpenThreadToken
0x1800e5c90  nop     dword ptr [rax+rax+00h]
0x1800e5c95  test    eax, eax
0x1800e5c97  jnz     short loc_1800E5CFD
0x1800e5c99  call    cs:__imp_GetLastError
0x1800e5ca0  nop     dword ptr [rax+rax+00h]
0x1800e5ca5  mov     edi, eax
0x1800e5ca7  test    eax, eax
0x1800e5ca9  jz      short loc_1800E5CFD
0x1800e5cab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5cb2  lea     rax, WPP_GLOBAL_Control
0x1800e5cb9  cmp     rcx, rax
0x1800e5cbc  jz      short loc_1800E5CD6
0x1800e5cbe  mov     rcx, [rcx+10h]
0x1800e5cc2  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e5cc9  mov     edx, 2Ah ; '*'
0x1800e5cce  mov     r9d, edi
0x1800e5cd1  call    WPP_SF_d
0x1800e5cd6  test    rbp, rbp
0x1800e5cd9  jz      short loc_1800E5CEC
0x1800e5cdb  call    cs:__imp_RevertToSelf
0x1800e5ce2  nop     dword ptr [rax+rax+00h]
0x1800e5ce7  jmp     loc_1800E5F04
0x1800e5cec  call    cs:__imp_RpcRevertToSelf
0x1800e5cf3  nop     dword ptr [rax+rax+00h]
0x1800e5cf8  jmp     loc_1800E5F04
0x1800e5cfd  test    rbp, rbp
0x1800e5d00  jz      short loc_1800E5D10
0x1800e5d02  call    cs:__imp_RevertToSelf
0x1800e5d09  nop     dword ptr [rax+rax+00h]
0x1800e5d0e  jmp     short loc_1800E5D1C
0x1800e5d10  call    cs:__imp_RpcRevertToSelf
0x1800e5d17  nop     dword ptr [rax+rax+00h]
0x1800e5d1c  mov     r9d, [rsp+88h+cbOutput]; cbOutput
0x1800e5d21  lea     rax, [rsp+88h+cbOutput]
0x1800e5d26  mov     rcx, [r15+60h]; hObject
0x1800e5d2a  lea     rdx, aPincacheapplic_0; "PinCacheApplicationTicket"
0x1800e5d31  mov     [rsp+88h+dwFlags], 40h ; '@'; dwFlags
0x1800e5d39  mov     r8, r15; pbOutput
0x1800e5d3c  mov     [rsp+88h+pcbResult], rax; pcbResult
0x1800e5d41  call    cs:__imp_NCryptGetProperty
0x1800e5d48  nop     dword ptr [rax+rax+00h]
0x1800e5d4d  mov     esi, eax
0x1800e5d4f  test    eax, eax
0x1800e5d51  jns     short loc_1800E5D74
0x1800e5d53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5d5a  lea     rax, WPP_GLOBAL_Control
0x1800e5d61  cmp     rcx, rax
0x1800e5d64  jz      loc_1800E5F04
0x1800e5d6a  mov     edx, 2Bh ; '+'
0x1800e5d6f  jmp     loc_1800E5EF1
0x1800e5d74  xor     r8d, r8d; nSize
0x1800e5d77  lea     rcx, aWindirSystem32; "%windir%\\System32\\lsass.exe"
0x1800e5d7e  xor     edx, edx; lpDst
0x1800e5d80  call    cs:__imp_ExpandEnvironmentStringsW
0x1800e5d87  nop     dword ptr [rax+rax+00h]
0x1800e5d8c  mov     ebx, eax
0x1800e5d8e  test    eax, eax
0x1800e5d90  jnz     short loc_1800E5DC3
0x1800e5d92  call    cs:__imp_GetLastError
0x1800e5d99  nop     dword ptr [rax+rax+00h]
0x1800e5d9e  mov     edi, eax
0x1800e5da0  test    eax, eax
0x1800e5da2  jz      short loc_1800E5DC3
0x1800e5da4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5dab  lea     rax, WPP_GLOBAL_Control
0x1800e5db2  cmp     rcx, rax
0x1800e5db5  jz      loc_1800E5F04
0x1800e5dbb  lea     edx, [rbx+2Ch]
0x1800e5dbe  jmp     loc_1800E5C31
0x1800e5dc3  lea     ebp, [rbx+1]
0x1800e5dc6  mov     ebx, ebp
0x1800e5dc8  add     rbx, rbx
0x1800e5dcb  mov     rcx, rbx
0x1800e5dce  call    VpnAlloc
0x1800e5dd3  mov     r12, rax
0x1800e5dd6  test    rax, rax
0x1800e5dd9  jnz     short loc_1800E5DFF
0x1800e5ddb  lea     ebx, [rax+0Eh]
0x1800e5dde  mov     edi, ebx
0x1800e5de0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5de7  lea     rax, WPP_GLOBAL_Control
0x1800e5dee  cmp     rcx, rax
0x1800e5df1  jz      loc_1800E5F04
0x1800e5df7  lea     edx, [rbx+1Fh]
0x1800e5dfa  jmp     loc_1800E5B9D
0x1800e5dff  mov     r8, rbx; Size
0x1800e5e02  xor     edx, edx; Val
0x1800e5e04  mov     rcx, r12; void *
0x1800e5e07  call    memset_0
0x1800e5e0c  mov     r8d, ebp; nSize
0x1800e5e0f  lea     rcx, aWindirSystem32; "%windir%\\System32\\lsass.exe"
0x1800e5e16  mov     rdx, r12; lpDst
0x1800e5e19  call    cs:__imp_ExpandEnvironmentStringsW
0x1800e5e20  nop     dword ptr [rax+rax+00h]
0x1800e5e25  mov     ebx, eax
0x1800e5e27  test    eax, eax
0x1800e5e29  jnz     short loc_1800E5E5C
0x1800e5e2b  call    cs:__imp_GetLastError
0x1800e5e32  nop     dword ptr [rax+rax+00h]
0x1800e5e37  mov     edi, eax
0x1800e5e39  test    eax, eax
0x1800e5e3b  jz      short loc_1800E5E5C
0x1800e5e3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5e44  lea     rax, WPP_GLOBAL_Control
0x1800e5e4b  cmp     rcx, rax
0x1800e5e4e  jz      loc_1800E5F04
0x1800e5e54  lea     edx, [rbx+2Eh]
0x1800e5e57  jmp     loc_1800E5C31
0x1800e5e5c  mov     rcx, [r14+60h]; hObject
0x1800e5e60  lea     r9d, [rbx+rbx]; cbInput
0x1800e5e64  mov     r8, r12; pbInput
0x1800e5e67  mov     dword ptr [rsp+88h+pcbResult], 0; dwFlags
0x1800e5e6f  lea     rdx, aPincacheapplic; "PinCacheApplicationImage"
0x1800e5e76  call    cs:__imp_NCryptSetProperty
0x1800e5e7d  nop     dword ptr [rax+rax+00h]
0x1800e5e82  mov     esi, eax
0x1800e5e84  test    eax, eax
0x1800e5e86  jns     short loc_1800E5EA2
0x1800e5e88  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5e8f  lea     rax, WPP_GLOBAL_Control
0x1800e5e96  cmp     rcx, rax
0x1800e5e99  jz      short loc_1800E5F04
0x1800e5e9b  mov     edx, 2Fh ; '/'
0x1800e5ea0  jmp     short loc_1800E5EF1
0x1800e5ea2  mov     r9d, [rsp+88h+var_54]; cbOutput
0x1800e5ea7  lea     rax, [rsp+88h+var_54]
0x1800e5eac  mov     rcx, [r14+60h]; hObject
0x1800e5eb0  lea     rdx, aPincacheapplic_0; "PinCacheApplicationTicket"
0x1800e5eb7  mov     [rsp+88h+dwFlags], 40h ; '@'; dwFlags
0x1800e5ebf  mov     r8, r14; pbOutput
0x1800e5ec2  mov     [rsp+88h+pcbResult], rax; pcbResult
0x1800e5ec7  call    cs:__imp_NCryptGetProperty
0x1800e5ece  nop     dword ptr [rax+rax+00h]
0x1800e5ed3  mov     esi, eax
0x1800e5ed5  test    eax, eax
0x1800e5ed7  jns     short loc_1800E5F04
0x1800e5ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5ee0  lea     rax, WPP_GLOBAL_Control
0x1800e5ee7  cmp     rcx, rax
0x1800e5eea  jz      short loc_1800E5F04
0x1800e5eec  mov     edx, 30h ; '0'
0x1800e5ef1  mov     rcx, [rcx+10h]
0x1800e5ef5  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e5efc  mov     r9d, esi
0x1800e5eff  call    WPP_SF_d
0x1800e5f04  mov     rax, [rsp+88h+arg_18]
0x1800e5f0c  mov     ebx, edi
0x1800e5f0e  mov     [rax], r15
0x1800e5f11  test    r14, r14
0x1800e5f14  jz      short loc_1800E5F1A
0x1800e5f16  mov     [r13+0], r14
0x1800e5f1a  test    esi, esi
0x1800e5f1c  jns     short loc_1800E5F36
0x1800e5f1e  test    edi, edi
0x1800e5f20  jnz     short loc_1800E5F36
0x1800e5f22  mov     eax, esi
0x1800e5f24  movzx   ebx, si
0x1800e5f27  and     eax, 1FFF0000h
0x1800e5f2c  cmp     eax, 70000h
0x1800e5f31  jz      short loc_1800E5F36
0x1800e5f33  lea     ebx, [rdi+0Dh]
0x1800e5f36  test    r12, r12
0x1800e5f39  jz      short loc_1800E5F43
0x1800e5f3b  mov     rcx, r12; lpMem
0x1800e5f3e  call    MprCommonFree
0x1800e5f43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5f4a  lea     rax, WPP_GLOBAL_Control
0x1800e5f51  cmp     rcx, rax
0x1800e5f54  jz      short loc_1800E5F7A
0x1800e5f56  test    byte ptr [rcx+1Ch], 80h
0x1800e5f5a  jz      short loc_1800E5F7A
0x1800e5f5c  cmp     byte ptr [rcx+19h], 6
0x1800e5f60  jb      short loc_1800E5F7A
0x1800e5f62  mov     rcx, [rcx+10h]
0x1800e5f66  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e5f6d  mov     edx, 31h ; '1'
0x1800e5f72  mov     r9d, ebx
0x1800e5f75  call    WPP_SF_d
0x1800e5f7a  mov     eax, ebx
0x1800e5f7c  add     rsp, 48h
0x1800e5f80  pop     r15
  ... truncated ...
```
