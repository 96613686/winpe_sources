# wil_details_RecordCachedUsage

- ea: `0x18000db88`
- end: `0x18000dccf`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `void __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a3d4`

## callees

- `0x180001a70`
- `0x18000c000`
- `0x18000db88`

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
0x18000db88  sub     rsp, 68h
0x18000db8c  mov     rax, cs:__security_cookie
0x18000db93  xor     rax, rsp
0x18000db96  mov     [rsp+68h+var_18], rax
0x18000db9b  mov     r9, rdx
0x18000db9e  mov     r10d, ecx
0x18000dba1  prefetchw byte ptr [rdx]
0x18000dba4  mov     eax, [rdx]
0x18000dba6  mov     r8d, eax
0x18000dba9  and     r8d, 0FFC0401Eh
0x18000dbb0  lock cmpxchg [rdx], r8d
0x18000dbb5  jnz     short loc_18000DBA6
0x18000dbb7  mov     ecx, eax
0x18000dbb9  mov     r8d, eax
0x18000dbbc  shr     r8d, 1
0x18000dbbf  and     r8d, 0Fh
0x18000dbc3  jz      short loc_18000DBE0
0x18000dbc5  prefetchw byte ptr [rdx+4]
0x18000dbc9  mov     eax, [rdx+4]
0x18000dbcc  mov     edx, eax
0x18000dbce  or      edx, r8d
0x18000dbd1  lock cmpxchg [r9+4], edx
0x18000dbd7  jnz     short loc_18000DBCC
0x18000dbd9  not     eax
0x18000dbdb  and     eax, r8d
0x18000dbde  jmp     short loc_18000DBE3
0x18000dbe0  mov     eax, r8d
0x18000dbe3  mov     r8d, 2
0x18000dbe9  lea     r9d, [r8-1]
0x18000dbed  test    r9b, al
0x18000dbf0  jz      short loc_18000DC06
0x18000dbf2  mov     [rsp+68h+var_48], r10d
0x18000dbf7  mov     [rsp+68h+var_44], 10002h
0x18000dbff  lea     rdx, [rsp+68h+var_40]
0x18000dc04  jmp     short loc_18000DC0B
0x18000dc06  lea     rdx, [rsp+68h+var_48]
0x18000dc0b  test    r8b, al
0x18000dc0e  jz      short loc_18000DC1E
0x18000dc10  mov     [rdx], r10d
0x18000dc13  mov     dword ptr [rdx+4], 10006h
0x18000dc1a  add     rdx, 8
0x18000dc1e  test    al, 4
0x18000dc20  jz      short loc_18000DC30
0x18000dc22  mov     [rdx], r10d
0x18000dc25  mov     dword ptr [rdx+4], 10003h
0x18000dc2c  add     rdx, 8
0x18000dc30  cmp     eax, 8
0x18000dc33  jb      short loc_18000DC43
0x18000dc35  mov     [rdx], r10d
0x18000dc38  mov     dword ptr [rdx+4], 10007h
0x18000dc3f  add     rdx, 8
0x18000dc43  mov     r8d, ecx
0x18000dc46  shr     r8d, 5
0x18000dc4a  mov     r11d, 1FFh
0x18000dc50  test    r11d, r8d
0x18000dc53  jz      short loc_18000DC76
0x18000dc55  mov     [rdx], r10d
0x18000dc58  mov     eax, ecx
0x18000dc5a  shr     eax, 0Eh
0x18000dc5d  and     ax, r9w
0x18000dc61  shl     ax, 2
0x18000dc65  mov     [rdx+4], ax
0x18000dc69  and     r8w, r11w; unsigned __int64
0x18000dc6d  mov     [rdx+6], r8w
0x18000dc72  add     rdx, 8
0x18000dc76  mov     eax, ecx
0x18000dc78  shr     eax, 0Fh
0x18000dc7b  test    al, 7Fh
0x18000dc7d  jz      short loc_18000DCA1
0x18000dc7f  mov     [rdx], r10d
0x18000dc82  shr     ecx, 16h
0x18000dc85  and     cx, r9w
0x18000dc89  shl     cx, 2
0x18000dc8d  add     cx, r9w
0x18000dc91  mov     [rdx+4], cx
0x18000dc95  and     ax, 7Fh
0x18000dc99  mov     [rdx+6], ax
0x18000dc9d  add     rdx, 8
0x18000dca1  lea     rax, [rsp+68h+var_48]
0x18000dca6  sub     rdx, rax
0x18000dca9  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000dcad  test    rdx, rdx
0x18000dcb0  jle     short loc_18000DCBD
0x18000dcb2  lea     rcx, [rsp+68h+var_48]; this
0x18000dcb7  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000dcbc  nop
0x18000dcbd  mov     rcx, [rsp+68h+var_18]
0x18000dcc2  xor     rcx, rsp; StackCookie
0x18000dcc5  call    __security_check_cookie
0x18000dcca  add     rsp, 68h
0x18000dcce  retn
```
