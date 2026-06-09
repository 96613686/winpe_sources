# FreeHostList

- ea: `0x180004374`
- end: `0x180004411`
- name: `FreeHostList`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004178`
- `0x18000a468`

## callees

- `0x1800023f0`
- `0x180004374`
- `0x180008ce0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800043c4`
- `KERNEL32!GlobalFree` at `0x1800043c4`

## pseudocode

```c
unsigned int __fastcall FreeHostList(__int64 a1)
{
  unsigned int result; // eax
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    result = WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Au, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, a1);
  v3 = *(_QWORD **)(a1 + 56);
  if ( v3 )
  {
    do
    {
      v4 = (_QWORD *)v3[1];
      result = (unsigned int)GlobalFree(v3);
      v3 = v4;
    }
    while ( v4 );
  }
  *(_QWORD *)(a1 + 56) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Bu, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180004374  mov     [rsp+arg_0], rbx
0x180004379  mov     [rsp+arg_8], rsi
0x18000437e  push    rdi
0x18000437f  sub     rsp, 20h
0x180004383  mov     rdi, rcx
0x180004386  mov     rcx, cs:WPP_GLOBAL_Control
0x18000438d  lea     rsi, WPP_GLOBAL_Control
0x180004394  cmp     rcx, rsi
0x180004397  jz      short loc_1800043B7
0x180004399  test    byte ptr [rcx+1Ch], 1
0x18000439d  jz      short loc_1800043B7
0x18000439f  mov     rcx, [rcx+10h]
0x1800043a3  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800043aa  mov     edx, 1Ah
0x1800043af  mov     r9, rdi
0x1800043b2  call    WPP_SF_q
0x1800043b7  mov     rcx, [rdi+38h]; hMem
0x1800043bb  test    rcx, rcx
0x1800043be  jz      short loc_1800043D2
0x1800043c0  mov     rbx, [rcx+8]
0x1800043c4  call    cs:__imp_GlobalFree
0x1800043ca  mov     rcx, rbx
0x1800043cd  test    rbx, rbx
0x1800043d0  jnz     short loc_1800043C0
0x1800043d2  mov     qword ptr [rdi+38h], 0
0x1800043da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043e1  cmp     rcx, rsi
0x1800043e4  jz      short loc_180004401
0x1800043e6  test    byte ptr [rcx+1Ch], 1
0x1800043ea  jz      short loc_180004401
0x1800043ec  mov     rcx, [rcx+10h]
0x1800043f0  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800043f7  mov     edx, 1Bh
0x1800043fc  call    WPP_SF_
0x180004401  mov     rbx, [rsp+28h+arg_0]
0x180004406  mov     rsi, [rsp+28h+arg_8]
0x18000440b  add     rsp, 20h
0x18000440f  pop     rdi
0x180004410  retn
```
