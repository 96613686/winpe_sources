# wil_details_RecordCachedUsage

- ea: `0x18000d3c0`
- end: `0x18000d507`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a68c`

## callees

- `0x180001640`
- `0x18000c264`
- `0x18000d3c0`

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
0x18000d3c0  sub     rsp, 68h
0x18000d3c4  mov     rax, cs:__security_cookie
0x18000d3cb  xor     rax, rsp
0x18000d3ce  mov     [rsp+68h+var_18], rax
0x18000d3d3  mov     r9, rdx
0x18000d3d6  mov     r10d, ecx
0x18000d3d9  prefetchw byte ptr [rdx]
0x18000d3dc  mov     eax, [rdx]
0x18000d3de  mov     r8d, eax
0x18000d3e1  and     r8d, 0FFC0401Eh
0x18000d3e8  lock cmpxchg [rdx], r8d
0x18000d3ed  jnz     short loc_18000D3DE
0x18000d3ef  mov     ecx, eax
0x18000d3f1  mov     r8d, eax
0x18000d3f4  shr     r8d, 1
0x18000d3f7  and     r8d, 0Fh
0x18000d3fb  jz      short loc_18000D418
0x18000d3fd  prefetchw byte ptr [rdx+4]
0x18000d401  mov     eax, [rdx+4]
0x18000d404  mov     edx, eax
0x18000d406  or      edx, r8d
0x18000d409  lock cmpxchg [r9+4], edx
0x18000d40f  jnz     short loc_18000D404
0x18000d411  not     eax
0x18000d413  and     eax, r8d
0x18000d416  jmp     short loc_18000D41B
0x18000d418  mov     eax, r8d
0x18000d41b  mov     r8d, 2
0x18000d421  lea     r9d, [r8-1]
0x18000d425  test    r9b, al
0x18000d428  jz      short loc_18000D43E
0x18000d42a  mov     [rsp+68h+var_48], r10d
0x18000d42f  mov     [rsp+68h+var_44], 10002h
0x18000d437  lea     rdx, [rsp+68h+var_40]
0x18000d43c  jmp     short loc_18000D443
0x18000d43e  lea     rdx, [rsp+68h+var_48]
0x18000d443  test    r8b, al
0x18000d446  jz      short loc_18000D456
0x18000d448  mov     [rdx], r10d
0x18000d44b  mov     dword ptr [rdx+4], 10006h
0x18000d452  add     rdx, 8
0x18000d456  test    al, 4
0x18000d458  jz      short loc_18000D468
0x18000d45a  mov     [rdx], r10d
0x18000d45d  mov     dword ptr [rdx+4], 10003h
0x18000d464  add     rdx, 8
0x18000d468  cmp     eax, 8
0x18000d46b  jb      short loc_18000D47B
0x18000d46d  mov     [rdx], r10d
0x18000d470  mov     dword ptr [rdx+4], 10007h
0x18000d477  add     rdx, 8
0x18000d47b  mov     r8d, ecx
0x18000d47e  shr     r8d, 5
0x18000d482  mov     r11d, 1FFh
0x18000d488  test    r11d, r8d
0x18000d48b  jz      short loc_18000D4AE
0x18000d48d  mov     [rdx], r10d
0x18000d490  mov     eax, ecx
0x18000d492  shr     eax, 0Eh
0x18000d495  and     ax, r9w
0x18000d499  shl     ax, 2
0x18000d49d  mov     [rdx+4], ax
0x18000d4a1  and     r8w, r11w; unsigned __int64
0x18000d4a5  mov     [rdx+6], r8w
0x18000d4aa  add     rdx, 8
0x18000d4ae  mov     eax, ecx
0x18000d4b0  shr     eax, 0Fh
0x18000d4b3  test    al, 7Fh
0x18000d4b5  jz      short loc_18000D4D9
0x18000d4b7  mov     [rdx], r10d
0x18000d4ba  shr     ecx, 16h
0x18000d4bd  and     cx, r9w
0x18000d4c1  shl     cx, 2
0x18000d4c5  add     cx, r9w
0x18000d4c9  mov     [rdx+4], cx
0x18000d4cd  and     ax, 7Fh
0x18000d4d1  mov     [rdx+6], ax
0x18000d4d5  add     rdx, 8
0x18000d4d9  lea     rax, [rsp+68h+var_48]
0x18000d4de  sub     rdx, rax
0x18000d4e1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000d4e5  test    rdx, rdx
0x18000d4e8  jle     short loc_18000D4F5
0x18000d4ea  lea     rcx, [rsp+68h+var_48]; this
0x18000d4ef  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000d4f4  nop
0x18000d4f5  mov     rcx, [rsp+68h+var_18]
0x18000d4fa  xor     rcx, rsp; StackCookie
0x18000d4fd  call    __security_check_cookie
0x18000d502  add     rsp, 68h
0x18000d506  retn
```
