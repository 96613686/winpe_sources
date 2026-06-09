# McGenControlCallbackV2

- ea: `0x140003ac0`
- end: `0x140003bd4`
- name: `McGenControlCallbackV2`
- size: `276`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003ac0`
- `0x140006000`

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
  unsigned int v8; // r8d
  unsigned __int8 v9; // cl
  __int64 v10; // rdx
  bool v11; // r11
  int v12; // edx
  int *v13; // rcx
  int v14; // eax
  int v15; // edx
  int v16; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v8 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v8 < *((unsigned __int16 *)CallbackContext + 21); ++v8 )
        {
          v9 = *((_BYTE *)CallbackContext + 40);
          v11 = 0;
          if ( *(_BYTE *)(v8 + *((_QWORD *)CallbackContext + 8)) <= v9 || !v9 )
          {
            v10 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v8);
            if ( !v10
              || (v10 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v10 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
            {
              v11 = 1;
            }
          }
          v12 = 1 << v8;
          v13 = (int *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v8 >> 5));
          v14 = *v13;
          if ( v11 )
            v15 = v14 | v12;
          else
            v15 = v14 & ~v12;
          *v13 = v15;
        }
      }
    }
    else
    {
      v16 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v16 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v16 - 1) / 32 + 1));
    }
    DiskETWEnabled = ControlCode != 0;
  }
}

```

## disassembly

```asm
0x140003ac0  mov     [rsp+arg_0], rbx
0x140003ac5  push    rdi
0x140003ac6  sub     rsp, 20h
0x140003aca  mov     r10, [rsp+28h+CallbackContext]
0x140003acf  xor     edi, edi
0x140003ad1  mov     ebx, edx
0x140003ad3  test    r10, r10
0x140003ad6  jz      loc_140003BC8
0x140003adc  mov     eax, edx
0x140003ade  test    edx, edx
0x140003ae0  jz      loc_140003B87
0x140003ae6  cmp     eax, 1
0x140003ae9  jnz     loc_140003BBF
0x140003aef  mov     rax, [rsp+28h+MatchAllKeyword]
0x140003af4  mov     [r10+28h], r8b
0x140003af8  mov     r8d, edi
0x140003afb  mov     [r10+18h], rax
0x140003aff  mov     [r10+10h], r9
0x140003b03  mov     [r10+24h], edx
0x140003b07  cmp     di, [r10+2Ah]
0x140003b0c  jnb     loc_140003BBF
0x140003b12  mov     rax, [r10+40h]
0x140003b16  mov     cl, [r10+28h]
0x140003b1a  mov     r9d, r8d
0x140003b1d  cmp     [r9+rax], cl
0x140003b21  jbe     short loc_140003B27
0x140003b23  test    cl, cl
0x140003b25  jnz     short loc_140003B49
0x140003b27  mov     rax, [r10+38h]
0x140003b2b  mov     rdx, [rax+r9*8]
0x140003b2f  test    rdx, rdx
0x140003b32  jz      short loc_140003B4E
0x140003b34  test    [r10+10h], rdx
0x140003b38  jz      short loc_140003B49
0x140003b3a  mov     rcx, [r10+18h]
0x140003b3e  mov     rax, rcx
0x140003b41  and     rax, rdx
0x140003b44  cmp     rax, rcx
0x140003b47  jz      short loc_140003B4E
0x140003b49  mov     r11b, dil
0x140003b4c  jmp     short loc_140003B51
0x140003b4e  mov     r11b, 1
0x140003b51  mov     rax, [r10+30h]
0x140003b55  mov     ecx, r8d
0x140003b58  shr     r9, 5
0x140003b5c  mov     edx, 1
0x140003b61  shl     edx, cl
0x140003b63  lea     rcx, [rax+r9*4]
0x140003b67  mov     eax, [rcx]
0x140003b69  test    r11b, r11b
0x140003b6c  jz      short loc_140003B72
0x140003b6e  or      edx, eax
0x140003b70  jmp     short loc_140003B76
0x140003b72  not     edx
0x140003b74  and     edx, eax
0x140003b76  mov     [rcx], edx
0x140003b78  inc     r8d
0x140003b7b  movzx   eax, word ptr [r10+2Ah]
0x140003b80  cmp     r8d, eax
0x140003b83  jb      short loc_140003B12
0x140003b85  jmp     short loc_140003BBF
0x140003b87  movzx   eax, word ptr [r10+2Ah]
0x140003b8c  mov     [r10+24h], edi
0x140003b90  mov     [r10+28h], dil
0x140003b94  mov     [r10+10h], rdi
0x140003b98  mov     [r10+18h], rdi
0x140003b9c  test    ax, ax
0x140003b9f  jz      short loc_140003BBF
0x140003ba1  dec     eax
0x140003ba3  mov     ecx, 20h ; ' '
0x140003ba8  cdq
0x140003ba9  idiv    ecx
0x140003bab  mov     rcx, [r10+30h]; void *
0x140003baf  xor     edx, edx; Val
0x140003bb1  inc     eax
0x140003bb3  movsxd  r8, eax
0x140003bb6  shl     r8, 2; Size
0x140003bba  call    memset
0x140003bbf  test    ebx, ebx
0x140003bc1  setnz   cs:DiskETWEnabled
0x140003bc8  mov     rbx, [rsp+28h+arg_0]
0x140003bcd  add     rsp, 20h
0x140003bd1  pop     rdi
0x140003bd2  retn
```
