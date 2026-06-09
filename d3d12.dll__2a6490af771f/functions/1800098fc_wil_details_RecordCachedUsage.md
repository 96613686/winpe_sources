# wil_details_RecordCachedUsage

- ea: `0x1800098fc`
- end: `0x180009a43`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d6a8`

## callees

- `0x1800098fc`
- `0x18000b410`
- `0x18000df18`

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
0x1800098fc  sub     rsp, 68h
0x180009900  mov     rax, cs:__security_cookie
0x180009907  xor     rax, rsp
0x18000990a  mov     [rsp+68h+var_18], rax
0x18000990f  mov     r9, rdx
0x180009912  mov     r10d, ecx
0x180009915  prefetchw byte ptr [rdx]
0x180009918  mov     eax, [rdx]
0x18000991a  mov     r8d, eax
0x18000991d  and     r8d, 0FFC0401Eh
0x180009924  lock cmpxchg [rdx], r8d
0x180009929  jnz     short loc_18000991A
0x18000992b  mov     ecx, eax
0x18000992d  mov     r8d, eax
0x180009930  shr     r8d, 1
0x180009933  and     r8d, 0Fh
0x180009937  jz      short loc_180009954
0x180009939  prefetchw byte ptr [rdx+4]
0x18000993d  mov     eax, [rdx+4]
0x180009940  mov     edx, eax
0x180009942  or      edx, r8d
0x180009945  lock cmpxchg [r9+4], edx
0x18000994b  jnz     short loc_180009940
0x18000994d  not     eax
0x18000994f  and     eax, r8d
0x180009952  jmp     short loc_180009957
0x180009954  mov     eax, r8d
0x180009957  mov     r8d, 2
0x18000995d  lea     r9d, [r8-1]
0x180009961  test    r9b, al
0x180009964  jz      short loc_18000997A
0x180009966  mov     [rsp+68h+var_48], r10d
0x18000996b  mov     [rsp+68h+var_44], 10002h
0x180009973  lea     rdx, [rsp+68h+var_40]
0x180009978  jmp     short loc_18000997F
0x18000997a  lea     rdx, [rsp+68h+var_48]
0x18000997f  test    r8b, al
0x180009982  jz      short loc_180009992
0x180009984  mov     [rdx], r10d
0x180009987  mov     dword ptr [rdx+4], 10006h
0x18000998e  add     rdx, 8
0x180009992  test    al, 4
0x180009994  jz      short loc_1800099A4
0x180009996  mov     [rdx], r10d
0x180009999  mov     dword ptr [rdx+4], 10003h
0x1800099a0  add     rdx, 8
0x1800099a4  cmp     eax, 8
0x1800099a7  jb      short loc_1800099B7
0x1800099a9  mov     [rdx], r10d
0x1800099ac  mov     dword ptr [rdx+4], 10007h
0x1800099b3  add     rdx, 8
0x1800099b7  mov     r8d, ecx
0x1800099ba  shr     r8d, 5
0x1800099be  mov     r11d, 1FFh
0x1800099c4  test    r11d, r8d
0x1800099c7  jz      short loc_1800099EA
0x1800099c9  mov     [rdx], r10d
0x1800099cc  mov     eax, ecx
0x1800099ce  shr     eax, 0Eh
0x1800099d1  and     ax, r9w
0x1800099d5  shl     ax, 2
0x1800099d9  mov     [rdx+4], ax
0x1800099dd  and     r8w, r11w; unsigned __int64
0x1800099e1  mov     [rdx+6], r8w
0x1800099e6  add     rdx, 8
0x1800099ea  mov     eax, ecx
0x1800099ec  shr     eax, 0Fh
0x1800099ef  test    al, 7Fh
0x1800099f1  jz      short loc_180009A15
0x1800099f3  mov     [rdx], r10d
0x1800099f6  shr     ecx, 16h
0x1800099f9  and     cx, r9w
0x1800099fd  shl     cx, 2
0x180009a01  add     cx, r9w
0x180009a05  mov     [rdx+4], cx
0x180009a09  and     ax, 7Fh
0x180009a0d  mov     [rdx+6], ax
0x180009a11  add     rdx, 8
0x180009a15  lea     rax, [rsp+68h+var_48]
0x180009a1a  sub     rdx, rax
0x180009a1d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180009a21  test    rdx, rdx
0x180009a24  jle     short loc_180009A31
0x180009a26  lea     rcx, [rsp+68h+var_48]; this
0x180009a2b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180009a30  nop
0x180009a31  mov     rcx, [rsp+68h+var_18]
0x180009a36  xor     rcx, rsp; StackCookie
0x180009a39  call    __security_check_cookie
0x180009a3e  add     rsp, 68h
0x180009a42  retn
```
