# W3_ISAPI_HANDLER::~W3_ISAPI_HANDLER(void)

- ea: `0x180001c84`
- end: `0x180001d4c`
- name: `??1W3_ISAPI_HANDLER@@QEAA@XZ`
- size: `200`
- prototype: `void __fastcall(W3_ISAPI_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001dc0`

## callees

- `0x180001c84`
- `0x180001ddc`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180001d26`
- `iisutil!PuDbgPrint` at `0x180001d26`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001d33`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001d33`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001d45`

## string_xrefs

- `0x180001d1f`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_handler.h`

## pseudocode

```c
void __fastcall W3_ISAPI_HANDLER::~W3_ISAPI_HANDLER(W3_ISAPI_HANDLER *this)
{
  ISAPI_DLL *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rax
  const void *v5; // [rsp+28h] [rbp-10h]

  *(_QWORD *)this = &W3_ISAPI_HANDLER::`vftable';
  v2 = (ISAPI_DLL *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    ISAPI_DLL::DereferenceIsapiDll(v2);
    *((_QWORD *)this + 4) = 0;
  }
  v3 = (***((__int64 (__fastcall ****)(_QWORD))this + 1))(*((_QWORD *)this + 1));
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v4 + 8LL))(v4, 29, 1);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x20000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_handler.h",
      124,
      "W3_ISAPI_HANDLER::~W3_ISAPI_HANDLER",
      "W3_ISAPI_HANDLER %p has been destroyed.\r\n",
      v5);
  STRA::~STRA((W3_ISAPI_HANDLER *)((char *)this + 216));
  STRA::~STRA((W3_ISAPI_HANDLER *)((char *)this + 160));
}

```

## disassembly

```asm
0x180001c84  push    rbx
0x180001c86  sub     rsp, 30h
0x180001c8a  lea     rax, ??_7W3_ISAPI_HANDLER@@6B@; const W3_ISAPI_HANDLER::`vftable'
0x180001c91  mov     rbx, rcx
0x180001c94  mov     [rcx], rax
0x180001c97  mov     rcx, [rcx+20h]; this
0x180001c9b  test    rcx, rcx
0x180001c9e  jz      short loc_180001CAD
0x180001ca0  call    ?DereferenceIsapiDll@ISAPI_DLL@@QEAAXXZ; ISAPI_DLL::DereferenceIsapiDll(void)
0x180001ca5  mov     qword ptr [rbx+20h], 0
0x180001cad  mov     rcx, [rbx+8]
0x180001cb1  mov     rax, [rcx]
0x180001cb4  mov     rax, [rax]
0x180001cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cbc  mov     rdx, rax
0x180001cbf  mov     rcx, [rax]
0x180001cc2  mov     rax, [rcx+18h]
0x180001cc6  mov     rcx, rdx
0x180001cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cce  mov     r9, rax
0x180001cd1  mov     edx, 1Dh
0x180001cd6  mov     rcx, [rax]
0x180001cd9  lea     r8d, [rdx-1Ch]
0x180001cdd  mov     rax, [rcx+8]
0x180001ce1  mov     rcx, r9
0x180001ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ce9  mov     eax, cs:g_dwDebugFlags
0x180001cef  test    al, 3
0x180001cf1  setnz   cl
0x180001cf4  bt      eax, 1Dh
0x180001cf8  setb    al
0x180001cfb  test    al, cl
0x180001cfd  jz      short loc_180001D2C
0x180001cff  mov     rcx, cs:g_pDebug
0x180001d06  lea     rax, aW3IsapiHandler; "W3_ISAPI_HANDLER %p has been destroyed."...
0x180001d0d  lea     r9, aW3IsapiHandler_2; "W3_ISAPI_HANDLER::~W3_ISAPI_HANDLER"
0x180001d14  mov     [rsp+38h+var_18], rax
0x180001d19  mov     r8d, 7Ch ; '|'
0x180001d1f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001d26  call    cs:__imp_PuDbgPrint
0x180001d2c  lea     rcx, [rbx+0D8h]
0x180001d33  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001d39  lea     rcx, [rbx+0A0h]
0x180001d40  add     rsp, 30h
0x180001d44  pop     rbx
0x180001d45  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
