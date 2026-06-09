# DumpLogRecords

- ea: `0x18000aec0`
- end: `0x18000b620`
- name: `DumpLogRecords`
- size: `1888`
- prototype: `BOOL __stdcall(PWSTR pwszLogFileName, CLFS_RECORD_TYPE fRecordType, PCLFS_LSN plsnStart, PCLFS_LSN plsnEnd, PFILE pstrmOut, CLFS_PRINT_RECORD_ROUTINE pfnPrintRecord, CLFS_BLOCK_ALLOCATION pfnAllocBlock, CLFS_BLOCK_DEALLOCATION pfnFreeBlock, PVOID pvBlockAllocContext, ULONG cbBlock, ULONG cMaxBlocks)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000187c`
- `0x180001cc8`
- `0x18000840c`
- `0x180009fe0`
- `0x18000aaa0`
- `0x18000aec0`
- `0x18000b940`
- `0x18000d8c0`
- `0x180010bdc`
- `0x1800114d8`
- `0x18001195c`
- `0x1800124f0`
- `0x180013058`
- `0x180014dce`
- `0x180014e00`
- `0x180016010`

## import_xrefs

- `msvcrt!fwprintf` at `0x18000b47f`
- `msvcrt!fwprintf` at `0x18000b542`
- `msvcrt!fwprintf` at `0x18000b571`
- `msvcrt!fwprintf` at `0x18001543a`
- `msvcrt!fwprintf` at `0x18001546f`
- `msvcrt!fwprintf` at `0x18000b47f`
- `msvcrt!fwprintf` at `0x18000b542`
- `msvcrt!fwprintf` at `0x18000b571`
- `msvcrt!fwprintf` at `0x18001543a`
- `msvcrt!fwprintf` at `0x18001546f`
- `msvcrt!fflush` at `0x18000b5c1`
- `msvcrt!fflush` at `0x1800154c5`
- `msvcrt!fflush` at `0x18000b5c1`
- `msvcrt!fflush` at `0x1800154c5`
- `ntdll!RtlInitUnicodeString` at `0x18000b18c`
- `ntdll!RtlInitUnicodeString` at `0x18000b18c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b1bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b36d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b418`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b4cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800154d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b1bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b36d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b418`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b4cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800154d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800154ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800154ae`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000b08f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000b08f`

## string_xrefs

- `0x18000b562`: `***Log record dump completed successfully for log file %s***\n`
- `0x18001545a`: `***Log record dump completed successfully for log file %s***\n`

## pseudocode

```c
BOOL __stdcall DumpLogRecords(
        PWSTR pwszLogFileName,
        CLFS_RECORD_TYPE fRecordType,
        PCLFS_LSN plsnStart,
        PCLFS_LSN plsnEnd,
        PFILE pstrmOut,
        CLFS_PRINT_RECORD_ROUTINE pfnPrintRecord,
        CLFS_BLOCK_ALLOCATION pfnAllocBlock,
        CLFS_BLOCK_DEALLOCATION pfnFreeBlock,
        PVOID pvBlockAllocContext,
        ULONG cbBlock,
        ULONG cMaxBlocks)
{
  FILE *v14; // r13
  ULONGLONG ullOffset; // rdi
  ULONG v16; // eax
  unsigned int (__fastcall *v17)(FILE *, unsigned __int8, void *, unsigned int); // rbx
  DWORD LastError; // r14d
  char *v19; // rax
  char *v20; // r12
  BOOL LogFileInformation; // r15d
  DWORD v22; // ecx
  CClfsMarshallingContext *v23; // rax
  CClfsMarshallingContext *v24; // r12
  DWORD v25; // ebx
  unsigned int v26; // eax
  DWORD v27; // ecx
  struct _CLFS_RECORD_HEADER *v28; // rax
  unsigned __int64 v29; // rbx
  struct _CLFS_RECORD_HEADER *v30; // rdx
  __int64 v31; // r8
  DWORD v32; // eax
  char v34; // [rsp+40h] [rbp-1B8h]
  char *hSourceHandle; // [rsp+48h] [rbp-1B0h]
  struct _CLFS_RECORD_HEADER *v37; // [rsp+60h] [rbp-198h] BYREF
  union _CLS_LSN BaseLsn; // [rsp+68h] [rbp-190h] BYREF
  ULONG v39; // [rsp+70h] [rbp-188h]
  PWSTR v40; // [rsp+78h] [rbp-180h]
  FILE *v41; // [rsp+80h] [rbp-178h]
  ULONGLONG v42; // [rsp+88h] [rbp-170h]
  CLFS_PRINT_RECORD_ROUTINE v43; // [rsp+90h] [rbp-168h]
  PVOID pvCursorContext; // [rsp+98h] [rbp-160h] BYREF
  PVOID pvMarshal; // [rsp+A0h] [rbp-158h]
  ULONG cbBuffer[2]; // [rsp+A8h] [rbp-150h] BYREF
  void (*v47)(void *, void *); // [rsp+B0h] [rbp-148h]
  void *v48; // [rsp+B8h] [rbp-140h]
  void *(*v49)(unsigned int, void *); // [rsp+C0h] [rbp-138h]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-130h] BYREF
  int v51; // [rsp+D8h] [rbp-120h]
  unsigned int (__fastcall *v52)(FILE *, unsigned __int8, void *, unsigned int); // [rsp+E0h] [rbp-118h]
  _SECURITY_ATTRIBUTES psaLogFile; // [rsp+E8h] [rbp-110h] BYREF
  char *v54; // [rsp+100h] [rbp-F8h]
  _OWORD pSecurityDescriptor[2]; // [rsp+108h] [rbp-F0h] BYREF
  __int64 v56; // [rsp+128h] [rbp-D0h]
  CLFS_INFORMATION pinfoBuffer; // [rsp+130h] [rbp-C8h] BYREF

  v43 = pfnPrintRecord;
  v40 = pwszLogFileName;
  v49 = pfnAllocBlock;
  v47 = pfnFreeBlock;
  v48 = pvBlockAllocContext;
  v14 = _acrt_iob_func(1u);
  pvMarshal = 0;
  pvCursorContext = 0;
  ullOffset = CLFS_LSN_INVALID.ullOffset;
  BaseLsn = CLFS_LSN_INVALID;
  v42 = CLFS_LSN_INVALID.ullOffset;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v37 = 0;
  v16 = 0;
  memset(&psaLogFile, 0, sizeof(psaLogFile));
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v56 = 0;
  if ( !pwszLogFileName )
    goto LABEL_80;
  if ( !cMaxBlocks )
    goto LABEL_80;
  if ( !cbBlock )
    goto LABEL_80;
  if ( fRecordType != (fRecordType & 0x3F) )
    goto LABEL_80;
  LOBYTE(v16) = fRecordType & 3;
  v39 = v16;
  cbBuffer[1] = v16;
  if ( (fRecordType & 3) == 0 )
    goto LABEL_80;
  if ( plsnStart )
  {
    if ( CLFS_LSN_INVALID.ullOffset == plsnStart->ullOffset )
      goto LABEL_80;
    BaseLsn = *plsnStart;
  }
  if ( !plsnEnd )
    goto LABEL_14;
  if ( CLFS_LSN_INVALID.ullOffset == plsnEnd->ullOffset || !plsnStart || plsnStart->ullOffset > plsnEnd->ullOffset )
  {
LABEL_80:
    SetLastError(0x57u);
    return 0;
  }
  ullOffset = plsnEnd->ullOffset;
  v42 = plsnEnd->ullOffset;
LABEL_14:
  if ( pstrmOut )
    v14 = pstrmOut;
  v41 = v14;
  v17 = (unsigned int (__fastcall *)(FILE *, unsigned __int8, void *, unsigned int))v43;
  if ( !v43 )
    v17 = NtPrintUserRecordBuffer;
  v43 = (CLFS_PRINT_RECORD_ROUTINE)v17;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    return 0;
  v34 = 0;
  LastError = 0;
  v52 = v17;
  psaLogFile.bInheritHandle = 0;
  psaLogFile.lpSecurityDescriptor = pSecurityDescriptor;
  psaLogFile.nLength = 24;
  cbBuffer[0] = 120;
  memset_0(&pinfoBuffer, 0, sizeof(pinfoBuffer));
  v19 = (char *)CreateLogFile(pwszLogFileName, 0x80000000, 7u, &psaLogFile, 3u, 0);
  v20 = v19;
  hSourceHandle = v19;
  if ( (unsigned __int64)(v19 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LogFileInformation = 0;
    goto LABEL_22;
  }
  if ( plsnStart )
  {
LABEL_25:
    pvMarshal = 0;
    if ( v49 )
    {
      if ( v47 )
      {
LABEL_30:
        if ( cbBlock < 0x200 )
        {
          v22 = 122;
        }
        else if ( (cbBlock & 0x1FF) != 0 )
        {
          v22 = 1784;
        }
        else
        {
          v23 = (CClfsMarshallingContext *)operator new(0x170u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v23 )
            v24 = CClfsMarshallingContext::CClfsMarshallingContext(v23, cMaxBlocks, cMaxBlocks);
          else
            v24 = 0;
          if ( v24 )
          {
            _InterlockedIncrement((volatile signed __int32 *)v24 + 27);
            v25 = CClfsMarshallingContext::Initialize(
                    v24,
                    hSourceHandle,
                    v49,
                    v47,
                    v48,
                    cbBlock,
                    cMaxBlocks,
                    cMaxBlocks);
            if ( v25 )
            {
              LogFileInformation = 0;
              CClfsMarshallingContext::Release(v24);
              v24 = 0;
            }
            else
            {
              LogFileInformation = 1;
            }
            pvMarshal = v24;
            SetLastError(v25);
LABEL_44:
            if ( LogFileInformation )
            {
              v48 = v24;
              if ( *(_DWORD *)v24 == -1040322550 && *((_DWORD *)v24 + 1) == 368 )
              {
                v26 = CClfsMarshallingContext::ReadLogRecord(
                        v24,
                        &BaseLsn,
                        ClfsContextForward,
                        &v37,
                        &pvCursorContext,
                        0);
                LastError = v26;
                if ( !v26 )
                {
                  v28 = v37;
                  v29 = *(_QWORD *)v37;
                  BaseLsn = *(union _CLS_LSN *)v37;
                  while ( !v34
                       && (CLFS_LSN_INVALID.ullOffset == ullOffset || v29 <= __PAIR64__(HIDWORD(v42), ullOffset)) )
                  {
                    NtPrintLogRecordHeader(v14, v28);
                    v30 = v37;
                    v31 = *((unsigned __int16 *)v37 + 17);
                    v51 = *((_DWORD *)v37 + 6) - v31;
                    v54 = (char *)v37 + v31;
                    LOBYTE(v30) = *((_BYTE *)v37 + 36) & 3;
                    v32 = ((__int64 (__fastcall *)(FILE *, struct _CLFS_RECORD_HEADER *))v43)(v14, v30);
                    LastError = v32;
                    if ( v32 )
                    {
                      fwprintf(v14, L"\n\nEncountered error calling user print record routine...error code %x\n", v32);
                      v27 = LastError;
                      goto LABEL_50;
                    }
                    v26 = CClfsMarshallingContext::ReadNextLogRecord(v24, pvCursorContext, v39, 0, &v37, 0);
                    LastError = v26;
                    if ( v26 == 38 )
                    {
                      v34 = 1;
                      SetLastError(0);
                      LogFileInformation = 1;
                      v28 = v37;
                    }
                    else
                    {
                      if ( v26 )
                        goto LABEL_49;
                      v28 = v37;
                      v29 = *(_QWORD *)v37;
                      BaseLsn = *(union _CLS_LSN *)v37;
                    }
                  }
                  goto LABEL_63;
                }
LABEL_49:
                v27 = v26;
              }
              else
              {
                v27 = 87;
              }
LABEL_50:
              SetLastError(v27);
            }
            else
            {
              LastError = GetLastError();
            }
LABEL_63:
            v20 = hSourceHandle;
            goto LABEL_64;
          }
          v22 = 14;
        }
LABEL_43:
        SetLastError(v22);
        v24 = 0;
        LogFileInformation = 0;
        goto LABEL_44;
      }
    }
    else if ( !v47 )
    {
      goto LABEL_30;
    }
    v22 = 87;
    goto LABEL_43;
  }
  LogFileInformation = GetLogFileInformation(v19, &pinfoBuffer, cbBuffer);
  if ( LogFileInformation )
  {
    RtlInitUnicodeString(&DestinationString, pwszLogFileName);
    BaseLsn = pinfoBuffer.BaseLsn;
    if ( CLFS_LSN_INVALID.ullOffset == pinfoBuffer.BaseLsn.ullOffset )
    {
      LastError = 5023;
      SetLastError(0x139Fu);
      goto LABEL_64;
    }
    goto LABEL_25;
  }
LABEL_22:
  LastError = GetLastError();
LABEL_64:
  if ( LastError )
  {
    if ( LastError == 38 )
    {
      fwprintf(v14, L"***Reached end of file for log file %s***\n", pwszLogFileName);
    }
    else if ( LastError == 6618 )
    {
      fwprintf(v14, L"***Reached start of file for log file %s***\n", pwszLogFileName);
    }
    else
    {
      fwprintf(
        v14,
        L"***Log record dump for log file %s unsuccessful with return code %x***\n",
        pwszLogFileName,
        LastError);
    }
  }
  else
  {
    fwprintf(v14, L"***Log record dump completed successfully for log file %s***\n", pwszLogFileName);
  }
  if ( pvCursorContext )
    TerminateReadLog(pvCursorContext);
  if ( pvMarshal )
    DeleteLogMarshallingArea(pvMarshal);
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v20);
  fflush(v14);
  if ( LastError )
  {
    SetLastError(LastError);
    return 0;
  }
  return LogFileInformation;
}

```

## disassembly

```asm
0x18000aec0  push    rbx
0x18000aec2  push    rsi
0x18000aec3  push    rdi
0x18000aec4  push    r12
0x18000aec6  push    r13
0x18000aec8  push    r14
0x18000aeca  push    r15
0x18000aecc  sub     rsp, 1C0h
0x18000aed3  mov     rax, cs:__security_cookie
0x18000aeda  xor     rax, rsp
0x18000aedd  mov     [rsp+1F8h+var_48], rax
0x18000aee5  mov     r14, r9
0x18000aee8  mov     r15, r8
0x18000aeeb  mov     bl, dl
0x18000aeed  mov     rax, rcx
0x18000aef0  mov     [rsp+1F8h+pszLogFileName], rcx
0x18000aef5  mov     rcx, [rsp+1F8h+pfnPrintRecord]
0x18000aefd  mov     [rsp+1F8h+var_168], rcx
0x18000af05  mov     [rsp+1F8h+var_180], rax
0x18000af0a  mov     r12, [rsp+1F8h+pstrmOut]
0x18000af12  mov     r8, [rsp+1F8h+pfnAllocBlock]
0x18000af1a  mov     [rsp+1F8h+var_138], r8
0x18000af22  mov     rax, [rsp+1F8h+pfnFreeBlock]
0x18000af2a  mov     [rsp+1F8h+var_148], rax
0x18000af32  mov     rax, [rsp+1F8h+pvBlockAllocContext]
0x18000af3a  mov     [rsp+1F8h+var_140], rax
0x18000af42  mov     ecx, 1; Ix
0x18000af47  call    __acrt_iob_func
0x18000af4c  mov     r13, rax
0x18000af4f  xor     esi, esi
0x18000af51  mov     [rsp+1F8h+pvMarshal], rsi
0x18000af59  mov     [rsp+1F8h+pvCursorContext], rsi
0x18000af61  mov     rdi, qword ptr cs:CLFS_LSN_INVALID
0x18000af68  mov     qword ptr [rsp+1F8h+var_190], rdi
0x18000af6d  mov     [rsp+1F8h+var_170], rdi
0x18000af75  mov     qword ptr [rsp+1F8h+DestinationString.Length], rsi
0x18000af7d  mov     [rsp+1F8h+DestinationString.Buffer], rsi
0x18000af85  mov     [rsp+1F8h+var_198], rsi
0x18000af8a  xorps   xmm0, xmm0
0x18000af8d  xor     eax, eax
0x18000af8f  movups  xmmword ptr [rsp+1F8h+psaLogFile.nLength], xmm0
0x18000af97  mov     qword ptr [rsp+1F8h+psaLogFile.bInheritHandle], rax
0x18000af9f  xorps   xmm1, xmm1
0x18000afa2  movups  [rsp+1F8h+pSecurityDescriptor], xmm1
0x18000afaa  movups  [rsp+1F8h+var_E0], xmm1
0x18000afb2  mov     [rsp+1F8h+var_D0], rax
0x18000afba  cmp     [rsp+1F8h+pszLogFileName], rsi
0x18000afbf  jz      loc_18000B5E9
0x18000afc5  cmp     [rsp+1F8h+cMaxBlocks], esi
0x18000afcc  jz      loc_18000B5E9
0x18000afd2  cmp     [rsp+1F8h+cbBlock], esi
0x18000afd9  jz      loc_18000B5E9
0x18000afdf  mov     al, bl
0x18000afe1  and     al, 3Fh
0x18000afe3  cmp     bl, al
0x18000afe5  jnz     loc_18000B5E9
0x18000afeb  and     bl, 3
0x18000afee  mov     al, bl
0x18000aff0  mov     [rsp+1F8h+var_188], eax
0x18000aff4  mov     [rsp+1F8h+var_14C], eax
0x18000affb  jz      loc_18000B5E9
0x18000b001  test    r15, r15
0x18000b004  jz      short loc_18000B017
0x18000b006  mov     rax, [r15]
0x18000b009  cmp     rdi, rax
0x18000b00c  jz      loc_18000B5E9
0x18000b012  mov     qword ptr [rsp+1F8h+var_190], rax
0x18000b017  test    r14, r14
0x18000b01a  jz      short loc_18000B055
0x18000b01c  cmp     rdi, [r14]
0x18000b01f  jz      loc_18000B5E9
0x18000b025  test    r15, r15
0x18000b028  jz      loc_18000B5E9
0x18000b02e  mov     eax, [r15+4]
0x18000b032  cmp     eax, [r14+4]
0x18000b036  jb      short loc_18000B04A
0x18000b038  jnz     loc_18000B5E9
0x18000b03e  mov     eax, [r14]
0x18000b041  cmp     [r15], eax
0x18000b044  ja      loc_18000B5E9
0x18000b04a  mov     rdi, [r14]
0x18000b04d  mov     [rsp+1F8h+var_170], rdi
0x18000b055  test    r12, r12
0x18000b058  cmovnz  r13, r12
0x18000b05c  mov     [rsp+1F8h+var_178], r13
0x18000b064  lea     rax, ?NtPrintUserRecordBuffer@@YAKPEAU_iobuf@@EPEAXK@Z; NtPrintUserRecordBuffer(_iobuf *,uchar,void *,ulong)
0x18000b06b  mov     rbx, [rsp+1F8h+var_168]
0x18000b073  test    rbx, rbx
0x18000b076  cmovz   rbx, rax
0x18000b07a  mov     [rsp+1F8h+var_168], rbx
0x18000b082  mov     edx, 1; dwRevision
0x18000b087  lea     rcx, [rsp+1F8h+pSecurityDescriptor]; pSecurityDescriptor
0x18000b08f  call    cs:__imp_InitializeSecurityDescriptor
0x18000b096  nop     dword ptr [rax+rax+00h]
0x18000b09b  test    eax, eax
0x18000b09d  jz      loc_18000B5FA
0x18000b0a3  mov     [rsp+1F8h+var_1B8], sil
0x18000b0a8  mov     r14d, esi
0x18000b0ab  mov     [rsp+1F8h+var_1B4], esi
0x18000b0af  mov     [rsp+1F8h+hSourceHandle], rsi
0x18000b0b4  mov     [rsp+1F8h+var_118], rbx
0x18000b0bc  mov     [rsp+1F8h+psaLogFile.bInheritHandle], esi
0x18000b0c3  lea     rax, [rsp+1F8h+pSecurityDescriptor]
0x18000b0cb  mov     [rsp+1F8h+psaLogFile.lpSecurityDescriptor], rax
0x18000b0d3  mov     [rsp+1F8h+psaLogFile.nLength], 18h
0x18000b0de  mov     r8d, 78h ; 'x'; Size
0x18000b0e4  mov     [rsp+1F8h+cbBuffer], r8d
0x18000b0ec  xor     edx, edx; Val
0x18000b0ee  lea     rcx, [rsp+1F8h+pinfoBuffer]; void *
0x18000b0f6  call    memset_0
0x18000b0fb  mov     [rsp+1F8h+fFlagsAndAttributes], esi; fFlagsAndAttributes
0x18000b0ff  mov     [rsp+1F8h+fCreateDisposition], 3; fCreateDisposition
0x18000b107  lea     r9, [rsp+1F8h+psaLogFile]; psaLogFile
0x18000b10f  mov     edx, 80000000h; fDesiredAccess
0x18000b114  mov     r8d, 7; dwShareMode
0x18000b11a  mov     rbx, [rsp+1F8h+pszLogFileName]
0x18000b11f  mov     rcx, rbx; pszLogFileName
0x18000b122  call    CreateLogFile
0x18000b127  mov     r12, rax
0x18000b12a  mov     [rsp+1F8h+hSourceHandle], rax
0x18000b12f  lea     rcx, [rax-1]
0x18000b133  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000b137  ja      loc_18000B50B
0x18000b13d  test    r15, r15
0x18000b140  jnz     loc_18000B1CD
0x18000b146  lea     r8, [rsp+1F8h+cbBuffer]; cbBuffer
0x18000b14e  lea     rdx, [rsp+1F8h+pinfoBuffer]; pinfoBuffer
0x18000b156  mov     rcx, rax; hLog
0x18000b159  call    GetLogFileInformation
0x18000b15e  mov     r15d, eax
0x18000b161  mov     [rsp+1F8h+var_1A8], eax
0x18000b165  test    eax, eax
0x18000b167  jnz     short loc_18000B181
0x18000b169  call    cs:__imp_GetLastError
0x18000b170  nop     dword ptr [rax+rax+00h]
0x18000b175  mov     r14d, eax
0x18000b178  mov     [rsp+1F8h+var_1B4], eax
0x18000b17c  jmp     loc_18000B51C
0x18000b181  mov     rdx, rbx; SourceString
0x18000b184  lea     rcx, [rsp+1F8h+DestinationString]; DestinationString
0x18000b18c  call    cs:__imp_RtlInitUnicodeString
0x18000b193  nop     dword ptr [rax+rax+00h]
0x18000b198  mov     rax, qword ptr [rsp+1F8h+pinfoBuffer.BaseLsn]
0x18000b1a0  mov     qword ptr [rsp+1F8h+var_190], rax
0x18000b1a5  cmp     qword ptr cs:CLFS_LSN_INVALID, rax
0x18000b1ac  jnz     short loc_18000B1CD
0x18000b1ae  mov     r14d, 139Fh
0x18000b1b4  mov     [rsp+1F8h+var_1B4], r14d
0x18000b1b9  mov     ecx, r14d; dwErrCode
0x18000b1bc  call    cs:__imp_SetLastError
0x18000b1c3  nop     dword ptr [rax+rax+00h]
0x18000b1c8  jmp     loc_18000B51C
0x18000b1cd  mov     [rsp+1F8h+pvMarshal], rsi
0x18000b1d5  mov     rax, [rsp+1F8h+var_138]
0x18000b1dd  mov     rcx, [rsp+1F8h+var_148]
0x18000b1e5  test    rax, rax
0x18000b1e8  jz      short loc_18000B1F4
0x18000b1ea  test    rcx, rcx
0x18000b1ed  jz      short loc_18000B1F9
0x18000b1ef  test    rax, rax
0x18000b1f2  jnz     short loc_18000B203
0x18000b1f4  test    rcx, rcx
0x18000b1f7  jz      short loc_18000B203
0x18000b1f9  mov     ecx, 57h ; 'W'
0x18000b1fe  jmp     loc_18000B2DD
0x18000b203  mov     ebx, [rsp+1F8h+cbBlock]
0x18000b20a  cmp     ebx, 200h
0x18000b210  jb      loc_18000B2D8
0x18000b216  test    ebx, 1FFh
0x18000b21c  jz      short loc_18000B228
0x18000b21e  mov     ecx, 6F8h
0x18000b223  jmp     loc_18000B2DD
0x18000b228  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b22f  mov     ecx, 170h; unsigned __int64
0x18000b234  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b239  mov     r15d, [rsp+1F8h+cMaxBlocks]
0x18000b241  test    rax, rax
0x18000b244  jz      short loc_18000B259
0x18000b246  mov     r8d, r15d; unsigned int
0x18000b249  mov     edx, r15d; unsigned int
0x18000b24c  mov     rcx, rax; this
0x18000b24f  call    ??0CClfsMarshallingContext@@QEAA@KK@Z; CClfsMarshallingContext::CClfsMarshallingContext(ulong,ulong)
0x18000b254  mov     r12, rax
0x18000b257  jmp     short loc_18000B25C
0x18000b259  mov     r12, rsi
0x18000b25c  test    r12, r12
0x18000b25f  jnz     short loc_18000B268
0x18000b261  lea     ecx, [r12+0Eh]
0x18000b266  jmp     short loc_18000B2DD
0x18000b268  lock inc dword ptr [r12+6Ch]
0x18000b26e  mov     [rsp+1F8h+var_1C0], r15d; unsigned int
0x18000b273  mov     [rsp+1F8h+var_1C8], r15d; unsigned int
0x18000b278  mov     [rsp+1F8h+fFlagsAndAttributes], ebx; unsigned int
0x18000b27c  mov     rax, [rsp+1F8h+var_140]
0x18000b284  mov     qword ptr [rsp+1F8h+fCreateDisposition], rax; void *
0x18000b289  mov     r9, [rsp+1F8h+var_148]; void (*)(void *, void *)
0x18000b291  mov     r8, [rsp+1F8h+var_138]; void *(*)(unsigned int, void *)
0x18000b299  mov     rdx, [rsp+1F8h+hSourceHandle]; hSourceHandle
0x18000b29e  mov     rcx, r12; this
0x18000b2a1  call    ?Initialize@CClfsMarshallingContext@@QEAAKPEAXP6APEAXK0@ZP6AX00@Z0KKK@Z; CClfsMarshallingContext::Initialize(void *,void * (*)(ulong,void *),void (*)(void *,void *),void *,ulong,ulong,ulong)
0x18000b2a6  mov     ebx, eax
0x18000b2a8  test    eax, eax
0x18000b2aa  jnz     short loc_18000B2B2
0x18000b2ac  lea     r15d, [rax+1]
0x18000b2b0  jmp     short loc_18000B2C0
0x18000b2b2  mov     r15d, esi
0x18000b2b5  mov     rcx, r12; this
0x18000b2b8  call    ?Release@CClfsMarshallingContext@@QEAAKXZ; CClfsMarshallingContext::Release(void)
0x18000b2bd  mov     r12, rsi
0x18000b2c0  mov     [rsp+1F8h+pvMarshal], r12
0x18000b2c8  mov     ecx, ebx; dwErrCode
0x18000b2ca  call    cs:__imp_SetLastError
0x18000b2d1  nop     dword ptr [rax+rax+00h]
0x18000b2d6  jmp     short loc_18000B2EF
0x18000b2d8  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000b2dd  call    cs:__imp_SetLastError
0x18000b2e4  nop     dword ptr [rax+rax+00h]
0x18000b2e9  mov     r12, rsi
0x18000b2ec  mov     r15d, esi
0x18000b2ef  mov     [rsp+1F8h+var_1A8], r15d
0x18000b2f4  test    r15d, r15d
0x18000b2f7  jnz     short loc_18000B311
0x18000b2f9  call    cs:__imp_GetLastError
0x18000b300  nop     dword ptr [rax+rax+00h]
0x18000b305  mov     r14d, eax
0x18000b308  mov     [rsp+1F8h+var_1B4], eax
0x18000b30c  jmp     loc_18000B517
0x18000b311  mov     [rsp+1F8h+var_140], r12
0x18000b319  cmp     dword ptr [r12], 0C1FDF00Ah
0x18000b321  jnz     loc_18000B501
0x18000b327  cmp     dword ptr [r12+4], 170h
0x18000b330  jnz     loc_18000B501
0x18000b336  mov     qword ptr [rsp+1F8h+fFlagsAndAttributes], rsi; struct _OVERLAPPED *
0x18000b33b  lea     rax, [rsp+1F8h+pvCursorContext]
0x18000b343  mov     qword ptr [rsp+1F8h+fCreateDisposition], rax; void **
0x18000b348  lea     r9, [rsp+1F8h+var_198]; struct _CLFS_RECORD_HEADER **
0x18000b34d  mov     r8d, 3; enum _CLFS_CONTEXT_MODE
0x18000b353  lea     rdx, [rsp+1F8h+var_190]; union _CLS_LSN *
0x18000b358  mov     rcx, r12; this
0x18000b35b  call    ?ReadLogRecord@CClfsMarshallingContext@@QEAAKAEBT_CLS_LSN@@W4_CLFS_CONTEXT_MODE@@AEAPEAU_CLFS_RECORD_HEADER@@AEAPEAXPEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::ReadLogRecord(_CLS_LSN const &,_CLFS_CONTEXT_MODE,_CLFS_RECORD_HEADER * &,void * &,_OVERLAPPED *)
0x18000b360  mov     r14d, eax
0x18000b363  mov     [rsp+1F8h+var_1B4], eax
0x18000b367  test    eax, eax
0x18000b369  jz      short loc_18000B37E
0x18000b36b  mov     ecx, eax; dwErrCode
0x18000b36d  call    cs:__imp_SetLastError
0x18000b374  nop     dword ptr [rax+rax+00h]
0x18000b379  jmp     loc_18000B517
0x18000b37e  mov     rax, [rsp+1F8h+var_198]
0x18000b383  mov     rbx, [rax]
0x18000b386  mov     qword ptr [rsp+1F8h+var_190], rbx
0x18000b38b  cmp     [rsp+1F8h+var_1B8], sil
0x18000b390  jnz     loc_18000B517
0x18000b396  cmp     qword ptr cs:CLFS_LSN_INVALID, rdi
0x18000b39d  jz      short loc_18000B3BD
0x18000b39f  mov     rcx, rbx
0x18000b3a2  shr     rcx, 20h
0x18000b3a6  cmp     ecx, dword ptr [rsp+1F8h+var_170+4]
0x18000b3ad  jb      short loc_18000B3BD
0x18000b3af  jnz     loc_18000B517
0x18000b3b5  cmp     ebx, edi
0x18000b3b7  ja      loc_18000B517
0x18000b3bd  mov     rdx, rax; struct _CLFS_RECORD_HEADER *
0x18000b3c0  mov     rcx, r13; Stream
0x18000b3c3  call    ?NtPrintLogRecordHeader@@YAKQEAU_iobuf@@AEBU_CLFS_RECORD_HEADER@@@Z; NtPrintLogRecordHeader(_iobuf * const,_CLFS_RECORD_HEADER const &)
0x18000b3c8  mov     rdx, [rsp+1F8h+var_198]
0x18000b3cd  movzx   r8d, word ptr [rdx+22h]
0x18000b3d2  mov     r9d, [rdx+18h]
0x18000b3d6  sub     r9d, r8d
0x18000b3d9  mov     [rsp+1F8h+var_120], r9d
0x18000b3e1  add     r8, rdx
0x18000b3e4  mov     [rsp+1F8h+var_F8], r8
0x18000b3ec  mov     dl, [rdx+24h]
0x18000b3ef  and     dl, 3
0x18000b3f2  mov     rcx, r13
0x18000b3f5  mov     rax, [rsp+1F8h+var_168]
0x18000b3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b402  mov     r14d, eax
0x18000b405  mov     [rsp+1F8h+var_1B4], eax
0x18000b409  mov     ecx, [rsp+1F8h+var_188]
0x18000b40d  jmp     short loc_18000B46D
0x18000b40f  mov     r14d, eax
0x18000b412  mov     [rsp+1F8h+var_1B4], eax
0x18000b416  mov     ecx, eax; dwErrCode
0x18000b418  call    cs:__imp_SetLastError
0x18000b41f  nop     dword ptr [rax+rax+00h]
0x18000b424  xor     esi, esi
0x18000b426  mov     r15d, [rsp+1F8h+var_1A8]
0x18000b42b  mov     r13, [rsp+1F8h+var_178]
0x18000b433  mov     rbx, qword ptr [rsp+1F8h+var_190]
0x18000b438  mov     rdi, [rsp+1F8h+var_170]
0x18000b440  mov     ecx, [rsp+1F8h+var_14C]
0x18000b447  mov     [rsp+1F8h+var_188], ecx
0x18000b44b  mov     r12, [rsp+1F8h+var_140]
0x18000b453  mov     rax, [rsp+1F8h+var_180]
0x18000b458  mov     [rsp+1F8h+pszLogFileName], rax
0x18000b45d  mov     rax, [rsp+1F8h+var_118]
0x18000b465  mov     [rsp+1F8h+var_168], rax
0x18000b46d  test    r14d, r14d
0x18000b470  jz      short loc_18000B493
  ... truncated ...
```
