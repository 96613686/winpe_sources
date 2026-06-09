# SSFGetChannelBindingToken(ISAPI_CONTEXT *,uchar * *,ulong *)

- ea: `0x180007680`
- end: `0x18000770c`
- name: `?SSFGetChannelBindingToken@@YAJPEAVISAPI_CONTEXT@@PEAPEAEPEAK@Z`
- size: `140`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180007680`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800076df`
- `iisutil!PuDbgPrint` at `0x1800076df`

## string_xrefs

- `0x1800076d8`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800076b9`: `\n  HSE_REQ_GET_CHANNEL_BINDING_TOKEN [%p]: Function Entry\n  <END>\n\n`
- `0x1800076c7`: `SSFGetChannelBindingToken`

## pseudocode

```c
__int64 __fastcall SSFGetChannelBindingToken(struct ISAPI_CONTEXT *a1, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v4; // rbx

  v4 = *((_QWORD *)a1 + 24);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      5117,
      "SSFGetChannelBindingToken",
      "\r\n  HSE_REQ_GET_CHANNEL_BINDING_TOKEN [%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
  return (*(__int64 (__fastcall **)(__int64, unsigned __int8 **, unsigned int *))(*(_QWORD *)v4 + 272LL))(v4, a2, a3);
}

```

## disassembly

```asm
0x180007680  mov     r11, rsp
0x180007683  mov     [r11+8], rbx
0x180007687  mov     [r11+10h], rsi
0x18000768b  push    rdi
0x18000768c  sub     rsp, 30h
0x180007690  mov     eax, cs:g_dwDebugFlags
0x180007696  mov     rdi, r8
0x180007699  mov     rbx, [rcx+0C0h]
0x1800076a0  test    al, 3
0x1800076a2  mov     rsi, rdx
0x1800076a5  setnz   r9b
0x1800076a9  bt      eax, 1Ah
0x1800076ad  setb    al
0x1800076b0  test    al, r9b
0x1800076b3  jz      short loc_1800076E5
0x1800076b5  mov     [r11-10h], rcx
0x1800076b9  lea     rax, aHseReqGetChann_0; "\r\n  HSE_REQ_GET_CHANNEL_BINDING_TOKEN"...
0x1800076c0  mov     rcx, cs:g_pDebug
0x1800076c7  lea     r9, aSsfgetchannelb; "SSFGetChannelBindingToken"
0x1800076ce  mov     r8d, 13FDh
0x1800076d4  mov     [r11-18h], rax
0x1800076d8  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800076df  call    cs:__imp_PuDbgPrint
0x1800076e5  mov     rax, [rbx]
0x1800076e8  mov     r8, rdi
0x1800076eb  mov     rdx, rsi
0x1800076ee  mov     rcx, rbx
0x1800076f1  mov     rax, [rax+110h]
0x1800076f8  mov     rbx, [rsp+38h+arg_0]
0x1800076fd  mov     rsi, [rsp+38h+arg_8]
0x180007702  add     rsp, 30h
0x180007706  pop     rdi
0x180007707  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
