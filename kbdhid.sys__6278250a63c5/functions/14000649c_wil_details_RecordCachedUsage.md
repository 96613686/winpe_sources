# wil_details_RecordCachedUsage

- ea: `0x14000649c`
- end: `0x1400065ea`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000f780`

## callees

- `0x14000649c`
- `0x140007130`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400065cb`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400065cb`

## pseudocode

```c
_DWORD *__fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  _DWORD *result; // rax
  _DWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h] BYREF

  _m_prefetchw((const void *)a2);
  v3 = _InterlockedAnd((volatile signed __int32 *)a2, 0xFFC0401E);
  v4 = (v3 >> 1) & 0xF;
  if ( v4 )
  {
    _m_prefetchw((const void *)(a2 + 4));
    v5 = *(_DWORD *)(a2 + 4);
    do
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 4), v4 | v5, v5);
    }
    while ( v6 != v5 );
    v7 = v4 & ~v5;
  }
  else
  {
    v7 = 0;
  }
  if ( (v7 & 1) != 0 )
  {
    v10[0] = a1;
    v8 = &v11;
    v10[1] = 65538;
  }
  else
  {
    v8 = (char *)v10;
  }
  if ( (v7 & 2) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65542;
    v8 += 8;
  }
  if ( (v7 & 4) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65539;
    v8 += 8;
  }
  if ( v7 >= 8 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65543;
    v8 += 8;
  }
  if ( ((v3 >> 5) & 0x1FF) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 5) & 0x1FF;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 14) & 1);
    v8 += 8;
  }
  if ( ((v3 >> 15) & 0x7F) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 15) & 0x7F;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 22) & 1) + 1;
    v8 += 8;
  }
  result = v10;
  if ( (v8 - (char *)v10) >> 3 > 0 )
    return (_DWORD *)RtlRecordFeatureUsage(v10);
  return result;
}

```

## disassembly

```asm
0x14000649c  sub     rsp, 68h
0x1400064a0  mov     rax, cs:__security_cookie
0x1400064a7  xor     rax, rsp
0x1400064aa  mov     [rsp+68h+var_18], rax
0x1400064af  mov     r9, rdx
0x1400064b2  mov     r10d, ecx
0x1400064b5  prefetchw byte ptr [rdx]
0x1400064b8  mov     eax, [rdx]
0x1400064ba  mov     r8d, eax
0x1400064bd  and     r8d, 0FFC0401Eh
0x1400064c4  lock cmpxchg [rdx], r8d
0x1400064c9  jnz     short loc_1400064BA
0x1400064cb  mov     r8d, eax
0x1400064ce  mov     ecx, eax
0x1400064d0  shr     r8d, 1
0x1400064d3  and     r8d, 0Fh
0x1400064d7  jz      short loc_1400064F4
0x1400064d9  prefetchw byte ptr [rdx+4]
0x1400064dd  mov     eax, [rdx+4]
0x1400064e0  mov     edx, eax
0x1400064e2  or      edx, r8d
0x1400064e5  lock cmpxchg [r9+4], edx
0x1400064eb  jnz     short loc_1400064E0
0x1400064ed  not     eax
0x1400064ef  and     eax, r8d
0x1400064f2  jmp     short loc_1400064F7
0x1400064f4  mov     eax, r8d
0x1400064f7  mov     r8d, 2
0x1400064fd  lea     r9d, [r8-1]
0x140006501  test    r9b, al
0x140006504  jz      short loc_14000651A
0x140006506  mov     [rsp+68h+var_48], r10d
0x14000650b  lea     rdx, [rsp+68h+var_40]
0x140006510  mov     [rsp+68h+var_44], 10002h
0x140006518  jmp     short loc_14000651F
0x14000651a  lea     rdx, [rsp+68h+var_48]
0x14000651f  test    r8b, al
0x140006522  jz      short loc_140006532
0x140006524  mov     [rdx], r10d
0x140006527  mov     dword ptr [rdx+4], 10006h
0x14000652e  add     rdx, 8
0x140006532  test    al, 4
0x140006534  jz      short loc_140006544
0x140006536  mov     [rdx], r10d
0x140006539  mov     dword ptr [rdx+4], 10003h
0x140006540  add     rdx, 8
0x140006544  cmp     eax, 8
0x140006547  jb      short loc_140006557
0x140006549  mov     [rdx], r10d
0x14000654c  mov     dword ptr [rdx+4], 10007h
0x140006553  add     rdx, 8
0x140006557  mov     r8d, ecx
0x14000655a  mov     r11d, 1FFh
0x140006560  shr     r8d, 5
0x140006564  test    r11d, r8d
0x140006567  jz      short loc_14000658A
0x140006569  and     r8w, r11w
0x14000656d  mov     [rdx], r10d
0x140006570  mov     eax, ecx
0x140006572  mov     [rdx+6], r8w
0x140006577  shr     eax, 0Eh
0x14000657a  and     ax, r9w
0x14000657e  shl     ax, 2
0x140006582  mov     [rdx+4], ax
0x140006586  add     rdx, 8
0x14000658a  mov     eax, ecx
0x14000658c  shr     eax, 0Fh
0x14000658f  test    al, 7Fh
0x140006591  jz      short loc_1400065B5
0x140006593  shr     ecx, 16h
0x140006596  and     ax, 7Fh
0x14000659a  and     cx, r9w
0x14000659e  mov     [rdx], r10d
0x1400065a1  shl     cx, 2
0x1400065a5  add     cx, r9w
0x1400065a9  mov     [rdx+6], ax
0x1400065ad  mov     [rdx+4], cx
0x1400065b1  add     rdx, 8
0x1400065b5  lea     rax, [rsp+68h+var_48]
0x1400065ba  sub     rdx, rax
0x1400065bd  sar     rdx, 3
0x1400065c1  test    rdx, rdx
0x1400065c4  jle     short loc_1400065D7
0x1400065c6  lea     rcx, [rsp+68h+var_48]
0x1400065cb  call    cs:__imp_RtlRecordFeatureUsage
0x1400065d2  nop     dword ptr [rax+rax+00h]
0x1400065d7  mov     rcx, [rsp+68h+var_18]
0x1400065dc  xor     rcx, rsp; StackCookie
0x1400065df  call    __security_check_cookie
0x1400065e4  add     rsp, 68h
0x1400065e8  retn
```
