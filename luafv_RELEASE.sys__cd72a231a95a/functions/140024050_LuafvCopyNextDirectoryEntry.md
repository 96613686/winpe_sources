# LuafvCopyNextDirectoryEntry

- ea: `0x140024050`
- end: `0x14002460b`
- name: `LuafvCopyNextDirectoryEntry`
- size: `1467`
- prototype: `char __fastcall(__int64, int, char, __int64, __int64, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14002205c`

## callees

- `0x140001b34`
- `0x140005be0`
- `0x140014008`
- `0x140014b8c`
- `0x140014bf0`
- `0x140014c8c`
- `0x1400226b4`
- `0x140024050`
- `0x140024614`

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
  int v18; // eax
  bool v19; // zf
  int v20; // ecx
  char *v21; // rbx
  unsigned __int64 v22; // rcx
  int v23; // eax
  unsigned __int64 v24; // rcx
  int v25; // edx
  _BYTE *v26; // rbx
  unsigned __int64 v27; // rcx
  int v29; // r8d
  _OWORD *v30; // rcx
  __int64 v31; // rax
  void *v32; // rdx
  __int64 v33; // rbx
  int IsEnabledDeviceUsageNoInline; // r8d
  _QWORD *v35; // rcx
  void *v36; // rdx
  __int64 v37; // rcx
  int v38; // r8d
  __int64 v39; // rax
  void *v40; // rdx
  int v41; // r8d
  __int64 v42; // rax
  void *v43; // rdx
  int v44; // r8d
  __int64 v45; // rax
  void *v46; // rdx
  int v47; // r8d
  _OWORD *v48; // rcx
  __int64 v49; // rax
  void *v50; // rdx
  int v51; // r9d
  __int64 v52; // rax
  void *v53; // rdx
  int v54; // r9d
  _QWORD *v55; // rcx
  __int64 v56; // rax
  void *v57; // rdx
  int v58; // r9d
  __int64 v59; // rax
  void *v60; // rdx
  int v61; // edi
  int v62; // edi
  int v63; // edi
  bool v64; // zf
  int v65; // edi
  int ULongFromUser; // eax
  int v67; // edi
  int v68; // edi
  int v69; // edi
  int v70[22]; // [rsp+50h] [rbp-58h] BYREF
  int v71; // [rsp+B0h] [rbp+8h] BYREF

  v8 = *(_QWORD *)(a1 + 96);
  v9 = 0;
  v70[0] = 0;
  v71 = 0;
  v13 = 0;
  LuafvQueryCommonDirectoryClass((unsigned int)a2, v70, &v71);
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
  v18 = LuafvCompareDirectoryEntryName(v14, (unsigned int)v70[0], (unsigned int)v71);
  if ( v18 < 0 )
    goto LABEL_27;
  if ( v18 > 0 )
  {
LABEL_33:
    v24 = *v16;
    v25 = *(_DWORD *)((unsigned int)v71 + *v16);
    if ( ((v25 - 2) & 0xFFFFFFFD) == 0
      && *(_WORD *)((unsigned int)v70[0] + v24) == 46
      && (v25 == 2 || *(_WORD *)((unsigned int)v70[0] + v24 + 2) == 46) )
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
    LuafvCopyDirectoryEntry(v8 + 32, v70[0], v71, a3, (char *)a4, a5, 1, a6, 0, (char *)a8);
LABEL_28:
    v23 = 1;
LABEL_119:
    LuafvCopyDirectoryEntry(v8, v70[0], v71, a3, (char *)a4, a5, v13, a6, (_QWORD *)(a7 & -(__int64)(v23 != 0)), v21);
    return 1;
  }
LABEL_38:
  v26 = (_BYTE *)a8;
  LuafvCopyDirectoryEntry(v8 + 32, v70[0], v71, a3, (char *)a4, a5, v13, a6, (_QWORD *)a7, (char *)a8);
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
    v29 = ((__int64 (*)(void))Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline)();
    v30 = (_OWORD *)(a4 + 68);
    v31 = *(_QWORD *)(v8 + 24);
    if ( v29 )
    {
      v32 = (void *)(v31 + 68);
      if ( a3 )
        RtlCopyToUser(v30, v32, 0x19u);
      else
        RtlCopyVolatileMemory(v30, v32, 0x19u);
    }
    else
    {
      *v30 = *(_OWORD *)(v31 + 68);
      *(_OWORD *)(a4 + 77) = *(_OWORD *)(v31 + 77);
    }
  }
  if ( a2 == 37 || a2 == 38 )
  {
    v33 = 72;
    if ( a2 != 38 )
      v33 = 96;
    IsEnabledDeviceUsageNoInline = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline((unsigned int)(a2 - 37));
    v35 = (_QWORD *)(v33 + a4);
    if ( IsEnabledDeviceUsageNoInline )
    {
      v36 = (void *)(v33 + *(_QWORD *)(v8 + 24));
      if ( a3 )
        RtlCopyToUser(v35, v36, 8u);
      else
        RtlCopyVolatileMemory(v35, v36, 8u);
    }
    else
    {
      *v35 = *(_QWORD *)(v33 + *(_QWORD *)(v8 + 24));
    }
  }
  v37 = (unsigned int)(a2 - 78);
  if ( a2 != 78 )
  {
    if ( a2 != 79 )
      goto LABEL_70;
    v38 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline(v37);
    v37 = a4 + 80;
    v39 = *(_QWORD *)(v8 + 24);
    if ( v38 )
    {
      v40 = (void *)(v39 + 80);
      if ( a3 )
        RtlCopyToUser((void *)v37, v40, 0x19u);
      else
        RtlCopyVolatileMemory((void *)v37, v40, 0x19u);
    }
    else
    {
      *(_OWORD *)v37 = *(_OWORD *)(v39 + 80);
      *(_OWORD *)(a4 + 89) = *(_OWORD *)(v39 + 89);
    }
  }
  v41 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline(v37);
  v37 = a4 + 72;
  v42 = *(_QWORD *)(v8 + 24);
  if ( v41 )
  {
    v43 = (void *)(v42 + 72);
    if ( a3 )
      RtlCopyToUser((void *)v37, v43, 8u);
    else
      RtlCopyVolatileMemory((void *)v37, v43, 8u);
  }
  else
  {
    *(_QWORD *)v37 = *(_QWORD *)(v42 + 72);
  }
LABEL_70:
  if ( a2 == 60 )
  {
LABEL_77:
    v47 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline(v37);
    v48 = (_OWORD *)(a4 + 72);
    v49 = *(_QWORD *)(v8 + 24);
    if ( v47 )
    {
      v50 = (void *)(v49 + 72);
      if ( a3 )
        RtlCopyToUser(v48, v50, 0x10u);
      else
        RtlCopyVolatileMemory(v48, v50, 0x10u);
    }
    else
    {
      *v48 = *(_OWORD *)(v49 + 72);
    }
    goto LABEL_82;
  }
  if ( a2 == 63 )
  {
    v44 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline(v37);
    v37 = a4 + 88;
    v45 = *(_QWORD *)(v8 + 24);
    if ( v44 )
    {
      v46 = (void *)(v45 + 88);
      if ( a3 )
        RtlCopyToUser((void *)v37, v46, 0x19u);
      else
        RtlCopyVolatileMemory((void *)v37, v46, 0x19u);
    }
    else
    {
      *(_OWORD *)v37 = *(_OWORD *)(v45 + 88);
      *(_OWORD *)(a4 + 97) = *(_OWORD *)(v45 + 97);
    }
    goto LABEL_77;
  }
LABEL_82:
  v27 = (unsigned int)(a2 - 80);
  if ( a2 != 80 )
  {
    if ( a2 != 81 )
      goto LABEL_99;
    v51 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline(v27);
    v27 = a4 + 96;
    v52 = *(_QWORD *)(v8 + 24);
    if ( v51 )
    {
      v53 = (void *)(v52 + 96);
      if ( a3 )
        RtlCopyToUser((void *)v27, v53, 0x19u);
      else
        RtlCopyVolatileMemory((void *)v27, v53, 0x19u);
    }
    else
    {
      *(_OWORD *)v27 = *(_OWORD *)(v52 + 96);
      *(_OWORD *)(a4 + 105) = *(_OWORD *)(v52 + 105);
    }
  }
  v54 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline(v27);
  v55 = (_QWORD *)(a4 + 72);
  v56 = *(_QWORD *)(v8 + 24);
  if ( v54 )
  {
    v57 = (void *)(v56 + 72);
    if ( a3 )
      RtlCopyToUser(v55, v57, 8u);
    else
      RtlCopyVolatileMemory(v55, v57, 8u);
  }
  else
  {
    *v55 = *(_QWORD *)(v56 + 72);
  }
  v58 = Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline(v55);
  v27 = a4 + 80;
  v59 = *(_QWORD *)(v8 + 24);
  if ( v58 )
  {
    v60 = (void *)(v59 + 80);
    if ( a3 )
      RtlCopyToUser((void *)v27, v60, 0x10u);
    else
      RtlCopyVolatileMemory((void *)v27, v60, 0x10u);
  }
  else
  {
    *(_OWORD *)v27 = *(_OWORD *)(v59 + 80);
  }
LABEL_99:
  if ( a2 > 60 )
  {
    v67 = a2 - 63;
    if ( !v67 )
      goto LABEL_107;
    v68 = v67 - 15;
    if ( !v68 )
      goto LABEL_107;
    v69 = v68 - 1;
    if ( !v69 )
      goto LABEL_107;
    v65 = v69 - 1;
    v64 = v65 == 0;
  }
  else
  {
    if ( a2 == 60 )
      goto LABEL_107;
    v61 = a2 - 1;
    if ( !v61 )
      goto LABEL_107;
    v62 = v61 - 1;
    if ( !v62 )
      goto LABEL_107;
    v63 = v62 - 1;
    if ( !v63 )
      goto LABEL_107;
    v65 = v63 - 34;
    v64 = v65 == 0;
  }
  if ( v64 || v65 == 1 )
  {
LABEL_107:
    if ( (unsigned int)Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline(v27) )
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
0x140024050  mov     rax, rsp
0x140024053  push    rbx
0x140024054  push    rbp
0x140024055  push    rsi
0x140024056  push    rdi
0x140024057  push    r12
0x140024059  push    r13
0x14002405b  push    r14
0x14002405d  push    r15
0x14002405f  sub     rsp, 68h
0x140024063  mov     r13, [rcx+60h]
0x140024067  xor     r12d, r12d
0x14002406a  mov     edi, edx
0x14002406c  mov     [rax-58h], r12d
0x140024070  mov     r10, rcx
0x140024073  mov     [rax+8], r12d
0x140024077  mov     r15b, r8b
0x14002407a  lea     rdx, [rax-58h]
0x14002407e  mov     ecx, edi
0x140024080  lea     r8, [rax+8]
0x140024084  mov     r14, r9
0x140024087  mov     sil, r12b
0x14002408a  call    LuafvQueryCommonDirectoryClass
0x14002408f  mov     r9, [r13+18h]
0x140024093  test    r9, r9
0x140024096  jz      loc_1400241A8
0x14002409c  mov     eax, [r13+0Ch]
0x1400240a0  add     rax, [r13+10h]
0x1400240a4  cmp     r9, rax
0x1400240a7  jnb     loc_1400241A8
0x1400240ad  lea     rbx, [r13+38h]
0x1400240b1  mov     r8, [rbx]
0x1400240b4  test    r8, r8
0x1400240b7  jz      loc_1400241B1
0x1400240bd  mov     eax, [r13+2Ch]
0x1400240c1  add     rax, [r13+30h]
0x1400240c5  cmp     r8, rax
0x1400240c8  jnb     loc_1400241B1
0x1400240ce  mov     r8d, [rsp+0A8h+arg_0]
0x1400240d6  mov     rcx, r10
0x1400240d9  mov     edx, [rsp+0A8h+var_58]
0x1400240dd  call    LuafvCompareDirectoryEntryName
0x1400240e2  test    eax, eax
0x1400240e4  js      loc_1400241CE
0x1400240ea  jg      loc_140024210
0x1400240f0  mov     r12b, 1
0x1400240f3  cmp     edi, 3Ch ; '<'
0x1400240f6  jg      loc_14002418F
0x1400240fc  jz      short loc_140024126
0x1400240fe  mov     ecx, edi
0x140024100  sub     ecx, 1
0x140024103  jz      short loc_140024126
0x140024105  sub     ecx, 1
0x140024108  jz      short loc_140024126
0x14002410a  sub     ecx, 1
0x14002410d  jz      short loc_140024126
0x14002410f  sub     ecx, 9
0x140024112  jz      loc_140024242
0x140024118  sub     ecx, 19h
0x14002411b  jz      short loc_140024126
0x14002411d  cmp     ecx, 1
0x140024120  jnz     loc_1400241CE
0x140024126  mov     rax, [r13+18h]
0x14002412a  mov     rcx, [rbx]
0x14002412d  mov     edx, [rax+38h]
0x140024130  mov     eax, [rcx+38h]
0x140024133  xor     eax, edx
0x140024135  test    al, 10h
0x140024137  jz      loc_140024242
0x14002413d  mov     al, [rsp+0A8h+arg_28]
0x140024144  lea     rcx, [r13+20h]; int
0x140024148  mov     rbx, [rsp+0A8h+arg_38]
0x140024150  mov     r9b, r15b; int
0x140024153  mov     r8d, [rsp+0A8h+arg_0]; int
0x14002415b  mov     edx, [rsp+0A8h+var_58]; int
0x14002415f  mov     [rsp+0A8h+var_60], rbx; __int64
0x140024164  mov     [rsp+0A8h+var_68], 0; __int64
0x14002416d  mov     [rsp+0A8h+var_70], al; char
0x140024171  mov     rax, [rsp+0A8h+arg_20]
0x140024179  mov     [rsp+0A8h+var_78], r12b; char
0x14002417e  mov     [rsp+0A8h+var_80], rax; __int64
0x140024183  mov     [rsp+0A8h+var_88], r14; void *
0x140024188  call    LuafvCopyDirectoryEntry
0x14002418d  jmp     short loc_1400241D6
0x14002418f  mov     ecx, edi
0x140024191  sub     ecx, 3Fh ; '?'
0x140024194  jz      short loc_140024126
0x140024196  sub     ecx, 0Fh
0x140024199  jz      short loc_140024126
0x14002419b  sub     ecx, 1
0x14002419e  jz      short loc_140024126
0x1400241a0  sub     ecx, 1
0x1400241a3  jmp     loc_14002411B
0x1400241a8  lea     rbx, [r13+38h]
0x1400241ac  test    r9, r9
0x1400241af  jz      short loc_1400241E0
0x1400241b1  mov     eax, [r13+0Ch]
0x1400241b5  add     rax, [r13+10h]
0x1400241b9  cmp     r9, rax
0x1400241bc  jnb     short loc_1400241E0
0x1400241be  cmp     [rbx], r12
0x1400241c1  jz      short loc_1400241E0
0x1400241c3  cmp     [r13+28h], r12d
0x1400241c7  jnz     short loc_1400241CE
0x1400241c9  mov     rcx, [rbx]
0x1400241cc  jmp     short loc_1400241EC
0x1400241ce  mov     rbx, [rsp+0A8h+arg_38]
0x1400241d6  mov     eax, 1
0x1400241db  jmp     loc_1400245A3
0x1400241e0  mov     rcx, [rbx]
0x1400241e3  test    rcx, rcx
0x1400241e6  jz      loc_1400245F6
0x1400241ec  mov     eax, [r13+2Ch]
0x1400241f0  add     rax, [r13+30h]
0x1400241f4  cmp     rcx, rax
0x1400241f7  jnb     loc_1400245F6
0x1400241fd  test    r9, r9
0x140024200  jz      loc_1400245F6
0x140024206  cmp     [r13+8], r12d
0x14002420a  jz      loc_1400245F6
0x140024210  mov     eax, [rsp+0A8h+arg_0]
0x140024217  mov     rcx, [rbx]
0x14002421a  mov     edx, [rax+rcx]
0x14002421d  lea     eax, [rdx-2]
0x140024220  test    eax, 0FFFFFFFDh
0x140024225  jnz     short loc_140024242
0x140024227  mov     eax, [rsp+0A8h+var_58]
0x14002422b  cmp     word ptr [rax+rcx], 2Eh ; '.'
0x140024230  jnz     short loc_140024242
0x140024232  cmp     edx, 2
0x140024235  jz      short loc_14002423F
0x140024237  cmp     word ptr [rax+rcx+2], 2Eh ; '.'
0x14002423d  jnz     short loc_140024242
0x14002423f  mov     sil, 1
0x140024242  mov     rax, [rsp+0A8h+arg_30]
0x14002424a  lea     rcx, [r13+20h]; int
0x14002424e  mov     rbx, [rsp+0A8h+arg_38]
0x140024256  mov     r9b, r15b; int
0x140024259  mov     r8d, [rsp+0A8h+arg_0]; int
0x140024261  mov     edx, [rsp+0A8h+var_58]; int
0x140024265  mov     [rsp+0A8h+var_60], rbx; __int64
0x14002426a  mov     [rsp+0A8h+var_68], rax; __int64
0x14002426f  mov     al, [rsp+0A8h+arg_28]
0x140024276  mov     [rsp+0A8h+var_70], al; char
0x14002427a  mov     rax, [rsp+0A8h+arg_20]
0x140024282  mov     [rsp+0A8h+var_78], sil; char
0x140024287  mov     [rsp+0A8h+var_80], rax; __int64
0x14002428c  mov     [rsp+0A8h+var_88], r14; void *
0x140024291  call    LuafvCopyDirectoryEntry
0x140024296  cmp     byte ptr [rbx], 0
0x140024299  jnz     loc_14002458E
0x14002429f  test    sil, sil
0x1400242a2  jz      short loc_1400242AB
0x1400242a4  xor     al, al
0x1400242a6  jmp     loc_1400245F9
0x1400242ab  test    r12b, r12b
0x1400242ae  jz      loc_14002451E
0x1400242b4  cmp     edi, 3
0x1400242b7  jz      short loc_1400242BE
0x1400242b9  cmp     edi, 25h ; '%'
0x1400242bc  jnz     short loc_140024303
0x1400242be  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x1400242c3  mov     r8d, eax
0x1400242c6  lea     rcx, [r14+44h]; void *
0x1400242ca  mov     rax, [r13+18h]
0x1400242ce  mov     ebp, 19h
0x1400242d3  test    r8d, r8d
0x1400242d6  jz      short loc_1400242F2
0x1400242d8  lea     rdx, [rax+44h]; Src
0x1400242dc  mov     r8d, ebp; Size
0x1400242df  test    r15b, r15b
0x1400242e2  jz      short loc_1400242EB
0x1400242e4  call    RtlCopyToUser
0x1400242e9  jmp     short loc_140024308
0x1400242eb  call    RtlCopyVolatileMemory
0x1400242f0  jmp     short loc_140024308
0x1400242f2  movups  xmm0, xmmword ptr [rax+44h]
0x1400242f6  movups  xmmword ptr [rcx], xmm0
0x1400242f9  movups  xmm1, xmmword ptr [rax+4Dh]
0x1400242fd  movups  xmmword ptr [rcx+9], xmm1
0x140024301  jmp     short loc_140024308
0x140024303  mov     ebp, 19h
0x140024308  mov     ecx, edi
0x14002430a  mov     esi, 8
0x14002430f  sub     ecx, 25h ; '%'
0x140024312  jz      short loc_140024319
0x140024314  cmp     ecx, 1
0x140024317  jnz     short loc_14002435E
0x140024319  mov     ebx, 48h ; 'H'
0x14002431e  cmp     edi, 26h ; '&'
0x140024321  lea     eax, [rbx+18h]
0x140024324  cmovnz  ebx, eax
0x140024327  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x14002432c  mov     r8d, eax
0x14002432f  lea     rcx, [rbx+r14]; void *
0x140024333  mov     rax, [r13+18h]
0x140024337  add     rax, rbx
0x14002433a  test    r8d, r8d
0x14002433d  jz      short loc_140024358
0x14002433f  mov     r8, rsi; Size
0x140024342  mov     rdx, rax; Src
0x140024345  test    r15b, r15b
0x140024348  jz      short loc_140024351
0x14002434a  call    RtlCopyToUser
0x14002434f  jmp     short loc_14002435E
0x140024351  call    RtlCopyVolatileMemory
0x140024356  jmp     short loc_14002435E
0x140024358  mov     rax, [rax]
0x14002435b  mov     [rcx], rax
0x14002435e  mov     ecx, edi
0x140024360  sub     ecx, 4Eh ; 'N'
0x140024363  jz      short loc_1400243A8
0x140024365  cmp     ecx, 1
0x140024368  jnz     short loc_1400243DE
0x14002436a  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x14002436f  mov     r8d, eax
0x140024372  lea     rcx, [r14+50h]; void *
0x140024376  mov     rax, [r13+18h]
0x14002437a  test    r8d, r8d
0x14002437d  jz      short loc_140024399
0x14002437f  lea     rdx, [rax+50h]; Src
0x140024383  mov     r8, rbp; Size
0x140024386  test    r15b, r15b
0x140024389  jz      short loc_140024392
0x14002438b  call    RtlCopyToUser
0x140024390  jmp     short loc_1400243A8
0x140024392  call    RtlCopyVolatileMemory
0x140024397  jmp     short loc_1400243A8
0x140024399  movups  xmm0, xmmword ptr [rax+50h]
0x14002439d  movups  xmmword ptr [rcx], xmm0
0x1400243a0  movups  xmm1, xmmword ptr [rax+59h]
0x1400243a4  movups  xmmword ptr [rcx+9], xmm1
0x1400243a8  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x1400243ad  mov     r8d, eax
0x1400243b0  lea     rcx, [r14+48h]; void *
0x1400243b4  mov     rax, [r13+18h]
0x1400243b8  test    r8d, r8d
0x1400243bb  jz      short loc_1400243D7
0x1400243bd  lea     rdx, [rax+48h]; Src
0x1400243c1  mov     r8, rsi; Size
0x1400243c4  test    r15b, r15b
0x1400243c7  jz      short loc_1400243D0
0x1400243c9  call    RtlCopyToUser
0x1400243ce  jmp     short loc_1400243DE
0x1400243d0  call    RtlCopyVolatileMemory
0x1400243d5  jmp     short loc_1400243DE
0x1400243d7  mov     rax, [rax+48h]
0x1400243db  mov     [rcx], rax
0x1400243de  cmp     edi, 3Ch ; '<'
0x1400243e1  jz      short loc_140024426
0x1400243e3  cmp     edi, 3Fh ; '?'
0x1400243e6  jnz     short loc_140024460
0x1400243e8  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x1400243ed  mov     r8d, eax
0x1400243f0  lea     rcx, [r14+58h]; void *
0x1400243f4  mov     rax, [r13+18h]
0x1400243f8  test    r8d, r8d
0x1400243fb  jz      short loc_140024417
0x1400243fd  lea     rdx, [rax+58h]; Src
0x140024401  mov     r8, rbp; Size
0x140024404  test    r15b, r15b
0x140024407  jz      short loc_140024410
0x140024409  call    RtlCopyToUser
0x14002440e  jmp     short loc_140024426
0x140024410  call    RtlCopyVolatileMemory
0x140024415  jmp     short loc_140024426
0x140024417  movups  xmm0, xmmword ptr [rax+58h]
0x14002441b  movups  xmmword ptr [rcx], xmm0
0x14002441e  movups  xmm1, xmmword ptr [rax+61h]
0x140024422  movups  xmmword ptr [rcx+9], xmm1
0x140024426  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x14002442b  mov     r8d, eax
0x14002442e  lea     rcx, [r14+48h]; void *
0x140024432  mov     rax, [r13+18h]
0x140024436  test    r8d, r8d
0x140024439  jz      short loc_140024458
0x14002443b  lea     rdx, [rax+48h]; Src
0x14002443f  mov     r8d, 10h; Size
0x140024445  test    r15b, r15b
0x140024448  jz      short loc_140024451
0x14002444a  call    RtlCopyToUser
0x14002444f  jmp     short loc_140024460
0x140024451  call    RtlCopyVolatileMemory
0x140024456  jmp     short loc_140024460
0x140024458  movups  xmm0, xmmword ptr [rax+48h]
0x14002445c  movdqu  xmmword ptr [rcx], xmm0
0x140024460  mov     ecx, edi
0x140024462  sub     ecx, 50h ; 'P'
0x140024465  jz      short loc_1400244AE
0x140024467  cmp     ecx, 1
0x14002446a  jnz     loc_14002451E
0x140024470  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x140024475  mov     r9d, eax
0x140024478  lea     rcx, [r14+60h]; void *
0x14002447c  mov     rax, [r13+18h]
0x140024480  test    r9d, r9d
0x140024483  jz      short loc_14002449F
0x140024485  lea     rdx, [rax+60h]; Src
0x140024489  mov     r8, rbp; Size
0x14002448c  test    r15b, r15b
  ... truncated ...
```
