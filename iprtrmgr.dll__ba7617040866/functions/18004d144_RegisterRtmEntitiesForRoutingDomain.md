# RegisterRtmEntitiesForRoutingDomain

- ea: `0x18004d144`
- end: `0x18004d81b`
- name: `RegisterRtmEntitiesForRoutingDomain`
- size: `1751`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020238`
- `0x1800208c4`
- `0x1800236d4`

## callees

- `0x180002040`
- `0x18000ac60`
- `0x180011790`
- `0x18004d144`
- `0x180056018`
- `0x180057b34`
- `0x180057e14`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18004d212`
- `KERNEL32!HeapAlloc` at `0x18004d212`
- `rtm!RtmRegisterForChangeNotification` at `0x18004d411`
- `rtm!RtmRegisterForChangeNotification` at `0x18004d60d`
- `rtm!RtmRegisterForChangeNotification` at `0x18004d411`
- `rtm!RtmRegisterForChangeNotification` at `0x18004d60d`
- `rtm!RtmRegisterEntity` at `0x18004d305`
- `rtm!RtmRegisterEntity` at `0x18004d4d5`
- `rtm!RtmRegisterEntity` at `0x18004d523`
- `rtm!RtmRegisterEntity` at `0x18004d575`
- `rtm!RtmRegisterEntity` at `0x18004d5cb`
- `rtm!RtmRegisterEntity` at `0x18004d305`
- `rtm!RtmRegisterEntity` at `0x18004d4d5`
- `rtm!RtmRegisterEntity` at `0x18004d523`
- `rtm!RtmRegisterEntity` at `0x18004d575`
- `rtm!RtmRegisterEntity` at `0x18004d5cb`

## string_xrefs

- `0x18004d249`: `RegisterRtmEntitiesForRoutingDomain: HeapAlloc failed for compartment Id %d (%d)`
- `0x18004d33f`: `RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for local routes failed for compartment Id (%d) (%d) `
- `0x18004d42c`: `RegisterRtmEntitiesForRoutingDomain: RtmRegisterForChangeNotificaition failed for compartment Id %d (%d)`
- `0x18004d4ec`: `RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for AutoStatic routes failed for compartment Id %d (%d)`
- `0x18004d53e`: `RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for Static routes failed for compartment Id %d (%d)`
- `0x18004d590`: `RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for DOD routes failed for compartment Id %d (%d)`
- `0x18004d5e6`: `RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for NetMgmt routes failed for compartmentId %d (%d)`

## pseudocode

```c
__int64 __fastcall RegisterRtmEntitiesForRoutingDomain(unsigned int a1, struct _GUID *a2)
{
  unsigned int CompartmentIdForRoutingDomain; // r14d
  DWORD v5; // edi
  _QWORD *v6; // rbx
  __int128 *v7; // r9
  RtMgrRdConfigStore *Instance; // rax
  DWORD v9; // eax
  char v10; // cl
  __int128 *v11; // r9
  bool v12; // sf
  char v13; // al
  const wchar_t *v14; // rdx
  __int128 *v15; // r9
  unsigned __int64 v16; // rcx
  HANDLE RtmRegHandle; // [rsp+30h] [rbp-8C8h] BYREF
  HANDLE v19; // [rsp+38h] [rbp-8C0h] BYREF
  HANDLE v20; // [rsp+40h] [rbp-8B8h] BYREF
  HANDLE v21; // [rsp+48h] [rbp-8B0h] BYREF
  HANDLE v22; // [rsp+50h] [rbp-8A8h] BYREF
  HANDLE v23; // [rsp+58h] [rbp-8A0h] BYREF
  HANDLE NotifyHandle; // [rsp+60h] [rbp-898h] BYREF
  struct _RTM_ENTITY_INFO RtmEntityInfo; // [rsp+68h] [rbp-890h] BYREF
  __int128 v26; // [rsp+78h] [rbp-880h] BYREF
  int v27; // [rsp+88h] [rbp-870h] BYREF
  __int128 v28; // [rsp+8Ch] [rbp-86Ch]
  __int128 v29; // [rsp+9Ch] [rbp-85Ch]
  int v30; // [rsp+ACh] [rbp-84Ch]
  int v31; // [rsp+B0h] [rbp-848h] BYREF
  _BYTE v32[2044]; // [rsp+B4h] [rbp-844h] BYREF

  RtmEntityInfo = 0;
  RtmRegHandle = 0;
  v19 = 0;
  v21 = 0;
  CompartmentIdForRoutingDomain = GetCompartmentIdForRoutingDomain(a2);
  v22 = 0;
  v20 = 0;
  NotifyHandle = 0;
  v23 = 0;
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v27 = 0;
  v28 = 0;
  v30 = 0;
  v29 = 0;
  v5 = 8;
  v26 = 0;
  v6 = HeapAlloc(IPRouterHeap, 8u, 0x60u);
  if ( v6 )
  {
    Instance = RtMgrRdConfigStore::GetInstance();
    RtmEntityInfo.RtmInstanceId = RtMgrRdConfigStore::GetRtmInstanceId(Instance, a2);
    if ( a1 == 33 )
      RtmEntityInfo.AddressFamily = 2;
    else
      RtmEntityInfo.AddressFamily = 23;
    RtmEntityInfo.EntityId.EntityId = 2;
    v9 = RtmRegisterEntity(&RtmEntityInfo, 0, RtmEventCallback, 0, &g_rtmProfile, &RtmRegHandle);
    v5 = v9;
    if ( v9 )
    {
      v10 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v31) = 0;
        LOWORD(v27) = 0;
        FormatRRASErrorString(
          &v31,
          L"RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for local routes failed for compartment Id (%d) (%d) ",
          CompartmentIdForRoutingDomain,
          v9);
        v10 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v11 = &v26;
          if ( a2 )
            LODWORD(v11) = (_DWORD)a2;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v31,
            (_DWORD)v11,
            0,
            (__int64)&v27);
          v10 = Microsoft_Windows_RRASEnableBits;
        }
      }
      v12 = v10 < 0;
      goto LABEL_17;
    }
    v5 = RtmRegisterForChangeNotification(RtmRegHandle, 1u, 4u, 0, &NotifyHandle);
    if ( v5 )
    {
LABEL_21:
      v13 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v14 = L"RegisterRtmEntitiesForRoutingDomain: RtmRegisterForChangeNotificaition failed for compartment Id %d (%d)";
        goto LABEL_23;
      }
LABEL_27:
      v12 = v13 < 0;
LABEL_17:
      if ( v12 )
      {
        LOWORD(v31) = 0;
        FormatRRASErrorString(&v31, L"Leaving: %ws", L"RegisterRtmEntitiesForRoutingDomain");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v31);
      }
LABEL_48:
      *(_DWORD *)v6 = 2;
      v6[1] = RtmRegHandle;
      *((_DWORD *)v6 + 1) = 0;
      *((_DWORD *)v6 + 4) = 10002;
      v6[3] = v19;
      *((_DWORD *)v6 + 5) = 1;
      *((_DWORD *)v6 + 8) = 10006;
      v6[5] = v21;
      *((_DWORD *)v6 + 9) = 1;
      *((_DWORD *)v6 + 12) = 10007;
      v6[7] = v22;
      *((_DWORD *)v6 + 13) = 1;
      *((_DWORD *)v6 + 16) = 3;
      v6[9] = v20;
      *((_DWORD *)v6 + 17) = 0;
      v6[10] = v23;
      v6[11] = NotifyHandle;
      SetRtmRegistrationInfo(a2, a1, (struct _RTM_ENTITY_REGISTRATION_INFO *)v6);
      return v5;
    }
    RtmEntityInfo.EntityId.EntityProtocolId = 10002;
    v5 = RtmRegisterEntity(&RtmEntityInfo, 0, 0, 0, &g_rtmProfile, &v19);
    if ( v5 )
    {
      v13 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_27;
      v14 = L"RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for AutoStatic routes failed for compartment Id %d (%d)";
    }
    else
    {
      RtmEntityInfo.EntityId.EntityProtocolId = 10006;
      v5 = RtmRegisterEntity(&RtmEntityInfo, 0, 0, 0, &g_rtmProfile, &v21);
      if ( v5 )
      {
        v13 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_27;
        v14 = L"RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for Static routes failed for compartment Id %d (%d)";
      }
      else
      {
        RtmEntityInfo.EntityId.EntityProtocolId = 10007;
        v5 = RtmRegisterEntity(&RtmEntityInfo, 0, 0, 0, &g_rtmProfile, &v22);
        if ( v5 )
        {
          v13 = Microsoft_Windows_RRASEnableBits;
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
            goto LABEL_27;
          v14 = L"RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for DOD routes failed for compartment Id %d (%d)";
        }
        else
        {
          RtmEntityInfo.EntityId.EntityProtocolId = 3;
          v5 = RtmRegisterEntity(&RtmEntityInfo, 0, RtmEventCallback, 1, &g_rtmProfile, &v20);
          if ( !v5 )
          {
            v5 = RtmRegisterForChangeNotification(v20, 1u, 0x10001u, 0, &v23);
            if ( !v5 )
            {
              v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
              if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
                v16 = *(_QWORD *)a2->Data4 - _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0];
              if ( !v16 )
              {
                if ( a1 == 33 )
                {
                  g_hLocalRoute = RtmRegHandle;
                  g_hAutoStaticRoute = v19;
                  *(_DWORD *)v6 = 2;
                  v6[1] = RtmRegHandle;
                  *((_DWORD *)v6 + 1) = 0;
                  *((_DWORD *)v6 + 4) = 10002;
                  v6[3] = v19;
                  *((_DWORD *)v6 + 5) = 1;
                  *((_DWORD *)v6 + 8) = 10006;
                  v6[5] = v21;
                  *((_DWORD *)v6 + 9) = 1;
                  *((_DWORD *)v6 + 12) = 10007;
                  v6[7] = v22;
                  *((_DWORD *)v6 + 13) = 1;
                  *((_DWORD *)v6 + 16) = 3;
                  v6[9] = v20;
                  *((_DWORD *)v6 + 17) = 0;
                }
                else if ( a1 == 87 )
                {
                  g_hLocalRouteV6 = RtmRegHandle;
                  qword_18008CAC8 = (__int64)RtmRegHandle;
                  qword_18008CAD8 = (__int64)v19;
                  qword_18008CAE8 = (__int64)v21;
                  qword_18008CAF8 = (__int64)v22;
                  qword_18008CB08 = (__int64)v20;
                  g_rgRtmHandlesV6 = 2;
                  dword_18008CAD0 = 10002;
                  dword_18008CAD4 = 1;
                  dword_18008CAE0 = 10006;
                  dword_18008CAE4 = 1;
                  dword_18008CAF0 = 10007;
                  dword_18008CAF4 = 1;
                  qword_18008CB00 = 3;
                }
              }
              goto LABEL_48;
            }
            goto LABEL_21;
          }
          v13 = Microsoft_Windows_RRASEnableBits;
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
            goto LABEL_27;
          v14 = L"RegisterRtmEntitiesForRoutingDomain: RtmRegisterClient for NetMgmt routes failed for compartmentId %d (%d)";
        }
      }
    }
LABEL_23:
    LOWORD(v31) = 0;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v31, v14, CompartmentIdForRoutingDomain, v5);
    v13 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v15 = &v26;
      if ( a2 )
        LODWORD(v15) = (_DWORD)a2;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v31,
        (_DWORD)v15,
        0,
        (__int64)&v27);
      v13 = Microsoft_Windows_RRASEnableBits;
    }
    goto LABEL_27;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v31) = 0;
    LOWORD(v27) = 0;
    FormatRRASErrorString(
      &v31,
      L"RegisterRtmEntitiesForRoutingDomain: HeapAlloc failed for compartment Id %d (%d)",
      CompartmentIdForRoutingDomain,
      8);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v7 = &v26;
      if ( a2 )
        LODWORD(v7) = (_DWORD)a2;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v31,
        (_DWORD)v7,
        0,
        (__int64)&v27);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18004d144  mov     rax, rsp
0x18004d147  mov     [rax+18h], rbx
0x18004d14b  mov     [rax+20h], rsi
0x18004d14f  push    rdi
0x18004d150  push    r12
0x18004d152  push    r13
0x18004d154  push    r14
0x18004d156  push    r15
0x18004d158  sub     rsp, 8D0h
0x18004d15f  movaps  xmmword ptr [rax-38h], xmm6
0x18004d163  mov     rax, cs:__security_cookie
0x18004d16a  xor     rax, rsp
0x18004d16d  mov     [rsp+8F8h+var_48], rax
0x18004d175  mov     r15d, ecx
0x18004d178  xorps   xmm0, xmm0
0x18004d17b  mov     rcx, rdx
0x18004d17e  mov     rsi, rdx
0x18004d181  movups  xmmword ptr [rsp+8F8h+RtmEntityInfo.RtmInstanceId], xmm0
0x18004d186  call    GetCompartmentIdForRoutingDomain
0x18004d18b  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18004d192  xor     r12d, r12d
0x18004d195  lea     rcx, [rsp+8F8h+var_844]; void *
0x18004d19d  xor     edx, edx; Val
0x18004d19f  mov     [rsp+8F8h+var_8C8], r12
0x18004d1a4  mov     r8d, 7FCh; Size
0x18004d1aa  mov     [rsp+8F8h+var_8C0], r12
0x18004d1af  mov     [rsp+8F8h+var_8B0], r12
0x18004d1b4  mov     r14d, eax
0x18004d1b7  mov     [rsp+8F8h+var_8A8], r12
0x18004d1bc  mov     [rsp+8F8h+var_8B8], r12
0x18004d1c1  mov     [rsp+8F8h+NotifyHandle], r12
0x18004d1c6  mov     [rsp+8F8h+var_8A0], r12
0x18004d1cb  mov     [rsp+8F8h+var_848], r12d
0x18004d1d3  call    memset_0
0x18004d1d8  mov     rcx, cs:IPRouterHeap; hHeap
0x18004d1df  lea     r8d, [r12+60h]; dwBytes
0x18004d1e4  xorps   xmm0, xmm0
0x18004d1e7  mov     [rsp+8F8h+var_870], r12d
0x18004d1ef  xor     eax, eax
0x18004d1f1  movups  [rsp+8F8h+var_86C], xmm0
0x18004d1f9  mov     [rsp+8F8h+var_84C], eax
0x18004d200  movups  [rsp+8F8h+var_85C], xmm0
0x18004d208  lea     edi, [rax+8]
0x18004d20b  mov     edx, edi; dwFlags
0x18004d20d  movups  [rsp+8F8h+var_880], xmm0
0x18004d212  call    cs:__imp_HeapAlloc
0x18004d218  mov     rbx, rax
0x18004d21b  test    rax, rax
0x18004d21e  jnz     loc_18004D2A8
0x18004d224  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004d22b  jz      loc_18004D7E7
0x18004d231  mov     r9d, edi
0x18004d234  mov     word ptr [rsp+8F8h+var_848], r12w
0x18004d23d  mov     r8d, r14d
0x18004d240  mov     word ptr [rsp+8F8h+var_870], r12w
0x18004d249  lea     rdx, aRegisterrtment_4; "RegisterRtmEntitiesForRoutingDomain: He"...
0x18004d250  lea     rcx, [rsp+8F8h+var_848]
0x18004d258  call    FormatRRASErrorString
0x18004d25d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004d264  jz      loc_18004D7E7
0x18004d26a  test    rsi, rsi
0x18004d26d  lea     rax, [rsp+8F8h+var_870]
0x18004d275  mov     [rsp+8F8h+RtmRegHandle], rax
0x18004d27a  lea     r9, [rsp+8F8h+var_880]
0x18004d27f  cmovnz  r9, rsi
0x18004d283  mov     [rsp+8F8h+RtmRegProfile], r12
0x18004d288  lea     r8, [rsp+8F8h+var_848]
0x18004d290  lea     rdx, RasRtrMgrParamTraceError
0x18004d297  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004d29e  call    McTemplateU0zjzz_EventWriteTransfer
0x18004d2a3  jmp     loc_18004D7E7
0x18004d2a8  call    ?GetInstance@RtMgrRdConfigStore@@SAPEAV1@XZ; RtMgrRdConfigStore::GetInstance(void)
0x18004d2ad  mov     rdx, rsi; struct _GUID *
0x18004d2b0  mov     rcx, rax; this
0x18004d2b3  call    ?GetRtmInstanceId@RtMgrRdConfigStore@@QEAAGPEAU_GUID@@@Z; RtMgrRdConfigStore::GetRtmInstanceId(_GUID *)
0x18004d2b8  mov     [rsp+8F8h+RtmEntityInfo.RtmInstanceId], ax
0x18004d2bd  mov     ecx, 2
0x18004d2c2  cmp     r15d, 21h ; '!'
0x18004d2c6  jnz     short loc_18004D2CF
0x18004d2c8  mov     [rsp+8F8h+RtmEntityInfo.AddressFamily], cx
0x18004d2cd  jmp     short loc_18004D2D9
0x18004d2cf  mov     eax, 17h
0x18004d2d4  mov     [rsp+8F8h+RtmEntityInfo.AddressFamily], ax
0x18004d2d9  lea     rax, [rsp+8F8h+var_8C8]
0x18004d2de  mov     qword ptr [rsp+8F8h+RtmEntityInfo.EntityId], rcx
0x18004d2e3  mov     [rsp+8F8h+RtmRegHandle], rax; RtmRegHandle
0x18004d2e8  lea     r8, RtmEventCallback; EventCallback
0x18004d2ef  lea     rax, g_rtmProfile
0x18004d2f6  xor     r9d, r9d; ReserveOpaquePointer
0x18004d2f9  xor     edx, edx; ExportMethods
0x18004d2fb  mov     [rsp+8F8h+RtmRegProfile], rax; RtmRegProfile
0x18004d300  lea     rcx, [rsp+8F8h+RtmEntityInfo]; RtmEntityInfo
0x18004d305  call    cs:__imp_RtmRegisterEntity
0x18004d30b  mov     edi, eax
0x18004d30d  mov     r13d, 1
0x18004d313  test    eax, eax
0x18004d315  jz      loc_18004D3F8
0x18004d31b  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18004d322  test    cl, 40h
0x18004d325  jz      short loc_18004D39F
0x18004d327  mov     r9d, eax
0x18004d32a  mov     word ptr [rsp+8F8h+var_848], r12w
0x18004d333  mov     r8d, r14d
0x18004d336  mov     word ptr [rsp+8F8h+var_870], r12w
0x18004d33f  lea     rdx, aRegisterrtment_3; "RegisterRtmEntitiesForRoutingDomain: Rt"...
0x18004d346  lea     rcx, [rsp+8F8h+var_848]
0x18004d34e  call    FormatRRASErrorString
0x18004d353  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18004d35a  test    cl, 40h
0x18004d35d  jz      short loc_18004D39F
0x18004d35f  test    rsi, rsi
0x18004d362  lea     rax, [rsp+8F8h+var_870]
0x18004d36a  mov     [rsp+8F8h+RtmRegHandle], rax
0x18004d36f  lea     r9, [rsp+8F8h+var_880]
0x18004d374  cmovnz  r9, rsi
0x18004d378  mov     [rsp+8F8h+RtmRegProfile], r12
0x18004d37d  lea     r8, [rsp+8F8h+var_848]
0x18004d385  lea     rdx, RasRtrMgrParamTraceError
0x18004d38c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004d393  call    McTemplateU0zjzz_EventWriteTransfer
0x18004d398  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18004d39f  test    cl, cl
0x18004d3a1  jns     loc_18004D764
0x18004d3a7  lea     r8, aRegisterrtment_0; "RegisterRtmEntitiesForRoutingDomain"
0x18004d3ae  mov     word ptr [rsp+8F8h+var_848], r12w
0x18004d3b7  lea     rdx, aLeavingWs; "Leaving: %ws"
0x18004d3be  lea     rcx, [rsp+8F8h+var_848]
0x18004d3c6  call    FormatRRASErrorString
0x18004d3cb  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18004d3d2  jge     loc_18004D764
0x18004d3d8  lea     r8, [rsp+8F8h+var_848]
0x18004d3e0  lea     rdx, RasRtrmgrTraceInfo
0x18004d3e7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004d3ee  call    McTemplateU0z_EventWriteTransfer
0x18004d3f3  jmp     loc_18004D764
0x18004d3f8  mov     rcx, [rsp+8F8h+var_8C8]; RtmRegHandle
0x18004d3fd  lea     rax, [rsp+8F8h+NotifyHandle]
0x18004d402  xor     r9d, r9d; NotifyContext
0x18004d405  mov     [rsp+8F8h+RtmRegProfile], rax; NotifyHandle
0x18004d40a  mov     edx, r13d; TargetViews
0x18004d40d  lea     r8d, [r9+4]; NotifyFlags
0x18004d411  call    cs:__imp_RtmRegisterForChangeNotification
0x18004d417  mov     edi, eax
0x18004d419  test    eax, eax
0x18004d41b  jz      loc_18004D4AA
0x18004d421  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004d428  test    al, 40h
0x18004d42a  jz      short loc_18004D4A3
0x18004d42c  lea     rdx, aRegisterrtment_1; "RegisterRtmEntitiesForRoutingDomain: Rt"...
0x18004d433  mov     r9d, edi
0x18004d436  mov     word ptr [rsp+8F8h+var_848], r12w
0x18004d43f  mov     r8d, r14d
0x18004d442  mov     word ptr [rsp+8F8h+var_870], r12w
0x18004d44b  lea     rcx, [rsp+8F8h+var_848]
0x18004d453  call    FormatRRASErrorString
0x18004d458  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004d45f  test    al, 40h
0x18004d461  jz      short loc_18004D4A3
0x18004d463  test    rsi, rsi
0x18004d466  lea     rax, [rsp+8F8h+var_870]
0x18004d46e  mov     [rsp+8F8h+RtmRegHandle], rax
0x18004d473  lea     r9, [rsp+8F8h+var_880]
0x18004d478  cmovnz  r9, rsi
0x18004d47c  mov     [rsp+8F8h+RtmRegProfile], r12
0x18004d481  lea     r8, [rsp+8F8h+var_848]
0x18004d489  lea     rdx, RasRtrMgrParamTraceError
0x18004d490  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004d497  call    McTemplateU0zjzz_EventWriteTransfer
0x18004d49c  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004d4a3  test    al, al
0x18004d4a5  jmp     loc_18004D3A1
0x18004d4aa  lea     rax, [rsp+8F8h+var_8C0]
0x18004d4af  mov     dword ptr [rsp+8F8h+RtmEntityInfo.EntityId], 2712h
0x18004d4b7  mov     [rsp+8F8h+RtmRegHandle], rax; RtmRegHandle
0x18004d4bc  lea     rcx, [rsp+8F8h+RtmEntityInfo]; RtmEntityInfo
0x18004d4c1  lea     rax, g_rtmProfile
0x18004d4c8  xor     r9d, r9d; ReserveOpaquePointer
0x18004d4cb  xor     r8d, r8d; EventCallback
0x18004d4ce  mov     [rsp+8F8h+RtmRegProfile], rax; RtmRegProfile
0x18004d4d3  xor     edx, edx; ExportMethods
0x18004d4d5  call    cs:__imp_RtmRegisterEntity
0x18004d4db  mov     edi, eax
0x18004d4dd  test    eax, eax
0x18004d4df  jz      short loc_18004D4F8
0x18004d4e1  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004d4e8  test    al, 40h
0x18004d4ea  jz      short loc_18004D4A3
0x18004d4ec  lea     rdx, aRegisterrtment_2; "RegisterRtmEntitiesForRoutingDomain: Rt"...
0x18004d4f3  jmp     loc_18004D433
0x18004d4f8  lea     rax, [rsp+8F8h+var_8B0]
0x18004d4fd  mov     dword ptr [rsp+8F8h+RtmEntityInfo.EntityId], 2716h
0x18004d505  mov     [rsp+8F8h+RtmRegHandle], rax; RtmRegHandle
0x18004d50a  lea     rcx, [rsp+8F8h+RtmEntityInfo]; RtmEntityInfo
0x18004d50f  lea     rax, g_rtmProfile
0x18004d516  xor     r9d, r9d; ReserveOpaquePointer
0x18004d519  xor     r8d, r8d; EventCallback
0x18004d51c  mov     [rsp+8F8h+RtmRegProfile], rax; RtmRegProfile
0x18004d521  xor     edx, edx; ExportMethods
0x18004d523  call    cs:__imp_RtmRegisterEntity
0x18004d529  mov     edi, eax
0x18004d52b  test    eax, eax
0x18004d52d  jz      short loc_18004D54A
0x18004d52f  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004d536  test    al, 40h
0x18004d538  jz      loc_18004D4A3
0x18004d53e  lea     rdx, aRegisterrtment; "RegisterRtmEntitiesForRoutingDomain: Rt"...
0x18004d545  jmp     loc_18004D433
0x18004d54a  lea     rax, [rsp+8F8h+var_8A8]
0x18004d54f  mov     dword ptr [rsp+8F8h+RtmEntityInfo.EntityId], 2717h
0x18004d557  mov     [rsp+8F8h+RtmRegHandle], rax; RtmRegHandle
0x18004d55c  lea     rcx, [rsp+8F8h+RtmEntityInfo]; RtmEntityInfo
0x18004d561  lea     rax, g_rtmProfile
0x18004d568  xor     r9d, r9d; ReserveOpaquePointer
0x18004d56b  xor     r8d, r8d; EventCallback
0x18004d56e  mov     [rsp+8F8h+RtmRegProfile], rax; RtmRegProfile
0x18004d573  xor     edx, edx; ExportMethods
0x18004d575  call    cs:__imp_RtmRegisterEntity
0x18004d57b  mov     edi, eax
0x18004d57d  test    eax, eax
0x18004d57f  jz      short loc_18004D59C
0x18004d581  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004d588  test    al, 40h
0x18004d58a  jz      loc_18004D4A3
0x18004d590  lea     rdx, aRegisterrtment_6; "RegisterRtmEntitiesForRoutingDomain: Rt"...
0x18004d597  jmp     loc_18004D433
0x18004d59c  lea     rax, [rsp+8F8h+var_8B8]
0x18004d5a1  mov     dword ptr [rsp+8F8h+RtmEntityInfo.EntityId], 3
0x18004d5a9  mov     [rsp+8F8h+RtmRegHandle], rax; RtmRegHandle
0x18004d5ae  lea     r8, RtmEventCallback; EventCallback
0x18004d5b5  lea     rax, g_rtmProfile
0x18004d5bc  mov     r9d, r13d; ReserveOpaquePointer
0x18004d5bf  xor     edx, edx; ExportMethods
0x18004d5c1  mov     [rsp+8F8h+RtmRegProfile], rax; RtmRegProfile
0x18004d5c6  lea     rcx, [rsp+8F8h+RtmEntityInfo]; RtmEntityInfo
0x18004d5cb  call    cs:__imp_RtmRegisterEntity
0x18004d5d1  mov     edi, eax
0x18004d5d3  test    eax, eax
0x18004d5d5  jz      short loc_18004D5F2
0x18004d5d7  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004d5de  test    al, 40h
0x18004d5e0  jz      loc_18004D4A3
0x18004d5e6  lea     rdx, aRegisterrtment_5; "RegisterRtmEntitiesForRoutingDomain: Rt"...
0x18004d5ed  jmp     loc_18004D433
0x18004d5f2  mov     rcx, [rsp+8F8h+var_8B8]; RtmRegHandle
0x18004d5f7  lea     rax, [rsp+8F8h+var_8A0]
0x18004d5fc  xor     r9d, r9d; NotifyContext
0x18004d5ff  mov     [rsp+8F8h+RtmRegProfile], rax; NotifyHandle
0x18004d604  mov     r8d, 10001h; NotifyFlags
0x18004d60a  mov     edx, r13d; TargetViews
0x18004d60d  call    cs:__imp_RtmRegisterForChangeNotification
0x18004d613  mov     edi, eax
0x18004d615  test    eax, eax
0x18004d617  jnz     loc_18004D421
0x18004d61d  mov     rcx, [rsi]
0x18004d620  movq    rax, xmm6
0x18004d625  sub     rcx, rax
0x18004d628  jnz     short loc_18004D63B
0x18004d62a  mov     rcx, [rsi+8]
0x18004d62e  psrldq  xmm6, 8
0x18004d633  movq    rax, xmm6
0x18004d638  sub     rcx, rax
0x18004d63b  test    rcx, rcx
0x18004d63e  jnz     loc_18004D764
0x18004d644  cmp     r15d, 21h ; '!'
0x18004d648  jnz     loc_18004D6CE
0x18004d64e  mov     rax, [rsp+8F8h+var_8C8]
0x18004d653  mov     cs:g_hLocalRoute, rax
0x18004d65a  mov     rax, [rsp+8F8h+var_8C0]
0x18004d65f  mov     cs:g_hAutoStaticRoute, rax
0x18004d666  mov     dword ptr [rbx], 2
0x18004d66c  mov     rax, [rsp+8F8h+var_8C8]
0x18004d671  mov     [rbx+8], rax
0x18004d675  mov     [rbx+4], r12d
0x18004d679  mov     dword ptr [rbx+10h], 2712h
0x18004d680  mov     rax, [rsp+8F8h+var_8C0]
0x18004d685  mov     [rbx+18h], rax
0x18004d689  mov     [rbx+14h], r13d
0x18004d68d  mov     dword ptr [rbx+20h], 2716h
0x18004d694  mov     rax, [rsp+8F8h+var_8B0]
0x18004d699  mov     [rbx+28h], rax
0x18004d69d  mov     [rbx+24h], r13d
0x18004d6a1  mov     dword ptr [rbx+30h], 2717h
0x18004d6a8  mov     rax, [rsp+8F8h+var_8A8]
0x18004d6ad  mov     [rbx+38h], rax
0x18004d6b1  mov     [rbx+34h], r13d
0x18004d6b5  mov     dword ptr [rbx+40h], 3
0x18004d6bc  mov     rax, [rsp+8F8h+var_8B8]
0x18004d6c1  mov     [rbx+48h], rax
0x18004d6c5  mov     [rbx+44h], r12d
0x18004d6c9  jmp     loc_18004D764
0x18004d6ce  cmp     r15d, 57h ; 'W'
0x18004d6d2  jnz     loc_18004D764
0x18004d6d8  mov     rax, [rsp+8F8h+var_8C8]
0x18004d6dd  mov     cs:g_hLocalRouteV6, rax
0x18004d6e4  mov     cs:qword_18008CAC8, rax
0x18004d6eb  mov     rax, [rsp+8F8h+var_8C0]
0x18004d6f0  mov     cs:qword_18008CAD8, rax
0x18004d6f7  mov     rax, [rsp+8F8h+var_8B0]
0x18004d6fc  mov     cs:qword_18008CAE8, rax
0x18004d703  mov     rax, [rsp+8F8h+var_8A8]
  ... truncated ...
```
