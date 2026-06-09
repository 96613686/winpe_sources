# RemoveProtocolCBFromBundle

- ea: `0x14002a83c`
- end: `0x14002a8d9`
- name: `RemoveProtocolCBFromBundle`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d0c0`
- `0x140010f40`

## callees

- `0x14002a83c`

## pseudocode

```c
__int64 __fastcall RemoveProtocolCBFromBundle(_QWORD *a1)
{
  __int64 v1; // r8
  __int64 result; // rax
  __int64 v4; // rax
  _QWORD *v5; // rcx
  int v6; // edx
  __int64 *v7; // rcx

  v1 = a1[8];
  result = *(_QWORD *)(v1 + 264);
  if ( *(_QWORD **)(result + 8LL * a1[6]) == a1 )
  {
    v4 = *a1;
    if ( *(_QWORD **)(*a1 + 8LL) != a1 || (v5 = (_QWORD *)a1[1], (_QWORD *)*v5 != a1) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    result = *(_QWORD *)(v1 + 264);
    *(_QWORD *)(result + 8LL * a1[6]) = 0;
    v6 = --*(_DWORD *)(v1 + 272);
    if ( *(_QWORD **)(v1 + 296) == a1 )
    {
      result = *a1;
      v7 = (__int64 *)(v1 + 280);
      *(_QWORD *)(v1 + 296) = *a1;
      if ( result == v1 + 280 )
      {
        if ( v6 )
        {
          result = *v7;
          *(_QWORD *)(v1 + 296) = *v7;
        }
        else
        {
          *(_QWORD *)(v1 + 296) = 0;
        }
      }
    }
    --*(_DWORD *)(v1 + 24);
  }
  return result;
}

```

## disassembly

```asm
0x14002a83c  mov     r8, [rcx+40h]
0x14002a840  mov     r9, rcx
0x14002a843  mov     rdx, [rcx+30h]
0x14002a847  mov     rax, [r8+108h]
0x14002a84e  cmp     [rax+rdx*8], rcx
0x14002a852  jnz     short locret_14002A8D0
0x14002a854  mov     rax, [rcx]
0x14002a857  cmp     [rax+8], rcx
0x14002a85b  jnz     short loc_14002A8D2
0x14002a85d  mov     rcx, [rcx+8]
0x14002a861  cmp     [rcx], r9
0x14002a864  jnz     short loc_14002A8D2
0x14002a866  mov     [rcx], rax
0x14002a869  or      r10d, 0FFFFFFFFh
0x14002a86d  mov     [rax+8], rcx
0x14002a871  mov     rcx, [r9+30h]
0x14002a875  mov     rax, [r8+108h]
0x14002a87c  mov     qword ptr [rax+rcx*8], 0
0x14002a884  add     [r8+110h], r10d
0x14002a88b  mov     edx, [r8+110h]
0x14002a892  cmp     [r8+128h], r9
0x14002a899  jnz     short loc_14002A8CC
0x14002a89b  mov     rax, [r9]
0x14002a89e  lea     rcx, [r8+118h]
0x14002a8a5  mov     [r8+128h], rax
0x14002a8ac  cmp     rax, rcx
0x14002a8af  jnz     short loc_14002A8CC
0x14002a8b1  test    edx, edx
0x14002a8b3  jz      short loc_14002A8C1
0x14002a8b5  mov     rax, [rcx]
0x14002a8b8  mov     [r8+128h], rax
0x14002a8bf  jmp     short loc_14002A8CC
0x14002a8c1  mov     qword ptr [r8+128h], 0
0x14002a8cc  add     [r8+18h], r10d
0x14002a8d0  retn
0x14002a8d2  mov     ecx, 3
0x14002a8d7  int     29h; Win8: RtlFailFast(ecx)
```
