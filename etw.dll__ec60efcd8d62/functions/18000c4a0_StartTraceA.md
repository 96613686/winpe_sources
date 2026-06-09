# StartTraceA

- ea: `0x18000c4a0`
- end: `0x18000cc8b`
- name: `StartTraceA`
- size: `2027`
- prototype: `ULONG __stdcall(PTRACEHANDLE TraceHandle, LPCSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, loader_planting`

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
- `0x180008a2c`
- `0x180008e3c`
- `0x180008f30`
- `0x180009228`
- `0x1800097e0`
- `0x1800098ec`
- `0x18000c4a0`
- `0x180013138`
- `0x1800131ec`
- `0x1800137e4`
- `0x180015804`
- `0x180015834`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000c8c4`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000c8c4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18000c8ab`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18000c8ab`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18000c891`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18000c891`
- `ntdll!RtlInitAnsiString` at `0x18000c980`
- `ntdll!RtlInitAnsiString` at `0x18000ca06`
- `ntdll!RtlInitAnsiString` at `0x18000c980`
- `ntdll!RtlInitAnsiString` at `0x18000ca06`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000c9ac`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000ca16`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000c9ac`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000ca16`
- `ntdll!RtlSetLastWin32Error` at `0x18000c6ce`
- `ntdll!RtlSetLastWin32Error` at `0x18000c7f9`
- `ntdll!RtlSetLastWin32Error` at `0x18000cc0b`
- `ntdll!RtlSetLastWin32Error` at `0x18000cc34`
- `ntdll!RtlSetLastWin32Error` at `0x18000c6ce`
- `ntdll!RtlSetLastWin32Error` at `0x18000c7f9`
- `ntdll!RtlSetLastWin32Error` at `0x18000cc0b`
- `ntdll!RtlSetLastWin32Error` at `0x18000cc34`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c52d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000c52d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18000c7b4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18000c7b4`

## pseudocode

```c
ULONG __stdcall StartTraceA(PTRACEHANDLE TraceHandle, LPCSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties)
{
  __int64 v3; // r12
  LPCSTR v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  ULONG v9; // ebx
  __int64 v10; // rax
  __int64 v11; // r13
  ULONG v12; // ebx
  bool v13; // zf
  __int64 v14; // rax
  const char *v15; // r14
  DWORD i; // ebx
  void *v17; // rax
  CHAR *v18; // r12
  DWORD FullPathNameA; // eax
  DWORD v20; // r12d
  _BOOL8 v21; // rax
  __int64 v23; // rbx
  char *v24; // rdi
  int v25; // eax
  char *v26; // rax
  char *v27; // rdi
  int v28; // eax
  ULONG v29; // eax
  unsigned int v30; // eax
  int v31; // r11d
  ULONG LogFileNameOffset; // ecx
  unsigned int v33; // ecx
  __int64 v34; // rax
  __int64 v35; // r9
  _BYTE *v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rax
  _BYTE *v39; // rax
  __int64 v40; // rax
  ULONG LoggerNameOffset; // ecx
  unsigned int v42; // ecx
  _BYTE *v43; // rdx
  __int64 v44; // r8
  _BYTE *v45; // rax
  ULONG LastError; // [rsp+30h] [rbp-A9h] BYREF
  char v47; // [rsp+34h] [rbp-A5h]
  size_t Size; // [rsp+38h] [rbp-A1h] BYREF
  BOOL v49; // [rsp+40h] [rbp-99h]
  unsigned int v50; // [rsp+44h] [rbp-95h]
  unsigned int v51; // [rsp+48h] [rbp-91h] BYREF
  PTRACEHANDLE v52; // [rsp+50h] [rbp-89h] BYREF
  void *Block; // [rsp+58h] [rbp-81h]
  _QWORD v54[3]; // [rsp+60h] [rbp-79h] BYREF
  char v55; // [rsp+78h] [rbp-61h]
  struct _EVENT_FILTER_DESCRIPTOR *v56; // [rsp+80h] [rbp-59h] BYREF
  struct _STRING DestinationString; // [rsp+88h] [rbp-51h] BYREF
  int v58; // [rsp+98h] [rbp-41h] BYREF
  char v59; // [rsp+9Ch] [rbp-3Dh]
  GUID ActivityId; // [rsp+A0h] [rbp-39h] BYREF
  char v61[32]; // [rsp+C0h] [rbp-19h] BYREF
  LPCSTR v62; // [rsp+E0h] [rbp+7h]
  int v63; // [rsp+E8h] [rbp+Fh]
  int v64; // [rsp+ECh] [rbp+13h]

  LODWORD(v3) = 0;
  v52 = TraceHandle;
  LastError = 0;
  v51 = 0;
  v56 = 0;
  LODWORD(Size) = 0;
  v58 = 0;
  v59 = 0;
  DestinationString = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v58 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    if ( InstanceName )
    {
      v6 = InstanceName;
      v7 = -1;
      do
        ++v7;
      while ( InstanceName[v7] );
      v8 = v7 + 1;
    }
    else
    {
      v6 = (LPCSTR)&qword_180017D30;
      v8 = 1;
    }
    v63 = v8;
    v62 = v6;
    v64 = 0;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)byte_1800192ED,
      (__int64)&ActivityId,
      0,
      3,
      (__int64)v61);
  }
  v55 = 1;
  v54[0] = &v58;
  v54[1] = &LastError;
  v54[2] = &v52;
  if ( !Properties || !v52 )
  {
    v9 = 87;
    goto LABEL_124;
  }
  if ( !InstanceName )
  {
    v9 = 123;
LABEL_124:
    LastError = v9;
LABEL_125:
    RtlSetLastWin32Error(v9);
    if ( v55 )
      lambda_d7e3293224a49450258b7fbf07695f92_::operator()(v54);
    if ( v58 != 1 )
      return v9;
    goto LABEL_128;
  }
  LastError = EtwpValidateTraceProperties(Properties, &v51, &v56, (unsigned int *)&Size);
  v9 = LastError;
  if ( LastError )
    goto LABEL_125;
  v10 = -1;
  do
    ++v10;
  while ( InstanceName[v10] );
  v11 = (unsigned int)Size;
  v12 = v10 + Size + 1;
  if ( (unsigned int)o__stricmp_0(InstanceName, "NT Kernel Logger") )
  {
    if ( *(_QWORD *)&Properties->Wnode.Guid.Data1 == *(_QWORD *)&SystemTraceControlGuid.Data1
      && *(_QWORD *)Properties->Wnode.Guid.Data4 == *(_QWORD *)SystemTraceControlGuid.Data4 )
    {
      goto LABEL_28;
    }
  }
  else
  {
    Properties->Wnode.Guid = SystemTraceControlGuid;
  }
  if ( !(unsigned int)o__stricmp_0(InstanceName, "Circular Kernel Context Logger") )
  {
    Properties->Wnode.Guid = (GUID)CKCLGuid;
    goto LABEL_34;
  }
  if ( *(_OWORD *)&Properties->Wnode.Guid == CKCLGuid )
  {
LABEL_28:
    v9 = 87;
    LastError = 87;
    RtlSetLastWin32Error(0x57u);
    if ( v55 )
      lambda_d7e3293224a49450258b7fbf07695f92_::operator()(v54);
    v13 = v58 == 1;
LABEL_31:
    if ( !v13 )
      return v9;
LABEL_128:
    v58 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
    return v9;
  }
LABEL_34:
  v47 = 0;
  Block = 0;
  if ( !Properties->LogFileNameOffset )
  {
    v15 = 0;
    LODWORD(v21) = 0;
    goto LABEL_56;
  }
  v14 = -1;
  v15 = (char *)Properties + Properties->LogFileNameOffset;
  do
    ++v14;
  while ( v15[v14] );
  v12 += v14 + 1;
  LODWORD(Size) = v12;
  if ( !strncmp_0(v15, "%SystemRoot%", 0xCu) || !strncmp_0(v15, "%DriverData%", 0xCu) )
  {
    v47 = 1;
LABEL_46:
    v3 = -1;
    do
      ++v3;
    while ( v15[v3] );
    v21 = (_DWORD)v3 != 0;
LABEL_56:
    v49 = v21;
    if ( Properties->Wnode.BufferSize < v12 )
    {
      LastError = 24;
LABEL_116:
      if ( Block )
        operator delete(Block);
      v9 = LastError;
      if ( LastError )
        RtlSetLastWin32Error(LastError);
      if ( v55 )
        lambda_d7e3293224a49450258b7fbf07695f92_::operator()(v54);
      v13 = v58 == 1;
      goto LABEL_31;
    }
    v23 = -1;
    do
      ++v23;
    while ( InstanceName[v23] );
    if ( !(_DWORD)v23 )
      goto LABEL_115;
    LastError = EtwpValidateLogFileMode(Properties, v21);
    if ( LastError )
      goto LABEL_116;
    if ( (Properties->LogFileMode & 8) != 0 )
    {
      v24 = strchr(v15, 37);
      if ( !v24 || v24 != strrchr(v15, 37) || !strstr(v15, "%d") )
      {
LABEL_115:
        LastError = 123;
        goto LABEL_116;
      }
    }
    LODWORD(Size) = 2 * (v23 + v3) + 180;
    LastError = EtwpCheckFlagExtensions(Properties, (unsigned int *)&Size);
    if ( LastError )
      goto LABEL_116;
    v13 = (Properties->LogFileMode & 0x10000) == 0;
    v50 = 0;
    v25 = Size;
    if ( !v13 )
    {
      v50 = *(unsigned __int16 *)((char *)&Properties->Wnode.ProviderId + v11);
      v25 = v50 + ((Size + 7) & 0xFFFFFFF8);
    }
    Size = (v25 + 7) & 0xFFFFFFF8;
    v26 = (char *)operator new(Size, (const struct std::nothrow_t *)&std::nothrow);
    v27 = v26;
    if ( !v26 )
    {
      LastError = 8;
      goto LABEL_116;
    }
    memset_0(v26, 0, Size);
    *v52 = 0;
    EtwpCopyPropertiesToInfo(Properties, (struct _WMI_LOGGER_INFORMATION *)v27);
    *((_DWORD *)v27 + 26) = Properties->Wnode.ProviderId;
    *((_DWORD *)v27 + 1) = 0;
    RtlInitAnsiString(&DestinationString, InstanceName);
    *((_WORD *)v27 + 73) = 2 * (v23 + 1);
    *((_QWORD *)v27 + 19) = v27 + 176;
    v28 = RtlAnsiStringToUnicodeString((PUNICODE_STRING)v27 + 9, &DestinationString, 0);
    if ( v28 < 0 )
      goto LABEL_71;
    if ( v49 )
    {
      *((_QWORD *)v27 + 17) = &v27[*((unsigned __int16 *)v27 + 73) + 176];
      *((_WORD *)v27 + 65) = 2 * (v3 + 1);
      RtlInitAnsiString(&DestinationString, v15);
      v28 = RtlAnsiStringToUnicodeString((PUNICODE_STRING)v27 + 8, &DestinationString, 0);
      if ( v28 < 0 )
      {
LABEL_71:
        v29 = RtlNtStatusToDosError_0(v28);
LABEL_72:
        LastError = v29;
LABEL_113:
        operator delete(v27);
        goto LABEL_116;
      }
      if ( !v47 )
      {
        v29 = EtwpCheckForEnoughFreeSpace(
                *((const unsigned __int16 **)v27 + 17),
                v3,
                Properties->MaximumFileSize,
                Properties->LogFileMode & 4,
                Properties->LogFileMode & 0x2000);
        if ( v29 )
          goto LABEL_72;
      }
    }
    v30 = Size;
    *((_DWORD *)v27 + 11) |= 0x20000u;
    *(_DWORD *)v27 = v30;
    LastError = EtwpCopyFlagExtensions(Properties, (struct _WMI_LOGGER_INFORMATION *)v27, v30);
    if ( !LastError )
    {
      if ( (Properties->LogFileMode & 0x10000) != 0 && v50 )
        memcpy_0(
          &v27[(*((unsigned __int16 *)v27 + 65) + 183LL + *((unsigned __int16 *)v27 + 73)) & 0xFFFFFFF8LL],
          (char *)Properties + v11,
          v50);
      LastError = EtwpStartLogger((struct _WMI_LOGGER_INFORMATION *)v27, v51, v56);
      if ( !LastError )
      {
        EtwpCopyInfoToProperties((struct _WMI_LOGGER_INFORMATION *)v27, Properties);
        if ( Properties->LoggerNameOffset == v31 )
          Properties->LoggerNameOffset = v11;
        else
          LODWORD(v11) = Properties->LoggerNameOffset;
        LogFileNameOffset = Properties->LogFileNameOffset;
        if ( (unsigned int)v11 > LogFileNameOffset )
          LogFileNameOffset = Properties->Wnode.BufferSize;
        v33 = LogFileNameOffset - v11;
        v34 = -1;
        do
          ++v34;
        while ( InstanceName[v34] != (_BYTE)v31 );
        v35 = 2147483646;
        if ( (int)v34 + 1 <= v33 )
        {
          v36 = (char *)Properties + (unsigned int)v11;
          v37 = v33;
          if ( v33 - 1 > 0x7FFFFFFE )
          {
            if ( v33 )
              *v36 = v31;
          }
          else
          {
            v38 = 2147483646;
            do
            {
              if ( !v38 )
                break;
              if ( !*InstanceName )
                break;
              *v36++ = *InstanceName++;
              --v38;
              --v37;
            }
            while ( v37 );
            v39 = v36 - 1;
            if ( v37 )
              v39 = v36;
            *v39 = v31;
          }
        }
        *v52 = *((_QWORD *)v27 + 1);
        v40 = Properties->LogFileNameOffset;
        LoggerNameOffset = Properties->LoggerNameOffset;
        if ( (unsigned int)v40 > LoggerNameOffset )
          LoggerNameOffset = Properties->Wnode.BufferSize;
        v42 = LoggerNameOffset - v40;
        if ( (_DWORD)v3 && v42 >= (unsigned int)v3 )
        {
          v43 = (char *)Properties + v40;
          v44 = v42;
          if ( v42 - 1 > 0x7FFFFFFE )
          {
            if ( v42 )
              *v43 = v31;
          }
          else
          {
            do
            {
              if ( !v35 )
                break;
              if ( !*v15 )
                break;
              *v43++ = *v15++;
              --v35;
              --v44;
            }
            while ( v44 );
            v45 = v43 - 1;
            if ( v44 )
              v45 = v43;
            *v45 = v31;
          }
        }
      }
    }
    goto LABEL_113;
  }
  for ( i = 1024; ; i = v20 )
  {
    v17 = operator new(i, (const struct std::nothrow_t *)&std::nothrow);
    Block = v17;
    v18 = (CHAR *)v17;
    if ( !v17 )
      break;
    memset_0(v17, 0, i);
    FullPathNameA = GetFullPathNameA(v15, i, v18, 0);
    v20 = FullPathNameA;
    if ( !FullPathNameA )
      goto LABEL_45;
    if ( FullPathNameA <= i )
    {
      v15 = (const char *)Block;
LABEL_45:
      v12 = Size;
      goto LABEL_46;
    }
    operator delete(Block);
  }
  RtlSetLastWin32Error(8u);
  if ( v55 )
    lambda_d7e3293224a49450258b7fbf07695f92_::operator()(v54);
  if ( v58 == 1 )
  {
    v58 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
  }
  return 8;
}

```

## disassembly

```asm
0x18000c4a0  mov     [rsp-8+arg_18], rbx
0x18000c4a5  push    rbp
0x18000c4a6  push    rsi
0x18000c4a7  push    rdi
0x18000c4a8  push    r12
0x18000c4aa  push    r13
0x18000c4ac  push    r14
0x18000c4ae  push    r15
0x18000c4b0  lea     rbp, [rsp-27h]
0x18000c4b5  sub     rsp, 100h
0x18000c4bc  mov     rax, cs:__security_cookie
0x18000c4c3  xor     rax, rsp
0x18000c4c6  mov     [rbp+57h+var_40], rax
0x18000c4ca  mov     eax, cs:dword_18001D020
0x18000c4d0  xor     r12d, r12d
0x18000c4d3  mov     [rsp+130h+var_E0], rcx
0x18000c4d8  xorps   xmm0, xmm0
0x18000c4db  mov     [rsp+130h+LastError], r12d
0x18000c4e0  mov     rsi, r8
0x18000c4e3  mov     dword ptr [rsp+130h+var_EC+4], r12d
0x18000c4e8  mov     r15, rdx
0x18000c4eb  mov     [rbp+57h+var_B0], r12
0x18000c4ef  lea     ebx, [r12+3]
0x18000c4f4  mov     dword ptr [rsp+130h+Size], r12d
0x18000c4f9  mov     [rbp+57h+var_98], r12d
0x18000c4fd  mov     [rbp+57h+var_94], r12b
0x18000c501  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000c505  cmp     eax, 5
0x18000c508  jbe     short loc_18000C535
0x18000c50a  mov     rcx, cs:qword_18001D038
0x18000c511  mov     rax, cs:qword_18001D030
0x18000c518  test    al, 10h
0x18000c51a  jz      short loc_18000C535
0x18000c51c  mov     rax, rcx
0x18000c51f  and     eax, 10h
0x18000c522  cmp     rax, rcx
0x18000c525  jnz     short loc_18000C535
0x18000c527  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18000c52b  mov     ecx, ebx; ControlCode
0x18000c52d  call    cs:__imp_EventActivityIdControl
0x18000c533  jmp     short loc_18000C539
0x18000c535  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18000c539  mov     eax, cs:dword_18001D020
0x18000c53f  lea     r13, dword_18001D020
0x18000c546  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000c54a  mov     r14d, 1
0x18000c550  mov     [rbp+57h+var_98], r14d
0x18000c554  cmp     eax, 5
0x18000c557  jbe     loc_18000C5EE
0x18000c55d  mov     rcx, cs:qword_18001D038
0x18000c564  mov     rax, cs:qword_18001D030
0x18000c56b  test    al, 10h
0x18000c56d  jz      short loc_18000C5EE
0x18000c56f  mov     rax, rcx
0x18000c572  and     eax, 10h
0x18000c575  cmp     rax, rcx
0x18000c578  jnz     short loc_18000C5EE
0x18000c57a  cmp     [rbp+57h+var_94], r12b
0x18000c57e  jz      short loc_18000C59E
0x18000c580  cmp     [rbp+57h+var_80], r12d
0x18000c584  jnz     short loc_18000C598
0x18000c586  cmp     [rbp+57h+var_7C], r12d
0x18000c58a  jnz     short loc_18000C598
0x18000c58c  cmp     [rbp+57h+var_78], r12d
0x18000c590  jnz     short loc_18000C598
0x18000c592  cmp     [rbp+57h+var_74], r12d
0x18000c596  jz      short loc_18000C59E
0x18000c598  lea     r9, [rbp+57h+var_80]
0x18000c59c  jmp     short loc_18000C5A1
0x18000c59e  mov     r9, r12
0x18000c5a1  test    r15, r15
0x18000c5a4  jz      short loc_18000C5B9
0x18000c5a6  mov     rcx, r15
0x18000c5a9  mov     rax, rdi
0x18000c5ac  inc     rax
0x18000c5af  cmp     [r15+rax], r12b
0x18000c5b3  jnz     short loc_18000C5AC
0x18000c5b5  inc     eax
0x18000c5b7  jmp     short loc_18000C5C3
0x18000c5b9  lea     rcx, qword_180017D30
0x18000c5c0  mov     eax, r14d
0x18000c5c3  mov     [rbp+57h+var_48], eax
0x18000c5c6  lea     r8, [rbp+57h+ActivityId]
0x18000c5ca  lea     rax, [rbp+57h+var_70]
0x18000c5ce  mov     [rbp+57h+var_50], rcx
0x18000c5d2  mov     [rsp+130h+var_108], rax
0x18000c5d7  lea     rdx, byte_1800192ED
0x18000c5de  mov     rcx, r13
0x18000c5e1  mov     [rsp+130h+var_110], ebx
0x18000c5e5  mov     [rbp+57h+var_44], r12d
0x18000c5e9  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000c5ee  mov     [rbp+57h+var_B8], r14b
0x18000c5f2  lea     rax, [rbp+57h+var_98]
0x18000c5f6  mov     [rbp+57h+var_D0], rax
0x18000c5fa  lea     rax, [rsp+130h+LastError]
0x18000c5ff  mov     [rbp+57h+var_C8], rax
0x18000c603  lea     rax, [rsp+130h+var_E0]
0x18000c608  mov     [rbp+57h+var_C0], rax
0x18000c60c  test    rsi, rsi
0x18000c60f  jz      loc_18000CC29
0x18000c615  cmp     [rsp+130h+var_E0], r12
0x18000c61a  jz      loc_18000CC29
0x18000c620  test    r15, r15
0x18000c623  jnz     short loc_18000C62E
0x18000c625  lea     ebx, [r15+7Bh]
0x18000c629  jmp     loc_18000CC2E
0x18000c62e  lea     r9, [rsp+130h+Size]; unsigned int *
0x18000c633  mov     rcx, rsi; struct _EVENT_TRACE_PROPERTIES *
0x18000c636  lea     r8, [rbp+57h+var_B0]; struct _EVENT_FILTER_DESCRIPTOR **
0x18000c63a  lea     rdx, [rsp+130h+var_EC+4]; unsigned int *
0x18000c63f  call    ?EtwpValidateTraceProperties@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAKPEAPEAU_EVENT_FILTER_DESCRIPTOR@@1@Z; EtwpValidateTraceProperties(_EVENT_TRACE_PROPERTIES *,ulong *,_EVENT_FILTER_DESCRIPTOR * *,ulong *)
0x18000c644  mov     [rsp+130h+LastError], eax
0x18000c648  mov     ebx, eax
0x18000c64a  test    eax, eax
0x18000c64c  jnz     loc_18000CC32
0x18000c652  mov     rax, rdi
0x18000c655  inc     rax
0x18000c658  cmp     [r15+rax], r12b
0x18000c65c  jnz     short loc_18000C655
0x18000c65e  mov     r13d, dword ptr [rsp+130h+Size]
0x18000c663  lea     rdx, aNtKernelLogger; "NT Kernel Logger"
0x18000c66a  mov     rcx, r15
0x18000c66d  lea     ebx, [r13+1]
0x18000c671  add     ebx, eax
0x18000c673  call    _o__stricmp_0
0x18000c678  test    eax, eax
0x18000c67a  jnz     short loc_18000C6A9
0x18000c67c  movups  xmm0, xmmword ptr cs:SystemTraceControlGuid.Data1
0x18000c683  movdqu  xmmword ptr [rsi+18h], xmm0
0x18000c688  lea     rdx, aCircularKernel; "Circular Kernel Context Logger"
0x18000c68f  mov     rcx, r15
0x18000c692  call    _o__stricmp_0
0x18000c697  test    eax, eax
0x18000c699  jnz     short loc_18000C6F9
0x18000c69b  movups  xmm0, cs:CKCLGuid
0x18000c6a2  movdqu  xmmword ptr [rsi+18h], xmm0
0x18000c6a7  jmp     short loc_18000C713
0x18000c6a9  mov     rax, [rsi+18h]
0x18000c6ad  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data1
0x18000c6b4  jnz     short loc_18000C688
0x18000c6b6  mov     rax, [rsi+20h]
0x18000c6ba  cmp     rax, qword ptr cs:SystemTraceControlGuid.Data4
0x18000c6c1  jnz     short loc_18000C688
0x18000c6c3  mov     ebx, 57h ; 'W'
0x18000c6c8  mov     ecx, ebx; LastError
0x18000c6ca  mov     [rsp+130h+LastError], ebx
0x18000c6ce  call    cs:__imp_RtlSetLastWin32Error
0x18000c6d4  cmp     [rbp+57h+var_B8], r12b
0x18000c6d8  jz      short loc_18000C6E3
0x18000c6da  lea     rcx, [rbp+57h+var_D0]
0x18000c6de  call    _lambda_d7e3293224a49450258b7fbf07695f92___operator__
0x18000c6e3  cmp     [rbp+57h+var_98], r14d
0x18000c6e7  jnz     loc_18000CC62
0x18000c6ed  lea     rcx, dword_18001D020
0x18000c6f4  jmp     loc_18000CC52
0x18000c6f9  mov     rax, [rsi+18h]
0x18000c6fd  cmp     rax, qword ptr cs:CKCLGuid
0x18000c704  jnz     short loc_18000C713
0x18000c706  mov     rax, [rsi+20h]
0x18000c70a  cmp     rax, qword ptr cs:CKCLGuid+8
0x18000c711  jz      short loc_18000C6C3
0x18000c713  mov     [rsp+130h+var_FC], r12b
0x18000c718  mov     [rsp+130h+Block], r12
0x18000c71d  cmp     [rsi+70h], r12d
0x18000c721  jbe     loc_18000C840
0x18000c727  mov     r14d, [rsi+70h]
0x18000c72b  mov     rax, rdi
0x18000c72e  add     r14, rsi
0x18000c731  inc     rax
0x18000c734  cmp     [r14+rax], r12b
0x18000c738  jnz     short loc_18000C731
0x18000c73a  inc     eax
0x18000c73c  lea     rdx, Str2; "%SystemRoot%"
0x18000c743  add     ebx, eax
0x18000c745  mov     r8d, 0Ch; MaxCount
0x18000c74b  mov     rcx, r14; Str1
0x18000c74e  mov     dword ptr [rsp+130h+Size], ebx
0x18000c752  call    strncmp_0
0x18000c757  test    eax, eax
0x18000c759  jz      loc_18000C839
0x18000c75f  mov     r8d, 0Ch; MaxCount
0x18000c765  lea     rdx, aDriverdata; "%DriverData%"
0x18000c76c  mov     rcx, r14; Str1
0x18000c76f  call    strncmp_0
0x18000c774  test    eax, eax
0x18000c776  jz      loc_18000C839
0x18000c77c  mov     ebx, 400h
0x18000c781  mov     ecx, ebx; unsigned __int64
0x18000c783  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c78a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c78f  mov     [rsp+130h+Block], rax
0x18000c794  mov     r12, rax
0x18000c797  test    rax, rax
0x18000c79a  jz      short loc_18000C7F4
0x18000c79c  mov     r8d, ebx; Size
0x18000c79f  xor     edx, edx; Val
0x18000c7a1  mov     rcx, rax; void *
0x18000c7a4  call    memset_0
0x18000c7a9  xor     r9d, r9d; lpFilePart
0x18000c7ac  mov     r8, r12; lpBuffer
0x18000c7af  mov     edx, ebx; nBufferLength
0x18000c7b1  mov     rcx, r14; lpFileName
0x18000c7b4  call    cs:__imp_GetFullPathNameA
0x18000c7ba  mov     r12d, eax
0x18000c7bd  test    eax, eax
0x18000c7bf  jz      short loc_18000C7D9
0x18000c7c1  cmp     eax, ebx
0x18000c7c3  jbe     short loc_18000C7D4
0x18000c7c5  mov     rcx, [rsp+130h+Block]; Block
0x18000c7ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c7cf  mov     ebx, r12d
0x18000c7d2  jmp     short loc_18000C781
0x18000c7d4  mov     r14, [rsp+130h+Block]
0x18000c7d9  mov     ebx, dword ptr [rsp+130h+Size]
0x18000c7dd  mov     r12, rdi
0x18000c7e0  inc     r12
0x18000c7e3  cmp     byte ptr [r14+r12], 0
0x18000c7e8  jnz     short loc_18000C7E0
0x18000c7ea  xor     eax, eax
0x18000c7ec  test    r12d, r12d
0x18000c7ef  setnz   al
0x18000c7f2  jmp     short loc_18000C845
0x18000c7f4  mov     ecx, 8; LastError
0x18000c7f9  call    cs:__imp_RtlSetLastWin32Error
0x18000c7ff  cmp     [rbp+57h+var_B8], 0
0x18000c803  jz      short loc_18000C80E
0x18000c805  lea     rcx, [rbp+57h+var_D0]
0x18000c809  call    _lambda_d7e3293224a49450258b7fbf07695f92___operator__
0x18000c80e  mov     ecx, 1
0x18000c813  cmp     [rbp+57h+var_98], ecx
0x18000c816  jnz     short loc_18000C82F
0x18000c818  lea     rdx, [rbp+57h+ActivityId]
0x18000c81c  mov     [rbp+57h+var_98], 2
0x18000c823  lea     rcx, dword_18001D020
0x18000c82a  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x18000c82f  mov     eax, 8
0x18000c834  jmp     loc_18000CC64
0x18000c839  mov     [rsp+130h+var_FC], 1
0x18000c83e  jmp     short loc_18000C7DD
0x18000c840  xor     r14d, r14d
0x18000c843  xor     eax, eax
0x18000c845  mov     [rsp+130h+var_F0], eax
0x18000c849  cmp     [rsi], ebx
0x18000c84b  jnb     short loc_18000C85A
0x18000c84d  mov     [rsp+130h+LastError], 18h
0x18000c855  jmp     loc_18000CBEF
0x18000c85a  mov     rbx, rdi
0x18000c85d  inc     rbx
0x18000c860  cmp     byte ptr [r15+rbx], 0
0x18000c865  jnz     short loc_18000C85D
0x18000c867  test    ebx, ebx
0x18000c869  jz      loc_18000CBE6
0x18000c86f  mov     edx, eax; unsigned int
0x18000c871  mov     rcx, rsi; struct _EVENT_TRACE_PROPERTIES *
0x18000c874  call    ?EtwpValidateLogFileMode@@YAKPEAU_EVENT_TRACE_PROPERTIES@@K@Z; EtwpValidateLogFileMode(_EVENT_TRACE_PROPERTIES *,ulong)
0x18000c879  mov     [rsp+130h+LastError], eax
0x18000c87d  test    eax, eax
0x18000c87f  jnz     loc_18000CBEF
0x18000c885  test    byte ptr [rsi+40h], 8
0x18000c889  jz      short loc_18000C8D3
0x18000c88b  lea     edx, [rax+25h]; Val
0x18000c88e  mov     rcx, r14; Str
0x18000c891  call    cs:__imp_strchr
0x18000c897  mov     rdi, rax
0x18000c89a  test    rax, rax
0x18000c89d  jz      loc_18000CBE6
0x18000c8a3  mov     edx, 25h ; '%'; Ch
0x18000c8a8  mov     rcx, r14; Str
0x18000c8ab  call    cs:__imp_strrchr
0x18000c8b1  cmp     rdi, rax
0x18000c8b4  jnz     loc_18000CBE6
0x18000c8ba  lea     rdx, SubStr; "%d"
0x18000c8c1  mov     rcx, r14; Str
0x18000c8c4  call    cs:__imp_strstr
0x18000c8ca  test    rax, rax
0x18000c8cd  jz      loc_18000CBE6
0x18000c8d3  lea     eax, [rbx+r12]
0x18000c8d7  mov     rcx, rsi; struct _EVENT_TRACE_PROPERTIES *
0x18000c8da  lea     eax, ds:0B4h[rax*2]
0x18000c8e1  lea     rdx, [rsp+130h+Size]; unsigned int *
0x18000c8e6  mov     dword ptr [rsp+130h+Size], eax
0x18000c8ea  call    ?EtwpCheckFlagExtensions@@YAKPEAU_EVENT_TRACE_PROPERTIES@@PEAK@Z; EtwpCheckFlagExtensions(_EVENT_TRACE_PROPERTIES *,ulong *)
0x18000c8ef  mov     [rsp+130h+LastError], eax
0x18000c8f3  test    eax, eax
0x18000c8f5  jnz     loc_18000CBEF
0x18000c8fb  test    dword ptr [rsi+40h], 10000h
0x18000c902  mov     edx, 0FFFFFFF8h
0x18000c907  mov     dword ptr [rsp+130h+var_EC], eax
0x18000c90b  mov     eax, dword ptr [rsp+130h+Size]
0x18000c90f  jz      short loc_18000C922
0x18000c911  movzx   ecx, word ptr [r13+rsi+4]
0x18000c917  add     eax, 7
0x18000c91a  and     eax, edx
0x18000c91c  mov     dword ptr [rsp+130h+var_EC], ecx
0x18000c920  add     eax, ecx
0x18000c922  add     eax, 7
0x18000c925  and     eax, edx
0x18000c927  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c92e  mov     ecx, eax; unsigned __int64
0x18000c930  mov     [rsp+130h+Size], rax
  ... truncated ...
```
