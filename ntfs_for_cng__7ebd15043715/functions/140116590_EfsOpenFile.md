# EfsOpenFile

- ea: `0x140116590`
- end: `0x140116b2e`
- name: `EfsOpenFile`
- size: `1438`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, __int64, int, int, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callees

- `0x140036464`
- `0x14003c94c`
- `0x140059250`
- `0x140116590`
- `0x1401464f0`
- `0x140146fe4`
- `0x140147658`
- `0x140260a90`
- `0x140270e84`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140116863`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116a69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116aa4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116ad0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116af6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116863`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116a69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116aa4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116ad0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116af6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14011687d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140116a87`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140116b14`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6e41`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6e7a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6eb3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14011687d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140116a87`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140116b14`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6e41`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6e7a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6eb3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14011666d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14011666d`

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
  struct _EVENT_DATA_DESCRIPTOR v46; // [rsp+88h] [rbp-60h] BYREF
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
  if ( !byte_140093DE4 )
    return 3221225488LL;
  if ( _bittest16((const signed __int16 *)(a3 + 24), 0xEu) && (a4 & 0x15) == 0 )
    return 0;
  v14 = ExAllocateFromNPagedLookasideList(&stru_140093AC0);
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
    if ( (unsigned int)dword_140092288 > 5 && tlgKeywordOn((__int64)&dword_140092288, 0x200000000000LL) )
    {
      v37 = v28;
      v47 = &v37;
      v48 = 4;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140092288, (unsigned __int8 *)word_140072DF2, 0, 0, 3u, &v46);
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
      ExFreeToNPagedLookasideList(&stru_140093AC0, v15);
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
      ExFreeToNPagedLookasideList(&stru_140093AC0, v15);
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
      ExFreeToNPagedLookasideList(&stru_140093AC0, v15);
      *v33 = 0;
    }
  }
  return (unsigned int)EfsData;
}

```

## disassembly

```asm
0x140116590  mov     [rsp+arg_10], rbx
0x140116595  mov     [rsp+arg_18], rsi
0x14011659a  push    rdi
0x14011659b  push    r12
0x14011659d  push    r13
0x14011659f  push    r14
0x1401165a1  push    r15
0x1401165a3  sub     rsp, 0C0h
0x1401165aa  mov     rax, cs:__security_cookie
0x1401165b1  xor     rax, rsp
0x1401165b4  mov     [rsp+0E8h+var_30], rax
0x1401165bc  mov     [rsp+0E8h+var_B8], r9d
0x1401165c1  mov     [rsp+0E8h+var_68], r8
0x1401165c9  mov     r15, rdx
0x1401165cc  mov     [rsp+0E8h+var_70], rcx
0x1401165d1  mov     rax, [rsp+0E8h+arg_28]
0x1401165d9  mov     [rsp+0E8h+var_90], rax
0x1401165de  mov     r13, [rsp+0E8h+arg_40]
0x1401165e6  mov     rdi, [rsp+0E8h+arg_48]
0x1401165ee  mov     [rsp+0E8h+var_88], rdi
0x1401165f3  mov     [rsp+0E8h+var_78], rdi
0x1401165f8  xor     eax, eax
0x1401165fa  mov     [rsp+0E8h+var_A8], eax
0x1401165fe  mov     dword ptr [rsp+0E8h+Size], eax
0x140116602  xor     r14d, r14d
0x140116605  mov     [rsp+0E8h+Src], r14
0x14011660a  xor     r12d, r12d
0x14011660d  mov     dword ptr [rsp+0E8h+Size+4], r12d
0x140116612  xor     esi, esi
0x140116614  mov     [rsp+0E8h+var_B4], esi
0x140116618  cmp     cs:byte_140093DE4, al
0x14011661e  jnz     short loc_140116653
0x140116620  mov     eax, 0C0000010h
0x140116625  mov     rcx, [rsp+0E8h+var_30]
0x14011662d  xor     rcx, rsp; StackCookie
0x140116630  call    __security_check_cookie
0x140116635  lea     r11, [rsp+0E8h+var_28]
0x14011663d  mov     rbx, [r11+40h]
0x140116641  mov     rsi, [r11+48h]
0x140116645  mov     rsp, r11
0x140116648  pop     r15
0x14011664a  pop     r14
0x14011664c  pop     r13
0x14011664e  pop     r12
0x140116650  pop     rdi
0x140116651  retn
0x140116653  bt      word ptr [r8+18h], 0Eh
0x14011665a  jnb     short loc_140116666
0x14011665c  test    r9b, 15h
0x140116660  jz      loc_140116AB0
0x140116666  lea     rcx, stru_140093AC0; Lookaside
0x14011666d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140116674  nop     dword ptr [rax+rax+00h]
0x140116679  mov     rbx, rax
0x14011667c  mov     [rdi], rax
0x14011667f  test    rax, rax
0x140116682  jnz     short loc_14011668B
0x140116684  mov     eax, 0C000009Ah
0x140116689  jmp     short loc_140116625
0x14011668b  xor     edi, edi
0x14011668d  mov     [rsp+0E8h+var_80], rbx
0x140116692  mov     [rax+8], rsi
0x140116696  mov     [rax+10h], rsi
0x14011669a  mov     [rax+18h], rsi
0x14011669e  mov     [rax], esi
0x1401166a0  mov     eax, [rsp+0E8h+arg_20]
0x1401166a7  mov     [rbx+4], eax
0x1401166aa  mov     eax, [rsp+0E8h+var_B8]
0x1401166ae  and     eax, 0Fh
0x1401166b1  sub     eax, 1
0x1401166b4  jz      loc_14011699E
0x1401166ba  sub     eax, 1
0x1401166bd  jz      loc_14011677E
0x1401166c3  cmp     eax, 2
0x1401166c6  jnz     loc_140116A35
0x1401166cc  mov     dword ptr [rbx], 0C0000002h
0x1401166d2  test    r15, r15
0x1401166d5  jz      short loc_140116716
0x1401166d7  lea     rax, [rsp+0E8h+Size+4]
0x1401166dc  mov     [rsp+0E8h+var_C0], rax
0x1401166e1  lea     rax, [rsp+0E8h+Size]
0x1401166e6  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1401166eb  lea     r9, [rsp+0E8h+Src]
0x1401166f0  xor     r8d, r8d
0x1401166f3  mov     rdx, [rsp+0E8h+var_90]
0x1401166f8  mov     rcx, r15
0x1401166fb  call    EfsReadEfsData
0x140116700  mov     edi, eax
0x140116702  mov     [rsp+0E8h+var_98], eax
0x140116706  mov     eax, dword ptr [rsp+0E8h+Size]
0x14011670a  mov     r14, [rsp+0E8h+Src]
0x14011670f  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x140116714  jmp     short loc_14011671A
0x140116716  mov     eax, [rsp+0E8h+var_A8]
0x14011671a  test    edi, edi
0x14011671c  js      loc_140116A35
0x140116722  mov     r15d, 10000h
0x140116728  cmp     r12d, r15d
0x14011672b  jnz     loc_140116A35
0x140116731  mov     rcx, r14; Src
0x140116734  mov     [rbx+10h], rcx
0x140116738  xor     r14d, r14d
0x14011673b  mov     [rsp+0E8h+var_C8], 4; int
0x140116743  lea     r9, [rsp+0E8h+var_B4]
0x140116748  lea     r8d, [r14+1]
0x14011674c  mov     edx, eax; Size
0x14011674e  call    EfsGetEfsStreamInfo
0x140116753  mov     edi, eax
0x140116755  test    eax, eax
0x140116757  jns     loc_140116A2E
0x14011675d  mov     r8d, 3ADh
0x140116763  mov     edx, 5
0x140116768  mov     r9d, eax
0x14011676b  call    EfspTraceLogAssert
0x140116770  mov     edi, 0C0000022h
0x140116775  mov     esi, [rsp+0E8h+var_B4]
0x140116779  jmp     loc_140116A35
0x14011677e  lea     rax, [rsp+0E8h+Size+4]
0x140116783  mov     [rsp+0E8h+var_C0], rax
0x140116788  lea     rax, [rsp+0E8h+Size]
0x14011678d  mov     qword ptr [rsp+0E8h+var_C8], rax
0x140116792  lea     r9, [rsp+0E8h+Src]
0x140116797  xor     r8d, r8d
0x14011679a  mov     rdx, [rsp+0E8h+var_90]
0x14011679f  mov     rcx, [rsp+0E8h+var_70]
0x1401167a4  call    EfsReadEfsData
0x1401167a9  mov     edi, eax
0x1401167ab  mov     r8d, dword ptr [rsp+0E8h+Size+4]
0x1401167b0  mov     r15d, 10000h
0x1401167b6  cmp     r8d, r15d
0x1401167b9  jnz     loc_140116923
0x1401167bf  mov     r10, [rsp+0E8h+Src]
0x1401167c4  mov     [rbx+8], r10
0x1401167c8  xor     r14d, r14d
0x1401167cb  mov     dword ptr [rbx], 4
0x1401167d1  cmp     [r13+0], r14
0x1401167d5  jnz     short loc_14011682F
0x1401167d7  mov     dword ptr [rbx], 40000004h
0x1401167dd  mov     [rsp+0E8h+var_C8], 4; int
0x1401167e5  lea     r9, [rsp+0E8h+var_B4]
0x1401167ea  mov     r12d, 1
0x1401167f0  mov     r8d, r12d
0x1401167f3  mov     edx, dword ptr [rsp+0E8h+Size]; Size
0x1401167f7  mov     rcx, r10; Src
0x1401167fa  call    EfsGetEfsStreamInfo
0x1401167ff  mov     edi, eax
0x140116801  test    eax, eax
0x140116803  jns     loc_14011689B
0x140116809  mov     r9d, eax
0x14011680c  lea     edx, [r12+4]
0x140116811  mov     r8d, 2EEh
0x140116817  call    EfspTraceLogAssert
0x14011681c  mov     edi, 0C0000022h
0x140116821  mov     esi, [rsp+0E8h+var_B4]
0x140116825  mov     r13d, [rsp+0E8h+var_B8]
0x14011682a  jmp     loc_1401168E6
0x14011682f  mov     dword ptr [rbx], 20000004h
0x140116835  mov     rcx, r13
0x140116838  call    EfsIsKeyDplWrapped
0x14011683d  test    al, al
0x14011683f  jz      short loc_1401167DD
0x140116841  test    edi, edi
0x140116843  jns     short loc_140116858
0x140116845  mov     r9d, edi
0x140116848  mov     edx, 5
0x14011684d  mov     r8d, 2D4h
0x140116853  call    EfspTraceLogAssert
0x140116858  mov     rcx, [rbx+8]; P
0x14011685c  test    rcx, rcx
0x14011685f  jz      short loc_140116873
0x140116861  xor     edx, edx; Tag
0x140116863  call    cs:__imp_ExFreePoolWithTag
0x14011686a  nop     dword ptr [rax+rax+00h]
0x14011686f  mov     [rbx+8], r14
0x140116873  mov     rdx, rbx; Entry
0x140116876  lea     rcx, stru_140093AC0; Lookaside
0x14011687d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140116884  nop     dword ptr [rax+rax+00h]
0x140116889  mov     rsi, [rsp+0E8h+var_88]
0x14011688e  mov     [rsi], r14
0x140116891  mov     eax, 0C0000022h
0x140116896  jmp     loc_140116625
0x14011689b  mov     esi, [rsp+0E8h+var_B4]
0x14011689f  mov     [rbx+18h], esi
0x1401168a2  mov     r13d, [rsp+0E8h+var_B8]
0x1401168a7  bt      r13d, 0Ah
0x1401168ac  jb      short loc_1401168E6
0x1401168ae  bt      r13d, 8
0x1401168b3  jnb     short loc_1401168C2
0x1401168b5  cmp     esi, 3
0x1401168b8  jz      short loc_1401168E6
0x1401168ba  mov     r8d, 2FDh
0x1401168c0  jmp     short loc_1401168D4
0x1401168c2  cmp     esi, 3
0x1401168c5  jnz     short loc_1401168E6
0x1401168c7  bt      r13d, 9
0x1401168cc  jb      short loc_1401168E6
0x1401168ce  mov     r8d, 301h
0x1401168d4  mov     edi, 0C0000022h
0x1401168d9  mov     r9d, edi
0x1401168dc  mov     edx, 5
0x1401168e1  call    EfspTraceLogAssert
0x1401168e6  test    r15d, r13d
0x1401168e9  jz      loc_140116A3A
0x1401168ef  xor     cl, cl
0x1401168f1  lea     eax, [rsi-1]
0x1401168f4  cmp     eax, r12d
0x1401168f7  ja      short loc_14011690E
0x1401168f9  mov     rax, [rbx+8]
0x1401168fd  cmp     [rax+4], r12d
0x140116901  jnz     short loc_14011690E
0x140116903  test    byte ptr [rax+0Eh], 2
0x140116907  movzx   ecx, cl
0x14011690a  cmovnz  ecx, r12d
0x14011690e  test    cl, cl
0x140116910  jz      short loc_14011691A
0x140116912  mov     [rbx], r14d
0x140116915  jmp     loc_140116A3A
0x14011691a  bts     dword ptr [rbx], 1Fh
0x14011691e  jmp     loc_140116A3A
0x140116923  mov     eax, cs:dword_140092288
0x140116929  cmp     eax, 5
0x14011692c  jbe     short loc_140116994
0x14011692e  mov     rdx, 200000000000h
0x140116938  lea     rcx, dword_140092288
0x14011693f  call    _tlgKeywordOn
0x140116944  test    al, al
0x140116946  jz      short loc_140116994
0x140116948  mov     [rsp+0E8h+var_A8], r8d
0x14011694d  lea     rax, [rsp+0E8h+var_A8]
0x140116952  mov     [rsp+0E8h+var_40], rax
0x14011695a  mov     [rsp+0E8h+var_38], 4
0x140116966  lea     rax, [rsp+0E8h+var_60]
0x14011696e  mov     [rsp+0E8h+var_C0], rax
0x140116973  mov     [rsp+0E8h+var_C8], 3
0x14011697b  xor     r9d, r9d
0x14011697e  xor     r8d, r8d
0x140116981  lea     rdx, word_140072DF2
0x140116988  lea     rcx, dword_140092288
0x14011698f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140116994  mov     r14, [rsp+0E8h+Src]
0x140116999  jmp     loc_140116A35
0x14011699e  mov     dword ptr [rbx], 0C0000001h
0x1401169a4  test    r15, r15
0x1401169a7  jz      short loc_1401169E8
0x1401169a9  lea     rax, [rsp+0E8h+Size+4]
0x1401169ae  mov     [rsp+0E8h+var_C0], rax
0x1401169b3  lea     rax, [rsp+0E8h+Size]
0x1401169b8  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1401169bd  lea     r9, [rsp+0E8h+Src]
0x1401169c2  xor     r8d, r8d
0x1401169c5  mov     rdx, [rsp+0E8h+var_90]
0x1401169ca  mov     rcx, r15
0x1401169cd  call    EfsReadEfsData
0x1401169d2  mov     edi, eax
0x1401169d4  mov     [rsp+0E8h+var_98], eax
0x1401169d8  mov     eax, dword ptr [rsp+0E8h+Size]
0x1401169dc  mov     r14, [rsp+0E8h+Src]
0x1401169e1  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x1401169e6  jmp     short loc_1401169EC
0x1401169e8  mov     eax, [rsp+0E8h+var_A8]
0x1401169ec  test    edi, edi
0x1401169ee  js      short loc_140116A35
0x1401169f0  mov     r15d, 10000h
0x1401169f6  cmp     r12d, r15d
0x1401169f9  jnz     short loc_140116A35
0x1401169fb  mov     rcx, r14; Src
0x1401169fe  mov     [rbx+10h], rcx
0x140116a02  xor     r14d, r14d
0x140116a05  mov     [rsp+0E8h+var_C8], 4; int
0x140116a0d  lea     r9, [rsp+0E8h+var_B4]
0x140116a12  lea     r8d, [r14+1]
0x140116a16  mov     edx, eax; Size
0x140116a18  call    EfsGetEfsStreamInfo
0x140116a1d  mov     edi, eax
0x140116a1f  test    eax, eax
0x140116a21  jns     short loc_140116A2E
0x140116a23  mov     r8d, 36Ah
0x140116a29  jmp     loc_140116763
0x140116a2e  mov     esi, [rsp+0E8h+var_B4]
0x140116a32  mov     [rbx+1Ch], esi
0x140116a35  mov     r13d, [rsp+0E8h+var_B8]
0x140116a3a  mov     rax, [rsp+0E8h+var_68]
0x140116a42  test    byte ptr [rax+18h], 4
0x140116a46  jz      short loc_140116AB7
0x140116a48  test    r13b, 5
0x140116a4c  jz      short loc_140116AB7
0x140116a4e  cmp     esi, 3
0x140116a51  jz      short loc_140116AB7
0x140116a53  mov     rsi, [rsp+0E8h+var_88]
0x140116a58  cmp     qword ptr [rsi], 0
0x140116a5c  jz      short loc_140116A9A
0x140116a5e  mov     rcx, [rbx+8]; P
0x140116a62  test    rcx, rcx
0x140116a65  jz      short loc_140116A7D
0x140116a67  xor     edx, edx; Tag
0x140116a69  call    cs:__imp_ExFreePoolWithTag
0x140116a70  nop     dword ptr [rax+rax+00h]
0x140116a75  mov     qword ptr [rbx+8], 0
0x140116a7d  mov     rdx, rbx; Entry
  ... truncated ...
```
