# W3_SERVER::InitializeUlAtq(void)

- ea: `0x18001dd3c`
- end: `0x18001dff1`
- name: `?InitializeUlAtq@W3_SERVER@@QEAAJXZ`
- size: `693`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034190`

## callees

- `0x18001dd3c`
- `0x180037790`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18001deb8`
- `msvcrt!_ultow_s` at `0x18001df7f`
- `msvcrt!_ultow_s` at `0x18001deb8`
- `msvcrt!_ultow_s` at `0x18001df7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001de9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001df64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001de9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001df64`
- `iisutil!PuDbgPrint` at `0x18001de90`
- `iisutil!PuDbgPrint` at `0x18001df58`
- `iisutil!PuDbgPrint` at `0x18001de90`
- `iisutil!PuDbgPrint` at `0x18001df58`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001ddc6`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001ddc6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001de00`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001de19`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001dec7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001df8e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001de00`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001de19`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001dec7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001df8e`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001def6`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001dfbd`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001def6`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001dfbd`
- `w3dt!UlAtqDuplicateRequestQueueHandle` at `0x18001df0e`
- `w3dt!UlAtqDuplicateRequestQueueHandle` at `0x18001df0e`
- `w3dt!UlAtqInitialize` at `0x18001de46`
- `w3dt!UlAtqInitialize` at `0x18001de46`

## string_xrefs

- `0x18001de77`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`
- `0x18001df3f`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`

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
0x18001dd3c  push    rbp
0x18001dd3e  push    rbx
0x18001dd3f  push    rsi
0x18001dd40  push    rdi
0x18001dd41  push    r14
0x18001dd43  push    r15
0x18001dd45  lea     rbp, [rsp-2Fh]
0x18001dd4a  sub     rsp, 0C8h
0x18001dd51  mov     rax, cs:__security_cookie
0x18001dd58  xor     rax, rsp
0x18001dd5b  mov     [rbp+57h+var_40], rax
0x18001dd5f  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x18001dd66  xor     eax, eax
0x18001dd68  mov     rsi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001dd6f  xorps   xmm0, xmm0
0x18001dd72  movups  [rbp+57h+var_A0], xmm0
0x18001dd76  mov     [rbp+57h+var_90], rax
0x18001dd7a  lea     r15d, [rax+1]
0x18001dd7e  movups  [rbp+57h+var_B0], xmm0
0x18001dd82  cmp     [rcx+8], eax
0x18001dd85  jz      short loc_18001DDD2
0x18001dd87  test    [rcx+28h], r15b
0x18001dd8b  jz      short loc_18001DDD2
0x18001dd8d  cmp     dword ptr [rcx+2Ch], 5
0x18001dd91  jb      short loc_18001DDD2
0x18001dd93  movups  [rbp+57h+var_76], xmm0
0x18001dd97  lea     eax, [r15+2Fh]
0x18001dd9b  movups  [rbp+57h+var_86], xmm0
0x18001dd9f  mov     [rbp+57h+var_88], ax
0x18001dda3  lea     rdx, [rbp+57h+var_88]
0x18001dda7  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISStartupEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISStartupEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001ddae  mov     word ptr [rbp+57h+var_86+4], r15w
0x18001ddb3  movups  [rbp+57h+var_76+0Eh], xmm0
0x18001ddb7  mov     qword ptr [rbp+57h+var_76+6], rax
0x18001ddbb  mov     [rbp+57h+var_5C], 1A0000h
0x18001ddc2  mov     byte ptr [rbp+57h+var_86+2], 12h
0x18001ddc6  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001ddcd  nop     dword ptr [rax+rax+00h]
0x18001ddd2  mov     ebx, [rsi+224h]
0x18001ddd8  lea     rax, ?OnNewRequest@W3_MAIN_CONTEXT@@SA?AW4NREQ_STATUS@@PEAX@Z; W3_MAIN_CONTEXT::OnNewRequest(void *)
0x18001dddf  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18001dde3  lea     rcx, [rsi+1A8h]
0x18001ddea  lea     rax, ?OnIoCompletion@W3_MAIN_CONTEXT@@SA?AW4NREQ_STATUS@@KPEAXKKPEAU_OVERLAPPED@@@Z; W3_MAIN_CONTEXT::OnIoCompletion(ulong,void *,ulong,ulong,_OVERLAPPED *)
0x18001ddf1  mov     qword ptr [rbp+57h+var_A0], rax
0x18001ddf5  lea     rax, ?OnDisconnect@W3_CONNECTION@@SAXPEAX@Z; W3_CONNECTION::OnDisconnect(void *)
0x18001ddfc  mov     [rbp+57h+var_90], rax
0x18001de00  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001de07  nop     dword ptr [rax+rax+00h]
0x18001de0c  lea     r14, [rsi+170h]
0x18001de13  mov     rdi, rax
0x18001de16  mov     rcx, r14
0x18001de19  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001de20  nop     dword ptr [rax+rax+00h]
0x18001de25  lea     rcx, [rbp+57h+var_A0]
0x18001de29  mov     [rsp+0F0h+var_C0], 2520h
0x18001de31  mov     [rsp+0F0h+var_C8], ebx
0x18001de35  xor     r9d, r9d
0x18001de38  mov     [rsp+0F0h+var_D0], rcx
0x18001de3d  xor     r8d, r8d
0x18001de40  mov     rcx, rax
0x18001de43  mov     rdx, rdi
0x18001de46  call    cs:__imp_?UlAtqInitialize@@YAJPEBG0PEAVMULTISZ@@KPEAU_ULATQ_CONFIG@@HK@Z; UlAtqInitialize(ushort const *,ushort const *,MULTISZ *,ulong,_ULATQ_CONFIG *,int,ulong)
0x18001de4d  nop     dword ptr [rax+rax+00h]
0x18001de52  mov     ebx, eax
0x18001de54  test    eax, eax
0x18001de56  jns     loc_18001DF07
0x18001de5c  test    byte ptr cs:g_dwDebugFlags, 3
0x18001de63  jz      short loc_18001DE9C
0x18001de65  mov     rcx, cs:g_pDebug
0x18001de6c  lea     r9, aW3ServerInitia_2; "W3_SERVER::InitializeUlAtq"
0x18001de73  mov     [rsp+0F0h+var_C8], eax
0x18001de77  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001de7e  lea     rax, aErrorInitializ_0; "Error initializing ULATQ.  hr = %x\n"
0x18001de85  mov     r8d, 36Ch
0x18001de8b  mov     [rsp+0F0h+var_D0], rax
0x18001de90  call    cs:__imp_PuDbgPrint
0x18001de97  nop     dword ptr [rax+rax+00h]
0x18001de9c  call    cs:__imp_GetCurrentProcessId
0x18001dea3  nop     dword ptr [rax+rax+00h]
0x18001dea8  mov     r9d, 0Ah; Radix
0x18001deae  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001deb2  mov     ecx, eax; Value
0x18001deb4  lea     r8d, [r9+1]; BufferCount
0x18001deb8  call    cs:__imp__ultow_s
0x18001debf  nop     dword ptr [rax+rax+00h]
0x18001dec4  mov     rcx, r14
0x18001dec7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001dece  nop     dword ptr [rax+rax+00h]
0x18001ded3  mov     r8d, 2
0x18001ded9  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18001dedd  mov     qword ptr [rbp+57h+var_B0], rax
0x18001dee1  lea     rcx, [rsi+1Ch]
0x18001dee5  lea     rax, [rbp+57h+Buffer]
0x18001dee9  mov     edx, 0C00008DDh
0x18001deee  lea     r9, [rbp+57h+var_B0]
0x18001def2  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18001def6  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001defd  nop     dword ptr [rax+rax+00h]
0x18001df02  jmp     loc_18001DFD2
0x18001df07  lea     rcx, [rsi+698h]
0x18001df0e  call    cs:__imp_?UlAtqDuplicateRequestQueueHandle@@YAJPEAPEAX@Z; UlAtqDuplicateRequestQueueHandle(void * *)
0x18001df15  nop     dword ptr [rax+rax+00h]
0x18001df1a  mov     ebx, eax
0x18001df1c  test    eax, eax
0x18001df1e  jns     loc_18001DFCB
0x18001df24  test    byte ptr cs:g_dwDebugFlags, 3
0x18001df2b  jz      short loc_18001DF64
0x18001df2d  mov     rcx, cs:g_pDebug
0x18001df34  lea     r9, aW3ServerInitia_2; "W3_SERVER::InitializeUlAtq"
0x18001df3b  mov     [rsp+0F0h+var_C8], eax
0x18001df3f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001df46  lea     rax, aErrorDuplicati; "Error duplicating the request queue han"...
0x18001df4d  mov     r8d, 386h
0x18001df53  mov     [rsp+0F0h+var_D0], rax
0x18001df58  call    cs:__imp_PuDbgPrint
0x18001df5f  nop     dword ptr [rax+rax+00h]
0x18001df64  call    cs:__imp_GetCurrentProcessId
0x18001df6b  nop     dword ptr [rax+rax+00h]
0x18001df70  mov     r8d, 0Bh; BufferCount
0x18001df76  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001df7a  mov     r9d, r8d; Radix
0x18001df7d  mov     ecx, eax; Value
0x18001df7f  call    cs:__imp__ultow_s
0x18001df86  nop     dword ptr [rax+rax+00h]
0x18001df8b  mov     rcx, r14
0x18001df8e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001df95  nop     dword ptr [rax+rax+00h]
0x18001df9a  mov     r8d, 2
0x18001dfa0  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18001dfa4  mov     qword ptr [rbp+57h+var_B0], rax
0x18001dfa8  lea     rcx, [rsi+1Ch]
0x18001dfac  lea     rax, [rbp+57h+Buffer]
0x18001dfb0  mov     edx, 0C0000907h
0x18001dfb5  lea     r9, [rbp+57h+var_B0]
0x18001dfb9  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18001dfbd  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001dfc4  nop     dword ptr [rax+rax+00h]
0x18001dfc9  xor     ebx, ebx
0x18001dfcb  mov     [rsi+620h], r15d
0x18001dfd2  mov     eax, ebx
0x18001dfd4  mov     rcx, [rbp+57h+var_40]
0x18001dfd8  xor     rcx, rsp; StackCookie
0x18001dfdb  call    __security_check_cookie
0x18001dfe0  add     rsp, 0C8h
0x18001dfe7  pop     r15
0x18001dfe9  pop     r14
0x18001dfeb  pop     rdi
0x18001dfec  pop     rsi
0x18001dfed  pop     rbx
0x18001dfee  pop     rbp
0x18001dfef  retn
```
