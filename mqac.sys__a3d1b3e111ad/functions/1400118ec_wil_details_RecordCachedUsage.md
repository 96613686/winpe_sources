# wil_details_RecordCachedUsage

- ea: `0x1400118ec`
- end: `0x140011a33`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002f7e0`

## callees

- `0x1400118ec`
- `0x140024bb0`
- `0x14002f834`

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
0x1400118ec  sub     rsp, 68h
0x1400118f0  mov     rax, cs:__security_cookie
0x1400118f7  xor     rax, rsp
0x1400118fa  mov     [rsp+68h+var_18], rax
0x1400118ff  mov     r9, rdx
0x140011902  mov     r10d, ecx
0x140011905  prefetchw byte ptr [rdx]
0x140011908  mov     eax, [rdx]
0x14001190a  mov     r8d, eax
0x14001190d  and     r8d, 0FFC0401Eh
0x140011914  lock cmpxchg [rdx], r8d
0x140011919  jnz     short loc_14001190A
0x14001191b  mov     r8d, eax
0x14001191e  mov     ecx, eax
0x140011920  shr     r8d, 1
0x140011923  and     r8d, 0Fh
0x140011927  jz      short loc_140011944
0x140011929  prefetchw byte ptr [rdx+4]
0x14001192d  mov     eax, [rdx+4]
0x140011930  mov     edx, eax
0x140011932  or      edx, r8d
0x140011935  lock cmpxchg [r9+4], edx
0x14001193b  jnz     short loc_140011930
0x14001193d  not     eax
0x14001193f  and     eax, r8d
0x140011942  jmp     short loc_140011947
0x140011944  mov     eax, r8d
0x140011947  mov     r8d, 2
0x14001194d  lea     r9d, [r8-1]
0x140011951  test    r9b, al
0x140011954  jz      short loc_14001196A
0x140011956  mov     [rsp+68h+var_48], r10d
0x14001195b  lea     rdx, [rsp+68h+var_40]
0x140011960  mov     [rsp+68h+var_44], 10002h
0x140011968  jmp     short loc_14001196F
0x14001196a  lea     rdx, [rsp+68h+var_48]
0x14001196f  test    r8b, al
0x140011972  jz      short loc_140011982
0x140011974  mov     [rdx], r10d
0x140011977  mov     dword ptr [rdx+4], 10006h
0x14001197e  add     rdx, 8
0x140011982  test    al, 4
0x140011984  jz      short loc_140011994
0x140011986  mov     [rdx], r10d
0x140011989  mov     dword ptr [rdx+4], 10003h
0x140011990  add     rdx, 8
0x140011994  cmp     eax, 8
0x140011997  jb      short loc_1400119A7
0x140011999  mov     [rdx], r10d
0x14001199c  mov     dword ptr [rdx+4], 10007h
0x1400119a3  add     rdx, 8
0x1400119a7  mov     r8d, ecx
0x1400119aa  mov     r11d, 1FFh
0x1400119b0  shr     r8d, 5
0x1400119b4  test    r11d, r8d
0x1400119b7  jz      short loc_1400119DA
0x1400119b9  and     r8w, r11w
0x1400119bd  mov     [rdx], r10d
0x1400119c0  mov     eax, ecx
0x1400119c2  mov     [rdx+6], r8w
0x1400119c7  shr     eax, 0Eh
0x1400119ca  and     ax, r9w
0x1400119ce  shl     ax, 2
0x1400119d2  mov     [rdx+4], ax
0x1400119d6  add     rdx, 8
0x1400119da  mov     eax, ecx
0x1400119dc  shr     eax, 0Fh
0x1400119df  test    al, 7Fh
0x1400119e1  jz      short loc_140011A05
0x1400119e3  shr     ecx, 16h
0x1400119e6  and     ax, 7Fh
0x1400119ea  and     cx, r9w
0x1400119ee  mov     [rdx], r10d
0x1400119f1  shl     cx, 2
0x1400119f5  add     cx, r9w
0x1400119f9  mov     [rdx+6], ax
0x1400119fd  mov     [rdx+4], cx
0x140011a01  add     rdx, 8
0x140011a05  lea     rax, [rsp+68h+var_48]
0x140011a0a  sub     rdx, rax
0x140011a0d  sar     rdx, 3
0x140011a11  test    rdx, rdx
0x140011a14  jle     short loc_140011A20
0x140011a16  lea     rcx, [rsp+68h+var_48]
0x140011a1b  call    wil_details_RecordFeatureUsageCallback
0x140011a20  mov     rcx, [rsp+68h+var_18]
0x140011a25  xor     rcx, rsp; StackCookie
0x140011a28  call    __security_check_cookie
0x140011a2d  add     rsp, 68h
0x140011a31  retn
```
