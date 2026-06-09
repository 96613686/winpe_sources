# FvePerfDevCreateInstance

- ea: `0x14002dde4`
- end: `0x14002e208`
- name: `FvePerfDevCreateInstance`
- size: `1060`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002d950`

## callees

- `0x14000a150`
- `0x14000ba88`
- `0x1400108a4`
- `0x140021a00`
- `0x14002dde4`
- `0x140098590`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14002df7a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002dfab`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002e1b4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002df7a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002dfab`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002e1b4`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14002de9a`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14002de9a`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14002deb5`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14002deb5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002de62`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002df8b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dfbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e1c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002de62`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002df8b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002dfbd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e1c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002de1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e17c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002de1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e17c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002df5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e072`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e13b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e1d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002df5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e072`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e13b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e1d9`
- `ntoskrnl!ExAllocatePool2` at `0x14002de7c`
- `ntoskrnl!ExAllocatePool2` at `0x14002df2c`
- `ntoskrnl!ExAllocatePool2` at `0x14002de7c`
- `ntoskrnl!ExAllocatePool2` at `0x14002df2c`

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
0x14002dde4  mov     r11, rsp
0x14002dde7  mov     [r11+10h], rdx
0x14002ddeb  push    rbx
0x14002ddec  push    rbp
0x14002dded  push    rsi
0x14002ddee  push    rdi
0x14002ddef  push    r12
0x14002ddf1  push    r13
0x14002ddf3  push    r14
0x14002ddf5  push    r15
0x14002ddf7  sub     rsp, 38h
0x14002ddfb  lea     r12, [rcx+2C0h]
0x14002de02  mov     rdi, rcx
0x14002de05  xor     eax, eax
0x14002de07  xor     r13b, r13b
0x14002de0a  mov     rcx, r12; SpinLock
0x14002de0d  mov     [r11+20h], ax
0x14002de12  mov     rbp, rdx
0x14002de15  mov     [rsp+78h+arg_10], r13b
0x14002de1d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002de24  nop     dword ptr [rax+rax+00h]
0x14002de29  mov     bl, al
0x14002de2b  mov     r8d, 1
0x14002de31  lock xadd [rdi+2D8h], r8d
0x14002de3a  mov     rdx, [rdi+2B8h]; SourceString
0x14002de41  inc     r8d
0x14002de44  cmp     r8d, 1
0x14002de48  setnle  r14b
0x14002de4c  mov     [rsp+78h+arg_0], r14b
0x14002de54  test    rdx, rdx
0x14002de57  jnz     loc_14002DF6C
0x14002de5d  mov     dl, bl; NewIrql
0x14002de5f  mov     rcx, r12; SpinLock
0x14002de62  call    cs:__imp_KeReleaseSpinLock
0x14002de69  nop     dword ptr [rax+rax+00h]
0x14002de6e  mov     edx, 10h
0x14002de73  mov     r8d, 30455646h
0x14002de79  lea     ecx, [rdx+30h]
0x14002de7c  call    cs:__imp_ExAllocatePool2
0x14002de83  nop     dword ptr [rax+rax+00h]
0x14002de88  mov     rbx, rax
0x14002de8b  test    rax, rax
0x14002de8e  jz      loc_14002E052
0x14002de94  xorps   xmm0, xmm0
0x14002de97  movups  xmmword ptr [rax], xmm0
0x14002de9a  call    cs:__imp_KeAreAllApcsDisabled
0x14002dea1  nop     dword ptr [rax+rax+00h]
0x14002dea6  test    al, al
0x14002dea8  jnz     loc_14002E086
0x14002deae  mov     rcx, [rdi+78h]; VolumeDeviceObject
0x14002deb2  mov     rdx, rbx; DosName
0x14002deb5  call    cs:__imp_IoVolumeDeviceToDosName
0x14002debc  nop     dword ptr [rax+rax+00h]
0x14002dec1  mov     esi, eax
0x14002dec3  test    eax, eax
0x14002dec5  js      loc_14002E005
0x14002decb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ded2  lea     rbp, WPP_GLOBAL_Control
0x14002ded9  cmp     rcx, rbp
0x14002dedc  jz      short loc_14002DEE9
0x14002dede  bt      dword ptr [rcx+2Ch], 0Eh
0x14002dee3  jb      loc_14002E101
0x14002dee9  cmp     word ptr [rbx], 4
0x14002deed  mov     [rsp+78h+arg_10], 1
0x14002def5  jb      loc_14002E067
0x14002defb  lea     r15, [rbx+8]
0x14002deff  mov     rdx, [r15]
0x14002df02  movzx   ecx, word ptr [rdx]
0x14002df05  lea     eax, [rcx-41h]
0x14002df08  cmp     ax, 19h
0x14002df0c  ja      loc_14002E059
0x14002df12  cmp     word ptr [rdx+2], 3Ah ; ':'
0x14002df17  jnz     loc_14002E067
0x14002df1d  movzx   edx, word ptr [rbx+2]
0x14002df21  mov     ecx, 40h ; '@'
0x14002df26  mov     r8d, 30455646h
0x14002df2c  call    cs:__imp_ExAllocatePool2
0x14002df33  nop     dword ptr [rax+rax+00h]
0x14002df38  mov     r13, rax
0x14002df3b  test    rax, rax
0x14002df3e  jnz     loc_14002E126
0x14002df44  mov     esi, 0C000009Ah
0x14002df49  mov     rcx, [rbx+8]; P
0x14002df4d  test    rcx, rcx
0x14002df50  jnz     loc_14002E1D7
0x14002df56  mov     edx, 30455646h; Tag
0x14002df5b  mov     rcx, rbx; P
0x14002df5e  call    cs:__imp_ExFreePoolWithTag
0x14002df65  nop     dword ptr [rax+rax+00h]
0x14002df6a  jmp     short loc_14002DFD2
0x14002df6c  test    r14b, r14b
0x14002df6f  jnz     loc_14002DE5D
0x14002df75  mov     rcx, rbp; DestinationString
0x14002df78  xor     esi, esi
0x14002df7a  call    cs:__imp_RtlCopyUnicodeString
0x14002df81  nop     dword ptr [rax+rax+00h]
0x14002df86  mov     dl, bl; NewIrql
0x14002df88  mov     rcx, r12; SpinLock
0x14002df8b  call    cs:__imp_KeReleaseSpinLock
0x14002df92  nop     dword ptr [rax+rax+00h]
0x14002df97  jmp     short loc_14002DFE2
0x14002df99  mov     rcx, [rsp+78h+DestinationString]; DestinationString
0x14002dfa1  mov     rdx, rbx; SourceString
0x14002dfa4  mov     [rdi+2B8h], rbx
0x14002dfab  call    cs:__imp_RtlCopyUnicodeString
0x14002dfb2  nop     dword ptr [rax+rax+00h]
0x14002dfb7  mov     dl, r14b; NewIrql
0x14002dfba  mov     rcx, r12; SpinLock
0x14002dfbd  call    cs:__imp_KeReleaseSpinLock
0x14002dfc4  nop     dword ptr [rax+rax+00h]
0x14002dfc9  test    rbp, rbp
0x14002dfcc  jnz     loc_14002E0D2
0x14002dfd2  mov     r13b, [rsp+78h+arg_10]
0x14002dfda  mov     r14b, [rsp+78h+arg_0]
0x14002dfe2  lock dec dword ptr [rdi+2D8h]
0x14002dfe9  test    esi, esi
0x14002dfeb  jns     loc_14002E1EA
0x14002dff1  mov     eax, esi
0x14002dff3  add     rsp, 38h
0x14002dff7  pop     r15
0x14002dff9  pop     r14
0x14002dffb  pop     r13
0x14002dffd  pop     r12
0x14002dfff  pop     rdi
0x14002e000  pop     rsi
0x14002e001  pop     rbp
0x14002e002  pop     rbx
0x14002e003  retn
0x14002e005  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e00c  lea     rbp, WPP_GLOBAL_Control
0x14002e013  cmp     rcx, rbp
0x14002e016  jz      loc_14002DF49
0x14002e01c  bt      dword ptr [rcx+2Ch], 0Eh
0x14002e021  jnb     loc_14002DF49
0x14002e027  cmp     byte ptr [rcx+29h], 5
0x14002e02b  jb      loc_14002DF49
0x14002e031  mov     rcx, [rcx+18h]
0x14002e035  lea     r8, WPP_6c49290f828f380fa8a5cd03eac9ff75_Traceguids
0x14002e03c  mov     edx, 1Dh
0x14002e041  mov     dword ptr [rsp+78h+var_58], eax
0x14002e045  mov     r9, rdi
0x14002e048  call    WPP_SF_qd
0x14002e04d  jmp     loc_14002DF49
0x14002e052  mov     esi, 0C000009Ah
0x14002e057  jmp     short loc_14002DFE2
0x14002e059  sub     cx, 61h ; 'a'
0x14002e05d  cmp     cx, 19h
0x14002e061  jbe     loc_14002DF12
0x14002e067  mov     rcx, [rbx+8]; P
0x14002e06b  test    rcx, rcx
0x14002e06e  jz      short loc_14002E07E
0x14002e070  xor     edx, edx; Tag
0x14002e072  call    cs:__imp_ExFreePoolWithTag
0x14002e079  nop     dword ptr [rax+rax+00h]
0x14002e07e  xorps   xmm0, xmm0
0x14002e081  movups  xmmword ptr [rbx], xmm0
0x14002e084  jmp     short loc_14002E099
0x14002e086  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e08d  lea     rbp, WPP_GLOBAL_Control
0x14002e094  cmp     rcx, rbp
0x14002e097  jnz     short loc_14002E0DA
0x14002e099  lea     r15, [rbx+8]
0x14002e09d  mov     rcx, rdi
0x14002e0a0  mov     rdx, r15
0x14002e0a3  lea     r8, [rsp+78h+arg_18]
0x14002e0ab  call    FveGetPdoName
0x14002e0b0  mov     esi, eax
0x14002e0b2  test    eax, eax
0x14002e0b4  js      loc_14002DF49
0x14002e0ba  movzx   eax, [rsp+78h+arg_18]
0x14002e0c2  mov     [rbx], ax
0x14002e0c5  add     ax, 2
0x14002e0c9  mov     [rbx+2], ax
0x14002e0cd  jmp     loc_14002DF1D
0x14002e0d2  mov     rbx, rbp
0x14002e0d5  jmp     loc_14002DF49
0x14002e0da  bt      dword ptr [rcx+2Ch], 0Eh
0x14002e0df  jnb     short loc_14002E099
0x14002e0e1  cmp     byte ptr [rcx+29h], 5
0x14002e0e5  jb      short loc_14002E099
0x14002e0e7  mov     rcx, [rcx+18h]
0x14002e0eb  lea     r8, WPP_6c49290f828f380fa8a5cd03eac9ff75_Traceguids
0x14002e0f2  mov     edx, 1Ch
0x14002e0f7  mov     r9, rdi
0x14002e0fa  call    WPP_SF_q
0x14002e0ff  jmp     short loc_14002E099
0x14002e101  cmp     byte ptr [rcx+29h], 5
0x14002e105  jb      loc_14002DEE9
0x14002e10b  mov     rcx, [rcx+18h]
0x14002e10f  mov     edx, 1Eh
0x14002e114  mov     r9, rbx
0x14002e117  mov     [rsp+78h+var_58], rdi
0x14002e11c  call    WPP_SF_Zq
0x14002e121  jmp     loc_14002DEE9
0x14002e126  movzx   r8d, word ptr [rbx+2]; Size
0x14002e12b  mov     rcx, r13; void *
0x14002e12e  mov     rdx, [r15]; Src
0x14002e131  call    memmove
0x14002e136  mov     rcx, [r15]; P
0x14002e139  xor     edx, edx; Tag
0x14002e13b  call    cs:__imp_ExFreePoolWithTag
0x14002e142  nop     dword ptr [rax+rax+00h]
0x14002e147  mov     [r15], r13
0x14002e14a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e151  cmp     rcx, rbp
0x14002e154  jz      short loc_14002E179
0x14002e156  bt      dword ptr [rcx+2Ch], 0Eh
0x14002e15b  jnb     short loc_14002E179
0x14002e15d  cmp     byte ptr [rcx+29h], 5
0x14002e161  jb      short loc_14002E179
0x14002e163  mov     rcx, [rcx+18h]
0x14002e167  mov     edx, 1Fh
0x14002e16c  mov     r9, rbx
0x14002e16f  mov     [rsp+78h+var_58], rdi
0x14002e174  call    WPP_SF_Zq
0x14002e179  mov     rcx, r12; SpinLock
0x14002e17c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e183  nop     dword ptr [rax+rax+00h]
0x14002e188  mov     rbp, [rdi+2B8h]
0x14002e18f  mov     r14b, al
0x14002e192  test    rbp, rbp
0x14002e195  jz      loc_14002DF99
0x14002e19b  cmp     [rsp+78h+arg_0], 0
0x14002e1a3  jnz     loc_14002DF99
0x14002e1a9  mov     rcx, [rsp+78h+DestinationString]; DestinationString
0x14002e1b1  mov     rdx, rbp; SourceString
0x14002e1b4  call    cs:__imp_RtlCopyUnicodeString
0x14002e1bb  nop     dword ptr [rax+rax+00h]
0x14002e1c0  mov     dl, r14b; NewIrql
0x14002e1c3  mov     rcx, r12; SpinLock
0x14002e1c6  call    cs:__imp_KeReleaseSpinLock
0x14002e1cd  nop     dword ptr [rax+rax+00h]
0x14002e1d2  jmp     loc_14002DF49
0x14002e1d7  xor     edx, edx; Tag
0x14002e1d9  call    cs:__imp_ExFreePoolWithTag
0x14002e1e0  nop     dword ptr [rax+rax+00h]
0x14002e1e5  jmp     loc_14002DF56
0x14002e1ea  test    r14b, r14b
0x14002e1ed  jz      loc_14002DFF1
0x14002e1f3  test    r13b, r13b
0x14002e1f6  jz      loc_14002DFF1
0x14002e1fc  lock dec dword ptr [rdi+2D8h]
0x14002e203  jmp     loc_14002DFF1
```
