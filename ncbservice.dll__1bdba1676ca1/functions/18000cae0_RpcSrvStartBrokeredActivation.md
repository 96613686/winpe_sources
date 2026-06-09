# RpcSrvStartBrokeredActivation

- ea: `0x18000cae0`
- end: `0x18000d2ac`
- name: `RpcSrvStartBrokeredActivation`
- size: `1996`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003f00`
- `0x180005d70`
- `0x180006540`
- `0x18000a0a0`
- `0x18000a160`
- `0x18000add0`
- `0x18000be70`
- `0x18000c820`
- `0x18000cae0`
- `0x180017b94`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000cd93`
- `ntdll!RtlInitUnicodeString` at `0x18000cd93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cbac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cbac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d0af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d0af`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000cc53`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000cc53`
- `api-ms-win-core-bicltapi-l1-1-6!BiCreateEventForPackageName` at `0x18000d139`
- `api-ms-win-core-bicltapi-l1-1-6!BiCreateEventForPackageName` at `0x18000d139`

## string_xrefs

- `0x18000cde5`: `NcbReg:RpcSrvStartBrokeredExecution finished with`
- `0x18000ce5d`: `RpcSrvStartBrokeredExecution`
- `0x18000d155`: `NcbReg:BiCreateEvent for push notification failed with`
- `0x18000d25e`: `NcbReg: Could not create WPM context`

## pseudocode

```c
__int64 __fastcall RpcSrvStartBrokeredActivation(
        __int64 a1,
        unsigned int a2,
        char a3,
        unsigned int a4,
        _OWORD *a5,
        _OWORD *a6,
        __int64 a7)
{
  PVOID *v10; // rcx
  unsigned int ControlChannelTriggerContext; // eax
  unsigned int updated; // ebx
  unsigned int IsContextAllowed; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  char *v16; // rcx
  const WCHAR *v17; // rdx
  struct _UNICODE_STRING *p_DestinationString; // rbx
  LPVOID v19; // rax
  HRESULT Guid; // eax
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  char *v26; // rdi
  char v27; // al
  PVOID *v28; // rcx
  __int64 v30; // rdx
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rdx
  unsigned int EventForPackageName; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  PVOID v37; // rcx
  PVOID v38; // rcx
  LPVOID lpMem; // [rsp+40h] [rbp-B8h] BYREF
  char v40[8]; // [rsp+48h] [rbp-B0h] BYREF
  unsigned int v41; // [rsp+50h] [rbp-A8h] BYREF
  int v42; // [rsp+58h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v44[16]; // [rsp+70h] [rbp-88h] BYREF
  const wchar_t *v45; // [rsp+80h] [rbp-78h]
  __int64 v46; // [rsp+88h] [rbp-70h]
  unsigned int *v47; // [rsp+90h] [rbp-68h]
  __int64 v48; // [rsp+98h] [rbp-60h]
  const char *v49; // [rsp+A0h] [rbp-58h]
  __int64 v50; // [rsp+A8h] [rbp-50h]
  int *v51; // [rsp+B0h] [rbp-48h]
  __int64 v52; // [rsp+B8h] [rbp-40h]

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  lpMem = 0;
  v40[0] = 0;
  DestinationString = 0;
  if ( !a7 )
  {
    if ( v10 == &WPP_GLOBAL_Control )
      return 87;
    if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 2u )
    {
      WPP_SF_(v10[2], 156, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 || *((_BYTE *)v10 + 25) < 6u )
      return 87;
    v33 = 157;
    goto LABEL_72;
  }
  if ( !a5 )
  {
    if ( v10 == &WPP_GLOBAL_Control )
      return 87;
    if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 2u )
    {
      WPP_SF_(v10[2], 158, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 || *((_BYTE *)v10 + 25) < 6u )
      return 87;
    v33 = 159;
    goto LABEL_72;
  }
  if ( a6 )
  {
    ControlChannelTriggerContext = FindOrCreateControlChannelTriggerContext(0, 0, 0, 0, a7, 0, (__int64 *)&lpMem);
    updated = ControlChannelTriggerContext;
    if ( ControlChannelTriggerContext )
    {
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return updated;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          162,
          &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids,
          ControlChannelTriggerContext);
        v28 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v28 == &WPP_GLOBAL_Control || (*((_BYTE *)v28 + 28) & 1) == 0 || *((_BYTE *)v28 + 25) < 6u )
        return updated;
      v30 = 163;
      goto LABEL_33;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 24));
    if ( a4 - 1 > 3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, a4);
      }
    }
    else
    {
      *((_DWORD *)lpMem + 102) = a4;
      IsContextAllowed = NcbRegistrarPolicyIsContextAllowed(lpMem, 255, v40);
      updated = IsContextAllowed;
      if ( IsContextAllowed )
      {
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(
            v15,
            v14,
            L"NcbReg: Policy context for internal client is not allowed",
            IsContextAllowed);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, updated);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 24));
        goto LABEL_109;
      }
    }
    if ( a3 && *((_BYTE *)lpMem + 232) )
    {
      updated = 5;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 24));
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_109;
      }
      v32 = 166;
    }
    else
    {
      *((_BYTE *)lpMem + 360) = a3;
      *((_DWORD *)lpMem + 94) = -1;
      v16 = (char *)lpMem;
      v17 = (const WCHAR *)*((_QWORD *)lpMem + 30);
      if ( v17 )
      {
        RtlInitUnicodeString(&DestinationString, v17);
        v16 = (char *)lpMem;
        p_DestinationString = &DestinationString;
      }
      else
      {
        p_DestinationString = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 24));
      v19 = lpMem;
      if ( a3 )
      {
        if ( *((_BYTE *)lpMem + 340) )
          goto LABEL_16;
        Guid = CoCreateGuid((GUID *)((char *)lpMem + 324));
        if ( Guid < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            168,
            &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids,
            (unsigned int)Guid);
        }
        goto LABEL_15;
      }
      if ( *((_BYTE *)lpMem + 340) )
      {
LABEL_16:
        v21 = KamSetKeepAliveIntervalTime(v19, a2);
        updated = v21;
        if ( v21 )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v21);
          }
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(v37, v22, L"NcbReg: KA timer start call failed", updated);
        }
        else
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 24));
          updated = NcbRegpCreateOrUpdateWPMContext(lpMem);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 24));
          if ( !updated )
          {
            v26 = (char *)lpMem;
            *a5 = *(_OWORD *)((char *)lpMem + 308);
            *a6 = *(_OWORD *)(v26 + 324);
LABEL_19:
            v27 = Microsoft_Windows_Network_Connection_BrokerEnableBits;
            if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            {
              v41 = updated;
              v45 = L"NcbReg:RpcSrvStartBrokeredExecution finished with";
              v46 = 100;
              v47 = &v41;
              v48 = 4;
              McGenEventWrite_EventWriteTransfer(v24, NcbApiStatus, v25, 3, v44);
              v27 = Microsoft_Windows_Network_Connection_BrokerEnableBits;
              v26 = (char *)lpMem;
            }
            if ( (v27 & 2) != 0 )
            {
              v41 = *((_DWORD *)v26 + 16);
              v42 = 2409;
              v45 = L"RpcSrvStartBrokeredExecution";
              v47 = &v41;
              v49 = "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\ncbreg.c";
              v51 = &v42;
              v46 = 58;
              v48 = 4;
              v50 = 47;
              v52 = 4;
              McGenEventWrite_EventWriteTransfer(v24, NcbDereferenceContext, v25, 5, v44);
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 16, 0xFFFFFFFF) == 1 )
              CleanupContextHelper(v26);
            v28 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
            {
              return updated;
            }
            v30 = 171;
LABEL_33:
            WPP_SF_d(v28[2], v30, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, updated);
            return updated;
          }
          v38 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              170,
              &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids,
              updated);
          }
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(v38, v23, L"NcbReg: Could not create WPM context", updated);
        }
LABEL_109:
        KamDestroyTimer((__int64)lpMem);
        v26 = (char *)lpMem;
        if ( !*((_BYTE *)lpMem + 340) && !*((_BYTE *)lpMem + 360) )
        {
          CloseBiEvent((char *)lpMem + 324);
          v26 = (char *)lpMem;
        }
        goto LABEL_19;
      }
      EventForPackageName = BiCreateEventForPackageName(
                              (char *)lpMem + 324,
                              g_NCB_BROKER_ID,
                              p_DestinationString,
                              *((_QWORD *)lpMem + 34),
                              82058,
                              0,
                              0);
      updated = EventForPackageName;
      if ( !EventForPackageName )
      {
LABEL_15:
        v19 = lpMem;
        goto LABEL_16;
      }
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v36,
          v35,
          L"NcbReg:BiCreateEvent for push notification failed with",
          EventForPackageName);
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_109;
      }
      v32 = 167;
    }
    WPP_SF_d(v31[2], v32, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, updated);
    goto LABEL_109;
  }
  if ( v10 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 2u )
    {
      WPP_SF_(v10[2], 160, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    {
      v33 = 161;
LABEL_72:
      WPP_SF_(v10[2], v33, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
    }
  }
  return 87;
}

```

## disassembly

```asm
0x18000cae0  mov     [rsp+arg_0], rbx
0x18000cae5  mov     [rsp+arg_10], rsi
0x18000caea  push    rdi
0x18000caeb  push    r12
0x18000caed  push    r13
0x18000caef  push    r14
0x18000caf1  push    r15
0x18000caf3  sub     rsp, 0D0h
0x18000cafa  mov     rax, cs:__security_cookie
0x18000cb01  xor     rax, rsp
0x18000cb04  mov     [rsp+0F8h+var_38], rax
0x18000cb0c  mov     r14, [rsp+0F8h+arg_20]
0x18000cb14  mov     esi, r9d
0x18000cb17  mov     r15, [rsp+0F8h+arg_28]
0x18000cb1f  movzx   edi, r8b
0x18000cb23  mov     rbx, [rsp+0F8h+arg_30]
0x18000cb2b  mov     r12d, edx
0x18000cb2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb35  lea     r13, WPP_GLOBAL_Control
0x18000cb3c  cmp     rcx, r13
0x18000cb3f  jnz     loc_18000CD30
0x18000cb45  mov     [rsp+0F8h+lpMem], 0
0x18000cb4e  xorps   xmm0, xmm0
0x18000cb51  mov     [rsp+0F8h+var_B0], 0
0x18000cb56  movups  xmmword ptr [rsp+0F8h+DestinationString.Length], xmm0
0x18000cb5b  test    rbx, rbx
0x18000cb5e  jz      loc_18000CEE1
0x18000cb64  test    r14, r14
0x18000cb67  jz      loc_18000CFA1
0x18000cb6d  test    r15, r15
0x18000cb70  jz      loc_18000CFF6
0x18000cb76  lea     rax, [rsp+0F8h+lpMem]
0x18000cb7b  xor     r9d, r9d
0x18000cb7e  mov     [rsp+0F8h+var_C8], rax
0x18000cb83  xor     r8d, r8d
0x18000cb86  mov     byte ptr [rsp+0F8h+var_D0], 0
0x18000cb8b  xor     edx, edx
0x18000cb8d  xor     ecx, ecx
0x18000cb8f  mov     [rsp+0F8h+var_D8], rbx
0x18000cb94  call    FindOrCreateControlChannelTriggerContext
0x18000cb99  mov     ebx, eax
0x18000cb9b  test    eax, eax
0x18000cb9d  jnz     loc_18000CEF0
0x18000cba3  mov     rcx, [rsp+0F8h+lpMem]
0x18000cba8  add     rcx, 18h; lpCriticalSection
0x18000cbac  call    cs:__imp_EnterCriticalSection
0x18000cbb2  lea     eax, [rsi-1]
0x18000cbb5  cmp     eax, 3
0x18000cbb8  ja      loc_18000D0BA
0x18000cbbe  mov     rax, [rsp+0F8h+lpMem]
0x18000cbc3  lea     r8, [rsp+0F8h+var_B0]
0x18000cbc8  mov     edx, 0FFh
0x18000cbcd  mov     [rax+198h], esi
0x18000cbd3  mov     rcx, [rsp+0F8h+lpMem]
0x18000cbd8  call    NcbRegistrarPolicyIsContextAllowed
0x18000cbdd  mov     ebx, eax
0x18000cbdf  test    eax, eax
0x18000cbe1  jnz     loc_18000D05E
0x18000cbe7  mov     rax, [rsp+0F8h+lpMem]
0x18000cbec  test    dil, dil
0x18000cbef  jz      short loc_18000CBFE
0x18000cbf1  cmp     byte ptr [rax+0E8h], 0
0x18000cbf8  jnz     loc_18000CDA8
0x18000cbfe  mov     [rax+168h], dil
0x18000cc05  mov     rax, [rsp+0F8h+lpMem]
0x18000cc0a  mov     dword ptr [rax+178h], 0FFFFFFFFh
0x18000cc14  mov     rcx, [rsp+0F8h+lpMem]
0x18000cc19  mov     rdx, [rcx+0F0h]; SourceString
0x18000cc20  test    rdx, rdx
0x18000cc23  jnz     loc_18000CD8E
0x18000cc29  xor     ebx, ebx
0x18000cc2b  add     rcx, 18h; lpCriticalSection
0x18000cc2f  call    cs:__imp_LeaveCriticalSection
0x18000cc35  mov     rax, [rsp+0F8h+lpMem]
0x18000cc3a  test    dil, dil
0x18000cc3d  jz      loc_18000D0FB
0x18000cc43  cmp     byte ptr [rax+154h], 0
0x18000cc4a  jnz     short loc_18000CC66
0x18000cc4c  lea     rcx, [rax+144h]; pguid
0x18000cc53  call    cs:__imp_CoCreateGuid
0x18000cc59  test    eax, eax
0x18000cc5b  js      loc_18000D1A2
0x18000cc61  mov     rax, [rsp+0F8h+lpMem]
0x18000cc66  mov     edx, r12d
0x18000cc69  mov     rcx, rax
0x18000cc6c  call    KamSetKeepAliveIntervalTime
0x18000cc71  mov     ebx, eax
0x18000cc73  test    eax, eax
0x18000cc75  jnz     loc_18000D1E3
0x18000cc7b  mov     rcx, [rsp+0F8h+lpMem]
0x18000cc80  add     rcx, 18h; lpCriticalSection
0x18000cc84  call    cs:__imp_EnterCriticalSection
0x18000cc8a  mov     rcx, [rsp+0F8h+lpMem]
0x18000cc8f  call    NcbRegpCreateOrUpdateWPMContext
0x18000cc94  mov     rcx, [rsp+0F8h+lpMem]
0x18000cc99  mov     ebx, eax
0x18000cc9b  add     rcx, 18h; lpCriticalSection
0x18000cc9f  call    cs:__imp_LeaveCriticalSection
0x18000cca5  test    ebx, ebx
0x18000cca7  jnz     loc_18000D225
0x18000ccad  mov     rdi, [rsp+0F8h+lpMem]
0x18000ccb2  movups  xmm0, xmmword ptr [rdi+134h]
0x18000ccb9  movups  xmmword ptr [r14], xmm0
0x18000ccbd  movups  xmm0, xmmword ptr [rdi+144h]
0x18000ccc4  movups  xmmword ptr [r15], xmm0
0x18000ccc8  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x18000ccce  test    al, 1
0x18000ccd0  jnz     loc_18000CDE5
0x18000ccd6  test    al, 2
0x18000ccd8  jnz     loc_18000CE49
0x18000ccde  mov     eax, 0FFFFFFFFh
0x18000cce3  lock xadd [rdi+40h], eax
0x18000cce8  cmp     eax, 1
0x18000cceb  jnz     short loc_18000CCF5
0x18000cced  mov     rcx, rdi; lpMem
0x18000ccf0  call    CleanupContextHelper
0x18000ccf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccfc  cmp     rcx, r13
0x18000ccff  jnz     short loc_18000CD65
0x18000cd01  mov     eax, ebx
0x18000cd03  mov     rcx, [rsp+0F8h+var_38]
0x18000cd0b  xor     rcx, rsp; StackCookie
0x18000cd0e  call    __security_check_cookie
0x18000cd13  lea     r11, [rsp+0F8h+var_28]
0x18000cd1b  mov     rbx, [r11+30h]
0x18000cd1f  mov     rsi, [r11+40h]
0x18000cd23  mov     rsp, r11
0x18000cd26  pop     r15
0x18000cd28  pop     r14
0x18000cd2a  pop     r13
0x18000cd2c  pop     r12
0x18000cd2e  pop     rdi
0x18000cd2f  retn
0x18000cd30  test    byte ptr [rcx+1Ch], 1
0x18000cd34  jz      loc_18000CB45
0x18000cd3a  cmp     byte ptr [rcx+19h], 6
0x18000cd3e  jb      loc_18000CB45
0x18000cd44  mov     rcx, [rcx+10h]
0x18000cd48  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000cd4f  mov     edx, 9Bh
0x18000cd54  call    WPP_SF_
0x18000cd59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd60  jmp     loc_18000CB45
0x18000cd65  test    byte ptr [rcx+1Ch], 1
0x18000cd69  jz      short loc_18000CD01
0x18000cd6b  cmp     byte ptr [rcx+19h], 6
0x18000cd6f  jb      short loc_18000CD01
0x18000cd71  mov     edx, 0ABh
0x18000cd76  mov     rcx, [rcx+10h]
0x18000cd7a  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000cd81  mov     r9d, ebx
0x18000cd84  call    WPP_SF_d
0x18000cd89  jmp     loc_18000CD01
0x18000cd8e  lea     rcx, [rsp+0F8h+DestinationString]; DestinationString
0x18000cd93  call    cs:__imp_RtlInitUnicodeString
0x18000cd99  mov     rcx, [rsp+0F8h+lpMem]
0x18000cd9e  lea     rbx, [rsp+0F8h+DestinationString]
0x18000cda3  jmp     loc_18000CC2B
0x18000cda8  lea     rcx, [rax+18h]; lpCriticalSection
0x18000cdac  mov     ebx, 5
0x18000cdb1  call    cs:__imp_LeaveCriticalSection
0x18000cdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdbe  cmp     rcx, r13
0x18000cdc1  jz      loc_18000D26D
0x18000cdc7  test    byte ptr [rcx+1Ch], 1
0x18000cdcb  jz      loc_18000D26D
0x18000cdd1  cmp     byte ptr [rcx+19h], 2
0x18000cdd5  jb      loc_18000D26D
0x18000cddb  mov     edx, 0A6h
0x18000cde0  jmp     loc_18000D18A
0x18000cde5  lea     rax, aNcbregRpcsrvst; "NcbReg:RpcSrvStartBrokeredExecution fin"...
0x18000cdec  mov     [rsp+0F8h+var_A8], ebx
0x18000cdf0  mov     [rsp+0F8h+var_78], rax
0x18000cdf8  lea     rdx, NcbApiStatus
0x18000cdff  lea     rax, [rsp+0F8h+var_A8]
0x18000ce04  mov     [rsp+0F8h+var_70], 64h ; 'd'
0x18000ce10  mov     [rsp+0F8h+var_68], rax
0x18000ce18  mov     r9d, 3
0x18000ce1e  lea     rax, [rsp+0F8h+var_88]
0x18000ce23  mov     [rsp+0F8h+var_60], 4
0x18000ce2f  mov     [rsp+0F8h+var_D8], rax
0x18000ce34  call    McGenEventWrite_EventWriteTransfer
0x18000ce39  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x18000ce3f  mov     rdi, [rsp+0F8h+lpMem]
0x18000ce44  jmp     loc_18000CCD6
0x18000ce49  mov     eax, [rdi+40h]
0x18000ce4c  lea     rdx, NcbDereferenceContext
0x18000ce53  mov     [rsp+0F8h+var_A8], eax
0x18000ce57  mov     r9d, 5
0x18000ce5d  lea     rax, aRpcsrvstartbro; "RpcSrvStartBrokeredExecution"
0x18000ce64  mov     [rsp+0F8h+var_A0], 969h
0x18000ce6c  mov     [rsp+0F8h+var_78], rax
0x18000ce74  lea     rax, [rsp+0F8h+var_A8]
0x18000ce79  mov     [rsp+0F8h+var_68], rax
0x18000ce81  lea     rax, aOnecoreuapNetN_4; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18000ce88  mov     [rsp+0F8h+var_58], rax
0x18000ce90  lea     rax, [rsp+0F8h+var_A0]
0x18000ce95  mov     [rsp+0F8h+var_48], rax
0x18000ce9d  lea     rax, [rsp+0F8h+var_88]
0x18000cea2  mov     [rsp+0F8h+var_D8], rax
0x18000cea7  mov     [rsp+0F8h+var_70], 3Ah ; ':'
0x18000ceb3  mov     [rsp+0F8h+var_60], 4
0x18000cebf  mov     [rsp+0F8h+var_50], 2Fh ; '/'
0x18000cecb  mov     [rsp+0F8h+var_40], 4
0x18000ced7  call    McGenEventWrite_EventWriteTransfer
0x18000cedc  jmp     loc_18000CCDE
0x18000cee1  cmp     rcx, r13
0x18000cee4  jnz     short loc_18000CF52
0x18000cee6  mov     eax, 57h ; 'W'
0x18000ceeb  jmp     loc_18000CD03
0x18000cef0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cef7  cmp     rcx, r13
0x18000cefa  jz      loc_18000CD01
0x18000cf00  test    byte ptr [rcx+1Ch], 1
0x18000cf04  jz      short loc_18000CF2B
0x18000cf06  cmp     byte ptr [rcx+19h], 2
0x18000cf0a  jb      short loc_18000CF2B
0x18000cf0c  mov     rcx, [rcx+10h]
0x18000cf10  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000cf17  mov     edx, 0A2h
0x18000cf1c  mov     r9d, ebx
0x18000cf1f  call    WPP_SF_d
0x18000cf24  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf2b  cmp     rcx, r13
0x18000cf2e  jz      loc_18000CD01
0x18000cf34  test    byte ptr [rcx+1Ch], 1
0x18000cf38  jz      loc_18000CD01
0x18000cf3e  cmp     byte ptr [rcx+19h], 6
0x18000cf42  jb      loc_18000CD01
0x18000cf48  mov     edx, 0A3h
0x18000cf4d  jmp     loc_18000CD76
0x18000cf52  test    byte ptr [rcx+1Ch], 1
0x18000cf56  jz      short loc_18000CF7A
0x18000cf58  cmp     byte ptr [rcx+19h], 2
0x18000cf5c  jb      short loc_18000CF7A
0x18000cf5e  mov     rcx, [rcx+10h]
0x18000cf62  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000cf69  mov     edx, 9Ch
0x18000cf6e  call    WPP_SF_
0x18000cf73  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf7a  cmp     rcx, r13
0x18000cf7d  jz      loc_18000CEE6
0x18000cf83  test    byte ptr [rcx+1Ch], 1
0x18000cf87  jz      loc_18000CEE6
0x18000cf8d  cmp     byte ptr [rcx+19h], 6
0x18000cf91  jb      loc_18000CEE6
0x18000cf97  mov     edx, 9Dh
0x18000cf9c  jmp     loc_18000D049
0x18000cfa1  cmp     rcx, r13
0x18000cfa4  jz      loc_18000CEE6
0x18000cfaa  test    byte ptr [rcx+1Ch], 1
0x18000cfae  jz      short loc_18000CFD2
0x18000cfb0  cmp     byte ptr [rcx+19h], 2
0x18000cfb4  jb      short loc_18000CFD2
0x18000cfb6  mov     rcx, [rcx+10h]
0x18000cfba  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000cfc1  mov     edx, 9Eh
0x18000cfc6  call    WPP_SF_
0x18000cfcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfd2  cmp     rcx, r13
0x18000cfd5  jz      loc_18000CEE6
0x18000cfdb  test    byte ptr [rcx+1Ch], 1
0x18000cfdf  jz      loc_18000CEE6
0x18000cfe5  cmp     byte ptr [rcx+19h], 6
0x18000cfe9  jb      loc_18000CEE6
0x18000cfef  mov     edx, 9Fh
0x18000cff4  jmp     short loc_18000D049
0x18000cff6  cmp     rcx, r13
0x18000cff9  jz      loc_18000CEE6
0x18000cfff  test    byte ptr [rcx+1Ch], 1
0x18000d003  jz      short loc_18000D027
0x18000d005  cmp     byte ptr [rcx+19h], 2
0x18000d009  jb      short loc_18000D027
0x18000d00b  mov     rcx, [rcx+10h]
0x18000d00f  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000d016  mov     edx, 0A0h
0x18000d01b  call    WPP_SF_
0x18000d020  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d027  cmp     rcx, r13
0x18000d02a  jz      loc_18000CEE6
0x18000d030  test    byte ptr [rcx+1Ch], 1
0x18000d034  jz      loc_18000CEE6
0x18000d03a  cmp     byte ptr [rcx+19h], 6
0x18000d03e  jb      loc_18000CEE6
0x18000d044  mov     edx, 0A1h
0x18000d049  mov     rcx, [rcx+10h]
0x18000d04d  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000d054  call    WPP_SF_
0x18000d059  jmp     loc_18000CEE6
0x18000d05e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000d065  jz      short loc_18000D076
0x18000d067  mov     r9d, ebx
0x18000d06a  lea     r8, aNcbregPolicyCo; "NcbReg: Policy context for internal cli"...
0x18000d071  call    McTemplateU0zq_EventWriteTransfer
0x18000d076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d07d  cmp     rcx, r13
0x18000d080  jz      short loc_18000D0A6
0x18000d082  test    byte ptr [rcx+1Ch], 1
0x18000d086  jz      short loc_18000D0A6
0x18000d088  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
