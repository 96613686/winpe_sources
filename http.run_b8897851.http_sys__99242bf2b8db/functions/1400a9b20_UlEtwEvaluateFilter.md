# UlEtwEvaluateFilter

- ea: `0x1400a9b20`
- end: `0x1400a9d3f`
- name: `UlEtwEvaluateFilter`
- size: `543`
- prototype: ``
- caller_count: `47`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140005d10`
- `0x1400068a8`
- `0x140009a90`
- `0x140032fd0`
- `0x14004d150`
- `0x14004e120`
- `0x14004edf0`
- `0x140057f60`
- `0x14005ce20`
- `0x14005d530`
- `0x14006462c`
- `0x140064800`
- `0x140065a30`
- `0x1400688b0`
- `0x1400703c0`
- `0x140079ac4`
- `0x14007a3c8`
- `0x14007f024`
- `0x140080180`
- `0x140080680`
- `0x14008d8b0`
- `0x140094540`
- `0x140097240`
- `0x1400b1bac`
- `0x1400b2ab0`
- `0x1400b3f4c`
- `0x1400b95a8`
- `0x1400c2c40`
- `0x1400c3cb0`
- `0x1400c3fc0`
- `0x1400daff4`
- `0x1400dcfd0`
- `0x1400e29d8`
- `0x1400e2a70`
- `0x14010c790`
- `0x1401102f0`
- `0x1401104e0`
- `0x140110df0`
- `0x140111c80`
- `0x140113f28`
- `0x140117800`
- `0x1401319a4`
- `0x14013879c`
- `0x140139a30`
- `0x140139b40`
- `0x14013c618`
- `0x14013ccb0`

## callees

- `0x14000a350`
- `0x140094f40`
- `0x1400a9b20`
- `0x1400e3160`
- `0x1400e31b0`
- `0x140132c3c`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400a9cfb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a9cfb`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400a9cd6`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400a9cd6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400a9ba6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400a9ba6`
- `NDIS!NdisReleaseRWLock` at `0x1400a9c1b`
- `NDIS!NdisReleaseRWLock` at `0x1400a9c1b`
- `NDIS!NdisAcquireRWLockRead` at `0x1400a9bcc`
- `NDIS!NdisAcquireRWLockRead` at `0x1400a9bcc`
- `NDIS!NdisGetJobObjectCompartmentId` at `0x1400a9c39`
- `NDIS!NdisGetJobObjectCompartmentId` at `0x1400a9c39`

## pseudocode

```c
char __fastcall UlEtwEvaluateFilter(
        __int64 a1,
        int a2,
        int a3,
        struct _KPROCESS *a4,
        __int64 a5,
        int a6,
        __int64 a7,
        unsigned int a8)
{
  int JobObjectCompartmentId; // esi
  ULONG_PTR *v13; // rdi
  struct _EX_RUNDOWN_REF *v14; // rbp
  ULONG_PTR v15; // rdi
  int v16; // eax
  __int64 v17; // rcx
  __int64 Buffer; // rbp
  int Length; // r14d
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF
  _LOCK_STATE_EX LockState; // [rsp+A0h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  DestinationString = 0;
  JobObjectCompartmentId = 1;
  v13 = (ULONG_PTR *)(a1 + 1776);
  if ( (BYTE1(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_qq(1036, 15, WPP_44c496324fa63838e09271a1387dbff3_Traceguids, a1, *v13);
  if ( !*(_BYTE *)(a1 + 4212) )
  {
    if ( *v13 )
    {
      v14 = (struct _EX_RUNDOWN_REF *)(a1 + 4216);
      if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 4216)) )
      {
        NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 1768), &LockState, 0);
        v15 = *v13;
        if ( v15 )
        {
          v16 = _InterlockedIncrement((volatile signed __int32 *)v15);
          if ( UxDebugCheckRefcount )
          {
            if ( v16 <= -1 )
              UlBugCheckEx(3u, v15, 0x21u, v16);
          }
        }
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 1768), &LockState);
        if ( v15 )
        {
          v17 = *(_QWORD *)(a1 + 64);
          if ( v17 )
            JobObjectCompartmentId = NdisGetJobObjectCompartmentId(v17);
          Buffer = a5;
          if ( !a5 || (Length = a6) == 0 )
          {
            Buffer = 0;
            Length = 0;
            if ( a7 )
            {
              if ( a8 && (int)UxSslValidateSni(a1, a7, a8, &DestinationString) >= 0 )
              {
                Buffer = (__int64)DestinationString.Buffer;
                Length = DestinationString.Length;
              }
            }
          }
          LOBYTE(JobObjectCompartmentId) = UlpEtwEvaluateFilterInternal(
                                             *(_QWORD *)(v15 + 8),
                                             JobObjectCompartmentId,
                                             a2,
                                             a3,
                                             a4,
                                             Buffer,
                                             Length);
          UlpDereferenceEtwRules(v15, 0x21u);
          v14 = (struct _EX_RUNDOWN_REF *)(a1 + 4216);
        }
        ExReleaseRundownProtection(v14);
      }
    }
  }
  if ( DestinationString.Buffer )
  {
    UlFreeWideString(&DestinationString.Buffer);
    RtlInitUnicodeString(&DestinationString, 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 0x10) != 0 )
    WPP_SF_d(1036, 16, WPP_44c496324fa63838e09271a1387dbff3_Traceguids, (unsigned __int8)JobObjectCompartmentId);
  return JobObjectCompartmentId;
}

```

## disassembly

```asm
0x1400a9b20  mov     r11, rsp
0x1400a9b23  push    rbx
0x1400a9b24  push    rbp
0x1400a9b25  push    rsi
0x1400a9b26  push    rdi
0x1400a9b27  push    r12
0x1400a9b29  push    r13
0x1400a9b2b  push    r14
0x1400a9b2d  push    r15
0x1400a9b2f  sub     rsp, 58h
0x1400a9b33  xor     eax, eax
0x1400a9b35  xorps   xmm0, xmm0
0x1400a9b38  mov     [r11+8], ax
0x1400a9b3d  mov     r15, r9
0x1400a9b40  mov     [r11+0Ah], al
0x1400a9b44  mov     r12, r8
0x1400a9b47  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x1400a9b4c  mov     r13, rdx
0x1400a9b4f  mov     rbx, rcx
0x1400a9b52  mov     esi, 1
0x1400a9b57  test    byte ptr cs:xmmword_1401A2CA0+1, 10h
0x1400a9b5e  lea     rdi, [rcx+6F0h]
0x1400a9b65  jz      short loc_1400A9B85
0x1400a9b67  mov     rax, [rdi]
0x1400a9b6a  lea     edx, [rsi+0Eh]
0x1400a9b6d  mov     ecx, 40Ch
0x1400a9b72  mov     [r11-78h], rax
0x1400a9b76  mov     r9, rbx
0x1400a9b79  lea     r8, WPP_44c496324fa63838e09271a1387dbff3_Traceguids
0x1400a9b80  call    WPP_SF_qq
0x1400a9b85  cmp     byte ptr [rbx+1074h], 0
0x1400a9b8c  jnz     loc_1400A9CE2
0x1400a9b92  cmp     qword ptr [rdi], 0
0x1400a9b96  jz      loc_1400A9CE2
0x1400a9b9c  lea     rbp, [rbx+1078h]
0x1400a9ba3  mov     rcx, rbp; RunRef
0x1400a9ba6  call    cs:__imp_ExAcquireRundownProtection
0x1400a9bad  nop     dword ptr [rax+rax+00h]
0x1400a9bb2  test    al, al
0x1400a9bb4  jz      loc_1400A9CE2
0x1400a9bba  mov     rcx, [rbx+6E8h]; Lock
0x1400a9bc1  lea     rdx, [rsp+98h+LockState]; LockState
0x1400a9bc9  xor     r8d, r8d; Flags
0x1400a9bcc  call    cs:__imp_NdisAcquireRWLockRead
0x1400a9bd3  nop     dword ptr [rax+rax+00h]
0x1400a9bd8  mov     rdi, [rdi]
0x1400a9bdb  test    rdi, rdi
0x1400a9bde  jz      short loc_1400A9C0C
0x1400a9be0  mov     eax, esi
0x1400a9be2  lock xadd [rdi], eax
0x1400a9be6  add     eax, esi
0x1400a9be8  cmp     cs:UxDebugCheckRefcount, 0
0x1400a9bef  jz      short loc_1400A9C0C
0x1400a9bf1  cmp     eax, 0FFFFFFFFh
0x1400a9bf4  jg      short loc_1400A9C0C
0x1400a9bf6  mov     r8d, 21h ; '!'; BugCheckParameter3
0x1400a9bfc  movsxd  r9, eax; BugCheckParameter4
0x1400a9bff  mov     rdx, rdi; BugCheckParameter2
0x1400a9c02  lea     ecx, [r8-1Eh]; BugCheckParameter1
0x1400a9c06  call    UlBugCheckEx
0x1400a9c0c  mov     rcx, [rbx+6E8h]; Lock
0x1400a9c13  lea     rdx, [rsp+98h+LockState]; LockState
0x1400a9c1b  call    cs:__imp_NdisReleaseRWLock
0x1400a9c22  nop     dword ptr [rax+rax+00h]
0x1400a9c27  test    rdi, rdi
0x1400a9c2a  jz      loc_1400A9CD3
0x1400a9c30  mov     rcx, [rbx+40h]
0x1400a9c34  test    rcx, rcx
0x1400a9c37  jz      short loc_1400A9C47
0x1400a9c39  call    cs:__imp_NdisGetJobObjectCompartmentId
0x1400a9c40  nop     dword ptr [rax+rax+00h]
0x1400a9c45  mov     esi, eax
0x1400a9c47  mov     rbp, [rsp+98h+arg_20]
0x1400a9c4f  test    rbp, rbp
0x1400a9c52  jz      short loc_1400A9C61
0x1400a9c54  mov     r14d, [rsp+98h+arg_28]
0x1400a9c5c  test    r14d, r14d
0x1400a9c5f  jnz     short loc_1400A9C9C
0x1400a9c61  mov     rdx, [rsp+98h+arg_30]
0x1400a9c69  xor     ebp, ebp
0x1400a9c6b  xor     r14d, r14d
0x1400a9c6e  test    rdx, rdx
0x1400a9c71  jz      short loc_1400A9C9C
0x1400a9c73  mov     r8d, [rsp+98h+arg_38]
0x1400a9c7b  test    r8d, r8d
0x1400a9c7e  jz      short loc_1400A9C9C
0x1400a9c80  lea     r9, [rsp+98h+DestinationString]
0x1400a9c85  mov     rcx, rbx
0x1400a9c88  call    UxSslValidateSni
0x1400a9c8d  test    eax, eax
0x1400a9c8f  js      short loc_1400A9C9C
0x1400a9c91  mov     rbp, [rsp+98h+DestinationString.Buffer]
0x1400a9c96  movzx   r14d, [rsp+98h+DestinationString.Length]
0x1400a9c9c  mov     rcx, [rdi+8]; int
0x1400a9ca0  mov     r9, r12; int
0x1400a9ca3  mov     [rsp+98h+var_68], r14d; int
0x1400a9ca8  mov     r8, r13; int
0x1400a9cab  mov     [rsp+98h+var_70], rbp; __int64
0x1400a9cb0  mov     edx, esi; int
0x1400a9cb2  mov     [rsp+98h+Process], r15; Process
0x1400a9cb7  call    UlpEtwEvaluateFilterInternal
0x1400a9cbc  mov     sil, al
0x1400a9cbf  mov     edx, 21h ; '!'; BugCheckParameter3
0x1400a9cc4  mov     rcx, rdi; BugCheckParameter2
0x1400a9cc7  call    UlpDereferenceEtwRules
0x1400a9ccc  lea     rbp, [rbx+1078h]
0x1400a9cd3  mov     rcx, rbp; RunRef
0x1400a9cd6  call    cs:__imp_ExReleaseRundownProtection
0x1400a9cdd  nop     dword ptr [rax+rax+00h]
0x1400a9ce2  cmp     [rsp+98h+DestinationString.Buffer], 0
0x1400a9ce8  jz      short loc_1400A9D07
0x1400a9cea  lea     rcx, [rsp+98h+DestinationString.Buffer]
0x1400a9cef  call    UlFreeWideString
0x1400a9cf4  xor     edx, edx; SourceString
0x1400a9cf6  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1400a9cfb  call    cs:__imp_RtlInitUnicodeString
0x1400a9d02  nop     dword ptr [rax+rax+00h]
0x1400a9d07  test    byte ptr cs:xmmword_1401A2CA0+1, 10h
0x1400a9d0e  jz      short loc_1400A9D2A
0x1400a9d10  movzx   r9d, sil
0x1400a9d14  lea     r8, WPP_44c496324fa63838e09271a1387dbff3_Traceguids
0x1400a9d1b  mov     edx, 10h
0x1400a9d20  mov     ecx, 40Ch
0x1400a9d25  call    WPP_SF_d
0x1400a9d2a  mov     al, sil
0x1400a9d2d  add     rsp, 58h
0x1400a9d31  pop     r15
0x1400a9d33  pop     r14
0x1400a9d35  pop     r13
0x1400a9d37  pop     r12
0x1400a9d39  pop     rdi
0x1400a9d3a  pop     rsi
0x1400a9d3b  pop     rbp
0x1400a9d3c  pop     rbx
0x1400a9d3d  retn
```
