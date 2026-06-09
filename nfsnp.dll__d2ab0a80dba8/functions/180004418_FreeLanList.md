# FreeLanList

- ea: `0x180004418`
- end: `0x1800044b5`
- name: `FreeLanList`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004178`
- `0x180009948`

## callees

- `0x1800023f0`
- `0x180004418`
- `0x180008ce0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180004468`
- `KERNEL32!GlobalFree` at `0x180004468`

## pseudocode

```c
unsigned int __fastcall FreeLanList(__int64 a1)
{
  unsigned int result; // eax
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    result = WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x18u, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, a1);
  v3 = *(_QWORD **)(a1 + 40);
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
  *(_QWORD *)(a1 + 40) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x19u, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180004418  mov     [rsp+arg_0], rbx
0x18000441d  mov     [rsp+arg_8], rsi
0x180004422  push    rdi
0x180004423  sub     rsp, 20h
0x180004427  mov     rdi, rcx
0x18000442a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004431  lea     rsi, WPP_GLOBAL_Control
0x180004438  cmp     rcx, rsi
0x18000443b  jz      short loc_18000445B
0x18000443d  test    byte ptr [rcx+1Ch], 1
0x180004441  jz      short loc_18000445B
0x180004443  mov     rcx, [rcx+10h]
0x180004447  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000444e  mov     edx, 18h
0x180004453  mov     r9, rdi
0x180004456  call    WPP_SF_q
0x18000445b  mov     rcx, [rdi+28h]; hMem
0x18000445f  test    rcx, rcx
0x180004462  jz      short loc_180004476
0x180004464  mov     rbx, [rcx+8]
0x180004468  call    cs:__imp_GlobalFree
0x18000446e  mov     rcx, rbx
0x180004471  test    rbx, rbx
0x180004474  jnz     short loc_180004464
0x180004476  mov     qword ptr [rdi+28h], 0
0x18000447e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004485  cmp     rcx, rsi
0x180004488  jz      short loc_1800044A5
0x18000448a  test    byte ptr [rcx+1Ch], 1
0x18000448e  jz      short loc_1800044A5
0x180004490  mov     rcx, [rcx+10h]
0x180004494  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000449b  mov     edx, 19h
0x1800044a0  call    WPP_SF_
0x1800044a5  mov     rbx, [rsp+28h+arg_0]
0x1800044aa  mov     rsi, [rsp+28h+arg_8]
0x1800044af  add     rsp, 20h
0x1800044b3  pop     rdi
0x1800044b4  retn
```
