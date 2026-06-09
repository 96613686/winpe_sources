# LipsStateIkeFilterUpdate

- ea: `0x180045c1c`
- end: `0x180045e0e`
- name: `LipsStateIkeFilterUpdate`
- size: `498`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180044928`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x180045344`
- `0x180045808`
- `0x180045c1c`
- `0x180045e14`
- `0x180045f1c`
- `0x180048478`
- `0x180048570`
- `0x1800486b0`

## string_xrefs

- `0x180045df3`: `LipsStateIkeFilterUpdate`

## pseudocode

```c
__int64 __fastcall LipsStateIkeFilterUpdate(__int64 a1, __int64 a2)
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
      updated = LipsStateIkeFilterUpdateListCreate(a1, v8, &v9);
      if ( updated )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_30;
        v6 = 31;
        goto LABEL_29;
      }
      updated = LipsStateIkeFilterDelete((__int64)v8[0], v9);
      if ( updated )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_30;
        v6 = 32;
        goto LABEL_29;
      }
    }
    if ( !a2 )
      goto LABEL_25;
    updated = LipsStateIkeFilterUpdateListCreate(a2, &v11, &v10);
    if ( updated )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_30;
      v6 = 33;
      goto LABEL_29;
    }
    updated = LipsStateIkeFilterAdd(v11, v10);
    if ( updated )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_30;
      v6 = 34;
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
      v6 = 35;
    }
LABEL_29:
    WPP_SF_d(v5[2], v6, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids, updated);
LABEL_30:
    LipsBfeTransactionAbort();
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids, updated);
LABEL_31:
  LipsIkePolicyProposalDestroy(&v11);
  LipsIkePolicyProposalDestroy(v8);
  if ( updated )
    return LipsReportError(updated, (int)"LipsStateIkeFilterUpdate");
  else
    return 0;
}

```

## disassembly

```asm
0x180045c1c  mov     [rsp-18h+arg_8], rbx
0x180045c21  push    rbp
0x180045c22  push    rsi
0x180045c23  push    rdi
0x180045c24  mov     rbp, rsp
0x180045c27  sub     rsp, 30h
0x180045c2b  mov     [rbp+arg_0], 0
0x180045c32  mov     rdi, rdx
0x180045c35  mov     [rbp+arg_10], 0
0x180045c3c  mov     rsi, rcx
0x180045c3f  mov     [rbp+var_10], 0
0x180045c47  mov     [rbp+arg_18], 0
0x180045c4f  test    rcx, rcx
0x180045c52  jnz     short loc_180045C5F
0x180045c54  xor     ebx, ebx
0x180045c56  test    rdx, rdx
0x180045c59  jz      loc_180045DD9
0x180045c5f  call    LipsBfeTransactionBegin
0x180045c64  mov     ebx, eax
0x180045c66  test    eax, eax
0x180045c68  jz      short loc_180045CA8
0x180045c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c71  lea     rax, WPP_GLOBAL_Control
0x180045c78  cmp     rcx, rax
0x180045c7b  jz      loc_180045DD9
0x180045c81  test    byte ptr [rcx+1Ch], 10h
0x180045c85  jz      loc_180045DD9
0x180045c8b  mov     rcx, [rcx+10h]
0x180045c8f  lea     r8, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids
0x180045c96  mov     edx, 1Eh
0x180045c9b  mov     r9d, ebx
0x180045c9e  call    WPP_SF_d
0x180045ca3  jmp     loc_180045DD9
0x180045ca8  test    rsi, rsi
0x180045cab  jz      short loc_180045D2B
0x180045cad  lea     r8, [rbp+arg_0]
0x180045cb1  mov     rcx, rsi
0x180045cb4  lea     rdx, [rbp+var_10]
0x180045cb8  call    LipsStateIkeFilterUpdateListCreate
0x180045cbd  mov     ebx, eax
0x180045cbf  test    eax, eax
0x180045cc1  jz      short loc_180045CEE
0x180045cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180045cca  lea     rax, WPP_GLOBAL_Control
0x180045cd1  cmp     rcx, rax
0x180045cd4  jz      loc_180045DD4
0x180045cda  test    byte ptr [rcx+1Ch], 10h
0x180045cde  jz      loc_180045DD4
0x180045ce4  mov     edx, 1Fh
0x180045ce9  jmp     loc_180045DC1
0x180045cee  mov     edx, [rbp+arg_0]
0x180045cf1  mov     rcx, [rbp+var_10]
0x180045cf5  call    LipsStateIkeFilterDelete
0x180045cfa  mov     ebx, eax
0x180045cfc  test    eax, eax
0x180045cfe  jz      short loc_180045D2B
0x180045d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d07  lea     rax, WPP_GLOBAL_Control
0x180045d0e  cmp     rcx, rax
0x180045d11  jz      loc_180045DD4
0x180045d17  test    byte ptr [rcx+1Ch], 10h
0x180045d1b  jz      loc_180045DD4
0x180045d21  mov     edx, 20h ; ' '
0x180045d26  jmp     loc_180045DC1
0x180045d2b  test    rdi, rdi
0x180045d2e  jz      short loc_180045D98
0x180045d30  lea     r8, [rbp+arg_10]
0x180045d34  mov     rcx, rdi
0x180045d37  lea     rdx, [rbp+arg_18]
0x180045d3b  call    LipsStateIkeFilterUpdateListCreate
0x180045d40  mov     ebx, eax
0x180045d42  test    eax, eax
0x180045d44  jz      short loc_180045D66
0x180045d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d4d  lea     rax, WPP_GLOBAL_Control
0x180045d54  cmp     rcx, rax
0x180045d57  jz      short loc_180045DD4
0x180045d59  test    byte ptr [rcx+1Ch], 10h
0x180045d5d  jz      short loc_180045DD4
0x180045d5f  mov     edx, 21h ; '!'
0x180045d64  jmp     short loc_180045DC1
0x180045d66  mov     edx, [rbp+arg_10]
0x180045d69  mov     rcx, [rbp+arg_18]
0x180045d6d  call    LipsStateIkeFilterAdd
0x180045d72  mov     ebx, eax
0x180045d74  test    eax, eax
0x180045d76  jz      short loc_180045D98
0x180045d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d7f  lea     rax, WPP_GLOBAL_Control
0x180045d86  cmp     rcx, rax
0x180045d89  jz      short loc_180045DD4
0x180045d8b  test    byte ptr [rcx+1Ch], 10h
0x180045d8f  jz      short loc_180045DD4
0x180045d91  mov     edx, 22h ; '"'
0x180045d96  jmp     short loc_180045DC1
0x180045d98  call    LipsBfeTransactionCommit
0x180045d9d  mov     ebx, eax
0x180045d9f  test    eax, eax
0x180045da1  jz      short loc_180045DD9
0x180045da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180045daa  lea     rax, WPP_GLOBAL_Control
0x180045db1  cmp     rcx, rax
0x180045db4  jz      short loc_180045DD4
0x180045db6  test    byte ptr [rcx+1Ch], 10h
0x180045dba  jz      short loc_180045DD4
0x180045dbc  mov     edx, 23h ; '#'
0x180045dc1  mov     rcx, [rcx+10h]
0x180045dc5  lea     r8, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids
0x180045dcc  mov     r9d, ebx
0x180045dcf  call    WPP_SF_d
0x180045dd4  call    LipsBfeTransactionAbort
0x180045dd9  lea     rcx, [rbp+arg_18]
0x180045ddd  call    LipsIkePolicyProposalDestroy
0x180045de2  lea     rcx, [rbp+var_10]
0x180045de6  call    LipsIkePolicyProposalDestroy
0x180045deb  test    ebx, ebx
0x180045ded  jnz     short loc_180045DF3
0x180045def  xor     eax, eax
0x180045df1  jmp     short loc_180045E01
0x180045df3  lea     rdx, aLipsstateikefi_0; "LipsStateIkeFilterUpdate"
0x180045dfa  mov     ecx, ebx
0x180045dfc  call    LipsReportError
0x180045e01  mov     rbx, [rsp+30h+arg_8]
0x180045e06  add     rsp, 30h
0x180045e0a  pop     rdi
0x180045e0b  pop     rsi
0x180045e0c  pop     rbp
0x180045e0d  retn
```
