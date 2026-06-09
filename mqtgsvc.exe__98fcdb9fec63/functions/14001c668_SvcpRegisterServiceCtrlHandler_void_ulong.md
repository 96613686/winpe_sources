# SvcpRegisterServiceCtrlHandler(void (*)(ulong))

- ea: `0x14001c668`
- end: `0x14001c6f9`
- name: `?SvcpRegisterServiceCtrlHandler@@YAXP6AXK@Z@Z`
- size: `145`
- prototype: `void __fastcall(void (*)(unsigned int))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x14001c630`

## callees

- `0x140001cc6`
- `0x140007554`
- `0x140008034`
- `0x14001c668`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x14001c67c`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x14001c67c`
- `KERNEL32!GetLastError` at `0x14001c687`
- `KERNEL32!GetLastError` at `0x14001c687`

## pseudocode

```c
void __fastcall SvcpRegisterServiceCtrlHandler(void (*a1)(unsigned int))
{
  SERVICE_STATUS_HANDLE v1; // rax
  DWORD LastError; // ebx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v1 = RegisterServiceCtrlHandlerW(&ServiceName, SvcpHandler);
  if ( !v1 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9df9884075d73472bc34f24e96197e6d_Traceguids);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, LastError);
    throw (bad_win32_error *)pExceptionObject;
  }
  qword_14002B128 = (__int64)v1;
  qword_14002B120 = (__int64)SvcpSetServiceStatus;
}

```

## disassembly

```asm
0x14001c668  push    rbx
0x14001c66a  sub     rsp, 40h
0x14001c66e  lea     rdx, SvcpHandler; lpHandlerProc
0x14001c675  lea     rcx, ServiceName; lpServiceName
0x14001c67c  call    cs:__imp_RegisterServiceCtrlHandlerW
0x14001c682  test    rax, rax
0x14001c685  jnz     short loc_14001C6DE
0x14001c687  call    cs:__imp_GetLastError
0x14001c68d  mov     ebx, eax
0x14001c68f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c696  lea     rax, WPP_GLOBAL_Control
0x14001c69d  cmp     rcx, rax
0x14001c6a0  jz      short loc_14001C6C0
0x14001c6a2  test    byte ptr [rcx+1Ch], 1
0x14001c6a6  jz      short loc_14001C6C0
0x14001c6a8  mov     rcx, [rcx+10h]
0x14001c6ac  lea     r8, WPP_9df9884075d73472bc34f24e96197e6d_Traceguids
0x14001c6b3  mov     edx, 0Bh
0x14001c6b8  mov     r9d, ebx
0x14001c6bb  call    WPP_SF_d
0x14001c6c0  mov     edx, ebx; unsigned int
0x14001c6c2  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14001c6c7  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x14001c6cc  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x14001c6d3  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14001c6d8  call    _CxxThrowException_0
0x14001c6de  mov     cs:qword_14002B128, rax
0x14001c6e5  lea     rax, ?SvcpSetServiceStatus@@YAXPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@Z; SvcpSetServiceStatus(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *)
0x14001c6ec  mov     cs:qword_14002B120, rax
0x14001c6f3  add     rsp, 40h
0x14001c6f7  pop     rbx
0x14001c6f8  retn
```
