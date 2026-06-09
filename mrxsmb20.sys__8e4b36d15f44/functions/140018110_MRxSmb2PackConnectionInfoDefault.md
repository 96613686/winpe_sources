# MRxSmb2PackConnectionInfoDefault

- ea: `0x140018110`
- end: `0x14001899f`
- name: `MRxSmb2PackConnectionInfoDefault`
- size: `2191`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *, unsigned int *, int, unsigned int *, char)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x140018080`

## callees

- `0x1400104c0`
- `0x1400122d0`
- `0x140018110`
- `0x1400282b0`
- `0x14002a9ac`
- `0x140030544`
- `0x14003081c`
- `0x140030bf0`
- `0x140030c84`
- `0x140037190`
- `0x1400372c0`
- `0x140050280`
- `0x1400502e4`
- `0x14005032c`
- `0x140050370`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400188f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400188f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037c18`
- `ntoskrnl!ExAllocatePool2` at `0x14001825e`
- `ntoskrnl!ExAllocatePool2` at `0x14001825e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400187e2`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400187e2`
- `ntoskrnl!KeBugCheckEx` at `0x140018769`
- `ntoskrnl!KeBugCheckEx` at `0x140018769`
- `mrxsmb!SmbCeTranslateObjectState` at `0x1400183ed`
- `mrxsmb!SmbCeTranslateObjectState` at `0x1400183ed`
- `mrxsmb!VctReferenceEndpoint` at `0x1400187b9`
- `mrxsmb!VctReferenceEndpoint` at `0x1400187b9`
- `mrxsmb!VctDereferenceEndpoint` at `0x1400188d8`
- `mrxsmb!VctDereferenceEndpoint` at `0x140037bfa`
- `mrxsmb!VctDereferenceEndpoint` at `0x1400188d8`
- `mrxsmb!VctDereferenceEndpoint` at `0x140037bfa`
- `mrxsmb!MRxSmbUpdateNetRootState` at `0x1400183ba`
- `mrxsmb!MRxSmbUpdateNetRootState` at `0x1400183ba`

## pseudocode

```c
__int64 __fastcall MRxSmb2PackConnectionInfoDefault(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        unsigned int *a4,
        int a5,
        unsigned int *a6,
        char a7)
{
  unsigned int v7; // r14d
  __int64 v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // r12
  __int64 v11; // r13
  __int64 v12; // r8
  unsigned int v13; // r9d
  int ConnectInfoLevel4Fields; // ebx
  unsigned int v15; // edi
  _WORD *Pool2; // rcx
  __int64 v17; // r15
  __int64 v18; // r14
  char v19; // r12
  char v20; // al
  __int64 v21; // rdx
  _DWORD *v22; // rcx
  char v23; // al
  __int64 v24; // rdx
  _DWORD *v25; // rcx
  char v26; // di
  unsigned __int8 v27; // al
  _DWORD *v28; // rcx
  char v29; // al
  __int64 v30; // rdx
  _DWORD *v31; // rcx
  char v32; // al
  void *v33; // rdx
  void *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r8
  int v37; // eax
  int v38; // eax
  char v39; // al
  _DWORD *v40; // rcx
  int v41; // esi
  __int64 v42; // rdi
  char v43; // al
  _WORD *v44; // rcx
  char v45; // cl
  __int64 v46; // rdx
  char ConnectInfoLevel3Fields; // di
  __int64 v48; // r9
  KIRQL v49; // r14
  _QWORD *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rdx
  _QWORD **v53; // r8
  _QWORD *v54; // rax
  _QWORD *v55; // rdx
  _QWORD *v56; // rdx
  __int64 v57; // r15
  __int64 v58; // rax
  char v60; // [rsp+38h] [rbp-D0h]
  unsigned int v61; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v62; // [rsp+54h] [rbp-B4h] BYREF
  int v63; // [rsp+58h] [rbp-B0h]
  __int64 v64; // [rsp+60h] [rbp-A8h]
  __int64 v65; // [rsp+68h] [rbp-A0h]
  int v66; // [rsp+70h] [rbp-98h]
  __int64 v67; // [rsp+78h] [rbp-90h]
  __int64 v68; // [rsp+80h] [rbp-88h]
  int v69; // [rsp+88h] [rbp-80h]
  int v70; // [rsp+8Ch] [rbp-7Ch]
  int v71; // [rsp+90h] [rbp-78h]
  int v72; // [rsp+94h] [rbp-74h]
  int v73; // [rsp+98h] [rbp-70h]
  int v74; // [rsp+9Ch] [rbp-6Ch]
  __int64 v75; // [rsp+A8h] [rbp-60h]
  __int64 v76; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v77; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD *v78; // [rsp+C8h] [rbp-40h]

  v7 = a2;
  v8 = a1;
  v77 = 0;
  v9 = *(_QWORD *)(a1 + 32);
  v10 = *(_QWORD *)(a1 + 40);
  v65 = v10;
  v75 = v10;
  v11 = *a3;
  v12 = *a6;
  v62 = *a6;
  v13 = *a4;
  v61 = v13;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqdqdd(WPP_GLOBAL_Control->AttachedDevice, 10, v12, a1, v10, a2, v11, v13, v12);
  }
  if ( v10 )
  {
    if ( v7 > 2 && *(_DWORD *)(*(_QWORD *)(v10 + 416) + 12LL) )
    {
      ConnectInfoLevel4Fields = -1073741790;
      goto LABEL_145;
    }
    ConnectInfoLevel4Fields = 0;
    if ( v7 )
    {
      switch ( v7 )
      {
        case 1u:
          v15 = 32;
          break;
        case 2u:
          v15 = 96;
          break;
        case 3u:
          v15 = 240;
          break;
        case 4u:
          v15 = 64;
          break;
        default:
          v15 = 0;
          ConnectInfoLevel4Fields = -1073741821;
          break;
      }
    }
    else
    {
      v15 = 24;
    }
    if ( ConnectInfoLevel4Fields < 0 )
    {
LABEL_144:
      v8 = a1;
      goto LABEL_145;
    }
    if ( v61 < v15 )
    {
      ConnectInfoLevel4Fields = -1073741789;
      goto LABEL_144;
    }
    Pool2 = (_WORD *)ExAllocatePool2(66, *(unsigned __int16 *)(v9 + 216) + 2LL, 1834185806);
    *((_QWORD *)&v77 + 1) = Pool2;
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_a17d72f4c36c3a1a53f0302036e7f0a6_Traceguids);
      }
      ConnectInfoLevel4Fields = -1073741670;
      goto LABEL_144;
    }
    v64 = 0;
    v17 = *(_QWORD *)(v10 + 416);
    v18 = *(_QWORD *)(v17 + 384);
    v68 = *(_QWORD *)(v18 + 24);
    v67 = v11 + v15;
    v76 = v67;
    v62 += v15;
    v61 -= v15;
    if ( a2 >= 4 )
    {
      v19 = a7;
      v41 = a5;
      goto LABEL_132;
    }
    *Pool2 = 92;
    memmove(Pool2 + 1, *(const void **)(v9 + 224), *(unsigned __int16 *)(v9 + 216));
    LOWORD(v77) = *(_WORD *)(v9 + 216) + 2;
    WORD1(v77) = v77;
    v19 = a7;
    if ( a7 )
    {
      v69 = 0;
      v20 = 0;
    }
    else
    {
      v69 = 1;
      v20 = 1;
    }
    v21 = *(unsigned int *)(v9 + 192);
    v22 = (_DWORD *)(v11 + 16);
    if ( v20 )
      RtlWriteULongToUser(v22, v21);
    else
      *v22 = v21;
    if ( a2 )
    {
      if ( a7 )
      {
        v70 = 0;
        v23 = 0;
      }
      else
      {
        v70 = 1;
        v23 = 1;
      }
      v24 = *(unsigned int *)(v9 + 80);
      v25 = (_DWORD *)(v11 + 20);
      if ( v23 )
        RtlWriteULongToUser(v25, v24);
      else
        *v25 = v24;
      MRxSmbUpdateNetRootState(v9);
      if ( a7 )
      {
        v71 = 0;
        v26 = 0;
      }
      else
      {
        v71 = 1;
        v26 = 1;
      }
      v27 = SmbCeTranslateObjectState(*(unsigned int *)(v65 + 12));
      v28 = (_DWORD *)(v11 + 24);
      if ( v26 )
        RtlWriteULongToUser(v28, v27);
      else
        *v28 = v27;
      if ( a7 )
      {
        v72 = 0;
        v29 = 0;
      }
      else
      {
        v72 = 1;
        v29 = 1;
      }
      v30 = *(unsigned int *)(v9 + 64);
      v31 = (_DWORD *)(v11 + 28);
      if ( v29 )
        RtlWriteULongToUser(v31, v30);
      else
        *v31 = v30;
    }
    if ( a2 <= 1 )
    {
LABEL_80:
      v41 = a5;
      v42 = v67;
      v43 = PackStringIntoConnectInfo(v11, (unsigned int)&v77, v67, (unsigned int)&v61, a5, (__int64)&v62, a7);
      v7 = a2;
      if ( !v43 )
      {
        if ( a2 > 1 )
        {
          if ( a7 )
          {
            LODWORD(v75) = 0;
          }
          else
          {
            LODWORD(v75) = 1;
            v43 = 1;
          }
          v44 = (_WORD *)(v11 + 32);
          if ( v43 )
            RtlWriteUShortToUser(v44, 0);
          else
            *v44 = 0;
          if ( a7 )
          {
            LODWORD(v68) = 0;
            v45 = 0;
          }
          else
          {
            LODWORD(v68) = 1;
            v45 = 1;
          }
          if ( v45 )
          {
            RtlWriteULong64ToUser(v11 + 40, 0);
            ConnectInfoLevel4Fields = -1073741789;
LABEL_135:
            v63 = ConnectInfoLevel4Fields;
LABEL_136:
            v57 = v64;
            goto LABEL_137;
          }
          *(_QWORD *)(v11 + 40) = 0;
        }
        ConnectInfoLevel4Fields = -1073741789;
        goto LABEL_135;
      }
      if ( a2 > 1 )
      {
        ConnectInfoLevel4Fields = Smb2PackCredentialsIntoConnectInfo(
                                    1,
                                    v17,
                                    (int)v11 + 32,
                                    (int)v11 + 48,
                                    v42,
                                    (__int64)&v61,
                                    a5,
                                    (__int64)&v62,
                                    a7);
        v63 = ConnectInfoLevel4Fields;
        if ( ConnectInfoLevel4Fields < 0 )
          goto LABEL_136;
      }
      if ( a2 <= 2 )
      {
LABEL_133:
        if ( v7 == 4 )
        {
          v60 = v19;
          v10 = v65;
          ConnectInfoLevel4Fields = GetConnectInfoLevel4Fields(
                                      v11,
                                      a1,
                                      v65,
                                      (unsigned int)&v76,
                                      (__int64)&v61,
                                      v41,
                                      (__int64)&v62,
                                      v60);
          v63 = ConnectInfoLevel4Fields;
          v11 = v76;
          v57 = v64;
LABEL_138:
          if ( v57 )
            VctDereferenceEndpoint(v57);
          if ( *((_QWORD *)&v77 + 1) )
            ExFreePoolWithTag(*((PVOID *)&v77 + 1), 0x6D53744Eu);
          if ( ConnectInfoLevel4Fields >= 0 )
          {
            *a3 = v11;
            *a4 = v61;
            *a6 = v62;
          }
          goto LABEL_144;
        }
        goto LABEL_136;
      }
      ConnectInfoLevel3Fields = GetConnectInfoLevel3Fields(v11, v17);
      if ( !ConnectInfoLevel3Fields )
      {
        ConnectInfoLevel4Fields = -1073741823;
        goto LABEL_135;
      }
      v49 = SmbCeAcquireSpinLock(v68, v46, v12, v48);
      v50 = 0;
      v78 = 0;
      v51 = *(unsigned __int16 *)(v17 + 2);
      if ( (_WORD)v51 )
        v52 = v17 + v51;
      else
        v52 = 0;
      v53 = (_QWORD **)(v52 + 8);
      if ( v52 == -8 || (v54 = *v53) == 0 || (v55 = *(_QWORD **)(v52 + 16)) == 0 )
        __fastfail(3u);
      if ( (_QWORD **)v54[1] != v53 || (_QWORD **)*v55 != v53 )
        __fastfail(3u);
      while ( v54 != v53 )
      {
        if ( !v54 || !*v54 || (v56 = (_QWORD *)v54[1]) == 0 )
          __fastfail(3u);
        if ( *(_QWORD **)(*v54 + 8LL) != v54 || (_QWORD *)*v56 != v54 )
          __fastfail(3u);
        v50 = v54 - 50;
        v78 = v54 - 50;
        v55 = (_QWORD *)*((int *)v54 - 98);
        if ( (int)v55 < 0 )
          KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v54 - 50), *((int *)v54 - 98), 0);
        if ( *(_WORD *)v50 != 0xE2FF )
          break;
        v54 = (_QWORD *)*v54;
        v50 = 0;
        v78 = 0;
      }
      if ( v50 )
      {
        v57 = v50[49];
        v64 = v57;
      }
      else
      {
        v57 = v64;
      }
      if ( v57 )
        VctReferenceEndpoint(v57, v55, v53, 58111);
      v58 = v68;
      *(_DWORD *)(v68 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v58 + 1920), v49);
      if ( v57 )
        ConnectInfoLevel3Fields = PackStringIntoConnectInfo(
                                    (int)v11 + 96,
                                    (unsigned int)*(_QWORD *)(v57 + 32) + 32,
                                    v67,
                                    (unsigned int)&v61,
                                    a5,
                                    (__int64)&v62,
                                    a7);
      if ( !ConnectInfoLevel3Fields )
      {
        ConnectInfoLevel4Fields = -1073741789;
        v63 = -1073741789;
        v7 = a2;
LABEL_137:
        v10 = v65;
        v11 = v67;
        goto LABEL_138;
      }
LABEL_132:
      v7 = a2;
      goto LABEL_133;
    }
    if ( a7 )
    {
      v73 = 0;
      v32 = 0;
    }
    else
    {
      v73 = 1;
      v32 = 1;
    }
    v33 = (void *)(v17 + 448);
    v34 = (void *)(v11 + 68);
    if ( v32 )
      RtlCopyToUser(v34, v33, 0x10u);
    else
      RtlCopyVolatileMemory(v34, v33, 0x10u);
    v35 = 29;
    v66 = 29;
    if ( (*(_BYTE *)(v18 + 736) & 1) != 0 )
      v35 = 2147483677LL;
    v66 = v35;
    v36 = *(_QWORD *)(v65 + 416);
    v37 = *(_DWORD *)(v36 + 4);
    if ( (v37 & 3) == 0 )
    {
      if ( (v37 & 4) != 0
        || (*(_DWORD *)(*(_QWORD *)(v65 + 424) + 180LL) & 0x40000) != 0
        || (v38 = *(_DWORD *)(v65 + 452), v38 == 3) )
      {
        LODWORD(v35) = v35 | 0x20000000;
        goto LABEL_73;
      }
      if ( *(_BYTE *)(v36 + 464) || v38 == 2 )
      {
        LODWORD(v35) = v35 | 0x40000000;
LABEL_73:
        v66 = v35;
      }
    }
    if ( a7 )
    {
      v74 = 0;
      v39 = 0;
    }
    else
    {
      v74 = 1;
      v39 = 1;
    }
    v40 = (_DWORD *)(v11 + 64);
    if ( v39 )
      RtlWriteULongToUser(v40, v35);
    else
      *v40 = v35;
    goto LABEL_80;
  }
  ConnectInfoLevel4Fields = -1073741300;
LABEL_145:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqdqddD(WPP_GLOBAL_Control->AttachedDevice, 12, v12, v8, v10, v7, v11, v61, v62, ConnectInfoLevel4Fields);
  }
  return (unsigned int)ConnectInfoLevel4Fields;
}

```

## disassembly

```asm
0x140018110  mov     rax, rsp
0x140018113  mov     [rax+20h], r9
0x140018117  mov     [rax+18h], r8
0x14001811b  mov     [rax+10h], edx
0x14001811e  mov     [rax+8], rcx
0x140018122  push    rbx
0x140018123  push    rsi
0x140018124  push    rdi
0x140018125  push    r12
0x140018127  push    r13
0x140018129  push    r14
0x14001812b  push    r15
0x14001812d  sub     rsp, 0D0h
0x140018134  mov     r14d, edx
0x140018137  mov     rdi, rcx
0x14001813a  xorps   xmm0, xmm0
0x14001813d  movups  xmmword ptr [rax-50h], xmm0
0x140018141  mov     rsi, [rcx+20h]
0x140018145  mov     r12, [rcx+28h]
0x140018149  mov     [rsp+108h+var_A0], r12
0x14001814e  mov     [rsp+108h+var_60], r12
0x140018156  mov     r13, [r8]
0x140018159  mov     r8, [rsp+108h+arg_28]
0x140018161  mov     r8d, [r8]
0x140018164  mov     [rsp+108h+var_B4], r8d
0x140018169  mov     r9d, [r9]
0x14001816c  mov     [rsp+108h+var_B8], r9d
0x140018171  lea     r15, WPP_GLOBAL_Control; __annotation("TMF:",
0x140018178  mov     rcx, cs:WPP_GLOBAL_Control
0x14001817f  cmp     rcx, r15
0x140018182  jz      short loc_1400181BB
0x140018184  mov     eax, [rcx+2Ch]
0x140018187  test    al, 2
0x140018189  jz      short loc_1400181BB
0x14001818b  cmp     byte ptr [rcx+29h], 4
0x14001818f  jb      short loc_1400181BB
0x140018191  mov     edx, 0Ah
0x140018196  mov     [rsp+108h+var_C8], r8d
0x14001819b  mov     dword ptr [rsp+108h+var_D0], r9d
0x1400181a0  mov     [rsp+108h+var_D8], r13
0x1400181a5  mov     dword ptr [rsp+108h+var_E0], r14d
0x1400181aa  mov     [rsp+108h+BugCheckParameter4], r12
0x1400181af  mov     r9, rdi
0x1400181b2  mov     rcx, [rcx+18h]
0x1400181b6  call    WPP_SF_qqdqdd
0x1400181bb  test    r12, r12
0x1400181be  jnz     short loc_1400181CA
0x1400181c0  mov     ebx, 0C000020Ch
0x1400181c5  jmp     loc_14001893C
0x1400181ca  cmp     r14d, 2
0x1400181ce  jbe     short loc_1400181E8
0x1400181d0  mov     rax, [r12+1A0h]
0x1400181d8  cmp     dword ptr [rax+0Ch], 0
0x1400181dc  jz      short loc_1400181E8
0x1400181de  mov     ebx, 0C0000022h
0x1400181e3  jmp     loc_14001893C
0x1400181e8  xor     ebx, ebx
0x1400181ea  mov     eax, r14d
0x1400181ed  test    r14d, r14d
0x1400181f0  jz      short loc_14001822B
0x1400181f2  sub     eax, 1
0x1400181f5  jz      short loc_140018224
0x1400181f7  sub     eax, 1
0x1400181fa  jz      short loc_14001821D
0x1400181fc  sub     eax, 1
0x1400181ff  jz      short loc_140018216
0x140018201  cmp     eax, 1
0x140018204  jz      short loc_14001820F
0x140018206  xor     edi, edi
0x140018208  mov     ebx, 0C0000003h
0x14001820d  jmp     short loc_140018230
0x14001820f  mov     edi, 40h ; '@'
0x140018214  jmp     short loc_140018230
0x140018216  mov     edi, 0F0h
0x14001821b  jmp     short loc_140018230
0x14001821d  mov     edi, 60h ; '`'
0x140018222  jmp     short loc_140018230
0x140018224  mov     edi, 20h ; ' '
0x140018229  jmp     short loc_140018230
0x14001822b  mov     edi, 18h
0x140018230  test    ebx, ebx
0x140018232  js      loc_140018934
0x140018238  cmp     [rsp+108h+var_B8], edi
0x14001823c  jnb     short loc_140018248
0x14001823e  mov     ebx, 0C0000023h
0x140018243  jmp     loc_140018934
0x140018248  movzx   edx, word ptr [rsi+0D8h]
0x14001824f  add     rdx, 2
0x140018253  mov     ecx, 42h ; 'B'
0x140018258  mov     r8d, 6D53744Eh
0x14001825e  call    cs:__imp_ExAllocatePool2
0x140018265  nop     dword ptr [rax+rax+00h]
0x14001826a  mov     rcx, rax
0x14001826d  mov     [rsp+108h+P], rax
0x140018275  test    rax, rax
0x140018278  jnz     short loc_1400182B2
0x14001827a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018281  cmp     rcx, r15
0x140018284  jz      short loc_1400182A8
0x140018286  mov     eax, [rcx+2Ch]
0x140018289  test    al, 1
0x14001828b  jz      short loc_1400182A8
0x14001828d  cmp     byte ptr [rcx+29h], 1
0x140018291  jb      short loc_1400182A8
0x140018293  mov     edx, 0Bh
0x140018298  lea     r8, WPP_a17d72f4c36c3a1a53f0302036e7f0a6_Traceguids
0x14001829f  mov     rcx, [rcx+18h]
0x1400182a3  call    WPP_SF_
0x1400182a8  mov     ebx, 0C000009Ah
0x1400182ad  jmp     loc_140018934
0x1400182b2  mov     [rsp+108h+var_A8], 0
0x1400182bb  mov     r15, [r12+1A0h]
0x1400182c3  mov     r14, [r15+180h]
0x1400182ca  mov     rax, [r14+18h]
0x1400182ce  mov     [rsp+108h+var_88], rax
0x1400182d6  mov     eax, edi
0x1400182d8  add     rax, r13
0x1400182db  mov     [rsp+108h+var_90], rax
0x1400182e0  mov     [rsp+108h+var_58], rax
0x1400182e8  add     [rsp+108h+var_B4], edi
0x1400182ec  sub     [rsp+108h+var_B8], edi
0x1400182f0  cmp     [rsp+108h+arg_8], 4
0x1400182f8  jnb     loc_14001884D
0x1400182fe  mov     eax, 5Ch ; '\'
0x140018303  mov     [rcx], ax
0x140018306  movzx   r8d, word ptr [rsi+0D8h]; Size
0x14001830e  add     rcx, 2; void *
0x140018312  mov     rdx, [rsi+0E0h]; Src
0x140018319  call    memmove
0x14001831e  movzx   eax, word ptr [rsi+0D8h]
0x140018325  add     ax, 2
0x140018329  mov     [rsp+108h+var_50], ax
0x140018331  mov     [rsp+108h+var_4E], ax
0x140018339  movzx   r12d, [rsp+108h+arg_30]
0x140018342  xor     edi, edi
0x140018344  test    r12b, r12b
0x140018347  jz      short loc_140018354
0x140018349  mov     [rsp+108h+var_80], edi
0x140018350  xor     al, al
0x140018352  jmp     short loc_140018361
0x140018354  mov     [rsp+108h+var_80], 1
0x14001835f  mov     al, 1
0x140018361  mov     edx, [rsi+0C0h]
0x140018367  lea     rcx, [r13+10h]
0x14001836b  test    al, al
0x14001836d  jz      short loc_140018376
0x14001836f  call    RtlWriteULongToUser
0x140018374  jmp     short loc_140018378
0x140018376  mov     [rcx], edx
0x140018378  cmp     [rsp+108h+arg_8], 0
0x140018380  jbe     loc_140018445
0x140018386  test    r12b, r12b
0x140018389  jz      short loc_140018396
0x14001838b  mov     [rsp+108h+var_7C], edi
0x140018392  xor     al, al
0x140018394  jmp     short loc_1400183A3
0x140018396  mov     [rsp+108h+var_7C], 1
0x1400183a1  mov     al, 1
0x1400183a3  mov     edx, [rsi+50h]
0x1400183a6  lea     rcx, [r13+14h]
0x1400183aa  test    al, al
0x1400183ac  jz      short loc_1400183B5
0x1400183ae  call    RtlWriteULongToUser
0x1400183b3  jmp     short loc_1400183B7
0x1400183b5  mov     [rcx], edx
0x1400183b7  mov     rcx, rsi
0x1400183ba  call    cs:__imp_MRxSmbUpdateNetRootState
0x1400183c1  nop     dword ptr [rax+rax+00h]
0x1400183c6  test    r12b, r12b
0x1400183c9  jz      short loc_1400183D7
0x1400183cb  mov     [rsp+108h+var_78], edi
0x1400183d2  xor     dil, dil
0x1400183d5  jmp     short loc_1400183E5
0x1400183d7  mov     [rsp+108h+var_78], 1
0x1400183e2  mov     dil, 1
0x1400183e5  mov     rcx, [rsp+108h+var_A0]
0x1400183ea  mov     ecx, [rcx+0Ch]
0x1400183ed  call    cs:__imp_SmbCeTranslateObjectState
0x1400183f4  nop     dword ptr [rax+rax+00h]
0x1400183f9  movzx   eax, al
0x1400183fc  lea     rcx, [r13+18h]
0x140018400  test    dil, dil
0x140018403  jz      short loc_14001840E
0x140018405  mov     edx, eax
0x140018407  call    RtlWriteULongToUser
0x14001840c  jmp     short loc_140018410
0x14001840e  mov     [rcx], eax
0x140018410  test    r12b, r12b
0x140018413  jz      short loc_140018424
0x140018415  mov     [rsp+108h+var_74], 0
0x140018420  xor     al, al
0x140018422  jmp     short loc_140018431
0x140018424  mov     [rsp+108h+var_74], 1
0x14001842f  mov     al, 1
0x140018431  mov     edx, [rsi+40h]
0x140018434  lea     rcx, [r13+1Ch]
0x140018438  test    al, al
0x14001843a  jz      short loc_140018443
0x14001843c  call    RtlWriteULongToUser
0x140018441  jmp     short loc_140018445
0x140018443  mov     [rcx], edx
0x140018445  cmp     [rsp+108h+arg_8], 1
0x14001844d  jbe     loc_140018566
0x140018453  test    r12b, r12b
0x140018456  jz      short loc_140018467
0x140018458  mov     [rsp+108h+var_70], 0
0x140018463  xor     al, al
0x140018465  jmp     short loc_140018474
0x140018467  mov     [rsp+108h+var_70], 1
0x140018472  mov     al, 1
0x140018474  lea     rdx, [r15+1C0h]; Src
0x14001847b  lea     rcx, [r13+44h]; void *
0x14001847f  mov     r8d, 10h; Size
0x140018485  test    al, al
0x140018487  jz      short loc_140018490
0x140018489  call    RtlCopyToUser
0x14001848e  jmp     short loc_140018496
0x140018490  call    RtlCopyVolatileMemory
0x140018495  nop
0x140018496  mov     edx, 1Dh
0x14001849b  mov     [rsp+108h+var_98], edx
0x14001849f  test    byte ptr [r14+2E0h], 1
0x1400184a7  mov     eax, 8000001Dh
0x1400184ac  cmovnz  edx, eax
0x1400184af  mov     [rsp+108h+var_98], edx
0x1400184b3  mov     r9, [rsp+108h+var_A0]
0x1400184b8  mov     r8, [r9+1A0h]
0x1400184bf  mov     eax, [r8+4]
0x1400184c3  test    al, 3
0x1400184c5  jnz     short loc_140018507
0x1400184c7  test    al, 4
0x1400184c9  jnz     short loc_1400184FF
0x1400184cb  mov     rax, [r9+1A8h]
0x1400184d2  test    dword ptr [rax+0B4h], 40000h
0x1400184dc  jnz     short loc_1400184FF
0x1400184de  mov     eax, [r9+1C4h]
0x1400184e5  cmp     eax, 3
0x1400184e8  jz      short loc_1400184FF
0x1400184ea  cmp     byte ptr [r8+1D0h], 0
0x1400184f2  jnz     short loc_1400184F9
0x1400184f4  cmp     eax, 2
0x1400184f7  jnz     short loc_140018507
0x1400184f9  bts     edx, 1Eh
0x1400184fd  jmp     short loc_140018503
0x1400184ff  bts     edx, 1Dh
0x140018503  mov     [rsp+108h+var_98], edx
0x140018507  test    r12b, r12b
0x14001850a  jz      short loc_14001851B
0x14001850c  mov     [rsp+108h+var_6C], 0
0x140018517  xor     al, al
0x140018519  jmp     short loc_140018528
0x14001851b  mov     [rsp+108h+var_6C], 1
0x140018526  mov     al, 1
0x140018528  lea     rcx, [r13+40h]
0x14001852c  test    al, al
0x14001852e  jz      short loc_140018537
0x140018530  call    RtlWriteULongToUser
0x140018535  jmp     short loc_140018566
0x140018537  mov     [rcx], edx
0x140018539  jmp     short loc_140018566
0x14001853b  mov     ebx, 0C00000E8h
0x140018540  mov     [rsp+108h+var_B0], ebx
0x140018544  mov     r13, [rsp+108h+var_58]
0x14001854c  mov     r12, [rsp+108h+var_60]
0x140018554  mov     r14d, [rsp+108h+arg_8]
0x14001855c  mov     r15, [rsp+108h+var_A8]
0x140018561  jmp     loc_1400188D0
0x140018566  mov     byte ptr [rsp+108h+var_D8], r12b
0x14001856b  lea     rax, [rsp+108h+var_B4]
0x140018570  mov     [rsp+108h+var_E0], rax
0x140018575  mov     esi, [rsp+108h+arg_20]
0x14001857c  mov     dword ptr [rsp+108h+BugCheckParameter4], esi
0x140018580  lea     r9, [rsp+108h+var_B8]
0x140018585  mov     rdi, [rsp+108h+var_90]
0x14001858a  mov     r8, rdi
0x14001858d  lea     rdx, [rsp+108h+var_50]
0x140018595  mov     rcx, r13
0x140018598  call    PackStringIntoConnectInfo
0x14001859d  mov     r14d, [rsp+108h+arg_8]
0x1400185a5  test    al, al
0x1400185a7  jnz     loc_140018636
0x1400185ad  cmp     r14d, 1
0x1400185b1  jbe     short loc_14001862C
0x1400185b3  test    r12b, r12b
0x1400185b6  jz      short loc_1400185C5
0x1400185b8  mov     dword ptr [rsp+108h+var_60], 0
0x1400185c3  jmp     short loc_1400185D2
0x1400185c5  mov     dword ptr [rsp+108h+var_60], 1
0x1400185d0  mov     al, 1
0x1400185d2  lea     rcx, [r13+20h]
0x1400185d6  test    al, al
0x1400185d8  jz      short loc_1400185E3
0x1400185da  xor     edx, edx
0x1400185dc  call    RtlWriteUShortToUser
0x1400185e1  jmp     short loc_1400185E8
0x1400185e3  xor     eax, eax
0x1400185e5  mov     [rcx], ax
0x1400185e8  test    r12b, r12b
0x1400185eb  jz      short loc_1400185FC
0x1400185ed  mov     dword ptr [rsp+108h+var_88], 0
  ... truncated ...
```
