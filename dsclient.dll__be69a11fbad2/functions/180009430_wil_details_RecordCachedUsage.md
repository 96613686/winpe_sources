# wil_details_RecordCachedUsage

- ea: `0x180009430`
- end: `0x180009576`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: `void __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006f10`

## callees

- `0x1800087b4`
- `0x180009430`
- `0x180009950`

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
0x180009430  sub     rsp, 68h
0x180009434  mov     rax, cs:__security_cookie
0x18000943b  xor     rax, rsp
0x18000943e  mov     [rsp+68h+var_18], rax
0x180009443  mov     r9, rdx
0x180009446  mov     r10d, ecx
0x180009449  prefetchw byte ptr [rdx]
0x18000944c  mov     eax, [rdx]
0x18000944e  mov     r8d, eax
0x180009451  and     r8d, 0FFC0401Eh
0x180009458  lock cmpxchg [rdx], r8d
0x18000945d  jnz     short loc_18000944E
0x18000945f  mov     r8d, eax
0x180009462  mov     ecx, eax
0x180009464  shr     r8d, 1
0x180009467  and     r8d, 0Fh
0x18000946b  jz      short loc_180009488
0x18000946d  prefetchw byte ptr [rdx+4]
0x180009471  mov     eax, [rdx+4]
0x180009474  mov     edx, eax
0x180009476  or      edx, r8d
0x180009479  lock cmpxchg [r9+4], edx
0x18000947f  jnz     short loc_180009474
0x180009481  not     eax
0x180009483  and     eax, r8d
0x180009486  jmp     short loc_18000948B
0x180009488  mov     eax, r8d
0x18000948b  mov     r8d, 2
0x180009491  lea     r9d, [r8-1]
0x180009495  test    r9b, al
0x180009498  jz      short loc_1800094AE
0x18000949a  mov     [rsp+68h+var_48], r10d
0x18000949f  lea     rdx, [rsp+68h+var_40]
0x1800094a4  mov     [rsp+68h+var_44], 10002h
0x1800094ac  jmp     short loc_1800094B3
0x1800094ae  lea     rdx, [rsp+68h+var_48]
0x1800094b3  test    r8b, al
0x1800094b6  jz      short loc_1800094C6
0x1800094b8  mov     [rdx], r10d
0x1800094bb  mov     dword ptr [rdx+4], 10006h
0x1800094c2  add     rdx, 8
0x1800094c6  test    al, 4
0x1800094c8  jz      short loc_1800094D8
0x1800094ca  mov     [rdx], r10d
0x1800094cd  mov     dword ptr [rdx+4], 10003h
0x1800094d4  add     rdx, 8
0x1800094d8  cmp     eax, 8
0x1800094db  jb      short loc_1800094EB
0x1800094dd  mov     [rdx], r10d
0x1800094e0  mov     dword ptr [rdx+4], 10007h
0x1800094e7  add     rdx, 8
0x1800094eb  mov     r8d, ecx
0x1800094ee  mov     r11d, 1FFh
0x1800094f4  shr     r8d, 5
0x1800094f8  test    r11d, r8d
0x1800094fb  jz      short loc_18000951E
0x1800094fd  and     r8w, r11w; unsigned __int64
0x180009501  mov     [rdx], r10d
0x180009504  mov     eax, ecx
0x180009506  mov     [rdx+6], r8w
0x18000950b  shr     eax, 0Eh
0x18000950e  and     ax, r9w
0x180009512  shl     ax, 2
0x180009516  mov     [rdx+4], ax
0x18000951a  add     rdx, 8
0x18000951e  mov     eax, ecx
0x180009520  shr     eax, 0Fh
0x180009523  test    al, 7Fh
0x180009525  jz      short loc_180009549
0x180009527  shr     ecx, 16h
0x18000952a  and     ax, 7Fh
0x18000952e  and     cx, r9w
0x180009532  mov     [rdx], r10d
0x180009535  shl     cx, 2
0x180009539  add     cx, r9w
0x18000953d  mov     [rdx+6], ax
0x180009541  mov     [rdx+4], cx
0x180009545  add     rdx, 8
0x180009549  lea     rax, [rsp+68h+var_48]
0x18000954e  sub     rdx, rax
0x180009551  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180009555  test    rdx, rdx
0x180009558  jle     short loc_180009564
0x18000955a  lea     rcx, [rsp+68h+var_48]; this
0x18000955f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180009564  mov     rcx, [rsp+68h+var_18]
0x180009569  xor     rcx, rsp; StackCookie
0x18000956c  call    __security_check_cookie
0x180009571  add     rsp, 68h
0x180009575  retn
```
