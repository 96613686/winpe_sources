# NfsRdrCryptoInit

- ea: `0x14002e5a8`
- end: `0x14002e7f5`
- name: `NfsRdrCryptoInit`
- size: `589`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE *phAlgorithm)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002d428`

## callees

- `0x140018310`
- `0x14001db18`
- `0x14002e5a8`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e732`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e732`
- `ntoskrnl!ExAllocatePool2` at `0x14002e76c`
- `ntoskrnl!ExAllocatePool2` at `0x14002e76c`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14002e62c`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14002e62c`
- `ksecdd!BCryptGetProperty` at `0x14002e694`
- `ksecdd!BCryptGetProperty` at `0x14002e6e7`
- `ksecdd!BCryptGetProperty` at `0x14002e694`
- `ksecdd!BCryptGetProperty` at `0x14002e6e7`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14002e750`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14002e750`

## pseudocode

```c
__int64 __fastcall NfsRdrCryptoInit(BCRYPT_ALG_HANDLE *phAlgorithm)
{
  NTSTATUS v2; // eax
  NTSTATUS Property; // ebx
  char v4; // bp
  PDEVICE_OBJECT v5; // rcx
  int v6; // edx
  BCRYPT_ALG_HANDLE v7; // rcx
  void *Pool2; // rax
  ULONG pcbResult; // [rsp+30h] [rbp-68h] BYREF
  char v11[24]; // [rsp+38h] [rbp-60h] BYREF

  strcpy(v11, "NfsRdrCryptoInit");
  pcbResult = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v11);
  v2 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA256", 0, 0);
  Property = v2;
  if ( v2 < 0 )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_sD(
        WPP_GLOBAL_Control->AttachedDevice,
        43,
        (unsigned int)WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
        (unsigned int)v11,
        v2);
    goto LABEL_17;
  }
  v4 = 1;
  Property = BCryptGetProperty(*phAlgorithm, L"ObjectLength", (PUCHAR)phAlgorithm + 16, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_17;
    v6 = 44;
LABEL_16:
    WPP_SF_sD(
      v5->AttachedDevice,
      v6,
      (unsigned int)WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
      (unsigned int)v11,
      Property);
LABEL_17:
    v7 = phAlgorithm[1];
    if ( v7 )
    {
      ExFreePoolWithTag(v7, 0);
      phAlgorithm[1] = 0;
    }
    if ( v4 )
      BCryptCloseAlgorithmProvider(*phAlgorithm, 0);
    goto LABEL_25;
  }
  Property = BCryptGetProperty(*phAlgorithm, L"HashDigestLength", (PUCHAR)phAlgorithm + 20, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_17;
    v6 = 45;
    goto LABEL_16;
  }
  Pool2 = (void *)ExAllocatePool2(258, *((unsigned int *)phAlgorithm + 4), 1465017934);
  phAlgorithm[1] = Pool2;
  if ( !Pool2
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v11);
  }
LABEL_25:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_sD(
      WPP_GLOBAL_Control->AttachedDevice,
      47,
      (unsigned int)WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
      (unsigned int)v11,
      Property);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14002e5a8  push    rbx
0x14002e5aa  push    rbp
0x14002e5ab  push    rsi
0x14002e5ac  push    rdi
0x14002e5ad  push    r12
0x14002e5af  push    r15
0x14002e5b1  sub     rsp, 68h
0x14002e5b5  mov     rax, cs:__security_cookie
0x14002e5bc  xor     rax, rsp
0x14002e5bf  mov     [rsp+98h+var_48], rax
0x14002e5c4  movups  xmm0, xmmword ptr cs:aNfsrdrcryptoin; "NfsRdrCryptoInit"
0x14002e5cb  mov     al, byte ptr cs:aNfsrdrcryptoin+10h; ""
0x14002e5d1  mov     rdi, rcx
0x14002e5d4  mov     [rsp+98h+var_60+10h], al
0x14002e5d8  movups  xmmword ptr [rsp+98h+var_60], xmm0
0x14002e5dd  mov     [rsp+98h+var_68], 0
0x14002e5e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e5ec  lea     r15, WPP_GLOBAL_Control
0x14002e5f3  lea     r12, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002e5fa  cmp     rcx, r15
0x14002e5fd  jz      short loc_14002E61C
0x14002e5ff  mov     eax, [rcx+2Ch]
0x14002e602  test    al, 8
0x14002e604  jz      short loc_14002E61C
0x14002e606  mov     rcx, [rcx+18h]
0x14002e60a  lea     r9, [rsp+98h+var_60]
0x14002e60f  mov     edx, 2Ah ; '*'
0x14002e614  mov     r8, r12
0x14002e617  call    WPP_SF_s
0x14002e61c  xor     r9d, r9d; dwFlags
0x14002e61f  lea     rdx, pszAlgId; "SHA256"
0x14002e626  xor     r8d, r8d; pszImplementation
0x14002e629  mov     rcx, rdi; phAlgorithm
0x14002e62c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002e633  nop     dword ptr [rax+rax+00h]
0x14002e638  mov     ebx, eax
0x14002e63a  test    eax, eax
0x14002e63c  jns     short loc_14002E66B
0x14002e63e  xor     bpl, bpl
0x14002e641  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e648  cmp     rcx, r15
0x14002e64b  jz      loc_14002E727
0x14002e651  mov     edx, [rcx+2Ch]
0x14002e654  test    dl, 1
0x14002e657  jz      loc_14002E727
0x14002e65d  mov     edx, 2Bh ; '+'
0x14002e662  mov     dword ptr [rsp+98h+pcbResult], eax
0x14002e666  jmp     loc_14002E716
0x14002e66b  mov     rcx, [rdi]; hObject
0x14002e66e  lea     rax, [rsp+98h+var_68]
0x14002e673  mov     [rsp+98h+dwFlags], 0; dwFlags
0x14002e67b  lea     r8, [rdi+10h]; pbOutput
0x14002e67f  mov     r9d, 4; cbOutput
0x14002e685  mov     [rsp+98h+pcbResult], rax; pcbResult
0x14002e68a  lea     rdx, pszProperty; "ObjectLength"
0x14002e691  mov     bpl, 1
0x14002e694  call    cs:__imp_BCryptGetProperty
0x14002e69b  nop     dword ptr [rax+rax+00h]
0x14002e6a0  mov     ebx, eax
0x14002e6a2  test    eax, eax
0x14002e6a4  jns     short loc_14002E6C1
0x14002e6a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e6ad  cmp     rcx, r15
0x14002e6b0  jz      short loc_14002E727
0x14002e6b2  mov     eax, [rcx+2Ch]
0x14002e6b5  test    bpl, al
0x14002e6b8  jz      short loc_14002E727
0x14002e6ba  mov     edx, 2Ch ; ','
0x14002e6bf  jmp     short loc_14002E712
0x14002e6c1  mov     rcx, [rdi]; hObject
0x14002e6c4  lea     rax, [rsp+98h+var_68]
0x14002e6c9  lea     r8, [rdi+14h]; pbOutput
0x14002e6cd  mov     [rsp+98h+dwFlags], 0; dwFlags
0x14002e6d5  mov     r9d, 4; cbOutput
0x14002e6db  mov     [rsp+98h+pcbResult], rax; pcbResult
0x14002e6e0  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14002e6e7  call    cs:__imp_BCryptGetProperty
0x14002e6ee  nop     dword ptr [rax+rax+00h]
0x14002e6f3  mov     ebx, eax
0x14002e6f5  test    eax, eax
0x14002e6f7  jns     short loc_14002E75E
0x14002e6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e700  cmp     rcx, r15
0x14002e703  jz      short loc_14002E727
0x14002e705  mov     eax, [rcx+2Ch]
0x14002e708  test    bpl, al
0x14002e70b  jz      short loc_14002E727
0x14002e70d  mov     edx, 2Dh ; '-'
0x14002e712  mov     dword ptr [rsp+98h+pcbResult], ebx
0x14002e716  mov     rcx, [rcx+18h]
0x14002e71a  lea     r9, [rsp+98h+var_60]
0x14002e71f  mov     r8, r12
0x14002e722  call    WPP_SF_sD
0x14002e727  mov     rcx, [rdi+8]; P
0x14002e72b  test    rcx, rcx
0x14002e72e  jz      short loc_14002E746
0x14002e730  xor     edx, edx; Tag
0x14002e732  call    cs:__imp_ExFreePoolWithTag
0x14002e739  nop     dword ptr [rax+rax+00h]
0x14002e73e  mov     qword ptr [rdi+8], 0
0x14002e746  test    bpl, bpl
0x14002e749  jz      short loc_14002E7AB
0x14002e74b  mov     rcx, [rdi]; hAlgorithm
0x14002e74e  xor     edx, edx; dwFlags
0x14002e750  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14002e757  nop     dword ptr [rax+rax+00h]
0x14002e75c  jmp     short loc_14002E7AB
0x14002e75e  mov     edx, [rdi+10h]
0x14002e761  mov     ecx, 102h
0x14002e766  mov     r8d, 5752664Eh
0x14002e76c  call    cs:__imp_ExAllocatePool2
0x14002e773  nop     dword ptr [rax+rax+00h]
0x14002e778  mov     [rdi+8], rax
0x14002e77c  test    rax, rax
0x14002e77f  jnz     short loc_14002E7AB
0x14002e781  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e788  cmp     rcx, r15
0x14002e78b  jz      short loc_14002E7AB
0x14002e78d  mov     eax, [rcx+2Ch]
0x14002e790  test    bpl, al
0x14002e793  jz      short loc_14002E7AB
0x14002e795  mov     rcx, [rcx+18h]
0x14002e799  lea     r9, [rsp+98h+var_60]
0x14002e79e  mov     edx, 2Eh ; '.'
0x14002e7a3  mov     r8, r12
0x14002e7a6  call    WPP_SF_s
0x14002e7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e7b2  cmp     rcx, r15
0x14002e7b5  jz      short loc_14002E7D8
0x14002e7b7  mov     eax, [rcx+2Ch]
0x14002e7ba  test    al, 8
0x14002e7bc  jz      short loc_14002E7D8
0x14002e7be  mov     rcx, [rcx+18h]
0x14002e7c2  lea     r9, [rsp+98h+var_60]
0x14002e7c7  mov     edx, 2Fh ; '/'
0x14002e7cc  mov     dword ptr [rsp+98h+pcbResult], ebx
0x14002e7d0  mov     r8, r12
0x14002e7d3  call    WPP_SF_sD
0x14002e7d8  mov     eax, ebx
0x14002e7da  mov     rcx, [rsp+98h+var_48]
0x14002e7df  xor     rcx, rsp; StackCookie
0x14002e7e2  call    __security_check_cookie
0x14002e7e7  add     rsp, 68h
0x14002e7eb  pop     r15
0x14002e7ed  pop     r12
0x14002e7ef  pop     rdi
0x14002e7f0  pop     rsi
0x14002e7f1  pop     rbp
0x14002e7f2  pop     rbx
0x14002e7f3  retn
```
