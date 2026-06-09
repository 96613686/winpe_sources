# ActionFveLockEDrv

- ea: `0x1400a2ab8`
- end: `0x1400a2e18`
- name: `ActionFveLockEDrv`
- size: `864`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14008b6ec`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140022bf0`
- `0x140023040`
- `0x140024a64`
- `0x1400251b4`
- `0x14002f334`
- `0x140031690`
- `0x140097240`
- `0x1400a2ab8`
- `0x1400b404c`
- `0x1400dce00`
- `0x1400dd144`
- `0x1400e6aa4`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a2d7c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a2d7c`
- `ntoskrnl!IoFreeMdl` at `0x1400a2d61`
- `ntoskrnl!IoFreeMdl` at `0x1400a2d61`
- `ntoskrnl!MmUnlockPages` at `0x1400a2d52`
- `ntoskrnl!MmUnlockPages` at `0x1400a2d52`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a2c36`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a2c36`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400a2bfe`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400a2bfe`
- `ntoskrnl!IoAllocateMdl` at `0x1400a2bd0`
- `ntoskrnl!IoAllocateMdl` at `0x1400a2bd0`
- `ntoskrnl!KeStackAttachProcess` at `0x1400a2ba9`
- `ntoskrnl!KeStackAttachProcess` at `0x1400a2ba9`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids);
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
      WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
      (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400a2ab8  mov     [rsp+arg_18], rbx
0x1400a2abd  push    rsi
0x1400a2abe  push    r12
0x1400a2ac0  push    r13
0x1400a2ac2  push    r14
0x1400a2ac4  push    r15
0x1400a2ac6  sub     rsp, 140h
0x1400a2acd  mov     rax, cs:__security_cookie
0x1400a2ad4  xor     rax, rsp
0x1400a2ad7  mov     [rsp+168h+var_38], rax
0x1400a2adf  mov     r15, r8
0x1400a2ae2  mov     rbx, rdx
0x1400a2ae5  mov     r14, rcx
0x1400a2ae8  mov     [rsp+168h+var_108], rcx
0x1400a2aed  xor     edx, edx; Val
0x1400a2aef  mov     r8d, 90h; Size
0x1400a2af5  lea     rcx, [rsp+168h+var_F8]; void *
0x1400a2afa  call    memset
0x1400a2aff  xorps   xmm0, xmm0
0x1400a2b02  movups  xmmword ptr [rsp+168h+ApcState.ApcListHead.Flink], xmm0
0x1400a2b0a  movups  xmmword ptr [rsp+168h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400a2b12  movups  xmmword ptr [rsp+168h+ApcState.Process], xmm0
0x1400a2b1a  xor     esi, esi
0x1400a2b1c  xor     r12b, r12b
0x1400a2b1f  mov     [rsp+168h+var_116], r12b
0x1400a2b24  mov     r8, [rbx+78h]
0x1400a2b28  mov     [rsp+168h+var_110], r8
0x1400a2b2d  xor     r13b, r13b
0x1400a2b30  xor     al, al
0x1400a2b32  mov     [rsp+168h+var_118], al
0x1400a2b36  mov     [rsp+168h+var_117], al
0x1400a2b3a  lea     rax, WPP_GLOBAL_Control
0x1400a2b41  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2b48  cmp     rcx, rax
0x1400a2b4b  jz      short loc_1400A2B72
0x1400a2b4d  mov     eax, [rcx+2Ch]
0x1400a2b50  test    al, 1
0x1400a2b52  jz      short loc_1400A2B72
0x1400a2b54  cmp     byte ptr [rcx+29h], 5
0x1400a2b58  jb      short loc_1400A2B72
0x1400a2b5a  lea     edx, [rsi+6Fh]
0x1400a2b5d  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x1400a2b64  mov     rcx, [rcx+18h]
0x1400a2b68  call    WPP_SF_
0x1400a2b6d  mov     r8, [rsp+168h+var_110]
0x1400a2b72  cmp     word ptr [r15], 18h
0x1400a2b77  jz      short loc_1400A2B86
0x1400a2b79  mov     ebx, 0C000000Dh
0x1400a2b7e  mov     r15b, sil
0x1400a2b81  jmp     loc_1400A2D45
0x1400a2b86  cmp     [r14+34Ch], esi
0x1400a2b8d  jle     short loc_1400A2B96
0x1400a2b8f  mov     ebx, 80000011h
0x1400a2b94  jmp     short loc_1400A2B7E
0x1400a2b96  mov     rbx, [r15+8]
0x1400a2b9a  mov     r15d, [r15+10h]
0x1400a2b9e  lea     rdx, [rsp+168h+ApcState]; ApcState
0x1400a2ba6  mov     rcx, r8; PROCESS
0x1400a2ba9  call    cs:__imp_KeStackAttachProcess
0x1400a2bb0  nop     dword ptr [rax+rax+00h]
0x1400a2bb5  mov     al, 1
0x1400a2bb7  mov     [rsp+168h+var_117], al
0x1400a2bbb  mov     [rsp+168h+var_113], al
0x1400a2bbf  mov     [rsp+168h+Irp], rsi; Irp
0x1400a2bc4  mov     r9b, al; ChargeQuota
0x1400a2bc7  xor     r8d, r8d; SecondaryBuffer
0x1400a2bca  mov     edx, r15d; Length
0x1400a2bcd  mov     rcx, rbx; VirtualAddress
0x1400a2bd0  call    cs:__imp_IoAllocateMdl
0x1400a2bd7  nop     dword ptr [rax+rax+00h]
0x1400a2bdc  mov     rsi, rax
0x1400a2bdf  mov     [rsp+168h+var_110], rax
0x1400a2be4  test    rax, rax
0x1400a2be7  jnz     short loc_1400A2BF6
0x1400a2be9  mov     ebx, 0C000009Ah
0x1400a2bee  mov     r15b, r12b
0x1400a2bf1  jmp     loc_1400A2D45
0x1400a2bf6  xor     r8d, r8d; Operation
0x1400a2bf9  mov     dl, 1; AccessMode
0x1400a2bfb  mov     rcx, rsi; MemoryDescriptorList
0x1400a2bfe  call    cs:__imp_MmProbeAndLockPages
0x1400a2c05  nop     dword ptr [rax+rax+00h]
0x1400a2c0a  nop
0x1400a2c0b  mov     r12b, 1
0x1400a2c0e  test    byte ptr [rsi+0Ah], 5
0x1400a2c12  jz      short loc_1400A2C1A
0x1400a2c14  mov     rbx, [rsi+18h]
0x1400a2c18  jmp     short loc_1400A2C45
0x1400a2c1a  mov     [rsp+168h+Priority], 40000010h; Priority
0x1400a2c22  mov     dword ptr [rsp+168h+Irp], 0; BugCheckOnFailure
0x1400a2c2a  xor     r9d, r9d; RequestedAddress
0x1400a2c2d  xor     edx, edx; AccessMode
0x1400a2c2f  lea     r8d, [r9+1]; CacheType
0x1400a2c33  mov     rcx, rsi; MemoryDescriptorList
0x1400a2c36  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400a2c3d  nop     dword ptr [rax+rax+00h]
0x1400a2c42  mov     rbx, rax
0x1400a2c45  test    rbx, rbx
0x1400a2c48  jnz     short loc_1400A2C59
0x1400a2c4a  mov     ebx, 0C000009Ah
0x1400a2c4f  mov     r15b, [rsp+168h+var_118]
0x1400a2c54  jmp     loc_1400A2D45
0x1400a2c59  mov     r8b, r12b
0x1400a2c5c  lea     rdx, [rsp+168h+var_F8]
0x1400a2c61  mov     rcx, r14
0x1400a2c64  call    FvepAcquireDevFveLock
0x1400a2c69  test    dword ptr [r14+354h], 200h
0x1400a2c74  jnz     short loc_1400A2C80
0x1400a2c76  mov     ebx, 0C000000Dh
0x1400a2c7b  jmp     loc_1400A2BEE
0x1400a2c80  mov     rcx, r14
0x1400a2c83  call    FveRundownAllReadsAndWrites
0x1400a2c88  mov     [rsp+168h+var_128], r12b
0x1400a2c8d  mov     [rsp+168h+var_130], r12b
0x1400a2c92  mov     [rsp+168h+var_138], 0
0x1400a2c9b  mov     qword ptr [rsp+168h+Priority], 0
0x1400a2ca4  mov     dword ptr [rsp+168h+Irp], r15d
0x1400a2ca9  mov     r9, rbx
0x1400a2cac  mov     r8d, r15d
0x1400a2caf  mov     rdx, rbx
0x1400a2cb2  mov     rcx, r14
0x1400a2cb5  call    SetBandSecurityInfo
0x1400a2cba  mov     ebx, eax
0x1400a2cbc  test    eax, eax
0x1400a2cbe  js      short loc_1400A2D1B
0x1400a2cc0  mov     [rsp+168h+Priority], 34h ; '4'
0x1400a2cc8  mov     byte ptr [rsp+168h+Irp], r12b
0x1400a2ccd  xor     r9d, r9d
0x1400a2cd0  xor     r8d, r8d
0x1400a2cd3  lea     edx, [r9+40h]
0x1400a2cd7  mov     rcx, r14
0x1400a2cda  call    SetFveStateEx
0x1400a2cdf  mov     dword ptr [r14+32Ch], 0C0210000h
0x1400a2cea  mov     r9d, 34h ; '4'
0x1400a2cf0  xor     r8d, r8d
0x1400a2cf3  mov     dl, r12b
0x1400a2cf6  mov     rcx, r14; Context
0x1400a2cf9  call    FveCleanup
0x1400a2cfe  mov     rcx, r14
0x1400a2d01  call    FveResumeAllReadsAndWrites
0x1400a2d06  xor     r13b, r13b
0x1400a2d09  mov     edx, 7
0x1400a2d0e  mov     rcx, r14
0x1400a2d11  call    FveRaiseStatusChangedEvent
0x1400a2d16  jmp     loc_1400A2BEE
0x1400a2d1b  mov     r13b, r12b
0x1400a2d1e  jmp     loc_1400A2BEE
0x1400a2d23  mov     ebx, 0C000000Dh
0x1400a2d28  mov     rsi, [rsp+168h+var_110]
0x1400a2d2d  mov     r12b, [rsp+168h+var_116]
0x1400a2d32  mov     r13b, r12b
0x1400a2d35  mov     r15b, r12b
0x1400a2d38  mov     al, [rsp+168h+var_113]
0x1400a2d3c  mov     [rsp+168h+var_117], al
0x1400a2d40  mov     r14, [rsp+168h+var_108]
0x1400a2d45  test    rsi, rsi
0x1400a2d48  jz      short loc_1400A2D6D
0x1400a2d4a  test    r12b, r12b
0x1400a2d4d  jz      short loc_1400A2D5E
0x1400a2d4f  mov     rcx, rsi; MemoryDescriptorList
0x1400a2d52  call    cs:__imp_MmUnlockPages
0x1400a2d59  nop     dword ptr [rax+rax+00h]
0x1400a2d5e  mov     rcx, rsi; Mdl
0x1400a2d61  call    cs:__imp_IoFreeMdl
0x1400a2d68  nop     dword ptr [rax+rax+00h]
0x1400a2d6d  cmp     [rsp+168h+var_117], 0
0x1400a2d72  jz      short loc_1400A2D88
0x1400a2d74  lea     rcx, [rsp+168h+ApcState]; ApcState
0x1400a2d7c  call    cs:__imp_KeUnstackDetachProcess
0x1400a2d83  nop     dword ptr [rax+rax+00h]
0x1400a2d88  test    r13b, r13b
0x1400a2d8b  jz      short loc_1400A2D95
0x1400a2d8d  mov     rcx, r14
0x1400a2d90  call    FveResumeAllReadsAndWrites
0x1400a2d95  mov     r8b, r15b
0x1400a2d98  mov     edx, 34h ; '4'
0x1400a2d9d  mov     rcx, r14
0x1400a2da0  call    FveTestDevStateChange
0x1400a2da5  test    r15b, r15b
0x1400a2da8  jz      short loc_1400A2DB4
0x1400a2daa  lea     rcx, [rsp+168h+var_F8]
0x1400a2daf  call    FvepReleaseDevFveLock
0x1400a2db4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2dbb  lea     rax, WPP_GLOBAL_Control
0x1400a2dc2  cmp     rcx, rax
0x1400a2dc5  jz      short loc_1400A2DEC
0x1400a2dc7  mov     eax, [rcx+2Ch]
0x1400a2dca  test    al, 1
0x1400a2dcc  jz      short loc_1400A2DEC
0x1400a2dce  cmp     byte ptr [rcx+29h], 5
0x1400a2dd2  jb      short loc_1400A2DEC
0x1400a2dd4  mov     edx, 70h ; 'p'
0x1400a2dd9  mov     r9d, ebx
0x1400a2ddc  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x1400a2de3  mov     rcx, [rcx+18h]
0x1400a2de7  call    WPP_SF_d
0x1400a2dec  mov     eax, ebx
0x1400a2dee  mov     rcx, [rsp+168h+var_38]
0x1400a2df6  xor     rcx, rsp; StackCookie
0x1400a2df9  call    __security_check_cookie
0x1400a2dfe  mov     rbx, [rsp+168h+arg_18]
0x1400a2e06  add     rsp, 140h
0x1400a2e0d  pop     r15
0x1400a2e0f  pop     r14
0x1400a2e11  pop     r13
0x1400a2e13  pop     r12
0x1400a2e15  pop     rsi
0x1400a2e16  retn
```
