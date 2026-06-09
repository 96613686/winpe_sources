# wil_details_RecordCachedUsage

- ea: `0x1800166d8`
- end: `0x18001681e`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800132bc`

## callees

- `0x180014df8`
- `0x1800166d8`
- `0x18001ed20`

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
0x1800166d8  sub     rsp, 68h
0x1800166dc  mov     rax, cs:__security_cookie
0x1800166e3  xor     rax, rsp
0x1800166e6  mov     [rsp+68h+var_18], rax
0x1800166eb  mov     r9, rdx
0x1800166ee  mov     r10d, ecx
0x1800166f1  prefetchw byte ptr [rdx]
0x1800166f4  mov     eax, [rdx]
0x1800166f6  mov     r8d, eax
0x1800166f9  and     r8d, 0FFC0401Eh
0x180016700  lock cmpxchg [rdx], r8d
0x180016705  jnz     short loc_1800166F6
0x180016707  mov     r8d, eax
0x18001670a  mov     ecx, eax
0x18001670c  shr     r8d, 1
0x18001670f  and     r8d, 0Fh
0x180016713  jz      short loc_180016730
0x180016715  prefetchw byte ptr [rdx+4]
0x180016719  mov     eax, [rdx+4]
0x18001671c  mov     edx, eax
0x18001671e  or      edx, r8d
0x180016721  lock cmpxchg [r9+4], edx
0x180016727  jnz     short loc_18001671C
0x180016729  not     eax
0x18001672b  and     eax, r8d
0x18001672e  jmp     short loc_180016733
0x180016730  mov     eax, r8d
0x180016733  mov     r8d, 2
0x180016739  lea     r9d, [r8-1]
0x18001673d  test    r9b, al
0x180016740  jz      short loc_180016756
0x180016742  mov     [rsp+68h+var_48], r10d
0x180016747  lea     rdx, [rsp+68h+var_40]
0x18001674c  mov     [rsp+68h+var_44], 10002h
0x180016754  jmp     short loc_18001675B
0x180016756  lea     rdx, [rsp+68h+var_48]
0x18001675b  test    r8b, al
0x18001675e  jz      short loc_18001676E
0x180016760  mov     [rdx], r10d
0x180016763  mov     dword ptr [rdx+4], 10006h
0x18001676a  add     rdx, 8
0x18001676e  test    al, 4
0x180016770  jz      short loc_180016780
0x180016772  mov     [rdx], r10d
0x180016775  mov     dword ptr [rdx+4], 10003h
0x18001677c  add     rdx, 8
0x180016780  cmp     eax, 8
0x180016783  jb      short loc_180016793
0x180016785  mov     [rdx], r10d
0x180016788  mov     dword ptr [rdx+4], 10007h
0x18001678f  add     rdx, 8
0x180016793  mov     r8d, ecx
0x180016796  mov     r11d, 1FFh
0x18001679c  shr     r8d, 5
0x1800167a0  test    r11d, r8d
0x1800167a3  jz      short loc_1800167C6
0x1800167a5  and     r8w, r11w; unsigned __int64
0x1800167a9  mov     [rdx], r10d
0x1800167ac  mov     eax, ecx
0x1800167ae  mov     [rdx+6], r8w
0x1800167b3  shr     eax, 0Eh
0x1800167b6  and     ax, r9w
0x1800167ba  shl     ax, 2
0x1800167be  mov     [rdx+4], ax
0x1800167c2  add     rdx, 8
0x1800167c6  mov     eax, ecx
0x1800167c8  shr     eax, 0Fh
0x1800167cb  test    al, 7Fh
0x1800167cd  jz      short loc_1800167F1
0x1800167cf  shr     ecx, 16h
0x1800167d2  and     ax, 7Fh
0x1800167d6  and     cx, r9w
0x1800167da  mov     [rdx], r10d
0x1800167dd  shl     cx, 2
0x1800167e1  add     cx, r9w
0x1800167e5  mov     [rdx+6], ax
0x1800167e9  mov     [rdx+4], cx
0x1800167ed  add     rdx, 8
0x1800167f1  lea     rax, [rsp+68h+var_48]
0x1800167f6  sub     rdx, rax
0x1800167f9  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800167fd  test    rdx, rdx
0x180016800  jle     short loc_18001680C
0x180016802  lea     rcx, [rsp+68h+var_48]; this
0x180016807  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18001680c  mov     rcx, [rsp+68h+var_18]
0x180016811  xor     rcx, rsp; StackCookie
0x180016814  call    __security_check_cookie
0x180016819  add     rsp, 68h
0x18001681d  retn
```
