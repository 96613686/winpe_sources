# HbEvtpMapSystemDiagLogBuffer

- ea: `0x140012abc`
- end: `0x140012c36`
- name: `HbEvtpMapSystemDiagLogBuffer`
- size: `378`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140011760`

## callees

- `0x140001600`
- `0x1400105d4`
- `0x140011128`
- `0x140012abc`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012bda`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012bda`
- `winhvr!WinHvMapEventLogBuffer` at `0x140012b23`
- `winhvr!WinHvMapEventLogBuffer` at `0x140012b23`
- `winhvr!WinHvUnmapEventLogBuffer` at `0x140012c11`
- `winhvr!WinHvUnmapEventLogBuffer` at `0x140012c11`
- `winhvr!WinHvMapPartitionEventLogBuffer` at `0x140012b8b`
- `winhvr!WinHvMapPartitionEventLogBuffer` at `0x140012b8b`

## string_xrefs

- `0x140012bee`: `MmMapLockedPagesSpecifyCache failed`

## pseudocode

```c
__int64 __fastcall HbEvtpMapSystemDiagLogBuffer(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbp
  PMDL *v3; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  PVOID v9; // rax
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF

  v2 = a2;
  v3 = (PMDL *)(a1 + 8);
  v11 = 0;
  v5 = HbEvtpAllocateAndInitializeEventLogMdl(a2, a1 + 8);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( byte_140009048 )
    {
      v7 = WinHvMapEventLogBuffer(2, *(unsigned int *)(a1 + 84), &(*v3)[1]);
      v6 = v7;
      if ( v7 < 0 )
      {
        HbpTraceEvent(0, "HbEvtpMapSystemDiagLogBuffer", 5397, "0x%x - WinHvMapEventLogBuffer failed", v7);
        goto LABEL_12;
      }
    }
    else
    {
      if ( (unsigned int)v2 > 0x1FE )
      {
        v6 = -1073741811;
        goto LABEL_12;
      }
      v8 = WinHvMapPartitionEventLogBuffer(2, *(unsigned int *)(a1 + 84), v2, &(*v3)[1], &v11);
      v6 = v8;
      if ( v8 < 0 )
      {
        HbpTraceEvent(0, "HbEvtpMapSystemDiagLogBuffer", 5417, "0x%x - WinHvMapPartitionEventLogBuffer failed", v8);
        goto LABEL_12;
      }
    }
    v9 = MmMapLockedPagesSpecifyCache(*v3, 0, MmCached, 0, 0, 0x40000020u);
    *(_QWORD *)a1 = v9;
    if ( v9 )
      return v6;
    HbpTraceEvent(0, "HbEvtpMapSystemDiagLogBuffer", 5438, "MmMapLockedPagesSpecifyCache failed");
    WinHvUnmapEventLogBuffer(2, *(unsigned int *)(a1 + 84));
    v6 = -1073741670;
LABEL_12:
    HbEvtpFreeEventLogMdl(v3);
    return v6;
  }
  HbpTraceEvent(0, "HbEvtpMapSystemDiagLogBuffer", 5380, "0x%x - HbEvtpAllocateAndInitializeEventLogMdl failed", v5);
  return v6;
}

```

## disassembly

```asm
0x140012abc  push    rbx
0x140012abe  push    rbp
0x140012abf  push    rsi
0x140012ac0  push    rdi
0x140012ac1  sub     rsp, 38h
0x140012ac5  mov     ebp, edx
0x140012ac7  lea     rdi, [rcx+8]
0x140012acb  mov     rsi, rcx
0x140012ace  mov     [rsp+58h+arg_0], 0
0x140012ad7  mov     rdx, rdi
0x140012ada  mov     ecx, ebp
0x140012adc  call    HbEvtpAllocateAndInitializeEventLogMdl
0x140012ae1  mov     ebx, eax
0x140012ae3  test    eax, eax
0x140012ae5  jns     short loc_140012B0B
0x140012ae7  lea     r9, a0xXHbevtpalloc; "0x%x - HbEvtpAllocateAndInitializeEvent"...
0x140012aee  mov     [rsp+58h+BugCheckOnFailure], eax
0x140012af2  mov     r8d, 1504h
0x140012af8  lea     rdx, aHbevtpmapsyste; "HbEvtpMapSystemDiagLogBuffer"
0x140012aff  xor     ecx, ecx
0x140012b01  call    HbpTraceEvent
0x140012b06  jmp     loc_140012C2A
0x140012b0b  cmp     cs:byte_140009048, 0
0x140012b12  jz      short loc_140012B5D
0x140012b14  mov     r8, [rdi]
0x140012b17  mov     ecx, 2
0x140012b1c  mov     edx, [rsi+54h]
0x140012b1f  add     r8, 30h ; '0'
0x140012b23  call    cs:__imp_WinHvMapEventLogBuffer
0x140012b2a  nop     dword ptr [rax+rax+00h]
0x140012b2f  mov     ebx, eax
0x140012b31  test    eax, eax
0x140012b33  jns     loc_140012BBE
0x140012b39  lea     r9, a0xXWinhvmapeve; "0x%x - WinHvMapEventLogBuffer failed"
0x140012b40  mov     [rsp+58h+BugCheckOnFailure], eax
0x140012b44  mov     r8d, 1515h
0x140012b4a  lea     rdx, aHbevtpmapsyste; "HbEvtpMapSystemDiagLogBuffer"
0x140012b51  xor     ecx, ecx
0x140012b53  call    HbpTraceEvent
0x140012b58  jmp     loc_140012C22
0x140012b5d  cmp     ebp, 1FEh
0x140012b63  jbe     short loc_140012B6F
0x140012b65  mov     ebx, 0C000000Dh
0x140012b6a  jmp     loc_140012C22
0x140012b6f  mov     r9, [rdi]
0x140012b72  lea     rax, [rsp+58h+arg_0]
0x140012b77  mov     edx, [rsi+54h]
0x140012b7a  add     r9, 30h ; '0'
0x140012b7e  mov     r8, rbp
0x140012b81  mov     qword ptr [rsp+58h+BugCheckOnFailure], rax
0x140012b86  mov     ecx, 2
0x140012b8b  call    cs:__imp_WinHvMapPartitionEventLogBuffer
0x140012b92  nop     dword ptr [rax+rax+00h]
0x140012b97  mov     ebx, eax
0x140012b99  test    eax, eax
0x140012b9b  jns     short loc_140012BBE
0x140012b9d  lea     r9, a0xXWinhvmappar; "0x%x - WinHvMapPartitionEventLogBuffer "...
0x140012ba4  mov     [rsp+58h+BugCheckOnFailure], eax
0x140012ba8  mov     r8d, 1529h
0x140012bae  lea     rdx, aHbevtpmapsyste; "HbEvtpMapSystemDiagLogBuffer"
0x140012bb5  xor     ecx, ecx
0x140012bb7  call    HbpTraceEvent
0x140012bbc  jmp     short loc_140012C22
0x140012bbe  mov     rcx, [rdi]; MemoryDescriptorList
0x140012bc1  xor     r9d, r9d; RequestedAddress
0x140012bc4  mov     [rsp+58h+Priority], 40000020h; Priority
0x140012bcc  xor     edx, edx; AccessMode
0x140012bce  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140012bd6  lea     r8d, [r9+1]; CacheType
0x140012bda  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012be1  nop     dword ptr [rax+rax+00h]
0x140012be6  mov     [rsi], rax
0x140012be9  test    rax, rax
0x140012bec  jnz     short loc_140012C2A
0x140012bee  lea     r9, aMmmaplockedpag; "MmMapLockedPagesSpecifyCache failed"
0x140012bf5  mov     r8d, 153Eh
0x140012bfb  lea     rdx, aHbevtpmapsyste; "HbEvtpMapSystemDiagLogBuffer"
0x140012c02  xor     ecx, ecx
0x140012c04  call    HbpTraceEvent
0x140012c09  mov     edx, [rsi+54h]
0x140012c0c  mov     ecx, 2
0x140012c11  call    cs:__imp_WinHvUnmapEventLogBuffer
0x140012c18  nop     dword ptr [rax+rax+00h]
0x140012c1d  mov     ebx, 0C000009Ah
0x140012c22  mov     rcx, rdi
0x140012c25  call    HbEvtpFreeEventLogMdl
0x140012c2a  mov     eax, ebx
0x140012c2c  add     rsp, 38h
0x140012c30  pop     rdi
0x140012c31  pop     rsi
0x140012c32  pop     rbp
0x140012c33  pop     rbx
0x140012c34  retn
```
