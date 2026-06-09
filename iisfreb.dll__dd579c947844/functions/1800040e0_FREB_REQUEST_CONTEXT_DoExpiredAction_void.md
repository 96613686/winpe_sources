# FREB_REQUEST_CONTEXT::DoExpiredAction(void)

- ea: `0x1800040e0`
- end: `0x180004160`
- name: `?DoExpiredAction@FREB_REQUEST_CONTEXT@@UEAAXXZ`
- size: `128`
- prototype: `void __fastcall(FREB_REQUEST_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800040e0`
- `0x180005588`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180004126`
- `iisutil!PuDbgPrint` at `0x180004126`

## string_xrefs

- `0x18000411f`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_request_context.cxx`

## pseudocode

```c
void __fastcall FREB_REQUEST_CONTEXT::DoExpiredAction(FREB_REQUEST_CONTEXT *this)
{
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_request_context.cxx",
      1771,
      "FREB_REQUEST_CONTEXT::DoExpiredAction",
      "Freb: timeout limit reached. All events buffered so far will be written to a log file\n");
  *((_DWORD *)this + 49) = 1;
  *((_DWORD *)this + 52) = 1;
  if ( !*(_DWORD *)(*((_QWORD *)this + 9) + 200LL) )
    FREB_REQUEST_CONTEXT::WriteTraceEventsToFile((FREB_REQUEST_CONTEXT *)((char *)this - 8), L"TIME_TAKEN");
}

```

## disassembly

```asm
0x1800040e0  push    rbx
0x1800040e2  sub     rsp, 30h
0x1800040e6  mov     eax, cs:g_dwDebugFlags
0x1800040ec  mov     rbx, rcx
0x1800040ef  test    al, 3
0x1800040f1  setnz   dl
0x1800040f4  bt      eax, 1Fh
0x1800040f8  setb    al
0x1800040fb  test    al, dl
0x1800040fd  jz      short loc_18000412C
0x1800040ff  mov     rcx, cs:g_pDebug
0x180004106  lea     rax, aFrebTimeoutLim; "Freb: timeout limit reached. All events"...
0x18000410d  lea     r9, aFrebRequestCon_0; "FREB_REQUEST_CONTEXT::DoExpiredAction"
0x180004114  mov     [rsp+38h+var_18], rax
0x180004119  mov     r8d, 6EBh
0x18000411f  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004126  call    cs:__imp_PuDbgPrint
0x18000412c  mov     eax, 1
0x180004131  lea     rcx, [rbx-8]; this
0x180004135  mov     [rcx+0CCh], eax
0x18000413b  mov     [rcx+0D8h], eax
0x180004141  mov     rax, [rbx+48h]
0x180004145  cmp     dword ptr [rax+0C8h], 0
0x18000414c  jnz     short loc_18000415A
0x18000414e  lea     rdx, aTimeTaken; "TIME_TAKEN"
0x180004155  call    ?WriteTraceEventsToFile@FREB_REQUEST_CONTEXT@@QEAAJPEBG@Z; FREB_REQUEST_CONTEXT::WriteTraceEventsToFile(ushort const *)
0x18000415a  add     rsp, 30h
0x18000415e  pop     rbx
0x18000415f  retn
```
