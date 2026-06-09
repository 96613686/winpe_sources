# Int_FWVerifyAuthenticationSet

- ea: `0x180014cb0`
- end: `0x1800150d0`
- name: `Int_FWVerifyAuthenticationSet`
- size: `1056`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c420`

## callees

- `0x18000bfd0`
- `0x18000ccd4`
- `0x180010f20`
- `0x180013690`
- `0x180014cb0`
- `0x1800169f0`
- `0x180017044`
- `0x180017d1c`
- `0x18002f38c`

## string_xrefs

- `0x180014f0e`: `MPSSVC.dll`

## pseudocode

```c
__int64 __fastcall Int_FWVerifyAuthenticationSet(__int64 a1, __int64 a2, enum _tag_FW_RULE_STATUS *a3)
{
  __int64 v5; // r9
  unsigned int v6; // esi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  struct _tag_FW_AUTH_SUITE *v13; // rdx
  _WORD *v15; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  *(_DWORD *)a3 = 0x10000;
  v15 = 0;
  if ( *(_WORD *)(a2 + 8) < 0x200u )
  {
    v5 = 87;
    *(_DWORD *)a3 = 1069136;
    v6 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 158;
LABEL_66:
      WPP_SF_d(v7[2], v8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v5);
      return v6;
    }
    return v6;
  }
  if ( *(_WORD *)(a2 + 8) >= 0x300u )
    *(_DWORD *)a3 = 0x40000;
  v9 = Int_FwValidateComplianceAndReduceAuthSetToVersion(a2, a3, *(unsigned __int16 *)(a2 + 8));
  v6 = v9;
  if ( !v9 )
  {
    if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 16), 0, 1u, 0xFFu) )
    {
      v5 = 87;
      *(_DWORD *)a3 = 524296;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 160;
        goto LABEL_66;
      }
      return v6;
    }
    if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 24), 1, 0, 0x2710u) )
    {
      v5 = 87;
      *(_DWORD *)a3 = 524289;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 161;
        goto LABEL_66;
      }
      return v6;
    }
    if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 32), 1, 0, 0x2710u) )
    {
      v5 = 87;
      *(_DWORD *)a3 = 524290;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 162;
        goto LABEL_66;
      }
      return v6;
    }
    if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 40), 1, 0, 0x2710u) )
    {
      v5 = 87;
      *(_DWORD *)a3 = 524295;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 163;
        goto LABEL_66;
      }
      return v6;
    }
    v10 = *(unsigned int *)(a2 + 12);
    if ( (unsigned int)(v10 - 1) > 1 )
    {
      v5 = 87;
      *(_DWORD *)a3 = 1052688;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 164;
        goto LABEL_66;
      }
      return v6;
    }
    if ( (_DWORD)v10 == 1 )
    {
      if ( (unsigned int)FwFieldNameMatchStringBegining(
                           L"{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE3}",
                           *(_QWORD *)(a2 + 16),
                           &v15) == 1
        && *v15 )
      {
        v5 = 87;
        *(_DWORD *)a3 = 524296;
        v6 = 87;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 165;
          goto LABEL_66;
        }
      }
      else
      {
        v12 = *(_DWORD *)(a2 + 48);
        if ( v12 && (v13 = *(struct _tag_FW_AUTH_SUITE **)(a2 + 56)) != 0 )
        {
          if ( (unsigned int)Int_FwValidatePhase1AuthSuites(v12, v13, a3, *(_WORD *)(a2 + 8)) )
          {
            v5 = 87;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 167;
              goto LABEL_66;
            }
          }
        }
        else
        {
          v5 = 87;
          *(_DWORD *)a3 = 1052704;
          v6 = 87;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 166;
            goto LABEL_66;
          }
        }
      }
      return v6;
    }
    if ( (_DWORD)v10 != 2 )
    {
      MicrosoftTelemetryAssertTriggeredArgs("MPSSVC.dll", v10, 0);
      return v6;
    }
    if ( (unsigned int)FwFieldNameMatchStringBegining(
                         L"{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE4}",
                         *(_QWORD *)(a2 + 16),
                         &v15) == 1
      && *v15 )
    {
      v5 = 87;
      *(_DWORD *)a3 = 524296;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 168;
        goto LABEL_66;
      }
      return v6;
    }
    v11 = *(_DWORD *)(a2 + 48);
    if ( v11 )
    {
      if ( *(_QWORD *)(a2 + 56) )
      {
LABEL_44:
        if ( (unsigned int)Int_FwValidatePhase2AuthSuites(
                             v11,
                             *(struct _tag_FW_AUTH_SUITE **)(a2 + 56),
                             a3,
                             *(_WORD *)(a2 + 8)) )
        {
          v5 = 87;
          v6 = 87;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 170;
            goto LABEL_66;
          }
        }
        return v6;
      }
    }
    else if ( !*(_QWORD *)(a2 + 56) )
    {
      goto LABEL_44;
    }
    v5 = 87;
    *(_DWORD *)a3 = 1052704;
    v6 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 169;
      goto LABEL_66;
    }
    return v6;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 159;
    v5 = v9;
    goto LABEL_66;
  }
  return v6;
}

```

## disassembly

```asm
0x180014cb0  mov     [rsp+arg_0], rbx
0x180014cb5  mov     [rsp+arg_10], rbp
0x180014cba  push    rsi
0x180014cbb  push    rdi
0x180014cbc  push    r12
0x180014cbe  push    r14
0x180014cc0  push    r15
0x180014cc2  sub     rsp, 20h
0x180014cc6  mov     rdi, r8
0x180014cc9  mov     rbp, rdx
0x180014ccc  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cd3  lea     r14, WPP_GLOBAL_Control
0x180014cda  lea     r12, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180014ce1  cmp     rcx, r14
0x180014ce4  jz      short loc_180014CFD
0x180014ce6  test    byte ptr [rcx+1Ch], 8
0x180014cea  jz      short loc_180014CFD
0x180014cec  mov     rcx, [rcx+10h]
0x180014cf0  mov     edx, 9Dh
0x180014cf5  mov     r8, r12
0x180014cf8  call    WPP_SF_
0x180014cfd  xor     r15d, r15d
0x180014d00  mov     dword ptr [rdi], 10000h
0x180014d06  mov     eax, 200h
0x180014d0b  mov     [rsp+48h+arg_8], r15
0x180014d10  cmp     [rbp+8], ax
0x180014d14  jnb     short loc_180014D49
0x180014d16  lea     r9d, [r15+57h]
0x180014d1a  mov     dword ptr [rdi], 105050h
0x180014d20  mov     esi, r9d
0x180014d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d2a  cmp     rcx, r14
0x180014d2d  jz      loc_1800150B7
0x180014d33  lea     ebx, [r15+1]
0x180014d37  test    [rcx+1Ch], bl
0x180014d3a  jz      loc_1800150B7
0x180014d40  lea     edx, [r9+47h]
0x180014d44  jmp     loc_1800150AB
0x180014d49  mov     eax, 300h
0x180014d4e  cmp     [rbp+8], ax
0x180014d52  jb      short loc_180014D5A
0x180014d54  mov     dword ptr [rdi], 40000h
0x180014d5a  movzx   r8d, word ptr [rbp+8]
0x180014d5f  mov     rdx, rdi
0x180014d62  mov     rcx, rbp
0x180014d65  call    Int_FwValidateComplianceAndReduceAuthSetToVersion
0x180014d6a  mov     esi, eax
0x180014d6c  test    eax, eax
0x180014d6e  jz      short loc_180014D9B
0x180014d70  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d77  cmp     rcx, r14
0x180014d7a  jz      loc_1800150B7
0x180014d80  mov     ebx, 1
0x180014d85  test    [rcx+1Ch], bl
0x180014d88  jz      loc_1800150B7
0x180014d8e  mov     edx, 9Fh
0x180014d93  mov     r9d, eax
0x180014d96  jmp     loc_1800150AB
0x180014d9b  mov     rcx, [rbp+10h]; Str
0x180014d9f  mov     ebx, 1
0x180014da4  mov     r8d, ebx
0x180014da7  mov     r9d, 0FFh
0x180014dad  xor     edx, edx
0x180014daf  call    Int_FwValidateString
0x180014db4  test    eax, eax
0x180014db6  jz      short loc_180014DE7
0x180014db8  lea     r9d, [rbx+56h]
0x180014dbc  mov     dword ptr [rdi], 80008h
0x180014dc2  mov     esi, r9d
0x180014dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dcc  cmp     rcx, r14
0x180014dcf  jz      loc_1800150B7
0x180014dd5  test    [rcx+1Ch], bl
0x180014dd8  jz      loc_1800150B7
0x180014dde  lea     edx, [r9+49h]
0x180014de2  jmp     loc_1800150AB
0x180014de7  mov     rcx, [rbp+18h]; Str
0x180014deb  mov     r9d, 2710h
0x180014df1  xor     r8d, r8d
0x180014df4  mov     edx, ebx
0x180014df6  call    Int_FwValidateString
0x180014dfb  test    eax, eax
0x180014dfd  jz      short loc_180014E30
0x180014dff  mov     r9d, 57h ; 'W'
0x180014e05  mov     dword ptr [rdi], 80001h
0x180014e0b  mov     esi, r9d
0x180014e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e15  cmp     rcx, r14
0x180014e18  jz      loc_1800150B7
0x180014e1e  test    [rcx+1Ch], bl
0x180014e21  jz      loc_1800150B7
0x180014e27  lea     edx, [r9+4Ah]
0x180014e2b  jmp     loc_1800150AB
0x180014e30  mov     rcx, [rbp+20h]; Str
0x180014e34  mov     r9d, 2710h
0x180014e3a  xor     r8d, r8d
0x180014e3d  mov     edx, ebx
0x180014e3f  call    Int_FwValidateString
0x180014e44  test    eax, eax
0x180014e46  jz      short loc_180014E79
0x180014e48  mov     r9d, 57h ; 'W'
0x180014e4e  mov     dword ptr [rdi], 80002h
0x180014e54  mov     esi, r9d
0x180014e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e5e  cmp     rcx, r14
0x180014e61  jz      loc_1800150B7
0x180014e67  test    [rcx+1Ch], bl
0x180014e6a  jz      loc_1800150B7
0x180014e70  lea     edx, [r9+4Bh]
0x180014e74  jmp     loc_1800150AB
0x180014e79  mov     rcx, [rbp+28h]; Str
0x180014e7d  mov     r9d, 2710h
0x180014e83  xor     r8d, r8d
0x180014e86  mov     edx, ebx
0x180014e88  call    Int_FwValidateString
0x180014e8d  test    eax, eax
0x180014e8f  jz      short loc_180014EC2
0x180014e91  mov     r9d, 57h ; 'W'
0x180014e97  mov     dword ptr [rdi], 80007h
0x180014e9d  mov     esi, r9d
0x180014ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ea7  cmp     rcx, r14
0x180014eaa  jz      loc_1800150B7
0x180014eb0  test    [rcx+1Ch], bl
0x180014eb3  jz      loc_1800150B7
0x180014eb9  lea     edx, [r9+4Ch]
0x180014ebd  jmp     loc_1800150AB
0x180014ec2  mov     edx, [rbp+0Ch]
0x180014ec5  lea     eax, [rdx-1]
0x180014ec8  cmp     eax, ebx
0x180014eca  jbe     short loc_180014EFD
0x180014ecc  mov     r9d, 57h ; 'W'
0x180014ed2  mov     dword ptr [rdi], 101010h
0x180014ed8  mov     esi, r9d
0x180014edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ee2  cmp     rcx, r14
0x180014ee5  jz      loc_1800150B7
0x180014eeb  test    [rcx+1Ch], bl
0x180014eee  jz      loc_1800150B7
0x180014ef4  lea     edx, [r9+4Dh]
0x180014ef8  jmp     loc_1800150AB
0x180014efd  mov     ecx, edx
0x180014eff  sub     ecx, ebx
0x180014f01  jz      loc_180014FFC
0x180014f07  cmp     ecx, ebx
0x180014f09  jz      short loc_180014F1F
0x180014f0b  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "FALSE", "Invalid pAuthSet->IpSecPhase")
0x180014f0e  lea     rcx, aMpssvcDll; "MPSSVC.dll"
0x180014f15  call    MicrosoftTelemetryAssertTriggeredArgs
0x180014f1a  jmp     loc_1800150B7
0x180014f1f  mov     rdx, [rbp+10h]
0x180014f23  lea     r8, [rsp+48h+arg_8]
0x180014f28  lea     rcx, aE5a5d32a4bce4e; "{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE4}"
0x180014f2f  call    FwFieldNameMatchStringBegining
0x180014f34  cmp     eax, ebx
0x180014f36  jnz     short loc_180014F74
0x180014f38  mov     rax, [rsp+48h+arg_8]
0x180014f3d  cmp     [rax], r15w
0x180014f41  jz      short loc_180014F74
0x180014f43  mov     r9d, 57h ; 'W'
0x180014f49  mov     dword ptr [rdi], 80008h
0x180014f4f  mov     esi, r9d
0x180014f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f59  cmp     rcx, r14
0x180014f5c  jz      loc_1800150B7
0x180014f62  test    [rcx+1Ch], bl
0x180014f65  jz      loc_1800150B7
0x180014f6b  lea     edx, [r9+51h]
0x180014f6f  jmp     loc_1800150AB
0x180014f74  mov     ecx, [rbp+30h]; unsigned int
0x180014f77  test    ecx, ecx
0x180014f79  jz      short loc_180014FC5
0x180014f7b  cmp     [rbp+38h], r15
0x180014f7f  jz      short loc_180014FCB
0x180014f81  movzx   r9d, word ptr [rbp+8]
0x180014f86  mov     r8, rdi; enum _tag_FW_RULE_STATUS *
0x180014f89  mov     rdx, [rbp+38h]; struct _tag_FW_AUTH_SUITE *
0x180014f8d  call    Int_FwValidatePhase2AuthSuites
0x180014f92  test    eax, eax
0x180014f94  jz      loc_1800150B7
0x180014f9a  mov     r9d, 57h ; 'W'
0x180014fa0  mov     esi, r9d
0x180014fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014faa  cmp     rcx, r14
0x180014fad  jz      loc_1800150B7
0x180014fb3  test    [rcx+1Ch], bl
0x180014fb6  jz      loc_1800150B7
0x180014fbc  lea     edx, [r9+53h]
0x180014fc0  jmp     loc_1800150AB
0x180014fc5  cmp     [rbp+38h], r15
0x180014fc9  jz      short loc_180014F81
0x180014fcb  mov     r9d, 57h ; 'W'
0x180014fd1  mov     dword ptr [rdi], 101020h
0x180014fd7  mov     esi, r9d
0x180014fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fe1  cmp     rcx, r14
0x180014fe4  jz      loc_1800150B7
0x180014fea  test    [rcx+1Ch], bl
0x180014fed  jz      loc_1800150B7
0x180014ff3  lea     edx, [r9+52h]
0x180014ff7  jmp     loc_1800150AB
0x180014ffc  mov     rdx, [rbp+10h]
0x180015000  lea     r8, [rsp+48h+arg_8]
0x180015005  lea     rcx, aE5a5d32a4bce4e_1; "{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE3}"
0x18001500c  call    FwFieldNameMatchStringBegining
0x180015011  cmp     eax, ebx
0x180015013  jnz     short loc_180015046
0x180015015  mov     rax, [rsp+48h+arg_8]
0x18001501a  cmp     [rax], r15w
0x18001501e  jz      short loc_180015046
0x180015020  mov     r9d, 57h ; 'W'
0x180015026  mov     dword ptr [rdi], 80008h
0x18001502c  mov     esi, r9d
0x18001502f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015036  cmp     rcx, r14
0x180015039  jz      short loc_1800150B7
0x18001503b  test    [rcx+1Ch], bl
0x18001503e  jz      short loc_1800150B7
0x180015040  lea     edx, [r9+4Eh]
0x180015044  jmp     short loc_1800150AB
0x180015046  mov     ecx, [rbp+30h]; unsigned int
0x180015049  test    ecx, ecx
0x18001504b  jz      short loc_180015087
0x18001504d  mov     rdx, [rbp+38h]; struct _tag_FW_AUTH_SUITE *
0x180015051  test    rdx, rdx
0x180015054  jz      short loc_180015087
0x180015056  movzx   r9d, word ptr [rbp+8]
0x18001505b  mov     r8, rdi; enum _tag_FW_RULE_STATUS *
0x18001505e  call    Int_FwValidatePhase1AuthSuites
0x180015063  test    eax, eax
0x180015065  jz      short loc_1800150B7
0x180015067  mov     r9d, 57h ; 'W'
0x18001506d  mov     esi, r9d
0x180015070  mov     rcx, cs:WPP_GLOBAL_Control
0x180015077  cmp     rcx, r14
0x18001507a  jz      short loc_1800150B7
0x18001507c  test    [rcx+1Ch], bl
0x18001507f  jz      short loc_1800150B7
0x180015081  lea     edx, [r9+50h]
0x180015085  jmp     short loc_1800150AB
0x180015087  mov     r9d, 57h ; 'W'
0x18001508d  mov     dword ptr [rdi], 101020h
0x180015093  mov     esi, r9d
0x180015096  mov     rcx, cs:WPP_GLOBAL_Control
0x18001509d  cmp     rcx, r14
0x1800150a0  jz      short loc_1800150B7
0x1800150a2  test    [rcx+1Ch], bl
0x1800150a5  jz      short loc_1800150B7
0x1800150a7  lea     edx, [r9+4Fh]
0x1800150ab  mov     rcx, [rcx+10h]
0x1800150af  mov     r8, r12
0x1800150b2  call    WPP_SF_d
0x1800150b7  mov     rbx, [rsp+48h+arg_0]
0x1800150bc  mov     eax, esi
0x1800150be  mov     rbp, [rsp+48h+arg_10]
0x1800150c3  add     rsp, 20h
0x1800150c7  pop     r15
0x1800150c9  pop     r14
0x1800150cb  pop     r12
0x1800150cd  pop     rdi
0x1800150ce  pop     rsi
0x1800150cf  retn
```
