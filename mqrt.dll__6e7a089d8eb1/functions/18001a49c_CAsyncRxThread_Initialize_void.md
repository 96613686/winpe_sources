# CAsyncRxThread::Initialize(void)

- ea: `0x18001a49c`
- end: `0x18001a636`
- name: `?Initialize@CAsyncRxThread@@AEAAXXZ`
- size: `410`
- prototype: `void __fastcall(CAsyncRxThread *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001a1b8`

## callees

- `0x1800022d6`
- `0x1800093d0`
- `0x18000da78`
- `0x180013d20`
- `0x18001a3b0`
- `0x18001a49c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001a5da`
- `KERNEL32!FreeLibrary` at `0x18001a5da`
- `KERNEL32!CreateThread` at `0x18001a5b9`
- `KERNEL32!CreateThread` at `0x18001a5b9`
- `KERNEL32!CreateEventW` at `0x18001a51f`
- `KERNEL32!CreateEventW` at `0x18001a51f`
- `KERNEL32!GetLastError` at `0x18001a4bf`
- `KERNEL32!GetLastError` at `0x18001a532`
- `KERNEL32!GetLastError` at `0x18001a5cb`
- `KERNEL32!GetLastError` at `0x18001a4bf`
- `KERNEL32!GetLastError` at `0x18001a532`
- `KERNEL32!GetLastError` at `0x18001a5cb`
- `KERNEL32!CloseHandle` at `0x18001a50f`
- `KERNEL32!CloseHandle` at `0x18001a50f`
- `KERNEL32!WaitForSingleObject` at `0x18001a4b5`
- `KERNEL32!WaitForSingleObject` at `0x18001a4b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAsyncRxThread::Initialize(CAsyncRxThread *this)
{
  DWORD LastError; // eax
  unsigned int v2; // ebx
  HANDLE v3; // rcx
  HANDLE EventW; // rax
  void *v5; // rbx
  DWORD v6; // eax
  unsigned int v7; // ebx
  DWORD v8; // ebx
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF
  CAsyncRxThread *ThreadId; // [rsp+60h] [rbp+8h] BYREF
  HANDLE v11; // [rsp+68h] [rbp+10h] BYREF

  ThreadId = this;
  if ( hObject )
  {
    if ( WaitForSingleObject(hObject, 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError )
        LogMsgNTStatus(LastError, (wchar_t *)L"rt/CRtReceive", 0x4B3u);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v2);
      throw (bad_win32_error *)pExceptionObject;
    }
    v3 = hObject;
    hObject = 0;
    CloseHandle(v3);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v5 = EventW;
  v11 = EventW;
  if ( !EventW )
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 )
      LogMsgNTStatus(v6, (wchar_t *)L"rt/CRtReceive", 0x4B4u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v7);
    throw (bad_win32_error *)pExceptionObject;
  }
  dword_18003D4B8 = 1;
  qword_18003D6C0 = (__int64)EventW;
  *(&hObject + 1) = (HANDLE)GetLibraryReference();
  LODWORD(ThreadId) = 0;
  hObject = CreateThread(0, 0, CAsyncRxThread::AsyncRxThreadProc, &g_AsyncRxThread, 0, (LPDWORD)&ThreadId);
  if ( !hObject )
  {
    v8 = GetLastError();
    FreeLibrary((HMODULE)*(&hObject + 1));
    if ( v8 )
      LogMsgNTStatus(v8, (wchar_t *)L"rt/CRtReceive", 0x4B5u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v8);
    throw (bad_win32_error *)pExceptionObject;
  }
  v11 = 0;
  hEvent = v5;
  CHandle::~CHandle((CHandle *)&v11);
}

```

## disassembly

```asm
0x18001a49c  mov     [rsp+ThreadId], rcx
0x18001a4a1  push    rbx
0x18001a4a2  sub     rsp, 50h
0x18001a4a6  mov     rcx, qword ptr cs:hObject; hHandle
0x18001a4ad  test    rcx, rcx
0x18001a4b0  jz      short loc_18001A515
0x18001a4b2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a4b5  call    cs:__imp_WaitForSingleObject
0x18001a4bb  test    eax, eax
0x18001a4bd  jz      short loc_18001A4FD
0x18001a4bf  call    cs:__imp_GetLastError
0x18001a4c5  mov     ebx, eax
0x18001a4c7  test    eax, eax
0x18001a4c9  jz      short loc_18001A4DF
0x18001a4cb  mov     r8d, 4B3h; unsigned __int16
0x18001a4d1  lea     rdx, aRtCrtreceive; "rt/CRtReceive"
0x18001a4d8  mov     ecx, eax; int
0x18001a4da  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001a4df  mov     edx, ebx; unsigned int
0x18001a4e1  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001a4e6  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18001a4eb  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18001a4f2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001a4f7  call    _CxxThrowException_0
0x18001a4fd  mov     rcx, qword ptr cs:hObject; hObject
0x18001a504  mov     qword ptr cs:hObject, 0
0x18001a50f  call    cs:__imp_CloseHandle
0x18001a515  xor     r9d, r9d; lpName
0x18001a518  xor     r8d, r8d; bInitialState
0x18001a51b  xor     edx, edx; bManualReset
0x18001a51d  xor     ecx, ecx; lpEventAttributes
0x18001a51f  call    cs:__imp_CreateEventW
0x18001a525  mov     rbx, rax
0x18001a528  mov     [rsp+58h+arg_8], rax
0x18001a52d  test    rax, rax
0x18001a530  jnz     short loc_18001A570
0x18001a532  call    cs:__imp_GetLastError
0x18001a538  mov     ebx, eax
0x18001a53a  test    eax, eax
0x18001a53c  jz      short loc_18001A552
0x18001a53e  mov     r8d, 4B4h; unsigned __int16
0x18001a544  lea     rdx, aRtCrtreceive; "rt/CRtReceive"
0x18001a54b  mov     ecx, eax; int
0x18001a54d  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001a552  mov     edx, ebx; unsigned int
0x18001a554  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001a559  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18001a55e  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18001a565  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001a56a  call    _CxxThrowException_0
0x18001a570  mov     cs:dword_18003D4B8, 1
0x18001a57a  mov     cs:qword_18003D6C0, rbx
0x18001a581  call    GetLibraryReference
0x18001a586  mov     qword ptr cs:hObject+8, rax
0x18001a58d  mov     dword ptr [rsp+58h+ThreadId], 0
0x18001a595  lea     rax, [rsp+58h+ThreadId]
0x18001a59a  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18001a59f  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18001a5a7  lea     r9, ?g_AsyncRxThread@@3VCAsyncRxThread@@A; lpParameter
0x18001a5ae  lea     r8, ?AsyncRxThreadProc@CAsyncRxThread@@CAKPEAX@Z; lpStartAddress
0x18001a5b5  xor     edx, edx; dwStackSize
0x18001a5b7  xor     ecx, ecx; lpThreadAttributes
0x18001a5b9  call    cs:__imp_CreateThread
0x18001a5bf  mov     qword ptr cs:hObject, rax
0x18001a5c6  test    rax, rax
0x18001a5c9  jnz     short loc_18001A616
0x18001a5cb  call    cs:__imp_GetLastError
0x18001a5d1  mov     ebx, eax
0x18001a5d3  mov     rcx, qword ptr cs:hObject+8; hLibModule
0x18001a5da  call    cs:__imp_FreeLibrary
0x18001a5e0  test    ebx, ebx
0x18001a5e2  jz      short loc_18001A5F8
0x18001a5e4  mov     r8d, 4B5h; unsigned __int16
0x18001a5ea  lea     rdx, aRtCrtreceive; "rt/CRtReceive"
0x18001a5f1  mov     ecx, ebx; int
0x18001a5f3  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001a5f8  mov     edx, ebx; unsigned int
0x18001a5fa  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001a5ff  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18001a604  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18001a60b  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001a610  call    _CxxThrowException_0
0x18001a616  mov     [rsp+58h+arg_8], 0
0x18001a61f  mov     cs:hEvent, rbx
0x18001a626  lea     rcx, [rsp+58h+arg_8]; this
0x18001a62b  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18001a630  add     rsp, 50h
0x18001a634  pop     rbx
0x18001a635  retn
```
