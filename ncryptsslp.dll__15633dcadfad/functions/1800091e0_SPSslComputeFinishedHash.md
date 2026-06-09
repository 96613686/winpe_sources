# SPSslComputeFinishedHash

- ea: `0x1800091e0`
- end: `0x1800097ea`
- name: `SPSslComputeFinishedHash`
- size: `1546`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int *, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000860c`
- `0x180009160`
- `0x1800091e0`
- `0x18000a120`
- `0x18000b594`
- `0x18000b654`
- `0x180018ac0`
- `0x18001fd90`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptDuplicateHash` at `0x1800093fa`
- `bcrypt!BCryptDuplicateHash` at `0x1800096ba`
- `bcrypt!BCryptDuplicateHash` at `0x1800093fa`
- `bcrypt!BCryptDuplicateHash` at `0x1800096ba`
- `bcrypt!BCryptDestroyHash` at `0x18000945d`
- `bcrypt!BCryptDestroyHash` at `0x1800097df`
- `bcrypt!BCryptDestroyHash` at `0x18000945d`
- `bcrypt!BCryptDestroyHash` at `0x1800097df`

## string_xrefs

- `0x18000934c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800094d6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009595`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800095ea`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009660`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009728`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180009770`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslComputeFinishedHash(_DWORD *a1, unsigned int *a2, __int64 a3, __int64 a4, int a5, int a6)
{
  __int64 v7; // rax
  __int64 v8; // r8
  unsigned int *v9; // rdi
  _DWORD *v10; // r14
  unsigned int v11; // ecx
  _DWORD *v12; // rax
  UCHAR *p_phNewHash; // rsi
  unsigned int v14; // r13d
  __int64 v15; // r15
  UCHAR *v16; // rax
  __int64 v17; // r9
  NTSTATUS v18; // r15d
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  void *v24; // rcx
  int v25; // eax
  _QWORD *v27; // rcx
  int v28; // eax
  __int64 v29; // [rsp+0h] [rbp-40h] BYREF
  ULONG dwFlags[2]; // [rsp+20h] [rbp-20h]
  const char *v31; // [rsp+28h] [rbp-18h]
  int v32; // [rsp+30h] [rbp-10h]
  __int64 v33; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+48h] [rbp+8h] BYREF
  unsigned int *v35; // [rsp+50h] [rbp+10h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+58h] [rbp+18h] BYREF

  v7 = a4;
  v8 = 0;
  v33 = a4;
  v9 = a2;
  v10 = a1;
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
    v10 = 0;
  if ( a2 )
  {
    v11 = *a2;
    v12 = a2 + 1;
    if ( *a2 < 0x50 || *v12 != 1936944181 )
      a2 = 0;
    v35 = a2;
    if ( v11 >= 0x70 && *v12 == 1936944179 )
    {
      v7 = a4;
      goto LABEL_13;
    }
    v7 = a4;
  }
  else
  {
    a2 = 0;
    v35 = 0;
  }
  v9 = 0;
LABEL_13:
  if ( !a3 || *(_DWORD *)a3 < 0x30u || *(_DWORD *)(a3 + 4) != 1936944178 )
    a3 = 0;
  phNewHash = 0;
  p_phNewHash = 0;
  hHash = 0;
  if ( !v10 || !a3 )
  {
    v18 = -2146893786;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v18;
    v32 = 753;
    goto LABEL_70;
  }
  if ( !v7 || !a5 )
  {
    v17 = 760;
    goto LABEL_31;
  }
  if ( (a6 & 0xFFFFFFFC) != 0 )
  {
    v18 = -2146893815;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v18;
    v32 = 768;
    v31 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
    dwFlags[0] = -2146893815;
    goto LABEL_66;
  }
  if ( v9 && ((v9[27] - 4) & 0xFFFFFFFB) == 0 )
  {
    v14 = v9[2];
    if ( v14 != 772 )
    {
      v18 = -2146893783;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v18;
      v32 = 783;
      v31 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
      dwFlags[0] = -2146893783;
      goto LABEL_66;
    }
    goto LABEL_25;
  }
  if ( !a2 )
  {
    v18 = -2146893786;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v18;
    v32 = 806;
LABEL_70:
    v31 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
    dwFlags[0] = -2146893786;
    goto LABEL_66;
  }
  v14 = a2[2];
  if ( v14 - 768 > 3 && v14 != 65277 && v14 != 65279 )
  {
    v18 = -2146893783;
    DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 799);
    goto LABEL_46;
  }
LABEL_25:
  v15 = (unsigned int)(*(_DWORD *)(a3 + 24) + *(_DWORD *)(a3 + 40));
  if ( (unsigned int)v15 < *(_DWORD *)(a3 + 24) )
  {
    v17 = 818;
LABEL_31:
    v18 = -2146893785;
    v19 = 2148073511LL;
    goto LABEL_32;
  }
  if ( !(_DWORD)v15 )
    goto LABEL_97;
  if ( (unsigned int)v15 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_97;
  a2 = (unsigned int *)((unsigned int)v15 + g_ulAdditionalProbeSize + 8);
  if ( (unsigned __int64)a2 < (unsigned int)v15
    || !(unsigned int)VerifyStackAvailable((unsigned int)v15 + g_ulAdditionalProbeSize + 8) )
  {
    goto LABEL_97;
  }
  v20 = (unsigned int)v15 + 23LL;
  if ( v20 <= (unsigned __int64)(unsigned int)v15 + 8 )
    v20 = 0xFFFFFFFFFFFFFF0LL;
  v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
  v22 = alloca(v21);
  v23 = alloca(v21);
  p_phNewHash = (UCHAR *)&v33;
  if ( &v29 == (__int64 *)-64LL || (LODWORD(v33) = 1801679955, (p_phNewHash = (UCHAR *)&phNewHash) == 0) )
  {
LABEL_97:
    if ( v15 + 8 >= (unsigned __int64)(unsigned int)v15 )
    {
      v16 = (UCHAR *)((__int64 (__fastcall *)(__int64, unsigned int *, __int64))g_pfnAllocate)(v15 + 8, a2, v8);
      p_phNewHash = v16;
      if ( v16 )
      {
        *(_DWORD *)v16 = 1885431112;
        p_phNewHash = v16 + 8;
      }
    }
  }
  if ( !p_phNewHash )
  {
    v18 = -2146893810;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_46;
    v32 = 827;
    v31 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
    dwFlags[0] = -2146893810;
    goto LABEL_66;
  }
  v18 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(a3 + 16), &phNewHash, p_phNewHash, *(_DWORD *)(a3 + 24), 0);
  if ( v18 < 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_46;
    v32 = 839;
LABEL_65:
    v31 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
    dwFlags[0] = v18;
LABEL_66:
    WPP_SF_sDsd(v27[2], (_DWORD)a2, v8, (unsigned int)"Status", dwFlags[0], (__int64)v31, v32);
    goto LABEL_46;
  }
  v24 = *(void **)(a3 + 32);
  if ( v24 )
  {
    v18 = BCryptDuplicateHash(v24, &hHash, &p_phNewHash[*(unsigned int *)(a3 + 24)], *(_DWORD *)(a3 + 40), 0);
    if ( v18 < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_46;
      v32 = 857;
      goto LABEL_65;
    }
  }
  if ( v14 == 772 )
  {
    v25 = Tls13ComputeFinishedHash(v10, v9, phNewHash, *(unsigned int *)(a3 + 28), v33, a5);
    v18 = v25;
    if ( v25 >= 0 )
      goto LABEL_45;
    v17 = 878;
    v19 = (unsigned int)v25;
  }
  else
  {
    if ( v14 >= 0x301 )
    {
      v18 = Tls1ComputeFinishedHash(v24, v35, hHash, phNewHash, *(_DWORD *)(a3 + 28), v33, a5, a6);
      if ( v18 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_46;
        v32 = 895;
        goto LABEL_65;
      }
      goto LABEL_45;
    }
    v28 = Ssl3ComputeFinishedHash(v10, v35, hHash, phNewHash, v33, a5, a6);
    v18 = v28;
    if ( v28 >= 0 )
    {
LABEL_45:
      v18 = 0;
      goto LABEL_46;
    }
    v17 = 911;
    v19 = (unsigned int)v28;
  }
LABEL_32:
  DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v17);
LABEL_46:
  if ( phNewHash )
    BCryptDestroyHash(phNewHash);
  if ( hHash )
    BCryptDestroyHash(hHash);
  if ( p_phNewHash && *((_DWORD *)p_phNewHash - 2) == 1885431112 )
    ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_phNewHash - 8);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800091e0  push    rbp
0x1800091e2  push    rbx
0x1800091e3  push    rsi
0x1800091e4  push    rdi
0x1800091e5  push    r12
0x1800091e7  push    r13
0x1800091e9  push    r14
0x1800091eb  push    r15
0x1800091ed  sub     rsp, 78h
0x1800091f1  lea     rbp, [rsp+40h]
0x1800091f6  mov     rax, cs:__security_cookie
0x1800091fd  xor     rax, rbp
0x180009200  mov     [rbp+70h+var_48], rax
0x180009204  mov     rbx, r8
0x180009207  mov     rax, r9
0x18000920a  xor     r8d, r8d
0x18000920d  mov     [rbp+70h+var_70], rax
0x180009211  mov     rdi, rdx
0x180009214  mov     r14, rcx
0x180009217  test    rcx, rcx
0x18000921a  jz      short loc_18000922D
0x18000921c  cmp     dword ptr [rcx], 310h
0x180009222  jb      short loc_18000922D
0x180009224  cmp     dword ptr [rcx+4], 73736C31h
0x18000922b  jz      short loc_180009230
0x18000922d  mov     r14, r8
0x180009230  test    rdx, rdx
0x180009233  jz      loc_180009789
0x180009239  mov     ecx, [rdx]
0x18000923b  lea     rax, [rdx+4]
0x18000923f  cmp     ecx, 50h ; 'P'
0x180009242  jb      short loc_18000924C
0x180009244  cmp     dword ptr [rax], 73736C35h
0x18000924a  jz      short loc_18000924F
0x18000924c  mov     rdx, r8
0x18000924f  mov     [rbp+70h+var_60], rdx
0x180009253  cmp     ecx, 70h ; 'p'
0x180009256  jb      short loc_180009264
0x180009258  cmp     dword ptr [rax], 73736C33h
0x18000925e  jz      loc_180009679
0x180009264  mov     rax, r9
0x180009267  mov     rdi, r8
0x18000926a  test    rbx, rbx
0x18000926d  jz      short loc_18000927D
0x18000926f  cmp     dword ptr [rbx], 30h ; '0'
0x180009272  jb      short loc_18000927D
0x180009274  cmp     dword ptr [rbx+4], 73736C32h
0x18000927b  jz      short loc_180009280
0x18000927d  mov     rbx, r8
0x180009280  mov     [rbp+70h+phNewHash], r8
0x180009284  mov     rsi, r8
0x180009287  mov     [rbp+70h+hHash], r8
0x18000928b  test    r14, r14
0x18000928e  jz      loc_1800095BB
0x180009294  test    rbx, rbx
0x180009297  jz      loc_1800095BB
0x18000929d  test    rax, rax
0x1800092a0  jz      loc_1800097D4
0x1800092a6  mov     r12d, [rbp+70h+arg_20]
0x1800092ad  test    r12d, r12d
0x1800092b0  jz      loc_1800097D4
0x1800092b6  test    [rbp+70h+arg_28], 0FFFFFFFCh
0x1800092c0  jnz     loc_180009741
0x1800092c6  test    rdi, rdi
0x1800092c9  jz      loc_180009499
0x1800092cf  mov     eax, [rdi+6Ch]
0x1800092d2  sub     eax, 4
0x1800092d5  test    eax, 0FFFFFFFBh
0x1800092da  jnz     loc_180009499
0x1800092e0  mov     r13d, [rdi+8]
0x1800092e4  cmp     r13d, 304h
0x1800092eb  jnz     loc_1800096F9
0x1800092f1  mov     r15d, [rbx+28h]
0x1800092f5  add     r15d, [rbx+18h]
0x1800092f9  cmp     r15d, [rbx+18h]
0x1800092fd  jb      short loc_18000933B
0x1800092ff  test    r15d, r15d
0x180009302  jnz     short loc_180009364
0x180009304  mov     eax, r15d
0x180009307  lea     rcx, [r15+8]
0x18000930b  cmp     rcx, rax
0x18000930e  jb      loc_1800093DA
0x180009314  mov     rax, cs:g_pfnAllocate
0x18000931b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009320  mov     rsi, rax
0x180009323  test    rax, rax
0x180009326  jz      loc_1800093DA
0x18000932c  mov     dword ptr [rax], 70616548h
0x180009332  add     rsi, 8
0x180009336  jmp     loc_1800093DA
0x18000933b  mov     r9d, 332h
0x180009341  mov     r15d, 80090027h
0x180009347  mov     ecx, 80090027h
0x18000934c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009353  lea     rdx, aStatus; "Status"
0x18000935a  call    DebugTraceError
0x18000935f  jmp     loc_180009454
0x180009364  mov     ecx, r15d
0x180009367  cmp     rcx, cs:g_ulMaxStackAllocSize
0x18000936e  ja      short loc_180009304
0x180009370  mov     rdx, cs:g_ulAdditionalProbeSize
0x180009377  add     rdx, 8
0x18000937b  add     rdx, rcx
0x18000937e  cmp     rdx, rcx
0x180009381  jb      short loc_180009304
0x180009383  mov     rcx, rdx
0x180009386  call    VerifyStackAvailable
0x18000938b  test    eax, eax
0x18000938d  jz      loc_180009304
0x180009393  mov     eax, r15d
0x180009396  add     rax, 8
0x18000939a  lea     rcx, [rax+0Fh]
0x18000939e  cmp     rcx, rax
0x1800093a1  ja      short loc_1800093AD
0x1800093a3  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800093ad  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800093b1  mov     rax, rcx
0x1800093b4  call    _alloca_probe
0x1800093b9  sub     rsp, rcx
0x1800093bc  lea     rsi, [rsp+0B0h+var_70]
0x1800093c1  test    rsi, rsi
0x1800093c4  jz      loc_180009304
0x1800093ca  mov     dword ptr [rsi], 6B637453h
0x1800093d0  add     rsi, 8
0x1800093d4  jz      loc_180009304
0x1800093da  test    rsi, rsi
0x1800093dd  jz      loc_180009631
0x1800093e3  mov     r9d, [rbx+18h]; cbHashObject
0x1800093e7  lea     rdx, [rbp+70h+phNewHash]; phNewHash
0x1800093eb  mov     rcx, [rbx+10h]; hHash
0x1800093ef  mov     r8, rsi; pbHashObject
0x1800093f2  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x1800093fa  call    cs:__imp_BCryptDuplicateHash
0x180009400  mov     r15d, eax
0x180009403  test    eax, eax
0x180009405  js      loc_18000956C
0x18000940b  mov     rcx, [rbx+20h]; hHash
0x18000940f  test    rcx, rcx
0x180009412  jnz     loc_1800096A3
0x180009418  cmp     r13d, 304h
0x18000941f  jnz     loc_1800094F9
0x180009425  mov     rax, [rbp+70h+var_70]
0x180009429  mov     rdx, rdi
0x18000942c  mov     r9d, [rbx+1Ch]
0x180009430  mov     rcx, r14
0x180009433  mov     r8, [rbp+70h+phNewHash]
0x180009437  mov     dword ptr [rsp+0B0h+var_88], r12d
0x18000943c  mov     qword ptr [rsp+0B0h+dwFlags], rax
0x180009441  call    Tls13ComputeFinishedHash
0x180009446  mov     r15d, eax
0x180009449  test    eax, eax
0x18000944b  js      loc_180009795
0x180009451  xor     r15d, r15d
0x180009454  mov     rcx, [rbp+70h+phNewHash]; hHash
0x180009458  test    rcx, rcx
0x18000945b  jz      short loc_180009463
0x18000945d  call    cs:__imp_BCryptDestroyHash
0x180009463  mov     rcx, [rbp+70h+hHash]; hHash
0x180009467  test    rcx, rcx
0x18000946a  jnz     loc_1800097DF
0x180009470  test    rsi, rsi
0x180009473  jnz     loc_180009681
0x180009479  mov     eax, r15d
0x18000947c  mov     rcx, [rbp+70h+var_48]
0x180009480  xor     rcx, rbp; StackCookie
0x180009483  call    __security_check_cookie
0x180009488  lea     rsp, [rbp+38h]
0x18000948c  pop     r15
0x18000948e  pop     r14
0x180009490  pop     r13
0x180009492  pop     r12
0x180009494  pop     rdi
0x180009495  pop     rsi
0x180009496  pop     rbx
0x180009497  pop     rbp
0x180009498  retn
0x180009499  test    rdx, rdx
0x18000949c  jz      loc_180009600
0x1800094a2  mov     r13d, [rdx+8]
0x1800094a6  lea     eax, [r13-300h]
0x1800094ad  cmp     eax, 3
0x1800094b0  jbe     loc_1800092F1
0x1800094b6  cmp     r13d, 0FEFDh
0x1800094bd  jz      loc_1800092F1
0x1800094c3  cmp     r13d, 0FEFFh
0x1800094ca  jz      loc_1800092F1
0x1800094d0  mov     r9d, 31Fh
0x1800094d6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800094dd  lea     rdx, aStatus; "Status"
0x1800094e4  mov     ecx, 80090029h
0x1800094e9  mov     r15d, 80090029h
0x1800094ef  call    DebugTraceError
0x1800094f4  jmp     loc_180009454
0x1800094f9  mov     eax, [rbp+70h+arg_28]
0x1800094ff  mov     r9, [rbp+70h+phNewHash]
0x180009503  mov     r8, [rbp+70h+hHash]
0x180009507  mov     rdx, [rbp+70h+var_60]
0x18000950b  cmp     r13d, 301h
0x180009512  jb      loc_1800097A2
0x180009518  mov     [rsp+0B0h+var_78], eax
0x18000951c  mov     rax, [rbp+70h+var_70]
0x180009520  mov     [rsp+0B0h+var_80], r12d
0x180009525  mov     [rsp+0B0h+var_88], rax
0x18000952a  mov     eax, [rbx+1Ch]
0x18000952d  mov     [rsp+0B0h+dwFlags], eax
0x180009531  call    Tls1ComputeFinishedHash
0x180009536  mov     r15d, eax
0x180009539  test    eax, eax
0x18000953b  jns     loc_180009451
0x180009541  mov     rcx, cs:WPP_GLOBAL_Control
0x180009548  lea     rax, WPP_GLOBAL_Control
0x18000954f  cmp     rcx, rax
0x180009552  jz      loc_180009454
0x180009558  test    byte ptr [rcx+1Ch], 1
0x18000955c  jz      loc_180009454
0x180009562  mov     [rsp+0B0h+var_80], 37Fh
0x18000956a  jmp     short loc_180009595
0x18000956c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009573  lea     rax, WPP_GLOBAL_Control
0x18000957a  cmp     rcx, rax
0x18000957d  jz      loc_180009454
0x180009583  test    byte ptr [rcx+1Ch], 1
0x180009587  jz      loc_180009454
0x18000958d  mov     [rsp+0B0h+var_80], 347h
0x180009595  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000959c  mov     [rsp+0B0h+var_88], rax
0x1800095a1  mov     [rsp+0B0h+dwFlags], r15d
0x1800095a6  mov     rcx, [rcx+10h]
0x1800095aa  lea     r9, aStatus; "Status"
0x1800095b1  call    WPP_SF_sDsd
0x1800095b6  jmp     loc_180009454
0x1800095bb  mov     r15d, 80090026h
0x1800095c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095c8  lea     rax, WPP_GLOBAL_Control
0x1800095cf  cmp     rcx, rax
0x1800095d2  jz      loc_180009479
0x1800095d8  test    byte ptr [rcx+1Ch], 1
0x1800095dc  jz      loc_180009479
0x1800095e2  mov     [rsp+0B0h+var_80], 2F1h
0x1800095ea  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800095f1  mov     [rsp+0B0h+var_88], rax
0x1800095f6  mov     [rsp+0B0h+dwFlags], 80090026h
0x1800095fe  jmp     short loc_1800095A6
0x180009600  mov     r15d, 80090026h
0x180009606  mov     rcx, cs:WPP_GLOBAL_Control
0x18000960d  lea     rax, WPP_GLOBAL_Control
0x180009614  cmp     rcx, rax
0x180009617  jz      loc_180009479
0x18000961d  test    byte ptr [rcx+1Ch], 1
0x180009621  jz      loc_180009479
0x180009627  mov     [rsp+0B0h+var_80], 326h
0x18000962f  jmp     short loc_1800095EA
0x180009631  mov     r15d, 8009000Eh
0x180009637  mov     rcx, cs:WPP_GLOBAL_Control
0x18000963e  lea     rax, WPP_GLOBAL_Control
0x180009645  cmp     rcx, rax
0x180009648  jz      loc_180009454
0x18000964e  test    byte ptr [rcx+1Ch], 1
0x180009652  jz      loc_180009454
0x180009658  mov     [rsp+0B0h+var_80], 33Bh
0x180009660  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009667  mov     [rsp+0B0h+var_88], rax
0x18000966c  mov     [rsp+0B0h+dwFlags], 8009000Eh
0x180009674  jmp     loc_1800095A6
0x180009679  mov     rax, r9
0x18000967c  jmp     loc_18000926A
0x180009681  cmp     dword ptr [rsi-8], 70616548h
0x180009688  lea     rcx, [rsi-8]
0x18000968c  jnz     loc_180009479
0x180009692  mov     rax, cs:g_pfnFree
0x180009699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000969e  jmp     loc_180009479
0x1800096a3  mov     r8d, [rbx+18h]
0x1800096a7  lea     rdx, [rbp+70h+hHash]; phNewHash
0x1800096ab  mov     r9d, [rbx+28h]; cbHashObject
0x1800096af  add     r8, rsi; pbHashObject
0x1800096b2  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x1800096ba  call    cs:__imp_BCryptDuplicateHash
0x1800096c0  mov     r15d, eax
0x1800096c3  test    eax, eax
0x1800096c5  jns     loc_180009418
0x1800096cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096d2  lea     rax, WPP_GLOBAL_Control
0x1800096d9  cmp     rcx, rax
0x1800096dc  jz      loc_180009454
0x1800096e2  test    byte ptr [rcx+1Ch], 1
0x1800096e6  jz      loc_180009454
0x1800096ec  mov     [rsp+0B0h+var_80], 359h
0x1800096f4  jmp     loc_180009595
0x1800096f9  mov     r15d, 80090029h
0x1800096ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180009706  lea     rax, WPP_GLOBAL_Control
0x18000970d  cmp     rcx, rax
0x180009710  jz      loc_180009479
0x180009716  test    byte ptr [rcx+1Ch], 1
0x18000971a  jz      loc_180009479
0x180009720  mov     [rsp+0B0h+var_80], 30Fh
0x180009728  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000972f  mov     [rsp+0B0h+var_88], rax
0x180009734  mov     [rsp+0B0h+dwFlags], 80090029h
  ... truncated ...
```
