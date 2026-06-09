# LsaDbpDsCauseTransactionToCommitOrAbort(uchar)

- ea: `0x180010d78`
- end: `0x180010ec0`
- name: `?LsaDbpDsCauseTransactionToCommitOrAbort@@YAJE@Z`
- size: `328`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015554`
- `0x18001f130`
- `0x18001f260`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000fd18`
- `0x180010d78`
- `0x18001182c`
- `0x180011d6c`

## import_xrefs

- `NTDSA!SampExistsDsTransaction` at `0x180010e0d`
- `NTDSA!SampExistsDsTransaction` at `0x180010e0d`
- `NTDSA!THQuery` at `0x180010e03`
- `NTDSA!THQuery` at `0x180010e03`
- `NTDSA!THClearErrors` at `0x180010e56`
- `NTDSA!THClearErrors` at `0x180010e97`
- `NTDSA!THClearErrors` at `0x180010e56`
- `NTDSA!THClearErrors` at `0x180010e97`
- `NTDSA!DirRead` at `0x180010e87`
- `NTDSA!DirRead` at `0x180010e87`
- `NTDSA!DirTransactControl` at `0x180010e61`
- `NTDSA!DirTransactControl` at `0x180010eb3`
- `NTDSA!DirTransactControl` at `0x180010e61`
- `NTDSA!DirTransactControl` at `0x180010eb3`

## pseudocode

```c
__int64 __fastcall LsaDbpDsCauseTransactionToCommitOrAbort(char a1)
{
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v8; // [rsp+28h] [rbp-D8h] BYREF
  __int128 *v9; // [rsp+38h] [rbp-C8h]
  __int64 v10; // [rsp+40h] [rbp-C0h]
  __int128 v11; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h]
  _QWORD v13[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v14[200]; // [rsp+78h] [rbp-88h] BYREF

  v7 = 0;
  v12 = 0;
  v8 = 0;
  v10 = 86;
  v9 = &v11;
  LOBYTE(v8) = 76;
  DWORD2(v8) = 1;
  v11 = 0;
  memset_0(v13, 0, 0xE0u);
  v13[1] = &v8;
  LsaDbpDsInitializeStdCommArg((struct _COMMARG *)v14, 0);
  if ( !(unsigned int)THQuery() )
    return 0;
  if ( !(unsigned int)SampExistsDsTransaction() )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids);
    return 0;
  }
  THClearErrors();
  DirTransactControl(1);
  v13[0] = LsaDbDsStateInfo;
  LODWORD(v11) = -(a1 == 0);
  v5 = DirRead(v13, &v7, v3, v4);
  if ( v7 )
  {
    v6 = LsaDbpDsMapDsReturnToStatusEx(v5, (struct _COMMRES *)(v7 + 48));
  }
  else
  {
    THClearErrors();
    v6 = -1073741801;
  }
  DirTransactControl(0);
  return v6;
}

```

## disassembly

```asm
0x180010d78  mov     [rsp-8+arg_0], rbx
0x180010d7d  push    rbp
0x180010d7e  lea     rbp, [rsp-50h]
0x180010d83  sub     rsp, 150h
0x180010d8a  mov     rax, cs:__security_cookie
0x180010d91  xor     rax, rsp
0x180010d94  mov     [rbp+50h+var_10], rax
0x180010d98  xor     eax, eax
0x180010d9a  mov     [rsp+150h+var_130], 0
0x180010da3  xorps   xmm1, xmm1
0x180010da6  mov     [rsp+150h+var_F8], rax
0x180010dab  movups  [rsp+150h+var_128], xmm1
0x180010db0  lea     rax, [rsp+150h+var_108]
0x180010db5  mov     bl, cl
0x180010db7  movups  [rsp+150h+var_118], xmm1
0x180010dbc  mov     qword ptr [rsp+150h+var_118], rax
0x180010dc1  xor     edx, edx; Val
0x180010dc3  xorps   xmm0, xmm0
0x180010dc6  mov     byte ptr [rsp+150h+var_128], 4Ch ; 'L'
0x180010dcb  mov     r8d, 0E0h; Size
0x180010dd1  mov     dword ptr [rsp+150h+var_128+8], 1
0x180010dd9  lea     rcx, [rsp+150h+var_F0]; void *
0x180010dde  mov     byte ptr [rsp+150h+var_118+8], 56h ; 'V'
0x180010de3  movups  [rsp+150h+var_108], xmm0
0x180010de8  call    memset_0
0x180010ded  lea     rax, [rsp+150h+var_128]
0x180010df2  xor     edx, edx; unsigned int
0x180010df4  lea     rcx, [rsp+150h+var_D8]; struct _COMMARG *
0x180010df9  mov     [rsp+150h+var_E8], rax
0x180010dfe  call    ?LsaDbpDsInitializeStdCommArg@@YAXPEAU_COMMARG@@K@Z; LsaDbpDsInitializeStdCommArg(_COMMARG *,ulong)
0x180010e03  call    cs:__imp_THQuery
0x180010e09  test    eax, eax
0x180010e0b  jz      short loc_180010E37
0x180010e0d  call    cs:__imp_SampExistsDsTransaction
0x180010e13  test    eax, eax
0x180010e15  jnz     short loc_180010E56
0x180010e17  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e1e  test    byte ptr [rcx+1Ch], 1
0x180010e22  jz      short loc_180010E37
0x180010e24  mov     rcx, [rcx+10h]
0x180010e28  lea     edx, [rax+1Bh]
0x180010e2b  lea     r8, WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids
0x180010e32  call    WPP_SF_
0x180010e37  xor     eax, eax
0x180010e39  mov     rcx, [rbp+50h+var_10]
0x180010e3d  xor     rcx, rsp; StackCookie
0x180010e40  call    __security_check_cookie
0x180010e45  mov     rbx, [rsp+150h+arg_0]
0x180010e4d  add     rsp, 150h
0x180010e54  pop     rbp
0x180010e55  retn
0x180010e56  call    cs:__imp_THClearErrors
0x180010e5c  mov     ecx, 1
0x180010e61  call    cs:__imp_DirTransactControl
0x180010e67  mov     rax, cs:?LsaDbDsStateInfo@@3U_LSADS_DS_STATE_INFO@@A; _LSADS_DS_STATE_INFO LsaDbDsStateInfo
0x180010e6e  lea     rdx, [rsp+150h+var_130]
0x180010e73  mov     [rsp+150h+var_F0], rax
0x180010e78  lea     rcx, [rsp+150h+var_F0]
0x180010e7d  neg     bl
0x180010e7f  sbb     eax, eax
0x180010e81  not     eax
0x180010e83  mov     dword ptr [rsp+150h+var_108], eax
0x180010e87  call    cs:__imp_DirRead
0x180010e8d  mov     rdx, [rsp+150h+var_130]
0x180010e92  test    rdx, rdx
0x180010e95  jnz     short loc_180010EA4
0x180010e97  call    cs:__imp_THClearErrors
0x180010e9d  mov     ebx, 0C0000017h
0x180010ea2  jmp     short loc_180010EB1
0x180010ea4  add     rdx, 30h ; '0'; struct _COMMRES *
0x180010ea8  mov     ecx, eax; unsigned int
0x180010eaa  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x180010eaf  mov     ebx, eax
0x180010eb1  xor     ecx, ecx
0x180010eb3  call    cs:__imp_DirTransactControl
0x180010eb9  mov     eax, ebx
0x180010ebb  jmp     loc_180010E39
```
