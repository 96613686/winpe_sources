# WEBSOCKET_IO_MANAGER::InitiateNextQueuedSend(void)

- ea: `0x1800050cc`
- end: `0x1800051b1`
- name: `?InitiateNextQueuedSend@WEBSOCKET_IO_MANAGER@@AEAAJXZ`
- size: `229`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800052d0`
- `0x180005568`

## callees

- `0x180004040`
- `0x1800050cc`
- `0x180005568`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050e3`
- `iisutil!PuDbgPrint` at `0x18000517c`
- `iisutil!PuDbgPrint` at `0x18000517c`

## string_xrefs

- `0x180005163`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wsio.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_IO_MANAGER::InitiateNextQueuedSend(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  unsigned int v3; // esi
  struct _RTL_CRITICAL_SECTION *DebugInfo; // rbx
  ULONG_PTR *v5; // rbx
  ULONG_PTR v6; // rdi
  int v7; // eax

  v1 = this + 1;
  v3 = 0;
  EnterCriticalSection(this + 1);
  DebugInfo = (struct _RTL_CRITICAL_SECTION *)v1[1].DebugInfo;
  LeaveCriticalSection(v1);
  if ( DebugInfo != &v1[1] )
  {
    v5 = QUEUE::Dequeue(v1);
    v6 = v5[6];
    v7 = WEBSOCKET_IO_MANAGER::Send(
           (WEBSOCKET_IO_MANAGER *)this,
           1,
           (union _WEB_SOCKET_BUFFER *)v5[4],
           *((_DWORD *)v5 + 10),
           0,
           *(void (**)(void *, int, unsigned int))(v6 + 8),
           *(void **)(v6 + 16),
           0);
    v3 = v7;
    if ( v7 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wsio.cxx",
          524,
          "WEBSOCKET_IO_MANAGER::InitiateNextQueuedSend",
          "ERROR = %08x\n",
          v7);
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v6 + 8))(*(_QWORD *)(v6 + 16), v3, 0);
    }
    (*(void (__fastcall **)(ULONG_PTR *, __int64))*v5)(v5, 1);
  }
  return v3;
}

```

## disassembly

```asm
0x1800050cc  push    rbx
0x1800050ce  push    rbp
0x1800050cf  push    rsi
0x1800050d0  push    rdi
0x1800050d1  push    r14
0x1800050d3  sub     rsp, 40h
0x1800050d7  lea     rbp, [rcx+28h]
0x1800050db  mov     r14, rcx
0x1800050de  mov     rcx, rbp; lpCriticalSection
0x1800050e1  xor     esi, esi
0x1800050e3  call    cs:__imp_EnterCriticalSection
0x1800050e9  lea     rdi, [rbp+28h]
0x1800050ed  mov     rcx, rbp; lpCriticalSection
0x1800050f0  mov     rbx, [rdi]
0x1800050f3  call    cs:__imp_LeaveCriticalSection
0x1800050f9  cmp     rbx, rdi
0x1800050fc  jz      loc_1800051A4
0x180005102  mov     rcx, rbp; lpCriticalSection
0x180005105  call    ?Dequeue@QUEUE@@QEAAPEAVQUEUE_RECORD@@XZ; QUEUE::Dequeue(void)
0x18000510a  mov     rbx, rax
0x18000510d  mov     [rsp+68h+var_30], rsi; int *
0x180005112  lea     ebp, [rsi+1]
0x180005115  mov     rcx, r14; this
0x180005118  mov     edx, ebp; int
0x18000511a  mov     rdi, [rax+30h]
0x18000511e  mov     r9d, [rbx+28h]; unsigned int
0x180005122  mov     r8, [rbx+20h]; union _WEB_SOCKET_BUFFER *
0x180005126  mov     rax, [rdi+10h]
0x18000512a  mov     [rsp+68h+var_38], rax; void *
0x18000512f  mov     rax, [rdi+8]
0x180005133  mov     [rsp+68h+var_40], rax; void (*)(void *, int, unsigned int)
0x180005138  mov     [rsp+68h+var_48], rsi; unsigned int *
0x18000513d  call    ?Send@WEBSOCKET_IO_MANAGER@@QEAAJHPEAT_WEB_SOCKET_BUFFER@@KPEAKP6AXPEAXJK@Z2PEAH@Z; WEBSOCKET_IO_MANAGER::Send(int,_WEB_SOCKET_BUFFER *,ulong,ulong *,void (*)(void *,long,ulong),void *,int *)
0x180005142  mov     esi, eax
0x180005144  test    eax, eax
0x180005146  jns     short loc_180005194
0x180005148  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000514f  jz      short loc_180005182
0x180005151  mov     rcx, cs:g_pDebug
0x180005158  lea     r9, aWebsocketIoMan_1; "WEBSOCKET_IO_MANAGER::InitiateNextQueue"...
0x18000515f  mov     dword ptr [rsp+68h+var_40], eax
0x180005163  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000516a  lea     rax, aError08x; "ERROR = %08x\n"
0x180005171  mov     r8d, 20Ch
0x180005177  mov     [rsp+68h+var_48], rax
0x18000517c  call    cs:__imp_PuDbgPrint
0x180005182  mov     rcx, [rdi+10h]
0x180005186  xor     r8d, r8d
0x180005189  mov     rax, [rdi+8]
0x18000518d  mov     edx, esi
0x18000518f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005194  mov     rax, [rbx]
0x180005197  mov     edx, ebp
0x180005199  mov     rcx, rbx
0x18000519c  mov     rax, [rax]
0x18000519f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a4  mov     eax, esi
0x1800051a6  add     rsp, 40h
0x1800051aa  pop     r14
0x1800051ac  pop     rdi
0x1800051ad  pop     rsi
0x1800051ae  pop     rbp
0x1800051af  pop     rbx
0x1800051b0  retn
```
