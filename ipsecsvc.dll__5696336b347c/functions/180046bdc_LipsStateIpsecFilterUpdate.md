# LipsStateIpsecFilterUpdate

- ea: `0x180046bdc`
- end: `0x180046dce`
- name: `LipsStateIpsecFilterUpdate`
- size: `498`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180044c20`

## callees

- `0x18000b2c8`
- `0x18000c4d0`
- `0x18000e510`
- `0x180045f1c`
- `0x18004674c`
- `0x180046bdc`
- `0x180046dd4`
- `0x180048478`
- `0x180048570`
- `0x1800486b0`

## string_xrefs

- `0x180046db3`: `LipsStateIpsecFilterUpdate`

## pseudocode

```c
__int64 __fastcall LipsStateIpsecFilterUpdate(__int64 a1, __int64 a2)
{
  unsigned int updated; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  void *v8[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v9; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v10; // [rsp+60h] [rbp+30h] BYREF
  void *v11; // [rsp+68h] [rbp+38h] BYREF

  v9 = 0;
  v10 = 0;
  v8[0] = 0;
  v11 = 0;
  if ( !a1 )
  {
    updated = 0;
    if ( !a2 )
      goto LABEL_31;
  }
  updated = LipsBfeTransactionBegin();
  if ( !updated )
  {
    if ( a1 )
    {
      updated = LipsStateIpsecFilterUpdateListCreate(a1, v8, &v9);
      if ( updated )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_30;
        v6 = 43;
        goto LABEL_29;
      }
      updated = LipsStateIpsecFilterDelete((__int64)v8[0], v9);
      if ( updated )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_30;
        v6 = 44;
        goto LABEL_29;
      }
    }
    if ( !a2 )
      goto LABEL_25;
    updated = LipsStateIpsecFilterUpdateListCreate(a2, &v11, &v10);
    if ( updated )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_30;
      v6 = 45;
      goto LABEL_29;
    }
    updated = LipsStateIpsecFilterAdd(v11, v10);
    if ( updated )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_30;
      v6 = 46;
    }
    else
    {
LABEL_25:
      updated = LipsBfeTransactionCommit();
      if ( !updated )
        goto LABEL_31;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_30;
      v6 = 47;
    }
LABEL_29:
    WPP_SF_d(v5[2], v6, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids, updated);
LABEL_30:
    LipsBfeTransactionAbort();
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids, updated);
LABEL_31:
  LipsIkePolicyProposalDestroy(&v11);
  LipsIkePolicyProposalDestroy(v8);
  if ( updated )
    return LipsReportError(updated, (int)"LipsStateIpsecFilterUpdate");
  else
    return 0;
}

```

## disassembly

```asm
0x180046bdc  mov     [rsp-18h+arg_8], rbx
0x180046be1  push    rbp
0x180046be2  push    rsi
0x180046be3  push    rdi
0x180046be4  mov     rbp, rsp
0x180046be7  sub     rsp, 30h
0x180046beb  mov     [rbp+arg_0], 0
0x180046bf2  mov     rdi, rdx
0x180046bf5  mov     [rbp+arg_10], 0
0x180046bfc  mov     rsi, rcx
0x180046bff  mov     [rbp+var_10], 0
0x180046c07  mov     [rbp+arg_18], 0
0x180046c0f  test    rcx, rcx
0x180046c12  jnz     short loc_180046C1F
0x180046c14  xor     ebx, ebx
0x180046c16  test    rdx, rdx
0x180046c19  jz      loc_180046D99
0x180046c1f  call    LipsBfeTransactionBegin
0x180046c24  mov     ebx, eax
0x180046c26  test    eax, eax
0x180046c28  jz      short loc_180046C68
0x180046c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c31  lea     rax, WPP_GLOBAL_Control
0x180046c38  cmp     rcx, rax
0x180046c3b  jz      loc_180046D99
0x180046c41  test    byte ptr [rcx+1Ch], 10h
0x180046c45  jz      loc_180046D99
0x180046c4b  mov     rcx, [rcx+10h]
0x180046c4f  lea     r8, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids
0x180046c56  mov     edx, 2Ah ; '*'
0x180046c5b  mov     r9d, ebx
0x180046c5e  call    WPP_SF_d
0x180046c63  jmp     loc_180046D99
0x180046c68  test    rsi, rsi
0x180046c6b  jz      short loc_180046CEB
0x180046c6d  lea     r8, [rbp+arg_0]
0x180046c71  mov     rcx, rsi
0x180046c74  lea     rdx, [rbp+var_10]
0x180046c78  call    LipsStateIpsecFilterUpdateListCreate
0x180046c7d  mov     ebx, eax
0x180046c7f  test    eax, eax
0x180046c81  jz      short loc_180046CAE
0x180046c83  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c8a  lea     rax, WPP_GLOBAL_Control
0x180046c91  cmp     rcx, rax
0x180046c94  jz      loc_180046D94
0x180046c9a  test    byte ptr [rcx+1Ch], 10h
0x180046c9e  jz      loc_180046D94
0x180046ca4  mov     edx, 2Bh ; '+'
0x180046ca9  jmp     loc_180046D81
0x180046cae  mov     edx, [rbp+arg_0]
0x180046cb1  mov     rcx, [rbp+var_10]
0x180046cb5  call    LipsStateIpsecFilterDelete
0x180046cba  mov     ebx, eax
0x180046cbc  test    eax, eax
0x180046cbe  jz      short loc_180046CEB
0x180046cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180046cc7  lea     rax, WPP_GLOBAL_Control
0x180046cce  cmp     rcx, rax
0x180046cd1  jz      loc_180046D94
0x180046cd7  test    byte ptr [rcx+1Ch], 10h
0x180046cdb  jz      loc_180046D94
0x180046ce1  mov     edx, 2Ch ; ','
0x180046ce6  jmp     loc_180046D81
0x180046ceb  test    rdi, rdi
0x180046cee  jz      short loc_180046D58
0x180046cf0  lea     r8, [rbp+arg_10]
0x180046cf4  mov     rcx, rdi
0x180046cf7  lea     rdx, [rbp+arg_18]
0x180046cfb  call    LipsStateIpsecFilterUpdateListCreate
0x180046d00  mov     ebx, eax
0x180046d02  test    eax, eax
0x180046d04  jz      short loc_180046D26
0x180046d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d0d  lea     rax, WPP_GLOBAL_Control
0x180046d14  cmp     rcx, rax
0x180046d17  jz      short loc_180046D94
0x180046d19  test    byte ptr [rcx+1Ch], 10h
0x180046d1d  jz      short loc_180046D94
0x180046d1f  mov     edx, 2Dh ; '-'
0x180046d24  jmp     short loc_180046D81
0x180046d26  mov     edx, [rbp+arg_10]
0x180046d29  mov     rcx, [rbp+arg_18]
0x180046d2d  call    LipsStateIpsecFilterAdd
0x180046d32  mov     ebx, eax
0x180046d34  test    eax, eax
0x180046d36  jz      short loc_180046D58
0x180046d38  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d3f  lea     rax, WPP_GLOBAL_Control
0x180046d46  cmp     rcx, rax
0x180046d49  jz      short loc_180046D94
0x180046d4b  test    byte ptr [rcx+1Ch], 10h
0x180046d4f  jz      short loc_180046D94
0x180046d51  mov     edx, 2Eh ; '.'
0x180046d56  jmp     short loc_180046D81
0x180046d58  call    LipsBfeTransactionCommit
0x180046d5d  mov     ebx, eax
0x180046d5f  test    eax, eax
0x180046d61  jz      short loc_180046D99
0x180046d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d6a  lea     rax, WPP_GLOBAL_Control
0x180046d71  cmp     rcx, rax
0x180046d74  jz      short loc_180046D94
0x180046d76  test    byte ptr [rcx+1Ch], 10h
0x180046d7a  jz      short loc_180046D94
0x180046d7c  mov     edx, 2Fh ; '/'
0x180046d81  mov     rcx, [rcx+10h]
0x180046d85  lea     r8, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids
0x180046d8c  mov     r9d, ebx
0x180046d8f  call    WPP_SF_d
0x180046d94  call    LipsBfeTransactionAbort
0x180046d99  lea     rcx, [rbp+arg_18]
0x180046d9d  call    LipsIkePolicyProposalDestroy
0x180046da2  lea     rcx, [rbp+var_10]
0x180046da6  call    LipsIkePolicyProposalDestroy
0x180046dab  test    ebx, ebx
0x180046dad  jnz     short loc_180046DB3
0x180046daf  xor     eax, eax
0x180046db1  jmp     short loc_180046DC1
0x180046db3  lea     rdx, aLipsstateipsec_7; "LipsStateIpsecFilterUpdate"
0x180046dba  mov     ecx, ebx
0x180046dbc  call    LipsReportError
0x180046dc1  mov     rbx, [rsp+30h+arg_8]
0x180046dc6  add     rsp, 30h
0x180046dca  pop     rdi
0x180046dcb  pop     rsi
0x180046dcc  pop     rbp
0x180046dcd  retn
```
