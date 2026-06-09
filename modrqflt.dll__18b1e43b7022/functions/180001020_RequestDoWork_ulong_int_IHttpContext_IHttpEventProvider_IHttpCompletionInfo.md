# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180001020`
- end: `0x1800010ba`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `154`
- prototype: ``
- caller_count: `25`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006230`
- `0x1800062a0`
- `0x180006310`
- `0x180006380`
- `0x180006430`
- `0x1800064a0`
- `0x180006510`
- `0x180006580`
- `0x1800065f0`
- `0x180006660`
- `0x1800066d0`
- `0x180006740`
- `0x1800067b0`
- `0x180006820`
- `0x180006890`
- `0x180006900`
- `0x1800069b0`
- `0x180006a20`
- `0x180006a90`
- `0x180006b00`
- `0x180006b70`
- `0x180006be0`
- `0x180006c50`
- `0x180006cc0`
- `0x180006d70`

## callees

- `0x180001020`
- `0x1800010c0`
- `0x180002ab0`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800010b0`
- `iisutil!PuDbgPrint` at `0x1800010b0`

## string_xrefs

- `0x18000108e`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\module.cxx`

## pseudocode

```c
__int64 __fastcall RequestDoWork(int a1, int a2, struct IHttpContext *a3)
{
  const char *v4; // rax

  if ( a1 == 16 || a1 == 1 )
    return DoBeginRequest(a3);
  if ( a1 == 0x20000000 )
    return DoSendResponseStatusAndHeaders(a3);
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v4 = "Post-n";
    if ( !a2 )
      v4 = "N";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\module.cxx",
      184,
      "RequestDoWork",
      "%sotification 0x%08x occurred.\r\n",
      v4,
      a1);
  }
  return 0;
}

```

## disassembly

```asm
0x180001020  sub     rsp, 48h
0x180001024  mov     rax, r8
0x180001027  cmp     ecx, 10h
0x18000102a  jnz     short loc_180001045
0x18000102c  mov     rdx, [rsp+48h+arg_20]
0x180001031  mov     r8, r9
0x180001034  mov     rcx, rax
0x180001037  add     rsp, 48h
0x18000103b  jmp     ?DoBeginRequest@@YA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpCompletionInfo@@PEAVIHttpEventProvider@@@Z; DoBeginRequest(IHttpContext *,IHttpCompletionInfo *,IHttpEventProvider *)
0x180001040  add     rsp, 48h
0x180001044  retn
0x180001045  mov     r8d, ecx
0x180001048  sub     r8d, 1
0x18000104c  jz      short loc_18000102C
0x18000104e  cmp     r8d, 1FFFFFFFh
0x180001055  jnz     short loc_180001063
0x180001057  mov     rcx, rax
0x18000105a  add     rsp, 48h
0x18000105e  jmp     ?DoSendResponseStatusAndHeaders@@YA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpCompletionInfo@@PEAVIHttpEventProvider@@@Z; DoSendResponseStatusAndHeaders(IHttpContext *,IHttpCompletionInfo *,IHttpEventProvider *)
0x180001063  test    byte ptr cs:g_dwDebugFlags, 3
0x18000106a  jz      short loc_1800010B6
0x18000106c  mov     [rsp+48h+var_18], ecx
0x180001070  lea     r8, aN; "N"
0x180001077  mov     rcx, cs:g_pDebug
0x18000107e  lea     rax, aPostN; "Post-n"
0x180001085  test    edx, edx
0x180001087  lea     r9, aRequestdowork; "RequestDoWork"
0x18000108e  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001095  cmovz   rax, r8
0x180001099  mov     r8d, 0B8h
0x18000109f  mov     [rsp+48h+var_20], rax
0x1800010a4  lea     rax, aSotification0x; "%sotification 0x%08x occurred.\r\n"
0x1800010ab  mov     [rsp+48h+var_28], rax
0x1800010b0  call    cs:__imp_PuDbgPrint
0x1800010b6  xor     eax, eax
0x1800010b8  jmp     short loc_180001040
```
