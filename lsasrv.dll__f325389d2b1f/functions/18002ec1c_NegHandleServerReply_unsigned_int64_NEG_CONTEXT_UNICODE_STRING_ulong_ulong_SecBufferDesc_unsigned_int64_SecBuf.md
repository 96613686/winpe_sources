# NegHandleServerReply(unsigned __int64,_NEG_CONTEXT *,_UNICODE_STRING *,ulong,ulong,_SecBufferDesc *,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x18002ec1c`
- end: `0x1800305ee`
- name: `?NegHandleServerReply@@YAJ_KPEAU_NEG_CONTEXT@@PEAU_UNICODE_STRING@@KKPEAU_SecBufferDesc@@PEA_K3PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `6610`
- prototype: `__int64 __fastcall(unsigned __int64, struct _NEG_CONTEXT *, struct _UNICODE_STRING *, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned __int64 *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009c208`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x180019e18`
- `0x180024338`
- `0x18002b8a0`
- `0x18002da8c`
- `0x18002ec1c`
- `0x180030808`
- `0x18003275c`
- `0x1800975ac`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x1800c7e28`
- `0x1800c8300`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ed3f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ee21`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002eff7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f2e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f3cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003009a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ed3f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ee21`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002eff7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f2e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f3cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003009a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002f480`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800300bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002f480`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800300bb`
- `ntdll!RtlFreeHeap` at `0x18002eec5`
- `ntdll!RtlFreeHeap` at `0x18002eec5`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f200`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f829`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f200`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f829`
- `ntdll!RtlEnterCriticalSection` at `0x18002f1dd`
- `ntdll!RtlEnterCriticalSection` at `0x18002f602`
- `ntdll!RtlEnterCriticalSection` at `0x18002f1dd`
- `ntdll!RtlEnterCriticalSection` at `0x18002f602`
- `MSASN1!ASN1_FreeEncoded` at `0x18002eeef`
- `MSASN1!ASN1_FreeEncoded` at `0x18002eeef`
- `MSASN1!ASN1_Encode` at `0x18002f6f8`
- `MSASN1!ASN1_Encode` at `0x18002f6f8`
- `MSASN1!ASN1_CreateEncoder` at `0x18002ed75`
- `MSASN1!ASN1_CreateEncoder` at `0x18002ed75`
- `MSASN1!ASN1_CreateDecoder` at `0x18002edae`
- `MSASN1!ASN1_CreateDecoder` at `0x18002f0d2`
- `MSASN1!ASN1_CreateDecoder` at `0x18002edae`
- `MSASN1!ASN1_CreateDecoder` at `0x18002f0d2`
- `MSASN1!ASN1_CloseEncoder` at `0x18002ef31`
- `MSASN1!ASN1_CloseEncoder` at `0x18002ef31`
- `MSASN1!ASN1_CloseDecoder` at `0x18002ef45`
- `MSASN1!ASN1_CloseDecoder` at `0x18002f138`
- `MSASN1!ASN1_CloseDecoder` at `0x18002ef45`
- `MSASN1!ASN1_CloseDecoder` at `0x18002f138`
- `MSASN1!ASN1_Decode` at `0x18002f112`
- `MSASN1!ASN1_Decode` at `0x18002f112`
- `MSASN1!ASN1_FreeDecoded` at `0x18002ef18`
- `MSASN1!ASN1_FreeDecoded` at `0x18002ef18`

## pseudocode

```c
__int64 __fastcall NegHandleServerReply(
        struct _RTL_CRITICAL_SECTION *a1,
        struct _NEG_CONTEXT *a2,
        struct _UNICODE_STRING *a3,
        unsigned int a4,
        unsigned int a5,
        struct _SecBufferDesc *a6,
        unsigned __int64 *a7,
        struct _SecBufferDesc *a8,
        unsigned int *a9,
        union _LARGE_INTEGER *a10,
        unsigned __int8 *a11,
        struct _SecBuffer *a12)
{
  int v12; // r13d
  struct _SecBufferDesc *v13; // rsi
  unsigned int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // r9
  LsaHandleCache *v18; // r10
  __int64 v19; // r8
  __int64 v20; // rdx
  signed int v21; // edi
  __int64 v22; // r14
  struct _SecBuffer *v23; // rbx
  unsigned int BufferType; // r15d
  __int64 cbBuffer; // r12
  __int64 v26; // rax
  struct _RTL_BALANCED_NODE *pvBuffer; // rsi
  _DWORD *v28; // rax
  struct _SecBufferDesc *v29; // r12
  int v30; // r13d
  _OWORD *v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rbx
  struct _RTL_BALANCED_NODE *v35; // rcx
  __int64 v36; // r14
  struct _SecBuffer *v37; // rbx
  unsigned int v38; // r15d
  __int64 v39; // r12
  unsigned int *p_cbBuffer; // rax
  struct _RTL_BALANCED_NODE *v41; // rsi
  _DWORD *v42; // rax
  struct _NEG_CONTEXT *v43; // r14
  int v44; // r15d
  __int64 v45; // rsi
  unsigned int v46; // eax
  unsigned int v47; // ebx
  int v48; // eax
  __int16 v49; // r12
  __int16 v50; // ax
  int v51; // ecx
  struct _RTL_CRITICAL_SECTION *v52; // rdi
  __int64 v53; // r15
  __int64 v54; // r13
  __int128 v55; // xmm0
  __int64 v56; // rax
  void *v57; // r12
  int v58; // ecx
  LsaHandleCache *v59; // rcx
  unsigned int v60; // edi
  int v61; // r8d
  _DWORD *v62; // r9
  unsigned int v63; // ecx
  int v64; // eax
  struct _SecBuffer v65; // xmm0
  union _LARGE_INTEGER *v66; // rax
  unsigned int *v67; // r13
  unsigned int v68; // r10d
  char v69; // cl
  unsigned int v70; // edx
  __int64 *v71; // rcx
  __int64 *v72; // rax
  unsigned int v73; // r8d
  __int16 *v74; // rdx
  int v75; // eax
  unsigned int v76; // ebx
  int v77; // eax
  __int64 v78; // r10
  signed int v79; // ebx
  unsigned int v80; // eax
  __int64 v81; // rax
  char v82; // cl
  unsigned __int8 v83; // al
  int v84; // eax
  int v85; // eax
  int v86; // eax
  __int64 v87; // rcx
  __int64 v88; // rdx
  int v89; // eax
  int v90; // eax
  bool v91; // zf
  LsaHandleCache *v92; // rcx
  __int64 v93; // rdx
  __int64 v94; // rcx
  LsaHandleCache *v95; // rcx
  LsaHandleCache *v96; // r10
  void *v97; // rax
  const void *v98; // rdx
  int v99; // ecx
  __int64 v100; // rdx
  struct _RTL_BALANCED_NODE *v101; // rax
  int v102; // eax
  struct _RTL_BALANCED_NODE *v103; // rax
  int v104; // eax
  LsaHandleCache *v105; // rcx
  __int64 v106; // rdx
  LsaHandleCache *v107; // rcx
  void *v108; // rbx
  struct _RTL_BALANCED_NODE *v109; // rcx
  __int64 v110; // rdx
  LsaHandleCache *v111; // rcx
  __int64 v112; // rdx
  void *v113; // rax
  char v114; // [rsp+70h] [rbp-90h]
  _OWORD *v115; // [rsp+78h] [rbp-88h]
  unsigned __int8 v116[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v117; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v118; // [rsp+88h] [rbp-78h] BYREF
  __int64 v119; // [rsp+90h] [rbp-70h] BYREF
  __int64 v120; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v121; // [rsp+A0h] [rbp-60h]
  struct _RTL_CRITICAL_SECTION *v122; // [rsp+A8h] [rbp-58h]
  unsigned int v123; // [rsp+B0h] [rbp-50h]
  unsigned int v124; // [rsp+B4h] [rbp-4Ch]
  struct _NEG_CONTEXT *v125; // [rsp+B8h] [rbp-48h]
  struct _SecBufferDesc *v126; // [rsp+C0h] [rbp-40h]
  _OWORD v127[2]; // [rsp+C8h] [rbp-38h] BYREF
  struct _SecBufferDesc v128; // [rsp+E8h] [rbp-18h] BYREF
  struct _SecBufferDesc v129; // [rsp+F8h] [rbp-8h] BYREF
  union _LARGE_INTEGER *v130; // [rsp+108h] [rbp+8h]
  __int64 v131; // [rsp+110h] [rbp+10h] BYREF
  struct _SecBuffer v132; // [rsp+118h] [rbp+18h] BYREF
  struct _SecBufferDesc *v133; // [rsp+128h] [rbp+28h]
  struct _UNICODE_STRING *v134; // [rsp+130h] [rbp+30h]
  _DWORD *Value; // [rsp+138h] [rbp+38h]
  unsigned int *v136; // [rsp+140h] [rbp+40h]
  unsigned __int8 *v137; // [rsp+148h] [rbp+48h]
  struct _SecBuffer *v138; // [rsp+150h] [rbp+50h]
  __int128 v139; // [rsp+158h] [rbp+58h] BYREF
  __int16 v140; // [rsp+170h] [rbp+70h] BYREF
  __int16 v141; // [rsp+178h] [rbp+78h]
  BOOL v142; // [rsp+17Ch] [rbp+7Ch]
  int v143; // [rsp+188h] [rbp+88h]
  __int64 v144; // [rsp+190h] [rbp+90h]
  int v145; // [rsp+198h] [rbp+98h]
  __int64 v146; // [rsp+1A0h] [rbp+A0h]
  struct ASN1objectidentifier_s *v147; // [rsp+1E0h] [rbp+E0h] BYREF
  __int16 v148; // [rsp+1E8h] [rbp+E8h]
  __int16 v149; // [rsp+1F0h] [rbp+F0h]
  __int128 *v150; // [rsp+1F8h] [rbp+F8h]
  int v151; // [rsp+210h] [rbp+110h]
  __int64 v152; // [rsp+218h] [rbp+118h]
  struct _SecHandle v153; // [rsp+250h] [rbp+150h] BYREF
  struct _SecHandle v154; // [rsp+260h] [rbp+160h] BYREF
  _OWORD v155[4]; // [rsp+270h] [rbp+170h] BYREF

  v12 = 0;
  v13 = a6;
  v136 = a9;
  v130 = a10;
  v137 = a11;
  v134 = a3;
  v125 = a2;
  v122 = a1;
  v138 = a12;
  v124 = a4;
  v126 = a6;
  v133 = a8;
  v119 = 0;
  memset_0(&v140, 0, 0x68u);
  memset_0(&v147, 0, 0x70u);
  v120 = 0;
  v131 = 0;
  v123 = a4 | 0x10000;
  memset(v155, 0, sizeof(v155));
  v153.dwLower = 0;
  v153.dwUpper = 0;
  v117 = 0;
  v128 = 0;
  memset(v127, 0, sizeof(v127));
  v129 = 0;
  v115 = 0;
  v154 = 0;
  Value = TlsGetValue(dwCallInfo);
  v139 = 0;
  if ( (a4 & 0x10000) == 0 && (a4 & 0x800000) != 0 )
    v123 = a4 & 0xFFFEFFFF;
  v15 = ASN1_CreateEncoder(SPNEGO_Module, &v120, 0, 0, 0);
  v16 = v15;
  if ( v15 )
  {
    v96 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v100 = 10;
LABEL_235:
      WPP_SF_d(*((_QWORD *)v96 + 2), v100, WPP_a36b0360a7043644a5a822ee72241678_Traceguids, v15);
    }
  }
  else
  {
    v15 = ASN1_CreateDecoder(SPNEGO_Module, &v131, 0, 0, 0);
    v16 = v15;
    if ( !v15 )
    {
      v18 = WPP_GLOBAL_Control;
      goto LABEL_5;
    }
    v96 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v100 = 11;
      goto LABEL_235;
    }
  }
  v21 = SpnegoAsnErrorToSecStatus(v16);
  if ( v21 < 0 )
  {
    v31 = 0;
    goto LABEL_20;
  }
LABEL_5:
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v118 = 0;
  if ( !a6->cBuffers )
    goto LABEL_368;
  v17 = 2;
  v22 = 0;
  while ( 1 )
  {
    v23 = &v13->pBuffers[v12];
    BufferType = v23->BufferType;
    if ( (BufferType & 0xFFFFFFF) == 2 )
    {
      cbBuffer = v23->cbBuffer;
      v26 = (__int64)&v13->pBuffers[v12];
      pvBuffer = (struct _RTL_BALANCED_NODE *)v23->pvBuffer;
      if ( v19 )
        v26 = v19;
      v118 = v26;
      v28 = TlsGetValue(dwCallInfo);
      if ( (v23->BufferType & 0x40000000) != 0 && v23->cbBuffer )
      {
        if ( (v23->BufferType & 0x20000000) == 0 )
        {
          v101 = (struct _RTL_BALANCED_NODE *)LsapAllocate(cbBuffer);
          pvBuffer = v101;
          if ( !v101 )
          {
            v21 = -1073741801;
            goto LABEL_12;
          }
          v102 = LsapCopyFromClient(v23->pvBuffer, v101, (unsigned int)cbBuffer);
          v21 = v102;
          if ( v102 < 0 )
          {
            if ( v102 == -1073741819 )
              v21 = -1073741811;
            LsapSubProv_FreeRoutine(pvBuffer, (void *)v20);
            goto LABEL_12;
          }
          goto LABEL_239;
        }
        v21 = (v28[8] & 1) == 0 ? 0xC0000005 : 0;
        if ( (v28[8] & 1) != 0 )
        {
LABEL_239:
          v23->cbBuffer = cbBuffer;
          v23->BufferType = BufferType & 0xBFFFFFFF;
          v23->pvBuffer = pvBuffer;
        }
      }
      else
      {
        v21 = 0;
      }
LABEL_12:
      if ( v22 )
        goto LABEL_15;
      v19 = v118;
      v17 = 2;
      v13 = v126;
      v20 = (__int64)v23;
      goto LABEL_14;
    }
    if ( (BufferType & 0xFFFFFFF) == 0 )
      break;
LABEL_14:
    if ( ++v12 >= v13->cBuffers )
      goto LABEL_15;
  }
  if ( !v20 )
  {
    v22 = (__int64)&v13->pBuffers[v12];
    goto LABEL_14;
  }
LABEL_15:
  if ( v21 < 0 )
  {
    v92 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v93 = 129;
LABEL_246:
    v94 = *((_QWORD *)v92 + 2);
LABEL_210:
    WPP_SF_d(v94, v93, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids, (unsigned int)v21);
    goto LABEL_19;
  }
  if ( !v118 )
  {
    v18 = WPP_GLOBAL_Control;
LABEL_368:
    if ( v18 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 1) == 0 )
      goto LABEL_18;
    v88 = 130;
    goto LABEL_371;
  }
  v29 = v133;
  v19 = 0;
  v20 = 0;
  v121 = 0;
  v21 = 0;
  v30 = 0;
  if ( !v133->cBuffers )
    goto LABEL_18;
  v36 = 0;
  while ( 2 )
  {
    v37 = &v29->pBuffers[v30];
    v38 = v37->BufferType;
    if ( (v38 & 0xFFFFFFF) == 2 )
    {
      v39 = v37->cbBuffer;
      p_cbBuffer = &v37->cbBuffer;
      v41 = (struct _RTL_BALANCED_NODE *)v37->pvBuffer;
      if ( v19 )
        p_cbBuffer = (unsigned int *)v19;
      v121 = p_cbBuffer;
      v42 = TlsGetValue(dwCallInfo);
      if ( (v37->BufferType & 0x40000000) != 0 && v37->cbBuffer )
      {
        if ( (v37->BufferType & 0x20000000) != 0 )
        {
          v21 = (v42[8] & 1) == 0 ? 0xC0000005 : 0;
          if ( (v42[8] & 1) != 0 )
            goto LABEL_250;
        }
        else
        {
          v103 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v39);
          v41 = v103;
          if ( v103 )
          {
            v104 = LsapCopyFromClient(v37->pvBuffer, v103, (unsigned int)v39);
            v21 = v104;
            if ( v104 >= 0 )
            {
LABEL_250:
              v37->cbBuffer = v39;
              v37->BufferType = v38 & 0xBFFFFFFF;
              v37->pvBuffer = v41;
            }
            else
            {
              if ( v104 == -1073741819 )
                v21 = -1073741811;
              LsapSubProv_FreeRoutine(v41, (void *)v20);
            }
          }
          else
          {
            v21 = -1073741801;
          }
        }
      }
      else
      {
        v21 = 0;
      }
      if ( v36 )
        goto LABEL_50;
      v19 = (__int64)v121;
      v20 = (__int64)v37;
      v29 = v133;
LABEL_49:
      if ( ++v30 >= v29->cBuffers )
        goto LABEL_50;
      continue;
    }
    break;
  }
  if ( (v38 & 0xFFFFFFF) != 0 )
    goto LABEL_49;
  if ( !v20 )
  {
    v36 = (__int64)&v29->pBuffers[v30];
    goto LABEL_49;
  }
LABEL_50:
  v43 = v125;
  if ( v21 < 0 )
  {
    v92 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v93 = 131;
    goto LABEL_246;
  }
  if ( !v121 )
  {
LABEL_18:
    v21 = -2146893048;
LABEL_19:
    v31 = v115;
LABEL_20:
    if ( *((_QWORD *)&v127[0] + 1) )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)&v127[0] + 1));
      *((_QWORD *)&v127[0] + 1) = 0;
    }
    if ( v31 )
    {
      v35 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)v31 + 1);
      if ( v35 )
        LsapSubProv_FreeRoutine(v35, (void *)v20);
    }
    if ( v120 )
      ASN1_FreeEncoded(v120, *(_QWORD *)(v120 + 16));
    v32 = v119;
    if ( v119 && v131 )
      ASN1_FreeDecoded(v131, v119, 1);
    v33 = v131;
    if ( v120 )
      ASN1_CloseEncoder(v120, v32, v19, v17);
    if ( v33 )
      ASN1_CloseDecoder(v33, v32);
    if ( v21 == -1073740755 )
      return (unsigned int)-2146893042;
    return (unsigned int)v21;
  }
  if ( !v125 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
    v21 = -2146893055;
    goto LABEL_19;
  }
  v20 = 0;
  v125 = 0;
  while ( (unsigned int)v20 < v126->cBuffers )
  {
    v19 = (__int64)&v126->pBuffers[(unsigned int)v20];
    if ( (*(_DWORD *)(v19 + 4) & 0xFFFFFFF) == 0xE )
    {
      v125 = (struct _NEG_CONTEXT *)&v126->pBuffers[(unsigned int)v20];
      break;
    }
    v20 = (unsigned int)(v20 + 1);
  }
  if ( !v122 )
    v122 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v43 + 1);
  v17 = v118;
  v118 = 0;
  v44 = *(_DWORD *)v17;
  if ( !*(_DWORD *)v17 || (v45 = *(_QWORD *)(v17 + 8)) == 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a36b0360a7043644a5a822ee72241678_Traceguids);
      v18 = WPP_GLOBAL_Control;
    }
    v21 = -2146893048;
LABEL_207:
    if ( v18 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 1) == 0 )
      goto LABEL_19;
    v94 = *((_QWORD *)v18 + 2);
    v93 = 133;
    goto LABEL_210;
  }
  v21 = 0;
  v46 = ASN1_CreateDecoder(SPNEGO_Module, &v118, 0, 0, 0);
  v47 = v46;
  if ( v46 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a36b0360a7043644a5a822ee72241678_Traceguids, v46);
    v21 = SpnegoAsnErrorToSecStatus(v47);
    if ( v21 < 0 )
      goto LABEL_207;
  }
  v119 = 0;
  v48 = ASN1_Decode(v118, &v119, 1, 8, v45, v44);
  v20 = (unsigned int)v48;
  if ( v48 >= 0 )
  {
    v18 = WPP_GLOBAL_Control;
    goto LABEL_65;
  }
  v21 = SpnegoAsnErrorToSecStatus((unsigned int)v48);
  if ( (_DWORD)v20 == -1009 || (_DWORD)v20 == -1002 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a36b0360a7043644a5a822ee72241678_Traceguids, 1);
      goto LABEL_191;
    }
  }
  else
  {
LABEL_191:
    v18 = WPP_GLOBAL_Control;
  }
  v119 = 0;
LABEL_65:
  if ( v118 )
  {
    ASN1_CloseDecoder(v118, v20);
    v18 = WPP_GLOBAL_Control;
  }
  if ( v21 < 0 )
    goto LABEL_207;
  v19 = 2;
  if ( *(_WORD *)v119 != 2 )
  {
    if ( v18 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 1) == 0 )
      goto LABEL_18;
    v88 = 134;
    goto LABEL_371;
  }
  v49 = 128;
  v20 = v119;
  v114 = 0;
  v50 = *(_WORD *)(v119 + 8);
  if ( (v50 & 0x80) == 0 )
  {
    if ( (*((_DWORD *)v43 + 24) & 0x200) != 0 )
      goto LABEL_74;
    if ( v18 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 1) == 0 )
      goto LABEL_18;
    v88 = 136;
LABEL_371:
    WPP_SF_(*((_QWORD *)v18 + 2), v88, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
    goto LABEL_18;
  }
  v51 = *(_DWORD *)(v119 + 12);
  if ( v51 == 2 )
  {
    if ( v18 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v18 + 2), 135, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
    v21 = -2146893044;
    goto LABEL_19;
  }
  if ( v51 )
  {
    if ( v51 == 3 )
    {
      *((_DWORD *)v43 + 24) |= 0x2000u;
      v50 = *(_WORD *)(v20 + 8);
      v18 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v114 = 1;
  }
LABEL_74:
  if ( (v50 & 0x40) != 0 )
  {
    if ( (*((_DWORD *)v43 + 24) & 0x200) != 0 )
      goto LABEL_76;
    v52 = v122;
    RtlEnterCriticalSection(v122 + 1);
    v70 = 0;
LABEL_127:
    if ( v70 >= HIDWORD(v52[2].SpinCount) )
    {
      v53 = -1;
    }
    else
    {
      v53 = v70;
      v71 = *(__int64 **)(*((_QWORD *)&v52[3].LockSemaphore + 4 * v70) + 24LL);
      v72 = *(__int64 **)(v119 + 16);
      while ( v72 )
      {
        v73 = *((_DWORD *)v72 + 2);
        if ( v73 < *((_DWORD *)v71 + 2) || v73 > *((_DWORD *)v71 + 2) )
          goto LABEL_134;
        v72 = (__int64 *)*v72;
        v71 = (__int64 *)*v71;
        if ( !v72 )
        {
          if ( v71 )
          {
LABEL_134:
            ++v70;
            goto LABEL_127;
          }
          break;
        }
        if ( !v71 )
          goto LABEL_134;
      }
    }
    v54 = *((_QWORD *)&v52[3].LockSemaphore + 4 * v53);
    RtlLeaveCriticalSection(v52 + 1);
    if ( v53 == -1 )
      goto LABEL_18;
    v85 = *((_DWORD *)v43 + 24);
    if ( (v85 & 0x200) != 0 && *((_QWORD *)v43 + 2) != v53 )
    {
      v21 = -2146893048;
      v105 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v106 = 138;
LABEL_279:
      WPP_SF_(*((_QWORD *)v105 + 2), v106, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
      goto LABEL_19;
    }
    v86 = v85 | 0x200;
    *((_DWORD *)v43 + 24) = v86;
    if ( *((_QWORD *)v43 + 2) != v53 )
    {
      *((_DWORD *)v43 + 24) = v86 | 0x2000;
      if ( (*(_BYTE *)(v119 + 8) & 0x20) != 0 )
      {
        v21 = -2146893048;
        v105 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_19;
        }
        v106 = 139;
        goto LABEL_279;
      }
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        140,
        WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids,
        *(_QWORD *)(v54 + 16) + 48LL);
LABEL_78:
      v18 = WPP_GLOBAL_Control;
    }
    v20 = v119;
    LODWORD(v19) = 0;
    v128.pBuffers = (PSecBuffer)v155;
    *(_QWORD *)&v128.ulVersion = 0;
    v129.ulVersion = 0;
    v129.pBuffers = (PSecBuffer)v127;
    v129.cBuffers = 1;
    v127[0] = 0x200000000uLL;
    if ( (*(_BYTE *)(v119 + 8) & 0x20) != 0 )
    {
      v91 = *((_DWORD *)v43 + 21) == 590610;
      v19 = 1;
      v128.cBuffers = 1;
      *((_QWORD *)&v155[0] + 1) = *(_QWORD *)(v119 + 32);
      LODWORD(v155[0]) = *(_DWORD *)(v119 + 24);
      DWORD1(v155[0]) = 2;
      if ( !v91 )
      {
        if ( v18 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 1) == 0 )
          goto LABEL_18;
        v88 = 145;
        goto LABEL_371;
      }
    }
    v55 = *(_OWORD *)((char *)v43 + 120);
    v19 = (unsigned int)(v19 + 1);
    v126 = 0;
    v128.cBuffers = v19;
    v155[(unsigned int)(v19 - 1)] = v55;
    if ( (*(_BYTE *)(v20 + 8) & 0x10) != 0 )
    {
      v20 = v119;
      if ( *(_DWORD *)(v119 + 40) )
      {
        v87 = (unsigned int)v19;
        v17 = (__int64)&v155[v87];
        v128.cBuffers = v19 + 1;
        v91 = *((_DWORD *)v43 + 21) == 590610;
        *((_QWORD *)&v155[v87] + 1) = *(_QWORD *)(v119 + 48);
        LODWORD(v155[v87]) = *(_DWORD *)(v20 + 40);
        DWORD1(v155[v87]) = 12;
        v126 = (struct _SecBufferDesc *)&v155[v87];
        if ( !v91 )
        {
          if ( v18 == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 1) == 0 )
            goto LABEL_18;
          v88 = 146;
          goto LABEL_371;
        }
      }
    }
    LODWORD(v118) = 1;
    if ( v18 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x1000) != 0 )
    {
      WPP_SF_Z(*((_QWORD *)v18 + 2), 147, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids, *(_QWORD *)(v54 + 16) + 48LL);
      v18 = WPP_GLOBAL_Control;
    }
    v56 = *((_QWORD *)v43 + 2);
    if ( v56 == v53 || (*((_BYTE *)v43 + 96) & 1) == 0 )
    {
      v153 = *(struct _SecHandle *)((char *)v43 + 24);
    }
    else
    {
      if ( v18 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x1000) != 0 )
        WPP_SF_Z(
          *((_QWORD *)v18 + 2),
          148,
          WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids,
          *(_QWORD *)(*((_QWORD *)&v52[3].LockSemaphore + 4 * v56) + 16LL) + 48LL);
      v108 = TlsGetValue(dwThreadPackage);
      WLsaDeleteContext((struct _SecHandle *)((char *)v43 + 24));
      TlsSetValue(dwThreadPackage, v108);
      v109 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)v43 + 9);
      *((_DWORD *)v43 + 24) &= ~1u;
      if ( v109 )
      {
        LsapSubProv_FreeRoutine(v109, (void *)v20);
        *((_QWORD *)v43 + 9) = 0;
        *((_DWORD *)v43 + 16) = 0;
      }
      *((_BYTE *)v43 + 80) = 0;
      *((_QWORD *)v43 + 2) = v53;
      *((_DWORD *)v43 + 21) = 590610;
      v18 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)v43 + 21) == 590610 )
    {
      v116[0] = 0;
      *(_QWORD *)&v132.cbBuffer = 0;
      v132.pvBuffer = 0;
      v57 = TlsGetValue(dwThreadPackage);
      v129.ulVersion = 0;
      v129.pBuffers = (PSecBuffer)v127;
      v129.cBuffers = 1;
      v127[0] = 0x200000000uLL;
      if ( v125 )
        v155[v128.cBuffers++] = *(_OWORD *)v125;
      v58 = *((_DWORD *)v43 + 24) & 0x4400;
      if ( !v58 )
      {
        v129.cBuffers = 2;
        DWORD1(v127[1]) = 12;
      }
      v31 = &v127[1];
      if ( v58 )
        v31 = 0;
      v115 = v31;
      v59 = WPP_GLOBAL_Control;
      v19 = (__int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          149,
          WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids,
          *(_QWORD *)(v54 + 16) + 48LL);
        v59 = WPP_GLOBAL_Control;
        v19 = (__int64)&WPP_GLOBAL_Control;
      }
      v20 = (__int64)Value;
      v17 = 0x8000;
      v117 = 0;
      v154 = (struct _SecHandle)*((_OWORD *)&v52[3].SpinCount + 2 * v53);
      if ( Value && (*(_DWORD *)(*(_QWORD *)(v54 + 16) + 16LL) & 0x100000) != 0 )
      {
        Value[8] |= 0x8000u;
        v59 = WPP_GLOBAL_Control;
      }
      if ( (BYTE4(v52->LockSemaphore) & 0x20) != 0 && v20 && (*(_DWORD *)(v20 + 32) & 0x8000) == 0 )
      {
        v21 = -2146893042;
        if ( v59 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v59 + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)v59 + 2), 150, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
        goto LABEL_20;
      }
      v60 = v123 | 0x100;
      v62 = TlsGetValue(dwSession);
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_DiiiiZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v153.dwUpper,
          v61,
          v62[4],
          v154.dwUpper,
          v154.dwLower,
          v153.dwUpper,
          v153.dwLower,
          (__int64)v43 + 40);
      }
      v21 = WLsaProcessContext(
              1,
              &v154,
              &v153,
              (struct _UNICODE_STRING *)((char *)v43 + 40),
              &v128,
              v60,
              a5,
              (struct _SecHandle *)((char *)v43 + 24),
              &v129,
              &v117,
              v130,
              v116,
              &v132);
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_ZD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          151,
          (unsigned int)WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids,
          *(_QWORD *)(*((_QWORD *)&v122[3].LockSemaphore + 4 * v53) + 16LL) + 48,
          v21);
      }
      TlsSetValue(dwThreadPackage, v57);
      v17 = 1;
      *((_DWORD *)v43 + 21) = v21;
      ++*((_BYTE *)v43 + 81);
      if ( v21 < 0 )
        goto LABEL_19;
      if ( v21 || (*((_DWORD *)v43 + 24) & 0x1800) != 0 )
      {
        v63 = v117;
      }
      else
      {
        v63 = v117 | 0x2000000;
        v117 |= 0x2000000u;
      }
      v19 = LODWORD(v127[0]);
      if ( (v63 & 0x2000000) != 0 )
      {
        v89 = *((_DWORD *)v43 + 24);
        v63 &= ~0x2000000u;
        v117 = v63;
        if ( LODWORD(v127[0]) )
        {
          v90 = v89 | 0x1000;
          v91 = v31 == 0;
        }
        else
        {
          v90 = v89 | 0x800;
          v91 = v126 == 0;
        }
        *((_DWORD *)v43 + 24) = v90;
        if ( v91 )
          *((_DWORD *)v43 + 24) = v90 | 0x4000;
      }
      if ( (v63 & 0x8000000) != 0 && (*(_BYTE *)(v54 + 40) & 2) == 0 )
      {
        *((_QWORD *)&v139 + 1) = *(_QWORD *)(v54 + 24);
        LODWORD(v118) = 2;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
          v63 = v117;
          v17 = 1;
          v19 = LODWORD(v127[0]);
        }
        v63 &= ~0x8000000u;
        v117 = v63;
      }
      v64 = *((_DWORD *)v43 + 24) | 1;
      v91 = (v124 & 0x100) == 0;
      *((_DWORD *)v43 + 24) = v64;
      if ( v91 )
      {
        v63 &= ~0x100u;
        v117 = v63;
      }
      v20 = 10240;
      *((_DWORD *)v43 + 14) = v63;
      if ( (v64 & 0x2800) == 0x2800 )
      {
        v20 = v119;
        if ( ((*(_BYTE *)(v119 + 8) & 0x10) == 0 || !*(_DWORD *)(v119 + 40))
          && !NegAcceptUnsafeUnprotectedNegotiation
          && (v63 & 0x10010) != 0 )
        {
          v95 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_219;
          }
          v110 = 153;
          goto LABEL_319;
        }
      }
      if ( v116[0] )
      {
        if ( *((_BYTE *)v43 + 80) )
        {
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
          }
          v21 = -2146893052;
          LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v132.pvBuffer, (void *)v20);
          goto LABEL_20;
        }
        v65 = v132;
        *((_BYTE *)v43 + 80) = v116[0];
        v66 = v130;
        *((struct _SecBuffer *)v43 + 4) = v65;
        *((union _LARGE_INTEGER *)v43 + 11) = *v66;
      }
      v67 = v121;
      v49 = 128;
LABEL_116:
      v68 = v118;
      v141 = 128;
      v140 = 2;
      v142 = v21 != 0;
      if ( (_DWORD)v19 && *((_QWORD *)&v127[0] + 1) )
      {
        if ( (_DWORD)v118 == 2 )
        {
          v152 = *((_QWORD *)&v127[0] + 1);
          v20 = (__int64)&v139;
          v69 = 0;
          v149 |= 0x40u;
          v147 = NegSpnegoMechOid;
          v148 = 1;
          v150 = &v139;
          v151 = v19;
        }
        else
        {
          v69 = v114;
          if ( v114 )
          {
            SpmpReportHourlyEvent(
              &NEGOTIATE_UNBALANCED_EXCHANGE,
              L"uu",
              v134,
              *(_QWORD *)(*((_QWORD *)&v122[3].LockSemaphore + 4 * v53) + 16LL) + 48LL);
            v111 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_337;
            }
            v112 = 157;
            goto LABEL_336;
          }
          v49 = 160;
          v141 = 160;
          v144 = *((_QWORD *)&v127[0] + 1);
          v143 = v19;
        }
      }
      else
      {
        v69 = v114;
      }
      if ( !v31 || !*(_DWORD *)v31 )
      {
        v20 = 12288;
        if ( (*((_DWORD *)v43 + 24) & 0x3000) == 0x3000
          && !NegAcceptUnsafeUnprotectedNegotiation
          && (*((_DWORD *)v43 + 14) & 0x10010) != 0 )
        {
          v95 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_219;
          }
          v110 = 159;
          goto LABEL_319;
        }
        if ( (*((_DWORD *)v43 + 24) & 0x800) != 0 )
        {
          v20 = v119;
          if ( (*(_BYTE *)(v119 + 8) & 0x10) != 0
            && (unsigned int)(*(_DWORD *)(v119 + 40) - 1) <= 0x3E
            && (*((_DWORD *)v43 + 14) & 0x10010) != 0 )
          {
            v95 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_219;
            }
            v110 = 160;
            goto LABEL_319;
          }
        }
        if ( v69 )
        {
          *v67 = 0;
LABEL_152:
          v82 = 0;
          if ( !v21 )
          {
            if ( (*((_BYTE *)v43 + 96) & 8) != 0 )
              v21 = 590610;
            else
              v82 = 1;
          }
          *v136 = *((_DWORD *)v43 + 14);
          v20 = (__int64)v130;
          *v130 = *(union _LARGE_INTEGER *)((char *)v43 + 88);
          if ( v82 )
          {
            v83 = *((_BYTE *)v43 + 80);
            if ( v83 )
            {
              *v137 = v83;
              *v138 = *((struct _SecBuffer *)v43 + 4);
              *((_QWORD *)v43 + 9) = 0;
            }
            v84 = NegpChangeHandle((struct _SecHandle *)((char *)v43 + 24));
            *((_QWORD *)v43 + 3) = 0;
            *((_QWORD *)v43 + 4) = 0;
            if ( !v84 )
              v21 = -1073741670;
          }
          goto LABEL_19;
        }
LABEL_138:
        if ( v21 )
        {
          if ( v68 == 2 )
            goto LABEL_142;
          LOBYTE(v49) = v141;
        }
        else
        {
          if ( v68 == 2 )
            goto LABEL_142;
          if ( (v49 & 0x10) == 0 )
          {
            v21 = 590610;
            v49 &= ~0x80u;
            v141 = v49;
          }
        }
        if ( (v49 & 0x30) == 0 )
        {
          v95 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_219;
          }
          v110 = 161;
LABEL_319:
          WPP_SF_(*((_QWORD *)v95 + 2), v110, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
LABEL_219:
          v21 = -2146893048;
          goto LABEL_20;
        }
LABEL_142:
        v74 = &v140;
        if ( v68 == 2 )
          v74 = (__int16 *)&v147;
        v75 = ASN1_Encode(v120, v74, v68, 16, 0, 0);
        v76 = v75;
        if ( v75 < 0 )
        {
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              WPP_a36b0360a7043644a5a822ee72241678_Traceguids,
              (unsigned int)v75);
          }
          v77 = SpnegoAsnErrorToSecStatus(v76);
          v79 = v77;
          if ( v77 < 0 )
          {
            if ( v78 != v20 && (*(_BYTE *)(v78 + 28) & 1) != 0 )
              WPP_SF_d(*(_QWORD *)(v78 + 16), 162, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids, (unsigned int)v77);
            v21 = v79;
            goto LABEL_19;
          }
        }
        v20 = v124;
        if ( (v124 & 0x100) != 0 )
        {
          v113 = (void *)LsapAllocate(*(unsigned int *)(v120 + 28));
          *((_QWORD *)v67 + 1) = v113;
          if ( v113 )
          {
            memcpy_0(v113, *(const void **)(v120 + 16), *(unsigned int *)(v120 + 28));
            *v67 = *(_DWORD *)(v120 + 28);
            *((_DWORD *)v43 + 14) |= 0x100u;
            goto LABEL_152;
          }
        }
        else
        {
          v80 = *(_DWORD *)(v120 + 28);
          if ( *v67 >= v80 )
          {
            memcpy_0(*((void **)v67 + 1), *(const void **)(v120 + 16), v80);
            v81 = v120;
            *((_DWORD *)v43 + 14) &= ~0x100u;
            *v67 = *(_DWORD *)(v81 + 28);
            goto LABEL_152;
          }
          if ( (v124 & 0x200000) != 0 && *v67 >= 5 )
          {
            v97 = (void *)LsapAllocate(*(unsigned int *)(v120 + 28));
            *((_QWORD *)v43 + 13) = v97;
            if ( v97 )
            {
              memcpy_0(v97, *(const void **)(v120 + 16), *(unsigned int *)(v120 + 28));
              v98 = (const void *)*((_QWORD *)v43 + 13);
              v99 = *(_DWORD *)(v120 + 28);
              *((_DWORD *)v43 + 24) |= 8u;
              *((_DWORD *)v43 + 29) = v99;
              memcpy_0(*((void **)v67 + 1), v98, *v67);
              *((_DWORD *)v43 + 28) = *v67;
              goto LABEL_152;
            }
          }
        }
        v21 = -2146893056;
        goto LABEL_19;
      }
      if ( !v69 )
      {
        *((_DWORD *)v43 + 24) |= 0x400u;
        v49 |= 0x10u;
        v141 = v49;
        v146 = *((_QWORD *)&v127[v129.cBuffers - 1] + 1);
        v145 = v127[v129.cBuffers - 1];
        goto LABEL_138;
      }
      SpmpReportHourlyEvent(
        &NEGOTIATE_UNBALANCED_EXCHANGE,
        L"uu",
        v134,
        *(_QWORD *)(*((_QWORD *)&v122[3].LockSemaphore + 4 * v53) + 16LL) + 48LL);
      v111 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_337:
        v21 = -2146893052;
        goto LABEL_20;
      }
      v112 = 158;
LABEL_336:
      WPP_SF_(*((_QWORD *)v111 + 2), v112, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
      goto LABEL_337;
    }
    if ( (*(_BYTE *)(v119 + 8) & 0x10) != 0 )
    {
      v21 = -2146893054;
      goto LABEL_19;
    }
    if ( v18 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x1000) != 0 )
      WPP_SF_(*((_QWORD *)v18 + 2), 155, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
    v67 = v121;
    *v121 = 0;
    v21 = *((_DWORD *)v43 + 21);
    if ( v21 >= 0 )
    {
      v19 = LODWORD(v127[0]);
      v21 = 0;
      v31 = 0;
      v17 = 1;
      goto LABEL_116;
    }
    v92 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v93 = 156;
    goto LABEL_246;
  }
  if ( (*((_DWORD *)v43 + 24) & 0x200) == 0
    && v18 != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v18 + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v18 + 2), 141, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
  }
LABEL_76:
  *((_DWORD *)v43 + 24) |= 0x200u;
  if ( (*((_BYTE *)v43 + 96) & 1) != 0 )
  {
    v52 = v122;
    RtlEnterCriticalSection(v122 + 1);
    v53 = *((_QWORD *)v43 + 2);
    v54 = *((_QWORD *)&v52[3].LockSemaphore + 4 * v53);
    RtlLeaveCriticalSection(v52 + 1);
    goto LABEL_78;
  }
  v107 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
      v107 = WPP_GLOBAL_Control;
    }
    if ( v107 != (LsaHandleCache *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v107 + 7) & 0x1000) != 0 )
      {
        WPP_SF_(*((_QWORD *)v107 + 2), 143, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
        v107 = WPP_GLOBAL_Control;
      }
      if ( v107 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v107 + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)v107 + 2), 144, WPP_4e4b3cee65fb35adc13b839ab1e7ff33_Traceguids);
    }
  }
  return 2148074248LL;
}

```

## disassembly

```asm
0x18002ec1c  push    rbp
0x18002ec1e  push    rbx
0x18002ec1f  push    rsi
0x18002ec20  push    rdi
0x18002ec21  push    r12
0x18002ec23  push    r13
0x18002ec25  push    r14
0x18002ec27  push    r15
0x18002ec29  lea     rbp, [rsp-1C8h]
0x18002ec31  sub     rsp, 2C8h
0x18002ec38  mov     rax, cs:__security_cookie
0x18002ec3f  xor     rax, rsp
0x18002ec42  mov     [rbp+200h+var_50], rax
0x18002ec49  mov     rax, [rbp+200h+arg_40]
0x18002ec50  xor     r13d, r13d
0x18002ec53  mov     rsi, [rbp+200h+arg_28]
0x18002ec5a  mov     edi, r9d
0x18002ec5d  mov     r12, [rbp+200h+arg_38]
0x18002ec64  mov     [rbp+200h+var_1C0], rax
0x18002ec68  mov     rax, [rbp+200h+arg_48]
0x18002ec6f  mov     [rbp+200h+var_1F8], rax
0x18002ec73  mov     rax, [rbp+200h+arg_50]
0x18002ec7a  mov     [rbp+200h+var_1B8], rax
0x18002ec7e  mov     rax, [rbp+200h+arg_58]
0x18002ec85  mov     [rbp+200h+var_1D0], r8
0x18002ec89  lea     r8d, [r13+68h]; Size
0x18002ec8d  mov     [rbp+200h+var_248], rdx
0x18002ec91  xor     edx, edx; Val
0x18002ec93  mov     [rbp+200h+var_258], rcx
0x18002ec97  lea     rcx, [rbp+200h+var_190]; void *
0x18002ec9b  mov     [rbp+200h+var_1B0], rax
0x18002ec9f  mov     [rbp+200h+var_24C], r9d
0x18002eca3  mov     [rbp+200h+var_240], rsi
0x18002eca7  mov     [rbp+200h+var_1D8], r12
0x18002ecab  mov     [rbp+200h+var_270], r13
0x18002ecaf  call    memset_0
0x18002ecb4  xor     edx, edx; Val
0x18002ecb6  lea     r8d, [r13+70h]; Size
0x18002ecba  lea     rcx, [rbp+200h+var_120]; void *
0x18002ecc1  call    memset_0
0x18002ecc6  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x18002eccc  xorps   xmm0, xmm0
0x18002eccf  xorps   xmm1, xmm1
0x18002ecd2  mov     [rbp+200h+var_268], r13
0x18002ecd6  movups  xmmword ptr [rbp+200h+var_6C], xmm0
0x18002ecdd  mov     ebx, edi
0x18002ecdf  mov     r15d, 10000h
0x18002ece5  movups  xmmword ptr [rbp+200h+P], xmm0
0x18002ece9  or      ebx, r15d
0x18002ecec  mov     [rbp+200h+var_1F0], r13
0x18002ecf0  xor     eax, eax
0x18002ecf2  mov     [rbp+200h+var_250], ebx
0x18002ecf5  movups  xmmword ptr [rbp+200h+var_6C+0Ch], xmm0
0x18002ecfc  mov     dword ptr [rbp+200h+var_90], r13d
0x18002ed03  movups  xmmword ptr [rbp+200h+P+0Ch], xmm0
0x18002ed07  mov     [rbp+200h+var_B0.dwLower], r13
0x18002ed0e  movups  [rbp+200h+var_90+4], xmm0
0x18002ed15  mov     [rbp+200h+var_B0.dwUpper], r13
0x18002ed1c  movups  [rbp+200h+var_7C], xmm0
0x18002ed23  mov     [rbp+200h+var_27C], r13d
0x18002ed27  movups  xmmword ptr [rbp+200h+var_218.ulVersion], xmm0
0x18002ed2b  mov     [rbp+200h+var_238], r13d
0x18002ed2f  movups  xmmword ptr [rbp+200h+var_208.ulVersion], xmm0
0x18002ed33  mov     [rsp+300h+var_288], r13
0x18002ed38  movups  xmmword ptr [rbp+200h+var_A0.dwLower], xmm1
0x18002ed3f  call    cs:__imp_TlsGetValue
0x18002ed46  nop     dword ptr [rax+rax+00h]
0x18002ed4b  xorps   xmm0, xmm0
0x18002ed4e  mov     [rbp+200h+var_1C8], rax
0x18002ed52  movups  [rbp+200h+var_1A8], xmm0
0x18002ed56  test    r15d, edi
0x18002ed59  jz      loc_18002FC38
0x18002ed5f  mov     rcx, cs:?SPNEGO_Module@@3PEAUtagASN1module_t@@EA; tagASN1module_t * SPNEGO_Module
0x18002ed66  lea     rdx, [rbp+200h+var_268]
0x18002ed6a  xor     r9d, r9d
0x18002ed6d  mov     [rsp+300h+var_2E0], r13
0x18002ed72  xor     r8d, r8d
0x18002ed75  call    cs:__imp_ASN1_CreateEncoder
0x18002ed7c  nop     dword ptr [rax+rax+00h]
0x18002ed81  lea     r12, WPP_GLOBAL_Control
0x18002ed88  mov     r15d, 1
0x18002ed8e  mov     ebx, eax
0x18002ed90  test    eax, eax
0x18002ed92  jnz     loc_18002FB9B
0x18002ed98  mov     rcx, cs:?SPNEGO_Module@@3PEAUtagASN1module_t@@EA; tagASN1module_t * SPNEGO_Module
0x18002ed9f  lea     rdx, [rbp+200h+var_1F0]
0x18002eda3  xor     r9d, r9d
0x18002eda6  mov     [rsp+300h+var_2E0], r13
0x18002edab  xor     r8d, r8d
0x18002edae  call    cs:__imp_ASN1_CreateDecoder
0x18002edb5  nop     dword ptr [rax+rax+00h]
0x18002edba  mov     ebx, eax
0x18002edbc  test    eax, eax
0x18002edbe  jnz     loc_18002FC5F
0x18002edc4  mov     r10, cs:WPP_GLOBAL_Control
0x18002edcb  xor     r8d, r8d
0x18002edce  xor     edx, edx
0x18002edd0  xor     edi, edi
0x18002edd2  mov     [rbp+200h+var_278], r8
0x18002edd6  cmp     [rsi+4], edx
0x18002edd9  jbe     loc_1800305C1
0x18002eddf  lea     r9d, [rdx+2]
0x18002ede3  mov     r14d, edx
0x18002ede6  mov     ebx, r13d
0x18002ede9  shl     rbx, 4
0x18002eded  add     rbx, [rsi+8]
0x18002edf1  mov     r15d, [rbx+4]
0x18002edf5  mov     eax, r15d
0x18002edf8  and     eax, 0FFFFFFFh
0x18002edfd  cmp     eax, r9d
0x18002ee00  jnz     loc_18002EF98
0x18002ee06  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x18002ee0c  test    r8, r8
0x18002ee0f  mov     r12d, [rbx]
0x18002ee12  mov     rax, rbx
0x18002ee15  mov     rsi, [rbx+8]
0x18002ee19  cmovnz  rax, r8
0x18002ee1d  mov     [rbp+200h+var_278], rax
0x18002ee21  call    cs:__imp_TlsGetValue
0x18002ee28  nop     dword ptr [rax+rax+00h]
0x18002ee2d  test    dword ptr [rbx+4], 40000000h
0x18002ee34  jnz     loc_18002FC9D
0x18002ee3a  xor     edi, edi
0x18002ee3c  test    r14, r14
0x18002ee3f  jnz     loc_18002EFAD
0x18002ee45  mov     r8, [rbp+200h+var_278]
0x18002ee49  lea     r9d, [r14+2]
0x18002ee4d  mov     rsi, [rbp+200h+var_240]
0x18002ee51  mov     rdx, rbx
0x18002ee54  mov     [rbp+200h+var_278], r8
0x18002ee58  mov     r15d, 1
0x18002ee5e  add     r13d, r15d
0x18002ee61  cmp     r13d, [rsi+4]
0x18002ee65  jb      loc_18002EDE6
0x18002ee6b  test    edi, edi
0x18002ee6d  js      loc_18002FAB2
0x18002ee73  cmp     [rbp+200h+var_278], 0
0x18002ee78  jz      loc_1800305B3
0x18002ee7e  mov     r12, [rbp+200h+var_1D8]
0x18002ee82  xor     r8d, r8d
0x18002ee85  xor     edx, edx
0x18002ee87  mov     [rbp+200h+var_260], r8
0x18002ee8b  xor     edi, edi
0x18002ee8d  xor     r13d, r13d
0x18002ee90  cmp     [r12+4], edx
0x18002ee95  ja      loc_18002EFB8
0x18002ee9b  mov     edi, 80090308h
0x18002eea0  mov     rbx, [rsp+300h+var_288]
0x18002eea5  mov     r14d, 8009030Eh
0x18002eeab  cmp     [rbp+200h+P+4], 0
0x18002eeb0  jz      short loc_18002EED9
0x18002eeb2  mov     rcx, gs:60h
0x18002eebb  xor     edx, edx; Flags
0x18002eebd  mov     r8, [rbp+200h+P+4]; P
0x18002eec1  mov     rcx, [rcx+30h]; HeapHandle
0x18002eec5  call    cs:__imp_RtlFreeHeap
0x18002eecc  nop     dword ptr [rax+rax+00h]
0x18002eed1  mov     [rbp+200h+P+4], 0
0x18002eed9  test    rbx, rbx
0x18002eedc  jnz     loc_18002EF81
0x18002eee2  mov     rcx, [rbp+200h+var_268]
0x18002eee6  test    rcx, rcx
0x18002eee9  jz      short loc_18002EEFB
0x18002eeeb  mov     rdx, [rcx+10h]
0x18002eeef  call    cs:__imp_ASN1_FreeEncoded
0x18002eef6  nop     dword ptr [rax+rax+00h]
0x18002eefb  mov     rdx, [rbp+200h+var_270]
0x18002eeff  test    rdx, rdx
0x18002ef02  jz      short loc_18002EF24
0x18002ef04  mov     rcx, [rbp+200h+var_1F0]
0x18002ef08  test    rcx, rcx
0x18002ef0b  jz      short loc_18002EF24
0x18002ef0d  test    rdx, rdx
0x18002ef10  jz      short loc_18002EF24
0x18002ef12  mov     r8d, 1
0x18002ef18  call    cs:__imp_ASN1_FreeDecoded
0x18002ef1f  nop     dword ptr [rax+rax+00h]
0x18002ef24  mov     rcx, [rbp+200h+var_268]
0x18002ef28  mov     rbx, [rbp+200h+var_1F0]
0x18002ef2c  test    rcx, rcx
0x18002ef2f  jz      short loc_18002EF3D
0x18002ef31  call    cs:__imp_ASN1_CloseEncoder
0x18002ef38  nop     dword ptr [rax+rax+00h]
0x18002ef3d  test    rbx, rbx
0x18002ef40  jz      short loc_18002EF51
0x18002ef42  mov     rcx, rbx
0x18002ef45  call    cs:__imp_ASN1_CloseDecoder
0x18002ef4c  nop     dword ptr [rax+rax+00h]
0x18002ef51  cmp     edi, 0C000042Dh
0x18002ef57  cmovz   edi, r14d
0x18002ef5b  mov     eax, edi
0x18002ef5d  mov     rcx, [rbp+200h+var_50]
0x18002ef64  xor     rcx, rsp; StackCookie
0x18002ef67  call    __security_check_cookie
0x18002ef6c  add     rsp, 2C8h
0x18002ef73  pop     r15
0x18002ef75  pop     r14
0x18002ef77  pop     r13
0x18002ef79  pop     r12
0x18002ef7b  pop     rdi
0x18002ef7c  pop     rsi
0x18002ef7d  pop     rbx
0x18002ef7e  pop     rbp
0x18002ef7f  retn
0x18002ef81  mov     rcx, [rbx+8]; struct _RTL_BALANCED_NODE *
0x18002ef85  test    rcx, rcx
0x18002ef88  jz      loc_18002EEE2
0x18002ef8e  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18002ef93  jmp     loc_18002EEE2
0x18002ef98  test    eax, eax
0x18002ef9a  jnz     loc_18002EE58
0x18002efa0  test    rdx, rdx
0x18002efa3  jnz     short loc_18002EFAD
0x18002efa5  mov     r14, rbx
0x18002efa8  jmp     loc_18002EE58
0x18002efad  mov     r15d, 1
0x18002efb3  jmp     loc_18002EE6B
0x18002efb8  mov     r14, rdx
0x18002efbb  mov     ebx, r13d
0x18002efbe  shl     rbx, 4
0x18002efc2  add     rbx, [r12+8]
0x18002efc7  mov     r15d, [rbx+4]
0x18002efcb  mov     eax, r15d
0x18002efce  and     eax, 0FFFFFFFh
0x18002efd3  cmp     eax, 2
0x18002efd6  jnz     loc_18002FA54
0x18002efdc  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x18002efe2  test    r8, r8
0x18002efe5  mov     r12d, [rbx]
0x18002efe8  mov     rax, rbx
0x18002efeb  mov     rsi, [rbx+8]
0x18002efef  cmovnz  rax, r8
0x18002eff3  mov     [rbp+200h+var_260], rax
0x18002eff7  call    cs:__imp_TlsGetValue
0x18002effe  nop     dword ptr [rax+rax+00h]
0x18002f003  test    dword ptr [rbx+4], 40000000h
0x18002f00a  jnz     loc_18002FD48
0x18002f010  xor     edi, edi
0x18002f012  test    r14, r14
0x18002f015  jnz     short loc_18002F030
0x18002f017  mov     r8, [rbp+200h+var_260]
0x18002f01b  mov     rdx, rbx
0x18002f01e  mov     r12, [rbp+200h+var_1D8]
0x18002f022  mov     [rbp+200h+var_260], r8
0x18002f026  inc     r13d
0x18002f029  cmp     r13d, [r12+4]
0x18002f02e  jb      short loc_18002EFBB
0x18002f030  mov     r14, [rbp+200h+var_248]
0x18002f034  test    edi, edi
0x18002f036  js      loc_18002FDD4
0x18002f03c  cmp     [rbp+200h+var_260], 0
0x18002f041  jz      loc_18002EE9B
0x18002f047  test    r14, r14
0x18002f04a  jz      loc_18002FA91
0x18002f050  mov     r9, [rbp+200h+var_240]
0x18002f054  xor     edx, edx
0x18002f056  mov     [rbp+200h+var_248], 0
0x18002f05e  lea     r13d, [rdx+1]
0x18002f062  cmp     edx, [r9+4]
0x18002f066  jnb     short loc_18002F08A
0x18002f068  mov     r8d, edx
0x18002f06b  shl     r8, 4
0x18002f06f  add     r8, [r9+8]
0x18002f073  mov     eax, [r8+4]
0x18002f077  and     eax, 0FFFFFFFh
0x18002f07c  cmp     eax, 0Eh
0x18002f07f  jz      short loc_18002F086
0x18002f081  add     edx, r13d
0x18002f084  jmp     short loc_18002F062
0x18002f086  mov     [rbp+200h+var_248], r8
0x18002f08a  cmp     [rbp+200h+var_258], 0
0x18002f08f  jz      loc_18002FE1E
0x18002f095  mov     r9, [rbp+200h+var_278]
0x18002f099  mov     [rbp+200h+var_278], 0
0x18002f0a1  mov     r15d, [r9]
0x18002f0a4  test    r15d, r15d
0x18002f0a7  jz      loc_18002FAE6
0x18002f0ad  mov     rsi, [r9+8]
0x18002f0b1  test    rsi, rsi
0x18002f0b4  jz      loc_18002FAE6
0x18002f0ba  mov     rcx, cs:?SPNEGO_Module@@3PEAUtagASN1module_t@@EA; tagASN1module_t * SPNEGO_Module
0x18002f0c1  lea     rdx, [rbp+200h+var_278]
0x18002f0c5  xor     edi, edi
0x18002f0c7  xor     r9d, r9d
0x18002f0ca  xor     r8d, r8d
0x18002f0cd  mov     [rsp+300h+var_2E0], rdi
0x18002f0d2  call    cs:__imp_ASN1_CreateDecoder
0x18002f0d9  nop     dword ptr [rax+rax+00h]
0x18002f0de  mov     ebx, eax
0x18002f0e0  test    eax, eax
0x18002f0e2  jnz     loc_18002FE2B
0x18002f0e8  lea     r12, WPP_GLOBAL_Control
0x18002f0ef  mov     rcx, [rbp+200h+var_278]
0x18002f0f3  lea     rdx, [rbp+200h+var_270]
0x18002f0f7  mov     [rsp+300h+var_2D8], r15d
0x18002f0fc  mov     r9d, 8
0x18002f102  mov     r8d, r13d
0x18002f105  mov     [rsp+300h+var_2E0], rsi
0x18002f10a  mov     [rbp+200h+var_270], 0
0x18002f112  call    cs:__imp_ASN1_Decode
  ... truncated ...
```
