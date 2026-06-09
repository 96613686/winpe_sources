# VmbusTlAuthenticateListenSockAddress

- ea: `0x14000695c`
- end: `0x140006bda`
- name: `VmbusTlAuthenticateListenSockAddress`
- size: `638`
- prototype: `__int64 __fastcall(__int64, __int64, struct _KPROCESS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001e5ac`

## callees

- `0x14000695c`
- `0x140009ec0`
- `0x14000a048`
- `0x14000a154`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x140018008`
- `0x140021ec0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006bba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006bba`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006bae`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006bae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006976`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006976`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006b88`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006b88`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006986`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006986`
- `ntoskrnl!PsGetProcessId` at `0x140006a3e`
- `ntoskrnl!PsGetProcessId` at `0x140006aee`
- `ntoskrnl!PsGetProcessId` at `0x140006a3e`
- `ntoskrnl!PsGetProcessId` at `0x140006aee`

## pseudocode

```c
__int64 __fastcall VmbusTlAuthenticateListenSockAddress(__int64 a1, __int64 a2, struct _KPROCESS *a3)
{
  void *v6; // rdi
  int v7; // r14d
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // edi
  void *v11; // rax
  unsigned int ProcessId; // eax
  int v13; // edx
  signed __int64 v14; // rax
  bool v15; // cc
  signed __int64 v16; // rax
  void (__fastcall *v17)(__int64); // rax

  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v6 = *(void **)(a1 + 384);
  v7 = a2 + 20;
  v8 = VmbusTlFindAndReferenceService(a1, a2 + 20);
  v9 = v8;
  if ( !v8 )
    goto LABEL_7;
  if ( *(_BYTE *)(v8 + 128) )
  {
    v11 = *(void **)(v8 + 144);
    if ( v11 )
    {
      v6 = v11;
      goto LABEL_8;
    }
LABEL_7:
    if ( !v6 )
    {
      if ( !memcmp((const void *)(a2 + 4), &HV_GUID_PARENT, 0x10u)
        || !memcmp((const void *)(a2 + 4), &HV_GUID_SILOHOST, 0x10u) )
      {
        v10 = VmbusTlEndpointAccessCheck(a3, *(PSECURITY_DESCRIPTOR *)(*(_QWORD *)(a1 + 200) + 1448LL));
        if ( v10 < 0 && (unsigned int)dword_140013058 > 2 )
        {
          if ( a3 )
            ProcessId = (unsigned int)PsGetProcessId(a3);
          else
            ProcessId = 0;
          v13 = 2021;
          goto LABEL_24;
        }
      }
      else
      {
        v10 = -1073741661;
        if ( (unsigned int)dword_140013058 > 2 )
          HvsocketTraceServiceError(
            (unsigned int)"VmbusTlAuthenticateListenSockAddress",
            2034,
            -1073741661,
            v7,
            a1 + 232);
      }
LABEL_25:
      if ( !v9 )
        goto LABEL_37;
      goto LABEL_26;
    }
LABEL_8:
    v10 = VmbusTlEndpointAccessCheck(a3, v6);
    if ( v10 < 0 && (unsigned int)dword_140013058 > 2 )
    {
      if ( a3 )
        ProcessId = (unsigned int)PsGetProcessId(a3);
      else
        ProcessId = 0;
      v13 = 2005;
LABEL_24:
      HvsocketTraceGuidULongError((unsigned int)"VmbusTlAuthenticateListenSockAddress", v13, v10, v7, ProcessId);
      goto LABEL_25;
    }
    goto LABEL_25;
  }
  v10 = -1073741436;
  if ( (unsigned int)dword_140013058 > 2 )
    HvsocketTraceServiceError(
      (unsigned int)"VmbusTlAuthenticateListenSockAddress",
      1987,
      -1073741436,
      a2 + 20,
      a1 + 232);
LABEL_26:
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlAuthenticateListenSockAddress",
      2042,
      v9,
      *(_QWORD *)(v9 + 8),
      (__int64)"Dereference object");
  v14 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v9 + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v15 = v14 <= 1;
  v16 = v14 - 1;
  if ( v15 )
  {
    if ( v16 )
      __fastfail(0xEu);
    v17 = *(void (__fastcall **)(__int64))(v9 + 80);
    if ( v17 )
      v17(v9);
    if ( *(_DWORD *)(v9 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v9, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v9 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v9 + 96), (PVOID)v9);
    }
  }
LABEL_37:
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000695c  push    rbx
0x14000695e  push    rbp
0x14000695f  push    rsi
0x140006960  push    rdi
0x140006961  push    r12
0x140006963  push    r13
0x140006965  push    r14
0x140006967  push    r15
0x140006969  sub     rsp, 38h
0x14000696d  mov     rsi, r8
0x140006970  mov     r15, rdx
0x140006973  mov     rbp, rcx
0x140006976  call    cs:__imp_KeEnterCriticalRegion
0x14000697d  nop     dword ptr [rax+rax+00h]
0x140006982  lea     rcx, [rbp+10h]; FastMutex
0x140006986  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000698d  nop     dword ptr [rax+rax+00h]
0x140006992  mov     rdi, [rbp+180h]
0x140006999  lea     r14, [r15+14h]
0x14000699d  mov     rdx, r14
0x1400069a0  mov     rcx, rbp
0x1400069a3  call    VmbusTlFindAndReferenceService
0x1400069a8  lea     r13, aVmbustlauthent_1; "VmbusTlAuthenticateListenSockAddress"
0x1400069af  mov     rbx, rax
0x1400069b2  test    rax, rax
0x1400069b5  jz      short loc_140006A09
0x1400069b7  cmp     byte ptr [rax+80h], 0
0x1400069be  jnz     short loc_1400069F8
0x1400069c0  mov     ecx, cs:dword_140013058
0x1400069c6  mov     edi, 0C0000184h
0x1400069cb  cmp     ecx, 2
0x1400069ce  jbe     loc_140006B1A
0x1400069d4  lea     rax, [rbp+0E8h]
0x1400069db  mov     r9, r14
0x1400069de  mov     r8d, edi
0x1400069e1  mov     [rsp+78h+var_58], rax
0x1400069e6  mov     edx, 7C3h
0x1400069eb  mov     rcx, r13
0x1400069ee  call    HvsocketTraceServiceError
0x1400069f3  jmp     loc_140006B1A
0x1400069f8  mov     rax, [rax+90h]
0x1400069ff  test    rax, rax
0x140006a02  jz      short loc_140006A09
0x140006a04  mov     rdi, rax
0x140006a07  jmp     short loc_140006A0E
0x140006a09  test    rdi, rdi
0x140006a0c  jz      short loc_140006A54
0x140006a0e  mov     rdx, rdi; SecurityDescriptor
0x140006a11  mov     rcx, rsi; Process
0x140006a14  call    VmbusTlEndpointAccessCheck
0x140006a19  mov     edi, eax
0x140006a1b  test    eax, eax
0x140006a1d  jns     loc_140006B11
0x140006a23  mov     ecx, cs:dword_140013058
0x140006a29  cmp     ecx, 2
0x140006a2c  jbe     loc_140006B11
0x140006a32  test    rsi, rsi
0x140006a35  jnz     short loc_140006A3B
0x140006a37  xor     eax, eax
0x140006a39  jmp     short loc_140006A4A
0x140006a3b  mov     rcx, rsi; Process
0x140006a3e  call    cs:__imp_PsGetProcessId
0x140006a45  nop     dword ptr [rax+rax+00h]
0x140006a4a  mov     edx, 7D5h
0x140006a4f  jmp     loc_140006AFF
0x140006a54  lea     rdi, [r15+4]
0x140006a58  mov     r15d, 10h
0x140006a5e  mov     r8d, r15d; Size
0x140006a61  lea     rdx, HV_GUID_PARENT; Buf2
0x140006a68  mov     rcx, rdi; Buf1
0x140006a6b  call    memcmp
0x140006a70  test    eax, eax
0x140006a72  jz      short loc_140006ABB
0x140006a74  mov     r8d, r15d; Size
0x140006a77  lea     rdx, HV_GUID_SILOHOST; Buf2
0x140006a7e  mov     rcx, rdi; Buf1
0x140006a81  call    memcmp
0x140006a86  test    eax, eax
0x140006a88  jz      short loc_140006ABB
0x140006a8a  mov     eax, cs:dword_140013058
0x140006a90  mov     edi, 0C00000A3h
0x140006a95  cmp     eax, 2
0x140006a98  jbe     short loc_140006B11
0x140006a9a  lea     rax, [rbp+0E8h]
0x140006aa1  mov     r9, r14
0x140006aa4  mov     r8d, edi
0x140006aa7  mov     [rsp+78h+var_58], rax
0x140006aac  mov     edx, 7F2h
0x140006ab1  mov     rcx, r13
0x140006ab4  call    HvsocketTraceServiceError
0x140006ab9  jmp     short loc_140006B11
0x140006abb  mov     rdx, [rbp+0C8h]
0x140006ac2  mov     rcx, rsi; Process
0x140006ac5  mov     rdx, [rdx+5A8h]; SecurityDescriptor
0x140006acc  call    VmbusTlEndpointAccessCheck
0x140006ad1  mov     edi, eax
0x140006ad3  test    eax, eax
0x140006ad5  jns     short loc_140006B11
0x140006ad7  mov     eax, cs:dword_140013058
0x140006add  cmp     eax, 2
0x140006ae0  jbe     short loc_140006B11
0x140006ae2  test    rsi, rsi
0x140006ae5  jnz     short loc_140006AEB
0x140006ae7  xor     eax, eax
0x140006ae9  jmp     short loc_140006AFA
0x140006aeb  mov     rcx, rsi; Process
0x140006aee  call    cs:__imp_PsGetProcessId
0x140006af5  nop     dword ptr [rax+rax+00h]
0x140006afa  mov     edx, 7E5h
0x140006aff  mov     r9, r14
0x140006b02  mov     dword ptr [rsp+78h+var_58], eax
0x140006b06  mov     r8d, edi
0x140006b09  mov     rcx, r13
0x140006b0c  call    HvsocketTraceGuidULongError
0x140006b11  test    rbx, rbx
0x140006b14  jz      loc_140006BAA
0x140006b1a  mov     eax, cs:dword_140013058
0x140006b20  cmp     eax, 5
0x140006b23  jbe     short loc_140006B45
0x140006b25  mov     r9, [rbx+8]
0x140006b29  lea     rax, aDereferenceObj; "Dereference object"
0x140006b30  mov     r8, rbx
0x140006b33  mov     [rsp+78h+var_58], rax
0x140006b38  mov     edx, 7FAh
0x140006b3d  mov     rcx, r13
0x140006b40  call    HvsocketTraceReferenceCount
0x140006b45  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006b49  lock xadd [rbx+8], rax
0x140006b4f  sub     rax, 1
0x140006b53  jg      short loc_140006BAA
0x140006b55  test    rax, rax
0x140006b58  jz      short loc_140006B63
0x140006b5a  mov     ecx, 0Eh
0x140006b5f  int     29h; Win8: RtlFailFast(ecx)
0x140006b61  jmp     short loc_140006BAA
0x140006b63  mov     rax, [rbx+50h]
0x140006b67  test    rax, rax
0x140006b6a  jz      short loc_140006B74
0x140006b6c  mov     rcx, rbx
0x140006b6f  call    _guard_dispatch_icall
0x140006b74  mov     ecx, [rbx+58h]
0x140006b77  sub     ecx, 1
0x140006b7a  jz      short loc_140006B96
0x140006b7c  cmp     ecx, 1
0x140006b7f  jnz     short loc_140006BAA
0x140006b81  mov     rcx, [rbx+60h]; Lookaside
0x140006b85  mov     rdx, rbx; Entry
0x140006b88  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006b8f  nop     dword ptr [rax+rax+00h]
0x140006b94  jmp     short loc_140006BAA
0x140006b96  mov     edx, 69706E56h; Tag
0x140006b9b  mov     rcx, rbx; P
0x140006b9e  call    cs:__imp_ExFreePoolWithTag
0x140006ba5  nop     dword ptr [rax+rax+00h]
0x140006baa  lea     rcx, [rbp+10h]; FastMutex
0x140006bae  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140006bb5  nop     dword ptr [rax+rax+00h]
0x140006bba  call    cs:__imp_KeLeaveCriticalRegion
0x140006bc1  nop     dword ptr [rax+rax+00h]
0x140006bc6  mov     eax, edi
0x140006bc8  add     rsp, 38h
0x140006bcc  pop     r15
0x140006bce  pop     r14
0x140006bd0  pop     r13
0x140006bd2  pop     r12
0x140006bd4  pop     rdi
0x140006bd5  pop     rsi
0x140006bd6  pop     rbp
0x140006bd7  pop     rbx
0x140006bd8  retn
```
