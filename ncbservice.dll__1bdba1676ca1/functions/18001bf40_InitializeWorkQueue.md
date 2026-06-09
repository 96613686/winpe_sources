# InitializeWorkQueue

- ea: `0x18001bf40`
- end: `0x18001bfb0`
- name: `InitializeWorkQueue`
- size: `112`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800164a4`
- `0x18001ae2c`

## callees

- `0x18001bf40`
- `0x18001e368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001bf7e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001bf7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bf60`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bf60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf71`

## pseudocode

```c
__int64 __fastcall InitializeWorkQueue(LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE EventW; // rax
  __int64 result; // rax

  memset_0(lpCriticalSection, 0, 0x58u);
  EventW = CreateEventW(0, 1, 1, 0);
  *(_QWORD *)&lpCriticalSection[1].LockCount = EventW;
  if ( EventW )
  {
    InitializeCriticalSection(lpCriticalSection);
    LODWORD(lpCriticalSection[1].DebugInfo) = 1;
    lpCriticalSection[1].SpinCount = (ULONG_PTR)&lpCriticalSection[1].LockSemaphore;
    result = 1;
    lpCriticalSection[1].LockSemaphore = &lpCriticalSection[1].LockSemaphore;
    LODWORD(lpCriticalSection[1].OwningThread) = 0;
    lpCriticalSection[2].DebugInfo = 0;
  }
  else
  {
    CloseHandle(0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001bf40  push    rbx
0x18001bf42  sub     rsp, 20h
0x18001bf46  xor     edx, edx; Val
0x18001bf48  mov     rbx, rcx
0x18001bf4b  lea     r8d, [rdx+58h]; Size
0x18001bf4f  call    memset_0
0x18001bf54  xor     r9d, r9d; lpName
0x18001bf57  xor     ecx, ecx; lpEventAttributes
0x18001bf59  lea     edx, [r9+1]; bManualReset
0x18001bf5d  mov     r8d, edx; bInitialState
0x18001bf60  call    cs:__imp_CreateEventW
0x18001bf66  mov     [rbx+30h], rax
0x18001bf6a  test    rax, rax
0x18001bf6d  jnz     short loc_18001BF7B
0x18001bf6f  xor     ecx, ecx; hObject
0x18001bf71  call    cs:__imp_CloseHandle
0x18001bf77  xor     eax, eax
0x18001bf79  jmp     short loc_18001BFAA
0x18001bf7b  mov     rcx, rbx; lpCriticalSection
0x18001bf7e  call    cs:__imp_InitializeCriticalSection
0x18001bf84  lea     rcx, [rbx+40h]
0x18001bf88  mov     dword ptr [rbx+28h], 1
0x18001bf8f  mov     [rcx+8], rcx
0x18001bf93  mov     eax, 1
0x18001bf98  mov     [rcx], rcx
0x18001bf9b  mov     dword ptr [rbx+38h], 0
0x18001bfa2  mov     qword ptr [rbx+50h], 0
0x18001bfaa  add     rsp, 20h
0x18001bfae  pop     rbx
0x18001bfaf  retn
```
