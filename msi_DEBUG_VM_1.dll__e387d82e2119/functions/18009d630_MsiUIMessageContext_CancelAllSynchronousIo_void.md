# MsiUIMessageContext::CancelAllSynchronousIo(void)

- ea: `0x18009d630`
- end: `0x18009d807`
- name: `?CancelAllSynchronousIo@MsiUIMessageContext@@QEAAIXZ`
- size: `471`
- prototype: `unsigned int __fastcall(MsiUIMessageContext *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18009bc00`

## callees

- `0x180025a18`
- `0x18009d630`
- `0x180146548`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18009d7d7`
- `KERNEL32!CloseHandle` at `0x18009d7d7`
- `KERNEL32!GetCurrentThreadId` at `0x18009d67a`
- `KERNEL32!GetCurrentThreadId` at `0x18009d67a`
- `KERNEL32!GetLastError` at `0x18009d6ca`
- `KERNEL32!GetLastError` at `0x18009d71e`
- `KERNEL32!GetLastError` at `0x18009d748`
- `KERNEL32!GetLastError` at `0x18009d78e`
- `KERNEL32!GetLastError` at `0x18009d7c1`
- `KERNEL32!GetLastError` at `0x18009d7cc`
- `KERNEL32!GetLastError` at `0x18009d6ca`
- `KERNEL32!GetLastError` at `0x18009d71e`
- `KERNEL32!GetLastError` at `0x18009d748`
- `KERNEL32!GetLastError` at `0x18009d78e`
- `KERNEL32!GetLastError` at `0x18009d7c1`
- `KERNEL32!GetLastError` at `0x18009d7cc`
- `KERNEL32!GetCurrentProcessId` at `0x18009d683`
- `KERNEL32!GetCurrentProcessId` at `0x18009d683`
- `KERNEL32!OpenThread` at `0x18009d707`
- `KERNEL32!OpenThread` at `0x18009d707`

## string_xrefs

- `0x18009d724`: `Could not open thread %u while attempting to cancel I/O. Error: %d`
- `0x18009d74e`: `I/O on thread %u could not be cancelled. Error: %d`

## pseudocode

```c
__int64 __fastcall MsiUIMessageContext::CancelAllSynchronousIo(MsiUIMessageContext *this)
{
  DWORD CurrentThreadId; // r15d
  __int64 CurrentProcessId; // r14
  __int64 v5; // rax
  void *v6; // rdi
  DWORD LastError; // ebx
  HANDLE v8; // rax
  DWORD v9; // eax
  const unsigned __int16 *v10; // r9
  __int64 v11; // [rsp+60h] [rbp+7h] BYREF
  DWORD dwThreadId[8]; // [rsp+68h] [rbp+Fh] BYREF

  if ( *((_BYTE *)this + 230) == 1 )
    return 0;
  memset(dwThreadId, 0, 28);
  CurrentThreadId = GetCurrentThreadId();
  CurrentProcessId = GetCurrentProcessId();
  v5 = ((__int64 (__fastcall *)(__int64, __int64))KERNEL32::CreateToolhelp32Snapshot)(4, CurrentProcessId);
  v11 = v5;
  v6 = (void *)v5;
  if ( v5 == -1
    || (dwThreadId[0] = 28,
        !(unsigned int)((__int64 (__fastcall *)(__int64, DWORD *))KERNEL32::Thread32First)(v5, dwThreadId)) )
  {
    LastError = GetLastError();
    CHandle::~CHandle((CHandle *)&v11);
    return LastError;
  }
  LastError = 0;
  do
  {
    if ( CurrentThreadId != dwThreadId[2] && dwThreadId[3] == (_DWORD)CurrentProcessId )
    {
      v8 = OpenThread(0x1FFFFFu, 0, dwThreadId[2]);
      v11 = (__int64)v8;
      if ( v8 )
      {
        if ( (unsigned int)((__int64 (__fastcall *)(HANDLE))KERNEL32::CancelSynchronousIo)(v8) )
        {
LABEL_17:
          CHandle::~CHandle((CHandle *)&v11);
          continue;
        }
        if ( g_dmDiagnosticMode )
        {
          v9 = GetLastError();
          v10 = L"I/O on thread %u could not be cancelled. Error: %d";
          goto LABEL_15;
        }
      }
      else if ( g_dmDiagnosticMode )
      {
        v9 = GetLastError();
        v10 = L"Could not open thread %u while attempting to cancel I/O. Error: %d";
LABEL_15:
        DebugString(
          9,
          0,
          0,
          v10,
          (const unsigned __int16 *)dwThreadId[2],
          (const unsigned __int16 *)v9,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      LastError = GetLastError();
      goto LABEL_17;
    }
  }
  while ( (unsigned int)((__int64 (__fastcall *)(void *, DWORD *))KERNEL32::Thread32Next)(v6, dwThreadId) );
  *((_BYTE *)this + 230) = 1;
  if ( GetLastError() != 18 )
    LastError = GetLastError();
  CloseHandle(v6);
  return LastError;
}

```

## disassembly

```asm
0x18009d630  mov     [rsp-8+arg_8], rbx
0x18009d635  mov     [rsp-8+arg_10], rsi
0x18009d63a  push    rbp
0x18009d63b  push    rdi
0x18009d63c  push    r13
0x18009d63e  push    r14
0x18009d640  push    r15
0x18009d642  lea     rbp, [rsp-37h]
0x18009d647  sub     rsp, 90h
0x18009d64e  mov     rax, cs:__security_cookie
0x18009d655  xor     rax, rsp
0x18009d658  mov     [rbp+57h+var_28], rax
0x18009d65c  cmp     byte ptr [rcx+0E6h], 1
0x18009d663  mov     rsi, rcx
0x18009d666  jnz     short loc_18009D66F
0x18009d668  xor     eax, eax
0x18009d66a  jmp     loc_18009D7DF
0x18009d66f  xorps   xmm0, xmm0
0x18009d672  movups  xmmword ptr [rbp+57h+dwThreadId], xmm0
0x18009d676  movups  xmmword ptr [rbp+57h+dwThreadId+0Ch], xmm0
0x18009d67a  call    cs:__imp_GetCurrentThreadId
0x18009d680  mov     r15d, eax
0x18009d683  call    cs:__imp_GetCurrentProcessId
0x18009d689  mov     r14d, eax
0x18009d68c  mov     edx, eax
0x18009d68e  mov     rax, cs:?CreateToolhelp32Snapshot@KERNEL32@@3P6APEAXKK@ZEA; void * (*KERNEL32::CreateToolhelp32Snapshot)(ulong,ulong)
0x18009d695  mov     ecx, 4
0x18009d69a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d69f  mov     [rbp+57h+var_50], rax
0x18009d6a3  mov     rdi, rax
0x18009d6a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009d6aa  jz      short loc_18009D6CA
0x18009d6ac  mov     rcx, rax
0x18009d6af  mov     [rbp+57h+dwThreadId], 1Ch
0x18009d6b6  mov     rax, cs:?Thread32First@KERNEL32@@3P6AHPEAXPEAUtagTHREADENTRY32@@@ZEA; int (*KERNEL32::Thread32First)(void *,tagTHREADENTRY32 *)
0x18009d6bd  lea     rdx, [rbp+57h+dwThreadId]
0x18009d6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d6c6  test    eax, eax
0x18009d6c8  jnz     short loc_18009D6E0
0x18009d6ca  call    cs:__imp_GetLastError
0x18009d6d0  lea     rcx, [rbp+57h+var_50]; this
0x18009d6d4  mov     ebx, eax
0x18009d6d6  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18009d6db  jmp     loc_18009D7DD
0x18009d6e0  xor     ebx, ebx
0x18009d6e2  lea     r13, aNull; "(NULL)"
0x18009d6e9  mov     r8d, [rbp+57h+dwThreadId+8]; dwThreadId
0x18009d6ed  cmp     r15d, r8d
0x18009d6f0  jz      loc_18009D79F
0x18009d6f6  cmp     [rbp+57h+dwThreadId+0Ch], r14d
0x18009d6fa  jnz     loc_18009D79F
0x18009d700  xor     edx, edx; bInheritHandle
0x18009d702  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18009d707  call    cs:__imp_OpenThread
0x18009d70d  mov     [rbp+57h+var_50], rax
0x18009d711  test    rax, rax
0x18009d714  jnz     short loc_18009D72D
0x18009d716  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18009d71c  jz      short loc_18009D78E
0x18009d71e  call    cs:__imp_GetLastError
0x18009d724  lea     r9, aCouldNotOpenTh; "Could not open thread %u while attempti"...
0x18009d72b  jmp     short loc_18009D755
0x18009d72d  mov     rcx, rax
0x18009d730  mov     rax, cs:?CancelSynchronousIo@KERNEL32@@3P6AHPEAX@ZEA; int (*KERNEL32::CancelSynchronousIo)(void *)
0x18009d737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d73c  test    eax, eax
0x18009d73e  jnz     short loc_18009D796
0x18009d740  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18009d746  jz      short loc_18009D78E
0x18009d748  call    cs:__imp_GetLastError
0x18009d74e  lea     r9, aIOOnThreadUCou; "I/O on thread %u could not be cancelled"...
0x18009d755  mov     ecx, [rbp+57h+dwThreadId+8]
0x18009d758  xor     edx, edx; unsigned __int16
0x18009d75a  mov     [rsp+0B0h+var_58], rdx; void *
0x18009d75f  xor     r8d, r8d; int
0x18009d762  mov     [rsp+0B0h+var_60], edx; unsigned int
0x18009d766  mov     [rsp+0B0h+var_68], r13; unsigned __int16 *
0x18009d76b  mov     [rsp+0B0h+var_70], r13; unsigned __int16 *
0x18009d770  mov     [rsp+0B0h+var_78], r13; unsigned __int16 *
0x18009d775  mov     eax, eax
0x18009d777  mov     [rsp+0B0h+var_80], r13; unsigned __int16 *
0x18009d77c  mov     [rsp+0B0h+var_88], rax; unsigned __int16 *
0x18009d781  mov     [rsp+0B0h+var_90], rcx; unsigned __int16 *
0x18009d786  lea     ecx, [rdx+9]; int
0x18009d789  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009d78e  call    cs:__imp_GetLastError
0x18009d794  mov     ebx, eax
0x18009d796  lea     rcx, [rbp+57h+var_50]; this
0x18009d79a  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18009d79f  mov     rax, cs:?Thread32Next@KERNEL32@@3P6AHPEAXPEAUtagTHREADENTRY32@@@ZEA; int (*KERNEL32::Thread32Next)(void *,tagTHREADENTRY32 *)
0x18009d7a6  lea     rdx, [rbp+57h+dwThreadId]
0x18009d7aa  mov     rcx, rdi
0x18009d7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d7b2  test    eax, eax
0x18009d7b4  jnz     loc_18009D6E9
0x18009d7ba  mov     byte ptr [rsi+0E6h], 1
0x18009d7c1  call    cs:__imp_GetLastError
0x18009d7c7  cmp     eax, 12h
0x18009d7ca  jz      short loc_18009D7D4
0x18009d7cc  call    cs:__imp_GetLastError
0x18009d7d2  mov     ebx, eax
0x18009d7d4  mov     rcx, rdi; hObject
0x18009d7d7  call    cs:__imp_CloseHandle
0x18009d7dd  mov     eax, ebx
0x18009d7df  mov     rcx, [rbp+57h+var_28]
0x18009d7e3  xor     rcx, rsp; StackCookie
0x18009d7e6  call    __security_check_cookie
0x18009d7eb  lea     r11, [rsp+0B0h+var_20]
0x18009d7f3  mov     rbx, [r11+38h]
0x18009d7f7  mov     rsi, [r11+40h]
0x18009d7fb  mov     rsp, r11
0x18009d7fe  pop     r15
0x18009d800  pop     r14
0x18009d802  pop     r13
0x18009d804  pop     rdi
0x18009d805  pop     rbp
0x18009d806  retn
```
