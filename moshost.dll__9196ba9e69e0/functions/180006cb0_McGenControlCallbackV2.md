# McGenControlCallbackV2

- ea: `0x180006cb0`
- end: `0x180006db0`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002722`
- `0x180006cb0`

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
0x180006cb0  push    rbx
0x180006cb2  sub     rsp, 20h
0x180006cb6  mov     r10, [rsp+28h+CallbackContext]
0x180006cbb  xor     ebx, ebx
0x180006cbd  test    r10, r10
0x180006cc0  jz      loc_180006DAA
0x180006cc6  test    edx, edx
0x180006cc8  jz      loc_180006D6F
0x180006cce  cmp     edx, 1
0x180006cd1  jnz     loc_180006DAA
0x180006cd7  mov     rax, [rsp+28h+MatchAllKeyword]
0x180006cdc  mov     [r10+28h], r8b
0x180006ce0  mov     r8d, ebx
0x180006ce3  mov     [r10+18h], rax
0x180006ce7  mov     [r10+10h], r9
0x180006ceb  mov     [r10+24h], edx
0x180006cef  cmp     bx, [r10+2Ah]
0x180006cf4  jnb     loc_180006DAA
0x180006cfa  mov     rax, [r10+40h]
0x180006cfe  mov     cl, [r10+28h]
0x180006d02  mov     r9d, r8d
0x180006d05  cmp     [r9+rax], cl
0x180006d09  jbe     short loc_180006D0F
0x180006d0b  test    cl, cl
0x180006d0d  jnz     short loc_180006D2F
0x180006d0f  mov     rax, [r10+38h]
0x180006d13  mov     rcx, [rax+r9*8]
0x180006d17  test    rcx, rcx
0x180006d1a  jz      short loc_180006D34
0x180006d1c  test    [r10+10h], rcx
0x180006d20  jz      short loc_180006D2F
0x180006d22  mov     rax, [r10+18h]
0x180006d26  and     rax, rcx
0x180006d29  cmp     rax, [r10+18h]
0x180006d2d  jz      short loc_180006D34
0x180006d2f  mov     r11b, bl
0x180006d32  jmp     short loc_180006D37
0x180006d34  mov     r11b, 1
0x180006d37  mov     rax, [r10+30h]
0x180006d3b  mov     ecx, r8d
0x180006d3e  shr     r9, 5
0x180006d42  mov     edx, 1
0x180006d47  shl     edx, cl
0x180006d49  lea     rcx, [rax+r9*4]
0x180006d4d  test    r11b, r11b
0x180006d50  jz      short loc_180006D56
0x180006d52  or      edx, [rcx]
0x180006d54  jmp     short loc_180006D5A
0x180006d56  not     edx
0x180006d58  and     edx, [rcx]
0x180006d5a  mov     [rcx], edx
0x180006d5c  inc     r8d
0x180006d5f  movzx   eax, word ptr [r10+2Ah]
0x180006d64  cmp     r8d, eax
0x180006d67  jb      short loc_180006CFA
0x180006d69  add     rsp, 20h
0x180006d6d  pop     rbx
0x180006d6e  retn
0x180006d6f  mov     [r10+24h], ebx
0x180006d73  mov     [r10+28h], bl
0x180006d77  mov     [r10+10h], rbx
0x180006d7b  mov     [r10+18h], rbx
0x180006d7f  cmp     [r10+2Ah], bx
0x180006d84  jbe     short loc_180006DAA
0x180006d86  movzx   eax, word ptr [r10+2Ah]
0x180006d8b  mov     rcx, [r10+30h]; void *
0x180006d8f  dec     eax
0x180006d91  cdq
0x180006d92  and     edx, 1Fh
0x180006d95  add     eax, edx
0x180006d97  xor     edx, edx; Val
0x180006d99  sar     eax, 5
0x180006d9c  inc     eax
0x180006d9e  movsxd  r8, eax
0x180006da1  shl     r8, 2; Size
0x180006da5  call    memset_0
0x180006daa  add     rsp, 20h
0x180006dae  pop     rbx
0x180006daf  retn
```
