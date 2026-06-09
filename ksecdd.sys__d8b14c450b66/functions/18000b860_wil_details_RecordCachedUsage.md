# wil_details_RecordCachedUsage

- ea: `0x18000b860`
- end: `0x18000b9a7`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800215e0`

## callees

- `0x18000b860`
- `0x180010840`
- `0x180021634`

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
0x18000b860  sub     rsp, 68h
0x18000b864  mov     rax, cs:__security_cookie
0x18000b86b  xor     rax, rsp
0x18000b86e  mov     [rsp+68h+var_18], rax
0x18000b873  mov     r9, rdx
0x18000b876  mov     r10d, ecx
0x18000b879  prefetchw byte ptr [rdx]
0x18000b87c  mov     eax, [rdx]
0x18000b87e  mov     r8d, eax
0x18000b881  and     r8d, 0FFC0401Eh
0x18000b888  lock cmpxchg [rdx], r8d
0x18000b88d  jnz     short loc_18000B87E
0x18000b88f  mov     r8d, eax
0x18000b892  mov     ecx, eax
0x18000b894  shr     r8d, 1
0x18000b897  and     r8d, 0Fh
0x18000b89b  jz      short loc_18000B8B8
0x18000b89d  prefetchw byte ptr [rdx+4]
0x18000b8a1  mov     eax, [rdx+4]
0x18000b8a4  mov     edx, eax
0x18000b8a6  or      edx, r8d
0x18000b8a9  lock cmpxchg [r9+4], edx
0x18000b8af  jnz     short loc_18000B8A4
0x18000b8b1  not     eax
0x18000b8b3  and     eax, r8d
0x18000b8b6  jmp     short loc_18000B8BB
0x18000b8b8  mov     eax, r8d
0x18000b8bb  mov     r8d, 2
0x18000b8c1  lea     r9d, [r8-1]
0x18000b8c5  test    r9b, al
0x18000b8c8  jz      short loc_18000B8DE
0x18000b8ca  mov     [rsp+68h+var_48], r10d
0x18000b8cf  lea     rdx, [rsp+68h+var_40]
0x18000b8d4  mov     [rsp+68h+var_44], 10002h
0x18000b8dc  jmp     short loc_18000B8E3
0x18000b8de  lea     rdx, [rsp+68h+var_48]
0x18000b8e3  test    r8b, al
0x18000b8e6  jz      short loc_18000B8F6
0x18000b8e8  mov     [rdx], r10d
0x18000b8eb  mov     dword ptr [rdx+4], 10006h
0x18000b8f2  add     rdx, 8
0x18000b8f6  test    al, 4
0x18000b8f8  jz      short loc_18000B908
0x18000b8fa  mov     [rdx], r10d
0x18000b8fd  mov     dword ptr [rdx+4], 10003h
0x18000b904  add     rdx, 8
0x18000b908  cmp     eax, 8
0x18000b90b  jb      short loc_18000B91B
0x18000b90d  mov     [rdx], r10d
0x18000b910  mov     dword ptr [rdx+4], 10007h
0x18000b917  add     rdx, 8
0x18000b91b  mov     r8d, ecx
0x18000b91e  mov     r11d, 1FFh
0x18000b924  shr     r8d, 5
0x18000b928  test    r11d, r8d
0x18000b92b  jz      short loc_18000B94E
0x18000b92d  and     r8w, r11w
0x18000b931  mov     [rdx], r10d
0x18000b934  mov     eax, ecx
0x18000b936  mov     [rdx+6], r8w
0x18000b93b  shr     eax, 0Eh
0x18000b93e  and     ax, r9w
0x18000b942  shl     ax, 2
0x18000b946  mov     [rdx+4], ax
0x18000b94a  add     rdx, 8
0x18000b94e  mov     eax, ecx
0x18000b950  shr     eax, 0Fh
0x18000b953  test    al, 7Fh
0x18000b955  jz      short loc_18000B979
0x18000b957  shr     ecx, 16h
0x18000b95a  and     ax, 7Fh
0x18000b95e  and     cx, r9w
0x18000b962  mov     [rdx], r10d
0x18000b965  shl     cx, 2
0x18000b969  add     cx, r9w
0x18000b96d  mov     [rdx+6], ax
0x18000b971  mov     [rdx+4], cx
0x18000b975  add     rdx, 8
0x18000b979  lea     rax, [rsp+68h+var_48]
0x18000b97e  sub     rdx, rax
0x18000b981  sar     rdx, 3
0x18000b985  test    rdx, rdx
0x18000b988  jle     short loc_18000B994
0x18000b98a  lea     rcx, [rsp+68h+var_48]
0x18000b98f  call    wil_details_RecordFeatureUsageCallback
0x18000b994  mov     rcx, [rsp+68h+var_18]
0x18000b999  xor     rcx, rsp; StackCookie
0x18000b99c  call    __security_check_cookie
0x18000b9a1  add     rsp, 68h
0x18000b9a5  retn
```
