# ControlTraceW

- ea: `0x18000a300`
- end: `0x18000ad5c`
- name: `ControlTraceW`
- size: `2652`
- prototype: `ULONG __stdcall(TRACEHANDLE TraceHandle, LPCWSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties, ULONG ControlCode)`
- caller_count: `6`
- callee_count: `25`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800026f0`
- `0x180002720`
- `0x180002770`
- `0x18000935c`
- `0x18000d5d0`
- `0x18000fe48`

## callees

- `0x180001008`
- `0x180001560`
- `0x180001e82`
- `0x180001eb2`
- `0x180001eca`
- `0x180001ee2`
- `0x180001ff0`
- `0x180002014`
- `0x180002020`
- `0x180002ec4`
- `0x180006180`
- `0x180008bb4`
- `0x180008e3c`
- `0x180009228`
- `0x180009308`
- `0x1800098ec`
- `0x18000a300`
- `0x180013138`
- `0x1800131ec`
- `0x180013284`
- `0x18001349c`
- `0x180013504`
- `0x1800138d0`
- `0x180013bc8`
- `0x18001581c`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18000ad07`
- `ntdll!RtlSetLastWin32Error` at `0x18000ad07`
- `ntdll!RtlInitUnicodeString` at `0x18000a74c`
- `ntdll!RtlInitUnicodeString` at `0x18000a74c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a39d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a39d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000a7fa`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000a7fa`

## pseudocode

```c
ULONG __stdcall ControlTraceW(
        TRACEHANDLE TraceHandle,
        LPCWSTR InstanceName,
        PEVENT_TRACE_PROPERTIES Properties,
        ULONG ControlCode)
{
  ULONG v4; // r13d
  const wchar_t *v6; // r15
  TRACEHANDLE v7; // rbx
  _DWORD *v8; // r14
  __int64 v9; // rsi
  __int64 *v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // r12d
  __int64 v14; // rbx
  __int64 v15; // rax
  bool v16; // al
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  __int16 v21; // r14
  unsigned int v22; // r13d
  char *v23; // rax
  char *v24; // rsi
  _WORD *v25; // rbx
  __int64 v26; // rax
  PCWSTR v27; // r11
  const WCHAR *v28; // r12
  DWORD v29; // ebx
  unsigned __int64 v30; // r13
  WCHAR *v31; // rax
  DWORD FullPathNameW; // eax
  DWORD v33; // r13d
  unsigned __int16 *v34; // rcx
  ULONG LogFileMode; // ecx
  ULONG v36; // eax
  ULONG v37; // eax
  ULONG v38; // eax
  ULONG v39; // eax
  ULONG v40; // eax
  NTSTATUS v41; // eax
  NTSTATUS updated; // eax
  int v43; // r9d
  __int64 v44; // r8
  struct _EVENT_TRACE_PROPERTIES *v45; // rcx
  unsigned int v46; // ebx
  unsigned int v47; // eax
  struct _WMI_LOGGER_INFORMATION *v48; // rcx
  ULONG LoggerNameOffset; // eax
  ULONG v50; // edx
  unsigned int v51; // r8d
  ULONG LogFileNameOffset; // ecx
  __int64 v53; // r15
  ULONG v54; // ecx
  unsigned __int64 v55; // r12
  ULONG v56; // eax
  char *v57; // rbx
  ULONG v58; // ecx
  __int64 v59; // rdx
  ULONG v60; // eax
  unsigned __int64 v61; // r15
  unsigned __int64 v62; // r13
  char *v63; // rbx
  ULONG v64; // ebx
  ULONG LastError; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v67; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v68; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR lpBuffer; // [rsp+40h] [rbp-C0h]
  ULONG v70; // [rsp+48h] [rbp-B8h]
  TRACEHANDLE v71; // [rsp+50h] [rbp-B0h]
  int v72; // [rsp+58h] [rbp-A8h]
  unsigned int v73; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v74; // [rsp+60h] [rbp-A0h]
  TRACEHANDLE v75; // [rsp+68h] [rbp-98h] BYREF
  struct _EVENT_FILTER_DESCRIPTOR *v76; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR v77; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v78[2]; // [rsp+80h] [rbp-80h] BYREF
  char v79; // [rsp+90h] [rbp-70h]
  int v80; // [rsp+98h] [rbp-68h] BYREF
  char v81; // [rsp+9Ch] [rbp-64h]
  GUID ActivityId; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v83[32]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v84; // [rsp+E0h] [rbp-20h]
  __int64 v85; // [rsp+E8h] [rbp-18h]
  TRACEHANDLE *v86; // [rsp+F0h] [rbp-10h]
  __int64 v87; // [rsp+F8h] [rbp-8h]
  unsigned int *v88; // [rsp+100h] [rbp+0h]
  __int64 v89; // [rsp+108h] [rbp+8h]
  LPCWSTR *v90; // [rsp+110h] [rbp+10h]
  __int64 v91; // [rsp+118h] [rbp+18h]

  v70 = ControlCode;
  v4 = ControlCode;
  v77 = InstanceName;
  v71 = TraceHandle;
  v6 = InstanceName;
  LastError = 0;
  v7 = TraceHandle;
  v76 = 0;
  v8 = 0;
  v67 = 0;
  lpBuffer = 0;
  v73 = 0;
  v80 = 0;
  v81 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v9 = -1;
  v80 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    v68 = v4;
    v75 = v7;
    v89 = 4;
    v88 = &v68;
    v86 = &v75;
    v87 = 8;
    if ( v6 )
    {
      v10 = (__int64 *)v6;
      v11 = -1;
      do
        ++v11;
      while ( v6[v11] );
      v12 = 2 * v11 + 2;
    }
    else
    {
      v10 = &qword_180017B18;
      v12 = 2;
    }
    v85 = v12;
    v84 = (unsigned int *)v10;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)&word_180019196,
      (__int64)&ActivityId,
      0,
      5,
      (__int64)v83);
  }
  v79 = 1;
  v78[0] = &v80;
  v78[1] = &LastError;
  if ( !Properties )
  {
    LastError = 87;
LABEL_111:
    if ( (unsigned int)dword_18001D020 > 2 && (qword_18001D030 & 2) != 0 && (qword_18001D038 & 2) == qword_18001D038 )
    {
      LODWORD(v75) = LastError;
      v90 = &v77;
      v77 = (LPCWSTR)v7;
      v68 = v4;
      v91 = 8;
      if ( v6 )
      {
        do
          ++v9;
        while ( v6[v9] );
        v47 = 2 * v9 + 2;
      }
      else
      {
        v6 = (const wchar_t *)&qword_180017B18;
        v47 = 2;
      }
      v89 = v47;
      v88 = (unsigned int *)v6;
      v86 = &v75;
      v84 = &v68;
      v87 = 4;
      v85 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_18001D020,
        (unsigned __int8 *)byte_180019145,
        0,
        0,
        6,
        (__int64)v83);
    }
LABEL_142:
    if ( v8 )
      goto LABEL_143;
    goto LABEL_144;
  }
  LastError = EtwpValidateTraceProperties(Properties, &v67, &v76, &v73);
  if ( LastError )
    goto LABEL_106;
  v13 = 1024;
  v72 = 1024;
  if ( !v6 )
    goto LABEL_26;
  v14 = -1;
  do
    ++v14;
  while ( v6[v14] );
  if ( wcsicmp(v6, L"NT Kernel Logger") )
  {
    if ( *(_QWORD *)&Properties->Wnode.Guid.Data1 == *(_QWORD *)&SystemTraceControlGuid.Data1
      && *(_QWORD *)Properties->Wnode.Guid.Data4 == *(_QWORD *)SystemTraceControlGuid.Data4 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v6[v18] );
      if ( v18 )
      {
        LastError = 87;
        goto LABEL_110;
      }
    }
  }
  else
  {
    Properties->Wnode.Guid = SystemTraceControlGuid;
  }
  v13 = v14 + 1;
  v72 = v14 + 1;
  if ( wcsicmp(v6, L"Circular Kernel Context Logger") )
  {
    if ( *(_OWORD *)&Properties->Wnode.Guid != CKCLGuid )
      goto LABEL_25;
    v19 = -1;
    do
      ++v19;
    while ( v6[v19] );
    if ( !v19 )
      goto LABEL_25;
    LastError = 87;
LABEL_110:
    v7 = v71;
    goto LABEL_111;
  }
  Properties->Wnode.Guid = (GUID)CKCLGuid;
LABEL_25:
  v7 = v71;
LABEL_26:
  v15 = *(_QWORD *)&Properties->Wnode.Guid.Data1 - *(_QWORD *)&SystemTraceControlGuid.Data1;
  if ( !v15 )
    v15 = *(_QWORD *)Properties->Wnode.Guid.Data4 - *(_QWORD *)SystemTraceControlGuid.Data4;
  v16 = v15 == 0;
  if ( !v7 && !v16 )
  {
    if ( !v6 )
      goto LABEL_34;
    v17 = -1;
    do
      ++v17;
    while ( v6[v17] );
    if ( !v17 )
      goto LABEL_34;
  }
  if ( (Properties->LogFileMode & 4) != 0 && v4 == 2 && Properties->LogFileNameOffset )
  {
LABEL_34:
    LastError = 87;
    goto LABEL_111;
  }
  LODWORD(v20) = 1024;
  while ( 1 )
  {
    while ( 1 )
    {
      v21 = v20 + 16;
      LODWORD(v75) = v20 + 16;
      v22 = (2 * (v20 + 16 + v13) + 183) & 0xFFFFFFF8;
      v74 = v22;
      v68 = v22;
      if ( v70 == 2 )
      {
        LastError = EtwpCheckFlagExtensions(Properties, &v68);
        if ( LastError )
        {
          v8 = 0;
          goto LABEL_106;
        }
        v22 = v68;
        v74 = v68;
      }
      v23 = (char *)operator new(v22, (const struct std::nothrow_t *)&std::nothrow);
      v24 = v23;
      if ( !v23 )
      {
        v8 = 0;
LABEL_118:
        v9 = -1;
        LastError = 8;
        goto LABEL_109;
      }
      memset_0(v23, 0, v22);
      v25 = v24 + 144;
      *((_OWORD *)v24 + 9) = 0;
      *((_WORD *)v24 + 73) = 2 * v13;
      *((_QWORD *)v24 + 19) = v24 + 176;
      *((_OWORD *)v24 + 8) = 0;
      *((_WORD *)v24 + 65) = 2 * v21;
      *((_QWORD *)v24 + 17) = &v24[2 * v13 + 176];
      if ( v6 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v6[v26] );
        if ( v26 )
        {
          StringCchCopyW((unsigned __int16 *)v24 + 88, v13, v6);
          RtlInitUnicodeString((PUNICODE_STRING)v24 + 9, v27);
        }
      }
      if ( Properties->LogFileNameOffset < v73 )
      {
        v8 = v24;
        goto LABEL_81;
      }
      v28 = (const WCHAR *)((char *)Properties + Properties->LogFileNameOffset);
      if ( wcsncmp_0(v28, L"%SystemRoot%", 0xCu) && wcsncmp_0(v28, L"%DriverData%", 0xCu) )
      {
        v29 = 1024;
        v8 = v24;
        while ( 1 )
        {
          v30 = 2LL * v29;
          if ( !is_mul_ok(v29, 2u) )
            v30 = -1;
          v31 = (WCHAR *)operator new(v30, (const struct std::nothrow_t *)&std::nothrow);
          lpBuffer = v31;
          if ( !v31 )
            break;
          memset_0(v31, 0, v30);
          FullPathNameW = GetFullPathNameW(v28, v29, lpBuffer, 0);
          v33 = FullPathNameW;
          if ( !FullPathNameW )
            goto LABEL_70;
          if ( FullPathNameW <= v29 )
          {
            v28 = lpBuffer;
LABEL_70:
            v22 = v74;
            goto LABEL_71;
          }
          operator delete(lpBuffer);
          v29 = v33;
        }
        lpBuffer = 0;
        goto LABEL_118;
      }
      v8 = v24;
LABEL_71:
      v20 = -1;
      do
        ++v20;
      while ( v28[v20] );
      v34 = (unsigned __int16 *)((char *)v8 + *((unsigned __int16 *)v24 + 73) + 176);
      *((_QWORD *)v24 + 17) = v34;
      if ( (unsigned int)v20 < (unsigned int)v75 )
        break;
      operator delete(v8);
      v13 = v72;
      if ( lpBuffer )
        goto LABEL_75;
    }
    if ( (_DWORD)v20 )
    {
      *((_WORD *)v24 + 64) = 2 * v20;
      StringCchCopyW(v34, (unsigned int)(v20 + 1), v28);
      v25 = v24 + 144;
    }
    else
    {
      v25 = v24 + 144;
      *((_WORD *)v24 + 64) = 0;
    }
LABEL_81:
    LogFileMode = Properties->LogFileMode;
    *((_DWORD *)v24 + 11) |= 0x20000u;
    v36 = v70;
    *((_QWORD *)v24 + 1) = v71;
    v8[16] = LogFileMode;
    *(_DWORD *)v24 = v22;
    *(GUID *)(v24 + 24) = Properties->Wnode.Guid;
    if ( v36 )
    {
      v37 = v36 - 1;
      if ( v37 )
      {
        v38 = v37 - 1;
        if ( v38 )
        {
          v39 = v38 - 1;
          if ( v39 )
          {
            v40 = v39 - 1;
            if ( v40 )
            {
              if ( v40 != 1 )
              {
                LastError = 87;
                goto LABEL_107;
              }
              v8[17] = Properties->FlushTimer;
              LODWORD(v75) = 0;
              if ( (LogFileMode & 0x800) != 0 || (v24[11] & 1) != 0 )
              {
                updated = 87;
              }
              else
              {
                v41 = NtTraceControl_0(7, v8, v22, v8, v22, &v75);
                updated = v41 ? RtlNtStatusToDosError_0(v41) : 0;
              }
            }
            else
            {
              updated = EtwpIncrementLoggerFile((struct _WMI_LOGGER_INFORMATION *)v8, v67, v76);
            }
          }
          else
          {
            updated = EtwpFlushLogger((struct _WMI_LOGGER_INFORMATION *)v8, v67, v76);
          }
        }
        else
        {
          EtwpCopyPropertiesToInfo(Properties, (struct _WMI_LOGGER_INFORMATION *)v8);
          *((_DWORD *)v24 + 11) |= v43;
          *((_QWORD *)v24 + 1) = v44;
          LastError = EtwpCopyFlagExtensions(v45, (struct _WMI_LOGGER_INFORMATION *)v8, v22);
          if ( LastError )
            goto LABEL_106;
          updated = EtwpUpdateLogger((struct _WMI_LOGGER_INFORMATION *)v8, v67, v76);
        }
      }
      else
      {
        if ( (LogFileMode & 0x10000) != 0 )
        {
          v8[26] = Properties->EventsLost;
          v8[28] = Properties->LogBuffersLost;
          if ( (LogFileMode & 0x1000) != 0 )
            *((_QWORD *)v24 + 2) = Properties->Wnode.KernelHandle;
        }
        updated = EtwpStopLogger((struct _WMI_LOGGER_INFORMATION *)v8, v67, v76);
      }
    }
    else
    {
      updated = EtwpQueryLogger((struct _WMI_LOGGER_INFORMATION *)v8, v67, v76);
    }
    LastError = updated;
    if ( updated != 234 )
      break;
    v46 = *((unsigned __int16 *)v24 + 65);
    v13 = *((unsigned __int16 *)v24 + 73) >> 1;
    v72 = v13;
    LODWORD(v20) = v46 >> 1;
    operator delete(v8);
    if ( lpBuffer )
    {
LABEL_75:
      operator delete(lpBuffer);
      lpBuffer = 0;
    }
  }
  if ( updated )
  {
LABEL_107:
    if ( LastError == 234 )
      goto LABEL_142;
    v9 = -1;
LABEL_109:
    v4 = v70;
    goto LABEL_110;
  }
  EtwpCopyInfoToProperties((struct _WMI_LOGGER_INFORMATION *)v8, Properties);
  EtwpFixupLoggerStrings(v48);
  LoggerNameOffset = Properties->LoggerNameOffset;
  v50 = LoggerNameOffset;
  v51 = v73;
  LogFileNameOffset = Properties->LogFileNameOffset;
  if ( !LoggerNameOffset )
    v50 = v73;
  if ( v50 > LogFileNameOffset )
    LogFileNameOffset = Properties->Wnode.BufferSize;
  v53 = (unsigned __int16)*v25;
  v54 = LogFileNameOffset - v50;
  if ( *v25 )
  {
    v55 = v54;
    if ( v54 < (unsigned __int64)(v53 + 2) )
    {
      v56 = v73 + v53 + *((unsigned __int16 *)v24 + 64) + 4;
      goto LABEL_128;
    }
    Properties->LoggerNameOffset = v50;
    v57 = (char *)Properties + v50;
    memset_0(v57, 0, v54);
    StringCchCopyW((unsigned __int16 *)v57, v55 >> 1, *((const unsigned __int16 **)v24 + 19));
    v51 = v73;
    *(_WORD *)&v57[2 * ((unsigned __int64)(unsigned int)v53 >> 1)] = 0;
    LoggerNameOffset = Properties->LoggerNameOffset;
  }
  v58 = Properties->LogFileNameOffset;
  if ( !v58 )
    v58 = v53 + LoggerNameOffset + 2;
  if ( v58 > LoggerNameOffset )
    LoggerNameOffset = Properties->Wnode.BufferSize;
  v59 = *((unsigned __int16 *)v24 + 64);
  v60 = LoggerNameOffset - v58;
  if ( !*((_WORD *)v24 + 64) )
    goto LABEL_138;
  v61 = v60;
  v62 = *((unsigned __int16 *)v24 + 64);
  if ( v60 >= (unsigned __int64)(v59 + 2) )
  {
    Properties->LogFileNameOffset = v58;
    v63 = (char *)Properties + v58;
    memset_0(v63, 0, v60);
    StringCchCopyW((unsigned __int16 *)v63, v61 >> 1, *((const unsigned __int16 **)v24 + 17));
    *(_WORD *)&v63[2 * (v62 >> 1)] = 0;
LABEL_138:
    v6 = v77;
LABEL_106:
    if ( !LastError )
      goto LABEL_142;
    goto LABEL_107;
  }
  v56 = v51 + 2 * (v59 + 2);
LABEL_128:
  Properties->Wnode.Flags |= 0x20u;
  Properties->BufferSize = v56;
  LastError = 234;
LABEL_143:
  operator delete(v8);
LABEL_144:
  if ( lpBuffer )
    operator delete(lpBuffer);
  v64 = LastError;
  if ( LastError )
    RtlSetLastWin32Error(LastError);
  lambda_f720df457a3c04ff4338b25f894e64cd_::operator()(v78);
  if ( v80 == 1 )
  {
    v80 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
  }
  return v64;
}

```

## disassembly

```asm
0x18000a300  mov     [rsp-8+arg_0], rbx
0x18000a305  push    rbp
0x18000a306  push    rsi
0x18000a307  push    rdi
0x18000a308  push    r12
0x18000a30a  push    r13
0x18000a30c  push    r14
0x18000a30e  push    r15
0x18000a310  lea     rbp, [rsp-30h]
0x18000a315  sub     rsp, 130h
0x18000a31c  mov     rax, cs:__security_cookie
0x18000a323  xor     rax, rsp
0x18000a326  mov     [rbp+60h+var_40], rax
0x18000a32a  mov     eax, cs:dword_18001D020
0x18000a330  xor     r12d, r12d
0x18000a333  mov     [rsp+160h+var_118], r9d
0x18000a338  mov     r13d, r9d
0x18000a33b  mov     [rsp+160h+var_E8], rdx
0x18000a340  mov     rdi, r8
0x18000a343  mov     [rsp+160h+var_110], rcx
0x18000a348  mov     r15, rdx
0x18000a34b  mov     [rsp+160h+LastError], r12d
0x18000a350  mov     rbx, rcx
0x18000a353  mov     [rsp+160h+var_F0], r12
0x18000a358  mov     r14d, r12d
0x18000a35b  mov     [rsp+160h+var_12C], r12d
0x18000a360  mov     [rsp+160h+lpBuffer], r12
0x18000a365  mov     [rsp+160h+var_104], r12d
0x18000a36a  mov     [rbp+60h+var_C8], r12d
0x18000a36e  mov     [rbp+60h+var_C4], r12b
0x18000a372  cmp     eax, 5
0x18000a375  jbe     short loc_18000A3A5
0x18000a377  mov     rcx, cs:qword_18001D038
0x18000a37e  mov     rax, cs:qword_18001D030
0x18000a385  test    al, 10h
0x18000a387  jz      short loc_18000A3A5
0x18000a389  mov     rax, rcx
0x18000a38c  and     eax, 10h
0x18000a38f  cmp     rax, rcx
0x18000a392  jnz     short loc_18000A3A5
0x18000a394  lea     rdx, [rbp+60h+ActivityId]; ActivityId
0x18000a398  lea     ecx, [r12+3]; ControlCode
0x18000a39d  call    cs:__imp_EventActivityIdControl
0x18000a3a3  jmp     short loc_18000A3AC
0x18000a3a5  xorps   xmm0, xmm0
0x18000a3a8  movups  xmmword ptr [rbp+60h+ActivityId.Data1], xmm0
0x18000a3ac  mov     eax, cs:dword_18001D020
0x18000a3b2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a3b6  mov     [rbp+60h+var_C8], 1
0x18000a3bd  cmp     eax, 5
0x18000a3c0  jbe     loc_18000A49B
0x18000a3c6  mov     rcx, cs:qword_18001D038
0x18000a3cd  mov     rax, cs:qword_18001D030
0x18000a3d4  test    al, 10h
0x18000a3d6  jz      loc_18000A49B
0x18000a3dc  mov     rax, rcx
0x18000a3df  and     eax, 10h
0x18000a3e2  cmp     rax, rcx
0x18000a3e5  jnz     loc_18000A49B
0x18000a3eb  mov     [rsp+160h+var_128], r13d
0x18000a3f0  mov     [rsp+160h+var_F8], rbx
0x18000a3f5  cmp     [rbp+60h+var_C4], r12b
0x18000a3f9  jz      short loc_18000A419
0x18000a3fb  cmp     [rbp+60h+var_B0], r12d
0x18000a3ff  jnz     short loc_18000A413
0x18000a401  cmp     [rbp+60h+var_AC], r12d
0x18000a405  jnz     short loc_18000A413
0x18000a407  cmp     [rbp+60h+var_A8], r12d
0x18000a40b  jnz     short loc_18000A413
0x18000a40d  cmp     [rbp+60h+var_A4], r12d
0x18000a411  jz      short loc_18000A419
0x18000a413  lea     r9, [rbp+60h+var_B0]
0x18000a417  jmp     short loc_18000A41C
0x18000a419  mov     r9, r12
0x18000a41c  mov     [rbp+60h+var_58], 4
0x18000a424  lea     rax, [rsp+160h+var_128]
0x18000a429  mov     [rbp+60h+var_60], rax
0x18000a42d  lea     rax, [rsp+160h+var_F8]
0x18000a432  mov     [rbp+60h+var_70], rax
0x18000a436  mov     [rbp+60h+var_68], 8
0x18000a43e  test    r15, r15
0x18000a441  jz      short loc_18000A45C
0x18000a443  mov     rcx, r15
0x18000a446  mov     rax, rsi
0x18000a449  inc     rax
0x18000a44c  cmp     [r15+rax*2], r12w
0x18000a451  jnz     short loc_18000A449
0x18000a453  lea     eax, ds:2[rax*2]
0x18000a45a  jmp     short loc_18000A468
0x18000a45c  lea     rcx, qword_180017B18
0x18000a463  mov     eax, 2
0x18000a468  mov     dword ptr [rbp+60h+var_78], eax
0x18000a46b  lea     r8, [rbp+60h+ActivityId]
0x18000a46f  lea     rax, [rbp+60h+var_A0]
0x18000a473  mov     [rbp+60h+var_80], rcx
0x18000a477  mov     [rsp+160h+var_138], rax
0x18000a47c  lea     rdx, word_180019196
0x18000a483  lea     rcx, dword_18001D020
0x18000a48a  mov     [rsp+160h+var_140], 5
0x18000a492  mov     dword ptr [rbp+60h+var_78+4], r12d
0x18000a496  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000a49b  mov     [rbp+60h+var_D0], 1
0x18000a49f  lea     rax, [rbp+60h+var_C8]
0x18000a4a3  mov     [rbp+60h+var_E0], rax
0x18000a4a7  lea     rax, [rsp+160h+LastError]
0x18000a4ac  mov     [rbp+60h+var_D8], rax
0x18000a4b0  test    rdi, rdi
0x18000a4b3  jnz     short loc_18000A4C2
0x18000a4b5  mov     [rsp+160h+LastError], 57h ; 'W'
0x18000a4bd  jmp     loc_18000AAB4
0x18000a4c2  lea     r9, [rsp+160h+var_104]; unsigned int *
0x18000a4c7  mov     rcx, rdi; struct _EVENT_TRACE_PROPERTIES *
0x18000a4ca  lea     r8, [rsp+160h+var_F0]; struct _EVENT_FILTER_DESCRIPTOR **
0x18000a4cf  lea     rdx, [rsp+160h+var_12C]; unsigned int *
0x18000a4d4  call    ?EtwpValidateTraceProperties@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAKPEAPEAU_EVENT_FILTER_DESCRIPTOR@@1@Z; EtwpValidateTraceProperties(_EVENT_TRACE_PROPERTIES *,ulong *,_EVENT_FILTER_DESCRIPTOR * *,ulong *)
0x18000a4d9  mov     [rsp+160h+LastError], eax
0x18000a4dd  test    eax, eax
0x18000a4df  jnz     loc_18000AA8D
0x18000a4e5  xor     ecx, ecx
0x18000a4e7  mov     r12d, 400h
0x18000a4ed  mov     [rsp+160h+var_108], r12d
0x18000a4f2  test    r15, r15
0x18000a4f5  jz      short loc_18000A55D
0x18000a4f7  mov     rbx, rsi
0x18000a4fa  xor     r12d, r12d
0x18000a4fd  inc     rbx
0x18000a500  cmp     [r15+rbx*2], r12w
0x18000a505  jnz     short loc_18000A4FD
0x18000a507  lea     rdx, aNtKernelLogger_0; "NT Kernel Logger"
0x18000a50e  mov     rcx, r15; String1
0x18000a511  call    _wcsicmp
0x18000a516  test    eax, eax
0x18000a518  jnz     loc_18000A5B7
0x18000a51e  movups  xmm0, xmmword ptr cs:SystemTraceControlGuid.Data1
0x18000a525  movdqu  xmmword ptr [rdi+18h], xmm0
0x18000a52a  lea     r12d, [rbx+1]
0x18000a52e  mov     rcx, r15; String1
0x18000a531  lea     rdx, aCircularKernel_0; "Circular Kernel Context Logger"
0x18000a538  mov     [rsp+160h+var_108], r12d
0x18000a53d  call    _wcsicmp
0x18000a542  xor     ecx, ecx
0x18000a544  test    eax, eax
0x18000a546  jnz     loc_18000A5FC
0x18000a54c  movups  xmm0, cs:CKCLGuid
0x18000a553  movdqu  xmmword ptr [rdi+18h], xmm0
0x18000a558  mov     rbx, [rsp+160h+var_110]
0x18000a55d  mov     rax, [rdi+18h]
0x18000a561  sub     rax, qword ptr cs:SystemTraceControlGuid.Data1
0x18000a568  jnz     short loc_18000A575
0x18000a56a  mov     rax, [rdi+20h]
0x18000a56e  sub     rax, qword ptr cs:SystemTraceControlGuid.Data4
0x18000a575  test    rax, rax
0x18000a578  setz    al
0x18000a57b  test    rbx, rbx
0x18000a57e  jnz     loc_18000A644
0x18000a584  test    al, al
0x18000a586  jnz     loc_18000A644
0x18000a58c  test    r15, r15
0x18000a58f  jz      short loc_18000A5A7
0x18000a591  mov     rax, rsi
0x18000a594  inc     rax
0x18000a597  cmp     [r15+rax*2], cx
0x18000a59c  jnz     short loc_18000A594
0x18000a59e  test    rax, rax
0x18000a5a1  jnz     loc_18000A644
0x18000a5a7  mov     [rsp+160h+LastError], 57h ; 'W'
0x18000a5af  xor     r12d, r12d
0x18000a5b2  jmp     loc_18000AAB4
0x18000a5b7  mov     rax, [rdi+18h]
0x18000a5bb  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data1
0x18000a5c2  jnz     loc_18000A52A
0x18000a5c8  mov     rax, [rdi+20h]
0x18000a5cc  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data4
0x18000a5d3  jnz     loc_18000A52A
0x18000a5d9  mov     rax, rsi
0x18000a5dc  inc     rax
0x18000a5df  cmp     [r15+rax*2], r12w
0x18000a5e4  jnz     short loc_18000A5DC
0x18000a5e6  test    rax, rax
0x18000a5e9  jz      loc_18000A52A
0x18000a5ef  mov     [rsp+160h+LastError], 57h ; 'W'
0x18000a5f7  jmp     loc_18000AAAF
0x18000a5fc  mov     rax, [rdi+18h]
0x18000a600  cmp     rax, qword ptr cs:CKCLGuid
0x18000a607  jnz     loc_18000A558
0x18000a60d  mov     rax, [rdi+20h]
0x18000a611  cmp     rax, qword ptr cs:CKCLGuid+8
0x18000a618  jnz     loc_18000A558
0x18000a61e  mov     rax, rsi
0x18000a621  inc     rax
0x18000a624  cmp     [r15+rax*2], cx
0x18000a629  jnz     short loc_18000A621
0x18000a62b  test    rax, rax
0x18000a62e  jz      loc_18000A558
0x18000a634  mov     [rsp+160h+LastError], 57h ; 'W'
0x18000a63c  xor     r12d, r12d
0x18000a63f  jmp     loc_18000AAAF
0x18000a644  test    byte ptr [rdi+40h], 4
0x18000a648  jz      short loc_18000A659
0x18000a64a  cmp     r13d, 2
0x18000a64e  jnz     short loc_18000A659
0x18000a650  cmp     [rdi+70h], ecx
0x18000a653  ja      loc_18000A5A7
0x18000a659  mov     ebx, 400h
0x18000a65e  lea     r14d, [rbx+10h]
0x18000a662  lea     eax, [r14+r12]
0x18000a666  mov     dword ptr [rsp+160h+var_F8], r14d
0x18000a66b  lea     r13d, ds:0B7h[rax*2]
0x18000a673  and     r13d, 0FFFFFFF8h
0x18000a677  cmp     [rsp+160h+var_118], 2
0x18000a67c  mov     [rsp+160h+var_100], r13d
0x18000a681  mov     [rsp+160h+var_128], r13d
0x18000a686  jnz     short loc_18000A6AB
0x18000a688  lea     rdx, [rsp+160h+var_128]; unsigned int *
0x18000a68d  mov     rcx, rdi; struct _EVENT_TRACE_PROPERTIES *
0x18000a690  call    ?EtwpCheckFlagExtensions@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAK@Z; EtwpCheckFlagExtensions(_EVENT_TRACE_PROPERTIES *,ulong *)
0x18000a695  mov     [rsp+160h+LastError], eax
0x18000a699  test    eax, eax
0x18000a69b  jnz     loc_18000AA87
0x18000a6a1  mov     r13d, [rsp+160h+var_128]
0x18000a6a6  mov     [rsp+160h+var_100], r13d
0x18000a6ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a6b2  mov     ecx, r13d; unsigned __int64
0x18000a6b5  mov     ebx, r13d
0x18000a6b8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a6bd  mov     rsi, rax
0x18000a6c0  test    rax, rax
0x18000a6c3  jz      loc_18000AC73
0x18000a6c9  mov     r8d, ebx; Size
0x18000a6cc  xor     edx, edx; Val
0x18000a6ce  mov     rcx, rax; void *
0x18000a6d1  call    memset_0
0x18000a6d6  lea     rbx, [rsi+90h]
0x18000a6dd  mov     edx, r12d; unsigned __int64
0x18000a6e0  movzx   ecx, r12w
0x18000a6e4  lea     r11, [rsi+0B0h]
0x18000a6eb  xorps   xmm0, xmm0
0x18000a6ee  add     cx, cx
0x18000a6f1  movups  xmmword ptr [rbx], xmm0
0x18000a6f4  mov     [rbx+2], cx
0x18000a6f8  movzx   eax, r14w
0x18000a6fc  add     ax, ax
0x18000a6ff  mov     [rbx+8], r11
0x18000a703  movups  xmmword ptr [rsi+80h], xmm0
0x18000a70a  mov     [rsi+82h], ax
0x18000a711  xor     r12d, r12d
0x18000a714  lea     rax, [rdx+58h]
0x18000a718  lea     rax, [rsi+rax*2]
0x18000a71c  mov     [rsi+88h], rax
0x18000a723  test    r15, r15
0x18000a726  jz      short loc_18000A752
0x18000a728  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a72c  inc     rax
0x18000a72f  cmp     [r15+rax*2], r12w
0x18000a734  jnz     short loc_18000A72C
0x18000a736  test    rax, rax
0x18000a739  jz      short loc_18000A752
0x18000a73b  mov     r8, r15; unsigned __int16 *
0x18000a73e  mov     rcx, r11; unsigned __int16 *
0x18000a741  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a746  mov     rdx, r11; SourceString
0x18000a749  mov     rcx, rbx; DestinationString
0x18000a74c  call    cs:__imp_RtlInitUnicodeString
0x18000a752  mov     eax, [rsp+160h+var_104]
0x18000a756  cmp     [rdi+70h], eax
0x18000a759  jb      loc_18000A8CB
0x18000a75f  mov     r12d, [rdi+70h]
0x18000a763  lea     rdx, aSystemroot; "%SystemRoot%"
0x18000a76a  add     r12, rdi
0x18000a76d  mov     ebx, 0Ch
0x18000a772  mov     rcx, r12; String1
0x18000a775  mov     r8d, ebx; MaxCount
0x18000a778  call    wcsncmp_0
0x18000a77d  xor     edx, edx
0x18000a77f  test    eax, eax
0x18000a781  jz      loc_18000A88A
0x18000a787  mov     r8d, ebx; MaxCount
0x18000a78a  lea     rdx, aDriverdata_0; "%DriverData%"
0x18000a791  mov     rcx, r12; String1
0x18000a794  call    wcsncmp_0
0x18000a799  xor     edx, edx
0x18000a79b  test    eax, eax
0x18000a79d  jz      loc_18000A88A
0x18000a7a3  mov     ebx, 400h
0x18000a7a8  mov     r14, rsi
0x18000a7ab  mov     ecx, ebx
0x18000a7ad  mov     eax, 2
0x18000a7b2  mul     rcx
0x18000a7b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a7bc  mov     r13, rax
0x18000a7bf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a7c6  cmovb   r13, rax
0x18000a7ca  mov     rcx, r13; unsigned __int64
0x18000a7cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a7d2  mov     [rsp+160h+lpBuffer], rax
0x18000a7d7  test    rax, rax
0x18000a7da  jz      loc_18000AB2A
0x18000a7e0  mov     r8, r13; Size
0x18000a7e3  xor     edx, edx; Val
0x18000a7e5  mov     rcx, rax; void *
  ... truncated ...
```
