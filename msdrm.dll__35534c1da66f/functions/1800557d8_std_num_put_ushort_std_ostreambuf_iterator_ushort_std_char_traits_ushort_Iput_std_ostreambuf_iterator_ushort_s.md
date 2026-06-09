# std::num_put<ushort,std::ostreambuf_iterator<ushort,std::char_traits<ushort>>>::_Iput(std::ostreambuf_iterator<ushort,std::char_traits<ushort>>,std::ios_base &,ushort,char *,unsigned __int64)

- ea: `0x1800557d8`
- end: `0x180055a63`
- name: `?_Iput@?$num_put@GV?$ostreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@GU?$char_traits@G@std@@@2@V32@AEAVios_base@2@GPEAD_K@Z`
- size: `651`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180055ee0`
- `0x180055ff0`
- `0x1800564f0`
- `0x1800565a0`
- `0x1800566b0`

## callees

- `0x180001284`
- `0x1800012e8`
- `0x180001364`
- `0x180024308`
- `0x180024cb4`
- `0x1800557d8`
- `0x180055adc`
- `0x180055bcc`
- `0x180055ca8`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180055923`
- `msvcrt!memmove_s` at `0x180055923`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::num_put<unsigned short,std::ostreambuf_iterator<unsigned short>>::_Iput(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        __int64 a4,
        unsigned __int16 a5,
        _BYTE *a6,
        unsigned __int64 a7)
{
  __int64 v7; // r15
  __int64 v9; // rdi
  _BYTE *v10; // r12
  unsigned __int64 v11; // r14
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rsi
  void **v16; // rax
  int v17; // ecx
  void **v18; // rax
  void **v19; // rdi
  char v20; // al
  __int64 v21; // r15
  __int64 v22; // rbx
  __int64 v23; // rbx
  int v24; // eax
  unsigned __int16 v25; // si
  __int16 v26; // ax
  __int128 v27; // xmm0
  int v28; // ecx
  __int128 v30; // [rsp+40h] [rbp-71h] BYREF
  __int64 v31; // [rsp+50h] [rbp-61h] BYREF
  _QWORD v32[2]; // [rsp+58h] [rbp-59h] BYREF
  __int64 v33; // [rsp+68h] [rbp-49h] BYREF
  __int64 v34; // [rsp+70h] [rbp-41h]
  __int64 v35; // [rsp+78h] [rbp-39h]
  void *Block[3]; // [rsp+80h] [rbp-31h] BYREF
  unsigned __int64 v37; // [rsp+98h] [rbp-19h]

  v35 = -2;
  v7 = a4;
  *(_QWORD *)&v30 = a4;
  v9 = a2;
  v32[0] = a2;
  v34 = a1;
  v10 = a6;
  v11 = a7;
  v33 = **(_QWORD **)(a4 + 64);
  v12 = v33;
  std::_Lockit::_Lockit((std::_Lockit *)&v31, 0);
  v13 = *(_QWORD *)(v12 + 8);
  if ( v13 != -1 )
    *(_QWORD *)(v12 + 8) = v13 + 1;
  std::_Lockit::~_Lockit((std::_Lockit *)&v31);
  v14 = std::use_facet<std::numpunct<unsigned short>>(&v33);
  v31 = v14;
  std::locale::~locale((std::locale *)&v33);
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v14 + 24LL))(v14, Block);
  if ( ((*a6 - 43) & 0xFD) != 0 )
  {
    if ( *a6 != 48 || ((a6[1] - 88) & 0xDF) != 0 )
      v15 = 0;
    else
      v15 = 2;
  }
  else
  {
    v15 = 1;
  }
  v16 = Block;
  v17 = (int)Block[0];
  if ( v37 >= 0x10 )
    v16 = (void **)Block[0];
  if ( *(_BYTE *)v16 != 127 )
  {
    v18 = Block;
    if ( v37 >= 0x10 )
      v18 = (void **)Block[0];
    if ( *(char *)v18 > 0 )
    {
      v19 = Block;
      if ( v37 >= 0x10 )
        v19 = (void **)Block[0];
      v20 = *(_BYTE *)v19;
      if ( *(_BYTE *)v19 != 127 )
      {
        v21 = a7;
        do
        {
          if ( v20 <= 0 )
            break;
          v17 = v20;
          if ( v20 >= (unsigned __int64)(v21 - v15) )
            break;
          v21 -= v20;
          memmove_s(&a6[v21 + 1], v11 - v21 + 1, &a6[v21], v11 - v21 + 1);
          a6[v21] = 0;
          ++v11;
          if ( *((char *)v19 + 1) > 0 )
            v19 = (void **)((char *)v19 + 1);
          v20 = *(_BYTE *)v19;
        }
        while ( *(_BYTE *)v19 != 127 );
        v7 = v30;
      }
      v9 = v32[0];
    }
  }
  v22 = *(_QWORD *)(v7 + 40);
  if ( v22 <= 0 || v22 <= v11 )
    v23 = 0;
  else
    v23 = v22 - v11;
  v24 = *(_DWORD *)(v7 + 24) & 0x1C0;
  if ( v24 == 64 )
  {
    v25 = a5;
  }
  else
  {
    v30 = *a3;
    if ( v24 == 256 )
    {
      v10 = &a6[v15];
      v11 -= v15;
      v30 = *(_OWORD *)std::num_put<unsigned short,std::ostreambuf_iterator<unsigned short>>::_Putc(
                         v34,
                         (unsigned int)v32,
                         (unsigned int)&v30,
                         (_DWORD)a6,
                         v15);
    }
    v25 = a5;
    *a3 = *(_OWORD *)std::num_put<unsigned short,std::ostreambuf_iterator<unsigned short>>::_Rep(
                       v17,
                       (unsigned int)v32,
                       (unsigned int)&v30,
                       a5,
                       v23);
    v23 = 0;
  }
  v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  v30 = *a3;
  v27 = *(_OWORD *)std::num_put<unsigned short,std::ostreambuf_iterator<unsigned short>>::_Putgrouped(
                     v34,
                     v32,
                     &v30,
                     v10,
                     v11,
                     v26);
  *(_QWORD *)(v7 + 40) = 0;
  v30 = v27;
  std::num_put<unsigned short,std::ostreambuf_iterator<unsigned short>>::_Rep(v28, v9, (unsigned int)&v30, v25, v23);
  if ( v37 >= 0x10 )
    operator delete(Block[0]);
  return v9;
}

```

## disassembly

```asm
0x1800557d8  push    rbp
0x1800557da  push    rbx
0x1800557db  push    rsi
0x1800557dc  push    rdi
0x1800557dd  push    r12
0x1800557df  push    r13
0x1800557e1  push    r14
0x1800557e3  push    r15
0x1800557e5  lea     rbp, [rsp-7]
0x1800557ea  sub     rsp, 0B8h
0x1800557f1  mov     [rbp+3Fh+var_78], 0FFFFFFFFFFFFFFFEh
0x1800557f9  mov     rax, cs:__security_cookie
0x180055800  xor     rax, rsp
0x180055803  mov     [rbp+3Fh+var_48], rax
0x180055807  mov     r15, r9
0x18005580a  mov     qword ptr [rbp+3Fh+var_B0], r9
0x18005580e  mov     r13, r8
0x180055811  mov     rdi, rdx
0x180055814  mov     [rbp+3Fh+var_98], rdx
0x180055818  mov     [rbp+3Fh+var_80], rcx
0x18005581c  movzx   eax, [rbp+3Fh+arg_20]
0x180055820  mov     [rsp+0F0h+var_C0], ax
0x180055825  mov     r12, [rbp+3Fh+arg_28]
0x180055829  mov     r14, [rbp+3Fh+arg_30]
0x18005582d  mov     rax, [r9+40h]
0x180055831  mov     rbx, [rax]
0x180055834  mov     [rbp+3Fh+var_88], rbx
0x180055838  xor     edx, edx; int
0x18005583a  lea     rcx, [rbp+3Fh+var_A0]; this
0x18005583e  call    ??0_Lockit@std@@QEAA@H@Z
0x180055843  mov     rax, [rbx+8]
0x180055847  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005584b  jnb     short loc_180055854
0x18005584d  inc     rax
0x180055850  mov     [rbx+8], rax
0x180055854  lea     rcx, [rbp+3Fh+var_A0]; this
0x180055858  call    ??1_Lockit@std@@QEAA@XZ
0x18005585d  nop
0x18005585e  lea     rcx, [rbp+3Fh+var_88]
0x180055862  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z
0x180055867  mov     rbx, rax
0x18005586a  mov     [rbp+3Fh+var_A0], rax
0x18005586e  lea     rcx, [rbp+3Fh+var_88]; this
0x180055872  call    ??1locale@std@@QEAA@XZ
0x180055877  mov     rax, [rbx]
0x18005587a  lea     rdx, [rbp+3Fh+Block]
0x18005587e  mov     rcx, rbx
0x180055881  mov     rax, [rax+18h]
0x180055885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005588a  nop
0x18005588b  mov     al, [r12]
0x18005588f  sub     al, 2Bh ; '+'
0x180055891  test    al, 0FDh
0x180055893  jz      short loc_1800558B2
0x180055895  cmp     byte ptr [r12], 30h ; '0'
0x18005589a  jnz     short loc_1800558AE
0x18005589c  mov     al, [r12+1]
0x1800558a1  sub     al, 58h ; 'X'
0x1800558a3  test    al, 0DFh
0x1800558a5  jnz     short loc_1800558AE
0x1800558a7  mov     esi, 2
0x1800558ac  jmp     short loc_1800558B7
0x1800558ae  xor     esi, esi
0x1800558b0  jmp     short loc_1800558B7
0x1800558b2  mov     esi, 1
0x1800558b7  lea     rax, [rbp+3Fh+Block]
0x1800558bb  mov     rcx, [rbp+3Fh+Block]
0x1800558bf  mov     rdx, [rbp+3Fh+var_58]
0x1800558c3  cmp     rdx, 10h
0x1800558c7  cmovnb  rax, rcx
0x1800558cb  cmp     byte ptr [rax], 7Fh
0x1800558ce  jz      short loc_180055948
0x1800558d0  lea     rax, [rbp+3Fh+Block]
0x1800558d4  cmp     rdx, 10h
0x1800558d8  cmovnb  rax, rcx
0x1800558dc  cmp     byte ptr [rax], 0
0x1800558df  jle     short loc_180055948
0x1800558e1  lea     rdi, [rbp+3Fh+Block]
0x1800558e5  cmp     rdx, 10h
0x1800558e9  cmovnb  rdi, rcx
0x1800558ed  mov     al, [rdi]
0x1800558ef  cmp     al, 7Fh
0x1800558f1  jz      short loc_180055944
0x1800558f3  mov     r15, r14
0x1800558f6  test    al, al
0x1800558f8  jle     short loc_180055940
0x1800558fa  movsx   rcx, al
0x1800558fe  mov     rax, r15
0x180055901  sub     rax, rsi
0x180055904  cmp     rcx, rax
0x180055907  jnb     short loc_180055940
0x180055909  sub     r15, rcx
0x18005590c  mov     rdx, r14
0x18005590f  sub     rdx, r15
0x180055912  inc     rdx; DestinationSize
0x180055915  lea     rbx, [r12+r15]
0x180055919  lea     rcx, [rbx+1]; Destination
0x18005591d  mov     r9, rdx; SourceSize
0x180055920  mov     r8, rbx; Source
0x180055923  call    cs:__imp_memmove_s
0x180055929  mov     byte ptr [rbx], 0
0x18005592c  inc     r14
0x18005592f  lea     rax, [rdi+1]
0x180055933  cmp     byte ptr [rax], 0
0x180055936  cmovg   rdi, rax
0x18005593a  mov     al, [rdi]
0x18005593c  cmp     al, 7Fh
0x18005593e  jnz     short loc_1800558F6
0x180055940  mov     r15, qword ptr [rbp+3Fh+var_B0]
0x180055944  mov     rdi, [rbp+3Fh+var_98]
0x180055948  mov     rbx, [r15+28h]
0x18005594c  test    rbx, rbx
0x18005594f  jle     short loc_18005595B
0x180055951  cmp     rbx, r14
0x180055954  jbe     short loc_18005595B
0x180055956  sub     rbx, r14
0x180055959  jmp     short loc_18005595D
0x18005595b  xor     ebx, ebx
0x18005595d  mov     eax, [r15+18h]
0x180055961  and     eax, 1C0h
0x180055966  cmp     eax, 40h ; '@'
0x180055969  jz      short loc_1800559CD
0x18005596b  movaps  xmm0, xmmword ptr [r13+0]
0x180055970  lea     r8, [rbp+3Fh+var_B0]
0x180055974  lea     rdx, [rbp+3Fh+var_98]
0x180055978  movdqa  [rbp+3Fh+var_B0], xmm0
0x18005597d  cmp     eax, 100h
0x180055982  jz      short loc_1800559A4
0x180055984  movzx   esi, [rsp+0F0h+var_C0]
0x180055989  movzx   r9d, si
0x18005598d  mov     [rsp+0F0h+var_D0], rbx
0x180055992  call    ?_Rep@?$num_put@GV?$ostreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@GU?$char_traits@G@std@@@2@V32@G_K@Z
0x180055997  movups  xmm0, xmmword ptr [rax]
0x18005599a  movdqu  xmmword ptr [r13+0], xmm0
0x1800559a0  xor     ebx, ebx
0x1800559a2  jmp     short loc_1800559D2
0x1800559a4  mov     [rsp+0F0h+var_D0], rsi
0x1800559a9  mov     r9, r12
0x1800559ac  mov     rcx, [rbp+3Fh+var_80]
0x1800559b0  call    ?_Putc@?$num_put@GV?$ostreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@GU?$char_traits@G@std@@@2@V32@PEBD_K@Z
0x1800559b5  add     r12, rsi
0x1800559b8  sub     r14, rsi
0x1800559bb  movups  xmm0, xmmword ptr [rax]
0x1800559be  movdqu  [rbp+3Fh+var_B0], xmm0
0x1800559c3  lea     r8, [rbp+3Fh+var_B0]
0x1800559c7  lea     rdx, [rbp+3Fh+var_98]
0x1800559cb  jmp     short loc_180055984
0x1800559cd  movzx   esi, [rsp+0F0h+var_C0]
0x1800559d2  mov     rcx, [rbp+3Fh+var_A0]
0x1800559d6  mov     rax, [rcx]
0x1800559d9  mov     rax, [rax+10h]
0x1800559dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800559e2  movaps  xmm0, xmmword ptr [r13+0]
0x1800559e7  movdqa  [rbp+3Fh+var_B0], xmm0
0x1800559ec  mov     [rsp+0F0h+var_C8], ax
0x1800559f1  mov     [rsp+0F0h+var_D0], r14
0x1800559f6  mov     r9, r12
0x1800559f9  lea     r8, [rbp+3Fh+var_B0]
0x1800559fd  lea     rdx, [rbp+3Fh+var_98]
0x180055a01  mov     rcx, [rbp+3Fh+var_80]
0x180055a05  call    ?_Putgrouped@?$num_put@GV?$ostreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@GU?$char_traits@G@std@@@2@V32@PEBD_KG@Z
0x180055a0a  movups  xmm0, xmmword ptr [rax]
0x180055a0d  mov     qword ptr [r15+28h], 0
0x180055a15  movdqa  [rbp+3Fh+var_B0], xmm0
0x180055a1a  mov     [rsp+0F0h+var_D0], rbx
0x180055a1f  movzx   r9d, si
0x180055a23  lea     r8, [rbp+3Fh+var_B0]
0x180055a27  mov     rdx, rdi
0x180055a2a  call    ?_Rep@?$num_put@GV?$ostreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@GU?$char_traits@G@std@@@2@V32@G_K@Z
0x180055a2f  nop
0x180055a30  cmp     [rbp+3Fh+var_58], 10h
0x180055a35  jb      short loc_180055A40
0x180055a37  mov     rcx, [rbp+3Fh+Block]; Block
0x180055a3b  call    ??3@YAXPEAX@Z
0x180055a40  mov     rax, rdi
0x180055a43  mov     rcx, [rbp+3Fh+var_48]
0x180055a47  xor     rcx, rsp; StackCookie
0x180055a4a  call    __security_check_cookie
0x180055a4f  add     rsp, 0B8h
0x180055a56  pop     r15
0x180055a58  pop     r14
0x180055a5a  pop     r13
0x180055a5c  pop     r12
0x180055a5e  pop     rdi
0x180055a5f  pop     rsi
0x180055a60  pop     rbx
0x180055a61  pop     rbp
0x180055a62  retn
```
