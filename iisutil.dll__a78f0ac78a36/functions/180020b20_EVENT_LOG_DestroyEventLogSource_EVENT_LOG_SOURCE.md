# EVENT_LOG::DestroyEventLogSource(_EVENT_LOG_SOURCE *)

- ea: `0x180020b20`
- end: `0x180020b99`
- name: `?DestroyEventLogSource@EVENT_LOG@@CAXPEAU_EVENT_LOG_SOURCE@@@Z`
- size: `121`
- prototype: `void __fastcall(struct _EVENT_LOG_SOURCE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800211e0`

## callees

- `0x180007300`
- `0x1800136ac`
- `0x180020b20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b50`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180020b32`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180020b32`

## string_xrefs

- `0x180020b68`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`

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
0x180020b20  push    rbx
0x180020b22  sub     rsp, 40h
0x180020b26  mov     rbx, rcx
0x180020b29  mov     rcx, [rcx+8]; hEventLog
0x180020b2d  test    rcx, rcx
0x180020b30  jz      short loc_180020B8B
0x180020b32  call    cs:__imp_DeregisterEventSource
0x180020b38  test    eax, eax
0x180020b3a  jnz     short loc_180020B8B
0x180020b3c  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180020b42  test    al, 3
0x180020b44  setnz   cl
0x180020b47  test    al, 4
0x180020b49  setnz   al
0x180020b4c  test    al, cl
0x180020b4e  jz      short loc_180020B8B
0x180020b50  call    cs:__imp_GetLastError
0x180020b56  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180020b5d  lea     r9, aEventLogDestro; "EVENT_LOG::DestroyEventLogSource"
0x180020b64  mov     [rsp+48h+var_18], eax
0x180020b68  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180020b6f  lea     rax, aDestructionOfE; "Destruction of EVENT_LOG_SOURCE[%p] fai"...
0x180020b76  mov     qword ptr [rsp+48h+var_20], rbx; char
0x180020b7b  mov     r8d, 1A5h; unsigned int
0x180020b81  mov     [rsp+48h+var_28], rax; char *
0x180020b86  call    PuDbgPrint
0x180020b8b  lea     rcx, [rbx+10h]; this
0x180020b8f  add     rsp, 40h
0x180020b93  pop     rbx
0x180020b94  jmp     ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
```
