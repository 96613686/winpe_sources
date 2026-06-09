# wil_details_RecordCachedUsage

- ea: `0x14000a5d8`
- end: `0x14000a726`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: `_DWORD *__fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400249e0`

## callees

- `0x14000a5d8`
- `0x14000bfa0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000a707`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000a707`

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
0x14000a5d8  sub     rsp, 68h
0x14000a5dc  mov     rax, cs:__security_cookie
0x14000a5e3  xor     rax, rsp
0x14000a5e6  mov     [rsp+68h+var_18], rax
0x14000a5eb  mov     r9, rdx
0x14000a5ee  mov     r10d, ecx
0x14000a5f1  prefetchw byte ptr [rdx]
0x14000a5f4  mov     eax, [rdx]
0x14000a5f6  mov     r8d, eax
0x14000a5f9  and     r8d, 0FFC0401Eh
0x14000a600  lock cmpxchg [rdx], r8d
0x14000a605  jnz     short loc_14000A5F6
0x14000a607  mov     r8d, eax
0x14000a60a  mov     ecx, eax
0x14000a60c  shr     r8d, 1
0x14000a60f  and     r8d, 0Fh
0x14000a613  jz      short loc_14000A630
0x14000a615  prefetchw byte ptr [rdx+4]
0x14000a619  mov     eax, [rdx+4]
0x14000a61c  mov     edx, eax
0x14000a61e  or      edx, r8d
0x14000a621  lock cmpxchg [r9+4], edx
0x14000a627  jnz     short loc_14000A61C
0x14000a629  not     eax
0x14000a62b  and     eax, r8d
0x14000a62e  jmp     short loc_14000A633
0x14000a630  mov     eax, r8d
0x14000a633  mov     r8d, 2
0x14000a639  lea     r9d, [r8-1]
0x14000a63d  test    r9b, al
0x14000a640  jz      short loc_14000A656
0x14000a642  mov     [rsp+68h+var_48], r10d
0x14000a647  lea     rdx, [rsp+68h+var_40]
0x14000a64c  mov     [rsp+68h+var_44], 10002h
0x14000a654  jmp     short loc_14000A65B
0x14000a656  lea     rdx, [rsp+68h+var_48]
0x14000a65b  test    r8b, al
0x14000a65e  jz      short loc_14000A66E
0x14000a660  mov     [rdx], r10d
0x14000a663  mov     dword ptr [rdx+4], 10006h
0x14000a66a  add     rdx, 8
0x14000a66e  test    al, 4
0x14000a670  jz      short loc_14000A680
0x14000a672  mov     [rdx], r10d
0x14000a675  mov     dword ptr [rdx+4], 10003h
0x14000a67c  add     rdx, 8
0x14000a680  cmp     eax, 8
0x14000a683  jb      short loc_14000A693
0x14000a685  mov     [rdx], r10d
0x14000a688  mov     dword ptr [rdx+4], 10007h
0x14000a68f  add     rdx, 8
0x14000a693  mov     r8d, ecx
0x14000a696  mov     r11d, 1FFh
0x14000a69c  shr     r8d, 5
0x14000a6a0  test    r11d, r8d
0x14000a6a3  jz      short loc_14000A6C6
0x14000a6a5  and     r8w, r11w
0x14000a6a9  mov     [rdx], r10d
0x14000a6ac  mov     eax, ecx
0x14000a6ae  mov     [rdx+6], r8w
0x14000a6b3  shr     eax, 0Eh
0x14000a6b6  and     ax, r9w
0x14000a6ba  shl     ax, 2
0x14000a6be  mov     [rdx+4], ax
0x14000a6c2  add     rdx, 8
0x14000a6c6  mov     eax, ecx
0x14000a6c8  shr     eax, 0Fh
0x14000a6cb  test    al, 7Fh
0x14000a6cd  jz      short loc_14000A6F1
0x14000a6cf  shr     ecx, 16h
0x14000a6d2  and     ax, 7Fh
0x14000a6d6  and     cx, r9w
0x14000a6da  mov     [rdx], r10d
0x14000a6dd  shl     cx, 2
0x14000a6e1  add     cx, r9w
0x14000a6e5  mov     [rdx+6], ax
0x14000a6e9  mov     [rdx+4], cx
0x14000a6ed  add     rdx, 8
0x14000a6f1  lea     rax, [rsp+68h+var_48]
0x14000a6f6  sub     rdx, rax
0x14000a6f9  sar     rdx, 3
0x14000a6fd  test    rdx, rdx
0x14000a700  jle     short loc_14000A713
0x14000a702  lea     rcx, [rsp+68h+var_48]
0x14000a707  call    cs:__imp_RtlRecordFeatureUsage
0x14000a70e  nop     dword ptr [rax+rax+00h]
0x14000a713  mov     rcx, [rsp+68h+var_18]
0x14000a718  xor     rcx, rsp; StackCookie
0x14000a71b  call    __security_check_cookie
0x14000a720  add     rsp, 68h
0x14000a724  retn
```
