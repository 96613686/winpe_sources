# TeredoRegisterWithWFP

- ea: `0x1800363b4`
- end: `0x180036838`
- name: `TeredoRegisterWithWFP`
- size: `1156`
- prototype: `__int64 __fastcall(void *context)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180013f64`
- `0x18003be70`
- `0x18005f440`

## callees

- `0x180004c54`
- `0x180004f50`
- `0x180005500`
- `0x180006c90`
- `0x180007698`
- `0x1800077d8`
- `0x18000d7b0`
- `0x1800190e0`
- `0x1800363b4`
- `0x180036840`
- `0x1800368d0`
- `0x18003d4a8`
- `0x180040f94`
- `0x180041b8c`
- `0x180042638`
- `0x18004b630`
- `0x18004c1c8`
- `0x18005f224`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800365e4`
- `RPCRT4!UuidCreate` at `0x1800365e4`
- `fwpuclnt!FwpmProviderAdd0` at `0x18003656e`
- `fwpuclnt!FwpmProviderAdd0` at `0x180036631`
- `fwpuclnt!FwpmProviderAdd0` at `0x18003656e`
- `fwpuclnt!FwpmProviderAdd0` at `0x180036631`
- `fwpuclnt!FwpmEngineClose0` at `0x18003678a`
- `fwpuclnt!FwpmEngineClose0` at `0x18003678a`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x180036759`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18003676f`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x180036759`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18003676f`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x1800366e2`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x1800366e2`

## string_xrefs

- `0x180036430`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18003670c`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180036450`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180036411`: `Teredo already registered with WFP.`
- `0x1800364d1`: `Teredo registering with WFP: Unable to open filtering engine (%u)`
- `0x180036511`: `Unable to create new sublayer, error : %u`

## pseudocode

```c
__int64 __fastcall TeredoRegisterWithWFP(FWPM_PROVIDER0 *context)
{
  bool v2; // zf
  __int64 result; // rax
  int v4; // eax
  HANDLE *p_providerData; // r14
  DWORD started; // eax
  DWORD v7; // edi
  __int64 v8; // rdx
  DWORD v9; // eax
  HANDLE v10; // rcx
  DWORD v11; // eax
  DWORD v12; // eax
  unsigned int v13; // eax
  HANDLE v14; // rcx
  DWORD v15; // eax
  HANDLE v16; // rcx
  DWORD v17; // eax
  HANDLE v18; // rcx
  DWORD v19; // eax
  int v20; // [rsp+28h] [rbp-81h]
  __int64 v21; // [rsp+40h] [rbp-69h] BYREF
  __int128 v22; // [rsp+50h] [rbp-59h]
  FWPM_FILTER_SUBSCRIPTION0 subscription; // [rsp+60h] [rbp-49h] BYREF
  char v24[8]; // [rsp+80h] [rbp-29h] BYREF
  GUID v25; // [rsp+88h] [rbp-21h]
  __int64 v26; // [rsp+B0h] [rbp+7h]

  memset_0(v24, 0, 0x48u);
  v2 = LODWORD(context[43].displayData.description) == 3;
  memset(&subscription, 0, sizeof(subscription));
  LODWORD(v21) = 0;
  if ( v2 )
  {
    EventWrite0(0x100000, L"Teredo already registered with WFP.");
    return 0;
  }
  EventWrite0(
    0x40000,
    L"ReferenceService: ++%u (%hs) @ %ls:%u",
    ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
    "TeredoRegisterWithWFP");
  do
  {
    v4 = g_Reference;
    if ( (g_Reference & 1) != 0 )
      return 1115;
  }
  while ( v4 != _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) );
  ReferenceCompartmentEx(context, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c", 1929);
  *((_BYTE *)&context[43].flags + 4) = 0;
  memset_0(v24, 0, 0x48u);
  p_providerData = (HANDLE *)&context[43].providerData;
  memset(&subscription, 0, sizeof(subscription));
  started = EtStartDynamicFilteringSession(L"Teredo Callback Session", &context[43].providerData);
  v7 = started;
  if ( started )
  {
    EventWriteError0(0x100000, L"Teredo registering with WFP: Unable to open filtering engine (%u)", started);
  }
  else
  {
    context[304].serviceName = (wchar_t *)&context[304].providerData.data;
    context[304].providerData.data = (UINT8 *)&context[304].providerData.data;
    *(_QWORD *)&context[304].providerData.size = (char *)context + 19488;
    *(_QWORD *)&context[304].flags = (char *)context + 19488;
    v9 = EtAddEtAuthorizationSubLayer(*p_providerData);
    v7 = v9;
    if ( v9 )
    {
      EventWriteError0(0x100000, L"Unable to create new sublayer, error : %u", v9);
    }
    else
    {
      memset_0(&context[305], 0, sizeof(FWPM_PROVIDER0));
      v10 = *p_providerData;
      context[305].displayData.description = L"Microsoft Windows Teredo firewall provider";
      context[305].flags = 0;
      context[305].displayData.name = L"Microsoft Corporation";
      context[305].providerKey = (GUID)TEREDO_WFP_PROVIDER_GUID;
      v11 = FwpmProviderAdd0(v10, context + 305, 0);
      v7 = v11;
      if ( v11 )
      {
        EventWriteError0(0x100000, L"Teredo registering with WFP: Teredo failed to plumb its provider. (%u)", v11);
      }
      else
      {
        v12 = EtPlumbAllFiltersIfNeededV6(
                *p_providerData,
                (int)L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
                (__int64)&context[304].providerData.data,
                (__int64)&context[304].flags,
                (__int64)&v21);
        v7 = v12;
        if ( v12 )
        {
          EventWriteError0(0x100000, L"Teredo registering with WFP: Unable to plumb filters for Teredo. (%u)", v12);
        }
        else
        {
          if ( (_DWORD)v21 == 1 )
            LODWORD(context[304].displayData.description) = 1;
          memset_0(&context[306], 0, sizeof(FWPM_PROVIDER0));
          v13 = UuidCreate(&context[306].providerKey);
          v7 = v13;
          if ( v13 )
          {
            EventWriteError0(
              0x100000,
              L"Teredo registering with WFP: Teredo failed to generate GUID for the sock opt provider. (%u)",
              v13);
          }
          else
          {
            v14 = *p_providerData;
            context[306].displayData.description = L"Microsoft Windows edge traversal socket option authorization provider";
            context[306].flags = 0;
            context[306].displayData.name = L"Microsoft Corporation";
            v15 = FwpmProviderAdd0(v14, context + 306, 0);
            v7 = v15;
            if ( v15 )
            {
              EventWriteError0(
                0x100000,
                L"Teredo registering with WFP: Teredo failed to plumb its sock opt provider. (%u)",
                v15);
            }
            else
            {
              v16 = *p_providerData;
              v22 = FWPM_SUBLAYER_EDGE_TRAVERSAL_TEREDO_AUTHORIZATION;
              v17 = EtPlumbEtAuthBlockFilter(v16, (__int64)&context[306], v20, (__int64)&context[44].flags);
              v7 = v17;
              if ( v17 )
              {
                EventWriteError0(0x100000, L"Plumbing of teredo auth block filters failed: %u", v17);
              }
              else
              {
                v7 = EtInitializeEnumerationTemplate(v24);
                if ( v7 )
                {
                  EventWriteError0(0x100000, L"Teredo registering with WFP: Unable to initialize filter conditions");
                }
                else
                {
                  v18 = *p_providerData;
                  subscription.enumTemplate = (FWPM_FILTER_ENUM_TEMPLATE0 *)v24;
                  subscription.flags = 3;
                  v25 = FWPM_LAYER_ALE_AUTH_RECV_ACCEPT_V6;
                  v19 = FwpmFilterSubscribeChanges0(
                          v18,
                          &subscription,
                          TeredoClientProcessFilterChangesCallback,
                          context,
                          (HANDLE *)&context[43].providerData.data);
                  v7 = v19;
                  if ( !v19 )
                  {
                    if ( v26 )
                    {
                      FREE(v26);
                      v26 = 0;
                    }
                    LODWORD(context[43].displayData.description) = 3;
                    TeredoCompartmentConfigurationChangeNotification((__int64)context, (unsigned int)dword_1800CA09C);
                    return 0;
                  }
                  EventWriteError0(
                    0x100000,
                    L"Teredo registering with WFP: Unable to subscribe to filter changes. (%u)",
                    v19);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v26 )
  {
    FREE(v26);
    v26 = 0;
  }
  if ( *p_providerData )
  {
    EtDeleteWfpFilters(*p_providerData, v8, &context[44].flags);
    EtRemoveAllFilters(*p_providerData);
    FwpmProviderDeleteByKey0(*p_providerData, &context[305].providerKey);
    FwpmProviderDeleteByKey0(*p_providerData, &context[306].providerKey);
    EtRemoveOthersFilters(&context[304].providerData.data);
    FwpmEngineClose0(*p_providerData);
    *p_providerData = 0;
  }
  LODWORD(context[304].displayData.description) = 0;
  DereferenceCompartmentEx(context, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c", 2162);
  DereferenceServiceEx("TeredoRegisterWithWFP", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c", 2164);
  result = v7;
  LODWORD(context[43].displayData.description) = 0;
  return result;
}

```

## disassembly

```asm
0x1800363b4  mov     [rsp-8+arg_8], rbx
0x1800363b9  mov     [rsp-8+arg_10], rsi
0x1800363be  push    rbp
0x1800363bf  push    rdi
0x1800363c0  push    r12
0x1800363c2  push    r14
0x1800363c4  push    r15
0x1800363c6  lea     rbp, [rsp-37h]
0x1800363cb  sub     rsp, 0E0h
0x1800363d2  mov     rax, cs:__security_cookie
0x1800363d9  xor     rax, rsp
0x1800363dc  mov     [rbp+57h+var_30], rax
0x1800363e0  mov     rbx, rcx
0x1800363e3  mov     edi, 48h ; 'H'
0x1800363e8  mov     r8d, edi; Size
0x1800363eb  lea     rcx, [rbp+57h+var_80]; void *
0x1800363ef  xor     edx, edx; Val
0x1800363f1  call    memset_0
0x1800363f6  cmp     dword ptr [rbx+0AD8h], 3
0x1800363fd  xorps   xmm0, xmm0
0x180036400  movups  xmmword ptr [rbp+57h+subscription.enumTemplate], xmm0
0x180036404  mov     dword ptr [rbp+57h+var_C0], 0
0x18003640b  movups  xmmword ptr [rbp+57h+subscription.sessionKey.Data2], xmm0
0x18003640f  jnz     short loc_180036429
0x180036411  lea     rdx, aTeredoAlreadyR; "Teredo already registered with WFP."
0x180036418  mov     ecx, 100000h
0x18003641d  call    EventWrite0
0x180036422  xor     eax, eax
0x180036424  jmp     loc_18003680F
0x180036429  mov     r8d, cs:g_Reference
0x180036430  lea     r15, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180036437  shr     r8d, 1
0x18003643a  lea     r9, aTeredoregister_0; "TeredoRegisterWithWFP"
0x180036441  and     r8d, 3FFFFFFFh
0x180036448  mov     dword ptr [rsp+100h+var_D8], 785h
0x180036450  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x180036457  mov     [rsp+100h+changeHandle], r15; int
0x18003645c  mov     ecx, 40000h
0x180036461  call    EventWrite0
0x180036466  mov     eax, cs:g_Reference
0x18003646c  test    al, 1
0x18003646e  jnz     loc_18003680A
0x180036474  lea     ecx, [rax+2]
0x180036477  lock cmpxchg cs:g_Reference, ecx
0x18003647f  jnz     short loc_180036466
0x180036481  mov     r8d, 789h
0x180036487  mov     rdx, r15
0x18003648a  mov     rcx, rbx
0x18003648d  call    ReferenceCompartmentEx
0x180036492  mov     r8, rdi; Size
0x180036495  mov     byte ptr [rbx+0AE4h], 0
0x18003649c  xor     edx, edx; Val
0x18003649e  lea     rcx, [rbp+57h+var_80]; void *
0x1800364a2  call    memset_0
0x1800364a7  xorps   xmm0, xmm0
0x1800364aa  lea     r14, [rbx+0AE8h]
0x1800364b1  mov     rdx, r14
0x1800364b4  lea     rcx, aTeredoCallback; "Teredo Callback Session"
0x1800364bb  movups  xmmword ptr [rbp+57h+subscription.enumTemplate], xmm0
0x1800364bf  movups  xmmword ptr [rbp+57h+subscription.sessionKey.Data2], xmm0
0x1800364c3  call    EtStartDynamicFilteringSession
0x1800364c8  mov     edi, eax
0x1800364ca  test    eax, eax
0x1800364cc  jz      short loc_1800364E7
0x1800364ce  mov     r8d, eax
0x1800364d1  lea     rdx, aTeredoRegister_19; "Teredo registering with WFP: Unable to "...
0x1800364d8  mov     ecx, 100000h
0x1800364dd  call    EventWriteError0
0x1800364e2  jmp     loc_180036713
0x1800364e7  lea     rsi, [rbx+4C30h]
0x1800364ee  mov     [rsi+8], rsi
0x1800364f2  lea     r15, [rbx+4C20h]
0x1800364f9  mov     [rsi], rsi
0x1800364fc  mov     [r15+8], r15
0x180036500  mov     [r15], r15
0x180036503  mov     rcx, [r14]; engineHandle
0x180036506  call    EtAddEtAuthorizationSubLayer
0x18003650b  mov     edi, eax
0x18003650d  test    eax, eax
0x18003650f  jz      short loc_18003651D
0x180036511  lea     rdx, aUnableToCreate; "Unable to create new sublayer, error : "...
0x180036518  jmp     loc_1800366FF
0x18003651d  xor     edx, edx; Val
0x18003651f  lea     r12, [rbx+4C40h]
0x180036526  mov     rcx, r12; void *
0x180036529  lea     r8d, [rdx+40h]; Size
0x18003652d  call    memset_0
0x180036532  movups  xmm0, cs:TEREDO_WFP_PROVIDER_GUID
0x180036539  mov     rcx, [r14]; engineHandle
0x18003653c  lea     rax, aMicrosoftWindo; "Microsoft Windows Teredo firewall provi"...
0x180036543  mov     [rbx+4C58h], rax
0x18003654a  xor     r8d, r8d; sd
0x18003654d  lea     rax, aMicrosoftCorpo; "Microsoft Corporation"
0x180036554  mov     dword ptr [rbx+4C60h], 0
0x18003655e  mov     rdx, r12; provider
0x180036561  mov     [rbx+4C50h], rax
0x180036568  movdqu  xmmword ptr [r12], xmm0
0x18003656e  call    cs:__imp_FwpmProviderAdd0
0x180036575  nop     dword ptr [rax+rax+00h]
0x18003657a  mov     edi, eax
0x18003657c  test    eax, eax
0x18003657e  jz      short loc_18003658C
0x180036580  lea     rdx, aTeredoRegister_7; "Teredo registering with WFP: Teredo fai"...
0x180036587  jmp     loc_1800366FF
0x18003658c  mov     rcx, [r14]; engineHandle
0x18003658f  lea     rax, [rbp+57h+var_C0]
0x180036593  mov     [rsp+100h+var_C8], rax; __int64
0x180036598  mov     r9, r12
0x18003659b  mov     [rsp+100h+var_D0], r15; __int64
0x1800365a0  mov     [rsp+100h+var_D8], rsi; int
0x1800365a5  call    EtPlumbAllFiltersIfNeededV6
0x1800365aa  mov     edi, eax
0x1800365ac  test    eax, eax
0x1800365ae  jz      short loc_1800365BC
0x1800365b0  lea     rdx, aTeredoRegister_13; "Teredo registering with WFP: Unable to "...
0x1800365b7  jmp     loc_1800366FF
0x1800365bc  cmp     dword ptr [rbp+57h+var_C0], 1
0x1800365c0  jnz     short loc_1800365CC
0x1800365c2  mov     dword ptr [rbx+4C18h], 1
0x1800365cc  xor     edx, edx; Val
0x1800365ce  lea     rsi, [rbx+4C80h]
0x1800365d5  mov     rcx, rsi; void *
0x1800365d8  lea     r8d, [rdx+40h]; Size
0x1800365dc  call    memset_0
0x1800365e1  mov     rcx, rsi; Uuid
0x1800365e4  call    cs:__imp_UuidCreate
0x1800365eb  nop     dword ptr [rax+rax+00h]
0x1800365f0  mov     edi, eax
0x1800365f2  test    eax, eax
0x1800365f4  jz      short loc_180036602
0x1800365f6  lea     rdx, aTeredoRegister_1; "Teredo registering with WFP: Teredo fai"...
0x1800365fd  jmp     loc_1800366FF
0x180036602  mov     rcx, [r14]; engineHandle
0x180036605  lea     rax, aMicrosoftWindo_0; "Microsoft Windows edge traversal socket"...
0x18003660c  mov     [rbx+4C98h], rax
0x180036613  xor     r8d, r8d; sd
0x180036616  lea     rax, aMicrosoftCorpo; "Microsoft Corporation"
0x18003661d  mov     dword ptr [rbx+4CA0h], 0
0x180036627  mov     rdx, rsi; provider
0x18003662a  mov     [rbx+4C90h], rax
0x180036631  call    cs:__imp_FwpmProviderAdd0
0x180036638  nop     dword ptr [rax+rax+00h]
0x18003663d  mov     edi, eax
0x18003663f  test    eax, eax
0x180036641  jz      short loc_18003664F
0x180036643  lea     rdx, aTeredoRegister; "Teredo registering with WFP: Teredo fai"...
0x18003664a  jmp     loc_1800366FF
0x18003664f  movups  xmm0, cs:FWPM_SUBLAYER_EDGE_TRAVERSAL_TEREDO_AUTHORIZATION
0x180036656  mov     rcx, [r14]; engineHandle
0x180036659  lea     rax, [rbx+0B20h]
0x180036660  mov     [rsp+100h+var_D0], rax; __int64
0x180036665  lea     rdx, [rbp+57h+var_B0]
0x180036669  movdqu  [rbp+57h+var_B0], xmm0
0x18003666e  mov     [rsp+100h+changeHandle], rsi; __int64
0x180036673  call    EtPlumbEtAuthBlockFilter
0x180036678  mov     edi, eax
0x18003667a  test    eax, eax
0x18003667c  jz      short loc_180036687
0x18003667e  lea     rdx, aPlumbingOfTere; "Plumbing of teredo auth block filters f"...
0x180036685  jmp     short loc_1800366FF
0x180036687  lea     rcx, [rbp+57h+var_80]; void *
0x18003668b  call    EtInitializeEnumerationTemplate
0x180036690  mov     edi, eax
0x180036692  test    eax, eax
0x180036694  jz      short loc_1800366A9
0x180036696  lea     rdx, aTeredoRegister_12; "Teredo registering with WFP: Unable to "...
0x18003669d  mov     ecx, 100000h
0x1800366a2  call    EventWriteError0
0x1800366a7  jmp     short loc_18003670C
0x1800366a9  movups  xmm0, xmmword ptr cs:FWPM_LAYER_ALE_AUTH_RECV_ACCEPT_V6.Data1
0x1800366b0  mov     rcx, [r14]; engineHandle
0x1800366b3  lea     rax, [rbp+57h+var_80]
0x1800366b7  mov     [rbp+57h+subscription.enumTemplate], rax
0x1800366bb  lea     r8, TeredoClientProcessFilterChangesCallback; callback
0x1800366c2  lea     rax, [rbx+0AF0h]
0x1800366c9  mov     esi, 3
0x1800366ce  mov     r9, rbx; context
0x1800366d1  mov     [rsp+100h+changeHandle], rax; changeHandle
0x1800366d6  lea     rdx, [rbp+57h+subscription]; subscription
0x1800366da  mov     [rbp+57h+subscription.flags], esi
0x1800366dd  movdqu  [rbp+57h+var_78], xmm0
0x1800366e2  call    cs:__imp_FwpmFilterSubscribeChanges0
0x1800366e9  nop     dword ptr [rax+rax+00h]
0x1800366ee  mov     edi, eax
0x1800366f0  test    eax, eax
0x1800366f2  jz      loc_1800367DB
0x1800366f8  lea     rdx, aTeredoRegister_11; "Teredo registering with WFP: Unable to "...
0x1800366ff  mov     r8d, eax
0x180036702  mov     ecx, 100000h
0x180036707  call    EventWriteError0
0x18003670c  lea     r15, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180036713  mov     rsi, rbx
0x180036716  mov     rcx, [rbp+57h+var_50]
0x18003671a  test    rcx, rcx
0x18003671d  jz      short loc_18003672C
0x18003671f  call    FREE
0x180036724  mov     [rbp+57h+var_50], 0
0x18003672c  mov     rcx, [r14]
0x18003672f  test    rcx, rcx
0x180036732  jz      short loc_18003679D
0x180036734  lea     r8, [rbx+0B20h]
0x18003673b  call    EtDeleteWfpFilters
0x180036740  mov     rcx, [r14]; engineHandle
0x180036743  lea     rdx, [rsi+4C20h]
0x18003674a  call    EtRemoveAllFilters
0x18003674f  mov     rcx, [r14]; engineHandle
0x180036752  lea     rdx, [rbx+4C40h]; key
0x180036759  call    cs:__imp_FwpmProviderDeleteByKey0
0x180036760  nop     dword ptr [rax+rax+00h]
0x180036765  mov     rcx, [r14]; engineHandle
0x180036768  lea     rdx, [rbx+4C80h]; key
0x18003676f  call    cs:__imp_FwpmProviderDeleteByKey0
0x180036776  nop     dword ptr [rax+rax+00h]
0x18003677b  lea     rcx, [rsi+4C30h]
0x180036782  call    EtRemoveOthersFilters
0x180036787  mov     rcx, [r14]; engineHandle
0x18003678a  call    cs:__imp_FwpmEngineClose0
0x180036791  nop     dword ptr [rax+rax+00h]
0x180036796  mov     qword ptr [r14], 0
0x18003679d  mov     r8d, 872h
0x1800367a3  mov     dword ptr [rbx+4C18h], 0
0x1800367ad  mov     rdx, r15
0x1800367b0  mov     rcx, rbx
0x1800367b3  call    DereferenceCompartmentEx
0x1800367b8  mov     r8d, 874h
0x1800367be  lea     rcx, aTeredoregister_0; "TeredoRegisterWithWFP"
0x1800367c5  mov     rdx, r15
0x1800367c8  call    DereferenceServiceEx
0x1800367cd  mov     eax, edi
0x1800367cf  mov     dword ptr [rbx+0AD8h], 0
0x1800367d9  jmp     short loc_18003680F
0x1800367db  mov     rcx, [rbp+57h+var_50]
0x1800367df  test    rcx, rcx
0x1800367e2  jz      short loc_1800367F1
0x1800367e4  call    FREE
0x1800367e9  mov     [rbp+57h+var_50], 0
0x1800367f1  mov     [rbx+0AD8h], esi
0x1800367f7  mov     rcx, rbx
0x1800367fa  mov     edx, cs:dword_1800CA09C
0x180036800  call    TeredoCompartmentConfigurationChangeNotification
0x180036805  jmp     loc_180036422
0x18003680a  mov     eax, 45Bh
0x18003680f  mov     rcx, [rbp+57h+var_30]
0x180036813  xor     rcx, rsp; StackCookie
0x180036816  call    __security_check_cookie
0x18003681b  lea     r11, [rsp+100h+var_20]
0x180036823  mov     rbx, [r11+38h]
0x180036827  mov     rsi, [r11+40h]
0x18003682b  mov     rsp, r11
0x18003682e  pop     r15
0x180036830  pop     r14
0x180036832  pop     r12
0x180036834  pop     rdi
0x180036835  pop     rbp
0x180036836  retn
```
