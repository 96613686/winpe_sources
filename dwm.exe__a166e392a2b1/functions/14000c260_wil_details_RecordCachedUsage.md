# wil_details_RecordCachedUsage

- ea: `0x14000c260`
- end: `0x14000c3a6`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009eb8`

## callees

- `0x140005530`
- `0x14000b594`
- `0x14000c260`

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
0x14000c260  sub     rsp, 68h
0x14000c264  mov     rax, cs:__security_cookie
0x14000c26b  xor     rax, rsp
0x14000c26e  mov     [rsp+68h+var_18], rax
0x14000c273  mov     r9, rdx
0x14000c276  mov     r10d, ecx
0x14000c279  prefetchw byte ptr [rdx]
0x14000c27c  mov     eax, [rdx]
0x14000c27e  mov     r8d, eax
0x14000c281  and     r8d, 0FFC0401Eh
0x14000c288  lock cmpxchg [rdx], r8d
0x14000c28d  jnz     short loc_14000C27E
0x14000c28f  mov     r8d, eax
0x14000c292  mov     ecx, eax
0x14000c294  shr     r8d, 1
0x14000c297  and     r8d, 0Fh
0x14000c29b  jz      short loc_14000C2B8
0x14000c29d  prefetchw byte ptr [rdx+4]
0x14000c2a1  mov     eax, [rdx+4]
0x14000c2a4  mov     edx, eax
0x14000c2a6  or      edx, r8d
0x14000c2a9  lock cmpxchg [r9+4], edx
0x14000c2af  jnz     short loc_14000C2A4
0x14000c2b1  not     eax
0x14000c2b3  and     eax, r8d
0x14000c2b6  jmp     short loc_14000C2BB
0x14000c2b8  mov     eax, r8d
0x14000c2bb  mov     r8d, 2
0x14000c2c1  lea     r9d, [r8-1]
0x14000c2c5  test    r9b, al
0x14000c2c8  jz      short loc_14000C2DE
0x14000c2ca  mov     [rsp+68h+var_48], r10d
0x14000c2cf  lea     rdx, [rsp+68h+var_40]
0x14000c2d4  mov     [rsp+68h+var_44], 10002h
0x14000c2dc  jmp     short loc_14000C2E3
0x14000c2de  lea     rdx, [rsp+68h+var_48]
0x14000c2e3  test    r8b, al
0x14000c2e6  jz      short loc_14000C2F6
0x14000c2e8  mov     [rdx], r10d
0x14000c2eb  mov     dword ptr [rdx+4], 10006h
0x14000c2f2  add     rdx, 8
0x14000c2f6  test    al, 4
0x14000c2f8  jz      short loc_14000C308
0x14000c2fa  mov     [rdx], r10d
0x14000c2fd  mov     dword ptr [rdx+4], 10003h
0x14000c304  add     rdx, 8
0x14000c308  cmp     eax, 8
0x14000c30b  jb      short loc_14000C31B
0x14000c30d  mov     [rdx], r10d
0x14000c310  mov     dword ptr [rdx+4], 10007h
0x14000c317  add     rdx, 8
0x14000c31b  mov     r8d, ecx
0x14000c31e  mov     r11d, 1FFh
0x14000c324  shr     r8d, 5
0x14000c328  test    r11d, r8d
0x14000c32b  jz      short loc_14000C34E
0x14000c32d  and     r8w, r11w; unsigned __int64
0x14000c331  mov     [rdx], r10d
0x14000c334  mov     eax, ecx
0x14000c336  mov     [rdx+6], r8w
0x14000c33b  shr     eax, 0Eh
0x14000c33e  and     ax, r9w
0x14000c342  shl     ax, 2
0x14000c346  mov     [rdx+4], ax
0x14000c34a  add     rdx, 8
0x14000c34e  mov     eax, ecx
0x14000c350  shr     eax, 0Fh
0x14000c353  test    al, 7Fh
0x14000c355  jz      short loc_14000C379
0x14000c357  shr     ecx, 16h
0x14000c35a  and     ax, 7Fh
0x14000c35e  and     cx, r9w
0x14000c362  mov     [rdx], r10d
0x14000c365  shl     cx, 2
0x14000c369  add     cx, r9w
0x14000c36d  mov     [rdx+6], ax
0x14000c371  mov     [rdx+4], cx
0x14000c375  add     rdx, 8
0x14000c379  lea     rax, [rsp+68h+var_48]
0x14000c37e  sub     rdx, rax
0x14000c381  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x14000c385  test    rdx, rdx
0x14000c388  jle     short loc_14000C394
0x14000c38a  lea     rcx, [rsp+68h+var_48]; this
0x14000c38f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x14000c394  mov     rcx, [rsp+68h+var_18]
0x14000c399  xor     rcx, rsp; StackCookie
0x14000c39c  call    __security_check_cookie
0x14000c3a1  add     rsp, 68h
0x14000c3a5  retn
```
