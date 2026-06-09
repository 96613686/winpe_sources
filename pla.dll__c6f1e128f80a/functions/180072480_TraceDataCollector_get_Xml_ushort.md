# _TraceDataCollector::get_Xml(ushort * *)

- ea: `0x180072480`
- end: `0x180074068`
- name: `?get_Xml@_TraceDataCollector@@UEAAJPEAPEAG@Z`
- size: `7144`
- prototype: `__int64 __fastcall(_TraceDataCollector *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180024ea0`
- `0x180026850`
- `0x18003bb54`
- `0x1800701e8`
- `0x180072480`
- `0x18007aa7c`
- `0x1800a9bac`
- `0x1800ec148`
- `0x18013aee0`
- `0x18013af70`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073ff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073ff0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072582`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072582`

## string_xrefs

- `0x18007253e`: `_TraceDataCollector::get_Xml`
- `0x18007261c`: `_TraceDataCollector::get_Xml`
- `0x18007280d`: `_TraceDataCollector::get_Xml`
- `0x180073f8a`: `_TraceDataCollector::get_Xml`
- `0x180073c9f`: `SessionThreadId`

## pseudocode

```c
__int64 __fastcall _TraceDataCollector::get_Xml(_TraceDataCollector *this, unsigned __int16 **a2)
{
  struct IXMLDOMDocument *v3; // r14
  struct IXMLDOMNode *v4; // r15
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  int Xml; // eax
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rcx
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
  int v48; // eax
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rax
  int v52; // eax
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rax
  int v58; // eax
  __int64 v59; // rax
  int v60; // eax
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // rax
  int v64; // eax
  __int64 v65; // rax
  int v66; // eax
  __int64 v67; // rax
  int v68; // eax
  __int64 v69; // rax
  int v70; // eax
  __int64 v71; // rax
  int v72; // eax
  __int64 v73; // rax
  int v74; // eax
  __int64 v75; // rax
  int v76; // eax
  __int64 v77; // rax
  int v78; // eax
  __int64 v79; // rax
  int v80; // eax
  __int64 v81; // rax
  int v82; // eax
  __int64 v83; // rax
  int v84; // eax
  __int64 v85; // rax
  int v86; // eax
  __int64 v87; // rax
  int v88; // eax
  __int64 v89; // rax
  int v90; // eax
  __int64 v91; // rax
  __int64 v93; // [rsp+48h] [rbp-B8h]
  __int64 v94; // [rsp+50h] [rbp-B0h]
  int v95; // [rsp+70h] [rbp-90h] BYREF
  int v96; // [rsp+78h] [rbp-88h] BYREF
  struct tagVARIANT v97; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMNode *v98; // [rsp+98h] [rbp-68h] BYREF
  struct IXMLDOMDocument *v99; // [rsp+A0h] [rbp-60h] BYREF
  struct ITraceDataProviderCollection *v100; // [rsp+A8h] [rbp-58h] BYREF
  _TraceDataCollector *v101; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v102; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v103[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v104[64]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v105[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v106[64]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v107[64]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v108[64]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v109[64]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned __int16 v110[64]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v111[64]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v112[64]; // [rsp+550h] [rbp+450h] BYREF
  unsigned __int16 v113[64]; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int16 v114[64]; // [rsp+650h] [rbp+550h] BYREF
  unsigned __int16 v115[64]; // [rsp+6D0h] [rbp+5D0h] BYREF
  unsigned __int16 v116[64]; // [rsp+750h] [rbp+650h] BYREF
  unsigned __int16 v117[64]; // [rsp+7D0h] [rbp+6D0h] BYREF
  unsigned __int16 v118[64]; // [rsp+850h] [rbp+750h] BYREF
  unsigned __int16 v119[64]; // [rsp+8D0h] [rbp+7D0h] BYREF
  unsigned __int16 v120[64]; // [rsp+950h] [rbp+850h] BYREF
  unsigned __int16 v121[64]; // [rsp+9D0h] [rbp+8D0h] BYREF
  unsigned __int16 v122[64]; // [rsp+A50h] [rbp+950h] BYREF
  unsigned __int16 v123[64]; // [rsp+AD0h] [rbp+9D0h] BYREF
  unsigned __int16 v124[64]; // [rsp+B50h] [rbp+A50h] BYREF
  unsigned __int16 v125[64]; // [rsp+BD0h] [rbp+AD0h] BYREF
  unsigned __int16 v126[64]; // [rsp+C50h] [rbp+B50h] BYREF
  unsigned __int16 v127[64]; // [rsp+CD0h] [rbp+BD0h] BYREF
  unsigned __int16 v128[64]; // [rsp+D50h] [rbp+C50h] BYREF
  unsigned __int16 v129[64]; // [rsp+DD0h] [rbp+CD0h] BYREF
  unsigned __int16 v130[64]; // [rsp+E50h] [rbp+D50h] BYREF
  unsigned __int16 v131[64]; // [rsp+ED0h] [rbp+DD0h] BYREF
  unsigned __int16 v132[64]; // [rsp+F50h] [rbp+E50h] BYREF
  unsigned __int16 v133[64]; // [rsp+FD0h] [rbp+ED0h] BYREF
  unsigned __int16 v134[64]; // [rsp+1050h] [rbp+F50h] BYREF
  unsigned __int16 v135[64]; // [rsp+10D0h] [rbp+FD0h] BYREF
  unsigned __int16 v136[64]; // [rsp+1150h] [rbp+1050h] BYREF
  unsigned __int16 v137[64]; // [rsp+11D0h] [rbp+10D0h] BYREF
  unsigned __int16 v138[64]; // [rsp+1250h] [rbp+1150h] BYREF
  unsigned __int16 v139[64]; // [rsp+12D0h] [rbp+11D0h] BYREF
  unsigned __int16 v140[64]; // [rsp+1350h] [rbp+1250h] BYREF
  unsigned __int16 v141[64]; // [rsp+13D0h] [rbp+12D0h] BYREF
  unsigned __int16 v142[64]; // [rsp+1450h] [rbp+1350h] BYREF
  unsigned __int16 v143[64]; // [rsp+14D0h] [rbp+13D0h] BYREF
  unsigned __int16 v144[64]; // [rsp+1550h] [rbp+1450h] BYREF

  v100 = 0;
  v99 = 0;
  memset(&v97, 0, sizeof(v97));
  v3 = 0;
  v4 = 0;
  v102 = 0;
  v98 = 0;
  v95 = 0;
  PlaiVariantInit(&v97);
  v96 = *((_DWORD *)this + 14);
  v101 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_METHOD,
      3,
      "_TraceDataCollector::get_Xml",
      29,
      &v101,
      8,
      &v96,
      4,
      v93,
      v94);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v6 = (*(__int64 (__fastcall **)(_TraceDataCollector *, struct ITraceDataProviderCollection **))(*(_QWORD *)this + 568LL))(
         this,
         &v100);
  v7 = v6;
  if ( v6 < 0 )
  {
    v96 = 0;
    v95 = v6;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v103, 0x4000000000000800uLL);
      v8 = -1;
      do
        ++v8;
      while ( v103[v8] );
LABEL_318:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v95,
        4,
        qword_180147320,
        1,
        &v96,
        4,
        "_TraceDataCollector::get_Xml",
        29);
      goto LABEL_319;
    }
    goto LABEL_319;
  }
  v9 = TraceDataProviderCollection::ValidateProviderList(&v95, v100);
  v7 = v9;
  if ( v9 >= 0 )
  {
    if ( v95 < 0 )
    {
      v96 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v105, 0x4000000000000800uLL);
        v12 = -1;
        do
          ++v12;
        while ( v105[v12] );
        goto LABEL_318;
      }
      goto LABEL_319;
    }
    Xml = _DataCollector<ITraceDataCollector>::CommonGetXml((__int64)this, v10, &v98, &v99);
    v7 = Xml;
    if ( Xml >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(_TraceDataCollector *, struct _GUID *))(*(_QWORD *)this + 384LL))(this, &v102);
      v7 = v15;
      if ( v15 >= 0 )
      {
        v4 = v98;
        v3 = v99;
        v18 = PlaiWriteXmlGuid(v16, v99, v98, &v102);
        v7 = v18;
        if ( v18 >= 0 )
        {
          PlaiVariantClear(&v97);
          v20 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 256LL))(this, &v97.cyVal);
          v7 = v20;
          if ( v20 >= 0 )
          {
            v97.vt = 19;
            if ( v20 == 3145984 || (v22 = PlaiWriteXmlElement(L"BufferSize", v3, v4, &v97), v7 = v22, v22 >= 0) )
            {
              PlaiVariantClear(&v97);
              v24 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 272LL))(this, &v97.cyVal);
              v7 = v24;
              if ( v24 >= 0 )
              {
                v97.vt = 19;
                if ( v24 == 3145984 || (v26 = PlaiWriteXmlElement(L"BuffersLost", v3, v4, &v97), v7 = v26, v26 >= 0) )
                {
                  PlaiVariantClear(&v97);
                  v28 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 288LL))(
                          this,
                          &v97.cyVal);
                  v7 = v28;
                  if ( v28 >= 0 )
                  {
                    v97.vt = 19;
                    if ( v28 == 3145984
                      || (v30 = PlaiWriteXmlElement(L"BuffersWritten", v3, v4, &v97), v7 = v30, v30 >= 0) )
                    {
                      PlaiVariantClear(&v97);
                      v32 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 304LL))(
                              this,
                              &v97.cyVal);
                      v7 = v32;
                      if ( v32 >= 0 )
                      {
                        v97.vt = 3;
                        if ( v32 == 3145984
                          || (v34 = PlaiWriteXmlElement(L"ClockType", v3, v4, &v97), v7 = v34, v34 >= 0) )
                        {
                          PlaiVariantClear(&v97);
                          v36 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 320LL))(
                                  this,
                                  &v97.cyVal);
                          v7 = v36;
                          if ( v36 >= 0 )
                          {
                            v97.vt = 19;
                            if ( v36 == 3145984
                              || (v38 = PlaiWriteXmlElement(L"EventsLost", v3, v4, &v97), v7 = v38, v38 >= 0) )
                            {
                              PlaiVariantClear(&v97);
                              v40 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 336LL))(
                                      this,
                                      &v97.cyVal);
                              v7 = v40;
                              if ( v40 >= 0 )
                              {
                                v97.vt = 19;
                                if ( v40 == 3145984
                                  || (v42 = PlaiWriteXmlElement(L"ExtendedModes", v3, v4, &v97), v7 = v42, v42 >= 0) )
                                {
                                  PlaiVariantClear(&v97);
                                  v44 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 352LL))(
                                          this,
                                          &v97.cyVal);
                                  v7 = v44;
                                  if ( v44 >= 0 )
                                  {
                                    v97.vt = 19;
                                    if ( v44 == 3145984
                                      || (v46 = PlaiWriteXmlElement(L"FlushTimer", v3, v4, &v97), v7 = v46, v46 >= 0) )
                                    {
                                      PlaiVariantClear(&v97);
                                      v48 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 368LL))(
                                              this,
                                              &v97.cyVal);
                                      v7 = v48;
                                      if ( v48 >= 0 )
                                      {
                                        v97.vt = 19;
                                        if ( v48 == 3145984
                                          || (v50 = PlaiWriteXmlElement(L"FreeBuffers", v3, v4, &v97), v7 = v50, v50 >= 0) )
                                        {
                                          PlaiVariantClear(&v97);
                                          v52 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 408LL))(
                                                  this,
                                                  &v97.cyVal);
                                          v7 = v52;
                                          if ( v52 >= 0 )
                                          {
                                            v97.vt = 19;
                                            if ( v52 == 3145984
                                              || (v54 = PlaiWriteXmlElement(L"MaximumBuffers", v3, v4, &v97),
                                                  v7 = v54,
                                                  v54 >= 0) )
                                            {
                                              PlaiVariantClear(&v97);
                                              v56 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 424LL))(
                                                      this,
                                                      &v97.cyVal);
                                              v7 = v56;
                                              if ( v56 >= 0 )
                                              {
                                                v97.vt = 19;
                                                if ( v56 == 3145984
                                                  || (v58 = PlaiWriteXmlElement(L"MinimumBuffers", v3, v4, &v97),
                                                      v7 = v58,
                                                      v58 >= 0) )
                                                {
                                                  PlaiVariantClear(&v97);
                                                  v60 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 440LL))(
                                                          this,
                                                          &v97.cyVal);
                                                  v7 = v60;
                                                  if ( v60 >= 0 )
                                                  {
                                                    v97.vt = 19;
                                                    if ( v60 == 3145984
                                                      || (v62 = PlaiWriteXmlElement(L"NumberOfBuffers", v3, v4, &v97),
                                                          v7 = v62,
                                                          v62 >= 0) )
                                                    {
                                                      PlaiVariantClear(&v97);
                                                      v64 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 456LL))(
                                                              this,
                                                              &v97.cyVal);
                                                      v7 = v64;
                                                      if ( v64 >= 0 )
                                                      {
                                                        v97.vt = 11;
                                                        if ( v64 == 3145984
                                                          || (v66 = PlaiWriteXmlElement(
                                                                      L"PreallocateFile",
                                                                      v3,
                                                                      v4,
                                                                      &v97),
                                                              v7 = v66,
                                                              v66 >= 0) )
                                                        {
                                                          PlaiVariantClear(&v97);
                                                          v68 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 472LL))(
                                                                  this,
                                                                  &v97.cyVal);
                                                          v7 = v68;
                                                          if ( v68 >= 0 )
                                                          {
                                                            v97.vt = 11;
                                                            if ( v68 == 3145984
                                                              || (v70 = PlaiWriteXmlElement(
                                                                          L"ProcessMode",
                                                                          v3,
                                                                          v4,
                                                                          &v97),
                                                                  v7 = v70,
                                                                  v70 >= 0) )
                                                            {
                                                              PlaiVariantClear(&v97);
                                                              v72 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 488LL))(
                                                                      this,
                                                                      &v97.cyVal);
                                                              v7 = v72;
                                                              if ( v72 >= 0 )
                                                              {
                                                                v97.vt = 19;
                                                                if ( v72 == 3145984
                                                                  || (v74 = PlaiWriteXmlElement(
                                                                              L"RealTimeBuffersLost",
                                                                              v3,
                                                                              v4,
                                                                              &v97),
                                                                      v7 = v74,
                                                                      v74 >= 0) )
                                                                {
                                                                  PlaiVariantClear(&v97);
                                                                  v76 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 520LL))(
                                                                          this,
                                                                          &v97.cyVal);
                                                                  v7 = v76;
                                                                  if ( v76 >= 0 )
                                                                  {
                                                                    v97.vt = 8;
                                                                    if ( v76 == 3145984
                                                                      || (v78 = PlaiWriteXmlElement(
                                                                                  L"SessionName",
                                                                                  v3,
                                                                                  v4,
                                                                                  &v97),
                                                                          v7 = v78,
                                                                          v78 >= 0) )
                                                                    {
                                                                      PlaiVariantClear(&v97);
                                                                      v80 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 536LL))(
                                                                              this,
                                                                              &v97.cyVal);
                                                                      v7 = v80;
                                                                      if ( v80 >= 0 )
                                                                      {
                                                                        v97.vt = 19;
                                                                        if ( v80 == 3145984
                                                                          || (v82 = PlaiWriteXmlElement(
                                                                                      L"SessionThreadId",
                                                                                      v3,
                                                                                      v4,
                                                                                      &v97),
                                                                              v7 = v82,
                                                                              v82 >= 0) )
                                                                        {
                                                                          PlaiVariantClear(&v97);
                                                                          v84 = (*(__int64 (__fastcall **)(_TraceDataCollector *, CY *))(*(_QWORD *)this + 552LL))(
                                                                                  this,
                                                                                  &v97.cyVal);
                                                                          v7 = v84;
                                                                          if ( v84 >= 0 )
                                                                          {
                                                                            v97.vt = 3;
                                                                            if ( v84 == 3145984
                                                                              || (v86 = PlaiWriteXmlElement(
                                                                                          L"StreamMode",
                                                                                          v3,
                                                                                          v4,
                                                                                          &v97),
                                                                                  v7 = v86,
                                                                                  v86 >= 0) )
                                                                            {
                                                                              v88 = TraceDataProviderCollection::GetXml(
                                                                                      v100,
                                                                                      v3,
                                                                                      v4);
                                                                              v7 = v88;
                                                                              if ( v88 >= 0 )
                                                                              {
                                                                                v90 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 **))v3->lpVtbl->get_xml)(
                                                                                        v3,
                                                                                        a2);
                                                                                v7 = v90;
                                                                                if ( v90 < 0 )
                                                                                {
                                                                                  v96 = 0;
                                                                                  v95 = v90;
                                                                                  if ( (_DWORD)xmmword_180169738 )
                                                                                  {
                                                                                    if ( (*(&xmmword_180169738 + 1)
                                                                                        & 0x4000000000000800LL) != 0
                                                                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                                                    {
                                                                                      PlaiWhoAmI(
                                                                                        v144,
                                                                                        0x4000000000000800uLL);
                                                                                      v91 = -1;
                                                                                      do
                                                                                        ++v91;
                                                                                      while ( v144[v91] );
                                                                                      goto LABEL_318;
                                                                                    }
                                                                                  }
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                v96 = 0;
                                                                                v95 = v88;
                                                                                if ( (_DWORD)xmmword_180169738
                                                                                  && (*(&xmmword_180169738 + 1)
                                                                                    & 0x4000000000000800LL) != 0
                                                                                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                                                {
                                                                                  PlaiWhoAmI(
                                                                                    v143,
                                                                                    0x4000000000000800uLL);
                                                                                  v89 = -1;
                                                                                  do
                                                                                    ++v89;
                                                                                  while ( v143[v89] );
                                                                                  goto LABEL_318;
                                                                                }
                                                                              }
                                                                            }
                                                                            else
                                                                            {
                                                                              v96 = 0;
                                                                              v95 = v86;
                                                                              if ( (_DWORD)xmmword_180169738
                                                                                && (*(&xmmword_180169738 + 1)
                                                                                  & 0x4000000000000800LL) != 0
                                                                                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                                              {
                                                                                PlaiWhoAmI(v142, 0x4000000000000800uLL);
                                                                                v87 = -1;
                                                                                do
                                                                                  ++v87;
                                                                                while ( v142[v87] );
                                                                                goto LABEL_318;
                                                                              }
                                                                            }
                                                                          }
                                                                          else
                                                                          {
                                                                            v96 = 0;
                                                                            v95 = v84;
                                                                            if ( (_DWORD)xmmword_180169738
                                                                              && (*(&xmmword_180169738 + 1)
                                                                                & 0x4000000000000800LL) != 0
                                                                              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                                            {
                                                                              PlaiWhoAmI(v141, 0x4000000000000800uLL);
                                                                              v85 = -1;
                                                                              do
                                                                                ++v85;
                                                                              while ( v141[v85] );
                                                                              goto LABEL_318;
                                                                            }
                                                                          }
                                                                        }
                                                                        else
                                                                        {
                                                                          v96 = 0;
                                                                          v95 = v82;
                                                                          if ( (_DWORD)xmmword_180169738
                                                                            && (*(&xmmword_180169738 + 1)
                                                                              & 0x4000000000000800LL) != 0
                                                                            && qword_180169748 == (qword_180169748
                                                                                                 & 0x4000000000000800LL) )
                                                                          {
                                                                            PlaiWhoAmI(v140, 0x4000000000000800uLL);
                                                                            v83 = -1;
                                                                            do
                                                                              ++v83;
                                                                            while ( v140[v83] );
                                                                            goto LABEL_318;
                                                                          }
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        v96 = 0;
                                                                        v95 = v80;
                                                                        if ( (_DWORD)xmmword_180169738
                                                                          && (*(&xmmword_180169738 + 1)
                                                                            & 0x4000000000000800LL) != 0
                                                                          && qword_180169748 == (qword_180169748
                                                                                               & 0x4000000000000800LL) )
                                                                        {
                                                                          PlaiWhoAmI(v139, 0x4000000000000800uLL);
                                                                          v81 = -1;
                                                                          do
                                                                            ++v81;
                                                                          while ( v139[v81] );
                                                                          goto LABEL_318;
                                                                        }
                                                                      }
                                                                    }
                                                                    else
                                                                    {
                                                                      v96 = 0;
                                                                      v95 = v78;
                                                                      if ( (_DWORD)xmmword_180169738
                                                                        && (*(&xmmword_180169738 + 1)
                                                                          & 0x4000000000000800LL) != 0
                                                                        && qword_180169748 == (qword_180169748
                                                                                             & 0x4000000000000800LL) )
                                                                      {
                                                                        PlaiWhoAmI(v138, 0x4000000000000800uLL);
                                                                        v79 = -1;
                                                                        do
                                                                          ++v79;
                                                                        while ( v138[v79] );
                                                                        goto LABEL_318;
                                                                      }
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    v96 = 0;
                                                                    v95 = v76;
                                                                    if ( (_DWORD)xmmword_180169738
                                                                      && (*(&xmmword_180169738 + 1)
                                                                        & 0x4000000000000800LL) != 0
                                                                      && qword_180169748 == (qword_180169748
                                                                                           & 0x4000000000000800LL) )
                                                                    {
                                                                      PlaiWhoAmI(v137, 0x4000000000000800uLL);
                                                                      v77 = -1;
                                                                      do
                                                                        ++v77;
                                                                      while ( v137[v77] );
                                                                      goto LABEL_318;
                                                                    }
                                                                  }
                                                                }
                                                                else
                                                                {
                                                                  v96 = 0;
                                                                  v95 = v74;
                                                                  if ( (_DWORD)xmmword_180169738
                                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                                    && qword_180169748 == (qword_180169748
                                                                                         & 0x4000000000000800LL) )
                                                                  {
                                                                    PlaiWhoAmI(v136, 0x4000000000000800uLL);
                                                                    v75 = -1;
                                                                    do
                                                                      ++v75;
                                                                    while ( v136[v75] );
                                                                    goto LABEL_318;
                                                                  }
                                                                }
                                                              }
                                                              else
                                                              {
                                                                v96 = 0;
                                                                v95 = v72;
                                                                if ( (_DWORD)xmmword_180169738
                                                                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                                  && qword_180169748 == (qword_180169748
                                                                                       & 0x4000000000000800LL) )
                                                                {
                                                                  PlaiWhoAmI(v135, 0x4000000000000800uLL);
                                                                  v73 = -1;
                                                                  do
                                                                    ++v73;
                                                                  while ( v135[v73] );
                                                                  goto LABEL_318;
                                                                }
                                                              }
                                                            }
                                                            else
                                                            {
                                                              v96 = 0;
                                                              v95 = v70;
                                                              if ( (_DWORD)xmmword_180169738
                                                                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                                && qword_180169748 == (qword_180169748
                                                                                     & 0x4000000000000800LL) )
                                                              {
                                                                PlaiWhoAmI(v134, 0x4000000000000800uLL);
                                                                v71 = -1;
                                                                do
                                                                  ++v71;
                                                                while ( v134[v71] );
                                                                goto LABEL_318;
                                                              }
                                                            }
                                                          }
                                                          else
                                                          {
                                                            v96 = 0;
                                                            v95 = v68;
                                                            if ( (_DWORD)xmmword_180169738
                                                              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                              && qword_180169748 == (qword_180169748
                                                                                   & 0x4000000000000800LL) )
                                                            {
                                                              PlaiWhoAmI(v133, 0x4000000000000800uLL);
                                                              v69 = -1;
                                                              do
                                                                ++v69;
                                                              while ( v133[v69] );
                                                              goto LABEL_318;
                                                            }
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v96 = 0;
                                                          v95 = v66;
                                                          if ( (_DWORD)xmmword_180169738
                                                            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                          {
                                                            PlaiWhoAmI(v132, 0x4000000000000800uLL);
                                                            v67 = -1;
                                                            do
                                                              ++v67;
                                                            while ( v132[v67] );
                                                            goto LABEL_318;
                                                          }
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v96 = 0;
                                                        v95 = v64;
                                                        if ( (_DWORD)xmmword_180169738
                                                          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                        {
                                                          PlaiWhoAmI(v131, 0x4000000000000800uLL);
                                                          v65 = -1;
                                                          do
                                                            ++v65;
                                                          while ( v131[v65] );
                                                          goto LABEL_318;
                                                        }
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v96 = 0;
                                                      v95 = v62;
                                                      if ( (_DWORD)xmmword_180169738
                                                        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                      {
                                                        PlaiWhoAmI(v130, 0x4000000000000800uLL);
                                                        v63 = -1;
                                                        do
                                                          ++v63;
                                                        while ( v130[v63] );
                                                        goto LABEL_318;
                                                      }
                                                    }
                                                  }
                                                  else
                                                  {
                                                    v96 = 0;
                                                    v95 = v60;
                                                    if ( (_DWORD)xmmword_180169738
                                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                    {
                                                      PlaiWhoAmI(v129, 0x4000000000000800uLL);
                                                      v61 = -1;
                                                      do
                                                        ++v61;
                                                      while ( v129[v61] );
                                                      goto LABEL_318;
                                                    }
                                                  }
                                                }
                                                else
                                                {
                                                  v96 = 0;
                                                  v95 = v58;
                                                  if ( (_DWORD)xmmword_180169738
                                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                  {
                                                    PlaiWhoAmI(v128, 0x4000000000000800uLL);
                                                    v59 = -1;
                                                    do
                                                      ++v59;
                                                    while ( v128[v59] );
                                                    goto LABEL_318;
                                                  }
                                                }
                                              }
                                              else
                                              {
                                                v96 = 0;
                                                v95 = v56;
                                                if ( (_DWORD)xmmword_180169738
                                                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                                {
                                                  PlaiWhoAmI(v127, 0x4000000000000800uLL);
                                                  v57 = -1;
                                                  do
                                                    ++v57;
                                                  while ( v127[v57] );
                                                  goto LABEL_318;
                                                }
                                              }
                                            }
                                            else
                                            {
                                              v96 = 0;
                                              v95 = v54;
                                              if ( (_DWORD)xmmword_180169738
                                                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                              {
                                                PlaiWhoAmI(v126, 0x4000000000000800uLL);
                                                v55 = -1;
                                                do
                                                  ++v55;
                                                while ( v126[v55] );
                                                goto LABEL_318;
                                              }
                                            }
                                          }
                                          else
                                          {
                                            v96 = 0;
                                            v95 = v52;
                                            if ( (_DWORD)xmmword_180169738
                                              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                            {
                                              PlaiWhoAmI(v125, 0x4000000000000800uLL);
                                              v53 = -1;
                                              do
                                                ++v53;
                                              while ( v125[v53] );
                                              goto LABEL_318;
                                            }
                                          }
                                        }
                                        else
                                        {
                                          v96 = 0;
                                          v95 = v50;
                                          if ( (_DWORD)xmmword_180169738
                                            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                          {
                                            PlaiWhoAmI(v124, 0x4000000000000800uLL);
                                            v51 = -1;
                                            do
                                              ++v51;
                                            while ( v124[v51] );
                                            goto LABEL_318;
                                          }
                                        }
                                      }
                                      else
                                      {
                                        v96 = 0;
                                        v95 = v48;
                                        if ( (_DWORD)xmmword_180169738
                                          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                        {
                                          PlaiWhoAmI(v123, 0x4000000000000800uLL);
                                          v49 = -1;
                                          do
                                            ++v49;
                                          while ( v123[v49] );
                                          goto LABEL_318;
                                        }
                                      }
                                    }
                                    else
                                    {
                                      v96 = 0;
                                      v95 = v46;
                                      if ( (_DWORD)xmmword_180169738
                                        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                      {
                                        PlaiWhoAmI(v122, 0x4000000000000800uLL);
                                        v47 = -1;
                                        do
                                          ++v47;
                                        while ( v122[v47] );
                                        goto LABEL_318;
                                      }
                                    }
                                  }
                                  else
                                  {
                                    v96 = 0;
                                    v95 = v44;
                                    if ( (_DWORD)xmmword_180169738
                                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                    {
                                      PlaiWhoAmI(v121, 0x4000000000000800uLL);
                                      v45 = -1;
                                      do
                                        ++v45;
                                      while ( v121[v45] );
                                      goto LABEL_318;
                                    }
                                  }
                                }
                                else
                                {
                                  v96 = 0;
                                  v95 = v42;
                                  if ( (_DWORD)xmmword_180169738
                                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                  {
                                    PlaiWhoAmI(v120, 0x4000000000000800uLL);
                                    v43 = -1;
                                    do
                                      ++v43;
                                    while ( v120[v43] );
                                    goto LABEL_318;
                                  }
                                }
                              }
                              else
                              {
                                v96 = 0;
                                v95 = v40;
                                if ( (_DWORD)xmmword_180169738
                                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                                {
                                  PlaiWhoAmI(v119, 0x4000000000000800uLL);
                                  v41 = -1;
                                  do
                                    ++v41;
                                  while ( v119[v41] );
                                  goto LABEL_318;
                                }
                              }
                            }
                            else
                            {
                              v96 = 0;
                              v95 = v38;
                              if ( (_DWORD)xmmword_180169738
                                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                              {
                                PlaiWhoAmI(v118, 0x4000000000000800uLL);
                                v39 = -1;
                                do
                                  ++v39;
                                while ( v118[v39] );
                                goto LABEL_318;
                              }
                            }
                          }
                          else
                          {
                            v96 = 0;
                            v95 = v36;
                            if ( (_DWORD)xmmword_180169738
                              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                            {
                              PlaiWhoAmI(v117, 0x4000000000000800uLL);
                              v37 = -1;
                              do
                                ++v37;
                              while ( v117[v37] );
                              goto LABEL_318;
                            }
                          }
                        }
                        else
                        {
                          v96 = 0;
                          v95 = v34;
                          if ( (_DWORD)xmmword_180169738
                            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                          {
                            PlaiWhoAmI(v116, 0x4000000000000800uLL);
                            v35 = -1;
                            do
                              ++v35;
                            while ( v116[v35] );
                            goto LABEL_318;
                          }
                        }
                      }
                      else
                      {
                        v96 = 0;
                        v95 = v32;
                        if ( (_DWORD)xmmword_180169738
                          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                        {
                          PlaiWhoAmI(v115, 0x4000000000000800uLL);
                          v33 = -1;
                          do
                            ++v33;
                          while ( v115[v33] );
                          goto LABEL_318;
                        }
                      }
                    }
                    else
                    {
                      v96 = 0;
                      v95 = v30;
                      if ( (_DWORD)xmmword_180169738
                        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                      {
                        PlaiWhoAmI(v114, 0x4000000000000800uLL);
                        v31 = -1;
                        do
                          ++v31;
                        while ( v114[v31] );
                        goto LABEL_318;
                      }
                    }
                  }
                  else
                  {
                    v96 = 0;
                    v95 = v28;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v113, 0x4000000000000800uLL);
                      v29 = -1;
                      do
                        ++v29;
                      while ( v113[v29] );
                      goto LABEL_318;
                    }
                  }
                }
                else
                {
                  v96 = 0;
                  v95 = v26;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v112, 0x4000000000000800uLL);
                    v27 = -1;
                    do
                      ++v27;
                    while ( v112[v27] );
                    goto LABEL_318;
                  }
                }
              }
              else
              {
                v96 = 0;
                v95 = v24;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v111, 0x4000000000000800uLL);
                  v25 = -1;
                  do
                    ++v25;
                  while ( v111[v25] );
                  goto LABEL_318;
                }
              }
            }
            else
            {
              v96 = 0;
              v95 = v22;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v110, 0x4000000000000800uLL);
                v23 = -1;
                do
                  ++v23;
                while ( v110[v23] );
                goto LABEL_318;
              }
            }
          }
          else
          {
            v96 = 0;
            v95 = v20;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v109, 0x4000000000000800uLL);
              v21 = -1;
              do
                ++v21;
              while ( v109[v21] );
              goto LABEL_318;
            }
          }
        }
        else
        {
          v96 = 0;
          v95 = v18;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v108, 0x4000000000000800uLL);
            v19 = -1;
            do
              ++v19;
            while ( v108[v19] );
            goto LABEL_318;
          }
        }
        goto LABEL_319;
      }
      v96 = 0;
      v95 = v15;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
LABEL_35:
        v3 = v99;
        v4 = v98;
        goto LABEL_319;
      }
      PlaiWhoAmI(v107, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v107[v17] );
    }
    else
    {
      v96 = 0;
      v95 = Xml;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_35;
      }
      PlaiWhoAmI(v106, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v106[v14] );
    }
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v95,
      4,
      qword_180147320,
      1,
      &v96,
      4,
      "_TraceDataCollector::get_Xml",
      29);
    goto LABEL_35;
  }
  v96 = 0;
  v95 = v9;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v104, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v104[v11] );
    goto LABEL_318;
  }
LABEL_319:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  PlaiVariantClear(&v97);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v3->lpVtbl->Release)(v3);
  if ( v100 )
    ((void (__fastcall *)(struct ITraceDataProviderCollection *))v100->lpVtbl->Release)(v100);
  return v7;
}

```

## disassembly

```asm
0x180072480  mov     [rsp-8+arg_10], rbx
0x180072485  push    rbp
0x180072486  push    rsi
0x180072487  push    rdi
0x180072488  push    r12
0x18007248a  push    r13
0x18007248c  push    r14
0x18007248e  push    r15
0x180072490  lea     rbp, [rsp-14E0h]
0x180072498  mov     eax, 15E0h
0x18007249d  call    _alloca_probe
0x1800724a2  sub     rsp, rax
0x1800724a5  mov     rax, cs:__security_cookie
0x1800724ac  xor     rax, rsp
0x1800724af  mov     [rbp+1510h+var_40], rax
0x1800724b6  xor     r12d, r12d
0x1800724b9  xorps   xmm0, xmm0
0x1800724bc  mov     rsi, rcx
0x1800724bf  mov     [rbp+1510h+var_1568], r12
0x1800724c3  xor     eax, eax
0x1800724c5  mov     [rbp+1510h+var_1570], r12
0x1800724c9  lea     rcx, [rbp+1510h+var_1590]; struct tagVARIANT *
0x1800724cd  mov     qword ptr [rbp+1510h+var_1590+10h], rax
0x1800724d1  movups  xmmword ptr [rbp+1510h+var_1590], xmm0
0x1800724d5  mov     r14d, r12d
0x1800724d8  mov     r15d, r12d
0x1800724db  movups  xmmword ptr [rbp+1510h+var_1558.Data1], xmm0
0x1800724df  mov     [rbp+1510h+var_1578], r12
0x1800724e3  mov     rdi, rdx
0x1800724e6  mov     [rsp+1610h+var_15A0], r12d
0x1800724eb  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800724f0  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800724f7  lea     r13d, [r12+4]
0x1800724fc  mov     eax, [rsi+38h]
0x1800724ff  mov     [rsp+1610h+var_1598], eax
0x180072503  mov     [rbp+1510h+var_1560], rsi
0x180072507  jz      short loc_180072578
0x180072509  mov     rdx, 4000000000000400h
0x180072513  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007251a  jz      short loc_180072578
0x18007251c  mov     rax, cs:qword_180169748
0x180072523  and     rax, rdx
0x180072526  cmp     cs:qword_180169748, rax
0x18007252d  jnz     short loc_180072578
0x18007252f  mov     [rsp+1610h+var_15D0], r13
0x180072534  lea     rax, [rsp+1610h+var_1598]
0x180072539  mov     [rsp+1610h+var_15D8], rax
0x18007253e  lea     r9, aTracedatacolle_29; "_TraceDataCollector::get_Xml"
0x180072545  lea     rax, [rbp+1510h+var_1560]
0x180072549  mov     [rsp+1610h+var_15E0], 8
0x180072552  mov     [rsp+1610h+var_15E8], rax
0x180072557  lea     r8d, [r12+3]
0x18007255c  lea     rdx, PLA_EVENT_METHOD
0x180072563  mov     [rsp+1610h+var_15F0], 1Dh
0x18007256c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180072573  call    EventingWriteEvent
0x180072578  cmp     [rsi+8], r12d
0x18007257c  jz      short loc_180072588
0x18007257e  lea     rcx, [rsi+10h]; lpCriticalSection
0x180072582  call    cs:__imp_EnterCriticalSection
0x180072588  mov     rax, [rsi]
0x18007258b  lea     rdx, [rbp+1510h+var_1568]
0x18007258f  mov     rcx, rsi
0x180072592  mov     rax, [rax+238h]
0x180072599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007259e  mov     ebx, eax
0x1800725a0  test    eax, eax
0x1800725a2  jns     loc_18007265F
0x1800725a8  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800725af  mov     [rsp+1610h+var_1598], r12d
0x1800725b4  mov     [rsp+1610h+var_15A0], eax
0x1800725b8  jz      loc_180073FE6
0x1800725be  mov     rdx, 4000000000000800h; unsigned __int64
0x1800725c8  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800725cf  jz      loc_180073FE6
0x1800725d5  mov     rax, cs:qword_180169748
0x1800725dc  and     rax, rdx
0x1800725df  cmp     cs:qword_180169748, rax
0x1800725e6  jnz     loc_180073FE6
0x1800725ec  lea     rcx, [rbp+1510h+var_1540]; unsigned __int16 *
0x1800725f0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800725f5  lea     rcx, [rbp+1510h+var_1540]
0x1800725f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800725fd  inc     rax
0x180072600  cmp     [rcx+rax*2], r12w
0x180072605  jnz     short loc_1800725FD
0x180072607  lea     ecx, [rax+rax]
0x18007260a  lea     rax, [rbp+1510h+var_1540]
0x18007260e  add     rcx, 2
0x180072612  mov     [rsp+1610h+var_15B0], rcx
0x180072617  mov     [rsp+1610h+var_15B8], rax
0x18007261c  lea     rax, aTracedatacolle_29; "_TraceDataCollector::get_Xml"
0x180072623  mov     [rsp+1610h+var_15C0], 1Dh
0x18007262c  mov     [rsp+1610h+var_15C8], rax
0x180072631  lea     rax, [rsp+1610h+var_1598]
0x180072636  mov     [rsp+1610h+var_15D0], r13
0x18007263b  mov     [rsp+1610h+var_15D8], rax
0x180072640  lea     rax, qword_180147320
0x180072647  mov     [rsp+1610h+var_15E0], 1
0x180072650  mov     [rsp+1610h+var_15E8], rax
0x180072655  mov     [rsp+1610h+var_15F0], r13
0x18007265a  jmp     loc_180073FC8
0x18007265f  mov     rdx, [rbp+1510h+var_1568]; struct ITraceDataProviderCollection *
0x180072663  lea     rcx, [rsp+1610h+var_15A0]; int *
0x180072668  call    ?ValidateProviderList@TraceDataProviderCollection@@SAJPEAJPEAUITraceDataProviderCollection@@@Z; TraceDataProviderCollection::ValidateProviderList(long *,ITraceDataProviderCollection *)
0x18007266d  mov     ebx, eax
0x18007266f  test    eax, eax
0x180072671  jns     short loc_1800726DE
0x180072673  cmp     dword ptr cs:xmmword_180169738, r12d
0x18007267a  mov     [rsp+1610h+var_1598], r12d
0x18007267f  mov     [rsp+1610h+var_15A0], eax
0x180072683  jz      loc_180073FE6
0x180072689  mov     rdx, 4000000000000800h; unsigned __int64
0x180072693  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007269a  jz      loc_180073FE6
0x1800726a0  mov     rax, cs:qword_180169748
0x1800726a7  and     rax, rdx
0x1800726aa  cmp     cs:qword_180169748, rax
0x1800726b1  jnz     loc_180073FE6
0x1800726b7  lea     rcx, [rbp+1510h+var_14C0]; unsigned __int16 *
0x1800726bb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800726c0  lea     rcx, [rbp+1510h+var_14C0]
0x1800726c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800726c8  inc     rax
0x1800726cb  cmp     [rcx+rax*2], r12w
0x1800726d0  jnz     short loc_1800726C8
0x1800726d2  lea     ecx, [rax+rax]
0x1800726d5  lea     rax, [rbp+1510h+var_14C0]
0x1800726d9  jmp     loc_18007260E
0x1800726de  mov     eax, [rsp+1610h+var_15A0]
0x1800726e2  test    eax, eax
0x1800726e4  jns     short loc_18007275A
0x1800726e6  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800726ed  mov     [rsp+1610h+var_1598], r12d
0x1800726f2  mov     [rsp+1610h+var_15A0], eax
0x1800726f6  jz      loc_180073FE6
0x1800726fc  mov     rdx, 4000000000000800h; unsigned __int64
0x180072706  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007270d  jz      loc_180073FE6
0x180072713  mov     rax, cs:qword_180169748
0x18007271a  and     rax, rdx
0x18007271d  cmp     cs:qword_180169748, rax
0x180072724  jnz     loc_180073FE6
0x18007272a  lea     rcx, [rbp+1510h+var_1440]; unsigned __int16 *
0x180072731  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180072736  lea     rcx, [rbp+1510h+var_1440]
0x18007273d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180072741  inc     rax
0x180072744  cmp     [rcx+rax*2], r12w
0x180072749  jnz     short loc_180072741
0x18007274b  lea     ecx, [rax+rax]
0x18007274e  lea     rax, [rbp+1510h+var_1440]
0x180072755  jmp     loc_18007260E
0x18007275a  lea     r9, [rbp+1510h+var_1570]
0x18007275e  mov     rcx, rsi
0x180072761  lea     r8, [rbp+1510h+var_1578]
0x180072765  call    ?CommonGetXml@?$_DataCollector@UITraceDataCollector@@@@IEAAJPEBGPEAPEAUIXMLDOMNode@@PEAPEAUIXMLDOMDocument@@@Z; _DataCollector<ITraceDataCollector>::CommonGetXml(ushort const *,IXMLDOMNode * *,IXMLDOMDocument * *)
0x18007276a  mov     ebx, eax
0x18007276c  test    eax, eax
0x18007276e  jns     loc_18007285A
0x180072774  cmp     dword ptr cs:xmmword_180169738, r12d
0x18007277b  mov     [rsp+1610h+var_1598], r12d
0x180072780  mov     [rsp+1610h+var_15A0], eax
0x180072784  jz      loc_18007284D
0x18007278a  mov     rdx, 4000000000000800h; unsigned __int64
0x180072794  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007279b  jz      loc_18007284D
0x1800727a1  mov     rax, cs:qword_180169748
0x1800727a8  and     rax, rdx
0x1800727ab  cmp     cs:qword_180169748, rax
0x1800727b2  jnz     loc_18007284D
0x1800727b8  lea     rcx, [rbp+1510h+var_13C0]; unsigned __int16 *
0x1800727bf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800727c4  lea     rcx, [rbp+1510h+var_13C0]
0x1800727cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800727cf  inc     rax
0x1800727d2  cmp     [rcx+rax*2], r12w
0x1800727d7  jnz     short loc_1800727CF
0x1800727d9  lea     ecx, [rax+rax]
0x1800727dc  lea     rax, [rbp+1510h+var_13C0]
0x1800727e3  add     rcx, 2
0x1800727e7  lea     r9, [rsp+1610h+var_15A0]
0x1800727ec  mov     [rsp+1610h+var_15B0], rcx
0x1800727f1  lea     rdx, PLA_EVENT_ERROR
0x1800727f8  mov     [rsp+1610h+var_15B8], rax
0x1800727fd  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180072804  mov     [rsp+1610h+var_15C0], 1Dh
0x18007280d  lea     rax, aTracedatacolle_29; "_TraceDataCollector::get_Xml"
0x180072814  mov     [rsp+1610h+var_15C8], rax
0x180072819  mov     r8d, 5
0x18007281f  mov     [rsp+1610h+var_15D0], r13
0x180072824  lea     rax, [rsp+1610h+var_1598]
0x180072829  mov     [rsp+1610h+var_15D8], rax
0x18007282e  lea     rax, qword_180147320
0x180072835  mov     [rsp+1610h+var_15E0], 1
0x18007283e  mov     [rsp+1610h+var_15E8], rax
0x180072843  mov     [rsp+1610h+var_15F0], r13
0x180072848  call    EventingWriteEvent
0x18007284d  mov     r14, [rbp+1510h+var_1570]
0x180072851  mov     r15, [rbp+1510h+var_1578]
0x180072855  jmp     loc_180073FE6
0x18007285a  mov     rax, [rsi]
0x18007285d  lea     rdx, [rbp+1510h+var_1558]
0x180072861  mov     rcx, rsi
0x180072864  mov     rax, [rax+180h]
0x18007286b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072870  mov     ebx, eax
0x180072872  test    eax, eax
0x180072874  jns     short loc_1800728DE
0x180072876  cmp     dword ptr cs:xmmword_180169738, r12d
0x18007287d  mov     [rsp+1610h+var_1598], r12d
0x180072882  mov     [rsp+1610h+var_15A0], eax
0x180072886  jz      short loc_18007284D
0x180072888  mov     rdx, 4000000000000800h; unsigned __int64
0x180072892  test    qword ptr cs:xmmword_180169738+8, rdx
0x180072899  jz      short loc_18007284D
0x18007289b  mov     rax, cs:qword_180169748
0x1800728a2  and     rax, rdx
0x1800728a5  cmp     cs:qword_180169748, rax
0x1800728ac  jnz     short loc_18007284D
0x1800728ae  lea     rcx, [rbp+1510h+var_1340]; unsigned __int16 *
0x1800728b5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800728ba  lea     rcx, [rbp+1510h+var_1340]
0x1800728c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800728c5  inc     rax
0x1800728c8  cmp     [rcx+rax*2], r12w
0x1800728cd  jnz     short loc_1800728C5
0x1800728cf  lea     ecx, [rax+rax]
0x1800728d2  lea     rax, [rbp+1510h+var_1340]
0x1800728d9  jmp     loc_1800727E3
0x1800728de  mov     r15, [rbp+1510h+var_1578]
0x1800728e2  lea     r9, [rbp+1510h+var_1558]; struct _GUID *
0x1800728e6  mov     r14, [rbp+1510h+var_1570]
0x1800728ea  mov     r8, r15; struct IXMLDOMNode *
0x1800728ed  mov     rdx, r14; struct IXMLDOMDocument *
0x1800728f0  call    ?PlaiWriteXmlGuid@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAU_GUID@@@Z; PlaiWriteXmlGuid(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,_GUID *)
0x1800728f5  mov     ebx, eax
0x1800728f7  test    eax, eax
0x1800728f9  jns     short loc_18007296F
0x1800728fb  cmp     dword ptr cs:xmmword_180169738, r12d
0x180072902  mov     [rsp+1610h+var_1598], r12d
0x180072907  mov     [rsp+1610h+var_15A0], eax
0x18007290b  jz      loc_180073FE6
0x180072911  mov     rdx, 4000000000000800h; unsigned __int64
0x18007291b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180072922  jz      loc_180073FE6
0x180072928  mov     rax, cs:qword_180169748
0x18007292f  and     rax, rdx
0x180072932  cmp     cs:qword_180169748, rax
0x180072939  jnz     loc_180073FE6
0x18007293f  lea     rcx, [rbp+1510h+var_12C0]; unsigned __int16 *
0x180072946  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007294b  lea     rcx, [rbp+1510h+var_12C0]
0x180072952  or      rax, 0FFFFFFFFFFFFFFFFh
0x180072956  inc     rax
0x180072959  cmp     [rcx+rax*2], r12w
0x18007295e  jnz     short loc_180072956
0x180072960  lea     ecx, [rax+rax]
0x180072963  lea     rax, [rbp+1510h+var_12C0]
0x18007296a  jmp     loc_18007260E
0x18007296f  lea     rcx, [rbp+1510h+var_1590]; struct tagVARIANT *
0x180072973  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x180072978  mov     rax, [rsi]
0x18007297b  lea     rdx, [rbp+1510h+var_1590+8]
0x18007297f  mov     rcx, rsi
0x180072982  mov     rax, [rax+100h]
0x180072989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007298e  mov     ebx, eax
0x180072990  test    eax, eax
0x180072992  jns     short loc_180072A08
0x180072994  cmp     dword ptr cs:xmmword_180169738, r12d
0x18007299b  mov     [rsp+1610h+var_1598], r12d
0x1800729a0  mov     [rsp+1610h+var_15A0], eax
0x1800729a4  jz      loc_180073FE6
0x1800729aa  mov     rdx, 4000000000000800h; unsigned __int64
0x1800729b4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800729bb  jz      loc_180073FE6
0x1800729c1  mov     rax, cs:qword_180169748
0x1800729c8  and     rax, rdx
0x1800729cb  cmp     cs:qword_180169748, rax
0x1800729d2  jnz     loc_180073FE6
0x1800729d8  lea     rcx, [rbp+1510h+var_1240]; unsigned __int16 *
0x1800729df  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800729e4  lea     rcx, [rbp+1510h+var_1240]
0x1800729eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800729ef  inc     rax
0x1800729f2  cmp     [rcx+rax*2], r12w
0x1800729f7  jnz     short loc_1800729EF
0x1800729f9  lea     ecx, [rax+rax]
0x1800729fc  lea     rax, [rbp+1510h+var_1240]
0x180072a03  jmp     loc_18007260E
0x180072a08  mov     r13d, 300100h
0x180072a0e  mov     eax, 13h
0x180072a13  mov     word ptr [rbp+1510h+var_1590], ax
0x180072a17  cmp     ebx, r13d
0x180072a1a  jz      loc_180072AB0
0x180072a20  lea     r9, [rbp+1510h+var_1590]; struct tagVARIANT *
0x180072a24  mov     r8, r15; struct IXMLDOMNode *
0x180072a27  mov     rdx, r14; struct IXMLDOMDocument *
0x180072a2a  lea     rcx, aBuffersize; "BufferSize"
  ... truncated ...
```
