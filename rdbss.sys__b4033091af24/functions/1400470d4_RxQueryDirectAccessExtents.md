# RxQueryDirectAccessExtents

- ea: `0x1400470d4`
- end: `0x140047431`
- name: `RxQueryDirectAccessExtents`
- size: `861`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4, ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140045410`

## callees

- `0x140017370`
- `0x140017a38`
- `0x14001b010`
- `0x1400470d4`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140047187`
- `ntoskrnl!KeBugCheckEx` at `0x140047187`

## pseudocode

```c
__int64 __fastcall RxQueryDirectAccessExtents(ULONG_PTR BugCheckParameter4, ULONG_PTR BugCheckParameter3, int a3)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  unsigned int *v8; // r11
  unsigned int v9; // r10d
  unsigned __int64 v10; // rax
  unsigned int *v11; // rbp
  unsigned __int64 *v12; // r13
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // r12
  __int64 v17; // rdx
  bool v18; // cf
  __int64 v19; // rax

  v4 = *(_QWORD *)(BugCheckParameter4 + 184);
  if ( *(_DWORD *)(v4 + 16) >= 0x18u )
  {
    v8 = *(unsigned int **)(BugCheckParameter3 + 712);
    if ( !v8 || (v9 = *v8) == 0 )
    {
      v5 = -1073741649;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v5;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
          3221225647LL,
          BugCheckParameter3);
      goto LABEL_43;
    }
    if ( v9 != 1 )
      KeBugCheckEx(0x27u, 0x908B5u, v9, BugCheckParameter3, BugCheckParameter4);
    v10 = *(unsigned int *)(v4 + 8);
    if ( (unsigned int)v10 < 8
      || (v11 = *(unsigned int **)(BugCheckParameter4 + 112), v10 < 16 * (unsigned __int64)*v11 + 8) )
    {
      v5 = -1073741811;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v5;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
        goto LABEL_43;
      v7 = 41;
      goto LABEL_6;
    }
    v12 = *(unsigned __int64 **)(v4 + 32);
    v13 = *v12;
    v14 = v12[1];
    v15 = ((*v12 & 0xFFF) != 0) + (*v12 >> 12);
    v16 = ((v14 & 0xFFF) != 0) + (v14 >> 12);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqDiiiiDiii(
        WPP_GLOBAL_Control->AttachedDevice,
        *((_QWORD *)v8 + 3) + *((_QWORD *)v8 + 2),
        *((_QWORD *)v8 + 2),
        a3,
        BugCheckParameter3,
        1,
        *((_QWORD *)v8 + 1),
        *((_QWORD *)v8 + 3),
        *((_QWORD *)v8 + 2),
        *((_QWORD *)v8 + 3) + *((_QWORD *)v8 + 2),
        *((_DWORD *)v12 + 4),
        ((v12[1] & 0xFFF) != 0) + (v12[1] >> 12),
        v15,
        v16 + v15);
    }
    if ( ((v13 + 4095) & 0xFFFFFFFFFFFFF000uLL) == v13
      && ((v14 + 4095) & 0xFFFFFFFFFFFFF000uLL) == v14
      && v14 + v13 >= v13 )
    {
      v17 = *(_QWORD *)(BugCheckParameter3 + 712);
      if ( *(_QWORD *)(v17 + 16) + v13 >= *(_QWORD *)(v17 + 16) && v11 && v12 )
      {
        if ( v16 + v15 <= *(_QWORD *)(v17 + 24) )
        {
          v5 = 0;
          v18 = *v11 == 0;
          v11[1] = *(_DWORD *)v17;
          if ( !v18 )
          {
            v19 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 712) + 16LL);
            *((_QWORD *)v11 + 2) = v16;
            *((_QWORD *)v11 + 1) = v15 + v19;
          }
        }
        else
        {
          v5 = -1073741807;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return v5;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              44,
              WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
              BugCheckParameter3,
              -1073741807);
        }
        goto LABEL_43;
      }
    }
    v5 = -1073741811;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v5;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 43;
      goto LABEL_6;
    }
  }
  else
  {
    v5 = -1073741811;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v5;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 39;
LABEL_6:
      WPP_SF_qD(
        v6->AttachedDevice,
        v7,
        WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
        BugCheckParameter3,
        -1073741811);
    }
  }
LABEL_43:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      45,
      WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
      v5,
      BugCheckParameter3);
  }
  return v5;
}

```

## disassembly

```asm
0x1400470d4  mov     [rsp+arg_10], r8
0x1400470d9  push    rbx
0x1400470da  push    rbp
0x1400470db  push    rsi
0x1400470dc  push    rdi
0x1400470dd  push    r12
0x1400470df  push    r13
0x1400470e1  push    r14
0x1400470e3  push    r15
0x1400470e5  sub     rsp, 78h
0x1400470e9  mov     rdi, rdx
0x1400470ec  mov     rdx, [rcx+0B8h]
0x1400470f3  cmp     dword ptr [rdx+10h], 18h
0x1400470f7  jnb     short loc_140047150
0x1400470f9  mov     r8d, 0C000000Dh
0x1400470ff  mov     ebx, r8d
0x140047102  mov     rcx, cs:WPP_GLOBAL_Control
0x140047109  lea     rsi, WPP_GLOBAL_Control
0x140047110  cmp     rcx, rsi
0x140047113  jz      loc_14004741D
0x140047119  mov     eax, [rcx+2Ch]
0x14004711c  test    al, 1
0x14004711e  jz      loc_1400473E6
0x140047124  cmp     byte ptr [rcx+29h], 1
0x140047128  jb      loc_1400473E6
0x14004712e  mov     edx, 27h ; '''
0x140047133  mov     dword ptr [rsp+0B8h+BugCheckParameter4], r8d
0x140047138  mov     rcx, [rcx+18h]
0x14004713c  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x140047143  mov     r9, rdi
0x140047146  call    WPP_SF_qD
0x14004714b  jmp     loc_1400473E6
0x140047150  mov     r11, [rdi+2C8h]
0x140047157  test    r11, r11
0x14004715a  jz      loc_1400473A4
0x140047160  mov     r10d, [r11]
0x140047163  test    r10d, r10d
0x140047166  jz      loc_1400473A4
0x14004716c  cmp     r10d, 1
0x140047170  jz      short loc_140047194
0x140047172  mov     [rsp+0B8h+BugCheckParameter4], rcx; BugCheckParameter4
0x140047177  mov     r8d, r10d; BugCheckParameter2
0x14004717a  mov     ecx, 27h ; '''; BugCheckCode
0x14004717f  mov     r9, rdi; BugCheckParameter3
0x140047182  mov     edx, 908B5h; BugCheckParameter1
0x140047187  call    cs:__imp_KeBugCheckEx
0x140047194  mov     eax, [rdx+8]
0x140047197  cmp     eax, 8
0x14004719a  jb      loc_14004736D
0x1400471a0  mov     rbp, [rcx+70h]
0x1400471a4  mov     ecx, [rbp+0]
0x1400471a7  shl     rcx, 4
0x1400471ab  add     rcx, 8
0x1400471af  cmp     rax, rcx
0x1400471b2  jb      loc_14004736D
0x1400471b8  mov     r13, [rdx+20h]
0x1400471bc  mov     ecx, 0
0x1400471c1  mov     edx, 0FFFh
0x1400471c6  mov     rbx, [r13+0]
0x1400471ca  mov     r14, [r13+8]
0x1400471ce  test    rdx, rbx
0x1400471d1  mov     r15, rbx
0x1400471d4  mov     r12, r14
0x1400471d7  setnz   cl
0x1400471da  shr     r15, 0Ch
0x1400471de  add     r15, rcx
0x1400471e1  mov     ecx, 0
0x1400471e6  test    rdx, r14
0x1400471e9  setnz   cl
0x1400471ec  shr     r12, 0Ch
0x1400471f0  add     r12, rcx
0x1400471f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400471fa  lea     rsi, WPP_GLOBAL_Control
0x140047201  cmp     rcx, rsi
0x140047204  jz      short loc_14004726F
0x140047206  test    dword ptr [rcx+2Ch], 100h
0x14004720d  jz      short loc_14004726F
0x14004720f  cmp     byte ptr [rcx+29h], 2
0x140047213  jb      short loc_14004726F
0x140047215  mov     r9, [r11+18h]
0x140047219  lea     rax, [r12+r15]
0x14004721d  mov     r8, [r11+10h]
0x140047221  mov     rcx, [rcx+18h]
0x140047225  mov     [rsp+0B8h+var_50], rax
0x14004722a  mov     eax, [r13+10h]
0x14004722e  mov     [rsp+0B8h+var_58], r15
0x140047233  lea     rdx, [r9+r8]
0x140047237  mov     [rsp+0B8h+var_60], r12
0x14004723c  mov     [rsp+0B8h+var_68], eax
0x140047240  mov     rax, [r11+8]
0x140047244  mov     [rsp+0B8h+var_70], rdx
0x140047249  mov     [rsp+0B8h+var_78], r8
0x14004724e  mov     [rsp+0B8h+var_80], r9
0x140047253  mov     r9, [rsp+0B8h+arg_10]
0x14004725b  mov     [rsp+0B8h+var_88], rax
0x140047260  mov     [rsp+0B8h+var_90], r10d
0x140047265  mov     [rsp+0B8h+BugCheckParameter4], rdi
0x14004726a  call    WPP_SF_qqDiiiiDiii
0x14004726f  lea     rax, [rbx+0FFFh]
0x140047276  mov     rcx, 0FFFFFFFFFFFFF000h
0x14004727d  and     rax, rcx
0x140047280  cmp     rax, rbx
0x140047283  jnz     loc_140047335
0x140047289  lea     rax, [r14+0FFFh]
0x140047290  and     rax, rcx
0x140047293  cmp     rax, r14
0x140047296  jnz     loc_140047335
0x14004729c  lea     rax, [r14+rbx]
0x1400472a0  cmp     rax, rbx
0x1400472a3  jb      loc_140047335
0x1400472a9  mov     rdx, [rdi+2C8h]
0x1400472b0  mov     rcx, [rdx+10h]
0x1400472b4  lea     rax, [rcx+rbx]
0x1400472b8  cmp     rax, rcx
0x1400472bb  jb      short loc_140047335
0x1400472bd  test    rbp, rbp
0x1400472c0  jz      short loc_140047335
0x1400472c2  test    r13, r13
0x1400472c5  jz      short loc_140047335
0x1400472c7  lea     rax, [r12+r15]
0x1400472cb  cmp     rax, [rdx+18h]
0x1400472cf  jbe     short loc_140047309
0x1400472d1  mov     ebx, 0C0000011h
0x1400472d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400472dd  cmp     rcx, rsi
0x1400472e0  jz      loc_14004741D
0x1400472e6  mov     eax, [rcx+2Ch]
0x1400472e9  test    al, 1
0x1400472eb  jz      loc_1400473E6
0x1400472f1  cmp     byte ptr [rcx+29h], 1
0x1400472f5  jb      loc_1400473E6
0x1400472fb  mov     edx, 2Ch ; ','
0x140047300  mov     dword ptr [rsp+0B8h+BugCheckParameter4], ebx
0x140047304  jmp     loc_140047138
0x140047309  mov     eax, [rdx]
0x14004730b  xor     ebx, ebx
0x14004730d  cmp     dword ptr [rbp+0], 1
0x140047311  mov     [rbp+4], eax
0x140047314  jb      loc_1400473E6
0x14004731a  mov     rax, [rdi+2C8h]
0x140047321  mov     rax, [rax+10h]
0x140047325  add     rax, r15
0x140047328  mov     [rbp+10h], r12
0x14004732c  mov     [rbp+8], rax
0x140047330  jmp     loc_1400473E6
0x140047335  mov     r8d, 0C000000Dh
0x14004733b  mov     ebx, r8d
0x14004733e  mov     rcx, cs:WPP_GLOBAL_Control
0x140047345  cmp     rcx, rsi
0x140047348  jz      loc_14004741D
0x14004734e  mov     eax, [rcx+2Ch]
0x140047351  test    al, 1
0x140047353  jz      loc_1400473E6
0x140047359  cmp     byte ptr [rcx+29h], 1
0x14004735d  jb      loc_1400473E6
0x140047363  mov     edx, 2Bh ; '+'
0x140047368  jmp     loc_140047133
0x14004736d  mov     r8d, 0C000000Dh
0x140047373  mov     ebx, r8d
0x140047376  mov     rcx, cs:WPP_GLOBAL_Control
0x14004737d  lea     rsi, WPP_GLOBAL_Control
0x140047384  cmp     rcx, rsi
0x140047387  jz      loc_14004741D
0x14004738d  mov     eax, [rcx+2Ch]
0x140047390  test    al, 1
0x140047392  jz      short loc_1400473E6
0x140047394  cmp     byte ptr [rcx+29h], 1
0x140047398  jb      short loc_1400473E6
0x14004739a  mov     edx, 29h ; ')'
0x14004739f  jmp     loc_140047133
0x1400473a4  mov     ebx, 0C00000AFh
0x1400473a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400473b0  lea     rsi, WPP_GLOBAL_Control
0x1400473b7  cmp     rcx, rsi
0x1400473ba  jz      short loc_14004741D
0x1400473bc  mov     eax, [rcx+2Ch]
0x1400473bf  test    al, 1
0x1400473c1  jz      short loc_1400473E6
0x1400473c3  cmp     byte ptr [rcx+29h], 1
0x1400473c7  jb      short loc_1400473E6
0x1400473c9  mov     rcx, [rcx+18h]
0x1400473cd  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x1400473d4  mov     edx, 28h ; '('
0x1400473d9  mov     [rsp+0B8h+BugCheckParameter4], rdi
0x1400473de  mov     r9d, ebx
0x1400473e1  call    WPP_SF_dq
0x1400473e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400473ed  cmp     rcx, rsi
0x1400473f0  jz      short loc_14004741D
0x1400473f2  mov     edx, [rcx+2Ch]
0x1400473f5  test    dl, 1
0x1400473f8  jz      short loc_14004741D
0x1400473fa  cmp     byte ptr [rcx+29h], 2
0x1400473fe  jb      short loc_14004741D
0x140047400  mov     rcx, [rcx+18h]
0x140047404  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x14004740b  mov     edx, 2Dh ; '-'
0x140047410  mov     [rsp+0B8h+BugCheckParameter4], rdi
0x140047415  mov     r9d, ebx
0x140047418  call    WPP_SF_dq
0x14004741d  mov     eax, ebx
0x14004741f  add     rsp, 78h
0x140047423  pop     r15
0x140047425  pop     r14
0x140047427  pop     r13
0x140047429  pop     r12
0x14004742b  pop     rdi
0x14004742c  pop     rsi
0x14004742d  pop     rbp
0x14004742e  pop     rbx
0x14004742f  retn
```
