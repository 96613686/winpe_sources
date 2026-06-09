# EtVerifyDefaultBlockFilter

- ea: `0x18000739c`
- end: `0x18000769f`
- name: `EtVerifyDefaultBlockFilter`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180006ca0`

## callees

- `0x180004c64`
- `0x18000739c`
- `0x180007db0`
- `0x180009010`
- `0x18000d7c0`
- `0x180012dcc`
- `0x1800190f0`
- `0x18003d4b8`
- `0x180040f54`
- `0x1800425f8`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x1800074b6`
- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x1800074b6`
- `fwpuclnt!FwpmFilterEnum0` at `0x1800074ea`
- `fwpuclnt!FwpmFilterEnum0` at `0x1800074ea`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800075fa`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800075fa`
- `fwpuclnt!FwpmFreeMemory0` at `0x180007611`
- `fwpuclnt!FwpmFreeMemory0` at `0x180007611`
- `fwpuclnt!FwpmEngineClose0` at `0x18000763c`
- `fwpuclnt!FwpmEngineClose0` at `0x18000763c`

## string_xrefs

- `0x180007464`: `ET verifying default block filter: Unable to open filtering engine. Error(%u)`
- `0x1800074c8`: `ET verifying default block filter: Unable to create filter enumeration handle. (%u)`

## pseudocode

```c
__int64 __fastcall EtVerifyDefaultBlockFilter(__int64 a1, GUID *a2, __int64 a3, _DWORD *a4, __int64 a5)
{
  DWORD started; // eax
  DWORD v8; // ebx
  DWORD v9; // eax
  DWORD v10; // eax
  UINT32 v11; // esi
  __int64 i; // rdi
  GUID *v13; // rax
  GUID *v14; // rdx
  GUID **v15; // rax
  UINT32 numEntriesReturned; // [rsp+30h] [rbp-51h] BYREF
  FWPM_FILTER0 **entries; // [rsp+38h] [rbp-49h] BYREF
  HANDLE engineHandle; // [rsp+40h] [rbp-41h] BYREF
  HANDLE enumHandle; // [rsp+48h] [rbp-39h] BYREF
  FWPM_FILTER_ENUM_TEMPLATE0 enumTemplate; // [rsp+50h] [rbp-31h] BYREF

  engineHandle = 0;
  enumHandle = 0;
  memset_0(&enumTemplate, 0, sizeof(enumTemplate));
  entries = 0;
  numEntriesReturned = 0;
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x100) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED,
      L"ET: Verifying the presence of a default block filter");
  *a4 = 0;
  memset_0(&enumTemplate, 0, sizeof(enumTemplate));
  EtRemoveOthersFilters(a5);
  started = EtStartDynamicFilteringSession(L"Teredo Session", &engineHandle);
  v8 = started;
  if ( started )
  {
    EventWriteError0(
      0x100000,
      L"ET verifying default block filter: Unable to open filtering engine. Error(%u)",
      started);
  }
  else
  {
    v8 = EtInitializeEnumerationTemplate(&enumTemplate);
    if ( v8 )
    {
      EventWriteError0(0x100000, L"ET verifying default block filter: Unable to initialize filter conditions");
    }
    else
    {
      enumTemplate.layerKey = *a2;
      v9 = FwpmFilterCreateEnumHandle0(engineHandle, &enumTemplate, &enumHandle);
      v8 = v9;
      if ( v9 )
      {
        EventWriteError0(
          0x100000,
          L"ET verifying default block filter: Unable to create filter enumeration handle. (%u)",
          v9);
      }
      else
      {
        v10 = FwpmFilterEnum0(engineHandle, enumHandle, 0xFFFFFFFF, &entries, &numEntriesReturned);
        v8 = v10;
        if ( v10 )
        {
          EventWriteError0(0x100000, L"ET verifying default block filter: Unable to enumerate filters. (%u)", v10);
        }
        else
        {
          v11 = numEntriesReturned;
          if ( !numEntriesReturned )
          {
            EventWrite0(0x100000, L"ET verifying default block filter: Filter count is 0");
            v11 = numEntriesReturned;
          }
          for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)EtVerifyDefaultBlockFilterConditions(entries[i]) )
            {
              _mm_lfence();
              EventWrite0(
                0x100000,
                L"Block Filter for Tunnel Type %u: Name %ls FilterId %I64u Action %d",
                14,
                entries[i]->displayData.name,
                entries[i]->filterId,
                entries[i]->action.type);
              v13 = (GUID *)MALLOC(0x20u);
              v14 = v13;
              if ( v13 )
              {
                _mm_lfence();
                v13[1] = entries[(unsigned int)i]->filterKey;
                v15 = *(GUID ***)(a5 + 8);
                if ( *v15 != (GUID *)a5 )
                  __fastfail(3u);
                *(_QWORD *)&v14->Data1 = a5;
                *(_QWORD *)v14->Data4 = v15;
                *v15 = v14;
                *(_QWORD *)(a5 + 8) = v14;
                EventWrite0(
                  0x100000,
                  L"ET verifying default block filter: Added a default block filter to the list for TunnelType %u.",
                  14);
                *a4 = 1;
              }
              else
              {
                EventWriteError0(
                  0x100000,
                  L"ET verifying default block filter: Unable to alloc space for filter entry.");
              }
              break;
            }
          }
        }
      }
    }
  }
  if ( enumHandle )
    FwpmFilterDestroyEnumHandle0(engineHandle, enumHandle);
  if ( entries )
    FwpmFreeMemory0((void **)&entries);
  if ( enumTemplate.filterCondition )
  {
    FREE(enumTemplate.filterCondition);
    enumTemplate.filterCondition = 0;
  }
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x200) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED,
      L"ET: Finished verifying the presence of a default block filter");
  return v8;
}

```

## disassembly

```asm
0x18000739c  mov     [rsp-8+arg_0], rbx
0x1800073a1  mov     [rsp-8+arg_10], rsi
0x1800073a6  push    rbp
0x1800073a7  push    rdi
0x1800073a8  push    r12
0x1800073aa  push    r14
0x1800073ac  push    r15
0x1800073ae  lea     rbp, [rsp-2Fh]
0x1800073b3  sub     rsp, 0B0h
0x1800073ba  mov     rax, cs:__security_cookie
0x1800073c1  xor     rax, rsp
0x1800073c4  mov     [rbp+4Fh+var_30], rax
0x1800073c8  mov     r14, [rbp+4Fh+arg_20]
0x1800073cc  lea     rcx, [rbp+4Fh+enumTemplate]; void *
0x1800073d0  mov     rdi, rdx
0x1800073d3  mov     [rbp+4Fh+engineHandle], 0
0x1800073db  mov     ebx, 48h ; 'H'
0x1800073e0  mov     [rbp+4Fh+enumHandle], 0
0x1800073e8  mov     r8d, ebx; Size
0x1800073eb  xor     edx, edx; Val
0x1800073ed  mov     r12, r9
0x1800073f0  call    memset_0
0x1800073f5  cmp     cs:IpHlpSvcEtwEnabled, 0
0x1800073fc  mov     [rbp+4Fh+entries], 0
0x180007404  mov     [rbp+4Fh+var_A0], 0
0x18000740b  jz      short loc_180007430
0x18000740d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 1
0x180007414  jz      short loc_180007430
0x180007416  lea     r8, aEtVerifyingThe; "ET: Verifying the presence of a default"...
0x18000741d  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED
0x180007424  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18000742b  call    McTemplateU0z_EventWriteTransfer
0x180007430  mov     r8, rbx; Size
0x180007433  mov     dword ptr [r12], 0
0x18000743b  xor     edx, edx; Val
0x18000743d  lea     rcx, [rbp+4Fh+enumTemplate]; void *
0x180007441  call    memset_0
0x180007446  mov     rcx, r14
0x180007449  call    EtRemoveOthersFilters
0x18000744e  lea     rdx, [rbp+4Fh+engineHandle]
0x180007452  lea     rcx, aTeredoSession; "Teredo Session"
0x180007459  call    EtStartDynamicFilteringSession
0x18000745e  mov     ebx, eax
0x180007460  test    eax, eax
0x180007462  jz      short loc_18000747D
0x180007464  lea     rdx, aEtVerifyingDef_2; "ET verifying default block filter: Unab"...
0x18000746b  mov     r8d, eax
0x18000746e  mov     ecx, 100000h
0x180007473  call    EventWriteError0
0x180007478  jmp     loc_1800075ED
0x18000747d  lea     rcx, [rbp+4Fh+enumTemplate]; void *
0x180007481  call    EtInitializeEnumerationTemplate
0x180007486  mov     ebx, eax
0x180007488  test    eax, eax
0x18000748a  jz      short loc_1800074A2
0x18000748c  lea     rdx, aEtVerifyingDef_4; "ET verifying default block filter: Unab"...
0x180007493  mov     ecx, 100000h
0x180007498  call    EventWriteError0
0x18000749d  jmp     loc_1800075ED
0x1800074a2  movaps  xmm0, xmmword ptr [rdi]
0x1800074a5  lea     r8, [rbp+4Fh+enumHandle]; enumHandle
0x1800074a9  mov     rcx, [rbp+4Fh+engineHandle]; engineHandle
0x1800074ad  lea     rdx, [rbp+4Fh+enumTemplate]; enumTemplate
0x1800074b1  movdqu  xmmword ptr [rbp+4Fh+enumTemplate.layerKey.Data1], xmm0
0x1800074b6  call    cs:__imp_FwpmFilterCreateEnumHandle0
0x1800074bd  nop     dword ptr [rax+rax+00h]
0x1800074c2  mov     ebx, eax
0x1800074c4  test    eax, eax
0x1800074c6  jz      short loc_1800074D1
0x1800074c8  lea     rdx, aEtVerifyingDef; "ET verifying default block filter: Unab"...
0x1800074cf  jmp     short loc_18000746B
0x1800074d1  mov     rdx, [rbp+4Fh+enumHandle]; enumHandle
0x1800074d5  lea     rax, [rbp+4Fh+var_A0]
0x1800074d9  mov     rcx, [rbp+4Fh+engineHandle]; engineHandle
0x1800074dd  lea     r9, [rbp+4Fh+entries]; entries
0x1800074e1  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x1800074e5  mov     [rsp+0D0h+numEntriesReturned], rax; numEntriesReturned
0x1800074ea  call    cs:__imp_FwpmFilterEnum0
0x1800074f1  nop     dword ptr [rax+rax+00h]
0x1800074f6  mov     ebx, eax
0x1800074f8  test    eax, eax
0x1800074fa  jz      short loc_180007508
0x1800074fc  lea     rdx, aEtVerifyingDef_5; "ET verifying default block filter: Unab"...
0x180007503  jmp     loc_18000746B
0x180007508  mov     esi, [rbp+4Fh+var_A0]
0x18000750b  test    esi, esi
0x18000750d  jnz     short loc_180007523
0x18000750f  lea     rdx, aEtVerifyingDef_1; "ET verifying default block filter: Filt"...
0x180007516  mov     ecx, 100000h
0x18000751b  call    EventWrite0
0x180007520  mov     esi, [rbp+4Fh+var_A0]
0x180007523  xor     edi, edi
0x180007525  cmp     edi, esi
0x180007527  jnb     loc_1800075ED
0x18000752d  mov     rcx, [rbp+4Fh+entries]
0x180007531  mov     r15d, edi
0x180007534  mov     rcx, [rcx+rdi*8]
0x180007538  call    EtVerifyDefaultBlockFilterConditions
0x18000753d  test    eax, eax
0x18000753f  jnz     short loc_180007545
0x180007541  inc     edi
0x180007543  jmp     short loc_180007525
0x180007545  lfence
0x180007548  mov     rax, [rbp+4Fh+entries]
0x18000754c  lea     rdx, aBlockFilterFor; "Block Filter for Tunnel Type %u: Name %"...
0x180007553  mov     ecx, 100000h
0x180007558  mov     r9, [rax+rdi*8]
0x18000755c  mov     edi, 0Eh
0x180007561  mov     r8d, edi
0x180007564  mov     eax, [r9+80h]
0x18000756b  mov     [rsp+0D0h+var_A8], eax
0x18000756f  mov     rax, [r9+0B0h]
0x180007576  mov     r9, [r9+10h]
0x18000757a  mov     [rsp+0D0h+numEntriesReturned], rax
0x18000757f  call    EventWrite0
0x180007584  lea     ecx, [rdi+12h]; dwBytes
0x180007587  call    MALLOC
0x18000758c  mov     rdx, rax
0x18000758f  test    rax, rax
0x180007592  jnz     short loc_1800075A0
0x180007594  lea     rdx, aEtVerifyingDef_0; "ET verifying default block filter: Unab"...
0x18000759b  jmp     loc_180007493
0x1800075a0  lfence
0x1800075a3  mov     rax, [rbp+4Fh+entries]
0x1800075a7  mov     rcx, [rax+r15*8]
0x1800075ab  movups  xmm0, xmmword ptr [rcx]
0x1800075ae  movdqu  xmmword ptr [rdx+10h], xmm0
0x1800075b3  mov     rax, [r14+8]
0x1800075b7  cmp     [rax], r14
0x1800075ba  jz      short loc_1800075C3
0x1800075bc  mov     ecx, 3
0x1800075c1  int     29h; Win8: RtlFailFast(ecx)
0x1800075c3  mov     [rdx], r14
0x1800075c6  mov     r8d, edi
0x1800075c9  mov     [rdx+8], rax
0x1800075cd  mov     ecx, 100000h
0x1800075d2  mov     [rax], rdx
0x1800075d5  mov     [r14+8], rdx
0x1800075d9  lea     rdx, aEtVerifyingDef_3; "ET verifying default block filter: Adde"...
0x1800075e0  call    EventWrite0
0x1800075e5  mov     dword ptr [r12], 1
0x1800075ed  mov     rdx, [rbp+4Fh+enumHandle]; enumHandle
0x1800075f1  test    rdx, rdx
0x1800075f4  jz      short loc_180007606
0x1800075f6  mov     rcx, [rbp+4Fh+engineHandle]; engineHandle
0x1800075fa  call    cs:__imp_FwpmFilterDestroyEnumHandle0
0x180007601  nop     dword ptr [rax+rax+00h]
0x180007606  cmp     [rbp+4Fh+entries], 0
0x18000760b  jz      short loc_18000761D
0x18000760d  lea     rcx, [rbp+4Fh+entries]; p
0x180007611  call    cs:__imp_FwpmFreeMemory0
0x180007618  nop     dword ptr [rax+rax+00h]
0x18000761d  mov     rcx, [rbp+4Fh+enumTemplate.filterCondition]
0x180007621  test    rcx, rcx
0x180007624  jz      short loc_180007633
0x180007626  call    FREE
0x18000762b  mov     [rbp+4Fh+enumTemplate.filterCondition], 0
0x180007633  mov     rcx, [rbp+4Fh+engineHandle]; engineHandle
0x180007637  test    rcx, rcx
0x18000763a  jz      short loc_180007648
0x18000763c  call    cs:__imp_FwpmEngineClose0
0x180007643  nop     dword ptr [rax+rax+00h]
0x180007648  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18000764f  jz      short loc_180007674
0x180007651  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 2
0x180007658  jz      short loc_180007674
0x18000765a  lea     r8, aEtFinishedVeri; "ET: Finished verifying the presence of "...
0x180007661  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED
0x180007668  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18000766f  call    McTemplateU0z_EventWriteTransfer
0x180007674  mov     eax, ebx
0x180007676  mov     rcx, [rbp+4Fh+var_30]
0x18000767a  xor     rcx, rsp; StackCookie
0x18000767d  call    __security_check_cookie
0x180007682  lea     r11, [rsp+0D0h+var_20]
0x18000768a  mov     rbx, [r11+30h]
0x18000768e  mov     rsi, [r11+40h]
0x180007692  mov     rsp, r11
0x180007695  pop     r15
0x180007697  pop     r14
0x180007699  pop     r12
0x18000769b  pop     rdi
0x18000769c  pop     rbp
0x18000769d  retn
```
