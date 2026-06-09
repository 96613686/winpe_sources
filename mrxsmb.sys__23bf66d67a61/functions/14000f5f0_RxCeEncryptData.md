# RxCeEncryptData

- ea: `0x14000f5f0`
- end: `0x14000f892`
- name: `RxCeEncryptData`
- size: `674`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e530`
- `0x14000f1a0`
- `0x14008c2e8`

## callees

- `0x14000f5f0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000f855`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000f855`
- `ntoskrnl!ExAllocatePool2` at `0x14000f671`
- `ntoskrnl!ExAllocatePool2` at `0x14000f671`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f801`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f801`
- `rdbss!RxAllocateMdl2` at `0x14000f7e0`
- `rdbss!RxAllocateMdl2` at `0x14000f7e0`
- `ksecdd!BCryptEncrypt` at `0x14000f7b9`
- `ksecdd!BCryptEncrypt` at `0x14000f7b9`
- `NETIO!RtlCopyMdlToBuffer` at `0x14000f6d3`
- `NETIO!RtlCopyMdlToBuffer` at `0x14000f6d3`

## pseudocode

```c
__int64 __fastcall RxCeEncryptData(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, _DWORD *a6)
{
  __int64 cbOutput; // r15
  _DWORD *v9; // rsi
  __int64 result; // rax
  __int64 Pool2; // rax
  __int64 v12; // r14
  __int64 v13; // rbp
  NTSTATUS v14; // ebx
  UCHAR *pbOutput; // rdi
  unsigned int LockArray_high; // r8d
  __int64 v17; // rax
  int v18; // ecx
  int v19; // edx
  signed __int64 v20; // rbx
  struct _MDL *Mdl2; // rax
  __int64 v22; // [rsp+50h] [rbp-A8h] BYREF
  __int128 pPaddingInfo; // [rsp+60h] [rbp-98h] BYREF
  __int128 v24; // [rsp+70h] [rbp-88h]
  __int128 v25; // [rsp+80h] [rbp-78h]
  __int128 v26; // [rsp+90h] [rbp-68h]
  __int128 v27; // [rsp+A0h] [rbp-58h]
  __int64 v28; // [rsp+B0h] [rbp-48h]
  ULONG pcbResult; // [rsp+118h] [rbp+20h] BYREF

  cbOutput = a4;
  v22 = 0;
  if ( a4 >= 0xFFFFFFCC )
  {
    *a6 = -1;
    return 3221226539LL;
  }
  else
  {
    v9 = a6;
    *a6 = a4 + 52;
    if ( a4 + 132 < 0x50 )
      return 3221226539LL;
    Pool2 = ExAllocatePool2(66, a4 + 132, 1834184261);
    v12 = a5;
    v13 = Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)(Pool2 + 124) = a1;
      pbOutput = (UCHAR *)(Pool2 + 132);
      *(_DWORD *)(Pool2 + 80) = 1112364029;
      *(_DWORD *)(Pool2 + 116) = cbOutput;
      *(_DWORD *)(Pool2 + 120) = 0x10000;
      RtlCopyMdlToBuffer(a3, 0, Pool2 + 132, cbOutput, &v22);
      v28 = 0;
      pPaddingInfo = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v27 = 0;
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      v17 = *(_QWORD *)(a2 + 8);
      v18 = *(_DWORD *)(v17 + 12);
      v19 = *(_DWORD *)(v17 + 8);
      *((_QWORD *)&v25 + 1) = v13 + 84;
      LODWORD(v26) = v18;
      *(_QWORD *)&pPaddingInfo = 0x100000058LL;
      *((_QWORD *)&v24 + 1) = v13 + 100;
      LODWORD(v25) = 32;
      *((_QWORD *)&pPaddingInfo + 1) = v13 + 100;
      LODWORD(v24) = v19;
      v20 = _InterlockedExchangeAdd64(
              (volatile signed __int64 *)SmbCryptoNonceCounter + 8 * (unsigned __int64)LockArray_high,
              1u);
      *(_QWORD *)(v13 + 108) = LockArray_high;
      *(_QWORD *)(v13 + 100) = v20 + 1;
      pcbResult = 0;
      v14 = BCryptEncrypt(
              *(BCRYPT_KEY_HANDLE *)a2,
              pbOutput,
              cbOutput,
              &pPaddingInfo,
              0,
              0,
              pbOutput,
              cbOutput,
              &pcbResult,
              0);
      if ( v14 >= 0 )
      {
        Mdl2 = (struct _MDL *)RxAllocateMdl2(v13 + 80, (unsigned int)*v9, 0, 0, 0);
        *(_QWORD *)v12 = Mdl2;
        if ( Mdl2 )
        {
          MmBuildMdlForNonPagedPool(Mdl2);
          *(_WORD *)(*(_QWORD *)v12 + 10LL) |= 0x1000u;
          return 0;
        }
        v14 = -1073741670;
      }
      ExFreePoolWithTag((PVOID)v13, 0x6D536E45u);
    }
    else
    {
      v14 = -1073741670;
    }
    *(_QWORD *)v12 = 0;
    result = (unsigned int)v14;
    *v9 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000f5f0  mov     [rsp+arg_10], r8
0x14000f5f5  push    rdi
0x14000f5f6  push    r13
0x14000f5f8  push    r15
0x14000f5fa  sub     rsp, 0E0h
0x14000f601  mov     r15d, r9d
0x14000f604  mov     r13, rdx
0x14000f607  mov     rdi, rcx
0x14000f60a  mov     [rsp+0F8h+var_A8], 0
0x14000f613  lea     eax, [r15+34h]
0x14000f617  cmp     eax, 34h ; '4'
0x14000f61a  jb      loc_14000F871
0x14000f620  mov     [rsp+0F8h+var_28], rsi
0x14000f628  mov     rsi, [rsp+0F8h+arg_28]
0x14000f630  mov     [rsi], eax
0x14000f632  add     eax, 50h ; 'P'
0x14000f635  cmp     eax, 50h ; 'P'
0x14000f638  jnb     short loc_14000F644
0x14000f63a  mov     eax, 0C000042Bh
0x14000f63f  jmp     loc_14000F83C
0x14000f644  mov     [rsp+0F8h+arg_0], rbx
0x14000f64c  mov     ecx, 42h ; 'B'
0x14000f651  mov     [rsp+0F8h+var_20], rbp
0x14000f659  mov     r8d, 6D536E45h
0x14000f65f  mov     [rsp+0F8h+var_30], r12
0x14000f667  mov     edx, eax
0x14000f669  mov     [rsp+0F8h+var_38], r14
0x14000f671  call    cs:__imp_ExAllocatePool2
0x14000f678  nop     dword ptr [rax+rax+00h]
0x14000f67d  mov     r14, [rsp+0F8h+arg_20]
0x14000f685  mov     rbp, rax
0x14000f688  test    rax, rax
0x14000f68b  jnz     short loc_14000F697
0x14000f68d  mov     ebx, 0C000009Ah
0x14000f692  jmp     loc_14000F80D
0x14000f697  mov     rcx, [rsp+0F8h+arg_10]
0x14000f69f  mov     r9, r15
0x14000f6a2  mov     [rax+7Ch], rdi
0x14000f6a6  xor     edx, edx
0x14000f6a8  lea     rdi, [rax+84h]
0x14000f6af  mov     dword ptr [rax+50h], 424D53FDh
0x14000f6b6  mov     [rax+74h], r15d
0x14000f6ba  mov     r8, rdi
0x14000f6bd  mov     dword ptr [rax+78h], 10000h
0x14000f6c4  mov     ebx, 1
0x14000f6c9  lea     rax, [rsp+0F8h+var_A8]
0x14000f6ce  mov     [rsp+0F8h+pbIV], rax
0x14000f6d3  call    cs:__imp_RtlCopyMdlToBuffer
0x14000f6da  nop     dword ptr [rax+rax+00h]
0x14000f6df  xor     eax, eax
0x14000f6e1  lea     r9, [rbp+64h]
0x14000f6e5  mov     [rsp+0F8h+var_48], rax
0x14000f6ed  xorps   xmm0, xmm0
0x14000f6f0  movups  [rsp+0F8h+pPaddingInfo], xmm0
0x14000f6f5  movups  [rsp+0F8h+var_88], xmm0
0x14000f6fa  movups  [rsp+0F8h+var_78], xmm0
0x14000f702  movups  [rsp+0F8h+var_68], xmm0
0x14000f70a  movups  [rsp+0F8h+var_58], xmm0
0x14000f712  mov     r8d, gs:1A4h
0x14000f71b  mov     rax, [r13+8]
0x14000f71f  mov     ecx, [rax+0Ch]
0x14000f722  mov     edx, [rax+8]
0x14000f725  lea     rax, [rbp+54h]
0x14000f729  mov     qword ptr [rsp+0F8h+var_78+8], rax
0x14000f731  mov     eax, r8d
0x14000f734  shl     rax, 6
0x14000f738  add     rax, cs:SmbCryptoNonceCounter
0x14000f73f  mov     dword ptr [rsp+0F8h+var_68], ecx
0x14000f746  mov     dword ptr [rsp+0F8h+pPaddingInfo], 58h ; 'X'
0x14000f74e  mov     dword ptr [rsp+0F8h+pPaddingInfo+4], ebx
0x14000f752  mov     qword ptr [rsp+0F8h+var_88+8], r9
0x14000f757  mov     dword ptr [rsp+0F8h+var_78], 20h ; ' '
0x14000f762  mov     qword ptr [rsp+0F8h+pPaddingInfo+8], r9
0x14000f767  mov     dword ptr [rsp+0F8h+var_88], edx
0x14000f76b  mov     ecx, r8d
0x14000f76e  lock xadd [rax], rbx
0x14000f773  mov     [rbp+6Ch], rcx
0x14000f777  lea     rax, [rsp+0F8h+arg_18]
0x14000f77f  xor     ecx, ecx
0x14000f781  inc     rbx
0x14000f784  mov     [rsp+0F8h+dwFlags], ecx; dwFlags
0x14000f788  mov     r8d, r15d; cbInput
0x14000f78b  mov     [rsp+0F8h+pcbResult], rax; pcbResult
0x14000f790  mov     rdx, rdi; pbInput
0x14000f793  mov     [rsp+0F8h+cbOutput], r15d; cbOutput
0x14000f798  mov     [r9], rbx
0x14000f79b  lea     r9, [rsp+0F8h+pPaddingInfo]; pPaddingInfo
0x14000f7a0  mov     [rsp+0F8h+pbOutput], rdi; pbOutput
0x14000f7a5  mov     [rsp+0F8h+cbIV], ecx; cbIV
0x14000f7a9  mov     [rsp+0F8h+pbIV], rcx; pbIV
0x14000f7ae  mov     [rsp+0F8h+arg_18], ecx
0x14000f7b5  mov     rcx, [r13+0]; hKey
0x14000f7b9  call    cs:__imp_BCryptEncrypt
0x14000f7c0  nop     dword ptr [rax+rax+00h]
0x14000f7c5  mov     ebx, eax
0x14000f7c7  test    eax, eax
0x14000f7c9  js      short loc_14000F7F9
0x14000f7cb  mov     edx, [rsi]
0x14000f7cd  lea     rcx, [rbp+50h]
0x14000f7d1  xor     r9d, r9d
0x14000f7d4  mov     [rsp+0F8h+pbIV], 0
0x14000f7dd  xor     r8d, r8d
0x14000f7e0  call    cs:__imp_RxAllocateMdl2
0x14000f7e7  nop     dword ptr [rax+rax+00h]
0x14000f7ec  mov     [r14], rax
0x14000f7ef  test    rax, rax
0x14000f7f2  jnz     short loc_14000F852
0x14000f7f4  mov     ebx, 0C000009Ah
0x14000f7f9  mov     edx, 6D536E45h; Tag
0x14000f7fe  mov     rcx, rbp; P
0x14000f801  call    cs:__imp_ExFreePoolWithTag
0x14000f808  nop     dword ptr [rax+rax+00h]
0x14000f80d  mov     qword ptr [r14], 0
0x14000f814  mov     eax, ebx
0x14000f816  mov     dword ptr [rsi], 0
0x14000f81c  mov     r12, [rsp+0F8h+var_30]
0x14000f824  mov     rbx, [rsp+0F8h+arg_0]
0x14000f82c  mov     rbp, [rsp+0F8h+var_20]
0x14000f834  mov     r14, [rsp+0F8h+var_38]
0x14000f83c  mov     rsi, [rsp+0F8h+var_28]
0x14000f844  add     rsp, 0E0h
0x14000f84b  pop     r15
0x14000f84d  pop     r13
0x14000f84f  pop     rdi
0x14000f850  retn
0x14000f852  mov     rcx, rax; MemoryDescriptorList
0x14000f855  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000f85c  nop     dword ptr [rax+rax+00h]
0x14000f861  mov     rax, [r14]
0x14000f864  mov     ecx, 1000h
0x14000f869  or      [rax+0Ah], cx
0x14000f86d  xor     eax, eax
0x14000f86f  jmp     short loc_14000F81C
0x14000f871  mov     rax, [rsp+0F8h+arg_28]
0x14000f879  mov     dword ptr [rax], 0FFFFFFFFh
0x14000f87f  mov     eax, 0C000042Bh
0x14000f884  add     rsp, 0E0h
0x14000f88b  pop     r15
0x14000f88d  pop     r13
0x14000f88f  pop     rdi
0x14000f890  retn
```
