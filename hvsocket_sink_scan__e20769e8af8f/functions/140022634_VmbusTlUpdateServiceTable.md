# VmbusTlUpdateServiceTable

- ea: `0x140022634`
- end: `0x140022b51`
- name: `VmbusTlUpdateServiceTable`
- size: `1309`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x14001b3c0`

## callees

- `0x140008c0c`
- `0x14000969c`
- `0x140009cf8`
- `0x140009df0`
- `0x140009fa4`
- `0x14000a048`
- `0x14000a154`
- `0x14000bdd4`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x140021cb4`
- `0x140021ec0`
- `0x140022634`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022af3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022af3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022ae7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022ae7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400227f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022ab4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400227f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022ab4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400226a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400226a2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400227df`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400229ae`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022a52`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400227df`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400229ae`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140022a52`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400226b9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400226b9`

## string_xrefs

- `0x140022b1a`: `ServiceInfoTable is invalid.`
- `0x1400228a6`: `VmbusTlUpdateServiceTable: Invalid service ID found.`
- `0x140022788`: `VmbusTlUpdateServiceTable`
- `0x14002294c`: `VmbusTlUpdateServiceTable`
- `0x1400229cd`: `VmbusTlUpdateServiceTable`
- `0x140022a04`: `VmbusTlUpdateServiceTable`
- `0x140022a9e`: `VmbusTlUpdateServiceTable`
- `0x140022b29`: `VmbusTlUpdateServiceTable`
- `0x1400228fb`: `VmbusTlUpdateServiceTable: Removing service.`
- `0x14002282d`: `VmbusTlUpdateServiceTable: Service created.`

## pseudocode

```c
__int64 __fastcall VmbusTlUpdateServiceTable(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  unsigned __int64 v5; // r14
  __int64 v6; // r13
  _OWORD *v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rbx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  signed __int64 v13; // rax
  bool v14; // cc
  signed __int64 v15; // rax
  void (__fastcall *v16)(__int64); // rax
  int updated; // edi
  __int64 *v18; // rcx
  __int64 *v19; // rax
  PNPAGED_LOOKASIDE_LIST *v20; // rsi
  PNPAGED_LOOKASIDE_LIST *v21; // rdi
  PNPAGED_LOOKASIDE_LIST *v22; // r14
  PNPAGED_LOOKASIDE_LIST *v23; // rbx
  PNPAGED_LOOKASIDE_LIST v24; // rdx
  PNPAGED_LOOKASIDE_LIST **v25; // rcx
  signed __int64 v26; // rax
  signed __int64 v27; // rax
  void (__fastcall *v28)(PNPAGED_LOOKASIDE_LIST *); // rax
  signed __int64 v29; // rax
  signed __int64 v30; // rax
  void (__fastcall *v31)(__int64); // rax
  __int64 v33; // [rsp+30h] [rbp-20h] BYREF
  PFAST_MUTEX FastMutex; // [rsp+38h] [rbp-18h]
  __int64 v35; // [rsp+40h] [rbp-10h] BYREF
  __int64 *v36; // [rsp+48h] [rbp-8h]

  v3 = a2;
  if ( !a2 || !a3 || (v5 = a3 / 0x30uLL, a3 != 48 * v5) )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("VmbusTlUpdateServiceTable", 910, 3221225485LL, "ServiceInfoTable is invalid.");
    return 3221225485LL;
  }
  v36 = &v35;
  v35 = (__int64)&v35;
  KeEnterCriticalRegion();
  FastMutex = (PFAST_MUTEX)(a1 + 16);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  if ( *(_BYTE *)(a1 + 393) )
  {
LABEL_66:
    updated = 0;
    goto LABEL_67;
  }
  v6 = 0;
  if ( !(_DWORD)v5 )
  {
LABEL_32:
    v20 = (PNPAGED_LOOKASIDE_LIST *)(a1 + 360);
    v21 = *(PNPAGED_LOOKASIDE_LIST **)(a1 + 360);
    if ( v21 != (PNPAGED_LOOKASIDE_LIST *)(a1 + 360) )
    {
      do
      {
        v22 = (PNPAGED_LOOKASIDE_LIST *)*v21;
        v23 = v21 - 12;
        if ( !*((_DWORD *)v21 + 15) )
        {
          if ( (unsigned int)dword_140013058 > 4 )
            HvsocketTraceMessage("VmbusTlUpdateServiceTable: Removing service.", v23 + 14);
          VmbusTlCloseServiceEndpoints(v21 - 12, 0);
          v24 = *v21;
          if ( (PNPAGED_LOOKASIDE_LIST *)(*v21)->L.ListHead.Region != v21 )
            goto LABEL_68;
          v25 = (PNPAGED_LOOKASIDE_LIST **)v23[13];
          if ( *v25 != v21 )
            goto LABEL_68;
          *v25 = (PNPAGED_LOOKASIDE_LIST *)v24;
          v24->L.ListHead.Region = (ULONGLONG)v25;
          v21[1] = (PNPAGED_LOOKASIDE_LIST)v21;
          *v21 = (PNPAGED_LOOKASIDE_LIST)v21;
          if ( (unsigned int)dword_140013058 > 5 )
            HvsocketTraceReferenceCount(
              (unsigned int)"VmbusTlUpdateServiceTable",
              1013,
              (_DWORD)v21 - 96,
              (unsigned int)v23[1],
              (__int64)"Dereference object");
          v26 = _InterlockedExchangeAdd64((volatile signed __int64 *)v23 + 1, 0xFFFFFFFFFFFFFFFFuLL);
          v14 = v26 <= 1;
          v27 = v26 - 1;
          if ( v14 )
          {
            if ( v27 )
              __fastfail(0xEu);
            v28 = (void (__fastcall *)(PNPAGED_LOOKASIDE_LIST *))v23[10];
            if ( v28 )
              v28(v21 - 12);
            if ( *((_DWORD *)v23 + 22) == 1 )
            {
              ExFreePoolWithTag(v21 - 12, 0x69706E56u);
            }
            else if ( *((_DWORD *)v23 + 22) == 2 )
            {
              ExFreeToNPagedLookasideList(*v21, v21 - 12);
            }
          }
        }
        v21 = v22;
      }
      while ( v22 != v20 );
    }
    DvAppendList(v20, &v35);
    goto LABEL_66;
  }
  while ( 1 )
  {
    v7 = (_OWORD *)(v3 + 48 * v6);
    if ( !memcmp(v7, &HV_GUID_BROADCAST, 0x10u) || !memcmp((const void *)(v3 + 48 * v6), &HV_GUID_ZERO, 0x10u) )
    {
      if ( (unsigned int)dword_140013058 > 4 )
        HvsocketTraceMessage("VmbusTlUpdateServiceTable: Invalid service ID found.", v3 + 48 * v6);
      goto LABEL_31;
    }
    v8 = VmbusTlFindAndReferenceService(a1, v3 + 48 * v6);
    v33 = v8;
    v9 = v8;
    if ( v8 )
    {
      v10 = (_QWORD *)(v8 + 96);
      v11 = *v10;
      if ( *(_QWORD **)(*v10 + 8LL) != v10 || (v12 = (_QWORD *)v10[1], (_QWORD *)*v12 != v10) )
LABEL_68:
        __fastfail(3u);
      *v12 = v11;
      *(_QWORD *)(v11 + 8) = v12;
      v10[1] = v10;
      *v10 = v10;
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlUpdateServiceTable",
          957,
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
      goto LABEL_26;
    }
    updated = VmbusTlCreateService(&v33);
    if ( updated < 0 )
      break;
    if ( (unsigned int)dword_140013058 > 4 )
      HvsocketTraceMessage("VmbusTlUpdateServiceTable: Service created.", v7);
    v9 = v33;
    *(_OWORD *)(v33 + 112) = *v7;
    *(_DWORD *)(v9 + 156) = 0;
LABEL_26:
    updated = VmbusTlUpdateService(v7, v12, v9);
    if ( updated < 0 )
    {
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceGuidError("VmbusTlUpdateServiceTable", 983, (unsigned int)updated, v7);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlUpdateServiceTable",
          984,
          v9,
          *(_QWORD *)(v9 + 8),
          (__int64)"Dereference object");
      v29 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v9 + 8), 0xFFFFFFFFFFFFFFFFuLL);
      v14 = v29 <= 1;
      v30 = v29 - 1;
      if ( v14 )
      {
        if ( v30 )
          __fastfail(0xEu);
        v31 = *(void (__fastcall **)(__int64))(v9 + 80);
        if ( v31 )
          v31(v9);
        if ( *(_DWORD *)(v9 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v9, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v9 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v9 + 96), (PVOID)v9);
        }
      }
      goto LABEL_67;
    }
    v18 = v36;
    if ( (__int64 *)*v36 != &v35 )
      goto LABEL_68;
    v19 = (__int64 *)(v9 + 96);
    v3 = a2;
    v19[1] = (__int64)v36;
    *v19 = (__int64)&v35;
    *v18 = (__int64)v19;
    v36 = v19;
LABEL_31:
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= (unsigned int)v5 )
      goto LABEL_32;
  }
  if ( (unsigned int)dword_140013058 > 2 )
    HvsocketTraceServiceError((unsigned int)"VmbusTlUpdateServiceTable", 966, updated, (_DWORD)v7, a1 + 232);
LABEL_67:
  ExReleaseFastMutexUnsafe(FastMutex);
  KeLeaveCriticalRegion();
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140022634  mov     [rsp-28h+arg_0], rbx
0x140022639  mov     [rsp-28h+arg_10], rsi
0x14002263e  mov     [rsp-28h+arg_8], rdx
0x140022643  push    rbp
0x140022644  push    rdi
0x140022645  push    r13
0x140022647  push    r14
0x140022649  push    r15
0x14002264b  mov     rbp, rsp
0x14002264e  sub     rsp, 50h
0x140022652  mov     rbx, rdx
0x140022655  mov     r15, rcx
0x140022658  test    rdx, rdx
0x14002265b  jz      loc_140022B0A
0x140022661  test    r8d, r8d
0x140022664  jz      loc_140022B0A
0x14002266a  mov     r8d, r8d
0x14002266d  mov     rax, 0AAAAAAAAAAAAAAABh
0x140022677  mul     r8
0x14002267a  mov     r14, rdx
0x14002267d  shr     r14, 5
0x140022681  lea     rax, [r14+r14*2]
0x140022685  shl     rax, 4
0x140022689  cmp     r8, rax
0x14002268c  jnz     loc_140022B0A
0x140022692  lea     rax, [rbp+var_10]
0x140022696  mov     [rbp+var_8], rax
0x14002269a  lea     rax, [rbp+var_10]
0x14002269e  mov     [rbp+var_10], rax
0x1400226a2  call    cs:__imp_KeEnterCriticalRegion
0x1400226a9  nop     dword ptr [rax+rax+00h]
0x1400226ae  lea     rax, [r15+10h]
0x1400226b2  mov     rcx, rax; FastMutex
0x1400226b5  mov     [rbp+FastMutex], rax
0x1400226b9  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400226c0  nop     dword ptr [rax+rax+00h]
0x1400226c5  cmp     byte ptr [r15+189h], 0
0x1400226cd  jnz     loc_140022AE1
0x1400226d3  xor     r13d, r13d
0x1400226d6  lea     rdi, aDereferenceObj; "Dereference object"
0x1400226dd  test    r14d, r14d
0x1400226e0  jz      loc_1400228BE
0x1400226e6  lea     rsi, ds:0[r13*2]
0x1400226ee  mov     r8d, 10h; Size
0x1400226f4  add     rsi, r13
0x1400226f7  lea     rdx, HV_GUID_BROADCAST; Buf2
0x1400226fe  shl     rsi, 4
0x140022702  add     rsi, rbx
0x140022705  mov     rcx, rsi; Buf1
0x140022708  call    memcmp
0x14002270d  test    eax, eax
0x14002270f  jz      loc_140022898
0x140022715  mov     r8d, 10h; Size
0x14002271b  lea     rdx, HV_GUID_ZERO; Buf2
0x140022722  mov     rcx, rsi; Buf1
0x140022725  call    memcmp
0x14002272a  test    eax, eax
0x14002272c  jz      loc_140022898
0x140022732  mov     rdx, rsi
0x140022735  mov     rcx, r15
0x140022738  call    VmbusTlFindAndReferenceService
0x14002273d  mov     [rbp+var_20], rax
0x140022741  mov     rbx, rax
0x140022744  test    rax, rax
0x140022747  jz      loc_14002280C
0x14002274d  add     rax, 60h ; '`'
0x140022751  mov     rcx, [rax]
0x140022754  cmp     [rcx+8], rax
0x140022758  jnz     loc_140022B03
0x14002275e  mov     rdx, [rax+8]
0x140022762  cmp     [rdx], rax
0x140022765  jnz     loc_140022B03
0x14002276b  mov     [rdx], rcx
0x14002276e  mov     [rcx+8], rdx
0x140022772  mov     [rax+8], rax
0x140022776  mov     [rax], rax
0x140022779  mov     eax, cs:dword_140013058
0x14002277f  cmp     eax, 5
0x140022782  jbe     short loc_1400227A1
0x140022784  mov     r9, [rbx+8]
0x140022788  lea     rcx, aVmbustlupdates_4; "VmbusTlUpdateServiceTable"
0x14002278f  mov     r8, rbx
0x140022792  mov     [rsp+50h+var_30], rdi
0x140022797  mov     edx, 3BDh
0x14002279c  call    HvsocketTraceReferenceCount
0x1400227a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400227a5  lock xadd [rbx+8], rax
0x1400227ab  sub     rax, 1
0x1400227af  jg      loc_14002284F
0x1400227b5  test    rax, rax
0x1400227b8  jnz     short loc_140022803
0x1400227ba  mov     rax, [rbx+50h]
0x1400227be  test    rax, rax
0x1400227c1  jz      short loc_1400227CB
0x1400227c3  mov     rcx, rbx
0x1400227c6  call    _guard_dispatch_icall
0x1400227cb  mov     ecx, [rbx+58h]
0x1400227ce  sub     ecx, 1
0x1400227d1  jz      short loc_1400227ED
0x1400227d3  cmp     ecx, 1
0x1400227d6  jnz     short loc_14002284F
0x1400227d8  mov     rcx, [rbx+60h]; Lookaside
0x1400227dc  mov     rdx, rbx; Entry
0x1400227df  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400227e6  nop     dword ptr [rax+rax+00h]
0x1400227eb  jmp     short loc_14002284F
0x1400227ed  mov     edx, 69706E56h; Tag
0x1400227f2  mov     rcx, rbx; P
0x1400227f5  call    cs:__imp_ExFreePoolWithTag
0x1400227fc  nop     dword ptr [rax+rax+00h]
0x140022801  jmp     short loc_14002284F
0x140022803  mov     ecx, 0Eh
0x140022808  int     29h; Win8: RtlFailFast(ecx)
0x14002280a  jmp     short loc_14002284F
0x14002280c  lea     rcx, [rbp+var_20]
0x140022810  call    VmbusTlCreateService
0x140022815  mov     edi, eax
0x140022817  test    eax, eax
0x140022819  mov     eax, cs:dword_140013058
0x14002281f  js      loc_140022A82
0x140022825  cmp     eax, 4
0x140022828  jbe     short loc_140022839
0x14002282a  mov     rdx, rsi
0x14002282d  lea     rcx, aVmbustlupdates; "VmbusTlUpdateServiceTable: Service crea"...
0x140022834  call    HvsocketTraceMessage
0x140022839  mov     rbx, [rbp+var_20]
0x14002283d  movups  xmm0, xmmword ptr [rsi]
0x140022840  movdqu  xmmword ptr [rbx+70h], xmm0
0x140022845  mov     dword ptr [rbx+9Ch], 0
0x14002284f  mov     r8, rbx
0x140022852  mov     rcx, rsi
0x140022855  call    VmbusTlUpdateService
0x14002285a  mov     edi, eax
0x14002285c  test    eax, eax
0x14002285e  js      loc_1400229BF
0x140022864  mov     rcx, [rbp+var_8]
0x140022868  lea     rax, [rbp+var_10]
0x14002286c  cmp     [rcx], rax
0x14002286f  jnz     loc_140022B03
0x140022875  lea     rax, [rbx+60h]
0x140022879  mov     rbx, [rbp+arg_8]
0x14002287d  mov     [rax+8], rcx
0x140022881  lea     rdx, [rbp+var_10]
0x140022885  mov     [rax], rdx
0x140022888  lea     rdi, aDereferenceObj; "Dereference object"
0x14002288f  mov     [rcx], rax
0x140022892  mov     [rbp+var_8], rax
0x140022896  jmp     short loc_1400228B2
0x140022898  mov     eax, cs:dword_140013058
0x14002289e  cmp     eax, 4
0x1400228a1  jbe     short loc_1400228B2
0x1400228a3  mov     rdx, rsi
0x1400228a6  lea     rcx, aVmbustlupdates_2; "VmbusTlUpdateServiceTable: Invalid serv"...
0x1400228ad  call    HvsocketTraceMessage
0x1400228b2  inc     r13d
0x1400228b5  cmp     r13d, r14d
0x1400228b8  jb      loc_1400226E6
0x1400228be  lea     rsi, [r15+168h]
0x1400228c5  mov     rdi, [rsi]
0x1400228c8  cmp     rdi, rsi
0x1400228cb  jz      loc_140022AD5
0x1400228d1  lea     r15, aDereferenceObj; "Dereference object"
0x1400228d8  mov     r14, [rdi]
0x1400228db  lea     rbx, [rdi-60h]
0x1400228df  cmp     dword ptr [rbx+9Ch], 0
0x1400228e6  jnz     loc_140022AC9
0x1400228ec  mov     eax, cs:dword_140013058
0x1400228f2  cmp     eax, 4
0x1400228f5  jbe     short loc_140022907
0x1400228f7  lea     rdx, [rbx+70h]
0x1400228fb  lea     rcx, aVmbustlupdates_5; "VmbusTlUpdateServiceTable: Removing ser"...
0x140022902  call    HvsocketTraceMessage
0x140022907  xor     edx, edx
0x140022909  mov     rcx, rbx
0x14002290c  call    VmbusTlCloseServiceEndpoints
0x140022911  lea     rax, [rbx+60h]
0x140022915  mov     rdx, [rax]
0x140022918  cmp     [rdx+8], rax
0x14002291c  jnz     loc_140022B03
0x140022922  mov     rcx, [rax+8]
0x140022926  cmp     [rcx], rax
0x140022929  jnz     loc_140022B03
0x14002292f  mov     [rcx], rdx
0x140022932  mov     [rdx+8], rcx
0x140022936  mov     [rax+8], rax
0x14002293a  mov     [rax], rax
0x14002293d  mov     eax, cs:dword_140013058
0x140022943  cmp     eax, 5
0x140022946  jbe     short loc_140022965
0x140022948  mov     r9, [rbx+8]
0x14002294c  lea     rcx, aVmbustlupdates_4; "VmbusTlUpdateServiceTable"
0x140022953  mov     r8, rbx
0x140022956  mov     [rsp+50h+var_30], r15
0x14002295b  mov     edx, 3F5h
0x140022960  call    HvsocketTraceReferenceCount
0x140022965  or      rax, 0FFFFFFFFFFFFFFFFh
0x140022969  lock xadd [rbx+8], rax
0x14002296f  sub     rax, 1
0x140022973  jg      loc_140022AC9
0x140022979  test    rax, rax
0x14002297c  jnz     loc_140022AC2
0x140022982  mov     rax, [rbx+50h]
0x140022986  test    rax, rax
0x140022989  jz      short loc_140022993
0x14002298b  mov     rcx, rbx
0x14002298e  call    _guard_dispatch_icall
0x140022993  mov     ecx, [rbx+58h]
0x140022996  sub     ecx, 1
0x140022999  jz      loc_140022AAC
0x14002299f  cmp     ecx, 1
0x1400229a2  jnz     loc_140022AC9
0x1400229a8  mov     rcx, [rdi]; Lookaside
0x1400229ab  mov     rdx, rbx; Entry
0x1400229ae  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400229b5  nop     dword ptr [rax+rax+00h]
0x1400229ba  jmp     loc_140022AC9
0x1400229bf  mov     eax, cs:dword_140013058
0x1400229c5  cmp     eax, 2
0x1400229c8  jbe     short loc_1400229E1
0x1400229ca  mov     r9, rsi
0x1400229cd  lea     rcx, aVmbustlupdates_4; "VmbusTlUpdateServiceTable"
0x1400229d4  mov     r8d, edi
0x1400229d7  mov     edx, 3D7h
0x1400229dc  call    HvsocketTraceGuidError
0x1400229e1  mov     eax, cs:dword_140013058
0x1400229e7  cmp     eax, 5
0x1400229ea  jbe     short loc_140022A10
0x1400229ec  mov     r9, [rbx+8]
0x1400229f0  lea     r15, aDereferenceObj; "Dereference object"
0x1400229f7  mov     r8, rbx
0x1400229fa  mov     [rsp+50h+var_30], r15
0x1400229ff  mov     edx, 3D8h
0x140022a04  lea     rcx, aVmbustlupdates_4; "VmbusTlUpdateServiceTable"
0x140022a0b  call    HvsocketTraceReferenceCount
0x140022a10  or      rax, 0FFFFFFFFFFFFFFFFh
0x140022a14  lock xadd [rbx+8], rax
0x140022a1a  sub     rax, 1
0x140022a1e  jg      loc_140022AE3
0x140022a24  test    rax, rax
0x140022a27  jnz     short loc_140022A79
0x140022a29  mov     rax, [rbx+50h]
0x140022a2d  test    rax, rax
0x140022a30  jz      short loc_140022A3A
0x140022a32  mov     rcx, rbx
0x140022a35  call    _guard_dispatch_icall
0x140022a3a  mov     ecx, [rbx+58h]
0x140022a3d  sub     ecx, 1
0x140022a40  jz      short loc_140022A63
0x140022a42  cmp     ecx, 1
0x140022a45  jnz     loc_140022AE3
0x140022a4b  mov     rcx, [rbx+60h]; Lookaside
0x140022a4f  mov     rdx, rbx; Entry
0x140022a52  call    cs:__imp_ExFreeToNPagedLookasideList
0x140022a59  nop     dword ptr [rax+rax+00h]
0x140022a5e  jmp     loc_140022AE3
0x140022a63  mov     edx, 69706E56h; Tag
0x140022a68  mov     rcx, rbx; P
0x140022a6b  call    cs:__imp_ExFreePoolWithTag
0x140022a72  nop     dword ptr [rax+rax+00h]
0x140022a77  jmp     short loc_140022AE3
0x140022a79  mov     ecx, 0Eh
0x140022a7e  int     29h; Win8: RtlFailFast(ecx)
0x140022a80  jmp     short loc_140022AE3
0x140022a82  cmp     eax, 2
0x140022a85  jbe     short loc_140022AE3
0x140022a87  lea     rax, [r15+0E8h]
0x140022a8e  mov     r9, rsi
0x140022a91  mov     r8d, edi
0x140022a94  mov     [rsp+50h+var_30], rax
0x140022a99  mov     edx, 3C6h
0x140022a9e  lea     rcx, aVmbustlupdates_4; "VmbusTlUpdateServiceTable"
0x140022aa5  call    HvsocketTraceServiceError
0x140022aaa  jmp     short loc_140022AE3
0x140022aac  mov     edx, 69706E56h; Tag
0x140022ab1  mov     rcx, rbx; P
0x140022ab4  call    cs:__imp_ExFreePoolWithTag
0x140022abb  nop     dword ptr [rax+rax+00h]
0x140022ac0  jmp     short loc_140022AC9
0x140022ac2  mov     ecx, 0Eh
0x140022ac7  int     29h; Win8: RtlFailFast(ecx)
0x140022ac9  mov     rdi, r14
0x140022acc  cmp     r14, rsi
0x140022acf  jnz     loc_1400228D8
0x140022ad5  lea     rdx, [rbp+var_10]
0x140022ad9  mov     rcx, rsi
0x140022adc  call    DvAppendList
0x140022ae1  xor     edi, edi
0x140022ae3  mov     rcx, [rbp+FastMutex]; FastMutex
0x140022ae7  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022aee  nop     dword ptr [rax+rax+00h]
0x140022af3  call    cs:__imp_KeLeaveCriticalRegion
0x140022afa  nop     dword ptr [rax+rax+00h]
0x140022aff  mov     eax, edi
0x140022b01  jmp     short loc_140022B37
0x140022b03  mov     ecx, 3
0x140022b08  int     29h; Win8: RtlFailFast(ecx)
0x140022b0a  mov     ecx, cs:dword_140013058
0x140022b10  mov     ebx, 0C000000Dh
0x140022b15  cmp     ecx, 2
0x140022b18  jbe     short loc_140022B35
  ... truncated ...
```
