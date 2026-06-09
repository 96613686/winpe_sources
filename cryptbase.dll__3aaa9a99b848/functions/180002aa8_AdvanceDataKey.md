# AdvanceDataKey

- ea: `0x180002aa8`
- end: `0x180002add`
- name: `AdvanceDataKey`
- size: `53`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001820`
- `0x180002ae4`
- `0x180002b3c`
- `0x180002bdc`
- `0x180002c90`

## callees

- `0x180002aa8`

## pseudocode

```c
__int64 __fastcall AdvanceDataKey(unsigned int *a1)
{
  __int64 v1; // r8
  __int64 v2; // r9
  __int64 result; // rax

  if ( *a1 > 7 )
  {
    *((_QWORD *)a1 + 2) += 7LL;
    v1 = *((_QWORD *)a1 + 1);
    v2 = *a1;
    result = v2 + v1;
    if ( *((_QWORD *)a1 + 2) + 7LL > (unsigned __int64)(v2 + v1) )
    {
      result = v2 + 2 * v1 - *((_QWORD *)a1 + 2);
      *((_QWORD *)a1 + 2) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002aa8  cmp     dword ptr [rcx], 7
0x180002aab  jbe     short locret_180002ADC
0x180002aad  add     qword ptr [rcx+10h], 7
0x180002ab2  mov     r8, [rcx+8]
0x180002ab6  mov     r9d, [rcx]
0x180002ab9  mov     rdx, [rcx+10h]
0x180002abd  add     rdx, 7
0x180002ac1  lea     rax, [r9+r8]
0x180002ac5  cmp     rdx, rax
0x180002ac8  jbe     short locret_180002ADC
0x180002aca  lea     rax, [r8+r8]
0x180002ace  sub     rax, rdx
0x180002ad1  add     rax, 7
0x180002ad5  add     rax, r9
0x180002ad8  mov     [rcx+10h], rax
0x180002adc  retn
```
