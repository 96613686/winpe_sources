# DiskCreateGuidSymbolicLink

- ea: `0x1400111d0`
- end: `0x14001142f`
- name: `DiskCreateGuidSymbolicLink`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140011438`

## callees

- `0x1400040a8`
- `0x14000572c`
- `0x1400058fc`
- `0x140005bf0`
- `0x1400111d0`
- `0x1400159c0`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400112a6`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400112a6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140011326`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400113b0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140011326`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400113b0`
- `ntoskrnl!ExUuidCreate` at `0x140011305`
- `ntoskrnl!ExUuidCreate` at `0x140011305`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011278`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011278`
- `ntoskrnl!RtlCompareMemory` at `0x140011233`
- `ntoskrnl!RtlCompareMemory` at `0x140011233`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400112f6`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400112f6`

## pseudocode

```c
__int64 __fastcall DiskCreateGuidSymbolicLink(__int64 a1)
{
  __int64 v1; // rdi
  NTSTATUS GuidSymbolicLinkName; // ebx
  __int64 v3; // r15
  UUID *v4; // rsi
  int v6; // r8d
  NTSTATUS v7; // eax
  int v8; // r8d
  _WORD *ErrorLogEntry; // rax
  _WORD *v10; // rbx
  _DWORD *v11; // rax
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+30h] [rbp-58h] BYREF
  __int128 Source2; // [rsp+40h] [rbp-48h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  GuidSymbolicLinkName = 0;
  v3 = *(_QWORD *)(v1 + 96);
  if ( !*(_BYTE *)(v3 + 524) )
  {
    v4 = (UUID *)(*(_QWORD *)(v1 + 1168) + 4LL);
    SymbolicLinkName = 0;
    Source2 = 0;
    if ( RtlCompareMemory(v4, &Source2, 0x10u) == 16 )
      return 3221225473LL;
    while ( 1 )
    {
      GuidSymbolicLinkName = DiskGetGuidSymbolicLinkName(v4, &SymbolicLinkName);
      if ( GuidSymbolicLinkName < 0 )
        break;
      v7 = IoCreateSymbolicLink(&SymbolicLinkName, (PUNICODE_STRING)(v1 + 112));
      GuidSymbolicLinkName = v7;
      if ( v7 >= 0 )
      {
        *(_BYTE *)(v3 + 524) = 1;
        goto LABEL_22;
      }
      if ( v7 != -1073741771 )
        goto LABEL_17;
      ErrorLogEntry = IoAllocateErrorLogEntry(*(PVOID *)(v1 + 8), 0x46u);
      v10 = ErrorLogEntry;
      if ( ErrorLogEntry )
      {
        *((_DWORD *)ErrorLogEntry + 3) = -2147221346;
        *(_QWORD *)ErrorLogEntry = 27;
        if ( RtlStringCbPrintfW(ErrorLogEntry + 24, 0x16u, L"%d", *(unsigned int *)(v1 + 588)) >= 0 )
        {
          ++v10[2];
          v10[3] = 48;
        }
        IoWriteErrorLogEntry(v10);
      }
      GuidSymbolicLinkName = ExUuidCreate(v4);
      v11 = *(_DWORD **)(v1 + 1168);
      if ( GuidSymbolicLinkName < 0 )
      {
        *v11 = 0;
        *v4 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids,
            (unsigned int)GuidSymbolicLinkName);
        }
LABEL_17:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_ZD(WPP_GLOBAL_Control->AttachedDevice, 20, v8, v1 + 112, GuidSymbolicLinkName);
        }
LABEL_22:
        RtlFreeUnicodeString(&SymbolicLinkName);
        return (unsigned int)GuidSymbolicLinkName;
      }
      *v11 |= 1u;
      RtlFreeUnicodeString(&SymbolicLinkName);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_ZD(WPP_GLOBAL_Control->AttachedDevice, 18, v6, v1 + 112, GuidSymbolicLinkName);
    }
    **(_DWORD **)(v1 + 1168) = 0;
    *v4 = 0;
  }
  return (unsigned int)GuidSymbolicLinkName;
}

```

## disassembly

```asm
0x1400111d0  mov     [rsp+arg_8], rbx
0x1400111d5  mov     [rsp+arg_10], rbp
0x1400111da  push    rsi
0x1400111db  push    rdi
0x1400111dc  push    r13
0x1400111de  push    r14
0x1400111e0  push    r15
0x1400111e2  sub     rsp, 60h
0x1400111e6  mov     rax, cs:__security_cookie
0x1400111ed  xor     rax, rsp
0x1400111f0  mov     [rsp+88h+var_38], rax
0x1400111f5  mov     rdi, [rcx+40h]
0x1400111f9  xor     ebx, ebx
0x1400111fb  mov     r15, [rdi+60h]
0x1400111ff  cmp     [r15+20Ch], bl
0x140011206  jnz     loc_140011406
0x14001120c  mov     rsi, [rdi+490h]
0x140011213  lea     r8d, [rbx+10h]; Length
0x140011217  xorps   xmm0, xmm0
0x14001121a  lea     rdx, [rsp+88h+Source2]; Source2
0x14001121f  xorps   xmm1, xmm1
0x140011222  add     rsi, 4
0x140011226  mov     rcx, rsi; Source1
0x140011229  movups  xmmword ptr [rsp+88h+SymbolicLinkName.Length], xmm0
0x14001122e  movups  [rsp+88h+Source2], xmm1
0x140011233  call    cs:__imp_RtlCompareMemory
0x14001123a  nop     dword ptr [rax+rax+00h]
0x14001123f  cmp     rax, 10h
0x140011243  jnz     short loc_14001124F
0x140011245  mov     eax, 0C0000001h
0x14001124a  jmp     loc_140011408
0x14001124f  lea     r14, [rdi+70h]
0x140011253  mov     r13d, 1
0x140011259  lea     rdx, [rsp+88h+SymbolicLinkName]
0x14001125e  mov     rcx, rsi
0x140011261  call    DiskGetGuidSymbolicLinkName
0x140011266  mov     ebx, eax
0x140011268  test    eax, eax
0x14001126a  js      loc_1400113BE
0x140011270  mov     rdx, r14; DeviceName
0x140011273  lea     rcx, [rsp+88h+SymbolicLinkName]; SymbolicLinkName
0x140011278  call    cs:__imp_IoCreateSymbolicLink
0x14001127f  nop     dword ptr [rax+rax+00h]
0x140011284  mov     ebx, eax
0x140011286  test    eax, eax
0x140011288  jns     loc_1400113A4
0x14001128e  lea     rbp, WPP_GLOBAL_Control
0x140011295  cmp     eax, 0C0000035h
0x14001129a  jnz     loc_140011374
0x1400112a0  mov     rcx, [rdi+8]; IoObject
0x1400112a4  mov     dl, 46h ; 'F'; EntrySize
0x1400112a6  call    cs:__imp_IoAllocateErrorLogEntry
0x1400112ad  nop     dword ptr [rax+rax+00h]
0x1400112b2  mov     rbx, rax
0x1400112b5  test    rax, rax
0x1400112b8  jz      short loc_140011302
0x1400112ba  mov     dword ptr [rax+0Ch], 8004009Eh
0x1400112c1  lea     rcx, [rax+30h]; pszDest
0x1400112c5  mov     qword ptr [rax], 1Bh
0x1400112cc  lea     r8, aD; "%d"
0x1400112d3  mov     r9d, [rdi+24Ch]
0x1400112da  mov     edx, 16h; cbDest
0x1400112df  call    RtlStringCbPrintfW
0x1400112e4  test    eax, eax
0x1400112e6  js      short loc_1400112F3
0x1400112e8  add     [rbx+4], r13w
0x1400112ed  mov     word ptr [rbx+6], 30h ; '0'
0x1400112f3  mov     rcx, rbx; ElEntry
0x1400112f6  call    cs:__imp_IoWriteErrorLogEntry
0x1400112fd  nop     dword ptr [rax+rax+00h]
0x140011302  mov     rcx, rsi; Uuid
0x140011305  call    cs:__imp_ExUuidCreate
0x14001130c  nop     dword ptr [rax+rax+00h]
0x140011311  mov     ebx, eax
0x140011313  mov     rax, [rdi+490h]
0x14001131a  test    ebx, ebx
0x14001131c  js      short loc_140011337
0x14001131e  or      [rax], r13d
0x140011321  lea     rcx, [rsp+88h+SymbolicLinkName]; UnicodeString
0x140011326  call    cs:__imp_RtlFreeUnicodeString
0x14001132d  nop     dword ptr [rax+rax+00h]
0x140011332  jmp     loc_140011259
0x140011337  xorps   xmm0, xmm0
0x14001133a  mov     dword ptr [rax], 0
0x140011340  movups  xmmword ptr [rsi], xmm0
0x140011343  mov     rcx, cs:WPP_GLOBAL_Control
0x14001134a  cmp     rcx, rbp
0x14001134d  jz      short loc_140011374
0x14001134f  mov     eax, [rcx+2Ch]
0x140011352  test    al, 2
0x140011354  jz      short loc_140011374
0x140011356  cmp     byte ptr [rcx+29h], 3
0x14001135a  jb      short loc_140011374
0x14001135c  mov     rcx, [rcx+18h]
0x140011360  lea     r8, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids
0x140011367  mov     edx, 13h
0x14001136c  mov     r9d, ebx
0x14001136f  call    WPP_SF_D
0x140011374  mov     rcx, cs:WPP_GLOBAL_Control
0x14001137b  cmp     rcx, rbp
0x14001137e  jz      short loc_1400113AB
0x140011380  mov     eax, [rcx+2Ch]
0x140011383  test    al, 2
0x140011385  jz      short loc_1400113AB
0x140011387  cmp     byte ptr [rcx+29h], 3
0x14001138b  jb      short loc_1400113AB
0x14001138d  mov     rcx, [rcx+18h]
0x140011391  mov     edx, 14h
0x140011396  mov     r9, r14
0x140011399  mov     [rsp+88h+var_68], ebx
0x14001139d  call    WPP_SF_ZD
0x1400113a2  jmp     short loc_1400113AB
0x1400113a4  mov     [r15+20Ch], r13b
0x1400113ab  lea     rcx, [rsp+88h+SymbolicLinkName]; UnicodeString
0x1400113b0  call    cs:__imp_RtlFreeUnicodeString
0x1400113b7  nop     dword ptr [rax+rax+00h]
0x1400113bc  jmp     short loc_140011406
0x1400113be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113c5  lea     rbp, WPP_GLOBAL_Control
0x1400113cc  cmp     rcx, rbp
0x1400113cf  jz      short loc_1400113F3
0x1400113d1  mov     eax, [rcx+2Ch]
0x1400113d4  test    al, 2
0x1400113d6  jz      short loc_1400113F3
0x1400113d8  cmp     byte ptr [rcx+29h], 3
0x1400113dc  jb      short loc_1400113F3
0x1400113de  mov     rcx, [rcx+18h]
0x1400113e2  mov     edx, 12h
0x1400113e7  mov     r9, r14
0x1400113ea  mov     [rsp+88h+var_68], ebx
0x1400113ee  call    WPP_SF_ZD
0x1400113f3  mov     rax, [rdi+490h]
0x1400113fa  xorps   xmm0, xmm0
0x1400113fd  mov     dword ptr [rax], 0
0x140011403  movups  xmmword ptr [rsi], xmm0
0x140011406  mov     eax, ebx
0x140011408  mov     rcx, [rsp+88h+var_38]
0x14001140d  xor     rcx, rsp; StackCookie
0x140011410  call    __security_check_cookie
0x140011415  lea     r11, [rsp+88h+var_28]
0x14001141a  mov     rbx, [r11+38h]
0x14001141e  mov     rbp, [r11+40h]
0x140011422  mov     rsp, r11
0x140011425  pop     r15
0x140011427  pop     r14
0x140011429  pop     r13
0x14001142b  pop     rdi
0x14001142c  pop     rsi
0x14001142d  retn
```
