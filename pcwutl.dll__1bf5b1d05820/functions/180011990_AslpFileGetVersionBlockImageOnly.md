# AslpFileGetVersionBlockImageOnly

- ea: `0x180011990`
- end: `0x180011c65`
- name: `AslpFileGetVersionBlockImageOnly`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180010d10`

## callees

- `0x1800027e2`
- `0x18000dcf4`
- `0x18000e240`
- `0x1800108c4`
- `0x180011638`
- `0x180011990`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180011c4d`
- `ntdll!RtlFreeHeap` at `0x180011c4d`
- `ntdll!RtlAllocateHeap` at `0x180011b80`
- `ntdll!RtlAllocateHeap` at `0x180011b80`

## string_xrefs

- `0x180011a60`: `AslpFileGetImageResourceDirectoryRoot failed to get resource directory root [%x]`
- `0x180011abc`: `AslpFileGetVersionBlockFromResourceRoot failed to get version block from resource directory [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlockImageOnly(_QWORD *a1, unsigned __int16 **a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r8
  unsigned __int16 *v8; // rcx
  unsigned int v9; // ebx
  int v10; // eax
  unsigned __int64 v11; // rdx
  int ImageResourceDirectoryRoot; // eax
  const char *v13; // r9
  __int64 v14; // r8
  int VersionBlockFromResourceRoot; // eax
  SIZE_T v16; // r14
  void *v17; // r12
  unsigned __int64 v18; // rax
  char *v19; // rcx
  SIZE_T v20; // r8
  unsigned __int64 v21; // rdx
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v23; // rsi
  unsigned __int16 *v24; // rax
  void *Src; // [rsp+40h] [rbp-48h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+18h] BYREF
  SIZE_T Size; // [rsp+A8h] [rbp+20h] BYREF

  v28 = 0;
  Src = 0;
  Size = 0;
  v7 = *(_QWORD *)(a4 + 64);
  if ( v7 )
  {
    v8 = 0;
    if ( *(_WORD *)(v7 + 2) >= 0x34u )
      v8 = (unsigned __int16 *)(v7 + 40);
    *a2 = v8;
    *a1 = *(_QWORD *)(a4 + 64);
    return 0;
  }
  v10 = AslFileMappingEnsure(a4, a1, 0, a4);
  v9 = v10;
  if ( v10 < 0 )
  {
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", 2288, "AslFileMappingEnsure failed [%x]", v10);
    return v9;
  }
  if ( *(_DWORD *)(a4 + 56) != 6 )
    return (unsigned int)-1073741687;
  ImageResourceDirectoryRoot = AslpFileGetImageResourceDirectoryRoot((unsigned __int64 *)&v28, v11, a4);
  v9 = ImageResourceDirectoryRoot;
  if ( ImageResourceDirectoryRoot < 0 )
  {
    if ( (unsigned int)(ImageResourceDirectoryRoot + 1073741687) <= 2 )
      return v9;
    v13 = "AslpFileGetImageResourceDirectoryRoot failed to get resource directory root [%x]";
    v14 = 2315;
LABEL_12:
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", v14, v13, v9);
    return v9;
  }
  VersionBlockFromResourceRoot = AslpFileGetVersionBlockFromResourceRoot((unsigned __int16 **)&Src, &Size, v28, a4);
  v9 = VersionBlockFromResourceRoot;
  if ( VersionBlockFromResourceRoot < 0 )
  {
    if ( (unsigned int)(VersionBlockFromResourceRoot + 1073741687) <= 2 )
      return v9;
    v13 = "AslpFileGetVersionBlockFromResourceRoot failed to get version block from resource directory [%x]";
    v14 = 2323;
    goto LABEL_12;
  }
  v16 = Size;
  if ( !Size )
    return (unsigned int)-1073741687;
  v17 = Src;
  if ( !Src )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockImageOnly",
      2335,
      "AslpFileGetVersionBlockFromResourceRoot returned null version block with status [%x]",
      VersionBlockFromResourceRoot);
    return (unsigned int)-1073741687;
  }
  if ( Size > 0x7FFF )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockImageOnly",
      2341,
      "AslpFileGetVersionBlockFromResourceRoot returned version block size that is too large");
    return (unsigned int)-1073741687;
  }
  v18 = *(_QWORD *)(a4 + 32);
  if ( (unsigned __int64)Src < v18
    || (v19 = (char *)Src + Size, Src > (char *)Src + Size)
    || (v20 = *(_QWORD *)(a4 + 40), v21 = v20 + v18, (unsigned __int64)Src > v20 + v18)
    || (unsigned __int64)v19 < v18
    || (unsigned __int64)v19 > v21
    || v18 > v21
    || Size > v20 )
  {
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", 2350, "Version block out of range");
    return (unsigned int)-1073741687;
  }
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
  v23 = Heap;
  if ( Heap )
  {
    memmove_0(Heap, v17, v16);
    if ( v16 < *v23 )
      *v23 = v16;
    v24 = v23 + 20;
    if ( v23[1] < 0x34u )
      v24 = 0;
    *a2 = v24;
    *a1 = v23;
    *(_QWORD *)(a4 + 64) = v23;
    return 0;
  }
  else
  {
    return (unsigned int)-1073741801;
  }
}

```

## disassembly

```asm
0x180011990  mov     rax, rsp
0x180011993  mov     [rax+18h], r8
0x180011997  mov     [rax+8], rcx
0x18001199b  push    rbx
0x18001199c  push    rsi
0x18001199d  push    rdi
0x18001199e  push    r12
0x1800119a0  push    r13
0x1800119a2  push    r14
0x1800119a4  push    r15
0x1800119a6  sub     rsp, 50h
0x1800119aa  mov     r15, r9
0x1800119ad  mov     r13, rdx
0x1800119b0  mov     rdx, rcx
0x1800119b3  xor     edi, edi
0x1800119b5  mov     [rax+18h], rdi
0x1800119b9  mov     [rax-48h], rdi
0x1800119bd  mov     esi, edi
0x1800119bf  mov     [rax-50h], rdi
0x1800119c3  mov     [rax+20h], rdi
0x1800119c7  mov     r8, [r9+40h]
0x1800119cb  test    r8, r8
0x1800119ce  jz      short loc_1800119F2
0x1800119d0  lea     rax, [r8+28h]
0x1800119d4  mov     ecx, edi
0x1800119d6  cmp     word ptr [r8+2], 34h ; '4'
0x1800119dc  cmovnb  rcx, rax
0x1800119e0  mov     [r13+0], rcx
0x1800119e4  mov     rax, [r9+40h]
0x1800119e8  mov     [rdx], rax
0x1800119eb  mov     ebx, edi
0x1800119ed  jmp     loc_180011C36
0x1800119f2  mov     rcx, r15
0x1800119f5  call    AslFileMappingEnsure
0x1800119fa  mov     ebx, eax
0x1800119fc  test    eax, eax
0x1800119fe  jns     short loc_180011A27
0x180011a00  mov     [rsp+88h+var_68], eax
0x180011a04  lea     r9, aAslfilemapping_2; "AslFileMappingEnsure failed [%x]"
0x180011a0b  mov     r8d, 8F0h
0x180011a11  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x180011a18  mov     ecx, 1
0x180011a1d  call    AslLogCallPrintf
0x180011a22  jmp     loc_180011C36
0x180011a27  cmp     dword ptr [r15+38h], 6
0x180011a2c  jz      short loc_180011A38
0x180011a2e  mov     ebx, 0C0000089h
0x180011a33  jmp     loc_180011C36
0x180011a38  mov     r8, r15
0x180011a3b  lea     rcx, [rsp+88h+arg_10]
0x180011a43  call    AslpFileGetImageResourceDirectoryRoot
0x180011a48  mov     ebx, eax
0x180011a4a  mov     [rsp+88h+var_58], eax
0x180011a4e  test    eax, eax
0x180011a50  jns     short loc_180011A87
0x180011a52  add     eax, 3FFFFF77h
0x180011a57  cmp     eax, 2
0x180011a5a  jbe     loc_180011C07
0x180011a60  lea     r9, aAslpfilegetima; "AslpFileGetImageResourceDirectoryRoot f"...
0x180011a67  mov     r8d, 90Bh
0x180011a6d  mov     [rsp+88h+var_68], ebx
0x180011a71  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x180011a78  mov     ecx, 1
0x180011a7d  call    AslLogCallPrintf
0x180011a82  jmp     loc_180011C07
0x180011a87  mov     r9, r15
0x180011a8a  mov     r8, [rsp+88h+arg_10]
0x180011a92  lea     rdx, [rsp+88h+Size]
0x180011a9a  lea     rcx, [rsp+88h+Src]
0x180011a9f  call    AslpFileGetVersionBlockFromResourceRoot
0x180011aa4  mov     ebx, eax
0x180011aa6  mov     [rsp+88h+var_58], eax
0x180011aaa  test    eax, eax
0x180011aac  jns     short loc_180011ACB
0x180011aae  add     eax, 3FFFFF77h
0x180011ab3  cmp     eax, 2
0x180011ab6  jbe     loc_180011C07
0x180011abc  lea     r9, aAslpfilegetver_6; "AslpFileGetVersionBlockFromResourceRoot"...
0x180011ac3  mov     r8d, 913h
0x180011ac9  jmp     short loc_180011A6D
0x180011acb  mov     r14, [rsp+88h+Size]
0x180011ad3  test    r14, r14
0x180011ad6  jz      loc_180011BFE
0x180011adc  mov     r12, [rsp+88h+Src]
0x180011ae1  test    r12, r12
0x180011ae4  jnz     short loc_180011B0D
0x180011ae6  mov     [rsp+88h+var_68], ebx
0x180011aea  lea     r9, aAslpfilegetver; "AslpFileGetVersionBlockFromResourceRoot"...
0x180011af1  mov     r8d, 91Fh
0x180011af7  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x180011afe  lea     ecx, [r12+1]
0x180011b03  call    AslLogCallPrintf
0x180011b08  jmp     loc_180011BFE
0x180011b0d  cmp     r14, 7FFFh
0x180011b14  jbe     short loc_180011B28
0x180011b16  lea     r9, aAslpfilegetver_2; "AslpFileGetVersionBlockFromResourceRoot"...
0x180011b1d  mov     r8d, 925h
0x180011b23  jmp     loc_180011BED
0x180011b28  mov     rax, [r15+20h]
0x180011b2c  cmp     r12, rax
0x180011b2f  jb      loc_180011BE0
0x180011b35  lea     rcx, [r14+r12]
0x180011b39  cmp     r12, rcx
0x180011b3c  ja      loc_180011BE0
0x180011b42  mov     r8, [r15+28h]
0x180011b46  lea     rdx, [r8+rax]
0x180011b4a  cmp     r12, rdx
0x180011b4d  ja      loc_180011BE0
0x180011b53  cmp     rcx, rax
0x180011b56  jb      loc_180011BE0
0x180011b5c  cmp     rcx, rdx
0x180011b5f  ja      short loc_180011BE0
0x180011b61  cmp     rax, rdx
0x180011b64  ja      short loc_180011BE0
0x180011b66  cmp     r14, r8
0x180011b69  ja      short loc_180011BE0
0x180011b6b  mov     rcx, gs:60h
0x180011b74  mov     r8, r14; Size
0x180011b77  mov     edx, 8; Flags
0x180011b7c  mov     rcx, [rcx+30h]; HeapHandle
0x180011b80  call    cs:__imp_RtlAllocateHeap
0x180011b86  mov     rsi, rax
0x180011b89  mov     [rsp+88h+var_50], rax
0x180011b8e  test    rax, rax
0x180011b91  jnz     short loc_180011B9A
0x180011b93  mov     ebx, 0C0000017h
0x180011b98  jmp     short loc_180011C03
0x180011b9a  mov     r8, r14; Size
0x180011b9d  mov     rdx, r12; Src
0x180011ba0  mov     rcx, rsi; void *
0x180011ba3  call    memmove_0
0x180011ba8  movzx   eax, word ptr [rsi]
0x180011bab  cmp     r14, rax
0x180011bae  jnb     short loc_180011BB4
0x180011bb0  mov     [rsi], r14w
0x180011bb4  lea     rax, [rsi+28h]
0x180011bb8  cmp     word ptr [rsi+2], 34h ; '4'
0x180011bbd  cmovb   rax, rdi
0x180011bc1  mov     [r13+0], rax
0x180011bc5  mov     rax, [rsp+88h+arg_0]
0x180011bcd  mov     [rax], rsi
0x180011bd0  mov     [r15+40h], rsi
0x180011bd4  mov     rsi, rdi
0x180011bd7  mov     [rsp+88h+var_50], rdi
0x180011bdc  mov     ebx, edi
0x180011bde  jmp     short loc_180011C03
0x180011be0  lea     r9, aVersionBlockOu; "Version block out of range"
0x180011be7  mov     r8d, 92Eh
0x180011bed  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x180011bf4  mov     ecx, 1
0x180011bf9  call    AslLogCallPrintf
0x180011bfe  mov     ebx, 0C0000089h
0x180011c03  mov     [rsp+88h+var_58], ebx
0x180011c07  jmp     short loc_180011C36
0x180011c09  mov     ebx, eax
0x180011c0b  mov     [rsp+88h+var_58], eax
0x180011c0f  mov     [rsp+88h+var_68], eax
0x180011c13  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x180011c1a  mov     r8d, 966h
0x180011c20  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x180011c27  mov     ecx, 1
0x180011c2c  call    AslLogCallPrintf
0x180011c31  mov     rsi, [rsp+88h+var_50]
0x180011c36  test    rsi, rsi
0x180011c39  jz      short loc_180011C53
0x180011c3b  mov     rcx, gs:60h
0x180011c44  mov     r8, rsi; P
0x180011c47  xor     edx, edx; Flags
0x180011c49  mov     rcx, [rcx+30h]; HeapHandle
0x180011c4d  call    cs:__imp_RtlFreeHeap
0x180011c53  mov     eax, ebx
0x180011c55  add     rsp, 50h
0x180011c59  pop     r15
0x180011c5b  pop     r14
0x180011c5d  pop     r13
0x180011c5f  pop     r12
0x180011c61  pop     rdi
0x180011c62  pop     rsi
0x180011c63  pop     rbx
0x180011c64  retn
0x180019716  push    rbp
0x180019718  sub     rsp, 30h
0x18001971c  mov     rbp, rdx
0x18001971f  mov     rax, [rcx]
0x180019722  xor     ecx, ecx
0x180019724  cmp     dword ptr [rax], 0C00000FDh
0x18001972a  setnz   cl
0x18001972d  mov     [rbp+34h], ecx
0x180019730  mov     eax, [rbp+34h]
0x180019733  add     rsp, 30h
0x180019737  pop     rbp
0x180019738  retn
```
