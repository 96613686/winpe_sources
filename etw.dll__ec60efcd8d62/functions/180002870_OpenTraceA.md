# OpenTraceA

- ea: `0x180002870`
- end: `0x180002935`
- name: `OpenTraceA`
- size: `197`
- prototype: `TRACEHANDLE __stdcall(PEVENT_TRACE_LOGFILEA Logfile)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002784`
- `0x180002870`
- `0x180007060`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800028e9`
- `ntdll!RtlFreeHeap` at `0x180002906`
- `ntdll!RtlFreeHeap` at `0x1800028e9`
- `ntdll!RtlFreeHeap` at `0x180002906`
- `ntdll!RtlSetLastWin32Error` at `0x18000291f`
- `ntdll!RtlSetLastWin32Error` at `0x18000291f`

## pseudocode

```c
TRACEHANDLE __stdcall OpenTraceA(PEVENT_TRACE_LOGFILEA Logfile)
{
  TRACEHANDLE v1; // rsi
  CHAR *LogFileName; // r15
  LPSTR *p_LoggerName; // r14
  const CHAR *LoggerName; // rbp
  ULONG v6; // edi

  v1 = -1;
  if ( !Logfile )
  {
    v6 = 87;
LABEL_12:
    RtlSetLastWin32Error(v6);
    return v1;
  }
  LogFileName = Logfile->LogFileName;
  p_LoggerName = &Logfile->LoggerName;
  LoggerName = Logfile->LoggerName;
  Logfile->LogFileName = 0;
  Logfile->LoggerName = 0;
  v6 = AnsiToUnicode(LogFileName);
  if ( !v6 )
  {
    v6 = AnsiToUnicode(LoggerName);
    if ( !v6 )
      v1 = OpenTraceW((PEVENT_TRACE_LOGFILEW)Logfile);
  }
  if ( Logfile->LogFileName )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Logfile->LogFileName);
  if ( *p_LoggerName )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *p_LoggerName);
  Logfile->LogFileName = LogFileName;
  *p_LoggerName = (LPSTR)LoggerName;
  if ( v6 )
    goto LABEL_12;
  return v1;
}

```

## disassembly

```asm
0x180002870  push    rbx
0x180002872  push    rbp
0x180002873  push    rsi
0x180002874  push    rdi
0x180002875  push    r14
0x180002877  push    r15
0x180002879  sub     rsp, 28h
0x18000287d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002881  mov     rbx, rcx
0x180002884  test    rcx, rcx
0x180002887  jz      loc_180002918
0x18000288d  mov     r15, [rcx]
0x180002890  lea     r14, [rcx+8]
0x180002894  mov     rbp, [r14]
0x180002897  mov     rdx, rcx
0x18000289a  mov     qword ptr [rcx], 0
0x1800028a1  mov     rcx, r15; lpMultiByteStr
0x1800028a4  mov     qword ptr [r14], 0
0x1800028ab  call    AnsiToUnicode
0x1800028b0  mov     edi, eax
0x1800028b2  test    eax, eax
0x1800028b4  jnz     short loc_1800028D2
0x1800028b6  mov     rdx, r14
0x1800028b9  mov     rcx, rbp; lpMultiByteStr
0x1800028bc  call    AnsiToUnicode
0x1800028c1  mov     edi, eax
0x1800028c3  test    eax, eax
0x1800028c5  jnz     short loc_1800028D2
0x1800028c7  mov     rcx, rbx; Logfile
0x1800028ca  call    OpenTraceW
0x1800028cf  mov     rsi, rax
0x1800028d2  mov     r8, [rbx]; P
0x1800028d5  test    r8, r8
0x1800028d8  jz      short loc_1800028EF
0x1800028da  mov     rcx, gs:60h
0x1800028e3  xor     edx, edx; Flags
0x1800028e5  mov     rcx, [rcx+30h]; HeapHandle
0x1800028e9  call    cs:__imp_RtlFreeHeap
0x1800028ef  mov     r8, [r14]; P
0x1800028f2  test    r8, r8
0x1800028f5  jz      short loc_18000290C
0x1800028f7  mov     rcx, gs:60h
0x180002900  xor     edx, edx; Flags
0x180002902  mov     rcx, [rcx+30h]; HeapHandle
0x180002906  call    cs:__imp_RtlFreeHeap
0x18000290c  mov     [rbx], r15
0x18000290f  mov     [r14], rbp
0x180002912  test    edi, edi
0x180002914  jz      short loc_180002925
0x180002916  jmp     short loc_18000291D
0x180002918  mov     edi, 57h ; 'W'
0x18000291d  mov     ecx, edi; LastError
0x18000291f  call    cs:__imp_RtlSetLastWin32Error
0x180002925  mov     rax, rsi
0x180002928  add     rsp, 28h
0x18000292c  pop     r15
0x18000292e  pop     r14
0x180002930  pop     rdi
0x180002931  pop     rsi
0x180002932  pop     rbp
0x180002933  pop     rbx
0x180002934  retn
```
