# EfsEncryptOrDecryptStreamWithKeyblob

- ea: `0x140053f20`
- end: `0x140054388`
- name: `EfsEncryptOrDecryptStreamWithKeyblob`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14005521c`

## callees

- `0x14000cba0`
- `0x14004d720`
- `0x14004e610`
- `0x14004ea30`
- `0x14004f910`
- `0x14004fa4c`
- `0x140050cf0`
- `0x140053f20`
- `0x14005489c`
- `0x140054fd4`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054286`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400542cf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400542e4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054311`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054286`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400542cf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400542e4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054311`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054183`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054235`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054183`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054235`

## pseudocode

```c
__int64 __fastcall EfsEncryptOrDecryptStreamWithKeyblob(
        __int64 a1,
        char a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6,
        unsigned int *a7,
        __int64 *a8)
{
  __int64 v8; // r15
  int v12; // r8d
  int v14; // ebx
  __int64 v15; // rcx
  int v16; // r10d
  __int64 v17; // r14
  __int64 result; // rax
  unsigned int v19; // ebx
  __int64 *v20; // r15
  __int64 v21; // r8
  unsigned int EfsStreamInfo; // ebx
  __int64 v23; // r8
  void *v24; // rcx
  char *v25; // r14
  _BOOL8 v26; // rcx
  unsigned int v27; // esi
  unsigned int v28; // ebx
  unsigned int v29; // eax
  char *v30; // rax
  __int64 v31; // r8
  PNPAGED_LOOKASIDE_LIST *KeyBlobBuffer; // rax
  PNPAGED_LOOKASIDE_LIST *v33; // rbx
  unsigned int *v34; // rsi
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // eax
  __int64 v38; // rcx
  unsigned int v39; // [rsp+30h] [rbp-38h] BYREF
  int v40; // [rsp+34h] [rbp-34h] BYREF
  int v41; // [rsp+38h] [rbp-30h] BYREF
  _DWORD Size[3]; // [rsp+3Ch] [rbp-2Ch] BYREF
  __int64 v43; // [rsp+48h] [rbp-20h]
  __int64 v44[3]; // [rsp+50h] [rbp-18h] BYREF
  char v45; // [rsp+B0h] [rbp+48h] BYREF

  v8 = a5;
  v12 = 0x8000000;
  memset(Size, 0, sizeof(Size));
  v14 = *(_DWORD *)(a1 + 8);
  v15 = 0;
  v41 = 0;
  v16 = 0;
  v17 = 0;
  v43 = 0;
  v45 = 0;
  v39 = 0;
  v40 = 0;
  v44[0] = 0;
  if ( (v14 & 0x8000000) != 0 )
  {
    result = EfsGetFileAndStreamTransition(a4, a3, a5, &v39, &v40, v44);
    if ( (int)result < 0 )
      return result;
    v15 = v39;
    v12 = 0x8000000;
    v16 = v40;
    v17 = v44[0];
  }
  v19 = v14 & 0xF77FFFFF;
  if ( v19 != 3 )
  {
    if ( v19 == 4 )
    {
      if ( (*(_DWORD *)(a1 + 8) & 0x8000000) == 0 )
      {
        v21 = 1552;
        goto LABEL_77;
      }
      if ( (_DWORD)v15 != 2 )
      {
        v21 = 1563;
        goto LABEL_77;
      }
      if ( (a2 & 1) == 0 )
        return 0;
      switch ( v16 )
      {
        case 1:
          v21 = 1575;
          goto LABEL_77;
        case 3:
          v21 = 1584;
          goto LABEL_77;
        case 0:
          result = EfsSetStreamTransition(a4, a3, v8, 0, 0);
          if ( (int)result < 0 )
            return result;
          break;
      }
      if ( v17 == -1 )
      {
LABEL_42:
        *a6 = 1;
        return 0;
      }
    }
LABEL_20:
    v20 = a8;
    goto LABEL_21;
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x8000000) == 0 )
  {
    v20 = a8;
    if ( *a8 )
    {
      v21 = 1425;
LABEL_77:
      EfsStreamInfo = -1073741808;
      goto LABEL_78;
    }
    if ( (a2 & 1) != 0 )
      return 0;
LABEL_21:
    LOBYTE(v12) = 1;
    result = EfsReadEfsData(a3, a4, v12, (unsigned int)&Size[1], (__int64)Size, (__int64)&v41);
    if ( (int)result < 0 )
      return result;
    if ( v41 != 0x10000 )
    {
      v21 = 1836;
      goto LABEL_77;
    }
    if ( (a2 & 2) == 0 )
    {
      EfsStreamInfo = -1073741808;
      v23 = 1660;
LABEL_46:
      EfspTraceLogAssert(v15, 6, v23, EfsStreamInfo);
      v24 = *(void **)&Size[1];
LABEL_47:
      ExFreePoolWithTag(v24, 0);
      return EfsStreamInfo;
    }
    if ( Size[0] < **(_DWORD **)(a1 + 16) )
    {
      EfsStreamInfo = -1073741811;
      v23 = 1669;
      goto LABEL_46;
    }
    v25 = *(char **)&Size[1];
    EfsStreamInfo = EfsGetEfsStreamInfo(*(void **)&Size[1], Size[0], 8);
    if ( (EfsStreamInfo & 0x80000000) == 0 )
    {
      v27 = HIDWORD(v43);
      if ( HIDWORD(v43) >= 8 && (unsigned int)v43 < HIDWORD(v43) )
      {
        v28 = 0;
        v29 = *(_DWORD *)(a1 + 32) + *(_DWORD *)(a1 + 40) - *(_DWORD *)(a1 + 16);
        if ( HIDWORD(v43) > v29 )
        {
          v27 = *(_DWORD *)(a1 + 32) + *(_DWORD *)(a1 + 40) - *(_DWORD *)(a1 + 16);
          v28 = HIDWORD(v43) - v29;
        }
        v26 = memcmp(
                &v25[(unsigned int)v43],
                (const void *)((unsigned int)v43 + *(_QWORD *)(a1 + 16)),
                v27 - (unsigned int)v43) == 0;
        v30 = &v25[v27];
        while ( v28 )
        {
          if ( *v30 )
            goto LABEL_58;
          ++v30;
          --v28;
        }
        if ( !v26 )
        {
LABEL_58:
          EfsStreamInfo = -1073741811;
          v31 = 1757;
          goto LABEL_74;
        }
        ExFreePoolWithTag(v25, 0);
        KeyBlobBuffer = (PNPAGED_LOOKASIDE_LIST *)GetKeyBlobBufferEx(
                                                    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 4LL),
                                                    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL));
        v33 = KeyBlobBuffer;
        if ( !KeyBlobBuffer )
          return 3221225626LL;
        v34 = a7;
        v35 = *(_QWORD *)(a1 + 24);
        v39 = *a7;
        if ( !(unsigned __int8)SetKeyTable(KeyBlobBuffer, &v39, v35) )
        {
          ExFreeToNPagedLookasideList(v33[9], v33);
          v21 = 1781;
          EfsStreamInfo = -1073741790;
LABEL_78:
          EfspTraceLogAssert(v15, 6, v21, EfsStreamInfo);
          return EfsStreamInfo;
        }
        if ( *v20 )
        {
          v37 = EfsSameContext(v33, *(_QWORD *)*v20, &v45, v36);
          if ( !v45 || v37 < 0 )
          {
            ExFreeToNPagedLookasideList(v33[9], v33);
            v21 = 1801;
            EfsStreamInfo = -1073741811;
            goto LABEL_78;
          }
          *v34 = v39;
          ExFreeToNPagedLookasideList(v33[9], v33);
        }
        else
        {
          v38 = AllocateAndSetContextDataBlock(v33);
          if ( !v38 )
          {
            ExFreeToNPagedLookasideList(v33[9], v33);
            return 3221225626LL;
          }
          *v34 = v39;
          *v20 = v38;
        }
        if ( (*(_DWORD *)(a1 + 8) & 0x8000000) != 0 )
          goto LABEL_42;
        return 0;
      }
      EfsStreamInfo = -1073739509;
      v31 = 1709;
LABEL_74:
      EfspTraceLogAssert(v26, 6, v31, EfsStreamInfo);
    }
    v24 = v25;
    goto LABEL_47;
  }
  if ( !(_DWORD)v15 )
  {
    if ( (a2 & 1) == 0 )
    {
      v21 = 1467;
      goto LABEL_77;
    }
    return 0;
  }
  if ( (_DWORD)v15 != 1 )
  {
    v21 = 1477;
    goto LABEL_77;
  }
  if ( (a2 & 1) != 0 )
  {
    if ( v16 == 2 )
    {
      v21 = 1490;
      goto LABEL_77;
    }
    if ( !v16 || v16 == 3 )
      return 0;
    goto LABEL_20;
  }
  if ( v16 )
  {
    v21 = 1521;
    goto LABEL_77;
  }
  result = EfsSetStreamTransition(a4, a3, v8, 0, 0);
  if ( (int)result >= 0 )
    goto LABEL_20;
  return result;
}

```

## disassembly

```asm
0x140053f20  push    rbp
0x140053f22  push    rbx
0x140053f23  push    rsi
0x140053f24  push    rdi
0x140053f25  push    r12
0x140053f27  push    r13
0x140053f29  push    r14
0x140053f2b  push    r15
0x140053f2d  mov     rbp, rsp
0x140053f30  sub     rsp, 68h
0x140053f34  mov     r15, [rbp+arg_20]
0x140053f38  mov     rdi, rcx
0x140053f3b  mov     r13, r8
0x140053f3e  mov     esi, edx
0x140053f40  xor     edx, edx
0x140053f42  mov     r8d, 8000000h
0x140053f48  mov     r12, r9
0x140053f4b  mov     dword ptr [rbp+Size], edx
0x140053f4e  mov     ebx, [rdi+8]
0x140053f51  mov     ecx, edx
0x140053f53  mov     [rbp+var_30], edx
0x140053f56  mov     r10d, edx
0x140053f59  mov     qword ptr [rbp+Size+4], rdx
0x140053f5d  mov     r14d, edx
0x140053f60  mov     [rbp+var_20], rdx
0x140053f64  mov     [rbp+arg_0], dl
0x140053f67  mov     [rbp+var_38], edx
0x140053f6a  mov     [rbp+var_34], edx
0x140053f6d  mov     [rbp+var_18], rdx
0x140053f71  test    r8d, ebx
0x140053f74  jz      short loc_140053FB5
0x140053f76  lea     rax, [rbp+var_18]
0x140053f7a  mov     r8, r15
0x140053f7d  mov     [rsp+68h+var_40], rax
0x140053f82  lea     r9, [rbp+var_38]
0x140053f86  lea     rax, [rbp+var_34]
0x140053f8a  mov     rdx, r13
0x140053f8d  mov     rcx, r12
0x140053f90  mov     qword ptr [rsp+68h+var_48], rax
0x140053f95  call    EfsGetFileAndStreamTransition
0x140053f9a  xor     edx, edx
0x140053f9c  test    eax, eax
0x140053f9e  js      loc_140054376
0x140053fa4  mov     ecx, [rbp+var_38]
0x140053fa7  mov     r8d, 8000000h
0x140053fad  mov     r10d, [rbp+var_34]
0x140053fb1  mov     r14, [rbp+var_18]
0x140053fb5  and     ebx, 0F77FFFFFh
0x140053fbb  cmp     ebx, 3
0x140053fbe  jnz     loc_1400540CD
0x140053fc4  test    [rdi+8], r8d
0x140053fc8  jnz     short loc_140053FED
0x140053fca  mov     r15, [rbp+arg_38]
0x140053fd1  cmp     [r15], rdx
0x140053fd4  jz      short loc_140053FE1
0x140053fd6  mov     r8d, 591h
0x140053fdc  jmp     loc_140054362
0x140053fe1  test    sil, 1
0x140053fe5  jnz     loc_140054153
0x140053feb  jmp     short loc_140054047
0x140053fed  test    ecx, ecx
0x140053fef  jnz     short loc_140054006
0x140053ff1  test    sil, 1
0x140053ff5  jnz     loc_140054153
0x140053ffb  mov     r8d, 5BBh
0x140054001  jmp     loc_140054362
0x140054006  cmp     ecx, 1
0x140054009  jz      short loc_140054016
0x14005400b  mov     r8d, 5C5h
0x140054011  jmp     loc_140054362
0x140054016  test    sil, 1
0x14005401a  jz      short loc_14005409A
0x14005401c  cmp     r10d, 2
0x140054020  jnz     short loc_14005402D
0x140054022  mov     r8d, 5D2h
0x140054028  jmp     loc_140054362
0x14005402d  test    r10d, r10d
0x140054030  jz      loc_140054153
0x140054036  cmp     r10d, 3
0x14005403a  jz      loc_140054153
0x140054040  mov     r15, [rbp+arg_38]
0x140054047  lea     rax, [rbp+var_30]
0x14005404b  mov     r8b, 1
0x14005404e  mov     [rsp+68h+var_40], rax
0x140054053  lea     r9, [rbp+Size+4]
0x140054057  lea     rax, [rbp+Size]
0x14005405b  mov     rdx, r12
0x14005405e  mov     rcx, r13
0x140054061  mov     qword ptr [rsp+68h+var_48], rax
0x140054066  call    EfsReadEfsData
0x14005406b  test    eax, eax
0x14005406d  js      loc_140054376
0x140054073  cmp     [rbp+var_30], 10000h
0x14005407a  jnz     loc_14005435C
0x140054080  test    sil, 2
0x140054084  jnz     loc_14005415A
0x14005408a  mov     ebx, 0C0000010h
0x14005408f  mov     r8d, 67Ch
0x140054095  jmp     loc_140054170
0x14005409a  test    r10d, r10d
0x14005409d  jz      short loc_1400540AA
0x14005409f  mov     r8d, 5F1h
0x1400540a5  jmp     loc_140054362
0x1400540aa  mov     qword ptr [rsp+68h+var_48], rdx
0x1400540af  xor     r9d, r9d
0x1400540b2  mov     rdx, r13
0x1400540b5  mov     r8, r15
0x1400540b8  mov     rcx, r12
0x1400540bb  call    EfsSetStreamTransition
0x1400540c0  test    eax, eax
0x1400540c2  jns     loc_140054040
0x1400540c8  jmp     loc_140054376
0x1400540cd  cmp     ebx, 4
0x1400540d0  jnz     loc_140054040
0x1400540d6  test    [rdi+8], r8d
0x1400540da  jnz     short loc_1400540E7
0x1400540dc  mov     r8d, 610h
0x1400540e2  jmp     loc_140054362
0x1400540e7  cmp     ecx, 2
0x1400540ea  jz      short loc_1400540F7
0x1400540ec  mov     r8d, 61Bh
0x1400540f2  jmp     loc_140054362
0x1400540f7  test    sil, 1
0x1400540fb  jz      short loc_140054153
0x1400540fd  cmp     r10d, 1
0x140054101  jnz     short loc_14005410E
0x140054103  mov     r8d, 627h
0x140054109  jmp     loc_140054362
0x14005410e  cmp     r10d, 3
0x140054112  jnz     short loc_14005411F
0x140054114  mov     r8d, 630h
0x14005411a  jmp     loc_140054362
0x14005411f  test    r10d, r10d
0x140054122  jnz     short loc_140054142
0x140054124  mov     qword ptr [rsp+68h+var_48], rdx
0x140054129  xor     r9d, r9d
0x14005412c  mov     rdx, r13
0x14005412f  mov     r8, r15
0x140054132  mov     rcx, r12
0x140054135  call    EfsSetStreamTransition
0x14005413a  test    eax, eax
0x14005413c  js      loc_140054376
0x140054142  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140054146  jnz     loc_140054040
0x14005414c  mov     rax, [rbp+arg_28]
0x140054150  mov     byte ptr [rax], 1
0x140054153  xor     eax, eax
0x140054155  jmp     loc_140054376
0x14005415a  mov     rax, [rdi+10h]
0x14005415e  mov     edx, dword ptr [rbp+Size]; Size
0x140054161  cmp     edx, [rax]
0x140054163  jnb     short loc_140054194
0x140054165  mov     ebx, 0C000000Dh
0x14005416a  mov     r8d, 685h
0x140054170  mov     r9d, ebx
0x140054173  mov     edx, 6
0x140054178  call    EfspTraceLogAssert
0x14005417d  mov     rcx, qword ptr [rbp+Size+4]; P
0x140054181  xor     edx, edx; Tag
0x140054183  call    cs:__imp_ExFreePoolWithTag
0x14005418a  nop     dword ptr [rax+rax+00h]
0x14005418f  jmp     loc_140054374
0x140054194  mov     r14, qword ptr [rbp+Size+4]
0x140054198  lea     r9, [rbp+var_20]
0x14005419c  mov     rcx, r14; Src
0x14005419f  mov     [rsp+68h+var_48], 8; int
0x1400541a7  mov     r8d, 7
0x1400541ad  call    EfsGetEfsStreamInfo
0x1400541b2  mov     ebx, eax
0x1400541b4  test    eax, eax
0x1400541b6  js      loc_140054354
0x1400541bc  mov     esi, dword ptr [rbp+var_20+4]
0x1400541bf  cmp     esi, 8
0x1400541c2  jb      loc_14005433C
0x1400541c8  mov     edx, dword ptr [rbp+var_20]
0x1400541cb  cmp     edx, esi
0x1400541cd  jnb     loc_14005433C
0x1400541d3  mov     eax, [rdi+28h]
0x1400541d6  xor     ebx, ebx
0x1400541d8  add     eax, [rdi+20h]
0x1400541db  sub     eax, [rdi+10h]
0x1400541de  cmp     esi, eax
0x1400541e0  jbe     short loc_1400541E8
0x1400541e2  mov     ebx, esi
0x1400541e4  mov     esi, eax
0x1400541e6  sub     ebx, eax
0x1400541e8  mov     rcx, rdx
0x1400541eb  mov     r8d, esi
0x1400541ee  sub     r8d, edx; Size
0x1400541f1  mov     rdx, [rdi+10h]
0x1400541f5  add     rdx, rcx; Buf2
0x1400541f8  add     rcx, r14; Buf1
0x1400541fb  call    memcmp
0x140054200  xor     ecx, ecx
0x140054202  test    eax, eax
0x140054204  mov     eax, esi
0x140054206  setz    cl
0x140054209  add     rax, r14
0x14005420c  test    ebx, ebx
0x14005420e  jz      short loc_14005421C
0x140054210  cmp     byte ptr [rax], 0
0x140054213  jnz     short loc_140054220
0x140054215  inc     rax
0x140054218  dec     ebx
0x14005421a  jmp     short loc_14005420C
0x14005421c  test    ecx, ecx
0x14005421e  jnz     short loc_140054230
0x140054220  mov     ebx, 0C000000Dh
0x140054225  mov     r8d, 6DDh
0x14005422b  jmp     loc_140054347
0x140054230  xor     edx, edx; Tag
0x140054232  mov     rcx, r14; P
0x140054235  call    cs:__imp_ExFreePoolWithTag
0x14005423c  nop     dword ptr [rax+rax+00h]
0x140054241  mov     rcx, [rdi+18h]
0x140054245  mov     edx, [rcx+8]
0x140054248  mov     ecx, [rcx+4]
0x14005424b  call    GetKeyBlobBufferEx
0x140054250  mov     rbx, rax
0x140054253  test    rax, rax
0x140054256  jnz     short loc_140054262
0x140054258  mov     eax, 0C000009Ah
0x14005425d  jmp     loc_140054376
0x140054262  mov     rsi, [rbp+arg_30]
0x140054266  lea     rdx, [rbp+var_38]
0x14005426a  mov     r8, [rdi+18h]
0x14005426e  mov     rcx, rbx
0x140054271  mov     eax, [rsi]
0x140054273  mov     [rbp+var_38], eax
0x140054276  call    SetKeyTable
0x14005427b  test    al, al
0x14005427d  jnz     short loc_1400542A2
0x14005427f  mov     rcx, [rbx+48h]; Lookaside
0x140054283  mov     rdx, rbx; Entry
0x140054286  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005428d  nop     dword ptr [rax+rax+00h]
0x140054292  mov     r8d, 6F5h
0x140054298  mov     ebx, 0C0000022h
0x14005429d  jmp     loc_140054367
0x1400542a2  mov     rdx, [r15]
0x1400542a5  mov     rcx, rbx
0x1400542a8  test    rdx, rdx
0x1400542ab  jz      short loc_1400542FD
0x1400542ad  mov     rdx, [rdx]
0x1400542b0  lea     r8, [rbp+arg_0]
0x1400542b4  call    EfsSameContext
0x1400542b9  cmp     [rbp+arg_0], 0
0x1400542bd  jz      short loc_1400542DD
0x1400542bf  test    eax, eax
0x1400542c1  js      short loc_1400542DD
0x1400542c3  mov     eax, [rbp+var_38]
0x1400542c6  mov     rdx, rbx; Entry
0x1400542c9  mov     [rsi], eax
0x1400542cb  mov     rcx, [rbx+48h]; Lookaside
0x1400542cf  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400542d6  nop     dword ptr [rax+rax+00h]
0x1400542db  jmp     short loc_14005432A
0x1400542dd  mov     rcx, [rbx+48h]; Lookaside
0x1400542e1  mov     rdx, rbx; Entry
0x1400542e4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400542eb  nop     dword ptr [rax+rax+00h]
0x1400542f0  mov     r8d, 709h
0x1400542f6  mov     ebx, 0C000000Dh
0x1400542fb  jmp     short loc_140054367
0x1400542fd  call    AllocateAndSetContextDataBlock
0x140054302  mov     rcx, rax
0x140054305  test    rax, rax
0x140054308  jnz     short loc_140054322
0x14005430a  mov     rcx, [rbx+48h]; Lookaside
0x14005430e  mov     rdx, rbx; Entry
0x140054311  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054318  nop     dword ptr [rax+rax+00h]
0x14005431d  jmp     loc_140054258
0x140054322  mov     eax, [rbp+var_38]
0x140054325  mov     [rsi], eax
0x140054327  mov     [r15], rcx
0x14005432a  test    dword ptr [rdi+8], 8000000h
0x140054331  jz      loc_140054153
0x140054337  jmp     loc_14005414C
0x14005433c  mov     ebx, 0C000090Bh
0x140054341  mov     r8d, 6ADh
0x140054347  mov     r9d, ebx
0x14005434a  mov     edx, 6
0x14005434f  call    EfspTraceLogAssert
0x140054354  mov     rcx, r14
0x140054357  jmp     loc_140054181
0x14005435c  mov     r8d, 72Ch
0x140054362  mov     ebx, 0C0000010h
0x140054367  mov     r9d, ebx
0x14005436a  mov     edx, 6
0x14005436f  call    EfspTraceLogAssert
0x140054374  mov     eax, ebx
0x140054376  add     rsp, 68h
0x14005437a  pop     r15
0x14005437c  pop     r14
0x14005437e  pop     r13
0x140054380  pop     r12
0x140054382  pop     rdi
0x140054383  pop     rsi
0x140054384  pop     rbx
  ... truncated ...
```
