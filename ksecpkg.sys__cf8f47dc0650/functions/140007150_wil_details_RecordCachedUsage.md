# wil_details_RecordCachedUsage

- ea: `0x140007150`
- end: `0x140007297`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140020530`

## callees

- `0x140007150`
- `0x140010160`
- `0x140020584`

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
0x140007150  sub     rsp, 68h
0x140007154  mov     rax, cs:__security_cookie
0x14000715b  xor     rax, rsp
0x14000715e  mov     [rsp+68h+var_18], rax
0x140007163  mov     r9, rdx
0x140007166  mov     r10d, ecx
0x140007169  prefetchw byte ptr [rdx]
0x14000716c  mov     eax, [rdx]
0x14000716e  mov     r8d, eax
0x140007171  and     r8d, 0FFC0401Eh
0x140007178  lock cmpxchg [rdx], r8d
0x14000717d  jnz     short loc_14000716E
0x14000717f  mov     r8d, eax
0x140007182  mov     ecx, eax
0x140007184  shr     r8d, 1
0x140007187  and     r8d, 0Fh
0x14000718b  jz      short loc_1400071A8
0x14000718d  prefetchw byte ptr [rdx+4]
0x140007191  mov     eax, [rdx+4]
0x140007194  mov     edx, eax
0x140007196  or      edx, r8d
0x140007199  lock cmpxchg [r9+4], edx
0x14000719f  jnz     short loc_140007194
0x1400071a1  not     eax
0x1400071a3  and     eax, r8d
0x1400071a6  jmp     short loc_1400071AB
0x1400071a8  mov     eax, r8d
0x1400071ab  mov     r8d, 2
0x1400071b1  lea     r9d, [r8-1]
0x1400071b5  test    r9b, al
0x1400071b8  jz      short loc_1400071CE
0x1400071ba  mov     [rsp+68h+var_48], r10d
0x1400071bf  lea     rdx, [rsp+68h+var_40]
0x1400071c4  mov     [rsp+68h+var_44], 10002h
0x1400071cc  jmp     short loc_1400071D3
0x1400071ce  lea     rdx, [rsp+68h+var_48]
0x1400071d3  test    r8b, al
0x1400071d6  jz      short loc_1400071E6
0x1400071d8  mov     [rdx], r10d
0x1400071db  mov     dword ptr [rdx+4], 10006h
0x1400071e2  add     rdx, 8
0x1400071e6  test    al, 4
0x1400071e8  jz      short loc_1400071F8
0x1400071ea  mov     [rdx], r10d
0x1400071ed  mov     dword ptr [rdx+4], 10003h
0x1400071f4  add     rdx, 8
0x1400071f8  cmp     eax, 8
0x1400071fb  jb      short loc_14000720B
0x1400071fd  mov     [rdx], r10d
0x140007200  mov     dword ptr [rdx+4], 10007h
0x140007207  add     rdx, 8
0x14000720b  mov     r8d, ecx
0x14000720e  mov     r11d, 1FFh
0x140007214  shr     r8d, 5
0x140007218  test    r11d, r8d
0x14000721b  jz      short loc_14000723E
0x14000721d  and     r8w, r11w
0x140007221  mov     [rdx], r10d
0x140007224  mov     eax, ecx
0x140007226  mov     [rdx+6], r8w
0x14000722b  shr     eax, 0Eh
0x14000722e  and     ax, r9w
0x140007232  shl     ax, 2
0x140007236  mov     [rdx+4], ax
0x14000723a  add     rdx, 8
0x14000723e  mov     eax, ecx
0x140007240  shr     eax, 0Fh
0x140007243  test    al, 7Fh
0x140007245  jz      short loc_140007269
0x140007247  shr     ecx, 16h
0x14000724a  and     ax, 7Fh
0x14000724e  and     cx, r9w
0x140007252  mov     [rdx], r10d
0x140007255  shl     cx, 2
0x140007259  add     cx, r9w
0x14000725d  mov     [rdx+6], ax
0x140007261  mov     [rdx+4], cx
0x140007265  add     rdx, 8
0x140007269  lea     rax, [rsp+68h+var_48]
0x14000726e  sub     rdx, rax
0x140007271  sar     rdx, 3
0x140007275  test    rdx, rdx
0x140007278  jle     short loc_140007284
0x14000727a  lea     rcx, [rsp+68h+var_48]
0x14000727f  call    wil_details_RecordFeatureUsageCallback
0x140007284  mov     rcx, [rsp+68h+var_18]
0x140007289  xor     rcx, rsp; StackCookie
0x14000728c  call    __security_check_cookie
0x140007291  add     rsp, 68h
0x140007295  retn
```
