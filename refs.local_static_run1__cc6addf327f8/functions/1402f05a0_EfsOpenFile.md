# EfsOpenFile

- ea: `0x1402f05a0`
- end: `0x1402f0b3e`
- name: `EfsOpenFile`
- size: `1438`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callees

- `0x140001008`
- `0x1400081e4`
- `0x1401f3fb0`
- `0x1402ee598`
- `0x1402efce0`
- `0x1402f0024`
- `0x1402f05a0`
- `0x1402f4cac`
- `0x1402f6d44`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f088d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f0a97`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f0b24`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a009`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a042`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a07b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f088d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f0a97`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f0b24`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a009`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a042`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a07b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402f067d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402f067d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0873`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0ab4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0ae0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0b06`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0873`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0ab4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0ae0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f0b06`

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
  if ( !byte_140268D64 )
    return 3221225488LL;
  if ( _bittest16((const signed __int16 *)(a3 + 24), 0xEu) && (a4 & 0x15) == 0 )
    return 0;
  v14 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.Dpc.DeferredRoutine);
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
    if ( (unsigned int)dword_1402472A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1402472A0, 0x200000000000LL) )
    {
      v37 = v28;
      v47 = &v37;
      v48 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_1402472A0, byte_1402254A3, 0, 0, 3, v46);
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
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.Dpc.DeferredRoutine, v15);
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
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.Dpc.DeferredRoutine, v15);
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
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.Dpc.DeferredRoutine, v15);
      *v33 = 0;
    }
  }
  return (unsigned int)EfsData;
}

```

## disassembly

```asm
0x1402f05a0  mov     [rsp+arg_10], rbx
0x1402f05a5  mov     [rsp+arg_18], rsi
0x1402f05aa  push    rdi
0x1402f05ab  push    r12
0x1402f05ad  push    r13
0x1402f05af  push    r14
0x1402f05b1  push    r15
0x1402f05b3  sub     rsp, 0C0h
0x1402f05ba  mov     rax, cs:__security_cookie
0x1402f05c1  xor     rax, rsp
0x1402f05c4  mov     [rsp+0E8h+var_30], rax
0x1402f05cc  mov     [rsp+0E8h+var_B8], r9d
0x1402f05d1  mov     [rsp+0E8h+var_68], r8
0x1402f05d9  mov     r15, rdx
0x1402f05dc  mov     [rsp+0E8h+var_70], rcx
0x1402f05e1  mov     rax, [rsp+0E8h+arg_28]
0x1402f05e9  mov     [rsp+0E8h+var_90], rax
0x1402f05ee  mov     r13, [rsp+0E8h+arg_40]
0x1402f05f6  mov     rdi, [rsp+0E8h+arg_48]
0x1402f05fe  mov     [rsp+0E8h+var_88], rdi
0x1402f0603  mov     [rsp+0E8h+var_78], rdi
0x1402f0608  xor     eax, eax
0x1402f060a  mov     [rsp+0E8h+var_A8], eax
0x1402f060e  mov     dword ptr [rsp+0E8h+Size], eax
0x1402f0612  xor     r14d, r14d
0x1402f0615  mov     [rsp+0E8h+Src], r14
0x1402f061a  xor     r12d, r12d
0x1402f061d  mov     dword ptr [rsp+0E8h+Size+4], r12d
0x1402f0622  xor     esi, esi
0x1402f0624  mov     [rsp+0E8h+var_B4], esi
0x1402f0628  cmp     cs:byte_140268D64, al
0x1402f062e  jnz     short loc_1402F0663
0x1402f0630  mov     eax, 0C0000010h
0x1402f0635  mov     rcx, [rsp+0E8h+var_30]
0x1402f063d  xor     rcx, rsp; StackCookie
0x1402f0640  call    __security_check_cookie
0x1402f0645  lea     r11, [rsp+0E8h+var_28]
0x1402f064d  mov     rbx, [r11+40h]
0x1402f0651  mov     rsi, [r11+48h]
0x1402f0655  mov     rsp, r11
0x1402f0658  pop     r15
0x1402f065a  pop     r14
0x1402f065c  pop     r13
0x1402f065e  pop     r12
0x1402f0660  pop     rdi
0x1402f0661  retn
0x1402f0663  bt      word ptr [r8+18h], 0Eh
0x1402f066a  jnb     short loc_1402F0676
0x1402f066c  test    r9b, 15h
0x1402f0670  jz      loc_1402F0AC0
0x1402f0676  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; Lookaside
0x1402f067d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1402f0684  nop     dword ptr [rax+rax+00h]
0x1402f0689  mov     rbx, rax
0x1402f068c  mov     [rdi], rax
0x1402f068f  test    rax, rax
0x1402f0692  jnz     short loc_1402F069B
0x1402f0694  mov     eax, 0C000009Ah
0x1402f0699  jmp     short loc_1402F0635
0x1402f069b  xor     edi, edi
0x1402f069d  mov     [rsp+0E8h+var_80], rbx
0x1402f06a2  mov     [rax+8], rsi
0x1402f06a6  mov     [rax+10h], rsi
0x1402f06aa  mov     [rax+18h], rsi
0x1402f06ae  mov     [rax], esi
0x1402f06b0  mov     eax, [rsp+0E8h+arg_20]
0x1402f06b7  mov     [rbx+4], eax
0x1402f06ba  mov     eax, [rsp+0E8h+var_B8]
0x1402f06be  and     eax, 0Fh
0x1402f06c1  sub     eax, 1
0x1402f06c4  jz      loc_1402F09AE
0x1402f06ca  sub     eax, 1
0x1402f06cd  jz      loc_1402F078E
0x1402f06d3  cmp     eax, 2
0x1402f06d6  jnz     loc_1402F0A45
0x1402f06dc  mov     dword ptr [rbx], 0C0000002h
0x1402f06e2  test    r15, r15
0x1402f06e5  jz      short loc_1402F0726
0x1402f06e7  lea     rax, [rsp+0E8h+Size+4]
0x1402f06ec  mov     [rsp+0E8h+var_C0], rax
0x1402f06f1  lea     rax, [rsp+0E8h+Size]
0x1402f06f6  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1402f06fb  lea     r9, [rsp+0E8h+Src]
0x1402f0700  xor     r8d, r8d
0x1402f0703  mov     rdx, [rsp+0E8h+var_90]
0x1402f0708  mov     rcx, r15
0x1402f070b  call    EfsReadEfsData
0x1402f0710  mov     edi, eax
0x1402f0712  mov     [rsp+0E8h+var_98], eax
0x1402f0716  mov     eax, dword ptr [rsp+0E8h+Size]
0x1402f071a  mov     r14, [rsp+0E8h+Src]
0x1402f071f  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x1402f0724  jmp     short loc_1402F072A
0x1402f0726  mov     eax, [rsp+0E8h+var_A8]
0x1402f072a  test    edi, edi
0x1402f072c  js      loc_1402F0A45
0x1402f0732  mov     r15d, 10000h
0x1402f0738  cmp     r12d, r15d
0x1402f073b  jnz     loc_1402F0A45
0x1402f0741  mov     rcx, r14; Src
0x1402f0744  mov     [rbx+10h], rcx
0x1402f0748  xor     r14d, r14d
0x1402f074b  mov     [rsp+0E8h+var_C8], 4; int
0x1402f0753  lea     r9, [rsp+0E8h+var_B4]
0x1402f0758  lea     r8d, [r14+1]
0x1402f075c  mov     edx, eax; Size
0x1402f075e  call    EfsGetEfsStreamInfo
0x1402f0763  mov     edi, eax
0x1402f0765  test    eax, eax
0x1402f0767  jns     loc_1402F0A3E
0x1402f076d  mov     r8d, 3ADh
0x1402f0773  mov     edx, 5
0x1402f0778  mov     r9d, eax
0x1402f077b  call    EfspTraceLogAssert
0x1402f0780  mov     edi, 0C0000022h
0x1402f0785  mov     esi, [rsp+0E8h+var_B4]
0x1402f0789  jmp     loc_1402F0A45
0x1402f078e  lea     rax, [rsp+0E8h+Size+4]
0x1402f0793  mov     [rsp+0E8h+var_C0], rax
0x1402f0798  lea     rax, [rsp+0E8h+Size]
0x1402f079d  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1402f07a2  lea     r9, [rsp+0E8h+Src]
0x1402f07a7  xor     r8d, r8d
0x1402f07aa  mov     rdx, [rsp+0E8h+var_90]
0x1402f07af  mov     rcx, [rsp+0E8h+var_70]
0x1402f07b4  call    EfsReadEfsData
0x1402f07b9  mov     edi, eax
0x1402f07bb  mov     r8d, dword ptr [rsp+0E8h+Size+4]
0x1402f07c0  mov     r15d, 10000h
0x1402f07c6  cmp     r8d, r15d
0x1402f07c9  jnz     loc_1402F0933
0x1402f07cf  mov     r10, [rsp+0E8h+Src]
0x1402f07d4  mov     [rbx+8], r10
0x1402f07d8  xor     r14d, r14d
0x1402f07db  mov     dword ptr [rbx], 4
0x1402f07e1  cmp     [r13+0], r14
0x1402f07e5  jnz     short loc_1402F083F
0x1402f07e7  mov     dword ptr [rbx], 40000004h
0x1402f07ed  mov     [rsp+0E8h+var_C8], 4; int
0x1402f07f5  lea     r9, [rsp+0E8h+var_B4]
0x1402f07fa  mov     r12d, 1
0x1402f0800  mov     r8d, r12d
0x1402f0803  mov     edx, dword ptr [rsp+0E8h+Size]; Size
0x1402f0807  mov     rcx, r10; Src
0x1402f080a  call    EfsGetEfsStreamInfo
0x1402f080f  mov     edi, eax
0x1402f0811  test    eax, eax
0x1402f0813  jns     loc_1402F08AB
0x1402f0819  mov     r9d, eax
0x1402f081c  lea     edx, [r12+4]
0x1402f0821  mov     r8d, 2EEh
0x1402f0827  call    EfspTraceLogAssert
0x1402f082c  mov     edi, 0C0000022h
0x1402f0831  mov     esi, [rsp+0E8h+var_B4]
0x1402f0835  mov     r13d, [rsp+0E8h+var_B8]
0x1402f083a  jmp     loc_1402F08F6
0x1402f083f  mov     dword ptr [rbx], 20000004h
0x1402f0845  mov     rcx, r13
0x1402f0848  call    EfsIsKeyDplWrapped
0x1402f084d  test    al, al
0x1402f084f  jz      short loc_1402F07ED
0x1402f0851  test    edi, edi
0x1402f0853  jns     short loc_1402F0868
0x1402f0855  mov     r9d, edi
0x1402f0858  mov     edx, 5
0x1402f085d  mov     r8d, 2D4h
0x1402f0863  call    EfspTraceLogAssert
0x1402f0868  mov     rcx, [rbx+8]; P
0x1402f086c  test    rcx, rcx
0x1402f086f  jz      short loc_1402F0883
0x1402f0871  xor     edx, edx; Tag
0x1402f0873  call    cs:__imp_ExFreePoolWithTag
0x1402f087a  nop     dword ptr [rax+rax+00h]
0x1402f087f  mov     [rbx+8], r14
0x1402f0883  mov     rdx, rbx; Entry
0x1402f0886  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; Lookaside
0x1402f088d  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f0894  nop     dword ptr [rax+rax+00h]
0x1402f0899  mov     rsi, [rsp+0E8h+var_88]
0x1402f089e  mov     [rsi], r14
0x1402f08a1  mov     eax, 0C0000022h
0x1402f08a6  jmp     loc_1402F0635
0x1402f08ab  mov     esi, [rsp+0E8h+var_B4]
0x1402f08af  mov     [rbx+18h], esi
0x1402f08b2  mov     r13d, [rsp+0E8h+var_B8]
0x1402f08b7  bt      r13d, 0Ah
0x1402f08bc  jb      short loc_1402F08F6
0x1402f08be  bt      r13d, 8
0x1402f08c3  jnb     short loc_1402F08D2
0x1402f08c5  cmp     esi, 3
0x1402f08c8  jz      short loc_1402F08F6
0x1402f08ca  mov     r8d, 2FDh
0x1402f08d0  jmp     short loc_1402F08E4
0x1402f08d2  cmp     esi, 3
0x1402f08d5  jnz     short loc_1402F08F6
0x1402f08d7  bt      r13d, 9
0x1402f08dc  jb      short loc_1402F08F6
0x1402f08de  mov     r8d, 301h
0x1402f08e4  mov     edi, 0C0000022h
0x1402f08e9  mov     r9d, edi
0x1402f08ec  mov     edx, 5
0x1402f08f1  call    EfspTraceLogAssert
0x1402f08f6  test    r15d, r13d
0x1402f08f9  jz      loc_1402F0A4A
0x1402f08ff  xor     cl, cl
0x1402f0901  lea     eax, [rsi-1]
0x1402f0904  cmp     eax, r12d
0x1402f0907  ja      short loc_1402F091E
0x1402f0909  mov     rax, [rbx+8]
0x1402f090d  cmp     [rax+4], r12d
0x1402f0911  jnz     short loc_1402F091E
0x1402f0913  test    byte ptr [rax+0Eh], 2
0x1402f0917  movzx   ecx, cl
0x1402f091a  cmovnz  ecx, r12d
0x1402f091e  test    cl, cl
0x1402f0920  jz      short loc_1402F092A
0x1402f0922  mov     [rbx], r14d
0x1402f0925  jmp     loc_1402F0A4A
0x1402f092a  bts     dword ptr [rbx], 1Fh
0x1402f092e  jmp     loc_1402F0A4A
0x1402f0933  mov     eax, cs:dword_1402472A0
0x1402f0939  cmp     eax, 5
0x1402f093c  jbe     short loc_1402F09A4
0x1402f093e  mov     rdx, 200000000000h
0x1402f0948  lea     rcx, dword_1402472A0
0x1402f094f  call    _tlgKeywordOn
0x1402f0954  test    al, al
0x1402f0956  jz      short loc_1402F09A4
0x1402f0958  mov     [rsp+0E8h+var_A8], r8d
0x1402f095d  lea     rax, [rsp+0E8h+var_A8]
0x1402f0962  mov     [rsp+0E8h+var_40], rax
0x1402f096a  mov     [rsp+0E8h+var_38], 4
0x1402f0976  lea     rax, [rsp+0E8h+var_60]
0x1402f097e  mov     [rsp+0E8h+var_C0], rax
0x1402f0983  mov     [rsp+0E8h+var_C8], 3
0x1402f098b  xor     r9d, r9d
0x1402f098e  xor     r8d, r8d
0x1402f0991  lea     rdx, byte_1402254A3
0x1402f0998  lea     rcx, dword_1402472A0
0x1402f099f  call    _tlgWriteTransfer_EtwWriteTransfer
0x1402f09a4  mov     r14, [rsp+0E8h+Src]
0x1402f09a9  jmp     loc_1402F0A45
0x1402f09ae  mov     dword ptr [rbx], 0C0000001h
0x1402f09b4  test    r15, r15
0x1402f09b7  jz      short loc_1402F09F8
0x1402f09b9  lea     rax, [rsp+0E8h+Size+4]
0x1402f09be  mov     [rsp+0E8h+var_C0], rax
0x1402f09c3  lea     rax, [rsp+0E8h+Size]
0x1402f09c8  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1402f09cd  lea     r9, [rsp+0E8h+Src]
0x1402f09d2  xor     r8d, r8d
0x1402f09d5  mov     rdx, [rsp+0E8h+var_90]
0x1402f09da  mov     rcx, r15
0x1402f09dd  call    EfsReadEfsData
0x1402f09e2  mov     edi, eax
0x1402f09e4  mov     [rsp+0E8h+var_98], eax
0x1402f09e8  mov     eax, dword ptr [rsp+0E8h+Size]
0x1402f09ec  mov     r14, [rsp+0E8h+Src]
0x1402f09f1  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x1402f09f6  jmp     short loc_1402F09FC
0x1402f09f8  mov     eax, [rsp+0E8h+var_A8]
0x1402f09fc  test    edi, edi
0x1402f09fe  js      short loc_1402F0A45
0x1402f0a00  mov     r15d, 10000h
0x1402f0a06  cmp     r12d, r15d
0x1402f0a09  jnz     short loc_1402F0A45
0x1402f0a0b  mov     rcx, r14; Src
0x1402f0a0e  mov     [rbx+10h], rcx
0x1402f0a12  xor     r14d, r14d
0x1402f0a15  mov     [rsp+0E8h+var_C8], 4; int
0x1402f0a1d  lea     r9, [rsp+0E8h+var_B4]
0x1402f0a22  lea     r8d, [r14+1]
0x1402f0a26  mov     edx, eax; Size
0x1402f0a28  call    EfsGetEfsStreamInfo
0x1402f0a2d  mov     edi, eax
0x1402f0a2f  test    eax, eax
0x1402f0a31  jns     short loc_1402F0A3E
0x1402f0a33  mov     r8d, 36Ah
0x1402f0a39  jmp     loc_1402F0773
0x1402f0a3e  mov     esi, [rsp+0E8h+var_B4]
0x1402f0a42  mov     [rbx+1Ch], esi
0x1402f0a45  mov     r13d, [rsp+0E8h+var_B8]
0x1402f0a4a  mov     rax, [rsp+0E8h+var_68]
0x1402f0a52  test    byte ptr [rax+18h], 4
0x1402f0a56  jz      short loc_1402F0AC7
0x1402f0a58  test    r13b, 5
0x1402f0a5c  jz      short loc_1402F0AC7
0x1402f0a5e  cmp     esi, 3
0x1402f0a61  jz      short loc_1402F0AC7
0x1402f0a63  mov     rsi, [rsp+0E8h+var_88]
0x1402f0a68  cmp     qword ptr [rsi], 0
0x1402f0a6c  jz      short loc_1402F0AAA
0x1402f0a6e  mov     rcx, [rbx+8]; P
0x1402f0a72  test    rcx, rcx
0x1402f0a75  jz      short loc_1402F0A8D
0x1402f0a77  xor     edx, edx; Tag
0x1402f0a79  call    cs:__imp_ExFreePoolWithTag
0x1402f0a80  nop     dword ptr [rax+rax+00h]
0x1402f0a85  mov     qword ptr [rbx+8], 0
0x1402f0a8d  mov     rdx, rbx; Entry
  ... truncated ...
```
