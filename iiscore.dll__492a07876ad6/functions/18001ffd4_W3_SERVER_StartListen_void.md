# W3_SERVER::StartListen(void)

- ea: `0x18001ffd4`
- end: `0x180020142`
- name: `?StartListen@W3_SERVER@@QEAAJXZ`
- size: `366`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034190`

## callees

- `0x18001ffd4`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1800200d4`
- `msvcrt!_ultow_s` at `0x1800200d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800200b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800200b8`
- `iisutil!PuDbgPrint` at `0x1800200a5`
- `iisutil!PuDbgPrint` at `0x1800200a5`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18002004f`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18002004f`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180020112`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180020112`
- `w3dt!UlAtqStartListen` at `0x18002005b`
- `w3dt!UlAtqStartListen` at `0x18002005b`

## string_xrefs

- `0x18002008c`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`

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
0x18001ffd4  mov     [rsp-8+arg_0], rbx
0x18001ffd9  mov     [rsp-8+arg_8], rdi
0x18001ffde  push    rbp
0x18001ffdf  mov     rbp, rsp
0x18001ffe2  sub     rsp, 80h
0x18001ffe9  mov     rax, cs:__security_cookie
0x18001fff0  xor     rax, rsp
0x18001fff3  mov     [rbp+var_10], rax
0x18001fff7  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x18001fffe  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180020005  cmp     dword ptr [rcx+8], 0
0x180020009  jz      short loc_18002005B
0x18002000b  mov     edx, 1
0x180020010  test    [rcx+28h], dl
0x180020013  jz      short loc_18002005B
0x180020015  cmp     dword ptr [rcx+2Ch], 4
0x180020019  jb      short loc_18002005B
0x18002001b  xorps   xmm0, xmm0
0x18002001e  lea     eax, [rdx+2Fh]
0x180020021  movups  [rbp+var_3E], xmm0
0x180020025  mov     [rbp+Buffer], ax
0x180020029  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISStartupEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISStartupEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180020030  movups  [rbp+var_2E], xmm0
0x180020034  mov     word ptr [rbp+var_3E+4], dx
0x180020038  lea     rdx, [rbp+Buffer]
0x18002003c  movups  [rbp+var_2E+0Eh], xmm0
0x180020040  mov     qword ptr [rbp+var_2E+6], rax
0x180020044  mov     [rbp+var_14], 1A0000h
0x18002004b  mov     byte ptr [rbp+var_3E+2], 26h ; '&'
0x18002004f  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x180020056  nop     dword ptr [rax+rax+00h]
0x18002005b  call    cs:__imp_?UlAtqStartListen@@YAJXZ; UlAtqStartListen(void)
0x180020062  nop     dword ptr [rax+rax+00h]
0x180020067  mov     ebx, eax
0x180020069  test    eax, eax
0x18002006b  jns     loc_18002011E
0x180020071  test    byte ptr cs:g_dwDebugFlags, 3
0x180020078  jz      short loc_1800200B1
0x18002007a  mov     rcx, cs:g_pDebug
0x180020081  lea     r9, aW3ServerStartl; "W3_SERVER::StartListen"
0x180020088  mov     [rsp+80h+var_58], eax
0x18002008c  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180020093  lea     rax, aErrorListening; "Error listening for HTTP requests.  hr "...
0x18002009a  mov     r8d, 676h
0x1800200a0  mov     [rsp+80h+var_60], rax
0x1800200a5  call    cs:__imp_PuDbgPrint
0x1800200ac  nop     dword ptr [rax+rax+00h]
0x1800200b1  xorps   xmm0, xmm0
0x1800200b4  movups  [rbp+var_50], xmm0
0x1800200b8  call    cs:__imp_GetCurrentProcessId
0x1800200bf  nop     dword ptr [rax+rax+00h]
0x1800200c4  mov     r9d, 0Ah; Radix
0x1800200ca  lea     rdx, [rbp+Buffer]; Buffer
0x1800200ce  mov     ecx, eax; Value
0x1800200d0  lea     r8d, [r9+6]; BufferCount
0x1800200d4  call    cs:__imp__ultow_s
0x1800200db  nop     dword ptr [rax+rax+00h]
0x1800200e0  mov     rax, [rdi]
0x1800200e3  mov     rcx, rdi
0x1800200e6  mov     rax, [rax+8]
0x1800200ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200ef  mov     qword ptr [rbp+var_50], rax
0x1800200f3  lea     rcx, [rdi+1Ch]
0x1800200f7  lea     rax, [rbp+Buffer]
0x1800200fb  mov     dword ptr [rsp+80h+var_60], ebx
0x1800200ff  mov     r8d, 2
0x180020105  mov     qword ptr [rbp+var_50+8], rax
0x180020109  lea     r9, [rbp+var_50]
0x18002010d  mov     edx, 0C00008DDh
0x180020112  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180020119  nop     dword ptr [rax+rax+00h]
0x18002011e  mov     eax, ebx
0x180020120  mov     rcx, [rbp+var_10]
0x180020124  xor     rcx, rsp; StackCookie
0x180020127  call    __security_check_cookie
0x18002012c  lea     r11, [rsp+80h+var_s0]
0x180020134  mov     rbx, [r11+10h]
0x180020138  mov     rdi, [r11+18h]
0x18002013c  mov     rsp, r11
0x18002013f  pop     rbp
0x180020140  retn
```
