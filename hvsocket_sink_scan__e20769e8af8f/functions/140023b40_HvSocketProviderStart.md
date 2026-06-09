# HvSocketProviderStart

- ea: `0x140023b40`
- end: `0x14002423f`
- name: `HvSocketProviderStart`
- size: `1791`
- prototype: `__int64 __fastcall(__int64, _OWORD *, int, _QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001350`
- `0x1400017ec`
- `0x140006220`
- `0x140009cf8`
- `0x14000a048`
- `0x14000a408`
- `0x14000aa04`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x140023b40`
- `0x140026694`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140023e78`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140023e78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024094`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002411c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002414c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002416b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024094`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002411c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002414c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002416b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140023d96`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140023dc9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140023dfc`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140023e2f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140023d96`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140023dc9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140023dfc`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140023e2f`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x140023eaa`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x140023f52`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x140023eaa`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x140023f52`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024088`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024110`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024140`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002415f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024088`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024110`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024140`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002415f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002420c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002420c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023bb4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023bee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400240e5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023bb4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023bee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400240e5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400241f6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400241f6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023bc7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023bfe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400240f5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023bc7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023bfe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400240f5`
- `NETIO!NmrRegisterProvider` at `0x1400240b1`
- `NETIO!NmrRegisterProvider` at `0x1400240b1`
- `NETIO!NetioInitializeWorkQueue` at `0x140023ff4`
- `NETIO!NetioInitializeWorkQueue` at `0x140023ff4`

## string_xrefs

- `0x140023c73`: `Currently registered provider incompatible.`
- `0x140023cb3`: `Could not create transport object.`
- `0x140023ecb`: `Failed to convert default security descriptor.`
- `0x140023f71`: `Failed to convert security descriptor.`
- `0x140023f2b`: `Failed to create wildcard descriptor object.`

## pseudocode

```c
__int64 __fastcall HvSocketProviderStart(__int64 a1, _OWORD *a2, int a3, _QWORD *a4)
{
  _QWORD *v4; // r13
  char v5; // bl
  _OWORD *v6; // rsi
  char *v9; // rdi
  char v10; // r15
  NTSTATUS v11; // esi
  int v12; // eax
  char *v13; // rbx
  const char *v14; // r9
  __int64 v15; // rdx
  char *v16; // r13
  char **v17; // rcx
  char *v18; // rax
  signed __int64 v19; // rax
  bool v20; // cc
  signed __int64 v21; // rax
  void (__fastcall *v22)(char *); // rax
  PVOID Entry; // [rsp+40h] [rbp-30h] BYREF
  _OWORD *v24; // [rsp+48h] [rbp-28h]
  _QWORD *v25; // [rsp+50h] [rbp-20h]
  _DWORD v26[4]; // [rsp+58h] [rbp-18h] BYREF

  v25 = a4;
  v4 = a4;
  v24 = a2;
  v5 = a3;
  v6 = a2;
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("HvSocketProviderStart", 254, 3221225485LL, "Invalid flags supplied.");
    return 3221225485LL;
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(&FastMutex);
  v9 = (char *)VmbusProviderContext;
  Entry = VmbusProviderContext;
  if ( !VmbusProviderContext )
  {
    v12 = VmbusTlCreateObject(6, 1536, &Entry);
    v11 = v12;
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceError("HvSocketProviderStart", 287, (unsigned int)v12, "Could not create transport object.");
      v9 = (char *)Entry;
      goto LABEL_51;
    }
    v9 = (char *)Entry;
    *((_QWORD *)Entry + 10) = HvSocketProviderDestructor;
    v13 = v9 + 1416;
    *((_QWORD *)v9 + 22) = 0;
    *((_QWORD *)v9 + 21) = 0;
    *((GUID *)v9 + 91) = HV_GUID_ZERO;
    *((GUID *)v9 + 92) = HV_GUID_ZERO;
    *(_OWORD *)(v9 + 1432) = 0;
    v9[121] = 0;
    VmbusTlProviderNotify.ProviderRegistrationInstance.ModuleId = (PNPI_MODULEID)NPI_MS_VMBUS_MODULEID;
    VmbusTlProviderNotify.ProviderRegistrationInstance.NpiSpecificCharacteristics = VmbusTlProviderCharacteristics;
    *((_QWORD *)v9 + 17) = v9 + 128;
    *((_QWORD *)v9 + 16) = v9 + 128;
    *((_QWORD *)v9 + 19) = v9 + 144;
    *((_QWORD *)v9 + 18) = v9 + 144;
    *((_QWORD *)v9 + 178) = v9 + 1416;
    *((_QWORD *)v9 + 177) = v9 + 1416;
    ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v9 + 192), 0, 0, 0x200u, 0x100u, 0x69706E56u, 0);
    ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v9 + 320), 0, 0, 0x200u, 0x150u, 0x69706E56u, 0);
    ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v9 + 448), 0, 0, 0x200u, 0x470u, 0x69706E56u, 0);
    ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v9 + 576), 0, 0, 0x200u, 0x1B0u, 0x69706E56u, 0);
    VmbusTlXPartInitLookAsideList(v9 + 704);
    VmbusTlLoopbackInitLookAsideList(v9 + 832);
    RtlInitializeGenericTableAvl(
      (PRTL_AVL_TABLE)(v9 + 1016),
      VmbusTlComparePointers,
      VmbusTlAllocateForAvlTable,
      VmbusTlFreeForAvlTable,
      0);
    VmbusTlInitializeObjectTable((PVOID)0x69706E56, (PRTL_AVL_TABLE)(v9 + 1312));
    v11 = SeConvertStringSecurityDescriptorToSecurityDescriptor(
            L"D:P(A;;FA;;;WD)(A;;FA;;;S-1-15-3-1024-3623855041-1826999956-3747069818-3525260223-3747374510-1746272624-950601168-56556331)",
            1,
            v9 + 1448);
    if ( v11 >= 0 )
    {
      v26[0] = -1717677100;
      v26[1] = 1279147356;
      v26[2] = -792823417;
      v26[3] = -514408338;
      Entry = 0;
      if ( (int)VmbusTlCreateWildcardDescriptor(v26, &Entry) >= 0 )
      {
        v16 = (char *)Entry;
        if ( (int)SeConvertStringSecurityDescriptorToSecurityDescriptor(
                    L"D:P(A;;FA;;;S-1-5-80-235582178-102246843-358262472-4132936818-1867412993)",
                    1,
                    (char *)Entry + 128) >= 0 )
        {
          v17 = (char **)*((_QWORD *)v9 + 178);
          if ( *v17 != v13 )
            __fastfail(3u);
          v6 = v24;
          v18 = v16 + 96;
          v4 = v25;
          v10 = 0;
          *(_QWORD *)v18 = v13;
          *((_QWORD *)v18 + 1) = v17;
          *v17 = v18;
          *((_QWORD *)v9 + 178) = v18;
LABEL_30:
          if ( v6 && !*((_QWORD *)v9 + 180) )
            *(_OWORD *)(v9 + 1432) = *v6;
          if ( !*((_QWORD *)v9 + 22) && a1 )
          {
            v11 = NetioInitializeWorkQueue(v9 + 960, VmbusTlEndpointWorkQueueDestructor, 0, a1);
            if ( v11 < 0 )
            {
              if ( (unsigned int)dword_140013058 > 2 )
                HvsocketTraceError(
                  "HvSocketProviderStart",
                  451,
                  (unsigned int)v11,
                  "Initialize close endpoint work queue failed.");
              goto LABEL_49;
            }
            *((_QWORD *)v9 + 22) = a1;
            v9[1008] = 1;
            v11 = HvSocketInitializeWorkQueues(v9);
            if ( v11 < 0 )
            {
              if ( (unsigned int)dword_140013058 > 2 )
                HvsocketTraceError("HvSocketProviderStart", 461, (unsigned int)v11, "Initialize work queues failed.");
              *((_QWORD *)v9 + 22) = 0;
              goto LABEL_49;
            }
            if ( v10 )
            {
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 16));
              KeLeaveCriticalRegion();
              v10 = 0;
            }
            v11 = NmrRegisterProvider(&VmbusTlProviderNotify, v9, (PHANDLE)v9 + 12);
            if ( v11 < 0 )
            {
              if ( (unsigned int)dword_140013058 > 2 )
                HvsocketTraceError("HvSocketProviderStart", 484, (unsigned int)v11, "Could not register provider.");
              KeEnterCriticalRegion();
              ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 16));
              *((_QWORD *)v9 + 22) = 0;
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 16));
              KeLeaveCriticalRegion();
LABEL_49:
              if ( !v10 )
                goto LABEL_51;
              goto LABEL_50;
            }
          }
          VmbusProviderContext = v9;
          v11 = 0;
          *v4 = v9;
          goto LABEL_49;
        }
        if ( (unsigned int)dword_140013058 <= 2 )
          goto LABEL_51;
        v14 = "Failed to convert security descriptor.";
        v15 = 420;
      }
      else
      {
        if ( (unsigned int)dword_140013058 <= 2 )
          goto LABEL_51;
        v14 = "Failed to create wildcard descriptor object.";
        v15 = 411;
      }
    }
    else
    {
      if ( (unsigned int)dword_140013058 <= 2 )
        goto LABEL_51;
      v14 = "Failed to convert default security descriptor.";
      v15 = 397;
    }
    HvsocketTraceError("HvSocketProviderStart", v15, (unsigned int)v11, v14);
    goto LABEL_51;
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 16));
  v10 = 1;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketProviderStart",
      266,
      (_DWORD)v9,
      *((_QWORD *)v9 + 1),
      (__int64)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)v9 + 1) <= 1 )
    __fastfail(0xEu);
  if ( v9[121] == (v5 & 1) )
    goto LABEL_30;
  v11 = -1073741436;
  if ( (unsigned int)dword_140013058 > 2 )
    HvsocketTraceError("HvSocketProviderStart", 272, 3221225860LL, "Currently registered provider incompatible.");
LABEL_50:
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 16));
  KeLeaveCriticalRegion();
LABEL_51:
  ExReleaseFastMutexUnsafe(&FastMutex);
  KeLeaveCriticalRegion();
  if ( v11 < 0 && v9 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketProviderStart",
        517,
        (_DWORD)v9,
        *((_QWORD *)v9 + 1),
        (__int64)"Dereference object");
    v19 = _InterlockedExchangeAdd64((volatile signed __int64 *)v9 + 1, 0xFFFFFFFFFFFFFFFFuLL);
    v20 = v19 <= 1;
    v21 = v19 - 1;
    if ( v20 )
    {
      if ( v21 )
        __fastfail(0xEu);
      v22 = (void (__fastcall *)(char *))*((_QWORD *)v9 + 10);
      if ( v22 )
        v22(v9);
      if ( *((_DWORD *)v9 + 22) == 1 )
      {
        ExFreePoolWithTag(v9, 0x69706E56u);
      }
      else if ( *((_DWORD *)v9 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v9 + 12), v9);
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140023b40  mov     [rsp-38h+arg_8], rbx
0x140023b45  push    rbp
0x140023b46  push    rsi
0x140023b47  push    rdi
0x140023b48  push    r12
0x140023b4a  push    r13
0x140023b4c  push    r14
0x140023b4e  push    r15
0x140023b50  mov     rbp, rsp
0x140023b53  sub     rsp, 70h
0x140023b57  mov     rax, cs:__security_cookie
0x140023b5e  xor     rax, rsp
0x140023b61  mov     [rbp+var_8], rax
0x140023b65  mov     [rbp+var_20], r9
0x140023b69  mov     r13, r9
0x140023b6c  mov     [rbp+var_28], rdx
0x140023b70  mov     ebx, r8d
0x140023b73  mov     rsi, rdx
0x140023b76  mov     r12, rcx
0x140023b79  test    r8d, 0FFFFFFFEh
0x140023b80  jz      short loc_140023BB4
0x140023b82  mov     ecx, cs:dword_140013058
0x140023b88  mov     ebx, 0C000000Dh
0x140023b8d  cmp     ecx, 2
0x140023b90  jbe     short loc_140023BAD
0x140023b92  lea     r9, aInvalidFlagsSu; "Invalid flags supplied."
0x140023b99  mov     r8d, ebx
0x140023b9c  mov     edx, 0FEh
0x140023ba1  lea     rcx, aHvsocketprovid_0; "HvSocketProviderStart"
0x140023ba8  call    HvsocketTraceError
0x140023bad  mov     eax, ebx
0x140023baf  jmp     loc_14002421A
0x140023bb4  call    cs:__imp_KeEnterCriticalRegion
0x140023bbb  nop     dword ptr [rax+rax+00h]
0x140023bc0  lea     rcx, FastMutex; FastMutex
0x140023bc7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140023bce  nop     dword ptr [rax+rax+00h]
0x140023bd3  mov     rdi, cs:VmbusProviderContext
0x140023bda  lea     r14, aHvsocketprovid_0; "HvSocketProviderStart"
0x140023be1  mov     [rbp+Entry], rdi
0x140023be5  test    rdi, rdi
0x140023be8  jz      loc_140023C8F
0x140023bee  call    cs:__imp_KeEnterCriticalRegion
0x140023bf5  nop     dword ptr [rax+rax+00h]
0x140023bfa  lea     rcx, [rdi+10h]; FastMutex
0x140023bfe  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140023c05  nop     dword ptr [rax+rax+00h]
0x140023c0a  mov     eax, cs:dword_140013058
0x140023c10  mov     r15b, 1
0x140023c13  cmp     eax, 5
0x140023c16  jbe     short loc_140023C38
0x140023c18  mov     r9, [rdi+8]
0x140023c1c  lea     rax, aReferenceObjec; "Reference object"
0x140023c23  mov     r8, rdi
0x140023c26  mov     [rsp+70h+Size], rax
0x140023c2b  mov     edx, 10Ah
0x140023c30  mov     rcx, r14
0x140023c33  call    HvsocketTraceReferenceCount
0x140023c38  mov     eax, 1
0x140023c3d  lock xadd [rdi+8], rax
0x140023c43  inc     rax
0x140023c46  cmp     rax, 1
0x140023c4a  jg      short loc_140023C53
0x140023c4c  mov     ecx, 0Eh
0x140023c51  int     29h; Win8: RtlFailFast(ecx)
0x140023c53  and     ebx, 1
0x140023c56  cmp     [rdi+79h], bl
0x140023c59  jz      loc_140023FAF
0x140023c5f  mov     eax, cs:dword_140013058
0x140023c65  mov     esi, 0C0000184h
0x140023c6a  cmp     eax, 2
0x140023c6d  jbe     loc_14002413C
0x140023c73  lea     r9, aCurrentlyRegis; "Currently registered provider incompati"...
0x140023c7a  mov     r8d, esi
0x140023c7d  mov     edx, 110h
0x140023c82  mov     rcx, r14
0x140023c85  call    HvsocketTraceError
0x140023c8a  jmp     loc_14002413C
0x140023c8f  lea     r8, [rbp+Entry]
0x140023c93  mov     edx, 600h
0x140023c98  mov     ecx, 6
0x140023c9d  call    VmbusTlCreateObject
0x140023ca2  mov     esi, eax
0x140023ca4  test    eax, eax
0x140023ca6  jns     short loc_140023CD3
0x140023ca8  mov     ecx, cs:dword_140013058
0x140023cae  cmp     ecx, 2
0x140023cb1  jbe     short loc_140023CCA
0x140023cb3  lea     r9, aCouldNotCreate; "Could not create transport object."
0x140023cba  mov     r8d, eax
0x140023cbd  mov     edx, 11Fh
0x140023cc2  mov     rcx, r14
0x140023cc5  call    HvsocketTraceError
0x140023cca  mov     rdi, [rbp+Entry]
0x140023cce  jmp     loc_140024158
0x140023cd3  mov     rdi, [rbp+Entry]
0x140023cd7  lea     rax, HvSocketProviderDestructor
0x140023cde  mov     esi, 200h
0x140023ce3  xor     r8d, r8d; Free
0x140023ce6  mov     r9d, esi; Flags
0x140023ce9  xor     edx, edx; Allocate
0x140023ceb  mov     [rdi+50h], rax
0x140023cef  lea     rbx, [rdi+588h]
0x140023cf6  mov     qword ptr [rdi+0B0h], 0
0x140023d01  lea     rax, NPI_MS_VMBUS_MODULEID
0x140023d08  mov     qword ptr [rdi+0A8h], 0
0x140023d13  lea     rcx, [rdi+0C0h]; Lookaside
0x140023d1a  movups  xmm0, xmmword ptr cs:HV_GUID_ZERO.Data1
0x140023d21  movdqu  xmmword ptr [rdi+5B0h], xmm0
0x140023d29  movups  xmm1, xmmword ptr cs:HV_GUID_ZERO.Data1
0x140023d30  xorps   xmm0, xmm0
0x140023d33  movdqu  xmmword ptr [rdi+5C0h], xmm1
0x140023d3b  movups  xmmword ptr [rdi+598h], xmm0
0x140023d42  mov     byte ptr [rdi+79h], 0
0x140023d46  mov     cs:VmbusTlProviderNotify.ProviderRegistrationInstance.ModuleId, rax
0x140023d4d  lea     rax, VmbusTlProviderCharacteristics
0x140023d54  mov     cs:VmbusTlProviderNotify.ProviderRegistrationInstance.NpiSpecificCharacteristics, rax
0x140023d5b  lea     rax, [rdi+80h]
0x140023d62  mov     [rax+8], rax
0x140023d66  mov     [rax], rax
0x140023d69  lea     rax, [rdi+90h]
0x140023d70  mov     [rax+8], rax
0x140023d74  mov     [rax], rax
0x140023d77  xor     eax, eax
0x140023d79  mov     [rsp+70h+Depth], ax; Depth
0x140023d7e  mov     [rsp+70h+Tag], 69706E56h; Tag
0x140023d86  mov     [rsp+70h+Size], 100h; Size
0x140023d8f  mov     [rbx+8], rbx
0x140023d93  mov     [rbx], rbx
0x140023d96  call    cs:__imp_ExInitializeNPagedLookasideList
0x140023d9d  nop     dword ptr [rax+rax+00h]
0x140023da2  xor     eax, eax
0x140023da4  lea     rcx, [rdi+140h]; Lookaside
0x140023dab  mov     [rsp+70h+Depth], ax; Depth
0x140023db0  mov     r9d, esi; Flags
0x140023db3  mov     [rsp+70h+Tag], 69706E56h; Tag
0x140023dbb  xor     r8d, r8d; Free
0x140023dbe  xor     edx, edx; Allocate
0x140023dc0  mov     [rsp+70h+Size], 150h; Size
0x140023dc9  call    cs:__imp_ExInitializeNPagedLookasideList
0x140023dd0  nop     dword ptr [rax+rax+00h]
0x140023dd5  xor     eax, eax
0x140023dd7  lea     rcx, [rdi+1C0h]; Lookaside
0x140023dde  mov     [rsp+70h+Depth], ax; Depth
0x140023de3  mov     r9d, esi; Flags
0x140023de6  mov     [rsp+70h+Tag], 69706E56h; Tag
0x140023dee  xor     r8d, r8d; Free
0x140023df1  xor     edx, edx; Allocate
0x140023df3  mov     [rsp+70h+Size], 470h; Size
0x140023dfc  call    cs:__imp_ExInitializeNPagedLookasideList
0x140023e03  nop     dword ptr [rax+rax+00h]
0x140023e08  xor     eax, eax
0x140023e0a  lea     rcx, [rdi+240h]; Lookaside
0x140023e11  mov     [rsp+70h+Depth], ax; Depth
0x140023e16  mov     r9d, esi; Flags
0x140023e19  mov     [rsp+70h+Tag], 69706E56h; Tag
0x140023e21  xor     r8d, r8d; Free
0x140023e24  xor     edx, edx; Allocate
0x140023e26  mov     [rsp+70h+Size], 1B0h; Size
0x140023e2f  call    cs:__imp_ExInitializeNPagedLookasideList
0x140023e36  nop     dword ptr [rax+rax+00h]
0x140023e3b  lea     rcx, [rdi+2C0h]
0x140023e42  call    VmbusTlXPartInitLookAsideList
0x140023e47  lea     rcx, [rdi+340h]
0x140023e4e  call    VmbusTlLoopbackInitLookAsideList
0x140023e53  lea     rcx, [rdi+3F8h]; Table
0x140023e5a  mov     [rsp+70h+Size], 0; TableContext
0x140023e63  lea     r9, VmbusTlFreeForAvlTable; FreeRoutine
0x140023e6a  lea     r8, VmbusTlAllocateForAvlTable; AllocateRoutine
0x140023e71  lea     rdx, VmbusTlComparePointers; CompareRoutine
0x140023e78  call    cs:__imp_RtlInitializeGenericTableAvl
0x140023e7f  nop     dword ptr [rax+rax+00h]
0x140023e84  lea     rdx, [rdi+520h]; Table
0x140023e8b  mov     ecx, 69706E56h; TableContext
0x140023e90  call    VmbusTlInitializeObjectTable
0x140023e95  xor     r9d, r9d
0x140023e98  lea     r8, [rdi+5A8h]
0x140023e9f  lea     rcx, aDPAFaWdAFaS115; "D:P(A;;FA;;;WD)(A;;FA;;;S-1-15-3-1024-3"...
0x140023ea6  lea     edx, [r9+1]
0x140023eaa  call    cs:__imp_SeConvertStringSecurityDescriptorToSecurityDescriptor
0x140023eb1  nop     dword ptr [rax+rax+00h]
0x140023eb6  mov     esi, eax
0x140023eb8  test    eax, eax
0x140023eba  jns     short loc_140023EE7
0x140023ebc  mov     eax, cs:dword_140013058
0x140023ec2  cmp     eax, 2
0x140023ec5  jbe     loc_140024158
0x140023ecb  lea     r9, aFailedToConver_0; "Failed to convert default security desc"...
0x140023ed2  mov     edx, 18Dh
0x140023ed7  mov     r8d, esi
0x140023eda  mov     rcx, r14
0x140023edd  call    HvsocketTraceError
0x140023ee2  jmp     loc_140024158
0x140023ee7  lea     rdx, [rbp+Entry]
0x140023eeb  mov     [rbp+var_18], 999E53D4h
0x140023ef2  lea     rcx, [rbp+var_18]
0x140023ef6  mov     [rbp+var_14], 4C3E3D5Ch
0x140023efd  mov     [rbp+var_10], 0D0BE7987h
0x140023f04  mov     [rbp+var_C], 0E156C06Eh
0x140023f0b  mov     [rbp+Entry], 0
0x140023f13  call    VmbusTlCreateWildcardDescriptor
0x140023f18  test    eax, eax
0x140023f1a  jns     short loc_140023F39
0x140023f1c  mov     eax, cs:dword_140013058
0x140023f22  cmp     eax, 2
0x140023f25  jbe     loc_140024158
0x140023f2b  lea     r9, aFailedToCreate_2; "Failed to create wildcard descriptor ob"...
0x140023f32  mov     edx, 19Bh
0x140023f37  jmp     short loc_140023ED7
0x140023f39  mov     r13, [rbp+Entry]
0x140023f3d  lea     rcx, aDPAFaS15802355; "D:P(A;;FA;;;S-1-5-80-235582178-10224684"...
0x140023f44  xor     r9d, r9d
0x140023f47  lea     r8, [r13+80h]
0x140023f4e  lea     edx, [r9+1]
0x140023f52  call    cs:__imp_SeConvertStringSecurityDescriptorToSecurityDescriptor
0x140023f59  nop     dword ptr [rax+rax+00h]
0x140023f5e  test    eax, eax
0x140023f60  jns     short loc_140023F82
0x140023f62  mov     eax, cs:dword_140013058
0x140023f68  cmp     eax, 2
0x140023f6b  jbe     loc_140024158
0x140023f71  lea     r9, aFailedToConver; "Failed to convert security descriptor."
0x140023f78  mov     edx, 1A4h
0x140023f7d  jmp     loc_140023ED7
0x140023f82  mov     rcx, [rbx+8]
0x140023f86  cmp     [rcx], rbx
0x140023f89  jz      short loc_140023F92
0x140023f8b  mov     ecx, 3
0x140023f90  int     29h; Win8: RtlFailFast(ecx)
0x140023f92  mov     rsi, [rbp+var_28]
0x140023f96  lea     rax, [r13+60h]
0x140023f9a  mov     r13, [rbp+var_20]
0x140023f9e  xor     r15b, r15b
0x140023fa1  mov     [rax], rbx
0x140023fa4  mov     [rax+8], rcx
0x140023fa8  mov     [rcx], rax
0x140023fab  mov     [rbx+8], rax
0x140023faf  test    rsi, rsi
0x140023fb2  jz      short loc_140023FC9
0x140023fb4  cmp     qword ptr [rdi+5A0h], 0
0x140023fbc  jnz     short loc_140023FC9
0x140023fbe  movups  xmm0, xmmword ptr [rsi]
0x140023fc1  movdqu  xmmword ptr [rdi+598h], xmm0
0x140023fc9  cmp     qword ptr [rdi+0B0h], 0
0x140023fd1  jnz     loc_14002412A
0x140023fd7  test    r12, r12
0x140023fda  jz      loc_14002412A
0x140023fe0  lea     rcx, [rdi+3C0h]
0x140023fe7  mov     r9, r12
0x140023fea  xor     r8d, r8d
0x140023fed  lea     rdx, VmbusTlEndpointWorkQueueDestructor
0x140023ff4  call    cs:__imp_NetioInitializeWorkQueue
0x140023ffb  nop     dword ptr [rax+rax+00h]
0x140024000  mov     esi, eax
0x140024002  test    eax, eax
0x140024004  jns     short loc_140024031
0x140024006  mov     eax, cs:dword_140013058
0x14002400c  cmp     eax, 2
0x14002400f  jbe     loc_140024137
0x140024015  lea     r9, aInitializeClos; "Initialize close endpoint work queue fa"...
0x14002401c  mov     r8d, esi
0x14002401f  mov     edx, 1C3h
0x140024024  mov     rcx, r14
0x140024027  call    HvsocketTraceError
0x14002402c  jmp     loc_140024137
0x140024031  mov     [rdi+0B0h], r12
0x140024038  mov     rcx, rdi
0x14002403b  mov     byte ptr [rdi+3F0h], 1
0x140024042  call    HvSocketInitializeWorkQueues
0x140024047  mov     esi, eax
0x140024049  test    eax, eax
0x14002404b  jns     short loc_14002407F
0x14002404d  mov     eax, cs:dword_140013058
0x140024053  cmp     eax, 2
0x140024056  jbe     short loc_14002406F
0x140024058  lea     r9, aInitializeWork; "Initialize work queues failed."
0x14002405f  mov     r8d, esi
0x140024062  mov     edx, 1CDh
0x140024067  mov     rcx, r14
0x14002406a  call    HvsocketTraceError
0x14002406f  mov     qword ptr [rdi+0B0h], 0
0x14002407a  jmp     loc_140024137
0x14002407f  test    r15b, r15b
0x140024082  jz      short loc_1400240A3
0x140024084  lea     rcx, [rdi+10h]; FastMutex
0x140024088  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002408f  nop     dword ptr [rax+rax+00h]
0x140024094  call    cs:__imp_KeLeaveCriticalRegion
0x14002409b  nop     dword ptr [rax+rax+00h]
0x1400240a0  xor     r15b, r15b
0x1400240a3  lea     r8, [rdi+60h]; NmrProviderHandle
0x1400240a7  mov     rdx, rdi; ProviderContext
0x1400240aa  lea     rcx, VmbusTlProviderNotify; ProviderCharacteristics
0x1400240b1  call    cs:__imp_NmrRegisterProvider
0x1400240b8  nop     dword ptr [rax+rax+00h]
0x1400240bd  mov     esi, eax
0x1400240bf  test    eax, eax
0x1400240c1  jns     short loc_14002412A
0x1400240c3  mov     eax, cs:dword_140013058
0x1400240c9  cmp     eax, 2
  ... truncated ...
```
