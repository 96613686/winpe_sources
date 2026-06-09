# wil_details_RecordCachedUsage

- ea: `0x14000b3d0`
- end: `0x14000b517`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `void __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008a14`

## callees

- `0x1400029a0`
- `0x140009cb8`
- `0x14000b3d0`

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
0x14000b3d0  sub     rsp, 68h
0x14000b3d4  mov     rax, cs:__security_cookie
0x14000b3db  xor     rax, rsp
0x14000b3de  mov     [rsp+68h+var_18], rax
0x14000b3e3  mov     r9, rdx
0x14000b3e6  mov     r10d, ecx
0x14000b3e9  prefetchw byte ptr [rdx]
0x14000b3ec  mov     eax, [rdx]
0x14000b3ee  mov     r8d, eax
0x14000b3f1  and     r8d, 0FFC0401Eh
0x14000b3f8  lock cmpxchg [rdx], r8d
0x14000b3fd  jnz     short loc_14000B3EE
0x14000b3ff  mov     ecx, eax
0x14000b401  mov     r8d, eax
0x14000b404  shr     r8d, 1
0x14000b407  and     r8d, 0Fh
0x14000b40b  jz      short loc_14000B428
0x14000b40d  prefetchw byte ptr [rdx+4]
0x14000b411  mov     eax, [rdx+4]
0x14000b414  mov     edx, eax
0x14000b416  or      edx, r8d
0x14000b419  lock cmpxchg [r9+4], edx
0x14000b41f  jnz     short loc_14000B414
0x14000b421  not     eax
0x14000b423  and     eax, r8d
0x14000b426  jmp     short loc_14000B42B
0x14000b428  mov     eax, r8d
0x14000b42b  mov     r8d, 2
0x14000b431  lea     r9d, [r8-1]
0x14000b435  test    r9b, al
0x14000b438  jz      short loc_14000B44E
0x14000b43a  mov     [rsp+68h+var_48], r10d
0x14000b43f  mov     [rsp+68h+var_44], 10002h
0x14000b447  lea     rdx, [rsp+68h+var_40]
0x14000b44c  jmp     short loc_14000B453
0x14000b44e  lea     rdx, [rsp+68h+var_48]
0x14000b453  test    r8b, al
0x14000b456  jz      short loc_14000B466
0x14000b458  mov     [rdx], r10d
0x14000b45b  mov     dword ptr [rdx+4], 10006h
0x14000b462  add     rdx, 8
0x14000b466  test    al, 4
0x14000b468  jz      short loc_14000B478
0x14000b46a  mov     [rdx], r10d
0x14000b46d  mov     dword ptr [rdx+4], 10003h
0x14000b474  add     rdx, 8
0x14000b478  cmp     eax, 8
0x14000b47b  jb      short loc_14000B48B
0x14000b47d  mov     [rdx], r10d
0x14000b480  mov     dword ptr [rdx+4], 10007h
0x14000b487  add     rdx, 8
0x14000b48b  mov     r8d, ecx
0x14000b48e  shr     r8d, 5
0x14000b492  mov     r11d, 1FFh
0x14000b498  test    r11d, r8d
0x14000b49b  jz      short loc_14000B4BE
0x14000b49d  mov     [rdx], r10d
0x14000b4a0  mov     eax, ecx
0x14000b4a2  shr     eax, 0Eh
0x14000b4a5  and     ax, r9w
0x14000b4a9  shl     ax, 2
0x14000b4ad  mov     [rdx+4], ax
0x14000b4b1  and     r8w, r11w; unsigned __int64
0x14000b4b5  mov     [rdx+6], r8w
0x14000b4ba  add     rdx, 8
0x14000b4be  mov     eax, ecx
0x14000b4c0  shr     eax, 0Fh
0x14000b4c3  test    al, 7Fh
0x14000b4c5  jz      short loc_14000B4E9
0x14000b4c7  mov     [rdx], r10d
0x14000b4ca  shr     ecx, 16h
0x14000b4cd  and     cx, r9w
0x14000b4d1  shl     cx, 2
0x14000b4d5  add     cx, r9w
0x14000b4d9  mov     [rdx+4], cx
0x14000b4dd  and     ax, 7Fh
0x14000b4e1  mov     [rdx+6], ax
0x14000b4e5  add     rdx, 8
0x14000b4e9  lea     rax, [rsp+68h+var_48]
0x14000b4ee  sub     rdx, rax
0x14000b4f1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x14000b4f5  test    rdx, rdx
0x14000b4f8  jle     short loc_14000B505
0x14000b4fa  lea     rcx, [rsp+68h+var_48]; this
0x14000b4ff  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x14000b504  nop
0x14000b505  mov     rcx, [rsp+68h+var_18]
0x14000b50a  xor     rcx, rsp; StackCookie
0x14000b50d  call    __security_check_cookie
0x14000b512  add     rsp, 68h
0x14000b516  retn
```
