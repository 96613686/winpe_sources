# IPM_INSTANCE::PipeConnected(void)

- ea: `0x18002b880`
- end: `0x18002b951`
- name: `?PipeConnected@IPM_INSTANCE@@UEAAJXZ`
- size: `209`
- prototype: `__int64 __fastcall(IPM_INSTANCE *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008000`
- `0x18002af70`
- `0x18002b880`
- `0x18002b960`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b8b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b8b3`

## string_xrefs

- `0x18002b92a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x18002b931`: `IPM_INSTANCE::PipeConnected WriteMessage failed hr=0x%08X\n`

## pseudocode

```c
__int64 __fastcall IPM_INSTANCE::PipeConnected(MULTI_IPM **this)
{
  DWORD CurrentProcessId; // eax
  HANDLE *v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  v7 = 0;
  MULTI_IPM::PipeConnected(this[1]);
  (*(void (__fastcall **)(_QWORD, MULTI_IPM *))(**((_QWORD **)this[1] + 12) + 8LL))(*((_QWORD *)this[1] + 12), this[2]);
  CurrentProcessId = GetCurrentProcessId();
  v3 = (HANDLE *)this[2];
  v7 = CurrentProcessId | 0x100000000LL;
  v4 = IPM2_MESSAGE_PIPE::WriteMessage(v3, 1, 0, 0, 0, 0, 8u, &v7);
  v5 = v4;
  if ( v4 < 0 && (g_dwDebugFlagsIISUtil & 0xF) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\multi_ipm.cxx",
      0x16Eu,
      "IPM_INSTANCE::PipeConnected",
      "IPM_INSTANCE::PipeConnected WriteMessage failed hr=0x%08X\n",
      v4);
  return v5;
}

```

## disassembly

```asm
0x18002b880  push    rbx
0x18002b882  sub     rsp, 40h
0x18002b886  mov     rbx, rcx
0x18002b889  mov     [rsp+48h+arg_0], 0
0x18002b892  mov     rcx, [rcx+8]; this
0x18002b896  call    ?PipeConnected@MULTI_IPM@@QEAAJXZ; MULTI_IPM::PipeConnected(void)
0x18002b89b  mov     rax, [rbx+8]
0x18002b89f  mov     rdx, [rbx+10h]
0x18002b8a3  mov     rcx, [rax+60h]
0x18002b8a7  mov     rax, [rcx]
0x18002b8aa  mov     rax, [rax+8]
0x18002b8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8b3  call    cs:__imp_GetCurrentProcessId
0x18002b8ba  nop     dword ptr [rax+rax+00h]
0x18002b8bf  mov     eax, eax
0x18002b8c1  mov     rcx, 100000000h
0x18002b8cb  or      rax, rcx
0x18002b8ce  xor     r9d, r9d
0x18002b8d1  mov     rcx, [rbx+10h]
0x18002b8d5  xor     r8d, r8d
0x18002b8d8  mov     [rsp+48h+arg_0], rax
0x18002b8dd  lea     rax, [rsp+48h+arg_0]
0x18002b8e2  mov     [rsp+48h+var_10], rax
0x18002b8e7  mov     [rsp+48h+var_18], 8
0x18002b8ef  lea     edx, [r9+1]
0x18002b8f3  mov     qword ptr [rsp+48h+var_20], 0
0x18002b8fc  mov     dword ptr [rsp+48h+var_28], 0
0x18002b904  call    ?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@HKKPEAXK1@Z; IPM2_MESSAGE_PIPE::WriteMessage(IPM2_OPCODE,int,ulong,ulong,void *,ulong,void *)
0x18002b909  mov     ebx, eax
0x18002b90b  test    eax, eax
0x18002b90d  jns     short loc_18002B948
0x18002b90f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002b916  jz      short loc_18002B948
0x18002b918  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002b91f  lea     r9, aIpmInstancePip_0; "IPM_INSTANCE::PipeConnected"
0x18002b926  mov     dword ptr [rsp+48h+var_20], eax; char
0x18002b92a  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002b931  lea     rax, aIpmInstancePip; "IPM_INSTANCE::PipeConnected WriteMessag"...
0x18002b938  mov     r8d, 16Eh; unsigned int
0x18002b93e  mov     [rsp+48h+var_28], rax; char *
0x18002b943  call    PuDbgPrint
0x18002b948  mov     eax, ebx
0x18002b94a  add     rsp, 40h
0x18002b94e  pop     rbx
0x18002b94f  retn
```
