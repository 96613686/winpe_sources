# CiAllocateImageDataForHvci

- ea: `0x1800a3148`
- end: `0x1800a3483`
- name: `CiAllocateImageDataForHvci`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18005bdf0`

## callees

- `0x18008e098`
- `0x1800904cc`
- `0x1800a3148`
- `0x1800a348c`
- `0x1800a352c`
- `0x1800a3634`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800a3203`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3203`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3456`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3475`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3456`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3475`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a33e4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a33e4`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a31a7`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a31a7`

## pseudocode

```c
__int64 __fastcall CiAllocateImageDataForHvci(__int64 a1, void *a2, unsigned int a3, __int64 *a4)
{
  void *v7; // r15
  char v8; // r12
  __int64 inserted; // rbx
  NTSTATUS SortedImageSectionTable; // edi
  DWORD v11; // r13d
  __int64 Pool2; // rax
  __int64 v13; // r14
  char *v14; // rsi
  unsigned int v15; // edx
  unsigned int v16; // r8d
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  __int64 v20; // rcx
  PIMAGE_NT_HEADERS NtHeader; // [rsp+28h] [rbp-60h] BYREF
  void *v23; // [rsp+30h] [rbp-58h] BYREF
  unsigned int NumberOfSections; // [rsp+38h] [rbp-50h]
  int v25; // [rsp+3Ch] [rbp-4Ch]
  __int64 v26; // [rsp+40h] [rbp-48h]
  char *v27; // [rsp+48h] [rbp-40h]
  __int64 v28; // [rsp+50h] [rbp-38h]
  DWORD v29; // [rsp+58h] [rbp-30h]

  v7 = 0;
  v23 = 0;
  v8 = 0;
  inserted = 0;
  v28 = 0;
  NtHeader = 0;
  if ( (unsigned __int8)CiHvciIsImageDisallowed(a1 + 88) )
  {
    CipQueryAndLogFileNameForEvent(a1, CiWritableExecutableSection);
    SortedImageSectionTable = -1073741637;
  }
  else
  {
    SortedImageSectionTable = RtlImageNtHeaderEx(0, a2, a3, &NtHeader);
    if ( SortedImageSectionTable >= 0 )
    {
      v11 = ((NtHeader->OptionalHeader.SizeOfImage & 0xFFF) != 0) + (NtHeader->OptionalHeader.SizeOfImage >> 12);
      v29 = v11;
      Pool2 = ExAllocatePool2(
                256,
                4 * (((v11 + 31) >> 5) + 6 * (NtHeader->FileHeader.NumberOfSections + 12)),
                1668499779);
      inserted = Pool2;
      v28 = Pool2;
      if ( Pool2 )
      {
        *(_DWORD *)Pool2 = 2;
        *(_QWORD *)(Pool2 + 8) = g_CiPolicyGenerationCounter;
        *(_DWORD *)(Pool2 + 80) = NtHeader->OptionalHeader.SizeOfHeaders;
        *(_QWORD *)(Pool2 + 56) = 0;
        *(_QWORD *)(Pool2 + 48) = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL);
        *(_DWORD *)(Pool2 + 68) = v11;
        NumberOfSections = NtHeader->FileHeader.NumberOfSections;
        *(_DWORD *)(Pool2 + 72) = NumberOfSections + 1;
        v26 = Pool2 + 264;
        *(_DWORD *)(Pool2 + 280) = (NtHeader->OptionalHeader.SizeOfHeaders >> 12)
                                 + ((NtHeader->OptionalHeader.SizeOfHeaders & 0xFFF) != 0);
        v13 = Pool2 + 288;
        v26 = Pool2 + 288;
        v14 = (char *)&NtHeader->OptionalHeader + NtHeader->FileHeader.SizeOfOptionalHeader;
        v27 = v14;
        SortedImageSectionTable = CiGetSortedImageSectionTable(v14, NtHeader->FileHeader.NumberOfSections, &v23);
        if ( SortedImageSectionTable < 0 )
        {
          v7 = v23;
        }
        else
        {
          v7 = v23;
          if ( v23 )
            v14 = (char *)v23;
          v27 = v14;
          SortedImageSectionTable = -1073741701;
          v15 = 0;
          v25 = 0;
          v16 = NumberOfSections;
          while ( v15 < v16 )
          {
            if ( v14 - (char *)NtHeader + 40 > NtHeader->OptionalHeader.SizeOfHeaders )
              goto LABEL_26;
            v17 = *((_DWORD *)v14 + 3);
            if ( (v17 & 0xFFF) != 0 )
              goto LABEL_26;
            if ( *((_DWORD *)v14 + 4) )
            {
              v18 = v17 >> 12;
              *(_DWORD *)(v13 + 12) = v18;
              if ( v18 < *(_DWORD *)(v13 - 8) + *(_DWORD *)(v13 - 12) )
                goto LABEL_26;
              *(_DWORD *)(inserted + 80) = *((_DWORD *)v14 + 5) + *((_DWORD *)v14 + 4);
              *(_QWORD *)v13 = *((unsigned int *)v14 + 5);
              *(_DWORD *)(v13 + 16) = (*((_DWORD *)v14 + 2) >> 12) + ((*((_DWORD *)v14 + 2) & 0xFFF) != 0);
              v19 = *((_DWORD *)v14 + 4);
              *(_DWORD *)(v13 + 8) = v19;
              if ( v19 > *(_DWORD *)(v13 + 16) << 12 )
                goto LABEL_26;
              v13 += 24;
              v26 = v13;
            }
            else
            {
              --*(_DWORD *)(inserted + 72);
            }
            v14 += 40;
            v27 = v14;
            v25 = ++v15;
          }
          *(_DWORD *)(inserted + 76) = v13 - inserted;
          inserted = CipFindOrInsertImage((PVOID)inserted);
          v8 = 1;
          if ( *(_DWORD *)(inserted + 68) == v11 )
          {
            *(_OWORD *)(inserted + 248) = *(_OWORD *)IoGetActivityIdThread(v20);
            *a4 = inserted;
            inserted = 0;
            SortedImageSectionTable = 0;
          }
          else
          {
            SortedImageSectionTable = -1073740760;
          }
        }
      }
      else
      {
        SortedImageSectionTable = -1073741801;
      }
    }
  }
LABEL_26:
  if ( v7 )
    ExFreePoolWithTag(v7, 0x63734943u);
  if ( inserted )
  {
    if ( v8 )
      CipReleaseImage((PVOID)inserted);
    else
      ExFreePoolWithTag((PVOID)inserted, 0);
  }
  return (unsigned int)SortedImageSectionTable;
}

```

## disassembly

```asm
0x1800a3148  mov     rax, rsp
0x1800a314b  mov     [rax+10h], rbx
0x1800a314f  mov     [rax+18h], rsi
0x1800a3153  mov     [rax+20h], r9
0x1800a3157  push    rdi
0x1800a3158  push    r12
0x1800a315a  push    r13
0x1800a315c  push    r14
0x1800a315e  push    r15
0x1800a3160  sub     rsp, 60h
0x1800a3164  mov     edi, r8d
0x1800a3167  mov     r14, rdx
0x1800a316a  mov     rsi, rcx
0x1800a316d  xor     r15d, r15d
0x1800a3170  mov     [rax-58h], r15
0x1800a3174  xor     r12b, r12b
0x1800a3177  mov     [rsp+88h+arg_0], r12b
0x1800a317f  xor     ebx, ebx
0x1800a3181  mov     [rax-38h], rbx
0x1800a3185  mov     [rax-60h], rbx
0x1800a3189  add     rcx, 58h ; 'X'
0x1800a318d  call    CiHvciIsImageDisallowed
0x1800a3192  test    al, al
0x1800a3194  jnz     loc_1800A3431
0x1800a319a  mov     r8d, edi; Size
0x1800a319d  lea     r9, [rsp+88h+NtHeader]; NtHeader
0x1800a31a2  mov     rdx, r14; BaseAddress
0x1800a31a5  xor     ecx, ecx; Flags
0x1800a31a7  call    cs:__imp_RtlImageNtHeaderEx
0x1800a31ae  nop     dword ptr [rax+rax+00h]
0x1800a31b3  mov     edi, eax
0x1800a31b5  mov     [rsp+88h+var_68], eax
0x1800a31b9  test    eax, eax
0x1800a31bb  js      loc_1800A3391
0x1800a31c1  mov     rdx, [rsp+88h+NtHeader]
0x1800a31c6  mov     ecx, [rdx+50h]
0x1800a31c9  mov     edi, 0FFFh
0x1800a31ce  test    edi, ecx
0x1800a31d0  mov     eax, ebx
0x1800a31d2  setnz   al
0x1800a31d5  shr     ecx, 0Ch
0x1800a31d8  lea     r13d, [rax+rcx]
0x1800a31dc  mov     [rsp+88h+var_30], r13d
0x1800a31e1  movzx   eax, word ptr [rdx+6]
0x1800a31e5  add     eax, 0Ch
0x1800a31e8  lea     ecx, [rax+rax*2]
0x1800a31eb  lea     eax, [r13+1Fh]
0x1800a31ef  shr     eax, 5
0x1800a31f2  lea     edx, [rax+rcx*2]
0x1800a31f5  shl     edx, 2
0x1800a31f8  mov     ecx, 100h
0x1800a31fd  mov     r8d, 63734943h
0x1800a3203  call    cs:__imp_ExAllocatePool2
0x1800a320a  nop     dword ptr [rax+rax+00h]
0x1800a320f  mov     rbx, rax
0x1800a3212  mov     [rsp+88h+var_38], rax
0x1800a3217  test    rax, rax
0x1800a321a  jz      loc_1800A3393
0x1800a3220  mov     dword ptr [rax], 2
0x1800a3226  mov     rax, cs:g_CiPolicyGenerationCounter
0x1800a322d  mov     [rbx+8], rax
0x1800a3231  mov     rax, [rsp+88h+NtHeader]
0x1800a3236  mov     ecx, [rax+54h]
0x1800a3239  mov     [rbx+50h], ecx
0x1800a323c  mov     [rbx+38h], r15
0x1800a3240  mov     rax, [rsi+28h]
0x1800a3244  mov     rcx, [rax+10h]
0x1800a3248  mov     [rbx+30h], rcx
0x1800a324c  mov     [rbx+44h], r13d
0x1800a3250  mov     rax, [rsp+88h+NtHeader]
0x1800a3255  movzx   eax, word ptr [rax+6]
0x1800a3259  mov     [rsp+88h+var_50], eax
0x1800a325d  inc     eax
0x1800a325f  mov     [rbx+48h], eax
0x1800a3262  lea     rdx, [rbx+108h]
0x1800a3269  mov     [rsp+88h+var_48], rdx
0x1800a326e  mov     rax, [rsp+88h+NtHeader]
0x1800a3273  mov     ecx, [rax+54h]
0x1800a3276  test    edi, ecx
0x1800a3278  mov     eax, r15d
0x1800a327b  setnz   al
0x1800a327e  shr     ecx, 0Ch
0x1800a3281  add     eax, ecx
0x1800a3283  mov     [rdx+10h], eax
0x1800a3286  lea     r14, [rdx+18h]
0x1800a328a  mov     [rsp+88h+var_48], r14
0x1800a328f  mov     rcx, [rsp+88h+NtHeader]
0x1800a3294  movzx   eax, word ptr [rcx+14h]
0x1800a3298  lea     rsi, [rcx+18h]
0x1800a329c  add     rsi, rax
0x1800a329f  mov     [rsp+88h+var_40], rsi
0x1800a32a4  movzx   edx, word ptr [rcx+6]
0x1800a32a8  lea     r8, [rsp+88h+var_58]
0x1800a32ad  mov     rcx, rsi
0x1800a32b0  call    CiGetSortedImageSectionTable
0x1800a32b5  mov     edi, eax
0x1800a32b7  mov     [rsp+88h+var_68], eax
0x1800a32bb  test    eax, eax
0x1800a32bd  js      loc_1800A339E
0x1800a32c3  mov     r15, [rsp+88h+var_58]
0x1800a32c8  test    r15, r15
0x1800a32cb  cmovnz  rsi, r15
0x1800a32cf  mov     [rsp+88h+var_40], rsi
0x1800a32d4  mov     edi, 0C000007Bh
0x1800a32d9  mov     [rsp+88h+var_68], edi
0x1800a32dd  xor     edx, edx
0x1800a32df  mov     [rsp+88h+var_4C], edx
0x1800a32e3  mov     r8d, [rsp+88h+var_50]
0x1800a32e8  mov     r9d, 0FFFh
0x1800a32ee  cmp     edx, r8d
0x1800a32f1  jnb     loc_1800A33AD
0x1800a32f7  mov     rcx, rsi
0x1800a32fa  mov     rax, [rsp+88h+NtHeader]
0x1800a32ff  sub     rcx, rax
0x1800a3302  add     rcx, 28h ; '('
0x1800a3306  mov     eax, [rax+54h]
0x1800a3309  cmp     rcx, rax
0x1800a330c  jg      loc_1800A33A5
0x1800a3312  mov     ecx, [rsi+0Ch]
0x1800a3315  test    r9d, ecx
0x1800a3318  jnz     loc_1800A33A7
0x1800a331e  cmp     dword ptr [rsi+10h], 0
0x1800a3322  jz      short loc_1800A338C
0x1800a3324  shr     ecx, 0Ch
0x1800a3327  mov     [r14+0Ch], ecx
0x1800a332b  mov     eax, [r14-0Ch]
0x1800a332f  add     eax, [r14-8]
0x1800a3333  cmp     ecx, eax
0x1800a3335  jb      short loc_1800A33A9
0x1800a3337  mov     eax, [rsi+10h]
0x1800a333a  add     eax, [rsi+14h]
0x1800a333d  mov     [rbx+50h], eax
0x1800a3340  mov     eax, [rsi+14h]
0x1800a3343  mov     [r14], rax
0x1800a3346  mov     ecx, [rsi+8]
0x1800a3349  test    r9d, ecx
0x1800a334c  mov     eax, 0
0x1800a3351  setnz   al
0x1800a3354  shr     ecx, 0Ch
0x1800a3357  add     eax, ecx
0x1800a3359  mov     [r14+10h], eax
0x1800a335d  mov     ecx, [rsi+10h]
0x1800a3360  mov     [r14+8], ecx
0x1800a3364  mov     eax, [r14+10h]
0x1800a3368  shl     eax, 0Ch
0x1800a336b  cmp     ecx, eax
0x1800a336d  ja      short loc_1800A33AB
0x1800a336f  add     r14, 18h
0x1800a3373  mov     [rsp+88h+var_48], r14
0x1800a3378  add     rsi, 28h ; '('
0x1800a337c  mov     [rsp+88h+var_40], rsi
0x1800a3381  inc     edx
0x1800a3383  mov     [rsp+88h+var_4C], edx
0x1800a3387  jmp     loc_1800A32EE
0x1800a338c  dec     dword ptr [rbx+48h]
0x1800a338f  jmp     short loc_1800A3378
0x1800a3391  jmp     short loc_1800A340A
0x1800a3393  mov     edi, 0C0000017h
0x1800a3398  mov     [rsp+88h+var_68], edi
0x1800a339c  jmp     short loc_1800A340A
0x1800a339e  mov     r15, [rsp+88h+var_58]
0x1800a33a3  jmp     short loc_1800A340A
0x1800a33a5  jmp     short loc_1800A340A
0x1800a33a7  jmp     short loc_1800A340A
0x1800a33a9  jmp     short loc_1800A340A
0x1800a33ab  jmp     short loc_1800A340A
0x1800a33ad  jmp     short loc_1800A33C9
0x1800a33af  mov     edi, eax
0x1800a33b1  mov     [rsp+88h+var_68], eax
0x1800a33b5  mov     r15, [rsp+88h+var_58]
0x1800a33ba  mov     r12b, [rsp+88h+arg_0]
0x1800a33c2  mov     rbx, [rsp+88h+var_38]
0x1800a33c7  jmp     short loc_1800A340A
0x1800a33c9  sub     r14d, ebx
0x1800a33cc  mov     [rbx+4Ch], r14d
0x1800a33d0  mov     rcx, rbx; P
0x1800a33d3  call    CipFindOrInsertImage
0x1800a33d8  mov     rbx, rax
0x1800a33db  mov     r12b, 1
0x1800a33de  cmp     [rax+44h], r13d
0x1800a33e2  jnz     short loc_1800A3447
0x1800a33e4  call    cs:__imp_IoGetActivityIdThread
0x1800a33eb  nop     dword ptr [rax+rax+00h]
0x1800a33f0  movups  xmm0, xmmword ptr [rax]
0x1800a33f3  movdqu  xmmword ptr [rbx+0F8h], xmm0
0x1800a33fb  mov     rax, [rsp+88h+arg_18]
0x1800a3403  mov     [rax], rbx
0x1800a3406  xor     ebx, ebx
0x1800a3408  xor     edi, edi
0x1800a340a  test    r15, r15
0x1800a340d  jnz     short loc_1800A344E
0x1800a340f  test    rbx, rbx
0x1800a3412  jnz     short loc_1800A3464
0x1800a3414  mov     eax, edi
0x1800a3416  lea     r11, [rsp+88h+var_28]
0x1800a341b  mov     rbx, [r11+38h]
0x1800a341f  mov     rsi, [r11+40h]
0x1800a3423  mov     rsp, r11
0x1800a3426  pop     r15
0x1800a3428  pop     r14
0x1800a342a  pop     r13
0x1800a342c  pop     r12
0x1800a342e  pop     rdi
0x1800a342f  retn
0x1800a3431  lea     rdx, CiWritableExecutableSection
0x1800a3438  mov     rcx, rsi
0x1800a343b  call    CipQueryAndLogFileNameForEvent
0x1800a3440  mov     edi, 0C00000BBh
0x1800a3445  jmp     short loc_1800A340A
0x1800a3447  mov     edi, 0C0000428h
0x1800a344c  jmp     short loc_1800A340A
0x1800a344e  mov     edx, 63734943h; Tag
0x1800a3453  mov     rcx, r15; P
0x1800a3456  call    cs:__imp_ExFreePoolWithTag
0x1800a345d  nop     dword ptr [rax+rax+00h]
0x1800a3462  jmp     short loc_1800A340F
0x1800a3464  mov     rcx, rbx; P
0x1800a3467  test    r12b, r12b
0x1800a346a  jz      short loc_1800A3473
0x1800a346c  call    CipReleaseImage
0x1800a3471  jmp     short loc_1800A3414
0x1800a3473  xor     edx, edx; Tag
0x1800a3475  call    cs:__imp_ExFreePoolWithTag
0x1800a347c  nop     dword ptr [rax+rax+00h]
0x1800a3481  jmp     short loc_1800A3414
```
