# SmbPseExchangeReceive_default

- ea: `0x140006230`
- end: `0x140006ade`
- name: `SmbPseExchangeReceive_default`
- size: `2222`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, unsigned int *, char *Src, _QWORD *, unsigned int *, __int16)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x140006230`
- `0x140007820`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e01c`
- `0x14000ebd8`
- `0x140012014`
- `0x140014128`
- `0x140016640`
- `0x1400166c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000663f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000663f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400063d7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400063d7`

## pseudocode

```c
__int64 __fastcall SmbPseExchangeReceive_default(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        char *Src,
        _QWORD *a6,
        unsigned int *a7,
        __int16 a8)
{
  unsigned int v8; // r15d
  char v9; // r13
  unsigned __int64 v10; // r12
  unsigned int *v11; // r11
  __int64 v12; // r8
  unsigned __int8 v14; // bp
  unsigned int v15; // r13d
  __int64 *v16; // rbx
  char *v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 *v20; // r14
  char v21; // cl
  int v22; // ebp
  bool v23; // r8
  unsigned int v24; // edx
  __int64 v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 (__fastcall *v28)(__int64, _QWORD, _QWORD, unsigned int *, char *, _QWORD *, unsigned int *, __int64 *); // rax
  char v29; // al
  __int64 result; // rax
  int v31; // eax
  unsigned int v32; // ebp
  unsigned int v33; // edx
  __int64 v34; // rcx
  PVOID v35; // rax
  void *v36; // rbx
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  unsigned int v39; // [rsp+50h] [rbp-48h]
  char v40; // [rsp+A0h] [rbp+8h]

  v8 = 0;
  v9 = *(_BYTE *)(a1 + 384) & 1;
  v10 = a3;
  v40 = v9;
  v11 = a4;
  v12 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids,
        (unsigned int)v10,
        a2);
      v11 = a4;
      v12 = a2;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids,
        *(_QWORD *)(a1 + 896));
      v11 = a4;
      v12 = a2;
    }
  }
  if ( v9 )
  {
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(a1 + 40);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
      v11 = a4;
    }
    v14 = *(_BYTE *)(a1 + 397);
  }
  else
  {
    v16 = (__int64 *)(a1 + 396);
    *(_DWORD *)(a1 + 1460) = v12;
    *(_DWORD *)(a1 + 1456) = v10;
    v31 = SmbCeParseSmbHeader(a1, (__int64)Src, a1 + 396, (int *)(a1 + 40), v10, v12, v11);
    *(_WORD *)(a1 + 384) |= 1u;
    *(_DWORD *)(a1 + 48) = v31;
    if ( v31 == -1073741802 )
      goto LABEL_51;
    if ( v31 )
      goto LABEL_41;
    v14 = *(_BYTE *)(a1 + 397);
    if ( v14 == 0xFF )
      goto LABEL_41;
    v11 = a4;
  }
  v15 = *(_DWORD *)(a1 + 40);
  if ( v15
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids, v15);
    v11 = a4;
  }
  v16 = (__int64 *)(a1 + 396);
  if ( v14 == 0xFF )
    goto LABEL_40;
  v17 = &SmbPseReceiveModelParameters[16 * v14];
  v18 = *(_DWORD *)(a1 + 360);
  if ( v18 < *((_DWORD *)v17 + 1) || v18 > *((_DWORD *)v17 + 2) )
  {
    *v11 = v10;
    *a6 = 0;
    *a7 = 0;
    *(_DWORD *)(a1 + 48) = -1073741629;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids, a1);
    goto LABEL_113;
  }
  if ( (unsigned __int64)*((unsigned int *)v17 + 3) + 32 > v10 )
  {
    *v11 = v10;
    *a6 = 0;
    *a7 = 0;
    *(_DWORD *)(a1 + 48) = -1073741629;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      WPP_SF_DDq(WPP_GLOBAL_Control->AttachedDevice, 41, v12, (unsigned int)(*((_DWORD *)v17 + 3) + 32), v10, a1);
      v16 = (__int64 *)(a1 + 396);
      goto LABEL_41;
    }
    goto LABEL_113;
  }
  v19 = *(unsigned __int16 *)(a1 + 399);
  v20 = (__int64 *)&Src[v19];
  if ( &Src[v19] >= &Src[v10] )
  {
    *v11 = v10;
    *a6 = 0;
    *a7 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_DDq(WPP_GLOBAL_Control->AttachedDevice, 42, v12, *(unsigned __int16 *)(a1 + 399), v10, a1);
    goto LABEL_105;
  }
  if ( *(_BYTE *)(a1 + 397) != 0xFF && !(_WORD)v19 )
  {
    *v11 = v10;
    *a6 = 0;
    *a7 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_DDq(
        WPP_GLOBAL_Control->AttachedDevice,
        43,
        v12,
        *(unsigned __int16 *)(a1 + 399),
        *(unsigned __int8 *)(a1 + 397),
        a1);
LABEL_105:
    *(_DWORD *)(a1 + 48) = -1073741629;
    goto LABEL_106;
  }
  *(_BYTE *)(a1 + 388) = v14;
  v21 = *v17;
  if ( !*v17 )
  {
    if ( *(_QWORD *)(a1 + 424) && !v40 )
    {
      v16 = (__int64 *)(a1 + 396);
LABEL_74:
      v9 = v40;
      goto LABEL_51;
    }
    if ( v14 != 46 )
    {
      v36 = *(void **)(a1 + 80);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          48,
          WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids,
          v14,
          *(char *)v20);
      }
      SmbCeTransportDisconnectIndicated(v36);
      *a4 = v10;
      *a6 = 0;
      *a7 = 0;
      goto LABEL_105;
    }
  }
  v22 = v21 & 2;
  v23 = !*(_BYTE *)v20 || (v21 & 2) == 0;
  if ( (v15 & 0xC0000000) == 0xC0000000 && v23 )
  {
    *v11 = v10;
    *(_DWORD *)(a1 + 48) = v15;
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      v38 = 45;
LABEL_85:
      WPP_SF_(v37->AttachedDevice, v38, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
LABEL_106:
      v16 = (__int64 *)(a1 + 396);
      goto LABEL_41;
    }
    goto LABEL_113;
  }
  v24 = 0;
  v39 = 0;
  if ( v15 && v23 )
  {
    if ( (v21 & 4) == 0 )
    {
      *v11 = v10;
      *(_DWORD *)(a1 + 48) = v15;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        v38 = 46;
        goto LABEL_85;
      }
LABEL_113:
      v16 = (__int64 *)(a1 + 396);
      goto LABEL_41;
    }
    v24 = v15;
    v39 = v15;
  }
  if ( (v21 & 8) == 0 )
  {
    v9 = v40;
    if ( !*(_QWORD *)(a1 + 424) || v40 )
    {
      if ( (v21 & 0x10) != 0 && !v40 )
      {
        v16 = (__int64 *)(a1 + 396);
        goto LABEL_51;
      }
      if ( KeGetCurrentIrql() < 2u )
      {
        v25 = (unsigned __int8)v17[1];
        if ( (unsigned __int8)v25 < 0x11u )
        {
          v26 = ((__int64 (__fastcall *)(__int64, __int64 *))SmbPseReceiveHandlers[v25])(a1, v20);
          if ( v26 )
          {
LABEL_38:
            *(_DWORD *)(a1 + 48) = v26;
            v16 = &NullGenericAndX;
            if ( v22 )
              v16 = v20;
LABEL_40:
            *a4 = v10;
            goto LABEL_41;
          }
        }
LABEL_37:
        v26 = v39;
        goto LABEL_38;
      }
    }
    v16 = (__int64 *)(a1 + 396);
LABEL_51:
    v32 = *(_DWORD *)(*(_QWORD *)(a1 + 896) + 40LL);
    if ( (unsigned int)v10 > v32 )
    {
      *(_DWORD *)(a1 + 48) = -1073741629;
      *a4 = v10;
    }
    else if ( (a8 & 0x400) != 0 && (v33 = a2, (unsigned int)v10 <= a2) && (unsigned int)v10 <= 0x7F )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
        v33 = a2;
      }
      *(_DWORD *)(a1 + 412) = v10;
      *a4 = v10;
      v34 = *(_QWORD *)(a1 + 896);
      if ( (*(_BYTE *)(v34 + 10) & 5) != 0 )
      {
        v35 = *(PVOID *)(v34 + 24);
      }
      else
      {
        v35 = MmMapLockedPagesSpecifyCache((PMDL)v34, 0, MmCached, 0, 0, 0x40000000u);
        v33 = a2;
      }
      if ( v35 )
        memmove(v35, Src, v33);
      *(_DWORD *)(a1 + 48) = -1073741802;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
      }
      *a6 = *(_QWORD *)(a1 + 896);
      *a7 = v32;
      *a4 = 0;
      v8 = -1073741802;
    }
    if ( v9 )
      *(_DWORD *)(a1 + 48) = -1073741629;
    goto LABEL_41;
  }
  v27 = (unsigned __int8)v17[1];
  v16 = (__int64 *)(a1 + 396);
  if ( (unsigned __int8)v27 >= 0x11u )
  {
    *v11 = v10;
    *a6 = 0;
    *a7 = 0;
    *(_DWORD *)(a1 + 48) = -1073741629;
    goto LABEL_41;
  }
  v28 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, unsigned int *, char *, _QWORD *, unsigned int *, __int64 *))SmbPseReceiveHandlers[v27];
  *(_DWORD *)(a1 + 404) = v24;
  v29 = v28(a1, a2, (unsigned int)v10, v11, Src, a6, a7, v20);
  if ( v29 == 1 )
  {
    v8 = -1073741802;
    goto LABEL_41;
  }
  if ( v29 != 2 )
  {
    if ( v29 != 3 )
      goto LABEL_37;
    goto LABEL_74;
  }
  *a4 = v10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
LABEL_41:
  result = v8;
  *(_DWORD *)(a1 + 396) = *(_DWORD *)v16;
  *(_BYTE *)(a1 + 400) = *((_BYTE *)v16 + 4);
  return result;
}

```

## disassembly

```asm
0x140006230  mov     [rsp+arg_18], r9
0x140006235  mov     dword ptr [rsp+Size], edx
0x140006239  push    rbx
0x14000623a  push    rsi
0x14000623b  push    rdi
0x14000623c  push    r12
0x14000623e  push    r13
0x140006240  push    r14
0x140006242  push    r15
0x140006244  sub     rsp, 60h
0x140006248  movzx   r13d, byte ptr [rcx+180h]
0x140006250  xor     r15d, r15d
0x140006253  and     r13b, 1
0x140006257  mov     r12d, r8d
0x14000625a  mov     [rsp+98h+arg_0], r13b
0x140006262  mov     r11, r9
0x140006265  mov     r8d, edx
0x140006268  mov     rsi, rcx
0x14000626b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006272  lea     rbx, WPP_GLOBAL_Control
0x140006279  cmp     rcx, rbx
0x14000627c  jz      short loc_1400062A4
0x14000627e  test    dword ptr [rcx+2Ch], 400h
0x140006285  jnz     loc_1400066BC
0x14000628b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006292  cmp     rcx, rbx
0x140006295  jz      short loc_1400062A4
0x140006297  test    dword ptr [rcx+2Ch], 400h
0x14000629e  jnz     loc_1400066EE
0x1400062a4  mov     [rsp+98h+arg_10], rbp
0x1400062ac  lea     rdi, [rsi+18Ch]
0x1400062b3  test    r13b, r13b
0x1400062b6  jz      loc_1400064D4
0x1400062bc  mov     eax, [rsi+28h]
0x1400062bf  mov     [rsi+30h], eax
0x1400062c2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400062c9  cmp     rcx, rbx
0x1400062cc  jz      short loc_1400062DB
0x1400062ce  test    dword ptr [rcx+2Ch], 400h
0x1400062d5  jnz     loc_14000671F
0x1400062db  movzx   ebp, byte ptr [rdi+1]
0x1400062df  mov     r13d, [rsi+28h]
0x1400062e3  test    r13d, r13d
0x1400062e6  jnz     loc_140006741
0x1400062ec  mov     rbx, rdi
0x1400062ef  cmp     bpl, 0FFh
0x1400062f3  jz      loc_1400064A2
0x1400062f9  movzx   eax, bpl
0x1400062fd  lea     r10, cs:140000000h
0x140006304  shl     rax, 4
0x140006308  lea     rbx, rva SmbPseReceiveModelParameters[r10]
0x14000630f  add     rbx, rax
0x140006312  mov     eax, [rsi+168h]
0x140006318  cmp     eax, [rbx+4]
0x14000631b  jl      loc_140006A82
0x140006321  cmp     eax, [rbx+8]
0x140006324  jg      loc_140006A82
0x14000632a  mov     eax, [rbx+0Ch]
0x14000632d  add     rax, 20h ; ' '
0x140006331  cmp     rax, r12
0x140006334  ja      loc_140006A1A
0x14000633a  mov     r9, [rsp+98h+Src]
0x140006342  movzx   edx, word ptr [rdi+3]
0x140006346  lea     rax, [r12+r9]
0x14000634a  lea     r14, [rdx+r9]
0x14000634e  cmp     r14, rax
0x140006351  jnb     loc_1400069B9
0x140006357  cmp     byte ptr [rdi+1], 0FFh
0x14000635b  jnz     loc_14000654A
0x140006361  mov     [rsi+184h], bpl
0x140006368  movzx   ecx, byte ptr [rbx]
0x14000636b  test    ecx, ecx
0x14000636d  jz      loc_140006783
0x140006373  mov     ebp, ecx
0x140006375  and     ebp, 2
0x140006378  cmp     [r14], r15b
0x14000637b  jz      loc_140006820
0x140006381  test    ebp, ebp
0x140006383  jz      loc_140006820
0x140006389  xor     r8b, r8b
0x14000638c  mov     eax, r13d
0x14000638f  and     eax, 0C0000000h
0x140006394  cmp     eax, 0C0000000h
0x140006399  jz      loc_140006828
0x14000639f  xor     edx, edx
0x1400063a1  mov     [rsp+98h+var_48], edx
0x1400063a5  test    r13d, r13d
0x1400063a8  jnz     loc_14000687D
0x1400063ae  test    cl, 8
0x1400063b1  jnz     short loc_140006417
0x1400063b3  movzx   r13d, [rsp+98h+arg_0]
0x1400063bc  cmp     [rsi+1A8h], r15
0x1400063c3  jz      short loc_1400063CE
0x1400063c5  test    r13b, r13b
0x1400063c8  jz      loc_1400065A7
0x1400063ce  test    cl, 10h
0x1400063d1  jnz     loc_1400068C4
0x1400063d7  call    cs:__imp_KeGetCurrentIrql
0x1400063de  nop     dword ptr [rax+rax+00h]
0x1400063e3  cmp     al, 2
0x1400063e5  jnb     loc_1400065A7
0x1400063eb  movzx   eax, byte ptr [rbx+1]
0x1400063ef  cmp     al, 11h
0x1400063f1  jnb     loc_14000648E
0x1400063f7  lea     rcx, cs:140000000h
0x1400063fe  mov     rdx, r14
0x140006401  mov     rax, (SmbPseReceiveHandlers - 140000000h)[rcx+rax*8]
0x140006409  mov     rcx, rsi
0x14000640c  call    _guard_dispatch_icall
0x140006411  test    eax, eax
0x140006413  jz      short loc_14000648E
0x140006415  jmp     short loc_140006492
0x140006417  movzx   eax, byte ptr [rbx+1]
0x14000641b  mov     rbx, rdi
0x14000641e  cmp     al, 11h
0x140006420  jnb     loc_140006697
0x140006426  mov     r10, (SmbPseReceiveHandlers - 140000000h)[r10+rax*8]
0x14000642e  mov     r8d, r12d
0x140006431  mov     rax, [rsp+98h+arg_30]
0x140006439  mov     rcx, rsi
0x14000643c  mov     [rsp+98h+var_60], r14
0x140006441  mov     [rsp+98h+var_68], rax
0x140006446  mov     rax, [rsp+98h+arg_28]
0x14000644e  mov     qword ptr [rsp+98h+Priority], rax
0x140006453  mov     rax, r10
0x140006456  mov     qword ptr [rsp+98h+BugCheckOnFailure], r9
0x14000645b  mov     r9, r11
0x14000645e  mov     [rsi+194h], edx
0x140006464  mov     edx, dword ptr [rsp+98h+Size]
0x14000646b  call    _guard_dispatch_icall
0x140006470  movzx   ecx, al
0x140006473  sub     ecx, 1
0x140006476  jz      loc_140006686
0x14000647c  sub     ecx, 1
0x14000647f  jz      loc_140006970
0x140006485  cmp     ecx, 1
0x140006488  jz      loc_140006799
0x14000648e  mov     eax, [rsp+98h+var_48]
0x140006492  test    ebp, ebp
0x140006494  mov     [rsi+30h], eax
0x140006497  lea     rbx, NullGenericAndX
0x14000649e  cmovnz  rbx, r14
0x1400064a2  mov     rax, [rsp+98h+arg_18]
0x1400064aa  mov     [rax], r12d
0x1400064ad  mov     ecx, [rbx]
0x1400064af  mov     eax, r15d
0x1400064b2  mov     rbp, [rsp+98h+arg_10]
0x1400064ba  mov     [rdi], ecx
0x1400064bc  movzx   ecx, byte ptr [rbx+4]
0x1400064c0  mov     [rdi+4], cl
0x1400064c3  add     rsp, 60h
0x1400064c7  pop     r15
0x1400064c9  pop     r14
0x1400064cb  pop     r13
0x1400064cd  pop     r12
0x1400064cf  pop     rdi
0x1400064d0  pop     rsi
0x1400064d1  pop     rbx
0x1400064d2  retn
0x1400064d4  mov     rdx, [rsp+98h+Src]
0x1400064dc  lea     r9, [rsi+28h]
0x1400064e0  mov     [rsp+98h+var_68], r11
0x1400064e5  mov     rcx, rsi
0x1400064e8  mov     [rsp+98h+Priority], r8d
0x1400064ed  mov     rbx, rdi
0x1400064f0  mov     [rsi+5B4h], r8d
0x1400064f7  mov     r8, rdi
0x1400064fa  mov     [rsi+5B0h], r12d
0x140006501  mov     [rsp+98h+BugCheckOnFailure], r12d
0x140006506  call    SmbCeParseSmbHeader
0x14000650b  or      word ptr [rsi+180h], 1
0x140006513  mov     [rsi+30h], eax
0x140006516  cmp     eax, 0C0000016h
0x14000651b  jz      loc_1400065AA
0x140006521  test    eax, eax
0x140006523  jnz     short loc_1400064AD
0x140006525  movzx   ebp, byte ptr [rsi+18Dh]
0x14000652c  cmp     bpl, 0FFh
0x140006530  jz      loc_1400064AD
0x140006536  mov     r11, [rsp+98h+arg_18]
0x14000653e  lea     rbx, WPP_GLOBAL_Control
0x140006545  jmp     loc_1400062DF
0x14000654a  test    dx, dx
0x14000654d  jnz     loc_140006361
0x140006553  mov     rax, [rsp+98h+arg_28]
0x14000655b  mov     [r11], r12d
0x14000655e  mov     [rax], r15
0x140006561  mov     rax, [rsp+98h+arg_30]
0x140006569  mov     [rax], r15d
0x14000656c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006573  lea     rax, WPP_GLOBAL_Control
0x14000657a  cmp     rcx, rax
0x14000657d  jz      loc_140006A0B
0x140006583  test    dword ptr [rcx+2Ch], 100h
0x14000658a  jz      loc_140006A0B
0x140006590  movzx   eax, byte ptr [rdi+1]
0x140006594  mov     edx, 2Bh ; '+'
0x140006599  mov     qword ptr [rsp+98h+Priority], rsi
0x14000659e  mov     [rsp+98h+BugCheckOnFailure], eax
0x1400065a2  jmp     loc_1400069FD
0x1400065a7  mov     rbx, rdi
0x1400065aa  mov     rax, [rsi+380h]
0x1400065b1  mov     ebp, [rax+28h]
0x1400065b4  cmp     r12d, ebp
0x1400065b7  ja      loc_1400068D5
0x1400065bd  test    [rsp+98h+arg_38], 400h
0x1400065c8  jz      loc_14000690D
0x1400065ce  mov     edx, dword ptr [rsp+98h+Size]
0x1400065d5  cmp     r12d, edx
0x1400065d8  ja      loc_14000690D
0x1400065de  cmp     r12d, 7Fh
0x1400065e2  ja      loc_14000690D
0x1400065e8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400065ef  lea     rax, WPP_GLOBAL_Control
0x1400065f6  cmp     rcx, rax
0x1400065f9  jz      short loc_140006608
0x1400065fb  test    dword ptr [rcx+2Ch], 400h
0x140006602  jnz     loc_1400068EC
0x140006608  mov     rax, [rsp+98h+arg_18]
0x140006610  mov     [rsi+19Ch], r12d
0x140006617  mov     [rax], r12d
0x14000661a  mov     rcx, [rsi+380h]; MemoryDescriptorList
0x140006621  test    byte ptr [rcx+0Ah], 5
0x140006625  jnz     short loc_140006691
0x140006627  mov     [rsp+98h+Priority], 40000000h; Priority
0x14000662f  xor     r9d, r9d; RequestedAddress
0x140006632  xor     edx, edx; AccessMode
0x140006634  mov     [rsp+98h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x140006639  mov     r8d, 1; CacheType
0x14000663f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140006646  nop     dword ptr [rax+rax+00h]
0x14000664b  mov     edx, dword ptr [rsp+98h+Size]
0x140006652  test    rax, rax
0x140006655  jz      short loc_14000666A
0x140006657  mov     r8d, edx; Size
0x14000665a  mov     rcx, rax; void *
0x14000665d  mov     rdx, [rsp+98h+Src]; Src
0x140006665  call    memmove
0x14000666a  mov     dword ptr [rsi+30h], 0C0000016h
0x140006671  test    r13b, r13b
0x140006674  jz      loc_1400064AD
0x14000667a  mov     dword ptr [rsi+30h], 0C00000C3h
0x140006681  jmp     loc_1400064AD
0x140006686  mov     r15d, 0C0000016h
0x14000668c  jmp     loc_1400064AD
0x140006691  mov     rax, [rcx+18h]
0x140006695  jmp     short loc_140006652
0x140006697  mov     rax, [rsp+98h+arg_28]
0x14000669f  mov     [r11], r12d
0x1400066a2  mov     [rax], r15
0x1400066a5  mov     rax, [rsp+98h+arg_30]
0x1400066ad  mov     [rax], r15d
0x1400066b0  mov     dword ptr [rsi+30h], 0C00000C3h
0x1400066b7  jmp     loc_1400064AD
0x1400066bc  mov     rcx, [rcx+18h]
0x1400066c0  mov     edx, 24h ; '$'
0x1400066c5  mov     [rsp+98h+BugCheckOnFailure], r8d
0x1400066ca  mov     r9d, r12d
0x1400066cd  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x1400066d4  call    WPP_SF_Dd
0x1400066d9  mov     r11, [rsp+98h+arg_18]
0x1400066e1  mov     r8d, dword ptr [rsp+98h+Size]
0x1400066e9  jmp     loc_14000628B
0x1400066ee  mov     r9, [rsi+380h]
0x1400066f5  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x1400066fc  mov     rcx, [rcx+18h]
0x140006700  mov     edx, 25h ; '%'
0x140006705  call    WPP_SF_q
0x14000670a  mov     r11, [rsp+98h+arg_18]
0x140006712  mov     r8d, dword ptr [rsp+98h+Size]
0x14000671a  jmp     loc_1400062A4
0x14000671f  mov     rcx, [rcx+18h]
0x140006723  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x14000672a  mov     edx, 26h ; '&'
0x14000672f  call    WPP_SF_
0x140006734  mov     r11, [rsp+98h+arg_18]
0x14000673c  jmp     loc_1400062DB
0x140006741  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006748  cmp     rcx, rbx
0x14000674b  jz      loc_1400062EC
0x140006751  test    dword ptr [rcx+2Ch], 400h
0x140006758  jz      loc_1400062EC
0x14000675e  mov     rcx, [rcx+18h]
0x140006762  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x140006769  mov     edx, 27h ; '''
0x14000676e  mov     r9d, r13d
0x140006771  call    WPP_SF_d
0x140006776  mov     r11, [rsp+98h+arg_18]
0x14000677e  jmp     loc_1400062EC
0x140006783  cmp     [rsi+1A8h], r15
0x14000678a  jz      short loc_1400067A7
0x14000678c  cmp     [rsp+98h+arg_0], r15b
0x140006794  jnz     short loc_1400067A7
0x140006796  mov     rbx, rdi
0x140006799  movzx   r13d, [rsp+98h+arg_0]
0x1400067a2  jmp     loc_1400065AA
0x1400067a7  cmp     bpl, 2Eh ; '.'
0x1400067ab  jz      loc_140006373
0x1400067b1  mov     rbx, [rsi+50h]
0x1400067b5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
  ... truncated ...
```
