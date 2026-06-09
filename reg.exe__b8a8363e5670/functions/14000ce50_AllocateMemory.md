# AllocateMemory

- ea: `0x14000ce50`
- end: `0x14000cf26`
- name: `AllocateMemory`
- size: `214`
- prototype: `LPVOID __fastcall(SIZE_T dwBytes)`
- caller_count: `32`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e90`
- `0x140002090`
- `0x14000263c`
- `0x140002a78`
- `0x1400033d8`
- `0x140003c24`
- `0x14000426c`
- `0x140004e84`
- `0x1400056ec`
- `0x140005910`
- `0x140005c78`
- `0x1400061e4`
- `0x1400064b0`
- `0x14000672c`
- `0x140006e6c`
- `0x1400075ac`
- `0x14000799c`
- `0x140007cbc`
- `0x1400080a4`
- `0x140008838`
- `0x1400090a8`
- `0x140009374`
- `0x140009498`
- `0x14000957c`
- `0x14000a0e0`
- `0x14000a358`
- `0x14000aa4c`
- `0x14000d3e8`
- `0x14000f294`
- `0x14000f43c`
- `0x14000f638`
- `0x14000f708`

## callees

- `0x14000ce50`
- `0x14000e484`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ce5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ceba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cefe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ce5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ceba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cefe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ce6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cecd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cee9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cf11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ce6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cecd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cee9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cf11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ce7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ce7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000cea0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000cea0`

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
0x14000ce50  push    rbx
0x14000ce52  sub     rsp, 30h
0x14000ce56  mov     ebx, ecx
0x14000ce58  test    ecx, ecx
0x14000ce5a  jnz     short loc_14000CE7D
0x14000ce5c  call    cs:__imp_GetLastError
0x14000ce63  nop     dword ptr [rax+rax+00h]
0x14000ce68  test    eax, eax
0x14000ce6a  jnz     short loc_14000CE8E
0x14000ce6c  lea     ecx, [rax+57h]; dwErrCode
0x14000ce6f  call    cs:__imp_SetLastError
0x14000ce76  nop     dword ptr [rax+rax+00h]
0x14000ce7b  jmp     short loc_14000CE8E
0x14000ce7d  call    cs:__imp_GetProcessHeap
0x14000ce84  nop     dword ptr [rax+rax+00h]
0x14000ce89  test    rax, rax
0x14000ce8c  jnz     short loc_14000CE95
0x14000ce8e  xor     eax, eax
0x14000ce90  jmp     loc_14000CF1F
0x14000ce95  mov     r8, rbx; dwBytes
0x14000ce98  mov     edx, 0Ch; dwFlags
0x14000ce9d  mov     rcx, rax; hHeap
0x14000cea0  call    cs:__imp_HeapAlloc
0x14000cea7  nop     dword ptr [rax+rax+00h]
0x14000ceac  mov     [rsp+38h+var_18], rax
0x14000ceb1  jmp     short loc_14000CF1F
0x14000ceb3  cmp     eax, 0C0000017h
0x14000ceb8  jnz     short loc_14000CEDD
0x14000ceba  call    cs:__imp_GetLastError
0x14000cec1  nop     dword ptr [rax+rax+00h]
0x14000cec6  test    eax, eax
0x14000cec8  jnz     short loc_14000CED9
0x14000ceca  lea     ecx, [rax+8]; dwErrCode
0x14000cecd  call    cs:__imp_SetLastError
0x14000ced4  nop     dword ptr [rax+rax+00h]
0x14000ced9  xor     eax, eax
0x14000cedb  jmp     short loc_14000CF1F
0x14000cedd  cmp     eax, 0C0000005h
0x14000cee2  jnz     short loc_14000CEFE
0x14000cee4  mov     ecx, 570h; dwErrCode
0x14000cee9  call    cs:__imp_SetLastError
0x14000cef0  nop     dword ptr [rax+rax+00h]
0x14000cef5  call    SaveLastError
0x14000cefa  xor     eax, eax
0x14000cefc  jmp     short loc_14000CF1F
0x14000cefe  call    cs:__imp_GetLastError
0x14000cf05  nop     dword ptr [rax+rax+00h]
0x14000cf0a  test    eax, eax
0x14000cf0c  jnz     short loc_14000CF1D
0x14000cf0e  lea     ecx, [rax+8]; dwErrCode
0x14000cf11  call    cs:__imp_SetLastError
0x14000cf18  nop     dword ptr [rax+rax+00h]
0x14000cf1d  xor     eax, eax
0x14000cf1f  add     rsp, 30h
0x14000cf23  pop     rbx
0x14000cf24  retn
```
