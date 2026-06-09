# AslpFileQueryExportName

- ea: `0x180012c38`
- end: `0x180012f98`
- name: `AslpFileQueryExportName`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180010288`

## callees

- `0x18000e240`
- `0x1800107f8`
- `0x180012c38`
- `0x180013658`

## string_xrefs

- `0x180012c98`: `AslpFileGetImageNtHeader failed [%x]`
- `0x180012ee5`: `Export directory invalid or invalid image format`
- `0x180012e92`: `RtlStringCchCopyA failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileQueryExportName(_BYTE *a1, __int64 a2)
{
  _BYTE *v3; // rdi
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // r12
  int ImageNtHeader; // eax
  int v7; // ebx
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rdx
  _BYTE *v15; // rax
  __int64 v16; // rdx
  _BYTE *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rcx
  unsigned __int64 v21; // [rsp+D0h] [rbp+8h] BYREF

  v3 = a1;
  v21 = 0;
  if ( a2 && (v4 = *(_QWORD *)(a2 + 32)) != 0 )
  {
    v5 = *(_QWORD *)(a2 + 40);
  }
  else
  {
    v4 = 0;
    v5 = 0;
  }
  *a1 = 0;
  ImageNtHeader = AslpFileGetImageNtHeader(&v21, a2);
  v7 = ImageNtHeader;
  if ( ImageNtHeader < 0 )
  {
    AslLogCallPrintf(1, "AslpFileQueryExportName", 4340, "AslpFileGetImageNtHeader failed [%x]", ImageNtHeader);
    return (unsigned int)v7;
  }
  v8 = v21;
  if ( v21 < v4
    || (v9 = v21 + 264, v21 >= v21 + 264)
    || (v10 = v5 + v4, v21 > v5 + v4)
    || v9 < v4
    || v9 > v10
    || v4 > v10
    || v5 < 0x108 )
  {
    AslLogCallPrintf(1, "AslpFileQueryExportName", 4351, "Image too small to be a valid PE");
    return (unsigned int)-1073741701;
  }
  if ( *(_WORD *)(v21 + 24) == 267 )
  {
    v11 = v21 + 120;
  }
  else
  {
    if ( *(_WORD *)(v21 + 24) != 523 )
    {
      AslLogCallPrintf(
        2,
        "AslpFileQueryExportName",
        4383,
        "Unknown image optional header magic value %x",
        *(unsigned __int16 *)(v21 + 24));
      return (unsigned int)-1073741637;
    }
    v11 = v21 + 136;
  }
  v12 = *(unsigned int *)(v11 + 4);
  v13 = AslpImageRvaToVa(v21, a2);
  if ( v13 < v4 || (v14 = v12 + v13, v13 > v12 + v13) || v13 > v10 || v14 < v4 || v14 > v10 || v12 > v5 )
  {
    if ( !(_DWORD)v12 && !v13 )
      return (unsigned int)-1073741275;
    AslLogCallPrintf(2, "AslpFileQueryExportName", 4405, "Export directory invalid or invalid image format");
    return (unsigned int)-1073741701;
  }
  v15 = (_BYTE *)AslpImageRvaToVa(v8, a2);
  v16 = 256;
  if ( (unsigned __int64)v15 < v4
    || (v17 = v15 + 256, v15 >= v15 + 256)
    || (unsigned __int64)v15 > v10
    || (unsigned __int64)v17 < v4
    || (unsigned __int64)v17 > v10 )
  {
    v7 = -1073741701;
    AslLogCallPrintf(2, "AslpFileQueryExportName", 4431, "Export name pointer out of bounds or invalid image format");
  }
  else
  {
    v18 = 2147483646;
    v7 = 0;
    v19 = 0;
    while ( v16 )
    {
      if ( !v18 || !*v15 )
        goto LABEL_36;
      *v3++ = *v15++;
      --v16;
      --v18;
      ++v19;
    }
    --v3;
    v7 = -2147483643;
LABEL_36:
    *v3 = 0;
    if ( v7 >= 0 )
      return 0;
    else
      AslLogCallPrintf(1, "AslpFileQueryExportName", 4457, "RtlStringCchCopyA failed [%x]", v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012c38  mov     rax, rsp
0x180012c3b  mov     [rax+10h], rbx
0x180012c3f  mov     [rax+18h], rsi
0x180012c43  push    rdi
0x180012c44  push    r12
0x180012c46  push    r13
0x180012c48  push    r14
0x180012c4a  push    r15
0x180012c4c  sub     rsp, 0A0h
0x180012c53  mov     r13, rdx
0x180012c56  mov     rdi, rcx
0x180012c59  mov     qword ptr [rax+8], 0
0x180012c61  test    rdx, rdx
0x180012c64  jz      short loc_180012C75
0x180012c66  mov     rsi, [rdx+20h]
0x180012c6a  test    rsi, rsi
0x180012c6d  jz      short loc_180012C75
0x180012c6f  mov     r12, [rdx+28h]
0x180012c73  jmp     short loc_180012C7A
0x180012c75  xor     esi, esi
0x180012c77  xor     r12d, r12d
0x180012c7a  mov     byte ptr [rcx], 0
0x180012c7d  lea     rcx, [rsp+0C8h+arg_0]
0x180012c85  call    AslpFileGetImageNtHeader
0x180012c8a  mov     ebx, eax
0x180012c8c  mov     [rsp+0C8h+var_98], eax
0x180012c90  test    eax, eax
0x180012c92  jns     short loc_180012CBB
0x180012c94  mov     [rsp+0C8h+var_A8], eax
0x180012c98  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x180012c9f  mov     r8d, 10F4h
0x180012ca5  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x180012cac  mov     ecx, 1
0x180012cb1  call    AslLogCallPrintf
0x180012cb6  jmp     loc_180012F4E
0x180012cbb  mov     r14, [rsp+0C8h+arg_0]
0x180012cc3  mov     [rsp+0C8h+var_60], r14
0x180012cc8  mov     ecx, 108h
0x180012ccd  mov     [rsp+0C8h+var_58], rcx
0x180012cd2  cmp     r14, rsi
0x180012cd5  jb      loc_180012F27
0x180012cdb  lea     rax, [r14+108h]
0x180012ce2  cmp     r14, rax
0x180012ce5  ja      loc_180012F27
0x180012ceb  lea     r15, [r12+rsi]
0x180012cef  cmp     r14, r15
0x180012cf2  ja      loc_180012F27
0x180012cf8  cmp     rax, rsi
0x180012cfb  jb      loc_180012F27
0x180012d01  cmp     rax, r15
0x180012d04  ja      loc_180012F27
0x180012d0a  cmp     rsi, r15
0x180012d0d  ja      loc_180012F27
0x180012d13  cmp     r12, rcx
0x180012d16  jb      loc_180012F27
0x180012d1c  lea     eax, [rcx+3]
0x180012d1f  cmp     [r14+18h], ax
0x180012d24  jnz     short loc_180012D2C
0x180012d26  lea     r8, [r14+78h]
0x180012d2a  jmp     short loc_180012D43
0x180012d2c  mov     eax, 20Bh
0x180012d31  cmp     [r14+18h], ax
0x180012d36  jnz     loc_180012EF9
0x180012d3c  lea     r8, [r14+88h]
0x180012d43  mov     ebx, [r8+4]
0x180012d47  mov     r8d, [r8]
0x180012d4a  mov     rdx, r13
0x180012d4d  mov     rcx, r14
0x180012d50  call    AslpImageRvaToVa
0x180012d55  mov     [rsp+0C8h+var_50], rax
0x180012d5a  mov     [rsp+0C8h+var_48], rbx
0x180012d62  cmp     rax, rsi
0x180012d65  jb      loc_180012ED5
0x180012d6b  lea     rdx, [rbx+rax]
0x180012d6f  cmp     rax, rdx
0x180012d72  ja      loc_180012ED5
0x180012d78  cmp     rax, r15
0x180012d7b  ja      loc_180012ED5
0x180012d81  cmp     rdx, rsi
0x180012d84  jb      loc_180012ED5
0x180012d8a  cmp     rdx, r15
0x180012d8d  ja      loc_180012ED5
0x180012d93  cmp     rbx, r12
0x180012d96  ja      loc_180012ED5
0x180012d9c  mov     r8d, [rax+0Ch]
0x180012da0  mov     rdx, r13
0x180012da3  mov     rcx, r14
0x180012da6  call    AslpImageRvaToVa
0x180012dab  mov     [rsp+0C8h+var_40], rax
0x180012db3  mov     edx, 100h
0x180012db8  mov     [rsp+0C8h+var_38], rdx
0x180012dc0  cmp     rax, rsi
0x180012dc3  jb      loc_180012EAC
0x180012dc9  lea     rcx, [rax+100h]
0x180012dd0  cmp     rax, rcx
0x180012dd3  ja      loc_180012EAC
0x180012dd9  cmp     rax, r15
0x180012ddc  ja      loc_180012EAC
0x180012de2  cmp     rcx, rsi
0x180012de5  jb      loc_180012EAC
0x180012deb  cmp     rcx, r15
0x180012dee  ja      loc_180012EAC
0x180012df4  xor     r10d, r10d
0x180012df7  mov     [rsp+0C8h+var_94], r10d
0x180012dfc  mov     [rsp+0C8h+var_94], r10d
0x180012e01  mov     r8d, 7FFFFFFEh
0x180012e07  mov     [rsp+0C8h+var_68], r8
0x180012e0c  mov     [rsp+0C8h+var_78], rax
0x180012e11  mov     [rsp+0C8h+var_70], rdx
0x180012e16  mov     [rsp+0C8h+var_88], rdi
0x180012e1b  mov     ebx, r10d
0x180012e1e  mov     ecx, r10d
0x180012e21  mov     [rsp+0C8h+var_80], rcx
0x180012e26  test    rdx, rdx
0x180012e29  jz      short loc_180012E6A
0x180012e2b  test    r8, r8
0x180012e2e  jz      short loc_180012E65
0x180012e30  mov     r9b, [rax]
0x180012e33  test    r9b, r9b
0x180012e36  jz      short loc_180012E65
0x180012e38  mov     [rdi], r9b
0x180012e3b  inc     rdi
0x180012e3e  mov     [rsp+0C8h+var_88], rdi
0x180012e43  inc     rax
0x180012e46  mov     [rsp+0C8h+var_78], rax
0x180012e4b  dec     rdx
0x180012e4e  mov     [rsp+0C8h+var_70], rdx
0x180012e53  dec     r8
0x180012e56  mov     [rsp+0C8h+var_68], r8
0x180012e5b  inc     rcx
0x180012e5e  mov     [rsp+0C8h+var_80], rcx
0x180012e63  jmp     short loc_180012E26
0x180012e65  test    rdx, rdx
0x180012e68  jnz     short loc_180012E7F
0x180012e6a  dec     rdi
0x180012e6d  mov     [rsp+0C8h+var_88], rdi
0x180012e72  dec     rcx
0x180012e75  mov     [rsp+0C8h+var_80], rcx
0x180012e7a  mov     ebx, 80000005h
0x180012e7f  mov     [rdi], r10b
0x180012e82  mov     [rsp+0C8h+var_94], ebx
0x180012e86  mov     [rsp+0C8h+var_98], ebx
0x180012e8a  test    ebx, ebx
0x180012e8c  jns     short loc_180012EA4
0x180012e8e  mov     [rsp+0C8h+var_A8], ebx
0x180012e92  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyA failed [%x]"
0x180012e99  mov     r8d, 1169h
0x180012e9f  jmp     loc_180012CA5
0x180012ea4  mov     ebx, r10d
0x180012ea7  jmp     loc_180012F4A
0x180012eac  mov     ebx, 0C000007Bh
0x180012eb1  mov     [rsp+0C8h+var_98], ebx
0x180012eb5  lea     r9, aExportNamePoin; "Export name pointer out of bounds or in"...
0x180012ebc  mov     r8d, 114Fh
0x180012ec2  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x180012ec9  mov     ecx, 2
0x180012ece  call    AslLogCallPrintf
0x180012ed3  jmp     short loc_180012F4E
0x180012ed5  test    ebx, ebx
0x180012ed7  jnz     short loc_180012EE5
0x180012ed9  test    rax, rax
0x180012edc  jnz     short loc_180012EE5
0x180012ede  mov     ebx, 0C0000225h
0x180012ee3  jmp     short loc_180012F4A
0x180012ee5  lea     r9, aExportDirector; "Export directory invalid or invalid ima"...
0x180012eec  mov     r8d, 1135h
0x180012ef2  mov     ecx, 2
0x180012ef7  jmp     short loc_180012F39
0x180012ef9  movzx   eax, word ptr [r14+18h]
0x180012efe  mov     [rsp+0C8h+var_A8], eax
0x180012f02  lea     r9, aUnknownImageOp; "Unknown image optional header magic val"...
0x180012f09  mov     r8d, 111Fh
0x180012f0f  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x180012f16  mov     ecx, 2
0x180012f1b  call    AslLogCallPrintf
0x180012f20  mov     ebx, 0C00000BBh
0x180012f25  jmp     short loc_180012F4A
0x180012f27  lea     r9, aImageTooSmallT; "Image too small to be a valid PE"
0x180012f2e  mov     r8d, 10FFh
0x180012f34  mov     ecx, 1
0x180012f39  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x180012f40  call    AslLogCallPrintf
0x180012f45  mov     ebx, 0C000007Bh
0x180012f4a  mov     [rsp+0C8h+var_98], ebx
0x180012f4e  jmp     short loc_180012F79
0x180012f50  mov     ebx, eax
0x180012f52  mov     [rsp+0C8h+var_98], eax
0x180012f56  mov     [rsp+0C8h+var_A8], eax
0x180012f5a  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x180012f61  mov     r8d, 1172h
0x180012f67  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x180012f6e  mov     ecx, 1
0x180012f73  call    AslLogCallPrintf
0x180012f78  nop
0x180012f79  mov     eax, ebx
0x180012f7b  lea     r11, [rsp+0C8h+var_28]
0x180012f83  mov     rbx, [r11+38h]
0x180012f87  mov     rsi, [r11+40h]
0x180012f8b  mov     rsp, r11
0x180012f8e  pop     r15
0x180012f90  pop     r14
0x180012f92  pop     r13
0x180012f94  pop     r12
0x180012f96  pop     rdi
0x180012f97  retn
0x1800197be  push    rbp
0x1800197c0  sub     rsp, 30h
0x1800197c4  mov     rbp, rdx
0x1800197c7  mov     rax, [rcx]
0x1800197ca  xor     ecx, ecx
0x1800197cc  cmp     dword ptr [rax], 0C00000FDh
0x1800197d2  setnz   cl
0x1800197d5  mov     [rbp+38h], ecx
0x1800197d8  mov     eax, [rbp+38h]
0x1800197db  add     rsp, 30h
0x1800197df  pop     rbp
0x1800197e0  retn
```
