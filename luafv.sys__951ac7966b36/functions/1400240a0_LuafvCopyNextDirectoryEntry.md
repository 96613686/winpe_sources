# LuafvCopyNextDirectoryEntry

- ea: `0x1400240a0`
- end: `0x14002465b`
- name: `LuafvCopyNextDirectoryEntry`
- size: `1467`
- prototype: `char __fastcall(__int64, int, char, __int64, __int64, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400220ac`

## callees

- `0x140001b34`
- `0x140005f60`
- `0x140014008`
- `0x140014b8c`
- `0x140014bf0`
- `0x140014c8c`
- `0x140022704`
- `0x1400240a0`
- `0x140024664`

## pseudocode

```c
char __fastcall LuafvCopyNextDirectoryEntry(
        __int64 a1,
        int a2,
        char a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // r13
  char v9; // r12
  char v13; // si
  __int64 v14; // r10
  unsigned __int64 v15; // r9
  unsigned __int64 *v16; // rbx
  unsigned __int64 v17; // r8
  LONG v18; // eax
  bool v19; // zf
  int v20; // ecx
  char *v21; // rbx
  unsigned __int64 v22; // rcx
  int v23; // eax
  unsigned __int64 v24; // rcx
  int v25; // edx
  _BYTE *v26; // rbx
  int IsEnabledDeviceUsageNoInline; // r8d
  _OWORD *v29; // rcx
  __int64 v30; // rax
  void *v31; // rdx
  __int64 v32; // rbx
  int v33; // r8d
  _QWORD *v34; // rcx
  void *v35; // rdx
  int v36; // r8d
  _OWORD *v37; // rcx
  __int64 v38; // rax
  void *v39; // rdx
  int v40; // r8d
  _QWORD *v41; // rcx
  __int64 v42; // rax
  void *v43; // rdx
  int v44; // r8d
  _OWORD *v45; // rcx
  __int64 v46; // rax
  void *v47; // rdx
  int v48; // r8d
  _OWORD *v49; // rcx
  __int64 v50; // rax
  void *v51; // rdx
  int v52; // r9d
  _OWORD *v53; // rcx
  __int64 v54; // rax
  void *v55; // rdx
  int v56; // r9d
  _QWORD *v57; // rcx
  __int64 v58; // rax
  void *v59; // rdx
  int v60; // r9d
  _OWORD *v61; // rcx
  __int64 v62; // rax
  void *v63; // rdx
  int v64; // edi
  int v65; // edi
  int v66; // edi
  bool v67; // zf
  int v68; // edi
  int ULongFromUser; // eax
  int v70; // edi
  int v71; // edi
  int v72; // edi
  int v73[22]; // [rsp+50h] [rbp-58h] BYREF
  int v74; // [rsp+B0h] [rbp+8h] BYREF

  v8 = *(_QWORD *)(a1 + 96);
  v9 = 0;
  v73[0] = 0;
  v74 = 0;
  v13 = 0;
  LuafvQueryCommonDirectoryClass((unsigned int)a2, v73, &v74);
  v15 = *(_QWORD *)(v8 + 24);
  if ( !v15 || v15 >= *(_QWORD *)(v8 + 16) + (unsigned __int64)*(unsigned int *)(v8 + 12) )
  {
    v16 = (unsigned __int64 *)(v8 + 56);
    if ( !v15 )
      goto LABEL_29;
    goto LABEL_23;
  }
  v16 = (unsigned __int64 *)(v8 + 56);
  v17 = *(_QWORD *)(v8 + 56);
  if ( !v17 || v17 >= *(_QWORD *)(v8 + 48) + (unsigned __int64)*(unsigned int *)(v8 + 44) )
  {
LABEL_23:
    if ( v15 < *(_QWORD *)(v8 + 16) + (unsigned __int64)*(unsigned int *)(v8 + 12) && *v16 )
    {
      if ( *(_DWORD *)(v8 + 40) )
        goto LABEL_27;
      v22 = *v16;
      goto LABEL_30;
    }
LABEL_29:
    v22 = *v16;
    if ( !*v16 )
      return v13;
LABEL_30:
    if ( v22 >= *(_QWORD *)(v8 + 48) + (unsigned __int64)*(unsigned int *)(v8 + 44) || !v15 || !*(_DWORD *)(v8 + 8) )
      return v13;
    goto LABEL_33;
  }
  v18 = LuafvCompareDirectoryEntryName(v14, v73[0], v74);
  if ( v18 < 0 )
    goto LABEL_27;
  if ( v18 > 0 )
  {
LABEL_33:
    v24 = *v16;
    v25 = *(_DWORD *)((unsigned int)v74 + *v16);
    if ( ((v25 - 2) & 0xFFFFFFFD) == 0
      && *(_WORD *)((unsigned int)v73[0] + v24) == 46
      && (v25 == 2 || *(_WORD *)((unsigned int)v73[0] + v24 + 2) == 46) )
    {
      v13 = 1;
    }
    goto LABEL_38;
  }
  v9 = 1;
  if ( a2 > 60 )
  {
    if ( a2 != 63 && a2 != 78 && a2 != 79 )
    {
      v20 = a2 - 80;
      v19 = a2 == 80;
      goto LABEL_14;
    }
  }
  else if ( a2 != 60 && a2 != 1 && a2 != 2 && a2 != 3 )
  {
    if ( a2 == 12 )
      goto LABEL_38;
    v20 = a2 - 37;
    v19 = a2 == 37;
LABEL_14:
    if ( v19 || v20 == 1 )
      goto LABEL_16;
LABEL_27:
    v21 = (char *)a8;
    goto LABEL_28;
  }
LABEL_16:
  if ( (((unsigned __int8)*(_DWORD *)(*(_QWORD *)(v8 + 24) + 56LL) ^ *(_BYTE *)(*v16 + 56)) & 0x10) != 0 )
  {
    v21 = (char *)a8;
    LuafvCopyDirectoryEntry(v8 + 32, v73[0], v74, a3, (char *)a4, a5, 1, a6, 0, (char *)a8);
LABEL_28:
    v23 = 1;
LABEL_119:
    LuafvCopyDirectoryEntry(v8, v73[0], v74, a3, (char *)a4, a5, v13, a6, (_QWORD *)(a7 & -(__int64)(v23 != 0)), v21);
    return 1;
  }
LABEL_38:
  v26 = (_BYTE *)a8;
  LuafvCopyDirectoryEntry(v8 + 32, v73[0], v74, a3, (char *)a4, a5, v13, a6, (_QWORD *)a7, (char *)a8);
  if ( *v26 )
  {
    v9 = 0;
    goto LABEL_117;
  }
  if ( v13 )
    return 0;
  if ( !v9 )
    goto LABEL_99;
  if ( a2 == 3 || a2 == 37 )
  {
    IsEnabledDeviceUsageNoInline = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
    v29 = (_OWORD *)(a4 + 68);
    v30 = *(_QWORD *)(v8 + 24);
    if ( IsEnabledDeviceUsageNoInline )
    {
      v31 = (void *)(v30 + 68);
      if ( a3 )
        RtlCopyToUser(v29, v31, 0x19u);
      else
        RtlCopyVolatileMemory(v29, v31, 0x19u);
    }
    else
    {
      *v29 = *(_OWORD *)(v30 + 68);
      *(_OWORD *)(a4 + 77) = *(_OWORD *)(v30 + 77);
    }
  }
  if ( a2 == 37 || a2 == 38 )
  {
    v32 = 72;
    if ( a2 != 38 )
      v32 = 96;
    v33 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
    v34 = (_QWORD *)(v32 + a4);
    if ( v33 )
    {
      v35 = (void *)(v32 + *(_QWORD *)(v8 + 24));
      if ( a3 )
        RtlCopyToUser(v34, v35, 8u);
      else
        RtlCopyVolatileMemory(v34, v35, 8u);
    }
    else
    {
      *v34 = *(_QWORD *)(v32 + *(_QWORD *)(v8 + 24));
    }
  }
  if ( a2 != 78 )
  {
    if ( a2 != 79 )
      goto LABEL_70;
    v36 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
    v37 = (_OWORD *)(a4 + 80);
    v38 = *(_QWORD *)(v8 + 24);
    if ( v36 )
    {
      v39 = (void *)(v38 + 80);
      if ( a3 )
        RtlCopyToUser(v37, v39, 0x19u);
      else
        RtlCopyVolatileMemory(v37, v39, 0x19u);
    }
    else
    {
      *v37 = *(_OWORD *)(v38 + 80);
      *(_OWORD *)(a4 + 89) = *(_OWORD *)(v38 + 89);
    }
  }
  v40 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
  v41 = (_QWORD *)(a4 + 72);
  v42 = *(_QWORD *)(v8 + 24);
  if ( v40 )
  {
    v43 = (void *)(v42 + 72);
    if ( a3 )
      RtlCopyToUser(v41, v43, 8u);
    else
      RtlCopyVolatileMemory(v41, v43, 8u);
  }
  else
  {
    *v41 = *(_QWORD *)(v42 + 72);
  }
LABEL_70:
  if ( a2 == 60 )
  {
LABEL_77:
    v48 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
    v49 = (_OWORD *)(a4 + 72);
    v50 = *(_QWORD *)(v8 + 24);
    if ( v48 )
    {
      v51 = (void *)(v50 + 72);
      if ( a3 )
        RtlCopyToUser(v49, v51, 0x10u);
      else
        RtlCopyVolatileMemory(v49, v51, 0x10u);
    }
    else
    {
      *v49 = *(_OWORD *)(v50 + 72);
    }
    goto LABEL_82;
  }
  if ( a2 == 63 )
  {
    v44 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
    v45 = (_OWORD *)(a4 + 88);
    v46 = *(_QWORD *)(v8 + 24);
    if ( v44 )
    {
      v47 = (void *)(v46 + 88);
      if ( a3 )
        RtlCopyToUser(v45, v47, 0x19u);
      else
        RtlCopyVolatileMemory(v45, v47, 0x19u);
    }
    else
    {
      *v45 = *(_OWORD *)(v46 + 88);
      *(_OWORD *)(a4 + 97) = *(_OWORD *)(v46 + 97);
    }
    goto LABEL_77;
  }
LABEL_82:
  if ( a2 != 80 )
  {
    if ( a2 != 81 )
      goto LABEL_99;
    v52 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
    v53 = (_OWORD *)(a4 + 96);
    v54 = *(_QWORD *)(v8 + 24);
    if ( v52 )
    {
      v55 = (void *)(v54 + 96);
      if ( a3 )
        RtlCopyToUser(v53, v55, 0x19u);
      else
        RtlCopyVolatileMemory(v53, v55, 0x19u);
    }
    else
    {
      *v53 = *(_OWORD *)(v54 + 96);
      *(_OWORD *)(a4 + 105) = *(_OWORD *)(v54 + 105);
    }
  }
  v56 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
  v57 = (_QWORD *)(a4 + 72);
  v58 = *(_QWORD *)(v8 + 24);
  if ( v56 )
  {
    v59 = (void *)(v58 + 72);
    if ( a3 )
      RtlCopyToUser(v57, v59, 8u);
    else
      RtlCopyVolatileMemory(v57, v59, 8u);
  }
  else
  {
    *v57 = *(_QWORD *)(v58 + 72);
  }
  v60 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline();
  v61 = (_OWORD *)(a4 + 80);
  v62 = *(_QWORD *)(v8 + 24);
  if ( v60 )
  {
    v63 = (void *)(v62 + 80);
    if ( a3 )
      RtlCopyToUser(v61, v63, 0x10u);
    else
      RtlCopyVolatileMemory(v61, v63, 0x10u);
  }
  else
  {
    *v61 = *(_OWORD *)(v62 + 80);
  }
LABEL_99:
  if ( a2 > 60 )
  {
    v70 = a2 - 63;
    if ( !v70 )
      goto LABEL_107;
    v71 = v70 - 15;
    if ( !v71 )
      goto LABEL_107;
    v72 = v71 - 1;
    if ( !v72 )
      goto LABEL_107;
    v68 = v72 - 1;
    v67 = v68 == 0;
  }
  else
  {
    if ( a2 == 60 )
      goto LABEL_107;
    v64 = a2 - 1;
    if ( !v64 )
      goto LABEL_107;
    v65 = v64 - 1;
    if ( !v65 )
      goto LABEL_107;
    v66 = v65 - 1;
    if ( !v66 )
      goto LABEL_107;
    v68 = v66 - 34;
    v67 = v68 == 0;
  }
  if ( v67 || v68 == 1 )
  {
LABEL_107:
    if ( (unsigned int)Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( a3 )
      {
        ULongFromUser = RtlReadULongFromUser(a4 + 56);
        RtlWriteULongToUser(a4 + 56, ULongFromUser | 0x10000u);
      }
      else
      {
        *(_DWORD *)(a4 + 56) |= 0x10000u;
      }
    }
    else
    {
      *(_DWORD *)(a4 + 56) |= 0x10000u;
    }
  }
LABEL_117:
  v13 = 1;
  if ( v9 )
  {
    v21 = (char *)a8;
    v23 = 0;
    goto LABEL_119;
  }
  return v13;
}

```

## disassembly

```asm
0x1400240a0  mov     rax, rsp
0x1400240a3  push    rbx
0x1400240a4  push    rbp
0x1400240a5  push    rsi
0x1400240a6  push    rdi
0x1400240a7  push    r12
0x1400240a9  push    r13
0x1400240ab  push    r14
0x1400240ad  push    r15
0x1400240af  sub     rsp, 68h
0x1400240b3  mov     r13, [rcx+60h]
0x1400240b7  xor     r12d, r12d
0x1400240ba  mov     edi, edx
0x1400240bc  mov     [rax-58h], r12d
0x1400240c0  mov     r10, rcx
0x1400240c3  mov     [rax+8], r12d
0x1400240c7  mov     r15b, r8b
0x1400240ca  lea     rdx, [rax-58h]
0x1400240ce  mov     ecx, edi
0x1400240d0  lea     r8, [rax+8]
0x1400240d4  mov     r14, r9
0x1400240d7  mov     sil, r12b
0x1400240da  call    LuafvQueryCommonDirectoryClass
0x1400240df  mov     r9, [r13+18h]
0x1400240e3  test    r9, r9
0x1400240e6  jz      loc_1400241F8
0x1400240ec  mov     eax, [r13+0Ch]
0x1400240f0  add     rax, [r13+10h]
0x1400240f4  cmp     r9, rax
0x1400240f7  jnb     loc_1400241F8
0x1400240fd  lea     rbx, [r13+38h]
0x140024101  mov     r8, [rbx]
0x140024104  test    r8, r8
0x140024107  jz      loc_140024201
0x14002410d  mov     eax, [r13+2Ch]
0x140024111  add     rax, [r13+30h]
0x140024115  cmp     r8, rax
0x140024118  jnb     loc_140024201
0x14002411e  mov     r8d, [rsp+0A8h+arg_0]
0x140024126  mov     rcx, r10
0x140024129  mov     edx, [rsp+0A8h+var_58]
0x14002412d  call    LuafvCompareDirectoryEntryName
0x140024132  test    eax, eax
0x140024134  js      loc_14002421E
0x14002413a  jg      loc_140024260
0x140024140  mov     r12b, 1
0x140024143  cmp     edi, 3Ch ; '<'
0x140024146  jg      loc_1400241DF
0x14002414c  jz      short loc_140024176
0x14002414e  mov     ecx, edi
0x140024150  sub     ecx, 1
0x140024153  jz      short loc_140024176
0x140024155  sub     ecx, 1
0x140024158  jz      short loc_140024176
0x14002415a  sub     ecx, 1
0x14002415d  jz      short loc_140024176
0x14002415f  sub     ecx, 9
0x140024162  jz      loc_140024292
0x140024168  sub     ecx, 19h
0x14002416b  jz      short loc_140024176
0x14002416d  cmp     ecx, 1
0x140024170  jnz     loc_14002421E
0x140024176  mov     rax, [r13+18h]
0x14002417a  mov     rcx, [rbx]
0x14002417d  mov     edx, [rax+38h]
0x140024180  mov     eax, [rcx+38h]
0x140024183  xor     eax, edx
0x140024185  test    al, 10h
0x140024187  jz      loc_140024292
0x14002418d  mov     al, [rsp+0A8h+arg_28]
0x140024194  lea     rcx, [r13+20h]; int
0x140024198  mov     rbx, [rsp+0A8h+arg_38]
0x1400241a0  mov     r9b, r15b; int
0x1400241a3  mov     r8d, [rsp+0A8h+arg_0]; int
0x1400241ab  mov     edx, [rsp+0A8h+var_58]; int
0x1400241af  mov     [rsp+0A8h+var_60], rbx; __int64
0x1400241b4  mov     [rsp+0A8h+var_68], 0; __int64
0x1400241bd  mov     [rsp+0A8h+var_70], al; char
0x1400241c1  mov     rax, [rsp+0A8h+arg_20]
0x1400241c9  mov     [rsp+0A8h+var_78], r12b; char
0x1400241ce  mov     [rsp+0A8h+var_80], rax; __int64
0x1400241d3  mov     [rsp+0A8h+var_88], r14; void *
0x1400241d8  call    LuafvCopyDirectoryEntry
0x1400241dd  jmp     short loc_140024226
0x1400241df  mov     ecx, edi
0x1400241e1  sub     ecx, 3Fh ; '?'
0x1400241e4  jz      short loc_140024176
0x1400241e6  sub     ecx, 0Fh
0x1400241e9  jz      short loc_140024176
0x1400241eb  sub     ecx, 1
0x1400241ee  jz      short loc_140024176
0x1400241f0  sub     ecx, 1
0x1400241f3  jmp     loc_14002416B
0x1400241f8  lea     rbx, [r13+38h]
0x1400241fc  test    r9, r9
0x1400241ff  jz      short loc_140024230
0x140024201  mov     eax, [r13+0Ch]
0x140024205  add     rax, [r13+10h]
0x140024209  cmp     r9, rax
0x14002420c  jnb     short loc_140024230
0x14002420e  cmp     [rbx], r12
0x140024211  jz      short loc_140024230
0x140024213  cmp     [r13+28h], r12d
0x140024217  jnz     short loc_14002421E
0x140024219  mov     rcx, [rbx]
0x14002421c  jmp     short loc_14002423C
0x14002421e  mov     rbx, [rsp+0A8h+arg_38]
0x140024226  mov     eax, 1
0x14002422b  jmp     loc_1400245F3
0x140024230  mov     rcx, [rbx]
0x140024233  test    rcx, rcx
0x140024236  jz      loc_140024646
0x14002423c  mov     eax, [r13+2Ch]
0x140024240  add     rax, [r13+30h]
0x140024244  cmp     rcx, rax
0x140024247  jnb     loc_140024646
0x14002424d  test    r9, r9
0x140024250  jz      loc_140024646
0x140024256  cmp     [r13+8], r12d
0x14002425a  jz      loc_140024646
0x140024260  mov     eax, [rsp+0A8h+arg_0]
0x140024267  mov     rcx, [rbx]
0x14002426a  mov     edx, [rax+rcx]
0x14002426d  lea     eax, [rdx-2]
0x140024270  test    eax, 0FFFFFFFDh
0x140024275  jnz     short loc_140024292
0x140024277  mov     eax, [rsp+0A8h+var_58]
0x14002427b  cmp     word ptr [rax+rcx], 2Eh ; '.'
0x140024280  jnz     short loc_140024292
0x140024282  cmp     edx, 2
0x140024285  jz      short loc_14002428F
0x140024287  cmp     word ptr [rax+rcx+2], 2Eh ; '.'
0x14002428d  jnz     short loc_140024292
0x14002428f  mov     sil, 1
0x140024292  mov     rax, [rsp+0A8h+arg_30]
0x14002429a  lea     rcx, [r13+20h]; int
0x14002429e  mov     rbx, [rsp+0A8h+arg_38]
0x1400242a6  mov     r9b, r15b; int
0x1400242a9  mov     r8d, [rsp+0A8h+arg_0]; int
0x1400242b1  mov     edx, [rsp+0A8h+var_58]; int
0x1400242b5  mov     [rsp+0A8h+var_60], rbx; __int64
0x1400242ba  mov     [rsp+0A8h+var_68], rax; __int64
0x1400242bf  mov     al, [rsp+0A8h+arg_28]
0x1400242c6  mov     [rsp+0A8h+var_70], al; char
0x1400242ca  mov     rax, [rsp+0A8h+arg_20]
0x1400242d2  mov     [rsp+0A8h+var_78], sil; char
0x1400242d7  mov     [rsp+0A8h+var_80], rax; __int64
0x1400242dc  mov     [rsp+0A8h+var_88], r14; void *
0x1400242e1  call    LuafvCopyDirectoryEntry
0x1400242e6  cmp     byte ptr [rbx], 0
0x1400242e9  jnz     loc_1400245DE
0x1400242ef  test    sil, sil
0x1400242f2  jz      short loc_1400242FB
0x1400242f4  xor     al, al
0x1400242f6  jmp     loc_140024649
0x1400242fb  test    r12b, r12b
0x1400242fe  jz      loc_14002456E
0x140024304  cmp     edi, 3
0x140024307  jz      short loc_14002430E
0x140024309  cmp     edi, 25h ; '%'
0x14002430c  jnz     short loc_140024353
0x14002430e  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x140024313  mov     r8d, eax
0x140024316  lea     rcx, [r14+44h]; void *
0x14002431a  mov     rax, [r13+18h]
0x14002431e  mov     ebp, 19h
0x140024323  test    r8d, r8d
0x140024326  jz      short loc_140024342
0x140024328  lea     rdx, [rax+44h]; Src
0x14002432c  mov     r8d, ebp; Size
0x14002432f  test    r15b, r15b
0x140024332  jz      short loc_14002433B
0x140024334  call    RtlCopyToUser
0x140024339  jmp     short loc_140024358
0x14002433b  call    RtlCopyVolatileMemory
0x140024340  jmp     short loc_140024358
0x140024342  movups  xmm0, xmmword ptr [rax+44h]
0x140024346  movups  xmmword ptr [rcx], xmm0
0x140024349  movups  xmm1, xmmword ptr [rax+4Dh]
0x14002434d  movups  xmmword ptr [rcx+9], xmm1
0x140024351  jmp     short loc_140024358
0x140024353  mov     ebp, 19h
0x140024358  mov     ecx, edi
0x14002435a  mov     esi, 8
0x14002435f  sub     ecx, 25h ; '%'
0x140024362  jz      short loc_140024369
0x140024364  cmp     ecx, 1
0x140024367  jnz     short loc_1400243AE
0x140024369  mov     ebx, 48h ; 'H'
0x14002436e  cmp     edi, 26h ; '&'
0x140024371  lea     eax, [rbx+18h]
0x140024374  cmovnz  ebx, eax
0x140024377  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x14002437c  mov     r8d, eax
0x14002437f  lea     rcx, [rbx+r14]; void *
0x140024383  mov     rax, [r13+18h]
0x140024387  add     rax, rbx
0x14002438a  test    r8d, r8d
0x14002438d  jz      short loc_1400243A8
0x14002438f  mov     r8, rsi; Size
0x140024392  mov     rdx, rax; Src
0x140024395  test    r15b, r15b
0x140024398  jz      short loc_1400243A1
0x14002439a  call    RtlCopyToUser
0x14002439f  jmp     short loc_1400243AE
0x1400243a1  call    RtlCopyVolatileMemory
0x1400243a6  jmp     short loc_1400243AE
0x1400243a8  mov     rax, [rax]
0x1400243ab  mov     [rcx], rax
0x1400243ae  mov     ecx, edi
0x1400243b0  sub     ecx, 4Eh ; 'N'
0x1400243b3  jz      short loc_1400243F8
0x1400243b5  cmp     ecx, 1
0x1400243b8  jnz     short loc_14002442E
0x1400243ba  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x1400243bf  mov     r8d, eax
0x1400243c2  lea     rcx, [r14+50h]; void *
0x1400243c6  mov     rax, [r13+18h]
0x1400243ca  test    r8d, r8d
0x1400243cd  jz      short loc_1400243E9
0x1400243cf  lea     rdx, [rax+50h]; Src
0x1400243d3  mov     r8, rbp; Size
0x1400243d6  test    r15b, r15b
0x1400243d9  jz      short loc_1400243E2
0x1400243db  call    RtlCopyToUser
0x1400243e0  jmp     short loc_1400243F8
0x1400243e2  call    RtlCopyVolatileMemory
0x1400243e7  jmp     short loc_1400243F8
0x1400243e9  movups  xmm0, xmmword ptr [rax+50h]
0x1400243ed  movups  xmmword ptr [rcx], xmm0
0x1400243f0  movups  xmm1, xmmword ptr [rax+59h]
0x1400243f4  movups  xmmword ptr [rcx+9], xmm1
0x1400243f8  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x1400243fd  mov     r8d, eax
0x140024400  lea     rcx, [r14+48h]; void *
0x140024404  mov     rax, [r13+18h]
0x140024408  test    r8d, r8d
0x14002440b  jz      short loc_140024427
0x14002440d  lea     rdx, [rax+48h]; Src
0x140024411  mov     r8, rsi; Size
0x140024414  test    r15b, r15b
0x140024417  jz      short loc_140024420
0x140024419  call    RtlCopyToUser
0x14002441e  jmp     short loc_14002442E
0x140024420  call    RtlCopyVolatileMemory
0x140024425  jmp     short loc_14002442E
0x140024427  mov     rax, [rax+48h]
0x14002442b  mov     [rcx], rax
0x14002442e  cmp     edi, 3Ch ; '<'
0x140024431  jz      short loc_140024476
0x140024433  cmp     edi, 3Fh ; '?'
0x140024436  jnz     short loc_1400244B0
0x140024438  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x14002443d  mov     r8d, eax
0x140024440  lea     rcx, [r14+58h]; void *
0x140024444  mov     rax, [r13+18h]
0x140024448  test    r8d, r8d
0x14002444b  jz      short loc_140024467
0x14002444d  lea     rdx, [rax+58h]; Src
0x140024451  mov     r8, rbp; Size
0x140024454  test    r15b, r15b
0x140024457  jz      short loc_140024460
0x140024459  call    RtlCopyToUser
0x14002445e  jmp     short loc_140024476
0x140024460  call    RtlCopyVolatileMemory
0x140024465  jmp     short loc_140024476
0x140024467  movups  xmm0, xmmword ptr [rax+58h]
0x14002446b  movups  xmmword ptr [rcx], xmm0
0x14002446e  movups  xmm1, xmmword ptr [rax+61h]
0x140024472  movups  xmmword ptr [rcx+9], xmm1
0x140024476  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x14002447b  mov     r8d, eax
0x14002447e  lea     rcx, [r14+48h]; void *
0x140024482  mov     rax, [r13+18h]
0x140024486  test    r8d, r8d
0x140024489  jz      short loc_1400244A8
0x14002448b  lea     rdx, [rax+48h]; Src
0x14002448f  mov     r8d, 10h; Size
0x140024495  test    r15b, r15b
0x140024498  jz      short loc_1400244A1
0x14002449a  call    RtlCopyToUser
0x14002449f  jmp     short loc_1400244B0
0x1400244a1  call    RtlCopyVolatileMemory
0x1400244a6  jmp     short loc_1400244B0
0x1400244a8  movups  xmm0, xmmword ptr [rax+48h]
0x1400244ac  movdqu  xmmword ptr [rcx], xmm0
0x1400244b0  mov     ecx, edi
0x1400244b2  sub     ecx, 50h ; 'P'
0x1400244b5  jz      short loc_1400244FE
0x1400244b7  cmp     ecx, 1
0x1400244ba  jnz     loc_14002456E
0x1400244c0  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x1400244c5  mov     r9d, eax
0x1400244c8  lea     rcx, [r14+60h]; void *
0x1400244cc  mov     rax, [r13+18h]
0x1400244d0  test    r9d, r9d
0x1400244d3  jz      short loc_1400244EF
0x1400244d5  lea     rdx, [rax+60h]; Src
0x1400244d9  mov     r8, rbp; Size
0x1400244dc  test    r15b, r15b
  ... truncated ...
```
