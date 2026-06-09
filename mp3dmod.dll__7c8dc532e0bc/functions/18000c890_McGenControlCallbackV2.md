# McGenControlCallbackV2

- ea: `0x18000c890`
- end: `0x18000c983`
- name: `McGenControlCallbackV2`
- size: `243`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c890`
- `0x18000efc8`

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
0x18000c890  push    rbx
0x18000c892  mov     r10, [rsp+8+CallbackContext]
0x18000c897  xor     ebx, ebx
0x18000c899  test    r10, r10
0x18000c89c  jnz     short loc_18000C8A0
0x18000c89e  pop     rbx
0x18000c89f  retn
0x18000c8a0  test    edx, edx
0x18000c8a2  jz      loc_18000C944
0x18000c8a8  cmp     edx, 1
0x18000c8ab  jnz     short loc_18000C89E
0x18000c8ad  mov     rax, [rsp+8+MatchAllKeyword]
0x18000c8b2  mov     [r10+28h], r8b
0x18000c8b6  mov     r8d, ebx
0x18000c8b9  mov     [r10+18h], rax
0x18000c8bd  mov     [r10+10h], r9
0x18000c8c1  mov     [r10+24h], edx
0x18000c8c5  cmp     bx, [r10+2Ah]
0x18000c8ca  jnb     short loc_18000C89E
0x18000c8cc  mov     rax, [r10+40h]
0x18000c8d0  mov     cl, [r10+28h]
0x18000c8d4  mov     r9d, r8d
0x18000c8d7  cmp     [r9+rax], cl
0x18000c8db  ja      short loc_18000C92F
0x18000c8dd  mov     rax, [r10+38h]
0x18000c8e1  mov     rcx, [rax+r9*8]
0x18000c8e5  test    rcx, rcx
0x18000c8e8  jz      short loc_18000C92A
0x18000c8ea  test    [r10+10h], rcx
0x18000c8ee  jnz     short loc_18000C935
0x18000c8f0  mov     r11b, bl
0x18000c8f3  mov     rax, [r10+30h]
0x18000c8f7  mov     ecx, r8d
0x18000c8fa  shr     r9, 5
0x18000c8fe  mov     edx, 1
0x18000c903  shl     edx, cl
0x18000c905  lea     rcx, [rax+r9*4]
0x18000c909  test    r11b, r11b
0x18000c90c  jz      short loc_18000C924
0x18000c90e  or      edx, [rcx]
0x18000c910  mov     [rcx], edx
0x18000c912  inc     r8d
0x18000c915  movzx   eax, word ptr [r10+2Ah]
0x18000c91a  cmp     r8d, eax
0x18000c91d  jb      short loc_18000C8CC
0x18000c91f  jmp     loc_18000C89E
0x18000c924  not     edx
0x18000c926  and     edx, [rcx]
0x18000c928  jmp     short loc_18000C910
0x18000c92a  mov     r11b, 1
0x18000c92d  jmp     short loc_18000C8F3
0x18000c92f  test    cl, cl
0x18000c931  jnz     short loc_18000C8F0
0x18000c933  jmp     short loc_18000C8DD
0x18000c935  mov     rax, [r10+18h]
0x18000c939  and     rax, rcx
0x18000c93c  cmp     rax, [r10+18h]
0x18000c940  jz      short loc_18000C92A
0x18000c942  jmp     short loc_18000C8F0
0x18000c944  mov     [r10+24h], ebx
0x18000c948  mov     [r10+28h], bl
0x18000c94c  mov     [r10+10h], rbx
0x18000c950  mov     [r10+18h], rbx
0x18000c954  cmp     [r10+2Ah], bx
0x18000c959  jbe     loc_18000C89E
0x18000c95f  movzx   eax, word ptr [r10+2Ah]
0x18000c964  mov     ecx, 20h ; ' '
0x18000c969  dec     eax
0x18000c96b  cdq
0x18000c96c  idiv    ecx
0x18000c96e  mov     rcx, [r10+30h]; void *
0x18000c972  xor     edx, edx; Val
0x18000c974  inc     eax
0x18000c976  movsxd  r8, eax
0x18000c979  shl     r8, 2; Size
0x18000c97d  pop     rbx
0x18000c97e  jmp     memset_0
```
