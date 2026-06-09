# CNode::GetTaskEnumerator(ushort *,IEnumTASK * *)

- ea: `0x18004e214`
- end: `0x18004eedf`
- name: `?GetTaskEnumerator@CNode@@QEAAJPEAGPEAPEAUIEnumTASK@@@Z`
- size: `3275`
- prototype: `__int64 __fastcall(CNode *__hidden this, unsigned __int16 *, struct IEnumTASK **)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800eabe0`

## callees

- `0x18000f228`
- `0x180013ac0`
- `0x1800163ac`
- `0x180016ba0`
- `0x180016bd4`
- `0x180017ed4`
- `0x180024a98`
- `0x180024fd0`
- `0x180026694`
- `0x180026a08`
- `0x180026af8`
- `0x180026ed4`
- `0x1800288b0`
- `0x18002a844`
- `0x18002ad38`
- `0x18003476c`
- `0x180035cd4`
- `0x18003a6c8`
- `0x18004276c`
- `0x180048018`
- `0x18004e214`
- `0x18004eee8`
- `0x180050358`
- `0x180050afc`
- `0x180054e70`
- `0x180055218`
- `0x180057074`
- `0x18005714c`
- `0x18006caec`
- `0x1800711a4`
- `0x1800743b4`
- `0x1800a4f04`
- `0x1800a5af0`
- `0x1800aa864`
- `0x1800c1400`
- `0x180124c60`
- `0x180134502`
- `0x180134540`
- `0x18013f010`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18004e25c`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18004e25c`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x18004e973`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x18004e999`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x18004e973`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x18004e999`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x18004e662`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x18004e92c`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x18004e662`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x18004e92c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004e921`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004e921`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18004e64c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18004e94e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18004e64c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18004e94e`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18004e26f`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18004e26f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18004e838`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18004e964`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18004e838`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18004e964`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e382`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e657`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e847`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e87b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e959`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004edc1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004eeaa`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e382`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e657`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e847`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e87b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004e959`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004edc1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004eeaa`

## string_xrefs

- `0x18004e71f`: `IComponentData`
- `0x18004e263`: `CNode::GetTaskEnumerator`
- `0x18004e410`: `IEnumTASK`
- `0x18004e57a`: `IEnumTASK`
- `0x18004eb98`: `IEnumTASK`
- `0x18004e328`: `IExtendTaskPad`
- `0x18004ea01`: `IExtendTaskPad`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CNode::GetTaskEnumerator(CMTNode **this, unsigned __int16 *a2, struct IEnumTASK **a3)
{
  CMTNode *v6; // rdi
  struct CMTSnapInNode *StaticParent; // r12
  _QWORD *v8; // r14
  int NodeType; // ebx
  CMTNode *v10; // rbx
  enum _DATA_OBJECT_TYPES v12; // edx
  int v13; // edi
  struct IUnknown *v14; // rax
  struct IUnknown *v15; // r13
  __int64 v16; // rbx
  int v17; // ebx
  __int64 v18; // rax
  struct CSnapInReference *v19; // rbx
  struct CComponentData *ComponentData; // r12
  int SnapIn; // eax
  struct CXMLObject *v22; // rbx
  __int64 SnapInReference; // rax
  CComponentData *v24; // rax
  CComponentData *v25; // rax
  struct CMTNode *v26; // rbx
  struct HMTNODE__ *v27; // rax
  unsigned int v28; // eax
  __int64 inited; // rax
  CNode *v30; // rbx
  struct CSnapIn *Component; // rax
  __int16 v32; // r14
  int v33; // edi
  int v34; // esi
  __int64 v35; // rbx
  struct HMTNODE__ *v36; // rax
  int v37; // eax
  int v38; // [rsp+30h] [rbp-D0h]
  struct IDataObject *v39; // [rsp+40h] [rbp-C0h] BYREF
  struct CSnapIn *v40; // [rsp+48h] [rbp-B8h] BYREF
  void **v41; // [rsp+50h] [rbp-B0h] BYREF
  struct CSnapInReference *v42; // [rsp+58h] [rbp-A8h]
  struct CMTNode *v43; // [rsp+60h] [rbp-A0h]
  void **v44; // [rsp+68h] [rbp-98h] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h]
  _BYTE v46[24]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v47; // [rsp+90h] [rbp-70h] BYREF
  int v48; // [rsp+98h] [rbp-68h]
  __int64 v49; // [rsp+9Ch] [rbp-64h]
  void **v50; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h]
  CNode *v52; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v53; // [rsp+C0h] [rbp-40h]
  void **v54; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-30h]
  _BYTE v56[24]; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v57[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v58; // [rsp+120h] [rbp+20h]
  __int128 v59; // [rsp+130h] [rbp+30h]
  __int64 v60; // [rsp+140h] [rbp+40h]
  __int64 v61; // [rsp+150h] [rbp+50h]
  _QWORD v62[3]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v63[24]; // [rsp+178h] [rbp+78h] BYREF
  void **v64; // [rsp+190h] [rbp+90h] BYREF
  __int64 v65; // [rsp+198h] [rbp+98h]
  __int64 v66; // [rsp+1A0h] [rbp+A0h]
  int v67; // [rsp+1A8h] [rbp+A8h]
  __int64 v68; // [rsp+1B0h] [rbp+B0h]
  GUID v69; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v70; // [rsp+1C8h] [rbp+C8h]
  __int64 v71; // [rsp+1D0h] [rbp+D0h]
  char v72; // [rsp+1D8h] [rbp+D8h]
  void **v73; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v74; // [rsp+1E8h] [rbp+E8h]
  __int64 v75; // [rsp+1F0h] [rbp+F0h]
  int v76; // [rsp+1F8h] [rbp+F8h]
  __int64 v77; // [rsp+200h] [rbp+100h]
  GUID v78; // [rsp+208h] [rbp+108h]
  const wchar_t *v79; // [rsp+218h] [rbp+118h]
  __int64 v80; // [rsp+220h] [rbp+120h]
  char v81; // [rsp+228h] [rbp+128h]
  _QWORD v82[3]; // [rsp+230h] [rbp+130h] BYREF
  int v83; // [rsp+248h] [rbp+148h]
  __int64 v84; // [rsp+250h] [rbp+150h]
  GUID v85; // [rsp+258h] [rbp+158h]
  const wchar_t *v86; // [rsp+268h] [rbp+168h]
  __int64 v87; // [rsp+270h] [rbp+170h]
  char v88; // [rsp+278h] [rbp+178h]
  void **v89; // [rsp+280h] [rbp+180h] BYREF
  __int64 v90; // [rsp+288h] [rbp+188h]
  __int64 v91; // [rsp+290h] [rbp+190h]
  int v92; // [rsp+298h] [rbp+198h]
  __int64 v93; // [rsp+2A0h] [rbp+1A0h]
  GUID v94; // [rsp+2A8h] [rbp+1A8h]
  const wchar_t *v95; // [rsp+2B8h] [rbp+1B8h]
  __int64 v96; // [rsp+2C0h] [rbp+1C0h]
  char v97; // [rsp+2C8h] [rbp+1C8h]
  struct _GUID v98; // [rsp+2D0h] [rbp+1D0h] BYREF
  _QWORD v99[3]; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v100; // [rsp+2F8h] [rbp+1F8h]
  __int64 v101; // [rsp+300h] [rbp+200h]
  GUID v102; // [rsp+308h] [rbp+208h]
  const unsigned __int16 *v103; // [rsp+318h] [rbp+218h]
  __int64 v104; // [rsp+320h] [rbp+220h]
  char v105; // [rsp+328h] [rbp+228h]
  _QWORD v106[3]; // [rsp+330h] [rbp+230h] BYREF
  int v107; // [rsp+348h] [rbp+248h]
  __int64 v108; // [rsp+350h] [rbp+250h]
  GUID v109; // [rsp+358h] [rbp+258h]
  const wchar_t *v110; // [rsp+368h] [rbp+268h]
  __int64 v111; // [rsp+370h] [rbp+270h]
  char v112; // [rsp+378h] [rbp+278h]

  v53 = a2;
  v52 = (CNode *)this;
  mmcerror::SC::SC((mmcerror::SC *)v46, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v46, L"CNode::GetTaskEnumerator");
  if ( a2 && a3 )
  {
    *a3 = 0;
    if ( !this[7] )
      goto LABEL_8;
    v6 = this[3];
    StaticParent = CMTNode::GetStaticParent(v6);
    v43 = StaticParent;
    v8 = (_QWORD *)*((_QWORD *)v6 + 32);
    v98 = 0;
    NodeType = CMTNode::GetNodeType(v6, &v98);
    if ( NodeType < 0 )
    {
LABEL_9:
      mmcerror::SC::~SC((mmcerror::SC *)v46);
      return (unsigned int)NodeType;
    }
    v10 = this[7];
    if ( !v10 )
    {
LABEL_8:
      NodeType = 1;
      goto LABEL_9;
    }
    memset_0(&v64, 0, 0x50u);
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v68 = 72;
    v69 = GUID_8dee6511_554d_11d1_9fea_00600832db4a;
    v70 = L"IExtendTaskPad";
    v71 = 0;
    v72 = 0;
    v64 = &IExtendTaskPadWrapper::`vftable';
    TSnapinInterfaceWrapper<ISnapinHelp2,2>::Assign((SnapinInterfaceWrapper *)&v64, (CMTNode *)((char *)v10 + 16));
    if ( !v65 )
    {
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v64);
      goto LABEL_8;
    }
    v39 = 0;
    ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&v39);
    v39 = 0;
    NodeType = CMTNode::QueryDataObject(v6, v12, &v39);
    if ( NodeType < 0 )
    {
      ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&v39);
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v64);
      goto LABEL_9;
    }
    memset_0(v82, 0, 0x50u);
    v82[1] = 0;
    v82[2] = 0;
    v83 = 0;
    v84 = 56;
    v85 = GUID_338698b1_5a02_11d1_9fec_00600832db4a;
    v86 = L"IEnumTASK";
    v87 = 0;
    v88 = 0;
    v82[0] = &IEnumTASKWrapper::`vftable';
    v13 = ((__int64 (__fastcall *)(void ***, struct IDataObject *, unsigned __int16 *, _QWORD *))v64[2])(
            &v64,
            v39,
            a2,
            v82);
    if ( v13 < 0 )
    {
LABEL_13:
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)v82);
      ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&v39);
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v64);
      NodeType = v13;
      goto LABEL_9;
    }
    v14 = (struct IUnknown *)operator new(0x78u);
    v15 = v14;
    v40 = (struct CSnapIn *)v14;
    if ( v14 )
    {
      LODWORD(v14[1].lpVtbl) = 0;
      *(_OWORD *)&v14[2].lpVtbl = 0;
      *(_OWORD *)&v14[4].lpVtbl = 0;
      v14[6].lpVtbl = 0;
      LOBYTE(v14[7].lpVtbl) = 0;
      LODWORD(v14[10].lpVtbl) = 0;
      v14[11].lpVtbl = 0;
      v14[9].lpVtbl = 0;
      v14[8].lpVtbl = 0;
      v14[12].lpVtbl = 0;
      LODWORD(v14[13].lpVtbl) = 10;
      v14[14].lpVtbl = 0;
      v14->lpVtbl = (struct IUnknownVtbl *)&ATL::CComObject<CTaskEnumerator>::`vftable';
      _InterlockedIncrement(&dword_1801C7678);
    }
    else
    {
      v15 = 0;
    }
    CComponentData::GetSnapInReference(v8, &v44);
    v16 = v45;
    if ( !v45 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 32, WPP_5e286a5d0e1f3971b95362f9cca1ca0a_Traceguids);
      v44 = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v44);
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)v82);
      ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&v39);
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v64);
      NodeType = -2147023537;
      goto LABEL_9;
    }
    CTaskEnumerator::AddTaskEnumerator(v15, v45, v82);
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 72LL))(v16);
    memset_0(&v89, 0, 0x50u);
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 56;
    v94 = GUID_338698b1_5a02_11d1_9fec_00600832db4a;
    v95 = L"IEnumTASK";
    v96 = 0;
    v97 = 0;
    v89 = &IEnumTASKWrapper::`vftable';
    TSnapinInterfaceWrapper<IEnumTASK,4>::Assign((SnapinInterfaceWrapper *)&v89, v15, v17);
    if ( v90 )
      *a3 = (struct IEnumTASK *)SnapinInterfaceWrapper::Detach((SnapinInterfaceWrapper *)&v89);
    v47 = 0;
    v49 = 0;
    v48 = 0;
    ExtractDynExtensions(v39, &v47);
    memset(v57, 0, sizeof(v57));
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v18 = CExtensionsIterator::ScInitialize(v57, v56, *v8, &v98, L"Task", v47, v48);
    mmcerror::SC::operator=(v46, v18);
    mmcerror::SC::~SC((mmcerror::SC *)v56);
    if ( mmcerror::SC::IsError((mmcerror::SC *)v46)
      || (unsigned int)CExtensionsIterator::IsEnd((CExtensionsIterator *)v57) == 1 )
    {
      CExtensionsIterator::~CExtensionsIterator((CExtensionsIterator *)v57);
      CArray<_GUID,_GUID &>::~CArray<_GUID,_GUID &>(&v47);
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v89);
      v44 = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v44);
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)v82);
      ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&v39);
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v64);
      NodeType = 0;
      goto LABEL_9;
    }
    while ( 1 )
    {
      if ( (unsigned int)CExtensionsIterator::IsEnd((CExtensionsIterator *)v57) )
      {
        CExtensionsIterator::~CExtensionsIterator((CExtensionsIterator *)v57);
        CArray<_GUID,_GUID &>::~CArray<_GUID,_GUID &>(&v47);
        SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v89);
        v44 = &CSnapInReferencePtr::`vftable';
        CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v44);
        SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)v82);
        ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&v39);
        SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v64);
        mmcerror::SC::~SC((mmcerror::SC *)v46);
        return 0;
      }
      CExtensionsIterator::GetSnapInReference(v57, &v41);
      v19 = v42;
      if ( !v42 )
        break;
      ComponentData = CMTSnapInNode::GetComponentData(StaticParent, v42);
      if ( !ComponentData )
        goto LABEL_26;
LABEL_45:
      if ( !*((_QWORD *)ComponentData + 11) )
      {
        v26 = v43;
        v27 = CMTNode::ToHandle(v43);
        v28 = CComponentData::Init(ComponentData, v27);
        mmcerror::SC::operator=(v46, v28);
        if ( mmcerror::SC::IsError((mmcerror::SC *)v46) )
        {
          CMTSnapInNode::CompressComponentDataArray(v26);
          mmcerror::SC::TraceAndClear((mmcerror::SC *)v46);
          v41 = &CSnapInReferencePtr::`vftable';
          CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v41);
          goto LABEL_77;
        }
        inited = CMTSnapInNode::ScInitIComponentData(v26, v63, ComponentData);
        mmcerror::SC::operator=(v46, inited);
        mmcerror::SC::~SC((mmcerror::SC *)v63);
        if ( (unsigned __int8)mmcerror::SC::operator bool(v46) )
        {
          mmcerror::SC::TraceAndClear((mmcerror::SC *)v46);
          v41 = &CSnapInReferencePtr::`vftable';
          CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v41);
          goto LABEL_77;
        }
      }
LABEL_50:
      memset_0(&v73, 0, 0x50u);
      v74 = 0;
      v75 = 0;
      v76 = 0;
      v77 = 72;
      v78 = GUID_8dee6511_554d_11d1_9fea_00600832db4a;
      v79 = L"IExtendTaskPad";
      v80 = 0;
      v81 = 0;
      v73 = &IExtendTaskPadWrapper::`vftable';
      if ( ComponentData )
      {
        v30 = v52;
        Component = CMTSnapInNode::GetComponent(
                      v43,
                      *(_DWORD *)(*((_QWORD *)v52 + 5) + 88LL),
                      *((_DWORD *)ComponentData + 24),
                      *(struct CSnapIn **)ComponentData);
        v40 = Component;
        if ( Component )
        {
          if ( !*((_QWORD *)Component + 12) )
          {
            v32 = *((_WORD *)ComponentData + 51);
            v33 = *(_DWORD *)(*((_QWORD *)v30 + 5) + 88LL);
            v34 = *((_DWORD *)ComponentData + 24);
            v35 = (**(__int64 (__fastcall ***)(CNode *))v30)(v30);
            v36 = CMTNode::ToHandle(v43);
            LOWORD(v38) = v32;
            v13 = CComponent::Init(v40, (char *)ComponentData + 8, v36, v35, v34, v33, v38);
            if ( v13 < 0 )
            {
              SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v73);
              v41 = &CSnapInReferencePtr::`vftable';
              CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v41);
              CExtensionsIterator::~CExtensionsIterator((CExtensionsIterator *)v57);
              CArray<_GUID,_GUID &>::~CArray<_GUID,_GUID &>(&v47);
              SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v89);
              v44 = &CSnapInReferencePtr::`vftable';
              CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v44);
              goto LABEL_13;
            }
            Component = v40;
          }
          TSnapinInterfaceWrapper<ISnapinHelp2,2>::Assign(
            (SnapinInterfaceWrapper *)&v73,
            (struct CSnapIn *)((char *)Component + 16));
        }
      }
      else
      {
        CExtensionsIterator::GetSnapInReference(v57, &v50);
        if ( v51 )
        {
          v37 = (*(__int64 (__fastcall **)(__int64, GUID *, void ***))(*(_QWORD *)v51 + 16LL))(
                  v51,
                  &IID_IExtendTaskPad,
                  &v73);
          v13 = v37;
          if ( v37 < 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                35,
                WPP_5e286a5d0e1f3971b95362f9cca1ca0a_Traceguids,
                (unsigned int)v37);
LABEL_72:
            v50 = &CSnapInReferencePtr::`vftable';
            CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v50);
            SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v73);
            v41 = &CSnapInReferencePtr::`vftable';
            CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v41);
            goto LABEL_77;
          }
        }
        else
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, WPP_5e286a5d0e1f3971b95362f9cca1ca0a_Traceguids);
          if ( v13 < 0 )
            goto LABEL_72;
        }
        v50 = &CSnapInReferencePtr::`vftable';
        CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v50);
      }
      if ( v74 )
      {
        memset_0(v106, 0, 0x50u);
        v106[1] = 0;
        v106[2] = 0;
        v107 = 0;
        v108 = 56;
        v109 = GUID_338698b1_5a02_11d1_9fec_00600832db4a;
        v110 = L"IEnumTASK";
        v111 = 0;
        v112 = 0;
        v106[0] = &IEnumTASKWrapper::`vftable';
        if ( !((unsigned int (__fastcall *)(void ***, struct IDataObject *, unsigned __int16 *, _QWORD *))v73[2])(
                &v73,
                v39,
                v53,
                v106) )
        {
          CExtensionsIterator::GetSnapInReference(v57, &v54);
          if ( v55 )
          {
            CTaskEnumerator::AddTaskEnumerator(v15, v55, v106);
          }
          else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 37, WPP_5e286a5d0e1f3971b95362f9cca1ca0a_Traceguids);
          }
          v54 = &CSnapInReferencePtr::`vftable';
          CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v54);
        }
        SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)v106);
      }
      SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)&v73);
      v41 = &CSnapInReferencePtr::`vftable';
      CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v41);
LABEL_77:
      CExtensionsIterator::Advance((CExtensionsIterator *)v57);
      StaticParent = v43;
    }
    ComponentData = 0;
LABEL_26:
    memset_0(v99, 0, 0x50u);
    v99[1] = 0;
    v99[2] = 0;
    v100 = 0;
    v101 = 80;
    v102 = GUID_955ab28a_5218_11d0_a985_00c04fd8d565;
    v103 = L"IComponentData";
    v104 = 0;
    v105 = 0;
    v99[0] = &IComponentDataWrapper::`vftable';
    if ( v19 )
    {
      SnapIn = CreateSnapIn(v19, (SnapinInterfaceWrapper *)v99, 0, 0);
      v13 = SnapIn;
      if ( SnapIn >= 0 )
      {
        v40 = 0;
        if ( *((_QWORD *)&v58 + 1) )
        {
          _com_ptr_t<_com_IIID<CSnapIn,&_GUID const IID_CSnapIn>>::operator=(
            &v40,
            *(_QWORD *)(*((_QWORD *)&v58 + 1) + 8LL));
        }
        else
        {
          v22 = qword_1801B7258;
          ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&v40);
          v40 = 0;
          SnapInReference = CExtensionsIterator::GetSnapInReference(v57, v62);
          CSnapInsCache::ScGetSnapIn(v22, v56, SnapInReference, &v40);
          v62[0] = &CSnapInReferencePtr::`vftable';
          CSnapInReferencePtr::Clear((CSnapInReferencePtr *)v62);
          if ( (unsigned __int8)mmcerror::SC::operator bool(v56) )
          {
            mmcerror::SC::~SC((mmcerror::SC *)v56);
            ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&v40);
            SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)v99);
            v41 = &CSnapInReferencePtr::`vftable';
            CSnapInReferencePtr::Clear((CSnapInReferencePtr *)&v41);
            goto LABEL_77;
          }
          mmcerror::SC::~SC((mmcerror::SC *)v56);
        }
        v24 = (CComponentData *)operator new(0x68u);
        v62[2] = v24;
        if ( v24 )
        {
          v25 = CComponentData::CComponentData(v24, v40);
          ComponentData = v25;
          if ( v25 )
          {
            TSnapinInterfaceWrapper<IComponentData,7>::Assign(
              (CComponentData *)((char *)v25 + 8),
              (struct SnapinInterfaceWrapper *)v99);
            CMTSnapInNode::AddComponentDataToArray(v43, ComponentData);
          }
        }
        else
        {
          ComponentData = 0;
        }
        ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&v40);
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          33,
          (unsigned int)WPP_5e286a5d0e1f3971b95362f9cca1ca0a_Traceguids,
          *((_QWORD *)v19 + 3),
          SnapIn);
      }
    }
    else
    {
      v13 = -2147023537;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_5e286a5d0e1f3971b95362f9cca1ca0a_Traceguids);
    }
    SnapinInterfaceWrapper::~SnapinInterfaceWrapper((SnapinInterfaceWrapper *)v99);
    if ( !ComponentData )
      goto LABEL_50;
    goto LABEL_45;
  }
  mmcerror::SC::~SC((mmcerror::SC *)v46);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18004e214  mov     [rsp-8+arg_18], rbx
0x18004e219  push    rbp
0x18004e21a  push    rsi
0x18004e21b  push    rdi
0x18004e21c  push    r12
0x18004e21e  push    r13
0x18004e220  push    r14
0x18004e222  push    r15
0x18004e224  lea     rbp, [rsp-290h]
0x18004e22c  sub     rsp, 390h
0x18004e233  mov     rax, cs:__security_cookie
0x18004e23a  xor     rax, rsp
0x18004e23d  mov     [rbp+2C0h+var_40], rax
0x18004e244  mov     rsi, r8
0x18004e247  mov     r13, rdx
0x18004e24a  mov     [rbp+2C0h+var_300], rdx
0x18004e24e  mov     r15, rcx
0x18004e251  mov     [rbp+2C0h+var_308], rcx
0x18004e255  xor     edx, edx
0x18004e257  lea     rcx, [rsp+3C0h+var_348]
0x18004e25c  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18004e262  nop
0x18004e263  lea     rdx, aCnodeGettasken; "CNode::GetTaskEnumerator"
0x18004e26a  lea     rcx, [rsp+3C0h+var_348]
0x18004e26f  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18004e275  test    r13, r13
0x18004e278  jz      loc_18004EEA5
0x18004e27e  test    rsi, rsi
0x18004e281  jz      loc_18004EEA5
0x18004e287  mov     qword ptr [rsi], 0
0x18004e28e  cmp     qword ptr [r15+38h], 0
0x18004e293  jz      loc_18004E378
0x18004e299  mov     rdi, [r15+18h]
0x18004e29d  mov     rcx, rdi; this
0x18004e2a0  call    ?GetStaticParent@CMTNode@@QEAAPEAVCMTSnapInNode@@XZ; CMTNode::GetStaticParent(void)
0x18004e2a5  mov     r12, rax
0x18004e2a8  mov     [rsp+3C0h+var_360], rax
0x18004e2ad  mov     r14, [rdi+100h]
0x18004e2b4  xorps   xmm0, xmm0
0x18004e2b7  movups  xmmword ptr [rbp+2C0h+var_F0.Data1], xmm0
0x18004e2be  lea     rdx, [rbp+2C0h+var_F0]; struct _GUID *
0x18004e2c5  mov     rcx, rdi; this
0x18004e2c8  call    ?GetNodeType@CMTNode@@QEAAJPEAU_GUID@@@Z; CMTNode::GetNodeType(_GUID *)
0x18004e2cd  mov     ebx, eax
0x18004e2cf  test    eax, eax
0x18004e2d1  js      loc_18004E37D
0x18004e2d7  mov     rbx, [r15+38h]
0x18004e2db  xor     r15d, r15d
0x18004e2de  test    rbx, rbx
0x18004e2e1  jz      loc_18004E378
0x18004e2e7  xor     edx, edx; Val
0x18004e2e9  lea     r8d, [r15+50h]; Size
0x18004e2ed  lea     rcx, [rbp+2C0h+var_230]; void *
0x18004e2f4  call    memset_0
0x18004e2f9  mov     [rbp+2C0h+var_228], r15
0x18004e300  mov     [rbp+2C0h+var_220], r15
0x18004e307  mov     [rbp+2C0h+var_218], r15d
0x18004e30e  mov     [rbp+2C0h+var_210], 48h ; 'H'
0x18004e319  movups  xmm0, xmmword ptr cs:_GUID_8dee6511_554d_11d1_9fea_00600832db4a.Data1
0x18004e320  movdqu  [rbp+2C0h+var_208], xmm0
0x18004e328  lea     rax, aIextendtaskpad; "IExtendTaskPad"
0x18004e32f  mov     [rbp+2C0h+var_1F8], rax
0x18004e336  mov     [rbp+2C0h+var_1F0], r15
0x18004e33d  mov     [rbp+2C0h+var_1E8], r15b
0x18004e344  lea     rax, ??_7IExtendTaskPadWrapper@@6B@; const IExtendTaskPadWrapper::`vftable'
0x18004e34b  mov     [rbp+2C0h+var_230], rax
0x18004e352  lea     rdx, [rbx+10h]; struct SnapinInterfaceWrapper *
0x18004e356  lea     rcx, [rbp+2C0h+var_230]; this
0x18004e35d  call    ?Assign@?$TSnapinInterfaceWrapper@UISnapinHelp2@@$01@@QEAAJAEBVIUnknownWrapper@@@Z; TSnapinInterfaceWrapper<ISnapinHelp2,2>::Assign(IUnknownWrapper const &)
0x18004e362  nop
0x18004e363  cmp     [rbp+2C0h+var_228], r15
0x18004e36a  jnz     short loc_18004E38F
0x18004e36c  lea     rcx, [rbp+2C0h+var_230]; this
0x18004e373  call    ??1SnapinInterfaceWrapper@@MEAA@XZ; SnapinInterfaceWrapper::~SnapinInterfaceWrapper(void)
0x18004e378  mov     ebx, 1
0x18004e37d  lea     rcx, [rsp+3C0h+var_348]
0x18004e382  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18004e388  mov     eax, ebx
0x18004e38a  jmp     loc_18004EEB5
0x18004e38f  mov     [rsp+3C0h+var_380], r15
0x18004e394  lea     rcx, [rsp+3C0h+var_380]
0x18004e399  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x18004e39e  mov     [rsp+3C0h+var_380], r15
0x18004e3a3  lea     r8, [rsp+3C0h+var_380]; struct IDataObject **
0x18004e3a8  mov     rcx, rdi; this
0x18004e3ab  call    ?QueryDataObject@CMTNode@@QEAAJW4_DATA_OBJECT_TYPES@@PEAPEAUIDataObject@@@Z; CMTNode::QueryDataObject(_DATA_OBJECT_TYPES,IDataObject * *)
0x18004e3b0  mov     ebx, eax
0x18004e3b2  test    eax, eax
0x18004e3b4  jns     short loc_18004E3CF
0x18004e3b6  lea     rcx, [rsp+3C0h+var_380]
0x18004e3bb  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x18004e3c0  nop
0x18004e3c1  lea     rcx, [rbp+2C0h+var_230]; this
0x18004e3c8  call    ??1SnapinInterfaceWrapper@@MEAA@XZ; SnapinInterfaceWrapper::~SnapinInterfaceWrapper(void)
0x18004e3cd  jmp     short loc_18004E37D
0x18004e3cf  xor     edx, edx; Val
0x18004e3d1  lea     r8d, [rdx+50h]; Size
0x18004e3d5  lea     rcx, [rbp+2C0h+var_190]; void *
0x18004e3dc  call    memset_0
0x18004e3e1  mov     [rbp+2C0h+var_188], r15
0x18004e3e8  mov     [rbp+2C0h+var_180], r15
0x18004e3ef  mov     [rbp+2C0h+var_178], r15d
0x18004e3f6  mov     [rbp+2C0h+var_170], 38h ; '8'
0x18004e401  movups  xmm0, xmmword ptr cs:_GUID_338698b1_5a02_11d1_9fec_00600832db4a.Data1
0x18004e408  movdqu  [rbp+2C0h+var_168], xmm0
0x18004e410  lea     rax, aIenumtask; "IEnumTASK"
0x18004e417  mov     [rbp+2C0h+var_158], rax
0x18004e41e  mov     [rbp+2C0h+var_150], r15
0x18004e425  mov     [rbp+2C0h+var_148], r15b
0x18004e42c  lea     rax, ??_7IEnumTASKWrapper@@6B@; const IEnumTASKWrapper::`vftable'
0x18004e433  mov     [rbp+2C0h+var_190], rax
0x18004e43a  mov     rax, [rbp+2C0h+var_230]
0x18004e441  lea     r9, [rbp+2C0h+var_190]
0x18004e448  mov     r8, r13
0x18004e44b  mov     rdx, [rsp+3C0h+var_380]
0x18004e450  lea     rcx, [rbp+2C0h+var_230]
0x18004e457  mov     rax, [rax+10h]
0x18004e45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e460  mov     edi, eax
0x18004e462  test    eax, eax
0x18004e464  jns     short loc_18004E491
0x18004e466  lea     rcx, [rbp+2C0h+var_190]; this
0x18004e46d  call    ??1SnapinInterfaceWrapper@@MEAA@XZ; SnapinInterfaceWrapper::~SnapinInterfaceWrapper(void)
0x18004e472  nop
0x18004e473  lea     rcx, [rsp+3C0h+var_380]
0x18004e478  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x18004e47d  nop
0x18004e47e  lea     rcx, [rbp+2C0h+var_230]; this
0x18004e485  call    ??1SnapinInterfaceWrapper@@MEAA@XZ; SnapinInterfaceWrapper::~SnapinInterfaceWrapper(void)
0x18004e48a  mov     ebx, edi
0x18004e48c  jmp     loc_18004E37D
0x18004e491  mov     ecx, 78h ; 'x'; Size
0x18004e496  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e49b  mov     r13, rax
0x18004e49e  mov     [rsp+3C0h+var_378], rax
0x18004e4a3  test    rax, rax
0x18004e4a6  jz      short loc_18004E4F7
0x18004e4a8  mov     [rax+8], r15d
0x18004e4ac  xorps   xmm0, xmm0
0x18004e4af  xor     eax, eax
0x18004e4b1  movups  xmmword ptr [r13+10h], xmm0
0x18004e4b6  movups  xmmword ptr [r13+20h], xmm0
0x18004e4bb  mov     [r13+30h], rax
0x18004e4bf  mov     [r13+38h], r15b
0x18004e4c3  mov     [r13+50h], r15d
0x18004e4c7  mov     [r13+58h], r15
0x18004e4cb  mov     [r13+48h], r15
0x18004e4cf  mov     [r13+40h], r15
0x18004e4d3  mov     [r13+60h], r15
0x18004e4d7  mov     dword ptr [r13+68h], 0Ah
0x18004e4df  mov     [r13+70h], r15
0x18004e4e3  lea     rax, ??_7?$CComObject@VCTaskEnumerator@@@ATL@@6B@; const ATL::CComObject<CTaskEnumerator>::`vftable'
0x18004e4ea  mov     [r13+0], rax
0x18004e4ee  lock inc cs:dword_1801C7678
0x18004e4f5  jmp     short loc_18004E4FA
0x18004e4f7  mov     r13, r15
0x18004e4fa  lea     rdx, [rsp+3C0h+var_358]
0x18004e4ff  mov     rcx, r14
0x18004e502  call    ?GetSnapInReference@CComponentData@@QEBA?AVCSnapInReferencePtr@@XZ; CComponentData::GetSnapInReference(void)
0x18004e507  nop
0x18004e508  mov     rbx, [rsp+3C0h+var_350]
0x18004e50d  test    rbx, rbx
0x18004e510  jz      loc_18004EE31
0x18004e516  lea     r8, [rbp+2C0h+var_190]
0x18004e51d  mov     rdx, rbx
0x18004e520  mov     rcx, r13
0x18004e523  call    ?AddTaskEnumerator@CTaskEnumerator@@QEAA_NAEBVCSnapInReference@@AEAV?$_snapin_ptr_t@VIEnumTASKWrapper@@UIEnumTASK@@@@@Z; CTaskEnumerator::AddTaskEnumerator(CSnapInReference const &,_snapin_ptr_t<IEnumTASKWrapper,IEnumTASK> &)
0x18004e528  mov     rax, [rbx]
0x18004e52b  mov     rcx, rbx
0x18004e52e  mov     rax, [rax+48h]
0x18004e532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e537  mov     ebx, eax
0x18004e539  xor     edx, edx; Val
0x18004e53b  lea     r8d, [rdx+50h]; Size
0x18004e53f  lea     rcx, [rbp+2C0h+var_140]; void *
0x18004e546  call    memset_0
0x18004e54b  mov     [rbp+2C0h+var_138], r15
0x18004e552  mov     [rbp+2C0h+var_130], r15
0x18004e559  mov     [rbp+2C0h+var_128], r15d
0x18004e560  mov     [rbp+2C0h+var_120], 38h ; '8'
0x18004e56b  movups  xmm0, xmmword ptr cs:_GUID_338698b1_5a02_11d1_9fec_00600832db4a.Data1
0x18004e572  movdqu  [rbp+2C0h+var_118], xmm0
0x18004e57a  lea     rax, aIenumtask; "IEnumTASK"
0x18004e581  mov     [rbp+2C0h+var_108], rax
0x18004e588  mov     [rbp+2C0h+var_100], r15
0x18004e58f  mov     [rbp+2C0h+var_F8], r15b
0x18004e596  lea     rax, ??_7IEnumTASKWrapper@@6B@; const IEnumTASKWrapper::`vftable'
0x18004e59d  mov     [rbp+2C0h+var_140], rax
0x18004e5a4  mov     r8d, ebx; int
0x18004e5a7  mov     rdx, r13; struct IUnknown *
0x18004e5aa  lea     rcx, [rbp+2C0h+var_140]; this
0x18004e5b1  call    ?Assign@?$TSnapinInterfaceWrapper@UIEnumTASK@@$03@@QEAAJPEAUIUnknown@@H@Z; TSnapinInterfaceWrapper<IEnumTASK,4>::Assign(IUnknown *,int)
0x18004e5b6  nop
0x18004e5b7  cmp     [rbp+2C0h+var_138], r15
0x18004e5be  jz      short loc_18004E5CF
0x18004e5c0  lea     rcx, [rbp+2C0h+var_140]; this
0x18004e5c7  call    ?Detach@SnapinInterfaceWrapper@@QEAAPEAUIUnknown@@XZ; SnapinInterfaceWrapper::Detach(void)
0x18004e5cc  mov     [rsi], rax
0x18004e5cf  mov     [rbp+2C0h+var_330], r15
0x18004e5d3  mov     [rbp+2C0h+var_324], r15
0x18004e5d7  mov     [rbp+2C0h+var_328], r15d
0x18004e5db  lea     rdx, [rbp+2C0h+var_330]
0x18004e5df  mov     rcx, [rsp+3C0h+var_380]
0x18004e5e4  call    ?ExtractDynExtensions@@YAJPEAUIDataObject@@AEAV?$CArray@U_GUID@@AEAU1@@@@Z; ExtractDynExtensions(IDataObject *,CArray<_GUID,_GUID &> &)
0x18004e5e9  xorps   xmm0, xmm0
0x18004e5ec  movdqa  [rbp+2C0h+var_2D0], xmm0
0x18004e5f1  xorps   xmm1, xmm1
0x18004e5f4  movdqa  [rbp+2C0h+var_2C0], xmm1
0x18004e5f9  movdqa  [rbp+2C0h+var_2B0], xmm0
0x18004e5fe  movdqa  [rbp+2C0h+var_2A0], xmm1
0x18004e603  movdqa  [rbp+2C0h+var_290], xmm0
0x18004e608  mov     [rbp+2C0h+var_280], r15
0x18004e60c  mov     [rbp+2C0h+var_270], r15
0x18004e610  mov     eax, [rbp+2C0h+var_328]
0x18004e613  mov     [rsp+3C0h+var_390], eax
0x18004e617  mov     rax, [rbp+2C0h+var_330]
0x18004e61b  mov     [rsp+3C0h+var_398], rax
0x18004e620  lea     rax, aTask_0; "Task"
0x18004e627  mov     [rsp+3C0h+var_3A0], rax
0x18004e62c  lea     r9, [rbp+2C0h+var_F0]
0x18004e633  mov     r8, [r14]
0x18004e636  lea     rdx, [rbp+2C0h+var_2E8]
0x18004e63a  lea     rcx, [rbp+2C0h+var_2D0]
0x18004e63e  call    ?ScInitialize@CExtensionsIterator@@QEAA?AVSC@mmcerror@@PEAVCSnapIn@@AEAU_GUID@@PEBGPEAU5@H@Z; CExtensionsIterator::ScInitialize(CSnapIn *,_GUID &,ushort const *,_GUID *,int)
0x18004e643  nop
0x18004e644  mov     rdx, rax
0x18004e647  lea     rcx, [rsp+3C0h+var_348]
0x18004e64c  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18004e652  nop
0x18004e653  lea     rcx, [rbp+2C0h+var_2E8]
0x18004e657  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18004e65d  lea     rcx, [rsp+3C0h+var_348]
0x18004e662  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x18004e668  test    al, al
0x18004e66a  jnz     loc_18004EDCE
0x18004e670  lea     rcx, [rbp+2C0h+var_2D0]; this
0x18004e674  call    ?IsEnd@CExtensionsIterator@@QEAAHXZ; CExtensionsIterator::IsEnd(void)
0x18004e679  cmp     eax, 1
0x18004e67c  jz      loc_18004EDCE
0x18004e682  lea     rsi, WPP_GLOBAL_Control
0x18004e689  lea     r14, WPP_5e286a5d0e1f3971b95362f9cca1ca0a_Traceguids
0x18004e690  lea     r15, ??_7CSnapInReferencePtr@@6B@; const CSnapInReferencePtr::`vftable'
0x18004e697  lea     rcx, [rbp+2C0h+var_2D0]; this
0x18004e69b  call    ?IsEnd@CExtensionsIterator@@QEAAHXZ; CExtensionsIterator::IsEnd(void)
0x18004e6a0  test    eax, eax
0x18004e6a2  jnz     loc_18004ED66
0x18004e6a8  lea     rdx, [rsp+3C0h+var_370]
0x18004e6ad  lea     rcx, [rbp+2C0h+var_2D0]
0x18004e6b1  call    ?GetSnapInReference@CExtensionsIterator@@QEAA?AVCSnapInReferencePtr@@XZ; CExtensionsIterator::GetSnapInReference(void)
0x18004e6b6  nop
0x18004e6b7  mov     rbx, [rsp+3C0h+var_368]
0x18004e6bc  test    rbx, rbx
0x18004e6bf  jnz     short loc_18004E6C6
0x18004e6c1  xor     r12d, r12d
0x18004e6c4  jmp     short loc_18004E6DD
0x18004e6c6  mov     rdx, rbx; struct CSnapInReference *
0x18004e6c9  mov     rcx, r12; this
0x18004e6cc  call    ?GetComponentData@CMTSnapInNode@@QEAAPEAVCComponentData@@AEBVCSnapInReference@@@Z; CMTSnapInNode::GetComponentData(CSnapInReference const &)
0x18004e6d1  mov     r12, rax
0x18004e6d4  test    rax, rax
0x18004e6d7  jnz     loc_18004E8F6
0x18004e6dd  mov     edi, 50h ; 'P'
0x18004e6e2  mov     r8d, edi; Size
0x18004e6e5  xor     edx, edx; Val
0x18004e6e7  lea     rcx, [rbp+2C0h+var_E0]; void *
0x18004e6ee  call    memset_0
0x18004e6f3  xor     ecx, ecx
0x18004e6f5  mov     [rbp+2C0h+var_D8], rcx
0x18004e6fc  mov     [rbp+2C0h+var_D0], rcx
0x18004e703  mov     [rbp+2C0h+var_C8], ecx
0x18004e709  mov     [rbp+2C0h+var_C0], rdi
0x18004e710  movups  xmm0, xmmword ptr cs:_GUID_955ab28a_5218_11d0_a985_00c04fd8d565.Data1
0x18004e717  movdqu  [rbp+2C0h+var_B8], xmm0
0x18004e71f  lea     rax, aIcomponentdata_0; "IComponentData"
0x18004e726  mov     [rbp+2C0h+var_A8], rax
0x18004e72d  mov     [rbp+2C0h+var_A0], rcx
0x18004e734  mov     [rbp+2C0h+var_98], cl
0x18004e73a  lea     rax, ??_7IComponentDataWrapper@@6B@; const IComponentDataWrapper::`vftable'
0x18004e741  mov     [rbp+2C0h+var_E0], rax
0x18004e748  test    rbx, rbx
0x18004e74b  jnz     short loc_18004E780
0x18004e74d  mov     edi, 8007054Fh
0x18004e752  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e759  cmp     rcx, rsi
0x18004e75c  jz      loc_18004E8E1
0x18004e762  cmp     byte ptr [rcx+19h], 2
0x18004e766  jb      loc_18004E8E1
0x18004e76c  lea     edx, [rbx+22h]
0x18004e76f  mov     r8, r14
0x18004e772  mov     rcx, [rcx+10h]
0x18004e776  call    WPP_SF_
0x18004e77b  jmp     loc_18004E8E1
0x18004e780  xor     r9d, r9d
0x18004e783  xor     r8d, r8d
0x18004e786  lea     rdx, [rbp+2C0h+var_E0]; this
0x18004e78d  mov     rcx, rbx; struct CSnapInReference *
0x18004e790  call    ?CreateSnapIn@@YAJAEBVCSnapInReference@@AEAV?$_snapin_ptr_t@VIComponentDataWrapper@@UIComponentData@@@@_N2@Z; CreateSnapIn(CSnapInReference const &,_snapin_ptr_t<IComponentDataWrapper,IComponentData> &,bool,bool)
0x18004e795  mov     edi, eax
0x18004e797  test    eax, eax
0x18004e799  jns     short loc_18004E7D3
  ... truncated ...
```
