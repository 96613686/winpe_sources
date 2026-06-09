# ActivateClassicITA(IMFPMPHost *,ushort const *,IStream *,_GUID const &,void * *)

- ea: `0x18019f298`
- end: `0x1801a04f6`
- name: `?ActivateClassicITA@@YAJPEAUIMFPMPHost@@PEBGPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `4702`
- prototype: `__int64 __fastcall(struct IMFPMPHost *, const unsigned __int16 *, struct IStream *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1802901c4`

## callees

- `0x18000320c`
- `0x18000329c`
- `0x1800053d0`
- `0x180006c50`
- `0x18001e590`
- `0x18019f298`
- `0x18029dde0`
- `0x18029ddf8`
- `0x18029e240`
- `0x18029ec94`
- `0x1802ea010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f406`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f55d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f6bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f801`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f96c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fac4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fc0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fd55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fec0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0018`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a01ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a02f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0453`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f406`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f55d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f6bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f801`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019f96c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fac4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fc0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fd55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019fec0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0018`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a01ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a02f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a0453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f39d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f4d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f77c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f8e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fa3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fa5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fb88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fcd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fcec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ff93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ffaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a03ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a03ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f39d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f4d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f77c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f8e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019f903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fa3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fa5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fb88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fcd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fcec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019fe57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ff93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019ffaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a0290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a03ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a03ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f38d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f4e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f642`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f788`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f8f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fa4b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fb94`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fcdc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fe47`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019ff9f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a0133`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a0280`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a03da`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f38d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f4e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f642`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f788`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019f8f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fa4b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fb94`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fcdc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019fe47`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18019ff9f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a0133`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a0280`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801a03da`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18019fb0e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18019fb0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019ff19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019ff19`
- `MFPlat!MFSerializeAttributesToStream` at `0x18019fc56`
- `MFPlat!MFSerializeAttributesToStream` at `0x18019fc56`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f3b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f47f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f50a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f5dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f668`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f723`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f7ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f88e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f919`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f9e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fa71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fb2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fbba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fc77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fd02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fde2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fe6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ff3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ffc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a00ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0159`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a021b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a02a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0375`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0400`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f3b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f47f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f50a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f5dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f668`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f723`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f7ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f88e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f919`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019f9e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fa71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fb2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fbba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fc77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fd02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fde2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019fe6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ff3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ffc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a00ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0159`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a021b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a02a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0375`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0400`
- `MFPlat!MFCreateAttributes` at `0x18019f311`
- `MFPlat!MFCreateAttributes` at `0x18019f311`

## pseudocode

```c
__int64 __fastcall ActivateClassicITA(
        struct IMFPMPHost *a1,
        const unsigned __int16 *a2,
        struct IStream *a3,
        const struct _GUID *a4,
        void **a5)
{
  void *v9; // r13
  __int64 v10; // rcx
  HRESULT Instance; // ebx
  CallStackTracing *v12; // rsi
  CallStackTracing *v13; // rax
  CallStackContext *v14; // r14
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  CallStackTracing *v22; // rsi
  CallStackTracing *v23; // rax
  CallStackContext *v24; // r14
  DWORD v25; // r15d
  CallStackContext *v26; // rax
  CallStackTracing *v27; // rcx
  CallStackTracing *v28; // rax
  __int64 v29; // rax
  struct IStreamVtbl *lpVtbl; // rax
  __int64 v31; // rcx
  CallStackTracing *v32; // rsi
  CallStackTracing *v33; // rax
  CallStackContext *v34; // r14
  DWORD v35; // r15d
  CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  CallStackTracing *v41; // rsi
  CallStackTracing *v42; // rax
  CallStackContext *v43; // r14
  DWORD v44; // r15d
  CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  CallStackTracing *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rcx
  CallStackTracing *v50; // rsi
  CallStackTracing *v51; // rax
  CallStackContext *v52; // r14
  DWORD v53; // r15d
  CallStackContext *v54; // rax
  CallStackTracing *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rcx
  CallStackTracing *v59; // rsi
  CallStackTracing *v60; // rax
  CallStackContext *v61; // r14
  DWORD v62; // r15d
  CallStackContext *v63; // rax
  CallStackTracing *v64; // rcx
  CallStackTracing *v65; // rax
  __int64 v66; // rax
  __int64 v67; // rcx
  CallStackTracing *v68; // rsi
  CallStackTracing *v69; // rax
  CallStackContext *v70; // r14
  DWORD v71; // r15d
  CallStackContext *v72; // rax
  CallStackTracing *v73; // rcx
  CallStackTracing *v74; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  CallStackTracing *v77; // rsi
  CallStackTracing *v78; // rax
  CallStackContext *v79; // r14
  DWORD v80; // r15d
  CallStackContext *v81; // rax
  CallStackTracing *v82; // rcx
  CallStackTracing *v83; // rax
  __int64 v84; // rax
  __int64 v85; // rcx
  CallStackTracing *v86; // rsi
  CallStackTracing *v87; // rax
  CallStackContext *v88; // r14
  DWORD v89; // r15d
  CallStackContext *v90; // rax
  CallStackTracing *v91; // rcx
  CallStackTracing *v92; // rax
  __int64 v93; // rax
  __int64 v94; // rcx
  CallStackTracing *v95; // rsi
  CallStackTracing *v96; // rax
  CallStackContext *v97; // r14
  DWORD v98; // r15d
  CallStackContext *v99; // rax
  CallStackTracing *v100; // rcx
  CallStackTracing *v101; // rax
  __int64 v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rcx
  CallStackTracing *v105; // rsi
  CallStackTracing *v106; // rax
  CallStackContext *v107; // r14
  DWORD v108; // r15d
  CallStackContext *v109; // rax
  CallStackTracing *v110; // rcx
  CallStackTracing *v111; // rax
  __int64 v112; // rax
  __int64 v113; // rcx
  CallStackTracing *v114; // rsi
  CallStackTracing *v115; // rax
  CallStackContext *v116; // r14
  DWORD v117; // r15d
  CallStackContext *v118; // rax
  CallStackTracing *v119; // rcx
  CallStackTracing *v120; // rax
  __int64 v121; // rax
  __int64 v122; // rcx
  CallStackTracing *v123; // rsi
  CallStackTracing *v124; // rax
  CallStackContext *v125; // r14
  DWORD v126; // r15d
  CallStackContext *v127; // rax
  CallStackTracing *v128; // rcx
  CallStackTracing *v129; // rax
  __int64 v130; // rax
  char v132[8]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v133; // [rsp+38h] [rbp-89h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v135; // [rsp+48h] [rbp-79h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-71h] BYREF
  LPVOID ppv[3]; // [rsp+58h] [rbp-69h] BYREF
  _BYTE v138[16]; // [rsp+70h] [rbp-51h] BYREF
  size_t Size; // [rsp+80h] [rbp-41h]

  v135 = 0;
  v9 = 0;
  memset_0(v138, 0, 0x50u);
  ppv[0] = 0;
  ppMFAttributes = 0;
  ppstm = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v132, "ActivateClassicITA", 5337);
  Instance = MFCreateAttributes(&ppMFAttributes, 3u);
  if ( Instance < 0 )
  {
    v12 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = (CallStackTracing *)&qword_18033DBA0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = (CallStackTracing *)((char *)v12 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v12 + 3));
      if ( Value )
      {
        v14 = Value;
      }
      else if ( !GetLastError() )
      {
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        v19 = (**(__int64 (__fastcall ***)(CallStackTracing *))v17)(v17);
        if ( v19 )
          v14 = (CallStackContext *)v19;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v14 + 499) != Instance )
        CallStackContext::TraceFailure(v14, "ActivateClassicITA", 5337, Instance);
    }
    if ( g_wppLevels )
    {
      v20 = 518;
LABEL_279:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
      goto LABEL_280;
    }
    goto LABEL_280;
  }
  Instance = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, const unsigned __int16 *))ppMFAttributes->lpVtbl->SetString)(
               ppMFAttributes,
               MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATABLE_CLASS_ID,
               a2);
  if ( Instance >= 0 )
  {
    if ( a3 )
    {
      lpVtbl = a3->lpVtbl;
      v133 = 0;
      Instance = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64))lpVtbl->Stat)(a3, v138, 3);
      if ( Instance < 0 )
      {
        v32 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v31);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = (CallStackTracing *)((char *)v32 + 208);
          v35 = GetLastError();
          v36 = (CallStackContext *)TlsGetValue(*((_DWORD *)v32 + 3));
          if ( v36 )
          {
            v34 = v36;
          }
          else if ( !GetLastError() )
          {
            v37 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v38;
              if ( v38
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
              {
                v37 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v37 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v39 = (**(__int64 (__fastcall ***)(CallStackTracing *))v37)(v37);
            if ( v39 )
              v34 = (CallStackContext *)v39;
          }
          SetLastError(v35);
          if ( *((_DWORD *)v34 + 499) != Instance )
            CallStackContext::TraceFailure(v34, "ActivateClassicITA", 5344, Instance);
        }
        if ( g_wppLevels )
        {
          v20 = 520;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
      v9 = operator new((unsigned int)Size);
      if ( !v9 )
      {
        v41 = CallStackTracing::s_wpInstance;
        Instance = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v40);
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v43 = (CallStackTracing *)((char *)v41 + 208);
          v44 = GetLastError();
          v45 = (CallStackContext *)TlsGetValue(*((_DWORD *)v41 + 3));
          if ( v45 )
          {
            v43 = v45;
          }
          else if ( !GetLastError() )
          {
            v46 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v47;
              if ( v47
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
              {
                v46 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v46 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v48 = (**(__int64 (__fastcall ***)(CallStackTracing *))v46)(v46);
            if ( v48 )
              v43 = (CallStackContext *)v48;
          }
          SetLastError(v44);
          if ( *((_DWORD *)v43 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v43, "ActivateClassicITA", 5348, -2147024882);
        }
        if ( g_wppLevels )
        {
          v20 = 521;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
      ((void (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a3->lpVtbl->Seek)(a3, v133, 0, 0);
      Instance = ((__int64 (__fastcall *)(struct IStream *, void *, _QWORD, unsigned int *))a3->lpVtbl->Read)(
                   a3,
                   v9,
                   (unsigned int)Size,
                   &v135);
      if ( Instance < 0 )
      {
        v50 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v49);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v50 + 8) )
        {
          v52 = (CallStackTracing *)((char *)v50 + 208);
          v53 = GetLastError();
          v54 = (CallStackContext *)TlsGetValue(*((_DWORD *)v50 + 3));
          if ( v54 )
          {
            v52 = v54;
          }
          else if ( !GetLastError() )
          {
            v55 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v56;
              if ( v56
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
              {
                v55 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v55 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v57 = (**(__int64 (__fastcall ***)(CallStackTracing *))v55)(v55);
            if ( v57 )
              v52 = (CallStackContext *)v57;
          }
          SetLastError(v53);
          if ( *((_DWORD *)v52 + 499) != Instance )
            CallStackContext::TraceFailure(v52, "ActivateClassicITA", 5351, Instance);
        }
        if ( g_wppLevels )
        {
          v20 = 522;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
      Instance = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *, _QWORD))ppMFAttributes->lpVtbl->SetBlob)(
                   ppMFAttributes,
                   MF_ENCRYPTEDMEDIAEXTENSIONS_INITIALIZATION_DATA,
                   v9,
                   v135);
      if ( Instance < 0 )
      {
        v59 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v58);
          CallStackTracing::s_wpInstance = v60;
          if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
          {
            v59 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v59 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v59 + 8) )
        {
          v61 = (CallStackTracing *)((char *)v59 + 208);
          v62 = GetLastError();
          v63 = (CallStackContext *)TlsGetValue(*((_DWORD *)v59 + 3));
          if ( v63 )
          {
            v61 = v63;
          }
          else if ( !GetLastError() )
          {
            v64 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v65;
              if ( v65
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
              {
                v64 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v64 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v66 = (**(__int64 (__fastcall ***)(CallStackTracing *))v64)(v64);
            if ( v66 )
              v61 = (CallStackContext *)v66;
          }
          SetLastError(v62);
          if ( *((_DWORD *)v61 + 499) != Instance )
            CallStackContext::TraceFailure(v61, "ActivateClassicITA", 5352, Instance);
        }
        if ( g_wppLevels )
        {
          v20 = 523;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
    }
    Instance = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( Instance < 0 )
    {
      v68 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v67);
        CallStackTracing::s_wpInstance = v69;
        if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
        {
          v68 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v68 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      if ( *((_BYTE *)v68 + 8) )
      {
        v70 = (CallStackTracing *)((char *)v68 + 208);
        v71 = GetLastError();
        v72 = (CallStackContext *)TlsGetValue(*((_DWORD *)v68 + 3));
        if ( v72 )
        {
          v70 = v72;
        }
        else if ( !GetLastError() )
        {
          v73 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v74;
            if ( v74 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
            {
              v73 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v73 = (CallStackTracing *)&qword_18033DBA0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
            }
          }
          v75 = (**(__int64 (__fastcall ***)(CallStackTracing *))v73)(v73);
          if ( v75 )
            v70 = (CallStackContext *)v75;
        }
        SetLastError(v71);
        if ( *((_DWORD *)v70 + 499) != Instance )
          CallStackContext::TraceFailure(v70, "ActivateClassicITA", 5356, Instance);
      }
      if ( g_wppLevels )
      {
        v20 = 524;
        goto LABEL_279;
      }
      goto LABEL_280;
    }
    Instance = MFSerializeAttributesToStream(ppMFAttributes, 0, ppstm);
    if ( Instance < 0 )
    {
      v77 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v76);
        CallStackTracing::s_wpInstance = v78;
        if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
        {
          v77 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v77 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      if ( *((_BYTE *)v77 + 8) )
      {
        v79 = (CallStackTracing *)((char *)v77 + 208);
        v80 = GetLastError();
        v81 = (CallStackContext *)TlsGetValue(*((_DWORD *)v77 + 3));
        if ( v81 )
        {
          v79 = v81;
        }
        else if ( !GetLastError() )
        {
          v82 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v83 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v83;
            if ( v83 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v83 + 8LL))(v83, 2032) )
            {
              v82 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v82 = (CallStackTracing *)&qword_18033DBA0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
            }
          }
          v84 = (**(__int64 (__fastcall ***)(CallStackTracing *))v82)(v82);
          if ( v84 )
            v79 = (CallStackContext *)v84;
        }
        SetLastError(v80);
        if ( *((_DWORD *)v79 + 499) != Instance )
          CallStackContext::TraceFailure(v79, "ActivateClassicITA", 5357, Instance);
      }
      if ( g_wppLevels )
      {
        v20 = 525;
        goto LABEL_279;
      }
      goto LABEL_280;
    }
    if ( a1 )
    {
      Instance = ((__int64 (__fastcall *)(struct IMFPMPHost *, const IID *, LPSTREAM, GUID *, LPVOID *))a1->lpVtbl->CreateObjectByCLSID)(
                   a1,
                   &MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATE,
                   ppstm,
                   &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67,
                   ppv);
      if ( Instance < 0 )
      {
        v86 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v85);
          CallStackTracing::s_wpInstance = v87;
          if ( v87 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(v87, 2032) )
          {
            v86 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v86 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v86 + 8) )
        {
          v88 = (CallStackTracing *)((char *)v86 + 208);
          v89 = GetLastError();
          v90 = (CallStackContext *)TlsGetValue(*((_DWORD *)v86 + 3));
          if ( v90 )
          {
            v88 = v90;
          }
          else if ( !GetLastError() )
          {
            v91 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v92;
              if ( v92
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v92 + 8LL))(v92, 2032) )
              {
                v91 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v91 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v93 = (**(__int64 (__fastcall ***)(CallStackTracing *))v91)(v91);
            if ( v93 )
              v88 = (CallStackContext *)v93;
          }
          SetLastError(v89);
          if ( *((_DWORD *)v88 + 499) != Instance )
            CallStackContext::TraceFailure(v88, "ActivateClassicITA", 5363, Instance);
        }
        if ( g_wppLevels )
        {
          v20 = 526;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
LABEL_258:
      Instance = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, void **))(*(_QWORD *)ppv[0] + 264LL))(
                   ppv[0],
                   a4,
                   a5);
      if ( Instance < 0 )
      {
        v123 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v124 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v122);
          CallStackTracing::s_wpInstance = v124;
          if ( v124 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v124 + 8LL))(v124, 2032) )
          {
            v123 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v123 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v123 + 8) )
        {
          v125 = (CallStackTracing *)((char *)v123 + 208);
          v126 = GetLastError();
          v127 = (CallStackContext *)TlsGetValue(*((_DWORD *)v123 + 3));
          if ( v127 )
          {
            v125 = v127;
          }
          else if ( !GetLastError() )
          {
            v128 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v129 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v129;
              if ( v129
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v129 + 8LL))(v129, 2032) )
              {
                v128 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v128 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v130 = (**(__int64 (__fastcall ***)(CallStackTracing *))v128)(v128);
            if ( v130 )
              v125 = (CallStackContext *)v130;
          }
          SetLastError(v126);
          if ( *((_DWORD *)v125 + 499) != Instance )
            CallStackContext::TraceFailure(v125, "ActivateClassicITA", 5381, Instance);
        }
        if ( g_wppLevels )
        {
          v20 = 530;
          goto LABEL_279;
        }
      }
      goto LABEL_280;
    }
    v133 = 0;
    Instance = CoCreateInstance(
                 &MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATE,
                 0,
                 1u,
                 &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67,
                 ppv);
    if ( Instance >= 0 )
    {
      ppv[1] = 0;
      ((void (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
      Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv[0])(ppv[0], &IID_IPersistStream, &v133);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, LPSTREAM))(*(_QWORD *)v133 + 40LL))(v133, ppstm);
        if ( Instance >= 0 )
        {
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v133);
          goto LABEL_258;
        }
        v114 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v115 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v113);
          CallStackTracing::s_wpInstance = v115;
          if ( v115 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v115 + 8LL))(v115, 2032) )
          {
            v114 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v114 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v114 + 8) )
        {
          v116 = (CallStackTracing *)((char *)v114 + 208);
          v117 = GetLastError();
          v118 = (CallStackContext *)TlsGetValue(*((_DWORD *)v114 + 3));
          if ( v118 )
          {
            v116 = v118;
          }
          else if ( !GetLastError() )
          {
            v119 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v120 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v120;
              if ( v120
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v120 + 8LL))(v120, 2032) )
              {
                v119 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v119 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v121 = (**(__int64 (__fastcall ***)(CallStackTracing *))v119)(v119);
            if ( v121 )
              v116 = (CallStackContext *)v121;
          }
          SetLastError(v117);
          if ( *((_DWORD *)v116 + 499) != Instance )
            CallStackContext::TraceFailure(v116, "ActivateClassicITA", 5377, Instance);
        }
        if ( !g_wppLevels )
        {
LABEL_214:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v133);
          goto LABEL_280;
        }
        v103 = 529;
      }
      else
      {
        v105 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v106 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v104);
          CallStackTracing::s_wpInstance = v106;
          if ( v106 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v106 + 8LL))(v106, 2032) )
          {
            v105 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v105 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v105 + 8) )
        {
          v107 = (CallStackTracing *)((char *)v105 + 208);
          v108 = GetLastError();
          v109 = (CallStackContext *)TlsGetValue(*((_DWORD *)v105 + 3));
          if ( v109 )
          {
            v107 = v109;
          }
          else if ( !GetLastError() )
          {
            v110 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v111 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v111;
              if ( v111
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v111 + 8LL))(v111, 2032) )
              {
                v110 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v110 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v112 = (**(__int64 (__fastcall ***)(CallStackTracing *))v110)(v110);
            if ( v112 )
              v107 = (CallStackContext *)v112;
          }
          SetLastError(v108);
          if ( *((_DWORD *)v107 + 499) != Instance )
            CallStackContext::TraceFailure(v107, "ActivateClassicITA", 5376, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_214;
        v103 = 528;
      }
    }
    else
    {
      v95 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v96 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v94);
        CallStackTracing::s_wpInstance = v96;
        if ( v96 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v96 + 8LL))(v96, 2032) )
        {
          v95 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v95 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      if ( *((_BYTE *)v95 + 8) )
      {
        v97 = (CallStackTracing *)((char *)v95 + 208);
        v98 = GetLastError();
        v99 = (CallStackContext *)TlsGetValue(*((_DWORD *)v95 + 3));
        if ( v99 )
        {
          v97 = v99;
        }
        else if ( !GetLastError() )
        {
          v100 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v101 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v101;
            if ( v101
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v101 + 8LL))(v101, 2032) )
            {
              v100 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v100 = (CallStackTracing *)&qword_18033DBA0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
            }
          }
          v102 = (**(__int64 (__fastcall ***)(CallStackTracing *))v100)(v100);
          if ( v102 )
            v97 = (CallStackContext *)v102;
        }
        SetLastError(v98);
        if ( *((_DWORD *)v97 + 499) != Instance )
          CallStackContext::TraceFailure(v97, "ActivateClassicITA", 5369, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_214;
      v103 = 527;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v103, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
    goto LABEL_214;
  }
  v22 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v21);
    CallStackTracing::s_wpInstance = v23;
    if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
    {
      v22 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v22 = (CallStackTracing *)&qword_18033DBA0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
    }
  }
  if ( *((_BYTE *)v22 + 8) )
  {
    v24 = (CallStackTracing *)((char *)v22 + 208);
    v25 = GetLastError();
    v26 = (CallStackContext *)TlsGetValue(*((_DWORD *)v22 + 3));
    if ( v26 )
    {
      v24 = v26;
    }
    else if ( !GetLastError() )
    {
      v27 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      v29 = (**(__int64 (__fastcall ***)(CallStackTracing *))v27)(v27);
      if ( v29 )
        v24 = (CallStackContext *)v29;
    }
    SetLastError(v25);
    if ( *((_DWORD *)v24 + 499) != Instance )
      CallStackContext::TraceFailure(v24, "ActivateClassicITA", 5338, Instance);
  }
  if ( g_wppLevels )
  {
    v20 = 519;
    goto LABEL_279;
  }
LABEL_280:
  operator delete(v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v132);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppstm);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFAttributes);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18019f298  push    rbp
0x18019f29a  push    rbx
0x18019f29b  push    rsi
0x18019f29c  push    rdi
0x18019f29d  push    r12
0x18019f29f  push    r13
0x18019f2a1  push    r14
0x18019f2a3  push    r15
0x18019f2a5  lea     rbp, [rsp-17h]
0x18019f2aa  sub     rsp, 0D8h
0x18019f2b1  mov     rax, cs:__security_cookie
0x18019f2b8  xor     rax, rsp
0x18019f2bb  mov     [rbp+4Fh+var_50], rax
0x18019f2bf  mov     r12, [rbp+4Fh+arg_20]
0x18019f2c3  xor     ebx, ebx
0x18019f2c5  mov     rdi, r8
0x18019f2c8  mov     [rbp+4Fh+var_C8], ebx
0x18019f2cb  mov     r14, rdx
0x18019f2ce  mov     rsi, rcx
0x18019f2d1  xor     edx, edx; Val
0x18019f2d3  lea     rcx, [rbp+4Fh+var_A0]; void *
0x18019f2d7  lea     r8d, [rbx+50h]; Size
0x18019f2db  mov     r15, r9
0x18019f2de  mov     r13d, ebx
0x18019f2e1  call    memset_0
0x18019f2e6  mov     r8d, 14D9h; int
0x18019f2ec  mov     [rbp+4Fh+var_B8], rbx
0x18019f2f0  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18019f2f7  mov     [rbp+4Fh+ppMFAttributes], rbx
0x18019f2fb  lea     rcx, [rsp+110h+var_E0]; this
0x18019f300  mov     [rsp+110h+ppstm], rbx
0x18019f305  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18019f30a  lea     edx, [rbx+3]; cInitialSize
0x18019f30d  lea     rcx, [rbp+4Fh+ppMFAttributes]; ppMFAttributes
0x18019f311  call    cs:__imp_MFCreateAttributes
0x18019f317  mov     ebx, eax
0x18019f319  test    eax, eax
0x18019f31b  jns     loc_18019F444
0x18019f321  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f328  mov     edi, 7F0h
0x18019f32d  test    rsi, rsi
0x18019f330  jnz     short loc_18019F370
0x18019f332  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f338  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f33f  mov     rcx, rax
0x18019f342  test    rax, rax
0x18019f345  jz      short loc_18019F362
0x18019f347  mov     rax, [rax]
0x18019f34a  mov     edx, edi
0x18019f34c  mov     rax, [rax+8]
0x18019f350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f355  test    eax, eax
0x18019f357  jz      short loc_18019F362
0x18019f359  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f360  jmp     short loc_18019F370
0x18019f362  lea     rsi, qword_18033DBA0
0x18019f369  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f370  cmp     [rsi+8], r13b
0x18019f374  jz      loc_18019F42D
0x18019f37a  lea     r14, [rsi+0D0h]
0x18019f381  call    cs:__imp_GetLastError
0x18019f387  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18019f38a  mov     r15d, eax
0x18019f38d  call    cs:__imp_TlsGetValue
0x18019f393  test    rax, rax
0x18019f396  jz      short loc_18019F39D
0x18019f398  mov     r14, rax
0x18019f39b  jmp     short loc_18019F403
0x18019f39d  call    cs:__imp_GetLastError
0x18019f3a3  test    eax, eax
0x18019f3a5  jnz     short loc_18019F403
0x18019f3a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f3ae  test    rcx, rcx
0x18019f3b1  jnz     short loc_18019F3F1
0x18019f3b3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f3b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f3c0  mov     rcx, rax
0x18019f3c3  test    rax, rax
0x18019f3c6  jz      short loc_18019F3E3
0x18019f3c8  mov     rax, [rax]
0x18019f3cb  mov     edx, edi
0x18019f3cd  mov     rax, [rax+8]
0x18019f3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f3d6  test    eax, eax
0x18019f3d8  jz      short loc_18019F3E3
0x18019f3da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f3e1  jmp     short loc_18019F3F1
0x18019f3e3  lea     rcx, qword_18033DBA0
0x18019f3ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f3f1  mov     rax, [rcx]
0x18019f3f4  mov     rax, [rax]
0x18019f3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f3fc  test    rax, rax
0x18019f3ff  cmovnz  r14, rax
0x18019f403  mov     ecx, r15d; dwErrCode
0x18019f406  call    cs:__imp_SetLastError
0x18019f40c  cmp     [r14+7CCh], ebx
0x18019f413  jz      short loc_18019F42D
0x18019f415  mov     r9d, ebx; int
0x18019f418  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18019f41f  mov     r8d, 14D9h; int
0x18019f425  mov     rcx, r14; this
0x18019f428  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019f42d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019f434  jb      loc_1801A04A6
0x18019f43a  mov     edx, 206h
0x18019f43f  jmp     loc_1801A0488
0x18019f444  mov     rcx, [rbp+4Fh+ppMFAttributes]
0x18019f448  lea     rdx, MF_ENCRYPTEDMEDIAEXTENSIONS_ACTIVATABLE_CLASS_ID
0x18019f44f  mov     r8, r14
0x18019f452  mov     rax, [rcx]
0x18019f455  mov     rax, [rax+0C8h]
0x18019f45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f461  xor     r14d, r14d
0x18019f464  mov     ebx, eax
0x18019f466  test    eax, eax
0x18019f468  jns     loc_18019F59B
0x18019f46e  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f475  mov     edi, 7F0h
0x18019f47a  test    rsi, rsi
0x18019f47d  jnz     short loc_18019F4BD
0x18019f47f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f485  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f48c  mov     rcx, rax
0x18019f48f  test    rax, rax
0x18019f492  jz      short loc_18019F4AF
0x18019f494  mov     rax, [rax]
0x18019f497  mov     edx, edi
0x18019f499  mov     rax, [rax+8]
0x18019f49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f4a2  test    eax, eax
0x18019f4a4  jz      short loc_18019F4AF
0x18019f4a6  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f4ad  jmp     short loc_18019F4BD
0x18019f4af  lea     rsi, qword_18033DBA0
0x18019f4b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f4bd  cmp     [rsi+8], r14b
0x18019f4c1  jz      loc_18019F584
0x18019f4c7  lea     r14, [rsi+0D0h]
0x18019f4ce  cmp     [rsi+8], r13b
0x18019f4d2  jz      loc_18019F563
0x18019f4d8  call    cs:__imp_GetLastError
0x18019f4de  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18019f4e1  mov     r15d, eax
0x18019f4e4  call    cs:__imp_TlsGetValue
0x18019f4ea  test    rax, rax
0x18019f4ed  jz      short loc_18019F4F4
0x18019f4ef  mov     r14, rax
0x18019f4f2  jmp     short loc_18019F55A
0x18019f4f4  call    cs:__imp_GetLastError
0x18019f4fa  test    eax, eax
0x18019f4fc  jnz     short loc_18019F55A
0x18019f4fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f505  test    rcx, rcx
0x18019f508  jnz     short loc_18019F548
0x18019f50a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f510  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f517  mov     rcx, rax
0x18019f51a  test    rax, rax
0x18019f51d  jz      short loc_18019F53A
0x18019f51f  mov     rax, [rax]
0x18019f522  mov     edx, edi
0x18019f524  mov     rax, [rax+8]
0x18019f528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f52d  test    eax, eax
0x18019f52f  jz      short loc_18019F53A
0x18019f531  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f538  jmp     short loc_18019F548
0x18019f53a  lea     rcx, qword_18033DBA0
0x18019f541  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f548  mov     rax, [rcx]
0x18019f54b  mov     rax, [rax]
0x18019f54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f553  test    rax, rax
0x18019f556  cmovnz  r14, rax
0x18019f55a  mov     ecx, r15d; dwErrCode
0x18019f55d  call    cs:__imp_SetLastError
0x18019f563  cmp     [r14+7CCh], ebx
0x18019f56a  jz      short loc_18019F584
0x18019f56c  mov     r9d, ebx; int
0x18019f56f  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18019f576  mov     r8d, 14DAh; int
0x18019f57c  mov     rcx, r14; this
0x18019f57f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019f584  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019f58b  jb      loc_1801A04A6
0x18019f591  mov     edx, 207h
0x18019f596  jmp     loc_1801A0488
0x18019f59b  test    rdi, rdi
0x18019f59e  jz      loc_18019FB02
0x18019f5a4  mov     rax, [rdi]
0x18019f5a7  lea     rdx, [rbp+4Fh+var_A0]
0x18019f5ab  mov     r8d, 3
0x18019f5b1  mov     [rsp+110h+var_D8], r14
0x18019f5b6  mov     rcx, rdi
0x18019f5b9  mov     rax, [rax+60h]
0x18019f5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f5c2  mov     ebx, eax
0x18019f5c4  test    eax, eax
0x18019f5c6  jns     loc_18019F6F9
0x18019f5cc  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f5d3  mov     edi, 7F0h
0x18019f5d8  test    rsi, rsi
0x18019f5db  jnz     short loc_18019F61B
0x18019f5dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f5e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f5ea  mov     rcx, rax
0x18019f5ed  test    rax, rax
0x18019f5f0  jz      short loc_18019F60D
0x18019f5f2  mov     rax, [rax]
0x18019f5f5  mov     edx, edi
0x18019f5f7  mov     rax, [rax+8]
0x18019f5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f600  test    eax, eax
0x18019f602  jz      short loc_18019F60D
0x18019f604  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f60b  jmp     short loc_18019F61B
0x18019f60d  lea     rsi, qword_18033DBA0
0x18019f614  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f61b  cmp     [rsi+8], r14b
0x18019f61f  jz      loc_18019F6E2
0x18019f625  lea     r14, [rsi+0D0h]
0x18019f62c  cmp     [rsi+8], r13b
0x18019f630  jz      loc_18019F6C1
0x18019f636  call    cs:__imp_GetLastError
0x18019f63c  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18019f63f  mov     r15d, eax
0x18019f642  call    cs:__imp_TlsGetValue
0x18019f648  test    rax, rax
0x18019f64b  jz      short loc_18019F652
0x18019f64d  mov     r14, rax
0x18019f650  jmp     short loc_18019F6B8
0x18019f652  call    cs:__imp_GetLastError
0x18019f658  test    eax, eax
0x18019f65a  jnz     short loc_18019F6B8
0x18019f65c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f663  test    rcx, rcx
0x18019f666  jnz     short loc_18019F6A6
0x18019f668  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f66e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f675  mov     rcx, rax
0x18019f678  test    rax, rax
0x18019f67b  jz      short loc_18019F698
0x18019f67d  mov     rax, [rax]
0x18019f680  mov     edx, edi
0x18019f682  mov     rax, [rax+8]
0x18019f686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f68b  test    eax, eax
0x18019f68d  jz      short loc_18019F698
0x18019f68f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f696  jmp     short loc_18019F6A6
0x18019f698  lea     rcx, qword_18033DBA0
0x18019f69f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f6a6  mov     rax, [rcx]
0x18019f6a9  mov     rax, [rax]
0x18019f6ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f6b1  test    rax, rax
0x18019f6b4  cmovnz  r14, rax
0x18019f6b8  mov     ecx, r15d; dwErrCode
0x18019f6bb  call    cs:__imp_SetLastError
0x18019f6c1  cmp     [r14+7CCh], ebx
0x18019f6c8  jz      short loc_18019F6E2
0x18019f6ca  mov     r9d, ebx; int
0x18019f6cd  lea     rdx, aActivateclassi; "ActivateClassicITA"
0x18019f6d4  mov     r8d, 14E0h; int
0x18019f6da  mov     rcx, r14; this
0x18019f6dd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019f6e2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019f6e9  jb      loc_1801A04A6
0x18019f6ef  mov     edx, 208h
0x18019f6f4  jmp     loc_1801A0488
0x18019f6f9  mov     ecx, dword ptr [rbp+4Fh+Size]; Size
0x18019f6fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18019f701  mov     r13, rax
0x18019f704  test    rax, rax
0x18019f707  jnz     loc_18019F83F
0x18019f70d  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f714  mov     ebx, 8007000Eh
0x18019f719  mov     edi, 7F0h
0x18019f71e  test    rsi, rsi
0x18019f721  jnz     short loc_18019F761
0x18019f723  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18019f729  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f730  mov     rcx, rax
0x18019f733  test    rax, rax
0x18019f736  jz      short loc_18019F753
0x18019f738  mov     rax, [rax]
0x18019f73b  mov     edx, edi
0x18019f73d  mov     rax, [rax+8]
0x18019f741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f746  test    eax, eax
0x18019f748  jz      short loc_18019F753
0x18019f74a  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f751  jmp     short loc_18019F761
0x18019f753  lea     rsi, qword_18033DBA0
0x18019f75a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18019f761  cmp     [rsi+8], r14b
0x18019f765  jz      loc_18019F828
0x18019f76b  cmp     byte ptr [rsi+8], 0
0x18019f76f  lea     r14, [rsi+0D0h]
  ... truncated ...
```
