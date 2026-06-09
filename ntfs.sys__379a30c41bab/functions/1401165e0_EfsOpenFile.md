# EfsOpenFile

- ea: `0x1401165e0`
- end: `0x140116b7e`
- name: `EfsOpenFile`
- size: `1438`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callees

- `0x140036464`
- `0x14003c94c`
- `0x1400592c0`
- `0x1401165e0`
- `0x140146540`
- `0x140147034`
- `0x1401476a8`
- `0x140260ae0`
- `0x140270ed4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401168b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116ab9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116b46`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401168b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116ab9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140116b46`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401168cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140116ad7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140116b64`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6e91`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6eca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6f03`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401168cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140116ad7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140116b64`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6e91`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6eca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402c6f03`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401166bd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401166bd`

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
    if ( (unsigned int)dword_140092288 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140092288, 0x200000000000LL) )
    {
      v37 = v28;
      v47 = &v37;
      v48 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140092288, word_140072DF2, 0, 0, 3, v46);
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
0x1401165e0  mov     [rsp+arg_10], rbx
0x1401165e5  mov     [rsp+arg_18], rsi
0x1401165ea  push    rdi
0x1401165eb  push    r12
0x1401165ed  push    r13
0x1401165ef  push    r14
0x1401165f1  push    r15
0x1401165f3  sub     rsp, 0C0h
0x1401165fa  mov     rax, cs:__security_cookie
0x140116601  xor     rax, rsp
0x140116604  mov     [rsp+0E8h+var_30], rax
0x14011660c  mov     [rsp+0E8h+var_B8], r9d
0x140116611  mov     [rsp+0E8h+var_68], r8
0x140116619  mov     r15, rdx
0x14011661c  mov     [rsp+0E8h+var_70], rcx
0x140116621  mov     rax, [rsp+0E8h+arg_28]
0x140116629  mov     [rsp+0E8h+var_90], rax
0x14011662e  mov     r13, [rsp+0E8h+arg_40]
0x140116636  mov     rdi, [rsp+0E8h+arg_48]
0x14011663e  mov     [rsp+0E8h+var_88], rdi
0x140116643  mov     [rsp+0E8h+var_78], rdi
0x140116648  xor     eax, eax
0x14011664a  mov     [rsp+0E8h+var_A8], eax
0x14011664e  mov     dword ptr [rsp+0E8h+Size], eax
0x140116652  xor     r14d, r14d
0x140116655  mov     [rsp+0E8h+Src], r14
0x14011665a  xor     r12d, r12d
0x14011665d  mov     dword ptr [rsp+0E8h+Size+4], r12d
0x140116662  xor     esi, esi
0x140116664  mov     [rsp+0E8h+var_B4], esi
0x140116668  cmp     cs:byte_140093DE4, al
0x14011666e  jnz     short loc_1401166A3
0x140116670  mov     eax, 0C0000010h
0x140116675  mov     rcx, [rsp+0E8h+var_30]
0x14011667d  xor     rcx, rsp; StackCookie
0x140116680  call    __security_check_cookie
0x140116685  lea     r11, [rsp+0E8h+var_28]
0x14011668d  mov     rbx, [r11+40h]
0x140116691  mov     rsi, [r11+48h]
0x140116695  mov     rsp, r11
0x140116698  pop     r15
0x14011669a  pop     r14
0x14011669c  pop     r13
0x14011669e  pop     r12
0x1401166a0  pop     rdi
0x1401166a1  retn
0x1401166a3  bt      word ptr [r8+18h], 0Eh
0x1401166aa  jnb     short loc_1401166B6
0x1401166ac  test    r9b, 15h
0x1401166b0  jz      loc_140116B00
0x1401166b6  lea     rcx, stru_140093AC0; Lookaside
0x1401166bd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1401166c4  nop     dword ptr [rax+rax+00h]
0x1401166c9  mov     rbx, rax
0x1401166cc  mov     [rdi], rax
0x1401166cf  test    rax, rax
0x1401166d2  jnz     short loc_1401166DB
0x1401166d4  mov     eax, 0C000009Ah
0x1401166d9  jmp     short loc_140116675
0x1401166db  xor     edi, edi
0x1401166dd  mov     [rsp+0E8h+var_80], rbx
0x1401166e2  mov     [rax+8], rsi
0x1401166e6  mov     [rax+10h], rsi
0x1401166ea  mov     [rax+18h], rsi
0x1401166ee  mov     [rax], esi
0x1401166f0  mov     eax, [rsp+0E8h+arg_20]
0x1401166f7  mov     [rbx+4], eax
0x1401166fa  mov     eax, [rsp+0E8h+var_B8]
0x1401166fe  and     eax, 0Fh
0x140116701  sub     eax, 1
0x140116704  jz      loc_1401169EE
0x14011670a  sub     eax, 1
0x14011670d  jz      loc_1401167CE
0x140116713  cmp     eax, 2
0x140116716  jnz     loc_140116A85
0x14011671c  mov     dword ptr [rbx], 0C0000002h
0x140116722  test    r15, r15
0x140116725  jz      short loc_140116766
0x140116727  lea     rax, [rsp+0E8h+Size+4]
0x14011672c  mov     [rsp+0E8h+var_C0], rax
0x140116731  lea     rax, [rsp+0E8h+Size]
0x140116736  mov     qword ptr [rsp+0E8h+var_C8], rax
0x14011673b  lea     r9, [rsp+0E8h+Src]
0x140116740  xor     r8d, r8d
0x140116743  mov     rdx, [rsp+0E8h+var_90]
0x140116748  mov     rcx, r15
0x14011674b  call    EfsReadEfsData
0x140116750  mov     edi, eax
0x140116752  mov     [rsp+0E8h+var_98], eax
0x140116756  mov     eax, dword ptr [rsp+0E8h+Size]
0x14011675a  mov     r14, [rsp+0E8h+Src]
0x14011675f  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x140116764  jmp     short loc_14011676A
0x140116766  mov     eax, [rsp+0E8h+var_A8]
0x14011676a  test    edi, edi
0x14011676c  js      loc_140116A85
0x140116772  mov     r15d, 10000h
0x140116778  cmp     r12d, r15d
0x14011677b  jnz     loc_140116A85
0x140116781  mov     rcx, r14; Src
0x140116784  mov     [rbx+10h], rcx
0x140116788  xor     r14d, r14d
0x14011678b  mov     [rsp+0E8h+var_C8], 4; int
0x140116793  lea     r9, [rsp+0E8h+var_B4]
0x140116798  lea     r8d, [r14+1]
0x14011679c  mov     edx, eax; Size
0x14011679e  call    EfsGetEfsStreamInfo
0x1401167a3  mov     edi, eax
0x1401167a5  test    eax, eax
0x1401167a7  jns     loc_140116A7E
0x1401167ad  mov     r8d, 3ADh
0x1401167b3  mov     edx, 5
0x1401167b8  mov     r9d, eax
0x1401167bb  call    EfspTraceLogAssert
0x1401167c0  mov     edi, 0C0000022h
0x1401167c5  mov     esi, [rsp+0E8h+var_B4]
0x1401167c9  jmp     loc_140116A85
0x1401167ce  lea     rax, [rsp+0E8h+Size+4]
0x1401167d3  mov     [rsp+0E8h+var_C0], rax
0x1401167d8  lea     rax, [rsp+0E8h+Size]
0x1401167dd  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1401167e2  lea     r9, [rsp+0E8h+Src]
0x1401167e7  xor     r8d, r8d
0x1401167ea  mov     rdx, [rsp+0E8h+var_90]
0x1401167ef  mov     rcx, [rsp+0E8h+var_70]
0x1401167f4  call    EfsReadEfsData
0x1401167f9  mov     edi, eax
0x1401167fb  mov     r8d, dword ptr [rsp+0E8h+Size+4]
0x140116800  mov     r15d, 10000h
0x140116806  cmp     r8d, r15d
0x140116809  jnz     loc_140116973
0x14011680f  mov     r10, [rsp+0E8h+Src]
0x140116814  mov     [rbx+8], r10
0x140116818  xor     r14d, r14d
0x14011681b  mov     dword ptr [rbx], 4
0x140116821  cmp     [r13+0], r14
0x140116825  jnz     short loc_14011687F
0x140116827  mov     dword ptr [rbx], 40000004h
0x14011682d  mov     [rsp+0E8h+var_C8], 4; int
0x140116835  lea     r9, [rsp+0E8h+var_B4]
0x14011683a  mov     r12d, 1
0x140116840  mov     r8d, r12d
0x140116843  mov     edx, dword ptr [rsp+0E8h+Size]; Size
0x140116847  mov     rcx, r10; Src
0x14011684a  call    EfsGetEfsStreamInfo
0x14011684f  mov     edi, eax
0x140116851  test    eax, eax
0x140116853  jns     loc_1401168EB
0x140116859  mov     r9d, eax
0x14011685c  lea     edx, [r12+4]
0x140116861  mov     r8d, 2EEh
0x140116867  call    EfspTraceLogAssert
0x14011686c  mov     edi, 0C0000022h
0x140116871  mov     esi, [rsp+0E8h+var_B4]
0x140116875  mov     r13d, [rsp+0E8h+var_B8]
0x14011687a  jmp     loc_140116936
0x14011687f  mov     dword ptr [rbx], 20000004h
0x140116885  mov     rcx, r13
0x140116888  call    EfsIsKeyDplWrapped
0x14011688d  test    al, al
0x14011688f  jz      short loc_14011682D
0x140116891  test    edi, edi
0x140116893  jns     short loc_1401168A8
0x140116895  mov     r9d, edi
0x140116898  mov     edx, 5
0x14011689d  mov     r8d, 2D4h
0x1401168a3  call    EfspTraceLogAssert
0x1401168a8  mov     rcx, [rbx+8]; P
0x1401168ac  test    rcx, rcx
0x1401168af  jz      short loc_1401168C3
0x1401168b1  xor     edx, edx; Tag
0x1401168b3  call    cs:__imp_ExFreePoolWithTag
0x1401168ba  nop     dword ptr [rax+rax+00h]
0x1401168bf  mov     [rbx+8], r14
0x1401168c3  mov     rdx, rbx; Entry
0x1401168c6  lea     rcx, stru_140093AC0; Lookaside
0x1401168cd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1401168d4  nop     dword ptr [rax+rax+00h]
0x1401168d9  mov     rsi, [rsp+0E8h+var_88]
0x1401168de  mov     [rsi], r14
0x1401168e1  mov     eax, 0C0000022h
0x1401168e6  jmp     loc_140116675
0x1401168eb  mov     esi, [rsp+0E8h+var_B4]
0x1401168ef  mov     [rbx+18h], esi
0x1401168f2  mov     r13d, [rsp+0E8h+var_B8]
0x1401168f7  bt      r13d, 0Ah
0x1401168fc  jb      short loc_140116936
0x1401168fe  bt      r13d, 8
0x140116903  jnb     short loc_140116912
0x140116905  cmp     esi, 3
0x140116908  jz      short loc_140116936
0x14011690a  mov     r8d, 2FDh
0x140116910  jmp     short loc_140116924
0x140116912  cmp     esi, 3
0x140116915  jnz     short loc_140116936
0x140116917  bt      r13d, 9
0x14011691c  jb      short loc_140116936
0x14011691e  mov     r8d, 301h
0x140116924  mov     edi, 0C0000022h
0x140116929  mov     r9d, edi
0x14011692c  mov     edx, 5
0x140116931  call    EfspTraceLogAssert
0x140116936  test    r15d, r13d
0x140116939  jz      loc_140116A8A
0x14011693f  xor     cl, cl
0x140116941  lea     eax, [rsi-1]
0x140116944  cmp     eax, r12d
0x140116947  ja      short loc_14011695E
0x140116949  mov     rax, [rbx+8]
0x14011694d  cmp     [rax+4], r12d
0x140116951  jnz     short loc_14011695E
0x140116953  test    byte ptr [rax+0Eh], 2
0x140116957  movzx   ecx, cl
0x14011695a  cmovnz  ecx, r12d
0x14011695e  test    cl, cl
0x140116960  jz      short loc_14011696A
0x140116962  mov     [rbx], r14d
0x140116965  jmp     loc_140116A8A
0x14011696a  bts     dword ptr [rbx], 1Fh
0x14011696e  jmp     loc_140116A8A
0x140116973  mov     eax, cs:dword_140092288
0x140116979  cmp     eax, 5
0x14011697c  jbe     short loc_1401169E4
0x14011697e  mov     rdx, 200000000000h
0x140116988  lea     rcx, dword_140092288
0x14011698f  call    _tlgKeywordOn
0x140116994  test    al, al
0x140116996  jz      short loc_1401169E4
0x140116998  mov     [rsp+0E8h+var_A8], r8d
0x14011699d  lea     rax, [rsp+0E8h+var_A8]
0x1401169a2  mov     [rsp+0E8h+var_40], rax
0x1401169aa  mov     [rsp+0E8h+var_38], 4
0x1401169b6  lea     rax, [rsp+0E8h+var_60]
0x1401169be  mov     [rsp+0E8h+var_C0], rax
0x1401169c3  mov     [rsp+0E8h+var_C8], 3
0x1401169cb  xor     r9d, r9d
0x1401169ce  xor     r8d, r8d
0x1401169d1  lea     rdx, word_140072DF2
0x1401169d8  lea     rcx, dword_140092288
0x1401169df  call    _tlgWriteTransfer_EtwWriteTransfer
0x1401169e4  mov     r14, [rsp+0E8h+Src]
0x1401169e9  jmp     loc_140116A85
0x1401169ee  mov     dword ptr [rbx], 0C0000001h
0x1401169f4  test    r15, r15
0x1401169f7  jz      short loc_140116A38
0x1401169f9  lea     rax, [rsp+0E8h+Size+4]
0x1401169fe  mov     [rsp+0E8h+var_C0], rax
0x140116a03  lea     rax, [rsp+0E8h+Size]
0x140116a08  mov     qword ptr [rsp+0E8h+var_C8], rax
0x140116a0d  lea     r9, [rsp+0E8h+Src]
0x140116a12  xor     r8d, r8d
0x140116a15  mov     rdx, [rsp+0E8h+var_90]
0x140116a1a  mov     rcx, r15
0x140116a1d  call    EfsReadEfsData
0x140116a22  mov     edi, eax
0x140116a24  mov     [rsp+0E8h+var_98], eax
0x140116a28  mov     eax, dword ptr [rsp+0E8h+Size]
0x140116a2c  mov     r14, [rsp+0E8h+Src]
0x140116a31  mov     r12d, dword ptr [rsp+0E8h+Size+4]
0x140116a36  jmp     short loc_140116A3C
0x140116a38  mov     eax, [rsp+0E8h+var_A8]
0x140116a3c  test    edi, edi
0x140116a3e  js      short loc_140116A85
0x140116a40  mov     r15d, 10000h
0x140116a46  cmp     r12d, r15d
0x140116a49  jnz     short loc_140116A85
0x140116a4b  mov     rcx, r14; Src
0x140116a4e  mov     [rbx+10h], rcx
0x140116a52  xor     r14d, r14d
0x140116a55  mov     [rsp+0E8h+var_C8], 4; int
0x140116a5d  lea     r9, [rsp+0E8h+var_B4]
0x140116a62  lea     r8d, [r14+1]
0x140116a66  mov     edx, eax; Size
0x140116a68  call    EfsGetEfsStreamInfo
0x140116a6d  mov     edi, eax
0x140116a6f  test    eax, eax
0x140116a71  jns     short loc_140116A7E
0x140116a73  mov     r8d, 36Ah
0x140116a79  jmp     loc_1401167B3
0x140116a7e  mov     esi, [rsp+0E8h+var_B4]
0x140116a82  mov     [rbx+1Ch], esi
0x140116a85  mov     r13d, [rsp+0E8h+var_B8]
0x140116a8a  mov     rax, [rsp+0E8h+var_68]
0x140116a92  test    byte ptr [rax+18h], 4
0x140116a96  jz      short loc_140116B07
0x140116a98  test    r13b, 5
0x140116a9c  jz      short loc_140116B07
0x140116a9e  cmp     esi, 3
0x140116aa1  jz      short loc_140116B07
0x140116aa3  mov     rsi, [rsp+0E8h+var_88]
0x140116aa8  cmp     qword ptr [rsi], 0
0x140116aac  jz      short loc_140116AEA
0x140116aae  mov     rcx, [rbx+8]; P
0x140116ab2  test    rcx, rcx
0x140116ab5  jz      short loc_140116ACD
0x140116ab7  xor     edx, edx; Tag
0x140116ab9  call    cs:__imp_ExFreePoolWithTag
0x140116ac0  nop     dword ptr [rax+rax+00h]
0x140116ac5  mov     qword ptr [rbx+8], 0
0x140116acd  mov     rdx, rbx; Entry
  ... truncated ...
```
