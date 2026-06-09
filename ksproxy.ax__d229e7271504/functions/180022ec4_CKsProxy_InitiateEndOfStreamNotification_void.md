# CKsProxy::InitiateEndOfStreamNotification(void *)

- ea: `0x180022ec4`
- end: `0x1800230d8`
- name: `?InitiateEndOfStreamNotification@CKsProxy@@QEAAJPEAX@Z`
- size: `532`
- prototype: `__int64 __fastcall(CKsProxy *this, char *hFile)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180028584`

## callees

- `0x18000bde0`
- `0x180022ec4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180022fd0`
- `KERNEL32!GetLastError` at `0x180022fd0`
- `KERNEL32!SetEvent` at `0x18002301c`
- `KERNEL32!SetEvent` at `0x180023068`
- `KERNEL32!SetEvent` at `0x18002301c`
- `KERNEL32!SetEvent` at `0x180023068`
- `KERNEL32!WaitForSingleObjectEx` at `0x180023035`
- `KERNEL32!WaitForSingleObjectEx` at `0x180023081`
- `KERNEL32!WaitForSingleObjectEx` at `0x180023035`
- `KERNEL32!WaitForSingleObjectEx` at `0x180023081`
- `KERNEL32!CloseHandle` at `0x180023099`
- `KERNEL32!CloseHandle` at `0x180023099`
- `KERNEL32!CreateThread` at `0x180022fb8`
- `KERNEL32!CreateThread` at `0x180022fb8`
- `KERNEL32!LeaveCriticalSection` at `0x180022fee`
- `KERNEL32!LeaveCriticalSection` at `0x1800230b3`
- `KERNEL32!LeaveCriticalSection` at `0x180022fee`
- `KERNEL32!LeaveCriticalSection` at `0x1800230b3`
- `KERNEL32!EnterCriticalSection` at `0x180022f74`
- `KERNEL32!EnterCriticalSection` at `0x180022f74`

## pseudocode

```c
__int64 __fastcall CKsProxy::InitiateEndOfStreamNotification(CKsProxy *this, char *hFile)
{
  unsigned int i; // r8d
  CCritSec *m_pLock; // rdi
  HANDLE v7; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  void **m_WaitEvents; // rcx
  int Param; // esi
  void **v12; // rcx
  void *m_WaitThreadHandle; // rcx
  GUID InBuffer; // [rsp+40h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-18h]
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+80h] [rbp+18h] BYREF

  v15 = 0;
  NumberOfBytesTransferred = 0;
  InBuffer = 0;
  for ( i = 1; i < this->m_ActiveWaitEventCount; ++i )
  {
    if ( this->m_WaitPins[i] == hFile )
      return 0;
  }
  v15 = 0x20000000004LL;
  InBuffer = GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000;
  if ( KsSynchronousDeviceControl(hFile, 0x2F0007u, &InBuffer, 0x18u, 0, 0, &NumberOfBytesTransferred) < 0 )
    return 0;
  m_pLock = this->m_pLock;
  EnterCriticalSection(&m_pLock->m_CritSec);
  if ( this->m_WaitThreadHandle
    || (ThreadId = 0,
        v7 = CreateThread(0, 0, CKsProxy::WaitThread, this, 0, &ThreadId),
        (this->m_WaitThreadHandle = v7) != 0) )
  {
    m_WaitEvents = this->m_WaitEvents;
    this->m_WaitMessage.Message = 1;
    this->m_WaitMessage.Param = hFile;
    SetEvent(*m_WaitEvents);
    WaitForSingleObjectEx(this->m_WaitReplyHandle, 0xFFFFFFFF, 0);
    Param = (int)this->m_WaitMessage.Param;
    if ( Param < 0 && this->m_ActiveWaitEventCount == 1 )
    {
      v12 = this->m_WaitEvents;
      this->m_WaitMessage.Message = 0;
      SetEvent(*v12);
      WaitForSingleObjectEx(this->m_WaitThreadHandle, 0xFFFFFFFF, 0);
      m_WaitThreadHandle = this->m_WaitThreadHandle;
      if ( m_WaitThreadHandle )
      {
        CloseHandle(m_WaitThreadHandle);
        this->m_WaitThreadHandle = 0;
      }
    }
    LeaveCriticalSection(&m_pLock->m_CritSec);
    return (unsigned int)Param;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  LeaveCriticalSection(&m_pLock->m_CritSec);
  return v9;
}

```

## disassembly

```asm
0x180022ec4  mov     [rsp+arg_8], rbx
0x180022ec9  mov     [rsp+arg_18], rsi
0x180022ece  push    rdi
0x180022ecf  sub     rsp, 60h
0x180022ed3  xor     eax, eax
0x180022ed5  xorps   xmm0, xmm0
0x180022ed8  mov     rsi, rdx
0x180022edb  mov     [rsp+68h+var_18], rax
0x180022ee0  mov     rbx, rcx
0x180022ee3  mov     [rsp+68h+NumberOfBytesTransferred], eax
0x180022ee7  movups  [rsp+68h+InBuffer], xmm0
0x180022eec  lea     r8d, [rax+1]
0x180022ef0  cmp     r8d, [rbx+220h]
0x180022ef7  jnb     short loc_180022F15
0x180022ef9  mov     rax, [rbx+218h]
0x180022f00  mov     ecx, r8d
0x180022f03  cmp     [rax+rcx*8], rsi
0x180022f07  jz      short loc_180022F0E
0x180022f09  inc     r8d
0x180022f0c  jmp     short loc_180022EF0
0x180022f0e  xor     eax, eax
0x180022f10  jmp     loc_1800230C5
0x180022f15  movups  xmm0, xmmword ptr cs:_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data1
0x180022f1c  lea     rax, [rsp+68h+NumberOfBytesTransferred]
0x180022f21  mov     dword ptr [rsp+68h+var_18], 4
0x180022f29  mov     [rsp+68h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180022f2e  lea     r8, [rsp+68h+InBuffer]; lpInBuffer
0x180022f33  mov     dword ptr [rsp+68h+lpThreadId], 0; DWORD
0x180022f3b  mov     r9d, 18h; nInBufferSize
0x180022f41  mov     edx, 2F0007h; dwIoControlCode
0x180022f46  mov     qword ptr [rsp+68h+dwCreationFlags], 0; LPVOID
0x180022f4f  mov     rcx, rsi; hFile
0x180022f52  mov     dword ptr [rsp+68h+var_18+4], 200h
0x180022f5a  movdqu  [rsp+68h+InBuffer], xmm0
0x180022f60  call    KsSynchronousDeviceControl
0x180022f65  test    eax, eax
0x180022f67  js      loc_1800230C1
0x180022f6d  mov     rdi, [rbx+50h]
0x180022f71  mov     rcx, rdi; lpCriticalSection
0x180022f74  call    cs:__imp_EnterCriticalSection
0x180022f7b  nop     dword ptr [rax+rax+00h]
0x180022f80  cmp     qword ptr [rbx+208h], 0
0x180022f88  jnz     short loc_180023001
0x180022f8a  lea     rax, [rsp+68h+ThreadId]
0x180022f92  mov     [rsp+68h+ThreadId], 0
0x180022f9d  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180022fa2  lea     r8, ?WaitThread@CKsProxy@@SAKPEAV1@@Z; lpStartAddress
0x180022fa9  mov     r9, rbx; lpParameter
0x180022fac  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x180022fb4  xor     edx, edx; dwStackSize
0x180022fb6  xor     ecx, ecx; lpThreadAttributes
0x180022fb8  call    cs:__imp_CreateThread
0x180022fbf  nop     dword ptr [rax+rax+00h]
0x180022fc4  mov     [rbx+208h], rax
0x180022fcb  test    rax, rax
0x180022fce  jnz     short loc_180023001
0x180022fd0  call    cs:__imp_GetLastError
0x180022fd7  nop     dword ptr [rax+rax+00h]
0x180022fdc  mov     ebx, eax
0x180022fde  test    eax, eax
0x180022fe0  jle     short loc_180022FEB
0x180022fe2  movzx   ebx, ax
0x180022fe5  or      ebx, 80070000h
0x180022feb  mov     rcx, rdi; lpCriticalSection
0x180022fee  call    cs:__imp_LeaveCriticalSection
0x180022ff5  nop     dword ptr [rax+rax+00h]
0x180022ffa  mov     eax, ebx
0x180022ffc  jmp     loc_1800230C5
0x180023001  mov     rcx, [rbx+210h]
0x180023008  mov     dword ptr [rbx+230h], 1
0x180023012  mov     [rbx+238h], rsi
0x180023019  mov     rcx, [rcx]; hEvent
0x18002301c  call    cs:__imp_SetEvent
0x180023023  nop     dword ptr [rax+rax+00h]
0x180023028  mov     rcx, [rbx+228h]; hHandle
0x18002302f  xor     r8d, r8d; bAlertable
0x180023032  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023035  call    cs:__imp_WaitForSingleObjectEx
0x18002303c  nop     dword ptr [rax+rax+00h]
0x180023041  mov     esi, [rbx+238h]
0x180023047  test    esi, esi
0x180023049  jns     short loc_1800230B0
0x18002304b  cmp     dword ptr [rbx+220h], 1
0x180023052  jnz     short loc_1800230B0
0x180023054  mov     rcx, [rbx+210h]
0x18002305b  mov     dword ptr [rbx+230h], 0
0x180023065  mov     rcx, [rcx]; hEvent
0x180023068  call    cs:__imp_SetEvent
0x18002306f  nop     dword ptr [rax+rax+00h]
0x180023074  mov     rcx, [rbx+208h]; hHandle
0x18002307b  xor     r8d, r8d; bAlertable
0x18002307e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023081  call    cs:__imp_WaitForSingleObjectEx
0x180023088  nop     dword ptr [rax+rax+00h]
0x18002308d  mov     rcx, [rbx+208h]; hObject
0x180023094  test    rcx, rcx
0x180023097  jz      short loc_1800230B0
0x180023099  call    cs:__imp_CloseHandle
0x1800230a0  nop     dword ptr [rax+rax+00h]
0x1800230a5  mov     qword ptr [rbx+208h], 0
0x1800230b0  mov     rcx, rdi; lpCriticalSection
0x1800230b3  call    cs:__imp_LeaveCriticalSection
0x1800230ba  nop     dword ptr [rax+rax+00h]
0x1800230bf  jmp     short loc_1800230C3
0x1800230c1  xor     esi, esi
0x1800230c3  mov     eax, esi
0x1800230c5  lea     r11, [rsp+68h+var_8]
0x1800230ca  mov     rbx, [r11+18h]
0x1800230ce  mov     rsi, [r11+28h]
0x1800230d2  mov     rsp, r11
0x1800230d5  pop     rdi
0x1800230d6  retn
```
