# INCORRECT_FMyPrimitiveCryptHMAC(uchar *,ulong,uchar *,ulong,void *,ulong,void * *)

- ea: `0x18000e4b0`
- end: `0x18000e874`
- name: `?INCORRECT_FMyPrimitiveCryptHMAC@@YAHPEAEK0KPEAXKPEAPEAX@Z`
- size: `964`
- prototype: `__int64 __fastcall(unsigned __int8 *, __int64, unsigned __int8 *, ULONG, BCRYPT_ALG_HANDLE hAlgorithm, unsigned int, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014c80`
- `0x180016370`

## callees

- `0x180007f10`
- `0x18000e4b0`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e83b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e83b`
- `bcrypt!BCryptFinishHash` at `0x18000e671`
- `bcrypt!BCryptFinishHash` at `0x18000e671`
- `bcrypt!BCryptDestroyHash` at `0x18000e70a`
- `bcrypt!BCryptDestroyHash` at `0x18000e70a`
- `bcrypt!BCryptHashData` at `0x18000e613`
- `bcrypt!BCryptHashData` at `0x18000e635`
- `bcrypt!BCryptHashData` at `0x18000e6c4`
- `bcrypt!BCryptHashData` at `0x18000e613`
- `bcrypt!BCryptHashData` at `0x18000e635`
- `bcrypt!BCryptHashData` at `0x18000e6c4`
- `bcrypt!BCryptCreateHash` at `0x18000e5ec`
- `bcrypt!BCryptCreateHash` at `0x18000e6a0`
- `bcrypt!BCryptCreateHash` at `0x18000e5ec`
- `bcrypt!BCryptCreateHash` at `0x18000e6a0`

## string_xrefs

- `0x18000e769`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`
- `0x18000e81e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`
- `0x18000e85a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\capiprim.cpp`

## pseudocode

```c
__int64 __fastcall INCORRECT_FMyPrimitiveCryptHMAC(
        unsigned __int8 *a1,
        __int64 a2,
        unsigned __int8 *a3,
        ULONG a4,
        BCRYPT_ALG_HANDLE hAlgorithm,
        unsigned int a6,
        void **a7)
{
  __m128 si128; // xmm3
  unsigned int v11; // r12d
  __m128 v12; // xmm7
  __m128 v13; // xmm9
  __m128 v14; // xmm6
  __m128 v15; // xmm8
  __m128 v16; // xmm7
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  NTSTATUS v20; // eax
  NTSTATUS Hash; // eax
  __int64 v23; // r9
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-C0h] BYREF
  UCHAR pbInput[16]; // [rsp+50h] [rbp-B0h] BYREF
  __m128 v26; // [rsp+60h] [rbp-A0h]
  __m128 v27; // [rsp+70h] [rbp-90h]
  __m128 v28; // [rsp+80h] [rbp-80h]
  UCHAR v29[16]; // [rsp+90h] [rbp-70h] BYREF
  __m128 v30; // [rsp+A0h] [rbp-60h]
  __m128 v31; // [rsp+B0h] [rbp-50h]
  __m128 v32; // [rsp+C0h] [rbp-40h]
  UCHAR pbOutput[64]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(pbInput, 0, 0x40u);
  memset_0(v29, 0, 0x40u);
  phHash = 0;
  if ( a6 == 32782 )
    return 0;
  si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
  v11 = 0;
  v12 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
  v26.m128_i32[0] = *((_DWORD *)a1 + 4);
  v13 = _mm_xor_ps(v12, v31);
  v14 = _mm_xor_ps(v12, v32);
  v30.m128_i32[0] = v26.m128_i32[0];
  v15 = _mm_xor_ps(v12, v30);
  v16 = _mm_xor_ps(v12, *(__m128 *)a1);
  *(__m128 *)pbInput = _mm_xor_ps(si128, *(__m128 *)a1);
  v26 = _mm_xor_ps(si128, v26);
  v27 = _mm_xor_ps(si128, v27);
  v28 = _mm_xor_ps(si128, v28);
  if ( !hAlgorithm )
  {
    DebugTraceError(
      87,
      "ERROR_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
      94);
    SetLastError(0x57u);
    goto LABEL_10;
  }
  v17 = BCryptCreateHash(hAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v17 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ntStatus",
        v17,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
        109);
    goto LABEL_10;
  }
  v18 = BCryptHashData(phHash, pbInput, 0x40u, 0);
  if ( v18 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ntStatus",
        v18,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
        121);
    goto LABEL_10;
  }
  v19 = BCryptHashData(phHash, a3, a4, 0);
  if ( v19 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ntStatus",
        v19,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
        132);
    goto LABEL_10;
  }
  *(__m128 *)v29 = v16;
  v30 = v15;
  v31 = v13;
  v32 = v14;
  v20 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
  if ( v20 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ntStatus",
        v20,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
        145);
    goto LABEL_10;
  }
  Hash = BCryptCreateHash(hAlgorithm, a7, 0, 0, 0, 0, 0);
  if ( Hash < 0 )
  {
    v23 = 161;
LABEL_30:
    DebugTraceError(
      (unsigned int)Hash,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\capiprim.cpp",
      v23);
    goto LABEL_10;
  }
  Hash = BCryptHashData(*a7, v29, 0x54u, 0);
  if ( Hash < 0 )
  {
    v23 = 173;
    goto LABEL_30;
  }
  v11 = 1;
LABEL_10:
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v11;
}

```

## disassembly

```asm
0x18000e4b0  push    rbp
0x18000e4b2  push    rbx
0x18000e4b3  push    rsi
0x18000e4b4  push    rdi
0x18000e4b5  push    r13
0x18000e4b7  push    r14
0x18000e4b9  push    r15
0x18000e4bb  lea     rbp, [rsp-60h]
0x18000e4c0  sub     rsp, 160h
0x18000e4c7  mov     rax, cs:__security_cookie
0x18000e4ce  xor     rax, rsp
0x18000e4d1  mov     [rbp+90h+var_80], rax
0x18000e4d5  mov     rbx, [rbp+90h+hAlgorithm]
0x18000e4dc  mov     rsi, r8
0x18000e4df  mov     rdi, [rbp+90h+arg_30]
0x18000e4e6  mov     r15, rcx
0x18000e4e9  mov     r8d, 40h ; '@'; Size
0x18000e4ef  lea     rcx, [rsp+190h+pbInput]; void *
0x18000e4f4  xor     edx, edx; Val
0x18000e4f6  mov     r14d, r9d
0x18000e4f9  call    memset_0
0x18000e4fe  xor     edx, edx; Val
0x18000e500  lea     rcx, [rbp+90h+var_100]; void *
0x18000e504  mov     r8d, 40h ; '@'; Size
0x18000e50a  call    memset_0
0x18000e50f  xor     r13d, r13d
0x18000e512  cmp     [rbp+90h+arg_28], 800Eh
0x18000e51c  mov     [rsp+190h+phHash], r13
0x18000e521  jz      loc_18000E740
0x18000e527  movdqa  xmm3, cs:__xmm@36363636363636363636363636363636
0x18000e52f  mov     eax, [r15+10h]
0x18000e533  movdqa  xmm0, xmm3
0x18000e537  mov     [rsp+190h+arg_8], r12
0x18000e53f  mov     r12d, r13d
0x18000e542  movaps  [rsp+190h+var_40], xmm6
0x18000e54a  movdqa  xmm6, cs:__xmm@5c5c5c5c5c5c5c5c5c5c5c5c5c5c5c5c
0x18000e552  movaps  [rsp+190h+var_50], xmm7
0x18000e55a  movdqa  xmm7, xmm6
0x18000e55e  movaps  [rsp+190h+var_60], xmm8
0x18000e567  movdqa  xmm8, xmm6
0x18000e56c  mov     dword ptr [rsp+190h+var_130], eax
0x18000e570  movaps  [rsp+190h+var_70], xmm9
0x18000e579  movdqa  xmm9, xmm6
0x18000e57e  xorps   xmm9, [rbp+90h+var_E0]
0x18000e583  xorps   xmm6, [rbp+90h+var_D0]
0x18000e587  mov     dword ptr [rbp+90h+var_F0], eax
0x18000e58a  xorps   xmm8, [rbp+90h+var_F0]
0x18000e58f  movups  xmm1, xmmword ptr [r15]
0x18000e593  xorps   xmm0, xmm1
0x18000e596  xorps   xmm7, xmm1
0x18000e599  movdqu  xmmword ptr [rsp+190h+pbInput], xmm0
0x18000e59f  movdqa  xmm0, xmm3
0x18000e5a3  xorps   xmm0, [rsp+190h+var_130]
0x18000e5a8  movdqu  [rsp+190h+var_130], xmm0
0x18000e5ae  movdqa  xmm0, xmm3
0x18000e5b2  xorps   xmm0, [rsp+190h+var_120]
0x18000e5b7  xorps   xmm3, [rbp+90h+var_110]
0x18000e5bb  movdqu  [rsp+190h+var_120], xmm0
0x18000e5c1  movdqu  [rbp+90h+var_110], xmm3
0x18000e5c6  test    rbx, rbx
0x18000e5c9  jz      loc_18000E818
0x18000e5cf  mov     [rsp+190h+dwFlags], r13d; dwFlags
0x18000e5d4  lea     rdx, [rsp+190h+phHash]; phHash
0x18000e5d9  mov     [rsp+190h+cbSecret], r13d; cbSecret
0x18000e5de  xor     r9d, r9d; cbHashObject
0x18000e5e1  xor     r8d, r8d; pbHashObject
0x18000e5e4  mov     [rsp+190h+pbSecret], r13; pbSecret
0x18000e5e9  mov     rcx, rbx; hAlgorithm
0x18000e5ec  call    cs:__imp_BCryptCreateHash
0x18000e5f3  nop     dword ptr [rax+rax+00h]
0x18000e5f8  test    eax, eax
0x18000e5fa  js      loc_18000E7BC
0x18000e600  mov     rcx, [rsp+190h+phHash]; hHash
0x18000e605  lea     rdx, [rsp+190h+pbInput]; pbInput
0x18000e60a  xor     r9d, r9d; dwFlags
0x18000e60d  mov     r8d, 40h ; '@'; cbInput
0x18000e613  call    cs:__imp_BCryptHashData
0x18000e61a  nop     dword ptr [rax+rax+00h]
0x18000e61f  test    eax, eax
0x18000e621  js      loc_18000E791
0x18000e627  mov     rcx, [rsp+190h+phHash]; hHash
0x18000e62c  xor     r9d, r9d; dwFlags
0x18000e62f  mov     r8d, r14d; cbInput
0x18000e632  mov     rdx, rsi; pbInput
0x18000e635  call    cs:__imp_BCryptHashData
0x18000e63c  nop     dword ptr [rax+rax+00h]
0x18000e641  test    eax, eax
0x18000e643  js      loc_18000E7EA
0x18000e649  mov     rcx, [rsp+190h+phHash]; hHash
0x18000e64e  lea     rdx, [rbp+90h+pbOutput]; pbOutput
0x18000e652  xor     r9d, r9d; dwFlags
0x18000e655  movdqu  xmmword ptr [rbp+90h+var_100], xmm7
0x18000e65a  mov     r8d, 14h; cbOutput
0x18000e660  movdqu  [rbp+90h+var_F0], xmm8
0x18000e666  movdqu  [rbp+90h+var_E0], xmm9
0x18000e66c  movdqu  [rbp+90h+var_D0], xmm6
0x18000e671  call    cs:__imp_BCryptFinishHash
0x18000e678  nop     dword ptr [rax+rax+00h]
0x18000e67d  test    eax, eax
0x18000e67f  js      loc_18000E744
0x18000e685  mov     [rsp+190h+dwFlags], r13d; dwFlags
0x18000e68a  xor     r9d, r9d; cbHashObject
0x18000e68d  mov     [rsp+190h+cbSecret], r13d; cbSecret
0x18000e692  xor     r8d, r8d; pbHashObject
0x18000e695  mov     rdx, rdi; phHash
0x18000e698  mov     [rsp+190h+pbSecret], r13; pbSecret
0x18000e69d  mov     rcx, rbx; hAlgorithm
0x18000e6a0  call    cs:__imp_BCryptCreateHash
0x18000e6a7  nop     dword ptr [rax+rax+00h]
0x18000e6ac  test    eax, eax
0x18000e6ae  js      loc_18000E84C
0x18000e6b4  mov     rcx, [rdi]; hHash
0x18000e6b7  lea     rdx, [rbp+90h+var_100]; pbInput
0x18000e6bb  xor     r9d, r9d; dwFlags
0x18000e6be  mov     r8d, 54h ; 'T'; cbInput
0x18000e6c4  call    cs:__imp_BCryptHashData
0x18000e6cb  nop     dword ptr [rax+rax+00h]
0x18000e6d0  test    eax, eax
0x18000e6d2  js      loc_18000E854
0x18000e6d8  mov     r12d, 1
0x18000e6de  mov     rcx, [rsp+190h+phHash]; hHash
0x18000e6e3  movaps  xmm9, [rsp+190h+var_70]
0x18000e6ec  movaps  xmm8, [rsp+190h+var_60]
0x18000e6f5  movaps  xmm7, [rsp+190h+var_50]
0x18000e6fd  movaps  xmm6, [rsp+190h+var_40]
0x18000e705  test    rcx, rcx
0x18000e708  jz      short loc_18000E716
0x18000e70a  call    cs:__imp_BCryptDestroyHash
0x18000e711  nop     dword ptr [rax+rax+00h]
0x18000e716  mov     eax, r12d
0x18000e719  mov     r12, [rsp+190h+arg_8]
0x18000e721  mov     rcx, [rbp+90h+var_80]
0x18000e725  xor     rcx, rsp; StackCookie
0x18000e728  call    __security_check_cookie
0x18000e72d  add     rsp, 160h
0x18000e734  pop     r15
0x18000e736  pop     r14
0x18000e738  pop     r13
0x18000e73a  pop     rdi
0x18000e73b  pop     rsi
0x18000e73c  pop     rbx
0x18000e73d  pop     rbp
0x18000e73e  retn
0x18000e740  xor     eax, eax
0x18000e742  jmp     short loc_18000E721
0x18000e744  mov     rdx, cs:WPP_GLOBAL_Control
0x18000e74b  lea     rcx, WPP_GLOBAL_Control
0x18000e752  cmp     rdx, rcx
0x18000e755  jz      short loc_18000E6DE
0x18000e757  test    byte ptr [rdx+1Ch], 1
0x18000e75b  jz      short loc_18000E6DE
0x18000e75d  mov     [rsp+190h+dwFlags], 91h
0x18000e765  mov     rcx, [rdx+10h]
0x18000e769  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000e770  mov     qword ptr [rsp+190h+cbSecret], r8
0x18000e775  lea     r9, aNtstatus; "ntStatus"
0x18000e77c  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000e783  mov     dword ptr [rsp+190h+pbSecret], eax
0x18000e787  call    WPP_SF_sDsd
0x18000e78c  jmp     loc_18000E6DE
0x18000e791  mov     rdx, cs:WPP_GLOBAL_Control
0x18000e798  lea     rcx, WPP_GLOBAL_Control
0x18000e79f  cmp     rdx, rcx
0x18000e7a2  jz      loc_18000E6DE
0x18000e7a8  test    byte ptr [rdx+1Ch], 1
0x18000e7ac  jz      loc_18000E6DE
0x18000e7b2  mov     [rsp+190h+dwFlags], 79h ; 'y'
0x18000e7ba  jmp     short loc_18000E765
0x18000e7bc  mov     rdx, cs:WPP_GLOBAL_Control
0x18000e7c3  lea     rcx, WPP_GLOBAL_Control
0x18000e7ca  cmp     rdx, rcx
0x18000e7cd  jz      loc_18000E6DE
0x18000e7d3  test    byte ptr [rdx+1Ch], 1
0x18000e7d7  jz      loc_18000E6DE
0x18000e7dd  mov     [rsp+190h+dwFlags], 6Dh ; 'm'
0x18000e7e5  jmp     loc_18000E765
0x18000e7ea  mov     rdx, cs:WPP_GLOBAL_Control
0x18000e7f1  lea     rcx, WPP_GLOBAL_Control
0x18000e7f8  cmp     rdx, rcx
0x18000e7fb  jz      loc_18000E6DE
0x18000e801  test    byte ptr [rdx+1Ch], 1
0x18000e805  jz      loc_18000E6DE
0x18000e80b  mov     [rsp+190h+dwFlags], 84h
0x18000e813  jmp     loc_18000E765
0x18000e818  mov     r9d, 5Eh ; '^'
0x18000e81e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000e825  lea     rdx, aErrorInvalidPa; "ERROR_INVALID_PARAMETER"
0x18000e82c  mov     ecx, 57h ; 'W'
0x18000e831  call    DebugTraceError
0x18000e836  mov     ecx, 57h ; 'W'; dwErrCode
0x18000e83b  call    cs:__imp_SetLastError
0x18000e842  nop     dword ptr [rax+rax+00h]
0x18000e847  jmp     loc_18000E6DE
0x18000e84c  mov     r9d, 0A1h
0x18000e852  jmp     short loc_18000E85A
0x18000e854  mov     r9d, 0ADh
0x18000e85a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000e861  mov     ecx, eax
0x18000e863  lea     rdx, aNtstatus; "ntStatus"
0x18000e86a  call    DebugTraceError
0x18000e86f  jmp     loc_18000E6DE
```
