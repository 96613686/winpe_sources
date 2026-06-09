# wil_details_RecordCachedUsage

- ea: `0x18000aaf0`
- end: `0x18000ac36`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007988`

## callees

- `0x180002620`
- `0x180009660`
- `0x18000aaf0`

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
0x18000aaf0  sub     rsp, 68h
0x18000aaf4  mov     rax, cs:__security_cookie
0x18000aafb  xor     rax, rsp
0x18000aafe  mov     [rsp+68h+var_18], rax
0x18000ab03  mov     r9, rdx
0x18000ab06  mov     r10d, ecx
0x18000ab09  prefetchw byte ptr [rdx]
0x18000ab0c  mov     eax, [rdx]
0x18000ab0e  mov     r8d, eax
0x18000ab11  and     r8d, 0FFC0401Eh
0x18000ab18  lock cmpxchg [rdx], r8d
0x18000ab1d  jnz     short loc_18000AB0E
0x18000ab1f  mov     r8d, eax
0x18000ab22  mov     ecx, eax
0x18000ab24  shr     r8d, 1
0x18000ab27  and     r8d, 0Fh
0x18000ab2b  jz      short loc_18000AB48
0x18000ab2d  prefetchw byte ptr [rdx+4]
0x18000ab31  mov     eax, [rdx+4]
0x18000ab34  mov     edx, eax
0x18000ab36  or      edx, r8d
0x18000ab39  lock cmpxchg [r9+4], edx
0x18000ab3f  jnz     short loc_18000AB34
0x18000ab41  not     eax
0x18000ab43  and     eax, r8d
0x18000ab46  jmp     short loc_18000AB4B
0x18000ab48  mov     eax, r8d
0x18000ab4b  mov     r8d, 2
0x18000ab51  lea     r9d, [r8-1]
0x18000ab55  test    r9b, al
0x18000ab58  jz      short loc_18000AB6E
0x18000ab5a  mov     [rsp+68h+var_48], r10d
0x18000ab5f  lea     rdx, [rsp+68h+var_40]
0x18000ab64  mov     [rsp+68h+var_44], 10002h
0x18000ab6c  jmp     short loc_18000AB73
0x18000ab6e  lea     rdx, [rsp+68h+var_48]
0x18000ab73  test    r8b, al
0x18000ab76  jz      short loc_18000AB86
0x18000ab78  mov     [rdx], r10d
0x18000ab7b  mov     dword ptr [rdx+4], 10006h
0x18000ab82  add     rdx, 8
0x18000ab86  test    al, 4
0x18000ab88  jz      short loc_18000AB98
0x18000ab8a  mov     [rdx], r10d
0x18000ab8d  mov     dword ptr [rdx+4], 10003h
0x18000ab94  add     rdx, 8
0x18000ab98  cmp     eax, 8
0x18000ab9b  jb      short loc_18000ABAB
0x18000ab9d  mov     [rdx], r10d
0x18000aba0  mov     dword ptr [rdx+4], 10007h
0x18000aba7  add     rdx, 8
0x18000abab  mov     r8d, ecx
0x18000abae  mov     r11d, 1FFh
0x18000abb4  shr     r8d, 5
0x18000abb8  test    r11d, r8d
0x18000abbb  jz      short loc_18000ABDE
0x18000abbd  and     r8w, r11w; unsigned __int64
0x18000abc1  mov     [rdx], r10d
0x18000abc4  mov     eax, ecx
0x18000abc6  mov     [rdx+6], r8w
0x18000abcb  shr     eax, 0Eh
0x18000abce  and     ax, r9w
0x18000abd2  shl     ax, 2
0x18000abd6  mov     [rdx+4], ax
0x18000abda  add     rdx, 8
0x18000abde  mov     eax, ecx
0x18000abe0  shr     eax, 0Fh
0x18000abe3  test    al, 7Fh
0x18000abe5  jz      short loc_18000AC09
0x18000abe7  shr     ecx, 16h
0x18000abea  and     ax, 7Fh
0x18000abee  and     cx, r9w
0x18000abf2  mov     [rdx], r10d
0x18000abf5  shl     cx, 2
0x18000abf9  add     cx, r9w
0x18000abfd  mov     [rdx+6], ax
0x18000ac01  mov     [rdx+4], cx
0x18000ac05  add     rdx, 8
0x18000ac09  lea     rax, [rsp+68h+var_48]
0x18000ac0e  sub     rdx, rax
0x18000ac11  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000ac15  test    rdx, rdx
0x18000ac18  jle     short loc_18000AC24
0x18000ac1a  lea     rcx, [rsp+68h+var_48]; this
0x18000ac1f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000ac24  mov     rcx, [rsp+68h+var_18]
0x18000ac29  xor     rcx, rsp; StackCookie
0x18000ac2c  call    __security_check_cookie
0x18000ac31  add     rsp, 68h
0x18000ac35  retn
```
