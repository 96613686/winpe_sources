# SspiCreateAsyncContext

- ea: `0x1800263e0`
- end: `0x180026422`
- name: `SspiCreateAsyncContext`
- size: `66`
- prototype: `SspiAsyncContext *__stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180010d00`
- `0x1800263e0`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1800263ed`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1800263ed`

## pseudocode

```c
SspiAsyncContext *__stdcall SspiCreateAsyncContext()
{
  SspiAsyncContext *result; // rax
  SspiAsyncContext *v1; // rbx

  result = (SspiAsyncContext *)ExAllocateFromLookasideListEx(&stru_180019690);
  v1 = result;
  if ( result )
  {
    memset(result, 0, 0xF0u);
    result = v1;
    *((_DWORD *)v1 + 5) = -2146893054;
  }
  return result;
}

```

## disassembly

```asm
0x1800263e0  push    rbx
0x1800263e2  sub     rsp, 20h
0x1800263e6  lea     rcx, stru_180019690; Lookaside
0x1800263ed  call    cs:__imp_ExAllocateFromLookasideListEx
0x1800263f4  nop     dword ptr [rax+rax+00h]
0x1800263f9  mov     rbx, rax
0x1800263fc  test    rax, rax
0x1800263ff  jz      short loc_18002641B
0x180026401  xor     edx, edx; Val
0x180026403  mov     r8d, 0F0h; Size
0x180026409  mov     rcx, rax; void *
0x18002640c  call    memset
0x180026411  mov     rax, rbx
0x180026414  mov     dword ptr [rbx+14h], 80090302h
0x18002641b  add     rsp, 20h
0x18002641f  pop     rbx
0x180026420  retn
```
