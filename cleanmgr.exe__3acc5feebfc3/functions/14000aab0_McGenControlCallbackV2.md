# McGenControlCallbackV2

- ea: `0x14000aab0`
- end: `0x14000abaf`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003390`
- `0x14000aab0`

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
0x14000aab0  push    rbx
0x14000aab2  sub     rsp, 20h
0x14000aab6  mov     r10, [rsp+28h+CallbackContext]
0x14000aabb  xor     ebx, ebx
0x14000aabd  test    r10, r10
0x14000aac0  jz      loc_14000ABA9
0x14000aac6  test    edx, edx
0x14000aac8  jz      loc_14000AB6F
0x14000aace  cmp     edx, 1
0x14000aad1  jnz     loc_14000ABA9
0x14000aad7  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000aadc  mov     [r10+28h], r8b
0x14000aae0  mov     r8d, ebx
0x14000aae3  mov     [r10+18h], rax
0x14000aae7  mov     [r10+10h], r9
0x14000aaeb  mov     [r10+24h], edx
0x14000aaef  cmp     bx, [r10+2Ah]
0x14000aaf4  jnb     loc_14000ABA9
0x14000aafa  mov     rax, [r10+40h]
0x14000aafe  mov     cl, [r10+28h]
0x14000ab02  mov     r9d, r8d
0x14000ab05  cmp     [r9+rax], cl
0x14000ab09  jbe     short loc_14000AB0F
0x14000ab0b  test    cl, cl
0x14000ab0d  jnz     short loc_14000AB2F
0x14000ab0f  mov     rax, [r10+38h]
0x14000ab13  mov     rcx, [rax+r9*8]
0x14000ab17  test    rcx, rcx
0x14000ab1a  jz      short loc_14000AB34
0x14000ab1c  test    [r10+10h], rcx
0x14000ab20  jz      short loc_14000AB2F
0x14000ab22  mov     rax, [r10+18h]
0x14000ab26  and     rax, rcx
0x14000ab29  cmp     rax, [r10+18h]
0x14000ab2d  jz      short loc_14000AB34
0x14000ab2f  mov     r11b, bl
0x14000ab32  jmp     short loc_14000AB37
0x14000ab34  mov     r11b, 1
0x14000ab37  mov     rax, [r10+30h]
0x14000ab3b  mov     ecx, r8d
0x14000ab3e  shr     r9, 5
0x14000ab42  mov     edx, 1
0x14000ab47  shl     edx, cl
0x14000ab49  lea     rcx, [rax+r9*4]
0x14000ab4d  test    r11b, r11b
0x14000ab50  jz      short loc_14000AB56
0x14000ab52  or      edx, [rcx]
0x14000ab54  jmp     short loc_14000AB5A
0x14000ab56  not     edx
0x14000ab58  and     edx, [rcx]
0x14000ab5a  mov     [rcx], edx
0x14000ab5c  inc     r8d
0x14000ab5f  movzx   eax, word ptr [r10+2Ah]
0x14000ab64  cmp     r8d, eax
0x14000ab67  jb      short loc_14000AAFA
0x14000ab69  add     rsp, 20h
0x14000ab6d  pop     rbx
0x14000ab6e  retn
0x14000ab6f  mov     [r10+24h], ebx
0x14000ab73  mov     [r10+28h], bl
0x14000ab77  mov     [r10+10h], rbx
0x14000ab7b  mov     [r10+18h], rbx
0x14000ab7f  cmp     [r10+2Ah], bx
0x14000ab84  jbe     short loc_14000ABA9
0x14000ab86  movzx   eax, word ptr [r10+2Ah]
0x14000ab8b  mov     ecx, 20h ; ' '
0x14000ab90  dec     eax
0x14000ab92  cdq
0x14000ab93  idiv    ecx
0x14000ab95  mov     rcx, [r10+30h]; void *
0x14000ab99  xor     edx, edx; Val
0x14000ab9b  inc     eax
0x14000ab9d  movsxd  r8, eax
0x14000aba0  shl     r8, 2; Size
0x14000aba4  call    memset_0
0x14000aba9  add     rsp, 20h
0x14000abad  pop     rbx
0x14000abae  retn
```
