# WanInterfaceInactiveToUp

- ea: `0x18001c814`
- end: `0x18001ce00`
- name: `WanInterfaceInactiveToUp`
- size: `1516`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000f868`
- `0x180024d28`

## callees

- `0x18000b104`
- `0x180011790`
- `0x180016f34`
- `0x180019bc8`
- `0x18001c814`
- `0x18003f1a4`
- `0x1800401a0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001c98d`
- `KERNEL32!HeapAlloc` at `0x18001c98d`
- `iprtprio!ComputeRouteMetric` at `0x18001cc5b`
- `iprtprio!ComputeRouteMetric` at `0x18001cce3`
- `iprtprio!ComputeRouteMetric` at `0x18001cc5b`
- `iprtprio!ComputeRouteMetric` at `0x18001cce3`

## string_xrefs

- `0x18001c901`: `WanInterfaceInactiveToUp: %ws coming up`
- `0x18001cb1d`: `WanInterfaceInactiveToUp::RemoveAddress = 0x%x`

## pseudocode

```c
__int64 __fastcall WanInterfaceInactiveToUp(__int64 a1)
{
  char v2; // al
  __int128 *v3; // r9
  __int64 v4; // r8
  __int128 *v5; // r9
  _DWORD *v6; // rax
  unsigned int v7; // eax
  __int64 v8; // r9
  __int64 v9; // r8
  __int128 *v10; // r9
  __int64 v11; // r8
  __int128 *v12; // r9
  __int64 v13; // r8
  __int128 *v14; // r9
  unsigned int v15; // eax
  __int128 *v16; // r9
  int *v17; // rax
  int v18; // ecx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // ecx
  int *v22; // rax
  int *v23; // r8
  __int64 v24; // r8
  __int128 *v25; // r9
  int v27; // [rsp+50h] [rbp-8D8h] BYREF
  int v28; // [rsp+54h] [rbp-8D4h]
  int v29; // [rsp+58h] [rbp-8D0h]
  int v30; // [rsp+5Ch] [rbp-8CCh]
  __int64 v31; // [rsp+60h] [rbp-8C8h]
  __int64 v32; // [rsp+68h] [rbp-8C0h]
  int v33; // [rsp+70h] [rbp-8B8h]
  int v34; // [rsp+74h] [rbp-8B4h]
  int v35; // [rsp+78h] [rbp-8B0h]
  int v36; // [rsp+80h] [rbp-8A8h]
  int v37; // [rsp+84h] [rbp-8A4h]
  int v38; // [rsp+88h] [rbp-8A0h]
  int v39; // [rsp+8Ch] [rbp-89Ch]
  int v40; // [rsp+90h] [rbp-898h]
  __int128 v41; // [rsp+A8h] [rbp-880h] BYREF
  int v42; // [rsp+B8h] [rbp-870h] BYREF
  __int128 v43; // [rsp+BCh] [rbp-86Ch]
  __int128 v44; // [rsp+CCh] [rbp-85Ch]
  int v45; // [rsp+DCh] [rbp-84Ch]
  int v46; // [rsp+E0h] [rbp-848h] BYREF
  _BYTE v47[2044]; // [rsp+E4h] [rbp-844h] BYREF

  memset_0(&v27, 0, 0x48u);
  v46 = 0;
  memset_0(v47, 0, sizeof(v47));
  v42 = 0;
  v45 = 0;
  v2 = Microsoft_Windows_RRASEnableBits;
  v43 = 0;
  v44 = 0;
  v41 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v42) = 0;
    v3 = &v41;
    if ( a1 != -688 )
      LODWORD(v3) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: WanInterfaceInactiveToUp",
      (_DWORD)v3,
      *(_QWORD *)(a1 + 72),
      (__int64)&v42);
    v2 = Microsoft_Windows_RRASEnableBits;
  }
  if ( v2 < 0 )
  {
    v4 = *(_QWORD *)(a1 + 72);
    LOWORD(v46) = 0;
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v46, L"WanInterfaceInactiveToUp: %ws coming up", v4);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v5 = &v41;
      if ( a1 != -688 )
        LODWORD(v5) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v46,
        (_DWORD)v5,
        *(_QWORD *)(a1 + 72),
        (__int64)&v42);
    }
  }
  GenericInterfaceComingUp(a1);
  DeleteAllRoutes(a1, 1);
  v6 = HeapAlloc(IPRouterHeap, 0, 8u);
  if ( v6 )
  {
    *v6 = *(_DWORD *)(a1 + 16);
    v6[1] = *(_DWORD *)(a1 + 516);
    *(_DWORD *)(a1 + 140) = 1;
    v7 = QueueAsyncFunction((LPTHREAD_START_ROUTINE)RestoreStaticRoutes, v6);
    if ( !v7 )
      goto LABEL_20;
    *(_DWORD *)(a1 + 140) = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      goto LABEL_20;
    v8 = *(_QWORD *)(a1 + 72);
    LOWORD(v46) = 0;
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v46, L"WanInterfaceInactiveToUp: Error %d queueing function for %ws", v7, v8);
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      goto LABEL_20;
    v9 = *(_QWORD *)(a1 + 72);
    LOWORD(v46) = 0;
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v46, L"WanInterfaceInactiveToUp: Error allocating context for %ws", v9);
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    v10 = &v41;
    if ( a1 != -688 )
      LODWORD(v10) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrMgrParamTraceError,
      (unsigned int)&v46,
      (_DWORD)v10,
      *(_QWORD *)(a1 + 72),
      (__int64)&v42);
  }
LABEL_20:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v11 = *(unsigned int *)(a1 + 516);
    LOWORD(v46) = 0;
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v46, L"WanInterfaceInactiveToUp::V4 = %d", v11);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v12 = &v41;
      if ( a1 != -688 )
        LODWORD(v12) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v46,
        (_DWORD)v12,
        *(_QWORD *)(a1 + 72),
        (__int64)&v42);
    }
  }
  if ( !*(_DWORD *)(a1 + 516) )
  {
    v20 = *(_QWORD *)(a1 + 712);
    if ( !*(_DWORD *)(v20 + 24) )
      return 0;
    LODWORD(v31) = 128;
    HIDWORD(v31) = *(_DWORD *)(v20 + 4);
    v32 = *(_QWORD *)(v20 + 8);
    v33 = *(_DWORD *)(v20 + 16);
    v27 = *(_DWORD *)(a1 + 672);
    v28 = *(_DWORD *)(a1 + 676);
    v29 = *(_DWORD *)(a1 + 680);
    v30 = *(_DWORD *)(a1 + 684);
    v36 = *(_DWORD *)(a1 + 16);
    v19 = ComputeRouteMetric(3);
    v40 = 1;
    v34 = -1;
    v35 = 0;
    goto LABEL_40;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v13 = *(unsigned int *)(a1 + 672);
    LOWORD(v46) = 0;
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v46, L"WanInterfaceInactiveToUp::RemoveAddress = 0x%x", v13);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v14 = &v41;
      if ( a1 != -688 )
        LODWORD(v14) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v46,
        (_DWORD)v14,
        *(_QWORD *)(a1 + 72),
        (__int64)&v42);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v46) = 0;
        LOWORD(v42) = 0;
        v15 = IsRemoteAddressPrivate(a1);
        FormatRRASErrorString(&v46, L"WanInterfaceInactiveToUp::IsRemoteAddressPrivate = %d", v15);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v16 = &v41;
          if ( a1 != -688 )
            LODWORD(v16) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v46,
            (_DWORD)v16,
            *(_QWORD *)(a1 + 72),
            (__int64)&v42);
        }
      }
    }
  }
  if ( *(_DWORD *)(a1 + 672) && (unsigned int)IsRemoteAddressPrivate(a1) )
  {
    v17 = *(int **)(a1 + 712);
    v28 = -1;
    v18 = *v17;
    v27 = *(_DWORD *)(a1 + 672);
    LODWORD(v17) = *(_DWORD *)(a1 + 16);
    v30 = v18;
    v36 = (int)v17;
    v32 = 1;
    v33 = 0;
    v19 = ComputeRouteMetric(3);
    v40 = 3;
    v31 = 0;
    v29 = 0;
LABEL_40:
    v21 = *(_DWORD *)(a1 + 516);
    v39 = v19;
    v22 = *(int **)(a1 + 712);
    v38 = 3;
    v37 = 3;
    v23 = v22 + 1;
    if ( !v21 )
      v23 = v22;
    if ( (unsigned int)AddSingleRoute(
                         *(_DWORD *)(a1 + 16),
                         (int)&v27,
                         *v23,
                         0,
                         1,
                         1,
                         1,
                         v21,
                         (struct _GUID *)(a1 + 688),
                         0) )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v24 = *(unsigned int *)(a1 + 672);
        LOWORD(v46) = 0;
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v46, L"WanInterfaceInactiveToUp: Couldnt add host route for %x", v24);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v25 = &v41;
          if ( a1 != -688 )
            LODWORD(v25) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v46,
            (_DWORD)v25,
            *(_QWORD *)(a1 + 72),
            (__int64)&v42);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c814  push    rbx
0x18001c816  push    rsi
0x18001c817  push    rdi
0x18001c818  push    r12
0x18001c81a  push    r13
0x18001c81c  push    r15
0x18001c81e  sub     rsp, 8F8h
0x18001c825  mov     rax, cs:__security_cookie
0x18001c82c  xor     rax, rsp
0x18001c82f  mov     [rsp+928h+var_48], rax
0x18001c837  xor     edx, edx; Val
0x18001c839  mov     rbx, rcx
0x18001c83c  lea     rcx, [rsp+928h+var_8D8]; void *
0x18001c841  lea     r8d, [rdx+48h]; Size
0x18001c845  call    memset_0
0x18001c84a  xor     esi, esi
0x18001c84c  lea     rcx, [rsp+928h+var_844]; void *
0x18001c854  xor     edx, edx; Val
0x18001c856  mov     [rsp+928h+var_848], esi
0x18001c85d  mov     r8d, 7FCh; Size
0x18001c863  call    memset_0
0x18001c868  xor     eax, eax
0x18001c86a  mov     [rsp+928h+var_870], esi
0x18001c871  xorps   xmm0, xmm0
0x18001c874  mov     [rsp+928h+var_84C], eax
0x18001c87b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001c882  lea     r13, RasRtrmgrParamTraceInfo
0x18001c889  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c890  lea     rdi, [rbx+2B0h]
0x18001c897  movups  [rsp+928h+var_86C], xmm0
0x18001c89f  movups  [rsp+928h+var_85C], xmm0
0x18001c8a7  movups  [rsp+928h+var_880], xmm0
0x18001c8af  test    al, 80h
0x18001c8b1  jz      short loc_18001C8F9
0x18001c8b3  lea     rax, [rsp+928h+var_870]
0x18001c8bb  mov     word ptr [rsp+928h+var_870], si
0x18001c8c3  mov     qword ptr [rsp+928h+var_900], rax
0x18001c8c8  lea     r9, [rsp+928h+var_880]
0x18001c8d0  mov     rax, [rbx+48h]
0x18001c8d4  lea     r8, aEnteredWaninte_1; "Entered: WanInterfaceInactiveToUp"
0x18001c8db  test    rdi, rdi
0x18001c8de  mov     qword ptr [rsp+928h+var_908], rax
0x18001c8e3  mov     rdx, r13
0x18001c8e6  mov     rcx, r15
0x18001c8e9  cmovnz  r9, rdi
0x18001c8ed  call    McTemplateU0zjzz_EventWriteTransfer
0x18001c8f2  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001c8f9  test    al, al
0x18001c8fb  jns     short loc_18001C966
0x18001c8fd  mov     r8, [rbx+48h]
0x18001c901  lea     rdx, aWaninterfacein_5; "WanInterfaceInactiveToUp: %ws coming up"
0x18001c908  lea     rcx, [rsp+928h+var_848]
0x18001c910  mov     word ptr [rsp+928h+var_848], si
0x18001c918  mov     word ptr [rsp+928h+var_870], si
0x18001c920  call    FormatRRASErrorString
0x18001c925  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001c92c  jge     short loc_18001C966
0x18001c92e  lea     rax, [rsp+928h+var_870]
0x18001c936  test    rdi, rdi
0x18001c939  mov     qword ptr [rsp+928h+var_900], rax
0x18001c93e  lea     r9, [rsp+928h+var_880]
0x18001c946  mov     rax, [rbx+48h]
0x18001c94a  lea     r8, [rsp+928h+var_848]
0x18001c952  cmovnz  r9, rdi
0x18001c956  mov     qword ptr [rsp+928h+var_908], rax
0x18001c95b  mov     rdx, r13
0x18001c95e  mov     rcx, r15
0x18001c961  call    McTemplateU0zjzz_EventWriteTransfer
0x18001c966  mov     rcx, rbx
0x18001c969  call    GenericInterfaceComingUp
0x18001c96e  mov     r12d, 1
0x18001c974  mov     rcx, rbx
0x18001c977  mov     edx, r12d
0x18001c97a  call    DeleteAllRoutes
0x18001c97f  mov     rcx, cs:IPRouterHeap; hHeap
0x18001c986  lea     r8d, [r12+7]; dwBytes
0x18001c98b  xor     edx, edx; dwFlags
0x18001c98d  call    cs:__imp_HeapAlloc
0x18001c993  test    rax, rax
0x18001c996  jz      short loc_18001CA04
0x18001c998  mov     ecx, [rbx+10h]
0x18001c99b  mov     rdx, rax; Context
0x18001c99e  mov     [rax], ecx
0x18001c9a0  mov     ecx, [rbx+204h]
0x18001c9a6  mov     [rax+4], ecx
0x18001c9a9  lea     rcx, RestoreStaticRoutes; Function
0x18001c9b0  mov     [rbx+8Ch], r12d
0x18001c9b7  call    QueueAsyncFunction
0x18001c9bc  test    eax, eax
0x18001c9be  jz      loc_18001CA81
0x18001c9c4  mov     [rbx+8Ch], esi
0x18001c9ca  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001c9d1  jz      loc_18001CA81
0x18001c9d7  mov     r9, [rbx+48h]
0x18001c9db  lea     rdx, aWaninterfacein_4; "WanInterfaceInactiveToUp: Error %d queu"...
0x18001c9e2  mov     r8d, eax
0x18001c9e5  mov     word ptr [rsp+928h+var_848], si
0x18001c9ed  lea     rcx, [rsp+928h+var_848]
0x18001c9f5  mov     word ptr [rsp+928h+var_870], si
0x18001c9fd  call    FormatRRASErrorString
0x18001ca02  jmp     short loc_18001CA35
0x18001ca04  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001ca0b  jz      short loc_18001CA81
0x18001ca0d  mov     r8, [rbx+48h]
0x18001ca11  lea     rdx, aWaninterfacein_1; "WanInterfaceInactiveToUp: Error allocat"...
0x18001ca18  lea     rcx, [rsp+928h+var_848]
0x18001ca20  mov     word ptr [rsp+928h+var_848], si
0x18001ca28  mov     word ptr [rsp+928h+var_870], si
0x18001ca30  call    FormatRRASErrorString
0x18001ca35  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001ca3c  jz      short loc_18001CA81
0x18001ca3e  lea     rax, [rbx+2B0h]
0x18001ca45  mov     rcx, r15
0x18001ca48  test    rax, rax
0x18001ca4b  lea     r9, [rsp+928h+var_880]
0x18001ca53  lea     r8, [rsp+928h+var_848]
0x18001ca5b  cmovnz  r9, rax
0x18001ca5f  lea     rdx, RasRtrMgrParamTraceError
0x18001ca66  lea     rax, [rsp+928h+var_870]
0x18001ca6e  mov     qword ptr [rsp+928h+var_900], rax
0x18001ca73  mov     rax, [rbx+48h]
0x18001ca77  mov     qword ptr [rsp+928h+var_908], rax
0x18001ca7c  call    McTemplateU0zjzz_EventWriteTransfer
0x18001ca81  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001ca88  jge     short loc_18001CAFD
0x18001ca8a  mov     r8d, [rbx+204h]
0x18001ca91  lea     rdx, aWaninterfacein_0; "WanInterfaceInactiveToUp::V4 = %d"
0x18001ca98  lea     rcx, [rsp+928h+var_848]
0x18001caa0  mov     word ptr [rsp+928h+var_848], si
0x18001caa8  mov     word ptr [rsp+928h+var_870], si
0x18001cab0  call    FormatRRASErrorString
0x18001cab5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001cabc  jge     short loc_18001CAFD
0x18001cabe  lea     rax, [rbx+2B0h]
0x18001cac5  mov     rdx, r13
0x18001cac8  test    rax, rax
0x18001cacb  lea     r9, [rsp+928h+var_880]
0x18001cad3  lea     r8, [rsp+928h+var_848]
0x18001cadb  mov     rcx, r15
0x18001cade  cmovnz  r9, rax
0x18001cae2  lea     rax, [rsp+928h+var_870]
0x18001caea  mov     qword ptr [rsp+928h+var_900], rax
0x18001caef  mov     rax, [rbx+48h]
0x18001caf3  mov     qword ptr [rsp+928h+var_908], rax
0x18001caf8  call    McTemplateU0zjzz_EventWriteTransfer
0x18001cafd  cmp     [rbx+204h], esi
0x18001cb03  jz      loc_18001CC76
0x18001cb09  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001cb10  jge     loc_18001CC06
0x18001cb16  mov     r8d, [rbx+2A0h]
0x18001cb1d  lea     rdx, aWaninterfacein; "WanInterfaceInactiveToUp::RemoveAddress"...
0x18001cb24  lea     rcx, [rsp+928h+var_848]
0x18001cb2c  mov     word ptr [rsp+928h+var_848], si
0x18001cb34  mov     word ptr [rsp+928h+var_870], si
0x18001cb3c  call    FormatRRASErrorString
0x18001cb41  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001cb48  jge     loc_18001CC06
0x18001cb4e  lea     rdi, [rbx+2B0h]
0x18001cb55  mov     rdx, r13
0x18001cb58  lea     rax, [rsp+928h+var_870]
0x18001cb60  test    rdi, rdi
0x18001cb63  mov     qword ptr [rsp+928h+var_900], rax
0x18001cb68  lea     r9, [rsp+928h+var_880]
0x18001cb70  mov     rax, [rbx+48h]
0x18001cb74  lea     r8, [rsp+928h+var_848]
0x18001cb7c  cmovnz  r9, rdi
0x18001cb80  mov     qword ptr [rsp+928h+var_908], rax
0x18001cb85  mov     rcx, r15
0x18001cb88  call    McTemplateU0zjzz_EventWriteTransfer
0x18001cb8d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001cb94  jge     short loc_18001CC06
0x18001cb96  mov     rcx, rbx
0x18001cb99  mov     word ptr [rsp+928h+var_848], si
0x18001cba1  mov     word ptr [rsp+928h+var_870], si
0x18001cba9  call    IsRemoteAddressPrivate
0x18001cbae  mov     r8d, eax
0x18001cbb1  lea     rdx, aWaninterfacein_2; "WanInterfaceInactiveToUp::IsRemoteAddre"...
0x18001cbb8  lea     rcx, [rsp+928h+var_848]
0x18001cbc0  call    FormatRRASErrorString
0x18001cbc5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001cbcc  jge     short loc_18001CC06
0x18001cbce  lea     rax, [rsp+928h+var_870]
0x18001cbd6  test    rdi, rdi
0x18001cbd9  mov     qword ptr [rsp+928h+var_900], rax
0x18001cbde  lea     r9, [rsp+928h+var_880]
0x18001cbe6  mov     rax, [rbx+48h]
0x18001cbea  lea     r8, [rsp+928h+var_848]
0x18001cbf2  cmovnz  r9, rdi
0x18001cbf6  mov     qword ptr [rsp+928h+var_908], rax
0x18001cbfb  mov     rdx, r13
0x18001cbfe  mov     rcx, r15
0x18001cc01  call    McTemplateU0zjzz_EventWriteTransfer
0x18001cc06  cmp     [rbx+2A0h], esi
0x18001cc0c  jz      loc_18001CDDD
0x18001cc12  mov     rcx, rbx
0x18001cc15  call    IsRemoteAddressPrivate
0x18001cc1a  test    eax, eax
0x18001cc1c  jz      loc_18001CDDD
0x18001cc22  mov     rax, [rbx+2C8h]
0x18001cc29  mov     edi, 3
0x18001cc2e  mov     [rsp+928h+var_8D4], 0FFFFFFFFh
0x18001cc36  mov     ecx, [rax]
0x18001cc38  mov     eax, [rbx+2A0h]
0x18001cc3e  mov     [rsp+928h+var_8D8], eax
0x18001cc42  mov     eax, [rbx+10h]
0x18001cc45  mov     [rsp+928h+var_8CC], ecx
0x18001cc49  mov     ecx, edi
0x18001cc4b  mov     [rsp+928h+var_8A8], eax
0x18001cc52  mov     [rsp+928h+var_8C0], r12
0x18001cc57  mov     [rsp+928h+var_8B8], esi
0x18001cc5b  call    cs:__imp_ComputeRouteMetric
0x18001cc61  mov     [rsp+928h+var_898], edi
0x18001cc68  mov     [rsp+928h+var_8C8], rsi
0x18001cc6d  mov     [rsp+928h+var_8D0], esi
0x18001cc71  jmp     loc_18001CCFD
0x18001cc76  mov     rcx, [rbx+2C8h]
0x18001cc7d  cmp     [rcx+18h], esi
0x18001cc80  jz      loc_18001CDDD
0x18001cc86  mov     dword ptr [rsp+928h+var_8C8], 80h
0x18001cc8e  mov     edi, 3
0x18001cc93  mov     eax, [rcx+4]
0x18001cc96  mov     dword ptr [rsp+928h+var_8C8+4], eax
0x18001cc9a  mov     eax, [rcx+8]
0x18001cc9d  mov     dword ptr [rsp+928h+var_8C0], eax
0x18001cca1  mov     eax, [rcx+0Ch]
0x18001cca4  mov     dword ptr [rsp+928h+var_8C0+4], eax
0x18001cca8  mov     eax, [rcx+10h]
0x18001ccab  mov     ecx, edi
0x18001ccad  mov     [rsp+928h+var_8B8], eax
0x18001ccb1  mov     eax, [rbx+2A0h]
0x18001ccb7  mov     [rsp+928h+var_8D8], eax
0x18001ccbb  mov     eax, [rbx+2A4h]
0x18001ccc1  mov     [rsp+928h+var_8D4], eax
0x18001ccc5  mov     eax, [rbx+2A8h]
0x18001cccb  mov     [rsp+928h+var_8D0], eax
0x18001cccf  mov     eax, [rbx+2ACh]
0x18001ccd5  mov     [rsp+928h+var_8CC], eax
0x18001ccd9  mov     eax, [rbx+10h]
0x18001ccdc  mov     [rsp+928h+var_8A8], eax
0x18001cce3  call    cs:__imp_ComputeRouteMetric
0x18001cce9  mov     [rsp+928h+var_898], r12d
0x18001ccf1  mov     [rsp+928h+var_8B4], 0FFFFFFFFh
0x18001ccf9  mov     [rsp+928h+var_8B0], esi
0x18001ccfd  mov     ecx, [rbx+204h]
0x18001cd03  lea     rdx, [rsp+928h+var_8D8]; int
0x18001cd08  mov     [rsp+928h+var_8E0], rsi; __int64
0x18001cd0d  xor     r9d, r9d; int
0x18001cd10  mov     [rsp+928h+var_89C], eax
0x18001cd17  test    ecx, ecx
0x18001cd19  mov     rax, [rbx+2C8h]
0x18001cd20  mov     [rsp+928h+var_8A0], edi
0x18001cd27  mov     [rsp+928h+var_8A4], edi
0x18001cd2e  lea     rdi, [rbx+2B0h]
0x18001cd35  mov     [rsp+928h+var_8E8], rdi; struct _GUID *
0x18001cd3a  mov     [rsp+928h+var_8F0], ecx; int
0x18001cd3e  lea     r8, [rax+4]
0x18001cd42  mov     ecx, [rbx+10h]; int
0x18001cd45  cmovz   r8, rax
0x18001cd49  mov     [rsp+928h+var_8F8], r12d; int
0x18001cd4e  mov     [rsp+928h+var_900], r12d; int
0x18001cd53  mov     [rsp+928h+var_908], r12d; int
0x18001cd58  mov     r8d, [r8]; int
0x18001cd5b  call    AddSingleRoute
0x18001cd60  test    eax, eax
0x18001cd62  jz      short loc_18001CDDD
0x18001cd64  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001cd6b  jz      short loc_18001CDDD
0x18001cd6d  mov     r8d, [rbx+2A0h]
0x18001cd74  lea     rdx, aWaninterfacein_3; "WanInterfaceInactiveToUp: Couldnt add h"...
0x18001cd7b  lea     rcx, [rsp+928h+var_848]
0x18001cd83  mov     word ptr [rsp+928h+var_848], si
0x18001cd8b  mov     word ptr [rsp+928h+var_870], si
0x18001cd93  call    FormatRRASErrorString
0x18001cd98  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001cd9f  jz      short loc_18001CDDD
0x18001cda1  lea     rax, [rsp+928h+var_870]
0x18001cda9  test    rdi, rdi
0x18001cdac  mov     qword ptr [rsp+928h+var_900], rax
0x18001cdb1  lea     r9, [rsp+928h+var_880]
0x18001cdb9  mov     rax, [rbx+48h]
0x18001cdbd  lea     r8, [rsp+928h+var_848]
0x18001cdc5  cmovnz  r9, rdi
0x18001cdc9  mov     qword ptr [rsp+928h+var_908], rax
0x18001cdce  lea     rdx, RasRtrMgrParamTraceError
0x18001cdd5  mov     rcx, r15
0x18001cdd8  call    McTemplateU0zjzz_EventWriteTransfer
0x18001cddd  xor     eax, eax
0x18001cddf  mov     rcx, [rsp+928h+var_48]
0x18001cde7  xor     rcx, rsp; StackCookie
0x18001cdea  call    __security_check_cookie
0x18001cdef  add     rsp, 8F8h
0x18001cdf6  pop     r15
0x18001cdf8  pop     r13
0x18001cdfa  pop     r12
0x18001cdfc  pop     rdi
0x18001cdfd  pop     rsi
0x18001cdfe  pop     rbx
0x18001cdff  retn
```
