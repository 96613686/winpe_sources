# NpQueryClientProcessImpl

- ea: `0x1400156e8`
- end: `0x140015871`
- name: `NpQueryClientProcessImpl`
- size: `393`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, void *, __int64, void *, _WORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000efb0`
- `0x140015610`

## callees

- `0x140001f40`
- `0x140014af4`
- `0x1400156e8`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140015839`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140015839`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140015740`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140015740`

## pseudocode

```c
__int64 __fastcall NpQueryClientProcessImpl(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        void *a6,
        _WORD *a7)
{
  _WORD *v7; // rax
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rsi
  unsigned int v13; // ebx
  _QWORD *v14; // rbx
  _QWORD *i; // rax
  _QWORD *v16; // rcx
  int v17; // eax
  _QWORD *v18; // rdi
  void *v19; // rdi
  size_t v20; // rbx
  void *Src[3]; // [rsp+20h] [rbp-18h] BYREF
  size_t Size; // [rsp+70h] [rbp+38h] BYREF

  v7 = *(_WORD **)(a1 + 24);
  Src[0] = 0;
  Size = 0;
  if ( *v7 != 514 || (*(_QWORD *)(a1 + 32) & 1) == 0 )
    return 3221225648LL;
  v11 = *(_QWORD *)(a1 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
  v12 = v11 + 64;
  ExAcquirePushLockSharedEx(v11 + 64, 0);
  if ( (*(_QWORD *)(a1 + 32) & 1) != 0 )
  {
    v14 = (_QWORD *)(v11 + 304);
    for ( i = *(_QWORD **)(v11 + 304); ; i = (_QWORD *)*i )
    {
      if ( i == v14 )
      {
        v16 = 0;
        v17 = -1073741275;
        goto LABEL_10;
      }
      if ( i[2] == 6 )
        break;
    }
    v16 = i + 4;
    if ( i[3] > 8u )
      v16 = (_QWORD *)*v16;
    v17 = 0;
LABEL_10:
    v18 = 0;
    if ( v17 >= 0 )
      v18 = v16;
    if ( (int)NpGetAttributeFromList(v14, 3u, Src, &Size) >= 0 && Size <= 8 )
      memmove(a4, Src[0], Size);
    if ( v18 && (int)NpGetAttributeFromList(v14, 4u, Src, &Size) >= 0 && Size == 8 )
      *a2 = *(_QWORD *)Src[0];
    v19 = a6;
    if ( a6 && (int)NpGetAttributeFromList(v14, 6u, Src, &Size) >= 0 )
    {
      v20 = Size;
      if ( Size > 0x1E )
        v20 = 30;
      memmove(v19, Src[0], v20);
      *a7 = v20;
    }
    v13 = 0;
  }
  else
  {
    v13 = -1073741648;
  }
  ExReleasePushLockSharedEx(v12, 0);
  return v13;
}

```

## disassembly

```asm
0x1400156e8  push    rbp
0x1400156ea  push    rbx
0x1400156eb  push    rsi
0x1400156ec  push    rdi
0x1400156ed  push    r14
0x1400156ef  push    r15
0x1400156f1  mov     rbp, rsp
0x1400156f4  sub     rsp, 38h
0x1400156f8  mov     rax, [rcx+18h]
0x1400156fc  mov     rbx, rcx
0x1400156ff  mov     ecx, 202h
0x140015704  mov     [rbp+Src], 0
0x14001570c  mov     r15, r9
0x14001570f  mov     [rbp+Size], 0
0x140015717  mov     r14, rdx
0x14001571a  cmp     [rax], cx
0x14001571d  jnz     loc_14001585E
0x140015723  mov     rax, [rbx+20h]
0x140015727  test    al, 1
0x140015729  jz      loc_14001585E
0x14001572f  mov     rdi, [rbx+20h]
0x140015733  xor     edx, edx
0x140015735  and     rdi, 0FFFFFFFFFFFFFFFCh
0x140015739  lea     rsi, [rdi+40h]
0x14001573d  mov     rcx, rsi
0x140015740  call    cs:__imp_ExAcquirePushLockSharedEx
0x140015747  nop     dword ptr [rax+rax+00h]
0x14001574c  mov     rax, [rbx+20h]
0x140015750  test    al, 1
0x140015752  jnz     short loc_14001575E
0x140015754  mov     ebx, 0C00000B0h
0x140015759  jmp     loc_140015834
0x14001575e  lea     rbx, [rdi+130h]
0x140015765  mov     rax, [rbx]
0x140015768  jmp     short loc_140015778
0x14001576a  cmp     qword ptr [rax+10h], 6
0x14001576f  jz      loc_140015849
0x140015775  mov     rax, [rax]
0x140015778  cmp     rax, rbx
0x14001577b  jnz     short loc_14001576A
0x14001577d  xor     ecx, ecx
0x14001577f  mov     eax, 0C0000225h
0x140015784  xor     edi, edi
0x140015786  lea     r9, [rbp+Size]
0x14001578a  test    eax, eax
0x14001578c  lea     r8, [rbp+Src]
0x140015790  mov     edx, 3
0x140015795  cmovns  rdi, rcx
0x140015799  mov     rcx, rbx
0x14001579c  call    NpGetAttributeFromList
0x1400157a1  test    eax, eax
0x1400157a3  js      short loc_1400157BB
0x1400157a5  mov     r8, [rbp+Size]; Size
0x1400157a9  cmp     r8, 8
0x1400157ad  ja      short loc_1400157BB
0x1400157af  mov     rdx, [rbp+Src]; Src
0x1400157b3  mov     rcx, r15; void *
0x1400157b6  call    memmove
0x1400157bb  test    rdi, rdi
0x1400157be  jz      short loc_1400157EA
0x1400157c0  lea     r9, [rbp+Size]
0x1400157c4  mov     edx, 4
0x1400157c9  lea     r8, [rbp+Src]
0x1400157cd  mov     rcx, rbx
0x1400157d0  call    NpGetAttributeFromList
0x1400157d5  test    eax, eax
0x1400157d7  js      short loc_1400157EA
0x1400157d9  cmp     [rbp+Size], 8
0x1400157de  jnz     short loc_1400157EA
0x1400157e0  mov     rax, [rbp+Src]
0x1400157e4  mov     r8, [rax]
0x1400157e7  mov     [r14], r8
0x1400157ea  mov     rdi, [rbp+arg_28]
0x1400157ee  test    rdi, rdi
0x1400157f1  jz      short loc_140015832
0x1400157f3  lea     r9, [rbp+Size]
0x1400157f7  mov     edx, 6
0x1400157fc  lea     r8, [rbp+Src]
0x140015800  mov     rcx, rbx
0x140015803  call    NpGetAttributeFromList
0x140015808  test    eax, eax
0x14001580a  js      short loc_140015832
0x14001580c  mov     rbx, [rbp+Size]
0x140015810  mov     eax, 1Eh
0x140015815  mov     rdx, [rbp+Src]; Src
0x140015819  cmp     rbx, rax
0x14001581c  mov     rcx, rdi; void *
0x14001581f  cmova   rbx, rax
0x140015823  mov     r8, rbx; Size
0x140015826  call    memmove
0x14001582b  mov     rax, [rbp+arg_30]
0x14001582f  mov     [rax], bx
0x140015832  xor     ebx, ebx
0x140015834  xor     edx, edx
0x140015836  mov     rcx, rsi
0x140015839  call    cs:__imp_ExReleasePushLockSharedEx
0x140015840  nop     dword ptr [rax+rax+00h]
0x140015845  mov     eax, ebx
0x140015847  jmp     short loc_140015863
0x140015849  cmp     qword ptr [rax+18h], 8
0x14001584e  lea     rcx, [rax+20h]
0x140015852  jbe     short loc_140015857
0x140015854  mov     rcx, [rcx]
0x140015857  xor     eax, eax
0x140015859  jmp     loc_140015784
0x14001585e  mov     eax, 0C00000B0h
0x140015863  add     rsp, 38h
0x140015867  pop     r15
0x140015869  pop     r14
0x14001586b  pop     rdi
0x14001586c  pop     rsi
0x14001586d  pop     rbx
0x14001586e  pop     rbp
0x14001586f  retn
```
