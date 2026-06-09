# AddCopyProtFontToWaitList

- ea: `0x140081220`
- end: `0x140081320`
- name: `AddCopyProtFontToWaitList`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140033950`

## callees

- `0x140038670`
- `0x1400392ac`
- `0x140052a14`
- `0x140076ede`
- `0x14007ee98`
- `0x140081220`

## pseudocode

```c
char __fastcall AddCopyProtFontToWaitList(__int64 a1, __int64 a2, __int64 a3)
{
  char v4; // si
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  void *v9; // r14
  _QWORD *i; // rdi
  __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  v4 = 0;
  v12 = 0;
  LOBYTE(a3) = 1;
  v5 = ATMallocExt(1120, a2, a3);
  v6 = v5;
  v12 = v5;
  if ( v5 )
  {
    v7 = *(_QWORD *)(a1 + 136);
    if ( v7 )
    {
      if ( (unsigned int)GetFontFilePath(v7, v5 + 522) == 1 )
      {
        v8 = *(_QWORD *)(a1 + 160);
        if ( !v8 || (unsigned int)GetFontFilePath(v8, v6) == 1 )
        {
          WStrCpyExt(v6 + 1046, a1 + 392, 64);
          *(_WORD *)(v6 + 1044) = *(_WORD *)(a1 + 1058);
          v9 = waitingList;
          for ( i = waitingList; i; i = (_QWORD *)i[139] )
          {
            if ( !memcmp_0(i, (const void *)v6, 0x458u) )
              goto LABEL_11;
          }
          *(_QWORD *)(v6 + 1112) = v9;
          waitingList = (void *)v6;
          v6 = 0;
          v12 = 0;
          v4 = 1;
        }
      }
    }
  }
LABEL_11:
  if ( v6 )
    EnhancedFree(&v12);
  return v4;
}

```

## disassembly

```asm
0x140081220  push    rbx
0x140081222  push    rsi
0x140081223  push    rdi
0x140081224  push    r14
0x140081226  sub     rsp, 38h
0x14008122a  mov     rdi, rcx
0x14008122d  xor     sil, sil
0x140081230  mov     [rsp+58h+arg_8], 0
0x140081239  mov     r9b, 1
0x14008123c  mov     r8b, r9b
0x14008123f  mov     ecx, 460h
0x140081244  call    ATMallocExt
0x140081249  mov     rbx, rax
0x14008124c  mov     [rsp+58h+arg_8], rax
0x140081251  test    rax, rax
0x140081254  jz      loc_140081304
0x14008125a  mov     rcx, [rdi+88h]
0x140081261  test    rcx, rcx
0x140081264  jz      loc_140081304
0x14008126a  lea     rdx, [rax+20Ah]
0x140081271  call    GetFontFilePath
0x140081276  cmp     eax, 1
0x140081279  jnz     loc_140081304
0x14008127f  mov     rcx, [rdi+0A0h]
0x140081286  test    rcx, rcx
0x140081289  jz      short loc_140081298
0x14008128b  mov     rdx, rbx
0x14008128e  call    GetFontFilePath
0x140081293  cmp     eax, 1
0x140081296  jnz     short loc_140081304
0x140081298  lea     rdx, [rdi+188h]
0x14008129f  lea     rcx, [rbx+416h]
0x1400812a6  mov     r8d, 40h ; '@'
0x1400812ac  call    WStrCpyExt
0x1400812b1  movzx   eax, word ptr [rdi+422h]
0x1400812b8  mov     [rbx+414h], ax
0x1400812bf  mov     r14, cs:waitingList
0x1400812c6  mov     rdi, r14
0x1400812c9  test    rdi, rdi
0x1400812cc  jz      short loc_1400812EC
0x1400812ce  mov     r8d, 458h; Size
0x1400812d4  mov     rdx, rbx; Buf2
0x1400812d7  mov     rcx, rdi; Buf1
0x1400812da  call    memcmp_0
0x1400812df  test    eax, eax
0x1400812e1  jz      short loc_140081304
0x1400812e3  mov     rdi, [rdi+458h]
0x1400812ea  jmp     short loc_1400812C9
0x1400812ec  mov     [rbx+458h], r14
0x1400812f3  mov     cs:waitingList, rbx
0x1400812fa  xor     ebx, ebx
0x1400812fc  mov     [rsp+58h+arg_8], rbx
0x140081301  mov     sil, 1
0x140081304  test    rbx, rbx
0x140081307  jz      short loc_140081313
0x140081309  lea     rcx, [rsp+58h+arg_8]
0x14008130e  call    EnhancedFree
0x140081313  mov     al, sil
0x140081316  add     rsp, 38h
0x14008131a  pop     r14
0x14008131c  pop     rdi
0x14008131d  pop     rsi
0x14008131e  pop     rbx
0x14008131f  retn
0x140097a57  push    rbp
0x140097a59  sub     rsp, 30h
0x140097a5d  mov     rbp, rdx
0x140097a60  cmp     qword ptr [rbp+68h], 0
0x140097a65  jz      short loc_140097A71
0x140097a67  lea     rcx, [rbp+68h]
0x140097a6b  call    EnhancedFree
0x140097a70  nop
0x140097a71  add     rsp, 30h
0x140097a75  pop     rbp
0x140097a76  retn
```
