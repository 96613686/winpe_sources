# CDirMonitorEntry::~CDirMonitorEntry(void)

- ea: `0x1800361cc`
- end: `0x1800362ee`
- name: `??1CDirMonitorEntry@@UEAA@XZ`
- size: `290`
- prototype: `void __fastcall(CDirMonitorEntry *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001be58`
- `0x180036300`

## callees

- `0x1800361cc`
- `0x1800366b4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036282`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036282`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362d4`
- `iisutil!PuDbgPrint` at `0x18003621d`
- `iisutil!PuDbgPrint` at `0x18003626a`
- `iisutil!PuDbgPrint` at `0x18003621d`
- `iisutil!PuDbgPrint` at `0x18003626a`

## string_xrefs

- `0x180036216`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x180036251`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x180036258`: `~CDirMonitorEntry: open handle %p\n`

## pseudocode

```c
void __fastcall CDirMonitorEntry::~CDirMonitorEntry(const void **this)
{
  char v2; // cl
  void *v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  *this = &CDirMonitorEntry::`vftable';
  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
      124,
      "CDirMonitorEntry::~CDirMonitorEntry",
      "[CDirMonitorEntry] Destructor\n");
    v2 = g_dwDebugFlags;
  }
  if ( this[5] != (const void *)-1LL )
  {
    if ( (v2 & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
        139,
        "CDirMonitorEntry::~CDirMonitorEntry",
        "~CDirMonitorEntry: open handle %p\n",
        this[5]);
    v3 = (void *)this[5];
    this[5] = (const void *)-1LL;
    CloseHandle(v3);
  }
  v4 = (__int64)this[12];
  if ( v4 )
  {
    CDirMonitor::RemoveEntry(v4, (__int64)this);
    this[12] = 0;
  }
  v5 = (void *)this[2];
  *((_DWORD *)this + 2) = 0;
  if ( v5 )
  {
    LocalFree(v5);
    this[2] = 0;
  }
  v6 = (void *)this[3];
  if ( v6 )
  {
    LocalFree(v6);
    *((_DWORD *)this + 22) = 0;
  }
}

```

## disassembly

```asm
0x1800361cc  push    rbx
0x1800361ce  sub     rsp, 30h
0x1800361d2  lea     rax, ??_7CDirMonitorEntry@@6B@; const CDirMonitorEntry::`vftable'
0x1800361d9  mov     rbx, rcx
0x1800361dc  mov     [rcx], rax
0x1800361df  mov     ecx, cs:g_dwDebugFlags
0x1800361e5  test    cl, 3
0x1800361e8  setnz   dl
0x1800361eb  bt      ecx, 10h
0x1800361ef  setb    al
0x1800361f2  test    al, dl
0x1800361f4  jz      short loc_18003622F
0x1800361f6  mov     rcx, cs:g_pDebug
0x1800361fd  lea     rax, aCdirmonitorent; "[CDirMonitorEntry] Destructor\n"
0x180036204  lea     r9, aCdirmonitorent_1; "CDirMonitorEntry::~CDirMonitorEntry"
0x18003620b  mov     [rsp+38h+var_18], rax
0x180036210  mov     r8d, 7Ch ; '|'
0x180036216  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003621d  call    cs:__imp_PuDbgPrint
0x180036224  nop     dword ptr [rax+rax+00h]
0x180036229  mov     ecx, cs:g_dwDebugFlags
0x18003622f  mov     rax, [rbx+28h]
0x180036233  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036237  jz      short loc_18003628E
0x180036239  test    cl, 3
0x18003623c  jz      short loc_180036276
0x18003623e  mov     rcx, cs:g_pDebug
0x180036245  lea     r9, aCdirmonitorent_1; "CDirMonitorEntry::~CDirMonitorEntry"
0x18003624c  mov     [rsp+38h+var_10], rax
0x180036251  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180036258  lea     rax, aCdirmonitorent_3; "~CDirMonitorEntry: open handle %p\n"
0x18003625f  mov     r8d, 8Bh
0x180036265  mov     [rsp+38h+var_18], rax
0x18003626a  call    cs:__imp_PuDbgPrint
0x180036271  nop     dword ptr [rax+rax+00h]
0x180036276  mov     rcx, [rbx+28h]; hObject
0x18003627a  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x180036282  call    cs:__imp_CloseHandle
0x180036289  nop     dword ptr [rax+rax+00h]
0x18003628e  mov     rcx, [rbx+60h]
0x180036292  test    rcx, rcx
0x180036295  jz      short loc_1800362A7
0x180036297  mov     rdx, rbx
0x18003629a  call    ?RemoveEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z; CDirMonitor::RemoveEntry(CDirMonitorEntry *)
0x18003629f  mov     qword ptr [rbx+60h], 0
0x1800362a7  mov     rcx, [rbx+10h]; hMem
0x1800362ab  mov     dword ptr [rbx+8], 0
0x1800362b2  test    rcx, rcx
0x1800362b5  jz      short loc_1800362CB
0x1800362b7  call    cs:__imp_LocalFree
0x1800362be  nop     dword ptr [rax+rax+00h]
0x1800362c3  mov     qword ptr [rbx+10h], 0
0x1800362cb  mov     rcx, [rbx+18h]; hMem
0x1800362cf  test    rcx, rcx
0x1800362d2  jz      short loc_1800362E7
0x1800362d4  call    cs:__imp_LocalFree
0x1800362db  nop     dword ptr [rax+rax+00h]
0x1800362e0  mov     dword ptr [rbx+58h], 0
0x1800362e7  add     rsp, 30h
0x1800362eb  pop     rbx
0x1800362ec  retn
```
