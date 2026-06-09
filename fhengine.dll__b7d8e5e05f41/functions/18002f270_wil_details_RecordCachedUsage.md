# wil_details_RecordCachedUsage

- ea: `0x18002f270`
- end: `0x18002f3b7`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002bdc0`

## callees

- `0x18002df88`
- `0x18002f270`
- `0x180031680`

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
0x18002f270  sub     rsp, 68h
0x18002f274  mov     rax, cs:__security_cookie
0x18002f27b  xor     rax, rsp
0x18002f27e  mov     [rsp+68h+var_18], rax
0x18002f283  mov     r9, rdx
0x18002f286  mov     r10d, ecx
0x18002f289  prefetchw byte ptr [rdx]
0x18002f28c  mov     eax, [rdx]
0x18002f28e  mov     r8d, eax
0x18002f291  and     r8d, 0FFC0401Eh
0x18002f298  lock cmpxchg [rdx], r8d
0x18002f29d  jnz     short loc_18002F28E
0x18002f29f  mov     ecx, eax
0x18002f2a1  mov     r8d, eax
0x18002f2a4  shr     r8d, 1
0x18002f2a7  and     r8d, 0Fh
0x18002f2ab  jz      short loc_18002F2C8
0x18002f2ad  prefetchw byte ptr [rdx+4]
0x18002f2b1  mov     eax, [rdx+4]
0x18002f2b4  mov     edx, eax
0x18002f2b6  or      edx, r8d
0x18002f2b9  lock cmpxchg [r9+4], edx
0x18002f2bf  jnz     short loc_18002F2B4
0x18002f2c1  not     eax
0x18002f2c3  and     eax, r8d
0x18002f2c6  jmp     short loc_18002F2CB
0x18002f2c8  mov     eax, r8d
0x18002f2cb  mov     r8d, 2
0x18002f2d1  lea     r9d, [r8-1]
0x18002f2d5  test    r9b, al
0x18002f2d8  jz      short loc_18002F2EE
0x18002f2da  mov     [rsp+68h+var_48], r10d
0x18002f2df  mov     [rsp+68h+var_44], 10002h
0x18002f2e7  lea     rdx, [rsp+68h+var_40]
0x18002f2ec  jmp     short loc_18002F2F3
0x18002f2ee  lea     rdx, [rsp+68h+var_48]
0x18002f2f3  test    r8b, al
0x18002f2f6  jz      short loc_18002F306
0x18002f2f8  mov     [rdx], r10d
0x18002f2fb  mov     dword ptr [rdx+4], 10006h
0x18002f302  add     rdx, 8
0x18002f306  test    al, 4
0x18002f308  jz      short loc_18002F318
0x18002f30a  mov     [rdx], r10d
0x18002f30d  mov     dword ptr [rdx+4], 10003h
0x18002f314  add     rdx, 8
0x18002f318  cmp     eax, 8
0x18002f31b  jb      short loc_18002F32B
0x18002f31d  mov     [rdx], r10d
0x18002f320  mov     dword ptr [rdx+4], 10007h
0x18002f327  add     rdx, 8
0x18002f32b  mov     r8d, ecx
0x18002f32e  shr     r8d, 5
0x18002f332  mov     r11d, 1FFh
0x18002f338  test    r11d, r8d
0x18002f33b  jz      short loc_18002F35E
0x18002f33d  mov     [rdx], r10d
0x18002f340  mov     eax, ecx
0x18002f342  shr     eax, 0Eh
0x18002f345  and     ax, r9w
0x18002f349  shl     ax, 2
0x18002f34d  mov     [rdx+4], ax
0x18002f351  and     r8w, r11w; unsigned __int64
0x18002f355  mov     [rdx+6], r8w
0x18002f35a  add     rdx, 8
0x18002f35e  mov     eax, ecx
0x18002f360  shr     eax, 0Fh
0x18002f363  test    al, 7Fh
0x18002f365  jz      short loc_18002F389
0x18002f367  mov     [rdx], r10d
0x18002f36a  shr     ecx, 16h
0x18002f36d  and     cx, r9w
0x18002f371  shl     cx, 2
0x18002f375  add     cx, r9w
0x18002f379  mov     [rdx+4], cx
0x18002f37d  and     ax, 7Fh
0x18002f381  mov     [rdx+6], ax
0x18002f385  add     rdx, 8
0x18002f389  lea     rax, [rsp+68h+var_48]
0x18002f38e  sub     rdx, rax
0x18002f391  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18002f395  test    rdx, rdx
0x18002f398  jle     short loc_18002F3A5
0x18002f39a  lea     rcx, [rsp+68h+var_48]; this
0x18002f39f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18002f3a4  nop
0x18002f3a5  mov     rcx, [rsp+68h+var_18]
0x18002f3aa  xor     rcx, rsp; StackCookie
0x18002f3ad  call    __security_check_cookie
0x18002f3b2  add     rsp, 68h
0x18002f3b6  retn
```
