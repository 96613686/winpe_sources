# RpcOpenTransportFilterHandle

- ea: `0x1800148a0`
- end: `0x180014a7d`
- name: `RpcOpenTransportFilterHandle`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18000e510`
- `0x18000fc6c`
- `0x1800148a0`
- `0x180017e80`
- `0x18001e650`
- `0x18004d05e`
- `0x18004d090`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180014a52`
- `RPCRT4!RpcRevertToSelf` at `0x180014a52`

## pseudocode

```c
__int64 __fastcall RpcOpenTransportFilterHandle(__int64 a1, unsigned int a2, __int64 a3, __int64 *a4)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  _DWORD v17[4]; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE v18[192]; // [rsp+40h] [rbp-E8h] BYREF

  memset_0(v18, 0, 0xB8u);
  v17[0] = 0;
  v7 = SPDImpersonateClient(v17);
  v8 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 157;
LABEL_5:
      v11 = v7;
LABEL_29:
      WPP_SF_d(v9[2], v10, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids, v11);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  if ( a2 >= 2 )
  {
    v8 = 50;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v10 = 158;
    goto LABEL_10;
  }
  if ( !a3 || !a4 )
  {
    v11 = 87;
    v8 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 159;
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  v12 = *(int **)(a3 + 8);
  if ( !v12 || *(_DWORD *)a3 != 1 )
  {
    v11 = 87;
    v8 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 160;
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  if ( *v12 > 2 )
  {
    v8 = 124;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v10 = 161;
LABEL_10:
    v11 = v8;
    goto LABEL_29;
  }
  CopyOldToNewTxFilter(v12, (__int64)v18);
  v7 = OpenTransportFilterHandleInternal(v14, v13, (__int64)v18, v15, a4);
  v8 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 162;
      goto LABEL_5;
    }
  }
LABEL_30:
  if ( v17[0] )
    RpcRevertToSelf();
  return v8;
}

```

## disassembly

```asm
0x1800148a0  mov     [rsp+arg_0], rbx
0x1800148a5  push    rbp
0x1800148a6  push    rsi
0x1800148a7  push    rdi
0x1800148a8  sub     rsp, 110h
0x1800148af  mov     rax, cs:__security_cookie
0x1800148b6  xor     rax, rsp
0x1800148b9  mov     [rsp+128h+var_28], rax
0x1800148c1  mov     rdi, r8
0x1800148c4  lea     rcx, [rsp+128h+var_E8]; void *
0x1800148c9  mov     ebp, edx
0x1800148cb  mov     r8d, 0B8h; Size
0x1800148d1  xor     edx, edx; Val
0x1800148d3  mov     rsi, r9
0x1800148d6  call    memset_0
0x1800148db  lea     rcx, [rsp+128h+var_F8]
0x1800148e0  mov     [rsp+128h+var_F8], 0
0x1800148e8  call    SPDImpersonateClient
0x1800148ed  mov     ebx, eax
0x1800148ef  test    eax, eax
0x1800148f1  jz      short loc_180014921
0x1800148f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148fa  lea     rdx, WPP_GLOBAL_Control
0x180014901  cmp     rcx, rdx
0x180014904  jz      loc_180014A4B
0x18001490a  test    byte ptr [rcx+1Ch], 10h
0x18001490e  jz      loc_180014A4B
0x180014914  mov     edx, 9Dh
0x180014919  mov     r9d, eax
0x18001491c  jmp     loc_180014A3B
0x180014921  cmp     ebp, 2
0x180014924  jb      short loc_180014957
0x180014926  mov     ebx, 32h ; '2'
0x18001492b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014932  lea     rdx, WPP_GLOBAL_Control
0x180014939  cmp     rcx, rdx
0x18001493c  jz      loc_180014A4B
0x180014942  test    byte ptr [rcx+1Ch], 10h
0x180014946  jz      loc_180014A4B
0x18001494c  lea     edx, [rbx+6Ch]
0x18001494f  mov     r9d, ebx
0x180014952  jmp     loc_180014A3B
0x180014957  test    rdi, rdi
0x18001495a  jz      loc_180014A15
0x180014960  test    rsi, rsi
0x180014963  jz      loc_180014A15
0x180014969  mov     rcx, [rdi+8]
0x18001496d  test    rcx, rcx
0x180014970  jz      short loc_1800149ED
0x180014972  cmp     dword ptr [rdi], 1
0x180014975  jnz     short loc_1800149ED
0x180014977  cmp     dword ptr [rcx], 2
0x18001497a  jle     short loc_1800149A7
0x18001497c  mov     ebx, 7Ch ; '|'
0x180014981  mov     rcx, cs:WPP_GLOBAL_Control
0x180014988  lea     rdx, WPP_GLOBAL_Control
0x18001498f  cmp     rcx, rdx
0x180014992  jz      loc_180014A4B
0x180014998  test    byte ptr [rcx+1Ch], 10h
0x18001499c  jz      loc_180014A4B
0x1800149a2  lea     edx, [rbx+25h]
0x1800149a5  jmp     short loc_18001494F
0x1800149a7  lea     rdx, [rsp+128h+var_E8]
0x1800149ac  call    CopyOldToNewTxFilter
0x1800149b1  lea     r8, [rsp+128h+var_E8]
0x1800149b6  mov     [rsp+128h+var_108], rsi
0x1800149bb  call    OpenTransportFilterHandleInternal
0x1800149c0  mov     ebx, eax
0x1800149c2  test    eax, eax
0x1800149c4  jz      loc_180014A4B
0x1800149ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149d1  lea     rdx, WPP_GLOBAL_Control
0x1800149d8  cmp     rcx, rdx
0x1800149db  jz      short loc_180014A4B
0x1800149dd  test    byte ptr [rcx+1Ch], 10h
0x1800149e1  jz      short loc_180014A4B
0x1800149e3  mov     edx, 0A2h
0x1800149e8  jmp     loc_180014919
0x1800149ed  mov     r9d, 57h ; 'W'
0x1800149f3  mov     ebx, r9d
0x1800149f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149fd  lea     rdx, WPP_GLOBAL_Control
0x180014a04  cmp     rcx, rdx
0x180014a07  jz      short loc_180014A4B
0x180014a09  test    byte ptr [rcx+1Ch], 10h
0x180014a0d  jz      short loc_180014A4B
0x180014a0f  lea     edx, [r9+49h]
0x180014a13  jmp     short loc_180014A3B
0x180014a15  mov     r9d, 57h ; 'W'
0x180014a1b  mov     ebx, r9d
0x180014a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a25  lea     rdx, WPP_GLOBAL_Control
0x180014a2c  cmp     rcx, rdx
0x180014a2f  jz      short loc_180014A4B
0x180014a31  test    byte ptr [rcx+1Ch], 10h
0x180014a35  jz      short loc_180014A4B
0x180014a37  lea     edx, [r9+48h]
0x180014a3b  mov     rcx, [rcx+10h]
0x180014a3f  lea     r8, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids
0x180014a46  call    WPP_SF_d
0x180014a4b  cmp     [rsp+128h+var_F8], 0
0x180014a50  jz      short loc_180014A58
0x180014a52  call    cs:__imp_RpcRevertToSelf
0x180014a58  mov     eax, ebx
0x180014a5a  mov     rcx, [rsp+128h+var_28]
0x180014a62  xor     rcx, rsp; StackCookie
0x180014a65  call    __security_check_cookie
0x180014a6a  mov     rbx, [rsp+128h+arg_0]
0x180014a72  add     rsp, 110h
0x180014a79  pop     rdi
0x180014a7a  pop     rsi
0x180014a7b  pop     rbp
0x180014a7c  retn
```
