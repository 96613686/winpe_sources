# I_MapCatalog

- ea: `0x18005d550`
- end: `0x18005da5c`
- name: `I_MapCatalog`
- size: `1292`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING String1, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180061be0`
- `0x1800a2f98`

## callees

- `0x180010094`
- `0x180059ee4`
- `0x18005d550`
- `0x18005da64`
- `0x180065ca0`
- `0x18006cd4c`
- `0x180092a04`
- `0x180096d60`
- `0x18009f2fc`
- `0x1800e2fec`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d6fd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d7fb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d6fd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d7fb`
- `ntoskrnl!ExAllocatePool2` at `0x18005d6d7`
- `ntoskrnl!ExAllocatePool2` at `0x18005d7d1`
- `ntoskrnl!ExAllocatePool2` at `0x18005d6d7`
- `ntoskrnl!ExAllocatePool2` at `0x18005d7d1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d86a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d884`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d86a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d884`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18005d675`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18005d675`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d6ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005da39`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d6ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005da39`
- `ntoskrnl!ZwClose` at `0x18005d9a5`
- `ntoskrnl!ZwClose` at `0x18005d9ba`
- `ntoskrnl!ZwClose` at `0x18005d9a5`
- `ntoskrnl!ZwClose` at `0x18005d9ba`
- `ntoskrnl!MmUnlockPages` at `0x18005d981`
- `ntoskrnl!MmUnlockPages` at `0x18005d981`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005d9d3`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005d9d3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d727`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d73a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d825`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d838`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d727`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d73a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d825`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d838`
- `ntoskrnl!IoFreeMdl` at `0x18005d990`
- `ntoskrnl!IoFreeMdl` at `0x18005d990`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005d658`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005d658`

## pseudocode

```c
__int64 __fastcall I_MapCatalog(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        PCUNICODE_STRING String1,
        int a6,
        __int64 a7,
        _QWORD *a8,
        _QWORD *a9)
{
  const UNICODE_STRING *v9; // rdi
  PVOID *p_P; // rbx
  PVOID *p_BaseAddress; // r13
  __int64 v14; // r15
  const UNICODE_STRING *v15; // r14
  int v16; // ebx
  __int64 *i; // r14
  USHORT v18; // r15
  int v19; // eax
  USHORT v20; // bx
  unsigned int v21; // r14d
  int v22; // eax
  struct _MDL *v23; // r14
  HANDLE v25; // [rsp+50h] [rbp-31h] BYREF
  PMDL MemoryDescriptorList; // [rsp+58h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-21h] BYREF
  struct _UNICODE_STRING P; // [rsp+68h] [rbp-19h] BYREF
  __int64 v30; // [rsp+D8h] [rbp+57h] BYREF
  PVOID BaseAddress; // [rsp+E0h] [rbp+5Fh] BYREF
  __int64 v32; // [rsp+E8h] [rbp+67h]

  v32 = a4;
  v9 = (const UNICODE_STRING *)(a3 + 200);
  v25 = 0;
  Handle = 0;
  BaseAddress = 0;
  LODWORD(v30) = 0;
  LODWORD(p_P) = 0;
  MemoryDescriptorList = 0;
  P = 0;
  if ( a2 )
  {
    p_BaseAddress = &BaseAddress;
    CiLogFileEvent(v9, CiCatalogLoadStart);
  }
  else
  {
    p_BaseAddress = 0;
  }
  v14 = a7;
  if ( a7 )
    goto LABEL_7;
  if ( *v9->Buffer == 92 )
  {
    LODWORD(p_P) = (_DWORD)v9;
LABEL_7:
    v15 = String1;
    goto LABEL_8;
  }
  v15 = &stru_18002EFE0;
  if ( String1 )
    v15 = String1;
  v20 = v9->Length + 4 + v15->Length;
  P.Buffer = (PWSTR)ExAllocatePool2(258, v20, 1919109443);
  if ( !P.Buffer )
  {
    v16 = -1073741801;
    goto LABEL_57;
  }
  P.MaximumLength = v20;
  RtlCopyUnicodeString(&P, v15);
  if ( P.Buffer[((unsigned __int64)P.Length >> 1) - 1] != 92 )
    RtlAppendUnicodeStringToString(&P, &Source);
  RtlAppendUnicodeStringToString(&P, v9);
  p_P = (PVOID *)&P;
LABEL_8:
  v16 = CipMapAndSizeDataFileWithMDL(
          (int)p_P,
          a6,
          v14,
          (int)&v25,
          (__int64)&Handle,
          p_BaseAddress,
          (__int64)&v30,
          a3 + 48,
          a3 + 56,
          (__int64)&MemoryDescriptorList);
  if ( v16 == -1073741772 )
  {
    if ( v14 || *v9->Buffer == 92 || v15 && v15 != &stru_18002EFE0 && !RtlEqualUnicodeString(v15, &stru_18002EFE0, 1u) )
      goto LABEL_51;
    ExAcquirePushLockSharedEx(&g_CatalogStoreListLock, 0);
    for ( i = (__int64 *)qword_180049780; i != &qword_180049780; i = (__int64 *)*i )
    {
      if ( (*(_DWORD *)(i - 3) & 5) == 0 )
      {
        ExFreePoolWithTag(P.Buffer, 0x72634943u);
        v18 = *((_WORD *)i - 8) + v9->Length + 4;
        P.Buffer = (PWSTR)ExAllocatePool2(258, v18, 1919109443);
        if ( !P.Buffer )
        {
          v16 = -1073741801;
          ExReleasePushLockSharedEx(&g_CatalogStoreListLock, 0);
          goto LABEL_51;
        }
        P.MaximumLength = v18;
        RtlCopyUnicodeString(&P, (PCUNICODE_STRING)i - 1);
        if ( P.Buffer[((unsigned __int64)P.Length >> 1) - 1] != 92 )
          RtlAppendUnicodeStringToString(&P, &Source);
        RtlAppendUnicodeStringToString(&P, v9);
        v19 = CipMapAndSizeDataFileWithMDL(
                (int)&P,
                a6,
                0,
                (int)&v25,
                (__int64)&Handle,
                p_BaseAddress,
                (__int64)&v30,
                a3 + 48,
                a3 + 56,
                (__int64)&MemoryDescriptorList);
        v16 = v19;
        if ( v19 == -1073741766 )
        {
          v16 = -1073741772;
        }
        else if ( v19 != -1073741772 )
        {
          break;
        }
      }
    }
    ExReleasePushLockSharedEx(&g_CatalogStoreListLock, 0);
  }
  if ( v16 < 0 )
  {
    if ( v16 == -1073741538 )
      v16 = -1073740760;
    goto LABEL_51;
  }
  if ( a8 )
    *(_QWORD *)(a3 + 48) = *a8;
  if ( a9 )
    *(_QWORD *)(a3 + 56) = *a9;
  v21 = v30;
  if ( (a2 & 0x40) != 0 )
  {
    v22 = I_TransferCatalogToHvci(a3, v32, BaseAddress, (unsigned int)v30);
    v16 = v22;
    if ( v22 < 0 )
    {
      if ( v22 != -1073740285 )
        goto LABEL_51;
      I_ParseCatalogAndMapHashes(a3, BaseAddress, v21, 0);
      goto LABEL_46;
    }
  }
  if ( (a2 & 0x3C) == 0 )
    goto LABEL_49;
  v16 = I_ParseCatalogAndMapHashes(a3, BaseAddress, v21, a2);
  if ( v16 == -1073740285 )
  {
LABEL_46:
    if ( !a1 )
      goto LABEL_51;
    CiInstrumentDriverSignatureRetry(a1, a3 + 72, a3 + 168, -1073740285, 0);
  }
  if ( v16 >= 0 )
  {
LABEL_49:
    if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() )
      v16 = KappxCheckTrustLabelAce(v25, (_BYTE *)(a3 + 272));
  }
LABEL_51:
  v23 = MemoryDescriptorList;
  if ( MemoryDescriptorList )
  {
    MmUnlockPages(MemoryDescriptorList);
    IoFreeMdl(v23);
  }
  if ( Handle )
    ZwClose(Handle);
  if ( v25 )
    ZwClose(v25);
LABEL_57:
  if ( BaseAddress )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
  if ( a2 )
  {
    if ( v16 >= 0 )
    {
      CiLogFileEvent(v9, CiCatalogLoadComplete);
      goto LABEL_67;
    }
    if ( v16 == -1073740285 )
      CiLogFileEvent(v9, CiRevokedCatalog);
    else
      CiLogFileEventWithStatus(v9, (unsigned int)v16, CiInvalidCatalog);
  }
  else if ( v16 >= 0 )
  {
    goto LABEL_67;
  }
  I_FreeCatalogData((void *)a3);
LABEL_67:
  if ( P.Buffer )
    ExFreePoolWithTag(P.Buffer, 0x72634943u);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18005d550  mov     [rsp-8+arg_18], r9
0x18005d555  mov     [rsp-8+arg_0], rcx
0x18005d55a  push    rbp
0x18005d55b  push    rbx
0x18005d55c  push    rsi
0x18005d55d  push    rdi
0x18005d55e  push    r12
0x18005d560  push    r13
0x18005d562  push    r14
0x18005d564  push    r15
0x18005d566  lea     rbp, [rsp-7]
0x18005d56b  sub     rsp, 88h
0x18005d572  xor     ecx, ecx
0x18005d574  lea     rdi, [r8+0C8h]
0x18005d57b  mov     [rbp+3Fh+var_70], rcx
0x18005d57f  xorps   xmm0, xmm0
0x18005d582  mov     [rbp+3Fh+Handle], rcx
0x18005d586  mov     rsi, r8
0x18005d589  mov     [rbp+3Fh+BaseAddress], rcx
0x18005d58d  mov     r12d, edx
0x18005d590  mov     dword ptr [rbp+3Fh+arg_8], ecx
0x18005d593  mov     ebx, ecx
0x18005d595  mov     [rbp+3Fh+MemoryDescriptorList], rcx
0x18005d599  movups  xmmword ptr [rbp+3Fh+P.Length], xmm0
0x18005d59d  test    edx, edx
0x18005d59f  jz      short loc_18005D5B6
0x18005d5a1  lea     rdx, CiCatalogLoadStart
0x18005d5a8  mov     rcx, rdi
0x18005d5ab  lea     r13, [rbp+3Fh+BaseAddress]
0x18005d5af  call    CiLogFileEvent
0x18005d5b4  jmp     short loc_18005D5B9
0x18005d5b6  mov     r13, rcx
0x18005d5b9  mov     r15, [rbp+3Fh+arg_30]
0x18005d5bd  test    r15, r15
0x18005d5c0  jnz     short loc_18005D5D3
0x18005d5c2  mov     rax, [rdi+8]
0x18005d5c6  cmp     word ptr [rax], 5Ch ; '\'
0x18005d5ca  jnz     loc_18005D7A1
0x18005d5d0  mov     rbx, rdi
0x18005d5d3  mov     r14, [rbp+3Fh+String1]
0x18005d5d7  lea     rdx, [rbp+3Fh+MemoryDescriptorList]
0x18005d5db  mov     r8, r15; int
0x18005d5de  mov     [rsp+0C0h+var_78], rdx; __int64
0x18005d5e3  lea     rcx, [rsi+38h]
0x18005d5e7  mov     rdx, qword ptr [rbp+3Fh+arg_28]; int
0x18005d5eb  lea     rax, [rsi+30h]
0x18005d5ef  mov     [rsp+0C0h+var_80], rcx; __int64
0x18005d5f4  lea     r9, [rbp+3Fh+var_70]; int
0x18005d5f8  mov     [rsp+0C0h+var_88], rax; __int64
0x18005d5fd  mov     rcx, rbx; int
0x18005d600  lea     rax, [rbp+3Fh+arg_8]
0x18005d604  mov     [rsp+0C0h+var_90], rax; __int64
0x18005d609  lea     rax, [rbp+3Fh+Handle]
0x18005d60d  mov     [rsp+0C0h+var_98], r13; BaseAddress
0x18005d612  mov     [rsp+0C0h+var_A0], rax; __int64
0x18005d617  call    CipMapAndSizeDataFileWithMDL
0x18005d61c  mov     ebx, eax
0x18005d61e  cmp     eax, 0C0000034h
0x18005d623  jnz     loc_18005D890
0x18005d629  test    r15, r15
0x18005d62c  jnz     loc_18005D975
0x18005d632  mov     r8, [rdi+8]
0x18005d636  cmp     word ptr [r8], 5Ch ; '\'
0x18005d63b  jz      loc_18005D975
0x18005d641  test    r14, r14
0x18005d644  jz      short loc_18005D66C
0x18005d646  lea     rdx, stru_18002EFE0; String2
0x18005d64d  cmp     r14, rdx
0x18005d650  jz      short loc_18005D66C
0x18005d652  mov     r8b, 1; CaseInSensitive
0x18005d655  mov     rcx, r14; String1
0x18005d658  call    cs:__imp_RtlEqualUnicodeString
0x18005d65f  nop     dword ptr [rax+rax+00h]
0x18005d664  test    al, al
0x18005d666  jz      loc_18005D975
0x18005d66c  xor     edx, edx
0x18005d66e  lea     rcx, g_CatalogStoreListLock
0x18005d675  call    cs:__imp_ExAcquirePushLockSharedEx
0x18005d67c  nop     dword ptr [rax+rax+00h]
0x18005d681  mov     r14, cs:qword_180049780
0x18005d688  lea     rax, qword_180049780
0x18005d68f  cmp     r14, rax
0x18005d692  jz      loc_18005D87B
0x18005d698  mov     eax, [r14-18h]
0x18005d69c  test    al, 5
0x18005d69e  jnz     loc_18005D854
0x18005d6a4  mov     rcx, [rbp+3Fh+P.Buffer]; P
0x18005d6a8  mov     edx, 72634943h; Tag
0x18005d6ad  call    cs:__imp_ExFreePoolWithTag
0x18005d6b4  nop     dword ptr [rax+rax+00h]
0x18005d6b9  movzx   ecx, word ptr [rdi]
0x18005d6bc  mov     r8d, 72634943h
0x18005d6c2  add     cx, 4
0x18005d6c6  add     cx, [r14-10h]
0x18005d6cb  movzx   r15d, cx
0x18005d6cf  mov     ecx, 102h
0x18005d6d4  mov     edx, r15d
0x18005d6d7  call    cs:__imp_ExAllocatePool2
0x18005d6de  nop     dword ptr [rax+rax+00h]
0x18005d6e3  mov     [rbp+3Fh+P.Buffer], rax
0x18005d6e7  test    rax, rax
0x18005d6ea  jz      loc_18005D85C
0x18005d6f0  lea     rdx, [r14-10h]; SourceString
0x18005d6f4  mov     [rbp+3Fh+P.MaximumLength], r15w
0x18005d6f9  lea     rcx, [rbp+3Fh+P]; DestinationString
0x18005d6fd  call    cs:__imp_RtlCopyUnicodeString
0x18005d704  nop     dword ptr [rax+rax+00h]
0x18005d709  movzx   ecx, [rbp+3Fh+P.Length]
0x18005d70d  mov     rax, [rbp+3Fh+P.Buffer]
0x18005d711  shr     rcx, 1
0x18005d714  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18005d71a  jz      short loc_18005D733
0x18005d71c  lea     rdx, Source; Source
0x18005d723  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d727  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d72e  nop     dword ptr [rax+rax+00h]
0x18005d733  mov     rdx, rdi; Source
0x18005d736  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d73a  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d741  nop     dword ptr [rax+rax+00h]
0x18005d746  mov     rdx, qword ptr [rbp+3Fh+arg_28]; int
0x18005d74a  lea     rax, [rbp+3Fh+MemoryDescriptorList]
0x18005d74e  mov     [rsp+0C0h+var_78], rax; __int64
0x18005d753  lea     r9, [rbp+3Fh+var_70]; int
0x18005d757  lea     rax, [rsi+38h]
0x18005d75b  xor     r8d, r8d; int
0x18005d75e  mov     [rsp+0C0h+var_80], rax; __int64
0x18005d763  lea     rcx, [rbp+3Fh+P]; int
0x18005d767  lea     rax, [rsi+30h]
0x18005d76b  mov     [rsp+0C0h+var_88], rax; __int64
0x18005d770  lea     rax, [rbp+3Fh+arg_8]
0x18005d774  mov     [rsp+0C0h+var_90], rax; __int64
0x18005d779  lea     rax, [rbp+3Fh+Handle]
0x18005d77d  mov     [rsp+0C0h+var_98], r13; BaseAddress
0x18005d782  mov     [rsp+0C0h+var_A0], rax; __int64
0x18005d787  call    CipMapAndSizeDataFileWithMDL
0x18005d78c  mov     ebx, eax
0x18005d78e  cmp     eax, 0C000003Ah
0x18005d793  jnz     loc_18005D84D
0x18005d799  lea     ebx, [rax-6]
0x18005d79c  jmp     loc_18005D854
0x18005d7a1  mov     rax, [rbp+3Fh+String1]
0x18005d7a5  lea     r14, stru_18002EFE0
0x18005d7ac  test    rax, rax
0x18005d7af  mov     r8d, 72634943h
0x18005d7b5  cmovnz  r14, rax
0x18005d7b9  movzx   eax, word ptr [rdi]
0x18005d7bc  add     ax, 4
0x18005d7c0  movzx   ecx, word ptr [r14]
0x18005d7c4  add     cx, ax
0x18005d7c7  movzx   ebx, cx
0x18005d7ca  mov     ecx, 102h
0x18005d7cf  mov     edx, ebx
0x18005d7d1  call    cs:__imp_ExAllocatePool2
0x18005d7d8  nop     dword ptr [rax+rax+00h]
0x18005d7dd  mov     [rbp+3Fh+P.Buffer], rax
0x18005d7e1  test    rax, rax
0x18005d7e4  jnz     short loc_18005D7F0
0x18005d7e6  mov     ebx, 0C0000017h
0x18005d7eb  jmp     loc_18005D9C6
0x18005d7f0  mov     rdx, r14; SourceString
0x18005d7f3  mov     [rbp+3Fh+P.MaximumLength], bx
0x18005d7f7  lea     rcx, [rbp+3Fh+P]; DestinationString
0x18005d7fb  call    cs:__imp_RtlCopyUnicodeString
0x18005d802  nop     dword ptr [rax+rax+00h]
0x18005d807  movzx   ecx, [rbp+3Fh+P.Length]
0x18005d80b  mov     rax, [rbp+3Fh+P.Buffer]
0x18005d80f  shr     rcx, 1
0x18005d812  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18005d818  jz      short loc_18005D831
0x18005d81a  lea     rdx, Source; Source
0x18005d821  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d825  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d82c  nop     dword ptr [rax+rax+00h]
0x18005d831  mov     rdx, rdi; Source
0x18005d834  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d838  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d83f  nop     dword ptr [rax+rax+00h]
0x18005d844  lea     rbx, [rbp+3Fh+P]
0x18005d848  jmp     loc_18005D5D7
0x18005d84d  cmp     eax, 0C0000034h
0x18005d852  jnz     short loc_18005D87B
0x18005d854  mov     r14, [r14]
0x18005d857  jmp     loc_18005D688
0x18005d85c  xor     edx, edx
0x18005d85e  lea     rcx, g_CatalogStoreListLock
0x18005d865  mov     ebx, 0C0000017h
0x18005d86a  call    cs:__imp_ExReleasePushLockSharedEx
0x18005d871  nop     dword ptr [rax+rax+00h]
0x18005d876  jmp     loc_18005D975
0x18005d87b  xor     edx, edx
0x18005d87d  lea     rcx, g_CatalogStoreListLock
0x18005d884  call    cs:__imp_ExReleasePushLockSharedEx
0x18005d88b  nop     dword ptr [rax+rax+00h]
0x18005d890  test    ebx, ebx
0x18005d892  jns     short loc_18005D8AA
0x18005d894  cmp     ebx, 0C000011Eh
0x18005d89a  jnz     loc_18005D975
0x18005d8a0  mov     ebx, 0C0000428h
0x18005d8a5  jmp     loc_18005D975
0x18005d8aa  mov     rax, [rbp+3Fh+arg_38]
0x18005d8b1  test    rax, rax
0x18005d8b4  jz      short loc_18005D8BD
0x18005d8b6  mov     rax, [rax]
0x18005d8b9  mov     [rsi+30h], rax
0x18005d8bd  mov     rax, [rbp+3Fh+arg_40]
0x18005d8c4  test    rax, rax
0x18005d8c7  jz      short loc_18005D8D0
0x18005d8c9  mov     rax, [rax]
0x18005d8cc  mov     [rsi+38h], rax
0x18005d8d0  mov     r14d, dword ptr [rbp+3Fh+arg_8]
0x18005d8d4  test    r12b, 40h
0x18005d8d8  jz      short loc_18005D90E
0x18005d8da  mov     r8, [rbp+3Fh+BaseAddress]
0x18005d8de  mov     r9d, r14d
0x18005d8e1  mov     rdx, [rbp+3Fh+arg_18]
0x18005d8e5  mov     rcx, rsi
0x18005d8e8  call    I_TransferCatalogToHvci
0x18005d8ed  mov     ebx, eax
0x18005d8ef  test    eax, eax
0x18005d8f1  jns     short loc_18005D90E
0x18005d8f3  cmp     eax, 0C0000603h
0x18005d8f8  jnz     short loc_18005D975
0x18005d8fa  mov     rdx, [rbp+3Fh+BaseAddress]
0x18005d8fe  xor     r9d, r9d
0x18005d901  mov     r8d, r14d
0x18005d904  mov     rcx, rsi
0x18005d907  call    I_ParseCatalogAndMapHashes
0x18005d90c  jmp     short loc_18005D92F
0x18005d90e  test    r12b, 3Ch
0x18005d912  jz      short loc_18005D95A
0x18005d914  mov     rdx, [rbp+3Fh+BaseAddress]
0x18005d918  mov     r9d, r12d
0x18005d91b  mov     r8d, r14d
0x18005d91e  mov     rcx, rsi
0x18005d921  call    I_ParseCatalogAndMapHashes
0x18005d926  mov     ebx, eax
0x18005d928  cmp     eax, 0C0000603h
0x18005d92d  jnz     short loc_18005D956
0x18005d92f  mov     rax, [rbp+3Fh+arg_0]
0x18005d933  test    rax, rax
0x18005d936  jz      short loc_18005D975
0x18005d938  lea     r8, [rsi+0A8h]
0x18005d93f  mov     byte ptr [rsp+0C0h+var_A0], 0
0x18005d944  lea     rdx, [rsi+48h]
0x18005d948  mov     r9d, 0C0000603h
0x18005d94e  mov     rcx, rax
0x18005d951  call    CiInstrumentDriverSignatureRetry
0x18005d956  test    ebx, ebx
0x18005d958  js      short loc_18005D975
0x18005d95a  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x18005d95f  test    eax, eax
0x18005d961  jz      short loc_18005D975
0x18005d963  mov     rcx, [rbp+3Fh+var_70]; Handle
0x18005d967  lea     rdx, [rsi+110h]
0x18005d96e  call    KappxCheckTrustLabelAce
0x18005d973  mov     ebx, eax
0x18005d975  mov     r14, [rbp+3Fh+MemoryDescriptorList]
0x18005d979  test    r14, r14
0x18005d97c  jz      short loc_18005D99C
0x18005d97e  mov     rcx, r14; MemoryDescriptorList
0x18005d981  call    cs:__imp_MmUnlockPages
0x18005d988  nop     dword ptr [rax+rax+00h]
0x18005d98d  mov     rcx, r14; Mdl
0x18005d990  call    cs:__imp_IoFreeMdl
0x18005d997  nop     dword ptr [rax+rax+00h]
0x18005d99c  mov     rcx, [rbp+3Fh+Handle]; Handle
0x18005d9a0  test    rcx, rcx
0x18005d9a3  jz      short loc_18005D9B1
0x18005d9a5  call    cs:__imp_ZwClose
0x18005d9ac  nop     dword ptr [rax+rax+00h]
0x18005d9b1  mov     rcx, [rbp+3Fh+var_70]; Handle
0x18005d9b5  test    rcx, rcx
0x18005d9b8  jz      short loc_18005D9C6
0x18005d9ba  call    cs:__imp_ZwClose
0x18005d9c1  nop     dword ptr [rax+rax+00h]
0x18005d9c6  mov     rdx, [rbp+3Fh+BaseAddress]; BaseAddress
0x18005d9ca  test    rdx, rdx
0x18005d9cd  jz      short loc_18005D9DF
0x18005d9cf  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005d9d3  call    cs:__imp_ZwUnmapViewOfSection
0x18005d9da  nop     dword ptr [rax+rax+00h]
0x18005d9df  test    r12d, r12d
0x18005d9e2  jz      short loc_18005DA1F
0x18005d9e4  mov     rcx, rdi
0x18005d9e7  test    ebx, ebx
0x18005d9e9  js      short loc_18005D9F9
0x18005d9eb  lea     rdx, CiCatalogLoadComplete
0x18005d9f2  call    CiLogFileEvent
0x18005d9f7  jmp     short loc_18005DA2B
0x18005d9f9  cmp     ebx, 0C0000603h
0x18005d9ff  jnz     short loc_18005DA0F
0x18005da01  lea     rdx, CiRevokedCatalog
0x18005da08  call    CiLogFileEvent
0x18005da0d  jmp     short loc_18005DA23
0x18005da0f  lea     r8, CiInvalidCatalog
0x18005da16  mov     edx, ebx
0x18005da18  call    CiLogFileEventWithStatus
0x18005da1d  jmp     short loc_18005DA23
0x18005da1f  test    ebx, ebx
  ... truncated ...
```
