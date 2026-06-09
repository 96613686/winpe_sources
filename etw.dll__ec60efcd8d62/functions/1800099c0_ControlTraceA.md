# ControlTraceA

- ea: `0x1800099c0`
- end: `0x18000a2eb`
- name: `ControlTraceA`
- size: `2347`
- prototype: `ULONG __stdcall(TRACEHANDLE TraceHandle, LPCSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties, ULONG ControlCode)`
- caller_count: `5`
- callee_count: `23`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800026d0`
- `0x180002710`
- `0x180002730`
- `0x180002750`
- `0x18000935c`

## callees

- `0x180001008`
- `0x180001560`
- `0x180001e76`
- `0x180001eb2`
- `0x180001ee2`
- `0x180001ff0`
- `0x180002014`
- `0x180002020`
- `0x180002ec4`
- `0x180008b10`
- `0x180008e3c`
- `0x180009228`
- `0x180009308`
- `0x1800098ec`
- `0x1800099c0`
- `0x180013138`
- `0x1800131ec`
- `0x180013284`
- `0x18001349c`
- `0x180013504`
- `0x1800138d0`
- `0x180013bc8`
- `0x180015804`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x180009db3`
- `ntdll!RtlInitAnsiString` at `0x180009ed2`
- `ntdll!RtlInitAnsiString` at `0x180009db3`
- `ntdll!RtlInitAnsiString` at `0x180009ed2`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180009dc4`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180009ef4`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180009dc4`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180009ef4`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000a0b3`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000a1ab`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000a0b3`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000a1ab`
- `ntdll!RtlFreeAnsiString` at `0x18000a198`
- `ntdll!RtlFreeAnsiString` at `0x18000a257`
- `ntdll!RtlFreeAnsiString` at `0x18000a198`
- `ntdll!RtlFreeAnsiString` at `0x18000a257`
- `ntdll!RtlSetLastWin32Error` at `0x18000a28c`
- `ntdll!RtlSetLastWin32Error` at `0x18000a28c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009a56`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009a56`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180009e56`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180009e56`

## pseudocode

```c
ULONG __stdcall ControlTraceA(
        TRACEHANDLE TraceHandle,
        LPCSTR InstanceName,
        PEVENT_TRACE_PROPERTIES Properties,
        ULONG ControlCode)
{
  ULONG v4; // edi
  LPCSTR v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // r12d
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  bool v16; // al
  __int64 v17; // rax
  void *v18; // r13
  __int64 v19; // rsi
  __int16 v20; // r14
  ULONG v21; // eax
  ULONG v22; // esi
  char *v23; // rax
  char *v24; // rdi
  __int64 v25; // rax
  int v26; // eax
  unsigned int v27; // r12d
  const CHAR *v28; // r12
  unsigned int v29; // eax
  char *v30; // r14
  unsigned int v31; // esi
  void *v32; // rax
  DWORD FullPathNameA; // eax
  DWORD v34; // esi
  int v35; // eax
  ULONG v36; // r8d
  ULONG v37; // eax
  ULONG LogFileMode; // ecx
  ULONG v39; // eax
  ULONG v40; // eax
  ULONG v41; // eax
  NTSTATUS updated; // eax
  int v43; // r10d
  __int64 v44; // r9
  struct _EVENT_TRACE_PROPERTIES *v45; // rcx
  unsigned int v46; // r8d
  unsigned int v47; // esi
  __int64 Length; // r15
  struct _WMI_LOGGER_INFORMATION *v49; // rcx
  __int64 LoggerNameOffset; // rsi
  ULONG LogFileNameOffset; // edi
  __int64 v52; // rdi
  int v53; // r12d
  ULONG v54; // eax
  ULONG v55; // eax
  _BYTE *v56; // rsi
  PCHAR Buffer; // rdx
  __int64 v58; // rax
  _BYTE *v59; // rcx
  _BYTE *v60; // rax
  ULONG v61; // r12d
  ULONG BufferSize; // esi
  ULONG v63; // esi
  __int64 v64; // r15
  __int64 v65; // rdi
  ULONG v66; // edx
  _BYTE *v67; // rbx
  PCHAR v68; // rax
  _BYTE *v69; // rax
  ULONG v70; // ebx
  ULONG LastError; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v73; // [rsp+34h] [rbp-CCh]
  unsigned int v74; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v75; // [rsp+3Ch] [rbp-C4h] BYREF
  size_t Size; // [rsp+40h] [rbp-C0h]
  ULONG v77; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_FILTER_DESCRIPTOR *v78; // [rsp+50h] [rbp-B0h] BYREF
  PCUNICODE_STRING v79; // [rsp+58h] [rbp-A8h] BYREF
  NTSTATUS Status[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _STRING AnsiString; // [rsp+68h] [rbp-98h] BYREF
  _STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  TRACEHANDLE v83; // [rsp+88h] [rbp-78h]
  PCUNICODE_STRING SourceString; // [rsp+90h] [rbp-70h]
  _QWORD v85[2]; // [rsp+98h] [rbp-68h] BYREF
  char v86; // [rsp+A8h] [rbp-58h]
  int v87; // [rsp+B0h] [rbp-50h] BYREF
  char v88; // [rsp+B4h] [rbp-4Ch]
  GUID ActivityId; // [rsp+B8h] [rbp-48h] BYREF
  char v90[32]; // [rsp+E0h] [rbp-20h] BYREF
  LPCSTR v91; // [rsp+100h] [rbp+0h]
  int v92; // [rsp+108h] [rbp+8h]
  int v93; // [rsp+10Ch] [rbp+Ch]
  NTSTATUS *v94; // [rsp+110h] [rbp+10h]
  __int64 v95; // [rsp+118h] [rbp+18h]
  ULONG *v96; // [rsp+120h] [rbp+20h]
  __int64 v97; // [rsp+128h] [rbp+28h]

  v73 = ControlCode;
  v83 = TraceHandle;
  v4 = ControlCode;
  LastError = 0;
  v78 = 0;
  v74 = 0;
  v75 = 0;
  v87 = 0;
  v88 = 0;
  AnsiString = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v87 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    v77 = v4;
    *(_QWORD *)Status = TraceHandle;
    v97 = 4;
    v96 = &v77;
    v94 = Status;
    v95 = 8;
    if ( InstanceName )
    {
      v8 = InstanceName;
      v9 = -1;
      do
        ++v9;
      while ( InstanceName[v9] );
      v10 = v9 + 1;
    }
    else
    {
      v8 = (LPCSTR)&qword_180017D30;
      v10 = 1;
    }
    v92 = v10;
    v91 = v8;
    v93 = 0;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)byte_1800191FB,
      (__int64)&ActivityId,
      0,
      5,
      (__int64)v90);
  }
  v86 = 1;
  v85[0] = &v87;
  v85[1] = &LastError;
  AnsiString = 0;
  if ( !Properties )
    goto LABEL_142;
  LastError = EtwpValidateTraceProperties(Properties, &v74, &v78, &v75);
  if ( LastError )
    goto LABEL_137;
  Size = 0x40000000400LL;
  v11 = 1024;
  if ( InstanceName )
  {
    v12 = -1;
    do
      ++v12;
    while ( InstanceName[v12] );
    if ( (unsigned int)o__stricmp_0(InstanceName, "NT Kernel Logger") )
    {
      if ( *(_QWORD *)&Properties->Wnode.Guid.Data1 == *(_QWORD *)&SystemTraceControlGuid.Data1
        && *(_QWORD *)Properties->Wnode.Guid.Data4 == *(_QWORD *)SystemTraceControlGuid.Data4 )
      {
        v13 = -1;
        do
          ++v13;
        while ( InstanceName[v13] );
        if ( v13 )
          goto LABEL_142;
      }
    }
    else
    {
      Properties->Wnode.Guid = SystemTraceControlGuid;
    }
    v11 = v12 + 1;
    HIDWORD(Size) = v12 + 1;
    if ( !(unsigned int)o__stricmp_0(InstanceName, "Circular Kernel Context Logger") )
    {
      Properties->Wnode.Guid = (GUID)CKCLGuid;
LABEL_33:
      v4 = v73;
      goto LABEL_34;
    }
    if ( *(_OWORD *)&Properties->Wnode.Guid != CKCLGuid )
      goto LABEL_33;
    v14 = -1;
    do
      ++v14;
    while ( InstanceName[v14] );
    if ( !v14 )
      goto LABEL_33;
LABEL_142:
    LastError = 87;
    goto LABEL_137;
  }
LABEL_34:
  v15 = *(_QWORD *)&Properties->Wnode.Guid.Data1 - *(_QWORD *)&SystemTraceControlGuid.Data1;
  if ( !v15 )
    v15 = *(_QWORD *)Properties->Wnode.Guid.Data4 - *(_QWORD *)SystemTraceControlGuid.Data4;
  v16 = v15 == 0;
  if ( !TraceHandle && !v16 )
  {
    if ( !InstanceName )
      goto LABEL_142;
    v17 = -1;
    do
      ++v17;
    while ( InstanceName[v17] );
    if ( !v17 )
      goto LABEL_142;
  }
  if ( (Properties->LogFileMode & 4) != 0 && v4 == 2 && Properties->LogFileNameOffset )
    goto LABEL_142;
  v18 = 0;
  LODWORD(v19) = 1024;
  while ( 1 )
  {
    v20 = v19 + 16;
    Status[0] = v19 + 16;
    v21 = (2 * (v19 + 16 + v11) + 183) & 0xFFFFFFF8;
    v77 = v21;
    LODWORD(v79) = v21;
    if ( v4 == 2 )
    {
      LastError = EtwpCheckFlagExtensions(Properties, (unsigned int *)&v79);
      if ( LastError )
        goto LABEL_135;
      v21 = (unsigned int)v79;
      v77 = (unsigned int)v79;
    }
    v22 = v21;
    v23 = (char *)operator new(v21, (const struct std::nothrow_t *)&std::nothrow);
    v24 = v23;
    if ( !v23 )
      break;
    memset_0(v23, 0, v22);
    SourceString = (PCUNICODE_STRING)(v24 + 144);
    *((_OWORD *)v24 + 9) = 0;
    *((_WORD *)v24 + 73) = 2 * v11;
    *((_QWORD *)v24 + 19) = v24 + 176;
    v79 = (PCUNICODE_STRING)(v24 + 128);
    *((_OWORD *)v24 + 8) = 0;
    *((_WORD *)v24 + 65) = 2 * v20;
    *((_QWORD *)v24 + 17) = &v24[2 * v11 + 176];
    if ( InstanceName )
    {
      v25 = -1;
      do
        ++v25;
      while ( InstanceName[v25] );
      if ( v25 )
      {
        DestinationString = 0;
        RtlInitAnsiString(&DestinationString, InstanceName);
        v26 = RtlAnsiStringToUnicodeString((PUNICODE_STRING)v24 + 9, &DestinationString, 0);
        if ( v26 < 0 )
        {
          LastError = RtlNtStatusToDosError_0(v26);
          v30 = v24;
          goto LABEL_133;
        }
      }
    }
    v27 = v75;
    if ( Properties->LogFileNameOffset < v75 )
    {
      v30 = v24;
LABEL_73:
      v36 = v77;
      v37 = v73;
      *((_QWORD *)v24 + 1) = v83;
      LogFileMode = Properties->LogFileMode;
      *((_DWORD *)v24 + 11) |= 0x20000u;
      *((_DWORD *)v30 + 16) = LogFileMode;
      *(_DWORD *)v24 = v36;
      *(GUID *)(v24 + 24) = Properties->Wnode.Guid;
      if ( v37 )
      {
        v39 = v37 - 1;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( v40 )
          {
            v41 = v40 - 1;
            if ( v41 )
            {
              if ( v41 == 1 )
                updated = EtwpIncrementLoggerFile((struct _WMI_LOGGER_INFORMATION *)v30, v74, v78);
              else
                updated = 87;
            }
            else
            {
              updated = EtwpFlushLogger((struct _WMI_LOGGER_INFORMATION *)v30, v74, v78);
            }
          }
          else
          {
            EtwpCopyPropertiesToInfo(Properties, (struct _WMI_LOGGER_INFORMATION *)v30);
            *((_DWORD *)v24 + 11) |= v43;
            *((_QWORD *)v24 + 1) = v44;
            LastError = EtwpCopyFlagExtensions(v45, (struct _WMI_LOGGER_INFORMATION *)v30, v46);
            if ( LastError )
              goto LABEL_133;
            updated = EtwpUpdateLogger((struct _WMI_LOGGER_INFORMATION *)v30, v74, v78);
          }
        }
        else
        {
          if ( (LogFileMode & 0x10000) != 0 )
          {
            *((_DWORD *)v30 + 26) = Properties->EventsLost;
            *((_DWORD *)v30 + 28) = Properties->LogBuffersLost;
          }
          updated = EtwpStopLogger((struct _WMI_LOGGER_INFORMATION *)v30, v74, v78);
        }
      }
      else
      {
        updated = EtwpQueryLogger((struct _WMI_LOGGER_INFORMATION *)v30, v74, v78);
      }
      LastError = updated;
      if ( updated != 234 )
      {
        if ( !updated )
        {
          LODWORD(Length) = 0;
          EtwpCopyInfoToProperties((struct _WMI_LOGGER_INFORMATION *)v30, Properties);
          EtwpFixupLoggerStrings(v49);
          LoggerNameOffset = Properties->LoggerNameOffset;
          LogFileNameOffset = Properties->LogFileNameOffset;
          if ( !(_DWORD)LoggerNameOffset )
            LoggerNameOffset = v27;
          if ( (unsigned int)LoggerNameOffset > LogFileNameOffset )
            LogFileNameOffset = Properties->Wnode.BufferSize;
          v52 = LogFileNameOffset - (unsigned int)LoggerNameOffset;
          v53 = RtlUnicodeStringToAnsiString(&AnsiString, SourceString, 1u);
          if ( v53 >= 0 )
          {
            Length = AnsiString.Length;
            if ( (unsigned int)v52 < (unsigned __int64)AnsiString.Length + 1 )
            {
              v54 = v75 + 2 + AnsiString.Length + v79->Length;
              Properties->Wnode.Flags |= 0x20u;
              Properties->BufferSize = v54;
              v55 = 234;
              goto LABEL_132;
            }
            Properties->LoggerNameOffset = LoggerNameOffset;
            v56 = (char *)Properties + LoggerNameOffset;
            memset_0(v56, 0, (unsigned int)v52);
            if ( (_DWORD)Length && (_DWORD)v52 )
            {
              if ( (unsigned int)v52 <= 0x7FFFFFFFuLL )
              {
                Buffer = AnsiString.Buffer;
                v58 = Length;
                v59 = v56;
                do
                {
                  if ( !v58 )
                    break;
                  if ( !*Buffer )
                    break;
                  *v59++ = *Buffer++;
                  --v58;
                  --v52;
                }
                while ( v52 );
                v60 = v59 - 1;
                if ( v52 )
                  v60 = v59;
                *v60 = 0;
              }
              else
              {
                *v56 = 0;
              }
            }
            v56[Length] = 0;
            LastError = RtlNtStatusToDosError_0(v53);
          }
          v61 = Properties->LogFileNameOffset;
          if ( !v61 )
            v61 = Length + Properties->LoggerNameOffset + 1;
          BufferSize = Properties->LoggerNameOffset;
          if ( v61 > BufferSize )
            BufferSize = Properties->Wnode.BufferSize;
          v63 = BufferSize - v61;
          RtlFreeAnsiString(&AnsiString);
          Status[0] = RtlUnicodeStringToAnsiString(&AnsiString, v79, 1u);
          if ( Status[0] >= 0 )
          {
            v64 = AnsiString.Length;
            v65 = v63;
            if ( v63 >= (unsigned __int64)AnsiString.Length + 1 )
            {
              Properties->LogFileNameOffset = v61;
              v67 = (char *)Properties + v61;
              memset_0(v67, 0, v63);
              if ( v63 )
              {
                if ( v63 <= 0x7FFFFFFFuLL )
                {
                  v68 = AnsiString.Buffer;
                  do
                  {
                    if ( !v64 )
                      break;
                    if ( !*v68 )
                      break;
                    *v67++ = *v68++;
                    --v64;
                    --v65;
                  }
                  while ( v65 );
                  v69 = v67 - 1;
                  if ( v65 )
                    v69 = v67;
                  *v69 = 0;
                }
                else
                {
                  *v67 = 0;
                }
              }
            }
            else
            {
              v66 = Properties->Wnode.BufferSize + 1;
              LastError = 234;
              Properties->Wnode.Flags |= 0x20u;
              Properties->BufferSize = v64 - v63 + v66;
            }
            v55 = RtlNtStatusToDosError_0(Status[0]);
LABEL_132:
            LastError = v55;
            RtlFreeAnsiString(&AnsiString);
          }
        }
LABEL_133:
        operator delete(v30);
        goto LABEL_135;
      }
      v47 = *((unsigned __int16 *)v24 + 65);
      v11 = *((unsigned __int16 *)v24 + 73) >> 1;
      HIDWORD(Size) = v11;
      LODWORD(v19) = v47 >> 1;
      operator delete(v30);
      v4 = v73;
      if ( v18 )
      {
LABEL_69:
        operator delete(v18);
        v18 = 0;
      }
    }
    else
    {
      v28 = (char *)Properties + Properties->LogFileNameOffset;
      if ( strncmp_0(v28, "%SystemRoot%", 0xCu) && strncmp_0(v28, "%DriverData%", 0xCu) )
      {
        v29 = Size;
        v30 = v24;
        while ( 1 )
        {
          v31 = v29;
          v32 = operator new(v29, (const struct std::nothrow_t *)&std::nothrow);
          v18 = v32;
          if ( !v32 )
            break;
          memset_0(v32, 0, v31);
          FullPathNameA = GetFullPathNameA(v28, Size, (LPSTR)v18, 0);
          v34 = FullPathNameA;
          if ( !FullPathNameA )
            goto LABEL_65;
          if ( FullPathNameA <= (unsigned int)Size )
          {
            v28 = (const CHAR *)v18;
            goto LABEL_65;
          }
          operator delete(v18);
          v29 = v34;
          LODWORD(Size) = v34;
        }
        LastError = 8;
        goto LABEL_133;
      }
      v30 = v24;
LABEL_65:
      v19 = -1;
      do
        ++v19;
      while ( v28[v19] );
      if ( (unsigned int)v19 < Status[0] )
      {
        if ( (_DWORD)v19 )
        {
          DestinationString = 0;
          RtlInitAnsiString(&DestinationString, v28);
          *((_WORD *)v24 + 65) = 2 * (v19 + 1);
          v35 = RtlAnsiStringToUnicodeString((PUNICODE_STRING)v24 + 8, &DestinationString, 0);
          if ( v35 < 0 )
          {
            LastError = RtlNtStatusToDosError_0(v35);
            goto LABEL_133;
          }
        }
        v27 = v75;
        goto LABEL_73;
      }
      operator delete(v30);
      v11 = HIDWORD(Size);
      v4 = v73;
      if ( v18 )
        goto LABEL_69;
    }
  }
  LastError = 8;
LABEL_135:
  if ( v18 )
    operator delete(v18);
LABEL_137:
  v70 = LastError;
  if ( LastError )
    RtlSetLastWin32Error(LastError);
  lambda_db69095f55fab6badd012ab3803b2db9_::operator()(v85);
  if ( v87 == 1 )
  {
    v87 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
  }
  return v70;
}

```

## disassembly

```asm
0x1800099c0  mov     [rsp-8+arg_0], rbx
0x1800099c5  push    rbp
0x1800099c6  push    rsi
0x1800099c7  push    rdi
0x1800099c8  push    r12
0x1800099ca  push    r13
0x1800099cc  push    r14
0x1800099ce  push    r15
0x1800099d0  lea     rbp, [rsp-40h]
0x1800099d5  sub     rsp, 140h
0x1800099dc  mov     rax, cs:__security_cookie
0x1800099e3  xor     rax, rsp
0x1800099e6  mov     [rbp+70h+var_40], rax
0x1800099ea  mov     eax, cs:dword_18001D020
0x1800099f0  xor     r14d, r14d
0x1800099f3  mov     [rsp+170h+var_13C], r9d
0x1800099f8  xorps   xmm0, xmm0
0x1800099fb  mov     [rbp+70h+var_E8], rcx
0x1800099ff  mov     edi, r9d
0x180009a02  mov     [rsp+170h+LastError], r14d
0x180009a07  mov     rbx, r8
0x180009a0a  mov     [rsp+170h+var_120], r14
0x180009a0f  mov     r15, rdx
0x180009a12  mov     [rsp+170h+var_138], r14d
0x180009a17  mov     rsi, rcx
0x180009a1a  mov     [rsp+170h+var_134], r14d
0x180009a1f  mov     [rbp+70h+var_C0], r14d
0x180009a23  mov     [rbp+70h+var_BC], r14b
0x180009a27  movups  xmmword ptr [rsp+170h+AnsiString.Length], xmm0
0x180009a2c  cmp     eax, 5
0x180009a2f  jbe     short loc_180009A5E
0x180009a31  mov     rcx, cs:qword_18001D038
0x180009a38  mov     rax, cs:qword_18001D030
0x180009a3f  test    al, 10h
0x180009a41  jz      short loc_180009A5E
0x180009a43  mov     rax, rcx
0x180009a46  and     eax, 10h
0x180009a49  cmp     rax, rcx
0x180009a4c  jnz     short loc_180009A5E
0x180009a4e  lea     rdx, [rbp+70h+ActivityId]; ActivityId
0x180009a52  lea     ecx, [r14+3]; ControlCode
0x180009a56  call    cs:__imp_EventActivityIdControl
0x180009a5c  jmp     short loc_180009A62
0x180009a5e  movups  xmmword ptr [rbp+70h+ActivityId.Data1], xmm0
0x180009a62  mov     eax, cs:dword_18001D020
0x180009a68  mov     r13d, 1
0x180009a6e  mov     [rbp+70h+var_C0], r13d
0x180009a72  cmp     eax, 5
0x180009a75  jbe     loc_180009B48
0x180009a7b  mov     rcx, cs:qword_18001D038
0x180009a82  mov     rax, cs:qword_18001D030
0x180009a89  test    al, 10h
0x180009a8b  jz      loc_180009B48
0x180009a91  mov     rax, rcx
0x180009a94  and     eax, 10h
0x180009a97  cmp     rax, rcx
0x180009a9a  jnz     loc_180009B48
0x180009aa0  mov     [rsp+170h+var_128], edi
0x180009aa4  mov     qword ptr [rsp+170h+Status], rsi
0x180009aa9  cmp     [rbp+70h+var_BC], r14b
0x180009aad  jz      short loc_180009ACD
0x180009aaf  cmp     [rbp+70h+var_A8], r14d
0x180009ab3  jnz     short loc_180009AC7
0x180009ab5  cmp     [rbp+70h+var_A4], r14d
0x180009ab9  jnz     short loc_180009AC7
0x180009abb  cmp     [rbp+70h+var_A0], r14d
0x180009abf  jnz     short loc_180009AC7
0x180009ac1  cmp     [rbp+70h+var_9C], r14d
0x180009ac5  jz      short loc_180009ACD
0x180009ac7  lea     r9, [rbp+70h+var_A8]
0x180009acb  jmp     short loc_180009AD0
0x180009acd  mov     r9, r14
0x180009ad0  mov     [rbp+70h+var_48], 4
0x180009ad8  lea     rax, [rsp+170h+var_128]
0x180009add  mov     [rbp+70h+var_50], rax
0x180009ae1  lea     rax, [rsp+170h+Status]
0x180009ae6  mov     [rbp+70h+var_60], rax
0x180009aea  mov     [rbp+70h+var_58], 8
0x180009af2  test    r15, r15
0x180009af5  jz      short loc_180009B0B
0x180009af7  mov     rcx, r15
0x180009afa  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009afe  inc     rax
0x180009b01  cmp     [r15+rax], r14b
0x180009b05  jnz     short loc_180009AFE
0x180009b07  inc     eax
0x180009b09  jmp     short loc_180009B15
0x180009b0b  lea     rcx, qword_180017D30
0x180009b12  mov     eax, r13d
0x180009b15  mov     [rbp+70h+var_68], eax
0x180009b18  lea     r8, [rbp+70h+ActivityId]
0x180009b1c  lea     rax, [rbp+70h+var_90]
0x180009b20  mov     [rbp+70h+var_70], rcx
0x180009b24  mov     [rsp+170h+var_148], rax
0x180009b29  lea     rdx, byte_1800191FB
0x180009b30  lea     rcx, dword_18001D020
0x180009b37  mov     [rsp+170h+var_150], 5
0x180009b3f  mov     [rbp+70h+var_64], r14d
0x180009b43  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180009b48  mov     [rbp+70h+var_C8], r13b
0x180009b4c  lea     rax, [rbp+70h+var_C0]
0x180009b50  mov     [rbp+70h+var_D8], rax
0x180009b54  lea     rax, [rsp+170h+LastError]
0x180009b59  mov     [rbp+70h+var_D0], rax
0x180009b5d  xorps   xmm0, xmm0
0x180009b60  movups  xmmword ptr [rsp+170h+AnsiString.Length], xmm0
0x180009b65  test    rbx, rbx
0x180009b68  jz      loc_18000A2E1
0x180009b6e  lea     r9, [rsp+170h+var_134]; unsigned int *
0x180009b73  mov     rcx, rbx; struct _EVENT_TRACE_PROPERTIES *
0x180009b76  lea     r8, [rsp+170h+var_120]; struct _EVENT_FILTER_DESCRIPTOR **
0x180009b7b  lea     rdx, [rsp+170h+var_138]; unsigned int *
0x180009b80  call    ?EtwpValidateTraceProperties@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAKPEAPEAU_EVENT_FILTER_DESCRIPTOR@@1@Z; EtwpValidateTraceProperties(_EVENT_TRACE_PROPERTIES *,ulong *,_EVENT_FILTER_DESCRIPTOR * *,ulong *)
0x180009b85  mov     [rsp+170h+LastError], eax
0x180009b89  test    eax, eax
0x180009b8b  jnz     loc_18000A282
0x180009b91  mov     ecx, 400h
0x180009b96  mov     dword ptr [rsp+170h+Size], ecx
0x180009b9a  mov     r12d, ecx
0x180009b9d  mov     dword ptr [rsp+170h+Size+4], ecx
0x180009ba1  test    r15, r15
0x180009ba4  jz      loc_180009C6D
0x180009baa  or      r12, 0FFFFFFFFFFFFFFFFh
0x180009bae  mov     rdi, r12
0x180009bb1  inc     rdi
0x180009bb4  cmp     [r15+rdi], r14b
0x180009bb8  jnz     short loc_180009BB1
0x180009bba  lea     rdx, aNtKernelLogger; "NT Kernel Logger"
0x180009bc1  mov     rcx, r15
0x180009bc4  call    _o__stricmp_0
0x180009bc9  test    eax, eax
0x180009bcb  jnz     short loc_180009BDB
0x180009bcd  movups  xmm0, xmmword ptr cs:SystemTraceControlGuid.Data1
0x180009bd4  movdqu  xmmword ptr [rbx+18h], xmm0
0x180009bd9  jmp     short loc_180009C0A
0x180009bdb  mov     rax, [rbx+18h]
0x180009bdf  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data1
0x180009be6  jnz     short loc_180009C0A
0x180009be8  mov     rax, [rbx+20h]
0x180009bec  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data4
0x180009bf3  jnz     short loc_180009C0A
0x180009bf5  mov     rax, r12
0x180009bf8  inc     rax
0x180009bfb  cmp     [r15+rax], r14b
0x180009bff  jnz     short loc_180009BF8
0x180009c01  test    rax, rax
0x180009c04  jnz     loc_18000A2E1
0x180009c0a  lea     r12d, [rdi+1]
0x180009c0e  mov     rcx, r15
0x180009c11  lea     rdx, aCircularKernel; "Circular Kernel Context Logger"
0x180009c18  mov     dword ptr [rsp+170h+Size+4], r12d
0x180009c1d  call    _o__stricmp_0
0x180009c22  test    eax, eax
0x180009c24  jnz     short loc_180009C34
0x180009c26  movups  xmm0, cs:CKCLGuid
0x180009c2d  movdqu  xmmword ptr [rbx+18h], xmm0
0x180009c32  jmp     short loc_180009C64
0x180009c34  mov     rax, [rbx+18h]
0x180009c38  cmp     rax, qword ptr cs:CKCLGuid
0x180009c3f  jnz     short loc_180009C64
0x180009c41  mov     rax, [rbx+20h]
0x180009c45  cmp     rax, qword ptr cs:CKCLGuid+8
0x180009c4c  jnz     short loc_180009C64
0x180009c4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009c52  inc     rax
0x180009c55  cmp     [r15+rax], r14b
0x180009c59  jnz     short loc_180009C52
0x180009c5b  test    rax, rax
0x180009c5e  jnz     loc_18000A2E1
0x180009c64  mov     edi, [rsp+170h+var_13C]
0x180009c68  mov     ecx, 400h
0x180009c6d  mov     rax, [rbx+18h]
0x180009c71  sub     rax, qword ptr cs:SystemTraceControlGuid.Data1
0x180009c78  jnz     short loc_180009C85
0x180009c7a  mov     rax, [rbx+20h]
0x180009c7e  sub     rax, qword ptr cs:SystemTraceControlGuid.Data4
0x180009c85  test    rax, rax
0x180009c88  setz    al
0x180009c8b  test    rsi, rsi
0x180009c8e  jnz     short loc_180009CB3
0x180009c90  test    al, al
0x180009c92  jnz     short loc_180009CB3
0x180009c94  test    r15, r15
0x180009c97  jz      loc_18000A2E1
0x180009c9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009ca1  inc     rax
0x180009ca4  cmp     [r15+rax], r14b
0x180009ca8  jnz     short loc_180009CA1
0x180009caa  test    rax, rax
0x180009cad  jz      loc_18000A2E1
0x180009cb3  test    byte ptr [rbx+40h], 4
0x180009cb7  jz      short loc_180009CC8
0x180009cb9  cmp     edi, 2
0x180009cbc  jnz     short loc_180009CC8
0x180009cbe  cmp     [rbx+70h], r14d
0x180009cc2  ja      loc_18000A2E1
0x180009cc8  mov     r13, r14
0x180009ccb  mov     esi, ecx
0x180009ccd  lea     r14d, [rsi+10h]
0x180009cd1  lea     eax, [r14+r12]
0x180009cd5  mov     [rsp+170h+Status], r14d
0x180009cda  lea     eax, ds:0B7h[rax*2]
0x180009ce1  and     eax, 0FFFFFFF8h
0x180009ce4  mov     [rsp+170h+var_128], eax
0x180009ce8  mov     dword ptr [rsp+170h+var_118], eax
0x180009cec  cmp     edi, 2
0x180009cef  jnz     short loc_180009D12
0x180009cf1  lea     rdx, [rsp+170h+var_118]; unsigned int *
0x180009cf6  mov     rcx, rbx; struct _EVENT_TRACE_PROPERTIES *
0x180009cf9  call    ?EtwpCheckFlagExtensions@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAK@Z; EtwpCheckFlagExtensions(_EVENT_TRACE_PROPERTIES *,ulong *)
0x180009cfe  mov     [rsp+170h+LastError], eax
0x180009d02  test    eax, eax
0x180009d04  jnz     loc_18000A26F
0x180009d0a  mov     eax, dword ptr [rsp+170h+var_118]
0x180009d0e  mov     [rsp+170h+var_128], eax
0x180009d12  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009d19  mov     ecx, eax; unsigned __int64
0x180009d1b  mov     esi, eax
0x180009d1d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009d22  mov     rdi, rax
0x180009d25  test    rax, rax
0x180009d28  jz      loc_18000A267
0x180009d2e  mov     r8d, esi; Size
0x180009d31  xor     edx, edx; Val
0x180009d33  mov     rcx, rax; void *
0x180009d36  call    memset_0
0x180009d3b  lea     rsi, [rdi+90h]
0x180009d42  movzx   ecx, r12w
0x180009d46  add     cx, cx
0x180009d49  mov     [rbp+70h+SourceString], rsi
0x180009d4d  lea     rdx, [rdi+80h]
0x180009d54  xorps   xmm0, xmm0
0x180009d57  movups  xmmword ptr [rsi], xmm0
0x180009d5a  mov     [rsi+2], cx
0x180009d5e  lea     rax, [rdi+0B0h]
0x180009d65  mov     [rsi+8], rax
0x180009d69  movzx   eax, r14w
0x180009d6d  add     ax, ax
0x180009d70  mov     ecx, r12d
0x180009d73  add     rcx, 58h ; 'X'
0x180009d77  mov     [rsp+170h+var_118], rdx
0x180009d7c  movups  xmmword ptr [rdx], xmm0
0x180009d7f  mov     [rdx+2], ax
0x180009d83  lea     rcx, [rdi+rcx*2]
0x180009d87  mov     [rdx+8], rcx
0x180009d8b  test    r15, r15
0x180009d8e  jz      short loc_180009DD2
0x180009d90  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009d94  inc     rax
0x180009d97  cmp     byte ptr [r15+rax], 0
0x180009d9c  jnz     short loc_180009D94
0x180009d9e  test    rax, rax
0x180009da1  jz      short loc_180009DD2
0x180009da3  xorps   xmm0, xmm0
0x180009da6  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180009dab  mov     rdx, r15; SourceString
0x180009dae  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x180009db3  call    cs:__imp_RtlInitAnsiString
0x180009db9  xor     r8d, r8d; AllocateDestinationString
0x180009dbc  lea     rdx, [rsp+170h+DestinationString]; SourceString
0x180009dc1  mov     rcx, rsi; DestinationString
0x180009dc4  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180009dca  test    eax, eax
0x180009dcc  js      loc_18000A048
0x180009dd2  mov     r12d, [rsp+170h+var_134]
0x180009dd7  cmp     [rbx+70h], r12d
0x180009ddb  jb      loc_180009F5F
0x180009de1  mov     r12d, [rbx+70h]
0x180009de5  lea     rdx, Str2; "%SystemRoot%"
0x180009dec  add     r12, rbx
0x180009def  mov     esi, 0Ch
0x180009df4  mov     rcx, r12; Str1
0x180009df7  mov     r8d, esi; MaxCount
0x180009dfa  call    strncmp_0
0x180009dff  test    eax, eax
0x180009e01  jz      short loc_180009E7D
0x180009e03  mov     r8d, esi; MaxCount
0x180009e06  lea     rdx, aDriverdata; "%DriverData%"
0x180009e0d  mov     rcx, r12; Str1
0x180009e10  call    strncmp_0
0x180009e15  test    eax, eax
0x180009e17  jz      short loc_180009E7D
0x180009e19  mov     eax, dword ptr [rsp+170h+Size]
0x180009e1d  mov     r14, rdi
0x180009e20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e27  mov     ecx, eax; unsigned __int64
0x180009e29  mov     esi, eax
0x180009e2b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009e30  mov     r13, rax
0x180009e33  test    rax, rax
0x180009e36  jz      loc_18000A05B
0x180009e3c  mov     r8d, esi; Size
0x180009e3f  xor     edx, edx; Val
0x180009e41  mov     rcx, rax; void *
0x180009e44  call    memset_0
0x180009e49  mov     edx, dword ptr [rsp+170h+Size]; nBufferLength
0x180009e4d  xor     r9d, r9d; lpFilePart
0x180009e50  mov     r8, r13; lpBuffer
0x180009e53  mov     rcx, r12; lpFileName
0x180009e56  call    cs:__imp_GetFullPathNameA
  ... truncated ...
```
