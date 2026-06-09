# _ApiTracingDataCollector::get_Xml(ushort * *)

- ea: `0x1800c8eb0`
- end: `0x1800c9ad4`
- name: `?get_Xml@_ApiTracingDataCollector@@UEAAJPEAPEAG@Z`
- size: `3108`
- prototype: `__int64 __fastcall(_ApiTracingDataCollector *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180024ea0`
- `0x180026850`
- `0x18003bb54`
- `0x180053524`
- `0x1800c8eb0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c9a71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c9a71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c8f9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c8f9a`

## string_xrefs

- `0x1800c93f8`: `ExePath`
- `0x1800c8f56`: `_ApiTracingDataCollector::get_Xml`
- `0x1800c903d`: `_ApiTracingDataCollector::get_Xml`
- `0x1800c911d`: `_ApiTracingDataCollector::get_Xml`
- `0x1800c9a0b`: `_ApiTracingDataCollector::get_Xml`
- `0x1800c9533`: `LogFilePath`

## pseudocode

```c
__int64 __fastcall _ApiTracingDataCollector::get_Xml(_ApiTracingDataCollector *this, unsigned __int16 **a2)
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
  int v41; // [rsp+70h] [rbp-90h] BYREF
  struct IXMLDOMDocument *v42; // [rsp+78h] [rbp-88h] BYREF
  struct tagVARIANT v43; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMNode *v44; // [rsp+98h] [rbp-68h] BYREF
  _ApiTracingDataCollector *v45; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v46[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v47[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v48[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v49[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v50[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v51[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v52[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v53[64]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v54[64]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v55[64]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v56[64]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 v57[64]; // [rsp+630h] [rbp+530h] BYREF
  unsigned __int16 v58[64]; // [rsp+6B0h] [rbp+5B0h] BYREF
  unsigned __int16 v59[64]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v60[64]; // [rsp+7B0h] [rbp+6B0h] BYREF
  unsigned __int16 v61[64]; // [rsp+830h] [rbp+730h] BYREF

  memset(&v43, 0, sizeof(v43));
  v42 = 0;
  v44 = 0;
  PlaiVariantInit(&v43);
  v41 = *((_DWORD *)this + 14);
  v45 = this;
  if ( (_DWORD)xmmword_180169738 )
  {
    v4 = 0x4000000000000400LL;
    if ( (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
    {
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "_ApiTracingDataCollector::get_Xml", 34, &v45, 8, &v41, 4);
    }
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  Xml = _DataCollector<IApiTracingDataCollector>::CommonGetXml(this, v4, &v44, &v42);
  v6 = v42;
  v7 = Xml;
  v8 = v44;
  if ( Xml >= 0 )
  {
    PlaiVariantClear(&v43);
    v10 = (*(__int64 (__fastcall **)(_ApiTracingDataCollector *, CY *))(*(_QWORD *)this + 256LL))(this, &v43.cyVal);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v43.vt = 11;
      if ( v10 == 3145984 || (v12 = PlaiWriteXmlElement(L"LogApiNamesOnly", v6, v8, &v43), v7 = v12, v12 >= 0) )
      {
        PlaiVariantClear(&v43);
        v14 = (*(__int64 (__fastcall **)(_ApiTracingDataCollector *, CY *))(*(_QWORD *)this + 272LL))(this, &v43.cyVal);
        v7 = v14;
        if ( v14 >= 0 )
        {
          v43.vt = 11;
          if ( v14 == 3145984 || (v16 = PlaiWriteXmlElement(L"LogApisRecursively", v6, v8, &v43), v7 = v16, v16 >= 0) )
          {
            PlaiVariantClear(&v43);
            v18 = (*(__int64 (__fastcall **)(_ApiTracingDataCollector *, CY *))(*(_QWORD *)this + 288LL))(
                    this,
                    &v43.cyVal);
            v7 = v18;
            if ( v18 >= 0 )
            {
              v43.vt = 8;
              if ( v18 == 3145984 || (v20 = PlaiWriteXmlElement(L"ExePath", v6, v8, &v43), v7 = v20, v20 >= 0) )
              {
                PlaiVariantClear(&v43);
                v22 = (*(__int64 (__fastcall **)(_ApiTracingDataCollector *, CY *))(*(_QWORD *)this + 304LL))(
                        this,
                        &v43.cyVal);
                v7 = v22;
                if ( v22 >= 0 )
                {
                  v43.vt = 8;
                  if ( v22 == 3145984 || (v24 = PlaiWriteXmlElement(L"LogFilePath", v6, v8, &v43), v7 = v24, v24 >= 0) )
                  {
                    PlaiVariantClear(&v43);
                    v26 = (*(__int64 (__fastcall **)(_ApiTracingDataCollector *, CY *))(*(_QWORD *)this + 320LL))(
                            this,
                            &v43.cyVal);
                    v7 = v26;
                    if ( v26 >= 0 )
                    {
                      v43.vt = 8200;
                      if ( v26 == 3145984
                        || (v28 = PlaiWriteXmlElement(L"IncludeModule", v6, v8, &v43), v7 = v28, v28 >= 0) )
                      {
                        PlaiVariantClear(&v43);
                        v30 = (*(__int64 (__fastcall **)(_ApiTracingDataCollector *, CY *))(*(_QWORD *)this + 336LL))(
                                this,
                                &v43.cyVal);
                        v7 = v30;
                        if ( v30 >= 0 )
                        {
                          v43.vt = 8200;
                          if ( v30 == 3145984
                            || (v32 = PlaiWriteXmlElement(L"IncludeApi", v6, v8, &v43), v7 = v32, v32 >= 0) )
                          {
                            PlaiVariantClear(&v43);
                            v34 = (*(__int64 (__fastcall **)(_ApiTracingDataCollector *, CY *))(*(_QWORD *)this + 352LL))(
                                    this,
                                    &v43.cyVal);
                            v7 = v34;
                            if ( v34 >= 0 )
                            {
                              v43.vt = 8200;
                              if ( v34 == 3145984
                                || (v36 = PlaiWriteXmlElement(L"ExcludeApi", v6, v8, &v43), v7 = v36, v36 >= 0) )
                              {
                                v38 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 **))v6->lpVtbl->get_xml)(
                                        v6,
                                        a2);
                                v7 = v38;
                                if ( v38 >= 0 )
                                  goto LABEL_126;
                                LODWORD(v42) = 0;
                                v41 = v38;
                                if ( !(_DWORD)xmmword_180169738
                                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                {
                                  goto LABEL_126;
                                }
                                PlaiWhoAmI(v61, 0x4000000000000800uLL);
                                v39 = -1;
                                do
                                  ++v39;
                                while ( v61[v39] );
                              }
                              else
                              {
                                LODWORD(v42) = 0;
                                v41 = v36;
                                if ( !(_DWORD)xmmword_180169738
                                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                                {
                                  goto LABEL_126;
                                }
                                PlaiWhoAmI(v60, 0x4000000000000800uLL);
                                v37 = -1;
                                do
                                  ++v37;
                                while ( v60[v37] );
                              }
                            }
                            else
                            {
                              LODWORD(v42) = 0;
                              v41 = v34;
                              if ( !(_DWORD)xmmword_180169738
                                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                              {
                                goto LABEL_126;
                              }
                              PlaiWhoAmI(v59, 0x4000000000000800uLL);
                              v35 = -1;
                              do
                                ++v35;
                              while ( v59[v35] );
                            }
                          }
                          else
                          {
                            LODWORD(v42) = 0;
                            v41 = v32;
                            if ( !(_DWORD)xmmword_180169738
                              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                            {
                              goto LABEL_126;
                            }
                            PlaiWhoAmI(v58, 0x4000000000000800uLL);
                            v33 = -1;
                            do
                              ++v33;
                            while ( v58[v33] );
                          }
                        }
                        else
                        {
                          LODWORD(v42) = 0;
                          v41 = v30;
                          if ( !(_DWORD)xmmword_180169738
                            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                          {
                            goto LABEL_126;
                          }
                          PlaiWhoAmI(v57, 0x4000000000000800uLL);
                          v31 = -1;
                          do
                            ++v31;
                          while ( v57[v31] );
                        }
                      }
                      else
                      {
                        LODWORD(v42) = 0;
                        v41 = v28;
                        if ( !(_DWORD)xmmword_180169738
                          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                        {
                          goto LABEL_126;
                        }
                        PlaiWhoAmI(v56, 0x4000000000000800uLL);
                        v29 = -1;
                        do
                          ++v29;
                        while ( v56[v29] );
                      }
                    }
                    else
                    {
                      LODWORD(v42) = 0;
                      v41 = v26;
                      if ( !(_DWORD)xmmword_180169738
                        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                      {
                        goto LABEL_126;
                      }
                      PlaiWhoAmI(v55, 0x4000000000000800uLL);
                      v27 = -1;
                      do
                        ++v27;
                      while ( v55[v27] );
                    }
                  }
                  else
                  {
                    LODWORD(v42) = 0;
                    v41 = v24;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_126;
                    }
                    PlaiWhoAmI(v54, 0x4000000000000800uLL);
                    v25 = -1;
                    do
                      ++v25;
                    while ( v54[v25] );
                  }
                }
                else
                {
                  LODWORD(v42) = 0;
                  v41 = v22;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_126;
                  }
                  PlaiWhoAmI(v53, 0x4000000000000800uLL);
                  v23 = -1;
                  do
                    ++v23;
                  while ( v53[v23] );
                }
              }
              else
              {
                LODWORD(v42) = 0;
                v41 = v20;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_126;
                }
                PlaiWhoAmI(v52, 0x4000000000000800uLL);
                v21 = -1;
                do
                  ++v21;
                while ( v52[v21] );
              }
            }
            else
            {
              LODWORD(v42) = 0;
              v41 = v18;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_126;
              }
              PlaiWhoAmI(v51, 0x4000000000000800uLL);
              v19 = -1;
              do
                ++v19;
              while ( v51[v19] );
            }
          }
          else
          {
            LODWORD(v42) = 0;
            v41 = v16;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_126;
            }
            PlaiWhoAmI(v50, 0x4000000000000800uLL);
            v17 = -1;
            do
              ++v17;
            while ( v50[v17] );
          }
        }
        else
        {
          LODWORD(v42) = 0;
          v41 = v14;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_126;
          }
          PlaiWhoAmI(v49, 0x4000000000000800uLL);
          v15 = -1;
          do
            ++v15;
          while ( v49[v15] );
        }
      }
      else
      {
        LODWORD(v42) = 0;
        v41 = v12;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_126;
        }
        PlaiWhoAmI(v48, 0x4000000000000800uLL);
        v13 = -1;
        do
          ++v13;
        while ( v48[v13] );
      }
    }
    else
    {
      LODWORD(v42) = 0;
      v41 = v10;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_126;
      }
      PlaiWhoAmI(v47, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v47[v11] );
    }
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v41, 4, byte_180147320, 1, &v42, 4);
    goto LABEL_126;
  }
  v41 = 0;
  LODWORD(v42) = Xml;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v46, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v46[v9] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v42, 4, byte_180147320, 1, &v41, 4);
  }
LABEL_126:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  PlaiVariantClear(&v43);
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v6->lpVtbl->Release)(v6);
  return v7;
}

```

## disassembly

```asm
0x1800c8eb0  mov     [rsp-8+arg_10], rbx
0x1800c8eb5  push    rbp
0x1800c8eb6  push    rsi
0x1800c8eb7  push    rdi
0x1800c8eb8  push    r12
0x1800c8eba  push    r13
0x1800c8ebc  push    r14
0x1800c8ebe  push    r15
0x1800c8ec0  lea     rbp, [rsp-7C0h]
0x1800c8ec8  sub     rsp, 8C0h
0x1800c8ecf  mov     rax, cs:__security_cookie
0x1800c8ed6  xor     rax, rsp
0x1800c8ed9  mov     [rbp+7F0h+var_40], rax
0x1800c8ee0  mov     rdi, rcx
0x1800c8ee3  xorps   xmm0, xmm0
0x1800c8ee6  xor     eax, eax
0x1800c8ee8  lea     rcx, [rbp+7F0h+var_870]; struct tagVARIANT *
0x1800c8eec  xor     r12d, r12d
0x1800c8eef  mov     qword ptr [rbp+7F0h+var_870+10h], rax
0x1800c8ef3  movups  xmmword ptr [rbp+7F0h+var_870], xmm0
0x1800c8ef7  mov     [rsp+8F0h+var_878], r12
0x1800c8efc  mov     rsi, rdx
0x1800c8eff  mov     [rbp+7F0h+var_858], r12
0x1800c8f03  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800c8f08  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c8f0f  lea     r13d, [r12+4]
0x1800c8f14  mov     eax, [rdi+38h]
0x1800c8f17  mov     [rsp+8F0h+var_880], eax
0x1800c8f1b  mov     [rbp+7F0h+var_850], rdi
0x1800c8f1f  jz      short loc_1800C8F90
0x1800c8f21  mov     rdx, 4000000000000400h
0x1800c8f2b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c8f32  jz      short loc_1800C8F90
0x1800c8f34  mov     rax, cs:qword_180169748
0x1800c8f3b  and     rax, rdx
0x1800c8f3e  cmp     cs:qword_180169748, rax
0x1800c8f45  jnz     short loc_1800C8F90
0x1800c8f47  mov     [rsp+8F0h+var_8B0], r13
0x1800c8f4c  lea     rax, [rsp+8F0h+var_880]
0x1800c8f51  mov     [rsp+8F0h+var_8B8], rax
0x1800c8f56  lea     r9, aApitracingdata_14; "_ApiTracingDataCollector::get_Xml"
0x1800c8f5d  lea     rax, [rbp+7F0h+var_850]
0x1800c8f61  mov     [rsp+8F0h+var_8C0], 8
0x1800c8f6a  mov     [rsp+8F0h+var_8C8], rax
0x1800c8f6f  lea     r8d, [r12+3]
0x1800c8f74  lea     rdx, PLA_EVENT_METHOD
0x1800c8f7b  mov     [rsp+8F0h+var_8D0], 22h ; '"'
0x1800c8f84  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800c8f8b  call    EventingWriteEvent
0x1800c8f90  cmp     [rdi+8], r12d
0x1800c8f94  jz      short loc_1800C8FA0
0x1800c8f96  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800c8f9a  call    cs:__imp_EnterCriticalSection
0x1800c8fa0  lea     r9, [rsp+8F0h+var_878]
0x1800c8fa5  mov     rcx, rdi
0x1800c8fa8  lea     r8, [rbp+7F0h+var_858]
0x1800c8fac  call    ?CommonGetXml@?$_DataCollector@UIApiTracingDataCollector@@@@IEAAJPEBGPEAPEAUIXMLDOMNode@@PEAPEAUIXMLDOMDocument@@@Z; _DataCollector<IApiTracingDataCollector>::CommonGetXml(ushort const *,IXMLDOMNode * *,IXMLDOMDocument * *)
0x1800c8fb1  mov     r14, [rsp+8F0h+var_878]
0x1800c8fb6  mov     ebx, eax
0x1800c8fb8  mov     r15, [rbp+7F0h+var_858]
0x1800c8fbc  test    eax, eax
0x1800c8fbe  jns     loc_1800C9080
0x1800c8fc4  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c8fcb  mov     [rsp+8F0h+var_880], r12d
0x1800c8fd0  mov     dword ptr [rsp+8F0h+var_878], eax
0x1800c8fd4  jz      loc_1800C9A67
0x1800c8fda  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c8fe4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c8feb  jz      loc_1800C9A67
0x1800c8ff1  mov     rax, cs:qword_180169748
0x1800c8ff8  and     rax, rdx
0x1800c8ffb  cmp     cs:qword_180169748, rax
0x1800c9002  jnz     loc_1800C9A67
0x1800c9008  lea     rcx, [rbp+7F0h+var_840]; unsigned __int16 *
0x1800c900c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c9011  lea     rcx, [rbp+7F0h+var_840]
0x1800c9015  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c9019  inc     rax
0x1800c901c  cmp     [rcx+rax*2], r12w
0x1800c9021  jnz     short loc_1800C9019
0x1800c9023  lea     ecx, [rax+rax]
0x1800c9026  lea     rax, [rbp+7F0h+var_840]
0x1800c902a  add     rcx, 2
0x1800c902e  mov     [rsp+8F0h+var_890], rcx
0x1800c9033  lea     r9, [rsp+8F0h+var_878]
0x1800c9038  mov     [rsp+8F0h+var_898], rax
0x1800c903d  lea     rax, aApitracingdata_14; "_ApiTracingDataCollector::get_Xml"
0x1800c9044  mov     [rsp+8F0h+var_8A0], 22h ; '"'
0x1800c904d  mov     [rsp+8F0h+var_8A8], rax
0x1800c9052  lea     rax, [rsp+8F0h+var_880]
0x1800c9057  mov     [rsp+8F0h+var_8B0], r13
0x1800c905c  mov     [rsp+8F0h+var_8B8], rax
0x1800c9061  lea     rax, byte_180147320
0x1800c9068  mov     [rsp+8F0h+var_8C0], 1
0x1800c9071  mov     [rsp+8F0h+var_8C8], rax
0x1800c9076  mov     [rsp+8F0h+var_8D0], r13
0x1800c907b  jmp     loc_1800C9A4E
0x1800c9080  lea     rcx, [rbp+7F0h+var_870]; struct tagVARIANT *
0x1800c9084  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800c9089  mov     rax, [rdi]
0x1800c908c  lea     rdx, [rbp+7F0h+var_870+8]
0x1800c9090  mov     rcx, rdi
0x1800c9093  mov     rax, [rax+100h]
0x1800c909a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c909f  mov     ebx, eax
0x1800c90a1  test    eax, eax
0x1800c90a3  jns     loc_1800C9160
0x1800c90a9  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c90b0  mov     dword ptr [rsp+8F0h+var_878], r12d
0x1800c90b5  mov     [rsp+8F0h+var_880], eax
0x1800c90b9  jz      loc_1800C9A67
0x1800c90bf  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c90c9  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c90d0  jz      loc_1800C9A67
0x1800c90d6  mov     rax, cs:qword_180169748
0x1800c90dd  and     rax, rdx
0x1800c90e0  cmp     cs:qword_180169748, rax
0x1800c90e7  jnz     loc_1800C9A67
0x1800c90ed  lea     rcx, [rbp+7F0h+var_7C0]; unsigned __int16 *
0x1800c90f1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c90f6  lea     rcx, [rbp+7F0h+var_7C0]
0x1800c90fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c90fe  inc     rax
0x1800c9101  cmp     [rcx+rax*2], r12w
0x1800c9106  jnz     short loc_1800C90FE
0x1800c9108  lea     ecx, [rax+rax]
0x1800c910b  lea     rax, [rbp+7F0h+var_7C0]
0x1800c910f  add     rcx, 2
0x1800c9113  mov     [rsp+8F0h+var_890], rcx
0x1800c9118  mov     [rsp+8F0h+var_898], rax
0x1800c911d  lea     rax, aApitracingdata_14; "_ApiTracingDataCollector::get_Xml"
0x1800c9124  mov     [rsp+8F0h+var_8A0], 22h ; '"'
0x1800c912d  mov     [rsp+8F0h+var_8A8], rax
0x1800c9132  lea     rax, [rsp+8F0h+var_878]
0x1800c9137  mov     [rsp+8F0h+var_8B0], r13
0x1800c913c  mov     [rsp+8F0h+var_8B8], rax
0x1800c9141  lea     rax, byte_180147320
0x1800c9148  mov     [rsp+8F0h+var_8C0], 1
0x1800c9151  mov     [rsp+8F0h+var_8C8], rax
0x1800c9156  mov     [rsp+8F0h+var_8D0], r13
0x1800c915b  jmp     loc_1800C9A49
0x1800c9160  mov     r13d, 300100h
0x1800c9166  mov     eax, 0Bh
0x1800c916b  mov     word ptr [rbp+7F0h+var_870], ax
0x1800c916f  cmp     ebx, r13d
0x1800c9172  jz      loc_1800C9208
0x1800c9178  lea     r9, [rbp+7F0h+var_870]; struct tagVARIANT *
0x1800c917c  mov     r8, r15; struct IXMLDOMNode *
0x1800c917f  mov     rdx, r14; struct IXMLDOMDocument *
0x1800c9182  lea     rcx, aLogapinamesonl; "LogApiNamesOnly"
0x1800c9189  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800c918e  mov     ebx, eax
0x1800c9190  test    eax, eax
0x1800c9192  jns     short loc_1800C9208
0x1800c9194  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c919b  mov     dword ptr [rsp+8F0h+var_878], r12d
0x1800c91a0  mov     [rsp+8F0h+var_880], eax
0x1800c91a4  jz      loc_1800C9A67
0x1800c91aa  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c91b4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c91bb  jz      loc_1800C9A67
0x1800c91c1  mov     rax, cs:qword_180169748
0x1800c91c8  and     rax, rdx
0x1800c91cb  cmp     cs:qword_180169748, rax
0x1800c91d2  jnz     loc_1800C9A67
0x1800c91d8  lea     rcx, [rbp+7F0h+var_740]; unsigned __int16 *
0x1800c91df  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c91e4  lea     rcx, [rbp+7F0h+var_740]
0x1800c91eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c91ef  inc     rax
0x1800c91f2  cmp     [rcx+rax*2], r12w
0x1800c91f7  jnz     short loc_1800C91EF
0x1800c91f9  lea     ecx, [rax+rax]
0x1800c91fc  lea     rax, [rbp+7F0h+var_740]
0x1800c9203  jmp     loc_1800C99F8
0x1800c9208  lea     rcx, [rbp+7F0h+var_870]; struct tagVARIANT *
0x1800c920c  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800c9211  mov     rax, [rdi]
0x1800c9214  lea     rdx, [rbp+7F0h+var_870+8]
0x1800c9218  mov     rcx, rdi
0x1800c921b  mov     rax, [rax+110h]
0x1800c9222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9227  mov     ebx, eax
0x1800c9229  test    eax, eax
0x1800c922b  jns     short loc_1800C92A1
0x1800c922d  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c9234  mov     dword ptr [rsp+8F0h+var_878], r12d
0x1800c9239  mov     [rsp+8F0h+var_880], eax
0x1800c923d  jz      loc_1800C9A67
0x1800c9243  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c924d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c9254  jz      loc_1800C9A67
0x1800c925a  mov     rax, cs:qword_180169748
0x1800c9261  and     rax, rdx
0x1800c9264  cmp     cs:qword_180169748, rax
0x1800c926b  jnz     loc_1800C9A67
0x1800c9271  lea     rcx, [rbp+7F0h+var_6C0]; unsigned __int16 *
0x1800c9278  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c927d  lea     rcx, [rbp+7F0h+var_6C0]
0x1800c9284  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c9288  inc     rax
0x1800c928b  cmp     [rcx+rax*2], r12w
0x1800c9290  jnz     short loc_1800C9288
0x1800c9292  lea     ecx, [rax+rax]
0x1800c9295  lea     rax, [rbp+7F0h+var_6C0]
0x1800c929c  jmp     loc_1800C99F8
0x1800c92a1  mov     eax, 0Bh
0x1800c92a6  mov     word ptr [rbp+7F0h+var_870], ax
0x1800c92aa  cmp     ebx, r13d
0x1800c92ad  jz      loc_1800C9343
0x1800c92b3  lea     r9, [rbp+7F0h+var_870]; struct tagVARIANT *
0x1800c92b7  mov     r8, r15; struct IXMLDOMNode *
0x1800c92ba  mov     rdx, r14; struct IXMLDOMDocument *
0x1800c92bd  lea     rcx, aLogapisrecursi; "LogApisRecursively"
0x1800c92c4  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800c92c9  mov     ebx, eax
0x1800c92cb  test    eax, eax
0x1800c92cd  jns     short loc_1800C9343
0x1800c92cf  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c92d6  mov     dword ptr [rsp+8F0h+var_878], r12d
0x1800c92db  mov     [rsp+8F0h+var_880], eax
0x1800c92df  jz      loc_1800C9A67
0x1800c92e5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c92ef  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c92f6  jz      loc_1800C9A67
0x1800c92fc  mov     rax, cs:qword_180169748
0x1800c9303  and     rax, rdx
0x1800c9306  cmp     cs:qword_180169748, rax
0x1800c930d  jnz     loc_1800C9A67
0x1800c9313  lea     rcx, [rbp+7F0h+var_640]; unsigned __int16 *
0x1800c931a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c931f  lea     rcx, [rbp+7F0h+var_640]
0x1800c9326  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c932a  inc     rax
0x1800c932d  cmp     [rcx+rax*2], r12w
0x1800c9332  jnz     short loc_1800C932A
0x1800c9334  lea     ecx, [rax+rax]
0x1800c9337  lea     rax, [rbp+7F0h+var_640]
0x1800c933e  jmp     loc_1800C99F8
0x1800c9343  lea     rcx, [rbp+7F0h+var_870]; struct tagVARIANT *
0x1800c9347  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800c934c  mov     rax, [rdi]
0x1800c934f  lea     rdx, [rbp+7F0h+var_870+8]
0x1800c9353  mov     rcx, rdi
0x1800c9356  mov     rax, [rax+120h]
0x1800c935d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9362  mov     ebx, eax
0x1800c9364  test    eax, eax
0x1800c9366  jns     short loc_1800C93DC
0x1800c9368  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c936f  mov     dword ptr [rsp+8F0h+var_878], r12d
0x1800c9374  mov     [rsp+8F0h+var_880], eax
0x1800c9378  jz      loc_1800C9A67
0x1800c937e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c9388  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c938f  jz      loc_1800C9A67
0x1800c9395  mov     rax, cs:qword_180169748
0x1800c939c  and     rax, rdx
0x1800c939f  cmp     cs:qword_180169748, rax
0x1800c93a6  jnz     loc_1800C9A67
0x1800c93ac  lea     rcx, [rbp+7F0h+var_5C0]; unsigned __int16 *
0x1800c93b3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c93b8  lea     rcx, [rbp+7F0h+var_5C0]
0x1800c93bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c93c3  inc     rax
0x1800c93c6  cmp     [rcx+rax*2], r12w
0x1800c93cb  jnz     short loc_1800C93C3
0x1800c93cd  lea     ecx, [rax+rax]
0x1800c93d0  lea     rax, [rbp+7F0h+var_5C0]
0x1800c93d7  jmp     loc_1800C99F8
0x1800c93dc  mov     eax, 8
0x1800c93e1  mov     word ptr [rbp+7F0h+var_870], ax
0x1800c93e5  cmp     ebx, r13d
0x1800c93e8  jz      loc_1800C947E
0x1800c93ee  lea     r9, [rbp+7F0h+var_870]; struct tagVARIANT *
0x1800c93f2  mov     r8, r15; struct IXMLDOMNode *
0x1800c93f5  mov     rdx, r14; struct IXMLDOMDocument *
0x1800c93f8  lea     rcx, aExepath; "ExePath"
0x1800c93ff  call    ?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)
0x1800c9404  mov     ebx, eax
0x1800c9406  test    eax, eax
0x1800c9408  jns     short loc_1800C947E
0x1800c940a  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c9411  mov     dword ptr [rsp+8F0h+var_878], r12d
0x1800c9416  mov     [rsp+8F0h+var_880], eax
0x1800c941a  jz      loc_1800C9A67
0x1800c9420  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c942a  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c9431  jz      loc_1800C9A67
0x1800c9437  mov     rax, cs:qword_180169748
0x1800c943e  and     rax, rdx
0x1800c9441  cmp     cs:qword_180169748, rax
0x1800c9448  jnz     loc_1800C9A67
0x1800c944e  lea     rcx, [rbp+7F0h+var_540]; unsigned __int16 *
0x1800c9455  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c945a  lea     rcx, [rbp+7F0h+var_540]
0x1800c9461  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c9465  inc     rax
0x1800c9468  cmp     [rcx+rax*2], r12w
0x1800c946d  jnz     short loc_1800C9465
  ... truncated ...
```
