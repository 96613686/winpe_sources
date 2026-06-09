# CiAllocateImageDataForHvci

- ea: `0x1800a67cc`
- end: `0x1800a6b07`
- name: `CiAllocateImageDataForHvci`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18005b1b0`

## callees

- `0x180096298`
- `0x18009dc10`
- `0x1800a67cc`
- `0x1800a6b10`
- `0x1800a6bb0`
- `0x1800a6cb8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800a6887`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6887`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a6ada`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a6af9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a6ada`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a6af9`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a682b`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a682b`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a6a68`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a6a68`

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
0x1800a67cc  mov     rax, rsp
0x1800a67cf  mov     [rax+10h], rbx
0x1800a67d3  mov     [rax+18h], rsi
0x1800a67d7  mov     [rax+20h], r9
0x1800a67db  push    rdi
0x1800a67dc  push    r12
0x1800a67de  push    r13
0x1800a67e0  push    r14
0x1800a67e2  push    r15
0x1800a67e4  sub     rsp, 60h
0x1800a67e8  mov     edi, r8d
0x1800a67eb  mov     r14, rdx
0x1800a67ee  mov     rsi, rcx
0x1800a67f1  xor     r15d, r15d
0x1800a67f4  mov     [rax-58h], r15
0x1800a67f8  xor     r12b, r12b
0x1800a67fb  mov     [rsp+88h+arg_0], r12b
0x1800a6803  xor     ebx, ebx
0x1800a6805  mov     [rax-38h], rbx
0x1800a6809  mov     [rax-60h], rbx
0x1800a680d  add     rcx, 58h ; 'X'
0x1800a6811  call    CiHvciIsImageDisallowed
0x1800a6816  test    al, al
0x1800a6818  jnz     loc_1800A6AB5
0x1800a681e  mov     r8d, edi; Size
0x1800a6821  lea     r9, [rsp+88h+NtHeader]; NtHeader
0x1800a6826  mov     rdx, r14; BaseAddress
0x1800a6829  xor     ecx, ecx; Flags
0x1800a682b  call    cs:__imp_RtlImageNtHeaderEx
0x1800a6832  nop     dword ptr [rax+rax+00h]
0x1800a6837  mov     edi, eax
0x1800a6839  mov     [rsp+88h+var_68], eax
0x1800a683d  test    eax, eax
0x1800a683f  js      loc_1800A6A15
0x1800a6845  mov     rdx, [rsp+88h+NtHeader]
0x1800a684a  mov     ecx, [rdx+50h]
0x1800a684d  mov     edi, 0FFFh
0x1800a6852  test    edi, ecx
0x1800a6854  mov     eax, ebx
0x1800a6856  setnz   al
0x1800a6859  shr     ecx, 0Ch
0x1800a685c  lea     r13d, [rax+rcx]
0x1800a6860  mov     [rsp+88h+var_30], r13d
0x1800a6865  movzx   eax, word ptr [rdx+6]
0x1800a6869  add     eax, 0Ch
0x1800a686c  lea     ecx, [rax+rax*2]
0x1800a686f  lea     eax, [r13+1Fh]
0x1800a6873  shr     eax, 5
0x1800a6876  lea     edx, [rax+rcx*2]
0x1800a6879  shl     edx, 2
0x1800a687c  mov     ecx, 100h
0x1800a6881  mov     r8d, 63734943h
0x1800a6887  call    cs:__imp_ExAllocatePool2
0x1800a688e  nop     dword ptr [rax+rax+00h]
0x1800a6893  mov     rbx, rax
0x1800a6896  mov     [rsp+88h+var_38], rax
0x1800a689b  test    rax, rax
0x1800a689e  jz      loc_1800A6A17
0x1800a68a4  mov     dword ptr [rax], 2
0x1800a68aa  mov     rax, cs:g_CiPolicyGenerationCounter
0x1800a68b1  mov     [rbx+8], rax
0x1800a68b5  mov     rax, [rsp+88h+NtHeader]
0x1800a68ba  mov     ecx, [rax+54h]
0x1800a68bd  mov     [rbx+50h], ecx
0x1800a68c0  mov     [rbx+38h], r15
0x1800a68c4  mov     rax, [rsi+28h]
0x1800a68c8  mov     rcx, [rax+10h]
0x1800a68cc  mov     [rbx+30h], rcx
0x1800a68d0  mov     [rbx+44h], r13d
0x1800a68d4  mov     rax, [rsp+88h+NtHeader]
0x1800a68d9  movzx   eax, word ptr [rax+6]
0x1800a68dd  mov     [rsp+88h+var_50], eax
0x1800a68e1  inc     eax
0x1800a68e3  mov     [rbx+48h], eax
0x1800a68e6  lea     rdx, [rbx+108h]
0x1800a68ed  mov     [rsp+88h+var_48], rdx
0x1800a68f2  mov     rax, [rsp+88h+NtHeader]
0x1800a68f7  mov     ecx, [rax+54h]
0x1800a68fa  test    edi, ecx
0x1800a68fc  mov     eax, r15d
0x1800a68ff  setnz   al
0x1800a6902  shr     ecx, 0Ch
0x1800a6905  add     eax, ecx
0x1800a6907  mov     [rdx+10h], eax
0x1800a690a  lea     r14, [rdx+18h]
0x1800a690e  mov     [rsp+88h+var_48], r14
0x1800a6913  mov     rcx, [rsp+88h+NtHeader]
0x1800a6918  movzx   eax, word ptr [rcx+14h]
0x1800a691c  lea     rsi, [rcx+18h]
0x1800a6920  add     rsi, rax
0x1800a6923  mov     [rsp+88h+var_40], rsi
0x1800a6928  movzx   edx, word ptr [rcx+6]
0x1800a692c  lea     r8, [rsp+88h+var_58]
0x1800a6931  mov     rcx, rsi
0x1800a6934  call    CiGetSortedImageSectionTable
0x1800a6939  mov     edi, eax
0x1800a693b  mov     [rsp+88h+var_68], eax
0x1800a693f  test    eax, eax
0x1800a6941  js      loc_1800A6A22
0x1800a6947  mov     r15, [rsp+88h+var_58]
0x1800a694c  test    r15, r15
0x1800a694f  cmovnz  rsi, r15
0x1800a6953  mov     [rsp+88h+var_40], rsi
0x1800a6958  mov     edi, 0C000007Bh
0x1800a695d  mov     [rsp+88h+var_68], edi
0x1800a6961  xor     edx, edx
0x1800a6963  mov     [rsp+88h+var_4C], edx
0x1800a6967  mov     r8d, [rsp+88h+var_50]
0x1800a696c  mov     r9d, 0FFFh
0x1800a6972  cmp     edx, r8d
0x1800a6975  jnb     loc_1800A6A31
0x1800a697b  mov     rcx, rsi
0x1800a697e  mov     rax, [rsp+88h+NtHeader]
0x1800a6983  sub     rcx, rax
0x1800a6986  add     rcx, 28h ; '('
0x1800a698a  mov     eax, [rax+54h]
0x1800a698d  cmp     rcx, rax
0x1800a6990  jg      loc_1800A6A29
0x1800a6996  mov     ecx, [rsi+0Ch]
0x1800a6999  test    r9d, ecx
0x1800a699c  jnz     loc_1800A6A2B
0x1800a69a2  cmp     dword ptr [rsi+10h], 0
0x1800a69a6  jz      short loc_1800A6A10
0x1800a69a8  shr     ecx, 0Ch
0x1800a69ab  mov     [r14+0Ch], ecx
0x1800a69af  mov     eax, [r14-0Ch]
0x1800a69b3  add     eax, [r14-8]
0x1800a69b7  cmp     ecx, eax
0x1800a69b9  jb      short loc_1800A6A2D
0x1800a69bb  mov     eax, [rsi+10h]
0x1800a69be  add     eax, [rsi+14h]
0x1800a69c1  mov     [rbx+50h], eax
0x1800a69c4  mov     eax, [rsi+14h]
0x1800a69c7  mov     [r14], rax
0x1800a69ca  mov     ecx, [rsi+8]
0x1800a69cd  test    r9d, ecx
0x1800a69d0  mov     eax, 0
0x1800a69d5  setnz   al
0x1800a69d8  shr     ecx, 0Ch
0x1800a69db  add     eax, ecx
0x1800a69dd  mov     [r14+10h], eax
0x1800a69e1  mov     ecx, [rsi+10h]
0x1800a69e4  mov     [r14+8], ecx
0x1800a69e8  mov     eax, [r14+10h]
0x1800a69ec  shl     eax, 0Ch
0x1800a69ef  cmp     ecx, eax
0x1800a69f1  ja      short loc_1800A6A2F
0x1800a69f3  add     r14, 18h
0x1800a69f7  mov     [rsp+88h+var_48], r14
0x1800a69fc  add     rsi, 28h ; '('
0x1800a6a00  mov     [rsp+88h+var_40], rsi
0x1800a6a05  inc     edx
0x1800a6a07  mov     [rsp+88h+var_4C], edx
0x1800a6a0b  jmp     loc_1800A6972
0x1800a6a10  dec     dword ptr [rbx+48h]
0x1800a6a13  jmp     short loc_1800A69FC
0x1800a6a15  jmp     short loc_1800A6A8E
0x1800a6a17  mov     edi, 0C0000017h
0x1800a6a1c  mov     [rsp+88h+var_68], edi
0x1800a6a20  jmp     short loc_1800A6A8E
0x1800a6a22  mov     r15, [rsp+88h+var_58]
0x1800a6a27  jmp     short loc_1800A6A8E
0x1800a6a29  jmp     short loc_1800A6A8E
0x1800a6a2b  jmp     short loc_1800A6A8E
0x1800a6a2d  jmp     short loc_1800A6A8E
0x1800a6a2f  jmp     short loc_1800A6A8E
0x1800a6a31  jmp     short loc_1800A6A4D
0x1800a6a33  mov     edi, eax
0x1800a6a35  mov     [rsp+88h+var_68], eax
0x1800a6a39  mov     r15, [rsp+88h+var_58]
0x1800a6a3e  mov     r12b, [rsp+88h+arg_0]
0x1800a6a46  mov     rbx, [rsp+88h+var_38]
0x1800a6a4b  jmp     short loc_1800A6A8E
0x1800a6a4d  sub     r14d, ebx
0x1800a6a50  mov     [rbx+4Ch], r14d
0x1800a6a54  mov     rcx, rbx; P
0x1800a6a57  call    CipFindOrInsertImage
0x1800a6a5c  mov     rbx, rax
0x1800a6a5f  mov     r12b, 1
0x1800a6a62  cmp     [rax+44h], r13d
0x1800a6a66  jnz     short loc_1800A6ACB
0x1800a6a68  call    cs:__imp_IoGetActivityIdThread
0x1800a6a6f  nop     dword ptr [rax+rax+00h]
0x1800a6a74  movups  xmm0, xmmword ptr [rax]
0x1800a6a77  movdqu  xmmword ptr [rbx+0F8h], xmm0
0x1800a6a7f  mov     rax, [rsp+88h+arg_18]
0x1800a6a87  mov     [rax], rbx
0x1800a6a8a  xor     ebx, ebx
0x1800a6a8c  xor     edi, edi
0x1800a6a8e  test    r15, r15
0x1800a6a91  jnz     short loc_1800A6AD2
0x1800a6a93  test    rbx, rbx
0x1800a6a96  jnz     short loc_1800A6AE8
0x1800a6a98  mov     eax, edi
0x1800a6a9a  lea     r11, [rsp+88h+var_28]
0x1800a6a9f  mov     rbx, [r11+38h]
0x1800a6aa3  mov     rsi, [r11+40h]
0x1800a6aa7  mov     rsp, r11
0x1800a6aaa  pop     r15
0x1800a6aac  pop     r14
0x1800a6aae  pop     r13
0x1800a6ab0  pop     r12
0x1800a6ab2  pop     rdi
0x1800a6ab3  retn
0x1800a6ab5  lea     rdx, CiWritableExecutableSection
0x1800a6abc  mov     rcx, rsi
0x1800a6abf  call    CipQueryAndLogFileNameForEvent
0x1800a6ac4  mov     edi, 0C00000BBh
0x1800a6ac9  jmp     short loc_1800A6A8E
0x1800a6acb  mov     edi, 0C0000428h
0x1800a6ad0  jmp     short loc_1800A6A8E
0x1800a6ad2  mov     edx, 63734943h; Tag
0x1800a6ad7  mov     rcx, r15; P
0x1800a6ada  call    cs:__imp_ExFreePoolWithTag
0x1800a6ae1  nop     dword ptr [rax+rax+00h]
0x1800a6ae6  jmp     short loc_1800A6A93
0x1800a6ae8  mov     rcx, rbx; P
0x1800a6aeb  test    r12b, r12b
0x1800a6aee  jz      short loc_1800A6AF7
0x1800a6af0  call    CipReleaseImage
0x1800a6af5  jmp     short loc_1800A6A98
0x1800a6af7  xor     edx, edx; Tag
0x1800a6af9  call    cs:__imp_ExFreePoolWithTag
0x1800a6b00  nop     dword ptr [rax+rax+00h]
0x1800a6b05  jmp     short loc_1800A6A98
```
