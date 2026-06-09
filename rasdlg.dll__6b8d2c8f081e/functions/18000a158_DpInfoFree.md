# DpInfoFree

- ea: `0x18000a158`
- end: `0x18000a261`
- name: `DpInfoFree`
- size: `265`
- prototype: `DWORD __fastcall(unsigned int *hMem)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007820`
- `0x180008ffc`
- `0x18000ac58`

## callees

- `0x18000a104`
- `0x18000a158`
- `0x18004d0d2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a200`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a200`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a1f1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a230`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a243`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a250`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a1f1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a230`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a243`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000a250`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a1e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a1e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1c5`
- `USER32!SetWindowLongPtrW` at `0x18000a19d`
- `USER32!SetWindowLongPtrW` at `0x18000a19d`
- `rtutils!TracePrintfExA` at `0x18000a17c`
- `rtutils!TracePrintfExA` at `0x18000a17c`

## pseudocode

```c
DWORD __fastcall DpInfoFree(unsigned int *hMem)
{
  DWORD result; // eax
  LONG_PTR v3; // r8
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  _WORD *v8; // rcx
  __int64 v9; // r8
  void *v10; // rcx

  if ( g_dwTraceId != -1 )
    result = TracePrintfExA(g_dwTraceId, 0xCu, "DpInfoFree");
  if ( hMem )
  {
    v3 = *((_QWORD *)hMem + 8);
    if ( v3 )
    {
      SetWindowLongPtrW(*((HWND *)hMem + 2), -4, v3);
      *((_QWORD *)hMem + 8) = 0;
    }
    v4 = (void *)*((_QWORD *)hMem + 16);
    if ( v4 )
      CloseHandle(v4);
    v5 = (void *)*((_QWORD *)hMem + 18);
    if ( v5 )
      CloseHandle(v5);
    DpFreeStates(*((_QWORD *)hMem + 10), hMem[22]);
    *hMem = 0;
    if ( hMem[28] )
      DeleteCriticalSection(*((LPCRITICAL_SECTION *)hMem + 13));
    v6 = (void *)*((_QWORD *)hMem + 13);
    if ( v6 )
      GlobalFree(v6);
    v7 = (void *)*((_QWORD *)hMem + 4);
    if ( v7 )
      LocalFree(v7);
    v8 = (_WORD *)*((_QWORD *)hMem + 6);
    if ( v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      memset_0(v8, 0, 2 * v9 + 2);
      GlobalFree(*((HGLOBAL *)hMem + 6));
      *((_QWORD *)hMem + 6) = 0;
    }
    v10 = (void *)*((_QWORD *)hMem + 5);
    if ( v10 )
    {
      GlobalFree(v10);
      *((_QWORD *)hMem + 5) = 0;
    }
    return (unsigned int)GlobalFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x18000a158  mov     [rsp+arg_0], rbx
0x18000a15d  push    rdi
0x18000a15e  sub     rsp, 20h
0x18000a162  mov     rbx, rcx
0x18000a165  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a16b  cmp     ecx, 0FFFFFFFFh
0x18000a16e  jz      short loc_18000A182
0x18000a170  lea     r8, aDpinfofree; "DpInfoFree"
0x18000a177  mov     edx, 0Ch; dwFlags
0x18000a17c  call    cs:__imp_TracePrintfExA
0x18000a182  xor     edi, edi
0x18000a184  test    rbx, rbx
0x18000a187  jz      loc_18000A256
0x18000a18d  mov     r8, [rbx+40h]; dwNewLong
0x18000a191  test    r8, r8
0x18000a194  jz      short loc_18000A1A7
0x18000a196  mov     rcx, [rbx+10h]; hWnd
0x18000a19a  lea     edx, [rdi-4]; nIndex
0x18000a19d  call    cs:__imp_SetWindowLongPtrW
0x18000a1a3  mov     [rbx+40h], rdi
0x18000a1a7  mov     rcx, [rbx+80h]; hObject
0x18000a1ae  test    rcx, rcx
0x18000a1b1  jz      short loc_18000A1B9
0x18000a1b3  call    cs:__imp_CloseHandle
0x18000a1b9  mov     rcx, [rbx+90h]; hObject
0x18000a1c0  test    rcx, rcx
0x18000a1c3  jz      short loc_18000A1CB
0x18000a1c5  call    cs:__imp_CloseHandle
0x18000a1cb  mov     edx, [rbx+58h]
0x18000a1ce  mov     rcx, [rbx+50h]
0x18000a1d2  call    DpFreeStates
0x18000a1d7  mov     [rbx], edi
0x18000a1d9  cmp     [rbx+70h], edi
0x18000a1dc  jz      short loc_18000A1E8
0x18000a1de  mov     rcx, [rbx+68h]; lpCriticalSection
0x18000a1e2  call    cs:__imp_DeleteCriticalSection
0x18000a1e8  mov     rcx, [rbx+68h]; hMem
0x18000a1ec  test    rcx, rcx
0x18000a1ef  jz      short loc_18000A1F7
0x18000a1f1  call    cs:__imp_GlobalFree
0x18000a1f7  mov     rcx, [rbx+20h]; hMem
0x18000a1fb  test    rcx, rcx
0x18000a1fe  jz      short loc_18000A206
0x18000a200  call    cs:__imp_LocalFree
0x18000a206  mov     rcx, [rbx+30h]; void *
0x18000a20a  test    rcx, rcx
0x18000a20d  jz      short loc_18000A23A
0x18000a20f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a213  inc     r8
0x18000a216  cmp     [rcx+r8*2], di
0x18000a21b  jnz     short loc_18000A213
0x18000a21d  lea     r8, ds:2[r8*2]; Size
0x18000a225  xor     edx, edx; Val
0x18000a227  call    memset_0
0x18000a22c  mov     rcx, [rbx+30h]; hMem
0x18000a230  call    cs:__imp_GlobalFree
0x18000a236  mov     [rbx+30h], rdi
0x18000a23a  mov     rcx, [rbx+28h]; hMem
0x18000a23e  test    rcx, rcx
0x18000a241  jz      short loc_18000A24D
0x18000a243  call    cs:__imp_GlobalFree
0x18000a249  mov     [rbx+28h], rdi
0x18000a24d  mov     rcx, rbx; hMem
0x18000a250  call    cs:__imp_GlobalFree
0x18000a256  mov     rbx, [rsp+28h+arg_0]
0x18000a25b  add     rsp, 20h
0x18000a25f  pop     rdi
0x18000a260  retn
```
