# CLine21InSampleQueue::Create(void)

- ea: `0x180126de8`
- end: `0x180126e8e`
- name: `?Create@CLine21InSampleQueue@@QEAAHXZ`
- size: `166`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180127ec0`

## callees

- `0x180126de8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180126e0f`
- `KERNEL32!CreateEventW` at `0x180126e41`
- `KERNEL32!CreateEventW` at `0x180126e0f`
- `KERNEL32!CreateEventW` at `0x180126e41`
- `KERNEL32!LeaveCriticalSection` at `0x180126e27`
- `KERNEL32!LeaveCriticalSection` at `0x180126e74`
- `KERNEL32!LeaveCriticalSection` at `0x180126e27`
- `KERNEL32!LeaveCriticalSection` at `0x180126e74`
- `KERNEL32!EnterCriticalSection` at `0x180126df5`
- `KERNEL32!EnterCriticalSection` at `0x180126df5`
- `KERNEL32!CloseHandle` at `0x180126e5a`
- `KERNEL32!CloseHandle` at `0x180126e5a`

## pseudocode

```c
__int64 __fastcall CLine21InSampleQueue::Create(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // edi
  struct _RTL_CRITICAL_SECTION_DEBUG *EventW; // rax
  HANDLE v5; // rax

  EnterCriticalSection(lpCriticalSection);
  v2 = 1;
  EventW = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventW(0, 1, 0, 0);
  lpCriticalSection[1].DebugInfo = EventW;
  if ( EventW )
  {
    v5 = CreateEventW(0, 1, 1, 0);
    *(_QWORD *)&lpCriticalSection[1].LockCount = v5;
    if ( v5 )
    {
      LODWORD(lpCriticalSection[1].OwningThread) = 0;
    }
    else
    {
      CloseHandle(lpCriticalSection[1].DebugInfo);
      v2 = 0;
    }
    LeaveCriticalSection(lpCriticalSection);
    return v2;
  }
  else
  {
    LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
}

```

## disassembly

```asm
0x180126de8  mov     [rsp+arg_0], rbx
0x180126ded  push    rdi
0x180126dee  sub     rsp, 20h
0x180126df2  mov     rbx, rcx
0x180126df5  call    cs:__imp_EnterCriticalSection
0x180126dfc  nop     dword ptr [rax+rax+00h]
0x180126e01  xor     r9d, r9d; lpName
0x180126e04  xor     r8d, r8d; bInitialState
0x180126e07  xor     ecx, ecx; lpEventAttributes
0x180126e09  lea     edi, [r9+1]
0x180126e0d  mov     edx, edi; bManualReset
0x180126e0f  call    cs:__imp_CreateEventW
0x180126e16  nop     dword ptr [rax+rax+00h]
0x180126e1b  mov     [rbx+28h], rax
0x180126e1f  test    rax, rax
0x180126e22  jnz     short loc_180126E37
0x180126e24  mov     rcx, rbx; lpCriticalSection
0x180126e27  call    cs:__imp_LeaveCriticalSection
0x180126e2e  nop     dword ptr [rax+rax+00h]
0x180126e33  xor     eax, eax
0x180126e35  jmp     short loc_180126E82
0x180126e37  xor     r9d, r9d; lpName
0x180126e3a  mov     r8d, edi; bInitialState
0x180126e3d  mov     edx, edi; bManualReset
0x180126e3f  xor     ecx, ecx; lpEventAttributes
0x180126e41  call    cs:__imp_CreateEventW
0x180126e48  nop     dword ptr [rax+rax+00h]
0x180126e4d  mov     [rbx+30h], rax
0x180126e51  test    rax, rax
0x180126e54  jnz     short loc_180126E6A
0x180126e56  mov     rcx, [rbx+28h]; hObject
0x180126e5a  call    cs:__imp_CloseHandle
0x180126e61  nop     dword ptr [rax+rax+00h]
0x180126e66  xor     edi, edi
0x180126e68  jmp     short loc_180126E71
0x180126e6a  mov     dword ptr [rbx+38h], 0
0x180126e71  mov     rcx, rbx; lpCriticalSection
0x180126e74  call    cs:__imp_LeaveCriticalSection
0x180126e7b  nop     dword ptr [rax+rax+00h]
0x180126e80  mov     eax, edi
0x180126e82  mov     rbx, [rsp+28h+arg_0]
0x180126e87  add     rsp, 20h
0x180126e8b  pop     rdi
0x180126e8c  retn
```
