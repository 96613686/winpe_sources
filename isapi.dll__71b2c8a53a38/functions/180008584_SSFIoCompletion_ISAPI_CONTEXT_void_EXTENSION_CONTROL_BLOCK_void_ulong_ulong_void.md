# SSFIoCompletion(ISAPI_CONTEXT *,void (*)(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong),void *)

- ea: `0x180008584`
- end: `0x180008663`
- name: `?SSFIoCompletion@@YAJPEAVISAPI_CONTEXT@@P6AXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z2@Z`
- size: `223`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, void (*)(struct _EXTENSION_CONTROL_BLOCK *, void *, unsigned int, unsigned int), void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180008584`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800085e8`
- `iisutil!PuDbgPrint` at `0x180008636`
- `iisutil!PuDbgPrint` at `0x1800085e8`
- `iisutil!PuDbgPrint` at `0x180008636`

## string_xrefs

- `0x1800085d0`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000862f`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800085ba`: `\n  HSE_REQ_IO_COMPLETION[%p]: Function Entry\n    Completion Routine: %p\n    Context: %p\n  <END>\n\n`
- `0x1800085c5`: `SSFIoCompletion`
- `0x18000861d`: `SSFIoCompletion`
- `0x180008611`: `\n  HSE_REQ_IO_COMPLETION[%p]: Parameter validation failure\n    Completion Routine: NULL\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFIoCompletion(
        struct ISAPI_CONTEXT *a1,
        void (*a2)(struct _EXTENSION_CONTROL_BLOCK *, void *, unsigned int, unsigned int),
        void *a3)
{
  int v5; // edx
  __int64 result; // rax

  v5 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      1107,
      "SSFIoCompletion",
      "\r\n"
      "  HSE_REQ_IO_COMPLETION[%p]: Function Entry\r\n"
      "    Completion Routine: %p\r\n"
      "    Context: %p\r\n"
      "  <END>\r\n"
      "\r\n",
      a1,
      a2,
      a3);
    v5 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    *((_QWORD *)a1 + 28) = a2;
    result = 0;
    *((_QWORD *)a1 + 29) = a3;
  }
  else
  {
    if ( (v5 & 3) != 0 && (v5 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1123,
        "SSFIoCompletion",
        "\r\n"
        "  HSE_REQ_IO_COMPLETION[%p]: Parameter validation failure\r\n"
        "    Completion Routine: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008584  mov     r11, rsp
0x180008587  mov     [r11+8], rbx
0x18000858b  mov     [r11+10h], rsi
0x18000858f  push    rdi
0x180008590  sub     rsp, 40h
0x180008594  mov     rdi, rdx
0x180008597  mov     rsi, r8
0x18000859a  mov     edx, cs:g_dwDebugFlags
0x1800085a0  mov     rbx, rcx
0x1800085a3  test    dl, 3
0x1800085a6  setnz   r9b
0x1800085aa  bt      edx, 1Ah
0x1800085ae  setb    al
0x1800085b1  test    al, r9b
0x1800085b4  jz      short loc_1800085F4
0x1800085b6  mov     [r11-10h], r8
0x1800085ba  lea     rax, aHseReqIoComple; "\r\n  HSE_REQ_IO_COMPLETION[%p]: Functi"...
0x1800085c1  mov     [r11-18h], rdi
0x1800085c5  lea     r9, aSsfiocompletio; "SSFIoCompletion"
0x1800085cc  mov     [r11-20h], rcx
0x1800085d0  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800085d7  mov     rcx, cs:g_pDebug
0x1800085de  mov     r8d, 453h
0x1800085e4  mov     [r11-28h], rax
0x1800085e8  call    cs:__imp_PuDbgPrint
0x1800085ee  mov     edx, cs:g_dwDebugFlags
0x1800085f4  test    rdi, rdi
0x1800085f7  jnz     short loc_180008643
0x1800085f9  test    dl, 3
0x1800085fc  setnz   cl
0x1800085ff  bt      edx, 14h
0x180008603  setb    al
0x180008606  test    al, cl
0x180008608  jz      short loc_18000863C
0x18000860a  mov     rcx, cs:g_pDebug
0x180008611  lea     rax, aHseReqIoComple_1; "\r\n  HSE_REQ_IO_COMPLETION[%p]: Parame"...
0x180008618  mov     [rsp+48h+var_20], rbx
0x18000861d  lea     r9, aSsfiocompletio; "SSFIoCompletion"
0x180008624  mov     r8d, 463h
0x18000862a  mov     [rsp+48h+var_28], rax
0x18000862f  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008636  call    cs:__imp_PuDbgPrint
0x18000863c  mov     eax, 80070057h
0x180008641  jmp     short loc_180008653
0x180008643  mov     [rbx+0E0h], rdi
0x18000864a  xor     eax, eax
0x18000864c  mov     [rbx+0E8h], rsi
0x180008653  mov     rbx, [rsp+48h+arg_0]
0x180008658  mov     rsi, [rsp+48h+arg_8]
0x18000865d  add     rsp, 40h
0x180008661  pop     rdi
0x180008662  retn
```
