# DsRolepDnsNameToFlatName

- ea: `0x1800168e0`
- end: `0x180016c5f`
- name: `DsRolepDnsNameToFlatName`
- size: `895`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, wchar_t **, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800068a0`

## callees

- `0x180008fd4`
- `0x180009020`
- `0x1800168e0`
- `0x180020dbc`
- `0x18002c012`
- `0x18002c050`

## import_xrefs

- `msvcrt!wcschr` at `0x180016aac`
- `msvcrt!wcschr` at `0x180016aac`
- `msvcrt!_ultow` at `0x180016b56`
- `msvcrt!_ultow` at `0x180016b56`
- `msvcrt!malloc` at `0x1800169ab`
- `msvcrt!malloc` at `0x1800169ab`
- `msvcrt!free` at `0x1800169f0`
- `msvcrt!free` at `0x1800169f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016a0a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016c00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016a0a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016c00`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18001695f`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180016a60`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180016a6f`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18001695f`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180016a60`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180016a6f`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18001693a`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18001694f`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18001693a`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18001694f`
- `ntdll!RtlEqualSid` at `0x18001698e`
- `ntdll!RtlEqualSid` at `0x18001698e`
- `netjoin!NetpValidateName` at `0x180016ae3`
- `netjoin!NetpValidateName` at `0x180016bc3`
- `netjoin!NetpValidateName` at `0x180016ae3`
- `netjoin!NetpValidateName` at `0x180016bc3`

## pseudocode

```c
__int64 __fastcall DsRolepDnsNameToFlatName(STRSAFE_PCNZWCH pszSrc, wchar_t **a2, _DWORD *a3)
{
  size_t *v5; // r8
  unsigned int v6; // ebx
  void *v7; // rdx
  void *v8; // rcx
  unsigned __int16 *v9; // rsi
  char v10; // di
  __int64 v11; // r15
  _WORD *v12; // rax
  _WORD *v13; // r14
  wchar_t *v14; // rax
  wchar_t **v15; // rsi
  wchar_t *v16; // rax
  unsigned int v17; // eax
  __int64 v18; // r14
  unsigned int v19; // r15d
  __int64 v20; // rax
  wchar_t *v21; // rdi
  size_t v22; // rsi
  __int64 v23; // rax
  unsigned int v24; // eax
  size_t v25; // r14
  wchar_t *v26; // rax
  unsigned __int16 *v28; // [rsp+30h] [rbp-50h] BYREF
  __int64 v29; // [rsp+38h] [rbp-48h] BYREF
  wchar_t **v30; // [rsp+40h] [rbp-40h]
  wchar_t pszDest[8]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v32; // [rsp+58h] [rbp-28h] BYREF
  wchar_t Buffer[4]; // [rsp+68h] [rbp-18h] BYREF

  v30 = a2;
  *a3 = 0;
  v28 = 0;
  v29 = 0;
  DsRolepLogPrintRoutine(4, "Getting NetBIOS name for Dns name %ws\n", pszSrc);
  if ( (int)LsaIQueryInformationPolicyTrusted(5, &v29) >= 0 )
  {
    if ( (int)LsaIQueryInformationPolicyTrusted(12, &v28) >= 0 )
    {
      v6 = 0;
      v7 = (void *)*((_QWORD *)v28 + 8);
      if ( v7 && (v8 = *(void **)(v29 + 16)) != 0 && RtlEqualSid(v8, v7) )
      {
        v9 = v28;
        v10 = 1;
        v11 = *v28;
        v12 = malloc(v11 + 2);
        v13 = v12;
        if ( v12 )
        {
          memcpy_0(v12, *((const void **)v9 + 1), (unsigned int)v11);
          v13[(unsigned __int64)*v28 >> 1] = 0;
          DsRolepLogPrintRoutine(4, "Using existing NetBIOS domain name %ws\n", v13);
          free(v13);
          v9 = v28;
        }
        v14 = (wchar_t *)LocalAlloc(0x40u, 2LL * *v9 + 2);
        v15 = v30;
        *v30 = v14;
        if ( v14 )
        {
          memcpy_0(v14, *((const void **)v28 + 1), *v28);
          v10 = 0;
          (*v15)[(unsigned __int64)*v28 >> 1] = 0;
          *a3 = 3;
        }
      }
      else
      {
        v10 = 1;
      }
      LsaIFree_LSAPR_POLICY_INFORMATION(5, v29);
      LsaIFree_LSAPR_POLICY_INFORMATION(12, v28);
      if ( !v10 )
        return v6;
    }
    else
    {
      LsaIFree_LSAPR_POLICY_INFORMATION(5, v29);
    }
  }
  *(_OWORD *)pszDest = 0;
  v32 = 0;
  StringCopyWorkerW(pszDest, 0x10u, v5, pszSrc, 0xFu);
  v16 = wcschr(pszDest, 0x2Eu);
  if ( v16 )
    *v16 = 0;
  DsRolepLogPrintRoutine(4, "Testing default NetBIOS name %ws\n", pszDest);
  v17 = NetpValidateName(0, pszDest, 0, 0, 4);
  v18 = -1;
  v6 = v17;
  if ( !v17 )
  {
    *a3 = 1;
    do
LABEL_33:
      ++v18;
    while ( pszDest[v18] );
    v25 = v18 + 1;
    v26 = (wchar_t *)LocalAlloc(0x40u, 2 * v25);
    *v30 = v26;
    if ( v26 )
    {
      StringCchCopyW(v26, v25, pszDest);
      DsRolepLogPrintRoutine(4, "Found usable NetBIOS domain name %ws\n", pszDest);
    }
    return v6;
  }
  if ( v17 == 52 )
  {
    v19 = 0;
    v20 = -1;
    do
      ++v20;
    while ( pszDest[v20] );
    v21 = &pszDest[v20];
    v22 = 17 - v20;
    if ( (wchar_t *)((char *)&v32 + 12) == v21 - 1 )
    {
      --v21;
    }
    else
    {
      v21[1] = 0;
      --v22;
    }
    do
    {
      _ultow(v19, Buffer, 10);
      if ( v19 == 10 || v19 == 100 )
      {
        v23 = -1;
        do
          ++v23;
        while ( Buffer[v23] );
        if ( (char *)&v32 + 14 < (char *)&v21[v23] )
        {
          --v21;
          ++v22;
        }
      }
      StringCchCopyW(v21, v22, Buffer);
      DsRolepLogPrintRoutine(4, "Testing default NetBIOS name %ws\n", pszDest);
      v24 = NetpValidateName(0, pszDest, 0, 0, 4);
      v6 = v24;
      if ( v24 != 52 )
        break;
      ++v19;
    }
    while ( v19 < 0x104 );
    if ( !v24 )
      goto LABEL_33;
  }
  return v6;
}

```

## disassembly

```asm
0x1800168e0  mov     [rsp-38h+arg_18], rbx
0x1800168e5  push    rbp
0x1800168e6  push    rsi
0x1800168e7  push    rdi
0x1800168e8  push    r12
0x1800168ea  push    r13
0x1800168ec  push    r14
0x1800168ee  push    r15
0x1800168f0  mov     rbp, rsp
0x1800168f3  sub     rsp, 80h
0x1800168fa  mov     rax, cs:__security_cookie
0x180016901  xor     rax, rsp
0x180016904  mov     [rbp+var_10], rax
0x180016908  xor     esi, esi
0x18001690a  mov     [rbp+var_40], rdx
0x18001690e  mov     r12, r8
0x180016911  mov     [r8], esi
0x180016914  mov     r13, rcx
0x180016917  mov     [rbp+var_50], rsi
0x18001691b  mov     r8, rcx
0x18001691e  mov     [rbp+var_48], rsi
0x180016922  lea     ecx, [rsi+4]
0x180016925  lea     rdx, aGettingNetbios; "Getting NetBIOS name for Dns name %ws\n"
0x18001692c  call    DsRolepLogPrintRoutine
0x180016931  lea     ebx, [rsi+5]
0x180016934  mov     ecx, ebx
0x180016936  lea     rdx, [rbp+var_48]
0x18001693a  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x180016940  test    eax, eax
0x180016942  js      loc_180016A7E
0x180016948  lea     rdx, [rbp+var_50]
0x18001694c  lea     ecx, [rsi+0Ch]
0x18001694f  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x180016955  test    eax, eax
0x180016957  jns     short loc_18001696A
0x180016959  mov     rdx, [rbp+var_48]
0x18001695d  mov     ecx, ebx
0x18001695f  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x180016965  jmp     loc_180016A7E
0x18001696a  mov     rax, [rbp+var_50]
0x18001696e  mov     ebx, esi
0x180016970  mov     rdx, [rax+40h]; Sid2
0x180016974  test    rdx, rdx
0x180016977  jz      loc_180016A54
0x18001697d  mov     rax, [rbp+var_48]
0x180016981  mov     rcx, [rax+10h]; Sid1
0x180016985  test    rcx, rcx
0x180016988  jz      loc_180016A54
0x18001698e  call    cs:__imp_RtlEqualSid
0x180016994  test    al, al
0x180016996  jz      loc_180016A54
0x18001699c  mov     rsi, [rbp+var_50]
0x1800169a0  mov     dil, 1
0x1800169a3  movzx   r15d, word ptr [rsi]
0x1800169a7  lea     rcx, [r15+2]; Size
0x1800169ab  call    cs:__imp_malloc
0x1800169b1  mov     r14, rax
0x1800169b4  test    rax, rax
0x1800169b7  jz      short loc_1800169FA
0x1800169b9  mov     rdx, [rsi+8]; Src
0x1800169bd  mov     r8d, r15d; Size
0x1800169c0  mov     rcx, rax; void *
0x1800169c3  call    memcpy_0
0x1800169c8  mov     rcx, [rbp+var_50]
0x1800169cc  mov     r8, r14
0x1800169cf  movzx   edx, word ptr [rcx]
0x1800169d2  xor     ecx, ecx
0x1800169d4  shr     rdx, 1
0x1800169d7  mov     [r14+rdx*2], cx
0x1800169dc  lea     rdx, aUsingExistingN; "Using existing NetBIOS domain name %ws"...
0x1800169e3  mov     ecx, 4
0x1800169e8  call    DsRolepLogPrintRoutine
0x1800169ed  mov     rcx, r14; Block
0x1800169f0  call    cs:__imp_free
0x1800169f6  mov     rsi, [rbp+var_50]
0x1800169fa  movzx   edx, word ptr [rsi]
0x1800169fd  mov     ecx, 40h ; '@'; uFlags
0x180016a02  lea     rdx, ds:2[rdx*2]; uBytes
0x180016a0a  call    cs:__imp_LocalAlloc
0x180016a10  mov     rsi, [rbp+var_40]
0x180016a14  mov     [rsi], rax
0x180016a17  test    rax, rax
0x180016a1a  jz      short loc_180016A50
0x180016a1c  mov     rdx, [rbp+var_50]
0x180016a20  mov     rcx, rax; void *
0x180016a23  movzx   r8d, word ptr [rdx]; Size
0x180016a27  mov     rdx, [rdx+8]; Src
0x180016a2b  call    memcpy_0
0x180016a30  mov     rcx, [rsi]
0x180016a33  mov     rax, [rbp+var_50]
0x180016a37  movzx   edx, word ptr [rax]
0x180016a3a  shr     rdx, 1
0x180016a3d  xor     esi, esi
0x180016a3f  mov     dil, sil
0x180016a42  mov     [rcx+rdx*2], si
0x180016a46  mov     dword ptr [r12], 3
0x180016a4e  jmp     short loc_180016A57
0x180016a50  xor     esi, esi
0x180016a52  jmp     short loc_180016A57
0x180016a54  mov     dil, 1
0x180016a57  mov     rdx, [rbp+var_48]
0x180016a5b  mov     ecx, 5
0x180016a60  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x180016a66  mov     rdx, [rbp+var_50]
0x180016a6a  mov     ecx, 0Ch
0x180016a6f  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x180016a75  test    dil, dil
0x180016a78  jz      loc_180016C36
0x180016a7e  xorps   xmm0, xmm0
0x180016a81  mov     [rsp+80h+cchToCopy], 0Fh; cchToCopy
0x180016a8a  mov     r9, r13; pszSrc
0x180016a8d  lea     rcx, [rbp+pszDest]; pszDest
0x180016a91  mov     edx, 10h; cchDest
0x180016a96  movups  xmmword ptr [rbp+pszDest], xmm0
0x180016a9a  movups  [rbp+var_28], xmm0
0x180016a9e  call    StringCopyWorkerW
0x180016aa3  mov     edx, 2Eh ; '.'; Ch
0x180016aa8  lea     rcx, [rbp+pszDest]; Str
0x180016aac  call    cs:__imp_wcschr
0x180016ab2  test    rax, rax
0x180016ab5  jz      short loc_180016ABA
0x180016ab7  mov     [rax], si
0x180016aba  lea     r8, [rbp+pszDest]
0x180016abe  mov     ecx, 4
0x180016ac3  lea     rdx, aTestingDefault; "Testing default NetBIOS name %ws\n"
0x180016aca  call    DsRolepLogPrintRoutine
0x180016acf  xor     r9d, r9d
0x180016ad2  mov     dword ptr [rsp+80h+cchToCopy], 4
0x180016ada  xor     r8d, r8d
0x180016add  lea     rdx, [rbp+pszDest]
0x180016ae1  xor     ecx, ecx
0x180016ae3  call    cs:__imp_NetpValidateName
0x180016ae9  or      r14, 0FFFFFFFFFFFFFFFFh
0x180016aed  mov     ebx, eax
0x180016aef  test    eax, eax
0x180016af1  jnz     short loc_180016B00
0x180016af3  mov     dword ptr [r12], 1
0x180016afb  jmp     loc_180016BE6
0x180016b00  cmp     eax, 34h ; '4'
0x180016b03  jnz     loc_180016C36
0x180016b09  mov     r15d, esi
0x180016b0c  lea     rcx, [rbp+pszDest]
0x180016b10  mov     rax, r14
0x180016b13  inc     rax
0x180016b16  cmp     [rcx+rax*2], si
0x180016b1a  jnz     short loc_180016B13
0x180016b1c  lea     rdi, [rbp+pszDest]
0x180016b20  mov     esi, 11h
0x180016b25  lea     rdi, [rdi+rax*2]
0x180016b29  sub     rsi, rax
0x180016b2c  lea     rcx, [rdi-2]
0x180016b30  xor     r12d, r12d
0x180016b33  lea     rax, [rbp+var_28+0Ch]
0x180016b37  cmp     rax, rcx
0x180016b3a  jz      short loc_180016B46
0x180016b3c  mov     [rdi+2], r12w
0x180016b41  dec     rsi
0x180016b44  jmp     short loc_180016B49
0x180016b46  mov     rdi, rcx
0x180016b49  mov     r8d, 0Ah; Radix
0x180016b4f  lea     rdx, [rbp+Buffer]; Buffer
0x180016b53  mov     ecx, r15d; Value
0x180016b56  call    cs:__imp__ultow
0x180016b5c  cmp     r15d, 0Ah
0x180016b60  jz      short loc_180016B68
0x180016b62  cmp     r15d, 64h ; 'd'
0x180016b66  jnz     short loc_180016B8D
0x180016b68  lea     rcx, [rbp+Buffer]
0x180016b6c  mov     rax, r14
0x180016b6f  inc     rax
0x180016b72  cmp     [rcx+rax*2], r12w
0x180016b77  jnz     short loc_180016B6F
0x180016b79  lea     rax, [rdi+rax*2]
0x180016b7d  lea     rcx, [rbp+var_28+0Eh]
0x180016b81  cmp     rcx, rax
0x180016b84  jnb     short loc_180016B8D
0x180016b86  sub     rdi, 2
0x180016b8a  inc     rsi
0x180016b8d  lea     r8, [rbp+Buffer]; pszSrc
0x180016b91  mov     rdx, rsi; cchDest
0x180016b94  mov     rcx, rdi; pszDest
0x180016b97  call    StringCchCopyW
0x180016b9c  mov     ebx, 4
0x180016ba1  lea     r8, [rbp+pszDest]
0x180016ba5  mov     ecx, ebx
0x180016ba7  lea     rdx, aTestingDefault; "Testing default NetBIOS name %ws\n"
0x180016bae  call    DsRolepLogPrintRoutine
0x180016bb3  xor     r9d, r9d
0x180016bb6  mov     dword ptr [rsp+80h+cchToCopy], ebx
0x180016bba  xor     r8d, r8d
0x180016bbd  lea     rdx, [rbp+pszDest]
0x180016bc1  xor     ecx, ecx
0x180016bc3  call    cs:__imp_NetpValidateName
0x180016bc9  mov     ebx, eax
0x180016bcb  cmp     eax, 34h ; '4'
0x180016bce  jnz     short loc_180016BE0
0x180016bd0  inc     r15d
0x180016bd3  cmp     r15d, 104h
0x180016bda  jb      loc_180016B49
0x180016be0  xor     esi, esi
0x180016be2  test    eax, eax
0x180016be4  jnz     short loc_180016C36
0x180016be6  lea     rax, [rbp+pszDest]
0x180016bea  inc     r14
0x180016bed  cmp     [rax+r14*2], si
0x180016bf2  jnz     short loc_180016BEA
0x180016bf4  inc     r14
0x180016bf7  mov     ecx, 40h ; '@'; uFlags
0x180016bfc  lea     rdx, [r14+r14]; uBytes
0x180016c00  call    cs:__imp_LocalAlloc
0x180016c06  mov     rdx, [rbp+var_40]
0x180016c0a  mov     [rdx], rax
0x180016c0d  test    rax, rax
0x180016c10  jz      short loc_180016C36
0x180016c12  lea     r8, [rbp+pszDest]; pszSrc
0x180016c16  mov     rdx, r14; cchDest
0x180016c19  mov     rcx, rax; pszDest
0x180016c1c  call    StringCchCopyW
0x180016c21  lea     r8, [rbp+pszDest]
0x180016c25  mov     ecx, 4
0x180016c2a  lea     rdx, aFoundUsableNet; "Found usable NetBIOS domain name %ws\n"
0x180016c31  call    DsRolepLogPrintRoutine
0x180016c36  mov     eax, ebx
0x180016c38  mov     rcx, [rbp+var_10]
0x180016c3c  xor     rcx, rsp; StackCookie
0x180016c3f  call    __security_check_cookie
0x180016c44  mov     rbx, [rsp+80h+arg_18]
0x180016c4c  add     rsp, 80h
0x180016c53  pop     r15
0x180016c55  pop     r14
0x180016c57  pop     r13
0x180016c59  pop     r12
0x180016c5b  pop     rdi
0x180016c5c  pop     rsi
0x180016c5d  pop     rbp
0x180016c5e  retn
```
