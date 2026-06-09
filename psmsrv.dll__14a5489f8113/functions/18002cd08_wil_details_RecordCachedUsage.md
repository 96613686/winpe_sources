# wil_details_RecordCachedUsage

- ea: `0x18002cd08`
- end: `0x18002ce4e`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800199f4`

## callees

- `0x18001b7e0`
- `0x1800299a4`
- `0x18002cd08`

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
0x18002cd08  sub     rsp, 68h
0x18002cd0c  mov     rax, cs:__security_cookie
0x18002cd13  xor     rax, rsp
0x18002cd16  mov     [rsp+68h+var_18], rax
0x18002cd1b  mov     r9, rdx
0x18002cd1e  mov     r10d, ecx
0x18002cd21  prefetchw byte ptr [rdx]
0x18002cd24  mov     eax, [rdx]
0x18002cd26  mov     r8d, eax
0x18002cd29  and     r8d, 0FFC0401Eh
0x18002cd30  lock cmpxchg [rdx], r8d
0x18002cd35  jnz     short loc_18002CD26
0x18002cd37  mov     r8d, eax
0x18002cd3a  mov     ecx, eax
0x18002cd3c  shr     r8d, 1
0x18002cd3f  and     r8d, 0Fh
0x18002cd43  jz      short loc_18002CD60
0x18002cd45  prefetchw byte ptr [rdx+4]
0x18002cd49  mov     eax, [rdx+4]
0x18002cd4c  mov     edx, eax
0x18002cd4e  or      edx, r8d
0x18002cd51  lock cmpxchg [r9+4], edx
0x18002cd57  jnz     short loc_18002CD4C
0x18002cd59  not     eax
0x18002cd5b  and     eax, r8d
0x18002cd5e  jmp     short loc_18002CD63
0x18002cd60  mov     eax, r8d
0x18002cd63  mov     r8d, 2
0x18002cd69  lea     r9d, [r8-1]
0x18002cd6d  test    r9b, al
0x18002cd70  jz      short loc_18002CD86
0x18002cd72  mov     [rsp+68h+var_48], r10d
0x18002cd77  lea     rdx, [rsp+68h+var_40]
0x18002cd7c  mov     [rsp+68h+var_44], 10002h
0x18002cd84  jmp     short loc_18002CD8B
0x18002cd86  lea     rdx, [rsp+68h+var_48]
0x18002cd8b  test    r8b, al
0x18002cd8e  jz      short loc_18002CD9E
0x18002cd90  mov     [rdx], r10d
0x18002cd93  mov     dword ptr [rdx+4], 10006h
0x18002cd9a  add     rdx, 8
0x18002cd9e  test    al, 4
0x18002cda0  jz      short loc_18002CDB0
0x18002cda2  mov     [rdx], r10d
0x18002cda5  mov     dword ptr [rdx+4], 10003h
0x18002cdac  add     rdx, 8
0x18002cdb0  cmp     eax, 8
0x18002cdb3  jb      short loc_18002CDC3
0x18002cdb5  mov     [rdx], r10d
0x18002cdb8  mov     dword ptr [rdx+4], 10007h
0x18002cdbf  add     rdx, 8
0x18002cdc3  mov     r8d, ecx
0x18002cdc6  mov     r11d, 1FFh
0x18002cdcc  shr     r8d, 5
0x18002cdd0  test    r11d, r8d
0x18002cdd3  jz      short loc_18002CDF6
0x18002cdd5  and     r8w, r11w; unsigned __int64
0x18002cdd9  mov     [rdx], r10d
0x18002cddc  mov     eax, ecx
0x18002cdde  mov     [rdx+6], r8w
0x18002cde3  shr     eax, 0Eh
0x18002cde6  and     ax, r9w
0x18002cdea  shl     ax, 2
0x18002cdee  mov     [rdx+4], ax
0x18002cdf2  add     rdx, 8
0x18002cdf6  mov     eax, ecx
0x18002cdf8  shr     eax, 0Fh
0x18002cdfb  test    al, 7Fh
0x18002cdfd  jz      short loc_18002CE21
0x18002cdff  shr     ecx, 16h
0x18002ce02  and     ax, 7Fh
0x18002ce06  and     cx, r9w
0x18002ce0a  mov     [rdx], r10d
0x18002ce0d  shl     cx, 2
0x18002ce11  add     cx, r9w
0x18002ce15  mov     [rdx+6], ax
0x18002ce19  mov     [rdx+4], cx
0x18002ce1d  add     rdx, 8
0x18002ce21  lea     rax, [rsp+68h+var_48]
0x18002ce26  sub     rdx, rax
0x18002ce29  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18002ce2d  test    rdx, rdx
0x18002ce30  jle     short loc_18002CE3C
0x18002ce32  lea     rcx, [rsp+68h+var_48]; this
0x18002ce37  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18002ce3c  mov     rcx, [rsp+68h+var_18]
0x18002ce41  xor     rcx, rsp; StackCookie
0x18002ce44  call    __security_check_cookie
0x18002ce49  add     rsp, 68h
0x18002ce4d  retn
```
