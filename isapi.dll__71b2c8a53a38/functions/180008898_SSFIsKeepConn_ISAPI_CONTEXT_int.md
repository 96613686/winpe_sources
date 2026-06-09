# SSFIsKeepConn(ISAPI_CONTEXT *,int *)

- ea: `0x180008898`
- end: `0x180008963`
- name: `?SSFIsKeepConn@@YAJPEAVISAPI_CONTEXT@@PEAH@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180008898`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800088f0`
- `iisutil!PuDbgPrint` at `0x180008941`
- `iisutil!PuDbgPrint` at `0x1800088f0`
- `iisutil!PuDbgPrint` at `0x180008941`

## string_xrefs

- `0x1800088e9`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000893a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFIsKeepConn(struct ISAPI_CONTEXT *a1, int *a2)
{
  int v2; // r9d

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      866,
      "SSFIsKeepConn",
      "\r\n  HSE_REQ_IS_KEEP_CONN[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v2 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    *a2 = *((_DWORD *)a1 + 62);
    return 0;
  }
  else
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        882,
        "SSFIsKeepConn",
        "\r\n  HSE_REQ_IS_KEEP_CONN[%p]: Parameter validation failure\r\n    KeepAlive Ptr: NULL\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180008898  mov     [rsp+arg_0], rbx
0x18000889d  push    rdi
0x18000889e  sub     rsp, 30h
0x1800088a2  mov     r9d, cs:g_dwDebugFlags
0x1800088a9  mov     rdi, rdx
0x1800088ac  test    r9b, 3
0x1800088b0  mov     rbx, rcx
0x1800088b3  setnz   r8b
0x1800088b7  bt      r9d, 1Ah
0x1800088bc  setb    al
0x1800088bf  test    al, r8b
0x1800088c2  jz      short loc_1800088FD
0x1800088c4  mov     [rsp+38h+var_10], rcx
0x1800088c9  lea     rax, aHseReqIsKeepCo_1; "\r\n  HSE_REQ_IS_KEEP_CONN[%p]: Functio"...
0x1800088d0  mov     rcx, cs:g_pDebug
0x1800088d7  lea     r9, aSsfiskeepconn; "SSFIsKeepConn"
0x1800088de  mov     r8d, 362h
0x1800088e4  mov     [rsp+38h+var_18], rax
0x1800088e9  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800088f0  call    cs:__imp_PuDbgPrint
0x1800088f6  mov     r9d, cs:g_dwDebugFlags
0x1800088fd  test    rdi, rdi
0x180008900  jnz     short loc_18000894E
0x180008902  test    r9b, 3
0x180008906  setnz   cl
0x180008909  bt      r9d, 14h
0x18000890e  setb    al
0x180008911  test    al, cl
0x180008913  jz      short loc_180008947
0x180008915  mov     rcx, cs:g_pDebug
0x18000891c  lea     rax, aHseReqIsKeepCo_0; "\r\n  HSE_REQ_IS_KEEP_CONN[%p]: Paramet"...
0x180008923  mov     [rsp+38h+var_10], rbx
0x180008928  lea     r9, aSsfiskeepconn; "SSFIsKeepConn"
0x18000892f  mov     r8d, 372h
0x180008935  mov     [rsp+38h+var_18], rax
0x18000893a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008941  call    cs:__imp_PuDbgPrint
0x180008947  mov     eax, 80070057h
0x18000894c  jmp     short loc_180008958
0x18000894e  mov     eax, [rbx+0F8h]
0x180008954  mov     [rdi], eax
0x180008956  xor     eax, eax
0x180008958  mov     rbx, [rsp+38h+arg_0]
0x18000895d  add     rsp, 30h
0x180008961  pop     rdi
0x180008962  retn
```
