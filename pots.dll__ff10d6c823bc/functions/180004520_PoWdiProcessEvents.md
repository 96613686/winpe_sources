# PoWdiProcessEvents

- ea: `0x180004520`
- end: `0x1800045ee`
- name: `PoWdiProcessEvents`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c40`

## callees

- `0x180004520`
- `0x180004902`
- `0x180004930`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180004589`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180004589`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x1800045c3`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x1800045c3`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x1800045aa`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x1800045aa`

## pseudocode

```c
_BOOL8 __fastcall PoWdiProcessEvents(WCHAR *a1, void (__stdcall *a2)(PEVENT_TRACE pEvent), void *a3)
{
  BOOL v6; // ebp
  ULONG64 HandleArray[2]; // [rsp+20h] [rbp-1F8h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-1E8h] BYREF

  v6 = 0;
  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileMode = 268439552;
  Logfile.LogFileName = a1;
  Logfile.EventCallback = a2;
  Logfile.Context = a3;
  HandleArray[0] = OpenTraceW(&Logfile);
  if ( HandleArray[0] != -1 )
  {
    v6 = ProcessTrace(HandleArray, 1u, 0, 0) == 0;
    if ( HandleArray[0] != -1 )
      CloseTrace(HandleArray[0]);
  }
  return v6;
}

```

## disassembly

```asm
0x180004520  mov     [rsp+arg_18], rbx
0x180004525  push    rbp
0x180004526  push    rsi
0x180004527  push    rdi
0x180004528  sub     rsp, 200h
0x18000452f  mov     rax, cs:__security_cookie
0x180004536  xor     rax, rsp
0x180004539  mov     [rsp+218h+var_28], rax
0x180004541  mov     rsi, r8
0x180004544  mov     [rsp+218h+HandleArray], 0FFFFFFFFFFFFFFFFh
0x18000454d  mov     rdi, rdx
0x180004550  mov     rbx, rcx
0x180004553  xor     edx, edx; Val
0x180004555  lea     rcx, [rsp+218h+Logfile]; void *
0x18000455a  mov     r8d, 1C0h; Size
0x180004560  xor     ebp, ebp
0x180004562  call    memset_0
0x180004567  lea     rcx, [rsp+218h+Logfile]; Logfile
0x18000456c  mov     dword ptr [rsp+218h+Logfile.1Ch], 10001000h
0x180004574  mov     [rsp+218h+Logfile.LogFileName], rbx
0x180004579  mov     qword ptr [rsp+218h+Logfile.1A8h], rdi
0x180004581  mov     [rsp+218h+Logfile.Context], rsi
0x180004589  call    cs:__imp_OpenTraceW
0x18000458f  mov     [rsp+218h+HandleArray], rax
0x180004594  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004598  jz      short loc_1800045C9
0x18000459a  lea     ebx, [rbp+1]
0x18000459d  xor     r9d, r9d; EndTime
0x1800045a0  mov     edx, ebx; HandleCount
0x1800045a2  lea     rcx, [rsp+218h+HandleArray]; HandleArray
0x1800045a7  xor     r8d, r8d; StartTime
0x1800045aa  call    cs:__imp_ProcessTrace
0x1800045b0  test    eax, eax
0x1800045b2  mov     rax, [rsp+218h+HandleArray]
0x1800045b7  cmovz   ebp, ebx
0x1800045ba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800045be  jz      short loc_1800045C9
0x1800045c0  mov     rcx, rax; TraceHandle
0x1800045c3  call    cs:__imp_CloseTrace
0x1800045c9  mov     eax, ebp
0x1800045cb  mov     rcx, [rsp+218h+var_28]
0x1800045d3  xor     rcx, rsp; StackCookie
0x1800045d6  call    __security_check_cookie
0x1800045db  mov     rbx, [rsp+218h+arg_18]
0x1800045e3  add     rsp, 200h
0x1800045ea  pop     rdi
0x1800045eb  pop     rsi
0x1800045ec  pop     rbp
0x1800045ed  retn
```
