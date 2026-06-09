# wil_details_RecordCachedUsage

- ea: `0x18001b650`
- end: `0x18001b797`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800195bc`

## callees

- `0x180006330`
- `0x18001a888`
- `0x18001b650`

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
0x18001b650  sub     rsp, 68h
0x18001b654  mov     rax, cs:__security_cookie
0x18001b65b  xor     rax, rsp
0x18001b65e  mov     [rsp+68h+var_18], rax
0x18001b663  mov     r9, rdx
0x18001b666  mov     r10d, ecx
0x18001b669  prefetchw byte ptr [rdx]
0x18001b66c  mov     eax, [rdx]
0x18001b66e  mov     r8d, eax
0x18001b671  and     r8d, 0FFC0401Eh
0x18001b678  lock cmpxchg [rdx], r8d
0x18001b67d  jnz     short loc_18001B66E
0x18001b67f  mov     ecx, eax
0x18001b681  mov     r8d, eax
0x18001b684  shr     r8d, 1
0x18001b687  and     r8d, 0Fh
0x18001b68b  jz      short loc_18001B6A8
0x18001b68d  prefetchw byte ptr [rdx+4]
0x18001b691  mov     eax, [rdx+4]
0x18001b694  mov     edx, eax
0x18001b696  or      edx, r8d
0x18001b699  lock cmpxchg [r9+4], edx
0x18001b69f  jnz     short loc_18001B694
0x18001b6a1  not     eax
0x18001b6a3  and     eax, r8d
0x18001b6a6  jmp     short loc_18001B6AB
0x18001b6a8  mov     eax, r8d
0x18001b6ab  mov     r8d, 2
0x18001b6b1  lea     r9d, [r8-1]
0x18001b6b5  test    r9b, al
0x18001b6b8  jz      short loc_18001B6CE
0x18001b6ba  mov     [rsp+68h+var_48], r10d
0x18001b6bf  mov     [rsp+68h+var_44], 10002h
0x18001b6c7  lea     rdx, [rsp+68h+var_40]
0x18001b6cc  jmp     short loc_18001B6D3
0x18001b6ce  lea     rdx, [rsp+68h+var_48]
0x18001b6d3  test    r8b, al
0x18001b6d6  jz      short loc_18001B6E6
0x18001b6d8  mov     [rdx], r10d
0x18001b6db  mov     dword ptr [rdx+4], 10006h
0x18001b6e2  add     rdx, 8
0x18001b6e6  test    al, 4
0x18001b6e8  jz      short loc_18001B6F8
0x18001b6ea  mov     [rdx], r10d
0x18001b6ed  mov     dword ptr [rdx+4], 10003h
0x18001b6f4  add     rdx, 8
0x18001b6f8  cmp     eax, 8
0x18001b6fb  jb      short loc_18001B70B
0x18001b6fd  mov     [rdx], r10d
0x18001b700  mov     dword ptr [rdx+4], 10007h
0x18001b707  add     rdx, 8
0x18001b70b  mov     r8d, ecx
0x18001b70e  shr     r8d, 5
0x18001b712  mov     r11d, 1FFh
0x18001b718  test    r11d, r8d
0x18001b71b  jz      short loc_18001B73E
0x18001b71d  mov     [rdx], r10d
0x18001b720  mov     eax, ecx
0x18001b722  shr     eax, 0Eh
0x18001b725  and     ax, r9w
0x18001b729  shl     ax, 2
0x18001b72d  mov     [rdx+4], ax
0x18001b731  and     r8w, r11w; unsigned __int64
0x18001b735  mov     [rdx+6], r8w
0x18001b73a  add     rdx, 8
0x18001b73e  mov     eax, ecx
0x18001b740  shr     eax, 0Fh
0x18001b743  test    al, 7Fh
0x18001b745  jz      short loc_18001B769
0x18001b747  mov     [rdx], r10d
0x18001b74a  shr     ecx, 16h
0x18001b74d  and     cx, r9w
0x18001b751  shl     cx, 2
0x18001b755  add     cx, r9w
0x18001b759  mov     [rdx+4], cx
0x18001b75d  and     ax, 7Fh
0x18001b761  mov     [rdx+6], ax
0x18001b765  add     rdx, 8
0x18001b769  lea     rax, [rsp+68h+var_48]
0x18001b76e  sub     rdx, rax
0x18001b771  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18001b775  test    rdx, rdx
0x18001b778  jle     short loc_18001B785
0x18001b77a  lea     rcx, [rsp+68h+var_48]; this
0x18001b77f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18001b784  nop
0x18001b785  mov     rcx, [rsp+68h+var_18]
0x18001b78a  xor     rcx, rsp; StackCookie
0x18001b78d  call    __security_check_cookie
0x18001b792  add     rsp, 68h
0x18001b796  retn
```
