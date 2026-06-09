# wil_details_RecordCachedUsage

- ea: `0x180016320`
- end: `0x180016466`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014304`

## callees

- `0x18000e2f0`
- `0x180015474`
- `0x180016320`

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
    v8 = &v12;
    v11[1] = 65538;
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
    LOWORD(v9) = v9 & 0x1FF;
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = v9;
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
  v10 = (v8 - (char *)v11) >> 3;
  if ( v10 > 0 )
    wil::details::WilApi_RecordFeatureUsageReports((wil::details *)v11, (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10, v9);
}

```

## disassembly

```asm
0x180016320  sub     rsp, 68h
0x180016324  mov     rax, cs:__security_cookie
0x18001632b  xor     rax, rsp
0x18001632e  mov     [rsp+68h+var_18], rax
0x180016333  mov     r9, rdx
0x180016336  mov     r10d, ecx
0x180016339  prefetchw byte ptr [rdx]
0x18001633c  mov     eax, [rdx]
0x18001633e  mov     r8d, eax
0x180016341  and     r8d, 0FFC0401Eh
0x180016348  lock cmpxchg [rdx], r8d
0x18001634d  jnz     short loc_18001633E
0x18001634f  mov     r8d, eax
0x180016352  mov     ecx, eax
0x180016354  shr     r8d, 1
0x180016357  and     r8d, 0Fh
0x18001635b  jz      short loc_180016378
0x18001635d  prefetchw byte ptr [rdx+4]
0x180016361  mov     eax, [rdx+4]
0x180016364  mov     edx, eax
0x180016366  or      edx, r8d
0x180016369  lock cmpxchg [r9+4], edx
0x18001636f  jnz     short loc_180016364
0x180016371  not     eax
0x180016373  and     eax, r8d
0x180016376  jmp     short loc_18001637B
0x180016378  mov     eax, r8d
0x18001637b  mov     r8d, 2
0x180016381  lea     r9d, [r8-1]
0x180016385  test    r9b, al
0x180016388  jz      short loc_18001639E
0x18001638a  mov     [rsp+68h+var_48], r10d
0x18001638f  lea     rdx, [rsp+68h+var_40]
0x180016394  mov     [rsp+68h+var_44], 10002h
0x18001639c  jmp     short loc_1800163A3
0x18001639e  lea     rdx, [rsp+68h+var_48]
0x1800163a3  test    r8b, al
0x1800163a6  jz      short loc_1800163B6
0x1800163a8  mov     [rdx], r10d
0x1800163ab  mov     dword ptr [rdx+4], 10006h
0x1800163b2  add     rdx, 8
0x1800163b6  test    al, 4
0x1800163b8  jz      short loc_1800163C8
0x1800163ba  mov     [rdx], r10d
0x1800163bd  mov     dword ptr [rdx+4], 10003h
0x1800163c4  add     rdx, 8
0x1800163c8  cmp     eax, 8
0x1800163cb  jb      short loc_1800163DB
0x1800163cd  mov     [rdx], r10d
0x1800163d0  mov     dword ptr [rdx+4], 10007h
0x1800163d7  add     rdx, 8
0x1800163db  mov     r8d, ecx
0x1800163de  mov     r11d, 1FFh
0x1800163e4  shr     r8d, 5
0x1800163e8  test    r11d, r8d
0x1800163eb  jz      short loc_18001640E
0x1800163ed  and     r8w, r11w; unsigned __int64
0x1800163f1  mov     [rdx], r10d
0x1800163f4  mov     eax, ecx
0x1800163f6  mov     [rdx+6], r8w
0x1800163fb  shr     eax, 0Eh
0x1800163fe  and     ax, r9w
0x180016402  shl     ax, 2
0x180016406  mov     [rdx+4], ax
0x18001640a  add     rdx, 8
0x18001640e  mov     eax, ecx
0x180016410  shr     eax, 0Fh
0x180016413  test    al, 7Fh
0x180016415  jz      short loc_180016439
0x180016417  shr     ecx, 16h
0x18001641a  and     ax, 7Fh
0x18001641e  and     cx, r9w
0x180016422  mov     [rdx], r10d
0x180016425  shl     cx, 2
0x180016429  add     cx, r9w
0x18001642d  mov     [rdx+6], ax
0x180016431  mov     [rdx+4], cx
0x180016435  add     rdx, 8
0x180016439  lea     rax, [rsp+68h+var_48]
0x18001643e  sub     rdx, rax
0x180016441  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180016445  test    rdx, rdx
0x180016448  jle     short loc_180016454
0x18001644a  lea     rcx, [rsp+68h+var_48]; this
0x18001644f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180016454  mov     rcx, [rsp+68h+var_18]
0x180016459  xor     rcx, rsp; StackCookie
0x18001645c  call    __security_check_cookie
0x180016461  add     rsp, 68h
0x180016465  retn
```
