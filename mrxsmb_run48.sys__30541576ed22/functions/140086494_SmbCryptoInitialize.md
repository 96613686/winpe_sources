# SmbCryptoInitialize

- ea: `0x140086494`
- end: `0x140086616`
- name: `SmbCryptoInitialize`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14008cfdc`

## callees

- `0x14004d160`
- `0x140086394`
- `0x140086494`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400864c6`
- `ntoskrnl!ExAllocatePool2` at `0x1400864c6`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140086603`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140086603`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400864a8`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400864a8`
- `ksecdd!BCryptGenRandom` at `0x140086518`
- `ksecdd!BCryptGenRandom` at `0x140086518`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400865e6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400865e6`

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
  v2 = SmbCryptoInitializeCipher(&SmbCryptoCiphers, v1, L"ChainingModeCCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = SmbCryptoInitializeCipher(&unk_14007D308, v5, L"ChainingModeGCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = SmbCryptoInitializeCipher(&unk_14007D320, v6, L"ChainingModeCCM");
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = SmbCryptoInitializeCipher(&unk_14007D338, v7, L"ChainingModeGCM");
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
0x140086494  mov     [rsp+arg_0], rbx
0x140086499  mov     [rsp+arg_8], rsi
0x14008649e  push    rdi
0x14008649f  sub     rsp, 30h
0x1400864a3  mov     ecx, 0FFFFh; GroupNumber
0x1400864a8  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400864af  nop     dword ptr [rax+rax+00h]
0x1400864b4  mov     ecx, 4Ah ; 'J'
0x1400864b9  mov     r8d, 2332534Ch
0x1400864bf  mov     edx, eax
0x1400864c1  mov     esi, eax
0x1400864c3  shl     edx, 6
0x1400864c6  call    cs:__imp_ExAllocatePool2
0x1400864cd  nop     dword ptr [rax+rax+00h]
0x1400864d2  mov     cs:SmbCryptoNonceCounter, rax
0x1400864d9  test    rax, rax
0x1400864dc  jnz     short loc_1400864FB
0x1400864de  mov     ebx, 0C000009Ah
0x1400864e3  call    SmbCryptoDeinitialize
0x1400864e8  mov     eax, ebx
0x1400864ea  mov     rbx, [rsp+38h+arg_0]
0x1400864ef  mov     rsi, [rsp+38h+arg_8]
0x1400864f4  add     rsp, 30h
0x1400864f8  pop     rdi
0x1400864f9  retn
0x1400864fb  xor     edi, edi
0x1400864fd  cmp     edi, esi
0x1400864ff  jnb     short loc_14008652E
0x140086501  xor     ecx, ecx; hAlgorithm
0x140086503  mov     edx, edi
0x140086505  shl     rdx, 6
0x140086509  add     rdx, cs:SmbCryptoNonceCounter; pbBuffer
0x140086510  lea     r9d, [rcx+2]; dwFlags
0x140086514  lea     r8d, [rcx+8]; cbBuffer
0x140086518  call    cs:__imp_BCryptGenRandom
0x14008651f  nop     dword ptr [rax+rax+00h]
0x140086524  mov     ebx, eax
0x140086526  test    eax, eax
0x140086528  js      short loc_1400864E3
0x14008652a  inc     edi
0x14008652c  jmp     short loc_1400864FD
0x14008652e  mov     edi, 10h
0x140086533  lea     r8, aChainingmodecc; "ChainingModeCCM"
0x14008653a  mov     [rsp+38h+var_10], edi
0x14008653e  lea     rcx, SmbCryptoCiphers
0x140086545  lea     esi, [rdi-5]
0x140086548  mov     [rsp+38h+var_18], esi
0x14008654c  call    SmbCryptoInitializeCipher
0x140086551  mov     ebx, eax
0x140086553  test    eax, eax
0x140086555  js      short loc_1400864E3
0x140086557  mov     [rsp+38h+var_10], edi
0x14008655b  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x140086562  lea     rcx, unk_14007D308
0x140086569  mov     [rsp+38h+var_18], 0Ch
0x140086571  call    SmbCryptoInitializeCipher
0x140086576  mov     ebx, eax
0x140086578  test    eax, eax
0x14008657a  js      loc_1400864E3
0x140086580  lea     edi, [rsi+15h]
0x140086583  mov     [rsp+38h+var_10], edi
0x140086587  lea     r8, aChainingmodecc; "ChainingModeCCM"
0x14008658e  lea     rcx, unk_14007D320
0x140086595  mov     [rsp+38h+var_18], esi
0x140086599  call    SmbCryptoInitializeCipher
0x14008659e  mov     ebx, eax
0x1400865a0  test    eax, eax
0x1400865a2  js      loc_1400864E3
0x1400865a8  mov     [rsp+38h+var_10], edi
0x1400865ac  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x1400865b3  lea     rcx, unk_14007D338
0x1400865ba  mov     [rsp+38h+var_18], 0Ch
0x1400865c2  call    SmbCryptoInitializeCipher
0x1400865c7  mov     ebx, eax
0x1400865c9  test    eax, eax
0x1400865cb  js      loc_1400864E3
0x1400865d1  lea     r9d, [rsi-0Ah]; dwFlags
0x1400865d5  xor     r8d, r8d; pszImplementation
0x1400865d8  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x1400865df  lea     rcx, SmbCryptoSp800108CtrHmacAlgHandle; phAlgorithm
0x1400865e6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400865ed  nop     dword ptr [rax+rax+00h]
0x1400865f2  mov     ebx, eax
0x1400865f4  test    eax, eax
0x1400865f6  js      loc_1400864E3
0x1400865fc  lea     rcx, RunOnce; RunOnce
0x140086603  call    cs:__imp_RtlRunOnceInitialize
0x14008660a  nop     dword ptr [rax+rax+00h]
0x14008660f  xor     eax, eax
0x140086611  jmp     loc_1400864EA
```
