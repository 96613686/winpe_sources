# DeallocateAndRemoveBcbFromTable

- ea: `0x180010850`
- end: `0x18001099a`
- name: `DeallocateAndRemoveBcbFromTable`
- size: `330`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180014514`
- `0x1800155b8`
- `0x180015ae0`

## callees

- `0x180010850`
- `0x1800187b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010964`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001097c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001098e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010964`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001097c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001098e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010903`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001091d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010927`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010931`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010903`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001091d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010927`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010931`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108e2`

## pseudocode

```c
void __fastcall DeallocateAndRemoveBcbFromTable(char *lpMem)
{
  __int64 v2; // r8
  _QWORD *v3; // rcx
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  char *v7; // rax
  __int64 v8; // rdx
  char *v9; // rax
  void *v10; // rcx
  void *v11; // r8
  void *v12; // r8

  if ( lpMem )
  {
    v2 = *((_DWORD *)lpMem + 10) % (unsigned int)qword_18004C970;
    v3 = (_QWORD *)*((_QWORD *)*(&PcbTable + 1) + v2);
    if ( v3 )
    {
      v4 = (_QWORD *)*((_QWORD *)*(&PcbTable + 1) + v2);
      while ( v4[5] != *((_QWORD *)lpMem + 5) )
      {
        v3 = v4;
        v4 = (_QWORD *)*v4;
        if ( !v4 )
          goto LABEL_10;
      }
      v5 = *v4;
      if ( v4 == *((_QWORD **)*(&PcbTable + 1) + v2) )
        *((_QWORD *)*(&PcbTable + 1) + v2) = v5;
      else
        *v3 = v5;
    }
LABEL_10:
    v6 = 257;
    v7 = lpMem + 762;
    v8 = 257;
    do
    {
      *v7++ = 0;
      --v8;
    }
    while ( v8 );
    v9 = lpMem + 1019;
    do
    {
      *v9++ = 0;
      --v6;
    }
    while ( v6 );
    v10 = (void *)*((_QWORD *)lpMem + 8);
    if ( v10 != (void *)-1LL )
      CloseHandle(v10);
    LocalFree(*((HLOCAL *)lpMem + 11));
    LocalFree(*((HLOCAL *)lpMem + 12));
    LocalFree(*((HLOCAL *)lpMem + 19));
    LocalFree(*((HLOCAL *)lpMem + 20));
    LocalFree(*((HLOCAL *)lpMem + 21));
    LocalFree(*((HLOCAL *)lpMem + 13));
    LocalFree(*((HLOCAL *)lpMem + 14));
    FreePassword(lpMem + 184);
    FreePassword(lpMem + 200);
    v11 = (void *)*((_QWORD *)lpMem + 22);
    if ( v11 )
      HeapFree(hHeap, 0, v11);
    v12 = (void *)*((_QWORD *)lpMem + 1);
    if ( v12 )
      HeapFree(hHeap, 0, v12);
    HeapFree(hHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180010850  test    rcx, rcx
0x180010853  jz      locret_180010999
0x180010859  push    rbx
0x18001085a  sub     rsp, 20h
0x18001085e  mov     eax, [rcx+28h]
0x180010861  xor     edx, edx
0x180010863  div     dword ptr cs:qword_18004C970
0x180010869  mov     r9, qword ptr cs:PcbTable+8
0x180010870  mov     rbx, rcx
0x180010873  mov     r8d, edx
0x180010876  mov     rcx, [r9+rdx*8]
0x18001087a  test    rcx, rcx
0x18001087d  jz      short loc_1800108AB
0x18001087f  mov     rdx, [rbx+28h]
0x180010883  mov     rax, rcx
0x180010886  cmp     [rax+28h], rdx
0x18001088a  jz      short loc_180010899
0x18001088c  mov     rcx, rax
0x18001088f  mov     rax, [rax]
0x180010892  test    rax, rax
0x180010895  jnz     short loc_180010886
0x180010897  jmp     short loc_1800108AB
0x180010899  mov     rdx, [rax]
0x18001089c  cmp     rax, [r9+r8*8]
0x1800108a0  jnz     short loc_1800108A8
0x1800108a2  mov     [r9+r8*8], rdx
0x1800108a6  jmp     short loc_1800108AB
0x1800108a8  mov     [rcx], rdx
0x1800108ab  mov     ecx, 101h
0x1800108b0  lea     rax, [rbx+2FAh]
0x1800108b7  mov     edx, ecx
0x1800108b9  mov     byte ptr [rax], 0
0x1800108bc  inc     rax
0x1800108bf  sub     rdx, 1
0x1800108c3  jnz     short loc_1800108B9
0x1800108c5  lea     rax, [rbx+3FBh]
0x1800108cc  mov     byte ptr [rax], 0
0x1800108cf  inc     rax
0x1800108d2  sub     rcx, 1
0x1800108d6  jnz     short loc_1800108CC
0x1800108d8  mov     rcx, [rbx+40h]; hObject
0x1800108dc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800108e0  jz      short loc_1800108E8
0x1800108e2  call    cs:__imp_CloseHandle
0x1800108e8  mov     rcx, [rbx+58h]; hMem
0x1800108ec  call    cs:__imp_LocalFree
0x1800108f2  mov     rcx, [rbx+60h]; hMem
0x1800108f6  call    cs:__imp_LocalFree
0x1800108fc  mov     rcx, [rbx+98h]; hMem
0x180010903  call    cs:__imp_LocalFree
0x180010909  mov     rcx, [rbx+0A0h]; hMem
0x180010910  call    cs:__imp_LocalFree
0x180010916  mov     rcx, [rbx+0A8h]; hMem
0x18001091d  call    cs:__imp_LocalFree
0x180010923  mov     rcx, [rbx+68h]; hMem
0x180010927  call    cs:__imp_LocalFree
0x18001092d  mov     rcx, [rbx+70h]; hMem
0x180010931  call    cs:__imp_LocalFree
0x180010937  lea     rcx, [rbx+0B8h]
0x18001093e  call    FreePassword
0x180010943  lea     rcx, [rbx+0C8h]
0x18001094a  call    FreePassword
0x18001094f  mov     r8, [rbx+0B0h]; lpMem
0x180010956  test    r8, r8
0x180010959  jz      short loc_18001096A
0x18001095b  mov     rcx, cs:hHeap; hHeap
0x180010962  xor     edx, edx; dwFlags
0x180010964  call    cs:__imp_HeapFree
0x18001096a  mov     r8, [rbx+8]; lpMem
0x18001096e  test    r8, r8
0x180010971  jz      short loc_180010982
0x180010973  mov     rcx, cs:hHeap; hHeap
0x18001097a  xor     edx, edx; dwFlags
0x18001097c  call    cs:__imp_HeapFree
0x180010982  mov     rcx, cs:hHeap; hHeap
0x180010989  mov     r8, rbx; lpMem
0x18001098c  xor     edx, edx; dwFlags
0x18001098e  call    cs:__imp_HeapFree
0x180010994  add     rsp, 20h
0x180010998  pop     rbx
0x180010999  retn
```
