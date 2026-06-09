# ACCreateRemoteProxy

- ea: `0x1400058fc`
- end: `0x140005ce4`
- name: `ACCreateRemoteProxy`
- size: `1000`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _FILE_OBJECT *, volatile void *Address)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x1400010a4`
- `0x140001128`
- `0x140001c04`
- `0x140001c34`
- `0x140003d84`
- `0x1400058fc`
- `0x140007684`
- `0x140009008`
- `0x1400095e0`
- `0x140012754`
- `0x14001b5a8`
- `0x14002186c`
- `0x14002479c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140005983`
- `ntoskrnl!ProbeForRead` at `0x140005983`

## pseudocode

```c
__int64 __fastcall ACCreateRemoteProxy(struct _DEVICE_OBJECT *a1, struct _FILE_OBJECT *a2, wchar_t **Address)
{
  wchar_t *v6; // rsi
  wchar_t *v8; // r15
  struct QUEUE_FORMAT *v9; // rbx
  const wchar_t *v10; // rbx
  CProxy *v11; // rax
  unsigned int v12; // r9d
  struct QUEUE_FORMAT *v13; // r15
  CProxy *v14; // r14
  wchar_t *v15; // rax
  unsigned int v16; // [rsp+20h] [rbp-58h]
  wchar_t *v17; // [rsp+30h] [rbp-48h]
  struct QUEUE_FORMAT *v18; // [rsp+98h] [rbp+20h] BYREF

  v6 = 0;
  v18 = 0;
  if ( !Address )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 203, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
    }
    return 3221225485LL;
  }
  ProbeForRead(Address, 0x18u, 1u);
  v8 = Address[1];
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 204, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, 0);
    }
    return 3221225485LL;
  }
  v9 = (struct QUEUE_FORMAT *)*Address;
  ACProbeArrayElementsForRead(*Address, 0x20u, 1u);
  ACDeepCopyQueueFormat(v9, 1u, &v18);
  v10 = Address[2];
  if ( !v10 )
  {
LABEL_22:
    v11 = (CProxy *)operator new(0xA8u, 0x40u, 0x4341514Du, LowPoolPriority);
    if ( v11 )
    {
      v17 = v8;
      v13 = v18;
      v14 = CProxy::CProxy(v11, a1, a2, v12, v16, v18, v17);
    }
    else
    {
      v14 = 0;
      v13 = v18;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 207, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v14);
    }
    if ( v14 )
    {
      if ( !v6 || (v15 = ACpDupString(v6), (*((_QWORD *)v14 + 20) = v15) != 0) )
      {
        if ( v6 )
          operator delete(v6);
        if ( v13 )
          ACFreeDeepCopyQueueFormat(v13, 1u);
        a2->FsContext = v14;
        *((_DWORD *)a2->FsContext2 + 5) |= 1u;
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 17, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids);
        }
        operator delete(v6);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->Queue.ListEntry.Blink,
            209,
            WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
            3221225626LL);
        }
        CBaseObject::Release(v14);
        ACFreeDeepCopyQueueFormat(v13, 1u);
        return 3221225626LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 208, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
      }
      ACFreeDeepCopyQueueFormat(v13, 1u);
      if ( v6 )
        operator delete(v6);
      return 3221225626LL;
    }
  }
  if ( ACWCUserStringLen(Address[2]) - 1 <= 0x1F )
  {
    v6 = ACpDupString(v10);
    if ( !v6 )
    {
      ACFreeDeepCopyQueueFormat(v18, 1u);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 206, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
      }
      return 3221225626LL;
    }
    goto LABEL_22;
  }
  ACFreeDeepCopyQueueFormat(v18, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 205, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400058fc  mov     rax, rsp
0x1400058ff  mov     [rax+8], rbx
0x140005903  mov     [rax+10h], rsi
0x140005907  mov     [rax+18h], r8
0x14000590b  push    rdi
0x14000590c  push    r12
0x14000590e  push    r13
0x140005910  push    r14
0x140005912  push    r15
0x140005914  sub     rsp, 50h
0x140005918  mov     r14, r8
0x14000591b  mov     r13, rdx
0x14000591e  mov     r12, rcx
0x140005921  mov     qword ptr [rax-30h], 0
0x140005929  xor     esi, esi
0x14000592b  mov     [rax-38h], rsi
0x14000592f  mov     [rax+20h], rsi
0x140005933  test    r8, r8
0x140005936  jnz     short loc_140005975
0x140005938  lea     rbx, WPP_GLOBAL_Control
0x14000593f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005946  cmp     rcx, rbx
0x140005949  jz      short loc_14000596B
0x14000594b  mov     eax, [rcx+6Ch]
0x14000594e  lea     edi, [rsi+1]
0x140005951  test    dil, al
0x140005954  jz      short loc_14000596B
0x140005956  mov     edx, 0CBh
0x14000595b  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005962  mov     rcx, [rcx+58h]
0x140005966  call    WPP_SF_
0x14000596b  mov     eax, 0C000000Dh
0x140005970  jmp     loc_140005CC9
0x140005975  mov     edi, 1
0x14000597a  mov     r8d, edi; Alignment
0x14000597d  lea     edx, [rdi+17h]; Length
0x140005980  mov     rcx, r14; Address
0x140005983  call    cs:__imp_ProbeForRead
0x14000598a  nop     dword ptr [rax+rax+00h]
0x14000598f  mov     r15, [r14+8]
0x140005993  test    r15, r15
0x140005996  jnz     short loc_1400059D5
0x140005998  lea     rbx, WPP_GLOBAL_Control
0x14000599f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059a6  cmp     rcx, rbx
0x1400059a9  jz      short loc_1400059CB
0x1400059ab  mov     eax, [rcx+6Ch]
0x1400059ae  test    dil, al
0x1400059b1  jz      short loc_1400059CB
0x1400059b3  mov     edx, 0CCh
0x1400059b8  xor     r9d, r9d
0x1400059bb  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400059c2  mov     rcx, [rcx+58h]
0x1400059c6  call    WPP_SF_q
0x1400059cb  mov     eax, 0C000000Dh
0x1400059d0  jmp     loc_140005CC9
0x1400059d5  mov     rbx, [r14]
0x1400059d8  mov     r8d, edi; unsigned int
0x1400059db  mov     edx, 20h ; ' '; unsigned int
0x1400059e0  mov     rcx, rbx; void *
0x1400059e3  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x1400059e8  lea     r8, [rsp+78h+arg_18]; struct QUEUE_FORMAT **
0x1400059f0  mov     edx, edi; unsigned int
0x1400059f2  mov     rcx, rbx; struct QUEUE_FORMAT *
0x1400059f5  call    ?ACDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@KPEAPEAU1@@Z; ACDeepCopyQueueFormat(QUEUE_FORMAT *,ulong,QUEUE_FORMAT * *)
0x1400059fa  mov     rbx, [r14+10h]
0x1400059fe  test    rbx, rbx
0x140005a01  jz      loc_140005AC1
0x140005a07  mov     rcx, rbx; wchar_t *
0x140005a0a  call    ?ACWCUserStringLen@@YAKPEA_W@Z; ACWCUserStringLen(wchar_t *)
0x140005a0f  dec     eax
0x140005a11  cmp     eax, 1Fh
0x140005a14  ja      short loc_140005A78
0x140005a16  mov     rcx, rbx; Src
0x140005a19  call    ?ACpDupString@@YAPEA_WPEB_W@Z; ACpDupString(wchar_t const *)
0x140005a1e  mov     rsi, rax
0x140005a21  mov     [rsp+78h+var_38], rax
0x140005a26  test    rax, rax
0x140005a29  jnz     loc_140005AC1
0x140005a2f  mov     edx, edi; unsigned int
0x140005a31  mov     rcx, [rsp+78h+arg_18]; struct QUEUE_FORMAT *
0x140005a39  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140005a3e  lea     rbx, WPP_GLOBAL_Control
0x140005a45  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a4c  cmp     rcx, rbx
0x140005a4f  jz      short loc_140005A6E
0x140005a51  mov     eax, [rcx+6Ch]
0x140005a54  test    dil, al
0x140005a57  jz      short loc_140005A6E
0x140005a59  mov     edx, 0CEh
0x140005a5e  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005a65  mov     rcx, [rcx+58h]
0x140005a69  call    WPP_SF_
0x140005a6e  mov     eax, 0C000009Ah
0x140005a73  jmp     loc_140005CC9
0x140005a78  mov     edx, edi; unsigned int
0x140005a7a  mov     rcx, [rsp+78h+arg_18]; struct QUEUE_FORMAT *
0x140005a82  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140005a87  lea     rbx, WPP_GLOBAL_Control
0x140005a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a95  cmp     rcx, rbx
0x140005a98  jz      short loc_140005AB7
0x140005a9a  mov     eax, [rcx+6Ch]
0x140005a9d  test    dil, al
0x140005aa0  jz      short loc_140005AB7
0x140005aa2  mov     edx, 0CDh
0x140005aa7  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005aae  mov     rcx, [rcx+58h]
0x140005ab2  call    WPP_SF_
0x140005ab7  mov     eax, 0C000000Dh
0x140005abc  jmp     loc_140005CC9
0x140005ac1  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x140005ac4  lea     edx, [r9+40h]; unsigned __int64
0x140005ac8  lea     ecx, [rdx+68h]; unsigned __int64
0x140005acb  mov     r8d, 4341514Dh; unsigned int
0x140005ad1  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x140005ad6  test    rax, rax
0x140005ad9  jz      short loc_140005B00
0x140005adb  mov     [rsp+78h+var_48], r15; void *
0x140005ae0  mov     r15, [rsp+78h+arg_18]
0x140005ae8  mov     [rsp+78h+var_50], r15; struct QUEUE_FORMAT *
0x140005aed  mov     r8, r13; struct _FILE_OBJECT *
0x140005af0  mov     rdx, r12; struct _DEVICE_OBJECT *
0x140005af3  mov     rcx, rax; this
0x140005af6  call    ??0CProxy@@QEAA@PEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@KKPEBUQUEUE_FORMAT@@PEBX@Z; CProxy::CProxy(_DEVICE_OBJECT *,_FILE_OBJECT *,ulong,ulong,QUEUE_FORMAT const *,void const *)
0x140005afb  mov     r14, rax
0x140005afe  jmp     short loc_140005B0B
0x140005b00  xor     r14d, r14d
0x140005b03  mov     r15, [rsp+78h+arg_18]
0x140005b0b  mov     [rsp+78h+var_30], r14
0x140005b10  lea     rbx, WPP_GLOBAL_Control
0x140005b17  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b1e  cmp     rcx, rbx
0x140005b21  jz      short loc_140005B42
0x140005b23  mov     eax, [rcx+6Ch]
0x140005b26  test    al, 4
0x140005b28  jz      short loc_140005B42
0x140005b2a  mov     edx, 0CFh
0x140005b2f  mov     r9, r14
0x140005b32  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005b39  mov     rcx, [rcx+58h]
0x140005b3d  call    WPP_SF_q
0x140005b42  test    r14, r14
0x140005b45  jnz     short loc_140005B91
0x140005b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b4e  cmp     rcx, rbx
0x140005b51  jz      short loc_140005B70
0x140005b53  mov     eax, [rcx+6Ch]
0x140005b56  test    dil, al
0x140005b59  jz      short loc_140005B70
0x140005b5b  mov     edx, 0D0h
0x140005b60  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005b67  mov     rcx, [rcx+58h]
0x140005b6b  call    WPP_SF_
0x140005b70  mov     edx, edi; unsigned int
0x140005b72  mov     rcx, r15; struct QUEUE_FORMAT *
0x140005b75  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140005b7a  test    rsi, rsi
0x140005b7d  jz      short loc_140005B87
0x140005b7f  mov     rcx, rsi; void *
0x140005b82  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140005b87  mov     eax, 0C000009Ah
0x140005b8c  jmp     loc_140005CC9
0x140005b91  test    rsi, rsi
0x140005b94  jz      loc_140005C2A
0x140005b9a  mov     rcx, rsi; Src
0x140005b9d  call    ?ACpDupString@@YAPEA_WPEB_W@Z; ACpDupString(wchar_t const *)
0x140005ba2  mov     [r14+0A0h], rax
0x140005ba9  test    rax, rax
0x140005bac  jnz     short loc_140005C2A
0x140005bae  mov     rcx, cs:WPP_GLOBAL_Control
0x140005bb5  cmp     rcx, rbx
0x140005bb8  jz      short loc_140005BD7
0x140005bba  mov     eax, [rcx+6Ch]
0x140005bbd  test    dil, al
0x140005bc0  jz      short loc_140005BD7
0x140005bc2  mov     edx, 11h
0x140005bc7  lea     r8, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids
0x140005bce  mov     rcx, [rcx+58h]
0x140005bd2  call    WPP_SF_
0x140005bd7  mov     rcx, rsi; void *
0x140005bda  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140005bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140005be6  cmp     rcx, rbx
0x140005be9  jz      short loc_140005C0E
0x140005beb  mov     eax, [rcx+6Ch]
0x140005bee  test    dil, al
0x140005bf1  jz      short loc_140005C0E
0x140005bf3  mov     edx, 0D1h
0x140005bf8  mov     r9d, 0C000009Ah
0x140005bfe  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005c05  mov     rcx, [rcx+58h]
0x140005c09  call    WPP_SF_d
0x140005c0e  mov     rcx, r14; this
0x140005c11  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140005c16  mov     edx, edi; unsigned int
0x140005c18  mov     rcx, r15; struct QUEUE_FORMAT *
0x140005c1b  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140005c20  mov     eax, 0C000009Ah
0x140005c25  jmp     loc_140005CC9
0x140005c2a  test    rsi, rsi
0x140005c2d  jz      short loc_140005C37
0x140005c2f  mov     rcx, rsi; void *
0x140005c32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140005c37  test    r15, r15
0x140005c3a  jz      short loc_140005C46
0x140005c3c  mov     edx, edi; unsigned int
0x140005c3e  mov     rcx, r15; struct QUEUE_FORMAT *
0x140005c41  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140005c46  mov     [r13+18h], r14
0x140005c4a  mov     rax, [r13+20h]
0x140005c4e  or      [rax+14h], edi
0x140005c51  xor     eax, eax
0x140005c53  jmp     short loc_140005CC9
0x140005c55  mov     ebx, eax
0x140005c57  mov     rcx, [rsp+78h+var_38]; void *
0x140005c5c  test    rcx, rcx
0x140005c5f  jz      short loc_140005C66
0x140005c61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140005c66  mov     rcx, [rsp+78h+var_30]; this
0x140005c6b  test    rcx, rcx
0x140005c6e  jz      short loc_140005C75
0x140005c70  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140005c75  mov     rcx, [rsp+78h+arg_18]; struct QUEUE_FORMAT *
0x140005c7d  test    rcx, rcx
0x140005c80  jz      short loc_140005C8C
0x140005c82  mov     edx, 1; unsigned int
0x140005c87  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140005c8c  lea     rax, WPP_GLOBAL_Control
0x140005c93  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c9a  cmp     rcx, rax
0x140005c9d  jz      short loc_140005CC7
0x140005c9f  mov     eax, [rcx+6Ch]
0x140005ca2  test    al, 1
0x140005ca4  jz      short loc_140005CC7
0x140005ca6  mov     edx, 0D2h
0x140005cab  mov     [rsp+78h+var_58], ebx
0x140005caf  mov     r9, [rsp+78h+arg_10]
0x140005cb7  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005cbe  mov     rcx, [rcx+58h]
0x140005cc2  call    WPP_SF_qD
0x140005cc7  mov     eax, ebx
0x140005cc9  lea     r11, [rsp+78h+var_28]
0x140005cce  mov     rbx, [r11+30h]
0x140005cd2  mov     rsi, [r11+38h]
0x140005cd6  mov     rsp, r11
0x140005cd9  pop     r15
0x140005cdb  pop     r14
0x140005cdd  pop     r13
0x140005cdf  pop     r12
0x140005ce1  pop     rdi
0x140005ce2  retn
```
