# GetKeyBlobBufferEx

- ea: `0x1402ea850`
- end: `0x1402eab05`
- name: `GetKeyBlobBufferEx`
- size: `693`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140107100`
- `0x1402eebc0`
- `0x1402eff08`
- `0x1402f01f0`
- `0x1402f10e8`
- `0x1402f1800`
- `0x1402f2f38`

## callees

- `0x1401ea140`
- `0x1402ea850`
- `0x1402eab0c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402eaa67`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402eaa67`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402ea8f2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402ea9cb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402ea8f2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402ea9cb`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402ea89a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402ea978`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402ea89a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402ea978`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402ea8d6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402ea9bc`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402ea8d6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402ea9bc`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1402ea965`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1402ea965`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402ea908`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402ea908`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402eaa92`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402eaa92`

## pseudocode

```c
_DWORD *__fastcall GetKeyBlobBufferEx(int a1, int a2)
{
  unsigned int KeyBlobLength; // eax
  SIZE_T Size; // r14
  struct _NPAGED_LOOKASIDE_LIST *v6; // rsi
  int v7; // ebp
  __int64 *i; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  __int64 v11; // rcx
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  int v14; // edi
  int v15; // edi
  int v16; // edi
  int v17; // edi
  int v18; // edi
  int v19; // edi
  __int64 (__fastcall *v20)(int, int, int, int, int); // rax

  KeyBlobLength = GetKeyBlobLength();
  Size = KeyBlobLength;
  if ( !KeyBlobLength )
    return 0;
  v6 = 0;
  if ( a1 == 26128 )
  {
    v7 = 268461584;
  }
  else
  {
    v7 = a1;
    if ( a1 == 26126 )
      v7 = 268461582;
  }
  ExAcquireFastMutex(&stru_140261B98);
  for ( i = (__int64 *)qword_140261B88; i != &qword_140261B88; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i - 4) == v7 && *((_DWORD *)i - 3) == (_DWORD)Size )
    {
      v6 = (struct _NPAGED_LOOKASIDE_LIST *)*(i - 1);
      break;
    }
  }
  ExReleaseFastMutex(&stru_140261B98);
  if ( !v6 )
  {
    v6 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(&stru_140261C80);
    v9 = ExAllocateFromPagedLookasideList(&stru_140261C00);
    v10 = v9;
    if ( v6 )
    {
      if ( v9 )
      {
        v9[2] = 0;
        v9[3] = 0;
        v9[1] = v6;
        *(_DWORD *)v9 = v7;
        *((_DWORD *)v9 + 1) = Size;
        ExInitializeNPagedLookasideList(v6, 0, 0, 0x200u, Size, 0x6D736645u, 0x1Eu);
        ExAcquireFastMutex(&stru_140261B98);
        v11 = qword_140261B88;
        if ( *(__int64 **)(qword_140261B88 + 8) != &qword_140261B88 )
          __fastfail(3u);
        v10[2] = qword_140261B88;
        v10[3] = &qword_140261B88;
        *(_QWORD *)(v11 + 8) = v10 + 2;
        qword_140261B88 = (__int64)(v10 + 2);
        ExReleaseFastMutex(&stru_140261B98);
        goto LABEL_19;
      }
      ExFreeToNPagedLookasideList(&stru_140261C80, v6);
    }
    else if ( v9 )
    {
      ExFreeToPagedLookasideList(&stru_140261C00, v9);
    }
    return 0;
  }
LABEL_19:
  v12 = ExAllocateFromNPagedLookasideList(v6);
  v13 = v12;
  if ( v12 )
  {
    memset(v12, 0, Size);
    v13[1] = a1;
    *v13 = Size;
    *((_QWORD *)v13 + 9) = v6;
    v13[6] = a2;
    v14 = a1 - 26113;
    if ( v14 )
    {
      v15 = v14 - 2;
      if ( !v15 )
      {
        *((_QWORD *)v13 + 2) = EfsDes3Enc;
        v20 = EfsDes3Dec;
        goto LABEL_37;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        v13[20] = 5;
LABEL_36:
        *((_QWORD *)v13 + 2) = &EfsCngDesEnc;
        v20 = EfsCngDesDec;
        goto LABEL_37;
      }
      v17 = v16 - 10;
      if ( !v17 || (v18 = v17 - 2) == 0 )
      {
        v13[20] = 1;
        *((_QWORD *)v13 + 11) = 0;
        *((_QWORD *)v13 + 2) = EfsAesEnc;
        v20 = (__int64 (__fastcall *)(int, int, int, int, int))EfsAesDec;
        goto LABEL_37;
      }
      v19 = v18 - 0x20000000;
      if ( !v19 || v19 == 0x20000000 )
      {
        v13[20] = 1;
        *((_QWORD *)v13 + 2) = EfsXtsAesEnc;
        v20 = (__int64 (__fastcall *)(int, int, int, int, int))EfsXtsAesDec;
        *((_QWORD *)v13 + 11) = 0;
LABEL_37:
        *((_QWORD *)v13 + 1) = v20;
        return v13;
      }
    }
    v13[20] = 4;
    goto LABEL_36;
  }
  return v13;
}

```

## disassembly

```asm
0x1402ea850  push    rbx
0x1402ea852  push    rbp
0x1402ea853  push    rsi
0x1402ea854  push    rdi
0x1402ea855  push    r14
0x1402ea857  push    r15
0x1402ea859  sub     rsp, 48h
0x1402ea85d  mov     r15d, edx
0x1402ea860  mov     edi, ecx
0x1402ea862  call    GetKeyBlobLength
0x1402ea867  mov     r14d, eax
0x1402ea86a  test    eax, eax
0x1402ea86c  jz      loc_1402EAA73
0x1402ea872  xor     esi, esi
0x1402ea874  cmp     edi, 6610h
0x1402ea87a  jnz     short loc_1402EA883
0x1402ea87c  mov     ebp, 10006610h
0x1402ea881  jmp     short loc_1402EA893
0x1402ea883  cmp     edi, 660Eh
0x1402ea889  mov     ebp, edi
0x1402ea88b  mov     eax, 1000660Eh
0x1402ea890  cmovz   ebp, eax
0x1402ea893  lea     rcx, stru_140261B98; FastMutex
0x1402ea89a  call    cs:__imp_ExAcquireFastMutex
0x1402ea8a1  nop     dword ptr [rax+rax+00h]
0x1402ea8a6  mov     rax, cs:qword_140261B88
0x1402ea8ad  lea     rcx, qword_140261B88
0x1402ea8b4  jmp     short loc_1402EA8C4
0x1402ea8b6  cmp     [rax-10h], ebp
0x1402ea8b9  jnz     short loc_1402EA8C1
0x1402ea8bb  cmp     [rax-0Ch], r14d
0x1402ea8bf  jz      short loc_1402EA8CB
0x1402ea8c1  mov     rax, [rax]
0x1402ea8c4  cmp     rax, rcx
0x1402ea8c7  jnz     short loc_1402EA8B6
0x1402ea8c9  jmp     short loc_1402EA8CF
0x1402ea8cb  mov     rsi, [rax-8]
0x1402ea8cf  lea     rcx, stru_140261B98; FastMutex
0x1402ea8d6  call    cs:__imp_ExReleaseFastMutex
0x1402ea8dd  nop     dword ptr [rax+rax+00h]
0x1402ea8e2  test    rsi, rsi
0x1402ea8e5  jnz     loc_1402EA9C8
0x1402ea8eb  lea     rcx, stru_140261C80; Lookaside
0x1402ea8f2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1402ea8f9  nop     dword ptr [rax+rax+00h]
0x1402ea8fe  lea     rcx, stru_140261C00; Lookaside
0x1402ea905  mov     rsi, rax
0x1402ea908  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1402ea90f  nop     dword ptr [rax+rax+00h]
0x1402ea914  mov     rbx, rax
0x1402ea917  test    rsi, rsi
0x1402ea91a  jz      loc_1402EAA83
0x1402ea920  test    rax, rax
0x1402ea923  jz      loc_1402EAA5D
0x1402ea929  mov     qword ptr [rax+10h], 0
0x1402ea931  mov     r9d, 200h; Flags
0x1402ea937  mov     qword ptr [rax+18h], 0
0x1402ea93f  xor     r8d, r8d; Free
0x1402ea942  mov     [rsp+78h+Depth], 1Eh; Depth
0x1402ea949  xor     edx, edx; Allocate
0x1402ea94b  mov     [rsp+78h+Tag], 6D736645h; Tag
0x1402ea953  mov     rcx, rsi; Lookaside
0x1402ea956  mov     [rax+8], rsi
0x1402ea95a  mov     [rax], ebp
0x1402ea95c  mov     [rax+4], r14d
0x1402ea960  mov     [rsp+78h+Size], r14; Size
0x1402ea965  call    cs:__imp_ExInitializeNPagedLookasideList
0x1402ea96c  nop     dword ptr [rax+rax+00h]
0x1402ea971  lea     rcx, stru_140261B98; FastMutex
0x1402ea978  call    cs:__imp_ExAcquireFastMutex
0x1402ea97f  nop     dword ptr [rax+rax+00h]
0x1402ea984  mov     rcx, cs:qword_140261B88
0x1402ea98b  lea     rdx, qword_140261B88
0x1402ea992  cmp     [rcx+8], rdx
0x1402ea996  jz      short loc_1402EA99F
0x1402ea998  mov     ecx, 3
0x1402ea99d  int     29h; Win8: RtlFailFast(ecx)
0x1402ea99f  lea     rax, [rbx+10h]
0x1402ea9a3  mov     [rax], rcx
0x1402ea9a6  mov     [rax+8], rdx
0x1402ea9aa  mov     [rcx+8], rax
0x1402ea9ae  lea     rcx, stru_140261B98; FastMutex
0x1402ea9b5  mov     cs:qword_140261B88, rax
0x1402ea9bc  call    cs:__imp_ExReleaseFastMutex
0x1402ea9c3  nop     dword ptr [rax+rax+00h]
0x1402ea9c8  mov     rcx, rsi; Lookaside
0x1402ea9cb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1402ea9d2  nop     dword ptr [rax+rax+00h]
0x1402ea9d7  mov     rbx, rax
0x1402ea9da  test    rax, rax
0x1402ea9dd  jz      loc_1402EAAFD
0x1402ea9e3  mov     r8, r14; Size
0x1402ea9e6  xor     edx, edx; Val
0x1402ea9e8  mov     rcx, rax; void *
0x1402ea9eb  call    memset
0x1402ea9f0  mov     [rbx+4], edi
0x1402ea9f3  mov     [rbx], r14d
0x1402ea9f6  mov     [rbx+48h], rsi
0x1402ea9fa  mov     [rbx+18h], r15d
0x1402ea9fe  sub     edi, 6601h
0x1402eaa04  jz      loc_1402EAAE0
0x1402eaa0a  sub     edi, 2
0x1402eaa0d  jz      loc_1402EAACC
0x1402eaa13  sub     edi, 1
0x1402eaa16  jz      loc_1402EAAC3
0x1402eaa1c  sub     edi, 0Ah
0x1402eaa1f  jz      short loc_1402EAAA0
0x1402eaa21  sub     edi, 2
0x1402eaa24  jz      short loc_1402EAAA0
0x1402eaa26  mov     eax, 20000000h
0x1402eaa2b  sub     edi, eax
0x1402eaa2d  jz      short loc_1402EAA37
0x1402eaa2f  cmp     edi, eax
0x1402eaa31  jnz     loc_1402EAAE0
0x1402eaa37  lea     rax, EfsXtsAesEnc
0x1402eaa3e  mov     dword ptr [rbx+50h], 1
0x1402eaa45  mov     [rbx+10h], rax
0x1402eaa49  lea     rax, EfsXtsAesDec
0x1402eaa50  mov     qword ptr [rbx+58h], 0
0x1402eaa58  jmp     loc_1402EAAF9
0x1402eaa5d  mov     rdx, rsi; Entry
0x1402eaa60  lea     rcx, stru_140261C80; Lookaside
0x1402eaa67  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402eaa6e  nop     dword ptr [rax+rax+00h]
0x1402eaa73  xor     eax, eax
0x1402eaa75  add     rsp, 48h
0x1402eaa79  pop     r15
0x1402eaa7b  pop     r14
0x1402eaa7d  pop     rdi
0x1402eaa7e  pop     rsi
0x1402eaa7f  pop     rbp
0x1402eaa80  pop     rbx
0x1402eaa81  retn
0x1402eaa83  test    rbx, rbx
0x1402eaa86  jz      short loc_1402EAA73
0x1402eaa88  mov     rdx, rbx; Entry
0x1402eaa8b  lea     rcx, stru_140261C00; Lookaside
0x1402eaa92  call    cs:__imp_ExFreeToPagedLookasideList
0x1402eaa99  nop     dword ptr [rax+rax+00h]
0x1402eaa9e  jmp     short loc_1402EAA73
0x1402eaaa0  lea     rax, EfsAesEnc
0x1402eaaa7  mov     dword ptr [rbx+50h], 1
0x1402eaaae  mov     qword ptr [rbx+58h], 0
0x1402eaab6  mov     [rbx+10h], rax
0x1402eaaba  lea     rax, EfsAesDec
0x1402eaac1  jmp     short loc_1402EAAF9
0x1402eaac3  mov     dword ptr [rbx+50h], 5
0x1402eaaca  jmp     short loc_1402EAAE7
0x1402eaacc  lea     rax, EfsDes3Enc
0x1402eaad3  mov     [rbx+10h], rax
0x1402eaad7  lea     rax, EfsDes3Dec
0x1402eaade  jmp     short loc_1402EAAF9
0x1402eaae0  mov     dword ptr [rbx+50h], 4
0x1402eaae7  lea     rax, EfsCngDesEnc
0x1402eaaee  mov     [rbx+10h], rax
0x1402eaaf2  lea     rax, EfsCngDesDec
0x1402eaaf9  mov     [rbx+8], rax
0x1402eaafd  mov     rax, rbx
0x1402eab00  jmp     loc_1402EAA75
```
