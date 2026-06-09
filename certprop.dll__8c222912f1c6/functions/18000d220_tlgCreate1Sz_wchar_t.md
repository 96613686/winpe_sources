# _tlgCreate1Sz_wchar_t

- ea: `0x18000d220`
- end: `0x18000d25f`
- name: `_tlgCreate1Sz_wchar_t`
- size: `63`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b09c`
- `0x1800180f4`

## callees

- `0x18000d220`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_wchar_t(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    while ( *((_WORD *)a2 + ++v2) != 0 )
      ;
    result = (unsigned int)(2 * v2 + 2);
  }
  else
  {
    a2 = &qword_180027F58;
    result = 2;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x18000d220  test    rdx, rdx
0x18000d223  jz      short loc_18000D251
0x18000d225  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d22c  nop     dword ptr [rax+00h]
0x18000d230  cmp     word ptr [rdx+rax*2+2], 0
0x18000d236  lea     rax, [rax+1]
0x18000d23a  jnz     short loc_18000D230
0x18000d23c  lea     eax, ds:2[rax*2]
0x18000d243  mov     [rcx], rdx
0x18000d246  mov     [rcx+8], eax
0x18000d249  mov     dword ptr [rcx+0Ch], 0
0x18000d250  retn
0x18000d251  lea     rdx, qword_180027F58
0x18000d258  mov     eax, 2
0x18000d25d  jmp     short loc_18000D243
```
