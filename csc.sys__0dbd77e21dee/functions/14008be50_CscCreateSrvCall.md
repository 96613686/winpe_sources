# CscCreateSrvCall

- ea: `0x14008be50`
- end: `0x14008c128`
- name: `CscCreateSrvCall`
- size: `728`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000a634`
- `0x1400119d0`
- `0x1400169d4`
- `0x140018930`
- `0x14001b710`
- `0x14001db14`
- `0x14002f0f0`
- `0x14008be50`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008bf3d`
- `ntoskrnl!ExAllocatePool2` at `0x14008bf3d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14008bf1f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14008bf1f`

## pseudocode

```c
__int64 __fastcall CscCreateSrvCall(__int64 a1, __int64 a2)
{
  __int64 v2; // r9
  __int64 v3; // rdi
  __int64 v4; // rsi
  int Entry; // ebx
  __int64 v7; // rax
  const UNICODE_STRING *v8; // r14
  bool v9; // bp
  __int64 Pool2; // rbx
  void (__fastcall *v11)(__int64); // rax
  __int64 v13; // [rsp+78h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a2 + 32);
  v3 = a2;
  v4 = *(_QWORD *)(a2 + 264);
  Entry = -1073741634;
  v13 = 0;
  v7 = *(_QWORD *)(v2 + 576);
  v8 = *(const UNICODE_STRING **)(v4 + 64);
  v9 = v7 && *(_DWORD *)(v7 + 4) == -977269668;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(a2) = (*(_BYTE *)(v2 + 749) & 8) != 0 ? 89 : 78;
    WPP_SF_qqccZ(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      v9 ? 89 : 78,
      v4,
      *(_QWORD *)(v2 + 568),
      a2,
      v9 ? 89 : 78,
      *(_QWORD *)(v4 + 64));
  }
  if ( v9 )
  {
    if ( RtlCompareUnicodeString(v8, &CscControlSrvCallName, 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids);
      Entry = CscStoreFindOrCreateEntry((unsigned int)&v13, 0, 0, (_DWORD)v8, 0, 0, 0, 0);
      if ( Entry < 0 )
      {
        Entry = -1073741634;
        goto LABEL_31;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v13, 0, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids);
        }
      }
      CscStoreDereferenceEntry(&v13);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v13, 0, 0);
      goto LABEL_29;
    }
    Pool2 = ExAllocatePool2(64, 136, 1061124178);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids);
    *(_QWORD *)(v4 + 40) = Pool2;
    if ( Pool2 )
    {
      *(_BYTE *)(Pool2 + 4) |= 1u;
      *(_DWORD *)Pool2 = 8972967;
      *(_DWORD *)(v4 + 96) |= 0x200u;
      Entry = 0;
LABEL_29:
      *(_DWORD *)(a1 + 96) |= 0xCu;
      *(_DWORD *)(a1 + 100) = 0;
      goto LABEL_31;
    }
    Entry = -1073741670;
  }
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
      (unsigned int)Entry);
  v11 = *(void (__fastcall **)(__int64))(v3 + 272);
  *(_DWORD *)(v3 + 280) = Entry;
  v11(v3);
  return 259;
}

```

## disassembly

```asm
0x14008be50  mov     [rsp+arg_0], rbx
0x14008be55  mov     [rsp+arg_10], rbp
0x14008be5a  push    rsi
0x14008be5b  push    rdi
0x14008be5c  push    r13
0x14008be5e  push    r14
0x14008be60  push    r15
0x14008be62  sub     rsp, 40h
0x14008be66  mov     r9, [rdx+20h]
0x14008be6a  mov     rdi, rdx
0x14008be6d  mov     rsi, [rdx+108h]
0x14008be74  mov     r15, rcx
0x14008be77  mov     ebx, 0C00000BEh
0x14008be7c  mov     [rsp+68h+arg_8], 0
0x14008be85  mov     rax, [r9+240h]
0x14008be8c  mov     r14, [rsi+40h]
0x14008be90  test    rax, rax
0x14008be93  jz      short loc_14008BEA3
0x14008be95  cmp     dword ptr [rax+4], 0C5C00C5Ch
0x14008be9c  jnz     short loc_14008BEA3
0x14008be9e  mov     bpl, 1
0x14008bea1  jmp     short loc_14008BEA6
0x14008bea3  xor     bpl, bpl
0x14008bea6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bead  lea     r13, WPP_GLOBAL_Control
0x14008beb4  cmp     rcx, r13
0x14008beb7  jz      short loc_14008BF09
0x14008beb9  mov     eax, [rcx+2Ch]
0x14008bebc  test    al, 20h
0x14008bebe  jz      short loc_14008BF09
0x14008bec0  mov     rcx, [rcx+18h]
0x14008bec4  mov     al, bpl
0x14008bec7  neg     al
0x14008bec9  mov     [rsp+68h+var_30], r14
0x14008bece  mov     al, [r9+2EDh]
0x14008bed5  sbb     r8b, r8b
0x14008bed8  and     al, 8
0x14008beda  and     r8b, 0Bh
0x14008bede  add     r8b, 4Eh ; 'N'
0x14008bee2  neg     al
0x14008bee4  mov     byte ptr [rsp+68h+var_38], r8b
0x14008bee9  mov     rax, [r9+238h]
0x14008bef0  mov     r9, rsi
0x14008bef3  sbb     dl, dl
0x14008bef5  and     dl, 0Bh
0x14008bef8  add     dl, 4Eh ; 'N'
0x14008befb  mov     byte ptr [rsp+68h+var_40], dl
0x14008beff  mov     [rsp+68h+var_48], rax
0x14008bf04  call    WPP_SF_qqccZ
0x14008bf09  test    bpl, bpl
0x14008bf0c  jz      loc_14008C0C9
0x14008bf12  xor     r8d, r8d; CaseInSensitive
0x14008bf15  lea     rdx, CscControlSrvCallName; String2
0x14008bf1c  mov     rcx, r14; String1
0x14008bf1f  call    cs:__imp_RtlCompareUnicodeString
0x14008bf26  nop     dword ptr [rax+rax+00h]
0x14008bf2b  test    eax, eax
0x14008bf2d  jnz     short loc_14008BF9D
0x14008bf2f  mov     edx, 88h
0x14008bf34  lea     ecx, [rax+40h]
0x14008bf37  mov     r8d, 3F3F7852h
0x14008bf3d  call    cs:__imp_ExAllocatePool2
0x14008bf44  nop     dword ptr [rax+rax+00h]
0x14008bf49  mov     rbx, rax
0x14008bf4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bf53  cmp     rcx, r13
0x14008bf56  jz      short loc_14008BF74
0x14008bf58  mov     eax, [rcx+2Ch]
0x14008bf5b  test    al, 40h
0x14008bf5d  jz      short loc_14008BF74
0x14008bf5f  mov     rcx, [rcx+18h]
0x14008bf63  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14008bf6a  mov     edx, 0Ch
0x14008bf6f  call    WPP_SF_
0x14008bf74  mov     [rsi+28h], rbx
0x14008bf78  test    rbx, rbx
0x14008bf7b  jz      short loc_14008BF93
0x14008bf7d  or      byte ptr [rbx+4], 1
0x14008bf81  mov     dword ptr [rbx], 88EAA7h
0x14008bf87  bts     dword ptr [rsi+60h], 9
0x14008bf8c  xor     ebx, ebx
0x14008bf8e  jmp     loc_14008C0B5
0x14008bf93  mov     ebx, 0C000009Ah
0x14008bf98  jmp     loc_14008C0C9
0x14008bf9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bfa4  cmp     rcx, r13
0x14008bfa7  jz      short loc_14008BFC5
0x14008bfa9  mov     eax, [rcx+2Ch]
0x14008bfac  test    al, 40h
0x14008bfae  jz      short loc_14008BFC5
0x14008bfb0  mov     rcx, [rcx+18h]
0x14008bfb4  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14008bfbb  mov     edx, 0Dh
0x14008bfc0  call    WPP_SF_
0x14008bfc5  mov     [rsp+68h+var_30], 0
0x14008bfce  lea     rcx, [rsp+68h+arg_8]
0x14008bfd3  mov     [rsp+68h+var_38], 0
0x14008bfdc  mov     r9, r14
0x14008bfdf  mov     [rsp+68h+var_40], 0
0x14008bfe8  xor     r8d, r8d
0x14008bfeb  xor     edx, edx
0x14008bfed  mov     dword ptr [rsp+68h+var_48], 0
0x14008bff5  call    CscStoreFindOrCreateEntry
0x14008bffa  mov     ebx, eax
0x14008bffc  test    eax, eax
0x14008bffe  js      loc_14008C0C4
0x14008c004  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c00b  cmp     rcx, r13
0x14008c00e  jz      short loc_14008C06C
0x14008c010  mov     edx, [rcx+2Ch]
0x14008c013  test    dl, 40h
0x14008c016  jz      short loc_14008C044
0x14008c018  mov     r9, [rsp+68h+arg_8]
0x14008c01d  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14008c024  mov     rcx, [rcx+18h]
0x14008c028  mov     edx, 0Eh
0x14008c02d  mov     [rsp+68h+var_40], 0
0x14008c036  mov     [rsp+68h+var_48], 0
0x14008c03f  call    WPP_SF_qqq
0x14008c044  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c04b  cmp     rcx, r13
0x14008c04e  jz      short loc_14008C06C
0x14008c050  mov     eax, [rcx+2Ch]
0x14008c053  test    al, 40h
0x14008c055  jz      short loc_14008C06C
0x14008c057  mov     rcx, [rcx+18h]
0x14008c05b  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14008c062  mov     edx, 0Fh
0x14008c067  call    WPP_SF_
0x14008c06c  lea     rcx, [rsp+68h+arg_8]
0x14008c071  call    CscStoreDereferenceEntry
0x14008c076  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c07d  cmp     rcx, r13
0x14008c080  jz      short loc_14008C0B5
0x14008c082  mov     eax, [rcx+2Ch]
0x14008c085  test    al, 40h
0x14008c087  jz      short loc_14008C0B5
0x14008c089  mov     r9, [rsp+68h+arg_8]
0x14008c08e  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14008c095  mov     rcx, [rcx+18h]
0x14008c099  mov     edx, 10h
0x14008c09e  mov     [rsp+68h+var_40], 0
0x14008c0a7  mov     [rsp+68h+var_48], 0
0x14008c0b0  call    WPP_SF_qqq
0x14008c0b5  or      dword ptr [r15+60h], 0Ch
0x14008c0ba  mov     dword ptr [r15+64h], 0
0x14008c0c2  jmp     short loc_14008C0C9
0x14008c0c4  mov     ebx, 0C00000BEh
0x14008c0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c0d0  cmp     rcx, r13
0x14008c0d3  jz      short loc_14008C0F4
0x14008c0d5  mov     eax, [rcx+2Ch]
0x14008c0d8  test    al, 20h
0x14008c0da  jz      short loc_14008C0F4
0x14008c0dc  mov     rcx, [rcx+18h]
0x14008c0e0  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14008c0e7  mov     edx, 11h
0x14008c0ec  mov     r9d, ebx
0x14008c0ef  call    WPP_SF_d
0x14008c0f4  mov     rax, [rdi+110h]
0x14008c0fb  mov     rcx, rdi
0x14008c0fe  mov     [rdi+118h], ebx
0x14008c104  call    _guard_dispatch_icall
0x14008c109  lea     r11, [rsp+68h+var_28]
0x14008c10e  mov     eax, 103h
0x14008c113  mov     rbx, [r11+30h]
0x14008c117  mov     rbp, [r11+40h]
0x14008c11b  mov     rsp, r11
0x14008c11e  pop     r15
0x14008c120  pop     r14
0x14008c122  pop     r13
0x14008c124  pop     rdi
0x14008c125  pop     rsi
0x14008c126  retn
```
