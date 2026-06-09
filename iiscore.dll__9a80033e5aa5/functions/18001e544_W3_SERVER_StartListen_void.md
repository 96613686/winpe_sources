# W3_SERVER::StartListen(void)

- ea: `0x18001e544`
- end: `0x18001e68d`
- name: `?StartListen@W3_SERVER@@QEAAJXZ`
- size: `329`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800313a0`

## callees

- `0x18001e544`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18001e62c`
- `msvcrt!_ultow_s` at `0x18001e62c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e616`
- `iisutil!PuDbgPrint` at `0x18001e609`
- `iisutil!PuDbgPrint` at `0x18001e609`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001e5bf`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001e5bf`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e664`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e664`
- `w3dt!UlAtqStartListen` at `0x18001e5c5`
- `w3dt!UlAtqStartListen` at `0x18001e5c5`

## string_xrefs

- `0x18001e5f0`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`

## pseudocode

```c
__int64 __fastcall W3_SERVER::StartListen(W3_SERVER *this)
{
  W3_SERVER *v1; // rdi
  int started; // eax
  unsigned int v3; // ebx
  DWORD CurrentProcessId; // eax
  __int128 v6; // [rsp+30h] [rbp-50h] BYREF
  struct _EVENT_TRACE_HEADER Buffer; // [rsp+40h] [rbp-40h] BYREF

  v1 = g_pW3Server;
  if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
    && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 1) != 0
    && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
  {
    memset(&Buffer.FieldTypeFlags, 0, 24);
    Buffer.Size = 48;
    Buffer.Class.Version = 1;
    *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&Buffer.24 + 8) = 0;
    Buffer.GuidPtr = (ULONGLONG)&`IISStartupEvents::GetAreaGuid'::`2'::AreaGuid;
    Buffer.UserTime = 1703936;
    Buffer.Class.Type = 38;
    CEtwTracer::EtwTraceEvent(g_pEtwGlobalTracer, &Buffer);
  }
  started = UlAtqStartListen();
  v3 = started;
  if ( started < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3server.cxx",
        1654,
        "W3_SERVER::StartListen",
        "Error listening for HTTP requests.  hr = %x\n",
        started);
    v6 = 0;
    CurrentProcessId = GetCurrentProcessId();
    _ultow_s(CurrentProcessId, &Buffer.Size, 0x10u, 10);
    *(_QWORD *)&v6 = (*(__int64 (__fastcall **)(W3_SERVER *))(*(_QWORD *)v1 + 8LL))(v1);
    *((_QWORD *)&v6 + 1) = &Buffer;
    EVENT_LOG::LogEvent((W3_SERVER *)((char *)v1 + 28), 0xC00008DD, 2u, (const unsigned __int16 **const)&v6, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18001e544  mov     [rsp-8+arg_0], rbx
0x18001e549  mov     [rsp-8+arg_8], rdi
0x18001e54e  push    rbp
0x18001e54f  mov     rbp, rsp
0x18001e552  sub     rsp, 80h
0x18001e559  mov     rax, cs:__security_cookie
0x18001e560  xor     rax, rsp
0x18001e563  mov     [rbp+var_10], rax
0x18001e567  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x18001e56e  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001e575  cmp     dword ptr [rcx+8], 0
0x18001e579  jz      short loc_18001E5C5
0x18001e57b  mov     edx, 1
0x18001e580  test    [rcx+28h], dl
0x18001e583  jz      short loc_18001E5C5
0x18001e585  cmp     dword ptr [rcx+2Ch], 4
0x18001e589  jb      short loc_18001E5C5
0x18001e58b  xorps   xmm0, xmm0
0x18001e58e  lea     eax, [rdx+2Fh]
0x18001e591  movups  [rbp+var_3E], xmm0
0x18001e595  mov     [rbp+Buffer], ax
0x18001e599  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISStartupEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISStartupEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001e5a0  movups  [rbp+var_2E], xmm0
0x18001e5a4  mov     word ptr [rbp+var_3E+4], dx
0x18001e5a8  lea     rdx, [rbp+Buffer]
0x18001e5ac  movups  [rbp+var_2E+0Eh], xmm0
0x18001e5b0  mov     qword ptr [rbp+var_2E+6], rax
0x18001e5b4  mov     [rbp+var_14], 1A0000h
0x18001e5bb  mov     byte ptr [rbp+var_3E+2], 26h ; '&'
0x18001e5bf  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001e5c5  call    cs:__imp_?UlAtqStartListen@@YAJXZ; UlAtqStartListen(void)
0x18001e5cb  mov     ebx, eax
0x18001e5cd  test    eax, eax
0x18001e5cf  jns     loc_18001E66A
0x18001e5d5  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e5dc  jz      short loc_18001E60F
0x18001e5de  mov     rcx, cs:g_pDebug
0x18001e5e5  lea     r9, aW3ServerStartl; "W3_SERVER::StartListen"
0x18001e5ec  mov     [rsp+80h+var_58], eax
0x18001e5f0  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001e5f7  lea     rax, aErrorListening; "Error listening for HTTP requests.  hr "...
0x18001e5fe  mov     r8d, 676h
0x18001e604  mov     [rsp+80h+var_60], rax
0x18001e609  call    cs:__imp_PuDbgPrint
0x18001e60f  xorps   xmm0, xmm0
0x18001e612  movups  [rbp+var_50], xmm0
0x18001e616  call    cs:__imp_GetCurrentProcessId
0x18001e61c  mov     r9d, 0Ah; Radix
0x18001e622  lea     rdx, [rbp+Buffer]; Buffer
0x18001e626  mov     ecx, eax; Value
0x18001e628  lea     r8d, [r9+6]; BufferCount
0x18001e62c  call    cs:__imp__ultow_s
0x18001e632  mov     rax, [rdi]
0x18001e635  mov     rcx, rdi
0x18001e638  mov     rax, [rax+8]
0x18001e63c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e641  mov     qword ptr [rbp+var_50], rax
0x18001e645  lea     rcx, [rdi+1Ch]
0x18001e649  lea     rax, [rbp+Buffer]
0x18001e64d  mov     dword ptr [rsp+80h+var_60], ebx
0x18001e651  mov     r8d, 2
0x18001e657  mov     qword ptr [rbp+var_50+8], rax
0x18001e65b  lea     r9, [rbp+var_50]
0x18001e65f  mov     edx, 0C00008DDh
0x18001e664  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001e66a  mov     eax, ebx
0x18001e66c  mov     rcx, [rbp+var_10]
0x18001e670  xor     rcx, rsp; StackCookie
0x18001e673  call    __security_check_cookie
0x18001e678  lea     r11, [rsp+80h+var_s0]
0x18001e680  mov     rbx, [r11+10h]
0x18001e684  mov     rdi, [r11+18h]
0x18001e688  mov     rsp, r11
0x18001e68b  pop     rbp
0x18001e68c  retn
```
