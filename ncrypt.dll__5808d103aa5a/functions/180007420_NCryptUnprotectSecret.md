# NCryptUnprotectSecret

- ea: `0x180007420`
- end: `0x1800077ea`
- name: `NCryptUnprotectSecret`
- size: `970`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180007024`
- `0x180007098`
- `0x180007274`
- `0x180007420`
- `0x180007ae0`
- `0x18000d02c`
- `0x18000e120`
- `0x18000f098`
- `0x18001b808`
- `0x180020010`

## string_xrefs

- `0x1800076dc`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x1800075c9`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x18000763e`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x18000768e`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180007728`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x18000777e`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800077ae`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall NCryptUnprotectSecret(
        _QWORD *a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 *a5,
        __int64 a6,
        _QWORD *a7,
        _DWORD *a8)
{
  _BYTE *v8; // r12
  __int64 v9; // r14
  __int64 *v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // edi
  int v15; // edx
  int v16; // r8d
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // r15d
  __int64 v21; // rax
  _BYTE *v22; // rdx
  _QWORD *v24; // rcx
  __int64 ProcessName; // rax
  int v26; // ecx
  _DWORD *v27; // rax
  PVOID *v28; // rcx
  unsigned int v29; // ecx
  char v30; // [rsp+30h] [rbp-30h]
  unsigned int v31; // [rsp+40h] [rbp-20h] BYREF
  __int64 v32; // [rsp+48h] [rbp-18h] BYREF
  _BYTE *v33; // [rsp+50h] [rbp-10h] BYREF
  int v35; // [rsp+B0h] [rbp+50h]

  v35 = a3;
  v8 = 0;
  v9 = 0;
  v32 = 0;
  v33 = 0;
  v31 = 0;
  if ( !a3 || !a4 || !a7 || !a8 )
  {
    v14 = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        93);
    goto LABEL_35;
  }
  if ( a1 )
    *a1 = 0;
  *a7 = 0;
  *a8 = 0;
  if ( (a2 & 0xFFFFFFBE) != 0 )
  {
    v14 = -2146893815;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        111);
LABEL_35:
    v12 = a5;
    goto LABEL_30;
  }
  v12 = &NCryptDefaultAllocPara;
  if ( a5 )
    v12 = a5;
  v13 = I_OpenProtectedMessage((unsigned int)&v32, a2, a3, a4, (__int64)v12, a6, (__int64)&v33, (__int64)&v31);
  v14 = v13;
  if ( v13 )
  {
    DebugTraceError(
      v13,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
      1928);
    v9 = v32;
    v8 = v33;
    goto LABEL_30;
  }
  v8 = v33;
  if ( (a2 & 1) != 0 )
  {
    *a1 = v32;
LABEL_18:
    v14 = 0;
    goto LABEL_19;
  }
  v9 = v32;
  v14 = CMSG_ImportContentEncryptionKey(*(_QWORD *)(v32 + 24), *(_QWORD *)(v32 + 32) + 72LL, v33, v31);
  if ( v14 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v30 = -95;
      goto LABEL_29;
    }
  }
  else
  {
    v17 = *(_QWORD *)(v9 + 32);
    v18 = *(_DWORD *)(v17 + 112);
    if ( v18 )
    {
      v19 = *(_QWORD *)(v17 + 120);
      v20 = v18;
    }
    else
    {
      v27 = *(_DWORD **)(v9 + 24);
      if ( !v27 || *v27 != 368 )
      {
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v17,
            v16,
            (unsigned int)"Status",
            38,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
            96);
          v28 = (PVOID *)WPP_GLOBAL_Control;
        }
        v14 = -2146893786;
        if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 1) != 0 )
          WPP_SF_sDsd(
            (unsigned int)v28[2],
            v17,
            v16,
            (unsigned int)"Status",
            38,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
            182);
        goto LABEL_30;
      }
      v29 = v27[12];
      if ( v29 > a4 )
      {
        v14 = -2146893819;
        DebugTraceError(
          2148073477LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
          1981);
        goto LABEL_30;
      }
      LODWORD(v19) = v35 + v29;
      v20 = a4 - v29;
    }
    v14 = CMSG_DecryptAndAllocate(*(_QWORD *)(v9 + 24), v19, v20, (_DWORD)a7, (__int64)a8);
    if ( !v14 )
    {
      if ( a1 )
      {
        *a1 = v9;
        v9 = 0;
      }
      goto LABEL_18;
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v30 = -45;
LABEL_29:
      WPP_SF_sDsd(
        v24[2],
        v15,
        v16,
        (unsigned int)"Status",
        v14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        v30);
    }
  }
LABEL_30:
  if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 2) != 0 )
  {
    ProcessName = I_GetProcessName();
    McTemplateU0ddz_EventWriteTransfer(v26, (unsigned int)ETW_LOG_NCRYPT_UNPROTECT_SECRET_FAILED, a2, v14, ProcessName);
  }
LABEL_19:
  if ( v8 )
  {
    v21 = v31;
    v22 = v8;
    if ( v31 )
    {
      do
      {
        *v22++ = 0;
        --v21;
      }
      while ( v21 );
    }
    ((void (__fastcall *)(_BYTE *, _BYTE *))v12[2])(v8, v22);
  }
  if ( v9 )
    NCryptCloseProtectionDescriptor(v9);
  return v14;
}

```

## disassembly

```asm
0x180007420  mov     [rsp-38h+arg_0], rbx
0x180007425  mov     [rsp-38h+arg_10], r8
0x18000742a  mov     [rsp-38h+arg_8], edx
0x18000742e  push    rbp
0x18000742f  push    rsi
0x180007430  push    rdi
0x180007431  push    r12
0x180007433  push    r13
0x180007435  push    r14
0x180007437  push    r15
0x180007439  mov     rbp, rsp
0x18000743c  sub     rsp, 60h
0x180007440  xor     r12d, r12d
0x180007443  xor     r14d, r14d
0x180007446  mov     [rbp+var_18], r14
0x18000744a  mov     r15d, r9d
0x18000744d  mov     [rbp+var_10], r12
0x180007451  mov     rsi, rcx
0x180007454  mov     [rbp+var_20], r12d
0x180007458  test    r8, r8
0x18000745b  jz      loc_180007618
0x180007461  cmp     r9d, 1
0x180007465  jb      loc_180007618
0x18000746b  mov     r13, [rbp+arg_30]
0x18000746f  test    r13, r13
0x180007472  jz      loc_180007618
0x180007478  mov     rax, [rbp+arg_38]
0x18000747c  test    rax, rax
0x18000747f  jz      loc_180007618
0x180007485  test    rcx, rcx
0x180007488  jz      short loc_18000748D
0x18000748a  mov     [rcx], r12
0x18000748d  mov     [r13+0], r12
0x180007491  mov     [rax], r12d
0x180007494  test    edx, 0FFFFFFBEh
0x18000749a  jnz     loc_180007668
0x1800074a0  mov     rax, [rbp+arg_20]
0x1800074a4  lea     rbx, NCryptDefaultAllocPara
0x1800074ab  test    rax, rax
0x1800074ae  lea     rcx, [rbp+var_18]
0x1800074b2  cmovnz  rbx, rax
0x1800074b6  lea     rax, [rbp+var_20]
0x1800074ba  mov     [rsp+60h+var_28], rax
0x1800074bf  lea     rax, [rbp+var_10]
0x1800074c3  mov     [rsp+60h+var_30], rax
0x1800074c8  mov     rax, [rbp+arg_28]
0x1800074cc  mov     [rsp+60h+var_38], rax
0x1800074d1  mov     [rsp+60h+var_40], rbx
0x1800074d6  call    I_OpenProtectedMessage
0x1800074db  mov     edi, eax
0x1800074dd  test    eax, eax
0x1800074df  jnz     loc_180007778
0x1800074e5  mov     eax, [rbp+arg_8]
0x1800074e8  mov     r12, [rbp+var_10]
0x1800074ec  test    al, 1
0x1800074ee  jnz     loc_18000773E
0x1800074f4  mov     r14, [rbp+var_18]
0x1800074f8  mov     r8, r12
0x1800074fb  mov     r9d, [rbp+var_20]
0x1800074ff  mov     rdx, [r14+20h]
0x180007503  mov     rcx, [r14+18h]
0x180007507  add     rdx, 48h ; 'H'
0x18000750b  call    CMSG_ImportContentEncryptionKey
0x180007510  mov     edi, eax
0x180007512  test    eax, eax
0x180007514  jnz     loc_18000774A
0x18000751a  mov     rdx, [r14+20h]
0x18000751e  mov     eax, [rdx+70h]
0x180007521  test    eax, eax
0x180007523  jz      loc_1800076A4
0x180007529  mov     rdx, [rdx+78h]
0x18000752d  mov     r15d, eax
0x180007530  mov     rax, [rbp+arg_38]
0x180007534  mov     r9, r13
0x180007537  mov     rcx, [r14+18h]
0x18000753b  mov     r8d, r15d
0x18000753e  mov     [rsp+60h+var_40], rax
0x180007543  call    CMSG_DecryptAndAllocate
0x180007548  mov     edi, eax
0x18000754a  test    eax, eax
0x18000754c  jnz     short loc_1800075A8
0x18000754e  test    rsi, rsi
0x180007551  jnz     loc_1800077DF
0x180007557  xor     edi, edi
0x180007559  test    r12, r12
0x18000755c  jz      short loc_180007581
0x18000755e  mov     eax, [rbp+var_20]
0x180007561  mov     rdx, r12
0x180007564  test    rax, rax
0x180007567  jz      short loc_180007575
0x180007569  mov     byte ptr [rdx], 0
0x18000756c  inc     rdx
0x18000756f  sub     rax, 1
0x180007573  jnz     short loc_180007569
0x180007575  mov     rax, [rbx+10h]
0x180007579  mov     rcx, r12
0x18000757c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007581  test    r14, r14
0x180007584  jz      short loc_18000758E
0x180007586  mov     rcx, r14
0x180007589  call    NCryptCloseProtectionDescriptor
0x18000758e  mov     rbx, [rsp+60h+arg_0]
0x180007596  mov     eax, edi
0x180007598  add     rsp, 60h
0x18000759c  pop     r15
0x18000759e  pop     r14
0x1800075a0  pop     r13
0x1800075a2  pop     r12
0x1800075a4  pop     rdi
0x1800075a5  pop     rsi
0x1800075a6  pop     rbp
0x1800075a7  retn
0x1800075a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075af  lea     rsi, WPP_GLOBAL_Control
0x1800075b6  cmp     rcx, rsi
0x1800075b9  jz      short loc_1800075E9
0x1800075bb  test    byte ptr [rcx+1Ch], 1
0x1800075bf  jz      short loc_1800075E9
0x1800075c1  mov     dword ptr [rsp+60h+var_30], 7D3h
0x1800075c9  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800075d0  mov     [rsp+60h+var_38], rax
0x1800075d5  mov     dword ptr [rsp+60h+var_40], edi
0x1800075d9  mov     rcx, [rcx+10h]
0x1800075dd  lea     r9, aStatus; "Status"
0x1800075e4  call    WPP_SF_sDsd
0x1800075e9  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 2
0x1800075f0  jz      loc_180007559
0x1800075f6  call    I_GetProcessName
0x1800075fb  mov     r8d, [rbp+arg_8]
0x1800075ff  lea     rdx, ETW_LOG_NCRYPT_UNPROTECT_SECRET_FAILED
0x180007606  mov     r9d, edi
0x180007609  mov     [rsp+60h+var_40], rax
0x18000760e  call    McTemplateU0ddz_EventWriteTransfer
0x180007613  jmp     loc_180007559
0x180007618  mov     edi, 80090027h
0x18000761d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007624  lea     rsi, WPP_GLOBAL_Control
0x18000762b  cmp     rcx, rsi
0x18000762e  jz      short loc_180007662
0x180007630  test    byte ptr [rcx+1Ch], 1
0x180007634  jz      short loc_180007662
0x180007636  mov     dword ptr [rsp+60h+var_30], 75Dh
0x18000763e  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007645  mov     [rsp+60h+var_38], rax
0x18000764a  mov     dword ptr [rsp+60h+var_40], 80090027h
0x180007652  mov     rcx, [rcx+10h]
0x180007656  lea     r9, aStatus; "Status"
0x18000765d  call    WPP_SF_sDsd
0x180007662  mov     rbx, [rbp+arg_20]
0x180007666  jmp     short loc_1800075E9
0x180007668  mov     edi, 80090009h
0x18000766d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007674  lea     rsi, WPP_GLOBAL_Control
0x18000767b  cmp     rcx, rsi
0x18000767e  jz      short loc_180007662
0x180007680  test    byte ptr [rcx+1Ch], 1
0x180007684  jz      short loc_180007662
0x180007686  mov     dword ptr [rsp+60h+var_30], 76Fh
0x18000768e  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007695  mov     [rsp+60h+var_38], rax
0x18000769a  mov     dword ptr [rsp+60h+var_40], 80090009h
0x1800076a2  jmp     short loc_180007652
0x1800076a4  mov     rax, [r14+18h]
0x1800076a8  test    rax, rax
0x1800076ab  jz      short loc_1800076B9
0x1800076ad  cmp     dword ptr [rax], 170h
0x1800076b3  jz      loc_1800077A0
0x1800076b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076c0  lea     rsi, WPP_GLOBAL_Control
0x1800076c7  mov     r15d, 80090026h
0x1800076cd  cmp     rcx, rsi
0x1800076d0  jz      short loc_180007708
0x1800076d2  test    byte ptr [rcx+1Ch], 1
0x1800076d6  jz      short loc_180007708
0x1800076d8  mov     rcx, [rcx+10h]
0x1800076dc  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800076e3  mov     dword ptr [rsp+60h+var_30], 260h
0x1800076eb  lea     r9, aStatus; "Status"
0x1800076f2  mov     [rsp+60h+var_38], rax
0x1800076f7  mov     dword ptr [rsp+60h+var_40], r15d
0x1800076fc  call    WPP_SF_sDsd
0x180007701  mov     rcx, cs:WPP_GLOBAL_Control
0x180007708  mov     edi, 80090026h
0x18000770d  cmp     rcx, rsi
0x180007710  jz      loc_1800075E9
0x180007716  test    byte ptr [rcx+1Ch], 1
0x18000771a  jz      loc_1800075E9
0x180007720  mov     dword ptr [rsp+60h+var_30], 7B6h
0x180007728  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000772f  mov     [rsp+60h+var_38], rax
0x180007734  mov     dword ptr [rsp+60h+var_40], r15d
0x180007739  jmp     loc_1800075D9
0x18000773e  mov     rax, [rbp+var_18]
0x180007742  mov     [rsi], rax
0x180007745  jmp     loc_180007557
0x18000774a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007751  lea     rsi, WPP_GLOBAL_Control
0x180007758  cmp     rcx, rsi
0x18000775b  jz      loc_1800075E9
0x180007761  test    byte ptr [rcx+1Ch], 1
0x180007765  jz      loc_1800075E9
0x18000776b  mov     dword ptr [rsp+60h+var_30], 7A1h
0x180007773  jmp     loc_1800075C9
0x180007778  mov     r9d, 788h
0x18000777e  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007785  lea     rdx, aStatus; "Status"
0x18000778c  mov     ecx, eax
0x18000778e  call    DebugTraceError
0x180007793  mov     r14, [rbp+var_18]
0x180007797  mov     r12, [rbp+var_10]
0x18000779b  jmp     loc_1800075E9
0x1800077a0  mov     ecx, [rax+30h]
0x1800077a3  cmp     ecx, r15d
0x1800077a6  jbe     short loc_1800077D0
0x1800077a8  mov     r9d, 7BDh
0x1800077ae  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800077b5  lea     rdx, aStatus; "Status"
0x1800077bc  mov     ecx, 80090005h
0x1800077c1  mov     edi, 80090005h
0x1800077c6  call    DebugTraceError
0x1800077cb  jmp     loc_1800075E9
0x1800077d0  mov     rdx, rcx
0x1800077d3  add     rdx, [rbp+arg_10]
0x1800077d7  sub     r15d, ecx
0x1800077da  jmp     loc_180007530
0x1800077df  mov     [rsi], r14
0x1800077e2  xor     r14d, r14d
0x1800077e5  jmp     loc_180007557
```
