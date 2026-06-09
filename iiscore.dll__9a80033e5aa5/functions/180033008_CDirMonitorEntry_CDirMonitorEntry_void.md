# CDirMonitorEntry::~CDirMonitorEntry(void)

- ea: `0x180033008`
- end: `0x18003310b`
- name: `??1CDirMonitorEntry@@UEAA@XZ`
- size: `259`
- prototype: `void __fastcall(CDirMonitorEntry *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a7d0`
- `0x180033120`

## callees

- `0x180033008`
- `0x180033480`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800330b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800330b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330f8`
- `iisutil!PuDbgPrint` at `0x180033059`
- `iisutil!PuDbgPrint` at `0x1800330a0`
- `iisutil!PuDbgPrint` at `0x180033059`
- `iisutil!PuDbgPrint` at `0x1800330a0`

## string_xrefs

- `0x180033052`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x180033087`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x18003308e`: `~CDirMonitorEntry: open handle %p\n`

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
0x180033008  push    rbx
0x18003300a  sub     rsp, 30h
0x18003300e  lea     rax, ??_7CDirMonitorEntry@@6B@; const CDirMonitorEntry::`vftable'
0x180033015  mov     rbx, rcx
0x180033018  mov     [rcx], rax
0x18003301b  mov     ecx, cs:g_dwDebugFlags
0x180033021  test    cl, 3
0x180033024  setnz   dl
0x180033027  bt      ecx, 10h
0x18003302b  setb    al
0x18003302e  test    al, dl
0x180033030  jz      short loc_180033065
0x180033032  mov     rcx, cs:g_pDebug
0x180033039  lea     rax, aCdirmonitorent; "[CDirMonitorEntry] Destructor\n"
0x180033040  lea     r9, aCdirmonitorent_1; "CDirMonitorEntry::~CDirMonitorEntry"
0x180033047  mov     [rsp+38h+var_18], rax
0x18003304c  mov     r8d, 7Ch ; '|'
0x180033052  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180033059  call    cs:__imp_PuDbgPrint
0x18003305f  mov     ecx, cs:g_dwDebugFlags
0x180033065  mov     rax, [rbx+28h]
0x180033069  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003306d  jz      short loc_1800330B8
0x18003306f  test    cl, 3
0x180033072  jz      short loc_1800330A6
0x180033074  mov     rcx, cs:g_pDebug
0x18003307b  lea     r9, aCdirmonitorent_1; "CDirMonitorEntry::~CDirMonitorEntry"
0x180033082  mov     [rsp+38h+var_10], rax
0x180033087  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003308e  lea     rax, aCdirmonitorent_3; "~CDirMonitorEntry: open handle %p\n"
0x180033095  mov     r8d, 8Bh
0x18003309b  mov     [rsp+38h+var_18], rax
0x1800330a0  call    cs:__imp_PuDbgPrint
0x1800330a6  mov     rcx, [rbx+28h]; hObject
0x1800330aa  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x1800330b2  call    cs:__imp_CloseHandle
0x1800330b8  mov     rcx, [rbx+60h]
0x1800330bc  test    rcx, rcx
0x1800330bf  jz      short loc_1800330D1
0x1800330c1  mov     rdx, rbx
0x1800330c4  call    ?RemoveEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z; CDirMonitor::RemoveEntry(CDirMonitorEntry *)
0x1800330c9  mov     qword ptr [rbx+60h], 0
0x1800330d1  mov     rcx, [rbx+10h]; hMem
0x1800330d5  mov     dword ptr [rbx+8], 0
0x1800330dc  test    rcx, rcx
0x1800330df  jz      short loc_1800330EF
0x1800330e1  call    cs:__imp_LocalFree
0x1800330e7  mov     qword ptr [rbx+10h], 0
0x1800330ef  mov     rcx, [rbx+18h]; hMem
0x1800330f3  test    rcx, rcx
0x1800330f6  jz      short loc_180033105
0x1800330f8  call    cs:__imp_LocalFree
0x1800330fe  mov     dword ptr [rbx+58h], 0
0x180033105  add     rsp, 30h
0x180033109  pop     rbx
0x18003310a  retn
```
