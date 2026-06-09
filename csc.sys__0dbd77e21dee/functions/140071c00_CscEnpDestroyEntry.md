# CscEnpDestroyEntry

- ea: `0x140071c00`
- end: `0x140071f1b`
- name: `CscEnpDestroyEntry`
- size: `795`
- prototype: `void __fastcall(char *P)`
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140025e0c`
- `0x14006d870`
- `0x140071990`

## callees

- `0x14000a64c`
- `0x14000f6a8`
- `0x140010e20`
- `0x140011dac`
- `0x1400169d4`
- `0x1400197f4`
- `0x1400269c4`
- `0x14002cccc`
- `0x14002f010`
- `0x140046750`
- `0x140071c00`
- `0x140083064`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140071c8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071cbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071d70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071ef0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071c8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071cbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071d70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071ef0`
- `ntoskrnl!ExDeleteResourceLite` at `0x140071c7a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140071caa`
- `ntoskrnl!ExDeleteResourceLite` at `0x140071edc`
- `ntoskrnl!ExDeleteResourceLite` at `0x140071c7a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140071caa`
- `ntoskrnl!ExDeleteResourceLite` at `0x140071edc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140071d36`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140071d4c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140071d36`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140071d4c`

## pseudocode

```c
void __fastcall CscEnpDestroyEntry(char *P)
{
  char v1; // bp
  __int64 v2; // rsi
  char v4; // bp
  int v5; // eax
  void *v6; // rdi
  void *v7; // rdi
  __int64 v8; // rax
  void *v9; // rcx
  char **v10; // rcx
  PVOID *v11; // rdx
  void *v12; // rdi
  bool v13; // zf
  char v14; // al
  char v15[8]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v16; // [rsp+48h] [rbp-60h] BYREF
  __int64 v17; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v18[16]; // [rsp+58h] [rbp-50h] BYREF

  v1 = P[20];
  v2 = 0;
  v17 = 0;
  v15[0] = 0;
  v4 = v1 & 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    v14 = 89;
    if ( !v4 )
      v14 = 78;
    WPP_SF_qc(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, P, v14);
  }
  v5 = *((_DWORD *)P + 5);
  if ( (v5 & 0x80u) != 0 && (v5 & 8) == 0 )
  {
    v16 = *(_QWORD *)(P + 196);
    CscEnpOverrideShareInformationIfNeeded(P, &v16);
    CscEnpComputePqQueueCommand(SHIDWORD(v16), *((_DWORD *)P + 48), *((_WORD *)P + 132), 1, 0, (__int64)v18, v15);
    if ( v15[0] )
      CscPqUpdateEntry(
        *(_QWORD *)(*((_QWORD *)P + 1) + 48LL),
        *((_DWORD *)P + 32),
        *((_QWORD *)P + 17),
        0,
        (__int64)v18);
  }
  CscDiffTransferCloseHandle(P);
  if ( P[440] )
  {
    *((_DWORD *)P + 5) |= 0x20u;
    CscEnDeleteEntry((__int64)P, 0, 1);
  }
  v6 = (void *)*((_QWORD *)P + 14);
  if ( v6 )
  {
    ExDeleteResourceLite(*((PERESOURCE *)P + 14));
    ExFreePoolWithTag(v6, 0x22407343u);
    *((_QWORD *)P + 14) = 0;
  }
  v7 = (void *)*((_QWORD *)P + 15);
  if ( v7 )
  {
    ExDeleteResourceLite(*((PERESOURCE *)P + 15));
    ExFreePoolWithTag(v7, 0x22407343u);
    *((_QWORD *)P + 15) = 0;
  }
  v8 = *((_QWORD *)P + 1);
  if ( v8 )
  {
    v13 = *((_DWORD *)P + 4) == 0;
    *((_QWORD *)P + 1) = 0;
    if ( v13 )
      v2 = v8;
    v17 = v2;
  }
  v9 = (void *)*((_QWORD *)P + 18);
  if ( v9 )
  {
    CscStorepLowIoClose(v9);
    *((_QWORD *)P + 18) = 0;
  }
  if ( *((_QWORD *)P + 3) )
  {
    v10 = (char **)*((_QWORD *)P + 12);
    if ( v10[1] != P + 96 || (v11 = (PVOID *)*((_QWORD *)P + 13), *v11 != P + 96) )
      __fastfail(3u);
    *v11 = v10;
    v10[1] = (char *)v11;
    if ( !v4 )
      CscEnDereferenceEntry((__int64)(P + 24));
    *((_QWORD *)P + 3) = 0;
  }
  if ( *((_QWORD *)P + 7) )
    RtlFreeUnicodeString((PUNICODE_STRING)P + 3);
  if ( *((_QWORD *)P + 9) )
    RtlFreeUnicodeString((PUNICODE_STRING)P + 4);
  v12 = (void *)*((_QWORD *)P + 23);
  if ( v12 )
  {
    ExDeleteResourceLite(*((PERESOURCE *)P + 23));
    ExFreePoolWithTag(v12, 0x22407343u);
    *((_QWORD *)P + 23) = 0;
  }
  ExFreePoolWithTag(P, 0x26407343u);
  if ( v2 )
  {
    *(_QWORD *)(v2 + 32) = 0;
    CscEnpDestroyNamespace(&v17);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids);
}

```

## disassembly

```asm
0x140071c00  push    rbx
0x140071c02  push    rbp
0x140071c03  push    rsi
0x140071c04  push    rdi
0x140071c05  push    r14
0x140071c07  push    r15
0x140071c09  sub     rsp, 78h
0x140071c0d  mov     rax, cs:__security_cookie
0x140071c14  xor     rax, rsp
0x140071c17  mov     [rsp+0A8h+var_40], rax
0x140071c1c  movzx   ebp, byte ptr [rcx+14h]
0x140071c20  xor     r14d, r14d
0x140071c23  mov     esi, r14d
0x140071c26  mov     [rsp+0A8h+var_58], r14
0x140071c2b  mov     [rsp+0A8h+var_68], sil
0x140071c30  mov     rbx, rcx
0x140071c33  and     bpl, 1
0x140071c37  mov     rcx, cs:WPP_GLOBAL_Control
0x140071c3e  lea     r15, WPP_GLOBAL_Control
0x140071c45  cmp     rcx, r15
0x140071c48  jnz     loc_140071DE1
0x140071c4e  mov     eax, [rbx+14h]
0x140071c51  test    al, al
0x140071c53  js      loc_140071E1F
0x140071c59  mov     rcx, rbx
0x140071c5c  call    CscDiffTransferCloseHandle
0x140071c61  cmp     [rbx+1B8h], sil
0x140071c68  jnz     loc_140071EAE
0x140071c6e  mov     rdi, [rbx+70h]
0x140071c72  test    rdi, rdi
0x140071c75  jz      short loc_140071C9E
0x140071c77  mov     rcx, rdi; Resource
0x140071c7a  call    cs:__imp_ExDeleteResourceLite
0x140071c81  nop     dword ptr [rax+rax+00h]
0x140071c86  mov     edx, 22407343h; Tag
0x140071c8b  mov     rcx, rdi; P
0x140071c8e  call    cs:__imp_ExFreePoolWithTag
0x140071c95  nop     dword ptr [rax+rax+00h]
0x140071c9a  mov     [rbx+70h], r14
0x140071c9e  mov     rdi, [rbx+78h]
0x140071ca2  test    rdi, rdi
0x140071ca5  jz      short loc_140071CCE
0x140071ca7  mov     rcx, rdi; Resource
0x140071caa  call    cs:__imp_ExDeleteResourceLite
0x140071cb1  nop     dword ptr [rax+rax+00h]
0x140071cb6  mov     edx, 22407343h; Tag
0x140071cbb  mov     rcx, rdi; P
0x140071cbe  call    cs:__imp_ExFreePoolWithTag
0x140071cc5  nop     dword ptr [rax+rax+00h]
0x140071cca  mov     [rbx+78h], r14
0x140071cce  mov     rax, [rbx+8]
0x140071cd2  test    rax, rax
0x140071cd5  jnz     loc_140071DAC
0x140071cdb  mov     rcx, [rbx+90h]; Handle
0x140071ce2  test    rcx, rcx
0x140071ce5  jz      short loc_140071CF3
0x140071ce7  call    CscStorepLowIoClose
0x140071cec  mov     [rbx+90h], r14
0x140071cf3  cmp     [rbx+18h], r14
0x140071cf7  jz      short loc_140071D2C
0x140071cf9  mov     rcx, [rbx+60h]
0x140071cfd  lea     rax, [rbx+60h]
0x140071d01  cmp     [rcx+8], rax
0x140071d05  jnz     loc_140071ED2
0x140071d0b  mov     rdx, [rax+8]
0x140071d0f  cmp     [rdx], rax
0x140071d12  jnz     loc_140071ED2
0x140071d18  mov     [rdx], rcx
0x140071d1b  mov     [rcx+8], rdx
0x140071d1f  test    bpl, bpl
0x140071d22  jz      loc_140071EC4
0x140071d28  mov     [rbx+18h], r14
0x140071d2c  cmp     [rbx+38h], r14
0x140071d30  jz      short loc_140071D42
0x140071d32  lea     rcx, [rbx+30h]; UnicodeString
0x140071d36  call    cs:__imp_RtlFreeUnicodeString
0x140071d3d  nop     dword ptr [rax+rax+00h]
0x140071d42  cmp     [rbx+48h], r14
0x140071d46  jz      short loc_140071D58
0x140071d48  lea     rcx, [rbx+40h]; UnicodeString
0x140071d4c  call    cs:__imp_RtlFreeUnicodeString
0x140071d53  nop     dword ptr [rax+rax+00h]
0x140071d58  mov     rdi, [rbx+0B8h]
0x140071d5f  test    rdi, rdi
0x140071d62  jnz     loc_140071ED9
0x140071d68  mov     edx, 26407343h; Tag
0x140071d6d  mov     rcx, rbx; P
0x140071d70  call    cs:__imp_ExFreePoolWithTag
0x140071d77  nop     dword ptr [rax+rax+00h]
0x140071d7c  test    rsi, rsi
0x140071d7f  jnz     loc_140071F08
0x140071d85  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d8c  cmp     rcx, r15
0x140071d8f  jnz     short loc_140071DC1
0x140071d91  mov     rcx, [rsp+0A8h+var_40]
0x140071d96  xor     rcx, rsp; StackCookie
0x140071d99  call    __security_check_cookie
0x140071d9e  add     rsp, 78h
0x140071da2  pop     r15
0x140071da4  pop     r14
0x140071da6  pop     rdi
0x140071da7  pop     rsi
0x140071da8  pop     rbp
0x140071da9  pop     rbx
0x140071daa  retn
0x140071dac  cmp     [rbx+10h], esi
0x140071daf  mov     [rbx+8], r14
0x140071db3  cmovz   rsi, rax
0x140071db7  mov     [rsp+0A8h+var_58], rsi
0x140071dbc  jmp     loc_140071CDB
0x140071dc1  test    dword ptr [rcx+2Ch], 40000h
0x140071dc8  jz      short loc_140071D91
0x140071dca  mov     rcx, [rcx+18h]
0x140071dce  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x140071dd5  mov     edx, 1Ch
0x140071dda  call    WPP_SF_
0x140071ddf  jmp     short loc_140071D91
0x140071de1  test    dword ptr [rcx+2Ch], 40000h
0x140071de8  jz      loc_140071C4E
0x140071dee  mov     rcx, [rcx+18h]
0x140071df2  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x140071df9  mov     edx, 4Eh ; 'N'
0x140071dfe  test    bpl, bpl
0x140071e01  mov     eax, 59h ; 'Y'
0x140071e06  mov     r9, rbx
0x140071e09  cmovz   eax, edx
0x140071e0c  mov     edx, 1Bh
0x140071e11  mov     byte ptr [rsp+0A8h+var_88], al
0x140071e15  call    WPP_SF_qc
0x140071e1a  jmp     loc_140071C4E
0x140071e1f  test    al, 8
0x140071e21  jnz     loc_140071C59
0x140071e27  mov     rax, [rbx+0C4h]
0x140071e2e  lea     rdx, [rsp+0A8h+var_60]
0x140071e33  mov     rcx, rbx
0x140071e36  mov     [rsp+0A8h+var_60], rax
0x140071e3b  call    CscEnpOverrideShareInformationIfNeeded
0x140071e40  movzx   r8d, word ptr [rbx+108h]
0x140071e48  lea     rcx, [rsp+0A8h+var_68]
0x140071e4d  mov     edx, [rbx+0C0h]
0x140071e53  mov     r9d, 1
0x140071e59  mov     [rsp+0A8h+var_78], rcx
0x140071e5e  lea     rcx, [rsp+0A8h+var_50]
0x140071e63  mov     [rsp+0A8h+var_80], rcx
0x140071e68  mov     ecx, dword ptr [rsp+0A8h+var_60+4]
0x140071e6c  mov     word ptr [rsp+0A8h+var_88], r14w
0x140071e72  call    CscEnpComputePqQueueCommand
0x140071e77  cmp     [rsp+0A8h+var_68], sil
0x140071e7c  jz      loc_140071C59
0x140071e82  mov     rcx, [rbx+8]
0x140071e86  lea     rax, [rsp+0A8h+var_50]
0x140071e8b  mov     r8, [rbx+88h]
0x140071e92  xor     r9d, r9d
0x140071e95  mov     edx, [rbx+80h]
0x140071e9b  mov     [rsp+0A8h+var_88], rax
0x140071ea0  mov     rcx, [rcx+30h]
0x140071ea4  call    CscPqUpdateEntry
0x140071ea9  jmp     loc_140071C59
0x140071eae  or      dword ptr [rbx+14h], 20h
0x140071eb2  mov     r8b, 1
0x140071eb5  xor     edx, edx
0x140071eb7  mov     rcx, rbx
0x140071eba  call    CscEnDeleteEntry
0x140071ebf  jmp     loc_140071C6E
0x140071ec4  lea     rcx, [rbx+18h]
0x140071ec8  call    CscEnDereferenceEntry
0x140071ecd  jmp     loc_140071D28
0x140071ed2  mov     ecx, 3
0x140071ed7  int     29h; Win8: RtlFailFast(ecx)
0x140071ed9  mov     rcx, rdi; Resource
0x140071edc  call    cs:__imp_ExDeleteResourceLite
0x140071ee3  nop     dword ptr [rax+rax+00h]
0x140071ee8  mov     edx, 22407343h; Tag
0x140071eed  mov     rcx, rdi; P
0x140071ef0  call    cs:__imp_ExFreePoolWithTag
0x140071ef7  nop     dword ptr [rax+rax+00h]
0x140071efc  mov     [rbx+0B8h], r14
0x140071f03  jmp     loc_140071D68
0x140071f08  lea     rcx, [rsp+0A8h+var_58]
0x140071f0d  mov     [rsi+20h], r14
0x140071f11  call    CscEnpDestroyNamespace
0x140071f16  jmp     loc_140071D85
```
