# MakeAuthProtocolOption

- ea: `0x180008338`
- end: `0x1800084de`
- name: `MakeAuthProtocolOption`
- size: `422`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000638c`
- `0x180007020`
- `0x180007690`
- `0x180007910`

## callees

- `0x180008338`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000841b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000841b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800083cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008445`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800083cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008467`

## pseudocode

```c
DWORD __fastcall MakeAuthProtocolOption(__int64 a1)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  bool v5; // zf
  LPVOID *v6; // rsi
  LPVOID v7; // rax
  void *v8; // r8
  LPVOID v9; // rax
  void *v11; // r8

  v2 = *(_DWORD *)(a1 + 8) - 1;
  if ( !v2 )
  {
    *(_DWORD *)(a1 + 124) = 49703;
LABEL_18:
    if ( *(_DWORD *)(a1 + 128) )
    {
      v11 = *(void **)(a1 + 136);
      *(_DWORD *)(a1 + 128) = 0;
      if ( v11 )
      {
        HeapFree(hHeap, 0, v11);
        *(_QWORD *)(a1 + 136) = 0;
      }
    }
    return 0;
  }
  v3 = v2 - 1;
  if ( v3 )
  {
    v4 = v3 - 2;
    if ( !v4 )
    {
      v5 = *(_DWORD *)(a1 + 128) == 1;
      v6 = (LPVOID *)(a1 + 136);
      *(_DWORD *)(a1 + 124) = 49699;
      if ( !v5 )
      {
        v5 = *v6 == 0;
        *(_DWORD *)(a1 + 128) = 1;
        if ( !v5 )
        {
          HeapFree(hHeap, 0, *v6);
          *v6 = 0;
        }
        v7 = HeapAlloc(hHeap, 8u, *(unsigned int *)(a1 + 128));
        *v6 = v7;
        if ( !v7 )
          goto LABEL_15;
      }
      *(_BYTE *)*v6 = 5;
      return 0;
    }
    if ( v4 == 4 )
    {
      *(_DWORD *)(a1 + 124) = 49187;
      goto LABEL_18;
    }
  }
  v5 = *(_DWORD *)(a1 + 128) == 1;
  *(_DWORD *)(a1 + 124) = 49699;
  if ( !v5 )
  {
    v8 = *(void **)(a1 + 136);
    *(_DWORD *)(a1 + 128) = 1;
    if ( v8 )
    {
      HeapFree(hHeap, 0, v8);
      *(_QWORD *)(a1 + 136) = 0;
    }
    v9 = HeapAlloc(hHeap, 8u, *(unsigned int *)(a1 + 128));
    *(_QWORD *)(a1 + 136) = v9;
    if ( !v9 )
    {
LABEL_15:
      *(_DWORD *)(a1 + 128) = 0;
      return GetLastError();
    }
  }
  **(_BYTE **)(a1 + 136) = (*(_DWORD *)(a1 + 8) == 2) + 0x80;
  return 0;
}

```

## disassembly

```asm
0x180008338  mov     [rsp+arg_0], rbx
0x18000833d  push    rsi
0x18000833e  sub     rsp, 20h
0x180008342  mov     rbx, rcx
0x180008345  mov     ecx, [rcx+8]
0x180008348  sub     ecx, 1
0x18000834b  jz      loc_18000848A
0x180008351  sub     ecx, 1
0x180008354  jz      loc_1800083EC
0x18000835a  sub     ecx, 2
0x18000835d  jz      short loc_180008374
0x18000835f  cmp     ecx, 4
0x180008362  jnz     loc_1800083EC
0x180008368  mov     dword ptr [rbx+7Ch], 0C023h
0x18000836f  jmp     loc_180008491
0x180008374  cmp     dword ptr [rbx+80h], 1
0x18000837b  lea     rsi, [rbx+88h]
0x180008382  mov     dword ptr [rbx+7Ch], 0C223h
0x180008389  jz      short loc_1800083E1
0x18000838b  cmp     qword ptr [rsi], 0
0x18000838f  mov     dword ptr [rbx+80h], 1
0x180008399  jz      short loc_1800083BA
0x18000839b  mov     r8, [rsi]; lpMem
0x18000839e  xor     edx, edx; dwFlags
0x1800083a0  mov     rcx, cs:hHeap; hHeap
0x1800083a7  call    cs:__imp_HeapFree
0x1800083ae  nop     dword ptr [rax+rax+00h]
0x1800083b3  mov     qword ptr [rsi], 0
0x1800083ba  mov     r8d, [rbx+80h]; dwBytes
0x1800083c1  mov     edx, 8; dwFlags
0x1800083c6  mov     rcx, cs:hHeap; hHeap
0x1800083cd  call    cs:__imp_HeapAlloc
0x1800083d4  nop     dword ptr [rax+rax+00h]
0x1800083d9  mov     [rsi], rax
0x1800083dc  test    rax, rax
0x1800083df  jz      short loc_18000845D
0x1800083e1  mov     rax, [rsi]
0x1800083e4  mov     byte ptr [rax], 5
0x1800083e7  jmp     loc_1800084D0
0x1800083ec  cmp     dword ptr [rbx+80h], 1
0x1800083f3  mov     dword ptr [rbx+7Ch], 0C223h
0x1800083fa  jz      short loc_180008475
0x1800083fc  mov     r8, [rbx+88h]; lpMem
0x180008403  mov     dword ptr [rbx+80h], 1
0x18000840d  test    r8, r8
0x180008410  jz      short loc_180008432
0x180008412  mov     rcx, cs:hHeap; hHeap
0x180008419  xor     edx, edx; dwFlags
0x18000841b  call    cs:__imp_HeapFree
0x180008422  nop     dword ptr [rax+rax+00h]
0x180008427  mov     qword ptr [rbx+88h], 0
0x180008432  mov     r8d, [rbx+80h]; dwBytes
0x180008439  mov     edx, 8; dwFlags
0x18000843e  mov     rcx, cs:hHeap; hHeap
0x180008445  call    cs:__imp_HeapAlloc
0x18000844c  nop     dword ptr [rax+rax+00h]
0x180008451  mov     [rbx+88h], rax
0x180008458  test    rax, rax
0x18000845b  jnz     short loc_180008475
0x18000845d  mov     dword ptr [rbx+80h], 0
0x180008467  call    cs:__imp_GetLastError
0x18000846e  nop     dword ptr [rax+rax+00h]
0x180008473  jmp     short loc_1800084D2
0x180008475  cmp     dword ptr [rbx+8], 2
0x180008479  mov     rax, [rbx+88h]
0x180008480  setz    cl
0x180008483  add     cl, 80h
0x180008486  mov     [rax], cl
0x180008488  jmp     short loc_1800084D0
0x18000848a  mov     dword ptr [rbx+7Ch], 0C227h
0x180008491  cmp     dword ptr [rbx+80h], 0
0x180008498  jz      short loc_1800084D0
0x18000849a  mov     r8, [rbx+88h]; lpMem
0x1800084a1  mov     dword ptr [rbx+80h], 0
0x1800084ab  test    r8, r8
0x1800084ae  jz      short loc_1800084D0
0x1800084b0  mov     rcx, cs:hHeap; hHeap
0x1800084b7  xor     edx, edx; dwFlags
0x1800084b9  call    cs:__imp_HeapFree
0x1800084c0  nop     dword ptr [rax+rax+00h]
0x1800084c5  mov     qword ptr [rbx+88h], 0
0x1800084d0  xor     eax, eax
0x1800084d2  mov     rbx, [rsp+28h+arg_0]
0x1800084d7  add     rsp, 20h
0x1800084db  pop     rsi
0x1800084dc  retn
```
