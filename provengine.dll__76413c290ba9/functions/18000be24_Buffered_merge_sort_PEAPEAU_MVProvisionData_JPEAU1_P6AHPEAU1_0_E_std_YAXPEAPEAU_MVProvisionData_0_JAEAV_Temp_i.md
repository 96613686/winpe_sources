# ??$_Buffered_merge_sort@PEAPEAU_MVProvisionData@@_JPEAU1@P6AHPEAU1@0@_E@std@@YAXPEAPEAU_MVProvisionData@@0_JAEAV?$_Temp_iterator@PEAU_MVProvisionData@@@0@P6AHPEAU1@3@_E@Z

- ea: `0x18000be24`
- end: `0x18000c06e`
- name: `??$_Buffered_merge_sort@PEAPEAU_MVProvisionData@@_JPEAU1@P6AHPEAU1@0@_E@std@@YAXPEAPEAU_MVProvisionData@@0_JAEAV?$_Temp_iterator@PEAU_MVProvisionData@@@0@P6AHPEAU1@3@_E@Z`
- size: `586`
- prototype: `void *__fastcall(char *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000efa4`

## callees

- `0x18000be24`
- `0x18000ecfc`
- `0x18000ed94`
- `0x18000ee30`
- `0x18004370e`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000bf1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bf7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bf8a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bf1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bf7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bf8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void *__fastcall ____Buffered_merge_sort_PEAPEAU_MVProvisionData___JPEAU1_P6AHPEAU1_0__E_std__YAXPEAPEAU_MVProvisionData__0_JAEAV___Temp_iterator_PEAU_MVProvisionData___0_P6AHPEAU1_3__E_Z(
        char *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // r13
  __int64 v6; // r12
  char *v7; // r15
  __int64 v8; // rsi
  __int64 i; // rdi
  char *v10; // rbx
  void *result; // rax
  __int64 v12; // r9
  __int64 v13; // rbx
  _QWORD *v14; // r10
  __int64 v15; // r15
  int v16; // esi
  __int64 v17; // r13
  __int64 v18; // r15
  char **v19; // rax
  char *v20; // rsi
  char *v21; // rcx
  __int64 v22; // r13
  char *v23; // rax
  char *v24; // rbx
  _QWORD *v25; // rdx
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // [rsp+90h] [rbp-29h]
  void *v29[14]; // [rsp+98h] [rbp-21h] BYREF
  char *v30; // [rsp+118h] [rbp+5Fh]

  v30 = a1;
  v4 = a4;
  v6 = a2;
  v7 = a1;
  v8 = a3;
  for ( i = 32; v8 >= 32; v8 -= 32 )
  {
    v10 = a1 + 256;
    ____Insertion_sort_PEAPEAU_MVProvisionData__P6AHPEAU1_0__E_std__YAXPEAPEAU_MVProvisionData__0P6AHPEAU1_1__E_Z(a1);
    a1 = v10;
  }
  result = (void *)____Insertion_sort_PEAPEAU_MVProvisionData__P6AHPEAU1_0__E_std__YAXPEAPEAU_MVProvisionData__0P6AHPEAU1_1__E_Z(a1);
  if ( a3 > 32 )
  {
    do
    {
      *(_QWORD *)(*(_QWORD *)(v4 + 32) + 8LL) = **(_QWORD **)(v4 + 32);
      v12 = *(_QWORD *)(v4 + 32);
      v13 = a3;
      v14 = v7;
      v15 = 2 * i;
      v16 = 8 * i;
      if ( 2 * i <= a3 )
      {
        do
        {
          v17 = (__int64)&v14[2 * i];
          v12 = *(_QWORD *)(____Merge_PEAPEAU_MVProvisionData__PEAPEAU1_V___Temp_iterator_PEAU_MVProvisionData___std__P6AHPEAU1_0__E_std__YA_AV___Temp_iterator_PEAU_MVProvisionData___0_PEAPEAU_MVProvisionData__000V10_P6AHPEAU2_2__E_Z(
                              (unsigned int)v29,
                              (_DWORD)v14,
                              v16 + (int)v14,
                              v16 + (int)v14,
                              v17)
                          + 32);
          v28 = v12;
          if ( v29[0] )
          {
            operator delete(v29[0]);
            v12 = v28;
          }
          v14 = (_QWORD *)v17;
          v13 -= v15;
        }
        while ( v15 <= v13 );
        v4 = a4;
      }
      if ( v13 <= i )
      {
        while ( v14 != (_QWORD *)v6 )
        {
          v25 = *(_QWORD **)(v12 + 8);
          v26 = *(_QWORD *)(v12 + 16);
          *v25 = *v14;
          v27 = *(_QWORD *)(v12 + 8) + 8LL;
          *(_QWORD *)(v12 + 8) = v27;
          if ( (unsigned __int64)v25 >= v26 )
            *(_QWORD *)(v12 + 16) = v27;
          ++v14;
        }
      }
      else
      {
        ____Merge_PEAPEAU_MVProvisionData__PEAPEAU1_V___Temp_iterator_PEAU_MVProvisionData___std__P6AHPEAU1_0__E_std__YA_AV___Temp_iterator_PEAU_MVProvisionData___0_PEAPEAU_MVProvisionData__000V10_P6AHPEAU2_2__E_Z(
          (unsigned int)v29,
          (_DWORD)v14,
          v16 + (_DWORD)v14,
          v16 + (_DWORD)v14,
          v6);
        if ( v29[0] )
          operator delete(v29[0]);
      }
      v18 = 2 * i;
      v19 = *(char ***)(v4 + 32);
      v20 = v19[1];
      v21 = *v19;
      v22 = a3;
      v23 = v30;
      i *= 4;
      if ( i <= a3 )
      {
        do
        {
          v24 = &v21[16 * v18];
          v23 = (char *)____Merge_PEAPEAU_MVProvisionData__PEAPEAU1_PEAPEAU1_P6AHPEAU1_0__E_std__YAPEAPEAU_MVProvisionData__PEAPEAU1_0000P6AHPEAU1_1__E_Z(
                          v21,
                          v23);
          v21 = v24;
          v22 -= i;
        }
        while ( i <= v22 );
      }
      if ( v22 > v18 )
        result = (void *)____Merge_PEAPEAU_MVProvisionData__PEAPEAU1_PEAPEAU1_P6AHPEAU1_0__E_std__YAPEAPEAU_MVProvisionData__PEAPEAU1_0000P6AHPEAU1_1__E_Z(
                           v21,
                           v23);
      else
        result = memmove_0(v23, v21, (v20 - v21) & 0xFFFFFFFFFFFFFFF8uLL);
      v6 = a2;
      v7 = v30;
      v4 = a4;
    }
    while ( i < a3 );
  }
  return result;
}

```

## disassembly

```asm
0x18000be24  mov     rax, rsp
0x18000be27  mov     [rax+20h], r9
0x18000be2b  mov     [rax+10h], rdx
0x18000be2f  mov     [rax+8], rcx
0x18000be33  push    rbp
0x18000be34  push    rbx
0x18000be35  push    rsi
0x18000be36  push    rdi
0x18000be37  push    r12
0x18000be39  push    r13
0x18000be3b  push    r14
0x18000be3d  push    r15
0x18000be3f  lea     rbp, [rax-57h]
0x18000be43  sub     rsp, 0C8h
0x18000be4a  mov     r13, r9
0x18000be4d  mov     r14, r8
0x18000be50  mov     r12, rdx
0x18000be53  mov     r15, rcx
0x18000be56  mov     rsi, r8
0x18000be59  mov     edi, 20h ; ' '
0x18000be5e  cmp     r8, rdi
0x18000be61  jl      short loc_18000BE7D
0x18000be63  lea     rbx, [rcx+100h]
0x18000be6a  mov     rdx, rbx
0x18000be6d  call    ??$_Insertion_sort@PEAPEAU_MVProvisionData@@P6AHPEAU1@0@_E@std@@YAXPEAPEAU_MVProvisionData@@0P6AHPEAU1@1@_E@Z
0x18000be72  mov     rcx, rbx; Src
0x18000be75  sub     rsi, rdi
0x18000be78  cmp     rsi, rdi
0x18000be7b  jge     short loc_18000BE63
0x18000be7d  mov     rdx, r12
0x18000be80  call    ??$_Insertion_sort@PEAPEAU_MVProvisionData@@P6AHPEAU1@0@_E@std@@YAXPEAPEAU_MVProvisionData@@0P6AHPEAU1@1@_E@Z
0x18000be85  cmp     r14, rdi
0x18000be88  jle     loc_18000C05A
0x18000be8e  mov     rcx, [r13+20h]
0x18000be92  mov     rax, [rcx]
0x18000be95  mov     [rcx+8], rax
0x18000be99  xorps   xmm0, xmm0
0x18000be9c  movdqu  [rbp+4Fh+var_98], xmm0
0x18000bea1  xorps   xmm1, xmm1
0x18000bea4  movdqu  [rbp+4Fh+var_88], xmm1
0x18000bea9  mov     r9, [r13+20h]
0x18000bead  mov     [rbp+4Fh+var_78], r9
0x18000beb1  lea     rax, [rbp+4Fh+var_98]
0x18000beb5  mov     [rbp+4Fh+arg_10], rax
0x18000beb9  mov     rbx, r14
0x18000bebc  mov     r10, r15
0x18000bebf  lea     r15, [rdi+rdi]
0x18000bec3  lea     rsi, ds:0[rdi*8]
0x18000becb  cmp     r15, r14
0x18000bece  jg      short loc_18000BF33
0x18000bed0  lea     r8, [rsi+r10]
0x18000bed4  lea     r13, [r10+rsi*2]
0x18000bed8  xorps   xmm0, xmm0
0x18000bedb  movdqu  [rbp+4Fh+var_C0], xmm0
0x18000bee0  xorps   xmm1, xmm1
0x18000bee3  movdqu  [rbp+4Fh+var_B0], xmm1
0x18000bee8  mov     [rbp+4Fh+var_A0], r9
0x18000beec  lea     rax, [rbp+4Fh+var_C0]
0x18000bef0  mov     [rsp+28h], rax
0x18000bef5  mov     [rsp+100h+var_E0], r13
0x18000befa  mov     r9, r8
0x18000befd  mov     rdx, r10
0x18000bf00  lea     rcx, [rbp+4Fh+var_70]
0x18000bf04  call    ??$_Merge@PEAPEAU_MVProvisionData@@PEAPEAU1@V?$_Temp_iterator@PEAU_MVProvisionData@@@std@@P6AHPEAU1@0@_E@std@@YA?AV?$_Temp_iterator@PEAU_MVProvisionData@@@0@PEAPEAU_MVProvisionData@@000V10@P6AHPEAU2@2@_E@Z
0x18000bf09  mov     r9, [rax+20h]
0x18000bf0d  mov     [rbp+4Fh+var_78], r9
0x18000bf11  mov     rcx, [rbp+4Fh+var_70]
0x18000bf15  test    rcx, rcx
0x18000bf18  jz      short loc_18000BF24
0x18000bf1a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bf20  mov     r9, [rbp+4Fh+var_78]
0x18000bf24  mov     r10, r13
0x18000bf27  sub     rbx, r15
0x18000bf2a  cmp     r15, rbx
0x18000bf2d  jle     short loc_18000BED0
0x18000bf2f  mov     r13, [rbp+4Fh+arg_18]
0x18000bf33  cmp     rbx, rdi
0x18000bf36  jle     loc_18000C003
0x18000bf3c  lea     r8, [rsi+r10]
0x18000bf40  xorps   xmm0, xmm0
0x18000bf43  movdqu  [rbp+4Fh+var_C0], xmm0
0x18000bf48  xorps   xmm1, xmm1
0x18000bf4b  movdqu  [rbp+4Fh+var_B0], xmm1
0x18000bf50  mov     [rbp+4Fh+var_A0], r9
0x18000bf54  lea     rax, [rbp+4Fh+var_C0]
0x18000bf58  mov     [rsp+28h], rax
0x18000bf5d  mov     [rsp+100h+var_E0], r12
0x18000bf62  mov     r9, r8
0x18000bf65  mov     rdx, r10
0x18000bf68  lea     rcx, [rbp+4Fh+var_70]
0x18000bf6c  call    ??$_Merge@PEAPEAU_MVProvisionData@@PEAPEAU1@V?$_Temp_iterator@PEAU_MVProvisionData@@@std@@P6AHPEAU1@0@_E@std@@YA?AV?$_Temp_iterator@PEAU_MVProvisionData@@@0@PEAPEAU_MVProvisionData@@000V10@P6AHPEAU2@2@_E@Z
0x18000bf71  mov     rcx, [rbp+4Fh+var_70]
0x18000bf75  test    rcx, rcx
0x18000bf78  jz      short loc_18000BF81
0x18000bf7a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bf80  nop
0x18000bf81  mov     rcx, qword ptr [rbp+4Fh+var_98]
0x18000bf85  test    rcx, rcx
0x18000bf88  jz      short loc_18000BF90
0x18000bf8a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bf90  lea     r15, [rdi+rdi]
0x18000bf94  mov     rax, [r13+20h]
0x18000bf98  mov     rsi, [rax+8]
0x18000bf9c  mov     rcx, [rax]; Src
0x18000bf9f  mov     r13, r14
0x18000bfa2  mov     rax, [rbp+4Fh+arg_0]
0x18000bfa6  lea     rdi, [r15+r15]
0x18000bfaa  cmp     rdi, r14
0x18000bfad  jg      short loc_18000C00D
0x18000bfaf  lea     r12, ds:0[r15*8]
0x18000bfb7  lea     rdx, [r12+rcx]
0x18000bfbb  lea     rbx, [rcx+r12*2]
0x18000bfbf  mov     [rsp+100h+var_E0], rax; void *
0x18000bfc4  mov     r9, rbx
0x18000bfc7  mov     r8, rdx
0x18000bfca  call    ??$_Merge@PEAPEAU_MVProvisionData@@PEAPEAU1@PEAPEAU1@P6AHPEAU1@0@_E@std@@YAPEAPEAU_MVProvisionData@@PEAPEAU1@0000P6AHPEAU1@1@_E@Z
0x18000bfcf  mov     rcx, rbx
0x18000bfd2  sub     r13, rdi
0x18000bfd5  cmp     rdi, r13
0x18000bfd8  jle     short loc_18000BFAF
0x18000bfda  jmp     short loc_18000C015
0x18000bfdc  mov     rdx, [r9+8]
0x18000bfe0  mov     rcx, [r9+10h]
0x18000bfe4  mov     rax, [r10]
0x18000bfe7  mov     [rdx], rax
0x18000bfea  mov     rax, [r9+8]
0x18000bfee  add     rax, 8
0x18000bff2  mov     [r9+8], rax
0x18000bff6  cmp     rdx, rcx
0x18000bff9  jb      short loc_18000BFFF
0x18000bffb  mov     [r9+10h], rax
0x18000bfff  add     r10, 8
0x18000c003  cmp     r10, r12
0x18000c006  jnz     short loc_18000BFDC
0x18000c008  jmp     loc_18000BF81
0x18000c00d  lea     r12, ds:0[r15*8]
0x18000c015  cmp     r13, r15
0x18000c018  jg      short loc_18000C031
0x18000c01a  sub     rsi, rcx
0x18000c01d  and     rsi, 0FFFFFFFFFFFFFFF8h
0x18000c021  mov     r8, rsi; Size
0x18000c024  mov     rdx, rcx; Src
0x18000c027  mov     rcx, rax; void *
0x18000c02a  call    memmove_0
0x18000c02f  jmp     short loc_18000C045
0x18000c031  lea     rdx, [r12+rcx]
0x18000c035  mov     [rsp+100h+var_E0], rax; void *
0x18000c03a  mov     r9, rsi
0x18000c03d  mov     r8, rdx
0x18000c040  call    ??$_Merge@PEAPEAU_MVProvisionData@@PEAPEAU1@PEAPEAU1@P6AHPEAU1@0@_E@std@@YAPEAPEAU_MVProvisionData@@PEAPEAU1@0000P6AHPEAU1@1@_E@Z
0x18000c045  cmp     rdi, r14
0x18000c048  mov     r12, [rbp+4Fh+arg_8]
0x18000c04c  mov     r15, [rbp+4Fh+arg_0]
0x18000c050  mov     r13, [rbp+4Fh+arg_18]
0x18000c054  jl      loc_18000BE8E
0x18000c05a  add     rsp, 0C8h
0x18000c061  pop     r15
0x18000c063  pop     r14
0x18000c065  pop     r13
0x18000c067  pop     r12
0x18000c069  pop     rdi
0x18000c06a  pop     rsi
0x18000c06b  pop     rbx
0x18000c06c  pop     rbp
0x18000c06d  retn
```
