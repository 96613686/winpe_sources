# CscStoreQueryInformationEntryEx

- ea: `0x14000f8b0`
- end: `0x14000fc00`
- name: `CscStoreQueryInformationEntryEx`
- size: `848`
- prototype: ``
- caller_count: `30`
- callee_count: `7`
- tags: ``

## callers

- `0x1400012ec`
- `0x140010180`
- `0x140013324`
- `0x140013650`
- `0x14001a0c0`
- `0x14004b610`
- `0x14004d450`
- `0x14004e438`
- `0x1400504b0`
- `0x140050ab0`
- `0x140051340`
- `0x140062b70`
- `0x14006f360`
- `0x140070c70`
- `0x140074c74`
- `0x1400761e0`
- `0x140076898`
- `0x140076afc`
- `0x1400770e0`
- `0x14007939c`
- `0x14007dee4`
- `0x14007eb20`
- `0x140083570`
- `0x1400837e0`
- `0x140085e80`
- `0x140087bec`
- `0x140087fd8`
- `0x140088890`
- `0x14008a174`
- `0x14008ab40`

## callees

- `0x14000f8b0`
- `0x140018930`
- `0x1400190ec`
- `0x14001b568`
- `0x1400224f4`
- `0x140023cc8`
- `0x14007a500`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000f9dc`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000f9dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fa22`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fa22`

## pseudocode

```c
__int64 __fastcall CscStoreQueryInformationEntryEx(
        __int64 a1,
        char a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5,
        __int64 a6,
        __int64 a7)
{
  char v8; // di
  int InformationEntry; // ebp
  int v13; // r8d
  char v15; // al
  int v16; // [rsp+20h] [rbp-48h]
  void *retaddr; // [rsp+68h] [rbp+0h]

  v8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qqqqq(
      WPP_GLOBAL_Control->AttachedDevice,
      45,
      WPP_3bd1e00568fe30bc384778544301c268_Traceguids,
      a1,
      a3,
      a4,
      a5,
      a6);
  if ( !a3 && !a4 )
  {
    if ( a5 )
    {
      if ( !a6 )
        goto LABEL_29;
    }
    else if ( !a6 )
    {
      if ( !a7 )
      {
        InformationEntry = -1073741811;
        v13 = 2636;
        goto LABEL_10;
      }
LABEL_29:
      InformationEntry = 0;
      if ( !a7 )
        goto LABEL_6;
    }
  }
  InformationEntry = CscEnQueryInformationEntry(a1, a2 & 1, a3, a4, a6, a7);
  if ( InformationEntry < 0 )
  {
    v13 = 2648;
    goto LABEL_8;
  }
LABEL_6:
  if ( a5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a1, retaddr);
    }
    ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 112), 1u);
    InformationEntry = 0;
    if ( (*(_DWORD *)(a1 + 20) & 8) != 0 )
    {
      InformationEntry = *(_DWORD *)(a1 + 40);
      if ( InformationEntry >= 0 )
        InformationEntry = -1073741533;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
          (unsigned int)InformationEntry);
      }
    }
    else
    {
      v8 = *(_BYTE *)(a1 + 440);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a1, retaddr);
    }
    ExReleaseResourceLite(*(PERESOURCE *)(a1 + 112));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      v15 = 89;
      if ( !v8 )
        v15 = 78;
      LOBYTE(v16) = v15;
      WPP_SF_qcDD(
        WPP_GLOBAL_Control->AttachedDevice,
        62,
        WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
        a1,
        v16,
        InformationEntry,
        (InformationEntry >> 31) & 0x1E30);
    }
    if ( InformationEntry < 0 )
    {
      v13 = 2654;
      goto LABEL_9;
    }
  }
  v13 = 0;
LABEL_8:
  if ( a5 )
LABEL_9:
    *a5 = v8;
LABEL_10:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      46,
      WPP_3bd1e00568fe30bc384778544301c268_Traceguids,
      (unsigned int)InformationEntry,
      v13);
  return (unsigned int)InformationEntry;
}

```

## disassembly

```asm
0x14000f8b0  mov     rax, rsp
0x14000f8b3  sub     rsp, 68h
0x14000f8b7  mov     [rax+8], rbx
0x14000f8bb  mov     [rax+18h], rsi
0x14000f8bf  mov     rsi, r8
0x14000f8c2  mov     [rax-8], rdi
0x14000f8c6  xor     dil, dil
0x14000f8c9  mov     [rax-10h], r12
0x14000f8cd  mov     [rax-18h], r13
0x14000f8d1  mov     r13, r9
0x14000f8d4  mov     [rax-20h], r14
0x14000f8d8  mov     r14, rcx
0x14000f8db  mov     [rax-28h], r15
0x14000f8df  movzx   r15d, dl
0x14000f8e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8ea  lea     r8, WPP_GLOBAL_Control
0x14000f8f1  mov     r12, [rsp+68h+arg_28]
0x14000f8f9  mov     rbx, [rsp+68h+arg_20]
0x14000f901  cmp     rcx, r8
0x14000f904  jz      short loc_14000F913
0x14000f906  test    dword ptr [rcx+2Ch], 40000h
0x14000f90d  jnz     loc_14000FA8A
0x14000f913  mov     rax, [rsp+68h+arg_30]
0x14000f91b  mov     [rsp+68h+arg_8], rbp
0x14000f920  test    rsi, rsi
0x14000f923  jz      loc_14000FA5A
0x14000f929  mov     [rsp+68h+var_40], rax
0x14000f92e  and     r15b, 1
0x14000f932  movzx   edx, r15b
0x14000f936  mov     [rsp+68h+var_48], r12
0x14000f93b  mov     r9, r13
0x14000f93e  mov     r8, rsi
0x14000f941  mov     rcx, r14
0x14000f944  call    CscEnQueryInformationEntry
0x14000f949  mov     ebp, eax
0x14000f94b  test    eax, eax
0x14000f94d  js      loc_14000FAE7
0x14000f953  lea     r8, WPP_GLOBAL_Control
0x14000f95a  test    rbx, rbx
0x14000f95d  jnz     short loc_14000F9BD
0x14000f95f  lea     rsi, WPP_GLOBAL_Control
0x14000f966  xor     r8d, r8d
0x14000f969  test    rbx, rbx
0x14000f96c  jz      short loc_14000F971
0x14000f96e  mov     [rbx], dil
0x14000f971  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f978  mov     r15, [rsp+68h+var_28]
0x14000f97d  cmp     rcx, rsi
0x14000f980  mov     rsi, [rsp+68h+arg_10]
0x14000f988  mov     r14, [rsp+68h+var_20]
0x14000f98d  mov     r13, [rsp+68h+var_18]
0x14000f992  mov     r12, [rsp+68h+var_10]
0x14000f997  mov     rdi, [rsp+68h+var_8]
0x14000f99c  mov     rbx, [rsp+68h+arg_0]
0x14000f9a1  jz      short loc_14000F9B0
0x14000f9a3  test    dword ptr [rcx+2Ch], 40000h
0x14000f9aa  jnz     loc_14000FBDE
0x14000f9b0  mov     eax, ebp
0x14000f9b2  mov     rbp, [rsp+68h+arg_8]
0x14000f9b7  add     rsp, 68h
0x14000f9bb  retn
0x14000f9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f9c4  cmp     rcx, r8
0x14000f9c7  jz      short loc_14000F9D6
0x14000f9c9  test    dword ptr [rcx+2Ch], 40000h
0x14000f9d0  jnz     loc_14000FAF9
0x14000f9d6  mov     rcx, [r14+70h]; Resource
0x14000f9da  mov     dl, 1; Wait
0x14000f9dc  call    cs:__imp_ExAcquireResourceSharedLite
0x14000f9e3  nop     dword ptr [rax+rax+00h]
0x14000f9e8  mov     eax, [r14+14h]
0x14000f9ec  xor     ebp, ebp
0x14000f9ee  test    al, 8
0x14000f9f0  jnz     loc_14000FB20
0x14000f9f6  lea     rsi, WPP_GLOBAL_Control
0x14000f9fd  movzx   edi, byte ptr [r14+1B8h]
0x14000fa05  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa0c  cmp     rcx, rsi
0x14000fa0f  jz      short loc_14000FA1E
0x14000fa11  test    dword ptr [rcx+2Ch], 40000h
0x14000fa18  jnz     loc_14000FB6F
0x14000fa1e  mov     rcx, [r14+70h]; Resource
0x14000fa22  call    cs:__imp_ExReleaseResourceLite
0x14000fa29  nop     dword ptr [rax+rax+00h]
0x14000fa2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa35  cmp     rcx, rsi
0x14000fa38  jz      short loc_14000FA47
0x14000fa3a  test    dword ptr [rcx+2Ch], 40000h
0x14000fa41  jnz     loc_14000FB96
0x14000fa47  test    ebp, ebp
0x14000fa49  jns     loc_14000F966
0x14000fa4f  mov     r8d, 0A5Eh
0x14000fa55  jmp     loc_14000F96E
0x14000fa5a  test    r13, r13
0x14000fa5d  jnz     loc_14000F929
0x14000fa63  test    rbx, rbx
0x14000fa66  jz      short loc_14000FAC2
0x14000fa68  test    r12, r12
0x14000fa6b  jnz     loc_14000F929
0x14000fa71  xor     ebp, ebp
0x14000fa73  test    rax, rax
0x14000fa76  jz      loc_14000F95A
0x14000fa7c  jmp     loc_14000F929
0x14000fa81  test    ebp, ebp
0x14000fa83  js      short loc_14000FA05
0x14000fa85  jmp     loc_14000F9FD
0x14000fa8a  mov     rcx, [rcx+18h]
0x14000fa8e  lea     r8, WPP_3bd1e00568fe30bc384778544301c268_Traceguids
0x14000fa95  mov     [rsp+68h+var_30], r12
0x14000fa9a  mov     edx, 2Dh ; '-'
0x14000fa9f  mov     [rsp+68h+var_38], rbx
0x14000faa4  mov     r9, r14
0x14000faa7  mov     [rsp+68h+var_40], r13
0x14000faac  mov     [rsp+68h+var_48], rsi
0x14000fab1  call    WPP_SF_qqqqq
0x14000fab6  lea     r8, WPP_GLOBAL_Control
0x14000fabd  jmp     loc_14000F913
0x14000fac2  test    r12, r12
0x14000fac5  jnz     loc_14000F929
0x14000facb  test    rax, rax
0x14000face  jnz     short loc_14000FA71
0x14000fad0  mov     ebp, 0C000000Dh
0x14000fad5  lea     rsi, WPP_GLOBAL_Control
0x14000fadc  mov     r8d, 0A4Ch
0x14000fae2  jmp     loc_14000F971
0x14000fae7  mov     r8d, 0A58h
0x14000faed  lea     rsi, WPP_GLOBAL_Control
0x14000faf4  jmp     loc_14000F969
0x14000faf9  mov     rax, [rsp+68h]
0x14000fafe  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14000fb05  mov     rcx, [rcx+18h]
0x14000fb09  mov     edx, 0Eh
0x14000fb0e  mov     r9, r14
0x14000fb11  mov     [rsp+68h+var_48], rax
0x14000fb16  call    WPP_SF_qq
0x14000fb1b  jmp     loc_14000F9D6
0x14000fb20  mov     ebp, [r14+28h]
0x14000fb24  mov     eax, 0C0000123h
0x14000fb29  test    ebp, ebp
0x14000fb2b  cmovns  ebp, eax
0x14000fb2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb35  lea     rsi, WPP_GLOBAL_Control
0x14000fb3c  cmp     rcx, rsi
0x14000fb3f  jz      loc_14000FA05
0x14000fb45  test    dword ptr [rcx+2Ch], 20000h
0x14000fb4c  jz      loc_14000FA81
0x14000fb52  mov     rcx, [rcx+18h]
0x14000fb56  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14000fb5d  mov     edx, 1Ah
0x14000fb62  mov     r9d, ebp
0x14000fb65  call    WPP_SF_d
0x14000fb6a  jmp     loc_14000FA81
0x14000fb6f  mov     rax, [rsp+68h]
0x14000fb74  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14000fb7b  mov     rcx, [rcx+18h]
0x14000fb7f  mov     edx, 0Fh
0x14000fb84  mov     r9, r14
0x14000fb87  mov     [rsp+68h+var_48], rax
0x14000fb8c  call    WPP_SF_qq
0x14000fb91  jmp     loc_14000FA1E
0x14000fb96  mov     rcx, [rcx+18h]
0x14000fb9a  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14000fba1  mov     edx, 4Eh ; 'N'
0x14000fba6  mov     r9d, ebp
0x14000fba9  sar     r9d, 1Fh
0x14000fbad  mov     eax, 59h ; 'Y'
0x14000fbb2  and     r9d, 1E30h
0x14000fbb9  mov     dword ptr [rsp+68h+var_38], r9d
0x14000fbbe  test    dil, dil
0x14000fbc1  mov     dword ptr [rsp+68h+var_40], ebp
0x14000fbc5  mov     r9, r14
0x14000fbc8  cmovz   eax, edx
0x14000fbcb  mov     edx, 3Eh ; '>'
0x14000fbd0  mov     byte ptr [rsp+68h+var_48], al
0x14000fbd4  call    WPP_SF_qcDD
0x14000fbd9  jmp     loc_14000FA47
0x14000fbde  mov     rcx, [rcx+18h]
0x14000fbe2  mov     edx, 2Eh ; '.'
0x14000fbe7  mov     dword ptr [rsp+68h+var_48], r8d
0x14000fbec  mov     r9d, ebp
0x14000fbef  lea     r8, WPP_3bd1e00568fe30bc384778544301c268_Traceguids
0x14000fbf6  call    WPP_SF_Dd
0x14000fbfb  jmp     loc_14000F9B0
```
