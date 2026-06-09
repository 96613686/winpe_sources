# ControlEventLogParser::InitializeAnalysis(ushort const *)

- ea: `0x1800590f8`
- end: `0x180059192`
- name: `?InitializeAnalysis@ControlEventLogParser@@AEAAKPEBG@Z`
- size: `154`
- prototype: `unsigned int __fastcall(ControlEventLogParser *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18005956c`

## callees

- `0x18004ca90`
- `0x18004d8fc`
- `0x1800590f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059167`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180059158`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180059158`

## pseudocode

```c
DWORD __fastcall ControlEventLogParser::InitializeAnalysis(ControlEventLogParser *this, WCHAR *a2)
{
  TRACEHANDLE v4; // rax
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+20h] [rbp-1D8h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileName = a2;
  Logfile.EventCallback = (PEVENT_CALLBACK)ControlEventLogParser::DispatchEventStatic;
  Logfile.LogFileMode = 0x10000000;
  Logfile.Context = this;
  v4 = OpenTraceW(&Logfile);
  *((_QWORD *)this + 1) = v4;
  if ( v4 )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800590f8  mov     [rsp+arg_10], rbx
0x1800590fd  push    rdi
0x1800590fe  sub     rsp, 1F0h
0x180059105  mov     rax, cs:__security_cookie
0x18005910c  xor     rax, rsp
0x18005910f  mov     [rsp+1F8h+var_18], rax
0x180059117  mov     rbx, rdx
0x18005911a  mov     rdi, rcx
0x18005911d  xor     edx, edx; Val
0x18005911f  lea     rcx, [rsp+1F8h+Logfile]; void *
0x180059124  mov     r8d, 1C0h; Size
0x18005912a  call    memset_0
0x18005912f  lea     rax, ?DispatchEventStatic@ControlEventLogParser@@CAXPEAU_EVENT_RECORD@@@Z; ControlEventLogParser::DispatchEventStatic(_EVENT_RECORD *)
0x180059136  mov     [rsp+1F8h+Logfile.LogFileName], rbx
0x18005913b  lea     rcx, [rsp+1F8h+Logfile]; Logfile
0x180059140  mov     qword ptr [rsp+1F8h+Logfile.1A8h], rax
0x180059148  mov     dword ptr [rsp+1F8h+Logfile.1Ch], 10000000h
0x180059150  mov     [rsp+1F8h+Logfile.Context], rdi
0x180059158  call    cs:__imp_OpenTraceW
0x18005915e  mov     [rdi+8], rax
0x180059162  test    rax, rax
0x180059165  jnz     short loc_18005916F
0x180059167  call    cs:__imp_GetLastError
0x18005916d  jmp     short loc_180059171
0x18005916f  xor     eax, eax
0x180059171  mov     rcx, [rsp+1F8h+var_18]
0x180059179  xor     rcx, rsp; StackCookie
0x18005917c  call    __security_check_cookie
0x180059181  mov     rbx, [rsp+1F8h+arg_10]
0x180059189  add     rsp, 1F0h
0x180059190  pop     rdi
0x180059191  retn
```
