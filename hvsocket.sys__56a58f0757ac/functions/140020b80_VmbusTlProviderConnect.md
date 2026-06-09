# VmbusTlProviderConnect

- ea: `0x140020b80`
- end: `0x1400213c0`
- name: `VmbusTlProviderConnect`
- size: `2112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1400023b0`
- `0x140002d08`
- `0x140004dec`
- `0x1400058d0`
- `0x140009834`
- `0x1400098f4`
- `0x140009cf8`
- `0x140009df0`
- `0x140009ec0`
- `0x14000a048`
- `0x14000a154`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x1400193ec`
- `0x14001954c`
- `0x14001960c`
- `0x1400196a4`
- `0x14001a148`
- `0x14001dfd8`
- `0x14001e1c0`
- `0x14001f540`
- `0x140020b80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140020f89`
- `ntoskrnl!KeSetEvent` at `0x140020f89`
- `ntoskrnl!PsGetSiloContainerId` at `0x140020c53`
- `ntoskrnl!PsGetSiloContainerId` at `0x140020c53`
- `ntoskrnl!PsGetProcessServerSilo` at `0x140020c44`
- `ntoskrnl!PsGetProcessServerSilo` at `0x140020c44`
- `ntoskrnl!PsGetThreadServerSilo` at `0x140020c33`
- `ntoskrnl!PsGetThreadServerSilo` at `0x140020c33`
- `ntoskrnl!KeClearEvent` at `0x140020f39`
- `ntoskrnl!KeClearEvent` at `0x140020f39`
- `ntoskrnl!PsGetCurrentProcess` at `0x140020c1a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140020c1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400210ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400212ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021385`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400210ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400212ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021385`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400210d4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400212d9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002136f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400210d4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400212d9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002136f`
- `ntoskrnl!PsGetProcessId` at `0x140020de8`
- `ntoskrnl!PsGetProcessId` at `0x140020de8`

## pseudocode

```c
__int64 __fastcall VmbusTlProviderConnect(__int64 a1, __int64 a2)
{
  char *v2; // rbx
  __int128 v5; // xmm6
  __int64 v6; // r14
  struct _KPROCESS *CurrentProcess; // r15
  GUID v8; // xmm0
  __int64 ThreadServerSilo; // rax
  __int64 SiloContainerId; // rax
  const GUID *v11; // rcx
  __int64 v12; // rsi
  unsigned int v13; // edi
  __int128 *v14; // rax
  int v15; // edx
  unsigned int ProcessId; // eax
  GUID v17; // xmm0
  __int64 v18; // r8
  signed __int64 v19; // rax
  bool v20; // cc
  signed __int64 v21; // rax
  signed __int64 v22; // rax
  signed __int64 v23; // rax
  void (__fastcall *v24)(char *); // rax
  signed __int64 v25; // rax
  signed __int64 v26; // rax
  signed __int64 v27; // rax
  signed __int64 v28; // rax
  void (__fastcall *v29)(__int64); // rax
  signed __int64 v30; // rax
  signed __int64 v31; // rax
  void (__fastcall *v32)(char *); // rax
  char v34; // [rsp+38h] [rbp-69h]
  int v35; // [rsp+3Ch] [rbp-65h]
  char IsPassthruRequest; // [rsp+40h] [rbp-61h]
  PVOID Entry; // [rsp+48h] [rbp-59h] BYREF
  GUID v38; // [rsp+50h] [rbp-51h] BYREF
  __int128 v39; // [rsp+60h] [rbp-41h] BYREF
  __int128 v40; // [rsp+70h] [rbp-31h] BYREF
  int v41; // [rsp+80h] [rbp-21h]
  GUID v42; // [rsp+88h] [rbp-19h] BYREF
  __int128 v43; // [rsp+98h] [rbp-9h] BYREF

  *(_QWORD *)(a2 + 104) = 0;
  v2 = 0;
  v5 = 0;
  v41 = 0;
  v6 = 0;
  Entry = 0;
  v42 = 0;
  v34 = 0;
  v39 = 0;
  v40 = 0;
  v43 = 0;
  v38 = HV_GUID_ZERO;
  if ( *(int *)(a2 + 16) < 0 && (v6 = *(_QWORD *)(a2 + 24)) != 0 )
  {
    CurrentProcess = *(struct _KPROCESS **)(v6 + 272);
    v8 = *(GUID *)(v6 + 280);
  }
  else
  {
    CurrentProcess = *(struct _KPROCESS **)(a2 + 40);
    if ( !CurrentProcess )
      CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
    if ( *(_QWORD *)(a2 + 48) )
      ThreadServerSilo = PsGetThreadServerSilo();
    else
      ThreadServerSilo = PsGetProcessServerSilo(CurrentProcess);
    SiloContainerId = PsGetSiloContainerId(ThreadServerSilo);
    v11 = &HV_GUID_CHILDREN;
    if ( SiloContainerId )
      v11 = (const GUID *)SiloContainerId;
    v8 = *v11;
  }
  v42 = v8;
  v12 = VmbusTlFindAndReferencePartition(a1, &v42);
  if ( !v12 )
  {
    v13 = -1073741275;
    v35 = -1073741275;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("VmbusTlProviderConnect", 407, 3221226021LL, &v42);
    goto LABEL_66;
  }
  v14 = *(__int128 **)(a2 + 88);
  if ( *(_WORD *)v14 != 34 )
  {
    v13 = -1073741811;
    v35 = -1073741811;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("VmbusTlProviderConnect", 418, 3221225485LL, "Invalid address family.");
    goto LABEL_66;
  }
  v39 = *v14;
  v40 = v14[1];
  v41 = *((_DWORD *)v14 + 8);
  v35 = HvSocketResolveUniversalAddress(a1, v12, (char *)&v39 + 4, (char *)&v39 + 4);
  v13 = v35;
  if ( v35 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_66;
    v15 = 426;
LABEL_21:
    HvsocketTraceServiceError(
      (unsigned int)"VmbusTlProviderConnect",
      v15,
      v13,
      (unsigned int)&v40 + 4,
      (__int64)&v39 + 4);
    goto LABEL_66;
  }
  IsPassthruRequest = HvSocketIsPassthruRequest(a1, &v39, v12, &v38);
  v35 = VmbusTlValidateSockAddress(a1, &v39, v12, (__int64)CurrentProcess, IsPassthruRequest, (__int64)&v43);
  v13 = v35;
  if ( v35 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_66;
    v15 = 443;
    goto LABEL_21;
  }
  v35 = VmbusTlCreateConnection(a1, CurrentProcess, &Entry);
  v13 = v35;
  if ( v35 >= 0 )
  {
    v2 = (char *)Entry;
    *((_QWORD *)Entry + 41) = v6;
    if ( v6 )
    {
      v5 = *(_OWORD *)(v6 + 176);
      *(_QWORD *)(v6 + 328) = v2;
    }
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlProviderConnect",
        475,
        (_DWORD)v2,
        *((_QWORD *)v2 + 1),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)v2 + 1) <= 1 )
      __fastfail(0xEu);
    *((_QWORD *)v2 + 14) = a1;
    *(_OWORD *)(v2 + 136) = v39;
    *(_OWORD *)(v2 + 152) = v40;
    *((_DWORD *)v2 + 42) = v41;
    *((_OWORD *)v2 + 30) = *(_OWORD *)(v2 + 136);
    *((_OWORD *)v2 + 31) = *(_OWORD *)(v2 + 152);
    *((_DWORD *)v2 + 128) = *((_DWORD *)v2 + 42);
    *(GUID *)(v2 + 280) = v42;
    *((_OWORD *)v2 + 11) = v5;
    *((_OWORD *)v2 + 55) = v43;
    v17 = v38;
    *((_DWORD *)v2 + 129) ^= ((unsigned __int8)*((_DWORD *)v2 + 129) ^ (unsigned __int8)(4 * IsPassthruRequest)) & 4;
    *((GUID *)v2 + 56) = v17;
    *((_QWORD *)v2 + 114) = *(_QWORD *)(a2 + 112);
    *((_QWORD *)v2 + 116) = *(_QWORD *)(a2 + 72);
    KeClearEvent((PRKEVENT)(v2 + 712));
    VmbusTlEndpointSetPendingConnectRequest(v2, *(_QWORD *)a2, *(_QWORD *)(a2 + 8));
    VmbusTlSetupConnection(v2);
    v35 = VmbusTlAssociateConnectionToPartition(a1, &v43, v12 + 232, v2);
    v13 = v35;
    if ( v35 >= 0 )
    {
      LOBYTE(v18) = 1;
      v35 = VmbusTlEstablishConnection(a1, v2, v18);
      v13 = v35;
      if ( v35 >= 0 )
      {
        v34 = 1;
        if ( v35 == 259 )
        {
          *(_QWORD *)(a2 + 104) = v2;
          goto LABEL_66;
        }
      }
      else
      {
        if ( (unsigned int)dword_140013058 > 2 )
          HvsocketTraceEndpointGuidError(
            (unsigned int)"VmbusTlProviderConnect",
            541,
            v35,
            (_DWORD)v2,
            (__int64)(v2 + 156));
        v34 = 1;
      }
      VmbusTlConnectComplete(v2);
      v13 = 259;
      v35 = 259;
    }
    else
    {
      KeSetEvent((PRKEVENT)(v2 + 712), 0, 0);
      VmbusTlEndpointClearPendingConnectRequest(v2);
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceEndpointGuidError((unsigned int)"VmbusTlProviderConnect", 522, v35, (_DWORD)v2, (__int64)&v43);
      if ( (*((_DWORD *)v2 + 129) & 8) != 0 )
      {
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (unsigned int)"VmbusTlProviderConnect",
            527,
            (_DWORD)v2,
            *((_QWORD *)v2 + 38),
            (__int64)"Pending setup connection. (deref)");
        v19 = _InterlockedExchangeAdd64((volatile signed __int64 *)v2 + 38, 0xFFFFFFFFFFFFFFFFuLL);
        v20 = v19 <= 1;
        v21 = v19 - 1;
        if ( v20 )
        {
          if ( v21 )
            __fastfail(0xEu);
          if ( (unsigned int)dword_140013058 > 4 )
            HvsocketTraceEndpointEvent("VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", v2, 9);
          VmbusTlQueueEndpointAction(v2, v2 + 200, 9);
        }
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (unsigned int)"VmbusTlProviderConnect",
            528,
            (_DWORD)v2,
            *((_QWORD *)v2 + 1),
            (__int64)"Dereference object");
        v22 = _InterlockedExchangeAdd64((volatile signed __int64 *)v2 + 1, 0xFFFFFFFFFFFFFFFFuLL);
        v20 = v22 <= 1;
        v23 = v22 - 1;
        if ( v20 )
        {
          if ( v23 )
            __fastfail(0xEu);
          v24 = (void (__fastcall *)(char *))*((_QWORD *)v2 + 10);
          if ( v24 )
            v24(v2);
          if ( *((_DWORD *)v2 + 22) == 1 )
          {
            ExFreePoolWithTag(v2, 0x69706E56u);
          }
          else if ( *((_DWORD *)v2 + 22) == 2 )
          {
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v2 + 12), v2);
          }
        }
      }
    }
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
    {
      if ( CurrentProcess )
        ProcessId = (unsigned int)PsGetProcessId(CurrentProcess);
      else
        ProcessId = 0;
      HvsocketTraceGuidULongError((unsigned int)"VmbusTlProviderConnect", 456, v35, (unsigned int)&v40 + 4, ProcessId);
    }
    v2 = (char *)Entry;
  }
LABEL_66:
  _InterlockedIncrement((volatile signed __int32 *)VmbusProviderContext + 305);
  if ( !v34 )
  {
    _InterlockedIncrement((volatile signed __int32 *)VmbusProviderContext + 306);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 1256));
    if ( v2 )
    {
      if ( v2[172] )
      {
        VmbusTlConnectComplete(v2);
        v13 = v35;
      }
      else
      {
        v2[296] = 1;
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (unsigned int)"VmbusTlProviderConnect",
            591,
            (_DWORD)v2,
            *((_QWORD *)v2 + 38),
            (__int64)"Initial reference. (deref)");
        v25 = _InterlockedExchangeAdd64((volatile signed __int64 *)v2 + 38, 0xFFFFFFFFFFFFFFFFuLL);
        v20 = v25 <= 1;
        v26 = v25 - 1;
        if ( v20 )
        {
          if ( v26 )
            __fastfail(0xEu);
          if ( (unsigned int)dword_140013058 > 4 )
            HvsocketTraceEndpointEvent("VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", v2, 9);
          VmbusTlQueueEndpointAction(v2, v2 + 200, 9);
        }
      }
    }
  }
  if ( v12 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlProviderConnect",
        598,
        v12,
        *(_QWORD *)(v12 + 8),
        (__int64)"Dereference object");
    v27 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v12 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v20 = v27 <= 1;
    v28 = v27 - 1;
    if ( v20 )
    {
      if ( v28 )
        __fastfail(0xEu);
      v29 = *(void (__fastcall **)(__int64))(v12 + 80);
      if ( v29 )
        v29(v12);
      if ( *(_DWORD *)(v12 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v12, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v12 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v12 + 96), (PVOID)v12);
      }
    }
  }
  if ( v2 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlProviderConnect",
        606,
        (_DWORD)v2,
        *((_QWORD *)v2 + 1),
        (__int64)"Dereference object");
    v30 = _InterlockedExchangeAdd64((volatile signed __int64 *)v2 + 1, 0xFFFFFFFFFFFFFFFFuLL);
    v20 = v30 <= 1;
    v31 = v30 - 1;
    if ( v20 )
    {
      if ( v31 )
        __fastfail(0xEu);
      v32 = (void (__fastcall *)(char *))*((_QWORD *)v2 + 10);
      if ( v32 )
        v32(v2);
      if ( *((_DWORD *)v2 + 22) == 1 )
      {
        ExFreePoolWithTag(v2, 0x69706E56u);
      }
      else if ( *((_DWORD *)v2 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v2 + 12), v2);
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x140020b80  mov     rax, rsp
0x140020b83  mov     [rax+18h], rbx
0x140020b87  push    rbp
0x140020b88  push    rsi
0x140020b89  push    rdi
0x140020b8a  push    r12
0x140020b8c  push    r13
0x140020b8e  push    r14
0x140020b90  push    r15
0x140020b92  lea     rbp, [rax-5Fh]
0x140020b96  sub     rsp, 0C0h
0x140020b9d  movaps  xmmword ptr [rax-48h], xmm6
0x140020ba1  mov     rax, cs:__security_cookie
0x140020ba8  xor     rax, rsp
0x140020bab  mov     [rbp+57h+var_50], rax
0x140020baf  xor     edi, edi
0x140020bb1  xorps   xmm0, xmm0
0x140020bb4  xor     eax, eax
0x140020bb6  mov     [rdx+68h], rdi
0x140020bba  xorps   xmm1, xmm1
0x140020bbd  mov     ebx, edi
0x140020bbf  mov     r12, rdx
0x140020bc2  mov     r13, rcx
0x140020bc5  xorps   xmm6, xmm6
0x140020bc8  mov     [rbp+57h+var_78], eax
0x140020bcb  mov     r14d, edi
0x140020bce  mov     [rbp+57h+Entry], rbx
0x140020bd2  movups  [rbp+57h+var_70], xmm0
0x140020bd6  mov     [rbp+57h+var_C0], dil
0x140020bda  movups  [rbp+57h+var_98], xmm0
0x140020bde  movups  [rbp+57h+var_88], xmm0
0x140020be2  movups  xmm0, xmmword ptr cs:HV_GUID_ZERO.Data1
0x140020be9  movups  [rbp+57h+var_60], xmm1
0x140020bed  movdqu  [rbp+57h+var_A8], xmm0
0x140020bf2  cmp     [rdx+10h], edi
0x140020bf5  jge     short loc_140020C11
0x140020bf7  mov     r14, [rdx+18h]
0x140020bfb  test    r14, r14
0x140020bfe  jz      short loc_140020C11
0x140020c00  mov     r15, [r14+110h]
0x140020c07  movups  xmm0, xmmword ptr [r14+118h]
0x140020c0f  jmp     short loc_140020C70
0x140020c11  mov     r15, [rdx+28h]
0x140020c15  test    r15, r15
0x140020c18  jnz     short loc_140020C29
0x140020c1a  call    cs:__imp_PsGetCurrentProcess
0x140020c21  nop     dword ptr [rax+rax+00h]
0x140020c26  mov     r15, rax
0x140020c29  mov     rcx, [r12+30h]
0x140020c2e  test    rcx, rcx
0x140020c31  jz      short loc_140020C41
0x140020c33  call    cs:__imp_PsGetThreadServerSilo
0x140020c3a  nop     dword ptr [rax+rax+00h]
0x140020c3f  jmp     short loc_140020C50
0x140020c41  mov     rcx, r15
0x140020c44  call    cs:__imp_PsGetProcessServerSilo
0x140020c4b  nop     dword ptr [rax+rax+00h]
0x140020c50  mov     rcx, rax
0x140020c53  call    cs:__imp_PsGetSiloContainerId
0x140020c5a  nop     dword ptr [rax+rax+00h]
0x140020c5f  test    rax, rax
0x140020c62  lea     rcx, HV_GUID_CHILDREN
0x140020c69  cmovnz  rcx, rax
0x140020c6d  movups  xmm0, xmmword ptr [rcx]
0x140020c70  lea     rdx, [rbp+57h+var_70]
0x140020c74  mov     rcx, r13
0x140020c77  movdqu  [rbp+57h+var_70], xmm0
0x140020c7c  call    VmbusTlFindAndReferencePartition
0x140020c81  mov     rsi, rax
0x140020c84  test    rax, rax
0x140020c87  jnz     short loc_140020CBD
0x140020c89  mov     eax, cs:dword_140013058
0x140020c8f  mov     edi, 0C0000225h
0x140020c94  mov     [rbp+57h+var_BC], edi
0x140020c97  cmp     eax, 2
0x140020c9a  jbe     loc_14002113B
0x140020ca0  lea     r9, [rbp+57h+var_70]
0x140020ca4  mov     r8d, edi
0x140020ca7  mov     edx, 197h
0x140020cac  lea     rcx, aVmbustlprovide_1; "VmbusTlProviderConnect"
0x140020cb3  call    HvsocketTraceGuidError
0x140020cb8  jmp     loc_14002113B
0x140020cbd  mov     rax, [r12+58h]
0x140020cc2  cmp     word ptr [rax], 22h ; '"'
0x140020cc6  jz      short loc_140020CFF
0x140020cc8  mov     eax, cs:dword_140013058
0x140020cce  mov     edi, 0C000000Dh
0x140020cd3  mov     [rbp+57h+var_BC], edi
0x140020cd6  cmp     eax, 2
0x140020cd9  jbe     loc_14002113B
0x140020cdf  lea     r9, aInvalidAddress; "Invalid address family."
0x140020ce6  mov     r8d, edi
0x140020ce9  mov     edx, 1A2h
0x140020cee  lea     rcx, aVmbustlprovide_1; "VmbusTlProviderConnect"
0x140020cf5  call    HvsocketTraceError
0x140020cfa  jmp     loc_14002113B
0x140020cff  movups  xmm0, xmmword ptr [rax]
0x140020d02  lea     r9, [rbp+57h+var_98+4]
0x140020d06  mov     rdx, rsi
0x140020d09  lea     r8, [rbp+57h+var_98+4]
0x140020d0d  mov     rcx, r13
0x140020d10  movups  [rbp+57h+var_98], xmm0
0x140020d14  movups  xmm1, xmmword ptr [rax+10h]
0x140020d18  movups  [rbp+57h+var_88], xmm1
0x140020d1c  mov     eax, [rax+20h]
0x140020d1f  mov     [rbp+57h+var_78], eax
0x140020d22  call    HvSocketResolveUniversalAddress
0x140020d27  mov     [rbp+57h+var_BC], eax
0x140020d2a  mov     edi, eax
0x140020d2c  test    eax, eax
0x140020d2e  jns     short loc_140020D65
0x140020d30  mov     eax, cs:dword_140013058
0x140020d36  cmp     eax, 2
0x140020d39  jbe     loc_14002113B
0x140020d3f  mov     edx, 1AAh
0x140020d44  lea     rax, [rbp+57h+var_98+4]
0x140020d48  mov     r8d, edi
0x140020d4b  lea     r9, [rbp+57h+var_88+4]
0x140020d4f  mov     [rsp+0F0h+var_D0], rax
0x140020d54  lea     rcx, aVmbustlprovide_1; "VmbusTlProviderConnect"
0x140020d5b  call    HvsocketTraceServiceError
0x140020d60  jmp     loc_14002113B
0x140020d65  lea     r9, [rbp+57h+var_A8]
0x140020d69  mov     r8, rsi
0x140020d6c  lea     rdx, [rbp+57h+var_98]
0x140020d70  mov     rcx, r13
0x140020d73  call    HvSocketIsPassthruRequest
0x140020d78  lea     rcx, [rbp+57h+var_60]
0x140020d7c  mov     [rbp+57h+var_B8], al
0x140020d7f  mov     [rsp+0F0h+var_C8], rcx
0x140020d84  lea     rdx, [rbp+57h+var_98]
0x140020d88  mov     rcx, r13
0x140020d8b  mov     byte ptr [rsp+0F0h+var_D0], al
0x140020d8f  mov     r9, r15
0x140020d92  mov     r8, rsi
0x140020d95  call    VmbusTlValidateSockAddress
0x140020d9a  mov     [rbp+57h+var_BC], eax
0x140020d9d  mov     edi, eax
0x140020d9f  test    eax, eax
0x140020da1  jns     short loc_140020DB9
0x140020da3  mov     eax, cs:dword_140013058
0x140020da9  cmp     eax, 2
0x140020dac  jbe     loc_14002113B
0x140020db2  mov     edx, 1BBh
0x140020db7  jmp     short loc_140020D44
0x140020db9  lea     r8, [rbp+57h+Entry]
0x140020dbd  mov     rdx, r15
0x140020dc0  mov     rcx, r13
0x140020dc3  call    VmbusTlCreateConnection
0x140020dc8  mov     [rbp+57h+var_BC], eax
0x140020dcb  mov     edi, eax
0x140020dcd  test    eax, eax
0x140020dcf  jns     short loc_140020E19
0x140020dd1  mov     eax, cs:dword_140013058
0x140020dd7  cmp     eax, 2
0x140020dda  jbe     short loc_140020E10
0x140020ddc  test    r15, r15
0x140020ddf  jnz     short loc_140020DE5
0x140020de1  xor     eax, eax
0x140020de3  jmp     short loc_140020DF4
0x140020de5  mov     rcx, r15; Process
0x140020de8  call    cs:__imp_PsGetProcessId
0x140020def  nop     dword ptr [rax+rax+00h]
0x140020df4  lea     r9, [rbp+57h+var_88+4]
0x140020df8  mov     dword ptr [rsp+0F0h+var_D0], eax
0x140020dfc  mov     r8d, edi
0x140020dff  lea     rcx, aVmbustlprovide_1; "VmbusTlProviderConnect"
0x140020e06  mov     edx, 1C8h
0x140020e0b  call    HvsocketTraceGuidULongError
0x140020e10  mov     rbx, [rbp+57h+Entry]
0x140020e14  jmp     loc_14002113B
0x140020e19  mov     rbx, [rbp+57h+Entry]
0x140020e1d  mov     [rbx+148h], r14
0x140020e24  test    r14, r14
0x140020e27  jz      short loc_140020E38
0x140020e29  movups  xmm6, xmmword ptr [r14+0B0h]
0x140020e31  mov     [r14+148h], rbx
0x140020e38  mov     eax, cs:dword_140013058
0x140020e3e  cmp     eax, 5
0x140020e41  jbe     short loc_140020E67
0x140020e43  mov     r9, [rbx+8]
0x140020e47  lea     rax, aReferenceObjec; "Reference object"
0x140020e4e  mov     r8, rbx
0x140020e51  mov     [rsp+0F0h+var_D0], rax
0x140020e56  mov     edx, 1DBh
0x140020e5b  lea     rcx, aVmbustlprovide_1; "VmbusTlProviderConnect"
0x140020e62  call    HvsocketTraceReferenceCount
0x140020e67  mov     eax, 1
0x140020e6c  lock xadd [rbx+8], rax
0x140020e72  inc     rax
0x140020e75  mov     r15d, 0Eh
0x140020e7b  cmp     rax, 1
0x140020e7f  jg      short loc_140020E86
0x140020e81  mov     ecx, r15d
0x140020e84  int     29h; Win8: RtlFailFast(ecx)
0x140020e86  movzx   ecx, [rbp+57h+var_B8]
0x140020e8a  lea     r14, [rbx+2C8h]
0x140020e91  mov     [rbx+70h], r13
0x140020e95  movups  xmm0, [rbp+57h+var_98]
0x140020e99  shl     ecx, 2
0x140020e9c  movups  xmmword ptr [rbx+88h], xmm0
0x140020ea3  movups  xmm1, [rbp+57h+var_88]
0x140020ea7  movups  xmmword ptr [rbx+98h], xmm1
0x140020eae  mov     eax, [rbp+57h+var_78]
0x140020eb1  mov     [rbx+0A8h], eax
0x140020eb7  movups  xmm0, xmmword ptr [rbx+88h]
0x140020ebe  movups  xmmword ptr [rbx+1E0h], xmm0
0x140020ec5  movups  xmm1, xmmword ptr [rbx+98h]
0x140020ecc  movups  xmmword ptr [rbx+1F0h], xmm1
0x140020ed3  mov     eax, [rbx+0A8h]
0x140020ed9  mov     [rbx+200h], eax
0x140020edf  movups  xmm0, [rbp+57h+var_70]
0x140020ee3  movdqu  xmmword ptr [rbx+118h], xmm0
0x140020eeb  movdqu  xmmword ptr [rbx+0B0h], xmm6
0x140020ef3  movups  xmm0, [rbp+57h+var_60]
0x140020ef7  movdqu  xmmword ptr [rbx+370h], xmm0
0x140020eff  mov     eax, [rbx+204h]
0x140020f05  xor     ecx, eax
0x140020f07  movups  xmm0, [rbp+57h+var_A8]
0x140020f0b  and     ecx, 4
0x140020f0e  xor     ecx, eax
0x140020f10  mov     [rbx+204h], ecx
0x140020f16  mov     rcx, r14; Event
0x140020f19  movdqu  xmmword ptr [rbx+380h], xmm0
0x140020f21  mov     rax, [r12+70h]
0x140020f26  mov     [rbx+390h], rax
0x140020f2d  mov     rax, [r12+48h]
0x140020f32  mov     [rbx+3A0h], rax
0x140020f39  call    cs:__imp_KeClearEvent
0x140020f40  nop     dword ptr [rax+rax+00h]
0x140020f45  mov     r8, [r12+8]
0x140020f4a  mov     rcx, rbx
0x140020f4d  mov     rdx, [r12]
0x140020f51  call    VmbusTlEndpointSetPendingConnectRequest
0x140020f56  mov     rcx, rbx
0x140020f59  call    VmbusTlSetupConnection
0x140020f5e  lea     r8, [rsi+0E8h]
0x140020f65  mov     r9, rbx
0x140020f68  lea     rdx, [rbp+57h+var_60]
0x140020f6c  mov     rcx, r13
0x140020f6f  call    VmbusTlAssociateConnectionToPartition
0x140020f74  mov     [rbp+57h+var_BC], eax
0x140020f77  mov     edi, eax
0x140020f79  test    eax, eax
0x140020f7b  jns     loc_1400210F8
0x140020f81  xor     r8d, r8d; Wait
0x140020f84  xor     edx, edx; Increment
0x140020f86  mov     rcx, r14; Event
0x140020f89  call    cs:__imp_KeSetEvent
0x140020f90  nop     dword ptr [rax+rax+00h]
0x140020f95  mov     rcx, rbx; P
0x140020f98  call    VmbusTlEndpointClearPendingConnectRequest
0x140020f9d  mov     eax, cs:dword_140013058
0x140020fa3  cmp     eax, 2
0x140020fa6  jbe     short loc_140020FC8
0x140020fa8  lea     rax, [rbp+57h+var_60]
0x140020fac  mov     r9, rbx
0x140020faf  mov     r8d, edi
0x140020fb2  mov     [rsp+0F0h+var_D0], rax
0x140020fb7  mov     edx, 20Ah
0x140020fbc  lea     rcx, aVmbustlprovide_1; "VmbusTlProviderConnect"
0x140020fc3  call    HvsocketTraceEndpointGuidError
0x140020fc8  mov     eax, [rbx+204h]
0x140020fce  test    al, 8
0x140020fd0  jz      loc_14002113B
0x140020fd6  mov     eax, cs:dword_140013058
0x140020fdc  cmp     eax, 5
0x140020fdf  jbe     short loc_140021008
0x140020fe1  mov     r9, [rbx+130h]
0x140020fe8  lea     rax, aPendingSetupCo_0; "Pending setup connection. (deref)"
0x140020fef  mov     r8, rbx
0x140020ff2  mov     [rsp+0F0h+var_D0], rax
0x140020ff7  mov     edx, 20Fh
0x140020ffc  lea     rcx, aVmbustlprovide_1; "VmbusTlProviderConnect"
0x140021003  call    HvsocketTraceReferenceCount
0x140021008  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002100c  lock xadd [rbx+130h], rax
0x140021015  sub     rax, 1
0x140021019  jg      short loc_14002105D
0x14002101b  test    rax, rax
0x14002101e  jz      short loc_140021027
0x140021020  mov     rcx, r15
0x140021023  int     29h; Win8: RtlFailFast(ecx)
0x140021025  jmp     short loc_14002105D
0x140021027  mov     eax, cs:dword_140013058
0x14002102d  cmp     eax, 4
0x140021030  jbe     short loc_140021047
0x140021032  mov     r8d, 9
0x140021038  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x14002103f  mov     rdx, rbx
0x140021042  call    HvsocketTraceEndpointEvent
0x140021047  xor     r9d, r9d
0x14002104a  lea     rdx, [rbx+0C8h]
0x140021051  mov     rcx, rbx
0x140021054  lea     r8d, [r9+9]
0x140021058  call    VmbusTlQueueEndpointAction
0x14002105d  mov     eax, cs:dword_140013058
0x140021063  lea     r14, aDereferenceObj; "Dereference object"
0x14002106a  cmp     eax, 5
0x14002106d  jbe     short loc_14002108C
  ... truncated ...
```
