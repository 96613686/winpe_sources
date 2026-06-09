# VmbusTlProcessNewConnection

- ea: `0x14001bd20`
- end: `0x14001c2c7`
- name: `VmbusTlProcessNewConnection`
- size: `1447`
- prototype: `__int64 __fastcall(__int64, struct _FAST_MUTEX *, __int64, __int64, __int64, __int64, UUID *, int)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001b98c`
- `0x14001cf60`
- `0x1400251e0`
- `0x140025fe0`

## callees

- `0x140001008`
- `0x140001ac8`
- `0x1400023b0`
- `0x140007034`
- `0x14000975c`
- `0x14000a048`
- `0x14000a154`
- `0x14000b86c`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001bd20`
- `0x14001c2d0`
- `0x14001dcf8`
- `0x14001f540`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14001be27`
- `ntoskrnl!ExUuidCreate` at `0x14001be27`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001be97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001be97`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001be8b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001be8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bf41`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c0a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c15e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c28e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bf41`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c0a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c15e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c28e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001be5f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001be5f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bf2b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c091`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c148`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c278`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bf2b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c091`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c148`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001c278`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001be6e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001be6e`

## string_xrefs

- `0x14001bda1`: `Process a new incoming connection request.`

## pseudocode

```c
__int64 __fastcall VmbusTlProcessNewConnection(
        __int64 a1,
        struct _FAST_MUTEX *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        UUID *a7,
        int a8)
{
  struct _FAST_MUTEX *v8; // rbx
  unsigned int v10; // r12d
  __int64 v11; // rdi
  __int64 v12; // r15
  __int64 v13; // r14
  struct _FAST_MUTEX *v14; // rsi
  __int64 v15; // rdi
  char PendingOutboundConnectionFromPartition; // si
  signed __int64 v17; // rax
  bool v18; // cc
  signed __int64 v19; // rax
  void (__fastcall *v20)(__int64); // rax
  char *v21; // rdi
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  signed __int64 v25; // rax
  signed __int64 v26; // rax
  void (__fastcall *v27)(struct _FAST_MUTEX *); // rax
  char v28; // si
  signed __int64 v29; // rax
  signed __int64 v30; // rax
  void (__fastcall *v31)(char *); // rax
  unsigned int v32; // eax
  signed __int64 v33; // rax
  signed __int64 v34; // rax
  void (__fastcall *v35)(struct _FAST_MUTEX *); // rax
  char v37; // [rsp+50h] [rbp-B0h]
  int v38; // [rsp+54h] [rbp-ACh] BYREF
  struct _FAST_MUTEX *v39; // [rsp+58h] [rbp-A8h] BYREF
  PVOID Entry; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  __int64 v43; // [rsp+78h] [rbp-88h]
  UUID Uuid; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45[16]; // [rsp+90h] [rbp-70h] BYREF

  v8 = a2;
  v39 = a2;
  v41 = a1;
  v10 = 0;
  v43 = a4;
  v42 = a6;
  Entry = 0;
  v37 = 0;
  Uuid = 0;
  if ( (unsigned int)dword_140013058 > 4 )
  {
    v45[12] = a6;
    v45[4] = (__int64)"Process a new incoming connection request.";
    v45[5] = 43;
    v45[6] = (__int64)&v38;
    v38 = a8 & 1;
    v45[7] = 4;
    v45[8] = a4;
    v45[9] = 16;
    v45[10] = a3;
    v45[11] = 16;
    v45[13] = 16;
    v45[14] = (__int64)a7;
    v45[15] = 16;
    tlgWriteTransfer_EtwWriteTransfer((int)&dword_140013058, (int)&byte_140011495, a3, a4, 8u, (__int64)v45);
  }
  if ( (a8 & 2) != 0 )
    ExUuidCreate(&Uuid);
  else
    Uuid = *a7;
  if ( (a8 & 1) != 0 )
  {
    v32 = VmbusTlProcessNewConnectionForListener(v41, &v39, a3, v43, a5, v42, a7, &Uuid, a8);
    v8 = v39;
    v10 = v32;
  }
  else
  {
    v11 = v41;
    v12 = v43;
    v13 = v42;
    v14 = (struct _FAST_MUTEX *)(v41 + 16);
    v39 = (struct _FAST_MUTEX *)(v41 + 16);
    while ( 1 )
    {
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe(v14);
      v15 = VmbusTlFindAndReferencePartition(v11, v12);
      ExReleaseFastMutexUnsafe(v14);
      KeLeaveCriticalRegion();
      if ( !v15 )
        break;
      PendingOutboundConnectionFromPartition = HvSocketGetPendingOutboundConnectionFromPartition(v15, v13, a7, &Entry);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"HvSocketGetPendingOutboundConnection",
          1638,
          v15,
          *(_QWORD *)(v15 + 8),
          (__int64)"Dereference object");
      v17 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v15 + 8), 0xFFFFFFFFFFFFFFFFuLL);
      v18 = v17 <= 1;
      v19 = v17 - 1;
      if ( v18 )
      {
        if ( v19 )
          __fastfail(0xEu);
        v20 = *(void (__fastcall **)(__int64))(v15 + 80);
        if ( v20 )
          v20(v15);
        if ( *(_DWORD *)(v15 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v15, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v15 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v15 + 96), (PVOID)v15);
        }
      }
      if ( !PendingOutboundConnectionFromPartition )
        goto LABEL_61;
      v21 = (char *)Entry;
      if ( (unsigned __int8)HvSocketBeginProcessingConnection(Entry) )
      {
        if ( !memcmp(v21 + 464, &HV_GUID_ZERO, 0x10u)
          && (v38 = VmbusTlSetEndpointId(v21, &Uuid), v22 = (unsigned int)v38, v38 < 0) )
        {
          if ( (unsigned int)dword_140013058 > 2 )
            HvsocketTraceEndpointError("VmbusTlProcessNewConnectionForConnectRequest", 465, (unsigned int)v38, v21);
        }
        else
        {
          v38 = (*(__int64 (__fastcall **)(struct _FAST_MUTEX *, char *, __int64))(*((_QWORD *)v21 + 92) + 120LL))(
                  v8,
                  v21,
                  v22);
          if ( v38 == 259 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v24, v23, 259);
          }
          else if ( v38 < 0 && (unsigned int)dword_140013058 > 2 )
          {
            HvsocketTraceEndpointError("VmbusTlProcessNewConnectionForConnectRequest", 479, (unsigned int)v38, v21);
          }
          if ( v8 )
          {
            if ( (unsigned int)dword_140013058 > 5 )
              HvsocketTraceReferenceCount(
                (unsigned int)"VmbusTlProcessNewConnectionForConnectRequest",
                484,
                (_DWORD)v8,
                v8->Owner,
                (__int64)"Dereference object");
            v25 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v8->Owner, 0xFFFFFFFFFFFFFFFFuLL);
            v18 = v25 <= 1;
            v26 = v25 - 1;
            if ( v18 )
            {
              if ( v26 )
                __fastfail(0xEu);
              v27 = *(void (__fastcall **)(struct _FAST_MUTEX *))&v8[1].Event.Header.Lock;
              if ( v27 )
                v27(v8);
              if ( LODWORD(v8[1].Event.Header.WaitListHead.Flink) == 1 )
              {
                ExFreePoolWithTag(v8, 0x69706E56u);
              }
              else if ( LODWORD(v8[1].Event.Header.WaitListHead.Flink) == 2 )
              {
                ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v8[1].Event.Header.WaitListHead.Blink, v8);
              }
            }
            v8 = 0;
          }
        }
        VmbusTlConnectComplete(v21);
        v10 = v38;
        v28 = v37;
      }
      else
      {
        v28 = 1;
        v37 = 1;
      }
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"VmbusTlProcessNewConnection",
          855,
          (_DWORD)v21,
          *((_QWORD *)v21 + 1),
          (__int64)"Dereference object");
      v29 = _InterlockedExchangeAdd64((volatile signed __int64 *)v21 + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v18 = v29 <= 1;
      v30 = v29 - 1;
      if ( v18 )
      {
        if ( v30 )
          __fastfail(0xEu);
        v31 = (void (__fastcall *)(char *))*((_QWORD *)v21 + 10);
        if ( v31 )
          v31(v21);
        if ( *((_DWORD *)v21 + 22) == 1 )
        {
          ExFreePoolWithTag(v21, 0x69706E56u);
        }
        else if ( *((_DWORD *)v21 + 22) == 2 )
        {
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v21 + 12), v21);
        }
      }
      Entry = 0;
      if ( !v28 )
        goto LABEL_63;
      v14 = v39;
      v11 = v41;
    }
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError((unsigned int)"HvSocketGetPendingOutboundConnection", 1629, -1073741275, v13, v12);
LABEL_61:
    v10 = -1073741275;
  }
LABEL_63:
  if ( v8 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlProcessNewConnection",
        883,
        (_DWORD)v8,
        v8->Owner,
        (__int64)"Dereference object");
    v33 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v8->Owner, 0xFFFFFFFFFFFFFFFFuLL);
    v18 = v33 <= 1;
    v34 = v33 - 1;
    if ( v18 )
    {
      if ( v34 )
        __fastfail(0xEu);
      v35 = *(void (__fastcall **)(struct _FAST_MUTEX *))&v8[1].Event.Header.Lock;
      if ( v35 )
        v35(v8);
      if ( LODWORD(v8[1].Event.Header.WaitListHead.Flink) == 1 )
      {
        ExFreePoolWithTag(v8, 0x69706E56u);
      }
      else if ( LODWORD(v8[1].Event.Header.WaitListHead.Flink) == 2 )
      {
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v8[1].Event.Header.WaitListHead.Blink, v8);
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14001bd20  push    rbp
0x14001bd22  push    rbx
0x14001bd23  push    rsi
0x14001bd24  push    rdi
0x14001bd25  push    r12
0x14001bd27  push    r13
0x14001bd29  push    r14
0x14001bd2b  push    r15
0x14001bd2d  lea     rbp, [rsp-28h]
0x14001bd32  sub     rsp, 128h
0x14001bd39  mov     rax, cs:__security_cookie
0x14001bd40  xor     rax, rsp
0x14001bd43  mov     [rbp+60h+var_50], rax
0x14001bd47  mov     esi, [rbp+60h+arg_38]
0x14001bd4d  mov     rbx, rdx
0x14001bd50  mov     eax, cs:dword_140013058
0x14001bd56  mov     edi, esi
0x14001bd58  mov     r15, [rbp+60h+arg_20]
0x14001bd5f  and     edi, 1
0x14001bd62  mov     r13, [rbp+60h+arg_30]
0x14001bd69  xorps   xmm0, xmm0
0x14001bd6c  mov     [rsp+160h+var_108], rdx
0x14001bd71  mov     r14, r8
0x14001bd74  xor     edx, edx
0x14001bd76  mov     [rsp+160h+var_F8], rcx
0x14001bd7b  mov     rcx, [rbp+60h+arg_28]
0x14001bd82  mov     r12d, edx
0x14001bd85  mov     [rsp+160h+var_E8], r9
0x14001bd8a  mov     [rsp+160h+var_F0], rcx
0x14001bd8f  mov     [rsp+160h+Entry], rdx
0x14001bd94  mov     [rsp+160h+var_110], dl
0x14001bd98  movups  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x14001bd9c  cmp     eax, 4
0x14001bd9f  jbe     short loc_14001BE1D
0x14001bda1  lea     rax, aProcessANewInc; "Process a new incoming connection reque"...
0x14001bda8  mov     [rbp+60h+var_70], rcx
0x14001bdac  mov     [rbp+60h+var_B0], rax
0x14001bdb0  lea     rdx, byte_140011495; int
0x14001bdb7  lea     rax, [rsp+160h+var_10C]
0x14001bdbc  mov     [rbp+60h+var_A8], 2Bh ; '+'
0x14001bdc4  mov     [rbp+60h+var_A0], rax
0x14001bdc8  lea     rcx, dword_140013058; int
0x14001bdcf  lea     rax, [rbp+60h+var_D0]
0x14001bdd3  mov     [rsp+160h+var_10C], edi
0x14001bdd7  mov     [rsp+160h+var_138], rax; __int64
0x14001bddc  mov     [rsp+160h+var_140], 8; ULONG
0x14001bde4  mov     [rbp+60h+var_98], 4
0x14001bdec  mov     [rbp+60h+var_90], r9
0x14001bdf0  mov     [rbp+60h+var_88], 10h
0x14001bdf8  mov     [rbp+60h+var_80], r8
0x14001bdfc  mov     [rbp+60h+var_78], 10h
0x14001be04  mov     [rbp+60h+var_68], 10h
0x14001be0c  mov     [rbp+60h+var_60], r13
0x14001be10  mov     [rbp+60h+var_58], 10h
0x14001be18  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001be1d  test    sil, 2
0x14001be21  jz      short loc_14001BE35
0x14001be23  lea     rcx, [rbp+60h+Uuid]; Uuid
0x14001be27  call    cs:__imp_ExUuidCreate
0x14001be2e  nop     dword ptr [rax+rax+00h]
0x14001be33  jmp     short loc_14001BE3F
0x14001be35  movups  xmm0, xmmword ptr [r13+0]
0x14001be3a  movdqu  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x14001be3f  test    edi, edi
0x14001be41  jnz     loc_14001C1C6
0x14001be47  mov     rdi, [rsp+160h+var_F8]
0x14001be4c  mov     r15, [rsp+160h+var_E8]
0x14001be51  mov     r14, [rsp+160h+var_F0]
0x14001be56  lea     rsi, [rdi+10h]
0x14001be5a  mov     [rsp+160h+var_108], rsi
0x14001be5f  call    cs:__imp_KeEnterCriticalRegion
0x14001be66  nop     dword ptr [rax+rax+00h]
0x14001be6b  mov     rcx, rsi; FastMutex
0x14001be6e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001be75  nop     dword ptr [rax+rax+00h]
0x14001be7a  mov     rdx, r15
0x14001be7d  mov     rcx, rdi
0x14001be80  call    VmbusTlFindAndReferencePartition
0x14001be85  mov     rcx, rsi; FastMutex
0x14001be88  mov     rdi, rax
0x14001be8b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001be92  nop     dword ptr [rax+rax+00h]
0x14001be97  call    cs:__imp_KeLeaveCriticalRegion
0x14001be9e  nop     dword ptr [rax+rax+00h]
0x14001bea3  test    rdi, rdi
0x14001bea6  jz      loc_14001C194
0x14001beac  lea     r9, [rsp+160h+Entry]
0x14001beb1  mov     r8, r13
0x14001beb4  mov     rdx, r14
0x14001beb7  mov     rcx, rdi
0x14001beba  call    HvSocketGetPendingOutboundConnectionFromPartition
0x14001bebf  mov     sil, al
0x14001bec2  mov     eax, cs:dword_140013058
0x14001bec8  cmp     eax, 5
0x14001becb  jbe     short loc_14001BEF1
0x14001becd  mov     r9, [rdi+8]
0x14001bed1  lea     rax, aDereferenceObj; "Dereference object"
0x14001bed8  mov     r8, rdi
0x14001bedb  mov     qword ptr [rsp+160h+var_140], rax
0x14001bee0  mov     edx, 666h
0x14001bee5  lea     rcx, aHvsocketgetpen_2; "HvSocketGetPendingOutboundConnection"
0x14001beec  call    HvsocketTraceReferenceCount
0x14001bef1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001bef5  lock xadd [rdi+8], rax
0x14001befb  sub     rax, 1
0x14001beff  jg      short loc_14001BF56
0x14001bf01  test    rax, rax
0x14001bf04  jnz     short loc_14001BF4F
0x14001bf06  mov     rax, [rdi+50h]
0x14001bf0a  test    rax, rax
0x14001bf0d  jz      short loc_14001BF17
0x14001bf0f  mov     rcx, rdi
0x14001bf12  call    _guard_dispatch_icall
0x14001bf17  mov     ecx, [rdi+58h]
0x14001bf1a  sub     ecx, 1
0x14001bf1d  jz      short loc_14001BF39
0x14001bf1f  cmp     ecx, 1
0x14001bf22  jnz     short loc_14001BF56
0x14001bf24  mov     rcx, [rdi+60h]; Lookaside
0x14001bf28  mov     rdx, rdi; Entry
0x14001bf2b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001bf32  nop     dword ptr [rax+rax+00h]
0x14001bf37  jmp     short loc_14001BF56
0x14001bf39  mov     edx, 69706E56h; Tag
0x14001bf3e  mov     rcx, rdi; P
0x14001bf41  call    cs:__imp_ExFreePoolWithTag
0x14001bf48  nop     dword ptr [rax+rax+00h]
0x14001bf4d  jmp     short loc_14001BF56
0x14001bf4f  mov     ecx, 0Eh
0x14001bf54  int     29h; Win8: RtlFailFast(ecx)
0x14001bf56  test    sil, sil
0x14001bf59  jz      loc_14001C1BE
0x14001bf5f  mov     rdi, [rsp+160h+Entry]
0x14001bf64  mov     rcx, rdi
0x14001bf67  call    HvSocketBeginProcessingConnection
0x14001bf6c  test    al, al
0x14001bf6e  jz      loc_14001C0D7
0x14001bf74  lea     rcx, [rdi+1D0h]; Buf1
0x14001bf7b  mov     r8d, 10h; Size
0x14001bf81  lea     rdx, HV_GUID_ZERO; Buf2
0x14001bf88  call    memcmp
0x14001bf8d  test    eax, eax
0x14001bf8f  jnz     short loc_14001BFD0
0x14001bf91  lea     rdx, [rbp+60h+Uuid]
0x14001bf95  mov     rcx, rdi
0x14001bf98  call    VmbusTlSetEndpointId
0x14001bf9d  mov     [rsp+160h+var_10C], eax
0x14001bfa1  mov     r8d, eax
0x14001bfa4  test    eax, eax
0x14001bfa6  jns     short loc_14001BFD0
0x14001bfa8  mov     eax, cs:dword_140013058
0x14001bfae  cmp     eax, 2
0x14001bfb1  jbe     loc_14001C0BE
0x14001bfb7  mov     r9, rdi
0x14001bfba  lea     rcx, aVmbustlprocess_1; "VmbusTlProcessNewConnectionForConnectRe"...
0x14001bfc1  mov     edx, 1D1h
0x14001bfc6  call    HvsocketTraceEndpointError
0x14001bfcb  jmp     loc_14001C0BE
0x14001bfd0  mov     rax, [rdi+2E0h]
0x14001bfd7  mov     rdx, rdi
0x14001bfda  mov     rcx, rbx
0x14001bfdd  mov     rax, [rax+78h]
0x14001bfe1  call    _guard_dispatch_icall
0x14001bfe6  mov     [rsp+160h+var_10C], eax
0x14001bfea  mov     r8d, eax
0x14001bfed  cmp     eax, 103h
0x14001bff2  jnz     short loc_14001BFFB
0x14001bff4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001bff9  jmp     short loc_14001C01F
0x14001bffb  test    r8d, r8d
0x14001bffe  jns     short loc_14001C01F
0x14001c000  mov     eax, cs:dword_140013058
0x14001c006  cmp     eax, 2
0x14001c009  jbe     short loc_14001C01F
0x14001c00b  mov     r9, rdi
0x14001c00e  lea     rcx, aVmbustlprocess_1; "VmbusTlProcessNewConnectionForConnectRe"...
0x14001c015  mov     edx, 1DFh
0x14001c01a  call    HvsocketTraceEndpointError
0x14001c01f  test    rbx, rbx
0x14001c022  jz      loc_14001C0BE
0x14001c028  mov     eax, cs:dword_140013058
0x14001c02e  cmp     eax, 5
0x14001c031  jbe     short loc_14001C057
0x14001c033  mov     r9, [rbx+8]
0x14001c037  lea     rax, aDereferenceObj; "Dereference object"
0x14001c03e  mov     r8, rbx
0x14001c041  mov     qword ptr [rsp+160h+var_140], rax
0x14001c046  mov     edx, 1E4h
0x14001c04b  lea     rcx, aVmbustlprocess_1; "VmbusTlProcessNewConnectionForConnectRe"...
0x14001c052  call    HvsocketTraceReferenceCount
0x14001c057  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c05b  lock xadd [rbx+8], rax
0x14001c061  sub     rax, 1
0x14001c065  jg      short loc_14001C0BC
0x14001c067  test    rax, rax
0x14001c06a  jnz     short loc_14001C0B5
0x14001c06c  mov     rax, [rbx+50h]
0x14001c070  test    rax, rax
0x14001c073  jz      short loc_14001C07D
0x14001c075  mov     rcx, rbx
0x14001c078  call    _guard_dispatch_icall
0x14001c07d  mov     ecx, [rbx+58h]
0x14001c080  sub     ecx, 1
0x14001c083  jz      short loc_14001C09F
0x14001c085  cmp     ecx, 1
0x14001c088  jnz     short loc_14001C0BC
0x14001c08a  mov     rcx, [rbx+60h]; Lookaside
0x14001c08e  mov     rdx, rbx; Entry
0x14001c091  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001c098  nop     dword ptr [rax+rax+00h]
0x14001c09d  jmp     short loc_14001C0BC
0x14001c09f  mov     edx, 69706E56h; Tag
0x14001c0a4  mov     rcx, rbx; P
0x14001c0a7  call    cs:__imp_ExFreePoolWithTag
0x14001c0ae  nop     dword ptr [rax+rax+00h]
0x14001c0b3  jmp     short loc_14001C0BC
0x14001c0b5  mov     ecx, 0Eh
0x14001c0ba  int     29h; Win8: RtlFailFast(ecx)
0x14001c0bc  xor     ebx, ebx
0x14001c0be  lea     rdx, [rsp+160h+var_10C]
0x14001c0c3  mov     rcx, rdi; P
0x14001c0c6  call    VmbusTlConnectComplete
0x14001c0cb  mov     r12d, [rsp+160h+var_10C]
0x14001c0d0  mov     sil, [rsp+160h+var_110]
0x14001c0d5  jmp     short loc_14001C0DF
0x14001c0d7  mov     sil, 1
0x14001c0da  mov     [rsp+160h+var_110], sil
0x14001c0df  mov     eax, cs:dword_140013058
0x14001c0e5  cmp     eax, 5
0x14001c0e8  jbe     short loc_14001C10E
0x14001c0ea  mov     r9, [rdi+8]
0x14001c0ee  lea     rax, aDereferenceObj; "Dereference object"
0x14001c0f5  mov     r8, rdi
0x14001c0f8  mov     qword ptr [rsp+160h+var_140], rax
0x14001c0fd  mov     edx, 357h
0x14001c102  lea     rcx, aVmbustlprocess_0; "VmbusTlProcessNewConnection"
0x14001c109  call    HvsocketTraceReferenceCount
0x14001c10e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c112  lock xadd [rdi+8], rax
0x14001c118  sub     rax, 1
0x14001c11c  jg      short loc_14001C173
0x14001c11e  test    rax, rax
0x14001c121  jnz     short loc_14001C16C
0x14001c123  mov     rax, [rdi+50h]
0x14001c127  test    rax, rax
0x14001c12a  jz      short loc_14001C134
0x14001c12c  mov     rcx, rdi
0x14001c12f  call    _guard_dispatch_icall
0x14001c134  mov     ecx, [rdi+58h]
0x14001c137  sub     ecx, 1
0x14001c13a  jz      short loc_14001C156
0x14001c13c  cmp     ecx, 1
0x14001c13f  jnz     short loc_14001C173
0x14001c141  mov     rcx, [rdi+60h]; Lookaside
0x14001c145  mov     rdx, rdi; Entry
0x14001c148  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001c14f  nop     dword ptr [rax+rax+00h]
0x14001c154  jmp     short loc_14001C173
0x14001c156  mov     edx, 69706E56h; Tag
0x14001c15b  mov     rcx, rdi; P
0x14001c15e  call    cs:__imp_ExFreePoolWithTag
0x14001c165  nop     dword ptr [rax+rax+00h]
0x14001c16a  jmp     short loc_14001C173
0x14001c16c  mov     ecx, 0Eh
0x14001c171  int     29h; Win8: RtlFailFast(ecx)
0x14001c173  mov     [rsp+160h+Entry], 0
0x14001c17c  test    sil, sil
0x14001c17f  jz      loc_14001C206
0x14001c185  mov     rsi, [rsp+160h+var_108]
0x14001c18a  mov     rdi, [rsp+160h+var_F8]
0x14001c18f  jmp     loc_14001BE5F
0x14001c194  mov     eax, cs:dword_140013058
0x14001c19a  cmp     eax, 2
0x14001c19d  jbe     short loc_14001C1BE
0x14001c19f  mov     r9, r14
0x14001c1a2  mov     qword ptr [rsp+160h+var_140], r15
0x14001c1a7  mov     edx, 65Dh
0x14001c1ac  lea     rcx, aHvsocketgetpen_2; "HvSocketGetPendingOutboundConnection"
0x14001c1b3  mov     r8d, 0C0000225h
0x14001c1b9  call    HvsocketTraceServiceError
0x14001c1be  mov     r12d, 0C0000225h
0x14001c1c4  jmp     short loc_14001C206
0x14001c1c6  mov     r9, [rsp+160h+var_E8]
0x14001c1cb  lea     rax, [rbp+60h+Uuid]
0x14001c1cf  mov     rcx, [rsp+160h+var_F8]
0x14001c1d4  lea     rdx, [rsp+160h+var_108]
0x14001c1d9  mov     [rsp+160h+var_120], esi
0x14001c1dd  mov     r8, r14
0x14001c1e0  mov     [rsp+160h+var_128], rax
0x14001c1e5  mov     rax, [rsp+160h+var_F0]
0x14001c1ea  mov     [rsp+160h+var_130], r13
0x14001c1ef  mov     [rsp+160h+var_138], rax
0x14001c1f4  mov     qword ptr [rsp+160h+var_140], r15
0x14001c1f9  call    VmbusTlProcessNewConnectionForListener
0x14001c1fe  mov     rbx, [rsp+160h+var_108]
0x14001c203  mov     r12d, eax
0x14001c206  test    rbx, rbx
0x14001c209  jz      loc_14001C2A3
0x14001c20f  mov     edx, cs:dword_140013058
0x14001c215  cmp     edx, 5
  ... truncated ...
```
