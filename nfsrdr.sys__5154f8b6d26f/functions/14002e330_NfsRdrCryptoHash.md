# NfsRdrCryptoHash

- ea: `0x14002e330`
- end: `0x14002e5a0`
- name: `NfsRdrCryptoHash`
- size: `624`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140028870`
- `0x140028ac8`

## callees

- `0x140018310`
- `0x14001db18`
- `0x14002e330`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e523`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e523`
- `ntoskrnl!ExAllocatePool2` at `0x14002e3c3`
- `ntoskrnl!ExAllocatePool2` at `0x14002e3c3`
- `ksecdd!BCryptCreateHash` at `0x14002e435`
- `ksecdd!BCryptCreateHash` at `0x14002e435`
- `ksecdd!BCryptHashData` at `0x14002e47f`
- `ksecdd!BCryptHashData` at `0x14002e47f`
- `ksecdd!BCryptFinishHash` at `0x14002e4d3`
- `ksecdd!BCryptFinishHash` at `0x14002e4d3`
- `ksecdd!BCryptDestroyHash` at `0x14002e546`
- `ksecdd!BCryptDestroyHash` at `0x14002e546`

## pseudocode

```c
__int64 __fastcall NfsRdrCryptoHash(__int64 a1, PUCHAR *a2, ULONG *a3, UCHAR *a4, ULONG cbInput)
{
  char v9; // di
  ULONG v10; // eax
  __int64 Pool2; // rax
  NTSTATUS v12; // ebx
  NTSTATUS v13; // eax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-20h] BYREF
  char v16[16]; // [rsp+48h] [rbp-18h] BYREF

  strcpy(v16, "NfsRdrHash");
  phHash = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v16);
  v10 = *(_DWORD *)(a1 + 20);
  *a3 = v10;
  Pool2 = ExAllocatePool2(258, v10, 1481795150);
  *a2 = (PUCHAR)Pool2;
  if ( Pool2 )
  {
    v13 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)a1, &phHash, *(PUCHAR *)(a1 + 8), *(_DWORD *)(a1 + 16), 0, 0, 0);
    v12 = v13;
    if ( v13 >= 0 )
    {
      v12 = BCryptHashData(phHash, a4, cbInput, 0);
      if ( v12 >= 0 )
      {
        v12 = BCryptFinishHash(phHash, *a2, *a3, 0);
        if ( v12 >= 0 )
        {
LABEL_25:
          BCryptDestroyHash(phHash);
          goto LABEL_26;
        }
        v9 = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_sD(
            WPP_GLOBAL_Control->AttachedDevice,
            54,
            (unsigned int)WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
            (unsigned int)v16,
            v12);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_sD(
            WPP_GLOBAL_Control->AttachedDevice,
            53,
            (unsigned int)WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
            (unsigned int)v16,
            v12);
        v9 = 1;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_sD(
        WPP_GLOBAL_Control->AttachedDevice,
        52,
        (unsigned int)WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
        (unsigned int)v16,
        v13);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v16);
    v12 = -1073741670;
  }
  if ( *a2 )
  {
    ExFreePoolWithTag(*a2, 0);
    *a2 = 0;
    *a3 = 0;
  }
  if ( v9 )
    goto LABEL_25;
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_sD(
      WPP_GLOBAL_Control->AttachedDevice,
      55,
      (unsigned int)WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
      (unsigned int)v16,
      v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14002e330  push    rbp
0x14002e332  push    rbx
0x14002e333  push    rsi
0x14002e334  push    rdi
0x14002e335  push    r13
0x14002e337  push    r14
0x14002e339  push    r15
0x14002e33b  mov     rbp, rsp
0x14002e33e  sub     rsp, 60h
0x14002e342  mov     rax, cs:__security_cookie
0x14002e349  xor     rax, rsp
0x14002e34c  mov     [rbp+var_8], rax
0x14002e350  movsd   xmm0, qword ptr cs:aNfsrdrhash; "NfsRdrHash"
0x14002e358  mov     r15, r9
0x14002e35b  mov     eax, dword ptr cs:aNfsrdrhash+7; "ash"
0x14002e361  mov     r14, r8
0x14002e364  movsd   qword ptr [rbp+var_18], xmm0
0x14002e369  mov     rsi, rdx
0x14002e36c  mov     dword ptr [rbp+var_18+7], eax
0x14002e36f  mov     rbx, rcx
0x14002e372  mov     [rbp+phHash], 0
0x14002e37a  xor     dil, dil
0x14002e37d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e384  lea     r13, WPP_GLOBAL_Control
0x14002e38b  cmp     rcx, r13
0x14002e38e  jz      short loc_14002E3B0
0x14002e390  mov     eax, [rcx+2Ch]
0x14002e393  test    al, 8
0x14002e395  jz      short loc_14002E3B0
0x14002e397  mov     rcx, [rcx+18h]
0x14002e39b  lea     r9, [rbp+var_18]
0x14002e39f  mov     edx, 32h ; '2'
0x14002e3a4  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002e3ab  call    WPP_SF_s
0x14002e3b0  mov     eax, [rbx+14h]
0x14002e3b3  mov     ecx, 102h
0x14002e3b8  mov     edx, eax
0x14002e3ba  mov     [r14], eax
0x14002e3bd  mov     r8d, 5852664Eh
0x14002e3c3  call    cs:__imp_ExAllocatePool2
0x14002e3ca  nop     dword ptr [rax+rax+00h]
0x14002e3cf  mov     [rsi], rax
0x14002e3d2  test    rax, rax
0x14002e3d5  jnz     short loc_14002E40D
0x14002e3d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e3de  cmp     rcx, r13
0x14002e3e1  jz      short loc_14002E403
0x14002e3e3  mov     eax, [rcx+2Ch]
0x14002e3e6  test    al, 1
0x14002e3e8  jz      short loc_14002E403
0x14002e3ea  mov     rcx, [rcx+18h]
0x14002e3ee  lea     r9, [rbp+var_18]
0x14002e3f2  mov     edx, 33h ; '3'
0x14002e3f7  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002e3fe  call    WPP_SF_s
0x14002e403  mov     ebx, 0C000009Ah
0x14002e408  jmp     loc_14002E519
0x14002e40d  mov     r9d, [rbx+10h]; cbHashObject
0x14002e411  lea     rdx, [rbp+phHash]; phHash
0x14002e415  mov     r8, [rbx+8]; pbHashObject
0x14002e419  mov     rcx, [rbx]; hAlgorithm
0x14002e41c  mov     [rsp+60h+dwFlags], 0; dwFlags
0x14002e424  mov     [rsp+60h+cbSecret], 0; cbSecret
0x14002e42c  mov     [rsp+60h+pbSecret], 0; pbSecret
0x14002e435  call    cs:__imp_BCryptCreateHash
0x14002e43c  nop     dword ptr [rax+rax+00h]
0x14002e441  mov     ebx, eax
0x14002e443  test    eax, eax
0x14002e445  jns     short loc_14002E471
0x14002e447  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e44e  cmp     rcx, r13
0x14002e451  jz      loc_14002E519
0x14002e457  mov     edx, [rcx+2Ch]
0x14002e45a  test    dl, 1
0x14002e45d  jz      loc_14002E519
0x14002e463  mov     edx, 34h ; '4'
0x14002e468  mov     dword ptr [rsp+60h+pbSecret], eax
0x14002e46c  jmp     loc_14002E505
0x14002e471  mov     r8d, [rbp+cbInput]; cbInput
0x14002e475  xor     r9d, r9d; dwFlags
0x14002e478  mov     rcx, [rbp+phHash]; hHash
0x14002e47c  mov     rdx, r15; pbInput
0x14002e47f  call    cs:__imp_BCryptHashData
0x14002e486  nop     dword ptr [rax+rax+00h]
0x14002e48b  mov     ebx, eax
0x14002e48d  test    eax, eax
0x14002e48f  jns     short loc_14002E4C6
0x14002e491  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e498  cmp     rcx, r13
0x14002e49b  jz      short loc_14002E4C1
0x14002e49d  mov     eax, [rcx+2Ch]
0x14002e4a0  test    al, 1
0x14002e4a2  jz      short loc_14002E4C1
0x14002e4a4  mov     rcx, [rcx+18h]
0x14002e4a8  lea     r9, [rbp+var_18]
0x14002e4ac  mov     edx, 35h ; '5'
0x14002e4b1  mov     dword ptr [rsp+60h+pbSecret], ebx
0x14002e4b5  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002e4bc  call    WPP_SF_sD
0x14002e4c1  mov     dil, 1
0x14002e4c4  jmp     short loc_14002E519
0x14002e4c6  mov     r8d, [r14]; cbOutput
0x14002e4c9  xor     r9d, r9d; dwFlags
0x14002e4cc  mov     rdx, [rsi]; pbOutput
0x14002e4cf  mov     rcx, [rbp+phHash]; hHash
0x14002e4d3  call    cs:__imp_BCryptFinishHash
0x14002e4da  nop     dword ptr [rax+rax+00h]
0x14002e4df  mov     ebx, eax
0x14002e4e1  test    eax, eax
0x14002e4e3  jns     short loc_14002E542
0x14002e4e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e4ec  mov     dil, 1
0x14002e4ef  cmp     rcx, r13
0x14002e4f2  jz      short loc_14002E519
0x14002e4f4  mov     eax, [rcx+2Ch]
0x14002e4f7  test    dil, al
0x14002e4fa  jz      short loc_14002E519
0x14002e4fc  mov     edx, 36h ; '6'
0x14002e501  mov     dword ptr [rsp+60h+pbSecret], ebx
0x14002e505  mov     rcx, [rcx+18h]
0x14002e509  lea     r9, [rbp+var_18]
0x14002e50d  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002e514  call    WPP_SF_sD
0x14002e519  mov     rcx, [rsi]; P
0x14002e51c  test    rcx, rcx
0x14002e51f  jz      short loc_14002E53D
0x14002e521  xor     edx, edx; Tag
0x14002e523  call    cs:__imp_ExFreePoolWithTag
0x14002e52a  nop     dword ptr [rax+rax+00h]
0x14002e52f  mov     qword ptr [rsi], 0
0x14002e536  mov     dword ptr [r14], 0
0x14002e53d  test    dil, dil
0x14002e540  jz      short loc_14002E552
0x14002e542  mov     rcx, [rbp+phHash]; hHash
0x14002e546  call    cs:__imp_BCryptDestroyHash
0x14002e54d  nop     dword ptr [rax+rax+00h]
0x14002e552  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e559  cmp     rcx, r13
0x14002e55c  jz      short loc_14002E582
0x14002e55e  mov     eax, [rcx+2Ch]
0x14002e561  test    al, 8
0x14002e563  jz      short loc_14002E582
0x14002e565  mov     rcx, [rcx+18h]
0x14002e569  lea     r9, [rbp+var_18]
0x14002e56d  mov     edx, 37h ; '7'
0x14002e572  mov     dword ptr [rsp+60h+pbSecret], ebx
0x14002e576  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002e57d  call    WPP_SF_sD
0x14002e582  mov     eax, ebx
0x14002e584  mov     rcx, [rbp+var_8]
0x14002e588  xor     rcx, rsp; StackCookie
0x14002e58b  call    __security_check_cookie
0x14002e590  add     rsp, 60h
0x14002e594  pop     r15
0x14002e596  pop     r14
0x14002e598  pop     r13
0x14002e59a  pop     rdi
0x14002e59b  pop     rsi
0x14002e59c  pop     rbx
0x14002e59d  pop     rbp
0x14002e59e  retn
```
