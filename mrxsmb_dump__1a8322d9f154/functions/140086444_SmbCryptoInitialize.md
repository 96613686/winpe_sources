# SmbCryptoInitialize

- ea: `0x140086444`
- end: `0x1400865c6`
- name: `SmbCryptoInitialize`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14008cf8c`

## callees

- `0x14004d160`
- `0x140086344`
- `0x140086444`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140086476`
- `ntoskrnl!ExAllocatePool2` at `0x140086476`
- `ntoskrnl!RtlRunOnceInitialize` at `0x1400865b3`
- `ntoskrnl!RtlRunOnceInitialize` at `0x1400865b3`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140086458`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140086458`
- `ksecdd!BCryptGenRandom` at `0x1400864c8`
- `ksecdd!BCryptGenRandom` at `0x1400864c8`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140086596`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140086596`

## pseudocode

```c
__int64 SmbCryptoInitialize()
{
  ULONG MaximumProcessorCount; // esi
  __int64 v1; // rdx
  NTSTATUS v2; // ebx
  ULONG i; // edi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx

  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  SmbCryptoNonceCounter = (PVOID)ExAllocatePool2(74, MaximumProcessorCount << 6, 590500684);
  if ( !SmbCryptoNonceCounter )
  {
    v2 = -1073741670;
LABEL_3:
    SmbCryptoDeinitialize();
    return (unsigned int)v2;
  }
  for ( i = 0; i < MaximumProcessorCount; ++i )
  {
    v2 = BCryptGenRandom(0, (PUCHAR)SmbCryptoNonceCounter + 64 * (unsigned __int64)i, 8u, 2u);
    if ( v2 < 0 )
      goto LABEL_3;
  }
  v2 = SmbCryptoInitializeCipher(SmbCryptoCiphers, v1, L"ChainingModeCCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = SmbCryptoInitializeCipher(qword_14007D308, v5, L"ChainingModeGCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = SmbCryptoInitializeCipher(qword_14007D320, v6, L"ChainingModeCCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = SmbCryptoInitializeCipher(qword_14007D338, v7, L"ChainingModeGCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = BCryptOpenAlgorithmProvider(&SmbCryptoSp800108CtrHmacAlgHandle, L"SP800_108_CTR_HMAC", 0, 1u);
  if ( v2 < 0 )
    goto LABEL_3;
  RtlRunOnceInitialize(&RunOnce);
  return 0;
}

```

## disassembly

```asm
0x140086444  mov     [rsp+arg_0], rbx
0x140086449  mov     [rsp+arg_8], rsi
0x14008644e  push    rdi
0x14008644f  sub     rsp, 30h
0x140086453  mov     ecx, 0FFFFh; GroupNumber
0x140086458  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14008645f  nop     dword ptr [rax+rax+00h]
0x140086464  mov     ecx, 4Ah ; 'J'
0x140086469  mov     r8d, 2332534Ch
0x14008646f  mov     edx, eax
0x140086471  mov     esi, eax
0x140086473  shl     edx, 6
0x140086476  call    cs:__imp_ExAllocatePool2
0x14008647d  nop     dword ptr [rax+rax+00h]
0x140086482  mov     cs:SmbCryptoNonceCounter, rax
0x140086489  test    rax, rax
0x14008648c  jnz     short loc_1400864AB
0x14008648e  mov     ebx, 0C000009Ah
0x140086493  call    SmbCryptoDeinitialize
0x140086498  mov     eax, ebx
0x14008649a  mov     rbx, [rsp+38h+arg_0]
0x14008649f  mov     rsi, [rsp+38h+arg_8]
0x1400864a4  add     rsp, 30h
0x1400864a8  pop     rdi
0x1400864a9  retn
0x1400864ab  xor     edi, edi
0x1400864ad  cmp     edi, esi
0x1400864af  jnb     short loc_1400864DE
0x1400864b1  xor     ecx, ecx; hAlgorithm
0x1400864b3  mov     edx, edi
0x1400864b5  shl     rdx, 6
0x1400864b9  add     rdx, cs:SmbCryptoNonceCounter; pbBuffer
0x1400864c0  lea     r9d, [rcx+2]; dwFlags
0x1400864c4  lea     r8d, [rcx+8]; cbBuffer
0x1400864c8  call    cs:__imp_BCryptGenRandom
0x1400864cf  nop     dword ptr [rax+rax+00h]
0x1400864d4  mov     ebx, eax
0x1400864d6  test    eax, eax
0x1400864d8  js      short loc_140086493
0x1400864da  inc     edi
0x1400864dc  jmp     short loc_1400864AD
0x1400864de  mov     edi, 10h
0x1400864e3  lea     r8, aChainingmodecc; "ChainingModeCCM"
0x1400864ea  mov     [rsp+38h+var_10], edi
0x1400864ee  lea     rcx, SmbCryptoCiphers
0x1400864f5  lea     esi, [rdi-5]
0x1400864f8  mov     [rsp+38h+var_18], esi
0x1400864fc  call    SmbCryptoInitializeCipher
0x140086501  mov     ebx, eax
0x140086503  test    eax, eax
0x140086505  js      short loc_140086493
0x140086507  mov     [rsp+38h+var_10], edi
0x14008650b  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x140086512  lea     rcx, qword_14007D308
0x140086519  mov     [rsp+38h+var_18], 0Ch
0x140086521  call    SmbCryptoInitializeCipher
0x140086526  mov     ebx, eax
0x140086528  test    eax, eax
0x14008652a  js      loc_140086493
0x140086530  lea     edi, [rsi+15h]
0x140086533  mov     [rsp+38h+var_10], edi
0x140086537  lea     r8, aChainingmodecc; "ChainingModeCCM"
0x14008653e  lea     rcx, qword_14007D320
0x140086545  mov     [rsp+38h+var_18], esi
0x140086549  call    SmbCryptoInitializeCipher
0x14008654e  mov     ebx, eax
0x140086550  test    eax, eax
0x140086552  js      loc_140086493
0x140086558  mov     [rsp+38h+var_10], edi
0x14008655c  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x140086563  lea     rcx, qword_14007D338
0x14008656a  mov     [rsp+38h+var_18], 0Ch
0x140086572  call    SmbCryptoInitializeCipher
0x140086577  mov     ebx, eax
0x140086579  test    eax, eax
0x14008657b  js      loc_140086493
0x140086581  lea     r9d, [rsi-0Ah]; dwFlags
0x140086585  xor     r8d, r8d; pszImplementation
0x140086588  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x14008658f  lea     rcx, SmbCryptoSp800108CtrHmacAlgHandle; phAlgorithm
0x140086596  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14008659d  nop     dword ptr [rax+rax+00h]
0x1400865a2  mov     ebx, eax
0x1400865a4  test    eax, eax
0x1400865a6  js      loc_140086493
0x1400865ac  lea     rcx, RunOnce; RunOnce
0x1400865b3  call    cs:__imp_RtlRunOnceInitialize
0x1400865ba  nop     dword ptr [rax+rax+00h]
0x1400865bf  xor     eax, eax
0x1400865c1  jmp     loc_14008649A
```
