# wil_details_RecordCachedUsage

- ea: `0x14000a154`
- end: `0x14000a2a2`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140017de0`

## callees

- `0x14000a154`
- `0x14000da60`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000a283`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000a283`

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
0x14000a154  sub     rsp, 68h
0x14000a158  mov     rax, cs:__security_cookie
0x14000a15f  xor     rax, rsp
0x14000a162  mov     [rsp+68h+var_18], rax
0x14000a167  mov     r9, rdx
0x14000a16a  mov     r10d, ecx
0x14000a16d  prefetchw byte ptr [rdx]
0x14000a170  mov     eax, [rdx]
0x14000a172  mov     r8d, eax
0x14000a175  and     r8d, 0FFC0401Eh
0x14000a17c  lock cmpxchg [rdx], r8d
0x14000a181  jnz     short loc_14000A172
0x14000a183  mov     r8d, eax
0x14000a186  mov     ecx, eax
0x14000a188  shr     r8d, 1
0x14000a18b  and     r8d, 0Fh
0x14000a18f  jz      short loc_14000A1AC
0x14000a191  prefetchw byte ptr [rdx+4]
0x14000a195  mov     eax, [rdx+4]
0x14000a198  mov     edx, eax
0x14000a19a  or      edx, r8d
0x14000a19d  lock cmpxchg [r9+4], edx
0x14000a1a3  jnz     short loc_14000A198
0x14000a1a5  not     eax
0x14000a1a7  and     eax, r8d
0x14000a1aa  jmp     short loc_14000A1AF
0x14000a1ac  mov     eax, r8d
0x14000a1af  mov     r8d, 2
0x14000a1b5  lea     r9d, [r8-1]
0x14000a1b9  test    r9b, al
0x14000a1bc  jz      short loc_14000A1D2
0x14000a1be  mov     [rsp+68h+var_48], r10d
0x14000a1c3  lea     rdx, [rsp+68h+var_40]
0x14000a1c8  mov     [rsp+68h+var_44], 10002h
0x14000a1d0  jmp     short loc_14000A1D7
0x14000a1d2  lea     rdx, [rsp+68h+var_48]
0x14000a1d7  test    r8b, al
0x14000a1da  jz      short loc_14000A1EA
0x14000a1dc  mov     [rdx], r10d
0x14000a1df  mov     dword ptr [rdx+4], 10006h
0x14000a1e6  add     rdx, 8
0x14000a1ea  test    al, 4
0x14000a1ec  jz      short loc_14000A1FC
0x14000a1ee  mov     [rdx], r10d
0x14000a1f1  mov     dword ptr [rdx+4], 10003h
0x14000a1f8  add     rdx, 8
0x14000a1fc  cmp     eax, 8
0x14000a1ff  jb      short loc_14000A20F
0x14000a201  mov     [rdx], r10d
0x14000a204  mov     dword ptr [rdx+4], 10007h
0x14000a20b  add     rdx, 8
0x14000a20f  mov     r8d, ecx
0x14000a212  mov     r11d, 1FFh
0x14000a218  shr     r8d, 5
0x14000a21c  test    r11d, r8d
0x14000a21f  jz      short loc_14000A242
0x14000a221  and     r8w, r11w
0x14000a225  mov     [rdx], r10d
0x14000a228  mov     eax, ecx
0x14000a22a  mov     [rdx+6], r8w
0x14000a22f  shr     eax, 0Eh
0x14000a232  and     ax, r9w
0x14000a236  shl     ax, 2
0x14000a23a  mov     [rdx+4], ax
0x14000a23e  add     rdx, 8
0x14000a242  mov     eax, ecx
0x14000a244  shr     eax, 0Fh
0x14000a247  test    al, 7Fh
0x14000a249  jz      short loc_14000A26D
0x14000a24b  shr     ecx, 16h
0x14000a24e  and     ax, 7Fh
0x14000a252  and     cx, r9w
0x14000a256  mov     [rdx], r10d
0x14000a259  shl     cx, 2
0x14000a25d  add     cx, r9w
0x14000a261  mov     [rdx+6], ax
0x14000a265  mov     [rdx+4], cx
0x14000a269  add     rdx, 8
0x14000a26d  lea     rax, [rsp+68h+var_48]
0x14000a272  sub     rdx, rax
0x14000a275  sar     rdx, 3
0x14000a279  test    rdx, rdx
0x14000a27c  jle     short loc_14000A28F
0x14000a27e  lea     rcx, [rsp+68h+var_48]
0x14000a283  call    cs:__imp_RtlRecordFeatureUsage
0x14000a28a  nop     dword ptr [rax+rax+00h]
0x14000a28f  mov     rcx, [rsp+68h+var_18]
0x14000a294  xor     rcx, rsp; StackCookie
0x14000a297  call    __security_check_cookie
0x14000a29c  add     rsp, 68h
0x14000a2a0  retn
```
