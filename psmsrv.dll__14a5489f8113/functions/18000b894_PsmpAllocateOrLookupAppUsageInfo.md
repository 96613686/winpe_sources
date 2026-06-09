# PsmpAllocateOrLookupAppUsageInfo

- ea: `0x18000b894`
- end: `0x18000bc13`
- name: `PsmpAllocateOrLookupAppUsageInfo`
- size: `895`
- prototype: `__int64 __fastcall(__int64, __int64 Args, signed __int32 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000abf0`
- `0x18000cb7c`

## callees

- `0x1800017b0`
- `0x18000b894`
- `0x18000c3a8`
- `0x18000ce64`
- `0x180019c30`
- `0x18001b7e0`
- `0x18002e17c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000bc0b`
- `ntdll!RtlFreeHeap` at `0x18000bc0b`
- `ntdll!RtlCopySid` at `0x18000bb44`
- `ntdll!RtlCopySid` at `0x18000bb44`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000b9ea`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000b9ea`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000b901`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000b957`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000b901`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000b957`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000b9c6`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000bb87`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000b9c6`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000bb87`
- `ntdll!RtlInitializeSRWLock` at `0x18000bb2a`
- `ntdll!RtlInitializeSRWLock` at `0x18000bb2a`
- `ntdll!RtlAllocateHeap` at `0x18000ba13`
- `ntdll!RtlAllocateHeap` at `0x18000ba13`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000bb4e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000bb4e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000bbc4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000bbc4`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b98e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b98e`

## pseudocode

```c
__int64 __fastcall PsmpAllocateOrLookupAppUsageInfo(__int64 a1, __int64 Args, signed __int32 **a3)
{
  __int64 v3; // rax
  int v4; // edi
  WCHAR *v5; // rsi
  WCHAR v6; // bx
  int v7; // ecx
  unsigned __int64 v8; // rsi
  __int64 v9; // rax
  int *v10; // rbp
  int v11; // r14d
  WCHAR *v12; // rdi
  WCHAR v13; // bx
  int v14; // ecx
  unsigned __int64 v15; // rdi
  int *v16; // r15
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  int *i; // r14
  signed __int32 *v21; // rbx
  signed __int32 v22; // eax
  char *Heap; // rax
  _QWORD *v24; // rdi
  __int64 result; // rax
  char *v26; // rbx
  int *j; // r14
  signed __int32 v28; // eax
  signed __int32 v29; // edx
  int *v30; // rsi
  int v31; // [rsp+20h] [rbp-2C8h]
  wchar_t Src[288]; // [rsp+60h] [rbp-288h] BYREF

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(Args + 2 * v3) );
  if ( (unsigned __int64)(2 * v3 + 38) <= 0x240 )
    RtlStringCbPrintfExW(Src, 2048, (wchar_t *)L"%ws%wc%I64d", Args);
  v4 = 0;
  v5 = Src;
  do
  {
    v6 = *v5++;
    v7 = 37 * v4 + RtlUpcaseUnicodeChar(v6);
    v4 = v7;
  }
  while ( v6 );
  v8 = (char *)v5 - (char *)Src;
  v9 = v7 & 0x7F;
  v10 = &PsmpUsageTable[4 * v9 + 2 + 2 * v9];
  if ( v10 )
  {
    v16 = &PsmpUsageTable[4 * v9 + 2 + 2 * v9];
    v15 = (unsigned int)v8;
  }
  else
  {
    v11 = 0;
    v12 = Src;
    do
    {
      v13 = *v12++;
      v14 = 37 * v11 + RtlUpcaseUnicodeChar(v13);
      v11 = v14;
    }
    while ( v13 );
    v15 = (char *)v12 - (char *)Src;
    v16 = &PsmpUsageTable[4 * (v14 & 0x7F) + 2 + 2 * (v14 & 0x7F)];
  }
  RtlAcquireSRWLockShared(v16 + 4);
  for ( i = *(int **)v16; i != v16; i = *(int **)i )
  {
    v21 = i - 6;
    if ( v15 == *((_QWORD *)i - 1) )
    {
      LOBYTE(v31) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(*((_QWORD *)v21 + 1), v15 >> 1, Src, v15 >> 1, v31) )
      {
        _m_prefetchw(v21);
        v22 = *v21;
        while ( v22 > 0 )
        {
          v17 = (unsigned int)v22;
          v22 = _InterlockedCompareExchange(v21, v22 + 1, v22);
          if ( v22 == (_DWORD)v17 )
            goto LABEL_19;
        }
      }
    }
  }
  v21 = 0;
LABEL_19:
  RtlReleaseSRWLockShared(v16 + 4, v17, v18, v19);
  if ( v21 )
  {
    if ( _InterlockedDecrement(v21) == -1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else
  {
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v8 + 2952LL);
    v24 = Heap;
    if ( !Heap )
      return 3221225626LL;
    v26 = Heap + 2952;
    memcpy_0(Heap + 2952, Src, (unsigned int)v8);
    v24[1] = v26;
    *(_DWORD *)v24 = 1;
    v24[2] = (unsigned int)v8;
    *((_DWORD *)v24 + 1) = ((char *)v10 - (char *)PsmpUsageTable - 8) / 24;
    v24[4] = v24 + 3;
    v24[3] = v24 + 3;
    v24[14] = *(_QWORD *)(a1 + 96);
    RtlInitializeSRWLock(v24 + 15);
    RtlCopySid(0x44u, v24 + 5, *(PSID *)(*(_QWORD *)(a1 + 312) + 40LL));
    RtlAcquireSRWLockExclusive(v10 + 4);
    for ( j = *(int **)v10; j != v10; j = *(int **)j )
    {
      v21 = j - 6;
      if ( v8 == *((_QWORD *)j - 1) )
      {
        LOBYTE(v31) = 1;
        if ( !(unsigned int)RtlCompareUnicodeStrings(*((_QWORD *)v21 + 1), v8 >> 1, Src, v8 >> 1, v31) )
        {
          _m_prefetchw(v21);
          v28 = *v21;
          while ( v28 > 0 )
          {
            v29 = v28;
            v28 = _InterlockedCompareExchange(v21, v28 + 1, v28);
            if ( v28 == v29 )
            {
              v30 = j - 6;
              if ( j != (int *)24 )
                goto LABEL_35;
              goto LABEL_34;
            }
          }
        }
      }
    }
    v30 = 0;
LABEL_34:
    PsmpInsertHashEntry(v10, v24);
    v21 = (signed __int32 *)v24;
    v24 = 0;
LABEL_35:
    RtlReleaseSRWLockExclusive(v10 + 4);
    if ( v24 )
    {
      PsmpDereferenceObjectEx(v30, 0);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
    }
  }
  result = 0;
  *a3 = v21;
  return result;
}

```

## disassembly

```asm
0x18000b894  mov     [rsp+arg_18], rbx
0x18000b899  push    rbp
0x18000b89a  push    rsi
0x18000b89b  push    rdi
0x18000b89c  push    r12
0x18000b89e  push    r13
0x18000b8a0  push    r14
0x18000b8a2  push    r15
0x18000b8a4  sub     rsp, 2B0h
0x18000b8ab  mov     rax, cs:__security_cookie
0x18000b8b2  xor     rax, rsp
0x18000b8b5  mov     [rsp+2E8h+var_48], rax
0x18000b8bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b8c1  mov     [rsp+2E8h+var_290], r8
0x18000b8c6  xor     r15d, r15d
0x18000b8c9  mov     [rsp+2E8h+var_298], rcx
0x18000b8ce  inc     rax
0x18000b8d1  cmp     [rdx+rax*2], r15w
0x18000b8d6  jnz     short loc_18000B8CE
0x18000b8d8  lea     rax, ds:26h[rax*2]
0x18000b8e0  mov     r10d, 240h
0x18000b8e6  cmp     rax, r10
0x18000b8e9  jbe     loc_18000BA55
0x18000b8ef  mov     edi, r15d
0x18000b8f2  lea     rsi, [rsp+2E8h+Src]
0x18000b8f7  movzx   ebx, word ptr [rsi]
0x18000b8fa  add     rsi, 2
0x18000b8fe  movzx   ecx, bx; Source
0x18000b901  call    cs:__imp_RtlUpcaseUnicodeChar
0x18000b907  movzx   ecx, ax
0x18000b90a  imul    eax, edi, 25h ; '%'
0x18000b90d  add     ecx, eax
0x18000b90f  mov     edi, ecx
0x18000b911  test    bx, bx
0x18000b914  jnz     short loc_18000B8F7
0x18000b916  lea     rax, [rsp+2E8h+Src]
0x18000b91b  sub     rsi, rax
0x18000b91e  lea     r12, PsmpUsageTable
0x18000b925  mov     eax, ecx
0x18000b927  mov     r13d, esi
0x18000b92a  and     eax, 7Fh
0x18000b92d  lea     rbp, ds:1[rax*2]
0x18000b935  add     rbp, rax
0x18000b938  lea     rbp, [r12+rbp*8]
0x18000b93c  test    rbp, rbp
0x18000b93f  jnz     loc_18000BBDF
0x18000b945  mov     r14d, r15d
0x18000b948  lea     rdi, [rsp+2E8h+Src]
0x18000b94d  movzx   ebx, word ptr [rdi]
0x18000b950  add     rdi, 2
0x18000b954  movzx   ecx, bx; Source
0x18000b957  call    cs:__imp_RtlUpcaseUnicodeChar
0x18000b95d  movzx   ecx, ax
0x18000b960  imul    eax, r14d, 25h ; '%'
0x18000b964  add     ecx, eax
0x18000b966  mov     r14d, ecx
0x18000b969  test    bx, bx
0x18000b96c  jnz     short loc_18000B94D
0x18000b96e  lea     rax, [rsp+2E8h+Src]
0x18000b973  sub     rdi, rax
0x18000b976  mov     eax, ecx
0x18000b978  and     eax, 7Fh
0x18000b97b  lea     r15, ds:1[rax*2]
0x18000b983  add     r15, rax
0x18000b986  lea     r15, [r12+r15*8]
0x18000b98a  lea     rcx, [r15+10h]
0x18000b98e  call    cs:__imp_RtlAcquireSRWLockShared
0x18000b994  mov     r14, [r15]
0x18000b997  cmp     r14, r15
0x18000b99a  jz      loc_18000BA97
0x18000b9a0  lea     rbx, [r14-18h]
0x18000b9a4  cmp     rdi, [rbx+10h]
0x18000b9a8  jz      short loc_18000B9AF
0x18000b9aa  mov     r14, [r14]
0x18000b9ad  jmp     short loc_18000B997
0x18000b9af  mov     rcx, [rbx+8]
0x18000b9b3  lea     r8, [rsp+2E8h+Src]
0x18000b9b8  mov     rdx, rdi
0x18000b9bb  mov     byte ptr [rsp+2E8h+var_2C8], 1
0x18000b9c0  shr     rdx, 1
0x18000b9c3  mov     r9, rdx
0x18000b9c6  call    cs:__imp_RtlCompareUnicodeStrings
0x18000b9cc  test    eax, eax
0x18000b9ce  jnz     short loc_18000B9AA
0x18000b9d0  prefetchw byte ptr [rbx]
0x18000b9d3  mov     eax, [rbx]
0x18000b9d5  test    eax, eax
0x18000b9d7  jle     short loc_18000B9AA
0x18000b9d9  mov     edx, eax
0x18000b9db  lea     ecx, [rax+1]
0x18000b9de  lock cmpxchg [rbx], ecx
0x18000b9e2  cmp     eax, edx
0x18000b9e4  jnz     short loc_18000B9D5
0x18000b9e6  lea     rcx, [r15+10h]
0x18000b9ea  call    cs:__imp_RtlReleaseSRWLockShared
0x18000b9f0  xor     r12d, r12d
0x18000b9f3  test    rbx, rbx
0x18000b9f6  jnz     loc_18000BA9E
0x18000b9fc  mov     rcx, gs:60h
0x18000ba05  lea     r8, [r13+0B88h]; Size
0x18000ba0c  lea     edx, [rbx+8]; Flags
0x18000ba0f  mov     rcx, [rcx+30h]; HeapHandle
0x18000ba13  call    cs:__imp_RtlAllocateHeap
0x18000ba19  mov     rdi, rax
0x18000ba1c  test    rax, rax
0x18000ba1f  jnz     loc_18000BABA
0x18000ba25  mov     eax, 0C000009Ah
0x18000ba2a  mov     rcx, [rsp+2E8h+var_48]
0x18000ba32  xor     rcx, rsp; StackCookie
0x18000ba35  call    __security_check_cookie
0x18000ba3a  mov     rbx, [rsp+2E8h+arg_18]
0x18000ba42  add     rsp, 2B0h
0x18000ba49  pop     r15
0x18000ba4b  pop     r14
0x18000ba4d  pop     r13
0x18000ba4f  pop     r12
0x18000ba51  pop     rdi
0x18000ba52  pop     rsi
0x18000ba53  pop     rbp
0x18000ba54  retn
0x18000ba55  mov     rax, [rcx+60h]
0x18000ba59  xor     r9d, r9d
0x18000ba5c  mov     [rsp+2E8h+var_2A8], rax
0x18000ba61  lea     rcx, [rsp+2E8h+Src]; Buffer
0x18000ba66  mov     [rsp+2E8h+var_2B0], 2Ah ; '*'
0x18000ba6e  lea     rax, aWsWcI64d; "%ws%wc%I64d"
0x18000ba75  mov     qword ptr [rsp+2E8h+Args], rdx; Args
0x18000ba7a  xor     r8d, r8d
0x18000ba7d  mov     [rsp+2E8h+Format], rax; Format
0x18000ba82  mov     rdx, r10
0x18000ba85  mov     [rsp+2E8h+var_2C8], 800h; int
0x18000ba8d  call    RtlStringCbPrintfExW
0x18000ba92  jmp     loc_18000B8EF
0x18000ba97  xor     ebx, ebx
0x18000ba99  jmp     loc_18000B9E6
0x18000ba9e  or      eax, 0FFFFFFFFh
0x18000baa1  lock xadd [rbx], eax
0x18000baa5  dec     eax
0x18000baa7  cmp     eax, 0FFFFFFFFh
0x18000baaa  jnz     loc_18000BBCF
0x18000bab0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000bab5  jmp     loc_18000BBCF
0x18000baba  lea     rbx, [rax+0B88h]
0x18000bac1  mov     r8, r13; Size
0x18000bac4  mov     rcx, rbx; void *
0x18000bac7  lea     rdx, [rsp+2E8h+Src]; Src
0x18000bacc  call    memcpy_0
0x18000bad1  mov     [rdi+8], rbx
0x18000bad5  lea     rax, PsmpUsageTable
0x18000badc  mov     rbx, [rsp+2E8h+var_298]
0x18000bae1  mov     rcx, rbp
0x18000bae4  sub     rcx, rax
0x18000bae7  mov     dword ptr [rdi], 1
0x18000baed  mov     [rdi+10h], r13
0x18000baf1  sub     rcx, 8
0x18000baf5  mov     rax, 2AAAAAAAAAAAAAABh
0x18000baff  imul    rcx
0x18000bb02  lea     rcx, [rdi+78h]
0x18000bb06  sar     rdx, 2
0x18000bb0a  mov     rax, rdx
0x18000bb0d  shr     rax, 3Fh
0x18000bb11  add     rdx, rax
0x18000bb14  lea     rax, [rdi+18h]
0x18000bb18  mov     [rdi+4], edx
0x18000bb1b  mov     [rax+8], rax
0x18000bb1f  mov     [rax], rax
0x18000bb22  mov     rax, [rbx+60h]
0x18000bb26  mov     [rdi+70h], rax
0x18000bb2a  call    cs:__imp_RtlInitializeSRWLock
0x18000bb30  mov     r8, [rbx+138h]
0x18000bb37  lea     rdx, [rdi+28h]; DestinationSid
0x18000bb3b  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000bb40  mov     r8, [r8+28h]; SourceSid
0x18000bb44  call    cs:__imp_RtlCopySid
0x18000bb4a  lea     rcx, [rbp+10h]
0x18000bb4e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000bb54  mov     r14, [rbp+0]
0x18000bb58  cmp     r14, rbp
0x18000bb5b  jz      loc_18000BBEA
0x18000bb61  lea     rbx, [r14-18h]
0x18000bb65  cmp     rsi, [rbx+10h]
0x18000bb69  jz      short loc_18000BB70
0x18000bb6b  mov     r14, [r14]
0x18000bb6e  jmp     short loc_18000BB58
0x18000bb70  mov     rcx, [rbx+8]
0x18000bb74  lea     r8, [rsp+2E8h+Src]
0x18000bb79  mov     rdx, rsi
0x18000bb7c  mov     byte ptr [rsp+2E8h+var_2C8], 1
0x18000bb81  shr     rdx, 1
0x18000bb84  mov     r9, rdx
0x18000bb87  call    cs:__imp_RtlCompareUnicodeStrings
0x18000bb8d  test    eax, eax
0x18000bb8f  jnz     short loc_18000BB6B
0x18000bb91  prefetchw byte ptr [rbx]
0x18000bb94  mov     eax, [rbx]
0x18000bb96  test    eax, eax
0x18000bb98  jle     short loc_18000BB6B
0x18000bb9a  mov     edx, eax
0x18000bb9c  lea     ecx, [rax+1]
0x18000bb9f  lock cmpxchg [rbx], ecx
0x18000bba3  cmp     eax, edx
0x18000bba5  jnz     short loc_18000BB96
0x18000bba7  mov     rsi, rbx
0x18000bbaa  test    rbx, rbx
0x18000bbad  jnz     short loc_18000BBC0
0x18000bbaf  mov     rdx, rdi
0x18000bbb2  mov     rcx, rbp
0x18000bbb5  call    PsmpInsertHashEntry
0x18000bbba  mov     rbx, rdi
0x18000bbbd  mov     rdi, r12
0x18000bbc0  lea     rcx, [rbp+10h]
0x18000bbc4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000bbca  test    rdi, rdi
0x18000bbcd  jnz     short loc_18000BBEF
0x18000bbcf  mov     rcx, [rsp+2E8h+var_290]
0x18000bbd4  mov     eax, r12d
0x18000bbd7  mov     [rcx], rbx
0x18000bbda  jmp     loc_18000BA2A
0x18000bbdf  mov     r15, rbp
0x18000bbe2  mov     rdi, r13
0x18000bbe5  jmp     loc_18000B98A
0x18000bbea  mov     rsi, r12
0x18000bbed  jmp     short loc_18000BBAF
0x18000bbef  xor     edx, edx
0x18000bbf1  mov     rcx, rsi
0x18000bbf4  call    PsmpDereferenceObjectEx
0x18000bbf9  mov     rcx, gs:60h
0x18000bc02  mov     r8, rdi; P
0x18000bc05  xor     edx, edx; Flags
0x18000bc07  mov     rcx, [rcx+30h]; HeapHandle
0x18000bc0b  call    cs:__imp_RtlFreeHeap
0x18000bc11  jmp     short loc_18000BBCF
```
