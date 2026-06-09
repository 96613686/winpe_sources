# wil_details_RecordCachedUsage

- ea: `0x1400031d8`
- end: `0x140003326`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: `_DWORD *__fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140016b50`

## callees

- `0x1400031d8`
- `0x140005f30`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003307`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003307`

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
0x1400031d8  sub     rsp, 68h
0x1400031dc  mov     rax, cs:__security_cookie
0x1400031e3  xor     rax, rsp
0x1400031e6  mov     [rsp+68h+var_18], rax
0x1400031eb  mov     r9, rdx
0x1400031ee  mov     r10d, ecx
0x1400031f1  prefetchw byte ptr [rdx]
0x1400031f4  mov     eax, [rdx]
0x1400031f6  mov     r8d, eax
0x1400031f9  and     r8d, 0FFC0401Eh
0x140003200  lock cmpxchg [rdx], r8d
0x140003205  jnz     short loc_1400031F6
0x140003207  mov     r8d, eax
0x14000320a  mov     ecx, eax
0x14000320c  shr     r8d, 1
0x14000320f  and     r8d, 0Fh
0x140003213  jz      short loc_140003230
0x140003215  prefetchw byte ptr [rdx+4]
0x140003219  mov     eax, [rdx+4]
0x14000321c  mov     edx, eax
0x14000321e  or      edx, r8d
0x140003221  lock cmpxchg [r9+4], edx
0x140003227  jnz     short loc_14000321C
0x140003229  not     eax
0x14000322b  and     eax, r8d
0x14000322e  jmp     short loc_140003233
0x140003230  mov     eax, r8d
0x140003233  mov     r8d, 2
0x140003239  lea     r9d, [r8-1]
0x14000323d  test    r9b, al
0x140003240  jz      short loc_140003256
0x140003242  mov     [rsp+68h+var_48], r10d
0x140003247  lea     rdx, [rsp+68h+var_40]
0x14000324c  mov     [rsp+68h+var_44], 10002h
0x140003254  jmp     short loc_14000325B
0x140003256  lea     rdx, [rsp+68h+var_48]
0x14000325b  test    r8b, al
0x14000325e  jz      short loc_14000326E
0x140003260  mov     [rdx], r10d
0x140003263  mov     dword ptr [rdx+4], 10006h
0x14000326a  add     rdx, 8
0x14000326e  test    al, 4
0x140003270  jz      short loc_140003280
0x140003272  mov     [rdx], r10d
0x140003275  mov     dword ptr [rdx+4], 10003h
0x14000327c  add     rdx, 8
0x140003280  cmp     eax, 8
0x140003283  jb      short loc_140003293
0x140003285  mov     [rdx], r10d
0x140003288  mov     dword ptr [rdx+4], 10007h
0x14000328f  add     rdx, 8
0x140003293  mov     r8d, ecx
0x140003296  mov     r11d, 1FFh
0x14000329c  shr     r8d, 5
0x1400032a0  test    r11d, r8d
0x1400032a3  jz      short loc_1400032C6
0x1400032a5  and     r8w, r11w
0x1400032a9  mov     [rdx], r10d
0x1400032ac  mov     eax, ecx
0x1400032ae  mov     [rdx+6], r8w
0x1400032b3  shr     eax, 0Eh
0x1400032b6  and     ax, r9w
0x1400032ba  shl     ax, 2
0x1400032be  mov     [rdx+4], ax
0x1400032c2  add     rdx, 8
0x1400032c6  mov     eax, ecx
0x1400032c8  shr     eax, 0Fh
0x1400032cb  test    al, 7Fh
0x1400032cd  jz      short loc_1400032F1
0x1400032cf  shr     ecx, 16h
0x1400032d2  and     ax, 7Fh
0x1400032d6  and     cx, r9w
0x1400032da  mov     [rdx], r10d
0x1400032dd  shl     cx, 2
0x1400032e1  add     cx, r9w
0x1400032e5  mov     [rdx+6], ax
0x1400032e9  mov     [rdx+4], cx
0x1400032ed  add     rdx, 8
0x1400032f1  lea     rax, [rsp+68h+var_48]
0x1400032f6  sub     rdx, rax
0x1400032f9  sar     rdx, 3
0x1400032fd  test    rdx, rdx
0x140003300  jle     short loc_140003313
0x140003302  lea     rcx, [rsp+68h+var_48]
0x140003307  call    cs:__imp_RtlRecordFeatureUsage
0x14000330e  nop     dword ptr [rax+rax+00h]
0x140003313  mov     rcx, [rsp+68h+var_18]
0x140003318  xor     rcx, rsp; StackCookie
0x14000331b  call    __security_check_cookie
0x140003320  add     rsp, 68h
0x140003324  retn
```
