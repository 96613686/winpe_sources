# VpnRequestNgcCachedPinComplete

- ea: `0x1800e5f94`
- end: `0x1800e640f`
- name: `VpnRequestNgcCachedPinComplete`
- size: `1147`
- prototype: `__int64 __fastcall(PBYTE pbInput)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800597e0`
- `0x18005b06c`
- `0x1800e577c`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c37c`
- `0x18004c19c`
- `0x1800e53e0`
- `0x1800e5f94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e602e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e602e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e604c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e604c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e60a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e6332`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e60a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e6332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6397`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e6397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e605c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e60b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e635a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e605c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e60b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e635a`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e626f`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e626f`
- `ncrypt!NCryptFreeObject` at `0x1800e630f`
- `ncrypt!NCryptFreeObject` at `0x1800e630f`
- `ncrypt!NCryptSetProperty` at `0x1800e6198`
- `ncrypt!NCryptSetProperty` at `0x1800e62c6`
- `ncrypt!NCryptSetProperty` at `0x1800e6198`
- `ncrypt!NCryptSetProperty` at `0x1800e62c6`

## string_xrefs

- `0x1800e62bf`: `PinCacheFreeApplicationTicket`

## pseudocode

```c
__int64 __fastcall VpnRequestNgcCachedPinComplete(PBYTE pbInput, __int64 a2, int a3)
{
  struct _LIST_ENTRY *v5; // rcx
  int v6; // r15d
  int v7; // r14d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // r9
  int v14; // esi
  __int64 v15; // rsi
  SECURITY_STATUS v16; // eax
  DWORD v17; // eax
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  __int64 pbInputa; // [rsp+88h] [rbp+48h] BYREF
  int v21; // [rsp+90h] [rbp+50h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+98h] [rbp+58h] BYREF

  pbInputa = a2;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_qc(WPP_GLOBAL_Control[1].Flink, 50, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, a2, a3 != 0);
    v5 = WPP_GLOBAL_Control;
  }
  TokenHandle = 0;
  v6 = 0;
  v21 = 0;
  phProvider = 0;
  if ( a3 )
  {
    v7 = 0;
    if ( !*((_QWORD *)pbInput + 13) || !*((_QWORD *)pbInput + 12) )
    {
      v10 = 87;
      if ( v5 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v10;
      v11 = 51;
      v13 = 87;
      goto LABEL_52;
    }
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError == 1008 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 52, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids);
        }
      }
      else if ( LastError )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_54;
        v11 = 53;
        goto LABEL_51;
      }
    }
    if ( !SetThreadToken(0, *((HANDLE *)pbInput + 13)) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_54;
        v11 = 54;
LABEL_51:
        v13 = LastError;
LABEL_52:
        WPP_SF_d(v5[1].Flink, v11, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v13);
        goto LABEL_53;
      }
    }
    v6 = 1;
    v12 = VpnDummySign(*((_QWORD *)pbInput + 12));
    v13 = 14;
    v10 = v12;
    if ( v12 == 14 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_54;
      v11 = 55;
      goto LABEL_52;
    }
    v5 = WPP_GLOBAL_Control;
    v14 = v21;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      LOBYTE(v13) = v21 != 0;
      WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 56, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v13);
      v5 = WPP_GLOBAL_Control;
    }
    if ( !v14 )
    {
      if ( pbInputa )
      {
        LastError = NCryptSetProperty(*((_QWORD *)pbInput + 12), L"HWND Handle", (PBYTE)&pbInputa, 8u, 0);
        v10 = LastError;
        if ( LastError )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_54;
          v11 = 57;
          goto LABEL_51;
        }
        LastError = VpnDummySign(*((_QWORD *)pbInput + 12));
        v10 = LastError;
        if ( LastError )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_54;
          v11 = 58;
          goto LABEL_51;
        }
LABEL_53:
        v5 = WPP_GLOBAL_Control;
        goto LABEL_54;
      }
      v10 = 703;
      if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v5[1].Blink) < 0 && BYTE1(v5[1].Blink) >= 2u )
      {
        WPP_SF_(v5[1].Flink, 59, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids);
        goto LABEL_53;
      }
    }
LABEL_54:
    if ( phProvider )
    {
      NCryptFreeObject(phProvider);
      v5 = WPP_GLOBAL_Control;
      phProvider = 0;
    }
    if ( v6 != 1 )
      goto LABEL_63;
    if ( !SetThreadToken(0, TokenHandle) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 3u )
      {
        goto LABEL_63;
      }
      v17 = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 62, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v17);
    }
    v5 = WPP_GLOBAL_Control;
LABEL_63:
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v7 < 0 && !v10 )
    {
      v10 = (unsigned __int16)v7;
      if ( (v7 & 0x1FFF0000) != 0x70000 )
        v10 = 13;
    }
    goto LABEL_69;
  }
  v10 = 0;
  if ( *((_QWORD *)pbInput + 12) )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&pbInput[2 * v15] );
    v16 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
    v7 = v16;
    if ( v16 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_54;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 60, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, (unsigned int)v16);
      goto LABEL_53;
    }
    LastError = NCryptSetProperty(phProvider, L"PinCacheFreeApplicationTicket", pbInput, 2 * v15 + 2, 0x40u);
    v10 = LastError;
    if ( LastError )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_54;
      v11 = 61;
      goto LABEL_51;
    }
    goto LABEL_53;
  }
LABEL_69:
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v5[1].Blink) < 0 && BYTE1(v5[1].Blink) >= 6u )
    WPP_SF_d(v5[1].Flink, 63, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x1800e5f94  mov     [rsp-38h+arg_0], rbx
0x1800e5f99  mov     [rsp-38h+pbInput], rdx
0x1800e5f9e  push    rbp
0x1800e5f9f  push    rsi
0x1800e5fa0  push    rdi
0x1800e5fa1  push    r12
0x1800e5fa3  push    r13
0x1800e5fa5  push    r14
0x1800e5fa7  push    r15
0x1800e5fa9  mov     rbp, rsp
0x1800e5fac  sub     rsp, 40h
0x1800e5fb0  mov     ebx, r8d
0x1800e5fb3  mov     r9, rdx
0x1800e5fb6  mov     rdi, rcx
0x1800e5fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5fc0  lea     r13, WPP_GLOBAL_Control
0x1800e5fc7  xor     r12d, r12d
0x1800e5fca  cmp     rcx, r13
0x1800e5fcd  jz      short loc_1800E6000
0x1800e5fcf  test    byte ptr [rcx+1Ch], 80h
0x1800e5fd3  jz      short loc_1800E6000
0x1800e5fd5  cmp     byte ptr [rcx+19h], 6
0x1800e5fd9  jb      short loc_1800E6000
0x1800e5fdb  mov     rcx, [rcx+10h]
0x1800e5fdf  lea     edx, [r12+32h]
0x1800e5fe4  test    ebx, ebx
0x1800e5fe6  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e5fed  setnz   al
0x1800e5ff0  mov     byte ptr [rsp+40h+dwFlags], al
0x1800e5ff4  call    WPP_SF_qc
0x1800e5ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6000  mov     [rbp+TokenHandle], r12
0x1800e6004  mov     r15d, r12d
0x1800e6007  mov     [rbp+arg_10], r12d
0x1800e600b  mov     [rbp+phProvider], r12
0x1800e600f  test    ebx, ebx
0x1800e6011  jz      loc_1800E6246
0x1800e6017  mov     r14d, r12d
0x1800e601a  cmp     [rdi+68h], r12
0x1800e601e  jz      loc_1800E622D
0x1800e6024  cmp     [rdi+60h], r12
0x1800e6028  jz      loc_1800E622D
0x1800e602e  call    cs:__imp_GetCurrentThread
0x1800e6035  nop     dword ptr [rax+rax+00h]
0x1800e603a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e603e  mov     edx, 0F01FFh; DesiredAccess
0x1800e6043  mov     rcx, rax; ThreadHandle
0x1800e6046  mov     r8d, 1; OpenAsSelf
0x1800e604c  call    cs:__imp_OpenThreadToken
0x1800e6053  nop     dword ptr [rax+rax+00h]
0x1800e6058  test    eax, eax
0x1800e605a  jnz     short loc_1800E609E
0x1800e605c  call    cs:__imp_GetLastError
0x1800e6063  nop     dword ptr [rax+rax+00h]
0x1800e6068  mov     ebx, eax
0x1800e606a  cmp     eax, 3F0h
0x1800e606f  jnz     short loc_1800E60E0
0x1800e6071  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6078  cmp     rcx, r13
0x1800e607b  jz      short loc_1800E609E
0x1800e607d  test    byte ptr [rcx+1Ch], 80h
0x1800e6081  jz      short loc_1800E609E
0x1800e6083  cmp     byte ptr [rcx+19h], 5
0x1800e6087  jb      short loc_1800E609E
0x1800e6089  mov     rcx, [rcx+10h]
0x1800e608d  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e6094  mov     edx, 34h ; '4'
0x1800e6099  call    WPP_SF_
0x1800e609e  mov     rdx, [rdi+68h]; Token
0x1800e60a2  xor     ecx, ecx; Thread
0x1800e60a4  call    cs:__imp_SetThreadToken
0x1800e60ab  nop     dword ptr [rax+rax+00h]
0x1800e60b0  test    eax, eax
0x1800e60b2  jnz     short loc_1800E60FE
0x1800e60b4  call    cs:__imp_GetLastError
0x1800e60bb  nop     dword ptr [rax+rax+00h]
0x1800e60c0  mov     ebx, eax
0x1800e60c2  test    eax, eax
0x1800e60c4  jz      short loc_1800E60FE
0x1800e60c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e60cd  cmp     rcx, r13
0x1800e60d0  jz      loc_1800E6303
0x1800e60d6  mov     edx, 36h ; '6'
0x1800e60db  jmp     loc_1800E62E9
0x1800e60e0  test    eax, eax
0x1800e60e2  jz      short loc_1800E609E
0x1800e60e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e60eb  cmp     rcx, r13
0x1800e60ee  jz      loc_1800E6303
0x1800e60f4  mov     edx, 35h ; '5'
0x1800e60f9  jmp     loc_1800E62E9
0x1800e60fe  mov     rcx, [rdi+60h]; hKey
0x1800e6102  lea     rdx, [rbp+arg_10]
0x1800e6106  mov     r15d, 1
0x1800e610c  call    VpnDummySign
0x1800e6111  lea     r9d, [r15+0Dh]
0x1800e6115  mov     ebx, eax
0x1800e6117  cmp     eax, r9d
0x1800e611a  jnz     short loc_1800E6135
0x1800e611c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6123  cmp     rcx, r13
0x1800e6126  jz      loc_1800E6303
0x1800e612c  lea     edx, [r15+36h]
0x1800e6130  jmp     loc_1800E62EC
0x1800e6135  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e613c  mov     esi, [rbp+arg_10]
0x1800e613f  cmp     rcx, r13
0x1800e6142  jz      short loc_1800E6172
0x1800e6144  test    byte ptr [rcx+1Ch], 80h
0x1800e6148  jz      short loc_1800E6172
0x1800e614a  cmp     byte ptr [rcx+19h], 5
0x1800e614e  jb      short loc_1800E6172
0x1800e6150  mov     rcx, [rcx+10h]
0x1800e6154  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e615b  test    esi, esi
0x1800e615d  mov     edx, 38h ; '8'
0x1800e6162  setnz   r9b
0x1800e6166  call    WPP_SF_c
0x1800e616b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6172  test    esi, esi
0x1800e6174  jnz     loc_1800E6303
0x1800e617a  cmp     [rbp+pbInput], r12
0x1800e617e  jz      short loc_1800E61F1
0x1800e6180  mov     rcx, [rdi+60h]; hObject
0x1800e6184  lea     r9d, [rsi+8]; cbInput
0x1800e6188  lea     r8, [rbp+pbInput]; pbInput
0x1800e618c  mov     [rsp+40h+dwFlags], r12d; dwFlags
0x1800e6191  lea     rdx, aHwndHandle; "HWND Handle"
0x1800e6198  call    cs:__imp_NCryptSetProperty
0x1800e619f  nop     dword ptr [rax+rax+00h]
0x1800e61a4  mov     ebx, eax
0x1800e61a6  test    eax, eax
0x1800e61a8  jz      short loc_1800E61C2
0x1800e61aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e61b1  cmp     rcx, r13
0x1800e61b4  jz      loc_1800E6303
0x1800e61ba  lea     edx, [rsi+39h]
0x1800e61bd  jmp     loc_1800E62E9
0x1800e61c2  mov     rcx, [rdi+60h]; hKey
0x1800e61c6  xor     edx, edx
0x1800e61c8  call    VpnDummySign
0x1800e61cd  mov     ebx, eax
0x1800e61cf  test    eax, eax
0x1800e61d1  jz      loc_1800E62FC
0x1800e61d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e61de  cmp     rcx, r13
0x1800e61e1  jz      loc_1800E6303
0x1800e61e7  mov     edx, 3Ah ; ':'
0x1800e61ec  jmp     loc_1800E62E9
0x1800e61f1  mov     ebx, 2BFh
0x1800e61f6  cmp     rcx, r13
0x1800e61f9  jz      loc_1800E6303
0x1800e61ff  test    byte ptr [rcx+1Ch], 80h
0x1800e6203  jz      loc_1800E6303
0x1800e6209  cmp     byte ptr [rcx+19h], 2
0x1800e620d  jb      loc_1800E6303
0x1800e6213  mov     rcx, [rcx+10h]
0x1800e6217  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e621e  mov     edx, 3Bh ; ';'
0x1800e6223  call    WPP_SF_
0x1800e6228  jmp     loc_1800E62FC
0x1800e622d  mov     ebx, 57h ; 'W'
0x1800e6232  cmp     rcx, r13
0x1800e6235  jz      loc_1800E63F4
0x1800e623b  lea     edx, [rbx-24h]
0x1800e623e  mov     r9d, ebx
0x1800e6241  jmp     loc_1800E62EC
0x1800e6246  mov     ebx, r12d
0x1800e6249  cmp     [rdi+60h], r12
0x1800e624d  jz      loc_1800E63CB
0x1800e6253  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800e6257  inc     rsi
0x1800e625a  cmp     [rdi+rsi*2], r12w
0x1800e625f  jnz     short loc_1800E6257
0x1800e6261  xor     r8d, r8d; dwFlags
0x1800e6264  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x1800e626b  lea     rcx, [rbp+phProvider]; phProvider
0x1800e626f  call    cs:__imp_NCryptOpenStorageProvider
0x1800e6276  nop     dword ptr [rax+rax+00h]
0x1800e627b  mov     r14d, eax
0x1800e627e  test    eax, eax
0x1800e6280  jns     short loc_1800E62A8
0x1800e6282  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6289  cmp     rcx, r13
0x1800e628c  jz      short loc_1800E6303
0x1800e628e  mov     rcx, [rcx+10h]
0x1800e6292  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e6299  mov     edx, 3Ch ; '<'
0x1800e629e  mov     r9d, eax
0x1800e62a1  call    WPP_SF_d
0x1800e62a6  jmp     short loc_1800E62FC
0x1800e62a8  mov     rcx, [rbp+phProvider]; hObject
0x1800e62ac  lea     r9d, ds:2[rsi*2]; cbInput
0x1800e62b4  mov     r8, rdi; pbInput
0x1800e62b7  mov     [rsp+40h+dwFlags], 40h ; '@'; dwFlags
0x1800e62bf  lea     rdx, aPincachefreeap; "PinCacheFreeApplicationTicket"
0x1800e62c6  call    cs:__imp_NCryptSetProperty
0x1800e62cd  nop     dword ptr [rax+rax+00h]
0x1800e62d2  mov     ebx, eax
0x1800e62d4  test    eax, eax
0x1800e62d6  jz      short loc_1800E62FC
0x1800e62d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e62df  cmp     rcx, r13
0x1800e62e2  jz      short loc_1800E6303
0x1800e62e4  mov     edx, 3Dh ; '='
0x1800e62e9  mov     r9d, eax
0x1800e62ec  mov     rcx, [rcx+10h]
0x1800e62f0  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e62f7  call    WPP_SF_d
0x1800e62fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6303  mov     rax, [rbp+phProvider]
0x1800e6307  test    rax, rax
0x1800e630a  jz      short loc_1800E6326
0x1800e630c  mov     rcx, rax; hObject
0x1800e630f  call    cs:__imp_NCryptFreeObject
0x1800e6316  nop     dword ptr [rax+rax+00h]
0x1800e631b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6322  mov     [rbp+phProvider], r12
0x1800e6326  cmp     r15d, 1
0x1800e632a  jnz     short loc_1800E638B
0x1800e632c  mov     rdx, [rbp+TokenHandle]; Token
0x1800e6330  xor     ecx, ecx; Thread
0x1800e6332  call    cs:__imp_SetThreadToken
0x1800e6339  nop     dword ptr [rax+rax+00h]
0x1800e633e  test    eax, eax
0x1800e6340  jnz     short loc_1800E6384
0x1800e6342  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6349  cmp     rcx, r13
0x1800e634c  jz      short loc_1800E638B
0x1800e634e  test    byte ptr [rcx+1Ch], 80h
0x1800e6352  jz      short loc_1800E638B
0x1800e6354  cmp     byte ptr [rcx+19h], 3
0x1800e6358  jb      short loc_1800E638B
0x1800e635a  call    cs:__imp_GetLastError
0x1800e6361  nop     dword ptr [rax+rax+00h]
0x1800e6366  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e636d  lea     edx, [r15+3Dh]
0x1800e6371  mov     r9d, eax
0x1800e6374  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e637b  mov     rcx, [rcx+10h]
0x1800e637f  call    WPP_SF_d
0x1800e6384  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e638b  mov     rax, [rbp+TokenHandle]
0x1800e638f  test    rax, rax
0x1800e6392  jz      short loc_1800E63AA
0x1800e6394  mov     rcx, rax; hObject
0x1800e6397  call    cs:__imp_CloseHandle
0x1800e639e  nop     dword ptr [rax+rax+00h]
0x1800e63a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e63aa  test    r14d, r14d
0x1800e63ad  jns     short loc_1800E63CB
0x1800e63af  test    ebx, ebx
0x1800e63b1  jnz     short loc_1800E63CB
0x1800e63b3  mov     eax, r14d
0x1800e63b6  movzx   ebx, r14w
0x1800e63ba  and     eax, 1FFF0000h
0x1800e63bf  cmp     eax, 70000h
0x1800e63c4  jz      short loc_1800E63CB
0x1800e63c6  mov     ebx, 0Dh
0x1800e63cb  cmp     rcx, r13
0x1800e63ce  jz      short loc_1800E63F4
0x1800e63d0  test    byte ptr [rcx+1Ch], 80h
0x1800e63d4  jz      short loc_1800E63F4
0x1800e63d6  cmp     byte ptr [rcx+19h], 6
0x1800e63da  jb      short loc_1800E63F4
0x1800e63dc  mov     rcx, [rcx+10h]
0x1800e63e0  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e63e7  mov     edx, 3Fh ; '?'
0x1800e63ec  mov     r9d, ebx
0x1800e63ef  call    WPP_SF_d
0x1800e63f4  mov     eax, ebx
0x1800e63f6  mov     rbx, [rsp+40h+arg_0]
0x1800e63fe  add     rsp, 40h
0x1800e6402  pop     r15
0x1800e6404  pop     r14
0x1800e6406  pop     r13
0x1800e6408  pop     r12
0x1800e640a  pop     rdi
0x1800e640b  pop     rsi
0x1800e640c  pop     rbp
0x1800e640d  retn
```
