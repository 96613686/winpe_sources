# FreeHostList

- ea: `0x180004500`
- end: `0x1800045a4`
- name: `FreeHostList`
- size: `164`
- prototype: `HGLOBAL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004348`
- `0x18000abcc`

## callees

- `0x180002508`
- `0x180004500`
- `0x180009338`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180004550`
- `KERNEL32!GlobalFree` at `0x180004550`

## pseudocode

```c
HGLOBAL __fastcall FreeHostList(__int64 a1)
{
  HGLOBAL result; // rax
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    result = (HGLOBAL)WPP_SF_q(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        26,
                        &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                        a1);
  v3 = *(_QWORD **)(a1 + 56);
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
  *(_QWORD *)(a1 + 56) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return (HGLOBAL)WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180004500  mov     [rsp+arg_0], rbx
0x180004505  mov     [rsp+arg_8], rsi
0x18000450a  push    rdi
0x18000450b  sub     rsp, 20h
0x18000450f  mov     rdi, rcx
0x180004512  mov     rcx, cs:WPP_GLOBAL_Control
0x180004519  lea     rsi, WPP_GLOBAL_Control
0x180004520  cmp     rcx, rsi
0x180004523  jz      short loc_180004543
0x180004525  test    byte ptr [rcx+1Ch], 1
0x180004529  jz      short loc_180004543
0x18000452b  mov     rcx, [rcx+10h]
0x18000452f  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004536  mov     edx, 1Ah
0x18000453b  mov     r9, rdi
0x18000453e  call    WPP_SF_q
0x180004543  mov     rcx, [rdi+38h]; hMem
0x180004547  test    rcx, rcx
0x18000454a  jz      short loc_180004564
0x18000454c  mov     rbx, [rcx+8]
0x180004550  call    cs:__imp_GlobalFree
0x180004557  nop     dword ptr [rax+rax+00h]
0x18000455c  mov     rcx, rbx
0x18000455f  test    rbx, rbx
0x180004562  jnz     short loc_18000454C
0x180004564  mov     qword ptr [rdi+38h], 0
0x18000456c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004573  cmp     rcx, rsi
0x180004576  jz      short loc_180004593
0x180004578  test    byte ptr [rcx+1Ch], 1
0x18000457c  jz      short loc_180004593
0x18000457e  mov     rcx, [rcx+10h]
0x180004582  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004589  mov     edx, 1Bh
0x18000458e  call    WPP_SF_
0x180004593  mov     rbx, [rsp+28h+arg_0]
0x180004598  mov     rsi, [rsp+28h+arg_8]
0x18000459d  add     rsp, 20h
0x1800045a1  pop     rdi
0x1800045a2  retn
```
