# AllocateMemory

- ea: `0x14000c62c`
- end: `0x14000c6c8`
- name: `AllocateMemory`
- size: `156`
- prototype: `LPVOID __fastcall(SIZE_T dwBytes)`
- caller_count: `32`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e90`
- `0x140002070`
- `0x1400024a4`
- `0x140002940`
- `0x14000329c`
- `0x140003a58`
- `0x14000406c`
- `0x140004bbc`
- `0x1400053e0`
- `0x1400055f8`
- `0x140005940`
- `0x140005e84`
- `0x14000612c`
- `0x140006394`
- `0x140006a5c`
- `0x140007170`
- `0x14000752c`
- `0x140007834`
- `0x140007be0`
- `0x140008320`
- `0x140008b4c`
- `0x140008dfc`
- `0x140008f10`
- `0x140008fe8`
- `0x140009ae4`
- `0x140009d40`
- `0x14000a3f8`
- `0x14000caa8`
- `0x14000e604`
- `0x14000e7a4`
- `0x14000e994`
- `0x14000ea5c`

## callees

- `0x14000c62c`
- `0x14000d978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c67b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c6ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c67b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c6ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c645`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c688`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c69e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c6ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c645`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c688`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c69e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c6ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c64d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c64d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c667`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c667`

## pseudocode

```c
LPVOID __fastcall AllocateMemory(SIZE_T dwBytes)
{
  SIZE_T v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = (unsigned int)dwBytes;
  if ( !(_DWORD)dwBytes )
  {
    if ( !GetLastError() )
      SetLastError(0x57u);
    return 0;
  }
  ProcessHeap = GetProcessHeap();
  if ( !ProcessHeap )
    return 0;
  return HeapAlloc(ProcessHeap, 0xCu, v1);
}

```

## disassembly

```asm
0x14000c62c  push    rbx
0x14000c62e  sub     rsp, 30h
0x14000c632  mov     ebx, ecx
0x14000c634  test    ecx, ecx
0x14000c636  jnz     short loc_14000C64D
0x14000c638  call    cs:__imp_GetLastError
0x14000c63e  test    eax, eax
0x14000c640  jnz     short loc_14000C658
0x14000c642  lea     ecx, [rax+57h]; dwErrCode
0x14000c645  call    cs:__imp_SetLastError
0x14000c64b  jmp     short loc_14000C658
0x14000c64d  call    cs:__imp_GetProcessHeap
0x14000c653  test    rax, rax
0x14000c656  jnz     short loc_14000C65C
0x14000c658  xor     eax, eax
0x14000c65a  jmp     short loc_14000C6C2
0x14000c65c  mov     r8, rbx; dwBytes
0x14000c65f  mov     edx, 0Ch; dwFlags
0x14000c664  mov     rcx, rax; hHeap
0x14000c667  call    cs:__imp_HeapAlloc
0x14000c66d  mov     [rsp+38h+var_18], rax
0x14000c672  jmp     short loc_14000C6C2
0x14000c674  cmp     eax, 0C0000017h
0x14000c679  jnz     short loc_14000C692
0x14000c67b  call    cs:__imp_GetLastError
0x14000c681  test    eax, eax
0x14000c683  jnz     short loc_14000C68E
0x14000c685  lea     ecx, [rax+8]; dwErrCode
0x14000c688  call    cs:__imp_SetLastError
0x14000c68e  xor     eax, eax
0x14000c690  jmp     short loc_14000C6C2
0x14000c692  cmp     eax, 0C0000005h
0x14000c697  jnz     short loc_14000C6AD
0x14000c699  mov     ecx, 570h; dwErrCode
0x14000c69e  call    cs:__imp_SetLastError
0x14000c6a4  call    SaveLastError
0x14000c6a9  xor     eax, eax
0x14000c6ab  jmp     short loc_14000C6C2
0x14000c6ad  call    cs:__imp_GetLastError
0x14000c6b3  test    eax, eax
0x14000c6b5  jnz     short loc_14000C6C0
0x14000c6b7  lea     ecx, [rax+8]; dwErrCode
0x14000c6ba  call    cs:__imp_SetLastError
0x14000c6c0  xor     eax, eax
0x14000c6c2  add     rsp, 30h
0x14000c6c6  pop     rbx
0x14000c6c7  retn
```
