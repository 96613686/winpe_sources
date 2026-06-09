# GetRegisteredClientPages(_PROPSHEETPAGEW * *,ulong *,_CERT_CONTEXT const *)

- ea: `0x180026fac`
- end: `0x180027249`
- name: `?GetRegisteredClientPages@@YAHPEAPEAU_PROPSHEETPAGEW@@PEAKPEBU_CERT_CONTEXT@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(struct _PROPSHEETPAGEW **, unsigned int *, const struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002a710`
- `0x18002aad0`

## callees

- `0x180001f66`
- `0x180026fac`
- `0x18003e582`
- `0x18003e5c0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027051`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002714d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027051`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002714d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027205`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027205`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180027192`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180027192`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027064`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800271f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027064`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800271f3`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x1800271cf`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180027217`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x1800271cf`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180027217`
- `CRYPT32!CryptGetDefaultOIDFunctionAddress` at `0x1800270c4`
- `CRYPT32!CryptGetDefaultOIDFunctionAddress` at `0x1800270c4`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x18002700d`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x18002700d`
- `CRYPT32!CryptGetDefaultOIDDllList` at `0x18002702c`
- `CRYPT32!CryptGetDefaultOIDDllList` at `0x18002707f`
- `CRYPT32!CryptGetDefaultOIDDllList` at `0x18002702c`
- `CRYPT32!CryptGetDefaultOIDDllList` at `0x18002707f`

## pseudocode

```c
__int64 __fastcall GetRegisteredClientPages(HLOCAL *a1, unsigned int *a2, const struct _CERT_CONTEXT *a3)
{
  WCHAR *v6; // rbx
  HCRYPTOIDFUNCSET inited; // rax
  void *v8; // r15
  unsigned int v9; // esi
  WCHAR *v10; // rax
  const WCHAR *i; // rdi
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  struct _PROPSHEETPAGEW *v14; // rax
  struct _PROPSHEETPAGEW *v15; // rdx
  DWORD v16; // ecx
  unsigned int v17; // r8d
  struct _PROPSHEETPAGEW *v18; // rax
  DWORD pcchDllList; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-CCh] BYREF
  HCRYPTOIDFUNCADDR hFuncAddr; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvFuncAddr; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Src[2080]; // [rsp+50h] [rbp-B0h] BYREF

  v21 = 20;
  *a1 = 0;
  *a2 = 0;
  ppvFuncAddr = 0;
  hFuncAddr = 0;
  pcchDllList = 0;
  v6 = 0;
  inited = CryptInitOIDFunctionSet("CryptUIDlgClientCertPropPagesCallback", 0);
  v8 = inited;
  if ( inited )
  {
    if ( CryptGetDefaultOIDDllList(inited, 0, 0, &pcchDllList) )
    {
      v9 = 1;
      if ( pcchDllList )
      {
        v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * pcchDllList);
        v6 = v10;
        if ( v10 )
        {
          *v10 = 0;
          if ( CryptGetDefaultOIDDllList(v8, 0, v10, &pcchDllList) )
          {
            v6[pcchDllList - 1] = 0;
            for ( i = v6; ; i += (int)v12 + 1 )
            {
              if ( !*i )
                goto LABEL_30;
              if ( CryptGetDefaultOIDFunctionAddress(v8, 0, i, 0, &ppvFuncAddr, &hFuncAddr) )
              {
                v21 = 20;
                memset_0(Src, 0, sizeof(Src));
                if ( ((unsigned int (__fastcall *)(const struct _CERT_CONTEXT *, _BYTE *, unsigned int *))ppvFuncAddr)(
                       a3,
                       Src,
                       &v21)
                  && v21 )
                {
                  if ( *a1 )
                  {
                    v17 = v21 + *a2;
                    if ( v17 < v21 || 104 * (unsigned __int64)v17 > 0xFFFFFFFF )
                    {
LABEL_27:
                      v16 = 534;
                      goto LABEL_28;
                    }
                    v18 = (struct _PROPSHEETPAGEW *)LocalReAlloc(*a1, 104 * v17, 2u);
                    v15 = v18;
                    if ( !v18 )
                      goto LABEL_18;
                    *a1 = v18;
                  }
                  else
                  {
                    v13 = 104LL * v21;
                    if ( v13 > 0xFFFFFFFF )
                      goto LABEL_27;
                    v14 = (struct _PROPSHEETPAGEW *)LocalAlloc(0x40u, (unsigned int)v13);
                    *a1 = v14;
                    v15 = v14;
                    if ( !v14 )
                    {
LABEL_18:
                      v16 = -2147024882;
LABEL_28:
                      SetLastError(v16);
                      break;
                    }
                  }
                  memcpy_0(&v15[*a2], Src, 104LL * v21);
                  *a2 += v21;
                }
                CryptFreeOIDFunctionAddress(hFuncAddr, 0);
                hFuncAddr = 0;
                v12 = -1;
                do
                  ++v12;
                while ( i[v12] );
              }
              else
              {
                v12 = -1;
                do
                  ++v12;
                while ( i[v12] );
              }
            }
          }
        }
        else
        {
          SetLastError(0x8007000E);
        }
      }
    }
  }
  v9 = 0;
  if ( v6 )
LABEL_30:
    LocalFree(v6);
  if ( hFuncAddr )
    CryptFreeOIDFunctionAddress(hFuncAddr, 0);
  return v9;
}

```

## disassembly

```asm
0x180026fac  mov     [rsp-8+arg_18], rbx
0x180026fb1  push    rbp
0x180026fb2  push    rsi
0x180026fb3  push    rdi
0x180026fb4  push    r12
0x180026fb6  push    r13
0x180026fb8  push    r14
0x180026fba  push    r15
0x180026fbc  lea     rbp, [rsp-780h]
0x180026fc4  sub     rsp, 880h
0x180026fcb  mov     rax, cs:__security_cookie
0x180026fd2  xor     rax, rsp
0x180026fd5  mov     [rbp+7B0h+var_40], rax
0x180026fdc  xor     edi, edi
0x180026fde  mov     [rsp+8B0h+var_87C], 14h
0x180026fe6  mov     [rcx], rdi
0x180026fe9  mov     r12, rdx
0x180026fec  mov     [rdx], edi
0x180026fee  mov     r14, rcx
0x180026ff1  xor     edx, edx; dwFlags
0x180026ff3  mov     [rsp+8B0h+var_870], rdi
0x180026ff8  lea     rcx, pszFuncName; "CryptUIDlgClientCertPropPagesCallback"
0x180026fff  mov     [rsp+8B0h+hFuncAddr], rdi
0x180027004  mov     r13, r8
0x180027007  mov     [rsp+8B0h+pcchDllList], edi
0x18002700b  mov     ebx, edi
0x18002700d  call    cs:__imp_CryptInitOIDFunctionSet
0x180027013  mov     r15, rax
0x180027016  test    rax, rax
0x180027019  jz      loc_1800271FB
0x18002701f  lea     r9, [rsp+8B0h+pcchDllList]; pcchDllList
0x180027024  xor     r8d, r8d; pwszDllList
0x180027027  xor     edx, edx; dwEncodingType
0x180027029  mov     rcx, rax; hFuncSet
0x18002702c  call    cs:__imp_CryptGetDefaultOIDDllList
0x180027032  test    eax, eax
0x180027034  jz      loc_1800271FB
0x18002703a  lea     esi, [rdi+1]
0x18002703d  cmp     [rsp+8B0h+pcchDllList], esi
0x180027041  jb      loc_1800271FB
0x180027047  mov     edx, [rsp+8B0h+pcchDllList]
0x18002704b  lea     ecx, [rdi+40h]; uFlags
0x18002704e  add     rdx, rdx; uBytes
0x180027051  call    cs:__imp_LocalAlloc
0x180027057  mov     rbx, rax
0x18002705a  test    rax, rax
0x18002705d  jnz     short loc_18002706F
0x18002705f  mov     ecx, 8007000Eh; dwErrCode
0x180027064  call    cs:__imp_SetLastError
0x18002706a  jmp     loc_1800271FB
0x18002706f  lea     r9, [rsp+8B0h+pcchDllList]; pcchDllList
0x180027074  mov     [rax], di
0x180027077  mov     r8, rbx; pwszDllList
0x18002707a  xor     edx, edx; dwEncodingType
0x18002707c  mov     rcx, r15; hFuncSet
0x18002707f  call    cs:__imp_CryptGetDefaultOIDDllList
0x180027085  test    eax, eax
0x180027087  jz      loc_1800271FB
0x18002708d  mov     eax, [rsp+8B0h+pcchDllList]
0x180027091  dec     eax
0x180027093  xor     ecx, ecx
0x180027095  mov     [rbx+rax*2], di
0x180027099  mov     rdi, rbx
0x18002709c  cmp     [rdi], cx
0x18002709f  jz      loc_180027202
0x1800270a5  lea     rax, [rsp+8B0h+hFuncAddr]
0x1800270aa  xor     r9d, r9d; dwFlags
0x1800270ad  mov     [rsp+8B0h+phFuncAddr], rax; phFuncAddr
0x1800270b2  mov     r8, rdi; pwszDll
0x1800270b5  lea     rax, [rsp+8B0h+var_870]
0x1800270ba  xor     edx, edx; dwEncodingType
0x1800270bc  mov     rcx, r15; hFuncSet
0x1800270bf  mov     [rsp+8B0h+ppvFuncAddr], rax; ppvFuncAddr
0x1800270c4  call    cs:__imp_CryptGetDefaultOIDFunctionAddress
0x1800270ca  xor     ecx, ecx
0x1800270cc  test    eax, eax
0x1800270ce  jnz     short loc_1800270E9
0x1800270d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800270d4  inc     rax
0x1800270d7  cmp     [rdi+rax*2], cx
0x1800270db  jnz     short loc_1800270D4
0x1800270dd  cdqe
0x1800270df  lea     rdi, [rdi+rax*2]
0x1800270e3  add     rdi, 2
0x1800270e7  jmp     short loc_18002709C
0x1800270e9  xor     edx, edx; Val
0x1800270eb  mov     [rsp+8B0h+var_87C], 14h
0x1800270f3  mov     r8d, 820h; Size
0x1800270f9  lea     rcx, [rsp+8B0h+Src]; void *
0x1800270fe  call    memset_0
0x180027103  mov     rax, [rsp+8B0h+var_870]
0x180027108  lea     r8, [rsp+8B0h+var_87C]
0x18002710d  lea     rdx, [rsp+8B0h+Src]
0x180027112  mov     rcx, r13
0x180027115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002711a  test    eax, eax
0x18002711c  jz      loc_1800271C8
0x180027122  mov     ecx, [rsp+8B0h+var_87C]
0x180027126  cmp     ecx, esi
0x180027128  jb      loc_1800271C8
0x18002712e  cmp     qword ptr [r14], 0
0x180027132  jnz     short loc_180027168
0x180027134  imul    rcx, 68h ; 'h'
0x180027138  mov     eax, 0FFFFFFFFh
0x18002713d  cmp     rcx, rax
0x180027140  ja      loc_1800271EE
0x180027146  mov     edx, ecx; uBytes
0x180027148  mov     ecx, 40h ; '@'; uFlags
0x18002714d  call    cs:__imp_LocalAlloc
0x180027153  mov     [r14], rax
0x180027156  mov     rdx, rax
0x180027159  test    rax, rax
0x18002715c  jnz     short loc_1800271A3
0x18002715e  mov     ecx, 8007000Eh
0x180027163  jmp     loc_1800271F3
0x180027168  mov     r8d, [r12]
0x18002716c  add     r8d, ecx
0x18002716f  cmp     r8d, ecx
0x180027172  jb      short loc_1800271EE
0x180027174  mov     eax, r8d
0x180027177  imul    rdx, rax, 68h ; 'h'
0x18002717b  mov     eax, 0FFFFFFFFh
0x180027180  cmp     rdx, rax
0x180027183  ja      short loc_1800271EE
0x180027185  mov     rcx, [r14]; hMem
0x180027188  imul    edx, r8d, 68h ; 'h'; uBytes
0x18002718c  mov     r8d, 2; uFlags
0x180027192  call    cs:__imp_LocalReAlloc
0x180027198  mov     rdx, rax
0x18002719b  test    rax, rax
0x18002719e  jz      short loc_18002715E
0x1800271a0  mov     [r14], rax
0x1800271a3  mov     eax, [rsp+8B0h+var_87C]
0x1800271a7  imul    r8, rax, 68h ; 'h'; Size
0x1800271ab  mov     eax, [r12]
0x1800271af  imul    rcx, rax, 68h ; 'h'
0x1800271b3  add     rcx, rdx; void *
0x1800271b6  lea     rdx, [rsp+8B0h+Src]; Src
0x1800271bb  call    memcpy_0
0x1800271c0  mov     eax, [rsp+8B0h+var_87C]
0x1800271c4  add     [r12], eax
0x1800271c8  mov     rcx, [rsp+8B0h+hFuncAddr]; hFuncAddr
0x1800271cd  xor     edx, edx; dwFlags
0x1800271cf  call    cs:__imp_CryptFreeOIDFunctionAddress
0x1800271d5  xor     ecx, ecx
0x1800271d7  mov     [rsp+8B0h+hFuncAddr], rcx
0x1800271dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800271e0  inc     rax
0x1800271e3  cmp     [rdi+rax*2], cx
0x1800271e7  jnz     short loc_1800271E0
0x1800271e9  jmp     loc_1800270DD
0x1800271ee  mov     ecx, 216h; dwErrCode
0x1800271f3  call    cs:__imp_SetLastError
0x1800271f9  xor     edi, edi
0x1800271fb  mov     esi, edi
0x1800271fd  test    rbx, rbx
0x180027200  jz      short loc_18002720B
0x180027202  mov     rcx, rbx; hMem
0x180027205  call    cs:__imp_LocalFree
0x18002720b  mov     rcx, [rsp+8B0h+hFuncAddr]; hFuncAddr
0x180027210  test    rcx, rcx
0x180027213  jz      short loc_18002721D
0x180027215  xor     edx, edx; dwFlags
0x180027217  call    cs:__imp_CryptFreeOIDFunctionAddress
0x18002721d  mov     eax, esi
0x18002721f  mov     rcx, [rbp+7B0h+var_40]
0x180027226  xor     rcx, rsp; StackCookie
0x180027229  call    __security_check_cookie
0x18002722e  mov     rbx, [rsp+8B0h+arg_18]
0x180027236  add     rsp, 880h
0x18002723d  pop     r15
0x18002723f  pop     r14
0x180027241  pop     r13
0x180027243  pop     r12
0x180027245  pop     rdi
0x180027246  pop     rsi
0x180027247  pop     rbp
0x180027248  retn
```
