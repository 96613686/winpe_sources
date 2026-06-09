# AddMachineGuidAndAppContainerSidHashToContainerNameW

- ea: `0x180008840`
- end: `0x180008d55`
- name: `AddMachineGuidAndAppContainerSidHashToContainerNameW`
- size: `1301`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, int, wchar_t *)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ed10`
- `0x180029004`
- `0x18002a0c0`
- `0x1800362fc`

## callees

- `0x1800086d0`
- `0x180008754`
- `0x180008840`
- `0x180008d5c`
- `0x1800093ec`
- `0x18000af80`
- `0x18000b250`
- `0x1800121e4`
- `0x18002095c`
- `0x18003892c`
- `0x180038970`
- `0x180039bf0`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180008beb`
- `ntdll!RtlFreeHeap` at `0x180008beb`

## string_xrefs

- `0x1800088c9`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180008c45`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180008c61`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180008cf2`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180008d2f`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall AddMachineGuidAndAppContainerSidHashToContainerNameW(STRSAFE_PCNZWCH pszSrc, int a2, wchar_t *a3)
{
  size_t v6; // r8
  __int64 v7; // rax
  size_t v9; // r15
  wchar_t *p_P; // rdi
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  const wchar_t *v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  size_t v17; // rdx
  size_t *v18; // r8
  int v19; // ebx
  unsigned int MachineGUID; // eax
  const wchar_t *v21; // rcx
  size_t v22; // r8
  PVOID v23; // rdi
  unsigned int v24; // ebx
  size_t v25; // rdx
  size_t *v26; // r8
  __int64 v27; // rdx
  wchar_t *v28; // rax
  __int64 v29; // r10
  const wchar_t *v30; // r11
  __int64 v31; // rcx
  const wchar_t *v32; // r8
  wchar_t *v33; // r9
  wchar_t *v34; // rcx
  __int64 v35; // rdx
  wchar_t *v36; // rax
  __int64 v37; // rcx
  wchar_t *v38; // r8
  wchar_t *v39; // r9
  wchar_t *v40; // rcx
  __int64 v41; // rdx
  wchar_t *v42; // rax
  __int64 v43; // rcx
  wchar_t *v44; // r8
  wchar_t *v45; // rcx
  __int64 v46; // rax
  wchar_t *v47; // rcx
  wchar_t *v48; // r8
  wchar_t *v49; // rdx
  wchar_t *v50; // rcx
  wchar_t *v52; // rax
  unsigned int HashOfAppContainerSid; // eax
  __int64 v54; // [rsp+0h] [rbp-40h] BYREF
  size_t cchToCopy; // [rsp+20h] [rbp-20h]
  __int64 v56; // [rsp+28h] [rbp-18h]
  int v57; // [rsp+30h] [rbp-10h]
  PVOID P; // [rsp+40h] [rbp+0h] BYREF
  unsigned int v59; // [rsp+48h] [rbp+8h] BYREF
  int v60; // [rsp+4Ch] [rbp+Ch]
  int v61; // [rsp+50h] [rbp+10h]
  int v62; // [rsp+54h] [rbp+14h]
  wchar_t pszDest[40]; // [rsp+60h] [rbp+20h] BYREF
  wchar_t v64[40]; // [rsp+B0h] [rbp+70h] BYREF

  memset_0(pszDest, 0, 0x42u);
  P = 0;
  memset_0(v64, 0, 0x42u);
  v7 = -1;
  while ( pszSrc[++v7] != 0 )
    ;
  v9 = (unsigned int)(v7 + 1);
  p_P = 0;
  v11 = 2 * v9;
  if ( 2 * v9 )
  {
    if ( v11 <= g_ulMaxStackAllocSize )
    {
      v12 = v11 + g_ulAdditionalProbeSize + 8;
      if ( v12 >= v11 )
      {
        if ( (unsigned int)VerifyStackAvailable(v12, "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c") )
        {
          v13 = v11 + 23;
          if ( v11 + 23 <= v11 + 8 )
            v13 = 0xFFFFFFFFFFFFFF0LL;
          v14 = (const wchar_t *)(v13 & 0xFFFFFFFFFFFFFFF0uLL);
          v15 = alloca((signed __int64)v14);
          v16 = alloca((signed __int64)v14);
          p_P = (wchar_t *)&P;
          if ( &v54 != (__int64 *)-64LL )
          {
            LODWORD(P) = 1801679955;
            p_P = (wchar_t *)&v59;
            if ( &v59 )
              goto LABEL_11;
          }
        }
      }
    }
  }
  v14 = (const wchar_t *)(v11 + 8);
  if ( v11 + 8 >= v11 )
  {
    v52 = (wchar_t *)((__int64 (__fastcall *)(const wchar_t *, const char *))g_pfnAllocate)(
                       v14,
                       "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c");
    p_P = v52;
    if ( !v52 )
      goto LABEL_76;
    *(_DWORD *)v52 = 1885431112;
    p_P = v52 + 4;
  }
  if ( p_P )
  {
LABEL_11:
    if ( StringValidateDestW(v14, v9, v6) < 0 )
    {
      if ( (_DWORD)v9 )
        *p_P = 0;
    }
    else
    {
      StringCopyWorkerW_0(p_P, v17, v18, pszSrc, cchToCopy);
    }
    wcslwr(p_P);
    SymCryptMd5(p_P, 2 * v9, &v59);
    v57 = v62;
    LODWORD(v56) = v61;
    LODWORD(cchToCopy) = v60;
    StringCchPrintfW(pszDest, 0x21u, L"%08lx%08lx%08lx%08lx", v59);
    v19 = 0;
    goto LABEL_14;
  }
LABEL_76:
  v19 = 8;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
  {
LABEL_81:
    v24 = v19 | 0x80070000;
    DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 3498);
    return v24;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
      v6,
      (unsigned int)"dwReturn",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
      25);
LABEL_14:
  if ( p_P && *((_DWORD *)p_P - 2) == 1885431112 )
    ((void (__fastcall *)(wchar_t *))g_pfnFree)(p_P - 4);
  if ( v19 )
    goto LABEL_81;
  MachineGUID = GetMachineGUID(&P);
  v23 = P;
  v24 = MachineGUID;
  if ( MachineGUID )
  {
LABEL_67:
    if ( v23 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
    return v24;
  }
  if ( P )
  {
    if ( a2 && (HashOfAppContainerSid = GetHashOfAppContainerSid(v64), (v24 = HashOfAppContainerSid) != 0) )
    {
      DebugTraceError(
        HashOfAppContainerSid,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        3520);
    }
    else
    {
      if ( StringValidateDestW(v21, 0x6Eu, v22) < 0 )
        *a3 = 0;
      else
        StringCopyWorkerW_0(a3, v25, v26, pszDest, cchToCopy);
      v27 = 110;
      v28 = a3;
      while ( *v28 )
      {
        ++v28;
        if ( !--v27 )
        {
          v29 = 2147483646;
          v30 = L"_";
          goto LABEL_32;
        }
      }
      v30 = L"_";
      v29 = 2147483646;
      v31 = 2147483646;
      v32 = L"_";
      v33 = &a3[110 - v27];
      do
      {
        if ( !v31 )
          break;
        if ( !*v32 )
          break;
        *v33++ = *v32++;
        --v31;
        --v27;
      }
      while ( v27 );
      v34 = v33 - 1;
      if ( v27 )
        v34 = v33;
      *v34 = 0;
LABEL_32:
      v35 = 110;
      v36 = a3;
      while ( *v36 )
      {
        ++v36;
        if ( !--v35 )
          goto LABEL_43;
      }
      v37 = 2147483646;
      v38 = (wchar_t *)v23;
      v39 = &a3[110 - v35];
      do
      {
        if ( !v37 )
          break;
        if ( !*v38 )
          break;
        *v39++ = *v38++;
        --v37;
        --v35;
      }
      while ( v35 );
      v40 = v39 - 1;
      if ( v35 )
        v40 = v39;
      *v40 = 0;
LABEL_43:
      if ( a2 )
      {
        v41 = 110;
        v42 = a3;
        while ( *v42 )
        {
          ++v42;
          if ( !--v41 )
            goto LABEL_55;
        }
        v43 = 2147483646;
        v44 = &a3[110 - v41];
        do
        {
          if ( !v43 )
            break;
          if ( !*v30 )
            break;
          *v44++ = *v30++;
          --v43;
          --v41;
        }
        while ( v41 );
        v45 = v44 - 1;
        if ( v41 )
          v45 = v44;
        *v45 = 0;
LABEL_55:
        v46 = 110;
        v47 = a3;
        while ( *v47 )
        {
          ++v47;
          if ( !--v46 )
            goto LABEL_66;
        }
        v48 = v64;
        v49 = &a3[110 - v46];
        do
        {
          if ( !v29 )
            break;
          if ( !*v48 )
            break;
          *v49++ = *v48++;
          --v29;
          --v46;
        }
        while ( v46 );
        v50 = v49 - 1;
        if ( v46 )
          v50 = v49;
        *v50 = 0;
      }
LABEL_66:
      v24 = 0;
    }
    goto LABEL_67;
  }
  return 2148073504LL;
}

```

## disassembly

```asm
0x180008840  push    rbp
0x180008842  push    rsi
0x180008843  push    rdi
0x180008844  push    r12
0x180008846  push    r13
0x180008848  push    r14
0x18000884a  push    r15
0x18000884c  sub     rsp, 110h
0x180008853  lea     rbp, [rsp+40h]
0x180008858  mov     [rbp+100h+arg_8], rbx
0x18000885f  mov     rax, cs:__security_cookie
0x180008866  xor     rax, rbp
0x180008869  mov     [rbp+100h+var_40], rax
0x180008870  mov     r13, r8
0x180008873  mov     r12d, edx
0x180008876  mov     rbx, rcx
0x180008879  xor     edx, edx; Val
0x18000887b  mov     r8d, 42h ; 'B'; Size
0x180008881  lea     rcx, [rbp+100h+pszDest]; void *
0x180008885  call    memset_0
0x18000888a  xor     edx, edx; Val
0x18000888c  mov     [rbp+100h+P], 0
0x180008894  mov     r8d, 42h ; 'B'; Size
0x18000889a  lea     rcx, [rbp+100h+var_90]; void *
0x18000889e  call    memset_0
0x1800088a3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800088aa  nop     word ptr [rax+rax+00h]
0x1800088b0  cmp     word ptr [rbx+rax*2+2], 0
0x1800088b6  lea     rax, [rax+1]
0x1800088ba  jnz     short loc_1800088B0
0x1800088bc  lea     r15d, [rax+1]
0x1800088c0  xor     edi, edi
0x1800088c2  lea     rsi, [r15+r15]
0x1800088c6  mov     r14d, r15d
0x1800088c9  lea     rdx, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800088d0  test    rsi, rsi
0x1800088d3  jz      loc_180008C4C
0x1800088d9  cmp     rsi, cs:g_ulMaxStackAllocSize
0x1800088e0  ja      loc_180008C4C
0x1800088e6  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800088ed  add     rcx, 8
0x1800088f1  add     rcx, rsi
0x1800088f4  cmp     rcx, rsi
0x1800088f7  jb      loc_180008C4C
0x1800088fd  call    VerifyStackAvailable
0x180008902  test    eax, eax
0x180008904  jz      loc_180008C45
0x18000890a  lea     rax, [rsi+8]
0x18000890e  lea     rcx, [rax+0Fh]
0x180008912  cmp     rcx, rax
0x180008915  ja      short loc_180008921
0x180008917  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180008921  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008925  mov     rax, rcx
0x180008928  call    _alloca_probe
0x18000892d  sub     rsp, rcx
0x180008930  lea     rdi, [rsp+140h+P]
0x180008935  test    rdi, rdi
0x180008938  jz      loc_180008C45
0x18000893e  mov     dword ptr [rdi], 6B637453h
0x180008944  add     rdi, 8
0x180008948  jz      loc_180008C45
0x18000894e  mov     rdx, r14; cchDest
0x180008951  call    StringValidateDestW
0x180008956  test    eax, eax
0x180008958  js      loc_180008CCB
0x18000895e  mov     r9, rbx; pszSrc
0x180008961  mov     rcx, rdi; pszDest
0x180008964  call    StringCopyWorkerW_0
0x180008969  mov     rcx, rdi; String
0x18000896c  call    _wcslwr
0x180008971  lea     r8, [rbp+100h+var_F8]
0x180008975  mov     rdx, rsi
0x180008978  mov     rcx, rdi
0x18000897b  call    SymCryptMd5
0x180008980  mov     eax, [rbp+100h+var_EC]
0x180008983  lea     r8, a08lx08lx08lx08; "%08lx%08lx%08lx%08lx"
0x18000898a  mov     r9d, [rbp+100h+var_F8]
0x18000898e  lea     rcx, [rbp+100h+pszDest]; pszDest
0x180008992  mov     [rsp+140h+var_110], eax
0x180008996  mov     edx, 21h ; '!'; cchDest
0x18000899b  mov     eax, dword ptr [rbp+100h+var_F4+4]
0x18000899e  mov     dword ptr [rsp+140h+var_118], eax
0x1800089a2  mov     eax, dword ptr [rbp+100h+var_F4]
0x1800089a5  mov     dword ptr [rsp+140h+cchToCopy], eax; cchToCopy
0x1800089a9  call    StringCchPrintfW
0x1800089ae  xor     ebx, ebx
0x1800089b0  test    rdi, rdi
0x1800089b3  jnz     loc_180008C23
0x1800089b9  test    ebx, ebx
0x1800089bb  jnz     loc_180008CDE
0x1800089c1  lea     rcx, [rbp+100h+P]
0x1800089c5  call    GetMachineGUID
0x1800089ca  mov     rdi, [rbp+100h+P]
0x1800089ce  mov     ebx, eax
0x1800089d0  test    eax, eax
0x1800089d2  jnz     loc_180008BD4
0x1800089d8  test    rdi, rdi
0x1800089db  jz      loc_180008D0C
0x1800089e1  test    r12d, r12d
0x1800089e4  jnz     loc_180008D16
0x1800089ea  mov     ebx, 6Eh ; 'n'
0x1800089ef  mov     edx, ebx; cchDest
0x1800089f1  call    StringValidateDestW
0x1800089f6  test    eax, eax
0x1800089f8  js      loc_180008D49
0x1800089fe  lea     r9, [rbp+100h+pszDest]; pszSrc
0x180008a02  mov     rcx, r13; pszDest
0x180008a05  call    StringCopyWorkerW_0
0x180008a0a  mov     rdx, rbx
0x180008a0d  mov     rax, r13
0x180008a10  cmp     word ptr [rax], 0
0x180008a14  jz      short loc_180008A2F
0x180008a16  add     rax, 2
0x180008a1a  sub     rdx, 1
0x180008a1e  jnz     short loc_180008A10
0x180008a20  mov     r10d, 7FFFFFFEh
0x180008a26  lea     r11, asc_180069770; "_"
0x180008a2d  jmp     short loc_180008A8B
0x180008a2f  mov     rax, rbx
0x180008a32  lea     r11, asc_180069770; "_"
0x180008a39  sub     rax, rdx
0x180008a3c  mov     r10d, 7FFFFFFEh
0x180008a42  mov     ecx, r10d
0x180008a45  mov     r8, r11
0x180008a48  lea     r9, ds:0[rax*2]
0x180008a50  add     r9, r13
0x180008a53  test    rdx, rdx
0x180008a56  jz      short loc_180008A7B
0x180008a58  test    rcx, rcx
0x180008a5b  jz      short loc_180008A7B
0x180008a5d  movzx   eax, word ptr [r8]
0x180008a61  test    ax, ax
0x180008a64  jz      short loc_180008A7B
0x180008a66  mov     [r9], ax
0x180008a6a  add     r8, 2
0x180008a6e  add     r9, 2
0x180008a72  dec     rcx
0x180008a75  sub     rdx, 1
0x180008a79  jnz     short loc_180008A58
0x180008a7b  test    rdx, rdx
0x180008a7e  lea     rcx, [r9-2]
0x180008a82  cmovnz  rcx, r9
0x180008a86  xor     eax, eax
0x180008a88  mov     [rcx], ax
0x180008a8b  mov     rdx, rbx
0x180008a8e  mov     rax, r13
0x180008a91  cmp     word ptr [rax], 0
0x180008a95  jz      short loc_180008AA3
0x180008a97  add     rax, 2
0x180008a9b  sub     rdx, 1
0x180008a9f  jnz     short loc_180008A91
0x180008aa1  jmp     short loc_180008AF3
0x180008aa3  mov     rax, rbx
0x180008aa6  mov     rcx, r10
0x180008aa9  sub     rax, rdx
0x180008aac  mov     r8, rdi
0x180008aaf  lea     r9, ds:0[rax*2]
0x180008ab7  add     r9, r13
0x180008aba  test    rdx, rdx
0x180008abd  jz      short loc_180008AE3
0x180008abf  nop
0x180008ac0  test    rcx, rcx
0x180008ac3  jz      short loc_180008AE3
0x180008ac5  movzx   eax, word ptr [r8]
0x180008ac9  test    ax, ax
0x180008acc  jz      short loc_180008AE3
0x180008ace  mov     [r9], ax
0x180008ad2  add     r8, 2
0x180008ad6  add     r9, 2
0x180008ada  dec     rcx
0x180008add  sub     rdx, 1
0x180008ae1  jnz     short loc_180008AC0
0x180008ae3  test    rdx, rdx
0x180008ae6  lea     rcx, [r9-2]
0x180008aea  cmovnz  rcx, r9
0x180008aee  xor     eax, eax
0x180008af0  mov     [rcx], ax
0x180008af3  test    r12d, r12d
0x180008af6  jz      loc_180008BD2
0x180008afc  mov     rdx, rbx
0x180008aff  mov     rax, r13
0x180008b02  cmp     word ptr [rax], 0
0x180008b06  jz      short loc_180008B14
0x180008b08  add     rax, 2
0x180008b0c  sub     rdx, 1
0x180008b10  jnz     short loc_180008B02
0x180008b12  jmp     short loc_180008B63
0x180008b14  mov     rax, rbx
0x180008b17  mov     rcx, r10
0x180008b1a  sub     rax, rdx
0x180008b1d  lea     r8, ds:0[rax*2]
0x180008b25  add     r8, r13
0x180008b28  test    rdx, rdx
0x180008b2b  jz      short loc_180008B53
0x180008b2d  nop     dword ptr [rax]
0x180008b30  test    rcx, rcx
0x180008b33  jz      short loc_180008B53
0x180008b35  movzx   eax, word ptr [r11]
0x180008b39  test    ax, ax
0x180008b3c  jz      short loc_180008B53
0x180008b3e  mov     [r8], ax
0x180008b42  add     r11, 2
0x180008b46  add     r8, 2
0x180008b4a  dec     rcx
0x180008b4d  sub     rdx, 1
0x180008b51  jnz     short loc_180008B30
0x180008b53  test    rdx, rdx
0x180008b56  lea     rcx, [r8-2]
0x180008b5a  cmovnz  rcx, r8
0x180008b5e  xor     eax, eax
0x180008b60  mov     [rcx], ax
0x180008b63  mov     rax, rbx
0x180008b66  mov     rcx, r13
0x180008b69  nop     dword ptr [rax+00000000h]
0x180008b70  cmp     word ptr [rcx], 0
0x180008b74  jz      short loc_180008B82
0x180008b76  add     rcx, 2
0x180008b7a  sub     rax, 1
0x180008b7e  jnz     short loc_180008B70
0x180008b80  jmp     short loc_180008BD2
0x180008b82  sub     rbx, rax
0x180008b85  lea     r8, [rbp+100h+var_90]
0x180008b89  lea     rdx, ds:0[rbx*2]
0x180008b91  add     rdx, r13
0x180008b94  test    rax, rax
0x180008b97  jz      short loc_180008BC2
0x180008b99  nop     dword ptr [rax+00000000h]
0x180008ba0  test    r10, r10
0x180008ba3  jz      short loc_180008BC2
0x180008ba5  movzx   ecx, word ptr [r8]
0x180008ba9  test    cx, cx
0x180008bac  jz      short loc_180008BC2
0x180008bae  mov     [rdx], cx
0x180008bb1  add     r8, 2
0x180008bb5  add     rdx, 2
0x180008bb9  dec     r10
0x180008bbc  sub     rax, 1
0x180008bc0  jnz     short loc_180008BA0
0x180008bc2  test    rax, rax
0x180008bc5  lea     rcx, [rdx-2]
0x180008bc9  cmovnz  rcx, rdx
0x180008bcd  xor     eax, eax
0x180008bcf  mov     [rcx], ax
0x180008bd2  xor     ebx, ebx
0x180008bd4  test    rdi, rdi
0x180008bd7  jz      short loc_180008BF7
0x180008bd9  mov     rcx, gs:60h
0x180008be2  mov     r8, rdi; P
0x180008be5  xor     edx, edx; Flags
0x180008be7  mov     rcx, [rcx+30h]; HeapHandle
0x180008beb  call    cs:__imp_RtlFreeHeap
0x180008bf2  nop     dword ptr [rax+rax+00h]
0x180008bf7  mov     eax, ebx
0x180008bf9  mov     rcx, [rbp+100h+var_40]
0x180008c00  xor     rcx, rbp; StackCookie
0x180008c03  call    __security_check_cookie
0x180008c08  mov     rbx, [rbp+100h+arg_8]
0x180008c0f  lea     rsp, [rbp+0D0h]
0x180008c16  pop     r15
0x180008c18  pop     r14
0x180008c1a  pop     r13
0x180008c1c  pop     r12
0x180008c1e  pop     rdi
0x180008c1f  pop     rsi
0x180008c20  pop     rbp
0x180008c21  retn
0x180008c23  cmp     dword ptr [rdi-8], 70616548h
0x180008c2a  lea     rcx, [rdi-8]
0x180008c2e  jnz     loc_1800089B9
0x180008c34  mov     rax, cs:g_pfnFree
0x180008c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c40  jmp     loc_1800089B9
0x180008c45  lea     rdx, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008c4c  lea     rcx, [rsi+8]
0x180008c50  cmp     rcx, rsi
0x180008c53  jb      short loc_180008C7A
0x180008c55  mov     rax, cs:g_pfnAllocate
0x180008c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c61  lea     rdx, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008c68  mov     rdi, rax
0x180008c6b  test    rax, rax
0x180008c6e  jz      short loc_180008C83
0x180008c70  mov     dword ptr [rax], 70616548h
0x180008c76  add     rdi, 8
0x180008c7a  test    rdi, rdi
0x180008c7d  jnz     loc_18000894E
0x180008c83  mov     ebx, 8
0x180008c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c8f  lea     rax, WPP_GLOBAL_Control
0x180008c96  cmp     rcx, rax
0x180008c99  jz      short loc_180008CDE
0x180008c9b  test    byte ptr [rcx+1Ch], 1
0x180008c9f  jz      loc_1800089B0
0x180008ca5  mov     rcx, [rcx+10h]
0x180008ca9  lea     r9, aDwreturn; "dwReturn"
0x180008cb0  mov     [rsp+140h+var_110], 0D19h
0x180008cb8  mov     [rsp+140h+var_118], rdx
0x180008cbd  mov     dword ptr [rsp+140h+cchToCopy], ebx
0x180008cc1  call    WPP_SF_sDsd
  ... truncated ...
```
