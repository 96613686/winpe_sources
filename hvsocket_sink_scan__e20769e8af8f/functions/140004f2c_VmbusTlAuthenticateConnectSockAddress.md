# VmbusTlAuthenticateConnectSockAddress

- ea: `0x140004f2c`
- end: `0x1400051a8`
- name: `VmbusTlAuthenticateConnectSockAddress`
- size: `636`
- prototype: `__int64 __fastcall(__int64, __int64, struct _KPROCESS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001a148`

## callees

- `0x140004f2c`
- `0x140009ec0`
- `0x14000a048`
- `0x14000a154`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x140018008`
- `0x140021ec0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005188`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005188`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000517c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000517c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000516c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000516c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004f46`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004f46`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005156`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005156`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140004f56`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140004f56`
- `ntoskrnl!PsGetProcessId` at `0x14000500e`
- `ntoskrnl!PsGetProcessId` at `0x14000500e`

## pseudocode

```c
__int64 __fastcall VmbusTlAuthenticateConnectSockAddress(__int64 a1, __int64 a2, struct _KPROCESS *a3)
{
  void *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rbx
  int v9; // edi
  void *v10; // rax
  unsigned int ProcessId; // eax
  const void *v12; // rdi
  int v13; // edx
  signed __int64 v14; // rax
  bool v15; // cc
  signed __int64 v16; // rax
  void (__fastcall *v17)(__int64); // rax

  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v6 = *(void **)(a1 + 376);
  v7 = VmbusTlFindAndReferenceService(a1, a2 + 20);
  v8 = v7;
  if ( !v7 )
    goto LABEL_7;
  if ( *(_BYTE *)(v7 + 128) )
  {
    v10 = *(void **)(v7 + 136);
    if ( v10 )
    {
      v6 = v10;
      goto LABEL_8;
    }
LABEL_7:
    if ( !v6 )
    {
      v12 = (const void *)(a2 + 4);
      if ( !memcmp((const void *)(a2 + 4), &HV_GUID_PARENT, 0x10u)
        || !memcmp(v12, &HV_GUID_SILOHOST, 0x10u)
        || !memcmp(v12, &HV_GUID_LOOPBACK, 0x10u) )
      {
        v9 = VmbusTlEndpointAccessCheck(a3, *(PSECURITY_DESCRIPTOR *)(*(_QWORD *)(a1 + 200) + 1448LL));
        if ( v9 >= 0 || (unsigned int)dword_140013058 <= 2 )
          goto LABEL_23;
        v13 = 899;
      }
      else
      {
        v9 = -1073741661;
        if ( (unsigned int)dword_140013058 <= 2 )
          goto LABEL_23;
        v13 = 911;
      }
      HvsocketTraceServiceError((unsigned int)"VmbusTlAuthenticateConnectSockAddress", v13, v9, a2 + 20, a1 + 232);
      goto LABEL_23;
    }
LABEL_8:
    v9 = VmbusTlEndpointAccessCheck(a3, v6);
    if ( v9 < 0 && (unsigned int)dword_140013058 > 2 )
    {
      if ( a3 )
        ProcessId = (unsigned int)PsGetProcessId(a3);
      else
        ProcessId = 0;
      HvsocketTraceGuidULongError((unsigned int)"VmbusTlAuthenticateConnectSockAddress", 881, v9, a2 + 20, ProcessId);
    }
LABEL_23:
    if ( !v8 )
      goto LABEL_35;
    goto LABEL_24;
  }
  v9 = -1073741436;
  if ( (unsigned int)dword_140013058 > 2 )
    HvsocketTraceServiceError(
      (unsigned int)"VmbusTlAuthenticateConnectSockAddress",
      863,
      -1073741436,
      a2 + 20,
      a1 + 232);
LABEL_24:
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlAuthenticateConnectSockAddress",
      919,
      v8,
      *(_QWORD *)(v8 + 8),
      (__int64)"Dereference object");
  v14 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v8 + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v15 = v14 <= 1;
  v16 = v14 - 1;
  if ( v15 )
  {
    if ( v16 )
      __fastfail(0xEu);
    v17 = *(void (__fastcall **)(__int64))(v8 + 80);
    if ( v17 )
      v17(v8);
    if ( *(_DWORD *)(v8 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v8, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v8 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v8 + 96), (PVOID)v8);
    }
  }
LABEL_35:
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140004f2c  push    rbx
0x140004f2e  push    rbp
0x140004f2f  push    rsi
0x140004f30  push    rdi
0x140004f31  push    r12
0x140004f33  push    r13
0x140004f35  push    r14
0x140004f37  push    r15
0x140004f39  sub     rsp, 38h
0x140004f3d  mov     rbp, r8
0x140004f40  mov     r15, rdx
0x140004f43  mov     rsi, rcx
0x140004f46  call    cs:__imp_KeEnterCriticalRegion
0x140004f4d  nop     dword ptr [rax+rax+00h]
0x140004f52  lea     rcx, [rsi+10h]; FastMutex
0x140004f56  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140004f5d  nop     dword ptr [rax+rax+00h]
0x140004f62  mov     rdi, [rsi+178h]
0x140004f69  lea     r14, [r15+14h]
0x140004f6d  mov     rdx, r14
0x140004f70  mov     rcx, rsi
0x140004f73  call    VmbusTlFindAndReferenceService
0x140004f78  lea     r13, aVmbustlauthent_0; "VmbusTlAuthenticateConnectSockAddress"
0x140004f7f  mov     rbx, rax
0x140004f82  test    rax, rax
0x140004f85  jz      short loc_140004FD9
0x140004f87  cmp     byte ptr [rax+80h], 0
0x140004f8e  jnz     short loc_140004FC8
0x140004f90  mov     ecx, cs:dword_140013058
0x140004f96  mov     edi, 0C0000184h
0x140004f9b  cmp     ecx, 2
0x140004f9e  jbe     loc_1400050E8
0x140004fa4  lea     rax, [rsi+0E8h]
0x140004fab  mov     r9, r14
0x140004fae  mov     r8d, edi
0x140004fb1  mov     [rsp+78h+var_58], rax
0x140004fb6  mov     edx, 35Fh
0x140004fbb  mov     rcx, r13
0x140004fbe  call    HvsocketTraceServiceError
0x140004fc3  jmp     loc_1400050E8
0x140004fc8  mov     rax, [rax+88h]
0x140004fcf  test    rax, rax
0x140004fd2  jz      short loc_140004FD9
0x140004fd4  mov     rdi, rax
0x140004fd7  jmp     short loc_140004FDE
0x140004fd9  test    rdi, rdi
0x140004fdc  jz      short loc_140005036
0x140004fde  mov     rdx, rdi; SecurityDescriptor
0x140004fe1  mov     rcx, rbp; Process
0x140004fe4  call    VmbusTlEndpointAccessCheck
0x140004fe9  mov     edi, eax
0x140004feb  test    eax, eax
0x140004fed  jns     loc_1400050DF
0x140004ff3  mov     ecx, cs:dword_140013058
0x140004ff9  cmp     ecx, 2
0x140004ffc  jbe     loc_1400050DF
0x140005002  test    rbp, rbp
0x140005005  jnz     short loc_14000500B
0x140005007  xor     eax, eax
0x140005009  jmp     short loc_14000501A
0x14000500b  mov     rcx, rbp; Process
0x14000500e  call    cs:__imp_PsGetProcessId
0x140005015  nop     dword ptr [rax+rax+00h]
0x14000501a  mov     r9, r14
0x14000501d  mov     dword ptr [rsp+78h+var_58], eax
0x140005021  mov     r8d, edi
0x140005024  mov     edx, 371h
0x140005029  mov     rcx, r13
0x14000502c  call    HvsocketTraceGuidULongError
0x140005031  jmp     loc_1400050DF
0x140005036  lea     rdi, [r15+4]
0x14000503a  mov     r15d, 10h
0x140005040  mov     r8d, r15d; Size
0x140005043  lea     rdx, HV_GUID_PARENT; Buf2
0x14000504a  mov     rcx, rdi; Buf1
0x14000504d  call    memcmp
0x140005052  test    eax, eax
0x140005054  jz      short loc_140005099
0x140005056  mov     r8d, r15d; Size
0x140005059  lea     rdx, HV_GUID_SILOHOST; Buf2
0x140005060  mov     rcx, rdi; Buf1
0x140005063  call    memcmp
0x140005068  test    eax, eax
0x14000506a  jz      short loc_140005099
0x14000506c  mov     r8d, r15d; Size
0x14000506f  lea     rdx, HV_GUID_LOOPBACK; Buf2
0x140005076  mov     rcx, rdi; Buf1
0x140005079  call    memcmp
0x14000507e  test    eax, eax
0x140005080  jz      short loc_140005099
0x140005082  mov     eax, cs:dword_140013058
0x140005088  mov     edi, 0C00000A3h
0x14000508d  cmp     eax, 2
0x140005090  jbe     short loc_1400050DF
0x140005092  mov     edx, 38Fh
0x140005097  jmp     short loc_1400050C5
0x140005099  mov     rdx, [rsi+0C8h]
0x1400050a0  mov     rcx, rbp; Process
0x1400050a3  mov     rdx, [rdx+5A8h]; SecurityDescriptor
0x1400050aa  call    VmbusTlEndpointAccessCheck
0x1400050af  mov     edi, eax
0x1400050b1  test    eax, eax
0x1400050b3  jns     short loc_1400050DF
0x1400050b5  mov     eax, cs:dword_140013058
0x1400050bb  cmp     eax, 2
0x1400050be  jbe     short loc_1400050DF
0x1400050c0  mov     edx, 383h
0x1400050c5  lea     rax, [rsi+0E8h]
0x1400050cc  mov     r9, r14
0x1400050cf  mov     r8d, edi
0x1400050d2  mov     [rsp+78h+var_58], rax
0x1400050d7  mov     rcx, r13
0x1400050da  call    HvsocketTraceServiceError
0x1400050df  test    rbx, rbx
0x1400050e2  jz      loc_140005178
0x1400050e8  mov     eax, cs:dword_140013058
0x1400050ee  cmp     eax, 5
0x1400050f1  jbe     short loc_140005113
0x1400050f3  mov     r9, [rbx+8]
0x1400050f7  lea     rax, aDereferenceObj; "Dereference object"
0x1400050fe  mov     r8, rbx
0x140005101  mov     [rsp+78h+var_58], rax
0x140005106  mov     edx, 397h
0x14000510b  mov     rcx, r13
0x14000510e  call    HvsocketTraceReferenceCount
0x140005113  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005117  lock xadd [rbx+8], rax
0x14000511d  sub     rax, 1
0x140005121  jg      short loc_140005178
0x140005123  test    rax, rax
0x140005126  jz      short loc_140005131
0x140005128  mov     ecx, 0Eh
0x14000512d  int     29h; Win8: RtlFailFast(ecx)
0x14000512f  jmp     short loc_140005178
0x140005131  mov     rax, [rbx+50h]
0x140005135  test    rax, rax
0x140005138  jz      short loc_140005142
0x14000513a  mov     rcx, rbx
0x14000513d  call    _guard_dispatch_icall
0x140005142  mov     ecx, [rbx+58h]
0x140005145  sub     ecx, 1
0x140005148  jz      short loc_140005164
0x14000514a  cmp     ecx, 1
0x14000514d  jnz     short loc_140005178
0x14000514f  mov     rcx, [rbx+60h]; Lookaside
0x140005153  mov     rdx, rbx; Entry
0x140005156  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000515d  nop     dword ptr [rax+rax+00h]
0x140005162  jmp     short loc_140005178
0x140005164  mov     edx, 69706E56h; Tag
0x140005169  mov     rcx, rbx; P
0x14000516c  call    cs:__imp_ExFreePoolWithTag
0x140005173  nop     dword ptr [rax+rax+00h]
0x140005178  lea     rcx, [rsi+10h]; FastMutex
0x14000517c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140005183  nop     dword ptr [rax+rax+00h]
0x140005188  call    cs:__imp_KeLeaveCriticalRegion
0x14000518f  nop     dword ptr [rax+rax+00h]
0x140005194  mov     eax, edi
0x140005196  add     rsp, 38h
0x14000519a  pop     r15
0x14000519c  pop     r14
0x14000519e  pop     r13
0x1400051a0  pop     r12
0x1400051a2  pop     rdi
0x1400051a3  pop     rsi
0x1400051a4  pop     rbp
0x1400051a5  pop     rbx
0x1400051a6  retn
```
