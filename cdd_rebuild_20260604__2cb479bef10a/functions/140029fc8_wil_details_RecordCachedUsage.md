# wil_details_RecordCachedUsage

- ea: `0x140029fc8`
- end: `0x14002a10f`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140043370`

## callees

- `0x140029fc8`
- `0x1400371f0`
- `0x1400433c4`

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
0x140029fc8  sub     rsp, 68h
0x140029fcc  mov     rax, cs:__security_cookie
0x140029fd3  xor     rax, rsp
0x140029fd6  mov     [rsp+68h+var_18], rax
0x140029fdb  mov     r9, rdx
0x140029fde  mov     r10d, ecx
0x140029fe1  prefetchw byte ptr [rdx]
0x140029fe4  mov     eax, [rdx]
0x140029fe6  mov     r8d, eax
0x140029fe9  and     r8d, 0FFC0401Eh
0x140029ff0  lock cmpxchg [rdx], r8d
0x140029ff5  jnz     short loc_140029FE6
0x140029ff7  mov     r8d, eax
0x140029ffa  mov     ecx, eax
0x140029ffc  shr     r8d, 1
0x140029fff  and     r8d, 0Fh
0x14002a003  jz      short loc_14002A020
0x14002a005  prefetchw byte ptr [rdx+4]
0x14002a009  mov     eax, [rdx+4]
0x14002a00c  mov     edx, eax
0x14002a00e  or      edx, r8d
0x14002a011  lock cmpxchg [r9+4], edx
0x14002a017  jnz     short loc_14002A00C
0x14002a019  not     eax
0x14002a01b  and     eax, r8d
0x14002a01e  jmp     short loc_14002A023
0x14002a020  mov     eax, r8d
0x14002a023  mov     r8d, 2
0x14002a029  lea     r9d, [r8-1]
0x14002a02d  test    r9b, al
0x14002a030  jz      short loc_14002A046
0x14002a032  mov     [rsp+68h+var_48], r10d
0x14002a037  lea     rdx, [rsp+68h+var_40]
0x14002a03c  mov     [rsp+68h+var_44], 10002h
0x14002a044  jmp     short loc_14002A04B
0x14002a046  lea     rdx, [rsp+68h+var_48]
0x14002a04b  test    r8b, al
0x14002a04e  jz      short loc_14002A05E
0x14002a050  mov     [rdx], r10d
0x14002a053  mov     dword ptr [rdx+4], 10006h
0x14002a05a  add     rdx, 8
0x14002a05e  test    al, 4
0x14002a060  jz      short loc_14002A070
0x14002a062  mov     [rdx], r10d
0x14002a065  mov     dword ptr [rdx+4], 10003h
0x14002a06c  add     rdx, 8
0x14002a070  cmp     eax, 8
0x14002a073  jb      short loc_14002A083
0x14002a075  mov     [rdx], r10d
0x14002a078  mov     dword ptr [rdx+4], 10007h
0x14002a07f  add     rdx, 8
0x14002a083  mov     r8d, ecx
0x14002a086  mov     r11d, 1FFh
0x14002a08c  shr     r8d, 5
0x14002a090  test    r11d, r8d
0x14002a093  jz      short loc_14002A0B6
0x14002a095  and     r8w, r11w
0x14002a099  mov     [rdx], r10d
0x14002a09c  mov     eax, ecx
0x14002a09e  mov     [rdx+6], r8w
0x14002a0a3  shr     eax, 0Eh
0x14002a0a6  and     ax, r9w
0x14002a0aa  shl     ax, 2
0x14002a0ae  mov     [rdx+4], ax
0x14002a0b2  add     rdx, 8
0x14002a0b6  mov     eax, ecx
0x14002a0b8  shr     eax, 0Fh
0x14002a0bb  test    al, 7Fh
0x14002a0bd  jz      short loc_14002A0E1
0x14002a0bf  shr     ecx, 16h
0x14002a0c2  and     ax, 7Fh
0x14002a0c6  and     cx, r9w
0x14002a0ca  mov     [rdx], r10d
0x14002a0cd  shl     cx, 2
0x14002a0d1  add     cx, r9w
0x14002a0d5  mov     [rdx+6], ax
0x14002a0d9  mov     [rdx+4], cx
0x14002a0dd  add     rdx, 8
0x14002a0e1  lea     rax, [rsp+68h+var_48]
0x14002a0e6  sub     rdx, rax
0x14002a0e9  sar     rdx, 3
0x14002a0ed  test    rdx, rdx
0x14002a0f0  jle     short loc_14002A0FC
0x14002a0f2  lea     rcx, [rsp+68h+var_48]
0x14002a0f7  call    wil_details_RecordFeatureUsageCallback
0x14002a0fc  mov     rcx, [rsp+68h+var_18]
0x14002a101  xor     rcx, rsp; StackCookie
0x14002a104  call    __security_check_cookie
0x14002a109  add     rsp, 68h
0x14002a10d  retn
```
