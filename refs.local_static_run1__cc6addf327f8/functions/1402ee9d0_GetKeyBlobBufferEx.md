# GetKeyBlobBufferEx

- ea: `0x1402ee9d0`
- end: `0x1402eec85`
- name: `GetKeyBlobBufferEx`
- size: `693`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14010bf60`
- `0x1402f2d40`
- `0x1402f4088`
- `0x1402f4370`
- `0x1402f5268`
- `0x1402f5980`
- `0x1402f70b8`

## callees

- `0x1401f4400`
- `0x1402ee9d0`
- `0x1402eec8c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402eebe7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402eebe7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402eea72`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402eeb4b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402eea72`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1402eeb4b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402eea1a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402eeaf8`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402eea1a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402eeaf8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402eea56`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402eeb3c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402eea56`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402eeb3c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1402eeae5`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1402eeae5`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402eea88`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1402eea88`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402eec12`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402eec12`

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
  ExAcquireFastMutex(&stru_140268B98);
  for ( i = (__int64 *)qword_140268B88; i != &qword_140268B88; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i - 4) == v7 && *((_DWORD *)i - 3) == (_DWORD)Size )
    {
      v6 = (struct _NPAGED_LOOKASIDE_LIST *)*(i - 1);
      break;
    }
  }
  ExReleaseFastMutex(&stru_140268B98);
  if ( !v6 )
  {
    v6 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(&stru_140268C80);
    v9 = ExAllocateFromPagedLookasideList(&stru_140268C00);
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
        ExAcquireFastMutex(&stru_140268B98);
        v11 = qword_140268B88;
        if ( *(__int64 **)(qword_140268B88 + 8) != &qword_140268B88 )
          __fastfail(3u);
        v10[2] = qword_140268B88;
        v10[3] = &qword_140268B88;
        *(_QWORD *)(v11 + 8) = v10 + 2;
        qword_140268B88 = (__int64)(v10 + 2);
        ExReleaseFastMutex(&stru_140268B98);
        goto LABEL_19;
      }
      ExFreeToNPagedLookasideList(&stru_140268C80, v6);
    }
    else if ( v9 )
    {
      ExFreeToPagedLookasideList(&stru_140268C00, v9);
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
0x1402ee9d0  push    rbx
0x1402ee9d2  push    rbp
0x1402ee9d3  push    rsi
0x1402ee9d4  push    rdi
0x1402ee9d5  push    r14
0x1402ee9d7  push    r15
0x1402ee9d9  sub     rsp, 48h
0x1402ee9dd  mov     r15d, edx
0x1402ee9e0  mov     edi, ecx
0x1402ee9e2  call    GetKeyBlobLength
0x1402ee9e7  mov     r14d, eax
0x1402ee9ea  test    eax, eax
0x1402ee9ec  jz      loc_1402EEBF3
0x1402ee9f2  xor     esi, esi
0x1402ee9f4  cmp     edi, 6610h
0x1402ee9fa  jnz     short loc_1402EEA03
0x1402ee9fc  mov     ebp, 10006610h
0x1402eea01  jmp     short loc_1402EEA13
0x1402eea03  cmp     edi, 660Eh
0x1402eea09  mov     ebp, edi
0x1402eea0b  mov     eax, 1000660Eh
0x1402eea10  cmovz   ebp, eax
0x1402eea13  lea     rcx, stru_140268B98; FastMutex
0x1402eea1a  call    cs:__imp_ExAcquireFastMutex
0x1402eea21  nop     dword ptr [rax+rax+00h]
0x1402eea26  mov     rax, cs:qword_140268B88
0x1402eea2d  lea     rcx, qword_140268B88
0x1402eea34  jmp     short loc_1402EEA44
0x1402eea36  cmp     [rax-10h], ebp
0x1402eea39  jnz     short loc_1402EEA41
0x1402eea3b  cmp     [rax-0Ch], r14d
0x1402eea3f  jz      short loc_1402EEA4B
0x1402eea41  mov     rax, [rax]
0x1402eea44  cmp     rax, rcx
0x1402eea47  jnz     short loc_1402EEA36
0x1402eea49  jmp     short loc_1402EEA4F
0x1402eea4b  mov     rsi, [rax-8]
0x1402eea4f  lea     rcx, stru_140268B98; FastMutex
0x1402eea56  call    cs:__imp_ExReleaseFastMutex
0x1402eea5d  nop     dword ptr [rax+rax+00h]
0x1402eea62  test    rsi, rsi
0x1402eea65  jnz     loc_1402EEB48
0x1402eea6b  lea     rcx, stru_140268C80; Lookaside
0x1402eea72  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1402eea79  nop     dword ptr [rax+rax+00h]
0x1402eea7e  lea     rcx, stru_140268C00; Lookaside
0x1402eea85  mov     rsi, rax
0x1402eea88  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1402eea8f  nop     dword ptr [rax+rax+00h]
0x1402eea94  mov     rbx, rax
0x1402eea97  test    rsi, rsi
0x1402eea9a  jz      loc_1402EEC03
0x1402eeaa0  test    rax, rax
0x1402eeaa3  jz      loc_1402EEBDD
0x1402eeaa9  mov     qword ptr [rax+10h], 0
0x1402eeab1  mov     r9d, 200h; Flags
0x1402eeab7  mov     qword ptr [rax+18h], 0
0x1402eeabf  xor     r8d, r8d; Free
0x1402eeac2  mov     [rsp+78h+Depth], 1Eh; Depth
0x1402eeac9  xor     edx, edx; Allocate
0x1402eeacb  mov     [rsp+78h+Tag], 6D736645h; Tag
0x1402eead3  mov     rcx, rsi; Lookaside
0x1402eead6  mov     [rax+8], rsi
0x1402eeada  mov     [rax], ebp
0x1402eeadc  mov     [rax+4], r14d
0x1402eeae0  mov     [rsp+78h+Size], r14; Size
0x1402eeae5  call    cs:__imp_ExInitializeNPagedLookasideList
0x1402eeaec  nop     dword ptr [rax+rax+00h]
0x1402eeaf1  lea     rcx, stru_140268B98; FastMutex
0x1402eeaf8  call    cs:__imp_ExAcquireFastMutex
0x1402eeaff  nop     dword ptr [rax+rax+00h]
0x1402eeb04  mov     rcx, cs:qword_140268B88
0x1402eeb0b  lea     rdx, qword_140268B88
0x1402eeb12  cmp     [rcx+8], rdx
0x1402eeb16  jz      short loc_1402EEB1F
0x1402eeb18  mov     ecx, 3
0x1402eeb1d  int     29h; Win8: RtlFailFast(ecx)
0x1402eeb1f  lea     rax, [rbx+10h]
0x1402eeb23  mov     [rax], rcx
0x1402eeb26  mov     [rax+8], rdx
0x1402eeb2a  mov     [rcx+8], rax
0x1402eeb2e  lea     rcx, stru_140268B98; FastMutex
0x1402eeb35  mov     cs:qword_140268B88, rax
0x1402eeb3c  call    cs:__imp_ExReleaseFastMutex
0x1402eeb43  nop     dword ptr [rax+rax+00h]
0x1402eeb48  mov     rcx, rsi; Lookaside
0x1402eeb4b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1402eeb52  nop     dword ptr [rax+rax+00h]
0x1402eeb57  mov     rbx, rax
0x1402eeb5a  test    rax, rax
0x1402eeb5d  jz      loc_1402EEC7D
0x1402eeb63  mov     r8, r14; Size
0x1402eeb66  xor     edx, edx; Val
0x1402eeb68  mov     rcx, rax; void *
0x1402eeb6b  call    memset
0x1402eeb70  mov     [rbx+4], edi
0x1402eeb73  mov     [rbx], r14d
0x1402eeb76  mov     [rbx+48h], rsi
0x1402eeb7a  mov     [rbx+18h], r15d
0x1402eeb7e  sub     edi, 6601h
0x1402eeb84  jz      loc_1402EEC60
0x1402eeb8a  sub     edi, 2
0x1402eeb8d  jz      loc_1402EEC4C
0x1402eeb93  sub     edi, 1
0x1402eeb96  jz      loc_1402EEC43
0x1402eeb9c  sub     edi, 0Ah
0x1402eeb9f  jz      short loc_1402EEC20
0x1402eeba1  sub     edi, 2
0x1402eeba4  jz      short loc_1402EEC20
0x1402eeba6  mov     eax, 20000000h
0x1402eebab  sub     edi, eax
0x1402eebad  jz      short loc_1402EEBB7
0x1402eebaf  cmp     edi, eax
0x1402eebb1  jnz     loc_1402EEC60
0x1402eebb7  lea     rax, EfsXtsAesEnc
0x1402eebbe  mov     dword ptr [rbx+50h], 1
0x1402eebc5  mov     [rbx+10h], rax
0x1402eebc9  lea     rax, EfsXtsAesDec
0x1402eebd0  mov     qword ptr [rbx+58h], 0
0x1402eebd8  jmp     loc_1402EEC79
0x1402eebdd  mov     rdx, rsi; Entry
0x1402eebe0  lea     rcx, stru_140268C80; Lookaside
0x1402eebe7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402eebee  nop     dword ptr [rax+rax+00h]
0x1402eebf3  xor     eax, eax
0x1402eebf5  add     rsp, 48h
0x1402eebf9  pop     r15
0x1402eebfb  pop     r14
0x1402eebfd  pop     rdi
0x1402eebfe  pop     rsi
0x1402eebff  pop     rbp
0x1402eec00  pop     rbx
0x1402eec01  retn
0x1402eec03  test    rbx, rbx
0x1402eec06  jz      short loc_1402EEBF3
0x1402eec08  mov     rdx, rbx; Entry
0x1402eec0b  lea     rcx, stru_140268C00; Lookaside
0x1402eec12  call    cs:__imp_ExFreeToPagedLookasideList
0x1402eec19  nop     dword ptr [rax+rax+00h]
0x1402eec1e  jmp     short loc_1402EEBF3
0x1402eec20  lea     rax, EfsAesEnc
0x1402eec27  mov     dword ptr [rbx+50h], 1
0x1402eec2e  mov     qword ptr [rbx+58h], 0
0x1402eec36  mov     [rbx+10h], rax
0x1402eec3a  lea     rax, EfsAesDec
0x1402eec41  jmp     short loc_1402EEC79
0x1402eec43  mov     dword ptr [rbx+50h], 5
0x1402eec4a  jmp     short loc_1402EEC67
0x1402eec4c  lea     rax, EfsDes3Enc
0x1402eec53  mov     [rbx+10h], rax
0x1402eec57  lea     rax, EfsDes3Dec
0x1402eec5e  jmp     short loc_1402EEC79
0x1402eec60  mov     dword ptr [rbx+50h], 4
0x1402eec67  lea     rax, EfsCngDesEnc
0x1402eec6e  mov     [rbx+10h], rax
0x1402eec72  lea     rax, EfsCngDesDec
0x1402eec79  mov     [rbx+8], rax
0x1402eec7d  mov     rax, rbx
0x1402eec80  jmp     loc_1402EEBF5
```
