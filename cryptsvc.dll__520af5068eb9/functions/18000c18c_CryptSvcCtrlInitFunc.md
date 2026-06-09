# CryptSvcCtrlInitFunc

- ea: `0x18000c18c`
- end: `0x18000c367`
- name: `CryptSvcCtrlInitFunc`
- size: `475`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009e50`

## callees

- `0x18000c18c`
- `0x18000e2f0`
- `0x180011230`
- `0x180017490`
- `0x180018010`

## import_xrefs

- `CRYPT32!CryptGetDefaultOIDDllList` at `0x18000c201`
- `CRYPT32!CryptGetDefaultOIDDllList` at `0x18000c2b8`
- `CRYPT32!CryptGetDefaultOIDDllList` at `0x18000c201`
- `CRYPT32!CryptGetDefaultOIDDllList` at `0x18000c2b8`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x18000c1dd`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x18000c1dd`
- `CRYPT32!CryptGetDefaultOIDFunctionAddress` at `0x18000c303`
- `CRYPT32!CryptGetDefaultOIDFunctionAddress` at `0x18000c303`

## string_xrefs

- `0x18000c1c0`: `CryptsvcDllCtrl`

## pseudocode

```c
int CryptSvcCtrlInitFunc()
{
  DWORD *p_pcchDllList; // rbx
  unsigned int v1; // r14d
  DWORD *inited; // rax
  DWORD *v3; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rcx
  void *v6; // rsp
  void *v7; // rsp
  const WCHAR *v8; // r15
  __int64 v9; // rdi
  unsigned int v10; // ecx
  const WCHAR *v11; // r15
  __int64 v13; // [rsp+0h] [rbp-30h] BYREF
  DWORD pcchDllList; // [rsp+30h] [rbp+0h] BYREF
  __int64 v15; // [rsp+38h] [rbp+8h] BYREF

  pcchDllList = 0;
  qword_180020370[0] = 0;
  p_pcchDllList = 0;
  qword_180020378[0] = (__int64)CertProtectCryptsvcDllCtrl;
  v1 = 1;
  inited = (DWORD *)CryptInitOIDFunctionSet("CryptsvcDllCtrl", 0);
  v3 = inited;
  if ( inited )
  {
    LODWORD(inited) = CryptGetDefaultOIDDllList(inited, 0, 0, &pcchDllList);
    if ( (_DWORD)inited )
    {
      LODWORD(inited) = pcchDllList;
      v4 = 2LL * pcchDllList;
      if ( !v4 )
        goto LABEL_28;
      if ( v4 > g_ulMaxStackAllocSize )
        goto LABEL_28;
      if ( v4 + g_ulAdditionalProbeSize + 8 < v4 )
        goto LABEL_28;
      LODWORD(inited) = VerifyStackAvailable();
      if ( !(_DWORD)inited )
        goto LABEL_28;
      v5 = v4 + 23;
      if ( v4 + 23 <= v4 + 8 )
        v5 = 0xFFFFFFFFFFFFFF0LL;
      LODWORD(inited) = v5 & 0xFFFFFFF0;
      v6 = alloca(v5 & 0xFFFFFFFFFFFFFFF0uLL);
      v7 = alloca(v5 & 0xFFFFFFFFFFFFFFF0uLL);
      p_pcchDllList = &pcchDllList;
      if ( &v13 == (__int64 *)-48LL || (pcchDllList = 1801679955, (p_pcchDllList = (DWORD *)&v15) == 0) )
      {
LABEL_28:
        if ( v4 + 8 >= v4 )
        {
          inited = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcchDllList = inited;
          if ( inited )
          {
            *inited = 1885431112;
            p_pcchDllList = inited + 2;
          }
        }
      }
      if ( p_pcchDllList )
      {
        v8 = (const WCHAR *)p_pcchDllList;
        LODWORD(inited) = CryptGetDefaultOIDDllList(v3, 0, (WCHAR *)p_pcchDllList, &pcchDllList);
        if ( (_DWORD)inited )
        {
          do
          {
            v9 = -1;
            do
              ++v9;
            while ( v8[v9] );
            if ( !v9 )
              break;
            LODWORD(inited) = CryptGetDefaultOIDFunctionAddress(
                                v3,
                                0,
                                v8,
                                0,
                                (void **)&qword_180020370[2 * v1 + 1],
                                (HCRYPTOIDFUNCADDR *)&qword_180020370[2 * v1]);
            v10 = v1 + 1;
            v11 = &v8[v9];
            if ( !(_DWORD)inited )
              v10 = v1;
            v8 = v11 + 1;
            v1 = v10;
          }
          while ( v10 < 5 );
        }
      }
    }
  }
  dword_180020234 = v1;
  if ( p_pcchDllList && *(p_pcchDllList - 2) == 1885431112 )
    LODWORD(inited) = ((__int64 (*)(void))g_pfnFree)();
  return (int)inited;
}

```

## disassembly

```asm
0x18000c18c  push    rbp
0x18000c18e  push    rbx
0x18000c18f  push    rsi
0x18000c190  push    rdi
0x18000c191  push    r12
0x18000c193  push    r13
0x18000c195  push    r14
0x18000c197  push    r15
0x18000c199  sub     rsp, 58h
0x18000c19d  lea     rbp, [rsp+30h]
0x18000c1a2  mov     rax, cs:__security_cookie
0x18000c1a9  xor     rax, rbp
0x18000c1ac  mov     [rbp+60h+var_50], rax
0x18000c1b0  xor     r12d, r12d
0x18000c1b3  lea     rax, CertProtectCryptsvcDllCtrl
0x18000c1ba  xor     edx, edx; dwFlags
0x18000c1bc  mov     [rbp+60h+pcchDllList], r12d
0x18000c1c0  lea     rcx, pszFuncName; "CryptsvcDllCtrl"
0x18000c1c7  mov     cs:qword_180020370, r12
0x18000c1ce  mov     ebx, r12d
0x18000c1d1  mov     cs:qword_180020378, rax
0x18000c1d8  lea     r14d, [r12+1]
0x18000c1dd  call    cs:__imp_CryptInitOIDFunctionSet
0x18000c1e3  mov     rsi, rax
0x18000c1e6  mov     r13d, 70616548h
0x18000c1ec  test    rax, rax
0x18000c1ef  jz      loc_18000C329
0x18000c1f5  lea     r9, [rbp+60h+pcchDllList]; pcchDllList
0x18000c1f9  xor     r8d, r8d; pwszDllList
0x18000c1fc  xor     edx, edx; dwEncodingType
0x18000c1fe  mov     rcx, rax; hFuncSet
0x18000c201  call    cs:__imp_CryptGetDefaultOIDDllList
0x18000c207  test    eax, eax
0x18000c209  jz      loc_18000C329
0x18000c20f  mov     eax, [rbp+60h+pcchDllList]
0x18000c212  lea     rdi, [rax+rax]
0x18000c216  test    rdi, rdi
0x18000c219  jz      short loc_18000C27C
0x18000c21b  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18000c222  ja      short loc_18000C27C
0x18000c224  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000c22b  add     rcx, 8
0x18000c22f  add     rcx, rdi
0x18000c232  cmp     rcx, rdi
0x18000c235  jb      short loc_18000C27C
0x18000c237  call    VerifyStackAvailable
0x18000c23c  test    eax, eax
0x18000c23e  jz      short loc_18000C27C
0x18000c240  lea     rax, [rdi+8]
0x18000c244  lea     rcx, [rax+0Fh]
0x18000c248  cmp     rcx, rax
0x18000c24b  ja      short loc_18000C257
0x18000c24d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000c257  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c25b  mov     rax, rcx
0x18000c25e  call    _alloca_probe
0x18000c263  sub     rsp, rcx
0x18000c266  lea     rbx, [rsp+90h+pcchDllList]
0x18000c26b  test    rbx, rbx
0x18000c26e  jz      short loc_18000C27C
0x18000c270  mov     dword ptr [rbx], 6B637453h
0x18000c276  add     rbx, 8
0x18000c27a  jnz     short loc_18000C2A0
0x18000c27c  lea     rcx, [rdi+8]
0x18000c280  cmp     rcx, rdi
0x18000c283  jb      short loc_18000C2A0
0x18000c285  mov     rax, cs:g_pfnAllocate
0x18000c28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c291  mov     rbx, rax
0x18000c294  test    rax, rax
0x18000c297  jz      short loc_18000C2A0
0x18000c299  mov     [rax], r13d
0x18000c29c  add     rbx, 8
0x18000c2a0  test    rbx, rbx
0x18000c2a3  jz      loc_18000C329
0x18000c2a9  lea     r9, [rbp+60h+pcchDllList]; pcchDllList
0x18000c2ad  mov     r8, rbx; pwszDllList
0x18000c2b0  xor     edx, edx; dwEncodingType
0x18000c2b2  mov     rcx, rsi; hFuncSet
0x18000c2b5  mov     r15, rbx
0x18000c2b8  call    cs:__imp_CryptGetDefaultOIDDllList
0x18000c2be  test    eax, eax
0x18000c2c0  jz      short loc_18000C329
0x18000c2c2  lea     r13, qword_180020370
0x18000c2c9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000c2cd  inc     rdi
0x18000c2d0  cmp     [r15+rdi*2], r12w
0x18000c2d5  jnz     short loc_18000C2CD
0x18000c2d7  test    rdi, rdi
0x18000c2da  jz      short loc_18000C323
0x18000c2dc  mov     eax, r14d
0x18000c2df  xor     r9d, r9d; dwFlags
0x18000c2e2  shl     rax, 4
0x18000c2e6  mov     r8, r15; pwszDll
0x18000c2e9  xor     edx, edx; dwEncodingType
0x18000c2eb  lea     rcx, [rax+r13]
0x18000c2ef  add     rax, 8
0x18000c2f3  mov     [rsp+90h+phFuncAddr], rcx; phFuncAddr
0x18000c2f8  add     rax, r13
0x18000c2fb  mov     rcx, rsi; hFuncSet
0x18000c2fe  mov     [rsp+90h+ppvFuncAddr], rax; ppvFuncAddr
0x18000c303  call    cs:__imp_CryptGetDefaultOIDFunctionAddress
0x18000c309  test    eax, eax
0x18000c30b  lea     ecx, [r14+1]
0x18000c30f  lea     r15, [r15+rdi*2]
0x18000c313  cmovz   ecx, r14d
0x18000c317  add     r15, 2
0x18000c31b  mov     r14d, ecx
0x18000c31e  cmp     ecx, 5
0x18000c321  jb      short loc_18000C2C9
0x18000c323  mov     r13d, 70616548h
0x18000c329  mov     cs:dword_180020234, r14d
0x18000c330  test    rbx, rbx
0x18000c333  jz      short loc_18000C34A
0x18000c335  lea     rcx, [rbx-8]
0x18000c339  cmp     [rcx], r13d
0x18000c33c  jnz     short loc_18000C34A
0x18000c33e  mov     rax, cs:g_pfnFree
0x18000c345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c34a  mov     rcx, [rbp+60h+var_50]
0x18000c34e  xor     rcx, rbp; StackCookie
0x18000c351  call    __security_check_cookie
0x18000c356  lea     rsp, [rbp+28h]
0x18000c35a  pop     r15
0x18000c35c  pop     r14
0x18000c35e  pop     r13
0x18000c360  pop     r12
0x18000c362  pop     rdi
0x18000c363  pop     rsi
0x18000c364  pop     rbx
0x18000c365  pop     rbp
0x18000c366  retn
```
