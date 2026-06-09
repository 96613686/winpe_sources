# bytes2time

- ea: `0x1800035d0`
- end: `0x18000360e`
- name: `bytes2time`
- size: `62`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003114`
- `0x180003568`
- `0x180003d64`
- `0x18000492c`
- `0x180004d18`

## callees

- `0x1800035d0`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180003603`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180003603`

## pseudocode

```c
int __fastcall bytes2time(__int64 a1, int a2, int a3)
{
  int result; // eax
  __int64 v4; // rdx
  int v5; // r8d
  int v6; // edx

  result = a2;
  if ( a3 == 9 )
  {
    v4 = *(_QWORD *)(a1 + 168);
    v5 = *(_DWORD *)(v4 + 8);
    v6 = *(_DWORD *)(v4 + 4);
  }
  else
  {
    if ( a3 )
      return result;
    v6 = 1000;
    v5 = *(_DWORD *)(*(_QWORD *)(a1 + 168) + 8LL);
  }
  return MulDiv(result, v6, v5);
}

```

## disassembly

```asm
0x1800035d0  sub     rsp, 28h
0x1800035d4  mov     eax, edx
0x1800035d6  cmp     r8d, 9
0x1800035da  jnz     short loc_1800035EC
0x1800035dc  mov     rdx, [rcx+0A8h]
0x1800035e3  mov     r8d, [rdx+8]
0x1800035e7  mov     edx, [rdx+4]
0x1800035ea  jmp     short loc_180003601
0x1800035ec  test    r8d, r8d
0x1800035ef  jnz     short loc_180003609
0x1800035f1  mov     r8, [rcx+0A8h]
0x1800035f8  mov     edx, 3E8h; nNumerator
0x1800035fd  mov     r8d, [r8+8]; nDenominator
0x180003601  mov     ecx, eax; nNumber
0x180003603  call    cs:__imp_MulDiv
0x180003609  add     rsp, 28h
0x18000360d  retn
```
