# SspRc4Key(ulong,void * *,uchar *)

- ea: `0x180006710`
- end: `0x1800069ca`
- name: `?SspRc4Key@@YAJKPEAPEAXPEAE@Z`
- size: `698`
- prototype: `int(unsigned int, void **, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004630`
- `0x180005d30`

## callees

- `0x180006710`
- `0x18002ee7c`
- `0x18002fb50`
- `0x18004c554`
- `0x18006bd74`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800067c0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800067c0`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006780`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800068f2`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006983`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006780`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800068f2`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006983`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800067eb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800067eb`

## pseudocode

```c
__int64 __fastcall SspRc4Key(int a1, void **a2, unsigned __int8 *a3)
{
  BCRYPT_ALG_HANDLE v6; // rbx
  NTSTATUS SymmetricKey; // eax
  unsigned int v8; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // r14d
  __int64 v14; // rdx
  __int64 v15; // r8
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-48h] BYREF
  UCHAR v17[4]; // [rsp+48h] [rbp-40h] BYREF
  int v18; // [rsp+4Ch] [rbp-3Ch]

  phAlgorithm = 0;
  if ( !hMsRc4AlgProvider
    && BCryptOpenAlgorithmProvider(&phAlgorithm, L"RC4", L"Microsoft Primitive Provider", 0) >= 0
    && _InterlockedCompareExchange64((volatile signed __int64 *)&hMsRc4AlgProvider, (signed __int64)phAlgorithm, 0) )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  v6 = hMsRc4AlgProvider;
  phAlgorithm = 0;
  if ( hMsRc4AlgProvider )
  {
    if ( (a1 & 0x80000) != 0 )
    {
      SymmetricKey = BCryptGenerateSymmetricKey(hMsRc4AlgProvider, a2, 0, 0, a3, 0x10u, 0);
      v8 = SymmetricKey;
      if ( SymmetricKey < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 25;
LABEL_33:
          v12 = (unsigned int)SymmetricKey;
          goto LABEL_34;
        }
      }
    }
    else if ( (a1 & 0x80u) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, 16);
      SymmetricKey = BCryptGenerateSymmetricKey(v6, a2, 0, 0, a3, 0x10u, 0);
      v8 = SymmetricKey;
      if ( SymmetricKey < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 29;
          goto LABEL_33;
        }
      }
    }
    else
    {
      if ( a1 >= 0 )
      {
        v13 = 5;
        *(_WORD *)((char *)&v18 + 1) = 14565;
        HIBYTE(v18) = -80;
      }
      else
      {
        v13 = 7;
        HIBYTE(v18) = -96;
      }
      memcpy_0(v17, a3, v13);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v13, *(_DWORD *)v17, v18);
      SymmetricKey = BCryptGenerateSymmetricKey(v6, a2, 0, 0, v17, 8u, 0);
      v8 = SymmetricKey;
      if ( SymmetricKey < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 27;
          goto LABEL_33;
        }
      }
    }
  }
  else
  {
    v8 = -1073741816;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 24;
      v12 = 3221225480LL;
LABEL_34:
      WPP_SF_d(v10[2], v11, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, v12);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180006710  push    rbx
0x180006712  push    rbp
0x180006713  push    rsi
0x180006714  push    rdi
0x180006715  push    r15
0x180006717  sub     rsp, 60h
0x18000671b  mov     rax, cs:__security_cookie
0x180006722  xor     rax, rsp
0x180006725  mov     [rsp+88h+var_38], rax
0x18000672a  xor     r15d, r15d
0x18000672d  mov     rsi, r8
0x180006730  cmp     cs:?hMsRc4AlgProvider@@3PEAXEA, r15; void * hMsRc4AlgProvider
0x180006737  mov     rbp, rdx
0x18000673a  mov     edi, ecx
0x18000673c  mov     [rsp+88h+phAlgorithm], r15
0x180006741  jz      short loc_1800067AA
0x180006743  mov     rbx, cs:?hMsRc4AlgProvider@@3PEAXEA; void * hMsRc4AlgProvider
0x18000674a  mov     [rsp+88h+phAlgorithm], r15
0x18000674f  test    rbx, rbx
0x180006752  jz      loc_1800067F6
0x180006758  bt      edi, 13h
0x18000675c  jnb     loc_180006853
0x180006762  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x180006767  xor     r9d, r9d; cbKeyObject
0x18000676a  mov     [rsp+88h+cbSecret], 10h; cbSecret
0x180006772  xor     r8d, r8d; pbKeyObject
0x180006775  mov     rdx, rbp; phKey
0x180006778  mov     [rsp+88h+pbSecret], rsi; pbSecret
0x18000677d  mov     rcx, rbx; hAlgorithm
0x180006780  call    cs:__imp_BCryptGenerateSymmetricKey
0x180006786  mov     ebx, eax
0x180006788  test    eax, eax
0x18000678a  js      loc_180006828
0x180006790  mov     eax, ebx
0x180006792  mov     rcx, [rsp+88h+var_38]
0x180006797  xor     rcx, rsp; StackCookie
0x18000679a  call    __security_check_cookie
0x18000679f  add     rsp, 60h
0x1800067a3  pop     r15
0x1800067a5  pop     rdi
0x1800067a6  pop     rsi
0x1800067a7  pop     rbp
0x1800067a8  pop     rbx
0x1800067a9  retn
0x1800067aa  xor     r9d, r9d; dwFlags
0x1800067ad  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800067b4  lea     rdx, pszAlgId; "RC4"
0x1800067bb  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x1800067c0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800067c6  test    eax, eax
0x1800067c8  js      loc_180006743
0x1800067ce  mov     rcx, [rsp+88h+phAlgorithm]
0x1800067d3  xor     eax, eax
0x1800067d5  lock cmpxchg cs:?hMsRc4AlgProvider@@3PEAXEA, rcx; void * hMsRc4AlgProvider
0x1800067de  jz      loc_180006743
0x1800067e4  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x1800067e9  xor     edx, edx; dwFlags
0x1800067eb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800067f1  jmp     loc_180006743
0x1800067f6  mov     ebx, 0C0000008h
0x1800067fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006802  lea     rdi, WPP_GLOBAL_Control
0x180006809  cmp     rcx, rdi
0x18000680c  jz      short loc_180006790
0x18000680e  test    byte ptr [rcx+1Ch], 1
0x180006812  jz      loc_180006790
0x180006818  mov     edx, 18h
0x18000681d  mov     r9d, 0C0000008h
0x180006823  jmp     loc_1800069B5
0x180006828  mov     rcx, cs:WPP_GLOBAL_Control
0x18000682f  lea     rdi, WPP_GLOBAL_Control
0x180006836  cmp     rcx, rdi
0x180006839  jz      loc_180006790
0x18000683f  test    byte ptr [rcx+1Ch], 1
0x180006843  jz      loc_180006790
0x180006849  mov     edx, 19h
0x18000684e  jmp     loc_1800069B2
0x180006853  test    dil, dil
0x180006856  jns     loc_18000692E
0x18000685c  mov     [rsp+88h+arg_0], r14
0x180006864  test    edi, edi
0x180006866  jns     short loc_180006875
0x180006868  mov     r14d, 7
0x18000686e  mov     [rsp+88h+var_39], 0A0h
0x180006873  jmp     short loc_180006887
0x180006875  mov     r14d, 5
0x18000687b  mov     [rsp+88h+var_3B], 38E5h
0x180006882  mov     [rsp+88h+var_39], 0B0h
0x180006887  mov     r8d, r14d; Size
0x18000688a  lea     rcx, [rsp+88h+var_40]; void *
0x18000688f  mov     rdx, rsi; Src
0x180006892  call    memcpy_0
0x180006897  mov     rcx, cs:WPP_GLOBAL_Control
0x18000689e  lea     rdi, WPP_GLOBAL_Control
0x1800068a5  cmp     rcx, rdi
0x1800068a8  jz      short loc_1800068CF
0x1800068aa  test    dword ptr [rcx+1Ch], 400h
0x1800068b1  jz      short loc_1800068CF
0x1800068b3  mov     eax, [rsp+4Ch]
0x1800068b7  mov     r9d, r14d
0x1800068ba  mov     rcx, [rcx+10h]
0x1800068be  mov     [rsp+88h+cbSecret], eax
0x1800068c2  mov     eax, dword ptr [rsp+88h+var_40]
0x1800068c6  mov     dword ptr [rsp+88h+pbSecret], eax
0x1800068ca  call    WPP_SF_LLL
0x1800068cf  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x1800068d4  lea     rax, [rsp+88h+var_40]
0x1800068d9  mov     [rsp+88h+cbSecret], 8; cbSecret
0x1800068e1  xor     r9d, r9d; cbKeyObject
0x1800068e4  xor     r8d, r8d; pbKeyObject
0x1800068e7  mov     [rsp+88h+pbSecret], rax; pbSecret
0x1800068ec  mov     rdx, rbp; phKey
0x1800068ef  mov     rcx, rbx; hAlgorithm
0x1800068f2  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800068f8  mov     r14, [rsp+88h+arg_0]
0x180006900  mov     ebx, eax
0x180006902  test    eax, eax
0x180006904  jns     loc_180006790
0x18000690a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006911  cmp     rcx, rdi
0x180006914  jz      loc_180006790
0x18000691a  test    byte ptr [rcx+1Ch], 1
0x18000691e  jz      loc_180006790
0x180006924  mov     edx, 1Bh
0x180006929  jmp     loc_1800069B2
0x18000692e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006935  lea     rdi, WPP_GLOBAL_Control
0x18000693c  cmp     rcx, rdi
0x18000693f  jz      short loc_180006965
0x180006941  test    dword ptr [rcx+1Ch], 400h
0x180006948  jz      short loc_180006965
0x18000694a  mov     rcx, [rcx+10h]
0x18000694e  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x180006955  mov     edx, 1Ch
0x18000695a  mov     r9d, 10h
0x180006960  call    WPP_SF_d
0x180006965  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x18000696a  xor     r9d, r9d; cbKeyObject
0x18000696d  mov     [rsp+88h+cbSecret], 10h; cbSecret
0x180006975  xor     r8d, r8d; pbKeyObject
0x180006978  mov     rdx, rbp; phKey
0x18000697b  mov     [rsp+88h+pbSecret], rsi; pbSecret
0x180006980  mov     rcx, rbx; hAlgorithm
0x180006983  call    cs:__imp_BCryptGenerateSymmetricKey
0x180006989  mov     ebx, eax
0x18000698b  test    eax, eax
0x18000698d  jns     loc_180006790
0x180006993  mov     rcx, cs:WPP_GLOBAL_Control
0x18000699a  cmp     rcx, rdi
0x18000699d  jz      loc_180006790
0x1800069a3  test    byte ptr [rcx+1Ch], 1
0x1800069a7  jz      loc_180006790
0x1800069ad  mov     edx, 1Dh
0x1800069b2  mov     r9d, eax
0x1800069b5  mov     rcx, [rcx+10h]
0x1800069b9  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x1800069c0  call    WPP_SF_d
0x1800069c5  jmp     loc_180006790
```
