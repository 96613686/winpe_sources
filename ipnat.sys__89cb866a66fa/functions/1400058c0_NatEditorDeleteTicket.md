# NatEditorDeleteTicket

- ea: `0x1400058c0`
- end: `0x140005a8a`
- name: `NatEditorDeleteTicket`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x1400058c0`
- `0x14000fe48`
- `0x14001d7ac`
- `0x14001e0f8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000593b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000593b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005a3e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005a3e`

## pseudocode

```c
__int64 __fastcall NatEditorDeleteTicket(
        __int64 a1,
        unsigned int a2,
        unsigned __int8 a3,
        unsigned __int16 a4,
        unsigned int a5,
        unsigned __int16 a6)
{
  __int64 v6; // rbx
  __int64 v8; // rdi
  __int64 v9; // rbp
  __int64 v10; // rbx
  __int64 v11; // rdi
  _QWORD *v12; // rax
  unsigned int v13; // ebx

  v6 = a4;
  v8 = a3;
  v9 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
  }
  v10 = v9 | (((v8 << 16) | v6) << 32);
  v11 = a5 | (((v8 << 16) | a6) << 32);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 24));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, v10, v11);
  }
  v12 = (_QWORD *)NatLookupTicket(a1, v10, v11, 0);
  if ( v12 )
  {
    NatDeleteTicket(a1, v12);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 0);
    }
    v13 = 0;
  }
  else
  {
    v13 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225473LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225473LL);
      }
    }
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 24));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x1400058c0  push    rbx
0x1400058c2  push    rbp
0x1400058c3  push    rsi
0x1400058c4  push    rdi
0x1400058c5  push    r12
0x1400058c7  sub     rsp, 30h
0x1400058cb  movzx   ebx, r9w
0x1400058cf  mov     rsi, rcx
0x1400058d2  movzx   edi, r8b
0x1400058d6  mov     ebp, edx
0x1400058d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400058df  lea     r12, WPP_GLOBAL_Control
0x1400058e6  cmp     rcx, r12
0x1400058e9  jz      short loc_14000590D
0x1400058eb  mov     eax, [rcx+2Ch]
0x1400058ee  test    al, 1
0x1400058f0  jz      short loc_14000590D
0x1400058f2  cmp     byte ptr [rcx+29h], 6
0x1400058f6  jb      short loc_14000590D
0x1400058f8  mov     rcx, [rcx+18h]
0x1400058fc  lea     r8, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids
0x140005903  mov     edx, 2Ch ; ','
0x140005908  call    WPP_SF_
0x14000590d  mov     eax, [rsp+58h+arg_20]
0x140005914  mov     rcx, rdi
0x140005917  movzx   edi, [rsp+58h+arg_28]
0x14000591f  shl     rcx, 10h
0x140005923  or      rbx, rcx
0x140005926  or      rdi, rcx
0x140005929  shl     rbx, 20h
0x14000592d  lea     rcx, [rsi+18h]; SpinLock
0x140005931  shl     rdi, 20h
0x140005935  or      rbx, rbp
0x140005938  or      rdi, rax
0x14000593b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140005942  nop     dword ptr [rax+rax+00h]
0x140005947  mov     rcx, cs:WPP_GLOBAL_Control
0x14000594e  cmp     rcx, r12
0x140005951  jz      short loc_14000597D
0x140005953  mov     eax, [rcx+2Ch]
0x140005956  test    al, 1
0x140005958  jz      short loc_14000597D
0x14000595a  cmp     byte ptr [rcx+29h], 6
0x14000595e  jb      short loc_14000597D
0x140005960  mov     rcx, [rcx+18h]
0x140005964  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14000596b  mov     edx, 3Bh ; ';'
0x140005970  mov     [rsp+58h+var_38], rdi
0x140005975  mov     r9, rbx
0x140005978  call    WPP_SF_ii
0x14000597d  xor     r9d, r9d
0x140005980  mov     r8, rdi
0x140005983  mov     rdx, rbx
0x140005986  mov     rcx, rsi
0x140005989  call    NatLookupTicket
0x14000598e  test    rax, rax
0x140005991  jz      short loc_1400059D3
0x140005993  mov     rdx, rax
0x140005996  mov     rcx, rsi
0x140005999  call    NatDeleteTicket
0x14000599e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059a5  cmp     rcx, r12
0x1400059a8  jz      short loc_1400059CF
0x1400059aa  mov     eax, [rcx+2Ch]
0x1400059ad  test    al, 1
0x1400059af  jz      short loc_1400059CF
0x1400059b1  cmp     byte ptr [rcx+29h], 6
0x1400059b5  jb      short loc_1400059CF
0x1400059b7  mov     rcx, [rcx+18h]
0x1400059bb  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x1400059c2  mov     edx, 3Ch ; '<'
0x1400059c7  xor     r9d, r9d
0x1400059ca  call    WPP_SF_d
0x1400059cf  xor     ebx, ebx
0x1400059d1  jmp     short loc_140005A3A
0x1400059d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059da  mov     ebx, 0C0000001h
0x1400059df  cmp     rcx, r12
0x1400059e2  jz      short loc_140005A3A
0x1400059e4  mov     eax, [rcx+2Ch]
0x1400059e7  test    al, 1
0x1400059e9  jz      short loc_140005A09
0x1400059eb  cmp     byte ptr [rcx+29h], 2
0x1400059ef  jb      short loc_140005A09
0x1400059f1  mov     rcx, [rcx+18h]
0x1400059f5  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x1400059fc  mov     edx, 3Dh ; '='
0x140005a01  mov     r9d, ebx
0x140005a04  call    WPP_SF_d
0x140005a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a10  cmp     rcx, r12
0x140005a13  jz      short loc_140005A3A
0x140005a15  mov     eax, [rcx+2Ch]
0x140005a18  test    al, 1
0x140005a1a  jz      short loc_140005A3A
0x140005a1c  cmp     byte ptr [rcx+29h], 6
0x140005a20  jb      short loc_140005A3A
0x140005a22  mov     rcx, [rcx+18h]
0x140005a26  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x140005a2d  mov     edx, 3Eh ; '>'
0x140005a32  mov     r9d, ebx
0x140005a35  call    WPP_SF_d
0x140005a3a  lea     rcx, [rsi+18h]; SpinLock
0x140005a3e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005a45  nop     dword ptr [rax+rax+00h]
0x140005a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a51  cmp     rcx, r12
0x140005a54  jz      short loc_140005A7C
0x140005a56  mov     edx, [rcx+2Ch]
0x140005a59  test    dl, 1
0x140005a5c  jz      short loc_140005A7C
0x140005a5e  cmp     byte ptr [rcx+29h], 6
0x140005a62  jb      short loc_140005A7C
0x140005a64  mov     rcx, [rcx+18h]
0x140005a68  lea     r8, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids
0x140005a6f  mov     edx, 2Dh ; '-'
0x140005a74  mov     r9d, ebx
0x140005a77  call    WPP_SF_d
0x140005a7c  mov     eax, ebx
0x140005a7e  add     rsp, 30h
0x140005a82  pop     r12
0x140005a84  pop     rdi
0x140005a85  pop     rsi
0x140005a86  pop     rbp
0x140005a87  pop     rbx
0x140005a88  retn
```
