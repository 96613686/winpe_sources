# wil_details_RecordCachedUsage

- ea: `0x180017010`
- end: `0x180017157`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014b20`

## callees

- `0x180016434`
- `0x180017010`
- `0x180018950`

## pseudocode

```c
void __fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  unsigned __int64 v9; // r8
  __int64 v10; // rdx
  _DWORD v11[2]; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h] BYREF

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
    v11[0] = a1;
    v11[1] = 65538;
    v8 = &v12;
  }
  else
  {
    v8 = (char *)v11;
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
  v9 = v3 >> 5;
  if ( (v9 & 0x1FF) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 14) & 1);
    LOWORD(v9) = v9 & 0x1FF;
    *((_WORD *)v8 + 3) = v9;
    v8 += 8;
  }
  if ( ((v3 >> 15) & 0x7F) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 22) & 1) + 1;
    *((_WORD *)v8 + 3) = (v3 >> 15) & 0x7F;
    v8 += 8;
  }
  v10 = (v8 - (char *)v11) >> 3;
  if ( v10 > 0 )
    wil::details::WilApi_RecordFeatureUsageReports((wil::details *)v11, (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10, v9);
}

```

## disassembly

```asm
0x180017010  sub     rsp, 68h
0x180017014  mov     rax, cs:__security_cookie
0x18001701b  xor     rax, rsp
0x18001701e  mov     [rsp+68h+var_18], rax
0x180017023  mov     r9, rdx
0x180017026  mov     r10d, ecx
0x180017029  prefetchw byte ptr [rdx]
0x18001702c  mov     eax, [rdx]
0x18001702e  mov     r8d, eax
0x180017031  and     r8d, 0FFC0401Eh
0x180017038  lock cmpxchg [rdx], r8d
0x18001703d  jnz     short loc_18001702E
0x18001703f  mov     ecx, eax
0x180017041  mov     r8d, eax
0x180017044  shr     r8d, 1
0x180017047  and     r8d, 0Fh
0x18001704b  jz      short loc_180017068
0x18001704d  prefetchw byte ptr [rdx+4]
0x180017051  mov     eax, [rdx+4]
0x180017054  mov     edx, eax
0x180017056  or      edx, r8d
0x180017059  lock cmpxchg [r9+4], edx
0x18001705f  jnz     short loc_180017054
0x180017061  not     eax
0x180017063  and     eax, r8d
0x180017066  jmp     short loc_18001706B
0x180017068  mov     eax, r8d
0x18001706b  mov     r8d, 2
0x180017071  lea     r9d, [r8-1]
0x180017075  test    r9b, al
0x180017078  jz      short loc_18001708E
0x18001707a  mov     [rsp+68h+var_48], r10d
0x18001707f  mov     [rsp+68h+var_44], 10002h
0x180017087  lea     rdx, [rsp+68h+var_40]
0x18001708c  jmp     short loc_180017093
0x18001708e  lea     rdx, [rsp+68h+var_48]
0x180017093  test    r8b, al
0x180017096  jz      short loc_1800170A6
0x180017098  mov     [rdx], r10d
0x18001709b  mov     dword ptr [rdx+4], 10006h
0x1800170a2  add     rdx, 8
0x1800170a6  test    al, 4
0x1800170a8  jz      short loc_1800170B8
0x1800170aa  mov     [rdx], r10d
0x1800170ad  mov     dword ptr [rdx+4], 10003h
0x1800170b4  add     rdx, 8
0x1800170b8  cmp     eax, 8
0x1800170bb  jb      short loc_1800170CB
0x1800170bd  mov     [rdx], r10d
0x1800170c0  mov     dword ptr [rdx+4], 10007h
0x1800170c7  add     rdx, 8
0x1800170cb  mov     r8d, ecx
0x1800170ce  shr     r8d, 5
0x1800170d2  mov     r11d, 1FFh
0x1800170d8  test    r11d, r8d
0x1800170db  jz      short loc_1800170FE
0x1800170dd  mov     [rdx], r10d
0x1800170e0  mov     eax, ecx
0x1800170e2  shr     eax, 0Eh
0x1800170e5  and     ax, r9w
0x1800170e9  shl     ax, 2
0x1800170ed  mov     [rdx+4], ax
0x1800170f1  and     r8w, r11w; unsigned __int64
0x1800170f5  mov     [rdx+6], r8w
0x1800170fa  add     rdx, 8
0x1800170fe  mov     eax, ecx
0x180017100  shr     eax, 0Fh
0x180017103  test    al, 7Fh
0x180017105  jz      short loc_180017129
0x180017107  mov     [rdx], r10d
0x18001710a  shr     ecx, 16h
0x18001710d  and     cx, r9w
0x180017111  shl     cx, 2
0x180017115  add     cx, r9w
0x180017119  mov     [rdx+4], cx
0x18001711d  and     ax, 7Fh
0x180017121  mov     [rdx+6], ax
0x180017125  add     rdx, 8
0x180017129  lea     rax, [rsp+68h+var_48]
0x18001712e  sub     rdx, rax
0x180017131  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180017135  test    rdx, rdx
0x180017138  jle     short loc_180017145
0x18001713a  lea     rcx, [rsp+68h+var_48]; this
0x18001713f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180017144  nop
0x180017145  mov     rcx, [rsp+68h+var_18]
0x18001714a  xor     rcx, rsp; StackCookie
0x18001714d  call    __security_check_cookie
0x180017152  add     rsp, 68h
0x180017156  retn
```
