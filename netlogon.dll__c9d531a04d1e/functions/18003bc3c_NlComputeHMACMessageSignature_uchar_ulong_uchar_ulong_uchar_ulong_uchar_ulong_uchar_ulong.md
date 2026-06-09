# NlComputeHMACMessageSignature(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18003bc3c`
- end: `0x18003be22`
- name: `?NlComputeHMACMessageSignature@@YAJPEAEK0K0K0KPEAPEAEPEAK@Z`
- size: `486`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, PUCHAR pbInput, ULONG cbInput, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180056164`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18003bc3c`
- `0x18003be28`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bcd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bcf7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bcd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bcf7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bde1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bdef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bde1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bdef`
- `bcrypt!BCryptHashData` at `0x18003bd6a`
- `bcrypt!BCryptHashData` at `0x18003bd6a`
- `bcrypt!BCryptFinishHash` at `0x18003bd90`
- `bcrypt!BCryptFinishHash` at `0x18003bd90`
- `bcrypt!BCryptDestroyHash` at `0x18003bdbb`
- `bcrypt!BCryptDestroyHash` at `0x18003bdbb`
- `bcrypt!BCryptCreateHash` at `0x18003bd3f`
- `bcrypt!BCryptCreateHash` at `0x18003bd3f`

## string_xrefs

- `0x18003bcaf`: `NlComputeHMACMessageSignatureFromKey: NlGetKDFKey failed: 0x%x\n`
- `0x18003bce6`: `NlComputeHMACMessageSignatureFromKey: failed to allocate memory for hash object: 0x%x\n`
- `0x18003bd0b`: `NlComputeHMACMessageSignatureFromKey: failed to allocate memory for hash buffer: 0x%x\n`
- `0x18003bd4b`: `NlComputeHMACMessageSignatureFromKey: BCryptCreateHash failed: 0x%x\n`
- `0x18003bd76`: `NlComputeHMACMessageSignatureFromKey: BCryptHashData failed: 0x%x\n`
- `0x18003bd9c`: `NlComputeHMACMessageSignatureFromKey: BCryptFinishHash failed: 0x%x\n`

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
0x18003bc3c  mov     [rsp+arg_8], rbx
0x18003bc41  push    rbp
0x18003bc42  push    rsi
0x18003bc43  push    rdi
0x18003bc44  push    r12
0x18003bc46  push    r13
0x18003bc48  push    r14
0x18003bc4a  push    r15
0x18003bc4c  sub     rsp, 0A0h
0x18003bc53  mov     rax, cs:__security_cookie
0x18003bc5a  xor     rax, rsp
0x18003bc5d  mov     [rsp+0D8h+var_48], rax
0x18003bc65  mov     r14d, cs:?NlGlobalSha512HashObjectSize@@3KA; ulong NlGlobalSha512HashObjectSize
0x18003bc6c  lea     rax, [rsp+0D8h+var_88]
0x18003bc71  mov     ebp, cs:?NlGlobalSha512HashSize@@3KA; ulong NlGlobalSha512HashSize
0x18003bc77  xor     esi, esi
0x18003bc79  mov     r15, [rsp+0D8h+arg_40]
0x18003bc81  mov     edi, esi
0x18003bc83  mov     r12, [rsp+0D8h+arg_48]
0x18003bc8b  mov     r13, [rsp+0D8h+pbInput]
0x18003bc93  mov     [rsp+0D8h+phHash], rsi
0x18003bc98  mov     [r15], rsi
0x18003bc9b  mov     [r12], esi
0x18003bc9f  mov     qword ptr [rsp+0D8h+dwFlags], rax; unsigned __int8 *
0x18003bca4  call    ?NlGetKDFKey@@YAJPEAEK0K0KQEAE@Z; NlGetKDFKey(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * const)
0x18003bca9  mov     ebx, eax
0x18003bcab  test    eax, eax
0x18003bcad  jns     short loc_18003BCC8
0x18003bcaf  lea     rdx, aNlcomputehmacm_2; "NlComputeHMACMessageSignatureFromKey: N"...
0x18003bcb6  mov     r8d, eax
0x18003bcb9  mov     ecx, 100h; unsigned int
0x18003bcbe  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003bcc3  jmp     loc_18003BDB1
0x18003bcc8  mov     ebx, 40h ; '@'
0x18003bccd  mov     rdx, r14; uBytes
0x18003bcd0  mov     ecx, ebx; uFlags
0x18003bcd2  call    cs:__imp_LocalAlloc
0x18003bcd8  mov     rsi, rax
0x18003bcdb  test    rax, rax
0x18003bcde  jnz     short loc_18003BCF2
0x18003bce0  mov     r8d, 0C0000017h
0x18003bce6  lea     rdx, aNlcomputehmacm_0; "NlComputeHMACMessageSignatureFromKey: f"...
0x18003bced  mov     ebx, r8d
0x18003bcf0  jmp     short loc_18003BCB9
0x18003bcf2  mov     rdx, rbp; uBytes
0x18003bcf5  mov     ecx, ebx; uFlags
0x18003bcf7  call    cs:__imp_LocalAlloc
0x18003bcfd  mov     rdi, rax
0x18003bd00  test    rax, rax
0x18003bd03  jnz     short loc_18003BD17
0x18003bd05  mov     r8d, 0C0000017h
0x18003bd0b  lea     rdx, aNlcomputehmacm_1; "NlComputeHMACMessageSignatureFromKey: f"...
0x18003bd12  mov     ebx, r8d
0x18003bd15  jmp     short loc_18003BCB9
0x18003bd17  mov     rcx, cs:?NlGlobalSha512Handle@@3PEAXEA; hAlgorithm
0x18003bd1e  lea     rax, [rsp+0D8h+var_88]
0x18003bd23  mov     [rsp+0D8h+dwFlags], 0; dwFlags
0x18003bd2b  lea     rdx, [rsp+0D8h+phHash]; phHash
0x18003bd30  mov     [rsp+0D8h+cbSecret], ebx; cbSecret
0x18003bd34  mov     r9d, r14d; cbHashObject
0x18003bd37  mov     r8, rsi; pbHashObject
0x18003bd3a  mov     [rsp+0D8h+pbSecret], rax; pbSecret
0x18003bd3f  call    cs:__imp_BCryptCreateHash
0x18003bd45  mov     ebx, eax
0x18003bd47  test    eax, eax
0x18003bd49  jns     short loc_18003BD57
0x18003bd4b  lea     rdx, aNlcomputehmacm_4; "NlComputeHMACMessageSignatureFromKey: B"...
0x18003bd52  jmp     loc_18003BCB6
0x18003bd57  mov     r8d, [rsp+0D8h+cbInput]; cbInput
0x18003bd5f  xor     r9d, r9d; dwFlags
0x18003bd62  mov     rcx, [rsp+0D8h+phHash]; hHash
0x18003bd67  mov     rdx, r13; pbInput
0x18003bd6a  call    cs:__imp_BCryptHashData
0x18003bd70  mov     ebx, eax
0x18003bd72  test    eax, eax
0x18003bd74  jns     short loc_18003BD82
0x18003bd76  lea     rdx, aNlcomputehmacm_3; "NlComputeHMACMessageSignatureFromKey: B"...
0x18003bd7d  jmp     loc_18003BCB6
0x18003bd82  mov     rcx, [rsp+0D8h+phHash]; hHash
0x18003bd87  xor     r9d, r9d; dwFlags
0x18003bd8a  mov     r8d, ebp; cbOutput
0x18003bd8d  mov     rdx, rdi; pbOutput
0x18003bd90  call    cs:__imp_BCryptFinishHash
0x18003bd96  mov     ebx, eax
0x18003bd98  test    eax, eax
0x18003bd9a  jns     short loc_18003BDA8
0x18003bd9c  lea     rdx, aNlcomputehmacm; "NlComputeHMACMessageSignatureFromKey: B"...
0x18003bda3  jmp     loc_18003BCB6
0x18003bda8  mov     [r15], rdi
0x18003bdab  xor     edi, edi
0x18003bdad  mov     [r12], ebp
0x18003bdb1  mov     rcx, [rsp+0D8h+phHash]; hHash
0x18003bdb6  test    rcx, rcx
0x18003bdb9  jz      short loc_18003BDD9
0x18003bdbb  call    cs:__imp_BCryptDestroyHash
0x18003bdc1  test    eax, eax
0x18003bdc3  jns     short loc_18003BDD9
0x18003bdc5  mov     r8d, eax
0x18003bdc8  lea     rdx, aNlgetkdfkeyBcr_1; "NlGetKDFKey: BCryptDestroyHash failed: "...
0x18003bdcf  mov     ecx, 100h; unsigned int
0x18003bdd4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003bdd9  test    rsi, rsi
0x18003bddc  jz      short loc_18003BDE7
0x18003bdde  mov     rcx, rsi; hMem
0x18003bde1  call    cs:__imp_LocalFree
0x18003bde7  test    rdi, rdi
0x18003bdea  jz      short loc_18003BDF5
0x18003bdec  mov     rcx, rdi; hMem
0x18003bdef  call    cs:__imp_LocalFree
0x18003bdf5  mov     eax, ebx
0x18003bdf7  mov     rcx, [rsp+0D8h+var_48]
0x18003bdff  xor     rcx, rsp; StackCookie
0x18003be02  call    __security_check_cookie
0x18003be07  mov     rbx, [rsp+0D8h+arg_8]
0x18003be0f  add     rsp, 0A0h
0x18003be16  pop     r15
0x18003be18  pop     r14
0x18003be1a  pop     r13
0x18003be1c  pop     r12
0x18003be1e  pop     rdi
0x18003be1f  pop     rsi
0x18003be20  pop     rbp
0x18003be21  retn
```
