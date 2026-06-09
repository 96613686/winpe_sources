# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18001bf04`
- end: `0x18001bf77`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180031580`

## callees

- `0x18001bf04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bf30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bf30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bf44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bf44`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x18001bf04  mov     [rsp+arg_0], rbx
0x18001bf09  mov     [rsp+arg_8], rbp
0x18001bf0e  mov     [rsp+arg_10], rsi
0x18001bf13  push    rdi
0x18001bf14  sub     rsp, 20h
0x18001bf18  lea     rbp, [rcx+50h]
0x18001bf1c  mov     rdi, rcx
0x18001bf1f  cmp     rcx, rbp
0x18001bf22  jz      short loc_18001BF61
0x18001bf24  mov     rsi, [rdi]
0x18001bf27  jmp     short loc_18001BF50
0x18001bf29  mov     rbx, rsi
0x18001bf2c  mov     rsi, [rsi+8]
0x18001bf30  call    cs:__imp_GetProcessHeap
0x18001bf37  nop     dword ptr [rax+rax+00h]
0x18001bf3c  mov     r8, rbx; lpMem
0x18001bf3f  xor     edx, edx; dwFlags
0x18001bf41  mov     rcx, rax; hHeap
0x18001bf44  call    cs:__imp_HeapFree
0x18001bf4b  nop     dword ptr [rax+rax+00h]
0x18001bf50  test    rsi, rsi
0x18001bf53  jnz     short loc_18001BF29
0x18001bf55  mov     [rdi], rsi
0x18001bf58  add     rdi, 8
0x18001bf5c  cmp     rdi, rbp
0x18001bf5f  jnz     short loc_18001BF24
0x18001bf61  mov     rbx, [rsp+28h+arg_0]
0x18001bf66  mov     rbp, [rsp+28h+arg_8]
0x18001bf6b  mov     rsi, [rsp+28h+arg_10]
0x18001bf70  add     rsp, 20h
0x18001bf74  pop     rdi
0x18001bf75  retn
```
