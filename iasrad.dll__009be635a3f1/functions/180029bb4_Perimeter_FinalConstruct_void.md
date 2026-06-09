# Perimeter::FinalConstruct(void)

- ea: `0x180029bb4`
- end: `0x180029c2b`
- name: `?FinalConstruct@Perimeter@@QEAAJXZ`
- size: `119`
- prototype: `__int64 __fastcall(Perimeter *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b560`
- `0x180014d54`
- `0x180020ebc`

## callees

- `0x180029bb4`

## import_xrefs

- `KERNEL32!CreateSemaphoreW` at `0x180029bca`
- `KERNEL32!CreateSemaphoreW` at `0x180029bfa`
- `KERNEL32!CreateSemaphoreW` at `0x180029bca`
- `KERNEL32!CreateSemaphoreW` at `0x180029bfa`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180029c12`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180029c12`
- `KERNEL32!GetLastError` at `0x180029bd9`
- `KERNEL32!GetLastError` at `0x180029bd9`

## pseudocode

```c
signed int __fastcall Perimeter::FinalConstruct(Perimeter *this)
{
  HANDLE SemaphoreW; // rax
  signed int result; // eax
  HANDLE v4; // rax

  SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
  *((_QWORD *)this + 6) = SemaphoreW;
  if ( SemaphoreW
    && (v4 = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0), (*((_QWORD *)this + 7) = v4) != 0)
    && InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 8), 0x1000u) )
  {
    *((_DWORD *)this + 19) = 1;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180029bb4  push    rbx
0x180029bb6  sub     rsp, 20h
0x180029bba  mov     rbx, rcx
0x180029bbd  xor     r9d, r9d; lpName
0x180029bc0  xor     ecx, ecx; lpSemaphoreAttributes
0x180029bc2  xor     edx, edx; lInitialCount
0x180029bc4  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180029bca  call    cs:__imp_CreateSemaphoreW
0x180029bd0  mov     [rbx+30h], rax
0x180029bd4  test    rax, rax
0x180029bd7  jnz     short loc_180029BED
0x180029bd9  call    cs:__imp_GetLastError
0x180029bdf  test    eax, eax
0x180029be1  jle     short loc_180029C25
0x180029be3  movzx   eax, ax
0x180029be6  or      eax, 80070000h
0x180029beb  jmp     short loc_180029C25
0x180029bed  xor     r9d, r9d; lpName
0x180029bf0  xor     edx, edx; lInitialCount
0x180029bf2  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180029bf8  xor     ecx, ecx; lpSemaphoreAttributes
0x180029bfa  call    cs:__imp_CreateSemaphoreW
0x180029c00  mov     [rbx+38h], rax
0x180029c04  test    rax, rax
0x180029c07  jz      short loc_180029BD9
0x180029c09  lea     rcx, [rbx+8]; lpCriticalSection
0x180029c0d  mov     edx, 1000h; dwSpinCount
0x180029c12  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180029c18  test    eax, eax
0x180029c1a  jz      short loc_180029BD9
0x180029c1c  mov     dword ptr [rbx+4Ch], 1
0x180029c23  xor     eax, eax
0x180029c25  add     rsp, 20h
0x180029c29  pop     rbx
0x180029c2a  retn
```
