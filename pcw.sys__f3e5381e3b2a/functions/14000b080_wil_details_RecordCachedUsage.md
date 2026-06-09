# wil_details_RecordCachedUsage

- ea: `0x14000b080`
- end: `0x14000b1c7`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b000`

## callees

- `0x140001370`
- `0x14000b080`
- `0x14000b1d0`

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
    return (_DWORD *)wil_details_RecordFeatureUsageCallback(v10);
  return result;
}

```

## disassembly

```asm
0x14000b080  sub     rsp, 68h
0x14000b084  mov     rax, cs:__security_cookie
0x14000b08b  xor     rax, rsp
0x14000b08e  mov     [rsp+68h+var_18], rax
0x14000b093  mov     r9, rdx
0x14000b096  mov     r10d, ecx
0x14000b099  prefetchw byte ptr [rdx]
0x14000b09c  mov     eax, [rdx]
0x14000b09e  mov     r8d, eax
0x14000b0a1  and     r8d, 0FFC0401Eh
0x14000b0a8  lock cmpxchg [rdx], r8d
0x14000b0ad  jnz     short loc_14000B09E
0x14000b0af  mov     r8d, eax
0x14000b0b2  mov     ecx, eax
0x14000b0b4  shr     r8d, 1
0x14000b0b7  and     r8d, 0Fh
0x14000b0bb  jz      short loc_14000B0D8
0x14000b0bd  prefetchw byte ptr [rdx+4]
0x14000b0c1  mov     eax, [rdx+4]
0x14000b0c4  mov     edx, eax
0x14000b0c6  or      edx, r8d
0x14000b0c9  lock cmpxchg [r9+4], edx
0x14000b0cf  jnz     short loc_14000B0C4
0x14000b0d1  not     eax
0x14000b0d3  and     eax, r8d
0x14000b0d6  jmp     short loc_14000B0DB
0x14000b0d8  mov     eax, r8d
0x14000b0db  mov     r8d, 2
0x14000b0e1  lea     r9d, [r8-1]
0x14000b0e5  test    r9b, al
0x14000b0e8  jz      short loc_14000B0FE
0x14000b0ea  mov     [rsp+68h+var_48], r10d
0x14000b0ef  lea     rdx, [rsp+68h+var_40]
0x14000b0f4  mov     [rsp+68h+var_44], 10002h
0x14000b0fc  jmp     short loc_14000B103
0x14000b0fe  lea     rdx, [rsp+68h+var_48]
0x14000b103  test    r8b, al
0x14000b106  jz      short loc_14000B116
0x14000b108  mov     [rdx], r10d
0x14000b10b  mov     dword ptr [rdx+4], 10006h
0x14000b112  add     rdx, 8
0x14000b116  test    al, 4
0x14000b118  jz      short loc_14000B128
0x14000b11a  mov     [rdx], r10d
0x14000b11d  mov     dword ptr [rdx+4], 10003h
0x14000b124  add     rdx, 8
0x14000b128  cmp     eax, 8
0x14000b12b  jb      short loc_14000B13B
0x14000b12d  mov     [rdx], r10d
0x14000b130  mov     dword ptr [rdx+4], 10007h
0x14000b137  add     rdx, 8
0x14000b13b  mov     r8d, ecx
0x14000b13e  mov     r11d, 1FFh
0x14000b144  shr     r8d, 5
0x14000b148  test    r11d, r8d
0x14000b14b  jz      short loc_14000B16E
0x14000b14d  and     r8w, r11w
0x14000b151  mov     [rdx], r10d
0x14000b154  mov     eax, ecx
0x14000b156  mov     [rdx+6], r8w
0x14000b15b  shr     eax, 0Eh
0x14000b15e  and     ax, r9w
0x14000b162  shl     ax, 2
0x14000b166  mov     [rdx+4], ax
0x14000b16a  add     rdx, 8
0x14000b16e  mov     eax, ecx
0x14000b170  shr     eax, 0Fh
0x14000b173  test    al, 7Fh
0x14000b175  jz      short loc_14000B199
0x14000b177  shr     ecx, 16h
0x14000b17a  and     ax, 7Fh
0x14000b17e  and     cx, r9w
0x14000b182  mov     [rdx], r10d
0x14000b185  shl     cx, 2
0x14000b189  add     cx, r9w
0x14000b18d  mov     [rdx+6], ax
0x14000b191  mov     [rdx+4], cx
0x14000b195  add     rdx, 8
0x14000b199  lea     rax, [rsp+68h+var_48]
0x14000b19e  sub     rdx, rax
0x14000b1a1  sar     rdx, 3
0x14000b1a5  test    rdx, rdx
0x14000b1a8  jle     short loc_14000B1B4
0x14000b1aa  lea     rcx, [rsp+68h+var_48]
0x14000b1af  call    wil_details_RecordFeatureUsageCallback
0x14000b1b4  mov     rcx, [rsp+68h+var_18]
0x14000b1b9  xor     rcx, rsp; StackCookie
0x14000b1bc  call    __security_check_cookie
0x14000b1c1  add     rsp, 68h
0x14000b1c5  retn
```
