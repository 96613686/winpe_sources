# CRunConsolidate::RunOperation(void)

- ea: `0x18000ae70`
- end: `0x18000c63c`
- name: `?RunOperation@CRunConsolidate@@UEAAJXZ`
- size: `6092`
- prototype: `__int64 __fastcall(CRunConsolidate *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18000ae70`
- `0x18000c644`
- `0x18000c700`
- `0x18000c794`
- `0x18000c848`
- `0x180013ae8`
- `0x18002acc4`
- `0x180038c3c`
- `0x180046494`
- `0x18004a92c`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000b82c`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000b82c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bb68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bb68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bb9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bbbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c18e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bb9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bbbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c18e`

## string_xrefs

- `0x18000b7ff`: `CDefragOperation::_OptimizeMoveForVolsnap`

## pseudocode

```c
// Hidden C++ exception states: #wind=46
__int64 __fastcall CRunConsolidate::RunOperation(CRunConsolidate *this)
{
  unsigned int v2; // r13d
  struct IRunnableThread *RunnableThread; // rbx
  __int64 v4; // r15
  int v5; // edi
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r14
  struct IFreeSpaceManager *v8; // rcx
  __int16 v9; // ax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  struct IFreeSpaceManager *v13; // rcx
  __int64 *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  struct IFreeSpaceManager *v18; // rcx
  unsigned __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, __int64, __int64 *); // rdi
  __int64 v21; // rdx
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *); // rdi
  __int64 v23; // r8
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rdi
  __int64 v25; // rdx
  __int16 v26; // ax
  unsigned int i; // esi
  unsigned int v28; // r14d
  __int64 v29; // rdx
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64 *); // rdi
  int v31; // esi
  unsigned int v32; // r13d
  __int64 v33; // rdx
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64 *); // rdi
  __int64 (__fastcall *v35)(__int64, _QWORD, __int64, __int64 *); // rax
  bool v36; // sf
  __int16 v37; // ax
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // rsi
  unsigned int v40; // r14d
  unsigned __int64 v41; // rsi
  __int64 v42; // r8
  unsigned int *v43; // r14
  __int64 v44; // rdx
  __int64 (__fastcall *v45)(__int64, __int64, __int64, __int64 *); // rax
  __int16 v46; // ax
  void *v47; // rcx
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v49; // rcx
  unsigned int v50; // edi
  bool v51; // cf
  __int64 (__fastcall *v52)(__int64, _QWORD, __int64 *, __int64 **); // rax
  bool v53; // sf
  __int64 v54; // rax
  unsigned int j; // esi
  __int64 v56; // rdx
  int v57; // eax
  LPVOID *v58; // rax
  void *v59; // rcx
  unsigned int *v60; // rdi
  void *v61; // rcx
  _QWORD *v62; // rax
  __int64 v63; // rdx
  __int64 (__fastcall *v64)(__int64, __int64, __int64 *, __int64 **); // rax
  __int64 v65; // rdx
  __int16 v66; // ax
  int v67; // eax
  bool v68; // sf
  void *v69; // rcx
  int v70; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v71; // [rsp+64h] [rbp-9Ch]
  __int16 v72; // [rsp+66h] [rbp-9Ah]
  __int64 *v73; // [rsp+98h] [rbp-68h] BYREF
  struct IFreeSpaceManager *v74; // [rsp+A0h] [rbp-60h] BYREF
  int v75; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v76; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v77; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v78; // [rsp+C0h] [rbp-40h] BYREF
  int v79; // [rsp+C4h] [rbp-3Ch] BYREF
  int v80; // [rsp+C8h] [rbp-38h] BYREF
  int v81; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int v82; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v83; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v84; // [rsp+E0h] [rbp-20h] BYREF
  int v85; // [rsp+E4h] [rbp-1Ch]
  __int64 v86; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v87; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v88; // [rsp+F8h] [rbp-8h] BYREF
  int v89; // [rsp+100h] [rbp+0h] BYREF
  int v90; // [rsp+104h] [rbp+4h] BYREF
  unsigned int v91; // [rsp+108h] [rbp+8h] BYREF
  int v92; // [rsp+10Ch] [rbp+Ch] BYREF
  int v93; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v94; // [rsp+114h] [rbp+14h]
  unsigned int v95; // [rsp+118h] [rbp+18h]
  unsigned __int64 v96; // [rsp+120h] [rbp+20h] BYREF
  char *v97; // [rsp+128h] [rbp+28h] BYREF
  LPVOID v98; // [rsp+130h] [rbp+30h]
  unsigned __int64 v99; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v100; // [rsp+148h] [rbp+48h]
  unsigned int v101; // [rsp+150h] [rbp+50h]
  int v102[3]; // [rsp+154h] [rbp+54h] BYREF
  LPVOID pv[2]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v104; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v105; // [rsp+178h] [rbp+78h]
  int v106; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v107; // [rsp+188h] [rbp+88h]
  unsigned __int64 v108; // [rsp+190h] [rbp+90h]
  int v109; // [rsp+198h] [rbp+98h] BYREF
  __int64 v110; // [rsp+19Ch] [rbp+9Ch]
  __int16 v111; // [rsp+1A4h] [rbp+A4h]
  const char *v112; // [rsp+1A8h] [rbp+A8h]
  __int128 v113; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v114; // [rsp+1C0h] [rbp+C0h]
  int v115; // [rsp+1C8h] [rbp+C8h]
  int v116; // [rsp+1D0h] [rbp+D0h]
  __int64 v117; // [rsp+1D8h] [rbp+D8h]
  struct IRunnableThread *v118; // [rsp+1E0h] [rbp+E0h]
  unsigned __int64 v119; // [rsp+1E8h] [rbp+E8h]
  _OWORD v120[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v121; // [rsp+210h] [rbp+110h]
  _OWORD v122[2]; // [rsp+218h] [rbp+118h] BYREF
  __int64 v123; // [rsp+238h] [rbp+138h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v70, "CRunConsolidate::RunOperation", 92, 1);
  v2 = 0;
  v117 = 0;
  v76 = 0;
  v77 = 0;
  v73 = 0;
  v74 = 0;
  RunnableThread = 0;
  v118 = 0;
  v83 = 0;
  v87 = 0;
  v86 = 0;
  v82 = 0;
  v78 = 0;
  memset(v120, 0, sizeof(v120));
  v121 = 0;
  memset(v122, 0, sizeof(v122));
  v123 = 0;
  v97 = 0;
  v96 = 0;
  v88 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v81 = 0;
  v75 = 0;
  v80 = 0;
  v84 = 0;
  v89 = 0;
  v102[0] = 0;
  v90 = 0;
  v106 = 0;
  v4 = *((_QWORD *)this + 93);
  if ( v4 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 8LL))(*((_QWORD *)this + 93));
  v117 = v4;
  if ( !v4 )
  {
    v5 = -2147467259;
    v70 = -2147467259;
    v72 = 151;
    goto LABEL_12;
  }
  v5 = CDefragOperation::_SetPhase(this, 2u);
  v70 = v5;
  if ( v5 < 0 )
  {
    v72 = 154;
    goto LABEL_12;
  }
  v71 = 154;
  RunnableThread = CDefragOperation::_GetRunnableThread(this);
  v118 = RunnableThread;
  v70 = 0;
  v71 = 158;
  v6 = *((_QWORD *)this + 96);
  v119 = v6;
  v7 = *((_QWORD *)this + 97);
  v104 = v7;
  v5 = (*(__int64 (__fastcall **)(__int64, int *, int *, int *, int *))(*(_QWORD *)v4 + 192LL))(
         v4,
         v102,
         &v89,
         &v90,
         &v106);
  v70 = v5;
  if ( v5 < 0 )
  {
    v72 = 164;
    goto LABEL_12;
  }
  v71 = 164;
  if ( v89 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 5) + 192LL))(*((_QWORD *)this + 5), &v80);
    v70 = v5;
    if ( v5 < 0 )
    {
      v72 = 169;
      goto LABEL_12;
    }
    v71 = 169;
    if ( v80 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v4 + 200LL))(v4, &v80);
      v70 = v5;
      if ( v5 < 0 )
      {
        v72 = 174;
        goto LABEL_12;
      }
      v71 = 174;
    }
  }
  if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v4 + 224LL))(v4) >= 0 )
  {
    v18 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v5 = CTieredFreeSpaceManager::CreateInstance(
           *((unsigned __int16 **)this + 87),
           *((_QWORD *)this + 18),
           *((_DWORD *)this + 38),
           &v74);
    v70 = v5;
    v9 = 182;
    if ( v5 < 0 )
    {
      v72 = 182;
      goto LABEL_12;
    }
  }
  else
  {
    v8 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v5 = CFreeSpaceManager::CreateInstance(*((unsigned __int16 **)this + 87), *((_QWORD *)this + 18), &v74);
    v70 = v5;
    v9 = 186;
    if ( v5 < 0 )
    {
      v72 = 186;
      goto LABEL_12;
    }
  }
  v71 = v9;
  v107 = 0;
  if ( v6 )
  {
    v107 = v6 - 1;
    v99 = 0;
    v100 = v6 - 1;
    v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, unsigned __int64 *))(*(_QWORD *)v74 + 48LL))(v74, &v99);
    v70 = v5;
    v2 = 0;
    if ( v5 < 0 )
    {
      v72 = 195;
      goto LABEL_12;
    }
    v71 = 195;
  }
  v108 = 0;
  v99 = 0;
  v19 = *((_QWORD *)this + 18) - 1LL;
  if ( v7 < v19 )
  {
    v108 = v7 + 1;
    v99 = v7 + 1;
    v100 = v19;
    v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, unsigned __int64 *))(*(_QWORD *)v74 + 48LL))(v74, &v99);
    v70 = v5;
    v2 = 0;
    if ( v5 < 0 )
    {
      v72 = 202;
      goto LABEL_12;
    }
    v99 = v19;
    v71 = 202;
  }
  if ( v90 && !*((_DWORD *)this + 196) )
  {
    pv[0] = *((LPVOID *)this + 22);
    pv[1] = *((LPVOID *)this + 21);
    v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, LPVOID *))(*(_QWORD *)v74 + 48LL))(v74, pv);
    v70 = v5;
    if ( v5 < 0 )
    {
      v72 = 212;
      goto LABEL_12;
    }
    v71 = 212;
  }
  v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v4 + 104LL);
  v21 = v83;
  if ( v83 )
  {
    v83 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v5 = v20(v4, 1, &v83);
  v70 = v5;
  if ( v5 < 0 )
  {
    v72 = 216;
    goto LABEL_12;
  }
  v71 = 216;
  v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v4 + 104LL);
  v23 = v87;
  if ( v87 )
  {
    v87 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v5 = v22(v4, 2, &v87);
  v70 = v5;
  if ( v5 < 0 )
  {
    v72 = 217;
    goto LABEL_12;
  }
  v71 = 217;
  v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v4 + 104LL);
  v25 = v86;
  if ( v86 )
  {
    v86 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v5 = v24(v4, 0, &v86);
  v70 = v5;
  if ( v5 < 0 )
  {
    v72 = 218;
    goto LABEL_12;
  }
  v71 = 218;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 64LL))(v4, &v91);
  v70 = v5;
  v26 = 220;
  if ( v5 < 0 )
  {
    v72 = 220;
    goto LABEL_12;
  }
  for ( i = 0; ; ++i )
  {
    v71 = v26;
    v94 = v2;
    v28 = v91;
    if ( i >= v91 )
      break;
    v29 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      v29 = v76;
    }
    v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v4 + 80LL);
    if ( v29 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v5 = v30(v4, i, &v76);
    v70 = v5;
    v26 = 225;
    if ( v5 < 0 )
      goto LABEL_242;
    v71 = 225;
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v76 + 64LL))(v76, &v92);
    v70 = v5;
    v26 = 228;
    if ( v5 < 0 )
      goto LABEL_242;
    v2 += v92;
  }
  v95 = 0;
  v85 = 0;
  v31 = 0;
  v79 = 0;
  v32 = 1;
LABEL_57:
  if ( !v28 )
  {
    v104 = 0;
    v105 = v107;
    v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, unsigned __int64 *))(*(_QWORD *)v74 + 56LL))(v74, &v104);
    v70 = v5;
    if ( v5 < 0 )
    {
      v72 = 600;
    }
    else
    {
      v71 = 600;
      v104 = v108;
      v105 = v99;
      v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, unsigned __int64 *))(*(_QWORD *)v74 + 56LL))(
             v74,
             &v104);
      v70 = v5;
      if ( v5 < 0 )
      {
        v72 = 602;
      }
      else
      {
        v71 = 602;
        v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v74 + 24LL))(v74);
        v70 = v5;
        if ( v5 < 0 )
        {
          v72 = 605;
        }
        else
        {
          v71 = 605;
          v5 = CalculateAggregateStatistics((char *)this + 56, v74);
          v70 = v5;
          if ( v5 >= 0 )
          {
            v71 = 607;
            v5 = CDefragOperation::_SetPercentComplete(this, 0x64u);
            v70 = v5;
            if ( v5 >= 0 )
            {
              v71 = 609;
              v5 = 0;
              v70 = 0;
            }
            else
            {
              v72 = 609;
            }
          }
          else
          {
            v72 = 607;
          }
        }
      }
    }
    goto LABEL_12;
  }
  v33 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = v76;
  }
  v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v4 + 80LL);
  if ( v33 )
  {
    v76 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v101 = v28 - 1;
  v5 = v34(v4, v28 - 1, &v76);
  v70 = v5;
  v26 = 238;
  if ( v5 < 0 )
    goto LABEL_242;
  v71 = 238;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ee341452bf5830146a4fbd1ddfd548bb_Traceguids, v28 - 1);
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v76 + 48LL))(v76, &v82);
  v70 = v5;
  v26 = 243;
  if ( v5 < 0 )
  {
LABEL_242:
    v72 = v26;
    goto LABEL_12;
  }
  v71 = 243;
  v98 = 0;
  pv[0] = 0;
  while ( 1 )
  {
    if ( v5 == 1 || !v82 )
    {
      v42 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        v42 = v77;
      }
      v43 = (unsigned int *)pv[0];
      while ( v43 )
      {
        v44 = *v43;
        v45 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v4 + 144LL);
        if ( v42 )
        {
          v70 = v45(v4, v44, v42, 0);
          v46 = 507;
          if ( v70 < 0 )
            goto LABEL_217;
        }
        else
        {
          v70 = v45(v4, v44, 0, &v77);
          v46 = 502;
          if ( v70 < 0 )
            goto LABEL_217;
        }
        v71 = v46;
        v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 32LL))(v76, *v43);
        v46 = 511;
        if ( v70 < 0
          || (v71 = 511,
              v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v77 + 24LL))(v77, *((_QWORD *)v43 + 1)),
              v46 = 515,
              v70 < 0)
          || (v71 = 515,
              v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 24LL))(v76, *v43),
              v46 = 518,
              v70 < 0) )
        {
LABEL_217:
          v72 = v46;
          goto LABEL_143;
        }
        v47 = v43;
        v71 = 518;
        v43 = (unsigned int *)*((_QWORD *)v43 + 2);
        CoTaskMemFree(v47);
        v42 = v77;
      }
      v60 = (unsigned int *)v98;
      while ( 1 )
      {
        if ( !v60 )
        {
          v5 = CalculateAggregateStatistics((char *)this + 56, v74);
          v70 = v5;
          v26 = 593;
          if ( v5 < 0 )
            goto LABEL_242;
          v71 = 593;
          v28 = v101;
          goto LABEL_57;
        }
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ee341452bf5830146a4fbd1ddfd548bb_Traceguids, *v60);
        }
        v64 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 **))(*(_QWORD *)v4 + 56LL);
        v65 = *v60;
        if ( v73 )
        {
          v70 = v64(v4, v65, v73, 0);
          v66 = 537;
          if ( v70 < 0 )
            goto LABEL_258;
        }
        else
        {
          v70 = v64(v4, v65, 0, &v73);
          v66 = 533;
          if ( v70 < 0 )
            goto LABEL_258;
        }
        v71 = v66;
        v75 = 0;
        v70 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(*v73 + 64))(v73, 128, &v75);
        v66 = 542;
        if ( v70 < 0 )
          goto LABEL_258;
        v71 = 542;
        v70 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned __int64 *))(*v73 + 40))(
                v73,
                *((_QWORD *)this + 23),
                &v88);
        v66 = 543;
        if ( v70 < 0 )
          goto LABEL_258;
        v71 = 543;
        if ( v75 )
        {
          if ( v88 <= 2 )
            goto LABEL_190;
        }
        else if ( v88 <= 1 )
        {
          goto LABEL_190;
        }
        v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v83 + 32LL))(v83, *v60);
        v66 = 548;
        if ( v70 < 0 )
          goto LABEL_258;
        v71 = 548;
LABEL_190:
        v67 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IFreeSpaceManager *, char *))(*v73 + 104))(
                v73,
                v4,
                v74,
                (char *)this + 56);
        v70 = v67;
        if ( v67 < 0 )
        {
          v66 = 552;
LABEL_258:
          v72 = v66;
          goto LABEL_147;
        }
        v71 = 552;
        if ( v67 != 1 )
        {
          v70 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned __int64 *))(*v73 + 40))(
                  v73,
                  *((_QWORD *)this + 23),
                  &v88);
          v66 = 572;
          if ( v70 < 0 )
            goto LABEL_258;
          v71 = 572;
          v75 = 0;
          v70 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(*v73 + 64))(v73, 128, &v75);
          v66 = 575;
          if ( v70 < 0 )
            goto LABEL_258;
          v71 = 575;
          if ( v75 )
          {
            if ( v88 > 2 )
              goto LABEL_196;
          }
          else if ( v88 > 1 )
          {
LABEL_196:
            v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v83 + 24LL))(v83, *v60);
            v66 = 580;
            if ( v70 < 0 )
              goto LABEL_258;
            v71 = 580;
          }
          v70 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(*v73 + 72))(v73, 8, 0);
          v68 = v70 < 0;
          v66 = 584;
          goto LABEL_206;
        }
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ee341452bf5830146a4fbd1ddfd548bb_Traceguids);
        }
        v70 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v73 + 144))(v73, v4);
        v66 = 559;
        if ( v70 < 0 )
          goto LABEL_258;
        v71 = 559;
        v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v83 + 32LL))(v83, *v60);
        v66 = 562;
        if ( v70 < 0 )
          goto LABEL_258;
        v71 = 562;
        v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 32LL))(v87, *v60);
        v66 = 563;
        if ( v70 < 0 )
          goto LABEL_258;
        v71 = 563;
        v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v86 + 32LL))(v86, *v60);
        v66 = 564;
        if ( v70 < 0 )
          goto LABEL_258;
        v71 = 564;
        v70 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 152LL))(v4, *v60);
        v68 = v70 < 0;
        v66 = 567;
LABEL_206:
        if ( v68 )
          goto LABEL_258;
        v71 = v66;
        v69 = v60;
        v60 = (unsigned int *)*((_QWORD *)v60 + 1);
        CoTaskMemFree(v69);
      }
    }
    v35 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v4 + 144LL);
    if ( v77 )
    {
      v5 = v35(v4, v82, v77, 0);
      v70 = v5;
      v36 = v5 < 0;
      v37 = 260;
    }
    else
    {
      v5 = v35(v4, v82, 0, &v77);
      v70 = v5;
      v36 = v5 < 0;
      v37 = 255;
    }
    if ( v36 )
      goto LABEL_142;
    v71 = v37;
    v5 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v77 + 48LL))(v77, v120);
    v70 = v5;
    v37 = 262;
    if ( v5 < 0 )
      goto LABEL_142;
    v71 = 262;
    if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v4 + 224LL))(v4) >= 0 )
    {
      v79 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v4 + 216LL))(v4, *(_QWORD *)&v120[0], &v79);
      v70 = v5;
      v37 = 268;
      if ( v5 < 0 )
        goto LABEL_142;
      v71 = 268;
      if ( v79 == 2 )
        v31 = 1;
      v79 = v31;
    }
    if ( *(_QWORD *)&v120[0] != -1 && *(_QWORD *)&v120[0] >= v119 && *(_QWORD *)&v120[0] <= v104 && !v31 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v77 + 56LL))(v77, &v96);
      v70 = v5;
      v37 = 283;
      if ( v5 < 0 )
        goto LABEL_142;
      v71 = 283;
      v38 = *((_QWORD *)this + 24);
      v39 = v96;
      if ( v96 < v38 || !v38 )
        break;
    }
LABEL_85:
    v5 = (*(__int64 (__fastcall **)(CRunConsolidate *))(*(_QWORD *)this + 32LL))(this);
    v70 = v5;
    v37 = 465;
    if ( v5 < 0 )
      goto LABEL_142;
    v71 = 465;
    if ( !v94 || (v41 = 100 * (unsigned __int64)v32 / v94, (unsigned int)v41 > 0x64) )
      LODWORD(v41) = 100;
    if ( (unsigned int)v41 > v95 )
    {
      v5 = CDefragOperation::_SetPercentComplete(this, v41);
      v70 = v5;
      v37 = 483;
      if ( v5 < 0 )
        goto LABEL_142;
      v71 = 483;
      v95 = v41;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v76 + 56LL))(v76, &v82);
    v70 = v5;
    v37 = 489;
    if ( v5 < 0 )
      goto LABEL_142;
    ++v32;
    v71 = 489;
    v31 = v79;
  }
  v40 = 0;
  if ( v80 )
  {
    v109 = 0;
    v110 = 643;
    v111 = 1;
    v112 = "CDefragOperation::_OptimizeMoveForVolsnap";
    v113 = 0;
    v114 = 0;
    v115 = 0;
    ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v113 + 8);
    if ( ThreadContextRetail < 0 )
    {
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSxGlobalTracer *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_105:
        if ( v111 )
        {
          if ( v111 == 1 )
          {
            if ( v49 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v49 + 7) & 0x20000000) == 0 )
              goto LABEL_109;
            v63 = 12;
LABEL_177:
            WPP_SF_s(*((_QWORD *)v49 + 2), v63, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v112);
            goto LABEL_109;
          }
          if ( v49 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x20000) != 0 )
          {
            v63 = 13;
            goto LABEL_177;
          }
        }
        else if ( v49 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x8000000) != 0 )
        {
          v63 = 11;
          goto LABEL_177;
        }
LABEL_109:
        v116 = 0;
        v109 = 0;
        LOWORD(v110) = 647;
        v50 = 4 * *((_DWORD *)this + 65);
        CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v109);
        v70 = 0;
        v71 = 296;
        v51 = v39 < v50;
        v39 = v96;
        if ( !v51 )
          v40 = *((_DWORD *)this + 65);
        goto LABEL_82;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
        (unsigned int)ThreadContextRetail);
    }
    else
    {
      *(_QWORD *)&v113 = *(_QWORD *)(*((_QWORD *)&v113 + 1) + 32LL);
      *(_QWORD *)(*((_QWORD *)&v113 + 1) + 32LL) = &v109;
    }
    v49 = WPP_GLOBAL_Control;
    goto LABEL_105;
  }
LABEL_82:
  v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, unsigned __int64, char **))(*(_QWORD *)v74 + 32LL))(
         v74,
         v39,
         &v97);
  v70 = v5;
  v37 = 304;
  if ( v5 < 0 )
    goto LABEL_142;
  v71 = 304;
  if ( v5 == 1 || (unsigned __int64)v97 >= *(_QWORD *)&v120[0] )
    goto LABEL_85;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v77 + 32LL))(v77, &v78);
  v70 = v5;
  v37 = 316;
  if ( v5 < 0 )
    goto LABEL_142;
  v71 = 316;
  v52 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, __int64 **))(*(_QWORD *)v4 + 56LL);
  if ( v73 )
  {
    v5 = v52(v4, v78, v73, 0);
    v70 = v5;
    v53 = v5 < 0;
    v37 = 326;
  }
  else
  {
    v5 = v52(v4, v78, 0, &v73);
    v70 = v5;
    v53 = v5 < 0;
    v37 = 321;
  }
  if ( v53 )
    goto LABEL_142;
  v71 = v37;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(*v73 + 64))(v73, 1, &v81);
  v70 = v5;
  v37 = 330;
  if ( v5 < 0 )
    goto LABEL_142;
  v71 = 330;
  if ( v81 )
    goto LABEL_85;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(*v73 + 64))(v73, 256, &v81);
  v70 = v5;
  v37 = 335;
  if ( v5 < 0 )
    goto LABEL_142;
  v71 = 335;
  if ( v81 )
    goto LABEL_85;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _OWORD *))(*(_QWORD *)v4 + 256LL))(v4, v78, v120);
  v70 = v5;
  v37 = 342;
  if ( v5 < 0 )
    goto LABEL_142;
  v71 = 342;
  v54 = *v73;
  if ( v5 != 1 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _OWORD *))(v54 + 24))(v73, 0, v122);
    v70 = v5;
    v37 = 349;
    if ( v5 < 0 )
      goto LABEL_142;
    for ( j = 0; ; ++j )
    {
      v71 = v37;
      if ( v5 == 1 )
        break;
      if ( *(_QWORD *)&v122[0] == *(_QWORD *)&v120[0] )
      {
        if ( !j )
        {
          v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(*v73 + 64))(v73, 128, &v75);
          v70 = v5;
          v37 = 365;
          if ( v5 < 0 )
            goto LABEL_142;
          v71 = 365;
          if ( v75 )
            break;
        }
        if ( v40 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, char *, unsigned int *))(*v73 + 184))(
                 v73,
                 j,
                 j,
                 v40,
                 v97,
                 &v84);
          v70 = v5;
          v37 = 379;
          if ( v5 < 0 )
            goto LABEL_142;
          v71 = 379;
          v56 = v84;
        }
        else
        {
          v56 = 0;
          v84 = 0;
        }
        v57 = (*(__int64 (__fastcall **)(__int64 *, _OWORD *, _QWORD, _QWORD, char *, _QWORD, __int64, struct IFreeSpaceManager *, struct IRunnableThread *, _QWORD))(*v73 + 112))(
                v73,
                v120,
                j,
                j,
                &v97[v56],
                *((_QWORD *)this + 25),
                v4,
                v74,
                RunnableThread,
                0);
        v5 = v57;
        if ( v57 != 1 && v57 != -1996488682 )
        {
          v70 = v57;
          v36 = v57 < 0;
          v37 = 411;
          if ( v36 )
            goto LABEL_142;
          v71 = 411;
          if ( v96 )
          {
            v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, _QWORD))(*(_QWORD *)v74 + 72LL))(
                   v74,
                   *(_QWORD *)&v120[0]);
            v70 = v5;
            v37 = 416;
            if ( v5 < 0 )
              goto LABEL_142;
            v71 = 416;
          }
          v58 = (LPVOID *)CoTaskMemAlloc(0x18u);
          if ( !v58 )
          {
            v37 = 422;
            goto LABEL_141;
          }
          v71 = 422;
          *(_DWORD *)v58 = v82;
          v58[2] = pv[0];
          v58[1] = v97;
          pv[0] = v58;
          v70 = 0;
          goto LABEL_85;
        }
        if ( (unsigned int)++v85 < 3 )
          break;
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ee341452bf5830146a4fbd1ddfd548bb_Traceguids);
        }
        v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v74 + 24LL))(v74);
        v70 = v5;
        v37 = 405;
        if ( v5 >= 0 )
        {
          v71 = 405;
          v85 = 0;
          v70 = 0;
          goto LABEL_85;
        }
        goto LABEL_142;
      }
      v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _OWORD *))(*v73 + 32))(v73, 0, v122);
      v70 = v5;
      v37 = 355;
      if ( v5 < 0 )
        goto LABEL_142;
    }
LABEL_124:
    v70 = 0;
    goto LABEL_85;
  }
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(v54 + 64))(v73, 8, &v93);
  v70 = v5;
  v37 = 440;
  if ( v5 < 0 )
    goto LABEL_142;
  v71 = 440;
  if ( v93 )
    goto LABEL_124;
  v62 = CoTaskMemAlloc(0x10u);
  if ( v62 )
  {
    v70 = 0;
    v71 = 446;
    *(_DWORD *)v62 = v78;
    v62[1] = v98;
    v98 = v62;
    v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*v73 + 72))(v73, 8, 1);
    v70 = v5;
    v37 = 454;
    if ( v5 < 0 )
      goto LABEL_142;
    v71 = 454;
    goto LABEL_124;
  }
  v37 = 446;
LABEL_141:
  v5 = -2147024882;
  v70 = -2147024882;
LABEL_142:
  v72 = v37;
  v43 = (unsigned int *)pv[0];
  if ( pv[0] )
  {
    do
    {
LABEL_143:
      v59 = v43;
      v43 = (unsigned int *)*((_QWORD *)v43 + 2);
      CoTaskMemFree(v59);
    }
    while ( v43 );
    v5 = v70;
  }
  if ( v98 )
  {
    v60 = (unsigned int *)v98;
    do
    {
LABEL_147:
      v61 = v60;
      v60 = (unsigned int *)*((_QWORD *)v60 + 1);
      CoTaskMemFree(v61);
    }
    while ( v60 );
    v5 = v70;
  }
LABEL_12:
  v10 = v86;
  if ( v86 )
  {
    v86 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v87;
  if ( v87 )
  {
    v87 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v83;
  if ( v83 )
  {
    v83 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( RunnableThread )
    (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)RunnableThread + 16LL))(RunnableThread);
  v13 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  }
  v15 = v77;
  if ( v77 )
  {
    v77 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v70);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ae70  push    rbp
0x18000ae72  push    rbx
0x18000ae73  push    rsi
0x18000ae74  push    rdi
0x18000ae75  push    r12
0x18000ae77  push    r13
0x18000ae79  push    r14
0x18000ae7b  push    r15
0x18000ae7d  lea     rbp, [rsp-158h]
0x18000ae85  sub     rsp, 258h
0x18000ae8c  mov     rax, cs:__security_cookie
0x18000ae93  xor     rax, rsp
0x18000ae96  mov     [rbp+190h+var_50], rax
0x18000ae9d  mov     r12, rcx
0x18000aea0  mov     r9d, 1; unsigned __int16
0x18000aea6  mov     r8d, 5Ch ; '\'; unsigned __int16
0x18000aeac  lea     rdx, aCrunconsolidat_1; "CRunConsolidate::RunOperation"
0x18000aeb3  lea     rcx, [rsp+290h+var_230]; this
0x18000aeb8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000aebd  nop
0x18000aebe  xor     r13d, r13d
0x18000aec1  mov     [rbp+190h+var_B8], r13
0x18000aec8  mov     [rbp+190h+var_1E0], r13
0x18000aecc  mov     [rbp+190h+var_1D8], r13
0x18000aed0  mov     [rbp+190h+var_1F8], r13
0x18000aed4  mov     [rbp+190h+var_1F0], r13
0x18000aed8  mov     ebx, r13d
0x18000aedb  mov     [rbp+190h+var_B0], rbx
0x18000aee2  mov     [rbp+190h+var_1B8], r13
0x18000aee6  mov     [rbp+190h+var_1A0], r13
0x18000aeea  mov     [rbp+190h+var_1A8], r13
0x18000aeee  mov     [rbp+190h+var_1C0], r13d
0x18000aef2  mov     [rbp+190h+var_1D0], r13d
0x18000aef6  xorps   xmm0, xmm0
0x18000aef9  xor     eax, eax
0x18000aefb  movups  [rbp+190h+var_A0], xmm0
0x18000af02  movups  [rbp+190h+var_90], xmm0
0x18000af09  mov     [rbp+190h+var_80], rax
0x18000af10  xorps   xmm1, xmm1
0x18000af13  movups  [rbp+190h+var_78], xmm1
0x18000af1a  movups  [rbp+190h+var_68], xmm1
0x18000af21  mov     [rbp+190h+var_58], rax
0x18000af28  mov     [rbp+190h+var_168], r13
0x18000af2c  mov     [rbp+190h+var_170], r13
0x18000af30  mov     [rbp+190h+var_198], r13
0x18000af34  mov     [rbp+190h+var_188], r13d
0x18000af38  mov     [rbp+190h+var_184], r13d
0x18000af3c  mov     [rbp+190h+var_180], r13d
0x18000af40  mov     [rbp+190h+var_1C4], r13d
0x18000af44  mov     [rbp+190h+var_1E8], r13d
0x18000af48  mov     [rbp+190h+var_1C8], r13d
0x18000af4c  mov     [rbp+190h+var_1B0], r13d
0x18000af50  mov     [rbp+190h+var_190], r13d
0x18000af54  mov     [rbp+190h+var_13C], r13d
0x18000af58  mov     [rbp+190h+var_18C], r13d
0x18000af5c  mov     [rbp+190h+var_110], r13d
0x18000af63  mov     r15, [r12+2E8h]
0x18000af6b  test    r15, r15
0x18000af6e  jz      short loc_18000AF80
0x18000af70  mov     rax, [r15]
0x18000af73  mov     rcx, r15
0x18000af76  mov     rax, [rax+8]
0x18000af7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af7f  nop
0x18000af80  mov     [rbp+190h+var_B8], r15
0x18000af87  test    r15, r15
0x18000af8a  jz      loc_18000C2C9
0x18000af90  mov     edx, 2
0x18000af95  mov     rcx, r12
0x18000af98  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x18000af9d  mov     edi, eax
0x18000af9f  mov     [rsp+290h+var_230], eax
0x18000afa3  test    eax, eax
0x18000afa5  mov     eax, 9Ah
0x18000afaa  js      loc_18000C2E1
0x18000afb0  mov     [rsp+290h+var_22C], ax
0x18000afb5  mov     rcx, r12; this
0x18000afb8  call    ?_GetRunnableThread@CDefragOperation@@IEAAPEAUIRunnableThread@@XZ; CDefragOperation::_GetRunnableThread(void)
0x18000afbd  mov     rbx, rax
0x18000afc0  mov     [rbp+190h+var_B0], rax
0x18000afc7  mov     [rsp+290h+var_230], r13d
0x18000afcc  mov     eax, 9Eh
0x18000afd1  mov     [rsp+290h+var_22C], ax
0x18000afd6  mov     rsi, [r12+300h]
0x18000afde  mov     [rbp+190h+var_A8], rsi
0x18000afe5  mov     r14, [r12+308h]
0x18000afed  mov     [rbp+190h+var_120], r14
0x18000aff1  mov     rax, [r15]
0x18000aff4  lea     rcx, [rbp+190h+var_110]
0x18000affb  mov     [rsp+290h+var_270], rcx
0x18000b000  lea     r9, [rbp+190h+var_18C]
0x18000b004  lea     r8, [rbp+190h+var_190]
0x18000b008  lea     rdx, [rbp+190h+var_13C]
0x18000b00c  mov     rcx, r15
0x18000b00f  mov     rax, [rax+0C0h]
0x18000b016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b01b  mov     edi, eax
0x18000b01d  mov     [rsp+290h+var_230], eax
0x18000b021  test    eax, eax
0x18000b023  mov     eax, 0A4h
0x18000b028  js      loc_18000C2EB
0x18000b02e  mov     [rsp+290h+var_22C], ax
0x18000b033  cmp     [rbp+190h+var_190], 0
0x18000b037  jnz     loc_18000C2F5
0x18000b03d  mov     rax, [r15]
0x18000b040  mov     rcx, r15
0x18000b043  mov     rax, [rax+0E0h]
0x18000b04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b04f  test    eax, eax
0x18000b051  jns     loc_18000B1B1
0x18000b057  mov     rcx, [rbp+190h+var_1F0]
0x18000b05b  test    rcx, rcx
0x18000b05e  jz      short loc_18000B071
0x18000b060  mov     [rbp+190h+var_1F0], r13
0x18000b064  mov     rax, [rcx]
0x18000b067  mov     rax, [rax+10h]
0x18000b06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b070  nop
0x18000b071  lea     r8, [rbp+190h+var_1F0]; struct IFreeSpaceManager **
0x18000b075  mov     rdx, [r12+90h]; unsigned __int64
0x18000b07d  mov     rcx, [r12+2B8h]; unsigned __int16 *
0x18000b085  call    ?CreateInstance@CFreeSpaceManager@@SAJPEAG_KPEAPEAUIFreeSpaceManager@@@Z; CFreeSpaceManager::CreateInstance(ushort *,unsigned __int64,IFreeSpaceManager * *)
0x18000b08a  mov     edi, eax
0x18000b08c  mov     [rsp+290h+var_230], eax
0x18000b090  test    eax, eax
0x18000b092  mov     eax, 0BAh
0x18000b097  jns     loc_18000B1FF
0x18000b09d  mov     [rsp+290h+var_22A], ax
0x18000b0a2  mov     rcx, [rbp+190h+var_1A8]
0x18000b0a6  test    rcx, rcx
0x18000b0a9  jz      short loc_18000B0BC
0x18000b0ab  mov     [rbp+190h+var_1A8], r13
0x18000b0af  mov     rax, [rcx]
0x18000b0b2  mov     rax, [rax+10h]
0x18000b0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0bb  nop
0x18000b0bc  mov     rcx, [rbp+190h+var_1A0]
0x18000b0c0  test    rcx, rcx
0x18000b0c3  jz      short loc_18000B0D6
0x18000b0c5  mov     [rbp+190h+var_1A0], r13
0x18000b0c9  mov     rax, [rcx]
0x18000b0cc  mov     rax, [rax+10h]
0x18000b0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0d5  nop
0x18000b0d6  mov     rcx, [rbp+190h+var_1B8]
0x18000b0da  test    rcx, rcx
0x18000b0dd  jz      short loc_18000B0F0
0x18000b0df  mov     [rbp+190h+var_1B8], r13
0x18000b0e3  mov     rax, [rcx]
0x18000b0e6  mov     rax, [rax+10h]
0x18000b0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ef  nop
0x18000b0f0  test    rbx, rbx
0x18000b0f3  jz      short loc_18000B105
0x18000b0f5  mov     rax, [rbx]
0x18000b0f8  mov     rcx, rbx
0x18000b0fb  mov     rax, [rax+10h]
0x18000b0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b104  nop
0x18000b105  mov     rcx, [rbp+190h+var_1F0]
0x18000b109  test    rcx, rcx
0x18000b10c  jz      short loc_18000B11F
0x18000b10e  mov     [rbp+190h+var_1F0], r13
0x18000b112  mov     rax, [rcx]
0x18000b115  mov     rax, [rax+10h]
0x18000b119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11e  nop
0x18000b11f  mov     rcx, [rbp+190h+var_1F8]
0x18000b123  test    rcx, rcx
0x18000b126  jz      short loc_18000B139
0x18000b128  mov     [rbp+190h+var_1F8], r13
0x18000b12c  mov     rax, [rcx]
0x18000b12f  mov     rax, [rax+10h]
0x18000b133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b138  nop
0x18000b139  mov     rcx, [rbp+190h+var_1D8]
0x18000b13d  test    rcx, rcx
0x18000b140  jz      short loc_18000B153
0x18000b142  mov     [rbp+190h+var_1D8], r13
0x18000b146  mov     rax, [rcx]
0x18000b149  mov     rax, [rax+10h]
0x18000b14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b152  nop
0x18000b153  mov     rcx, [rbp+190h+var_1E0]
0x18000b157  test    rcx, rcx
0x18000b15a  jz      short loc_18000B16D
0x18000b15c  mov     [rbp+190h+var_1E0], r13
0x18000b160  mov     rax, [rcx]
0x18000b163  mov     rax, [rax+10h]
0x18000b167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b16c  nop
0x18000b16d  test    r15, r15
0x18000b170  jz      short loc_18000B182
0x18000b172  mov     rax, [r15]
0x18000b175  mov     rcx, r15
0x18000b178  mov     rax, [rax+10h]
0x18000b17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b181  nop
0x18000b182  lea     rcx, [rsp+290h+var_230]; this
0x18000b187  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000b18c  mov     eax, edi
0x18000b18e  mov     rcx, [rbp+190h+var_50]
0x18000b195  xor     rcx, rsp; StackCookie
0x18000b198  call    __security_check_cookie
0x18000b19d  add     rsp, 258h
0x18000b1a4  pop     r15
0x18000b1a6  pop     r14
0x18000b1a8  pop     r13
0x18000b1aa  pop     r12
0x18000b1ac  pop     rdi
0x18000b1ad  pop     rsi
0x18000b1ae  pop     rbx
0x18000b1af  pop     rbp
0x18000b1b0  retn
0x18000b1b1  mov     rcx, [rbp+190h+var_1F0]
0x18000b1b5  test    rcx, rcx
0x18000b1b8  jz      short loc_18000B1CB
0x18000b1ba  mov     [rbp+190h+var_1F0], r13
0x18000b1be  mov     rax, [rcx]
0x18000b1c1  mov     rax, [rax+10h]
0x18000b1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ca  nop
0x18000b1cb  lea     r9, [rbp+190h+var_1F0]; struct IFreeSpaceManager **
0x18000b1cf  mov     r8d, [r12+98h]; unsigned int
0x18000b1d7  mov     rdx, [r12+90h]; unsigned __int64
0x18000b1df  mov     rcx, [r12+2B8h]; unsigned __int16 *
0x18000b1e7  call    ?CreateInstance@CTieredFreeSpaceManager@@SAJPEAG_KKPEAPEAUIFreeSpaceManager@@@Z; CTieredFreeSpaceManager::CreateInstance(ushort *,unsigned __int64,ulong,IFreeSpaceManager * *)
0x18000b1ec  mov     edi, eax
0x18000b1ee  mov     [rsp+290h+var_230], eax
0x18000b1f2  test    eax, eax
0x18000b1f4  mov     eax, 0B6h
0x18000b1f9  js      loc_18000C36E
0x18000b1ff  mov     [rsp+290h+var_22C], ax
0x18000b204  mov     [rbp+190h+var_108], r13
0x18000b20b  test    rsi, rsi
0x18000b20e  jnz     loc_18000C378
0x18000b214  mov     [rbp+190h+var_100], r13
0x18000b21b  mov     [rbp+190h+var_150], r13
0x18000b21f  mov     rsi, [r12+90h]
0x18000b227  dec     rsi
0x18000b22a  cmp     r14, rsi
0x18000b22d  jb      loc_18000C3C9
0x18000b233  cmp     [rbp+190h+var_18C], 0
0x18000b237  jnz     loc_18000C41A
0x18000b23d  mov     rax, [r15]
0x18000b240  mov     rdi, [rax+68h]
0x18000b244  mov     rdx, [rbp+190h+var_1B8]
0x18000b248  test    rdx, rdx
0x18000b24b  jz      short loc_18000B261
0x18000b24d  mov     [rbp+190h+var_1B8], r13
0x18000b251  mov     rcx, [rdx]
0x18000b254  mov     rax, [rcx+10h]
0x18000b258  mov     rcx, rdx
0x18000b25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b260  nop
0x18000b261  lea     r8, [rbp+190h+var_1B8]
0x18000b265  mov     edx, 1
0x18000b26a  mov     rcx, r15
0x18000b26d  mov     rax, rdi
0x18000b270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b275  mov     edi, eax
0x18000b277  mov     [rsp+290h+var_230], eax
0x18000b27b  test    eax, eax
0x18000b27d  mov     eax, 0D8h
0x18000b282  js      loc_18000C478
0x18000b288  mov     [rsp+290h+var_22C], ax
0x18000b28d  mov     rax, [r15]
0x18000b290  mov     rdi, [rax+68h]
0x18000b294  mov     r8, [rbp+190h+var_1A0]
0x18000b298  test    r8, r8
0x18000b29b  jz      short loc_18000B2B1
0x18000b29d  mov     [rbp+190h+var_1A0], r13
0x18000b2a1  mov     rcx, [r8]
0x18000b2a4  mov     rax, [rcx+10h]
0x18000b2a8  mov     rcx, r8
0x18000b2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2b0  nop
0x18000b2b1  lea     r8, [rbp+190h+var_1A0]
0x18000b2b5  mov     edx, 2
0x18000b2ba  mov     rcx, r15
0x18000b2bd  mov     rax, rdi
0x18000b2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c5  mov     edi, eax
0x18000b2c7  mov     [rsp+290h+var_230], eax
0x18000b2cb  test    eax, eax
0x18000b2cd  mov     eax, 0D9h
0x18000b2d2  js      loc_18000C482
0x18000b2d8  mov     [rsp+290h+var_22C], ax
0x18000b2dd  mov     rax, [r15]
0x18000b2e0  mov     rdi, [rax+68h]
0x18000b2e4  mov     rdx, [rbp+190h+var_1A8]
0x18000b2e8  test    rdx, rdx
0x18000b2eb  jz      short loc_18000B301
0x18000b2ed  mov     [rbp+190h+var_1A8], r13
0x18000b2f1  mov     rcx, [rdx]
0x18000b2f4  mov     rax, [rcx+10h]
0x18000b2f8  mov     rcx, rdx
0x18000b2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b300  nop
0x18000b301  lea     r8, [rbp+190h+var_1A8]
  ... truncated ...
```
