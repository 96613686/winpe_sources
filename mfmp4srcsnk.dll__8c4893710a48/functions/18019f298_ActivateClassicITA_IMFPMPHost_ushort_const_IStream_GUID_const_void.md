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
  __int64 v10; // rdx
  __int64 v11; // rcx
  HRESULT Instance; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  CallStackTracing *v15; // rsi
  CallStackTracing *v16; // rax
  CallStackContext *v17; // r14
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  CallStackTracing *v31; // rsi
  CallStackTracing *v32; // rax
  CallStackContext *v33; // r14
  DWORD v34; // r15d
  CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  CallStackTracing *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 v41; // rax
  struct IStreamVtbl *lpVtbl; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  CallStackTracing *v47; // rsi
  CallStackTracing *v48; // rax
  CallStackContext *v49; // r14
  DWORD v50; // r15d
  CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  CallStackTracing *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  CallStackTracing *v62; // rsi
  CallStackTracing *v63; // rax
  CallStackContext *v64; // r14
  DWORD v65; // r15d
  CallStackContext *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  CallStackTracing *v70; // rcx
  CallStackTracing *v71; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // r9
  CallStackTracing *v77; // rsi
  CallStackTracing *v78; // rax
  CallStackContext *v79; // r14
  DWORD v80; // r15d
  CallStackContext *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  CallStackTracing *v85; // rcx
  CallStackTracing *v86; // rax
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // r8
  __int64 v91; // r9
  CallStackTracing *v92; // rsi
  CallStackTracing *v93; // rax
  CallStackContext *v94; // r14
  DWORD v95; // r15d
  CallStackContext *v96; // rax
  __int64 v97; // rdx
  __int64 v98; // r8
  __int64 v99; // r9
  CallStackTracing *v100; // rcx
  CallStackTracing *v101; // rax
  __int64 v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // r8
  __int64 v106; // r9
  CallStackTracing *v107; // rsi
  CallStackTracing *v108; // rax
  CallStackContext *v109; // r14
  DWORD v110; // r15d
  CallStackContext *v111; // rax
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  CallStackTracing *v115; // rcx
  CallStackTracing *v116; // rax
  __int64 v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rcx
  __int64 v120; // r8
  __int64 v121; // r9
  CallStackTracing *v122; // rsi
  CallStackTracing *v123; // rax
  CallStackContext *v124; // r14
  DWORD v125; // r15d
  CallStackContext *v126; // rax
  __int64 v127; // rdx
  __int64 v128; // r8
  __int64 v129; // r9
  CallStackTracing *v130; // rcx
  CallStackTracing *v131; // rax
  __int64 v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rcx
  __int64 v135; // r8
  __int64 v136; // r9
  CallStackTracing *v137; // rsi
  CallStackTracing *v138; // rax
  CallStackContext *v139; // r14
  DWORD v140; // r15d
  CallStackContext *v141; // rax
  __int64 v142; // rdx
  __int64 v143; // r8
  __int64 v144; // r9
  CallStackTracing *v145; // rcx
  CallStackTracing *v146; // rax
  __int64 v147; // rax
  __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // r8
  __int64 v151; // r9
  CallStackTracing *v152; // rsi
  CallStackTracing *v153; // rax
  CallStackContext *v154; // r14
  DWORD v155; // r15d
  CallStackContext *v156; // rax
  __int64 v157; // rdx
  __int64 v158; // r8
  __int64 v159; // r9
  CallStackTracing *v160; // rcx
  CallStackTracing *v161; // rax
  __int64 v162; // rax
  __int64 v163; // rdx
  __int64 v164; // rdx
  __int64 v165; // rcx
  __int64 v166; // r8
  __int64 v167; // r9
  CallStackTracing *v168; // rsi
  CallStackTracing *v169; // rax
  CallStackContext *v170; // r14
  DWORD v171; // r15d
  CallStackContext *v172; // rax
  __int64 v173; // rdx
  __int64 v174; // r8
  __int64 v175; // r9
  CallStackTracing *v176; // rcx
  CallStackTracing *v177; // rax
  __int64 v178; // rax
  __int64 v179; // rdx
  __int64 v180; // rcx
  __int64 v181; // r8
  __int64 v182; // r9
  CallStackTracing *v183; // rsi
  CallStackTracing *v184; // rax
  CallStackContext *v185; // r14
  DWORD v186; // r15d
  CallStackContext *v187; // rax
  __int64 v188; // rdx
  __int64 v189; // r8
  __int64 v190; // r9
  CallStackTracing *v191; // rcx
  CallStackTracing *v192; // rax
  __int64 v193; // rax
  __int64 v194; // rdx
  __int64 v195; // rcx
  __int64 v196; // r8
  __int64 v197; // r9
  CallStackTracing *v198; // rsi
  CallStackTracing *v199; // rax
  CallStackContext *v200; // r14
  DWORD v201; // r15d
  CallStackContext *v202; // rax
  __int64 v203; // rdx
  __int64 v204; // r8
  __int64 v205; // r9
  CallStackTracing *v206; // rcx
  CallStackTracing *v207; // rax
  __int64 v208; // rax
  char v210[8]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v211; // [rsp+38h] [rbp-89h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v213; // [rsp+48h] [rbp-79h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-71h] BYREF
  LPVOID ppv[3]; // [rsp+58h] [rbp-69h] BYREF
  _BYTE v216[16]; // [rsp+70h] [rbp-51h] BYREF
  size_t Size; // [rsp+80h] [rbp-41h]

  v213 = 0;
  v9 = 0;
  memset_0(v216, 0, 0x50u);
  ppv[0] = 0;
  ppMFAttributes = 0;
  ppstm = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v210, "ActivateClassicITA", 5337);
  Instance = MFCreateAttributes(&ppMFAttributes, 3u);
  if ( Instance < 0 )
  {
    v15 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v10, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = (CallStackTracing *)&qword_18033DBA0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = (CallStackTracing *)((char *)v15 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v15 + 3));
      if ( Value )
      {
        v17 = Value;
      }
      else if ( !GetLastError() )
      {
        v23 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        v25 = (**(__int64 (__fastcall ***)(CallStackTracing *))v23)(v23);
        if ( v25 )
          v17 = (CallStackContext *)v25;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v17 + 499) != Instance )
        CallStackContext::TraceFailure(v17, "ActivateClassicITA", 5337, Instance);
    }
    if ( g_wppLevels )
    {
      v26 = 518;
LABEL_279:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
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
      v211 = 0;
      Instance = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64))lpVtbl->Stat)(a3, v216, 3);
      if ( Instance < 0 )
      {
        v47 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v44, v43, v45, v46);
          CallStackTracing::s_wpInstance = v48;
          if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
          {
            v47 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v47 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v47 + 8) )
        {
          v49 = (CallStackTracing *)((char *)v47 + 208);
          v50 = GetLastError();
          v51 = (CallStackContext *)TlsGetValue(*((_DWORD *)v47 + 3));
          if ( v51 )
          {
            v49 = v51;
          }
          else if ( !GetLastError() )
          {
            v55 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
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
              v49 = (CallStackContext *)v57;
          }
          SetLastError(v50);
          if ( *((_DWORD *)v49 + 499) != Instance )
            CallStackContext::TraceFailure(v49, "ActivateClassicITA", 5344, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 520;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
      v9 = operator new((unsigned int)Size);
      if ( !v9 )
      {
        v62 = CallStackTracing::s_wpInstance;
        Instance = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v59, v58, v60, v61);
          CallStackTracing::s_wpInstance = v63;
          if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
          {
            v62 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v62 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v62 + 8) )
        {
          v64 = (CallStackTracing *)((char *)v62 + 208);
          v65 = GetLastError();
          v66 = (CallStackContext *)TlsGetValue(*((_DWORD *)v62 + 3));
          if ( v66 )
          {
            v64 = v66;
          }
          else if ( !GetLastError() )
          {
            v70 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68, v69);
              CallStackTracing::s_wpInstance = v71;
              if ( v71
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
              {
                v70 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v70 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v72 = (**(__int64 (__fastcall ***)(CallStackTracing *))v70)(v70);
            if ( v72 )
              v64 = (CallStackContext *)v72;
          }
          SetLastError(v65);
          if ( *((_DWORD *)v64 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v64, "ActivateClassicITA", 5348, -2147024882);
        }
        if ( g_wppLevels )
        {
          v26 = 521;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
      ((void (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a3->lpVtbl->Seek)(a3, v211, 0, 0);
      Instance = ((__int64 (__fastcall *)(struct IStream *, void *, _QWORD, unsigned int *))a3->lpVtbl->Read)(
                   a3,
                   v9,
                   (unsigned int)Size,
                   &v213);
      if ( Instance < 0 )
      {
        v77 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v74, v73, v75, v76);
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
            v85 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83, v84);
              CallStackTracing::s_wpInstance = v86;
              if ( v86
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(v86, 2032) )
              {
                v85 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v85 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v87 = (**(__int64 (__fastcall ***)(CallStackTracing *))v85)(v85);
            if ( v87 )
              v79 = (CallStackContext *)v87;
          }
          SetLastError(v80);
          if ( *((_DWORD *)v79 + 499) != Instance )
            CallStackContext::TraceFailure(v79, "ActivateClassicITA", 5351, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 522;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
      Instance = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *, _QWORD))ppMFAttributes->lpVtbl->SetBlob)(
                   ppMFAttributes,
                   MF_ENCRYPTEDMEDIAEXTENSIONS_INITIALIZATION_DATA,
                   v9,
                   v213);
      if ( Instance < 0 )
      {
        v92 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v89, v88, v90, v91);
          CallStackTracing::s_wpInstance = v93;
          if ( v93 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
          {
            v92 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v92 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v92 + 8) )
        {
          v94 = (CallStackTracing *)((char *)v92 + 208);
          v95 = GetLastError();
          v96 = (CallStackContext *)TlsGetValue(*((_DWORD *)v92 + 3));
          if ( v96 )
          {
            v94 = v96;
          }
          else if ( !GetLastError() )
          {
            v100 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v101 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v97, v98, v99);
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
              v94 = (CallStackContext *)v102;
          }
          SetLastError(v95);
          if ( *((_DWORD *)v94 + 499) != Instance )
            CallStackContext::TraceFailure(v94, "ActivateClassicITA", 5352, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 523;
          goto LABEL_279;
        }
        goto LABEL_280;
      }
    }
    Instance = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( Instance < 0 )
    {
      v107 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v108 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v104, v103, v105, v106);
        CallStackTracing::s_wpInstance = v108;
        if ( v108 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v108 + 8LL))(v108, 2032) )
        {
          v107 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v107 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      if ( *((_BYTE *)v107 + 8) )
      {
        v109 = (CallStackTracing *)((char *)v107 + 208);
        v110 = GetLastError();
        v111 = (CallStackContext *)TlsGetValue(*((_DWORD *)v107 + 3));
        if ( v111 )
        {
          v109 = v111;
        }
        else if ( !GetLastError() )
        {
          v115 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v116 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v112, v113, v114);
            CallStackTracing::s_wpInstance = v116;
            if ( v116
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v116 + 8LL))(v116, 2032) )
            {
              v115 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v115 = (CallStackTracing *)&qword_18033DBA0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
            }
          }
          v117 = (**(__int64 (__fastcall ***)(CallStackTracing *))v115)(v115);
          if ( v117 )
            v109 = (CallStackContext *)v117;
        }
        SetLastError(v110);
        if ( *((_DWORD *)v109 + 499) != Instance )
          CallStackContext::TraceFailure(v109, "ActivateClassicITA", 5356, Instance);
      }
      if ( g_wppLevels )
      {
        v26 = 524;
        goto LABEL_279;
      }
      goto LABEL_280;
    }
    Instance = MFSerializeAttributesToStream(ppMFAttributes, 0, ppstm);
    if ( Instance < 0 )
    {
      v122 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v123 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v119, v118, v120, v121);
        CallStackTracing::s_wpInstance = v123;
        if ( v123 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v123 + 8LL))(v123, 2032) )
        {
          v122 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v122 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      if ( *((_BYTE *)v122 + 8) )
      {
        v124 = (CallStackTracing *)((char *)v122 + 208);
        v125 = GetLastError();
        v126 = (CallStackContext *)TlsGetValue(*((_DWORD *)v122 + 3));
        if ( v126 )
        {
          v124 = v126;
        }
        else if ( !GetLastError() )
        {
          v130 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v131 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v127, v128, v129);
            CallStackTracing::s_wpInstance = v131;
            if ( v131
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v131 + 8LL))(v131, 2032) )
            {
              v130 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v130 = (CallStackTracing *)&qword_18033DBA0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
            }
          }
          v132 = (**(__int64 (__fastcall ***)(CallStackTracing *))v130)(v130);
          if ( v132 )
            v124 = (CallStackContext *)v132;
        }
        SetLastError(v125);
        if ( *((_DWORD *)v124 + 499) != Instance )
          CallStackContext::TraceFailure(v124, "ActivateClassicITA", 5357, Instance);
      }
      if ( g_wppLevels )
      {
        v26 = 525;
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
        v137 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v138 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v134, v133, v135, v136);
          CallStackTracing::s_wpInstance = v138;
          if ( v138 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v138 + 8LL))(v138, 2032) )
          {
            v137 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v137 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v137 + 8) )
        {
          v139 = (CallStackTracing *)((char *)v137 + 208);
          v140 = GetLastError();
          v141 = (CallStackContext *)TlsGetValue(*((_DWORD *)v137 + 3));
          if ( v141 )
          {
            v139 = v141;
          }
          else if ( !GetLastError() )
          {
            v145 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v146 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v142, v143, v144);
              CallStackTracing::s_wpInstance = v146;
              if ( v146
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v146 + 8LL))(v146, 2032) )
              {
                v145 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v145 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v147 = (**(__int64 (__fastcall ***)(CallStackTracing *))v145)(v145);
            if ( v147 )
              v139 = (CallStackContext *)v147;
          }
          SetLastError(v140);
          if ( *((_DWORD *)v139 + 499) != Instance )
            CallStackContext::TraceFailure(v139, "ActivateClassicITA", 5363, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 526;
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
        v198 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v199 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v195, v194, v196, v197);
          CallStackTracing::s_wpInstance = v199;
          if ( v199 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v199 + 8LL))(v199, 2032) )
          {
            v198 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v198 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v198 + 8) )
        {
          v200 = (CallStackTracing *)((char *)v198 + 208);
          v201 = GetLastError();
          v202 = (CallStackContext *)TlsGetValue(*((_DWORD *)v198 + 3));
          if ( v202 )
          {
            v200 = v202;
          }
          else if ( !GetLastError() )
          {
            v206 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v207 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v203, v204, v205);
              CallStackTracing::s_wpInstance = v207;
              if ( v207
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v207 + 8LL))(v207, 2032) )
              {
                v206 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v206 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v208 = (**(__int64 (__fastcall ***)(CallStackTracing *))v206)(v206);
            if ( v208 )
              v200 = (CallStackContext *)v208;
          }
          SetLastError(v201);
          if ( *((_DWORD *)v200 + 499) != Instance )
            CallStackContext::TraceFailure(v200, "ActivateClassicITA", 5381, Instance);
        }
        if ( g_wppLevels )
        {
          v26 = 530;
          goto LABEL_279;
        }
      }
      goto LABEL_280;
    }
    v211 = 0;
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
      Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv[0])(ppv[0], &IID_IPersistStream, &v211);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, LPSTREAM))(*(_QWORD *)v211 + 40LL))(v211, ppstm);
        if ( Instance >= 0 )
        {
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v211);
          goto LABEL_258;
        }
        v183 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v184 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v180, v179, v181, v182);
          CallStackTracing::s_wpInstance = v184;
          if ( v184 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v184 + 8LL))(v184, 2032) )
          {
            v183 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v183 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v183 + 8) )
        {
          v185 = (CallStackTracing *)((char *)v183 + 208);
          v186 = GetLastError();
          v187 = (CallStackContext *)TlsGetValue(*((_DWORD *)v183 + 3));
          if ( v187 )
          {
            v185 = v187;
          }
          else if ( !GetLastError() )
          {
            v191 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v192 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v188, v189, v190);
              CallStackTracing::s_wpInstance = v192;
              if ( v192
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v192 + 8LL))(v192, 2032) )
              {
                v191 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v191 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v193 = (**(__int64 (__fastcall ***)(CallStackTracing *))v191)(v191);
            if ( v193 )
              v185 = (CallStackContext *)v193;
          }
          SetLastError(v186);
          if ( *((_DWORD *)v185 + 499) != Instance )
            CallStackContext::TraceFailure(v185, "ActivateClassicITA", 5377, Instance);
        }
        if ( !g_wppLevels )
        {
LABEL_214:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v211);
          goto LABEL_280;
        }
        v163 = 529;
      }
      else
      {
        v168 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v169 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v165, v164, v166, v167);
          CallStackTracing::s_wpInstance = v169;
          if ( v169 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v169 + 8LL))(v169, 2032) )
          {
            v168 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v168 = (CallStackTracing *)&qword_18033DBA0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
          }
        }
        if ( *((_BYTE *)v168 + 8) )
        {
          v170 = (CallStackTracing *)((char *)v168 + 208);
          v171 = GetLastError();
          v172 = (CallStackContext *)TlsGetValue(*((_DWORD *)v168 + 3));
          if ( v172 )
          {
            v170 = v172;
          }
          else if ( !GetLastError() )
          {
            v176 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v177 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v173, v174, v175);
              CallStackTracing::s_wpInstance = v177;
              if ( v177
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v177 + 8LL))(v177, 2032) )
              {
                v176 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v176 = (CallStackTracing *)&qword_18033DBA0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
              }
            }
            v178 = (**(__int64 (__fastcall ***)(CallStackTracing *))v176)(v176);
            if ( v178 )
              v170 = (CallStackContext *)v178;
          }
          SetLastError(v171);
          if ( *((_DWORD *)v170 + 499) != Instance )
            CallStackContext::TraceFailure(v170, "ActivateClassicITA", 5376, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_214;
        v163 = 528;
      }
    }
    else
    {
      v152 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v153 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v149, v148, v150, v151);
        CallStackTracing::s_wpInstance = v153;
        if ( v153 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v153 + 8LL))(v153, 2032) )
        {
          v152 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v152 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      if ( *((_BYTE *)v152 + 8) )
      {
        v154 = (CallStackTracing *)((char *)v152 + 208);
        v155 = GetLastError();
        v156 = (CallStackContext *)TlsGetValue(*((_DWORD *)v152 + 3));
        if ( v156 )
        {
          v154 = v156;
        }
        else if ( !GetLastError() )
        {
          v160 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v161 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v157, v158, v159);
            CallStackTracing::s_wpInstance = v161;
            if ( v161
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v161 + 8LL))(v161, 2032) )
            {
              v160 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v160 = (CallStackTracing *)&qword_18033DBA0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
            }
          }
          v162 = (**(__int64 (__fastcall ***)(CallStackTracing *))v160)(v160);
          if ( v162 )
            v154 = (CallStackContext *)v162;
        }
        SetLastError(v155);
        if ( *((_DWORD *)v154 + 499) != Instance )
          CallStackContext::TraceFailure(v154, "ActivateClassicITA", 5369, Instance);
      }
      if ( !g_wppLevels )
        goto LABEL_214;
      v163 = 527;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v163, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, Instance);
    goto LABEL_214;
  }
  v31 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27, v29, v30);
    CallStackTracing::s_wpInstance = v32;
    if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
    {
      v31 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v31 = (CallStackTracing *)&qword_18033DBA0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
    }
  }
  if ( *((_BYTE *)v31 + 8) )
  {
    v33 = (CallStackTracing *)((char *)v31 + 208);
    v34 = GetLastError();
    v35 = (CallStackContext *)TlsGetValue(*((_DWORD *)v31 + 3));
    if ( v35 )
    {
      v33 = v35;
    }
    else if ( !GetLastError() )
    {
      v39 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = (CallStackTracing *)&qword_18033DBA0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18033DBA0;
        }
      }
      v41 = (**(__int64 (__fastcall ***)(CallStackTracing *))v39)(v39);
      if ( v41 )
        v33 = (CallStackContext *)v41;
    }
    SetLastError(v34);
    if ( *((_DWORD *)v33 + 499) != Instance )
      CallStackContext::TraceFailure(v33, "ActivateClassicITA", 5338, Instance);
  }
  if ( g_wppLevels )
  {
    v26 = 519;
    goto LABEL_279;
  }
LABEL_280:
  operator delete(v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v210);
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
