# Int_FwValidatePhase1AuthSuites

- ea: `0x1800169f0`
- end: `0x18001703d`
- name: `Int_FwValidatePhase1AuthSuites`
- size: `1613`
- prototype: `__int64 __fastcall(unsigned int, struct _tag_FW_AUTH_SUITE *, enum _tag_FW_RULE_STATUS *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014cb0`

## callees

- `0x18000ccd4`
- `0x180010f20`
- `0x180014028`
- `0x18001476c`
- `0x180014b6c`
- `0x1800169f0`
- `0x180017d1c`
- `0x18001e1d0`
- `0x18002d930`
- `0x18002daf4`
- `0x18002f38c`
- `0x18002f43c`

## string_xrefs

- `0x180016b1e`: `MPSSVC.dll`

## pseudocode

```c
__int64 __fastcall Int_FwValidatePhase1AuthSuites(
        unsigned int a1,
        struct _tag_FW_AUTH_SUITE *a2,
        enum _tag_FW_RULE_STATUS *a3,
        __int16 a4)
{
  unsigned int v7; // ebx
  int v8; // r13d
  int v9; // ebp
  unsigned int v10; // r15d
  unsigned int *v11; // rsi
  struct _tag_FW_CERT_CRITERIA *v12; // rcx
  int v13; // edx
  int v14; // eax
  __int64 v15; // r9
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  unsigned __int16 v21; // [rsp+34h] [rbp-84h] BYREF
  int v22; // [rsp+38h] [rbp-80h] BYREF
  int v23; // [rsp+3Ch] [rbp-7Ch]
  int v24; // [rsp+40h] [rbp-78h]
  int v25; // [rsp+44h] [rbp-74h]
  _OWORD v26[3]; // [rsp+48h] [rbp-70h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 382, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  v25 = 0;
  v7 = 0;
  v23 = 0;
  v8 = 0;
  v24 = 0;
  v9 = 0;
  v22 = 0;
  v21 = 0;
  memset(v26, 0, 44);
  if ( !a1 || !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v10 = 0;
  if ( !a1 )
  {
LABEL_55:
    if ( !(unsigned int)Int_FwCertSelectionValidationCrossSuiteValid(a1, a2) )
    {
      v15 = 87;
      *(_DWORD *)a3 = 1052793;
      v7 = 87;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 397;
        goto LABEL_104;
      }
      return v7;
    }
    if ( !v8 )
      return v7;
    if ( !v25 )
      return v7;
    v15 = 87;
    *(_DWORD *)a3 = 1052720;
    v7 = 87;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v17 = 398;
    goto LABEL_104;
  }
  while ( 1 )
  {
    v11 = (unsigned int *)((char *)a2 + 24 * v10);
    switch ( *v11 )
    {
      case 1u:
        goto LABEL_41;
      case 2u:
LABEL_46:
        v7 = Int_FwValidateKerbAuthSuite((struct _tag_FW_AUTH_SUITE *)((char *)a2 + 24 * v10), a3);
        if ( v7 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v7;
          v17 = 394;
LABEL_71:
          v15 = v7;
          goto LABEL_104;
        }
        goto LABEL_43;
      case 4u:
        goto LABEL_40;
    }
    if ( *v11 != 5 )
    {
      if ( *v11 == 3 )
        goto LABEL_21;
      if ( *v11 != 9 )
      {
        v15 = 87;
        *(_DWORD *)a3 = 1052720;
        v7 = 87;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 383;
          goto LABEL_104;
        }
        return v7;
      }
      switch ( *v11 )
      {
        case 1u:
          goto LABEL_41;
        case 2u:
          goto LABEL_46;
        case 3u:
LABEL_21:
          if ( (unsigned int)Int_FwValidateString(*((wchar_t **)v11 + 1), 0, 1u, 0x2710u) )
          {
            v15 = 87;
            *(_DWORD *)a3 = 1052752;
            v7 = 87;
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v17 = 390;
              goto LABEL_104;
            }
            return v7;
          }
          if ( *((_WORD *)v11 + 2) )
          {
            v15 = 87;
            *(_DWORD *)a3 = 1052736;
            v7 = 87;
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v17 = 391;
              goto LABEL_104;
            }
            return v7;
          }
          v8 = 1;
          goto LABEL_43;
        case 4u:
          goto LABEL_40;
      }
      if ( *v11 != 5 )
      {
        if ( *v11 != 9 )
        {
          MicrosoftTelemetryAssertTriggeredArgs("MPSSVC.dll", *v11, 0);
          goto LABEL_43;
        }
LABEL_40:
        v25 = 1;
LABEL_41:
        if ( *((_WORD *)v11 + 2) )
        {
          v15 = 87;
          *(_DWORD *)a3 = 1052736;
          v7 = 87;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v7;
          v17 = 392;
        }
        else
        {
          if ( !*((_QWORD *)v11 + 1) )
            goto LABEL_43;
          v15 = 87;
          *(_DWORD *)a3 = 3670016;
          v7 = 87;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v7;
          v17 = 393;
        }
LABEL_104:
        WPP_SF_d(v16[2], v17, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v15);
        return v7;
      }
    }
    if ( (v11[1] & 0x3F) != *((_WORD *)v11 + 2) )
    {
      v15 = 87;
      *(_DWORD *)a3 = 1052736;
      v7 = 87;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 384;
        goto LABEL_104;
      }
      return v7;
    }
    v7 = Int_FwValidateCAName(*((LPCWSTR *)v11 + 1), a3);
    if ( v7 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v17 = 385;
      goto LABEL_71;
    }
    v12 = (struct _tag_FW_CERT_CRITERIA *)*((_QWORD *)v11 + 2);
    if ( v12 )
    {
      if ( *(_WORD *)v12 != a4 )
      {
        v15 = 87;
        *(_DWORD *)a3 = 1052786;
        v7 = 87;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 386;
          goto LABEL_104;
        }
        return v7;
      }
      v7 = Int_FwValidateCertificateCriteria(v12, a3);
      if ( v7 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v17 = 387;
        goto LABEL_71;
      }
    }
    v7 = Int_FwValidateCrossSuiteSigning(a2, v10, &v21, a3, &v22);
    if ( v7 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v17 = 388;
      goto LABEL_71;
    }
    if ( v22 == 1 )
    {
      v13 = 0;
      v22 = 0;
      v14 = 0;
      v24 = 0;
      v23 = 0;
    }
    else
    {
      v14 = v23;
      v13 = v24;
    }
    if ( (v11[1] & 2) != 0 )
    {
      v23 = 1;
    }
    else
    {
      v13 = 1;
      v24 = 1;
      if ( !v14 )
        goto LABEL_43;
    }
    if ( v13 )
    {
      v15 = 87;
      *(_DWORD *)a3 = 1052769;
      v7 = 87;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 389;
        goto LABEL_104;
      }
      return v7;
    }
LABEL_43:
    if ( *v11 == 1 )
    {
      if ( v9 == 1 )
      {
        v15 = 87;
        *(_DWORD *)a3 = 1052722;
        v7 = 87;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 395;
          goto LABEL_104;
        }
        return v7;
      }
      v9 = 1;
    }
    else if ( *v11 != 2 && *v11 != 4 && *v11 != 3 && *v11 != 9 )
    {
      goto LABEL_54;
    }
    v18 = (int)*v11;
    if ( *((_DWORD *)v26 + v18) == 1 )
      break;
    *((_DWORD *)v26 + v18) = 1;
LABEL_54:
    if ( ++v10 >= a1 )
      goto LABEL_55;
  }
  v15 = 87;
  *(_DWORD *)a3 = 1052723;
  v7 = 87;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = 396;
    goto LABEL_104;
  }
  return v7;
}

```

## disassembly

```asm
0x1800169f0  mov     [rsp+arg_0], rbx
0x1800169f5  push    rbp
0x1800169f6  push    rsi
0x1800169f7  push    rdi
0x1800169f8  push    r12
0x1800169fa  push    r13
0x1800169fc  push    r14
0x1800169fe  push    r15
0x180016a00  sub     rsp, 80h
0x180016a07  mov     rax, cs:__security_cookie
0x180016a0e  xor     rax, rsp
0x180016a11  mov     [rsp+0B8h+var_40], rax
0x180016a16  mov     [rsp+0B8h+var_88], r9w
0x180016a1c  mov     rdi, r8
0x180016a1f  mov     r12, rdx
0x180016a22  mov     r14d, ecx
0x180016a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a2c  lea     rsi, WPP_GLOBAL_Control
0x180016a33  cmp     rcx, rsi
0x180016a36  jz      short loc_180016A53
0x180016a38  test    byte ptr [rcx+1Ch], 8
0x180016a3c  jz      short loc_180016A53
0x180016a3e  mov     rcx, [rcx+10h]
0x180016a42  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180016a49  mov     edx, 17Eh
0x180016a4e  call    WPP_SF_
0x180016a53  xor     r9d, r9d
0x180016a56  xorps   xmm0, xmm0
0x180016a59  mov     [rsp+0B8h+var_74], r9d
0x180016a5e  mov     ebx, r9d
0x180016a61  mov     [rsp+0B8h+var_7C], r9d
0x180016a66  mov     r13d, r9d
0x180016a69  mov     [rsp+0B8h+var_78], r9d
0x180016a6e  mov     ebp, r9d
0x180016a71  mov     [rsp+0B8h+var_80], r9d
0x180016a76  mov     [rsp+0B8h+var_84], r9w
0x180016a7c  movups  xmmword ptr [rsp+0B8h+var_60], xmm0
0x180016a81  movups  xmmword ptr [rsp+0B8h+var_60+0Ch], xmm0
0x180016a86  movups  [rsp+0B8h+var_70], xmm0
0x180016a8b  test    r14d, r14d
0x180016a8e  jz      short loc_180016A95
0x180016a90  test    r12, r12
0x180016a93  jnz     short loc_180016A9D
0x180016a95  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwNumSuites > 0 && pSuites != NULL")
0x180016a9a  xor     r9d, r9d
0x180016a9d  mov     r15d, r9d
0x180016aa0  mov     r8d, 1
0x180016aa6  test    r14d, r14d
0x180016aa9  jz      loc_180016CEC
0x180016aaf  mov     eax, r15d
0x180016ab2  lea     rcx, [rax+rax*2]
0x180016ab6  lea     rsi, [r12+rcx*8]
0x180016aba  cmp     [rsi], r8d
0x180016abd  jz      loc_180016C6C
0x180016ac3  cmp     dword ptr [rsi], 2
0x180016ac6  jz      loc_180016C94
0x180016acc  cmp     dword ptr [rsi], 4
0x180016acf  jz      loc_180016C67
0x180016ad5  cmp     dword ptr [rsi], 5
0x180016ad8  jz      loc_180016B6E
0x180016ade  cmp     dword ptr [rsi], 3
0x180016ae1  jz      short loc_180016B3B
0x180016ae3  cmp     dword ptr [rsi], 9
0x180016ae6  jnz     loc_180016D32
0x180016aec  mov     ecx, [rsi]
0x180016aee  sub     ecx, 1
0x180016af1  jz      loc_180016C6C
0x180016af7  sub     ecx, 1
0x180016afa  jz      loc_180016C94
0x180016b00  sub     ecx, 1
0x180016b03  jz      short loc_180016B3B
0x180016b05  sub     ecx, 1
0x180016b08  jz      loc_180016C67
0x180016b0e  sub     ecx, 1
0x180016b11  jz      short loc_180016B6E
0x180016b13  cmp     ecx, 4
0x180016b16  jz      loc_180016C67
0x180016b1c  mov     edx, [rsi]; __annotation("Debug", "TelemetryAssert", "FALSE", "Invalid pSuites[dwIndex].Method")
0x180016b1e  lea     rcx, aMpssvcDll; "MPSSVC.dll"
0x180016b25  xor     r8d, r8d
0x180016b28  call    MicrosoftTelemetryAssertTriggeredArgs
0x180016b2d  mov     r8d, 1
0x180016b33  xor     r9d, r9d
0x180016b36  jmp     loc_180016C81
0x180016b3b  mov     rcx, [rsi+8]; Str
0x180016b3f  xor     edx, edx
0x180016b41  mov     r9d, 2710h
0x180016b47  call    Int_FwValidateString
0x180016b4c  xor     r9d, r9d
0x180016b4f  test    eax, eax
0x180016b51  jnz     loc_180016DA6
0x180016b57  cmp     [rsi+4], r9w
0x180016b5c  jnz     loc_180016D6C
0x180016b62  lea     r8d, [r9+1]
0x180016b66  mov     r13d, r8d
0x180016b69  jmp     loc_180016C81
0x180016b6e  movzx   eax, word ptr [rsi+4]
0x180016b72  and     ax, 3Fh
0x180016b76  cmp     ax, [rsi+4]
0x180016b7a  jnz     loc_180016E9B
0x180016b80  mov     rcx, [rsi+8]; pszX500
0x180016b84  mov     rdx, rdi; enum _tag_FW_RULE_STATUS *
0x180016b87  call    ?Int_FwValidateCAName@@YAKPEAGPEAW4_tag_FW_RULE_STATUS@@@Z; Int_FwValidateCAName(ushort *,_tag_FW_RULE_STATUS *)
0x180016b8c  mov     ebx, eax
0x180016b8e  test    eax, eax
0x180016b90  jnz     loc_180016E70
0x180016b96  mov     rcx, [rsi+10h]; struct _tag_FW_CERT_CRITERIA *
0x180016b9a  test    rcx, rcx
0x180016b9d  jz      short loc_180016BBF
0x180016b9f  movzx   eax, [rsp+0B8h+var_88]
0x180016ba4  cmp     [rcx], ax
0x180016ba7  jnz     loc_180016E0E
0x180016bad  mov     rdx, rdi; enum _tag_FW_RULE_STATUS *
0x180016bb0  call    ?Int_FwValidateCertificateCriteria@@YAKPEAU_tag_FW_CERT_CRITERIA@@PEAW4_tag_FW_RULE_STATUS@@@Z; Int_FwValidateCertificateCriteria(_tag_FW_CERT_CRITERIA *,_tag_FW_RULE_STATUS *)
0x180016bb5  mov     ebx, eax
0x180016bb7  test    eax, eax
0x180016bb9  jnz     loc_180016DE0
0x180016bbf  lea     rax, [rsp+0B8h+var_80]
0x180016bc4  mov     r9, rdi; enum _tag_FW_RULE_STATUS *
0x180016bc7  lea     r8, [rsp+0B8h+var_84]; unsigned __int16 *
0x180016bcc  mov     [rsp+0B8h+var_98], rax; int *
0x180016bd1  mov     edx, r15d; unsigned int
0x180016bd4  mov     rcx, r12; struct _tag_FW_AUTH_SUITE *
0x180016bd7  call    ?Int_FwValidateCrossSuiteSigning@@YAKPEAU_tag_FW_AUTH_SUITE@@KPEAGPEAW4_tag_FW_RULE_STATUS@@PEAH@Z; Int_FwValidateCrossSuiteSigning(_tag_FW_AUTH_SUITE *,ulong,ushort *,_tag_FW_RULE_STATUS *,int *)
0x180016bdc  xor     r9d, r9d
0x180016bdf  mov     ebx, eax
0x180016be1  test    eax, eax
0x180016be3  jnz     loc_180016E48
0x180016be9  lea     r8d, [rax+1]
0x180016bed  cmp     [rsp+0B8h+var_80], r8d
0x180016bf2  jnz     short loc_180016C09
0x180016bf4  mov     edx, r9d
0x180016bf7  mov     [rsp+0B8h+var_80], r9d
0x180016bfc  mov     eax, r9d
0x180016bff  mov     [rsp+0B8h+var_78], edx
0x180016c03  mov     [rsp+0B8h+var_7C], eax
0x180016c07  jmp     short loc_180016C11
0x180016c09  mov     eax, [rsp+0B8h+var_7C]
0x180016c0d  mov     edx, [rsp+0B8h+var_78]
0x180016c11  test    byte ptr [rsi+4], 2
0x180016c15  jz      short loc_180016C1E
0x180016c17  mov     [rsp+0B8h+var_7C], r8d
0x180016c1c  jmp     short loc_180016C29
0x180016c1e  mov     edx, r8d
0x180016c21  mov     [rsp+0B8h+var_78], edx
0x180016c25  test    eax, eax
0x180016c27  jz      short loc_180016C81
0x180016c29  test    edx, edx
0x180016c2b  jz      short loc_180016C81
0x180016c2d  mov     r9d, 57h ; 'W'
0x180016c33  mov     dword ptr [rdi], 101061h
0x180016c39  mov     ebx, r9d
0x180016c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c43  lea     rax, WPP_GLOBAL_Control
0x180016c4a  cmp     rcx, rax
0x180016c4d  jz      loc_180017013
0x180016c53  test    [rcx+1Ch], r8b
0x180016c57  jz      loc_180017013
0x180016c5d  mov     edx, 185h
0x180016c62  jmp     loc_180017003
0x180016c67  mov     [rsp+0B8h+var_74], r8d
0x180016c6c  cmp     [rsi+4], r9w
0x180016c71  jnz     loc_180016FA3
0x180016c77  cmp     [rsi+8], r9
0x180016c7b  jnz     loc_180016F74
0x180016c81  cmp     [rsi], r8d
0x180016c84  jnz     short loc_180016CB2
0x180016c86  cmp     ebp, r8d
0x180016c89  jz      loc_180016F00
0x180016c8f  mov     ebp, r8d
0x180016c92  jmp     short loc_180016CC6
0x180016c94  mov     rdx, rdi; enum _tag_FW_RULE_STATUS *
0x180016c97  mov     rcx, rsi; struct _tag_FW_AUTH_SUITE *
0x180016c9a  call    ?Int_FwValidateKerbAuthSuite@@YAKPEBU_tag_FW_AUTH_SUITE@@PEAW4_tag_FW_RULE_STATUS@@@Z; Int_FwValidateKerbAuthSuite(_tag_FW_AUTH_SUITE const *,_tag_FW_RULE_STATUS *)
0x180016c9f  xor     r9d, r9d
0x180016ca2  mov     ebx, eax
0x180016ca4  test    eax, eax
0x180016ca6  jnz     loc_180016ED5
0x180016cac  lea     r8d, [rax+1]
0x180016cb0  jmp     short loc_180016C81
0x180016cb2  cmp     dword ptr [rsi], 2
0x180016cb5  jz      short loc_180016CC6
0x180016cb7  cmp     dword ptr [rsi], 4
0x180016cba  jz      short loc_180016CC6
0x180016cbc  cmp     dword ptr [rsi], 3
0x180016cbf  jz      short loc_180016CC6
0x180016cc1  cmp     dword ptr [rsi], 9
0x180016cc4  jnz     short loc_180016CD9
0x180016cc6  movsxd  rax, dword ptr [rsi]
0x180016cc9  cmp     dword ptr [rsp+rax*4+0B8h+var_70], r8d
0x180016cce  jz      loc_180016F3A
0x180016cd4  mov     dword ptr [rsp+rax*4+0B8h+var_70], r8d
0x180016cd9  add     r15d, r8d
0x180016cdc  cmp     r15d, r14d
0x180016cdf  jb      loc_180016AAF
0x180016ce5  lea     rsi, WPP_GLOBAL_Control
0x180016cec  mov     rdx, r12; struct _tag_FW_AUTH_SUITE *
0x180016cef  mov     ecx, r14d; unsigned int
0x180016cf2  call    ?Int_FwCertSelectionValidationCrossSuiteValid@@YAHKPEAU_tag_FW_AUTH_SUITE@@@Z; Int_FwCertSelectionValidationCrossSuiteValid(ulong,_tag_FW_AUTH_SUITE *)
0x180016cf7  xor     ecx, ecx
0x180016cf9  test    eax, eax
0x180016cfb  jnz     loc_180016FD2
0x180016d01  lea     r9d, [rcx+57h]
0x180016d05  mov     dword ptr [rdi], 101079h
0x180016d0b  mov     ebx, r9d
0x180016d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d15  cmp     rcx, rsi
0x180016d18  jz      loc_180017013
0x180016d1e  test    byte ptr [rcx+1Ch], 1
0x180016d22  jz      loc_180017013
0x180016d28  mov     edx, 18Dh
0x180016d2d  jmp     loc_180017003
0x180016d32  mov     r9d, 57h ; 'W'
0x180016d38  mov     dword ptr [rdi], 101030h
0x180016d3e  mov     ebx, r9d
0x180016d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d48  lea     rax, WPP_GLOBAL_Control
0x180016d4f  cmp     rcx, rax
0x180016d52  jz      loc_180017013
0x180016d58  test    [rcx+1Ch], r8b
0x180016d5c  jz      loc_180017013
0x180016d62  mov     edx, 17Fh
0x180016d67  jmp     loc_180017003
0x180016d6c  mov     r9d, 57h ; 'W'
0x180016d72  mov     dword ptr [rdi], 101040h
0x180016d78  mov     ebx, r9d
0x180016d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d82  lea     rax, WPP_GLOBAL_Control
0x180016d89  cmp     rcx, rax
0x180016d8c  jz      loc_180017013
0x180016d92  test    byte ptr [rcx+1Ch], 1
0x180016d96  jz      loc_180017013
0x180016d9c  mov     edx, 187h
0x180016da1  jmp     loc_180017003
0x180016da6  mov     r9d, 57h ; 'W'
0x180016dac  mov     dword ptr [rdi], 101050h
0x180016db2  mov     ebx, r9d
0x180016db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016dbc  lea     rax, WPP_GLOBAL_Control
0x180016dc3  cmp     rcx, rax
0x180016dc6  jz      loc_180017013
0x180016dcc  test    byte ptr [rcx+1Ch], 1
0x180016dd0  jz      loc_180017013
0x180016dd6  mov     edx, 186h
0x180016ddb  jmp     loc_180017003
0x180016de0  mov     rcx, cs:WPP_GLOBAL_Control
0x180016de7  lea     rax, WPP_GLOBAL_Control
0x180016dee  cmp     rcx, rax
0x180016df1  jz      loc_180017013
0x180016df7  test    byte ptr [rcx+1Ch], 1
0x180016dfb  jz      loc_180017013
0x180016e01  mov     edx, 183h
0x180016e06  mov     r9d, ebx
0x180016e09  jmp     loc_180017003
0x180016e0e  mov     r9d, 57h ; 'W'
0x180016e14  mov     dword ptr [rdi], 101072h
0x180016e1a  mov     ebx, r9d
0x180016e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e24  lea     rax, WPP_GLOBAL_Control
0x180016e2b  cmp     rcx, rax
0x180016e2e  jz      loc_180017013
0x180016e34  test    byte ptr [rcx+1Ch], 1
0x180016e38  jz      loc_180017013
0x180016e3e  mov     edx, 182h
0x180016e43  jmp     loc_180017003
0x180016e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e4f  lea     rax, WPP_GLOBAL_Control
0x180016e56  cmp     rcx, rax
0x180016e59  jz      loc_180017013
0x180016e5f  test    byte ptr [rcx+1Ch], 1
0x180016e63  jz      loc_180017013
0x180016e69  mov     edx, 184h
0x180016e6e  jmp     short loc_180016E06
0x180016e70  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e77  lea     rax, WPP_GLOBAL_Control
0x180016e7e  cmp     rcx, rax
0x180016e81  jz      loc_180017013
0x180016e87  test    byte ptr [rcx+1Ch], 1
0x180016e8b  jz      loc_180017013
0x180016e91  mov     edx, 181h
0x180016e96  jmp     loc_180016E06
0x180016e9b  mov     r9d, 57h ; 'W'
0x180016ea1  mov     dword ptr [rdi], 101040h
0x180016ea7  mov     ebx, r9d
0x180016eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180016eb1  lea     rax, WPP_GLOBAL_Control
0x180016eb8  cmp     rcx, rax
0x180016ebb  jz      loc_180017013
0x180016ec1  test    [rcx+1Ch], r8b
0x180016ec5  jz      loc_180017013
0x180016ecb  mov     edx, 180h
0x180016ed0  jmp     loc_180017003
0x180016ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016edc  lea     rax, WPP_GLOBAL_Control
0x180016ee3  cmp     rcx, rax
0x180016ee6  jz      loc_180017013
0x180016eec  test    byte ptr [rcx+1Ch], 1
0x180016ef0  jz      loc_180017013
0x180016ef6  mov     edx, 18Ah
0x180016efb  jmp     loc_180016E06
  ... truncated ...
```
