# AslpFileQueryExportName

- ea: `0x14082daac`
- end: `0x14082dddb`
- name: `AslpFileQueryExportName`
- size: `815`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x14082ba2c`

## callees

- `0x14041a320`
- `0x14045ef10`
- `0x14052039c`
- `0x1406ce6ec`
- `0x1406ce734`
- `0x140724374`
- `0x14072f65c`
- `0x140734c10`
- `0x140737e58`
- `0x140738460`
- `0x14082bf9c`
- `0x14082daac`
- `0x14082e044`
- `0x1408c2f88`

## string_xrefs

- `0x14082db2d`: `AslpFileGetImageNtHeader failed [%x]`
- `0x14082dd5c`: `RtlStringCchCopyA failed [%x]`
- `0x14082dc51`: `Export directory invalid or invalid image format`

## pseudocode

```c
__int64 __fastcall AslpFileQueryExportName(char *a1, __int64 a2)
{
  __int64 v4; // rdx
  int ImageNtHeader; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  int v8; // r8d
  __int64 v9; // rbx
  char IsUserAddress; // si
  unsigned __int16 UShortFromUser; // ax
  __int64 v12; // rax
  unsigned int *v13; // r15
  __int64 ULongFromUser; // r15
  __int64 v15; // r11
  void *v16; // r14
  const char *v17; // r9
  int v18; // r8d
  int v19; // ecx
  __int64 v20; // rax
  size_t v21; // rbx
  char *v22; // rsi
  __int64 v24; // [rsp+40h] [rbp-78h] BYREF
  __int64 v25; // [rsp+48h] [rbp-70h]
  __int64 v26; // [rsp+50h] [rbp-68h] BYREF
  __int64 v27; // [rsp+58h] [rbp-60h]
  __int128 v28; // [rsp+60h] [rbp-58h] BYREF
  void *v29; // [rsp+70h] [rbp-48h] BYREF
  __int64 v30; // [rsp+78h] [rbp-40h]
  __int64 v31; // [rsp+C0h] [rbp+8h] BYREF

  v28 = 0;
  v31 = 0;
  AslpMemorySpanInitViewFromFileMapping(&v28);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  *a1 = 0;
  ImageNtHeader = AslpFileGetImageNtHeader(&v31, v4);
  v6 = ImageNtHeader;
  if ( ImageNtHeader >= 0 )
  {
    v9 = v31;
    v24 = v31;
    v25 = 264;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v24, &v28) )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslpFileQueryExportName",
        4351,
        (unsigned int)"Image too small to be a valid PE");
      return (unsigned int)-1073741701;
    }
    IsUserAddress = MmIsUserAddress(v9);
    if ( IsUserAddress )
      UShortFromUser = RtlReadUShortFromUser(v9 + 24);
    else
      UShortFromUser = *(_WORD *)(v9 + 24);
    if ( UShortFromUser == 267 )
    {
      v12 = v9 + 120;
    }
    else
    {
      if ( UShortFromUser != 523 )
      {
        AslLogCallPrintf(
          2,
          (unsigned int)"AslpFileQueryExportName",
          4383,
          (unsigned int)"Unknown image optional header magic value %x",
          UShortFromUser);
        return (unsigned int)-1073741637;
      }
      v12 = v9 + 136;
    }
    v13 = (unsigned int *)(v12 + 4);
    if ( IsUserAddress )
    {
      RtlReadULongFromUser(v12);
      ULongFromUser = (unsigned int)RtlReadULongFromUser(v13);
    }
    else
    {
      ULongFromUser = *v13;
    }
    v26 = AslpImageRvaToVa(v9, a2);
    v27 = ULongFromUser;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v26, &v28) )
    {
      if ( !ULongFromUser && !v15 )
        return (unsigned int)-1073741275;
      AslLogCallPrintf(
        2,
        (unsigned int)"AslpFileQueryExportName",
        4405,
        (unsigned int)"Export directory invalid or invalid image format");
      return (unsigned int)-1073741701;
    }
    if ( IsUserAddress )
      RtlReadULongFromUser(v15 + 12);
    v16 = (void *)AslpImageRvaToVa(v9, a2);
    v29 = v16;
    v30 = 256;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v29, &v28) )
    {
      v6 = -1073741701;
      v17 = "Export name pointer out of bounds or invalid image format";
      v18 = 4431;
      v19 = 2;
LABEL_26:
      AslLogCallPrintf(v19, (unsigned int)"AslpFileQueryExportName", v18, (_DWORD)v17);
      return v6;
    }
    if ( IsUserAddress )
    {
      v20 = RtlStringLengthFromUser(v16);
      v21 = v20;
      if ( (unsigned __int64)(v20 + 1) > 0x100 )
      {
        v6 = -2147483643;
        v17 = "Export name too long";
        v18 = 4440;
        v19 = 1;
        goto LABEL_26;
      }
      v22 = &a1[v20];
      if ( (unsigned __int8)MmIsUserAddress(a1) )
      {
        RtlCopyToUserFromUser(a1, v16, v21);
        RtlWriteUCharToUser(v22, 0);
      }
      else
      {
        RtlCopyFromUser(a1, v16, v21);
        *v22 = 0;
      }
    }
    else
    {
      ImageNtHeader = RtlStringCchCopyA(a1, 0x100u, (NTSTRSAFE_PCSTR)v16);
      v6 = ImageNtHeader;
      if ( ImageNtHeader < 0 )
      {
        v7 = "RtlStringCchCopyA failed [%x]";
        v8 = 4457;
        goto LABEL_3;
      }
    }
    return 0;
  }
  v7 = "AslpFileGetImageNtHeader failed [%x]";
  v8 = 4340;
LABEL_3:
  AslLogCallPrintf(1, (unsigned int)"AslpFileQueryExportName", v8, (_DWORD)v7, ImageNtHeader);
  return v6;
}

```

## disassembly

```asm
0x14082daac  mov     rax, rsp
0x14082daaf  push    rbx
0x14082dab0  push    rsi
0x14082dab1  push    rdi
0x14082dab2  push    r12
0x14082dab4  push    r14
0x14082dab6  push    r15
0x14082dab8  sub     rsp, 88h
0x14082dabf  mov     r14, rdx
0x14082dac2  mov     rdi, rcx
0x14082dac5  xorps   xmm0, xmm0
0x14082dac8  movups  xmmword ptr [rax-58h], xmm0
0x14082dacc  mov     qword ptr [rax+8], 0
0x14082dad4  lea     rcx, [rax-58h]
0x14082dad8  call    AslpMemorySpanInitViewFromFileMapping
0x14082dadd  mov     [rsp+0B8h+var_78], 0
0x14082dae6  mov     [rsp+0B8h+var_70], 0
0x14082daef  mov     [rsp+0B8h+var_68], 0
0x14082daf8  mov     [rsp+0B8h+var_60], 0
0x14082db01  mov     [rsp+0B8h+var_48], 0
0x14082db0a  mov     [rsp+0B8h+var_40], 0
0x14082db13  mov     byte ptr [rdi], 0
0x14082db16  lea     rcx, [rsp+0B8h+arg_0]
0x14082db1e  call    AslpFileGetImageNtHeader
0x14082db23  mov     ebx, eax
0x14082db25  mov     [rsp+0B8h+var_88], eax
0x14082db29  test    eax, eax
0x14082db2b  jns     short loc_14082DB54
0x14082db2d  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x14082db34  mov     r8d, 10F4h
0x14082db3a  mov     [rsp+0B8h+var_98], eax
0x14082db3e  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082db45  mov     ecx, 1
0x14082db4a  call    AslLogCallPrintf
0x14082db4f  jmp     loc_14082DD9C
0x14082db54  mov     rbx, [rsp+0B8h+arg_0]
0x14082db5c  mov     [rsp+0B8h+var_78], rbx
0x14082db61  mov     [rsp+0B8h+var_70], 108h
0x14082db6a  lea     rdx, [rsp+0B8h+var_58]
0x14082db6f  lea     rcx, [rsp+0B8h+var_78]
0x14082db74  call    AslpMemorySpanCheckBounds
0x14082db79  test    al, al
0x14082db7b  jnz     short loc_14082DBA5
0x14082db7d  lea     r9, aImageTooSmallT; "Image too small to be a valid PE"
0x14082db84  mov     r8d, 10FFh
0x14082db8a  mov     ecx, 1
0x14082db8f  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082db96  call    AslLogCallPrintf
0x14082db9b  mov     ebx, 0C000007Bh
0x14082dba0  jmp     loc_14082DD98
0x14082dba5  mov     rcx, rbx
0x14082dba8  call    MmIsUserAddress
0x14082dbad  mov     sil, al
0x14082dbb0  test    al, al
0x14082dbb2  jz      short loc_14082DBBF
0x14082dbb4  lea     rcx, [rbx+18h]
0x14082dbb8  call    RtlReadUShortFromUser
0x14082dbbd  jmp     short loc_14082DBC3
0x14082dbbf  movzx   eax, word ptr [rbx+18h]
0x14082dbc3  mov     ecx, 10Bh
0x14082dbc8  cmp     ax, cx
0x14082dbcb  jnz     short loc_14082DBD3
0x14082dbcd  lea     rax, [rbx+78h]
0x14082dbd1  jmp     short loc_14082DBE8
0x14082dbd3  mov     ecx, 20Bh
0x14082dbd8  cmp     ax, cx
0x14082dbdb  jnz     loc_14082DD6E
0x14082dbe1  lea     rax, [rbx+88h]
0x14082dbe8  lea     r15, [rax+4]
0x14082dbec  test    sil, sil
0x14082dbef  jz      short loc_14082DC09
0x14082dbf1  mov     rcx, rax
0x14082dbf4  call    RtlReadULongFromUser
0x14082dbf9  mov     r12d, eax
0x14082dbfc  mov     rcx, r15
0x14082dbff  call    RtlReadULongFromUser
0x14082dc04  mov     r15d, eax
0x14082dc07  jmp     short loc_14082DC0F
0x14082dc09  mov     r12d, [rax]
0x14082dc0c  mov     r15d, [r15]
0x14082dc0f  mov     r8d, r12d
0x14082dc12  mov     rdx, r14
0x14082dc15  mov     rcx, rbx
0x14082dc18  call    AslpImageRvaToVa
0x14082dc1d  mov     r11, rax
0x14082dc20  mov     [rsp+0B8h+var_68], rax
0x14082dc25  mov     [rsp+0B8h+var_60], r15
0x14082dc2a  lea     rdx, [rsp+0B8h+var_58]
0x14082dc2f  lea     rcx, [rsp+0B8h+var_68]
0x14082dc34  call    AslpMemorySpanCheckBounds
0x14082dc39  test    al, al
0x14082dc3b  jnz     short loc_14082DC68
0x14082dc3d  test    r15, r15
0x14082dc40  jnz     short loc_14082DC51
0x14082dc42  test    r11, r11
0x14082dc45  jnz     short loc_14082DC51
0x14082dc47  mov     ebx, 0C0000225h
0x14082dc4c  jmp     loc_14082DD98
0x14082dc51  lea     r9, aExportDirector; "Export directory invalid or invalid ima"...
0x14082dc58  mov     r8d, 1135h
0x14082dc5e  mov     ecx, 2
0x14082dc63  jmp     loc_14082DB8F
0x14082dc68  test    sil, sil
0x14082dc6b  jz      short loc_14082DC78
0x14082dc6d  lea     rcx, [r11+0Ch]
0x14082dc71  call    RtlReadULongFromUser
0x14082dc76  jmp     short loc_14082DC7C
0x14082dc78  mov     eax, [r11+0Ch]
0x14082dc7c  mov     r8d, eax
0x14082dc7f  mov     rdx, r14
0x14082dc82  mov     rcx, rbx
0x14082dc85  call    AslpImageRvaToVa
0x14082dc8a  mov     r14, rax
0x14082dc8d  mov     [rsp+0B8h+var_48], rax
0x14082dc92  mov     r15d, 100h
0x14082dc98  mov     [rsp+0B8h+var_40], r15
0x14082dc9d  lea     rdx, [rsp+0B8h+var_58]
0x14082dca2  lea     rcx, [rsp+0B8h+var_48]
0x14082dca7  call    AslpMemorySpanCheckBounds
0x14082dcac  test    al, al
0x14082dcae  jnz     short loc_14082DCDC
0x14082dcb0  mov     ebx, 0C000007Bh
0x14082dcb5  lea     r9, aExportNamePoin; "Export name pointer out of bounds or in"...
0x14082dcbc  mov     r8d, 114Fh
0x14082dcc2  mov     ecx, 2
0x14082dcc7  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082dcce  mov     [rsp+0B8h+var_88], ebx
0x14082dcd2  call    AslLogCallPrintf
0x14082dcd7  jmp     loc_14082DD9C
0x14082dcdc  test    sil, sil
0x14082dcdf  jz      short loc_14082DD44
0x14082dce1  mov     rcx, r14
0x14082dce4  call    RtlStringLengthFromUser
0x14082dce9  mov     rbx, rax
0x14082dcec  lea     rcx, [rax+1]
0x14082dcf0  cmp     rcx, r15
0x14082dcf3  jbe     short loc_14082DD0E
0x14082dcf5  mov     ebx, 80000005h
0x14082dcfa  lea     r9, aExportNameTooL; "Export name too long"
0x14082dd01  mov     r8d, 1158h
0x14082dd07  mov     ecx, 1
0x14082dd0c  jmp     short loc_14082DCC7
0x14082dd0e  lea     rsi, [rax+rdi]
0x14082dd12  mov     rcx, rdi
0x14082dd15  call    MmIsUserAddress
0x14082dd1a  mov     r8, rbx; Size
0x14082dd1d  mov     rdx, r14; Src
0x14082dd20  mov     rcx, rdi; void *
0x14082dd23  test    al, al
0x14082dd25  jz      short loc_14082DD3A
0x14082dd27  call    RtlCopyToUserFromUser
0x14082dd2c  xor     edx, edx
0x14082dd2e  mov     rcx, rsi
0x14082dd31  call    RtlWriteUCharToUser
0x14082dd36  xor     ebx, ebx
0x14082dd38  jmp     short loc_14082DD98
0x14082dd3a  call    RtlCopyFromUser
0x14082dd3f  mov     byte ptr [rsi], 0
0x14082dd42  jmp     short loc_14082DD36
0x14082dd44  mov     r8, r14; pszSrc
0x14082dd47  mov     rdx, r15; cchDest
0x14082dd4a  mov     rcx, rdi; pszDest
0x14082dd4d  call    RtlStringCchCopyA
0x14082dd52  mov     ebx, eax
0x14082dd54  mov     [rsp+0B8h+var_88], eax
0x14082dd58  test    eax, eax
0x14082dd5a  jns     short loc_14082DD36
0x14082dd5c  lea     r9, aRtlstringcchco_1; "RtlStringCchCopyA failed [%x]"
0x14082dd63  mov     r8d, 1169h
0x14082dd69  jmp     loc_14082DB3A
0x14082dd6e  movzx   eax, ax
0x14082dd71  mov     [rsp+0B8h+var_98], eax
0x14082dd75  lea     r9, aUnknownImageOp; "Unknown image optional header magic val"...
0x14082dd7c  mov     r8d, 111Fh
0x14082dd82  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082dd89  mov     ecx, 2
0x14082dd8e  call    AslLogCallPrintf
0x14082dd93  mov     ebx, 0C00000BBh
0x14082dd98  mov     [rsp+0B8h+var_88], ebx
0x14082dd9c  jmp     short loc_14082DDC7
0x14082dd9e  mov     ebx, eax
0x14082dda0  mov     [rsp+0B8h+var_88], eax
0x14082dda4  mov     [rsp+0B8h+var_98], eax
0x14082dda8  lea     r9, aExceptionEncou_0; "Exception encountered [%x]"
0x14082ddaf  mov     r8d, 1172h
0x14082ddb5  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14082ddbc  mov     ecx, 1
0x14082ddc1  call    AslLogCallPrintf
0x14082ddc6  nop
0x14082ddc7  mov     eax, ebx
0x14082ddc9  add     rsp, 88h
0x14082ddd0  pop     r15
0x14082ddd2  pop     r14
0x14082ddd4  pop     r12
0x14082ddd6  pop     rdi
0x14082ddd7  pop     rsi
0x14082ddd8  pop     rbx
0x14082ddd9  retn
0x140b4bf39  push    rbp
0x140b4bf3b  sub     rsp, 30h
0x140b4bf3f  mov     rbp, rdx
0x140b4bf42  mov     eax, 1
0x140b4bf47  add     rsp, 30h
0x140b4bf4b  pop     rbp
0x140b4bf4c  retn
```
