# McGenControlCallbackV2

- ea: `0x1400039b0`
- end: `0x140003aae`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400039b0`
- `0x1400068c0`

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
0x1400039b0  push    rbx
0x1400039b2  sub     rsp, 20h
0x1400039b6  mov     r10, [rsp+28h+CallbackContext]
0x1400039bb  xor     ebx, ebx
0x1400039bd  test    r10, r10
0x1400039c0  jz      loc_140003AA7
0x1400039c6  test    edx, edx
0x1400039c8  jz      loc_140003A6F
0x1400039ce  cmp     edx, 1
0x1400039d1  jnz     loc_140003AA7
0x1400039d7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400039dc  mov     [r10+28h], r8b
0x1400039e0  mov     r8d, ebx
0x1400039e3  mov     [r10+18h], rax
0x1400039e7  mov     [r10+10h], r9
0x1400039eb  mov     [r10+24h], edx
0x1400039ef  cmp     bx, [r10+2Ah]
0x1400039f4  jnb     loc_140003AA7
0x1400039fa  mov     rax, [r10+40h]
0x1400039fe  mov     cl, [r10+28h]
0x140003a02  mov     r9d, r8d
0x140003a05  cmp     [r9+rax], cl
0x140003a09  jbe     short loc_140003A0F
0x140003a0b  test    cl, cl
0x140003a0d  jnz     short loc_140003A31
0x140003a0f  mov     rax, [r10+38h]
0x140003a13  mov     rdx, [rax+r9*8]
0x140003a17  test    rdx, rdx
0x140003a1a  jz      short loc_140003A36
0x140003a1c  test    [r10+10h], rdx
0x140003a20  jz      short loc_140003A31
0x140003a22  mov     rcx, [r10+18h]
0x140003a26  mov     rax, rcx
0x140003a29  and     rax, rdx
0x140003a2c  cmp     rax, rcx
0x140003a2f  jz      short loc_140003A36
0x140003a31  mov     r11b, bl
0x140003a34  jmp     short loc_140003A39
0x140003a36  mov     r11b, 1
0x140003a39  mov     rax, [r10+30h]
0x140003a3d  mov     ecx, r8d
0x140003a40  shr     r9, 5
0x140003a44  mov     edx, 1
0x140003a49  shl     edx, cl
0x140003a4b  lea     rcx, [rax+r9*4]
0x140003a4f  mov     eax, [rcx]
0x140003a51  test    r11b, r11b
0x140003a54  jz      short loc_140003A5A
0x140003a56  or      edx, eax
0x140003a58  jmp     short loc_140003A5E
0x140003a5a  not     edx
0x140003a5c  and     edx, eax
0x140003a5e  mov     [rcx], edx
0x140003a60  inc     r8d
0x140003a63  movzx   eax, word ptr [r10+2Ah]
0x140003a68  cmp     r8d, eax
0x140003a6b  jb      short loc_1400039FA
0x140003a6d  jmp     short loc_140003AA7
0x140003a6f  movzx   eax, word ptr [r10+2Ah]
0x140003a74  mov     [r10+24h], ebx
0x140003a78  mov     [r10+28h], bl
0x140003a7c  mov     [r10+10h], rbx
0x140003a80  mov     [r10+18h], rbx
0x140003a84  test    ax, ax
0x140003a87  jz      short loc_140003AA7
0x140003a89  dec     eax
0x140003a8b  mov     ecx, 20h ; ' '
0x140003a90  cdq
0x140003a91  idiv    ecx
0x140003a93  mov     rcx, [r10+30h]; void *
0x140003a97  xor     edx, edx; Val
0x140003a99  inc     eax
0x140003a9b  movsxd  r8, eax
0x140003a9e  shl     r8, 2; Size
0x140003aa2  call    memset
0x140003aa7  add     rsp, 20h
0x140003aab  pop     rbx
0x140003aac  retn
```
