# McGenControlCallbackV2

- ea: `0x14000ebf0`
- end: `0x14000ecf0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002bc6`
- `0x14000ebf0`

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
0x14000ebf0  push    rbx
0x14000ebf2  sub     rsp, 20h
0x14000ebf6  mov     r10, [rsp+28h+CallbackContext]
0x14000ebfb  xor     ebx, ebx
0x14000ebfd  test    r10, r10
0x14000ec00  jz      loc_14000ECEA
0x14000ec06  test    edx, edx
0x14000ec08  jz      loc_14000ECAF
0x14000ec0e  cmp     edx, 1
0x14000ec11  jnz     loc_14000ECEA
0x14000ec17  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000ec1c  mov     [r10+28h], r8b
0x14000ec20  mov     r8d, ebx
0x14000ec23  mov     [r10+18h], rax
0x14000ec27  mov     [r10+10h], r9
0x14000ec2b  mov     [r10+24h], edx
0x14000ec2f  cmp     bx, [r10+2Ah]
0x14000ec34  jnb     loc_14000ECEA
0x14000ec3a  mov     rax, [r10+40h]
0x14000ec3e  mov     cl, [r10+28h]
0x14000ec42  mov     r9d, r8d
0x14000ec45  cmp     [r9+rax], cl
0x14000ec49  jbe     short loc_14000EC4F
0x14000ec4b  test    cl, cl
0x14000ec4d  jnz     short loc_14000EC6F
0x14000ec4f  mov     rax, [r10+38h]
0x14000ec53  mov     rcx, [rax+r9*8]
0x14000ec57  test    rcx, rcx
0x14000ec5a  jz      short loc_14000EC74
0x14000ec5c  test    [r10+10h], rcx
0x14000ec60  jz      short loc_14000EC6F
0x14000ec62  mov     rax, [r10+18h]
0x14000ec66  and     rax, rcx
0x14000ec69  cmp     rax, [r10+18h]
0x14000ec6d  jz      short loc_14000EC74
0x14000ec6f  mov     r11b, bl
0x14000ec72  jmp     short loc_14000EC77
0x14000ec74  mov     r11b, 1
0x14000ec77  mov     rax, [r10+30h]
0x14000ec7b  mov     ecx, r8d
0x14000ec7e  shr     r9, 5
0x14000ec82  mov     edx, 1
0x14000ec87  shl     edx, cl
0x14000ec89  lea     rcx, [rax+r9*4]
0x14000ec8d  test    r11b, r11b
0x14000ec90  jz      short loc_14000EC96
0x14000ec92  or      edx, [rcx]
0x14000ec94  jmp     short loc_14000EC9A
0x14000ec96  not     edx
0x14000ec98  and     edx, [rcx]
0x14000ec9a  mov     [rcx], edx
0x14000ec9c  inc     r8d
0x14000ec9f  movzx   eax, word ptr [r10+2Ah]
0x14000eca4  cmp     r8d, eax
0x14000eca7  jb      short loc_14000EC3A
0x14000eca9  add     rsp, 20h
0x14000ecad  pop     rbx
0x14000ecae  retn
0x14000ecaf  mov     [r10+24h], ebx
0x14000ecb3  mov     [r10+28h], bl
0x14000ecb7  mov     [r10+10h], rbx
0x14000ecbb  mov     [r10+18h], rbx
0x14000ecbf  cmp     [r10+2Ah], bx
0x14000ecc4  jbe     short loc_14000ECEA
0x14000ecc6  movzx   eax, word ptr [r10+2Ah]
0x14000eccb  mov     rcx, [r10+30h]; void *
0x14000eccf  dec     eax
0x14000ecd1  cdq
0x14000ecd2  and     edx, 1Fh
0x14000ecd5  add     eax, edx
0x14000ecd7  xor     edx, edx; Val
0x14000ecd9  sar     eax, 5
0x14000ecdc  inc     eax
0x14000ecde  movsxd  r8, eax
0x14000ece1  shl     r8, 2; Size
0x14000ece5  call    memset_0
0x14000ecea  add     rsp, 20h
0x14000ecee  pop     rbx
0x14000ecef  retn
```
