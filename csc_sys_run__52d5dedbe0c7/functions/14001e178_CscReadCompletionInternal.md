# CscReadCompletionInternal

- ea: `0x14001e178`
- end: `0x14001e775`
- name: `CscReadCompletionInternal`
- size: `1533`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002680`
- `0x14001e160`

## callees

- `0x140003a00`
- `0x1400043b4`
- `0x14000e070`
- `0x1400170cc`
- `0x140018930`
- `0x1400190ec`
- `0x14001a494`
- `0x14001ac1c`
- `0x14001b5bc`
- `0x14001e178`
- `0x14001ef50`
- `0x14001f1f8`
- `0x14001f3f4`
- `0x14002f010`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e1ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e6ae`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e1ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e6ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e6d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e6d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e497`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e497`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e590`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e6e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e590`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e6e0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001e389`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001e389`
- `ntoskrnl!KeSetEvent` at `0x14001e5e4`
- `ntoskrnl!KeSetEvent` at `0x14001e5e4`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e5f5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e5f5`
- `ntoskrnl!IoFreeMdl` at `0x14001e46e`
- `ntoskrnl!IoFreeMdl` at `0x14001e46e`
- `rdbss!RxLowIoCompletion` at `0x14001e64f`
- `rdbss!RxLowIoCompletion` at `0x14001e64f`

## pseudocode

```c
__int64 __fastcall CscReadCompletionInternal(__int64 a1, char a2)
{
  _DWORD *v2; // rsi
  __int64 v3; // r14
  int v4; // r12d
  __int64 v5; // r13
  __int64 v7; // rdi
  bool v8; // r15
  int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // r9
  __int64 v16; // r8
  char v17; // r15
  __int64 v18; // rsi
  int v19; // r8d
  __int64 v20; // rbx
  __int64 v21; // rbx
  int v22; // ecx
  __int64 v23; // rdi
  int v24; // r14d
  struct _MDL *v25; // rcx
  unsigned __int64 v26; // rcx
  _QWORD *v27; // rax
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  int v30; // r8d
  KIRQL CurrentIrql; // al
  unsigned int v32; // eax
  __int64 v33; // r8
  __int64 v34; // r9
  PDEVICE_OBJECT v35; // rcx
  int v36; // ebx
  char v38[4]; // [rsp+30h] [rbp-69h]
  char v39; // [rsp+60h] [rbp-39h]
  int v41; // [rsp+64h] [rbp-35h]
  __int128 v42; // [rsp+70h] [rbp-29h] BYREF
  __int128 v43; // [rsp+80h] [rbp-19h]
  __int64 v44; // [rsp+90h] [rbp-9h]
  __int128 v45; // [rsp+98h] [rbp-1h] BYREF

  v2 = *(_DWORD **)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 72);
  v4 = *(_DWORD *)(a1 + 568);
  v5 = *(_QWORD *)(a1 + 560);
  v7 = *(_QWORD *)(a1 + 272);
  v44 = 0;
  v8 = *(_QWORD *)(a1 + 80) != (_QWORD)CscDeviceObject;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v45 = 0;
  KeEnterCriticalRegion();
  CscGetContextsEx(a1, *(_QWORD *)(a1 + 56), &v42);
  LOBYTE(v9) = 1;
  CscUpdateAndCaptureConnectionStateEx((_DWORD)v2, v3, a1, v9, (__int64)&v45, 1);
  *(_QWORD *)(a1 + 528) = *(_QWORD *)(v7 + 16);
  v13 = v43;
  v39 = 0;
  if ( (_QWORD)v43 )
  {
    if ( *(_QWORD *)(v43 + 8) )
    {
      if ( (v45 & 8) != 0 )
      {
        v14 = v2[41];
        if ( (v14 & 2) != 0 || (v14 & 1) != 0 )
          v39 = 1;
      }
    }
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_24;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v12) = v8 ? 89 : 78;
    WPP_SF_cqqDDDDDi(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      v11,
      v12,
      v2,
      v3,
      v2[39],
      v2[41],
      v2[40],
      *(_DWORD *)(v3 + 72),
      v4,
      v5);
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
LABEL_24:
    v17 = v39;
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      if ( v13 )
        v15 = *(_QWORD *)(v13 + 8);
      else
        v15 = 0;
      if ( v13 )
        v16 = *(unsigned int *)(v13 + 24);
      else
        v16 = 0;
      v17 = v39;
      LOBYTE(v10) = v39 != 0 ? 89 : 78;
      v38[0] = v10;
      WPP_SF_qDqc(WPP_GLOBAL_Control->AttachedDevice, v10, v16, v13, v16, v15, *(_DWORD *)v38);
    }
    else
    {
      v17 = v39;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
        v7,
        *(_DWORD *)(v7 + 4));
  }
  v18 = v42;
  ExAcquireResourceExclusiveLite((PERESOURCE)(v42 + 88), 1u);
  if ( (BYTE1(v45) & 0x40) != 0 )
  {
    *(_DWORD *)(v7 + 4) |= 0x10u;
    v19 = *(_DWORD *)(v7 + 4);
    *(_DWORD *)(v7 + 108) = (BYTE2(v45) & 1) != 0 ? -1073741628 : -1073741300;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_a14d127135023115663fdf7ff6985b18_Traceguids, v7, v19);
  }
  if ( a2 )
    *(_DWORD *)(v7 + 4) |= 0x20u;
  *(_DWORD *)(v7 + 4) |= 2u;
  while ( 1 )
  {
    v20 = *(_QWORD *)(v18 + 72);
    if ( v20 == v18 + 72 )
      break;
    v21 = v20 - 56;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
        v21,
        *(_DWORD *)(v21 + 4));
    v22 = *(_DWORD *)(v21 + 4);
    if ( (v22 & 2) == 0 )
    {
      v36 = 833;
      goto LABEL_73;
    }
    v23 = *(_QWORD *)(v21 + 8);
    if ( (v22 & 0x10) != 0 )
    {
      v24 = *(_DWORD *)(v21 + 108);
      if ( *(_QWORD *)(v21 + 40) )
      {
        v25 = *(struct _MDL **)(v21 + 48);
        if ( v25 )
        {
          IoFreeMdl(v25);
          *(_QWORD *)(*(_QWORD *)(v23 + 40) + 8LL) = *(_QWORD *)(v21 + 32);
          *(_QWORD *)(v23 + 544) = *(_QWORD *)(v21 + 32);
        }
        ExFreePoolWithTag(*(PVOID *)(v21 + 40), 0);
        *(_QWORD *)(v21 + 40) = 0;
      }
    }
    else
    {
      v24 = *(_DWORD *)(v23 + 176);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_qdq(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
          v21,
          v22,
          *(_QWORD *)(v21 + 8));
      CscReadFinalize((PRX_CONTEXT)v23, *(void **)(v21 + 40), *(PMDL *)(v21 + 48), v17);
      if ( v24 >= 0 && v17 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(CscDevExtn + 2496), *(_QWORD *)(v23 + 184));
        v26 = *(_QWORD *)(v23 + 184);
        v18 = v42;
        if ( (*(_DWORD *)(v21 + 4) & 0x20) != 0 )
          _InterlockedAdd64((volatile signed __int64 *)(CscDevExtn + 2504), v26);
        else
          _InterlockedAdd64((volatile signed __int64 *)(CscDevExtn + 2512), v26);
      }
      else
      {
        v18 = v42;
      }
    }
    v27 = (_QWORD *)(v18 + 72);
    *(_QWORD *)(v23 + 272) = 0;
    v28 = *(_QWORD **)(v18 + 72);
    if ( v28[1] != v18 + 72 || (v29 = *v28, *(_QWORD **)(*v28 + 8LL) != v28) )
      __fastfail(3u);
    *v27 = v29;
    *(_QWORD *)(v29 + 8) = v27;
    KeLeaveCriticalRegion();
    v30 = *(_DWORD *)(v21 + 4);
    if ( (v30 & 0x20) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_qdq(
          WPP_GLOBAL_Control->AttachedDevice,
          23,
          WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
          v21,
          v30,
          v23);
      KeSetEvent((PRKEVENT)(v21 + 72), 0, 0);
    }
    else
    {
      CurrentIrql = KeGetCurrentIrql();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
          v23,
          v21,
          CurrentIrql);
      *(_DWORD *)(v23 + 176) = v24;
      *(_WORD *)(v23 + 522) &= ~1u;
      v32 = RxLowIoCompletion((PRX_CONTEXT)v23);
      v33 = (unsigned int)v41;
      v34 = v32;
      if ( !v24 )
        v24 = v32;
      if ( v24 < 0 )
        v33 = (unsigned int)v24;
      v41 = v33;
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_DDd(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
          v32,
          v24,
          v33);
      CscReadWriteAsyncContextFree(v35, v21, v33, v34);
    }
    KeEnterCriticalRegion();
  }
  v36 = 0;
LABEL_73:
  ExReleaseResourceLite((PERESOURCE)(v18 + 88));
  KeLeaveCriticalRegion();
  if ( v41 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 259;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_a14d127135023115663fdf7ff6985b18_Traceguids,
        (unsigned int)v41);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_a14d127135023115663fdf7ff6985b18_Traceguids, 259, v36);
  return 259;
}

```

## disassembly

```asm
0x14001e178  push    rbp
0x14001e17a  push    rbx
0x14001e17b  push    rsi
0x14001e17c  push    rdi
0x14001e17d  push    r12
0x14001e17f  push    r13
0x14001e181  push    r14
0x14001e183  push    r15
0x14001e185  lea     rbp, [rsp-1Fh]
0x14001e18a  sub     rsp, 0B8h
0x14001e191  mov     rax, cs:__security_cookie
0x14001e198  xor     rax, rsp
0x14001e19b  mov     [rbp+57h+var_48], rax
0x14001e19f  mov     rsi, [rcx+38h]
0x14001e1a3  xor     eax, eax
0x14001e1a5  mov     r14, [rcx+48h]
0x14001e1a9  xorps   xmm0, xmm0
0x14001e1ac  mov     r12d, [rcx+238h]
0x14001e1b3  xor     r9d, r9d
0x14001e1b6  mov     r13, [rcx+230h]
0x14001e1bd  mov     rbx, rcx
0x14001e1c0  mov     rdi, [rcx+110h]
0x14001e1c7  mov     [rbp+57h+var_60], rax
0x14001e1cb  mov     rax, cs:CscDeviceObject
0x14001e1d2  cmp     [rcx+50h], rax
0x14001e1d6  mov     [rbp+57h+var_8F], dl
0x14001e1d9  setnz   r15b
0x14001e1dd  mov     [rbp+57h+var_8C], r9d
0x14001e1e1  movups  [rbp+57h+var_80], xmm0
0x14001e1e5  movups  [rbp+57h+var_70], xmm0
0x14001e1e9  movups  [rbp+57h+var_58], xmm0
0x14001e1ed  call    cs:__imp_KeEnterCriticalRegion
0x14001e1f4  nop     dword ptr [rax+rax+00h]
0x14001e1f9  mov     rdx, [rbx+38h]
0x14001e1fd  lea     r8, [rbp+57h+var_80]
0x14001e201  mov     rcx, rbx
0x14001e204  call    CscGetContextsEx
0x14001e209  lea     rax, [rbp+57h+var_58]
0x14001e20d  mov     byte ptr [rsp+0F0h+Mdl], 1
0x14001e212  mov     r9b, 1
0x14001e215  mov     [rsp+0F0h+Src], rax
0x14001e21a  mov     r8, rbx
0x14001e21d  mov     rdx, r14
0x14001e220  mov     rcx, rsi
0x14001e223  call    CscUpdateAndCaptureConnectionStateEx
0x14001e228  mov     rax, [rdi+10h]
0x14001e22c  mov     [rbx+210h], rax
0x14001e233  mov     rbx, qword ptr [rbp+57h+var_70]
0x14001e237  test    rbx, rbx
0x14001e23a  jz      short loc_14001E25D
0x14001e23c  cmp     qword ptr [rbx+8], 0
0x14001e241  jz      short loc_14001E25D
0x14001e243  test    byte ptr [rbp+57h+var_58], 8
0x14001e247  jz      short loc_14001E25D
0x14001e249  mov     eax, [rsi+0A4h]
0x14001e24f  test    al, 2
0x14001e251  jnz     short loc_14001E257
0x14001e253  test    al, 1
0x14001e255  jz      short loc_14001E25D
0x14001e257  mov     [rbp+57h+var_90], 1
0x14001e25b  jmp     short loc_14001E261
0x14001e25d  mov     [rbp+57h+var_90], 0
0x14001e261  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e268  lea     rax, WPP_GLOBAL_Control
0x14001e26f  cmp     rcx, rax
0x14001e272  jz      loc_14001E374
0x14001e278  mov     eax, [rcx+2Ch]
0x14001e27b  test    al, 20h
0x14001e27d  jz      short loc_14001E2D5
0x14001e27f  mov     eax, [r14+48h]
0x14001e283  neg     r15b
0x14001e286  mov     rcx, [rcx+18h]
0x14001e28a  mov     edx, 11h
0x14001e28f  mov     [rsp+0F0h+var_98], r13
0x14001e294  sbb     r9b, r9b
0x14001e297  mov     [rsp+0F0h+var_A0], r12d
0x14001e29c  and     r9b, 0Bh
0x14001e2a0  mov     [rsp+0F0h+var_A8], eax
0x14001e2a4  add     r9b, 4Eh ; 'N'
0x14001e2a8  mov     eax, [rsi+0A0h]
0x14001e2ae  mov     [rsp+0F0h+var_B0], eax
0x14001e2b2  mov     eax, [rsi+0A4h]
0x14001e2b8  mov     [rsp+0F0h+var_B8], eax
0x14001e2bc  mov     eax, [rsi+9Ch]
0x14001e2c2  mov     dword ptr [rsp+0F0h+var_C0], eax
0x14001e2c6  mov     [rsp+0F0h+Mdl], r14
0x14001e2cb  mov     [rsp+0F0h+Src], rsi
0x14001e2d0  call    WPP_SF_cqqDDDDDi
0x14001e2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e2dc  lea     r13, WPP_GLOBAL_Control
0x14001e2e3  cmp     rcx, r13
0x14001e2e6  jz      loc_14001E37B
0x14001e2ec  mov     eax, [rcx+2Ch]
0x14001e2ef  test    al, 40h
0x14001e2f1  jz      short loc_14001E33C
0x14001e2f3  test    rbx, rbx
0x14001e2f6  jz      short loc_14001E2FE
0x14001e2f8  mov     r9, [rbx+8]
0x14001e2fc  jmp     short loc_14001E301
0x14001e2fe  xor     r9d, r9d
0x14001e301  test    rbx, rbx
0x14001e304  jz      short loc_14001E30C
0x14001e306  mov     r8d, [rbx+18h]
0x14001e30a  jmp     short loc_14001E30F
0x14001e30c  xor     r8d, r8d
0x14001e30f  mov     r15b, [rbp+57h+var_90]
0x14001e313  mov     rcx, [rcx+18h]
0x14001e317  mov     al, r15b
0x14001e31a  neg     al
0x14001e31c  sbb     dl, dl
0x14001e31e  and     dl, 0Bh
0x14001e321  add     dl, 4Eh ; 'N'
0x14001e324  mov     [rsp+0F0h+var_C0], dl
0x14001e328  mov     [rsp+0F0h+Mdl], r9
0x14001e32d  mov     r9, rbx
0x14001e330  mov     dword ptr [rsp+0F0h+Src], r8d
0x14001e335  call    WPP_SF_qDqc
0x14001e33a  jmp     short loc_14001E340
0x14001e33c  mov     r15b, [rbp+57h+var_90]
0x14001e340  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e347  cmp     rcx, r13
0x14001e34a  jz      short loc_14001E37F
0x14001e34c  mov     eax, [rcx+2Ch]
0x14001e34f  test    al, 20h
0x14001e351  jz      short loc_14001E37F
0x14001e353  mov     eax, [rdi+4]
0x14001e356  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001e35d  mov     rcx, [rcx+18h]
0x14001e361  mov     edx, 13h
0x14001e366  mov     r9, rdi
0x14001e369  mov     dword ptr [rsp+0F0h+Src], eax
0x14001e36d  call    WPP_SF_qD
0x14001e372  jmp     short loc_14001E37F
0x14001e374  lea     r13, WPP_GLOBAL_Control
0x14001e37b  mov     r15b, [rbp+57h+var_90]
0x14001e37f  mov     rsi, qword ptr [rbp+57h+var_80]
0x14001e383  mov     dl, 1; Wait
0x14001e385  lea     rcx, [rsi+58h]; Resource
0x14001e389  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001e390  nop     dword ptr [rax+rax+00h]
0x14001e395  test    byte ptr [rbp+57h+var_58+1], 40h
0x14001e399  jz      short loc_14001E3EB
0x14001e39b  or      dword ptr [rdi+4], 10h
0x14001e39f  mov     al, byte ptr [rbp+57h+var_58+2]
0x14001e3a2  mov     r8d, [rdi+4]
0x14001e3a6  and     al, 1
0x14001e3a8  neg     al
0x14001e3aa  sbb     ecx, ecx
0x14001e3ac  and     ecx, 0FFFFFEB8h
0x14001e3b2  add     ecx, 0C000020Ch
0x14001e3b8  mov     [rdi+6Ch], ecx
0x14001e3bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e3c2  cmp     rcx, r13
0x14001e3c5  jz      short loc_14001E3EB
0x14001e3c7  mov     eax, [rcx+2Ch]
0x14001e3ca  test    al, 20h
0x14001e3cc  jz      short loc_14001E3EB
0x14001e3ce  mov     rcx, [rcx+18h]
0x14001e3d2  mov     edx, 14h
0x14001e3d7  mov     dword ptr [rsp+0F0h+Src], r8d
0x14001e3dc  mov     r9, rdi
0x14001e3df  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001e3e6  call    WPP_SF_qD
0x14001e3eb  xor     r12d, r12d
0x14001e3ee  cmp     [rbp+57h+var_8F], r12b
0x14001e3f2  jz      short loc_14001E3F8
0x14001e3f4  or      dword ptr [rdi+4], 20h
0x14001e3f8  or      dword ptr [rdi+4], 2
0x14001e3fc  lea     rax, [rsi+48h]
0x14001e400  mov     rbx, [rax]
0x14001e403  cmp     rbx, rax
0x14001e406  jz      loc_14001E6CD
0x14001e40c  add     rbx, 0FFFFFFFFFFFFFFC8h
0x14001e410  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e417  cmp     rcx, r13
0x14001e41a  jz      short loc_14001E442
0x14001e41c  mov     eax, [rcx+2Ch]
0x14001e41f  test    al, 20h
0x14001e421  jz      short loc_14001E442
0x14001e423  mov     eax, [rbx+4]
0x14001e426  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001e42d  mov     rcx, [rcx+18h]
0x14001e431  mov     edx, 15h
0x14001e436  mov     r9, rbx
0x14001e439  mov     dword ptr [rsp+0F0h+Src], eax
0x14001e43d  call    WPP_SF_qD
0x14001e442  mov     ecx, [rbx+4]
0x14001e445  test    cl, 2
0x14001e448  jz      loc_14001E6C6
0x14001e44e  mov     rdi, [rbx+8]
0x14001e452  test    cl, 10h
0x14001e455  jz      short loc_14001E4AC
0x14001e457  mov     r14d, [rbx+6Ch]
0x14001e45b  cmp     [rbx+28h], r12
0x14001e45f  jz      loc_14001E564
0x14001e465  mov     rcx, [rbx+30h]; Mdl
0x14001e469  test    rcx, rcx
0x14001e46c  jz      short loc_14001E491
0x14001e46e  call    cs:__imp_IoFreeMdl
0x14001e475  nop     dword ptr [rax+rax+00h]
0x14001e47a  mov     rax, [rbx+20h]
0x14001e47e  mov     rcx, [rdi+28h]
0x14001e482  mov     [rcx+8], rax
0x14001e486  mov     rax, [rbx+20h]
0x14001e48a  mov     [rdi+220h], rax
0x14001e491  mov     rcx, [rbx+28h]; P
0x14001e495  xor     edx, edx; Tag
0x14001e497  call    cs:__imp_ExFreePoolWithTag
0x14001e49e  nop     dword ptr [rax+rax+00h]
0x14001e4a3  mov     [rbx+28h], r12
0x14001e4a7  jmp     loc_14001E564
0x14001e4ac  mov     r14d, [rdi+0B0h]
0x14001e4b3  mov     r10, cs:WPP_GLOBAL_Control
0x14001e4ba  cmp     r10, r13
0x14001e4bd  jz      short loc_14001E4E8
0x14001e4bf  mov     eax, [r10+2Ch]
0x14001e4c3  test    al, 20h
0x14001e4c5  jz      short loc_14001E4E8
0x14001e4c7  mov     [rsp+0F0h+Mdl], rdi
0x14001e4cc  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001e4d3  mov     dword ptr [rsp+0F0h+Src], ecx
0x14001e4d7  mov     edx, 16h
0x14001e4dc  mov     rcx, [r10+18h]
0x14001e4e0  mov     r9, rbx
0x14001e4e3  call    WPP_SF_qdq
0x14001e4e8  mov     rax, [rbx+30h]
0x14001e4ec  lea     r8, [rbp+57h+var_58]
0x14001e4f0  mov     r9, [rbx+20h]
0x14001e4f4  lea     rdx, [rbp+57h+var_80]
0x14001e4f8  mov     [rsp+0F0h+var_C0], r15b; char
0x14001e4fd  mov     rcx, rdi; RxContext
0x14001e500  mov     [rsp+0F0h+Mdl], rax; Mdl
0x14001e505  mov     rax, [rbx+28h]
0x14001e509  mov     [rsp+0F0h+Src], rax; Src
0x14001e50e  call    CscReadFinalize
0x14001e513  test    r14d, r14d
0x14001e516  js      short loc_14001E560
0x14001e518  test    r15b, r15b
0x14001e51b  jz      short loc_14001E560
0x14001e51d  mov     rcx, cs:CscDevExtn
0x14001e524  mov     rax, [rdi+0B8h]
0x14001e52b  lock add [rcx+9C0h], rax
0x14001e533  mov     eax, [rbx+4]
0x14001e536  test    al, 20h
0x14001e538  mov     rax, cs:CscDevExtn
0x14001e53f  mov     rcx, [rdi+0B8h]
0x14001e546  mov     rsi, qword ptr [rbp+57h+var_80]
0x14001e54a  jz      short loc_14001E556
0x14001e54c  lock add [rax+9C8h], rcx
0x14001e554  jmp     short loc_14001E564
0x14001e556  lock add [rax+9D0h], rcx
0x14001e55e  jmp     short loc_14001E564
0x14001e560  mov     rsi, qword ptr [rbp+57h+var_80]
0x14001e564  lea     rax, [rsi+48h]
0x14001e568  mov     [rdi+110h], r12
0x14001e56f  mov     rcx, [rax]
0x14001e572  cmp     [rcx+8], rax
0x14001e576  jnz     loc_14001E6BF
0x14001e57c  mov     rdx, [rcx]
0x14001e57f  cmp     [rdx+8], rcx
0x14001e583  jnz     loc_14001E6BF
0x14001e589  mov     [rax], rdx
0x14001e58c  mov     [rdx+8], rax
0x14001e590  call    cs:__imp_KeLeaveCriticalRegion
0x14001e597  nop     dword ptr [rax+rax+00h]
0x14001e59c  mov     r8d, [rbx+4]
0x14001e5a0  test    r8b, 20h
0x14001e5a4  jz      short loc_14001E5F5
0x14001e5a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e5ad  cmp     rcx, r13
0x14001e5b0  jz      short loc_14001E5DB
0x14001e5b2  mov     eax, [rcx+2Ch]
0x14001e5b5  test    al, 20h
0x14001e5b7  jz      short loc_14001E5DB
0x14001e5b9  mov     rcx, [rcx+18h]
0x14001e5bd  mov     edx, 17h
0x14001e5c2  mov     [rsp+0F0h+Mdl], rdi
0x14001e5c7  mov     r9, rbx
0x14001e5ca  mov     dword ptr [rsp+0F0h+Src], r8d
0x14001e5cf  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001e5d6  call    WPP_SF_qdq
0x14001e5db  lea     rcx, [rbx+48h]; Event
0x14001e5df  xor     r8d, r8d; Wait
0x14001e5e2  xor     edx, edx; Increment
0x14001e5e4  call    cs:__imp_KeSetEvent
0x14001e5eb  nop     dword ptr [rax+rax+00h]
0x14001e5f0  jmp     loc_14001E6AE
0x14001e5f5  call    cs:__imp_KeGetCurrentIrql
0x14001e5fc  nop     dword ptr [rax+rax+00h]
0x14001e601  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e608  cmp     rcx, r13
0x14001e60b  jz      short loc_14001E639
0x14001e60d  mov     edx, [rcx+2Ch]
0x14001e610  test    dl, 20h
0x14001e613  jz      short loc_14001E639
0x14001e615  mov     rcx, [rcx+18h]
0x14001e619  lea     r8, WPP_a14d127135023115663fdf7ff6985b18_Traceguids
0x14001e620  movzx   eax, al
0x14001e623  mov     edx, 18h
0x14001e628  mov     dword ptr [rsp+0F0h+Mdl], eax
  ... truncated ...
```
