# EfsOpenFile

- ea: `0x1400501d0`
- end: `0x14005076e`
- name: `EfsOpenFile`
- size: `1438`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callees

- `0x140001010`
- `0x1400010b4`
- `0x14000c230`
- `0x14004e16c`
- `0x14004f910`
- `0x14004fc54`
- `0x1400501d0`
- `0x14005489c`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400502ad`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400502ad`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400504bd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400506c7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140050754`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006037d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400603b6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400603ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400504bd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400506c7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140050754`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006037d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400603b6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400603ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400504a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400506a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400506e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050710`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050736`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400504a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400506a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400506e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050710`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050736`

## pseudocode

```c
__int64 __fastcall EfsOpenFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        int a8,
        _QWORD *a9,
        _QWORD *a10)
{
  void *v11; // r14
  int v12; // r12d
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  int EfsData; // edi
  unsigned int v17; // eax
  void *v18; // rcx
  int EfsStreamInfo; // eax
  __int64 v20; // rcx
  __int64 v21; // r8
  void *v22; // r10
  int v23; // eax
  __int64 v24; // rcx
  int v25; // r13d
  __int64 v26; // rcx
  void *v27; // rcx
  unsigned int v28; // r8d
  unsigned int v29; // eax
  void *v30; // rcx
  _QWORD *v31; // rsi
  void *v32; // rcx
  _QWORD *v33; // rsi
  void *v34; // rcx
  size_t Size; // [rsp+38h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+40h] [rbp-A8h] BYREF
  void *Src; // [rsp+48h] [rbp-A0h] BYREF
  int v39; // [rsp+50h] [rbp-98h]
  __int64 v40; // [rsp+58h] [rbp-90h]
  _QWORD *v41; // [rsp+60h] [rbp-88h]
  _QWORD *v42; // [rsp+68h] [rbp-80h]
  _QWORD *v43; // [rsp+70h] [rbp-78h]
  __int64 v44; // [rsp+78h] [rbp-70h]
  __int64 v45; // [rsp+80h] [rbp-68h]
  char v46[32]; // [rsp+88h] [rbp-60h] BYREF
  unsigned int *v47; // [rsp+A8h] [rbp-40h]
  __int64 v48; // [rsp+B0h] [rbp-38h]

  v45 = a3;
  v44 = a1;
  v40 = a6;
  v41 = a10;
  v43 = a10;
  v37 = 0;
  Size = 0;
  v11 = 0;
  Src = 0;
  v12 = 0;
  if ( !byte_140017924 )
    return 3221225488LL;
  if ( _bittest16((const signed __int16 *)(a3 + 24), 0xEu) && (a4 & 0x15) == 0 )
    return 0;
  v14 = ExAllocateFromNPagedLookasideList(&Lookaside);
  v15 = v14;
  *a10 = v14;
  if ( !v14 )
    return 3221225626LL;
  EfsData = 0;
  v42 = v14;
  v14[1] = 0;
  v14[2] = 0;
  v14[3] = 0;
  *(_DWORD *)v14 = 0;
  *((_DWORD *)v14 + 1) = a5;
  if ( (a4 & 0xF) == 1 )
  {
    *(_DWORD *)v14 = -1073741823;
    if ( a2 )
    {
      EfsData = EfsReadEfsData(a2, v40, 0, (unsigned int)&Src, (__int64)&Size, (__int64)&Size + 4);
      v39 = EfsData;
      v29 = Size;
      v11 = Src;
      v12 = HIDWORD(Size);
    }
    else
    {
      v29 = v37;
    }
    if ( EfsData < 0 || v12 != 0x10000 )
      goto LABEL_46;
    v30 = v11;
    v15[2] = v11;
    v11 = 0;
    EfsStreamInfo = EfsGetEfsStreamInfo(v30, v29, 4);
    EfsData = EfsStreamInfo;
    if ( EfsStreamInfo < 0 )
    {
      v21 = 874;
      goto LABEL_17;
    }
LABEL_45:
    *((_DWORD *)v15 + 7) = 0;
    goto LABEL_46;
  }
  if ( (a4 & 0xF) != 2 )
  {
    if ( (a4 & 0xF) != 4 )
      goto LABEL_46;
    *(_DWORD *)v14 = -1073741822;
    if ( a2 )
    {
      EfsData = EfsReadEfsData(a2, v40, 0, (unsigned int)&Src, (__int64)&Size, (__int64)&Size + 4);
      v39 = EfsData;
      v17 = Size;
      v11 = Src;
      v12 = HIDWORD(Size);
    }
    else
    {
      v17 = v37;
    }
    if ( EfsData < 0 || v12 != 0x10000 )
      goto LABEL_46;
    v18 = v11;
    v15[2] = v11;
    v11 = 0;
    EfsStreamInfo = EfsGetEfsStreamInfo(v18, v17, 4);
    EfsData = EfsStreamInfo;
    if ( EfsStreamInfo < 0 )
    {
      v21 = 941;
LABEL_17:
      EfspTraceLogAssert(v20, 5, v21, (unsigned int)EfsStreamInfo);
      EfsData = -1073741790;
LABEL_46:
      LOBYTE(v25) = a4;
      goto LABEL_47;
    }
    goto LABEL_45;
  }
  EfsData = EfsReadEfsData(v44, v40, 0, (unsigned int)&Src, (__int64)&Size, (__int64)&Size + 4);
  if ( HIDWORD(Size) != 0x10000 )
  {
    if ( (unsigned int)dword_140017130 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140017130, 0x200000000000LL) )
    {
      v37 = v28;
      v47 = &v37;
      v48 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140017130, &unk_140010C67, 0, 0, 3, v46);
    }
    v11 = Src;
    goto LABEL_46;
  }
  v22 = Src;
  v15[1] = Src;
  v11 = 0;
  *(_DWORD *)v15 = 4;
  if ( *a9 )
  {
    *(_DWORD *)v15 = 536870916;
    if ( (unsigned __int8)EfsIsKeyDplWrapped(a9) )
    {
      if ( EfsData < 0 )
        EfspTraceLogAssert(v26, 5, 724, (unsigned int)EfsData);
      v27 = (void *)v15[1];
      if ( v27 )
      {
        ExFreePoolWithTag(v27, 0);
        v15[1] = 0;
      }
      ExFreeToNPagedLookasideList(&Lookaside, v15);
      *v41 = 0;
      return 3221225506LL;
    }
  }
  else
  {
    *(_DWORD *)v15 = 1073741828;
  }
  v23 = EfsGetEfsStreamInfo(v22, (unsigned int)Size, 4);
  EfsData = v23;
  if ( v23 >= 0 )
  {
    *((_DWORD *)v15 + 6) = 0;
    v25 = a4;
    if ( (a4 & 0x400) == 0 && (a4 & 0x100) != 0 )
    {
      EfsData = -1073741790;
      EfspTraceLogAssert(v24, 5, 765, 3221225506LL);
    }
  }
  else
  {
    EfspTraceLogAssert(v24, 5, 750, (unsigned int)v23);
    EfsData = -1073741790;
    v25 = a4;
  }
  if ( (v25 & 0x10000) != 0 )
    *(_DWORD *)v15 |= 0x80000000;
LABEL_47:
  if ( (*(_BYTE *)(v45 + 24) & 4) != 0 && (v25 & 5) != 0 )
  {
    v31 = v41;
    if ( *v41 )
    {
      v32 = (void *)v15[1];
      if ( v32 )
      {
        ExFreePoolWithTag(v32, 0);
        v15[1] = 0;
      }
      ExFreeToNPagedLookasideList(&Lookaside, v15);
      *v31 = 0;
    }
    if ( v11 )
      ExFreePoolWithTag(v11, 0);
    return 0;
  }
  if ( *(_DWORD *)v15 )
    EfsTriggerServiceStart();
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( EfsData < 0 )
  {
    v33 = v41;
    if ( *v41 )
    {
      v34 = (void *)v15[1];
      if ( v34 )
      {
        ExFreePoolWithTag(v34, 0);
        v15[1] = 0;
      }
      ExFreeToNPagedLookasideList(&Lookaside, v15);
      *v33 = 0;
    }
  }
  return (unsigned int)EfsData;
}

```

## disassembly

```asm
0x1400501d0  mov     [rsp+arg_10], rbx
0x1400501d5  mov     [rsp+arg_18], rsi
0x1400501da  push    rdi
0x1400501db  push    r12
0x1400501dd  push    r13
0x1400501df  push    r14
0x1400501e1  push    r15
0x1400501e3  sub     rsp, 0C0h
0x1400501ea  mov     rax, cs:__security_cookie
0x1400501f1  xor     rax, rsp
0x1400501f4  mov     [rsp+0E8h+var_30], rax
0x1400501fc  mov     [rsp+0E8h+var_B8], r9d
0x140050201  mov     [rsp+0E8h+var_68], r8
0x140050209  mov     r15, rdx
0x14005020c  mov     [rsp+0E8h+var_70], rcx
0x140050211  mov     rax, [rsp+0E8h+arg_28]
0x140050219  mov     [rsp+0E8h+var_90], rax
0x14005021e  mov     r13, [rsp+0E8h+arg_40]
0x140050226  mov     rdi, [rsp+0E8h+arg_48]
0x14005022e  mov     [rsp+0E8h+var_88], rdi
0x140050233  mov     [rsp+0E8h+var_78], rdi
0x140050238  xor     eax, eax
0x14005023a  mov     [rsp+0E8h+var_A8], eax
0x14005023e  mov     dword ptr [rsp+0E8h+Size], eax
0x140050242  xor     r14d, r14d
0x140050245  mov     [rsp+0E8h+Src], r14
0x14005024a  xor     r12d, r12d
0x14005024d  mov     dword ptr [rsp+0E8h+Size+4], r12d
0x140050252  xor     esi, esi
0x140050254  mov     [rsp+0E8h+var_B4], esi
0x140050258  cmp     cs:byte_140017924, al
0x14005025e  jnz     short loc_140050293
0x140050260  mov     eax, 0C0000010h
0x140050265  mov     rcx, [rsp+0E8h+var_30]
0x14005026d  xor     rcx, rsp; StackCookie
0x140050270  call    __security_check_cookie
0x140050275  lea     r11, [rsp+0E8h+var_28]
0x14005027d  mov     rbx, [r11+40h]
0x140050281  mov     rsi, [r11+48h]
0x140050285  mov     rsp, r11
0x140050288  pop     r15
0x14005028a  pop     r14
0x14005028c  pop     r13
0x14005028e  pop     r12
0x140050290  pop     rdi
0x140050291  retn
0x140050293  bt      word ptr [r8+18h], 0Eh
0x14005029a  jnb     short loc_1400502A6
0x14005029c  test    r9b, 15h
0x1400502a0  jz      loc_1400506F0
0x1400502a6  lea     rcx, Lookaside; Lookaside
0x1400502ad  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400502b4  nop     dword ptr [rax+rax+00h]
0x1400502b9  mov     rbx, rax
0x1400502bc  mov     [rdi], rax
0x1400502bf  test    rax, rax
0x1400502c2  jnz     short loc_1400502CB
0x1400502c4  mov     eax, 0C000009Ah
0x1400502c9  jmp     short loc_140050265
0x1400502cb  xor     edi, edi
0x1400502cd  mov     [rsp+0E8h+var_80], rbx
0x1400502d2  mov     [rax+8], rsi
0x1400502d6  mov     [rax+10h], rsi
0x1400502da  mov     [rax+18h], rsi
0x1400502de  mov     [rax], esi
0x1400502e0  mov     eax, [rsp+0E8h+arg_20]
0x1400502e7  mov     [rbx+4], eax
0x1400502ea  mov     eax, [rsp+0E8h+var_B8]
0x1400502ee  and     eax, 0Fh
0x1400502f1  sub     eax, 1
0x1400502f4  jz      loc_1400505DE
0x1400502fa  sub     eax, 1
0x1400502fd  jz      loc_1400503BE
0x140050303  cmp     eax, 2
0x140050306  jnz     loc_140050675
0x14005030c  mov     dword ptr [rbx], 0C0000002h
0x140050312  test    r15, r15
0x140050315  jz      short loc_140050356
0x140050317  lea     rax, [rsp+0E8h+Size+4]
0x14005031c  mov     [rsp+0E8h+var_C0], rax
0x140050321  lea     rax, [rsp+0E8h+Size]
0x140050326  mov     qword ptr [rsp+0E8h+var_C8], rax
0x14005032b  lea     r9, [rsp+0E8h+Src]
0x140050330  xor     r8d, r8d
0x140050333  mov     rdx, [rsp+0E8h+var_90]
0x140050338  mov     rcx, r15
0x14005033b  call    EfsReadEfsData
0x140050340  mov     edi, eax
0x140050342  mov     [rsp+0E8h+var_98], eax
0x140050346  mov     eax, dword ptr [rsp+0E8h+Size]
0x14005034a  mov     r14, [rsp+0E8h+Src]
0x14005034f  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x140050354  jmp     short loc_14005035A
0x140050356  mov     eax, [rsp+0E8h+var_A8]
0x14005035a  test    edi, edi
0x14005035c  js      loc_140050675
0x140050362  mov     r15d, 10000h
0x140050368  cmp     r12d, r15d
0x14005036b  jnz     loc_140050675
0x140050371  mov     rcx, r14; Src
0x140050374  mov     [rbx+10h], rcx
0x140050378  xor     r14d, r14d
0x14005037b  mov     [rsp+0E8h+var_C8], 4; int
0x140050383  lea     r9, [rsp+0E8h+var_B4]
0x140050388  lea     r8d, [r14+1]
0x14005038c  mov     edx, eax; Size
0x14005038e  call    EfsGetEfsStreamInfo
0x140050393  mov     edi, eax
0x140050395  test    eax, eax
0x140050397  jns     loc_14005066E
0x14005039d  mov     r8d, 3ADh
0x1400503a3  mov     edx, 5
0x1400503a8  mov     r9d, eax
0x1400503ab  call    EfspTraceLogAssert
0x1400503b0  mov     edi, 0C0000022h
0x1400503b5  mov     esi, [rsp+0E8h+var_B4]
0x1400503b9  jmp     loc_140050675
0x1400503be  lea     rax, [rsp+0E8h+Size+4]
0x1400503c3  mov     [rsp+0E8h+var_C0], rax
0x1400503c8  lea     rax, [rsp+0E8h+Size]
0x1400503cd  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1400503d2  lea     r9, [rsp+0E8h+Src]
0x1400503d7  xor     r8d, r8d
0x1400503da  mov     rdx, [rsp+0E8h+var_90]
0x1400503df  mov     rcx, [rsp+0E8h+var_70]
0x1400503e4  call    EfsReadEfsData
0x1400503e9  mov     edi, eax
0x1400503eb  mov     r8d, dword ptr [rsp+0E8h+Size+4]
0x1400503f0  mov     r15d, 10000h
0x1400503f6  cmp     r8d, r15d
0x1400503f9  jnz     loc_140050563
0x1400503ff  mov     r10, [rsp+0E8h+Src]
0x140050404  mov     [rbx+8], r10
0x140050408  xor     r14d, r14d
0x14005040b  mov     dword ptr [rbx], 4
0x140050411  cmp     [r13+0], r14
0x140050415  jnz     short loc_14005046F
0x140050417  mov     dword ptr [rbx], 40000004h
0x14005041d  mov     [rsp+0E8h+var_C8], 4; int
0x140050425  lea     r9, [rsp+0E8h+var_B4]
0x14005042a  mov     r12d, 1
0x140050430  mov     r8d, r12d
0x140050433  mov     edx, dword ptr [rsp+0E8h+Size]; Size
0x140050437  mov     rcx, r10; Src
0x14005043a  call    EfsGetEfsStreamInfo
0x14005043f  mov     edi, eax
0x140050441  test    eax, eax
0x140050443  jns     loc_1400504DB
0x140050449  mov     r9d, eax
0x14005044c  lea     edx, [r12+4]
0x140050451  mov     r8d, 2EEh
0x140050457  call    EfspTraceLogAssert
0x14005045c  mov     edi, 0C0000022h
0x140050461  mov     esi, [rsp+0E8h+var_B4]
0x140050465  mov     r13d, [rsp+0E8h+var_B8]
0x14005046a  jmp     loc_140050526
0x14005046f  mov     dword ptr [rbx], 20000004h
0x140050475  mov     rcx, r13
0x140050478  call    EfsIsKeyDplWrapped
0x14005047d  test    al, al
0x14005047f  jz      short loc_14005041D
0x140050481  test    edi, edi
0x140050483  jns     short loc_140050498
0x140050485  mov     r9d, edi
0x140050488  mov     edx, 5
0x14005048d  mov     r8d, 2D4h
0x140050493  call    EfspTraceLogAssert
0x140050498  mov     rcx, [rbx+8]; P
0x14005049c  test    rcx, rcx
0x14005049f  jz      short loc_1400504B3
0x1400504a1  xor     edx, edx; Tag
0x1400504a3  call    cs:__imp_ExFreePoolWithTag
0x1400504aa  nop     dword ptr [rax+rax+00h]
0x1400504af  mov     [rbx+8], r14
0x1400504b3  mov     rdx, rbx; Entry
0x1400504b6  lea     rcx, Lookaside; Lookaside
0x1400504bd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400504c4  nop     dword ptr [rax+rax+00h]
0x1400504c9  mov     rsi, [rsp+0E8h+var_88]
0x1400504ce  mov     [rsi], r14
0x1400504d1  mov     eax, 0C0000022h
0x1400504d6  jmp     loc_140050265
0x1400504db  mov     esi, [rsp+0E8h+var_B4]
0x1400504df  mov     [rbx+18h], esi
0x1400504e2  mov     r13d, [rsp+0E8h+var_B8]
0x1400504e7  bt      r13d, 0Ah
0x1400504ec  jb      short loc_140050526
0x1400504ee  bt      r13d, 8
0x1400504f3  jnb     short loc_140050502
0x1400504f5  cmp     esi, 3
0x1400504f8  jz      short loc_140050526
0x1400504fa  mov     r8d, 2FDh
0x140050500  jmp     short loc_140050514
0x140050502  cmp     esi, 3
0x140050505  jnz     short loc_140050526
0x140050507  bt      r13d, 9
0x14005050c  jb      short loc_140050526
0x14005050e  mov     r8d, 301h
0x140050514  mov     edi, 0C0000022h
0x140050519  mov     r9d, edi
0x14005051c  mov     edx, 5
0x140050521  call    EfspTraceLogAssert
0x140050526  test    r15d, r13d
0x140050529  jz      loc_14005067A
0x14005052f  xor     cl, cl
0x140050531  lea     eax, [rsi-1]
0x140050534  cmp     eax, r12d
0x140050537  ja      short loc_14005054E
0x140050539  mov     rax, [rbx+8]
0x14005053d  cmp     [rax+4], r12d
0x140050541  jnz     short loc_14005054E
0x140050543  test    byte ptr [rax+0Eh], 2
0x140050547  movzx   ecx, cl
0x14005054a  cmovnz  ecx, r12d
0x14005054e  test    cl, cl
0x140050550  jz      short loc_14005055A
0x140050552  mov     [rbx], r14d
0x140050555  jmp     loc_14005067A
0x14005055a  bts     dword ptr [rbx], 1Fh
0x14005055e  jmp     loc_14005067A
0x140050563  mov     eax, cs:dword_140017130
0x140050569  cmp     eax, 5
0x14005056c  jbe     short loc_1400505D4
0x14005056e  mov     rdx, 200000000000h
0x140050578  lea     rcx, dword_140017130
0x14005057f  call    _tlgKeywordOn
0x140050584  test    al, al
0x140050586  jz      short loc_1400505D4
0x140050588  mov     [rsp+0E8h+var_A8], r8d
0x14005058d  lea     rax, [rsp+0E8h+var_A8]
0x140050592  mov     [rsp+0E8h+var_40], rax
0x14005059a  mov     [rsp+0E8h+var_38], 4
0x1400505a6  lea     rax, [rsp+0E8h+var_60]
0x1400505ae  mov     [rsp+0E8h+var_C0], rax
0x1400505b3  mov     [rsp+0E8h+var_C8], 3
0x1400505bb  xor     r9d, r9d
0x1400505be  xor     r8d, r8d
0x1400505c1  lea     rdx, unk_140010C67
0x1400505c8  lea     rcx, dword_140017130
0x1400505cf  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400505d4  mov     r14, [rsp+0E8h+Src]
0x1400505d9  jmp     loc_140050675
0x1400505de  mov     dword ptr [rbx], 0C0000001h
0x1400505e4  test    r15, r15
0x1400505e7  jz      short loc_140050628
0x1400505e9  lea     rax, [rsp+0E8h+Size+4]
0x1400505ee  mov     [rsp+0E8h+var_C0], rax
0x1400505f3  lea     rax, [rsp+0E8h+Size]
0x1400505f8  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1400505fd  lea     r9, [rsp+0E8h+Src]
0x140050602  xor     r8d, r8d
0x140050605  mov     rdx, [rsp+0E8h+var_90]
0x14005060a  mov     rcx, r15
0x14005060d  call    EfsReadEfsData
0x140050612  mov     edi, eax
0x140050614  mov     [rsp+0E8h+var_98], eax
0x140050618  mov     eax, dword ptr [rsp+0E8h+Size]
0x14005061c  mov     r14, [rsp+0E8h+Src]
0x140050621  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x140050626  jmp     short loc_14005062C
0x140050628  mov     eax, [rsp+0E8h+var_A8]
0x14005062c  test    edi, edi
0x14005062e  js      short loc_140050675
0x140050630  mov     r15d, 10000h
0x140050636  cmp     r12d, r15d
0x140050639  jnz     short loc_140050675
0x14005063b  mov     rcx, r14; Src
0x14005063e  mov     [rbx+10h], rcx
0x140050642  xor     r14d, r14d
0x140050645  mov     [rsp+0E8h+var_C8], 4; int
0x14005064d  lea     r9, [rsp+0E8h+var_B4]
0x140050652  lea     r8d, [r14+1]
0x140050656  mov     edx, eax; Size
0x140050658  call    EfsGetEfsStreamInfo
0x14005065d  mov     edi, eax
0x14005065f  test    eax, eax
0x140050661  jns     short loc_14005066E
0x140050663  mov     r8d, 36Ah
0x140050669  jmp     loc_1400503A3
0x14005066e  mov     esi, [rsp+0E8h+var_B4]
0x140050672  mov     [rbx+1Ch], esi
0x140050675  mov     r13d, [rsp+0E8h+var_B8]
0x14005067a  mov     rax, [rsp+0E8h+var_68]
0x140050682  test    byte ptr [rax+18h], 4
0x140050686  jz      short loc_1400506F7
0x140050688  test    r13b, 5
0x14005068c  jz      short loc_1400506F7
0x14005068e  cmp     esi, 3
0x140050691  jz      short loc_1400506F7
0x140050693  mov     rsi, [rsp+0E8h+var_88]
0x140050698  cmp     qword ptr [rsi], 0
0x14005069c  jz      short loc_1400506DA
0x14005069e  mov     rcx, [rbx+8]; P
0x1400506a2  test    rcx, rcx
0x1400506a5  jz      short loc_1400506BD
0x1400506a7  xor     edx, edx; Tag
0x1400506a9  call    cs:__imp_ExFreePoolWithTag
0x1400506b0  nop     dword ptr [rax+rax+00h]
0x1400506b5  mov     qword ptr [rbx+8], 0
0x1400506bd  mov     rdx, rbx; Entry
  ... truncated ...
```
