# VpnRequestNgcCachedPinComplete

- ea: `0x1800e4420`
- end: `0x1800e4852`
- name: `VpnRequestNgcCachedPinComplete`
- size: `1074`
- prototype: `__int64 __fastcall(PBYTE pbInput)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180056db0`
- `0x1800584e0`
- `0x1800e3c88`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bf70`
- `0x180049d94`
- `0x1800e3908`
- `0x1800e4420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e451e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e4788`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e451e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e4788`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e44d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e44d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e44ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e44ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e47e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e47e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e44dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e47aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e44dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e47aa`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e46d7`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e46d7`
- `ncrypt!NCryptFreeObject` at `0x1800e476b`
- `ncrypt!NCryptFreeObject` at `0x1800e476b`
- `ncrypt!NCryptSetProperty` at `0x1800e4606`
- `ncrypt!NCryptSetProperty` at `0x1800e4728`
- `ncrypt!NCryptSetProperty` at `0x1800e4606`
- `ncrypt!NCryptSetProperty` at `0x1800e4728`

## string_xrefs

- `0x1800e4721`: `PinCacheFreeApplicationTicket`

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
0x1800e4420  mov     [rsp-38h+arg_0], rbx
0x1800e4425  mov     [rsp-38h+pbInput], rdx
0x1800e442a  push    rbp
0x1800e442b  push    rsi
0x1800e442c  push    rdi
0x1800e442d  push    r12
0x1800e442f  push    r13
0x1800e4431  push    r14
0x1800e4433  push    r15
0x1800e4435  mov     rbp, rsp
0x1800e4438  sub     rsp, 40h
0x1800e443c  mov     ebx, r8d
0x1800e443f  mov     r9, rdx
0x1800e4442  mov     rdi, rcx
0x1800e4445  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e444c  lea     r13, WPP_GLOBAL_Control
0x1800e4453  xor     r12d, r12d
0x1800e4456  cmp     rcx, r13
0x1800e4459  jz      short loc_1800E448C
0x1800e445b  test    byte ptr [rcx+1Ch], 80h
0x1800e445f  jz      short loc_1800E448C
0x1800e4461  cmp     byte ptr [rcx+19h], 6
0x1800e4465  jb      short loc_1800E448C
0x1800e4467  mov     rcx, [rcx+10h]
0x1800e446b  lea     edx, [r12+32h]
0x1800e4470  test    ebx, ebx
0x1800e4472  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e4479  setnz   al
0x1800e447c  mov     byte ptr [rsp+40h+dwFlags], al
0x1800e4480  call    WPP_SF_qc
0x1800e4485  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e448c  mov     [rbp+TokenHandle], r12
0x1800e4490  mov     r15d, r12d
0x1800e4493  mov     [rbp+arg_10], r12d
0x1800e4497  mov     [rbp+phProvider], r12
0x1800e449b  test    ebx, ebx
0x1800e449d  jz      loc_1800E46AE
0x1800e44a3  mov     r14d, r12d
0x1800e44a6  cmp     [rdi+68h], r12
0x1800e44aa  jz      loc_1800E4695
0x1800e44b0  cmp     [rdi+60h], r12
0x1800e44b4  jz      loc_1800E4695
0x1800e44ba  call    cs:__imp_GetCurrentThread
0x1800e44c0  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e44c4  mov     edx, 0F01FFh; DesiredAccess
0x1800e44c9  mov     rcx, rax; ThreadHandle
0x1800e44cc  mov     r8d, 1; OpenAsSelf
0x1800e44d2  call    cs:__imp_OpenThreadToken
0x1800e44d8  test    eax, eax
0x1800e44da  jnz     short loc_1800E4518
0x1800e44dc  call    cs:__imp_GetLastError
0x1800e44e2  mov     ebx, eax
0x1800e44e4  cmp     eax, 3F0h
0x1800e44e9  jnz     short loc_1800E454E
0x1800e44eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e44f2  cmp     rcx, r13
0x1800e44f5  jz      short loc_1800E4518
0x1800e44f7  test    byte ptr [rcx+1Ch], 80h
0x1800e44fb  jz      short loc_1800E4518
0x1800e44fd  cmp     byte ptr [rcx+19h], 5
0x1800e4501  jb      short loc_1800E4518
0x1800e4503  mov     rcx, [rcx+10h]
0x1800e4507  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e450e  mov     edx, 34h ; '4'
0x1800e4513  call    WPP_SF_
0x1800e4518  mov     rdx, [rdi+68h]; Token
0x1800e451c  xor     ecx, ecx; Thread
0x1800e451e  call    cs:__imp_SetThreadToken
0x1800e4524  test    eax, eax
0x1800e4526  jnz     short loc_1800E456C
0x1800e4528  call    cs:__imp_GetLastError
0x1800e452e  mov     ebx, eax
0x1800e4530  test    eax, eax
0x1800e4532  jz      short loc_1800E456C
0x1800e4534  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e453b  cmp     rcx, r13
0x1800e453e  jz      loc_1800E475F
0x1800e4544  mov     edx, 36h ; '6'
0x1800e4549  jmp     loc_1800E4745
0x1800e454e  test    eax, eax
0x1800e4550  jz      short loc_1800E4518
0x1800e4552  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4559  cmp     rcx, r13
0x1800e455c  jz      loc_1800E475F
0x1800e4562  mov     edx, 35h ; '5'
0x1800e4567  jmp     loc_1800E4745
0x1800e456c  mov     rcx, [rdi+60h]; hKey
0x1800e4570  lea     rdx, [rbp+arg_10]
0x1800e4574  mov     r15d, 1
0x1800e457a  call    VpnDummySign
0x1800e457f  lea     r9d, [r15+0Dh]
0x1800e4583  mov     ebx, eax
0x1800e4585  cmp     eax, r9d
0x1800e4588  jnz     short loc_1800E45A3
0x1800e458a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4591  cmp     rcx, r13
0x1800e4594  jz      loc_1800E475F
0x1800e459a  lea     edx, [r15+36h]
0x1800e459e  jmp     loc_1800E4748
0x1800e45a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e45aa  mov     esi, [rbp+arg_10]
0x1800e45ad  cmp     rcx, r13
0x1800e45b0  jz      short loc_1800E45E0
0x1800e45b2  test    byte ptr [rcx+1Ch], 80h
0x1800e45b6  jz      short loc_1800E45E0
0x1800e45b8  cmp     byte ptr [rcx+19h], 5
0x1800e45bc  jb      short loc_1800E45E0
0x1800e45be  mov     rcx, [rcx+10h]
0x1800e45c2  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e45c9  test    esi, esi
0x1800e45cb  mov     edx, 38h ; '8'
0x1800e45d0  setnz   r9b
0x1800e45d4  call    WPP_SF_c
0x1800e45d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e45e0  test    esi, esi
0x1800e45e2  jnz     loc_1800E475F
0x1800e45e8  cmp     [rbp+pbInput], r12
0x1800e45ec  jz      short loc_1800E4659
0x1800e45ee  mov     rcx, [rdi+60h]; hObject
0x1800e45f2  lea     r9d, [rsi+8]; cbInput
0x1800e45f6  lea     r8, [rbp+pbInput]; pbInput
0x1800e45fa  mov     [rsp+40h+dwFlags], r12d; dwFlags
0x1800e45ff  lea     rdx, aHwndHandle; "HWND Handle"
0x1800e4606  call    cs:__imp_NCryptSetProperty
0x1800e460c  mov     ebx, eax
0x1800e460e  test    eax, eax
0x1800e4610  jz      short loc_1800E462A
0x1800e4612  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4619  cmp     rcx, r13
0x1800e461c  jz      loc_1800E475F
0x1800e4622  lea     edx, [rsi+39h]
0x1800e4625  jmp     loc_1800E4745
0x1800e462a  mov     rcx, [rdi+60h]; hKey
0x1800e462e  xor     edx, edx
0x1800e4630  call    VpnDummySign
0x1800e4635  mov     ebx, eax
0x1800e4637  test    eax, eax
0x1800e4639  jz      loc_1800E4758
0x1800e463f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4646  cmp     rcx, r13
0x1800e4649  jz      loc_1800E475F
0x1800e464f  mov     edx, 3Ah ; ':'
0x1800e4654  jmp     loc_1800E4745
0x1800e4659  mov     ebx, 2BFh
0x1800e465e  cmp     rcx, r13
0x1800e4661  jz      loc_1800E475F
0x1800e4667  test    byte ptr [rcx+1Ch], 80h
0x1800e466b  jz      loc_1800E475F
0x1800e4671  cmp     byte ptr [rcx+19h], 2
0x1800e4675  jb      loc_1800E475F
0x1800e467b  mov     rcx, [rcx+10h]
0x1800e467f  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e4686  mov     edx, 3Bh ; ';'
0x1800e468b  call    WPP_SF_
0x1800e4690  jmp     loc_1800E4758
0x1800e4695  mov     ebx, 57h ; 'W'
0x1800e469a  cmp     rcx, r13
0x1800e469d  jz      loc_1800E4838
0x1800e46a3  lea     edx, [rbx-24h]
0x1800e46a6  mov     r9d, ebx
0x1800e46a9  jmp     loc_1800E4748
0x1800e46ae  mov     ebx, r12d
0x1800e46b1  cmp     [rdi+60h], r12
0x1800e46b5  jz      loc_1800E480F
0x1800e46bb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800e46bf  inc     rsi
0x1800e46c2  cmp     [rdi+rsi*2], r12w
0x1800e46c7  jnz     short loc_1800E46BF
0x1800e46c9  xor     r8d, r8d; dwFlags
0x1800e46cc  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x1800e46d3  lea     rcx, [rbp+phProvider]; phProvider
0x1800e46d7  call    cs:__imp_NCryptOpenStorageProvider
0x1800e46dd  mov     r14d, eax
0x1800e46e0  test    eax, eax
0x1800e46e2  jns     short loc_1800E470A
0x1800e46e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e46eb  cmp     rcx, r13
0x1800e46ee  jz      short loc_1800E475F
0x1800e46f0  mov     rcx, [rcx+10h]
0x1800e46f4  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e46fb  mov     edx, 3Ch ; '<'
0x1800e4700  mov     r9d, eax
0x1800e4703  call    WPP_SF_d
0x1800e4708  jmp     short loc_1800E4758
0x1800e470a  mov     rcx, [rbp+phProvider]; hObject
0x1800e470e  lea     r9d, ds:2[rsi*2]; cbInput
0x1800e4716  mov     r8, rdi; pbInput
0x1800e4719  mov     [rsp+40h+dwFlags], 40h ; '@'; dwFlags
0x1800e4721  lea     rdx, aPincachefreeap; "PinCacheFreeApplicationTicket"
0x1800e4728  call    cs:__imp_NCryptSetProperty
0x1800e472e  mov     ebx, eax
0x1800e4730  test    eax, eax
0x1800e4732  jz      short loc_1800E4758
0x1800e4734  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e473b  cmp     rcx, r13
0x1800e473e  jz      short loc_1800E475F
0x1800e4740  mov     edx, 3Dh ; '='
0x1800e4745  mov     r9d, eax
0x1800e4748  mov     rcx, [rcx+10h]
0x1800e474c  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e4753  call    WPP_SF_d
0x1800e4758  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e475f  mov     rax, [rbp+phProvider]
0x1800e4763  test    rax, rax
0x1800e4766  jz      short loc_1800E477C
0x1800e4768  mov     rcx, rax; hObject
0x1800e476b  call    cs:__imp_NCryptFreeObject
0x1800e4771  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4778  mov     [rbp+phProvider], r12
0x1800e477c  cmp     r15d, 1
0x1800e4780  jnz     short loc_1800E47D5
0x1800e4782  mov     rdx, [rbp+TokenHandle]; Token
0x1800e4786  xor     ecx, ecx; Thread
0x1800e4788  call    cs:__imp_SetThreadToken
0x1800e478e  test    eax, eax
0x1800e4790  jnz     short loc_1800E47CE
0x1800e4792  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e4799  cmp     rcx, r13
0x1800e479c  jz      short loc_1800E47D5
0x1800e479e  test    byte ptr [rcx+1Ch], 80h
0x1800e47a2  jz      short loc_1800E47D5
0x1800e47a4  cmp     byte ptr [rcx+19h], 3
0x1800e47a8  jb      short loc_1800E47D5
0x1800e47aa  call    cs:__imp_GetLastError
0x1800e47b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e47b7  lea     edx, [r15+3Dh]
0x1800e47bb  mov     r9d, eax
0x1800e47be  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e47c5  mov     rcx, [rcx+10h]
0x1800e47c9  call    WPP_SF_d
0x1800e47ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e47d5  mov     rax, [rbp+TokenHandle]
0x1800e47d9  test    rax, rax
0x1800e47dc  jz      short loc_1800E47EE
0x1800e47de  mov     rcx, rax; hObject
0x1800e47e1  call    cs:__imp_CloseHandle
0x1800e47e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e47ee  test    r14d, r14d
0x1800e47f1  jns     short loc_1800E480F
0x1800e47f3  test    ebx, ebx
0x1800e47f5  jnz     short loc_1800E480F
0x1800e47f7  mov     eax, r14d
0x1800e47fa  movzx   ebx, r14w
0x1800e47fe  and     eax, 1FFF0000h
0x1800e4803  cmp     eax, 70000h
0x1800e4808  jz      short loc_1800E480F
0x1800e480a  mov     ebx, 0Dh
0x1800e480f  cmp     rcx, r13
0x1800e4812  jz      short loc_1800E4838
0x1800e4814  test    byte ptr [rcx+1Ch], 80h
0x1800e4818  jz      short loc_1800E4838
0x1800e481a  cmp     byte ptr [rcx+19h], 6
0x1800e481e  jb      short loc_1800E4838
0x1800e4820  mov     rcx, [rcx+10h]
0x1800e4824  lea     r8, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e482b  mov     edx, 3Fh ; '?'
0x1800e4830  mov     r9d, ebx
0x1800e4833  call    WPP_SF_d
0x1800e4838  mov     eax, ebx
0x1800e483a  mov     rbx, [rsp+40h+arg_0]
0x1800e4842  add     rsp, 40h
0x1800e4846  pop     r15
0x1800e4848  pop     r14
0x1800e484a  pop     r13
0x1800e484c  pop     r12
0x1800e484e  pop     rdi
0x1800e484f  pop     rsi
0x1800e4850  pop     rbp
0x1800e4851  retn
```
