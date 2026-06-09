# DfscCreateEas

- ea: `0x1400131d0`
- end: `0x140013384`
- name: `DfscCreateEas`
- size: `436`
- prototype: `__int64 __fastcall(char, __int64, const void *, unsigned int, char **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400136f0`
- `0x140026660`

## callees

- `0x1400027f8`
- `0x140006080`
- `0x140006380`
- `0x1400131d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001326b`
- `ntoskrnl!ExAllocatePool2` at `0x14001326b`

## string_xrefs

- `0x1400132e4`: `DFSCreate`

## pseudocode

```c
__int64 __fastcall DfscCreateEas(char a1, __int64 a2, const void *a3, unsigned int a4, char **a5, unsigned int *a6)
{
  size_t v6; // r14
  unsigned int v9; // edi
  int v10; // eax
  unsigned int v11; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  char *Pool2; // rax
  char *v15; // rsi
  unsigned int v17; // r15d
  unsigned int *v18; // r12

  v6 = a4;
  v9 = a1 != 0 ? 0x14 : 0;
  if ( a2 && (v10 = *(_DWORD *)(a2 + 72)) != 0 )
  {
    v11 = v10 + v9;
    if ( v10 + v9 < v9 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
      {
        return 3221225621LL;
      }
      v13 = 33;
LABEL_19:
      WPP_SF_D(v12->AttachedDevice, v13, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids, 3221225621LL);
      return 3221225621LL;
    }
  }
  else
  {
    v11 = a1 != 0 ? 0x14 : 0;
  }
  if ( a3 && a4 )
  {
    if ( v11 + a4 < v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0 )
      {
        return 3221225621LL;
      }
      v13 = 34;
      goto LABEL_19;
    }
    v11 += a4;
  }
  if ( v11 < v9 || v11 > 0xFFFF )
    return 3221225485LL;
  Pool2 = (char *)ExAllocatePool2(258, v11, 1698915908);
  v15 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v17 = 0;
  v18 = (unsigned int *)Pool2;
  memset(Pool2, 0, v11);
  if ( a1 )
  {
    v17 = v9;
    strcpy(v15 + 8, "DFSCreate");
    *((_WORD *)v15 + 3) = 0;
    *(_DWORD *)v15 = 0;
    v15[5] = 10;
  }
  if ( a2 )
  {
    *(_DWORD *)v15 = v17;
    v18 = (unsigned int *)&v15[v17];
    memmove(v18, (const void *)(a2 + 80), *(unsigned int *)(a2 + 72));
    *v18 = 0;
    v17 = *(_DWORD *)(a2 + 72);
  }
  if ( a3 && (_DWORD)v6 )
  {
    *v18 = v17;
    memmove((char *)v18 + v17, a3, v6);
  }
  *a5 = v15;
  *a6 = v11;
  return 0;
}

```

## disassembly

```asm
0x1400131d0  mov     [rsp+arg_0], cl
0x1400131d4  push    rbx
0x1400131d5  push    rbp
0x1400131d6  push    rsi
0x1400131d7  push    rdi
0x1400131d8  push    r12
0x1400131da  push    r13
0x1400131dc  push    r14
0x1400131de  push    r15
0x1400131e0  sub     rsp, 28h
0x1400131e4  mov     al, cl
0x1400131e6  mov     r14d, r9d
0x1400131e9  neg     al
0x1400131eb  mov     r13, r8
0x1400131ee  mov     rbp, rdx
0x1400131f1  sbb     edi, edi
0x1400131f3  and     edi, 14h
0x1400131f6  test    rdx, rdx
0x1400131f9  jz      short loc_140013234
0x1400131fb  mov     eax, [rdx+48h]
0x1400131fe  test    eax, eax
0x140013200  jz      short loc_140013234
0x140013202  lea     ebx, [rax+rdi]
0x140013205  cmp     ebx, edi
0x140013207  jnb     short loc_140013236
0x140013209  mov     rcx, cs:WPP_GLOBAL_Control
0x140013210  lea     rax, WPP_GLOBAL_Control
0x140013217  cmp     rcx, rax
0x14001321a  jz      loc_1400132C0
0x140013220  test    dword ptr [rcx+2Ch], 400000h
0x140013227  jz      loc_1400132C0
0x14001322d  mov     edx, 21h ; '!'
0x140013232  jmp     short loc_1400132AA
0x140013234  mov     ebx, edi
0x140013236  test    r13, r13
0x140013239  jz      short loc_14001324A
0x14001323b  test    r9d, r9d
0x14001323e  jz      short loc_14001324A
0x140013240  lea     eax, [rbx+r14]
0x140013244  cmp     eax, ebx
0x140013246  jb      short loc_140013289
0x140013248  mov     ebx, eax
0x14001324a  cmp     ebx, edi
0x14001324c  jb      loc_14001336D
0x140013252  cmp     ebx, 0FFFFh
0x140013258  ja      loc_14001336D
0x14001325e  mov     edx, ebx
0x140013260  mov     ecx, 102h
0x140013265  mov     r8d, 65436644h
0x14001326b  call    cs:__imp_ExAllocatePool2
0x140013272  nop     dword ptr [rax+rax+00h]
0x140013277  mov     rsi, rax
0x14001327a  test    rax, rax
0x14001327d  jnz     short loc_1400132CA
0x14001327f  mov     eax, 0C000009Ah
0x140013284  jmp     loc_140013372
0x140013289  mov     rcx, cs:WPP_GLOBAL_Control
0x140013290  lea     rax, WPP_GLOBAL_Control
0x140013297  cmp     rcx, rax
0x14001329a  jz      short loc_1400132C0
0x14001329c  test    dword ptr [rcx+2Ch], 400000h
0x1400132a3  jz      short loc_1400132C0
0x1400132a5  mov     edx, 22h ; '"'
0x1400132aa  mov     rcx, [rcx+18h]
0x1400132ae  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x1400132b5  mov     r9d, 0C0000095h
0x1400132bb  call    WPP_SF_D
0x1400132c0  mov     eax, 0C0000095h
0x1400132c5  jmp     loc_140013372
0x1400132ca  mov     r8d, ebx; Size
0x1400132cd  xor     edx, edx; Val
0x1400132cf  mov     rcx, rsi; void *
0x1400132d2  xor     r15d, r15d
0x1400132d5  mov     r12, rsi
0x1400132d8  call    memset
0x1400132dd  cmp     [rsp+68h+arg_0], r15b
0x1400132e2  jz      short loc_14001330B
0x1400132e4  movsd   xmm0, qword ptr cs:aDfscreate; "DFSCreate"
0x1400132ec  mov     r15d, edi
0x1400132ef  movsd   qword ptr [rsi+8], xmm0
0x1400132f4  movzx   eax, word ptr cs:aDfscreate+8; "e"
0x1400132fb  mov     [rsi+10h], ax
0x1400132ff  xor     eax, eax
0x140013301  mov     [rsi+6], ax
0x140013305  mov     [rsi], eax
0x140013307  mov     byte ptr [rsi+5], 0Ah
0x14001330b  test    rbp, rbp
0x14001330e  jz      short loc_140013335
0x140013310  mov     [rsi], r15d
0x140013313  lea     rdx, [rbp+50h]; Src
0x140013317  mov     r8d, [rbp+48h]; Size
0x14001331b  mov     r12d, r15d
0x14001331e  add     r12, rsi
0x140013321  mov     rcx, r12; void *
0x140013324  call    memmove
0x140013329  mov     dword ptr [r12], 0
0x140013331  mov     r15d, [rbp+48h]
0x140013335  test    r13, r13
0x140013338  jz      short loc_140013354
0x14001333a  test    r14d, r14d
0x14001333d  jz      short loc_140013354
0x14001333f  mov     ecx, r15d
0x140013342  mov     r8, r14; Size
0x140013345  add     rcx, r12; void *
0x140013348  mov     [r12], r15d
0x14001334c  mov     rdx, r13; Src
0x14001334f  call    memmove
0x140013354  mov     rax, [rsp+68h+arg_20]
0x14001335c  mov     [rax], rsi
0x14001335f  mov     rax, [rsp+68h+arg_28]
0x140013367  mov     [rax], ebx
0x140013369  xor     eax, eax
0x14001336b  jmp     short loc_140013372
0x14001336d  mov     eax, 0C000000Dh
0x140013372  add     rsp, 28h
0x140013376  pop     r15
0x140013378  pop     r14
0x14001337a  pop     r13
0x14001337c  pop     r12
0x14001337e  pop     rdi
0x14001337f  pop     rsi
0x140013380  pop     rbp
0x140013381  pop     rbx
0x140013382  retn
```
