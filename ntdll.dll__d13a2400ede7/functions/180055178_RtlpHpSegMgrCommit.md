# RtlpHpSegMgrCommit

- ea: `0x180055178`
- end: `0x1800555bc`
- name: `RtlpHpSegMgrCommit`
- size: `1092`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800328a8`
- `0x1800bf67c`
- `0x1800bf73c`

## callees

- `0x180055178`
- `0x1800555d0`
- `0x180055658`
- `0x18005638c`
- `0x1800d6148`
- `0x18010f11c`
- `0x180111d88`
- `0x180118654`
- `0x18011d14c`
- `0x1801583c4`
- `0x18015eea0`
- `0x18016f020`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlpHpSegMgrCommit(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        int a7)
{
  unsigned __int64 v7; // r14
  int v9; // r15d
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // rsi
  unsigned int v13; // edi
  int v14; // r15d
  _WORD *v15; // rax
  void *v16; // r12
  size_t v17; // rbx
  int v18; // r13d
  unsigned __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // eax
  int v23; // ebx
  int v24; // edx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  bool v29; // cf
  int v30; // eax
  int v31; // eax
  int v32; // eax
  __int16 v33; // [rsp+28h] [rbp-80h]
  unsigned __int64 v34; // [rsp+30h] [rbp-78h] BYREF
  __int64 v35; // [rsp+38h] [rbp-70h] BYREF
  _WORD *v36; // [rsp+40h] [rbp-68h]
  __int64 v37; // [rsp+48h] [rbp-60h] BYREF
  size_t Size; // [rsp+50h] [rbp-58h]
  __int128 v39; // [rsp+60h] [rbp-48h] BYREF
  __int128 v40; // [rsp+70h] [rbp-38h]
  char v41; // [rsp+B0h] [rbp+8h] BYREF

  v7 = a5;
  v9 = *(_DWORD *)a1;
  v11 = a3;
  v12 = a1;
  v34 = 0;
  v35 = 0;
  v41 = 0;
  v37 = 0;
  if ( a5 > 0 && !(unsigned int)RtlpHpSegHeapCheckCommitLimit(a5 << 12, *(_QWORD *)(a1 + 56)) )
    return (unsigned int)-1073741523;
  v13 = a6 & 0xBFFFFFFF;
  a5 = a6 & 0x40000000;
  if ( (*(_BYTE *)(v12 + 13) & 7) != 0 )
  {
    v34 = a2 & 0xFFFFFFFFFFE00000uLL;
    v39 = 0;
    v40 = 0;
    RtlpHpVaMgrCtxQuery(qword_1801C6968, a2 & 0xFFFFFFFFFFE00000uLL, &v39);
    LODWORD(a1) = v40;
    if ( (int)v7 <= 0 || (_DWORD)v11 || (unsigned int)-v9 >= 0x200000 || a2 <= v34 )
    {
      v14 = a7;
    }
    else
    {
      v14 = a7;
      if ( (a7 & 2) == 0 )
        v14 = a7 | 1;
    }
    v15 = (_WORD *)(v40 + 2 * (v11 >> 9));
  }
  else
  {
    v14 = a7;
    v15 = 0;
  }
  v16 = (void *)(a2 + (unsigned int)((_DWORD)v11 << 12));
  v36 = v15;
  v17 = (unsigned int)(a4 << 12);
  v18 = a5;
  Size = v17;
  while ( 1 )
  {
    v35 = v17;
    v19 = (unsigned __int64)v16;
    v34 = (unsigned __int64)v16;
    v20 = v17;
    if ( !v15 )
      goto LABEL_6;
    v32 = RtlpHpSegMgrCommitInitiate(v12, (_DWORD)v15, v7, v14, (__int64)&v37, (__int64)&v41);
    if ( v32 == -1073741568 )
      break;
    v19 = v34;
    if ( v32 != -1073741566 )
    {
      v20 = v35;
LABEL_6:
      if ( (int)v7 <= 0 )
        goto LABEL_7;
      goto LABEL_18;
    }
    v19 = v34 & 0xFFFFFFFFFFE00000uLL;
    v20 = 0x200000;
    v34 &= 0xFFFFFFFFFFE00000uLL;
    v35 = 0x200000;
    if ( (int)v7 <= 0 )
    {
LABEL_7:
      if ( v13 == 0x8000 )
      {
        v34 = (v19 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL;
        v35 = v19 - v34 + v20;
        if ( !v35 )
        {
          v23 = 0;
          goto LABEL_14;
        }
        RtlpHpVaMgrCtxFree(qword_1801C6968, &v34, &v35);
      }
      else
      {
        if ( (unsigned __int8)(*(_BYTE *)(v12 + 41) - 2) > 2u )
        {
          v21 = (unsigned __int16)v13 & 0xC000;
          if ( *(_BYTE *)(v12 + 41) == 5 )
            v22 = ((__int64 (__fastcall *)(__int64, __int64, unsigned __int64 *, __int64 *, _DWORD))(RtlpHpHeapGlobals ^ *(_QWORD *)(*(_QWORD *)(v12 + 48) + 16LL) ^ *(_QWORD *)(v12 + 48)))(
                    RtlpHpHeapGlobals ^ **(_QWORD **)(v12 + 48) ^ *(_QWORD *)(v12 + 48),
                    -1,
                    &v34,
                    &v35,
                    v21);
          else
            v22 = ZwFreeVirtualMemory(-1, &v34, &v35, v21);
          v23 = v22;
LABEL_12:
          if ( (RtlpHpHeapFeatures & 0x10) != 0 )
            RtlpHpTlLogVAChange(v13, v35, v34, (unsigned int)v23);
          goto LABEL_14;
        }
        RtlpHpVaMgrCtxDecommit(qword_1801C6968, v19, v20);
      }
      v23 = 0;
      goto LABEL_12;
    }
    v13 |= 0x20000000u;
LABEL_18:
    if ( v18 && (v13 & 0x20000000) == 0 )
      v13 |= 0x40000000u;
    v26 = *(_QWORD *)(v12 + 56);
    v27 = *(unsigned __int8 *)(v26 + 1);
    v28 = *(_QWORD *)(v26 + 8);
    v29 = (*(_DWORD *)(v26 + 20) & 0x40000000) != 0;
    v39 = *(_OWORD *)(v12 + 40);
    v30 = RtlpHpHeapValidateProtection(v26, v29 ? 64 : 4, v27, v28);
    v31 = RtlpHpAllocVA((unsigned int)&v34, (unsigned int)&v35, 0, v13, v30, (__int64)&v39);
    v23 = v31;
    if ( v18 && v31 >= 0 && (v13 & 0x40000000) == 0 )
      memset_thunk_772440563353939046(v16, 0, Size);
LABEL_14:
    v24 = (int)v36;
    if ( !v36 )
      return (unsigned int)v23;
    if ( (*v36 & 0x4000) != 0 && v23 >= 0 )
    {
      a1 = 1;
      if ( (int)v7 <= 0 )
        a1 = -1;
      _InterlockedAdd64((volatile signed __int64 *)(*(__int16 *)(v12 + 20) + v12 + 8), a1);
      LODWORD(a1) = v7;
      _InterlockedAdd64((volatile signed __int64 *)(*(__int16 *)(v12 + 20) + v12), v7);
    }
    RtlpHpSegMgrCommitComplete(a1, v24, v7, v23 >= 0, (__int64)&v37, v33);
    if ( (v13 & 0x20000000) == 0 || v23 >= 0 || (v14 & 2) != 0 )
      return (unsigned int)v23;
    v15 = v36;
    v14 |= 1u;
    v17 = Size;
    v13 &= ~0x20000000u;
  }
  _InterlockedAdd64((volatile signed __int64 *)(*(__int16 *)(v12 + 20) + v12), v7);
  if ( v18 )
    memset_thunk_772440563353939046(v16, 0, v17);
  return 0;
}

```

## disassembly

```asm
0x180055178  mov     rax, rsp
0x18005517b  mov     [rax+10h], rbx
0x18005517f  mov     [rax+18h], rsi
0x180055183  push    rdi
0x180055184  push    r12
0x180055186  push    r13
0x180055188  push    r14
0x18005518a  push    r15
0x18005518c  sub     rsp, 80h
0x180055193  movsxd  r14, [rsp+0A8h+arg_20]
0x18005519b  mov     r13d, r9d
0x18005519e  mov     r15d, [rcx]
0x1800551a1  mov     rbx, rdx
0x1800551a4  mov     r12d, r8d
0x1800551a7  mov     rsi, rcx
0x1800551aa  mov     qword ptr [rax-78h], 0
0x1800551b2  mov     qword ptr [rax-70h], 0
0x1800551ba  mov     byte ptr [rax+8], 0
0x1800551be  mov     qword ptr [rax-60h], 0
0x1800551c6  test    r14d, r14d
0x1800551c9  jg      loc_1800552BE
0x1800551cf  mov     edi, [rsp+0A8h+arg_28]
0x1800551d6  mov     eax, edi
0x1800551d8  and     eax, 40000000h
0x1800551dd  btr     edi, 1Eh
0x1800551e1  mov     [rsp+0A8h+arg_20], eax
0x1800551e8  mov     al, [rsi+0Dh]
0x1800551eb  and     al, 7
0x1800551ed  cmp     al, 1
0x1800551ef  jnb     loc_18005536A
0x1800551f5  mov     r15d, [rsp+0A8h+arg_30]
0x1800551fd  xor     eax, eax
0x1800551ff  shl     r12d, 0Ch
0x180055203  add     r12, rbx
0x180055206  mov     [rsp+0A8h+var_68], rax
0x18005520b  shl     r13d, 0Ch
0x18005520f  mov     ebx, r13d
0x180055212  mov     r13d, [rsp+0A8h+arg_20]
0x18005521a  mov     [rsp+0A8h+Size], rbx
0x18005521f  mov     [rsp+0A8h+var_70], rbx
0x180055224  mov     rdx, r12
0x180055227  mov     [rsp+0A8h+var_78], rdx
0x18005522c  mov     r8, rbx
0x18005522f  test    rax, rax
0x180055232  jnz     loc_18005541E
0x180055238  test    r14d, r14d
0x18005523b  jg      loc_1800552DF
0x180055241  cmp     edi, 8000h
0x180055247  jz      loc_1800554A3
0x18005524d  mov     al, [rsi+29h]
0x180055250  sub     al, 2
0x180055252  cmp     al, 2
0x180055254  jbe     loc_1800554E5
0x18005525a  mov     r9d, edi
0x18005525d  and     r9d, 0C000h
0x180055264  cmp     byte ptr [rsi+29h], 5
0x180055268  jz      loc_1800553B9
0x18005526e  lea     r8, [rsp+0A8h+var_70]
0x180055273  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180055277  lea     rdx, [rsp+0A8h+var_78]
0x18005527c  call    ZwFreeVirtualMemory
0x180055281  mov     ebx, eax
0x180055283  test    cs:RtlpHpHeapFeatures, 10h
0x18005528a  jnz     loc_1800554F8
0x180055290  mov     rdx, [rsp+0A8h+var_68]
0x180055295  test    rdx, rdx
0x180055298  jnz     loc_180055511
0x18005529e  lea     r11, [rsp+0A8h+var_28]
0x1800552a6  mov     eax, ebx
0x1800552a8  mov     rbx, [r11+38h]
0x1800552ac  mov     rsi, [r11+40h]
0x1800552b0  mov     rsp, r11
0x1800552b3  pop     r15
0x1800552b5  pop     r14
0x1800552b7  pop     r13
0x1800552b9  pop     r12
0x1800552bb  pop     rdi
0x1800552bc  retn
0x1800552be  mov     rdx, [rsi+38h]
0x1800552c2  mov     eax, r14d
0x1800552c5  shl     eax, 0Ch
0x1800552c8  movsxd  rcx, eax
0x1800552cb  call    RtlpHpSegHeapCheckCommitLimit
0x1800552d0  test    eax, eax
0x1800552d2  jnz     loc_1800551CF
0x1800552d8  mov     ebx, 0C000012Dh
0x1800552dd  jmp     short loc_18005529E
0x1800552df  test    r13d, r13d
0x1800552e2  jnz     loc_180055490
0x1800552e8  mov     rcx, [rsi+38h]
0x1800552ec  movups  xmm0, xmmword ptr [rsi+28h]
0x1800552f0  mov     eax, [rcx+14h]
0x1800552f3  movzx   r8d, byte ptr [rcx+1]
0x1800552f8  and     eax, 40000000h
0x1800552fd  mov     r9, [rcx+8]
0x180055301  neg     eax
0x180055303  movdqu  [rsp+0A8h+var_48], xmm0
0x180055309  sbb     edx, edx
0x18005530b  and     edx, 3Ch
0x18005530e  add     edx, 4
0x180055311  call    RtlpHpHeapValidateProtection
0x180055316  lea     rcx, [rsp+0A8h+var_48]
0x18005531b  mov     r9d, edi
0x18005531e  mov     [rsp+0A8h+var_80], rcx
0x180055323  lea     rdx, [rsp+0A8h+var_70]
0x180055328  lea     rcx, [rsp+0A8h+var_78]
0x18005532d  mov     dword ptr [rsp+0A8h+var_88], eax
0x180055331  xor     r8d, r8d
0x180055334  call    RtlpHpAllocVA
0x180055339  mov     ebx, eax
0x18005533b  test    r13d, r13d
0x18005533e  jz      loc_180055290
0x180055344  test    eax, eax
0x180055346  js      loc_180055290
0x18005534c  bt      edi, 1Eh
0x180055350  jb      loc_180055290
0x180055356  mov     r8, [rsp+0A8h+Size]; Size
0x18005535b  xor     edx, edx; Val
0x18005535d  mov     rcx, r12; void *
0x180055360  call    memset$thunk$772440563353939046
0x180055365  jmp     loc_180055290
0x18005536a  xorps   xmm0, xmm0
0x18005536d  lea     r8, [rsp+0A8h+var_48]
0x180055372  mov     rdx, rbx
0x180055375  lea     rcx, qword_1801C6968
0x18005537c  and     rdx, 0FFFFFFFFFFE00000h
0x180055383  mov     [rsp+0A8h+var_78], rdx
0x180055388  movups  [rsp+0A8h+var_48], xmm0
0x18005538d  movups  [rsp+0A8h+var_38], xmm0
0x180055392  call    RtlpHpVaMgrCtxQuery
0x180055397  mov     rcx, qword ptr [rsp+0A8h+var_38]
0x18005539c  test    r14d, r14d
0x18005539f  jg      short loc_1800553F2
0x1800553a1  mov     r15d, [rsp+0A8h+arg_30]
0x1800553a9  mov     rax, r12
0x1800553ac  shr     rax, 9
0x1800553b0  lea     rax, [rcx+rax*2]
0x1800553b4  jmp     loc_1800551FF
0x1800553b9  mov     rax, [rsi+30h]
0x1800553bd  lea     r8, [rsp+0A8h+var_78]
0x1800553c2  mov     rcx, rax
0x1800553c5  mov     dword ptr [rsp+0A8h+var_88], r9d
0x1800553ca  lea     r9, [rsp+0A8h+var_70]
0x1800553cf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800553d3  xor     rcx, [rax]
0x1800553d6  xor     rax, [rax+10h]
0x1800553da  xor     rax, cs:RtlpHpHeapGlobals
0x1800553e1  xor     rcx, cs:RtlpHpHeapGlobals
0x1800553e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553ed  jmp     loc_180055281
0x1800553f2  test    r12d, r12d
0x1800553f5  jnz     short loc_1800553A1
0x1800553f7  neg     r15d
0x1800553fa  cmp     r15d, 200000h
0x180055401  jnb     short loc_1800553A1
0x180055403  cmp     rbx, [rsp+0A8h+var_78]
0x180055408  jbe     short loc_1800553A1
0x18005540a  mov     r15d, [rsp+0A8h+arg_30]
0x180055412  test    r15b, 2
0x180055416  jnz     short loc_1800553A9
0x180055418  or      r15d, 1
0x18005541c  jmp     short loc_1800553A9
0x18005541e  lea     rcx, [rsp+0A8h+arg_0]
0x180055426  mov     r9d, r15d
0x180055429  mov     [rsp+0A8h+var_80], rcx
0x18005542e  mov     r8d, r14d
0x180055431  lea     rcx, [rsp+0A8h+var_60]
0x180055436  mov     rdx, rax
0x180055439  mov     [rsp+0A8h+var_88], rcx
0x18005543e  mov     rcx, rsi
0x180055441  call    RtlpHpSegMgrCommitInitiate
0x180055446  cmp     eax, 0C0000100h
0x18005544b  jz      loc_180055596
0x180055451  mov     rdx, [rsp+0A8h+var_78]
0x180055456  cmp     eax, 0C0000102h
0x18005545b  jnz     short loc_180055486
0x18005545d  and     rdx, 0FFFFFFFFFFE00000h
0x180055464  mov     r8d, 200000h
0x18005546a  mov     [rsp+0A8h+var_78], rdx
0x18005546f  mov     [rsp+0A8h+var_70], r8
0x180055474  test    r14d, r14d
0x180055477  jle     loc_180055241
0x18005547d  bts     edi, 1Dh
0x180055481  jmp     loc_1800552DF
0x180055486  mov     r8, [rsp+0A8h+var_70]
0x18005548b  jmp     loc_180055238
0x180055490  bt      edi, 1Dh
0x180055494  jb      loc_1800552E8
0x18005549a  bts     edi, 1Eh
0x18005549e  jmp     loc_1800552E8
0x1800554a3  lea     rax, [rdx+0FFFFFh]
0x1800554aa  and     rax, 0FFFFFFFFFFF00000h
0x1800554b0  sub     rdx, rax
0x1800554b3  mov     [rsp+0A8h+var_78], rax
0x1800554b8  lea     rax, [rdx+r8]
0x1800554bc  mov     [rsp+0A8h+var_70], rax
0x1800554c1  test    rax, rax
0x1800554c4  jnz     short loc_1800554CD
0x1800554c6  xor     ebx, ebx
0x1800554c8  jmp     loc_180055290
0x1800554cd  lea     r8, [rsp+0A8h+var_70]
0x1800554d2  lea     rdx, [rsp+0A8h+var_78]
0x1800554d7  lea     rcx, qword_1801C6968
0x1800554de  call    RtlpHpVaMgrCtxFree
0x1800554e3  jmp     short loc_1800554F1
0x1800554e5  lea     rcx, qword_1801C6968
0x1800554ec  call    RtlpHpVaMgrCtxDecommit
0x1800554f1  xor     ebx, ebx
0x1800554f3  jmp     loc_180055283
0x1800554f8  mov     r8, [rsp+0A8h+var_78]
0x1800554fd  mov     r9d, ebx
0x180055500  mov     rdx, [rsp+0A8h+var_70]
0x180055505  mov     ecx, edi
0x180055507  call    RtlpHpTlLogVAChange
0x18005550c  jmp     loc_180055290
0x180055511  movzx   eax, word ptr [rdx]
0x180055514  bt      ax, 0Eh
0x180055519  jnb     short loc_180055547
0x18005551b  test    ebx, ebx
0x18005551d  js      short loc_180055547
0x18005551f  mov     ecx, 1
0x180055524  test    r14d, r14d
0x180055527  lea     rax, [rcx-2]
0x18005552b  cmovle  rcx, rax
0x18005552f  movsx   rax, word ptr [rsi+14h]
0x180055534  lock add [rax+rsi+8], rcx
0x18005553a  movsx   rax, word ptr [rsi+14h]
0x18005553f  mov     rcx, r14
0x180055542  lock add [rax+rsi], rcx
0x180055547  mov     r9d, ebx
0x18005554a  lea     rax, [rsp+0A8h+var_60]
0x18005554f  not     r9d
0x180055552  mov     [rsp+0A8h+var_88], rax
0x180055557  shr     r9d, 1Fh
0x18005555b  mov     r8d, r14d
0x18005555e  call    RtlpHpSegMgrCommitComplete
0x180055563  bt      edi, 1Dh
0x180055567  jnb     loc_18005529E
0x18005556d  test    ebx, ebx
0x18005556f  jns     loc_18005529E
0x180055575  test    r15b, 2
0x180055579  jnz     loc_18005529E
0x18005557f  mov     rax, [rsp+0A8h+var_68]
0x180055584  or      r15d, 1
0x180055588  mov     rbx, [rsp+0A8h+Size]
0x18005558d  btr     edi, 1Dh
0x180055591  jmp     loc_18005521F
0x180055596  movsx   rax, word ptr [rsi+14h]
0x18005559b  mov     rdx, r14
0x18005559e  lock add [rax+rsi], rdx
0x1800555a3  test    r13d, r13d
0x1800555a6  jz      short loc_1800555B5
0x1800555a8  mov     r8, rbx; Size
0x1800555ab  xor     edx, edx; Val
0x1800555ad  mov     rcx, r12; void *
0x1800555b0  call    memset$thunk$772440563353939046
0x1800555b5  xor     ebx, ebx
0x1800555b7  jmp     loc_18005529E
```
