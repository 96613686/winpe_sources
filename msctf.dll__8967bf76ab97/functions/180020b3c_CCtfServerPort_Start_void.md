# CCtfServerPort::Start(void)

- ea: `0x180020b3c`
- end: `0x180020cd8`
- name: `?Start@CCtfServerPort@@QEAA_NXZ`
- size: `412`
- prototype: `char __fastcall(CCtfServerPort *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800a6a60`

## callees

- `0x18000e588`
- `0x18000f900`
- `0x180020940`
- `0x180020b3c`
- `0x18003f2f0`
- `0x180091cb4`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020b75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020b8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020b75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020b8b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180020c80`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180020c80`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020cd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c89`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020be4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020be4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020ba9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020c24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020ba9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020c24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c99`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180020c15`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180020c15`
- `USER32!GetThreadDesktop` at `0x180020bb1`
- `USER32!GetThreadDesktop` at `0x180020bb1`

## pseudocode

```c
char __fastcall CCtfServerPort::Start(CCtfServerPort *this)
{
  HANDLE EventW; // rax
  bool v3; // zf
  DWORD CurrentThreadId; // eax
  HANDLE Thread; // rax
  struct IUnknown *Instance; // rax
  unsigned int v7; // r8d
  struct _SECURITY_ATTRIBUTES *v8; // rax
  HANDLE MutexW; // rbx
  HANDLE Handles[2]; // [rsp+30h] [rbp-258h] BYREF
  __int128 v12; // [rsp+40h] [rbp-248h] BYREF
  __int64 v13; // [rsp+50h] [rbp-238h]
  WCHAR Name[264]; // [rsp+60h] [rbp-228h] BYREF

  if ( *((_QWORD *)this + 1) )
    return 1;
  *((_QWORD *)this + 2) = CreateEventW(0, 1, 0, 0);
  EventW = CreateEventW(0, 1, 0, 0);
  v3 = *((_QWORD *)this + 2) == 0;
  *((_QWORD *)this + 3) = EventW;
  if ( !v3 && EventW )
  {
    CurrentThreadId = GetCurrentThreadId();
    *((_QWORD *)this + 19) = GetThreadDesktop(CurrentThreadId);
    _InterlockedIncrement((volatile signed __int32 *)this + 40);
    Thread = CreateThread(0, 0, CCtfServerPort::StaticServerThread, this, 0, 0);
    *((_QWORD *)this + 1) = Thread;
    if ( Thread )
    {
      Handles[0] = Thread;
      Handles[1] = *((HANDLE *)this + 2);
      if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) == 1 )
      {
        *((_DWORD *)this + 26) = GetCurrentThreadId();
        Instance = (struct IUnknown *)CInputProfileMasterAssembly::CreateInstance();
        if ( *((struct IUnknown **)this + 12) != Instance )
          ATL::AtlComPtrAssign((struct IUnknown **)this + 12, Instance);
        if ( *((_QWORD *)this + 12) )
        {
          GetDesktopUniqueName(L"Local\\MSCTF.CtfServerMutex", Name, v7);
          v12 = 0;
          v13 = 0;
          v8 = (struct _SECURITY_ATTRIBUTES *)CCicSecAttr::operator _SECURITY_ATTRIBUTES *(&v12);
          MutexW = CreateMutexW(v8, 0, Name);
          if ( GetLastError() == 183 )
            CloseHandle(MutexW);
          else
            WaitForSingleObject(MutexW, 0);
          return 1;
        }
      }
    }
    CCtfServerPort::Release(this);
  }
  return 0;
}

```

## disassembly

```asm
0x180020b3c  mov     [rsp+arg_8], rbx
0x180020b41  push    rdi
0x180020b42  sub     rsp, 280h
0x180020b49  mov     rax, cs:__security_cookie
0x180020b50  xor     rax, rsp
0x180020b53  mov     [rsp+288h+var_18], rax
0x180020b5b  cmp     qword ptr [rcx+8], 0
0x180020b60  mov     rbx, rcx
0x180020b63  jnz     loc_180020C9F
0x180020b69  xor     r9d, r9d; lpName
0x180020b6c  xor     r8d, r8d; bInitialState
0x180020b6f  xor     ecx, ecx; lpEventAttributes
0x180020b71  lea     edx, [r9+1]; bManualReset
0x180020b75  call    cs:__imp_CreateEventW
0x180020b7b  xor     r9d, r9d; lpName
0x180020b7e  xor     r8d, r8d; bInitialState
0x180020b81  xor     ecx, ecx; lpEventAttributes
0x180020b83  mov     [rbx+10h], rax
0x180020b87  lea     edx, [r9+1]; bManualReset
0x180020b8b  call    cs:__imp_CreateEventW
0x180020b91  cmp     qword ptr [rbx+10h], 0
0x180020b96  mov     [rbx+18h], rax
0x180020b9a  jz      loc_180020CCA
0x180020ba0  test    rax, rax
0x180020ba3  jz      loc_180020CCA
0x180020ba9  call    cs:__imp_GetCurrentThreadId
0x180020baf  mov     ecx, eax; dwThreadId
0x180020bb1  call    cs:__imp_GetThreadDesktop
0x180020bb7  mov     [rbx+98h], rax
0x180020bbe  lock inc dword ptr [rbx+0A0h]
0x180020bc5  mov     [rsp+288h+lpThreadId], 0; lpThreadId
0x180020bce  lea     r8, ?StaticServerThread@CCtfServerPort@@CAKPEAX@Z; lpStartAddress
0x180020bd5  mov     r9, rbx; lpParameter
0x180020bd8  mov     [rsp+288h+dwCreationFlags], 0; dwCreationFlags
0x180020be0  xor     edx, edx; dwStackSize
0x180020be2  xor     ecx, ecx; lpThreadAttributes
0x180020be4  call    cs:__imp_CreateThread
0x180020bea  mov     [rbx+8], rax
0x180020bee  test    rax, rax
0x180020bf1  jz      loc_180020CC2
0x180020bf7  xor     r8d, r8d; bWaitAll
0x180020bfa  mov     [rsp+288h+Handles], rax
0x180020bff  mov     rax, [rbx+10h]
0x180020c03  lea     rdx, [rsp+288h+Handles]; lpHandles
0x180020c08  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180020c0c  mov     [rsp+288h+var_250], rax
0x180020c11  lea     ecx, [r8+2]; nCount
0x180020c15  call    cs:__imp_WaitForMultipleObjects
0x180020c1b  cmp     eax, 1
0x180020c1e  jnz     loc_180020CC2
0x180020c24  call    cs:__imp_GetCurrentThreadId
0x180020c2a  mov     [rbx+68h], eax
0x180020c2d  call    ?CreateInstance@CInputProfileMasterAssembly@@SAPEAV1@XZ; CInputProfileMasterAssembly::CreateInstance(void)
0x180020c32  lea     rdi, [rbx+60h]
0x180020c36  cmp     [rdi], rax
0x180020c39  jz      short loc_180020C46
0x180020c3b  mov     rdx, rax; struct IUnknown *
0x180020c3e  mov     rcx, rdi; struct IUnknown **
0x180020c41  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180020c46  cmp     qword ptr [rdi], 0
0x180020c4a  jz      short loc_180020CC2
0x180020c4c  lea     rdx, [rsp+288h+Name]; unsigned __int16 *
0x180020c51  lea     rcx, aLocalMsctfCtfs; "Local\\MSCTF.CtfServerMutex"
0x180020c58  call    ?GetDesktopUniqueName@@YAXPEBGPEAGK@Z; GetDesktopUniqueName(ushort const *,ushort *,ulong)
0x180020c5d  xorps   xmm0, xmm0
0x180020c60  lea     rcx, [rsp+288h+var_248]
0x180020c65  xor     eax, eax
0x180020c67  movups  [rsp+288h+var_248], xmm0
0x180020c6c  mov     [rsp+288h+var_238], rax
0x180020c71  call    ??BCCicSecAttr@@QEAAPEAU_SECURITY_ATTRIBUTES@@XZ; CCicSecAttr::operator _SECURITY_ATTRIBUTES *(void)
0x180020c76  mov     rcx, rax; lpMutexAttributes
0x180020c79  lea     r8, [rsp+288h+Name]; lpName
0x180020c7e  xor     edx, edx; bInitialOwner
0x180020c80  call    cs:__imp_CreateMutexW
0x180020c86  mov     rbx, rax
0x180020c89  call    cs:__imp_GetLastError
0x180020c8f  mov     rcx, rbx; hHandle
0x180020c92  cmp     eax, 0B7h
0x180020c97  jnz     short loc_180020CCE
0x180020c99  call    cs:__imp_CloseHandle
0x180020c9f  mov     al, 1
0x180020ca1  mov     rcx, [rsp+288h+var_18]
0x180020ca9  xor     rcx, rsp; StackCookie
0x180020cac  call    __security_check_cookie
0x180020cb1  mov     rbx, [rsp+288h+arg_8]
0x180020cb9  add     rsp, 280h
0x180020cc0  pop     rdi
0x180020cc1  retn
0x180020cc2  mov     rcx, rbx; this
0x180020cc5  call    ?Release@CCtfServerPort@@QEAAKXZ; CCtfServerPort::Release(void)
0x180020cca  xor     al, al
0x180020ccc  jmp     short loc_180020CA1
0x180020cce  xor     edx, edx; dwMilliseconds
0x180020cd0  call    cs:__imp_WaitForSingleObject
0x180020cd6  jmp     short loc_180020C9F
```
