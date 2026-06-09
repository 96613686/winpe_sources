# IPM_INSTANCE::PipeConnected(void)

- ea: `0x180029a40`
- end: `0x180029b0a`
- name: `?PipeConnected@IPM_INSTANCE@@UEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(IPM_INSTANCE *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007300`
- `0x180029130`
- `0x180029a40`
- `0x180029b10`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029a73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029a73`

## string_xrefs

- `0x180029ae4`: `servercommon\inetsrv\iis\iisrearc\core\common\util\multi_ipm.cxx`
- `0x180029aeb`: `IPM_INSTANCE::PipeConnected WriteMessage failed hr=0x%08X\n`

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
0x180029a40  push    rbx
0x180029a42  sub     rsp, 40h
0x180029a46  mov     rbx, rcx
0x180029a49  mov     [rsp+48h+arg_0], 0
0x180029a52  mov     rcx, [rcx+8]; this
0x180029a56  call    ?PipeConnected@MULTI_IPM@@QEAAJXZ; MULTI_IPM::PipeConnected(void)
0x180029a5b  mov     rax, [rbx+8]
0x180029a5f  mov     rdx, [rbx+10h]
0x180029a63  mov     rcx, [rax+60h]
0x180029a67  mov     rax, [rcx]
0x180029a6a  mov     rax, [rax+8]
0x180029a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a73  call    cs:__imp_GetCurrentProcessId
0x180029a79  mov     eax, eax
0x180029a7b  mov     rcx, 100000000h
0x180029a85  or      rax, rcx
0x180029a88  xor     r9d, r9d
0x180029a8b  mov     rcx, [rbx+10h]
0x180029a8f  xor     r8d, r8d
0x180029a92  mov     [rsp+48h+arg_0], rax
0x180029a97  lea     rax, [rsp+48h+arg_0]
0x180029a9c  mov     [rsp+48h+var_10], rax
0x180029aa1  mov     [rsp+48h+var_18], 8
0x180029aa9  lea     edx, [r9+1]
0x180029aad  mov     qword ptr [rsp+48h+var_20], 0
0x180029ab6  mov     dword ptr [rsp+48h+var_28], 0
0x180029abe  call    ?WriteMessage@IPM2_MESSAGE_PIPE@@QEAAJW4IPM2_OPCODE@@HKKPEAXK1@Z; IPM2_MESSAGE_PIPE::WriteMessage(IPM2_OPCODE,int,ulong,ulong,void *,ulong,void *)
0x180029ac3  mov     ebx, eax
0x180029ac5  test    eax, eax
0x180029ac7  jns     short loc_180029B02
0x180029ac9  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180029ad0  jz      short loc_180029B02
0x180029ad2  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029ad9  lea     r9, aIpmInstancePip_0; "IPM_INSTANCE::PipeConnected"
0x180029ae0  mov     dword ptr [rsp+48h+var_20], eax; char
0x180029ae4  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029aeb  lea     rax, aIpmInstancePip; "IPM_INSTANCE::PipeConnected WriteMessag"...
0x180029af2  mov     r8d, 16Eh; unsigned int
0x180029af8  mov     [rsp+48h+var_28], rax; char *
0x180029afd  call    PuDbgPrint
0x180029b02  mov     eax, ebx
0x180029b04  add     rsp, 40h
0x180029b08  pop     rbx
0x180029b09  retn
```
