# wil_details_RecordCachedUsage

- ea: `0x1800237b0`
- end: `0x1800238f7`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fd30`

## callees

- `0x180013b20`
- `0x180022a64`
- `0x1800237b0`

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
0x1800237b0  sub     rsp, 68h
0x1800237b4  mov     rax, cs:__security_cookie
0x1800237bb  xor     rax, rsp
0x1800237be  mov     [rsp+68h+var_18], rax
0x1800237c3  mov     r9, rdx
0x1800237c6  mov     r10d, ecx
0x1800237c9  prefetchw byte ptr [rdx]
0x1800237cc  mov     eax, [rdx]
0x1800237ce  mov     r8d, eax
0x1800237d1  and     r8d, 0FFC0401Eh
0x1800237d8  lock cmpxchg [rdx], r8d
0x1800237dd  jnz     short loc_1800237CE
0x1800237df  mov     ecx, eax
0x1800237e1  mov     r8d, eax
0x1800237e4  shr     r8d, 1
0x1800237e7  and     r8d, 0Fh
0x1800237eb  jz      short loc_180023808
0x1800237ed  prefetchw byte ptr [rdx+4]
0x1800237f1  mov     eax, [rdx+4]
0x1800237f4  mov     edx, eax
0x1800237f6  or      edx, r8d
0x1800237f9  lock cmpxchg [r9+4], edx
0x1800237ff  jnz     short loc_1800237F4
0x180023801  not     eax
0x180023803  and     eax, r8d
0x180023806  jmp     short loc_18002380B
0x180023808  mov     eax, r8d
0x18002380b  mov     r8d, 2
0x180023811  lea     r9d, [r8-1]
0x180023815  test    r9b, al
0x180023818  jz      short loc_18002382E
0x18002381a  mov     [rsp+68h+var_48], r10d
0x18002381f  mov     [rsp+68h+var_44], 10002h
0x180023827  lea     rdx, [rsp+68h+var_40]
0x18002382c  jmp     short loc_180023833
0x18002382e  lea     rdx, [rsp+68h+var_48]
0x180023833  test    r8b, al
0x180023836  jz      short loc_180023846
0x180023838  mov     [rdx], r10d
0x18002383b  mov     dword ptr [rdx+4], 10006h
0x180023842  add     rdx, 8
0x180023846  test    al, 4
0x180023848  jz      short loc_180023858
0x18002384a  mov     [rdx], r10d
0x18002384d  mov     dword ptr [rdx+4], 10003h
0x180023854  add     rdx, 8
0x180023858  cmp     eax, 8
0x18002385b  jb      short loc_18002386B
0x18002385d  mov     [rdx], r10d
0x180023860  mov     dword ptr [rdx+4], 10007h
0x180023867  add     rdx, 8
0x18002386b  mov     r8d, ecx
0x18002386e  shr     r8d, 5
0x180023872  mov     r11d, 1FFh
0x180023878  test    r11d, r8d
0x18002387b  jz      short loc_18002389E
0x18002387d  mov     [rdx], r10d
0x180023880  mov     eax, ecx
0x180023882  shr     eax, 0Eh
0x180023885  and     ax, r9w
0x180023889  shl     ax, 2
0x18002388d  mov     [rdx+4], ax
0x180023891  and     r8w, r11w; unsigned __int64
0x180023895  mov     [rdx+6], r8w
0x18002389a  add     rdx, 8
0x18002389e  mov     eax, ecx
0x1800238a0  shr     eax, 0Fh
0x1800238a3  test    al, 7Fh
0x1800238a5  jz      short loc_1800238C9
0x1800238a7  mov     [rdx], r10d
0x1800238aa  shr     ecx, 16h
0x1800238ad  and     cx, r9w
0x1800238b1  shl     cx, 2
0x1800238b5  add     cx, r9w
0x1800238b9  mov     [rdx+4], cx
0x1800238bd  and     ax, 7Fh
0x1800238c1  mov     [rdx+6], ax
0x1800238c5  add     rdx, 8
0x1800238c9  lea     rax, [rsp+68h+var_48]
0x1800238ce  sub     rdx, rax
0x1800238d1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800238d5  test    rdx, rdx
0x1800238d8  jle     short loc_1800238E5
0x1800238da  lea     rcx, [rsp+68h+var_48]; this
0x1800238df  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1800238e4  nop
0x1800238e5  mov     rcx, [rsp+68h+var_18]
0x1800238ea  xor     rcx, rsp; StackCookie
0x1800238ed  call    __security_check_cookie
0x1800238f2  add     rsp, 68h
0x1800238f6  retn
```
