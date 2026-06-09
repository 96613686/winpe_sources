# I_CryptExtractFileBlobFromCab

- ea: `0x18003a964`
- end: `0x18003abfd`
- name: `I_CryptExtractFileBlobFromCab`
- size: `665`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003a770`
- `0x18003a800`

## callees

- `0x180034270`
- `0x18003a964`
- `0x1800bec20`
- `0x1800bf4d2`
- `0x1800bf63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003aa4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ab83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003aa4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ab83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003aa09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ab50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003aa09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ab50`
- `Cabinet!__imp_FDICreate` at `0x18003aaa7`
- `Cabinet!__imp_FDICreate` at `0x18003aaa7`
- `Cabinet!__imp_FDICopy` at `0x18003aae6`
- `Cabinet!__imp_FDICopy` at `0x18003aae6`
- `Cabinet!__imp_FDIDestroy` at `0x18003ab91`
- `Cabinet!__imp_FDIDestroy` at `0x18003ab91`

## pseudocode

```c
__int64 __fastcall I_CryptExtractFileBlobFromCab(__int64 a1, unsigned int a2, __int64 a3, LPVOID *a4, _DWORD *a5)
{
  int v9; // r15d
  HFDI v10; // rbx
  unsigned int v11; // edi
  BOOL v12; // eax
  DWORD LastError; // esi
  DWORD v14; // ecx
  __int64 v15; // rdx
  __int64 *v16; // rax
  __int64 result; // rax
  __int64 pvUser; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v19; // [rsp+58h] [rbp-A8h] BYREF
  char Buffer[40]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+88h] [rbp-78h]
  __int64 v22; // [rsp+90h] [rbp-70h]
  unsigned int v23; // [rsp+98h] [rbp-68h]
  LPVOID pv; // [rsp+A0h] [rbp-60h]
  int v25; // [rsp+A8h] [rbp-58h]
  int v26; // [rsp+ACh] [rbp-54h]
  DWORD v27; // [rsp+B0h] [rbp-50h]
  ERF perf; // [rsp+110h] [rbp+10h] BYREF

  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  pvUser = 0;
  v9 = 0;
  v10 = 0;
  memset_0(&v19, 0, 0xB0u);
  if ( a2 > 0xA00000 )
  {
    v14 = 534;
  }
  else
  {
    v23 = a2;
    v11 = 1;
    v22 = a1;
    v21 = a3;
    if ( itoa_s(_InterlockedIncrement(&dword_18015D2A8), Buffer, 0x22u, 10) )
      goto LABEL_10;
    AcquireSRWLockExclusive(&stru_18015D2A0);
    if ( *(__int64 **)(qword_18015D290 + 8) != &qword_18015D290 )
      goto LABEL_19;
    v19 = &qword_18015D290;
    pvUser = qword_18015D290;
    *(_QWORD *)(qword_18015D290 + 8) = &pvUser;
    qword_18015D290 = (__int64)&pvUser;
    ReleaseSRWLockExclusive(&stru_18015D2A0);
    v9 = 1;
    v10 = FDICreate(
            ExtractAllocCallback,
            (PFNFREE)ExtractFreeCallback,
            ExtractOpenCallback,
            ExtractReadCallback,
            ExtractWriteCallback,
            ExtractCloseCallback,
            ExtractSeekCallback,
            -1,
            &perf);
    if ( !v10 )
    {
LABEL_10:
      v14 = -2147418113;
      goto LABEL_11;
    }
    v12 = FDICopy(v10, Buffer, (LPSTR)"c:\\crypt32\\", 0, ExtractNotifyCallback, 0, &pvUser);
    if ( v26 == 3 )
    {
      v14 = v27;
    }
    else if ( v12 )
    {
      if ( v26 )
      {
        if ( v26 == 2 )
        {
          LastError = GetLastError();
          goto LABEL_12;
        }
        goto LABEL_10;
      }
      v14 = 2;
    }
    else
    {
      v14 = 13;
    }
  }
LABEL_11:
  SetLastError(v14);
  ICM_Free(pv);
  pv = 0;
  v25 = 0;
  v11 = 0;
  LastError = GetLastError();
  if ( !v9 )
    goto LABEL_15;
LABEL_12:
  AcquireSRWLockExclusive(&stru_18015D2A0);
  v15 = pvUser;
  if ( *(__int64 **)(pvUser + 8) != &pvUser || (v16 = v19, (__int64 *)*v19 != &pvUser) )
LABEL_19:
    __fastfail(3u);
  *v19 = pvUser;
  *(_QWORD *)(v15 + 8) = v16;
  ReleaseSRWLockExclusive(&stru_18015D2A0);
LABEL_15:
  if ( v10 )
    FDIDestroy(v10);
  SetLastError(LastError);
  result = v11;
  *a4 = pv;
  *a5 = v25;
  return result;
}

```

## disassembly

```asm
0x18003a964  push    rbp
0x18003a966  push    rbx
0x18003a967  push    rsi
0x18003a968  push    rdi
0x18003a969  push    r12
0x18003a96b  push    r13
0x18003a96d  push    r14
0x18003a96f  push    r15
0x18003a971  lea     rbp, [rsp-38h]
0x18003a976  sub     rsp, 138h
0x18003a97d  mov     rax, cs:__security_cookie
0x18003a984  xor     rax, rsp
0x18003a987  mov     [rbp+70h+var_50], rax
0x18003a98b  mov     r13, [rbp+70h+arg_20]
0x18003a992  xor     eax, eax
0x18003a994  mov     r14, r8
0x18003a997  mov     qword ptr [rbp+70h+var_60.erfOper], rax
0x18003a99b  mov     edi, edx
0x18003a99d  mov     [rbp+70h+var_60.fError], eax
0x18003a9a0  mov     rsi, rcx
0x18003a9a3  mov     [rsp+170h+pvUser], rax
0x18003a9a8  xor     edx, edx; Val
0x18003a9aa  lea     rcx, [rsp+170h+var_118]; void *
0x18003a9af  mov     r8d, 0B0h; Size
0x18003a9b5  mov     r12, r9
0x18003a9b8  xor     r15d, r15d
0x18003a9bb  xor     ebx, ebx
0x18003a9bd  call    memset_0
0x18003a9c2  cmp     edi, 0A00000h
0x18003a9c8  ja      loc_18003ABDF
0x18003a9ce  mov     [rbp+70h+var_D8], edi
0x18003a9d1  lea     edi, [rbx+1]
0x18003a9d4  mov     ecx, edi
0x18003a9d6  mov     [rbp+70h+var_E0], rsi
0x18003a9da  mov     [rbp+70h+var_E8], r14
0x18003a9de  lock xadd cs:dword_18015D2A8, ecx
0x18003a9e6  add     ecx, edi; Value
0x18003a9e8  lea     r9d, [r15+0Ah]; Radix
0x18003a9ec  lea     r8d, [r15+22h]; BufferCount
0x18003a9f0  lea     rdx, [rsp+170h+Buffer]; Buffer
0x18003a9f5  call    _itoa_s
0x18003a9fa  test    eax, eax
0x18003a9fc  jnz     loc_18003AB17
0x18003aa02  lea     rcx, stru_18015D2A0; SRWLock
0x18003aa09  call    cs:__imp_AcquireSRWLockExclusive
0x18003aa0f  mov     rax, cs:qword_18015D290
0x18003aa16  lea     rcx, qword_18015D290
0x18003aa1d  cmp     [rax+8], rcx
0x18003aa21  jnz     loc_18003ABD8
0x18003aa27  mov     [rsp+170h+var_118], rcx
0x18003aa2c  lea     rcx, [rsp+170h+pvUser]
0x18003aa31  mov     [rsp+170h+pvUser], rax
0x18003aa36  mov     [rax+8], rcx
0x18003aa3a  lea     rax, [rsp+170h+pvUser]
0x18003aa3f  lea     rcx, stru_18015D2A0; SRWLock
0x18003aa46  mov     cs:qword_18015D290, rax
0x18003aa4d  call    cs:__imp_ReleaseSRWLockExclusive
0x18003aa53  lea     rax, [rbp+70h+var_60]
0x18003aa57  mov     r15d, edi
0x18003aa5a  mov     [rsp+170h+perf], rax; perf
0x18003aa5f  lea     r9, ExtractReadCallback; pfnread
0x18003aa66  mov     [rsp+170h+cpuType], 0FFFFFFFFh; cpuType
0x18003aa6e  lea     rax, ExtractSeekCallback
0x18003aa75  mov     [rsp+170h+pfnseek], rax; pfnseek
0x18003aa7a  lea     r8, ExtractOpenCallback; pfnopen
0x18003aa81  lea     rax, ExtractCloseCallback
0x18003aa88  mov     [rsp+170h+pfnclose], rax; pfnclose
0x18003aa8d  lea     rdx, ExtractFreeCallback; pfnfree
0x18003aa94  lea     rax, ExtractWriteCallback
0x18003aa9b  lea     rcx, ExtractAllocCallback; pfnalloc
0x18003aaa2  mov     [rsp+170h+pfnwrite], rax; pfnwrite
0x18003aaa7  call    cs:__imp_FDICreate
0x18003aaad  mov     rbx, rax
0x18003aab0  test    rax, rax
0x18003aab3  jz      short loc_18003AB17
0x18003aab5  lea     rax, [rsp+170h+pvUser]
0x18003aaba  xor     r9d, r9d; flags
0x18003aabd  mov     [rsp+170h+pfnseek], rax; pvUser
0x18003aac2  lea     r8, pszCabPath; "c:\\crypt32\\"
0x18003aac9  lea     rax, ExtractNotifyCallback
0x18003aad0  mov     [rsp+170h+pfnclose], 0; pfnfdid
0x18003aad9  lea     rdx, [rsp+170h+Buffer]; pszCabinet
0x18003aade  mov     [rsp+170h+pfnwrite], rax; pfnfdin
0x18003aae3  mov     rcx, rbx; hfdi
0x18003aae6  call    cs:__imp_FDICopy
0x18003aaec  mov     ecx, [rbp+70h+var_C4]
0x18003aaef  cmp     ecx, 3
0x18003aaf2  jz      loc_18003ABD0
0x18003aaf8  test    eax, eax
0x18003aafa  jz      loc_18003ABE9
0x18003ab00  test    ecx, ecx
0x18003ab02  jz      loc_18003ABF3
0x18003ab08  cmp     ecx, 2
0x18003ab0b  jnz     short loc_18003AB17
0x18003ab0d  call    cs:__imp_GetLastError
0x18003ab13  mov     esi, eax
0x18003ab15  jmp     short loc_18003AB49
0x18003ab17  mov     ecx, 8000FFFFh; dwErrCode
0x18003ab1c  call    cs:__imp_SetLastError
0x18003ab22  mov     rcx, [rbp+70h+pv]; pv
0x18003ab26  call    ?ICM_Free@@YAXPEAX@Z; ICM_Free(void *)
0x18003ab2b  mov     [rbp+70h+pv], 0
0x18003ab33  mov     [rbp+70h+var_C8], 0
0x18003ab3a  call    cs:__imp_GetLastError
0x18003ab40  xor     edi, edi
0x18003ab42  mov     esi, eax
0x18003ab44  test    r15d, r15d
0x18003ab47  jz      short loc_18003AB89
0x18003ab49  lea     rcx, stru_18015D2A0; SRWLock
0x18003ab50  call    cs:__imp_AcquireSRWLockExclusive
0x18003ab56  mov     rdx, [rsp+170h+pvUser]
0x18003ab5b  lea     rax, [rsp+170h+pvUser]
0x18003ab60  cmp     [rdx+8], rax
0x18003ab64  jnz     short loc_18003ABD8
0x18003ab66  mov     rax, [rsp+170h+var_118]
0x18003ab6b  lea     r8, [rsp+170h+pvUser]
0x18003ab70  cmp     [rax], r8
0x18003ab73  jnz     short loc_18003ABD8
0x18003ab75  mov     [rax], rdx
0x18003ab78  lea     rcx, stru_18015D2A0; SRWLock
0x18003ab7f  mov     [rdx+8], rax
0x18003ab83  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ab89  test    rbx, rbx
0x18003ab8c  jz      short loc_18003AB97
0x18003ab8e  mov     rcx, rbx; hfdi
0x18003ab91  call    cs:__imp_FDIDestroy
0x18003ab97  mov     ecx, esi; dwErrCode
0x18003ab99  call    cs:__imp_SetLastError
0x18003ab9f  mov     rcx, [rbp+70h+pv]
0x18003aba3  mov     eax, edi
0x18003aba5  mov     [r12], rcx
0x18003aba9  mov     ecx, [rbp+70h+var_C8]
0x18003abac  mov     [r13+0], ecx
0x18003abb0  mov     rcx, [rbp+70h+var_50]
0x18003abb4  xor     rcx, rsp; StackCookie
0x18003abb7  call    __security_check_cookie
0x18003abbc  add     rsp, 138h
0x18003abc3  pop     r15
0x18003abc5  pop     r14
0x18003abc7  pop     r13
0x18003abc9  pop     r12
0x18003abcb  pop     rdi
0x18003abcc  pop     rsi
0x18003abcd  pop     rbx
0x18003abce  pop     rbp
0x18003abcf  retn
0x18003abd0  mov     ecx, [rbp+70h+var_C0]
0x18003abd3  jmp     loc_18003AB1C
0x18003abd8  mov     ecx, 3
0x18003abdd  int     29h; Win8: RtlFailFast(ecx)
0x18003abdf  mov     ecx, 216h
0x18003abe4  jmp     loc_18003AB1C
0x18003abe9  mov     ecx, 0Dh
0x18003abee  jmp     loc_18003AB1C
0x18003abf3  mov     ecx, 2
0x18003abf8  jmp     loc_18003AB1C
```
