# NlComputeHMACMessageSignature(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18003e1a0`
- end: `0x18003e3b7`
- name: `?NlComputeHMACMessageSignature@@YAJPEAEK0K0K0KPEAPEAEPEAK@Z`
- size: `535`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, PUCHAR pbInput, ULONG cbInput, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180059ecc`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18003e1a0`
- `0x18003e3c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e236`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e261`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e236`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e261`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e369`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e37d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e369`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e37d`
- `bcrypt!BCryptHashData` at `0x18003e2e0`
- `bcrypt!BCryptHashData` at `0x18003e2e0`
- `bcrypt!BCryptFinishHash` at `0x18003e30c`
- `bcrypt!BCryptFinishHash` at `0x18003e30c`
- `bcrypt!BCryptDestroyHash` at `0x18003e33d`
- `bcrypt!BCryptDestroyHash` at `0x18003e33d`
- `bcrypt!BCryptCreateHash` at `0x18003e2af`
- `bcrypt!BCryptCreateHash` at `0x18003e2af`

## string_xrefs

- `0x18003e213`: `NlComputeHMACMessageSignatureFromKey: NlGetKDFKey failed: 0x%x\n`
- `0x18003e250`: `NlComputeHMACMessageSignatureFromKey: failed to allocate memory for hash object: 0x%x\n`
- `0x18003e27b`: `NlComputeHMACMessageSignatureFromKey: failed to allocate memory for hash buffer: 0x%x\n`
- `0x18003e2c1`: `NlComputeHMACMessageSignatureFromKey: BCryptCreateHash failed: 0x%x\n`
- `0x18003e2f2`: `NlComputeHMACMessageSignatureFromKey: BCryptHashData failed: 0x%x\n`
- `0x18003e31e`: `NlComputeHMACMessageSignatureFromKey: BCryptFinishHash failed: 0x%x\n`

## pseudocode

```c
__int64 __fastcall NlComputeHMACMessageSignature(
        unsigned __int8 *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        PUCHAR pbInput,
        ULONG cbInput,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  SIZE_T v10; // r14
  SIZE_T v11; // rbp
  UCHAR *v12; // rsi
  UCHAR *v13; // rdi
  NTSTATUS KDFKey; // eax
  unsigned int v15; // ebx
  unsigned __int16 *v16; // rdx
  NTSTATUS v17; // eax
  unsigned __int8 *pbSecret; // [rsp+20h] [rbp-B8h]
  ULONG cbSecret; // [rsp+28h] [rbp-B0h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-98h] BYREF
  UCHAR v22[64]; // [rsp+50h] [rbp-88h] BYREF

  v10 = (unsigned int)NlGlobalSha512HashObjectSize;
  v11 = (unsigned int)NlGlobalSha512HashSize;
  v12 = 0;
  v13 = 0;
  phHash = 0;
  *a9 = 0;
  *a10 = 0;
  KDFKey = NlGetKDFKey(a1, a2, a3, a4, pbSecret, cbSecret, v22);
  v15 = KDFKey;
  if ( KDFKey < 0 )
  {
    v16 = L"NlComputeHMACMessageSignatureFromKey: NlGetKDFKey failed: 0x%x\n";
LABEL_3:
    NlPrintRoutine(0x100u, v16, (unsigned int)KDFKey);
    goto LABEL_16;
  }
  v12 = (UCHAR *)LocalAlloc(0x40u, v10);
  if ( v12 )
  {
    v13 = (UCHAR *)LocalAlloc(0x40u, v11);
    if ( v13 )
    {
      KDFKey = BCryptCreateHash(NlGlobalSha512Handle, &phHash, v12, v10, v22, 0x40u, 0);
      v15 = KDFKey;
      if ( KDFKey < 0 )
      {
        v16 = L"NlComputeHMACMessageSignatureFromKey: BCryptCreateHash failed: 0x%x\n";
        goto LABEL_3;
      }
      KDFKey = BCryptHashData(phHash, pbInput, cbInput, 0);
      v15 = KDFKey;
      if ( KDFKey < 0 )
      {
        v16 = L"NlComputeHMACMessageSignatureFromKey: BCryptHashData failed: 0x%x\n";
        goto LABEL_3;
      }
      KDFKey = BCryptFinishHash(phHash, v13, v11, 0);
      v15 = KDFKey;
      if ( KDFKey < 0 )
      {
        v16 = L"NlComputeHMACMessageSignatureFromKey: BCryptFinishHash failed: 0x%x\n";
        goto LABEL_3;
      }
      *a9 = v13;
      v13 = 0;
      *a10 = v11;
    }
    else
    {
      v15 = -1073741801;
      NlPrintRoutine(
        0x100u,
        L"NlComputeHMACMessageSignatureFromKey: failed to allocate memory for hash buffer: 0x%x\n",
        3221225495LL);
    }
  }
  else
  {
    v15 = -1073741801;
    NlPrintRoutine(
      0x100u,
      L"NlComputeHMACMessageSignatureFromKey: failed to allocate memory for hash object: 0x%x\n",
      3221225495LL);
  }
LABEL_16:
  if ( phHash )
  {
    v17 = BCryptDestroyHash(phHash);
    if ( v17 < 0 )
      NlPrintRoutine(0x100u, L"NlGetKDFKey: BCryptDestroyHash failed: 0x%x\n", (unsigned int)v17);
  }
  if ( v12 )
    LocalFree(v12);
  if ( v13 )
    LocalFree(v13);
  return v15;
}

```

## disassembly

```asm
0x18003e1a0  mov     [rsp+arg_8], rbx
0x18003e1a5  push    rbp
0x18003e1a6  push    rsi
0x18003e1a7  push    rdi
0x18003e1a8  push    r12
0x18003e1aa  push    r13
0x18003e1ac  push    r14
0x18003e1ae  push    r15
0x18003e1b0  sub     rsp, 0A0h
0x18003e1b7  mov     rax, cs:__security_cookie
0x18003e1be  xor     rax, rsp
0x18003e1c1  mov     [rsp+0D8h+var_48], rax
0x18003e1c9  mov     r14d, cs:?NlGlobalSha512HashObjectSize@@3KA; ulong NlGlobalSha512HashObjectSize
0x18003e1d0  lea     rax, [rsp+0D8h+var_88]
0x18003e1d5  mov     ebp, cs:?NlGlobalSha512HashSize@@3KA; ulong NlGlobalSha512HashSize
0x18003e1db  xor     esi, esi
0x18003e1dd  mov     r15, [rsp+0D8h+arg_40]
0x18003e1e5  mov     edi, esi
0x18003e1e7  mov     r12, [rsp+0D8h+arg_48]
0x18003e1ef  mov     r13, [rsp+0D8h+pbInput]
0x18003e1f7  mov     [rsp+0D8h+phHash], rsi
0x18003e1fc  mov     [r15], rsi
0x18003e1ff  mov     [r12], esi
0x18003e203  mov     qword ptr [rsp+0D8h+dwFlags], rax; unsigned __int8 *
0x18003e208  call    ?NlGetKDFKey@@YAJPEAEK0K0KQEAE@Z; NlGetKDFKey(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * const)
0x18003e20d  mov     ebx, eax
0x18003e20f  test    eax, eax
0x18003e211  jns     short loc_18003E22C
0x18003e213  lea     rdx, aNlcomputehmacm_2; "NlComputeHMACMessageSignatureFromKey: N"...
0x18003e21a  mov     r8d, eax
0x18003e21d  mov     ecx, 100h; unsigned int
0x18003e222  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003e227  jmp     loc_18003E333
0x18003e22c  mov     ebx, 40h ; '@'
0x18003e231  mov     rdx, r14; uBytes
0x18003e234  mov     ecx, ebx; uFlags
0x18003e236  call    cs:__imp_LocalAlloc
0x18003e23d  nop     dword ptr [rax+rax+00h]
0x18003e242  mov     rsi, rax
0x18003e245  test    rax, rax
0x18003e248  jnz     short loc_18003E25C
0x18003e24a  mov     r8d, 0C0000017h
0x18003e250  lea     rdx, aNlcomputehmacm_0; "NlComputeHMACMessageSignatureFromKey: f"...
0x18003e257  mov     ebx, r8d
0x18003e25a  jmp     short loc_18003E21D
0x18003e25c  mov     rdx, rbp; uBytes
0x18003e25f  mov     ecx, ebx; uFlags
0x18003e261  call    cs:__imp_LocalAlloc
0x18003e268  nop     dword ptr [rax+rax+00h]
0x18003e26d  mov     rdi, rax
0x18003e270  test    rax, rax
0x18003e273  jnz     short loc_18003E287
0x18003e275  mov     r8d, 0C0000017h
0x18003e27b  lea     rdx, aNlcomputehmacm_1; "NlComputeHMACMessageSignatureFromKey: f"...
0x18003e282  mov     ebx, r8d
0x18003e285  jmp     short loc_18003E21D
0x18003e287  mov     rcx, cs:?NlGlobalSha512Handle@@3PEAXEA; hAlgorithm
0x18003e28e  lea     rax, [rsp+0D8h+var_88]
0x18003e293  mov     [rsp+0D8h+dwFlags], 0; dwFlags
0x18003e29b  lea     rdx, [rsp+0D8h+phHash]; phHash
0x18003e2a0  mov     [rsp+0D8h+cbSecret], ebx; cbSecret
0x18003e2a4  mov     r9d, r14d; cbHashObject
0x18003e2a7  mov     r8, rsi; pbHashObject
0x18003e2aa  mov     [rsp+0D8h+pbSecret], rax; pbSecret
0x18003e2af  call    cs:__imp_BCryptCreateHash
0x18003e2b6  nop     dword ptr [rax+rax+00h]
0x18003e2bb  mov     ebx, eax
0x18003e2bd  test    eax, eax
0x18003e2bf  jns     short loc_18003E2CD
0x18003e2c1  lea     rdx, aNlcomputehmacm_4; "NlComputeHMACMessageSignatureFromKey: B"...
0x18003e2c8  jmp     loc_18003E21A
0x18003e2cd  mov     r8d, [rsp+0D8h+cbInput]; cbInput
0x18003e2d5  xor     r9d, r9d; dwFlags
0x18003e2d8  mov     rcx, [rsp+0D8h+phHash]; hHash
0x18003e2dd  mov     rdx, r13; pbInput
0x18003e2e0  call    cs:__imp_BCryptHashData
0x18003e2e7  nop     dword ptr [rax+rax+00h]
0x18003e2ec  mov     ebx, eax
0x18003e2ee  test    eax, eax
0x18003e2f0  jns     short loc_18003E2FE
0x18003e2f2  lea     rdx, aNlcomputehmacm_3; "NlComputeHMACMessageSignatureFromKey: B"...
0x18003e2f9  jmp     loc_18003E21A
0x18003e2fe  mov     rcx, [rsp+0D8h+phHash]; hHash
0x18003e303  xor     r9d, r9d; dwFlags
0x18003e306  mov     r8d, ebp; cbOutput
0x18003e309  mov     rdx, rdi; pbOutput
0x18003e30c  call    cs:__imp_BCryptFinishHash
0x18003e313  nop     dword ptr [rax+rax+00h]
0x18003e318  mov     ebx, eax
0x18003e31a  test    eax, eax
0x18003e31c  jns     short loc_18003E32A
0x18003e31e  lea     rdx, aNlcomputehmacm; "NlComputeHMACMessageSignatureFromKey: B"...
0x18003e325  jmp     loc_18003E21A
0x18003e32a  mov     [r15], rdi
0x18003e32d  xor     edi, edi
0x18003e32f  mov     [r12], ebp
0x18003e333  mov     rcx, [rsp+0D8h+phHash]; hHash
0x18003e338  test    rcx, rcx
0x18003e33b  jz      short loc_18003E361
0x18003e33d  call    cs:__imp_BCryptDestroyHash
0x18003e344  nop     dword ptr [rax+rax+00h]
0x18003e349  test    eax, eax
0x18003e34b  jns     short loc_18003E361
0x18003e34d  mov     r8d, eax
0x18003e350  lea     rdx, aNlgetkdfkeyBcr_1; "NlGetKDFKey: BCryptDestroyHash failed: "...
0x18003e357  mov     ecx, 100h; unsigned int
0x18003e35c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003e361  test    rsi, rsi
0x18003e364  jz      short loc_18003E375
0x18003e366  mov     rcx, rsi; hMem
0x18003e369  call    cs:__imp_LocalFree
0x18003e370  nop     dword ptr [rax+rax+00h]
0x18003e375  test    rdi, rdi
0x18003e378  jz      short loc_18003E389
0x18003e37a  mov     rcx, rdi; hMem
0x18003e37d  call    cs:__imp_LocalFree
0x18003e384  nop     dword ptr [rax+rax+00h]
0x18003e389  mov     eax, ebx
0x18003e38b  mov     rcx, [rsp+0D8h+var_48]
0x18003e393  xor     rcx, rsp; StackCookie
0x18003e396  call    __security_check_cookie
0x18003e39b  mov     rbx, [rsp+0D8h+arg_8]
0x18003e3a3  add     rsp, 0A0h
0x18003e3aa  pop     r15
0x18003e3ac  pop     r14
0x18003e3ae  pop     r13
0x18003e3b0  pop     r12
0x18003e3b2  pop     rdi
0x18003e3b3  pop     rsi
0x18003e3b4  pop     rbp
0x18003e3b5  retn
```
