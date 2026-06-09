# VmbusTlConnectProcessIoRequestLocked

- ea: `0x140007b00`
- end: `0x1400081ed`
- name: `VmbusTlConnectProcessIoRequestLocked`
- size: `1773`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, KIRQL NewIrql)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140008200`
- `0x1400083f0`

## callees

- `0x140003bc8`
- `0x14000483c`
- `0x1400058d0`
- `0x140007b00`
- `0x1400085c8`
- `0x14000975c`
- `0x140009834`
- `0x140009a94`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007e60`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007e60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007bc9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f37`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007bc9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008108`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400081cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008108`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400081cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400080ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400081b7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400080ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400081b7`

## pseudocode

```c
__int64 __fastcall VmbusTlConnectProcessIoRequestLocked(__int64 a1, int a2, __int64 a3, __int64 a4, KIRQL NewIrql)
{
  __int64 v5; // rsi
  int v10; // ebx
  int v12; // ebp
  signed __int64 v13; // rax
  bool v14; // cc
  signed __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rcx
  int v18; // eax
  _QWORD *v19; // r14
  __int64 v20; // rcx
  __int64 v21; // rax
  KIRQL v22; // al
  bool v23; // zf
  _QWORD *v24; // rax
  char v25; // r14
  signed __int64 v26; // rax
  signed __int64 v27; // rax
  void (__fastcall *v28)(__int64); // rax
  signed __int64 v29; // rax
  signed __int64 v30; // rax
  void (__fastcall *v31)(__int64); // rax
  __int64 v32; // [rsp+30h] [rbp-58h]
  __int64 v33; // [rsp+38h] [rbp-50h]
  __int64 v34; // [rsp+90h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 736);
  v34 = 0;
  if ( *(_DWORD *)(a1 + 520) == 4 && *(_DWORD *)(a1 + 524) == 19 || !v5 )
  {
    v10 = -1073741616;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointError("VmbusTlConnectProcessIoRequestLocked", 459, 3221225680LL, a1);
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlConnectProcessIoRequestLocked",
        453,
        v5,
        *(_QWORD *)(v5 + 8),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v5 + 8)) <= 1 )
      __fastfail(0xEu);
    v10 = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 72), NewIrql);
  if ( v10 < 0 )
    return (unsigned int)v10;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlConnectProcessIoRequestLocked",
      471,
      a1,
      *(_QWORD *)(a1 + 304),
      (__int64)"Dispatch call guard.");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 304)) <= 1 )
    __fastfail(0xEu);
  if ( (int)VmbusTlCreateIoRequest(*(_QWORD *)(v5 + 96), *(_QWORD *)(a1 + 112), &v34) >= 0 )
  {
    v16 = v34;
    *(_DWORD *)(v34 + 120) = a2;
    *(_QWORD *)(v16 + 128) = a1;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlConnectProcessIoRequestLocked",
        489,
        a1,
        *(_QWORD *)(a1 + 304),
        (__int64)"Pending I/O request guard.");
    if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 304)) <= 1 )
      __fastfail(0xEu);
    *(_OWORD *)(v16 + 136) = *(_OWORD *)a3;
    *(_OWORD *)(v16 + 152) = *(_OWORD *)(a3 + 16);
    *(_OWORD *)(v16 + 168) = *(_OWORD *)(a3 + 32);
    *(_OWORD *)(v16 + 184) = *(_OWORD *)(a3 + 48);
    *(_OWORD *)(v16 + 200) = *(_OWORD *)(a3 + 64);
    if ( a2 == 1 )
    {
      *(_QWORD *)(v16 + 216) = *(_QWORD *)(a3 + 80);
      v33 = a3;
      v32 = 0;
      *(_QWORD *)(*(_QWORD *)(v16 + 224) + 8LL) = *(_QWORD *)(a3 + 32);
      v17 = *(_QWORD *)(*(_QWORD *)(v16 + 224) + 184LL);
      v18 = *(_DWORD *)(a3 + 48);
      *(_BYTE *)(v17 - 72) = 4;
    }
    else
    {
      v32 = a3;
      v33 = 0;
      *(_QWORD *)(*(_QWORD *)(v16 + 224) + 8LL) = *(_QWORD *)(a3 + 24);
      v17 = *(_QWORD *)(*(_QWORD *)(v16 + 224) + 184LL);
      v18 = *(_DWORD *)(a3 + 40);
      *(_BYTE *)(v17 - 72) = 3;
    }
    *(_DWORD *)(v17 - 64) = v18;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlConnectProcessIoRequestLocked",
        514,
        a1,
        *(_QWORD *)(a1 + 8),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 8)) <= 1 )
      __fastfail(0xEu);
    v19 = (_QWORD *)(v16 + 104);
    *(_QWORD *)(v16 + 112) = v16 + 104;
    *(_QWORD *)(v16 + 104) = v16 + 104;
    v20 = *(_QWORD *)(*(_QWORD *)(v16 + 224) + 184LL);
    *(_QWORD *)(v20 - 16) = *(_QWORD *)(v5 + 144);
    *(_QWORD *)(v20 - 8) = v16;
    *(_BYTE *)(v20 - 69) = -32;
    v21 = *(_QWORD *)(v16 + 224);
    --*(_BYTE *)(v21 + 67);
    *(_QWORD *)(v21 + 184) -= 72LL;
    v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a4 + 16));
    v23 = *(_BYTE *)(a4 + 24) == 0;
    LOBYTE(v34) = v22;
    if ( v23 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(v5 + 136))(a1, v16);
      if ( v12 == 259 )
      {
        v24 = *(_QWORD **)(a4 + 8);
        if ( *v24 != a4 )
          __fastfail(3u);
        *v19 = a4;
        *(_QWORD *)(v16 + 112) = v24;
        *v24 = v19;
        *(_QWORD *)(a4 + 8) = v19;
      }
    }
    else
    {
      v12 = -1073741616;
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceEndpointError("VmbusTlConnectProcessIoRequestLocked", 542, 3221225680LL, a1);
    }
    v25 = 0;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlConnectProcessIoRequestLocked",
        574,
        v16,
        *(_QWORD *)(v16 + 8),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v16 + 8)) <= 1 )
      __fastfail(0xEu);
    KeReleaseSpinLock((PKSPIN_LOCK)(a4 + 16), v34);
    if ( v12 == -1073741616 )
    {
      if ( a2 == 2 )
      {
        *(_QWORD *)(v16 + 184) = 0;
        v25 = 1;
        v12 = 0;
      }
      else if ( a2 == 1 )
      {
        *(_QWORD *)(v16 + 200) = 0;
      }
      goto LABEL_50;
    }
    if ( v12 == -1073741802 )
    {
      v12 = 259;
    }
    else if ( v12 != 259 )
    {
LABEL_50:
      *(_DWORD *)(*(_QWORD *)(v16 + 224) + 48LL) = v12;
      if ( v12 < 0 && (unsigned int)dword_140013058 > 2 )
        HvsocketTraceEndpointIoRequestError(
          (unsigned int)"VmbusTlConnectProcessIoRequestLocked",
          609,
          v12,
          a1,
          *(_QWORD *)(v16 + 240));
      if ( a2 == 2 )
      {
        *(_QWORD *)(v32 + 48) = *(_QWORD *)(v16 + 184);
      }
      else if ( a2 == 1 )
      {
        *(_QWORD *)(v33 + 64) = *(_QWORD *)(v16 + 200);
        if ( v12 == -1073741811 )
          *(_BYTE *)(v16 + 248) = 1;
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(v5 + 144))(0, *(_QWORD *)(v16 + 224), v16);
      if ( a2 == 2 && !v12 && !*(_QWORD *)(v16 + 184) && !v25 )
      {
        VmbusTlCommonOppositeEndpointDisconnectRequest(a1);
        v25 = 1;
      }
      if ( !*(_BYTE *)(v16 + 248) )
        v12 = 259;
    }
    if ( a2 == 2 && !v25 )
      VmbusTlpActivateDeliveryQueue(a1, 0);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlConnectProcessIoRequestLocked",
        655,
        v16,
        *(_QWORD *)(v16 + 8),
        (__int64)"Dereference object");
    v26 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v16 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v14 = v26 <= 1;
    v27 = v26 - 1;
    if ( v14 )
    {
      if ( v27 )
        __fastfail(0xEu);
      v28 = *(void (__fastcall **)(__int64))(v16 + 80);
      if ( v28 )
        v28(v16);
      if ( *(_DWORD *)(v16 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v16, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v16 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v16 + 96), (PVOID)v16);
      }
    }
    goto LABEL_20;
  }
  v12 = -1073741670;
  if ( (unsigned int)dword_140013058 > 2 )
    HvsocketTraceEndpointError("VmbusTlConnectProcessIoRequestLocked", 481, 3221225626LL, a1);
LABEL_20:
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlConnectProcessIoRequestLocked",
      659,
      a1,
      *(_QWORD *)(a1 + 304),
      (__int64)"Dispatch call guard. (deref)");
  v13 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 304), 0xFFFFFFFFFFFFFFFFuLL);
  v14 = v13 <= 1;
  v15 = v13 - 1;
  if ( v14 )
  {
    if ( v15 )
      __fastfail(0xEu);
    if ( (unsigned int)dword_140013058 > 4 )
      HvsocketTraceEndpointEvent("VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", a1, 9);
    VmbusTlQueueEndpointAction(a1, a1 + 200, 9);
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlConnectProcessIoRequestLocked",
      660,
      v5,
      *(_QWORD *)(v5 + 8),
      (__int64)"Dereference object");
  v29 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v5 + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v14 = v29 <= 1;
  v30 = v29 - 1;
  if ( v14 )
  {
    if ( v30 )
      __fastfail(0xEu);
    v31 = *(void (__fastcall **)(__int64))(v5 + 80);
    if ( v31 )
      v31(v5);
    if ( *(_DWORD *)(v5 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v5, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v5 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 96), (PVOID)v5);
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140007b00  mov     rax, rsp
0x140007b03  push    rbx
0x140007b04  push    rbp
0x140007b05  push    rsi
0x140007b06  push    rdi
0x140007b07  push    r12
0x140007b09  push    r13
0x140007b0b  push    r14
0x140007b0d  push    r15
0x140007b0f  sub     rsp, 48h
0x140007b13  mov     rsi, [rcx+2E0h]
0x140007b1a  lea     r12, aVmbustlconnect_1; "VmbusTlConnectProcessIoRequestLocked"
0x140007b21  mov     rdi, rcx
0x140007b24  mov     qword ptr [rax+8], 0
0x140007b2c  mov     r15d, edx
0x140007b2f  mov     r13, r9
0x140007b32  mov     rbp, r8
0x140007b35  lea     rdx, aReferenceObjec; "Reference object"
0x140007b3c  mov     ecx, 0C00000D0h
0x140007b41  mov     r14d, 1
0x140007b47  cmp     dword ptr [rdi+208h], 4
0x140007b4e  jnz     short loc_140007B59
0x140007b50  cmp     dword ptr [rdi+20Ch], 13h
0x140007b57  jz      short loc_140007B9E
0x140007b59  test    rsi, rsi
0x140007b5c  jz      short loc_140007B9E
0x140007b5e  mov     eax, cs:dword_140013058
0x140007b64  cmp     eax, 5
0x140007b67  jbe     short loc_140007B82
0x140007b69  mov     r9, [rsi+8]
0x140007b6d  mov     r8, rsi
0x140007b70  mov     [rsp+88h+var_68], rdx
0x140007b75  mov     rcx, r12
0x140007b78  mov     edx, 1C5h
0x140007b7d  call    HvsocketTraceReferenceCount
0x140007b82  mov     rax, r14
0x140007b85  lock xadd [rsi+8], rax
0x140007b8b  add     rax, r14
0x140007b8e  cmp     rax, r14
0x140007b91  jg      short loc_140007B9A
0x140007b93  mov     ecx, 0Eh
0x140007b98  int     29h; Win8: RtlFailFast(ecx)
0x140007b9a  xor     ebx, ebx
0x140007b9c  jmp     short loc_140007BBE
0x140007b9e  mov     eax, cs:dword_140013058
0x140007ba4  mov     ebx, ecx
0x140007ba6  cmp     eax, 2
0x140007ba9  jbe     short loc_140007BBE
0x140007bab  mov     r8d, ecx
0x140007bae  mov     r9, rdi
0x140007bb1  mov     rcx, r12
0x140007bb4  mov     edx, 1CBh
0x140007bb9  call    HvsocketTraceEndpointError
0x140007bbe  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x140007bc5  lea     rcx, [rdi+48h]; SpinLock
0x140007bc9  call    cs:__imp_KeReleaseSpinLock
0x140007bd0  nop     dword ptr [rax+rax+00h]
0x140007bd5  test    ebx, ebx
0x140007bd7  jns     short loc_140007BE0
0x140007bd9  mov     eax, ebx
0x140007bdb  jmp     loc_1400081DB
0x140007be0  mov     eax, cs:dword_140013058
0x140007be6  cmp     eax, 5
0x140007be9  jbe     short loc_140007C0E
0x140007beb  mov     r9, [rdi+130h]
0x140007bf2  lea     rax, aDispatchCallGu; "Dispatch call guard."
0x140007bf9  mov     r8, rdi
0x140007bfc  mov     [rsp+88h+var_68], rax
0x140007c01  mov     edx, 1D7h
0x140007c06  mov     rcx, r12
0x140007c09  call    HvsocketTraceReferenceCount
0x140007c0e  mov     rax, r14
0x140007c11  lock xadd [rdi+130h], rax
0x140007c1a  add     rax, r14
0x140007c1d  cmp     rax, r14
0x140007c20  jg      short loc_140007C29
0x140007c22  mov     ecx, 0Eh
0x140007c27  int     29h; Win8: RtlFailFast(ecx)
0x140007c29  mov     rdx, [rdi+70h]
0x140007c2d  lea     r8, [rsp+88h+arg_0]
0x140007c35  mov     rcx, [rsi+60h]
0x140007c39  call    VmbusTlCreateIoRequest
0x140007c3e  test    eax, eax
0x140007c40  jns     loc_140007CCA
0x140007c46  mov     eax, cs:dword_140013058
0x140007c4c  mov     ebp, 0C000009Ah
0x140007c51  cmp     eax, 2
0x140007c54  jbe     short loc_140007C69
0x140007c56  mov     r9, rdi
0x140007c59  mov     r8d, ebp
0x140007c5c  mov     edx, 1E1h
0x140007c61  mov     rcx, r12
0x140007c64  call    HvsocketTraceEndpointError
0x140007c69  lea     r14, aDereferenceObj; "Dereference object"
0x140007c70  mov     eax, cs:dword_140013058
0x140007c76  cmp     eax, 5
0x140007c79  jbe     short loc_140007C9E
0x140007c7b  mov     r9, [rdi+130h]
0x140007c82  lea     rax, aDispatchCallGu_0; "Dispatch call guard. (deref)"
0x140007c89  mov     r8, rdi
0x140007c8c  mov     [rsp+88h+var_68], rax
0x140007c91  mov     edx, 293h
0x140007c96  mov     rcx, r12
0x140007c99  call    HvsocketTraceReferenceCount
0x140007c9e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007ca2  lock xadd [rdi+130h], rax
0x140007cab  sub     rax, 1
0x140007caf  jg      loc_140008150
0x140007cb5  test    rax, rax
0x140007cb8  jz      loc_140008119
0x140007cbe  mov     ecx, 0Eh
0x140007cc3  int     29h; Win8: RtlFailFast(ecx)
0x140007cc5  jmp     loc_140008150
0x140007cca  mov     rbx, [rsp+88h+arg_0]
0x140007cd2  mov     [rbx+78h], r15d
0x140007cd6  mov     [rbx+80h], rdi
0x140007cdd  mov     eax, cs:dword_140013058
0x140007ce3  cmp     eax, 5
0x140007ce6  jbe     short loc_140007D0B
0x140007ce8  mov     r9, [rdi+130h]
0x140007cef  lea     rax, aPendingIOReque; "Pending I/O request guard."
0x140007cf6  mov     r8, rdi
0x140007cf9  mov     [rsp+88h+var_68], rax
0x140007cfe  mov     edx, 1E9h
0x140007d03  mov     rcx, r12
0x140007d06  call    HvsocketTraceReferenceCount
0x140007d0b  mov     rax, r14
0x140007d0e  lock xadd [rdi+130h], rax
0x140007d17  add     rax, r14
0x140007d1a  cmp     rax, r14
0x140007d1d  jg      short loc_140007D26
0x140007d1f  mov     ecx, 0Eh
0x140007d24  int     29h; Win8: RtlFailFast(ecx)
0x140007d26  movups  xmm0, xmmword ptr [rbp+0]
0x140007d2a  movups  xmmword ptr [rbx+88h], xmm0
0x140007d31  movups  xmm1, xmmword ptr [rbp+10h]
0x140007d35  movups  xmmword ptr [rbx+98h], xmm1
0x140007d3c  movups  xmm0, xmmword ptr [rbp+20h]
0x140007d40  movups  xmmword ptr [rbx+0A8h], xmm0
0x140007d47  movups  xmm1, xmmword ptr [rbp+30h]
0x140007d4b  movups  xmmword ptr [rbx+0B8h], xmm1
0x140007d52  movups  xmm0, xmmword ptr [rbp+40h]
0x140007d56  movups  xmmword ptr [rbx+0C8h], xmm0
0x140007d5d  cmp     r15d, r14d
0x140007d60  jnz     short loc_140007DA3
0x140007d62  movsd   xmm1, qword ptr [rbp+50h]
0x140007d67  movsd   qword ptr [rbx+0D8h], xmm1
0x140007d6f  mov     rcx, [rbx+0E0h]
0x140007d76  mov     rax, [rbp+20h]
0x140007d7a  mov     [rsp+88h+var_50], rbp
0x140007d7f  mov     [rsp+88h+var_58], 0
0x140007d88  mov     [rcx+8], rax
0x140007d8c  mov     rax, [rbx+0E0h]
0x140007d93  mov     rcx, [rax+0B8h]
0x140007d9a  mov     eax, [rbp+30h]
0x140007d9d  mov     byte ptr [rcx-48h], 4
0x140007da1  jmp     short loc_140007DD5
0x140007da3  mov     rcx, [rbx+0E0h]
0x140007daa  mov     rax, [rbp+18h]
0x140007dae  mov     [rsp+88h+var_58], rbp
0x140007db3  mov     [rsp+88h+var_50], 0
0x140007dbc  mov     [rcx+8], rax
0x140007dc0  mov     rax, [rbx+0E0h]
0x140007dc7  mov     rcx, [rax+0B8h]
0x140007dce  mov     eax, [rbp+28h]
0x140007dd1  mov     byte ptr [rcx-48h], 3
0x140007dd5  mov     [rcx-40h], eax
0x140007dd8  mov     eax, cs:dword_140013058
0x140007dde  cmp     eax, 5
0x140007de1  jbe     short loc_140007E03
0x140007de3  mov     r9, [rdi+8]
0x140007de7  lea     rax, aReferenceObjec; "Reference object"
0x140007dee  mov     r8, rdi
0x140007df1  mov     [rsp+88h+var_68], rax
0x140007df6  mov     edx, 202h
0x140007dfb  mov     rcx, r12
0x140007dfe  call    HvsocketTraceReferenceCount
0x140007e03  mov     rax, r14
0x140007e06  lock xadd [rdi+8], rax
0x140007e0c  add     rax, r14
0x140007e0f  cmp     rax, r14
0x140007e12  jg      short loc_140007E1B
0x140007e14  mov     ecx, 0Eh
0x140007e19  int     29h; Win8: RtlFailFast(ecx)
0x140007e1b  lea     r14, [rbx+68h]
0x140007e1f  mov     [r14+8], r14
0x140007e23  lea     r12, [r13+10h]
0x140007e27  mov     [r14], r14
0x140007e2a  mov     rax, [rbx+0E0h]
0x140007e31  mov     rcx, [rax+0B8h]
0x140007e38  mov     rax, [rsi+90h]
0x140007e3f  mov     [rcx-10h], rax
0x140007e43  mov     [rcx-8], rbx
0x140007e47  mov     byte ptr [rcx-45h], 0E0h
0x140007e4b  mov     rcx, r12; SpinLock
0x140007e4e  mov     rax, [rbx+0E0h]
0x140007e55  dec     byte ptr [rax+43h]
0x140007e58  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140007e60  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007e67  nop     dword ptr [rax+rax+00h]
0x140007e6c  cmp     byte ptr [r13+18h], 0
0x140007e71  mov     byte ptr [rsp+88h+arg_0], al
0x140007e78  jz      short loc_140007EA5
0x140007e7a  mov     ecx, cs:dword_140013058
0x140007e80  mov     eax, 0C00000D0h
0x140007e85  mov     ebp, eax
0x140007e87  cmp     ecx, 2
0x140007e8a  jbe     short loc_140007EDE
0x140007e8c  mov     r9, rdi
0x140007e8f  lea     rcx, aVmbustlconnect_1; "VmbusTlConnectProcessIoRequestLocked"
0x140007e96  mov     r8d, eax
0x140007e99  mov     edx, 21Eh
0x140007e9e  call    HvsocketTraceEndpointError
0x140007ea3  jmp     short loc_140007EDE
0x140007ea5  mov     rax, [rsi+88h]
0x140007eac  mov     rdx, rbx
0x140007eaf  mov     rcx, rdi
0x140007eb2  call    _guard_dispatch_icall
0x140007eb7  mov     ebp, eax
0x140007eb9  cmp     eax, 103h
0x140007ebe  jnz     short loc_140007EDE
0x140007ec0  mov     rax, [r13+8]
0x140007ec4  cmp     [rax], r13
0x140007ec7  jz      short loc_140007ED0
0x140007ec9  mov     ecx, 3
0x140007ece  int     29h; Win8: RtlFailFast(ecx)
0x140007ed0  mov     [r14], r13
0x140007ed3  mov     [r14+8], rax
0x140007ed7  mov     [rax], r14
0x140007eda  mov     [r13+8], r14
0x140007ede  mov     eax, cs:dword_140013058
0x140007ee4  xor     r14b, r14b
0x140007ee7  cmp     eax, 5
0x140007eea  jbe     short loc_140007F10
0x140007eec  mov     r9, [rbx+8]
0x140007ef0  lea     rax, aReferenceObjec; "Reference object"
0x140007ef7  mov     r8, rbx
0x140007efa  mov     [rsp+88h+var_68], rax
0x140007eff  mov     edx, 23Eh
0x140007f04  lea     rcx, aVmbustlconnect_1; "VmbusTlConnectProcessIoRequestLocked"
0x140007f0b  call    HvsocketTraceReferenceCount
0x140007f10  mov     r13d, 1
0x140007f16  mov     eax, r13d
0x140007f19  lock xadd [rbx+8], rax
0x140007f1f  add     rax, r13
0x140007f22  cmp     rax, r13
0x140007f25  jg      short loc_140007F2D
0x140007f27  lea     ecx, [r13+0Dh]
0x140007f2b  int     29h; Win8: RtlFailFast(ecx)
0x140007f2d  mov     dl, byte ptr [rsp+88h+arg_0]; NewIrql
0x140007f34  mov     rcx, r12; SpinLock
0x140007f37  call    cs:__imp_KeReleaseSpinLock
0x140007f3e  nop     dword ptr [rax+rax+00h]
0x140007f43  cmp     ebp, 0C00000D0h
0x140007f49  jnz     loc_140007FD1
0x140007f4f  cmp     r15d, 2
0x140007f53  jnz     short loc_140007FBF
0x140007f55  mov     qword ptr [rbx+0B8h], 0
0x140007f60  mov     r14b, r13b
0x140007f63  xor     ebp, ebp
0x140007f65  mov     r12d, 103h
0x140007f6b  mov     rax, [rbx+0E0h]
0x140007f72  mov     [rax+30h], ebp
0x140007f75  test    ebp, ebp
0x140007f77  jns     short loc_140007FA7
0x140007f79  mov     eax, cs:dword_140013058
0x140007f7f  cmp     eax, 2
0x140007f82  jbe     short loc_140007FA7
0x140007f84  mov     rax, [rbx+0F0h]
0x140007f8b  lea     rcx, aVmbustlconnect_1; "VmbusTlConnectProcessIoRequestLocked"
0x140007f92  mov     r9, rdi
0x140007f95  mov     [rsp+88h+var_68], rax
0x140007f9a  mov     r8d, ebp
0x140007f9d  mov     edx, 261h
0x140007fa2  call    HvsocketTraceEndpointIoRequestError
0x140007fa7  cmp     r15d, 2
0x140007fab  jnz     short loc_140007FF0
0x140007fad  mov     rcx, [rsp+88h+var_58]
0x140007fb2  mov     rax, [rbx+0B8h]
0x140007fb9  mov     [rcx+30h], rax
0x140007fbd  jmp     short loc_140008014
0x140007fbf  cmp     r15d, r13d
0x140007fc2  jnz     short loc_140007F65
0x140007fc4  mov     qword ptr [rbx+0C8h], 0
0x140007fcf  jmp     short loc_140007F65
0x140007fd1  cmp     ebp, 0C0000016h
0x140007fd7  jnz     short loc_140007FE0
0x140007fd9  mov     ebp, 103h
0x140007fde  jmp     short loc_14000805B
0x140007fe0  mov     r12d, 103h
0x140007fe6  cmp     ebp, r12d
0x140007fe9  jz      short loc_14000805B
0x140007feb  jmp     loc_140007F6B
0x140007ff0  cmp     r15d, r13d
0x140007ff3  jnz     short loc_140008014
0x140007ff5  mov     rcx, [rsp+88h+var_50]
0x140007ffa  mov     rax, [rbx+0C8h]
0x140008001  mov     [rcx+40h], rax
0x140008005  cmp     ebp, 0C000000Dh
0x14000800b  jnz     short loc_140008014
  ... truncated ...
```
