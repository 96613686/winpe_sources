# wil_details_RecordCachedUsage

- ea: `0x140004c4c`
- end: `0x140004d9a`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e9d0`

## callees

- `0x140004c4c`
- `0x140006630`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140004d7b`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140004d7b`

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
0x140004c4c  sub     rsp, 68h
0x140004c50  mov     rax, cs:__security_cookie
0x140004c57  xor     rax, rsp
0x140004c5a  mov     [rsp+68h+var_18], rax
0x140004c5f  mov     r9, rdx
0x140004c62  mov     r10d, ecx
0x140004c65  prefetchw byte ptr [rdx]
0x140004c68  mov     eax, [rdx]
0x140004c6a  mov     r8d, eax
0x140004c6d  and     r8d, 0FFC0401Eh
0x140004c74  lock cmpxchg [rdx], r8d
0x140004c79  jnz     short loc_140004C6A
0x140004c7b  mov     r8d, eax
0x140004c7e  mov     ecx, eax
0x140004c80  shr     r8d, 1
0x140004c83  and     r8d, 0Fh
0x140004c87  jz      short loc_140004CA4
0x140004c89  prefetchw byte ptr [rdx+4]
0x140004c8d  mov     eax, [rdx+4]
0x140004c90  mov     edx, eax
0x140004c92  or      edx, r8d
0x140004c95  lock cmpxchg [r9+4], edx
0x140004c9b  jnz     short loc_140004C90
0x140004c9d  not     eax
0x140004c9f  and     eax, r8d
0x140004ca2  jmp     short loc_140004CA7
0x140004ca4  mov     eax, r8d
0x140004ca7  mov     r8d, 2
0x140004cad  lea     r9d, [r8-1]
0x140004cb1  test    r9b, al
0x140004cb4  jz      short loc_140004CCA
0x140004cb6  mov     [rsp+68h+var_48], r10d
0x140004cbb  lea     rdx, [rsp+68h+var_40]
0x140004cc0  mov     [rsp+68h+var_44], 10002h
0x140004cc8  jmp     short loc_140004CCF
0x140004cca  lea     rdx, [rsp+68h+var_48]
0x140004ccf  test    r8b, al
0x140004cd2  jz      short loc_140004CE2
0x140004cd4  mov     [rdx], r10d
0x140004cd7  mov     dword ptr [rdx+4], 10006h
0x140004cde  add     rdx, 8
0x140004ce2  test    al, 4
0x140004ce4  jz      short loc_140004CF4
0x140004ce6  mov     [rdx], r10d
0x140004ce9  mov     dword ptr [rdx+4], 10003h
0x140004cf0  add     rdx, 8
0x140004cf4  cmp     eax, 8
0x140004cf7  jb      short loc_140004D07
0x140004cf9  mov     [rdx], r10d
0x140004cfc  mov     dword ptr [rdx+4], 10007h
0x140004d03  add     rdx, 8
0x140004d07  mov     r8d, ecx
0x140004d0a  mov     r11d, 1FFh
0x140004d10  shr     r8d, 5
0x140004d14  test    r11d, r8d
0x140004d17  jz      short loc_140004D3A
0x140004d19  and     r8w, r11w
0x140004d1d  mov     [rdx], r10d
0x140004d20  mov     eax, ecx
0x140004d22  mov     [rdx+6], r8w
0x140004d27  shr     eax, 0Eh
0x140004d2a  and     ax, r9w
0x140004d2e  shl     ax, 2
0x140004d32  mov     [rdx+4], ax
0x140004d36  add     rdx, 8
0x140004d3a  mov     eax, ecx
0x140004d3c  shr     eax, 0Fh
0x140004d3f  test    al, 7Fh
0x140004d41  jz      short loc_140004D65
0x140004d43  shr     ecx, 16h
0x140004d46  and     ax, 7Fh
0x140004d4a  and     cx, r9w
0x140004d4e  mov     [rdx], r10d
0x140004d51  shl     cx, 2
0x140004d55  add     cx, r9w
0x140004d59  mov     [rdx+6], ax
0x140004d5d  mov     [rdx+4], cx
0x140004d61  add     rdx, 8
0x140004d65  lea     rax, [rsp+68h+var_48]
0x140004d6a  sub     rdx, rax
0x140004d6d  sar     rdx, 3
0x140004d71  test    rdx, rdx
0x140004d74  jle     short loc_140004D87
0x140004d76  lea     rcx, [rsp+68h+var_48]
0x140004d7b  call    cs:__imp_RtlRecordFeatureUsage
0x140004d82  nop     dword ptr [rax+rax+00h]
0x140004d87  mov     rcx, [rsp+68h+var_18]
0x140004d8c  xor     rcx, rsp; StackCookie
0x140004d8f  call    __security_check_cookie
0x140004d94  add     rsp, 68h
0x140004d98  retn
```
