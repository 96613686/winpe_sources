# CiAllocateImageDataForHvci

- ea: `0x1800a7c4c`
- end: `0x1800a7f87`
- name: `CiAllocateImageDataForHvci`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18005bec0`

## callees

- `0x1800978c8`
- `0x18009f240`
- `0x1800a7c4c`
- `0x1800a7f90`
- `0x1800a8030`
- `0x1800a8138`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800a7d07`
- `ntoskrnl!ExAllocatePool2` at `0x1800a7d07`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a7f5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a7f79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a7f5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a7f79`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a7cab`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x1800a7cab`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a7ee8`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a7ee8`

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
0x1800a7c4c  mov     rax, rsp
0x1800a7c4f  mov     [rax+10h], rbx
0x1800a7c53  mov     [rax+18h], rsi
0x1800a7c57  mov     [rax+20h], r9
0x1800a7c5b  push    rdi
0x1800a7c5c  push    r12
0x1800a7c5e  push    r13
0x1800a7c60  push    r14
0x1800a7c62  push    r15
0x1800a7c64  sub     rsp, 60h
0x1800a7c68  mov     edi, r8d
0x1800a7c6b  mov     r14, rdx
0x1800a7c6e  mov     rsi, rcx
0x1800a7c71  xor     r15d, r15d
0x1800a7c74  mov     [rax-58h], r15
0x1800a7c78  xor     r12b, r12b
0x1800a7c7b  mov     [rsp+88h+arg_0], r12b
0x1800a7c83  xor     ebx, ebx
0x1800a7c85  mov     [rax-38h], rbx
0x1800a7c89  mov     [rax-60h], rbx
0x1800a7c8d  add     rcx, 58h ; 'X'
0x1800a7c91  call    CiHvciIsImageDisallowed
0x1800a7c96  test    al, al
0x1800a7c98  jnz     loc_1800A7F35
0x1800a7c9e  mov     r8d, edi; Size
0x1800a7ca1  lea     r9, [rsp+88h+NtHeader]; NtHeader
0x1800a7ca6  mov     rdx, r14; BaseAddress
0x1800a7ca9  xor     ecx, ecx; Flags
0x1800a7cab  call    cs:__imp_RtlImageNtHeaderEx
0x1800a7cb2  nop     dword ptr [rax+rax+00h]
0x1800a7cb7  mov     edi, eax
0x1800a7cb9  mov     [rsp+88h+var_68], eax
0x1800a7cbd  test    eax, eax
0x1800a7cbf  js      loc_1800A7E95
0x1800a7cc5  mov     rdx, [rsp+88h+NtHeader]
0x1800a7cca  mov     ecx, [rdx+50h]
0x1800a7ccd  mov     edi, 0FFFh
0x1800a7cd2  test    edi, ecx
0x1800a7cd4  mov     eax, ebx
0x1800a7cd6  setnz   al
0x1800a7cd9  shr     ecx, 0Ch
0x1800a7cdc  lea     r13d, [rax+rcx]
0x1800a7ce0  mov     [rsp+88h+var_30], r13d
0x1800a7ce5  movzx   eax, word ptr [rdx+6]
0x1800a7ce9  add     eax, 0Ch
0x1800a7cec  lea     ecx, [rax+rax*2]
0x1800a7cef  lea     eax, [r13+1Fh]
0x1800a7cf3  shr     eax, 5
0x1800a7cf6  lea     edx, [rax+rcx*2]
0x1800a7cf9  shl     edx, 2
0x1800a7cfc  mov     ecx, 100h
0x1800a7d01  mov     r8d, 63734943h
0x1800a7d07  call    cs:__imp_ExAllocatePool2
0x1800a7d0e  nop     dword ptr [rax+rax+00h]
0x1800a7d13  mov     rbx, rax
0x1800a7d16  mov     [rsp+88h+var_38], rax
0x1800a7d1b  test    rax, rax
0x1800a7d1e  jz      loc_1800A7E97
0x1800a7d24  mov     dword ptr [rax], 2
0x1800a7d2a  mov     rax, cs:g_CiPolicyGenerationCounter
0x1800a7d31  mov     [rbx+8], rax
0x1800a7d35  mov     rax, [rsp+88h+NtHeader]
0x1800a7d3a  mov     ecx, [rax+54h]
0x1800a7d3d  mov     [rbx+50h], ecx
0x1800a7d40  mov     [rbx+38h], r15
0x1800a7d44  mov     rax, [rsi+28h]
0x1800a7d48  mov     rcx, [rax+10h]
0x1800a7d4c  mov     [rbx+30h], rcx
0x1800a7d50  mov     [rbx+44h], r13d
0x1800a7d54  mov     rax, [rsp+88h+NtHeader]
0x1800a7d59  movzx   eax, word ptr [rax+6]
0x1800a7d5d  mov     [rsp+88h+var_50], eax
0x1800a7d61  inc     eax
0x1800a7d63  mov     [rbx+48h], eax
0x1800a7d66  lea     rdx, [rbx+108h]
0x1800a7d6d  mov     [rsp+88h+var_48], rdx
0x1800a7d72  mov     rax, [rsp+88h+NtHeader]
0x1800a7d77  mov     ecx, [rax+54h]
0x1800a7d7a  test    edi, ecx
0x1800a7d7c  mov     eax, r15d
0x1800a7d7f  setnz   al
0x1800a7d82  shr     ecx, 0Ch
0x1800a7d85  add     eax, ecx
0x1800a7d87  mov     [rdx+10h], eax
0x1800a7d8a  lea     r14, [rdx+18h]
0x1800a7d8e  mov     [rsp+88h+var_48], r14
0x1800a7d93  mov     rcx, [rsp+88h+NtHeader]
0x1800a7d98  movzx   eax, word ptr [rcx+14h]
0x1800a7d9c  lea     rsi, [rcx+18h]
0x1800a7da0  add     rsi, rax
0x1800a7da3  mov     [rsp+88h+var_40], rsi
0x1800a7da8  movzx   edx, word ptr [rcx+6]
0x1800a7dac  lea     r8, [rsp+88h+var_58]
0x1800a7db1  mov     rcx, rsi
0x1800a7db4  call    CiGetSortedImageSectionTable
0x1800a7db9  mov     edi, eax
0x1800a7dbb  mov     [rsp+88h+var_68], eax
0x1800a7dbf  test    eax, eax
0x1800a7dc1  js      loc_1800A7EA2
0x1800a7dc7  mov     r15, [rsp+88h+var_58]
0x1800a7dcc  test    r15, r15
0x1800a7dcf  cmovnz  rsi, r15
0x1800a7dd3  mov     [rsp+88h+var_40], rsi
0x1800a7dd8  mov     edi, 0C000007Bh
0x1800a7ddd  mov     [rsp+88h+var_68], edi
0x1800a7de1  xor     edx, edx
0x1800a7de3  mov     [rsp+88h+var_4C], edx
0x1800a7de7  mov     r8d, [rsp+88h+var_50]
0x1800a7dec  mov     r9d, 0FFFh
0x1800a7df2  cmp     edx, r8d
0x1800a7df5  jnb     loc_1800A7EB1
0x1800a7dfb  mov     rcx, rsi
0x1800a7dfe  mov     rax, [rsp+88h+NtHeader]
0x1800a7e03  sub     rcx, rax
0x1800a7e06  add     rcx, 28h ; '('
0x1800a7e0a  mov     eax, [rax+54h]
0x1800a7e0d  cmp     rcx, rax
0x1800a7e10  jg      loc_1800A7EA9
0x1800a7e16  mov     ecx, [rsi+0Ch]
0x1800a7e19  test    r9d, ecx
0x1800a7e1c  jnz     loc_1800A7EAB
0x1800a7e22  cmp     dword ptr [rsi+10h], 0
0x1800a7e26  jz      short loc_1800A7E90
0x1800a7e28  shr     ecx, 0Ch
0x1800a7e2b  mov     [r14+0Ch], ecx
0x1800a7e2f  mov     eax, [r14-0Ch]
0x1800a7e33  add     eax, [r14-8]
0x1800a7e37  cmp     ecx, eax
0x1800a7e39  jb      short loc_1800A7EAD
0x1800a7e3b  mov     eax, [rsi+10h]
0x1800a7e3e  add     eax, [rsi+14h]
0x1800a7e41  mov     [rbx+50h], eax
0x1800a7e44  mov     eax, [rsi+14h]
0x1800a7e47  mov     [r14], rax
0x1800a7e4a  mov     ecx, [rsi+8]
0x1800a7e4d  test    r9d, ecx
0x1800a7e50  mov     eax, 0
0x1800a7e55  setnz   al
0x1800a7e58  shr     ecx, 0Ch
0x1800a7e5b  add     eax, ecx
0x1800a7e5d  mov     [r14+10h], eax
0x1800a7e61  mov     ecx, [rsi+10h]
0x1800a7e64  mov     [r14+8], ecx
0x1800a7e68  mov     eax, [r14+10h]
0x1800a7e6c  shl     eax, 0Ch
0x1800a7e6f  cmp     ecx, eax
0x1800a7e71  ja      short loc_1800A7EAF
0x1800a7e73  add     r14, 18h
0x1800a7e77  mov     [rsp+88h+var_48], r14
0x1800a7e7c  add     rsi, 28h ; '('
0x1800a7e80  mov     [rsp+88h+var_40], rsi
0x1800a7e85  inc     edx
0x1800a7e87  mov     [rsp+88h+var_4C], edx
0x1800a7e8b  jmp     loc_1800A7DF2
0x1800a7e90  dec     dword ptr [rbx+48h]
0x1800a7e93  jmp     short loc_1800A7E7C
0x1800a7e95  jmp     short loc_1800A7F0E
0x1800a7e97  mov     edi, 0C0000017h
0x1800a7e9c  mov     [rsp+88h+var_68], edi
0x1800a7ea0  jmp     short loc_1800A7F0E
0x1800a7ea2  mov     r15, [rsp+88h+var_58]
0x1800a7ea7  jmp     short loc_1800A7F0E
0x1800a7ea9  jmp     short loc_1800A7F0E
0x1800a7eab  jmp     short loc_1800A7F0E
0x1800a7ead  jmp     short loc_1800A7F0E
0x1800a7eaf  jmp     short loc_1800A7F0E
0x1800a7eb1  jmp     short loc_1800A7ECD
0x1800a7eb3  mov     edi, eax
0x1800a7eb5  mov     [rsp+88h+var_68], eax
0x1800a7eb9  mov     r15, [rsp+88h+var_58]
0x1800a7ebe  mov     r12b, [rsp+88h+arg_0]
0x1800a7ec6  mov     rbx, [rsp+88h+var_38]
0x1800a7ecb  jmp     short loc_1800A7F0E
0x1800a7ecd  sub     r14d, ebx
0x1800a7ed0  mov     [rbx+4Ch], r14d
0x1800a7ed4  mov     rcx, rbx; P
0x1800a7ed7  call    CipFindOrInsertImage
0x1800a7edc  mov     rbx, rax
0x1800a7edf  mov     r12b, 1
0x1800a7ee2  cmp     [rax+44h], r13d
0x1800a7ee6  jnz     short loc_1800A7F4B
0x1800a7ee8  call    cs:__imp_IoGetActivityIdThread
0x1800a7eef  nop     dword ptr [rax+rax+00h]
0x1800a7ef4  movups  xmm0, xmmword ptr [rax]
0x1800a7ef7  movdqu  xmmword ptr [rbx+0F8h], xmm0
0x1800a7eff  mov     rax, [rsp+88h+arg_18]
0x1800a7f07  mov     [rax], rbx
0x1800a7f0a  xor     ebx, ebx
0x1800a7f0c  xor     edi, edi
0x1800a7f0e  test    r15, r15
0x1800a7f11  jnz     short loc_1800A7F52
0x1800a7f13  test    rbx, rbx
0x1800a7f16  jnz     short loc_1800A7F68
0x1800a7f18  mov     eax, edi
0x1800a7f1a  lea     r11, [rsp+88h+var_28]
0x1800a7f1f  mov     rbx, [r11+38h]
0x1800a7f23  mov     rsi, [r11+40h]
0x1800a7f27  mov     rsp, r11
0x1800a7f2a  pop     r15
0x1800a7f2c  pop     r14
0x1800a7f2e  pop     r13
0x1800a7f30  pop     r12
0x1800a7f32  pop     rdi
0x1800a7f33  retn
0x1800a7f35  lea     rdx, CiWritableExecutableSection
0x1800a7f3c  mov     rcx, rsi
0x1800a7f3f  call    CipQueryAndLogFileNameForEvent
0x1800a7f44  mov     edi, 0C00000BBh
0x1800a7f49  jmp     short loc_1800A7F0E
0x1800a7f4b  mov     edi, 0C0000428h
0x1800a7f50  jmp     short loc_1800A7F0E
0x1800a7f52  mov     edx, 63734943h; Tag
0x1800a7f57  mov     rcx, r15; P
0x1800a7f5a  call    cs:__imp_ExFreePoolWithTag
0x1800a7f61  nop     dword ptr [rax+rax+00h]
0x1800a7f66  jmp     short loc_1800A7F13
0x1800a7f68  mov     rcx, rbx; P
0x1800a7f6b  test    r12b, r12b
0x1800a7f6e  jz      short loc_1800A7F77
0x1800a7f70  call    CipReleaseImage
0x1800a7f75  jmp     short loc_1800A7F18
0x1800a7f77  xor     edx, edx; Tag
0x1800a7f79  call    cs:__imp_ExFreePoolWithTag
0x1800a7f80  nop     dword ptr [rax+rax+00h]
0x1800a7f85  jmp     short loc_1800A7F18
```
