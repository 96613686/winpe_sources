# wil_details_RecordCachedUsage

- ea: `0x14000a374`
- end: `0x14000a4c2`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140041890`

## callees

- `0x14000a374`
- `0x14000ba20`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000a4a3`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000a4a3`

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
0x14000a374  sub     rsp, 68h
0x14000a378  mov     rax, cs:__security_cookie
0x14000a37f  xor     rax, rsp
0x14000a382  mov     [rsp+68h+var_18], rax
0x14000a387  mov     r9, rdx
0x14000a38a  mov     r10d, ecx
0x14000a38d  prefetchw byte ptr [rdx]
0x14000a390  mov     eax, [rdx]
0x14000a392  mov     r8d, eax
0x14000a395  and     r8d, 0FFC0401Eh
0x14000a39c  lock cmpxchg [rdx], r8d
0x14000a3a1  jnz     short loc_14000A392
0x14000a3a3  mov     r8d, eax
0x14000a3a6  mov     ecx, eax
0x14000a3a8  shr     r8d, 1
0x14000a3ab  and     r8d, 0Fh
0x14000a3af  jz      short loc_14000A3CC
0x14000a3b1  prefetchw byte ptr [rdx+4]
0x14000a3b5  mov     eax, [rdx+4]
0x14000a3b8  mov     edx, eax
0x14000a3ba  or      edx, r8d
0x14000a3bd  lock cmpxchg [r9+4], edx
0x14000a3c3  jnz     short loc_14000A3B8
0x14000a3c5  not     eax
0x14000a3c7  and     eax, r8d
0x14000a3ca  jmp     short loc_14000A3CF
0x14000a3cc  mov     eax, r8d
0x14000a3cf  mov     r8d, 2
0x14000a3d5  lea     r9d, [r8-1]
0x14000a3d9  test    r9b, al
0x14000a3dc  jz      short loc_14000A3F2
0x14000a3de  mov     [rsp+68h+var_48], r10d
0x14000a3e3  lea     rdx, [rsp+68h+var_40]
0x14000a3e8  mov     [rsp+68h+var_44], 10002h
0x14000a3f0  jmp     short loc_14000A3F7
0x14000a3f2  lea     rdx, [rsp+68h+var_48]
0x14000a3f7  test    r8b, al
0x14000a3fa  jz      short loc_14000A40A
0x14000a3fc  mov     [rdx], r10d
0x14000a3ff  mov     dword ptr [rdx+4], 10006h
0x14000a406  add     rdx, 8
0x14000a40a  test    al, 4
0x14000a40c  jz      short loc_14000A41C
0x14000a40e  mov     [rdx], r10d
0x14000a411  mov     dword ptr [rdx+4], 10003h
0x14000a418  add     rdx, 8
0x14000a41c  cmp     eax, 8
0x14000a41f  jb      short loc_14000A42F
0x14000a421  mov     [rdx], r10d
0x14000a424  mov     dword ptr [rdx+4], 10007h
0x14000a42b  add     rdx, 8
0x14000a42f  mov     r8d, ecx
0x14000a432  mov     r11d, 1FFh
0x14000a438  shr     r8d, 5
0x14000a43c  test    r11d, r8d
0x14000a43f  jz      short loc_14000A462
0x14000a441  and     r8w, r11w
0x14000a445  mov     [rdx], r10d
0x14000a448  mov     eax, ecx
0x14000a44a  mov     [rdx+6], r8w
0x14000a44f  shr     eax, 0Eh
0x14000a452  and     ax, r9w
0x14000a456  shl     ax, 2
0x14000a45a  mov     [rdx+4], ax
0x14000a45e  add     rdx, 8
0x14000a462  mov     eax, ecx
0x14000a464  shr     eax, 0Fh
0x14000a467  test    al, 7Fh
0x14000a469  jz      short loc_14000A48D
0x14000a46b  shr     ecx, 16h
0x14000a46e  and     ax, 7Fh
0x14000a472  and     cx, r9w
0x14000a476  mov     [rdx], r10d
0x14000a479  shl     cx, 2
0x14000a47d  add     cx, r9w
0x14000a481  mov     [rdx+6], ax
0x14000a485  mov     [rdx+4], cx
0x14000a489  add     rdx, 8
0x14000a48d  lea     rax, [rsp+68h+var_48]
0x14000a492  sub     rdx, rax
0x14000a495  sar     rdx, 3
0x14000a499  test    rdx, rdx
0x14000a49c  jle     short loc_14000A4AF
0x14000a49e  lea     rcx, [rsp+68h+var_48]
0x14000a4a3  call    cs:__imp_RtlRecordFeatureUsage
0x14000a4aa  nop     dword ptr [rax+rax+00h]
0x14000a4af  mov     rcx, [rsp+68h+var_18]
0x14000a4b4  xor     rcx, rsp; StackCookie
0x14000a4b7  call    __security_check_cookie
0x14000a4bc  add     rsp, 68h
0x14000a4c0  retn
```
