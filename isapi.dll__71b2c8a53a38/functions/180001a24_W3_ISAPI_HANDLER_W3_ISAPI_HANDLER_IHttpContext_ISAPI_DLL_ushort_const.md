# W3_ISAPI_HANDLER::W3_ISAPI_HANDLER(IHttpContext *,ISAPI_DLL *,ushort const *)

- ea: `0x180001a24`
- end: `0x180001ba5`
- name: `??0W3_ISAPI_HANDLER@@QEAA@PEAVIHttpContext@@PEAVISAPI_DLL@@PEBG@Z`
- size: `385`
- prototype: `W3_ISAPI_HANDLER *__fastcall(W3_ISAPI_HANDLER *__hidden this, struct IHttpContext *, struct ISAPI_DLL *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002d9c`

## callees

- `0x180001a24`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180001af3`
- `iisutil!PuDbgPrint` at `0x180001b8c`
- `iisutil!PuDbgPrint` at `0x180001af3`
- `iisutil!PuDbgPrint` at `0x180001b8c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001a96`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001a96`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001a7c`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001a7c`

## string_xrefs

- `0x180001b67`: `W3_ISAPI_HANDLER %p created successfully.\n`
- `0x180001ae1`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_handler.h`
- `0x180001b85`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_handler.h`

## pseudocode

```c
W3_ISAPI_HANDLER *__fastcall W3_ISAPI_HANDLER::W3_ISAPI_HANDLER(
        W3_ISAPI_HANDLER *this,
        struct IHttpContext *a2,
        struct ISAPI_DLL *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rax
  void (__fastcall ***v8)(_QWORD, __int64, __int64); // rbx

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &W3_ISAPI_HANDLER::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = a3;
  *((_QWORD *)this + 5) = 1;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  STRA::STRA((W3_ISAPI_HANDLER *)((char *)this + 160));
  STRA::STRA((W3_ISAPI_HANDLER *)((char *)this + 216), (char *)this + 272, 0x80u);
  *((_QWORD *)this + 51) = a4;
  *((_WORD *)this + 200) = 0;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x20000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_handler.h",
      85,
      "W3_ISAPI_HANDLER::W3_ISAPI_HANDLER",
      "Creating W3_ISAPI_HANDLER %p.  IHttpContext=%p.\r\n",
      this,
      a2);
  v7 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
  v8 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
  (**v8)(v8, 29, 1);
  (**v8)(v8, 30, 1);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x20000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_handler.h",
      101,
      "W3_ISAPI_HANDLER::W3_ISAPI_HANDLER",
      "W3_ISAPI_HANDLER %p created successfully.\r\n",
      this);
  return this;
}

```

## disassembly

```asm
0x180001a24  mov     [rsp+arg_0], rbx
0x180001a29  mov     [rsp+arg_8], rsi
0x180001a2e  push    rdi
0x180001a2f  sub     rsp, 40h
0x180001a33  lea     rax, ??_7W3_ISAPI_HANDLER@@6B@; const W3_ISAPI_HANDLER::`vftable'
0x180001a3a  mov     [rcx+8], rdx
0x180001a3e  mov     [rcx], rax
0x180001a41  mov     rdi, rcx
0x180001a44  mov     qword ptr [rcx+10h], 0
0x180001a4c  mov     rbx, r9
0x180001a4f  mov     qword ptr [rcx+18h], 0
0x180001a57  mov     rsi, rdx
0x180001a5a  mov     [rcx+20h], r8
0x180001a5e  mov     qword ptr [rcx+28h], 1
0x180001a66  mov     dword ptr [rcx+30h], 0
0x180001a6d  mov     qword ptr [rcx+38h], 0
0x180001a75  add     rcx, 0A0h
0x180001a7c  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180001a82  lea     rdx, [rdi+110h]
0x180001a89  mov     r8d, 80h
0x180001a8f  lea     rcx, [rdi+0D8h]
0x180001a96  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180001a9c  xor     eax, eax
0x180001a9e  mov     [rdi+198h], rbx
0x180001aa5  mov     [rdi+190h], ax
0x180001aac  mov     eax, cs:g_dwDebugFlags
0x180001ab2  test    al, 3
0x180001ab4  setnz   cl
0x180001ab7  bt      eax, 1Dh
0x180001abb  setb    al
0x180001abe  test    al, cl
0x180001ac0  jz      short loc_180001AF9
0x180001ac2  mov     rcx, cs:g_pDebug
0x180001ac9  lea     rax, aCreatingW3Isap; "Creating W3_ISAPI_HANDLER %p.  IHttpCon"...
0x180001ad0  mov     [rsp+48h+var_18], rsi
0x180001ad5  lea     r9, aW3IsapiHandler_0; "W3_ISAPI_HANDLER::W3_ISAPI_HANDLER"
0x180001adc  mov     [rsp+48h+var_20], rdi
0x180001ae1  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001ae8  mov     r8d, 55h ; 'U'
0x180001aee  mov     [rsp+48h+var_28], rax
0x180001af3  call    cs:__imp_PuDbgPrint
0x180001af9  mov     rax, [rsi]
0x180001afc  mov     rcx, rsi
0x180001aff  mov     rax, [rax]
0x180001b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b07  mov     rdx, rax
0x180001b0a  mov     rcx, [rax]
0x180001b0d  mov     rax, [rcx+18h]
0x180001b11  mov     rcx, rdx
0x180001b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b19  mov     rbx, rax
0x180001b1c  mov     edx, 1Dh
0x180001b21  mov     rcx, [rax]
0x180001b24  lea     r8d, [rdx-1Ch]
0x180001b28  mov     rax, [rcx]
0x180001b2b  mov     rcx, rbx
0x180001b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b33  mov     rcx, [rbx]
0x180001b36  mov     edx, 1Eh
0x180001b3b  mov     rax, [rcx]
0x180001b3e  lea     r8d, [rdx-1Dh]
0x180001b42  mov     rcx, rbx
0x180001b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b4a  mov     eax, cs:g_dwDebugFlags
0x180001b50  test    al, 3
0x180001b52  setnz   cl
0x180001b55  bt      eax, 1Dh
0x180001b59  setb    al
0x180001b5c  test    al, cl
0x180001b5e  jz      short loc_180001B92
0x180001b60  mov     rcx, cs:g_pDebug
0x180001b67  lea     rax, aW3IsapiHandler_3; "W3_ISAPI_HANDLER %p created successfull"...
0x180001b6e  mov     [rsp+48h+var_20], rdi
0x180001b73  lea     r9, aW3IsapiHandler_0; "W3_ISAPI_HANDLER::W3_ISAPI_HANDLER"
0x180001b7a  mov     r8d, 65h ; 'e'
0x180001b80  mov     [rsp+48h+var_28], rax
0x180001b85  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001b8c  call    cs:__imp_PuDbgPrint
0x180001b92  mov     rbx, [rsp+48h+arg_0]
0x180001b97  mov     rax, rdi
0x180001b9a  mov     rsi, [rsp+48h+arg_8]
0x180001b9f  add     rsp, 40h
0x180001ba3  pop     rdi
0x180001ba4  retn
```
