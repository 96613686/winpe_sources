# ACDeepProbeReceiveParams(_DEVICE_OBJECT *,CACReceiveParameters *,ACReceiveParametersPointerContents *)

- ea: `0x140023b00`
- end: `0x1400242ab`
- name: `?ACDeepProbeReceiveParams@@YAXPEAU_DEVICE_OBJECT@@PEAVCACReceiveParameters@@PEAUACReceiveParametersPointerContents@@@Z`
- size: `1963`
- prototype: `void __fastcall(struct _DEVICE_OBJECT *, struct CACReceiveParameters *, struct ACReceiveParametersPointerContents *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140015e04`

## callees

- `0x140001c04`
- `0x14000770c`
- `0x140021b5c`
- `0x140023b00`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140023da3`
- `ntoskrnl!ProbeForRead` at `0x140023dc1`
- `ntoskrnl!ProbeForRead` at `0x140023ddf`
- `ntoskrnl!ProbeForRead` at `0x140023dfd`
- `ntoskrnl!ProbeForRead` at `0x140023e1b`
- `ntoskrnl!ProbeForRead` at `0x140023e39`
- `ntoskrnl!ProbeForRead` at `0x140023e57`
- `ntoskrnl!ProbeForRead` at `0x140023e75`
- `ntoskrnl!ProbeForRead` at `0x140023e93`
- `ntoskrnl!ProbeForRead` at `0x140023eb1`
- `ntoskrnl!ProbeForRead` at `0x140023da3`
- `ntoskrnl!ProbeForRead` at `0x140023dc1`
- `ntoskrnl!ProbeForRead` at `0x140023ddf`
- `ntoskrnl!ProbeForRead` at `0x140023dfd`
- `ntoskrnl!ProbeForRead` at `0x140023e1b`
- `ntoskrnl!ProbeForRead` at `0x140023e39`
- `ntoskrnl!ProbeForRead` at `0x140023e57`
- `ntoskrnl!ProbeForRead` at `0x140023e75`
- `ntoskrnl!ProbeForRead` at `0x140023e93`
- `ntoskrnl!ProbeForRead` at `0x140023eb1`
- `ntoskrnl!ProbeForWrite` at `0x140023b36`
- `ntoskrnl!ProbeForWrite` at `0x140023b63`
- `ntoskrnl!ProbeForWrite` at `0x140023b90`
- `ntoskrnl!ProbeForWrite` at `0x140023bbd`
- `ntoskrnl!ProbeForWrite` at `0x140023bea`
- `ntoskrnl!ProbeForWrite` at `0x140023c17`
- `ntoskrnl!ProbeForWrite` at `0x140023c44`
- `ntoskrnl!ProbeForWrite` at `0x140023c71`
- `ntoskrnl!ProbeForWrite` at `0x140023c9e`
- `ntoskrnl!ProbeForWrite` at `0x140023ccb`
- `ntoskrnl!ProbeForWrite` at `0x140023cf8`
- `ntoskrnl!ProbeForWrite` at `0x140023d16`
- `ntoskrnl!ProbeForWrite` at `0x140023d34`
- `ntoskrnl!ProbeForWrite` at `0x140023d52`
- `ntoskrnl!ProbeForWrite` at `0x140023d70`
- `ntoskrnl!ProbeForWrite` at `0x140023b36`
- `ntoskrnl!ProbeForWrite` at `0x140023b63`
- `ntoskrnl!ProbeForWrite` at `0x140023b90`
- `ntoskrnl!ProbeForWrite` at `0x140023bbd`
- `ntoskrnl!ProbeForWrite` at `0x140023bea`
- `ntoskrnl!ProbeForWrite` at `0x140023c17`
- `ntoskrnl!ProbeForWrite` at `0x140023c44`
- `ntoskrnl!ProbeForWrite` at `0x140023c71`
- `ntoskrnl!ProbeForWrite` at `0x140023c9e`
- `ntoskrnl!ProbeForWrite` at `0x140023ccb`
- `ntoskrnl!ProbeForWrite` at `0x140023cf8`
- `ntoskrnl!ProbeForWrite` at `0x140023d16`
- `ntoskrnl!ProbeForWrite` at `0x140023d34`
- `ntoskrnl!ProbeForWrite` at `0x140023d52`
- `ntoskrnl!ProbeForWrite` at `0x140023d70`
- `ntoskrnl!ExRaiseStatus` at `0x140024282`
- `ntoskrnl!ExRaiseStatus` at `0x140024282`

## pseudocode

```c
void __fastcall ACDeepProbeReceiveParams(
        struct _DEVICE_OBJECT *a1,
        struct CACReceiveParameters *a2,
        struct ACReceiveParametersPointerContents *a3)
{
  unsigned int v6; // edx
  volatile void *v7; // rcx
  volatile void *v8; // rcx
  volatile void *v9; // rcx
  volatile void *v10; // rcx
  volatile void *v11; // rcx
  volatile void *v12; // rcx
  volatile void *v13; // rcx
  volatile void *v14; // rcx
  volatile void *v15; // rcx
  volatile void *v16; // rcx
  volatile void *v17; // rcx
  volatile void *v18; // rcx
  volatile void *v19; // rcx
  volatile void *v20; // rcx
  volatile void *v21; // rcx
  volatile void *v22; // rcx
  volatile void *v23; // rcx
  volatile void *v24; // rcx
  volatile void *v25; // rcx
  volatile void *v26; // rcx
  volatile void *v27; // rcx
  volatile void *v28; // rcx
  volatile void *v29; // rcx
  volatile void *v30; // rcx
  volatile void *v31; // rcx
  void **v32; // rsi
  void *v33; // rsi
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  void **v36; // rsi
  void *v37; // rsi
  void **v38; // rsi
  void *v39; // rsi
  void **v40; // rsi
  void *v41; // rsi
  void **v42; // rsi
  void *v43; // rsi
  void **v44; // rsi
  void *v45; // rsi
  void **v46; // rsi
  void *v47; // rsi
  void **v48; // rsi
  void *v49; // rsi
  void **v50; // rsi
  void *v51; // rsi
  void **v52; // rbx
  void *v53; // rbx
  unsigned int v54; // r8d

  ACDeepProbeMsgPropsForReceive(a1, a2, a3);
  v7 = (volatile void *)*((_QWORD *)a2 + 76);
  if ( v7 )
  {
    ProbeForWrite(v7, 4u, 1u);
    *((_DWORD *)a3 + 48) = **((_DWORD **)a2 + 76);
  }
  v8 = (volatile void *)*((_QWORD *)a2 + 78);
  if ( v8 )
  {
    ProbeForWrite(v8, 4u, 1u);
    *((_DWORD *)a3 + 52) = **((_DWORD **)a2 + 78);
  }
  v9 = (volatile void *)*((_QWORD *)a2 + 80);
  if ( v9 )
  {
    ProbeForWrite(v9, 4u, 1u);
    *((_DWORD *)a3 + 56) = **((_DWORD **)a2 + 80);
  }
  v10 = (volatile void *)*((_QWORD *)a2 + 82);
  if ( v10 )
  {
    ProbeForWrite(v10, 4u, 1u);
    *((_DWORD *)a3 + 60) = **((_DWORD **)a2 + 82);
  }
  v11 = (volatile void *)*((_QWORD *)a2 + 84);
  if ( v11 )
  {
    ProbeForWrite(v11, 4u, 1u);
    *((_DWORD *)a3 + 64) = **((_DWORD **)a2 + 84);
  }
  v12 = (volatile void *)*((_QWORD *)a2 + 86);
  if ( v12 )
  {
    ProbeForWrite(v12, 4u, 1u);
    *((_DWORD *)a3 + 68) = **((_DWORD **)a2 + 86);
  }
  v13 = (volatile void *)*((_QWORD *)a2 + 88);
  if ( v13 )
  {
    ProbeForWrite(v13, 4u, 1u);
    *((_DWORD *)a3 + 72) = **((_DWORD **)a2 + 88);
  }
  v14 = (volatile void *)*((_QWORD *)a2 + 91);
  if ( v14 )
  {
    ProbeForWrite(v14, 4u, 1u);
    *((_DWORD *)a3 + 76) = **((_DWORD **)a2 + 91);
  }
  v15 = (volatile void *)*((_QWORD *)a2 + 93);
  if ( v15 )
  {
    ProbeForWrite(v15, 4u, 1u);
    *((_DWORD *)a3 + 80) = **((_DWORD **)a2 + 93);
  }
  v16 = (volatile void *)*((_QWORD *)a2 + 97);
  if ( v16 )
  {
    ProbeForWrite(v16, 4u, 1u);
    *((_DWORD *)a3 + 84) = **((_DWORD **)a2 + 97);
  }
  v17 = (volatile void *)*((_QWORD *)a2 + 94);
  if ( v17 )
    ProbeForWrite(v17, 1u, 1u);
  v18 = (volatile void *)*((_QWORD *)a2 + 95);
  if ( v18 )
    ProbeForWrite(v18, 1u, 1u);
  v19 = (volatile void *)*((_QWORD *)a2 + 98);
  if ( v19 )
    ProbeForWrite(v19, 4u, 1u);
  v20 = (volatile void *)*((_QWORD *)a2 + 99);
  if ( v20 )
    ProbeForWrite(v20, 4u, 1u);
  v21 = (volatile void *)*((_QWORD *)a2 + 100);
  if ( v21 )
    ProbeForWrite(v21, 4u, 1u);
  if ( !*((_DWORD *)a1->DeviceExtension + 246) )
  {
    v22 = (volatile void *)*((_QWORD *)a2 + 75);
    if ( v22 )
      ProbeForRead(v22, 8u, 1u);
    v23 = (volatile void *)*((_QWORD *)a2 + 77);
    if ( v23 )
      ProbeForRead(v23, 8u, 1u);
    v24 = (volatile void *)*((_QWORD *)a2 + 79);
    if ( v24 )
      ProbeForRead(v24, 8u, 1u);
    v25 = (volatile void *)*((_QWORD *)a2 + 81);
    if ( v25 )
      ProbeForRead(v25, 8u, 1u);
    v26 = (volatile void *)*((_QWORD *)a2 + 83);
    if ( v26 )
      ProbeForRead(v26, 8u, 1u);
    v27 = (volatile void *)*((_QWORD *)a2 + 85);
    if ( v27 )
      ProbeForRead(v27, 8u, 1u);
    v28 = (volatile void *)*((_QWORD *)a2 + 87);
    if ( v28 )
      ProbeForRead(v28, 8u, 1u);
    v29 = (volatile void *)*((_QWORD *)a2 + 89);
    if ( v29 )
      ProbeForRead(v29, 8u, 1u);
    v30 = (volatile void *)*((_QWORD *)a2 + 92);
    if ( v30 )
      ProbeForRead(v30, 8u, 1u);
    v31 = (volatile void *)*((_QWORD *)a2 + 96);
    if ( v31 )
      ProbeForRead(v31, 8u, 1u);
  }
  v32 = (void **)*((_QWORD *)a2 + 75);
  if ( v32 )
  {
    v33 = *v32;
    if ( !v33 && *((_DWORD *)a3 + 48) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 20;
LABEL_125:
        WPP_SF_(v34->Queue.ListEntry.Blink, v35, WPP_aba9ea4786c33bee720bab7b7487891b_Traceguids);
        goto LABEL_126;
      }
      goto LABEL_126;
    }
    ACProbeArrayElementsForWrite(v33, v6, *((_DWORD *)a3 + 48));
    *((_QWORD *)a3 + 23) = v33;
  }
  v36 = (void **)*((_QWORD *)a2 + 77);
  if ( v36 )
  {
    v37 = *v36;
    if ( !v37 && *((_DWORD *)a3 + 52) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 21;
        goto LABEL_125;
      }
LABEL_126:
      ExRaiseStatus(-1073741811);
    }
    ACProbeArrayElementsForWrite(v37, v6, *((_DWORD *)a3 + 52));
    *((_QWORD *)a3 + 25) = v37;
  }
  v38 = (void **)*((_QWORD *)a2 + 79);
  if ( v38 )
  {
    v39 = *v38;
    if ( !v39 && *((_DWORD *)a3 + 56) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 22;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ACProbeArrayElementsForWrite(v39, v6, *((_DWORD *)a3 + 56));
    *((_QWORD *)a3 + 27) = v39;
  }
  v40 = (void **)*((_QWORD *)a2 + 81);
  if ( v40 )
  {
    v41 = *v40;
    if ( !v41 && *((_DWORD *)a3 + 60) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 23;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ACProbeArrayElementsForWrite(v41, v6, *((_DWORD *)a3 + 60));
    *((_QWORD *)a3 + 29) = v41;
  }
  v42 = (void **)*((_QWORD *)a2 + 83);
  if ( v42 )
  {
    v43 = *v42;
    if ( !v43 && *((_DWORD *)a3 + 64) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 24;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ACProbeArrayElementsForWrite(v43, v6, *((_DWORD *)a3 + 64));
    *((_QWORD *)a3 + 31) = v43;
  }
  v44 = (void **)*((_QWORD *)a2 + 85);
  if ( v44 )
  {
    v45 = *v44;
    if ( !v45 && *((_DWORD *)a3 + 68) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 25;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ACProbeArrayElementsForWrite(v45, v6, *((_DWORD *)a3 + 68));
    *((_QWORD *)a3 + 33) = v45;
  }
  v46 = (void **)*((_QWORD *)a2 + 87);
  if ( v46 )
  {
    v47 = *v46;
    if ( !v47 && *((_DWORD *)a3 + 72) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 26;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ACProbeArrayElementsForWrite(v47, v6, *((_DWORD *)a3 + 72));
    *((_QWORD *)a3 + 35) = v47;
  }
  v48 = (void **)*((_QWORD *)a2 + 89);
  if ( v48 )
  {
    v49 = *v48;
    if ( !v49 && *((_DWORD *)a3 + 76) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 27;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ACProbeArrayElementsForWrite(v49, v6, *((_DWORD *)a3 + 76));
    *((_QWORD *)a3 + 37) = v49;
  }
  v50 = (void **)*((_QWORD *)a2 + 92);
  if ( v50 )
  {
    v51 = *v50;
    if ( !v51 && *((_DWORD *)a3 + 80) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 28;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ACProbeArrayElementsForWrite(v51, v6, *((_DWORD *)a3 + 80));
    *((_QWORD *)a3 + 39) = v51;
  }
  v52 = (void **)*((_QWORD *)a2 + 96);
  if ( v52 )
  {
    v53 = *v52;
    if ( !v53 && *((_DWORD *)a3 + 84) )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 29;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    v54 = *((_DWORD *)a3 + 84);
    if ( !v54 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v35 = 30;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ACProbeArrayElementsForWrite(v53, v6, v54);
    *((_QWORD *)a3 + 41) = v53;
  }
}

```

## disassembly

```asm
0x140023b00  push    rbx
0x140023b02  push    rsi
0x140023b03  push    rdi
0x140023b04  push    r14
0x140023b06  push    r15
0x140023b08  sub     rsp, 20h
0x140023b0c  mov     rdi, r8
0x140023b0f  mov     rbx, rdx
0x140023b12  mov     rsi, rcx
0x140023b15  call    ?ACDeepProbeMsgPropsForReceive@@YAXPEAU_DEVICE_OBJECT@@PEAVCACMessageProperties@@PEAUACMessagePropertiesPointerContents@@@Z; ACDeepProbeMsgPropsForReceive(_DEVICE_OBJECT *,CACMessageProperties *,ACMessagePropertiesPointerContents *)
0x140023b1a  mov     rcx, [rbx+260h]; Address
0x140023b21  mov     r14d, 1
0x140023b27  lea     r15d, [r14+3]
0x140023b2b  test    rcx, rcx
0x140023b2e  jz      short loc_140023B51
0x140023b30  mov     r8d, r14d; Alignment
0x140023b33  mov     edx, r15d; Length
0x140023b36  call    cs:__imp_ProbeForWrite
0x140023b3d  nop     dword ptr [rax+rax+00h]
0x140023b42  mov     rax, [rbx+260h]
0x140023b49  mov     ecx, [rax]
0x140023b4b  mov     [rdi+0C0h], ecx
0x140023b51  mov     rcx, [rbx+270h]; Address
0x140023b58  test    rcx, rcx
0x140023b5b  jz      short loc_140023B7E
0x140023b5d  mov     r8d, r14d; Alignment
0x140023b60  mov     rdx, r15; Length
0x140023b63  call    cs:__imp_ProbeForWrite
0x140023b6a  nop     dword ptr [rax+rax+00h]
0x140023b6f  mov     rax, [rbx+270h]
0x140023b76  mov     ecx, [rax]
0x140023b78  mov     [rdi+0D0h], ecx
0x140023b7e  mov     rcx, [rbx+280h]; Address
0x140023b85  test    rcx, rcx
0x140023b88  jz      short loc_140023BAB
0x140023b8a  mov     r8d, r14d; Alignment
0x140023b8d  mov     rdx, r15; Length
0x140023b90  call    cs:__imp_ProbeForWrite
0x140023b97  nop     dword ptr [rax+rax+00h]
0x140023b9c  mov     rax, [rbx+280h]
0x140023ba3  mov     ecx, [rax]
0x140023ba5  mov     [rdi+0E0h], ecx
0x140023bab  mov     rcx, [rbx+290h]; Address
0x140023bb2  test    rcx, rcx
0x140023bb5  jz      short loc_140023BD8
0x140023bb7  mov     r8d, r14d; Alignment
0x140023bba  mov     rdx, r15; Length
0x140023bbd  call    cs:__imp_ProbeForWrite
0x140023bc4  nop     dword ptr [rax+rax+00h]
0x140023bc9  mov     rax, [rbx+290h]
0x140023bd0  mov     ecx, [rax]
0x140023bd2  mov     [rdi+0F0h], ecx
0x140023bd8  mov     rcx, [rbx+2A0h]; Address
0x140023bdf  test    rcx, rcx
0x140023be2  jz      short loc_140023C05
0x140023be4  mov     r8d, r14d; Alignment
0x140023be7  mov     rdx, r15; Length
0x140023bea  call    cs:__imp_ProbeForWrite
0x140023bf1  nop     dword ptr [rax+rax+00h]
0x140023bf6  mov     rax, [rbx+2A0h]
0x140023bfd  mov     ecx, [rax]
0x140023bff  mov     [rdi+100h], ecx
0x140023c05  mov     rcx, [rbx+2B0h]; Address
0x140023c0c  test    rcx, rcx
0x140023c0f  jz      short loc_140023C32
0x140023c11  mov     r8d, r14d; Alignment
0x140023c14  mov     rdx, r15; Length
0x140023c17  call    cs:__imp_ProbeForWrite
0x140023c1e  nop     dword ptr [rax+rax+00h]
0x140023c23  mov     rax, [rbx+2B0h]
0x140023c2a  mov     ecx, [rax]
0x140023c2c  mov     [rdi+110h], ecx
0x140023c32  mov     rcx, [rbx+2C0h]; Address
0x140023c39  test    rcx, rcx
0x140023c3c  jz      short loc_140023C5F
0x140023c3e  mov     r8d, r14d; Alignment
0x140023c41  mov     rdx, r15; Length
0x140023c44  call    cs:__imp_ProbeForWrite
0x140023c4b  nop     dword ptr [rax+rax+00h]
0x140023c50  mov     rax, [rbx+2C0h]
0x140023c57  mov     ecx, [rax]
0x140023c59  mov     [rdi+120h], ecx
0x140023c5f  mov     rcx, [rbx+2D8h]; Address
0x140023c66  test    rcx, rcx
0x140023c69  jz      short loc_140023C8C
0x140023c6b  mov     r8d, r14d; Alignment
0x140023c6e  mov     rdx, r15; Length
0x140023c71  call    cs:__imp_ProbeForWrite
0x140023c78  nop     dword ptr [rax+rax+00h]
0x140023c7d  mov     rax, [rbx+2D8h]
0x140023c84  mov     ecx, [rax]
0x140023c86  mov     [rdi+130h], ecx
0x140023c8c  mov     rcx, [rbx+2E8h]; Address
0x140023c93  test    rcx, rcx
0x140023c96  jz      short loc_140023CB9
0x140023c98  mov     r8d, r14d; Alignment
0x140023c9b  mov     rdx, r15; Length
0x140023c9e  call    cs:__imp_ProbeForWrite
0x140023ca5  nop     dword ptr [rax+rax+00h]
0x140023caa  mov     rax, [rbx+2E8h]
0x140023cb1  mov     ecx, [rax]
0x140023cb3  mov     [rdi+140h], ecx
0x140023cb9  mov     rcx, [rbx+308h]; Address
0x140023cc0  test    rcx, rcx
0x140023cc3  jz      short loc_140023CE6
0x140023cc5  mov     r8d, r14d; Alignment
0x140023cc8  mov     rdx, r15; Length
0x140023ccb  call    cs:__imp_ProbeForWrite
0x140023cd2  nop     dword ptr [rax+rax+00h]
0x140023cd7  mov     rax, [rbx+308h]
0x140023cde  mov     ecx, [rax]
0x140023ce0  mov     [rdi+150h], ecx
0x140023ce6  mov     rcx, [rbx+2F0h]; Address
0x140023ced  test    rcx, rcx
0x140023cf0  jz      short loc_140023D04
0x140023cf2  mov     r8d, r14d; Alignment
0x140023cf5  mov     rdx, r14; Length
0x140023cf8  call    cs:__imp_ProbeForWrite
0x140023cff  nop     dword ptr [rax+rax+00h]
0x140023d04  mov     rcx, [rbx+2F8h]; Address
0x140023d0b  test    rcx, rcx
0x140023d0e  jz      short loc_140023D22
0x140023d10  mov     r8d, r14d; Alignment
0x140023d13  mov     rdx, r14; Length
0x140023d16  call    cs:__imp_ProbeForWrite
0x140023d1d  nop     dword ptr [rax+rax+00h]
0x140023d22  mov     rcx, [rbx+310h]; Address
0x140023d29  test    rcx, rcx
0x140023d2c  jz      short loc_140023D40
0x140023d2e  mov     r8d, r14d; Alignment
0x140023d31  mov     rdx, r15; Length
0x140023d34  call    cs:__imp_ProbeForWrite
0x140023d3b  nop     dword ptr [rax+rax+00h]
0x140023d40  mov     rcx, [rbx+318h]; Address
0x140023d47  test    rcx, rcx
0x140023d4a  jz      short loc_140023D5E
0x140023d4c  mov     r8d, r14d; Alignment
0x140023d4f  mov     rdx, r15; Length
0x140023d52  call    cs:__imp_ProbeForWrite
0x140023d59  nop     dword ptr [rax+rax+00h]
0x140023d5e  mov     rcx, [rbx+320h]; Address
0x140023d65  test    rcx, rcx
0x140023d68  jz      short loc_140023D7C
0x140023d6a  mov     r8d, r14d; Alignment
0x140023d6d  mov     rdx, r15; Length
0x140023d70  call    cs:__imp_ProbeForWrite
0x140023d77  nop     dword ptr [rax+rax+00h]
0x140023d7c  mov     rax, [rsi+40h]
0x140023d80  cmp     dword ptr [rax+3D8h], 0
0x140023d87  jnz     loc_140023EBD
0x140023d8d  mov     rcx, [rbx+258h]; Address
0x140023d94  mov     esi, 8
0x140023d99  test    rcx, rcx
0x140023d9c  jz      short loc_140023DAF
0x140023d9e  mov     r8d, r14d; Alignment
0x140023da1  mov     edx, esi; Length
0x140023da3  call    cs:__imp_ProbeForRead
0x140023daa  nop     dword ptr [rax+rax+00h]
0x140023daf  mov     rcx, [rbx+268h]; Address
0x140023db6  test    rcx, rcx
0x140023db9  jz      short loc_140023DCD
0x140023dbb  mov     r8d, r14d; Alignment
0x140023dbe  mov     rdx, rsi; Length
0x140023dc1  call    cs:__imp_ProbeForRead
0x140023dc8  nop     dword ptr [rax+rax+00h]
0x140023dcd  mov     rcx, [rbx+278h]; Address
0x140023dd4  test    rcx, rcx
0x140023dd7  jz      short loc_140023DEB
0x140023dd9  mov     r8d, r14d; Alignment
0x140023ddc  mov     rdx, rsi; Length
0x140023ddf  call    cs:__imp_ProbeForRead
0x140023de6  nop     dword ptr [rax+rax+00h]
0x140023deb  mov     rcx, [rbx+288h]; Address
0x140023df2  test    rcx, rcx
0x140023df5  jz      short loc_140023E09
0x140023df7  mov     r8d, r14d; Alignment
0x140023dfa  mov     rdx, rsi; Length
0x140023dfd  call    cs:__imp_ProbeForRead
0x140023e04  nop     dword ptr [rax+rax+00h]
0x140023e09  mov     rcx, [rbx+298h]; Address
0x140023e10  test    rcx, rcx
0x140023e13  jz      short loc_140023E27
0x140023e15  mov     r8d, r14d; Alignment
0x140023e18  mov     rdx, rsi; Length
0x140023e1b  call    cs:__imp_ProbeForRead
0x140023e22  nop     dword ptr [rax+rax+00h]
0x140023e27  mov     rcx, [rbx+2A8h]; Address
0x140023e2e  test    rcx, rcx
0x140023e31  jz      short loc_140023E45
0x140023e33  mov     r8d, r14d; Alignment
0x140023e36  mov     rdx, rsi; Length
0x140023e39  call    cs:__imp_ProbeForRead
0x140023e40  nop     dword ptr [rax+rax+00h]
0x140023e45  mov     rcx, [rbx+2B8h]; Address
0x140023e4c  test    rcx, rcx
0x140023e4f  jz      short loc_140023E63
0x140023e51  mov     r8d, r14d; Alignment
0x140023e54  mov     rdx, rsi; Length
0x140023e57  call    cs:__imp_ProbeForRead
0x140023e5e  nop     dword ptr [rax+rax+00h]
0x140023e63  mov     rcx, [rbx+2C8h]; Address
0x140023e6a  test    rcx, rcx
0x140023e6d  jz      short loc_140023E81
0x140023e6f  mov     r8d, r14d; Alignment
0x140023e72  mov     rdx, rsi; Length
0x140023e75  call    cs:__imp_ProbeForRead
0x140023e7c  nop     dword ptr [rax+rax+00h]
0x140023e81  mov     rcx, [rbx+2E0h]; Address
0x140023e88  test    rcx, rcx
0x140023e8b  jz      short loc_140023E9F
0x140023e8d  mov     r8d, r14d; Alignment
0x140023e90  mov     rdx, rsi; Length
0x140023e93  call    cs:__imp_ProbeForRead
0x140023e9a  nop     dword ptr [rax+rax+00h]
0x140023e9f  mov     rcx, [rbx+300h]; Address
0x140023ea6  test    rcx, rcx
0x140023ea9  jz      short loc_140023EBD
0x140023eab  mov     r8d, r14d; Alignment
0x140023eae  mov     rdx, rsi; Length
0x140023eb1  call    cs:__imp_ProbeForRead
0x140023eb8  nop     dword ptr [rax+rax+00h]
0x140023ebd  mov     rsi, [rbx+258h]
0x140023ec4  test    rsi, rsi
0x140023ec7  jz      short loc_140023F1A
0x140023ec9  mov     rsi, [rsi]
0x140023ecc  test    rsi, rsi
0x140023ecf  jnz     short loc_140023F04
0x140023ed1  cmp     [rdi+0C0h], esi
0x140023ed7  jz      short loc_140023F04
0x140023ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ee0  lea     rax, WPP_GLOBAL_Control
0x140023ee7  cmp     rcx, rax
0x140023eea  jz      loc_14002427D
0x140023ef0  mov     eax, [rcx+6Ch]
0x140023ef3  test    r14b, al
0x140023ef6  jz      loc_14002427D
0x140023efc  lea     edx, [rsi+14h]
0x140023eff  jmp     loc_14002426D
0x140023f04  mov     r8d, [rdi+0C0h]; unsigned int
0x140023f0b  mov     rcx, rsi; void *
0x140023f0e  call    ?ACProbeArrayElementsForWrite@@YAXPEAXKK@Z; ACProbeArrayElementsForWrite(void *,ulong,ulong)
0x140023f13  mov     [rdi+0B8h], rsi
0x140023f1a  mov     rsi, [rbx+268h]
0x140023f21  test    rsi, rsi
0x140023f24  jz      short loc_140023F77
0x140023f26  mov     rsi, [rsi]
0x140023f29  test    rsi, rsi
0x140023f2c  jnz     short loc_140023F61
0x140023f2e  cmp     [rdi+0D0h], esi
0x140023f34  jz      short loc_140023F61
0x140023f36  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f3d  lea     rax, WPP_GLOBAL_Control
0x140023f44  cmp     rcx, rax
0x140023f47  jz      loc_14002427D
0x140023f4d  mov     eax, [rcx+6Ch]
0x140023f50  test    r14b, al
0x140023f53  jz      loc_14002427D
0x140023f59  lea     edx, [rsi+15h]
0x140023f5c  jmp     loc_14002426D
0x140023f61  mov     r8d, [rdi+0D0h]; unsigned int
0x140023f68  mov     rcx, rsi; void *
0x140023f6b  call    ?ACProbeArrayElementsForWrite@@YAXPEAXKK@Z; ACProbeArrayElementsForWrite(void *,ulong,ulong)
0x140023f70  mov     [rdi+0C8h], rsi
0x140023f77  mov     rsi, [rbx+278h]
0x140023f7e  test    rsi, rsi
0x140023f81  jz      short loc_140023FD4
0x140023f83  mov     rsi, [rsi]
0x140023f86  test    rsi, rsi
0x140023f89  jnz     short loc_140023FBE
0x140023f8b  cmp     [rdi+0E0h], esi
0x140023f91  jz      short loc_140023FBE
0x140023f93  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f9a  lea     rax, WPP_GLOBAL_Control
0x140023fa1  cmp     rcx, rax
0x140023fa4  jz      loc_14002427D
0x140023faa  mov     eax, [rcx+6Ch]
0x140023fad  test    r14b, al
0x140023fb0  jz      loc_14002427D
0x140023fb6  lea     edx, [rsi+16h]
0x140023fb9  jmp     loc_14002426D
0x140023fbe  mov     r8d, [rdi+0E0h]; unsigned int
0x140023fc5  mov     rcx, rsi; void *
0x140023fc8  call    ?ACProbeArrayElementsForWrite@@YAXPEAXKK@Z; ACProbeArrayElementsForWrite(void *,ulong,ulong)
0x140023fcd  mov     [rdi+0D8h], rsi
0x140023fd4  mov     rsi, [rbx+288h]
0x140023fdb  test    rsi, rsi
0x140023fde  jz      short loc_140024031
0x140023fe0  mov     rsi, [rsi]
0x140023fe3  test    rsi, rsi
0x140023fe6  jnz     short loc_14002401B
0x140023fe8  cmp     [rdi+0F0h], esi
0x140023fee  jz      short loc_14002401B
0x140023ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ff7  lea     rax, WPP_GLOBAL_Control
0x140023ffe  cmp     rcx, rax
0x140024001  jz      loc_14002427D
0x140024007  mov     eax, [rcx+6Ch]
0x14002400a  test    r14b, al
0x14002400d  jz      loc_14002427D
0x140024013  lea     edx, [rsi+17h]
  ... truncated ...
```
