# wil_details_RecordCachedUsage

- ea: `0x18003e090`
- end: `0x18003e1d6`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003cc74`

## callees

- `0x180024220`
- `0x18003d93c`
- `0x18003e090`

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
0x18003e090  sub     rsp, 68h
0x18003e094  mov     rax, cs:__security_cookie
0x18003e09b  xor     rax, rsp
0x18003e09e  mov     [rsp+68h+var_18], rax
0x18003e0a3  mov     r9, rdx
0x18003e0a6  mov     r10d, ecx
0x18003e0a9  prefetchw byte ptr [rdx]
0x18003e0ac  mov     eax, [rdx]
0x18003e0ae  mov     r8d, eax
0x18003e0b1  and     r8d, 0FFC0401Eh
0x18003e0b8  lock cmpxchg [rdx], r8d
0x18003e0bd  jnz     short loc_18003E0AE
0x18003e0bf  mov     r8d, eax
0x18003e0c2  mov     ecx, eax
0x18003e0c4  shr     r8d, 1
0x18003e0c7  and     r8d, 0Fh
0x18003e0cb  jz      short loc_18003E0E8
0x18003e0cd  prefetchw byte ptr [rdx+4]
0x18003e0d1  mov     eax, [rdx+4]
0x18003e0d4  mov     edx, eax
0x18003e0d6  or      edx, r8d
0x18003e0d9  lock cmpxchg [r9+4], edx
0x18003e0df  jnz     short loc_18003E0D4
0x18003e0e1  not     eax
0x18003e0e3  and     eax, r8d
0x18003e0e6  jmp     short loc_18003E0EB
0x18003e0e8  mov     eax, r8d
0x18003e0eb  mov     r8d, 2
0x18003e0f1  lea     r9d, [r8-1]
0x18003e0f5  test    r9b, al
0x18003e0f8  jz      short loc_18003E10E
0x18003e0fa  mov     [rsp+68h+var_48], r10d
0x18003e0ff  lea     rdx, [rsp+68h+var_40]
0x18003e104  mov     [rsp+68h+var_44], 10002h
0x18003e10c  jmp     short loc_18003E113
0x18003e10e  lea     rdx, [rsp+68h+var_48]
0x18003e113  test    r8b, al
0x18003e116  jz      short loc_18003E126
0x18003e118  mov     [rdx], r10d
0x18003e11b  mov     dword ptr [rdx+4], 10006h
0x18003e122  add     rdx, 8
0x18003e126  test    al, 4
0x18003e128  jz      short loc_18003E138
0x18003e12a  mov     [rdx], r10d
0x18003e12d  mov     dword ptr [rdx+4], 10003h
0x18003e134  add     rdx, 8
0x18003e138  cmp     eax, 8
0x18003e13b  jb      short loc_18003E14B
0x18003e13d  mov     [rdx], r10d
0x18003e140  mov     dword ptr [rdx+4], 10007h
0x18003e147  add     rdx, 8
0x18003e14b  mov     r8d, ecx
0x18003e14e  mov     r11d, 1FFh
0x18003e154  shr     r8d, 5
0x18003e158  test    r11d, r8d
0x18003e15b  jz      short loc_18003E17E
0x18003e15d  and     r8w, r11w; unsigned __int64
0x18003e161  mov     [rdx], r10d
0x18003e164  mov     eax, ecx
0x18003e166  mov     [rdx+6], r8w
0x18003e16b  shr     eax, 0Eh
0x18003e16e  and     ax, r9w
0x18003e172  shl     ax, 2
0x18003e176  mov     [rdx+4], ax
0x18003e17a  add     rdx, 8
0x18003e17e  mov     eax, ecx
0x18003e180  shr     eax, 0Fh
0x18003e183  test    al, 7Fh
0x18003e185  jz      short loc_18003E1A9
0x18003e187  shr     ecx, 16h
0x18003e18a  and     ax, 7Fh
0x18003e18e  and     cx, r9w
0x18003e192  mov     [rdx], r10d
0x18003e195  shl     cx, 2
0x18003e199  add     cx, r9w
0x18003e19d  mov     [rdx+6], ax
0x18003e1a1  mov     [rdx+4], cx
0x18003e1a5  add     rdx, 8
0x18003e1a9  lea     rax, [rsp+68h+var_48]
0x18003e1ae  sub     rdx, rax
0x18003e1b1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18003e1b5  test    rdx, rdx
0x18003e1b8  jle     short loc_18003E1C4
0x18003e1ba  lea     rcx, [rsp+68h+var_48]; this
0x18003e1bf  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18003e1c4  mov     rcx, [rsp+68h+var_18]
0x18003e1c9  xor     rcx, rsp; StackCookie
0x18003e1cc  call    __security_check_cookie
0x18003e1d1  add     rsp, 68h
0x18003e1d5  retn
```
