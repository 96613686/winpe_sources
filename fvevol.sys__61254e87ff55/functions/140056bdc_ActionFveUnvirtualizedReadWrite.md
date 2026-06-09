# ActionFveUnvirtualizedReadWrite

- ea: `0x140056bdc`
- end: `0x140056f60`
- name: `ActionFveUnvirtualizedReadWrite`
- size: `900`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14008b6ec`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140009cb4`
- `0x140022bf0`
- `0x140056bdc`
- `0x1400e859c`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x140056e67`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140056e67`
- `ntoskrnl!IoFreeMdl` at `0x140056e1a`
- `ntoskrnl!IoFreeMdl` at `0x140056eef`
- `ntoskrnl!IoFreeMdl` at `0x140056e1a`
- `ntoskrnl!IoFreeMdl` at `0x140056eef`
- `ntoskrnl!MmUnlockPages` at `0x140056e0b`
- `ntoskrnl!MmUnlockPages` at `0x140056ee0`
- `ntoskrnl!MmUnlockPages` at `0x140056e0b`
- `ntoskrnl!MmUnlockPages` at `0x140056ee0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140056db3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140056db3`
- `ntoskrnl!MmProbeAndLockPages` at `0x140056d7c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140056d7c`
- `ntoskrnl!IoAllocateMdl` at `0x140056d47`
- `ntoskrnl!IoAllocateMdl` at `0x140056d47`
- `ntoskrnl!KeStackAttachProcess` at `0x140056d04`
- `ntoskrnl!KeStackAttachProcess` at `0x140056d04`

## pseudocode

```c
__int64 __fastcall ActionFveUnvirtualizedReadWrite(__int64 a1, __int64 a2, __int64 a3)
{
  PDEVICE_OBJECT v6; // rcx
  struct _MDL *v7; // rsi
  char v8; // r12
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  int v13; // edi
  unsigned int i; // r13d
  ULONG v15; // edi
  struct _MDL *Mdl; // rax
  PVOID MappedSystemVa; // rcx
  int v18; // eax
  int v20; // [rsp+44h] [rbp-94h]
  struct _KPROCESS *PROCESS; // [rsp+48h] [rbp-90h]
  ULONG PROCESSa; // [rsp+48h] [rbp-90h]
  unsigned __int64 v23; // [rsp+58h] [rbp-80h]
  char *VirtualAddress; // [rsp+60h] [rbp-78h]
  unsigned int MemoryDescriptorList; // [rsp+68h] [rbp-70h]
  struct _KAPC_STATE ApcState; // [rsp+78h] [rbp-60h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  v20 = *(_DWORD *)(a3 + 4);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids);
  }
  v7 = 0;
  v8 = 0;
  if ( *(_WORD *)a3 != 32 )
    goto LABEL_32;
  if ( (PROCESS = *(struct _KPROCESS **)(a2 + 120),
        (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v6, a2))
    && (*(_BYTE *)(a1 + 4419) & 8) != 0
    || (v9 = *(_QWORD *)(a1 + 976), *(_WORD *)(v9 + 10) == 1) )
  {
    v10 = 0;
  }
  else
  {
    v10 = *(unsigned int *)(v9 + 28);
    if ( !(_DWORD)v10 )
      v10 = 1;
  }
  v11 = v10 * *(unsigned int *)(a1 + 1308);
  v12 = *(unsigned int *)(a3 + 24);
  MemoryDescriptorList = *(_DWORD *)(a3 + 24);
  if ( v12 <= v11 && (v23 = *(_QWORD *)(a3 + 8), v23 <= v11 - v12) )
  {
    v13 = 0;
    VirtualAddress = *(char **)(a3 + 16);
    KeStackAttachProcess(PROCESS, &ApcState);
    for ( i = MemoryDescriptorList; ; i -= PROCESSa )
    {
      v7 = 0;
      v8 = 0;
      if ( !i )
        break;
      v15 = i;
      if ( i > 0x100000 )
        v15 = 0x100000;
      PROCESSa = v15;
      Mdl = IoAllocateMdl(VirtualAddress, v15, 0, 1u, 0);
      v7 = Mdl;
      if ( !Mdl
        || ((MmProbeAndLockPages(Mdl, 1, (LOCK_OPERATION)(v20 != 15)), v8 = 1, (v7->MdlFlags & 5) == 0)
          ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000010u))
          : (MappedSystemVa = v7->MappedSystemVa),
            !MappedSystemVa) )
      {
        v13 = -1073741670;
        break;
      }
      v13 = FveRawIoSynchronous(
              a1,
              *(_QWORD *)(a1 + 112),
              4 - (unsigned int)(v20 != 15),
              0,
              0,
              v23,
              v15,
              (__int64)MappedSystemVa);
      if ( v13 < 0 )
        break;
      MmUnlockPages(v7);
      IoFreeMdl(v7);
      v23 += PROCESSa;
      VirtualAddress += PROCESSa;
    }
    KeUnstackDetachProcess(&ApcState);
    if ( v13 >= 0 && v20 == 15 )
    {
      v18 = FveRawIoSynchronous(a1, *(_QWORD *)(a1 + 112), 9, 0, 0, 0, 0, 0);
      v13 = v18;
      if ( v18 == -1073741822 || v18 == -1073741808 || v18 == -1073741637 )
        v13 = 0;
    }
  }
  else
  {
LABEL_32:
    v13 = -1073741811;
  }
  if ( v7 )
  {
    if ( v8 )
      MmUnlockPages(v7);
    IoFreeMdl(v7);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      114,
      WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
      (unsigned int)v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140056bdc  mov     r11, rsp
0x140056bdf  mov     [r11+20h], rsi
0x140056be3  push    rdi
0x140056be4  push    r12
0x140056be6  push    r13
0x140056be8  push    r14
0x140056bea  push    r15
0x140056bec  sub     rsp, 0B0h
0x140056bf3  mov     rax, cs:__security_cookie
0x140056bfa  xor     rax, rsp
0x140056bfd  mov     [rsp+0D8h+var_30], rax
0x140056c05  mov     r13, r8
0x140056c08  mov     rdi, rdx
0x140056c0b  mov     r15, rcx
0x140056c0e  mov     [rsp+0D8h+var_68], rcx
0x140056c13  xorps   xmm0, xmm0
0x140056c16  movups  xmmword ptr [rsp+0D8h+ApcState.ApcListHead.Flink], xmm0
0x140056c1b  movups  xmmword ptr [r11-50h], xmm0
0x140056c20  movups  xmmword ptr [r11-40h], xmm0
0x140056c25  mov     eax, [r8+4]
0x140056c29  mov     [rsp+0D8h+var_94], eax
0x140056c2d  lea     rax, WPP_GLOBAL_Control
0x140056c34  mov     rcx, cs:WPP_GLOBAL_Control
0x140056c3b  mov     r14d, 1
0x140056c41  cmp     rcx, rax
0x140056c44  jz      short loc_140056C68
0x140056c46  mov     eax, [rcx+2Ch]
0x140056c49  test    r14b, al
0x140056c4c  jz      short loc_140056C68
0x140056c4e  cmp     byte ptr [rcx+29h], 5
0x140056c52  jb      short loc_140056C68
0x140056c54  lea     edx, [r14+70h]
0x140056c58  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140056c5f  mov     rcx, [rcx+18h]
0x140056c63  call    WPP_SF_
0x140056c68  xor     esi, esi
0x140056c6a  xor     r12b, r12b
0x140056c6d  cmp     word ptr [r13+0], 20h ; ' '
0x140056c73  jnz     loc_140056ECE
0x140056c79  mov     rax, [rdi+78h]
0x140056c7d  mov     [rsp+0D8h+PROCESS], rax
0x140056c82  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x140056c87  test    eax, eax
0x140056c89  jz      short loc_140056C95
0x140056c8b  test    byte ptr [r15+1143h], 8
0x140056c93  jnz     short loc_140056CA3
0x140056c95  mov     rax, [r15+3D0h]
0x140056c9c  cmp     [rax+0Ah], r14w
0x140056ca1  jnz     short loc_140056CA7
0x140056ca3  xor     eax, eax
0x140056ca5  jmp     short loc_140056CB0
0x140056ca7  mov     eax, [rax+1Ch]
0x140056caa  test    eax, eax
0x140056cac  cmovz   eax, r14d
0x140056cb0  mov     ecx, [r15+51Ch]
0x140056cb7  imul    rcx, rax
0x140056cbb  mov     eax, [r13+18h]
0x140056cbf  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140056cc4  cmp     rax, rcx
0x140056cc7  ja      loc_140056ECE
0x140056ccd  mov     rdx, [r13+8]
0x140056cd1  mov     [rsp+0D8h+var_80], rdx
0x140056cd6  sub     rcx, rax
0x140056cd9  cmp     rdx, rcx
0x140056cdc  ja      loc_140056ECE
0x140056ce2  mov     eax, [rsp+0D8h+var_94]
0x140056ce6  mov     [rsp+0D8h+var_88], eax
0x140056cea  xor     edi, edi
0x140056cec  mov     [rsp+0D8h+var_98], sil
0x140056cf1  mov     rax, [r13+10h]
0x140056cf5  mov     [rsp+0D8h+VirtualAddress], rax
0x140056cfa  lea     rdx, [rsp+0D8h+ApcState]; ApcState
0x140056cff  mov     rcx, [rsp+0D8h+PROCESS]; PROCESS
0x140056d04  call    cs:__imp_KeStackAttachProcess
0x140056d0b  nop     dword ptr [rax+rax+00h]
0x140056d10  mov     r13, [rsp+0D8h+MemoryDescriptorList]
0x140056d15  mov     eax, 100000h
0x140056d1a  xor     esi, esi
0x140056d1c  xor     r12b, r12b
0x140056d1f  test    r13d, r13d
0x140056d22  jz      loc_140056E5D
0x140056d28  mov     edi, r13d
0x140056d2b  cmp     r13d, eax
0x140056d2e  cmova   edi, eax
0x140056d31  mov     dword ptr [rsp+0D8h+PROCESS], edi
0x140056d35  mov     [rsp+0D8h+Irp], rsi; Irp
0x140056d3a  mov     r9b, r14b; ChargeQuota
0x140056d3d  xor     r8d, r8d; SecondaryBuffer
0x140056d40  mov     edx, edi; Length
0x140056d42  mov     rcx, [rsp+0D8h+VirtualAddress]; VirtualAddress
0x140056d47  call    cs:__imp_IoAllocateMdl
0x140056d4e  nop     dword ptr [rax+rax+00h]
0x140056d53  mov     rsi, rax
0x140056d56  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140056d5b  test    rax, rax
0x140056d5e  jnz     short loc_140056D6A
0x140056d60  mov     edi, 0C000009Ah
0x140056d65  jmp     loc_140056E5D
0x140056d6a  xor     r8d, r8d
0x140056d6d  cmp     [rsp+0D8h+var_94], 0Fh
0x140056d72  setnz   r8b; Operation
0x140056d76  mov     dl, r14b; AccessMode
0x140056d79  mov     rcx, rsi; MemoryDescriptorList
0x140056d7c  call    cs:__imp_MmProbeAndLockPages
0x140056d83  nop     dword ptr [rax+rax+00h]
0x140056d88  nop
0x140056d89  mov     r12b, r14b
0x140056d8c  test    byte ptr [rsi+0Ah], 5
0x140056d90  jz      short loc_140056D98
0x140056d92  mov     rcx, [rsi+18h]
0x140056d96  jmp     short loc_140056DC2
0x140056d98  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x140056da0  mov     dword ptr [rsp+0D8h+Irp], 0; BugCheckOnFailure
0x140056da8  xor     r9d, r9d; RequestedAddress
0x140056dab  mov     r8d, r14d; CacheType
0x140056dae  xor     edx, edx; AccessMode
0x140056db0  mov     rcx, rsi; MemoryDescriptorList
0x140056db3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140056dba  nop     dword ptr [rax+rax+00h]
0x140056dbf  mov     rcx, rax
0x140056dc2  test    rcx, rcx
0x140056dc5  jz      short loc_140056D60
0x140056dc7  mov     eax, [rsp+0D8h+var_94]
0x140056dcb  add     eax, 0FFFFFFF1h
0x140056dce  neg     eax
0x140056dd0  sbb     r8d, r8d
0x140056dd3  add     r8d, 4
0x140056dd7  mov     [rsp+0D8h+var_A0], rcx
0x140056ddc  mov     [rsp+0D8h+var_A8], edi
0x140056de0  mov     rax, [rsp+0D8h+var_80]
0x140056de5  mov     qword ptr [rsp+0D8h+Priority], rax
0x140056dea  mov     [rsp+0D8h+Irp], 0
0x140056df3  xor     r9d, r9d
0x140056df6  mov     rdx, [r15+70h]
0x140056dfa  mov     rcx, r15
0x140056dfd  call    FveRawIoSynchronous
0x140056e02  mov     edi, eax
0x140056e04  test    eax, eax
0x140056e06  js      short loc_140056E5D
0x140056e08  mov     rcx, rsi; MemoryDescriptorList
0x140056e0b  call    cs:__imp_MmUnlockPages
0x140056e12  nop     dword ptr [rax+rax+00h]
0x140056e17  mov     rcx, rsi; Mdl
0x140056e1a  call    cs:__imp_IoFreeMdl
0x140056e21  nop     dword ptr [rax+rax+00h]
0x140056e26  mov     eax, dword ptr [rsp+0D8h+PROCESS]
0x140056e2a  add     [rsp+0D8h+var_80], rax
0x140056e2f  add     [rsp+0D8h+VirtualAddress], rax
0x140056e34  sub     r13d, eax
0x140056e37  jmp     loc_140056D15
0x140056e3c  mov     edi, 0C000000Dh
0x140056e41  mov     r12b, [rsp+0D8h+var_98]
0x140056e46  mov     r14d, 1
0x140056e4c  mov     rsi, [rsp+0D8h+MemoryDescriptorList]
0x140056e51  mov     r15, [rsp+0D8h+var_68]
0x140056e56  mov     r13d, [rsp+0D8h+var_88]
0x140056e5b  jmp     short loc_140056E62
0x140056e5d  mov     r13d, [rsp+0D8h+var_94]
0x140056e62  lea     rcx, [rsp+0D8h+ApcState]; ApcState
0x140056e67  call    cs:__imp_KeUnstackDetachProcess
0x140056e6e  nop     dword ptr [rax+rax+00h]
0x140056e73  test    edi, edi
0x140056e75  js      short loc_140056ED3
0x140056e77  cmp     r13d, 0Fh
0x140056e7b  jnz     short loc_140056ED3
0x140056e7d  mov     [rsp+0D8h+var_A0], 0
0x140056e86  mov     [rsp+0D8h+var_A8], 0
0x140056e8e  mov     qword ptr [rsp+0D8h+Priority], 0
0x140056e97  mov     [rsp+0D8h+Irp], 0
0x140056ea0  xor     r9d, r9d
0x140056ea3  lea     r8d, [r13-6]
0x140056ea7  mov     rdx, [r15+70h]
0x140056eab  mov     rcx, r15
0x140056eae  call    FveRawIoSynchronous
0x140056eb3  mov     edi, eax
0x140056eb5  cmp     eax, 0C0000002h
0x140056eba  jz      short loc_140056ECA
0x140056ebc  cmp     eax, 0C0000010h
0x140056ec1  jz      short loc_140056ECA
0x140056ec3  cmp     eax, 0C00000BBh
0x140056ec8  jnz     short loc_140056ED3
0x140056eca  xor     edi, edi
0x140056ecc  jmp     short loc_140056ED3
0x140056ece  mov     edi, 0C000000Dh
0x140056ed3  test    rsi, rsi
0x140056ed6  jz      short loc_140056EFB
0x140056ed8  test    r12b, r12b
0x140056edb  jz      short loc_140056EEC
0x140056edd  mov     rcx, rsi; MemoryDescriptorList
0x140056ee0  call    cs:__imp_MmUnlockPages
0x140056ee7  nop     dword ptr [rax+rax+00h]
0x140056eec  mov     rcx, rsi; Mdl
0x140056eef  call    cs:__imp_IoFreeMdl
0x140056ef6  nop     dword ptr [rax+rax+00h]
0x140056efb  mov     rcx, cs:WPP_GLOBAL_Control
0x140056f02  lea     rax, WPP_GLOBAL_Control
0x140056f09  cmp     rcx, rax
0x140056f0c  jz      short loc_140056F34
0x140056f0e  mov     eax, [rcx+2Ch]
0x140056f11  test    r14b, al
0x140056f14  jz      short loc_140056F34
0x140056f16  cmp     byte ptr [rcx+29h], 5
0x140056f1a  jb      short loc_140056F34
0x140056f1c  mov     edx, 72h ; 'r'
0x140056f21  mov     r9d, edi
0x140056f24  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140056f2b  mov     rcx, [rcx+18h]
0x140056f2f  call    WPP_SF_d
0x140056f34  mov     eax, edi
0x140056f36  mov     rcx, [rsp+0D8h+var_30]
0x140056f3e  xor     rcx, rsp; StackCookie
0x140056f41  call    __security_check_cookie
0x140056f46  mov     rsi, [rsp+0D8h+arg_18]
0x140056f4e  add     rsp, 0B0h
0x140056f55  pop     r15
0x140056f57  pop     r14
0x140056f59  pop     r13
0x140056f5b  pop     r12
0x140056f5d  pop     rdi
0x140056f5e  retn
```
