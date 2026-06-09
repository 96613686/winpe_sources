# CscExtendForWrite

- ea: `0x140001ed0`
- end: `0x140002677`
- name: `CscExtendForWrite`
- size: `1959`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `installer_update`

## callers

- `0x140001eb0`
- `0x1400173d0`

## callees

- `0x1400017c0`
- `0x140001ed0`
- `0x140003a00`
- `0x1400084f0`
- `0x1400169d4`
- `0x140018930`
- `0x140018b50`
- `0x1400190ec`
- `0x14001a624`
- `0x14001f108`
- `0x14001f314`
- `0x14001f58c`
- `0x140020168`
- `0x140023cc8`
- `0x14002f010`
- `0x14002f0f0`
- `0x14002f440`
- `0x14004fe58`
- `0x1400501e8`
- `0x14006872c`
- `0x14007a500`
- `0x140088580`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400023df`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400023df`

## pseudocode

```c
__int64 __fastcall CscExtendForWrite(__int64 a1, _QWORD *a2, _QWORD *a3, char a4)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  bool v6; // r15
  __int64 v8; // r14
  __int64 v9; // r13
  unsigned int v10; // edi
  __int64 v11; // r8
  __int64 v12; // r15
  unsigned __int8 v13; // cl
  unsigned int v14; // r12d
  __int64 v15; // rcx
  int v16; // eax
  _QWORD *v17; // r12
  int v18; // edx
  int v19; // esi
  __int64 v21; // r12
  __int64 v22; // rdx
  int InformationEntry; // r12d
  __int64 v24; // r8
  int v25; // esi
  int v26; // eax
  __int64 v27; // rdx
  bool v29; // [rsp+51h] [rbp-78h]
  _QWORD *v30; // [rsp+58h] [rbp-71h] BYREF
  __int64 v31; // [rsp+60h] [rbp-69h]
  _QWORD *v32; // [rsp+68h] [rbp-61h]
  __int64 v33; // [rsp+70h] [rbp-59h]
  __int128 v34; // [rsp+78h] [rbp-51h] BYREF
  _QWORD v35[10]; // [rsp+90h] [rbp-39h] BYREF

  v4 = *(_QWORD *)(a1 + 56);
  v5 = *(_QWORD *)(a1 + 72);
  v6 = *(_QWORD *)(a1 + 80) != (_QWORD)CscDeviceObject;
  v29 = v6;
  v32 = a3;
  v30 = a2;
  v34 = 0;
  if ( v4 )
    v33 = *(_QWORD *)(v4 + 144);
  else
    v33 = 0;
  if ( v5 )
    v8 = *(_QWORD *)(v5 + 56);
  else
    v8 = 0;
  CscUpdateAndCaptureConnectionStateEx(v4, v5, a1, 1u, (__int64)&v34, 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_cqcii(WPP_GLOBAL_Control->AttachedDevice);
  if ( v8 && (*(_DWORD *)(v8 + 24) & 0x809) != 0 )
  {
    v10 = -1073741811;
    v19 = 2527;
    goto LABEL_32;
  }
  if ( (BYTE1(v34) & 0x40) != 0 )
  {
    v10 = -1073741628;
    v19 = 2533;
    if ( (BYTE2(v34) & 1) == 0 )
      v10 = -1073741300;
    goto LABEL_32;
  }
  v9 = *(_QWORD *)(a1 + 56);
  v10 = 0;
  v11 = *(_QWORD *)(a1 + 72);
  v31 = v11;
  v12 = *(_QWORD *)(v9 + 144);
  if ( v12 && *(_WORD *)v12 != 0xEAA1 )
    v12 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_qqZDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)&WPP_GLOBAL_Control,
      v11,
      v9,
      v11,
      *(_QWORD *)(v11 + 80),
      *(_DWORD *)(v9 + 156),
      *(_DWORD *)(v9 + 164),
      *(_DWORD *)(v9 + 160));
    v11 = v31;
  }
  v13 = v34;
  if ( (v34 & 0x20) == 0 || (v34 & 0x10) != 0 || (v26 = *(_DWORD *)(v9 + 164), (v26 & 1) == 0) || (v26 & 2) != 0 )
  {
    v14 = 1786;
  }
  else
  {
    v14 = 0;
    if ( !(unsigned __int8)CscOKToMarkSparseOnOplockBreak(*(_QWORD *)(v11 + 80), v12)
      && ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v31 + 32) + 8LL))
      && (BYTE1(v34) & 2) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          51,
          WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
          *(_QWORD *)(v31 + 80));
      CscCloseServerStateAndUpdateTime(v9);
      CscTransitionFcbOffline(v9, 0, 8, 0);
      v27 = v31;
      *(_QWORD *)(v12 + 64) = MEMORY[0xFFFFF78000000014] + 100000000LL;
      CscUpdateAndCaptureConnectionStateEx(v9, v27, a1, 1u, (__int64)&v34, 1);
    }
    v13 = v34;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_a14d127135023115663fdf7ff6985b18_Traceguids, v14);
    v13 = v34;
  }
  if ( !v29 || (v13 & 0x10) != 0 )
    goto LABEL_30;
  v15 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL);
  if ( a4 )
  {
    if ( !*(_QWORD *)(v15 + 400) )
    {
      v10 = -1073741822;
      goto LABEL_76;
    }
    if ( (*(_DWORD *)(a1 + 128) & 2) == 0 )
    {
      *(_OWORD *)(a1 + 208) = 0;
      *(_OWORD *)(a1 + 224) = 0;
      *(_QWORD *)(a1 + 240) = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 400LL))(
              a1,
              v30,
              v32);
      goto LABEL_28;
    }
  }
  else
  {
    if ( !*(_QWORD *)(v15 + 392) )
    {
      v10 = -1073741822;
      goto LABEL_76;
    }
    if ( (*(_DWORD *)(a1 + 128) & 2) == 0 )
    {
      *(_OWORD *)(a1 + 208) = 0;
      *(_OWORD *)(a1 + 224) = 0;
      *(_QWORD *)(a1 + 240) = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 392LL))(
              a1,
              v30,
              v32);
LABEL_28:
      v10 = v16;
      if ( v16 >= 0 )
        goto LABEL_29;
      goto LABEL_76;
    }
  }
  v10 = -1073741536;
LABEL_76:
  if ( !(unsigned __int8)CscCheckRdrStatusTransitionIfNetErr(v10, &v34, v4) || (BYTE1(v34) & 0x40) != 0 )
  {
    v19 = 2577;
    goto LABEL_32;
  }
LABEL_29:
  v13 = v34;
  if ( (v34 & 0x30) == 0x20 && v8 )
  {
    memset(v35, 0, sizeof(v35));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_a14d127135023115663fdf7ff6985b18_Traceguids);
    v21 = *(_QWORD *)(v33 + 56);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_qqqqq(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        WPP_3bd1e00568fe30bc384778544301c268_Traceguids,
        v21,
        v35,
        0,
        0,
        0);
    }
    InformationEntry = CscEnQueryInformationEntry(v21, 0, (__int64)v35, 0, 0, 0);
    v24 = 0;
    if ( InformationEntry < 0 )
      v24 = 2648;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        WPP_3bd1e00568fe30bc384778544301c268_Traceguids,
        (unsigned int)InformationEntry,
        v24);
    }
    if ( InformationEntry < 0 )
    {
      v19 = 2606;
      goto LABEL_32;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, v22, v24, v4, v35[0], v35[7]);
    v17 = v30;
    if ( (v35[0] & 0x20) == 0 )
    {
      v25 = CscEnSetInformationEntryOpenHandle(*(_QWORD *)(v8 + 8), (v34 & 0x10) != 0, 20, 8, (__int64)v30, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          73,
          WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
          (unsigned int)v25);
      if ( v25 < 0 )
        goto LABEL_58;
    }
    v35[7] = *v30;
    v25 = CscStoreSetInformationEntry(*(_QWORD *)(v33 + 56), 0, 0, 0, (__int64)&v35[2], 0, 0);
    if ( v25 < 0 )
    {
LABEL_58:
      CscHandleStoreError(a1, (v34 & 0x10) != 0, (unsigned int)v25);
      v19 = 2660;
      goto LABEL_32;
    }
    *(_DWORD *)(v8 + 24) |= 0x400u;
    v13 = v34;
    goto LABEL_31;
  }
LABEL_30:
  v17 = v30;
LABEL_31:
  v18 = v13;
  v19 = 0;
  if ( (v13 & 0x10) != 0 && (v13 & 0x20) != 0 && v8 )
  {
    if ( a4 )
    {
      v10 = 0;
LABEL_93:
      *v32 = *v17;
      CscNotifyReportChange(a1, 8, 3);
      goto LABEL_32;
    }
    LOBYTE(v18) = (v13 & 0x10) != 0;
    v10 = CscEnSetInformationEntryOpenHandle(*(_QWORD *)(v8 + 8), v18, 20, 8, (__int64)v17, (__int64)&v30);
    if ( (v10 & 0x80000000) == 0 )
      goto LABEL_93;
  }
LABEL_32:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_a14d127135023115663fdf7ff6985b18_Traceguids, v10, v19);
  return v10;
}

```

## disassembly

```asm
0x140001ed0  mov     [rsp-8+arg_18], rbx
0x140001ed5  push    rbp
0x140001ed6  push    rsi
0x140001ed7  push    rdi
0x140001ed8  push    r12
0x140001eda  push    r13
0x140001edc  push    r14
0x140001ede  push    r15
0x140001ee0  lea     rbp, [rsp-27h]
0x140001ee5  sub     rsp, 0F0h
0x140001eec  mov     rax, cs:__security_cookie
0x140001ef3  xor     rax, rsp
0x140001ef6  mov     [rbp+57h+var_40], rax
0x140001efa  mov     rax, cs:CscDeviceObject
0x140001f01  xorps   xmm0, xmm0
0x140001f04  cmp     [rcx+50h], rax
0x140001f08  movzx   r12d, r9b
0x140001f0c  mov     rsi, [rcx+38h]
0x140001f10  mov     r13, rdx
0x140001f13  mov     rdi, [rcx+48h]
0x140001f17  setnz   r15b
0x140001f1b  mov     [rbp+57h+var_CF], r15b
0x140001f1f  mov     rbx, rcx
0x140001f22  mov     [rbp+57h+var_D0], r9b
0x140001f26  mov     [rbp+57h+var_B8], r8
0x140001f2a  mov     [rbp+57h+var_C8], rdx
0x140001f2e  movups  [rbp+57h+var_A8], xmm0
0x140001f32  test    rsi, rsi
0x140001f35  jz      loc_1400022BD
0x140001f3b  mov     rax, [rsi+90h]
0x140001f42  mov     [rbp+57h+var_B0], rax
0x140001f46  test    rdi, rdi
0x140001f49  jz      loc_1400022F1
0x140001f4f  mov     r14, [rdi+38h]
0x140001f53  lea     rax, [rbp+57h+var_A8]
0x140001f57  mov     byte ptr [rsp+120h+var_F8], 1
0x140001f5c  mov     r9b, 1
0x140001f5f  mov     [rsp+120h+var_100], rax
0x140001f64  mov     r8, rbx
0x140001f67  mov     rdx, rdi
0x140001f6a  mov     rcx, rsi
0x140001f6d  call    CscUpdateAndCaptureConnectionStateEx
0x140001f72  mov     rdx, cs:WPP_GLOBAL_Control
0x140001f79  lea     rax, WPP_GLOBAL_Control
0x140001f80  cmp     rdx, rax
0x140001f83  jz      short loc_140001F90
0x140001f85  mov     eax, [rdx+2Ch]
0x140001f88  test    al, 20h
0x140001f8a  jnz     loc_1400022F9
0x140001f90  test    r14, r14
0x140001f93  jz      short loc_140001FA3
0x140001f95  test    dword ptr [r14+18h], 809h
0x140001f9d  jnz     loc_14000213B
0x140001fa3  test    byte ptr [rbp+57h+var_A8+1], 40h
0x140001fa7  jnz     loc_14000233D
0x140001fad  mov     r13, [rbx+38h]
0x140001fb1  xor     edi, edi
0x140001fb3  mov     r8, [rbx+48h]
0x140001fb7  mov     [rbp+57h+var_C0], r8
0x140001fbb  mov     r15, [r13+90h]
0x140001fc2  test    r15, r15
0x140001fc5  jz      short loc_140001FD6
0x140001fc7  xor     eax, eax
0x140001fc9  mov     ecx, 0EAA1h
0x140001fce  cmp     cx, [r15]
0x140001fd2  cmovnz  r15, rax
0x140001fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140001fdd  lea     rdx, WPP_GLOBAL_Control
0x140001fe4  cmp     rcx, rdx
0x140001fe7  jz      short loc_140001FF4
0x140001fe9  mov     eax, [rcx+2Ch]
0x140001fec  test    al, 40h
0x140001fee  jnz     loc_140002358
0x140001ff4  movzx   ecx, byte ptr [rbp+57h+var_A8]
0x140001ff8  test    cl, 20h
0x140001ffb  jnz     loc_14000239C
0x140002001  mov     r12d, 6FAh
0x140002007  mov     r10, cs:WPP_GLOBAL_Control
0x14000200e  lea     r15, WPP_GLOBAL_Control
0x140002015  cmp     r10, r15
0x140002018  jz      short loc_140002026
0x14000201a  mov     eax, [r10+2Ch]
0x14000201e  test    al, 20h
0x140002020  jnz     loc_14000248C
0x140002026  movzx   r13d, [rbp+57h+var_D0]
0x14000202b  cmp     [rbp+57h+var_CF], dil
0x14000202f  jz      loc_1400020C4
0x140002035  test    cl, 10h
0x140002038  jnz     loc_1400020C4
0x14000203e  mov     rax, [rbx+50h]
0x140002042  mov     rcx, [rax+160h]
0x140002049  test    r13b, r13b
0x14000204c  jz      loc_140002271
0x140002052  cmp     [rcx+190h], rdi
0x140002059  jz      loc_1400024AD
0x14000205f  mov     eax, [rbx+80h]
0x140002065  test    al, 2
0x140002067  jnz     loc_140002147
0x14000206d  xor     eax, eax
0x14000206f  xorps   xmm0, xmm0
0x140002072  movups  xmmword ptr [rbx+0D0h], xmm0
0x140002079  movups  xmmword ptr [rbx+0E0h], xmm0
0x140002080  mov     [rbx+0F0h], rax
0x140002087  mov     rax, [rbx+50h]
0x14000208b  mov     rcx, [rax+160h]
0x140002092  mov     rax, [rcx+190h]
0x140002099  mov     r8, [rbp+57h+var_B8]
0x14000209d  mov     rcx, rbx
0x1400020a0  mov     rdx, [rbp+57h+var_C8]
0x1400020a4  call    _guard_dispatch_icall
0x1400020a9  mov     edi, eax
0x1400020ab  test    eax, eax
0x1400020ad  js      loc_1400024B9
0x1400020b3  movzx   ecx, byte ptr [rbp+57h+var_A8]
0x1400020b7  movzx   eax, cl
0x1400020ba  and     al, 30h
0x1400020bc  cmp     al, 20h ; ' '
0x1400020be  jz      loc_140002151
0x1400020c4  mov     r12, [rbp+57h+var_C8]
0x1400020c8  movzx   edx, cl
0x1400020cb  xor     esi, esi
0x1400020cd  shr     dl, 4
0x1400020d0  and     dl, 1
0x1400020d3  jnz     loc_14000260C
0x1400020d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020e0  lea     rax, WPP_GLOBAL_Control
0x1400020e7  cmp     rcx, rax
0x1400020ea  jnz     short loc_140002116
0x1400020ec  mov     eax, edi
0x1400020ee  mov     rcx, [rbp+57h+var_40]
0x1400020f2  xor     rcx, rsp; StackCookie
0x1400020f5  call    __security_check_cookie
0x1400020fa  mov     rbx, [rsp+120h+arg_18]
0x140002102  add     rsp, 0F0h
0x140002109  pop     r15
0x14000210b  pop     r14
0x14000210d  pop     r13
0x14000210f  pop     r12
0x140002111  pop     rdi
0x140002112  pop     rsi
0x140002113  pop     rbp
0x140002114  retn
0x140002116  mov     eax, [rcx+2Ch]
0x140002119  test    al, 20h
0x14000211b  jz      short loc_1400020EC
0x14000211d  mov     rcx, [rcx+18h]
0x140002121  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x140002128  mov     edx, 4Ah ; 'J'
0x14000212d  mov     dword ptr [rsp+120h+var_100], esi
0x140002131  mov     r9d, edi
0x140002134  call    WPP_SF_Dd
0x140002139  jmp     short loc_1400020EC
0x14000213b  mov     edi, 0C000000Dh
0x140002140  mov     esi, 9DFh
0x140002145  jmp     short loc_1400020D9
0x140002147  mov     edi, 0C0000120h
0x14000214c  jmp     loc_1400024B9
0x140002151  test    r14, r14
0x140002154  jz      loc_1400020C4
0x14000215a  xor     edx, edx; Val
0x14000215c  lea     rcx, [rbp+57h+var_90]; void *
0x140002160  mov     r8d, 50h ; 'P'; Size
0x140002166  call    memset
0x14000216b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002172  cmp     rcx, r15
0x140002175  jnz     loc_1400024DF
0x14000217b  mov     r15, [rbp+57h+var_B0]
0x14000217f  mov     r12, [r15+38h]
0x140002183  mov     rcx, cs:WPP_GLOBAL_Control
0x14000218a  lea     rax, WPP_GLOBAL_Control
0x140002191  cmp     rcx, rax
0x140002194  jz      short loc_1400021A3
0x140002196  test    dword ptr [rcx+2Ch], 40000h
0x14000219d  jnz     loc_140002504
0x1400021a3  mov     [rsp+120h+var_F8], 0
0x1400021ac  lea     r8, [rbp+57h+var_90]
0x1400021b0  xor     r9d, r9d
0x1400021b3  mov     [rsp+120h+var_100], 0
0x1400021bc  xor     edx, edx
0x1400021be  mov     rcx, r12
0x1400021c1  call    CscEnQueryInformationEntry
0x1400021c6  mov     r12d, eax
0x1400021c9  xor     r8d, r8d
0x1400021cc  test    r12d, r12d
0x1400021cf  mov     eax, 0A58h
0x1400021d4  cmovs   r8d, eax
0x1400021d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021df  lea     rax, WPP_GLOBAL_Control
0x1400021e6  cmp     rcx, rax
0x1400021e9  jz      short loc_1400021FF
0x1400021eb  test    dword ptr [rcx+2Ch], 40000h
0x1400021f2  jnz     loc_140002545
0x1400021f8  lea     rax, WPP_GLOBAL_Control
0x1400021ff  test    r12d, r12d
0x140002202  js      loc_140002567
0x140002208  mov     rcx, cs:WPP_GLOBAL_Control
0x14000220f  cmp     rcx, rax
0x140002212  jnz     loc_140002571
0x140002218  test    byte ptr [rbp+57h+var_90], 20h
0x14000221c  mov     r12, [rbp+57h+var_C8]
0x140002220  jz      loc_14000259D
0x140002226  mov     rax, [r12]
0x14000222a  xor     r9d, r9d
0x14000222d  mov     [rbp+57h+var_58], rax
0x140002231  xor     r8d, r8d
0x140002234  mov     rcx, [r15+38h]
0x140002238  lea     rax, [rbp+57h+var_80]
0x14000223c  mov     [rsp+120h+var_F0], 0
0x140002245  xor     edx, edx
0x140002247  mov     [rsp+120h+var_F8], 0
0x140002250  mov     [rsp+120h+var_100], rax
0x140002255  call    CscStoreSetInformationEntry
0x14000225a  mov     esi, eax
0x14000225c  test    eax, eax
0x14000225e  js      short loc_1400022D2
0x140002260  or      dword ptr [r14+18h], 400h
0x140002268  movzx   ecx, byte ptr [rbp+57h+var_A8]
0x14000226c  jmp     loc_1400020C8
0x140002271  cmp     [rcx+188h], rdi
0x140002278  jz      loc_1400024B4
0x14000227e  mov     eax, [rbx+80h]
0x140002284  test    al, 2
0x140002286  jnz     loc_140002147
0x14000228c  xor     eax, eax
0x14000228e  xorps   xmm0, xmm0
0x140002291  movups  xmmword ptr [rbx+0D0h], xmm0
0x140002298  movups  xmmword ptr [rbx+0E0h], xmm0
0x14000229f  mov     [rbx+0F0h], rax
0x1400022a6  mov     rax, [rbx+50h]
0x1400022aa  mov     rcx, [rax+160h]
0x1400022b1  mov     rax, [rcx+188h]
0x1400022b8  jmp     loc_140002099
0x1400022bd  mov     [rbp+57h+var_B0], 0
0x1400022c5  jmp     loc_140001F46
0x1400022ca  test    esi, esi
0x1400022cc  jns     loc_140002226
0x1400022d2  movzx   edx, byte ptr [rbp+57h+var_A8]
0x1400022d6  mov     r8d, esi
0x1400022d9  shr     dl, 4
0x1400022dc  mov     rcx, rbx
0x1400022df  and     dl, 1
0x1400022e2  call    CscHandleStoreError
0x1400022e7  mov     esi, 0A64h
0x1400022ec  jmp     loc_1400020D9
0x1400022f1  xor     r14d, r14d
0x1400022f4  jmp     loc_140001F53
0x1400022f9  mov     r9d, 59h ; 'Y'
0x1400022ff  test    r12b, r12b
0x140002302  mov     ecx, r9d
0x140002305  mov     eax, 4Eh ; 'N'
0x14000230a  cmovz   ecx, eax
0x14000230d  test    r15b, r15b
0x140002310  cmovz   r9d, eax
0x140002314  mov     rax, [r13+0]
0x140002318  mov     [rsp+120h+var_E8], rax
0x14000231d  mov     rax, [rsi+20h]
0x140002321  mov     [rsp+120h+var_F0], rax
0x140002326  mov     byte ptr [rsp+120h+var_F8], cl
0x14000232a  mov     rcx, [rdx+18h]
0x14000232e  mov     [rsp+120h+var_100], rdi
0x140002333  call    WPP_SF_cqcii
0x140002338  jmp     loc_140001F90
0x14000233d  test    byte ptr [rbp+57h+var_A8+2], 1
0x140002341  mov     edi, 0C00000C4h
0x140002346  mov     eax, 0C000020Ch
0x14000234b  mov     esi, 9E5h
0x140002350  cmovz   edi, eax
0x140002353  jmp     loc_1400020D9
0x140002358  mov     eax, [r13+0A0h]
0x14000235f  mov     r9, r13
0x140002362  mov     rcx, [rcx+18h]
0x140002366  mov     [rsp+120h+var_E0], eax
0x14000236a  mov     eax, [r13+0A4h]
0x140002371  mov     dword ptr [rsp+120h+var_E8], eax
0x140002375  mov     eax, [r13+9Ch]
0x14000237c  mov     dword ptr [rsp+120h+var_F0], eax
0x140002380  mov     rax, [r8+50h]
0x140002384  mov     [rsp+120h+var_F8], rax
0x140002389  mov     [rsp+120h+var_100], r8
0x14000238e  call    WPP_SF_qqZDDD
0x140002393  mov     r8, [rbp+57h+var_C0]
0x140002397  jmp     loc_140001FF4
0x14000239c  test    cl, 10h
0x14000239f  jnz     loc_140002001
0x1400023a5  mov     eax, [r13+0A4h]
0x1400023ac  test    al, 1
0x1400023ae  jz      loc_140002001
0x1400023b4  test    al, 2
0x1400023b6  jnz     loc_140002001
0x1400023bc  mov     rcx, [r8+50h]
0x1400023c0  mov     rdx, r15
0x1400023c3  xor     r12d, r12d
0x1400023c6  call    CscOKToMarkSparseOnOplockBreak
0x1400023cb  test    al, al
0x1400023cd  jnz     loc_140002483
0x1400023d3  mov     rcx, [rbp+57h+var_C0]
0x1400023d7  mov     rcx, [rcx+20h]
0x1400023db  mov     rcx, [rcx+8]; Resource
0x1400023df  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400023e6  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
