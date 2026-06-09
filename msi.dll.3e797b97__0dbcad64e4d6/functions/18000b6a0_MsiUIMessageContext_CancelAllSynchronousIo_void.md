# MsiUIMessageContext::CancelAllSynchronousIo(void)

- ea: `0x18000b6a0`
- end: `0x18000b8b4`
- name: `?CancelAllSynchronousIo@MsiUIMessageContext@@QEAAIXZ`
- size: `532`
- prototype: `unsigned int __fastcall(MsiUIMessageContext *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180009c38`

## callees

- `0x18000b6a0`
- `0x18000c4bc`
- `0x18014ae8c`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000b87d`
- `KERNEL32!CloseHandle` at `0x18000b87d`
- `KERNEL32!GetCurrentThreadId` at `0x18000b6ea`
- `KERNEL32!GetCurrentThreadId` at `0x18000b6ea`
- `KERNEL32!GetLastError` at `0x18000b746`
- `KERNEL32!GetLastError` at `0x18000b7a6`
- `KERNEL32!GetLastError` at `0x18000b7d6`
- `KERNEL32!GetLastError` at `0x18000b822`
- `KERNEL32!GetLastError` at `0x18000b85b`
- `KERNEL32!GetLastError` at `0x18000b86c`
- `KERNEL32!GetLastError` at `0x18000b746`
- `KERNEL32!GetLastError` at `0x18000b7a6`
- `KERNEL32!GetLastError` at `0x18000b7d6`
- `KERNEL32!GetLastError` at `0x18000b822`
- `KERNEL32!GetLastError` at `0x18000b85b`
- `KERNEL32!GetLastError` at `0x18000b86c`
- `KERNEL32!GetCurrentProcessId` at `0x18000b6f9`
- `KERNEL32!GetCurrentProcessId` at `0x18000b6f9`
- `KERNEL32!OpenThread` at `0x18000b789`
- `KERNEL32!OpenThread` at `0x18000b789`

## string_xrefs

- `0x18000b7b2`: `Could not open thread %u while attempting to cancel I/O. Error: %d`
- `0x18000b7e2`: `I/O on thread %u could not be cancelled. Error: %d`

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
0x18000b6a0  mov     [rsp-8+arg_8], rbx
0x18000b6a5  mov     [rsp-8+arg_10], rsi
0x18000b6aa  push    rbp
0x18000b6ab  push    rdi
0x18000b6ac  push    r13
0x18000b6ae  push    r14
0x18000b6b0  push    r15
0x18000b6b2  lea     rbp, [rsp-37h]
0x18000b6b7  sub     rsp, 90h
0x18000b6be  mov     rax, cs:__security_cookie
0x18000b6c5  xor     rax, rsp
0x18000b6c8  mov     [rbp+57h+var_28], rax
0x18000b6cc  cmp     byte ptr [rcx+0E6h], 1
0x18000b6d3  mov     rsi, rcx
0x18000b6d6  jnz     short loc_18000B6DF
0x18000b6d8  xor     eax, eax
0x18000b6da  jmp     loc_18000B88B
0x18000b6df  xorps   xmm0, xmm0
0x18000b6e2  movups  xmmword ptr [rbp+57h+dwThreadId], xmm0
0x18000b6e6  movups  xmmword ptr [rbp+57h+dwThreadId+0Ch], xmm0
0x18000b6ea  call    cs:__imp_GetCurrentThreadId
0x18000b6f1  nop     dword ptr [rax+rax+00h]
0x18000b6f6  mov     r15d, eax
0x18000b6f9  call    cs:__imp_GetCurrentProcessId
0x18000b700  nop     dword ptr [rax+rax+00h]
0x18000b705  mov     r14d, eax
0x18000b708  mov     edx, eax
0x18000b70a  mov     rax, cs:?CreateToolhelp32Snapshot@KERNEL32@@3P6APEAXKK@ZEA; void * (*KERNEL32::CreateToolhelp32Snapshot)(ulong,ulong)
0x18000b711  mov     ecx, 4
0x18000b716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b71b  mov     [rbp+57h+var_50], rax
0x18000b71f  mov     rdi, rax
0x18000b722  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b726  jz      short loc_18000B746
0x18000b728  mov     rcx, rax
0x18000b72b  mov     [rbp+57h+dwThreadId], 1Ch
0x18000b732  mov     rax, cs:?Thread32First@KERNEL32@@3P6AHPEAXPEAUtagTHREADENTRY32@@@ZEA; int (*KERNEL32::Thread32First)(void *,tagTHREADENTRY32 *)
0x18000b739  lea     rdx, [rbp+57h+dwThreadId]
0x18000b73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b742  test    eax, eax
0x18000b744  jnz     short loc_18000B762
0x18000b746  call    cs:__imp_GetLastError
0x18000b74d  nop     dword ptr [rax+rax+00h]
0x18000b752  lea     rcx, [rbp+57h+var_50]; this
0x18000b756  mov     ebx, eax
0x18000b758  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18000b75d  jmp     loc_18000B889
0x18000b762  xor     ebx, ebx
0x18000b764  lea     r13, aNull; "(NULL)"
0x18000b76b  mov     r8d, [rbp+57h+dwThreadId+8]; dwThreadId
0x18000b76f  cmp     r15d, r8d
0x18000b772  jz      loc_18000B839
0x18000b778  cmp     [rbp+57h+dwThreadId+0Ch], r14d
0x18000b77c  jnz     loc_18000B839
0x18000b782  xor     edx, edx; bInheritHandle
0x18000b784  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18000b789  call    cs:__imp_OpenThread
0x18000b790  nop     dword ptr [rax+rax+00h]
0x18000b795  mov     [rbp+57h+var_50], rax
0x18000b799  test    rax, rax
0x18000b79c  jnz     short loc_18000B7BB
0x18000b79e  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18000b7a4  jz      short loc_18000B822
0x18000b7a6  call    cs:__imp_GetLastError
0x18000b7ad  nop     dword ptr [rax+rax+00h]
0x18000b7b2  lea     r9, aCouldNotOpenTh; "Could not open thread %u while attempti"...
0x18000b7b9  jmp     short loc_18000B7E9
0x18000b7bb  mov     rcx, rax
0x18000b7be  mov     rax, cs:?CancelSynchronousIo@KERNEL32@@3P6AHPEAX@ZEA; int (*KERNEL32::CancelSynchronousIo)(void *)
0x18000b7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7ca  test    eax, eax
0x18000b7cc  jnz     short loc_18000B830
0x18000b7ce  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18000b7d4  jz      short loc_18000B822
0x18000b7d6  call    cs:__imp_GetLastError
0x18000b7dd  nop     dword ptr [rax+rax+00h]
0x18000b7e2  lea     r9, aIOOnThreadUCou; "I/O on thread %u could not be cancelled"...
0x18000b7e9  mov     ecx, [rbp+57h+dwThreadId+8]
0x18000b7ec  xor     edx, edx; unsigned __int16
0x18000b7ee  mov     [rsp+0B0h+var_58], rdx; void *
0x18000b7f3  xor     r8d, r8d; int
0x18000b7f6  mov     [rsp+0B0h+var_60], edx; unsigned int
0x18000b7fa  mov     [rsp+0B0h+var_68], r13; unsigned __int16 *
0x18000b7ff  mov     [rsp+0B0h+var_70], r13; unsigned __int16 *
0x18000b804  mov     [rsp+0B0h+var_78], r13; unsigned __int16 *
0x18000b809  mov     eax, eax
0x18000b80b  mov     [rsp+0B0h+var_80], r13; unsigned __int16 *
0x18000b810  mov     [rsp+0B0h+var_88], rax; unsigned __int16 *
0x18000b815  mov     [rsp+0B0h+var_90], rcx; unsigned __int16 *
0x18000b81a  lea     ecx, [rdx+9]; int
0x18000b81d  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18000b822  call    cs:__imp_GetLastError
0x18000b829  nop     dword ptr [rax+rax+00h]
0x18000b82e  mov     ebx, eax
0x18000b830  lea     rcx, [rbp+57h+var_50]; this
0x18000b834  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18000b839  mov     rax, cs:?Thread32Next@KERNEL32@@3P6AHPEAXPEAUtagTHREADENTRY32@@@ZEA; int (*KERNEL32::Thread32Next)(void *,tagTHREADENTRY32 *)
0x18000b840  lea     rdx, [rbp+57h+dwThreadId]
0x18000b844  mov     rcx, rdi
0x18000b847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b84c  test    eax, eax
0x18000b84e  jnz     loc_18000B76B
0x18000b854  mov     byte ptr [rsi+0E6h], 1
0x18000b85b  call    cs:__imp_GetLastError
0x18000b862  nop     dword ptr [rax+rax+00h]
0x18000b867  cmp     eax, 12h
0x18000b86a  jz      short loc_18000B87A
0x18000b86c  call    cs:__imp_GetLastError
0x18000b873  nop     dword ptr [rax+rax+00h]
0x18000b878  mov     ebx, eax
0x18000b87a  mov     rcx, rdi; hObject
0x18000b87d  call    cs:__imp_CloseHandle
0x18000b884  nop     dword ptr [rax+rax+00h]
0x18000b889  mov     eax, ebx
0x18000b88b  mov     rcx, [rbp+57h+var_28]
0x18000b88f  xor     rcx, rsp; StackCookie
0x18000b892  call    __security_check_cookie
0x18000b897  lea     r11, [rsp+0B0h+var_20]
0x18000b89f  mov     rbx, [r11+38h]
0x18000b8a3  mov     rsi, [r11+40h]
0x18000b8a7  mov     rsp, r11
0x18000b8aa  pop     r15
0x18000b8ac  pop     r14
0x18000b8ae  pop     r13
0x18000b8b0  pop     rdi
0x18000b8b1  pop     rbp
0x18000b8b2  retn
```
