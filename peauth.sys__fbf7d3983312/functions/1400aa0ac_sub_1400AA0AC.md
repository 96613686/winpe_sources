# sub_1400AA0AC

- ea: `0x1400aa0ac`
- end: `0x1400aa333`
- name: `sub_1400AA0AC`
- size: `647`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400a893c`

## callees

- `0x140006ffc`
- `0x140007880`
- `0x140007a2c`
- `0x140007a44`
- `0x14000857c`
- `0x1400098ec`
- `0x14000991c`
- `0x14000995c`
- `0x140009a18`
- `0x140009b84`
- `0x14000ddd0`
- `0x140046e14`
- `0x1400aa0ac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa30c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa30c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400aa0ea`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400aa0ea`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400aa2f6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400aa2f6`

## pseudocode

```c
__int64 __fastcall sub_1400AA0AC(
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
  char v9; // r15
  __int64 v12; // rax
  void *v13; // rdi
  unsigned int v14; // ebx
  char *v15; // r14
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rbp
  unsigned int v19; // r12d
  __int64 v20; // rsi
  int v21; // r9d
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  __int64 *v26; // rax
  int v28; // [rsp+28h] [rbp-80h]
  __int64 v29; // [rsp+50h] [rbp-58h] BYREF
  _DWORD v30[20]; // [rsp+58h] [rbp-50h] BYREF

  v9 = byte_14003A801;
  v29 = 0;
  if ( byte_14003A801 )
    v12 = (__int64)ExAllocateFromPagedLookasideList(&Lookaside);
  else
    v12 = sub_140046E14(2592);
  v13 = (void *)v12;
  if ( !v12 )
    return (unsigned int)-1073741801;
  if ( a5 > 8 )
    goto LABEL_7;
  v15 = (char *)(v12 - ((v12 + 31) & 0xFFFFFFFFFFFFFFE0uLL));
  v16 = sub_1400098EC(4096);
  v17 = sub_14000991C(((unsigned __int64)v13 + 31) & 0xFFFFFFFFFFFFFFE0uLL, v15 + 2592, v16);
  v18 = v17;
  if ( !v17 )
    goto LABEL_7;
  sub_140009B84(a6, a7, 2, v17);
  v19 = sub_140009A18(v18);
  sub_14000995C(v18);
  if ( v19 < 0x400
    || (v30[1] = v19,
        v30[0] = 1,
        v30[3] = 1,
        v30[2] = 0,
        (v20 = sub_140007880(((unsigned __int64)v13 + 31) & 0xFFFFFFFFFFFFFFE0uLL, v15 + 2592, v30)) == 0) )
  {
LABEL_7:
    v14 = -1073740760;
    goto LABEL_27;
  }
  if ( !(unsigned int)sub_140006FFC(a4, a5, &v29)
    && !(unsigned int)sub_14000857C(a6, a7, (unsigned int)&v29, v21, 0, 0, 0)
    && a9 == (unsigned int)sub_140007A44(v20) )
  {
    v22 = a1 - 32771;
    if ( !v22 )
    {
      v26 = &qword_1400290F0;
      goto LABEL_25;
    }
    v23 = v22 - 1;
    if ( !v23 )
    {
      v26 = &qword_140029150;
      goto LABEL_25;
    }
    v24 = v23 - 8;
    if ( !v24 )
    {
      v26 = &qword_140029170;
      goto LABEL_25;
    }
    v25 = v24 - 1;
    if ( !v25 )
    {
      v26 = &qword_140029110;
      goto LABEL_25;
    }
    if ( v25 == 1 )
    {
      v26 = &qword_140029130;
LABEL_25:
      v14 = (unsigned int)sub_14000DDD0(v20, a2, a3, a8, a9, v28, (__int64)v26) != 0 ? 0xC0000428 : 0;
      goto LABEL_26;
    }
  }
  v14 = -1073740760;
LABEL_26:
  sub_140007A2C(v20);
LABEL_27:
  if ( v9 )
    ExFreeToPagedLookasideList(&Lookaside, v13);
  else
    ExFreePoolWithTag(v13, 0x72634943u);
  return v14;
}

```

## disassembly

```asm
0x1400aa0ac  mov     rax, rsp
0x1400aa0af  mov     [rax+8], rbx
0x1400aa0b3  mov     [rax+18h], r8
0x1400aa0b7  mov     [rax+10h], rdx
0x1400aa0bb  push    rbp
0x1400aa0bc  push    rsi
0x1400aa0bd  push    rdi
0x1400aa0be  push    r12
0x1400aa0c0  push    r13
0x1400aa0c2  push    r14
0x1400aa0c4  push    r15
0x1400aa0c6  sub     rsp, 70h
0x1400aa0ca  mov     r15b, cs:byte_14003A801
0x1400aa0d1  mov     r13, r9
0x1400aa0d4  mov     qword ptr [rax-58h], 0
0x1400aa0dc  mov     ebx, ecx
0x1400aa0de  test    r15b, r15b
0x1400aa0e1  jz      short loc_1400AA0F8
0x1400aa0e3  lea     rcx, Lookaside; Lookaside
0x1400aa0ea  call    cs:ExAllocateFromPagedLookasideList
0x1400aa0f1  nop     dword ptr [rax+rax+00h]
0x1400aa0f6  jmp     short loc_1400AA102
0x1400aa0f8  mov     ecx, 0A20h
0x1400aa0fd  call    sub_140046E14
0x1400aa102  mov     rdi, rax
0x1400aa105  test    rax, rax
0x1400aa108  jnz     short loc_1400AA114
0x1400aa10a  mov     ebx, 0C0000017h
0x1400aa10f  jmp     loc_1400AA318
0x1400aa114  cmp     [rsp+0A8h+arg_20], 8
0x1400aa11d  jbe     short loc_1400AA129
0x1400aa11f  mov     ebx, 0C0000428h
0x1400aa124  jmp     loc_1400AA2E7
0x1400aa129  lea     rsi, [rdi+1Fh]
0x1400aa12d  mov     r14, rdi
0x1400aa130  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1400aa134  mov     ecx, 1000h
0x1400aa139  sub     r14, rsi
0x1400aa13c  call    sub_1400098EC
0x1400aa141  mov     r8d, eax
0x1400aa144  lea     rdx, [r14+0A20h]
0x1400aa14b  mov     rcx, rsi
0x1400aa14e  call    sub_14000991C
0x1400aa153  mov     rbp, rax
0x1400aa156  test    rax, rax
0x1400aa159  jz      short loc_1400AA11F
0x1400aa15b  mov     rdx, [rsp+0A8h+arg_30]
0x1400aa163  mov     r9, rax
0x1400aa166  mov     rcx, [rsp+0A8h+arg_28]
0x1400aa16e  mov     r8d, 2
0x1400aa174  call    sub_140009B84
0x1400aa179  mov     rcx, rbp
0x1400aa17c  call    sub_140009A18
0x1400aa181  mov     rcx, rbp
0x1400aa184  mov     r12d, eax
0x1400aa187  call    sub_14000995C
0x1400aa18c  cmp     r12d, 400h
0x1400aa193  jb      short loc_1400AA11F
0x1400aa195  mov     ebp, 1
0x1400aa19a  mov     [rsp+0A8h+var_4C], r12d
0x1400aa19f  lea     r8, [rsp+0A8h+var_50]
0x1400aa1a4  mov     [rsp+0A8h+var_50], ebp
0x1400aa1a8  lea     rdx, [r14+0A20h]
0x1400aa1af  mov     [rsp+0A8h+var_44], ebp
0x1400aa1b3  mov     rcx, rsi
0x1400aa1b6  mov     [rsp+0A8h+var_48], 0
0x1400aa1be  call    sub_140007880
0x1400aa1c3  mov     rsi, rax
0x1400aa1c6  test    rax, rax
0x1400aa1c9  jz      loc_1400AA11F
0x1400aa1cf  mov     rdx, [rsp+0A8h+arg_20]
0x1400aa1d7  lea     r8, [rsp+0A8h+var_58]
0x1400aa1dc  mov     rcx, r13
0x1400aa1df  call    sub_140006FFC
0x1400aa1e4  test    eax, eax
0x1400aa1e6  jz      short loc_1400AA1F2
0x1400aa1e8  mov     ebx, 0C0000428h
0x1400aa1ed  jmp     loc_1400AA2DF
0x1400aa1f2  mov     rdx, [rsp+0A8h+arg_30]
0x1400aa1fa  lea     r8, [rsp+0A8h+var_58]
0x1400aa1ff  mov     rcx, [rsp+0A8h+arg_28]
0x1400aa207  mov     [rsp+0A8h+var_60], rsi
0x1400aa20c  mov     [rsp+0A8h+var_68], 1000h
0x1400aa214  mov     dword ptr [rsp+0A8h+var_78], 0
0x1400aa21c  mov     [rsp+0A8h+var_80], 0
0x1400aa225  mov     [rsp+0A8h+var_88], 0
0x1400aa22e  call    sub_14000857C
0x1400aa233  test    eax, eax
0x1400aa235  jnz     short loc_1400AA1E8
0x1400aa237  mov     rcx, rsi
0x1400aa23a  call    sub_140007A44
0x1400aa23f  mov     rdx, [rsp+0A8h+arg_40]
0x1400aa247  mov     ecx, eax
0x1400aa249  cmp     rdx, rcx
0x1400aa24c  jnz     short loc_1400AA1E8
0x1400aa24e  xor     ecx, ecx
0x1400aa250  test    [rsp+0A8h+arg_48], bpl
0x1400aa258  lea     eax, [rcx+2]
0x1400aa25b  cmovnz  ecx, eax
0x1400aa25e  sub     ebx, 8003h
0x1400aa264  jz      short loc_1400AA29F
0x1400aa266  sub     ebx, ebp
0x1400aa268  jz      short loc_1400AA296
0x1400aa26a  sub     ebx, 8
0x1400aa26d  jz      short loc_1400AA28D
0x1400aa26f  sub     ebx, ebp
0x1400aa271  jz      short loc_1400AA284
0x1400aa273  cmp     ebx, ebp
0x1400aa275  jnz     loc_1400AA1E8
0x1400aa27b  lea     rax, qword_140029130
0x1400aa282  jmp     short loc_1400AA2A6
0x1400aa284  lea     rax, qword_140029110
0x1400aa28b  jmp     short loc_1400AA2A6
0x1400aa28d  lea     rax, qword_140029170
0x1400aa294  jmp     short loc_1400AA2A6
0x1400aa296  lea     rax, qword_140029150
0x1400aa29d  jmp     short loc_1400AA2A6
0x1400aa29f  lea     rax, qword_1400290F0
0x1400aa2a6  mov     r9, [rsp+0A8h+arg_38]
0x1400aa2ae  mov     r8, [rsp+0A8h+arg_10]
0x1400aa2b6  mov     [rsp+0A8h+var_68], ecx
0x1400aa2ba  mov     rcx, rsi
0x1400aa2bd  mov     [rsp+0A8h+var_78], rax
0x1400aa2c2  mov     [rsp+0A8h+var_88], rdx
0x1400aa2c7  mov     rdx, [rsp+0A8h+arg_8]
0x1400aa2cf  call    sub_14000DDD0
0x1400aa2d4  neg     eax
0x1400aa2d6  mov     ebx, 0C0000428h
0x1400aa2db  sbb     edx, edx
0x1400aa2dd  and     ebx, edx
0x1400aa2df  mov     rcx, rsi
0x1400aa2e2  call    sub_140007A2C
0x1400aa2e7  test    r15b, r15b
0x1400aa2ea  jz      short loc_1400AA304
0x1400aa2ec  mov     rdx, rdi; Entry
0x1400aa2ef  lea     rcx, Lookaside; Lookaside
0x1400aa2f6  call    cs:ExFreeToPagedLookasideList
0x1400aa2fd  nop     dword ptr [rax+rax+00h]
0x1400aa302  jmp     short loc_1400AA318
0x1400aa304  mov     edx, 72634943h; Tag
0x1400aa309  mov     rcx, rdi; P
0x1400aa30c  call    cs:ExFreePoolWithTag
0x1400aa313  nop     dword ptr [rax+rax+00h]
0x1400aa318  mov     eax, ebx
0x1400aa31a  mov     rbx, [rsp+0A8h+arg_0]
0x1400aa322  add     rsp, 70h
0x1400aa326  pop     r15
0x1400aa328  pop     r14
0x1400aa32a  pop     r13
0x1400aa32c  pop     r12
0x1400aa32e  pop     rdi
0x1400aa32f  pop     rsi
0x1400aa330  pop     rbp
0x1400aa331  retn
```
