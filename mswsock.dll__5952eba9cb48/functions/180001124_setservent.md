# setservent

- ea: `0x180001124`
- end: `0x1800011d2`
- name: `setservent`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800018b0`
- `0x180001998`

## callees

- `0x180001124`
- `0x1800011d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001134`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001154`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000116a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800011a5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001134`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001154`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000116a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001199`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800011a5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800011c4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800011c4`

## pseudocode

```c
LPVOID setservent()
{
  char *v0; // rdi
  __int64 v1; // rbx
  __int64 v2; // rcx
  _QWORD *Value; // rax

  if ( *(_QWORD *)(*((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9) + 272LL) )
  {
    Value = TlsGetValue(MSAFD_SockTlsSlot);
    SetFilePointer(*(HANDLE *)(Value[9] + 272LL), 0, 0, 0);
  }
  else
  {
    v0 = (char *)*((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9);
    v1 = *((_QWORD *)TlsGetValue(MSAFD_SockTlsSlot) + 9);
    *(_QWORD *)(v1 + 272) = SockOpenNetworkDataBase(v2, v0);
  }
  return TlsGetValue(MSAFD_SockTlsSlot);
}

```

## disassembly

```asm
0x180001124  mov     [rsp+arg_0], rbx
0x180001129  push    rdi
0x18000112a  sub     rsp, 30h
0x18000112e  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001134  call    cs:__imp_TlsGetValue
0x18000113b  nop     dword ptr [rax+rax+00h]
0x180001140  mov     rcx, [rax+48h]
0x180001144  cmp     qword ptr [rcx+110h], 0
0x18000114c  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001152  jnz     short loc_1800011A5
0x180001154  call    cs:__imp_TlsGetValue
0x18000115b  nop     dword ptr [rax+rax+00h]
0x180001160  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180001166  mov     rdi, [rax+48h]
0x18000116a  call    cs:__imp_TlsGetValue
0x180001171  nop     dword ptr [rax+rax+00h]
0x180001176  mov     rdx, rdi
0x180001179  mov     rbx, [rax+48h]
0x18000117d  call    SockOpenNetworkDataBase
0x180001182  mov     [rbx+110h], rax
0x180001189  mov     ecx, cs:MSAFD_SockTlsSlot
0x18000118f  mov     rbx, [rsp+38h+arg_0]
0x180001194  add     rsp, 30h
0x180001198  pop     rdi
0x180001199  jmp     cs:__imp_TlsGetValue
0x1800011a5  call    cs:__imp_TlsGetValue
0x1800011ac  nop     dword ptr [rax+rax+00h]
0x1800011b1  xor     r9d, r9d; dwMoveMethod
0x1800011b4  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800011b7  xor     edx, edx; lDistanceToMove
0x1800011b9  mov     rcx, [rax+48h]
0x1800011bd  mov     rcx, [rcx+110h]; hFile
0x1800011c4  call    cs:__imp_SetFilePointer
0x1800011cb  nop     dword ptr [rax+rax+00h]
0x1800011d0  jmp     short loc_180001189
```
