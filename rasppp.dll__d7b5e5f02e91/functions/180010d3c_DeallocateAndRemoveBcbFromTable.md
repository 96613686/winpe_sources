# DeallocateAndRemoveBcbFromTable

- ea: `0x180010d3c`
- end: `0x180010ec9`
- name: `DeallocateAndRemoveBcbFromTable`
- size: `397`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180014bfc`
- `0x180015d28`
- `0x180016260`

## callees

- `0x180010d3c`
- `0x18001904c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010e80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010e9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010eb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010e80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010e9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010eb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010dde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010dee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010dde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010dee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010dce`

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
    v2 = *((_DWORD *)lpMem + 10) % (unsigned int)qword_18004D970;
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
0x180010d3c  test    rcx, rcx
0x180010d3f  jz      locret_180010EC7
0x180010d45  push    rbx
0x180010d46  sub     rsp, 20h
0x180010d4a  mov     eax, [rcx+28h]
0x180010d4d  xor     edx, edx
0x180010d4f  div     dword ptr cs:qword_18004D970
0x180010d55  mov     r9, qword ptr cs:PcbTable+8
0x180010d5c  mov     rbx, rcx
0x180010d5f  mov     r8d, edx
0x180010d62  mov     rcx, [r9+rdx*8]
0x180010d66  test    rcx, rcx
0x180010d69  jz      short loc_180010D97
0x180010d6b  mov     rdx, [rbx+28h]
0x180010d6f  mov     rax, rcx
0x180010d72  cmp     [rax+28h], rdx
0x180010d76  jz      short loc_180010D85
0x180010d78  mov     rcx, rax
0x180010d7b  mov     rax, [rax]
0x180010d7e  test    rax, rax
0x180010d81  jnz     short loc_180010D72
0x180010d83  jmp     short loc_180010D97
0x180010d85  mov     rdx, [rax]
0x180010d88  cmp     rax, [r9+r8*8]
0x180010d8c  jnz     short loc_180010D94
0x180010d8e  mov     [r9+r8*8], rdx
0x180010d92  jmp     short loc_180010D97
0x180010d94  mov     [rcx], rdx
0x180010d97  mov     ecx, 101h
0x180010d9c  lea     rax, [rbx+2FAh]
0x180010da3  mov     edx, ecx
0x180010da5  mov     byte ptr [rax], 0
0x180010da8  inc     rax
0x180010dab  sub     rdx, 1
0x180010daf  jnz     short loc_180010DA5
0x180010db1  lea     rax, [rbx+3FBh]
0x180010db8  mov     byte ptr [rax], 0
0x180010dbb  inc     rax
0x180010dbe  sub     rcx, 1
0x180010dc2  jnz     short loc_180010DB8
0x180010dc4  mov     rcx, [rbx+40h]; hObject
0x180010dc8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010dcc  jz      short loc_180010DDA
0x180010dce  call    cs:__imp_CloseHandle
0x180010dd5  nop     dword ptr [rax+rax+00h]
0x180010dda  mov     rcx, [rbx+58h]; hMem
0x180010dde  call    cs:__imp_LocalFree
0x180010de5  nop     dword ptr [rax+rax+00h]
0x180010dea  mov     rcx, [rbx+60h]; hMem
0x180010dee  call    cs:__imp_LocalFree
0x180010df5  nop     dword ptr [rax+rax+00h]
0x180010dfa  mov     rcx, [rbx+98h]; hMem
0x180010e01  call    cs:__imp_LocalFree
0x180010e08  nop     dword ptr [rax+rax+00h]
0x180010e0d  mov     rcx, [rbx+0A0h]; hMem
0x180010e14  call    cs:__imp_LocalFree
0x180010e1b  nop     dword ptr [rax+rax+00h]
0x180010e20  mov     rcx, [rbx+0A8h]; hMem
0x180010e27  call    cs:__imp_LocalFree
0x180010e2e  nop     dword ptr [rax+rax+00h]
0x180010e33  mov     rcx, [rbx+68h]; hMem
0x180010e37  call    cs:__imp_LocalFree
0x180010e3e  nop     dword ptr [rax+rax+00h]
0x180010e43  mov     rcx, [rbx+70h]; hMem
0x180010e47  call    cs:__imp_LocalFree
0x180010e4e  nop     dword ptr [rax+rax+00h]
0x180010e53  lea     rcx, [rbx+0B8h]
0x180010e5a  call    FreePassword
0x180010e5f  lea     rcx, [rbx+0C8h]
0x180010e66  call    FreePassword
0x180010e6b  mov     r8, [rbx+0B0h]; lpMem
0x180010e72  test    r8, r8
0x180010e75  jz      short loc_180010E8C
0x180010e77  mov     rcx, cs:hHeap; hHeap
0x180010e7e  xor     edx, edx; dwFlags
0x180010e80  call    cs:__imp_HeapFree
0x180010e87  nop     dword ptr [rax+rax+00h]
0x180010e8c  mov     r8, [rbx+8]; lpMem
0x180010e90  test    r8, r8
0x180010e93  jz      short loc_180010EAA
0x180010e95  mov     rcx, cs:hHeap; hHeap
0x180010e9c  xor     edx, edx; dwFlags
0x180010e9e  call    cs:__imp_HeapFree
0x180010ea5  nop     dword ptr [rax+rax+00h]
0x180010eaa  mov     rcx, cs:hHeap; hHeap
0x180010eb1  mov     r8, rbx; lpMem
0x180010eb4  xor     edx, edx; dwFlags
0x180010eb6  call    cs:__imp_HeapFree
0x180010ebd  nop     dword ptr [rax+rax+00h]
0x180010ec2  add     rsp, 20h
0x180010ec6  pop     rbx
0x180010ec7  retn
```
