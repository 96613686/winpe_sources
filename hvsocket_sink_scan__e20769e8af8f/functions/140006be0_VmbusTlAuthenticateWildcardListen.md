# VmbusTlAuthenticateWildcardListen

- ea: `0x140006be0`
- end: `0x140006de0`
- name: `VmbusTlAuthenticateWildcardListen`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001e5ac`

## callees

- `0x140006be0`
- `0x140009ec0`
- `0x14000a048`
- `0x14000bfe0`
- `0x140018008`
- `0x14001d60c`
- `0x14002672c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006c6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006c6f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006c63`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006c63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d6c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006c35`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006c35`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006d56`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006d56`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006c45`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006c45`
- `ntoskrnl!PsGetProcessId` at `0x140006c1f`
- `ntoskrnl!PsGetProcessId` at `0x140006cba`
- `ntoskrnl!PsGetProcessId` at `0x140006da9`
- `ntoskrnl!PsGetProcessId` at `0x140006c1f`
- `ntoskrnl!PsGetProcessId` at `0x140006cba`
- `ntoskrnl!PsGetProcessId` at `0x140006da9`

## pseudocode

```c
__int64 __fastcall VmbusTlAuthenticateWildcardListen(__int64 a1, __int64 a2, struct _KPROCESS *a3)
{
  int v6; // ebx
  unsigned int ProcessId; // eax
  int v8; // edx
  __int64 v9; // rdi
  void *v10; // rdx
  char v11; // r14
  unsigned int v12; // eax
  signed __int64 v13; // rax
  bool v14; // cc
  signed __int64 v15; // rax
  void (__fastcall *v16)(__int64); // rax

  if ( (unsigned __int8)HvSocketGetAzureFeatureSetEnabled() )
  {
    v6 = -1073741304;
    if ( (unsigned int)dword_140013058 > 2 )
    {
      if ( a3 )
        ProcessId = (unsigned int)PsGetProcessId(a3);
      else
        ProcessId = 0;
      v8 = 2078;
LABEL_34:
      HvsocketTraceGuidULongError((unsigned int)"VmbusTlAuthenticateWildcardListen", v8, v6, a2, ProcessId);
    }
  }
  else
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v9 = VmbusTlFindAndReferenceWildcardDescriptor(a1, a2);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    KeLeaveCriticalRegion();
    if ( !v9 )
      goto LABEL_29;
    v10 = *(void **)(v9 + 128);
    v6 = 0;
    v11 = 0;
    if ( v10 )
    {
      v6 = VmbusTlEndpointAccessCheck(a3, v10);
      if ( v6 < 0 && (unsigned int)dword_140013058 > 2 )
      {
        if ( a3 )
          v12 = (unsigned int)PsGetProcessId(a3);
        else
          v12 = 0;
        HvsocketTraceGuidULongError((unsigned int)"VmbusTlAuthenticateWildcardListen", 2093, v6, a2, v12);
      }
      v11 = 1;
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlAuthenticateWildcardListen",
        2097,
        v9,
        *(_QWORD *)(v9 + 8),
        (__int64)"Dereference object");
    v13 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v9 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v14 = v13 <= 1;
    v15 = v13 - 1;
    if ( v14 )
    {
      if ( v15 )
        __fastfail(0xEu);
      v16 = *(void (__fastcall **)(__int64))(v9 + 80);
      if ( v16 )
        v16(v9);
      if ( *(_DWORD *)(v9 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v9, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v9 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v9 + 96), (PVOID)v9);
      }
    }
    if ( !v11 )
    {
LABEL_29:
      v6 = VmbusTlEndpointAccessCheck(a3, *(PSECURITY_DESCRIPTOR *)(a1 + 1448));
      if ( v6 < 0 && (unsigned int)dword_140013058 > 2 )
      {
        if ( a3 )
          ProcessId = (unsigned int)PsGetProcessId(a3);
        else
          ProcessId = 0;
        v8 = 2109;
        goto LABEL_34;
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140006be0  push    rbx
0x140006be2  push    rbp
0x140006be3  push    rsi
0x140006be4  push    rdi
0x140006be5  push    r14
0x140006be7  push    r15
0x140006be9  sub     rsp, 38h
0x140006bed  mov     rsi, r8
0x140006bf0  mov     rbp, rdx
0x140006bf3  mov     r15, rcx
0x140006bf6  call    HvSocketGetAzureFeatureSetEnabled
0x140006bfb  test    al, al
0x140006bfd  jz      short loc_140006C35
0x140006bff  mov     eax, cs:dword_140013058
0x140006c05  mov     ebx, 0C0000208h
0x140006c0a  cmp     eax, 2
0x140006c0d  jbe     loc_140006DD0
0x140006c13  test    rsi, rsi
0x140006c16  jnz     short loc_140006C1C
0x140006c18  xor     eax, eax
0x140006c1a  jmp     short loc_140006C2B
0x140006c1c  mov     rcx, rsi; Process
0x140006c1f  call    cs:__imp_PsGetProcessId
0x140006c26  nop     dword ptr [rax+rax+00h]
0x140006c2b  mov     edx, 81Eh
0x140006c30  jmp     loc_140006DBA
0x140006c35  call    cs:__imp_KeEnterCriticalRegion
0x140006c3c  nop     dword ptr [rax+rax+00h]
0x140006c41  lea     rcx, [r15+10h]; FastMutex
0x140006c45  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140006c4c  nop     dword ptr [rax+rax+00h]
0x140006c51  mov     rdx, rbp
0x140006c54  mov     rcx, r15
0x140006c57  call    VmbusTlFindAndReferenceWildcardDescriptor
0x140006c5c  lea     rcx, [r15+10h]; FastMutex
0x140006c60  mov     rdi, rax
0x140006c63  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140006c6a  nop     dword ptr [rax+rax+00h]
0x140006c6f  call    cs:__imp_KeLeaveCriticalRegion
0x140006c76  nop     dword ptr [rax+rax+00h]
0x140006c7b  test    rdi, rdi
0x140006c7e  jz      loc_140006D7D
0x140006c84  mov     rdx, [rdi+80h]; SecurityDescriptor
0x140006c8b  xor     ebx, ebx
0x140006c8d  xor     r14b, r14b
0x140006c90  test    rdx, rdx
0x140006c93  jz      short loc_140006CE4
0x140006c95  mov     rcx, rsi; Process
0x140006c98  call    VmbusTlEndpointAccessCheck
0x140006c9d  mov     ebx, eax
0x140006c9f  test    eax, eax
0x140006ca1  jns     short loc_140006CE1
0x140006ca3  mov     ecx, cs:dword_140013058
0x140006ca9  cmp     ecx, 2
0x140006cac  jbe     short loc_140006CE1
0x140006cae  test    rsi, rsi
0x140006cb1  jnz     short loc_140006CB7
0x140006cb3  xor     eax, eax
0x140006cb5  jmp     short loc_140006CC6
0x140006cb7  mov     rcx, rsi; Process
0x140006cba  call    cs:__imp_PsGetProcessId
0x140006cc1  nop     dword ptr [rax+rax+00h]
0x140006cc6  mov     r9, rbp
0x140006cc9  mov     dword ptr [rsp+68h+var_48], eax
0x140006ccd  mov     r8d, ebx
0x140006cd0  lea     rcx, aVmbustlauthent; "VmbusTlAuthenticateWildcardListen"
0x140006cd7  mov     edx, 82Dh
0x140006cdc  call    HvsocketTraceGuidULongError
0x140006ce1  mov     r14b, 1
0x140006ce4  mov     eax, cs:dword_140013058
0x140006cea  cmp     eax, 5
0x140006ced  jbe     short loc_140006D13
0x140006cef  mov     r9, [rdi+8]
0x140006cf3  lea     rax, aDereferenceObj; "Dereference object"
0x140006cfa  mov     r8, rdi
0x140006cfd  mov     [rsp+68h+var_48], rax
0x140006d02  mov     edx, 831h
0x140006d07  lea     rcx, aVmbustlauthent; "VmbusTlAuthenticateWildcardListen"
0x140006d0e  call    HvsocketTraceReferenceCount
0x140006d13  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006d17  lock xadd [rdi+8], rax
0x140006d1d  sub     rax, 1
0x140006d21  jg      short loc_140006D78
0x140006d23  test    rax, rax
0x140006d26  jz      short loc_140006D31
0x140006d28  mov     ecx, 0Eh
0x140006d2d  int     29h; Win8: RtlFailFast(ecx)
0x140006d2f  jmp     short loc_140006D78
0x140006d31  mov     rax, [rdi+50h]
0x140006d35  test    rax, rax
0x140006d38  jz      short loc_140006D42
0x140006d3a  mov     rcx, rdi
0x140006d3d  call    _guard_dispatch_icall
0x140006d42  mov     ecx, [rdi+58h]
0x140006d45  sub     ecx, 1
0x140006d48  jz      short loc_140006D64
0x140006d4a  cmp     ecx, 1
0x140006d4d  jnz     short loc_140006D78
0x140006d4f  mov     rcx, [rdi+60h]; Lookaside
0x140006d53  mov     rdx, rdi; Entry
0x140006d56  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006d5d  nop     dword ptr [rax+rax+00h]
0x140006d62  jmp     short loc_140006D78
0x140006d64  mov     edx, 69706E56h; Tag
0x140006d69  mov     rcx, rdi; P
0x140006d6c  call    cs:__imp_ExFreePoolWithTag
0x140006d73  nop     dword ptr [rax+rax+00h]
0x140006d78  test    r14b, r14b
0x140006d7b  jnz     short loc_140006DD0
0x140006d7d  mov     rdx, [r15+5A8h]; SecurityDescriptor
0x140006d84  mov     rcx, rsi; Process
0x140006d87  call    VmbusTlEndpointAccessCheck
0x140006d8c  mov     ebx, eax
0x140006d8e  test    eax, eax
0x140006d90  jns     short loc_140006DD0
0x140006d92  mov     eax, cs:dword_140013058
0x140006d98  cmp     eax, 2
0x140006d9b  jbe     short loc_140006DD0
0x140006d9d  test    rsi, rsi
0x140006da0  jnz     short loc_140006DA6
0x140006da2  xor     eax, eax
0x140006da4  jmp     short loc_140006DB5
0x140006da6  mov     rcx, rsi; Process
0x140006da9  call    cs:__imp_PsGetProcessId
0x140006db0  nop     dword ptr [rax+rax+00h]
0x140006db5  mov     edx, 83Dh
0x140006dba  mov     r9, rbp
0x140006dbd  mov     dword ptr [rsp+68h+var_48], eax
0x140006dc1  mov     r8d, ebx
0x140006dc4  lea     rcx, aVmbustlauthent; "VmbusTlAuthenticateWildcardListen"
0x140006dcb  call    HvsocketTraceGuidULongError
0x140006dd0  mov     eax, ebx
0x140006dd2  add     rsp, 38h
0x140006dd6  pop     r15
0x140006dd8  pop     r14
0x140006dda  pop     rdi
0x140006ddb  pop     rsi
0x140006ddc  pop     rbp
0x140006ddd  pop     rbx
0x140006dde  retn
```
