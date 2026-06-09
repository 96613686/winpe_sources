# I_MapCatalog

- ea: `0x18005d4f0`
- end: `0x18005d9fc`
- name: `I_MapCatalog`
- size: `1292`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING String1, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180061d44`
- `0x18008c1a0`

## callees

- `0x1800100a4`
- `0x180059e0c`
- `0x18005d4f0`
- `0x18005da04`
- `0x180065e10`
- `0x18006d02c`
- `0x18008ceb8`
- `0x180090588`
- `0x180098364`
- `0x1800e2fbc`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d69d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d79b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d69d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d79b`
- `ntoskrnl!ExAllocatePool2` at `0x18005d677`
- `ntoskrnl!ExAllocatePool2` at `0x18005d771`
- `ntoskrnl!ExAllocatePool2` at `0x18005d677`
- `ntoskrnl!ExAllocatePool2` at `0x18005d771`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d80a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d824`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d80a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d824`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18005d615`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18005d615`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d64d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d9d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d64d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d9d9`
- `ntoskrnl!ZwClose` at `0x18005d945`
- `ntoskrnl!ZwClose` at `0x18005d95a`
- `ntoskrnl!ZwClose` at `0x18005d945`
- `ntoskrnl!ZwClose` at `0x18005d95a`
- `ntoskrnl!MmUnlockPages` at `0x18005d921`
- `ntoskrnl!MmUnlockPages` at `0x18005d921`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005d973`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005d973`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d6c7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d6da`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d7c5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d7d8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d6c7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d6da`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d7c5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d7d8`
- `ntoskrnl!IoFreeMdl` at `0x18005d930`
- `ntoskrnl!IoFreeMdl` at `0x18005d930`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005d5f8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005d5f8`

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
  v15 = &stru_18002E470;
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
    if ( v14 || *v9->Buffer == 92 || v15 && v15 != &stru_18002E470 && !RtlEqualUnicodeString(v15, &stru_18002E470, 1u) )
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
0x18005d4f0  mov     [rsp-8+arg_18], r9
0x18005d4f5  mov     [rsp-8+arg_0], rcx
0x18005d4fa  push    rbp
0x18005d4fb  push    rbx
0x18005d4fc  push    rsi
0x18005d4fd  push    rdi
0x18005d4fe  push    r12
0x18005d500  push    r13
0x18005d502  push    r14
0x18005d504  push    r15
0x18005d506  lea     rbp, [rsp-7]
0x18005d50b  sub     rsp, 88h
0x18005d512  xor     ecx, ecx
0x18005d514  lea     rdi, [r8+0C8h]
0x18005d51b  mov     [rbp+3Fh+var_70], rcx
0x18005d51f  xorps   xmm0, xmm0
0x18005d522  mov     [rbp+3Fh+Handle], rcx
0x18005d526  mov     rsi, r8
0x18005d529  mov     [rbp+3Fh+BaseAddress], rcx
0x18005d52d  mov     r12d, edx
0x18005d530  mov     dword ptr [rbp+3Fh+arg_8], ecx
0x18005d533  mov     ebx, ecx
0x18005d535  mov     [rbp+3Fh+MemoryDescriptorList], rcx
0x18005d539  movups  xmmword ptr [rbp+3Fh+P.Length], xmm0
0x18005d53d  test    edx, edx
0x18005d53f  jz      short loc_18005D556
0x18005d541  lea     rdx, CiCatalogLoadStart
0x18005d548  mov     rcx, rdi
0x18005d54b  lea     r13, [rbp+3Fh+BaseAddress]
0x18005d54f  call    CiLogFileEvent
0x18005d554  jmp     short loc_18005D559
0x18005d556  mov     r13, rcx
0x18005d559  mov     r15, [rbp+3Fh+arg_30]
0x18005d55d  test    r15, r15
0x18005d560  jnz     short loc_18005D573
0x18005d562  mov     rax, [rdi+8]
0x18005d566  cmp     word ptr [rax], 5Ch ; '\'
0x18005d56a  jnz     loc_18005D741
0x18005d570  mov     rbx, rdi
0x18005d573  mov     r14, [rbp+3Fh+String1]
0x18005d577  lea     rdx, [rbp+3Fh+MemoryDescriptorList]
0x18005d57b  mov     r8, r15; int
0x18005d57e  mov     [rsp+0C0h+var_78], rdx; __int64
0x18005d583  lea     rcx, [rsi+38h]
0x18005d587  mov     rdx, qword ptr [rbp+3Fh+arg_28]; int
0x18005d58b  lea     rax, [rsi+30h]
0x18005d58f  mov     [rsp+0C0h+var_80], rcx; __int64
0x18005d594  lea     r9, [rbp+3Fh+var_70]; int
0x18005d598  mov     [rsp+0C0h+var_88], rax; __int64
0x18005d59d  mov     rcx, rbx; int
0x18005d5a0  lea     rax, [rbp+3Fh+arg_8]
0x18005d5a4  mov     [rsp+0C0h+var_90], rax; __int64
0x18005d5a9  lea     rax, [rbp+3Fh+Handle]
0x18005d5ad  mov     [rsp+0C0h+var_98], r13; BaseAddress
0x18005d5b2  mov     [rsp+0C0h+var_A0], rax; __int64
0x18005d5b7  call    CipMapAndSizeDataFileWithMDL
0x18005d5bc  mov     ebx, eax
0x18005d5be  cmp     eax, 0C0000034h
0x18005d5c3  jnz     loc_18005D830
0x18005d5c9  test    r15, r15
0x18005d5cc  jnz     loc_18005D915
0x18005d5d2  mov     r8, [rdi+8]
0x18005d5d6  cmp     word ptr [r8], 5Ch ; '\'
0x18005d5db  jz      loc_18005D915
0x18005d5e1  test    r14, r14
0x18005d5e4  jz      short loc_18005D60C
0x18005d5e6  lea     rdx, stru_18002E470; String2
0x18005d5ed  cmp     r14, rdx
0x18005d5f0  jz      short loc_18005D60C
0x18005d5f2  mov     r8b, 1; CaseInSensitive
0x18005d5f5  mov     rcx, r14; String1
0x18005d5f8  call    cs:__imp_RtlEqualUnicodeString
0x18005d5ff  nop     dword ptr [rax+rax+00h]
0x18005d604  test    al, al
0x18005d606  jz      loc_18005D915
0x18005d60c  xor     edx, edx
0x18005d60e  lea     rcx, g_CatalogStoreListLock
0x18005d615  call    cs:__imp_ExAcquirePushLockSharedEx
0x18005d61c  nop     dword ptr [rax+rax+00h]
0x18005d621  mov     r14, cs:qword_180049780
0x18005d628  lea     rax, qword_180049780
0x18005d62f  cmp     r14, rax
0x18005d632  jz      loc_18005D81B
0x18005d638  mov     eax, [r14-18h]
0x18005d63c  test    al, 5
0x18005d63e  jnz     loc_18005D7F4
0x18005d644  mov     rcx, [rbp+3Fh+P.Buffer]; P
0x18005d648  mov     edx, 72634943h; Tag
0x18005d64d  call    cs:__imp_ExFreePoolWithTag
0x18005d654  nop     dword ptr [rax+rax+00h]
0x18005d659  movzx   ecx, word ptr [rdi]
0x18005d65c  mov     r8d, 72634943h
0x18005d662  add     cx, 4
0x18005d666  add     cx, [r14-10h]
0x18005d66b  movzx   r15d, cx
0x18005d66f  mov     ecx, 102h
0x18005d674  mov     edx, r15d
0x18005d677  call    cs:__imp_ExAllocatePool2
0x18005d67e  nop     dword ptr [rax+rax+00h]
0x18005d683  mov     [rbp+3Fh+P.Buffer], rax
0x18005d687  test    rax, rax
0x18005d68a  jz      loc_18005D7FC
0x18005d690  lea     rdx, [r14-10h]; SourceString
0x18005d694  mov     [rbp+3Fh+P.MaximumLength], r15w
0x18005d699  lea     rcx, [rbp+3Fh+P]; DestinationString
0x18005d69d  call    cs:__imp_RtlCopyUnicodeString
0x18005d6a4  nop     dword ptr [rax+rax+00h]
0x18005d6a9  movzx   ecx, [rbp+3Fh+P.Length]
0x18005d6ad  mov     rax, [rbp+3Fh+P.Buffer]
0x18005d6b1  shr     rcx, 1
0x18005d6b4  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18005d6ba  jz      short loc_18005D6D3
0x18005d6bc  lea     rdx, Source; Source
0x18005d6c3  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d6c7  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d6ce  nop     dword ptr [rax+rax+00h]
0x18005d6d3  mov     rdx, rdi; Source
0x18005d6d6  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d6da  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d6e1  nop     dword ptr [rax+rax+00h]
0x18005d6e6  mov     rdx, qword ptr [rbp+3Fh+arg_28]; int
0x18005d6ea  lea     rax, [rbp+3Fh+MemoryDescriptorList]
0x18005d6ee  mov     [rsp+0C0h+var_78], rax; __int64
0x18005d6f3  lea     r9, [rbp+3Fh+var_70]; int
0x18005d6f7  lea     rax, [rsi+38h]
0x18005d6fb  xor     r8d, r8d; int
0x18005d6fe  mov     [rsp+0C0h+var_80], rax; __int64
0x18005d703  lea     rcx, [rbp+3Fh+P]; int
0x18005d707  lea     rax, [rsi+30h]
0x18005d70b  mov     [rsp+0C0h+var_88], rax; __int64
0x18005d710  lea     rax, [rbp+3Fh+arg_8]
0x18005d714  mov     [rsp+0C0h+var_90], rax; __int64
0x18005d719  lea     rax, [rbp+3Fh+Handle]
0x18005d71d  mov     [rsp+0C0h+var_98], r13; BaseAddress
0x18005d722  mov     [rsp+0C0h+var_A0], rax; __int64
0x18005d727  call    CipMapAndSizeDataFileWithMDL
0x18005d72c  mov     ebx, eax
0x18005d72e  cmp     eax, 0C000003Ah
0x18005d733  jnz     loc_18005D7ED
0x18005d739  lea     ebx, [rax-6]
0x18005d73c  jmp     loc_18005D7F4
0x18005d741  mov     rax, [rbp+3Fh+String1]
0x18005d745  lea     r14, stru_18002E470
0x18005d74c  test    rax, rax
0x18005d74f  mov     r8d, 72634943h
0x18005d755  cmovnz  r14, rax
0x18005d759  movzx   eax, word ptr [rdi]
0x18005d75c  add     ax, 4
0x18005d760  movzx   ecx, word ptr [r14]
0x18005d764  add     cx, ax
0x18005d767  movzx   ebx, cx
0x18005d76a  mov     ecx, 102h
0x18005d76f  mov     edx, ebx
0x18005d771  call    cs:__imp_ExAllocatePool2
0x18005d778  nop     dword ptr [rax+rax+00h]
0x18005d77d  mov     [rbp+3Fh+P.Buffer], rax
0x18005d781  test    rax, rax
0x18005d784  jnz     short loc_18005D790
0x18005d786  mov     ebx, 0C0000017h
0x18005d78b  jmp     loc_18005D966
0x18005d790  mov     rdx, r14; SourceString
0x18005d793  mov     [rbp+3Fh+P.MaximumLength], bx
0x18005d797  lea     rcx, [rbp+3Fh+P]; DestinationString
0x18005d79b  call    cs:__imp_RtlCopyUnicodeString
0x18005d7a2  nop     dword ptr [rax+rax+00h]
0x18005d7a7  movzx   ecx, [rbp+3Fh+P.Length]
0x18005d7ab  mov     rax, [rbp+3Fh+P.Buffer]
0x18005d7af  shr     rcx, 1
0x18005d7b2  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18005d7b8  jz      short loc_18005D7D1
0x18005d7ba  lea     rdx, Source; Source
0x18005d7c1  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d7c5  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d7cc  nop     dword ptr [rax+rax+00h]
0x18005d7d1  mov     rdx, rdi; Source
0x18005d7d4  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d7d8  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d7df  nop     dword ptr [rax+rax+00h]
0x18005d7e4  lea     rbx, [rbp+3Fh+P]
0x18005d7e8  jmp     loc_18005D577
0x18005d7ed  cmp     eax, 0C0000034h
0x18005d7f2  jnz     short loc_18005D81B
0x18005d7f4  mov     r14, [r14]
0x18005d7f7  jmp     loc_18005D628
0x18005d7fc  xor     edx, edx
0x18005d7fe  lea     rcx, g_CatalogStoreListLock
0x18005d805  mov     ebx, 0C0000017h
0x18005d80a  call    cs:__imp_ExReleasePushLockSharedEx
0x18005d811  nop     dword ptr [rax+rax+00h]
0x18005d816  jmp     loc_18005D915
0x18005d81b  xor     edx, edx
0x18005d81d  lea     rcx, g_CatalogStoreListLock
0x18005d824  call    cs:__imp_ExReleasePushLockSharedEx
0x18005d82b  nop     dword ptr [rax+rax+00h]
0x18005d830  test    ebx, ebx
0x18005d832  jns     short loc_18005D84A
0x18005d834  cmp     ebx, 0C000011Eh
0x18005d83a  jnz     loc_18005D915
0x18005d840  mov     ebx, 0C0000428h
0x18005d845  jmp     loc_18005D915
0x18005d84a  mov     rax, [rbp+3Fh+arg_38]
0x18005d851  test    rax, rax
0x18005d854  jz      short loc_18005D85D
0x18005d856  mov     rax, [rax]
0x18005d859  mov     [rsi+30h], rax
0x18005d85d  mov     rax, [rbp+3Fh+arg_40]
0x18005d864  test    rax, rax
0x18005d867  jz      short loc_18005D870
0x18005d869  mov     rax, [rax]
0x18005d86c  mov     [rsi+38h], rax
0x18005d870  mov     r14d, dword ptr [rbp+3Fh+arg_8]
0x18005d874  test    r12b, 40h
0x18005d878  jz      short loc_18005D8AE
0x18005d87a  mov     r8, [rbp+3Fh+BaseAddress]
0x18005d87e  mov     r9d, r14d
0x18005d881  mov     rdx, [rbp+3Fh+arg_18]
0x18005d885  mov     rcx, rsi
0x18005d888  call    I_TransferCatalogToHvci
0x18005d88d  mov     ebx, eax
0x18005d88f  test    eax, eax
0x18005d891  jns     short loc_18005D8AE
0x18005d893  cmp     eax, 0C0000603h
0x18005d898  jnz     short loc_18005D915
0x18005d89a  mov     rdx, [rbp+3Fh+BaseAddress]
0x18005d89e  xor     r9d, r9d
0x18005d8a1  mov     r8d, r14d
0x18005d8a4  mov     rcx, rsi
0x18005d8a7  call    I_ParseCatalogAndMapHashes
0x18005d8ac  jmp     short loc_18005D8CF
0x18005d8ae  test    r12b, 3Ch
0x18005d8b2  jz      short loc_18005D8FA
0x18005d8b4  mov     rdx, [rbp+3Fh+BaseAddress]
0x18005d8b8  mov     r9d, r12d
0x18005d8bb  mov     r8d, r14d
0x18005d8be  mov     rcx, rsi
0x18005d8c1  call    I_ParseCatalogAndMapHashes
0x18005d8c6  mov     ebx, eax
0x18005d8c8  cmp     eax, 0C0000603h
0x18005d8cd  jnz     short loc_18005D8F6
0x18005d8cf  mov     rax, [rbp+3Fh+arg_0]
0x18005d8d3  test    rax, rax
0x18005d8d6  jz      short loc_18005D915
0x18005d8d8  lea     r8, [rsi+0A8h]
0x18005d8df  mov     byte ptr [rsp+0C0h+var_A0], 0
0x18005d8e4  lea     rdx, [rsi+48h]
0x18005d8e8  mov     r9d, 0C0000603h
0x18005d8ee  mov     rcx, rax
0x18005d8f1  call    CiInstrumentDriverSignatureRetry
0x18005d8f6  test    ebx, ebx
0x18005d8f8  js      short loc_18005D915
0x18005d8fa  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x18005d8ff  test    eax, eax
0x18005d901  jz      short loc_18005D915
0x18005d903  mov     rcx, [rbp+3Fh+var_70]; Handle
0x18005d907  lea     rdx, [rsi+110h]
0x18005d90e  call    KappxCheckTrustLabelAce
0x18005d913  mov     ebx, eax
0x18005d915  mov     r14, [rbp+3Fh+MemoryDescriptorList]
0x18005d919  test    r14, r14
0x18005d91c  jz      short loc_18005D93C
0x18005d91e  mov     rcx, r14; MemoryDescriptorList
0x18005d921  call    cs:__imp_MmUnlockPages
0x18005d928  nop     dword ptr [rax+rax+00h]
0x18005d92d  mov     rcx, r14; Mdl
0x18005d930  call    cs:__imp_IoFreeMdl
0x18005d937  nop     dword ptr [rax+rax+00h]
0x18005d93c  mov     rcx, [rbp+3Fh+Handle]; Handle
0x18005d940  test    rcx, rcx
0x18005d943  jz      short loc_18005D951
0x18005d945  call    cs:__imp_ZwClose
0x18005d94c  nop     dword ptr [rax+rax+00h]
0x18005d951  mov     rcx, [rbp+3Fh+var_70]; Handle
0x18005d955  test    rcx, rcx
0x18005d958  jz      short loc_18005D966
0x18005d95a  call    cs:__imp_ZwClose
0x18005d961  nop     dword ptr [rax+rax+00h]
0x18005d966  mov     rdx, [rbp+3Fh+BaseAddress]; BaseAddress
0x18005d96a  test    rdx, rdx
0x18005d96d  jz      short loc_18005D97F
0x18005d96f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005d973  call    cs:__imp_ZwUnmapViewOfSection
0x18005d97a  nop     dword ptr [rax+rax+00h]
0x18005d97f  test    r12d, r12d
0x18005d982  jz      short loc_18005D9BF
0x18005d984  mov     rcx, rdi
0x18005d987  test    ebx, ebx
0x18005d989  js      short loc_18005D999
0x18005d98b  lea     rdx, CiCatalogLoadComplete
0x18005d992  call    CiLogFileEvent
0x18005d997  jmp     short loc_18005D9CB
0x18005d999  cmp     ebx, 0C0000603h
0x18005d99f  jnz     short loc_18005D9AF
0x18005d9a1  lea     rdx, CiRevokedCatalog
0x18005d9a8  call    CiLogFileEvent
0x18005d9ad  jmp     short loc_18005D9C3
0x18005d9af  lea     r8, CiInvalidCatalog
0x18005d9b6  mov     edx, ebx
0x18005d9b8  call    CiLogFileEventWithStatus
0x18005d9bd  jmp     short loc_18005D9C3
0x18005d9bf  test    ebx, ebx
  ... truncated ...
```
