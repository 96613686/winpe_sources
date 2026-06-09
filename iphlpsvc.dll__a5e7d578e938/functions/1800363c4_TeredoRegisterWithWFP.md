# TeredoRegisterWithWFP

- ea: `0x1800363c4`
- end: `0x180036848`
- name: `TeredoRegisterWithWFP`
- size: `1156`
- prototype: `__int64 __fastcall(void *context)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180013f74`
- `0x18003be80`
- `0x18005f460`

## callees

- `0x180004c64`
- `0x180004f60`
- `0x180005510`
- `0x180006ca0`
- `0x1800076a8`
- `0x1800077e8`
- `0x18000d7c0`
- `0x1800190f0`
- `0x1800363c4`
- `0x180036850`
- `0x1800368e0`
- `0x18003d4b8`
- `0x180040f54`
- `0x180041b4c`
- `0x1800425f8`
- `0x18004b5f0`
- `0x18004c188`
- `0x18005f244`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800365f4`
- `RPCRT4!UuidCreate` at `0x1800365f4`
- `fwpuclnt!FwpmProviderAdd0` at `0x18003657e`
- `fwpuclnt!FwpmProviderAdd0` at `0x180036641`
- `fwpuclnt!FwpmProviderAdd0` at `0x18003657e`
- `fwpuclnt!FwpmProviderAdd0` at `0x180036641`
- `fwpuclnt!FwpmEngineClose0` at `0x18003679a`
- `fwpuclnt!FwpmEngineClose0` at `0x18003679a`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x180036769`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18003677f`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x180036769`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18003677f`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x1800366f2`
- `fwpuclnt!FwpmFilterSubscribeChanges0` at `0x1800366f2`

## string_xrefs

- `0x180036440`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18003671c`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180036460`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180036421`: `Teredo already registered with WFP.`
- `0x1800364e1`: `Teredo registering with WFP: Unable to open filtering engine (%u)`
- `0x180036521`: `Unable to create new sublayer, error : %u`

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
0x1800363c4  mov     [rsp-8+arg_8], rbx
0x1800363c9  mov     [rsp-8+arg_10], rsi
0x1800363ce  push    rbp
0x1800363cf  push    rdi
0x1800363d0  push    r12
0x1800363d2  push    r14
0x1800363d4  push    r15
0x1800363d6  lea     rbp, [rsp-37h]
0x1800363db  sub     rsp, 0E0h
0x1800363e2  mov     rax, cs:__security_cookie
0x1800363e9  xor     rax, rsp
0x1800363ec  mov     [rbp+57h+var_30], rax
0x1800363f0  mov     rbx, rcx
0x1800363f3  mov     edi, 48h ; 'H'
0x1800363f8  mov     r8d, edi; Size
0x1800363fb  lea     rcx, [rbp+57h+var_80]; void *
0x1800363ff  xor     edx, edx; Val
0x180036401  call    memset_0
0x180036406  cmp     dword ptr [rbx+0AD8h], 3
0x18003640d  xorps   xmm0, xmm0
0x180036410  movups  xmmword ptr [rbp+57h+subscription.enumTemplate], xmm0
0x180036414  mov     dword ptr [rbp+57h+var_C0], 0
0x18003641b  movups  xmmword ptr [rbp+57h+subscription.sessionKey.Data2], xmm0
0x18003641f  jnz     short loc_180036439
0x180036421  lea     rdx, aTeredoAlreadyR; "Teredo already registered with WFP."
0x180036428  mov     ecx, 100000h
0x18003642d  call    EventWrite0
0x180036432  xor     eax, eax
0x180036434  jmp     loc_18003681F
0x180036439  mov     r8d, cs:g_Reference
0x180036440  lea     r15, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180036447  shr     r8d, 1
0x18003644a  lea     r9, aTeredoregister_0; "TeredoRegisterWithWFP"
0x180036451  and     r8d, 3FFFFFFFh
0x180036458  mov     dword ptr [rsp+100h+var_D8], 785h
0x180036460  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x180036467  mov     [rsp+100h+changeHandle], r15; int
0x18003646c  mov     ecx, 40000h
0x180036471  call    EventWrite0
0x180036476  mov     eax, cs:g_Reference
0x18003647c  test    al, 1
0x18003647e  jnz     loc_18003681A
0x180036484  lea     ecx, [rax+2]
0x180036487  lock cmpxchg cs:g_Reference, ecx
0x18003648f  jnz     short loc_180036476
0x180036491  mov     r8d, 789h
0x180036497  mov     rdx, r15
0x18003649a  mov     rcx, rbx
0x18003649d  call    ReferenceCompartmentEx
0x1800364a2  mov     r8, rdi; Size
0x1800364a5  mov     byte ptr [rbx+0AE4h], 0
0x1800364ac  xor     edx, edx; Val
0x1800364ae  lea     rcx, [rbp+57h+var_80]; void *
0x1800364b2  call    memset_0
0x1800364b7  xorps   xmm0, xmm0
0x1800364ba  lea     r14, [rbx+0AE8h]
0x1800364c1  mov     rdx, r14
0x1800364c4  lea     rcx, aTeredoCallback; "Teredo Callback Session"
0x1800364cb  movups  xmmword ptr [rbp+57h+subscription.enumTemplate], xmm0
0x1800364cf  movups  xmmword ptr [rbp+57h+subscription.sessionKey.Data2], xmm0
0x1800364d3  call    EtStartDynamicFilteringSession
0x1800364d8  mov     edi, eax
0x1800364da  test    eax, eax
0x1800364dc  jz      short loc_1800364F7
0x1800364de  mov     r8d, eax
0x1800364e1  lea     rdx, aTeredoRegister_19; "Teredo registering with WFP: Unable to "...
0x1800364e8  mov     ecx, 100000h
0x1800364ed  call    EventWriteError0
0x1800364f2  jmp     loc_180036723
0x1800364f7  lea     rsi, [rbx+4C30h]
0x1800364fe  mov     [rsi+8], rsi
0x180036502  lea     r15, [rbx+4C20h]
0x180036509  mov     [rsi], rsi
0x18003650c  mov     [r15+8], r15
0x180036510  mov     [r15], r15
0x180036513  mov     rcx, [r14]; engineHandle
0x180036516  call    EtAddEtAuthorizationSubLayer
0x18003651b  mov     edi, eax
0x18003651d  test    eax, eax
0x18003651f  jz      short loc_18003652D
0x180036521  lea     rdx, aUnableToCreate; "Unable to create new sublayer, error : "...
0x180036528  jmp     loc_18003670F
0x18003652d  xor     edx, edx; Val
0x18003652f  lea     r12, [rbx+4C40h]
0x180036536  mov     rcx, r12; void *
0x180036539  lea     r8d, [rdx+40h]; Size
0x18003653d  call    memset_0
0x180036542  movups  xmm0, cs:TEREDO_WFP_PROVIDER_GUID
0x180036549  mov     rcx, [r14]; engineHandle
0x18003654c  lea     rax, aMicrosoftWindo; "Microsoft Windows Teredo firewall provi"...
0x180036553  mov     [rbx+4C58h], rax
0x18003655a  xor     r8d, r8d; sd
0x18003655d  lea     rax, aMicrosoftCorpo; "Microsoft Corporation"
0x180036564  mov     dword ptr [rbx+4C60h], 0
0x18003656e  mov     rdx, r12; provider
0x180036571  mov     [rbx+4C50h], rax
0x180036578  movdqu  xmmword ptr [r12], xmm0
0x18003657e  call    cs:__imp_FwpmProviderAdd0
0x180036585  nop     dword ptr [rax+rax+00h]
0x18003658a  mov     edi, eax
0x18003658c  test    eax, eax
0x18003658e  jz      short loc_18003659C
0x180036590  lea     rdx, aTeredoRegister_7; "Teredo registering with WFP: Teredo fai"...
0x180036597  jmp     loc_18003670F
0x18003659c  mov     rcx, [r14]; engineHandle
0x18003659f  lea     rax, [rbp+57h+var_C0]
0x1800365a3  mov     [rsp+100h+var_C8], rax; __int64
0x1800365a8  mov     r9, r12
0x1800365ab  mov     [rsp+100h+var_D0], r15; __int64
0x1800365b0  mov     [rsp+100h+var_D8], rsi; int
0x1800365b5  call    EtPlumbAllFiltersIfNeededV6
0x1800365ba  mov     edi, eax
0x1800365bc  test    eax, eax
0x1800365be  jz      short loc_1800365CC
0x1800365c0  lea     rdx, aTeredoRegister_13; "Teredo registering with WFP: Unable to "...
0x1800365c7  jmp     loc_18003670F
0x1800365cc  cmp     dword ptr [rbp+57h+var_C0], 1
0x1800365d0  jnz     short loc_1800365DC
0x1800365d2  mov     dword ptr [rbx+4C18h], 1
0x1800365dc  xor     edx, edx; Val
0x1800365de  lea     rsi, [rbx+4C80h]
0x1800365e5  mov     rcx, rsi; void *
0x1800365e8  lea     r8d, [rdx+40h]; Size
0x1800365ec  call    memset_0
0x1800365f1  mov     rcx, rsi; Uuid
0x1800365f4  call    cs:__imp_UuidCreate
0x1800365fb  nop     dword ptr [rax+rax+00h]
0x180036600  mov     edi, eax
0x180036602  test    eax, eax
0x180036604  jz      short loc_180036612
0x180036606  lea     rdx, aTeredoRegister_1; "Teredo registering with WFP: Teredo fai"...
0x18003660d  jmp     loc_18003670F
0x180036612  mov     rcx, [r14]; engineHandle
0x180036615  lea     rax, aMicrosoftWindo_0; "Microsoft Windows edge traversal socket"...
0x18003661c  mov     [rbx+4C98h], rax
0x180036623  xor     r8d, r8d; sd
0x180036626  lea     rax, aMicrosoftCorpo; "Microsoft Corporation"
0x18003662d  mov     dword ptr [rbx+4CA0h], 0
0x180036637  mov     rdx, rsi; provider
0x18003663a  mov     [rbx+4C90h], rax
0x180036641  call    cs:__imp_FwpmProviderAdd0
0x180036648  nop     dword ptr [rax+rax+00h]
0x18003664d  mov     edi, eax
0x18003664f  test    eax, eax
0x180036651  jz      short loc_18003665F
0x180036653  lea     rdx, aTeredoRegister; "Teredo registering with WFP: Teredo fai"...
0x18003665a  jmp     loc_18003670F
0x18003665f  movups  xmm0, cs:FWPM_SUBLAYER_EDGE_TRAVERSAL_TEREDO_AUTHORIZATION
0x180036666  mov     rcx, [r14]; engineHandle
0x180036669  lea     rax, [rbx+0B20h]
0x180036670  mov     [rsp+100h+var_D0], rax; __int64
0x180036675  lea     rdx, [rbp+57h+var_B0]
0x180036679  movdqu  [rbp+57h+var_B0], xmm0
0x18003667e  mov     [rsp+100h+changeHandle], rsi; __int64
0x180036683  call    EtPlumbEtAuthBlockFilter
0x180036688  mov     edi, eax
0x18003668a  test    eax, eax
0x18003668c  jz      short loc_180036697
0x18003668e  lea     rdx, aPlumbingOfTere; "Plumbing of teredo auth block filters f"...
0x180036695  jmp     short loc_18003670F
0x180036697  lea     rcx, [rbp+57h+var_80]; void *
0x18003669b  call    EtInitializeEnumerationTemplate
0x1800366a0  mov     edi, eax
0x1800366a2  test    eax, eax
0x1800366a4  jz      short loc_1800366B9
0x1800366a6  lea     rdx, aTeredoRegister_12; "Teredo registering with WFP: Unable to "...
0x1800366ad  mov     ecx, 100000h
0x1800366b2  call    EventWriteError0
0x1800366b7  jmp     short loc_18003671C
0x1800366b9  movups  xmm0, xmmword ptr cs:FWPM_LAYER_ALE_AUTH_RECV_ACCEPT_V6.Data1
0x1800366c0  mov     rcx, [r14]; engineHandle
0x1800366c3  lea     rax, [rbp+57h+var_80]
0x1800366c7  mov     [rbp+57h+subscription.enumTemplate], rax
0x1800366cb  lea     r8, TeredoClientProcessFilterChangesCallback; callback
0x1800366d2  lea     rax, [rbx+0AF0h]
0x1800366d9  mov     esi, 3
0x1800366de  mov     r9, rbx; context
0x1800366e1  mov     [rsp+100h+changeHandle], rax; changeHandle
0x1800366e6  lea     rdx, [rbp+57h+subscription]; subscription
0x1800366ea  mov     [rbp+57h+subscription.flags], esi
0x1800366ed  movdqu  [rbp+57h+var_78], xmm0
0x1800366f2  call    cs:__imp_FwpmFilterSubscribeChanges0
0x1800366f9  nop     dword ptr [rax+rax+00h]
0x1800366fe  mov     edi, eax
0x180036700  test    eax, eax
0x180036702  jz      loc_1800367EB
0x180036708  lea     rdx, aTeredoRegister_11; "Teredo registering with WFP: Unable to "...
0x18003670f  mov     r8d, eax
0x180036712  mov     ecx, 100000h
0x180036717  call    EventWriteError0
0x18003671c  lea     r15, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180036723  mov     rsi, rbx
0x180036726  mov     rcx, [rbp+57h+var_50]
0x18003672a  test    rcx, rcx
0x18003672d  jz      short loc_18003673C
0x18003672f  call    FREE
0x180036734  mov     [rbp+57h+var_50], 0
0x18003673c  mov     rcx, [r14]
0x18003673f  test    rcx, rcx
0x180036742  jz      short loc_1800367AD
0x180036744  lea     r8, [rbx+0B20h]
0x18003674b  call    EtDeleteWfpFilters
0x180036750  mov     rcx, [r14]; engineHandle
0x180036753  lea     rdx, [rsi+4C20h]
0x18003675a  call    EtRemoveAllFilters
0x18003675f  mov     rcx, [r14]; engineHandle
0x180036762  lea     rdx, [rbx+4C40h]; key
0x180036769  call    cs:__imp_FwpmProviderDeleteByKey0
0x180036770  nop     dword ptr [rax+rax+00h]
0x180036775  mov     rcx, [r14]; engineHandle
0x180036778  lea     rdx, [rbx+4C80h]; key
0x18003677f  call    cs:__imp_FwpmProviderDeleteByKey0
0x180036786  nop     dword ptr [rax+rax+00h]
0x18003678b  lea     rcx, [rsi+4C30h]
0x180036792  call    EtRemoveOthersFilters
0x180036797  mov     rcx, [r14]; engineHandle
0x18003679a  call    cs:__imp_FwpmEngineClose0
0x1800367a1  nop     dword ptr [rax+rax+00h]
0x1800367a6  mov     qword ptr [r14], 0
0x1800367ad  mov     r8d, 872h
0x1800367b3  mov     dword ptr [rbx+4C18h], 0
0x1800367bd  mov     rdx, r15
0x1800367c0  mov     rcx, rbx
0x1800367c3  call    DereferenceCompartmentEx
0x1800367c8  mov     r8d, 874h
0x1800367ce  lea     rcx, aTeredoregister_0; "TeredoRegisterWithWFP"
0x1800367d5  mov     rdx, r15
0x1800367d8  call    DereferenceServiceEx
0x1800367dd  mov     eax, edi
0x1800367df  mov     dword ptr [rbx+0AD8h], 0
0x1800367e9  jmp     short loc_18003681F
0x1800367eb  mov     rcx, [rbp+57h+var_50]
0x1800367ef  test    rcx, rcx
0x1800367f2  jz      short loc_180036801
0x1800367f4  call    FREE
0x1800367f9  mov     [rbp+57h+var_50], 0
0x180036801  mov     [rbx+0AD8h], esi
0x180036807  mov     rcx, rbx
0x18003680a  mov     edx, cs:dword_1800CA09C
0x180036810  call    TeredoCompartmentConfigurationChangeNotification
0x180036815  jmp     loc_180036432
0x18003681a  mov     eax, 45Bh
0x18003681f  mov     rcx, [rbp+57h+var_30]
0x180036823  xor     rcx, rsp; StackCookie
0x180036826  call    __security_check_cookie
0x18003682b  lea     r11, [rsp+100h+var_20]
0x180036833  mov     rbx, [r11+38h]
0x180036837  mov     rsi, [r11+40h]
0x18003683b  mov     rsp, r11
0x18003683e  pop     r15
0x180036840  pop     r14
0x180036842  pop     r12
0x180036844  pop     rdi
0x180036845  pop     rbp
0x180036846  retn
```
