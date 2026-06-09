# Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(AutoHSTRING &,IUnknown *,Windows::Foundation::IPropertyValue *,bool,bool,int)

- ea: `0x180004054`
- end: `0x180005924`
- name: `?ReadPropertyValueVarFromRuntimeClassName@ProjectionMarshaler@Projection@@AEAAPEAXAEAVAutoHSTRING@@PEAUIUnknown@@PEAUIPropertyValue@Foundation@Windows@@_N3H@Z`
- size: `6352`
- prototype: `void *__fastcall(Projection::ProjectionMarshaler *__hidden this, struct AutoHSTRING *, struct IUnknown *, struct Windows::Foundation::IPropertyValue *, bool, bool, int)`
- caller_count: `3`
- callee_count: `29`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003d00`
- `0x18008e884`
- `0x180091978`

## callees

- `0x180004014`
- `0x180004054`
- `0x18000592c`
- `0x18001aaa4`
- `0x1800891a4`
- `0x18008abf8`
- `0x18008ac88`
- `0x18008ad14`
- `0x18008ade4`
- `0x18008af9c`
- `0x18008c8dc`
- `0x18009aaa0`
- `0x18014aab8`
- `0x18017c3a8`
- `0x1801a25bc`
- `0x1801b0600`
- `0x1801dc434`
- `0x18022d8b0`
- `0x180231218`
- `0x1802401b0`
- `0x18029f6b0`
- `0x18038f438`
- `0x1803c2828`
- `0x1803e9254`
- `0x180471cdc`
- `0x180471d98`
- `0x18052165c`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180004147`
- `msvcrt!wcsstr` at `0x180004167`
- `msvcrt!wcsstr` at `0x180004147`
- `msvcrt!wcsstr` at `0x180004167`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800040ec`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800040ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=64
void *__fastcall Projection::ProjectionMarshaler::ReadPropertyValueVarFromRuntimeClassName(
        Projection::ProjectionMarshaler *this,
        struct AutoHSTRING *a2,
        struct IUnknown *a3,
        struct IInspectable *a4,
        bool a5,
        bool a6,
        int a7)
{
  __int64 v10; // rax
  __int64 v11; // rbx
  const WCHAR *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  const wchar_t *v15; // rbx
  __int64 v16; // r14
  wchar_t *v17; // rax
  wchar_t *v18; // rax
  _BYTE *v19; // rdi
  char v20; // bl
  int v21; // esi
  __int64 v22; // rdi
  char v23; // bl
  int v24; // esi
  struct Js::JavascriptString *StringForChar; // rax
  __int64 v26; // rdi
  char v27; // bl
  int v28; // esi
  __int64 v29; // rdi
  char v30; // bl
  int v31; // esi
  struct Js::ScriptContext *v32; // rdx
  void *VarFromRuntimeClassName; // rbx
  __int64 v34; // rdi
  char v35; // bl
  int v36; // esi
  __int64 v37; // rbx
  __int64 v38; // rdi
  char v39; // bl
  int v40; // esi
  __int64 v41; // rdi
  char v42; // bl
  int v43; // esi
  __int64 v44; // rdi
  char v45; // bl
  int v46; // esi
  __int64 v47; // rdi
  char v48; // bl
  int v49; // esi
  struct Js::ScriptContext *v50; // rdx
  double v51; // xmm0_8
  _BYTE *v52; // rdi
  char v53; // bl
  int v54; // esi
  __int64 v55; // rdi
  char v56; // bl
  int v57; // esi
  __int64 v58; // rdi
  char v59; // bl
  int v60; // esi
  __int64 v61; // rdi
  char v62; // bl
  int v63; // esi
  unsigned __int64 v64; // r8
  __int64 v65; // rdi
  char v66; // bl
  int v67; // esi
  __int64 v68; // rdi
  char v69; // bl
  int v70; // esi
  __int64 v71; // rdi
  char v72; // bl
  int v73; // esi
  __int64 v74; // rdi
  char v75; // bl
  int v76; // esi
  int v77; // eax
  __int64 v78; // rdi
  char v79; // bl
  int v80; // esi
  int v81; // eax
  __int64 v82; // rdi
  char v83; // bl
  int v84; // esi
  int v85; // eax
  __int64 v86; // rdi
  char v87; // bl
  int v88; // esi
  int v89; // eax
  __int64 v90; // rdi
  char v91; // bl
  int v92; // esi
  int v93; // eax
  __int64 v94; // rdi
  char v95; // bl
  int v96; // esi
  int v97; // eax
  __int64 v98; // rdi
  char v99; // bl
  int v100; // esi
  int v101; // eax
  __int64 v102; // rdi
  char v103; // bl
  int v104; // esi
  int v105; // eax
  __int64 v106; // rdi
  char v107; // bl
  int v108; // esi
  int v109; // eax
  __int64 v110; // rdi
  char v111; // bl
  int v112; // esi
  int v113; // eax
  __int64 v114; // rdi
  char v115; // bl
  int v116; // esi
  int v117; // eax
  __int64 v118; // rdi
  char v119; // bl
  int v120; // esi
  int v121; // eax
  __int64 v122; // rdi
  char v123; // bl
  int v124; // esi
  unsigned int v125; // ebx
  unsigned __int8 *v126; // rdi
  struct Projection::ProjectionContext *v127; // rsi
  const struct ProjectionModel::ConcreteType *v128; // rax
  int v129; // eax
  __int64 v130; // rdi
  char v131; // bl
  int v132; // esi
  unsigned int v133; // ebx
  unsigned __int8 *v134; // rdi
  struct Projection::ProjectionContext *v135; // rsi
  const struct ProjectionModel::ConcreteType *v136; // rax
  int v137; // eax
  __int64 v138; // rdi
  char v139; // bl
  int v140; // esi
  unsigned int v141; // ebx
  unsigned __int8 *v142; // rdi
  struct Projection::ProjectionContext *v143; // rsi
  const struct ProjectionModel::ConcreteType *v144; // rax
  int v145; // eax
  __int64 v146; // rdi
  char v147; // bl
  int v148; // esi
  int v149; // eax
  __int64 v150; // rcx
  struct Js::DynamicObject *v151; // rax
  unsigned int v152; // eax
  bool v154[8]; // [rsp+58h] [rbp-91h] BYREF
  void *v155; // [rsp+60h] [rbp-89h] BYREF
  char v156; // [rsp+68h] [rbp-81h]
  __int64 v157; // [rsp+70h] [rbp-79h] BYREF
  char v158; // [rsp+78h] [rbp-71h]
  _BYTE v159[32]; // [rsp+90h] [rbp-59h] BYREF
  int v160; // [rsp+B0h] [rbp-39h] BYREF
  __int64 v161; // [rsp+B8h] [rbp-31h]
  __int64 v162; // [rsp+C0h] [rbp-29h]
  struct IUnknown *v163[2]; // [rsp+C8h] [rbp-21h] BYREF
  void *retaddr; // [rsp+130h] [rbp+47h]

  v162 = -2;
  v163[0] = a3;
  v154[5] = a5;
  v154[4] = a6;
  *(_DWORD *)v154 = a7;
  v10 = *((_QWORD *)this + 2);
  v11 = *(_QWORD *)(v10 + 96) + 7920LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v10 + 96) + 7936LL) )
  {
    v12 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(*(_QWORD *)(v10 + 96) + 7920LL);
    *(_QWORD *)(v11 + 8) = LoadLibraryExW(v12, 0, 0x800u);
    *(_BYTE *)(v11 + 16) = 1;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, *(_QWORD *)a2, 0);
  v15 = (const wchar_t *)v13;
  v161 = v13;
  if ( (Microsoft_JScriptEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v14, JSCRIPT_PROJECTION_PROPERTYVALUEVARFROMGRCN_START, v13);
  v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 112LL);
  v17 = wcsstr(v15, L"Windows.Foundation.IReference`1");
  if ( !v17 || v17 != v15 )
  {
    v18 = wcsstr(v15, L"Windows.Foundation.IReferenceArray`1");
    if ( !v18 || v18 != v15 )
      Js::JavascriptError::ThrowTypeError((struct Js::ScriptContext *)v16, -2146823194, v15);
  }
  v160 = 0;
  Js::JavascriptErrorDebug::ClearErrorInfo((struct Js::ScriptContext *)v16);
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
  v19 = *(_BYTE **)(v16 + 880);
  v155 = v19;
  v156 = v19[313];
  v20 = v156;
  v19[313] = 1;
  v21 = ((__int64 (__fastcall *)(struct IInspectable *, int *))a4->lpVtbl[1].QueryInterface)(a4, &v160);
  ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
  v19[313] = v20;
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
  if ( v21 < 0 )
    Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v21);
  Js::JavascriptErrorDebug::ClearErrorInfo((struct Js::ScriptContext *)v16);
  v155 = 0;
  if ( v160 > 1025 )
  {
    switch ( v160 )
    {
      case 1026:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v78 = *(_QWORD *)(v16 + 880);
        v157 = v78;
        v158 = *(_BYTE *)(v78 + 313);
        v79 = v158;
        *(_BYTE *)(v78 + 313) = 1;
        v80 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[4].GetIids)(
                a4,
                v154,
                v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v78 + 313) = v79;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v80 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v80);
        v81 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 40LL),
                *((struct Projection::ProjectionContext **)this + 2),
                (unsigned __int8 *)v163[0],
                *(unsigned int *)v154,
                *(unsigned int *)v154,
                1,
                &v155,
                1);
        if ( v81 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v81);
        goto LABEL_146;
      case 1027:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v82 = *(_QWORD *)(v16 + 880);
        v157 = v82;
        v158 = *(_BYTE *)(v82 + 313);
        v83 = v158;
        *(_BYTE *)(v82 + 313) = 1;
        v84 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[4].GetRuntimeClassName)(
                a4,
                v154,
                v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v82 + 313) = v83;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v84 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v84);
        v85 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 88LL),
                *((struct Projection::ProjectionContext **)this + 2),
                (unsigned __int8 *)v163[0],
                *(unsigned int *)v154,
                *(unsigned int *)v154,
                1,
                &v155,
                1);
        if ( v85 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v85);
        goto LABEL_146;
      case 1028:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v86 = *(_QWORD *)(v16 + 880);
        v157 = v86;
        v158 = *(_BYTE *)(v86 + 313);
        v87 = v158;
        *(_BYTE *)(v86 + 313) = 1;
        v88 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[4].GetTrustLevel)(
                a4,
                v154,
                v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v86 + 313) = v87;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v88 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v88);
        v89 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 48LL),
                *((struct Projection::ProjectionContext **)this + 2),
                (unsigned __int8 *)v163[0],
                *(unsigned int *)v154,
                *(unsigned int *)v154,
                1,
                &v155,
                1);
        if ( v89 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v89);
        goto LABEL_146;
      case 1029:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v90 = *(_QWORD *)(v16 + 880);
        v157 = v90;
        v158 = *(_BYTE *)(v90 + 313);
        v91 = v158;
        *(_BYTE *)(v90 + 313) = 1;
        v92 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[5].QueryInterface)(
                a4,
                v154,
                v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v90 + 313) = v91;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v92 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v92);
        v93 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 96LL),
                *((struct Projection::ProjectionContext **)this + 2),
                (unsigned __int8 *)v163[0],
                *(unsigned int *)v154,
                *(unsigned int *)v154,
                1,
                &v155,
                1);
        if ( v93 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v93);
        goto LABEL_146;
      case 1030:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v94 = *(_QWORD *)(v16 + 880);
        v157 = v94;
        v158 = *(_BYTE *)(v94 + 313);
        v95 = v158;
        *(_BYTE *)(v94 + 313) = 1;
        v96 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[5].AddRef)(
                a4,
                v154,
                v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v94 + 313) = v95;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v96 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v96);
        v97 = Projection::ArrayProjection::CreateArrayProjectionObject(
                *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 56LL),
                *((struct Projection::ProjectionContext **)this + 2),
                (unsigned __int8 *)v163[0],
                *(unsigned int *)v154,
                *(unsigned int *)v154,
                1,
                &v155,
                1);
        if ( v97 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v97);
        goto LABEL_146;
      case 1031:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v98 = *(_QWORD *)(v16 + 880);
        v157 = v98;
        v158 = *(_BYTE *)(v98 + 313);
        v99 = v158;
        *(_BYTE *)(v98 + 313) = 1;
        v100 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[5].Release)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v98 + 313) = v99;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v100 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v100);
        v101 = Projection::ArrayProjection::CreateArrayProjectionObject(
                 *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 104LL),
                 *((struct Projection::ProjectionContext **)this + 2),
                 (unsigned __int8 *)v163[0],
                 *(unsigned int *)v154,
                 *(unsigned int *)v154,
                 1,
                 &v155,
                 1);
        if ( v101 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v101);
        goto LABEL_146;
      case 1032:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v102 = *(_QWORD *)(v16 + 880);
        v157 = v102;
        v158 = *(_BYTE *)(v102 + 313);
        v103 = v158;
        *(_BYTE *)(v102 + 313) = 1;
        v104 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[5].GetIids)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v102 + 313) = v103;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v104 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v104);
        v105 = Projection::ArrayProjection::CreateArrayProjectionObject(
                 *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 64LL),
                 *((struct Projection::ProjectionContext **)this + 2),
                 (unsigned __int8 *)v163[0],
                 *(unsigned int *)v154,
                 *(unsigned int *)v154,
                 1,
                 &v155,
                 1);
        if ( v105 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v105);
        goto LABEL_146;
      case 1033:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v106 = *(_QWORD *)(v16 + 880);
        v157 = v106;
        v158 = *(_BYTE *)(v106 + 313);
        v107 = v158;
        *(_BYTE *)(v106 + 313) = 1;
        v108 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[5].GetRuntimeClassName)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v106 + 313) = v107;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v108 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v108);
        v109 = Projection::ArrayProjection::CreateArrayProjectionObject(
                 *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 72LL),
                 *((struct Projection::ProjectionContext **)this + 2),
                 (unsigned __int8 *)v163[0],
                 *(unsigned int *)v154,
                 *(unsigned int *)v154,
                 1,
                 &v155,
                 1);
        if ( v109 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v109);
        goto LABEL_146;
      case 1034:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v110 = *(_QWORD *)(v16 + 880);
        v157 = v110;
        v158 = *(_BYTE *)(v110 + 313);
        v111 = v158;
        *(_BYTE *)(v110 + 313) = 1;
        v112 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[5].GetTrustLevel)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v110 + 313) = v111;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v112 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v112);
        v113 = Projection::ArrayProjection::CreateArrayProjectionObject(
                 *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 24LL),
                 *((struct Projection::ProjectionContext **)this + 2),
                 (unsigned __int8 *)v163[0],
                 *(unsigned int *)v154,
                 *(unsigned int *)v154,
                 1,
                 &v155,
                 1);
        if ( v113 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v113);
        goto LABEL_146;
      case 1035:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v114 = *(_QWORD *)(v16 + 880);
        v157 = v114;
        v158 = *(_BYTE *)(v114 + 313);
        v115 = v158;
        *(_BYTE *)(v114 + 313) = 1;
        v116 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[6].QueryInterface)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v114 + 313) = v115;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v116 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v116);
        v117 = Projection::ArrayProjection::CreateArrayProjectionObject(
                 *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 112LL),
                 *((struct Projection::ProjectionContext **)this + 2),
                 (unsigned __int8 *)v163[0],
                 *(unsigned int *)v154,
                 *(unsigned int *)v154,
                 1,
                 &v155,
                 1);
        if ( v117 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v117);
        goto LABEL_146;
      case 1036:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v118 = *(_QWORD *)(v16 + 880);
        v157 = v118;
        v158 = *(_BYTE *)(v118 + 313);
        v119 = v158;
        *(_BYTE *)(v118 + 313) = 1;
        v120 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[6].AddRef)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v118 + 313) = v119;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v120 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v120);
        v121 = Projection::ArrayProjection::CreateArrayProjectionObject(
                 *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 80LL),
                 *((struct Projection::ProjectionContext **)this + 2),
                 (unsigned __int8 *)v163[0],
                 *(unsigned int *)v154,
                 *(unsigned int *)v154,
                 1,
                 &v155,
                 1);
        if ( v121 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v121);
        goto LABEL_146;
      case 1037:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v146 = *(_QWORD *)(v16 + 880);
        v157 = v146;
        v158 = *(_BYTE *)(v146 + 313);
        v147 = v158;
        *(_BYTE *)(v146 + 313) = 1;
        v148 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[6].Release)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v146 + 313) = v147;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v148 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v148);
        v149 = Projection::ArrayProjection::CreateArrayProjectionObject(
                 *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 136LL),
                 *((struct Projection::ProjectionContext **)this + 2),
                 (unsigned __int8 *)v163[0],
                 *(unsigned int *)v154,
                 *(unsigned int *)v154,
                 1,
                 &v155,
                 1);
        if ( v149 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v149);
        goto LABEL_146;
      case 1038:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v122 = *(_QWORD *)(v16 + 880);
        v157 = v122;
        v158 = *(_BYTE *)(v122 + 313);
        v123 = v158;
        *(_BYTE *)(v122 + 313) = 1;
        v124 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[6].GetRuntimeClassName)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v122 + 313) = v123;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v124 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v124);
        v125 = *(_DWORD *)v154;
        v126 = (unsigned __int8 *)v163[0];
        v127 = (struct Projection::ProjectionContext *)*((_QWORD *)this + 2);
        v128 = ProjectionModel::ConcreteType::From(*(const struct ProjectionModel::Type **)(*((_QWORD *)v127 + 15)
                                                                                          + 152LL));
        v129 = Projection::ArrayProjection::CreateArrayProjectionObject(v128, v127, v126, v125, v125, 1, &v155, 1);
        if ( v129 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v129);
        goto LABEL_146;
      case 1039:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v130 = *(_QWORD *)(v16 + 880);
        v157 = v130;
        v158 = *(_BYTE *)(v130 + 313);
        v131 = v158;
        *(_BYTE *)(v130 + 313) = 1;
        v132 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[6].GetTrustLevel)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v130 + 313) = v131;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v132 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v132);
        v133 = *(_DWORD *)v154;
        v134 = (unsigned __int8 *)v163[0];
        v135 = (struct Projection::ProjectionContext *)*((_QWORD *)this + 2);
        v136 = ProjectionModel::ConcreteType::From(*(const struct ProjectionModel::Type **)(*((_QWORD *)v135 + 15)
                                                                                          + 160LL));
        v137 = Projection::ArrayProjection::CreateArrayProjectionObject(v136, v135, v134, v133, v133, 1, &v155, 1);
        if ( v137 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v137);
        goto LABEL_146;
      case 1040:
        v163[0] = 0;
        *(_DWORD *)v154 = 0;
        Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
        v138 = *(_QWORD *)(v16 + 880);
        v157 = v138;
        v158 = *(_BYTE *)(v138 + 313);
        v139 = v158;
        *(_BYTE *)(v138 + 313) = 1;
        v140 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[6].GetIids)(
                 a4,
                 v154,
                 v163);
        ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
        *(_BYTE *)(v138 + 313) = v139;
        Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
        if ( v140 < 0 )
          Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v140);
        v141 = *(_DWORD *)v154;
        v142 = (unsigned __int8 *)v163[0];
        v143 = (struct Projection::ProjectionContext *)*((_QWORD *)this + 2);
        v144 = ProjectionModel::ConcreteType::From(*(const struct ProjectionModel::Type **)(*((_QWORD *)v143 + 15)
                                                                                          + 144LL));
        v145 = Projection::ArrayProjection::CreateArrayProjectionObject(v144, v143, v142, v141, v141, 1, &v155, 1);
        if ( v145 < 0 )
          Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v145);
        goto LABEL_146;
      default:
        goto LABEL_153;
    }
  }
  if ( v160 == 1025 )
  {
    v163[0] = 0;
    *(_DWORD *)v154 = 0;
    Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v159, v16, retaddr);
    v74 = *(_QWORD *)(v16 + 880);
    v157 = v74;
    v158 = *(_BYTE *)(v74 + 313);
    v75 = v158;
    *(_BYTE *)(v74 + 313) = 1;
    v76 = ((__int64 (__fastcall *)(struct IInspectable *, bool *, struct IUnknown **))a4->lpVtbl[4].Release)(
            a4,
            v154,
            v163);
    ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
    *(_BYTE *)(v74 + 313) = v75;
    Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v159);
    if ( v76 < 0 )
      Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v76);
    v77 = Projection::ArrayProjection::CreateArrayProjectionObject(
            *(const struct ProjectionModel::ConcreteType **)(*(_QWORD *)(*((_QWORD *)this + 2) + 120LL) + 32LL),
            *((struct Projection::ProjectionContext **)this + 2),
            (unsigned __int8 *)v163[0],
            *(unsigned int *)v154,
            *(unsigned int *)v154,
            1,
            &v155,
            1);
    if ( v77 < 0 )
      Js::JavascriptError::MapAndThrowError((struct Js::ScriptContext *)v16, v77);
LABEL_146:
    VarFromRuntimeClassName = v155;
    goto LABEL_147;
  }
  if ( v160 > 8 )
  {
    if ( v160 != 9 )
    {
      switch ( v160 )
      {
        case 10:
          *(_WORD *)v154 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v68 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v68;
          LOBYTE(v163[1]) = *(_BYTE *)(v68 + 313);
          v69 = (char)v163[1];
          *(_BYTE *)(v68 + 313) = 1;
          v70 = ((__int64 (__fastcall *)(struct IInspectable *, bool *))a4->lpVtbl[2].GetTrustLevel)(a4, v154);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v68 + 313) = v69;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v70 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v70);
          StringForChar = Js::CharStringCache::GetStringForChar(
                            (Js::CharStringCache *)(*(_QWORD *)(v16 + 8) + 4992LL),
                            *(unsigned __int16 *)v154);
          goto LABEL_32;
        case 11:
          v154[0] = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v65 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v65;
          LOBYTE(v163[1]) = *(_BYTE *)(v65 + 313);
          v66 = (char)v163[1];
          *(_BYTE *)(v65 + 313) = 1;
          v67 = ((__int64 (__fastcall *)(struct IInspectable *, bool *))a4->lpVtbl[3].QueryInterface)(a4, v154);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v65 + 313) = v66;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v67 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v67);
          VarFromRuntimeClassName = *(void **)(*(_QWORD *)(v16 + 8) + (-(__int64)v154[0] & 0xFFFFFFFFFFFFFFF8uLL) + 936);
          goto LABEL_147;
        case 12:
          v155 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v61 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v61;
          LOBYTE(v163[1]) = *(_BYTE *)(v61 + 313);
          v62 = (char)v163[1];
          *(_BYTE *)(v61 + 313) = 1;
          v63 = ((__int64 (__fastcall *)(struct IInspectable *, void **))a4->lpVtbl[3].AddRef)(a4, &v155);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v61 + 313) = v62;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v63 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v63);
          *((_QWORD *)this + 3) = regex::ImmutableList<HSTRING__ *>::Prepend(
                                    *((_QWORD *)this + 3),
                                    v155,
                                    *((_QWORD *)this + 1));
          StringForChar = (struct Js::JavascriptString *)Projection::ProjectionMarshaler::ReadOutString(
                                                           this,
                                                           (unsigned __int8 *)&v155,
                                                           v64);
          goto LABEL_32;
        case 13:
          Js::JavascriptError::ThrowTypeError((struct Js::ScriptContext *)v16, -2146828275, 0);
        case 14:
          v155 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v58 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v58;
          LOBYTE(v163[1]) = *(_BYTE *)(v58 + 313);
          v59 = (char)v163[1];
          *(_BYTE *)(v58 + 313) = 1;
          v60 = ((__int64 (__fastcall *)(struct IInspectable *, void **))a4->lpVtbl[3].GetIids)(a4, &v155);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v58 + 313) = v59;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v60 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v60);
          StringForChar = (struct Js::JavascriptString *)Projection::ProjectionMarshaler::ReadOutWindowsFoundationDateTimeType(
                                                           this,
                                                           (unsigned __int8 *)&v155,
                                                           8u);
          goto LABEL_32;
        case 15:
          v155 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v55 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v55;
          LOBYTE(v163[1]) = *(_BYTE *)(v55 + 313);
          v56 = (char)v163[1];
          *(_BYTE *)(v55 + 313) = 1;
          v57 = ((__int64 (__fastcall *)(struct IInspectable *, void **))a4->lpVtbl[3].GetRuntimeClassName)(a4, &v155);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v55 + 313) = v56;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v57 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v57);
          StringForChar = (struct Js::JavascriptString *)Projection::ProjectionMarshaler::ReadOutWindowsFoundationTimeSpanType(
                                                           this,
                                                           (unsigned __int8 *)&v155,
                                                           8u);
          goto LABEL_32;
        case 16:
          *(_OWORD *)v163 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v52 = *(_BYTE **)(v16 + 880);
          v155 = v52;
          v156 = v52[313];
          v53 = v156;
          v52[313] = 1;
          v54 = ((__int64 (__fastcall *)(struct IInspectable *, struct IUnknown **))a4->lpVtbl[3].Release)(a4, v163);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          v52[313] = v53;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v54 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v54);
          StringForChar = (struct Js::JavascriptString *)Projection::ProjectionMarshaler::ReadOutSystemGuidType(
                                                           this,
                                                           1,
                                                           (unsigned __int8 *)v163,
                                                           0x10u);
          goto LABEL_32;
      }
      goto LABEL_153;
    }
    v155 = 0;
    Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
    v71 = *(_QWORD *)(v16 + 880);
    v163[0] = (struct IUnknown *)v71;
    LOBYTE(v163[1]) = *(_BYTE *)(v71 + 313);
    v72 = (char)v163[1];
    *(_BYTE *)(v71 + 313) = 1;
    v73 = ((__int64 (__fastcall *)(struct IInspectable *, void **))a4->lpVtbl[2].GetRuntimeClassName)(a4, &v155);
    ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
    *(_BYTE *)(v71 + 313) = v72;
    Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
    if ( v73 < 0 )
      Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v73);
    v51 = *(double *)&v155;
  }
  else
  {
    if ( v160 != 8 )
    {
      switch ( v160 )
      {
        case 0:
          VarFromRuntimeClassName = *(void **)(*(_QWORD *)(v16 + 8) + 1008LL);
          goto LABEL_147;
        case 1:
          v154[0] = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v44 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v44;
          LOBYTE(v163[1]) = *(_BYTE *)(v44 + 313);
          v45 = (char)v163[1];
          *(_BYTE *)(v44 + 313) = 1;
          v46 = ((__int64 (__fastcall *)(struct IInspectable *, bool *))a4->lpVtbl[1].Release)(a4, v154);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v44 + 313) = v45;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v46 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v46);
          v37 = v154[0];
          break;
        case 2:
          *(_WORD *)v154 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v41 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v41;
          LOBYTE(v163[1]) = *(_BYTE *)(v41 + 313);
          v42 = (char)v163[1];
          *(_BYTE *)(v41 + 313) = 1;
          v43 = ((__int64 (__fastcall *)(struct IInspectable *, bool *))a4->lpVtbl[1].GetIids)(a4, v154);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v41 + 313) = v42;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v43 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v43);
          v37 = (unsigned int)*(__int16 *)v154;
          break;
        case 3:
          *(_WORD *)v154 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v38 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v38;
          LOBYTE(v163[1]) = *(_BYTE *)(v38 + 313);
          v39 = (char)v163[1];
          *(_BYTE *)(v38 + 313) = 1;
          v40 = ((__int64 (__fastcall *)(struct IInspectable *, bool *))a4->lpVtbl[1].GetRuntimeClassName)(a4, v154);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v38 + 313) = v39;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v40 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v40);
          v37 = *(unsigned __int16 *)v154;
          break;
        case 4:
          *(_DWORD *)v154 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v34 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v34;
          LOBYTE(v163[1]) = *(_BYTE *)(v34 + 313);
          v35 = (char)v163[1];
          *(_BYTE *)(v34 + 313) = 1;
          v36 = ((__int64 (__fastcall *)(struct IInspectable *, bool *))a4->lpVtbl[1].GetTrustLevel)(a4, v154);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v34 + 313) = v35;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v36 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v36);
          v37 = *(unsigned int *)v154;
          break;
        case 5:
          *(_DWORD *)v154 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v29 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v29;
          LOBYTE(v163[1]) = *(_BYTE *)(v29 + 313);
          v30 = (char)v163[1];
          *(_BYTE *)(v29 + 313) = 1;
          v31 = ((__int64 (__fastcall *)(struct IInspectable *, bool *))a4->lpVtbl[2].QueryInterface)(a4, v154);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v29 + 313) = v30;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v31 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v31);
          StringForChar = (struct Js::JavascriptString *)Js::JavascriptNumber::ToVar(*(unsigned int *)v154, v32);
          goto LABEL_32;
        case 6:
          v155 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v26 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v26;
          LOBYTE(v163[1]) = *(_BYTE *)(v26 + 313);
          v27 = (char)v163[1];
          *(_BYTE *)(v26 + 313) = 1;
          v28 = ((__int64 (__fastcall *)(struct IInspectable *, void **))a4->lpVtbl[2].AddRef)(a4, &v155);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v26 + 313) = v27;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v28 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v28);
          StringForChar = (struct Js::JavascriptString *)Js::JavascriptTypedNumber<__int64>::ToVar(v155, v16);
          goto LABEL_32;
        case 7:
          v155 = 0;
          Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
          v22 = *(_QWORD *)(v16 + 880);
          v163[0] = (struct IUnknown *)v22;
          LOBYTE(v163[1]) = *(_BYTE *)(v22 + 313);
          v23 = (char)v163[1];
          *(_BYTE *)(v22 + 313) = 1;
          v24 = ((__int64 (__fastcall *)(struct IInspectable *, void **))a4->lpVtbl[2].Release)(a4, &v155);
          ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
          *(_BYTE *)(v22 + 313) = v23;
          Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
          if ( v24 < 0 )
            Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v24);
          StringForChar = (struct Js::JavascriptString *)Js::JavascriptTypedNumber<unsigned __int64>::ToVar(v155, v16);
          goto LABEL_32;
        default:
LABEL_153:
          VarFromRuntimeClassName = Projection::ProjectionMarshaler::ReadVarFromRuntimeClassName(
                                      this,
                                      a2,
                                      v163[0],
                                      a4,
                                      v154[5],
                                      v154[4],
                                      0,
                                      *(int *)v154,
                                      0);
          goto LABEL_154;
      }
      VarFromRuntimeClassName = (void *)(v37 | 0x1000000000000LL);
      goto LABEL_147;
    }
    *(_DWORD *)v154 = 0;
    Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(&v157, v16, retaddr);
    v47 = *(_QWORD *)(v16 + 880);
    v163[0] = (struct IUnknown *)v47;
    LOBYTE(v163[1]) = *(_BYTE *)(v47 + 313);
    v48 = (char)v163[1];
    *(_BYTE *)(v47 + 313) = 1;
    v49 = ((__int64 (__fastcall *)(struct IInspectable *, bool *))a4->lpVtbl[2].GetIids)(a4, v154);
    ThreadContext::DisposeOnLeaveScript(*(ThreadContext **)(v16 + 880));
    *(_BYTE *)(v47 + 313) = v48;
    Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(&v157);
    if ( v49 < 0 )
      Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v16, v49);
    v51 = *(float *)v154;
  }
  StringForChar = (struct Js::JavascriptString *)Js::JavascriptNumber::NewWithCheck(v51, v50);
LABEL_32:
  VarFromRuntimeClassName = StringForChar;
LABEL_147:
  Projection::ProjectionContext::GetProjectionWriter(*((Projection::ProjectionContext **)this + 2));
  if ( v154[5] )
    Projection::ProjectionContext::TypeInstanceCreated(
      *((Projection::ProjectionContext **)this + 2),
      (struct IUnknown *)a4);
  if ( !v154[4] && Js::DynamicObject::Is(VarFromRuntimeClassName) && !*(_DWORD *)(*((_QWORD *)this + 2) + 56LL) )
  {
    v151 = Js::DynamicObject::FromVar(VarFromRuntimeClassName);
    v152 = (*(__int64 (__fastcall **)(struct Js::DynamicObject *))(*(_QWORD *)v151 + 424LL))(v151);
    Js::VerifyCatastrophic<int>(v152);
  }
LABEL_154:
  if ( (Microsoft_JScriptEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v150, L"2", v161);
  return VarFromRuntimeClassName;
}

```

## disassembly

```asm
0x180004054  mov     rax, rsp
0x180004057  mov     [rax+20h], r9
0x18000405b  mov     [rax+18h], r8
0x18000405f  mov     [rax+10h], rdx
0x180004063  mov     [rax+8], rcx
0x180004067  push    rbp
0x180004068  push    rbx
0x180004069  push    rsi
0x18000406a  push    rdi
0x18000406b  push    r12
0x18000406d  push    r13
0x18000406f  push    r14
0x180004071  push    r15
0x180004073  lea     rbp, [rax-47h]
0x180004077  sub     rsp, 0E8h
0x18000407e  mov     [rbp+3Fh+var_68], 0FFFFFFFFFFFFFFFEh
0x180004086  mov     rax, cs:__security_cookie
0x18000408d  xor     rax, rsp
0x180004090  mov     [rbp+3Fh+var_50], rax
0x180004094  mov     r13, [rbp+3Fh+arg_0]
0x180004098  mov     r12, [rbp+3Fh+arg_8]
0x18000409c  mov     rax, [rbp+3Fh+arg_10]
0x1800040a0  mov     [rbp+3Fh+var_60], rax
0x1800040a4  mov     r15, [rbp+3Fh+arg_18]
0x1800040a8  mov     al, [rbp+3Fh+arg_20]
0x1800040ab  mov     [rsp+120h+var_D0+5], al
0x1800040af  mov     al, [rbp+3Fh+arg_28]
0x1800040b2  mov     [rsp+120h+var_D0+4], al
0x1800040b6  mov     eax, [rbp+3Fh+arg_30]
0x1800040b9  mov     dword ptr [rsp+120h+var_D0], eax
0x1800040bd  mov     rax, [r13+10h]
0x1800040c1  mov     rbx, [rax+60h]
0x1800040c5  add     rbx, 1EF0h
0x1800040cc  cmp     byte ptr [rbx+10h], 0
0x1800040d0  jnz     short loc_180004100
0x1800040d2  mov     rax, [rbx]
0x1800040d5  mov     rcx, rbx
0x1800040d8  mov     rax, [rax+8]
0x1800040dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040e1  mov     rcx, rax; lpLibFileName
0x1800040e4  xor     edx, edx; hFile
0x1800040e6  mov     r8d, 800h; dwFlags
0x1800040ec  call    cs:__imp_LoadLibraryExW
0x1800040f3  nop     dword ptr [rax+rax+00h]
0x1800040f8  mov     [rbx+8], rax
0x1800040fc  mov     byte ptr [rbx+10h], 1
0x180004100  mov     rax, [rbx]
0x180004103  xor     r8d, r8d
0x180004106  mov     rdx, [r12]
0x18000410a  mov     rcx, rbx
0x18000410d  mov     rax, [rax+28h]
0x180004111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004116  mov     rbx, rax
0x180004119  mov     [rbp+3Fh+var_70], rax
0x18000411d  test    byte ptr cs:Microsoft_JScriptEnableBits, 8
0x180004124  jz      short loc_180004135
0x180004126  mov     r8, rax
0x180004129  lea     rdx, JSCRIPT_PROJECTION_PROPERTYVALUEVARFROMGRCN_START
0x180004130  call    McTemplateU0z_EventWriteTransfer
0x180004135  mov     rcx, [r13+10h]
0x180004139  mov     r14, [rcx+70h]
0x18000413d  lea     rdx, aWindowsFoundat_29; "Windows.Foundation.IReference`1"
0x180004144  mov     rcx, rbx; Str
0x180004147  call    cs:__imp_wcsstr
0x18000414e  nop     dword ptr [rax+rax+00h]
0x180004153  test    rax, rax
0x180004156  jz      short loc_18000415D
0x180004158  cmp     rax, rbx
0x18000415b  jz      short loc_180004185
0x18000415d  lea     rdx, aWindowsFoundat_1; "Windows.Foundation.IReferenceArray`1"
0x180004164  mov     rcx, rbx; Str
0x180004167  call    cs:__imp_wcsstr
0x18000416e  nop     dword ptr [rax+rax+00h]
0x180004173  test    rax, rax
0x180004176  jz      loc_1800058D6
0x18000417c  cmp     rax, rbx
0x18000417f  jnz     loc_1800058D6
0x180004185  mov     [rbp+3Fh+var_78], 0
0x18000418c  mov     rcx, r14; struct Js::ScriptContext *
0x18000418f  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x180004194  mov     r8, [rbp+47h]
0x180004198  mov     rdx, r14
0x18000419b  lea     rcx, [rbp+3Fh+var_B8]
0x18000419f  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1800041a4  nop
0x1800041a5  mov     rdi, [r14+370h]
0x1800041ac  mov     [rsp+120h+var_C8], rdi
0x1800041b1  mov     bl, [rdi+139h]
0x1800041b7  mov     [rsp+120h+var_C0], bl
0x1800041bb  mov     byte ptr [rdi+139h], 1
0x1800041c2  mov     rax, [r15]
0x1800041c5  lea     rdx, [rbp+3Fh+var_78]
0x1800041c9  mov     rcx, r15
0x1800041cc  mov     rax, [rax+30h]
0x1800041d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041d5  mov     esi, eax
0x1800041d7  mov     rcx, [r14+370h]; this
0x1800041de  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1800041e3  nop
0x1800041e4  mov     [rdi+139h], bl
0x1800041ea  lea     rcx, [rbp+3Fh+var_B8]
0x1800041ee  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1800041f3  mov     rcx, r14; struct Js::ScriptContext *
0x1800041f6  test    esi, esi
0x1800041f8  jns     short loc_180004202
0x1800041fa  mov     edx, esi; int
0x1800041fc  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x180004202  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x180004207  mov     [rsp+120h+var_C8], 0
0x180004210  mov     ecx, [rbp+3Fh+var_78]
0x180004213  mov     eax, 401h
0x180004218  cmp     ecx, eax
0x18000421a  jg      loc_180004BC6
0x180004220  jz      loc_180004AFC
0x180004226  cmp     ecx, 8
0x180004229  jg      loc_1800046A7
0x18000422f  jz      loc_18000461F
0x180004235  test    ecx, ecx
0x180004237  jz      loc_18000460F
0x18000423d  sub     ecx, 1
0x180004240  jz      loc_180004586
0x180004246  sub     ecx, 1
0x180004249  jz      loc_18000450B
0x18000424f  sub     ecx, 1
0x180004252  jz      loc_18000448D
0x180004258  sub     ecx, 1
0x18000425b  jz      loc_18000440F
0x180004261  sub     ecx, 1
0x180004264  jz      loc_180004389
0x18000426a  sub     ecx, 1
0x18000426d  jz      loc_180004304
0x180004273  cmp     ecx, 1
0x180004276  jnz     def_180004BE9; jumptable 0000000180004BE9 default case
0x18000427c  mov     [rsp+120h+var_C8], 0
0x180004285  mov     r8, [rbp+47h]
0x180004289  mov     rdx, r14
0x18000428c  lea     rcx, [rbp+3Fh+var_B8]
0x180004290  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x180004295  nop
0x180004296  mov     rdi, [r14+370h]
0x18000429d  mov     [rbp+3Fh+var_60], rdi
0x1800042a1  mov     bl, [rdi+139h]
0x1800042a7  mov     byte ptr [rbp+3Fh+var_60+8], bl
0x1800042aa  mov     byte ptr [rdi+139h], 1
0x1800042b1  mov     rax, [r15]
0x1800042b4  lea     rdx, [rsp+120h+var_C8]
0x1800042b9  mov     rcx, r15
0x1800042bc  mov     rax, [rax+70h]
0x1800042c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042c5  mov     esi, eax
0x1800042c7  mov     rcx, [r14+370h]; this
0x1800042ce  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1800042d3  nop
0x1800042d4  mov     [rdi+139h], bl
0x1800042da  lea     rcx, [rbp+3Fh+var_B8]
0x1800042de  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1800042e3  test    esi, esi
0x1800042e5  jns     short loc_1800042F2
0x1800042e7  mov     edx, esi; int
0x1800042e9  mov     rcx, r14; struct Js::ScriptContext *
0x1800042ec  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1800042f2  mov     rdx, r14
0x1800042f5  mov     rcx, [rsp+120h+var_C8]
0x1800042fa  call    ?ToVar@?$JavascriptTypedNumber@_K@Js@@SAPEAX_KPEAVScriptContext@2@@Z; Js::JavascriptTypedNumber<unsigned __int64>::ToVar(unsigned __int64,Js::ScriptContext *)
0x1800042ff  jmp     loc_180004407
0x180004304  mov     [rsp+120h+var_C8], 0
0x18000430d  mov     r8, [rbp+47h]
0x180004311  mov     rdx, r14
0x180004314  lea     rcx, [rbp+3Fh+var_B8]
0x180004318  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x18000431d  nop
0x18000431e  mov     rdi, [r14+370h]
0x180004325  mov     [rbp+3Fh+var_60], rdi
0x180004329  mov     bl, [rdi+139h]
0x18000432f  mov     byte ptr [rbp+3Fh+var_60+8], bl
0x180004332  mov     byte ptr [rdi+139h], 1
0x180004339  mov     rax, [r15]
0x18000433c  lea     rdx, [rsp+120h+var_C8]
0x180004341  mov     rcx, r15
0x180004344  mov     rax, [rax+68h]
0x180004348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000434d  mov     esi, eax
0x18000434f  mov     rcx, [r14+370h]; this
0x180004356  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x18000435b  nop
0x18000435c  mov     [rdi+139h], bl
0x180004362  lea     rcx, [rbp+3Fh+var_B8]
0x180004366  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x18000436b  test    esi, esi
0x18000436d  jns     short loc_18000437A
0x18000436f  mov     edx, esi; int
0x180004371  mov     rcx, r14; struct Js::ScriptContext *
0x180004374  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x18000437a  mov     rdx, r14
0x18000437d  mov     rcx, [rsp+120h+var_C8]
0x180004382  call    ?ToVar@?$JavascriptTypedNumber@_J@Js@@SAPEAX_JPEAVScriptContext@2@@Z; Js::JavascriptTypedNumber<__int64>::ToVar(__int64,Js::ScriptContext *)
0x180004387  jmp     short loc_180004407
0x180004389  mov     dword ptr [rsp+120h+var_D0], 0
0x180004391  mov     r8, [rbp+47h]
0x180004395  mov     rdx, r14
0x180004398  lea     rcx, [rbp+3Fh+var_B8]
0x18000439c  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1800043a1  nop
0x1800043a2  mov     rdi, [r14+370h]
0x1800043a9  mov     [rbp+3Fh+var_60], rdi
0x1800043ad  mov     bl, [rdi+139h]
0x1800043b3  mov     byte ptr [rbp+3Fh+var_60+8], bl
0x1800043b6  mov     byte ptr [rdi+139h], 1
0x1800043bd  mov     rax, [r15]
0x1800043c0  lea     rdx, [rsp+120h+var_D0]
0x1800043c5  mov     rcx, r15
0x1800043c8  mov     rax, [rax+60h]
0x1800043cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043d1  mov     esi, eax
0x1800043d3  mov     rcx, [r14+370h]; this
0x1800043da  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1800043df  nop
0x1800043e0  mov     [rdi+139h], bl
0x1800043e6  lea     rcx, [rbp+3Fh+var_B8]
0x1800043ea  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1800043ef  test    esi, esi
0x1800043f1  jns     short loc_1800043FE
0x1800043f3  mov     edx, esi; int
0x1800043f5  mov     rcx, r14; struct Js::ScriptContext *
0x1800043f8  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x1800043fe  mov     ecx, dword ptr [rsp+120h+var_D0]; unsigned int
0x180004402  call    ?ToVar@JavascriptNumber@Js@@SAPEAXIPEAVScriptContext@2@@Z; Js::JavascriptNumber::ToVar(uint,Js::ScriptContext *)
0x180004407  mov     rbx, rax
0x18000440a  jmp     loc_1800057FF
0x18000440f  mov     dword ptr [rsp+120h+var_D0], 0
0x180004417  mov     r8, [rbp+47h]
0x18000441b  mov     rdx, r14
0x18000441e  lea     rcx, [rbp+3Fh+var_B8]
0x180004422  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x180004427  nop
0x180004428  mov     rdi, [r14+370h]
0x18000442f  mov     [rbp+3Fh+var_60], rdi
0x180004433  mov     bl, [rdi+139h]
0x180004439  mov     byte ptr [rbp+3Fh+var_60+8], bl
0x18000443c  mov     byte ptr [rdi+139h], 1
0x180004443  mov     rax, [r15]
0x180004446  lea     rdx, [rsp+120h+var_D0]
0x18000444b  mov     rcx, r15
0x18000444e  mov     rax, [rax+58h]
0x180004452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004457  mov     esi, eax
0x180004459  mov     rcx, [r14+370h]; this
0x180004460  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x180004465  nop
0x180004466  mov     [rdi+139h], bl
0x18000446c  lea     rcx, [rbp+3Fh+var_B8]
0x180004470  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x180004475  test    esi, esi
0x180004477  jns     short loc_180004484
0x180004479  mov     edx, esi; int
0x18000447b  mov     rcx, r14; struct Js::ScriptContext *
0x18000447e  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x180004484  mov     ebx, dword ptr [rsp+120h+var_D0]
0x180004488  jmp     loc_1800045FD
0x18000448d  xor     eax, eax
0x18000448f  mov     word ptr [rsp+120h+var_D0], ax
0x180004494  mov     r8, [rbp+47h]
0x180004498  mov     rdx, r14
0x18000449b  lea     rcx, [rbp+3Fh+var_B8]
0x18000449f  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1800044a4  nop
0x1800044a5  mov     rdi, [r14+370h]
0x1800044ac  mov     [rbp+3Fh+var_60], rdi
0x1800044b0  mov     bl, [rdi+139h]
0x1800044b6  mov     byte ptr [rbp+3Fh+var_60+8], bl
0x1800044b9  mov     byte ptr [rdi+139h], 1
0x1800044c0  mov     rax, [r15]
0x1800044c3  lea     rdx, [rsp+120h+var_D0]
0x1800044c8  mov     rcx, r15
0x1800044cb  mov     rax, [rax+50h]
0x1800044cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d4  mov     esi, eax
0x1800044d6  mov     rcx, [r14+370h]; this
0x1800044dd  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1800044e2  nop
0x1800044e3  mov     [rdi+139h], bl
0x1800044e9  lea     rcx, [rbp+3Fh+var_B8]
0x1800044ed  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1800044f2  test    esi, esi
0x1800044f4  jns     short loc_180004501
0x1800044f6  mov     edx, esi; int
0x1800044f8  mov     rcx, r14; struct Js::ScriptContext *
0x1800044fb  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
0x180004501  movzx   ebx, word ptr [rsp+120h+var_D0]
0x180004506  jmp     loc_1800045FD
0x18000450b  xor     eax, eax
0x18000450d  mov     word ptr [rsp+120h+var_D0], ax
0x180004512  mov     r8, [rbp+47h]
0x180004516  mov     rdx, r14
0x180004519  lea     rcx, [rbp+3Fh+var_B8]
0x18000451d  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x180004522  nop
0x180004523  mov     rdi, [r14+370h]
0x18000452a  mov     [rbp+3Fh+var_60], rdi
0x18000452e  mov     bl, [rdi+139h]
  ... truncated ...
```
