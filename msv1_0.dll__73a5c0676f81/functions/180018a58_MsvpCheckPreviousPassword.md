# MsvpCheckPreviousPassword

- ea: `0x180018a58`
- end: `0x180018ccf`
- name: `MsvpCheckPreviousPassword`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800132c0`

## callees

- `0x180018a58`
- `0x18002fb50`

## import_xrefs

- `NtlmShared!MsvpPasswordValidate` at `0x180018beb`
- `NtlmShared!MsvpPasswordValidate` at `0x180018c29`
- `NtlmShared!MsvpPasswordValidate` at `0x180018beb`
- `NtlmShared!MsvpPasswordValidate` at `0x180018c29`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180018c80`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180018c80`
- `SAMSRV!SamrCloseHandle` at `0x180018ca7`
- `SAMSRV!SamrCloseHandle` at `0x180018ca7`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x180018b25`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x180018b25`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x180018c95`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x180018c95`
- `CRYPTSP!SystemFunction027` at `0x180018b6c`
- `CRYPTSP!SystemFunction027` at `0x180018b95`
- `CRYPTSP!SystemFunction027` at `0x180018b6c`
- `CRYPTSP!SystemFunction027` at `0x180018b95`

## pseudocode

```c
__int64 __fastcall MsvpCheckPreviousPassword(
        char a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6,
        _BYTE *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v12; // rdi
  __int64 result; // rax
  __int64 v14; // rcx
  int v15; // ebx
  char v16; // r15
  char v17; // r14
  __int64 v18; // rsi
  __int64 v19; // rdi
  __int64 v20; // rsi
  bool v21; // zf
  __int64 v22; // r15
  _BYTE *v23; // rax
  __int64 v24; // rax
  __int128 *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int128 *v28; // rcx
  _BYTE *v29; // rcx
  __int64 v31; // [rsp+48h] [rbp-99h] BYREF
  __int64 v32; // [rsp+50h] [rbp-91h] BYREF
  __int64 v33; // [rsp+58h] [rbp-89h]
  __int64 v34; // [rsp+60h] [rbp-81h]
  __int64 v35; // [rsp+68h] [rbp-79h]
  __int64 v36; // [rsp+70h] [rbp-71h] BYREF
  __int64 v37; // [rsp+78h] [rbp-69h]
  _BYTE *v38; // [rsp+80h] [rbp-61h]
  _BYTE *v39; // [rsp+88h] [rbp-59h]
  _QWORD v40[5]; // [rsp+90h] [rbp-51h] BYREF
  __int128 v41; // [rsp+B8h] [rbp-29h] BYREF
  __int128 v42; // [rsp+C8h] [rbp-19h] BYREF

  v33 = a8;
  v12 = a3;
  v34 = a9;
  v35 = a10;
  *a7 = 0;
  memset(&v40[2], 0, 19);
  v38 = a6;
  v39 = a7;
  *a6 = 0;
  v32 = 0;
  v31 = 0;
  v36 = 0;
  *(_OWORD *)v40 = 0;
  v37 = 0;
  v41 = 0;
  v42 = 0;
  result = SamIGetUserLogonInformationEx(a4, 8, a5, 603979780, &v31, &v36, &v32);
  v15 = result;
  if ( (int)result < 0 )
    return result;
  v16 = 0;
  v17 = 0;
  v18 = v31;
  if ( *(_WORD *)(v31 + 240) >= 0x44u )
  {
    v19 = *(_QWORD *)(v31 + 248);
    if ( *(_DWORD *)v19 == 2 )
    {
      if ( *(_WORD *)(v19 + 60) >= 0x20u )
      {
        v15 = SystemFunction027(v19 + 84, v31 + 272, &v41);
        if ( v15 < 0 )
          goto LABEL_18;
        v16 = 1;
      }
      if ( *(_WORD *)(v19 + 60) >= 0x30u )
      {
        v15 = SystemFunction027(v19 + 100, v18 + 272, &v42);
        if ( v15 < 0 )
          goto LABEL_18;
        v17 = 1;
      }
    }
    v12 = a3;
  }
  v20 = v33;
  v21 = v16 == 0;
  v22 = v34;
  LOWORD(v40[4]) = 1;
  if ( v21
    || (LOBYTE(v14) = a1, *(_OWORD *)v40 = v41, !(unsigned __int8)MsvpPasswordValidate(v14, a2, v12, v40, v33, v34, v35)) )
  {
    if ( !v17 )
      goto LABEL_18;
    LOBYTE(v14) = a1;
    *(_OWORD *)v40 = v42;
    if ( !(unsigned __int8)MsvpPasswordValidate(v14, a2, v12, v40, v20, v22, v35) )
      goto LABEL_18;
    v23 = v39;
  }
  else
  {
    v23 = v38;
  }
  *v23 = 1;
LABEL_18:
  v24 = 16;
  v25 = &v41;
  v26 = 16;
  do
  {
    *(_BYTE *)v25 = 0;
    v25 = (__int128 *)((char *)v25 + 1);
    --v26;
  }
  while ( v26 );
  v27 = 16;
  v28 = &v42;
  do
  {
    *(_BYTE *)v28 = 0;
    v28 = (__int128 *)((char *)v28 + 1);
    --v27;
  }
  while ( v27 );
  v29 = v40;
  do
  {
    *v29++ = 0;
    --v24;
  }
  while ( v24 );
  if ( v37 )
    SamIFreeSidAndAttributesList(&v36, 0);
  if ( v31 )
    SamIFree_SAMPR_USER_INFO_BUFFER(v31, 21);
  if ( v32 )
    SamrCloseHandle(&v32);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180018a58  push    rbp
0x180018a5a  push    rbx
0x180018a5b  push    rsi
0x180018a5c  push    rdi
0x180018a5d  push    r12
0x180018a5f  push    r13
0x180018a61  push    r14
0x180018a63  push    r15
0x180018a65  lea     rbp, [rsp-7]
0x180018a6a  sub     rsp, 0E8h
0x180018a71  mov     rax, cs:__security_cookie
0x180018a78  xor     rax, rsp
0x180018a7b  mov     [rbp+3Fh+var_48], rax
0x180018a7f  mov     r12b, cl
0x180018a82  mov     [rsp+120h+var_E0], r8
0x180018a87  mov     rcx, [rbp+3Fh+arg_38]
0x180018a8e  xor     esi, esi
0x180018a90  mov     [rsp+120h+var_C8], rcx
0x180018a95  xorps   xmm0, xmm0
0x180018a98  mov     rcx, [rbp+3Fh+arg_40]
0x180018a9f  mov     rax, r9
0x180018aa2  mov     r9, [rbp+3Fh+arg_30]
0x180018aa6  mov     r13d, edx
0x180018aa9  mov     rdx, [rbp+3Fh+arg_28]
0x180018aad  mov     rdi, r8
0x180018ab0  mov     r8, [rbp+3Fh+arg_20]
0x180018ab4  xorps   xmm1, xmm1
0x180018ab7  mov     [rsp+120h+var_C0], rcx
0x180018abc  mov     rcx, [rbp+3Fh+arg_48]
0x180018ac3  mov     [rbp+3Fh+var_B8], rcx
0x180018ac7  xor     ecx, ecx
0x180018ac9  mov     [r9], sil
0x180018acc  movups  [rbp+3Fh+var_80], xmm0
0x180018ad0  mov     dword ptr [rbp+3Fh+var_80+0Fh], ecx
0x180018ad3  lea     rcx, [rsp+120h+var_D0]
0x180018ad8  mov     [rsp+120h+var_F0], rcx
0x180018add  lea     rcx, [rbp+3Fh+var_B0]
0x180018ae1  mov     [rsp+120h+var_F8], rcx
0x180018ae6  lea     rcx, [rsp+120h+var_D8]
0x180018aeb  mov     [rsp+120h+var_100], rcx
0x180018af0  mov     rcx, rax
0x180018af3  mov     [rbp+3Fh+var_A0], rdx
0x180018af7  mov     [rbp+3Fh+var_98], r9
0x180018afb  mov     r9d, 24000004h
0x180018b01  mov     [rdx], sil
0x180018b04  lea     edx, [rsi+8]
0x180018b07  mov     [rsp+120h+var_D0], rsi
0x180018b0c  mov     [rsp+120h+var_D8], rsi
0x180018b11  mov     [rbp+3Fh+var_B0], rsi
0x180018b15  movups  [rbp+3Fh+var_90], xmm0
0x180018b19  mov     [rbp+3Fh+var_A8], rsi
0x180018b1d  movups  [rbp+3Fh+var_68], xmm0
0x180018b21  movups  [rbp+3Fh+var_58], xmm1
0x180018b25  call    cs:__imp_SamIGetUserLogonInformationEx
0x180018b2b  mov     ebx, eax
0x180018b2d  test    eax, eax
0x180018b2f  js      loc_180018CAF
0x180018b35  mov     r15b, sil
0x180018b38  mov     r14b, sil
0x180018b3b  mov     rsi, [rsp+120h+var_D8]
0x180018b40  cmp     word ptr [rsi+0F0h], 44h ; 'D'
0x180018b48  jb      short loc_180018BAD
0x180018b4a  mov     rdi, [rsi+0F8h]
0x180018b51  cmp     dword ptr [rdi], 2
0x180018b54  jnz     short loc_180018BA8
0x180018b56  cmp     word ptr [rdi+3Ch], 20h ; ' '
0x180018b5b  jb      short loc_180018B7F
0x180018b5d  lea     rdx, [rsi+110h]
0x180018b64  lea     rcx, [rdi+54h]
0x180018b68  lea     r8, [rbp+3Fh+var_68]
0x180018b6c  call    cs:__imp_SystemFunction027
0x180018b72  mov     ebx, eax
0x180018b74  test    eax, eax
0x180018b76  js      loc_180018C3A
0x180018b7c  mov     r15b, 1
0x180018b7f  cmp     word ptr [rdi+3Ch], 30h ; '0'
0x180018b84  jb      short loc_180018BA8
0x180018b86  lea     rdx, [rsi+110h]
0x180018b8d  lea     rcx, [rdi+64h]
0x180018b91  lea     r8, [rbp+3Fh+var_58]
0x180018b95  call    cs:__imp_SystemFunction027
0x180018b9b  mov     ebx, eax
0x180018b9d  test    eax, eax
0x180018b9f  js      loc_180018C3A
0x180018ba5  mov     r14b, 1
0x180018ba8  mov     rdi, [rsp+120h+var_E0]
0x180018bad  mov     rsi, [rsp+120h+var_C8]
0x180018bb2  test    r15b, r15b
0x180018bb5  mov     r15, [rsp+120h+var_C0]
0x180018bba  mov     [rbp+3Fh+var_70], 1
0x180018bc0  jz      short loc_180018BFB
0x180018bc2  movups  xmm0, [rbp+3Fh+var_68]
0x180018bc6  mov     rax, [rbp+3Fh+var_B8]
0x180018bca  lea     r9, [rbp+3Fh+var_90]
0x180018bce  mov     [rsp+120h+var_F0], rax
0x180018bd3  mov     r8, rdi
0x180018bd6  mov     [rsp+120h+var_F8], r15
0x180018bdb  mov     edx, r13d
0x180018bde  mov     cl, r12b
0x180018be1  mov     [rsp+120h+var_100], rsi
0x180018be6  movdqu  [rbp+3Fh+var_90], xmm0
0x180018beb  call    cs:__imp_MsvpPasswordValidate
0x180018bf1  test    al, al
0x180018bf3  jz      short loc_180018BFB
0x180018bf5  mov     rax, [rbp+3Fh+var_A0]
0x180018bf9  jmp     short loc_180018C37
0x180018bfb  test    r14b, r14b
0x180018bfe  jz      short loc_180018C3A
0x180018c00  movups  xmm0, [rbp+3Fh+var_58]
0x180018c04  mov     rax, [rbp+3Fh+var_B8]
0x180018c08  lea     r9, [rbp+3Fh+var_90]
0x180018c0c  mov     [rsp+120h+var_F0], rax
0x180018c11  mov     r8, rdi
0x180018c14  mov     [rsp+120h+var_F8], r15
0x180018c19  mov     edx, r13d
0x180018c1c  mov     cl, r12b
0x180018c1f  mov     [rsp+120h+var_100], rsi
0x180018c24  movdqu  [rbp+3Fh+var_90], xmm0
0x180018c29  call    cs:__imp_MsvpPasswordValidate
0x180018c2f  test    al, al
0x180018c31  jz      short loc_180018C3A
0x180018c33  mov     rax, [rbp+3Fh+var_98]
0x180018c37  mov     byte ptr [rax], 1
0x180018c3a  mov     eax, 10h
0x180018c3f  lea     rcx, [rbp+3Fh+var_68]
0x180018c43  mov     edx, eax
0x180018c45  xor     edi, edi
0x180018c47  mov     [rcx], dil
0x180018c4a  inc     rcx
0x180018c4d  sub     rdx, 1
0x180018c51  jnz     short loc_180018C47
0x180018c53  mov     rdx, rax
0x180018c56  lea     rcx, [rbp+3Fh+var_58]
0x180018c5a  mov     [rcx], dil
0x180018c5d  inc     rcx
0x180018c60  sub     rdx, 1
0x180018c64  jnz     short loc_180018C5A
0x180018c66  lea     rcx, [rbp+3Fh+var_90]
0x180018c6a  mov     [rcx], dil
0x180018c6d  inc     rcx
0x180018c70  sub     rax, 1
0x180018c74  jnz     short loc_180018C6A
0x180018c76  cmp     [rbp+3Fh+var_A8], rdi
0x180018c7a  jz      short loc_180018C86
0x180018c7c  lea     rcx, [rbp+3Fh+var_B0]
0x180018c80  call    cs:__imp_SamIFreeSidAndAttributesList
0x180018c86  mov     rcx, [rsp+120h+var_D8]
0x180018c8b  test    rcx, rcx
0x180018c8e  jz      short loc_180018C9B
0x180018c90  mov     edx, 15h
0x180018c95  call    cs:__imp_SamIFree_SAMPR_USER_INFO_BUFFER
0x180018c9b  cmp     [rsp+120h+var_D0], rdi
0x180018ca0  jz      short loc_180018CAD
0x180018ca2  lea     rcx, [rsp+120h+var_D0]
0x180018ca7  call    cs:__imp_SamrCloseHandle
0x180018cad  mov     eax, ebx
0x180018caf  mov     rcx, [rbp+3Fh+var_48]
0x180018cb3  xor     rcx, rsp; StackCookie
0x180018cb6  call    __security_check_cookie
0x180018cbb  add     rsp, 0E8h
0x180018cc2  pop     r15
0x180018cc4  pop     r14
0x180018cc6  pop     r13
0x180018cc8  pop     r12
0x180018cca  pop     rdi
0x180018ccb  pop     rsi
0x180018ccc  pop     rbx
0x180018ccd  pop     rbp
0x180018cce  retn
```
