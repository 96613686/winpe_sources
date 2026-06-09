# ReadString_7

- ea: `0x18005a838`
- end: `0x18005aa22`
- name: `ReadString_7`
- size: `490`
- prototype: `__int64 __fastcall(int, int, int, int, int SizeConverted, int, FILE *Stream, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18005aa28`
- `0x18005abc0`

## callees

- `0x180005d70`
- `0x18002f05c`
- `0x180050afc`
- `0x180052afc`
- `0x18005a838`

## pseudocode

```c
__int64 __fastcall ReadString_7(
        char a1,
        __int64 a2,
        wint_t *a3,
        _DWORD *a4,
        char **SizeConverted,
        int a6,
        FILE *Stream,
        int a8,
        _DWORD *a9)
{
  char **v9; // rsi
  char *v13; // r12
  int v14; // ebx
  int v15; // eax
  FILE *v16; // rcx
  int v17; // ebp
  wint_t v18; // ax
  int v19; // ecx
  char *v20; // rdx
  errno_t v21; // eax
  bool v22; // zf
  char *v23; // rcx
  int v26; // [rsp+80h] [rbp+18h]

  v9 = SizeConverted;
  v13 = *SizeConverted;
  --*a4;
  v26 = -((a1 & 8) != 0);
  if ( *a3 != 0xFFFF )
    ungetwc_nolock(*a3, Stream);
  v14 = a1 & 4;
  v15 = a1 & 1;
  while ( 1 )
  {
    if ( v15 )
    {
      if ( !a6 )
        goto LABEL_28;
      --a6;
    }
    v16 = Stream;
    v17 = a1 & 4;
    ++*a4;
    v18 = fgetwc_nolock(v16);
    *a3 = v18;
    if ( v18 == 0xFFFF )
      break;
    if ( (a1 & 0x10) == 0 && ((a1 & 0x20) == 0 || (unsigned __int16)(v18 - 9) <= 4u || v18 == 32) )
    {
      v17 = a1 & 4;
      if ( (a1 & 0x40) == 0 )
        break;
      if ( v18 < (unsigned __int16)(v18 >> 3) )
        break;
      v19 = v26 ^ *(char *)((v18 >> 3) + a2);
      if ( !_bittest(&v19, v18 & 7) )
        break;
    }
    if ( (a1 & 4) != 0 )
    {
      v13 += 2;
LABEL_24:
      v15 = a1 & 1;
    }
    else
    {
      v20 = *v9;
      if ( (a1 & 2) != 0 )
      {
        *(_WORD *)v20 = v18;
        *v9 += 2;
        goto LABEL_24;
      }
      LODWORD(SizeConverted) = 0;
      v21 = wctomb_s((int *)&SizeConverted, v20, 5u, v18);
      if ( !v21 )
      {
        *v9 += (int)SizeConverted;
        goto LABEL_24;
      }
      if ( v21 == 22 || (v22 = v21 == 34, v15 = a1 & 1, v22) )
        invoke_watson(0, 0, 0, 0, 0);
    }
  }
  --*a4;
  if ( *a3 == 0xFFFF )
    v14 = v17;
  else
    ungetwc_nolock(*a3, Stream);
LABEL_28:
  if ( v13 == *v9 )
    return 0xFFFFFFFFLL;
  if ( !v14 )
  {
    ++*a9;
    if ( (a1 & 0x10) == 0 )
    {
      v23 = *v9;
      if ( (a1 & 2) != 0 )
        *(_WORD *)v23 = 0;
      else
        *v23 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005a838  mov     [rsp+arg_8], rdx
0x18005a83d  push    rbx
0x18005a83e  push    rbp
0x18005a83f  push    rsi
0x18005a840  push    rdi
0x18005a841  push    r12
0x18005a843  push    r13
0x18005a845  push    r14
0x18005a847  sub     rsp, 30h
0x18005a84b  mov     rsi, [rsp+68h+SizeConverted]
0x18005a853  mov     eax, ecx
0x18005a855  and     al, 8
0x18005a857  mov     r13, r8
0x18005a85a  neg     al
0x18005a85c  mov     r8d, 0FFFFh
0x18005a862  mov     r14, r9
0x18005a865  mov     edi, ecx
0x18005a867  mov     r12, [rsi]
0x18005a86a  sbb     eax, eax
0x18005a86c  dec     dword ptr [r9]
0x18005a86f  mov     [rsp+68h+arg_10], eax
0x18005a876  cmp     r8w, [r13+0]
0x18005a87b  jz      short loc_18005A88F
0x18005a87d  mov     rdx, [rsp+68h+Stream]; Stream
0x18005a885  movzx   ecx, word ptr [r13+0]; Character
0x18005a88a  call    _ungetwc_nolock
0x18005a88f  mov     ebx, edi
0x18005a891  mov     eax, edi
0x18005a893  and     ebx, 4
0x18005a896  and     eax, 1
0x18005a899  mov     [rsp+68h+arg_0], eax
0x18005a89d  test    eax, eax
0x18005a89f  jz      short loc_18005A8B9
0x18005a8a1  mov     eax, [rsp+68h+arg_28]
0x18005a8a8  test    eax, eax
0x18005a8aa  jz      loc_18005A9E0
0x18005a8b0  dec     eax
0x18005a8b2  mov     [rsp+68h+arg_28], eax
0x18005a8b9  mov     rcx, [rsp+68h+Stream]; Stream
0x18005a8c1  mov     ebp, ebx
0x18005a8c3  inc     dword ptr [r14]
0x18005a8c6  call    _fgetwc_nolock
0x18005a8cb  mov     r8d, 0FFFFh
0x18005a8d1  mov     [r13+0], ax
0x18005a8d6  movzx   r9d, ax; WCh
0x18005a8da  cmp     r8w, ax
0x18005a8de  jz      loc_18005A9C0
0x18005a8e4  test    dil, 10h
0x18005a8e8  jnz     short loc_18005A941
0x18005a8ea  test    dil, 20h
0x18005a8ee  jz      short loc_18005A905
0x18005a8f0  lea     eax, [r9-9]
0x18005a8f4  mov     ecx, 4
0x18005a8f9  cmp     ax, cx
0x18005a8fc  jbe     short loc_18005A905
0x18005a8fe  cmp     r9w, 20h ; ' '
0x18005a903  jnz     short loc_18005A941
0x18005a905  mov     ebp, ebx
0x18005a907  test    dil, 40h
0x18005a90b  jz      loc_18005A9C0
0x18005a911  movzx   ecx, r9w
0x18005a915  shr     cx, 3
0x18005a919  cmp     r9w, cx
0x18005a91d  jb      loc_18005A9C0
0x18005a923  movzx   eax, cx
0x18005a926  mov     edx, r9d
0x18005a929  mov     rcx, [rsp+68h+arg_8]
0x18005a92e  and     edx, 7
0x18005a931  movsx   ecx, byte ptr [rax+rcx]
0x18005a935  xor     ecx, [rsp+68h+arg_10]
0x18005a93c  bt      ecx, edx
0x18005a93f  jnb     short loc_18005A9C0
0x18005a941  test    ebx, ebx
0x18005a943  jnz     short loc_18005A9B3
0x18005a945  mov     rdx, [rsi]; MbCh
0x18005a948  test    dil, 2
0x18005a94c  jz      short loc_18005A958
0x18005a94e  mov     [rdx], r9w
0x18005a952  add     qword ptr [rsi], 2
0x18005a956  jmp     short loc_18005A9B7
0x18005a958  mov     r8d, 5; SizeInBytes
0x18005a95e  mov     dword ptr [rsp+68h+SizeConverted], 0
0x18005a969  lea     rcx, [rsp+68h+SizeConverted]; SizeConverted
0x18005a971  call    wctomb_s
0x18005a976  test    eax, eax
0x18005a978  jz      short loc_18005A9A6
0x18005a97a  cmp     eax, 16h
0x18005a97d  jz      short loc_18005A98C
0x18005a97f  cmp     eax, 22h ; '"'
0x18005a982  mov     eax, [rsp+68h+arg_0]
0x18005a986  jnz     loc_18005A89D
0x18005a98c  xor     r9d, r9d; LineNo
0x18005a98f  mov     [rsp+68h+Reserved], 0; Reserved
0x18005a998  xor     r8d, r8d; FileName
0x18005a99b  xor     edx, edx; FunctionName
0x18005a99d  xor     ecx, ecx; Expression
0x18005a99f  call    _invoke_watson
0x18005a9a4  jmp     short loc_18005A9B7
0x18005a9a6  movsxd  rax, dword ptr [rsp+68h+SizeConverted]
0x18005a9ae  add     [rsi], rax
0x18005a9b1  jmp     short loc_18005A9B7
0x18005a9b3  add     r12, 2
0x18005a9b7  mov     eax, [rsp+68h+arg_0]
0x18005a9bb  jmp     loc_18005A89D
0x18005a9c0  dec     dword ptr [r14]
0x18005a9c3  cmp     r8w, [r13+0]
0x18005a9c8  jz      short loc_18005A9DE
0x18005a9ca  mov     rdx, [rsp+68h+Stream]; Stream
0x18005a9d2  movzx   ecx, word ptr [r13+0]; Character
0x18005a9d7  call    _ungetwc_nolock
0x18005a9dc  jmp     short loc_18005A9E0
0x18005a9de  mov     ebx, ebp
0x18005a9e0  cmp     r12, [rsi]
0x18005a9e3  jz      short loc_18005AA10
0x18005a9e5  test    ebx, ebx
0x18005a9e7  jnz     short loc_18005AA0C
0x18005a9e9  mov     rax, [rsp+68h+arg_40]
0x18005a9f1  inc     dword ptr [rax]
0x18005a9f3  test    dil, 10h
0x18005a9f7  jnz     short loc_18005AA0C
0x18005a9f9  mov     rcx, [rsi]
0x18005a9fc  test    dil, 2
0x18005aa00  jz      short loc_18005AA09
0x18005aa02  xor     eax, eax
0x18005aa04  mov     [rcx], ax
0x18005aa07  jmp     short loc_18005AA0C
0x18005aa09  mov     byte ptr [rcx], 0
0x18005aa0c  xor     eax, eax
0x18005aa0e  jmp     short loc_18005AA13
0x18005aa10  or      eax, 0FFFFFFFFh
0x18005aa13  add     rsp, 30h
0x18005aa17  pop     r14
0x18005aa19  pop     r13
0x18005aa1b  pop     r12
0x18005aa1d  pop     rdi
0x18005aa1e  pop     rsi
0x18005aa1f  pop     rbp
0x18005aa20  pop     rbx
0x18005aa21  retn
```
