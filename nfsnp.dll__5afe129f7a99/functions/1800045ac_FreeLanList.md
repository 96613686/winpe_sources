# FreeLanList

- ea: `0x1800045ac`
- end: `0x180004650`
- name: `FreeLanList`
- size: `164`
- prototype: `HGLOBAL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004348`
- `0x18000a020`

## callees

- `0x180002508`
- `0x1800045ac`
- `0x180009338`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800045fc`
- `KERNEL32!GlobalFree` at `0x1800045fc`

## pseudocode

```c
HGLOBAL __fastcall FreeLanList(__int64 a1)
{
  HGLOBAL result; // rax
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    result = (HGLOBAL)WPP_SF_q(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        24,
                        &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                        a1);
  v3 = *(_QWORD **)(a1 + 40);
  if ( v3 )
  {
    do
    {
      v4 = (_QWORD *)v3[1];
      result = GlobalFree(v3);
      v3 = v4;
    }
    while ( v4 );
  }
  *(_QWORD *)(a1 + 40) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return (HGLOBAL)WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800045ac  mov     [rsp+arg_0], rbx
0x1800045b1  mov     [rsp+arg_8], rsi
0x1800045b6  push    rdi
0x1800045b7  sub     rsp, 20h
0x1800045bb  mov     rdi, rcx
0x1800045be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045c5  lea     rsi, WPP_GLOBAL_Control
0x1800045cc  cmp     rcx, rsi
0x1800045cf  jz      short loc_1800045EF
0x1800045d1  test    byte ptr [rcx+1Ch], 1
0x1800045d5  jz      short loc_1800045EF
0x1800045d7  mov     rcx, [rcx+10h]
0x1800045db  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800045e2  mov     edx, 18h
0x1800045e7  mov     r9, rdi
0x1800045ea  call    WPP_SF_q
0x1800045ef  mov     rcx, [rdi+28h]; hMem
0x1800045f3  test    rcx, rcx
0x1800045f6  jz      short loc_180004610
0x1800045f8  mov     rbx, [rcx+8]
0x1800045fc  call    cs:__imp_GlobalFree
0x180004603  nop     dword ptr [rax+rax+00h]
0x180004608  mov     rcx, rbx
0x18000460b  test    rbx, rbx
0x18000460e  jnz     short loc_1800045F8
0x180004610  mov     qword ptr [rdi+28h], 0
0x180004618  mov     rcx, cs:WPP_GLOBAL_Control
0x18000461f  cmp     rcx, rsi
0x180004622  jz      short loc_18000463F
0x180004624  test    byte ptr [rcx+1Ch], 1
0x180004628  jz      short loc_18000463F
0x18000462a  mov     rcx, [rcx+10h]
0x18000462e  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004635  mov     edx, 19h
0x18000463a  call    WPP_SF_
0x18000463f  mov     rbx, [rsp+28h+arg_0]
0x180004644  mov     rsi, [rsp+28h+arg_8]
0x180004649  add     rsp, 20h
0x18000464d  pop     rdi
0x18000464e  retn
```
