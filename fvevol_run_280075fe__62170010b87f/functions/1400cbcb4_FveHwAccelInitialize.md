# FveHwAccelInitialize

- ea: `0x1400cbcb4`
- end: `0x1400cc1f9`
- name: `FveHwAccelInitialize`
- size: `1349`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400eb6e0`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000d500`
- `0x140021d00`
- `0x1400cbcb4`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400cc0d0`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400cc0d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cc14e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cc14e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cbd5b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cbd5b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cbd6b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cc15a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cbd6b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cc15a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cbd3c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cbd3c`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400cc03c`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400cc03c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc19c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc19c`
- `ntoskrnl!ExAllocatePool2` at `0x1400cbef7`
- `ntoskrnl!ExAllocatePool2` at `0x1400cc090`
- `ntoskrnl!ExAllocatePool2` at `0x1400cbef7`
- `ntoskrnl!ExAllocatePool2` at `0x1400cc090`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeOffloadWorkspace` at `0x1400cbd9d`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeOffloadWorkspace` at `0x1400cbd9d`
- `ext-ms-win-accel-api-km-l1-1-1!AccelAcquireResourcesSync` at `0x1400cbe74`
- `ext-ms-win-accel-api-km-l1-1-1!AccelAcquireResourcesSync` at `0x1400cbf6a`
- `ext-ms-win-accel-api-km-l1-1-1!AccelAcquireResourcesSync` at `0x1400cbe74`
- `ext-ms-win-accel-api-km-l1-1-1!AccelAcquireResourcesSync` at `0x1400cbf6a`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyOffloadWorkspace` at `0x1400cc183`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyOffloadWorkspace` at `0x1400cc183`
- `ext-ms-win-accel-api-km-l1-1-1!AccelCloseResource` at `0x1400cc16e`
- `ext-ms-win-accel-api-km-l1-1-1!AccelCloseResource` at `0x1400cc16e`
- `ext-ms-win-accel-api-km-l1-1-1!AccelQueryDescriptorSize` at `0x1400cbfe5`
- `ext-ms-win-accel-api-km-l1-1-1!AccelQueryDescriptorSize` at `0x1400cbfe5`

## pseudocode

```c
__int64 __fastcall FveHwAccelInitialize(__int64 a1)
{
  void *v2; // r15
  __int64 v3; // r14
  char v4; // r12
  int v5; // eax
  int v6; // ebx
  bool v7; // zf
  unsigned int v8; // eax
  int v9; // eax
  __int64 Pool2; // rax
  _QWORD *v11; // rcx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  ULONG RecommendedSharedDataAlignment; // r8d
  int v16; // r9d
  struct _NPAGED_LOOKASIDE_LIST *v17; // rsi
  int v18; // eax
  __int64 *v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  int Size; // [rsp+20h] [rbp-99h]
  ULONG Tag; // [rsp+28h] [rbp-91h]
  __int128 v26; // [rsp+40h] [rbp-79h] BYREF
  __int128 v27; // [rsp+50h] [rbp-69h]
  __int128 v28; // [rsp+60h] [rbp-59h] BYREF
  __int128 v29; // [rsp+70h] [rbp-49h]
  _QWORD v30[18]; // [rsp+80h] [rbp-39h] BYREF
  SIZE_T v31; // [rsp+120h] [rbp+67h] BYREF
  __int64 v32; // [rsp+128h] [rbp+6Fh] BYREF

  v28 = 0;
  v29 = 0;
  memset(v30, 0, 0x58u);
  v26 = 0;
  v2 = 0;
  v32 = 0;
  v27 = 0;
  v3 = 0;
  LODWORD(v31) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids);
  }
  KeEnterCriticalRegion();
  v4 = 1;
  if ( !ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 10352), 1u) )
    KeLeaveCriticalRegion();
  *(_QWORD *)&v28 = 2097153;
  *((_QWORD *)&v28 + 1) = &GUID_FVE_HW_OFFLOAD_WORKSPACE;
  *((_QWORD *)&v29 + 1) = *(_QWORD *)a1;
  *(_QWORD *)&v29 = 0;
  v5 = AccelInitializeOffloadWorkspace(&v28, &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids,
        (unsigned int)v5);
    }
    goto LABEL_56;
  }
  v7 = (*(_DWORD *)(a1 + 9680) & 0x800000) == 0;
  v30[1] = v32;
  v30[2] = &GUID_ACCELERATOR_TYPE_CRYPTO;
  v26 = 0;
  v30[5] = FveHwAccelNotifyCallback;
  v30[0] = 5767169;
  v30[7] = 0x10000;
  v30[6] = a1;
  v30[3] = 0x100000001LL;
  v30[4] = 0;
  memset(&v30[8], 0, 24);
  v27 = 0;
  LODWORD(v26) = 2097153;
  if ( !v7 )
  {
    v8 = 8;
    DWORD2(v27) = 8;
    goto LABEL_21;
  }
  v9 = AccelAcquireResourcesSync(v30, &v26);
  v6 = v9;
  if ( v9 != -1073741632 )
  {
    v4 = 0;
    if ( v9 != -1073741789 )
      goto LABEL_28;
    v8 = DWORD2(v27);
    v4 = 1;
LABEL_21:
    Pool2 = ExAllocatePool2(64, v8, 809850438);
    v2 = (void *)Pool2;
    if ( !Pool2 )
    {
      v6 = -1073741670;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_53:
        v19 = FVE_HW_ACCEL_CRYPTO_INITIALIZED;
        Tag = 0;
        if ( v6 < 0 )
          v19 = FVE_HW_ACCEL_CRYPTO_INITIALIZED_FAILED;
        Size = v31;
        FveLogStatusEventWithData(a1, 0, v19);
        goto LABEL_56;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, 3221225626LL);
LABEL_29:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v13 = 24;
LABEL_33:
        WPP_SF_d(v12->AttachedDevice, v13, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, (unsigned int)v6);
        goto LABEL_52;
      }
      goto LABEL_52;
    }
    v7 = (*(_DWORD *)(a1 + 9680) & 0x800000) == 0;
    v11 = (_QWORD *)Pool2;
    *(_QWORD *)&v27 = Pool2;
    if ( !v7 )
    {
LABEL_35:
      v3 = *v11;
      if ( (*(_DWORD *)(a1 + 9680) & 0x800000) != 0 )
      {
        v6 = 0;
      }
      else
      {
        v6 = AccelQueryDescriptorSize(*v11, &v31);
        if ( v6 < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v13 = 25;
            goto LABEL_33;
          }
LABEL_52:
          if ( !v4 )
            goto LABEL_56;
          goto LABEL_53;
        }
        v14 = v31;
        if ( (unsigned int)v31 > 8 )
        {
LABEL_44:
          LODWORD(v31) = v14;
          RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
          if ( ((RecommendedSharedDataAlignment - 1) & RecommendedSharedDataAlignment) != 0
            || !RecommendedSharedDataAlignment )
          {
            v16 = v31;
            if ( (unsigned int)v31 % RecommendedSharedDataAlignment )
              v16 = RecommendedSharedDataAlignment - (unsigned int)v31 % RecommendedSharedDataAlignment + v31;
          }
          else
          {
            v16 = ~(RecommendedSharedDataAlignment - 1) & (RecommendedSharedDataAlignment + v31 - 1);
          }
          LODWORD(v31) = v16;
          v17 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 809850438);
          if ( v17 )
          {
            ExInitializeNPagedLookasideList(v17, 0, 0, 0x200u, (unsigned int)v31, 0x30455646u, 0);
            *(_QWORD *)(a1 + 10464) = v32;
            v18 = v31;
            *(_QWORD *)(a1 + 10472) = v3;
            v3 = 0;
            *(_DWORD *)(a1 + 10480) = v18;
            v32 = 0;
            *(_QWORD *)(a1 + 10456) = v17;
          }
          else
          {
            v6 = -1073741670;
          }
          goto LABEL_52;
        }
      }
      v14 = 8;
      goto LABEL_44;
    }
    v6 = AccelAcquireResourcesSync(v30, &v26);
LABEL_28:
    if ( v6 < 0 )
      goto LABEL_29;
    v11 = (_QWORD *)v27;
    goto LABEL_35;
  }
  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids);
  }
LABEL_56:
  ExReleaseResourceLite((PERESOURCE)(a1 + 10352));
  KeLeaveCriticalRegion();
  if ( v3 )
    AccelCloseResource(v3);
  if ( v32 )
    AccelDestroyOffloadWorkspace(v32, v20, v21, v22, Size, Tag);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x30455646u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400cbcb4  mov     [rsp-8+arg_10], rbx
0x1400cbcb9  push    rbp
0x1400cbcba  push    rsi
0x1400cbcbb  push    rdi
0x1400cbcbc  push    r12
0x1400cbcbe  push    r13
0x1400cbcc0  push    r14
0x1400cbcc2  push    r15
0x1400cbcc4  lea     rbp, [rsp-27h]
0x1400cbcc9  sub     rsp, 0E0h
0x1400cbcd0  xorps   xmm0, xmm0
0x1400cbcd3  xor     edx, edx; Val
0x1400cbcd5  mov     rdi, rcx
0x1400cbcd8  lea     rcx, [rbp+57h+var_90]; void *
0x1400cbcdc  movups  [rbp+57h+var_B0], xmm0
0x1400cbce0  lea     r8d, [rdx+58h]; Size
0x1400cbce4  movups  [rbp+57h+var_A0], xmm0
0x1400cbce8  call    memset
0x1400cbced  xor     esi, esi
0x1400cbcef  xorps   xmm0, xmm0
0x1400cbcf2  movups  [rbp+57h+var_D0], xmm0
0x1400cbcf6  mov     r15d, esi
0x1400cbcf9  mov     [rbp+57h+arg_8], rsi
0x1400cbcfd  movups  [rbp+57h+var_C0], xmm0
0x1400cbd01  mov     r14d, esi
0x1400cbd04  mov     dword ptr [rbp+57h+arg_0], esi
0x1400cbd07  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbd0e  lea     rax, WPP_GLOBAL_Control
0x1400cbd15  cmp     rcx, rax
0x1400cbd18  jz      short loc_1400CBD3C
0x1400cbd1a  test    dword ptr [rcx+2Ch], 400000h
0x1400cbd21  jz      short loc_1400CBD3C
0x1400cbd23  cmp     byte ptr [rcx+29h], 5
0x1400cbd27  jb      short loc_1400CBD3C
0x1400cbd29  mov     rcx, [rcx+18h]
0x1400cbd2d  lea     edx, [rsi+14h]
0x1400cbd30  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cbd37  call    WPP_SF_
0x1400cbd3c  call    cs:__imp_KeEnterCriticalRegion
0x1400cbd43  nop     dword ptr [rax+rax+00h]
0x1400cbd48  lea     r13, [rdi+2870h]
0x1400cbd4f  mov     r12d, 1
0x1400cbd55  mov     dl, r12b; Wait
0x1400cbd58  mov     rcx, r13; Resource
0x1400cbd5b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400cbd62  nop     dword ptr [rax+rax+00h]
0x1400cbd67  test    al, al
0x1400cbd69  jnz     short loc_1400CBD77
0x1400cbd6b  call    cs:__imp_KeLeaveCriticalRegion
0x1400cbd72  nop     dword ptr [rax+rax+00h]
0x1400cbd77  lea     rax, GUID_FVE_HW_OFFLOAD_WORKSPACE
0x1400cbd7e  mov     qword ptr [rbp+57h+var_B0], 200001h
0x1400cbd86  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1400cbd8a  lea     rdx, [rbp+57h+arg_8]
0x1400cbd8e  mov     rax, [rdi]
0x1400cbd91  lea     rcx, [rbp+57h+var_B0]
0x1400cbd95  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1400cbd99  mov     qword ptr [rbp+57h+var_A0], rsi
0x1400cbd9d  call    cs:__imp_AccelInitializeOffloadWorkspace
0x1400cbda4  nop     dword ptr [rax+rax+00h]
0x1400cbda9  mov     ebx, eax
0x1400cbdab  test    eax, eax
0x1400cbdad  jns     short loc_1400CBDFA
0x1400cbdaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbdb6  lea     rdi, WPP_GLOBAL_Control
0x1400cbdbd  cmp     rcx, rdi
0x1400cbdc0  jz      loc_1400CC14B
0x1400cbdc6  test    dword ptr [rcx+2Ch], 400000h
0x1400cbdcd  jz      loc_1400CC14B
0x1400cbdd3  cmp     byte ptr [rcx+29h], 2
0x1400cbdd7  jb      loc_1400CC14B
0x1400cbddd  mov     rcx, [rcx+18h]
0x1400cbde1  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cbde8  mov     edx, 15h
0x1400cbded  mov     r9d, eax
0x1400cbdf0  call    WPP_SF_d
0x1400cbdf5  jmp     loc_1400CC14B
0x1400cbdfa  test    dword ptr [rdi+25D0h], 800000h
0x1400cbe04  xorps   xmm0, xmm0
0x1400cbe07  mov     rax, [rbp+57h+arg_8]
0x1400cbe0b  mov     [rbp+57h+var_88], rax
0x1400cbe0f  lea     rax, GUID_ACCELERATOR_TYPE_CRYPTO
0x1400cbe16  mov     [rbp+57h+var_80], rax
0x1400cbe1a  lea     rax, FveHwAccelNotifyCallback
0x1400cbe21  movups  [rbp+57h+var_D0], xmm0
0x1400cbe25  mov     [rbp+57h+var_68], rax
0x1400cbe29  mov     [rbp+57h+var_90], 580001h
0x1400cbe31  mov     [rbp+57h+var_58], 10000h
0x1400cbe39  mov     [rbp+57h+var_60], rdi
0x1400cbe3d  mov     [rbp+57h+var_78], r12d
0x1400cbe41  mov     [rbp+57h+var_74], r12d
0x1400cbe45  mov     [rbp+57h+var_70], rsi
0x1400cbe49  mov     [rbp+57h+var_50], rsi
0x1400cbe4d  mov     [rbp+57h+var_48], rsi
0x1400cbe51  mov     [rbp+57h+var_40], rsi
0x1400cbe55  movups  [rbp+57h+var_C0], xmm0
0x1400cbe59  mov     dword ptr [rbp+57h+var_D0], 200001h
0x1400cbe60  jz      short loc_1400CBE6C
0x1400cbe62  mov     eax, 8
0x1400cbe67  mov     dword ptr [rbp+57h+var_C0+8], eax
0x1400cbe6a  jmp     short loc_1400CBEEA
0x1400cbe6c  lea     rdx, [rbp+57h+var_D0]
0x1400cbe70  lea     rcx, [rbp+57h+var_90]
0x1400cbe74  call    cs:__imp_AccelAcquireResourcesSync
0x1400cbe7b  nop     dword ptr [rax+rax+00h]
0x1400cbe80  mov     ebx, eax
0x1400cbe82  cmp     eax, 0C00000C0h
0x1400cbe87  jnz     short loc_1400CBED3
0x1400cbe89  mov     ebx, esi
0x1400cbe8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbe92  lea     rdi, WPP_GLOBAL_Control
0x1400cbe99  cmp     rcx, rdi
0x1400cbe9c  jz      loc_1400CC14B
0x1400cbea2  test    dword ptr [rcx+2Ch], 400000h
0x1400cbea9  jz      loc_1400CC14B
0x1400cbeaf  cmp     byte ptr [rcx+29h], 4
0x1400cbeb3  jb      loc_1400CC14B
0x1400cbeb9  mov     rcx, [rcx+18h]
0x1400cbebd  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cbec4  mov     edx, 16h
0x1400cbec9  call    WPP_SF_
0x1400cbece  jmp     loc_1400CC14B
0x1400cbed3  mov     r12b, sil
0x1400cbed6  cmp     eax, 0C0000023h
0x1400cbedb  jnz     loc_1400CBF78
0x1400cbee1  mov     eax, dword ptr [rbp+57h+var_C0+8]
0x1400cbee4  mov     r12d, 1
0x1400cbeea  mov     edx, eax
0x1400cbeec  mov     ecx, 40h ; '@'
0x1400cbef1  mov     r8d, 30455646h
0x1400cbef7  call    cs:__imp_ExAllocatePool2
0x1400cbefe  nop     dword ptr [rax+rax+00h]
0x1400cbf03  mov     r15, rax
0x1400cbf06  test    rax, rax
0x1400cbf09  jnz     short loc_1400CBF4F
0x1400cbf0b  mov     ebx, 0C000009Ah
0x1400cbf10  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbf17  lea     rax, WPP_GLOBAL_Control
0x1400cbf1e  cmp     rcx, rax
0x1400cbf21  jz      loc_1400CC110
0x1400cbf27  test    dword ptr [rcx+2Ch], 400000h
0x1400cbf2e  jz      short loc_1400CBF7C
0x1400cbf30  cmp     byte ptr [rcx+29h], 2
0x1400cbf34  jb      short loc_1400CBF7C
0x1400cbf36  mov     rcx, [rcx+18h]
0x1400cbf3a  lea     edx, [r15+17h]
0x1400cbf3e  mov     r9d, ebx
0x1400cbf41  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cbf48  call    WPP_SF_d
0x1400cbf4d  jmp     short loc_1400CBF7C
0x1400cbf4f  test    dword ptr [rdi+25D0h], 800000h
0x1400cbf59  mov     rcx, rax
0x1400cbf5c  mov     qword ptr [rbp+57h+var_C0], rax
0x1400cbf60  jnz     short loc_1400CBFCB
0x1400cbf62  lea     rdx, [rbp+57h+var_D0]
0x1400cbf66  lea     rcx, [rbp+57h+var_90]
0x1400cbf6a  call    cs:__imp_AccelAcquireResourcesSync
0x1400cbf71  nop     dword ptr [rax+rax+00h]
0x1400cbf76  mov     ebx, eax
0x1400cbf78  test    ebx, ebx
0x1400cbf7a  jns     short loc_1400CBFC7
0x1400cbf7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbf83  lea     rdx, WPP_GLOBAL_Control
0x1400cbf8a  cmp     rcx, rdx
0x1400cbf8d  jz      loc_1400CC10B
0x1400cbf93  test    dword ptr [rcx+2Ch], 400000h
0x1400cbf9a  jz      loc_1400CC10B
0x1400cbfa0  cmp     byte ptr [rcx+29h], 2
0x1400cbfa4  jb      loc_1400CC10B
0x1400cbfaa  mov     edx, 18h
0x1400cbfaf  mov     rcx, [rcx+18h]
0x1400cbfb3  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cbfba  mov     r9d, ebx
0x1400cbfbd  call    WPP_SF_d
0x1400cbfc2  jmp     loc_1400CC10B
0x1400cbfc7  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1400cbfcb  test    dword ptr [rdi+25D0h], 800000h
0x1400cbfd5  mov     r14, [rcx]
0x1400cbfd8  jz      short loc_1400CBFDE
0x1400cbfda  mov     ebx, esi
0x1400cbfdc  jmp     short loc_1400CC034
0x1400cbfde  lea     rdx, [rbp+57h+arg_0]
0x1400cbfe2  mov     rcx, r14
0x1400cbfe5  call    cs:__imp_AccelQueryDescriptorSize
0x1400cbfec  nop     dword ptr [rax+rax+00h]
0x1400cbff1  mov     ebx, eax
0x1400cbff3  test    eax, eax
0x1400cbff5  jns     short loc_1400CC02C
0x1400cbff7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbffe  lea     rax, WPP_GLOBAL_Control
0x1400cc005  cmp     rcx, rax
0x1400cc008  jz      loc_1400CC10B
0x1400cc00e  test    dword ptr [rcx+2Ch], 400000h
0x1400cc015  jz      loc_1400CC10B
0x1400cc01b  cmp     byte ptr [rcx+29h], 2
0x1400cc01f  jb      loc_1400CC10B
0x1400cc025  mov     edx, 19h
0x1400cc02a  jmp     short loc_1400CBFAF
0x1400cc02c  mov     eax, dword ptr [rbp+57h+arg_0]
0x1400cc02f  cmp     eax, 8
0x1400cc032  ja      short loc_1400CC039
0x1400cc034  mov     eax, 8
0x1400cc039  mov     dword ptr [rbp+57h+arg_0], eax
0x1400cc03c  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400cc043  nop     dword ptr [rax+rax+00h]
0x1400cc048  mov     r8d, eax
0x1400cc04b  dec     eax
0x1400cc04d  test    r8d, eax
0x1400cc050  jnz     short loc_1400CC068
0x1400cc052  test    r8d, r8d
0x1400cc055  jz      short loc_1400CC068
0x1400cc057  mov     r9d, dword ptr [rbp+57h+arg_0]
0x1400cc05b  not     eax
0x1400cc05d  dec     r9d
0x1400cc060  add     r9d, r8d
0x1400cc063  and     r9d, eax
0x1400cc066  jmp     short loc_1400CC07E
0x1400cc068  mov     r9d, dword ptr [rbp+57h+arg_0]
0x1400cc06c  xor     edx, edx
0x1400cc06e  mov     eax, r9d
0x1400cc071  div     r8d
0x1400cc074  test    edx, edx
0x1400cc076  jz      short loc_1400CC07E
0x1400cc078  sub     r8d, edx
0x1400cc07b  add     r9d, r8d
0x1400cc07e  mov     edx, 80h
0x1400cc083  mov     dword ptr [rbp+57h+arg_0], r9d
0x1400cc087  mov     r8d, 30455646h
0x1400cc08d  lea     ecx, [rdx-40h]
0x1400cc090  call    cs:__imp_ExAllocatePool2
0x1400cc097  nop     dword ptr [rax+rax+00h]
0x1400cc09c  mov     rsi, rax
0x1400cc09f  test    rax, rax
0x1400cc0a2  jnz     short loc_1400CC0AB
0x1400cc0a4  mov     ebx, 0C000009Ah
0x1400cc0a9  jmp     short loc_1400CC109
0x1400cc0ab  mov     ecx, dword ptr [rbp+57h+arg_0]
0x1400cc0ae  xor     eax, eax
0x1400cc0b0  mov     [rsp+110h+Depth], ax; Depth
0x1400cc0b5  mov     r9d, 200h; Flags
0x1400cc0bb  mov     [rsp+110h+Tag], 30455646h; Tag
0x1400cc0c3  xor     r8d, r8d; Free
0x1400cc0c6  mov     [rsp+110h+Size], rcx; Size
0x1400cc0cb  xor     edx, edx; Allocate
0x1400cc0cd  mov     rcx, rsi; Lookaside
0x1400cc0d0  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400cc0d7  nop     dword ptr [rax+rax+00h]
0x1400cc0dc  mov     rax, [rbp+57h+arg_8]
0x1400cc0e0  mov     [rdi+28E0h], rax
0x1400cc0e7  mov     eax, dword ptr [rbp+57h+arg_0]
0x1400cc0ea  mov     [rdi+28E8h], r14
0x1400cc0f1  xor     r14d, r14d
0x1400cc0f4  mov     [rdi+28F0h], eax
0x1400cc0fa  mov     [rbp+57h+arg_8], 0
0x1400cc102  mov     [rdi+28D8h], rsi
0x1400cc109  xor     esi, esi
0x1400cc10b  test    r12b, r12b
0x1400cc10e  jz      short loc_1400CC144
0x1400cc110  lea     rax, FVE_HW_ACCEL_CRYPTO_INITIALIZED_FAILED
0x1400cc117  mov     [rsp+110h+var_D8], esi
0x1400cc11b  test    ebx, ebx
0x1400cc11d  mov     dword ptr [rsp+110h+Depth], esi
0x1400cc121  lea     r8, FVE_HW_ACCEL_CRYPTO_INITIALIZED
0x1400cc128  mov     [rsp+110h+Tag], esi
0x1400cc12c  cmovs   r8, rax
0x1400cc130  mov     r9d, ebx
0x1400cc133  mov     eax, dword ptr [rbp+57h+arg_0]
0x1400cc136  xor     edx, edx
0x1400cc138  mov     rcx, rdi
0x1400cc13b  mov     dword ptr [rsp+110h+Size], eax
0x1400cc13f  call    FveLogStatusEventWithData
0x1400cc144  lea     rdi, WPP_GLOBAL_Control
0x1400cc14b  mov     rcx, r13; Resource
0x1400cc14e  call    cs:__imp_ExReleaseResourceLite
0x1400cc155  nop     dword ptr [rax+rax+00h]
0x1400cc15a  call    cs:__imp_KeLeaveCriticalRegion
0x1400cc161  nop     dword ptr [rax+rax+00h]
0x1400cc166  test    r14, r14
0x1400cc169  jz      short loc_1400CC17A
0x1400cc16b  mov     rcx, r14
0x1400cc16e  call    cs:__imp_AccelCloseResource
0x1400cc175  nop     dword ptr [rax+rax+00h]
0x1400cc17a  mov     rcx, [rbp+57h+arg_8]
0x1400cc17e  test    rcx, rcx
0x1400cc181  jz      short loc_1400CC18F
0x1400cc183  call    cs:__imp_AccelDestroyOffloadWorkspace
0x1400cc18a  nop     dword ptr [rax+rax+00h]
0x1400cc18f  test    r15, r15
0x1400cc192  jz      short loc_1400CC1A8
0x1400cc194  mov     edx, 30455646h; Tag
0x1400cc199  mov     rcx, r15; P
0x1400cc19c  call    cs:__imp_ExFreePoolWithTag
0x1400cc1a3  nop     dword ptr [rax+rax+00h]
0x1400cc1a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc1af  cmp     rcx, rdi
0x1400cc1b2  jz      short loc_1400CC1DB
0x1400cc1b4  test    dword ptr [rcx+2Ch], 400000h
0x1400cc1bb  jz      short loc_1400CC1DB
0x1400cc1bd  cmp     byte ptr [rcx+29h], 5
0x1400cc1c1  jb      short loc_1400CC1DB
  ... truncated ...
```
