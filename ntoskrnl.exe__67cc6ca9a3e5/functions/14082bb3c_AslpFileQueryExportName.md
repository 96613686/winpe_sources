# AslpFileQueryExportName

- ea: `0x14082bb3c`
- end: `0x14082be6b`
- name: `AslpFileQueryExportName`
- size: `815`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x140829abc`

## callees

- `0x1404058e0`
- `0x14044a490`
- `0x140519f7c`
- `0x1406cba8c`
- `0x1406cbad4`
- `0x14071dd6c`
- `0x140720384`
- `0x14073044c`
- `0x140733698`
- `0x140733ca0`
- `0x14082a02c`
- `0x14082bb3c`
- `0x14082c0d4`
- `0x14097d158`

## string_xrefs

- `0x14082bbbd`: `AslpFileGetImageNtHeader failed [%x]`
- `0x14082bce1`: `Export directory invalid or invalid image format`
- `0x14082bdec`: `RtlStringCchCopyA failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileQueryExportName(char *a1, __int64 a2)
{
  __int64 v4; // rdx
  int ImageNtHeader; // ebx
  const char *v6; // r9
  int v7; // r8d
  __int64 v8; // rbx
  const char *v9; // r9
  int v10; // r8d
  int v11; // ecx
  char IsUserAddress; // si
  __int16 UShortFromUser; // ax
  unsigned int *v14; // rax
  unsigned int *v15; // r15
  __int64 ULongFromUser; // r15
  __int64 v17; // r11
  void *v18; // r14
  const char *v19; // r9
  int v20; // r8d
  int v21; // ecx
  __int64 v22; // rax
  size_t v23; // rbx
  char *v24; // rsi
  __int64 v26; // [rsp+40h] [rbp-78h] BYREF
  __int64 v27; // [rsp+48h] [rbp-70h]
  __int64 v28; // [rsp+50h] [rbp-68h] BYREF
  __int64 v29; // [rsp+58h] [rbp-60h]
  __int128 v30; // [rsp+60h] [rbp-58h] BYREF
  void *v31; // [rsp+70h] [rbp-48h] BYREF
  __int64 v32; // [rsp+78h] [rbp-40h]
  __int64 v33; // [rsp+C0h] [rbp+8h] BYREF

  v30 = 0;
  v33 = 0;
  AslpMemorySpanInitViewFromFileMapping(&v30);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v31 = 0;
  v32 = 0;
  *a1 = 0;
  ImageNtHeader = AslpFileGetImageNtHeader(&v33, v4);
  if ( ImageNtHeader >= 0 )
  {
    v8 = v33;
    v26 = v33;
    v27 = 264;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v26, &v30) )
    {
      v9 = "Image too small to be a valid PE";
      v10 = 4351;
      v11 = 1;
LABEL_6:
      AslLogCallPrintf(v11, (unsigned int)"AslpFileQueryExportName", v10, (_DWORD)v9);
      return (unsigned int)-1073741701;
    }
    IsUserAddress = MmIsUserAddress(v8);
    if ( IsUserAddress )
      UShortFromUser = RtlReadUShortFromUser(v8 + 24);
    else
      UShortFromUser = *(_WORD *)(v8 + 24);
    if ( UShortFromUser == 267 )
    {
      v14 = (unsigned int *)(v8 + 120);
    }
    else
    {
      if ( UShortFromUser != 523 )
      {
        AslLogCallPrintf(
          2,
          (unsigned int)"AslpFileQueryExportName",
          4383,
          (unsigned int)"Unknown image optional header magic value %x");
        return (unsigned int)-1073741637;
      }
      v14 = (unsigned int *)(v8 + 136);
    }
    v15 = v14 + 1;
    if ( IsUserAddress )
    {
      RtlReadULongFromUser(v14);
      ULongFromUser = (unsigned int)RtlReadULongFromUser(v15);
    }
    else
    {
      ULongFromUser = *v15;
    }
    v28 = AslpImageRvaToVa(v8, a2);
    v29 = ULongFromUser;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v28, &v30) )
    {
      if ( !ULongFromUser && !v17 )
        return (unsigned int)-1073741275;
      v9 = "Export directory invalid or invalid image format";
      v10 = 4405;
      v11 = 2;
      goto LABEL_6;
    }
    if ( IsUserAddress )
      RtlReadULongFromUser((unsigned int *)(v17 + 12));
    v18 = (void *)AslpImageRvaToVa(v8, a2);
    v31 = v18;
    v32 = 256;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v31, &v30) )
    {
      ImageNtHeader = -1073741701;
      v19 = "Export name pointer out of bounds or invalid image format";
      v20 = 4431;
      v21 = 2;
LABEL_26:
      AslLogCallPrintf(v21, (unsigned int)"AslpFileQueryExportName", v20, (_DWORD)v19);
      return (unsigned int)ImageNtHeader;
    }
    if ( IsUserAddress )
    {
      v22 = RtlStringLengthFromUser(v18);
      v23 = v22;
      if ( (unsigned __int64)(v22 + 1) > 0x100 )
      {
        ImageNtHeader = -2147483643;
        v19 = "Export name too long";
        v20 = 4440;
        v21 = 1;
        goto LABEL_26;
      }
      v24 = &a1[v22];
      if ( (unsigned __int8)MmIsUserAddress(a1) )
      {
        RtlCopyToUserFromUser(a1, v18, v23);
        RtlWriteUCharToUser(v24, 0);
      }
      else
      {
        RtlCopyFromUser(a1, v18, v23);
        *v24 = 0;
      }
    }
    else
    {
      ImageNtHeader = RtlStringCchCopyA(a1, 0x100u, (NTSTRSAFE_PCSTR)v18);
      if ( ImageNtHeader < 0 )
      {
        v6 = "RtlStringCchCopyA failed [%x]";
        v7 = 4457;
        goto LABEL_3;
      }
    }
    return 0;
  }
  v6 = "AslpFileGetImageNtHeader failed [%x]";
  v7 = 4340;
LABEL_3:
  AslLogCallPrintf(1, (unsigned int)"AslpFileQueryExportName", v7, (_DWORD)v6);
  return (unsigned int)ImageNtHeader;
}

```

## disassembly

```asm
0x14082bb3c  mov     rax, rsp
0x14082bb3f  push    rbx
0x14082bb40  push    rsi
0x14082bb41  push    rdi
0x14082bb42  push    r12
0x14082bb44  push    r14
0x14082bb46  push    r15
0x14082bb48  sub     rsp, 88h
0x14082bb4f  mov     r14, rdx
0x14082bb52  mov     rdi, rcx
0x14082bb55  xorps   xmm0, xmm0
0x14082bb58  movups  xmmword ptr [rax-58h], xmm0
0x14082bb5c  mov     qword ptr [rax+8], 0
0x14082bb64  lea     rcx, [rax-58h]
0x14082bb68  call    AslpMemorySpanInitViewFromFileMapping
0x14082bb6d  mov     [rsp+0B8h+var_78], 0
0x14082bb76  mov     [rsp+0B8h+var_70], 0
0x14082bb7f  mov     [rsp+0B8h+var_68], 0
0x14082bb88  mov     [rsp+0B8h+var_60], 0
0x14082bb91  mov     [rsp+0B8h+var_48], 0
0x14082bb9a  mov     [rsp+0B8h+var_40], 0
0x14082bba3  mov     byte ptr [rdi], 0
0x14082bba6  lea     rcx, [rsp+0B8h+arg_0]
0x14082bbae  call    AslpFileGetImageNtHeader
0x14082bbb3  mov     ebx, eax
0x14082bbb5  mov     [rsp+0B8h+var_88], eax
0x14082bbb9  test    eax, eax
0x14082bbbb  jns     short loc_14082BBE4
0x14082bbbd  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x14082bbc4  mov     r8d, 10F4h
0x14082bbca  mov     [rsp+0B8h+var_98], eax
0x14082bbce  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082bbd5  mov     ecx, 1
0x14082bbda  call    AslLogCallPrintf
0x14082bbdf  jmp     loc_14082BE2C
0x14082bbe4  mov     rbx, [rsp+0B8h+arg_0]
0x14082bbec  mov     [rsp+0B8h+var_78], rbx
0x14082bbf1  mov     [rsp+0B8h+var_70], 108h
0x14082bbfa  lea     rdx, [rsp+0B8h+var_58]
0x14082bbff  lea     rcx, [rsp+0B8h+var_78]
0x14082bc04  call    AslpMemorySpanCheckBounds
0x14082bc09  test    al, al
0x14082bc0b  jnz     short loc_14082BC35
0x14082bc0d  lea     r9, aImageTooSmallT; "Image too small to be a valid PE"
0x14082bc14  mov     r8d, 10FFh
0x14082bc1a  mov     ecx, 1
0x14082bc1f  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082bc26  call    AslLogCallPrintf
0x14082bc2b  mov     ebx, 0C000007Bh
0x14082bc30  jmp     loc_14082BE28
0x14082bc35  mov     rcx, rbx
0x14082bc38  call    MmIsUserAddress
0x14082bc3d  mov     sil, al
0x14082bc40  test    al, al
0x14082bc42  jz      short loc_14082BC4F
0x14082bc44  lea     rcx, [rbx+18h]
0x14082bc48  call    RtlReadUShortFromUser
0x14082bc4d  jmp     short loc_14082BC53
0x14082bc4f  movzx   eax, word ptr [rbx+18h]
0x14082bc53  mov     ecx, 10Bh
0x14082bc58  cmp     ax, cx
0x14082bc5b  jnz     short loc_14082BC63
0x14082bc5d  lea     rax, [rbx+78h]
0x14082bc61  jmp     short loc_14082BC78
0x14082bc63  mov     ecx, 20Bh
0x14082bc68  cmp     ax, cx
0x14082bc6b  jnz     loc_14082BDFE
0x14082bc71  lea     rax, [rbx+88h]
0x14082bc78  lea     r15, [rax+4]
0x14082bc7c  test    sil, sil
0x14082bc7f  jz      short loc_14082BC99
0x14082bc81  mov     rcx, rax
0x14082bc84  call    RtlReadULongFromUser
0x14082bc89  mov     r12d, eax
0x14082bc8c  mov     rcx, r15
0x14082bc8f  call    RtlReadULongFromUser
0x14082bc94  mov     r15d, eax
0x14082bc97  jmp     short loc_14082BC9F
0x14082bc99  mov     r12d, [rax]
0x14082bc9c  mov     r15d, [r15]
0x14082bc9f  mov     r8d, r12d
0x14082bca2  mov     rdx, r14
0x14082bca5  mov     rcx, rbx
0x14082bca8  call    AslpImageRvaToVa
0x14082bcad  mov     r11, rax
0x14082bcb0  mov     [rsp+0B8h+var_68], rax
0x14082bcb5  mov     [rsp+0B8h+var_60], r15
0x14082bcba  lea     rdx, [rsp+0B8h+var_58]
0x14082bcbf  lea     rcx, [rsp+0B8h+var_68]
0x14082bcc4  call    AslpMemorySpanCheckBounds
0x14082bcc9  test    al, al
0x14082bccb  jnz     short loc_14082BCF8
0x14082bccd  test    r15, r15
0x14082bcd0  jnz     short loc_14082BCE1
0x14082bcd2  test    r11, r11
0x14082bcd5  jnz     short loc_14082BCE1
0x14082bcd7  mov     ebx, 0C0000225h
0x14082bcdc  jmp     loc_14082BE28
0x14082bce1  lea     r9, aExportDirector; "Export directory invalid or invalid ima"...
0x14082bce8  mov     r8d, 1135h
0x14082bcee  mov     ecx, 2
0x14082bcf3  jmp     loc_14082BC1F
0x14082bcf8  test    sil, sil
0x14082bcfb  jz      short loc_14082BD08
0x14082bcfd  lea     rcx, [r11+0Ch]
0x14082bd01  call    RtlReadULongFromUser
0x14082bd06  jmp     short loc_14082BD0C
0x14082bd08  mov     eax, [r11+0Ch]
0x14082bd0c  mov     r8d, eax
0x14082bd0f  mov     rdx, r14
0x14082bd12  mov     rcx, rbx
0x14082bd15  call    AslpImageRvaToVa
0x14082bd1a  mov     r14, rax
0x14082bd1d  mov     [rsp+0B8h+var_48], rax
0x14082bd22  mov     r15d, 100h
0x14082bd28  mov     [rsp+0B8h+var_40], r15
0x14082bd2d  lea     rdx, [rsp+0B8h+var_58]
0x14082bd32  lea     rcx, [rsp+0B8h+var_48]
0x14082bd37  call    AslpMemorySpanCheckBounds
0x14082bd3c  test    al, al
0x14082bd3e  jnz     short loc_14082BD6C
0x14082bd40  mov     ebx, 0C000007Bh
0x14082bd45  lea     r9, aExportNamePoin; "Export name pointer out of bounds or in"...
0x14082bd4c  mov     r8d, 114Fh
0x14082bd52  mov     ecx, 2
0x14082bd57  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082bd5e  mov     [rsp+0B8h+var_88], ebx
0x14082bd62  call    AslLogCallPrintf
0x14082bd67  jmp     loc_14082BE2C
0x14082bd6c  test    sil, sil
0x14082bd6f  jz      short loc_14082BDD4
0x14082bd71  mov     rcx, r14
0x14082bd74  call    RtlStringLengthFromUser
0x14082bd79  mov     rbx, rax
0x14082bd7c  lea     rcx, [rax+1]
0x14082bd80  cmp     rcx, r15
0x14082bd83  jbe     short loc_14082BD9E
0x14082bd85  mov     ebx, 80000005h
0x14082bd8a  lea     r9, aExportNameTooL; "Export name too long"
0x14082bd91  mov     r8d, 1158h
0x14082bd97  mov     ecx, 1
0x14082bd9c  jmp     short loc_14082BD57
0x14082bd9e  lea     rsi, [rax+rdi]
0x14082bda2  mov     rcx, rdi
0x14082bda5  call    MmIsUserAddress
0x14082bdaa  mov     r8, rbx; Size
0x14082bdad  mov     rdx, r14; Src
0x14082bdb0  mov     rcx, rdi; void *
0x14082bdb3  test    al, al
0x14082bdb5  jz      short loc_14082BDCA
0x14082bdb7  call    RtlCopyToUserFromUser
0x14082bdbc  xor     edx, edx
0x14082bdbe  mov     rcx, rsi
0x14082bdc1  call    RtlWriteUCharToUser
0x14082bdc6  xor     ebx, ebx
0x14082bdc8  jmp     short loc_14082BE28
0x14082bdca  call    RtlCopyFromUser
0x14082bdcf  mov     byte ptr [rsi], 0
0x14082bdd2  jmp     short loc_14082BDC6
0x14082bdd4  mov     r8, r14; pszSrc
0x14082bdd7  mov     rdx, r15; cchDest
0x14082bdda  mov     rcx, rdi; pszDest
0x14082bddd  call    RtlStringCchCopyA
0x14082bde2  mov     ebx, eax
0x14082bde4  mov     [rsp+0B8h+var_88], eax
0x14082bde8  test    eax, eax
0x14082bdea  jns     short loc_14082BDC6
0x14082bdec  lea     r9, aRtlstringcchco_1; "RtlStringCchCopyA failed [%x]"
0x14082bdf3  mov     r8d, 1169h
0x14082bdf9  jmp     loc_14082BBCA
0x14082bdfe  movzx   eax, ax
0x14082be01  mov     [rsp+0B8h+var_98], eax
0x14082be05  lea     r9, aUnknownImageOp; "Unknown image optional header magic val"...
0x14082be0c  mov     r8d, 111Fh
0x14082be12  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082be19  mov     ecx, 2
0x14082be1e  call    AslLogCallPrintf
0x14082be23  mov     ebx, 0C00000BBh
0x14082be28  mov     [rsp+0B8h+var_88], ebx
0x14082be2c  jmp     short loc_14082BE57
0x14082be2e  mov     ebx, eax
0x14082be30  mov     [rsp+0B8h+var_88], eax
0x14082be34  mov     [rsp+0B8h+var_98], eax
0x14082be38  lea     r9, aExceptionEncou_0; "Exception encountered [%x]"
0x14082be3f  mov     r8d, 1172h
0x14082be45  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082be4c  mov     ecx, 1
0x14082be51  call    AslLogCallPrintf
0x14082be56  nop
0x14082be57  mov     eax, ebx
0x14082be59  add     rsp, 88h
0x14082be60  pop     r15
0x14082be62  pop     r14
0x14082be64  pop     r12
0x14082be66  pop     rdi
0x14082be67  pop     rsi
0x14082be68  pop     rbx
0x14082be69  retn
0x140b4a7ed  push    rbp
0x140b4a7ef  sub     rsp, 30h
0x140b4a7f3  mov     rbp, rdx
0x140b4a7f6  mov     eax, 1
0x140b4a7fb  add     rsp, 30h
0x140b4a7ff  pop     rbp
0x140b4a800  retn
```
