# wil_details_RecordCachedUsage

- ea: `0x14002d2d8`
- end: `0x14002d426`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140044f70`

## callees

- `0x14002d2d8`
- `0x140030f40`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14002d407`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14002d407`

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
0x14002d2d8  sub     rsp, 68h
0x14002d2dc  mov     rax, cs:__security_cookie
0x14002d2e3  xor     rax, rsp
0x14002d2e6  mov     [rsp+68h+var_18], rax
0x14002d2eb  mov     r9, rdx
0x14002d2ee  mov     r10d, ecx
0x14002d2f1  prefetchw byte ptr [rdx]
0x14002d2f4  mov     eax, [rdx]
0x14002d2f6  mov     r8d, eax
0x14002d2f9  and     r8d, 0FFC0401Eh
0x14002d300  lock cmpxchg [rdx], r8d
0x14002d305  jnz     short loc_14002D2F6
0x14002d307  mov     r8d, eax
0x14002d30a  mov     ecx, eax
0x14002d30c  shr     r8d, 1
0x14002d30f  and     r8d, 0Fh
0x14002d313  jz      short loc_14002D330
0x14002d315  prefetchw byte ptr [rdx+4]
0x14002d319  mov     eax, [rdx+4]
0x14002d31c  mov     edx, eax
0x14002d31e  or      edx, r8d
0x14002d321  lock cmpxchg [r9+4], edx
0x14002d327  jnz     short loc_14002D31C
0x14002d329  not     eax
0x14002d32b  and     eax, r8d
0x14002d32e  jmp     short loc_14002D333
0x14002d330  mov     eax, r8d
0x14002d333  mov     r8d, 2
0x14002d339  lea     r9d, [r8-1]
0x14002d33d  test    r9b, al
0x14002d340  jz      short loc_14002D356
0x14002d342  mov     [rsp+68h+var_48], r10d
0x14002d347  lea     rdx, [rsp+68h+var_40]
0x14002d34c  mov     [rsp+68h+var_44], 10002h
0x14002d354  jmp     short loc_14002D35B
0x14002d356  lea     rdx, [rsp+68h+var_48]
0x14002d35b  test    r8b, al
0x14002d35e  jz      short loc_14002D36E
0x14002d360  mov     [rdx], r10d
0x14002d363  mov     dword ptr [rdx+4], 10006h
0x14002d36a  add     rdx, 8
0x14002d36e  test    al, 4
0x14002d370  jz      short loc_14002D380
0x14002d372  mov     [rdx], r10d
0x14002d375  mov     dword ptr [rdx+4], 10003h
0x14002d37c  add     rdx, 8
0x14002d380  cmp     eax, 8
0x14002d383  jb      short loc_14002D393
0x14002d385  mov     [rdx], r10d
0x14002d388  mov     dword ptr [rdx+4], 10007h
0x14002d38f  add     rdx, 8
0x14002d393  mov     r8d, ecx
0x14002d396  mov     r11d, 1FFh
0x14002d39c  shr     r8d, 5
0x14002d3a0  test    r11d, r8d
0x14002d3a3  jz      short loc_14002D3C6
0x14002d3a5  and     r8w, r11w
0x14002d3a9  mov     [rdx], r10d
0x14002d3ac  mov     eax, ecx
0x14002d3ae  mov     [rdx+6], r8w
0x14002d3b3  shr     eax, 0Eh
0x14002d3b6  and     ax, r9w
0x14002d3ba  shl     ax, 2
0x14002d3be  mov     [rdx+4], ax
0x14002d3c2  add     rdx, 8
0x14002d3c6  mov     eax, ecx
0x14002d3c8  shr     eax, 0Fh
0x14002d3cb  test    al, 7Fh
0x14002d3cd  jz      short loc_14002D3F1
0x14002d3cf  shr     ecx, 16h
0x14002d3d2  and     ax, 7Fh
0x14002d3d6  and     cx, r9w
0x14002d3da  mov     [rdx], r10d
0x14002d3dd  shl     cx, 2
0x14002d3e1  add     cx, r9w
0x14002d3e5  mov     [rdx+6], ax
0x14002d3e9  mov     [rdx+4], cx
0x14002d3ed  add     rdx, 8
0x14002d3f1  lea     rax, [rsp+68h+var_48]
0x14002d3f6  sub     rdx, rax
0x14002d3f9  sar     rdx, 3
0x14002d3fd  test    rdx, rdx
0x14002d400  jle     short loc_14002D413
0x14002d402  lea     rcx, [rsp+68h+var_48]
0x14002d407  call    cs:__imp_RtlRecordFeatureUsage
0x14002d40e  nop     dword ptr [rax+rax+00h]
0x14002d413  mov     rcx, [rsp+68h+var_18]
0x14002d418  xor     rcx, rsp; StackCookie
0x14002d41b  call    __security_check_cookie
0x14002d420  add     rsp, 68h
0x14002d424  retn
```
