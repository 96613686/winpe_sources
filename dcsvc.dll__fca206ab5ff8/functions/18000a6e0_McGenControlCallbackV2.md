# McGenControlCallbackV2

- ea: `0x18000a6e0`
- end: `0x18000a7e0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800026c8`
- `0x18000a6e0`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        unsigned __int16 *CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rcx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // edx

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < CallbackContext[21]; ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          v10 = 0;
          if ( *(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8 )
          {
            v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
            if ( !v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
            {
              v10 = 1;
            }
          }
          v11 = 1 << v7;
          v12 = (int *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
          if ( v10 )
            v13 = *v12 | v11;
          else
            v13 = *v12 & ~v11;
          *v12 = v13;
        }
      }
    }
    else
    {
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( CallbackContext[21] )
        memset_0(*((void **)CallbackContext + 6), 0, 4LL * ((CallbackContext[21] - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x18000a6e0  push    rbx
0x18000a6e2  sub     rsp, 20h
0x18000a6e6  mov     r10, [rsp+28h+CallbackContext]
0x18000a6eb  xor     ebx, ebx
0x18000a6ed  test    r10, r10
0x18000a6f0  jz      loc_18000A7DA
0x18000a6f6  test    edx, edx
0x18000a6f8  jz      loc_18000A79F
0x18000a6fe  cmp     edx, 1
0x18000a701  jnz     loc_18000A7DA
0x18000a707  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000a70c  mov     [r10+28h], r8b
0x18000a710  mov     r8d, ebx
0x18000a713  mov     [r10+18h], rax
0x18000a717  mov     [r10+10h], r9
0x18000a71b  mov     [r10+24h], edx
0x18000a71f  cmp     bx, [r10+2Ah]
0x18000a724  jnb     loc_18000A7DA
0x18000a72a  mov     rax, [r10+40h]
0x18000a72e  mov     cl, [r10+28h]
0x18000a732  mov     r9d, r8d
0x18000a735  cmp     [r9+rax], cl
0x18000a739  jbe     short loc_18000A73F
0x18000a73b  test    cl, cl
0x18000a73d  jnz     short loc_18000A75F
0x18000a73f  mov     rax, [r10+38h]
0x18000a743  mov     rcx, [rax+r9*8]
0x18000a747  test    rcx, rcx
0x18000a74a  jz      short loc_18000A764
0x18000a74c  test    [r10+10h], rcx
0x18000a750  jz      short loc_18000A75F
0x18000a752  mov     rax, [r10+18h]
0x18000a756  and     rax, rcx
0x18000a759  cmp     rax, [r10+18h]
0x18000a75d  jz      short loc_18000A764
0x18000a75f  mov     r11b, bl
0x18000a762  jmp     short loc_18000A767
0x18000a764  mov     r11b, 1
0x18000a767  mov     rax, [r10+30h]
0x18000a76b  mov     ecx, r8d
0x18000a76e  shr     r9, 5
0x18000a772  mov     edx, 1
0x18000a777  shl     edx, cl
0x18000a779  lea     rcx, [rax+r9*4]
0x18000a77d  test    r11b, r11b
0x18000a780  jz      short loc_18000A786
0x18000a782  or      edx, [rcx]
0x18000a784  jmp     short loc_18000A78A
0x18000a786  not     edx
0x18000a788  and     edx, [rcx]
0x18000a78a  mov     [rcx], edx
0x18000a78c  inc     r8d
0x18000a78f  movzx   eax, word ptr [r10+2Ah]
0x18000a794  cmp     r8d, eax
0x18000a797  jb      short loc_18000A72A
0x18000a799  add     rsp, 20h
0x18000a79d  pop     rbx
0x18000a79e  retn
0x18000a79f  mov     [r10+24h], ebx
0x18000a7a3  mov     [r10+28h], bl
0x18000a7a7  mov     [r10+10h], rbx
0x18000a7ab  mov     [r10+18h], rbx
0x18000a7af  cmp     [r10+2Ah], bx
0x18000a7b4  jbe     short loc_18000A7DA
0x18000a7b6  movzx   eax, word ptr [r10+2Ah]
0x18000a7bb  mov     rcx, [r10+30h]; void *
0x18000a7bf  dec     eax
0x18000a7c1  cdq
0x18000a7c2  and     edx, 1Fh
0x18000a7c5  add     eax, edx
0x18000a7c7  xor     edx, edx; Val
0x18000a7c9  sar     eax, 5
0x18000a7cc  inc     eax
0x18000a7ce  movsxd  r8, eax
0x18000a7d1  shl     r8, 2; Size
0x18000a7d5  call    memset_0
0x18000a7da  add     rsp, 20h
0x18000a7de  pop     rbx
0x18000a7df  retn
```
