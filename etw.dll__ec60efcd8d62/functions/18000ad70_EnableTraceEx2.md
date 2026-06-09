# EnableTraceEx2

- ea: `0x18000ad70`
- end: `0x18000b5de`
- name: `EnableTraceEx2`
- size: `2158`
- prototype: `ULONG __stdcall(TRACEHANDLE TraceHandle, LPCGUID ProviderId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, ULONG Timeout, PENABLE_TRACE_PARAMETERS EnableParameters)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180002450`

## callees

- `0x180001008`
- `0x180001560`
- `0x180001eb2`
- `0x180001ebe`
- `0x180001ed6`
- `0x180001ef0`
- `0x180002ec4`
- `0x180008988`
- `0x180008de0`
- `0x180009488`
- `0x18000ad70`
- `0x1800144a4`
- `0x180015834`

## import_xrefs

- `ntdll!EtwDeliverDataBlock` at `0x18000b36c`
- `ntdll!EtwDeliverDataBlock` at `0x18000b36c`
- `ntdll!EtwSendNotification` at `0x18000b3a2`
- `ntdll!EtwSendNotification` at `0x18000b3a2`
- `ntdll!RtlSetLastWin32Error` at `0x18000b580`
- `ntdll!RtlSetLastWin32Error` at `0x18000b580`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ae27`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ae27`
- `ext-ms-win-eventing-rundown-l1-1-0!EtwLogSysConfigRundown` at `0x18000b469`
- `ext-ms-win-eventing-rundown-l1-1-0!EtwLogSysConfigRundown` at `0x18000b469`

## pseudocode

```c
ULONG __stdcall EnableTraceEx2(
        TRACEHANDLE TraceHandle,
        LPCGUID ProviderId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        ULONG Timeout,
        PENABLE_TRACE_PARAMETERS EnableParameters)
{
  ULONG EnableProperty; // r15d
  LPCGUID v10; // r13
  ULONG *v13; // rax
  char v14; // r12
  unsigned __int64 EnableFilterDesc; // rsi
  __int64 v16; // r14
  ULONG v17; // ebx
  TRACEHANDLE v18; // rax
  UCHAR v19; // r12
  unsigned int v20; // ebx
  bool v22; // cl
  __int64 v23; // r8
  ULONGLONG v24; // r12
  ULONG v25; // edx
  bool v26; // zf
  int v27; // ecx
  unsigned int v28; // edx
  __int128 *p_P; // rdi
  __int64 v30; // rax
  int v31; // ebx
  _OWORD *Heap_0; // rax
  char *v33; // r13
  _BYTE *v34; // r15
  __int64 v35; // r12
  __int64 v36; // rbx
  char v37; // cl
  __int16 v38; // ax
  int v39; // eax
  unsigned int v40; // eax
  unsigned __int64 v41; // rcx
  UCHAR v42; // [rsp+30h] [rbp-D0h] BYREF
  ULONG LastError; // [rsp+34h] [rbp-CCh] BYREF
  ULONG v44; // [rsp+38h] [rbp-C8h] BYREF
  ULONG v45; // [rsp+3Ch] [rbp-C4h] BYREF
  UCHAR v46; // [rsp+40h] [rbp-C0h]
  ULONG v47; // [rsp+44h] [rbp-BCh]
  TRACEHANDLE v48; // [rsp+48h] [rbp-B8h]
  TRACEHANDLE v49; // [rsp+50h] [rbp-B0h] BYREF
  LPCGUID v50; // [rsp+58h] [rbp-A8h]
  ULONGLONG v51; // [rsp+60h] [rbp-A0h] BYREF
  ULONGLONG v52; // [rsp+68h] [rbp-98h] BYREF
  TRACEHANDLE v53; // [rsp+70h] [rbp-90h] BYREF
  int v54; // [rsp+78h] [rbp-88h] BYREF
  char v55; // [rsp+7Ch] [rbp-84h]
  GUID ActivityId; // [rsp+80h] [rbp-80h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-60h] BYREF
  char v58; // [rsp+B0h] [rbp-50h]
  __int128 v59; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v60; // [rsp+C8h] [rbp-38h]
  __int128 P; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v62; // [rsp+E8h] [rbp-18h]
  _BYTE v63[48]; // [rsp+F8h] [rbp-8h]
  __int128 v64; // [rsp+128h] [rbp+28h]
  __int128 v65; // [rsp+138h] [rbp+38h]
  __int64 v66; // [rsp+148h] [rbp+48h]
  GUID v67; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v68[32]; // [rsp+160h] [rbp+60h] BYREF
  TRACEHANDLE *v69; // [rsp+180h] [rbp+80h]
  __int64 v70; // [rsp+188h] [rbp+88h]
  ULONG *v71; // [rsp+190h] [rbp+90h]
  __int64 v72; // [rsp+198h] [rbp+98h]
  ULONG *p_Data1; // [rsp+1A0h] [rbp+A0h]
  __int64 v74; // [rsp+1A8h] [rbp+A8h]
  UCHAR *v75; // [rsp+1B0h] [rbp+B0h]
  __int64 v76; // [rsp+1B8h] [rbp+B8h]
  ULONGLONG *v77; // [rsp+1C0h] [rbp+C0h]
  __int64 v78; // [rsp+1C8h] [rbp+C8h]
  ULONGLONG *v79; // [rsp+1D0h] [rbp+D0h]
  __int64 v80; // [rsp+1D8h] [rbp+D8h]
  ULONG *v81; // [rsp+1E0h] [rbp+E0h]
  __int64 v82; // [rsp+1E8h] [rbp+E8h]

  EnableProperty = 0;
  v50 = ProviderId;
  v10 = ProviderId;
  v48 = TraceHandle;
  v49 = TraceHandle;
  v46 = Level;
  v47 = ControlCode;
  LastError = 0;
  memset_0(&P, 0, 0x78u);
  v54 = 0;
  v55 = 0;
  v59 = 0;
  v60 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v54 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    v45 = Timeout;
    v51 = MatchAllKeyword;
    v52 = MatchAnyKeyword;
    v42 = Level;
    v44 = ControlCode;
    if ( v10 )
    {
      v13 = (ULONG *)&v67;
      v67 = *v10;
    }
    else
    {
      v13 = (ULONG *)&v57;
      v57 = 0;
    }
    v53 = TraceHandle;
    v71 = v13;
    v81 = &v45;
    v69 = &v53;
    v79 = &v51;
    v77 = &v52;
    v82 = 4;
    v75 = &v42;
    v80 = 8;
    p_Data1 = &v44;
    v78 = 8;
    v76 = 1;
    v74 = 4;
    v72 = 16;
    v70 = 8;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)byte_180018F0B,
      (__int64)&ActivityId,
      0,
      9,
      (__int64)v68);
  }
  v14 = BYTE3(v49);
  *(_QWORD *)&v57 = &v54;
  *((_QWORD *)&v57 + 1) = &LastError;
  v58 = 1;
  if ( !EnableParameters )
  {
    EnableFilterDesc = 0;
    LODWORD(v16) = 0;
    goto LABEL_25;
  }
  if ( !EnableParameters->ControlFlags )
  {
    EnableFilterDesc = (unsigned __int64)EnableParameters->EnableFilterDesc;
    if ( EnableParameters->Version == 1 )
    {
      if ( EnableFilterDesc )
        EnableFilterDesc &= -(__int64)(*(_DWORD *)(EnableFilterDesc + 8) != 0);
      v16 = EnableFilterDesc != 0;
LABEL_21:
      EnableProperty = EnableParameters->EnableProperty;
      if ( (_DWORD)v16 )
      {
        LastError = EtwpValidateFilterDescriptors(
                      BYTE3(v49) & 1,
                      ControlCode,
                      v16,
                      (struct _EVENT_FILTER_DESCRIPTOR *)EnableFilterDesc);
        v17 = LastError;
        if ( LastError )
        {
LABEL_108:
          lambda_cb80d53bc1f4542c2acac4cfc40ddcc6_::operator()(&v57);
          if ( v54 == 1 )
          {
            v54 = 2;
            _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
          }
          return v17;
        }
      }
LABEL_25:
      v18 = v48;
      v19 = v14 & 1;
      v20 = (unsigned __int16)v48;
      v42 = v19;
      if ( v19 )
      {
        if ( (EnableProperty & 0x20) != 0 || (EnableProperty & 0x100) != 0 )
          goto LABEL_28;
        v22 = 0;
        LOWORD(v20) = v48 | 0x8000;
        v44 = (unsigned __int16)v48 | 0x8000;
      }
      else
      {
        if ( (unsigned __int16)v48 == 0xFFFF )
          v20 = 0;
        v44 = v20;
        EtwpCacheMaxLogger();
        v18 = v48;
        v22 = v20 >= EtwpMaxLoggers;
      }
      if ( !v10 || v47 > 2 || v18 - 1 > 0xFFFFFFFFFFFFFFFDuLL || v22 )
      {
        LastError = 87;
        goto LABEL_99;
      }
      memset_0(&P, 0, 0x78u);
      v23 = 8;
      *(_QWORD *)&P = 0x7800000003LL;
      DWORD2(v62) = -1;
      if ( Timeout && (!v19 || (unsigned __int16)(v48 - 8) > 0x37u) )
      {
        BYTE12(P) = 1;
        LODWORD(v62) = Timeout;
      }
      *(GUID *)&v63[8] = *v10;
      if ( EnableParameters )
        *(GUID *)&v63[24] = EnableParameters->SourceId;
      v24 = MatchAnyKeyword;
      v25 = v47;
      v63[44] = v46;
      *(_QWORD *)&v65 = MatchAllKeyword;
      *(_DWORD *)&v63[40] = v47;
      *((_QWORD *)&v64 + 1) = MatchAnyKeyword;
      *(_WORD *)&v63[46] = v20;
      LODWORD(v64) = EnableProperty;
      if ( *(_OWORD *)&SystemTraceControlGuid != *(_OWORD *)v10 || v47 != 2 )
      {
        p_P = &P;
        if ( !(_DWORD)v16 || !v47 )
          goto LABEL_66;
        v28 = 0;
        v27 = 16 * v16;
        do
        {
LABEL_60:
          v30 = v28++;
          v27 += *(_DWORD *)(16 * v30 + EnableFilterDesc + 8);
        }
        while ( v28 < (unsigned int)v16 );
        v31 = v27 + 120;
        Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v27 + 120));
        p_P = Heap_0;
        if ( !Heap_0 )
        {
          LastError = 14;
LABEL_100:
          v25 = v47;
          goto LABEL_101;
        }
        DWORD1(P) = v31;
        v33 = (char *)Heap_0 + 120;
        HIDWORD(v66) = v16;
        *Heap_0 = P;
        v34 = (char *)&Heap_0[(unsigned int)v16 + 7] + 8;
        v45 = 0;
        Heap_0[1] = v62;
        Heap_0[2] = *(_OWORD *)v63;
        Heap_0[3] = *(_OWORD *)&v63[16];
        Heap_0[4] = *(_OWORD *)&v63[32];
        Heap_0[5] = v64;
        Heap_0[6] = v65;
        *((_QWORD *)Heap_0 + 14) = v66;
        v35 = 0;
        do
        {
          v36 = 2 * v35;
          *(_DWORD *)&v33[8 * v36 + 12] = *(_DWORD *)(EnableFilterDesc + 16 * v35 + 12);
          *(_DWORD *)&v33[8 * v36 + 8] = *(_DWORD *)(EnableFilterDesc + 16 * v35 + 8);
          *(_QWORD *)&v33[8 * v36] = v34 - (_BYTE *)p_P;
          memcpy_0(
            v34,
            *(const void **)(EnableFilterDesc + 16 * v35),
            *(unsigned int *)(EnableFilterDesc + 16 * v35 + 8));
          ++v35;
          v34 += *(unsigned int *)&v33[8 * v36 + 8];
          ++v45;
        }
        while ( v45 < (unsigned int)v16 );
        v24 = MatchAnyKeyword;
        v10 = v50;
        LOWORD(v20) = v44;
LABEL_66:
        if ( v42 && (unsigned __int16)(v48 - 8) <= 0x37u )
        {
          v37 = *((_BYTE *)p_P + 76);
          *((_DWORD *)p_P + 28) = *((_DWORD *)p_P + 18);
          *((_DWORD *)p_P + 27) = *((_DWORD *)p_P + 22);
          v38 = *((_WORD *)p_P + 39) & 0x7FFF;
          *((_BYTE *)p_P + 106) = v37;
          v26 = *((_QWORD *)p_P + 11) == 0;
          *((_WORD *)p_P + 52) = v38;
          *((_BYTE *)p_P + 107) = 1;
          if ( v26 )
            *((_QWORD *)p_P + 11) = -1;
          if ( !v37 )
            *((_BYTE *)p_P + 76) = -1;
          v39 = *((_DWORD *)p_P + 20);
          if ( (v39 & 0x10) != 0 )
            v40 = v39 & 0xFFFFFFEF;
          else
            v40 = v39 | 0x40;
          *((_DWORD *)p_P + 20) = v40;
          LastError = EtwDeliverDataBlock(p_P, 0x7FFF, v23);
          goto LABEL_95;
        }
        v44 = 0;
        v45 = 0;
        LastError = EtwSendNotification(p_P, 0, 0, &v44, &v45);
        v26 = *(_QWORD *)&v10->Data1 == KernelRundownGuid;
        v59 = 0;
        v60 = 0;
        if ( v26 && *(_QWORD *)v10->Data4 == 0xCDF584518E9C7793uLL && v47 == 1 )
        {
          if ( v24 == 2 )
          {
            v41 = 0xFFFF;
LABEL_81:
            EtwpQueryGroupMaskForRundown(v41, (struct _PERFINFO_GROUPMASK *)&v59);
            goto LABEL_92;
          }
          if ( v24 == 8 )
          {
            v41 = 2;
            goto LABEL_81;
          }
        }
        else if ( *(_QWORD *)&v10->Data1 == *(_QWORD *)&SystemTraceControlGuid.Data1
               && *(_QWORD *)v10->Data4 == *(_QWORD *)SystemTraceControlGuid.Data4
               && v47 == 2 )
        {
          if ( *(_DWORD *)(EnableFilterDesc + 12) == -2147483647 )
            memcpy_0(&v59, *(const void **)EnableFilterDesc, *(unsigned int *)(EnableFilterDesc + 8));
          else
            EtwpQueryGroupMaskForRundown(**(unsigned __int16 **)EnableFilterDesc, (struct _PERFINFO_GROUPMASK *)&v59);
          if ( v24 == 2 || v24 == 8 )
          {
LABEL_92:
            if ( (unsigned __int8)IsEtwLogHeapRundownPresent() && (DWORD2(v60) & 0x1FFFFFFF) != 0 )
              EtwLogSysConfigRundown((unsigned __int16)v20, &v59);
          }
        }
LABEL_95:
        if ( p_P && p_P != &P )
          RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, p_P);
LABEL_99:
        if ( !LastError )
        {
LABEL_105:
          if ( LastError )
            RtlSetLastWin32Error(LastError);
          v17 = LastError;
          goto LABEL_108;
        }
        goto LABEL_100;
      }
      if ( EnableFilterDesc && (_DWORD)v16 )
      {
        if ( *(_DWORD *)(EnableFilterDesc + 12) == -2147483647 )
        {
          if ( *(_DWORD *)(EnableFilterDesc + 8) > 0x20u )
            goto LABEL_56;
          v26 = (*(_BYTE *)(EnableFilterDesc + 8) & 3) == 0;
        }
        else
        {
          if ( *(_DWORD *)(EnableFilterDesc + 12) != -2147483646 )
            goto LABEL_56;
          v26 = *(_DWORD *)(EnableFilterDesc + 8) == 8;
        }
        if ( v26 )
        {
          v27 = 16 * v16;
          v28 = 0;
          goto LABEL_60;
        }
      }
LABEL_56:
      LastError = 87;
LABEL_101:
      if ( (unsigned int)dword_18001D020 > 2 && (qword_18001D030 & 2) != 0 && (qword_18001D038 & 2) == qword_18001D038 )
      {
        v49 = v48;
        v44 = LastError;
        v75 = (UCHAR *)&v49;
        v71 = &v45;
        v69 = (TRACEHANDLE *)&v44;
        v45 = v25;
        v76 = 8;
        p_Data1 = &v10->Data1;
        v74 = 16;
        v72 = 4;
        v70 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_18001D020,
          (unsigned __int8 *)byte_180018EB9,
          0,
          0,
          6,
          (__int64)v68);
      }
      goto LABEL_105;
    }
    if ( EnableParameters->Version == 2 )
    {
      LODWORD(v16) = EnableParameters->FilterDescCount;
      goto LABEL_21;
    }
  }
LABEL_28:
  LastError = 87;
  lambda_cb80d53bc1f4542c2acac4cfc40ddcc6_::operator()(&v57);
  if ( v54 == 1 )
  {
    v54 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
  }
  return 87;
}

```

## disassembly

```asm
0x18000ad70  mov     [rsp-8+arg_8], rbx
0x18000ad75  push    rbp
0x18000ad76  push    rsi
0x18000ad77  push    rdi
0x18000ad78  push    r12
0x18000ad7a  push    r13
0x18000ad7c  push    r14
0x18000ad7e  push    r15
0x18000ad80  lea     rbp, [rsp-100h]
0x18000ad88  sub     rsp, 200h
0x18000ad8f  mov     rax, cs:__security_cookie
0x18000ad96  xor     rax, rsp
0x18000ad99  mov     [rbp+130h+var_40], rax
0x18000ada0  mov     rdi, [rbp+130h+EnableParameters]
0x18000ada7  mov     ebx, r8d
0x18000adaa  xor     r15d, r15d
0x18000adad  mov     [rsp+230h+var_1D8], rdx
0x18000adb2  mov     r13, rdx
0x18000adb5  mov     [rsp+230h+var_1E8], rcx
0x18000adba  mov     r14, rcx
0x18000adbd  mov     [rsp+230h+var_1E0], rcx
0x18000adc2  xor     edx, edx; Val
0x18000adc4  mov     [rsp+230h+var_1F0], r9b
0x18000adc9  lea     r8d, [r15+78h]; Size
0x18000adcd  mov     [rsp+230h+var_1EC], ebx
0x18000add1  lea     rcx, [rbp+130h+P]; void *
0x18000add5  mov     [rsp+230h+LastError], r15d
0x18000adda  mov     sil, r9b
0x18000addd  call    memset_0
0x18000ade2  mov     eax, cs:dword_18001D020
0x18000ade8  xorps   xmm0, xmm0
0x18000adeb  mov     [rsp+230h+var_1B8], r15d
0x18000adf0  mov     [rsp+230h+var_1B4], r15b
0x18000adf5  movups  [rbp+130h+var_178], xmm0
0x18000adf9  movups  [rbp+130h+var_168], xmm0
0x18000adfd  cmp     eax, 5
0x18000ae00  jbe     short loc_18000AE2F
0x18000ae02  mov     rcx, cs:qword_18001D038
0x18000ae09  mov     rax, cs:qword_18001D030
0x18000ae10  test    al, 10h
0x18000ae12  jz      short loc_18000AE2F
0x18000ae14  mov     rax, rcx
0x18000ae17  and     eax, 10h
0x18000ae1a  cmp     rax, rcx
0x18000ae1d  jnz     short loc_18000AE2F
0x18000ae1f  lea     rdx, [rbp+130h+ActivityId]; ActivityId
0x18000ae23  lea     ecx, [r15+3]; ControlCode
0x18000ae27  call    cs:__imp_EventActivityIdControl
0x18000ae2d  jmp     short loc_18000AE33
0x18000ae2f  movups  xmmword ptr [rbp+130h+ActivityId.Data1], xmm0
0x18000ae33  mov     eax, cs:dword_18001D020
0x18000ae39  mov     [rsp+230h+var_1B8], 1
0x18000ae41  cmp     eax, 5
0x18000ae44  jbe     loc_18000AFAB
0x18000ae4a  mov     rcx, cs:qword_18001D038
0x18000ae51  mov     rax, cs:qword_18001D030
0x18000ae58  test    al, 10h
0x18000ae5a  jz      loc_18000AFAB
0x18000ae60  mov     rax, rcx
0x18000ae63  and     eax, 10h
0x18000ae66  cmp     rax, rcx
0x18000ae69  jnz     loc_18000AFAB
0x18000ae6f  mov     eax, [rbp+130h+Timeout]
0x18000ae75  mov     [rsp+230h+var_1F4], eax
0x18000ae79  mov     rax, [rbp+130h+MatchAllKeyword]
0x18000ae80  mov     [rsp+230h+var_1D0], rax
0x18000ae85  mov     rax, [rbp+130h+MatchAnyKeyword]
0x18000ae8c  mov     [rsp+230h+var_1C8], rax
0x18000ae91  mov     [rsp+230h+var_200], sil
0x18000ae96  mov     [rsp+230h+var_1F8], ebx
0x18000ae9a  test    r13, r13
0x18000ae9d  jz      short loc_18000AEAF
0x18000ae9f  movups  xmm0, xmmword ptr [r13+0]
0x18000aea4  lea     rax, [rbp+130h+var_E0]
0x18000aea8  movdqu  [rbp+130h+var_E0], xmm0
0x18000aead  jmp     short loc_18000AEBA
0x18000aeaf  xorps   xmm0, xmm0
0x18000aeb2  lea     rax, [rbp+130h+var_190]
0x18000aeb6  movups  [rbp+130h+var_190], xmm0
0x18000aeba  mov     [rsp+230h+var_1C0], r14
0x18000aebf  cmp     [rsp+230h+var_1B4], r15b
0x18000aec4  jz      short loc_18000AEE4
0x18000aec6  cmp     [rbp+130h+var_1A0], r15d
0x18000aeca  jnz     short loc_18000AEDE
0x18000aecc  cmp     [rbp+130h+var_19C], r15d
0x18000aed0  jnz     short loc_18000AEDE
0x18000aed2  cmp     [rbp+130h+var_198], r15d
0x18000aed6  jnz     short loc_18000AEDE
0x18000aed8  cmp     [rbp+130h+var_194], r15d
0x18000aedc  jz      short loc_18000AEE4
0x18000aede  lea     r9, [rbp+130h+var_1A0]
0x18000aee2  jmp     short loc_18000AEE7
0x18000aee4  mov     r9, r15
0x18000aee7  mov     [rbp+130h+var_A0], rax
0x18000aeee  lea     rcx, [rsp+230h+var_1F4]
0x18000aef3  mov     [rbp+130h+var_50], rcx
0x18000aefa  lea     rax, [rsp+230h+var_1C0]
0x18000aeff  lea     rcx, [rsp+230h+var_1D0]
0x18000af04  mov     [rbp+130h+var_B0], rax
0x18000af0b  mov     [rbp+130h+var_60], rcx
0x18000af12  lea     rax, [rbp+130h+var_D0]
0x18000af16  lea     rcx, [rsp+230h+var_1C8]
0x18000af1b  mov     [rsp+230h+var_208], rax
0x18000af20  mov     [rbp+130h+var_70], rcx
0x18000af27  lea     r8, [rbp+130h+ActivityId]
0x18000af2b  lea     rcx, [rsp+230h+var_200]
0x18000af30  mov     [rbp+130h+var_48], 4
0x18000af3b  mov     [rbp+130h+var_80], rcx
0x18000af42  lea     rdx, byte_180018F0B
0x18000af49  lea     rcx, [rsp+230h+var_1F8]
0x18000af4e  mov     [rbp+130h+var_58], 8
0x18000af59  mov     [rbp+130h+var_90], rcx
0x18000af60  lea     rcx, dword_18001D020
0x18000af67  mov     [rbp+130h+var_68], 8
0x18000af72  mov     [rbp+130h+var_78], 1
0x18000af7d  mov     [rbp+130h+var_88], 4
0x18000af88  mov     [rbp+130h+var_98], 10h
0x18000af93  mov     [rbp+130h+var_A8], 8
0x18000af9e  mov     dword ptr [rsp+230h+var_210], 9
0x18000afa6  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000afab  mov     r12b, byte ptr [rsp+230h+var_1E0+3]
0x18000afb0  lea     rax, [rsp+230h+var_1B8]
0x18000afb5  mov     qword ptr [rbp+130h+var_190], rax
0x18000afb9  lea     rax, [rsp+230h+LastError]
0x18000afbe  mov     qword ptr [rbp+130h+var_190+8], rax
0x18000afc2  mov     [rbp+130h+var_180], 1
0x18000afc6  test    rdi, rdi
0x18000afc9  jz      short loc_18000B02A
0x18000afcb  cmp     [rdi+8], r15d
0x18000afcf  jnz     short loc_18000B04F
0x18000afd1  cmp     dword ptr [rdi], 1
0x18000afd4  mov     rsi, [rdi+20h]
0x18000afd8  jnz     short loc_18000AFF6
0x18000afda  test    rsi, rsi
0x18000afdd  jz      short loc_18000AFEA
0x18000afdf  mov     eax, [rsi+8]
0x18000afe2  neg     eax
0x18000afe4  sbb     rcx, rcx
0x18000afe7  and     rsi, rcx
0x18000afea  test    rsi, rsi
0x18000afed  mov     r14d, r15d
0x18000aff0  setnz   r14b
0x18000aff4  jmp     short loc_18000AFFF
0x18000aff6  cmp     dword ptr [rdi], 2
0x18000aff9  jnz     short loc_18000B04F
0x18000affb  mov     r14d, [rdi+28h]
0x18000afff  mov     r15d, [rdi+4]
0x18000b003  test    r14d, r14d
0x18000b006  jz      short loc_18000B02F
0x18000b008  mov     cl, r12b
0x18000b00b  mov     r9, rsi; struct _EVENT_FILTER_DESCRIPTOR *
0x18000b00e  and     cl, 1; unsigned __int8
0x18000b011  mov     r8d, r14d; unsigned int
0x18000b014  mov     edx, ebx; unsigned int
0x18000b016  call    ?EtwpValidateFilterDescriptors@@YAKEKKPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpValidateFilterDescriptors(uchar,ulong,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x18000b01b  mov     [rsp+230h+LastError], eax
0x18000b01f  mov     ebx, eax
0x18000b021  test    eax, eax
0x18000b023  jz      short loc_18000B02F
0x18000b025  jmp     loc_18000B58A
0x18000b02a  xor     esi, esi
0x18000b02c  xor     r14d, r14d
0x18000b02f  mov     rax, [rsp+230h+var_1E8]
0x18000b034  and     r12b, 1
0x18000b038  movzx   ebx, ax
0x18000b03b  mov     [rsp+230h+var_200], r12b
0x18000b040  jz      short loc_18000B095
0x18000b042  test    r15b, 20h
0x18000b046  jnz     short loc_18000B04F
0x18000b048  bt      r15d, 8
0x18000b04d  jnb     short loc_18000B089
0x18000b04f  lea     rcx, [rbp+130h+var_190]
0x18000b053  mov     [rsp+230h+LastError], 57h ; 'W'
0x18000b05b  call    _lambda_cb80d53bc1f4542c2acac4cfc40ddcc6___operator__
0x18000b060  cmp     [rsp+230h+var_1B8], 1
0x18000b065  jnz     short loc_18000B07F
0x18000b067  lea     rdx, [rbp+130h+ActivityId]
0x18000b06b  mov     [rsp+230h+var_1B8], 2
0x18000b073  lea     rcx, dword_18001D020
0x18000b07a  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x18000b07f  mov     eax, 57h ; 'W'
0x18000b084  jmp     loc_18000B5B4
0x18000b089  xor     cl, cl
0x18000b08b  bts     ebx, 0Fh
0x18000b08f  mov     [rsp+230h+var_1F8], ebx
0x18000b093  jmp     short loc_18000B0B7
0x18000b095  xor     eax, eax
0x18000b097  cmp     ebx, 0FFFFh
0x18000b09d  cmovz   ebx, eax
0x18000b0a0  mov     [rsp+230h+var_1F8], ebx
0x18000b0a4  call    ?EtwpCacheMaxLogger@@YAXXZ; EtwpCacheMaxLogger(void)
0x18000b0a9  cmp     ebx, cs:?EtwpMaxLoggers@@3KA; ulong EtwpMaxLoggers
0x18000b0af  mov     rax, [rsp+230h+var_1E8]
0x18000b0b4  setnb   cl
0x18000b0b7  test    r13, r13
0x18000b0ba  jz      loc_18000B496
0x18000b0c0  cmp     [rsp+230h+var_1EC], 2
0x18000b0c5  ja      loc_18000B496
0x18000b0cb  dec     rax
0x18000b0ce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b0d2  ja      loc_18000B496
0x18000b0d8  test    cl, cl
0x18000b0da  jnz     loc_18000B496
0x18000b0e0  xor     edx, edx; Val
0x18000b0e2  lea     rcx, [rbp+130h+P]; void *
0x18000b0e6  lea     r8d, [rdx+78h]; Size
0x18000b0ea  call    memset_0
0x18000b0ef  mov     ecx, [rbp+130h+Timeout]
0x18000b0f5  mov     r8d, 8
0x18000b0fb  mov     dword ptr [rbp+130h+P], 3
0x18000b102  mov     dword ptr [rbp+130h+P+4], 78h ; 'x'
0x18000b109  mov     dword ptr [rbp+130h+var_148+8], 0FFFFFFFFh
0x18000b110  test    ecx, ecx
0x18000b112  jz      short loc_18000B12F
0x18000b114  test    r12b, r12b
0x18000b117  jz      short loc_18000B128
0x18000b119  movzx   eax, word ptr [rsp+230h+var_1E8]
0x18000b11e  sub     ax, r8w
0x18000b122  cmp     ax, 37h ; '7'
0x18000b126  jbe     short loc_18000B12F
0x18000b128  mov     byte ptr [rbp+130h+P+0Ch], 1
0x18000b12c  mov     dword ptr [rbp+130h+var_148], ecx
0x18000b12f  movups  xmm0, xmmword ptr [r13+0]
0x18000b134  movdqu  [rbp+130h+var_130], xmm0
0x18000b139  test    rdi, rdi
0x18000b13c  jz      short loc_18000B147
0x18000b13e  movups  xmm0, xmmword ptr [rdi+0Ch]
0x18000b142  movdqu  [rbp+130h+var_120], xmm0
0x18000b147  mov     al, [rsp+230h+var_1F0]
0x18000b14b  mov     r12, [rbp+130h+MatchAnyKeyword]
0x18000b152  mov     edx, [rsp+230h+var_1EC]
0x18000b156  mov     [rbp+130h+var_10C], al
0x18000b159  mov     rax, [rbp+130h+MatchAllKeyword]
0x18000b160  mov     qword ptr [rbp+130h+var_F8], rax
0x18000b164  mov     rax, qword ptr cs:SystemTraceControlGuid.Data1
0x18000b16b  mov     [rbp+130h+var_110], edx
0x18000b16e  mov     qword ptr [rbp+130h+var_108+8], r12
0x18000b172  mov     [rbp+130h+var_10A], bx
0x18000b176  mov     dword ptr [rbp+130h+var_108], r15d
0x18000b17a  cmp     rax, [r13+0]
0x18000b17e  jnz     short loc_18000B1D8
0x18000b180  mov     rax, qword ptr cs:SystemTraceControlGuid.Data4
0x18000b187  cmp     rax, [r13+8]
0x18000b18b  jnz     short loc_18000B1D8
0x18000b18d  cmp     edx, 2
0x18000b190  jnz     short loc_18000B1D8
0x18000b192  test    rsi, rsi
0x18000b195  jz      short loc_18000B1CB
0x18000b197  cmp     r14d, 1
0x18000b19b  jb      short loc_18000B1CB
0x18000b19d  cmp     dword ptr [rsi+0Ch], 80000001h
0x18000b1a4  jnz     short loc_18000B1B2
0x18000b1a6  cmp     dword ptr [rsi+8], 20h ; ' '
0x18000b1aa  ja      short loc_18000B1CB
0x18000b1ac  test    byte ptr [rsi+8], 3
0x18000b1b0  jmp     short loc_18000B1BF
0x18000b1b2  cmp     dword ptr [rsi+0Ch], 80000002h
0x18000b1b9  jnz     short loc_18000B1CB
0x18000b1bb  cmp     [rsi+8], r8d
0x18000b1bf  jnz     short loc_18000B1CB
0x18000b1c1  mov     ecx, r14d
0x18000b1c4  shl     ecx, 4
0x18000b1c7  xor     edx, edx
0x18000b1c9  jmp     short loc_18000B1FA
0x18000b1cb  mov     [rsp+230h+LastError], 57h ; 'W'
0x18000b1d3  jmp     loc_18000B4AD
0x18000b1d8  lea     rdi, [rbp+130h+P]
0x18000b1dc  test    r14d, r14d
0x18000b1df  jz      loc_18000B2FE
0x18000b1e5  test    edx, edx
0x18000b1e7  jz      loc_18000B2FE
0x18000b1ed  mov     ecx, r14d
0x18000b1f0  xor     edx, edx
0x18000b1f2  shl     ecx, 4
0x18000b1f5  test    r14d, r14d
0x18000b1f8  jz      short loc_18000B20B
0x18000b1fa  mov     eax, edx
0x18000b1fc  inc     edx
0x18000b1fe  shl     rax, 4
0x18000b202  add     ecx, [rax+rsi+8]
0x18000b206  cmp     edx, r14d
0x18000b209  jb      short loc_18000B1FA
0x18000b20b  lea     ebx, [rcx+78h]
0x18000b20e  xor     edx, edx; Flags
0x18000b210  mov     rcx, gs:60h
0x18000b219  mov     r8d, ebx; Size
0x18000b21c  mov     rcx, [rcx+30h]; HeapHandle
0x18000b220  call    RtlAllocateHeap_0
0x18000b225  mov     rdi, rax
0x18000b228  test    rax, rax
0x18000b22b  jnz     short loc_18000B23A
0x18000b22d  mov     [rsp+230h+LastError], 0Eh
0x18000b235  jmp     loc_18000B4A9
0x18000b23a  mov     dword ptr [rbp+130h+P+4], ebx
0x18000b23d  lea     r13, [rax+78h]
0x18000b241  movups  xmm0, [rbp+130h+P]
0x18000b245  mov     [rbp+130h+var_E4], r14d
0x18000b249  mov     r15d, r14d
0x18000b24c  movups  xmmword ptr [rax], xmm0
0x18000b24f  shl     r15, 4
  ... truncated ...
```
