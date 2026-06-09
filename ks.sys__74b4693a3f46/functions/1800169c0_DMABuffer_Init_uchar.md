# DMABuffer::Init(uchar)

- ea: `0x1800169c0`
- end: `0x180016b7e`
- name: `?Init@DMABuffer@@QEAAJE@Z`
- size: `446`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003b740`
- `0x18003b7e0`

## callees

- `0x18000b7bc`
- `0x1800169c0`
- `0x180016d48`
- `0x180016e3c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180016ac9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180016ac9`
- `ntoskrnl!MmAllocatePagesForMdl` at `0x180016a80`
- `ntoskrnl!MmAllocatePagesForMdl` at `0x180016a80`
- `ntoskrnl!KeInitializeSpinLock` at `0x180016a13`
- `ntoskrnl!KeInitializeSpinLock` at `0x180016a13`

## pseudocode

```c
__int64 __fastcall DMABuffer::Init(PKSPIN_LOCK SpinLock, char a2)
{
  struct _MDL *PagesForMdl; // rax
  PDEVICE_OBJECT v5; // rcx
  int v6; // r9d
  PVOID v7; // rax
  int v8; // r8d
  KSPIN_LOCK v10; // r10
  KSPIN_LOCK v11; // rdx
  int BugCheckOnFailure; // [rsp+20h] [rbp-58h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      3,
      17,
      (__int64)WPP_8d03f3cebf6b3270dc662b593865d526_Traceguids);
  KeInitializeSpinLock(SpinLock);
  *((_BYTE *)SpinLock + 92) = a2;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_iiD(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        3,
        18,
        (__int64)WPP_8d03f3cebf6b3270dc662b593865d526_Traceguids,
        0,
        -1,
        0);
    PagesForMdl = MmAllocatePagesForMdl(0, (PHYSICAL_ADDRESS)0xFFFFFFFFLL, 0, 0x200000u);
    SpinLock[2] = (KSPIN_LOCK)PagesForMdl;
    if ( !PagesForMdl )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 3221225626LL;
      v5 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        return 3221225626LL;
      v6 = 19;
LABEL_16:
      WPP_RECORDER_SF_(v5->DeviceExtension, 0, 3, v6, (__int64)WPP_8d03f3cebf6b3270dc662b593865d526_Traceguids);
      return 3221225626LL;
    }
    v7 = MmMapLockedPagesSpecifyCache(PagesForMdl, 0, MmCached, 0, 0, 0x40000020u);
    SpinLock[1] = (KSPIN_LOCK)v7;
    if ( !v7 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 3221225626LL;
      v5 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        return 3221225626LL;
      v6 = 20;
      goto LABEL_16;
    }
    v10 = SpinLock[2];
    v11 = ((SpinLock[1] & 0xFFF) + (unsigned __int64)*(unsigned int *)(v10 + 40) + 4095) >> 12;
    *((_DWORD *)SpinLock + 22) = v11;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_Dqq(WPP_GLOBAL_Control->DeviceExtension, v11, v8, 21, BugCheckOnFailure, v11, (char)v7, v10);
    *((_BYTE *)SpinLock + 92) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800169c0  push    rbx
0x1800169c2  push    rbp
0x1800169c3  push    rsi
0x1800169c4  push    rdi
0x1800169c5  push    r12
0x1800169c7  push    r14
0x1800169c9  sub     rsp, 48h
0x1800169cd  mov     bl, dl
0x1800169cf  mov     rsi, rcx
0x1800169d2  lea     r14, WPP_RECORDER_INITIALIZED
0x1800169d9  xor     ebp, ebp
0x1800169db  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800169e2  lea     r12, WPP_8d03f3cebf6b3270dc662b593865d526_Traceguids
0x1800169e9  jz      short loc_180016A10
0x1800169eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169f2  cmp     [rcx+48h], bp
0x1800169f6  jz      short loc_180016A10
0x1800169f8  mov     rcx, [rcx+40h]
0x1800169fc  lea     r9d, [rbp+11h]
0x180016a00  xor     edx, edx
0x180016a02  mov     qword ptr [rsp+78h+BugCheckOnFailure], r12
0x180016a07  lea     r8d, [rbp+3]
0x180016a0b  call    WPP_RECORDER_SF_
0x180016a10  mov     rcx, rsi; SpinLock
0x180016a13  call    cs:__imp_KeInitializeSpinLock
0x180016a1a  nop     dword ptr [rax+rax+00h]
0x180016a1f  mov     [rsi+5Ch], bl
0x180016a22  test    bl, bl
0x180016a24  jz      loc_180016B6E
0x180016a2a  mov     ebx, 0FFFFFFFFh
0x180016a2f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016a36  jz      short loc_180016A71
0x180016a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a3f  cmp     [rcx+48h], bp
0x180016a43  jz      short loc_180016A71
0x180016a45  mov     rcx, [rcx+40h]
0x180016a49  mov     r9d, 12h
0x180016a4f  mov     dword ptr [rsp+78h+var_40], 200000h
0x180016a57  xor     edx, edx
0x180016a59  mov     [rsp+78h+var_48], rbx
0x180016a5e  mov     qword ptr [rsp+78h+Priority], rbp
0x180016a63  lea     r8d, [r9-0Fh]
0x180016a67  mov     qword ptr [rsp+78h+BugCheckOnFailure], r12
0x180016a6c  call    WPP_RECORDER_SF_iiD
0x180016a71  mov     r9d, 200000h; TotalBytes
0x180016a77  mov     r8, rbp; SkipBytes
0x180016a7a  mov     rdx, rbx; HighAddress
0x180016a7d  mov     rcx, rbp; LowAddress
0x180016a80  call    cs:__imp_MmAllocatePagesForMdl
0x180016a87  nop     dword ptr [rax+rax+00h]
0x180016a8c  mov     [rsi+10h], rax
0x180016a90  test    rax, rax
0x180016a93  jnz     short loc_180016AB1
0x180016a95  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016a9c  jz      short loc_180016B0E
0x180016a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016aa5  cmp     [rcx+48h], bp
0x180016aa9  jz      short loc_180016B0E
0x180016aab  lea     r9d, [rax+13h]
0x180016aaf  jmp     short loc_180016AF8
0x180016ab1  xor     r9d, r9d; RequestedAddress
0x180016ab4  mov     [rsp+78h+Priority], 40000020h; Priority
0x180016abc  xor     edx, edx; AccessMode
0x180016abe  mov     [rsp+78h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x180016ac2  mov     rcx, rax; MemoryDescriptorList
0x180016ac5  lea     r8d, [r9+1]; CacheType
0x180016ac9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180016ad0  nop     dword ptr [rax+rax+00h]
0x180016ad5  mov     [rsi+8], rax
0x180016ad9  test    rax, rax
0x180016adc  jnz     short loc_180016B15
0x180016ade  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016ae5  jz      short loc_180016B0E
0x180016ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016aee  cmp     [rcx+48h], bp
0x180016af2  jz      short loc_180016B0E
0x180016af4  lea     r9d, [rax+14h]
0x180016af8  mov     rcx, [rcx+40h]
0x180016afc  mov     r8d, 3
0x180016b02  xor     edx, edx
0x180016b04  mov     qword ptr [rsp+78h+BugCheckOnFailure], r12
0x180016b09  call    WPP_RECORDER_SF_
0x180016b0e  mov     eax, 0C000009Ah
0x180016b13  jmp     short loc_180016B70
0x180016b15  mov     ecx, [rsi+8]
0x180016b18  mov     r10, [rsi+10h]
0x180016b1c  and     ecx, 0FFFh
0x180016b22  mov     edx, [r10+28h]
0x180016b26  add     rdx, 0FFFh
0x180016b2d  add     rdx, rcx
0x180016b30  shr     rdx, 0Ch
0x180016b34  mov     [rsi+58h], edx
0x180016b37  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016b3e  jz      short loc_180016B6A
0x180016b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b47  cmp     [rcx+48h], bp
0x180016b4b  jz      short loc_180016B6A
0x180016b4d  mov     rcx, [rcx+40h]
0x180016b51  mov     r9d, 15h
0x180016b57  mov     [rsp+78h+var_40], r10
0x180016b5c  mov     [rsp+78h+var_48], rax
0x180016b61  mov     [rsp+78h+Priority], edx
0x180016b65  call    WPP_RECORDER_SF_Dqq
0x180016b6a  mov     [rsi+5Ch], bpl
0x180016b6e  xor     eax, eax
0x180016b70  add     rsp, 48h
0x180016b74  pop     r14
0x180016b76  pop     r12
0x180016b78  pop     rdi
0x180016b79  pop     rsi
0x180016b7a  pop     rbp
0x180016b7b  pop     rbx
0x180016b7c  retn
```
