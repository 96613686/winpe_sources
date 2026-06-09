# InetInitializeResource

- ea: `0x1800151a0`
- end: `0x180015274`
- name: `InetInitializeResource`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180015180`
- `0x180019cc0`

## callees

- `0x1800151a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015201`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015234`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015201`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015234`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800151b2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800151b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015247`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015247`

## pseudocode

```c
__int64 __fastcall InetInitializeResource(__int64 a1)
{
  HANDLE Semaphore; // rax
  HANDLE v3; // rax
  __int64 result; // rax

  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)a1, 0x3E8u) )
    return 0;
  if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    **(_WORD **)a1 = 1;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  *(_QWORD *)(a1 + 40) = Semaphore;
  if ( !Semaphore )
    return 0;
  *(_DWORD *)(a1 + 48) = 0;
  v3 = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  *(_QWORD *)(a1 + 56) = v3;
  if ( !v3 )
  {
    CloseHandle(*(HANDLE *)(a1 + 40));
    return 0;
  }
  *(_DWORD *)(a1 + 64) = 0;
  result = 1;
  *(_DWORD *)(a1 + 68) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  return result;
}

```

## disassembly

```asm
0x1800151a0  mov     [rsp+arg_0], rbx
0x1800151a5  push    rsi
0x1800151a6  sub     rsp, 30h
0x1800151aa  mov     edx, 3E8h; dwSpinCount
0x1800151af  mov     rbx, rcx
0x1800151b2  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800151b8  test    eax, eax
0x1800151ba  jz      loc_18001524D
0x1800151c0  mov     rcx, [rbx]
0x1800151c3  mov     esi, 1
0x1800151c8  lea     rax, [rcx-1]
0x1800151cc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800151d0  ja      short loc_1800151D5
0x1800151d2  mov     [rcx], si
0x1800151d5  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800151dd  xor     r9d, r9d; lpName
0x1800151e0  xor     edx, edx; lInitialCount
0x1800151e2  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800151ea  xor     ecx, ecx; lpSemaphoreAttributes
0x1800151ec  mov     qword ptr [rbx+58h], 0
0x1800151f4  mov     r8d, 7FFFFFFFh; lMaximumCount
0x1800151fa  mov     dword ptr [rbx+50h], 0
0x180015201  call    cs:__imp_CreateSemaphoreExW
0x180015207  mov     [rbx+28h], rax
0x18001520b  test    rax, rax
0x18001520e  jz      short loc_18001524D
0x180015210  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180015218  xor     r9d, r9d; lpName
0x18001521b  xor     edx, edx; lInitialCount
0x18001521d  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180015225  xor     ecx, ecx; lpSemaphoreAttributes
0x180015227  mov     dword ptr [rbx+30h], 0
0x18001522e  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180015234  call    cs:__imp_CreateSemaphoreExW
0x18001523a  mov     [rbx+38h], rax
0x18001523e  test    rax, rax
0x180015241  jnz     short loc_18001525A
0x180015243  mov     rcx, [rbx+28h]; hObject
0x180015247  call    cs:__imp_CloseHandle
0x18001524d  xor     eax, eax
0x18001524f  mov     rbx, [rsp+38h+arg_0]
0x180015254  add     rsp, 30h
0x180015258  pop     rsi
0x180015259  retn
0x18001525a  mov     dword ptr [rbx+40h], 0
0x180015261  mov     eax, esi
0x180015263  mov     dword ptr [rbx+44h], 0
0x18001526a  mov     qword ptr [rbx+48h], 0
0x180015272  jmp     short loc_18001524F
```
