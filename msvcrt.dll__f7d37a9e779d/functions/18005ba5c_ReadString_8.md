# ReadString_8

- ea: `0x18005ba5c`
- end: `0x18005bc5e`
- name: `ReadString_8`
- size: `514`
- prototype: `__int64 __fastcall(int, int, int, int, int SizeConverted, int, FILE *Stream, rsize_t SizeInBytes, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18005bc64`
- `0x18005be00`

## callees

- `0x180005d70`
- `0x180007f00`
- `0x180050afc`
- `0x180052afc`
- `0x18005ba5c`

## pseudocode

```c
__int64 __fastcall ReadString_8(
        char a1,
        __int64 a2,
        wint_t *a3,
        _DWORD *a4,
        char **SizeConverted,
        int a6,
        FILE *Stream,
        rsize_t SizeInBytes,
        int a9,
        _DWORD *a10)
{
  char **v10; // rsi
  wint_t *v11; // rbx
  char *v14; // r14
  rsize_t v15; // r15
  int v16; // ecx
  FILE *v17; // rcx
  wint_t v18; // ax
  int v19; // ecx
  char *v20; // rdx
  int v21; // ebx
  __int64 v22; // rax
  char *v24; // rcx
  int v27; // [rsp+78h] [rbp+20h]

  v10 = SizeConverted;
  v11 = a3;
  v14 = *SizeConverted;
  --*a4;
  v27 = -((a1 & 8) != 0);
  if ( *a3 != 0xFFFF )
    ungetwc_nolock(*a3, Stream);
  v15 = SizeInBytes - 1;
  if ( (a1 & 0x10) != 0 )
    v15 = SizeInBytes;
  v16 = a1 & 1;
  while ( 1 )
  {
    if ( v16 )
    {
      if ( !a6 )
        goto LABEL_33;
      --a6;
    }
    v17 = Stream;
    ++*a4;
    v18 = fgetwc_nolock(v17);
    *v11 = v18;
    if ( v18 == 0xFFFF )
      break;
    if ( (a1 & 0x10) == 0 && ((a1 & 0x20) == 0 || (unsigned __int16)(v18 - 9) <= 4u || v18 == 32) )
    {
      if ( (a1 & 0x40) == 0 )
        break;
      if ( v18 < (unsigned __int16)(v18 >> 3) )
        break;
      v19 = v27 ^ *(char *)((v18 >> 3) + a2);
      if ( !_bittest(&v19, v18 & 7) )
        break;
    }
    if ( (a1 & 4) != 0 )
    {
      v14 += 2;
LABEL_25:
      v16 = a1 & 1;
    }
    else
    {
      if ( !v15 )
      {
        v21 = a1 & 2;
LABEL_27:
        *errno() = 12;
        if ( v21 )
          *(_WORD *)v14 = 0;
        else
          *v14 = 0;
        return 0xFFFFFFFFLL;
      }
      v20 = *v10;
      v21 = a1 & 2;
      if ( (a1 & 2) != 0 )
      {
        v11 = a3;
        *(_WORD *)v20 = v18;
        *v10 += 2;
        --v15;
        goto LABEL_25;
      }
      LODWORD(SizeConverted) = 0;
      if ( wctomb_s((int *)&SizeConverted, v20, v15, v18) == 34 )
        goto LABEL_27;
      v22 = (int)SizeConverted;
      v11 = a3;
      v16 = a1 & 1;
      if ( (int)SizeConverted > 0 )
      {
        *v10 += (int)SizeConverted;
        v15 -= v22;
      }
    }
  }
  --*a4;
  if ( *v11 != 0xFFFF )
    ungetwc_nolock(*v11, Stream);
LABEL_33:
  if ( v14 == *v10 )
    return 0xFFFFFFFFLL;
  if ( (a1 & 4) == 0 )
  {
    ++*a10;
    if ( (a1 & 0x10) == 0 )
    {
      v24 = *v10;
      if ( (a1 & 2) != 0 )
        *(_WORD *)v24 = 0;
      else
        *v24 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005ba5c  mov     [rsp+arg_10], r8
0x18005ba61  mov     [rsp+arg_8], rdx
0x18005ba66  push    rbx
0x18005ba67  push    rbp
0x18005ba68  push    rsi
0x18005ba69  push    rdi
0x18005ba6a  push    r12
0x18005ba6c  push    r14
0x18005ba6e  push    r15
0x18005ba70  sub     rsp, 20h
0x18005ba74  mov     rsi, [rsp+58h+SizeConverted]
0x18005ba7c  mov     eax, ecx
0x18005ba7e  and     al, 8
0x18005ba80  mov     rbx, r8
0x18005ba83  neg     al
0x18005ba85  mov     r8d, 0FFFFh
0x18005ba8b  mov     rbp, r9
0x18005ba8e  mov     edi, ecx
0x18005ba90  mov     r14, [rsi]
0x18005ba93  sbb     eax, eax
0x18005ba95  dec     dword ptr [r9]
0x18005ba98  mov     [rsp+58h+arg_18], eax
0x18005ba9c  cmp     r8w, [rbx]
0x18005baa0  jz      short loc_18005BAB2
0x18005baa2  mov     rdx, [rsp+58h+Stream]; Stream
0x18005baaa  movzx   ecx, word ptr [rbx]; Character
0x18005baad  call    _ungetwc_nolock
0x18005bab2  mov     rax, [rsp+58h+SizeInBytes]
0x18005baba  mov     r12d, edi
0x18005babd  and     r12d, 10h
0x18005bac1  mov     ecx, edi
0x18005bac3  lea     r15, [rax-1]
0x18005bac7  cmovnz  r15, rax
0x18005bacb  and     ecx, 1
0x18005bace  mov     [rsp+58h+arg_0], ecx
0x18005bad2  test    ecx, ecx
0x18005bad4  jz      short loc_18005BAEE
0x18005bad6  mov     eax, [rsp+58h+arg_28]
0x18005badd  test    eax, eax
0x18005badf  jz      loc_18005BC2D
0x18005bae5  dec     eax
0x18005bae7  mov     [rsp+58h+arg_28], eax
0x18005baee  mov     rcx, [rsp+58h+Stream]; Stream
0x18005baf6  inc     dword ptr [rbp+0]
0x18005baf9  call    _fgetwc_nolock
0x18005bafe  mov     r8d, 0FFFFh
0x18005bb04  mov     [rbx], ax
0x18005bb07  movzx   r9d, ax; WCh
0x18005bb0b  cmp     r8w, ax
0x18005bb0f  jz      loc_18005BC14
0x18005bb15  test    r12d, r12d
0x18005bb18  jnz     short loc_18005BB6C
0x18005bb1a  test    dil, 20h
0x18005bb1e  jz      short loc_18005BB31
0x18005bb20  lea     eax, [r9-9]
0x18005bb24  cmp     ax, 4
0x18005bb28  jbe     short loc_18005BB31
0x18005bb2a  cmp     r9w, 20h ; ' '
0x18005bb2f  jnz     short loc_18005BB6C
0x18005bb31  test    dil, 40h
0x18005bb35  jz      loc_18005BC14
0x18005bb3b  movzx   ecx, r9w
0x18005bb3f  shr     cx, 3
0x18005bb43  cmp     r9w, cx
0x18005bb47  jb      loc_18005BC14
0x18005bb4d  movzx   eax, cx
0x18005bb50  mov     edx, r9d
0x18005bb53  mov     rcx, [rsp+58h+arg_8]
0x18005bb58  and     edx, 7
0x18005bb5b  movsx   ecx, byte ptr [rax+rcx]
0x18005bb5f  xor     ecx, [rsp+58h+arg_18]
0x18005bb63  bt      ecx, edx
0x18005bb66  jnb     loc_18005BC14
0x18005bb6c  test    dil, 4
0x18005bb70  jnz     short loc_18005BBD7
0x18005bb72  mov     ebx, edi
0x18005bb74  test    r15, r15
0x18005bb77  jz      short loc_18005BBE4
0x18005bb79  mov     rdx, [rsi]; MbCh
0x18005bb7c  and     ebx, 2
0x18005bb7f  jz      short loc_18005BB93
0x18005bb81  mov     rbx, [rsp+58h+arg_10]
0x18005bb86  mov     [rdx], r9w
0x18005bb8a  add     qword ptr [rsi], 2
0x18005bb8e  dec     r15
0x18005bb91  jmp     short loc_18005BBDB
0x18005bb93  mov     r8, r15; SizeInBytes
0x18005bb96  mov     dword ptr [rsp+58h+SizeConverted], 0
0x18005bba1  lea     rcx, [rsp+58h+SizeConverted]; SizeConverted
0x18005bba9  call    wctomb_s
0x18005bbae  cmp     eax, 22h ; '"'
0x18005bbb1  jz      short loc_18005BBE7
0x18005bbb3  movsxd  rax, dword ptr [rsp+58h+SizeConverted]
0x18005bbbb  mov     rbx, [rsp+58h+arg_10]
0x18005bbc0  mov     ecx, [rsp+58h+arg_0]
0x18005bbc4  test    eax, eax
0x18005bbc6  jle     loc_18005BAD2
0x18005bbcc  add     [rsi], rax
0x18005bbcf  sub     r15, rax
0x18005bbd2  jmp     loc_18005BAD2
0x18005bbd7  add     r14, 2
0x18005bbdb  mov     ecx, [rsp+58h+arg_0]
0x18005bbdf  jmp     loc_18005BAD2
0x18005bbe4  and     ebx, 2
0x18005bbe7  call    _errno
0x18005bbec  mov     dword ptr [rax], 0Ch
0x18005bbf2  test    ebx, ebx
0x18005bbf4  jz      short loc_18005BC0E
0x18005bbf6  xor     eax, eax
0x18005bbf8  mov     [r14], ax
0x18005bbfc  or      eax, 0FFFFFFFFh
0x18005bbff  add     rsp, 20h
0x18005bc03  pop     r15
0x18005bc05  pop     r14
0x18005bc07  pop     r12
0x18005bc09  pop     rdi
0x18005bc0a  pop     rsi
0x18005bc0b  pop     rbp
0x18005bc0c  pop     rbx
0x18005bc0d  retn
0x18005bc0e  mov     byte ptr [r14], 0
0x18005bc12  jmp     short loc_18005BBFC
0x18005bc14  dec     dword ptr [rbp+0]
0x18005bc17  cmp     r8w, [rbx]
0x18005bc1b  jz      short loc_18005BC2D
0x18005bc1d  mov     rdx, [rsp+58h+Stream]; Stream
0x18005bc25  movzx   ecx, word ptr [rbx]; Character
0x18005bc28  call    _ungetwc_nolock
0x18005bc2d  cmp     r14, [rsi]
0x18005bc30  jz      short loc_18005BBFC
0x18005bc32  test    dil, 4
0x18005bc36  jnz     short loc_18005BC5A
0x18005bc38  mov     rax, [rsp+58h+arg_48]
0x18005bc40  inc     dword ptr [rax]
0x18005bc42  test    r12d, r12d
0x18005bc45  jnz     short loc_18005BC5A
0x18005bc47  mov     rcx, [rsi]
0x18005bc4a  test    dil, 2
0x18005bc4e  jz      short loc_18005BC57
0x18005bc50  xor     eax, eax
0x18005bc52  mov     [rcx], ax
0x18005bc55  jmp     short loc_18005BC5A
0x18005bc57  mov     byte ptr [rcx], 0
0x18005bc5a  xor     eax, eax
0x18005bc5c  jmp     short loc_18005BBFF
```
