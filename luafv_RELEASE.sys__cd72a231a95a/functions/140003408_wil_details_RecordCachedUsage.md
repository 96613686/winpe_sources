# wil_details_RecordCachedUsage

- ea: `0x140003408`
- end: `0x140003556`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: `_DWORD *__fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140016b00`

## callees

- `0x140003408`
- `0x140005bb0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003537`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003537`

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
0x140003408  sub     rsp, 68h
0x14000340c  mov     rax, cs:__security_cookie
0x140003413  xor     rax, rsp
0x140003416  mov     [rsp+68h+var_18], rax
0x14000341b  mov     r9, rdx
0x14000341e  mov     r10d, ecx
0x140003421  prefetchw byte ptr [rdx]
0x140003424  mov     eax, [rdx]
0x140003426  mov     r8d, eax
0x140003429  and     r8d, 0FFC0401Eh
0x140003430  lock cmpxchg [rdx], r8d
0x140003435  jnz     short loc_140003426
0x140003437  mov     r8d, eax
0x14000343a  mov     ecx, eax
0x14000343c  shr     r8d, 1
0x14000343f  and     r8d, 0Fh
0x140003443  jz      short loc_140003460
0x140003445  prefetchw byte ptr [rdx+4]
0x140003449  mov     eax, [rdx+4]
0x14000344c  mov     edx, eax
0x14000344e  or      edx, r8d
0x140003451  lock cmpxchg [r9+4], edx
0x140003457  jnz     short loc_14000344C
0x140003459  not     eax
0x14000345b  and     eax, r8d
0x14000345e  jmp     short loc_140003463
0x140003460  mov     eax, r8d
0x140003463  mov     r8d, 2
0x140003469  lea     r9d, [r8-1]
0x14000346d  test    r9b, al
0x140003470  jz      short loc_140003486
0x140003472  mov     [rsp+68h+var_48], r10d
0x140003477  lea     rdx, [rsp+68h+var_40]
0x14000347c  mov     [rsp+68h+var_44], 10002h
0x140003484  jmp     short loc_14000348B
0x140003486  lea     rdx, [rsp+68h+var_48]
0x14000348b  test    r8b, al
0x14000348e  jz      short loc_14000349E
0x140003490  mov     [rdx], r10d
0x140003493  mov     dword ptr [rdx+4], 10006h
0x14000349a  add     rdx, 8
0x14000349e  test    al, 4
0x1400034a0  jz      short loc_1400034B0
0x1400034a2  mov     [rdx], r10d
0x1400034a5  mov     dword ptr [rdx+4], 10003h
0x1400034ac  add     rdx, 8
0x1400034b0  cmp     eax, 8
0x1400034b3  jb      short loc_1400034C3
0x1400034b5  mov     [rdx], r10d
0x1400034b8  mov     dword ptr [rdx+4], 10007h
0x1400034bf  add     rdx, 8
0x1400034c3  mov     r8d, ecx
0x1400034c6  mov     r11d, 1FFh
0x1400034cc  shr     r8d, 5
0x1400034d0  test    r11d, r8d
0x1400034d3  jz      short loc_1400034F6
0x1400034d5  and     r8w, r11w
0x1400034d9  mov     [rdx], r10d
0x1400034dc  mov     eax, ecx
0x1400034de  mov     [rdx+6], r8w
0x1400034e3  shr     eax, 0Eh
0x1400034e6  and     ax, r9w
0x1400034ea  shl     ax, 2
0x1400034ee  mov     [rdx+4], ax
0x1400034f2  add     rdx, 8
0x1400034f6  mov     eax, ecx
0x1400034f8  shr     eax, 0Fh
0x1400034fb  test    al, 7Fh
0x1400034fd  jz      short loc_140003521
0x1400034ff  shr     ecx, 16h
0x140003502  and     ax, 7Fh
0x140003506  and     cx, r9w
0x14000350a  mov     [rdx], r10d
0x14000350d  shl     cx, 2
0x140003511  add     cx, r9w
0x140003515  mov     [rdx+6], ax
0x140003519  mov     [rdx+4], cx
0x14000351d  add     rdx, 8
0x140003521  lea     rax, [rsp+68h+var_48]
0x140003526  sub     rdx, rax
0x140003529  sar     rdx, 3
0x14000352d  test    rdx, rdx
0x140003530  jle     short loc_140003543
0x140003532  lea     rcx, [rsp+68h+var_48]
0x140003537  call    cs:__imp_RtlRecordFeatureUsage
0x14000353e  nop     dword ptr [rax+rax+00h]
0x140003543  mov     rcx, [rsp+68h+var_18]
0x140003548  xor     rcx, rsp; StackCookie
0x14000354b  call    __security_check_cookie
0x140003550  add     rsp, 68h
0x140003554  retn
```
