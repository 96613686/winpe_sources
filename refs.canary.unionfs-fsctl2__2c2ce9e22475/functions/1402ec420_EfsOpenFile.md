# EfsOpenFile

- ea: `0x1402ec420`
- end: `0x1402ec9be`
- name: `EfsOpenFile`
- size: `1438`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callees

- `0x140001008`
- `0x1400086c4`
- `0x1401e9ce0`
- `0x1402ea418`
- `0x1402ebb60`
- `0x1402ebea4`
- `0x1402ec420`
- `0x1402f0b2c`
- `0x1402f2bc4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402ec70d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402ec917`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402ec9a4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1403470ff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140347138`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140347171`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402ec70d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402ec917`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402ec9a4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1403470ff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140347138`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140347171`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402ec4fd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402ec4fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec6f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec8f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec934`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec960`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec986`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec6f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec8f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec934`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec960`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ec986`

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
  if ( !byte_140261D64 )
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
    if ( (unsigned int)dword_1402402A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1402402A0, 0x200000000000LL) )
    {
      v37 = v28;
      v47 = &v37;
      v48 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_1402402A0, byte_14021E875, 0, 0, 3, v46);
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
0x1402ec420  mov     [rsp+arg_10], rbx
0x1402ec425  mov     [rsp+arg_18], rsi
0x1402ec42a  push    rdi
0x1402ec42b  push    r12
0x1402ec42d  push    r13
0x1402ec42f  push    r14
0x1402ec431  push    r15
0x1402ec433  sub     rsp, 0C0h
0x1402ec43a  mov     rax, cs:__security_cookie
0x1402ec441  xor     rax, rsp
0x1402ec444  mov     [rsp+0E8h+var_30], rax
0x1402ec44c  mov     [rsp+0E8h+var_B8], r9d
0x1402ec451  mov     [rsp+0E8h+var_68], r8
0x1402ec459  mov     r15, rdx
0x1402ec45c  mov     [rsp+0E8h+var_70], rcx
0x1402ec461  mov     rax, [rsp+0E8h+arg_28]
0x1402ec469  mov     [rsp+0E8h+var_90], rax
0x1402ec46e  mov     r13, [rsp+0E8h+arg_40]
0x1402ec476  mov     rdi, [rsp+0E8h+arg_48]
0x1402ec47e  mov     [rsp+0E8h+var_88], rdi
0x1402ec483  mov     [rsp+0E8h+var_78], rdi
0x1402ec488  xor     eax, eax
0x1402ec48a  mov     [rsp+0E8h+var_A8], eax
0x1402ec48e  mov     dword ptr [rsp+0E8h+Size], eax
0x1402ec492  xor     r14d, r14d
0x1402ec495  mov     [rsp+0E8h+Src], r14
0x1402ec49a  xor     r12d, r12d
0x1402ec49d  mov     dword ptr [rsp+0E8h+Size+4], r12d
0x1402ec4a2  xor     esi, esi
0x1402ec4a4  mov     [rsp+0E8h+var_B4], esi
0x1402ec4a8  cmp     cs:byte_140261D64, al
0x1402ec4ae  jnz     short loc_1402EC4E3
0x1402ec4b0  mov     eax, 0C0000010h
0x1402ec4b5  mov     rcx, [rsp+0E8h+var_30]
0x1402ec4bd  xor     rcx, rsp; StackCookie
0x1402ec4c0  call    __security_check_cookie
0x1402ec4c5  lea     r11, [rsp+0E8h+var_28]
0x1402ec4cd  mov     rbx, [r11+40h]
0x1402ec4d1  mov     rsi, [r11+48h]
0x1402ec4d5  mov     rsp, r11
0x1402ec4d8  pop     r15
0x1402ec4da  pop     r14
0x1402ec4dc  pop     r13
0x1402ec4de  pop     r12
0x1402ec4e0  pop     rdi
0x1402ec4e1  retn
0x1402ec4e3  bt      word ptr [r8+18h], 0Eh
0x1402ec4ea  jnb     short loc_1402EC4F6
0x1402ec4ec  test    r9b, 15h
0x1402ec4f0  jz      loc_1402EC940
0x1402ec4f6  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; Lookaside
0x1402ec4fd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1402ec504  nop     dword ptr [rax+rax+00h]
0x1402ec509  mov     rbx, rax
0x1402ec50c  mov     [rdi], rax
0x1402ec50f  test    rax, rax
0x1402ec512  jnz     short loc_1402EC51B
0x1402ec514  mov     eax, 0C000009Ah
0x1402ec519  jmp     short loc_1402EC4B5
0x1402ec51b  xor     edi, edi
0x1402ec51d  mov     [rsp+0E8h+var_80], rbx
0x1402ec522  mov     [rax+8], rsi
0x1402ec526  mov     [rax+10h], rsi
0x1402ec52a  mov     [rax+18h], rsi
0x1402ec52e  mov     [rax], esi
0x1402ec530  mov     eax, [rsp+0E8h+arg_20]
0x1402ec537  mov     [rbx+4], eax
0x1402ec53a  mov     eax, [rsp+0E8h+var_B8]
0x1402ec53e  and     eax, 0Fh
0x1402ec541  sub     eax, 1
0x1402ec544  jz      loc_1402EC82E
0x1402ec54a  sub     eax, 1
0x1402ec54d  jz      loc_1402EC60E
0x1402ec553  cmp     eax, 2
0x1402ec556  jnz     loc_1402EC8C5
0x1402ec55c  mov     dword ptr [rbx], 0C0000002h
0x1402ec562  test    r15, r15
0x1402ec565  jz      short loc_1402EC5A6
0x1402ec567  lea     rax, [rsp+0E8h+Size+4]
0x1402ec56c  mov     [rsp+0E8h+var_C0], rax
0x1402ec571  lea     rax, [rsp+0E8h+Size]
0x1402ec576  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1402ec57b  lea     r9, [rsp+0E8h+Src]
0x1402ec580  xor     r8d, r8d
0x1402ec583  mov     rdx, [rsp+0E8h+var_90]
0x1402ec588  mov     rcx, r15
0x1402ec58b  call    EfsReadEfsData
0x1402ec590  mov     edi, eax
0x1402ec592  mov     [rsp+0E8h+var_98], eax
0x1402ec596  mov     eax, dword ptr [rsp+0E8h+Size]
0x1402ec59a  mov     r14, [rsp+0E8h+Src]
0x1402ec59f  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x1402ec5a4  jmp     short loc_1402EC5AA
0x1402ec5a6  mov     eax, [rsp+0E8h+var_A8]
0x1402ec5aa  test    edi, edi
0x1402ec5ac  js      loc_1402EC8C5
0x1402ec5b2  mov     r15d, 10000h
0x1402ec5b8  cmp     r12d, r15d
0x1402ec5bb  jnz     loc_1402EC8C5
0x1402ec5c1  mov     rcx, r14; Src
0x1402ec5c4  mov     [rbx+10h], rcx
0x1402ec5c8  xor     r14d, r14d
0x1402ec5cb  mov     [rsp+0E8h+var_C8], 4; int
0x1402ec5d3  lea     r9, [rsp+0E8h+var_B4]
0x1402ec5d8  lea     r8d, [r14+1]
0x1402ec5dc  mov     edx, eax; Size
0x1402ec5de  call    EfsGetEfsStreamInfo
0x1402ec5e3  mov     edi, eax
0x1402ec5e5  test    eax, eax
0x1402ec5e7  jns     loc_1402EC8BE
0x1402ec5ed  mov     r8d, 3ADh
0x1402ec5f3  mov     edx, 5
0x1402ec5f8  mov     r9d, eax
0x1402ec5fb  call    EfspTraceLogAssert
0x1402ec600  mov     edi, 0C0000022h
0x1402ec605  mov     esi, [rsp+0E8h+var_B4]
0x1402ec609  jmp     loc_1402EC8C5
0x1402ec60e  lea     rax, [rsp+0E8h+Size+4]
0x1402ec613  mov     [rsp+0E8h+var_C0], rax
0x1402ec618  lea     rax, [rsp+0E8h+Size]
0x1402ec61d  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1402ec622  lea     r9, [rsp+0E8h+Src]
0x1402ec627  xor     r8d, r8d
0x1402ec62a  mov     rdx, [rsp+0E8h+var_90]
0x1402ec62f  mov     rcx, [rsp+0E8h+var_70]
0x1402ec634  call    EfsReadEfsData
0x1402ec639  mov     edi, eax
0x1402ec63b  mov     r8d, dword ptr [rsp+0E8h+Size+4]
0x1402ec640  mov     r15d, 10000h
0x1402ec646  cmp     r8d, r15d
0x1402ec649  jnz     loc_1402EC7B3
0x1402ec64f  mov     r10, [rsp+0E8h+Src]
0x1402ec654  mov     [rbx+8], r10
0x1402ec658  xor     r14d, r14d
0x1402ec65b  mov     dword ptr [rbx], 4
0x1402ec661  cmp     [r13+0], r14
0x1402ec665  jnz     short loc_1402EC6BF
0x1402ec667  mov     dword ptr [rbx], 40000004h
0x1402ec66d  mov     [rsp+0E8h+var_C8], 4; int
0x1402ec675  lea     r9, [rsp+0E8h+var_B4]
0x1402ec67a  mov     r12d, 1
0x1402ec680  mov     r8d, r12d
0x1402ec683  mov     edx, dword ptr [rsp+0E8h+Size]; Size
0x1402ec687  mov     rcx, r10; Src
0x1402ec68a  call    EfsGetEfsStreamInfo
0x1402ec68f  mov     edi, eax
0x1402ec691  test    eax, eax
0x1402ec693  jns     loc_1402EC72B
0x1402ec699  mov     r9d, eax
0x1402ec69c  lea     edx, [r12+4]
0x1402ec6a1  mov     r8d, 2EEh
0x1402ec6a7  call    EfspTraceLogAssert
0x1402ec6ac  mov     edi, 0C0000022h
0x1402ec6b1  mov     esi, [rsp+0E8h+var_B4]
0x1402ec6b5  mov     r13d, [rsp+0E8h+var_B8]
0x1402ec6ba  jmp     loc_1402EC776
0x1402ec6bf  mov     dword ptr [rbx], 20000004h
0x1402ec6c5  mov     rcx, r13
0x1402ec6c8  call    EfsIsKeyDplWrapped
0x1402ec6cd  test    al, al
0x1402ec6cf  jz      short loc_1402EC66D
0x1402ec6d1  test    edi, edi
0x1402ec6d3  jns     short loc_1402EC6E8
0x1402ec6d5  mov     r9d, edi
0x1402ec6d8  mov     edx, 5
0x1402ec6dd  mov     r8d, 2D4h
0x1402ec6e3  call    EfspTraceLogAssert
0x1402ec6e8  mov     rcx, [rbx+8]; P
0x1402ec6ec  test    rcx, rcx
0x1402ec6ef  jz      short loc_1402EC703
0x1402ec6f1  xor     edx, edx; Tag
0x1402ec6f3  call    cs:__imp_ExFreePoolWithTag
0x1402ec6fa  nop     dword ptr [rax+rax+00h]
0x1402ec6ff  mov     [rbx+8], r14
0x1402ec703  mov     rdx, rbx; Entry
0x1402ec706  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; Lookaside
0x1402ec70d  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402ec714  nop     dword ptr [rax+rax+00h]
0x1402ec719  mov     rsi, [rsp+0E8h+var_88]
0x1402ec71e  mov     [rsi], r14
0x1402ec721  mov     eax, 0C0000022h
0x1402ec726  jmp     loc_1402EC4B5
0x1402ec72b  mov     esi, [rsp+0E8h+var_B4]
0x1402ec72f  mov     [rbx+18h], esi
0x1402ec732  mov     r13d, [rsp+0E8h+var_B8]
0x1402ec737  bt      r13d, 0Ah
0x1402ec73c  jb      short loc_1402EC776
0x1402ec73e  bt      r13d, 8
0x1402ec743  jnb     short loc_1402EC752
0x1402ec745  cmp     esi, 3
0x1402ec748  jz      short loc_1402EC776
0x1402ec74a  mov     r8d, 2FDh
0x1402ec750  jmp     short loc_1402EC764
0x1402ec752  cmp     esi, 3
0x1402ec755  jnz     short loc_1402EC776
0x1402ec757  bt      r13d, 9
0x1402ec75c  jb      short loc_1402EC776
0x1402ec75e  mov     r8d, 301h
0x1402ec764  mov     edi, 0C0000022h
0x1402ec769  mov     r9d, edi
0x1402ec76c  mov     edx, 5
0x1402ec771  call    EfspTraceLogAssert
0x1402ec776  test    r15d, r13d
0x1402ec779  jz      loc_1402EC8CA
0x1402ec77f  xor     cl, cl
0x1402ec781  lea     eax, [rsi-1]
0x1402ec784  cmp     eax, r12d
0x1402ec787  ja      short loc_1402EC79E
0x1402ec789  mov     rax, [rbx+8]
0x1402ec78d  cmp     [rax+4], r12d
0x1402ec791  jnz     short loc_1402EC79E
0x1402ec793  test    byte ptr [rax+0Eh], 2
0x1402ec797  movzx   ecx, cl
0x1402ec79a  cmovnz  ecx, r12d
0x1402ec79e  test    cl, cl
0x1402ec7a0  jz      short loc_1402EC7AA
0x1402ec7a2  mov     [rbx], r14d
0x1402ec7a5  jmp     loc_1402EC8CA
0x1402ec7aa  bts     dword ptr [rbx], 1Fh
0x1402ec7ae  jmp     loc_1402EC8CA
0x1402ec7b3  mov     eax, cs:dword_1402402A0
0x1402ec7b9  cmp     eax, 5
0x1402ec7bc  jbe     short loc_1402EC824
0x1402ec7be  mov     rdx, 200000000000h
0x1402ec7c8  lea     rcx, dword_1402402A0
0x1402ec7cf  call    _tlgKeywordOn
0x1402ec7d4  test    al, al
0x1402ec7d6  jz      short loc_1402EC824
0x1402ec7d8  mov     [rsp+0E8h+var_A8], r8d
0x1402ec7dd  lea     rax, [rsp+0E8h+var_A8]
0x1402ec7e2  mov     [rsp+0E8h+var_40], rax
0x1402ec7ea  mov     [rsp+0E8h+var_38], 4
0x1402ec7f6  lea     rax, [rsp+0E8h+var_60]
0x1402ec7fe  mov     [rsp+0E8h+var_C0], rax
0x1402ec803  mov     [rsp+0E8h+var_C8], 3
0x1402ec80b  xor     r9d, r9d
0x1402ec80e  xor     r8d, r8d
0x1402ec811  lea     rdx, byte_14021E875
0x1402ec818  lea     rcx, dword_1402402A0
0x1402ec81f  call    _tlgWriteTransfer_EtwWriteTransfer
0x1402ec824  mov     r14, [rsp+0E8h+Src]
0x1402ec829  jmp     loc_1402EC8C5
0x1402ec82e  mov     dword ptr [rbx], 0C0000001h
0x1402ec834  test    r15, r15
0x1402ec837  jz      short loc_1402EC878
0x1402ec839  lea     rax, [rsp+0E8h+Size+4]
0x1402ec83e  mov     [rsp+0E8h+var_C0], rax
0x1402ec843  lea     rax, [rsp+0E8h+Size]
0x1402ec848  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1402ec84d  lea     r9, [rsp+0E8h+Src]
0x1402ec852  xor     r8d, r8d
0x1402ec855  mov     rdx, [rsp+0E8h+var_90]
0x1402ec85a  mov     rcx, r15
0x1402ec85d  call    EfsReadEfsData
0x1402ec862  mov     edi, eax
0x1402ec864  mov     [rsp+0E8h+var_98], eax
0x1402ec868  mov     eax, dword ptr [rsp+0E8h+Size]
0x1402ec86c  mov     r14, [rsp+0E8h+Src]
0x1402ec871  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x1402ec876  jmp     short loc_1402EC87C
0x1402ec878  mov     eax, [rsp+0E8h+var_A8]
0x1402ec87c  test    edi, edi
0x1402ec87e  js      short loc_1402EC8C5
0x1402ec880  mov     r15d, 10000h
0x1402ec886  cmp     r12d, r15d
0x1402ec889  jnz     short loc_1402EC8C5
0x1402ec88b  mov     rcx, r14; Src
0x1402ec88e  mov     [rbx+10h], rcx
0x1402ec892  xor     r14d, r14d
0x1402ec895  mov     [rsp+0E8h+var_C8], 4; int
0x1402ec89d  lea     r9, [rsp+0E8h+var_B4]
0x1402ec8a2  lea     r8d, [r14+1]
0x1402ec8a6  mov     edx, eax; Size
0x1402ec8a8  call    EfsGetEfsStreamInfo
0x1402ec8ad  mov     edi, eax
0x1402ec8af  test    eax, eax
0x1402ec8b1  jns     short loc_1402EC8BE
0x1402ec8b3  mov     r8d, 36Ah
0x1402ec8b9  jmp     loc_1402EC5F3
0x1402ec8be  mov     esi, [rsp+0E8h+var_B4]
0x1402ec8c2  mov     [rbx+1Ch], esi
0x1402ec8c5  mov     r13d, [rsp+0E8h+var_B8]
0x1402ec8ca  mov     rax, [rsp+0E8h+var_68]
0x1402ec8d2  test    byte ptr [rax+18h], 4
0x1402ec8d6  jz      short loc_1402EC947
0x1402ec8d8  test    r13b, 5
0x1402ec8dc  jz      short loc_1402EC947
0x1402ec8de  cmp     esi, 3
0x1402ec8e1  jz      short loc_1402EC947
0x1402ec8e3  mov     rsi, [rsp+0E8h+var_88]
0x1402ec8e8  cmp     qword ptr [rsi], 0
0x1402ec8ec  jz      short loc_1402EC92A
0x1402ec8ee  mov     rcx, [rbx+8]; P
0x1402ec8f2  test    rcx, rcx
0x1402ec8f5  jz      short loc_1402EC90D
0x1402ec8f7  xor     edx, edx; Tag
0x1402ec8f9  call    cs:__imp_ExFreePoolWithTag
0x1402ec900  nop     dword ptr [rax+rax+00h]
0x1402ec905  mov     qword ptr [rbx+8], 0
0x1402ec90d  mov     rdx, rbx; Entry
  ... truncated ...
```
