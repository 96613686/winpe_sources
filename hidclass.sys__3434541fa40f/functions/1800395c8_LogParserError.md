# LogParserError

- ea: `0x1800395c8`
- end: `0x18003a1af`
- name: `LogParserError`
- size: `3047`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x180042b00`

## callees

- `0x18000ddc8`
- `0x180021d38`
- `0x180021e1c`
- `0x1800222c0`
- `0x1800223ac`
- `0x1800395c8`

## string_xrefs

- `0x1800396aa`: `Couldn't allocate memory for preparse data`
- `0x180039848`: `One byte was expected in the report descriptor but not found`
- `0x180039b27`: `Two bytes were expected in the report descriptor but not found`
- `0x180039a9d`: `Four bytes were expected in the report descriptor but not found`
- `0x180039e43`: `An unknown item was found in the report descriptor`
- `0x180039dcf`: `Report ID declaration found outside of top level collection`
- `0x18003a196`: `A main item was detected outside of a top level collection`
- `0x18003a10c`: `A start delimiter token was found with no corresponding end delimiter`
- `0x18003a00e`: `The parser detected either a close delimiter without a corresponding open delimiter or detected a nested open delimiter`
- `0x180039f84`: `The given report descriptor was found to have a valid report descriptorcontaining a scenario that this parser does not support`

## pseudocode

```c
__int64 __fastcall LogParserError(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // eax
  __int64 v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  __int64 result; // rax
  bool v10; // dl
  const char *v11; // rdx
  bool v12; // dl
  bool v13; // dl
  bool v14; // dl
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  bool v18; // dl
  const char *v19; // rdx
  bool v20; // dl
  bool v21; // dl
  bool v22; // dl
  bool v23; // dl
  bool v24; // dl
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  bool v28; // dl
  bool v29; // dl
  bool v30; // dl
  bool v31; // dl
  bool v32; // dl
  bool v33; // dl
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  bool v37; // dl
  bool v38; // dl
  bool v39; // dl
  bool v40; // dl
  bool v41; // dl

  v3 = *(_DWORD *)(a1 + 192);
  v5 = *(unsigned int *)(a1 + 188);
  if ( v3 <= 0x10 )
  {
    if ( v3 == 16 )
    {
LABEL_97:
      v24 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qL(
          WPP_GLOBAL_Control->AttachedDevice,
          v24,
          a3,
          g_RecorderLog,
          2,
          3,
          51,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          *(_QWORD *)a1,
          v5);
      v11 = "Insufficient resources to allocate needed memory";
      return TraceLoggingParserError(a1, v11, a3, v5);
    }
    if ( v3 <= 6 )
    {
      if ( v3 == 6 )
      {
        v14 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_qL(
            WPP_GLOBAL_Control->AttachedDevice,
            v14,
            a3,
            g_RecorderLog,
            2,
            3,
            55,
            (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
            *(_QWORD *)a1,
            v5);
        v11 = "One byte was expected in the report descriptor but not found";
        return TraceLoggingParserError(a1, v11, a3, v5);
      }
      v6 = v3 - 1;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            result = v8 - 1;
            if ( (_DWORD)result )
            {
              if ( (_DWORD)result != 1 )
                return result;
              v10 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_AND_TRACE_SF_qL(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v10,
                  a3,
                  g_RecorderLog,
                  2,
                  3,
                  54,
                  (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
                  *(_QWORD *)a1,
                  v5);
              v11 = "Couldn't allocate memory for preparse data";
            }
            else
            {
              v12 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_AND_TRACE_SF_qL(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v12,
                  a3,
                  g_RecorderLog,
                  2,
                  3,
                  53,
                  (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
                  *(_QWORD *)a1,
                  v5);
              v11 = "Extra end collection found or end collection not found";
            }
          }
          else
          {
            v13 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
            LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_AND_TRACE_SF_qL(
                WPP_GLOBAL_Control->AttachedDevice,
                v13,
                a3,
                g_RecorderLog,
                2,
                3,
                52,
                (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
                *(_QWORD *)a1,
                v5);
            v11 = "Insufficient resources to make top level collection";
          }
          return TraceLoggingParserError(a1, v11, a3, v5);
        }
      }
      goto LABEL_97;
    }
    v15 = v3 - 7;
    if ( !v15 )
    {
      v23 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v23 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qL(
          WPP_GLOBAL_Control->AttachedDevice,
          v23,
          a3,
          g_RecorderLog,
          2,
          3,
          56,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          *(_QWORD *)a1,
          v5);
      v11 = "Two bytes were expected in the report descriptor but not found";
      return TraceLoggingParserError(a1, v11, a3, v5);
    }
    v16 = v15 - 1;
    if ( !v16 )
    {
      v22 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v22 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qL(
          WPP_GLOBAL_Control->AttachedDevice,
          v22,
          a3,
          g_RecorderLog,
          2,
          3,
          57,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          *(_QWORD *)a1,
          v5);
      v11 = "Four bytes were expected in the report descriptor but not found";
      return TraceLoggingParserError(a1, v11, a3, v5);
    }
    v17 = v16 - 1;
    if ( v17 )
    {
      result = v17 - 1;
      if ( !(_DWORD)result )
      {
        v20 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_qL(
            WPP_GLOBAL_Control->AttachedDevice,
            v20,
            a3,
            g_RecorderLog,
            2,
            3,
            59,
            (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
            *(_QWORD *)a1,
            v5);
        v11 = "A non constant main item was declared without a corresponding usage";
        return TraceLoggingParserError(a1, v11, a3, v5);
      }
      if ( (_DWORD)result != 1 )
        return result;
      v18 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      if ( v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, v18, a3, v5);
      }
      v19 = "A top level collection was declared without a usage or with more than one usage";
    }
    else
    {
      v21 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      if ( v21 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qDddddd(WPP_GLOBAL_Control->AttachedDevice, v21, a3, v5);
      }
      v19 = "Report was not byte aligned. Collection is";
    }
    return TraceLoggingParserErrorWithParam(a1, v19, *(unsigned int *)(a1 + 196), v5);
  }
  if ( v3 <= 0x1A )
  {
    if ( v3 == 26 )
    {
      v33 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_qL(
          WPP_GLOBAL_Control->AttachedDevice,
          v33,
          a3,
          g_RecorderLog,
          2,
          3,
          66,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          *(_QWORD *)a1,
          v5);
      v11 = "No top level collections were found in this device";
      return TraceLoggingParserError(a1, v11, a3, v5);
    }
    v25 = v3 - 18;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( !v27 )
        {
          v30 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v30 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_AND_TRACE_SF_qL(
              WPP_GLOBAL_Control->AttachedDevice,
              v30,
              a3,
              g_RecorderLog,
              2,
              3,
              63,
              (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
              *(_QWORD *)a1,
              v5);
          v11 = "A bad report ID value was found.Report IDs must be within the range of 1-255";
          return TraceLoggingParserError(a1, v11, a3, v5);
        }
        result = v27 - 1;
        if ( (_DWORD)result )
        {
          if ( (_DWORD)result != 1 )
            return result;
          v28 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          if ( v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, v28, a3, v5);
          }
          v19 = "The default report ID is only allowed for devices with one top-level collection and don't have any repor"
                "t IDs explicitly declared";
        }
        else
        {
          v29 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          if ( v29 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, v29, a3, v5);
          }
          v19 = "No report ID in collection";
        }
      }
      else
      {
        v31 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        if ( v31 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, v31, a3, v5);
        }
        v19 = "Report ID declaration found outside of top level collection";
      }
    }
    else
    {
      v32 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      if ( v32 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, v32, a3, v5);
      }
      v19 = "An unknown item was found in the report descriptor";
    }
    return TraceLoggingParserErrorWithParam(a1, v19, *(unsigned int *)(a1 + 196), v5);
  }
  v34 = v3 - 27;
  if ( !v34 )
  {
    v41 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v41 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v41,
        a3,
        g_RecorderLog,
        2,
        3,
        67,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *(_QWORD *)a1,
        v5);
    v11 = "A main item was detected outside of a top level collection";
    return TraceLoggingParserError(a1, v11, a3, v5);
  }
  v35 = v34 - 5;
  if ( !v35 )
  {
    v40 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v40 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v40,
        a3,
        g_RecorderLog,
        2,
        3,
        68,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *(_QWORD *)a1,
        v5);
    v11 = "A start delimiter token was found with no corresponding end delimiter";
    return TraceLoggingParserError(a1, v11, a3, v5);
  }
  v36 = v35 - 1;
  if ( !v36 )
  {
    v39 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( v39 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, v39, a3, v5);
    }
    v19 = "The parser detected a non-usage item with a delimiter declaration";
    return TraceLoggingParserErrorWithParam(a1, v19, *(unsigned int *)(a1 + 196), v5);
  }
  result = v36 - 1;
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result != 30 )
      return result;
    v37 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v37 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v37,
        a3,
        g_RecorderLog,
        2,
        3,
        71,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *(_QWORD *)a1,
        v5);
    v11 = "The given report descriptor was found to have a valid report descriptorcontaining a scenario that this parser "
          "does not support";
  }
  else
  {
    v38 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v38 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v38,
        a3,
        g_RecorderLog,
        2,
        3,
        70,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *(_QWORD *)a1,
        v5);
    v11 = "The parser detected either a close delimiter without a corresponding open delimiter or detected a nested open delimiter";
  }
  return TraceLoggingParserError(a1, v11, a3, v5);
}

```

## disassembly

```asm
0x1800395c8  push    rbx
0x1800395ca  sub     rsp, 80h
0x1800395d1  mov     eax, [rcx+0C0h]
0x1800395d7  mov     rbx, rcx
0x1800395da  mov     r9d, [rcx+0BCh]
0x1800395e1  cmp     eax, 10h
0x1800395e4  ja      loc_180039BBD
0x1800395ea  jz      loc_180039B33
0x1800395f0  cmp     eax, 6
0x1800395f3  ja      loc_180039854
0x1800395f9  jz      loc_1800397CA
0x1800395ff  sub     eax, 1
0x180039602  jz      loc_180039B33
0x180039608  sub     eax, 1
0x18003960b  jz      loc_180039B33
0x180039611  sub     eax, 1
0x180039614  jz      loc_180039740
0x18003961a  sub     eax, 1
0x18003961d  jz      loc_1800396B6
0x180039623  cmp     eax, 1
0x180039626  jnz     loc_18003A1A5
0x18003962c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039633  lea     rax, WPP_GLOBAL_Control
0x18003963a  cmp     rcx, rax
0x18003963d  jz      short loc_180039650
0x18003963f  mov     eax, [rcx+2Ch]
0x180039642  test    al, 4
0x180039644  jz      short loc_180039650
0x180039646  cmp     byte ptr [rcx+29h], 2
0x18003964a  jb      short loc_180039650
0x18003964c  mov     dl, 1
0x18003964e  jmp     short loc_180039652
0x180039650  xor     dl, dl
0x180039652  lea     rax, WPP_RECORDER_INITIALIZED
0x180039659  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180039660  setnz   r8b
0x180039664  test    dl, dl
0x180039666  jnz     short loc_18003966D
0x180039668  test    r8b, r8b
0x18003966b  jz      short loc_1800396AA
0x18003966d  mov     rax, [rbx]
0x180039670  mov     rcx, [rcx+18h]
0x180039674  mov     [rsp+88h+var_40], r9d
0x180039679  mov     r9, cs:g_RecorderLog
0x180039680  mov     [rsp+88h+var_48], rax
0x180039685  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18003968c  mov     [rsp+88h+var_50], rax
0x180039691  mov     [rsp+88h+var_58], 36h ; '6'
0x180039698  mov     [rsp+88h+var_60], 3
0x1800396a0  mov     [rsp+88h+var_68], 2
0x1800396a5  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1800396aa  lea     rdx, aCouldnTAllocat; "Couldn't allocate memory for preparse d"...
0x1800396b1  jmp     loc_18003A19D
0x1800396b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396bd  lea     rax, WPP_GLOBAL_Control
0x1800396c4  cmp     rcx, rax
0x1800396c7  jz      short loc_1800396DA
0x1800396c9  mov     eax, [rcx+2Ch]
0x1800396cc  test    al, 4
0x1800396ce  jz      short loc_1800396DA
0x1800396d0  cmp     byte ptr [rcx+29h], 2
0x1800396d4  jb      short loc_1800396DA
0x1800396d6  mov     dl, 1
0x1800396d8  jmp     short loc_1800396DC
0x1800396da  xor     dl, dl
0x1800396dc  lea     rax, WPP_RECORDER_INITIALIZED
0x1800396e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800396ea  setnz   r8b
0x1800396ee  test    dl, dl
0x1800396f0  jnz     short loc_1800396F7
0x1800396f2  test    r8b, r8b
0x1800396f5  jz      short loc_180039734
0x1800396f7  mov     rax, [rbx]
0x1800396fa  mov     rcx, [rcx+18h]
0x1800396fe  mov     [rsp+88h+var_40], r9d
0x180039703  mov     r9, cs:g_RecorderLog
0x18003970a  mov     [rsp+88h+var_48], rax
0x18003970f  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x180039716  mov     [rsp+88h+var_50], rax
0x18003971b  mov     [rsp+88h+var_58], 35h ; '5'
0x180039722  mov     [rsp+88h+var_60], 3
0x18003972a  mov     [rsp+88h+var_68], 2
0x18003972f  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180039734  lea     rdx, aExtraEndCollec; "Extra end collection found or end colle"...
0x18003973b  jmp     loc_18003A19D
0x180039740  mov     rcx, cs:WPP_GLOBAL_Control
0x180039747  lea     rax, WPP_GLOBAL_Control
0x18003974e  cmp     rcx, rax
0x180039751  jz      short loc_180039764
0x180039753  mov     eax, [rcx+2Ch]
0x180039756  test    al, 4
0x180039758  jz      short loc_180039764
0x18003975a  cmp     byte ptr [rcx+29h], 2
0x18003975e  jb      short loc_180039764
0x180039760  mov     dl, 1
0x180039762  jmp     short loc_180039766
0x180039764  xor     dl, dl
0x180039766  lea     rax, WPP_RECORDER_INITIALIZED
0x18003976d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180039774  setnz   r8b
0x180039778  test    dl, dl
0x18003977a  jnz     short loc_180039781
0x18003977c  test    r8b, r8b
0x18003977f  jz      short loc_1800397BE
0x180039781  mov     rax, [rbx]
0x180039784  mov     rcx, [rcx+18h]
0x180039788  mov     [rsp+88h+var_40], r9d
0x18003978d  mov     r9, cs:g_RecorderLog
0x180039794  mov     [rsp+88h+var_48], rax
0x180039799  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x1800397a0  mov     [rsp+88h+var_50], rax
0x1800397a5  mov     [rsp+88h+var_58], 34h ; '4'
0x1800397ac  mov     [rsp+88h+var_60], 3
0x1800397b4  mov     [rsp+88h+var_68], 2
0x1800397b9  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1800397be  lea     rdx, aInsufficientRe_0; "Insufficient resources to make top leve"...
0x1800397c5  jmp     loc_18003A19D
0x1800397ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800397d1  lea     rax, WPP_GLOBAL_Control
0x1800397d8  cmp     rcx, rax
0x1800397db  jz      short loc_1800397EE
0x1800397dd  mov     eax, [rcx+2Ch]
0x1800397e0  test    al, 4
0x1800397e2  jz      short loc_1800397EE
0x1800397e4  cmp     byte ptr [rcx+29h], 2
0x1800397e8  jb      short loc_1800397EE
0x1800397ea  mov     dl, 1
0x1800397ec  jmp     short loc_1800397F0
0x1800397ee  xor     dl, dl
0x1800397f0  lea     rax, WPP_RECORDER_INITIALIZED
0x1800397f7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800397fe  setnz   r8b
0x180039802  test    dl, dl
0x180039804  jnz     short loc_18003980B
0x180039806  test    r8b, r8b
0x180039809  jz      short loc_180039848
0x18003980b  mov     rax, [rbx]
0x18003980e  mov     rcx, [rcx+18h]
0x180039812  mov     [rsp+88h+var_40], r9d
0x180039817  mov     r9, cs:g_RecorderLog
0x18003981e  mov     [rsp+88h+var_48], rax
0x180039823  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18003982a  mov     [rsp+88h+var_50], rax
0x18003982f  mov     [rsp+88h+var_58], 37h ; '7'
0x180039836  mov     [rsp+88h+var_60], 3
0x18003983e  mov     [rsp+88h+var_68], 2
0x180039843  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180039848  lea     rdx, aOneByteWasExpe; "One byte was expected in the report des"...
0x18003984f  jmp     loc_18003A19D
0x180039854  sub     eax, 7
0x180039857  jz      loc_180039AA9
0x18003985d  sub     eax, 1
0x180039860  jz      loc_180039A1F
0x180039866  sub     eax, 1
0x180039869  jz      loc_18003997B
0x18003986f  sub     eax, 1
0x180039872  jz      short loc_1800398F1
0x180039874  cmp     eax, 1
0x180039877  jnz     loc_18003A1A5
0x18003987d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039884  lea     rax, WPP_GLOBAL_Control
0x18003988b  cmp     rcx, rax
0x18003988e  jz      short loc_1800398A1
0x180039890  mov     eax, [rcx+2Ch]
0x180039893  test    al, 4
0x180039895  jz      short loc_1800398A1
0x180039897  cmp     byte ptr [rcx+29h], 2
0x18003989b  jb      short loc_1800398A1
0x18003989d  mov     dl, 1
0x18003989f  jmp     short loc_1800398A3
0x1800398a1  xor     dl, dl
0x1800398a3  lea     rax, WPP_RECORDER_INITIALIZED
0x1800398aa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800398b1  setnz   r8b
0x1800398b5  test    dl, dl
0x1800398b7  jnz     short loc_1800398BE
0x1800398b9  test    r8b, r8b
0x1800398bc  jz      short loc_1800398E5
0x1800398be  mov     eax, [rbx+0C4h]
0x1800398c4  mov     rcx, [rcx+18h]
0x1800398c8  mov     [rsp+88h+var_38], eax
0x1800398cc  mov     rax, [rbx]
0x1800398cf  mov     [rsp+88h+var_40], r9d
0x1800398d4  mov     [rsp+88h+var_48], rax
0x1800398d9  mov     [rsp+88h+var_58], 3Ch ; '<'
0x1800398e0  call    WPP_RECORDER_AND_TRACE_SF_qDd
0x1800398e5  lea     rdx, aATopLevelColle; "A top level collection was declared wit"...
0x1800398ec  jmp     loc_180039A0B
0x1800398f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398f8  lea     rax, WPP_GLOBAL_Control
0x1800398ff  cmp     rcx, rax
0x180039902  jz      short loc_180039915
0x180039904  mov     eax, [rcx+2Ch]
0x180039907  test    al, 4
0x180039909  jz      short loc_180039915
0x18003990b  cmp     byte ptr [rcx+29h], 2
0x18003990f  jb      short loc_180039915
0x180039911  mov     dl, 1
0x180039913  jmp     short loc_180039917
0x180039915  xor     dl, dl
0x180039917  lea     rax, WPP_RECORDER_INITIALIZED
0x18003991e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180039925  setnz   r8b
0x180039929  test    dl, dl
0x18003992b  jnz     short loc_180039932
0x18003992d  test    r8b, r8b
0x180039930  jz      short loc_18003996F
0x180039932  mov     rax, [rbx]
0x180039935  mov     rcx, [rcx+18h]
0x180039939  mov     [rsp+88h+var_40], r9d
0x18003993e  mov     r9, cs:g_RecorderLog
0x180039945  mov     [rsp+88h+var_48], rax
0x18003994a  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x180039951  mov     [rsp+88h+var_50], rax
0x180039956  mov     [rsp+88h+var_58], 3Bh ; ';'
0x18003995d  mov     [rsp+88h+var_60], 3
0x180039965  mov     [rsp+88h+var_68], 2
0x18003996a  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003996f  lea     rdx, aANonConstantMa; "A non constant main item was declared w"...
0x180039976  jmp     loc_18003A19D
0x18003997b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039982  lea     rax, WPP_GLOBAL_Control
0x180039989  cmp     rcx, rax
0x18003998c  jz      short loc_18003999F
0x18003998e  mov     eax, [rcx+2Ch]
0x180039991  test    al, 4
0x180039993  jz      short loc_18003999F
0x180039995  cmp     byte ptr [rcx+29h], 2
0x180039999  jb      short loc_18003999F
0x18003999b  mov     dl, 1
0x18003999d  jmp     short loc_1800399A1
0x18003999f  xor     dl, dl
0x1800399a1  lea     rax, WPP_RECORDER_INITIALIZED
0x1800399a8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800399af  setnz   r8b
0x1800399b3  test    dl, dl
0x1800399b5  jnz     short loc_1800399BC
0x1800399b7  test    r8b, r8b
0x1800399ba  jz      short loc_180039A04
0x1800399bc  mov     eax, [rbx+0D4h]
0x1800399c2  mov     rcx, [rcx+18h]
0x1800399c6  mov     [rsp+88h+var_18], eax
0x1800399ca  mov     eax, [rbx+0D0h]
0x1800399d0  mov     [rsp+88h+var_20], eax
0x1800399d4  mov     eax, [rbx+0CCh]
0x1800399da  mov     [rsp+88h+var_28], eax
0x1800399de  mov     eax, [rbx+0C8h]
0x1800399e4  mov     [rsp+88h+var_30], eax
0x1800399e8  mov     eax, [rbx+0C4h]
0x1800399ee  mov     [rsp+88h+var_38], eax
0x1800399f2  mov     rax, [rbx]
0x1800399f5  mov     [rsp+88h+var_40], r9d
0x1800399fa  mov     [rsp+88h+var_48], rax
0x1800399ff  call    WPP_RECORDER_AND_TRACE_SF_qDddddd
0x180039a04  lea     rdx, aReportWasNotBy; "Report was not byte aligned. Collection"...
0x180039a0b  mov     r8d, [rbx+0C4h]
0x180039a12  mov     rcx, rbx
0x180039a15  call    TraceLoggingParserErrorWithParam
0x180039a1a  jmp     loc_18003A1A5
0x180039a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a26  lea     rax, WPP_GLOBAL_Control
0x180039a2d  cmp     rcx, rax
0x180039a30  jz      short loc_180039A43
0x180039a32  mov     eax, [rcx+2Ch]
0x180039a35  test    al, 4
0x180039a37  jz      short loc_180039A43
0x180039a39  cmp     byte ptr [rcx+29h], 2
0x180039a3d  jb      short loc_180039A43
0x180039a3f  mov     dl, 1
0x180039a41  jmp     short loc_180039A45
0x180039a43  xor     dl, dl
0x180039a45  lea     rax, WPP_RECORDER_INITIALIZED
0x180039a4c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180039a53  setnz   r8b
0x180039a57  test    dl, dl
0x180039a59  jnz     short loc_180039A60
0x180039a5b  test    r8b, r8b
0x180039a5e  jz      short loc_180039A9D
0x180039a60  mov     rax, [rbx]
0x180039a63  mov     rcx, [rcx+18h]
0x180039a67  mov     [rsp+88h+var_40], r9d
0x180039a6c  mov     r9, cs:g_RecorderLog
0x180039a73  mov     [rsp+88h+var_48], rax
0x180039a78  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x180039a7f  mov     [rsp+88h+var_50], rax
0x180039a84  mov     [rsp+88h+var_58], 39h ; '9'
0x180039a8b  mov     [rsp+88h+var_60], 3
0x180039a93  mov     [rsp+88h+var_68], 2
0x180039a98  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180039a9d  lea     rdx, aFourBytesWereE; "Four bytes were expected in the report "...
0x180039aa4  jmp     loc_18003A19D
0x180039aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ab0  lea     rax, WPP_GLOBAL_Control
0x180039ab7  cmp     rcx, rax
0x180039aba  jz      short loc_180039ACD
0x180039abc  mov     eax, [rcx+2Ch]
0x180039abf  test    al, 4
0x180039ac1  jz      short loc_180039ACD
0x180039ac3  cmp     byte ptr [rcx+29h], 2
0x180039ac7  jb      short loc_180039ACD
  ... truncated ...
```
