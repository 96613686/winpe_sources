# HsmpCtxCreateStreamHandleContext

- ea: `0x14005be10`
- end: `0x14005c56d`
- name: `HsmpCtxCreateStreamHandleContext`
- size: `1885`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14005aaf0`

## callees

- `0x140003c50`
- `0x140006b78`
- `0x140006c64`
- `0x1400074b0`
- `0x140007e18`
- `0x14000a674`
- `0x14000ac28`
- `0x14000ceb4`
- `0x14000d49c`
- `0x14001e220`
- `0x14001e580`
- `0x140058cbc`
- `0x14005be10`
- `0x14005c600`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005c2ad`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005c2ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c315`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c315`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c309`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c309`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c297`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c297`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14005c2cc`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14005c2cc`
- `ntoskrnl!ObfDereferenceObject` at `0x14005c09d`
- `ntoskrnl!ObfDereferenceObject` at `0x14005c09d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c0c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c32f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c0c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c32f`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005bf04`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005bf04`
- `FLTMGR!FltReferenceContext` at `0x14005beaf`
- `FLTMGR!FltReferenceContext` at `0x14005beaf`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005bf44`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005bf44`
- `FLTMGR!FltAllocateContext` at `0x14005be6c`
- `FLTMGR!FltAllocateContext` at `0x14005be6c`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c115`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c238`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c280`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c115`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c238`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c280`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14005c1f6`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14005c1f6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005c0d3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005c3ba`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005c0d3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005c3ba`
- `FLTMGR!FltReleaseContext` at `0x14005c1d9`
- `FLTMGR!FltReleaseContext` at `0x14005c1d9`

## pseudocode

```c
__int64 __fastcall HsmpCtxCreateStreamHandleContext(
        __int64 a1,
        __int64 a2,
        struct _FLT_CALLBACK_DATA *a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD *v5; // r12
  __int64 EcpListFromCallbackData; // rsi
  _QWORD *v11; // rax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  ULONG Options; // edi
  _DWORD *v14; // rdi
  unsigned __int8 ThreadPlaceholderHydrationAlwaysExplicit; // al
  int v16; // eax
  unsigned __int8 IsOsProcess; // al
  char v18; // al
  int v19; // r8d
  __int64 v20; // rcx
  char *v21; // r9
  PDEVICE_OBJECT v22; // r8
  __int64 v23; // r14
  __int64 v24; // rdx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // r8
  _DWORD *v28; // rax
  __int64 v29; // rdx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v31; // rax
  _QWORD *v32; // r9
  char *v33; // rax
  __int64 StreamSize; // rax
  __int64 v35; // r9
  __int64 v36; // r8
  __int64 v37; // [rsp+50h] [rbp-21h]
  PECP_LIST EcpList; // [rsp+58h] [rbp-19h] BYREF
  __int128 P; // [rsp+60h] [rbp-11h] BYREF
  PVOID Object; // [rsp+70h] [rbp-1h]
  PFLT_CONTEXT Context; // [rsp+E8h] [rbp+77h] BYREF

  v5 = a5;
  v37 = *(_QWORD *)(a4 + 16);
  Context = 0;
  *a5 = 0;
  EcpListFromCallbackData = (unsigned int)FltAllocateContext(Filter, 0x10u, 0x68u, PagedPool, &Context);
  HsmDbgBreakOnStatus(EcpListFromCallbackData);
  if ( (int)EcpListFromCallbackData < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v29 = 85;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v31 = *(_QWORD *)(v37 + 32);
LABEL_66:
      WPP_SF_qqiqd(
        AttachedDevice,
        v29,
        WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
        a1,
        a4,
        a2,
        v31,
        EcpListFromCallbackData);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  memset(Context, 0, 0x68u);
  *(_DWORD *)Context = 1665692488;
  *((_QWORD *)Context + 2) = a4;
  FltReferenceContext((PFLT_CONTEXT)a4);
  v11 = (char *)Context + 24;
  *((_QWORD *)Context + 4) = (char *)Context + 24;
  *v11 = v11;
  *((_QWORD *)Context + 6) = a2;
  if ( !a3 )
  {
    FltAcquirePushLockExclusiveEx(a4 + 64, 0);
    ++*(_DWORD *)(a4 + 72);
    goto LABEL_23;
  }
  Iopb = a3->Iopb;
  EcpList = 0;
  Options = Iopb->Parameters.Create.Options;
  Object = 0;
  LOBYTE(a5) = 0;
  P = 0;
  EcpListFromCallbackData = (unsigned int)FltGetEcpListFromCallbackData(Filter, a3, &EcpList);
  HsmDbgBreakOnStatus(EcpListFromCallbackData);
  if ( (int)EcpListFromCallbackData < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_37;
    }
    v29 = 86;
    v31 = *(_QWORD *)(v37 + 32);
LABEL_65:
    AttachedDevice = v26->AttachedDevice;
    goto LABEL_66;
  }
  if ( !EcpList )
    goto LABEL_7;
  EcpListFromCallbackData = (unsigned int)FltFindExtraCreateParameter(Filter, EcpList, &GUID_ECP_SRV_OPEN, 0, 0);
  HsmDbgBreakOnStatus(EcpListFromCallbackData);
  *((_DWORD *)Context + 10) = *((_DWORD *)Context + 10) & 0xFFFFFEFF
                            | ~((unsigned int)EcpListFromCallbackData >> 23) & 0x100;
  if ( (_DWORD)EcpListFromCallbackData == -1073741275 )
  {
    LODWORD(EcpListFromCallbackData) = 0;
    goto LABEL_7;
  }
  if ( (int)EcpListFromCallbackData < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_37;
    }
    v29 = 87;
    v31 = *(_QWORD *)(v37 + 32);
    goto LABEL_65;
  }
LABEL_7:
  *((_DWORD *)Context + 10) |= 0x80u;
  *((_DWORD *)Context + 10) = *((_DWORD *)Context + 10) & 0xFFFFFFFE | (Options >> 2) & 1;
  *((_DWORD *)Context + 10) = *((_DWORD *)Context + 10) & 0xFFFFFFFB | (Options >> 20) & 4;
  *((_DWORD *)Context + 10) = *((_DWORD *)Context + 10) & 0xFFFFFFFD | (Options >> 10) & 2;
  if ( *(_BYTE *)(a2 + 74) || *(_BYTE *)(a2 + 75) )
    *((_DWORD *)Context + 10) |= 0x20u;
  v14 = Context;
  v14[16] = HsmOsGetProxiedProcessId((__int64)a3);
  ThreadPlaceholderHydrationAlwaysExplicit = HsmOsGetThreadPlaceholderHydrationAlwaysExplicit((__int64)a3);
  *((_DWORD *)Context + 10) ^= ((unsigned __int16)*((_DWORD *)Context + 10)
                              ^ (unsigned __int16)(ThreadPlaceholderHydrationAlwaysExplicit << 10))
                             & 0x400;
  HsmpFillOutAttributionInformation(Context, a4, a3, &P);
  v16 = *((_DWORD *)Context + 10);
  if ( (v16 & 0x100) != 0 )
  {
    *((_DWORD *)Context + 10) = v16 | 0x40;
  }
  else if ( (int)HsmOsCheckAppCompatPolicy(&P, 3, &a5) >= 0 && (_BYTE)a5 )
  {
    *((_DWORD *)Context + 10) |= 0x40u;
  }
  IsOsProcess = HsmOsIsOsProcess(&P);
  *((_DWORD *)Context + 10) ^= ((unsigned __int16)*((_DWORD *)Context + 10)
                              ^ (unsigned __int16)(IsOsProcess << 9))
                             & 0x200;
  if ( (*((_DWORD *)Context + 10) & 0x40) == 0 )
  {
    FltAcquirePushLockSharedEx(a4 + 64, 0);
    v27 = *(_QWORD *)(a4 + 88);
    if ( v27 == a4 + 88 )
    {
      FltReleasePushLockEx(a4 + 64, 0);
      if ( *(_QWORD *)(a1 + 8) )
      {
        KeEnterCriticalRegion();
        ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(a1 + 8) + 8LL), 1u);
        v28 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(*(_QWORD *)(a1 + 8) + 216LL), (PVOID)(v37 + 32));
        if ( v28 )
        {
          *((_DWORD *)Context + 16) = v28[3];
          *((_DWORD *)Context + 10) ^= ((unsigned __int16)*((_DWORD *)Context + 10)
                                      ^ (unsigned __int16)(*((unsigned __int8 *)v28 + 16) << 10))
                                     & 0x400;
        }
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 8) + 8LL));
        KeLeaveCriticalRegion();
      }
    }
    else
    {
      *((_DWORD *)Context + 16) = *(_DWORD *)(v27 + 40);
      *((_DWORD *)Context + 10) ^= (*(_DWORD *)(v27 + 16) ^ *((_DWORD *)Context + 10)) & 0x400;
      FltReleasePushLockEx(a4 + 64, 0);
    }
  }
  if ( Object )
    ObfDereferenceObject(Object);
  v18 = P;
  if ( (P & 1) != 0 )
  {
    ExFreePoolWithTag(*((PVOID *)&P + 1), 0x69417348u);
    v18 = P;
  }
  if ( (v18 & 2) != 0 )
    ExFreePoolWithTag(&P, 0x69437348u);
  FltAcquirePushLockExclusiveEx(a4 + 64, 0);
  ++*(_DWORD *)(a4 + 72);
  if ( (*(_DWORD *)(a4 + 28) & 2) == 0 )
  {
    v19 = *(_DWORD *)(a4 + 80);
    if ( (*((_DWORD *)Context + 10) & 0x20) != 0 )
    {
      ++*(_DWORD *)(a4 + 76);
      if ( (*((_DWORD *)Context + 10) & 0x40) != 0 )
      {
        ++*(_DWORD *)(a4 + 80);
        v32 = *(_QWORD **)(a4 + 96);
        if ( *v32 != a4 + 88 )
          __fastfail(3u);
        v33 = (char *)Context + 24;
        *((_QWORD *)Context + 3) = a4 + 88;
        *((_QWORD *)v33 + 1) = v32;
        *v32 = v33;
        *(_QWORD *)(a4 + 96) = v33;
      }
    }
    if ( (*(_DWORD *)(a4 + 28) & 0x100) == 0 && *(_DWORD *)(a4 + 80) == 1 && !v19 )
      HsmpDbgBreakOnHydration(Context, a3, 8);
  }
LABEL_23:
  FltReleasePushLockEx(a4 + 64, 0);
  v20 = *(_QWORD *)(a4 + 160);
  v21 = (char *)Context;
  if ( v20 && (*((_DWORD *)Context + 10) & 4) != 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v20 + 48));
    v21 = (char *)Context;
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    StreamSize = HsmpGetStreamSize(a4);
    v23 = v37;
    WPP_SF_qiqLiqL(
      *(_QWORD *)(v36 + 24),
      *(unsigned int *)(v35 + 40),
      v36,
      a1,
      *(_QWORD *)(v37 + 32),
      a4,
      *(_DWORD *)(a4 + 28),
      StreamSize,
      v35,
      *(_DWORD *)(v35 + 40));
    v21 = (char *)Context;
  }
  else
  {
    v23 = v37;
  }
  v24 = *(_QWORD *)(a4 + 8);
  if ( !v24 )
    goto LABEL_29;
  EcpListFromCallbackData = (unsigned int)((__int64 (__fastcall *)(char *, __int64, char *))qword_140029718)(
                                            v21,
                                            v24,
                                            v21 + 8);
  HsmDbgBreakOnStatus(EcpListFromCallbackData);
  if ( (int)EcpListFromCallbackData >= 0 )
  {
    v21 = (char *)Context;
LABEL_29:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qqDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        90,
        v22,
        Context,
        a4,
        *(_DWORD *)(a4 + 72),
        *(_DWORD *)(a4 + 76),
        *(_DWORD *)(a4 + 80));
      v21 = (char *)Context;
    }
    *v5 = v21;
    return (unsigned int)EcpListFromCallbackData;
  }
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v31 = *(_QWORD *)(v23 + 32);
    v29 = 89;
    goto LABEL_65;
  }
LABEL_37:
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)EcpListFromCallbackData;
}

```

## disassembly

```asm
0x14005be10  push    rbp
0x14005be12  push    rbx
0x14005be13  push    rsi
0x14005be14  push    rdi
0x14005be15  push    r12
0x14005be17  push    r13
0x14005be19  push    r14
0x14005be1b  push    r15
0x14005be1d  lea     rbp, [rsp-17h]
0x14005be22  sub     rsp, 88h
0x14005be29  mov     rax, [r9+10h]
0x14005be2d  xor     edi, edi
0x14005be2f  mov     r12, [rbp+4Fh+arg_20]
0x14005be33  mov     rbx, r9
0x14005be36  mov     [rbp+4Fh+var_70], rax
0x14005be3a  mov     r14, r8
0x14005be3d  mov     r15, rdx
0x14005be40  mov     [rbp+4Fh+Context], rdi
0x14005be44  mov     r13, rcx
0x14005be47  lea     rax, [rbp+4Fh+Context]
0x14005be4b  mov     [r12], rdi
0x14005be4f  mov     edx, 10h; ContextType
0x14005be54  mov     rcx, cs:Filter; Filter
0x14005be5b  mov     r9d, 1; PoolType
0x14005be61  mov     r8d, 68h ; 'h'; ContextSize
0x14005be67  mov     [rsp+0C0h+ReturnedContext], rax; ReturnedContext
0x14005be6c  call    cs:__imp_FltAllocateContext
0x14005be73  nop     dword ptr [rax+rax+00h]
0x14005be78  mov     ecx, eax
0x14005be7a  mov     esi, eax
0x14005be7c  call    HsmDbgBreakOnStatus
0x14005be81  test    esi, esi
0x14005be83  js      loc_14005C36F
0x14005be89  mov     rcx, [rbp+4Fh+Context]; void *
0x14005be8d  xor     edx, edx; Val
0x14005be8f  mov     r8d, 68h ; 'h'; Size
0x14005be95  call    memset
0x14005be9a  mov     rax, [rbp+4Fh+Context]
0x14005be9e  mov     rcx, rbx; Context
0x14005bea1  mov     dword ptr [rax], 63487348h
0x14005bea7  mov     rax, [rbp+4Fh+Context]
0x14005beab  mov     [rax+10h], rbx
0x14005beaf  call    cs:__imp_FltReferenceContext
0x14005beb6  nop     dword ptr [rax+rax+00h]
0x14005bebb  mov     rax, [rbp+4Fh+Context]
0x14005bebf  add     rax, 18h
0x14005bec3  mov     [rax+8], rax
0x14005bec7  mov     [rax], rax
0x14005beca  mov     rax, [rbp+4Fh+Context]
0x14005bece  mov     [rax+30h], r15
0x14005bed2  test    r14, r14
0x14005bed5  jz      loc_14005C3B4
0x14005bedb  mov     rax, [r14+10h]
0x14005bedf  lea     r8, [rbp+4Fh+EcpList]; EcpList
0x14005bee3  mov     rcx, cs:Filter; Filter
0x14005beea  xorps   xmm0, xmm0
0x14005beed  mov     [rbp+4Fh+EcpList], rdi
0x14005bef1  mov     rdx, r14; CallbackData
0x14005bef4  mov     edi, [rax+20h]
0x14005bef7  xor     eax, eax
0x14005bef9  mov     [rbp+4Fh+Object], rax
0x14005befd  mov     byte ptr [rbp+4Fh+arg_20], al
0x14005bf00  movups  [rbp+4Fh+P], xmm0
0x14005bf04  call    cs:__imp_FltGetEcpListFromCallbackData
0x14005bf0b  nop     dword ptr [rax+rax+00h]
0x14005bf10  mov     ecx, eax
0x14005bf12  mov     esi, eax
0x14005bf14  call    HsmDbgBreakOnStatus
0x14005bf19  test    esi, esi
0x14005bf1b  js      loc_14005C41F
0x14005bf21  mov     rdx, [rbp+4Fh+EcpList]; EcpList
0x14005bf25  test    rdx, rdx
0x14005bf28  jz      short loc_14005BF84
0x14005bf2a  mov     rcx, cs:Filter; Filter
0x14005bf31  lea     r8, GUID_ECP_SRV_OPEN; EcpType
0x14005bf38  xor     r9d, r9d; EcpContext
0x14005bf3b  mov     [rsp+0C0h+ReturnedContext], 0; EcpContextSize
0x14005bf44  call    cs:__imp_FltFindExtraCreateParameter
0x14005bf4b  nop     dword ptr [rax+rax+00h]
0x14005bf50  mov     ecx, eax
0x14005bf52  mov     esi, eax
0x14005bf54  call    HsmDbgBreakOnStatus
0x14005bf59  mov     rdx, [rbp+4Fh+Context]
0x14005bf5d  mov     ecx, esi
0x14005bf5f  shr     ecx, 17h
0x14005bf62  not     ecx
0x14005bf64  and     ecx, 100h
0x14005bf6a  mov     eax, [rdx+28h]
0x14005bf6d  btr     eax, 8
0x14005bf71  or      ecx, eax
0x14005bf73  mov     [rdx+28h], ecx
0x14005bf76  cmp     esi, 0C0000225h
0x14005bf7c  jnz     loc_14005C483
0x14005bf82  xor     esi, esi
0x14005bf84  mov     rax, [rbp+4Fh+Context]
0x14005bf88  mov     ecx, edi
0x14005bf8a  shr     ecx, 2
0x14005bf8d  and     ecx, 1
0x14005bf90  or      dword ptr [rax+28h], 80h
0x14005bf97  mov     rdx, [rbp+4Fh+Context]
0x14005bf9b  mov     eax, [rdx+28h]
0x14005bf9e  and     eax, 0FFFFFFFEh
0x14005bfa1  or      ecx, eax
0x14005bfa3  mov     [rdx+28h], ecx
0x14005bfa6  mov     ecx, edi
0x14005bfa8  mov     rdx, [rbp+4Fh+Context]
0x14005bfac  shr     ecx, 14h
0x14005bfaf  and     ecx, 4
0x14005bfb2  shr     edi, 0Ah
0x14005bfb5  and     edi, 2
0x14005bfb8  mov     eax, [rdx+28h]
0x14005bfbb  and     eax, 0FFFFFFFBh
0x14005bfbe  or      ecx, eax
0x14005bfc0  mov     [rdx+28h], ecx
0x14005bfc3  mov     rcx, [rbp+4Fh+Context]
0x14005bfc7  mov     eax, [rcx+28h]
0x14005bfca  and     eax, 0FFFFFFFDh
0x14005bfcd  or      edi, eax
0x14005bfcf  mov     [rcx+28h], edi
0x14005bfd2  cmp     byte ptr [r15+4Ah], 0
0x14005bfd7  jnz     loc_14005C249
0x14005bfdd  cmp     byte ptr [r15+4Bh], 0
0x14005bfe2  jnz     loc_14005C249
0x14005bfe8  mov     rdi, [rbp+4Fh+Context]
0x14005bfec  mov     rcx, r14
0x14005bfef  call    HsmOsGetProxiedProcessId
0x14005bff4  mov     rcx, r14
0x14005bff7  mov     [rdi+40h], eax
0x14005bffa  call    HsmOsGetThreadPlaceholderHydrationAlwaysExplicit
0x14005bfff  mov     rcx, [rbp+4Fh+Context]
0x14005c003  lea     r9, [rbp+4Fh+P]
0x14005c007  movzx   edx, al
0x14005c00a  mov     r8, r14
0x14005c00d  shl     edx, 0Ah
0x14005c010  mov     eax, [rcx+28h]
0x14005c013  xor     edx, eax
0x14005c015  and     edx, 400h
0x14005c01b  xor     edx, eax
0x14005c01d  mov     [rcx+28h], edx
0x14005c020  mov     rdx, rbx
0x14005c023  mov     rcx, [rbp+4Fh+Context]
0x14005c027  call    HsmpFillOutAttributionInformation
0x14005c02c  mov     rcx, [rbp+4Fh+Context]
0x14005c030  mov     eax, [rcx+28h]
0x14005c033  bt      eax, 8
0x14005c037  jb      loc_14005C256
0x14005c03d  lea     r8, [rbp+4Fh+arg_20]
0x14005c041  mov     edx, 3
0x14005c046  lea     rcx, [rbp+4Fh+P]
0x14005c04a  call    HsmOsCheckAppCompatPolicy
0x14005c04f  test    eax, eax
0x14005c051  js      short loc_14005C061
0x14005c053  cmp     byte ptr [rbp+4Fh+arg_20], 0
0x14005c057  jz      short loc_14005C061
0x14005c059  mov     rax, [rbp+4Fh+Context]
0x14005c05d  or      dword ptr [rax+28h], 40h
0x14005c061  lea     rcx, [rbp+4Fh+P]
0x14005c065  call    HsmOsIsOsProcess
0x14005c06a  mov     rcx, [rbp+4Fh+Context]
0x14005c06e  movzx   edx, al
0x14005c071  shl     edx, 9
0x14005c074  mov     eax, [rcx+28h]
0x14005c077  xor     edx, eax
0x14005c079  and     edx, 200h
0x14005c07f  xor     edx, eax
0x14005c081  mov     [rcx+28h], edx
0x14005c084  mov     rax, [rbp+4Fh+Context]
0x14005c088  mov     ecx, [rax+28h]
0x14005c08b  test    cl, 40h
0x14005c08e  jz      loc_14005C1F0
0x14005c094  mov     rcx, [rbp+4Fh+Object]; Object
0x14005c098  test    rcx, rcx
0x14005c09b  jz      short loc_14005C0A9
0x14005c09d  call    cs:__imp_ObfDereferenceObject
0x14005c0a4  nop     dword ptr [rax+rax+00h]
0x14005c0a9  mov     eax, dword ptr [rbp+4Fh+P]
0x14005c0ac  test    al, 1
0x14005c0ae  jnz     loc_14005C326
0x14005c0b4  test    al, 2
0x14005c0b6  jz      short loc_14005C0CD
0x14005c0b8  mov     edx, 69437348h; Tag
0x14005c0bd  lea     rcx, [rbp+4Fh+P]; P
0x14005c0c1  call    cs:__imp_ExFreePoolWithTag
0x14005c0c8  nop     dword ptr [rax+rax+00h]
0x14005c0cd  xor     edx, edx
0x14005c0cf  lea     rcx, [rbx+40h]
0x14005c0d3  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14005c0da  nop     dword ptr [rax+rax+00h]
0x14005c0df  mov     eax, [rbx+48h]
0x14005c0e2  inc     eax
0x14005c0e4  mov     [rbx+48h], eax
0x14005c0e7  mov     eax, [rbx+1Ch]
0x14005c0ea  test    al, 2
0x14005c0ec  jnz     short loc_14005C10F
0x14005c0ee  mov     r8d, [rbx+50h]
0x14005c0f2  mov     rax, [rbp+4Fh+Context]
0x14005c0f6  mov     ecx, [rax+28h]
0x14005c0f9  test    cl, 20h
0x14005c0fc  jnz     loc_14005C3D3
0x14005c102  test    dword ptr [rbx+1Ch], 100h
0x14005c109  jz      loc_14005C343
0x14005c10f  xor     edx, edx
0x14005c111  lea     rcx, [rbx+40h]
0x14005c115  call    cs:__imp_FltReleasePushLockEx
0x14005c11c  nop     dword ptr [rax+rax+00h]
0x14005c121  mov     rcx, [rbx+0A0h]
0x14005c128  mov     r9, [rbp+4Fh+Context]
0x14005c12c  test    rcx, rcx
0x14005c12f  jnz     loc_14005C261
0x14005c135  mov     r8, cs:WPP_GLOBAL_Control
0x14005c13c  lea     rdi, WPP_GLOBAL_Control
0x14005c143  cmp     r8, rdi
0x14005c146  jz      short loc_14005C15B
0x14005c148  mov     eax, [r8+2Ch]
0x14005c14c  test    al, 1
0x14005c14e  jz      short loc_14005C15B
0x14005c150  cmp     byte ptr [r8+29h], 5
0x14005c155  jnb     loc_14005C4C6
0x14005c15b  mov     r14, [rbp+4Fh+var_70]
0x14005c15f  mov     rdx, [rbx+8]
0x14005c163  test    rdx, rdx
0x14005c166  jnz     short loc_14005C1A0
0x14005c168  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c16f  cmp     rcx, rdi
0x14005c172  jz      short loc_14005C185
0x14005c174  mov     eax, [rcx+2Ch]
0x14005c177  test    al, 1
0x14005c179  jz      short loc_14005C185
0x14005c17b  cmp     byte ptr [rcx+29h], 5
0x14005c17f  jnb     loc_14005C538
0x14005c185  mov     [r12], r9
0x14005c189  mov     eax, esi
0x14005c18b  add     rsp, 88h
0x14005c192  pop     r15
0x14005c194  pop     r14
0x14005c196  pop     r13
0x14005c198  pop     r12
0x14005c19a  pop     rdi
0x14005c19b  pop     rsi
0x14005c19c  pop     rbx
0x14005c19d  pop     rbp
0x14005c19e  retn
0x14005c1a0  mov     rax, cs:qword_140029718
0x14005c1a7  lea     r8, [r9+8]
0x14005c1ab  mov     rcx, r9
0x14005c1ae  call    _guard_dispatch_icall
0x14005c1b3  mov     ecx, eax
0x14005c1b5  mov     esi, eax
0x14005c1b7  call    HsmDbgBreakOnStatus
0x14005c1bc  test    esi, esi
0x14005c1be  jns     short loc_14005C1E7
0x14005c1c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c1c7  cmp     rcx, rdi
0x14005c1ca  jnz     loc_14005C50E
0x14005c1d0  mov     rcx, [rbp+4Fh+Context]; Context
0x14005c1d4  test    rcx, rcx
0x14005c1d7  jz      short loc_14005C189
0x14005c1d9  call    cs:__imp_FltReleaseContext
0x14005c1e0  nop     dword ptr [rax+rax+00h]
0x14005c1e5  jmp     short loc_14005C189
0x14005c1e7  mov     r9, [rbp+4Fh+Context]
0x14005c1eb  jmp     loc_14005C168
0x14005c1f0  xor     edx, edx
0x14005c1f2  lea     rcx, [rbx+40h]
0x14005c1f6  call    cs:__imp_FltAcquirePushLockSharedEx
0x14005c1fd  nop     dword ptr [rax+rax+00h]
0x14005c202  mov     r8, [rbx+58h]
0x14005c206  lea     rax, [rbx+58h]
0x14005c20a  cmp     r8, rax
0x14005c20d  jz      short loc_14005C27A
0x14005c20f  mov     ecx, [r8+28h]
0x14005c213  mov     rax, [rbp+4Fh+Context]
0x14005c217  mov     [rax+40h], ecx
0x14005c21a  mov     rdx, [rbp+4Fh+Context]
0x14005c21e  mov     eax, [rdx+28h]
0x14005c221  mov     ecx, eax
0x14005c223  xor     ecx, [r8+10h]
0x14005c227  and     ecx, 400h
0x14005c22d  xor     ecx, eax
0x14005c22f  mov     [rdx+28h], ecx
0x14005c232  xor     edx, edx
0x14005c234  lea     rcx, [rbx+40h]
0x14005c238  call    cs:__imp_FltReleasePushLockEx
0x14005c23f  nop     dword ptr [rax+rax+00h]
0x14005c244  jmp     loc_14005C094
0x14005c249  mov     rax, [rbp+4Fh+Context]
0x14005c24d  or      dword ptr [rax+28h], 20h
0x14005c251  jmp     loc_14005BFE8
0x14005c256  or      eax, 40h
0x14005c259  mov     [rcx+28h], eax
0x14005c25c  jmp     loc_14005C061
0x14005c261  mov     eax, [r9+28h]
0x14005c265  test    al, 4
0x14005c267  jz      loc_14005C135
0x14005c26d  lock inc dword ptr [rcx+30h]
0x14005c271  mov     r9, [rbp+4Fh+Context]
0x14005c275  jmp     loc_14005C135
0x14005c27a  xor     edx, edx
0x14005c27c  lea     rcx, [rbx+40h]
0x14005c280  call    cs:__imp_FltReleasePushLockEx
  ... truncated ...
```
