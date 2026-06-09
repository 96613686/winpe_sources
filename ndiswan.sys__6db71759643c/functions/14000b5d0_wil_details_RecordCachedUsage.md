# wil_details_RecordCachedUsage

- ea: `0x14000b5d0`
- end: `0x14000b71e`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400377b0`

## callees

- `0x14000b5d0`
- `0x1400161f0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000b6ff`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000b6ff`

## pseudocode

```c
_DWORD *__fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  _DWORD *result; // rax
  _DWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h] BYREF

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
    v10[0] = a1;
    v8 = &v11;
    v10[1] = 65538;
  }
  else
  {
    v8 = (char *)v10;
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
  if ( ((v3 >> 5) & 0x1FF) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 5) & 0x1FF;
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
  result = v10;
  if ( (v8 - (char *)v10) >> 3 > 0 )
    return (_DWORD *)RtlRecordFeatureUsage(v10);
  return result;
}

```

## disassembly

```asm
0x14000b5d0  sub     rsp, 68h
0x14000b5d4  mov     rax, cs:__security_cookie
0x14000b5db  xor     rax, rsp
0x14000b5de  mov     [rsp+68h+var_18], rax
0x14000b5e3  mov     r9, rdx
0x14000b5e6  mov     r10d, ecx
0x14000b5e9  prefetchw byte ptr [rdx]
0x14000b5ec  mov     eax, [rdx]
0x14000b5ee  mov     r8d, eax
0x14000b5f1  and     r8d, 0FFC0401Eh
0x14000b5f8  lock cmpxchg [rdx], r8d
0x14000b5fd  jnz     short loc_14000B5EE
0x14000b5ff  mov     r8d, eax
0x14000b602  mov     ecx, eax
0x14000b604  shr     r8d, 1
0x14000b607  and     r8d, 0Fh
0x14000b60b  jz      short loc_14000B628
0x14000b60d  prefetchw byte ptr [rdx+4]
0x14000b611  mov     eax, [rdx+4]
0x14000b614  mov     edx, eax
0x14000b616  or      edx, r8d
0x14000b619  lock cmpxchg [r9+4], edx
0x14000b61f  jnz     short loc_14000B614
0x14000b621  not     eax
0x14000b623  and     eax, r8d
0x14000b626  jmp     short loc_14000B62B
0x14000b628  mov     eax, r8d
0x14000b62b  mov     r8d, 2
0x14000b631  lea     r9d, [r8-1]
0x14000b635  test    r9b, al
0x14000b638  jz      short loc_14000B64E
0x14000b63a  mov     [rsp+68h+var_48], r10d
0x14000b63f  lea     rdx, [rsp+68h+var_40]
0x14000b644  mov     [rsp+68h+var_44], 10002h
0x14000b64c  jmp     short loc_14000B653
0x14000b64e  lea     rdx, [rsp+68h+var_48]
0x14000b653  test    r8b, al
0x14000b656  jz      short loc_14000B666
0x14000b658  mov     [rdx], r10d
0x14000b65b  mov     dword ptr [rdx+4], 10006h
0x14000b662  add     rdx, 8
0x14000b666  test    al, 4
0x14000b668  jz      short loc_14000B678
0x14000b66a  mov     [rdx], r10d
0x14000b66d  mov     dword ptr [rdx+4], 10003h
0x14000b674  add     rdx, 8
0x14000b678  cmp     eax, 8
0x14000b67b  jb      short loc_14000B68B
0x14000b67d  mov     [rdx], r10d
0x14000b680  mov     dword ptr [rdx+4], 10007h
0x14000b687  add     rdx, 8
0x14000b68b  mov     r8d, ecx
0x14000b68e  mov     r11d, 1FFh
0x14000b694  shr     r8d, 5
0x14000b698  test    r11d, r8d
0x14000b69b  jz      short loc_14000B6BE
0x14000b69d  and     r8w, r11w
0x14000b6a1  mov     [rdx], r10d
0x14000b6a4  mov     eax, ecx
0x14000b6a6  mov     [rdx+6], r8w
0x14000b6ab  shr     eax, 0Eh
0x14000b6ae  and     ax, r9w
0x14000b6b2  shl     ax, 2
0x14000b6b6  mov     [rdx+4], ax
0x14000b6ba  add     rdx, 8
0x14000b6be  mov     eax, ecx
0x14000b6c0  shr     eax, 0Fh
0x14000b6c3  test    al, 7Fh
0x14000b6c5  jz      short loc_14000B6E9
0x14000b6c7  shr     ecx, 16h
0x14000b6ca  and     ax, 7Fh
0x14000b6ce  and     cx, r9w
0x14000b6d2  mov     [rdx], r10d
0x14000b6d5  shl     cx, 2
0x14000b6d9  add     cx, r9w
0x14000b6dd  mov     [rdx+6], ax
0x14000b6e1  mov     [rdx+4], cx
0x14000b6e5  add     rdx, 8
0x14000b6e9  lea     rax, [rsp+68h+var_48]
0x14000b6ee  sub     rdx, rax
0x14000b6f1  sar     rdx, 3
0x14000b6f5  test    rdx, rdx
0x14000b6f8  jle     short loc_14000B70B
0x14000b6fa  lea     rcx, [rsp+68h+var_48]
0x14000b6ff  call    cs:__imp_RtlRecordFeatureUsage
0x14000b706  nop     dword ptr [rax+rax+00h]
0x14000b70b  mov     rcx, [rsp+68h+var_18]
0x14000b710  xor     rcx, rsp; StackCookie
0x14000b713  call    __security_check_cookie
0x14000b718  add     rsp, 68h
0x14000b71c  retn
```
