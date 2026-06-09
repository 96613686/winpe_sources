# CscDclpInitializeFsctlBufferContext

- ea: `0x14007c5b4`
- end: `0x14007cd2a`
- name: `CscDclpInitializeFsctlBufferContext`
- size: `1910`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, KPROCESSOR_MODE, unsigned __int64, SIZE_T Length)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14007cd30`

## callees

- `0x140012b74`
- `0x1400169d4`
- `0x140018930`
- `0x1400190ec`
- `0x140019608`
- `0x14002e8b0`
- `0x14002ea2c`
- `0x14007c5b4`
- `0x14007d3d8`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14007cbab`
- `ntoskrnl!IoAllocateMdl` at `0x14007cbab`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007cc2c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007cc2c`
- `ntoskrnl!ProbeForWrite` at `0x14007cac1`
- `ntoskrnl!ProbeForWrite` at `0x14007cac1`
- `ntoskrnl!ProbeForRead` at `0x14007cab3`
- `ntoskrnl!ProbeForRead` at `0x14007cab3`
- `ntoskrnl!MmIsKernelAddress` at `0x14007ca26`
- `ntoskrnl!MmIsKernelAddress` at `0x14007ca60`
- `ntoskrnl!MmIsKernelAddress` at `0x14007ca26`
- `ntoskrnl!MmIsKernelAddress` at `0x14007ca60`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007cbfa`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007cbfa`
- `ntoskrnl!RtlAssert` at `0x14007c745`
- `ntoskrnl!RtlAssert` at `0x14007c87b`
- `ntoskrnl!RtlAssert` at `0x14007ca49`
- `ntoskrnl!RtlAssert` at `0x14007ca83`
- `ntoskrnl!RtlAssert` at `0x14007c745`
- `ntoskrnl!RtlAssert` at `0x14007c87b`
- `ntoskrnl!RtlAssert` at `0x14007ca49`
- `ntoskrnl!RtlAssert` at `0x14007ca83`

## string_xrefs

- `0x14007c73e`: `CscDclpIsValidFsctlBufferDescriptor(Descriptor)`

## pseudocode

```c
__int64 __fastcall CscDclpInitializeFsctlBufferContext(
        __int64 a1,
        unsigned __int8 *a2,
        KPROCESSOR_MODE a3,
        unsigned __int64 a4,
        SIZE_T Length)
{
  ULONG v7; // r12d
  int v8; // edx
  int v9; // edi
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rdx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  unsigned __int8 v15; // bl
  unsigned int v16; // ebx
  unsigned __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v21; // r9
  ULONG v22; // r8d
  __int64 v23; // rcx
  unsigned __int64 v24; // r9
  void *v25; // rcx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  struct _MDL *Mdl; // rax
  __int64 v29; // rcx
  PVOID v30; // rax

  v7 = Length;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qqDDDDDqD(
      WPP_GLOBAL_Control->AttachedDevice,
      a2[1],
      *a2,
      a1,
      a2,
      *a2,
      a2[1],
      *((_DWORD *)a2 + 1),
      *((_DWORD *)a2 + 2),
      a3,
      a4,
      Length);
  v8 = a2[1];
  v9 = 0;
  if ( !(_BYTE)v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      goto LABEL_23;
    v11 = a2[1];
    v12 = 10;
    goto LABEL_22;
  }
  v11 = a2[1];
  if ( ((v8 - 1) & v8) != 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      goto LABEL_23;
    v12 = 11;
LABEL_22:
    WPP_SF_d(v10->AttachedDevice, v12, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, v11);
    goto LABEL_23;
  }
  if ( (*a2 & 1) != 0 && (*a2 & 2) != 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      goto LABEL_23;
    v14 = 12;
    goto LABEL_14;
  }
  v15 = 1;
  if ( *((_DWORD *)a2 + 1) > *((_DWORD *)a2 + 2) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      goto LABEL_23;
    v14 = 13;
LABEL_14:
    WPP_SF_(v13->AttachedDevice, v14, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids);
LABEL_23:
    v15 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, v15);
  if ( !v15 )
    RtlAssert(
      "CscDclpIsValidFsctlBufferDescriptor(Descriptor)",
      "base\\fs\\remotefs\\rdr\\csc\\dcl\\kernel\\fsctl.c",
      0x727u,
      0);
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  if ( (*a2 & 1) == 0 )
  {
    v21 = *((unsigned int *)a2 + 1);
    if ( (unsigned int)Length < (unsigned int)v21 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, v21, Length);
      if ( a3 )
        goto LABEL_49;
      v22 = 1851;
LABEL_48:
      RtlAssert("KernelMode != RequestorMode", "base\\fs\\remotefs\\rdr\\csc\\dcl\\kernel\\fsctl.c", v22, 0);
LABEL_49:
      v16 = -1073741811;
LABEL_112:
      CscDclpCleanupFsctlBufferContext(a1, 0);
      goto LABEL_38;
    }
    if ( (_DWORD)Length && !*((_DWORD *)a2 + 2) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids);
      if ( a3 )
        goto LABEL_49;
      v22 = 1859;
      goto LABEL_48;
    }
    if ( (unsigned int)Length > *((_DWORD *)a2 + 2) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids);
      v7 = *((_DWORD *)a2 + 2);
    }
    v23 = a2[1];
    v24 = a4;
    if ( ((v23 - 1) & a4) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids);
      if ( a3 )
        goto LABEL_49;
      v22 = 1881;
      goto LABEL_48;
    }
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids);
      *(_QWORD *)(a1 + 16) = 0;
      goto LABEL_31;
    }
    if ( !a4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, v7);
      if ( a3 )
        goto LABEL_49;
      v22 = 1905;
      goto LABEL_48;
    }
    if ( !a3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids);
        v24 = a4;
      }
      if ( !(unsigned __int8)MmIsKernelAddress(v24) )
        RtlAssert("MmIsKernelAddress( Buffer )", "base\\fs\\remotefs\\rdr\\csc\\dcl\\kernel\\fsctl.c", 0x783u, 0);
      if ( !(unsigned __int8)MmIsKernelAddress(a4 + v7) )
        RtlAssert(
          "MmIsKernelAddress( ((PCHAR)( ((PCHAR)(Buffer)) + ((ULONG_PTR)(Length)) )) )",
          "base\\fs\\remotefs\\rdr\\csc\\dcl\\kernel\\fsctl.c",
          0x784u,
          0);
      v17 = a4;
      *(_QWORD *)(a1 + 16) = a4;
      v16 = 0;
      goto LABEL_33;
    }
    if ( (*a2 & 2) != 0 )
      ProbeForWrite((volatile void *)a4, v7, v23);
    else
      ProbeForRead((volatile void *)a4, v7, v23);
    if ( (*a2 & 4) != 0 )
    {
      v25 = (void *)CscDclpAllocate(*((_QWORD *)a2 + 2), v7);
      *(_QWORD *)(a1 + 16) = v25;
      if ( !v25 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        {
          goto LABEL_97;
        }
        v27 = 44;
LABEL_96:
        WPP_SF_(v26->AttachedDevice, v27, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids);
LABEL_97:
        v16 = -1073741670;
        goto LABEL_112;
      }
      if ( (*a2 & 2) == 0 )
        RtlCopyFromUser(v25, (void *)a4, v7);
    }
    else
    {
      Mdl = IoAllocateMdl((PVOID)a4, v7, 0, 1u, 0);
      *(_QWORD *)(a1 + 8) = Mdl;
      if ( !Mdl )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        {
          goto LABEL_97;
        }
        v27 = 46;
        goto LABEL_96;
      }
      MmProbeAndLockPages(Mdl, a3, (LOCK_OPERATION)((*a2 >> 1) & 1));
      v29 = *(_QWORD *)(a1 + 8);
      if ( (*(_BYTE *)(v29 + 10) & 5) != 0 )
        v30 = *(PVOID *)(v29 + 24);
      else
        v30 = MmMapLockedPagesSpecifyCache((PMDL)v29, 0, MmCached, 0, 0, 0x40000010u);
      *(_QWORD *)(a1 + 16) = v30;
      if ( !v30 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        {
          goto LABEL_97;
        }
        v27 = 48;
        goto LABEL_96;
      }
    }
    v16 = 0;
    goto LABEL_32;
  }
  v7 = 0;
LABEL_31:
  v16 = 0;
LABEL_32:
  v17 = a4;
LABEL_33:
  *(_QWORD *)a1 = v17;
  *(_DWORD *)(a1 + 24) = v7;
  v18 = *a2;
  *(_BYTE *)(a1 + 28) = v18;
  *(_BYTE *)(a1 + 29) = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    v19 = *(_QWORD *)(a1 + 8);
    if ( v19 )
      v9 = *(__int16 *)(v19 + 10);
    WPP_SF_qDDDqqqD(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)a3,
      v18,
      a1,
      v18,
      a3,
      v7,
      *(_QWORD *)(a1 + 16),
      a4,
      v19,
      v9);
  }
LABEL_38:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x14007c5b4  mov     r11, rsp
0x14007c5b7  mov     [r11+20h], r9
0x14007c5bb  mov     [r11+18h], r8b
0x14007c5bf  mov     [r11+10h], rdx
0x14007c5c3  mov     [r11+8], rcx
0x14007c5c7  push    rbx
0x14007c5c8  push    rdi
0x14007c5c9  push    r12
0x14007c5cb  push    r13
0x14007c5cd  push    r14
0x14007c5cf  push    r15
0x14007c5d1  sub     rsp, 68h
0x14007c5d5  mov     r14, rdx
0x14007c5d8  mov     r13, rcx
0x14007c5db  lea     r15, WPP_GLOBAL_Control
0x14007c5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c5e9  mov     r12d, dword ptr [rsp+98h+Length]
0x14007c5f1  cmp     rcx, r15
0x14007c5f4  jz      short loc_14007C63D
0x14007c5f6  mov     eax, [rcx+2Ch]
0x14007c5f9  test    al, 40h
0x14007c5fb  jz      short loc_14007C63D
0x14007c5fd  movsx   eax, r8b
0x14007c601  movzx   edx, byte ptr [rdx+1]
0x14007c605  movzx   r8d, byte ptr [r14]
0x14007c609  mov     [r11-40h], r12d
0x14007c60d  mov     [r11-48h], r9
0x14007c611  mov     dword ptr [rsp+98h+var_50], eax
0x14007c615  mov     eax, [r14+8]
0x14007c619  mov     dword ptr [rsp+98h+var_58], eax
0x14007c61d  mov     eax, [r14+4]
0x14007c621  mov     dword ptr [rsp+98h+var_60], eax
0x14007c625  mov     [rsp+98h+var_68], edx
0x14007c629  mov     [r11-70h], r8d
0x14007c62d  mov     [r11-78h], r14
0x14007c631  mov     r9, r13
0x14007c634  mov     rcx, [rcx+18h]
0x14007c638  call    WPP_SF_qqDDDDDqD
0x14007c63d  movzx   edx, byte ptr [r14+1]
0x14007c642  xor     edi, edi
0x14007c644  test    dl, dl
0x14007c646  jnz     short loc_14007C66B
0x14007c648  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c64f  cmp     rcx, r15
0x14007c652  jz      loc_14007C6F8
0x14007c658  mov     eax, [rcx+2Ch]
0x14007c65b  test    al, 40h
0x14007c65d  jz      loc_14007C6F8
0x14007c663  mov     r9d, edx
0x14007c666  lea     edx, [rdi+0Ah]
0x14007c669  jmp     short loc_14007C6E8
0x14007c66b  mov     r9d, edx
0x14007c66e  lea     eax, [rdx-1]
0x14007c671  test    edx, eax
0x14007c673  jnz     short loc_14007C6D0
0x14007c675  mov     al, [r14]
0x14007c678  test    al, 1
0x14007c67a  jz      short loc_14007C6AA
0x14007c67c  test    al, 2
0x14007c67e  jz      short loc_14007C6AA
0x14007c680  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c687  cmp     rcx, r15
0x14007c68a  jz      short loc_14007C6F8
0x14007c68c  mov     eax, [rcx+2Ch]
0x14007c68f  test    al, 40h
0x14007c691  jz      short loc_14007C6F8
0x14007c693  mov     edx, 0Ch
0x14007c698  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c69f  mov     rcx, [rcx+18h]
0x14007c6a3  call    WPP_SF_
0x14007c6a8  jmp     short loc_14007C6F8
0x14007c6aa  mov     bl, 1
0x14007c6ac  mov     eax, [r14+8]
0x14007c6b0  cmp     [r14+4], eax
0x14007c6b4  jbe     short loc_14007C6FB
0x14007c6b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c6bd  cmp     rcx, r15
0x14007c6c0  jz      short loc_14007C6F8
0x14007c6c2  mov     eax, [rcx+2Ch]
0x14007c6c5  test    al, 40h
0x14007c6c7  jz      short loc_14007C6F8
0x14007c6c9  mov     edx, 0Dh
0x14007c6ce  jmp     short loc_14007C698
0x14007c6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c6d7  cmp     rcx, r15
0x14007c6da  jz      short loc_14007C6F8
0x14007c6dc  mov     eax, [rcx+2Ch]
0x14007c6df  test    al, 40h
0x14007c6e1  jz      short loc_14007C6F8
0x14007c6e3  mov     edx, 0Bh
0x14007c6e8  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c6ef  mov     rcx, [rcx+18h]
0x14007c6f3  call    WPP_SF_d
0x14007c6f8  mov     bl, dil
0x14007c6fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c702  cmp     rcx, r15
0x14007c705  jz      short loc_14007C727
0x14007c707  mov     eax, [rcx+2Ch]
0x14007c70a  test    al, 40h
0x14007c70c  jz      short loc_14007C727
0x14007c70e  movzx   r9d, bl
0x14007c712  mov     edx, 0Eh
0x14007c717  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c71e  mov     rcx, [rcx+18h]
0x14007c722  call    WPP_SF_d
0x14007c727  test    bl, bl
0x14007c729  lea     rbx, aBaseFsRemotefs_3; "base\\fs\\remotefs\\rdr\\csc\\dcl\\kern"...
0x14007c730  jnz     short loc_14007C751
0x14007c732  xor     r9d, r9d; MutableMessage
0x14007c735  mov     r8d, 727h; LineNumber
0x14007c73b  mov     rdx, rbx; VoidFileName
0x14007c73e  lea     rcx, aCscdclpisvalid; "CscDclpIsValidFsctlBufferDescriptor(Des"...
0x14007c745  call    cs:__imp_RtlAssert
0x14007c74c  nop     dword ptr [rax+rax+00h]
0x14007c751  xorps   xmm0, xmm0
0x14007c754  movups  xmmword ptr [r13+0], xmm0
0x14007c759  movups  xmmword ptr [r13+10h], xmm0
0x14007c75e  test    byte ptr [r14], 1
0x14007c762  jz      loc_14007C828
0x14007c768  mov     r12d, edi
0x14007c76b  mov     ebx, edi
0x14007c76d  mov     rax, [rsp+98h+Address]
0x14007c775  mov     [r13+0], rax
0x14007c779  mov     [r13+18h], r12d
0x14007c77d  movzx   r8d, byte ptr [r14]
0x14007c781  mov     [r13+1Ch], r8b
0x14007c785  movsx   edx, [rsp+98h+AccessMode]
0x14007c78d  mov     [r13+1Dh], dl
0x14007c791  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c798  cmp     rcx, r15
0x14007c79b  jz      short loc_14007C7EA
0x14007c79d  mov     eax, [rcx+2Ch]
0x14007c7a0  test    al, 40h
0x14007c7a2  jz      short loc_14007C7EA
0x14007c7a4  mov     rax, [r13+8]
0x14007c7a8  test    rax, rax
0x14007c7ab  jz      short loc_14007C7B1
0x14007c7ad  movsx   edi, word ptr [rax+0Ah]
0x14007c7b1  mov     [rsp+98h+var_48], edi
0x14007c7b5  mov     [rsp+98h+var_50], rax
0x14007c7ba  mov     rax, [rsp+98h+Address]
0x14007c7c2  mov     [rsp+98h+var_58], rax
0x14007c7c7  mov     rax, [r13+10h]
0x14007c7cb  mov     [rsp+98h+var_60], rax
0x14007c7d0  mov     [rsp+98h+var_68], r12d
0x14007c7d5  mov     [rsp+98h+Priority], edx
0x14007c7d9  mov     dword ptr [rsp+98h+Irp], r8d
0x14007c7de  mov     r9, r13
0x14007c7e1  mov     rcx, [rcx+18h]
0x14007c7e5  call    WPP_SF_qDDDqqqD
0x14007c7ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c7f1  cmp     rcx, r15
0x14007c7f4  jz      short loc_14007C816
0x14007c7f6  mov     edx, [rcx+2Ch]
0x14007c7f9  test    dl, 40h
0x14007c7fc  jz      short loc_14007C816
0x14007c7fe  mov     edx, 32h ; '2'
0x14007c803  mov     r9d, ebx
0x14007c806  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c80d  mov     rcx, [rcx+18h]
0x14007c811  call    WPP_SF_d
0x14007c816  mov     eax, ebx
0x14007c818  add     rsp, 68h
0x14007c81c  pop     r15
0x14007c81e  pop     r14
0x14007c820  pop     r13
0x14007c822  pop     r12
0x14007c824  pop     rdi
0x14007c825  pop     rbx
0x14007c826  retn
0x14007c828  mov     r9d, [r14+4]
0x14007c82c  cmp     r12d, r9d
0x14007c82f  jnb     short loc_14007C891
0x14007c831  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c838  cmp     rcx, r15
0x14007c83b  jz      short loc_14007C85E
0x14007c83d  mov     eax, [rcx+2Ch]
0x14007c840  test    al, 40h
0x14007c842  jz      short loc_14007C85E
0x14007c844  mov     edx, 24h ; '$'
0x14007c849  mov     dword ptr [rsp+98h+Irp], r12d
0x14007c84e  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c855  mov     rcx, [rcx+18h]
0x14007c859  call    WPP_SF_Dd
0x14007c85e  cmp     [rsp+98h+AccessMode], dil
0x14007c866  jnz     short loc_14007C887
0x14007c868  mov     r8d, 73Bh; LineNumber
0x14007c86e  xor     r9d, r9d; MutableMessage
0x14007c871  mov     rdx, rbx; VoidFileName
0x14007c874  lea     rcx, aKernelmodeRequ; "KernelMode != RequestorMode"
0x14007c87b  call    cs:__imp_RtlAssert
0x14007c882  nop     dword ptr [rax+rax+00h]
0x14007c887  mov     ebx, 0C000000Dh
0x14007c88c  jmp     loc_14007CD1B
0x14007c891  test    r12d, r12d
0x14007c894  jz      short loc_14007C8D6
0x14007c896  cmp     [r14+8], edi
0x14007c89a  jnz     short loc_14007C8D6
0x14007c89c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c8a3  cmp     rcx, r15
0x14007c8a6  jz      short loc_14007C8C4
0x14007c8a8  mov     eax, [rcx+2Ch]
0x14007c8ab  test    al, 40h
0x14007c8ad  jz      short loc_14007C8C4
0x14007c8af  mov     edx, 25h ; '%'
0x14007c8b4  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c8bb  mov     rcx, [rcx+18h]
0x14007c8bf  call    WPP_SF_
0x14007c8c4  cmp     [rsp+98h+AccessMode], dil
0x14007c8cc  jnz     short loc_14007C887
0x14007c8ce  mov     r8d, 743h
0x14007c8d4  jmp     short loc_14007C86E
0x14007c8d6  cmp     r12d, [r14+8]
0x14007c8da  jbe     short loc_14007C910
0x14007c8dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c8e3  cmp     rcx, r15
0x14007c8e6  jz      short loc_14007C904
0x14007c8e8  mov     eax, [rcx+2Ch]
0x14007c8eb  test    al, 40h
0x14007c8ed  jz      short loc_14007C904
0x14007c8ef  mov     edx, 26h ; '&'
0x14007c8f4  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c8fb  mov     rcx, [rcx+18h]
0x14007c8ff  call    WPP_SF_
0x14007c904  mov     r12d, [r14+8]
0x14007c908  mov     dword ptr [rsp+98h+Length], r12d
0x14007c910  movzx   ecx, byte ptr [r14+1]
0x14007c915  lea     rax, [rcx-1]
0x14007c919  mov     r9, [rsp+98h+Address]
0x14007c921  test    r9, rax
0x14007c924  jz      short loc_14007C967
0x14007c926  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c92d  cmp     rcx, r15
0x14007c930  jz      short loc_14007C94E
0x14007c932  mov     eax, [rcx+2Ch]
0x14007c935  test    al, 40h
0x14007c937  jz      short loc_14007C94E
0x14007c939  mov     edx, 27h ; '''
0x14007c93e  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c945  mov     rcx, [rcx+18h]
0x14007c949  call    WPP_SF_
0x14007c94e  cmp     [rsp+98h+AccessMode], dil
0x14007c956  jnz     loc_14007C887
0x14007c95c  mov     r8d, 759h
0x14007c962  jmp     loc_14007C86E
0x14007c967  test    r12d, r12d
0x14007c96a  jnz     short loc_14007C99D
0x14007c96c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c973  cmp     rcx, r15
0x14007c976  jz      short loc_14007C994
0x14007c978  mov     eax, [rcx+2Ch]
0x14007c97b  test    al, 40h
0x14007c97d  jz      short loc_14007C994
0x14007c97f  lea     edx, [r12+28h]
0x14007c984  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c98b  mov     rcx, [rcx+18h]
0x14007c98f  call    WPP_SF_
0x14007c994  mov     [r13+10h], rdi
0x14007c998  jmp     loc_14007C76B
0x14007c99d  test    r9, r9
0x14007c9a0  jnz     short loc_14007C9E5
0x14007c9a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c9a9  cmp     rcx, r15
0x14007c9ac  jz      short loc_14007C9CC
0x14007c9ae  mov     eax, [rcx+2Ch]
0x14007c9b1  test    al, 40h
0x14007c9b3  jz      short loc_14007C9CC
0x14007c9b5  lea     edx, [r9+29h]
0x14007c9b9  mov     r9d, r12d
0x14007c9bc  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007c9c3  mov     rcx, [rcx+18h]
0x14007c9c7  call    WPP_SF_d
0x14007c9cc  cmp     [rsp+98h+AccessMode], dil
0x14007c9d4  jnz     loc_14007C887
0x14007c9da  mov     r8d, 771h
0x14007c9e0  jmp     loc_14007C86E
0x14007c9e5  cmp     [rsp+98h+AccessMode], dil
0x14007c9ed  jnz     loc_14007CAA2
0x14007c9f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c9fa  cmp     rcx, r15
0x14007c9fd  jz      short loc_14007CA23
0x14007c9ff  mov     eax, [rcx+2Ch]
0x14007ca02  test    al, 40h
0x14007ca04  jz      short loc_14007CA23
0x14007ca06  mov     edx, 2Ah ; '*'
0x14007ca0b  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007ca12  mov     rcx, [rcx+18h]
0x14007ca16  call    WPP_SF_
0x14007ca1b  mov     r9, [rsp+98h+Address]
0x14007ca23  mov     rcx, r9
0x14007ca26  call    cs:__imp_MmIsKernelAddress
0x14007ca2d  nop     dword ptr [rax+rax+00h]
0x14007ca32  test    al, al
0x14007ca34  jnz     short loc_14007CA55
0x14007ca36  xor     r9d, r9d; MutableMessage
0x14007ca39  mov     r8d, 783h; LineNumber
0x14007ca3f  mov     rdx, rbx; VoidFileName
0x14007ca42  lea     rcx, aMmiskerneladdr; "MmIsKernelAddress( Buffer )"
0x14007ca49  call    cs:__imp_RtlAssert
0x14007ca50  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
