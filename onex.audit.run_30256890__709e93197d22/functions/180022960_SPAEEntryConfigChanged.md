# SPAEEntryConfigChanged

- ea: `0x180022960`
- end: `0x180022c28`
- name: `SPAEEntryConfigChanged`
- size: `712`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callees

- `0x180004710`
- `0x180005440`
- `0x180007f60`
- `0x18000cd90`
- `0x180010ae0`
- `0x180012660`
- `0x180013560`
- `0x180018d60`
- `0x1800214f0`
- `0x180022960`
- `0x18002a5d4`
- `0x18002b0f4`

## pseudocode

```c
__int64 __fastcall SPAEEntryConfigChanged(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v3; // esi
  _QWORD *v4; // rcx
  int v5; // eax
  unsigned int v6; // r14d
  __int64 v7; // rbp
  unsigned int IsEapConfigDifferent; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v13; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  v13 = 0;
  v3 = *(_DWORD *)(v1 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 89, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids);
  *(_QWORD *)(v1 + 2368) = *(_QWORD *)(a1 + 64);
  if ( !(unsigned int)MSMNotifyAuthRestarted(v1, 4) )
    goto LABEL_8;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 90, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids);
LABEL_8:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x200) != 0 )
    WPP_SF_d(v4[7], 91, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, *(unsigned int *)(v1 + 20));
LABEL_12:
  if ( (byte_18003DF41 & 0x10) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(v4, StartAuth, *(unsigned int *)(v1 + 20), 3);
  *(_QWORD *)(v1 + 28) = 1;
  *(_DWORD *)(v1 + 36) = 0;
  PortMgrSetEapError(v1, 0);
  v5 = SupplicantSetCachedCreds(v1 + 2384, 0, 0);
  if ( v5 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 92, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v3, v5);
  v6 = *(_DWORD *)(a1 + 44);
  v7 = *(_QWORD *)(a1 + 48);
  IsEapConfigDifferent = ProfileMgrIsEapConfigDifferent(*(_QWORD *)(v1 + 2744), v7, &v13);
  v9 = IsEapConfigDifferent;
  if ( !IsEapConfigDifferent )
  {
    IsEapConfigDifferent = PortMgrUpdatePortCharacterstics(v1, v6, v7, 0);
    v9 = IsEapConfigDifferent;
    if ( IsEapConfigDifferent )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v9;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_45;
      v11 = 94;
    }
    else
    {
      if ( v13 )
      {
        IsEapConfigDifferent = GenerateSupplicantEvent(v1, 28);
        v9 = IsEapConfigDifferent;
        if ( IsEapConfigDifferent )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v9;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_45;
          v11 = 95;
          goto LABEL_43;
        }
      }
      else
      {
        IsEapConfigDifferent = GenerateSupplicantEvent(v1, 25);
        v9 = IsEapConfigDifferent;
        if ( IsEapConfigDifferent )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v9;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_45;
          v11 = 96;
          goto LABEL_43;
        }
        IsEapConfigDifferent = GenerateSupplicantEvent(v1, 26);
        v9 = IsEapConfigDifferent;
        if ( IsEapConfigDifferent )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v9;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_45;
          v11 = 97;
          goto LABEL_43;
        }
      }
      IsEapConfigDifferent = GenerateSupplicantEvent(v1, 4);
      v9 = IsEapConfigDifferent;
      if ( !IsEapConfigDifferent )
      {
LABEL_44:
        v10 = WPP_GLOBAL_Control;
        goto LABEL_45;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v9;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_45;
      v11 = 98;
    }
LABEL_43:
    WPP_SF_dd(v10[7], v11, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v3, IsEapConfigDifferent);
    goto LABEL_44;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v11 = 93;
    goto LABEL_43;
  }
LABEL_45:
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
    WPP_SF_D(v10[7], 99, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180022960  push    rbx
0x180022962  push    rbp
0x180022963  push    rsi
0x180022964  push    rdi
0x180022965  push    r14
0x180022967  push    r15
0x180022969  sub     rsp, 38h
0x18002296d  mov     rdi, [rcx+18h]
0x180022971  mov     rbp, rcx
0x180022974  mov     [rsp+68h+arg_0], 0
0x18002297c  mov     esi, [rdi+14h]
0x18002297f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022986  lea     r15, WPP_GLOBAL_Control
0x18002298d  lea     rbx, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180022994  cmp     rcx, r15
0x180022997  jz      short loc_1800229B3
0x180022999  test    dword ptr [rcx+44h], 800h
0x1800229a0  jz      short loc_1800229B3
0x1800229a2  mov     rcx, [rcx+38h]
0x1800229a6  mov     edx, 59h ; 'Y'
0x1800229ab  mov     r8, rbx
0x1800229ae  call    WPP_SF_
0x1800229b3  mov     rax, [rbp+40h]
0x1800229b7  mov     edx, 4
0x1800229bc  mov     rcx, rdi
0x1800229bf  mov     [rdi+940h], rax
0x1800229c6  call    MSMNotifyAuthRestarted
0x1800229cb  test    eax, eax
0x1800229cd  jz      short loc_1800229F2
0x1800229cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229d6  cmp     rcx, r15
0x1800229d9  jz      short loc_180022A1C
0x1800229db  test    byte ptr [rcx+44h], 1
0x1800229df  jz      short loc_1800229F9
0x1800229e1  mov     rcx, [rcx+38h]
0x1800229e5  mov     edx, 5Ah ; 'Z'
0x1800229ea  mov     r8, rbx
0x1800229ed  call    WPP_SF_
0x1800229f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229f9  cmp     rcx, r15
0x1800229fc  jz      short loc_180022A1C
0x1800229fe  test    dword ptr [rcx+44h], 200h
0x180022a05  jz      short loc_180022A1C
0x180022a07  mov     r9d, [rdi+14h]
0x180022a0b  mov     edx, 5Bh ; '['
0x180022a10  mov     rcx, [rcx+38h]
0x180022a14  mov     r8, rbx
0x180022a17  call    WPP_SF_d
0x180022a1c  test    cs:byte_18003DF41, 10h
0x180022a23  jz      short loc_180022A3B
0x180022a25  mov     r8d, [rdi+14h]
0x180022a29  lea     rdx, StartAuth
0x180022a30  mov     r9d, 3
0x180022a36  call    McTemplateU0qq_EtwEventWriteTransfer
0x180022a3b  xor     edx, edx
0x180022a3d  mov     qword ptr [rdi+1Ch], 1
0x180022a45  mov     rcx, rdi
0x180022a48  mov     dword ptr [rdi+24h], 0
0x180022a4f  call    PortMgrSetEapError
0x180022a54  lea     rcx, [rdi+950h]
0x180022a5b  xor     r8d, r8d
0x180022a5e  xor     edx, edx
0x180022a60  call    SupplicantSetCachedCreds
0x180022a65  test    eax, eax
0x180022a67  jz      short loc_180022A93
0x180022a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a70  cmp     rcx, r15
0x180022a73  jz      short loc_180022A93
0x180022a75  test    byte ptr [rcx+44h], 1
0x180022a79  jz      short loc_180022A93
0x180022a7b  mov     rcx, [rcx+38h]
0x180022a7f  mov     edx, 5Ch ; '\'
0x180022a84  mov     r9d, esi
0x180022a87  mov     [rsp+68h+var_48], eax
0x180022a8b  mov     r8, rbx
0x180022a8e  call    WPP_SF_dd
0x180022a93  mov     r14d, [rbp+2Ch]
0x180022a97  lea     r8, [rsp+68h+arg_0]
0x180022a9c  mov     rbp, [rbp+30h]
0x180022aa0  mov     rcx, [rdi+0AB8h]
0x180022aa7  mov     rdx, rbp
0x180022aaa  call    ProfileMgrIsEapConfigDifferent
0x180022aaf  mov     ebx, eax
0x180022ab1  test    eax, eax
0x180022ab3  jz      short loc_180022AD9
0x180022ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x180022abc  cmp     rcx, r15
0x180022abf  jz      loc_180022C19
0x180022ac5  test    byte ptr [rcx+44h], 1
0x180022ac9  jz      loc_180022BF3
0x180022acf  mov     edx, 5Dh ; ']'
0x180022ad4  jmp     loc_180022BD5
0x180022ad9  xor     r9d, r9d
0x180022adc  mov     r8, rbp
0x180022adf  mov     edx, r14d
0x180022ae2  mov     rcx, rdi
0x180022ae5  call    PortMgrUpdatePortCharacterstics
0x180022aea  mov     ebx, eax
0x180022aec  test    eax, eax
0x180022aee  jz      short loc_180022B14
0x180022af0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022af7  cmp     rcx, r15
0x180022afa  jz      loc_180022C19
0x180022b00  test    byte ptr [rcx+44h], 1
0x180022b04  jz      loc_180022BF3
0x180022b0a  mov     edx, 5Eh ; '^'
0x180022b0f  jmp     loc_180022BD5
0x180022b14  cmp     [rsp+68h+arg_0], 0
0x180022b19  mov     rcx, rdi
0x180022b1c  jz      short loc_180022B52
0x180022b1e  mov     edx, 1Ch
0x180022b23  call    GenerateSupplicantEvent
0x180022b28  mov     ebx, eax
0x180022b2a  test    eax, eax
0x180022b2c  jz      short loc_180022BAB
0x180022b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b35  cmp     rcx, r15
0x180022b38  jz      loc_180022C19
0x180022b3e  test    byte ptr [rcx+44h], 1
0x180022b42  jz      loc_180022BF3
0x180022b48  mov     edx, 5Fh ; '_'
0x180022b4d  jmp     loc_180022BD5
0x180022b52  mov     edx, 19h
0x180022b57  call    GenerateSupplicantEvent
0x180022b5c  mov     ebx, eax
0x180022b5e  test    eax, eax
0x180022b60  jz      short loc_180022B7F
0x180022b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b69  cmp     rcx, r15
0x180022b6c  jz      loc_180022C19
0x180022b72  test    byte ptr [rcx+44h], 1
0x180022b76  jz      short loc_180022BF3
0x180022b78  mov     edx, 60h ; '`'
0x180022b7d  jmp     short loc_180022BD5
0x180022b7f  mov     edx, 1Ah
0x180022b84  mov     rcx, rdi
0x180022b87  call    GenerateSupplicantEvent
0x180022b8c  mov     ebx, eax
0x180022b8e  test    eax, eax
0x180022b90  jz      short loc_180022BAB
0x180022b92  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b99  cmp     rcx, r15
0x180022b9c  jz      short loc_180022C19
0x180022b9e  test    byte ptr [rcx+44h], 1
0x180022ba2  jz      short loc_180022BF3
0x180022ba4  mov     edx, 61h ; 'a'
0x180022ba9  jmp     short loc_180022BD5
0x180022bab  mov     edx, 4
0x180022bb0  mov     rcx, rdi
0x180022bb3  call    GenerateSupplicantEvent
0x180022bb8  mov     ebx, eax
0x180022bba  test    eax, eax
0x180022bbc  jz      short loc_180022BEC
0x180022bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bc5  cmp     rcx, r15
0x180022bc8  jz      short loc_180022C19
0x180022bca  test    byte ptr [rcx+44h], 1
0x180022bce  jz      short loc_180022BF3
0x180022bd0  mov     edx, 62h ; 'b'
0x180022bd5  mov     rcx, [rcx+38h]
0x180022bd9  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180022be0  mov     r9d, esi
0x180022be3  mov     [rsp+68h+var_48], eax
0x180022be7  call    WPP_SF_dd
0x180022bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bf3  cmp     rcx, r15
0x180022bf6  jz      short loc_180022C19
0x180022bf8  test    dword ptr [rcx+44h], 800h
0x180022bff  jz      short loc_180022C19
0x180022c01  mov     rcx, [rcx+38h]
0x180022c05  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x180022c0c  mov     edx, 63h ; 'c'
0x180022c11  mov     r9d, ebx
0x180022c14  call    WPP_SF_D
0x180022c19  mov     eax, ebx
0x180022c1b  add     rsp, 38h
0x180022c1f  pop     r15
0x180022c21  pop     r14
0x180022c23  pop     rdi
0x180022c24  pop     rsi
0x180022c25  pop     rbp
0x180022c26  pop     rbx
0x180022c27  retn
```
