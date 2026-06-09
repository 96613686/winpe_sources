# MRxSmb2PackConnectionInfoThunked

- ea: `0x1400189b0`
- end: `0x1400191ab`
- name: `MRxSmb2PackConnectionInfoThunked`
- size: `2043`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *, unsigned int *, int, _DWORD *, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x140018080`

## callees

- `0x1400104c0`
- `0x1400122d0`
- `0x1400189b0`
- `0x14002a9ac`
- `0x1400306b8`
- `0x140030a38`
- `0x140030bf0`
- `0x140030c84`
- `0x140037190`
- `0x1400372c0`
- `0x140050280`
- `0x1400502e4`
- `0x14005032c`
- `0x140050370`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140019104`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037ca8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019104`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037ca8`
- `ntoskrnl!ExAllocatePool2` at `0x140018adf`
- `ntoskrnl!ExAllocatePool2` at `0x140018adf`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140019058`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140019058`
- `ntoskrnl!KeBugCheckEx` at `0x140018fe2`
- `ntoskrnl!KeBugCheckEx` at `0x140018fe2`
- `mrxsmb!SmbCeTranslateObjectState` at `0x140018c6d`
- `mrxsmb!SmbCeTranslateObjectState` at `0x140018c6d`
- `mrxsmb!VctReferenceEndpoint` at `0x140019032`
- `mrxsmb!VctReferenceEndpoint` at `0x140019032`
- `mrxsmb!VctDereferenceEndpoint` at `0x1400190e6`
- `mrxsmb!VctDereferenceEndpoint` at `0x140037c8a`
- `mrxsmb!VctDereferenceEndpoint` at `0x1400190e6`
- `mrxsmb!VctDereferenceEndpoint` at `0x140037c8a`
- `mrxsmb!MRxSmbUpdateNetRootState` at `0x140018c39`
- `mrxsmb!MRxSmbUpdateNetRootState` at `0x140018c39`

## pseudocode

```c
__int64 __fastcall MRxSmb2PackConnectionInfoThunked(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        unsigned int *a4,
        int a5,
        _DWORD *a6,
        char a7)
{
  __int64 v7; // r12
  unsigned int v8; // edi
  __int64 v9; // r8
  __int64 v10; // r15
  __int64 v11; // r13
  unsigned int v12; // esi
  int v13; // r14d
  int v14; // ebx
  unsigned int v15; // edi
  _WORD *Pool2; // rdx
  __int64 v17; // r13
  char v18; // al
  __int64 v19; // rdx
  _DWORD *v20; // rcx
  char v21; // al
  __int64 v22; // rdx
  _DWORD *v23; // rcx
  char v24; // di
  unsigned __int8 v25; // al
  _DWORD *v26; // rcx
  char v27; // al
  __int64 v28; // rdx
  _DWORD *v29; // rcx
  char v30; // al
  void *v31; // rdx
  void *v32; // rcx
  char v33; // al
  _DWORD *v34; // rcx
  __int64 v35; // rdi
  char v36; // al
  _WORD *v37; // rcx
  char v38; // cl
  __int64 v39; // rdx
  char ConnectInfoLevel3FieldsThunked; // di
  __int64 v41; // r9
  KIRQL v42; // si
  _QWORD *v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rdx
  _QWORD **v46; // r8
  _QWORD *v47; // rax
  _QWORD *v48; // rdx
  _QWORD *v49; // rdx
  __int64 v50; // r15
  __int64 v51; // rax
  int v52; // ecx
  unsigned int v54; // [rsp+50h] [rbp-C8h] BYREF
  int v55; // [rsp+54h] [rbp-C4h] BYREF
  int v56; // [rsp+58h] [rbp-C0h]
  __int64 v57; // [rsp+60h] [rbp-B8h]
  __int64 v58; // [rsp+68h] [rbp-B0h]
  __int64 v59; // [rsp+70h] [rbp-A8h]
  __int64 v60; // [rsp+78h] [rbp-A0h]
  __int128 v61; // [rsp+80h] [rbp-98h] BYREF
  __int128 v62; // [rsp+90h] [rbp-88h] BYREF
  int v63; // [rsp+A0h] [rbp-78h]
  int v64; // [rsp+A4h] [rbp-74h]
  int v65; // [rsp+A8h] [rbp-70h]
  int v66; // [rsp+ACh] [rbp-6Ch]
  int v67; // [rsp+B0h] [rbp-68h]
  __int128 v68; // [rsp+C0h] [rbp-58h] BYREF
  _QWORD *v69; // [rsp+D0h] [rbp-48h]

  v7 = *a3;
  v8 = a2;
  v9 = a1;
  v68 = 0;
  v10 = *(_QWORD *)(a1 + 32);
  v11 = *(_QWORD *)(a1 + 40);
  v59 = v11;
  *(_QWORD *)&v61 = v11;
  v60 = *(_QWORD *)(v11 + 24);
  v57 = v7;
  v12 = *a4;
  v13 = *a6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqdqdd(WPP_GLOBAL_Control->AttachedDevice, 13, a1, a1, v11, a2, v7, v12, *a6);
  }
  if ( v8 > 2 && *(_DWORD *)(*(_QWORD *)(v11 + 416) + 12LL) )
  {
    v14 = -1073741790;
    goto LABEL_126;
  }
  v14 = 0;
  if ( v8 )
  {
    switch ( v8 )
    {
      case 1u:
        v15 = 24;
        break;
      case 2u:
        v15 = 68;
        break;
      case 3u:
        v15 = 208;
        break;
      default:
        v15 = 0;
        v14 = -1073741821;
        break;
    }
  }
  else
  {
    v15 = 12;
  }
  if ( v14 < 0 )
  {
LABEL_125:
    v8 = a2;
    goto LABEL_126;
  }
  if ( v12 < v15 )
  {
    v14 = -1073741789;
    goto LABEL_125;
  }
  Pool2 = (_WORD *)ExAllocatePool2(66, *(unsigned __int16 *)(v10 + 216) + 2LL, 1834185806);
  *((_QWORD *)&v68 + 1) = Pool2;
  if ( Pool2 )
  {
    v58 = 0;
    v17 = *(_QWORD *)(v11 + 416);
    v57 += v15;
    *(_QWORD *)&v62 = v57;
    v55 = v15 + v13;
    v54 = v12 - v15;
    *Pool2 = 92;
    memmove(Pool2 + 1, *(const void **)(v10 + 224), *(unsigned __int16 *)(v10 + 216));
    LOWORD(v68) = *(_WORD *)(v10 + 216) + 2;
    WORD1(v68) = v68;
    if ( a7 )
    {
      v63 = 0;
      v18 = 0;
    }
    else
    {
      v63 = 1;
      v18 = 1;
    }
    v19 = *(unsigned int *)(v10 + 192);
    v20 = (_DWORD *)(v7 + 8);
    if ( v18 )
      RtlWriteULongToUser(v20, v19);
    else
      *v20 = v19;
    if ( a2 )
    {
      if ( a7 )
      {
        v64 = 0;
        v21 = 0;
      }
      else
      {
        v64 = 1;
        v21 = 1;
      }
      v22 = *(unsigned int *)(v10 + 80);
      v23 = (_DWORD *)(v7 + 12);
      if ( v21 )
        RtlWriteULongToUser(v23, v22);
      else
        *v23 = v22;
      MRxSmbUpdateNetRootState(v10);
      if ( a7 )
      {
        v65 = 0;
        v24 = 0;
      }
      else
      {
        v65 = 1;
        v24 = 1;
      }
      v25 = SmbCeTranslateObjectState(*(unsigned int *)(v59 + 12));
      v26 = (_DWORD *)(v7 + 16);
      if ( v24 )
        RtlWriteULongToUser(v26, v25);
      else
        *v26 = v25;
      if ( a7 )
      {
        v66 = 0;
        v27 = 0;
      }
      else
      {
        v66 = 1;
        v27 = 1;
      }
      v28 = *(unsigned int *)(v10 + 64);
      v29 = (_DWORD *)(v7 + 20);
      if ( v27 )
        RtlWriteULongToUser(v29, v28);
      else
        *v29 = v28;
    }
    if ( a2 > 1 )
    {
      if ( a7 )
      {
        v67 = 0;
        v30 = 0;
      }
      else
      {
        v67 = 1;
        v30 = 1;
      }
      v31 = (void *)(v17 + 448);
      v32 = (void *)(v7 + 44);
      if ( v30 )
        RtlCopyToUser(v32, v31, 0x10u);
      else
        RtlCopyVolatileMemory(v32, v31, 0x10u);
      if ( a7 )
      {
        LODWORD(v61) = 0;
        v33 = 0;
      }
      else
      {
        LODWORD(v61) = 1;
        v33 = 1;
      }
      v34 = (_DWORD *)(v7 + 40);
      if ( v33 )
        RtlWriteULongToUser(v34, 29);
      else
        *v34 = 29;
    }
    v35 = v57;
    v36 = PackStringIntoConnectInfoThunked(v7, (unsigned int)&v68, v57, (unsigned int)&v54, a5, (__int64)&v55, a7);
    if ( !v36 )
    {
      if ( a2 > 1 )
      {
        if ( a7 )
        {
          LODWORD(v62) = 0;
        }
        else
        {
          LODWORD(v62) = 1;
          v36 = 1;
        }
        v37 = (_WORD *)(v7 + 24);
        if ( v36 )
          RtlWriteUShortToUser(v37, 0);
        else
          *v37 = 0;
        if ( a7 )
        {
          LODWORD(v60) = 0;
          v38 = 0;
        }
        else
        {
          LODWORD(v60) = 1;
          v38 = 1;
        }
        if ( v38 )
        {
          RtlWriteULong64ToUser(v7 + 28, 0);
          v14 = -1073741789;
LABEL_117:
          v56 = v14;
          goto LABEL_118;
        }
        *(_QWORD *)(v7 + 28) = 0;
      }
      v14 = -1073741789;
      goto LABEL_117;
    }
    if ( a2 > 1 )
    {
      v62 = 0;
      v61 = 0;
      v14 = Smb2PackCredentialsIntoConnectInfo(
              1,
              v17,
              (unsigned int)&v62,
              (unsigned int)&v61,
              v35,
              (__int64)&v54,
              a5,
              (__int64)&v55,
              a7);
      v56 = v14;
      if ( v14 < 0 )
        goto LABEL_118;
      *(_DWORD *)(v7 + 24) = v62;
      *(_DWORD *)(v7 + 28) = DWORD2(v62);
      *(_DWORD *)(v7 + 32) = v61;
      *(_DWORD *)(v7 + 36) = DWORD2(v61);
    }
    if ( a2 > 2 )
    {
      ConnectInfoLevel3FieldsThunked = GetConnectInfoLevel3FieldsThunked(v7, v17);
      if ( ConnectInfoLevel3FieldsThunked )
      {
        v42 = SmbCeAcquireSpinLock(v60, v39, v9, v41);
        v43 = 0;
        v69 = 0;
        v44 = *(unsigned __int16 *)(v17 + 2);
        if ( (_WORD)v44 )
          v45 = v17 + v44;
        else
          v45 = 0;
        v46 = (_QWORD **)(v45 + 8);
        if ( v45 == -8 || (v47 = *v46) == 0 || (v48 = *(_QWORD **)(v45 + 16)) == 0 )
          __fastfail(3u);
        if ( (_QWORD **)v47[1] != v46 || (_QWORD **)*v48 != v46 )
          __fastfail(3u);
        while ( v47 != v46 )
        {
          if ( !v47 || !*v47 || (v49 = (_QWORD *)v47[1]) == 0 )
            __fastfail(3u);
          if ( *(_QWORD **)(*v47 + 8LL) != v47 || (_QWORD *)*v49 != v47 )
            __fastfail(3u);
          v43 = v47 - 50;
          v69 = v47 - 50;
          v48 = (_QWORD *)*((int *)v47 - 98);
          if ( (int)v48 < 0 )
            KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v47 - 50), *((int *)v47 - 98), 0);
          if ( *(_WORD *)v43 != 0xE2FF )
            break;
          v47 = (_QWORD *)*v47;
          v43 = 0;
          v69 = 0;
        }
        if ( v43 )
        {
          v50 = v43[49];
          v58 = v50;
        }
        else
        {
          v50 = v58;
        }
        if ( v50 )
          VctReferenceEndpoint(v50, v48, v46, 58111);
        v51 = v60;
        *(_DWORD *)(v60 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v51 + 1920), v42);
        if ( v50 )
        {
          v52 = v7 + 68;
          v7 = v57;
          ConnectInfoLevel3FieldsThunked = PackStringIntoConnectInfoThunked(
                                             v52,
                                             (unsigned int)*(_QWORD *)(v50 + 32) + 32,
                                             v57,
                                             (unsigned int)&v54,
                                             a5,
                                             (__int64)&v55,
                                             a7);
        }
        else
        {
          v7 = v57;
        }
        if ( !ConnectInfoLevel3FieldsThunked )
        {
          v14 = -1073741789;
          v56 = -1073741789;
        }
        goto LABEL_119;
      }
      v14 = -1073741823;
      goto LABEL_117;
    }
LABEL_118:
    v50 = v58;
    v7 = v57;
LABEL_119:
    v11 = v59;
    if ( v50 )
      VctDereferenceEndpoint(v50);
    if ( *((_QWORD *)&v68 + 1) )
      ExFreePoolWithTag(*((PVOID *)&v68 + 1), 0x6D53744Eu);
    v12 = v54;
    v13 = v55;
    if ( v14 >= 0 )
    {
      *a3 = v7;
      *a4 = v12;
      *a6 = v13;
    }
    goto LABEL_125;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_a17d72f4c36c3a1a53f0302036e7f0a6_Traceguids);
  }
  v14 = -1073741670;
  v8 = a2;
LABEL_126:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqdqddD(WPP_GLOBAL_Control->AttachedDevice, 15, v9, a1, v11, v8, v7, v12, v13, v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400189b0  mov     rax, rsp
0x1400189b3  mov     [rax+20h], r9
0x1400189b7  mov     [rax+18h], r8
0x1400189bb  mov     [rax+10h], edx
0x1400189be  mov     [rax+8], rcx
0x1400189c2  push    rbx
0x1400189c3  push    rsi
0x1400189c4  push    rdi
0x1400189c5  push    r12
0x1400189c7  push    r13
0x1400189c9  push    r14
0x1400189cb  push    r15
0x1400189cd  sub     rsp, 0E0h
0x1400189d4  mov     r12, [r8]
0x1400189d7  mov     edi, edx
0x1400189d9  mov     r8, rcx
0x1400189dc  xorps   xmm0, xmm0
0x1400189df  movups  xmmword ptr [rax-58h], xmm0
0x1400189e3  mov     r15, [rcx+20h]
0x1400189e7  mov     r13, [rcx+28h]
0x1400189eb  mov     [rsp+118h+var_A8], r13
0x1400189f0  mov     qword ptr [rsp+118h+var_98], r13
0x1400189f8  mov     rax, [r13+18h]
0x1400189fc  mov     [rsp+118h+var_A0], rax
0x140018a01  mov     [rsp+118h+var_B8], r12
0x140018a06  mov     esi, [r9]
0x140018a09  mov     r14, [rsp+118h+arg_28]
0x140018a11  mov     r14d, [r14]
0x140018a14  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140018a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018a22  cmp     rcx, rax
0x140018a25  jz      short loc_140018A5C
0x140018a27  mov     eax, [rcx+2Ch]
0x140018a2a  test    al, 2
0x140018a2c  jz      short loc_140018A5C
0x140018a2e  cmp     byte ptr [rcx+29h], 4
0x140018a32  jb      short loc_140018A5C
0x140018a34  mov     edx, 0Dh
0x140018a39  mov     [rsp+118h+var_D8], r14d
0x140018a3e  mov     dword ptr [rsp+118h+var_E0], esi
0x140018a42  mov     [rsp+118h+var_E8], r12
0x140018a47  mov     dword ptr [rsp+118h+var_F0], edi
0x140018a4b  mov     [rsp+118h+BugCheckParameter4], r13
0x140018a50  mov     r9, r8
0x140018a53  mov     rcx, [rcx+18h]
0x140018a57  call    WPP_SF_qqdqdd
0x140018a5c  cmp     edi, 2
0x140018a5f  jbe     short loc_140018A78
0x140018a61  mov     rax, [r13+1A0h]
0x140018a68  cmp     dword ptr [rax+0Ch], 0
0x140018a6c  jz      short loc_140018A78
0x140018a6e  mov     ebx, 0C0000022h
0x140018a73  jmp     loc_140019144
0x140018a78  xor     ebx, ebx
0x140018a7a  mov     eax, edi
0x140018a7c  test    edi, edi
0x140018a7e  jz      short loc_140018AAD
0x140018a80  sub     eax, 1
0x140018a83  jz      short loc_140018AA6
0x140018a85  sub     eax, 1
0x140018a88  jz      short loc_140018A9F
0x140018a8a  cmp     eax, 1
0x140018a8d  jz      short loc_140018A98
0x140018a8f  xor     edi, edi
0x140018a91  mov     ebx, 0C0000003h
0x140018a96  jmp     short loc_140018AB2
0x140018a98  mov     edi, 0D0h
0x140018a9d  jmp     short loc_140018AB2
0x140018a9f  mov     edi, 44h ; 'D'
0x140018aa4  jmp     short loc_140018AB2
0x140018aa6  mov     edi, 18h
0x140018aab  jmp     short loc_140018AB2
0x140018aad  mov     edi, 0Ch
0x140018ab2  test    ebx, ebx
0x140018ab4  js      loc_14001913D
0x140018aba  cmp     esi, edi
0x140018abc  jnb     short loc_140018AC8
0x140018abe  mov     ebx, 0C0000023h
0x140018ac3  jmp     loc_14001913D
0x140018ac8  movzx   edx, word ptr [r15+0D8h]
0x140018ad0  add     rdx, 2
0x140018ad4  mov     ecx, 42h ; 'B'
0x140018ad9  mov     r8d, 6D53744Eh
0x140018adf  call    cs:__imp_ExAllocatePool2
0x140018ae6  nop     dword ptr [rax+rax+00h]
0x140018aeb  mov     rdx, rax
0x140018aee  mov     [rsp+118h+P], rax
0x140018af6  test    rax, rax
0x140018af9  jnz     short loc_140018B41
0x140018afb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018b02  lea     r15, WPP_GLOBAL_Control
0x140018b09  cmp     rcx, r15
0x140018b0c  jz      short loc_140018B30
0x140018b0e  mov     eax, [rcx+2Ch]
0x140018b11  test    al, 1
0x140018b13  jz      short loc_140018B30
0x140018b15  cmp     byte ptr [rcx+29h], 1
0x140018b19  jb      short loc_140018B30
0x140018b1b  mov     edx, 0Eh
0x140018b20  lea     r8, WPP_a17d72f4c36c3a1a53f0302036e7f0a6_Traceguids
0x140018b27  mov     rcx, [rcx+18h]
0x140018b2b  call    WPP_SF_
0x140018b30  mov     ebx, 0C000009Ah
0x140018b35  mov     edi, [rsp+118h+arg_8]
0x140018b3c  jmp     loc_14001914B
0x140018b41  mov     [rsp+118h+var_B0], 0
0x140018b4a  mov     r13, [r13+1A0h]
0x140018b51  mov     eax, edi
0x140018b53  mov     rcx, [rsp+118h+var_B8]
0x140018b58  add     rcx, rax
0x140018b5b  mov     [rsp+118h+var_B8], rcx
0x140018b60  mov     qword ptr [rsp+118h+var_88], rcx
0x140018b68  add     r14d, edi
0x140018b6b  mov     [rsp+118h+var_C4], r14d
0x140018b70  sub     esi, edi
0x140018b72  mov     [rsp+118h+var_C8], esi
0x140018b76  mov     eax, 5Ch ; '\'
0x140018b7b  mov     [rdx], ax
0x140018b7e  movzx   r8d, word ptr [r15+0D8h]; Size
0x140018b86  lea     rcx, [rdx+2]; void *
0x140018b8a  mov     rdx, [r15+0E0h]; Src
0x140018b91  call    memmove
0x140018b96  movzx   eax, word ptr [r15+0D8h]
0x140018b9e  add     ax, 2
0x140018ba2  mov     [rsp+118h+var_58], ax
0x140018baa  mov     [rsp+118h+var_56], ax
0x140018bb2  movzx   esi, [rsp+118h+arg_30]
0x140018bba  xor     r14d, r14d
0x140018bbd  test    sil, sil
0x140018bc0  jz      short loc_140018BCE
0x140018bc2  mov     [rsp+118h+var_78], r14d
0x140018bca  xor     al, al
0x140018bcc  jmp     short loc_140018BDB
0x140018bce  mov     [rsp+118h+var_78], 1
0x140018bd9  mov     al, 1
0x140018bdb  mov     edx, [r15+0C0h]
0x140018be2  lea     rcx, [r12+8]
0x140018be7  test    al, al
0x140018be9  jz      short loc_140018BF2
0x140018beb  call    RtlWriteULongToUser
0x140018bf0  jmp     short loc_140018BF4
0x140018bf2  mov     [rcx], edx
0x140018bf4  cmp     [rsp+118h+arg_8], 0
0x140018bfc  jbe     loc_140018CC5
0x140018c02  test    sil, sil
0x140018c05  jz      short loc_140018C13
0x140018c07  mov     [rsp+118h+var_74], r14d
0x140018c0f  xor     al, al
0x140018c11  jmp     short loc_140018C20
0x140018c13  mov     [rsp+118h+var_74], 1
0x140018c1e  mov     al, 1
0x140018c20  mov     edx, [r15+50h]
0x140018c24  lea     rcx, [r12+0Ch]
0x140018c29  test    al, al
0x140018c2b  jz      short loc_140018C34
0x140018c2d  call    RtlWriteULongToUser
0x140018c32  jmp     short loc_140018C36
0x140018c34  mov     [rcx], edx
0x140018c36  mov     rcx, r15
0x140018c39  call    cs:__imp_MRxSmbUpdateNetRootState
0x140018c40  nop     dword ptr [rax+rax+00h]
0x140018c45  test    sil, sil
0x140018c48  jz      short loc_140018C57
0x140018c4a  mov     [rsp+118h+var_70], r14d
0x140018c52  xor     dil, dil
0x140018c55  jmp     short loc_140018C65
0x140018c57  mov     [rsp+118h+var_70], 1
0x140018c62  mov     dil, 1
0x140018c65  mov     rcx, [rsp+118h+var_A8]
0x140018c6a  mov     ecx, [rcx+0Ch]
0x140018c6d  call    cs:__imp_SmbCeTranslateObjectState
0x140018c74  nop     dword ptr [rax+rax+00h]
0x140018c79  movzx   eax, al
0x140018c7c  lea     rcx, [r12+10h]
0x140018c81  test    dil, dil
0x140018c84  jz      short loc_140018C8F
0x140018c86  mov     edx, eax
0x140018c88  call    RtlWriteULongToUser
0x140018c8d  jmp     short loc_140018C91
0x140018c8f  mov     [rcx], eax
0x140018c91  test    sil, sil
0x140018c94  jz      short loc_140018CA2
0x140018c96  mov     [rsp+118h+var_6C], r14d
0x140018c9e  xor     al, al
0x140018ca0  jmp     short loc_140018CAF
0x140018ca2  mov     [rsp+118h+var_6C], 1
0x140018cad  mov     al, 1
0x140018caf  mov     edx, [r15+40h]
0x140018cb3  lea     rcx, [r12+14h]
0x140018cb8  test    al, al
0x140018cba  jz      short loc_140018CC3
0x140018cbc  call    RtlWriteULongToUser
0x140018cc1  jmp     short loc_140018CC5
0x140018cc3  mov     [rcx], edx
0x140018cc5  mov     r15d, [rsp+118h+arg_8]
0x140018ccd  cmp     r15d, 1
0x140018cd1  jbe     loc_140018D76
0x140018cd7  test    sil, sil
0x140018cda  jz      short loc_140018CE8
0x140018cdc  mov     [rsp+118h+var_68], r14d
0x140018ce4  xor     al, al
0x140018ce6  jmp     short loc_140018CF5
0x140018ce8  mov     [rsp+118h+var_68], 1
0x140018cf3  mov     al, 1
0x140018cf5  lea     rdx, [r13+1C0h]; Src
0x140018cfc  lea     rcx, [r12+2Ch]; void *
0x140018d01  mov     r8d, 10h; Size
0x140018d07  test    al, al
0x140018d09  jz      short loc_140018D12
0x140018d0b  call    RtlCopyToUser
0x140018d10  jmp     short loc_140018D18
0x140018d12  call    RtlCopyVolatileMemory
0x140018d17  nop
0x140018d18  test    sil, sil
0x140018d1b  jz      short loc_140018D29
0x140018d1d  mov     dword ptr [rsp+118h+var_98], r14d
0x140018d25  xor     al, al
0x140018d27  jmp     short loc_140018D36
0x140018d29  mov     dword ptr [rsp+118h+var_98], 1
0x140018d34  mov     al, 1
0x140018d36  lea     rcx, [r12+28h]
0x140018d3b  test    al, al
0x140018d3d  jz      short loc_140018D4B
0x140018d3f  mov     edx, 1Dh
0x140018d44  call    RtlWriteULongToUser
0x140018d49  jmp     short loc_140018D76
0x140018d4b  mov     dword ptr [rcx], 1Dh
0x140018d51  jmp     short loc_140018D76
0x140018d53  mov     ebx, 0C00000E8h
0x140018d58  mov     [rsp+118h+var_C0], ebx
0x140018d5c  mov     r12, qword ptr [rsp+118h+var_88]
0x140018d64  mov     r13, qword ptr [rsp+118h+var_98]
0x140018d6c  mov     r15, [rsp+118h+var_B0]
0x140018d71  jmp     loc_1400190DE
0x140018d76  mov     byte ptr [rsp+118h+var_E8], sil
0x140018d7b  lea     rax, [rsp+118h+var_C4]
0x140018d80  mov     [rsp+118h+var_F0], rax
0x140018d85  mov     r14d, [rsp+118h+arg_20]
0x140018d8d  mov     dword ptr [rsp+118h+BugCheckParameter4], r14d
0x140018d92  lea     r9, [rsp+118h+var_C8]
0x140018d97  mov     rdi, [rsp+118h+var_B8]
0x140018d9c  mov     r8, rdi
0x140018d9f  lea     rdx, [rsp+118h+var_58]
0x140018da7  mov     rcx, r12
0x140018daa  call    PackStringIntoConnectInfoThunked
0x140018daf  test    al, al
0x140018db1  jnz     loc_140018E3C
0x140018db7  cmp     r15d, 1
0x140018dbb  jbe     short loc_140018E32
0x140018dbd  test    sil, sil
0x140018dc0  jz      short loc_140018DCF
0x140018dc2  mov     dword ptr [rsp+118h+var_88], 0
0x140018dcd  jmp     short loc_140018DDC
0x140018dcf  mov     dword ptr [rsp+118h+var_88], 1
0x140018dda  mov     al, 1
0x140018ddc  lea     rcx, [r12+18h]
0x140018de1  test    al, al
0x140018de3  jz      short loc_140018DEE
0x140018de5  xor     edx, edx
0x140018de7  call    RtlWriteUShortToUser
0x140018dec  jmp     short loc_140018DF3
0x140018dee  xor     eax, eax
0x140018df0  mov     [rcx], ax
0x140018df3  test    sil, sil
0x140018df6  jz      short loc_140018E04
0x140018df8  mov     dword ptr [rsp+118h+var_A0], 0
0x140018e00  xor     cl, cl
0x140018e02  jmp     short loc_140018E0E
0x140018e04  mov     dword ptr [rsp+118h+var_A0], 1
0x140018e0c  mov     cl, 1
0x140018e0e  lea     rax, [r12+1Ch]
0x140018e13  test    cl, cl
0x140018e15  jz      short loc_140018E2B
0x140018e17  xor     edx, edx
0x140018e19  mov     rcx, rax
0x140018e1c  call    RtlWriteULong64ToUser
0x140018e21  mov     ebx, 0C0000023h
0x140018e26  jmp     loc_1400190CB
0x140018e2b  mov     qword ptr [rax], 0
0x140018e32  mov     ebx, 0C0000023h
0x140018e37  jmp     loc_1400190CB
0x140018e3c  cmp     r15d, 1
0x140018e40  jbe     loc_140018EFA
0x140018e46  xorps   xmm0, xmm0
0x140018e49  movups  [rsp+118h+var_88], xmm0
0x140018e51  xorps   xmm1, xmm1
0x140018e54  movups  [rsp+118h+var_98], xmm1
0x140018e5c  mov     byte ptr [rsp+118h+var_D8], sil
0x140018e61  lea     rax, [rsp+118h+var_C4]
0x140018e66  mov     [rsp+118h+var_E0], rax
0x140018e6b  mov     dword ptr [rsp+118h+var_E8], r14d
0x140018e70  lea     rax, [rsp+118h+var_C8]
0x140018e75  mov     [rsp+118h+var_F0], rax
0x140018e7a  mov     [rsp+118h+BugCheckParameter4], rdi
0x140018e7f  lea     r9, [rsp+118h+var_98]
0x140018e87  lea     r8, [rsp+118h+var_88]
0x140018e8f  mov     rdx, r13
0x140018e92  mov     ecx, 1
0x140018e97  call    Smb2PackCredentialsIntoConnectInfo
0x140018e9c  mov     ebx, eax
  ... truncated ...
```
