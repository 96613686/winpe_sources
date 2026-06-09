# CdCommonQueryVolInfo

- ea: `0x14001a688`
- end: `0x14001a8bb`
- name: `CdCommonQueryVolInfo`
- size: `563`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001160`
- `0x140003000`
- `0x1400181a4`
- `0x14001a400`
- `0x14001a688`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001a8a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bf1a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a8a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bf1a`
- `ntoskrnl!FsRtlGetSectorSizeInformation` at `0x14001a758`
- `ntoskrnl!FsRtlGetSectorSizeInformation` at `0x14001a758`

## pseudocode

```c
__int64 __fastcall CdCommonQueryVolInfo(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 v3; // r15
  __int64 v4; // r13
  __int64 v5; // rsi
  int v6; // eax
  __int64 v7; // rsi
  unsigned int SectorSizeInformation; // ebx
  unsigned int v10; // edi
  unsigned int v11; // eax
  _DWORD *v12; // rdx
  unsigned int v13; // ebx
  unsigned int v14; // eax
  _DWORD *v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned int v19; // edi
  unsigned int v20; // r12d

  v2 = a2;
  v3 = a1;
  v4 = *(_QWORD *)(a2 + 184);
  v5 = *(_QWORD *)(v4 + 48);
  v6 = *(_DWORD *)(v5 + 32) & 7;
  if ( v6 )
    v7 = *(_QWORD *)(v5 + 24);
  else
    v7 = 0;
  SectorSizeInformation = -1073741811;
  if ( v6 )
  {
    v10 = *(_DWORD *)(v4 + 8);
    CdAcquireResource(a1, *(_QWORD *)(v7 + 120) + 128LL, 0, 1);
    CdVerifyVcb(v3, *(_QWORD *)(v7 + 120));
    if ( *(_DWORD *)(v4 + 16) == 1 )
    {
      v17 = *(_QWORD *)(v2 + 24);
      v18 = *(_QWORD *)(v7 + 120);
      *(_QWORD *)v17 = *(_QWORD *)(*(_QWORD *)(v18 + 72) + 464LL);
      *(_DWORD *)(v17 + 8) = *(_DWORD *)(*(_QWORD *)(v18 + 8) + 24LL);
      *(_BYTE *)(v17 + 16) = 0;
      v19 = v10 - 18;
      v20 = *(unsigned __int16 *)(*(_QWORD *)(v18 + 8) + 6LL);
      SectorSizeInformation = v19 < v20 ? 0x80000005 : 0;
      if ( v19 < v20 )
        v20 = v19;
      *(_DWORD *)(v17 + 12) = v20;
      if ( v20 )
        memmove((void *)(v17 + 18), (const void *)(*(_QWORD *)(v18 + 8) + 32LL), v20);
      v10 = v19 - v20;
      goto LABEL_28;
    }
    if ( *(_DWORD *)(v4 + 16) == 3 )
    {
      v16 = *(_QWORD *)(v2 + 24);
      *(_QWORD *)v16 = *(__int64 *)(*(_QWORD *)(*(_QWORD *)(v7 + 120) + 72LL) + 24LL) >> 11;
      *(_QWORD *)(v16 + 8) = 0;
      *(_DWORD *)(v16 + 16) = 1;
      *(_DWORD *)(v16 + 20) = 2048;
      v10 -= 24;
    }
    else
    {
      if ( *(_DWORD *)(v4 + 16) != 4 )
      {
        if ( *(_DWORD *)(v4 + 16) == 5 )
        {
          v12 = *(_DWORD **)(v2 + 24);
          *v12 = 17301505;
          if ( (*(_DWORD *)(*(_QWORD *)(v3 + 16) + 48LL) & 4) != 0 )
          {
            *v12 = 17301509;
            v12[1] = 110;
          }
          else
          {
            v12[1] = 221;
          }
          v13 = (v10 - 12) & 0xFFFFFFFE;
          v14 = v13;
          if ( v13 >= 8 )
            v14 = 8;
          v10 = v13 - v14;
          v12[2] = v14;
          memmove(v12 + 3, L"CDFS", v14);
          SectorSizeInformation = v13 < 8 ? 0x80000005 : 0;
        }
        else if ( *(_DWORD *)(v4 + 16) == 11 )
        {
          SectorSizeInformation = FsRtlGetSectorSizeInformation(
                                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 120) + 8LL) + 16LL),
                                    *(_QWORD *)(v2 + 24));
          v11 = v10 - 28;
          if ( (SectorSizeInformation & 0x80000000) != 0 )
            v11 = v10;
          v10 = v11;
        }
        goto LABEL_28;
      }
      v15 = *(_DWORD **)(v2 + 24);
      v15[1] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 120) + 16LL) + 52LL);
      *v15 = 2;
      v10 -= 8;
    }
    SectorSizeInformation = 0;
LABEL_28:
    *(_QWORD *)(v2 + 56) = *(_DWORD *)(v4 + 8) - v10;
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v7 + 120) + 128LL));
    a2 = v2;
    a1 = v3;
  }
  CdCompleteRequest(a1, a2, SectorSizeInformation);
  return SectorSizeInformation;
}

```

## disassembly

```asm
0x14001a688  mov     [rsp+arg_0], rbx
0x14001a68d  mov     [rsp+arg_10], rsi
0x14001a692  push    rdi
0x14001a693  push    r12
0x14001a695  push    r13
0x14001a697  push    r14
0x14001a699  push    r15
0x14001a69b  sub     rsp, 20h
0x14001a69f  mov     r14, rdx
0x14001a6a2  mov     r15, rcx
0x14001a6a5  mov     r13, [rdx+0B8h]
0x14001a6ac  mov     rsi, [r13+30h]
0x14001a6b0  mov     eax, [rsi+20h]
0x14001a6b3  and     eax, 7
0x14001a6b6  jnz     short loc_14001A6BC
0x14001a6b8  xor     esi, esi
0x14001a6ba  jmp     short loc_14001A6C0
0x14001a6bc  mov     rsi, [rsi+18h]
0x14001a6c0  mov     [rsp+48h+arg_8], rsi
0x14001a6c5  mov     ebx, 0C000000Dh
0x14001a6ca  test    eax, eax
0x14001a6cc  jnz     short loc_14001A6F1
0x14001a6ce  mov     r8d, ebx
0x14001a6d1  call    CdCompleteRequest
0x14001a6d6  mov     eax, ebx
0x14001a6d8  mov     rbx, [rsp+48h+arg_0]
0x14001a6dd  mov     rsi, [rsp+48h+arg_10]
0x14001a6e2  add     rsp, 20h
0x14001a6e6  pop     r15
0x14001a6e8  pop     r14
0x14001a6ea  pop     r13
0x14001a6ec  pop     r12
0x14001a6ee  pop     rdi
0x14001a6ef  retn
0x14001a6f1  mov     edi, [r13+8]
0x14001a6f5  mov     rdx, [rsi+78h]
0x14001a6f9  sub     rdx, 0FFFFFFFFFFFFFF80h
0x14001a6fd  mov     r12d, 1
0x14001a703  mov     r9d, r12d
0x14001a706  xor     r8d, r8d
0x14001a709  call    CdAcquireResource
0x14001a70e  nop
0x14001a70f  mov     rdx, [rsi+78h]
0x14001a713  mov     rcx, r15
0x14001a716  call    CdVerifyVcb
0x14001a71b  mov     ecx, [r13+10h]
0x14001a71f  sub     ecx, r12d
0x14001a722  jz      loc_14001A82E
0x14001a728  sub     ecx, 2
0x14001a72b  jz      loc_14001A7FD
0x14001a731  sub     ecx, r12d
0x14001a734  jz      loc_14001A7E0
0x14001a73a  sub     ecx, r12d
0x14001a73d  jz      short loc_14001A775
0x14001a73f  cmp     ecx, 6
0x14001a742  jnz     loc_14001A892
0x14001a748  mov     rax, [rsi+78h]
0x14001a74c  mov     rcx, [rax+8]
0x14001a750  mov     rdx, [r14+18h]
0x14001a754  mov     rcx, [rcx+10h]
0x14001a758  call    cs:__imp_FsRtlGetSectorSizeInformation
0x14001a75f  nop     dword ptr [rax+rax+00h]
0x14001a764  mov     ebx, eax
0x14001a766  lea     eax, [rdi-1Ch]
0x14001a769  test    ebx, ebx
0x14001a76b  cmovs   eax, edi
0x14001a76e  mov     edi, eax
0x14001a770  jmp     loc_14001A892
0x14001a775  mov     rdx, [r14+18h]
0x14001a779  mov     dword ptr [rdx], 1080001h
0x14001a77f  mov     rax, [r15+10h]
0x14001a783  mov     ecx, [rax+30h]
0x14001a786  test    cl, 4
0x14001a789  jz      short loc_14001A79A
0x14001a78b  mov     dword ptr [rdx], 1080005h
0x14001a791  mov     dword ptr [rdx+4], 6Eh ; 'n'
0x14001a798  jmp     short loc_14001A7A1
0x14001a79a  mov     dword ptr [rdx+4], 0DDh
0x14001a7a1  lea     ebx, [rdi-0Ch]
0x14001a7a4  and     ebx, 0FFFFFFFEh
0x14001a7a7  mov     eax, ebx
0x14001a7a9  mov     r12d, 8
0x14001a7af  cmp     ebx, r12d
0x14001a7b2  cmovnb  eax, r12d
0x14001a7b6  mov     edi, ebx
0x14001a7b8  sub     edi, eax
0x14001a7ba  mov     [rdx+8], eax
0x14001a7bd  mov     r8d, eax; Size
0x14001a7c0  lea     rcx, [rdx+0Ch]; void *
0x14001a7c4  lea     rdx, aCdfs; "CDFS"
0x14001a7cb  call    memmove
0x14001a7d0  cmp     ebx, r12d
0x14001a7d3  sbb     ebx, ebx
0x14001a7d5  and     ebx, 80000005h
0x14001a7db  jmp     loc_14001A892
0x14001a7e0  mov     rdx, [r14+18h]
0x14001a7e4  mov     rax, [rsi+78h]
0x14001a7e8  mov     rcx, [rax+10h]
0x14001a7ec  mov     eax, [rcx+34h]
0x14001a7ef  mov     [rdx+4], eax
0x14001a7f2  mov     dword ptr [rdx], 2
0x14001a7f8  add     edi, 0FFFFFFF8h
0x14001a7fb  jmp     short loc_14001A82A
0x14001a7fd  mov     rdx, [r14+18h]
0x14001a801  mov     rax, [rsi+78h]
0x14001a805  mov     rcx, [rax+48h]
0x14001a809  mov     rax, [rcx+18h]
0x14001a80d  sar     rax, 0Bh
0x14001a811  mov     [rdx], rax
0x14001a814  mov     qword ptr [rdx+8], 0
0x14001a81c  mov     [rdx+10h], r12d
0x14001a820  mov     dword ptr [rdx+14h], 800h
0x14001a827  add     edi, 0FFFFFFE8h
0x14001a82a  xor     ebx, ebx
0x14001a82c  jmp     short loc_14001A892
0x14001a82e  mov     r9, [r14+18h]
0x14001a832  mov     rdx, [rsi+78h]
0x14001a836  mov     rax, [rdx+48h]
0x14001a83a  mov     rcx, [rax+1D0h]
0x14001a841  mov     [r9], rcx
0x14001a844  mov     rax, [rdx+8]
0x14001a848  mov     ecx, [rax+18h]
0x14001a84b  mov     [r9+8], ecx
0x14001a84f  mov     byte ptr [r9+10h], 0
0x14001a854  add     edi, 0FFFFFFEEh
0x14001a857  mov     rax, [rdx+8]
0x14001a85b  movzx   r12d, word ptr [rax+6]
0x14001a860  cmp     edi, r12d
0x14001a863  sbb     ebx, ebx
0x14001a865  and     ebx, 80000005h
0x14001a86b  cmp     edi, r12d
0x14001a86e  cmovb   r12d, edi
0x14001a872  mov     [r9+0Ch], r12d
0x14001a876  test    r12d, r12d
0x14001a879  jz      short loc_14001A88F
0x14001a87b  mov     r8d, r12d; Size
0x14001a87e  mov     rdx, [rdx+8]
0x14001a882  add     rdx, 20h ; ' '; Src
0x14001a886  lea     rcx, [r9+12h]; void *
0x14001a88a  call    memmove
0x14001a88f  sub     edi, r12d
0x14001a892  mov     eax, [r13+8]
0x14001a896  sub     eax, edi
0x14001a898  mov     [r14+38h], rax
0x14001a89c  mov     rcx, [rsi+78h]
0x14001a8a0  sub     rcx, 0FFFFFFFFFFFFFF80h; Resource
0x14001a8a4  call    cs:__imp_ExReleaseResourceLite
0x14001a8ab  nop     dword ptr [rax+rax+00h]
0x14001a8b0  mov     rdx, r14
0x14001a8b3  mov     rcx, r15
0x14001a8b6  jmp     loc_14001A6CE
0x14001bf05  push    rbp
0x14001bf07  sub     rsp, 20h
0x14001bf0b  mov     rbp, rdx
0x14001bf0e  mov     rax, [rbp+58h]
0x14001bf12  mov     rcx, [rax+78h]
0x14001bf16  sub     rcx, 0FFFFFFFFFFFFFF80h; Resource
0x14001bf1a  call    cs:__imp_ExReleaseResourceLite
0x14001bf21  nop     dword ptr [rax+rax+00h]
0x14001bf26  nop
0x14001bf27  add     rsp, 20h
0x14001bf2b  pop     rbp
0x14001bf2c  retn
```
