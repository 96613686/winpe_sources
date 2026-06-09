# ISAPI_REQUEST::~ISAPI_REQUEST(void)

- ea: `0x18000c3cc`
- end: `0x18000c454`
- name: `??1ISAPI_REQUEST@@AEAA@XZ`
- size: `136`
- prototype: `void __fastcall(ISAPI_REQUEST *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f440`

## callees

- `0x18000c3cc`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000c448`
- `iisutil!PuDbgPrint` at `0x18000c448`

## string_xrefs

- `0x18000c441`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_request.cxx`

## pseudocode

```c
void __fastcall ISAPI_REQUEST::~ISAPI_REQUEST(ISAPI_REQUEST *this)
{
  __int64 v2; // rcx
  int v3; // eax
  bool v4; // zf

  *(_QWORD *)this = &ISAPI_REQUEST::`vftable';
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 256LL))(v2);
    *((_QWORD *)this + 7) = 0;
  }
  v3 = g_dwDebugFlags;
  v4 = (g_dwDebugFlags & 3) == 0;
  *((_DWORD *)this + 2) = 1230197350;
  if ( !v4 && (v3 & 0x20000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_request.cxx",
      3909,
      "ISAPI_REQUEST::~ISAPI_REQUEST",
      "ISAPI_REQUEST %p has been destroyed.\r\n",
      this);
}

```

## disassembly

```asm
0x18000c3cc  push    rbx
0x18000c3ce  sub     rsp, 30h
0x18000c3d2  lea     rax, ??_7ISAPI_REQUEST@@6B@; const ISAPI_REQUEST::`vftable'
0x18000c3d9  mov     rbx, rcx
0x18000c3dc  mov     [rcx], rax
0x18000c3df  mov     rcx, [rcx+38h]
0x18000c3e3  test    rcx, rcx
0x18000c3e6  jz      short loc_18000C3FF
0x18000c3e8  mov     rax, [rcx]
0x18000c3eb  mov     rax, [rax+100h]
0x18000c3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f7  mov     qword ptr [rbx+38h], 0
0x18000c3ff  mov     eax, cs:g_dwDebugFlags
0x18000c405  test    al, 3
0x18000c407  mov     dword ptr [rbx+8], 49535266h
0x18000c40e  setnz   cl
0x18000c411  bt      eax, 1Dh
0x18000c415  setb    al
0x18000c418  test    al, cl
0x18000c41a  jz      short loc_18000C44E
0x18000c41c  mov     rcx, cs:g_pDebug
0x18000c423  lea     rax, aIsapiRequestPH; "ISAPI_REQUEST %p has been destroyed.\r"...
0x18000c42a  mov     [rsp+38h+var_10], rbx
0x18000c42f  lea     r9, aIsapiRequestIs; "ISAPI_REQUEST::~ISAPI_REQUEST"
0x18000c436  mov     r8d, 0F45h
0x18000c43c  mov     [rsp+38h+var_18], rax
0x18000c441  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000c448  call    cs:__imp_PuDbgPrint
0x18000c44e  add     rsp, 30h
0x18000c452  pop     rbx
0x18000c453  retn
```
