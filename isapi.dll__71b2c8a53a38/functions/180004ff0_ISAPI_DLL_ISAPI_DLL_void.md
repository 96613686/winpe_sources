# ISAPI_DLL::ISAPI_DLL(void)

- ea: `0x180004ff0`
- end: `0x1800050cd`
- name: `??0ISAPI_DLL@@QEAA@XZ`
- size: `221`
- prototype: `ISAPI_DLL *__fastcall(ISAPI_DLL *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005224`

## callees

- `0x180004ff0`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800050b4`
- `iisutil!PuDbgPrint` at `0x1800050b4`
- `iisutil!IISInitializeCriticalSection` at `0x1800050be`
- `iisutil!IISInitializeCriticalSection` at `0x1800050be`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180005061`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180005061`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000500a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005014`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000500a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180005014`

## string_xrefs

- `0x1800050ad`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.h`
- `0x18000508f`: `Created new ISAPI_DLL %p.\n`
- `0x18000509b`: `ISAPI_DLL::ISAPI_DLL`

## pseudocode

```c
ISAPI_DLL *__fastcall ISAPI_DLL::ISAPI_DLL(ISAPI_DLL *this)
{
  int v2; // eax
  bool v3; // zf

  *(_DWORD *)this = 1279546185;
  *((_DWORD *)this + 1) = 1;
  STRU::STRU((ISAPI_DLL *)((char *)this + 8));
  STRU::STRU((ISAPI_DLL *)((char *)this + 64));
  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 41) = 1;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  BUFFER::BUFFER((ISAPI_DLL *)((char *)this + 200));
  v2 = g_dwDebugFlags;
  v3 = (g_dwDebugFlags & 3) == 0;
  *((_QWORD *)this + 31) = 0;
  if ( !v3 && v2 < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.h",
      126,
      "ISAPI_DLL::ISAPI_DLL",
      "Created new ISAPI_DLL %p.\r\n",
      this);
  IISInitializeCriticalSection((char *)this + 120);
  return this;
}

```

## disassembly

```asm
0x180004ff0  push    rbx
0x180004ff2  sub     rsp, 30h
0x180004ff6  mov     rbx, rcx
0x180004ff9  mov     dword ptr [rcx], 4C445349h
0x180004fff  mov     dword ptr [rcx+4], 1
0x180005006  add     rcx, 8
0x18000500a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180005010  lea     rcx, [rbx+40h]
0x180005014  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000501a  mov     dword ptr [rbx+0A0h], 0
0x180005024  lea     rcx, [rbx+0C8h]
0x18000502b  mov     dword ptr [rbx+0A4h], 1
0x180005035  mov     qword ptr [rbx+0A8h], 0
0x180005040  mov     qword ptr [rbx+0B0h], 0
0x18000504b  mov     qword ptr [rbx+0B8h], 0
0x180005056  mov     qword ptr [rbx+0C0h], 0
0x180005061  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180005067  mov     eax, cs:g_dwDebugFlags
0x18000506d  test    al, 3
0x18000506f  mov     qword ptr [rbx+0F8h], 0
0x18000507a  setnz   cl
0x18000507d  bt      eax, 1Fh
0x180005081  setb    al
0x180005084  test    al, cl
0x180005086  jz      short loc_1800050BA
0x180005088  mov     rcx, cs:g_pDebug
0x18000508f  lea     rax, aCreatedNewIsap; "Created new ISAPI_DLL %p.\r\n"
0x180005096  mov     [rsp+38h+var_10], rbx
0x18000509b  lea     r9, aIsapiDllIsapiD; "ISAPI_DLL::ISAPI_DLL"
0x1800050a2  mov     r8d, 7Eh ; '~'
0x1800050a8  mov     [rsp+38h+var_18], rax
0x1800050ad  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800050b4  call    cs:__imp_PuDbgPrint
0x1800050ba  lea     rcx, [rbx+78h]
0x1800050be  call    cs:__imp_IISInitializeCriticalSection
0x1800050c4  mov     rax, rbx
0x1800050c7  add     rsp, 30h
0x1800050cb  pop     rbx
0x1800050cc  retn
```
