# CDirMonitorEntry::RequestNotification(void)

- ea: `0x180036748`
- end: `0x18003680f`
- name: `?RequestNotification@CDirMonitorEntry@@AEAAHXZ`
- size: `199`
- prototype: `__int64 __fastcall(CDirMonitorEntry *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001869c`
- `0x18003649c`

## callees

- `0x1800187fc`
- `0x180036748`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18003679a`
- `iisutil!PuDbgPrint` at `0x18003679a`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x1800367e7`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x1800367e7`

## string_xrefs

- `0x180036793`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`

## pseudocode

```c
__int64 __fastcall CDirMonitorEntry::RequestNotification(CDirMonitorEntry *this)
{
  unsigned int v2; // edi
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  BytesReturned = 0;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
      237,
      "CDirMonitorEntry::RequestNotification",
      "[CDirMonitorEntry] Request change notification\n");
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 9);
  v2 = ReadDirectoryChangesW(
         *((HANDLE *)this + 5),
         *((LPVOID *)this + 3),
         *((_DWORD *)this + 22),
         *((_DWORD *)this + 12),
         *((_DWORD *)this + 13),
         &BytesReturned,
         (LPOVERLAPPED)((char *)this + 56),
         0);
  if ( !v2 )
    CDirMonitorEntry::IORelease(this);
  return v2;
}

```

## disassembly

```asm
0x180036748  mov     [rsp+arg_8], rbx
0x18003674d  push    rdi
0x18003674e  sub     rsp, 40h
0x180036752  mov     eax, cs:g_dwDebugFlags
0x180036758  mov     rbx, rcx
0x18003675b  test    al, 3
0x18003675d  mov     [rsp+48h+BytesReturned], 0
0x180036765  setnz   dl
0x180036768  bt      eax, 10h
0x18003676c  setb    al
0x18003676f  test    al, dl
0x180036771  jz      short loc_1800367A6
0x180036773  mov     rcx, cs:g_pDebug
0x18003677a  lea     rax, aCdirmonitorent_0; "[CDirMonitorEntry] Request change notif"...
0x180036781  lea     r9, aCdirmonitorent_2; "CDirMonitorEntry::RequestNotification"
0x180036788  mov     qword ptr [rsp+48h+dwNotifyFilter], rax
0x18003678d  mov     r8d, 0EDh
0x180036793  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003679a  call    cs:__imp_PuDbgPrint
0x1800367a1  nop     dword ptr [rax+rax+00h]
0x1800367a6  lea     rax, [rbx+38h]
0x1800367aa  xorps   xmm0, xmm0
0x1800367ad  movups  xmmword ptr [rax], xmm0
0x1800367b0  movups  xmmword ptr [rax+10h], xmm0
0x1800367b4  lock inc dword ptr [rbx+24h]
0x1800367b8  mov     r9d, [rbx+30h]; bWatchSubtree
0x1800367bc  mov     r8d, [rbx+58h]; nBufferLength
0x1800367c0  mov     rdx, [rbx+18h]; lpBuffer
0x1800367c4  mov     rcx, [rbx+28h]; hDirectory
0x1800367c8  mov     [rsp+48h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800367d1  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x1800367d6  lea     rax, [rsp+48h+BytesReturned]
0x1800367db  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x1800367e0  mov     eax, [rbx+34h]
0x1800367e3  mov     [rsp+48h+dwNotifyFilter], eax; dwNotifyFilter
0x1800367e7  call    cs:__imp_ReadDirectoryChangesW
0x1800367ee  nop     dword ptr [rax+rax+00h]
0x1800367f3  mov     edi, eax
0x1800367f5  test    eax, eax
0x1800367f7  jnz     short loc_180036801
0x1800367f9  mov     rcx, rbx; this
0x1800367fc  call    ?IORelease@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::IORelease(void)
0x180036801  mov     rbx, [rsp+48h+arg_8]
0x180036806  mov     eax, edi
0x180036808  add     rsp, 40h
0x18003680c  pop     rdi
0x18003680d  retn
```
