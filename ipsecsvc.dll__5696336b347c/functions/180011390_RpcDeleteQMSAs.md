# RpcDeleteQMSAs

- ea: `0x180011390`
- end: `0x1800115dd`
- name: `RpcDeleteQMSAs`
- size: `589`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x18000e510`
- `0x180011390`
- `0x180017e80`
- `0x18002e94c`
- `0x1800438f0`
- `0x180043918`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800115c5`
- `RPCRT4!RpcRevertToSelf` at `0x1800115c5`

## pseudocode

```c
__int64 __fastcall RpcDeleteQMSAs(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  _DWORD v21[6]; // [rsp+20h] [rbp-18h] BYREF

  v21[0] = 0;
  v5 = SPDImpersonateClient(v21);
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 175;
LABEL_5:
      v8 = v5;
LABEL_40:
      WPP_SF_d(v6[2], v7, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids, v8);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  if ( a2 < 2 )
  {
    if ( !a3 )
    {
      v8 = 87;
      v5 = 87;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 177;
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    v9 = *(_QWORD *)(a3 + 8);
    if ( !v9 || !*(_DWORD *)a3 )
    {
      v8 = 87;
      v5 = 87;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 178;
        goto LABEL_40;
      }
      goto LABEL_41;
    }
    v10 = *(_DWORD *)(v9 + 136);
    if ( v10 > 2 )
    {
      v5 = 124;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 179;
        goto LABEL_5;
      }
      goto LABEL_41;
    }
    v11 = v9 + 144;
    if ( v10 )
    {
      v5 = ValidateV6Addr(v11);
      if ( v5 )
        goto LABEL_34;
      v5 = ValidateV6Addr(v17 + 176);
      if ( v5 )
        goto LABEL_34;
      v5 = ValidateV6Addr(v18 + 232);
      if ( v5 )
        goto LABEL_34;
      v15 = ValidateV6Addr(v19 + 264);
    }
    else
    {
      v5 = ValidateV4Addr(v11);
      if ( v5 )
        goto LABEL_34;
      v5 = ValidateV4Addr(v12 + 176);
      if ( v5 )
        goto LABEL_34;
      v5 = ValidateV4Addr(v13 + 232);
      if ( v5 )
        goto LABEL_34;
      v15 = ValidateV4Addr(v14 + 264);
    }
    v5 = v15;
    if ( !v15 )
    {
      v5 = DeleteQMSAsInternal(v16);
      if ( v5 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 181;
          goto LABEL_5;
        }
      }
      goto LABEL_41;
    }
LABEL_34:
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 180;
      goto LABEL_5;
    }
    goto LABEL_41;
  }
  v5 = 50;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v7 = 176;
    goto LABEL_5;
  }
LABEL_41:
  if ( v21[0] )
    RpcRevertToSelf();
  return v5;
}

```

## disassembly

```asm
0x180011390  mov     rax, rsp
0x180011393  mov     [rax+8], rbx
0x180011397  mov     [rax+10h], rsi
0x18001139b  push    rdi
0x18001139c  sub     rsp, 30h
0x1800113a0  lea     rcx, [rax-18h]
0x1800113a4  mov     dword ptr [rax-18h], 0
0x1800113ab  mov     rdi, r8
0x1800113ae  mov     esi, edx
0x1800113b0  call    SPDImpersonateClient
0x1800113b5  mov     ebx, eax
0x1800113b7  test    eax, eax
0x1800113b9  jz      short loc_1800113E9
0x1800113bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113c2  lea     rax, WPP_GLOBAL_Control
0x1800113c9  cmp     rcx, rax
0x1800113cc  jz      loc_1800115BE
0x1800113d2  test    byte ptr [rcx+1Ch], 10h
0x1800113d6  jz      loc_1800115BE
0x1800113dc  mov     edx, 0AFh
0x1800113e1  mov     r9d, ebx
0x1800113e4  jmp     loc_1800115AE
0x1800113e9  cmp     esi, 2
0x1800113ec  jb      short loc_180011419
0x1800113ee  mov     ebx, 32h ; '2'
0x1800113f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113fa  lea     rax, WPP_GLOBAL_Control
0x180011401  cmp     rcx, rax
0x180011404  jz      loc_1800115BE
0x18001140a  test    byte ptr [rcx+1Ch], 10h
0x18001140e  jz      loc_1800115BE
0x180011414  lea     edx, [rbx+7Eh]
0x180011417  jmp     short loc_1800113E1
0x180011419  test    rdi, rdi
0x18001141c  jnz     short loc_18001144F
0x18001141e  lea     r9d, [rdi+57h]
0x180011422  mov     ebx, r9d
0x180011425  mov     rcx, cs:WPP_GLOBAL_Control
0x18001142c  lea     rax, WPP_GLOBAL_Control
0x180011433  cmp     rcx, rax
0x180011436  jz      loc_1800115BE
0x18001143c  test    byte ptr [rcx+1Ch], 10h
0x180011440  jz      loc_1800115BE
0x180011446  lea     edx, [r9+5Ah]
0x18001144a  jmp     loc_1800115AE
0x18001144f  mov     r8, [rdi+8]
0x180011453  test    r8, r8
0x180011456  jz      loc_180011588
0x18001145c  cmp     dword ptr [rdi], 0
0x18001145f  jz      loc_180011588
0x180011465  mov     eax, [r8+88h]
0x18001146c  cmp     eax, 2
0x18001146f  jle     short loc_18001149F
0x180011471  mov     ebx, 7Ch ; '|'
0x180011476  mov     rcx, cs:WPP_GLOBAL_Control
0x18001147d  lea     rax, WPP_GLOBAL_Control
0x180011484  cmp     rcx, rax
0x180011487  jz      loc_1800115BE
0x18001148d  test    byte ptr [rcx+1Ch], 10h
0x180011491  jz      loc_1800115BE
0x180011497  lea     edx, [rbx+37h]
0x18001149a  jmp     loc_1800113E1
0x18001149f  lea     rcx, [r8+90h]
0x1800114a6  test    eax, eax
0x1800114a8  jnz     short loc_1800114F3
0x1800114aa  call    ValidateV4Addr
0x1800114af  mov     ebx, eax
0x1800114b1  test    eax, eax
0x1800114b3  jnz     loc_180011565
0x1800114b9  lea     rcx, [r8+0B0h]
0x1800114c0  call    ValidateV4Addr
0x1800114c5  mov     ebx, eax
0x1800114c7  test    eax, eax
0x1800114c9  jnz     loc_180011565
0x1800114cf  lea     rcx, [r8+0E8h]
0x1800114d6  call    ValidateV4Addr
0x1800114db  mov     ebx, eax
0x1800114dd  test    eax, eax
0x1800114df  jnz     loc_180011565
0x1800114e5  lea     rcx, [r8+108h]
0x1800114ec  call    ValidateV4Addr
0x1800114f1  jmp     short loc_18001152E
0x1800114f3  call    ValidateV6Addr
0x1800114f8  mov     ebx, eax
0x1800114fa  test    eax, eax
0x1800114fc  jnz     short loc_180011565
0x1800114fe  lea     rcx, [r8+0B0h]
0x180011505  call    ValidateV6Addr
0x18001150a  mov     ebx, eax
0x18001150c  test    eax, eax
0x18001150e  jnz     short loc_180011565
0x180011510  lea     rcx, [r8+0E8h]
0x180011517  call    ValidateV6Addr
0x18001151c  mov     ebx, eax
0x18001151e  test    eax, eax
0x180011520  jnz     short loc_180011565
0x180011522  lea     rcx, [r8+108h]
0x180011529  call    ValidateV6Addr
0x18001152e  mov     ebx, eax
0x180011530  test    eax, eax
0x180011532  jnz     short loc_180011565
0x180011534  mov     rcx, r8
0x180011537  call    DeleteQMSAsInternal
0x18001153c  mov     ebx, eax
0x18001153e  test    eax, eax
0x180011540  jz      short loc_1800115BE
0x180011542  mov     rcx, cs:WPP_GLOBAL_Control
0x180011549  lea     rax, WPP_GLOBAL_Control
0x180011550  cmp     rcx, rax
0x180011553  jz      short loc_1800115BE
0x180011555  test    byte ptr [rcx+1Ch], 10h
0x180011559  jz      short loc_1800115BE
0x18001155b  mov     edx, 0B5h
0x180011560  jmp     loc_1800113E1
0x180011565  mov     rcx, cs:WPP_GLOBAL_Control
0x18001156c  lea     rax, WPP_GLOBAL_Control
0x180011573  cmp     rcx, rax
0x180011576  jz      short loc_1800115BE
0x180011578  test    byte ptr [rcx+1Ch], 10h
0x18001157c  jz      short loc_1800115BE
0x18001157e  mov     edx, 0B4h
0x180011583  jmp     loc_1800113E1
0x180011588  mov     r9d, 57h ; 'W'
0x18001158e  mov     ebx, r9d
0x180011591  mov     rcx, cs:WPP_GLOBAL_Control
0x180011598  lea     rax, WPP_GLOBAL_Control
0x18001159f  cmp     rcx, rax
0x1800115a2  jz      short loc_1800115BE
0x1800115a4  test    byte ptr [rcx+1Ch], 10h
0x1800115a8  jz      short loc_1800115BE
0x1800115aa  lea     edx, [r9+5Bh]
0x1800115ae  mov     rcx, [rcx+10h]
0x1800115b2  lea     r8, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids
0x1800115b9  call    WPP_SF_d
0x1800115be  cmp     [rsp+38h+var_18], 0
0x1800115c3  jz      short loc_1800115CB
0x1800115c5  call    cs:__imp_RpcRevertToSelf
0x1800115cb  mov     rsi, [rsp+38h+arg_8]
0x1800115d0  mov     eax, ebx
0x1800115d2  mov     rbx, [rsp+38h+arg_0]
0x1800115d7  add     rsp, 30h
0x1800115db  pop     rdi
0x1800115dc  retn
```
