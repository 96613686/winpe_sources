# AslpFileQueryExportName

- ea: `0x14000f7ac`
- end: `0x14000fb0c`
- name: `AslpFileQueryExportName`
- size: `864`
- prototype: `__int64 __fastcall(_BYTE *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000d704`

## callees

- `0x140007074`
- `0x14000dc74`
- `0x14000f7ac`
- `0x1400101cc`

## string_xrefs

- `0x14000f80c`: `AslpFileGetImageNtHeader failed [%x]`
- `0x14000fa59`: `Export directory invalid or invalid image format`
- `0x14000fa06`: `RtlStringCchCopyA failed [%x]`

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
0x14000f7ac  mov     rax, rsp
0x14000f7af  mov     [rax+10h], rbx
0x14000f7b3  mov     [rax+18h], rsi
0x14000f7b7  push    rdi
0x14000f7b8  push    r12
0x14000f7ba  push    r13
0x14000f7bc  push    r14
0x14000f7be  push    r15
0x14000f7c0  sub     rsp, 0A0h
0x14000f7c7  mov     r13, rdx
0x14000f7ca  mov     rdi, rcx
0x14000f7cd  mov     qword ptr [rax+8], 0
0x14000f7d5  test    rdx, rdx
0x14000f7d8  jz      short loc_14000F7E9
0x14000f7da  mov     rsi, [rdx+20h]
0x14000f7de  test    rsi, rsi
0x14000f7e1  jz      short loc_14000F7E9
0x14000f7e3  mov     r12, [rdx+28h]
0x14000f7e7  jmp     short loc_14000F7EE
0x14000f7e9  xor     esi, esi
0x14000f7eb  xor     r12d, r12d
0x14000f7ee  mov     byte ptr [rcx], 0
0x14000f7f1  lea     rcx, [rsp+0C8h+arg_0]
0x14000f7f9  call    AslpFileGetImageNtHeader
0x14000f7fe  mov     ebx, eax
0x14000f800  mov     [rsp+0C8h+var_98], eax
0x14000f804  test    eax, eax
0x14000f806  jns     short loc_14000F82F
0x14000f808  mov     [rsp+0C8h+var_A8], eax
0x14000f80c  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x14000f813  mov     r8d, 10F4h
0x14000f819  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14000f820  mov     ecx, 1
0x14000f825  call    AslLogCallPrintf
0x14000f82a  jmp     loc_14000FAC2
0x14000f82f  mov     r14, [rsp+0C8h+arg_0]
0x14000f837  mov     [rsp+0C8h+var_60], r14
0x14000f83c  mov     ecx, 108h
0x14000f841  mov     [rsp+0C8h+var_58], rcx
0x14000f846  cmp     r14, rsi
0x14000f849  jb      loc_14000FA9B
0x14000f84f  lea     rax, [r14+108h]
0x14000f856  cmp     r14, rax
0x14000f859  ja      loc_14000FA9B
0x14000f85f  lea     r15, [r12+rsi]
0x14000f863  cmp     r14, r15
0x14000f866  ja      loc_14000FA9B
0x14000f86c  cmp     rax, rsi
0x14000f86f  jb      loc_14000FA9B
0x14000f875  cmp     rax, r15
0x14000f878  ja      loc_14000FA9B
0x14000f87e  cmp     rsi, r15
0x14000f881  ja      loc_14000FA9B
0x14000f887  cmp     r12, rcx
0x14000f88a  jb      loc_14000FA9B
0x14000f890  lea     eax, [rcx+3]
0x14000f893  cmp     [r14+18h], ax
0x14000f898  jnz     short loc_14000F8A0
0x14000f89a  lea     r8, [r14+78h]
0x14000f89e  jmp     short loc_14000F8B7
0x14000f8a0  mov     eax, 20Bh
0x14000f8a5  cmp     [r14+18h], ax
0x14000f8aa  jnz     loc_14000FA6D
0x14000f8b0  lea     r8, [r14+88h]
0x14000f8b7  mov     ebx, [r8+4]
0x14000f8bb  mov     r8d, [r8]
0x14000f8be  mov     rdx, r13
0x14000f8c1  mov     rcx, r14
0x14000f8c4  call    AslpImageRvaToVa
0x14000f8c9  mov     [rsp+0C8h+var_50], rax
0x14000f8ce  mov     [rsp+0C8h+var_48], rbx
0x14000f8d6  cmp     rax, rsi
0x14000f8d9  jb      loc_14000FA49
0x14000f8df  lea     rdx, [rbx+rax]
0x14000f8e3  cmp     rax, rdx
0x14000f8e6  ja      loc_14000FA49
0x14000f8ec  cmp     rax, r15
0x14000f8ef  ja      loc_14000FA49
0x14000f8f5  cmp     rdx, rsi
0x14000f8f8  jb      loc_14000FA49
0x14000f8fe  cmp     rdx, r15
0x14000f901  ja      loc_14000FA49
0x14000f907  cmp     rbx, r12
0x14000f90a  ja      loc_14000FA49
0x14000f910  mov     r8d, [rax+0Ch]
0x14000f914  mov     rdx, r13
0x14000f917  mov     rcx, r14
0x14000f91a  call    AslpImageRvaToVa
0x14000f91f  mov     [rsp+0C8h+var_40], rax
0x14000f927  mov     edx, 100h
0x14000f92c  mov     [rsp+0C8h+var_38], rdx
0x14000f934  cmp     rax, rsi
0x14000f937  jb      loc_14000FA20
0x14000f93d  lea     rcx, [rax+100h]
0x14000f944  cmp     rax, rcx
0x14000f947  ja      loc_14000FA20
0x14000f94d  cmp     rax, r15
0x14000f950  ja      loc_14000FA20
0x14000f956  cmp     rcx, rsi
0x14000f959  jb      loc_14000FA20
0x14000f95f  cmp     rcx, r15
0x14000f962  ja      loc_14000FA20
0x14000f968  xor     r10d, r10d
0x14000f96b  mov     [rsp+0C8h+var_94], r10d
0x14000f970  mov     [rsp+0C8h+var_94], r10d
0x14000f975  mov     r8d, 7FFFFFFEh
0x14000f97b  mov     [rsp+0C8h+var_68], r8
0x14000f980  mov     [rsp+0C8h+var_78], rax
0x14000f985  mov     [rsp+0C8h+var_70], rdx
0x14000f98a  mov     [rsp+0C8h+var_88], rdi
0x14000f98f  mov     ebx, r10d
0x14000f992  mov     ecx, r10d
0x14000f995  mov     [rsp+0C8h+var_80], rcx
0x14000f99a  test    rdx, rdx
0x14000f99d  jz      short loc_14000F9DE
0x14000f99f  test    r8, r8
0x14000f9a2  jz      short loc_14000F9D9
0x14000f9a4  mov     r9b, [rax]
0x14000f9a7  test    r9b, r9b
0x14000f9aa  jz      short loc_14000F9D9
0x14000f9ac  mov     [rdi], r9b
0x14000f9af  inc     rdi
0x14000f9b2  mov     [rsp+0C8h+var_88], rdi
0x14000f9b7  inc     rax
0x14000f9ba  mov     [rsp+0C8h+var_78], rax
0x14000f9bf  dec     rdx
0x14000f9c2  mov     [rsp+0C8h+var_70], rdx
0x14000f9c7  dec     r8
0x14000f9ca  mov     [rsp+0C8h+var_68], r8
0x14000f9cf  inc     rcx
0x14000f9d2  mov     [rsp+0C8h+var_80], rcx
0x14000f9d7  jmp     short loc_14000F99A
0x14000f9d9  test    rdx, rdx
0x14000f9dc  jnz     short loc_14000F9F3
0x14000f9de  dec     rdi
0x14000f9e1  mov     [rsp+0C8h+var_88], rdi
0x14000f9e6  dec     rcx
0x14000f9e9  mov     [rsp+0C8h+var_80], rcx
0x14000f9ee  mov     ebx, 80000005h
0x14000f9f3  mov     [rdi], r10b
0x14000f9f6  mov     [rsp+0C8h+var_94], ebx
0x14000f9fa  mov     [rsp+0C8h+var_98], ebx
0x14000f9fe  test    ebx, ebx
0x14000fa00  jns     short loc_14000FA18
0x14000fa02  mov     [rsp+0C8h+var_A8], ebx
0x14000fa06  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyA failed [%x]"
0x14000fa0d  mov     r8d, 1169h
0x14000fa13  jmp     loc_14000F819
0x14000fa18  mov     ebx, r10d
0x14000fa1b  jmp     loc_14000FABE
0x14000fa20  mov     ebx, 0C000007Bh
0x14000fa25  mov     [rsp+0C8h+var_98], ebx
0x14000fa29  lea     r9, aExportNamePoin; "Export name pointer out of bounds or in"...
0x14000fa30  mov     r8d, 114Fh
0x14000fa36  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14000fa3d  mov     ecx, 2
0x14000fa42  call    AslLogCallPrintf
0x14000fa47  jmp     short loc_14000FAC2
0x14000fa49  test    ebx, ebx
0x14000fa4b  jnz     short loc_14000FA59
0x14000fa4d  test    rax, rax
0x14000fa50  jnz     short loc_14000FA59
0x14000fa52  mov     ebx, 0C0000225h
0x14000fa57  jmp     short loc_14000FABE
0x14000fa59  lea     r9, aExportDirector; "Export directory invalid or invalid ima"...
0x14000fa60  mov     r8d, 1135h
0x14000fa66  mov     ecx, 2
0x14000fa6b  jmp     short loc_14000FAAD
0x14000fa6d  movzx   eax, word ptr [r14+18h]
0x14000fa72  mov     [rsp+0C8h+var_A8], eax
0x14000fa76  lea     r9, aUnknownImageOp; "Unknown image optional header magic val"...
0x14000fa7d  mov     r8d, 111Fh
0x14000fa83  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14000fa8a  mov     ecx, 2
0x14000fa8f  call    AslLogCallPrintf
0x14000fa94  mov     ebx, 0C00000BBh
0x14000fa99  jmp     short loc_14000FABE
0x14000fa9b  lea     r9, aImageTooSmallT; "Image too small to be a valid PE"
0x14000faa2  mov     r8d, 10FFh
0x14000faa8  mov     ecx, 1
0x14000faad  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14000fab4  call    AslLogCallPrintf
0x14000fab9  mov     ebx, 0C000007Bh
0x14000fabe  mov     [rsp+0C8h+var_98], ebx
0x14000fac2  jmp     short loc_14000FAED
0x14000fac4  mov     ebx, eax
0x14000fac6  mov     [rsp+0C8h+var_98], eax
0x14000faca  mov     [rsp+0C8h+var_A8], eax
0x14000face  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14000fad5  mov     r8d, 1172h
0x14000fadb  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x14000fae2  mov     ecx, 1
0x14000fae7  call    AslLogCallPrintf
0x14000faec  nop
0x14000faed  mov     eax, ebx
0x14000faef  lea     r11, [rsp+0C8h+var_28]
0x14000faf7  mov     rbx, [r11+38h]
0x14000fafb  mov     rsi, [r11+40h]
0x14000faff  mov     rsp, r11
0x14000fb02  pop     r15
0x14000fb04  pop     r14
0x14000fb06  pop     r13
0x14000fb08  pop     r12
0x14000fb0a  pop     rdi
0x14000fb0b  retn
0x14001188a  push    rbp
0x14001188c  sub     rsp, 30h
0x140011890  mov     rbp, rdx
0x140011893  mov     rax, [rcx]
0x140011896  xor     ecx, ecx
0x140011898  cmp     dword ptr [rax], 0C00000FDh
0x14001189e  setnz   cl
0x1400118a1  mov     [rbp+38h], ecx
0x1400118a4  mov     eax, [rbp+38h]
0x1400118a7  add     rsp, 30h
0x1400118ab  pop     rbp
0x1400118ac  retn
```
