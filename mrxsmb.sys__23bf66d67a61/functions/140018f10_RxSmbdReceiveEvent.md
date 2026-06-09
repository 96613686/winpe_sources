# RxSmbdReceiveEvent

- ea: `0x140018f10`
- end: `0x140019426`
- name: `RxSmbdReceiveEvent`
- size: `1302`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x140018f10`
- `0x140019470`
- `0x14001a008`
- `0x14001a2a0`
- `0x14001a354`
- `0x140027ca0`
- `0x14003838c`
- `0x140039fa8`
- `0x14003e14c`
- `0x140053e40`
- `0x140059dc0`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1400191f2`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400191f2`
- `ntoskrnl!EtwProviderEnabled` at `0x1400191b3`
- `ntoskrnl!EtwProviderEnabled` at `0x1400191da`
- `ntoskrnl!EtwProviderEnabled` at `0x1400191b3`
- `ntoskrnl!EtwProviderEnabled` at `0x1400191da`

## pseudocode

```c
void __fastcall RxSmbdReceiveEvent(unsigned int a1, char *a2, __int64 a3, char a4, unsigned int a5)
{
  unsigned int v5; // r12d
  unsigned int v9; // ebx
  __int64 v10; // r9
  bool v11; // zf
  int v12; // r13d
  unsigned int v13; // esi
  unsigned int v14; // eax
  __int64 v15; // rax
  int v16; // r13d
  BOOLEAN v17; // al
  const GUID *ActivityIdThread; // rax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rdx
  unsigned int v23; // ecx
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  unsigned int v26; // eax
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  unsigned int v29; // eax
  const GUID *v30; // rsi
  __int64 v31; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+28h] [rbp-D8h]
  __int64 v33; // [rsp+30h] [rbp-D0h]
  unsigned int v34; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int Size; // [rsp+68h] [rbp-98h] BYREF
  unsigned int Size_4; // [rsp+6Ch] [rbp-94h]
  int v37; // [rsp+70h] [rbp-90h]
  int v38; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v39; // [rsp+78h] [rbp-88h]
  unsigned int v40; // [rsp+7Ch] [rbp-84h]
  _DWORD *v41; // [rsp+80h] [rbp-80h]
  __int64 v42; // [rsp+88h] [rbp-78h] BYREF
  const GUID *v43; // [rsp+90h] [rbp-70h]
  PMDL MemoryDescriptorList; // [rsp+98h] [rbp-68h] BYREF
  __int128 v45; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v46[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v47[28]; // [rsp+B8h] [rbp-48h]
  unsigned int v48; // [rsp+D4h] [rbp-2Ch]
  _OWORD v49[3]; // [rsp+D8h] [rbp-28h] BYREF

  v5 = a5;
  v34 = a1;
  v39 = a5;
  v38 = 0;
  MemoryDescriptorList = 0;
  Size = 0;
  v9 = a1;
  v42 = 0;
  memset(v49, 0, sizeof(v49));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids, a3, a1);
  }
  v10 = *(unsigned int *)(a3 + 328);
  if ( v9 >= (unsigned int)v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids, v10);
    }
    return;
  }
  if ( v9 <= 4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids);
    }
    return;
  }
  v11 = *(_DWORD *)a2 == 1112364029;
  v12 = 0;
  v37 = 0;
  if ( v11 )
  {
    if ( (int)RxCeDecryptData(a3, a2, v9, &v34, (char *)v49 + 8) < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return;
      }
      v25 = 14;
    }
    else
    {
      v9 = v34;
      v12 = 0x10000000;
      v37 = 0x10000000;
      if ( (int)RxCeVerifyPostTransformData((struct _EX_RUNDOWN_REF *)a3, (__int64)a2, v34, *((__int64 *)&v49[0] + 1)) >= 0 )
        goto LABEL_6;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return;
      }
      v25 = 15;
    }
    WPP_SF_(v24->AttachedDevice, v25, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids);
    return;
  }
LABEL_6:
  v45 = 0;
  v13 = 0;
  v40 = 0;
  if ( (byte_1400712C4 & 0x20) == 0 )
    goto LABEL_7;
  LOWORD(Size_4) = *(_WORD *)(a3 + 320);
  if ( !EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x200000000uLL) )
    goto LABEL_7;
  v17 = EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x800000000000uLL);
  v34 = v9;
  if ( !v17 && v9 >= 0x40 && *(_DWORD *)a2 == 1112364030 )
  {
    v26 = *((_DWORD *)a2 + 5) + 576;
    if ( v26 > v9 )
      v26 = v9;
    v34 = v26;
  }
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  v43 = ActivityIdThread;
  if ( !ActivityIdThread )
  {
    v45 = (unsigned __int64)_InterlockedIncrement64(&Correlation);
    ActivityIdThread = (const GUID *)&v45;
    v43 = (const GUID *)&v45;
  }
  if ( v34 >= 0xF000 )
  {
    v27 = *(_OWORD *)(a3 + 428);
    v48 = v34;
    v28 = *(_OWORD *)(a3 + 440);
    v46[0] = (unsigned __int16)Size_4;
    *(_OWORD *)v47 = v27;
    *(_OWORD *)&v47[12] = v28;
    v41 = a2;
    v46[1] = 28;
    v29 = Template_qqbjqb_ex(REMOTEFS_SMB_Context, v19, 0x240000000LL, ActivityIdThread, 40, (__int64)v46);
    v23 = v34;
    v22 = v29;
    v30 = v43;
    while ( 1 )
    {
      if ( (int)v22 < 0 )
      {
LABEL_37:
        v13 = v40;
        v5 = v39;
        goto LABEL_18;
      }
      if ( v23 >= 0xF000 )
      {
        v20 = 61440;
        v21 = 0x200000000LL;
        Size_4 = 61440;
        if ( v23 != 61440 )
          goto LABEL_36;
      }
      else
      {
        v20 = v23;
        Size_4 = v23;
      }
      v21 = 0x280000000LL;
LABEL_36:
      LODWORD(v22) = Template_qqbjqb_ex(REMOTEFS_SMB_Context, v22, v21, v30, v20, (__int64)v41);
      v41 = (_DWORD *)((char *)v41 + Size_4);
      v23 = v34 - Size_4;
      v34 = v23;
      if ( !v23 )
        goto LABEL_37;
    }
  }
  Template_qqbqb_ex(
    REMOTEFS_SMB_Context,
    a3 + 428,
    0x200000000LL,
    ActivityIdThread,
    Size_4,
    v31,
    a3 + 428,
    v34,
    (__int64)a2);
LABEL_7:
  while ( v13 < v9 )
  {
    DWORD1(v49[0]) = 0;
    v14 = v12 | 0x80000000;
    *((_QWORD *)&v49[0] + 1) = -1;
    if ( !a4 )
      v14 = v12;
    v37 = v14;
    LODWORD(v49[0]) = v14;
    v15 = *(_QWORD *)(a3 + 392);
    v39 = v9 - v13;
    v16 = (*(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD, _QWORD, _QWORD, int *, char *, PMDL *, __int64 *, unsigned int *))(v15 + 16))(
            a3,
            v49,
            v9 - v13,
            v9 - v13,
            v5,
            &v38,
            &a2[v13],
            &MemoryDescriptorList,
            &v42,
            &Size);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      LODWORD(v33) = Size;
      LODWORD(v32) = v16;
      WPP_SF_LLLL(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids,
        v39,
        v38,
        v32,
        v33);
    }
    if ( v16 == -1073741285 )
      break;
    v13 += v38;
    if ( v16 == -1073741802 )
    {
      if ( Size > v9 - v13 )
      {
        (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)(a3 + 392) + 24LL))(
          a3,
          v42,
          0,
          3221225996LL);
        return;
      }
      CopyBufferToMdl(MemoryDescriptorList, &a2[v13], Size);
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)(a3 + 392) + 24LL))(a3, v42, Size, 0);
      v13 += Size;
    }
LABEL_18:
    v12 = v37;
  }
}

```

## disassembly

```asm
0x140018f10  push    rbp
0x140018f12  push    rbx
0x140018f13  push    rsi
0x140018f14  push    rdi
0x140018f15  push    r12
0x140018f17  push    r14
0x140018f19  push    r15
0x140018f1b  lea     rbp, [rsp-10h]
0x140018f20  sub     rsp, 110h
0x140018f27  mov     rax, cs:__security_cookie
0x140018f2e  xor     rax, rsp
0x140018f31  mov     [rbp+40h+var_38], rax
0x140018f35  mov     r12d, [rbp+40h+arg_20]
0x140018f39  xorps   xmm0, xmm0
0x140018f3c  mov     r14, rdx
0x140018f3f  mov     [rsp+140h+var_E0], ecx
0x140018f43  xor     edx, edx
0x140018f45  mov     [rsp+140h+var_C8], r12d
0x140018f4a  mov     [rsp+140h+var_CC], edx
0x140018f4e  movzx   r15d, r9b
0x140018f52  mov     [rbp+40h+MemoryDescriptorList], rdx
0x140018f56  mov     rdi, r8
0x140018f59  mov     dword ptr [rsp+140h+Size], edx
0x140018f5d  mov     ebx, ecx
0x140018f5f  mov     [rbp+40h+var_B8], rdx
0x140018f63  movups  [rbp+40h+var_68], xmm0
0x140018f67  movups  [rbp+40h+var_58], xmm0
0x140018f6b  movups  [rbp+40h+var_48], xmm0
0x140018f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f76  lea     rsi, WPP_GLOBAL_Control
0x140018f7d  cmp     rcx, rsi
0x140018f80  jz      short loc_140018F8D
0x140018f82  mov     eax, [rcx+2Ch]
0x140018f85  test    al, 4
0x140018f87  jnz     loc_1400192E7
0x140018f8d  mov     r9d, [rdi+148h]
0x140018f94  cmp     ebx, r9d
0x140018f97  jnb     loc_1400190A7
0x140018f9d  cmp     ebx, 4
0x140018fa0  jbe     loc_140019314
0x140018fa6  cmp     dword ptr [r14], 424D53FDh
0x140018fad  mov     [rsp+140h+arg_18], r13
0x140018fb5  mov     r13d, edx
0x140018fb8  mov     [rsp+140h+var_D0], edx
0x140018fbc  jz      loc_140019140
0x140018fc2  test    cs:byte_1400712C4, 20h
0x140018fc9  xorps   xmm0, xmm0
0x140018fcc  movups  [rbp+40h+var_A0], xmm0
0x140018fd0  mov     esi, edx
0x140018fd2  mov     [rsp+140h+var_C4], edx
0x140018fd6  jnz     loc_140019194
0x140018fdc  cmp     esi, ebx
0x140018fde  jnb     loc_140019080
0x140018fe4  mov     dword ptr [rbp+40h+var_68+4], edx
0x140018fe7  lea     r9, [rsp+140h+Size]
0x140018fec  mov     [rsp+140h+var_F8], r9
0x140018ff1  mov     eax, r13d
0x140018ff4  bts     eax, 1Fh
0x140018ff8  mov     edx, r12d
0x140018ffb  test    r15b, r15b
0x140018ffe  mov     qword ptr [rbp+40h+var_68+8], 0FFFFFFFFFFFFFFFFh
0x140019006  lea     r9, [rbp+40h+var_B8]
0x14001900a  mov     ecx, esi
0x14001900c  mov     [rsp+140h+var_100], r9
0x140019011  cmovz   eax, r13d
0x140019015  add     rcx, r14
0x140019018  mov     [rsp+140h+var_D0], eax
0x14001901c  lea     r9, [rbp+40h+MemoryDescriptorList]
0x140019020  mov     dword ptr [rbp+40h+var_68], eax
0x140019023  mov     rax, [rdi+188h]
0x14001902a  mov     r8d, ebx
0x14001902d  mov     [rsp+140h+var_108], r9
0x140019032  sub     r8d, esi
0x140019035  mov     [rsp+140h+var_110], rcx
0x14001903a  mov     r9d, r8d
0x14001903d  lea     rcx, [rsp+140h+var_CC]
0x140019042  mov     [rsp+140h+var_C8], r8d
0x140019047  mov     rax, [rax+10h]
0x14001904b  mov     [rsp+140h+var_118], rcx
0x140019050  mov     rcx, rdi
0x140019053  mov     [rsp+140h+var_120], rdx
0x140019058  lea     rdx, [rbp+40h+var_68]
0x14001905c  call    _guard_dispatch_icall
0x140019061  mov     r13d, eax
0x140019064  mov     r10, cs:WPP_GLOBAL_Control
0x14001906b  lea     rax, WPP_GLOBAL_Control
0x140019072  cmp     r10, rax
0x140019075  jnz     short loc_1400190F4
0x140019077  cmp     r13d, 0C000021Bh
0x14001907e  jnz     short loc_1400190D7
0x140019080  mov     r13, [rsp+140h+arg_18]
0x140019088  mov     rcx, [rbp+40h+var_38]
0x14001908c  xor     rcx, rsp; StackCookie
0x14001908f  call    __security_check_cookie
0x140019094  add     rsp, 110h
0x14001909b  pop     r15
0x14001909d  pop     r14
0x14001909f  pop     r12
0x1400190a1  pop     rdi
0x1400190a2  pop     rsi
0x1400190a3  pop     rbx
0x1400190a4  pop     rbp
0x1400190a5  retn
0x1400190a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400190ae  cmp     rcx, rsi
0x1400190b1  jz      short loc_140019088
0x1400190b3  mov     eax, [rcx+2Ch]
0x1400190b6  test    al, 1
0x1400190b8  jz      short loc_140019088
0x1400190ba  cmp     byte ptr [rcx+29h], 1
0x1400190be  jb      short loc_140019088
0x1400190c0  mov     rcx, [rcx+18h]
0x1400190c4  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x1400190cb  mov     edx, 0Ch
0x1400190d0  call    WPP_SF_d
0x1400190d5  jmp     short loc_140019088
0x1400190d7  add     esi, [rsp+140h+var_CC]
0x1400190db  cmp     r13d, 0C0000016h
0x1400190e2  jz      loc_1400193DE
0x1400190e8  mov     r13d, [rsp+140h+var_D0]
0x1400190ed  xor     edx, edx
0x1400190ef  jmp     loc_140018FDC
0x1400190f4  mov     ecx, [r10+2Ch]
0x1400190f8  test    cl, 4
0x1400190fb  jz      loc_140019077
0x140019101  cmp     byte ptr [r10+29h], 4
0x140019106  jb      loc_140019077
0x14001910c  mov     eax, dword ptr [rsp+140h+Size]
0x140019110  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x140019117  mov     r9d, [rsp+140h+var_C8]
0x14001911c  mov     edx, 10h
0x140019121  mov     rcx, [r10+18h]
0x140019125  mov     dword ptr [rsp+140h+var_110], eax
0x140019129  mov     eax, [rsp+140h+var_CC]
0x14001912d  mov     dword ptr [rsp+140h+var_118], r13d
0x140019132  mov     dword ptr [rsp+140h+var_120], eax
0x140019136  call    WPP_SF_LLLL
0x14001913b  jmp     loc_140019077
0x140019140  lea     rax, [rbp+40h+var_68+8]
0x140019144  mov     r8d, ebx
0x140019147  lea     r9, [rsp+140h+var_E0]
0x14001914c  mov     [rsp+140h+var_120], rax
0x140019151  mov     rdx, r14
0x140019154  mov     rcx, rdi
0x140019157  call    RxCeDecryptData
0x14001915c  test    eax, eax
0x14001915e  js      loc_140019353
0x140019164  mov     ebx, [rsp+140h+var_E0]
0x140019168  mov     r13d, 10000000h
0x14001916e  mov     r9, qword ptr [rbp+40h+var_68+8]
0x140019172  mov     r8d, ebx
0x140019175  mov     rdx, r14
0x140019178  mov     [rsp+140h+var_D0], r13d
0x14001917d  mov     rcx, rdi
0x140019180  call    RxCeVerifyPostTransformData
0x140019185  test    eax, eax
0x140019187  js      loc_140019382
0x14001918d  xor     edx, edx
0x14001918f  jmp     loc_140018FC2
0x140019194  movzx   eax, word ptr [rdi+140h]
0x14001919b  xor     edx, edx; Level
0x14001919d  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x1400191a4  mov     r8, 200000000h; Keyword
0x1400191ae  mov     word ptr [rsp+140h+Size+4], ax
0x1400191b3  call    cs:__imp_EtwProviderEnabled
0x1400191ba  nop     dword ptr [rax+rax+00h]
0x1400191bf  test    al, al
0x1400191c1  jz      loc_1400190ED
0x1400191c7  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x1400191ce  xor     edx, edx; Level
0x1400191d0  mov     r8, 800000000000h; Keyword
0x1400191da  call    cs:__imp_EtwProviderEnabled
0x1400191e1  nop     dword ptr [rax+rax+00h]
0x1400191e6  mov     [rsp+140h+var_E0], ebx
0x1400191ea  test    al, al
0x1400191ec  jz      loc_1400193B1
0x1400191f2  call    cs:__imp_IoGetActivityIdThread
0x1400191f9  nop     dword ptr [rax+rax+00h]
0x1400191fe  mov     [rbp+40h+var_B0], rax
0x140019202  test    rax, rax
0x140019205  jnz     short loc_14001922B
0x140019207  xorps   xmm0, xmm0
0x14001920a  mov     eax, 1
0x14001920f  movups  [rbp+40h+var_A0], xmm0
0x140019213  lock xadd cs:Correlation, rax
0x14001921c  inc     rax
0x14001921f  mov     qword ptr [rbp+40h+var_A0], rax
0x140019223  lea     rax, [rbp+40h+var_A0]
0x140019227  mov     [rbp+40h+var_B0], rax
0x14001922b  mov     ecx, [rsp+140h+var_E0]
0x14001922f  mov     r9, rax
0x140019232  movzx   r8d, word ptr [rsp+140h+Size+4]
0x140019238  cmp     ecx, 0F000h
0x14001923e  jnb     loc_14005E0D2
0x140019244  mov     [rsp+140h+var_100], r14
0x140019249  lea     rdx, [rdi+1ACh]
0x140019250  mov     dword ptr [rsp+140h+var_108], ecx
0x140019254  mov     rcx, cs:REMOTEFS_SMB_Context
0x14001925b  mov     [rsp+140h+var_110], rdx
0x140019260  mov     dword ptr [rsp+140h+var_120], r8d
0x140019265  mov     r8, 200000000h
0x14001926f  call    Template_qqbqb_ex
0x140019274  xor     edx, edx
0x140019276  jmp     loc_140018FDC
0x140019280  test    edx, edx
0x140019282  js      short loc_1400192C9
0x140019284  cmp     ecx, 0F000h
0x14001928a  jnb     short loc_1400192D7
0x14001928c  mov     eax, ecx
0x14001928e  mov     dword ptr [rsp+140h+Size+4], ecx
0x140019292  mov     r8, r12
0x140019295  mov     rcx, [rbp+40h+var_C0]
0x140019299  mov     r9, rsi
0x14001929c  mov     [rsp+140h+var_118], rcx
0x1400192a1  mov     rcx, cs:REMOTEFS_SMB_Context
0x1400192a8  mov     dword ptr [rsp+140h+var_120], eax
0x1400192ac  call    Template_qqbjqb_ex
0x1400192b1  mov     ecx, [rsp+140h+var_E0]
0x1400192b5  mov     edx, eax
0x1400192b7  mov     eax, dword ptr [rsp+140h+Size+4]
0x1400192bb  add     [rbp+40h+var_C0], rax
0x1400192bf  sub     ecx, eax
0x1400192c1  mov     [rsp+140h+var_E0], ecx
0x1400192c5  test    ecx, ecx
0x1400192c7  jnz     short loc_140019280
0x1400192c9  mov     esi, [rsp+140h+var_C4]
0x1400192cd  mov     r12d, [rsp+140h+var_C8]
0x1400192d2  jmp     loc_1400190E8
0x1400192d7  mov     eax, 0F000h
0x1400192dc  mov     r8, r13
0x1400192df  mov     dword ptr [rsp+140h+Size+4], eax
0x1400192e3  jnz     short loc_140019295
0x1400192e5  jmp     short loc_140019292
0x1400192e7  cmp     byte ptr [rcx+29h], 4
0x1400192eb  jb      loc_140018F8D
0x1400192f1  mov     rcx, [rcx+18h]
0x1400192f5  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x1400192fc  mov     edx, 0Bh
0x140019301  mov     dword ptr [rsp+140h+var_120], ebx
0x140019305  mov     r9, rdi
0x140019308  call    WPP_SF_qD
0x14001930d  xor     edx, edx
0x14001930f  jmp     loc_140018F8D
0x140019314  mov     rcx, cs:WPP_GLOBAL_Control
0x14001931b  cmp     rcx, rsi
0x14001931e  jz      loc_140019088
0x140019324  mov     eax, [rcx+2Ch]
0x140019327  test    al, 1
0x140019329  jz      loc_140019088
0x14001932f  cmp     byte ptr [rcx+29h], 1
0x140019333  jb      loc_140019088
0x140019339  mov     rcx, [rcx+18h]
0x14001933d  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x140019344  mov     edx, 0Dh
0x140019349  call    WPP_SF_
0x14001934e  jmp     loc_140019088
0x140019353  mov     rcx, cs:WPP_GLOBAL_Control
0x14001935a  cmp     rcx, rsi
0x14001935d  jz      loc_140019080
0x140019363  mov     eax, [rcx+2Ch]
0x140019366  test    al, 1
0x140019368  jz      loc_140019080
0x14001936e  cmp     byte ptr [rcx+29h], 1
0x140019372  jb      loc_140019080
0x140019378  mov     edx, 0Eh
0x14001937d  jmp     loc_14005E0BC
0x140019382  mov     rcx, cs:WPP_GLOBAL_Control
0x140019389  cmp     rcx, rsi
0x14001938c  jz      loc_140019080
0x140019392  mov     eax, [rcx+2Ch]
0x140019395  test    al, 1
0x140019397  jz      loc_140019080
0x14001939d  cmp     byte ptr [rcx+29h], 1
0x1400193a1  jb      loc_140019080
0x1400193a7  mov     edx, 0Fh
0x1400193ac  jmp     loc_14005E0BC
0x1400193b1  cmp     ebx, 40h ; '@'
0x1400193b4  jb      loc_1400191F2
0x1400193ba  cmp     dword ptr [r14], 424D53FEh
0x1400193c1  jnz     loc_1400191F2
0x1400193c7  mov     eax, [r14+14h]
0x1400193cb  add     eax, 240h
0x1400193d0  cmp     eax, ebx
0x1400193d2  cmova   eax, ebx
0x1400193d5  mov     [rsp+140h+var_E0], eax
0x1400193d9  jmp     loc_1400191F2
0x1400193de  mov     r8d, dword ptr [rsp+140h+Size]; Size
0x1400193e3  mov     eax, ebx
0x1400193e5  sub     eax, esi
0x1400193e7  cmp     r8d, eax
0x1400193ea  ja      loc_14005E153
0x1400193f0  mov     rcx, [rbp+40h+MemoryDescriptorList]; MemoryDescriptorList
0x1400193f4  mov     edx, esi
0x1400193f6  add     rdx, r14; Src
0x1400193f9  call    CopyBufferToMdl
0x1400193fe  mov     rax, [rdi+188h]
0x140019405  xor     r9d, r9d
0x140019408  mov     r8d, dword ptr [rsp+140h+Size]
0x14001940d  mov     rcx, rdi
0x140019410  mov     rdx, [rbp+40h+var_B8]
  ... truncated ...
```
