# List_Deallocate

- ea: `0x18000137c`
- end: `0x1800013f3`
- name: `List_Deallocate`
- size: `119`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000240c`
- `0x180003d28`
- `0x1800042b0`

## callees

- `0x18000137c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800013e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800013e8`

## pseudocode

```c
__int64 __fastcall List_Deallocate(unsigned int a1, __int64 a2)
{
  __int64 v2; // r9
  __int64 v3; // r10
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v7; // r8
  __int64 v8; // rcx

  v2 = 2LL * a1;
  v3 = 0;
  v4 = qword_18000A628[2 * a1];
  v5 = v4 + 16;
  result = -v4;
  v7 = v5 & -(__int64)(result != 0);
  if ( v7 )
  {
    while ( v7 != a2 )
    {
      if ( v7 )
      {
        result = *(_QWORD *)(v7 - 16);
        if ( result )
        {
          v3 = v7;
          v7 = result + 16;
          if ( result != -16 )
            continue;
        }
      }
      return result;
    }
    v8 = v7 - 16;
    if ( v3 )
      *(_QWORD *)(v3 - 16) = *(_QWORD *)v8;
    if ( qword_18000A628[v2] == v8 )
      qword_18000A628[v2] = *(_QWORD *)v8;
    return (__int64)LocalFree(*(HLOCAL *)(v8 + 8));
  }
  return result;
}

```

## disassembly

```asm
0x18000137c  sub     rsp, 28h
0x180001380  mov     r9d, ecx
0x180001383  lea     r11, qword_18000A628
0x18000138a  add     r9, r9
0x18000138d  xor     r10d, r10d
0x180001390  mov     rax, [r11+r9*8]
0x180001394  lea     rcx, [rax+10h]
0x180001398  neg     rax
0x18000139b  sbb     r8, r8
0x18000139e  and     r8, rcx
0x1800013a1  jz      short loc_1800013EE
0x1800013a3  cmp     r8, rdx
0x1800013a6  jz      short loc_1800013C7
0x1800013a8  test    r8, r8
0x1800013ab  jz      short loc_1800013EE
0x1800013ad  mov     rax, [r8-10h]
0x1800013b1  test    rax, rax
0x1800013b4  jz      short loc_1800013EE
0x1800013b6  mov     r10, r8
0x1800013b9  lea     r8, [rax+10h]
0x1800013bd  test    r8, r8
0x1800013c0  jnz     short loc_1800013A3
0x1800013c2  add     rsp, 28h
0x1800013c6  retn
0x1800013c7  lea     rcx, [r8-10h]
0x1800013cb  test    r10, r10
0x1800013ce  jz      short loc_1800013D7
0x1800013d0  mov     rax, [rcx]
0x1800013d3  mov     [r10-10h], rax
0x1800013d7  cmp     [r11+r9*8], rcx
0x1800013db  jnz     short loc_1800013E4
0x1800013dd  mov     rax, [rcx]
0x1800013e0  mov     [r11+r9*8], rax
0x1800013e4  mov     rcx, [rcx+8]; hMem
0x1800013e8  call    cs:__imp_LocalFree
0x1800013ee  add     rsp, 28h
0x1800013f2  retn
```
