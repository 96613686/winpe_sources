# Smb2ComputeOutgoingSignatureForRdmaBuffer

- ea: `0x140033234`
- end: `0x1400334ab`
- name: `Smb2ComputeOutgoingSignatureForRdmaBuffer`
- size: `631`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140020490`
- `0x140031250`

## callees

- `0x14002a1dc`
- `0x14002a6a8`
- `0x140033234`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140033485`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033485`
- `ntoskrnl!ExAllocatePool2` at `0x140033272`
- `ntoskrnl!ExAllocatePool2` at `0x140033272`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400333ad`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400333ad`
- `ksecdd!BCryptHashData` at `0x1400333db`
- `ksecdd!BCryptHashData` at `0x1400333db`
- `ksecdd!BCryptFinishHash` at `0x140033409`
- `ksecdd!BCryptFinishHash` at `0x140033409`
- `ksecdd!BCryptDuplicateHash` at `0x1400332ae`
- `ksecdd!BCryptDuplicateHash` at `0x1400332ae`
- `ksecdd!BCryptDestroyHash` at `0x140033463`
- `ksecdd!BCryptDestroyHash` at `0x140033463`
- `mrxsmb!SmbCryptoCalculateAndSetIVForRdmaBuffer` at `0x14003332a`
- `mrxsmb!SmbCryptoCalculateAndSetIVForRdmaBuffer` at `0x14003332a`

## pseudocode

```c
__int64 __fastcall Smb2ComputeOutgoingSignatureForRdmaBuffer(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  UCHAR *Pool2; // rax
  UCHAR *v6; // r15
  NTSTATUS v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  struct _MDL *v10; // rdi
  ULONG i; // ebp
  UCHAR *MappedSystemVa; // rax
  ULONG ByteCount; // r12d
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 96LL);
  phNewHash = 0;
  Pool2 = (UCHAR *)ExAllocatePool2(66, *(unsigned int *)(v4 + 512), 1834184520);
  v6 = Pool2;
  if ( !Pool2 )
  {
LABEL_2:
    v7 = -1073741670;
    goto LABEL_30;
  }
  v7 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(v4 + 496), &phNewHash, Pool2, *(_DWORD *)(v4 + 512), 0);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_60db1590be613abca80435fd5891bee8_Traceguids,
        *(_QWORD *)(a1 + 56),
        a1,
        v7);
    }
    goto LABEL_30;
  }
  v7 = SmbCryptoCalculateAndSetIVForRdmaBuffer(
         phNewHash,
         a2 + *(unsigned __int16 *)(a2 + 2) + 8LL,
         *(unsigned __int16 *)(a2 + 4));
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_30;
    }
    v9 = 22;
LABEL_29:
    WPP_SF_qq(v8->AttachedDevice, v9, WPP_60db1590be613abca80435fd5891bee8_Traceguids, *(_QWORD *)(a1 + 56), a1);
    goto LABEL_30;
  }
  v10 = *(struct _MDL **)(a1 + 768);
  for ( i = *(_DWORD *)(a1 + 776); v10 && i; i -= ByteCount )
  {
    if ( (v10->MdlFlags & 5) != 0 )
      MappedSystemVa = (UCHAR *)v10->MappedSystemVa;
    else
      MappedSystemVa = (UCHAR *)MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u);
    if ( !MappedSystemVa )
      goto LABEL_2;
    ByteCount = v10->ByteCount;
    if ( ByteCount >= i )
      ByteCount = i;
    v7 = BCryptHashData(phNewHash, MappedSystemVa, ByteCount, 0);
    if ( v7 < 0 )
      goto LABEL_30;
    v10 = v10->Next;
  }
  v7 = BCryptFinishHash(phNewHash, (PUCHAR)(a2 + 8), *(unsigned __int16 *)(a2 + 2), 0);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v9 = 23;
      goto LABEL_29;
    }
  }
LABEL_30:
  if ( phNewHash )
  {
    BCryptDestroyHash(phNewHash);
    phNewHash = 0;
  }
  if ( v6 )
    ExFreePoolWithTag(v6, 0x6D536F48u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140033234  mov     [rsp+arg_8], rbx
0x140033239  mov     [rsp+arg_10], rbp
0x14003323e  push    rsi
0x14003323f  push    rdi
0x140033240  push    r12
0x140033242  push    r14
0x140033244  push    r15
0x140033246  sub     rsp, 30h
0x14003324a  mov     rax, [rcx+38h]
0x14003324e  mov     r14, rdx
0x140033251  mov     rsi, rcx
0x140033254  mov     r8d, 6D536F48h
0x14003325a  mov     ecx, 42h ; 'B'
0x14003325f  mov     rbx, [rax+60h]
0x140033263  mov     [rsp+58h+phNewHash], 0
0x14003326c  mov     edx, [rbx+200h]
0x140033272  call    cs:__imp_ExAllocatePool2
0x140033279  nop     dword ptr [rax+rax+00h]
0x14003327e  mov     r15, rax
0x140033281  test    rax, rax
0x140033284  jnz     short loc_140033290
0x140033286  mov     ebx, 0C000009Ah
0x14003328b  jmp     loc_140033459
0x140033290  mov     r9d, [rbx+200h]; cbHashObject
0x140033297  lea     rdx, [rsp+58h+phNewHash]; phNewHash
0x14003329c  mov     rcx, [rbx+1F0h]; hHash
0x1400332a3  mov     r8, r15; pbHashObject
0x1400332a6  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1400332ae  call    cs:__imp_BCryptDuplicateHash
0x1400332b5  nop     dword ptr [rax+rax+00h]
0x1400332ba  mov     ebx, eax
0x1400332bc  test    eax, eax
0x1400332be  jns     short loc_140033314
0x1400332c0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400332c7  lea     rax, WPP_GLOBAL_Control
0x1400332ce  cmp     rcx, rax
0x1400332d1  jz      loc_140033459
0x1400332d7  mov     edx, [rcx+2Ch]
0x1400332da  test    dl, 1
0x1400332dd  jz      loc_140033459
0x1400332e3  cmp     byte ptr [rcx+29h], 1
0x1400332e7  jb      loc_140033459
0x1400332ed  mov     r9, [rsi+38h]
0x1400332f1  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x1400332f8  mov     rcx, [rcx+18h]
0x1400332fc  mov     edx, 15h
0x140033301  mov     [rsp+58h+Priority], ebx
0x140033305  mov     qword ptr [rsp+58h+dwFlags], rsi
0x14003330a  call    WPP_SF_qqD
0x14003330f  jmp     loc_140033459
0x140033314  movzx   edx, word ptr [r14+2]
0x140033319  movzx   r8d, word ptr [r14+4]
0x14003331e  add     rdx, 8
0x140033322  mov     rcx, [rsp+58h+phNewHash]
0x140033327  add     rdx, r14
0x14003332a  call    cs:__imp_SmbCryptoCalculateAndSetIVForRdmaBuffer
0x140033331  nop     dword ptr [rax+rax+00h]
0x140033336  mov     ebx, eax
0x140033338  test    eax, eax
0x14003333a  jns     short loc_140033372
0x14003333c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033343  lea     rax, WPP_GLOBAL_Control
0x14003334a  cmp     rcx, rax
0x14003334d  jz      loc_140033459
0x140033353  mov     eax, [rcx+2Ch]
0x140033356  test    al, 1
0x140033358  jz      loc_140033459
0x14003335e  cmp     byte ptr [rcx+29h], 1
0x140033362  jb      loc_140033459
0x140033368  mov     edx, 16h
0x14003336d  jmp     loc_140033440
0x140033372  mov     rdi, [rsi+300h]
0x140033379  mov     ebp, [rsi+308h]
0x14003337f  jmp     short loc_1400333F3
0x140033381  test    ebp, ebp
0x140033383  jz      short loc_1400333F8
0x140033385  test    byte ptr [rdi+0Ah], 5
0x140033389  jz      short loc_140033391
0x14003338b  mov     rax, [rdi+18h]
0x14003338f  jmp     short loc_1400333B9
0x140033391  xor     r9d, r9d; RequestedAddress
0x140033394  mov     [rsp+58h+Priority], 40000010h; Priority
0x14003339c  xor     edx, edx; AccessMode
0x14003339e  mov     [rsp+58h+dwFlags], 0; BugCheckOnFailure
0x1400333a6  mov     rcx, rdi; MemoryDescriptorList
0x1400333a9  lea     r8d, [r9+1]; CacheType
0x1400333ad  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400333b4  nop     dword ptr [rax+rax+00h]
0x1400333b9  test    rax, rax
0x1400333bc  jz      loc_140033286
0x1400333c2  mov     r12d, [rdi+28h]
0x1400333c6  mov     rdx, rax; pbInput
0x1400333c9  mov     rcx, [rsp+58h+phNewHash]; hHash
0x1400333ce  cmp     r12d, ebp
0x1400333d1  cmovnb  r12d, ebp
0x1400333d5  xor     r9d, r9d; dwFlags
0x1400333d8  mov     r8d, r12d; cbInput
0x1400333db  call    cs:__imp_BCryptHashData
0x1400333e2  nop     dword ptr [rax+rax+00h]
0x1400333e7  mov     ebx, eax
0x1400333e9  test    eax, eax
0x1400333eb  js      short loc_140033459
0x1400333ed  mov     rdi, [rdi]
0x1400333f0  sub     ebp, r12d
0x1400333f3  test    rdi, rdi
0x1400333f6  jnz     short loc_140033381
0x1400333f8  movzx   r8d, word ptr [r14+2]; cbOutput
0x1400333fd  lea     rdx, [r14+8]; pbOutput
0x140033401  mov     rcx, [rsp+58h+phNewHash]; hHash
0x140033406  xor     r9d, r9d; dwFlags
0x140033409  call    cs:__imp_BCryptFinishHash
0x140033410  nop     dword ptr [rax+rax+00h]
0x140033415  mov     ebx, eax
0x140033417  test    eax, eax
0x140033419  jns     short loc_140033459
0x14003341b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033422  lea     rax, WPP_GLOBAL_Control
0x140033429  cmp     rcx, rax
0x14003342c  jz      short loc_140033459
0x14003342e  mov     eax, [rcx+2Ch]
0x140033431  test    al, 1
0x140033433  jz      short loc_140033459
0x140033435  cmp     byte ptr [rcx+29h], 1
0x140033439  jb      short loc_140033459
0x14003343b  mov     edx, 17h
0x140033440  mov     r9, [rsi+38h]
0x140033444  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14003344b  mov     rcx, [rcx+18h]
0x14003344f  mov     qword ptr [rsp+58h+dwFlags], rsi
0x140033454  call    WPP_SF_qq
0x140033459  mov     rcx, [rsp+58h+phNewHash]; hHash
0x14003345e  test    rcx, rcx
0x140033461  jz      short loc_140033478
0x140033463  call    cs:__imp_BCryptDestroyHash
0x14003346a  nop     dword ptr [rax+rax+00h]
0x14003346f  mov     [rsp+58h+phNewHash], 0
0x140033478  test    r15, r15
0x14003347b  jz      short loc_140033491
0x14003347d  mov     edx, 6D536F48h; Tag
0x140033482  mov     rcx, r15; P
0x140033485  call    cs:__imp_ExFreePoolWithTag
0x14003348c  nop     dword ptr [rax+rax+00h]
0x140033491  mov     rbp, [rsp+58h+arg_10]
0x140033496  mov     eax, ebx
0x140033498  mov     rbx, [rsp+58h+arg_8]
0x14003349d  add     rsp, 30h
0x1400334a1  pop     r15
0x1400334a3  pop     r14
0x1400334a5  pop     r12
0x1400334a7  pop     rdi
0x1400334a8  pop     rsi
0x1400334a9  retn
```
