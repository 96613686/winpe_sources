# SSFSetImmediateFlushFlag(ISAPI_CONTEXT *,int)

- ea: `0x18000a100`
- end: `0x18000a1e3`
- name: `?SSFSetImmediateFlushFlag@@YAJPEAVISAPI_CONTEXT@@H@Z`
- size: `227`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x18000a100`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000a162`
- `iisutil!PuDbgPrint` at `0x18000a1cb`
- `iisutil!PuDbgPrint` at `0x18000a162`
- `iisutil!PuDbgPrint` at `0x18000a1cb`

## string_xrefs

- `0x18000a151`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000a1ad`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFSetImmediateFlushFlag(struct ISAPI_CONTEXT *a1, unsigned int a2)
{
  __int64 v3; // rsi
  int v5; // eax
  unsigned int v6; // ebx

  v3 = *((_QWORD *)a1 + 24);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4461,
      "SSFSetImmediateFlushFlag",
      "\r\n  HSE_REQ_SET_FLUSH_FLAG[%p]: Function Entry\r\n   fFlushImmediate - %d\r\n  <END>\r\n\r\n",
      a1,
      a2);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 208LL))(v3, a2);
  v6 = v5;
  if ( v5 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4476,
      "SSFSetImmediateFlushFlag",
      "\r\n  HSE_REQ_SET_FLUSH_FLAG[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v5);
  return v6;
}

```

## disassembly

```asm
0x18000a100  mov     r11, rsp
0x18000a103  mov     [r11+8], rbx
0x18000a107  mov     [r11+10h], rsi
0x18000a10b  push    rdi
0x18000a10c  sub     rsp, 40h
0x18000a110  mov     eax, cs:g_dwDebugFlags
0x18000a116  mov     ebx, edx
0x18000a118  mov     rsi, [rcx+0C0h]
0x18000a11f  test    al, 3
0x18000a121  mov     rdi, rcx
0x18000a124  setnz   r8b
0x18000a128  bt      eax, 1Ah
0x18000a12c  setb    al
0x18000a12f  test    al, r8b
0x18000a132  jz      short loc_18000A168
0x18000a134  mov     [rsp+48h+var_18], edx
0x18000a138  lea     rax, aHseReqSetFlush_0; "\r\n  HSE_REQ_SET_FLUSH_FLAG[%p]: Funct"...
0x18000a13f  mov     [r11-20h], rcx
0x18000a143  lea     r9, aSsfsetimmediat; "SSFSetImmediateFlushFlag"
0x18000a14a  mov     rcx, cs:g_pDebug
0x18000a151  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a158  mov     r8d, 116Dh
0x18000a15e  mov     [r11-28h], rax
0x18000a162  call    cs:__imp_PuDbgPrint
0x18000a168  mov     rax, [rsi]
0x18000a16b  mov     edx, ebx
0x18000a16d  mov     rcx, rsi
0x18000a170  mov     rax, [rax+0D0h]
0x18000a177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a17c  mov     ebx, eax
0x18000a17e  test    eax, eax
0x18000a180  jns     short loc_18000A1D1
0x18000a182  mov     ecx, cs:g_dwDebugFlags
0x18000a188  test    cl, 3
0x18000a18b  setnz   r8b
0x18000a18f  bt      ecx, 14h
0x18000a193  setb    cl
0x18000a196  test    cl, r8b
0x18000a199  jz      short loc_18000A1D1
0x18000a19b  mov     rcx, cs:g_pDebug
0x18000a1a2  lea     r9, aSsfsetimmediat; "SSFSetImmediateFlushFlag"
0x18000a1a9  mov     [rsp+48h+var_18], eax
0x18000a1ad  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000a1b4  lea     rax, aHseReqSetFlush_1; "\r\n  HSE_REQ_SET_FLUSH_FLAG[%p]: Faile"...
0x18000a1bb  mov     [rsp+48h+var_20], rdi
0x18000a1c0  mov     r8d, 117Ch
0x18000a1c6  mov     [rsp+48h+var_28], rax
0x18000a1cb  call    cs:__imp_PuDbgPrint
0x18000a1d1  mov     rsi, [rsp+48h+arg_8]
0x18000a1d6  mov     eax, ebx
0x18000a1d8  mov     rbx, [rsp+48h+arg_0]
0x18000a1dd  add     rsp, 40h
0x18000a1e1  pop     rdi
0x18000a1e2  retn
```
