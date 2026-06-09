# MakeAuthProtocolOption

- ea: `0x180008048`
- end: `0x1800081c5`
- name: `MakeAuthProtocolOption`
- size: `381`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006118`
- `0x180006d70`
- `0x1800073d0`
- `0x180007640`

## callees

- `0x180008048`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000811b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000811b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000813f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000813f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000815b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000815b`

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
0x180008048  mov     [rsp+arg_0], rbx
0x18000804d  push    rsi
0x18000804e  sub     rsp, 20h
0x180008052  mov     rbx, rcx
0x180008055  mov     ecx, [rcx+8]
0x180008058  sub     ecx, 1
0x18000805b  jz      loc_180008178
0x180008061  sub     ecx, 1
0x180008064  jz      loc_1800080EC
0x18000806a  sub     ecx, 2
0x18000806d  jz      short loc_180008080
0x18000806f  cmp     ecx, 4
0x180008072  jnz     short loc_1800080EC
0x180008074  mov     dword ptr [rbx+7Ch], 0C023h
0x18000807b  jmp     loc_18000817F
0x180008080  cmp     dword ptr [rbx+80h], 1
0x180008087  lea     rsi, [rbx+88h]
0x18000808e  mov     dword ptr [rbx+7Ch], 0C223h
0x180008095  jz      short loc_1800080E1
0x180008097  cmp     qword ptr [rsi], 0
0x18000809b  mov     dword ptr [rbx+80h], 1
0x1800080a5  jz      short loc_1800080C0
0x1800080a7  mov     r8, [rsi]; lpMem
0x1800080aa  xor     edx, edx; dwFlags
0x1800080ac  mov     rcx, cs:hHeap; hHeap
0x1800080b3  call    cs:__imp_HeapFree
0x1800080b9  mov     qword ptr [rsi], 0
0x1800080c0  mov     r8d, [rbx+80h]; dwBytes
0x1800080c7  mov     edx, 8; dwFlags
0x1800080cc  mov     rcx, cs:hHeap; hHeap
0x1800080d3  call    cs:__imp_HeapAlloc
0x1800080d9  mov     [rsi], rax
0x1800080dc  test    rax, rax
0x1800080df  jz      short loc_180008151
0x1800080e1  mov     rax, [rsi]
0x1800080e4  mov     byte ptr [rax], 5
0x1800080e7  jmp     loc_1800081B8
0x1800080ec  cmp     dword ptr [rbx+80h], 1
0x1800080f3  mov     dword ptr [rbx+7Ch], 0C223h
0x1800080fa  jz      short loc_180008163
0x1800080fc  mov     r8, [rbx+88h]; lpMem
0x180008103  mov     dword ptr [rbx+80h], 1
0x18000810d  test    r8, r8
0x180008110  jz      short loc_18000812C
0x180008112  mov     rcx, cs:hHeap; hHeap
0x180008119  xor     edx, edx; dwFlags
0x18000811b  call    cs:__imp_HeapFree
0x180008121  mov     qword ptr [rbx+88h], 0
0x18000812c  mov     r8d, [rbx+80h]; dwBytes
0x180008133  mov     edx, 8; dwFlags
0x180008138  mov     rcx, cs:hHeap; hHeap
0x18000813f  call    cs:__imp_HeapAlloc
0x180008145  mov     [rbx+88h], rax
0x18000814c  test    rax, rax
0x18000814f  jnz     short loc_180008163
0x180008151  mov     dword ptr [rbx+80h], 0
0x18000815b  call    cs:__imp_GetLastError
0x180008161  jmp     short loc_1800081BA
0x180008163  cmp     dword ptr [rbx+8], 2
0x180008167  mov     rax, [rbx+88h]
0x18000816e  setz    cl
0x180008171  add     cl, 80h
0x180008174  mov     [rax], cl
0x180008176  jmp     short loc_1800081B8
0x180008178  mov     dword ptr [rbx+7Ch], 0C227h
0x18000817f  cmp     dword ptr [rbx+80h], 0
0x180008186  jz      short loc_1800081B8
0x180008188  mov     r8, [rbx+88h]; lpMem
0x18000818f  mov     dword ptr [rbx+80h], 0
0x180008199  test    r8, r8
0x18000819c  jz      short loc_1800081B8
0x18000819e  mov     rcx, cs:hHeap; hHeap
0x1800081a5  xor     edx, edx; dwFlags
0x1800081a7  call    cs:__imp_HeapFree
0x1800081ad  mov     qword ptr [rbx+88h], 0
0x1800081b8  xor     eax, eax
0x1800081ba  mov     rbx, [rsp+28h+arg_0]
0x1800081bf  add     rsp, 20h
0x1800081c3  pop     rsi
0x1800081c4  retn
```
