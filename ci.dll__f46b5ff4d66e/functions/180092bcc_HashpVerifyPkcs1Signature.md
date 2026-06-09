# HashpVerifyPkcs1Signature

- ea: `0x180092bcc`
- end: `0x180092e99`
- name: `HashpVerifyPkcs1Signature`
- size: `717`
- prototype: `__int64 __fastcall(int, int, int, __int64, unsigned __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180076788`
- `0x180092948`

## callees

- `0x180005d90`
- `0x180006298`
- `0x180006c60`
- `0x18000c454`
- `0x18000c4f8`
- `0x18000c5a0`
- `0x18000c5e0`
- `0x18000cf60`
- `0x18000dfd4`
- `0x18000e0a8`
- `0x18000f2f8`
- `0x180092bcc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180092e46`
- `ntoskrnl!ExAllocatePool2` at `0x180092e46`
- `ntoskrnl!ExFreePoolWithTag` at `0x180092e88`
- `ntoskrnl!ExFreePoolWithTag` at `0x180092e88`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180092c0e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180092c0e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180092de8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180092de8`

## pseudocode

```c
__int64 __fastcall HashpVerifyPkcs1Signature(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        unsigned __int64 a9,
        char a10)
{
  char v10; // r12
  char *Pool2; // rax
  void *v14; // rdi
  unsigned __int64 v15; // rsi
  char *v16; // r14
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rbp
  unsigned int v20; // r15d
  __int64 v21; // rsi
  __int64 v22; // r9
  int v23; // ecx
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  __int64 *v27; // rax
  unsigned int v28; // ebx
  int v30; // ebx
  int v31; // [rsp+28h] [rbp-80h]
  __int64 v32; // [rsp+38h] [rbp-70h]
  __int64 v33; // [rsp+38h] [rbp-70h]
  __int64 v34; // [rsp+50h] [rbp-58h] BYREF
  _DWORD v35[20]; // [rsp+58h] [rbp-50h] BYREF

  v10 = byte_180048F04;
  v34 = 0;
  if ( byte_180048F04 )
    Pool2 = (char *)ExAllocateFromPagedLookasideList(&Lookaside);
  else
    Pool2 = (char *)ExAllocatePool2(258, 2592, 1919109443);
  v14 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741801;
  if ( a5 <= 8 )
  {
    v15 = (unsigned __int64)(Pool2 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
    v16 = &Pool2[-v15];
    v17 = SymCryptDigitsFromBits(4096);
    v18 = SymCryptIntCreate(v15, v16 + 2592, v17);
    v19 = v18;
    if ( v18 )
    {
      SymCryptIntSetValue(a6, a7, 2, v18);
      v20 = SymCryptIntBitsizeOfValue(v19);
      SymCryptIntWipe(v19);
      if ( v20 >= 0x400 )
      {
        v35[1] = v20;
        v35[0] = 1;
        v35[3] = 1;
        v35[2] = 0;
        v21 = SymCryptRsakeyCreate(v15, (__int64)(v16 + 2592), v35);
        if ( v21 )
        {
          if ( !(unsigned int)SymCryptLoadMsbFirstUint64(a4, a5, &v34)
            && !(unsigned int)SymCryptRsakeySetValue(a6, a7, (__int64)&v34, v22, 0, 0, 0, v32, 4096, v21)
            && a9 == (unsigned int)SymCryptRsakeySizeofModulus(v21) )
          {
            v23 = 0;
            if ( (a10 & 1) != 0 )
              v23 = 2;
            v24 = a1 - 32771;
            if ( !v24 )
            {
              v27 = &SymCryptMd5OidList;
              goto LABEL_17;
            }
            v25 = v24 - 1;
            if ( !v25 )
            {
              v27 = &SymCryptSha1OidList;
              goto LABEL_17;
            }
            v26 = v25 - 8;
            if ( !v26 )
            {
              v27 = &SymCryptSha256OidList;
LABEL_17:
              v28 = (unsigned int)SymCryptRsaPkcs1Verify(v21, a2, a3, a8, a9, v31, (__int64)v27, v33, v23) != 0
                  ? 0xC0000428
                  : 0;
LABEL_18:
              SymCryptRsakeyWipe(v21);
              goto LABEL_19;
            }
            v30 = v26 - 1;
            if ( !v30 )
            {
              v27 = &SymCryptSha384OidList;
              goto LABEL_17;
            }
            if ( v30 == 1 )
            {
              v27 = &SymCryptSha512OidList;
              goto LABEL_17;
            }
          }
          v28 = -1073740760;
          goto LABEL_18;
        }
      }
    }
  }
  v28 = -1073740760;
LABEL_19:
  if ( v10 )
    ExFreeToPagedLookasideList(&Lookaside, v14);
  else
    ExFreePoolWithTag(v14, 0x72634943u);
  return v28;
}

```

## disassembly

```asm
0x180092bcc  mov     rax, rsp
0x180092bcf  mov     [rax+8], rbx
0x180092bd3  mov     [rax+18h], r8
0x180092bd7  mov     [rax+10h], rdx
0x180092bdb  push    rbp
0x180092bdc  push    rsi
0x180092bdd  push    rdi
0x180092bde  push    r12
0x180092be0  push    r13
0x180092be2  push    r14
0x180092be4  push    r15
0x180092be6  sub     rsp, 70h
0x180092bea  mov     r12b, cs:byte_180048F04
0x180092bf1  mov     r13, r9
0x180092bf4  mov     qword ptr [rax-58h], 0
0x180092bfc  mov     ebx, ecx
0x180092bfe  test    r12b, r12b
0x180092c01  jz      loc_180092E36
0x180092c07  lea     rcx, Lookaside; Lookaside
0x180092c0e  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180092c15  nop     dword ptr [rax+rax+00h]
0x180092c1a  mov     rdi, rax
0x180092c1d  test    rax, rax
0x180092c20  jz      loc_180092E57
0x180092c26  cmp     [rsp+0A8h+arg_20], 8
0x180092c2f  ja      loc_180092E5E
0x180092c35  lea     rsi, [rax+1Fh]
0x180092c39  mov     r14, rax
0x180092c3c  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180092c40  mov     ecx, 1000h
0x180092c45  sub     r14, rsi
0x180092c48  call    SymCryptDigitsFromBits
0x180092c4d  mov     r8d, eax
0x180092c50  lea     rdx, [r14+0A20h]
0x180092c57  mov     rcx, rsi
0x180092c5a  call    SymCryptIntCreate
0x180092c5f  mov     rbp, rax
0x180092c62  test    rax, rax
0x180092c65  jz      loc_180092E5E
0x180092c6b  mov     rdx, [rsp+0A8h+arg_30]
0x180092c73  mov     r9, rax
0x180092c76  mov     rcx, [rsp+0A8h+arg_28]
0x180092c7e  mov     r8d, 2
0x180092c84  call    SymCryptIntSetValue
0x180092c89  mov     rcx, rbp
0x180092c8c  call    SymCryptIntBitsizeOfValue
0x180092c91  mov     rcx, rbp
0x180092c94  mov     r15d, eax
0x180092c97  call    SymCryptIntWipe
0x180092c9c  cmp     r15d, 400h
0x180092ca3  jb      loc_180092E5E
0x180092ca9  mov     ebp, 1
0x180092cae  mov     [rsp+0A8h+var_4C], r15d
0x180092cb3  lea     r8, [rsp+0A8h+var_50]
0x180092cb8  mov     [rsp+0A8h+var_50], ebp
0x180092cbc  lea     rdx, [r14+0A20h]
0x180092cc3  mov     [rsp+0A8h+var_44], ebp
0x180092cc7  mov     rcx, rsi
0x180092cca  mov     [rsp+0A8h+var_48], 0
0x180092cd2  call    SymCryptRsakeyCreate
0x180092cd7  mov     rsi, rax
0x180092cda  test    rax, rax
0x180092cdd  jz      loc_180092E5E
0x180092ce3  mov     rdx, [rsp+0A8h+arg_20]
0x180092ceb  lea     r8, [rsp+0A8h+var_58]
0x180092cf0  mov     rcx, r13
0x180092cf3  call    SymCryptLoadMsbFirstUint64
0x180092cf8  test    eax, eax
0x180092cfa  jnz     loc_180092E13
0x180092d00  mov     rdx, [rsp+0A8h+arg_30]
0x180092d08  lea     r8, [rsp+0A8h+var_58]
0x180092d0d  mov     rcx, [rsp+0A8h+arg_28]
0x180092d15  mov     [rsp+0A8h+var_60], rsi
0x180092d1a  mov     [rsp+0A8h+var_68], 1000h
0x180092d22  mov     dword ptr [rsp+0A8h+var_78], eax
0x180092d26  mov     [rsp+0A8h+var_80], 0
0x180092d2f  mov     [rsp+0A8h+var_88], 0
0x180092d38  call    SymCryptRsakeySetValue
0x180092d3d  test    eax, eax
0x180092d3f  jnz     loc_180092E13
0x180092d45  mov     rcx, rsi
0x180092d48  call    SymCryptRsakeySizeofModulus
0x180092d4d  mov     rdx, [rsp+0A8h+arg_40]
0x180092d55  mov     ecx, eax
0x180092d57  cmp     rdx, rcx
0x180092d5a  jnz     loc_180092E13
0x180092d60  xor     ecx, ecx
0x180092d62  lea     eax, [rbp+1]
0x180092d65  test    [rsp+0A8h+arg_48], bpl
0x180092d6d  cmovnz  ecx, eax
0x180092d70  sub     ebx, 8003h
0x180092d76  jz      loc_180092E74
0x180092d7c  sub     ebx, ebp
0x180092d7e  jz      loc_180092E1A
0x180092d84  sub     ebx, 8
0x180092d87  jnz     loc_180092E26
0x180092d8d  lea     rax, SymCryptSha256OidList
0x180092d94  mov     r9, [rsp+0A8h+arg_38]
0x180092d9c  mov     r8, [rsp+0A8h+arg_10]
0x180092da4  mov     [rsp+0A8h+var_68], ecx
0x180092da8  mov     rcx, rsi
0x180092dab  mov     [rsp+0A8h+var_78], rax
0x180092db0  mov     [rsp+0A8h+var_88], rdx
0x180092db5  mov     rdx, [rsp+0A8h+arg_8]
0x180092dbd  call    SymCryptRsaPkcs1Verify
0x180092dc2  neg     eax
0x180092dc4  mov     ebx, 0C0000428h
0x180092dc9  sbb     edx, edx
0x180092dcb  and     ebx, edx
0x180092dcd  mov     rcx, rsi
0x180092dd0  call    SymCryptRsakeyWipe
0x180092dd5  test    r12b, r12b
0x180092dd8  jz      loc_180092E80
0x180092dde  mov     rdx, rdi; Entry
0x180092de1  lea     rcx, Lookaside; Lookaside
0x180092de8  call    cs:__imp_ExFreeToPagedLookasideList
0x180092def  nop     dword ptr [rax+rax+00h]
0x180092df4  mov     eax, ebx
0x180092df6  mov     rbx, [rsp+0A8h+arg_0]
0x180092dfe  add     rsp, 70h
0x180092e02  pop     r15
0x180092e04  pop     r14
0x180092e06  pop     r13
0x180092e08  pop     r12
0x180092e0a  pop     rdi
0x180092e0b  pop     rsi
0x180092e0c  pop     rbp
0x180092e0d  retn
0x180092e0f  cmp     ebx, ebp
0x180092e11  jz      short loc_180092E68
0x180092e13  mov     ebx, 0C0000428h
0x180092e18  jmp     short loc_180092DCD
0x180092e1a  lea     rax, SymCryptSha1OidList
0x180092e21  jmp     loc_180092D94
0x180092e26  sub     ebx, ebp
0x180092e28  jnz     short loc_180092E0F
0x180092e2a  lea     rax, SymCryptSha384OidList
0x180092e31  jmp     loc_180092D94
0x180092e36  mov     edx, 0A20h
0x180092e3b  mov     ecx, 102h
0x180092e40  mov     r8d, 72634943h
0x180092e46  call    cs:__imp_ExAllocatePool2
0x180092e4d  nop     dword ptr [rax+rax+00h]
0x180092e52  jmp     loc_180092C1A
0x180092e57  mov     ebx, 0C0000017h
0x180092e5c  jmp     short loc_180092DF4
0x180092e5e  mov     ebx, 0C0000428h
0x180092e63  jmp     loc_180092DD5
0x180092e68  lea     rax, SymCryptSha512OidList
0x180092e6f  jmp     loc_180092D94
0x180092e74  lea     rax, SymCryptMd5OidList
0x180092e7b  jmp     loc_180092D94
0x180092e80  mov     edx, 72634943h; Tag
0x180092e85  mov     rcx, rdi; P
0x180092e88  call    cs:__imp_ExFreePoolWithTag
0x180092e8f  nop     dword ptr [rax+rax+00h]
0x180092e94  jmp     loc_180092DF4
```
