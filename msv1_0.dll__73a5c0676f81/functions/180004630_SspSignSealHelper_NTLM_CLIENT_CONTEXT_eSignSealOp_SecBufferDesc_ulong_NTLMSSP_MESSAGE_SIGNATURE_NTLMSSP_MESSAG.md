# SspSignSealHelper(_NTLM_CLIENT_CONTEXT *,_eSignSealOp,_SecBufferDesc *,ulong,_NTLMSSP_MESSAGE_SIGNATURE *,_NTLMSSP_MESSAGE_SIGNATURE * *)

- ea: `0x180004630`
- end: `0x180004e59`
- name: `?SspSignSealHelper@@YAJPEAU_NTLM_CLIENT_CONTEXT@@W4_eSignSealOp@@PEAU_SecBufferDesc@@KPEAU_NTLMSSP_MESSAGE_SIGNATURE@@PEAPEAU4@@Z`
- size: `2089`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180003660`
- `0x1800038e0`
- `0x180003d40`
- `0x1800042e0`
- `0x180005260`

## callees

- `0x180004630`
- `0x180006710`
- `0x180009880`
- `0x18002ee7c`
- `0x18002fb50`
- `0x18004c5b4`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180004937`
- `bcrypt!BCryptFinishHash` at `0x180004b8b`
- `bcrypt!BCryptFinishHash` at `0x180004937`
- `bcrypt!BCryptFinishHash` at `0x180004b8b`
- `bcrypt!BCryptDestroyHash` at `0x180004975`
- `bcrypt!BCryptDestroyHash` at `0x180004e14`
- `bcrypt!BCryptDestroyHash` at `0x180004e23`
- `bcrypt!BCryptDestroyHash` at `0x180004975`
- `bcrypt!BCryptDestroyHash` at `0x180004e14`
- `bcrypt!BCryptDestroyHash` at `0x180004e23`
- `bcrypt!BCryptHashData` at `0x1800048a8`
- `bcrypt!BCryptHashData` at `0x1800048ee`
- `bcrypt!BCryptHashData` at `0x1800049d9`
- `bcrypt!BCryptHashData` at `0x180004a92`
- `bcrypt!BCryptHashData` at `0x1800048a8`
- `bcrypt!BCryptHashData` at `0x1800048ee`
- `bcrypt!BCryptHashData` at `0x1800049d9`
- `bcrypt!BCryptHashData` at `0x180004a92`
- `bcrypt!BCryptCreateHash` at `0x1800047bb`
- `bcrypt!BCryptCreateHash` at `0x18000484d`
- `bcrypt!BCryptCreateHash` at `0x1800047bb`
- `bcrypt!BCryptCreateHash` at `0x18000484d`

## pseudocode

```c
__int64 __fastcall SspSignSealHelper(__int64 a1, unsigned int a2, __int64 a3, int a4, _OWORD *a5, _QWORD *a6)
{
  __int64 v8; // r9
  unsigned int i; // ecx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r8
  int v14; // edx
  NTSTATUS v15; // ebx
  _DWORD *v16; // rsi
  UCHAR *v17; // r14
  void **v18; // r13
  UCHAR *pbSecret; // r12
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // ecx
  __int64 v24; // rax
  unsigned int j; // r14d
  __int64 v26; // r9
  int v27; // eax
  unsigned int v28; // r8d
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r8
  bool v33; // zf
  unsigned int v34; // edx
  unsigned int k; // r12d
  __int64 v36; // r9
  int v37; // ecx
  unsigned int v38; // r8d
  __int64 v39; // r8
  int v40; // r9d
  unsigned __int8 *m; // r10
  __int64 v42; // rax
  BCRYPT_HASH_HANDLE hHash; // [rsp+48h] [rbp-51h] BYREF
  int v46; // [rsp+50h] [rbp-49h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-41h] BYREF
  int v48; // [rsp+60h] [rbp-39h]
  int v49; // [rsp+64h] [rbp-35h]
  __int64 v50; // [rsp+68h] [rbp-31h]
  _OWORD *v51; // [rsp+70h] [rbp-29h]
  UCHAR pbInput[16]; // [rsp+78h] [rbp-21h] BYREF
  UCHAR pbOutput[16]; // [rsp+88h] [rbp-11h] BYREF
  UCHAR v54[16]; // [rsp+98h] [rbp-1h] BYREF

  v46 = a4;
  v51 = a5;
  *(_OWORD *)pbInput = 0;
  v8 = a3;
  *(_OWORD *)pbOutput = 0;
  hHash = 0;
  phHash = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(a3 + 4) )
      return (unsigned int)-2146893048;
    v11 = *(_QWORD *)(a3 + 8);
    if ( *(_BYTE *)(v11 + 16LL * i + 4) == 2 )
      break;
  }
  if ( i == -1 )
    return (unsigned int)-2146893048;
  v12 = 16LL * (int)i;
  v50 = v12;
  if ( *(_DWORD *)(v11 + v12) < 0x10u )
    return (unsigned int)-2146893048;
  v13 = *(_QWORD *)(v11 + v12 + 8);
  *a6 = v13;
  v14 = *(_DWORD *)(a1 + 48);
  if ( (v14 & 0x10) == 0 && a2 <= 1 )
  {
    *a5 = 0;
    *(_DWORD *)a5 = 1;
    return 0;
  }
  if ( (v14 & 0x20) == 0 && (*(_DWORD *)(a1 + 48) & 0x10) == 0 && a2 - 2 <= 1 )
    return (unsigned int)-2146893054;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
LABEL_19:
      v16 = *(_DWORD **)(a1 + 80);
      v17 = (UCHAR *)(a1 + 244);
      v18 = *(void ***)(a1 + 96);
      pbSecret = (UCHAR *)(a1 + 212);
      goto LABEL_21;
    }
    if ( a2 != 2 )
    {
      if ( a2 != 3 )
        return (unsigned int)-1073741496;
      goto LABEL_19;
    }
  }
  v16 = *(_DWORD **)(a1 + 72);
  v17 = (UCHAR *)(a1 + 228);
  v18 = *(void ***)(a1 + 88);
  pbSecret = (UCHAR *)(a1 + 196);
LABEL_21:
  v49 = *(_DWORD *)(v13 + 4);
  v20 = *(_DWORD *)(v13 + 12);
  v48 = v20;
  *(_DWORD *)pbInput = 1;
  if ( (v14 & 0x80000) != 0 )
  {
    if ( (v14 & 0x40) == 0 )
    {
      *(_DWORD *)&pbInput[12] = (*v16)++;
LABEL_24:
      v15 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &phHash, 0, 0, pbSecret, 0x10u, 0);
      if ( v15 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          goto LABEL_127;
        v22 = 46;
        goto LABEL_38;
      }
      v15 = BCryptHashData(phHash, &pbInput[12], 4u, 0);
      if ( v15 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          goto LABEL_127;
        v22 = 47;
        goto LABEL_38;
      }
      v24 = a3;
      for ( j = 0; ; ++j )
      {
        if ( j >= *(_DWORD *)(v24 + 4) )
        {
          v15 = BCryptFinishHash(phHash, v54, 0x10u, 0);
          if ( v15 >= 0 )
          {
            v33 = (*(_DWORD *)(a1 + 48) & 0x40000000) == 0;
            *(_QWORD *)&pbInput[4] = *(_QWORD *)v54;
            if ( v33 )
              goto LABEL_126;
            v15 = SspEncryptBuffer((struct _NTLM_CLIENT_CONTEXT *)a1, v18, 8u, &pbInput[4]);
            if ( v15 >= 0 )
              goto LABEL_126;
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              v22 = 52;
              goto LABEL_38;
            }
          }
          else
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              v22 = 51;
              goto LABEL_38;
            }
          }
          goto LABEL_127;
        }
        v26 = *(_QWORD *)(v24 + 8);
        v27 = *(_DWORD *)(v26 + 16LL * j + 4);
        if ( (_BYTE)v27 != 1 )
          goto LABEL_71;
        v28 = *(_DWORD *)(v26 + 16LL * j);
        if ( !v28 )
          goto LABEL_71;
        v29 = v27 & 0x90000000;
        if ( v29 == -1879048192 )
          goto LABEL_82;
        if ( a2 == 3 && !v29 )
        {
          v15 = SspEncryptBuffer((struct _NTLM_CLIENT_CONTEXT *)a1, v18, v28, *(void **)(v26 + 16LL * j + 8));
          if ( v15 < 0 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              v22 = 48;
              goto LABEL_38;
            }
            goto LABEL_127;
          }
        }
        v15 = BCryptHashData(
                phHash,
                *(PUCHAR *)(*(_QWORD *)(a3 + 8) + 16LL * j + 8),
                *(_DWORD *)(*(_QWORD *)(a3 + 8) + 16LL * j),
                0);
        if ( v15 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WPP_SF_dL(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, j, v15);
          }
          goto LABEL_127;
        }
        v24 = a3;
        if ( a2 == 2 )
        {
          v32 = *(_QWORD *)(a3 + 8);
          if ( (*(_DWORD *)(v32 + 16LL * j + 4) & 0x90000000) == 0 )
            break;
        }
LABEL_72:
        ;
      }
      v15 = SspEncryptBuffer(
              (struct _NTLM_CLIENT_CONTEXT *)a1,
              v18,
              *(_DWORD *)(v32 + 16LL * j),
              *(void **)(v32 + 16LL * j + 8));
      if ( v15 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          v22 = 50;
          goto LABEL_38;
        }
        goto LABEL_127;
      }
LABEL_71:
      v24 = a3;
      goto LABEL_72;
    }
    if ( (a2 & 0xFFFFFFFD) == 0 || a4 )
    {
      *(_DWORD *)&pbInput[12] = a4;
      if ( a2 == 2 )
        goto LABEL_34;
    }
    else
    {
      *(_DWORD *)&pbInput[12] = v20;
    }
    if ( a2 != 3 && (v14 & 0x40000000) == 0 )
      goto LABEL_24;
LABEL_34:
    v15 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &hHash, 0, 0, 0, 0, 0);
    if ( v15 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        goto LABEL_127;
      v22 = 41;
      goto LABEL_38;
    }
    v15 = BCryptHashData(hHash, v17, 0x10u, 0);
    if ( v15 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        goto LABEL_127;
      v22 = 42;
      goto LABEL_38;
    }
    v15 = BCryptHashData(hHash, &pbInput[12], 4u, 0);
    if ( v15 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        goto LABEL_127;
      v22 = 43;
      goto LABEL_38;
    }
    v15 = BCryptFinishHash(hHash, pbOutput, 0x10u, 0);
    if ( v15 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        goto LABEL_127;
      v22 = 44;
      goto LABEL_38;
    }
    BCryptDestroyHash(hHash);
    v23 = *(_DWORD *)(a1 + 48);
    hHash = 0;
    v15 = SspRc4Key(v23, v18, pbOutput);
    if ( v15 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        goto LABEL_127;
      v22 = 45;
      goto LABEL_38;
    }
    goto LABEL_24;
  }
  v34 = -1;
  *(_DWORD *)&pbInput[8] = -1;
  for ( k = 0; k < *(_DWORD *)(v8 + 4); ++k )
  {
    v36 = *(_QWORD *)(v8 + 8);
    v37 = *(_DWORD *)(v36 + 16LL * k + 4);
    if ( (_BYTE)v37 == 1 )
    {
      v38 = *(_DWORD *)(v36 + 16LL * k);
      if ( v38 )
      {
        if ( (v37 & 0x90000000) == 0x90000000 )
        {
LABEL_82:
          v15 = -2146893048;
          goto LABEL_127;
        }
        if ( v37 >= 0 )
        {
          if ( a2 == 3 && (v37 & 0x10000000) == 0 )
          {
            v15 = SspEncryptBuffer((struct _NTLM_CLIENT_CONTEXT *)a1, v18, v38, *(void **)(v36 + 16LL * k + 8));
            if ( v15 < 0 )
            {
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
              {
                goto LABEL_127;
              }
              v22 = 53;
              goto LABEL_38;
            }
            v34 = *(_DWORD *)&pbInput[8];
          }
          v39 = *(_QWORD *)(a3 + 8);
          v40 = *(_DWORD *)(v39 + 16LL * k);
          for ( m = *(unsigned __int8 **)(v39 + 16LL * k + 8); v40; --v40 )
          {
            v42 = *m++;
            v34 = *((_DWORD *)CRCTable + (v42 ^ (unsigned __int8)v34)) ^ (v34 >> 8);
          }
          *(_DWORD *)&pbInput[8] = v34;
          if ( a2 == 2 && (*(_DWORD *)(v39 + 16LL * k + 4) & 0x10000000) == 0 )
          {
            v15 = SspEncryptBuffer(
                    (struct _NTLM_CLIENT_CONTEXT *)a1,
                    v18,
                    *(_DWORD *)(v39 + 16LL * k),
                    *(void **)(v39 + 16LL * k + 8));
            if ( v15 < 0 )
            {
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
              {
                goto LABEL_127;
              }
              v22 = 54;
              goto LABEL_38;
            }
            v34 = *(_DWORD *)&pbInput[8];
          }
        }
      }
    }
    v8 = a3;
  }
  *(_DWORD *)&pbInput[12] = 0;
  *(_DWORD *)&pbInput[8] = ~v34;
  v15 = SspEncryptBuffer((struct _NTLM_CLIENT_CONTEXT *)a1, v18, 0xCu, &pbInput[4]);
  if ( v15 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_127;
    v22 = 55;
LABEL_38:
    WPP_SF_d(v21[2], v22, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, (unsigned int)v15);
    goto LABEL_127;
  }
  if ( (*(_BYTE *)(a1 + 48) & 0x40) != 0 )
  {
    if ( (a2 & 0xFFFFFFFD) == 0 || v46 )
      *(_DWORD *)&pbInput[12] ^= v46;
    else
      *(_DWORD *)&pbInput[12] = v48;
  }
  else
  {
    *(_DWORD *)&pbInput[12] ^= (*v16)++;
  }
  *(_DWORD *)&pbInput[4] = v49;
LABEL_126:
  v15 = 0;
  *(_DWORD *)(v50 + *(_QWORD *)(a3 + 8)) = 16;
  *v51 = *(_OWORD *)pbInput;
LABEL_127:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180004630  mov     [rsp-8+arg_8], rbx
0x180004635  push    rbp
0x180004636  push    rsi
0x180004637  push    rdi
0x180004638  push    r12
0x18000463a  push    r13
0x18000463c  push    r14
0x18000463e  push    r15
0x180004640  lea     rbp, [rsp-17h]
0x180004645  sub     rsp, 0B0h
0x18000464c  mov     rax, cs:__security_cookie
0x180004653  xor     rax, rsp
0x180004656  mov     [rbp+47h+var_38], rax
0x18000465a  mov     rbx, [rbp+47h+arg_20]
0x18000465e  xorps   xmm0, xmm0
0x180004661  mov     r10, [rbp+47h+arg_28]
0x180004665  xorps   xmm1, xmm1
0x180004668  mov     r11d, r9d
0x18000466b  mov     [rbp+47h+var_90], r9d
0x18000466f  mov     rdi, rcx
0x180004672  mov     [rbp+47h+var_70], rbx
0x180004676  movups  xmmword ptr [rbp+47h+pbInput], xmm0
0x18000467a  mov     r9, r8
0x18000467d  mov     [rbp+47h+var_A0], r8
0x180004681  movups  xmmword ptr [rbp+47h+pbOutput], xmm1
0x180004685  mov     r15d, edx
0x180004688  mov     [rbp+47h+hHash], 0
0x180004690  mov     [rbp+47h+phHash], 0
0x180004698  xor     ecx, ecx
0x18000469a  cmp     ecx, [r8+4]
0x18000469e  jnb     loc_180004E2B
0x1800046a4  mov     rdx, [r8+8]
0x1800046a8  mov     eax, ecx
0x1800046aa  add     rax, rax
0x1800046ad  cmp     byte ptr [rdx+rax*8+4], 2
0x1800046b2  jz      short loc_1800046B8
0x1800046b4  inc     ecx
0x1800046b6  jmp     short loc_18000469A
0x1800046b8  cmp     ecx, 0FFFFFFFFh
0x1800046bb  jz      loc_180004E2B
0x1800046c1  movsxd  rax, ecx
0x1800046c4  shl     rax, 4
0x1800046c8  mov     [rbp+47h+var_78], rax
0x1800046cc  cmp     dword ptr [rdx+rax], 10h
0x1800046d0  jb      loc_180004E2B
0x1800046d6  mov     r8, [rdx+rax+8]
0x1800046db  mov     [r10], r8
0x1800046de  mov     edx, [rdi+30h]
0x1800046e1  mov     eax, edx
0x1800046e3  and     eax, 10h
0x1800046e6  jnz     short loc_180004701
0x1800046e8  cmp     r15d, 1
0x1800046ec  ja      short loc_180004701
0x1800046ee  xorps   xmm0, xmm0
0x1800046f1  movups  xmmword ptr [rbx], xmm0
0x1800046f4  mov     dword ptr [rbx], 1
0x1800046fa  xor     ebx, ebx
0x1800046fc  jmp     loc_180004E30
0x180004701  test    dl, 20h
0x180004704  jnz     short loc_18000471D
0x180004706  test    eax, eax
0x180004708  jnz     short loc_18000471D
0x18000470a  lea     eax, [r15-2]
0x18000470e  cmp     eax, 1
0x180004711  ja      short loc_18000471D
0x180004713  mov     ebx, 80090302h
0x180004718  jmp     loc_180004E30
0x18000471d  mov     ecx, r15d
0x180004720  test    r15d, r15d
0x180004723  jz      short loc_180004756
0x180004725  sub     ecx, 1
0x180004728  jz      short loc_18000473E
0x18000472a  sub     ecx, 1
0x18000472d  jz      short loc_180004756
0x18000472f  cmp     ecx, 1
0x180004732  jz      short loc_18000473E
0x180004734  mov     ebx, 0C0000148h
0x180004739  jmp     loc_180004E30
0x18000473e  mov     rsi, [rdi+50h]
0x180004742  lea     r14, [rdi+0F4h]
0x180004749  mov     r13, [rdi+60h]
0x18000474d  lea     r12, [rdi+0D4h]
0x180004754  jmp     short loc_18000476C
0x180004756  mov     rsi, [rdi+48h]
0x18000475a  lea     r14, [rdi+0E4h]
0x180004761  mov     r13, [rdi+58h]
0x180004765  lea     r12, [rdi+0C4h]
0x18000476c  mov     eax, [r8+4]
0x180004770  mov     [rbp+47h+var_7C], eax
0x180004773  mov     eax, [r8+0Ch]
0x180004777  mov     [rbp+47h+var_80], eax
0x18000477a  mov     dword ptr [rbp+47h+pbInput], 1
0x180004781  bt      edx, 13h
0x180004785  jnb     loc_180004C27
0x18000478b  test    dl, 40h
0x18000478e  jnz     short loc_1800047F9
0x180004790  mov     eax, [rsi]
0x180004792  mov     dword ptr [rbp+47h+pbInput+0Ch], eax
0x180004795  inc     dword ptr [rsi]
0x180004797  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x18000479f  lea     rdx, [rbp+47h+phHash]; phHash
0x1800047a3  mov     [rsp+0E0h+cbSecret], 10h; cbSecret
0x1800047ab  xor     r9d, r9d; cbHashObject
0x1800047ae  xor     r8d, r8d; pbHashObject
0x1800047b1  mov     [rsp+0E0h+pbSecret], r12; pbSecret
0x1800047b6  mov     ecx, 91h; hAlgorithm
0x1800047bb  call    cs:__imp_BCryptCreateHash
0x1800047c1  mov     ebx, eax
0x1800047c3  test    eax, eax
0x1800047c5  jns     loc_1800049CA
0x1800047cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047d2  lea     rax, WPP_GLOBAL_Control
0x1800047d9  cmp     rcx, rax
0x1800047dc  jz      loc_180004E0B
0x1800047e2  test    dword ptr [rcx+1Ch], 100h
0x1800047e9  jz      loc_180004E0B
0x1800047ef  mov     edx, 2Eh ; '.'
0x1800047f4  jmp     loc_180004882
0x1800047f9  test    r15d, 0FFFFFFFDh
0x180004800  jz      short loc_18000480C
0x180004802  test    r11d, r11d
0x180004805  jnz     short loc_18000480C
0x180004807  mov     dword ptr [rbp+47h+pbInput+0Ch], eax
0x18000480a  jmp     short loc_180004816
0x18000480c  mov     dword ptr [rbp+47h+pbInput+0Ch], r11d
0x180004810  cmp     r15d, 2
0x180004814  jz      short loc_180004826
0x180004816  cmp     r15d, 3
0x18000481a  jz      short loc_180004826
0x18000481c  bt      edx, 1Eh
0x180004820  jnb     loc_180004797
0x180004826  xor     r9d, r9d; cbHashObject
0x180004829  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x180004831  mov     [rsp+0E0h+cbSecret], 0; cbSecret
0x180004839  lea     rdx, [rbp+47h+hHash]; phHash
0x18000483d  xor     r8d, r8d; pbHashObject
0x180004840  mov     [rsp+0E0h+pbSecret], 0; pbSecret
0x180004849  lea     ecx, [r9+21h]; hAlgorithm
0x18000484d  call    cs:__imp_BCryptCreateHash
0x180004853  mov     ebx, eax
0x180004855  test    eax, eax
0x180004857  jns     short loc_18000489A
0x180004859  mov     rcx, cs:WPP_GLOBAL_Control
0x180004860  lea     rax, WPP_GLOBAL_Control
0x180004867  cmp     rcx, rax
0x18000486a  jz      loc_180004E0B
0x180004870  test    dword ptr [rcx+1Ch], 100h
0x180004877  jz      loc_180004E0B
0x18000487d  mov     edx, 29h ; ')'
0x180004882  mov     rcx, [rcx+10h]
0x180004886  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x18000488d  mov     r9d, ebx
0x180004890  call    WPP_SF_d
0x180004895  jmp     loc_180004E0B
0x18000489a  mov     rcx, [rbp+47h+hHash]; hHash
0x18000489e  xor     r9d, r9d; dwFlags
0x1800048a1  mov     rdx, r14; pbInput
0x1800048a4  lea     r8d, [r9+10h]; cbInput
0x1800048a8  call    cs:__imp_BCryptHashData
0x1800048ae  mov     ebx, eax
0x1800048b0  test    eax, eax
0x1800048b2  jns     short loc_1800048DF
0x1800048b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048bb  lea     rax, WPP_GLOBAL_Control
0x1800048c2  cmp     rcx, rax
0x1800048c5  jz      loc_180004E0B
0x1800048cb  test    dword ptr [rcx+1Ch], 100h
0x1800048d2  jz      loc_180004E0B
0x1800048d8  mov     edx, 2Ah ; '*'
0x1800048dd  jmp     short loc_180004882
0x1800048df  mov     rcx, [rbp+47h+hHash]; hHash
0x1800048e3  lea     rdx, [rbp+47h+pbInput+0Ch]; pbInput
0x1800048e7  xor     r9d, r9d; dwFlags
0x1800048ea  lea     r8d, [r9+4]; cbInput
0x1800048ee  call    cs:__imp_BCryptHashData
0x1800048f4  mov     ebx, eax
0x1800048f6  test    eax, eax
0x1800048f8  jns     short loc_180004928
0x1800048fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180004901  lea     rax, WPP_GLOBAL_Control
0x180004908  cmp     rcx, rax
0x18000490b  jz      loc_180004E0B
0x180004911  test    dword ptr [rcx+1Ch], 100h
0x180004918  jz      loc_180004E0B
0x18000491e  mov     edx, 2Bh ; '+'
0x180004923  jmp     loc_180004882
0x180004928  mov     rcx, [rbp+47h+hHash]; hHash
0x18000492c  lea     rdx, [rbp+47h+pbOutput]; pbOutput
0x180004930  xor     r9d, r9d; dwFlags
0x180004933  lea     r8d, [r9+10h]; cbOutput
0x180004937  call    cs:__imp_BCryptFinishHash
0x18000493d  mov     ebx, eax
0x18000493f  test    eax, eax
0x180004941  jns     short loc_180004971
0x180004943  mov     rcx, cs:WPP_GLOBAL_Control
0x18000494a  lea     rax, WPP_GLOBAL_Control
0x180004951  cmp     rcx, rax
0x180004954  jz      loc_180004E0B
0x18000495a  test    dword ptr [rcx+1Ch], 100h
0x180004961  jz      loc_180004E0B
0x180004967  mov     edx, 2Ch ; ','
0x18000496c  jmp     loc_180004882
0x180004971  mov     rcx, [rbp+47h+hHash]; hHash
0x180004975  call    cs:__imp_BCryptDestroyHash
0x18000497b  mov     ecx, [rdi+30h]; unsigned int
0x18000497e  lea     r8, [rbp+47h+pbOutput]; unsigned __int8 *
0x180004982  mov     rdx, r13; void **
0x180004985  mov     [rbp+47h+hHash], 0
0x18000498d  call    ?SspRc4Key@@YAJKPEAPEAXPEAE@Z; SspRc4Key(ulong,void * *,uchar *)
0x180004992  mov     ebx, eax
0x180004994  test    eax, eax
0x180004996  jns     loc_180004797
0x18000499c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049a3  lea     rax, WPP_GLOBAL_Control
0x1800049aa  cmp     rcx, rax
0x1800049ad  jz      loc_180004E0B
0x1800049b3  test    dword ptr [rcx+1Ch], 100h
0x1800049ba  jz      loc_180004E0B
0x1800049c0  mov     edx, 2Dh ; '-'
0x1800049c5  jmp     loc_180004882
0x1800049ca  mov     rcx, [rbp+47h+phHash]; hHash
0x1800049ce  lea     rdx, [rbp+47h+pbInput+0Ch]; pbInput
0x1800049d2  xor     r9d, r9d; dwFlags
0x1800049d5  lea     r8d, [r9+4]; cbInput
0x1800049d9  call    cs:__imp_BCryptHashData
0x1800049df  mov     ebx, eax
0x1800049e1  test    eax, eax
0x1800049e3  jns     short loc_180004A13
0x1800049e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049ec  lea     rax, WPP_GLOBAL_Control
0x1800049f3  cmp     rcx, rax
0x1800049f6  jz      loc_180004E0B
0x1800049fc  test    dword ptr [rcx+1Ch], 100h
0x180004a03  jz      loc_180004E0B
0x180004a09  mov     edx, 2Fh ; '/'
0x180004a0e  jmp     loc_180004882
0x180004a13  mov     rax, [rbp+47h+var_A0]
0x180004a17  xor     r14d, r14d
0x180004a1a  mov     r12d, 90000000h
0x180004a20  cmp     r14d, [rax+4]
0x180004a24  jnb     loc_180004B7C
0x180004a2a  mov     r9, [rax+8]
0x180004a2e  mov     esi, r14d
0x180004a31  add     rsi, rsi
0x180004a34  mov     eax, [r9+rsi*8+4]
0x180004a39  cmp     al, 1
0x180004a3b  jnz     loc_180004AD1
0x180004a41  mov     r8d, [r9+rsi*8]; unsigned int
0x180004a45  test    r8d, r8d
0x180004a48  jz      loc_180004AD1
0x180004a4e  and     eax, r12d
0x180004a51  cmp     eax, r12d
0x180004a54  jz      loc_180004B72
0x180004a5a  cmp     r15d, 3
0x180004a5e  jnz     short loc_180004A7A
0x180004a60  test    eax, eax
0x180004a62  jnz     short loc_180004A7A
0x180004a64  mov     r9, [r9+rsi*8+8]; void *
0x180004a69  mov     rdx, r13; void **
0x180004a6c  mov     rcx, rdi; struct _NTLM_CLIENT_CONTEXT *
0x180004a6f  call    ?SspEncryptBuffer@@YAJPEAU_NTLM_CLIENT_CONTEXT@@PEAPEAXKPEAX@Z; SspEncryptBuffer(_NTLM_CLIENT_CONTEXT *,void * *,ulong,void *)
0x180004a74  mov     ebx, eax
0x180004a76  test    eax, eax
0x180004a78  js      short loc_180004ADD
0x180004a7a  mov     rax, [rbp+47h+var_A0]
0x180004a7e  xor     r9d, r9d; dwFlags
0x180004a81  mov     rcx, [rbp+47h+phHash]; hHash
0x180004a85  mov     rdx, [rax+8]
0x180004a89  mov     r8d, [rdx+rsi*8]; cbInput
0x180004a8d  mov     rdx, [rdx+rsi*8+8]; pbInput
0x180004a92  call    cs:__imp_BCryptHashData
0x180004a98  mov     ebx, eax
0x180004a9a  test    eax, eax
0x180004a9c  js      loc_180004B39
0x180004aa2  mov     rax, [rbp+47h+var_A0]
0x180004aa6  cmp     r15d, 2
0x180004aaa  jnz     short loc_180004AD5
0x180004aac  mov     r8, [rax+8]
0x180004ab0  test    [r8+rsi*8+4], r12d
0x180004ab5  jnz     short loc_180004AD5
0x180004ab7  mov     r9, [r8+rsi*8+8]; void *
0x180004abc  mov     rdx, r13; void **
0x180004abf  mov     r8d, [r8+rsi*8]; unsigned int
0x180004ac3  mov     rcx, rdi; struct _NTLM_CLIENT_CONTEXT *
0x180004ac6  call    ?SspEncryptBuffer@@YAJPEAU_NTLM_CLIENT_CONTEXT@@PEAPEAXKPEAX@Z; SspEncryptBuffer(_NTLM_CLIENT_CONTEXT *,void * *,ulong,void *)
0x180004acb  mov     ebx, eax
0x180004acd  test    eax, eax
0x180004acf  js      short loc_180004B0B
0x180004ad1  mov     rax, [rbp+47h+var_A0]
0x180004ad5  inc     r14d
0x180004ad8  jmp     loc_180004A20
0x180004add  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ae4  lea     rax, WPP_GLOBAL_Control
0x180004aeb  cmp     rcx, rax
0x180004aee  jz      loc_180004E0B
0x180004af4  test    dword ptr [rcx+1Ch], 100h
0x180004afb  jz      loc_180004E0B
0x180004b01  mov     edx, 30h ; '0'
0x180004b06  jmp     loc_180004882
0x180004b0b  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
