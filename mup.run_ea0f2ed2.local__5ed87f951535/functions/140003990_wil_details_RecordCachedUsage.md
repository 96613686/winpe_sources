# wil_details_RecordCachedUsage

- ea: `0x140003990`
- end: `0x140003ade`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011ef0`

## callees

- `0x140003990`
- `0x1400054a0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003abf`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003abf`

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
0x140003990  sub     rsp, 68h
0x140003994  mov     rax, cs:__security_cookie
0x14000399b  xor     rax, rsp
0x14000399e  mov     [rsp+68h+var_18], rax
0x1400039a3  mov     r9, rdx
0x1400039a6  mov     r10d, ecx
0x1400039a9  prefetchw byte ptr [rdx]
0x1400039ac  mov     eax, [rdx]
0x1400039ae  mov     r8d, eax
0x1400039b1  and     r8d, 0FFC0401Eh
0x1400039b8  lock cmpxchg [rdx], r8d
0x1400039bd  jnz     short loc_1400039AE
0x1400039bf  mov     r8d, eax
0x1400039c2  mov     ecx, eax
0x1400039c4  shr     r8d, 1
0x1400039c7  and     r8d, 0Fh
0x1400039cb  jz      short loc_1400039E8
0x1400039cd  prefetchw byte ptr [rdx+4]
0x1400039d1  mov     eax, [rdx+4]
0x1400039d4  mov     edx, eax
0x1400039d6  or      edx, r8d
0x1400039d9  lock cmpxchg [r9+4], edx
0x1400039df  jnz     short loc_1400039D4
0x1400039e1  not     eax
0x1400039e3  and     eax, r8d
0x1400039e6  jmp     short loc_1400039EB
0x1400039e8  mov     eax, r8d
0x1400039eb  mov     r8d, 2
0x1400039f1  lea     r9d, [r8-1]
0x1400039f5  test    r9b, al
0x1400039f8  jz      short loc_140003A0E
0x1400039fa  mov     [rsp+68h+var_48], r10d
0x1400039ff  lea     rdx, [rsp+68h+var_40]
0x140003a04  mov     [rsp+68h+var_44], 10002h
0x140003a0c  jmp     short loc_140003A13
0x140003a0e  lea     rdx, [rsp+68h+var_48]
0x140003a13  test    r8b, al
0x140003a16  jz      short loc_140003A26
0x140003a18  mov     [rdx], r10d
0x140003a1b  mov     dword ptr [rdx+4], 10006h
0x140003a22  add     rdx, 8
0x140003a26  test    al, 4
0x140003a28  jz      short loc_140003A38
0x140003a2a  mov     [rdx], r10d
0x140003a2d  mov     dword ptr [rdx+4], 10003h
0x140003a34  add     rdx, 8
0x140003a38  cmp     eax, 8
0x140003a3b  jb      short loc_140003A4B
0x140003a3d  mov     [rdx], r10d
0x140003a40  mov     dword ptr [rdx+4], 10007h
0x140003a47  add     rdx, 8
0x140003a4b  mov     r8d, ecx
0x140003a4e  mov     r11d, 1FFh
0x140003a54  shr     r8d, 5
0x140003a58  test    r11d, r8d
0x140003a5b  jz      short loc_140003A7E
0x140003a5d  and     r8w, r11w
0x140003a61  mov     [rdx], r10d
0x140003a64  mov     eax, ecx
0x140003a66  mov     [rdx+6], r8w
0x140003a6b  shr     eax, 0Eh
0x140003a6e  and     ax, r9w
0x140003a72  shl     ax, 2
0x140003a76  mov     [rdx+4], ax
0x140003a7a  add     rdx, 8
0x140003a7e  mov     eax, ecx
0x140003a80  shr     eax, 0Fh
0x140003a83  test    al, 7Fh
0x140003a85  jz      short loc_140003AA9
0x140003a87  shr     ecx, 16h
0x140003a8a  and     ax, 7Fh
0x140003a8e  and     cx, r9w
0x140003a92  mov     [rdx], r10d
0x140003a95  shl     cx, 2
0x140003a99  add     cx, r9w
0x140003a9d  mov     [rdx+6], ax
0x140003aa1  mov     [rdx+4], cx
0x140003aa5  add     rdx, 8
0x140003aa9  lea     rax, [rsp+68h+var_48]
0x140003aae  sub     rdx, rax
0x140003ab1  sar     rdx, 3
0x140003ab5  test    rdx, rdx
0x140003ab8  jle     short loc_140003ACB
0x140003aba  lea     rcx, [rsp+68h+var_48]
0x140003abf  call    cs:__imp_RtlRecordFeatureUsage
0x140003ac6  nop     dword ptr [rax+rax+00h]
0x140003acb  mov     rcx, [rsp+68h+var_18]
0x140003ad0  xor     rcx, rsp; StackCookie
0x140003ad3  call    __security_check_cookie
0x140003ad8  add     rsp, 68h
0x140003adc  retn
```
