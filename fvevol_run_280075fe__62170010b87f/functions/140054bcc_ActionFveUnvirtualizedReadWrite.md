# ActionFveUnvirtualizedReadWrite

- ea: `0x140054bcc`
- end: `0x140054f50`
- name: `ActionFveUnvirtualizedReadWrite`
- size: `900`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14008964c`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140009bf4`
- `0x1400218c0`
- `0x140054bcc`
- `0x1400e5cec`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x140054e57`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140054e57`
- `ntoskrnl!IoFreeMdl` at `0x140054e0a`
- `ntoskrnl!IoFreeMdl` at `0x140054edf`
- `ntoskrnl!IoFreeMdl` at `0x140054e0a`
- `ntoskrnl!IoFreeMdl` at `0x140054edf`
- `ntoskrnl!MmUnlockPages` at `0x140054dfb`
- `ntoskrnl!MmUnlockPages` at `0x140054ed0`
- `ntoskrnl!MmUnlockPages` at `0x140054dfb`
- `ntoskrnl!MmUnlockPages` at `0x140054ed0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140054da3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140054da3`
- `ntoskrnl!MmProbeAndLockPages` at `0x140054d6c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140054d6c`
- `ntoskrnl!IoAllocateMdl` at `0x140054d37`
- `ntoskrnl!IoAllocateMdl` at `0x140054d37`
- `ntoskrnl!KeStackAttachProcess` at `0x140054cf4`
- `ntoskrnl!KeStackAttachProcess` at `0x140054cf4`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_db10fbeca6e03e7325aab39114461952_Traceguids);
  }
  v7 = 0;
  v8 = 0;
  if ( *(_WORD *)a3 != 32 )
    goto LABEL_32;
  if ( (PROCESS = *(struct _KPROCESS **)(a2 + 120),
        (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v6))
    && (*(_BYTE *)(a1 + 4403) & 8) != 0
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
      WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
      (unsigned int)v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140054bcc  mov     r11, rsp
0x140054bcf  mov     [r11+20h], rsi
0x140054bd3  push    rdi
0x140054bd4  push    r12
0x140054bd6  push    r13
0x140054bd8  push    r14
0x140054bda  push    r15
0x140054bdc  sub     rsp, 0B0h
0x140054be3  mov     rax, cs:__security_cookie
0x140054bea  xor     rax, rsp
0x140054bed  mov     [rsp+0D8h+var_30], rax
0x140054bf5  mov     r13, r8
0x140054bf8  mov     rdi, rdx
0x140054bfb  mov     r15, rcx
0x140054bfe  mov     [rsp+0D8h+var_68], rcx
0x140054c03  xorps   xmm0, xmm0
0x140054c06  movups  xmmword ptr [rsp+0D8h+ApcState.ApcListHead.Flink], xmm0
0x140054c0b  movups  xmmword ptr [r11-50h], xmm0
0x140054c10  movups  xmmword ptr [r11-40h], xmm0
0x140054c15  mov     eax, [r8+4]
0x140054c19  mov     [rsp+0D8h+var_94], eax
0x140054c1d  lea     rax, WPP_GLOBAL_Control
0x140054c24  mov     rcx, cs:WPP_GLOBAL_Control
0x140054c2b  mov     r14d, 1
0x140054c31  cmp     rcx, rax
0x140054c34  jz      short loc_140054C58
0x140054c36  mov     eax, [rcx+2Ch]
0x140054c39  test    r14b, al
0x140054c3c  jz      short loc_140054C58
0x140054c3e  cmp     byte ptr [rcx+29h], 5
0x140054c42  jb      short loc_140054C58
0x140054c44  lea     edx, [r14+70h]
0x140054c48  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140054c4f  mov     rcx, [rcx+18h]
0x140054c53  call    WPP_SF_
0x140054c58  xor     esi, esi
0x140054c5a  xor     r12b, r12b
0x140054c5d  cmp     word ptr [r13+0], 20h ; ' '
0x140054c63  jnz     loc_140054EBE
0x140054c69  mov     rax, [rdi+78h]
0x140054c6d  mov     [rsp+0D8h+PROCESS], rax
0x140054c72  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x140054c77  test    eax, eax
0x140054c79  jz      short loc_140054C85
0x140054c7b  test    byte ptr [r15+1133h], 8
0x140054c83  jnz     short loc_140054C93
0x140054c85  mov     rax, [r15+3D0h]
0x140054c8c  cmp     [rax+0Ah], r14w
0x140054c91  jnz     short loc_140054C97
0x140054c93  xor     eax, eax
0x140054c95  jmp     short loc_140054CA0
0x140054c97  mov     eax, [rax+1Ch]
0x140054c9a  test    eax, eax
0x140054c9c  cmovz   eax, r14d
0x140054ca0  mov     ecx, [r15+51Ch]
0x140054ca7  imul    rcx, rax
0x140054cab  mov     eax, [r13+18h]
0x140054caf  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140054cb4  cmp     rax, rcx
0x140054cb7  ja      loc_140054EBE
0x140054cbd  mov     rdx, [r13+8]
0x140054cc1  mov     [rsp+0D8h+var_80], rdx
0x140054cc6  sub     rcx, rax
0x140054cc9  cmp     rdx, rcx
0x140054ccc  ja      loc_140054EBE
0x140054cd2  mov     eax, [rsp+0D8h+var_94]
0x140054cd6  mov     [rsp+0D8h+var_88], eax
0x140054cda  xor     edi, edi
0x140054cdc  mov     [rsp+0D8h+var_98], sil
0x140054ce1  mov     rax, [r13+10h]
0x140054ce5  mov     [rsp+0D8h+VirtualAddress], rax
0x140054cea  lea     rdx, [rsp+0D8h+ApcState]; ApcState
0x140054cef  mov     rcx, [rsp+0D8h+PROCESS]; PROCESS
0x140054cf4  call    cs:__imp_KeStackAttachProcess
0x140054cfb  nop     dword ptr [rax+rax+00h]
0x140054d00  mov     r13, [rsp+0D8h+MemoryDescriptorList]
0x140054d05  mov     eax, 100000h
0x140054d0a  xor     esi, esi
0x140054d0c  xor     r12b, r12b
0x140054d0f  test    r13d, r13d
0x140054d12  jz      loc_140054E4D
0x140054d18  mov     edi, r13d
0x140054d1b  cmp     r13d, eax
0x140054d1e  cmova   edi, eax
0x140054d21  mov     dword ptr [rsp+0D8h+PROCESS], edi
0x140054d25  mov     [rsp+0D8h+Irp], rsi; Irp
0x140054d2a  mov     r9b, r14b; ChargeQuota
0x140054d2d  xor     r8d, r8d; SecondaryBuffer
0x140054d30  mov     edx, edi; Length
0x140054d32  mov     rcx, [rsp+0D8h+VirtualAddress]; VirtualAddress
0x140054d37  call    cs:__imp_IoAllocateMdl
0x140054d3e  nop     dword ptr [rax+rax+00h]
0x140054d43  mov     rsi, rax
0x140054d46  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140054d4b  test    rax, rax
0x140054d4e  jnz     short loc_140054D5A
0x140054d50  mov     edi, 0C000009Ah
0x140054d55  jmp     loc_140054E4D
0x140054d5a  xor     r8d, r8d
0x140054d5d  cmp     [rsp+0D8h+var_94], 0Fh
0x140054d62  setnz   r8b; Operation
0x140054d66  mov     dl, r14b; AccessMode
0x140054d69  mov     rcx, rsi; MemoryDescriptorList
0x140054d6c  call    cs:__imp_MmProbeAndLockPages
0x140054d73  nop     dword ptr [rax+rax+00h]
0x140054d78  nop
0x140054d79  mov     r12b, r14b
0x140054d7c  test    byte ptr [rsi+0Ah], 5
0x140054d80  jz      short loc_140054D88
0x140054d82  mov     rcx, [rsi+18h]
0x140054d86  jmp     short loc_140054DB2
0x140054d88  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x140054d90  mov     dword ptr [rsp+0D8h+Irp], 0; BugCheckOnFailure
0x140054d98  xor     r9d, r9d; RequestedAddress
0x140054d9b  mov     r8d, r14d; CacheType
0x140054d9e  xor     edx, edx; AccessMode
0x140054da0  mov     rcx, rsi; MemoryDescriptorList
0x140054da3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140054daa  nop     dword ptr [rax+rax+00h]
0x140054daf  mov     rcx, rax
0x140054db2  test    rcx, rcx
0x140054db5  jz      short loc_140054D50
0x140054db7  mov     eax, [rsp+0D8h+var_94]
0x140054dbb  add     eax, 0FFFFFFF1h
0x140054dbe  neg     eax
0x140054dc0  sbb     r8d, r8d
0x140054dc3  add     r8d, 4
0x140054dc7  mov     [rsp+0D8h+var_A0], rcx
0x140054dcc  mov     [rsp+0D8h+var_A8], edi
0x140054dd0  mov     rax, [rsp+0D8h+var_80]
0x140054dd5  mov     qword ptr [rsp+0D8h+Priority], rax
0x140054dda  mov     [rsp+0D8h+Irp], 0
0x140054de3  xor     r9d, r9d
0x140054de6  mov     rdx, [r15+70h]
0x140054dea  mov     rcx, r15
0x140054ded  call    FveRawIoSynchronous
0x140054df2  mov     edi, eax
0x140054df4  test    eax, eax
0x140054df6  js      short loc_140054E4D
0x140054df8  mov     rcx, rsi; MemoryDescriptorList
0x140054dfb  call    cs:__imp_MmUnlockPages
0x140054e02  nop     dword ptr [rax+rax+00h]
0x140054e07  mov     rcx, rsi; Mdl
0x140054e0a  call    cs:__imp_IoFreeMdl
0x140054e11  nop     dword ptr [rax+rax+00h]
0x140054e16  mov     eax, dword ptr [rsp+0D8h+PROCESS]
0x140054e1a  add     [rsp+0D8h+var_80], rax
0x140054e1f  add     [rsp+0D8h+VirtualAddress], rax
0x140054e24  sub     r13d, eax
0x140054e27  jmp     loc_140054D05
0x140054e2c  mov     edi, 0C000000Dh
0x140054e31  mov     r12b, [rsp+0D8h+var_98]
0x140054e36  mov     r14d, 1
0x140054e3c  mov     rsi, [rsp+0D8h+MemoryDescriptorList]
0x140054e41  mov     r15, [rsp+0D8h+var_68]
0x140054e46  mov     r13d, [rsp+0D8h+var_88]
0x140054e4b  jmp     short loc_140054E52
0x140054e4d  mov     r13d, [rsp+0D8h+var_94]
0x140054e52  lea     rcx, [rsp+0D8h+ApcState]; ApcState
0x140054e57  call    cs:__imp_KeUnstackDetachProcess
0x140054e5e  nop     dword ptr [rax+rax+00h]
0x140054e63  test    edi, edi
0x140054e65  js      short loc_140054EC3
0x140054e67  cmp     r13d, 0Fh
0x140054e6b  jnz     short loc_140054EC3
0x140054e6d  mov     [rsp+0D8h+var_A0], 0
0x140054e76  mov     [rsp+0D8h+var_A8], 0
0x140054e7e  mov     qword ptr [rsp+0D8h+Priority], 0
0x140054e87  mov     [rsp+0D8h+Irp], 0
0x140054e90  xor     r9d, r9d
0x140054e93  lea     r8d, [r13-6]
0x140054e97  mov     rdx, [r15+70h]
0x140054e9b  mov     rcx, r15
0x140054e9e  call    FveRawIoSynchronous
0x140054ea3  mov     edi, eax
0x140054ea5  cmp     eax, 0C0000002h
0x140054eaa  jz      short loc_140054EBA
0x140054eac  cmp     eax, 0C0000010h
0x140054eb1  jz      short loc_140054EBA
0x140054eb3  cmp     eax, 0C00000BBh
0x140054eb8  jnz     short loc_140054EC3
0x140054eba  xor     edi, edi
0x140054ebc  jmp     short loc_140054EC3
0x140054ebe  mov     edi, 0C000000Dh
0x140054ec3  test    rsi, rsi
0x140054ec6  jz      short loc_140054EEB
0x140054ec8  test    r12b, r12b
0x140054ecb  jz      short loc_140054EDC
0x140054ecd  mov     rcx, rsi; MemoryDescriptorList
0x140054ed0  call    cs:__imp_MmUnlockPages
0x140054ed7  nop     dword ptr [rax+rax+00h]
0x140054edc  mov     rcx, rsi; Mdl
0x140054edf  call    cs:__imp_IoFreeMdl
0x140054ee6  nop     dword ptr [rax+rax+00h]
0x140054eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140054ef2  lea     rax, WPP_GLOBAL_Control
0x140054ef9  cmp     rcx, rax
0x140054efc  jz      short loc_140054F24
0x140054efe  mov     eax, [rcx+2Ch]
0x140054f01  test    r14b, al
0x140054f04  jz      short loc_140054F24
0x140054f06  cmp     byte ptr [rcx+29h], 5
0x140054f0a  jb      short loc_140054F24
0x140054f0c  mov     edx, 72h ; 'r'
0x140054f11  mov     r9d, edi
0x140054f14  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140054f1b  mov     rcx, [rcx+18h]
0x140054f1f  call    WPP_SF_d
0x140054f24  mov     eax, edi
0x140054f26  mov     rcx, [rsp+0D8h+var_30]
0x140054f2e  xor     rcx, rsp; StackCookie
0x140054f31  call    __security_check_cookie
0x140054f36  mov     rsi, [rsp+0D8h+arg_18]
0x140054f3e  add     rsp, 0B0h
0x140054f45  pop     r15
0x140054f47  pop     r14
0x140054f49  pop     r13
0x140054f4b  pop     r12
0x140054f4d  pop     rdi
0x140054f4e  retn
```
