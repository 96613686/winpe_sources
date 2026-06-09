# FIPfOpenListRemove

- ea: `0x140015754`
- end: `0x14001579f`
- name: `FIPfOpenListRemove`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400156d4`

## callees

- `0x140015754`

## pseudocode

```c
_QWORD *__fastcall FIPfOpenListRemove(_QWORD **a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  _QWORD *result; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // rdx

  for ( result = *a1; ; result = (_QWORD *)*result )
  {
    if ( result == a1 )
    {
      _InterlockedIncrement(&dword_1400097E8);
      return 0;
    }
    if ( result[5] == a3 && result[3] == a4 )
      break;
  }
  v6 = (_QWORD *)*result;
  if ( *(_QWORD **)(*result + 8LL) != result || (v7 = (_QWORD *)result[1], (_QWORD *)*v7 != result) )
    __fastfail(3u);
  *v7 = v6;
  v6[1] = v7;
  --*a2;
  return result;
}

```

## disassembly

```asm
0x140015754  mov     rax, [rcx]
0x140015757  mov     r10, rdx
0x14001575a  cmp     rax, rcx
0x14001575d  jz      short loc_140015795
0x14001575f  cmp     [rax+28h], r8
0x140015763  jnz     short loc_14001576B
0x140015765  cmp     [rax+18h], r9
0x140015769  jz      short loc_140015770
0x14001576b  mov     rax, [rax]
0x14001576e  jmp     short loc_14001575A
0x140015770  mov     rcx, [rax]
0x140015773  cmp     [rcx+8], rax
0x140015777  jnz     short loc_14001578E
0x140015779  mov     rdx, [rax+8]
0x14001577d  cmp     [rdx], rax
0x140015780  jnz     short loc_14001578E
0x140015782  mov     [rdx], rcx
0x140015785  mov     [rcx+8], rdx
0x140015789  dec     dword ptr [r10]
0x14001578c  retn
0x14001578e  mov     ecx, 3
0x140015793  int     29h; Win8: RtlFailFast(ecx)
0x140015795  lock inc cs:dword_1400097E8
0x14001579c  xor     eax, eax
0x14001579e  retn
```
