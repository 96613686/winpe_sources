# IdentifyAndSetupOneXUser

- ea: `0x180001ac0`
- end: `0x18000200e`
- name: `IdentifyAndSetupOneXUser`
- size: `1358`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180001510`

## callees

- `0x180001ac0`
- `0x180002470`
- `0x180002f64`
- `0x180005440`
- `0x180007f60`
- `0x18000c4c0`
- `0x18000c5a0`
- `0x18000cd90`
- `0x180019300`
- `0x18001d108`
- `0x18001de08`
- `0x180020ce0`
- `0x180020de4`
- `0x1800214f0`
- `0x18002275c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001dc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001dc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e45`
- `MobileNetworking!FreeMemory` at `0x180001ddb`
- `MobileNetworking!FreeMemory` at `0x180001df2`
- `MobileNetworking!FreeMemory` at `0x180001e09`
- `MobileNetworking!FreeMemory` at `0x180001e74`
- `MobileNetworking!FreeMemory` at `0x180001eae`
- `MobileNetworking!FreeMemory` at `0x180001ee1`
- `MobileNetworking!FreeMemory` at `0x180001ddb`
- `MobileNetworking!FreeMemory` at `0x180001df2`
- `MobileNetworking!FreeMemory` at `0x180001e09`
- `MobileNetworking!FreeMemory` at `0x180001e74`
- `MobileNetworking!FreeMemory` at `0x180001eae`
- `MobileNetworking!FreeMemory` at `0x180001ee1`

## string_xrefs

- `0x180001e66`: `SetUserTokenInfo`

## pseudocode

```c
__int64 __fastcall IdentifyAndSetupOneXUser(__int64 a1)
{
  _DWORD *v1; // r14
  __int64 v2; // rdi
  unsigned int v4; // r12d
  int v5; // r15d
  int v6; // esi
  __int64 v7; // r9
  unsigned int v8; // eax
  int v9; // ecx
  unsigned int SupplicantEvent; // esi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // r13d
  int v14; // edx
  void *v15; // rcx
  __int64 v16; // r13
  HANDLE v17; // r15
  PSID *v18; // rax
  bool v19; // zf
  int v20; // r8d
  _QWORD *v21; // rcx
  __int64 v23; // [rsp+40h] [rbp-38h] BYREF
  PSID *v24; // [rsp+48h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-28h] BYREF
  int v26; // [rsp+B0h] [rbp+38h] BYREF
  PSID *v27; // [rsp+B8h] [rbp+40h] BYREF
  __int64 v28; // [rsp+C0h] [rbp+48h] BYREF
  __int64 v29; // [rsp+C8h] [rbp+50h] BYREF

  v1 = *(_DWORD **)a1;
  LODWORD(v2) = 5;
  hObject = 0;
  LODWORD(v27) = 5;
  LODWORD(v28) = 0;
  v4 = v1[5];
  v24 = 0;
  v23 = 0;
  v29 = 0;
  v26 = -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 59, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids);
  if ( !(unsigned __int8)IsWTSQueryUserTokenPresent() && !(unsigned __int8)IsQueryUserTokenPresent() )
  {
    v26 = 0;
    LODWORD(v2) = 2;
    v5 = 13;
    goto LABEL_32;
  }
  v6 = IdentifyOneXCredentialsToUse(a1, (unsigned int)&v27, (unsigned int)&hObject, (unsigned int)&v24, (__int64)&v26);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 60, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v4, v6);
    v1[9] = v6;
    v5 = 12;
    v1[8] = 327681;
LABEL_32:
    SupplicantEvent = GenerateSupplicantEvent((__int64)v1, 27);
    if ( SupplicantEvent )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_41;
      v12 = 65;
LABEL_40:
      WPP_SF_dd(v11[7], v12, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v4, SupplicantEvent);
LABEL_41:
      if ( hObject )
        CloseHandle(hObject);
      FreeMemory(&v24, "IdentifyAndSetupOneXUser", 1050);
      FreeMemory(&v23, "IdentifyAndSetupOneXUser", 1051);
      FreeMemory(&v29, "IdentifyAndSetupOneXUser", 1052);
      goto LABEL_61;
    }
    goto LABEL_36;
  }
  v2 = (int)v27;
  v8 = CompareOneXCredentials(a1, (int)v27, v24, v7, (int *)&v28);
  SupplicantEvent = v8;
  if ( v8 )
  {
    if ( (byte_18003DF41 & 1) != 0 )
      McTemplateU0qqq_EtwEventWriteTransfer(v9, (unsigned int)CompareOneXCredentialsFailed, v8, 988, v4);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_41;
    v12 = 61;
    goto LABEL_40;
  }
  v13 = v28;
  if ( (_DWORD)v28
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      62,
      (unsigned int)WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids,
      v4,
      (__int64)c_AuthIdentityDescription[v2]);
  }
  if ( (_DWORD)v2 == 2 )
  {
    SupplicantEvent = GetUserAndDomainName(v4, v24, (LPWSTR *)&v23, &v29);
    if ( SupplicantEvent )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_41;
      v12 = 63;
      goto LABEL_40;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
      WPP_SF_dSS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        64,
        (unsigned int)WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids,
        v4,
        v23,
        v29);
  }
  else
  {
    v23 = 0;
    v29 = 0;
  }
  v5 = 13;
  if ( v13 )
    goto LABEL_32;
LABEL_36:
  SupplicantEvent = GenerateSupplicantEvent((__int64)v1, v5);
  if ( SupplicantEvent )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_41;
    v12 = 66;
    goto LABEL_40;
  }
  v15 = *(void **)(a1 + 456);
  v16 = v29;
  v17 = hObject;
  v28 = v23;
  v18 = v24;
  v27 = v24;
  *(_DWORD *)(a1 + 444) = v2;
  if ( v15 )
  {
    CloseHandle(v15);
    v18 = v27;
  }
  v19 = *(_QWORD *)(a1 + 464) == 0;
  *(_QWORD *)(a1 + 456) = v17;
  if ( !v19 )
  {
    FreeMemory(a1 + 464, "SetUserTokenInfo", 147);
    v18 = v27;
  }
  v19 = *(_QWORD *)(a1 + 472) == 0;
  v20 = v26;
  *(_DWORD *)(a1 + 448) = v26;
  *(_QWORD *)(a1 + 464) = v18;
  if ( !v19 )
  {
    FreeMemory(a1 + 472, "SetUserName", 156);
    v20 = v26;
  }
  v19 = *(_QWORD *)(a1 + 480) == 0;
  *(_QWORD *)(a1 + 472) = v28;
  if ( !v19 )
  {
    FreeMemory(a1 + 480, "SetDomainName", 170);
    v20 = v26;
  }
  *(_QWORD *)(a1 + 480) = v16;
  if ( (_DWORD)v2 != 5 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x200) != 0 )
    {
      WPP_SF_dSdSS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        v2,
        v20,
        v1[5],
        (__int64)c_AuthIdentityDescription[(int)v2],
        v20,
        v23,
        v29);
      v21 = WPP_GLOBAL_Control;
      LOBYTE(v20) = v26;
    }
    if ( (byte_18003DF41 & 0x10) == 0 )
      goto LABEL_62;
    McTemplateU0qzqzz_EtwEventWriteTransfer(
      (_DWORD)v21,
      v14,
      v1[5],
      (unsigned int)c_AuthIdentityDescription[(int)v2],
      v20,
      v23,
      v29);
    goto LABEL_61;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return SupplicantEvent;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x200) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 68, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v4, 0);
LABEL_61:
    v21 = WPP_GLOBAL_Control;
  }
LABEL_62:
  if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 17) & 0x800) != 0 )
    WPP_SF_D(v21[7], 69, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, SupplicantEvent);
  return SupplicantEvent;
}

```

## disassembly

```asm
0x180001ac0  push    rbp
0x180001ac2  push    rbx
0x180001ac3  push    rdi
0x180001ac4  push    r12
0x180001ac6  push    r14
0x180001ac8  push    r15
0x180001aca  mov     rbp, rsp
0x180001acd  sub     rsp, 78h
0x180001ad1  mov     r14, [rcx]
0x180001ad4  xor     r15d, r15d
0x180001ad7  mov     edi, 5
0x180001adc  mov     [rbp+hObject], r15
0x180001ae0  mov     rbx, rcx
0x180001ae3  mov     dword ptr [rbp+arg_8], edi
0x180001ae6  mov     dword ptr [rbp+arg_10], r15d
0x180001aea  mov     r12d, [r14+14h]
0x180001aee  mov     [rbp+var_30], r15
0x180001af2  mov     [rbp+var_38], r15
0x180001af6  mov     [rbp+arg_18], r15
0x180001afa  mov     [rbp+arg_0], 0FFFFFFFFh
0x180001b01  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b08  lea     rax, WPP_GLOBAL_Control
0x180001b0f  cmp     rcx, rax
0x180001b12  jz      short loc_180001B32
0x180001b14  test    dword ptr [rcx+44h], 800h
0x180001b1b  jz      short loc_180001B32
0x180001b1d  mov     rcx, [rcx+38h]
0x180001b21  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180001b28  mov     edx, 3Bh ; ';'
0x180001b2d  call    WPP_SF_
0x180001b32  mov     [rsp+78h+var_8], rsi
0x180001b37  mov     [rsp+78h+var_10], r13
0x180001b3c  call    IsWTSQueryUserTokenPresent
0x180001b41  test    al, al
0x180001b43  jnz     short loc_180001B62
0x180001b45  call    IsQueryUserTokenPresent
0x180001b4a  test    al, al
0x180001b4c  jnz     short loc_180001B62
0x180001b4e  mov     [rbp+arg_0], r15d
0x180001b52  mov     edi, 2
0x180001b57  mov     r15d, 0Dh
0x180001b5d  jmp     loc_180001D36
0x180001b62  lea     rax, [rbp+arg_0]
0x180001b66  mov     rcx, rbx
0x180001b69  lea     r9, [rbp+var_30]
0x180001b6d  mov     [rsp+78h+var_58], rax
0x180001b72  lea     r8, [rbp+hObject]
0x180001b76  lea     rdx, [rbp+arg_8]
0x180001b7a  call    IdentifyOneXCredentialsToUse
0x180001b7f  mov     esi, eax
0x180001b81  test    eax, eax
0x180001b83  jz      short loc_180001BD1
0x180001b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b8c  lea     rax, WPP_GLOBAL_Control
0x180001b93  cmp     rcx, rax
0x180001b96  jz      short loc_180001BBA
0x180001b98  test    byte ptr [rcx+44h], 8
0x180001b9c  jz      short loc_180001BBA
0x180001b9e  mov     rcx, [rcx+38h]
0x180001ba2  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180001ba9  mov     edx, 3Ch ; '<'
0x180001bae  mov     dword ptr [rsp+78h+var_58], esi
0x180001bb2  mov     r9d, r12d
0x180001bb5  call    WPP_SF_dd
0x180001bba  mov     [r14+24h], esi
0x180001bbe  mov     r15d, 0Ch
0x180001bc4  mov     dword ptr [r14+20h], 50001h
0x180001bcc  jmp     loc_180001D30
0x180001bd1  movsxd  rdi, dword ptr [rbp+arg_8]
0x180001bd5  lea     rax, [rbp+arg_10]
0x180001bd9  mov     r8, [rbp+var_30]
0x180001bdd  mov     edx, edi
0x180001bdf  mov     rcx, rbx
0x180001be2  mov     [rsp+78h+var_58], rax
0x180001be7  call    CompareOneXCredentials
0x180001bec  mov     esi, eax
0x180001bee  test    eax, eax
0x180001bf0  jz      short loc_180001C40
0x180001bf2  test    cs:byte_18003DF41, 1
0x180001bf9  jz      short loc_180001C15
0x180001bfb  mov     r9d, 3DCh
0x180001c01  mov     dword ptr [rsp+78h+var_58], r12d
0x180001c06  mov     r8d, eax
0x180001c09  lea     rdx, CompareOneXCredentialsFailed
0x180001c10  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180001c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c1c  lea     rax, WPP_GLOBAL_Control
0x180001c23  cmp     rcx, rax
0x180001c26  jz      loc_180001DBB
0x180001c2c  test    byte ptr [rcx+44h], 1
0x180001c30  jz      loc_180001DBB
0x180001c36  mov     edx, 3Dh ; '='
0x180001c3b  jmp     loc_180001DA4
0x180001c40  mov     r13d, dword ptr [rbp+arg_10]
0x180001c44  lea     r8, c_AuthIdentityDescription
0x180001c4b  test    r13d, r13d
0x180001c4e  jz      short loc_180001C8A
0x180001c50  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c57  lea     rax, WPP_GLOBAL_Control
0x180001c5e  cmp     rcx, rax
0x180001c61  jz      short loc_180001C8A
0x180001c63  test    byte ptr [rcx+44h], 8
0x180001c67  jz      short loc_180001C8A
0x180001c69  mov     rax, [r8+rdi*8]
0x180001c6d  mov     edx, 3Eh ; '>'
0x180001c72  mov     rcx, [rcx+38h]
0x180001c76  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180001c7d  mov     r9d, r12d
0x180001c80  mov     [rsp+78h+var_58], rax
0x180001c85  call    WPP_SF_dS
0x180001c8a  cmp     edi, 2
0x180001c8d  jnz     loc_180001D1D
0x180001c93  mov     rdx, [rbp+var_30]
0x180001c97  lea     r9, [rbp+arg_18]
0x180001c9b  lea     r8, [rbp+var_38]
0x180001c9f  mov     ecx, r12d
0x180001ca2  call    GetUserAndDomainName
0x180001ca7  mov     esi, eax
0x180001ca9  test    eax, eax
0x180001cab  jz      short loc_180001CD8
0x180001cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cb4  lea     rax, WPP_GLOBAL_Control
0x180001cbb  cmp     rcx, rax
0x180001cbe  jz      loc_180001DBB
0x180001cc4  test    byte ptr [rcx+44h], 1
0x180001cc8  jz      loc_180001DBB
0x180001cce  mov     edx, 3Fh ; '?'
0x180001cd3  jmp     loc_180001DA4
0x180001cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cdf  lea     rax, WPP_GLOBAL_Control
0x180001ce6  cmp     rcx, rax
0x180001ce9  jz      short loc_180001D25
0x180001ceb  test    byte ptr [rcx+44h], 8
0x180001cef  jz      short loc_180001D25
0x180001cf1  mov     rax, [rbp+arg_18]
0x180001cf5  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180001cfc  mov     rcx, [rcx+38h]
0x180001d00  mov     edx, 40h ; '@'
0x180001d05  mov     [rsp+78h+var_50], rax
0x180001d0a  mov     r9d, r12d
0x180001d0d  mov     rax, [rbp+var_38]
0x180001d11  mov     [rsp+78h+var_58], rax
0x180001d16  call    WPP_SF_dSS
0x180001d1b  jmp     short loc_180001D25
0x180001d1d  mov     [rbp+var_38], r15
0x180001d21  mov     [rbp+arg_18], r15
0x180001d25  mov     r15d, 0Dh
0x180001d2b  test    r13d, r13d
0x180001d2e  jz      short loc_180001D69
0x180001d30  mov     eax, [rbp+arg_0]
0x180001d33  mov     [rbp+arg_0], eax
0x180001d36  mov     edx, 1Bh
0x180001d3b  mov     rcx, r14
0x180001d3e  call    GenerateSupplicantEvent
0x180001d43  mov     esi, eax
0x180001d45  test    eax, eax
0x180001d47  jz      short loc_180001D71
0x180001d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d50  lea     rax, WPP_GLOBAL_Control
0x180001d57  cmp     rcx, rax
0x180001d5a  jz      short loc_180001DBB
0x180001d5c  test    byte ptr [rcx+44h], 1
0x180001d60  jz      short loc_180001DBB
0x180001d62  mov     edx, 41h ; 'A'
0x180001d67  jmp     short loc_180001DA4
0x180001d69  mov     r13d, [rbp+arg_0]
0x180001d6d  mov     [rbp+arg_0], r13d
0x180001d71  mov     edx, r15d
0x180001d74  mov     rcx, r14
0x180001d77  call    GenerateSupplicantEvent
0x180001d7c  mov     esi, eax
0x180001d7e  test    eax, eax
0x180001d80  jz      loc_180001E1B
0x180001d86  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d8d  lea     rax, WPP_GLOBAL_Control
0x180001d94  cmp     rcx, rax
0x180001d97  jz      short loc_180001DBB
0x180001d99  test    byte ptr [rcx+44h], 1
0x180001d9d  jz      short loc_180001DBB
0x180001d9f  mov     edx, 42h ; 'B'
0x180001da4  mov     rcx, [rcx+38h]
0x180001da8  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180001daf  mov     r9d, r12d
0x180001db2  mov     dword ptr [rsp+78h+var_58], esi
0x180001db6  call    WPP_SF_dd
0x180001dbb  mov     rcx, [rbp+hObject]; hObject
0x180001dbf  test    rcx, rcx
0x180001dc2  jz      short loc_180001DCA
0x180001dc4  call    cs:__imp_CloseHandle
0x180001dca  mov     r8d, 41Ah
0x180001dd0  lea     rdx, aIdentifyandset; "IdentifyAndSetupOneXUser"
0x180001dd7  lea     rcx, [rbp+var_30]
0x180001ddb  call    cs:__imp_FreeMemory
0x180001de1  mov     r8d, 41Bh
0x180001de7  lea     rdx, aIdentifyandset; "IdentifyAndSetupOneXUser"
0x180001dee  lea     rcx, [rbp+var_38]
0x180001df2  call    cs:__imp_FreeMemory
0x180001df8  mov     r8d, 41Ch
0x180001dfe  lea     rdx, aIdentifyandset; "IdentifyAndSetupOneXUser"
0x180001e05  lea     rcx, [rbp+arg_18]
0x180001e09  call    cs:__imp_FreeMemory
0x180001e0f  lea     r15, WPP_GLOBAL_Control
0x180001e16  jmp     loc_180001FC7
0x180001e1b  mov     rax, [rbp+var_38]
0x180001e1f  mov     rcx, [rbx+1C8h]; hObject
0x180001e26  mov     r13, [rbp+arg_18]
0x180001e2a  mov     r15, [rbp+hObject]
0x180001e2e  mov     [rbp+arg_10], rax
0x180001e32  mov     rax, [rbp+var_30]
0x180001e36  mov     [rbp+arg_8], rax
0x180001e3a  mov     [rbx+1BCh], edi
0x180001e40  test    rcx, rcx
0x180001e43  jz      short loc_180001E4F
0x180001e45  call    cs:__imp_CloseHandle
0x180001e4b  mov     rax, [rbp+arg_8]
0x180001e4f  cmp     qword ptr [rbx+1D0h], 0
0x180001e57  mov     [rbx+1C8h], r15
0x180001e5e  jz      short loc_180001E7E
0x180001e60  mov     r8d, 93h
0x180001e66  lea     rdx, aSetusertokenin; "SetUserTokenInfo"
0x180001e6d  lea     rcx, [rbx+1D0h]
0x180001e74  call    cs:__imp_FreeMemory
0x180001e7a  mov     rax, [rbp+arg_8]
0x180001e7e  cmp     qword ptr [rbx+1D8h], 0
0x180001e86  mov     r8d, [rbp+arg_0]
0x180001e8a  mov     [rbx+1C0h], r8d
0x180001e91  mov     [rbx+1D0h], rax
0x180001e98  jz      short loc_180001EB8
0x180001e9a  mov     r8d, 9Ch
0x180001ea0  lea     rdx, aSetusername; "SetUserName"
0x180001ea7  lea     rcx, [rbx+1D8h]
0x180001eae  call    cs:__imp_FreeMemory
0x180001eb4  mov     r8d, [rbp+arg_0]
0x180001eb8  cmp     qword ptr [rbx+1E0h], 0
0x180001ec0  mov     rax, [rbp+arg_10]
0x180001ec4  mov     [rbx+1D8h], rax
0x180001ecb  jz      short loc_180001EEB
0x180001ecd  mov     r8d, 0AAh
0x180001ed3  lea     rdx, aSetdomainname; "SetDomainName"
0x180001eda  lea     rcx, [rbx+1E0h]
0x180001ee1  call    cs:__imp_FreeMemory
0x180001ee7  mov     r8d, [rbp+arg_0]
0x180001eeb  mov     [rbx+1E0h], r13
0x180001ef2  cmp     edi, 5
0x180001ef5  jz      loc_180001F8B
0x180001efb  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f02  lea     r15, WPP_GLOBAL_Control
0x180001f09  lea     rbx, c_AuthIdentityDescription
0x180001f10  cmp     rcx, r15
0x180001f13  jz      short loc_180001F59
0x180001f15  test    dword ptr [rcx+44h], 200h
0x180001f1c  jz      short loc_180001F59
0x180001f1e  mov     rax, [rbp+arg_18]
0x180001f22  mov     r9d, [r14+14h]
0x180001f26  mov     rcx, [rcx+38h]
0x180001f2a  mov     [rsp+78h+var_40], rax
0x180001f2f  mov     rax, [rbp+var_38]
0x180001f33  mov     [rsp+78h+var_48], rax
0x180001f38  movsxd  rdx, edi
0x180001f3b  mov     dword ptr [rsp+78h+var_50], r8d
0x180001f40  mov     rax, [rbx+rdx*8]
0x180001f44  mov     [rsp+78h+var_58], rax
0x180001f49  call    WPP_SF_dSdSS
0x180001f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f55  mov     r8d, [rbp+arg_0]
0x180001f59  test    cs:byte_18003DF41, 10h
0x180001f60  jz      short loc_180001FCE
0x180001f62  mov     rax, [rbp+arg_18]
0x180001f66  mov     [rsp+78h+var_48], rax
0x180001f6b  mov     rax, [rbp+var_38]
0x180001f6f  mov     [rsp+78h+var_50], rax
0x180001f74  mov     dword ptr [rsp+78h+var_58], r8d
0x180001f79  mov     r8d, [r14+14h]
0x180001f7d  movsxd  r9, edi
0x180001f80  mov     r9, [rbx+r9*8]
0x180001f84  call    McTemplateU0qzqzz_EtwEventWriteTransfer
0x180001f89  jmp     short loc_180001FC7
0x180001f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f92  lea     r15, WPP_GLOBAL_Control
0x180001f99  cmp     rcx, r15
0x180001f9c  jz      short loc_180001FF4
0x180001f9e  test    dword ptr [rcx+44h], 200h
0x180001fa5  jz      short loc_180001FCE
0x180001fa7  mov     rcx, [rcx+38h]
0x180001fab  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180001fb2  mov     edx, 44h ; 'D'
0x180001fb7  mov     dword ptr [rsp+78h+var_58], 0
0x180001fbf  mov     r9d, r12d
0x180001fc2  call    WPP_SF_dd
0x180001fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fce  cmp     rcx, r15
0x180001fd1  jz      short loc_180001FF4
0x180001fd3  test    dword ptr [rcx+44h], 800h
0x180001fda  jz      short loc_180001FF4
0x180001fdc  mov     rcx, [rcx+38h]
0x180001fe0  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180001fe7  mov     edx, 45h ; 'E'
0x180001fec  mov     r9d, esi
0x180001fef  call    WPP_SF_D
0x180001ff4  mov     r13, [rsp+78h+var_10]
  ... truncated ...
```
