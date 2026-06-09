# wil_details_RecordCachedUsage

- ea: `0x18001b220`
- end: `0x18001b367`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800188a0`

## callees

- `0x180014130`
- `0x18001a364`
- `0x18001b220`

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
0x18001b220  sub     rsp, 68h
0x18001b224  mov     rax, cs:__security_cookie
0x18001b22b  xor     rax, rsp
0x18001b22e  mov     [rsp+68h+var_18], rax
0x18001b233  mov     r9, rdx
0x18001b236  mov     r10d, ecx
0x18001b239  prefetchw byte ptr [rdx]
0x18001b23c  mov     eax, [rdx]
0x18001b23e  mov     r8d, eax
0x18001b241  and     r8d, 0FFC0401Eh
0x18001b248  lock cmpxchg [rdx], r8d
0x18001b24d  jnz     short loc_18001B23E
0x18001b24f  mov     ecx, eax
0x18001b251  mov     r8d, eax
0x18001b254  shr     r8d, 1
0x18001b257  and     r8d, 0Fh
0x18001b25b  jz      short loc_18001B278
0x18001b25d  prefetchw byte ptr [rdx+4]
0x18001b261  mov     eax, [rdx+4]
0x18001b264  mov     edx, eax
0x18001b266  or      edx, r8d
0x18001b269  lock cmpxchg [r9+4], edx
0x18001b26f  jnz     short loc_18001B264
0x18001b271  not     eax
0x18001b273  and     eax, r8d
0x18001b276  jmp     short loc_18001B27B
0x18001b278  mov     eax, r8d
0x18001b27b  mov     r8d, 2
0x18001b281  lea     r9d, [r8-1]
0x18001b285  test    r9b, al
0x18001b288  jz      short loc_18001B29E
0x18001b28a  mov     [rsp+68h+var_48], r10d
0x18001b28f  mov     [rsp+68h+var_44], 10002h
0x18001b297  lea     rdx, [rsp+68h+var_40]
0x18001b29c  jmp     short loc_18001B2A3
0x18001b29e  lea     rdx, [rsp+68h+var_48]
0x18001b2a3  test    r8b, al
0x18001b2a6  jz      short loc_18001B2B6
0x18001b2a8  mov     [rdx], r10d
0x18001b2ab  mov     dword ptr [rdx+4], 10006h
0x18001b2b2  add     rdx, 8
0x18001b2b6  test    al, 4
0x18001b2b8  jz      short loc_18001B2C8
0x18001b2ba  mov     [rdx], r10d
0x18001b2bd  mov     dword ptr [rdx+4], 10003h
0x18001b2c4  add     rdx, 8
0x18001b2c8  cmp     eax, 8
0x18001b2cb  jb      short loc_18001B2DB
0x18001b2cd  mov     [rdx], r10d
0x18001b2d0  mov     dword ptr [rdx+4], 10007h
0x18001b2d7  add     rdx, 8
0x18001b2db  mov     r8d, ecx
0x18001b2de  shr     r8d, 5
0x18001b2e2  mov     r11d, 1FFh
0x18001b2e8  test    r11d, r8d
0x18001b2eb  jz      short loc_18001B30E
0x18001b2ed  mov     [rdx], r10d
0x18001b2f0  mov     eax, ecx
0x18001b2f2  shr     eax, 0Eh
0x18001b2f5  and     ax, r9w
0x18001b2f9  shl     ax, 2
0x18001b2fd  mov     [rdx+4], ax
0x18001b301  and     r8w, r11w; unsigned __int64
0x18001b305  mov     [rdx+6], r8w
0x18001b30a  add     rdx, 8
0x18001b30e  mov     eax, ecx
0x18001b310  shr     eax, 0Fh
0x18001b313  test    al, 7Fh
0x18001b315  jz      short loc_18001B339
0x18001b317  mov     [rdx], r10d
0x18001b31a  shr     ecx, 16h
0x18001b31d  and     cx, r9w
0x18001b321  shl     cx, 2
0x18001b325  add     cx, r9w
0x18001b329  mov     [rdx+4], cx
0x18001b32d  and     ax, 7Fh
0x18001b331  mov     [rdx+6], ax
0x18001b335  add     rdx, 8
0x18001b339  lea     rax, [rsp+68h+var_48]
0x18001b33e  sub     rdx, rax
0x18001b341  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18001b345  test    rdx, rdx
0x18001b348  jle     short loc_18001B355
0x18001b34a  lea     rcx, [rsp+68h+var_48]; this
0x18001b34f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18001b354  nop
0x18001b355  mov     rcx, [rsp+68h+var_18]
0x18001b35a  xor     rcx, rsp; StackCookie
0x18001b35d  call    __security_check_cookie
0x18001b362  add     rsp, 68h
0x18001b366  retn
```
