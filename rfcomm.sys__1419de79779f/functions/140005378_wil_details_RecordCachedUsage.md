# wil_details_RecordCachedUsage

- ea: `0x140005378`
- end: `0x1400054c6`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400334b0`

## callees

- `0x140005378`
- `0x14001fc30`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400054a7`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400054a7`

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
0x140005378  sub     rsp, 68h
0x14000537c  mov     rax, cs:__security_cookie
0x140005383  xor     rax, rsp
0x140005386  mov     [rsp+68h+var_18], rax
0x14000538b  mov     r9, rdx
0x14000538e  mov     r10d, ecx
0x140005391  prefetchw byte ptr [rdx]
0x140005394  mov     eax, [rdx]
0x140005396  mov     r8d, eax
0x140005399  and     r8d, 0FFC0401Eh
0x1400053a0  lock cmpxchg [rdx], r8d
0x1400053a5  jnz     short loc_140005396
0x1400053a7  mov     r8d, eax
0x1400053aa  mov     ecx, eax
0x1400053ac  shr     r8d, 1
0x1400053af  and     r8d, 0Fh
0x1400053b3  jz      short loc_1400053D0
0x1400053b5  prefetchw byte ptr [rdx+4]
0x1400053b9  mov     eax, [rdx+4]
0x1400053bc  mov     edx, eax
0x1400053be  or      edx, r8d
0x1400053c1  lock cmpxchg [r9+4], edx
0x1400053c7  jnz     short loc_1400053BC
0x1400053c9  not     eax
0x1400053cb  and     eax, r8d
0x1400053ce  jmp     short loc_1400053D3
0x1400053d0  mov     eax, r8d
0x1400053d3  mov     r8d, 2
0x1400053d9  lea     r9d, [r8-1]
0x1400053dd  test    r9b, al
0x1400053e0  jz      short loc_1400053F6
0x1400053e2  mov     [rsp+68h+var_48], r10d
0x1400053e7  lea     rdx, [rsp+68h+var_40]
0x1400053ec  mov     [rsp+68h+var_44], 10002h
0x1400053f4  jmp     short loc_1400053FB
0x1400053f6  lea     rdx, [rsp+68h+var_48]
0x1400053fb  test    r8b, al
0x1400053fe  jz      short loc_14000540E
0x140005400  mov     [rdx], r10d
0x140005403  mov     dword ptr [rdx+4], 10006h
0x14000540a  add     rdx, 8
0x14000540e  test    al, 4
0x140005410  jz      short loc_140005420
0x140005412  mov     [rdx], r10d
0x140005415  mov     dword ptr [rdx+4], 10003h
0x14000541c  add     rdx, 8
0x140005420  cmp     eax, 8
0x140005423  jb      short loc_140005433
0x140005425  mov     [rdx], r10d
0x140005428  mov     dword ptr [rdx+4], 10007h
0x14000542f  add     rdx, 8
0x140005433  mov     r8d, ecx
0x140005436  mov     r11d, 1FFh
0x14000543c  shr     r8d, 5
0x140005440  test    r11d, r8d
0x140005443  jz      short loc_140005466
0x140005445  and     r8w, r11w
0x140005449  mov     [rdx], r10d
0x14000544c  mov     eax, ecx
0x14000544e  mov     [rdx+6], r8w
0x140005453  shr     eax, 0Eh
0x140005456  and     ax, r9w
0x14000545a  shl     ax, 2
0x14000545e  mov     [rdx+4], ax
0x140005462  add     rdx, 8
0x140005466  mov     eax, ecx
0x140005468  shr     eax, 0Fh
0x14000546b  test    al, 7Fh
0x14000546d  jz      short loc_140005491
0x14000546f  shr     ecx, 16h
0x140005472  and     ax, 7Fh
0x140005476  and     cx, r9w
0x14000547a  mov     [rdx], r10d
0x14000547d  shl     cx, 2
0x140005481  add     cx, r9w
0x140005485  mov     [rdx+6], ax
0x140005489  mov     [rdx+4], cx
0x14000548d  add     rdx, 8
0x140005491  lea     rax, [rsp+68h+var_48]
0x140005496  sub     rdx, rax
0x140005499  sar     rdx, 3
0x14000549d  test    rdx, rdx
0x1400054a0  jle     short loc_1400054B3
0x1400054a2  lea     rcx, [rsp+68h+var_48]
0x1400054a7  call    cs:__imp_RtlRecordFeatureUsage
0x1400054ae  nop     dword ptr [rax+rax+00h]
0x1400054b3  mov     rcx, [rsp+68h+var_18]
0x1400054b8  xor     rcx, rsp; StackCookie
0x1400054bb  call    __security_check_cookie
0x1400054c0  add     rsp, 68h
0x1400054c4  retn
```
