# WPP_SF_Z

- ea: `0x1400027ac`
- end: `0x14000281d`
- name: `WPP_SF_Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140005a4c`
- `0x140005b3c`
- `0x1400130e0`
- `0x14001f6c0`
- `0x1400252f8`
- `0x140025520`
- `0x1400255d4`
- `0x140025758`
- `0x14002586c`
- `0x140025aa0`

## callees

- `0x1400027ac`
- `0x140006880`

## pseudocode

```c
__int64 __fastcall WPP_SF_Z(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // r10
  const wchar_t *v5; // r11

  if ( a4 )
  {
    v4 = *a4;
    if ( *a4 )
    {
      v5 = (const wchar_t *)*((_QWORD *)a4 + 1);
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 8;
  }
  v5 = L"NULL";
LABEL_6:
  if ( !a4 )
    a4 = L"\b";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           2,
           v5,
           v4,
           0);
}

```

## disassembly

```asm
0x1400027ac  push    rbx
0x1400027ae  sub     rsp, 50h
0x1400027b2  xor     ebx, ebx
0x1400027b4  test    r9, r9
0x1400027b7  jz      short loc_1400027C9
0x1400027b9  movzx   r10d, word ptr [r9]
0x1400027bd  cmp     [r9], bx
0x1400027c1  jz      short loc_1400027CF
0x1400027c3  mov     r11, [r9+8]
0x1400027c7  jmp     short loc_1400027D6
0x1400027c9  mov     r10d, 8
0x1400027cf  lea     r11, aNull_0; "NULL"
0x1400027d6  mov     [rsp+58h+var_18], rbx
0x1400027db  lea     rax, asc_140009230; "\b"
0x1400027e2  mov     [rsp+58h+var_20], r10
0x1400027e7  test    r9, r9
0x1400027ea  mov     [rsp+58h+var_28], r11
0x1400027ef  cmovz   r9, rax
0x1400027f3  mov     [rsp+58h+var_30], 2
0x1400027fc  mov     rax, cs:pfnWppTraceMessage
0x140002803  mov     [rsp+58h+var_38], r9
0x140002808  movzx   r9d, dx
0x14000280c  mov     edx, 2Bh ; '+'
0x140002811  call    _guard_dispatch_icall
0x140002816  add     rsp, 50h
0x14000281a  pop     rbx
0x14000281b  retn
```
