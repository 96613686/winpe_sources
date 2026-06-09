# _ConfigurationDataCollector::get_Xml(ushort * *)

- ea: `0x180095260`
- end: `0x1800960fa`
- name: `?get_Xml@_ConfigurationDataCollector@@UEAAJPEAPEAG@Z`
- size: `3738`
- prototype: `__int64 __fastcall(_ConfigurationDataCollector *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180024ea0`
- `0x180026850`
- `0x18003bb54`
- `0x180095260`
- `0x1800cdfe0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096097`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180096097`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009534a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009534a`

## string_xrefs

- `0x18009566d`: `RegistryKey`
- `0x180095306`: `_ConfigurationDataCollector::get_Xml`
- `0x1800953ed`: `_ConfigurationDataCollector::get_Xml`
- `0x1800954cd`: `_ConfigurationDataCollector::get_Xml`
- `0x180096031`: `_ConfigurationDataCollector::get_Xml`
- `0x180095dcf`: `RegistryMaxRecursiveDepth`

## pseudocode

```c
__int64 __fastcall _ConfigurationDataCollector::get_Xml(_ConfigurationDataCollector *this, unsigned __int16 **a2)
{
  __int64 v4; // rdx
  int Xml; // eax
  struct IXMLDOMDocument *v6; // r14
  unsigned int v7; // ebx
  struct IXMLDOMNode *v8; // r15
  __int64 v9; // rax
  int v10; // eax
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
  __int64 v49; // [rsp+48h] [rbp-B8h]
  __int64 v50; // [rsp+50h] [rbp-B0h]
  int v51; // [rsp+70h] [rbp-90h] BYREF
  struct IXMLDOMDocument *v52; // [rsp+78h] [rbp-88h] BYREF
  struct tagVARIANT v53; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMNode *v54; // [rsp+98h] [rbp-68h] BYREF
  _ConfigurationDataCollector *v55; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v56[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v57[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v58[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v59[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v60[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v61[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v62[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v63[64]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v64[64]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v65[64]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v66[64]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 v67[64]; // [rsp+630h] [rbp+530h] BYREF
  unsigned __int16 v68[64]; // [rsp+6B0h] [rbp+5B0h] BYREF
  unsigned __int16 v69[64]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v70[64]; // [rsp+7B0h] [rbp+6B0h] BYREF
  unsigned __int16 v71[64]; // [rsp+830h] [rbp+730h] BYREF
  unsigned __int16 v72[64]; // [rsp+8B0h] [rbp+7B0h] BYREF
  unsigned __int16 v73[64]; // [rsp+930h] [rbp+830h] BYREF
  unsigned __int16 v74[64]; // [rsp+9B0h] [rbp+8B0h] BYREF
  unsigned __int16 v75[64]; // [rsp+A30h] [rbp+930h] BYREF

  memset(&v53, 0, sizeof(v53));
  v52 = 0;
  v54 = 0;
  PlaiVariantInit(&v53);
  v51 = *((_DWORD *)this + 14);
  v55 = this;
  if ( (_DWORD)xmmword_180169738 )
  {
    v4 = 0x4000000000000400LL;
    if ( (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
    {
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_METHOD,
        3,
        "_ConfigurationDataCollector::get_Xml",
        37,
        &v55,
        8,
        &v51,
        4,
        v49,
        v50);
    }
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  Xml = _DataCollector<IConfigurationDataCollector>::CommonGetXml((__int64)this, v4, &v54, &v52);
  v6 = v52;
  v7 = Xml;
  v8 = v54;
  if ( Xml >= 0 )
  {
    PlaiVariantClear(&v53);
    v10 = (*(__int64 (__fastcall **)(_ConfigurationDataCollector *, CY *))(*(_QWORD *)this + 336LL))(this, &v53.cyVal);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v53.vt = 11;
      if ( v10 == 3145984 || (v12 = PlaiWriteXmlElement(L"QueryNetworkAdapters", v6, v8, &v53), v7 = v12, v12 >= 0) )
      {
        PlaiVariantClear(&v53);
        v14 = (*(__int64 (__fastcall **)(_ConfigurationDataCollector *, CY *))(*(_QWORD *)this + 352LL))(
                this,
                &v53.cyVal);
        v7 = v14;
        if ( v14 >= 0 )
        {
          v53.vt = 8200;
          if ( v14 == 3145984 || (v16 = PlaiWriteXmlElement(L"RegistryKey", v6, v8, &v53), v7 = v16, v16 >= 0) )
          {
            PlaiVariantClear(&v53);
            v18 = (*(__int64 (__fastcall **)(_ConfigurationDataCollector *, CY *))(*(_QWORD *)this + 304LL))(
                    this,
                    &v53.cyVal);
            v7 = v18;
            if ( v18 >= 0 )
            {
              v53.vt = 8200;
              if ( v18 == 3145984 || (v20 = PlaiWriteXmlElement(L"File", v6, v8, &v53), v7 = v20, v20 >= 0) )
              {
                PlaiVariantClear(&v53);
                v22 = (*(__int64 (__fastcall **)(_ConfigurationDataCollector *, CY *))(*(_QWORD *)this + 320LL))(
                        this,
                        &v53.cyVal);
                v7 = v22;
                if ( v22 >= 0 )
                {
                  v53.vt = 8200;
                  if ( v22 == 3145984
                    || (v24 = PlaiWriteXmlElement(L"ManagementQuery", v6, v8, &v53), v7 = v24, v24 >= 0) )
                  {
                    PlaiVariantClear(&v53);
                    v26 = (*(__int64 (__fastcall **)(_ConfigurationDataCollector *, CY *))(*(_QWORD *)this + 256LL))(
                            this,
                            &v53.cyVal);
                    v7 = v26;
                    if ( v26 >= 0 )
                    {
                      v53.vt = 19;
                      if ( v26 == 3145984
                        || (v28 = PlaiWriteXmlElement(L"FileMaxCount", v6, v8, &v53), v7 = v28, v28 >= 0) )
                      {
                        PlaiVariantClear(&v53);
                        v30 = (*(__int64 (__fastcall **)(_ConfigurationDataCollector *, CY *))(*(_QWORD *)this + 288LL))(
                                this,
                                &v53.cyVal);
                        v7 = v30;
                        if ( v30 >= 0 )
                        {
                          v53.vt = 19;
                          if ( v30 == 3145984
                            || (v32 = PlaiWriteXmlElement(L"FileMaxTotalSize", v6, v8, &v53), v7 = v32, v32 >= 0) )
                          {
                            PlaiVariantClear(&v53);
                            v34 = (*(__int64 (__fastcall **)(_ConfigurationDataCollector *, CY *))(*(_QWORD *)this
                                                                                                 + 272LL))(
                                    this,
                                    &v53.cyVal);
                            v7 = v34;
                            if ( v34 >= 0 )
                            {
                              v53.vt = 19;
                              if ( v34 == 3145984
                                || (v36 = PlaiWriteXmlElement(L"FileMaxRecursiveDepth", v6, v8, &v53), v7 = v36, v36 >= 0) )
                              {
                                PlaiVariantClear(&v53);
                                v38 = (*(__int64 (__fastcall **)(_ConfigurationDataCollector *, CY *))(*(_QWORD *)this + 368LL))(
                                        this,
                                        &v53.cyVal);
                                v7 = v38;
                                if ( v38 >= 0 )
                                {
                                  v53.vt = 19;
                                  if ( v38 == 3145984
                                    || (v40 = PlaiWriteXmlElement(L"RegistryMaxRecursiveDepth", v6, v8, &v53),
                                        v7 = v40,
                                        v40 >= 0) )
                                  {
                                    PlaiVariantClear(&v53);
                                    v42 = (*(__int64 (__fastcall **)(_ConfigurationDataCollector *, CY *))(*(_QWORD *)this + 384LL))(
                                            this,
                                            &v53.cyVal);
                                    v7 = v42;
                                    if ( v42 >= 0 )
                                    {
                                      v53.vt = 8;
                                      if ( v42 == 3145984
                                        || (v44 = PlaiWriteXmlElement(L"SystemStateFile", v6, v8, &v53),
                                            v7 = v44,
                                            v44 >= 0) )
                                      {
                                        v46 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 **))v6->lpVtbl->get_xml)(
                                                v6,
                                                a2);
                                        v7 = v46;
                                        if ( v46 >= 0 )
                                          goto LABEL_156;
                                        LODWORD(v52) = 0;
                                        v51 = v46;
                                        if ( !(_DWORD)xmmword_180169738
                                          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                        {
                                          goto LABEL_156;
                                        }
                                        PlaiWhoAmI(v75, 0x4000000000000800uLL);
                                        v47 = -1;
                                        do
                                          ++v47;
                                        while ( v75[v47] );
                                      }
                                      else
                                      {
                                        LODWORD(v52) = 0;
                                        v51 = v44;
                                        if ( !(_DWORD)xmmword_180169738
                                          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                        {
                                          goto LABEL_156;
                                        }
                                        PlaiWhoAmI(v74, 0x4000000000000800uLL);
                                        v45 = -1;
                                        do
                                          ++v45;
                                        while ( v74[v45] );
                                      }
                                    }
                                    else
                                    {
                                      LODWORD(v52) = 0;
                                      v51 = v42;
                                      if ( !(_DWORD)xmmword_180169738
                                        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                      {
                                        goto LABEL_156;
                                      }
                                      PlaiWhoAmI(v73, 0x4000000000000800uLL);
                                      v43 = -1;
                                      do
                                        ++v43;
                                      while ( v73[v43] );
                                    }
                                  }
                                  else
                                  {
                                    LODWORD(v52) = 0;
                                    v51 = v40;
                                    if ( !(_DWORD)xmmword_180169738
                                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                    {
                                      goto LABEL_156;
                                    }
                                    PlaiWhoAmI(v72, 0x4000000000000800uLL);
                                    v41 = -1;
                                    do
                                      ++v41;
                                    while ( v72[v41] );
                                  }
                                }
                                else
                                {
                                  LODWORD(v52) = 0;
                                  v51 = v38;
                                  if ( !(_DWORD)xmmword_180169738
                                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                  {
                                    goto LABEL_156;
                                  }
                                  PlaiWhoAmI(v71, 0x4000000000000800uLL);
                                  v39 = -1;
                                  do
                                    ++v39;
                                  while ( v71[v39] );
                                }
                              }
                              else
                              {
                                LODWORD(v52) = 0;
                                v51 = v36;
                                if ( !(_DWORD)xmmword_180169738
                                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                {
                                  goto LABEL_156;
                                }
                                PlaiWhoAmI(v70, 0x4000000000000800uLL);
                                v37 = -1;
                                do
                                  ++v37;
                                while ( v70[v37] );
                              }
                            }
                            else
                            {
                              LODWORD(v52) = 0;
                              v51 = v34;
                              if ( !(_DWORD)xmmword_180169738
                                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                              {
                                goto LABEL_156;
                              }
                              PlaiWhoAmI(v69, 0x4000000000000800uLL);
                              v35 = -1;
                              do
                                ++v35;
                              while ( v69[v35] );
                            }
                          }
                          else
                          {
                            LODWORD(v52) = 0;
                            v51 = v32;
                            if ( !(_DWORD)xmmword_180169738
                              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                            {
                              goto LABEL_156;
                            }
                            PlaiWhoAmI(v68, 0x4000000000000800uLL);
                            v33 = -1;
                            do
                              ++v33;
                            while ( v68[v33] );
                          }
                        }
                        else
                        {
                          LODWORD(v52) = 0;
                          v51 = v30;
                          if ( !(_DWORD)xmmword_180169738
                            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                          {
                            goto LABEL_156;
                          }
                          PlaiWhoAmI(v67, 0x4000000000000800uLL);
                          v31 = -1;
                          do
                            ++v31;
                          while ( v67[v31] );
                        }
                      }
                      else
                      {
                        LODWORD(v52) = 0;
                        v51 = v28;
                        if ( !(_DWORD)xmmword_180169738
                          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                        {
                          goto LABEL_156;
                        }
                        PlaiWhoAmI(v66, 0x4000000000000800uLL);
                        v29 = -1;
                        do
                          ++v29;
                        while ( v66[v29] );
                      }
                    }
                    else
                    {
                      LODWORD(v52) = 0;
                      v51 = v26;
                      if ( !(_DWORD)xmmword_180169738
                        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                      {
                        goto LABEL_156;
                      }
                      PlaiWhoAmI(v65, 0x4000000000000800uLL);
                      v27 = -1;
                      do
                        ++v27;
                      while ( v65[v27] );
                    }
                  }
                  else
                  {
                    LODWORD(v52) = 0;
                    v51 = v24;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_156;
                    }
                    PlaiWhoAmI(v64, 0x4000000000000800uLL);
                    v25 = -1;
                    do
                      ++v25;
                    while ( v64[v25] );
                  }
                }
                else
                {
                  LODWORD(v52) = 0;
                  v51 = v22;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_156;
                  }
                  PlaiWhoAmI(v63, 0x4000000000000800uLL);
                  v23 = -1;
                  do
                    ++v23;
                  while ( v63[v23] );
                }
              }
              else
              {
                LODWORD(v52) = 0;
                v51 = v20;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_156;
                }
                PlaiWhoAmI(v62, 0x4000000000000800uLL);
                v21 = -1;
                do
                  ++v21;
                while ( v62[v21] );
              }
            }
            else
            {
              LODWORD(v52) = 0;
              v51 = v18;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_156;
              }
              PlaiWhoAmI(v61, 0x4000000000000800uLL);
              v19 = -1;
              do
                ++v19;
              while ( v61[v19] );
            }
          }
          else
          {
            LODWORD(v52) = 0;
            v51 = v16;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_156;
            }
            PlaiWhoAmI(v60, 0x4000000000000800uLL);
            v17 = -1;
            do
              ++v17;
            while ( v60[v17] );
          }
        }
        else
        {
          LODWORD(v52) = 0;
          v51 = v14;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_156;
          }
          PlaiWhoAmI(v59, 0x4000000000000800uLL);
          v15 = -1;
          do
            ++v15;
          while ( v59[v15] );
        }
      }
      else
      {
        LODWORD(v52) = 0;
        v51 = v12;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_156;
        }
        PlaiWhoAmI(v58, 0x4000000000000800uLL);
        v13 = -1;
        do
          ++v13;
        while ( v58[v13] );
      }
    }
    else
    {
      LODWORD(v52) = 0;
      v51 = v10;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_156;
      }
      PlaiWhoAmI(v57, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v57[v11] );
    }
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v51,
      4,
      qword_180147320,
      1,
      &v52,
      4,
      "_ConfigurationDataCollector::get_Xml",
      37);
    goto LABEL_156;
  }
  v51 = 0;
  LODWORD(v52) = Xml;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v56, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v56[v9] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v52,
      4,
      qword_180147320,
      1,
      &v51,
      4,
      "_ConfigurationDataCollector::get_Xml",
      37);
  }
LABEL_156:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  PlaiVariantClear(&v53);
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v6->lpVtbl->Release)(v6);
  return v7;
}

```

## disassembly

```asm
0x180095260  mov     [rsp-8+arg_10], rbx
0x180095265  push    rbp
0x180095266  push    rsi
0x180095267  push    rdi
0x180095268  push    r12
0x18009526a  push    r13
0x18009526c  push    r14
0x18009526e  push    r15
0x180095270  lea     rbp, [rsp-9C0h]
0x180095278  sub     rsp, 0AC0h
0x18009527f  mov     rax, cs:__security_cookie
0x180095286  xor     rax, rsp
0x180095289  mov     [rbp+9F0h+var_40], rax
0x180095290  mov     rdi, rcx
0x180095293  xorps   xmm0, xmm0
0x180095296  xor     eax, eax
0x180095298  lea     rcx, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x18009529c  xor     r12d, r12d
0x18009529f  mov     qword ptr [rbp+9F0h+var_A70+10h], rax
0x1800952a3  movups  xmmword ptr [rbp+9F0h+var_A70], xmm0
0x1800952a7  mov     [rsp+0AF0h+var_A78], r12
0x1800952ac  mov     rsi, rdx
0x1800952af  mov     [rbp+9F0h+var_A58], r12
0x1800952b3  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800952b8  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800952bf  lea     r13d, [r12+4]
0x1800952c4  mov     eax, [rdi+38h]
0x1800952c7  mov     [rsp+0AF0h+var_A80], eax
0x1800952cb  mov     [rbp+9F0h+var_A50], rdi
0x1800952cf  jz      short loc_180095340
0x1800952d1  mov     rdx, 4000000000000400h
0x1800952db  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800952e2  jz      short loc_180095340
0x1800952e4  mov     rax, cs:qword_180169748
0x1800952eb  and     rax, rdx
0x1800952ee  cmp     cs:qword_180169748, rax
0x1800952f5  jnz     short loc_180095340
0x1800952f7  mov     [rsp+0AF0h+var_AB0], r13
0x1800952fc  lea     rax, [rsp+0AF0h+var_A80]
0x180095301  mov     [rsp+0AF0h+var_AB8], rax
0x180095306  lea     r9, aConfigurationd_6; "_ConfigurationDataCollector::get_Xml"
0x18009530d  lea     rax, [rbp+9F0h+var_A50]
0x180095311  mov     [rsp+0AF0h+var_AC0], 8
0x18009531a  mov     [rsp+0AF0h+var_AC8], rax
0x18009531f  lea     r8d, [r12+3]
0x180095324  lea     rdx, PLA_EVENT_METHOD
0x18009532b  mov     [rsp+0AF0h+var_AD0], 25h ; '%'
0x180095334  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18009533b  call    EventingWriteEvent
0x180095340  cmp     [rdi+8], r12d
0x180095344  jz      short loc_180095350
0x180095346  lea     rcx, [rdi+10h]; lpCriticalSection
0x18009534a  call    cs:__imp_EnterCriticalSection
0x180095350  lea     r9, [rsp+0AF0h+var_A78]
0x180095355  mov     rcx, rdi
0x180095358  lea     r8, [rbp+9F0h+var_A58]
0x18009535c  call    ?CommonGetXml@?$_DataCollector@UIConfigurationDataCollector@@@@IEAAJPEBGPEAPEAUIXMLDOMNode@@PEAPEAUIXMLDOMDocument@@@Z; _DataCollector<IConfigurationDataCollector>::CommonGetXml(ushort const *,IXMLDOMNode * *,IXMLDOMDocument * *)
0x180095361  mov     r14, [rsp+0AF0h+var_A78]
0x180095366  mov     ebx, eax
0x180095368  mov     r15, [rbp+9F0h+var_A58]
0x18009536c  test    eax, eax
0x18009536e  jns     loc_180095430
0x180095374  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009537b  mov     [rsp+0AF0h+var_A80], r12d
0x180095380  mov     dword ptr [rsp+0AF0h+var_A78], eax
0x180095384  jz      loc_18009608D
0x18009538a  mov     rdx, 4000000000000800h; unsigned __int64
0x180095394  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009539b  jz      loc_18009608D
0x1800953a1  mov     rax, cs:qword_180169748
0x1800953a8  and     rax, rdx
0x1800953ab  cmp     cs:qword_180169748, rax
0x1800953b2  jnz     loc_18009608D
0x1800953b8  lea     rcx, [rbp+9F0h+var_A40]; unsigned __int16 *
0x1800953bc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800953c1  lea     rcx, [rbp+9F0h+var_A40]
0x1800953c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800953c9  inc     rax
0x1800953cc  cmp     [rcx+rax*2], r12w
0x1800953d1  jnz     short loc_1800953C9
0x1800953d3  lea     ecx, [rax+rax]
0x1800953d6  lea     rax, [rbp+9F0h+var_A40]
0x1800953da  add     rcx, 2
0x1800953de  mov     [rsp+0AF0h+var_A90], rcx
0x1800953e3  lea     r9, [rsp+0AF0h+var_A78]
0x1800953e8  mov     [rsp+0AF0h+var_A98], rax
0x1800953ed  lea     rax, aConfigurationd_6; "_ConfigurationDataCollector::get_Xml"
0x1800953f4  mov     [rsp+0AF0h+var_AA0], 25h ; '%'
0x1800953fd  mov     [rsp+0AF0h+var_AA8], rax
0x180095402  lea     rax, [rsp+0AF0h+var_A80]
0x180095407  mov     [rsp+0AF0h+var_AB0], r13
0x18009540c  mov     [rsp+0AF0h+var_AB8], rax
0x180095411  lea     rax, qword_180147320
0x180095418  mov     [rsp+0AF0h+var_AC0], 1
0x180095421  mov     [rsp+0AF0h+var_AC8], rax
0x180095426  mov     [rsp+0AF0h+var_AD0], r13
0x18009542b  jmp     loc_180096074
0x180095430  lea     rcx, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x180095434  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x180095439  mov     rax, [rdi]
0x18009543c  lea     rdx, [rbp+9F0h+var_A70+8]
0x180095440  mov     rcx, rdi
0x180095443  mov     rax, [rax+150h]
0x18009544a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009544f  mov     ebx, eax
0x180095451  test    eax, eax
0x180095453  jns     loc_180095510
0x180095459  cmp     dword ptr cs:xmmword_180169738, r12d
0x180095460  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x180095465  mov     [rsp+0AF0h+var_A80], eax
0x180095469  jz      loc_18009608D
0x18009546f  mov     rdx, 4000000000000800h; unsigned __int64
0x180095479  test    qword ptr cs:xmmword_180169738+8, rdx
0x180095480  jz      loc_18009608D
0x180095486  mov     rax, cs:qword_180169748
0x18009548d  and     rax, rdx
0x180095490  cmp     cs:qword_180169748, rax
0x180095497  jnz     loc_18009608D
0x18009549d  lea     rcx, [rbp+9F0h+var_9C0]; unsigned __int16 *
0x1800954a1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800954a6  lea     rcx, [rbp+9F0h+var_9C0]
0x1800954aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800954ae  inc     rax
0x1800954b1  cmp     [rcx+rax*2], r12w
0x1800954b6  jnz     short loc_1800954AE
0x1800954b8  lea     ecx, [rax+rax]
0x1800954bb  lea     rax, [rbp+9F0h+var_9C0]
0x1800954bf  add     rcx, 2
0x1800954c3  mov     [rsp+0AF0h+var_A90], rcx
0x1800954c8  mov     [rsp+0AF0h+var_A98], rax
0x1800954cd  lea     rax, aConfigurationd_6; "_ConfigurationDataCollector::get_Xml"
0x1800954d4  mov     [rsp+0AF0h+var_AA0], 25h ; '%'
0x1800954dd  mov     [rsp+0AF0h+var_AA8], rax
0x1800954e2  lea     rax, [rsp+0AF0h+var_A78]
0x1800954e7  mov     [rsp+0AF0h+var_AB0], r13
0x1800954ec  mov     [rsp+0AF0h+var_AB8], rax
0x1800954f1  lea     rax, qword_180147320
0x1800954f8  mov     [rsp+0AF0h+var_AC0], 1
0x180095501  mov     [rsp+0AF0h+var_AC8], rax
0x180095506  mov     [rsp+0AF0h+var_AD0], r13
0x18009550b  jmp     loc_18009606F
0x180095510  mov     r13d, 300100h
0x180095516  mov     eax, 0Bh
0x18009551b  mov     word ptr [rbp+9F0h+var_A70], ax
0x18009551f  cmp     ebx, r13d
0x180095522  jz      loc_1800955B8
0x180095528  lea     r9, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x18009552c  mov     r8, r15; struct IXMLDOMNode *
0x18009552f  mov     rdx, r14; struct IXMLDOMDocument *
0x180095532  lea     rcx, aQuerynetworkad; "QueryNetworkAdapters"
0x180095539  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x18009553e  mov     ebx, eax
0x180095540  test    eax, eax
0x180095542  jns     short loc_1800955B8
0x180095544  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009554b  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x180095550  mov     [rsp+0AF0h+var_A80], eax
0x180095554  jz      loc_18009608D
0x18009555a  mov     rdx, 4000000000000800h; unsigned __int64
0x180095564  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009556b  jz      loc_18009608D
0x180095571  mov     rax, cs:qword_180169748
0x180095578  and     rax, rdx
0x18009557b  cmp     cs:qword_180169748, rax
0x180095582  jnz     loc_18009608D
0x180095588  lea     rcx, [rbp+9F0h+var_940]; unsigned __int16 *
0x18009558f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180095594  lea     rcx, [rbp+9F0h+var_940]
0x18009559b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009559f  inc     rax
0x1800955a2  cmp     [rcx+rax*2], r12w
0x1800955a7  jnz     short loc_18009559F
0x1800955a9  lea     ecx, [rax+rax]
0x1800955ac  lea     rax, [rbp+9F0h+var_940]
0x1800955b3  jmp     loc_18009601E
0x1800955b8  lea     rcx, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800955bc  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800955c1  mov     rax, [rdi]
0x1800955c4  lea     rdx, [rbp+9F0h+var_A70+8]
0x1800955c8  mov     rcx, rdi
0x1800955cb  mov     rax, [rax+160h]
0x1800955d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800955d7  mov     ebx, eax
0x1800955d9  test    eax, eax
0x1800955db  jns     short loc_180095651
0x1800955dd  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800955e4  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x1800955e9  mov     [rsp+0AF0h+var_A80], eax
0x1800955ed  jz      loc_18009608D
0x1800955f3  mov     rdx, 4000000000000800h; unsigned __int64
0x1800955fd  test    qword ptr cs:xmmword_180169738+8, rdx
0x180095604  jz      loc_18009608D
0x18009560a  mov     rax, cs:qword_180169748
0x180095611  and     rax, rdx
0x180095614  cmp     cs:qword_180169748, rax
0x18009561b  jnz     loc_18009608D
0x180095621  lea     rcx, [rbp+9F0h+var_8C0]; unsigned __int16 *
0x180095628  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009562d  lea     rcx, [rbp+9F0h+var_8C0]
0x180095634  or      rax, 0FFFFFFFFFFFFFFFFh
0x180095638  inc     rax
0x18009563b  cmp     [rcx+rax*2], r12w
0x180095640  jnz     short loc_180095638
0x180095642  lea     ecx, [rax+rax]
0x180095645  lea     rax, [rbp+9F0h+var_8C0]
0x18009564c  jmp     loc_18009601E
0x180095651  mov     eax, 2008h
0x180095656  mov     word ptr [rbp+9F0h+var_A70], ax
0x18009565a  cmp     ebx, r13d
0x18009565d  jz      loc_1800956F3
0x180095663  lea     r9, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x180095667  mov     r8, r15; struct IXMLDOMNode *
0x18009566a  mov     rdx, r14; struct IXMLDOMDocument *
0x18009566d  lea     rcx, aRegistrykey; "RegistryKey"
0x180095674  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x180095679  mov     ebx, eax
0x18009567b  test    eax, eax
0x18009567d  jns     short loc_1800956F3
0x18009567f  cmp     dword ptr cs:xmmword_180169738, r12d
0x180095686  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x18009568b  mov     [rsp+0AF0h+var_A80], eax
0x18009568f  jz      loc_18009608D
0x180095695  mov     rdx, 4000000000000800h; unsigned __int64
0x18009569f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800956a6  jz      loc_18009608D
0x1800956ac  mov     rax, cs:qword_180169748
0x1800956b3  and     rax, rdx
0x1800956b6  cmp     cs:qword_180169748, rax
0x1800956bd  jnz     loc_18009608D
0x1800956c3  lea     rcx, [rbp+9F0h+var_840]; unsigned __int16 *
0x1800956ca  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800956cf  lea     rcx, [rbp+9F0h+var_840]
0x1800956d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800956da  inc     rax
0x1800956dd  cmp     [rcx+rax*2], r12w
0x1800956e2  jnz     short loc_1800956DA
0x1800956e4  lea     ecx, [rax+rax]
0x1800956e7  lea     rax, [rbp+9F0h+var_840]
0x1800956ee  jmp     loc_18009601E
0x1800956f3  lea     rcx, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800956f7  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800956fc  mov     rax, [rdi]
0x1800956ff  lea     rdx, [rbp+9F0h+var_A70+8]
0x180095703  mov     rcx, rdi
0x180095706  mov     rax, [rax+130h]
0x18009570d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095712  mov     ebx, eax
0x180095714  test    eax, eax
0x180095716  jns     short loc_18009578C
0x180095718  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009571f  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x180095724  mov     [rsp+0AF0h+var_A80], eax
0x180095728  jz      loc_18009608D
0x18009572e  mov     rdx, 4000000000000800h; unsigned __int64
0x180095738  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009573f  jz      loc_18009608D
0x180095745  mov     rax, cs:qword_180169748
0x18009574c  and     rax, rdx
0x18009574f  cmp     cs:qword_180169748, rax
0x180095756  jnz     loc_18009608D
0x18009575c  lea     rcx, [rbp+9F0h+var_7C0]; unsigned __int16 *
0x180095763  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180095768  lea     rcx, [rbp+9F0h+var_7C0]
0x18009576f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180095773  inc     rax
0x180095776  cmp     [rcx+rax*2], r12w
0x18009577b  jnz     short loc_180095773
0x18009577d  lea     ecx, [rax+rax]
0x180095780  lea     rax, [rbp+9F0h+var_7C0]
0x180095787  jmp     loc_18009601E
0x18009578c  mov     eax, 2008h
0x180095791  mov     word ptr [rbp+9F0h+var_A70], ax
0x180095795  cmp     ebx, r13d
0x180095798  jz      loc_18009582E
0x18009579e  lea     r9, [rbp+9F0h+var_A70]; struct tagVARIANT *
0x1800957a2  mov     r8, r15; struct IXMLDOMNode *
0x1800957a5  mov     rdx, r14; struct IXMLDOMDocument *
0x1800957a8  lea     rcx, aFile_0; "File"
0x1800957af  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800957b4  mov     ebx, eax
0x1800957b6  test    eax, eax
0x1800957b8  jns     short loc_18009582E
0x1800957ba  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800957c1  mov     dword ptr [rsp+0AF0h+var_A78], r12d
0x1800957c6  mov     [rsp+0AF0h+var_A80], eax
0x1800957ca  jz      loc_18009608D
0x1800957d0  mov     rdx, 4000000000000800h; unsigned __int64
0x1800957da  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800957e1  jz      loc_18009608D
0x1800957e7  mov     rax, cs:qword_180169748
0x1800957ee  and     rax, rdx
0x1800957f1  cmp     cs:qword_180169748, rax
0x1800957f8  jnz     loc_18009608D
0x1800957fe  lea     rcx, [rbp+9F0h+var_740]; unsigned __int16 *
0x180095805  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009580a  lea     rcx, [rbp+9F0h+var_740]
0x180095811  or      rax, 0FFFFFFFFFFFFFFFFh
0x180095815  inc     rax
0x180095818  cmp     [rcx+rax*2], r12w
0x18009581d  jnz     short loc_180095815
  ... truncated ...
```
