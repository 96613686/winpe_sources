# _AlertDataCollector::get_Xml(ushort * *)

- ea: `0x1800d36a0`
- end: `0x1800d4530`
- name: `?get_Xml@_AlertDataCollector@@UEAAJPEAPEAG@Z`
- size: `3728`
- prototype: `__int64 __fastcall(_AlertDataCollector *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180024ea0`
- `0x180026850`
- `0x18003bb54`
- `0x1800d36a0`
- `0x1800dc11c`
- `0x180108fb8`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d44cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d44cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d378a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d378a`

## string_xrefs

- `0x1800d3746`: `_AlertDataCollector::get_Xml`
- `0x1800d382d`: `_AlertDataCollector::get_Xml`
- `0x1800d3903`: `_AlertDataCollector::get_Xml`
- `0x1800d4467`: `_AlertDataCollector::get_Xml`
- `0x1800d3f8f`: `TaskRunAsSelf`
- `0x1800d40ca`: `TaskArguments`
- `0x1800d4205`: `TaskUserTextArguments`

## pseudocode

```c
__int64 __fastcall _AlertDataCollector::get_Xml(_AlertDataCollector *this, unsigned __int16 **a2)
{
  __int64 v4; // rdx
  int Xml; // eax
  struct IXMLDOMDocument *v6; // r14
  unsigned int v7; // ebx
  struct IXMLDOMNode *v8; // r15
  __int64 v9; // rax
  int EnglishAlertThresholds; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rax
  int v42; // eax
  __int64 v43; // rax
  int v44; // eax
  __int64 v45; // rax
  int v46; // eax
  __int64 v47; // rax
  int v49; // [rsp+70h] [rbp-90h] BYREF
  struct IXMLDOMDocument *v50; // [rsp+78h] [rbp-88h] BYREF
  struct tagVARIANT v51; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMNode *v52; // [rsp+98h] [rbp-68h] BYREF
  _AlertDataCollector *v53; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v54[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v55[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v56[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v57[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v58[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v59[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v60[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v61[64]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v62[64]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v63[64]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v64[64]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 v65[64]; // [rsp+630h] [rbp+530h] BYREF
  unsigned __int16 v66[64]; // [rsp+6B0h] [rbp+5B0h] BYREF
  unsigned __int16 v67[64]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v68[64]; // [rsp+7B0h] [rbp+6B0h] BYREF
  unsigned __int16 v69[64]; // [rsp+830h] [rbp+730h] BYREF
  unsigned __int16 v70[64]; // [rsp+8B0h] [rbp+7B0h] BYREF
  unsigned __int16 v71[64]; // [rsp+930h] [rbp+830h] BYREF
  unsigned __int16 v72[64]; // [rsp+9B0h] [rbp+8B0h] BYREF
  unsigned __int16 v73[64]; // [rsp+A30h] [rbp+930h] BYREF

  memset(&v51, 0, sizeof(v51));
  v50 = 0;
  v52 = 0;
  PlaiVariantInit(&v51);
  v49 = *((_DWORD *)this + 14);
  v53 = this;
  if ( (_DWORD)xmmword_180169738 )
  {
    v4 = 0x4000000000000400LL;
    if ( (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
    {
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "_AlertDataCollector::get_Xml", 29, &v53, 8, &v49, 4);
    }
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  Xml = _DataCollector<IAlertDataCollector>::CommonGetXml(this, v4, &v52, &v50);
  v6 = v50;
  v7 = Xml;
  v8 = v52;
  if ( Xml >= 0 )
  {
    PlaiVariantClear(&v51);
    EnglishAlertThresholds = _AlertDataCollector::get_EnglishAlertThresholds(this, &v51.parray);
    v7 = EnglishAlertThresholds;
    if ( EnglishAlertThresholds >= 0 )
    {
      v51.vt = 8200;
      if ( EnglishAlertThresholds == 3145984 || (v12 = PlaiWriteXmlElement(L"Alert", v6, v8, &v51), v7 = v12, v12 >= 0) )
      {
        PlaiVariantClear(&v51);
        v14 = (*(__int64 (__fastcall **)(_AlertDataCollector *, CY *))(*(_QWORD *)this + 256LL))(this, &v51.cyVal);
        v7 = v14;
        if ( v14 >= 0 )
        {
          v51.vt = 8200;
          if ( v14 == 3145984 || (v16 = PlaiWriteXmlElement(L"AlertDisplayName", v6, v8, &v51), v7 = v16, v16 >= 0) )
          {
            PlaiVariantClear(&v51);
            v18 = (*(__int64 (__fastcall **)(_AlertDataCollector *, CY *))(*(_QWORD *)this + 272LL))(this, &v51.cyVal);
            v7 = v18;
            if ( v18 >= 0 )
            {
              v51.vt = 11;
              if ( v18 == 3145984 || (v20 = PlaiWriteXmlElement(L"EventLog", v6, v8, &v51), v7 = v20, v20 >= 0) )
              {
                PlaiVariantClear(&v51);
                v22 = (*(__int64 (__fastcall **)(_AlertDataCollector *, CY *))(*(_QWORD *)this + 288LL))(
                        this,
                        &v51.cyVal);
                v7 = v22;
                if ( v22 >= 0 )
                {
                  v51.vt = 19;
                  if ( v22 == 3145984
                    || (v24 = PlaiWriteXmlElement(L"SampleInterval", v6, v8, &v51), v7 = v24, v24 >= 0) )
                  {
                    PlaiVariantClear(&v51);
                    v26 = (*(__int64 (__fastcall **)(_AlertDataCollector *, CY *))(*(_QWORD *)this + 304LL))(
                            this,
                            &v51.cyVal);
                    v7 = v26;
                    if ( v26 >= 0 )
                    {
                      v51.vt = 8;
                      if ( v26 == 3145984 || (v28 = PlaiWriteXmlElement(L"Task", v6, v8, &v51), v7 = v28, v28 >= 0) )
                      {
                        PlaiVariantClear(&v51);
                        v30 = (*(__int64 (__fastcall **)(_AlertDataCollector *, CY *))(*(_QWORD *)this + 320LL))(
                                this,
                                &v51.cyVal);
                        v7 = v30;
                        if ( v30 >= 0 )
                        {
                          v51.vt = 11;
                          if ( v30 == 3145984
                            || (v32 = PlaiWriteXmlElement(L"TaskRunAsSelf", v6, v8, &v51), v7 = v32, v32 >= 0) )
                          {
                            PlaiVariantClear(&v51);
                            v34 = (*(__int64 (__fastcall **)(_AlertDataCollector *, CY *))(*(_QWORD *)this + 336LL))(
                                    this,
                                    &v51.cyVal);
                            v7 = v34;
                            if ( v34 >= 0 )
                            {
                              v51.vt = 8;
                              if ( v34 == 3145984
                                || (v36 = PlaiWriteXmlElement(L"TaskArguments", v6, v8, &v51), v7 = v36, v36 >= 0) )
                              {
                                PlaiVariantClear(&v51);
                                v38 = (*(__int64 (__fastcall **)(_AlertDataCollector *, CY *))(*(_QWORD *)this + 352LL))(
                                        this,
                                        &v51.cyVal);
                                v7 = v38;
                                if ( v38 >= 0 )
                                {
                                  v51.vt = 8;
                                  if ( v38 == 3145984
                                    || (v40 = PlaiWriteXmlElement(L"TaskUserTextArguments", v6, v8, &v51),
                                        v7 = v40,
                                        v40 >= 0) )
                                  {
                                    PlaiVariantClear(&v51);
                                    v42 = (*(__int64 (__fastcall **)(_AlertDataCollector *, CY *))(*(_QWORD *)this
                                                                                                 + 368LL))(
                                            this,
                                            &v51.cyVal);
                                    v7 = v42;
                                    if ( v42 >= 0 )
                                    {
                                      v51.vt = 8;
                                      if ( v42 == 3145984
                                        || (v44 = PlaiWriteXmlElement(L"TriggerDataCollectorSet", v6, v8, &v51),
                                            v7 = v44,
                                            v44 >= 0) )
                                      {
                                        v46 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 **))v6->lpVtbl->get_xml)(
                                                v6,
                                                a2);
                                        v7 = v46;
                                        if ( v46 >= 0 )
                                          goto LABEL_156;
                                        LODWORD(v50) = 0;
                                        v49 = v46;
                                        if ( !(_DWORD)xmmword_180169738
                                          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                        {
                                          goto LABEL_156;
                                        }
                                        PlaiWhoAmI(v73, 0x4000000000000800uLL);
                                        v47 = -1;
                                        do
                                          ++v47;
                                        while ( v73[v47] );
                                      }
                                      else
                                      {
                                        LODWORD(v50) = 0;
                                        v49 = v44;
                                        if ( !(_DWORD)xmmword_180169738
                                          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                        {
                                          goto LABEL_156;
                                        }
                                        PlaiWhoAmI(v72, 0x4000000000000800uLL);
                                        v45 = -1;
                                        do
                                          ++v45;
                                        while ( v72[v45] );
                                      }
                                    }
                                    else
                                    {
                                      LODWORD(v50) = 0;
                                      v49 = v42;
                                      if ( !(_DWORD)xmmword_180169738
                                        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                      {
                                        goto LABEL_156;
                                      }
                                      PlaiWhoAmI(v71, 0x4000000000000800uLL);
                                      v43 = -1;
                                      do
                                        ++v43;
                                      while ( v71[v43] );
                                    }
                                  }
                                  else
                                  {
                                    LODWORD(v50) = 0;
                                    v49 = v40;
                                    if ( !(_DWORD)xmmword_180169738
                                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                    {
                                      goto LABEL_156;
                                    }
                                    PlaiWhoAmI(v70, 0x4000000000000800uLL);
                                    v41 = -1;
                                    do
                                      ++v41;
                                    while ( v70[v41] );
                                  }
                                }
                                else
                                {
                                  LODWORD(v50) = 0;
                                  v49 = v38;
                                  if ( !(_DWORD)xmmword_180169738
                                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                  {
                                    goto LABEL_156;
                                  }
                                  PlaiWhoAmI(v69, 0x4000000000000800uLL);
                                  v39 = -1;
                                  do
                                    ++v39;
                                  while ( v69[v39] );
                                }
                              }
                              else
                              {
                                LODWORD(v50) = 0;
                                v49 = v36;
                                if ( !(_DWORD)xmmword_180169738
                                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                {
                                  goto LABEL_156;
                                }
                                PlaiWhoAmI(v68, 0x4000000000000800uLL);
                                v37 = -1;
                                do
                                  ++v37;
                                while ( v68[v37] );
                              }
                            }
                            else
                            {
                              LODWORD(v50) = 0;
                              v49 = v34;
                              if ( !(_DWORD)xmmword_180169738
                                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                              {
                                goto LABEL_156;
                              }
                              PlaiWhoAmI(v67, 0x4000000000000800uLL);
                              v35 = -1;
                              do
                                ++v35;
                              while ( v67[v35] );
                            }
                          }
                          else
                          {
                            LODWORD(v50) = 0;
                            v49 = v32;
                            if ( !(_DWORD)xmmword_180169738
                              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                            {
                              goto LABEL_156;
                            }
                            PlaiWhoAmI(v66, 0x4000000000000800uLL);
                            v33 = -1;
                            do
                              ++v33;
                            while ( v66[v33] );
                          }
                        }
                        else
                        {
                          LODWORD(v50) = 0;
                          v49 = v30;
                          if ( !(_DWORD)xmmword_180169738
                            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                          {
                            goto LABEL_156;
                          }
                          PlaiWhoAmI(v65, 0x4000000000000800uLL);
                          v31 = -1;
                          do
                            ++v31;
                          while ( v65[v31] );
                        }
                      }
                      else
                      {
                        LODWORD(v50) = 0;
                        v49 = v28;
                        if ( !(_DWORD)xmmword_180169738
                          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                        {
                          goto LABEL_156;
                        }
                        PlaiWhoAmI(v64, 0x4000000000000800uLL);
                        v29 = -1;
                        do
                          ++v29;
                        while ( v64[v29] );
                      }
                    }
                    else
                    {
                      LODWORD(v50) = 0;
                      v49 = v26;
                      if ( !(_DWORD)xmmword_180169738
                        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                      {
                        goto LABEL_156;
                      }
                      PlaiWhoAmI(v63, 0x4000000000000800uLL);
                      v27 = -1;
                      do
                        ++v27;
                      while ( v63[v27] );
                    }
                  }
                  else
                  {
                    LODWORD(v50) = 0;
                    v49 = v24;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_156;
                    }
                    PlaiWhoAmI(v62, 0x4000000000000800uLL);
                    v25 = -1;
                    do
                      ++v25;
                    while ( v62[v25] );
                  }
                }
                else
                {
                  LODWORD(v50) = 0;
                  v49 = v22;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_156;
                  }
                  PlaiWhoAmI(v61, 0x4000000000000800uLL);
                  v23 = -1;
                  do
                    ++v23;
                  while ( v61[v23] );
                }
              }
              else
              {
                LODWORD(v50) = 0;
                v49 = v20;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_156;
                }
                PlaiWhoAmI(v60, 0x4000000000000800uLL);
                v21 = -1;
                do
                  ++v21;
                while ( v60[v21] );
              }
            }
            else
            {
              LODWORD(v50) = 0;
              v49 = v18;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_156;
              }
              PlaiWhoAmI(v59, 0x4000000000000800uLL);
              v19 = -1;
              do
                ++v19;
              while ( v59[v19] );
            }
          }
          else
          {
            LODWORD(v50) = 0;
            v49 = v16;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_156;
            }
            PlaiWhoAmI(v58, 0x4000000000000800uLL);
            v17 = -1;
            do
              ++v17;
            while ( v58[v17] );
          }
        }
        else
        {
          LODWORD(v50) = 0;
          v49 = v14;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_156;
          }
          PlaiWhoAmI(v57, 0x4000000000000800uLL);
          v15 = -1;
          do
            ++v15;
          while ( v57[v15] );
        }
      }
      else
      {
        LODWORD(v50) = 0;
        v49 = v12;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_156;
        }
        PlaiWhoAmI(v56, 0x4000000000000800uLL);
        v13 = -1;
        do
          ++v13;
        while ( v56[v13] );
      }
    }
    else
    {
      LODWORD(v50) = 0;
      v49 = EnglishAlertThresholds;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_156;
      }
      PlaiWhoAmI(v55, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v55[v11] );
    }
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v49, 4, byte_180147320, 1, &v50, 4);
    goto LABEL_156;
  }
  v49 = 0;
  LODWORD(v50) = Xml;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v54, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v54[v9] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v50, 4, byte_180147320, 1, &v49, 4);
  }
LABEL_156:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  PlaiVariantClear(&v51);
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v6->lpVtbl->Release)(v6);
  return v7;
}

```

## disassembly

```asm
0x1800d36a0  mov     [rsp-8+arg_10], rbx
0x1800d36a5  push    rbp
0x1800d36a6  push    rsi
0x1800d36a7  push    rdi
0x1800d36a8  push    r12
0x1800d36aa  push    r13
0x1800d36ac  push    r14
0x1800d36ae  push    r15
0x1800d36b0  lea     rbp, [rsp-9C0h]
0x1800d36b8  sub     rsp, 0AC0h
0x1800d36bf  mov     rax, cs:__security_cookie
0x1800d36c6  xor     rax, rsp
0x1800d36c9  mov     [rbp+9F0h+var_40], rax
0x1800d36d0  mov     rdi, rcx
0x1800d36d3  xorps   xmm0, xmm0
0x1800d36d6  xor     eax, eax
0x1800d36d8  lea     rcx, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800d36dc  xor     r12d, r12d
0x1800d36df  mov     qword ptr [rbp+9F0h+var_A70+10h], rax
0x1800d36e3  movups  xmmword ptr [rbp+9F0h+var_A70], xmm0
0x1800d36e7  mov     [rsp+0AF0h+var_A78], r12
0x1800d36ec  mov     rsi, rdx
0x1800d36ef  mov     [rbp+9F0h+var_A58], r12
0x1800d36f3  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800d36f8  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d36ff  lea     r13d, [r12+4]
0x1800d3704  mov     eax, [rdi+38h]
0x1800d3707  mov     [rsp+0AF0h+var_A80], eax
0x1800d370b  mov     [rbp+9F0h+var_A50], rdi
0x1800d370f  jz      short loc_1800D3780
0x1800d3711  mov     rdx, 4000000000000400h
0x1800d371b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d3722  jz      short loc_1800D3780
0x1800d3724  mov     rax, cs:qword_180169748
0x1800d372b  and     rax, rdx
0x1800d372e  cmp     cs:qword_180169748, rax
0x1800d3735  jnz     short loc_1800D3780
0x1800d3737  mov     [rsp+0AF0h+var_AB0], r13
0x1800d373c  lea     rax, [rsp+0AF0h+var_A80]
0x1800d3741  mov     [rsp+0AF0h+var_AB8], rax
0x1800d3746  lea     r9, aAlertdatacolle_19; "_AlertDataCollector::get_Xml"
0x1800d374d  lea     rax, [rbp+9F0h+var_A50]
0x1800d3751  mov     [rsp+0AF0h+var_AC0], 8
0x1800d375a  mov     [rsp+0AF0h+var_AC8], rax
0x1800d375f  lea     r8d, [r12+3]
0x1800d3764  lea     rdx, PLA_EVENT_METHOD
0x1800d376b  mov     [rsp+0AF0h+var_AD0], 1Dh
0x1800d3774  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800d377b  call    EventingWriteEvent
0x1800d3780  cmp     [rdi+8], r12d
0x1800d3784  jz      short loc_1800D3790
0x1800d3786  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800d378a  call    cs:__imp_EnterCriticalSection
0x1800d3790  lea     r9, [rsp+0AF0h+var_A78]
0x1800d3795  mov     rcx, rdi
0x1800d3798  lea     r8, [rbp+9F0h+var_A58]
0x1800d379c  call    ?CommonGetXml@?$_DataCollector@UIAlertDataCollector@@@@IEAAJPEBGPEAPEAUIXMLDOMNode@@PEAPEAUIXMLDOMDocument@@@Z; _DataCollector<IAlertDataCollector>::CommonGetXml(ushort const *,IXMLDOMNode * *,IXMLDOMDocument * *)
0x1800d37a1  mov     r14, [rsp+0AF0h+var_A78]
0x1800d37a6  mov     ebx, eax
0x1800d37a8  mov     r15, [rbp+9F0h+var_A58]
0x1800d37ac  test    eax, eax
0x1800d37ae  jns     loc_1800D3870
0x1800d37b4  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d37bb  mov     [rsp+0AF0h+var_A80], r12d
0x1800d37c0  mov     dword ptr [rsp+0AF0h+var_A78], eax
0x1800d37c4  jz      loc_1800D44C3
0x1800d37ca  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d37d4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d37db  jz      loc_1800D44C3
0x1800d37e1  mov     rax, cs:qword_180169748
0x1800d37e8  and     rax, rdx
0x1800d37eb  cmp     cs:qword_180169748, rax
0x1800d37f2  jnz     loc_1800D44C3
0x1800d37f8  lea     rcx, [rbp+9F0h+var_A40]; unsigned __int16 *
0x1800d37fc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d3801  lea     rcx, [rbp+9F0h+var_A40]
0x1800d3805  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d3809  inc     rax
0x1800d380c  cmp     [rcx+rax*2], r12w
0x1800d3811  jnz     short loc_1800D3809
0x1800d3813  lea     ecx, [rax+rax]
0x1800d3816  lea     rax, [rbp+9F0h+var_A40]
0x1800d381a  add     rcx, 2
0x1800d381e  mov     [rsp+0AF0h+var_A90], rcx
0x1800d3823  lea     r9, [rsp+0AF0h+var_A78]
0x1800d3828  mov     [rsp+0AF0h+var_A98], rax
0x1800d382d  lea     rax, aAlertdatacolle_19; "_AlertDataCollector::get_Xml"
0x1800d3834  mov     [rsp+0AF0h+var_AA0], 1Dh
0x1800d383d  mov     [rsp+0AF0h+var_AA8], rax
0x1800d3842  lea     rax, [rsp+0AF0h+var_A80]
0x1800d3847  mov     [rsp+0AF0h+var_AB0], r13
0x1800d384c  mov     [rsp+0AF0h+var_AB8], rax
0x1800d3851  lea     rax, byte_180147320
0x1800d3858  mov     [rsp+0AF0h+var_AC0], 1
0x1800d3861  mov     [rsp+0AF0h+var_AC8], rax
0x1800d3866  mov     [rsp+0AF0h+var_AD0], r13
0x1800d386b  jmp     loc_1800D44AA
0x1800d3870  lea     rcx, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800d3874  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800d3879  lea     rdx, [rbp+9F0h+var_A70+8]; struct tagSAFEARRAY **
0x1800d387d  mov     rcx, rdi; this
0x1800d3880  call    ?get_EnglishAlertThresholds@_AlertDataCollector@@QEAAJPEAPEAUtagSAFEARRAY@@@Z; _AlertDataCollector::get_EnglishAlertThresholds(tagSAFEARRAY * *)
0x1800d3885  mov     ebx, eax
0x1800d3887  test    eax, eax
0x1800d3889  jns     loc_1800D3946
0x1800d388f  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d3896  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x1800d389b  mov     [rsp+0AF0h+var_A80], eax
0x1800d389f  jz      loc_1800D44C3
0x1800d38a5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d38af  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d38b6  jz      loc_1800D44C3
0x1800d38bc  mov     rax, cs:qword_180169748
0x1800d38c3  and     rax, rdx
0x1800d38c6  cmp     cs:qword_180169748, rax
0x1800d38cd  jnz     loc_1800D44C3
0x1800d38d3  lea     rcx, [rbp+9F0h+var_9C0]; unsigned __int16 *
0x1800d38d7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d38dc  lea     rcx, [rbp+9F0h+var_9C0]
0x1800d38e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d38e4  inc     rax
0x1800d38e7  cmp     [rcx+rax*2], r12w
0x1800d38ec  jnz     short loc_1800D38E4
0x1800d38ee  lea     ecx, [rax+rax]
0x1800d38f1  lea     rax, [rbp+9F0h+var_9C0]
0x1800d38f5  add     rcx, 2
0x1800d38f9  mov     [rsp+0AF0h+var_A90], rcx
0x1800d38fe  mov     [rsp+0AF0h+var_A98], rax
0x1800d3903  lea     rax, aAlertdatacolle_19; "_AlertDataCollector::get_Xml"
0x1800d390a  mov     [rsp+0AF0h+var_AA0], 1Dh
0x1800d3913  mov     [rsp+0AF0h+var_AA8], rax
0x1800d3918  lea     rax, [rsp+0AF0h+var_A78]
0x1800d391d  mov     [rsp+0AF0h+var_AB0], r13
0x1800d3922  mov     [rsp+0AF0h+var_AB8], rax
0x1800d3927  lea     rax, byte_180147320
0x1800d392e  mov     [rsp+0AF0h+var_AC0], 1
0x1800d3937  mov     [rsp+0AF0h+var_AC8], rax
0x1800d393c  mov     [rsp+0AF0h+var_AD0], r13
0x1800d3941  jmp     loc_1800D44A5
0x1800d3946  mov     r13d, 300100h
0x1800d394c  mov     eax, 2008h
0x1800d3951  mov     word ptr [rbp+9F0h+var_A70], ax
0x1800d3955  cmp     ebx, r13d
0x1800d3958  jz      loc_1800D39EE
0x1800d395e  lea     r9, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800d3962  mov     r8, r15; struct IXMLDOMNode *
0x1800d3965  mov     rdx, r14; struct IXMLDOMDocument *
0x1800d3968  lea     rcx, aAlert; "Alert"
0x1800d396f  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800d3974  mov     ebx, eax
0x1800d3976  test    eax, eax
0x1800d3978  jns     short loc_1800D39EE
0x1800d397a  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d3981  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x1800d3986  mov     [rsp+0AF0h+var_A80], eax
0x1800d398a  jz      loc_1800D44C3
0x1800d3990  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d399a  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d39a1  jz      loc_1800D44C3
0x1800d39a7  mov     rax, cs:qword_180169748
0x1800d39ae  and     rax, rdx
0x1800d39b1  cmp     cs:qword_180169748, rax
0x1800d39b8  jnz     loc_1800D44C3
0x1800d39be  lea     rcx, [rbp+9F0h+var_940]; unsigned __int16 *
0x1800d39c5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d39ca  lea     rcx, [rbp+9F0h+var_940]
0x1800d39d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d39d5  inc     rax
0x1800d39d8  cmp     [rcx+rax*2], r12w
0x1800d39dd  jnz     short loc_1800D39D5
0x1800d39df  lea     ecx, [rax+rax]
0x1800d39e2  lea     rax, [rbp+9F0h+var_940]
0x1800d39e9  jmp     loc_1800D4454
0x1800d39ee  lea     rcx, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800d39f2  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800d39f7  mov     rax, [rdi]
0x1800d39fa  lea     rdx, [rbp+9F0h+var_A70+8]
0x1800d39fe  mov     rcx, rdi
0x1800d3a01  mov     rax, [rax+100h]
0x1800d3a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3a0d  mov     ebx, eax
0x1800d3a0f  test    eax, eax
0x1800d3a11  jns     short loc_1800D3A87
0x1800d3a13  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d3a1a  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x1800d3a1f  mov     [rsp+0AF0h+var_A80], eax
0x1800d3a23  jz      loc_1800D44C3
0x1800d3a29  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d3a33  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d3a3a  jz      loc_1800D44C3
0x1800d3a40  mov     rax, cs:qword_180169748
0x1800d3a47  and     rax, rdx
0x1800d3a4a  cmp     cs:qword_180169748, rax
0x1800d3a51  jnz     loc_1800D44C3
0x1800d3a57  lea     rcx, [rbp+9F0h+var_8C0]; unsigned __int16 *
0x1800d3a5e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d3a63  lea     rcx, [rbp+9F0h+var_8C0]
0x1800d3a6a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d3a6e  inc     rax
0x1800d3a71  cmp     [rcx+rax*2], r12w
0x1800d3a76  jnz     short loc_1800D3A6E
0x1800d3a78  lea     ecx, [rax+rax]
0x1800d3a7b  lea     rax, [rbp+9F0h+var_8C0]
0x1800d3a82  jmp     loc_1800D4454
0x1800d3a87  mov     eax, 2008h
0x1800d3a8c  mov     word ptr [rbp+9F0h+var_A70], ax
0x1800d3a90  cmp     ebx, r13d
0x1800d3a93  jz      loc_1800D3B29
0x1800d3a99  lea     r9, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800d3a9d  mov     r8, r15; struct IXMLDOMNode *
0x1800d3aa0  mov     rdx, r14; struct IXMLDOMDocument *
0x1800d3aa3  lea     rcx, aAlertdisplayna; "AlertDisplayName"
0x1800d3aaa  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800d3aaf  mov     ebx, eax
0x1800d3ab1  test    eax, eax
0x1800d3ab3  jns     short loc_1800D3B29
0x1800d3ab5  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d3abc  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x1800d3ac1  mov     [rsp+0AF0h+var_A80], eax
0x1800d3ac5  jz      loc_1800D44C3
0x1800d3acb  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d3ad5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d3adc  jz      loc_1800D44C3
0x1800d3ae2  mov     rax, cs:qword_180169748
0x1800d3ae9  and     rax, rdx
0x1800d3aec  cmp     cs:qword_180169748, rax
0x1800d3af3  jnz     loc_1800D44C3
0x1800d3af9  lea     rcx, [rbp+9F0h+var_840]; unsigned __int16 *
0x1800d3b00  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d3b05  lea     rcx, [rbp+9F0h+var_840]
0x1800d3b0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d3b10  inc     rax
0x1800d3b13  cmp     [rcx+rax*2], r12w
0x1800d3b18  jnz     short loc_1800D3B10
0x1800d3b1a  lea     ecx, [rax+rax]
0x1800d3b1d  lea     rax, [rbp+9F0h+var_840]
0x1800d3b24  jmp     loc_1800D4454
0x1800d3b29  lea     rcx, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800d3b2d  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800d3b32  mov     rax, [rdi]
0x1800d3b35  lea     rdx, [rbp+9F0h+var_A70+8]
0x1800d3b39  mov     rcx, rdi
0x1800d3b3c  mov     rax, [rax+110h]
0x1800d3b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3b48  mov     ebx, eax
0x1800d3b4a  test    eax, eax
0x1800d3b4c  jns     short loc_1800D3BC2
0x1800d3b4e  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d3b55  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x1800d3b5a  mov     [rsp+0AF0h+var_A80], eax
0x1800d3b5e  jz      loc_1800D44C3
0x1800d3b64  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d3b6e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d3b75  jz      loc_1800D44C3
0x1800d3b7b  mov     rax, cs:qword_180169748
0x1800d3b82  and     rax, rdx
0x1800d3b85  cmp     cs:qword_180169748, rax
0x1800d3b8c  jnz     loc_1800D44C3
0x1800d3b92  lea     rcx, [rbp+9F0h+var_7C0]; unsigned __int16 *
0x1800d3b99  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d3b9e  lea     rcx, [rbp+9F0h+var_7C0]
0x1800d3ba5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d3ba9  inc     rax
0x1800d3bac  cmp     [rcx+rax*2], r12w
0x1800d3bb1  jnz     short loc_1800D3BA9
0x1800d3bb3  lea     ecx, [rax+rax]
0x1800d3bb6  lea     rax, [rbp+9F0h+var_7C0]
0x1800d3bbd  jmp     loc_1800D4454
0x1800d3bc2  mov     eax, 0Bh
0x1800d3bc7  mov     word ptr [rbp+9F0h+var_A70], ax
0x1800d3bcb  cmp     ebx, r13d
0x1800d3bce  jz      loc_1800D3C64
0x1800d3bd4  lea     r9, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800d3bd8  mov     r8, r15; struct IXMLDOMNode *
0x1800d3bdb  mov     rdx, r14; struct IXMLDOMDocument *
0x1800d3bde  lea     rcx, aEventlog; "EventLog"
0x1800d3be5  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800d3bea  mov     ebx, eax
0x1800d3bec  test    eax, eax
0x1800d3bee  jns     short loc_1800D3C64
0x1800d3bf0  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d3bf7  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x1800d3bfc  mov     [rsp+0AF0h+var_A80], eax
0x1800d3c00  jz      loc_1800D44C3
0x1800d3c06  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d3c10  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d3c17  jz      loc_1800D44C3
0x1800d3c1d  mov     rax, cs:qword_180169748
0x1800d3c24  and     rax, rdx
0x1800d3c27  cmp     cs:qword_180169748, rax
0x1800d3c2e  jnz     loc_1800D44C3
0x1800d3c34  lea     rcx, [rbp+9F0h+var_740]; unsigned __int16 *
0x1800d3c3b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d3c40  lea     rcx, [rbp+9F0h+var_740]
0x1800d3c47  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d3c4b  inc     rax
0x1800d3c4e  cmp     [rcx+rax*2], r12w
0x1800d3c53  jnz     short loc_1800D3C4B
0x1800d3c55  lea     ecx, [rax+rax]
0x1800d3c58  lea     rax, [rbp+9F0h+var_740]
  ... truncated ...
```
