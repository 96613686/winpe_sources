# InterfaceConnected

- ea: `0x180024d28`
- end: `0x180025383`
- name: `InterfaceConnected`
- size: `1627`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003d9c0`
- `0x18003d9e0`

## callees

- `0x180001f30`
- `0x18000ac60`
- `0x180011790`
- `0x1800125dc`
- `0x18001c514`
- `0x18001c814`
- `0x180024d28`
- `0x18003de54`
- `0x180051a14`
- `0x180057bac`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlConvertExclusiveToShared` at `0x180024fa2`
- `ntdll!RtlConvertExclusiveToShared` at `0x180024fa2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180024e50`
- `ntdll!RtlAcquireResourceExclusive` at `0x180024e50`
- `ntdll!RtlReleaseResource` at `0x180024f09`
- `ntdll!RtlReleaseResource` at `0x1800251bd`
- `ntdll!RtlReleaseResource` at `0x1800252c5`
- `ntdll!RtlReleaseResource` at `0x180024f09`
- `ntdll!RtlReleaseResource` at `0x1800251bd`
- `ntdll!RtlReleaseResource` at `0x1800252c5`
- `ntdll!RtlAcquireResourceShared` at `0x180025174`
- `ntdll!RtlAcquireResourceShared` at `0x180025174`
- `KERNEL32!LeaveCriticalSection` at `0x180024dfc`
- `KERNEL32!LeaveCriticalSection` at `0x180024f29`
- `KERNEL32!LeaveCriticalSection` at `0x180025304`
- `KERNEL32!LeaveCriticalSection` at `0x18002530e`
- `KERNEL32!LeaveCriticalSection` at `0x180024dfc`
- `KERNEL32!LeaveCriticalSection` at `0x180024f29`
- `KERNEL32!LeaveCriticalSection` at `0x180025304`
- `KERNEL32!LeaveCriticalSection` at `0x18002530e`
- `KERNEL32!EnterCriticalSection` at `0x180024de1`
- `KERNEL32!EnterCriticalSection` at `0x180024f16`
- `KERNEL32!EnterCriticalSection` at `0x1800252f1`
- `KERNEL32!EnterCriticalSection` at `0x180024de1`
- `KERNEL32!EnterCriticalSection` at `0x180024f16`
- `KERNEL32!EnterCriticalSection` at `0x1800252f1`

## string_xrefs

- `0x18002503b`: `InterfaceConnected: GetCompleteIPv6AddressForClient: Failed with error %d`

## pseudocode

```c
__int64 __fastcall InterfaceConnected(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 *v6; // rax
  int v8; // eax
  int *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // r13
  __int128 *v12; // r9
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // r14
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  unsigned int CompleteIPv6AddressForClient; // eax
  __int128 *v21; // r9
  _DWORD *v22; // rax
  _DWORD *v23; // rcx
  char v24; // dl
  int v25; // ecx
  __int64 *v26; // rcx
  _QWORD *i; // rdi
  void (__fastcall *v28)(_QWORD, __int64 *); // rax
  __int64 *v29; // rdx
  __int64 *v30; // r12
  unsigned int v31; // r13d
  __int64 j; // rdi
  __int64 (__fastcall *v33)(__int64); // rax
  unsigned int v34; // eax
  __int128 *v35; // r9
  __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v37; // [rsp+38h] [rbp-C8h]
  int *v38; // [rsp+40h] [rbp-C0h]
  __int64 *v39; // [rsp+48h] [rbp-B8h]
  __int64 InternalInterfaceForRoutingDomain; // [rsp+50h] [rbp-B0h]
  __int128 v41; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v42; // [rsp+68h] [rbp-98h] BYREF
  int v43; // [rsp+78h] [rbp-88h]
  int v44; // [rsp+80h] [rbp-80h] BYREF
  __int128 v45; // [rsp+84h] [rbp-7Ch]
  __int128 v46; // [rsp+94h] [rbp-6Ch]
  int v47; // [rsp+A4h] [rbp-5Ch]
  int v48; // [rsp+B0h] [rbp-50h] BYREF
  char v49[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v48 = 0;
  LODWORD(v36) = a4 == 33;
  v6 = &g_rgicInfoCbv4;
  if ( a4 != 33 )
    v6 = &g_rgicInfoCbv6;
  v39 = v6;
  v8 = 5;
  if ( a4 != 33 )
    v8 = 3;
  v37 = v8;
  v9 = &g_bUninitServerv4;
  if ( a4 != 33 )
    v9 = &g_bUninitServerv6;
  v38 = v9;
  memset_0(v49, 0, sizeof(v49));
  v44 = 0;
  v47 = 0;
  v45 = 0;
  v46 = 0;
  v41 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( !(_DWORD)RouterState )
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v48) = 0;
      FormatRRASErrorString(&v48, L"Entered: %ws", L"InterfaceConnected");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v48);
    }
    RtlAcquireResourceExclusive(&Resource, 1u);
    v10 = InterfaceLookupByICBSeqNumber(a1);
    InternalInterfaceForRoutingDomain = GetInternalInterfaceForRoutingDomain((struct _GUID *)(v10 + 688), a4);
    v11 = InternalInterfaceForRoutingDomain;
    if ( !v10 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v48) = 0;
        FormatRRASErrorString(&v48, L"InterfaceConnected : No interface with ICB number %d", a1);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v48);
      }
      goto LABEL_77;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v48) = 0;
      LOWORD(v44) = 0;
      FormatRRASErrorString(
        &v48,
        L"InterfaceConnected: InterfaceConnected called for %ws. State is %d. V4 = %d",
        *(_QWORD *)(v10 + 72),
        *(unsigned int *)(v10 + 168),
        *(_DWORD *)(v10 + 516));
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v12 = &v41;
        if ( v10 != -688 )
          LODWORD(v12) = v10 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v48,
          (_DWORD)v12,
          *(_QWORD *)(v10 + 72),
          (__int64)&v44);
      }
    }
    if ( !*(_DWORD *)(v10 + 144) )
    {
      if ( !InternalInterfaceForRoutingDomain )
      {
        RtlReleaseResource(&Resource);
        EnterCriticalSection(&RouterStateLock);
        --HIDWORD(RouterState);
        LeaveCriticalSection(&RouterStateLock);
        return 1609;
      }
      if ( *v38 )
        TryUpdateInternalInterface(InternalInterfaceForRoutingDomain, v36);
    }
    if ( *(_DWORD *)(v10 + 168) == 1 )
      WanInterfaceDownToInactive(v10);
    if ( *(_DWORD *)(v10 + 168) != 3 )
      *(_DWORD *)(v10 + 168) = 3;
    *(_DWORD *)(v10 + 180) |= 2u;
    if ( (*(_BYTE *)(v10 + 180) & 3) != 3 )
      goto LABEL_77;
    *(_DWORD *)(v10 + 168) = 4;
    if ( *(_DWORD *)(v10 + 144) )
    {
      RtlConvertExclusiveToShared(&Resource);
      WanInterfaceInactiveToUp(v10);
    }
    else
    {
      v36 = 0;
      v43 = 0;
      v42 = 0;
      if ( a4 == 33 )
      {
        v14 = 32;
        v15 = 12;
        v16 = a3 + 36;
        v17 = a3 + 56;
      }
      else
      {
        v17 = 52;
        v14 = a3 + 92;
        v15 = a3 + 72;
        v16 = 32;
      }
      v18 = *(_QWORD *)(v10 + 712);
      *(_DWORD *)(v10 + 668) = 1;
      *(_DWORD *)(v10 + 512) = 1;
      if ( a4 == 33 )
      {
        *(_DWORD *)v18 = *(_DWORD *)v16;
        v19 = *(_DWORD *)v17;
      }
      else
      {
        CompleteIPv6AddressForClient = GetCompleteIPv6AddressForClient((__int64 *)v15, (_QWORD *)(v18 + 4));
        if ( CompleteIPv6AddressForClient )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v48) = 0;
            LOWORD(v44) = 0;
            FormatRRASErrorString(
              &v48,
              L"InterfaceConnected: GetCompleteIPv6AddressForClient: Failed with error %d",
              CompleteIPv6AddressForClient);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v21 = &v41;
              if ( v10 != -688 )
                LODWORD(v21) = v10 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v48,
                (_DWORD)v21,
                *(_QWORD *)(v10 + 72),
                (__int64)&v44);
            }
          }
          goto LABEL_77;
        }
        **(_DWORD **)(v10 + 712) = 128;
        *(_DWORD *)(*(_QWORD *)(v10 + 712) + 24LL) = 1;
        v19 = *(_DWORD *)v14;
      }
      *(_DWORD *)(*(_QWORD *)(v10 + 712) + 20LL) = v19;
      if ( *(_DWORD *)(v11 + 512) )
      {
        v22 = *(_DWORD **)(v11 + 712);
        v23 = *(_DWORD **)(v10 + 712);
        if ( a4 == 33 )
          v23[1] = v22[1];
        else
          *v23 = *v22;
      }
      else if ( a4 == 33 )
      {
        v24 = *(_BYTE *)v16;
        if ( *(char *)v16 < 0 )
        {
          if ( (v24 & 0xC0) == 0x80 )
          {
            v25 = 0xFFFF;
          }
          else
          {
            v25 = -1;
            if ( (v24 & 0xE0) == 0xC0 )
              v25 = 0xFFFFFF;
          }
        }
        else
        {
          v25 = 255;
        }
        *(_DWORD *)(*(_QWORD *)(v10 + 712) + 4LL) = v25;
      }
      *(_DWORD *)(*(_QWORD *)(v10 + 712) + 24LL) = 1;
      v26 = *(__int64 **)(v10 + 712);
      if ( a4 == 33 )
      {
        v36 = *v26;
      }
      else
      {
        v42 = *(_OWORD *)((char *)v26 + 4);
        v43 = *(_DWORD *)v26;
      }
      RtlAcquireResourceShared(&stru_18008C4A0, 1u);
      for ( i = *(_QWORD **)(v11 + 56); i != (_QWORD *)(v11 + 56); i = (_QWORD *)*i )
      {
        v28 = *(void (__fastcall **)(_QWORD, __int64 *))(i[3] + 184LL);
        if ( v28 )
        {
          v29 = (__int64 *)&v42;
          if ( a4 == 33 )
            v29 = &v36;
          v28(*(unsigned int *)(v11 + 16), v29);
        }
      }
      RtlReleaseResource(&stru_18008C4A0);
      v30 = v39;
      v31 = v37;
      for ( j = 0; (unsigned int)j < v31; j = (unsigned int)(j + 1) )
      {
        v33 = (__int64 (__fastcall *)(__int64))v30[5 * j + 3];
        if ( v33 )
        {
          v34 = v33(v10);
          if ( v34 )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              LOWORD(v48) = 0;
              LOWORD(v44) = 0;
              FormatRRASErrorString(
                &v48,
                L"InterfaceConnected: Error %d binding %ws for %hs info",
                v34,
                *(_QWORD *)(v10 + 72),
                v30[5 * j]);
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                v35 = &v41;
                if ( v10 != -688 )
                  LODWORD(v35) = v10 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrMgrParamTraceError,
                  (unsigned int)&v48,
                  (_DWORD)v35,
                  *(_QWORD *)(v10 + 72),
                  (__int64)&v44);
              }
            }
          }
        }
      }
      AddAllClientRoutes(v10, *(_DWORD *)(InternalInterfaceForRoutingDomain + 16));
    }
LABEL_77:
    RtlReleaseResource(&Resource);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: InterfaceConnected");
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    return 0;
  }
  LeaveCriticalSection(&RouterStateLock);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v48) = 0;
    FormatRRASErrorString(&v48, L"error %d on RM API", 900);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v48);
  }
  return 900;
}

```

## disassembly

```asm
0x180024d28  mov     [rsp-8+arg_8], rbx
0x180024d2d  push    rbp
0x180024d2e  push    rsi
0x180024d2f  push    rdi
0x180024d30  push    r12
0x180024d32  push    r13
0x180024d34  push    r14
0x180024d36  push    r15
0x180024d38  lea     rbp, [rsp-7C0h]
0x180024d40  sub     rsp, 8C0h
0x180024d47  mov     rax, cs:__security_cookie
0x180024d4e  xor     rax, rsp
0x180024d51  mov     [rbp+7F0h+var_40], rax
0x180024d58  xor     ebx, ebx
0x180024d5a  mov     rdi, rcx
0x180024d5d  cmp     r9d, 21h ; '!'
0x180024d61  mov     [rbp+7F0h+var_840], ebx
0x180024d64  mov     eax, ebx
0x180024d66  lea     rcx, g_rgicInfoCbv6
0x180024d6d  setz    al
0x180024d70  mov     r12, r8
0x180024d73  mov     dword ptr [rsp+8F0h+var_8C0], eax
0x180024d77  mov     r8d, 7FCh; Size
0x180024d7d  lea     rax, g_rgicInfoCbv4
0x180024d84  mov     r15d, r9d
0x180024d87  cmovnz  rax, rcx
0x180024d8b  lea     ecx, [rbx+3]
0x180024d8e  mov     [rsp+8F0h+var_8A8], rax
0x180024d93  lea     eax, [rbx+5]
0x180024d96  cmovnz  eax, ecx
0x180024d99  lea     rcx, g_bUninitServerv6
0x180024da0  mov     [rsp+8F0h+var_8B8], eax
0x180024da4  lea     rax, g_bUninitServerv4
0x180024dab  cmovnz  rax, rcx
0x180024daf  xor     edx, edx; Val
0x180024db1  lea     rcx, [rbp+7F0h+var_83C]; void *
0x180024db5  mov     [rsp+8F0h+var_8B0], rax
0x180024dba  call    memset_0
0x180024dbf  xorps   xmm0, xmm0
0x180024dc2  mov     [rbp+7F0h+var_870], ebx
0x180024dc5  xor     eax, eax
0x180024dc7  lea     rsi, RouterStateLock
0x180024dce  mov     rcx, rsi; lpCriticalSection
0x180024dd1  mov     [rbp+7F0h+var_84C], eax
0x180024dd4  movups  [rbp+7F0h+var_86C], xmm0
0x180024dd8  movups  [rbp+7F0h+var_85C], xmm0
0x180024ddc  movups  [rsp+8F0h+var_898], xmm0
0x180024de1  call    cs:__imp_EnterCriticalSection
0x180024de7  cmp     dword ptr cs:RouterState, ebx
0x180024ded  mov     rcx, rsi; lpCriticalSection
0x180024df0  jnz     loc_18002530E
0x180024df6  inc     dword ptr cs:RouterState+4
0x180024dfc  call    cs:__imp_LeaveCriticalSection
0x180024e02  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180024e08  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024e0f  jge     short loc_180024E47
0x180024e11  lea     r8, aInterfaceconne_0; "InterfaceConnected"
0x180024e18  mov     word ptr [rbp+7F0h+var_840], bx
0x180024e1c  lea     rdx, aEnteredWs; "Entered: %ws"
0x180024e23  lea     rcx, [rbp+7F0h+var_840]
0x180024e27  call    FormatRRASErrorString
0x180024e2c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180024e32  jge     short loc_180024E47
0x180024e34  lea     r8, [rbp+7F0h+var_840]
0x180024e38  mov     rcx, rsi
0x180024e3b  lea     rdx, RasRtrmgrTraceInfo
0x180024e42  call    McTemplateU0z_EventWriteTransfer
0x180024e47  mov     dl, 1; Wait
0x180024e49  lea     rcx, Resource; Resource
0x180024e50  call    cs:__imp_RtlAcquireResourceExclusive
0x180024e56  mov     ecx, edi
0x180024e58  call    InterfaceLookupByICBSeqNumber
0x180024e5d  mov     edx, r15d; unsigned int
0x180024e60  mov     rbx, rax
0x180024e63  lea     r14, [rax+2B0h]
0x180024e6a  mov     rcx, r14; struct _GUID *
0x180024e6d  call    GetInternalInterfaceForRoutingDomain
0x180024e72  mov     [rsp+8F0h+var_8A0], rax
0x180024e77  mov     r13, rax
0x180024e7a  test    rbx, rbx
0x180024e7d  jz      loc_180025280
0x180024e83  xor     edi, edi
0x180024e85  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180024e8c  jge     short loc_180024EF5
0x180024e8e  mov     word ptr [rbp+7F0h+var_840], di
0x180024e92  lea     rdx, aInterfaceconne_1; "InterfaceConnected: InterfaceConnected "...
0x180024e99  mov     word ptr [rbp+7F0h+var_870], di
0x180024e9d  lea     rcx, [rbp+7F0h+var_840]
0x180024ea1  mov     eax, [rbx+204h]
0x180024ea7  mov     r9d, [rbx+0A8h]
0x180024eae  mov     r8, [rbx+48h]
0x180024eb2  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x180024eb6  call    FormatRRASErrorString
0x180024ebb  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180024ec2  jge     short loc_180024EF5
0x180024ec4  lea     rax, [rbp+7F0h+var_870]
0x180024ec8  test    r14, r14
0x180024ecb  mov     [rsp+8F0h+var_8C8], rax
0x180024ed0  lea     r9, [rsp+8F0h+var_898]
0x180024ed5  mov     rax, [rbx+48h]
0x180024ed9  lea     r8, [rbp+7F0h+var_840]
0x180024edd  cmovnz  r9, r14
0x180024ee1  mov     [rsp+8F0h+var_8D0], rax
0x180024ee6  lea     rdx, RasRtrmgrParamTraceInfo
0x180024eed  mov     rcx, rsi
0x180024ef0  call    McTemplateU0zjzz_EventWriteTransfer
0x180024ef5  cmp     [rbx+90h], edi
0x180024efb  jnz     short loc_180024F4E
0x180024efd  test    r13, r13
0x180024f00  jnz     short loc_180024F39
0x180024f02  lea     rcx, Resource; Resource
0x180024f09  call    cs:__imp_RtlReleaseResource
0x180024f0f  lea     rcx, RouterStateLock; lpCriticalSection
0x180024f16  call    cs:__imp_EnterCriticalSection
0x180024f1c  dec     dword ptr cs:RouterState+4
0x180024f22  lea     rcx, RouterStateLock; lpCriticalSection
0x180024f29  call    cs:__imp_LeaveCriticalSection
0x180024f2f  mov     eax, 649h
0x180024f34  jmp     loc_180025359
0x180024f39  mov     rax, [rsp+8F0h+var_8B0]
0x180024f3e  cmp     [rax], edi
0x180024f40  jz      short loc_180024F4E
0x180024f42  mov     edx, dword ptr [rsp+8F0h+var_8C0]
0x180024f46  mov     rcx, r13
0x180024f49  call    TryUpdateInternalInterface
0x180024f4e  cmp     dword ptr [rbx+0A8h], 1
0x180024f55  jnz     short loc_180024F5F
0x180024f57  mov     rcx, rbx
0x180024f5a  call    WanInterfaceDownToInactive
0x180024f5f  mov     ecx, 3
0x180024f64  cmp     [rbx+0A8h], ecx
0x180024f6a  jz      short loc_180024F72
0x180024f6c  mov     [rbx+0A8h], ecx
0x180024f72  or      dword ptr [rbx+0B4h], 2
0x180024f79  mov     eax, [rbx+0B4h]
0x180024f7f  and     eax, ecx
0x180024f81  cmp     al, cl
0x180024f83  jnz     loc_1800252BE
0x180024f89  mov     dword ptr [rbx+0A8h], 4
0x180024f93  cmp     [rbx+90h], edi
0x180024f99  jz      short loc_180024FB5
0x180024f9b  lea     rcx, Resource; Resource
0x180024fa2  call    cs:__imp_RtlConvertExclusiveToShared
0x180024fa8  mov     rcx, rbx
0x180024fab  call    WanInterfaceInactiveToUp
0x180024fb0  jmp     loc_1800252BE
0x180024fb5  xor     eax, eax
0x180024fb7  mov     [rsp+8F0h+var_8C0], rdi
0x180024fbc  mov     [rsp+8F0h+var_878], eax
0x180024fc0  xorps   xmm0, xmm0
0x180024fc3  movups  [rsp+8F0h+var_888], xmm0
0x180024fc8  cmp     r15d, 21h ; '!'
0x180024fcc  jnz     short loc_180024FE0
0x180024fce  lea     edi, [rax+20h]
0x180024fd1  lea     eax, [rdi-14h]
0x180024fd4  lea     r14, [r12+24h]
0x180024fd9  lea     rdx, [r12+38h]
0x180024fde  jmp     short loc_180024FF3
0x180024fe0  mov     edx, 34h ; '4'
0x180024fe5  lea     rdi, [r12+5Ch]
0x180024fea  lea     rax, [r12+48h]
0x180024fef  lea     r14d, [rdx-14h]
0x180024ff3  mov     rcx, [rbx+2C8h]
0x180024ffa  mov     dword ptr [rbx+29Ch], 1
0x180025004  mov     dword ptr [rbx+200h], 1
0x18002500e  jnz     short loc_18002501C
0x180025010  mov     eax, [r14]
0x180025013  mov     [rcx], eax
0x180025015  mov     eax, [rdx]
0x180025017  jmp     loc_1800250BD
0x18002501c  lea     rdx, [rcx+4]
0x180025020  mov     rcx, rax
0x180025023  call    GetCompleteIPv6AddressForClient
0x180025028  test    eax, eax
0x18002502a  jz      short loc_1800250A0
0x18002502c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025033  jz      loc_1800252BE
0x180025039  xor     ecx, ecx
0x18002503b  lea     rdx, aInterfaceconne; "InterfaceConnected: GetCompleteIPv6Addr"...
0x180025042  mov     word ptr [rbp+7F0h+var_840], cx
0x180025046  mov     r8d, eax
0x180025049  mov     word ptr [rbp+7F0h+var_870], cx
0x18002504d  lea     rcx, [rbp+7F0h+var_840]
0x180025051  call    FormatRRASErrorString
0x180025056  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002505d  jz      loc_1800252BE
0x180025063  lea     r15, [rbx+2B0h]
0x18002506a  mov     rcx, rsi
0x18002506d  lea     rax, [rbp+7F0h+var_870]
0x180025071  test    r15, r15
0x180025074  mov     [rsp+8F0h+var_8C8], rax
0x180025079  lea     r9, [rsp+8F0h+var_898]
0x18002507e  mov     rax, [rbx+48h]
0x180025082  lea     r8, [rbp+7F0h+var_840]
0x180025086  cmovnz  r9, r15
0x18002508a  mov     [rsp+8F0h+var_8D0], rax
0x18002508f  lea     rdx, RasRtrMgrParamTraceError
0x180025096  call    McTemplateU0zjzz_EventWriteTransfer
0x18002509b  jmp     loc_1800252BE
0x1800250a0  mov     rax, [rbx+2C8h]
0x1800250a7  mov     dword ptr [rax], 80h
0x1800250ad  mov     rax, [rbx+2C8h]
0x1800250b4  mov     dword ptr [rax+18h], 1
0x1800250bb  mov     eax, [rdi]
0x1800250bd  mov     rcx, [rbx+2C8h]
0x1800250c4  mov     [rcx+14h], eax
0x1800250c7  cmp     dword ptr [r13+200h], 0
0x1800250cf  jz      short loc_1800250F3
0x1800250d1  mov     rax, [r13+2C8h]
0x1800250d8  mov     rcx, [rbx+2C8h]
0x1800250df  cmp     r15d, 21h ; '!'
0x1800250e3  jnz     short loc_1800250ED
0x1800250e5  mov     eax, [rax+4]
0x1800250e8  mov     [rcx+4], eax
0x1800250eb  jmp     short loc_180025131
0x1800250ed  mov     eax, [rax]
0x1800250ef  mov     [rcx], eax
0x1800250f1  jmp     short loc_180025131
0x1800250f3  cmp     r15d, 21h ; '!'
0x1800250f7  jnz     short loc_180025131
0x1800250f9  mov     dl, [r14]
0x1800250fc  test    dl, dl
0x1800250fe  js      short loc_180025107
0x180025100  mov     ecx, 0FFh
0x180025105  jmp     short loc_180025127
0x180025107  mov     al, dl
0x180025109  and     al, 0C0h
0x18002510b  cmp     al, 80h
0x18002510d  jnz     short loc_180025116
0x18002510f  mov     ecx, 0FFFFh
0x180025114  jmp     short loc_180025127
0x180025116  or      ecx, 0FFFFFFFFh
0x180025119  and     dl, 0E0h
0x18002511c  cmp     dl, 0C0h
0x18002511f  mov     eax, 0FFFFFFh
0x180025124  cmovz   ecx, eax
0x180025127  mov     rax, [rbx+2C8h]
0x18002512e  mov     [rax+4], ecx
0x180025131  mov     rax, [rbx+2C8h]
0x180025138  mov     dword ptr [rax+18h], 1
0x18002513f  mov     rcx, [rbx+2C8h]
0x180025146  cmp     r15d, 21h ; '!'
0x18002514a  jnz     short loc_18002515B
0x18002514c  mov     eax, [rcx]
0x18002514e  mov     dword ptr [rsp+8F0h+var_8C0], eax
0x180025152  mov     eax, [rcx+4]
0x180025155  mov     dword ptr [rsp+8F0h+var_8C0+4], eax
0x180025159  jmp     short loc_18002516B
0x18002515b  movups  xmm0, xmmword ptr [rcx+4]
0x18002515f  movdqu  [rsp+8F0h+var_888], xmm0
0x180025165  mov     eax, [rcx]
0x180025167  mov     [rsp+8F0h+var_878], eax
0x18002516b  mov     dl, 1; Wait
0x18002516d  lea     rcx, stru_18008C4A0; Resource
0x180025174  call    cs:__imp_RtlAcquireResourceShared
0x18002517a  lea     r14, [r13+38h]
0x18002517e  mov     rdi, [r14]
0x180025181  jmp     short loc_1800251B1
0x180025183  mov     rax, [rdi+18h]
0x180025187  mov     rax, [rax+0B8h]
0x18002518e  test    rax, rax
0x180025191  jz      short loc_1800251AE
0x180025193  lea     rcx, [rsp+8F0h+var_8C0]
0x180025198  cmp     r15d, 21h ; '!'
0x18002519c  lea     rdx, [rsp+8F0h+var_888]
0x1800251a1  cmovz   rdx, rcx
0x1800251a5  mov     ecx, [r13+10h]
0x1800251a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251ae  mov     rdi, [rdi]
0x1800251b1  cmp     rdi, r14
0x1800251b4  jnz     short loc_180025183
0x1800251b6  lea     rcx, stru_18008C4A0; Resource
0x1800251bd  call    cs:__imp_RtlReleaseResource
0x1800251c3  mov     r12, [rsp+8F0h+var_8A8]
0x1800251c8  lea     r15, [rbx+2B0h]
0x1800251cf  mov     r13d, [rsp+8F0h+var_8B8]
0x1800251d4  xor     edi, edi
0x1800251d6  cmp     edi, r13d
0x1800251d9  jnb     loc_18002526D
0x1800251df  lea     r14, [rdi+rdi*4]
0x1800251e3  mov     rax, [r12+r14*8+18h]
0x1800251e8  test    rax, rax
0x1800251eb  jz      short loc_180025266
0x1800251ed  mov     rcx, rbx
0x1800251f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251f5  test    eax, eax
0x1800251f7  jz      short loc_180025266
0x1800251f9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180025200  jz      short loc_180025266
0x180025202  xor     ecx, ecx
0x180025204  lea     rdx, aInterfaceconne_3; "InterfaceConnected: Error %d binding %w"...
0x18002520b  mov     word ptr [rbp+7F0h+var_840], cx
0x18002520f  mov     r8d, eax
0x180025212  mov     word ptr [rbp+7F0h+var_870], cx
0x180025216  mov     rcx, [r12+r14*8]
0x18002521a  mov     r9, [rbx+48h]
0x18002521e  mov     [rsp+8F0h+var_8D0], rcx
0x180025223  lea     rcx, [rbp+7F0h+var_840]
0x180025227  call    FormatRRASErrorString
0x18002522c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
  ... truncated ...
```
