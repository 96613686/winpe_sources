# SendUsingSmallMsg

- ea: `0x18003ff84`
- end: `0x180040c02`
- name: `SendUsingSmallMsg`
- size: `3198`
- prototype: `__int64 __usercall@<rax>(PVOID CompletionContext@<rcx>, __int64)`
- caller_count: `4`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1800289a0`
- `0x18003dae8`
- `0x18004b1d0`
- `0x180050074`

## callees

- `0x1800052a0`
- `0x180023b04`
- `0x180023c0c`
- `0x180023cc0`
- `0x180023dd0`
- `0x1800240a8`
- `0x180024fa4`
- `0x180038a20`
- `0x180038c40`
- `0x180038cf4`
- `0x180038d60`
- `0x18003ae8c`
- `0x18003dae8`
- `0x18003ff84`
- `0x180040c08`
- `0x180047484`
- `0x180047914`
- `0x180049af0`
- `0x18004c5dc`
- `0x18004c770`
- `0x18004f0d0`
- `0x18004f514`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800400cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040317`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040385`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800403b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040536`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004094b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040a33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040ae0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040bc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800400cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040317`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040385`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800403b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040536`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004094b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040a33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040ae0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040bc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800400a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040334`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800403a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040517`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040619`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040737`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040aca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040b13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040ba2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800400a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040334`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800403a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040517`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040619`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040737`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040aca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040b13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040ba2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180040325`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180040393`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180040325`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180040393`

## pseudocode

```c
__int64 __fastcall SendUsingSmallMsg(char *CompletionContext, __int64 a2, int a3, __int64 a4, _DWORD *a5)
{
  __int64 v5; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // r8d
  signed int v13; // r10d
  int v14; // r12d
  int IoSize; // r15d
  char *v16; // r8
  unsigned int v17; // r13d
  unsigned int v18; // r9d
  int v19; // ecx
  int v20; // eax
  _DWORD *v21; // rsi
  unsigned int v22; // eax
  unsigned int v23; // edx
  __int64 *v24; // rax
  __int64 v25; // rcx
  char *v26; // r15
  int v27; // ecx
  __int16 v28; // cx
  bool v29; // zf
  __int16 v30; // ax
  int v31; // eax
  ULONG v32; // r12d
  int v33; // esi
  int v34; // ecx
  int v35; // eax
  unsigned int v36; // ecx
  __int64 v37; // rsi
  unsigned int ControlHeader; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rcx
  int v42; // eax
  int v43; // r13d
  char v44; // al
  int v45; // esi
  int v46; // esi
  __int64 v47; // rcx
  __int64 v48; // r10
  ULONG v49; // esi
  volatile signed __int32 *v50; // rax
  int v51; // ecx
  __int64 v52; // r8
  int v53; // r9d
  unsigned int v54; // esi
  int v55; // r13d
  int v56; // r13d
  int v57; // esi
  char v58; // al
  int v59; // esi
  __int64 v60; // rdx
  __int64 v61; // rcx
  char *v62; // r8
  char *i; // rdx
  _QWORD *v64; // rax
  char **v65; // rcx
  __int64 v66; // rax
  __int64 (__fastcall *v67)(__int64, __int64 *, __int64, int *, _QWORD, char *, _QWORD, _QWORD, unsigned int *); // rax
  __int64 v68; // rcx
  int v69; // eax
  unsigned int v70; // eax
  PVOID *v71; // rdx
  int v72; // eax
  char *v73; // r15
  char *v74; // r8
  int v75; // eax
  int v76; // eax
  __int64 v77; // rax
  char **v78; // rdx
  int v79; // eax
  unsigned int v80; // ecx
  unsigned __int16 v81; // ax
  unsigned int v82; // edx
  __int16 v83; // ax
  unsigned __int16 v84; // ax
  char v85; // al
  unsigned int v86; // r8d
  __int64 ControlMessageStore; // rax
  PVOID *v89; // rdx
  _QWORD *v90; // rax
  int v91; // eax
  signed __int32 v92[6]; // [rsp+8h] [rbp-91h] BYREF
  int v93[2]; // [rsp+28h] [rbp-71h]
  int v94[2]; // [rsp+30h] [rbp-69h]
  __int64 v95; // [rsp+38h] [rbp-61h]
  ULONG v96[2]; // [rsp+40h] [rbp-59h]
  unsigned int *v97; // [rsp+48h] [rbp-51h]
  int v98; // [rsp+58h] [rbp-41h]
  int v99; // [rsp+5Ch] [rbp-3Dh]
  int v100; // [rsp+60h] [rbp-39h]
  int v101; // [rsp+64h] [rbp-35h]
  int v102; // [rsp+68h] [rbp-31h]
  int v103; // [rsp+6Ch] [rbp-2Dh]
  int v104; // [rsp+70h] [rbp-29h]
  signed int v105; // [rsp+74h] [rbp-25h]
  __int64 v106; // [rsp+78h] [rbp-21h] BYREF
  __int64 v107; // [rsp+80h] [rbp-19h]
  ULONG v108; // [rsp+88h] [rbp-11h] BYREF
  unsigned int v109; // [rsp+8Ch] [rbp-Dh]
  unsigned int v110; // [rsp+90h] [rbp-9h]
  int v111; // [rsp+94h] [rbp-5h]
  int v112; // [rsp+98h] [rbp-1h] BYREF
  int v113; // [rsp+9Ch] [rbp+3h]
  int v114[2]; // [rsp+A0h] [rbp+7h]
  __int64 v115; // [rsp+A8h] [rbp+Fh]
  unsigned int v116; // [rsp+100h] [rbp+67h] BYREF
  ULONG v117; // [rsp+108h] [rbp+6Fh]
  __int64 v118; // [rsp+110h] [rbp+77h]

  v118 = a4;
  v117 = a3;
  v5 = 0;
  LODWORD(v107) = 0;
  v106 = 0;
  v112 = 0;
  if ( !a2 )
  {
    v11 = 0;
    v115 = 0;
    v103 = 0;
    v101 = 0;
    *(_QWORD *)v114 = 0;
    v105 = 0;
LABEL_6:
    v14 = 1;
    goto LABEL_7;
  }
  v5 = *(_QWORD *)(a2 + 48);
  v10 = *(_QWORD *)(a2 + 136);
  v11 = *(unsigned int *)(a2 + 56);
  v12 = *(_DWORD *)(a2 + 60);
  v13 = *(_DWORD *)(a2 + 144);
  v115 = v5;
  v103 = v11;
  v101 = v12;
  *(_QWORD *)v114 = v10;
  v105 = v13;
  if ( !v5 && !v10 )
    goto LABEL_6;
  v14 = 0;
  v115 = v5;
  v103 = v11;
  v101 = v12;
  *(_QWORD *)v114 = v10;
  v105 = v13;
LABEL_7:
  v100 = v14;
  if ( a5 )
    *a5 = 0;
  v116 = 0;
  if ( a3 )
  {
    IoSize = a3;
  }
  else if ( a2 )
  {
    IoSize = *(_DWORD *)(a2 + 80) - *(_DWORD *)(a2 + 84);
  }
  else
  {
    IoSize = GetIoSize(v5, v11);
  }
  v99 = IoSize;
  while ( 1 )
  {
    if ( !(unsigned int)AreSendBuffersAvailable(CompletionContext) )
    {
      if ( !(unsigned __int8)InitializeStuckSendTracker((__int64)CompletionContext) )
      {
        if ( !v14 )
        {
LABEL_188:
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          *((_DWORD *)CompletionContext + 115) = 0;
          LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        }
        return 10055;
      }
      v116 = 997;
      if ( v14 && *(_BYTE *)(a4 + 24) != 20 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        ControlMessageStore = GetControlMessageStore(CompletionContext);
        if ( ControlMessageStore )
        {
          *(_BYTE *)(ControlMessageStore + 24) = *(_BYTE *)(a4 + 24);
          *(_QWORD *)(ControlMessageStore + 32) = *(_QWORD *)(a4 + 32);
          *(_QWORD *)(ControlMessageStore + 40) = *(_QWORD *)(a4 + 40);
          *(_QWORD *)(ControlMessageStore + 48) = *(_QWORD *)(a4 + 48);
          *(_QWORD *)(ControlMessageStore + 56) = *(_QWORD *)(a4 + 56);
          *(_DWORD *)(ControlMessageStore + 64) = 2;
          v89 = (PVOID *)*((_QWORD *)CompletionContext + 53);
          if ( *v89 != CompletionContext + 416 )
            goto LABEL_195;
          v90 = (_QWORD *)(ControlMessageStore + 8);
          v90[1] = v89;
          *v90 = CompletionContext + 416;
          *v89 = v90;
          *((_QWORD *)CompletionContext + 53) = v90;
        }
        else
        {
          v116 = 10055;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      }
      if ( a2 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        v91 = *(_DWORD *)(a2 + 92);
        if ( (v91 & 0x800) == 0 )
          *(_DWORD *)(a2 + 92) = v91 | 0x120;
        *((_DWORD *)CompletionContext + 115) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      }
      *(_DWORD *)(*((_QWORD *)CompletionContext + 64) + 36LL) = 1;
      return v116;
    }
    if ( IoSize > *((unsigned __int16 *)CompletionContext + 419)
      && !(unsigned __int8)AllocateStuckSendTracker(CompletionContext) )
    {
      goto LABEL_188;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    v16 = CompletionContext + 368;
    if ( *(char **)v16 != v16 && !*((_WORD *)CompletionContext + 422) )
      break;
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  }
  if ( a2 )
  {
    *(_DWORD *)(a2 + 92) &= 0xFFFFFFDE;
    ++*(_DWORD *)(a2 + 96);
  }
  v17 = *((_DWORD *)CompletionContext + 108);
  v116 = 0;
  v18 = 2 * (v14 ^ 1);
  v19 = 0;
  v110 = v18;
  if ( v17 <= v18 )
  {
    v116 = 997;
    v19 = 997;
    if ( a2 )
    {
      v20 = *(_DWORD *)(a2 + 92);
      if ( (v20 & 0x800) == 0 )
        *(_DWORD *)(a2 + 92) = v20 | 1;
    }
  }
  v21 = CompletionContext + 460;
  if ( v14 && (v17 - *v21 < 2 || *((char **)CompletionContext + 52) != CompletionContext + 416) )
  {
    v22 = CheckControlMessageSpecialConditions(CompletionContext, v118);
    v17 -= *v21;
    v16 = CompletionContext + 368;
    v18 = v110;
    v19 = v22;
    v116 = v22;
  }
  if ( v19 || !v14 && IoSize <= 0 )
  {
    v27 = v99;
    v23 = 0;
    v98 = 0;
    v26 = 0;
    goto LABEL_44;
  }
  --*((_DWORD *)CompletionContext + 108);
  if ( *v21 && !v14 )
    --*v21;
  v23 = *((_DWORD *)CompletionContext + 110);
  v98 = v23;
  *((_DWORD *)CompletionContext + 110) = v23 + 1;
  v24 = *(__int64 **)v16;
  if ( *(char **)(*(_QWORD *)v16 + 8LL) != v16 || (v25 = *v24, *(__int64 **)(*v24 + 8) != v24) )
LABEL_195:
    __fastfail(3u);
  *(_QWORD *)v16 = v25;
  v26 = (char *)(v24 - 5);
  *(_QWORD *)(v25 + 8) = v16;
  v27 = v99;
  if ( v99 > 0 && !v117 )
  {
    v28 = *((_WORD *)CompletionContext + 424);
    v29 = v28 == 300;
    v30 = v28 + 1;
    v27 = v99;
    *((_WORD *)CompletionContext + 424) = v30;
    if ( v29 )
      *((_DWORD *)CompletionContext + 212) = 0;
  }
LABEL_44:
  LOBYTE(v21) = 0;
  v102 = (int)v21;
  while ( 2 )
  {
    if ( v17 <= v18 || !v26 || !v14 && v27 <= 0 )
    {
LABEL_162:
      if ( a2 )
      {
        --*(_DWORD *)(a2 + 96);
        CheckBSQHeadForCompletion(CompletionContext);
      }
      v80 = RdmaThreshold;
      if ( (_BYTE)v21 )
      {
        ++*((_WORD *)CompletionContext + 425);
        v81 = v80;
        v82 = *(_DWORD *)(a2 + 80);
        if ( v82 < v80 )
          v81 = *(_DWORD *)(a2 + 80);
        if ( v81 <= *((_WORD *)CompletionContext + 421) )
        {
          v83 = *((_WORD *)CompletionContext + 421);
        }
        else
        {
          v83 = v80;
          if ( v82 < v80 )
            v83 = *(_DWORD *)(a2 + 80);
        }
        *((_WORD *)CompletionContext + 421) = v83;
      }
      if ( !v14 )
      {
        GetLargeRecvFCInfoNoPop(CompletionContext, 0);
        LOWORD(v80) = RdmaThreshold;
        *((_DWORD *)CompletionContext + 115) = 0;
      }
      if ( *((_WORD *)CompletionContext + 425) <= 0x1Eu )
        goto LABEL_161;
      v84 = *((_WORD *)CompletionContext + 419);
      if ( *((_WORD *)CompletionContext + 421) <= v84 )
        goto LABEL_161;
      if ( v84 >= (unsigned __int16)(v80 - 32) )
        goto LABEL_161;
      if ( !*((_DWORD *)CompletionContext + 220) )
        goto LABEL_161;
      v85 = CompletionContext[801];
      if ( (v85 & 0x12) != 0 || *((_WORD *)CompletionContext + 423) )
        goto LABEL_161;
      CompletionContext[801] = v85 | 2;
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      if ( (BYTE3(xmmword_180063D60) & 1) != 0 )
      {
        v86 = *((unsigned __int16 *)CompletionContext + 421);
        if ( RdmaThreshold < v86 )
          v86 = RdmaThreshold;
        WPP_SF_qD(1048, 209, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, CompletionContext, v86);
      }
      SendControlMessage(CompletionContext, 0, 0);
      return v116;
    }
    if ( a2 )
    {
      v31 = *((unsigned __int16 *)CompletionContext + 419);
      v32 = v27;
      v33 = *(_DWORD *)(a2 + 84);
      v104 = v33;
      if ( v31 < v27 )
        v32 = v31;
      ++*(_DWORD *)(a2 + 88);
      *(_DWORD *)(a2 + 40) += v32;
      v34 = *(_DWORD *)(a2 + 40);
      *(_DWORD *)(a2 + 84) = v33 + v32;
      v35 = *(_DWORD *)(a2 + 92);
      if ( (v35 & 8) != 0 && v34 == *(_DWORD *)(a2 + 80) )
      {
        v36 = *(_DWORD *)(a2 + 160);
        if ( !v36 || *(_DWORD *)(a2 + 168) >= v36 || (v35 & 0x200) != 0 )
          *(_DWORD *)(a2 + 92) = v35 | 0x10;
      }
    }
    else
    {
      v104 = 0;
      v32 = 0;
    }
    v37 = v118;
    ControlHeader = CreateControlHeader(CompletionContext, *((_QWORD *)v26 + 12), v118, v23);
    v29 = *((_DWORD *)CompletionContext + 112) == -1;
    v41 = *((_QWORD *)v26 + 12);
    v109 = ControlHeader;
    v113 = *((_DWORD *)CompletionContext + 109);
    v42 = *(_DWORD *)(v41 + 16);
    v111 = v42;
    *((_DWORD *)CompletionContext + 109) = v42;
    if ( v29 )
    {
      v111 = v42 + 1;
      *((_DWORD *)CompletionContext + 109) = v42 + 1;
    }
    v43 = v100;
    if ( v100 )
    {
      v44 = *(_BYTE *)(v37 + 24);
      if ( v44 == 16 )
      {
        DontSendAnyMore(CompletionContext, v39, v40, 0);
        v45 = v98;
        while ( v45 != *((_DWORD *)CompletionContext + 228) )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          Sleep(0);
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        }
        ResetFlowControlVars(CompletionContext);
        v98 = --*((_DWORD *)CompletionContext + 228);
      }
      else if ( v44 == 15 )
      {
        if ( !CompletionContext[208] )
          DontSendAnyMore(CompletionContext, v39, v40, 0);
        CompletionContext[800] |= 0x80u;
        v46 = v98;
        while ( v46 != *((_DWORD *)CompletionContext + 228) )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          Sleep(0);
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        }
      }
    }
    else
    {
      ++*((_DWORD *)CompletionContext + 113);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    v47 = v109;
    v48 = *((_QWORD *)v26 + 12) + v109;
    v107 = v48;
    if ( v117 )
    {
      v49 = v117;
      if ( a2 )
        v49 = v32;
    }
    else
    {
      v49 = *((unsigned __int16 *)CompletionContext + 418) - v109 + 40;
    }
    LODWORD(v106) = v49;
    if ( v43 )
    {
      v56 = v99;
      goto LABEL_97;
    }
    if ( *(_QWORD *)v114 )
    {
      v51 = 0;
      v108 = 0;
      v52 = *((_QWORD *)CompletionContext + 27);
      v53 = a2 != 0 ? v104 : 0;
      v97 = &v108;
      if ( (int)(v53 + v49) < v105 )
        v51 = 259;
      v54 = AfdCompleteRedirectedRequest(
              v51,
              *(_QWORD *)(*(_QWORD *)CompletionContext + 8LL),
              (int)v52 + 24,
              v114[0],
              v51,
              v53,
              v48,
              v49,
              (__int64)v97);
      if ( (v54 & 0xC0000000) != 0xC0000000 )
      {
        v49 = v108;
        if ( v108 != v32 )
        {
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_ddq(1025, 205, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v32, v108, CompletionContext);
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          *(_DWORD *)(a2 + 84) += v49 - v32;
          *(_DWORD *)(a2 + 40) += v49 - v32;
          LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        }
        LODWORD(v106) = v49;
        goto LABEL_95;
      }
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 204, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v54);
      v116 = NtStatusToSocketError(v54);
LABEL_82:
      v14 = 0;
      goto LABEL_124;
    }
    if ( (unsigned int)CopyFromUserBuffer(v48, (unsigned int)&v106, v115, v103, v104) )
    {
      v50 = (volatile signed __int32 *)*((_QWORD *)CompletionContext + 1);
      v116 = 10014;
      _InterlockedIncrement(v50);
      goto LABEL_82;
    }
    v49 = v106;
LABEL_95:
    v55 = v99;
    v47 = v109;
    *a5 += v49;
    v56 = v55 - v49;
    v99 = v56;
LABEL_97:
    v14 = v100;
    v107 = *((_QWORD *)v26 + 12);
    if ( v100 )
    {
      v57 = v47;
      LODWORD(v106) = v47;
    }
    else
    {
      v57 = v47 + v49;
      LODWORD(v106) = v57;
    }
    *(_DWORD *)(*((_QWORD *)v26 + 12) + 4LL) = v57;
    v58 = v101 & 1;
    v29 = (v101 & 1) == 0;
    *(_WORD *)(v26 + 85) = 256;
    v26[87] = v58;
    *((_QWORD *)v26 + 7) = CompletionContext;
    *((_QWORD *)v26 + 9) = a2;
    if ( !v29 )
      *(_DWORD *)(*((_QWORD *)v26 + 12) + 20LL) |= 1u;
    v59 = v98;
    if ( (xmmword_180063D60 & 0x80u) != 0LL )
    {
      LODWORD(v95) = *((_DWORD *)CompletionContext + 111);
      v94[0] = v98;
      WPP_SF_dqdd(v47, 206, 0, (unsigned int)v106, v26, *(_QWORD *)v94, v95);
      if ( (xmmword_180063D60 & 0x80u) != 0LL )
        WPP_SF_iDq(v61, v60, 0, *((_QWORD *)CompletionContext + 13), v101, v26 + 8);
    }
    if ( v59 == *((_DWORD *)CompletionContext + 228) )
    {
      v66 = *((_QWORD *)CompletionContext + 2);
      v97 = &v116;
      *(_QWORD *)v96 = 0;
      v95 = 0;
      v67 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64, int *, _QWORD, char *, _QWORD, _QWORD, unsigned int *))(v66 + 248);
      *(_QWORD *)v94 = v26 + 8;
      v68 = *((_QWORD *)CompletionContext + 13);
      v93[0] = 0;
      v69 = v67(v68, &v106, 1, &v112, *(_QWORD *)v93, v26 + 8, 0, 0, &v116);
      _InterlockedIncrement((volatile signed __int32 *)CompletionContext + 228);
      v29 = v69 == -1;
      v70 = v116;
      if ( v29 && v116 == 997 )
      {
        v70 = 0;
        v116 = 0;
      }
      if ( !v70 && v56 > 0 )
        AreSendBuffersAvailable(CompletionContext);
LABEL_124:
      EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      if ( !v116 )
      {
        v26[84] = 1;
        v71 = (PVOID *)*((_QWORD *)CompletionContext + 49);
        if ( *v71 != CompletionContext + 384 )
          goto LABEL_195;
        *((_QWORD *)v26 + 5) = CompletionContext + 384;
        *((_QWORD *)v26 + 6) = v71;
        *v71 = v26 + 40;
        *((_QWORD *)CompletionContext + 49) = v26 + 40;
        if ( *((char **)CompletionContext + 115) != CompletionContext + 920 )
          CheckIfSendsCurrent(CompletionContext, 0);
        goto LABEL_128;
      }
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 208, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v116);
      v78 = (char **)*((_QWORD *)CompletionContext + 47);
      if ( *v78 == CompletionContext + 368 )
      {
        *((_QWORD *)v26 + 5) = CompletionContext + 368;
        *((_QWORD *)v26 + 6) = v78;
        *v78 = v26 + 40;
        *((_QWORD *)CompletionContext + 47) = v26 + 40;
        v79 = v113 + *((_DWORD *)CompletionContext + 109) - v111;
        ++*((_DWORD *)CompletionContext + 108);
        --*((_DWORD *)CompletionContext + 110);
        *((_DWORD *)CompletionContext + 109) = v79;
        if ( !v14 )
        {
          --*((_DWORD *)CompletionContext + 113);
          *((_DWORD *)CompletionContext + 115) = 0;
        }
        if ( *((char **)CompletionContext + 115) != CompletionContext + 920 )
          CheckIfSendsCurrent(CompletionContext, v116);
        if ( a2 )
        {
          --*(_DWORD *)(a2 + 88);
          --*(_DWORD *)(a2 + 96);
LABEL_160:
          CheckBSQHeadForCompletion(CompletionContext);
        }
        goto LABEL_161;
      }
      goto LABEL_195;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    v62 = CompletionContext + 920;
    *((_DWORD *)v26 + 6) = v106;
    *((_DWORD *)v26 + 7) = 0;
    for ( i = (char *)*((_QWORD *)CompletionContext + 115); i != v62; i = *(char **)i )
    {
      if ( v59 - *(_DWORD *)(*((_QWORD *)i + 7) + 8LL) < 0 )
      {
        v64 = (_QWORD *)*((_QWORD *)i + 1);
        *((_QWORD *)v26 + 6) = v64;
        *((_QWORD *)v26 + 5) = i;
        *v64 = v26 + 40;
        *(_QWORD *)(*((_QWORD *)v26 + 5) + 8LL) = v26 + 40;
        goto LABEL_113;
      }
    }
    v65 = (char **)*((_QWORD *)CompletionContext + 116);
    if ( *v65 != v62 )
      goto LABEL_195;
    *((_QWORD *)v26 + 5) = v62;
    *((_QWORD *)v26 + 6) = v65;
    *v65 = v26 + 40;
    *((_QWORD *)CompletionContext + 116) = v26 + 40;
LABEL_113:
    _InterlockedOr(v92, 0);
    v116 = CheckIfSendsCurrent(CompletionContext, 0);
    if ( !v116 )
    {
LABEL_128:
      v27 = v99;
      LOBYTE(v21) = v102;
      if ( v99 > 0 && a2 )
      {
        LODWORD(v21) = (unsigned __int8)v102;
        if ( ResizeEnabled )
          LODWORD(v21) = 1;
        v102 = (int)v21;
      }
      v17 = *((_DWORD *)CompletionContext + 108);
      if ( v17 > 2 )
      {
        if ( v99 > 0 )
        {
          v73 = (char *)*((_QWORD *)CompletionContext + 46);
          v74 = CompletionContext + 368;
          if ( v73 != CompletionContext + 368 )
          {
            *((_DWORD *)CompletionContext + 108) = v17 - 1;
            v76 = *((_DWORD *)CompletionContext + 115);
            if ( v76 )
              *((_DWORD *)CompletionContext + 115) = v76 - 1;
            v23 = *((_DWORD *)CompletionContext + 110);
            v98 = v23;
            *((_DWORD *)CompletionContext + 110) = v23 + 1;
            if ( *((char **)v73 + 1) != v74 )
              goto LABEL_195;
            v77 = *(_QWORD *)v73;
            if ( *(char **)(*(_QWORD *)v73 + 8LL) != v73 )
              goto LABEL_195;
            *((_QWORD *)CompletionContext + 46) = v77;
            v26 = v73 - 40;
            *(_QWORD *)(v77 + 8) = v74;
            goto LABEL_144;
          }
          v75 = *(_DWORD *)(a2 + 92);
          if ( (v75 & 0x800) == 0 )
            *(_DWORD *)(a2 + 92) = v75 | 0x120;
          InitializeStuckSendTracker((__int64)CompletionContext);
          v27 = v99;
          v26 = 0;
          *(_DWORD *)(*((_QWORD *)CompletionContext + 64) + 36LL) = 1;
        }
      }
      else if ( a2 && v99 > 0 )
      {
        v72 = *(_DWORD *)(a2 + 92);
        v23 = v98;
        if ( (v72 & 0x800) == 0 )
          *(_DWORD *)(a2 + 92) = v72 | 1;
        goto LABEL_144;
      }
      v23 = v98;
LABEL_144:
      if ( v14 )
        goto LABEL_162;
      v18 = v110;
      continue;
    }
    break;
  }
  if ( !v14 )
    *((_DWORD *)CompletionContext + 115) = 0;
  if ( a2 )
  {
    --*(_DWORD *)(a2 + 96);
    goto LABEL_160;
  }
LABEL_161:
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  return v116;
}

```

## disassembly

```asm
0x18003ff84  mov     rax, rsp
0x18003ff87  mov     [rax+8], rbx
0x18003ff8b  mov     [rax+20h], r9
0x18003ff8f  mov     [rax+18h], r8d
0x18003ff93  push    rbp
0x18003ff94  push    rsi
0x18003ff95  push    rdi
0x18003ff96  push    r12
0x18003ff98  push    r13
0x18003ff9a  push    r14
0x18003ff9c  push    r15
0x18003ff9e  lea     rbp, [rax-57h]
0x18003ffa2  sub     rsp, 0B0h
0x18003ffa9  xor     eax, eax
0x18003ffab  xor     r13d, r13d
0x18003ffae  mov     qword ptr [rbp+4Fh+var_6C], rax
0x18003ffb2  mov     rsi, r9
0x18003ffb5  mov     [rbp-21h], rax
0x18003ffb9  mov     r9d, r8d
0x18003ffbc  mov     [rbp+4Fh+var_50], r13d
0x18003ffc0  mov     rdi, rdx
0x18003ffc3  mov     rbx, rcx
0x18003ffc6  test    rdx, rdx
0x18003ffc9  jz      short loc_180040019
0x18003ffcb  mov     rax, [rdx+30h]
0x18003ffcf  mov     rcx, [rdi+88h]
0x18003ffd6  mov     edx, [rdx+38h]
0x18003ffd9  mov     r8d, [rdi+3Ch]
0x18003ffdd  mov     r10d, [rdi+90h]
0x18003ffe4  mov     [rbp+4Fh+var_40], rax
0x18003ffe8  mov     [rbp+4Fh+var_7C], edx
0x18003ffeb  mov     [rbp+4Fh+var_84], r8d
0x18003ffef  mov     qword ptr [rbp+4Fh+var_48], rcx
0x18003fff3  mov     [rbp+4Fh+var_74], r10d
0x18003fff7  test    rax, rax
0x18003fffa  jnz     short loc_180040001
0x18003fffc  test    rcx, rcx
0x18003ffff  jz      short loc_18004002F
0x180040001  mov     r12d, r13d
0x180040004  mov     [rbp+4Fh+var_40], rax
0x180040008  mov     [rbp+4Fh+var_7C], edx
0x18004000b  mov     [rbp+4Fh+var_84], r8d
0x18004000f  mov     qword ptr [rbp+4Fh+var_48], rcx
0x180040013  mov     [rbp+4Fh+var_74], r10d
0x180040017  jmp     short loc_180040035
0x180040019  mov     edx, r13d
0x18004001c  mov     [rbp+4Fh+var_40], rax
0x180040020  mov     [rbp+4Fh+var_7C], edx
0x180040023  mov     [rbp+4Fh+var_84], r13d
0x180040027  mov     qword ptr [rbp+4Fh+var_48], r13
0x18004002b  mov     [rbp+4Fh+var_74], r13d
0x18004002f  mov     r12d, 1
0x180040035  mov     rcx, [rbp+4Fh+arg_20]
0x180040039  mov     [rbp+4Fh+var_88], r12d
0x18004003d  test    rcx, rcx
0x180040040  jz      short loc_180040045
0x180040042  mov     [rcx], r13d
0x180040045  mov     [rbp+4Fh+arg_8], r13d
0x180040049  test    r9d, r9d
0x18004004c  jz      short loc_180040053
0x18004004e  mov     r15d, r9d
0x180040051  jmp     short loc_18004006D
0x180040053  test    rdi, rdi
0x180040056  jz      short loc_180040062
0x180040058  mov     r15d, [rdi+50h]
0x18004005c  sub     r15d, [rdi+54h]
0x180040060  jmp     short loc_18004006D
0x180040062  mov     rcx, rax
0x180040065  call    GetIoSize
0x18004006a  mov     r15d, eax
0x18004006d  mov     [rbp+4Fh+var_8C], r15d
0x180040071  lea     r14, [rbx+30h]
0x180040075  mov     rcx, rbx
0x180040078  call    AreSendBuffersAvailable
0x18004007d  test    eax, eax
0x18004007f  jz      loc_180040AB6
0x180040085  movzx   eax, word ptr [rbx+346h]
0x18004008c  cmp     r15d, eax
0x18004008f  jle     short loc_1800400A1
0x180040091  mov     rcx, rbx
0x180040094  call    AllocateStuckSendTracker
0x180040099  test    al, al
0x18004009b  jz      loc_180040AC7
0x1800400a1  mov     rcx, r14; lpCriticalSection
0x1800400a4  call    cs:__imp_EnterCriticalSection
0x1800400ab  nop     dword ptr [rax+rax+00h]
0x1800400b0  lea     r8, [rbx+170h]
0x1800400b7  cmp     [r8], r8
0x1800400ba  jz      short loc_1800400CC
0x1800400bc  xor     r10d, r10d
0x1800400bf  cmp     [rbx+34Ch], r10w
0x1800400c7  jz      short loc_1800400DD
0x1800400c9  xor     r13d, r13d
0x1800400cc  mov     rcx, r14; lpCriticalSection
0x1800400cf  call    cs:__imp_LeaveCriticalSection
0x1800400d6  nop     dword ptr [rax+rax+00h]
0x1800400db  jmp     short loc_180040075
0x1800400dd  mov     r11d, 1
0x1800400e3  test    rdi, rdi
0x1800400e6  jz      short loc_1800400F0
0x1800400e8  and     dword ptr [rdi+5Ch], 0FFFFFFDEh
0x1800400ec  add     [rdi+60h], r11d
0x1800400f0  mov     r13d, [rbx+1B0h]
0x1800400f7  mov     r9d, r12d
0x1800400fa  xor     r9d, r11d
0x1800400fd  mov     [rbp+4Fh+arg_8], r10d
0x180040101  add     r9d, r9d
0x180040104  mov     ecx, r10d
0x180040107  mov     [rbp+4Fh+var_58], r9d
0x18004010b  mov     edx, 3E5h
0x180040110  cmp     r13d, r9d
0x180040113  ja      short loc_18004012E
0x180040115  mov     [rbp+4Fh+arg_8], edx
0x180040118  mov     ecx, edx
0x18004011a  test    rdi, rdi
0x18004011d  jz      short loc_18004012E
0x18004011f  mov     eax, [rdi+5Ch]
0x180040122  bt      eax, 0Bh
0x180040126  jb      short loc_18004012E
0x180040128  or      eax, r11d
0x18004012b  mov     [rdi+5Ch], eax
0x18004012e  lea     rsi, [rbx+1CCh]
0x180040135  test    r12d, r12d
0x180040138  jz      short loc_180040176
0x18004013a  mov     eax, r13d
0x18004013d  sub     eax, [rsi]
0x18004013f  cmp     eax, 2
0x180040142  jb      short loc_180040150
0x180040144  lea     rax, [rbx+1A0h]
0x18004014b  cmp     [rax], rax
0x18004014e  jz      short loc_180040176
0x180040150  mov     rdx, [rbp+4Fh+arg_18]
0x180040154  mov     rcx, rbx
0x180040157  call    CheckControlMessageSpecialConditions
0x18004015c  sub     r13d, [rsi]
0x18004015f  lea     r8, [rbx+170h]
0x180040166  mov     r9d, [rbp+4Fh+var_58]
0x18004016a  xor     r10d, r10d
0x18004016d  mov     ecx, eax
0x18004016f  mov     [rbp+4Fh+arg_8], eax
0x180040172  lea     r11d, [r10+1]
0x180040176  test    ecx, ecx
0x180040178  jnz     loc_180040212
0x18004017e  test    r12d, r12d
0x180040181  jnz     short loc_18004018C
0x180040183  test    r15d, r15d
0x180040186  jle     loc_180040212
0x18004018c  dec     dword ptr [rbx+1B0h]
0x180040192  mov     eax, [rsi]
0x180040194  test    eax, eax
0x180040196  jz      short loc_1800401A1
0x180040198  test    r12d, r12d
0x18004019b  jnz     short loc_1800401A1
0x18004019d  dec     eax
0x18004019f  mov     [rsi], eax
0x1800401a1  mov     edx, [rbx+1B8h]
0x1800401a7  mov     [rbp+4Fh+var_90], edx
0x1800401aa  lea     eax, [rdx+1]
0x1800401ad  mov     [rbx+1B8h], eax
0x1800401b3  mov     rax, [r8]
0x1800401b6  cmp     [rax+8], r8
0x1800401ba  jnz     loc_180040B7D
0x1800401c0  mov     rcx, [rax]
0x1800401c3  cmp     [rcx+8], rax
0x1800401c7  jnz     loc_180040B7D
0x1800401cd  mov     [r8], rcx
0x1800401d0  lea     r15, [rax-28h]
0x1800401d4  mov     [rcx+8], r8
0x1800401d8  mov     ecx, [rbp+4Fh+var_8C]
0x1800401db  test    ecx, ecx
0x1800401dd  jle     short loc_18004021E
0x1800401df  cmp     [rbp+4Fh+arg_10], r10d
0x1800401e3  jnz     short loc_18004021E
0x1800401e5  movzx   ecx, word ptr [rbx+350h]
0x1800401ec  mov     r8d, 12Ch
0x1800401f2  cmp     cx, r8w
0x1800401f6  lea     eax, [r11+rcx]
0x1800401fa  mov     ecx, [rbp+4Fh+var_8C]
0x1800401fd  mov     [rbx+350h], ax
0x180040204  jnz     short loc_18004021E
0x180040206  mov     dword ptr [rbx+350h], 0
0x180040210  jmp     short loc_18004021E
0x180040212  mov     ecx, [rbp+4Fh+var_8C]
0x180040215  mov     edx, r10d
0x180040218  mov     [rbp+4Fh+var_90], edx
0x18004021b  mov     r15, r10
0x18004021e  mov     sil, r10b
0x180040221  mov     [rbp+4Fh+var_80], esi
0x180040224  cmp     r13d, r9d
0x180040227  jbe     loc_18004095C
0x18004022d  test    r15, r15
0x180040230  jz      loc_18004095C
0x180040236  test    r12d, r12d
0x180040239  jnz     short loc_180040243
0x18004023b  test    ecx, ecx
0x18004023d  jle     loc_18004095C
0x180040243  test    rdi, rdi
0x180040246  jz      short loc_18004029C
0x180040248  movzx   eax, word ptr [rbx+346h]
0x18004024f  mov     r12d, ecx
0x180040252  mov     esi, [rdi+54h]
0x180040255  cmp     eax, ecx
0x180040257  mov     [rbp+4Fh+var_78], esi
0x18004025a  cmovl   r12d, eax
0x18004025e  add     [rdi+58h], r11d
0x180040262  add     [rdi+28h], r12d
0x180040266  mov     ecx, [rdi+28h]
0x180040269  lea     eax, [rsi+r12]
0x18004026d  mov     [rdi+54h], eax
0x180040270  mov     eax, [rdi+5Ch]
0x180040273  test    al, 8
0x180040275  jz      short loc_1800402A3
0x180040277  cmp     ecx, [rdi+50h]
0x18004027a  jnz     short loc_1800402A3
0x18004027c  mov     ecx, [rdi+0A0h]
0x180040282  test    ecx, ecx
0x180040284  jz      short loc_180040294
0x180040286  cmp     [rdi+0A8h], ecx
0x18004028c  jnb     short loc_180040294
0x18004028e  bt      eax, 9
0x180040292  jnb     short loc_1800402A3
0x180040294  or      eax, 10h
0x180040297  mov     [rdi+5Ch], eax
0x18004029a  jmp     short loc_1800402A3
0x18004029c  mov     [rbp+4Fh+var_78], r10d
0x1800402a0  mov     r12d, r10d
0x1800402a3  mov     rsi, [rbp+4Fh+arg_18]
0x1800402a7  mov     r9d, edx
0x1800402aa  mov     rdx, [r15+60h]
0x1800402ae  mov     r8, rsi
0x1800402b1  mov     rcx, rbx
0x1800402b4  call    CreateControlHeader
0x1800402b9  cmp     dword ptr [rbx+1C0h], 0FFFFFFFFh
0x1800402c0  mov     rcx, [r15+60h]
0x1800402c4  mov     dword ptr [rbp+4Fh+var_60+4], eax
0x1800402c7  mov     eax, [rbx+1B4h]
0x1800402cd  mov     [rbp+4Fh+var_4C], eax
0x1800402d0  mov     eax, [rcx+10h]
0x1800402d3  mov     [rbp+4Fh+var_54], eax
0x1800402d6  mov     [rbx+1B4h], eax
0x1800402dc  jnz     short loc_1800402E9
0x1800402de  inc     eax
0x1800402e0  mov     [rbp+4Fh+var_54], eax
0x1800402e3  mov     [rbx+1B4h], eax
0x1800402e9  mov     r13d, [rbp+4Fh+var_88]
0x1800402ed  xor     r9d, r9d
0x1800402f0  test    r13d, r13d
0x1800402f3  jnz     short loc_180040300
0x1800402f5  inc     dword ptr [rbx+1C4h]
0x1800402fb  jmp     loc_1800403B6
0x180040300  mov     al, [rsi+18h]
0x180040303  cmp     al, 10h
0x180040305  jnz     short loc_180040361
0x180040307  mov     rcx, rbx
0x18004030a  call    DontSendAnyMore
0x18004030f  mov     esi, [rbp+4Fh+var_90]
0x180040312  jmp     short loc_180040340
0x180040314  mov     rcx, r14; lpCriticalSection
0x180040317  call    cs:__imp_LeaveCriticalSection
0x18004031e  nop     dword ptr [rax+rax+00h]
0x180040323  xor     ecx, ecx; dwMilliseconds
0x180040325  call    cs:__imp_Sleep
0x18004032c  nop     dword ptr [rax+rax+00h]
0x180040331  mov     rcx, r14; lpCriticalSection
0x180040334  call    cs:__imp_EnterCriticalSection
0x18004033b  nop     dword ptr [rax+rax+00h]
0x180040340  cmp     esi, [rbx+390h]
0x180040346  jnz     short loc_180040314
0x180040348  mov     rcx, rbx
0x18004034b  call    ResetFlowControlVars
0x180040350  dec     dword ptr [rbx+390h]
0x180040356  mov     esi, [rbx+390h]
0x18004035c  mov     [rbp+4Fh+var_90], esi
0x18004035f  jmp     short loc_1800403B6
0x180040361  cmp     al, 0Fh
0x180040363  jnz     short loc_1800403B6
0x180040365  cmp     [rbx+0D0h], r9b
0x18004036c  jnz     short loc_180040376
0x18004036e  mov     rcx, rbx
0x180040371  call    DontSendAnyMore
0x180040376  or      byte ptr [rbx+320h], 80h
0x18004037d  mov     esi, [rbp+4Fh+var_90]
0x180040380  jmp     short loc_1800403AE
0x180040382  mov     rcx, r14; lpCriticalSection
0x180040385  call    cs:__imp_LeaveCriticalSection
0x18004038c  nop     dword ptr [rax+rax+00h]
0x180040391  xor     ecx, ecx; dwMilliseconds
0x180040393  call    cs:__imp_Sleep
0x18004039a  nop     dword ptr [rax+rax+00h]
0x18004039f  mov     rcx, r14; lpCriticalSection
0x1800403a2  call    cs:__imp_EnterCriticalSection
0x1800403a9  nop     dword ptr [rax+rax+00h]
0x1800403ae  cmp     esi, [rbx+390h]
0x1800403b4  jnz     short loc_180040382
0x1800403b6  mov     rcx, r14; lpCriticalSection
0x1800403b9  call    cs:__imp_LeaveCriticalSection
0x1800403c0  nop     dword ptr [rax+rax+00h]
0x1800403c5  mov     ecx, dword ptr [rbp+4Fh+var_60+4]
0x1800403c8  xor     r8d, r8d
0x1800403cb  mov     eax, [rbp+4Fh+arg_10]
  ... truncated ...
```
