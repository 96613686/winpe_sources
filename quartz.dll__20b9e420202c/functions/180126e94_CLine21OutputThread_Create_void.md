# CLine21OutputThread::Create(void)

- ea: `0x180126e94`
- end: `0x180126fd6`
- name: `?Create@CLine21OutputThread@@QEAAHXZ`
- size: `322`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801287d0`

## callees

- `0x180126e94`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180126f25`
- `KERNEL32!CreateThread` at `0x180126f25`
- `KERNEL32!CreateEventW` at `0x180126ec7`
- `KERNEL32!CreateEventW` at `0x180126ee1`
- `KERNEL32!CreateEventW` at `0x180126ec7`
- `KERNEL32!CreateEventW` at `0x180126ee1`
- `KERNEL32!LeaveCriticalSection` at `0x180126f61`
- `KERNEL32!LeaveCriticalSection` at `0x180126fbc`
- `KERNEL32!LeaveCriticalSection` at `0x180126f61`
- `KERNEL32!LeaveCriticalSection` at `0x180126fbc`
- `KERNEL32!EnterCriticalSection` at `0x180126ea1`
- `KERNEL32!EnterCriticalSection` at `0x180126ea1`
- `KERNEL32!CloseHandle` at `0x180126f4a`
- `KERNEL32!CloseHandle` at `0x180126f86`
- `KERNEL32!CloseHandle` at `0x180126fa3`
- `KERNEL32!CloseHandle` at `0x180126f4a`
- `KERNEL32!CloseHandle` at `0x180126f86`
- `KERNEL32!CloseHandle` at `0x180126fa3`
- `KERNEL32!GetLastError` at `0x180126f3a`
- `KERNEL32!GetLastError` at `0x180126f71`
- `KERNEL32!GetLastError` at `0x180126f3a`
- `KERNEL32!GetLastError` at `0x180126f71`

## pseudocode

```c
__int64 __fastcall CLine21OutputThread::Create(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // edi
  HANDLE EventW; // rax
  bool v4; // zf
  struct _RTL_CRITICAL_SECTION_DEBUG *v5; // rax
  HANDLE OwningThread; // rcx
  void *v8; // rcx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  EnterCriticalSection(lpCriticalSection);
  v2 = 1;
  if ( !lpCriticalSection[1].DebugInfo )
  {
    *(_QWORD *)&lpCriticalSection[1].LockCount = CreateEventW(0, 1, 0, 0);
    EventW = CreateEventW(0, 1, 0, 0);
    v4 = *(_QWORD *)&lpCriticalSection[1].LockCount == 0;
    lpCriticalSection[1].OwningThread = EventW;
    if ( v4 || !EventW )
    {
      GetLastError();
      OwningThread = lpCriticalSection[1].OwningThread;
      if ( OwningThread )
      {
        CloseHandle(OwningThread);
        lpCriticalSection[1].OwningThread = 0;
      }
      v8 = *(void **)&lpCriticalSection[1].LockCount;
      if ( v8 )
      {
        CloseHandle(v8);
        *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
      }
      v2 = 0;
    }
    else
    {
      ThreadId = 0;
      v5 = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateThread(
                                                   0,
                                                   0,
                                                   CLine21OutputThread::InitialThreadProc,
                                                   lpCriticalSection,
                                                   0,
                                                   &ThreadId);
      lpCriticalSection[1].DebugInfo = v5;
      if ( !v5 )
      {
        GetLastError();
        CloseHandle(*(HANDLE *)&lpCriticalSection[1].LockCount);
        *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
        LeaveCriticalSection(lpCriticalSection);
        return 0;
      }
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x180126e94  mov     [rsp+arg_8], rbx
0x180126e99  push    rdi
0x180126e9a  sub     rsp, 30h
0x180126e9e  mov     rbx, rcx
0x180126ea1  call    cs:__imp_EnterCriticalSection
0x180126ea8  nop     dword ptr [rax+rax+00h]
0x180126ead  cmp     qword ptr [rbx+28h], 0
0x180126eb2  mov     edi, 1
0x180126eb7  jnz     loc_180126FB9
0x180126ebd  xor     r9d, r9d; lpName
0x180126ec0  xor     r8d, r8d; bInitialState
0x180126ec3  mov     edx, edi; bManualReset
0x180126ec5  xor     ecx, ecx; lpEventAttributes
0x180126ec7  call    cs:__imp_CreateEventW
0x180126ece  nop     dword ptr [rax+rax+00h]
0x180126ed3  xor     r9d, r9d; lpName
0x180126ed6  xor     r8d, r8d; bInitialState
0x180126ed9  mov     edx, edi; bManualReset
0x180126edb  mov     [rbx+30h], rax
0x180126edf  xor     ecx, ecx; lpEventAttributes
0x180126ee1  call    cs:__imp_CreateEventW
0x180126ee8  nop     dword ptr [rax+rax+00h]
0x180126eed  cmp     qword ptr [rbx+30h], 0
0x180126ef2  mov     [rbx+38h], rax
0x180126ef6  jz      short loc_180126F71
0x180126ef8  test    rax, rax
0x180126efb  jz      short loc_180126F71
0x180126efd  lea     rax, [rsp+38h+ThreadId]
0x180126f02  mov     [rsp+38h+ThreadId], 0
0x180126f0a  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180126f0f  lea     r8, ?InitialThreadProc@CLine21OutputThread@@SAKPEAV1@@Z; lpStartAddress
0x180126f16  mov     r9, rbx; lpParameter
0x180126f19  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180126f21  xor     edx, edx; dwStackSize
0x180126f23  xor     ecx, ecx; lpThreadAttributes
0x180126f25  call    cs:__imp_CreateThread
0x180126f2c  nop     dword ptr [rax+rax+00h]
0x180126f31  mov     [rbx+28h], rax
0x180126f35  test    rax, rax
0x180126f38  jnz     short loc_180126FB9
0x180126f3a  call    cs:__imp_GetLastError
0x180126f41  nop     dword ptr [rax+rax+00h]
0x180126f46  mov     rcx, [rbx+30h]; hObject
0x180126f4a  call    cs:__imp_CloseHandle
0x180126f51  nop     dword ptr [rax+rax+00h]
0x180126f56  mov     rcx, rbx; lpCriticalSection
0x180126f59  mov     qword ptr [rbx+30h], 0
0x180126f61  call    cs:__imp_LeaveCriticalSection
0x180126f68  nop     dword ptr [rax+rax+00h]
0x180126f6d  xor     eax, eax
0x180126f6f  jmp     short loc_180126FCA
0x180126f71  call    cs:__imp_GetLastError
0x180126f78  nop     dword ptr [rax+rax+00h]
0x180126f7d  mov     rcx, [rbx+38h]; hObject
0x180126f81  test    rcx, rcx
0x180126f84  jz      short loc_180126F9A
0x180126f86  call    cs:__imp_CloseHandle
0x180126f8d  nop     dword ptr [rax+rax+00h]
0x180126f92  mov     qword ptr [rbx+38h], 0
0x180126f9a  mov     rcx, [rbx+30h]; hObject
0x180126f9e  test    rcx, rcx
0x180126fa1  jz      short loc_180126FB7
0x180126fa3  call    cs:__imp_CloseHandle
0x180126faa  nop     dword ptr [rax+rax+00h]
0x180126faf  mov     qword ptr [rbx+30h], 0
0x180126fb7  xor     edi, edi
0x180126fb9  mov     rcx, rbx; lpCriticalSection
0x180126fbc  call    cs:__imp_LeaveCriticalSection
0x180126fc3  nop     dword ptr [rax+rax+00h]
0x180126fc8  mov     eax, edi
0x180126fca  mov     rbx, [rsp+38h+arg_8]
0x180126fcf  add     rsp, 30h
0x180126fd3  pop     rdi
0x180126fd4  retn
```
