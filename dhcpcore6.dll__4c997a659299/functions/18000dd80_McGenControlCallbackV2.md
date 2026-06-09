# McGenControlCallbackV2

- ea: `0x18000dd80`
- end: `0x18000de6d`
- name: `McGenControlCallbackV2`
- size: `237`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dd80`
- `0x18001a3ee`

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
0x18000dd80  push    rbx
0x18000dd82  mov     r10, [rsp+8+CallbackContext]
0x18000dd87  xor     ebx, ebx
0x18000dd89  test    r10, r10
0x18000dd8c  jz      loc_18000DE1E
0x18000dd92  test    edx, edx
0x18000dd94  jz      loc_18000DE32
0x18000dd9a  cmp     edx, 1
0x18000dd9d  jnz     short loc_18000DE1E
0x18000dd9f  mov     rax, [rsp+8+MatchAllKeyword]
0x18000dda4  mov     [r10+28h], r8b
0x18000dda8  mov     r8d, ebx
0x18000ddab  mov     [r10+18h], rax
0x18000ddaf  mov     [r10+10h], r9
0x18000ddb3  mov     [r10+24h], edx
0x18000ddb7  cmp     bx, [r10+2Ah]
0x18000ddbc  jnb     short loc_18000DE1E
0x18000ddbe  mov     rax, [r10+40h]
0x18000ddc2  mov     cl, [r10+28h]
0x18000ddc6  mov     r9d, r8d
0x18000ddc9  cmp     [r9+rax], cl
0x18000ddcd  ja      short loc_18000DE2C
0x18000ddcf  mov     rax, [r10+38h]
0x18000ddd3  mov     rcx, [rax+r9*8]
0x18000ddd7  test    rcx, rcx
0x18000ddda  jz      short loc_18000DDEF
0x18000dddc  test    [r10+10h], rcx
0x18000dde0  jz      short loc_18000DE27
0x18000dde2  mov     rax, [r10+18h]
0x18000dde6  and     rax, rcx
0x18000dde9  cmp     rax, [r10+18h]
0x18000dded  jnz     short loc_18000DE27
0x18000ddef  mov     r11b, 1
0x18000ddf2  mov     rax, [r10+30h]
0x18000ddf6  mov     ecx, r8d
0x18000ddf9  shr     r9, 5
0x18000ddfd  mov     edx, 1
0x18000de02  shl     edx, cl
0x18000de04  lea     rcx, [rax+r9*4]
0x18000de08  test    r11b, r11b
0x18000de0b  jz      short loc_18000DE21
0x18000de0d  or      edx, [rcx]
0x18000de0f  mov     [rcx], edx
0x18000de11  inc     r8d
0x18000de14  movzx   eax, word ptr [r10+2Ah]
0x18000de19  cmp     r8d, eax
0x18000de1c  jb      short loc_18000DDBE
0x18000de1e  pop     rbx
0x18000de1f  retn
0x18000de21  not     edx
0x18000de23  and     edx, [rcx]
0x18000de25  jmp     short loc_18000DE0F
0x18000de27  mov     r11b, bl
0x18000de2a  jmp     short loc_18000DDF2
0x18000de2c  test    cl, cl
0x18000de2e  jnz     short loc_18000DE27
0x18000de30  jmp     short loc_18000DDCF
0x18000de32  mov     [r10+24h], ebx
0x18000de36  mov     [r10+28h], bl
0x18000de3a  mov     [r10+10h], rbx
0x18000de3e  mov     [r10+18h], rbx
0x18000de42  cmp     [r10+2Ah], bx
0x18000de47  jbe     short loc_18000DE1E
0x18000de49  movzx   eax, word ptr [r10+2Ah]
0x18000de4e  mov     ecx, 20h ; ' '
0x18000de53  dec     eax
0x18000de55  cdq
0x18000de56  idiv    ecx
0x18000de58  mov     rcx, [r10+30h]; void *
0x18000de5c  xor     edx, edx; Val
0x18000de5e  inc     eax
0x18000de60  movsxd  r8, eax
0x18000de63  shl     r8, 2; Size
0x18000de67  pop     rbx
0x18000de68  jmp     memset_0
```
