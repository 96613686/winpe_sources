# HsmpCtxCreateStreamHandleContext

- ea: `0x14005bf30`
- end: `0x14005c68d`
- name: `HsmpCtxCreateStreamHandleContext`
- size: `1885`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14005ac10`

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
- `0x14001e2a0`
- `0x14001e600`
- `0x140058ddc`
- `0x14005bf30`
- `0x14005c720`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005c3cd`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005c3cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c435`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c435`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c429`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c429`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c3b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c3b7`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14005c3ec`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14005c3ec`
- `ntoskrnl!ObfDereferenceObject` at `0x14005c1bd`
- `ntoskrnl!ObfDereferenceObject` at `0x14005c1bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c1e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c44f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c1e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c44f`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005c024`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005c024`
- `FLTMGR!FltReferenceContext` at `0x14005bfcf`
- `FLTMGR!FltReferenceContext` at `0x14005bfcf`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005c064`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005c064`
- `FLTMGR!FltAllocateContext` at `0x14005bf8c`
- `FLTMGR!FltAllocateContext` at `0x14005bf8c`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c235`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c358`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c3a0`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c235`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c358`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c3a0`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14005c316`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14005c316`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005c1f3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005c4da`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005c1f3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005c4da`
- `FLTMGR!FltReleaseContext` at `0x14005c2f9`
- `FLTMGR!FltReleaseContext` at `0x14005c2f9`

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
  NTSTATUS EcpListFromCallbackData; // esi
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
  EcpListFromCallbackData = FltAllocateContext(Filter, 0x10u, 0x68u, PagedPool, &Context);
  HsmDbgBreakOnStatus(EcpListFromCallbackData);
  if ( EcpListFromCallbackData < 0 )
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
  EcpListFromCallbackData = FltGetEcpListFromCallbackData(Filter, a3, &EcpList);
  HsmDbgBreakOnStatus(EcpListFromCallbackData);
  if ( EcpListFromCallbackData < 0 )
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
  EcpListFromCallbackData = FltFindExtraCreateParameter(Filter, EcpList, &GUID_ECP_SRV_OPEN, 0, 0);
  HsmDbgBreakOnStatus(EcpListFromCallbackData);
  *((_DWORD *)Context + 10) = *((_DWORD *)Context + 10) & 0xFFFFFEFF
                            | ~((unsigned int)EcpListFromCallbackData >> 23) & 0x100;
  if ( EcpListFromCallbackData == -1073741275 )
  {
    EcpListFromCallbackData = 0;
    goto LABEL_7;
  }
  if ( EcpListFromCallbackData < 0 )
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
  EcpListFromCallbackData = ((__int64 (__fastcall *)(char *, __int64, char *))qword_140029718)(v21, v24, v21 + 8);
  HsmDbgBreakOnStatus(EcpListFromCallbackData);
  if ( EcpListFromCallbackData >= 0 )
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
0x14005bf30  push    rbp
0x14005bf32  push    rbx
0x14005bf33  push    rsi
0x14005bf34  push    rdi
0x14005bf35  push    r12
0x14005bf37  push    r13
0x14005bf39  push    r14
0x14005bf3b  push    r15
0x14005bf3d  lea     rbp, [rsp-17h]
0x14005bf42  sub     rsp, 88h
0x14005bf49  mov     rax, [r9+10h]
0x14005bf4d  xor     edi, edi
0x14005bf4f  mov     r12, [rbp+4Fh+arg_20]
0x14005bf53  mov     rbx, r9
0x14005bf56  mov     [rbp+4Fh+var_70], rax
0x14005bf5a  mov     r14, r8
0x14005bf5d  mov     r15, rdx
0x14005bf60  mov     [rbp+4Fh+Context], rdi
0x14005bf64  mov     r13, rcx
0x14005bf67  lea     rax, [rbp+4Fh+Context]
0x14005bf6b  mov     [r12], rdi
0x14005bf6f  mov     edx, 10h; ContextType
0x14005bf74  mov     rcx, cs:Filter; Filter
0x14005bf7b  mov     r9d, 1; PoolType
0x14005bf81  mov     r8d, 68h ; 'h'; ContextSize
0x14005bf87  mov     [rsp+0C0h+ReturnedContext], rax; ReturnedContext
0x14005bf8c  call    cs:__imp_FltAllocateContext
0x14005bf93  nop     dword ptr [rax+rax+00h]
0x14005bf98  mov     ecx, eax
0x14005bf9a  mov     esi, eax
0x14005bf9c  call    HsmDbgBreakOnStatus
0x14005bfa1  test    esi, esi
0x14005bfa3  js      loc_14005C48F
0x14005bfa9  mov     rcx, [rbp+4Fh+Context]; void *
0x14005bfad  xor     edx, edx; Val
0x14005bfaf  mov     r8d, 68h ; 'h'; Size
0x14005bfb5  call    memset
0x14005bfba  mov     rax, [rbp+4Fh+Context]
0x14005bfbe  mov     rcx, rbx; Context
0x14005bfc1  mov     dword ptr [rax], 63487348h
0x14005bfc7  mov     rax, [rbp+4Fh+Context]
0x14005bfcb  mov     [rax+10h], rbx
0x14005bfcf  call    cs:__imp_FltReferenceContext
0x14005bfd6  nop     dword ptr [rax+rax+00h]
0x14005bfdb  mov     rax, [rbp+4Fh+Context]
0x14005bfdf  add     rax, 18h
0x14005bfe3  mov     [rax+8], rax
0x14005bfe7  mov     [rax], rax
0x14005bfea  mov     rax, [rbp+4Fh+Context]
0x14005bfee  mov     [rax+30h], r15
0x14005bff2  test    r14, r14
0x14005bff5  jz      loc_14005C4D4
0x14005bffb  mov     rax, [r14+10h]
0x14005bfff  lea     r8, [rbp+4Fh+EcpList]; EcpList
0x14005c003  mov     rcx, cs:Filter; Filter
0x14005c00a  xorps   xmm0, xmm0
0x14005c00d  mov     [rbp+4Fh+EcpList], rdi
0x14005c011  mov     rdx, r14; CallbackData
0x14005c014  mov     edi, [rax+20h]
0x14005c017  xor     eax, eax
0x14005c019  mov     [rbp+4Fh+Object], rax
0x14005c01d  mov     byte ptr [rbp+4Fh+arg_20], al
0x14005c020  movups  [rbp+4Fh+P], xmm0
0x14005c024  call    cs:__imp_FltGetEcpListFromCallbackData
0x14005c02b  nop     dword ptr [rax+rax+00h]
0x14005c030  mov     ecx, eax
0x14005c032  mov     esi, eax
0x14005c034  call    HsmDbgBreakOnStatus
0x14005c039  test    esi, esi
0x14005c03b  js      loc_14005C53F
0x14005c041  mov     rdx, [rbp+4Fh+EcpList]; EcpList
0x14005c045  test    rdx, rdx
0x14005c048  jz      short loc_14005C0A4
0x14005c04a  mov     rcx, cs:Filter; Filter
0x14005c051  lea     r8, GUID_ECP_SRV_OPEN; EcpType
0x14005c058  xor     r9d, r9d; EcpContext
0x14005c05b  mov     [rsp+0C0h+ReturnedContext], 0; EcpContextSize
0x14005c064  call    cs:__imp_FltFindExtraCreateParameter
0x14005c06b  nop     dword ptr [rax+rax+00h]
0x14005c070  mov     ecx, eax
0x14005c072  mov     esi, eax
0x14005c074  call    HsmDbgBreakOnStatus
0x14005c079  mov     rdx, [rbp+4Fh+Context]
0x14005c07d  mov     ecx, esi
0x14005c07f  shr     ecx, 17h
0x14005c082  not     ecx
0x14005c084  and     ecx, 100h
0x14005c08a  mov     eax, [rdx+28h]
0x14005c08d  btr     eax, 8
0x14005c091  or      ecx, eax
0x14005c093  mov     [rdx+28h], ecx
0x14005c096  cmp     esi, 0C0000225h
0x14005c09c  jnz     loc_14005C5A3
0x14005c0a2  xor     esi, esi
0x14005c0a4  mov     rax, [rbp+4Fh+Context]
0x14005c0a8  mov     ecx, edi
0x14005c0aa  shr     ecx, 2
0x14005c0ad  and     ecx, 1
0x14005c0b0  or      dword ptr [rax+28h], 80h
0x14005c0b7  mov     rdx, [rbp+4Fh+Context]
0x14005c0bb  mov     eax, [rdx+28h]
0x14005c0be  and     eax, 0FFFFFFFEh
0x14005c0c1  or      ecx, eax
0x14005c0c3  mov     [rdx+28h], ecx
0x14005c0c6  mov     ecx, edi
0x14005c0c8  mov     rdx, [rbp+4Fh+Context]
0x14005c0cc  shr     ecx, 14h
0x14005c0cf  and     ecx, 4
0x14005c0d2  shr     edi, 0Ah
0x14005c0d5  and     edi, 2
0x14005c0d8  mov     eax, [rdx+28h]
0x14005c0db  and     eax, 0FFFFFFFBh
0x14005c0de  or      ecx, eax
0x14005c0e0  mov     [rdx+28h], ecx
0x14005c0e3  mov     rcx, [rbp+4Fh+Context]
0x14005c0e7  mov     eax, [rcx+28h]
0x14005c0ea  and     eax, 0FFFFFFFDh
0x14005c0ed  or      edi, eax
0x14005c0ef  mov     [rcx+28h], edi
0x14005c0f2  cmp     byte ptr [r15+4Ah], 0
0x14005c0f7  jnz     loc_14005C369
0x14005c0fd  cmp     byte ptr [r15+4Bh], 0
0x14005c102  jnz     loc_14005C369
0x14005c108  mov     rdi, [rbp+4Fh+Context]
0x14005c10c  mov     rcx, r14
0x14005c10f  call    HsmOsGetProxiedProcessId
0x14005c114  mov     rcx, r14
0x14005c117  mov     [rdi+40h], eax
0x14005c11a  call    HsmOsGetThreadPlaceholderHydrationAlwaysExplicit
0x14005c11f  mov     rcx, [rbp+4Fh+Context]
0x14005c123  lea     r9, [rbp+4Fh+P]
0x14005c127  movzx   edx, al
0x14005c12a  mov     r8, r14
0x14005c12d  shl     edx, 0Ah
0x14005c130  mov     eax, [rcx+28h]
0x14005c133  xor     edx, eax
0x14005c135  and     edx, 400h
0x14005c13b  xor     edx, eax
0x14005c13d  mov     [rcx+28h], edx
0x14005c140  mov     rdx, rbx
0x14005c143  mov     rcx, [rbp+4Fh+Context]
0x14005c147  call    HsmpFillOutAttributionInformation
0x14005c14c  mov     rcx, [rbp+4Fh+Context]
0x14005c150  mov     eax, [rcx+28h]
0x14005c153  bt      eax, 8
0x14005c157  jb      loc_14005C376
0x14005c15d  lea     r8, [rbp+4Fh+arg_20]
0x14005c161  mov     edx, 3
0x14005c166  lea     rcx, [rbp+4Fh+P]
0x14005c16a  call    HsmOsCheckAppCompatPolicy
0x14005c16f  test    eax, eax
0x14005c171  js      short loc_14005C181
0x14005c173  cmp     byte ptr [rbp+4Fh+arg_20], 0
0x14005c177  jz      short loc_14005C181
0x14005c179  mov     rax, [rbp+4Fh+Context]
0x14005c17d  or      dword ptr [rax+28h], 40h
0x14005c181  lea     rcx, [rbp+4Fh+P]
0x14005c185  call    HsmOsIsOsProcess
0x14005c18a  mov     rcx, [rbp+4Fh+Context]
0x14005c18e  movzx   edx, al
0x14005c191  shl     edx, 9
0x14005c194  mov     eax, [rcx+28h]
0x14005c197  xor     edx, eax
0x14005c199  and     edx, 200h
0x14005c19f  xor     edx, eax
0x14005c1a1  mov     [rcx+28h], edx
0x14005c1a4  mov     rax, [rbp+4Fh+Context]
0x14005c1a8  mov     ecx, [rax+28h]
0x14005c1ab  test    cl, 40h
0x14005c1ae  jz      loc_14005C310
0x14005c1b4  mov     rcx, [rbp+4Fh+Object]; Object
0x14005c1b8  test    rcx, rcx
0x14005c1bb  jz      short loc_14005C1C9
0x14005c1bd  call    cs:__imp_ObfDereferenceObject
0x14005c1c4  nop     dword ptr [rax+rax+00h]
0x14005c1c9  mov     eax, dword ptr [rbp+4Fh+P]
0x14005c1cc  test    al, 1
0x14005c1ce  jnz     loc_14005C446
0x14005c1d4  test    al, 2
0x14005c1d6  jz      short loc_14005C1ED
0x14005c1d8  mov     edx, 69437348h; Tag
0x14005c1dd  lea     rcx, [rbp+4Fh+P]; P
0x14005c1e1  call    cs:__imp_ExFreePoolWithTag
0x14005c1e8  nop     dword ptr [rax+rax+00h]
0x14005c1ed  xor     edx, edx
0x14005c1ef  lea     rcx, [rbx+40h]
0x14005c1f3  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14005c1fa  nop     dword ptr [rax+rax+00h]
0x14005c1ff  mov     eax, [rbx+48h]
0x14005c202  inc     eax
0x14005c204  mov     [rbx+48h], eax
0x14005c207  mov     eax, [rbx+1Ch]
0x14005c20a  test    al, 2
0x14005c20c  jnz     short loc_14005C22F
0x14005c20e  mov     r8d, [rbx+50h]
0x14005c212  mov     rax, [rbp+4Fh+Context]
0x14005c216  mov     ecx, [rax+28h]
0x14005c219  test    cl, 20h
0x14005c21c  jnz     loc_14005C4F3
0x14005c222  test    dword ptr [rbx+1Ch], 100h
0x14005c229  jz      loc_14005C463
0x14005c22f  xor     edx, edx
0x14005c231  lea     rcx, [rbx+40h]
0x14005c235  call    cs:__imp_FltReleasePushLockEx
0x14005c23c  nop     dword ptr [rax+rax+00h]
0x14005c241  mov     rcx, [rbx+0A0h]
0x14005c248  mov     r9, [rbp+4Fh+Context]
0x14005c24c  test    rcx, rcx
0x14005c24f  jnz     loc_14005C381
0x14005c255  mov     r8, cs:WPP_GLOBAL_Control
0x14005c25c  lea     rdi, WPP_GLOBAL_Control
0x14005c263  cmp     r8, rdi
0x14005c266  jz      short loc_14005C27B
0x14005c268  mov     eax, [r8+2Ch]
0x14005c26c  test    al, 1
0x14005c26e  jz      short loc_14005C27B
0x14005c270  cmp     byte ptr [r8+29h], 5
0x14005c275  jnb     loc_14005C5E6
0x14005c27b  mov     r14, [rbp+4Fh+var_70]
0x14005c27f  mov     rdx, [rbx+8]
0x14005c283  test    rdx, rdx
0x14005c286  jnz     short loc_14005C2C0
0x14005c288  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c28f  cmp     rcx, rdi
0x14005c292  jz      short loc_14005C2A5
0x14005c294  mov     eax, [rcx+2Ch]
0x14005c297  test    al, 1
0x14005c299  jz      short loc_14005C2A5
0x14005c29b  cmp     byte ptr [rcx+29h], 5
0x14005c29f  jnb     loc_14005C658
0x14005c2a5  mov     [r12], r9
0x14005c2a9  mov     eax, esi
0x14005c2ab  add     rsp, 88h
0x14005c2b2  pop     r15
0x14005c2b4  pop     r14
0x14005c2b6  pop     r13
0x14005c2b8  pop     r12
0x14005c2ba  pop     rdi
0x14005c2bb  pop     rsi
0x14005c2bc  pop     rbx
0x14005c2bd  pop     rbp
0x14005c2be  retn
0x14005c2c0  mov     rax, cs:qword_140029718
0x14005c2c7  lea     r8, [r9+8]
0x14005c2cb  mov     rcx, r9
0x14005c2ce  call    _guard_dispatch_icall
0x14005c2d3  mov     ecx, eax
0x14005c2d5  mov     esi, eax
0x14005c2d7  call    HsmDbgBreakOnStatus
0x14005c2dc  test    esi, esi
0x14005c2de  jns     short loc_14005C307
0x14005c2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c2e7  cmp     rcx, rdi
0x14005c2ea  jnz     loc_14005C62E
0x14005c2f0  mov     rcx, [rbp+4Fh+Context]; Context
0x14005c2f4  test    rcx, rcx
0x14005c2f7  jz      short loc_14005C2A9
0x14005c2f9  call    cs:__imp_FltReleaseContext
0x14005c300  nop     dword ptr [rax+rax+00h]
0x14005c305  jmp     short loc_14005C2A9
0x14005c307  mov     r9, [rbp+4Fh+Context]
0x14005c30b  jmp     loc_14005C288
0x14005c310  xor     edx, edx
0x14005c312  lea     rcx, [rbx+40h]
0x14005c316  call    cs:__imp_FltAcquirePushLockSharedEx
0x14005c31d  nop     dword ptr [rax+rax+00h]
0x14005c322  mov     r8, [rbx+58h]
0x14005c326  lea     rax, [rbx+58h]
0x14005c32a  cmp     r8, rax
0x14005c32d  jz      short loc_14005C39A
0x14005c32f  mov     ecx, [r8+28h]
0x14005c333  mov     rax, [rbp+4Fh+Context]
0x14005c337  mov     [rax+40h], ecx
0x14005c33a  mov     rdx, [rbp+4Fh+Context]
0x14005c33e  mov     eax, [rdx+28h]
0x14005c341  mov     ecx, eax
0x14005c343  xor     ecx, [r8+10h]
0x14005c347  and     ecx, 400h
0x14005c34d  xor     ecx, eax
0x14005c34f  mov     [rdx+28h], ecx
0x14005c352  xor     edx, edx
0x14005c354  lea     rcx, [rbx+40h]
0x14005c358  call    cs:__imp_FltReleasePushLockEx
0x14005c35f  nop     dword ptr [rax+rax+00h]
0x14005c364  jmp     loc_14005C1B4
0x14005c369  mov     rax, [rbp+4Fh+Context]
0x14005c36d  or      dword ptr [rax+28h], 20h
0x14005c371  jmp     loc_14005C108
0x14005c376  or      eax, 40h
0x14005c379  mov     [rcx+28h], eax
0x14005c37c  jmp     loc_14005C181
0x14005c381  mov     eax, [r9+28h]
0x14005c385  test    al, 4
0x14005c387  jz      loc_14005C255
0x14005c38d  lock inc dword ptr [rcx+30h]
0x14005c391  mov     r9, [rbp+4Fh+Context]
0x14005c395  jmp     loc_14005C255
0x14005c39a  xor     edx, edx
0x14005c39c  lea     rcx, [rbx+40h]
0x14005c3a0  call    cs:__imp_FltReleasePushLockEx
  ... truncated ...
```
