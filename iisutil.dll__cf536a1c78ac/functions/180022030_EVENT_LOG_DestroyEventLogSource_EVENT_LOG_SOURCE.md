# EVENT_LOG::DestroyEventLogSource(_EVENT_LOG_SOURCE *)

- ea: `0x180022030`
- end: `0x1800220b5`
- name: `?DestroyEventLogSource@EVENT_LOG@@CAXPEAU_EVENT_LOG_SOURCE@@@Z`
- size: `133`
- prototype: `void __fastcall(struct _EVENT_LOG_SOURCE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800227a0`

## callees

- `0x180008000`
- `0x1800140d8`
- `0x180022030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022066`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180022042`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180022042`

## string_xrefs

- `0x180022084`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`

## pseudocode

```c
void __fastcall EVENT_LOG::DestroyEventLogSource(struct _EVENT_LOG_SOURCE *a1)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)a1 + 1);
  if ( v2 && !DeregisterEventSource(v2) && (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 4) != 0 )
  {
    GetLastError();
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\eventlog.cxx",
      0x1A5u,
      "EVENT_LOG::DestroyEventLogSource",
      "Destruction of EVENT_LOG_SOURCE[%p] failed. error %lu\n",
      (char)a1);
  }
  SMALL_STRU::Reset((struct _EVENT_LOG_SOURCE *)((char *)a1 + 16));
}

```

## disassembly

```asm
0x180022030  push    rbx
0x180022032  sub     rsp, 40h
0x180022036  mov     rbx, rcx
0x180022039  mov     rcx, [rcx+8]; hEventLog
0x18002203d  test    rcx, rcx
0x180022040  jz      short loc_1800220A7
0x180022042  call    cs:__imp_DeregisterEventSource
0x180022049  nop     dword ptr [rax+rax+00h]
0x18002204e  test    eax, eax
0x180022050  jnz     short loc_1800220A7
0x180022052  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180022058  test    al, 3
0x18002205a  setnz   cl
0x18002205d  test    al, 4
0x18002205f  setnz   al
0x180022062  test    al, cl
0x180022064  jz      short loc_1800220A7
0x180022066  call    cs:__imp_GetLastError
0x18002206d  nop     dword ptr [rax+rax+00h]
0x180022072  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180022079  lea     r9, aEventLogDestro; "EVENT_LOG::DestroyEventLogSource"
0x180022080  mov     [rsp+48h+var_18], eax
0x180022084  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002208b  lea     rax, aDestructionOfE; "Destruction of EVENT_LOG_SOURCE[%p] fai"...
0x180022092  mov     qword ptr [rsp+48h+var_20], rbx; char
0x180022097  mov     r8d, 1A5h; unsigned int
0x18002209d  mov     [rsp+48h+var_28], rax; char *
0x1800220a2  call    PuDbgPrint
0x1800220a7  lea     rcx, [rbx+10h]; this
0x1800220ab  add     rsp, 40h
0x1800220af  pop     rbx
0x1800220b0  jmp     ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
```
