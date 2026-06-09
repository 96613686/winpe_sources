# CNfsEtwEvents::StartTracing(CNfsEventPropertyHandler *)

- ea: `0x180016acc`
- end: `0x180016bac`
- name: `?StartTracing@CNfsEtwEvents@@QEAAKPEAVCNfsEventPropertyHandler@@@Z`
- size: `224`
- prototype: `unsigned int __fastcall(CNfsEtwEvents *__hidden this, struct CNfsEventPropertyHandler *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000db50`

## callees

- `0x180016acc`
- `0x180016c48`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180016b57`
- `KERNEL32!GetLastError` at `0x180016b57`
- `ADVAPI32!OpenTraceW` at `0x180016b47`
- `ADVAPI32!OpenTraceW` at `0x180016b47`
- `ADVAPI32!ProcessTrace` at `0x180016b71`
- `ADVAPI32!ProcessTrace` at `0x180016b71`

## pseudocode

```c
__int64 __fastcall CNfsEtwEvents::StartTracing(CNfsEtwEvents *this, struct CNfsEventPropertyHandler *a2)
{
  TRACEHANDLE v4; // rax
  DWORD LastError; // ebx
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+20h] [rbp-1D8h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileMode = 268435712;
  Logfile.LoggerName = (LPWSTR)L"{4CCCC0BF-B617-47A4-A85B-52E12FCD0693}";
  Logfile.Context = a2;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)xdr_void;
  Logfile.EventCallback = (PEVENT_CALLBACK)CNfsEtwEvents::ProcessEvent;
  v4 = OpenTraceW(&Logfile);
  *((_QWORD *)this + 3) = v4;
  if ( v4 == -1 && (LastError = GetLastError()) != 0
    || (LastError = ProcessTrace((PTRACEHANDLE)this + 3, 1u, 0, 0)) != 0 )
  {
    CNfsEtwEvents::StopTracing(this);
  }
  return LastError;
}

```

## disassembly

```asm
0x180016acc  mov     [rsp+arg_10], rbx
0x180016ad1  mov     [rsp+arg_18], rsi
0x180016ad6  push    rdi
0x180016ad7  sub     rsp, 1F0h
0x180016ade  mov     rax, cs:__security_cookie
0x180016ae5  xor     rax, rsp
0x180016ae8  mov     [rsp+1F8h+var_18], rax
0x180016af0  mov     rbx, rdx
0x180016af3  mov     rdi, rcx
0x180016af6  xor     edx, edx; Val
0x180016af8  lea     rcx, [rsp+1F8h+Logfile]; void *
0x180016afd  mov     r8d, 1C0h; Size
0x180016b03  call    memset_0
0x180016b08  lea     rax, InstanceName; "{4CCCC0BF-B617-47A4-A85B-52E12FCD0693}"
0x180016b0f  mov     dword ptr [rsp+1F8h+Logfile.1Ch], 10000100h
0x180016b17  mov     [rsp+1F8h+Logfile.LoggerName], rax
0x180016b1c  lea     rcx, [rsp+1F8h+Logfile]; Logfile
0x180016b21  lea     rax, xdr_void
0x180016b28  mov     [rsp+1F8h+Logfile.Context], rbx
0x180016b30  mov     [rsp+1F8h+Logfile.BufferCallback], rax
0x180016b38  lea     rax, ?ProcessEvent@CNfsEtwEvents@@SAXPEAU_EVENT_RECORD@@@Z; CNfsEtwEvents::ProcessEvent(_EVENT_RECORD *)
0x180016b3f  mov     qword ptr [rsp+1F8h+Logfile.1A8h], rax
0x180016b47  call    cs:__imp_OpenTraceW
0x180016b4d  mov     [rdi+18h], rax
0x180016b51  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016b55  jnz     short loc_180016B63
0x180016b57  call    cs:__imp_GetLastError
0x180016b5d  mov     ebx, eax
0x180016b5f  test    eax, eax
0x180016b61  jnz     short loc_180016B7D
0x180016b63  xor     r9d, r9d; EndTime
0x180016b66  lea     rcx, [rdi+18h]; HandleArray
0x180016b6a  xor     r8d, r8d; StartTime
0x180016b6d  lea     edx, [r9+1]; HandleCount
0x180016b71  call    cs:__imp_ProcessTrace
0x180016b77  mov     ebx, eax
0x180016b79  test    eax, eax
0x180016b7b  jz      short loc_180016B85
0x180016b7d  mov     rcx, rdi; this
0x180016b80  call    ?StopTracing@CNfsEtwEvents@@QEAAXXZ; CNfsEtwEvents::StopTracing(void)
0x180016b85  mov     eax, ebx
0x180016b87  mov     rcx, [rsp+1F8h+var_18]
0x180016b8f  xor     rcx, rsp; StackCookie
0x180016b92  call    __security_check_cookie
0x180016b97  lea     r11, [rsp+1F8h+var_8]
0x180016b9f  mov     rbx, [r11+20h]
0x180016ba3  mov     rsi, [r11+28h]
0x180016ba7  mov     rsp, r11
0x180016baa  pop     rdi
0x180016bab  retn
```
