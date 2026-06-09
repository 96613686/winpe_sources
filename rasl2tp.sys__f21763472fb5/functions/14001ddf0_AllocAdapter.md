# AllocAdapter

- ea: `0x14001ddf0`
- end: `0x14001e3b7`
- name: `AllocAdapter`
- size: `1479`
- prototype: `__int64 __fastcall(NDIS_HANDLE NdisHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14001d600`

## callees

- `0x140001b70`
- `0x140003050`
- `0x140003080`
- `0x1400047f0`
- `0x14001d39c`
- `0x14001dcb4`
- `0x14001ddf0`
- `0x14001e3c0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e04f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e093`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e0d7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e11b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e15f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e1a3`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e1e7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e04f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e093`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e0d7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e11b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e15f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e1a3`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001e1e7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001ded7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001deea`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001e312`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001ded7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001deea`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001e312`
- `NDIS!NdisGetVersion` at `0x14001e01a`
- `NDIS!NdisGetVersion` at `0x14001e05f`
- `NDIS!NdisGetVersion` at `0x14001e0a3`
- `NDIS!NdisGetVersion` at `0x14001e0e7`
- `NDIS!NdisGetVersion` at `0x14001e12b`
- `NDIS!NdisGetVersion` at `0x14001e16f`
- `NDIS!NdisGetVersion` at `0x14001e1b3`
- `NDIS!NdisGetVersion` at `0x14001e01a`
- `NDIS!NdisGetVersion` at `0x14001e05f`
- `NDIS!NdisGetVersion` at `0x14001e0a3`
- `NDIS!NdisGetVersion` at `0x14001e0e7`
- `NDIS!NdisGetVersion` at `0x14001e12b`
- `NDIS!NdisGetVersion` at `0x14001e16f`
- `NDIS!NdisGetVersion` at `0x14001e1b3`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14001e22a`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14001e283`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14001e22a`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14001e283`

## pseudocode

```c
__int64 __fastcall AllocAdapter(NDIS_HANDLE NdisHandle)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  NDIS_STATUS RegistrySettings; // edi
  KSPIN_LOCK *v5; // rcx
  _QWORD *v6; // rax
  void *v7; // rcx
  USHORT Depth; // di
  USHORT v9; // di
  USHORT v10; // di
  USHORT v11; // di
  USHORT v12; // di
  USHORT v13; // di
  NDIS_HANDLE v14; // rax
  NDIS_HANDLE v15; // rax
  __int64 v16; // rax
  int v17; // eax
  USHORT v19[2]; // [rsp+B8h] [rbp+7h] BYREF
  bool v20; // [rsp+BCh] [rbp+Bh] BYREF
  bool v21; // [rsp+BDh] [rbp+Ch] BYREF
  bool v22; // [rsp+BEh] [rbp+Dh] BYREF
  ULONG v23; // [rsp+C0h] [rbp+Fh] BYREF
  ULONG v24; // [rsp+C4h] [rbp+13h] BYREF
  ULONG v25; // [rsp+C8h] [rbp+17h] BYREF
  _NET_BUFFER_LIST_POOL_PARAMETERS Parameters; // [rsp+D0h] [rbp+1Fh] BYREF

  v25 = 0;
  v23 = 0;
  v19[0] = 0;
  v21 = 0;
  v22 = 0;
  v24 = 0;
  v20 = 0;
  Parameters = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids);
  }
  v2 = ALLOC_NONPAGED(1344, 827601484);
  v3 = v2;
  if ( !v2 )
  {
    RegistrySettings = -1073741670;
LABEL_26:
    v3 = 0;
    goto LABEL_27;
  }
  *(_DWORD *)v2 = 827601484;
  v5 = (KSPIN_LOCK *)(v2 + 144);
  *(_QWORD *)(v2 + 328) = NdisHandle;
  v6 = (_QWORD *)(v2 + 128);
  v6[1] = v6;
  *v6 = v6;
  KeInitializeSpinLock(v5);
  KeInitializeSpinLock((PKSPIN_LOCK)(v3 + 192));
  v7 = *(void **)(v3 + 328);
  *(_OWORD *)(v3 + 360) = xmmword_14000A108;
  *(_DWORD *)(v3 + 360) = 1400;
  RegistrySettings = GetRegistrySettings(
                       v7,
                       (_WORD *)(v3 + 96),
                       &v25,
                       &v23,
                       (ULONG *)(v3 + 24),
                       (ULONG *)(v3 + 28),
                       (ULONG *)(v3 + 36),
                       (ULONG *)(v3 + 20),
                       (ULONG *)(v3 + 32),
                       (USHORT *)(v3 + 12),
                       (USHORT *)(v3 + 14),
                       (USHORT *)(v3 + 16),
                       (ULONG *)(v3 + 364),
                       v19,
                       (__int64 *)(v3 + 72),
                       (__int64 *)(v3 + 48),
                       &v21,
                       &v22,
                       &v24,
                       &v20,
                       (__int64 *)(v3 + 56));
  if ( RegistrySettings )
  {
    *(_WORD *)(v3 + 96) = 0;
LABEL_25:
    FreeAdapter(v3);
    goto LABEL_26;
  }
  if ( v23 == 2 )
    *(_DWORD *)(v3 + 8) |= 1u;
  if ( v21 )
    *(_DWORD *)(v3 + 8) |= 2u;
  if ( v22 )
    *(_DWORD *)(v3 + 8) |= 4u;
  *(_QWORD *)(v3 + 64) = 1;
  v19[0] = 0;
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 448), 0, 0, 0x200u, 0x50u, 0x3554324Cu, 0);
  Depth = v19[0];
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 576), 0, 0, 0x200u, 0x28u, 0x3754324Cu, Depth);
  v9 = v19[0];
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 704), 0, 0, 0x200u, 0x50u, 0x6554324Cu, v9);
  v10 = v19[0];
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 832), 0, 0, 0x200u, 0x60u, 0x6754324Cu, v10);
  v11 = v19[0];
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 960), 0, 0, 0x200u, 0x40u, 0x6D54324Cu, v11);
  v12 = v19[0];
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 1088), 0, 0, 0x200u, 0x140u, 0x6F54324Cu, v12);
  v13 = v19[0];
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 1216), 0, 0, 0x200u, 0x50u, 0x7554324Cu, v13);
  Parameters.Header = (NDIS_OBJECT_HEADER)1048960;
  Parameters.fAllocateNetBuffer = 1;
  *(_WORD *)(v3 + 220) = 0;
  Parameters.ContextSize = 0;
  Parameters.PoolTag = 945041996;
  *(_DWORD *)(v3 + 216) = 1554;
  Parameters.DataSize = 1554;
  v14 = NdisAllocateNetBufferListPool(NdisHandle, &Parameters);
  *(_QWORD *)(v3 + 208) = v14;
  if ( !v14 )
  {
    RegistrySettings = -1073741670;
    goto LABEL_25;
  }
  Parameters.Header = (NDIS_OBJECT_HEADER)1048960;
  Parameters.fAllocateNetBuffer = 1;
  *(_WORD *)(v3 + 236) = 0;
  Parameters.ContextSize = 0;
  Parameters.PoolTag = 961819212;
  *(_DWORD *)(v3 + 232) = 42;
  Parameters.DataSize = 42;
  v15 = NdisAllocateNetBufferListPool(NdisHandle, &Parameters);
  *(_QWORD *)(v3 + 224) = v15;
  if ( !v15 )
  {
    RegistrySettings = -1073741670;
    goto LABEL_25;
  }
  RegistrySettings = WskInitialize(v20 ? 2 : 0, v3 + 208, v3 + 240);
  if ( RegistrySettings >= 0 )
  {
    RegistrySettings = WskInitialize(v20 ? 2 : 0, v3 + 208, v3 + 280);
    if ( RegistrySettings >= 0 )
    {
      v16 = ALLOC_NONPAGED(8 * (unsigned int)*(unsigned __int16 *)(v3 + 96), 877933132);
      *(_QWORD *)(v3 + 88) = v16;
      if ( !v16 )
      {
        RegistrySettings = -1073741670;
        goto LABEL_25;
      }
      KeInitializeSpinLock((PKSPIN_LOCK)(v3 + 104));
      v17 = *(unsigned __int16 *)(v3 + 96);
      *(_DWORD *)(v3 + 100) = v17;
      *(_WORD *)(v3 + 120) = v17 + 1;
    }
  }
  if ( RegistrySettings )
    goto LABEL_25;
LABEL_27:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids,
      (unsigned int)RegistrySettings);
  }
  return v3;
}

```

## disassembly

```asm
0x14001ddf0  mov     r11, rsp
0x14001ddf3  push    rbp
0x14001ddf4  push    rbx
0x14001ddf5  lea     rbp, [r11-5Fh]
0x14001ddf9  sub     rsp, 0F8h
0x14001de00  mov     rax, cs:__security_cookie
0x14001de07  xor     rax, rsp
0x14001de0a  mov     [rbp+57h+var_28], rax
0x14001de0e  mov     [r11-18h], r13
0x14001de12  xorps   xmm0, xmm0
0x14001de15  mov     [r11-28h], r15
0x14001de19  mov     r13, rcx
0x14001de1c  xor     r15d, r15d
0x14001de1f  mov     [rbp+57h+var_40], r15d
0x14001de23  mov     [rbp+57h+var_48], r15d
0x14001de27  mov     [rbp+57h+var_50], r15w
0x14001de2c  mov     [rbp+57h+var_4B], r15b
0x14001de30  mov     [rbp+57h+var_4A], r15b
0x14001de34  mov     [rbp+57h+var_44], r15d
0x14001de38  mov     [rbp+57h+var_4C], r15b
0x14001de3c  movups  xmmword ptr [rbp+57h+Parameters.Header.Type], xmm0
0x14001de40  mov     rcx, cs:WPP_GLOBAL_Control
0x14001de47  lea     rax, WPP_GLOBAL_Control
0x14001de4e  cmp     rcx, rax
0x14001de51  jz      short loc_14001DE77
0x14001de53  test    dword ptr [rcx+2Ch], 200h
0x14001de5a  jz      short loc_14001DE77
0x14001de5c  cmp     byte ptr [rcx+29h], 4
0x14001de60  jb      short loc_14001DE77
0x14001de62  mov     rcx, [rcx+18h]
0x14001de66  lea     r8, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids
0x14001de6d  mov     edx, 25h ; '%'
0x14001de72  call    WPP_SF_
0x14001de77  mov     [rsp+100h+arg_8], rsi
0x14001de7f  mov     edx, 3154324Ch
0x14001de84  mov     [rsp+100h+arg_10], rdi
0x14001de8c  mov     ecx, 540h
0x14001de91  mov     [rsp+100h+var_18], r14
0x14001de99  call    ALLOC_NONPAGED
0x14001de9e  mov     rbx, rax
0x14001dea1  test    rax, rax
0x14001dea4  jnz     short loc_14001DEB0
0x14001dea6  mov     edi, 0C000009Ah
0x14001deab  jmp     loc_14001E338
0x14001deb0  mov     dword ptr [rax], 3154324Ch
0x14001deb6  lea     rcx, [rbx+90h]; SpinLock
0x14001debd  mov     [rax+148h], r13
0x14001dec4  sub     rax, 0FFFFFFFFFFFFFF80h
0x14001dec8  mov     [rsp+100h+arg_18], r12
0x14001ded0  mov     [rax+8], rax
0x14001ded4  mov     [rax], rax
0x14001ded7  call    cs:__imp_KeInitializeSpinLock
0x14001dede  nop     dword ptr [rax+rax+00h]
0x14001dee3  lea     rcx, [rbx+0C0h]; SpinLock
0x14001deea  call    cs:__imp_KeInitializeSpinLock
0x14001def1  nop     dword ptr [rax+rax+00h]
0x14001def6  movups  xmm0, cs:xmmword_14000A108
0x14001defd  lea     rax, [rbx+38h]
0x14001df01  mov     [rsp+0A0h], rax
0x14001df09  lea     rcx, [rbx+30h]
0x14001df0d  lea     rax, [rbp+57h+var_4C]
0x14001df11  mov     [rsp+100h+var_68], rax
0x14001df19  lea     rdx, [rbx+48h]
0x14001df1d  lea     rax, [rbp+57h+var_44]
0x14001df21  mov     [rsp+100h+var_70], rax
0x14001df29  lea     r8, [rbx+16Ch]
0x14001df30  lea     rax, [rbp+57h+var_4A]
0x14001df34  mov     [rsp+100h+var_78], rax
0x14001df3c  lea     r9, [rbx+10h]
0x14001df40  lea     rax, [rbp+57h+var_4B]
0x14001df44  mov     [rsp+100h+var_80], rax
0x14001df4c  lea     r10, [rbx+0Eh]
0x14001df50  mov     [rsp+100h+var_88], rcx
0x14001df55  lea     rax, [rbp+57h+var_50]
0x14001df59  mov     rcx, [rbx+148h]
0x14001df60  lea     r11, [rbx+0Ch]
0x14001df64  mov     [rsp+100h+var_90], rdx
0x14001df69  lea     rdi, [rbx+20h]
0x14001df6d  mov     [rsp+100h+var_98], rax
0x14001df72  lea     rsi, [rbx+14h]
0x14001df76  mov     [rsp+100h+var_A0], r8
0x14001df7b  lea     r14, [rbx+24h]
0x14001df7f  mov     [rsp+100h+var_A8], r9
0x14001df84  lea     r15, [rbx+1Ch]
0x14001df88  mov     [rsp+100h+var_B0], r10
0x14001df8d  lea     r12, [rbx+18h]
0x14001df91  mov     [rsp+100h+var_B8], r11
0x14001df96  lea     r9, [rbp+57h+var_48]
0x14001df9a  mov     [rsp+100h+var_C0], rdi
0x14001df9f  lea     r8, [rbp+57h+var_40]
0x14001dfa3  mov     [rsp+100h+var_C8], rsi
0x14001dfa8  lea     rdx, [rbx+60h]
0x14001dfac  mov     qword ptr [rsp+100h+Depth], r14
0x14001dfb1  movups  xmmword ptr [rbx+168h], xmm0
0x14001dfb8  mov     qword ptr [rsp+100h+Tag], r15
0x14001dfbd  mov     [rsp+100h+Size], r12
0x14001dfc2  mov     dword ptr [rbx+168h], 578h
0x14001dfcc  call    GetRegistrySettings
0x14001dfd1  mov     r12, [rsp+100h+arg_18]
0x14001dfd9  mov     edi, eax
0x14001dfdb  test    eax, eax
0x14001dfdd  jz      short loc_14001DFEC
0x14001dfdf  xor     r15d, r15d
0x14001dfe2  mov     [rbx+60h], r15w
0x14001dfe7  jmp     loc_14001E330
0x14001dfec  cmp     [rbp+57h+var_48], 2
0x14001dff0  jnz     short loc_14001DFF6
0x14001dff2  or      dword ptr [rbx+8], 1
0x14001dff6  cmp     [rbp+57h+var_4B], 0
0x14001dffa  jz      short loc_14001E000
0x14001dffc  or      dword ptr [rbx+8], 2
0x14001e000  cmp     [rbp+57h+var_4A], 0
0x14001e004  jz      short loc_14001E00A
0x14001e006  or      dword ptr [rbx+8], 4
0x14001e00a  mov     qword ptr [rbx+40h], 1
0x14001e012  xor     r15d, r15d
0x14001e015  mov     [rbp+57h+var_50], r15w
0x14001e01a  call    cs:__imp_NdisGetVersion
0x14001e021  nop     dword ptr [rax+rax+00h]
0x14001e026  mov     [rsp+100h+Depth], r15w; Depth
0x14001e02c  lea     rcx, [rbx+1C0h]; Lookaside
0x14001e033  mov     [rsp+100h+Tag], 3554324Ch; Tag
0x14001e03b  mov     r9d, 200h; Flags
0x14001e041  xor     r8d, r8d; Free
0x14001e044  mov     [rsp+100h+Size], 50h ; 'P'; Size
0x14001e04d  xor     edx, edx; Allocate
0x14001e04f  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001e056  nop     dword ptr [rax+rax+00h]
0x14001e05b  movzx   edi, [rbp+57h+var_50]
0x14001e05f  call    cs:__imp_NdisGetVersion
0x14001e066  nop     dword ptr [rax+rax+00h]
0x14001e06b  mov     [rsp+100h+Depth], di; Depth
0x14001e070  lea     rcx, [rbx+240h]; Lookaside
0x14001e077  mov     [rsp+100h+Tag], 3754324Ch; Tag
0x14001e07f  mov     r9d, 200h; Flags
0x14001e085  xor     r8d, r8d; Free
0x14001e088  mov     [rsp+100h+Size], 28h ; '('; Size
0x14001e091  xor     edx, edx; Allocate
0x14001e093  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001e09a  nop     dword ptr [rax+rax+00h]
0x14001e09f  movzx   edi, [rbp+57h+var_50]
0x14001e0a3  call    cs:__imp_NdisGetVersion
0x14001e0aa  nop     dword ptr [rax+rax+00h]
0x14001e0af  mov     [rsp+100h+Depth], di; Depth
0x14001e0b4  lea     rcx, [rbx+2C0h]; Lookaside
0x14001e0bb  mov     [rsp+100h+Tag], 6554324Ch; Tag
0x14001e0c3  mov     r9d, 200h; Flags
0x14001e0c9  xor     r8d, r8d; Free
0x14001e0cc  mov     [rsp+100h+Size], 50h ; 'P'; Size
0x14001e0d5  xor     edx, edx; Allocate
0x14001e0d7  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001e0de  nop     dword ptr [rax+rax+00h]
0x14001e0e3  movzx   edi, [rbp+57h+var_50]
0x14001e0e7  call    cs:__imp_NdisGetVersion
0x14001e0ee  nop     dword ptr [rax+rax+00h]
0x14001e0f3  mov     [rsp+100h+Depth], di; Depth
0x14001e0f8  lea     rcx, [rbx+340h]; Lookaside
0x14001e0ff  mov     [rsp+100h+Tag], 6754324Ch; Tag
0x14001e107  mov     r9d, 200h; Flags
0x14001e10d  xor     r8d, r8d; Free
0x14001e110  mov     [rsp+100h+Size], 60h ; '`'; Size
0x14001e119  xor     edx, edx; Allocate
0x14001e11b  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001e122  nop     dword ptr [rax+rax+00h]
0x14001e127  movzx   edi, [rbp+57h+var_50]
0x14001e12b  call    cs:__imp_NdisGetVersion
0x14001e132  nop     dword ptr [rax+rax+00h]
0x14001e137  mov     [rsp+100h+Depth], di; Depth
0x14001e13c  lea     rcx, [rbx+3C0h]; Lookaside
0x14001e143  mov     [rsp+100h+Tag], 6D54324Ch; Tag
0x14001e14b  mov     r9d, 200h; Flags
0x14001e151  xor     r8d, r8d; Free
0x14001e154  mov     [rsp+100h+Size], 40h ; '@'; Size
0x14001e15d  xor     edx, edx; Allocate
0x14001e15f  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001e166  nop     dword ptr [rax+rax+00h]
0x14001e16b  movzx   edi, [rbp+57h+var_50]
0x14001e16f  call    cs:__imp_NdisGetVersion
0x14001e176  nop     dword ptr [rax+rax+00h]
0x14001e17b  mov     [rsp+100h+Depth], di; Depth
0x14001e180  lea     rcx, [rbx+440h]; Lookaside
0x14001e187  mov     [rsp+100h+Tag], 6F54324Ch; Tag
0x14001e18f  mov     r9d, 200h; Flags
0x14001e195  xor     r8d, r8d; Free
0x14001e198  mov     [rsp+100h+Size], 140h; Size
0x14001e1a1  xor     edx, edx; Allocate
0x14001e1a3  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001e1aa  nop     dword ptr [rax+rax+00h]
0x14001e1af  movzx   edi, [rbp+57h+var_50]
0x14001e1b3  call    cs:__imp_NdisGetVersion
0x14001e1ba  nop     dword ptr [rax+rax+00h]
0x14001e1bf  mov     [rsp+100h+Depth], di; Depth
0x14001e1c4  lea     rcx, [rbx+4C0h]; Lookaside
0x14001e1cb  mov     [rsp+100h+Tag], 7554324Ch; Tag
0x14001e1d3  mov     r9d, 200h; Flags
0x14001e1d9  xor     r8d, r8d; Free
0x14001e1dc  mov     [rsp+100h+Size], 50h ; 'P'; Size
0x14001e1e5  xor     edx, edx; Allocate
0x14001e1e7  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001e1ee  nop     dword ptr [rax+rax+00h]
0x14001e1f3  mov     dword ptr [rbp+57h+Parameters.Header.Type], 100180h
0x14001e1fa  lea     rdx, [rbp+57h+Parameters]; Parameters
0x14001e1fe  mov     [rbp+57h+Parameters.fAllocateNetBuffer], 1
0x14001e202  mov     rcx, r13; NdisHandle
0x14001e205  mov     [rbx+0DCh], r15w
0x14001e20d  mov     [rbp+57h+Parameters.ContextSize], r15w
0x14001e212  mov     [rbp+57h+Parameters.PoolTag], 3854324Ch
0x14001e219  mov     dword ptr [rbx+0D8h], 612h
0x14001e223  mov     [rbp+57h+Parameters.DataSize], 612h
0x14001e22a  call    cs:__imp_NdisAllocateNetBufferListPool
0x14001e231  nop     dword ptr [rax+rax+00h]
0x14001e236  mov     [rbx+0D0h], rax
0x14001e23d  test    rax, rax
0x14001e240  jnz     short loc_14001E24C
0x14001e242  mov     edi, 0C000009Ah
0x14001e247  jmp     loc_14001E330
0x14001e24c  mov     dword ptr [rbp+57h+Parameters.Header.Type], 100180h
0x14001e253  lea     rdx, [rbp+57h+Parameters]; Parameters
0x14001e257  mov     [rbp+57h+Parameters.fAllocateNetBuffer], 1
0x14001e25b  mov     rcx, r13; NdisHandle
0x14001e25e  mov     [rbx+0ECh], r15w
0x14001e266  mov     [rbp+57h+Parameters.ContextSize], r15w
0x14001e26b  mov     [rbp+57h+Parameters.PoolTag], 3954324Ch
0x14001e272  mov     dword ptr [rbx+0E8h], 2Ah ; '*'
0x14001e27c  mov     [rbp+57h+Parameters.DataSize], 2Ah ; '*'
0x14001e283  call    cs:__imp_NdisAllocateNetBufferListPool
0x14001e28a  nop     dword ptr [rax+rax+00h]
0x14001e28f  mov     [rbx+0E0h], rax
0x14001e296  test    rax, rax
0x14001e299  jnz     short loc_14001E2A5
0x14001e29b  mov     edi, 0C000009Ah
0x14001e2a0  jmp     loc_14001E330
0x14001e2a5  movzx   eax, [rbp+57h+var_4C]
0x14001e2a9  lea     r8, [rbx+0F0h]
0x14001e2b0  neg     al
0x14001e2b2  lea     rdx, [rbx+0D0h]
0x14001e2b9  sbb     ecx, ecx
0x14001e2bb  and     ecx, 2
0x14001e2be  call    WskInitialize
0x14001e2c3  mov     edi, eax
0x14001e2c5  test    eax, eax
0x14001e2c7  js      short loc_14001E32C
0x14001e2c9  movzx   eax, [rbp+57h+var_4C]
0x14001e2cd  lea     r8, [rbx+118h]
0x14001e2d4  neg     al
0x14001e2d6  lea     rdx, [rbx+0D0h]
0x14001e2dd  sbb     ecx, ecx
0x14001e2df  and     ecx, 2
0x14001e2e2  call    WskInitialize
0x14001e2e7  mov     edi, eax
0x14001e2e9  test    eax, eax
0x14001e2eb  js      short loc_14001E32C
0x14001e2ed  movzx   ecx, word ptr [rbx+60h]
0x14001e2f1  mov     edx, 3454324Ch
0x14001e2f6  shl     ecx, 3
0x14001e2f9  call    ALLOC_NONPAGED
0x14001e2fe  mov     [rbx+58h], rax
0x14001e302  test    rax, rax
0x14001e305  jnz     short loc_14001E30E
0x14001e307  mov     edi, 0C000009Ah
0x14001e30c  jmp     short loc_14001E330
0x14001e30e  lea     rcx, [rbx+68h]; SpinLock
0x14001e312  call    cs:__imp_KeInitializeSpinLock
0x14001e319  nop     dword ptr [rax+rax+00h]
0x14001e31e  movzx   eax, word ptr [rbx+60h]
0x14001e322  mov     [rbx+64h], eax
0x14001e325  inc     ax
0x14001e328  mov     [rbx+78h], ax
0x14001e32c  test    edi, edi
0x14001e32e  jz      short loc_14001E33B
0x14001e330  mov     rcx, rbx
0x14001e333  call    FreeAdapter
0x14001e338  mov     rbx, r15
0x14001e33b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e342  lea     rax, WPP_GLOBAL_Control
0x14001e349  mov     r15, [rsp+100h+var_20]
0x14001e351  mov     r14, [rsp+100h+var_18]
0x14001e359  mov     r13, [rsp+0F0h]
0x14001e361  mov     rsi, [rsp+100h+arg_8]
0x14001e369  cmp     rcx, rax
0x14001e36c  jz      short loc_14001E395
0x14001e36e  test    dword ptr [rcx+2Ch], 200h
0x14001e375  jz      short loc_14001E395
0x14001e377  cmp     byte ptr [rcx+29h], 4
0x14001e37b  jb      short loc_14001E395
0x14001e37d  mov     rcx, [rcx+18h]
0x14001e381  lea     r8, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids
0x14001e388  mov     edx, 26h ; '&'
0x14001e38d  mov     r9d, edi
0x14001e390  call    WPP_SF_d
0x14001e395  mov     rdi, [rsp+100h+arg_10]
0x14001e39d  mov     rax, rbx
0x14001e3a0  mov     rcx, [rbp+57h+var_28]
0x14001e3a4  xor     rcx, rsp; StackCookie
0x14001e3a7  call    __security_check_cookie
0x14001e3ac  add     rsp, 0F8h
0x14001e3b3  pop     rbx
0x14001e3b4  pop     rbp
0x14001e3b5  retn
```
