# CpuUtilizationTroubleshooter::ProcessSampleEvent(_EVENT_RECORD *)

- ea: `0x180018ce0`
- end: `0x180019acb`
- name: `?ProcessSampleEvent@CpuUtilizationTroubleshooter@@AEAAXPEAU_EVENT_RECORD@@@Z`
- size: `3563`
- prototype: `void(CpuUtilizationTroubleshooter *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180019d60`

## callees

- `0x180018c3c`
- `0x180018c90`
- `0x180018ce0`
- `0x180019d38`
- `0x18003dfdc`
- `0x18004ca90`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800190a5`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180019465`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001947e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800190a5`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180019465`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001947e`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180018d63`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180018dae`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180018d63`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x180018dae`

## string_xrefs

- `0x180018d7b`: `ThreadId`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CpuUtilizationTroubleshooter::ProcessSampleEvent(__int64 **this, struct _EVENT_RECORD *a2)
{
  __int64 *v4; // r8
  __int64 *v5; // rax
  __int64 *i; // rdx
  __int64 *v7; // r8
  __int64 *v8; // rax
  __int64 *v9; // r9
  __int64 **v10; // r12
  unsigned int ProcessorNumber; // ecx
  __int64 *v12; // rsi
  __int64 *v13; // rbx
  int v14; // r14d
  __int64 *v15; // r9
  __int64 *v16; // rax
  __int64 *v17; // rdi
  __int64 *v18; // rsi
  LARGE_INTEGER TimeStamp; // rdi
  __int64 v20; // r8
  unsigned int v21; // ecx
  __int64 *v22; // r13
  __int64 *v23; // rbx
  int v24; // r15d
  __int64 *v25; // r9
  __int64 *v26; // rax
  __int64 *v27; // r14
  __int64 v28; // rdi
  __int64 v29; // r9
  CpuUtilizationTroubleshooter *v30; // r10
  _QWORD *v31; // r13
  unsigned __int64 v32; // rdi
  unsigned __int64 *j; // rbx
  __int64 *v34; // rdx
  __int64 v35; // rbx
  __int64 v36; // rdx
  __int64 *v37; // r12
  __int64 *v38; // rdi
  int v39; // r15d
  __int64 *v40; // r9
  __int64 *v41; // rax
  __int64 *v42; // rsi
  ULONGLONG v43; // rsi
  int v44; // r15d
  ULONGLONG PropertyName; // r9
  ULONGLONG v46; // rax
  ULONGLONG *v47; // r14
  char *v48; // rax
  __int64 v49; // rdx
  ULONGLONG v50; // rcx
  ULONGLONG *v51; // r11
  ULONGLONG v52; // r10
  __int64 v53; // rdx
  __int64 *v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 *v57; // r10
  __int64 *v58; // r11
  _DWORD *v59; // rax
  _DWORD *v60; // rax
  char *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rdx
  __int64 *v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rax
  char *v67; // rax
  __int64 v68; // rdx
  __int64 *v69; // r10
  _QWORD *v70; // rdx
  __int64 v71; // rcx
  __int64 *v72; // r8
  __int64 v73; // rax
  __int64 v74; // rax
  _QWORD *v75; // r8
  _QWORD *v76; // rax
  _QWORD *v77; // rcx
  _QWORD *v78; // r8
  __int64 v79; // rax
  _QWORD *v80; // rax
  _QWORD *v81; // r8
  __int64 v82; // rax
  _QWORD *v83; // rax
  _QWORD *v84; // rax
  char *v85; // rax
  __int64 v86; // rdx
  __int64 *v87; // r10
  _QWORD *v88; // rdx
  __int64 v89; // rcx
  __int64 *v90; // r8
  __int64 v91; // rax
  __int64 v92; // rax
  _QWORD *v93; // r8
  _QWORD *v94; // rax
  _QWORD *v95; // rcx
  _QWORD *v96; // r8
  __int64 v97; // rax
  _QWORD *v98; // rax
  _QWORD *v99; // r8
  __int64 v100; // rax
  _QWORD *v101; // rax
  _QWORD *v102; // rax
  __int64 v103; // [rsp+40h] [rbp-39h] BYREF
  BYTE v104[4]; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v105; // [rsp+4Ch] [rbp-2Dh] BYREF
  unsigned int v106; // [rsp+50h] [rbp-29h] BYREF
  CpuUtilizationTroubleshooter *v107; // [rsp+58h] [rbp-21h]
  BYTE pBuffer[8]; // [rsp+60h] [rbp-19h] BYREF
  __int64 *v109; // [rsp+68h] [rbp-11h] BYREF
  __int64 v110; // [rsp+70h] [rbp-9h]
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+80h] [rbp+7h] BYREF

  v107 = (CpuUtilizationTroubleshooter *)this;
  *(_QWORD *)pBuffer = 0;
  *(_DWORD *)v104 = 0;
  if ( !*((_BYTE *)this + 36) )
    return;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"InstructionPointer";
  if ( TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 8u, pBuffer) )
    return;
  pPropertyData.Reserved = 0;
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = (ULONGLONG)L"ThreadId";
  if ( TdhGetProperty(a2, 0, 0, 1u, &pPropertyData, 4u, v104) )
    return;
  v4 = this[11];
  v5 = (__int64 *)v4[1];
  pPropertyData.Reserved = 0;
  for ( i = v4; !*((_BYTE *)v5 + 25); v5 = (__int64 *)*v5 )
  {
    if ( *((_DWORD *)v5 + 7) >= *(_DWORD *)v104 )
      i = v5;
    else
      v5 += 2;
  }
  if ( *((_BYTE *)i + 25) || *(_DWORD *)v104 < *((_DWORD *)i + 7) || i == v4 )
    return;
  v7 = this[9];
  v8 = (__int64 *)v7[1];
  pPropertyData.Reserved = 0;
  v9 = v7;
  v109 = v7;
  if ( !*((_BYTE *)v8 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v8 + 7) >= *((_DWORD *)i + 8) )
        v9 = v8;
      else
        v8 += 2;
      v8 = (__int64 *)*v8;
    }
    while ( !*((_BYTE *)v8 + 25) );
    v109 = v9;
  }
  if ( *((_BYTE *)v9 + 25) || *((_DWORD *)i + 8) < *((_DWORD *)v9 + 7) || v9 == v7 )
    return;
  v10 = this + 13;
  ProcessorNumber = a2->BufferContext.ProcessorNumber;
  v105 = ProcessorNumber;
  v12 = this[13];
  v13 = (__int64 *)v12[1];
  v14 = 0;
  pPropertyData.Reserved = 0;
  v15 = v12;
  v16 = v13;
  if ( *((_BYTE *)v13 + 25) )
  {
    v17 = v13;
  }
  else
  {
    do
    {
      v17 = v16;
      v13 = v16;
      if ( *((_DWORD *)v16 + 8) < ProcessorNumber )
      {
        v14 = 0;
        v16 += 2;
      }
      else
      {
        v14 = 1;
        v15 = v16;
      }
      v16 = (__int64 *)*v16;
    }
    while ( !*((_BYTE *)v16 + 25) );
  }
  if ( *((_BYTE *)v15 + 25) || ProcessorNumber < *((_DWORD *)v15 + 8) )
  {
    if ( this[14] == (__int64 *)0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    pPropertyData.PropertyName = (ULONGLONG)(this + 13);
    *(_QWORD *)&pPropertyData.ArrayIndex = 0;
    v67 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    v103 = (__int64)&v105;
    ____0AEBK__Z__V___pair___CBK_K_std__QEAA_Upiecewise_construct_t_1_V__tuple_AEBK_1_V__tuple___V_1__Z(
      v67 + 32,
      v68,
      &v103);
    *v15 = (__int64)v12;
    v15[1] = (__int64)v12;
    v15[2] = (__int64)v12;
    *((_WORD *)v15 + 12) = 0;
    this[14] = (__int64 *)((char *)this[14] + 1);
    v69 = *v10;
    v15[1] = (__int64)v13;
    if ( v17 == v69 )
    {
      *v69 = (__int64)v15;
      v69[1] = (__int64)v15;
      v69[2] = (__int64)v15;
      *((_BYTE *)v15 + 24) = 1;
      goto LABEL_25;
    }
    if ( v14 )
    {
      *v13 = (__int64)v15;
      if ( v17 == (__int64 *)*v69 )
        *v69 = (__int64)v15;
    }
    else
    {
      v13[2] = (__int64)v15;
      if ( v17 == (__int64 *)v69[2] )
        v69[2] = (__int64)v15;
    }
    v70 = v15;
    if ( *(_BYTE *)(v15[1] + 24) )
    {
LABEL_133:
      *(_BYTE *)(v69[1] + 24) = 1;
      goto LABEL_25;
    }
    while ( 1 )
    {
      v71 = v70[1];
      v72 = *(__int64 **)(v71 + 8);
      v73 = *v72;
      if ( v71 == *v72 )
      {
        v74 = v72[2];
        if ( !*(_BYTE *)(v74 + 24) )
        {
          *(_BYTE *)(v71 + 24) = 1;
          *(_BYTE *)(v74 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v70[1] + 8LL) + 24LL) = 0;
          v70 = *(_QWORD **)(v70[1] + 8LL);
          goto LABEL_167;
        }
        v75 = *(_QWORD **)(v71 + 16);
        if ( v70 == v75 )
        {
          v70 = (_QWORD *)v70[1];
          *(_QWORD *)(v71 + 16) = *v75;
          if ( !*(_BYTE *)(*v75 + 25LL) )
            *(_QWORD *)(*v75 + 8LL) = v71;
          v75[1] = *(_QWORD *)(v71 + 8);
          if ( v71 == (*v10)[1] )
          {
            (*v10)[1] = (__int64)v75;
          }
          else
          {
            v76 = *(_QWORD **)(v71 + 8);
            if ( v71 == *v76 )
              *v76 = v75;
            else
              v76[2] = v75;
          }
          *v75 = v71;
          *(_QWORD *)(v71 + 8) = v75;
        }
        *(_BYTE *)(v70[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(v70[1] + 8LL) + 24LL) = 0;
        v77 = *(_QWORD **)(v70[1] + 8LL);
        v78 = (_QWORD *)*v77;
        *v77 = *(_QWORD *)(*v77 + 16LL);
        v79 = v78[2];
        if ( !*(_BYTE *)(v79 + 25) )
          *(_QWORD *)(v79 + 8) = v77;
        v78[1] = v77[1];
        if ( v77 == (_QWORD *)(*v10)[1] )
        {
          (*v10)[1] = (__int64)v78;
          v78[2] = v77;
        }
        else
        {
          v80 = (_QWORD *)v77[1];
          if ( v77 == (_QWORD *)v80[2] )
            v80[2] = v78;
          else
            *v80 = v78;
          v78[2] = v77;
        }
      }
      else
      {
        if ( !*(_BYTE *)(v73 + 24) )
        {
          *(_BYTE *)(v71 + 24) = 1;
          *(_BYTE *)(v73 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v70[1] + 8LL) + 24LL) = 0;
          v70 = *(_QWORD **)(v70[1] + 8LL);
          goto LABEL_167;
        }
        v81 = *(_QWORD **)v71;
        if ( v70 == *(_QWORD **)v71 )
        {
          v70 = (_QWORD *)v70[1];
          *(_QWORD *)v71 = v81[2];
          v82 = v81[2];
          if ( !*(_BYTE *)(v82 + 25) )
            *(_QWORD *)(v82 + 8) = v71;
          v81[1] = *(_QWORD *)(v71 + 8);
          if ( v71 == (*v10)[1] )
          {
            (*v10)[1] = (__int64)v81;
          }
          else
          {
            v83 = *(_QWORD **)(v71 + 8);
            if ( v71 == v83[2] )
              v83[2] = v81;
            else
              *v83 = v81;
          }
          v81[2] = v71;
          *(_QWORD *)(v71 + 8) = v81;
        }
        *(_BYTE *)(v70[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(v70[1] + 8LL) + 24LL) = 0;
        v77 = *(_QWORD **)(v70[1] + 8LL);
        v78 = (_QWORD *)v77[2];
        v77[2] = *v78;
        if ( !*(_BYTE *)(*v78 + 25LL) )
          *(_QWORD *)(*v78 + 8LL) = v77;
        v78[1] = v77[1];
        if ( v77 == (_QWORD *)(*v10)[1] )
        {
          (*v10)[1] = (__int64)v78;
        }
        else
        {
          v84 = (_QWORD *)v77[1];
          if ( v77 == (_QWORD *)*v84 )
            *v84 = v78;
          else
            v84[2] = v78;
        }
        *v78 = v77;
      }
      v77[1] = v78;
LABEL_167:
      if ( *(_BYTE *)(v70[1] + 24LL) )
        goto LABEL_133;
    }
  }
LABEL_25:
  v18 = (__int64 *)v15[5];
  TimeStamp = a2->EventHeader.TimeStamp;
  if ( !v18 )
    v18 = this[21];
  v20 = *((unsigned int *)this + 10);
  if ( 10 * (TimeStamp.QuadPart - (__int64)v18) > (unsigned int)(11 * v20) )
    v18 = (__int64 *)(TimeStamp.QuadPart - v20);
  v21 = a2->BufferContext.ProcessorNumber;
  v106 = v21;
  v22 = *v10;
  v23 = (__int64 *)(*v10)[1];
  v24 = 0;
  pPropertyData.Reserved = 0;
  v25 = v22;
  v26 = v23;
  if ( *((_BYTE *)v23 + 25) )
  {
    v27 = v23;
  }
  else
  {
    do
    {
      v27 = v26;
      v23 = v26;
      if ( *((_DWORD *)v26 + 8) < v21 )
      {
        v24 = 0;
        v26 += 2;
      }
      else
      {
        v24 = 1;
        v25 = v26;
      }
      v26 = (__int64 *)*v26;
    }
    while ( !*((_BYTE *)v26 + 25) );
  }
  if ( *((_BYTE *)v25 + 25) || v21 < *((_DWORD *)v25 + 8) )
  {
    if ( v10[1] == (__int64 *)0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    pPropertyData.PropertyName = (ULONGLONG)v10;
    *(_QWORD *)&pPropertyData.ArrayIndex = 0;
    v85 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    v103 = (__int64)&v106;
    ____0AEBK__Z__V___pair___CBK_K_std__QEAA_Upiecewise_construct_t_1_V__tuple_AEBK_1_V__tuple___V_1__Z(
      v85 + 32,
      v86,
      &v103);
    *v25 = (__int64)v22;
    v25[1] = (__int64)v22;
    v25[2] = (__int64)v22;
    *((_WORD *)v25 + 12) = 0;
    v10[1] = (__int64 *)((char *)v10[1] + 1);
    v87 = *v10;
    v25[1] = (__int64)v23;
    if ( v27 == v87 )
    {
      *v87 = (__int64)v25;
      v87[1] = (__int64)v25;
      v87[2] = (__int64)v25;
      *((_BYTE *)v25 + 24) = 1;
      goto LABEL_35;
    }
    if ( v24 )
    {
      *v23 = (__int64)v25;
      if ( v27 == (__int64 *)*v87 )
        *v87 = (__int64)v25;
    }
    else
    {
      v23[2] = (__int64)v25;
      if ( v27 == (__int64 *)v87[2] )
        v87[2] = (__int64)v25;
    }
    v88 = v25;
    if ( *(_BYTE *)(v25[1] + 24) )
    {
LABEL_182:
      *(_BYTE *)(v87[1] + 24) = 1;
      goto LABEL_35;
    }
    while ( 1 )
    {
      v89 = v88[1];
      v90 = *(__int64 **)(v89 + 8);
      v91 = *v90;
      if ( v89 == *v90 )
      {
        v92 = v90[2];
        if ( !*(_BYTE *)(v92 + 24) )
        {
          *(_BYTE *)(v89 + 24) = 1;
          *(_BYTE *)(v92 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v88[1] + 8LL) + 24LL) = 0;
          v88 = *(_QWORD **)(v88[1] + 8LL);
          goto LABEL_216;
        }
        v93 = *(_QWORD **)(v89 + 16);
        if ( v88 == v93 )
        {
          v88 = (_QWORD *)v88[1];
          *(_QWORD *)(v89 + 16) = *v93;
          if ( !*(_BYTE *)(*v93 + 25LL) )
            *(_QWORD *)(*v93 + 8LL) = v89;
          v93[1] = *(_QWORD *)(v89 + 8);
          if ( v89 == (*v10)[1] )
          {
            (*v10)[1] = (__int64)v93;
          }
          else
          {
            v94 = *(_QWORD **)(v89 + 8);
            if ( v89 == *v94 )
              *v94 = v93;
            else
              v94[2] = v93;
          }
          *v93 = v89;
          *(_QWORD *)(v89 + 8) = v93;
        }
        *(_BYTE *)(v88[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(v88[1] + 8LL) + 24LL) = 0;
        v95 = *(_QWORD **)(v88[1] + 8LL);
        v96 = (_QWORD *)*v95;
        *v95 = *(_QWORD *)(*v95 + 16LL);
        v97 = v96[2];
        if ( !*(_BYTE *)(v97 + 25) )
          *(_QWORD *)(v97 + 8) = v95;
        v96[1] = v95[1];
        if ( v95 == (_QWORD *)(*v10)[1] )
        {
          (*v10)[1] = (__int64)v96;
          v96[2] = v95;
        }
        else
        {
          v98 = (_QWORD *)v95[1];
          if ( v95 == (_QWORD *)v98[2] )
            v98[2] = v96;
          else
            *v98 = v96;
          v96[2] = v95;
        }
      }
      else
      {
        if ( !*(_BYTE *)(v91 + 24) )
        {
          *(_BYTE *)(v89 + 24) = 1;
          *(_BYTE *)(v91 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(v88[1] + 8LL) + 24LL) = 0;
          v88 = *(_QWORD **)(v88[1] + 8LL);
          goto LABEL_216;
        }
        v99 = *(_QWORD **)v89;
        if ( v88 == *(_QWORD **)v89 )
        {
          v88 = (_QWORD *)v88[1];
          *(_QWORD *)v89 = v99[2];
          v100 = v99[2];
          if ( !*(_BYTE *)(v100 + 25) )
            *(_QWORD *)(v100 + 8) = v89;
          v99[1] = *(_QWORD *)(v89 + 8);
          if ( v89 == (*v10)[1] )
          {
            (*v10)[1] = (__int64)v99;
          }
          else
          {
            v101 = *(_QWORD **)(v89 + 8);
            if ( v89 == v101[2] )
              v101[2] = v99;
            else
              *v101 = v99;
          }
          v99[2] = v89;
          *(_QWORD *)(v89 + 8) = v99;
        }
        *(_BYTE *)(v88[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(v88[1] + 8LL) + 24LL) = 0;
        v95 = *(_QWORD **)(v88[1] + 8LL);
        v96 = (_QWORD *)v95[2];
        v95[2] = *v96;
        if ( !*(_BYTE *)(*v96 + 25LL) )
          *(_QWORD *)(*v96 + 8LL) = v95;
        v96[1] = v95[1];
        if ( v95 == (_QWORD *)(*v10)[1] )
        {
          (*v10)[1] = (__int64)v96;
        }
        else
        {
          v102 = (_QWORD *)v95[1];
          if ( v95 == (_QWORD *)*v102 )
            *v102 = v96;
          else
            v102[2] = v96;
        }
        *v96 = v95;
      }
      v95[1] = v96;
LABEL_216:
      if ( *(_BYTE *)(v88[1] + 24LL) )
        goto LABEL_182;
    }
  }
LABEL_35:
  v25[5] = TimeStamp.QuadPart;
  v28 = TimeStamp.QuadPart - (_QWORD)v18;
  v29 = 0;
  if ( v28 >= 0 )
    v29 = v28;
  v103 = v29;
  v30 = v107;
  v31 = (_QWORD *)(*((_QWORD *)v107 + 6) + 104LL * *((unsigned int *)v109 + 8));
  v32 = *(_QWORD *)pBuffer;
  v31[5] += v29;
  for ( j = (unsigned __int64 *)v31[9]; ; j += 3 )
  {
    if ( j == (unsigned __int64 *)v31[10] )
      goto LABEL_46;
    if ( *j <= v32 && *j + j[1] > v32 )
      break;
  }
  pPropertyData.PropertyName = v31[7];
  v43 = *(_QWORD *)(pPropertyData.PropertyName + 8);
  v44 = 0;
  HIDWORD(v110) = 0;
  PropertyName = pPropertyData.PropertyName;
  v46 = v43;
  if ( *(_BYTE *)(v43 + 25) )
  {
    v47 = (ULONGLONG *)v43;
  }
  else
  {
    do
    {
      v47 = (ULONGLONG *)v46;
      v43 = v46;
      if ( *(_DWORD *)(v46 + 32) < *((_DWORD *)j + 4) )
      {
        v44 = 0;
        v46 += 16LL;
      }
      else
      {
        v44 = 1;
        PropertyName = v46;
      }
      v46 = *(_QWORD *)v46;
    }
    while ( !*(_BYTE *)(v46 + 25) );
  }
  if ( *(_BYTE *)(PropertyName + 25) || *((_DWORD *)j + 4) < *(_DWORD *)(PropertyName + 32) )
  {
    if ( v31[8] == 0x555555555555555LL )
LABEL_59:
      std::_Xlength_error("map/set too long");
    v109 = v31 + 7;
    v110 = 0;
    v48 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    v109 = (__int64 *)(j + 2);
    ____0AEBK__Z__V___pair___CBK_K_std__QEAA_Upiecewise_construct_t_1_V__tuple_AEBK_1_V__tuple___V_1__Z(
      v48 + 32,
      v49,
      &v109);
    v50 = pPropertyData.PropertyName;
    *(_QWORD *)PropertyName = pPropertyData.PropertyName;
    *(_QWORD *)(PropertyName + 8) = v50;
    *(_QWORD *)(PropertyName + 16) = v50;
    *(_WORD *)(PropertyName + 24) = 0;
    ++v31[8];
    v51 = (ULONGLONG *)v31[7];
    *(_QWORD *)(PropertyName + 8) = v43;
    if ( v47 == v51 )
    {
      *v51 = PropertyName;
      v51[1] = PropertyName;
      v51[2] = PropertyName;
      *(_BYTE *)(PropertyName + 24) = 1;
    }
    else
    {
      if ( v44 )
      {
        *(_QWORD *)v43 = PropertyName;
        if ( v47 == (ULONGLONG *)*v51 )
          *v51 = PropertyName;
      }
      else
      {
        *(_QWORD *)(v43 + 16) = PropertyName;
        if ( v47 == (ULONGLONG *)v51[2] )
          v51[2] = PropertyName;
      }
      v52 = PropertyName;
      while ( !*(_BYTE *)(*(_QWORD *)(v52 + 8) + 24LL) )
      {
        v53 = *(_QWORD *)(v52 + 8);
        v54 = *(__int64 **)(v53 + 8);
        v55 = *v54;
        if ( v53 == *v54 )
        {
          v56 = v54[2];
          if ( *(_BYTE *)(v56 + 24) )
          {
            if ( v52 == *(_QWORD *)(v53 + 16) )
              std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::vector<CustomDatum *>>>>::_Lrotate(
                v31 + 7,
                v53);
            *(_BYTE *)(*(_QWORD *)(v52 + 8) + 24LL) = 1;
            *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v52 + 8) + 8LL) + 24LL) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned __int64>>>::_Rrotate(
              v31 + 7,
              *(_QWORD *)(*(_QWORD *)(v52 + 8) + 8LL));
          }
          else
          {
            *(_BYTE *)(v53 + 24) = 1;
            *(_BYTE *)(v56 + 24) = 1;
            *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v52 + 8) + 8LL) + 24LL) = 0;
            v52 = *(_QWORD *)(*(_QWORD *)(v52 + 8) + 8LL);
          }
        }
        else if ( *(_BYTE *)(v55 + 24) )
        {
          if ( v52 == *(_QWORD *)v53 )
            std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned __int64>>>::_Rrotate(
              v31 + 7,
              v53);
          *(_BYTE *)(*(_QWORD *)(v52 + 8) + 24LL) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v52 + 8) + 8LL) + 24LL) = 0;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::vector<CustomDatum *>>>>::_Lrotate(
            v31 + 7,
            *(_QWORD *)(*(_QWORD *)(v52 + 8) + 8LL));
        }
        else
        {
          *(_BYTE *)(v53 + 24) = 1;
          *(_BYTE *)(v55 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v52 + 8) + 8LL) + 24LL) = 0;
          v52 = *(_QWORD *)(*(_QWORD *)(v52 + 8) + 8LL);
        }
      }
      *(_BYTE *)(v51[1] + 24) = 1;
    }
    v30 = v107;
  }
  v60 = (_DWORD *)v103;
  *(_QWORD *)(PropertyName + 40) += v103;
  v29 = (__int64)v60;
LABEL_46:
  if ( j == (unsigned __int64 *)v31[10] )
  {
    v34 = (__int64 *)v31[12];
    if ( !v34 )
      goto LABEL_89;
    v35 = *v34;
    v36 = v34[1];
    while ( 1 )
    {
      if ( v35 == v36 )
        goto LABEL_88;
      if ( *(_QWORD *)v35 <= v32 && *(_QWORD *)(v35 + 8) + *(_QWORD *)v35 > v32 )
        break;
      v35 += 24;
    }
    v37 = (__int64 *)v31[7];
    v38 = (__int64 *)v37[1];
    v39 = 0;
    pPropertyData.Reserved = 0;
    v40 = v37;
    v41 = v38;
    if ( *((_BYTE *)v38 + 25) )
    {
      v42 = v38;
    }
    else
    {
      do
      {
        v42 = v41;
        v38 = v41;
        if ( *((_DWORD *)v41 + 8) < *(_DWORD *)(v35 + 16) )
        {
          v39 = 0;
          v41 += 2;
        }
        else
        {
          v39 = 1;
          v40 = v41;
        }
        v41 = (__int64 *)*v41;
      }
      while ( !*((_BYTE *)v41 + 25) );
    }
    if ( *((_BYTE *)v40 + 25) || *(_DWORD *)(v35 + 16) < *((_DWORD *)v40 + 8) )
    {
      if ( v31[8] == 0x555555555555555LL )
        goto LABEL_59;
      pPropertyData.PropertyName = (ULONGLONG)(v31 + 7);
      *(_QWORD *)&pPropertyData.ArrayIndex = 0;
      v61 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
      pPropertyData.PropertyName = v35 + 16;
      ____0AEBK__Z__V___pair___CBK_K_std__QEAA_Upiecewise_construct_t_1_V__tuple_AEBK_1_V__tuple___V_1__Z(
        v61 + 32,
        v62,
        &pPropertyData);
      *v40 = (__int64)v37;
      v40[1] = (__int64)v37;
      v40[2] = (__int64)v37;
      *((_WORD *)v40 + 12) = 0;
      ++v31[8];
      v58 = (__int64 *)v31[7];
      v40[1] = (__int64)v38;
      if ( v42 == v58 )
      {
        *v58 = (__int64)v40;
        v58[1] = (__int64)v40;
        v58[2] = (__int64)v40;
        *((_BYTE *)v40 + 24) = 1;
      }
      else
      {
        if ( v39 )
        {
          *v38 = (__int64)v40;
          if ( v42 == (__int64 *)*v58 )
            *v58 = (__int64)v40;
        }
        else
        {
          v38[2] = (__int64)v40;
          if ( v42 == (__int64 *)v58[2] )
            v58[2] = (__int64)v40;
        }
        v57 = v40;
        while ( !*(_BYTE *)(v57[1] + 24) )
        {
          v63 = v57[1];
          v64 = *(__int64 **)(v63 + 8);
          v65 = *v64;
          if ( v63 == *v64 )
          {
            v66 = v64[2];
            if ( *(_BYTE *)(v66 + 24) )
            {
              if ( v57 == *(__int64 **)(v63 + 16) )
                std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::vector<CustomDatum *>>>>::_Lrotate(
                  v31 + 7,
                  v63);
              *(_BYTE *)(v57[1] + 24) = 1;
              *(_BYTE *)(*(_QWORD *)(v57[1] + 8) + 24LL) = 0;
              std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned __int64>>>::_Rrotate(
                v31 + 7,
                *(_QWORD *)(v57[1] + 8));
            }
            else
            {
              *(_BYTE *)(v63 + 24) = 1;
              *(_BYTE *)(v66 + 24) = 1;
              *(_BYTE *)(*(_QWORD *)(v57[1] + 8) + 24LL) = 0;
              v57 = *(__int64 **)(v57[1] + 8);
            }
          }
          else if ( *(_BYTE *)(v65 + 24) )
          {
            if ( v57 == *(__int64 **)v63 )
              std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned __int64>>>::_Rrotate(
                v31 + 7,
                v63);
            *(_BYTE *)(v57[1] + 24) = 1;
            *(_BYTE *)(*(_QWORD *)(v57[1] + 8) + 24LL) = 0;
            std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::vector<CustomDatum *>>>>::_Lrotate(
              v31 + 7,
              *(_QWORD *)(v57[1] + 8));
          }
          else
          {
            *(_BYTE *)(v63 + 24) = 1;
            *(_BYTE *)(v65 + 24) = 1;
            *(_BYTE *)(*(_QWORD *)(v57[1] + 8) + 24LL) = 0;
            v57 = *(__int64 **)(v57[1] + 8);
          }
        }
        *(_BYTE *)(v58[1] + 24) = 1;
      }
      v30 = v107;
    }
    v59 = (_DWORD *)v103;
    v40[5] += v103;
    v29 = (__int64)v59;
LABEL_88:
    if ( v35 == *(_QWORD *)(v31[12] + 8LL) )
LABEL_89:
      v31[6] += v29;
  }
  *((_DWORD *)v30 + 66) |= 8u;
}

```

## disassembly

```asm
0x180018ce0  mov     [rsp-8+arg_10], rbx
0x180018ce5  push    rbp
0x180018ce6  push    rsi
0x180018ce7  push    rdi
0x180018ce8  push    r12
0x180018cea  push    r13
0x180018cec  push    r14
0x180018cee  push    r15
0x180018cf0  lea     rbp, [rsp-27h]
0x180018cf5  sub     rsp, 0A0h
0x180018cfc  mov     rax, cs:__security_cookie
0x180018d03  xor     rax, rsp
0x180018d06  mov     [rbp+57h+var_38], rax
0x180018d0a  mov     r15, rdx
0x180018d0d  mov     r13, rcx
0x180018d10  mov     [rbp+57h+var_78], rcx
0x180018d14  xor     ebx, ebx
0x180018d16  mov     qword ptr [rbp+57h+var_70], rbx
0x180018d1a  mov     dword ptr [rbp+57h+var_88], ebx
0x180018d1d  cmp     [rcx+24h], bl
0x180018d20  jz      loc_180018FCB
0x180018d26  mov     [rbp+57h+var_50.Reserved], ebx
0x180018d29  mov     [rbp+57h+var_50.ArrayIndex], 0FFFFFFFFh
0x180018d30  lea     rax, aInstructionpoi; "InstructionPointer"
0x180018d37  mov     [rbp+57h+var_50.PropertyName], rax
0x180018d3b  lea     rax, [rbp+57h+var_70]
0x180018d3f  mov     [rsp+0D0h+pBuffer], rax; pBuffer
0x180018d44  mov     [rsp+0D0h+BufferSize], 8; BufferSize
0x180018d4c  lea     rax, [rbp+57h+var_50]
0x180018d50  mov     [rsp+0D0h+pPropertyData], rax; pPropertyData
0x180018d55  mov     r9d, 1; PropertyDataCount
0x180018d5b  xor     r8d, r8d; pTdhContext
0x180018d5e  xor     edx, edx; TdhContextCount
0x180018d60  mov     rcx, r15; pEvent
0x180018d63  call    cs:__imp_TdhGetProperty
0x180018d69  test    eax, eax
0x180018d6b  jnz     loc_180018FCB
0x180018d71  mov     [rbp+57h+var_50.Reserved], ebx
0x180018d74  mov     [rbp+57h+var_50.ArrayIndex], 0FFFFFFFFh
0x180018d7b  lea     rax, aThreadid; "ThreadId"
0x180018d82  mov     [rbp+57h+var_50.PropertyName], rax
0x180018d86  lea     rax, [rbp+57h+var_88]
0x180018d8a  mov     [rsp+0D0h+pBuffer], rax; pBuffer
0x180018d8f  mov     [rsp+0D0h+BufferSize], 4; BufferSize
0x180018d97  lea     rax, [rbp+57h+var_50]
0x180018d9b  mov     [rsp+0D0h+pPropertyData], rax; pPropertyData
0x180018da0  mov     r9d, 1; PropertyDataCount
0x180018da6  xor     r8d, r8d; pTdhContext
0x180018da9  xor     edx, edx; TdhContextCount
0x180018dab  mov     rcx, r15; pEvent
0x180018dae  call    cs:__imp_TdhGetProperty
0x180018db4  test    eax, eax
0x180018db6  jnz     loc_180018FCB
0x180018dbc  mov     r8, [r13+58h]
0x180018dc0  mov     rax, [r8+8]
0x180018dc4  xor     ecx, ecx
0x180018dc6  mov     [rbp+57h+var_50.Reserved], ecx
0x180018dc9  mov     rdx, r8
0x180018dcc  mov     ecx, dword ptr [rbp+57h+var_88]
0x180018dcf  cmp     [rax+19h], bl
0x180018dd2  jnz     short loc_180018DE9
0x180018dd4  cmp     [rax+1Ch], ecx
0x180018dd7  jnb     loc_180018FB3
0x180018ddd  add     rax, 10h
0x180018de1  mov     rax, [rax]
0x180018de4  cmp     [rax+19h], bl
0x180018de7  jz      short loc_180018DD4
0x180018de9  cmp     [rdx+19h], bl
0x180018dec  jnz     loc_180018FCB
0x180018df2  cmp     ecx, [rdx+1Ch]
0x180018df5  jb      loc_180018FCB
0x180018dfb  cmp     rdx, r8
0x180018dfe  jz      loc_180018FCB
0x180018e04  mov     r8, [r13+48h]
0x180018e08  mov     rax, [r8+8]
0x180018e0c  xor     ecx, ecx
0x180018e0e  mov     [rbp+57h+var_50.Reserved], ecx
0x180018e11  mov     r9, r8
0x180018e14  mov     [rbp+57h+var_68], r8
0x180018e18  cmp     [rax+19h], cl
0x180018e1b  jnz     short loc_180018E39
0x180018e1d  mov     ecx, [rdx+20h]
0x180018e20  cmp     [rax+1Ch], ecx
0x180018e23  jnb     loc_180018FBB
0x180018e29  add     rax, 10h
0x180018e2d  mov     rax, [rax]
0x180018e30  cmp     [rax+19h], bl
0x180018e33  jz      short loc_180018E20
0x180018e35  mov     [rbp+57h+var_68], r9
0x180018e39  cmp     [r9+19h], bl
0x180018e3d  jnz     loc_180018FCB
0x180018e43  mov     eax, [r9+1Ch]
0x180018e47  cmp     [rdx+20h], eax
0x180018e4a  jb      loc_180018FCB
0x180018e50  cmp     r9, r8
0x180018e53  jz      loc_180018FCB
0x180018e59  lea     r12, [r13+68h]
0x180018e5d  movzx   ecx, byte ptr [r15+50h]
0x180018e62  mov     [rbp+57h+var_84], ecx
0x180018e65  mov     rsi, [r12]
0x180018e69  mov     rbx, [rsi+8]
0x180018e6d  xor     r11d, r11d
0x180018e70  mov     r14d, r11d
0x180018e73  xor     eax, eax
0x180018e75  mov     [rbp+57h+var_50.Reserved], eax
0x180018e78  mov     r9, rsi
0x180018e7b  mov     rax, rbx
0x180018e7e  cmp     [rbx+19h], r11b
0x180018e82  jnz     loc_180019328
0x180018e88  mov     rdi, rax
0x180018e8b  mov     rbx, rax
0x180018e8e  cmp     [rax+20h], ecx
0x180018e91  jb      loc_1800190AC
0x180018e97  mov     r14d, 1
0x180018e9d  mov     r9, rax
0x180018ea0  mov     rax, [rax]
0x180018ea3  cmp     [rax+19h], r11b
0x180018ea7  jz      short loc_180018E88
0x180018ea9  mov     r10, 555555555555555h
0x180018eb3  cmp     [r9+19h], r11b
0x180018eb7  jnz     loc_180019453
0x180018ebd  cmp     ecx, [r9+20h]
0x180018ec1  jb      loc_180019453
0x180018ec7  mov     rsi, [r9+28h]
0x180018ecb  mov     rdi, [r15+10h]
0x180018ecf  test    rsi, rsi
0x180018ed2  jnz     short loc_180018EDB
0x180018ed4  mov     rsi, [r13+0A8h]
0x180018edb  mov     r8d, [r13+28h]
0x180018edf  mov     rax, rdi
0x180018ee2  sub     rax, rsi
0x180018ee5  lea     rdx, [rax+rax*4]
0x180018ee9  add     rdx, rdx
0x180018eec  imul    ecx, r8d, 0Bh
0x180018ef0  cmp     rdx, rcx
0x180018ef3  jle     short loc_180018EFB
0x180018ef5  mov     rsi, rdi
0x180018ef8  sub     rsi, r8
0x180018efb  movzx   ecx, byte ptr [r15+50h]
0x180018f00  mov     [rbp+57h+var_80], ecx
0x180018f03  mov     r13, [r12]
0x180018f07  mov     rbx, [r13+8]
0x180018f0b  mov     r15d, r11d
0x180018f0e  xor     eax, eax
0x180018f10  mov     [rbp+57h+var_50.Reserved], eax
0x180018f13  mov     r9, r13
0x180018f16  mov     rax, rbx
0x180018f19  cmp     byte ptr [rbx+19h], 0
0x180018f1d  jnz     loc_180019330
0x180018f23  mov     r14, rax
0x180018f26  mov     rbx, rax
0x180018f29  cmp     [rax+20h], ecx
0x180018f2c  jb      loc_1800190B8
0x180018f32  mov     r15d, 1
0x180018f38  mov     r9, rax
0x180018f3b  mov     rax, [rax]
0x180018f3e  cmp     byte ptr [rax+19h], 0
0x180018f42  jz      short loc_180018F23
0x180018f44  cmp     byte ptr [r9+19h], 0
0x180018f49  jnz     loc_18001946C
0x180018f4f  cmp     ecx, [r9+20h]
0x180018f53  jb      loc_18001946C
0x180018f59  mov     [r9+28h], rdi
0x180018f5d  sub     rdi, rsi
0x180018f60  mov     r9, r11
0x180018f63  cmovns  r9, rdi
0x180018f67  mov     [rbp+57h+var_90], r9
0x180018f6b  mov     rax, [rbp+57h+var_68]
0x180018f6f  mov     eax, [rax+20h]
0x180018f72  imul    r13, rax, 68h ; 'h'
0x180018f76  mov     r10, [rbp+57h+var_78]
0x180018f7a  add     r13, [r10+30h]
0x180018f7e  mov     rdi, qword ptr [rbp+57h+var_70]
0x180018f82  add     [r13+28h], r9
0x180018f86  mov     rbx, [r13+48h]
0x180018f8a  mov     r8, [r13+50h]
0x180018f8e  xchg    ax, ax
0x180018f90  cmp     rbx, r8
0x180018f93  jz      short loc_180018FF2
0x180018f95  mov     rax, [rbx]
0x180018f98  cmp     rax, rdi
0x180018f9b  ja      short loc_180018FAD
0x180018f9d  mov     rdx, [rbx+8]
0x180018fa1  add     rdx, rax
0x180018fa4  cmp     rdx, rdi
0x180018fa7  ja      loc_1800190C4
0x180018fad  add     rbx, 18h
0x180018fb1  jmp     short loc_180018F90
0x180018fb3  mov     rdx, rax
0x180018fb6  jmp     loc_180018DE1
0x180018fbb  mov     r9, rax
0x180018fbe  jmp     loc_180018E2D
0x180018fc3  or      dword ptr [r10+108h], 8
0x180018fcb  mov     rcx, [rbp+57h+var_38]
0x180018fcf  xor     rcx, rsp; StackCookie
0x180018fd2  call    __security_check_cookie
0x180018fd7  mov     rbx, [rsp+0D0h+arg_10]
0x180018fdf  add     rsp, 0A0h
0x180018fe6  pop     r15
0x180018fe8  pop     r14
0x180018fea  pop     r13
0x180018fec  pop     r12
0x180018fee  pop     rdi
0x180018fef  pop     rsi
0x180018ff0  pop     rbp
0x180018ff1  retn
0x180018ff2  cmp     rbx, [r13+50h]
0x180018ff6  jnz     short loc_180018FC3
0x180018ff8  mov     rdx, [r13+60h]
0x180018ffc  test    rdx, rdx
0x180018fff  jz      loc_18001928F
0x180019005  mov     rbx, [rdx]
0x180019008  mov     rdx, [rdx+8]
0x18001900c  cmp     rbx, rdx
0x18001900f  jz      loc_180019281
0x180019015  mov     rcx, [rbx]
0x180019018  cmp     rcx, rdi
0x18001901b  ja      loc_1800192A4
0x180019021  add     rcx, [rbx+8]
0x180019025  cmp     rcx, rdi
0x180019028  jbe     loc_1800192A4
0x18001902e  lea     r14, [r13+38h]
0x180019032  mov     r12, [r14]
0x180019035  mov     rdi, [r12+8]
0x18001903a  mov     r15d, r11d
0x18001903d  xor     eax, eax
0x18001903f  mov     [rbp+57h+var_50.Reserved], eax
0x180019042  mov     r9, r12
0x180019045  mov     rax, rdi
0x180019048  cmp     byte ptr [rdi+19h], 0
0x18001904c  jnz     loc_180019318
0x180019052  mov     ecx, [rbx+10h]
0x180019055  mov     rsi, rax
0x180019058  mov     rdi, rax
0x18001905b  cmp     [rax+20h], ecx
0x18001905e  jb      loc_180019298
0x180019064  mov     r15d, 1
0x18001906a  mov     r9, rax
0x18001906d  mov     rax, [rax]
0x180019070  cmp     byte ptr [rax+19h], 0
0x180019074  jz      short loc_180019055
0x180019076  cmp     byte ptr [r9+19h], 0
0x18001907b  jnz     short loc_18001908A
0x18001907d  mov     eax, [r9+20h]
0x180019081  cmp     [rbx+10h], eax
0x180019084  jnb     loc_180019276
0x18001908a  mov     rax, 555555555555555h
0x180019094  cmp     [r14+8], rax
0x180019098  jnz     loc_180019338
0x18001909e  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800190a5  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800190ac  mov     r14d, r11d
0x1800190af  add     rax, 10h
0x1800190b3  jmp     loc_180018EA0
0x1800190b8  mov     r15d, r11d
0x1800190bb  add     rax, 10h
0x1800190bf  jmp     loc_180018F3B
0x1800190c4  lea     r12, [r13+38h]
0x1800190c8  mov     rax, [r12]
0x1800190cc  mov     [rbp+57h+var_50.PropertyName], rax
0x1800190d0  mov     rsi, [rax+8]
0x1800190d4  mov     r15d, r11d
0x1800190d7  xor     ecx, ecx
0x1800190d9  mov     [rbp+57h+var_5C], ecx
0x1800190dc  mov     r9, rax
0x1800190df  mov     rax, rsi
0x1800190e2  cmp     [rsi+19h], cl
0x1800190e5  jnz     loc_180019320
0x1800190eb  mov     ecx, [rbx+10h]
0x1800190ee  mov     r14, rax
0x1800190f1  mov     rsi, rax
0x1800190f4  cmp     [rax+20h], ecx
0x1800190f7  jb      loc_180019212
0x1800190fd  mov     r15d, 1
0x180019103  mov     r9, rax
0x180019106  mov     rax, [rax]
0x180019109  cmp     byte ptr [rax+19h], 0
0x18001910d  jz      short loc_1800190EE
0x18001910f  cmp     byte ptr [r9+19h], 0
0x180019114  jnz     short loc_180019123
0x180019116  mov     eax, [r9+20h]
0x18001911a  cmp     [rbx+10h], eax
0x18001911d  jnb     loc_180019308
0x180019123  mov     rax, 555555555555555h
0x18001912d  cmp     [r12+8], rax
0x180019132  jz      loc_18001909E
0x180019138  mov     [rbp+57h+var_68], r12
0x18001913c  mov     [rbp-9], r11
0x180019140  mov     ecx, 30h ; '0'
0x180019145  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001914a  mov     r9, rax
0x18001914d  lea     rax, [rbx+10h]
0x180019151  mov     [rbp+57h+var_68], rax
0x180019155  lea     rcx, [r9+20h]
0x180019159  lea     r8, [rbp+57h+var_68]
0x18001915d  call    ??$?0AEBK$$Z$$V@?$pair@$$CBK_K@std@@QEAA@Upiecewise_construct_t@1@V?$tuple@AEBK@1@V?$tuple@$$V@1@@Z
0x180019162  mov     rcx, [rbp+57h+var_50.PropertyName]
0x180019166  mov     [r9], rcx
0x180019169  mov     [r9+8], rcx
0x18001916d  mov     [r9+10h], rcx
  ... truncated ...
```
