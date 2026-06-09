# wil_details_RecordCachedUsage

- ea: `0x180016100`
- end: `0x180016247`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014b54`

## callees

- `0x18000fa10`
- `0x180015850`
- `0x180016100`

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
0x180016100  sub     rsp, 68h
0x180016104  mov     rax, cs:__security_cookie
0x18001610b  xor     rax, rsp
0x18001610e  mov     [rsp+68h+var_18], rax
0x180016113  mov     r9, rdx
0x180016116  mov     r10d, ecx
0x180016119  prefetchw byte ptr [rdx]
0x18001611c  mov     eax, [rdx]
0x18001611e  mov     r8d, eax
0x180016121  and     r8d, 0FFC0401Eh
0x180016128  lock cmpxchg [rdx], r8d
0x18001612d  jnz     short loc_18001611E
0x18001612f  mov     ecx, eax
0x180016131  mov     r8d, eax
0x180016134  shr     r8d, 1
0x180016137  and     r8d, 0Fh
0x18001613b  jz      short loc_180016158
0x18001613d  prefetchw byte ptr [rdx+4]
0x180016141  mov     eax, [rdx+4]
0x180016144  mov     edx, eax
0x180016146  or      edx, r8d
0x180016149  lock cmpxchg [r9+4], edx
0x18001614f  jnz     short loc_180016144
0x180016151  not     eax
0x180016153  and     eax, r8d
0x180016156  jmp     short loc_18001615B
0x180016158  mov     eax, r8d
0x18001615b  mov     r8d, 2
0x180016161  lea     r9d, [r8-1]
0x180016165  test    r9b, al
0x180016168  jz      short loc_18001617E
0x18001616a  mov     [rsp+68h+var_48], r10d
0x18001616f  mov     [rsp+68h+var_44], 10002h
0x180016177  lea     rdx, [rsp+68h+var_40]
0x18001617c  jmp     short loc_180016183
0x18001617e  lea     rdx, [rsp+68h+var_48]
0x180016183  test    r8b, al
0x180016186  jz      short loc_180016196
0x180016188  mov     [rdx], r10d
0x18001618b  mov     dword ptr [rdx+4], 10006h
0x180016192  add     rdx, 8
0x180016196  test    al, 4
0x180016198  jz      short loc_1800161A8
0x18001619a  mov     [rdx], r10d
0x18001619d  mov     dword ptr [rdx+4], 10003h
0x1800161a4  add     rdx, 8
0x1800161a8  cmp     eax, 8
0x1800161ab  jb      short loc_1800161BB
0x1800161ad  mov     [rdx], r10d
0x1800161b0  mov     dword ptr [rdx+4], 10007h
0x1800161b7  add     rdx, 8
0x1800161bb  mov     r8d, ecx
0x1800161be  shr     r8d, 5
0x1800161c2  mov     r11d, 1FFh
0x1800161c8  test    r11d, r8d
0x1800161cb  jz      short loc_1800161EE
0x1800161cd  mov     [rdx], r10d
0x1800161d0  mov     eax, ecx
0x1800161d2  shr     eax, 0Eh
0x1800161d5  and     ax, r9w
0x1800161d9  shl     ax, 2
0x1800161dd  mov     [rdx+4], ax
0x1800161e1  and     r8w, r11w; unsigned __int64
0x1800161e5  mov     [rdx+6], r8w
0x1800161ea  add     rdx, 8
0x1800161ee  mov     eax, ecx
0x1800161f0  shr     eax, 0Fh
0x1800161f3  test    al, 7Fh
0x1800161f5  jz      short loc_180016219
0x1800161f7  mov     [rdx], r10d
0x1800161fa  shr     ecx, 16h
0x1800161fd  and     cx, r9w
0x180016201  shl     cx, 2
0x180016205  add     cx, r9w
0x180016209  mov     [rdx+4], cx
0x18001620d  and     ax, 7Fh
0x180016211  mov     [rdx+6], ax
0x180016215  add     rdx, 8
0x180016219  lea     rax, [rsp+68h+var_48]
0x18001621e  sub     rdx, rax
0x180016221  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180016225  test    rdx, rdx
0x180016228  jle     short loc_180016235
0x18001622a  lea     rcx, [rsp+68h+var_48]; this
0x18001622f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180016234  nop
0x180016235  mov     rcx, [rsp+68h+var_18]
0x18001623a  xor     rcx, rsp; StackCookie
0x18001623d  call    __security_check_cookie
0x180016242  add     rsp, 68h
0x180016246  retn
```
