# wil_details_RecordCachedUsage

- ea: `0x1400188a8`
- end: `0x1400189ef`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140016d74`

## callees

- `0x140017d80`
- `0x1400188a8`
- `0x14001e050`

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
0x1400188a8  sub     rsp, 68h
0x1400188ac  mov     rax, cs:__security_cookie
0x1400188b3  xor     rax, rsp
0x1400188b6  mov     [rsp+68h+var_18], rax
0x1400188bb  mov     r9, rdx
0x1400188be  mov     r10d, ecx
0x1400188c1  prefetchw byte ptr [rdx]
0x1400188c4  mov     eax, [rdx]
0x1400188c6  mov     r8d, eax
0x1400188c9  and     r8d, 0FFC0401Eh
0x1400188d0  lock cmpxchg [rdx], r8d
0x1400188d5  jnz     short loc_1400188C6
0x1400188d7  mov     ecx, eax
0x1400188d9  mov     r8d, eax
0x1400188dc  shr     r8d, 1
0x1400188df  and     r8d, 0Fh
0x1400188e3  jz      short loc_140018900
0x1400188e5  prefetchw byte ptr [rdx+4]
0x1400188e9  mov     eax, [rdx+4]
0x1400188ec  mov     edx, eax
0x1400188ee  or      edx, r8d
0x1400188f1  lock cmpxchg [r9+4], edx
0x1400188f7  jnz     short loc_1400188EC
0x1400188f9  not     eax
0x1400188fb  and     eax, r8d
0x1400188fe  jmp     short loc_140018903
0x140018900  mov     eax, r8d
0x140018903  mov     r8d, 2
0x140018909  lea     r9d, [r8-1]
0x14001890d  test    r9b, al
0x140018910  jz      short loc_140018926
0x140018912  mov     [rsp+68h+var_48], r10d
0x140018917  mov     [rsp+68h+var_44], 10002h
0x14001891f  lea     rdx, [rsp+68h+var_40]
0x140018924  jmp     short loc_14001892B
0x140018926  lea     rdx, [rsp+68h+var_48]
0x14001892b  test    r8b, al
0x14001892e  jz      short loc_14001893E
0x140018930  mov     [rdx], r10d
0x140018933  mov     dword ptr [rdx+4], 10006h
0x14001893a  add     rdx, 8
0x14001893e  test    al, 4
0x140018940  jz      short loc_140018950
0x140018942  mov     [rdx], r10d
0x140018945  mov     dword ptr [rdx+4], 10003h
0x14001894c  add     rdx, 8
0x140018950  cmp     eax, 8
0x140018953  jb      short loc_140018963
0x140018955  mov     [rdx], r10d
0x140018958  mov     dword ptr [rdx+4], 10007h
0x14001895f  add     rdx, 8
0x140018963  mov     r8d, ecx
0x140018966  shr     r8d, 5
0x14001896a  mov     r11d, 1FFh
0x140018970  test    r11d, r8d
0x140018973  jz      short loc_140018996
0x140018975  mov     [rdx], r10d
0x140018978  mov     eax, ecx
0x14001897a  shr     eax, 0Eh
0x14001897d  and     ax, r9w
0x140018981  shl     ax, 2
0x140018985  mov     [rdx+4], ax
0x140018989  and     r8w, r11w; unsigned __int64
0x14001898d  mov     [rdx+6], r8w
0x140018992  add     rdx, 8
0x140018996  mov     eax, ecx
0x140018998  shr     eax, 0Fh
0x14001899b  test    al, 7Fh
0x14001899d  jz      short loc_1400189C1
0x14001899f  mov     [rdx], r10d
0x1400189a2  shr     ecx, 16h
0x1400189a5  and     cx, r9w
0x1400189a9  shl     cx, 2
0x1400189ad  add     cx, r9w
0x1400189b1  mov     [rdx+4], cx
0x1400189b5  and     ax, 7Fh
0x1400189b9  mov     [rdx+6], ax
0x1400189bd  add     rdx, 8
0x1400189c1  lea     rax, [rsp+68h+var_48]
0x1400189c6  sub     rdx, rax
0x1400189c9  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1400189cd  test    rdx, rdx
0x1400189d0  jle     short loc_1400189DD
0x1400189d2  lea     rcx, [rsp+68h+var_48]; this
0x1400189d7  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1400189dc  nop
0x1400189dd  mov     rcx, [rsp+68h+var_18]
0x1400189e2  xor     rcx, rsp; StackCookie
0x1400189e5  call    __security_check_cookie
0x1400189ea  add     rsp, 68h
0x1400189ee  retn
```
