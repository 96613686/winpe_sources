# AslFileMappingGetImageTypeEx

- ea: `0x18000e01c`
- end: `0x18000e239`
- name: `AslFileMappingGetImageTypeEx`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000de68`

## callees

- `0x18000dcf4`
- `0x18000e01c`
- `0x18000e240`
- `0x1800107f8`
- `0x180013658`

## string_xrefs

- `0x18000e0da`: `AslpFileGetImageNtHeader failed [%x]`

## pseudocode

```c
__int64 __fastcall AslFileMappingGetImageTypeEx(_WORD *a1, _WORD *a2, int *a3, _DWORD *a4, __int64 a5)
{
  __int16 v7; // ax
  __int16 v8; // r14
  int v9; // ecx
  int v10; // r13d
  unsigned int v11; // edi
  int ImageNtHeader; // eax
  const char *v13; // r9
  __int64 v14; // r8
  unsigned int v15; // r8d
  unsigned __int64 v16; // rax
  __int16 v18; // [rsp+30h] [rbp-58h]
  unsigned __int64 v19[8]; // [rsp+48h] [rbp-40h] BYREF
  _WORD *v21; // [rsp+98h] [rbp+10h]

  v21 = a2;
  v19[0] = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( *(_DWORD *)(a5 + 56) == 1 )
  {
    v11 = -1073741701;
    goto LABEL_25;
  }
  ImageNtHeader = AslFileMappingEnsure(a5, a2, a3, a4);
  v11 = ImageNtHeader;
  if ( ImageNtHeader < 0 )
  {
    v13 = "AslFileMappingEnsure failed [%x]";
    v14 = 1179;
LABEL_5:
    AslLogCallPrintf(1, "AslFileMappingGetImageTypeEx", v14, v13, ImageNtHeader);
LABEL_6:
    v7 = 0;
LABEL_7:
    v9 = 0;
    a2 = v21;
    goto LABEL_25;
  }
  if ( *(_DWORD *)(a5 + 56) != 6 )
  {
    v11 = -1073741701;
    goto LABEL_6;
  }
  ImageNtHeader = AslpFileGetImageNtHeader(v19, a5);
  v11 = ImageNtHeader;
  if ( ImageNtHeader < 0 )
  {
    v13 = "AslpFileGetImageNtHeader failed [%x]";
    v14 = 1199;
    goto LABEL_5;
  }
  v7 = *(_WORD *)(v19[0] + 4);
  v18 = v7;
  v8 = *(_WORD *)(v19[0] + 24);
  if ( *(_DWORD *)(a5 + 72) || !a3 && !a4 )
    goto LABEL_13;
  if ( v8 == 267 )
  {
    v15 = *(_DWORD *)(v19[0] + 232);
  }
  else
  {
    v15 = 0;
    if ( v8 == 523 )
      v15 = *(_DWORD *)(v19[0] + 248);
  }
  if ( !v15 )
  {
LABEL_13:
    v11 = 0;
    goto LABEL_7;
  }
  v16 = AslpImageRvaToVa(v19[0], a5, v15);
  if ( v16 )
  {
    v9 = 1;
    v10 = *(_DWORD *)(v16 + 16);
  }
  else
  {
    AslLogCallPrintf(2, "AslFileMappingGetImageTypeEx", 1253, "Failed to find the Cor20Header");
    v9 = 0;
  }
  v11 = 0;
  v7 = v18;
  a2 = v21;
LABEL_25:
  if ( a1 )
    *a1 = v7;
  if ( a2 )
    *a2 = v8;
  if ( a3 )
    *a3 = v9;
  if ( a4 )
    *a4 = v10;
  return v11;
}

```

## disassembly

```asm
0x18000e01c  mov     rax, rsp
0x18000e01f  mov     [rax+20h], r9
0x18000e023  mov     [rax+18h], r8
0x18000e027  mov     [rax+10h], rdx
0x18000e02b  mov     [rax+8], rcx
0x18000e02f  push    rbx
0x18000e030  push    rsi
0x18000e031  push    rdi
0x18000e032  push    r12
0x18000e034  push    r13
0x18000e036  push    r14
0x18000e038  push    r15
0x18000e03a  sub     rsp, 50h
0x18000e03e  mov     r15, r9
0x18000e041  mov     r12, r8
0x18000e044  xor     ebx, ebx
0x18000e046  mov     [rax-40h], rbx
0x18000e04a  movzx   eax, bx
0x18000e04d  movzx   r14d, bx
0x18000e051  mov     ecx, ebx
0x18000e053  mov     [rsp+88h+var_50], ebx
0x18000e057  mov     r13d, ebx
0x18000e05a  mov     [rsp+88h+var_48], ebx
0x18000e05e  mov     rsi, [rsp+88h+arg_20]
0x18000e066  cmp     dword ptr [rsi+38h], 1
0x18000e06a  jnz     short loc_18000E076
0x18000e06c  mov     edi, 0C000007Bh
0x18000e071  jmp     loc_18000E1FC
0x18000e076  mov     rcx, rsi
0x18000e079  call    AslFileMappingEnsure
0x18000e07e  mov     edi, eax
0x18000e080  test    eax, eax
0x18000e082  jns     short loc_18000E0BA
0x18000e084  lea     r9, aAslfilemapping_2; "AslFileMappingEnsure failed [%x]"
0x18000e08b  mov     r8d, 49Bh
0x18000e091  mov     [rsp+88h+var_68], eax
0x18000e095  lea     rdx, aAslfilemapping_8; "AslFileMappingGetImageTypeEx"
0x18000e09c  mov     ecx, 1
0x18000e0a1  call    AslLogCallPrintf
0x18000e0a6  movzx   eax, bx
0x18000e0a9  mov     ecx, [rsp+88h+var_50]
0x18000e0ad  mov     rdx, [rsp+88h+arg_8]
0x18000e0b5  jmp     loc_18000E1FC
0x18000e0ba  cmp     dword ptr [rsi+38h], 6
0x18000e0be  jz      short loc_18000E0C7
0x18000e0c0  mov     edi, 0C000007Bh
0x18000e0c5  jmp     short loc_18000E0A6
0x18000e0c7  mov     rdx, rsi
0x18000e0ca  lea     rcx, [rsp+88h+var_40]
0x18000e0cf  call    AslpFileGetImageNtHeader
0x18000e0d4  mov     edi, eax
0x18000e0d6  test    eax, eax
0x18000e0d8  jns     short loc_18000E0E9
0x18000e0da  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x18000e0e1  mov     r8d, 4AFh
0x18000e0e7  jmp     short loc_18000E091
0x18000e0e9  mov     rcx, [rsp+88h+var_40]
0x18000e0ee  movzx   eax, word ptr [rcx+4]
0x18000e0f2  mov     [rsp+88h+var_58], ax
0x18000e0f7  mov     word ptr [rsp+88h+arg_20], ax
0x18000e0ff  movzx   r14d, word ptr [rcx+18h]
0x18000e104  mov     [rsp+88h+var_54], r14w
0x18000e10a  cmp     [rsi+48h], ebx
0x18000e10d  jz      short loc_18000E113
0x18000e10f  mov     edi, ebx
0x18000e111  jmp     short loc_18000E0A9
0x18000e113  test    r12, r12
0x18000e116  jnz     short loc_18000E11D
0x18000e118  test    r15, r15
0x18000e11b  jz      short loc_18000E10F
0x18000e11d  mov     edx, 10Bh
0x18000e122  cmp     r14w, dx
0x18000e126  jnz     short loc_18000E131
0x18000e128  mov     r8d, [rcx+0E8h]
0x18000e12f  jmp     short loc_18000E146
0x18000e131  mov     r8d, ebx
0x18000e134  mov     edx, 20Bh
0x18000e139  cmp     r14w, dx
0x18000e13d  jnz     short loc_18000E146
0x18000e13f  mov     r8d, [rcx+0F8h]
0x18000e146  test    r8d, r8d
0x18000e149  jz      short loc_18000E10F
0x18000e14b  mov     rdx, rsi
0x18000e14e  call    AslpImageRvaToVa
0x18000e153  test    rax, rax
0x18000e156  jnz     short loc_18000E17E
0x18000e158  lea     r9, aFailedToFindTh; "Failed to find the Cor20Header"
0x18000e15f  mov     r8d, 4E5h
0x18000e165  lea     rdx, aAslfilemapping_8; "AslFileMappingGetImageTypeEx"
0x18000e16c  lea     ecx, [rax+2]
0x18000e16f  call    AslLogCallPrintf
0x18000e174  mov     [rsp+88h+var_4C], ebx
0x18000e178  mov     ecx, [rsp+88h+var_50]
0x18000e17c  jmp     short loc_18000E194
0x18000e17e  mov     ecx, 1
0x18000e183  mov     [rsp+88h+var_50], ecx
0x18000e187  mov     r13d, [rax+10h]
0x18000e18b  mov     [rsp+88h+var_48], r13d
0x18000e190  mov     [rsp+88h+var_4C], ebx
0x18000e194  mov     edi, ebx
0x18000e196  movzx   eax, [rsp+88h+var_58]
0x18000e19b  mov     rdx, [rsp+88h+arg_8]
0x18000e1a3  jmp     short loc_18000E1FC
0x18000e1a5  mov     edi, eax
0x18000e1a7  mov     [rsp+88h+var_4C], eax
0x18000e1ab  mov     [rsp+88h+var_68], eax
0x18000e1af  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x18000e1b6  mov     r8d, 4F2h
0x18000e1bc  lea     rdx, aAslfilemapping_8; "AslFileMappingGetImageTypeEx"
0x18000e1c3  mov     ecx, 1
0x18000e1c8  call    AslLogCallPrintf
0x18000e1cd  mov     r15, [rsp+88h+arg_18]
0x18000e1d5  mov     r12, [rsp+88h+arg_10]
0x18000e1dd  movzx   eax, word ptr [rsp+88h+arg_20]
0x18000e1e5  movzx   r14d, [rsp+88h+var_54]
0x18000e1eb  mov     r13d, [rsp+88h+var_48]
0x18000e1f0  mov     ecx, [rsp+88h+var_50]
0x18000e1f4  mov     rdx, [rsp+88h+arg_8]
0x18000e1fc  mov     r8, [rsp+88h+arg_0]
0x18000e204  test    r8, r8
0x18000e207  jz      short loc_18000E20D
0x18000e209  mov     [r8], ax
0x18000e20d  test    rdx, rdx
0x18000e210  jz      short loc_18000E216
0x18000e212  mov     [rdx], r14w
0x18000e216  test    r12, r12
0x18000e219  jz      short loc_18000E21F
0x18000e21b  mov     [r12], ecx
0x18000e21f  test    r15, r15
0x18000e222  jz      short loc_18000E227
0x18000e224  mov     [r15], r13d
0x18000e227  mov     eax, edi
0x18000e229  add     rsp, 50h
0x18000e22d  pop     r15
0x18000e22f  pop     r14
0x18000e231  pop     r13
0x18000e233  pop     r12
0x18000e235  pop     rdi
0x18000e236  pop     rsi
0x18000e237  pop     rbx
0x18000e238  retn
0x1800196ec  push    rbp
0x1800196ee  sub     rsp, 30h
0x1800196f2  mov     rbp, rdx
0x1800196f5  mov     rax, [rcx]
0x1800196f8  xor     ecx, ecx
0x1800196fa  cmp     dword ptr [rax], 0C00000FDh
0x180019700  setnz   cl
0x180019703  mov     [rbp+44h], ecx
0x180019706  mov     eax, [rbp+44h]
0x180019709  add     rsp, 30h
0x18001970d  pop     rbp
0x18001970e  retn
```
