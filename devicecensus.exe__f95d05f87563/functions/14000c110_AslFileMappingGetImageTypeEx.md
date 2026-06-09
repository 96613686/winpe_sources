# AslFileMappingGetImageTypeEx

- ea: `0x14000c110`
- end: `0x14000c32d`
- name: `AslFileMappingGetImageTypeEx`
- size: `541`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, int *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14000bf5c`

## callees

- `0x140007074`
- `0x14000bde8`
- `0x14000c110`
- `0x14000dc74`
- `0x1400101cc`

## string_xrefs

- `0x14000c1ce`: `AslpFileGetImageNtHeader failed [%x]`

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
  int v15; // r8d
  __int64 v16; // rax
  __int16 v18; // [rsp+30h] [rbp-58h]
  _QWORD v19[8]; // [rsp+48h] [rbp-40h] BYREF
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
  ImageNtHeader = AslFileMappingEnsure(a5);
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
  v7 = *(_WORD *)(v19[0] + 4LL);
  v18 = v7;
  v8 = *(_WORD *)(v19[0] + 24LL);
  if ( *(_DWORD *)(a5 + 72) || !a3 && !a4 )
    goto LABEL_13;
  if ( v8 == 267 )
  {
    v15 = *(_DWORD *)(v19[0] + 232LL);
  }
  else
  {
    v15 = 0;
    if ( v8 == 523 )
      v15 = *(_DWORD *)(v19[0] + 248LL);
  }
  if ( !v15 )
  {
LABEL_13:
    v11 = 0;
    goto LABEL_7;
  }
  v16 = AslpImageRvaToVa(v19[0], a5);
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
0x14000c110  mov     rax, rsp
0x14000c113  mov     [rax+20h], r9
0x14000c117  mov     [rax+18h], r8
0x14000c11b  mov     [rax+10h], rdx
0x14000c11f  mov     [rax+8], rcx
0x14000c123  push    rbx
0x14000c124  push    rsi
0x14000c125  push    rdi
0x14000c126  push    r12
0x14000c128  push    r13
0x14000c12a  push    r14
0x14000c12c  push    r15
0x14000c12e  sub     rsp, 50h
0x14000c132  mov     r15, r9
0x14000c135  mov     r12, r8
0x14000c138  xor     ebx, ebx
0x14000c13a  mov     [rax-40h], rbx
0x14000c13e  movzx   eax, bx
0x14000c141  movzx   r14d, bx
0x14000c145  mov     ecx, ebx
0x14000c147  mov     [rsp+88h+var_50], ebx
0x14000c14b  mov     r13d, ebx
0x14000c14e  mov     [rsp+88h+var_48], ebx
0x14000c152  mov     rsi, [rsp+88h+arg_20]
0x14000c15a  cmp     dword ptr [rsi+38h], 1
0x14000c15e  jnz     short loc_14000C16A
0x14000c160  mov     edi, 0C000007Bh
0x14000c165  jmp     loc_14000C2F0
0x14000c16a  mov     rcx, rsi
0x14000c16d  call    AslFileMappingEnsure
0x14000c172  mov     edi, eax
0x14000c174  test    eax, eax
0x14000c176  jns     short loc_14000C1AE
0x14000c178  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x14000c17f  mov     r8d, 49Bh
0x14000c185  mov     [rsp+88h+var_68], eax
0x14000c189  lea     rdx, aAslfilemapping_7; "AslFileMappingGetImageTypeEx"
0x14000c190  mov     ecx, 1
0x14000c195  call    AslLogCallPrintf
0x14000c19a  movzx   eax, bx
0x14000c19d  mov     ecx, [rsp+88h+var_50]
0x14000c1a1  mov     rdx, [rsp+88h+arg_8]
0x14000c1a9  jmp     loc_14000C2F0
0x14000c1ae  cmp     dword ptr [rsi+38h], 6
0x14000c1b2  jz      short loc_14000C1BB
0x14000c1b4  mov     edi, 0C000007Bh
0x14000c1b9  jmp     short loc_14000C19A
0x14000c1bb  mov     rdx, rsi
0x14000c1be  lea     rcx, [rsp+88h+var_40]
0x14000c1c3  call    AslpFileGetImageNtHeader
0x14000c1c8  mov     edi, eax
0x14000c1ca  test    eax, eax
0x14000c1cc  jns     short loc_14000C1DD
0x14000c1ce  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x14000c1d5  mov     r8d, 4AFh
0x14000c1db  jmp     short loc_14000C185
0x14000c1dd  mov     rcx, [rsp+88h+var_40]
0x14000c1e2  movzx   eax, word ptr [rcx+4]
0x14000c1e6  mov     [rsp+88h+var_58], ax
0x14000c1eb  mov     word ptr [rsp+88h+arg_20], ax
0x14000c1f3  movzx   r14d, word ptr [rcx+18h]
0x14000c1f8  mov     [rsp+88h+var_54], r14w
0x14000c1fe  cmp     [rsi+48h], ebx
0x14000c201  jz      short loc_14000C207
0x14000c203  mov     edi, ebx
0x14000c205  jmp     short loc_14000C19D
0x14000c207  test    r12, r12
0x14000c20a  jnz     short loc_14000C211
0x14000c20c  test    r15, r15
0x14000c20f  jz      short loc_14000C203
0x14000c211  mov     edx, 10Bh
0x14000c216  cmp     r14w, dx
0x14000c21a  jnz     short loc_14000C225
0x14000c21c  mov     r8d, [rcx+0E8h]
0x14000c223  jmp     short loc_14000C23A
0x14000c225  mov     r8d, ebx
0x14000c228  mov     edx, 20Bh
0x14000c22d  cmp     r14w, dx
0x14000c231  jnz     short loc_14000C23A
0x14000c233  mov     r8d, [rcx+0F8h]
0x14000c23a  test    r8d, r8d
0x14000c23d  jz      short loc_14000C203
0x14000c23f  mov     rdx, rsi
0x14000c242  call    AslpImageRvaToVa
0x14000c247  test    rax, rax
0x14000c24a  jnz     short loc_14000C272
0x14000c24c  lea     r9, aFailedToFindTh; "Failed to find the Cor20Header"
0x14000c253  mov     r8d, 4E5h
0x14000c259  lea     rdx, aAslfilemapping_7; "AslFileMappingGetImageTypeEx"
0x14000c260  lea     ecx, [rax+2]
0x14000c263  call    AslLogCallPrintf
0x14000c268  mov     [rsp+88h+var_4C], ebx
0x14000c26c  mov     ecx, [rsp+88h+var_50]
0x14000c270  jmp     short loc_14000C288
0x14000c272  mov     ecx, 1
0x14000c277  mov     [rsp+88h+var_50], ecx
0x14000c27b  mov     r13d, [rax+10h]
0x14000c27f  mov     [rsp+88h+var_48], r13d
0x14000c284  mov     [rsp+88h+var_4C], ebx
0x14000c288  mov     edi, ebx
0x14000c28a  movzx   eax, [rsp+88h+var_58]
0x14000c28f  mov     rdx, [rsp+88h+arg_8]
0x14000c297  jmp     short loc_14000C2F0
0x14000c299  mov     edi, eax
0x14000c29b  mov     [rsp+88h+var_4C], eax
0x14000c29f  mov     [rsp+88h+var_68], eax
0x14000c2a3  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14000c2aa  mov     r8d, 4F2h
0x14000c2b0  lea     rdx, aAslfilemapping_7; "AslFileMappingGetImageTypeEx"
0x14000c2b7  mov     ecx, 1
0x14000c2bc  call    AslLogCallPrintf
0x14000c2c1  mov     r15, [rsp+88h+arg_18]
0x14000c2c9  mov     r12, [rsp+88h+arg_10]
0x14000c2d1  movzx   eax, word ptr [rsp+88h+arg_20]
0x14000c2d9  movzx   r14d, [rsp+88h+var_54]
0x14000c2df  mov     r13d, [rsp+88h+var_48]
0x14000c2e4  mov     ecx, [rsp+88h+var_50]
0x14000c2e8  mov     rdx, [rsp+88h+arg_8]
0x14000c2f0  mov     r8, [rsp+88h+arg_0]
0x14000c2f8  test    r8, r8
0x14000c2fb  jz      short loc_14000C301
0x14000c2fd  mov     [r8], ax
0x14000c301  test    rdx, rdx
0x14000c304  jz      short loc_14000C30A
0x14000c306  mov     [rdx], r14w
0x14000c30a  test    r12, r12
0x14000c30d  jz      short loc_14000C313
0x14000c30f  mov     [r12], ecx
0x14000c313  test    r15, r15
0x14000c316  jz      short loc_14000C31B
0x14000c318  mov     [r15], r13d
0x14000c31b  mov     eax, edi
0x14000c31d  add     rsp, 50h
0x14000c321  pop     r15
0x14000c323  pop     r14
0x14000c325  pop     r13
0x14000c327  pop     r12
0x14000c329  pop     rdi
0x14000c32a  pop     rsi
0x14000c32b  pop     rbx
0x14000c32c  retn
0x140011860  push    rbp
0x140011862  sub     rsp, 30h
0x140011866  mov     rbp, rdx
0x140011869  mov     rax, [rcx]
0x14001186c  xor     ecx, ecx
0x14001186e  cmp     dword ptr [rax], 0C00000FDh
0x140011874  setnz   cl
0x140011877  mov     [rbp+44h], ecx
0x14001187a  mov     eax, [rbp+44h]
0x14001187d  add     rsp, 30h
0x140011881  pop     rbp
0x140011882  retn
```
