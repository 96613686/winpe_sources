# SignWithUserIdKeyHandle

- ea: `0x18001aaf8`
- end: `0x18001acc3`
- name: `SignWithUserIdKeyHandle`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a5dc`

## callees

- `0x180006538`
- `0x18001aaf8`
- `0x180028380`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac69`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001abd6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001abd6`
- `ncrypt!NCryptSignHash` at `0x18001abb7`
- `ncrypt!NCryptSignHash` at `0x18001ac42`
- `ncrypt!NCryptSignHash` at `0x18001abb7`
- `ncrypt!NCryptSignHash` at `0x18001ac42`
- `bcrypt!BCryptHash` at `0x18001ab64`
- `bcrypt!BCryptHash` at `0x18001ab64`

## string_xrefs

- `0x18001ab72`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18001ac52`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18001ac92`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall SignWithUserIdKeyHandle(
        NCRYPT_KEY_HANDLE a1,
        BYTE *a2,
        DWORD a3,
        void *a4,
        DWORD dwFlags,
        BYTE **a6,
        DWORD *a7)
{
  DWORD v10; // r12d
  int v11; // eax
  DWORD v13; // eax
  SECURITY_STATUS v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rdi
  BYTE *v17; // rax
  BYTE *v18; // rbx
  BYTE *i; // rcx
  BYTE *v20; // r8
  const wchar_t **v21; // rdx
  SECURITY_STATUS v22; // eax
  unsigned int v23; // edi
  DWORD v24; // eax
  DWORD *v25; // rcx
  int pbSignature; // [rsp+20h] [rbp-71h]
  int pbSignaturea; // [rsp+20h] [rbp-71h]
  DWORD pcbResult; // [rsp+40h] [rbp-51h] BYREF
  const wchar_t *v29; // [rsp+48h] [rbp-49h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp-41h]
  DWORD *v31; // [rsp+58h] [rbp-39h]
  char v32; // [rsp+60h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  hKey = a1;
  v31 = a7;
  pcbResult = 0;
  v10 = 32;
  if ( a4 )
  {
    v14 = NCryptSignHash(a1, a4, a2, a3, 0, 0, &pcbResult, dwFlags);
    if ( v14 < 0 )
    {
      v15 = 1680;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)(unsigned int)v14,
        pbSignature);
      return (unsigned int)v14;
    }
    v13 = pcbResult;
  }
  else
  {
    pbSignature = a3;
    v11 = BCryptHash(65, 0, 0, a2);
    if ( v11 < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x683,
               (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
               (const char *)(unsigned int)v11,
               pbSignature);
    v13 = 256;
    pcbResult = 256;
  }
  v16 = v13;
  v17 = (BYTE *)LocalAlloc(0, v13);
  v18 = v17;
  if ( !v17 )
  {
    v14 = -2147024882;
    v15 = 1684;
    goto LABEL_17;
  }
  for ( i = &v17[v16]; v17 != i; ++v17 )
    *v17 = 0;
  v20 = (BYTE *)&v32;
  v29 = L"SHA256";
  v21 = &v29;
  if ( a4 )
  {
    v10 = a3;
    v20 = a2;
    v21 = (const wchar_t **)a4;
  }
  v22 = NCryptSignHash(hKey, v21, v20, v10, v18, pcbResult, &pcbResult, dwFlags);
  v23 = v22;
  if ( v22 >= 0 )
  {
    v24 = pcbResult;
    v25 = v31;
    *a6 = v18;
    *v25 = v24;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69F,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v22,
      pbSignaturea);
    LocalFree(v18);
    return v23;
  }
}

```

## disassembly

```asm
0x18001aaf8  push    rbp
0x18001aafa  push    rbx
0x18001aafb  push    rsi
0x18001aafc  push    rdi
0x18001aafd  push    r12
0x18001aaff  push    r13
0x18001ab01  push    r14
0x18001ab03  push    r15
0x18001ab05  lea     rbp, [rsp-7]
0x18001ab0a  sub     rsp, 98h
0x18001ab11  mov     rax, cs:__security_cookie
0x18001ab18  xor     rax, rsp
0x18001ab1b  mov     [rbp+3Fh+var_50], rax
0x18001ab1f  mov     rax, [rbp+3Fh+arg_30]
0x18001ab23  xor     edi, edi
0x18001ab25  mov     r13, [rbp+3Fh+arg_28]
0x18001ab29  mov     rsi, r9
0x18001ab2c  mov     [rbp+3Fh+hKey], rcx
0x18001ab30  mov     r15d, r8d
0x18001ab33  mov     [rbp+3Fh+var_78], rax
0x18001ab37  mov     r14, rdx
0x18001ab3a  mov     [rbp+3Fh+var_90], edi
0x18001ab3d  lea     r12d, [rdi+20h]
0x18001ab41  test    r9, r9
0x18001ab44  jnz     short loc_18001AB95
0x18001ab46  lea     rax, [rbp+3Fh+var_70]
0x18001ab4a  mov     dword ptr [rsp+0D0h+pcbResult], r12d
0x18001ab4f  mov     qword ptr [rsp+0D0h+cbSignature], rax
0x18001ab54  lea     ecx, [rsi+41h]
0x18001ab57  mov     dword ptr [rsp+0D0h+pbSignature], r8d; int
0x18001ab5c  mov     r9, rdx
0x18001ab5f  xor     r8d, r8d
0x18001ab62  xor     edx, edx
0x18001ab64  call    cs:__imp_BCryptHash
0x18001ab6a  test    eax, eax
0x18001ab6c  jns     short loc_18001AB8B
0x18001ab6e  mov     rcx, [rbp+47h]; this
0x18001ab72  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18001ab79  mov     r9d, eax; char *
0x18001ab7c  mov     edx, 683h; void *
0x18001ab81  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001ab86  jmp     loc_18001ACA3
0x18001ab8b  mov     eax, 100h
0x18001ab90  mov     [rbp+3Fh+var_90], eax
0x18001ab93  jmp     short loc_18001ABD0
0x18001ab95  mov     eax, [rbp+3Fh+arg_20]
0x18001ab98  mov     r9d, r15d; cbHashValue
0x18001ab9b  mov     [rsp+0D0h+dwFlags], eax; dwFlags
0x18001ab9f  mov     r8, r14; pbHashValue
0x18001aba2  lea     rax, [rbp+3Fh+var_90]
0x18001aba6  mov     rdx, rsi; pPaddingInfo
0x18001aba9  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18001abae  mov     [rsp+0D0h+cbSignature], edi; cbSignature
0x18001abb2  mov     [rsp+0D0h+pbSignature], rdi; int
0x18001abb7  call    cs:__imp_NCryptSignHash
0x18001abbd  mov     ebx, eax
0x18001abbf  test    eax, eax
0x18001abc1  jns     short loc_18001ABCD
0x18001abc3  mov     edx, 690h
0x18001abc8  jmp     loc_18001AC8E
0x18001abcd  mov     eax, [rbp+3Fh+var_90]
0x18001abd0  mov     edx, eax; uBytes
0x18001abd2  xor     ecx, ecx; uFlags
0x18001abd4  mov     edi, eax
0x18001abd6  call    cs:__imp_LocalAlloc
0x18001abdc  mov     rbx, rax
0x18001abdf  test    rax, rax
0x18001abe2  jz      loc_18001AC84
0x18001abe8  lea     rcx, [rdi+rax]
0x18001abec  cmp     rax, rcx
0x18001abef  jz      short loc_18001ABFD
0x18001abf1  xor     edx, edx
0x18001abf3  mov     [rax], dl
0x18001abf5  inc     rax
0x18001abf8  cmp     rax, rcx
0x18001abfb  jnz     short loc_18001ABF1
0x18001abfd  mov     ecx, [rbp+3Fh+arg_20]
0x18001ac00  lea     rax, aSha256; "SHA256"
0x18001ac07  mov     [rsp+0D0h+dwFlags], ecx; dwFlags
0x18001ac0b  lea     r8, [rbp+3Fh+var_70]
0x18001ac0f  test    rsi, rsi
0x18001ac12  mov     [rbp+3Fh+var_88], rax
0x18001ac16  mov     eax, [rbp+3Fh+var_90]
0x18001ac19  lea     rcx, [rbp+3Fh+var_90]
0x18001ac1d  mov     [rsp+0D0h+pcbResult], rcx; pcbResult
0x18001ac22  lea     rdx, [rbp+3Fh+var_88]
0x18001ac26  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18001ac2a  cmovnz  r12d, r15d
0x18001ac2e  mov     [rsp+0D0h+cbSignature], eax; cbSignature
0x18001ac32  mov     r9d, r12d; cbHashValue
0x18001ac35  cmovnz  r8, r14; pbHashValue
0x18001ac39  mov     [rsp+0D0h+pbSignature], rbx; int
0x18001ac3e  cmovnz  rdx, rsi; pPaddingInfo
0x18001ac42  call    cs:__imp_NCryptSignHash
0x18001ac48  mov     edi, eax
0x18001ac4a  test    eax, eax
0x18001ac4c  jns     short loc_18001AC73
0x18001ac4e  mov     rcx, [rbp+47h]; this
0x18001ac52  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18001ac59  mov     r9d, eax; char *
0x18001ac5c  mov     edx, 69Fh; void *
0x18001ac61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ac66  mov     rcx, rbx; hMem
0x18001ac69  call    cs:__imp_LocalFree
0x18001ac6f  mov     eax, edi
0x18001ac71  jmp     short loc_18001ACA3
0x18001ac73  mov     eax, [rbp+3Fh+var_90]
0x18001ac76  mov     rcx, [rbp+3Fh+var_78]
0x18001ac7a  mov     [r13+0], rbx
0x18001ac7e  mov     [rcx], eax
0x18001ac80  xor     eax, eax
0x18001ac82  jmp     short loc_18001ACA3
0x18001ac84  mov     ebx, 8007000Eh
0x18001ac89  mov     edx, 694h; void *
0x18001ac8e  mov     rcx, [rbp+47h]; this
0x18001ac92  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18001ac99  mov     r9d, ebx; char *
0x18001ac9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aca1  mov     eax, ebx
0x18001aca3  mov     rcx, [rbp+3Fh+var_50]
0x18001aca7  xor     rcx, rsp; StackCookie
0x18001acaa  call    __security_check_cookie
0x18001acaf  add     rsp, 98h
0x18001acb6  pop     r15
0x18001acb8  pop     r14
0x18001acba  pop     r13
0x18001acbc  pop     r12
0x18001acbe  pop     rdi
0x18001acbf  pop     rsi
0x18001acc0  pop     rbx
0x18001acc1  pop     rbp
0x18001acc2  retn
```
