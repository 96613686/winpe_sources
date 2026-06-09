# ACDeepProbeSendParams(_DEVICE_OBJECT *,CACSendParameters *,ACSendParametersPointerContents *)

- ea: `0x1400242b4`
- end: `0x140024794`
- name: `?ACDeepProbeSendParams@@YAXPEAU_DEVICE_OBJECT@@PEAVCACSendParameters@@PEAUACSendParametersPointerContents@@@Z`
- size: `1248`
- prototype: `void __fastcall(struct _DEVICE_OBJECT *, struct CACSendParameters *, struct ACSendParametersPointerContents *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000881c`

## callees

- `0x140001c04`
- `0x140007684`
- `0x140009008`
- `0x14002186c`
- `0x140022b28`
- `0x1400242b4`
- `0x1400248b0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14002438f`
- `ntoskrnl!ProbeForRead` at `0x1400243ad`
- `ntoskrnl!ProbeForRead` at `0x1400243cb`
- `ntoskrnl!ProbeForRead` at `0x1400243e9`
- `ntoskrnl!ProbeForRead` at `0x140024407`
- `ntoskrnl!ProbeForRead` at `0x140024425`
- `ntoskrnl!ProbeForRead` at `0x1400244fa`
- `ntoskrnl!ProbeForRead` at `0x140024592`
- `ntoskrnl!ProbeForRead` at `0x14002438f`
- `ntoskrnl!ProbeForRead` at `0x1400243ad`
- `ntoskrnl!ProbeForRead` at `0x1400243cb`
- `ntoskrnl!ProbeForRead` at `0x1400243e9`
- `ntoskrnl!ProbeForRead` at `0x140024407`
- `ntoskrnl!ProbeForRead` at `0x140024425`
- `ntoskrnl!ProbeForRead` at `0x1400244fa`
- `ntoskrnl!ProbeForRead` at `0x140024592`
- `ntoskrnl!ExRaiseStatus` at `0x140024753`
- `ntoskrnl!ExRaiseStatus` at `0x140024753`

## pseudocode

```c
void __fastcall ACDeepProbeSendParams(
        struct _DEVICE_OBJECT *a1,
        struct CACSendParameters *a2,
        struct ACSendParametersPointerContents *a3)
{
  void *v6; // rcx
  _DWORD *DeviceExtension; // r14
  unsigned int *v8; // rbx
  void *v9; // rcx
  volatile void *v10; // rcx
  volatile void *v11; // rcx
  volatile void *v12; // rcx
  volatile void *v13; // rcx
  volatile void *v14; // rcx
  volatile void *v15; // rcx
  volatile void **v16; // rbx
  volatile void *v17; // rbx
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  volatile void **v20; // rbx
  volatile void *v21; // rbx
  wchar_t **v22; // r14
  wchar_t *v23; // r14
  unsigned int v24; // ebx
  wchar_t **v25; // r14
  wchar_t *v26; // r14
  unsigned int v27; // ebx
  wchar_t **v28; // r14
  wchar_t *v29; // r14
  unsigned int v30; // ebx
  wchar_t **v31; // rdi
  wchar_t *v32; // rdi
  unsigned int v33; // ebx

  ACPreSanitizeSendParamsLengths(a2);
  ACDeepProbeMsgPropsForSend(a1, a2, a3);
  v6 = (void *)*((_QWORD *)a2 + 73);
  DeviceExtension = a1->DeviceExtension;
  v8 = (unsigned int *)((char *)a2 + 592);
  if ( v6 )
  {
    if ( !DeviceExtension[246] )
      ACProbeArrayElementsForRead(v6, 0x20u, *v8);
    ACDeepCopyQueueFormat(*((struct QUEUE_FORMAT **)a2 + 73), *v8, (struct QUEUE_FORMAT **)a3 + 23);
  }
  else if ( *v8 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      v19 = 10;
      goto LABEL_73;
    }
LABEL_74:
    ExRaiseStatus(-1073741811);
  }
  v9 = (void *)*((_QWORD *)a2 + 75);
  if ( v9 )
  {
    if ( !DeviceExtension[246] )
      ACProbeArrayElementsForRead(v9, 0x20u, *((_DWORD *)a2 + 152));
    ACDeepCopyQueueFormat(*((struct QUEUE_FORMAT **)a2 + 75), *((_DWORD *)a2 + 152), (struct QUEUE_FORMAT **)a3 + 24);
  }
  else if ( *((_DWORD *)a2 + 152) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      v19 = 11;
      goto LABEL_73;
    }
    goto LABEL_74;
  }
  if ( !DeviceExtension[246] )
  {
    v10 = (volatile void *)*((_QWORD *)a2 + 77);
    if ( v10 )
      ProbeForRead(v10, 8u, 1u);
    v11 = (volatile void *)*((_QWORD *)a2 + 79);
    if ( v11 )
      ProbeForRead(v11, 8u, 1u);
    v12 = (volatile void *)*((_QWORD *)a2 + 81);
    if ( v12 )
      ProbeForRead(v12, 8u, 1u);
    v13 = (volatile void *)*((_QWORD *)a2 + 82);
    if ( v13 )
      ProbeForRead(v13, 8u, 1u);
    v14 = (volatile void *)*((_QWORD *)a2 + 83);
    if ( v14 )
      ProbeForRead(v14, 8u, 1u);
    v15 = (volatile void *)*((_QWORD *)a2 + 85);
    if ( v15 )
      ProbeForRead(v15, 8u, 1u);
  }
  v16 = (volatile void **)*((_QWORD *)a2 + 77);
  if ( v16 )
  {
    v17 = *v16;
    if ( !v17 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v19 = 12;
LABEL_73:
        WPP_SF_(v18->Queue.ListEntry.Blink, v19, WPP_aba9ea4786c33bee720bab7b7487891b_Traceguids);
        goto LABEL_74;
      }
      goto LABEL_74;
    }
    ProbeForRead(v17, *((unsigned int *)a2 + 156), 1u);
    *((_QWORD *)a3 + 25) = v17;
  }
  else if ( *((_DWORD *)a2 + 156) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      v19 = 13;
      goto LABEL_73;
    }
    goto LABEL_74;
  }
  v20 = (volatile void **)*((_QWORD *)a2 + 79);
  if ( v20 )
  {
    v21 = *v20;
    if ( !v21 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v19 = 14;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    ProbeForRead(v21, *((unsigned int *)a2 + 160), 1u);
    *((_QWORD *)a3 + 26) = v21;
  }
  else if ( *((_DWORD *)a2 + 160) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      v19 = 15;
      goto LABEL_73;
    }
    goto LABEL_74;
  }
  v22 = (wchar_t **)*((_QWORD *)a2 + 81);
  if ( v22 )
  {
    v23 = *v22;
    if ( !v23 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v19 = 16;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    v24 = ACWCUserStringLen(v23);
    ACProbeArrayElementsForRead(v23, 2u, v24 + 1);
    *((_QWORD *)a3 + 27) = v23;
    *((_DWORD *)a3 + 56) = v24;
  }
  v25 = (wchar_t **)*((_QWORD *)a2 + 82);
  if ( v25 )
  {
    v26 = *v25;
    if ( !v26 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v19 = 17;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    v27 = ACWCUserStringLen(v26);
    ACProbeArrayElementsForRead(v26, 2u, v27 + 1);
    *((_QWORD *)a3 + 29) = v26;
    *((_DWORD *)a3 + 60) = v27;
  }
  v28 = (wchar_t **)*((_QWORD *)a2 + 83);
  if ( v28 )
  {
    v29 = *v28;
    if ( !v29 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v19 = 18;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    v30 = ACWCUserStringLen(v29);
    ACProbeArrayElementsForRead(v29, 2u, v30 + 1);
    *((_QWORD *)a3 + 31) = v29;
    *((_DWORD *)a3 + 64) = v30;
  }
  v31 = (wchar_t **)*((_QWORD *)a2 + 85);
  if ( v31 )
  {
    v32 = *v31;
    if ( !v32 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        v19 = 19;
        goto LABEL_73;
      }
      goto LABEL_74;
    }
    v33 = ACWCUserStringLen(v32);
    ACProbeArrayElementsForRead(v32, 2u, v33 + 1);
    *((_QWORD *)a3 + 33) = v32;
    *((_DWORD *)a3 + 68) = v33;
  }
}

```

## disassembly

```asm
0x1400242b4  push    rbx
0x1400242b6  push    rbp
0x1400242b7  push    rsi
0x1400242b8  push    rdi
0x1400242b9  push    r14
0x1400242bb  sub     rsp, 20h
0x1400242bf  mov     rbx, rcx
0x1400242c2  mov     rbp, r8
0x1400242c5  mov     rcx, rdx; struct CACSendParameters *
0x1400242c8  mov     rdi, rdx
0x1400242cb  call    ?ACPreSanitizeSendParamsLengths@@YAXPEAVCACSendParameters@@@Z; ACPreSanitizeSendParamsLengths(CACSendParameters *)
0x1400242d0  mov     r8, rbp; struct ACMessagePropertiesPointerContents *
0x1400242d3  mov     rdx, rdi; struct CACMessageProperties *
0x1400242d6  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x1400242d9  call    ?ACDeepProbeMsgPropsForSend@@YAXPEAU_DEVICE_OBJECT@@PEAVCACMessageProperties@@PEAUACMessagePropertiesPointerContents@@@Z; ACDeepProbeMsgPropsForSend(_DEVICE_OBJECT *,CACMessageProperties *,ACMessagePropertiesPointerContents *)
0x1400242de  mov     rcx, [rdi+248h]; void *
0x1400242e5  mov     esi, 20h ; ' '
0x1400242ea  mov     r14, [rbx+40h]
0x1400242ee  lea     rbx, [rdi+250h]
0x1400242f5  test    rcx, rcx
0x1400242f8  jz      loc_140024478
0x1400242fe  cmp     dword ptr [r14+3D8h], 0
0x140024306  jnz     short loc_140024312
0x140024308  mov     r8d, [rbx]; unsigned int
0x14002430b  mov     edx, esi; unsigned int
0x14002430d  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x140024312  mov     edx, [rbx]; unsigned int
0x140024314  lea     r8, [rbp+0B8h]; struct QUEUE_FORMAT **
0x14002431b  mov     rcx, [rdi+248h]; struct QUEUE_FORMAT *
0x140024322  call    ?ACDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@KPEAPEAU1@@Z; ACDeepCopyQueueFormat(QUEUE_FORMAT *,ulong,QUEUE_FORMAT * *)
0x140024327  mov     rcx, [rdi+258h]; void *
0x14002432e  test    rcx, rcx
0x140024331  jz      loc_1400244B1
0x140024337  cmp     dword ptr [r14+3D8h], 0
0x14002433f  jnz     short loc_14002434F
0x140024341  mov     r8d, [rdi+260h]; unsigned int
0x140024348  mov     edx, esi; unsigned int
0x14002434a  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x14002434f  mov     edx, [rdi+260h]; unsigned int
0x140024355  lea     r8, [rbp+0C0h]; struct QUEUE_FORMAT **
0x14002435c  mov     rcx, [rdi+258h]; struct QUEUE_FORMAT *
0x140024363  call    ?ACDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@KPEAPEAU1@@Z; ACDeepCopyQueueFormat(QUEUE_FORMAT *,ulong,QUEUE_FORMAT * *)
0x140024368  cmp     dword ptr [r14+3D8h], 0
0x140024370  mov     esi, 1
0x140024375  jnz     loc_140024431
0x14002437b  mov     rcx, [rdi+268h]; Address
0x140024382  lea     ebx, [rsi+7]
0x140024385  test    rcx, rcx
0x140024388  jz      short loc_14002439B
0x14002438a  mov     r8d, esi; Alignment
0x14002438d  mov     edx, ebx; Length
0x14002438f  call    cs:__imp_ProbeForRead
0x140024396  nop     dword ptr [rax+rax+00h]
0x14002439b  mov     rcx, [rdi+278h]; Address
0x1400243a2  test    rcx, rcx
0x1400243a5  jz      short loc_1400243B9
0x1400243a7  mov     r8d, esi; Alignment
0x1400243aa  mov     rdx, rbx; Length
0x1400243ad  call    cs:__imp_ProbeForRead
0x1400243b4  nop     dword ptr [rax+rax+00h]
0x1400243b9  mov     rcx, [rdi+288h]; Address
0x1400243c0  test    rcx, rcx
0x1400243c3  jz      short loc_1400243D7
0x1400243c5  mov     r8d, esi; Alignment
0x1400243c8  mov     rdx, rbx; Length
0x1400243cb  call    cs:__imp_ProbeForRead
0x1400243d2  nop     dword ptr [rax+rax+00h]
0x1400243d7  mov     rcx, [rdi+290h]; Address
0x1400243de  test    rcx, rcx
0x1400243e1  jz      short loc_1400243F5
0x1400243e3  mov     r8d, esi; Alignment
0x1400243e6  mov     rdx, rbx; Length
0x1400243e9  call    cs:__imp_ProbeForRead
0x1400243f0  nop     dword ptr [rax+rax+00h]
0x1400243f5  mov     rcx, [rdi+298h]; Address
0x1400243fc  test    rcx, rcx
0x1400243ff  jz      short loc_140024413
0x140024401  mov     r8d, esi; Alignment
0x140024404  mov     rdx, rbx; Length
0x140024407  call    cs:__imp_ProbeForRead
0x14002440e  nop     dword ptr [rax+rax+00h]
0x140024413  mov     rcx, [rdi+2A8h]; Address
0x14002441a  test    rcx, rcx
0x14002441d  jz      short loc_140024431
0x14002441f  mov     r8d, esi; Alignment
0x140024422  mov     rdx, rbx; Length
0x140024425  call    cs:__imp_ProbeForRead
0x14002442c  nop     dword ptr [rax+rax+00h]
0x140024431  mov     rbx, [rdi+268h]
0x140024438  test    rbx, rbx
0x14002443b  jz      loc_140024550
0x140024441  mov     rbx, [rbx]
0x140024444  test    rbx, rbx
0x140024447  jnz     loc_1400244EE
0x14002444d  mov     rcx, cs:WPP_GLOBAL_Control
0x140024454  lea     rax, WPP_GLOBAL_Control
0x14002445b  cmp     rcx, rax
0x14002445e  jz      loc_14002474E
0x140024464  mov     eax, [rcx+6Ch]
0x140024467  test    sil, al
0x14002446a  jz      loc_14002474E
0x140024470  lea     edx, [rbx+0Ch]
0x140024473  jmp     loc_14002473E
0x140024478  cmp     dword ptr [rbx], 0
0x14002447b  jz      loc_140024327
0x140024481  mov     rcx, cs:WPP_GLOBAL_Control
0x140024488  lea     rax, WPP_GLOBAL_Control
0x14002448f  cmp     rcx, rax
0x140024492  jz      loc_14002474E
0x140024498  mov     eax, [rcx+6Ch]
0x14002449b  mov     esi, 1
0x1400244a0  test    sil, al
0x1400244a3  jz      loc_14002474E
0x1400244a9  lea     edx, [rsi+9]
0x1400244ac  jmp     loc_14002473E
0x1400244b1  cmp     dword ptr [rdi+260h], 0
0x1400244b8  jz      loc_140024368
0x1400244be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400244c5  lea     rax, WPP_GLOBAL_Control
0x1400244cc  cmp     rcx, rax
0x1400244cf  jz      loc_14002474E
0x1400244d5  mov     eax, [rcx+6Ch]
0x1400244d8  mov     esi, 1
0x1400244dd  test    sil, al
0x1400244e0  jz      loc_14002474E
0x1400244e6  lea     edx, [rsi+0Ah]
0x1400244e9  jmp     loc_14002473E
0x1400244ee  mov     edx, [rdi+270h]; Length
0x1400244f4  mov     r8d, esi; Alignment
0x1400244f7  mov     rcx, rbx; Address
0x1400244fa  call    cs:__imp_ProbeForRead
0x140024501  nop     dword ptr [rax+rax+00h]
0x140024506  mov     [rbp+0C8h], rbx
0x14002450d  mov     rbx, [rdi+278h]
0x140024514  test    rbx, rbx
0x140024517  jz      loc_1400245E9
0x14002451d  mov     rbx, [rbx]
0x140024520  test    rbx, rbx
0x140024523  jnz     short loc_140024586
0x140024525  mov     rcx, cs:WPP_GLOBAL_Control
0x14002452c  lea     rax, WPP_GLOBAL_Control
0x140024533  cmp     rcx, rax
0x140024536  jz      loc_14002474E
0x14002453c  mov     eax, [rcx+6Ch]
0x14002453f  test    sil, al
0x140024542  jz      loc_14002474E
0x140024548  lea     edx, [rbx+0Eh]
0x14002454b  jmp     loc_14002473E
0x140024550  cmp     dword ptr [rdi+270h], 0
0x140024557  jz      short loc_14002450D
0x140024559  mov     rcx, cs:WPP_GLOBAL_Control
0x140024560  lea     rax, WPP_GLOBAL_Control
0x140024567  cmp     rcx, rax
0x14002456a  jz      loc_14002474E
0x140024570  mov     eax, [rcx+6Ch]
0x140024573  test    sil, al
0x140024576  jz      loc_14002474E
0x14002457c  mov     edx, 0Dh
0x140024581  jmp     loc_14002473E
0x140024586  mov     edx, [rdi+280h]; Length
0x14002458c  mov     r8d, esi; Alignment
0x14002458f  mov     rcx, rbx; Address
0x140024592  call    cs:__imp_ProbeForRead
0x140024599  nop     dword ptr [rax+rax+00h]
0x14002459e  mov     [rbp+0D0h], rbx
0x1400245a5  mov     r14, [rdi+288h]
0x1400245ac  test    r14, r14
0x1400245af  jz      loc_140024647
0x1400245b5  mov     r14, [r14]
0x1400245b8  test    r14, r14
0x1400245bb  jnz     short loc_14002461F
0x1400245bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400245c4  lea     rax, WPP_GLOBAL_Control
0x1400245cb  cmp     rcx, rax
0x1400245ce  jz      loc_14002474E
0x1400245d4  mov     eax, [rcx+6Ch]
0x1400245d7  test    sil, al
0x1400245da  jz      loc_14002474E
0x1400245e0  lea     edx, [r14+10h]
0x1400245e4  jmp     loc_14002473E
0x1400245e9  cmp     dword ptr [rdi+280h], 0
0x1400245f0  jz      short loc_1400245A5
0x1400245f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400245f9  lea     rax, WPP_GLOBAL_Control
0x140024600  cmp     rcx, rax
0x140024603  jz      loc_14002474E
0x140024609  mov     eax, [rcx+6Ch]
0x14002460c  test    sil, al
0x14002460f  jz      loc_14002474E
0x140024615  mov     edx, 0Fh
0x14002461a  jmp     loc_14002473E
0x14002461f  mov     rcx, r14; wchar_t *
0x140024622  call    ?ACWCUserStringLen@@YAKPEA_W@Z; ACWCUserStringLen(wchar_t *)
0x140024627  mov     edx, 2; unsigned int
0x14002462c  mov     rcx, r14; void *
0x14002462f  mov     ebx, eax
0x140024631  lea     r8d, [rax+1]; unsigned int
0x140024635  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x14002463a  mov     [rbp+0D8h], r14
0x140024641  mov     [rbp+0E0h], ebx
0x140024647  mov     r14, [rdi+290h]
0x14002464e  test    r14, r14
0x140024651  jz      short loc_1400246AF
0x140024653  mov     r14, [r14]
0x140024656  test    r14, r14
0x140024659  jnz     short loc_140024687
0x14002465b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024662  lea     rax, WPP_GLOBAL_Control
0x140024669  cmp     rcx, rax
0x14002466c  jz      loc_14002474E
0x140024672  mov     eax, [rcx+6Ch]
0x140024675  test    sil, al
0x140024678  jz      loc_14002474E
0x14002467e  lea     edx, [r14+11h]
0x140024682  jmp     loc_14002473E
0x140024687  mov     rcx, r14; wchar_t *
0x14002468a  call    ?ACWCUserStringLen@@YAKPEA_W@Z; ACWCUserStringLen(wchar_t *)
0x14002468f  mov     edx, 2; unsigned int
0x140024694  mov     rcx, r14; void *
0x140024697  mov     ebx, eax
0x140024699  lea     r8d, [rax+1]; unsigned int
0x14002469d  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x1400246a2  mov     [rbp+0E8h], r14
0x1400246a9  mov     [rbp+0F0h], ebx
0x1400246af  mov     r14, [rdi+298h]
0x1400246b6  test    r14, r14
0x1400246b9  jz      short loc_14002470C
0x1400246bb  mov     r14, [r14]
0x1400246be  test    r14, r14
0x1400246c1  jnz     short loc_1400246E4
0x1400246c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400246ca  lea     rax, WPP_GLOBAL_Control
0x1400246d1  cmp     rcx, rax
0x1400246d4  jz      short loc_14002474E
0x1400246d6  mov     eax, [rcx+6Ch]
0x1400246d9  test    sil, al
0x1400246dc  jz      short loc_14002474E
0x1400246de  lea     edx, [r14+12h]
0x1400246e2  jmp     short loc_14002473E
0x1400246e4  mov     rcx, r14; wchar_t *
0x1400246e7  call    ?ACWCUserStringLen@@YAKPEA_W@Z; ACWCUserStringLen(wchar_t *)
0x1400246ec  mov     edx, 2; unsigned int
0x1400246f1  mov     rcx, r14; void *
0x1400246f4  mov     ebx, eax
0x1400246f6  lea     r8d, [rax+1]; unsigned int
0x1400246fa  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x1400246ff  mov     [rbp+0F8h], r14
0x140024706  mov     [rbp+100h], ebx
0x14002470c  mov     rdi, [rdi+2A8h]
0x140024713  test    rdi, rdi
0x140024716  jz      short loc_140024788
0x140024718  mov     rdi, [rdi]
0x14002471b  test    rdi, rdi
0x14002471e  jnz     short loc_140024760
0x140024720  mov     rcx, cs:WPP_GLOBAL_Control
0x140024727  lea     rax, WPP_GLOBAL_Control
0x14002472e  cmp     rcx, rax
0x140024731  jz      short loc_14002474E
0x140024733  mov     eax, [rcx+6Ch]
0x140024736  test    sil, al
0x140024739  jz      short loc_14002474E
0x14002473b  lea     edx, [rdi+13h]
0x14002473e  mov     rcx, [rcx+58h]
0x140024742  lea     r8, WPP_aba9ea4786c33bee720bab7b7487891b_Traceguids
0x140024749  call    WPP_SF_
0x14002474e  mov     ecx, 0C000000Dh; Status
0x140024753  call    cs:__imp_ExRaiseStatus
0x140024760  mov     rcx, rdi; wchar_t *
0x140024763  call    ?ACWCUserStringLen@@YAKPEA_W@Z; ACWCUserStringLen(wchar_t *)
0x140024768  mov     edx, 2; unsigned int
0x14002476d  mov     rcx, rdi; void *
0x140024770  mov     ebx, eax
0x140024772  lea     r8d, [rax+1]; unsigned int
0x140024776  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x14002477b  mov     [rbp+108h], rdi
0x140024782  mov     [rbp+110h], ebx
0x140024788  add     rsp, 20h
0x14002478c  pop     r14
0x14002478e  pop     rdi
0x14002478f  pop     rsi
0x140024790  pop     rbp
0x140024791  pop     rbx
0x140024792  retn
```
