# acmDriverOpen

- ea: `0x180002470`
- end: `0x18000252d`
- name: `acmDriverOpen`
- size: `189`
- prototype: `MMRESULT __stdcall(LPHACMDRIVER phad, HACMDRIVERID hadid, DWORD fdwOpen)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cfe0`

## callees

- `0x180002470`
- `0x180003e80`
- `0x180003ec0`
- `0x180003f40`
- `0x180005530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024d5`

## pseudocode

```c
MMRESULT __stdcall acmDriverOpen(LPHACMDRIVER phad, HACMDRIVERID hadid, DWORD fdwOpen)
{
  MMRESULT v7; // ebx

  if ( !(unsigned int)ValidateWritePointer(phad, 8) )
    return 11;
  *phad = 0;
  if ( !(unsigned int)ValidateHandle(hadid, 1) )
    return 5;
  if ( fdwOpen )
    return 10;
  if ( !pagFindAndBoot() )
    return 1;
  EnterCriticalSection((LPCRITICAL_SECTION)hadid - 1);
  v7 = IDriverOpen((__int64 *)phad, (__int64)hadid, 0);
  LeaveCriticalSection((LPCRITICAL_SECTION)hadid - 1);
  return v7;
}

```

## disassembly

```asm
0x180002470  mov     [rsp+arg_0], rbx
0x180002475  mov     [rsp+arg_8], rsi
0x18000247a  push    rdi
0x18000247b  sub     rsp, 20h
0x18000247f  mov     rsi, rdx
0x180002482  mov     edi, r8d
0x180002485  mov     edx, 8
0x18000248a  mov     rbx, rcx
0x18000248d  call    ValidateWritePointer
0x180002492  test    eax, eax
0x180002494  jnz     short loc_1800024AB
0x180002496  mov     eax, 0Bh
0x18000249b  mov     rbx, [rsp+28h+arg_0]
0x1800024a0  mov     rsi, [rsp+28h+arg_8]
0x1800024a5  add     rsp, 20h
0x1800024a9  pop     rdi
0x1800024aa  retn
0x1800024ab  mov     edx, 1
0x1800024b0  mov     qword ptr [rbx], 0
0x1800024b7  mov     rcx, rsi
0x1800024ba  call    ValidateHandle
0x1800024bf  test    eax, eax
0x1800024c1  jz      short loc_18000250E
0x1800024c3  test    edi, edi
0x1800024c5  jnz     short loc_1800024F9
0x1800024c7  call    pagFindAndBoot
0x1800024cc  test    rax, rax
0x1800024cf  jz      short loc_180002523
0x1800024d1  lea     rcx, [rsi-28h]; lpCriticalSection
0x1800024d5  call    cs:__imp_EnterCriticalSection
0x1800024db  xor     r8d, r8d
0x1800024de  mov     rdx, rsi
0x1800024e1  mov     rcx, rbx
0x1800024e4  call    IDriverOpen
0x1800024e9  lea     rcx, [rsi-28h]; lpCriticalSection
0x1800024ed  mov     ebx, eax
0x1800024ef  call    cs:__imp_LeaveCriticalSection
0x1800024f5  mov     eax, ebx
0x1800024f7  jmp     short loc_18000249B
0x1800024f9  mov     eax, 0Ah
0x1800024fe  mov     rbx, [rsp+28h+arg_0]
0x180002503  mov     rsi, [rsp+28h+arg_8]
0x180002508  add     rsp, 20h
0x18000250c  pop     rdi
0x18000250d  retn
0x18000250e  mov     rbx, [rsp+28h+arg_0]
0x180002513  mov     eax, 5
0x180002518  mov     rsi, [rsp+28h+arg_8]
0x18000251d  add     rsp, 20h
0x180002521  pop     rdi
0x180002522  retn
0x180002523  mov     eax, 1
0x180002528  jmp     loc_18000249B
```
