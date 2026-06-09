# CDirMonitorEntry::RequestNotification(void)

- ea: `0x180033508`
- end: `0x1800335c2`
- name: `?RequestNotification@CDirMonitorEntry@@AEAAHXZ`
- size: `186`
- prototype: `__int64 __fastcall(CDirMonitorEntry *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800172b4`
- `0x1800332a8`

## callees

- `0x1800173fc`
- `0x180033508`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18003355a`
- `iisutil!PuDbgPrint` at `0x18003355a`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x1800335a1`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x1800335a1`

## string_xrefs

- `0x180033553`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`

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
0x180033508  mov     [rsp+arg_8], rbx
0x18003350d  push    rdi
0x18003350e  sub     rsp, 40h
0x180033512  mov     eax, cs:g_dwDebugFlags
0x180033518  mov     rbx, rcx
0x18003351b  test    al, 3
0x18003351d  mov     [rsp+48h+BytesReturned], 0
0x180033525  setnz   dl
0x180033528  bt      eax, 10h
0x18003352c  setb    al
0x18003352f  test    al, dl
0x180033531  jz      short loc_180033560
0x180033533  mov     rcx, cs:g_pDebug
0x18003353a  lea     rax, aCdirmonitorent_0; "[CDirMonitorEntry] Request change notif"...
0x180033541  lea     r9, aCdirmonitorent_2; "CDirMonitorEntry::RequestNotification"
0x180033548  mov     qword ptr [rsp+48h+dwNotifyFilter], rax
0x18003354d  mov     r8d, 0EDh
0x180033553  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003355a  call    cs:__imp_PuDbgPrint
0x180033560  lea     rax, [rbx+38h]
0x180033564  xorps   xmm0, xmm0
0x180033567  movups  xmmword ptr [rax], xmm0
0x18003356a  movups  xmmword ptr [rax+10h], xmm0
0x18003356e  lock inc dword ptr [rbx+24h]
0x180033572  mov     r9d, [rbx+30h]; bWatchSubtree
0x180033576  mov     r8d, [rbx+58h]; nBufferLength
0x18003357a  mov     rdx, [rbx+18h]; lpBuffer
0x18003357e  mov     rcx, [rbx+28h]; hDirectory
0x180033582  mov     [rsp+48h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18003358b  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x180033590  lea     rax, [rsp+48h+BytesReturned]
0x180033595  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18003359a  mov     eax, [rbx+34h]
0x18003359d  mov     [rsp+48h+dwNotifyFilter], eax; dwNotifyFilter
0x1800335a1  call    cs:__imp_ReadDirectoryChangesW
0x1800335a7  mov     edi, eax
0x1800335a9  test    eax, eax
0x1800335ab  jnz     short loc_1800335B5
0x1800335ad  mov     rcx, rbx; this
0x1800335b0  call    ?IORelease@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::IORelease(void)
0x1800335b5  mov     rbx, [rsp+48h+arg_8]
0x1800335ba  mov     eax, edi
0x1800335bc  add     rsp, 40h
0x1800335c0  pop     rdi
0x1800335c1  retn
```
