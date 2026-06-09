# DMABuffer::Init(uchar)

- ea: `0x180016a10`
- end: `0x180016bce`
- name: `?Init@DMABuffer@@QEAAJE@Z`
- size: `446`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003b730`
- `0x18003b7d0`

## callees

- `0x18000b7bc`
- `0x180016a10`
- `0x180016d98`
- `0x180016e8c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180016b19`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180016b19`
- `ntoskrnl!MmAllocatePagesForMdl` at `0x180016ad0`
- `ntoskrnl!MmAllocatePagesForMdl` at `0x180016ad0`
- `ntoskrnl!KeInitializeSpinLock` at `0x180016a63`
- `ntoskrnl!KeInitializeSpinLock` at `0x180016a63`

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
0x180016a10  push    rbx
0x180016a12  push    rbp
0x180016a13  push    rsi
0x180016a14  push    rdi
0x180016a15  push    r12
0x180016a17  push    r14
0x180016a19  sub     rsp, 48h
0x180016a1d  mov     bl, dl
0x180016a1f  mov     rsi, rcx
0x180016a22  lea     r14, WPP_RECORDER_INITIALIZED
0x180016a29  xor     ebp, ebp
0x180016a2b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016a32  lea     r12, WPP_8d03f3cebf6b3270dc662b593865d526_Traceguids
0x180016a39  jz      short loc_180016A60
0x180016a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a42  cmp     [rcx+48h], bp
0x180016a46  jz      short loc_180016A60
0x180016a48  mov     rcx, [rcx+40h]
0x180016a4c  lea     r9d, [rbp+11h]
0x180016a50  xor     edx, edx
0x180016a52  mov     qword ptr [rsp+78h+BugCheckOnFailure], r12
0x180016a57  lea     r8d, [rbp+3]
0x180016a5b  call    WPP_RECORDER_SF_
0x180016a60  mov     rcx, rsi; SpinLock
0x180016a63  call    cs:__imp_KeInitializeSpinLock
0x180016a6a  nop     dword ptr [rax+rax+00h]
0x180016a6f  mov     [rsi+5Ch], bl
0x180016a72  test    bl, bl
0x180016a74  jz      loc_180016BBE
0x180016a7a  mov     ebx, 0FFFFFFFFh
0x180016a7f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016a86  jz      short loc_180016AC1
0x180016a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a8f  cmp     [rcx+48h], bp
0x180016a93  jz      short loc_180016AC1
0x180016a95  mov     rcx, [rcx+40h]
0x180016a99  mov     r9d, 12h
0x180016a9f  mov     dword ptr [rsp+78h+var_40], 200000h
0x180016aa7  xor     edx, edx
0x180016aa9  mov     [rsp+78h+var_48], rbx
0x180016aae  mov     qword ptr [rsp+78h+Priority], rbp
0x180016ab3  lea     r8d, [r9-0Fh]
0x180016ab7  mov     qword ptr [rsp+78h+BugCheckOnFailure], r12
0x180016abc  call    WPP_RECORDER_SF_iiD
0x180016ac1  mov     r9d, 200000h; TotalBytes
0x180016ac7  mov     r8, rbp; SkipBytes
0x180016aca  mov     rdx, rbx; HighAddress
0x180016acd  mov     rcx, rbp; LowAddress
0x180016ad0  call    cs:__imp_MmAllocatePagesForMdl
0x180016ad7  nop     dword ptr [rax+rax+00h]
0x180016adc  mov     [rsi+10h], rax
0x180016ae0  test    rax, rax
0x180016ae3  jnz     short loc_180016B01
0x180016ae5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016aec  jz      short loc_180016B5E
0x180016aee  mov     rcx, cs:WPP_GLOBAL_Control
0x180016af5  cmp     [rcx+48h], bp
0x180016af9  jz      short loc_180016B5E
0x180016afb  lea     r9d, [rax+13h]
0x180016aff  jmp     short loc_180016B48
0x180016b01  xor     r9d, r9d; RequestedAddress
0x180016b04  mov     [rsp+78h+Priority], 40000020h; Priority
0x180016b0c  xor     edx, edx; AccessMode
0x180016b0e  mov     [rsp+78h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x180016b12  mov     rcx, rax; MemoryDescriptorList
0x180016b15  lea     r8d, [r9+1]; CacheType
0x180016b19  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180016b20  nop     dword ptr [rax+rax+00h]
0x180016b25  mov     [rsi+8], rax
0x180016b29  test    rax, rax
0x180016b2c  jnz     short loc_180016B65
0x180016b2e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016b35  jz      short loc_180016B5E
0x180016b37  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b3e  cmp     [rcx+48h], bp
0x180016b42  jz      short loc_180016B5E
0x180016b44  lea     r9d, [rax+14h]
0x180016b48  mov     rcx, [rcx+40h]
0x180016b4c  mov     r8d, 3
0x180016b52  xor     edx, edx
0x180016b54  mov     qword ptr [rsp+78h+BugCheckOnFailure], r12
0x180016b59  call    WPP_RECORDER_SF_
0x180016b5e  mov     eax, 0C000009Ah
0x180016b63  jmp     short loc_180016BC0
0x180016b65  mov     ecx, [rsi+8]
0x180016b68  mov     r10, [rsi+10h]
0x180016b6c  and     ecx, 0FFFh
0x180016b72  mov     edx, [r10+28h]
0x180016b76  add     rdx, 0FFFh
0x180016b7d  add     rdx, rcx
0x180016b80  shr     rdx, 0Ch
0x180016b84  mov     [rsi+58h], edx
0x180016b87  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180016b8e  jz      short loc_180016BBA
0x180016b90  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b97  cmp     [rcx+48h], bp
0x180016b9b  jz      short loc_180016BBA
0x180016b9d  mov     rcx, [rcx+40h]
0x180016ba1  mov     r9d, 15h
0x180016ba7  mov     [rsp+78h+var_40], r10
0x180016bac  mov     [rsp+78h+var_48], rax
0x180016bb1  mov     [rsp+78h+Priority], edx
0x180016bb5  call    WPP_RECORDER_SF_Dqq
0x180016bba  mov     [rsi+5Ch], bpl
0x180016bbe  xor     eax, eax
0x180016bc0  add     rsp, 48h
0x180016bc4  pop     r14
0x180016bc6  pop     r12
0x180016bc8  pop     rdi
0x180016bc9  pop     rsi
0x180016bca  pop     rbp
0x180016bcb  pop     rbx
0x180016bcc  retn
```
