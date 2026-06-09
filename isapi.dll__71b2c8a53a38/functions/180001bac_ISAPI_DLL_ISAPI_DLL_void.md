# ISAPI_DLL::~ISAPI_DLL(void)

- ea: `0x180001bac`
- end: `0x180001c7d`
- name: `??1ISAPI_DLL@@AEAA@XZ`
- size: `209`
- prototype: `void __fastcall(ISAPI_DLL *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ddc`

## callees

- `0x180001bac`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001c08`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001c08`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001bfe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001bfe`
- `iisutil!PuDbgPrint` at `0x180001c50`
- `iisutil!PuDbgPrint` at `0x180001c50`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001c5d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001c5d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c67`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c67`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c76`

## string_xrefs

- `0x180001c2b`: `Deleted ISAPI_DLL %p.\n`
- `0x180001c37`: `ISAPI_DLL::~ISAPI_DLL`
- `0x180001c49`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.h`

## pseudocode

```c
void __fastcall ISAPI_DLL::~ISAPI_DLL(struct _RTL_CRITICAL_SECTION *this)
{
  void (__fastcall *OwningThread)(__int64); // rax
  HMODULE SpinCount; // rcx

  OwningThread = (void (__fastcall *)(__int64))this[4].OwningThread;
  LODWORD(this->DebugInfo) = 1715753801;
  if ( OwningThread )
  {
    OwningThread(2);
    this[4].OwningThread = 0;
  }
  SpinCount = (HMODULE)this[4].SpinCount;
  *(_QWORD *)&this[4].LockCount = 0;
  this[4].LockSemaphore = 0;
  if ( SpinCount )
    FreeLibrary(SpinCount);
  DeleteCriticalSection(this + 3);
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.h",
      297,
      "ISAPI_DLL::~ISAPI_DLL",
      "Deleted ISAPI_DLL %p.\r\n",
      this);
  BUFFER::~BUFFER((BUFFER *)&this[5]);
  STRU::~STRU((STRU *)&this[1].LockSemaphore);
  STRU::~STRU((STRU *)&this->LockCount);
}

```

## disassembly

```asm
0x180001bac  push    rbx
0x180001bae  sub     rsp, 30h
0x180001bb2  mov     rax, [rcx+0B0h]
0x180001bb9  mov     rbx, rcx
0x180001bbc  mov     dword ptr [rcx], 66445349h
0x180001bc2  test    rax, rax
0x180001bc5  jz      short loc_180001BDC
0x180001bc7  mov     ecx, 2
0x180001bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bd1  mov     qword ptr [rbx+0B0h], 0
0x180001bdc  mov     rcx, [rbx+0C0h]; hLibModule
0x180001be3  mov     qword ptr [rbx+0A8h], 0
0x180001bee  mov     qword ptr [rbx+0B8h], 0
0x180001bf9  test    rcx, rcx
0x180001bfc  jz      short loc_180001C04
0x180001bfe  call    cs:__imp_FreeLibrary
0x180001c04  lea     rcx, [rbx+78h]; lpCriticalSection
0x180001c08  call    cs:__imp_DeleteCriticalSection
0x180001c0e  mov     eax, cs:g_dwDebugFlags
0x180001c14  test    al, 3
0x180001c16  setnz   cl
0x180001c19  bt      eax, 1Fh
0x180001c1d  setb    al
0x180001c20  test    al, cl
0x180001c22  jz      short loc_180001C56
0x180001c24  mov     rcx, cs:g_pDebug
0x180001c2b  lea     rax, aDeletedIsapiDl; "Deleted ISAPI_DLL %p.\r\n"
0x180001c32  mov     [rsp+38h+var_10], rbx
0x180001c37  lea     r9, aIsapiDllIsapiD_0; "ISAPI_DLL::~ISAPI_DLL"
0x180001c3e  mov     r8d, 129h
0x180001c44  mov     [rsp+38h+var_18], rax
0x180001c49  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001c50  call    cs:__imp_PuDbgPrint
0x180001c56  lea     rcx, [rbx+0C8h]
0x180001c5d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180001c63  lea     rcx, [rbx+40h]
0x180001c67  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001c6d  lea     rcx, [rbx+8]
0x180001c71  add     rsp, 30h
0x180001c75  pop     rbx
0x180001c76  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
