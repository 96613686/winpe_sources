# wil_details_RecordCachedUsage

- ea: `0x18001e2a4`
- end: `0x18001e3f2`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180039410`

## callees

- `0x18001e2a4`
- `0x180027ba0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x18001e3d3`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x18001e3d3`

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
0x18001e2a4  sub     rsp, 68h
0x18001e2a8  mov     rax, cs:__security_cookie
0x18001e2af  xor     rax, rsp
0x18001e2b2  mov     [rsp+68h+var_18], rax
0x18001e2b7  mov     r9, rdx
0x18001e2ba  mov     r10d, ecx
0x18001e2bd  prefetchw byte ptr [rdx]
0x18001e2c0  mov     eax, [rdx]
0x18001e2c2  mov     r8d, eax
0x18001e2c5  and     r8d, 0FFC0401Eh
0x18001e2cc  lock cmpxchg [rdx], r8d
0x18001e2d1  jnz     short loc_18001E2C2
0x18001e2d3  mov     r8d, eax
0x18001e2d6  mov     ecx, eax
0x18001e2d8  shr     r8d, 1
0x18001e2db  and     r8d, 0Fh
0x18001e2df  jz      short loc_18001E2FC
0x18001e2e1  prefetchw byte ptr [rdx+4]
0x18001e2e5  mov     eax, [rdx+4]
0x18001e2e8  mov     edx, eax
0x18001e2ea  or      edx, r8d
0x18001e2ed  lock cmpxchg [r9+4], edx
0x18001e2f3  jnz     short loc_18001E2E8
0x18001e2f5  not     eax
0x18001e2f7  and     eax, r8d
0x18001e2fa  jmp     short loc_18001E2FF
0x18001e2fc  mov     eax, r8d
0x18001e2ff  mov     r8d, 2
0x18001e305  lea     r9d, [r8-1]
0x18001e309  test    r9b, al
0x18001e30c  jz      short loc_18001E322
0x18001e30e  mov     [rsp+68h+var_48], r10d
0x18001e313  lea     rdx, [rsp+68h+var_40]
0x18001e318  mov     [rsp+68h+var_44], 10002h
0x18001e320  jmp     short loc_18001E327
0x18001e322  lea     rdx, [rsp+68h+var_48]
0x18001e327  test    r8b, al
0x18001e32a  jz      short loc_18001E33A
0x18001e32c  mov     [rdx], r10d
0x18001e32f  mov     dword ptr [rdx+4], 10006h
0x18001e336  add     rdx, 8
0x18001e33a  test    al, 4
0x18001e33c  jz      short loc_18001E34C
0x18001e33e  mov     [rdx], r10d
0x18001e341  mov     dword ptr [rdx+4], 10003h
0x18001e348  add     rdx, 8
0x18001e34c  cmp     eax, 8
0x18001e34f  jb      short loc_18001E35F
0x18001e351  mov     [rdx], r10d
0x18001e354  mov     dword ptr [rdx+4], 10007h
0x18001e35b  add     rdx, 8
0x18001e35f  mov     r8d, ecx
0x18001e362  mov     r11d, 1FFh
0x18001e368  shr     r8d, 5
0x18001e36c  test    r11d, r8d
0x18001e36f  jz      short loc_18001E392
0x18001e371  and     r8w, r11w
0x18001e375  mov     [rdx], r10d
0x18001e378  mov     eax, ecx
0x18001e37a  mov     [rdx+6], r8w
0x18001e37f  shr     eax, 0Eh
0x18001e382  and     ax, r9w
0x18001e386  shl     ax, 2
0x18001e38a  mov     [rdx+4], ax
0x18001e38e  add     rdx, 8
0x18001e392  mov     eax, ecx
0x18001e394  shr     eax, 0Fh
0x18001e397  test    al, 7Fh
0x18001e399  jz      short loc_18001E3BD
0x18001e39b  shr     ecx, 16h
0x18001e39e  and     ax, 7Fh
0x18001e3a2  and     cx, r9w
0x18001e3a6  mov     [rdx], r10d
0x18001e3a9  shl     cx, 2
0x18001e3ad  add     cx, r9w
0x18001e3b1  mov     [rdx+6], ax
0x18001e3b5  mov     [rdx+4], cx
0x18001e3b9  add     rdx, 8
0x18001e3bd  lea     rax, [rsp+68h+var_48]
0x18001e3c2  sub     rdx, rax
0x18001e3c5  sar     rdx, 3
0x18001e3c9  test    rdx, rdx
0x18001e3cc  jle     short loc_18001E3DF
0x18001e3ce  lea     rcx, [rsp+68h+var_48]
0x18001e3d3  call    cs:__imp_RtlRecordFeatureUsage
0x18001e3da  nop     dword ptr [rax+rax+00h]
0x18001e3df  mov     rcx, [rsp+68h+var_18]
0x18001e3e4  xor     rcx, rsp; StackCookie
0x18001e3e7  call    __security_check_cookie
0x18001e3ec  add     rsp, 68h
0x18001e3f0  retn
```
