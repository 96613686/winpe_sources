# SspiCreateAsyncContext

- ea: `0x180026390`
- end: `0x1800263d2`
- name: `SspiCreateAsyncContext`
- size: `66`
- prototype: `SspiAsyncContext *__stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180010c80`
- `0x180026390`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x18002639d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x18002639d`

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
0x180026390  push    rbx
0x180026392  sub     rsp, 20h
0x180026396  lea     rcx, stru_180019690; Lookaside
0x18002639d  call    cs:__imp_ExAllocateFromLookasideListEx
0x1800263a4  nop     dword ptr [rax+rax+00h]
0x1800263a9  mov     rbx, rax
0x1800263ac  test    rax, rax
0x1800263af  jz      short loc_1800263CB
0x1800263b1  xor     edx, edx; Val
0x1800263b3  mov     r8d, 0F0h; Size
0x1800263b9  mov     rcx, rax; void *
0x1800263bc  call    memset
0x1800263c1  mov     rax, rbx
0x1800263c4  mov     dword ptr [rbx+14h], 80090302h
0x1800263cb  add     rsp, 20h
0x1800263cf  pop     rbx
0x1800263d0  retn
```
