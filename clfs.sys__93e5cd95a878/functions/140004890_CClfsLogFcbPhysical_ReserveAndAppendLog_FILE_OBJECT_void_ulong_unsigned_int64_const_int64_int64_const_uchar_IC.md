# CClfsLogFcbPhysical::ReserveAndAppendLog(_FILE_OBJECT *,void *,ulong,unsigned __int64 const &,__int64 &,__int64 const &,uchar,IClfsRequestAsync *,_CLS_LSN const &,_IO_STATUS_BLOCK *,__int64 &,_CLS_LSN &,_CLS_LSN &,_CLS_LSN &)

- ea: `0x140004890`
- end: `0x140004c99`
- name: `?ReserveAndAppendLog@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@PEAXKAEB_KAEA_JAEB_JEPEAUIClfsRequestAsync@@AEBT_CLS_LSN@@PEAU_IO_STATUS_BLOCK@@3AEAT4@88@Z`
- size: `1033`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, struct _FILE_OBJECT *@<rdx>, void *@<r8>, unsigned int@<r9d>, const unsigned __int64 *, __int64 *, const __int64 *, char, struct IClfsRequestAsync *, const union _CLS_LSN *, struct _IO_STATUS_BLOCK *, __int64 *, union _CLS_LSN *, union _CLS_LSN *, union _CLS_LSN *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140003040`
- `0x140004890`
- `0x140004ca0`
- `0x14000ed64`
- `0x140017f20`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400048f2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400048f2`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140004a6f`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140004c8b`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140018a8c`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140004a6f`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140004c8b`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140018a8c`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::ReserveAndAppendLog(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int64 *a5,
        __int64 *a6,
        __int64 *a7,
        char a8,
        struct IClfsRequestAsync *a9,
        const union _CLS_LSN *a10,
        struct _IO_STATUS_BLOCK *a11,
        __int64 *a12,
        union _CLS_LSN *a13,
        union _CLS_LSN *a14,
        union _CLS_LSN *a15)
{
  ULONG_PTR v18; // rbx
  unsigned __int16 *v19; // r14
  unsigned int v20; // r15d
  struct _ERESOURCE *v21; // rsi
  BOOLEAN v22; // al
  int v23; // ecx
  unsigned int v24; // r15d
  char v25; // cl
  unsigned __int16 v26; // ax
  __int64 v27; // rax
  unsigned int v28; // ecx
  union _CLS_LSN *v29; // rdi
  char *v30; // r10
  unsigned int i; // eax
  char v32; // dl
  int v33; // eax
  BOOLEAN v35; // [rsp+80h] [rbp-58h]
  unsigned __int16 v36; // [rsp+84h] [rbp-54h]
  int v37; // [rsp+90h] [rbp-48h] BYREF
  PERESOURCE Resource; // [rsp+98h] [rbp-40h]
  CLFS_LSN v39[2]; // [rsp+A0h] [rbp-38h] BYREF

  v39[0] = CLFS_LSN_NULL;
  LODWORD(v18) = 0;
  v19 = 0;
  v37 = 0;
  v20 = 0;
  *a12 = 0;
  v21 = (struct _ERESOURCE *)((char *)this + 200);
  Resource = (PERESOURCE)((char *)this + 200);
  v22 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  v35 = v22;
  if ( !a4 )
    goto LABEL_13;
  if ( a3 )
  {
    v23 = *(_DWORD *)(*((_QWORD *)this + 89) + 144LL);
    if ( v23 )
      v24 = -v23 & (v23 + a4 - 1);
    else
      v24 = 0;
    v20 = v24 >> 9;
    v19 = a3;
    v25 = *((_BYTE *)this + 689);
    *((_DWORD *)a3 + 3) = 0;
    v26 = a3[2];
    if ( !v26
      || a3[3] < v26
      || v26 << 9 > a4
      || (*((_DWORD *)a3 + 4) & 1) != 0
      || (*((_BYTE *)a3 + 2) = v25,
          HIBYTE(v36) = v25,
          v27 = *((unsigned int *)a3 + 26),
          v28 = v27 + 2 * (a4 >> 9),
          v28 < (unsigned int)v27)
      || (v27 & 7) != 0
      || v28 > a4 )
    {
      LODWORD(v18) = -1072037878;
    }
    else
    {
      v30 = (char *)a3 + v27;
      for ( i = 0; i < a4 >> 9; ++i )
      {
        v32 = 4;
        if ( !i )
          v32 = 68;
        LOBYTE(v36) = v32;
        if ( a3[2] - 1 == i )
          LOBYTE(v36) = v32 | 0x20;
        *(_WORD *)&v30[2 * i] = a3[256 * i + 255];
        a3[256 * i + 255] = v36;
      }
      *((_DWORD *)a3 + 4) &= ~2u;
      *((_DWORD *)a3 + 4) |= 1u;
    }
    if ( (v18 & 0x80000000) != 0LL )
    {
LABEL_28:
      v22 = v35;
      goto LABEL_38;
    }
LABEL_13:
    LODWORD(v18) = CClfsLogFcbPhysical::AppendLog(this, a2, 0, a3, v20, 0, 1, a5, a6, a7, a9, a11, a12, a13, a14);
    if ( (v18 & 0x80000000) != 0LL )
    {
      if ( v19 )
        ClfsDecodeBlock((struct _CLFS_LOG_BLOCK_HEADER *)v19, a4 >> 9, *((_BYTE *)v19 + 2), 4u, (unsigned int *)&a12);
    }
    else
    {
      v29 = a15;
      *a15 = *(union _CLS_LSN *)((char *)this + 480);
      ExReleaseResourceForThreadLite((PERESOURCE)((char *)this + 200), (ERESOURCE_THREAD)KeGetCurrentThread());
      v22 = 0;
      v35 = 0;
      if ( !a8 )
      {
LABEL_15:
        v21 = Resource;
        goto LABEL_38;
      }
      v33 = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, CLFS_LSN *, struct IClfsRequestAsync *, _QWORD, int *))(*(_QWORD *)this + 192LL))(
              this,
              v39,
              a9,
              0,
              &v37);
      v18 = v33;
      if ( v33 >= 0 )
      {
        v21 = Resource;
        if ( v33 != 259 )
          *v29 = v39[0];
        goto LABEL_28;
      }
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          30,
          (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
          (unsigned int)"CClfsLogFcbPhysical::ReserveAndAppendLog",
          23,
          v33);
      }
      a11->Status = -1072037841;
      a11->Information = v18;
      LODWORD(v18) = -1072037841;
    }
    v22 = v35;
    goto LABEL_15;
  }
  LODWORD(v18) = -1073741789;
LABEL_38:
  if ( v22 )
    ExReleaseResourceForThreadLite(v21, (ERESOURCE_THREAD)KeGetCurrentThread());
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140004890  mov     r11, rsp
0x140004893  mov     [r11+18h], rbx
0x140004897  mov     [r11+20h], rsi
0x14000489b  mov     [r11+10h], rdx
0x14000489f  mov     [r11+8], rcx
0x1400048a3  push    rdi
0x1400048a4  push    r12
0x1400048a6  push    r13
0x1400048a8  push    r14
0x1400048aa  push    r15
0x1400048ac  sub     rsp, 0B0h
0x1400048b3  mov     r12d, r9d
0x1400048b6  mov     rdi, r8
0x1400048b9  mov     r13, rcx
0x1400048bc  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x1400048c3  mov     [r11-38h], rax
0x1400048c7  xor     ebx, ebx
0x1400048c9  mov     r14d, ebx
0x1400048cc  mov     [r11-48h], ebx
0x1400048d0  mov     r15d, ebx
0x1400048d3  mov     rax, [rsp+0D8h+arg_58]
0x1400048db  mov     [rax], rbx
0x1400048de  lea     rsi, [rcx+0C8h]
0x1400048e5  mov     [rsp+0D8h+Resource], rsi
0x1400048ed  mov     dl, 1; Wait
0x1400048ef  mov     rcx, rsi; Resource
0x1400048f2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400048f9  nop     dword ptr [rax+rax+00h]
0x1400048fe  mov     [rsp+0D8h+var_58], al
0x140004905  test    r12d, r12d
0x140004908  jz      loc_1400049B0
0x14000490e  test    rdi, rdi
0x140004911  jz      loc_140004B9D
0x140004917  mov     rax, [r13+2C8h]
0x14000491e  mov     ecx, [rax+90h]
0x140004924  test    ecx, ecx
0x140004926  jz      loc_140004B95
0x14000492c  lea     r15d, [r12-1]
0x140004931  add     r15d, ecx
0x140004934  neg     ecx
0x140004936  and     r15d, ecx
0x140004939  shr     r15d, 9
0x14000493d  mov     r14, rdi
0x140004940  movzx   ecx, byte ptr [r13+2B1h]
0x140004948  mov     [rdi+0Ch], ebx
0x14000494b  mov     [rsp+0D8h+var_54], 0
0x140004955  movzx   eax, word ptr [rdi+4]
0x140004959  test    ax, ax
0x14000495c  jz      short loc_14000499A
0x14000495e  cmp     [rdi+6], ax
0x140004962  jb      short loc_14000499A
0x140004964  movzx   eax, ax
0x140004967  shl     eax, 9
0x14000496a  cmp     eax, r12d
0x14000496d  ja      short loc_14000499A
0x14000496f  mov     eax, [rdi+10h]
0x140004972  test    al, 1
0x140004974  jnz     short loc_14000499A
0x140004976  mov     [rdi+2], cl
0x140004979  mov     byte ptr [rsp+0D8h+var_54+1], cl
0x140004980  mov     r9d, r12d
0x140004983  shr     r9d, 9
0x140004987  mov     eax, [rdi+68h]
0x14000498a  lea     ecx, [rax+r9*2]
0x14000498e  cmp     ecx, eax
0x140004990  jb      short loc_14000499A
0x140004992  test    al, 7
0x140004994  jz      loc_140004A9E
0x14000499a  mov     ebx, 0C01A000Ah
0x14000499f  mov     [rsp+0D8h+var_50], ebx
0x1400049a6  test    ebx, ebx
0x1400049a8  js      loc_140004B88
0x1400049ae  xor     ebx, ebx
0x1400049b0  mov     rax, [rsp+0D8h+arg_68]
0x1400049b8  mov     [rsp+0D8h+var_68], rax; union _CLS_LSN *
0x1400049bd  mov     rax, [rsp+0D8h+arg_60]
0x1400049c5  mov     [rsp+0D8h+var_70], rax; union _CLS_LSN *
0x1400049ca  mov     rax, [rsp+0D8h+arg_58]
0x1400049d2  mov     [rsp+0D8h+var_78], rax; __int64 *
0x1400049d7  mov     rax, [rsp+0D8h+arg_50]
0x1400049df  mov     [rsp+0D8h+var_80], rax; struct _IO_STATUS_BLOCK *
0x1400049e4  mov     rsi, [rsp+0D8h+arg_40]
0x1400049ec  mov     [rsp+0D8h+var_88], rsi; struct IClfsRequestAsync *
0x1400049f1  mov     rax, [rsp+0D8h+arg_30]
0x1400049f9  mov     [rsp+0D8h+var_90], rax; __int64 *
0x1400049fe  mov     rax, [rsp+0D8h+arg_28]
0x140004a06  mov     [rsp+0D8h+var_98], rax; __int64 *
0x140004a0b  mov     rax, [rsp+0D8h+arg_20]
0x140004a13  mov     [rsp+0D8h+var_A0], rax; unsigned __int64 *
0x140004a18  mov     [rsp+0D8h+var_A8], 1; char
0x140004a1d  mov     [rsp+0D8h+var_B0], ebx; unsigned int
0x140004a21  mov     dword ptr [rsp+0D8h+var_B8], r15d; unsigned int
0x140004a26  mov     r9, rdi; void *
0x140004a29  xor     r8d, r8d; unsigned __int8
0x140004a2c  mov     rdx, [rsp+0D8h+arg_8]; struct _FILE_OBJECT *
0x140004a34  mov     rcx, r13; this
0x140004a37  call    ?AppendLog@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@EPEAXKKEAEB_KAEA_JAEB_JPEAUIClfsRequestAsync@@PEAU_IO_STATUS_BLOCK@@3AEAT_CLS_LSN@@7@Z; CClfsLogFcbPhysical::AppendLog(_FILE_OBJECT *,uchar,void *,ulong,ulong,uchar,unsigned __int64 const &,__int64 &,__int64 const &,IClfsRequestAsync *,_IO_STATUS_BLOCK *,__int64 &,_CLS_LSN &,_CLS_LSN &)
0x140004a3c  mov     ebx, eax
0x140004a3e  mov     [rsp+0D8h+var_50], eax
0x140004a45  test    eax, eax
0x140004a47  js      loc_140004BAE
0x140004a4d  mov     rax, [r13+1E0h]
0x140004a54  mov     rdi, [rsp+0D8h+arg_70]
0x140004a5c  mov     [rdi], rax
0x140004a5f  mov     rdx, gs:188h; ResourceThreadId
0x140004a68  lea     rcx, [r13+0C8h]; Resource
0x140004a6f  call    cs:__imp_ExReleaseResourceForThreadLite
0x140004a76  nop     dword ptr [rax+rax+00h]
0x140004a7b  xor     al, al
0x140004a7d  mov     [rsp+0D8h+var_58], al
0x140004a84  cmp     [rsp+0D8h+arg_38], al
0x140004a8b  jnz     loc_140004B38
0x140004a91  mov     rsi, [rsp+0D8h+Resource]
0x140004a99  jmp     loc_140004C5B
0x140004a9e  cmp     ecx, r12d
0x140004aa1  ja      loc_14000499A
0x140004aa7  lea     r10, [rdi+rax]
0x140004aab  mov     eax, ebx
0x140004aad  mov     [rsp+0D8h+var_4C], ebx
0x140004ab4  mov     r11d, 44h ; 'D'
0x140004aba  nop     word ptr [rax+rax+00h]
0x140004ac0  cmp     eax, r9d
0x140004ac3  jnb     short loc_140004B26
0x140004ac5  mov     byte ptr [rsp+0D8h+var_54], 4
0x140004acd  mov     edx, 4
0x140004ad2  test    eax, eax
0x140004ad4  cmovz   edx, r11d
0x140004ad8  mov     byte ptr [rsp+0D8h+var_54], dl
0x140004adf  movzx   ecx, word ptr [rdi+4]
0x140004ae3  dec     ecx
0x140004ae5  cmp     ecx, eax
0x140004ae7  jnz     short loc_140004AF3
0x140004ae9  or      dl, 20h
0x140004aec  mov     byte ptr [rsp+0D8h+var_54], dl
0x140004af3  mov     ecx, eax
0x140004af5  shl     ecx, 9
0x140004af8  mov     r8d, ecx
0x140004afb  mov     edx, eax
0x140004afd  movzx   ecx, word ptr [rcx+rdi+1FEh]
0x140004b05  mov     [r10+rdx*2], cx
0x140004b0a  movzx   ecx, [rsp+0D8h+var_54]
0x140004b12  mov     [r8+rdi+1FEh], cx
0x140004b1b  inc     eax
0x140004b1d  mov     [rsp+0D8h+var_4C], eax
0x140004b24  jmp     short loc_140004AC0
0x140004b26  and     dword ptr [rdi+10h], 0FFFFFFFDh
0x140004b2a  mov     eax, [rdi+10h]
0x140004b2d  or      eax, 1
0x140004b30  mov     [rdi+10h], eax
0x140004b33  jmp     loc_14000499F
0x140004b38  mov     rax, [r13+0]
0x140004b3c  mov     rax, [rax+0C0h]
0x140004b43  lea     rcx, [rsp+0D8h+var_48]
0x140004b4b  mov     [rsp+0D8h+var_B8], rcx
0x140004b50  xor     r9d, r9d
0x140004b53  mov     r8, rsi
0x140004b56  lea     rdx, [rsp+0D8h+var_38]
0x140004b5e  mov     rcx, r13
0x140004b61  call    _guard_dispatch_icall
0x140004b66  movsxd  rbx, eax
0x140004b69  mov     [rsp+0D8h+var_50], ebx
0x140004b70  test    eax, eax
0x140004b72  js      short loc_140004BE4
0x140004b74  mov     rsi, [rsp+0D8h+Resource]
0x140004b7c  cmp     ebx, 103h
0x140004b82  jnz     loc_140004C4B
0x140004b88  movzx   eax, [rsp+0D8h+var_58]
0x140004b90  jmp     loc_140004C5B
0x140004b95  mov     r15d, ebx
0x140004b98  jmp     loc_140004939
0x140004b9d  mov     ebx, 0C0000023h
0x140004ba2  mov     [rsp+0D8h+var_50], ebx
0x140004ba9  jmp     loc_140004C5B
0x140004bae  test    r14, r14
0x140004bb1  jz      short loc_140004BD7
0x140004bb3  shr     r12d, 9
0x140004bb7  lea     rax, [rsp+0D8h+arg_58]
0x140004bbf  mov     [rsp+0D8h+var_B8], rax; unsigned int *
0x140004bc4  mov     r9b, 4; unsigned __int8
0x140004bc7  movzx   r8d, byte ptr [r14+2]; unsigned __int8
0x140004bcc  mov     edx, r12d; unsigned int
0x140004bcf  mov     rcx, r14; struct _CLFS_LOG_BLOCK_HEADER *
0x140004bd2  call    ?ClfsDecodeBlock@@YAJPEAU_CLFS_LOG_BLOCK_HEADER@@KEEAEAK@Z; ClfsDecodeBlock(_CLFS_LOG_BLOCK_HEADER *,ulong,uchar,uchar,ulong &)
0x140004bd7  movzx   eax, [rsp+0D8h+var_58]
0x140004bdf  jmp     loc_140004A91
0x140004be4  lea     rax, WPP_GLOBAL_Control
0x140004beb  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bf2  cmp     rcx, rax
0x140004bf5  jz      short loc_140004C28
0x140004bf7  test    dword ptr [rcx+2Ch], 8000000h
0x140004bfe  jz      short loc_140004C28
0x140004c00  mov     edx, 1Eh
0x140004c05  mov     [rsp+0D8h+var_B0], ebx
0x140004c09  mov     dword ptr [rsp+0D8h+var_B8], 3C17h
0x140004c11  lea     r9, aCclfslogfcbphy_5; "CClfsLogFcbPhysical::ReserveAndAppendLo"...
0x140004c18  lea     r8, WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids
0x140004c1f  mov     rcx, [rcx+18h]
0x140004c23  call    WPP_SF_slD
0x140004c28  mov     rcx, [rsp+0D8h+arg_50]
0x140004c30  mov     dword ptr [rcx], 0C01A002Fh
0x140004c36  mov     rax, rbx
0x140004c39  mov     [rcx+8], rbx
0x140004c3d  mov     ebx, 0C01A002Fh
0x140004c42  mov     [rsp+0D8h+var_50], ebx
0x140004c49  jmp     short loc_140004BD7
0x140004c4b  mov     rax, qword ptr [rsp+0D8h+var_38]
0x140004c53  mov     [rdi], rax
0x140004c56  jmp     loc_140004B88
0x140004c5b  test    al, al
0x140004c5d  jnz     short loc_140004C7F
0x140004c5f  mov     eax, ebx
0x140004c61  lea     r11, [rsp+0D8h+var_28]
0x140004c69  mov     rbx, [r11+40h]
0x140004c6d  mov     rsi, [r11+48h]
0x140004c71  mov     rsp, r11
0x140004c74  pop     r15
0x140004c76  pop     r14
0x140004c78  pop     r13
0x140004c7a  pop     r12
0x140004c7c  pop     rdi
0x140004c7d  retn
0x140004c7f  mov     rdx, gs:188h; ResourceThreadId
0x140004c88  mov     rcx, rsi; Resource
0x140004c8b  call    cs:__imp_ExReleaseResourceForThreadLite
0x140004c92  nop     dword ptr [rax+rax+00h]
0x140004c97  jmp     short loc_140004C5F
0x140018a60  push    rbp
0x140018a62  sub     rsp, 80h
0x140018a69  mov     rbp, rdx
0x140018a6c  cmp     byte ptr [rbp+80h], 0
0x140018a73  jz      short loc_140018A9F
0x140018a75  mov     rdx, gs:188h; ResourceThreadId
0x140018a7e  mov     rcx, [rbp+0E0h]
0x140018a85  add     rcx, 0C8h; Resource
0x140018a8c  call    cs:__imp_ExReleaseResourceForThreadLite
0x140018a93  nop     dword ptr [rax+rax+00h]
0x140018a98  mov     byte ptr [rbp+80h], 0
0x140018a9f  add     rsp, 80h
0x140018aa6  pop     rbp
0x140018aa7  retn
```
