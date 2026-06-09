# RtlpOpenImageFileOptionsKeyEx

- ea: `0x1800d4a58`
- end: `0x1800d4d17`
- name: `RtlpOpenImageFileOptionsKeyEx`
- size: `703`
- prototype: ``
- caller_count: `8`
- callee_count: `11`
- tags: ``

## callers

- `0x180053b90`
- `0x1800d3468`
- `0x1800d36e4`
- `0x1800d4450`
- `0x1800d4580`
- `0x180113cd0`
- `0x1801147a0`
- `0x18013b95c`

## callees

- `0x1800d49a4`
- `0x1800d4a58`
- `0x1800d4d20`
- `0x1800d5174`
- `0x1800d5210`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015ee80`
- `0x18015f6d0`
- `0x180160650`

## string_xrefs

- `0x1800d4be8`: `FilterFullPath`

## pseudocode

```c
__int64 __fastcall RtlpOpenImageFileOptionsKeyEx(unsigned __int16 *a1, unsigned int a2, char a3, _QWORD *a4)
{
  __int64 v7; // rdx
  _WORD *v8; // r8
  int v9; // ecx
  char v10; // r12
  int v11; // ecx
  char v12; // r15
  __int64 result; // rax
  HANDLE v14; // rdi
  int v15; // eax
  int v16; // ebx
  int v17; // eax
  HANDLE v18; // rdi
  size_t v19; // rax
  size_t v20; // rax
  int v21; // eax
  HANDLE Handle; // [rsp+40h] [rbp-29h] BYREF
  const wchar_t *v23; // [rsp+48h] [rbp-21h]
  __int128 v24; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v25[96]; // [rsp+60h] [rbp-9h] BYREF
  HANDLE v26; // [rsp+D0h] [rbp+67h] BYREF
  int v27; // [rsp+E0h] [rbp+77h] BYREF
  _QWORD *v28; // [rsp+E8h] [rbp+7Fh]

  v28 = a4;
  *a4 = 0;
  Handle = 0;
  v26 = 0;
  v7 = *a1;
  v8 = (_WORD *)(v7 + *((_QWORD *)a1 + 1));
  v24 = 0;
  memset(v25, 0, 44);
  if ( a3 && (v7 + 2 > (unsigned __int64)a1[1] || *v8) )
    return 3221225485LL;
  v9 = v7;
  v10 = 0;
  while ( (_DWORD)v7 )
  {
    if ( *(v8 - 1) == 92 )
    {
      v10 = 1;
      break;
    }
    --v8;
    LODWORD(v7) = v7 - 2;
  }
  v11 = v9 - v7;
  *((_QWORD *)&v24 + 1) = v8;
  LOWORD(v24) = v11;
  if ( (unsigned __int16)v11 != v11 )
    return 3221225507LL;
  if ( a3 )
  {
    LOBYTE(v8) = a3;
    v12 = 1;
    result = RtlpOpenBaseImageFileOptionsKeyEx(&Handle, a2, v8);
  }
  else
  {
    v12 = 0;
    result = RtlpOpenBaseImageFileOptionsKey(&Handle);
  }
  if ( (int)result >= 0 )
  {
    v14 = Handle;
    *(_QWORD *)&v25[8] = Handle;
    *(_QWORD *)&v25[16] = &v24;
    *(_DWORD *)v25 = 48;
    *(_DWORD *)&v25[24] = 576;
    *(_OWORD *)&v25[32] = 0;
    if ( a3 )
      v15 = ZwCreateKey(&v26, a2, v25, 0, 0, 0, 0);
    else
      v15 = NtOpenKey(&v26, a2, v25);
    v16 = v15;
    if ( v12 )
      NtClose(v14);
    if ( v16 < 0 )
      return (unsigned int)v16;
    Handle = v26;
    v21 = RtlpProcessIFEOKeyFilter(&Handle, a2, a1);
    v18 = Handle;
    v16 = v21;
    if ( v21 < 0 )
      goto LABEL_38;
    if ( Handle != v26 || !v10 || !a3 )
      goto LABEL_32;
    Handle = 0;
    v17 = RtlpCreateIFEOKeyFilterKey(&Handle, v26, a2 | 0x10000);
    v18 = Handle;
    v16 = v17;
    if ( v17 < 0 )
    {
LABEL_31:
      NtClose(v26);
      if ( v16 >= 0 )
      {
LABEL_32:
        *v28 = v18;
        return (unsigned int)v16;
      }
LABEL_38:
      if ( v18 )
        NtClose(v18);
      return (unsigned int)v16;
    }
    Handle = 0;
    v23 = L"FilterFullPath";
    v19 = wcslen(L"FilterFullPath");
    if ( v19 <= 0x7FFE )
    {
      LOWORD(Handle) = 2 * v19;
      WORD1(Handle) = 2 * v19 + 2;
      v16 = ZwSetValueKey(v18, &Handle, 0, 1, *((_QWORD *)a1 + 1), a1[1]);
      if ( v16 < 0 )
      {
LABEL_30:
        NtDeleteKey(v18);
        goto LABEL_31;
      }
      v27 = 1;
      v23 = L"UseFilter";
      Handle = 0;
      v20 = wcslen(L"UseFilter");
      if ( v20 <= 0x7FFE )
      {
        LOWORD(Handle) = 2 * v20;
        WORD1(Handle) = 2 * v20 + 2;
        v16 = ZwSetValueKey(v26, &Handle, 0, 4, &v27, 4);
        if ( v16 >= 0 )
          goto LABEL_31;
        goto LABEL_30;
      }
    }
    v16 = -1073741562;
    goto LABEL_30;
  }
  return result;
}

```

## disassembly

```asm
0x1800d4a58  mov     [rsp-8+arg_8], rbx
0x1800d4a5d  mov     [rsp-8+arg_18], r9
0x1800d4a62  push    rbp
0x1800d4a63  push    rsi
0x1800d4a64  push    rdi
0x1800d4a65  push    r12
0x1800d4a67  push    r13
0x1800d4a69  push    r14
0x1800d4a6b  push    r15
0x1800d4a6d  lea     rbp, [rsp-27h]
0x1800d4a72  sub     rsp, 90h
0x1800d4a79  xor     ebx, ebx
0x1800d4a7b  xorps   xmm0, xmm0
0x1800d4a7e  mov     r13, rcx
0x1800d4a81  mov     [r9], rbx
0x1800d4a84  mov     r14b, r8b
0x1800d4a87  mov     [rbp+57h+Handle], rbx
0x1800d4a8b  mov     esi, edx
0x1800d4a8d  mov     [rbp+57h+arg_0], rbx
0x1800d4a91  xor     ecx, ecx
0x1800d4a93  movzx   edx, word ptr [r13+0]
0x1800d4a98  mov     r8, [r13+8]
0x1800d4a9c  add     r8, rdx
0x1800d4a9f  movups  [rbp+57h+var_50], xmm0
0x1800d4aa3  movups  [rbp+57h+var_70], xmm0
0x1800d4aa7  movups  [rbp+57h+var_60], xmm0
0x1800d4aab  movups  [rbp+57h+var_50+0Ch], xmm0
0x1800d4aaf  test    r14b, r14b
0x1800d4ab2  jnz     loc_1800D4B75
0x1800d4ab8  mov     ecx, edx
0x1800d4aba  mov     r12b, bl
0x1800d4abd  test    edx, edx
0x1800d4abf  jz      short loc_1800D4AD5
0x1800d4ac1  cmp     word ptr [r8-2], 5Ch ; '\'
0x1800d4ac7  jz      short loc_1800D4AD2
0x1800d4ac9  add     r8, 0FFFFFFFFFFFFFFFEh
0x1800d4acd  add     edx, 0FFFFFFFEh
0x1800d4ad0  jmp     short loc_1800D4ABD
0x1800d4ad2  mov     r12b, 1
0x1800d4ad5  sub     ecx, edx
0x1800d4ad7  mov     qword ptr [rbp+57h+var_70+8], r8
0x1800d4adb  movzx   eax, cx
0x1800d4ade  mov     word ptr [rbp+57h+var_70], ax
0x1800d4ae2  cmp     eax, ecx
0x1800d4ae4  jnz     loc_1800D4BB4
0x1800d4aea  lea     rcx, [rbp+57h+Handle]
0x1800d4aee  test    r14b, r14b
0x1800d4af1  jnz     loc_1800D4BA2
0x1800d4af7  mov     r15b, bl
0x1800d4afa  call    RtlpOpenBaseImageFileOptionsKey
0x1800d4aff  test    eax, eax
0x1800d4b01  js      short loc_1800D4B59
0x1800d4b03  mov     rdi, [rbp+57h+Handle]
0x1800d4b07  lea     rax, [rbp+57h+var_70]
0x1800d4b0b  mov     qword ptr [rbp+57h+var_60+8], rdi
0x1800d4b0f  xorps   xmm0, xmm0
0x1800d4b12  mov     qword ptr [rbp+57h+var_50], rax
0x1800d4b16  lea     r8, [rbp+57h+var_60]
0x1800d4b1a  mov     dword ptr [rbp+57h+var_60], 30h ; '0'
0x1800d4b21  mov     edx, esi
0x1800d4b23  mov     dword ptr [rbp+57h+var_50+8], 240h
0x1800d4b2a  lea     rcx, [rbp+57h+arg_0]
0x1800d4b2e  movdqu  [rbp+57h+var_40], xmm0
0x1800d4b33  test    r14b, r14b
0x1800d4b36  jnz     short loc_1800D4B8A
0x1800d4b38  call    NtOpenKey
0x1800d4b3d  mov     ebx, eax
0x1800d4b3f  test    r15b, r15b
0x1800d4b42  jz      short loc_1800D4B4C
0x1800d4b44  mov     rcx, rdi; Handle
0x1800d4b47  call    NtClose
0x1800d4b4c  xor     r15d, r15d
0x1800d4b4f  test    ebx, ebx
0x1800d4b51  jns     loc_1800D4CC2
0x1800d4b57  mov     eax, ebx
0x1800d4b59  mov     rbx, [rsp+0C0h+arg_8]
0x1800d4b61  add     rsp, 90h
0x1800d4b68  pop     r15
0x1800d4b6a  pop     r14
0x1800d4b6c  pop     r13
0x1800d4b6e  pop     r12
0x1800d4b70  pop     rdi
0x1800d4b71  pop     rsi
0x1800d4b72  pop     rbp
0x1800d4b73  retn
0x1800d4b75  movzx   ecx, word ptr [r13+2]
0x1800d4b7a  lea     rax, [rdx+2]
0x1800d4b7e  cmp     rax, rcx
0x1800d4b81  jbe     short loc_1800D4BBB
0x1800d4b83  mov     eax, 0C000000Dh
0x1800d4b88  jmp     short loc_1800D4B59
0x1800d4b8a  mov     [rsp+0C0h+var_90], rbx
0x1800d4b8f  xor     r9d, r9d
0x1800d4b92  mov     [rsp+0C0h+var_98], ebx
0x1800d4b96  mov     [rsp+0C0h+var_A0], rbx
0x1800d4b9b  call    ZwCreateKey
0x1800d4ba0  jmp     short loc_1800D4B3D
0x1800d4ba2  mov     r8b, r14b
0x1800d4ba5  mov     edx, esi
0x1800d4ba7  mov     r15b, 1
0x1800d4baa  call    RtlpOpenBaseImageFileOptionsKeyEx
0x1800d4baf  jmp     loc_1800D4AFF
0x1800d4bb4  mov     eax, 0C0000023h
0x1800d4bb9  jmp     short loc_1800D4B59
0x1800d4bbb  cmp     [r8], bx
0x1800d4bbf  jnz     short loc_1800D4B83
0x1800d4bc1  jmp     loc_1800D4AB8
0x1800d4bc6  bts     esi, 10h
0x1800d4bca  mov     [rbp+57h+Handle], r15
0x1800d4bce  mov     r8d, esi
0x1800d4bd1  lea     rcx, [rbp+57h+Handle]
0x1800d4bd5  call    RtlpCreateIFEOKeyFilterKey
0x1800d4bda  mov     rdi, [rbp+57h+Handle]
0x1800d4bde  mov     ebx, eax
0x1800d4be0  test    eax, eax
0x1800d4be2  js      loc_1800D4CA9
0x1800d4be8  lea     rcx, aFilterfullpath; "FilterFullPath"
0x1800d4bef  mov     [rbp+57h+Handle], r15
0x1800d4bf3  mov     [rbp+57h+var_78], rcx
0x1800d4bf7  call    wcslen
0x1800d4bfc  mov     esi, 7FFEh
0x1800d4c01  cmp     rax, rsi
0x1800d4c04  ja      loc_1800D4D10
0x1800d4c0a  add     ax, ax
0x1800d4c0d  lea     rdx, [rbp+57h+Handle]
0x1800d4c11  mov     word ptr [rbp+57h+Handle], ax
0x1800d4c15  mov     r14d, 1
0x1800d4c1b  add     ax, 2
0x1800d4c1f  mov     r9d, r14d
0x1800d4c22  mov     word ptr [rbp+57h+Handle+2], ax
0x1800d4c26  xor     r8d, r8d
0x1800d4c29  movzx   eax, word ptr [r13+2]
0x1800d4c2e  mov     rcx, rdi
0x1800d4c31  mov     [rsp+0C0h+var_98], eax
0x1800d4c35  mov     rax, [r13+8]
0x1800d4c39  mov     [rsp+0C0h+var_A0], rax
0x1800d4c3e  call    ZwSetValueKey
0x1800d4c43  mov     ebx, eax
0x1800d4c45  test    eax, eax
0x1800d4c47  js      short loc_1800D4CA1
0x1800d4c49  lea     rcx, aUsefilter; "UseFilter"
0x1800d4c50  mov     [rbp+57h+arg_10], r14d
0x1800d4c54  mov     [rbp+57h+var_78], rcx
0x1800d4c58  mov     [rbp+57h+Handle], r15
0x1800d4c5c  call    wcslen
0x1800d4c61  cmp     rax, rsi
0x1800d4c64  ja      loc_1800D4D10
0x1800d4c6a  mov     rcx, [rbp+57h+arg_0]
0x1800d4c6e  lea     r9d, [r14+3]
0x1800d4c72  add     ax, ax
0x1800d4c75  mov     [rsp+0C0h+var_98], r9d
0x1800d4c7a  mov     word ptr [rbp+57h+Handle], ax
0x1800d4c7e  lea     rdx, [rbp+57h+Handle]
0x1800d4c82  add     ax, 2
0x1800d4c86  xor     r8d, r8d
0x1800d4c89  mov     word ptr [rbp+57h+Handle+2], ax
0x1800d4c8d  lea     rax, [rbp+57h+arg_10]
0x1800d4c91  mov     [rsp+0C0h+var_A0], rax
0x1800d4c96  call    ZwSetValueKey
0x1800d4c9b  mov     ebx, eax
0x1800d4c9d  test    eax, eax
0x1800d4c9f  jns     short loc_1800D4CA9
0x1800d4ca1  mov     rcx, rdi
0x1800d4ca4  call    NtDeleteKey
0x1800d4ca9  mov     rcx, [rbp+57h+arg_0]; Handle
0x1800d4cad  call    NtClose
0x1800d4cb2  test    ebx, ebx
0x1800d4cb4  js      short loc_1800D4CFA
0x1800d4cb6  mov     rax, [rbp+57h+arg_18]
0x1800d4cba  mov     [rax], rdi
0x1800d4cbd  jmp     loc_1800D4B57
0x1800d4cc2  mov     rax, [rbp+57h+arg_0]
0x1800d4cc6  lea     rcx, [rbp+57h+Handle]
0x1800d4cca  mov     r8, r13
0x1800d4ccd  mov     [rbp+57h+Handle], rax
0x1800d4cd1  mov     edx, esi
0x1800d4cd3  call    RtlpProcessIFEOKeyFilter
0x1800d4cd8  mov     rdi, [rbp+57h+Handle]
0x1800d4cdc  mov     ebx, eax
0x1800d4cde  test    eax, eax
0x1800d4ce0  js      short loc_1800D4CFA
0x1800d4ce2  mov     rdx, [rbp+57h+arg_0]
0x1800d4ce6  cmp     rdi, rdx
0x1800d4ce9  jnz     short loc_1800D4CB6
0x1800d4ceb  test    r12b, r12b
0x1800d4cee  jz      short loc_1800D4CB6
0x1800d4cf0  test    r14b, r14b
0x1800d4cf3  jz      short loc_1800D4CB6
0x1800d4cf5  jmp     loc_1800D4BC6
0x1800d4cfa  test    rdi, rdi
0x1800d4cfd  jz      loc_1800D4B57
0x1800d4d03  mov     rcx, rdi; Handle
0x1800d4d06  call    NtClose
0x1800d4d0b  jmp     loc_1800D4B57
0x1800d4d10  mov     ebx, 0C0000106h
0x1800d4d15  jmp     short loc_1800D4CA1
```
