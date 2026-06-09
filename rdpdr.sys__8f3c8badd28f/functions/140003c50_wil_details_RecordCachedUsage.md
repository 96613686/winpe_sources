# wil_details_RecordCachedUsage

- ea: `0x140003c50`
- end: `0x140003d97`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400187f0`

## callees

- `0x140003c50`
- `0x140006480`
- `0x140018844`

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
0x140003c50  sub     rsp, 68h
0x140003c54  mov     rax, cs:__security_cookie
0x140003c5b  xor     rax, rsp
0x140003c5e  mov     [rsp+68h+var_18], rax
0x140003c63  mov     r9, rdx
0x140003c66  mov     r10d, ecx
0x140003c69  prefetchw byte ptr [rdx]
0x140003c6c  mov     eax, [rdx]
0x140003c6e  mov     r8d, eax
0x140003c71  and     r8d, 0FFC0401Eh
0x140003c78  lock cmpxchg [rdx], r8d
0x140003c7d  jnz     short loc_140003C6E
0x140003c7f  mov     r8d, eax
0x140003c82  mov     ecx, eax
0x140003c84  shr     r8d, 1
0x140003c87  and     r8d, 0Fh
0x140003c8b  jz      short loc_140003CA8
0x140003c8d  prefetchw byte ptr [rdx+4]
0x140003c91  mov     eax, [rdx+4]
0x140003c94  mov     edx, eax
0x140003c96  or      edx, r8d
0x140003c99  lock cmpxchg [r9+4], edx
0x140003c9f  jnz     short loc_140003C94
0x140003ca1  not     eax
0x140003ca3  and     eax, r8d
0x140003ca6  jmp     short loc_140003CAB
0x140003ca8  mov     eax, r8d
0x140003cab  mov     r8d, 2
0x140003cb1  lea     r9d, [r8-1]
0x140003cb5  test    r9b, al
0x140003cb8  jz      short loc_140003CCE
0x140003cba  mov     [rsp+68h+var_48], r10d
0x140003cbf  lea     rdx, [rsp+68h+var_40]
0x140003cc4  mov     [rsp+68h+var_44], 10002h
0x140003ccc  jmp     short loc_140003CD3
0x140003cce  lea     rdx, [rsp+68h+var_48]
0x140003cd3  test    r8b, al
0x140003cd6  jz      short loc_140003CE6
0x140003cd8  mov     [rdx], r10d
0x140003cdb  mov     dword ptr [rdx+4], 10006h
0x140003ce2  add     rdx, 8
0x140003ce6  test    al, 4
0x140003ce8  jz      short loc_140003CF8
0x140003cea  mov     [rdx], r10d
0x140003ced  mov     dword ptr [rdx+4], 10003h
0x140003cf4  add     rdx, 8
0x140003cf8  cmp     eax, 8
0x140003cfb  jb      short loc_140003D0B
0x140003cfd  mov     [rdx], r10d
0x140003d00  mov     dword ptr [rdx+4], 10007h
0x140003d07  add     rdx, 8
0x140003d0b  mov     r8d, ecx
0x140003d0e  mov     r11d, 1FFh
0x140003d14  shr     r8d, 5
0x140003d18  test    r11d, r8d
0x140003d1b  jz      short loc_140003D3E
0x140003d1d  and     r8w, r11w
0x140003d21  mov     [rdx], r10d
0x140003d24  mov     eax, ecx
0x140003d26  mov     [rdx+6], r8w
0x140003d2b  shr     eax, 0Eh
0x140003d2e  and     ax, r9w
0x140003d32  shl     ax, 2
0x140003d36  mov     [rdx+4], ax
0x140003d3a  add     rdx, 8
0x140003d3e  mov     eax, ecx
0x140003d40  shr     eax, 0Fh
0x140003d43  test    al, 7Fh
0x140003d45  jz      short loc_140003D69
0x140003d47  shr     ecx, 16h
0x140003d4a  and     ax, 7Fh
0x140003d4e  and     cx, r9w
0x140003d52  mov     [rdx], r10d
0x140003d55  shl     cx, 2
0x140003d59  add     cx, r9w
0x140003d5d  mov     [rdx+6], ax
0x140003d61  mov     [rdx+4], cx
0x140003d65  add     rdx, 8
0x140003d69  lea     rax, [rsp+68h+var_48]
0x140003d6e  sub     rdx, rax
0x140003d71  sar     rdx, 3
0x140003d75  test    rdx, rdx
0x140003d78  jle     short loc_140003D84
0x140003d7a  lea     rcx, [rsp+68h+var_48]
0x140003d7f  call    wil_details_RecordFeatureUsageCallback
0x140003d84  mov     rcx, [rsp+68h+var_18]
0x140003d89  xor     rcx, rsp; StackCookie
0x140003d8c  call    __security_check_cookie
0x140003d91  add     rsp, 68h
0x140003d95  retn
```
