# McGenControlCallbackV2

- ea: `0x140001c90`
- end: `0x140001d90`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001c90`
- `0x140001fc9`

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
0x140001c90  push    rbx
0x140001c92  sub     rsp, 20h
0x140001c96  mov     r10, [rsp+28h+CallbackContext]
0x140001c9b  xor     ebx, ebx
0x140001c9d  test    r10, r10
0x140001ca0  jz      loc_140001D8A
0x140001ca6  test    edx, edx
0x140001ca8  jz      loc_140001D4F
0x140001cae  cmp     edx, 1
0x140001cb1  jnz     loc_140001D8A
0x140001cb7  mov     rax, [rsp+28h+MatchAllKeyword]
0x140001cbc  mov     [r10+28h], r8b
0x140001cc0  mov     r8d, ebx
0x140001cc3  mov     [r10+18h], rax
0x140001cc7  mov     [r10+10h], r9
0x140001ccb  mov     [r10+24h], edx
0x140001ccf  cmp     bx, [r10+2Ah]
0x140001cd4  jnb     loc_140001D8A
0x140001cda  mov     rax, [r10+40h]
0x140001cde  mov     cl, [r10+28h]
0x140001ce2  mov     r9d, r8d
0x140001ce5  cmp     [r9+rax], cl
0x140001ce9  jbe     short loc_140001CEF
0x140001ceb  test    cl, cl
0x140001ced  jnz     short loc_140001D0F
0x140001cef  mov     rax, [r10+38h]
0x140001cf3  mov     rcx, [rax+r9*8]
0x140001cf7  test    rcx, rcx
0x140001cfa  jz      short loc_140001D14
0x140001cfc  test    [r10+10h], rcx
0x140001d00  jz      short loc_140001D0F
0x140001d02  mov     rax, [r10+18h]
0x140001d06  and     rax, rcx
0x140001d09  cmp     rax, [r10+18h]
0x140001d0d  jz      short loc_140001D14
0x140001d0f  mov     r11b, bl
0x140001d12  jmp     short loc_140001D17
0x140001d14  mov     r11b, 1
0x140001d17  mov     rax, [r10+30h]
0x140001d1b  mov     ecx, r8d
0x140001d1e  shr     r9, 5
0x140001d22  mov     edx, 1
0x140001d27  shl     edx, cl
0x140001d29  lea     rcx, [rax+r9*4]
0x140001d2d  test    r11b, r11b
0x140001d30  jz      short loc_140001D36
0x140001d32  or      edx, [rcx]
0x140001d34  jmp     short loc_140001D3A
0x140001d36  not     edx
0x140001d38  and     edx, [rcx]
0x140001d3a  mov     [rcx], edx
0x140001d3c  inc     r8d
0x140001d3f  movzx   eax, word ptr [r10+2Ah]
0x140001d44  cmp     r8d, eax
0x140001d47  jb      short loc_140001CDA
0x140001d49  add     rsp, 20h
0x140001d4d  pop     rbx
0x140001d4e  retn
0x140001d4f  mov     [r10+24h], ebx
0x140001d53  mov     [r10+28h], bl
0x140001d57  mov     [r10+10h], rbx
0x140001d5b  mov     [r10+18h], rbx
0x140001d5f  cmp     [r10+2Ah], bx
0x140001d64  jbe     short loc_140001D8A
0x140001d66  movzx   eax, word ptr [r10+2Ah]
0x140001d6b  mov     rcx, [r10+30h]; void *
0x140001d6f  dec     eax
0x140001d71  cdq
0x140001d72  and     edx, 1Fh
0x140001d75  add     eax, edx
0x140001d77  xor     edx, edx; Val
0x140001d79  sar     eax, 5
0x140001d7c  inc     eax
0x140001d7e  movsxd  r8, eax
0x140001d81  shl     r8, 2; Size
0x140001d85  call    memset_0
0x140001d8a  add     rsp, 20h
0x140001d8e  pop     rbx
0x140001d8f  retn
```
