# GlobalDoWork(ulong,IHttpEventProvider *)

- ea: `0x180001b20`
- end: `0x180001c3c`
- name: `?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `284`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180001eb0`
- `0x180001ec0`

## callees

- `0x180001048`
- `0x180001b20`
- `0x180003140`
- `0x180008010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001b51`
- `msvcrt!_wcsicmp` at `0x180001b51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c29`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001b66`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001b66`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001b9b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001b9b`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001b7b`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001b7b`
- `iisutil!PuDbgPrint` at `0x180001be9`
- `iisutil!PuDbgPrint` at `0x180001be9`

## string_xrefs

- `0x180001be2`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`

## pseudocode

```c
__int64 __fastcall GlobalDoWork(int a1, __int64 a2)
{
  const wchar_t *v2; // rax
  void *v3; // rbx
  struct _LIST_ENTRY *i; // rbx

  if ( a1 == 2 )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
          2513,
          "W3_CGI_HANDLER::KillAllCgis",
          "W3_CGI_HANDLER::KillAllCgis() called\n");
      EnterCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
      for ( i = W3_CGI_HANDLER::sm_CgiListHead.Flink; i != &W3_CGI_HANDLER::sm_CgiListHead; i = i->Flink )
        W3_CGI_HANDLER::CGITerminateProcess(&i[-522].Blink, 0);
      LeaveCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
    }
  }
  else if ( a1 == 64 )
  {
    v2 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    if ( !_wcsicmp(v2, L"MACHINE/WEBROOT/APPHOST") )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
      v3 = W3_RESTRICTION_LIST::sm_pRestrictionList;
      if ( W3_RESTRICTION_LIST::sm_pRestrictionList )
      {
        CLKRHashTable::~CLKRHashTable((CLKRHashTable *)W3_RESTRICTION_LIST::sm_pRestrictionList);
        operator delete(v3);
        W3_RESTRICTION_LIST::sm_pRestrictionList = 0;
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001b20  mov     [rsp+arg_0], rbx
0x180001b25  push    rdi
0x180001b26  sub     rsp, 30h
0x180001b2a  cmp     ecx, 2
0x180001b2d  jz      short loc_180001BA6
0x180001b2f  cmp     ecx, 40h ; '@'
0x180001b32  jnz     loc_180001C2F
0x180001b38  mov     rax, [rdx]
0x180001b3b  mov     rcx, rdx
0x180001b3e  mov     rax, [rax+8]
0x180001b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b47  mov     rcx, rax; String1
0x180001b4a  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180001b51  call    cs:__imp__wcsicmp
0x180001b57  test    eax, eax
0x180001b59  jnz     loc_180001C2F
0x180001b5f  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180001b66  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180001b6c  mov     rbx, cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180001b73  test    rbx, rbx
0x180001b76  jz      short loc_180001B94
0x180001b78  mov     rcx, rbx
0x180001b7b  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180001b81  mov     rcx, rbx; Block
0x180001b84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001b89  mov     cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA, 0; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180001b94  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180001b9b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001ba1  jmp     loc_180001C2F
0x180001ba6  mov     rax, [rdx]
0x180001ba9  mov     rcx, rdx
0x180001bac  mov     rax, [rax+8]
0x180001bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bb5  test    eax, eax
0x180001bb7  jnz     short loc_180001C2F
0x180001bb9  test    cs:g_dwDebugFlags, 3
0x180001bc0  jz      short loc_180001BEF
0x180001bc2  mov     rcx, cs:g_pDebug
0x180001bc9  lea     rax, aW3CgiHandlerKi; "W3_CGI_HANDLER::KillAllCgis() called\n"
0x180001bd0  lea     r9, aW3CgiHandlerKi_0; "W3_CGI_HANDLER::KillAllCgis"
0x180001bd7  mov     [rsp+38h+var_18], rax
0x180001bdc  mov     r8d, 9D1h
0x180001be2  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001be9  call    cs:__imp_PuDbgPrint
0x180001bef  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001bf6  call    cs:__imp_EnterCriticalSection
0x180001bfc  mov     rbx, cs:?sm_CgiListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY W3_CGI_HANDLER::sm_CgiListHead
0x180001c03  lea     rdi, ?sm_CgiListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY W3_CGI_HANDLER::sm_CgiListHead
0x180001c0a  jmp     short loc_180001C1D
0x180001c0c  lea     rcx, [rbx-2098h]; PVOID
0x180001c13  xor     edx, edx; BOOLEAN
0x180001c15  call    ?CGITerminateProcess@W3_CGI_HANDLER@@CAXPEAXE@Z; W3_CGI_HANDLER::CGITerminateProcess(void *,uchar)
0x180001c1a  mov     rbx, [rbx]
0x180001c1d  cmp     rbx, rdi
0x180001c20  jnz     short loc_180001C0C
0x180001c22  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001c29  call    cs:__imp_LeaveCriticalSection
0x180001c2f  mov     rbx, [rsp+38h+arg_0]
0x180001c34  xor     eax, eax
0x180001c36  add     rsp, 30h
0x180001c3a  pop     rdi
0x180001c3b  retn
```
