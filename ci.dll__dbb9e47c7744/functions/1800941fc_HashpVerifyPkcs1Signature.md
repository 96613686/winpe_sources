# HashpVerifyPkcs1Signature

- ea: `0x1800941fc`
- end: `0x1800944c9`
- name: `HashpVerifyPkcs1Signature`
- size: `717`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180077d38`
- `0x180093f78`

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
- `0x1800941fc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180094476`
- `ntoskrnl!ExAllocatePool2` at `0x180094476`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800944b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800944b8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009423e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009423e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180094418`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180094418`

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

  v9 = byte_180049EF4;
  v30 = 0;
  if ( byte_180049EF4 )
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
0x1800941fc  mov     rax, rsp
0x1800941ff  mov     [rax+8], rbx
0x180094203  mov     [rax+18h], r8
0x180094207  mov     [rax+10h], rdx
0x18009420b  push    rbp
0x18009420c  push    rsi
0x18009420d  push    rdi
0x18009420e  push    r12
0x180094210  push    r13
0x180094212  push    r14
0x180094214  push    r15
0x180094216  sub     rsp, 70h
0x18009421a  mov     r12b, cs:byte_180049EF4
0x180094221  mov     r13, r9
0x180094224  mov     qword ptr [rax-58h], 0
0x18009422c  mov     ebx, ecx
0x18009422e  test    r12b, r12b
0x180094231  jz      loc_180094466
0x180094237  lea     rcx, Lookaside; Lookaside
0x18009423e  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180094245  nop     dword ptr [rax+rax+00h]
0x18009424a  mov     rdi, rax
0x18009424d  test    rax, rax
0x180094250  jz      loc_180094487
0x180094256  cmp     [rsp+0A8h+arg_20], 8
0x18009425f  ja      loc_18009448E
0x180094265  lea     rsi, [rax+1Fh]
0x180094269  mov     r14, rax
0x18009426c  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180094270  mov     ecx, 1000h
0x180094275  sub     r14, rsi
0x180094278  call    SymCryptDigitsFromBits
0x18009427d  mov     r8d, eax
0x180094280  lea     rdx, [r14+0A20h]
0x180094287  mov     rcx, rsi
0x18009428a  call    SymCryptIntCreate
0x18009428f  mov     rbp, rax
0x180094292  test    rax, rax
0x180094295  jz      loc_18009448E
0x18009429b  mov     rdx, [rsp+0A8h+arg_30]
0x1800942a3  mov     r9, rax
0x1800942a6  mov     rcx, [rsp+0A8h+arg_28]
0x1800942ae  mov     r8d, 2
0x1800942b4  call    SymCryptIntSetValue
0x1800942b9  mov     rcx, rbp
0x1800942bc  call    SymCryptIntBitsizeOfValue
0x1800942c1  mov     rcx, rbp
0x1800942c4  mov     r15d, eax
0x1800942c7  call    SymCryptIntWipe
0x1800942cc  cmp     r15d, 400h
0x1800942d3  jb      loc_18009448E
0x1800942d9  mov     ebp, 1
0x1800942de  mov     [rsp+0A8h+var_4C], r15d
0x1800942e3  lea     r8, [rsp+0A8h+var_50]
0x1800942e8  mov     [rsp+0A8h+var_50], ebp
0x1800942ec  lea     rdx, [r14+0A20h]
0x1800942f3  mov     [rsp+0A8h+var_44], ebp
0x1800942f7  mov     rcx, rsi
0x1800942fa  mov     [rsp+0A8h+var_48], 0
0x180094302  call    SymCryptRsakeyCreate
0x180094307  mov     rsi, rax
0x18009430a  test    rax, rax
0x18009430d  jz      loc_18009448E
0x180094313  mov     rdx, [rsp+0A8h+arg_20]
0x18009431b  lea     r8, [rsp+0A8h+var_58]
0x180094320  mov     rcx, r13
0x180094323  call    SymCryptLoadMsbFirstUint64
0x180094328  test    eax, eax
0x18009432a  jnz     loc_180094443
0x180094330  mov     rdx, [rsp+0A8h+arg_30]
0x180094338  lea     r8, [rsp+0A8h+var_58]
0x18009433d  mov     rcx, [rsp+0A8h+arg_28]
0x180094345  mov     [rsp+0A8h+var_60], rsi
0x18009434a  mov     [rsp+0A8h+var_68], 1000h
0x180094352  mov     dword ptr [rsp+0A8h+var_78], eax
0x180094356  mov     [rsp+0A8h+var_80], 0
0x18009435f  mov     [rsp+0A8h+var_88], 0
0x180094368  call    SymCryptRsakeySetValue
0x18009436d  test    eax, eax
0x18009436f  jnz     loc_180094443
0x180094375  mov     rcx, rsi
0x180094378  call    SymCryptRsakeySizeofModulus
0x18009437d  mov     rdx, [rsp+0A8h+arg_40]
0x180094385  mov     ecx, eax
0x180094387  cmp     rdx, rcx
0x18009438a  jnz     loc_180094443
0x180094390  xor     ecx, ecx
0x180094392  lea     eax, [rbp+1]
0x180094395  test    [rsp+0A8h+arg_48], bpl
0x18009439d  cmovnz  ecx, eax
0x1800943a0  sub     ebx, 8003h
0x1800943a6  jz      loc_1800944A4
0x1800943ac  sub     ebx, ebp
0x1800943ae  jz      loc_18009444A
0x1800943b4  sub     ebx, 8
0x1800943b7  jnz     loc_180094456
0x1800943bd  lea     rax, SymCryptSha256OidList
0x1800943c4  mov     r9, [rsp+0A8h+arg_38]
0x1800943cc  mov     r8, [rsp+0A8h+arg_10]
0x1800943d4  mov     [rsp+0A8h+var_68], ecx
0x1800943d8  mov     rcx, rsi
0x1800943db  mov     [rsp+0A8h+var_78], rax
0x1800943e0  mov     [rsp+0A8h+var_88], rdx
0x1800943e5  mov     rdx, [rsp+0A8h+arg_8]
0x1800943ed  call    SymCryptRsaPkcs1Verify
0x1800943f2  neg     eax
0x1800943f4  mov     ebx, 0C0000428h
0x1800943f9  sbb     edx, edx
0x1800943fb  and     ebx, edx
0x1800943fd  mov     rcx, rsi
0x180094400  call    SymCryptRsakeyWipe
0x180094405  test    r12b, r12b
0x180094408  jz      loc_1800944B0
0x18009440e  mov     rdx, rdi; Entry
0x180094411  lea     rcx, Lookaside; Lookaside
0x180094418  call    cs:__imp_ExFreeToPagedLookasideList
0x18009441f  nop     dword ptr [rax+rax+00h]
0x180094424  mov     eax, ebx
0x180094426  mov     rbx, [rsp+0A8h+arg_0]
0x18009442e  add     rsp, 70h
0x180094432  pop     r15
0x180094434  pop     r14
0x180094436  pop     r13
0x180094438  pop     r12
0x18009443a  pop     rdi
0x18009443b  pop     rsi
0x18009443c  pop     rbp
0x18009443d  retn
0x18009443f  cmp     ebx, ebp
0x180094441  jz      short loc_180094498
0x180094443  mov     ebx, 0C0000428h
0x180094448  jmp     short loc_1800943FD
0x18009444a  lea     rax, SymCryptSha1OidList
0x180094451  jmp     loc_1800943C4
0x180094456  sub     ebx, ebp
0x180094458  jnz     short loc_18009443F
0x18009445a  lea     rax, SymCryptSha384OidList
0x180094461  jmp     loc_1800943C4
0x180094466  mov     edx, 0A20h
0x18009446b  mov     ecx, 102h
0x180094470  mov     r8d, 72634943h
0x180094476  call    cs:__imp_ExAllocatePool2
0x18009447d  nop     dword ptr [rax+rax+00h]
0x180094482  jmp     loc_18009424A
0x180094487  mov     ebx, 0C0000017h
0x18009448c  jmp     short loc_180094424
0x18009448e  mov     ebx, 0C0000428h
0x180094493  jmp     loc_180094405
0x180094498  lea     rax, SymCryptSha512OidList
0x18009449f  jmp     loc_1800943C4
0x1800944a4  lea     rax, SymCryptMd5OidList
0x1800944ab  jmp     loc_1800943C4
0x1800944b0  mov     edx, 72634943h; Tag
0x1800944b5  mov     rcx, rdi; P
0x1800944b8  call    cs:__imp_ExFreePoolWithTag
0x1800944bf  nop     dword ptr [rax+rax+00h]
0x1800944c4  jmp     loc_180094424
```
