# wil_details_RecordCachedUsage

- ea: `0x14000fb5c`
- end: `0x14000fcaa`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140033df0`

## callees

- `0x14000fb5c`
- `0x140016560`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000fc8b`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000fc8b`

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
0x14000fb5c  sub     rsp, 68h
0x14000fb60  mov     rax, cs:__security_cookie
0x14000fb67  xor     rax, rsp
0x14000fb6a  mov     [rsp+68h+var_18], rax
0x14000fb6f  mov     r9, rdx
0x14000fb72  mov     r10d, ecx
0x14000fb75  prefetchw byte ptr [rdx]
0x14000fb78  mov     eax, [rdx]
0x14000fb7a  mov     r8d, eax
0x14000fb7d  and     r8d, 0FFC0401Eh
0x14000fb84  lock cmpxchg [rdx], r8d
0x14000fb89  jnz     short loc_14000FB7A
0x14000fb8b  mov     r8d, eax
0x14000fb8e  mov     ecx, eax
0x14000fb90  shr     r8d, 1
0x14000fb93  and     r8d, 0Fh
0x14000fb97  jz      short loc_14000FBB4
0x14000fb99  prefetchw byte ptr [rdx+4]
0x14000fb9d  mov     eax, [rdx+4]
0x14000fba0  mov     edx, eax
0x14000fba2  or      edx, r8d
0x14000fba5  lock cmpxchg [r9+4], edx
0x14000fbab  jnz     short loc_14000FBA0
0x14000fbad  not     eax
0x14000fbaf  and     eax, r8d
0x14000fbb2  jmp     short loc_14000FBB7
0x14000fbb4  mov     eax, r8d
0x14000fbb7  mov     r8d, 2
0x14000fbbd  lea     r9d, [r8-1]
0x14000fbc1  test    r9b, al
0x14000fbc4  jz      short loc_14000FBDA
0x14000fbc6  mov     [rsp+68h+var_48], r10d
0x14000fbcb  lea     rdx, [rsp+68h+var_40]
0x14000fbd0  mov     [rsp+68h+var_44], 10002h
0x14000fbd8  jmp     short loc_14000FBDF
0x14000fbda  lea     rdx, [rsp+68h+var_48]
0x14000fbdf  test    r8b, al
0x14000fbe2  jz      short loc_14000FBF2
0x14000fbe4  mov     [rdx], r10d
0x14000fbe7  mov     dword ptr [rdx+4], 10006h
0x14000fbee  add     rdx, 8
0x14000fbf2  test    al, 4
0x14000fbf4  jz      short loc_14000FC04
0x14000fbf6  mov     [rdx], r10d
0x14000fbf9  mov     dword ptr [rdx+4], 10003h
0x14000fc00  add     rdx, 8
0x14000fc04  cmp     eax, 8
0x14000fc07  jb      short loc_14000FC17
0x14000fc09  mov     [rdx], r10d
0x14000fc0c  mov     dword ptr [rdx+4], 10007h
0x14000fc13  add     rdx, 8
0x14000fc17  mov     r8d, ecx
0x14000fc1a  mov     r11d, 1FFh
0x14000fc20  shr     r8d, 5
0x14000fc24  test    r11d, r8d
0x14000fc27  jz      short loc_14000FC4A
0x14000fc29  and     r8w, r11w
0x14000fc2d  mov     [rdx], r10d
0x14000fc30  mov     eax, ecx
0x14000fc32  mov     [rdx+6], r8w
0x14000fc37  shr     eax, 0Eh
0x14000fc3a  and     ax, r9w
0x14000fc3e  shl     ax, 2
0x14000fc42  mov     [rdx+4], ax
0x14000fc46  add     rdx, 8
0x14000fc4a  mov     eax, ecx
0x14000fc4c  shr     eax, 0Fh
0x14000fc4f  test    al, 7Fh
0x14000fc51  jz      short loc_14000FC75
0x14000fc53  shr     ecx, 16h
0x14000fc56  and     ax, 7Fh
0x14000fc5a  and     cx, r9w
0x14000fc5e  mov     [rdx], r10d
0x14000fc61  shl     cx, 2
0x14000fc65  add     cx, r9w
0x14000fc69  mov     [rdx+6], ax
0x14000fc6d  mov     [rdx+4], cx
0x14000fc71  add     rdx, 8
0x14000fc75  lea     rax, [rsp+68h+var_48]
0x14000fc7a  sub     rdx, rax
0x14000fc7d  sar     rdx, 3
0x14000fc81  test    rdx, rdx
0x14000fc84  jle     short loc_14000FC97
0x14000fc86  lea     rcx, [rsp+68h+var_48]
0x14000fc8b  call    cs:__imp_RtlRecordFeatureUsage
0x14000fc92  nop     dword ptr [rax+rax+00h]
0x14000fc97  mov     rcx, [rsp+68h+var_18]
0x14000fc9c  xor     rcx, rsp; StackCookie
0x14000fc9f  call    __security_check_cookie
0x14000fca4  add     rsp, 68h
0x14000fca8  retn
```
