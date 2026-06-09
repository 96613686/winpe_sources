# W3_SERVER::InitializeUlAtq(void)

- ea: `0x18001c480`
- end: `0x18001c6da`
- name: `?InitializeUlAtq@W3_SERVER@@QEAAJXZ`
- size: `602`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800313a0`

## callees

- `0x18001c480`
- `0x1800343f0`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18001c5d8`
- `msvcrt!_ultow_s` at `0x18001c67b`
- `msvcrt!_ultow_s` at `0x18001c5d8`
- `msvcrt!_ultow_s` at `0x18001c67b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c5c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c666`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c5c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c666`
- `iisutil!PuDbgPrint` at `0x18001c5bc`
- `iisutil!PuDbgPrint` at `0x18001c660`
- `iisutil!PuDbgPrint` at `0x18001c5bc`
- `iisutil!PuDbgPrint` at `0x18001c660`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001c50a`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001c50a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c53e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c551`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c5e1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c684`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c53e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c551`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c5e1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c684`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001c60a`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001c6ad`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001c60a`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001c6ad`
- `w3dt!UlAtqDuplicateRequestQueueHandle` at `0x18001c61c`
- `w3dt!UlAtqDuplicateRequestQueueHandle` at `0x18001c61c`
- `w3dt!UlAtqInitialize` at `0x18001c578`
- `w3dt!UlAtqInitialize` at `0x18001c578`

## string_xrefs

- `0x18001c5a3`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`
- `0x18001c647`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`

## pseudocode

```c
__int64 __fastcall W3_SERVER::InitializeUlAtq(W3_SERVER *this)
{
  W3_SERVER *v1; // rsi
  int v2; // ebx
  const unsigned __int16 *Str; // rdi
  const unsigned __int16 *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  DWORD v7; // eax
  int v8; // eax
  DWORD CurrentProcessId; // eax
  __int128 v11; // [rsp+40h] [rbp-59h] BYREF
  __int128 v12; // [rsp+50h] [rbp-49h] BYREF
  void (__fastcall *v13)(void *); // [rsp+60h] [rbp-39h]
  struct _EVENT_TRACE_HEADER v14; // [rsp+68h] [rbp-31h] BYREF
  wchar_t Buffer[12]; // [rsp+98h] [rbp-1h] BYREF

  v1 = g_pW3Server;
  v12 = 0;
  v13 = 0;
  v11 = 0;
  if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
    && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 1) != 0
    && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 5u )
  {
    memset(&v14.FieldTypeFlags, 0, 22);
    v14.Size = 48;
    v14.Class.Version = 1;
    *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v14.24 + 8) = 0;
    v14.GuidPtr = (ULONGLONG)&`IISStartupEvents::GetAreaGuid'::`2'::AreaGuid;
    v14.UserTime = 1703936;
    v14.Class.Type = 18;
    CEtwTracer::EtwTraceEvent(g_pEtwGlobalTracer, &v14);
  }
  v2 = *((_DWORD *)v1 + 137);
  *((_QWORD *)&v12 + 1) = W3_MAIN_CONTEXT::OnNewRequest;
  *(_QWORD *)&v12 = &W3_MAIN_CONTEXT::OnIoCompletion;
  v13 = W3_CONNECTION::OnDisconnect;
  Str = STRU::QueryStr((W3_SERVER *)((char *)v1 + 424));
  v4 = STRU::QueryStr((W3_SERVER *)((char *)v1 + 368));
  v5 = UlAtqInitialize(v4, Str, 0, 0, (struct _ULATQ_CONFIG *)&v12, v2, 0x2520u);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = UlAtqDuplicateRequestQueueHandle((void **)v1 + 211);
    v6 = v8;
    if ( v8 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3server.cxx",
          902,
          "W3_SERVER::InitializeUlAtq",
          "Error duplicating the request queue handle.  hr = %x\n",
          v8);
      CurrentProcessId = GetCurrentProcessId();
      _ultow_s(CurrentProcessId, Buffer, 0xBu, 11);
      *(_QWORD *)&v11 = STRU::QueryStr((W3_SERVER *)((char *)v1 + 368));
      *((_QWORD *)&v11 + 1) = Buffer;
      EVENT_LOG::LogEvent((W3_SERVER *)((char *)v1 + 28), 0xC0000907, 2u, (const unsigned __int16 **const)&v11, v6);
      v6 = 0;
    }
    *((_DWORD *)v1 + 392) = 1;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3server.cxx",
        876,
        "W3_SERVER::InitializeUlAtq",
        "Error initializing ULATQ.  hr = %x\n",
        v5);
    v7 = GetCurrentProcessId();
    _ultow_s(v7, Buffer, 0xBu, 10);
    *(_QWORD *)&v11 = STRU::QueryStr((W3_SERVER *)((char *)v1 + 368));
    *((_QWORD *)&v11 + 1) = Buffer;
    EVENT_LOG::LogEvent((W3_SERVER *)((char *)v1 + 28), 0xC00008DD, 2u, (const unsigned __int16 **const)&v11, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18001c480  push    rbp
0x18001c482  push    rbx
0x18001c483  push    rsi
0x18001c484  push    rdi
0x18001c485  push    r14
0x18001c487  push    r15
0x18001c489  lea     rbp, [rsp-2Fh]
0x18001c48e  sub     rsp, 0C8h
0x18001c495  mov     rax, cs:__security_cookie
0x18001c49c  xor     rax, rsp
0x18001c49f  mov     [rbp+57h+var_40], rax
0x18001c4a3  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x18001c4aa  xor     eax, eax
0x18001c4ac  mov     rsi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001c4b3  xorps   xmm0, xmm0
0x18001c4b6  movups  [rbp+57h+var_A0], xmm0
0x18001c4ba  mov     [rbp+57h+var_90], rax
0x18001c4be  lea     r15d, [rax+1]
0x18001c4c2  movups  [rbp+57h+var_B0], xmm0
0x18001c4c6  cmp     [rcx+8], eax
0x18001c4c9  jz      short loc_18001C510
0x18001c4cb  test    [rcx+28h], r15b
0x18001c4cf  jz      short loc_18001C510
0x18001c4d1  cmp     dword ptr [rcx+2Ch], 5
0x18001c4d5  jb      short loc_18001C510
0x18001c4d7  movups  [rbp+57h+var_76], xmm0
0x18001c4db  lea     eax, [r15+2Fh]
0x18001c4df  movups  [rbp+57h+var_86], xmm0
0x18001c4e3  mov     [rbp+57h+var_88], ax
0x18001c4e7  lea     rdx, [rbp+57h+var_88]
0x18001c4eb  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISStartupEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISStartupEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001c4f2  mov     word ptr [rbp+57h+var_86+4], r15w
0x18001c4f7  movups  [rbp+57h+var_76+0Eh], xmm0
0x18001c4fb  mov     qword ptr [rbp+57h+var_76+6], rax
0x18001c4ff  mov     [rbp+57h+var_5C], 1A0000h
0x18001c506  mov     byte ptr [rbp+57h+var_86+2], 12h
0x18001c50a  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001c510  mov     ebx, [rsi+224h]
0x18001c516  lea     rax, ?OnNewRequest@W3_MAIN_CONTEXT@@SA?AW4NREQ_STATUS@@PEAX@Z; W3_MAIN_CONTEXT::OnNewRequest(void *)
0x18001c51d  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18001c521  lea     rcx, [rsi+1A8h]
0x18001c528  lea     rax, ?OnIoCompletion@W3_MAIN_CONTEXT@@SA?AW4NREQ_STATUS@@KPEAXKKPEAU_OVERLAPPED@@@Z; W3_MAIN_CONTEXT::OnIoCompletion(ulong,void *,ulong,ulong,_OVERLAPPED *)
0x18001c52f  mov     qword ptr [rbp+57h+var_A0], rax
0x18001c533  lea     rax, ?OnDisconnect@W3_CONNECTION@@SAXPEAX@Z; W3_CONNECTION::OnDisconnect(void *)
0x18001c53a  mov     [rbp+57h+var_90], rax
0x18001c53e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001c544  lea     r14, [rsi+170h]
0x18001c54b  mov     rdi, rax
0x18001c54e  mov     rcx, r14
0x18001c551  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001c557  lea     rcx, [rbp+57h+var_A0]
0x18001c55b  mov     [rsp+0F0h+var_C0], 2520h
0x18001c563  mov     [rsp+0F0h+var_C8], ebx
0x18001c567  xor     r9d, r9d
0x18001c56a  mov     [rsp+0F0h+var_D0], rcx
0x18001c56f  xor     r8d, r8d
0x18001c572  mov     rcx, rax
0x18001c575  mov     rdx, rdi
0x18001c578  call    cs:__imp_?UlAtqInitialize@@YAJPEBG0PEAVMULTISZ@@KPEAU_ULATQ_CONFIG@@HK@Z; UlAtqInitialize(ushort const *,ushort const *,MULTISZ *,ulong,_ULATQ_CONFIG *,int,ulong)
0x18001c57e  mov     ebx, eax
0x18001c580  test    eax, eax
0x18001c582  jns     loc_18001C615
0x18001c588  test    byte ptr cs:g_dwDebugFlags, 3
0x18001c58f  jz      short loc_18001C5C2
0x18001c591  mov     rcx, cs:g_pDebug
0x18001c598  lea     r9, aW3ServerInitia_2; "W3_SERVER::InitializeUlAtq"
0x18001c59f  mov     [rsp+0F0h+var_C8], eax
0x18001c5a3  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001c5aa  lea     rax, aErrorInitializ_0; "Error initializing ULATQ.  hr = %x\n"
0x18001c5b1  mov     r8d, 36Ch
0x18001c5b7  mov     [rsp+0F0h+var_D0], rax
0x18001c5bc  call    cs:__imp_PuDbgPrint
0x18001c5c2  call    cs:__imp_GetCurrentProcessId
0x18001c5c8  mov     r9d, 0Ah; Radix
0x18001c5ce  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001c5d2  mov     ecx, eax; Value
0x18001c5d4  lea     r8d, [r9+1]; BufferCount
0x18001c5d8  call    cs:__imp__ultow_s
0x18001c5de  mov     rcx, r14
0x18001c5e1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001c5e7  mov     r8d, 2
0x18001c5ed  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18001c5f1  mov     qword ptr [rbp+57h+var_B0], rax
0x18001c5f5  lea     rcx, [rsi+1Ch]
0x18001c5f9  lea     rax, [rbp+57h+Buffer]
0x18001c5fd  mov     edx, 0C00008DDh
0x18001c602  lea     r9, [rbp+57h+var_B0]
0x18001c606  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18001c60a  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001c610  jmp     loc_18001C6BC
0x18001c615  lea     rcx, [rsi+698h]
0x18001c61c  call    cs:__imp_?UlAtqDuplicateRequestQueueHandle@@YAJPEAPEAX@Z; UlAtqDuplicateRequestQueueHandle(void * *)
0x18001c622  mov     ebx, eax
0x18001c624  test    eax, eax
0x18001c626  jns     loc_18001C6B5
0x18001c62c  test    byte ptr cs:g_dwDebugFlags, 3
0x18001c633  jz      short loc_18001C666
0x18001c635  mov     rcx, cs:g_pDebug
0x18001c63c  lea     r9, aW3ServerInitia_2; "W3_SERVER::InitializeUlAtq"
0x18001c643  mov     [rsp+0F0h+var_C8], eax
0x18001c647  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001c64e  lea     rax, aErrorDuplicati; "Error duplicating the request queue han"...
0x18001c655  mov     r8d, 386h
0x18001c65b  mov     [rsp+0F0h+var_D0], rax
0x18001c660  call    cs:__imp_PuDbgPrint
0x18001c666  call    cs:__imp_GetCurrentProcessId
0x18001c66c  mov     r8d, 0Bh; BufferCount
0x18001c672  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001c676  mov     r9d, r8d; Radix
0x18001c679  mov     ecx, eax; Value
0x18001c67b  call    cs:__imp__ultow_s
0x18001c681  mov     rcx, r14
0x18001c684  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001c68a  mov     r8d, 2
0x18001c690  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18001c694  mov     qword ptr [rbp+57h+var_B0], rax
0x18001c698  lea     rcx, [rsi+1Ch]
0x18001c69c  lea     rax, [rbp+57h+Buffer]
0x18001c6a0  mov     edx, 0C0000907h
0x18001c6a5  lea     r9, [rbp+57h+var_B0]
0x18001c6a9  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18001c6ad  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001c6b3  xor     ebx, ebx
0x18001c6b5  mov     [rsi+620h], r15d
0x18001c6bc  mov     eax, ebx
0x18001c6be  mov     rcx, [rbp+57h+var_40]
0x18001c6c2  xor     rcx, rsp; StackCookie
0x18001c6c5  call    __security_check_cookie
0x18001c6ca  add     rsp, 0C8h
0x18001c6d1  pop     r15
0x18001c6d3  pop     r14
0x18001c6d5  pop     rdi
0x18001c6d6  pop     rsi
0x18001c6d7  pop     rbx
0x18001c6d8  pop     rbp
0x18001c6d9  retn
```
