# Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(AutoHSTRING &,IUnknown *,Windows::Foundation::IPropertyValue *,bool,bool,int)

- ea: `0x1801c0b04`
- end: `0x1801c1f70`
- name: `?ReadPropertyValueVarFromRuntimeClassName@ProjectionMarshaler@Projection@@AEAAPEAXAEAVAutoHSTRING@@PEAUIUnknown@@PEAUIPropertyValue@Foundation@Windows@@_N3H@Z`
- size: `5228`
- prototype: `void *__fastcall(Projection::ProjectionMarshaler *this, struct AutoHSTRING *, struct IUnknown *, struct IInspectable *, bool, bool, int)`
- caller_count: `3`
- callee_count: `28`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801bfff4`
- `0x1801c3c54`
- `0x18024aa88`

## callees

- `0x18002cfbc`
- `0x18002d6cc`
- `0x180037618`
- `0x1800d5580`
- `0x1800e08d8`
- `0x1800e0908`
- `0x1800e58c0`
- `0x180156598`
- `0x1801ab38c`
- `0x1801bd22c`
- `0x1801c0b04`
- `0x1801c3250`
- `0x1801c3ed4`
- `0x1801c7f38`
- `0x1802292f8`
- `0x18022a144`
- `0x180230204`
- `0x18023d414`
- `0x180249918`
- `0x1802499c0`
- `0x180249d78`
- `0x180249dbc`
- `0x18024a454`
- `0x18024a8b8`
- `0x1802b6e64`
- `0x180306b80`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `msvcrt!wcsstr` at `0x1801c0bf5`
- `msvcrt!wcsstr` at `0x1801c0c15`
- `msvcrt!wcsstr` at `0x1801c0bf5`
- `msvcrt!wcsstr` at `0x1801c0c15`
- `KERNEL32!LoadLibraryExW` at `0x1801c0b9a`
- `KERNEL32!LoadLibraryExW` at `0x1801c0b9a`

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
    McTemplateU0z_EventWriteTransfer(v15, JSCRIPT_PROJECTION_PROPERTYVALUEVARFROMGRCN_START, v14);
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
    McTemplateU0z_EventWriteTransfer(v87, JSCRIPT_PROJECTION_PROPERTYVALUEVARFROMGRCN_STOP, v97);
  return VarFromRuntimeClassName;
}

```

## disassembly

```asm
0x1801c0b04  mov     rax, rsp
0x1801c0b07  mov     [rax+20h], r9
0x1801c0b0b  mov     [rax+18h], r8
0x1801c0b0f  mov     [rax+10h], rdx
0x1801c0b13  mov     [rax+8], rcx
0x1801c0b17  push    rbp
0x1801c0b18  push    rbx
0x1801c0b19  push    rsi
0x1801c0b1a  push    rdi
0x1801c0b1b  push    r12
0x1801c0b1d  push    r13
0x1801c0b1f  push    r14
0x1801c0b21  push    r15
0x1801c0b23  lea     rbp, [rax-47h]
0x1801c0b27  sub     rsp, 0D8h
0x1801c0b2e  mov     [rbp+3Fh+var_78], 0FFFFFFFFFFFFFFFEh
0x1801c0b36  mov     rax, cs:__security_cookie
0x1801c0b3d  xor     rax, rsp
0x1801c0b40  mov     [rbp+3Fh+var_50], rax
0x1801c0b44  mov     r13, [rbp+3Fh+arg_0]
0x1801c0b48  mov     rdi, [rbp+3Fh+arg_8]
0x1801c0b4c  mov     rsi, [rbp+3Fh+arg_10]
0x1801c0b50  mov     r15, [rbp+3Fh+arg_18]
0x1801c0b54  mov     al, [rbp+3Fh+arg_20]
0x1801c0b57  mov     [rbp+3Fh+var_AF], al
0x1801c0b5a  mov     al, [rbp+3Fh+arg_28]
0x1801c0b5d  mov     [rbp+3Fh+var_B0], al
0x1801c0b60  mov     r12d, [rbp+3Fh+arg_30]
0x1801c0b64  mov     [rbp+3Fh+var_84], 0
0x1801c0b6b  mov     rax, [r13+10h]
0x1801c0b6f  mov     rbx, [rax+60h]
0x1801c0b73  add     rbx, 20D8h
0x1801c0b7a  cmp     byte ptr [rbx+10h], 0
0x1801c0b7e  jnz     short loc_1801C0BAE
0x1801c0b80  mov     rax, [rbx]
0x1801c0b83  mov     rcx, rbx
0x1801c0b86  mov     rax, [rax+8]
0x1801c0b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0b8f  mov     rcx, rax; lpLibFileName
0x1801c0b92  xor     edx, edx; hFile
0x1801c0b94  mov     r8d, 800h; dwFlags
0x1801c0b9a  call    cs:__imp_LoadLibraryExW
0x1801c0ba1  nop     dword ptr [rax+rax+00h]
0x1801c0ba6  mov     [rbx+8], rax
0x1801c0baa  mov     byte ptr [rbx+10h], 1
0x1801c0bae  mov     rax, [rbx]
0x1801c0bb1  lea     r8, [rbp+3Fh+var_84]
0x1801c0bb5  mov     rdx, [rdi]
0x1801c0bb8  mov     rcx, rbx
0x1801c0bbb  mov     rax, [rax+28h]
0x1801c0bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0bc4  mov     rbx, rax
0x1801c0bc7  mov     [rbp+3Fh+var_80], rax
0x1801c0bcb  test    byte ptr cs:Microsoft_JScriptEnableBits, 8
0x1801c0bd2  jz      short loc_1801C0BE3
0x1801c0bd4  mov     r8, rax
0x1801c0bd7  lea     rdx, JSCRIPT_PROJECTION_PROPERTYVALUEVARFROMGRCN_START
0x1801c0bde  call    McTemplateU0z_EventWriteTransfer
0x1801c0be3  mov     rcx, [r13+10h]
0x1801c0be7  mov     r14, [rcx+70h]
0x1801c0beb  lea     rdx, aWindowsFoundat_4; "Windows.Foundation.IReference`1"
0x1801c0bf2  mov     rcx, rbx; Str
0x1801c0bf5  call    cs:__imp_wcsstr
0x1801c0bfc  nop     dword ptr [rax+rax+00h]
0x1801c0c01  test    rax, rax
0x1801c0c04  jz      short loc_1801C0C0B
0x1801c0c06  cmp     rax, rbx
0x1801c0c09  jz      short loc_1801C0C33
0x1801c0c0b  lea     rdx, aWindowsFoundat_1; "Windows.Foundation.IReferenceArray`1"
0x1801c0c12  mov     rcx, rbx; Str
0x1801c0c15  call    cs:__imp_wcsstr
0x1801c0c1c  nop     dword ptr [rax+rax+00h]
0x1801c0c21  test    rax, rax
0x1801c0c24  jz      loc_1801C1F20
0x1801c0c2a  cmp     rax, rbx
0x1801c0c2d  jnz     loc_1801C1F20
0x1801c0c33  mov     [rbp+3Fh+var_88], 0
0x1801c0c3a  mov     rcx, r14; struct Js::ScriptContext *
0x1801c0c3d  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1801c0c42  mov     r8, [rbp+47h]
0x1801c0c46  mov     rdx, r14
0x1801c0c49  lea     rcx, [rbp+3Fh+var_70]
0x1801c0c4d  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c0c52  nop
0x1801c0c53  mov     rax, [r15]
0x1801c0c56  lea     rdx, [rbp+3Fh+var_88]
0x1801c0c5a  mov     rcx, r15
0x1801c0c5d  mov     rax, [rax+30h]
0x1801c0c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0c66  mov     ebx, eax
0x1801c0c68  test    r14, r14
0x1801c0c6b  jz      short loc_1801C0C7A
0x1801c0c6d  mov     rcx, [r14+4A0h]; this
0x1801c0c74  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c0c79  nop
0x1801c0c7a  lea     rcx, [rbp+3Fh+var_70]
0x1801c0c7e  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c0c83  mov     rcx, r14; struct Js::ScriptContext *
0x1801c0c86  test    ebx, ebx
0x1801c0c88  jns     short loc_1801C0C92
0x1801c0c8a  mov     edx, ebx; int
0x1801c0c8c  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801c0c92  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1801c0c97  xor     r8d, r8d; unsigned __int16 *
0x1801c0c9a  mov     [rbp+3Fh+var_B8], r8
0x1801c0c9e  mov     ecx, [rbp+3Fh+var_88]
0x1801c0ca1  mov     eax, 401h
0x1801c0ca6  cmp     ecx, eax
0x1801c0ca8  jg      loc_1801C1444
0x1801c0cae  jz      loc_1801C139E
0x1801c0cb4  cmp     ecx, 8
0x1801c0cb7  jg      loc_1801C1039
0x1801c0cbd  jz      loc_1801C0FD0
0x1801c0cc3  test    ecx, ecx
0x1801c0cc5  jz      loc_1801C0FC1
0x1801c0ccb  sub     ecx, 1
0x1801c0cce  jz      loc_1801C0F54
0x1801c0cd4  sub     ecx, 1
0x1801c0cd7  jz      loc_1801C0EF5
0x1801c0cdd  sub     ecx, 1
0x1801c0ce0  jz      loc_1801C0E93
0x1801c0ce6  sub     ecx, 1
0x1801c0ce9  jz      loc_1801C0E34
0x1801c0cef  sub     ecx, 1
0x1801c0cf2  jz      loc_1801C0DCD
0x1801c0cf8  sub     ecx, 1
0x1801c0cfb  jz      short loc_1801C0D6B
0x1801c0cfd  cmp     ecx, 1
0x1801c0d00  jnz     def_1801C1467; jumptable 00000001801C1467 default case
0x1801c0d06  mov     [rbp+3Fh+var_B8], r8
0x1801c0d0a  mov     r8, [rbp+47h]
0x1801c0d0e  mov     rdx, r14
0x1801c0d11  lea     rcx, [rbp+3Fh+var_70]
0x1801c0d15  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c0d1a  nop
0x1801c0d1b  mov     rax, [r15]
0x1801c0d1e  lea     rdx, [rbp+3Fh+var_B8]
0x1801c0d22  mov     rcx, r15
0x1801c0d25  mov     rax, [rax+70h]
0x1801c0d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0d2e  mov     ebx, eax
0x1801c0d30  test    r14, r14
0x1801c0d33  jz      short loc_1801C0D42
0x1801c0d35  mov     rcx, [r14+4A0h]; this
0x1801c0d3c  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c0d41  nop
0x1801c0d42  lea     rcx, [rbp+3Fh+var_70]
0x1801c0d46  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c0d4b  test    ebx, ebx
0x1801c0d4d  jns     short loc_1801C0D5A
0x1801c0d4f  mov     edx, ebx; int
0x1801c0d51  mov     rcx, r14; struct Js::ScriptContext *
0x1801c0d54  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801c0d5a  mov     rdx, r14
0x1801c0d5d  mov     rcx, [rbp+3Fh+var_B8]
0x1801c0d61  call    ?ToVar@?$JavascriptTypedNumber@_K@Js@@SAPEAX_KPEAVScriptContext@2@@Z; Js::JavascriptTypedNumber<unsigned __int64>::ToVar(unsigned __int64,Js::ScriptContext *)
0x1801c0d66  jmp     loc_1801C0E2C
0x1801c0d6b  mov     [rbp+3Fh+var_B8], r8
0x1801c0d6f  mov     r8, [rbp+47h]
0x1801c0d73  mov     rdx, r14
0x1801c0d76  lea     rcx, [rbp+3Fh+var_70]
0x1801c0d7a  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c0d7f  nop
0x1801c0d80  mov     rax, [r15]
0x1801c0d83  lea     rdx, [rbp+3Fh+var_B8]
0x1801c0d87  mov     rcx, r15
0x1801c0d8a  mov     rax, [rax+68h]
0x1801c0d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0d93  mov     ebx, eax
0x1801c0d95  test    r14, r14
0x1801c0d98  jz      short loc_1801C0DA7
0x1801c0d9a  mov     rcx, [r14+4A0h]; this
0x1801c0da1  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c0da6  nop
0x1801c0da7  lea     rcx, [rbp+3Fh+var_70]
0x1801c0dab  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c0db0  test    ebx, ebx
0x1801c0db2  jns     short loc_1801C0DBF
0x1801c0db4  mov     edx, ebx; int
0x1801c0db6  mov     rcx, r14; struct Js::ScriptContext *
0x1801c0db9  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801c0dbf  mov     rdx, r14
0x1801c0dc2  mov     rcx, [rbp+3Fh+var_B8]
0x1801c0dc6  call    ?ToVar@?$JavascriptTypedNumber@_J@Js@@SAPEAX_JPEAVScriptContext@2@@Z; Js::JavascriptTypedNumber<__int64>::ToVar(__int64,Js::ScriptContext *)
0x1801c0dcb  jmp     short loc_1801C0E2C
0x1801c0dcd  mov     [rsp+110h+var_C0], r8d
0x1801c0dd2  mov     r8, [rbp+47h]
0x1801c0dd6  mov     rdx, r14
0x1801c0dd9  lea     rcx, [rbp+3Fh+var_70]
0x1801c0ddd  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c0de2  nop
0x1801c0de3  mov     rax, [r15]
0x1801c0de6  lea     rdx, [rsp+110h+var_C0]
0x1801c0deb  mov     rcx, r15
0x1801c0dee  mov     rax, [rax+60h]
0x1801c0df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0df7  mov     ebx, eax
0x1801c0df9  test    r14, r14
0x1801c0dfc  jz      short loc_1801C0E0B
0x1801c0dfe  mov     rcx, [r14+4A0h]; this
0x1801c0e05  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c0e0a  nop
0x1801c0e0b  lea     rcx, [rbp+3Fh+var_70]
0x1801c0e0f  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c0e14  test    ebx, ebx
0x1801c0e16  jns     short loc_1801C0E23
0x1801c0e18  mov     edx, ebx; int
0x1801c0e1a  mov     rcx, r14; struct Js::ScriptContext *
0x1801c0e1d  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801c0e23  mov     ecx, [rsp+110h+var_C0]; unsigned int
0x1801c0e27  call    ?ToVar@JavascriptNumber@Js@@SAPEAXIPEAVScriptContext@2@@Z; Js::JavascriptNumber::ToVar(uint,Js::ScriptContext *)
0x1801c0e2c  mov     rbx, rax
0x1801c0e2f  jmp     loc_1801C1E60
0x1801c0e34  mov     [rsp+110h+var_C0], r8d
0x1801c0e39  mov     r8, [rbp+47h]
0x1801c0e3d  mov     rdx, r14
0x1801c0e40  lea     rcx, [rbp+3Fh+var_70]
0x1801c0e44  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c0e49  nop
0x1801c0e4a  mov     rax, [r15]
0x1801c0e4d  lea     rdx, [rsp+110h+var_C0]
0x1801c0e52  mov     rcx, r15
0x1801c0e55  mov     rax, [rax+58h]
0x1801c0e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0e5e  mov     ebx, eax
0x1801c0e60  test    r14, r14
0x1801c0e63  jz      short loc_1801C0E72
0x1801c0e65  mov     rcx, [r14+4A0h]; this
0x1801c0e6c  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c0e71  nop
0x1801c0e72  lea     rcx, [rbp+3Fh+var_70]
0x1801c0e76  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c0e7b  test    ebx, ebx
0x1801c0e7d  jns     short loc_1801C0E8A
0x1801c0e7f  mov     edx, ebx; int
0x1801c0e81  mov     rcx, r14; struct Js::ScriptContext *
0x1801c0e84  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801c0e8a  mov     ebx, [rsp+110h+var_C0]
0x1801c0e8e  jmp     loc_1801C0FAF
0x1801c0e93  xor     eax, eax
0x1801c0e95  mov     word ptr [rsp+110h+var_C0], ax
0x1801c0e9a  mov     r8, [rbp+47h]
0x1801c0e9e  mov     rdx, r14
0x1801c0ea1  lea     rcx, [rbp+3Fh+var_70]
0x1801c0ea5  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c0eaa  nop
0x1801c0eab  mov     rax, [r15]
0x1801c0eae  lea     rdx, [rsp+110h+var_C0]
0x1801c0eb3  mov     rcx, r15
0x1801c0eb6  mov     rax, [rax+50h]
0x1801c0eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0ebf  mov     ebx, eax
0x1801c0ec1  test    r14, r14
0x1801c0ec4  jz      short loc_1801C0ED3
0x1801c0ec6  mov     rcx, [r14+4A0h]; this
0x1801c0ecd  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c0ed2  nop
0x1801c0ed3  lea     rcx, [rbp+3Fh+var_70]
0x1801c0ed7  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c0edc  test    ebx, ebx
0x1801c0ede  jns     short loc_1801C0EEB
0x1801c0ee0  mov     edx, ebx; int
0x1801c0ee2  mov     rcx, r14; struct Js::ScriptContext *
0x1801c0ee5  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801c0eeb  movzx   ebx, word ptr [rsp+110h+var_C0]
0x1801c0ef0  jmp     loc_1801C0FAF
0x1801c0ef5  xor     eax, eax
0x1801c0ef7  mov     word ptr [rsp+110h+var_C0], ax
0x1801c0efc  mov     r8, [rbp+47h]
0x1801c0f00  mov     rdx, r14
0x1801c0f03  lea     rcx, [rbp+3Fh+var_70]
0x1801c0f07  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c0f0c  nop
0x1801c0f0d  mov     rax, [r15]
0x1801c0f10  lea     rdx, [rsp+110h+var_C0]
0x1801c0f15  mov     rcx, r15
0x1801c0f18  mov     rax, [rax+48h]
0x1801c0f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0f21  mov     ebx, eax
0x1801c0f23  test    r14, r14
0x1801c0f26  jz      short loc_1801C0F35
0x1801c0f28  mov     rcx, [r14+4A0h]; this
0x1801c0f2f  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801c0f34  nop
0x1801c0f35  lea     rcx, [rbp+3Fh+var_70]
0x1801c0f39  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801c0f3e  test    ebx, ebx
0x1801c0f40  jns     short loc_1801C0F4D
0x1801c0f42  mov     edx, ebx; int
0x1801c0f44  mov     rcx, r14; struct Js::ScriptContext *
0x1801c0f47  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1801c0f4d  movsx   ebx, word ptr [rsp+110h+var_C0]
0x1801c0f52  jmp     short loc_1801C0FAF
0x1801c0f54  mov     byte ptr [rsp+110h+var_C0], r8b
0x1801c0f59  mov     r8, [rbp+47h]
0x1801c0f5d  mov     rdx, r14
0x1801c0f60  lea     rcx, [rbp+3Fh+var_70]
0x1801c0f64  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801c0f69  nop
0x1801c0f6a  mov     rax, [r15]
  ... truncated ...
```
