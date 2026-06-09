# WEBSOCKET_WRAPPER::CopyReceivedData(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER *)

- ea: `0x1800044d8`
- end: `0x18000455f`
- name: `?CopyReceivedData@WEBSOCKET_WRAPPER@@AEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@1@Z`
- size: `135`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000477c`
- `0x180004bac`

## callees

- `0x1800044d8`
- `0x1800085b6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004515`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004515`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004523`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004523`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_WRAPPER::CopyReceivedData(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  void *v8; // rax

  if ( a2 <= -2147483644 )
  {
    if ( a2 == -2147483644 )
      *(_WORD *)(a4 + 12) = *(_WORD *)(a3 + 12);
    *(_QWORD *)a4 = 0;
    *(_DWORD *)(a4 + 8) = 0;
    v6 = *(_DWORD *)(a3 + 8);
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 0, v6);
    *(_QWORD *)a4 = v8;
    if ( !v8 )
      return 2147942414LL;
    memcpy_0(v8, *(const void **)a3, *(unsigned int *)(a3 + 8));
    *(_DWORD *)(a4 + 8) = *(_DWORD *)(a3 + 8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800044d8  mov     [rsp+arg_0], rbx
0x1800044dd  mov     [rsp+arg_8], rsi
0x1800044e2  push    rdi
0x1800044e3  sub     rsp, 20h
0x1800044e7  mov     eax, 80000004h
0x1800044ec  mov     rsi, r9
0x1800044ef  mov     rdi, r8
0x1800044f2  cmp     edx, eax
0x1800044f4  jg      short loc_18000454D
0x1800044f6  jnz     short loc_180004502
0x1800044f8  movzx   eax, word ptr [r8+0Ch]
0x1800044fd  mov     [r9+0Ch], ax
0x180004502  mov     qword ptr [r9], 0
0x180004509  mov     dword ptr [r9+8], 0
0x180004511  mov     ebx, [r8+8]
0x180004515  call    cs:__imp_GetProcessHeap
0x18000451b  mov     r8d, ebx; dwBytes
0x18000451e  xor     edx, edx; dwFlags
0x180004520  mov     rcx, rax; hHeap
0x180004523  call    cs:__imp_HeapAlloc
0x180004529  mov     [rsi], rax
0x18000452c  test    rax, rax
0x18000452f  jnz     short loc_180004538
0x180004531  mov     eax, 8007000Eh
0x180004536  jmp     short loc_18000454F
0x180004538  mov     r8d, [rdi+8]; Size
0x18000453c  mov     rcx, rax; void *
0x18000453f  mov     rdx, [rdi]; Src
0x180004542  call    memcpy_0
0x180004547  mov     eax, [rdi+8]
0x18000454a  mov     [rsi+8], eax
0x18000454d  xor     eax, eax
0x18000454f  mov     rbx, [rsp+28h+arg_0]
0x180004554  mov     rsi, [rsp+28h+arg_8]
0x180004559  add     rsp, 20h
0x18000455d  pop     rdi
0x18000455e  retn
```
