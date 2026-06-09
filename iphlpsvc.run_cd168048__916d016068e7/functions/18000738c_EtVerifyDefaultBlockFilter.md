# EtVerifyDefaultBlockFilter

- ea: `0x18000738c`
- end: `0x18000768f`
- name: `EtVerifyDefaultBlockFilter`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180006c90`

## callees

- `0x180004c54`
- `0x18000738c`
- `0x180007da0`
- `0x180009000`
- `0x18000d7b0`
- `0x180012dbc`
- `0x1800190e0`
- `0x18003d4a8`
- `0x180040f94`
- `0x180042638`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x1800074a6`
- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x1800074a6`
- `fwpuclnt!FwpmFilterEnum0` at `0x1800074da`
- `fwpuclnt!FwpmFilterEnum0` at `0x1800074da`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800075ea`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800075ea`
- `fwpuclnt!FwpmFreeMemory0` at `0x180007601`
- `fwpuclnt!FwpmFreeMemory0` at `0x180007601`
- `fwpuclnt!FwpmEngineClose0` at `0x18000762c`
- `fwpuclnt!FwpmEngineClose0` at `0x18000762c`

## string_xrefs

- `0x180007454`: `ET verifying default block filter: Unable to open filtering engine. Error(%u)`
- `0x1800074b8`: `ET verifying default block filter: Unable to create filter enumeration handle. (%u)`

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
0x18000738c  mov     [rsp-8+arg_0], rbx
0x180007391  mov     [rsp-8+arg_10], rsi
0x180007396  push    rbp
0x180007397  push    rdi
0x180007398  push    r12
0x18000739a  push    r14
0x18000739c  push    r15
0x18000739e  lea     rbp, [rsp-2Fh]
0x1800073a3  sub     rsp, 0B0h
0x1800073aa  mov     rax, cs:__security_cookie
0x1800073b1  xor     rax, rsp
0x1800073b4  mov     [rbp+4Fh+var_30], rax
0x1800073b8  mov     r14, [rbp+4Fh+arg_20]
0x1800073bc  lea     rcx, [rbp+4Fh+enumTemplate]; void *
0x1800073c0  mov     rdi, rdx
0x1800073c3  mov     [rbp+4Fh+engineHandle], 0
0x1800073cb  mov     ebx, 48h ; 'H'
0x1800073d0  mov     [rbp+4Fh+enumHandle], 0
0x1800073d8  mov     r8d, ebx; Size
0x1800073db  xor     edx, edx; Val
0x1800073dd  mov     r12, r9
0x1800073e0  call    memset_0
0x1800073e5  cmp     cs:IpHlpSvcEtwEnabled, 0
0x1800073ec  mov     [rbp+4Fh+entries], 0
0x1800073f4  mov     [rbp+4Fh+var_A0], 0
0x1800073fb  jz      short loc_180007420
0x1800073fd  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 1
0x180007404  jz      short loc_180007420
0x180007406  lea     r8, aEtVerifyingThe; "ET: Verifying the presence of a default"...
0x18000740d  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED
0x180007414  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18000741b  call    McTemplateU0z_EventWriteTransfer
0x180007420  mov     r8, rbx; Size
0x180007423  mov     dword ptr [r12], 0
0x18000742b  xor     edx, edx; Val
0x18000742d  lea     rcx, [rbp+4Fh+enumTemplate]; void *
0x180007431  call    memset_0
0x180007436  mov     rcx, r14
0x180007439  call    EtRemoveOthersFilters
0x18000743e  lea     rdx, [rbp+4Fh+engineHandle]
0x180007442  lea     rcx, aTeredoSession; "Teredo Session"
0x180007449  call    EtStartDynamicFilteringSession
0x18000744e  mov     ebx, eax
0x180007450  test    eax, eax
0x180007452  jz      short loc_18000746D
0x180007454  lea     rdx, aEtVerifyingDef_2; "ET verifying default block filter: Unab"...
0x18000745b  mov     r8d, eax
0x18000745e  mov     ecx, 100000h
0x180007463  call    EventWriteError0
0x180007468  jmp     loc_1800075DD
0x18000746d  lea     rcx, [rbp+4Fh+enumTemplate]; void *
0x180007471  call    EtInitializeEnumerationTemplate
0x180007476  mov     ebx, eax
0x180007478  test    eax, eax
0x18000747a  jz      short loc_180007492
0x18000747c  lea     rdx, aEtVerifyingDef_4; "ET verifying default block filter: Unab"...
0x180007483  mov     ecx, 100000h
0x180007488  call    EventWriteError0
0x18000748d  jmp     loc_1800075DD
0x180007492  movaps  xmm0, xmmword ptr [rdi]
0x180007495  lea     r8, [rbp+4Fh+enumHandle]; enumHandle
0x180007499  mov     rcx, [rbp+4Fh+engineHandle]; engineHandle
0x18000749d  lea     rdx, [rbp+4Fh+enumTemplate]; enumTemplate
0x1800074a1  movdqu  xmmword ptr [rbp+4Fh+enumTemplate.layerKey.Data1], xmm0
0x1800074a6  call    cs:__imp_FwpmFilterCreateEnumHandle0
0x1800074ad  nop     dword ptr [rax+rax+00h]
0x1800074b2  mov     ebx, eax
0x1800074b4  test    eax, eax
0x1800074b6  jz      short loc_1800074C1
0x1800074b8  lea     rdx, aEtVerifyingDef; "ET verifying default block filter: Unab"...
0x1800074bf  jmp     short loc_18000745B
0x1800074c1  mov     rdx, [rbp+4Fh+enumHandle]; enumHandle
0x1800074c5  lea     rax, [rbp+4Fh+var_A0]
0x1800074c9  mov     rcx, [rbp+4Fh+engineHandle]; engineHandle
0x1800074cd  lea     r9, [rbp+4Fh+entries]; entries
0x1800074d1  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x1800074d5  mov     [rsp+0D0h+numEntriesReturned], rax; numEntriesReturned
0x1800074da  call    cs:__imp_FwpmFilterEnum0
0x1800074e1  nop     dword ptr [rax+rax+00h]
0x1800074e6  mov     ebx, eax
0x1800074e8  test    eax, eax
0x1800074ea  jz      short loc_1800074F8
0x1800074ec  lea     rdx, aEtVerifyingDef_5; "ET verifying default block filter: Unab"...
0x1800074f3  jmp     loc_18000745B
0x1800074f8  mov     esi, [rbp+4Fh+var_A0]
0x1800074fb  test    esi, esi
0x1800074fd  jnz     short loc_180007513
0x1800074ff  lea     rdx, aEtVerifyingDef_1; "ET verifying default block filter: Filt"...
0x180007506  mov     ecx, 100000h
0x18000750b  call    EventWrite0
0x180007510  mov     esi, [rbp+4Fh+var_A0]
0x180007513  xor     edi, edi
0x180007515  cmp     edi, esi
0x180007517  jnb     loc_1800075DD
0x18000751d  mov     rcx, [rbp+4Fh+entries]
0x180007521  mov     r15d, edi
0x180007524  mov     rcx, [rcx+rdi*8]
0x180007528  call    EtVerifyDefaultBlockFilterConditions
0x18000752d  test    eax, eax
0x18000752f  jnz     short loc_180007535
0x180007531  inc     edi
0x180007533  jmp     short loc_180007515
0x180007535  lfence
0x180007538  mov     rax, [rbp+4Fh+entries]
0x18000753c  lea     rdx, aBlockFilterFor; "Block Filter for Tunnel Type %u: Name %"...
0x180007543  mov     ecx, 100000h
0x180007548  mov     r9, [rax+rdi*8]
0x18000754c  mov     edi, 0Eh
0x180007551  mov     r8d, edi
0x180007554  mov     eax, [r9+80h]
0x18000755b  mov     [rsp+0D0h+var_A8], eax
0x18000755f  mov     rax, [r9+0B0h]
0x180007566  mov     r9, [r9+10h]
0x18000756a  mov     [rsp+0D0h+numEntriesReturned], rax
0x18000756f  call    EventWrite0
0x180007574  lea     ecx, [rdi+12h]; dwBytes
0x180007577  call    MALLOC
0x18000757c  mov     rdx, rax
0x18000757f  test    rax, rax
0x180007582  jnz     short loc_180007590
0x180007584  lea     rdx, aEtVerifyingDef_0; "ET verifying default block filter: Unab"...
0x18000758b  jmp     loc_180007483
0x180007590  lfence
0x180007593  mov     rax, [rbp+4Fh+entries]
0x180007597  mov     rcx, [rax+r15*8]
0x18000759b  movups  xmm0, xmmword ptr [rcx]
0x18000759e  movdqu  xmmword ptr [rdx+10h], xmm0
0x1800075a3  mov     rax, [r14+8]
0x1800075a7  cmp     [rax], r14
0x1800075aa  jz      short loc_1800075B3
0x1800075ac  mov     ecx, 3
0x1800075b1  int     29h; Win8: RtlFailFast(ecx)
0x1800075b3  mov     [rdx], r14
0x1800075b6  mov     r8d, edi
0x1800075b9  mov     [rdx+8], rax
0x1800075bd  mov     ecx, 100000h
0x1800075c2  mov     [rax], rdx
0x1800075c5  mov     [r14+8], rdx
0x1800075c9  lea     rdx, aEtVerifyingDef_3; "ET verifying default block filter: Adde"...
0x1800075d0  call    EventWrite0
0x1800075d5  mov     dword ptr [r12], 1
0x1800075dd  mov     rdx, [rbp+4Fh+enumHandle]; enumHandle
0x1800075e1  test    rdx, rdx
0x1800075e4  jz      short loc_1800075F6
0x1800075e6  mov     rcx, [rbp+4Fh+engineHandle]; engineHandle
0x1800075ea  call    cs:__imp_FwpmFilterDestroyEnumHandle0
0x1800075f1  nop     dword ptr [rax+rax+00h]
0x1800075f6  cmp     [rbp+4Fh+entries], 0
0x1800075fb  jz      short loc_18000760D
0x1800075fd  lea     rcx, [rbp+4Fh+entries]; p
0x180007601  call    cs:__imp_FwpmFreeMemory0
0x180007608  nop     dword ptr [rax+rax+00h]
0x18000760d  mov     rcx, [rbp+4Fh+enumTemplate.filterCondition]
0x180007611  test    rcx, rcx
0x180007614  jz      short loc_180007623
0x180007616  call    FREE
0x18000761b  mov     [rbp+4Fh+enumTemplate.filterCondition], 0
0x180007623  mov     rcx, [rbp+4Fh+engineHandle]; engineHandle
0x180007627  test    rcx, rcx
0x18000762a  jz      short loc_180007638
0x18000762c  call    cs:__imp_FwpmEngineClose0
0x180007633  nop     dword ptr [rax+rax+00h]
0x180007638  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18000763f  jz      short loc_180007664
0x180007641  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 2
0x180007648  jz      short loc_180007664
0x18000764a  lea     r8, aEtFinishedVeri; "ET: Finished verifying the presence of "...
0x180007651  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED
0x180007658  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18000765f  call    McTemplateU0z_EventWriteTransfer
0x180007664  mov     eax, ebx
0x180007666  mov     rcx, [rbp+4Fh+var_30]
0x18000766a  xor     rcx, rsp; StackCookie
0x18000766d  call    __security_check_cookie
0x180007672  lea     r11, [rsp+0D0h+var_20]
0x18000767a  mov     rbx, [r11+30h]
0x18000767e  mov     rsi, [r11+40h]
0x180007682  mov     rsp, r11
0x180007685  pop     r15
0x180007687  pop     r14
0x180007689  pop     r12
0x18000768b  pop     rdi
0x18000768c  pop     rbp
0x18000768d  retn
```
