# wil_details_RecordCachedUsage

- ea: `0x140001990`
- end: `0x140001ad7`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000aac0`

## callees

- `0x140001990`
- `0x140003690`
- `0x14000ab40`

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
    return (_DWORD *)wil_details_RecordFeatureUsageCallback(v10);
  return result;
}

```

## disassembly

```asm
0x140001990  sub     rsp, 68h
0x140001994  mov     rax, cs:__security_cookie
0x14000199b  xor     rax, rsp
0x14000199e  mov     [rsp+68h+var_18], rax
0x1400019a3  mov     r9, rdx
0x1400019a6  mov     r10d, ecx
0x1400019a9  prefetchw byte ptr [rdx]
0x1400019ac  mov     eax, [rdx]
0x1400019ae  mov     r8d, eax
0x1400019b1  and     r8d, 0FFC0401Eh
0x1400019b8  lock cmpxchg [rdx], r8d
0x1400019bd  jnz     short loc_1400019AE
0x1400019bf  mov     r8d, eax
0x1400019c2  mov     ecx, eax
0x1400019c4  shr     r8d, 1
0x1400019c7  and     r8d, 0Fh
0x1400019cb  jz      short loc_1400019E8
0x1400019cd  prefetchw byte ptr [rdx+4]
0x1400019d1  mov     eax, [rdx+4]
0x1400019d4  mov     edx, eax
0x1400019d6  or      edx, r8d
0x1400019d9  lock cmpxchg [r9+4], edx
0x1400019df  jnz     short loc_1400019D4
0x1400019e1  not     eax
0x1400019e3  and     eax, r8d
0x1400019e6  jmp     short loc_1400019EB
0x1400019e8  mov     eax, r8d
0x1400019eb  mov     r8d, 2
0x1400019f1  lea     r9d, [r8-1]
0x1400019f5  test    r9b, al
0x1400019f8  jz      short loc_140001A0E
0x1400019fa  mov     [rsp+68h+var_48], r10d
0x1400019ff  lea     rdx, [rsp+68h+var_40]
0x140001a04  mov     [rsp+68h+var_44], 10002h
0x140001a0c  jmp     short loc_140001A13
0x140001a0e  lea     rdx, [rsp+68h+var_48]
0x140001a13  test    r8b, al
0x140001a16  jz      short loc_140001A26
0x140001a18  mov     [rdx], r10d
0x140001a1b  mov     dword ptr [rdx+4], 10006h
0x140001a22  add     rdx, 8
0x140001a26  test    al, 4
0x140001a28  jz      short loc_140001A38
0x140001a2a  mov     [rdx], r10d
0x140001a2d  mov     dword ptr [rdx+4], 10003h
0x140001a34  add     rdx, 8
0x140001a38  cmp     eax, 8
0x140001a3b  jb      short loc_140001A4B
0x140001a3d  mov     [rdx], r10d
0x140001a40  mov     dword ptr [rdx+4], 10007h
0x140001a47  add     rdx, 8
0x140001a4b  mov     r8d, ecx
0x140001a4e  mov     r11d, 1FFh
0x140001a54  shr     r8d, 5
0x140001a58  test    r11d, r8d
0x140001a5b  jz      short loc_140001A7E
0x140001a5d  and     r8w, r11w
0x140001a61  mov     [rdx], r10d
0x140001a64  mov     eax, ecx
0x140001a66  mov     [rdx+6], r8w
0x140001a6b  shr     eax, 0Eh
0x140001a6e  and     ax, r9w
0x140001a72  shl     ax, 2
0x140001a76  mov     [rdx+4], ax
0x140001a7a  add     rdx, 8
0x140001a7e  mov     eax, ecx
0x140001a80  shr     eax, 0Fh
0x140001a83  test    al, 7Fh
0x140001a85  jz      short loc_140001AA9
0x140001a87  shr     ecx, 16h
0x140001a8a  and     ax, 7Fh
0x140001a8e  and     cx, r9w
0x140001a92  mov     [rdx], r10d
0x140001a95  shl     cx, 2
0x140001a99  add     cx, r9w
0x140001a9d  mov     [rdx+6], ax
0x140001aa1  mov     [rdx+4], cx
0x140001aa5  add     rdx, 8
0x140001aa9  lea     rax, [rsp+68h+var_48]
0x140001aae  sub     rdx, rax
0x140001ab1  sar     rdx, 3
0x140001ab5  test    rdx, rdx
0x140001ab8  jle     short loc_140001AC4
0x140001aba  lea     rcx, [rsp+68h+var_48]
0x140001abf  call    wil_details_RecordFeatureUsageCallback
0x140001ac4  mov     rcx, [rsp+68h+var_18]
0x140001ac9  xor     rcx, rsp; StackCookie
0x140001acc  call    __security_check_cookie
0x140001ad1  add     rsp, 68h
0x140001ad5  retn
```
