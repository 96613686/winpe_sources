# NcaEvCollProbeStart(ulong,NCA_EVCOLL_PROBE_ORIGIN_,NCA_EVCOLL_USER_PROBES_ *,NCA_EVCOLL_PROBE_ *)

- ea: `0x180011744`
- end: `0x180011bba`
- name: `?NcaEvCollProbeStart@@YAKKW4NCA_EVCOLL_PROBE_ORIGIN_@@PEAUNCA_EVCOLL_USER_PROBES_@@PEAUNCA_EVCOLL_PROBE_@@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(unsigned int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180011d54`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x1800050d8`
- `0x18000b1e8`
- `0x18000b51c`
- `0x18000db28`
- `0x18000e984`
- `0x18000eec0`
- `0x1800112ac`
- `0x1800115a4`
- `0x180011744`
- `0x180016678`
- `0x180018ffc`
- `0x180019784`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800119b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800119b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011883`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800118a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011883`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800118a1`

## pseudocode

```c
__int64 __fastcall NcaEvCollProbeStart(unsigned int a1, int a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // eax
  unsigned int ProbeObjectCopy; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // eax
  HANDLE EventW; // rax
  unsigned int v17; // eax
  _QWORD *v18; // rsi
  int v19; // edx
  int v20; // r9d
  _QWORD v22[3]; // [rsp+30h] [rbp-58h] BYREF
  int v23; // [rsp+48h] [rbp-40h]
  int v24; // [rsp+4Ch] [rbp-3Ch]

  v24 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids);
  v8 = NcaCriticalSectionCreate((LPCRITICAL_SECTION)(a4 + 232));
  ProbeObjectCopy = NcaHResultToWindowsError(v8);
  v10 = ProbeObjectCopy;
  if ( ProbeObjectCopy )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 30;
LABEL_8:
      v13 = ProbeObjectCopy;
LABEL_9:
      WPP_SF_d(v11[2], v12, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, v13);
LABEL_56:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_57;
    }
    goto LABEL_57;
  }
  v14 = NcaCriticalSectionCreate((LPCRITICAL_SECTION)(a4 + 280));
  ProbeObjectCopy = NcaHResultToWindowsError(v14);
  v10 = ProbeObjectCopy;
  if ( !ProbeObjectCopy )
  {
    v15 = NcaCriticalSectionCreate((LPCRITICAL_SECTION)(a4 + 328));
    ProbeObjectCopy = NcaHResultToWindowsError(v15);
    v10 = ProbeObjectCopy;
    if ( ProbeObjectCopy )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 32;
        goto LABEL_8;
      }
      goto LABEL_57;
    }
    *(_QWORD *)(a4 + 376) = CreateEventW(0, 1, 1, 0);
    EventW = CreateEventW(0, 1, 1, 0);
    *(_QWORD *)(a4 + 216) = 0;
    *(_QWORD *)(a4 + 384) = EventW;
    *(_DWORD *)(a4 + 24) = a2;
    *(_QWORD *)(a4 + 32) = a3;
    *(_DWORD *)(a4 + 224) = 0;
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        ProbeObjectCopy = NcaConfigMgrGetProbeObjectCopy(
                            a1,
                            (struct NCA_PROBE_LIST_ *)&xmmword_180028BD8,
                            (struct NCA_PROBE_ *)a4);
        v10 = ProbeObjectCopy;
        if ( ProbeObjectCopy )
        {
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 34;
            goto LABEL_8;
          }
          goto LABEL_57;
        }
      }
    }
    else
    {
      ProbeObjectCopy = NcaConfigMgrGetProbeObjectCopy(
                          a1,
                          (struct NCA_PROBE_LIST_ *)&xmmword_180028BC8,
                          (struct NCA_PROBE_ *)a4);
      v10 = ProbeObjectCopy;
      if ( ProbeObjectCopy )
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 33;
          goto LABEL_8;
        }
        goto LABEL_57;
      }
    }
    if ( *(_DWORD *)a4 == 2 )
    {
      v17 = NcaEvCollPingProbeSessionInit((struct NCA_EVCOLL_PROBE_ *)a4);
    }
    else
    {
      if ( *(_DWORD *)a4 != 3 )
      {
LABEL_36:
        EnterCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
        v18 = (_QWORD *)(a4 + 176);
        *(_DWORD *)(a4 + 216) = 1;
        ProbeObjectCopy = NcaTriggerRegisterWait((PTP_WAIT_CALLBACK)NcaEvCollProbeCollect, (PVOID)a4);
        v10 = ProbeObjectCopy;
        if ( ProbeObjectCopy )
        {
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 36;
            goto LABEL_8;
          }
        }
        else
        {
          ProbeObjectCopy = NcaSrcLnkdTriggerRegisterWait(1, &stru_180028D30, *v18, 0, a4, a4 + 184);
          v10 = ProbeObjectCopy;
          if ( ProbeObjectCopy )
          {
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v12 = 37;
              goto LABEL_8;
            }
          }
          else
          {
            ProbeObjectCopy = NcaIPTriggerRegisterWait(*v18, 0, a4, a4 + 192);
            v10 = ProbeObjectCopy;
            if ( ProbeObjectCopy )
            {
              v11 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v12 = 38;
                goto LABEL_8;
              }
            }
            else
            {
              v22[0] = *v18;
              v22[1] = 0;
              v22[2] = a4;
              v23 = 2;
              ProbeObjectCopy = NcaWtsSessionChangeTriggerRegisterWait(v22, a4 + 200);
              v10 = ProbeObjectCopy;
              if ( ProbeObjectCopy )
              {
                v11 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v12 = 39;
                  goto LABEL_8;
                }
              }
              else
              {
                ProbeObjectCopy = NcaTimerTriggerRegisterWait(*v18, v19, a4, v20, a4 + 208);
                v10 = ProbeObjectCopy;
                if ( !ProbeObjectCopy )
                  goto LABEL_56;
                v11 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v12 = 40;
                  goto LABEL_8;
                }
              }
            }
          }
        }
        goto LABEL_57;
      }
      v17 = NcaEvCollHttpProbeSessionInit((struct NCA_EVCOLL_PROBE_ *)a4);
    }
    v10 = v17;
    if ( v17 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 35;
        v13 = v17;
        goto LABEL_9;
      }
      goto LABEL_57;
    }
    goto LABEL_36;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 31;
    goto LABEL_8;
  }
LABEL_57:
  if ( !*(_DWORD *)a4 )
  {
    v10 = 0;
    NcaDAPEvidenceSnapshotSetGlobalState(21, 0);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(a4 + 216) == 1 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
    WPP_SF_(v11[2], 42, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids);
  return v10;
}

```

## disassembly

```asm
0x180011744  push    rbx
0x180011746  push    rbp
0x180011747  push    rsi
0x180011748  push    rdi
0x180011749  push    r12
0x18001174b  push    r14
0x18001174d  push    r15
0x18001174f  sub     rsp, 50h
0x180011753  mov     rdi, r9
0x180011756  mov     [rsp+88h+var_3C], 0
0x18001175e  mov     r14, r8
0x180011761  mov     esi, edx
0x180011763  mov     ebp, ecx
0x180011765  mov     rcx, cs:WPP_GLOBAL_Control
0x18001176c  lea     rax, WPP_GLOBAL_Control
0x180011773  cmp     rcx, rax
0x180011776  jz      short loc_180011793
0x180011778  test    byte ptr [rcx+1Ch], 8
0x18001177c  jz      short loc_180011793
0x18001177e  mov     rcx, [rcx+10h]
0x180011782  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180011789  mov     edx, 1Dh
0x18001178e  call    WPP_SF_
0x180011793  lea     r15, [rdi+0E8h]
0x18001179a  mov     rcx, r15; lpCriticalSection
0x18001179d  call    NcaCriticalSectionCreate
0x1800117a2  mov     ecx, eax
0x1800117a4  call    NcaHResultToWindowsError
0x1800117a9  mov     ebx, eax
0x1800117ab  mov     r12d, 1
0x1800117b1  test    eax, eax
0x1800117b3  jz      short loc_1800117F3
0x1800117b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117bc  lea     rsi, WPP_GLOBAL_Control
0x1800117c3  cmp     rcx, rsi
0x1800117c6  jz      loc_180011B51
0x1800117cc  test    [rcx+1Ch], r12b
0x1800117d0  jz      loc_180011B51
0x1800117d6  lea     edx, [r12+1Dh]
0x1800117db  mov     r9d, eax
0x1800117de  mov     rcx, [rcx+10h]
0x1800117e2  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x1800117e9  call    WPP_SF_d
0x1800117ee  jmp     loc_180011B4A
0x1800117f3  lea     rcx, [rdi+118h]; lpCriticalSection
0x1800117fa  call    NcaCriticalSectionCreate
0x1800117ff  mov     ecx, eax
0x180011801  call    NcaHResultToWindowsError
0x180011806  mov     ebx, eax
0x180011808  test    eax, eax
0x18001180a  jz      short loc_180011834
0x18001180c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011813  lea     rsi, WPP_GLOBAL_Control
0x18001181a  cmp     rcx, rsi
0x18001181d  jz      loc_180011B51
0x180011823  test    [rcx+1Ch], r12b
0x180011827  jz      loc_180011B51
0x18001182d  mov     edx, 1Fh
0x180011832  jmp     short loc_1800117DB
0x180011834  lea     rcx, [rdi+148h]; lpCriticalSection
0x18001183b  call    NcaCriticalSectionCreate
0x180011840  mov     ecx, eax
0x180011842  call    NcaHResultToWindowsError
0x180011847  mov     ebx, eax
0x180011849  test    eax, eax
0x18001184b  jz      short loc_180011878
0x18001184d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011854  lea     rsi, WPP_GLOBAL_Control
0x18001185b  cmp     rcx, rsi
0x18001185e  jz      loc_180011B51
0x180011864  test    [rcx+1Ch], r12b
0x180011868  jz      loc_180011B51
0x18001186e  mov     edx, 20h ; ' '
0x180011873  jmp     loc_1800117DB
0x180011878  xor     r9d, r9d; lpName
0x18001187b  mov     r8d, r12d; bInitialState
0x18001187e  mov     edx, r12d; bManualReset
0x180011881  xor     ecx, ecx; lpEventAttributes
0x180011883  call    cs:__imp_CreateEventW
0x18001188a  nop     dword ptr [rax+rax+00h]
0x18001188f  xor     r9d, r9d; lpName
0x180011892  mov     r8d, r12d; bInitialState
0x180011895  mov     edx, r12d; bManualReset
0x180011898  mov     [rdi+178h], rax
0x18001189f  xor     ecx, ecx; lpEventAttributes
0x1800118a1  call    cs:__imp_CreateEventW
0x1800118a8  nop     dword ptr [rax+rax+00h]
0x1800118ad  mov     qword ptr [rdi+0D8h], 0
0x1800118b8  mov     [rdi+180h], rax
0x1800118bf  mov     [rdi+18h], esi
0x1800118c2  mov     [rdi+20h], r14
0x1800118c6  mov     dword ptr [rdi+0E0h], 0
0x1800118d0  test    esi, esi
0x1800118d2  jnz     short loc_180011916
0x1800118d4  mov     r8, rdi; struct NCA_PROBE_ *
0x1800118d7  lea     rdx, xmmword_180028BC8; struct NCA_PROBE_LIST_ *
0x1800118de  mov     ecx, ebp; unsigned int
0x1800118e0  call    ?NcaConfigMgrGetProbeObjectCopy@@YAKKPEAUNCA_PROBE_LIST_@@PEAUNCA_PROBE_@@@Z; NcaConfigMgrGetProbeObjectCopy(ulong,NCA_PROBE_LIST_ *,NCA_PROBE_ *)
0x1800118e5  mov     ebx, eax
0x1800118e7  test    eax, eax
0x1800118e9  jz      short loc_18001195D
0x1800118eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118f2  lea     rsi, WPP_GLOBAL_Control
0x1800118f9  cmp     rcx, rsi
0x1800118fc  jz      loc_180011B51
0x180011902  test    [rcx+1Ch], r12b
0x180011906  jz      loc_180011B51
0x18001190c  mov     edx, 21h ; '!'
0x180011911  jmp     loc_1800117DB
0x180011916  cmp     esi, r12d
0x180011919  jnz     short loc_18001195D
0x18001191b  mov     r8, rdi; struct NCA_PROBE_ *
0x18001191e  lea     rdx, xmmword_180028BD8; struct NCA_PROBE_LIST_ *
0x180011925  mov     ecx, ebp; unsigned int
0x180011927  call    ?NcaConfigMgrGetProbeObjectCopy@@YAKKPEAUNCA_PROBE_LIST_@@PEAUNCA_PROBE_@@@Z; NcaConfigMgrGetProbeObjectCopy(ulong,NCA_PROBE_LIST_ *,NCA_PROBE_ *)
0x18001192c  mov     ebx, eax
0x18001192e  test    eax, eax
0x180011930  jz      short loc_18001195D
0x180011932  mov     rcx, cs:WPP_GLOBAL_Control
0x180011939  lea     rsi, WPP_GLOBAL_Control
0x180011940  cmp     rcx, rsi
0x180011943  jz      loc_180011B51
0x180011949  test    [rcx+1Ch], r12b
0x18001194d  jz      loc_180011B51
0x180011953  mov     edx, 22h ; '"'
0x180011958  jmp     loc_1800117DB
0x18001195d  mov     ecx, [rdi]
0x18001195f  sub     ecx, 2
0x180011962  jz      short loc_180011973
0x180011964  cmp     ecx, r12d
0x180011967  jnz     short loc_1800119AF
0x180011969  mov     rcx, rdi; struct NCA_EVCOLL_PROBE_ *
0x18001196c  call    ?NcaEvCollHttpProbeSessionInit@@YAKPEAUNCA_EVCOLL_PROBE_@@@Z; NcaEvCollHttpProbeSessionInit(NCA_EVCOLL_PROBE_ *)
0x180011971  jmp     short loc_18001197B
0x180011973  mov     rcx, rdi; struct NCA_EVCOLL_PROBE_ *
0x180011976  call    ?NcaEvCollPingProbeSessionInit@@YAKPEAUNCA_EVCOLL_PROBE_@@@Z; NcaEvCollPingProbeSessionInit(NCA_EVCOLL_PROBE_ *)
0x18001197b  mov     ebx, eax
0x18001197d  test    eax, eax
0x18001197f  jz      short loc_1800119AF
0x180011981  mov     rcx, cs:WPP_GLOBAL_Control
0x180011988  lea     rsi, WPP_GLOBAL_Control
0x18001198f  cmp     rcx, rsi
0x180011992  jz      loc_180011B51
0x180011998  test    [rcx+1Ch], r12b
0x18001199c  jz      loc_180011B51
0x1800119a2  mov     edx, 23h ; '#'
0x1800119a7  mov     r9d, eax
0x1800119aa  jmp     loc_1800117DE
0x1800119af  mov     rcx, r15; lpCriticalSection
0x1800119b2  call    cs:__imp_EnterCriticalSection
0x1800119b9  nop     dword ptr [rax+rax+00h]
0x1800119be  lea     rsi, [rdi+0B0h]
0x1800119c5  mov     [rdi+0D8h], r12d
0x1800119cc  mov     r8, rsi
0x1800119cf  lea     rcx, ?NcaEvCollProbeCollect@@YAXPEAX000@Z; pfnwa
0x1800119d6  mov     rdx, rdi; pv
0x1800119d9  call    NcaTriggerRegisterWait
0x1800119de  mov     ebx, eax
0x1800119e0  test    eax, eax
0x1800119e2  jz      short loc_180011A0F
0x1800119e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119eb  lea     rsi, WPP_GLOBAL_Control
0x1800119f2  cmp     rcx, rsi
0x1800119f5  jz      loc_180011B51
0x1800119fb  test    [rcx+1Ch], r12b
0x1800119ff  jz      loc_180011B51
0x180011a05  mov     edx, 24h ; '$'
0x180011a0a  jmp     loc_1800117DB
0x180011a0f  mov     r8, [rsi]
0x180011a12  lea     rax, [rdi+0B8h]
0x180011a19  mov     [rsp+88h+var_60], rax
0x180011a1e  lea     rdx, stru_180028D30
0x180011a25  xor     r9d, r9d
0x180011a28  mov     [rsp+88h+var_68], rdi
0x180011a2d  mov     ecx, r12d
0x180011a30  call    NcaSrcLnkdTriggerRegisterWait
0x180011a35  mov     ebx, eax
0x180011a37  test    eax, eax
0x180011a39  jz      short loc_180011A66
0x180011a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a42  lea     rsi, WPP_GLOBAL_Control
0x180011a49  cmp     rcx, rsi
0x180011a4c  jz      loc_180011B51
0x180011a52  test    [rcx+1Ch], r12b
0x180011a56  jz      loc_180011B51
0x180011a5c  mov     edx, 25h ; '%'
0x180011a61  jmp     loc_1800117DB
0x180011a66  mov     rcx, [rsi]
0x180011a69  lea     r9, [rdi+0C0h]
0x180011a70  mov     r8, rdi
0x180011a73  xor     edx, edx
0x180011a75  call    NcaIPTriggerRegisterWait
0x180011a7a  mov     ebx, eax
0x180011a7c  test    eax, eax
0x180011a7e  jz      short loc_180011AAB
0x180011a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a87  lea     rsi, WPP_GLOBAL_Control
0x180011a8e  cmp     rcx, rsi
0x180011a91  jz      loc_180011B51
0x180011a97  test    [rcx+1Ch], r12b
0x180011a9b  jz      loc_180011B51
0x180011aa1  mov     edx, 26h ; '&'
0x180011aa6  jmp     loc_1800117DB
0x180011aab  mov     rax, [rsi]
0x180011aae  lea     rdx, [rdi+0C8h]
0x180011ab5  lea     rcx, [rsp+88h+var_58]
0x180011aba  mov     [rsp+88h+var_58], rax
0x180011abf  mov     [rsp+88h+var_50], 0
0x180011ac8  mov     [rsp+88h+var_48], rdi
0x180011acd  mov     [rsp+88h+var_40], 2
0x180011ad5  call    NcaWtsSessionChangeTriggerRegisterWait
0x180011ada  mov     ebx, eax
0x180011adc  test    eax, eax
0x180011ade  jz      short loc_180011B03
0x180011ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ae7  lea     rsi, WPP_GLOBAL_Control
0x180011aee  cmp     rcx, rsi
0x180011af1  jz      short loc_180011B51
0x180011af3  test    [rcx+1Ch], r12b
0x180011af7  jz      short loc_180011B51
0x180011af9  mov     edx, 27h ; '''
0x180011afe  jmp     loc_1800117DB
0x180011b03  mov     rcx, [rsi]
0x180011b06  lea     rax, [rdi+0D0h]
0x180011b0d  mov     r8, rdi
0x180011b10  mov     [rsp+88h+var_68], rax
0x180011b15  call    NcaTimerTriggerRegisterWait
0x180011b1a  mov     ebx, eax
0x180011b1c  test    eax, eax
0x180011b1e  jz      short loc_180011B43
0x180011b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b27  lea     rsi, WPP_GLOBAL_Control
0x180011b2e  cmp     rcx, rsi
0x180011b31  jz      short loc_180011B51
0x180011b33  test    [rcx+1Ch], r12b
0x180011b37  jz      short loc_180011B51
0x180011b39  mov     edx, 28h ; '('
0x180011b3e  jmp     loc_1800117DB
0x180011b43  lea     rsi, WPP_GLOBAL_Control
0x180011b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b51  cmp     dword ptr [rdi], 0
0x180011b54  jnz     short loc_180011B69
0x180011b56  xor     ebx, ebx
0x180011b58  xor     edx, edx
0x180011b5a  lea     ecx, [rbx+15h]
0x180011b5d  call    NcaDAPEvidenceSnapshotSetGlobalState
0x180011b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b69  cmp     [rdi+0D8h], r12d
0x180011b70  jnz     short loc_180011B88
0x180011b72  mov     rcx, r15; lpCriticalSection
0x180011b75  call    cs:__imp_LeaveCriticalSection
0x180011b7c  nop     dword ptr [rax+rax+00h]
0x180011b81  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b88  cmp     rcx, rsi
0x180011b8b  jz      short loc_180011BA8
0x180011b8d  test    byte ptr [rcx+1Ch], 8
0x180011b91  jz      short loc_180011BA8
0x180011b93  mov     rcx, [rcx+10h]
0x180011b97  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180011b9e  mov     edx, 2Ah ; '*'
0x180011ba3  call    WPP_SF_
0x180011ba8  mov     eax, ebx
0x180011baa  add     rsp, 50h
0x180011bae  pop     r15
0x180011bb0  pop     r14
0x180011bb2  pop     r12
0x180011bb4  pop     rdi
0x180011bb5  pop     rsi
0x180011bb6  pop     rbp
0x180011bb7  pop     rbx
0x180011bb8  retn
```
