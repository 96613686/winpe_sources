# RdbssStatisticsDatabaseRemove

- ea: `0x1400525b4`
- end: `0x1400527c8`
- name: `RdbssStatisticsDatabaseRemove`
- size: `532`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140064350`
- `0x140065390`
- `0x140065ca0`

## callees

- `0x140016e20`
- `0x140025740`
- `0x140025d00`
- `0x1400525b4`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14005266f`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14005266f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140052717`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140052717`

## pseudocode

```c
__int64 __fastcall RdbssStatisticsDatabaseRemove(__int64 *a1, __int64 a2, int a3, int a4, __int64 a5)
{
  __int64 v9; // r15
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 Buffer; // [rsp+48h] [rbp-40h] BYREF
  int Buffer_8; // [rsp+50h] [rbp-38h]
  int Buffer_12; // [rsp+54h] [rbp-34h]
  __int64 v19; // [rsp+58h] [rbp-30h]

  v9 = *a1;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqDDq(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      (unsigned int)&WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids,
      (_DWORD)a1,
      a2,
      a3,
      a4,
      a5,
      *a1);
  }
  (*(void (__fastcall **)(__int64, __int64))(v9 + 48))(v9, a1[4]);
  v19 = 0;
  Buffer = a2;
  Buffer_8 = a3;
  Buffer_12 = a4;
  v11 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 5), &Buffer);
  if ( v11 )
  {
    if ( v11[2] == a5 )
    {
      if ( RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 5), &Buffer) )
      {
        ((void (__fastcall *)(__int64))a1[2])(a5);
        --*((_DWORD *)a1 + 7);
        goto LABEL_23;
      }
      v10 = -1073740007;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_23;
      }
      v13 = 30;
    }
    else
    {
      v10 = -1073740007;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_23;
      }
      v13 = 29;
    }
    v14 = 3221227289LL;
    goto LABEL_10;
  }
  v10 = -1073741275;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v13 = 28;
    v14 = 3221226021LL;
LABEL_10:
    WPP_SF_d(v12->AttachedDevice, v13, &WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids, v14);
  }
LABEL_23:
  (*(void (__fastcall **)(__int64, __int64))(v9 + 56))(v9, a1[4]);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, &WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x1400525b4  mov     r11, rsp
0x1400525b7  mov     [r11+10h], rbx
0x1400525bb  mov     [r11+18h], rsi
0x1400525bf  mov     [r11+8], rcx
0x1400525c3  push    rdi
0x1400525c4  push    r12
0x1400525c6  push    r13
0x1400525c8  push    r14
0x1400525ca  push    r15
0x1400525cc  sub     rsp, 60h
0x1400525d0  mov     r14d, r9d
0x1400525d3  mov     r12d, r8d
0x1400525d6  mov     r13, rdx
0x1400525d9  mov     rsi, rcx
0x1400525dc  mov     r15, [rcx]
0x1400525df  mov     [rsp+88h+var_48], r15
0x1400525e4  xor     ebx, ebx
0x1400525e6  lea     rax, WPP_GLOBAL_Control
0x1400525ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400525f4  mov     edi, 2000h
0x1400525f9  cmp     rcx, rax
0x1400525fc  jz      short loc_140052637
0x1400525fe  test    [rcx+2Ch], edi
0x140052601  jz      short loc_140052637
0x140052603  cmp     byte ptr [rcx+29h], 4
0x140052607  jb      short loc_140052637
0x140052609  lea     edx, [rbx+1Bh]
0x14005260c  mov     rax, [rsp+88h+arg_20]
0x140052614  mov     [r11-50h], rax
0x140052618  mov     [r11-58h], r9d
0x14005261c  mov     [r11-60h], r8d
0x140052620  mov     [r11-68h], r13
0x140052624  mov     r9, rsi
0x140052627  lea     r8, WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids
0x14005262e  mov     rcx, [rcx+18h]
0x140052632  call    WPP_SF_qqDDq
0x140052637  mov     rax, [r15+30h]
0x14005263b  mov     rdx, [rsi+20h]
0x14005263f  mov     rcx, r15
0x140052642  call    _guard_dispatch_icall
0x140052647  nop
0x140052648  xorps   xmm0, xmm0
0x14005264b  xor     eax, eax
0x14005264d  movups  [rsp+88h+Buffer], xmm0
0x140052652  mov     [rsp+88h+var_30], rax
0x140052657  mov     qword ptr [rsp+88h+Buffer], r13
0x14005265c  mov     dword ptr [rsp+88h+Buffer+8], r12d
0x140052661  mov     dword ptr [rsp+88h+Buffer+0Ch], r14d
0x140052666  lea     rdx, [rsp+88h+Buffer]; Buffer
0x14005266b  lea     rcx, [rsi+28h]; Table
0x14005266f  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140052676  nop     dword ptr [rax+rax+00h]
0x14005267b  mov     rcx, rax
0x14005267e  test    rax, rax
0x140052681  jnz     short loc_1400526D0
0x140052683  mov     ebx, 0C0000225h
0x140052688  mov     rcx, cs:WPP_GLOBAL_Control
0x14005268f  lea     r14, WPP_GLOBAL_Control
0x140052696  cmp     rcx, r14
0x140052699  jz      loc_14005276C
0x14005269f  test    [rcx+2Ch], edi
0x1400526a2  jz      loc_14005276C
0x1400526a8  cmp     byte ptr [rcx+29h], 4
0x1400526ac  jb      loc_14005276C
0x1400526b2  lea     edx, [rax+1Ch]
0x1400526b5  mov     r9d, 0C0000225h
0x1400526bb  lea     r8, WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids
0x1400526c2  mov     rcx, [rcx+18h]
0x1400526c6  call    WPP_SF_d
0x1400526cb  jmp     loc_14005276C
0x1400526d0  mov     rax, [rsp+88h+arg_20]
0x1400526d8  cmp     [rcx+10h], rax
0x1400526dc  jz      short loc_14005270E
0x1400526de  mov     ebx, 0C0000719h
0x1400526e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400526ea  lea     r14, WPP_GLOBAL_Control
0x1400526f1  cmp     rcx, r14
0x1400526f4  jz      short loc_14005276C
0x1400526f6  test    [rcx+2Ch], edi
0x1400526f9  jz      short loc_14005276C
0x1400526fb  cmp     byte ptr [rcx+29h], 4
0x1400526ff  jb      short loc_14005276C
0x140052701  mov     edx, 1Dh
0x140052706  mov     r9d, 0C0000719h
0x14005270c  jmp     short loc_1400526BB
0x14005270e  lea     rdx, [rsp+88h+Buffer]; Buffer
0x140052713  lea     rcx, [rsi+28h]; Table
0x140052717  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14005271e  nop     dword ptr [rax+rax+00h]
0x140052723  test    al, al
0x140052725  jnz     short loc_140052751
0x140052727  mov     ebx, 0C0000719h
0x14005272c  mov     rcx, cs:WPP_GLOBAL_Control
0x140052733  lea     r14, WPP_GLOBAL_Control
0x14005273a  cmp     rcx, r14
0x14005273d  jz      short loc_14005276C
0x14005273f  test    [rcx+2Ch], edi
0x140052742  jz      short loc_14005276C
0x140052744  cmp     byte ptr [rcx+29h], 4
0x140052748  jb      short loc_14005276C
0x14005274a  mov     edx, 1Eh
0x14005274f  jmp     short loc_140052706
0x140052751  mov     rax, [rsi+10h]
0x140052755  mov     rcx, [rsp+88h+arg_20]
0x14005275d  call    _guard_dispatch_icall
0x140052762  dec     dword ptr [rsi+1Ch]
0x140052765  lea     r14, WPP_GLOBAL_Control
0x14005276c  mov     rax, [r15+38h]
0x140052770  mov     rdx, [rsi+20h]
0x140052774  mov     rcx, r15
0x140052777  call    _guard_dispatch_icall
0x14005277c  mov     rcx, cs:WPP_GLOBAL_Control
0x140052783  cmp     rcx, r14
0x140052786  jz      short loc_1400527AB
0x140052788  test    [rcx+2Ch], edi
0x14005278b  jz      short loc_1400527AB
0x14005278d  cmp     byte ptr [rcx+29h], 4
0x140052791  jb      short loc_1400527AB
0x140052793  mov     edx, 1Fh
0x140052798  mov     r9d, ebx
0x14005279b  lea     r8, WPP_042c655a530a30d3c5548d9c69ab37a5_Traceguids
0x1400527a2  mov     rcx, [rcx+18h]
0x1400527a6  call    WPP_SF_d
0x1400527ab  mov     eax, ebx
0x1400527ad  lea     r11, [rsp+88h+var_28]
0x1400527b2  mov     rbx, [r11+38h]
0x1400527b6  mov     rsi, [r11+40h]
0x1400527ba  mov     rsp, r11
0x1400527bd  pop     r15
0x1400527bf  pop     r14
0x1400527c1  pop     r13
0x1400527c3  pop     r12
0x1400527c5  pop     rdi
0x1400527c6  retn
0x14007bd4f  push    rbp
0x14007bd51  sub     rsp, 40h
0x14007bd55  mov     rbp, rdx
0x14007bd58  mov     rcx, [rbp+40h]
0x14007bd5c  mov     rax, [rcx+38h]
0x14007bd60  mov     rdx, [rbp+90h]
0x14007bd67  mov     rdx, [rdx+20h]
0x14007bd6b  call    _guard_dispatch_icall
0x14007bd70  nop
0x14007bd71  add     rsp, 40h
0x14007bd75  pop     rbp
0x14007bd76  retn
```
