# FvePerfDevCreateInstance

- ea: `0x14002ede4`
- end: `0x14002f208`
- name: `FvePerfDevCreateInstance`
- size: `1060`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002e950`

## callees

- `0x14000a210`
- `0x14000bc14`
- `0x140010ca0`
- `0x140022d40`
- `0x14002ede4`
- `0x14009a640`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14002ef7a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002efab`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002f1b4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002ef7a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002efab`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002f1b4`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14002ee9a`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14002ee9a`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14002eeb5`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14002eeb5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ee62`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ef8b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002efbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f1c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ee62`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ef8b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002efbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f1c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ee1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f17c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ee1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f17c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f072`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f13b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f1d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f072`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f13b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f1d9`
- `ntoskrnl!ExAllocatePool2` at `0x14002ee7c`
- `ntoskrnl!ExAllocatePool2` at `0x14002ef2c`
- `ntoskrnl!ExAllocatePool2` at `0x14002ee7c`
- `ntoskrnl!ExAllocatePool2` at `0x14002ef2c`

## pseudocode

```c
__int64 __fastcall FvePerfDevCreateInstance(__int64 a1, struct _UNICODE_STRING *a2)
{
  KSPIN_LOCK *v2; // r12
  char v4; // r13
  KIRQL v6; // al
  KIRQL v7; // bl
  signed __int32 v8; // r8d
  const UNICODE_STRING *v9; // rdx
  int v10; // r8d
  bool v11; // r14
  UNICODE_STRING *Pool2; // rax
  UNICODE_STRING *v13; // rbx
  NTSTATUS v14; // eax
  int v15; // r8d
  int PdoName; // esi
  const void **p_Buffer; // r15
  wchar_t *Buffer; // rdx
  void *v19; // rax
  const void *v20; // r13
  wchar_t *v21; // rcx
  wchar_t *v23; // rcx
  unsigned __int16 v24; // ax
  int v25; // r8d
  KIRQL v26; // al
  const UNICODE_STRING *v27; // rbp
  KIRQL v28; // r14
  bool v29; // [rsp+80h] [rbp+8h]
  char v31; // [rsp+90h] [rbp+18h]
  unsigned __int16 v32; // [rsp+98h] [rbp+20h] BYREF

  v2 = (KSPIN_LOCK *)(a1 + 704);
  v4 = 0;
  v32 = 0;
  v31 = 0;
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 704));
  v7 = v6;
  v8 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 728), 1u);
  v9 = *(const UNICODE_STRING **)(a1 + 696);
  v10 = v8 + 1;
  v11 = v10 > 1;
  v29 = v10 > 1;
  if ( !v9 || v10 > 1 )
  {
    KeReleaseSpinLock(v2, v6);
    Pool2 = (UNICODE_STRING *)ExAllocatePool2(64, 16, 809850438);
    v13 = Pool2;
    if ( !Pool2 )
    {
      PdoName = -1073741670;
      goto LABEL_19;
    }
    *Pool2 = 0;
    if ( KeAreAllApcsDisabled() )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xEu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_6c49290f828f380fa8a5cd03eac9ff75_Traceguids, a1);
      }
    }
    else
    {
      v14 = IoVolumeDeviceToDosName(*(PVOID *)(a1 + 120), v13);
      PdoName = v14;
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xEu)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_6c49290f828f380fa8a5cd03eac9ff75_Traceguids, a1, v14);
        }
        goto LABEL_12;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xEu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_Zq(WPP_GLOBAL_Control->AttachedDevice, 30, v15, (_DWORD)v13, a1);
      }
      v31 = 1;
      if ( v13->Length >= 4u )
      {
        p_Buffer = (const void **)&v13->Buffer;
        Buffer = v13->Buffer;
        if ( ((unsigned __int16)(*Buffer - 65) <= 0x19u || (unsigned __int16)(*Buffer - 97) <= 0x19u) && Buffer[1] == 58 )
          goto LABEL_10;
      }
      v23 = v13->Buffer;
      if ( v23 )
        ExFreePoolWithTag(v23, 0);
      *v13 = 0;
    }
    p_Buffer = (const void **)&v13->Buffer;
    PdoName = FveGetPdoName(a1, &v13->Buffer, &v32);
    if ( PdoName < 0 )
      goto LABEL_12;
    v24 = v32;
    v13->Length = v32;
    v13->MaximumLength = v24 + 2;
LABEL_10:
    v19 = (void *)ExAllocatePool2(64, v13->MaximumLength, 809850438);
    v20 = v19;
    if ( v19 )
    {
      memmove(v19, *p_Buffer, v13->MaximumLength);
      ExFreePoolWithTag((PVOID)*p_Buffer, 0);
      *p_Buffer = v20;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xEu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_Zq(WPP_GLOBAL_Control->AttachedDevice, 31, v25, (_DWORD)v13, a1);
      }
      v26 = KeAcquireSpinLockRaiseToDpc(v2);
      v27 = *(const UNICODE_STRING **)(a1 + 696);
      v28 = v26;
      if ( !v27 || v29 )
      {
        *(_QWORD *)(a1 + 696) = v13;
        RtlCopyUnicodeString(a2, v13);
        KeReleaseSpinLock(v2, v28);
        if ( !v27 )
        {
LABEL_18:
          v4 = v31;
          v11 = v29;
          goto LABEL_19;
        }
        v13 = (UNICODE_STRING *)v27;
      }
      else
      {
        RtlCopyUnicodeString(a2, v27);
        KeReleaseSpinLock(v2, v28);
      }
    }
    else
    {
      PdoName = -1073741670;
    }
LABEL_12:
    v21 = v13->Buffer;
    if ( v21 )
      ExFreePoolWithTag(v21, 0);
    ExFreePoolWithTag(v13, 0x30455646u);
    goto LABEL_18;
  }
  PdoName = 0;
  RtlCopyUnicodeString(a2, v9);
  KeReleaseSpinLock(v2, v7);
LABEL_19:
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 728));
  if ( PdoName >= 0 && v11 && v4 )
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 728));
  return (unsigned int)PdoName;
}

```

## disassembly

```asm
0x14002ede4  mov     r11, rsp
0x14002ede7  mov     [r11+10h], rdx
0x14002edeb  push    rbx
0x14002edec  push    rbp
0x14002eded  push    rsi
0x14002edee  push    rdi
0x14002edef  push    r12
0x14002edf1  push    r13
0x14002edf3  push    r14
0x14002edf5  push    r15
0x14002edf7  sub     rsp, 38h
0x14002edfb  lea     r12, [rcx+2C0h]
0x14002ee02  mov     rdi, rcx
0x14002ee05  xor     eax, eax
0x14002ee07  xor     r13b, r13b
0x14002ee0a  mov     rcx, r12; SpinLock
0x14002ee0d  mov     [r11+20h], ax
0x14002ee12  mov     rbp, rdx
0x14002ee15  mov     [rsp+78h+arg_10], r13b
0x14002ee1d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ee24  nop     dword ptr [rax+rax+00h]
0x14002ee29  mov     bl, al
0x14002ee2b  mov     r8d, 1
0x14002ee31  lock xadd [rdi+2D8h], r8d
0x14002ee3a  mov     rdx, [rdi+2B8h]; SourceString
0x14002ee41  inc     r8d
0x14002ee44  cmp     r8d, 1
0x14002ee48  setnle  r14b
0x14002ee4c  mov     [rsp+78h+arg_0], r14b
0x14002ee54  test    rdx, rdx
0x14002ee57  jnz     loc_14002EF6C
0x14002ee5d  mov     dl, bl; NewIrql
0x14002ee5f  mov     rcx, r12; SpinLock
0x14002ee62  call    cs:__imp_KeReleaseSpinLock
0x14002ee69  nop     dword ptr [rax+rax+00h]
0x14002ee6e  mov     edx, 10h
0x14002ee73  mov     r8d, 30455646h
0x14002ee79  lea     ecx, [rdx+30h]
0x14002ee7c  call    cs:__imp_ExAllocatePool2
0x14002ee83  nop     dword ptr [rax+rax+00h]
0x14002ee88  mov     rbx, rax
0x14002ee8b  test    rax, rax
0x14002ee8e  jz      loc_14002F052
0x14002ee94  xorps   xmm0, xmm0
0x14002ee97  movups  xmmword ptr [rax], xmm0
0x14002ee9a  call    cs:__imp_KeAreAllApcsDisabled
0x14002eea1  nop     dword ptr [rax+rax+00h]
0x14002eea6  test    al, al
0x14002eea8  jnz     loc_14002F086
0x14002eeae  mov     rcx, [rdi+78h]; VolumeDeviceObject
0x14002eeb2  mov     rdx, rbx; DosName
0x14002eeb5  call    cs:__imp_IoVolumeDeviceToDosName
0x14002eebc  nop     dword ptr [rax+rax+00h]
0x14002eec1  mov     esi, eax
0x14002eec3  test    eax, eax
0x14002eec5  js      loc_14002F005
0x14002eecb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eed2  lea     rbp, WPP_GLOBAL_Control
0x14002eed9  cmp     rcx, rbp
0x14002eedc  jz      short loc_14002EEE9
0x14002eede  bt      dword ptr [rcx+2Ch], 0Eh
0x14002eee3  jb      loc_14002F101
0x14002eee9  cmp     word ptr [rbx], 4
0x14002eeed  mov     [rsp+78h+arg_10], 1
0x14002eef5  jb      loc_14002F067
0x14002eefb  lea     r15, [rbx+8]
0x14002eeff  mov     rdx, [r15]
0x14002ef02  movzx   ecx, word ptr [rdx]
0x14002ef05  lea     eax, [rcx-41h]
0x14002ef08  cmp     ax, 19h
0x14002ef0c  ja      loc_14002F059
0x14002ef12  cmp     word ptr [rdx+2], 3Ah ; ':'
0x14002ef17  jnz     loc_14002F067
0x14002ef1d  movzx   edx, word ptr [rbx+2]
0x14002ef21  mov     ecx, 40h ; '@'
0x14002ef26  mov     r8d, 30455646h
0x14002ef2c  call    cs:__imp_ExAllocatePool2
0x14002ef33  nop     dword ptr [rax+rax+00h]
0x14002ef38  mov     r13, rax
0x14002ef3b  test    rax, rax
0x14002ef3e  jnz     loc_14002F126
0x14002ef44  mov     esi, 0C000009Ah
0x14002ef49  mov     rcx, [rbx+8]; P
0x14002ef4d  test    rcx, rcx
0x14002ef50  jnz     loc_14002F1D7
0x14002ef56  mov     edx, 30455646h; Tag
0x14002ef5b  mov     rcx, rbx; P
0x14002ef5e  call    cs:__imp_ExFreePoolWithTag
0x14002ef65  nop     dword ptr [rax+rax+00h]
0x14002ef6a  jmp     short loc_14002EFD2
0x14002ef6c  test    r14b, r14b
0x14002ef6f  jnz     loc_14002EE5D
0x14002ef75  mov     rcx, rbp; DestinationString
0x14002ef78  xor     esi, esi
0x14002ef7a  call    cs:__imp_RtlCopyUnicodeString
0x14002ef81  nop     dword ptr [rax+rax+00h]
0x14002ef86  mov     dl, bl; NewIrql
0x14002ef88  mov     rcx, r12; SpinLock
0x14002ef8b  call    cs:__imp_KeReleaseSpinLock
0x14002ef92  nop     dword ptr [rax+rax+00h]
0x14002ef97  jmp     short loc_14002EFE2
0x14002ef99  mov     rcx, [rsp+78h+DestinationString]; DestinationString
0x14002efa1  mov     rdx, rbx; SourceString
0x14002efa4  mov     [rdi+2B8h], rbx
0x14002efab  call    cs:__imp_RtlCopyUnicodeString
0x14002efb2  nop     dword ptr [rax+rax+00h]
0x14002efb7  mov     dl, r14b; NewIrql
0x14002efba  mov     rcx, r12; SpinLock
0x14002efbd  call    cs:__imp_KeReleaseSpinLock
0x14002efc4  nop     dword ptr [rax+rax+00h]
0x14002efc9  test    rbp, rbp
0x14002efcc  jnz     loc_14002F0D2
0x14002efd2  mov     r13b, [rsp+78h+arg_10]
0x14002efda  mov     r14b, [rsp+78h+arg_0]
0x14002efe2  lock dec dword ptr [rdi+2D8h]
0x14002efe9  test    esi, esi
0x14002efeb  jns     loc_14002F1EA
0x14002eff1  mov     eax, esi
0x14002eff3  add     rsp, 38h
0x14002eff7  pop     r15
0x14002eff9  pop     r14
0x14002effb  pop     r13
0x14002effd  pop     r12
0x14002efff  pop     rdi
0x14002f000  pop     rsi
0x14002f001  pop     rbp
0x14002f002  pop     rbx
0x14002f003  retn
0x14002f005  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f00c  lea     rbp, WPP_GLOBAL_Control
0x14002f013  cmp     rcx, rbp
0x14002f016  jz      loc_14002EF49
0x14002f01c  bt      dword ptr [rcx+2Ch], 0Eh
0x14002f021  jnb     loc_14002EF49
0x14002f027  cmp     byte ptr [rcx+29h], 5
0x14002f02b  jb      loc_14002EF49
0x14002f031  mov     rcx, [rcx+18h]
0x14002f035  lea     r8, WPP_6c49290f828f380fa8a5cd03eac9ff75_Traceguids
0x14002f03c  mov     edx, 1Dh
0x14002f041  mov     dword ptr [rsp+78h+var_58], eax
0x14002f045  mov     r9, rdi
0x14002f048  call    WPP_SF_qd
0x14002f04d  jmp     loc_14002EF49
0x14002f052  mov     esi, 0C000009Ah
0x14002f057  jmp     short loc_14002EFE2
0x14002f059  sub     cx, 61h ; 'a'
0x14002f05d  cmp     cx, 19h
0x14002f061  jbe     loc_14002EF12
0x14002f067  mov     rcx, [rbx+8]; P
0x14002f06b  test    rcx, rcx
0x14002f06e  jz      short loc_14002F07E
0x14002f070  xor     edx, edx; Tag
0x14002f072  call    cs:__imp_ExFreePoolWithTag
0x14002f079  nop     dword ptr [rax+rax+00h]
0x14002f07e  xorps   xmm0, xmm0
0x14002f081  movups  xmmword ptr [rbx], xmm0
0x14002f084  jmp     short loc_14002F099
0x14002f086  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f08d  lea     rbp, WPP_GLOBAL_Control
0x14002f094  cmp     rcx, rbp
0x14002f097  jnz     short loc_14002F0DA
0x14002f099  lea     r15, [rbx+8]
0x14002f09d  mov     rcx, rdi
0x14002f0a0  mov     rdx, r15
0x14002f0a3  lea     r8, [rsp+78h+arg_18]
0x14002f0ab  call    FveGetPdoName
0x14002f0b0  mov     esi, eax
0x14002f0b2  test    eax, eax
0x14002f0b4  js      loc_14002EF49
0x14002f0ba  movzx   eax, [rsp+78h+arg_18]
0x14002f0c2  mov     [rbx], ax
0x14002f0c5  add     ax, 2
0x14002f0c9  mov     [rbx+2], ax
0x14002f0cd  jmp     loc_14002EF1D
0x14002f0d2  mov     rbx, rbp
0x14002f0d5  jmp     loc_14002EF49
0x14002f0da  bt      dword ptr [rcx+2Ch], 0Eh
0x14002f0df  jnb     short loc_14002F099
0x14002f0e1  cmp     byte ptr [rcx+29h], 5
0x14002f0e5  jb      short loc_14002F099
0x14002f0e7  mov     rcx, [rcx+18h]
0x14002f0eb  lea     r8, WPP_6c49290f828f380fa8a5cd03eac9ff75_Traceguids
0x14002f0f2  mov     edx, 1Ch
0x14002f0f7  mov     r9, rdi
0x14002f0fa  call    WPP_SF_q
0x14002f0ff  jmp     short loc_14002F099
0x14002f101  cmp     byte ptr [rcx+29h], 5
0x14002f105  jb      loc_14002EEE9
0x14002f10b  mov     rcx, [rcx+18h]
0x14002f10f  mov     edx, 1Eh
0x14002f114  mov     r9, rbx
0x14002f117  mov     [rsp+78h+var_58], rdi
0x14002f11c  call    WPP_SF_Zq
0x14002f121  jmp     loc_14002EEE9
0x14002f126  movzx   r8d, word ptr [rbx+2]; Size
0x14002f12b  mov     rcx, r13; void *
0x14002f12e  mov     rdx, [r15]; Src
0x14002f131  call    memmove
0x14002f136  mov     rcx, [r15]; P
0x14002f139  xor     edx, edx; Tag
0x14002f13b  call    cs:__imp_ExFreePoolWithTag
0x14002f142  nop     dword ptr [rax+rax+00h]
0x14002f147  mov     [r15], r13
0x14002f14a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f151  cmp     rcx, rbp
0x14002f154  jz      short loc_14002F179
0x14002f156  bt      dword ptr [rcx+2Ch], 0Eh
0x14002f15b  jnb     short loc_14002F179
0x14002f15d  cmp     byte ptr [rcx+29h], 5
0x14002f161  jb      short loc_14002F179
0x14002f163  mov     rcx, [rcx+18h]
0x14002f167  mov     edx, 1Fh
0x14002f16c  mov     r9, rbx
0x14002f16f  mov     [rsp+78h+var_58], rdi
0x14002f174  call    WPP_SF_Zq
0x14002f179  mov     rcx, r12; SpinLock
0x14002f17c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f183  nop     dword ptr [rax+rax+00h]
0x14002f188  mov     rbp, [rdi+2B8h]
0x14002f18f  mov     r14b, al
0x14002f192  test    rbp, rbp
0x14002f195  jz      loc_14002EF99
0x14002f19b  cmp     [rsp+78h+arg_0], 0
0x14002f1a3  jnz     loc_14002EF99
0x14002f1a9  mov     rcx, [rsp+78h+DestinationString]; DestinationString
0x14002f1b1  mov     rdx, rbp; SourceString
0x14002f1b4  call    cs:__imp_RtlCopyUnicodeString
0x14002f1bb  nop     dword ptr [rax+rax+00h]
0x14002f1c0  mov     dl, r14b; NewIrql
0x14002f1c3  mov     rcx, r12; SpinLock
0x14002f1c6  call    cs:__imp_KeReleaseSpinLock
0x14002f1cd  nop     dword ptr [rax+rax+00h]
0x14002f1d2  jmp     loc_14002EF49
0x14002f1d7  xor     edx, edx; Tag
0x14002f1d9  call    cs:__imp_ExFreePoolWithTag
0x14002f1e0  nop     dword ptr [rax+rax+00h]
0x14002f1e5  jmp     loc_14002EF56
0x14002f1ea  test    r14b, r14b
0x14002f1ed  jz      loc_14002EFF1
0x14002f1f3  test    r13b, r13b
0x14002f1f6  jz      loc_14002EFF1
0x14002f1fc  lock dec dword ptr [rdi+2D8h]
0x14002f203  jmp     loc_14002EFF1
```
