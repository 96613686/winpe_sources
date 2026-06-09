# McGenControlCallbackV2

- ea: `0x140002e30`
- end: `0x140002f2e`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002e30`
- `0x140003640`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
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
          v13 = *v12;
          if ( v10 )
            v14 = v13 | v11;
          else
            v14 = v13 & ~v11;
          *v12 = v14;
        }
      }
    }
    else
    {
      v15 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v15 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v15 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x140002e30  push    rbx
0x140002e32  sub     rsp, 20h
0x140002e36  mov     r10, [rsp+28h+CallbackContext]
0x140002e3b  xor     ebx, ebx
0x140002e3d  test    r10, r10
0x140002e40  jz      loc_140002F27
0x140002e46  test    edx, edx
0x140002e48  jz      loc_140002EEF
0x140002e4e  cmp     edx, 1
0x140002e51  jnz     loc_140002F27
0x140002e57  mov     rax, [rsp+28h+MatchAllKeyword]
0x140002e5c  mov     [r10+28h], r8b
0x140002e60  mov     r8d, ebx
0x140002e63  mov     [r10+18h], rax
0x140002e67  mov     [r10+10h], r9
0x140002e6b  mov     [r10+24h], edx
0x140002e6f  cmp     bx, [r10+2Ah]
0x140002e74  jnb     loc_140002F27
0x140002e7a  mov     rax, [r10+40h]
0x140002e7e  mov     cl, [r10+28h]
0x140002e82  mov     r9d, r8d
0x140002e85  cmp     [r9+rax], cl
0x140002e89  jbe     short loc_140002E8F
0x140002e8b  test    cl, cl
0x140002e8d  jnz     short loc_140002EB1
0x140002e8f  mov     rax, [r10+38h]
0x140002e93  mov     rdx, [rax+r9*8]
0x140002e97  test    rdx, rdx
0x140002e9a  jz      short loc_140002EB6
0x140002e9c  test    [r10+10h], rdx
0x140002ea0  jz      short loc_140002EB1
0x140002ea2  mov     rcx, [r10+18h]
0x140002ea6  mov     rax, rcx
0x140002ea9  and     rax, rdx
0x140002eac  cmp     rax, rcx
0x140002eaf  jz      short loc_140002EB6
0x140002eb1  mov     r11b, bl
0x140002eb4  jmp     short loc_140002EB9
0x140002eb6  mov     r11b, 1
0x140002eb9  mov     rax, [r10+30h]
0x140002ebd  mov     ecx, r8d
0x140002ec0  shr     r9, 5
0x140002ec4  mov     edx, 1
0x140002ec9  shl     edx, cl
0x140002ecb  lea     rcx, [rax+r9*4]
0x140002ecf  mov     eax, [rcx]
0x140002ed1  test    r11b, r11b
0x140002ed4  jz      short loc_140002EDA
0x140002ed6  or      edx, eax
0x140002ed8  jmp     short loc_140002EDE
0x140002eda  not     edx
0x140002edc  and     edx, eax
0x140002ede  mov     [rcx], edx
0x140002ee0  inc     r8d
0x140002ee3  movzx   eax, word ptr [r10+2Ah]
0x140002ee8  cmp     r8d, eax
0x140002eeb  jb      short loc_140002E7A
0x140002eed  jmp     short loc_140002F27
0x140002eef  movzx   eax, word ptr [r10+2Ah]
0x140002ef4  mov     [r10+24h], ebx
0x140002ef8  mov     [r10+28h], bl
0x140002efc  mov     [r10+10h], rbx
0x140002f00  mov     [r10+18h], rbx
0x140002f04  test    ax, ax
0x140002f07  jz      short loc_140002F27
0x140002f09  dec     eax
0x140002f0b  mov     ecx, 20h ; ' '
0x140002f10  cdq
0x140002f11  idiv    ecx
0x140002f13  mov     rcx, [r10+30h]; void *
0x140002f17  xor     edx, edx; Val
0x140002f19  inc     eax
0x140002f1b  movsxd  r8, eax
0x140002f1e  shl     r8, 2; Size
0x140002f22  call    memset
0x140002f27  add     rsp, 20h
0x140002f2b  pop     rbx
0x140002f2c  retn
```
