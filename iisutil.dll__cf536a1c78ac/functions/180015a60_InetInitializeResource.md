# InetInitializeResource

- ea: `0x180015a60`
- end: `0x180015b4d`
- name: `InetInitializeResource`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180015a40`
- `0x18001ab40`

## callees

- `0x180015a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015ac7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015b00`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015ac7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180015b00`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180015a72`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180015a72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015b19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015b19`

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
0x180015a60  mov     [rsp+arg_0], rbx
0x180015a65  push    rsi
0x180015a66  sub     rsp, 30h
0x180015a6a  mov     edx, 3E8h; dwSpinCount
0x180015a6f  mov     rbx, rcx
0x180015a72  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180015a79  nop     dword ptr [rax+rax+00h]
0x180015a7e  test    eax, eax
0x180015a80  jz      loc_180015B25
0x180015a86  mov     rcx, [rbx]
0x180015a89  mov     esi, 1
0x180015a8e  lea     rax, [rcx-1]
0x180015a92  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015a96  ja      short loc_180015A9B
0x180015a98  mov     [rcx], si
0x180015a9b  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180015aa3  xor     r9d, r9d; lpName
0x180015aa6  xor     edx, edx; lInitialCount
0x180015aa8  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180015ab0  xor     ecx, ecx; lpSemaphoreAttributes
0x180015ab2  mov     qword ptr [rbx+58h], 0
0x180015aba  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180015ac0  mov     dword ptr [rbx+50h], 0
0x180015ac7  call    cs:__imp_CreateSemaphoreExW
0x180015ace  nop     dword ptr [rax+rax+00h]
0x180015ad3  mov     [rbx+28h], rax
0x180015ad7  test    rax, rax
0x180015ada  jz      short loc_180015B25
0x180015adc  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180015ae4  xor     r9d, r9d; lpName
0x180015ae7  xor     edx, edx; lInitialCount
0x180015ae9  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180015af1  xor     ecx, ecx; lpSemaphoreAttributes
0x180015af3  mov     dword ptr [rbx+30h], 0
0x180015afa  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180015b00  call    cs:__imp_CreateSemaphoreExW
0x180015b07  nop     dword ptr [rax+rax+00h]
0x180015b0c  mov     [rbx+38h], rax
0x180015b10  test    rax, rax
0x180015b13  jnz     short loc_180015B33
0x180015b15  mov     rcx, [rbx+28h]; hObject
0x180015b19  call    cs:__imp_CloseHandle
0x180015b20  nop     dword ptr [rax+rax+00h]
0x180015b25  xor     eax, eax
0x180015b27  mov     rbx, [rsp+38h+arg_0]
0x180015b2c  add     rsp, 30h
0x180015b30  pop     rsi
0x180015b31  retn
0x180015b33  mov     dword ptr [rbx+40h], 0
0x180015b3a  mov     eax, esi
0x180015b3c  mov     dword ptr [rbx+44h], 0
0x180015b43  mov     qword ptr [rbx+48h], 0
0x180015b4b  jmp     short loc_180015B27
```
