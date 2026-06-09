# CscEnQueryDirectory

- ea: `0x1400724d0`
- end: `0x140072bad`
- name: `CscEnQueryDirectory`
- size: `1757`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140011ad0`

## callees

- `0x1400052c0`
- `0x140005390`
- `0x140007420`
- `0x14000cac0`
- `0x14000f6a8`
- `0x140012614`
- `0x140018930`
- `0x14001a494`
- `0x14001a548`
- `0x14001a69c`
- `0x140028820`
- `0x140028bdc`
- `0x1400724d0`
- `0x140072bc0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140072891`
- `ntoskrnl!ExAllocatePool2` at `0x140072891`

## pseudocode

```c
__int64 __fastcall CscEnQueryDirectory(
        __int64 a1,
        unsigned int *a2,
        char *a3,
        unsigned int a4,
        int a5,
        char a6,
        unsigned __int64 a7,
        __int64 a8,
        __int64 a9)
{
  char v9; // r11
  int v10; // r8d
  unsigned int v13; // r12d
  __int64 v14; // rsi
  char v15; // r15
  unsigned __int64 LowLimit; // r13
  unsigned int v17; // edi
  unsigned int v18; // ecx
  __int64 v19; // rcx
  int v20; // edi
  int v21; // esi
  int v22; // eax
  unsigned int v23; // ebp
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rdi
  unsigned __int16 v28; // ax
  int *v29; // rax
  _DWORD *v30; // r14
  __int64 v31; // rcx
  int *v32; // r8
  _DWORD *i; // rcx
  _DWORD *v34; // rsi
  __int64 v35; // rdi
  unsigned __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rax
  unsigned int v39; // eax
  unsigned int v40; // edi
  __int64 Pool2; // rax
  int v42; // r9d
  __int64 v43; // r10
  int v44; // r8d
  char v45[8]; // [rsp+20h] [rbp-B8h]
  size_t Size; // [rsp+30h] [rbp-A8h]
  unsigned __int16 v47; // [rsp+40h] [rbp-98h]
  __int64 v48; // [rsp+70h] [rbp-68h] BYREF
  _QWORD v49[4]; // [rsp+78h] [rbp-60h] BYREF
  unsigned int v50; // [rsp+E0h] [rbp+8h]
  char *v52; // [rsp+F0h] [rbp+18h]
  int v53; // [rsp+F8h] [rbp+20h]
  unsigned int v54; // [rsp+110h] [rbp+38h]

  v52 = a3;
  v9 = (char)a3;
  v10 = 0;
  v13 = a4;
  v53 = 0;
  LODWORD(v48) = 0;
  v14 = a9;
  v15 = a8;
  LowLimit = a7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    if ( a1 )
    {
      v42 = *(_DWORD *)(a1 + 16);
      v43 = *(_QWORD *)(a1 + 8);
    }
    else
    {
      LOBYTE(v42) = 0;
      LOBYTE(v43) = 0;
    }
    v17 = a5;
    v44 = 89;
    if ( !a9 )
      v44 = 78;
    WPP_SF_qqDqDDDZDc(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a2, v44, a1, v43, v42, v9, a4, a5, a6, a7, a8, v44);
    v10 = 0;
  }
  else
  {
    v17 = a5;
  }
  if ( a1 )
  {
    switch ( v17 )
    {
      case 3u:
        v50 = 94;
        v18 = 94;
LABEL_7:
        v54 = 60;
        goto LABEL_8;
      case 1u:
        v18 = 64;
        v50 = 64;
        goto LABEL_7;
      case 2u:
        v18 = 68;
        v50 = 68;
        goto LABEL_7;
      case 0xCu:
        v18 = 12;
        v54 = 8;
        v50 = 12;
LABEL_8:
        if ( a4 <= v18 )
        {
          v20 = -2147483643;
          v21 = 1122;
          goto LABEL_20;
        }
        CscEnpMainAcquireExclusive(*(_QWORD *)(a1 + 8));
        v19 = *(_QWORD *)(a1 + 8);
        if ( (*(_DWORD *)(a1 + 16) & 0x100) == 0 )
        {
          v20 = -1073741811;
          v21 = 1142;
LABEL_25:
          CscEnpMainRelease(v19);
LABEL_19:
          v10 = v53;
          goto LABEL_20;
        }
        v20 = CscEnpCheckState(v19);
        if ( v20 < 0 )
        {
          v21 = 1146;
        }
        else
        {
          if ( !v14 )
          {
LABEL_12:
            *(_WORD *)(a1 + 56) = 0;
LABEL_34:
            if ( *(_QWORD *)(a1 + 32) )
            {
              v29 = (int *)(a1 + 40);
              goto LABEL_36;
            }
            v39 = 616;
            if ( !a6 )
              v39 = 2464;
            v40 = v39;
            Pool2 = ExAllocatePool2(258, v39, 557871939);
            *(_QWORD *)(a1 + 32) = Pool2;
            if ( Pool2 )
            {
              *(_DWORD *)(a1 + 16) |= 0x200u;
              v29 = (int *)(a1 + 40);
              *(_DWORD *)(a1 + 40) = v40;
              *(_DWORD *)(a1 + 44) = 0;
LABEL_36:
              v30 = 0;
              if ( v15 )
              {
                v31 = *(_QWORD *)(a1 + 8);
                *(_QWORD *)(a1 + 48) = *(_QWORD *)(v31 + 196);
                CscEnpOverrideShareInformationIfNeeded(v31, a1 + 48);
                v32 = (int *)(a1 + 40);
              }
              else
              {
                v32 = v29;
              }
              i = (_DWORD *)(a1 + 44);
LABEL_39:
              v34 = i;
              if ( (*(_DWORD *)(a1 + 16) & 0x200) == 0 )
                goto LABEL_42;
              if ( (int)CscStorepLowIoQueryDirectoryFilePoster(
                          *(_QWORD *)(a1 + 24),
                          *(_QWORD *)(a1 + 32),
                          *v32,
                          37,
                          0,
                          LowLimit,
                          v15,
                          (__int64)&v48) >= 0 )
              {
                *(_DWORD *)(a1 + 16) &= ~0x200u;
                *v34 = 0;
LABEL_42:
                for ( i = (_DWORD *)(a1 + 44); ; i = v34 )
                {
                  if ( (*(_DWORD *)(a1 + 16) & 0x200) != 0 )
                  {
                    LowLimit = 0;
                    v32 = (int *)(a1 + 40);
                    v15 = 0;
                    goto LABEL_39;
                  }
                  v35 = *(_QWORD *)(a1 + 32) + (unsigned int)*v34;
                  v36 = *(_QWORD *)(a1 + 8);
                  v47 = *(_WORD *)(a1 + 56);
                  LODWORD(Size) = v50;
                  LOBYTE(a8) = 0;
                  v37 = CscEnpQueryDirectoryProcessSingleEntry(
                          v36,
                          (_QWORD *)(a1 + 48),
                          v35,
                          v52,
                          v13,
                          a5,
                          Size,
                          v54,
                          v47,
                          (char *)&a8,
                          &v48);
                  if ( v37 < 0 )
                  {
                    v49[0] = 0;
                    v49[1] = v35 + 104;
                    WORD1(v49[0]) = *(_WORD *)(v35 + 60);
                    LOWORD(v49[0]) = WORD1(v49[0]);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
                    {
                      WPP_SF_ZD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        18,
                        (unsigned int)WPP_0ffa5d83052038872389acecfcbed6d0_Traceguids,
                        (unsigned int)v49,
                        v37);
                    }
                    v38 = 0;
                    LODWORD(v48) = 0;
                  }
                  else
                  {
                    if ( (_BYTE)a8 )
                    {
                      v20 = -2147483643;
                      v21 = 1348;
                      if ( v53 )
                        v20 = 0;
                      goto LABEL_17;
                    }
                    v38 = (unsigned int)v48;
                  }
                  if ( *(_DWORD *)v35 )
                    *v34 += *(_DWORD *)v35;
                  else
                    *(_DWORD *)(a1 + 16) |= 0x200u;
                  if ( (_DWORD)v38 )
                  {
                    ++v53;
                    v13 -= v38;
                    v30 = v52;
                    if ( a6 )
                    {
                      v20 = 0;
                      v21 = 1383;
                      goto LABEL_17;
                    }
                    if ( v13 <= v50 )
                    {
                      v20 = 0;
                      v21 = 1395;
                      goto LABEL_17;
                    }
                    v52 += v38;
                  }
                }
              }
              v22 = 0;
              v21 = 1260;
              if ( !v53 )
                v22 = -2147483642;
              v20 = v22;
LABEL_17:
              CscEnpMainRelease(*(_QWORD *)(a1 + 8));
              if ( v30 )
                *v30 = 0;
              goto LABEL_19;
            }
            v20 = -1073741670;
            v21 = 1211;
            goto LABEL_68;
          }
          v25 = *(_QWORD *)(a1 + 8);
          v26 = *(unsigned int *)(v25 + 16);
          if ( (unsigned int)v26 < 2 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_0ffa5d83052038872389acecfcbed6d0_Traceguids, v26);
            }
            goto LABEL_12;
          }
          v27 = *(_QWORD *)(*(_QWORD *)(v25 + 8) + 56LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            v45[0] = 78;
            WPP_SF_qcq(
              WPP_GLOBAL_Control->AttachedDevice,
              17,
              WPP_238132d70db8346a917bc6570ec5eca2_Traceguids,
              v27,
              *(_DWORD *)v45,
              v14);
          }
          v28 = CscSidMappLookupIndexBySid(v27, v14);
          *(_WORD *)(a1 + 56) = v28;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_DDd(
              WPP_GLOBAL_Control->AttachedDevice,
              18,
              WPP_238132d70db8346a917bc6570ec5eca2_Traceguids,
              v28,
              0,
              1077);
          }
          if ( *(_WORD *)(a1 + 56) )
            goto LABEL_34;
          v20 = -2147483642;
          v21 = 1186;
        }
LABEL_68:
        v19 = *(_QWORD *)(a1 + 8);
        goto LABEL_25;
      case 0x25u:
        v18 = 104;
        v50 = 104;
        goto LABEL_7;
      case 0x26u:
        v18 = 80;
        v50 = 80;
        goto LABEL_7;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_0ffa5d83052038872389acecfcbed6d0_Traceguids, v17);
      v10 = 0;
    }
    v20 = -1073741811;
    v21 = 1111;
  }
  else
  {
    v20 = -1073741811;
    v21 = 1083;
  }
LABEL_20:
  v23 = a4 - v13;
  *a2 = v23;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    *(_DWORD *)v45 = v10;
    WPP_SF_DDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      WPP_0ffa5d83052038872389acecfcbed6d0_Traceguids,
      v23,
      *(_QWORD *)v45,
      v20,
      v21);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x1400724d0  mov     rax, rsp
0x1400724d3  mov     [rax+18h], r8
0x1400724d7  mov     [rax+10h], rdx
0x1400724db  push    rbp
0x1400724dc  push    rsi
0x1400724dd  push    rdi
0x1400724de  sub     rsp, 0C0h
0x1400724e5  mov     [rax-20h], rbx
0x1400724e9  mov     r11, r8
0x1400724ec  mov     [rax-28h], r12
0x1400724f0  xor     r8d, r8d
0x1400724f3  mov     [rax-30h], r13
0x1400724f7  mov     ebp, r9d
0x1400724fa  mov     [rax-38h], r14
0x1400724fe  mov     rbx, rcx
0x140072501  mov     [rax-40h], r15
0x140072505  mov     r12d, r9d
0x140072508  mov     [rsp+0D8h+arg_18], r8d
0x140072510  mov     [rax-68h], r8d
0x140072514  mov     rcx, cs:WPP_GLOBAL_Control
0x14007251b  lea     rax, WPP_GLOBAL_Control
0x140072522  mov     rsi, [rsp+0D8h+arg_40]
0x14007252a  movzx   r15d, byte ptr [rsp+0D8h+arg_38]
0x140072533  mov     r13, [rsp+0D8h+arg_30]
0x14007253b  movzx   r14d, [rsp+0D8h+arg_28]
0x140072544  cmp     rcx, rax
0x140072547  jz      short loc_140072556
0x140072549  test    dword ptr [rcx+2Ch], 20000h
0x140072550  jnz     loc_140072952
0x140072556  mov     edi, [rsp+0D8h+arg_20]
0x14007255d  test    rbx, rbx
0x140072560  jz      short loc_1400725CB
0x140072562  cmp     edi, 3
0x140072565  jnz     loc_1400729C4
0x14007256b  mov     dword ptr [rsp+0D8h+arg_0], 5Eh ; '^'
0x140072576  mov     ecx, 5Eh ; '^'
0x14007257b  mov     dword ptr [rsp+0D8h+arg_30], 3Ch ; '<'
0x140072586  cmp     ebp, ecx
0x140072588  jbe     loc_140072A92
0x14007258e  mov     rcx, [rbx+8]
0x140072592  call    CscEnpMainAcquireExclusive
0x140072597  test    dword ptr [rbx+10h], 100h
0x14007259e  mov     rcx, [rbx+8]
0x1400725a2  jz      loc_14007266F
0x1400725a8  call    CscEnpCheckState
0x1400725ad  mov     edi, eax
0x1400725af  test    eax, eax
0x1400725b1  js      loc_140072AA1
0x1400725b7  test    rsi, rsi
0x1400725ba  jnz     loc_140072680
0x1400725c0  xor     eax, eax
0x1400725c2  mov     [rbx+38h], ax
0x1400725c6  jmp     loc_1400726FD
0x1400725cb  mov     edi, 0C000000Dh
0x1400725d0  mov     esi, 43Bh
0x1400725d5  jmp     short loc_14007260C
0x1400725d7  xor     eax, eax
0x1400725d9  mov     edi, 80000006h
0x1400725de  cmp     [rsp+0D8h+arg_18], eax
0x1400725e5  mov     esi, 4ECh
0x1400725ea  cmovbe  eax, edi
0x1400725ed  mov     edi, eax
0x1400725ef  mov     rcx, [rbx+8]
0x1400725f3  call    CscEnpMainRelease
0x1400725f8  test    r14, r14
0x1400725fb  jz      short loc_140072604
0x1400725fd  mov     dword ptr [r14], 0
0x140072604  mov     r8d, [rsp+0D8h+arg_18]
0x14007260c  mov     rax, [rsp+0D8h+arg_8]
0x140072614  sub     ebp, r12d
0x140072617  mov     [rax], ebp
0x140072619  mov     rcx, cs:WPP_GLOBAL_Control
0x140072620  lea     rax, WPP_GLOBAL_Control
0x140072627  mov     r15, [rsp+0D8h+var_40]
0x14007262f  mov     r14, [rsp+0D8h+var_38]
0x140072637  mov     r13, [rsp+0D8h+var_30]
0x14007263f  mov     r12, [rsp+0D8h+var_28]
0x140072647  mov     rbx, [rsp+0D8h+var_20]
0x14007264f  cmp     rcx, rax
0x140072652  jz      short loc_140072661
0x140072654  test    dword ptr [rcx+2Ch], 20000h
0x14007265b  jnz     loc_140072B83
0x140072661  mov     eax, edi
0x140072663  add     rsp, 0C0h
0x14007266a  pop     rdi
0x14007266b  pop     rsi
0x14007266c  pop     rbp
0x14007266d  retn
0x14007266f  mov     edi, 0C000000Dh
0x140072674  mov     esi, 476h
0x140072679  call    CscEnpMainRelease
0x14007267e  jmp     short loc_140072604
0x140072680  mov     rdx, [rbx+8]
0x140072684  mov     r9d, [rdx+10h]
0x140072688  test    r9d, r9d
0x14007268b  jz      loc_1400728F9
0x140072691  cmp     r9d, 1
0x140072695  jz      loc_1400728F9
0x14007269b  mov     rax, [rdx+8]
0x14007269f  mov     rdi, [rax+38h]
0x1400726a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400726aa  lea     rax, WPP_GLOBAL_Control
0x1400726b1  cmp     rcx, rax
0x1400726b4  jz      short loc_1400726C3
0x1400726b6  test    dword ptr [rcx+2Ch], 40000h
0x1400726bd  jnz     loc_140072AAB
0x1400726c3  mov     rdx, rsi
0x1400726c6  mov     rcx, rdi
0x1400726c9  call    CscSidMappLookupIndexBySid
0x1400726ce  mov     [rbx+38h], ax
0x1400726d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400726d9  lea     rdx, WPP_GLOBAL_Control
0x1400726e0  cmp     rcx, rdx
0x1400726e3  jz      short loc_1400726F2
0x1400726e5  test    dword ptr [rcx+2Ch], 40000h
0x1400726ec  jnz     loc_140072AD2
0x1400726f2  cmp     word ptr [rbx+38h], 0
0x1400726f7  jz      loc_140072B00
0x1400726fd  cmp     qword ptr [rbx+20h], 0
0x140072702  jz      loc_140072872
0x140072708  lea     rax, [rbx+28h]
0x14007270c  xor     r14d, r14d
0x14007270f  test    r15b, r15b
0x140072712  jz      loc_14007294A
0x140072718  mov     rcx, [rbx+8]
0x14007271c  lea     rdx, [rbx+30h]
0x140072720  mov     rax, [rcx+0C4h]
0x140072727  mov     [rdx], rax
0x14007272a  call    CscEnpOverrideShareInformationIfNeeded
0x14007272f  lea     r8, [rbx+28h]
0x140072733  lea     rcx, [rbx+2Ch]
0x140072737  test    dword ptr [rbx+10h], 200h
0x14007273e  mov     rsi, rcx
0x140072741  jz      short loc_140072787
0x140072743  mov     r8d, [r8]; int
0x140072746  lea     rax, [rsp+0D8h+var_68]
0x14007274b  mov     rdx, [rbx+20h]; int
0x14007274f  mov     r9d, 25h ; '%'; int
0x140072755  mov     rcx, [rbx+18h]; int
0x140072759  mov     [rsp+0D8h+var_A0], rax; __int64
0x14007275e  mov     byte ptr [rsp+0D8h+Size], r15b; char
0x140072763  mov     [rsp+0D8h+LowLimit], r13; LowLimit
0x140072768  mov     [rsp+0D8h+var_B8], 0; char
0x14007276d  call    CscStorepLowIoQueryDirectoryFilePoster
0x140072772  test    eax, eax
0x140072774  js      loc_1400725D7
0x14007277a  and     dword ptr [rbx+10h], 0FFFFFDFFh
0x140072781  mov     dword ptr [rsi], 0
0x140072787  lea     rcx, [rbx+2Ch]
0x14007278b  test    dword ptr [rbx+10h], 200h
0x140072792  jnz     loc_1400728C3
0x140072798  mov     edi, [rsi]
0x14007279a  lea     rax, [rsp+0D8h+var_68]
0x14007279f  add     rdi, [rbx+20h]
0x1400727a3  lea     rdx, [rbx+30h]; int
0x1400727a7  mov     r15d, dword ptr [rsp+0D8h+arg_0]
0x1400727af  mov     r8, rdi; int
0x1400727b2  mov     r13, qword ptr [rsp+0D8h+arg_10]
0x1400727ba  mov     rcx, [rbx+8]; int
0x1400727be  mov     r9, r13; int
0x1400727c1  mov     [rsp+0D8h+var_88], rax; __int64
0x1400727c6  lea     rax, [rsp+0D8h+arg_38]
0x1400727ce  mov     [rsp+0D8h+var_90], rax; __int64
0x1400727d3  movzx   eax, word ptr [rbx+38h]
0x1400727d7  mov     [rsp+0D8h+var_98], ax; __int16
0x1400727dc  mov     eax, dword ptr [rsp+0D8h+arg_30]
0x1400727e3  mov     dword ptr [rsp+0D8h+var_A0], eax; int
0x1400727e7  mov     eax, [rsp+0D8h+arg_20]
0x1400727ee  mov     dword ptr [rsp+0D8h+Size], r15d; Size
0x1400727f3  mov     dword ptr [rsp+0D8h+LowLimit], eax; int
0x1400727f7  mov     dword ptr [rsp+0D8h+var_B8], r12d; int
0x1400727fc  mov     byte ptr [rsp+0D8h+arg_38], 0
0x140072804  call    CscEnpQueryDirectoryProcessSingleEntry
0x140072809  mov     r8d, eax
0x14007280c  test    eax, eax
0x14007280e  js      loc_140072B0F
0x140072814  cmp     byte ptr [rsp+0D8h+arg_38], 0
0x14007281c  jnz     loc_1400728D2
0x140072822  mov     eax, dword ptr [rsp+0D8h+var_68]
0x140072826  mov     ecx, [rdi]
0x140072828  test    ecx, ecx
0x14007282a  jz      short loc_140072869
0x14007282c  add     [rsi], ecx
0x14007282e  test    eax, eax
0x140072830  jz      short loc_140072861
0x140072832  inc     [rsp+0D8h+arg_18]
0x140072839  sub     r12d, eax
0x14007283c  cmp     [rsp+0D8h+arg_28], 0
0x140072844  mov     r14, r13
0x140072847  jnz     loc_1400728ED
0x14007284d  cmp     r12d, r15d
0x140072850  jbe     loc_140072B77
0x140072856  add     r13, rax
0x140072859  mov     qword ptr [rsp+0D8h+arg_10], r13
0x140072861  mov     rcx, rsi
0x140072864  jmp     loc_14007278B
0x140072869  or      dword ptr [rbx+10h], 200h
0x140072870  jmp     short loc_14007282E
0x140072872  mov     eax, 268h
0x140072877  mov     ecx, 9A0h
0x14007287c  test    r14b, r14b
0x14007287f  mov     r8d, 21407343h
0x140072885  cmovz   eax, ecx
0x140072888  mov     ecx, 102h
0x14007288d  mov     edx, eax
0x14007288f  mov     edi, eax
0x140072891  call    cs:__imp_ExAllocatePool2
0x140072898  nop     dword ptr [rax+rax+00h]
0x14007289d  mov     [rbx+20h], rax
0x1400728a1  test    rax, rax
0x1400728a4  jz      loc_140072937
0x1400728aa  or      dword ptr [rbx+10h], 200h
0x1400728b1  lea     rax, [rbx+28h]
0x1400728b5  mov     [rax], edi
0x1400728b7  mov     dword ptr [rbx+2Ch], 0
0x1400728be  jmp     loc_14007270C
0x1400728c3  xor     r13d, r13d
0x1400728c6  lea     r8, [rbx+28h]
0x1400728ca  xor     r15b, r15b
0x1400728cd  jmp     loc_140072737
0x1400728d2  xor     eax, eax
0x1400728d4  mov     edi, 80000005h
0x1400728d9  cmp     [rsp+0D8h+arg_18], eax
0x1400728e0  mov     esi, 544h
0x1400728e5  cmovnz  edi, eax
0x1400728e8  jmp     loc_1400725EF
0x1400728ed  xor     edi, edi
0x1400728ef  mov     esi, 567h
0x1400728f4  jmp     loc_1400725EF
0x1400728f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140072900  lea     rax, WPP_GLOBAL_Control
0x140072907  cmp     rcx, rax
0x14007290a  jz      loc_1400725C0
0x140072910  test    dword ptr [rcx+2Ch], 40000h
0x140072917  jz      loc_1400725C0
0x14007291d  mov     rcx, [rcx+18h]
0x140072921  lea     r8, WPP_0ffa5d83052038872389acecfcbed6d0_Traceguids
0x140072928  mov     edx, 11h
0x14007292d  call    WPP_SF_d
0x140072932  jmp     loc_1400725C0
0x140072937  mov     edi, 0C000009Ah
0x14007293c  mov     esi, 4BBh
0x140072941  mov     rcx, [rbx+8]
0x140072945  jmp     loc_140072679
0x14007294a  mov     r8, rax
0x14007294d  jmp     loc_140072733
0x140072952  test    rbx, rbx
0x140072955  jz      short loc_140072961
0x140072957  mov     r9d, [rbx+10h]
0x14007295b  mov     r10, [rbx+8]
0x14007295f  jmp     short loc_140072967
0x140072961  xor     r9d, r9d
0x140072964  xor     r10d, r10d
0x140072967  mov     edi, [rsp+0D8h+arg_20]
0x14007296e  test    rsi, rsi
0x140072971  mov     rcx, [rcx+18h]
0x140072975  mov     eax, 4Eh ; 'N'
0x14007297a  mov     r8d, 59h ; 'Y'
0x140072980  cmovz   r8d, eax
0x140072984  mov     [rsp+0D8h+var_78], r8b
0x140072989  mov     [rsp+0D8h+var_80], r15d
0x14007298e  mov     [rsp+0D8h+var_88], r13
0x140072993  mov     dword ptr [rsp+0D8h+var_90], r14d
0x140072998  mov     dword ptr [rsp+0D8h+var_98], edi
0x14007299c  mov     dword ptr [rsp+0D8h+var_A0], ebp
0x1400729a0  mov     [rsp+0D8h+Size], r11
0x1400729a5  mov     dword ptr [rsp+0D8h+LowLimit], r9d
0x1400729aa  mov     r9, rbx
0x1400729ad  mov     qword ptr [rsp+0D8h+var_B8], r10
0x1400729b2  call    WPP_SF_qqDqDDDZDc
0x1400729b7  mov     r8d, [rsp+0D8h+arg_18]
0x1400729bf  jmp     loc_14007255D
0x1400729c4  mov     ecx, edi
0x1400729c6  sub     ecx, 1
0x1400729c9  jz      loc_140072A81
0x1400729cf  sub     ecx, 1
0x1400729d2  jz      loc_140072A70
0x1400729d8  sub     ecx, 0Ah
0x1400729db  jz      short loc_140072A54
0x1400729dd  sub     ecx, 19h
0x1400729e0  jz      short loc_140072A43
0x1400729e2  cmp     ecx, 1
0x1400729e5  jz      short loc_140072A32
0x1400729e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400729ee  lea     rdx, WPP_GLOBAL_Control
0x1400729f5  cmp     rcx, rdx
0x1400729f8  jz      short loc_140072A23
0x1400729fa  test    dword ptr [rcx+2Ch], 40000h
0x140072a01  jz      short loc_140072A23
0x140072a03  mov     rcx, [rcx+18h]
0x140072a07  lea     r8, WPP_0ffa5d83052038872389acecfcbed6d0_Traceguids
0x140072a0e  mov     edx, 0Ah
0x140072a13  mov     r9d, edi
0x140072a16  call    WPP_SF_d
0x140072a1b  mov     r8d, [rsp+0D8h+arg_18]
0x140072a23  mov     edi, 0C000000Dh
0x140072a28  mov     esi, 457h
0x140072a2d  jmp     loc_14007260C
0x140072a32  mov     ecx, 50h ; 'P'
0x140072a37  mov     dword ptr [rsp+0D8h+arg_0], ecx
  ... truncated ...
```
