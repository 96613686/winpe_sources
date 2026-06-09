# Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(AutoHSTRING &,IUnknown *,Windows::Foundation::IPropertyValue *,bool,bool,int)

- ea: `0x1801be2bc`
- end: `0x1801bf710`
- name: `?ReadPropertyValueVarFromRuntimeClassName@ProjectionMarshaler@Projection@@AEAAPEAXAEAVAutoHSTRING@@PEAUIUnknown@@PEAUIPropertyValue@Foundation@Windows@@_N3H@Z`
- size: `5204`
- prototype: `void *__fastcall(Projection::ProjectionMarshaler *__hidden this, struct AutoHSTRING *, struct IUnknown *, struct Windows::Foundation::IPropertyValue *, bool, bool, int)`
- caller_count: `3`
- callee_count: `28`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801bd7b8`
- `0x1801c1394`
- `0x1802467fc`

## callees

- `0x180016010`
- `0x1800194d0`
- `0x180021e18`
- `0x180022508`
- `0x180054858`
- `0x18005f188`
- `0x180068c64`
- `0x1801524a4`
- `0x1801a8a70`
- `0x1801baa4c`
- `0x1801be2bc`
- `0x1801c09d0`
- `0x1801c1604`
- `0x1801c5558`
- `0x180225494`
- `0x1802262d4`
- `0x18022c278`
- `0x180239204`
- `0x1802456bc`
- `0x18024575c`
- `0x180245b14`
- `0x180245b58`
- `0x1802461e4`
- `0x180246634`
- `0x1802b1ae0`
- `0x1803012a0`
- `0x180341dd0`
- `0x18035e010`

## import_xrefs

- `msvcrt!wcsstr` at `0x1801be3a7`
- `msvcrt!wcsstr` at `0x1801be3c1`
- `msvcrt!wcsstr` at `0x1801be3a7`
- `msvcrt!wcsstr` at `0x1801be3c1`
- `KERNEL32!LoadLibraryExW` at `0x1801be352`
- `KERNEL32!LoadLibraryExW` at `0x1801be352`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
void *__fastcall Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(
        Projection::ProjectionMarshaler *this,
        struct AutoHSTRING *a2,
        struct IUnknown *a3,
        struct IInspectable *a4,
        bool a5,
        bool a6,
        int a7)
{
  __int64 v11; // rax
  __int64 v12; // rbx
  const WCHAR *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  const wchar_t *v16; // rbx
  ThreadContext **v17; // r14
  wchar_t *v18; // rax
  wchar_t *v19; // rax
  int v20; // ebx
  int v21; // ebx
  void *OutString; // rax
  int v23; // ebx
  int v24; // ebx
  struct Js::ScriptContext *v25; // rdx
  void *VarFromRuntimeClassName; // rbx
  int v27; // ebx
  __int64 v28; // rbx
  int v29; // ebx
  int v30; // ebx
  int v31; // ebx
  int v32; // ebx
  struct Js::ScriptContext *v33; // rdx
  double v34; // xmm0_8
  int v35; // ebx
  int v36; // ebx
  int v37; // ebx
  int v38; // ebx
  unsigned __int64 v39; // r8
  int v40; // ebx
  int v41; // ebx
  int v42; // ebx
  int v43; // ebx
  int v44; // eax
  int v45; // ebx
  int ArrayProjectionObject; // eax
  int v47; // ebx
  int v48; // eax
  int v49; // ebx
  int v50; // eax
  int v51; // ebx
  int v52; // eax
  int v53; // ebx
  int v54; // eax
  int v55; // ebx
  int v56; // eax
  int v57; // ebx
  int v58; // eax
  int v59; // ebx
  int v60; // eax
  int v61; // ebx
  int v62; // eax
  int v63; // ebx
  int v64; // eax
  int v65; // ebx
  int v66; // eax
  int v67; // ebx
  unsigned int v68; // ebx
  unsigned __int8 *v69; // rdi
  struct Projection::ProjectionContext *v70; // rsi
  const struct ProjectionModel::ConcreteType *v71; // rax
  int v72; // eax
  int v73; // ebx
  unsigned int v74; // ebx
  unsigned __int8 *v75; // rdi
  struct Projection::ProjectionContext *v76; // rsi
  const struct ProjectionModel::ConcreteType *v77; // rax
  int v78; // eax
  int v79; // ebx
  unsigned int v80; // ebx
  unsigned __int8 *v81; // rdi
  struct Projection::ProjectionContext *v82; // rsi
  const struct ProjectionModel::ConcreteType *v83; // rax
  int v84; // eax
  int v85; // ebx
  int v86; // eax
  __int64 v87; // rcx
  unsigned int v88; // eax
  float v90; // [rsp+58h] [rbp-81h] BYREF
  HSTRING v91; // [rsp+60h] [rbp-79h] BYREF
  bool v92; // [rsp+68h] [rbp-71h]
  bool v93; // [rsp+69h] [rbp-70h]
  _BYTE v94[32]; // [rsp+70h] [rbp-69h] BYREF
  int v95; // [rsp+90h] [rbp-49h] BYREF
  int v96; // [rsp+94h] [rbp-45h] BYREF
  __int64 v97; // [rsp+98h] [rbp-41h]
  __int64 v98; // [rsp+A0h] [rbp-39h]
  unsigned __int8 *v99[2]; // [rsp+A8h] [rbp-31h] BYREF
  void *retaddr; // [rsp+120h] [rbp+47h]

  v98 = -2;
  v93 = a5;
  v92 = a6;
  v96 = 0;
  v11 = *((_QWORD *)this + 2);
  v12 = *(_QWORD *)(v11 + 96) + 8408LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v11 + 96) + 8424LL) )
  {
    v13 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(*(_QWORD *)(v11 + 96) + 8408LL);
    *(_QWORD *)(v12 + 8) = LoadLibraryExW(v13, 0, 0x800u);
    *(_BYTE *)(v12 + 16) = 1;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v12 + 40LL))(v12, *(_QWORD *)a2, &v96);
  v16 = (const wchar_t *)v14;
  v97 = v14;
  if ( (Microsoft_JScriptEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v15, &JSCRIPT_PROJECTION_PROPERTYVALUEVARFROMGRCN_START, v14);
  v17 = *(ThreadContext ***)(*((_QWORD *)this + 2) + 112LL);
  v18 = wcsstr(v16, L"Windows.Foundation.IReference`1");
  if ( !v18 || v18 != v16 )
  {
    v19 = wcsstr(v16, L"Windows.Foundation.IReferenceArray`1");
    if ( !v19 || v19 != v16 )
      Js::JavascriptError::ThrowTypeError((struct Js::ScriptContext *)v17, -2146823194, v16);
  }
  v95 = 0;
  Js::JavascriptErrorDebug::ClearErrorInfo((struct Js::ScriptContext *)v17);
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v99, v17, retaddr);
  v20 = ((__int64 (__fastcall *)(struct IInspectable *, int *))a4->lpVtbl[1].QueryInterface)(a4, &v95);
  if ( v17 )
    ThreadContext::DisposeOnLeaveScript(v17[148]);
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v99);
  if ( v20 < 0 )
    Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v20);
  Js::JavascriptErrorDebug::ClearErrorInfo((struct Js::ScriptContext *)v17);
  v91 = 0;
  if ( v95 > 1025 )
  {
    switch ( v95 )
    {
      case 1026:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v45 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[4].GetIids)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v45 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v45);
        ArrayProjectionObject = Projection::ArrayProjection::CreateArrayProjectionObject(
                                  *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2)
                                                                                             + 120LL)
                                                                                 + 40LL),
                                  *((struct Projection::ProjectionContext **)this + 2),
                                  v99[0],
                                  LODWORD(v90),
                                  LODWORD(v90),
                                  1,
                                  (void **)&v91,
                                  1);
        if ( ArrayProjectionObject < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, ArrayProjectionObject);
        goto LABEL_210;
      case 1027:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v47 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[4].GetRuntimeClassName)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v47 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v47);
        v48 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 88LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v48 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v48);
        goto LABEL_210;
      case 1028:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v49 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[4].GetTrustLevel)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v49 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v49);
        v50 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 48LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v50 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v50);
        goto LABEL_210;
      case 1029:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v51 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[5].QueryInterface)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v51 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v51);
        v52 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 96LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v52 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v52);
        goto LABEL_210;
      case 1030:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v53 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[5].AddRef)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v53 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v53);
        v54 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 56LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v54 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v54);
        goto LABEL_210;
      case 1031:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v55 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[5].Release)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v55 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v55);
        v56 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 104LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v56 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v56);
        goto LABEL_210;
      case 1032:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v57 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[5].GetIids)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v57 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v57);
        v58 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 64LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v58 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v58);
        goto LABEL_210;
      case 1033:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v59 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[5].GetRuntimeClassName)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v59 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v59);
        v60 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 72LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v60 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v60);
        goto LABEL_210;
      case 1034:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v61 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[5].GetTrustLevel)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v61 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v61);
        v62 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 24LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v62 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v62);
        goto LABEL_210;
      case 1035:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v63 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[6].QueryInterface)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v63 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v63);
        v64 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 112LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v64 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v64);
        goto LABEL_210;
      case 1036:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v65 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[6].AddRef)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v65 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v65);
        v66 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 80LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v66 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v66);
        goto LABEL_210;
      case 1037:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v85 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[6].Release)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v85 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v85);
        v86 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 136LL),
                *((struct Projection::ProjectionContext **)this + 2),
                v99[0],
                LODWORD(v90),
                LODWORD(v90),
                1,
                (void **)&v91,
                1);
        if ( v86 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v86);
        goto LABEL_210;
      case 1038:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v67 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[6].GetRuntimeClassName)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v67 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v67);
        v68 = LODWORD(v90);
        v69 = v99[0];
        v70 = (struct Projection::ProjectionContext *)*((_QWORD *)this + 2);
        v71 = ProjectionModel::ConcreteType::From(*(const struct ProjectionModel::Type **)(*((_QWORD *)v70 + 15) + 152LL));
        v72 = Projection::ArrayProjection::CreateArrayProjectionObject(v71, v70, v69, v68, v68, 1, (void **)&v91, 1);
        if ( v72 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v72);
        goto LABEL_210;
      case 1039:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v73 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[6].GetTrustLevel)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v73 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v73);
        v74 = LODWORD(v90);
        v75 = v99[0];
        v76 = (struct Projection::ProjectionContext *)*((_QWORD *)this + 2);
        v77 = ProjectionModel::ConcreteType::From(*(const struct ProjectionModel::Type **)(*((_QWORD *)v76 + 15) + 160LL));
        v78 = Projection::ArrayProjection::CreateArrayProjectionObject(v77, v76, v75, v74, v74, 1, (void **)&v91, 1);
        if ( v78 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v78);
        goto LABEL_210;
      case 1040:
        v99[0] = 0;
        v90 = 0.0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
        v79 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[6].GetIids)(
                a4,
                &v90,
                v99);
        if ( v17 )
          ThreadContext::DisposeOnLeaveScript(v17[148]);
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
        if ( v79 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v79);
        v80 = LODWORD(v90);
        v81 = v99[0];
        v82 = (struct Projection::ProjectionContext *)*((_QWORD *)this + 2);
        v83 = ProjectionModel::ConcreteType::From(*(const struct ProjectionModel::Type **)(*((_QWORD *)v82 + 15) + 144LL));
        v84 = Projection::ArrayProjection::CreateArrayProjectionObject(v83, v82, v81, v80, v80, 1, (void **)&v91, 1);
        if ( v84 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v84);
        goto LABEL_210;
      default:
        goto LABEL_217;
    }
  }
  if ( v95 == 1025 )
  {
    v99[0] = 0;
    v90 = 0.0;
    Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
    v43 = ((__int64 (__fastcall *)(struct IInspectable *, float *, unsigned __int8 **))a4->lpVtbl[4].Release)(
            a4,
            &v90,
            v99);
    if ( v17 )
      ThreadContext::DisposeOnLeaveScript(v17[148]);
    Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
    if ( v43 < 0 )
      Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v43);
    v44 = Projection::ArrayProjection::CreateArrayProjectionObject(
            *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 32LL),
            *((struct Projection::ProjectionContext **)this + 2),
            v99[0],
            LODWORD(v90),
            LODWORD(v90),
            1,
            (void **)&v91,
            1);
    if ( v44 < 0 )
      Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v17, v44);
LABEL_210:
    VarFromRuntimeClassName = v91;
    goto LABEL_211;
  }
  if ( v95 > 8 )
  {
    if ( v95 != 9 )
    {
      switch ( v95 )
      {
        case 10:
          LOWORD(v90) = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
          v41 = ((__int64 (__fastcall *)(struct IInspectable *, float *))a4->lpVtbl[2].GetTrustLevel)(a4, &v90);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
          if ( v41 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v41);
          OutString = (void *)Js::JavascriptString::NewWithBufferT<Js::LiteralString,1>((unsigned __int16 *)&v90, 1u);
          goto LABEL_40;
        case 11:
          LOBYTE(v90) = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
          v40 = ((__int64 (__fastcall *)(struct IInspectable *, float *))a4->lpVtbl[3].QueryInterface)(a4, &v90);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
          if ( v40 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v40);
          VarFromRuntimeClassName = *(void **)((char *)*v17
                                             + (-(__int64)(LOBYTE(v90) != 0) & 0xFFFFFFFFFFFFFFF8uLL)
                                             + 992);
          goto LABEL_211;
        case 12:
          v91 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
          v38 = ((__int64 (__fastcall *)(struct IInspectable *, HSTRING *))a4->lpVtbl[3].AddRef)(a4, &v91);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
          if ( v38 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v38);
          Projection::ProjectionMarshaler::RecordToUndo(this, v91, 1);
          OutString = Projection::ProjectionMarshaler::ReadOutString(this, (unsigned __int8 *)&v91, v39);
          goto LABEL_40;
        case 13:
          Js::JavascriptError::ThrowTypeError((struct Js::ScriptContext *)v17, -2146828275, 0);
        case 14:
          v91 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
          v37 = ((__int64 (__fastcall *)(struct IInspectable *, HSTRING *))a4->lpVtbl[3].GetIids)(a4, &v91);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
          if ( v37 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v37);
          OutString = Projection::ProjectionMarshaler::ReadOutWindowsFoundationDateTimeType(
                        this,
                        (unsigned __int8 *)&v91,
                        8u);
          goto LABEL_40;
        case 15:
          v91 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
          v36 = ((__int64 (__fastcall *)(struct IInspectable *, HSTRING *))a4->lpVtbl[3].GetRuntimeClassName)(a4, &v91);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
          if ( v36 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v36);
          OutString = Projection::ProjectionMarshaler::ReadOutWindowsFoundationTimeSpanType(
                        this,
                        (unsigned __int8 *)&v91,
                        8u);
          goto LABEL_40;
        case 16:
          *(_OWORD *)v99 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
          v35 = ((__int64 (__fastcall *)(struct IInspectable *, unsigned __int8 **))a4->lpVtbl[3].Release)(a4, v99);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
          if ( v35 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v35);
          OutString = Projection::ProjectionMarshaler::ReadOutSystemGuidType(this, 1, (unsigned __int8 *)v99, 0x10u);
          goto LABEL_40;
      }
      goto LABEL_217;
    }
    v91 = 0;
    Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v94, v17, retaddr);
    v42 = ((__int64 (__fastcall *)(struct IInspectable *, HSTRING *))a4->lpVtbl[2].GetRuntimeClassName)(a4, &v91);
    if ( v17 )
      ThreadContext::DisposeOnLeaveScript(v17[148]);
    Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v94);
    if ( v42 < 0 )
      Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v42);
    v34 = *(double *)&v91;
  }
  else
  {
    if ( v95 != 8 )
    {
      switch ( v95 )
      {
        case 0:
          VarFromRuntimeClassName = (void *)*((_QWORD *)*v17 + 133);
          goto LABEL_211;
        case 1:
          LOBYTE(v90) = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v99, v17, retaddr);
          v31 = ((__int64 (__fastcall *)(struct IInspectable *, float *))a4->lpVtbl[1].Release)(a4, &v90);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v99);
          if ( v31 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v31);
          v28 = LOBYTE(v90);
          break;
        case 2:
          LOWORD(v90) = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v99, v17, retaddr);
          v30 = ((__int64 (__fastcall *)(struct IInspectable *, float *))a4->lpVtbl[1].GetIids)(a4, &v90);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v99);
          if ( v30 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v30);
          v28 = (unsigned int)SLOWORD(v90);
          break;
        case 3:
          LOWORD(v90) = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v99, v17, retaddr);
          v29 = ((__int64 (__fastcall *)(struct IInspectable *, float *))a4->lpVtbl[1].GetRuntimeClassName)(a4, &v90);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v99);
          if ( v29 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v29);
          v28 = LOWORD(v90);
          break;
        case 4:
          v90 = 0.0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v99, v17, retaddr);
          v27 = ((__int64 (__fastcall *)(struct IInspectable *, float *))a4->lpVtbl[1].GetTrustLevel)(a4, &v90);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v99);
          if ( v27 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v27);
          v28 = LODWORD(v90);
          break;
        case 5:
          v90 = 0.0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v99, v17, retaddr);
          v24 = ((__int64 (__fastcall *)(struct IInspectable *, float *))a4->lpVtbl[2].QueryInterface)(a4, &v90);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v99);
          if ( v24 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v24);
          OutString = Js::JavascriptNumber::ToVar(LODWORD(v90), v25);
          goto LABEL_40;
        case 6:
          v91 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v99, v17, retaddr);
          v23 = ((__int64 (__fastcall *)(struct IInspectable *, HSTRING *))a4->lpVtbl[2].AddRef)(a4, &v91);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v99);
          if ( v23 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v23);
          OutString = (void *)Js::JavascriptTypedNumber<__int64>::ToVar(v91, v17);
          goto LABEL_40;
        case 7:
          v91 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v99, v17, retaddr);
          v21 = ((__int64 (__fastcall *)(struct IInspectable *, HSTRING *))a4->lpVtbl[2].Release)(a4, &v91);
          if ( v17 )
            ThreadContext::DisposeOnLeaveScript(v17[148]);
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v99);
          if ( v21 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v21);
          OutString = (void *)Js::JavascriptTypedNumber<unsigned __int64>::ToVar(v91, v17);
          goto LABEL_40;
        default:
LABEL_217:
          VarFromRuntimeClassName = Projection::ProjectionMarshaler::ReadVarFromRuntimeClassName(
                                      this,
                                      a2,
                                      a3,
                                      a4,
                                      v93,
                                      v92,
                                      0,
                                      a7,
                                      0);
          goto LABEL_218;
      }
      VarFromRuntimeClassName = (void *)(v28 | 0x1000000000000LL);
      goto LABEL_211;
    }
    v90 = 0.0;
    Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v99, v17, retaddr);
    v32 = ((__int64 (__fastcall *)(struct IInspectable *, float *))a4->lpVtbl[2].GetIids)(a4, &v90);
    if ( v17 )
      ThreadContext::DisposeOnLeaveScript(v17[148]);
    Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v99);
    if ( v32 < 0 )
      Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v17, v32);
    v34 = v90;
  }
  OutString = Js::JavascriptNumber::ToVarWithCheck(v34, v33);
LABEL_40:
  VarFromRuntimeClassName = OutString;
LABEL_211:
  Projection::ProjectionContext::GetProjectionWriter(*((Projection::ProjectionContext **)this + 2));
  if ( v93 )
    Projection::ProjectionContext::TypeInstanceCreated(
      *((Projection::ProjectionContext **)this + 2),
      (struct IUnknown *)a4);
  if ( !v92 && Js::DynamicObject::Is(VarFromRuntimeClassName) && !*(_DWORD *)(*((_QWORD *)this + 2) + 56LL) )
  {
    v88 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)VarFromRuntimeClassName + 376LL))(VarFromRuntimeClassName);
    Js::VerifyCatastrophic<int>(v88);
  }
LABEL_218:
  if ( (Microsoft_JScriptEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v87, &JSCRIPT_PROJECTION_PROPERTYVALUEVARFROMGRCN_STOP, v97);
  return VarFromRuntimeClassName;
}

```

## disassembly

```asm
0x1801be2bc  mov     rax, rsp
0x1801be2bf  mov     [rax+20h], r9
0x1801be2c3  mov     [rax+18h], r8
0x1801be2c7  mov     [rax+10h], rdx
0x1801be2cb  mov     [rax+8], rcx
0x1801be2cf  push    rbp
0x1801be2d0  push    rbx
0x1801be2d1  push    rsi
0x1801be2d2  push    rdi
0x1801be2d3  push    r12
0x1801be2d5  push    r13
0x1801be2d7  push    r14
0x1801be2d9  push    r15
0x1801be2db  lea     rbp, [rax-47h]
0x1801be2df  sub     rsp, 0D8h
0x1801be2e6  mov     [rbp+3Fh+var_78], 0FFFFFFFFFFFFFFFEh
0x1801be2ee  mov     rax, cs:__security_cookie
0x1801be2f5  xor     rax, rsp
0x1801be2f8  mov     [rbp+3Fh+var_50], rax
0x1801be2fc  mov     r13, [rbp+3Fh+arg_0]
0x1801be300  mov     rdi, [rbp+3Fh+arg_8]
0x1801be304  mov     rsi, [rbp+3Fh+arg_10]
0x1801be308  mov     r15, [rbp+3Fh+arg_18]
0x1801be30c  mov     al, [rbp+3Fh+arg_20]
0x1801be30f  mov     [rbp+3Fh+var_AF], al
0x1801be312  mov     al, [rbp+3Fh+arg_28]
0x1801be315  mov     [rbp+3Fh+var_B0], al
0x1801be318  mov     r12d, [rbp+3Fh+arg_30]
0x1801be31c  mov     [rbp+3Fh+var_84], 0
0x1801be323  mov     rax, [r13+10h]
0x1801be327  mov     rbx, [rax+60h]
0x1801be32b  add     rbx, 20D8h
0x1801be332  cmp     byte ptr [rbx+10h], 0
0x1801be336  jnz     short loc_1801BE360
0x1801be338  mov     rax, [rbx]
0x1801be33b  mov     rcx, rbx
0x1801be33e  mov     rax, [rax+8]
0x1801be342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be347  mov     rcx, rax; lpLibFileName
0x1801be34a  xor     edx, edx; hFile
0x1801be34c  mov     r8d, 800h; dwFlags
0x1801be352  call    cs:__imp_LoadLibraryExW
0x1801be358  mov     [rbx+8], rax
0x1801be35c  mov     byte ptr [rbx+10h], 1
0x1801be360  mov     rax, [rbx]
0x1801be363  lea     r8, [rbp+3Fh+var_84]
0x1801be367  mov     rdx, [rdi]
0x1801be36a  mov     rcx, rbx
0x1801be36d  mov     rax, [rax+28h]
0x1801be371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be376  mov     rbx, rax
0x1801be379  mov     [rbp+3Fh+var_80], rax
0x1801be37d  test    byte ptr cs:Microsoft_JScriptEnableBits, 8
0x1801be384  jz      short loc_1801BE395
0x1801be386  mov     r8, rax
0x1801be389  lea     rdx, JSCRIPT_PROJECTION_PROPERTYVALUEVARFROMGRCN_START
0x1801be390  call    McTemplateU0z_EventWriteTransfer
0x1801be395  mov     rcx, [r13+10h]
0x1801be399  mov     r14, [rcx+70h]
0x1801be39d  lea     rdx, aWindowsFoundat_4; "Windows.Foundation.IReference`1"
0x1801be3a4  mov     rcx, rbx; Str
0x1801be3a7  call    cs:__imp_wcsstr
0x1801be3ad  test    rax, rax
0x1801be3b0  jz      short loc_1801BE3B7
0x1801be3b2  cmp     rax, rbx
0x1801be3b5  jz      short loc_1801BE3D9
0x1801be3b7  lea     rdx, aWindowsFoundat_1; "Windows.Foundation.IReferenceArray`1"
0x1801be3be  mov     rcx, rbx; Str
0x1801be3c1  call    cs:__imp_wcsstr
0x1801be3c7  test    rax, rax
0x1801be3ca  jz      loc_1801BF6C1
0x1801be3d0  cmp     rax, rbx
0x1801be3d3  jnz     loc_1801BF6C1
0x1801be3d9  mov     [rbp+3Fh+var_88], 0
0x1801be3e0  mov     rcx, r14; struct Js::ScriptContext *
0x1801be3e3  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1801be3e8  mov     r8, [rbp+47h]
0x1801be3ec  mov     rdx, r14
0x1801be3ef  lea     rcx, [rbp+3Fh+var_70]
0x1801be3f3  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801be3f8  nop
0x1801be3f9  mov     rax, [r15]
0x1801be3fc  lea     rdx, [rbp+3Fh+var_88]
0x1801be400  mov     rcx, r15
0x1801be403  mov     rax, [rax+30h]
0x1801be407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be40c  mov     ebx, eax
0x1801be40e  test    r14, r14
0x1801be411  jz      short loc_1801BE420
0x1801be413  mov     rcx, [r14+4A0h]; this
0x1801be41a  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801be41f  nop
0x1801be420  lea     rcx, [rbp+3Fh+var_70]
0x1801be424  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801be429  mov     rcx, r14; struct Js::ScriptContext *
0x1801be42c  test    ebx, ebx
0x1801be42e  jns     short loc_1801BE438
0x1801be430  mov     edx, ebx; int
0x1801be432  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801be438  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1801be43d  xor     r8d, r8d; unsigned __int16 *
0x1801be440  mov     [rbp+3Fh+var_B8], r8
0x1801be444  mov     ecx, [rbp+3Fh+var_88]
0x1801be447  mov     eax, 401h
0x1801be44c  cmp     ecx, eax
0x1801be44e  jg      loc_1801BEBEA
0x1801be454  jz      loc_1801BEB44
0x1801be45a  cmp     ecx, 8
0x1801be45d  jg      loc_1801BE7DF
0x1801be463  jz      loc_1801BE776
0x1801be469  test    ecx, ecx
0x1801be46b  jz      loc_1801BE767
0x1801be471  sub     ecx, 1
0x1801be474  jz      loc_1801BE6FA
0x1801be47a  sub     ecx, 1
0x1801be47d  jz      loc_1801BE69B
0x1801be483  sub     ecx, 1
0x1801be486  jz      loc_1801BE639
0x1801be48c  sub     ecx, 1
0x1801be48f  jz      loc_1801BE5DA
0x1801be495  sub     ecx, 1
0x1801be498  jz      loc_1801BE573
0x1801be49e  sub     ecx, 1
0x1801be4a1  jz      short loc_1801BE511
0x1801be4a3  cmp     ecx, 1
0x1801be4a6  jnz     def_1801BEC0D; jumptable 00000001801BEC0D default case
0x1801be4ac  mov     [rbp+3Fh+var_B8], r8
0x1801be4b0  mov     r8, [rbp+47h]
0x1801be4b4  mov     rdx, r14
0x1801be4b7  lea     rcx, [rbp+3Fh+var_70]
0x1801be4bb  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801be4c0  nop
0x1801be4c1  mov     rax, [r15]
0x1801be4c4  lea     rdx, [rbp+3Fh+var_B8]
0x1801be4c8  mov     rcx, r15
0x1801be4cb  mov     rax, [rax+70h]
0x1801be4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be4d4  mov     ebx, eax
0x1801be4d6  test    r14, r14
0x1801be4d9  jz      short loc_1801BE4E8
0x1801be4db  mov     rcx, [r14+4A0h]; this
0x1801be4e2  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801be4e7  nop
0x1801be4e8  lea     rcx, [rbp+3Fh+var_70]
0x1801be4ec  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801be4f1  test    ebx, ebx
0x1801be4f3  jns     short loc_1801BE500
0x1801be4f5  mov     edx, ebx; int
0x1801be4f7  mov     rcx, r14; struct Js::ScriptContext *
0x1801be4fa  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801be500  mov     rdx, r14
0x1801be503  mov     rcx, [rbp+3Fh+var_B8]
0x1801be507  call    ?ToVar@?$JavascriptTypedNumber@_K@Js@@SAPEAX_KPEAVScriptContext@2@@Z; Js::JavascriptTypedNumber<unsigned __int64>::ToVar(unsigned __int64,Js::ScriptContext *)
0x1801be50c  jmp     loc_1801BE5D2
0x1801be511  mov     [rbp+3Fh+var_B8], r8
0x1801be515  mov     r8, [rbp+47h]
0x1801be519  mov     rdx, r14
0x1801be51c  lea     rcx, [rbp+3Fh+var_70]
0x1801be520  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801be525  nop
0x1801be526  mov     rax, [r15]
0x1801be529  lea     rdx, [rbp+3Fh+var_B8]
0x1801be52d  mov     rcx, r15
0x1801be530  mov     rax, [rax+68h]
0x1801be534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be539  mov     ebx, eax
0x1801be53b  test    r14, r14
0x1801be53e  jz      short loc_1801BE54D
0x1801be540  mov     rcx, [r14+4A0h]; this
0x1801be547  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801be54c  nop
0x1801be54d  lea     rcx, [rbp+3Fh+var_70]
0x1801be551  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801be556  test    ebx, ebx
0x1801be558  jns     short loc_1801BE565
0x1801be55a  mov     edx, ebx; int
0x1801be55c  mov     rcx, r14; struct Js::ScriptContext *
0x1801be55f  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801be565  mov     rdx, r14
0x1801be568  mov     rcx, [rbp+3Fh+var_B8]
0x1801be56c  call    ?ToVar@?$JavascriptTypedNumber@_J@Js@@SAPEAX_JPEAVScriptContext@2@@Z; Js::JavascriptTypedNumber<__int64>::ToVar(__int64,Js::ScriptContext *)
0x1801be571  jmp     short loc_1801BE5D2
0x1801be573  mov     [rsp+110h+var_C0], r8d
0x1801be578  mov     r8, [rbp+47h]
0x1801be57c  mov     rdx, r14
0x1801be57f  lea     rcx, [rbp+3Fh+var_70]
0x1801be583  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801be588  nop
0x1801be589  mov     rax, [r15]
0x1801be58c  lea     rdx, [rsp+110h+var_C0]
0x1801be591  mov     rcx, r15
0x1801be594  mov     rax, [rax+60h]
0x1801be598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be59d  mov     ebx, eax
0x1801be59f  test    r14, r14
0x1801be5a2  jz      short loc_1801BE5B1
0x1801be5a4  mov     rcx, [r14+4A0h]; this
0x1801be5ab  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801be5b0  nop
0x1801be5b1  lea     rcx, [rbp+3Fh+var_70]
0x1801be5b5  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801be5ba  test    ebx, ebx
0x1801be5bc  jns     short loc_1801BE5C9
0x1801be5be  mov     edx, ebx; int
0x1801be5c0  mov     rcx, r14; struct Js::ScriptContext *
0x1801be5c3  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801be5c9  mov     ecx, [rsp+110h+var_C0]; unsigned int
0x1801be5cd  call    ?ToVar@JavascriptNumber@Js@@SAPEAXIPEAVScriptContext@2@@Z; Js::JavascriptNumber::ToVar(uint,Js::ScriptContext *)
0x1801be5d2  mov     rbx, rax
0x1801be5d5  jmp     loc_1801BF602
0x1801be5da  mov     [rsp+110h+var_C0], r8d
0x1801be5df  mov     r8, [rbp+47h]
0x1801be5e3  mov     rdx, r14
0x1801be5e6  lea     rcx, [rbp+3Fh+var_70]
0x1801be5ea  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801be5ef  nop
0x1801be5f0  mov     rax, [r15]
0x1801be5f3  lea     rdx, [rsp+110h+var_C0]
0x1801be5f8  mov     rcx, r15
0x1801be5fb  mov     rax, [rax+58h]
0x1801be5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be604  mov     ebx, eax
0x1801be606  test    r14, r14
0x1801be609  jz      short loc_1801BE618
0x1801be60b  mov     rcx, [r14+4A0h]; this
0x1801be612  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801be617  nop
0x1801be618  lea     rcx, [rbp+3Fh+var_70]
0x1801be61c  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801be621  test    ebx, ebx
0x1801be623  jns     short loc_1801BE630
0x1801be625  mov     edx, ebx; int
0x1801be627  mov     rcx, r14; struct Js::ScriptContext *
0x1801be62a  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801be630  mov     ebx, [rsp+110h+var_C0]
0x1801be634  jmp     loc_1801BE755
0x1801be639  xor     eax, eax
0x1801be63b  mov     word ptr [rsp+110h+var_C0], ax
0x1801be640  mov     r8, [rbp+47h]
0x1801be644  mov     rdx, r14
0x1801be647  lea     rcx, [rbp+3Fh+var_70]
0x1801be64b  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801be650  nop
0x1801be651  mov     rax, [r15]
0x1801be654  lea     rdx, [rsp+110h+var_C0]
0x1801be659  mov     rcx, r15
0x1801be65c  mov     rax, [rax+50h]
0x1801be660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be665  mov     ebx, eax
0x1801be667  test    r14, r14
0x1801be66a  jz      short loc_1801BE679
0x1801be66c  mov     rcx, [r14+4A0h]; this
0x1801be673  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801be678  nop
0x1801be679  lea     rcx, [rbp+3Fh+var_70]
0x1801be67d  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801be682  test    ebx, ebx
0x1801be684  jns     short loc_1801BE691
0x1801be686  mov     edx, ebx; int
0x1801be688  mov     rcx, r14; struct Js::ScriptContext *
0x1801be68b  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801be691  movzx   ebx, word ptr [rsp+110h+var_C0]
0x1801be696  jmp     loc_1801BE755
0x1801be69b  xor     eax, eax
0x1801be69d  mov     word ptr [rsp+110h+var_C0], ax
0x1801be6a2  mov     r8, [rbp+47h]
0x1801be6a6  mov     rdx, r14
0x1801be6a9  lea     rcx, [rbp+3Fh+var_70]
0x1801be6ad  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801be6b2  nop
0x1801be6b3  mov     rax, [r15]
0x1801be6b6  lea     rdx, [rsp+110h+var_C0]
0x1801be6bb  mov     rcx, r15
0x1801be6be  mov     rax, [rax+48h]
0x1801be6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be6c7  mov     ebx, eax
0x1801be6c9  test    r14, r14
0x1801be6cc  jz      short loc_1801BE6DB
0x1801be6ce  mov     rcx, [r14+4A0h]; this
0x1801be6d5  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801be6da  nop
0x1801be6db  lea     rcx, [rbp+3Fh+var_70]
0x1801be6df  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801be6e4  test    ebx, ebx
0x1801be6e6  jns     short loc_1801BE6F3
0x1801be6e8  mov     edx, ebx; int
0x1801be6ea  mov     rcx, r14; struct Js::ScriptContext *
0x1801be6ed  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801be6f3  movsx   ebx, word ptr [rsp+110h+var_C0]
0x1801be6f8  jmp     short loc_1801BE755
0x1801be6fa  mov     byte ptr [rsp+110h+var_C0], r8b
0x1801be6ff  mov     r8, [rbp+47h]
0x1801be703  mov     rdx, r14
0x1801be706  lea     rcx, [rbp+3Fh+var_70]
0x1801be70a  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801be70f  nop
0x1801be710  mov     rax, [r15]
0x1801be713  lea     rdx, [rsp+110h+var_C0]
0x1801be718  mov     rcx, r15
0x1801be71b  mov     rax, [rax+40h]
  ... truncated ...
```
