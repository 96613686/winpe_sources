# W3_FILTER_CONTEXT::GetUserToken(_HTTP_FILTER_CONTEXT *,void * *)

- ea: `0x18000ace0`
- end: `0x18000ad71`
- name: `?GetUserToken@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAPEAX@Z`
- size: `145`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ace0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad63`
- `iisutil!PuDbgPrint` at `0x18000ad58`
- `iisutil!PuDbgPrint` at `0x18000ad58`

## string_xrefs

- `0x18000ad51`: `servercommon\inetsrv\iis\iisrearc\iis70\isapifilters\filter.cxx`
- `0x18000ad38`: `[GetUserToken] Extension passed invalid parameters\n`
- `0x18000ad3f`: `W3_FILTER_CONTEXT::GetUserToken`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::GetUserToken(struct _HTTP_FILTER_CONTEXT *a1, void **a2)
{
  _QWORD **ServerContext; // rcx
  __int64 v4; // rax

  if ( a1 && (ServerContext = (_QWORD **)a1->ServerContext) != 0 && a2 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD *))(*ServerContext[3] + 48LL))(ServerContext[3]);
    *a2 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
    return 1;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapifilters\\filter.cxx",
        4453,
        "W3_FILTER_CONTEXT::GetUserToken",
        "[GetUserToken] Extension passed invalid parameters\r\n");
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000ace0  push    rbx
0x18000ace2  sub     rsp, 30h
0x18000ace6  mov     rbx, rdx
0x18000ace9  test    rcx, rcx
0x18000acec  jz      short loc_18000AD28
0x18000acee  mov     rcx, [rcx+8]
0x18000acf2  test    rcx, rcx
0x18000acf5  jz      short loc_18000AD28
0x18000acf7  test    rdx, rdx
0x18000acfa  jz      short loc_18000AD28
0x18000acfc  mov     rcx, [rcx+18h]
0x18000ad00  mov     rax, [rcx]
0x18000ad03  mov     rax, [rax+30h]
0x18000ad07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad0c  mov     rdx, rax
0x18000ad0f  mov     rcx, [rax]
0x18000ad12  mov     rax, [rcx+20h]
0x18000ad16  mov     rcx, rdx
0x18000ad19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad1e  mov     [rbx], rax
0x18000ad21  mov     eax, 1
0x18000ad26  jmp     short loc_18000AD6B
0x18000ad28  test    cs:g_dwDebugFlags, 3
0x18000ad2f  jz      short loc_18000AD5E
0x18000ad31  mov     rcx, cs:g_pDebug
0x18000ad38  lea     rax, aGetusertokenEx; "[GetUserToken] Extension passed invalid"...
0x18000ad3f  lea     r9, aW3FilterContex; "W3_FILTER_CONTEXT::GetUserToken"
0x18000ad46  mov     [rsp+38h+var_18], rax
0x18000ad4b  mov     r8d, 1165h
0x18000ad51  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000ad58  call    cs:__imp_PuDbgPrint
0x18000ad5e  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ad63  call    cs:__imp_SetLastError
0x18000ad69  xor     eax, eax
0x18000ad6b  add     rsp, 30h
0x18000ad6f  pop     rbx
0x18000ad70  retn
```
