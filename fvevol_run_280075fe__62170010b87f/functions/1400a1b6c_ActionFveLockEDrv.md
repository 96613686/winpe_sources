# ActionFveLockEDrv

- ea: `0x1400a1b6c`
- end: `0x1400a1ecc`
- name: `ActionFveLockEDrv`
- size: `864`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14008964c`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x1400218c0`
- `0x140021d00`
- `0x140023a64`
- `0x1400241b4`
- `0x14002e334`
- `0x140030690`
- `0x140095190`
- `0x1400a1b6c`
- `0x1400b2dc4`
- `0x1400da590`
- `0x1400da8d4`
- `0x1400e3eec`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a1e30`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a1e30`
- `ntoskrnl!IoFreeMdl` at `0x1400a1e15`
- `ntoskrnl!IoFreeMdl` at `0x1400a1e15`
- `ntoskrnl!MmUnlockPages` at `0x1400a1e06`
- `ntoskrnl!MmUnlockPages` at `0x1400a1e06`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a1cea`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a1cea`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400a1cb2`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400a1cb2`
- `ntoskrnl!IoAllocateMdl` at `0x1400a1c84`
- `ntoskrnl!IoAllocateMdl` at `0x1400a1c84`
- `ntoskrnl!KeStackAttachProcess` at `0x1400a1c5d`
- `ntoskrnl!KeStackAttachProcess` at `0x1400a1c5d`

## pseudocode

```c
__int64 __fastcall ActionFveLockEDrv(int *Context, __int64 a2, __int64 a3)
{
  struct _MDL *v6; // rsi
  char v7; // r12
  struct _KPROCESS *v8; // r8
  char v9; // r13
  int v10; // ebx
  char v11; // r15
  void *v12; // rbx
  ULONG v13; // r15d
  struct _MDL *Mdl; // rax
  PVOID MappedSystemVa; // rbx
  int Irp; // [rsp+20h] [rbp-148h]
  char v18; // [rsp+51h] [rbp-117h]
  struct _KPROCESS *v19; // [rsp+58h] [rbp-110h]
  _BYTE v20[144]; // [rsp+70h] [rbp-F8h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+100h] [rbp-68h] BYREF

  memset(v20, 0, sizeof(v20));
  memset(&ApcState, 0, sizeof(ApcState));
  v6 = 0;
  v7 = 0;
  v8 = *(struct _KPROCESS **)(a2 + 120);
  v19 = v8;
  v9 = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_db10fbeca6e03e7325aab39114461952_Traceguids);
    v8 = v19;
  }
  if ( *(_WORD *)a3 != 24 )
  {
    v10 = -1073741811;
LABEL_7:
    v11 = 0;
    goto LABEL_23;
  }
  if ( Context[211] > 0 )
  {
    v10 = -2147483631;
    goto LABEL_7;
  }
  v12 = *(void **)(a3 + 8);
  v13 = *(_DWORD *)(a3 + 16);
  KeStackAttachProcess(v8, &ApcState);
  v18 = 1;
  Mdl = IoAllocateMdl(v12, v13, 0, 1u, 0);
  v6 = Mdl;
  if ( !Mdl )
  {
    v10 = -1073741670;
LABEL_12:
    v11 = v7;
    goto LABEL_23;
  }
  MmProbeAndLockPages(Mdl, 1, IoReadAccess);
  v7 = 1;
  if ( (v6->MdlFlags & 5) != 0 )
    MappedSystemVa = v6->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v6, 0, MmCached, 0, 0, 0x40000010u);
  if ( MappedSystemVa )
  {
    LOBYTE(v8) = 1;
    FvepAcquireDevFveLock(Context, v20, v8);
    if ( (Context[213] & 0x200) != 0 )
    {
      FveRundownAllReadsAndWrites((__int64)Context);
      v10 = SetBandSecurityInfo(Context, MappedSystemVa, v13, MappedSystemVa, v13, 0, 0, 1, 1);
      if ( v10 < 0 )
      {
        v9 = 1;
      }
      else
      {
        LOBYTE(Irp) = 1;
        SetFveStateEx(Context, 64, 0, 0, Irp, 52);
        Context[203] = -1071579136;
        FveCleanup(Context);
        FveResumeAllReadsAndWrites((__int64)Context);
        v9 = 0;
        FveRaiseStatusChangedEvent(Context, 7);
      }
    }
    else
    {
      v10 = -1073741811;
    }
    goto LABEL_12;
  }
  v10 = -1073741670;
  v11 = 0;
LABEL_23:
  if ( v6 )
  {
    if ( v7 )
      MmUnlockPages(v6);
    IoFreeMdl(v6);
  }
  if ( v18 )
    KeUnstackDetachProcess(&ApcState);
  if ( v9 )
    FveResumeAllReadsAndWrites((__int64)Context);
  LOBYTE(v8) = v11;
  FveTestDevStateChange(Context, 52, v8);
  if ( v11 )
    FvepReleaseDevFveLock(v20);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      112,
      WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400a1b6c  mov     [rsp+arg_18], rbx
0x1400a1b71  push    rsi
0x1400a1b72  push    r12
0x1400a1b74  push    r13
0x1400a1b76  push    r14
0x1400a1b78  push    r15
0x1400a1b7a  sub     rsp, 140h
0x1400a1b81  mov     rax, cs:__security_cookie
0x1400a1b88  xor     rax, rsp
0x1400a1b8b  mov     [rsp+168h+var_38], rax
0x1400a1b93  mov     r15, r8
0x1400a1b96  mov     rbx, rdx
0x1400a1b99  mov     r14, rcx
0x1400a1b9c  mov     [rsp+168h+var_108], rcx
0x1400a1ba1  xor     edx, edx; Val
0x1400a1ba3  mov     r8d, 90h; Size
0x1400a1ba9  lea     rcx, [rsp+168h+var_F8]; void *
0x1400a1bae  call    memset
0x1400a1bb3  xorps   xmm0, xmm0
0x1400a1bb6  movups  xmmword ptr [rsp+168h+ApcState.ApcListHead.Flink], xmm0
0x1400a1bbe  movups  xmmword ptr [rsp+168h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400a1bc6  movups  xmmword ptr [rsp+168h+ApcState.Process], xmm0
0x1400a1bce  xor     esi, esi
0x1400a1bd0  xor     r12b, r12b
0x1400a1bd3  mov     [rsp+168h+var_116], r12b
0x1400a1bd8  mov     r8, [rbx+78h]
0x1400a1bdc  mov     [rsp+168h+var_110], r8
0x1400a1be1  xor     r13b, r13b
0x1400a1be4  xor     al, al
0x1400a1be6  mov     [rsp+168h+var_118], al
0x1400a1bea  mov     [rsp+168h+var_117], al
0x1400a1bee  lea     rax, WPP_GLOBAL_Control
0x1400a1bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1bfc  cmp     rcx, rax
0x1400a1bff  jz      short loc_1400A1C26
0x1400a1c01  mov     eax, [rcx+2Ch]
0x1400a1c04  test    al, 1
0x1400a1c06  jz      short loc_1400A1C26
0x1400a1c08  cmp     byte ptr [rcx+29h], 5
0x1400a1c0c  jb      short loc_1400A1C26
0x1400a1c0e  lea     edx, [rsi+6Fh]
0x1400a1c11  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x1400a1c18  mov     rcx, [rcx+18h]
0x1400a1c1c  call    WPP_SF_
0x1400a1c21  mov     r8, [rsp+168h+var_110]
0x1400a1c26  cmp     word ptr [r15], 18h
0x1400a1c2b  jz      short loc_1400A1C3A
0x1400a1c2d  mov     ebx, 0C000000Dh
0x1400a1c32  mov     r15b, sil
0x1400a1c35  jmp     loc_1400A1DF9
0x1400a1c3a  cmp     [r14+34Ch], esi
0x1400a1c41  jle     short loc_1400A1C4A
0x1400a1c43  mov     ebx, 80000011h
0x1400a1c48  jmp     short loc_1400A1C32
0x1400a1c4a  mov     rbx, [r15+8]
0x1400a1c4e  mov     r15d, [r15+10h]
0x1400a1c52  lea     rdx, [rsp+168h+ApcState]; ApcState
0x1400a1c5a  mov     rcx, r8; PROCESS
0x1400a1c5d  call    cs:__imp_KeStackAttachProcess
0x1400a1c64  nop     dword ptr [rax+rax+00h]
0x1400a1c69  mov     al, 1
0x1400a1c6b  mov     [rsp+168h+var_117], al
0x1400a1c6f  mov     [rsp+168h+var_113], al
0x1400a1c73  mov     [rsp+168h+Irp], rsi; Irp
0x1400a1c78  mov     r9b, al; ChargeQuota
0x1400a1c7b  xor     r8d, r8d; SecondaryBuffer
0x1400a1c7e  mov     edx, r15d; Length
0x1400a1c81  mov     rcx, rbx; VirtualAddress
0x1400a1c84  call    cs:__imp_IoAllocateMdl
0x1400a1c8b  nop     dword ptr [rax+rax+00h]
0x1400a1c90  mov     rsi, rax
0x1400a1c93  mov     [rsp+168h+var_110], rax
0x1400a1c98  test    rax, rax
0x1400a1c9b  jnz     short loc_1400A1CAA
0x1400a1c9d  mov     ebx, 0C000009Ah
0x1400a1ca2  mov     r15b, r12b
0x1400a1ca5  jmp     loc_1400A1DF9
0x1400a1caa  xor     r8d, r8d; Operation
0x1400a1cad  mov     dl, 1; AccessMode
0x1400a1caf  mov     rcx, rsi; MemoryDescriptorList
0x1400a1cb2  call    cs:__imp_MmProbeAndLockPages
0x1400a1cb9  nop     dword ptr [rax+rax+00h]
0x1400a1cbe  nop
0x1400a1cbf  mov     r12b, 1
0x1400a1cc2  test    byte ptr [rsi+0Ah], 5
0x1400a1cc6  jz      short loc_1400A1CCE
0x1400a1cc8  mov     rbx, [rsi+18h]
0x1400a1ccc  jmp     short loc_1400A1CF9
0x1400a1cce  mov     [rsp+168h+Priority], 40000010h; Priority
0x1400a1cd6  mov     dword ptr [rsp+168h+Irp], 0; BugCheckOnFailure
0x1400a1cde  xor     r9d, r9d; RequestedAddress
0x1400a1ce1  xor     edx, edx; AccessMode
0x1400a1ce3  lea     r8d, [r9+1]; CacheType
0x1400a1ce7  mov     rcx, rsi; MemoryDescriptorList
0x1400a1cea  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400a1cf1  nop     dword ptr [rax+rax+00h]
0x1400a1cf6  mov     rbx, rax
0x1400a1cf9  test    rbx, rbx
0x1400a1cfc  jnz     short loc_1400A1D0D
0x1400a1cfe  mov     ebx, 0C000009Ah
0x1400a1d03  mov     r15b, [rsp+168h+var_118]
0x1400a1d08  jmp     loc_1400A1DF9
0x1400a1d0d  mov     r8b, r12b
0x1400a1d10  lea     rdx, [rsp+168h+var_F8]
0x1400a1d15  mov     rcx, r14
0x1400a1d18  call    FvepAcquireDevFveLock
0x1400a1d1d  test    dword ptr [r14+354h], 200h
0x1400a1d28  jnz     short loc_1400A1D34
0x1400a1d2a  mov     ebx, 0C000000Dh
0x1400a1d2f  jmp     loc_1400A1CA2
0x1400a1d34  mov     rcx, r14
0x1400a1d37  call    FveRundownAllReadsAndWrites
0x1400a1d3c  mov     [rsp+168h+var_128], r12b
0x1400a1d41  mov     [rsp+168h+var_130], r12b
0x1400a1d46  mov     [rsp+168h+var_138], 0
0x1400a1d4f  mov     qword ptr [rsp+168h+Priority], 0
0x1400a1d58  mov     dword ptr [rsp+168h+Irp], r15d
0x1400a1d5d  mov     r9, rbx
0x1400a1d60  mov     r8d, r15d
0x1400a1d63  mov     rdx, rbx
0x1400a1d66  mov     rcx, r14
0x1400a1d69  call    SetBandSecurityInfo
0x1400a1d6e  mov     ebx, eax
0x1400a1d70  test    eax, eax
0x1400a1d72  js      short loc_1400A1DCF
0x1400a1d74  mov     [rsp+168h+Priority], 34h ; '4'
0x1400a1d7c  mov     byte ptr [rsp+168h+Irp], r12b
0x1400a1d81  xor     r9d, r9d
0x1400a1d84  xor     r8d, r8d
0x1400a1d87  lea     edx, [r9+40h]
0x1400a1d8b  mov     rcx, r14
0x1400a1d8e  call    SetFveStateEx
0x1400a1d93  mov     dword ptr [r14+32Ch], 0C0210000h
0x1400a1d9e  mov     r9d, 34h ; '4'
0x1400a1da4  xor     r8d, r8d
0x1400a1da7  mov     dl, r12b
0x1400a1daa  mov     rcx, r14; Context
0x1400a1dad  call    FveCleanup
0x1400a1db2  mov     rcx, r14
0x1400a1db5  call    FveResumeAllReadsAndWrites
0x1400a1dba  xor     r13b, r13b
0x1400a1dbd  mov     edx, 7
0x1400a1dc2  mov     rcx, r14
0x1400a1dc5  call    FveRaiseStatusChangedEvent
0x1400a1dca  jmp     loc_1400A1CA2
0x1400a1dcf  mov     r13b, r12b
0x1400a1dd2  jmp     loc_1400A1CA2
0x1400a1dd7  mov     ebx, 0C000000Dh
0x1400a1ddc  mov     rsi, [rsp+168h+var_110]
0x1400a1de1  mov     r12b, [rsp+168h+var_116]
0x1400a1de6  mov     r13b, r12b
0x1400a1de9  mov     r15b, r12b
0x1400a1dec  mov     al, [rsp+168h+var_113]
0x1400a1df0  mov     [rsp+168h+var_117], al
0x1400a1df4  mov     r14, [rsp+168h+var_108]
0x1400a1df9  test    rsi, rsi
0x1400a1dfc  jz      short loc_1400A1E21
0x1400a1dfe  test    r12b, r12b
0x1400a1e01  jz      short loc_1400A1E12
0x1400a1e03  mov     rcx, rsi; MemoryDescriptorList
0x1400a1e06  call    cs:__imp_MmUnlockPages
0x1400a1e0d  nop     dword ptr [rax+rax+00h]
0x1400a1e12  mov     rcx, rsi; Mdl
0x1400a1e15  call    cs:__imp_IoFreeMdl
0x1400a1e1c  nop     dword ptr [rax+rax+00h]
0x1400a1e21  cmp     [rsp+168h+var_117], 0
0x1400a1e26  jz      short loc_1400A1E3C
0x1400a1e28  lea     rcx, [rsp+168h+ApcState]; ApcState
0x1400a1e30  call    cs:__imp_KeUnstackDetachProcess
0x1400a1e37  nop     dword ptr [rax+rax+00h]
0x1400a1e3c  test    r13b, r13b
0x1400a1e3f  jz      short loc_1400A1E49
0x1400a1e41  mov     rcx, r14
0x1400a1e44  call    FveResumeAllReadsAndWrites
0x1400a1e49  mov     r8b, r15b
0x1400a1e4c  mov     edx, 34h ; '4'
0x1400a1e51  mov     rcx, r14
0x1400a1e54  call    FveTestDevStateChange
0x1400a1e59  test    r15b, r15b
0x1400a1e5c  jz      short loc_1400A1E68
0x1400a1e5e  lea     rcx, [rsp+168h+var_F8]
0x1400a1e63  call    FvepReleaseDevFveLock
0x1400a1e68  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1e6f  lea     rax, WPP_GLOBAL_Control
0x1400a1e76  cmp     rcx, rax
0x1400a1e79  jz      short loc_1400A1EA0
0x1400a1e7b  mov     eax, [rcx+2Ch]
0x1400a1e7e  test    al, 1
0x1400a1e80  jz      short loc_1400A1EA0
0x1400a1e82  cmp     byte ptr [rcx+29h], 5
0x1400a1e86  jb      short loc_1400A1EA0
0x1400a1e88  mov     edx, 70h ; 'p'
0x1400a1e8d  mov     r9d, ebx
0x1400a1e90  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x1400a1e97  mov     rcx, [rcx+18h]
0x1400a1e9b  call    WPP_SF_d
0x1400a1ea0  mov     eax, ebx
0x1400a1ea2  mov     rcx, [rsp+168h+var_38]
0x1400a1eaa  xor     rcx, rsp; StackCookie
0x1400a1ead  call    __security_check_cookie
0x1400a1eb2  mov     rbx, [rsp+168h+arg_18]
0x1400a1eba  add     rsp, 140h
0x1400a1ec1  pop     r15
0x1400a1ec3  pop     r14
0x1400a1ec5  pop     r13
0x1400a1ec7  pop     r12
0x1400a1ec9  pop     rsi
0x1400a1eca  retn
```
