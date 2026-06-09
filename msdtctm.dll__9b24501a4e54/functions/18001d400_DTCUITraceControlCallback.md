# DTCUITraceControlCallback

- ea: `0x18001d400`
- end: `0x18001d606`
- name: `DTCUITraceControlCallback`
- size: `518`
- prototype: `ULONG __stdcall(WMIDPREQUESTCODE RequestCode, PVOID RequestContext, ULONG *BufferSize, PVOID Buffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800063b0`
- `0x18001d400`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d4ff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d4ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d509`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableFlags` at `0x18001d4e8`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableFlags` at `0x18001d4e8`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceLoggerHandle` at `0x18001d4c9`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceLoggerHandle` at `0x18001d4c9`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableLevel` at `0x18001d4dc`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableLevel` at `0x18001d4dc`

## string_xrefs

- `0x18001d43d`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x18001d46c`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x18001d53a`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x18001d56d`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x18001d5d3`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`

## pseudocode

```c
__int64 __fastcall DTCUITraceControlCallback(
        WMIDPREQUESTCODE RequestCode,
        char *RequestContext,
        ULONG *BufferSize,
        PVOID Buffer)
{
  unsigned int v4; // ebx
  int v9; // edi
  TRACEHANDLE TraceLoggerHandle; // rax
  TRACEHANDLE v11; // rdi
  int TraceEnableLevel; // ebp
  ULONG TraceEnableFlags; // eax
  void *v14; // rcx
  ULONG v15; // r15d
  signed int LastError; // eax

  v4 = 0;
  TraceStringInline(
    14,
    6,
    L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
    414,
    L"DTCUITraceControlCallback",
    0,
    L"In");
  if ( RequestContext )
  {
    (**((void (__fastcall ***)(char *))RequestContext + 2))(RequestContext + 16);
    v9 = RequestCode - 4;
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        *((_QWORD *)RequestContext + 202) = 0;
        *((_DWORD *)RequestContext + 2) = 5;
      }
      else
      {
        v4 = 87;
      }
    }
    else
    {
      TraceLoggerHandle = GetTraceLoggerHandle(Buffer);
      *((_QWORD *)RequestContext + 202) = TraceLoggerHandle;
      v11 = TraceLoggerHandle;
      TraceEnableLevel = GetTraceEnableLevel(TraceLoggerHandle);
      TraceEnableFlags = GetTraceEnableFlags(v11);
      v14 = (void *)*((_QWORD *)RequestContext + 204);
      v15 = TraceEnableFlags;
      *((_DWORD *)RequestContext + 2) = 3;
      if ( !SetEvent(v14) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        TraceStringInline(
          14,
          1,
          L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
          444,
          L"DTCUITraceControlCallback",
          v4,
          L"SetEvent for m_hSessionEvent Failed");
      }
      TraceStringInline(
        14,
        3,
        L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
        447,
        L"DTCUITraceControlCallback",
        0,
        L"WMI_ENABLE_EVENTS Flags %x %d %08x",
        v15,
        TraceEnableLevel,
        v11);
    }
    *BufferSize = 0;
    (*(void (__fastcall **)(char *))(*((_QWORD *)RequestContext + 2) + 8LL))(RequestContext + 16);
  }
  else
  {
    TraceStringInline(
      14,
      1,
      L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
      418,
      L"DTCUITraceControlCallback",
      0,
      L"DTCUITraceControlCallback : pContext == NULL");
  }
  TraceStringInline(
    14,
    6,
    L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
    477,
    L"DTCUITraceControlCallback",
    0,
    L"Out");
  return v4;
}

```

## disassembly

```asm
0x18001d400  push    rbx
0x18001d402  push    rbp
0x18001d403  push    rsi
0x18001d404  push    rdi
0x18001d405  push    r12
0x18001d407  push    r14
0x18001d409  push    r15
0x18001d40b  sub     rsp, 50h
0x18001d40f  xor     ebx, ebx
0x18001d411  lea     rax, aIn_0; "In"
0x18001d418  mov     [rsp+88h+var_58], rax
0x18001d41d  lea     r14, aDtcuitracecont; "DTCUITraceControlCallback"
0x18001d424  mov     rbp, r9
0x18001d427  mov     [rsp+88h+var_60], rbx
0x18001d42c  mov     r12, r8
0x18001d42f  mov     [rsp+88h+var_68], r14
0x18001d434  mov     rsi, rdx
0x18001d437  lea     r15d, [rbx+0Eh]
0x18001d43b  mov     edi, ecx
0x18001d43d  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x18001d444  mov     ecx, r15d
0x18001d447  lea     edx, [rbx+6]
0x18001d44a  mov     r9d, 19Eh
0x18001d450  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001d455  test    rsi, rsi
0x18001d458  jnz     short loc_18001D48D
0x18001d45a  lea     rax, aDtcuitracecont_0; "DTCUITraceControlCallback : pContext =="...
0x18001d461  mov     r9d, 1A2h
0x18001d467  mov     [rsp+88h+var_58], rax
0x18001d46c  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x18001d473  mov     [rsp+88h+var_60], rbx
0x18001d478  lea     edx, [rbx+1]
0x18001d47b  mov     ecx, r15d
0x18001d47e  mov     [rsp+88h+var_68], r14
0x18001d483  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001d488  jmp     loc_18001D5C1
0x18001d48d  lea     r14, [rsi+10h]
0x18001d491  mov     rax, [r14]
0x18001d494  mov     rcx, r14
0x18001d497  mov     rax, [rax]
0x18001d49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d49f  sub     edi, 4
0x18001d4a2  jz      short loc_18001D4C6
0x18001d4a4  cmp     edi, 1
0x18001d4a7  jz      short loc_18001D4B3
0x18001d4a9  mov     ebx, 57h ; 'W'
0x18001d4ae  jmp     loc_18001D5A3
0x18001d4b3  mov     [rsi+650h], rbx
0x18001d4ba  mov     dword ptr [rsi+8], 5
0x18001d4c1  jmp     loc_18001D5A3
0x18001d4c6  mov     rcx, rbp; Buffer
0x18001d4c9  call    cs:__imp_GetTraceLoggerHandle
0x18001d4cf  mov     rcx, rax; TraceHandle
0x18001d4d2  mov     [rsi+650h], rax
0x18001d4d9  mov     rdi, rax
0x18001d4dc  call    cs:__imp_GetTraceEnableLevel
0x18001d4e2  mov     rcx, rdi; TraceHandle
0x18001d4e5  movzx   ebp, al
0x18001d4e8  call    cs:__imp_GetTraceEnableFlags
0x18001d4ee  mov     rcx, [rsi+660h]; hEvent
0x18001d4f5  mov     r15d, eax
0x18001d4f8  mov     dword ptr [rsi+8], 3
0x18001d4ff  call    cs:__imp_SetEvent
0x18001d505  test    eax, eax
0x18001d507  jnz     short loc_18001D556
0x18001d509  call    cs:__imp_GetLastError
0x18001d50f  mov     ebx, eax
0x18001d511  test    eax, eax
0x18001d513  jle     short loc_18001D51E
0x18001d515  movzx   ebx, ax
0x18001d518  or      ebx, 80070000h
0x18001d51e  mov     edx, 1
0x18001d523  lea     rax, aSeteventForMHs; "SetEvent for m_hSessionEvent Failed"
0x18001d52a  mov     [rsp+88h+var_58], rax
0x18001d52f  lea     rsi, aDtcuitracecont; "DTCUITraceControlCallback"
0x18001d536  mov     dword ptr [rsp+88h+var_60], ebx
0x18001d53a  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x18001d541  mov     r9d, 1BCh
0x18001d547  mov     [rsp+88h+var_68], rsi
0x18001d54c  lea     ecx, [rdx+0Dh]
0x18001d54f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001d554  jmp     short loc_18001D55D
0x18001d556  lea     rsi, aDtcuitracecont; "DTCUITraceControlCallback"
0x18001d55d  mov     [rsp+88h+var_40], rdi
0x18001d562  lea     rax, aWmiEnableEvent_0; "WMI_ENABLE_EVENTS Flags %x %d %08x"
0x18001d569  mov     [rsp+88h+var_48], ebp
0x18001d56d  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x18001d574  mov     [rsp+88h+var_50], r15d
0x18001d579  mov     edx, 3
0x18001d57e  mov     [rsp+88h+var_58], rax
0x18001d583  mov     r9d, 1BFh
0x18001d589  mov     [rsp+88h+var_60], 0
0x18001d592  mov     [rsp+88h+var_68], rsi
0x18001d597  lea     r15d, [rdx+0Bh]
0x18001d59b  mov     ecx, r15d
0x18001d59e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001d5a3  mov     dword ptr [r12], 0
0x18001d5ab  mov     rax, [r14]
0x18001d5ae  mov     rcx, r14
0x18001d5b1  mov     rax, [rax+8]
0x18001d5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5ba  lea     r14, aDtcuitracecont; "DTCUITraceControlCallback"
0x18001d5c1  lea     rax, aOut; "Out"
0x18001d5c8  mov     r9d, 1DDh
0x18001d5ce  mov     [rsp+88h+var_58], rax
0x18001d5d3  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x18001d5da  mov     [rsp+88h+var_60], 0
0x18001d5e3  mov     edx, 6
0x18001d5e8  mov     ecx, r15d
0x18001d5eb  mov     [rsp+88h+var_68], r14
0x18001d5f0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001d5f5  mov     eax, ebx
0x18001d5f7  add     rsp, 50h
0x18001d5fb  pop     r15
0x18001d5fd  pop     r14
0x18001d5ff  pop     r12
0x18001d601  pop     rdi
0x18001d602  pop     rsi
0x18001d603  pop     rbp
0x18001d604  pop     rbx
0x18001d605  retn
```
