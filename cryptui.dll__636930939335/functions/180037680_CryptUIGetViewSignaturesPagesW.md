# CryptUIGetViewSignaturesPagesW

- ea: `0x180037680`
- end: `0x1800378ed`
- name: `CryptUIGetViewSignaturesPagesW`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800375c0`

## callees

- `0x1800333f0`
- `0x180034a20`
- `0x180034fa0`
- `0x1800356ec`
- `0x180037680`
- `0x18003e582`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800376fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800377c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800376fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800377c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003781e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800378df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003781e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800378df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800376ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800376ba`
- `CRYPT32!CertOpenStore` at `0x18003777f`
- `CRYPT32!CertOpenStore` at `0x1800377ad`
- `CRYPT32!CertOpenStore` at `0x18003777f`
- `CRYPT32!CertOpenStore` at `0x1800377ad`
- `CRYPT32!CertCloseStore` at `0x180037802`
- `CRYPT32!CertCloseStore` at `0x1800378c3`
- `CRYPT32!CertCloseStore` at `0x180037802`
- `CRYPT32!CertCloseStore` at `0x1800378c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CryptUIGetViewSignaturesPagesW(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v7; // rdi
  _DWORD *v8; // rax
  HCERTSTORE v9; // rax
  HCERTSTORE v10; // rax
  HLOCAL v11; // rcx
  HLOCAL *v12; // rcx
  HLOCAL *v13; // rcx
  HLOCAL *v14; // [rsp+38h] [rbp-28h] BYREF
  char v15; // [rsp+40h] [rbp-20h]
  __int128 pvPara; // [rsp+48h] [rbp-18h] BYREF
  _DWORD *v17; // [rsp+90h] [rbp+30h] BYREF
  HLOCAL *v18; // [rsp+A8h] [rbp+48h] BYREF

  v17 = 0;
  pvPara = 0;
  if ( *(_DWORD *)a1 != 120 )
  {
    SetLastError(0x80070057);
    return 0;
  }
  if ( !(unsigned int)CommonInit() )
    return 0;
  v7 = AllocAndCopyViewSignaturesStruct(a1);
  if ( !v7 )
    return 0;
  v17 = LocalAlloc(0x40u, 0x20u);
  if ( !v17 )
  {
    FreeViewSignaturesStruct(v7);
    return 0;
  }
  v18 = (HLOCAL *)&v17;
  wil::scope_exit__lambda_dc330417dcfce0cfc3eac109669edc85___(&v14, &v18);
  *a3 = 1;
  v8 = v17;
  *(_OWORD *)v17 = 0;
  *((_OWORD *)v8 + 1) = 0;
  *(_QWORD *)v17 = v7;
  v17[4] = 1;
  if ( *(_WORD *)(a1 + 32) == 1 )
  {
    *((_QWORD *)&pvPara + 1) = *(_QWORD *)(a1 + 48);
    LODWORD(pvPara) = *(_DWORD *)(a1 + 40);
    v9 = CertOpenStore((LPCSTR)5, 0x10001u, 0, 0, &pvPara);
    *((_QWORD *)v17 + 3) = v9;
  }
  else if ( *(_WORD *)(a1 + 32) == 2 )
  {
    v10 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, *(const void **)(a1 + 40));
    *((_QWORD *)v17 + 3) = v10;
  }
  v11 = LocalAlloc(0x40u, 104LL * (unsigned int)*a3);
  *(_QWORD *)a2 = v11;
  if ( !v11 )
  {
    FreeViewSignaturesStruct(v7);
    if ( v15 )
    {
      v15 = 0;
      v12 = v14;
      if ( *((_QWORD *)*v14 + 3) )
      {
        CertCloseStore(*((HCERTSTORE *)*v14 + 3), 0);
        v12 = v14;
      }
      FreeViewSignaturesStruct(*(_QWORD *)*v12);
      LocalFree(*v14);
    }
    return 0;
  }
  v15 = 0;
  memset_0(v11, 0, 104LL * (unsigned int)*a3);
  **(_DWORD **)a2 = 104;
  *(_DWORD *)(*(_QWORD *)a2 + 4LL) = 128;
  *(_QWORD *)(*(_QWORD *)a2 + 8LL) = HinstDll;
  *(_QWORD *)(*(_QWORD *)a2 + 16LL) = 145;
  *(_QWORD *)(*(_QWORD *)a2 + 24LL) = 0;
  *(_QWORD *)(*(_QWORD *)a2 + 32LL) = 0;
  *(_QWORD *)(*(_QWORD *)a2 + 40LL) = ViewPageViewSignatures;
  *(_QWORD *)(*(_QWORD *)a2 + 48LL) = v17;
  *(_QWORD *)(*(_QWORD *)a2 + 56LL) = ViewSigsPropPageCallback;
  *(_QWORD *)(*(_QWORD *)a2 + 64LL) = 0;
  *a3 = 1;
  if ( v15 )
  {
    v15 = 0;
    v13 = v14;
    if ( *((_QWORD *)*v14 + 3) )
    {
      CertCloseStore(*((HCERTSTORE *)*v14 + 3), 0);
      v13 = v14;
    }
    FreeViewSignaturesStruct(*(_QWORD *)*v13);
    LocalFree(*v14);
  }
  return 1;
}

```

## disassembly

```asm
0x180037680  mov     [rsp-28h+arg_8], rbx
0x180037685  mov     [rsp-28h+arg_10], rsi
0x18003768a  push    rbp
0x18003768b  push    rdi
0x18003768c  push    r12
0x18003768e  push    r14
0x180037690  push    r15
0x180037692  mov     rbp, rsp
0x180037695  sub     rsp, 60h
0x180037699  mov     r14, r8
0x18003769c  mov     rsi, rdx
0x18003769f  mov     rbx, rcx
0x1800376a2  xor     r15d, r15d
0x1800376a5  mov     [rbp+arg_0], r15
0x1800376a9  xorps   xmm0, xmm0
0x1800376ac  movups  [rbp+var_18], xmm0
0x1800376b0  cmp     dword ptr [rcx], 78h ; 'x'
0x1800376b3  jz      short loc_1800376DB
0x1800376b5  mov     ecx, 80070057h; dwErrCode
0x1800376ba  call    cs:__imp_SetLastError
0x1800376c0  xor     eax, eax
0x1800376c2  lea     r11, [rsp+60h+var_s0]
0x1800376c7  mov     rbx, [r11+38h]
0x1800376cb  mov     rsi, [r11+40h]
0x1800376cf  mov     rsp, r11
0x1800376d2  pop     r15
0x1800376d4  pop     r14
0x1800376d6  pop     r12
0x1800376d8  pop     rdi
0x1800376d9  pop     rbp
0x1800376da  retn
0x1800376db  call    CommonInit
0x1800376e0  test    eax, eax
0x1800376e2  jz      short loc_1800376C0
0x1800376e4  mov     rcx, rbx
0x1800376e7  call    AllocAndCopyViewSignaturesStruct
0x1800376ec  mov     rdi, rax
0x1800376ef  test    rax, rax
0x1800376f2  jz      short loc_1800376C0
0x1800376f4  mov     edx, 20h ; ' '; uBytes
0x1800376f9  lea     ecx, [rdx+20h]; uFlags
0x1800376fc  call    cs:__imp_LocalAlloc
0x180037702  mov     [rbp+arg_0], rax
0x180037706  test    rax, rax
0x180037709  jnz     short loc_180037715
0x18003770b  mov     rcx, rdi
0x18003770e  call    FreeViewSignaturesStruct
0x180037713  jmp     short loc_1800376C0
0x180037715  lea     rax, [rbp+arg_0]
0x180037719  mov     [rbp+arg_18], rax
0x18003771d  lea     rdx, [rbp+arg_18]
0x180037721  lea     rcx, [rbp+var_28]
0x180037725  call    wil__scope_exit__lambda_dc330417dcfce0cfc3eac109669edc85___
0x18003772a  nop
0x18003772b  mov     r12d, 1
0x180037731  mov     [r14], r12d
0x180037734  xorps   xmm0, xmm0
0x180037737  mov     rax, [rbp+arg_0]
0x18003773b  movups  xmmword ptr [rax], xmm0
0x18003773e  movups  xmmword ptr [rax+10h], xmm0
0x180037742  mov     rax, [rbp+arg_0]
0x180037746  mov     [rax], rdi
0x180037749  mov     rax, [rbp+arg_0]
0x18003774d  mov     [rax+10h], r12d
0x180037751  cmp     [rbx+20h], r12w
0x180037756  jnz     short loc_18003778F
0x180037758  mov     rax, [rbx+30h]
0x18003775c  mov     qword ptr [rbp+var_18+8], rax
0x180037760  mov     eax, [rbx+28h]
0x180037763  mov     dword ptr [rbp+var_18], eax
0x180037766  lea     rax, [rbp+var_18]
0x18003776a  mov     [rsp+60h+pvPara], rax; pvPara
0x18003776f  xor     r9d, r9d; dwFlags
0x180037772  xor     r8d, r8d; hCryptProv
0x180037775  mov     edx, 10001h; dwEncodingType
0x18003777a  lea     ecx, [r12+4]; lpszStoreProvider
0x18003777f  call    cs:__imp_CertOpenStore
0x180037785  mov     rcx, [rbp+arg_0]
0x180037789  mov     [rcx+18h], rax
0x18003778d  jmp     short loc_1800377BB
0x18003778f  cmp     word ptr [rbx+20h], 2
0x180037794  jnz     short loc_1800377BB
0x180037796  mov     rax, [rbx+28h]
0x18003779a  mov     [rsp+60h+pvPara], rax; pvPara
0x18003779f  xor     r9d, r9d; dwFlags
0x1800377a2  xor     r8d, r8d; hCryptProv
0x1800377a5  mov     edx, 10001h; dwEncodingType
0x1800377aa  mov     rcx, r12; lpszStoreProvider
0x1800377ad  call    cs:__imp_CertOpenStore
0x1800377b3  mov     rdx, [rbp+arg_0]
0x1800377b7  mov     [rdx+18h], rax
0x1800377bb  mov     eax, [r14]
0x1800377be  imul    rdx, rax, 68h ; 'h'; uBytes
0x1800377c2  mov     ecx, 40h ; '@'; uFlags
0x1800377c7  call    cs:__imp_LocalAlloc
0x1800377cd  mov     rcx, rax; void *
0x1800377d0  mov     [rsi], rax
0x1800377d3  test    rax, rax
0x1800377d6  jnz     short loc_180037829
0x1800377d8  mov     rcx, rdi
0x1800377db  call    FreeViewSignaturesStruct
0x1800377e0  nop
0x1800377e1  cmp     [rbp+var_20], r15b
0x1800377e5  jz      loc_1800376C0
0x1800377eb  mov     [rbp+var_20], r15b
0x1800377ef  mov     rcx, [rbp+var_28]
0x1800377f3  mov     rax, [rcx]
0x1800377f6  cmp     [rax+18h], r15
0x1800377fa  jz      short loc_18003780C
0x1800377fc  xor     edx, edx; dwFlags
0x1800377fe  mov     rcx, [rax+18h]; hCertStore
0x180037802  call    cs:__imp_CertCloseStore
0x180037808  mov     rcx, [rbp+var_28]
0x18003780c  mov     rcx, [rcx]
0x18003780f  mov     rcx, [rcx]
0x180037812  call    FreeViewSignaturesStruct
0x180037817  mov     rcx, [rbp+var_28]
0x18003781b  mov     rcx, [rcx]; hMem
0x18003781e  call    cs:__imp_LocalFree
0x180037824  jmp     loc_1800376C0
0x180037829  mov     [rbp+var_20], r15b
0x18003782d  mov     eax, [r14]
0x180037830  imul    r8, rax, 68h ; 'h'; Size
0x180037834  xor     edx, edx; Val
0x180037836  call    memset_0
0x18003783b  mov     rax, [rsi]
0x18003783e  mov     dword ptr [rax], 68h ; 'h'
0x180037844  mov     rax, [rsi]
0x180037847  mov     dword ptr [rax+4], 80h
0x18003784e  mov     rcx, [rsi]
0x180037851  mov     rax, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * HinstDll
0x180037858  mov     [rcx+8], rax
0x18003785c  mov     rax, [rsi]
0x18003785f  mov     qword ptr [rax+10h], 91h
0x180037867  mov     rax, [rsi]
0x18003786a  mov     [rax+18h], r15
0x18003786e  mov     rax, [rsi]
0x180037871  mov     [rax+20h], r15
0x180037875  mov     rax, [rsi]
0x180037878  lea     rcx, ?ViewPageViewSignatures@@YA_JPEAUHWND__@@I_K_J@Z; ViewPageViewSignatures(HWND__ *,uint,unsigned __int64,__int64)
0x18003787f  mov     [rax+28h], rcx
0x180037883  mov     rcx, [rsi]
0x180037886  mov     rax, [rbp+arg_0]
0x18003788a  mov     [rcx+30h], rax
0x18003788e  mov     rax, [rsi]
0x180037891  lea     rcx, ?ViewSigsPropPageCallback@@YAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z; ViewSigsPropPageCallback(HWND__ *,uint,_PROPSHEETPAGEW *)
0x180037898  mov     [rax+38h], rcx
0x18003789c  mov     rax, [rsi]
0x18003789f  mov     [rax+40h], r15
0x1800378a3  mov     [r14], r12d
0x1800378a6  cmp     [rbp+var_20], r15b
0x1800378aa  jz      short loc_1800378E5
0x1800378ac  mov     [rbp+var_20], r15b
0x1800378b0  mov     rcx, [rbp+var_28]
0x1800378b4  mov     rax, [rcx]
0x1800378b7  cmp     [rax+18h], r15
0x1800378bb  jz      short loc_1800378CD
0x1800378bd  xor     edx, edx; dwFlags
0x1800378bf  mov     rcx, [rax+18h]; hCertStore
0x1800378c3  call    cs:__imp_CertCloseStore
0x1800378c9  mov     rcx, [rbp+var_28]
0x1800378cd  mov     rcx, [rcx]
0x1800378d0  mov     rcx, [rcx]
0x1800378d3  call    FreeViewSignaturesStruct
0x1800378d8  mov     rcx, [rbp+var_28]
0x1800378dc  mov     rcx, [rcx]; hMem
0x1800378df  call    cs:__imp_LocalFree
0x1800378e5  mov     eax, r12d
0x1800378e8  jmp     loc_1800376C2
```
