# HashpVerifyPkcs1Signature

- ea: `0x180099b5c`
- end: `0x180099e29`
- name: `HashpVerifyPkcs1Signature`
- size: `717`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180078018`
- `0x1800998d8`

## callees

- `0x180005da0`
- `0x1800062a8`
- `0x180006c70`
- `0x18000c464`
- `0x18000c508`
- `0x18000c5b0`
- `0x18000c5f0`
- `0x18000cf70`
- `0x18000dfe4`
- `0x18000e0b8`
- `0x18000f308`
- `0x180099b5c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180099dd6`
- `ntoskrnl!ExAllocatePool2` at `0x180099dd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099e18`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099e18`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180099b9e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180099b9e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180099d78`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180099d78`

## pseudocode

```c
__int64 __fastcall HashpVerifyPkcs1Signature(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        unsigned __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  char v9; // r12
  char *Pool2; // rax
  void *v13; // rdi
  unsigned __int64 v14; // rsi
  char *v15; // r14
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rbp
  unsigned int v19; // r15d
  __int64 v20; // rsi
  int v21; // r9d
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  __int64 *v25; // rax
  unsigned int v26; // ebx
  int v28; // ebx
  int v29; // [rsp+28h] [rbp-80h]
  __int64 v30; // [rsp+50h] [rbp-58h] BYREF
  _DWORD v31[20]; // [rsp+58h] [rbp-50h] BYREF

  v9 = byte_180049F0C;
  v30 = 0;
  if ( byte_180049F0C )
    Pool2 = (char *)ExAllocateFromPagedLookasideList(&Lookaside);
  else
    Pool2 = (char *)ExAllocatePool2(258, 2592, 1919109443);
  v13 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741801;
  if ( a5 <= 8 )
  {
    v14 = (unsigned __int64)(Pool2 + 31) & 0xFFFFFFFFFFFFFFE0uLL;
    v15 = &Pool2[-v14];
    v16 = SymCryptDigitsFromBits(4096);
    v17 = SymCryptIntCreate(v14, v15 + 2592, v16);
    v18 = v17;
    if ( v17 )
    {
      SymCryptIntSetValue(a6, a7, 2, v17);
      v19 = SymCryptIntBitsizeOfValue(v18);
      SymCryptIntWipe(v18);
      if ( v19 >= 0x400 )
      {
        v31[1] = v19;
        v31[0] = 1;
        v31[3] = 1;
        v31[2] = 0;
        v20 = SymCryptRsakeyCreate(v14, v15 + 2592, v31);
        if ( v20 )
        {
          if ( !(unsigned int)SymCryptLoadMsbFirstUint64(a4, a5, &v30)
            && !(unsigned int)SymCryptRsakeySetValue(a6, a7, (unsigned int)&v30, v21, 0, 0, 0)
            && a9 == (unsigned int)SymCryptRsakeySizeofModulus(v20) )
          {
            v22 = a1 - 32771;
            if ( !v22 )
            {
              v25 = &SymCryptMd5OidList;
              goto LABEL_15;
            }
            v23 = v22 - 1;
            if ( !v23 )
            {
              v25 = &SymCryptSha1OidList;
              goto LABEL_15;
            }
            v24 = v23 - 8;
            if ( !v24 )
            {
              v25 = &SymCryptSha256OidList;
LABEL_15:
              v26 = (unsigned int)SymCryptRsaPkcs1Verify(v20, a2, a3, a8, a9, v29, (__int64)v25) != 0 ? 0xC0000428 : 0;
LABEL_16:
              SymCryptRsakeyWipe(v20);
              goto LABEL_17;
            }
            v28 = v24 - 1;
            if ( !v28 )
            {
              v25 = &SymCryptSha384OidList;
              goto LABEL_15;
            }
            if ( v28 == 1 )
            {
              v25 = &SymCryptSha512OidList;
              goto LABEL_15;
            }
          }
          v26 = -1073740760;
          goto LABEL_16;
        }
      }
    }
  }
  v26 = -1073740760;
LABEL_17:
  if ( v9 )
    ExFreeToPagedLookasideList(&Lookaside, v13);
  else
    ExFreePoolWithTag(v13, 0x72634943u);
  return v26;
}

```

## disassembly

```asm
0x180099b5c  mov     rax, rsp
0x180099b5f  mov     [rax+8], rbx
0x180099b63  mov     [rax+18h], r8
0x180099b67  mov     [rax+10h], rdx
0x180099b6b  push    rbp
0x180099b6c  push    rsi
0x180099b6d  push    rdi
0x180099b6e  push    r12
0x180099b70  push    r13
0x180099b72  push    r14
0x180099b74  push    r15
0x180099b76  sub     rsp, 70h
0x180099b7a  mov     r12b, cs:byte_180049F0C
0x180099b81  mov     r13, r9
0x180099b84  mov     qword ptr [rax-58h], 0
0x180099b8c  mov     ebx, ecx
0x180099b8e  test    r12b, r12b
0x180099b91  jz      loc_180099DC6
0x180099b97  lea     rcx, Lookaside; Lookaside
0x180099b9e  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180099ba5  nop     dword ptr [rax+rax+00h]
0x180099baa  mov     rdi, rax
0x180099bad  test    rax, rax
0x180099bb0  jz      loc_180099DE7
0x180099bb6  cmp     [rsp+0A8h+arg_20], 8
0x180099bbf  ja      loc_180099DEE
0x180099bc5  lea     rsi, [rax+1Fh]
0x180099bc9  mov     r14, rax
0x180099bcc  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180099bd0  mov     ecx, 1000h
0x180099bd5  sub     r14, rsi
0x180099bd8  call    SymCryptDigitsFromBits
0x180099bdd  mov     r8d, eax
0x180099be0  lea     rdx, [r14+0A20h]
0x180099be7  mov     rcx, rsi
0x180099bea  call    SymCryptIntCreate
0x180099bef  mov     rbp, rax
0x180099bf2  test    rax, rax
0x180099bf5  jz      loc_180099DEE
0x180099bfb  mov     rdx, [rsp+0A8h+arg_30]
0x180099c03  mov     r9, rax
0x180099c06  mov     rcx, [rsp+0A8h+arg_28]
0x180099c0e  mov     r8d, 2
0x180099c14  call    SymCryptIntSetValue
0x180099c19  mov     rcx, rbp
0x180099c1c  call    SymCryptIntBitsizeOfValue
0x180099c21  mov     rcx, rbp
0x180099c24  mov     r15d, eax
0x180099c27  call    SymCryptIntWipe
0x180099c2c  cmp     r15d, 400h
0x180099c33  jb      loc_180099DEE
0x180099c39  mov     ebp, 1
0x180099c3e  mov     [rsp+0A8h+var_4C], r15d
0x180099c43  lea     r8, [rsp+0A8h+var_50]
0x180099c48  mov     [rsp+0A8h+var_50], ebp
0x180099c4c  lea     rdx, [r14+0A20h]
0x180099c53  mov     [rsp+0A8h+var_44], ebp
0x180099c57  mov     rcx, rsi
0x180099c5a  mov     [rsp+0A8h+var_48], 0
0x180099c62  call    SymCryptRsakeyCreate
0x180099c67  mov     rsi, rax
0x180099c6a  test    rax, rax
0x180099c6d  jz      loc_180099DEE
0x180099c73  mov     rdx, [rsp+0A8h+arg_20]
0x180099c7b  lea     r8, [rsp+0A8h+var_58]
0x180099c80  mov     rcx, r13
0x180099c83  call    SymCryptLoadMsbFirstUint64
0x180099c88  test    eax, eax
0x180099c8a  jnz     loc_180099DA3
0x180099c90  mov     rdx, [rsp+0A8h+arg_30]
0x180099c98  lea     r8, [rsp+0A8h+var_58]
0x180099c9d  mov     rcx, [rsp+0A8h+arg_28]
0x180099ca5  mov     [rsp+0A8h+var_60], rsi
0x180099caa  mov     [rsp+0A8h+var_68], 1000h
0x180099cb2  mov     dword ptr [rsp+0A8h+var_78], eax
0x180099cb6  mov     [rsp+0A8h+var_80], 0
0x180099cbf  mov     [rsp+0A8h+var_88], 0
0x180099cc8  call    SymCryptRsakeySetValue
0x180099ccd  test    eax, eax
0x180099ccf  jnz     loc_180099DA3
0x180099cd5  mov     rcx, rsi
0x180099cd8  call    SymCryptRsakeySizeofModulus
0x180099cdd  mov     rdx, [rsp+0A8h+arg_40]
0x180099ce5  mov     ecx, eax
0x180099ce7  cmp     rdx, rcx
0x180099cea  jnz     loc_180099DA3
0x180099cf0  xor     ecx, ecx
0x180099cf2  lea     eax, [rbp+1]
0x180099cf5  test    [rsp+0A8h+arg_48], bpl
0x180099cfd  cmovnz  ecx, eax
0x180099d00  sub     ebx, 8003h
0x180099d06  jz      loc_180099E04
0x180099d0c  sub     ebx, ebp
0x180099d0e  jz      loc_180099DAA
0x180099d14  sub     ebx, 8
0x180099d17  jnz     loc_180099DB6
0x180099d1d  lea     rax, SymCryptSha256OidList
0x180099d24  mov     r9, [rsp+0A8h+arg_38]
0x180099d2c  mov     r8, [rsp+0A8h+arg_10]
0x180099d34  mov     [rsp+0A8h+var_68], ecx
0x180099d38  mov     rcx, rsi
0x180099d3b  mov     [rsp+0A8h+var_78], rax
0x180099d40  mov     [rsp+0A8h+var_88], rdx
0x180099d45  mov     rdx, [rsp+0A8h+arg_8]
0x180099d4d  call    SymCryptRsaPkcs1Verify
0x180099d52  neg     eax
0x180099d54  mov     ebx, 0C0000428h
0x180099d59  sbb     edx, edx
0x180099d5b  and     ebx, edx
0x180099d5d  mov     rcx, rsi
0x180099d60  call    SymCryptRsakeyWipe
0x180099d65  test    r12b, r12b
0x180099d68  jz      loc_180099E10
0x180099d6e  mov     rdx, rdi; Entry
0x180099d71  lea     rcx, Lookaside; Lookaside
0x180099d78  call    cs:__imp_ExFreeToPagedLookasideList
0x180099d7f  nop     dword ptr [rax+rax+00h]
0x180099d84  mov     eax, ebx
0x180099d86  mov     rbx, [rsp+0A8h+arg_0]
0x180099d8e  add     rsp, 70h
0x180099d92  pop     r15
0x180099d94  pop     r14
0x180099d96  pop     r13
0x180099d98  pop     r12
0x180099d9a  pop     rdi
0x180099d9b  pop     rsi
0x180099d9c  pop     rbp
0x180099d9d  retn
0x180099d9f  cmp     ebx, ebp
0x180099da1  jz      short loc_180099DF8
0x180099da3  mov     ebx, 0C0000428h
0x180099da8  jmp     short loc_180099D5D
0x180099daa  lea     rax, SymCryptSha1OidList
0x180099db1  jmp     loc_180099D24
0x180099db6  sub     ebx, ebp
0x180099db8  jnz     short loc_180099D9F
0x180099dba  lea     rax, SymCryptSha384OidList
0x180099dc1  jmp     loc_180099D24
0x180099dc6  mov     edx, 0A20h
0x180099dcb  mov     ecx, 102h
0x180099dd0  mov     r8d, 72634943h
0x180099dd6  call    cs:__imp_ExAllocatePool2
0x180099ddd  nop     dword ptr [rax+rax+00h]
0x180099de2  jmp     loc_180099BAA
0x180099de7  mov     ebx, 0C0000017h
0x180099dec  jmp     short loc_180099D84
0x180099dee  mov     ebx, 0C0000428h
0x180099df3  jmp     loc_180099D65
0x180099df8  lea     rax, SymCryptSha512OidList
0x180099dff  jmp     loc_180099D24
0x180099e04  lea     rax, SymCryptMd5OidList
0x180099e0b  jmp     loc_180099D24
0x180099e10  mov     edx, 72634943h; Tag
0x180099e15  mov     rcx, rdi; P
0x180099e18  call    cs:__imp_ExFreePoolWithTag
0x180099e1f  nop     dword ptr [rax+rax+00h]
0x180099e24  jmp     loc_180099D84
```
