# NegHandleClientRequest(unsigned __int64,_NEG_CONTEXT *,ulong,ulong,_SecBufferDesc *,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x180030828`
- end: `0x180032755`
- name: `?NegHandleClientRequest@@YAJ_KPEAU_NEG_CONTEXT@@KKPEAU_SecBufferDesc@@PEA_K2PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `7981`
- prototype: `__int64 __fastcall(unsigned __int64, struct _NEG_CONTEXT *, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned __int64 *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019010`

## callees

- `0x180009330`
- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x180019e18`
- `0x180024338`
- `0x180026320`
- `0x18002b8a0`
- `0x18002da8c`
- `0x18002ea80`
- `0x1800305f4`
- `0x180030808`
- `0x180030828`
- `0x18003275c`
- `0x1800327b4`
- `0x180033234`
- `0x1800337fc`
- `0x180035420`
- `0x1800975ac`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x1800c7e28`
- `0x1800c8278`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030a2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030c24`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800310ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031176`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800312ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003206d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030a2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180030c24`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800310ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031176`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800312ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003206d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180031374`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003208d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180031374`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003208d`
- `ntdll!RtlLeaveCriticalSection` at `0x180031051`
- `ntdll!RtlLeaveCriticalSection` at `0x180031072`
- `ntdll!RtlLeaveCriticalSection` at `0x1800310fc`
- `ntdll!RtlLeaveCriticalSection` at `0x180031680`
- `ntdll!RtlLeaveCriticalSection` at `0x180031705`
- `ntdll!RtlLeaveCriticalSection` at `0x18003203c`
- `ntdll!RtlLeaveCriticalSection` at `0x180031051`
- `ntdll!RtlLeaveCriticalSection` at `0x180031072`
- `ntdll!RtlLeaveCriticalSection` at `0x1800310fc`
- `ntdll!RtlLeaveCriticalSection` at `0x180031680`
- `ntdll!RtlLeaveCriticalSection` at `0x180031705`
- `ntdll!RtlLeaveCriticalSection` at `0x18003203c`
- `ntdll!RtlEnterCriticalSection` at `0x180030e38`
- `ntdll!RtlEnterCriticalSection` at `0x180031060`
- `ntdll!RtlEnterCriticalSection` at `0x180031081`
- `ntdll!RtlEnterCriticalSection` at `0x180031f26`
- `ntdll!RtlEnterCriticalSection` at `0x180030e38`
- `ntdll!RtlEnterCriticalSection` at `0x180031060`
- `ntdll!RtlEnterCriticalSection` at `0x180031081`
- `ntdll!RtlEnterCriticalSection` at `0x180031f26`
- `MSASN1!ASN1_FreeEncoded` at `0x180030b05`
- `MSASN1!ASN1_FreeEncoded` at `0x180030b05`
- `MSASN1!ASN1_Encode` at `0x1800314ad`
- `MSASN1!ASN1_Encode` at `0x1800314ad`
- `MSASN1!ASN1_CreateEncoder` at `0x18003096e`
- `MSASN1!ASN1_CreateEncoder` at `0x18003096e`
- `MSASN1!ASN1_CreateDecoder` at `0x1800309a4`
- `MSASN1!ASN1_CreateDecoder` at `0x180030d31`
- `MSASN1!ASN1_CreateDecoder` at `0x1800309a4`
- `MSASN1!ASN1_CreateDecoder` at `0x180030d31`
- `MSASN1!ASN1_CloseEncoder` at `0x180030b6e`
- `MSASN1!ASN1_CloseEncoder` at `0x180030b6e`
- `MSASN1!ASN1_CloseDecoder` at `0x180030b82`
- `MSASN1!ASN1_CloseDecoder` at `0x180030d96`
- `MSASN1!ASN1_CloseDecoder` at `0x180030b82`
- `MSASN1!ASN1_CloseDecoder` at `0x180030d96`
- `MSASN1!ASN1_Decode` at `0x180030d6d`
- `MSASN1!ASN1_Decode` at `0x180030d6d`
- `MSASN1!ASN1_FreeDecoded` at `0x180030b34`
- `MSASN1!ASN1_FreeDecoded` at `0x180031502`
- `MSASN1!ASN1_FreeDecoded` at `0x180030b34`
- `MSASN1!ASN1_FreeDecoded` at `0x180031502`

## pseudocode

```c
__int64 __fastcall NegHandleClientRequest(
        unsigned __int64 a1,
        struct _NEG_CONTEXT *a2,
        unsigned int a3,
        unsigned int a4,
        struct _SecBufferDesc *a5,
        unsigned __int64 *a6,
        struct _SecBufferDesc *a7,
        unsigned int *a8,
        union _LARGE_INTEGER *a9,
        unsigned __int8 *a10,
        struct _SecBuffer *a11)
{
  struct _NEG_CONTEXT *Context; // rsi
  struct _SecBufferDesc *v12; // r14
  struct _NEG_CONTEXT *v13; // r13
  unsigned int v15; // ebx
  LsaHandleCache *v16; // r10
  _DWORD *v17; // r8
  struct _SecBuffer *v18; // rdx
  signed int v19; // edi
  int v20; // r13d
  __int64 v21; // rsi
  struct _SecBuffer *v22; // rbx
  unsigned int BufferType; // r15d
  __int64 cbBuffer; // r12
  __int64 v25; // rax
  struct _RTL_BALANCED_NODE *pvBuffer; // r14
  _DWORD *Value; // rax
  struct _SecBufferDesc *v28; // r12
  struct _SecBuffer *v29; // r8
  struct _SecBuffer *v30; // rdx
  int v31; // r13d
  LsaHandleCache *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned int v35; // r14d
  struct NegotiationToken *v36; // rdx
  struct ASN1decoding_s *v37; // rbx
  __int64 v39; // rsi
  struct _SecBuffer *v40; // rbx
  unsigned int v41; // r15d
  __int64 v42; // r12
  struct _SecBuffer *v43; // rax
  struct _RTL_BALANCED_NODE *v44; // r14
  _DWORD *v45; // rax
  struct _SecBuffer *v46; // r10
  unsigned int v47; // edx
  __int64 v48; // r13
  unsigned int i; // edx
  _DWORD *v50; // r12
  int v51; // edi
  __int64 v52; // r15
  int v53; // ebx
  unsigned int v54; // r14d
  int v55; // eax
  __int64 v56; // rdx
  LsaHandleCache *v57; // rcx
  unsigned int v58; // ebx
  struct ASN1objectidentifier_s *v59; // rax
  __int64 *v60; // r8
  unsigned int v61; // edx
  struct _RTL_CRITICAL_SECTION *v62; // r12
  struct _RTL_CRITICAL_SECTION *v63; // rbx
  int v64; // r14d
  _QWORD *v65; // r8
  unsigned int v66; // edx
  __int64 v67; // r10
  __int64 *v68; // rcx
  __int64 *v69; // rax
  unsigned int v70; // r9d
  __int64 v71; // r13
  LsaHandleCache *v72; // rcx
  struct MechTypeList *v73; // rdi
  __int64 v74; // r15
  int v75; // edx
  struct _RTL_CRITICAL_SECTION *v76; // rdi
  _QWORD *v77; // rax
  __int64 v78; // rcx
  struct _SecHandle *v79; // rdi
  struct _SecHandle v80; // xmm0
  void *v81; // rax
  __int64 v82; // r8
  __int64 v83; // r9
  __int64 v84; // rcx
  unsigned int cBuffers; // edx
  struct _SecHandle v86; // xmm0
  __int64 v87; // rcx
  unsigned __int64 v88; // r14
  unsigned int v89; // ecx
  int v90; // r9d
  _OWORD *v91; // r14
  __int64 v92; // r8
  struct _SecBufferDesc *v93; // rbx
  __int64 v94; // r8
  unsigned int *v95; // r9
  int *v96; // rbx
  LsaHandleCache *v97; // rcx
  int v98; // ecx
  _DWORD *v99; // r9
  __int16 v100; // r8
  int v101; // eax
  unsigned int v102; // ebx
  LsaHandleCache *v103; // r10
  int v104; // ebx
  struct _SecBuffer *v105; // rbx
  unsigned int v106; // eax
  unsigned int v107; // edx
  unsigned __int8 *v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // rax
  void *v111; // rax
  struct _SecBuffer *v112; // rbx
  int v113; // r10d
  void *v114; // rax
  const void *v115; // rdx
  int v116; // ecx
  unsigned __int8 v117; // al
  union _LARGE_INTEGER *v118; // rcx
  int v119; // eax
  unsigned int *v120; // rbx
  unsigned __int64 v121; // rcx
  __int64 v122; // rcx
  void *v123; // rsp
  void *v124; // rsp
  unsigned int *v125; // rax
  unsigned int v126; // edx
  __int64 v127; // rax
  __int64 v128; // rdx
  LsaHandleCache *v129; // r10
  __int64 v130; // rdx
  struct _RTL_BALANCED_NODE *v131; // rax
  int v132; // eax
  void *v133; // rdx
  struct _RTL_BALANCED_NODE *v134; // rax
  int v135; // eax
  void *v136; // rdx
  struct _RTL_CRITICAL_SECTION *v137; // r12
  unsigned int j; // ecx
  void *v139; // rbx
  __int64 **v140; // r14
  struct _RTL_CRITICAL_SECTION *v141; // rcx
  unsigned int m; // r8d
  __int64 v143; // rbx
  __int64 v144; // rax
  __int64 v145; // r9
  int v146; // eax
  int v147; // eax
  bool v148; // zf
  __int64 **v149; // rbx
  LsaHandleCache **v150; // r10
  unsigned int k; // r8d
  __int64 v152; // rax
  __int64 v153; // r9
  unsigned __int8 v154; // al
  int v155; // eax
  struct _RTL_BALANCED_NODE *v156; // rcx
  struct _SecBuffer *v157; // [rsp+30h] [rbp-40h]
  unsigned int v158; // [rsp+70h] [rbp+0h] BYREF
  struct _NEG_CONTEXT *v159; // [rsp+78h] [rbp+8h] BYREF
  struct NegotiationToken *v160; // [rsp+80h] [rbp+10h] BYREF
  __int64 v161; // [rsp+88h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION *v162; // [rsp+90h] [rbp+20h]
  unsigned int v163; // [rsp+98h] [rbp+28h]
  struct _SecBuffer *v164; // [rsp+A0h] [rbp+30h]
  _DWORD *v165; // [rsp+A8h] [rbp+38h] BYREF
  __int64 *v166; // [rsp+B0h] [rbp+40h] BYREF
  _OWORD *v167; // [rsp+B8h] [rbp+48h]
  struct ASN1decoding_s *v168; // [rsp+C0h] [rbp+50h] BYREF
  PVOID P; // [rsp+C8h] [rbp+58h]
  struct _SecBufferDesc *v170; // [rsp+D0h] [rbp+60h]
  struct _SecBufferDesc *v171; // [rsp+D8h] [rbp+68h]
  struct _SecBufferDesc v172; // [rsp+E0h] [rbp+70h] BYREF
  struct _SecBufferDesc v173; // [rsp+F0h] [rbp+80h] BYREF
  unsigned int v174; // [rsp+100h] [rbp+90h]
  union _LARGE_INTEGER *v175; // [rsp+108h] [rbp+98h]
  unsigned __int8 *v176; // [rsp+110h] [rbp+A0h]
  struct _SecBuffer *v177; // [rsp+118h] [rbp+A8h]
  LPVOID lpTlsValue; // [rsp+120h] [rbp+B0h]
  unsigned __int64 v179; // [rsp+128h] [rbp+B8h]
  unsigned int *v180; // [rsp+130h] [rbp+C0h]
  unsigned __int64 *v181; // [rsp+138h] [rbp+C8h]
  __int128 v182; // [rsp+140h] [rbp+D0h]
  __int16 v183; // [rsp+150h] [rbp+E0h] BYREF
  __int16 v184; // [rsp+158h] [rbp+E8h]
  int v185; // [rsp+15Ch] [rbp+ECh]
  __int64 v186; // [rsp+160h] [rbp+F0h]
  int v187; // [rsp+168h] [rbp+F8h]
  __int64 v188; // [rsp+170h] [rbp+100h]
  int v189; // [rsp+178h] [rbp+108h]
  __int64 v190; // [rsp+180h] [rbp+110h]
  struct _SecHandle v191; // [rsp+1C0h] [rbp+150h] BYREF
  struct _SecHandle v192; // [rsp+1D0h] [rbp+160h] BYREF
  _OWORD v193[3]; // [rsp+1E0h] [rbp+170h] BYREF
  _OWORD v194[4]; // [rsp+210h] [rbp+1A0h] BYREF

  Context = 0;
  v12 = a5;
  v13 = a2;
  v181 = a6;
  v180 = a8;
  v175 = a9;
  v176 = a10;
  v163 = a3;
  v159 = a2;
  v179 = a1;
  v177 = a11;
  v174 = a4;
  v171 = a5;
  v170 = a7;
  v160 = 0;
  v166 = 0;
  memset_0(&v183, 0, 0x68u);
  v161 = 0;
  v168 = 0;
  v158 = 2;
  v167 = 0;
  memset(v194, 0, sizeof(v194));
  memset(v193, 0, sizeof(v193));
  v173 = 0;
  v172 = 0;
  v182 = 0;
  v191 = 0;
  v15 = ASN1_CreateEncoder(SPNEGO_Module, &v161, 0, 0, 0);
  if ( v15 )
  {
    v129 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v130 = 10;
LABEL_284:
      WPP_SF_d(*((_QWORD *)v129 + 2), v130, WPP_a36b0360a7043644a5a822ee72241678_Traceguids, v15);
    }
  }
  else
  {
    v15 = ASN1_CreateDecoder(SPNEGO_Module, &v168, 0, 0, 0);
    if ( !v15 )
    {
      v16 = WPP_GLOBAL_Control;
      goto LABEL_4;
    }
    v129 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v130 = 11;
      goto LABEL_284;
    }
  }
  v19 = SpnegoAsnErrorToSecStatus(v15);
  if ( v19 < 0 )
  {
    if ( v16 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v16 + 28) & 1) == 0 )
      goto LABEL_30;
    WPP_SF_d(*((_QWORD *)v16 + 2), 98, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids, (unsigned int)v19);
    v35 = 2;
    goto LABEL_31;
  }
LABEL_4:
  v162 = (struct _RTL_CRITICAL_SECTION *)a1;
  Context = v13;
  P = v13;
  if ( !a1 && v13 )
    v162 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v13 + 1);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v165 = 0;
  v20 = 0;
  if ( !a5->cBuffers )
    goto LABEL_439;
  v21 = 0;
  while ( 1 )
  {
    v22 = &v12->pBuffers[v20];
    BufferType = v22->BufferType;
    if ( (BufferType & 0xFFFFFFF) == 2 )
    {
      cbBuffer = v22->cbBuffer;
      v25 = (__int64)&v12->pBuffers[v20];
      pvBuffer = (struct _RTL_BALANCED_NODE *)v22->pvBuffer;
      if ( v17 )
        v25 = (__int64)v17;
      v165 = (_DWORD *)v25;
      Value = TlsGetValue(dwCallInfo);
      if ( (v22->BufferType & 0x40000000) != 0 && v22->cbBuffer )
      {
        if ( (v22->BufferType & 0x20000000) == 0 )
        {
          v131 = (struct _RTL_BALANCED_NODE *)LsapAllocate(cbBuffer);
          pvBuffer = v131;
          if ( !v131 )
          {
            v19 = -1073741801;
            goto LABEL_12;
          }
          v132 = LsapCopyFromClient(v22->pvBuffer, v131, (unsigned int)cbBuffer);
          v19 = v132;
          if ( v132 < 0 )
          {
            if ( v132 == -1073741819 )
              v19 = -1073741811;
            LsapSubProv_FreeRoutine(pvBuffer, v133);
            goto LABEL_12;
          }
          goto LABEL_290;
        }
        v19 = (Value[8] & 1) == 0 ? 0xC0000005 : 0;
        if ( (Value[8] & 1) != 0 )
        {
LABEL_290:
          v22->cbBuffer = cbBuffer;
          v22->BufferType = BufferType & 0xBFFFFFFF;
          v22->pvBuffer = pvBuffer;
        }
      }
      else
      {
        v19 = 0;
      }
LABEL_12:
      if ( v21 )
        goto LABEL_15;
      v17 = v165;
      v12 = v171;
      v18 = v22;
      goto LABEL_14;
    }
    if ( (BufferType & 0xFFFFFFF) == 0 )
      break;
LABEL_14:
    if ( ++v20 >= v12->cBuffers )
      goto LABEL_15;
  }
  if ( !v18 )
  {
    v21 = (__int64)&v12->pBuffers[v20];
    goto LABEL_14;
  }
LABEL_15:
  Context = (struct _NEG_CONTEXT *)P;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids,
        (unsigned int)v19);
    goto LABEL_242;
  }
  if ( !v165 )
  {
    v16 = WPP_GLOBAL_Control;
LABEL_439:
    if ( v16 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v16 + 28) & 1) == 0 )
      goto LABEL_23;
    v34 = *((_QWORD *)v16 + 2);
    v33 = 100;
    goto LABEL_22;
  }
  v28 = v170;
  v29 = 0;
  v30 = 0;
  v164 = 0;
  v19 = 0;
  v31 = 0;
  if ( !v170->cBuffers )
  {
LABEL_18:
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v33 = 102;
      goto LABEL_21;
    }
    goto LABEL_23;
  }
  v39 = 0;
  while ( 2 )
  {
    v40 = &v28->pBuffers[v31];
    v41 = v40->BufferType;
    if ( (v41 & 0xFFFFFFF) == 2 )
    {
      v42 = v40->cbBuffer;
      v43 = v40;
      v44 = (struct _RTL_BALANCED_NODE *)v40->pvBuffer;
      if ( v29 )
        v43 = v29;
      v164 = v43;
      v45 = TlsGetValue(dwCallInfo);
      if ( (v40->BufferType & 0x40000000) != 0 && v40->cbBuffer )
      {
        if ( (v40->BufferType & 0x20000000) != 0 )
        {
          v19 = (v45[8] & 1) == 0 ? 0xC0000005 : 0;
          if ( (v45[8] & 1) != 0 )
            goto LABEL_300;
        }
        else
        {
          v134 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v42);
          v44 = v134;
          if ( v134 )
          {
            v135 = LsapCopyFromClient(v40->pvBuffer, v134, (unsigned int)v42);
            v19 = v135;
            if ( v135 >= 0 )
            {
LABEL_300:
              v40->cbBuffer = v42;
              v40->BufferType = v41 & 0xBFFFFFFF;
              v40->pvBuffer = v44;
            }
            else
            {
              if ( v135 == -1073741819 )
                v19 = -1073741811;
              LsapSubProv_FreeRoutine(v44, v136);
            }
          }
          else
          {
            v19 = -1073741801;
          }
        }
      }
      else
      {
        v19 = 0;
      }
      v28 = v170;
      if ( v39 )
        goto LABEL_60;
      v29 = v164;
      v30 = v40;
LABEL_59:
      if ( ++v31 >= v28->cBuffers )
        goto LABEL_60;
      continue;
    }
    break;
  }
  if ( (v41 & 0xFFFFFFF) != 0 )
    goto LABEL_59;
  if ( !v30 )
  {
    v39 = (__int64)&v28->pBuffers[v31];
    goto LABEL_59;
  }
LABEL_60:
  Context = (struct _NEG_CONTEXT *)P;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
LABEL_242:
    v13 = Context;
    goto LABEL_30;
  }
  v46 = v164;
  if ( !v164 )
    goto LABEL_18;
  v47 = 0;
  P = 0;
  while ( v47 < v171->cBuffers )
  {
    if ( (v171->pBuffers[v47].BufferType & 0xFFFFFFF) == 0xE )
    {
      P = &v171->pBuffers[v47];
      break;
    }
    ++v47;
  }
  v48 = 0;
  v171 = 0;
  for ( i = 0; i < v28->cBuffers; ++i )
  {
    if ( (v28->pBuffers[i].BufferType & 0xFFFFFFF) == 0x1E )
    {
      v48 = (__int64)&v28->pBuffers[i];
      v171 = (struct _SecBufferDesc *)v48;
      break;
    }
  }
  v50 = v165;
  v51 = *v165;
  if ( !*v165 && Context )
  {
    v164->cbBuffer = 0;
    v13 = Context;
    if ( !*((_DWORD *)Context + 21) )
    {
      v117 = *((_BYTE *)Context + 80);
      if ( v117 )
      {
        *v176 = v117;
        *v177 = *((struct _SecBuffer *)Context + 4);
        *((_OWORD *)Context + 4) = 0;
      }
      v118 = v175;
      v46->cbBuffer = 0;
      *v118 = *(union _LARGE_INTEGER *)((char *)Context + 88);
      v119 = NegpChangeHandle((struct _SecHandle *)((char *)Context + 24));
      *((_QWORD *)Context + 3) = 0;
      *((_QWORD *)Context + 4) = 0;
      v19 = v119 == 0 ? 0xC000009A : 0;
      Context = 0;
      goto LABEL_30;
    }
LABEL_29:
    v19 = -2146893048;
    goto LABEL_30;
  }
  v165 = 0;
  if ( !v51 || (v52 = *((_QWORD *)v50 + 1)) == 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a36b0360a7043644a5a822ee72241678_Traceguids);
LABEL_182:
    v107 = *v50;
    v108 = (unsigned __int8 *)*((_QWORD *)v50 + 1);
    v35 = 1;
    v58 = 1;
    v158 = 1;
    v19 = SpnegoUnpackData(v108, v107, 1u, (void **)&v160);
    if ( v19 >= 0 )
    {
      v57 = WPP_GLOBAL_Control;
      goto LABEL_82;
    }
    SpmpReportHourlyEvent(&NEGOTIATE_UNKNOWN_PACKET, (unsigned __int16 *)&cchOriginalDestLength);
    v13 = Context;
    goto LABEL_31;
  }
  v53 = 0;
  v54 = ASN1_CreateDecoder(SPNEGO_Module, &v165, 0, 0, 0);
  if ( v54 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a36b0360a7043644a5a822ee72241678_Traceguids, v54);
    v53 = SpnegoAsnErrorToSecStatus(v54);
    if ( v53 < 0 )
      goto LABEL_182;
  }
  v166 = 0;
  v55 = ASN1_Decode(v165, &v166, 2, 8, v52, v51);
  v56 = (unsigned int)v55;
  if ( v55 >= 0 )
  {
    v57 = WPP_GLOBAL_Control;
    goto LABEL_78;
  }
  v53 = SpnegoAsnErrorToSecStatus((unsigned int)v55);
  if ( (_DWORD)v56 == -1009 || (_DWORD)v56 == -1002 )
  {
    v57 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a36b0360a7043644a5a822ee72241678_Traceguids, 2);
      goto LABEL_186;
    }
  }
  else
  {
LABEL_186:
    v57 = WPP_GLOBAL_Control;
  }
  v166 = 0;
LABEL_78:
  if ( v165 )
  {
    ASN1_CloseDecoder(v165, v56);
    v57 = WPP_GLOBAL_Control;
  }
  if ( v53 < 0 )
    goto LABEL_182;
  v58 = 2;
  v160 = (struct NegotiationToken *)(v166 + 1);
LABEL_82:
  if ( v166 )
  {
    v59 = NegSpnegoMechOid;
    v60 = (__int64 *)*v166;
    if ( NegSpnegoMechOid )
    {
      while ( 1 )
      {
        v61 = *((_DWORD *)v59 + 2);
        if ( v61 < *((_DWORD *)v60 + 2) || v61 > *((_DWORD *)v60 + 2) )
          goto LABEL_28;
        v59 = *(struct ASN1objectidentifier_s **)v59;
        v60 = (__int64 *)*v60;
        if ( !v59 && !v60 )
          break;
        if ( !v60 || !v59 )
          goto LABEL_28;
      }
    }
  }
  if ( *(_WORD *)v160 == 2 )
  {
    if ( Context )
    {
      if ( (*((_DWORD *)Context + 24) & 0x200) != 0 )
      {
        v157 = (struct _SecBuffer *)v48;
        v13 = Context;
        v19 = NegHandleSubsequentClientRequest(
                v179,
                Context,
                v163,
                v174,
                v58,
                (struct _SecBuffer *)P,
                v157,
                v160,
                v181,
                v170,
                v180,
                v175,
                v176,
                v177);
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
        }
LABEL_30:
        v35 = v158;
        goto LABEL_31;
      }
      if ( v57 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 )
      {
        v109 = 103;
LABEL_262:
        WPP_SF_(*((_QWORD *)v57 + 2), v109, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
      }
    }
    else
    {
      if ( (*((_BYTE *)v160 + 8) & 0x20) == 0 )
      {
        if ( v57 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v57 + 28) & 1) == 0 )
          goto LABEL_28;
        v109 = 106;
        goto LABEL_262;
      }
      v137 = v162;
      if ( v162 )
      {
        v63 = v162 + 1;
        RtlEnterCriticalSection(v162 + 1);
        for ( j = 0; j < HIDWORD(v137[2].SpinCount); ++j )
        {
          v74 = j;
          v71 = *((_QWORD *)&v137[3].LockSemaphore + 4 * j);
          if ( (*(_DWORD *)(*(_QWORD *)(v71 + 16) + 16LL) & 0x100000) != 0 )
          {
            v73 = 0;
            v64 = 3;
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
            }
            v183 = 2;
            goto LABEL_117;
          }
        }
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
        }
        v19 = -2146893048;
        goto LABEL_342;
      }
      if ( v57 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 )
      {
        v109 = (unsigned int)((_DWORD)v162 + 107);
        goto LABEL_262;
      }
    }
LABEL_28:
    v13 = Context;
    goto LABEL_29;
  }
  if ( *(_WORD *)v160 != 1 )
  {
    if ( v57 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v57 + 28) & 1) == 0 )
      goto LABEL_28;
    v109 = 105;
    goto LABEL_262;
  }
  v62 = v162;
  v63 = v162 + 1;
  RtlEnterCriticalSection(v162 + 1);
  v64 = 0;
  v65 = (_QWORD *)*((_QWORD *)v160 + 2);
  while ( v65 )
  {
    v66 = 0;
LABEL_95:
    if ( v66 < HIDWORD(v62[2].SpinCount) )
    {
      v67 = 32LL * v66;
      v68 = (__int64 *)(*(_QWORD **)((char *)&v62[3].LockSemaphore + v67))[3];
      v69 = (__int64 *)v65[1];
      while ( v69 )
      {
        v70 = *((_DWORD *)v69 + 2);
        if ( v70 < *((_DWORD *)v68 + 2) || v70 > *((_DWORD *)v68 + 2) )
          goto LABEL_102;
        v69 = (__int64 *)*v69;
        v68 = (__int64 *)*v68;
        if ( !v69 )
        {
          if ( v68 )
          {
LABEL_102:
            ++v66;
            goto LABEL_95;
          }
          break;
        }
        if ( !v68 )
          goto LABEL_102;
      }
      _mm_lfence();
      v71 = *(__int64 *)((char *)&v62[3].LockSemaphore + v67);
      v64 = (v64 != 0) + 1;
LABEL_110:
      v72 = WPP_GLOBAL_Control;
      goto LABEL_111;
    }
    v65 = (_QWORD *)*v65;
    if ( !v64 )
      v64 = 3;
  }
  v71 = 0;
  v66 = -1;
  if ( v64 )
    goto LABEL_110;
  v64 = 3;
  v72 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
    goto LABEL_194;
  }
LABEL_111:
  if ( v64 == 3 || !v71 )
  {
LABEL_194:
    RtlLeaveCriticalSection(v63);
    SpmpReportHourlyEvent(&NEGOTIATE_UNKNOWN_PACKAGE, (unsigned __int16 *)&cchOriginalDestLength);
    v57 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v109 = 110;
      goto LABEL_262;
    }
    goto LABEL_28;
  }
  v73 = (struct MechTypeList *)*((_QWORD *)v160 + 2);
  v74 = v66;
  if ( v72 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v72 + 7) & 0x1000) != 0 )
  {
    WPP_SF_Z(*((_QWORD *)v72 + 2), 111, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids, *(_QWORD *)(v71 + 16) + 48LL);
    v72 = WPP_GLOBAL_Control;
  }
  v183 = 2;
  if ( Context )
    goto LABEL_119;
LABEL_117:
  Context = NegpCreateContext();
  if ( !Context )
  {
    v19 = -2146893056;
    goto LABEL_341;
  }
  v72 = WPP_GLOBAL_Control;
LABEL_119:
  v75 = *((_DWORD *)Context + 24);
  if ( (v75 & 0x200) != 0 )
  {
    v19 = -2146893048;
    if ( v72 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v72 + 2), 112, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
LABEL_341:
    if ( !v162 )
      goto LABEL_214;
LABEL_342:
    RtlLeaveCriticalSection(v63);
    goto LABEL_214;
  }
  v148 = *((_DWORD *)Context + 30) == 0;
  *((_DWORD *)Context + 24) = v75 | 0x200;
  if ( v148 )
  {
    if ( v73 )
    {
      v19 = NegpEncodeMechlist(v73, (struct _SecBuffer *)((char *)Context + 120));
      if ( v19 < 0 )
        goto LABEL_341;
    }
  }
  v76 = v162;
  if ( !*((_QWORD *)Context + 1) )
  {
    *((_QWORD *)Context + 1) = v162;
    RtlLeaveCriticalSection(v63);
    RtlEnterCriticalSection(v63);
    ++HIDWORD(v76->DebugInfo);
    RtlLeaveCriticalSection(v63);
    RtlEnterCriticalSection(v63);
  }
  *((_QWORD *)Context + 2) = v74;
  if ( *(_WORD *)v160 != 1 )
  {
    if ( *(_WORD *)v160 == 2 )
      goto LABEL_128;
    goto LABEL_199;
  }
  if ( v64 != 1 || (*((_BYTE *)v160 + 8) & 0x40) == 0 )
  {
LABEL_199:
    RtlLeaveCriticalSection(v63);
    if ( *(_WORD *)v160 != 1 )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      v33 = 124;
      goto LABEL_21;
    }
    if ( (*((_BYTE *)v160 + 8) & 0x40) == 0 || (*(_DWORD *)(*(_QWORD *)(v71 + 16) + 16LL) & 0x100000) == 0 )
    {
LABEL_201:
      SpmpReportHourlyEvent(
        &NEGOTIATE_MESSAGE_DECODED_NO_TOKEN,
        L"uu",
        *(_QWORD *)(v71 + 16) + 48LL,
        *(_QWORD *)(v71 + 16) + 48LL);
      v19 = 590610;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids,
          *(_QWORD *)(v71 + 16) + 48LL);
      }
      v184 |= 0xC0u;
      if ( v64 == 1 )
      {
        v185 = 1;
      }
      else
      {
        *((_DWORD *)Context + 24) |= 0x2000u;
        v185 = 3;
      }
      v110 = *(_QWORD *)(v71 + 24);
LABEL_205:
      v186 = v110;
      goto LABEL_166;
    }
    v149 = (__int64 **)*((_QWORD *)v160 + 2);
    v97 = WPP_GLOBAL_Control;
    v150 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
      v97 = WPP_GLOBAL_Control;
      v150 = &WPP_GLOBAL_Control;
    }
    if ( v149 )
    {
      do
      {
        for ( k = 0; k < HIDWORD(v76[2].SpinCount); ++k )
        {
          v71 = *((_QWORD *)&v76[3].LockSemaphore + 4 * k);
          v152 = *(_QWORD *)(v71 + 16);
          if ( (*(_DWORD *)(v152 + 16) & 0x100000) == 0
            && *(_DWORD *)(v152 + 20) != 16
            && !(unsigned int)NegpCompareOid(
                                (struct ASN1objectidentifier_s *)v149[1],
                                *(struct ASN1objectidentifier_s **)(v71 + 24)) )
          {
            *((_QWORD *)Context + 2) = v153;
            if ( v71 )
              goto LABEL_201;
            break;
          }
        }
        v149 = (__int64 **)*v149;
      }
      while ( v149 );
      v97 = WPP_GLOBAL_Control;
    }
    v19 = -2146893042;
    if ( v97 == (LsaHandleCache *)v150 || (*((_BYTE *)v97 + 28) & 1) == 0 )
      goto LABEL_214;
    v128 = 126;
LABEL_348:
    WPP_SF_(*((_QWORD *)v97 + 2), v128, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
    goto LABEL_214;
  }
LABEL_128:
  v192 = 0;
  v77 = TlsGetValue(dwCallInfo);
  v78 = 32LL * *((_QWORD *)Context + 2);
  v179 = (unsigned __int64)v77;
  v77[5] = (*(_QWORD **)((char *)&v76[3].LockSemaphore + v78))[3];
  RtlLeaveCriticalSection(v63);
  SpmpReportHourlyEvent(&NEGOTIATE_MESSAGE_DECODED, L"uu", *(_QWORD *)(v71 + 16) + 48LL, *(_QWORD *)(v71 + 16) + 48LL);
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
  }
  v79 = (struct _SecHandle *)((char *)Context + 24);
  v80 = *(struct _SecHandle *)((char *)Context + 24);
  v191 = v80;
  if ( **(_QWORD **)(v71 + 16) != v80.dwLower && v80.dwLower - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v139 = TlsGetValue(dwThreadPackage);
    WLsaDeleteContext((struct _SecHandle *)((char *)Context + 24));
    TlsSetValue(dwThreadPackage, v139);
    *v79 = 0;
    v191 = 0;
  }
  v81 = TlsGetValue(dwThreadPackage);
  v84 = 32LL * *((_QWORD *)Context + 2);
  cBuffers = 1;
  lpTlsValue = v81;
  v86 = *(struct _SecHandle *)((char *)&v162[3].SpinCount + v84);
  v172.ulVersion = 0;
  v172.pBuffers = (PSecBuffer)v193;
  v172.cBuffers = 1;
  v87 = *(_QWORD *)(v71 + 16);
  v192 = v86;
  v88 = *(unsigned int *)(v87 + 28);
  v89 = v164->cbBuffer;
  if ( v164->cbBuffer >= (unsigned int)v88 )
  {
    v90 = 2;
    *((_QWORD *)&v182 + 1) = v164->pvBuffer;
    *((_QWORD *)&v193[0] + 1) = *((_QWORD *)&v182 + 1);
    *(_QWORD *)&v193[0] = v89 | 0x200000000LL;
    goto LABEL_136;
  }
  v120 = 0;
  *(_QWORD *)&v193[0] = (unsigned int)v88 | 0x200000000LL;
  if ( (_DWORD)v88 )
  {
    if ( v88 <= g_ulMaxStackAllocSize )
    {
      v121 = v88 + g_ulAdditionalProbeSize + 8;
      if ( v121 >= v88 )
      {
        if ( (unsigned int)VerifyStackAvailable(v121, 1, v82, v83) )
        {
          v122 = v88 + 23;
          if ( v88 + 23 <= v88 + 8 )
            v122 = 0xFFFFFFFFFFFFFF0LL;
          v123 = alloca(v122 & 0xFFFFFFFFFFFFFFF0uLL);
          v124 = alloca(v122 & 0xFFFFFFFFFFFFFFF0uLL);
          v120 = &v158;
          if ( &v158 )
          {
            v158 = 1801679955;
            v120 = (unsigned int *)&v159;
            if ( &v159 )
            {
LABEL_276:
              cBuffers = v172.cBuffers;
              goto LABEL_277;
            }
          }
        }
        cBuffers = v172.cBuffers;
      }
    }
  }
  if ( v88 + 8 >= v88 )
  {
    v125 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
    v120 = v125;
    if ( v125 )
    {
      *v125 = 1885431112;
      v120 = v125 + 2;
    }
    goto LABEL_276;
  }
LABEL_277:
  *((_QWORD *)&v193[0] + 1) = v120;
  if ( !v120 )
  {
    v19 = -2146893056;
LABEL_214:
    v13 = v159;
    goto LABEL_30;
  }
  v90 = 2;
  v79 = (struct _SecHandle *)((char *)Context + 24);
LABEL_136:
  v91 = 0;
  v173.pBuffers = (PSecBuffer)v194;
  *(_QWORD *)&v173.ulVersion = 0;
  v148 = *(_WORD *)v160 == 1;
  v173.cBuffers = 1;
  if ( v148 )
  {
    *((_QWORD *)&v194[0] + 1) = *((_QWORD *)v160 + 6);
    LODWORD(v194[0]) = *((_DWORD *)v160 + 10);
    DWORD1(v194[0]) = -2147483646;
    v173.cBuffers = 2;
    v194[1] = *(_OWORD *)((char *)Context + 120);
    if ( (*((_BYTE *)v160 + 8) & 0x20) != 0 && *((_DWORD *)v160 + 14) )
    {
      v92 = 3;
      v91 = &v194[2];
      v173.cBuffers = 3;
      v90 = 3;
      *((_QWORD *)&v194[2] + 1) = *((_QWORD *)v160 + 8);
      LODWORD(v194[2]) = *((_DWORD *)v160 + 14);
      DWORD1(v194[2]) = 12;
    }
    else
    {
      v92 = 2;
    }
    if ( (*((_DWORD *)Context + 24) & 0x4400) == 0
      && ((*((_DWORD *)Context + 24) & 0x2000) != 0
       || (*((_BYTE *)v160 + 8) & 0x20) != 0 && *((_DWORD *)v160 + 14)
       || NegSendOptionalMechlistMIC) )
    {
      v172.cBuffers = ++cBuffers;
      DWORD1(v193[cBuffers - 1]) = 12;
      v167 = &v193[cBuffers - 1];
    }
  }
  else
  {
    v90 = 1;
    *((_QWORD *)&v194[0] + 1) = *((_QWORD *)v160 + 4);
    v92 = 1;
    LODWORD(v194[0]) = *((_DWORD *)v160 + 6);
    DWORD1(v194[0]) = -2147483646;
  }
  if ( P )
  {
    v173.cBuffers = v90 + 1;
    v194[v92] = *(_OWORD *)P;
  }
  v93 = v171;
  if ( v171 )
  {
    v126 = cBuffers + 1;
    v172.cBuffers = v126;
    if ( (v163 & 0x100) != 0 )
    {
      v171->ulVersion = 4;
      v127 = LsapAllocate(4);
      v93->pBuffers = (PSecBuffer)v127;
      if ( !v127 )
      {
        v19 = -2146893056;
        v97 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_214;
        }
        v128 = 114;
        goto LABEL_348;
      }
      v126 = v172.cBuffers;
    }
    v193[v126 - 1] = *v93;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(v71 + 16) + 16LL) & 0x100000) != 0 )
    *(_DWORD *)(v179 + 32) |= 0x8000u;
  v95 = (unsigned int *)TlsGetValue(dwSession);
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_Diiii(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v191.dwUpper,
      v94,
      v95[4],
      v192.dwUpper,
      v192.dwLower,
      v191.dwUpper,
      v191.dwLower);
  v96 = (int *)((char *)Context + 56);
  v19 = WLsaProcessContext(
          0,
          &v192,
          &v191,
          0,
          &v173,
          v163 & 0xFFFFFEFF,
          0x10u,
          v79,
          &v172,
          (unsigned int *)Context + 14,
          (union _LARGE_INTEGER *)Context + 11,
          (unsigned __int8 *)Context + 80,
          (struct _SecBuffer *)Context + 4);
  TlsSetValue(dwThreadPackage, lpTlsValue);
  ++*((_BYTE *)Context + 81);
  v97 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    WPP_SF_ZD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      115,
      (unsigned int)WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids,
      *(_QWORD *)(*((_QWORD *)&v162[3].LockSemaphore + 4 * *((_QWORD *)Context + 2)) + 16LL) + 48,
      v19);
    v97 = WPP_GLOBAL_Control;
  }
  if ( v19 < 0 )
  {
    if ( *((_QWORD *)Context + 4) )
    {
      WLsaDeleteContext((struct _SecHandle *)((char *)Context + 24));
      *(_OWORD *)((char *)Context + 24) = 0;
      v97 = WPP_GLOBAL_Control;
    }
    v113 = 1;
    if ( v19 != -2146893042 || *(_WORD *)v160 != 1 || (*(_DWORD *)(*(_QWORD *)(v71 + 16) + 16LL) & 0x100000) == 0 )
    {
      if ( v97 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v97 + 28) & 1) != 0 )
        WPP_SF_ZD(
          *((_QWORD *)v97 + 2),
          119,
          (unsigned int)WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids,
          *(_QWORD *)(v71 + 16) + 48,
          v19);
      goto LABEL_214;
    }
    v140 = (__int64 **)*((_QWORD *)v160 + 2);
    if ( v97 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v97 + 7) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)v97 + 2), 116, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
      v97 = WPP_GLOBAL_Control;
      v113 = 1;
    }
    if ( v140 )
    {
      while ( 2 )
      {
        v141 = v162;
        for ( m = 0; m < HIDWORD(v141[2].SpinCount); m += v113 )
        {
          v143 = *((_QWORD *)&v141[3].LockSemaphore + 4 * m);
          v144 = *(_QWORD *)(v143 + 16);
          if ( (*(_DWORD *)(v144 + 16) & 0x100000) == 0 && *(_DWORD *)(v144 + 20) != 16 )
          {
            if ( !(unsigned int)NegpCompareOid(
                                  (struct ASN1objectidentifier_s *)v140[1],
                                  *(struct ASN1objectidentifier_s **)(v143 + 24)) )
            {
              *((_QWORD *)Context + 2) = v145;
              if ( v143 )
              {
                if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                {
                  WPP_SF_Z(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    118,
                    WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids,
                    *(_QWORD *)(v143 + 16) + 48LL);
                }
                v19 = 590610;
                v184 |= 0xC0u;
                *((_DWORD *)Context + 24) |= 0x2000u;
                v185 = 3;
                v110 = *(_QWORD *)(v143 + 24);
                goto LABEL_205;
              }
              break;
            }
            v141 = v162;
          }
        }
        v140 = (__int64 **)*v140;
        if ( v140 )
          continue;
        break;
      }
      v97 = WPP_GLOBAL_Control;
    }
    if ( v97 == (LsaHandleCache *)&WPP_GLOBAL_Control || ((unsigned __int8)v113 & *((_BYTE *)v97 + 28)) == 0 )
      goto LABEL_214;
    v128 = 117;
    goto LABEL_348;
  }
  *((_DWORD *)Context + 21) = v19;
  if ( !v19 && (*((_DWORD *)Context + 24) & 0x1800) == 0 )
    *v96 |= 0x2000000u;
  v98 = *v96;
  v99 = v167;
  if ( (*v96 & 0x2000000) != 0 )
  {
    v146 = *((_DWORD *)Context + 24);
    v98 &= ~0x2000000u;
    *v96 = v98;
    if ( LODWORD(v193[0]) )
    {
      v147 = v146 | 0x800;
      v148 = v99 == 0;
    }
    else
    {
      v147 = v146 | 0x1000;
      v148 = v91 == 0;
    }
    *((_DWORD *)Context + 24) = v147;
    if ( v148 )
      *((_DWORD *)Context + 24) = v147 | 0x4000;
  }
  if ( *(_WORD *)v160 == 1
    && (*((_DWORD *)Context + 24) & 0x3000) == 0x3000
    && ((*((_BYTE *)v160 + 8) & 0x20) == 0 || !*((_DWORD *)v160 + 14))
    && !NegAcceptUnsafeUnprotectedNegotiation
    && (v98 & 0x20010) != 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v33 = 120;
      goto LABEL_21;
    }
LABEL_23:
    v13 = v159;
    goto LABEL_29;
  }
  *((_DWORD *)Context + 24) |= 1u;
  v100 = v184;
  if ( LODWORD(v193[0]) )
  {
    v100 = v184 | 0x20;
    v184 |= 0x20u;
    v188 = *((_QWORD *)&v193[0] + 1);
    v187 = v193[0];
  }
  if ( v99 && *v99 )
  {
    *((_DWORD *)Context + 24) |= 0x400u;
    v100 = v184 | 0x10;
    v184 |= 0x10u;
    v190 = *((_QWORD *)&v193[v172.cBuffers - 1] + 1);
    v189 = v193[v172.cBuffers - 1];
    goto LABEL_165;
  }
  if ( (*((_DWORD *)Context + 24) & 0x2800) == 0x2800 && !NegAcceptUnsafeUnprotectedNegotiation && (*v96 & 0x20010) != 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    v33 = 121;
    goto LABEL_21;
  }
  if ( *(_WORD *)v160 == 1
    && (*((_DWORD *)Context + 24) & 0x1000) != 0
    && (*((_BYTE *)v160 + 8) & 0x20) != 0
    && *((_DWORD *)v160 + 14)
    && *((_DWORD *)v160 + 10) < 0x40u
    && (*v96 & 0x10010) != 0 )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    v33 = 122;
LABEL_21:
    v34 = *((_QWORD *)v32 + 2);
LABEL_22:
    WPP_SF_(v34, v33, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
    goto LABEL_23;
  }
LABEL_165:
  v186 = *(_QWORD *)(v71 + 24);
  v184 = v100 | 0xC0;
  v185 = v19 != 0;
LABEL_166:
  v101 = ASN1_Encode(v161, &v183, 1, 16, 0, 0);
  v102 = v101;
  if ( v101 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_a36b0360a7043644a5a822ee72241678_Traceguids,
        (unsigned int)v101);
    v104 = SpnegoAsnErrorToSecStatus(v102);
  }
  else
  {
    v103 = WPP_GLOBAL_Control;
    v104 = 0;
  }
  if ( *((_QWORD *)&v193[0] + 1) != *((_QWORD *)&v182 + 1) )
  {
    if ( *((_QWORD *)&v193[0] + 1) && *(_DWORD *)(*((_QWORD *)&v193[0] + 1) - 8LL) == 1885431112 )
    {
      ((void (*)(void))g_pfnFree)();
      v103 = WPP_GLOBAL_Control;
    }
    *((_QWORD *)&v193[0] + 1) = 0;
  }
  v35 = v158;
  if ( v166 )
  {
    if ( v168 )
    {
      ASN1_FreeDecoded(v168, v166, v158);
      v103 = WPP_GLOBAL_Control;
    }
    v166 = 0;
LABEL_173:
    v160 = 0;
  }
  else if ( v160 )
  {
    SpnegoFreeDecodedData(v168, v158, v160);
    v103 = WPP_GLOBAL_Control;
    goto LABEL_173;
  }
  if ( v104 < 0 )
  {
    if ( v103 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v103 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v103 + 2), 128, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids, (unsigned int)v104);
    v19 = v104;
    goto LABEL_180;
  }
  if ( (v163 & 0x100) != 0 )
  {
    v111 = (void *)LsapAllocate(*(unsigned int *)(v161 + 28));
    v112 = v164;
    v164->pvBuffer = v111;
    if ( !v111 )
      goto LABEL_207;
    memcpy_0(v111, *(const void **)(v161 + 16), *(unsigned int *)(v161 + 28));
    v112->cbBuffer = *(_DWORD *)(v161 + 28);
    *((_DWORD *)Context + 14) |= 0x100u;
LABEL_178:
    *v180 = *((_DWORD *)Context + 14);
    *v175 = *(union _LARGE_INTEGER *)((char *)Context + 88);
    if ( v19 )
    {
      *v181 = (unsigned __int64)Context;
      goto LABEL_180;
    }
    v154 = *((_BYTE *)Context + 80);
    if ( v154 )
    {
      *v176 = v154;
      *v177 = *((struct _SecBuffer *)Context + 4);
      *((_QWORD *)Context + 9) = 0;
    }
    v155 = NegpChangeHandle((struct _SecHandle *)((char *)Context + 24));
    v13 = v159;
    *((_QWORD *)Context + 3) = 0;
    if ( !v155 )
      v19 = -1073741670;
    *((_QWORD *)Context + 4) = 0;
    if ( !v13 )
      NegpDeleteContext(Context);
    Context = 0;
  }
  else
  {
    v105 = v164;
    v106 = *(_DWORD *)(v161 + 28);
    if ( v164->cbBuffer >= v106 )
    {
      memcpy_0(v164->pvBuffer, *(const void **)(v161 + 16), v106);
      v105->cbBuffer = *(_DWORD *)(v161 + 28);
      goto LABEL_178;
    }
    if ( (v163 & 0x800000) != 0 && v164->cbBuffer >= 5 )
    {
      v114 = (void *)LsapAllocate(*(unsigned int *)(v161 + 28));
      *((_QWORD *)Context + 13) = v114;
      if ( v114 )
      {
        memcpy_0(v114, *(const void **)(v161 + 16), *(unsigned int *)(v161 + 28));
        v115 = (const void *)*((_QWORD *)Context + 13);
        v116 = *(_DWORD *)(v161 + 28);
        *((_DWORD *)Context + 24) |= 8u;
        *((_DWORD *)Context + 29) = v116;
        memcpy_0(v105->pvBuffer, v115, v105->cbBuffer);
        *((_DWORD *)Context + 28) = v105->cbBuffer;
        goto LABEL_178;
      }
    }
LABEL_207:
    v19 = -2146893056;
LABEL_180:
    v13 = v159;
  }
LABEL_31:
  if ( v161 )
    ASN1_FreeEncoded(v161, *(_QWORD *)(v161 + 16));
  v36 = (struct NegotiationToken *)v166;
  if ( (v166 || (v36 = v160) != 0) && v168 && v36 )
    ASN1_FreeDecoded(v168, v36, v35);
  if ( *((_QWORD *)&v193[0] + 1) != *((_QWORD *)&v182 + 1)
    && *((_QWORD *)&v193[0] + 1)
    && *(_DWORD *)(*((_QWORD *)&v193[0] + 1) - 8LL) == 1885431112 )
  {
    ((void (*)(void))g_pfnFree)();
  }
  if ( v167 )
  {
    v156 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)v167 + 1);
    if ( v156 )
      LsapSubProv_FreeRoutine(v156, v36);
  }
  v37 = v168;
  if ( v161 )
    ASN1_CloseEncoder();
  if ( v37 )
    ASN1_CloseDecoder(v37, v36);
  if ( v19 < 0 && Context )
  {
    if ( *((_QWORD *)Context + 3) )
    {
      WLsaDeleteContext((struct _SecHandle *)((char *)Context + 24));
      *((_QWORD *)Context + 3) = 0;
    }
    if ( !v13 )
      NegpDeleteContext(Context);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180030828  push    rbp
0x18003082a  push    rbx
0x18003082b  push    rsi
0x18003082c  push    rdi
0x18003082d  push    r12
0x18003082f  push    r13
0x180030831  push    r14
0x180030833  push    r15
0x180030835  sub     rsp, 268h
0x18003083c  lea     rbp, [rsp+70h]
0x180030841  mov     rax, cs:__security_cookie
0x180030848  xor     rax, rbp
0x18003084b  mov     [rbp+230h+var_50], rax
0x180030852  mov     rax, [rbp+230h+arg_28]
0x180030859  xor     esi, esi
0x18003085b  mov     r14, [rbp+230h+arg_20]
0x180030862  mov     r13, rdx
0x180030865  mov     r12, [rbp+230h+arg_30]
0x18003086c  mov     r15, rcx
0x18003086f  mov     [rbp+230h+var_168], rax
0x180030876  mov     rax, [rbp+230h+arg_38]
0x18003087d  mov     [rbp+230h+var_170], rax
0x180030884  mov     rax, [rbp+230h+arg_40]
0x18003088b  mov     [rbp+230h+var_198], rax
0x180030892  mov     rax, [rbp+230h+arg_48]
0x180030899  mov     [rbp+230h+var_190], rax
0x1800308a0  mov     rax, [rbp+230h+arg_50]
0x1800308a7  mov     [rbp+230h+var_208], r8d
0x1800308ab  lea     r8d, [rsi+68h]; Size
0x1800308af  mov     [rbp+230h+var_228], rdx
0x1800308b3  xor     edx, edx; Val
0x1800308b5  mov     [rbp+230h+var_178], rcx
0x1800308bc  lea     rcx, [rbp+230h+var_150]; void *
0x1800308c3  mov     [rbp+230h+var_188], rax
0x1800308ca  mov     [rbp+230h+var_1A0], r9d
0x1800308d1  mov     [rbp+230h+var_1C8], r14
0x1800308d5  mov     [rbp+230h+var_1D0], r12
0x1800308d9  mov     [rbp+230h+var_220], rsi
0x1800308dd  mov     [rbp+230h+var_1F0], rsi
0x1800308e1  call    memset_0
0x1800308e6  mov     rcx, cs:?SPNEGO_Module@@3PEAUtagASN1module_t@@EA; tagASN1module_t * SPNEGO_Module
0x1800308ed  lea     r12d, [rsi+2]
0x1800308f1  xorps   xmm1, xmm1
0x1800308f4  mov     [rbp+230h+var_218], rsi
0x1800308f8  xorps   xmm0, xmm0
0x1800308fb  mov     [rbp+230h+var_1E0], rsi
0x1800308ff  movups  xmmword ptr [rbp+230h+var_6C], xmm1
0x180030906  xor     eax, eax
0x180030908  xor     r9d, r9d
0x18003090b  movups  xmmword ptr [rbp+230h+var_AC], xmm1
0x180030912  xor     r8d, r8d
0x180030915  mov     [rbp+230h+var_230], r12d
0x180030919  lea     rdx, [rbp+230h+var_218]
0x18003091d  mov     [rbp+230h+var_1E8], rsi
0x180030921  movups  xmmword ptr [rbp+230h+var_6C+0Ch], xmm1
0x180030928  mov     dword ptr [rbp+230h+var_90], esi
0x18003092e  movups  xmmword ptr [rbp+230h+var_AC+0Ch], xmm1
0x180030935  mov     dword ptr [rbp+230h+var_C0], esi
0x18003093b  movups  xmmword ptr [rbp+230h+var_1B0.ulVersion], xmm0
0x180030942  mov     [rsp+2A0h+var_280], rsi
0x180030947  movups  [rbp+230h+var_90+4], xmm1
0x18003094e  movups  [rbp+230h+var_7C], xmm1
0x180030955  movups  xmmword ptr [rbp+230h+var_1C0.ulVersion], xmm0
0x180030959  movups  [rbp+230h+var_C0+4], xmm1
0x180030960  movups  [rbp+230h+var_160], xmm0
0x180030967  movups  xmmword ptr [rbp+230h+var_E0.dwLower], xmm1
0x18003096e  call    cs:__imp_ASN1_CreateEncoder
0x180030975  nop     dword ptr [rax+rax+00h]
0x18003097a  mov     ebx, eax
0x18003097c  lea     edi, [rsi+1]
0x18003097f  lea     rax, WPP_GLOBAL_Control
0x180030986  test    ebx, ebx
0x180030988  jnz     loc_180031B88
0x18003098e  mov     rcx, cs:?SPNEGO_Module@@3PEAUtagASN1module_t@@EA; tagASN1module_t * SPNEGO_Module
0x180030995  lea     rdx, [rbp+230h+var_1E0]
0x180030999  xor     r9d, r9d
0x18003099c  mov     [rsp+2A0h+var_280], rsi
0x1800309a1  xor     r8d, r8d
0x1800309a4  call    cs:__imp_ASN1_CreateDecoder
0x1800309ab  nop     dword ptr [rax+rax+00h]
0x1800309b0  mov     ebx, eax
0x1800309b2  test    eax, eax
0x1800309b4  jnz     loc_180031C8E
0x1800309ba  mov     r10, cs:WPP_GLOBAL_Control
0x1800309c1  mov     [rbp+230h+var_210], r15
0x1800309c5  mov     rsi, r13
0x1800309c8  mov     [rbp+230h+P], r13
0x1800309cc  test    r15, r15
0x1800309cf  jz      loc_180031CD3
0x1800309d5  xor     r8d, r8d
0x1800309d8  xor     edx, edx
0x1800309da  xor     edi, edi
0x1800309dc  mov     [rbp+230h+var_1F8], r8
0x1800309e0  xor     r13d, r13d
0x1800309e3  cmp     [r14+4], edx
0x1800309e7  jbe     loc_1800326EB
0x1800309ed  mov     esi, edx
0x1800309ef  mov     ebx, r13d
0x1800309f2  shl     rbx, 4
0x1800309f6  add     rbx, [r14+8]
0x1800309fa  mov     r15d, [rbx+4]
0x1800309fe  mov     eax, r15d
0x180030a01  and     eax, 0FFFFFFFh
0x180030a06  cmp     eax, r12d
0x180030a09  jnz     loc_180030ACE
0x180030a0f  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x180030a15  test    r8, r8
0x180030a18  mov     r12d, [rbx]
0x180030a1b  mov     rax, rbx
0x180030a1e  mov     r14, [rbx+8]
0x180030a22  cmovnz  rax, r8
0x180030a26  mov     [rbp+230h+var_1F8], rax
0x180030a2a  call    cs:__imp_TlsGetValue
0x180030a31  nop     dword ptr [rax+rax+00h]
0x180030a36  test    dword ptr [rbx+4], 40000000h
0x180030a3d  jnz     loc_180031CE9
0x180030a43  xor     edi, edi
0x180030a45  test    rsi, rsi
0x180030a48  jnz     short loc_180030A66
0x180030a4a  mov     r8, [rbp+230h+var_1F8]
0x180030a4e  lea     r12d, [rsi+2]
0x180030a52  mov     r14, [rbp+230h+var_1C8]
0x180030a56  mov     rdx, rbx
0x180030a59  mov     [rbp+230h+var_1F8], r8
0x180030a5d  inc     r13d
0x180030a60  cmp     r13d, [r14+4]
0x180030a64  jb      short loc_1800309EF
0x180030a66  mov     rsi, [rbp+230h+P]
0x180030a6a  test    edi, edi
0x180030a6c  js      loc_180031BFB
0x180030a72  cmp     [rbp+230h+var_1F8], 0
0x180030a77  jz      loc_1800326E4
0x180030a7d  mov     r12, [rbp+230h+var_1D0]
0x180030a81  xor     r8d, r8d
0x180030a84  xor     edx, edx
0x180030a86  mov     [rbp+230h+var_200], r8
0x180030a8a  xor     edi, edi
0x180030a8c  xor     r13d, r13d
0x180030a8f  cmp     [r12+4], edx
0x180030a94  ja      loc_180030BE5
0x180030a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030aa1  lea     rax, WPP_GLOBAL_Control
0x180030aa8  cmp     rcx, rax
0x180030aab  jz      short loc_180030AC8
0x180030aad  test    byte ptr [rcx+1Ch], 1
0x180030ab1  jz      short loc_180030AC8
0x180030ab3  mov     edx, 66h ; 'f'
0x180030ab8  mov     rcx, [rcx+10h]
0x180030abc  lea     r8, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids
0x180030ac3  call    WPP_SF_
0x180030ac8  mov     r13, [rbp+230h+var_228]
0x180030acc  jmp     short loc_180030AEF
0x180030ace  test    eax, eax
0x180030ad0  jnz     short loc_180030A5D
0x180030ad2  test    rdx, rdx
0x180030ad5  jnz     short loc_180030A66
0x180030ad7  mov     rsi, rbx
0x180030ada  jmp     short loc_180030A5D
0x180030adc  lea     rax, WPP_GLOBAL_Control
0x180030ae3  cmp     rcx, rax
0x180030ae6  jnz     loc_1800318DE
0x180030aec  mov     r13, rsi
0x180030aef  mov     edi, 80090308h
0x180030af4  mov     r14d, [rbp+230h+var_230]
0x180030af8  mov     rcx, [rbp+230h+var_218]
0x180030afc  test    rcx, rcx
0x180030aff  jz      short loc_180030B11
0x180030b01  mov     rdx, [rcx+10h]
0x180030b05  call    cs:__imp_ASN1_FreeEncoded
0x180030b0c  nop     dword ptr [rax+rax+00h]
0x180030b11  mov     rdx, [rbp+230h+var_1F0]
0x180030b15  test    rdx, rdx
0x180030b18  jnz     short loc_180030B23
0x180030b1a  mov     rdx, [rbp+230h+var_220]
0x180030b1e  test    rdx, rdx
0x180030b21  jz      short loc_180030B40
0x180030b23  mov     rcx, [rbp+230h+var_1E0]
0x180030b27  test    rcx, rcx
0x180030b2a  jz      short loc_180030B40
0x180030b2c  test    rdx, rdx
0x180030b2f  jz      short loc_180030B40
0x180030b31  mov     r8d, r14d
0x180030b34  call    cs:__imp_ASN1_FreeDecoded
0x180030b3b  nop     dword ptr [rax+rax+00h]
0x180030b40  mov     rax, qword ptr [rbp+230h+var_C0+8]
0x180030b47  cmp     rax, qword ptr [rbp+230h+var_160+8]
0x180030b4e  jnz     loc_180032714
0x180030b54  mov     rax, [rbp+230h+var_1E8]
0x180030b58  test    rax, rax
0x180030b5b  jnz     loc_18003273E
0x180030b61  mov     rcx, [rbp+230h+var_218]
0x180030b65  mov     rbx, [rbp+230h+var_1E0]
0x180030b69  test    rcx, rcx
0x180030b6c  jz      short loc_180030B7A
0x180030b6e  call    cs:__imp_ASN1_CloseEncoder
0x180030b75  nop     dword ptr [rax+rax+00h]
0x180030b7a  test    rbx, rbx
0x180030b7d  jz      short loc_180030B8E
0x180030b7f  mov     rcx, rbx
0x180030b82  call    cs:__imp_ASN1_CloseDecoder
0x180030b89  nop     dword ptr [rax+rax+00h]
0x180030b8e  test    edi, edi
0x180030b90  js      short loc_180030BB8
0x180030b92  mov     eax, edi
0x180030b94  mov     rcx, [rbp+230h+var_50]
0x180030b9b  xor     rcx, rbp; StackCookie
0x180030b9e  call    __security_check_cookie
0x180030ba3  lea     rsp, [rbp+1F8h]
0x180030baa  pop     r15
0x180030bac  pop     r14
0x180030bae  pop     r13
0x180030bb0  pop     r12
0x180030bb2  pop     rdi
0x180030bb3  pop     rsi
0x180030bb4  pop     rbx
0x180030bb5  pop     rbp
0x180030bb6  retn
0x180030bb8  test    rsi, rsi
0x180030bbb  jz      short loc_180030B92
0x180030bbd  lea     rbx, [rsi+18h]
0x180030bc1  cmp     qword ptr [rbx], 0
0x180030bc5  jz      short loc_180030BD6
0x180030bc7  mov     rcx, rbx; struct _SecHandle *
0x180030bca  call    ?WLsaDeleteContext@@YAJPEAU_SecHandle@@@Z; WLsaDeleteContext(_SecHandle *)
0x180030bcf  mov     qword ptr [rbx], 0
0x180030bd6  test    r13, r13
0x180030bd9  jnz     short loc_180030B92
0x180030bdb  mov     rcx, rsi; P
0x180030bde  call    ?NegpDeleteContext@@YAXPEAU_NEG_CONTEXT@@@Z; NegpDeleteContext(_NEG_CONTEXT *)
0x180030be3  jmp     short loc_180030B92
0x180030be5  mov     rsi, rdx
0x180030be8  mov     ebx, r13d
0x180030beb  shl     rbx, 4
0x180030bef  add     rbx, [r12+8]
0x180030bf4  mov     r15d, [rbx+4]
0x180030bf8  mov     eax, r15d
0x180030bfb  and     eax, 0FFFFFFFh
0x180030c00  cmp     eax, 2
0x180030c03  jnz     loc_18003185B
0x180030c09  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x180030c0f  test    r8, r8
0x180030c12  mov     r12d, [rbx]
0x180030c15  mov     rax, rbx
0x180030c18  mov     r14, [rbx+8]
0x180030c1c  cmovnz  rax, r8
0x180030c20  mov     [rbp+230h+var_200], rax
0x180030c24  call    cs:__imp_TlsGetValue
0x180030c2b  nop     dword ptr [rax+rax+00h]
0x180030c30  test    dword ptr [rbx+4], 40000000h
0x180030c37  jnz     loc_180031D75
0x180030c3d  xor     edi, edi
0x180030c3f  mov     r12, [rbp+230h+var_1D0]
0x180030c43  test    rsi, rsi
0x180030c46  jnz     loc_1800318D4
0x180030c4c  mov     r8, [rbp+230h+var_200]
0x180030c50  mov     rdx, rbx
0x180030c53  mov     [rbp+230h+var_200], r8
0x180030c57  mov     ebx, 1
0x180030c5c  add     r13d, ebx
0x180030c5f  cmp     r13d, [r12+4]
0x180030c64  jb      short loc_180030BE8
0x180030c66  mov     rsi, [rbp+230h+P]
0x180030c6a  test    edi, edi
0x180030c6c  js      loc_180031A0B
0x180030c72  mov     r10, [rbp+230h+var_200]
0x180030c76  test    r10, r10
0x180030c79  jz      loc_180030A9A
0x180030c7f  mov     r9, [rbp+230h+var_1C8]
0x180030c83  xor     edx, edx
0x180030c85  mov     [rbp+230h+P], 0
0x180030c8d  mov     r11d, 0FFFFFFFh
0x180030c93  cmp     edx, [r9+4]
0x180030c97  jnb     short loc_180030CB8
0x180030c99  mov     r8d, edx
0x180030c9c  shl     r8, 4
0x180030ca0  add     r8, [r9+8]
0x180030ca4  mov     eax, [r8+4]
0x180030ca8  and     eax, r11d
0x180030cab  cmp     eax, 0Eh
0x180030cae  jz      short loc_180030CB4
0x180030cb0  add     edx, ebx
0x180030cb2  jmp     short loc_180030C93
0x180030cb4  mov     [rbp+230h+P], r8
0x180030cb8  xor     r13d, r13d
0x180030cbb  mov     [rbp+230h+var_1C8], r13
0x180030cbf  xor     edx, edx
0x180030cc1  cmp     edx, [r12+4]
0x180030cc6  jnb     short loc_180030CEB
0x180030cc8  mov     r8d, edx
0x180030ccb  shl     r8, 4
0x180030ccf  add     r8, [r12+8]
0x180030cd4  mov     eax, [r8+4]
0x180030cd8  and     eax, r11d
0x180030cdb  cmp     eax, 1Eh
0x180030cde  jz      short loc_180030CE4
0x180030ce0  add     edx, ebx
0x180030ce2  jmp     short loc_180030CC1
0x180030ce4  mov     r13, r8
0x180030ce7  mov     [rbp+230h+var_1C8], r8
0x180030ceb  mov     r12, [rbp+230h+var_1F8]
  ... truncated ...
```
