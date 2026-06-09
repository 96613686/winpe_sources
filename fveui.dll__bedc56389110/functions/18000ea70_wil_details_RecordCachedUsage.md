# wil_details_RecordCachedUsage

- ea: `0x18000ea70`
- end: `0x18000ebb7`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a7f4`

## callees

- `0x180001bb0`
- `0x18000c624`
- `0x18000ea70`

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
0x18000ea70  sub     rsp, 68h
0x18000ea74  mov     rax, cs:__security_cookie
0x18000ea7b  xor     rax, rsp
0x18000ea7e  mov     [rsp+68h+var_18], rax
0x18000ea83  mov     r9, rdx
0x18000ea86  mov     r10d, ecx
0x18000ea89  prefetchw byte ptr [rdx]
0x18000ea8c  mov     eax, [rdx]
0x18000ea8e  mov     r8d, eax
0x18000ea91  and     r8d, 0FFC0401Eh
0x18000ea98  lock cmpxchg [rdx], r8d
0x18000ea9d  jnz     short loc_18000EA8E
0x18000ea9f  mov     ecx, eax
0x18000eaa1  mov     r8d, eax
0x18000eaa4  shr     r8d, 1
0x18000eaa7  and     r8d, 0Fh
0x18000eaab  jz      short loc_18000EAC8
0x18000eaad  prefetchw byte ptr [rdx+4]
0x18000eab1  mov     eax, [rdx+4]
0x18000eab4  mov     edx, eax
0x18000eab6  or      edx, r8d
0x18000eab9  lock cmpxchg [r9+4], edx
0x18000eabf  jnz     short loc_18000EAB4
0x18000eac1  not     eax
0x18000eac3  and     eax, r8d
0x18000eac6  jmp     short loc_18000EACB
0x18000eac8  mov     eax, r8d
0x18000eacb  mov     r8d, 2
0x18000ead1  lea     r9d, [r8-1]
0x18000ead5  test    r9b, al
0x18000ead8  jz      short loc_18000EAEE
0x18000eada  mov     [rsp+68h+var_48], r10d
0x18000eadf  mov     [rsp+68h+var_44], 10002h
0x18000eae7  lea     rdx, [rsp+68h+var_40]
0x18000eaec  jmp     short loc_18000EAF3
0x18000eaee  lea     rdx, [rsp+68h+var_48]
0x18000eaf3  test    r8b, al
0x18000eaf6  jz      short loc_18000EB06
0x18000eaf8  mov     [rdx], r10d
0x18000eafb  mov     dword ptr [rdx+4], 10006h
0x18000eb02  add     rdx, 8
0x18000eb06  test    al, 4
0x18000eb08  jz      short loc_18000EB18
0x18000eb0a  mov     [rdx], r10d
0x18000eb0d  mov     dword ptr [rdx+4], 10003h
0x18000eb14  add     rdx, 8
0x18000eb18  cmp     eax, 8
0x18000eb1b  jb      short loc_18000EB2B
0x18000eb1d  mov     [rdx], r10d
0x18000eb20  mov     dword ptr [rdx+4], 10007h
0x18000eb27  add     rdx, 8
0x18000eb2b  mov     r8d, ecx
0x18000eb2e  shr     r8d, 5
0x18000eb32  mov     r11d, 1FFh
0x18000eb38  test    r11d, r8d
0x18000eb3b  jz      short loc_18000EB5E
0x18000eb3d  mov     [rdx], r10d
0x18000eb40  mov     eax, ecx
0x18000eb42  shr     eax, 0Eh
0x18000eb45  and     ax, r9w
0x18000eb49  shl     ax, 2
0x18000eb4d  mov     [rdx+4], ax
0x18000eb51  and     r8w, r11w; unsigned __int64
0x18000eb55  mov     [rdx+6], r8w
0x18000eb5a  add     rdx, 8
0x18000eb5e  mov     eax, ecx
0x18000eb60  shr     eax, 0Fh
0x18000eb63  test    al, 7Fh
0x18000eb65  jz      short loc_18000EB89
0x18000eb67  mov     [rdx], r10d
0x18000eb6a  shr     ecx, 16h
0x18000eb6d  and     cx, r9w
0x18000eb71  shl     cx, 2
0x18000eb75  add     cx, r9w
0x18000eb79  mov     [rdx+4], cx
0x18000eb7d  and     ax, 7Fh
0x18000eb81  mov     [rdx+6], ax
0x18000eb85  add     rdx, 8
0x18000eb89  lea     rax, [rsp+68h+var_48]
0x18000eb8e  sub     rdx, rax
0x18000eb91  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000eb95  test    rdx, rdx
0x18000eb98  jle     short loc_18000EBA5
0x18000eb9a  lea     rcx, [rsp+68h+var_48]; this
0x18000eb9f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000eba4  nop
0x18000eba5  mov     rcx, [rsp+68h+var_18]
0x18000ebaa  xor     rcx, rsp; StackCookie
0x18000ebad  call    __security_check_cookie
0x18000ebb2  add     rsp, 68h
0x18000ebb6  retn
```
