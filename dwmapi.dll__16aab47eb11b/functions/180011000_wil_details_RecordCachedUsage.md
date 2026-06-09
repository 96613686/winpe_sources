# wil_details_RecordCachedUsage

- ea: `0x180011000`
- end: `0x180011146`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f980`

## callees

- `0x18000d0a0`
- `0x1800106d4`
- `0x180011000`

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
0x180011000  sub     rsp, 68h
0x180011004  mov     rax, cs:__security_cookie
0x18001100b  xor     rax, rsp
0x18001100e  mov     [rsp+68h+var_18], rax
0x180011013  mov     r9, rdx
0x180011016  mov     r10d, ecx
0x180011019  prefetchw byte ptr [rdx]
0x18001101c  mov     eax, [rdx]
0x18001101e  mov     r8d, eax
0x180011021  and     r8d, 0FFC0401Eh
0x180011028  lock cmpxchg [rdx], r8d
0x18001102d  jnz     short loc_18001101E
0x18001102f  mov     r8d, eax
0x180011032  mov     ecx, eax
0x180011034  shr     r8d, 1
0x180011037  and     r8d, 0Fh
0x18001103b  jz      short loc_180011058
0x18001103d  prefetchw byte ptr [rdx+4]
0x180011041  mov     eax, [rdx+4]
0x180011044  mov     edx, eax
0x180011046  or      edx, r8d
0x180011049  lock cmpxchg [r9+4], edx
0x18001104f  jnz     short loc_180011044
0x180011051  not     eax
0x180011053  and     eax, r8d
0x180011056  jmp     short loc_18001105B
0x180011058  mov     eax, r8d
0x18001105b  mov     r8d, 2
0x180011061  lea     r9d, [r8-1]
0x180011065  test    r9b, al
0x180011068  jz      short loc_18001107E
0x18001106a  mov     [rsp+68h+var_48], r10d
0x18001106f  lea     rdx, [rsp+68h+var_40]
0x180011074  mov     [rsp+68h+var_44], 10002h
0x18001107c  jmp     short loc_180011083
0x18001107e  lea     rdx, [rsp+68h+var_48]
0x180011083  test    r8b, al
0x180011086  jz      short loc_180011096
0x180011088  mov     [rdx], r10d
0x18001108b  mov     dword ptr [rdx+4], 10006h
0x180011092  add     rdx, 8
0x180011096  test    al, 4
0x180011098  jz      short loc_1800110A8
0x18001109a  mov     [rdx], r10d
0x18001109d  mov     dword ptr [rdx+4], 10003h
0x1800110a4  add     rdx, 8
0x1800110a8  cmp     eax, 8
0x1800110ab  jb      short loc_1800110BB
0x1800110ad  mov     [rdx], r10d
0x1800110b0  mov     dword ptr [rdx+4], 10007h
0x1800110b7  add     rdx, 8
0x1800110bb  mov     r8d, ecx
0x1800110be  mov     r11d, 1FFh
0x1800110c4  shr     r8d, 5
0x1800110c8  test    r11d, r8d
0x1800110cb  jz      short loc_1800110EE
0x1800110cd  and     r8w, r11w; unsigned __int64
0x1800110d1  mov     [rdx], r10d
0x1800110d4  mov     eax, ecx
0x1800110d6  mov     [rdx+6], r8w
0x1800110db  shr     eax, 0Eh
0x1800110de  and     ax, r9w
0x1800110e2  shl     ax, 2
0x1800110e6  mov     [rdx+4], ax
0x1800110ea  add     rdx, 8
0x1800110ee  mov     eax, ecx
0x1800110f0  shr     eax, 0Fh
0x1800110f3  test    al, 7Fh
0x1800110f5  jz      short loc_180011119
0x1800110f7  shr     ecx, 16h
0x1800110fa  and     ax, 7Fh
0x1800110fe  and     cx, r9w
0x180011102  mov     [rdx], r10d
0x180011105  shl     cx, 2
0x180011109  add     cx, r9w
0x18001110d  mov     [rdx+6], ax
0x180011111  mov     [rdx+4], cx
0x180011115  add     rdx, 8
0x180011119  lea     rax, [rsp+68h+var_48]
0x18001111e  sub     rdx, rax
0x180011121  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180011125  test    rdx, rdx
0x180011128  jle     short loc_180011134
0x18001112a  lea     rcx, [rsp+68h+var_48]; this
0x18001112f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180011134  mov     rcx, [rsp+68h+var_18]
0x180011139  xor     rcx, rsp; StackCookie
0x18001113c  call    __security_check_cookie
0x180011141  add     rsp, 68h
0x180011145  retn
```
