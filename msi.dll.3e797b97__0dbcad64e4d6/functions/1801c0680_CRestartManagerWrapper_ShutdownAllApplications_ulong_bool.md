# CRestartManagerWrapper::ShutdownAllApplications(ulong,bool)

- ea: `0x1801c0680`
- end: `0x1801c07d4`
- name: `?ShutdownAllApplications@CRestartManagerWrapper@@UEAAIK_N@Z`
- size: `340`
- prototype: `unsigned int __fastcall(CRestartManagerWrapper *__hidden this, unsigned int, bool)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18013d2f0`
- `0x1801c0680`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1801c06c4`
- `KERNEL32!LeaveCriticalSection` at `0x1801c077d`
- `KERNEL32!LeaveCriticalSection` at `0x1801c06c4`
- `KERNEL32!LeaveCriticalSection` at `0x1801c077d`
- `KERNEL32!GetExitCodeThread` at `0x1801c07af`
- `KERNEL32!GetExitCodeThread` at `0x1801c07af`
- `KERNEL32!GetLastError` at `0x1801c07c3`
- `KERNEL32!GetLastError` at `0x1801c07c3`
- `KERNEL32!EnterCriticalSection` at `0x1801c069b`
- `KERNEL32!EnterCriticalSection` at `0x1801c069b`
- `KERNEL32!WaitForSingleObject` at `0x1801c078f`
- `KERNEL32!WaitForSingleObject` at `0x1801c078f`
- `KERNEL32!CreateThread` at `0x1801c073d`
- `KERNEL32!CreateThread` at `0x1801c073d`

## pseudocode

```c
unsigned int __fastcall CRestartManagerWrapper::ShutdownAllApplications(CRestartManagerWrapper *this, int a2, char a3)
{
  bool v6; // zf
  unsigned int result; // eax
  int v8; // esi
  HANDLE *v9; // rdi
  HANDLE v10; // rax
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+68h] [rbp+20h] BYREF

  EnterCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  v6 = *((_BYTE *)this + 84) == 0;
  ExitCode = 0;
  if ( !v6 )
  {
    ExitCode = 5;
LABEL_3:
    LeaveCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
    return ExitCode;
  }
  v8 = 1;
  if ( (unsigned int)(*((_DWORD *)this + 20) - 3) > 1 )
  {
    ExitCode = 22;
    goto LABEL_3;
  }
  *((_DWORD *)this + 199) = a2;
  v9 = (HANDLE *)((char *)this + 800);
  v6 = *((_QWORD *)this + 100) == 0;
  *((_DWORD *)this + 20) = 5;
  ThreadId = 0;
  if ( !v6
    || (v10 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ShutdownAppsThreadStart, this, 0, &ThreadId),
        CHandle::operator=((char *)this + 800, v10),
        *v9) )
  {
    *((_BYTE *)this + 788) = a3;
    v8 = 3;
  }
  *((_DWORD *)this + 22) = v8;
  if ( g_scServerContext != 2 )
    goto LABEL_3;
  LeaveCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  result = WaitForSingleObject(*v9, 0xFFFFFFFF);
  ExitCode = result;
  if ( !result )
  {
    if ( !GetExitCodeThread(*v9, &ExitCode) )
      return GetLastError();
    return ExitCode;
  }
  return result;
}

```

## disassembly

```asm
0x1801c0680  mov     [rsp+arg_8], rbx
0x1801c0685  push    rbp
0x1801c0686  push    rsi
0x1801c0687  push    rdi
0x1801c0688  sub     rsp, 30h
0x1801c068c  mov     rbx, rcx
0x1801c068f  mov     bpl, r8b
0x1801c0692  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801c0699  mov     edi, edx
0x1801c069b  call    cs:__imp_EnterCriticalSection
0x1801c06a2  nop     dword ptr [rax+rax+00h]
0x1801c06a7  cmp     byte ptr [rbx+54h], 0
0x1801c06ab  mov     [rsp+48h+ExitCode], 0
0x1801c06b3  jz      short loc_1801C06E2
0x1801c06b5  mov     [rsp+48h+ExitCode], 5
0x1801c06bd  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801c06c4  call    cs:__imp_LeaveCriticalSection
0x1801c06cb  nop     dword ptr [rax+rax+00h]
0x1801c06d0  mov     eax, [rsp+48h+ExitCode]
0x1801c06d4  mov     rbx, [rsp+48h+arg_8]
0x1801c06d9  add     rsp, 30h
0x1801c06dd  pop     rdi
0x1801c06de  pop     rsi
0x1801c06df  pop     rbp
0x1801c06e0  retn
0x1801c06e2  mov     eax, [rbx+50h]
0x1801c06e5  mov     esi, 1
0x1801c06ea  sub     eax, 3
0x1801c06ed  cmp     eax, esi
0x1801c06ef  jbe     short loc_1801C06FB
0x1801c06f1  mov     [rsp+48h+ExitCode], 16h
0x1801c06f9  jmp     short loc_1801C06BD
0x1801c06fb  mov     [rbx+31Ch], edi
0x1801c0701  lea     rdi, [rbx+320h]
0x1801c0708  cmp     qword ptr [rdi], 0
0x1801c070c  mov     dword ptr [rbx+50h], 5
0x1801c0713  mov     [rsp+48h+ThreadId], 0
0x1801c071b  jnz     short loc_1801C075A
0x1801c071d  lea     rax, [rsp+48h+ThreadId]
0x1801c0722  mov     r9, rbx; lpParameter
0x1801c0725  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1801c072a  lea     r8, ?ShutdownAppsThreadStart@@YAKPEAX@Z; lpStartAddress
0x1801c0731  xor     edx, edx; dwStackSize
0x1801c0733  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1801c073b  xor     ecx, ecx; lpThreadAttributes
0x1801c073d  call    cs:__imp_CreateThread
0x1801c0744  nop     dword ptr [rax+rax+00h]
0x1801c0749  mov     rdx, rax
0x1801c074c  mov     rcx, rdi
0x1801c074f  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x1801c0754  cmp     qword ptr [rdi], 0
0x1801c0758  jz      short loc_1801C0766
0x1801c075a  mov     [rbx+314h], bpl
0x1801c0761  mov     esi, 3
0x1801c0766  mov     [rbx+58h], esi
0x1801c0769  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1801c0770  jnz     loc_1801C06BD
0x1801c0776  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801c077d  call    cs:__imp_LeaveCriticalSection
0x1801c0784  nop     dword ptr [rax+rax+00h]
0x1801c0789  mov     rcx, [rdi]; hHandle
0x1801c078c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801c078f  call    cs:__imp_WaitForSingleObject
0x1801c0796  nop     dword ptr [rax+rax+00h]
0x1801c079b  mov     [rsp+48h+ExitCode], eax
0x1801c079f  test    eax, eax
0x1801c07a1  jnz     loc_1801C06D4
0x1801c07a7  mov     rcx, [rdi]; hThread
0x1801c07aa  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x1801c07af  call    cs:__imp_GetExitCodeThread
0x1801c07b6  nop     dword ptr [rax+rax+00h]
0x1801c07bb  test    eax, eax
0x1801c07bd  jnz     loc_1801C06D0
0x1801c07c3  call    cs:__imp_GetLastError
0x1801c07ca  nop     dword ptr [rax+rax+00h]
0x1801c07cf  jmp     loc_1801C06D4
```
