# ISAPI_REQUEST::Create(void)

- ea: `0x18000c7d8`
- end: `0x18000c891`
- name: `?Create@ISAPI_REQUEST@@QEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b3d0`

## callees

- `0x18000c7d8`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000c837`
- `iisutil!PuDbgPrint` at `0x18000c883`
- `iisutil!PuDbgPrint` at `0x18000c837`
- `iisutil!PuDbgPrint` at `0x18000c883`

## string_xrefs

- `0x18000c801`: `ISAPI_REQUEST::Create`
- `0x18000c86a`: `ISAPI_REQUEST::Create`
- `0x18000c80c`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_request.cxx`
- `0x18000c87c`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_request.cxx`
- `0x18000c85e`: `ISAPI_REQUEST %p created successfully.\n`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::Create(ISAPI_REQUEST *this)
{
  int v1; // r8d

  v1 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x20000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_request.cxx",
      207,
      "ISAPI_REQUEST::Create",
      "Creating ISAPI_REQUEST %p, W3Context=%p, Handler=%p.\r\n",
      this,
      *((const void **)this + 3),
      *((const void **)this + 4));
    v1 = g_dwDebugFlags;
  }
  if ( (v1 & 3) != 0 && (v1 & 0x20000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_request.cxx",
      216,
      "ISAPI_REQUEST::Create",
      "ISAPI_REQUEST %p created successfully.\r\n",
      this);
  return 0;
}

```

## disassembly

```asm
0x18000c7d8  mov     r11, rsp
0x18000c7db  push    rbx
0x18000c7dc  sub     rsp, 40h
0x18000c7e0  mov     r8d, cs:g_dwDebugFlags
0x18000c7e7  mov     rbx, rcx
0x18000c7ea  test    r8b, 3
0x18000c7ee  setnz   dl
0x18000c7f1  bt      r8d, 1Dh
0x18000c7f6  setb    al
0x18000c7f9  test    al, dl
0x18000c7fb  jz      short loc_18000C844
0x18000c7fd  mov     rax, [rcx+20h]
0x18000c801  lea     r9, aIsapiRequestCr; "ISAPI_REQUEST::Create"
0x18000c808  mov     [r11-10h], rax
0x18000c80c  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000c813  mov     rax, [rcx+18h]
0x18000c817  mov     r8d, 0CFh
0x18000c81d  mov     [r11-18h], rax
0x18000c821  lea     rax, aCreatingIsapiR; "Creating ISAPI_REQUEST %p, W3Context=%p"...
0x18000c828  mov     [r11-20h], rcx
0x18000c82c  mov     rcx, cs:g_pDebug
0x18000c833  mov     [r11-28h], rax
0x18000c837  call    cs:__imp_PuDbgPrint
0x18000c83d  mov     r8d, cs:g_dwDebugFlags
0x18000c844  test    r8b, 3
0x18000c848  setnz   cl
0x18000c84b  bt      r8d, 1Dh
0x18000c850  setb    al
0x18000c853  test    al, cl
0x18000c855  jz      short loc_18000C889
0x18000c857  mov     rcx, cs:g_pDebug
0x18000c85e  lea     rax, aIsapiRequestPC; "ISAPI_REQUEST %p created successfully."...
0x18000c865  mov     [rsp+48h+var_20], rbx
0x18000c86a  lea     r9, aIsapiRequestCr; "ISAPI_REQUEST::Create"
0x18000c871  mov     r8d, 0D8h
0x18000c877  mov     [rsp+48h+var_28], rax
0x18000c87c  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000c883  call    cs:__imp_PuDbgPrint
0x18000c889  xor     eax, eax
0x18000c88b  add     rsp, 40h
0x18000c88f  pop     rbx
0x18000c890  retn
```
