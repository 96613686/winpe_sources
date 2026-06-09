# ExtractAtoBStyleClut

- ea: `0x180019b00`
- end: `0x180019d2c`
- name: `ExtractAtoBStyleClut`
- size: `556`
- prototype: `__int64 __fastcall(HPROFILE hProfile, TAGTYPE tag, unsigned int, unsigned __int8, unsigned __int8, unsigned __int64 dwOffset, __int64, _DWORD *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180020c14`
- `0x1800213cc`

## callees

- `0x1800042e0`
- `0x18000604c`
- `0x1800060f0`
- `0x180018b68`
- `0x180019b00`
- `0x18003d040`

## import_xrefs

- `mscms!GetColorProfileElement` at `0x180019bbd`
- `mscms!GetColorProfileElement` at `0x180019bbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019b98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019b98`

## pseudocode

```c
__int64 __fastcall ExtractAtoBStyleClut(
        HPROFILE hProfile,
        TAGTYPE tag,
        unsigned int a3,
        unsigned __int8 a4,
        char a5,
        unsigned __int64 dwOffset,
        __int64 a7,
        _DWORD *a8,
        _QWORD *a9,
        __int64 a10)
{
  void *v10; // rsi
  unsigned int v13; // edi
  unsigned __int64 i; // rax
  int v15; // ecx
  unsigned __int64 j; // rax
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // r8
  int v19; // r14d
  unsigned __int64 v20; // rdi
  unsigned int v21; // edi
  void *v22; // rax
  unsigned int v23; // ebx
  _DWORD *v24; // rcx
  DWORD pcbElement; // [rsp+30h] [rbp-40h] BYREF
  __int16 v27; // [rsp+34h] [rbp-3Ch] BYREF
  WINBOOL pbReference; // [rsp+38h] [rbp-38h] BYREF
  TAGTYPE taga; // [rsp+3Ch] [rbp-34h]
  _QWORD *v30; // [rsp+40h] [rbp-30h]
  __int64 v31; // [rsp+48h] [rbp-28h]
  __int128 pElement; // [rsp+50h] [rbp-20h] BYREF
  int v33; // [rsp+60h] [rbp-10h]

  v10 = 0;
  v30 = a9;
  v31 = a10;
  v13 = a4;
  taga = tag;
  v27 = 0;
  pcbElement = 0;
  v33 = 0;
  pElement = 0;
  if ( a4 > 8u )
    goto LABEL_30;
  if ( dwOffset >= a3 )
    goto LABEL_30;
  pcbElement = 20;
  if ( a3 - dwOffset < 0x14 )
    goto LABEL_30;
  pbReference = 0;
  SetLastError(0);
  if ( !GetColorProfileElement(hProfile, tag, dwOffset, &pcbElement, &pElement, &pbReference) )
  {
    v23 = 2012;
    goto LABEL_31;
  }
  if ( pcbElement != 20 )
    goto LABEL_30;
  *a8 = 0;
  for ( i = 0; i < v13; ++i )
  {
    v15 = *((unsigned __int8 *)&pElement + i);
    if ( !(_BYTE)v15 )
      goto LABEL_30;
    *(_BYTE *)(a7 + i) = v15;
    if ( v15 > *a8 )
      *a8 = v15;
  }
  for ( j = v13; j < 0x10; ++j )
  {
    if ( *((_BYTE *)&pElement + j) )
      goto LABEL_30;
  }
  v17 = 0;
  v18 = 1;
  while ( v17 < v13 )
  {
    if ( v18 >= 0xFFFFFFFF / *(unsigned __int8 *)(a7 + v17) )
      goto LABEL_30;
    v18 *= *(unsigned __int8 *)(a7 + v17++);
  }
  if ( v18 >= 0xFFFFFFFF / (unsigned __int8)a5 )
    goto LABEL_30;
  v19 = (unsigned __int8)v33;
  if ( (unsigned __int8)(v33 - 1) > 1u )
    goto LABEL_30;
  v20 = v18 * (unsigned __int8)a5;
  if ( v20 >= 0xFFFFFFFF / (unsigned __int8)v33 )
    goto LABEL_30;
  v21 = (unsigned __int8)v33 * (_DWORD)v20;
  v22 = SmartNewPtr(v21, &v27);
  v23 = v27;
  v10 = v22;
  if ( v27 )
    goto LABEL_31;
  pcbElement = v21;
  v23 = CMGetPartialProfileElement(hProfile, taga, (int)dwOffset + 20, &pcbElement, v22);
  if ( v23 )
    goto LABEL_31;
  if ( pcbElement != v21 )
  {
LABEL_30:
    v23 = 2011;
    goto LABEL_31;
  }
  if ( (_BYTE)v19 == 2 )
    SwapShortOffset(v10, 0, v21);
  v24 = (_DWORD *)v31;
  *v30 = v10;
  *v24 = 8 * v19;
  v10 = 0;
LABEL_31:
  DisposeIfPtr(v10);
  return v23;
}

```

## disassembly

```asm
0x180019b00  mov     [rsp-38h+arg_10], rbx
0x180019b05  push    rbp
0x180019b06  push    rsi
0x180019b07  push    rdi
0x180019b08  push    r12
0x180019b0a  push    r13
0x180019b0c  push    r14
0x180019b0e  push    r15
0x180019b10  mov     rbp, rsp
0x180019b13  sub     rsp, 70h
0x180019b17  mov     rax, cs:__security_cookie
0x180019b1e  xor     rax, rsp
0x180019b21  mov     [rbp+var_8], rax
0x180019b25  mov     rax, [rbp+arg_40]
0x180019b2c  xor     esi, esi
0x180019b2e  mov     r14, [rbp+arg_30]
0x180019b32  xorps   xmm0, xmm0
0x180019b35  mov     rbx, [rbp+arg_38]
0x180019b39  mov     r15d, edx
0x180019b3c  mov     [rbp+var_30], rax
0x180019b40  mov     r13, rcx
0x180019b43  mov     rax, [rbp+arg_48]
0x180019b4a  mov     [rbp+var_28], rax
0x180019b4e  xor     eax, eax
0x180019b50  movzx   edi, r9b
0x180019b54  mov     [rbp+tag], edx
0x180019b57  mov     [rbp+var_3C], ax
0x180019b5b  mov     [rbp+pcbElement], eax
0x180019b5e  mov     [rbp+var_10], eax
0x180019b61  movups  [rbp+var_20], xmm0
0x180019b65  cmp     dil, 8
0x180019b69  ja      loc_180019CF9
0x180019b6f  mov     r12, [rbp+dwOffset]
0x180019b73  mov     eax, r8d
0x180019b76  cmp     r12, rax
0x180019b79  jnb     loc_180019CF9
0x180019b7f  sub     rax, r12
0x180019b82  mov     [rbp+pcbElement], 14h
0x180019b89  cmp     rax, 14h
0x180019b8d  jb      loc_180019CF9
0x180019b93  xor     ecx, ecx; dwErrCode
0x180019b95  mov     [rbp+var_38], esi
0x180019b98  call    cs:__imp_SetLastError
0x180019b9e  lea     rax, [rbp+var_38]
0x180019ba2  mov     r8d, r12d; dwOffset
0x180019ba5  mov     [rsp+70h+pbReference], rax; pbReference
0x180019baa  lea     r9, [rbp+pcbElement]; pcbElement
0x180019bae  lea     rax, [rbp+var_20]
0x180019bb2  mov     edx, r15d; tag
0x180019bb5  mov     rcx, r13; hProfile
0x180019bb8  mov     [rsp+70h+pElement], rax; pElement
0x180019bbd  call    cs:__imp_GetColorProfileElement
0x180019bc3  test    eax, eax
0x180019bc5  jz      loc_180019CF2
0x180019bcb  cmp     [rbp+pcbElement], 14h
0x180019bcf  jnz     loc_180019CF9
0x180019bd5  mov     r10d, edi
0x180019bd8  mov     [rbx], esi
0x180019bda  lea     edi, [rsi+1]
0x180019bdd  xor     eax, eax
0x180019bdf  cmp     rax, r10
0x180019be2  jnb     short loc_180019C00
0x180019be4  movzx   ecx, byte ptr [rbp+rax+var_20]
0x180019be9  test    cl, cl
0x180019beb  jz      loc_180019CF9
0x180019bf1  mov     [r14+rax], cl
0x180019bf5  cmp     ecx, [rbx]
0x180019bf7  jle     short loc_180019BFB
0x180019bf9  mov     [rbx], ecx
0x180019bfb  add     rax, rdi
0x180019bfe  jmp     short loc_180019BDF
0x180019c00  mov     rax, r10
0x180019c03  cmp     rax, 10h
0x180019c07  jnb     short loc_180019C19
0x180019c09  cmp     byte ptr [rbp+rax+var_20], sil
0x180019c0e  jnz     loc_180019CF9
0x180019c14  add     rax, rdi
0x180019c17  jmp     short loc_180019C03
0x180019c19  xor     r9d, r9d
0x180019c1c  mov     r8, rdi
0x180019c1f  or      ebx, 0FFFFFFFFh
0x180019c22  xor     edx, edx
0x180019c24  mov     eax, ebx
0x180019c26  cmp     r9, r10
0x180019c29  jnb     short loc_180019C47
0x180019c2b  movzx   r11d, byte ptr [r14+r9]
0x180019c30  div     r11d
0x180019c33  mov     ecx, eax
0x180019c35  cmp     r8, rcx
0x180019c38  jnb     loc_180019CF9
0x180019c3e  imul    r8, r11
0x180019c42  add     r9, rdi
0x180019c45  jmp     short loc_180019C22
0x180019c47  movzx   ecx, [rbp+arg_20]
0x180019c4b  div     ecx
0x180019c4d  mov     ecx, eax
0x180019c4f  cmp     r8, rcx
0x180019c52  jnb     loc_180019CF9
0x180019c58  movzx   r14d, byte ptr [rbp+var_10]
0x180019c5d  mov     cl, r14b
0x180019c60  sub     cl, dil
0x180019c63  cmp     cl, dil
0x180019c66  ja      loc_180019CF9
0x180019c6c  movzx   edi, [rbp+arg_20]
0x180019c70  xor     edx, edx
0x180019c72  mov     eax, ebx
0x180019c74  mov     r15d, r14d
0x180019c77  div     r14d
0x180019c7a  imul    rdi, r8
0x180019c7e  mov     ecx, eax
0x180019c80  cmp     rdi, rcx
0x180019c83  jnb     short loc_180019CF9
0x180019c85  imul    edi, r15d
0x180019c89  lea     rdx, [rbp+var_3C]
0x180019c8d  mov     ecx, edi
0x180019c8f  call    SmartNewPtr
0x180019c94  movsx   ebx, [rbp+var_3C]
0x180019c98  mov     rsi, rax
0x180019c9b  test    ebx, ebx
0x180019c9d  jnz     short loc_180019CFE
0x180019c9f  mov     edx, [rbp+tag]; tag
0x180019ca2  lea     r8d, [r12+14h]; dwOffset
0x180019ca7  lea     r9, [rbp+pcbElement]; pcbElement
0x180019cab  mov     [rbp+pcbElement], edi
0x180019cae  mov     rcx, r13; hProfile
0x180019cb1  mov     [rsp+70h+pElement], rax; PVOID
0x180019cb6  call    CMGetPartialProfileElement
0x180019cbb  mov     ebx, eax
0x180019cbd  test    eax, eax
0x180019cbf  jnz     short loc_180019CFE
0x180019cc1  cmp     [rbp+pcbElement], edi
0x180019cc4  jnz     short loc_180019CF9
0x180019cc6  cmp     r14b, 2
0x180019cca  jnz     short loc_180019CD9
0x180019ccc  mov     r8d, edi
0x180019ccf  xor     edx, edx
0x180019cd1  mov     rcx, rsi
0x180019cd4  call    SwapShortOffset
0x180019cd9  mov     rax, [rbp+var_30]
0x180019cdd  mov     rcx, [rbp+var_28]
0x180019ce1  mov     [rax], rsi
0x180019ce4  lea     eax, ds:0[r14*8]
0x180019cec  mov     [rcx], eax
0x180019cee  xor     esi, esi
0x180019cf0  jmp     short loc_180019CFE
0x180019cf2  mov     ebx, 7DCh
0x180019cf7  jmp     short loc_180019CFE
0x180019cf9  mov     ebx, 7DBh
0x180019cfe  mov     rcx, rsi
0x180019d01  call    DisposeIfPtr
0x180019d06  mov     eax, ebx
0x180019d08  mov     rcx, [rbp+var_8]
0x180019d0c  xor     rcx, rsp; StackCookie
0x180019d0f  call    __security_check_cookie
0x180019d14  mov     rbx, [rsp+70h+arg_10]
0x180019d1c  add     rsp, 70h
0x180019d20  pop     r15
0x180019d22  pop     r14
0x180019d24  pop     r13
0x180019d26  pop     r12
0x180019d28  pop     rdi
0x180019d29  pop     rsi
0x180019d2a  pop     rbp
0x180019d2b  retn
```
