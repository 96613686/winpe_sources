# I_MapCatalog

- ea: `0x18005cee8`
- end: `0x18005d3f4`
- name: `I_MapCatalog`
- size: `1292`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING String1, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18006139c`
- `0x1800a1968`

## callees

- `0x180010128`
- `0x1800591cc`
- `0x18005cee8`
- `0x18005d3fc`
- `0x1800653ac`
- `0x18006bf78`
- `0x1800913d4`
- `0x180095730`
- `0x18009dccc`
- `0x1800e1ffc`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d095`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d193`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d095`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005d193`
- `ntoskrnl!ExAllocatePool2` at `0x18005d06f`
- `ntoskrnl!ExAllocatePool2` at `0x18005d169`
- `ntoskrnl!ExAllocatePool2` at `0x18005d06f`
- `ntoskrnl!ExAllocatePool2` at `0x18005d169`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d202`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d21c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d202`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005d21c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18005d00d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18005d00d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d045`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d3d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d045`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d3d1`
- `ntoskrnl!ZwClose` at `0x18005d33d`
- `ntoskrnl!ZwClose` at `0x18005d352`
- `ntoskrnl!ZwClose` at `0x18005d33d`
- `ntoskrnl!ZwClose` at `0x18005d352`
- `ntoskrnl!MmUnlockPages` at `0x18005d319`
- `ntoskrnl!MmUnlockPages` at `0x18005d319`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005d36b`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x18005d36b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d0bf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d0d2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d1bd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d1d0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d0bf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d0d2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d1bd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005d1d0`
- `ntoskrnl!IoFreeMdl` at `0x18005d328`
- `ntoskrnl!IoFreeMdl` at `0x18005d328`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005cff0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005cff0`

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
    for ( i = (__int64 *)qword_180048780; i != &qword_180048780; i = (__int64 *)*i )
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
0x18005cee8  mov     [rsp-8+arg_18], r9
0x18005ceed  mov     [rsp-8+arg_0], rcx
0x18005cef2  push    rbp
0x18005cef3  push    rbx
0x18005cef4  push    rsi
0x18005cef5  push    rdi
0x18005cef6  push    r12
0x18005cef8  push    r13
0x18005cefa  push    r14
0x18005cefc  push    r15
0x18005cefe  lea     rbp, [rsp-7]
0x18005cf03  sub     rsp, 88h
0x18005cf0a  xor     ecx, ecx
0x18005cf0c  lea     rdi, [r8+0C8h]
0x18005cf13  mov     [rbp+3Fh+var_70], rcx
0x18005cf17  xorps   xmm0, xmm0
0x18005cf1a  mov     [rbp+3Fh+Handle], rcx
0x18005cf1e  mov     rsi, r8
0x18005cf21  mov     [rbp+3Fh+BaseAddress], rcx
0x18005cf25  mov     r12d, edx
0x18005cf28  mov     dword ptr [rbp+3Fh+arg_8], ecx
0x18005cf2b  mov     ebx, ecx
0x18005cf2d  mov     [rbp+3Fh+MemoryDescriptorList], rcx
0x18005cf31  movups  xmmword ptr [rbp+3Fh+P.Length], xmm0
0x18005cf35  test    edx, edx
0x18005cf37  jz      short loc_18005CF4E
0x18005cf39  lea     rdx, CiCatalogLoadStart
0x18005cf40  mov     rcx, rdi
0x18005cf43  lea     r13, [rbp+3Fh+BaseAddress]
0x18005cf47  call    CiLogFileEvent
0x18005cf4c  jmp     short loc_18005CF51
0x18005cf4e  mov     r13, rcx
0x18005cf51  mov     r15, [rbp+3Fh+arg_30]
0x18005cf55  test    r15, r15
0x18005cf58  jnz     short loc_18005CF6B
0x18005cf5a  mov     rax, [rdi+8]
0x18005cf5e  cmp     word ptr [rax], 5Ch ; '\'
0x18005cf62  jnz     loc_18005D139
0x18005cf68  mov     rbx, rdi
0x18005cf6b  mov     r14, [rbp+3Fh+String1]
0x18005cf6f  lea     rdx, [rbp+3Fh+MemoryDescriptorList]
0x18005cf73  mov     r8, r15; int
0x18005cf76  mov     [rsp+0C0h+var_78], rdx; __int64
0x18005cf7b  lea     rcx, [rsi+38h]
0x18005cf7f  mov     rdx, qword ptr [rbp+3Fh+arg_28]; int
0x18005cf83  lea     rax, [rsi+30h]
0x18005cf87  mov     [rsp+0C0h+var_80], rcx; __int64
0x18005cf8c  lea     r9, [rbp+3Fh+var_70]; int
0x18005cf90  mov     [rsp+0C0h+var_88], rax; __int64
0x18005cf95  mov     rcx, rbx; int
0x18005cf98  lea     rax, [rbp+3Fh+arg_8]
0x18005cf9c  mov     [rsp+0C0h+var_90], rax; __int64
0x18005cfa1  lea     rax, [rbp+3Fh+Handle]
0x18005cfa5  mov     [rsp+0C0h+var_98], r13; BaseAddress
0x18005cfaa  mov     [rsp+0C0h+var_A0], rax; __int64
0x18005cfaf  call    CipMapAndSizeDataFileWithMDL
0x18005cfb4  mov     ebx, eax
0x18005cfb6  cmp     eax, 0C0000034h
0x18005cfbb  jnz     loc_18005D228
0x18005cfc1  test    r15, r15
0x18005cfc4  jnz     loc_18005D30D
0x18005cfca  mov     r8, [rdi+8]
0x18005cfce  cmp     word ptr [r8], 5Ch ; '\'
0x18005cfd3  jz      loc_18005D30D
0x18005cfd9  test    r14, r14
0x18005cfdc  jz      short loc_18005D004
0x18005cfde  lea     rdx, stru_18002EFE0; String2
0x18005cfe5  cmp     r14, rdx
0x18005cfe8  jz      short loc_18005D004
0x18005cfea  mov     r8b, 1; CaseInSensitive
0x18005cfed  mov     rcx, r14; String1
0x18005cff0  call    cs:__imp_RtlEqualUnicodeString
0x18005cff7  nop     dword ptr [rax+rax+00h]
0x18005cffc  test    al, al
0x18005cffe  jz      loc_18005D30D
0x18005d004  xor     edx, edx
0x18005d006  lea     rcx, g_CatalogStoreListLock
0x18005d00d  call    cs:__imp_ExAcquirePushLockSharedEx
0x18005d014  nop     dword ptr [rax+rax+00h]
0x18005d019  mov     r14, cs:qword_180048780
0x18005d020  lea     rax, qword_180048780
0x18005d027  cmp     r14, rax
0x18005d02a  jz      loc_18005D213
0x18005d030  mov     eax, [r14-18h]
0x18005d034  test    al, 5
0x18005d036  jnz     loc_18005D1EC
0x18005d03c  mov     rcx, [rbp+3Fh+P.Buffer]; P
0x18005d040  mov     edx, 72634943h; Tag
0x18005d045  call    cs:__imp_ExFreePoolWithTag
0x18005d04c  nop     dword ptr [rax+rax+00h]
0x18005d051  movzx   ecx, word ptr [rdi]
0x18005d054  mov     r8d, 72634943h
0x18005d05a  add     cx, 4
0x18005d05e  add     cx, [r14-10h]
0x18005d063  movzx   r15d, cx
0x18005d067  mov     ecx, 102h
0x18005d06c  mov     edx, r15d
0x18005d06f  call    cs:__imp_ExAllocatePool2
0x18005d076  nop     dword ptr [rax+rax+00h]
0x18005d07b  mov     [rbp+3Fh+P.Buffer], rax
0x18005d07f  test    rax, rax
0x18005d082  jz      loc_18005D1F4
0x18005d088  lea     rdx, [r14-10h]; SourceString
0x18005d08c  mov     [rbp+3Fh+P.MaximumLength], r15w
0x18005d091  lea     rcx, [rbp+3Fh+P]; DestinationString
0x18005d095  call    cs:__imp_RtlCopyUnicodeString
0x18005d09c  nop     dword ptr [rax+rax+00h]
0x18005d0a1  movzx   ecx, [rbp+3Fh+P.Length]
0x18005d0a5  mov     rax, [rbp+3Fh+P.Buffer]
0x18005d0a9  shr     rcx, 1
0x18005d0ac  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18005d0b2  jz      short loc_18005D0CB
0x18005d0b4  lea     rdx, Source; Source
0x18005d0bb  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d0bf  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d0c6  nop     dword ptr [rax+rax+00h]
0x18005d0cb  mov     rdx, rdi; Source
0x18005d0ce  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d0d2  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d0d9  nop     dword ptr [rax+rax+00h]
0x18005d0de  mov     rdx, qword ptr [rbp+3Fh+arg_28]; int
0x18005d0e2  lea     rax, [rbp+3Fh+MemoryDescriptorList]
0x18005d0e6  mov     [rsp+0C0h+var_78], rax; __int64
0x18005d0eb  lea     r9, [rbp+3Fh+var_70]; int
0x18005d0ef  lea     rax, [rsi+38h]
0x18005d0f3  xor     r8d, r8d; int
0x18005d0f6  mov     [rsp+0C0h+var_80], rax; __int64
0x18005d0fb  lea     rcx, [rbp+3Fh+P]; int
0x18005d0ff  lea     rax, [rsi+30h]
0x18005d103  mov     [rsp+0C0h+var_88], rax; __int64
0x18005d108  lea     rax, [rbp+3Fh+arg_8]
0x18005d10c  mov     [rsp+0C0h+var_90], rax; __int64
0x18005d111  lea     rax, [rbp+3Fh+Handle]
0x18005d115  mov     [rsp+0C0h+var_98], r13; BaseAddress
0x18005d11a  mov     [rsp+0C0h+var_A0], rax; __int64
0x18005d11f  call    CipMapAndSizeDataFileWithMDL
0x18005d124  mov     ebx, eax
0x18005d126  cmp     eax, 0C000003Ah
0x18005d12b  jnz     loc_18005D1E5
0x18005d131  lea     ebx, [rax-6]
0x18005d134  jmp     loc_18005D1EC
0x18005d139  mov     rax, [rbp+3Fh+String1]
0x18005d13d  lea     r14, stru_18002EFE0
0x18005d144  test    rax, rax
0x18005d147  mov     r8d, 72634943h
0x18005d14d  cmovnz  r14, rax
0x18005d151  movzx   eax, word ptr [rdi]
0x18005d154  add     ax, 4
0x18005d158  movzx   ecx, word ptr [r14]
0x18005d15c  add     cx, ax
0x18005d15f  movzx   ebx, cx
0x18005d162  mov     ecx, 102h
0x18005d167  mov     edx, ebx
0x18005d169  call    cs:__imp_ExAllocatePool2
0x18005d170  nop     dword ptr [rax+rax+00h]
0x18005d175  mov     [rbp+3Fh+P.Buffer], rax
0x18005d179  test    rax, rax
0x18005d17c  jnz     short loc_18005D188
0x18005d17e  mov     ebx, 0C0000017h
0x18005d183  jmp     loc_18005D35E
0x18005d188  mov     rdx, r14; SourceString
0x18005d18b  mov     [rbp+3Fh+P.MaximumLength], bx
0x18005d18f  lea     rcx, [rbp+3Fh+P]; DestinationString
0x18005d193  call    cs:__imp_RtlCopyUnicodeString
0x18005d19a  nop     dword ptr [rax+rax+00h]
0x18005d19f  movzx   ecx, [rbp+3Fh+P.Length]
0x18005d1a3  mov     rax, [rbp+3Fh+P.Buffer]
0x18005d1a7  shr     rcx, 1
0x18005d1aa  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18005d1b0  jz      short loc_18005D1C9
0x18005d1b2  lea     rdx, Source; Source
0x18005d1b9  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d1bd  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d1c4  nop     dword ptr [rax+rax+00h]
0x18005d1c9  mov     rdx, rdi; Source
0x18005d1cc  lea     rcx, [rbp+3Fh+P]; Destination
0x18005d1d0  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d1d7  nop     dword ptr [rax+rax+00h]
0x18005d1dc  lea     rbx, [rbp+3Fh+P]
0x18005d1e0  jmp     loc_18005CF6F
0x18005d1e5  cmp     eax, 0C0000034h
0x18005d1ea  jnz     short loc_18005D213
0x18005d1ec  mov     r14, [r14]
0x18005d1ef  jmp     loc_18005D020
0x18005d1f4  xor     edx, edx
0x18005d1f6  lea     rcx, g_CatalogStoreListLock
0x18005d1fd  mov     ebx, 0C0000017h
0x18005d202  call    cs:__imp_ExReleasePushLockSharedEx
0x18005d209  nop     dword ptr [rax+rax+00h]
0x18005d20e  jmp     loc_18005D30D
0x18005d213  xor     edx, edx
0x18005d215  lea     rcx, g_CatalogStoreListLock
0x18005d21c  call    cs:__imp_ExReleasePushLockSharedEx
0x18005d223  nop     dword ptr [rax+rax+00h]
0x18005d228  test    ebx, ebx
0x18005d22a  jns     short loc_18005D242
0x18005d22c  cmp     ebx, 0C000011Eh
0x18005d232  jnz     loc_18005D30D
0x18005d238  mov     ebx, 0C0000428h
0x18005d23d  jmp     loc_18005D30D
0x18005d242  mov     rax, [rbp+3Fh+arg_38]
0x18005d249  test    rax, rax
0x18005d24c  jz      short loc_18005D255
0x18005d24e  mov     rax, [rax]
0x18005d251  mov     [rsi+30h], rax
0x18005d255  mov     rax, [rbp+3Fh+arg_40]
0x18005d25c  test    rax, rax
0x18005d25f  jz      short loc_18005D268
0x18005d261  mov     rax, [rax]
0x18005d264  mov     [rsi+38h], rax
0x18005d268  mov     r14d, dword ptr [rbp+3Fh+arg_8]
0x18005d26c  test    r12b, 40h
0x18005d270  jz      short loc_18005D2A6
0x18005d272  mov     r8, [rbp+3Fh+BaseAddress]
0x18005d276  mov     r9d, r14d
0x18005d279  mov     rdx, [rbp+3Fh+arg_18]
0x18005d27d  mov     rcx, rsi
0x18005d280  call    I_TransferCatalogToHvci
0x18005d285  mov     ebx, eax
0x18005d287  test    eax, eax
0x18005d289  jns     short loc_18005D2A6
0x18005d28b  cmp     eax, 0C0000603h
0x18005d290  jnz     short loc_18005D30D
0x18005d292  mov     rdx, [rbp+3Fh+BaseAddress]
0x18005d296  xor     r9d, r9d
0x18005d299  mov     r8d, r14d
0x18005d29c  mov     rcx, rsi
0x18005d29f  call    I_ParseCatalogAndMapHashes
0x18005d2a4  jmp     short loc_18005D2C7
0x18005d2a6  test    r12b, 3Ch
0x18005d2aa  jz      short loc_18005D2F2
0x18005d2ac  mov     rdx, [rbp+3Fh+BaseAddress]
0x18005d2b0  mov     r9d, r12d
0x18005d2b3  mov     r8d, r14d
0x18005d2b6  mov     rcx, rsi
0x18005d2b9  call    I_ParseCatalogAndMapHashes
0x18005d2be  mov     ebx, eax
0x18005d2c0  cmp     eax, 0C0000603h
0x18005d2c5  jnz     short loc_18005D2EE
0x18005d2c7  mov     rax, [rbp+3Fh+arg_0]
0x18005d2cb  test    rax, rax
0x18005d2ce  jz      short loc_18005D30D
0x18005d2d0  lea     r8, [rsi+0A8h]
0x18005d2d7  mov     byte ptr [rsp+0C0h+var_A0], 0
0x18005d2dc  lea     rdx, [rsi+48h]
0x18005d2e0  mov     r9d, 0C0000603h
0x18005d2e6  mov     rcx, rax
0x18005d2e9  call    CiInstrumentDriverSignatureRetry
0x18005d2ee  test    ebx, ebx
0x18005d2f0  js      short loc_18005D30D
0x18005d2f2  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x18005d2f7  test    eax, eax
0x18005d2f9  jz      short loc_18005D30D
0x18005d2fb  mov     rcx, [rbp+3Fh+var_70]; Handle
0x18005d2ff  lea     rdx, [rsi+110h]
0x18005d306  call    KappxCheckTrustLabelAce
0x18005d30b  mov     ebx, eax
0x18005d30d  mov     r14, [rbp+3Fh+MemoryDescriptorList]
0x18005d311  test    r14, r14
0x18005d314  jz      short loc_18005D334
0x18005d316  mov     rcx, r14; MemoryDescriptorList
0x18005d319  call    cs:__imp_MmUnlockPages
0x18005d320  nop     dword ptr [rax+rax+00h]
0x18005d325  mov     rcx, r14; Mdl
0x18005d328  call    cs:__imp_IoFreeMdl
0x18005d32f  nop     dword ptr [rax+rax+00h]
0x18005d334  mov     rcx, [rbp+3Fh+Handle]; Handle
0x18005d338  test    rcx, rcx
0x18005d33b  jz      short loc_18005D349
0x18005d33d  call    cs:__imp_ZwClose
0x18005d344  nop     dword ptr [rax+rax+00h]
0x18005d349  mov     rcx, [rbp+3Fh+var_70]; Handle
0x18005d34d  test    rcx, rcx
0x18005d350  jz      short loc_18005D35E
0x18005d352  call    cs:__imp_ZwClose
0x18005d359  nop     dword ptr [rax+rax+00h]
0x18005d35e  mov     rdx, [rbp+3Fh+BaseAddress]; BaseAddress
0x18005d362  test    rdx, rdx
0x18005d365  jz      short loc_18005D377
0x18005d367  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005d36b  call    cs:__imp_ZwUnmapViewOfSection
0x18005d372  nop     dword ptr [rax+rax+00h]
0x18005d377  test    r12d, r12d
0x18005d37a  jz      short loc_18005D3B7
0x18005d37c  mov     rcx, rdi
0x18005d37f  test    ebx, ebx
0x18005d381  js      short loc_18005D391
0x18005d383  lea     rdx, CiCatalogLoadComplete
0x18005d38a  call    CiLogFileEvent
0x18005d38f  jmp     short loc_18005D3C3
0x18005d391  cmp     ebx, 0C0000603h
0x18005d397  jnz     short loc_18005D3A7
0x18005d399  lea     rdx, CiRevokedCatalog
0x18005d3a0  call    CiLogFileEvent
0x18005d3a5  jmp     short loc_18005D3BB
0x18005d3a7  lea     r8, CiInvalidCatalog
0x18005d3ae  mov     edx, ebx
0x18005d3b0  call    CiLogFileEventWithStatus
0x18005d3b5  jmp     short loc_18005D3BB
0x18005d3b7  test    ebx, ebx
  ... truncated ...
```
