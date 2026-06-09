# SmbCeAllocateNewInvalidAuthEntry

- ea: `0x140084dc4`
- end: `0x140084ff8`
- name: `SmbCeAllocateNewInvalidAuthEntry`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140090700`

## callees

- `0x140039fd8`
- `0x14004c720`
- `0x140084dc4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140084efe`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140084efe`
- `ntoskrnl!RtlCopyLuid` at `0x140084f45`
- `ntoskrnl!RtlCopyLuid` at `0x140084f5a`
- `ntoskrnl!RtlCopyLuid` at `0x140084f45`
- `ntoskrnl!RtlCopyLuid` at `0x140084f5a`
- `ntoskrnl!ExAllocatePool2` at `0x140084ec9`
- `ntoskrnl!ExAllocatePool2` at `0x140084ec9`
- `ksecdd!SspiCopyAuthIdentity` at `0x140084e46`
- `ksecdd!SspiCopyAuthIdentity` at `0x140084e46`
- `ksecdd!MapSecurityError` at `0x140084e5a`
- `ksecdd!MapSecurityError` at `0x140084e5a`
- `ksecdd!SspiFreeAuthIdentity` at `0x140084fd5`
- `ksecdd!SspiFreeAuthIdentity` at `0x140084fd5`

## pseudocode

```c
__int64 __fastcall SmbCeAllocateNewInvalidAuthEntry(
        wchar_t *a1,
        __int64 a2,
        __int64 a3,
        const UNICODE_STRING *a4,
        int a5,
        __int64 a6)
{
  int v7; // esi
  SECURITY_STATUS v10; // ebp
  __int64 v11; // rcx
  __int64 v12; // rdi
  void *v13; // rcx
  SECURITY_STATUS v14; // eax
  unsigned int v15; // edi
  UNICODE_STRING *Pool2; // rax
  UNICODE_STRING *v17; // rbx
  int v18; // edx
  int v19; // r8d
  __int64 v20; // rax
  struct _LUID v21; // [rsp+40h] [rbp-38h] BYREF
  struct _LUID SourceLuid; // [rsp+88h] [rbp+10h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+90h] [rbp+18h] BYREF

  AuthDataCopy = 0;
  v21 = 0;
  v7 = a2;
  SourceLuid = 0;
  if ( !a2 )
    return 0;
  v10 = 0;
  v11 = *(_QWORD *)(a2 + 128);
  v12 = *(_QWORD *)(a2 + 384);
  v21 = *(struct _LUID *)(a2 + 104);
  SourceLuid = *(struct _LUID *)(a2 + 96);
  if ( v11 && (v13 = *(void **)(v11 + 8)) != 0 && (v14 = SspiCopyAuthIdentity(v13, &AuthDataCopy), (v10 = v14) != 0) )
  {
    v15 = MapSecurityError(v14);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_48980f24b3dc39b8aaca68646dc5bd2a_Traceguids, v15, v10);
    }
  }
  else
  {
    Pool2 = (UNICODE_STRING *)ExAllocatePool2(258, a4->Length + 80LL, 1834180937);
    v17 = Pool2;
    if ( Pool2 )
    {
      Pool2[1].Buffer = &Pool2[5].Length;
      Pool2[1].MaximumLength = a4->Length;
      RtlCopyUnicodeString(Pool2 + 1, a4);
      *(_DWORD *)&v17[2].Length = *(_DWORD *)(v12 + 72);
      *(_DWORD *)(&v17[2].MaximumLength + 1) = a5;
      *(_QWORD *)&v17[3].Length = a6;
      LODWORD(v17[2].Buffer) = 1;
      v17[3].Buffer = (wchar_t *)AuthDataCopy;
      RtlCopyLuid((PLUID)&v17[4], &SourceLuid);
      RtlCopyLuid((PLUID)&v17[4].Buffer, &v21);
      v20 = *(_QWORD *)a1;
      if ( *(wchar_t **)(*(_QWORD *)a1 + 8LL) != a1 )
        __fastfail(3u);
      *(_QWORD *)&v17->Length = v20;
      v15 = 0;
      v17->Buffer = a1;
      *(_QWORD *)(v20 + 8) = v17;
      *(_QWORD *)a1 = v17;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqZPd(WPP_GLOBAL_Control->AttachedDevice, v18, v19, v7);
      }
    }
    else
    {
      v15 = -1073741670;
    }
    if ( !v10 && (v15 & 0x80000000) == 0 )
      return v15;
  }
  if ( AuthDataCopy )
    SspiFreeAuthIdentity(AuthDataCopy);
  return v15;
}

```

## disassembly

```asm
0x140084dc4  mov     rax, rsp
0x140084dc7  mov     [rax+8], rbx
0x140084dcb  mov     [rax+18h], r8
0x140084dcf  push    rbp
0x140084dd0  push    rsi
0x140084dd1  push    rdi
0x140084dd2  push    r14
0x140084dd4  push    r15
0x140084dd6  sub     rsp, 50h
0x140084dda  mov     qword ptr [rax+18h], 0
0x140084de2  mov     r15, r9
0x140084de5  mov     qword ptr [rax-38h], 0
0x140084ded  mov     rsi, rdx
0x140084df0  mov     qword ptr [rax+10h], 0
0x140084df8  mov     r14, rcx
0x140084dfb  test    rdx, rdx
0x140084dfe  jnz     short loc_140084E07
0x140084e00  xor     eax, eax
0x140084e02  jmp     loc_140084FE3
0x140084e07  mov     rax, [rdx+68h]
0x140084e0b  xor     ebp, ebp
0x140084e0d  mov     rcx, [rdx+80h]
0x140084e14  mov     rdi, [rdx+180h]
0x140084e1b  mov     qword ptr [rsp+78h+var_38.LowPart], rax
0x140084e20  mov     rax, [rdx+60h]
0x140084e24  mov     qword ptr [rsp+78h+SourceLuid.LowPart], rax
0x140084e2c  test    rcx, rcx
0x140084e2f  jz      loc_140084EB6
0x140084e35  mov     rcx, [rcx+8]; AuthData
0x140084e39  test    rcx, rcx
0x140084e3c  jz      short loc_140084EB6
0x140084e3e  lea     rdx, [rsp+78h+AuthDataCopy]; AuthDataCopy
0x140084e46  call    cs:__imp_SspiCopyAuthIdentity
0x140084e4d  nop     dword ptr [rax+rax+00h]
0x140084e52  mov     ebp, eax
0x140084e54  test    eax, eax
0x140084e56  jz      short loc_140084EB6
0x140084e58  mov     ecx, eax; SecStatus
0x140084e5a  call    cs:__imp_MapSecurityError
0x140084e61  nop     dword ptr [rax+rax+00h]
0x140084e66  mov     edi, eax
0x140084e68  mov     rcx, cs:WPP_GLOBAL_Control
0x140084e6f  lea     rax, WPP_GLOBAL_Control
0x140084e76  cmp     rcx, rax
0x140084e79  jz      loc_140084FC8
0x140084e7f  mov     edx, [rcx+2Ch]
0x140084e82  test    dl, 1
0x140084e85  jz      loc_140084FC8
0x140084e8b  cmp     byte ptr [rcx+29h], 1
0x140084e8f  jb      loc_140084FC8
0x140084e95  mov     rcx, [rcx+18h]
0x140084e99  lea     r8, WPP_48980f24b3dc39b8aaca68646dc5bd2a_Traceguids
0x140084ea0  mov     edx, 0Bh
0x140084ea5  mov     [rsp+78h+var_58], ebp
0x140084ea9  mov     r9d, edi
0x140084eac  call    WPP_SF_Dd
0x140084eb1  jmp     loc_140084FC8
0x140084eb6  movzx   edx, word ptr [r15]
0x140084eba  mov     ecx, 102h
0x140084ebf  add     rdx, 50h ; 'P'
0x140084ec3  mov     r8d, 6D536149h
0x140084ec9  call    cs:__imp_ExAllocatePool2
0x140084ed0  nop     dword ptr [rax+rax+00h]
0x140084ed5  mov     rbx, rax
0x140084ed8  test    rax, rax
0x140084edb  jnz     short loc_140084EE7
0x140084edd  mov     edi, 0C000009Ah
0x140084ee2  jmp     loc_140084FC0
0x140084ee7  add     rax, 50h ; 'P'
0x140084eeb  lea     rcx, [rbx+10h]; DestinationString
0x140084eef  mov     [rbx+18h], rax
0x140084ef3  mov     rdx, r15; SourceString
0x140084ef6  movzx   eax, word ptr [r15]
0x140084efa  mov     [rbx+12h], ax
0x140084efe  call    cs:__imp_RtlCopyUnicodeString
0x140084f05  nop     dword ptr [rax+rax+00h]
0x140084f0a  mov     eax, [rdi+48h]
0x140084f0d  lea     rcx, [rbx+40h]; DestinationLuid
0x140084f11  mov     [rbx+20h], eax
0x140084f14  lea     rdx, [rsp+78h+SourceLuid]; SourceLuid
0x140084f1c  mov     eax, [rsp+78h+arg_20]
0x140084f23  mov     [rbx+24h], eax
0x140084f26  mov     rax, [rsp+78h+arg_28]
0x140084f2e  mov     [rbx+30h], rax
0x140084f32  mov     dword ptr [rbx+28h], 1
0x140084f39  mov     rax, [rsp+78h+AuthDataCopy]
0x140084f41  mov     [rbx+38h], rax
0x140084f45  call    cs:__imp_RtlCopyLuid
0x140084f4c  nop     dword ptr [rax+rax+00h]
0x140084f51  lea     rcx, [rbx+48h]; DestinationLuid
0x140084f55  lea     rdx, [rsp+78h+var_38]; SourceLuid
0x140084f5a  call    cs:__imp_RtlCopyLuid
0x140084f61  nop     dword ptr [rax+rax+00h]
0x140084f66  mov     rax, [r14]
0x140084f69  cmp     [rax+8], r14
0x140084f6d  jz      short loc_140084F76
0x140084f6f  mov     ecx, 3
0x140084f74  int     29h; Win8: RtlFailFast(ecx)
0x140084f76  mov     [rbx], rax
0x140084f79  xor     edi, edi
0x140084f7b  mov     [rbx+8], r14
0x140084f7f  mov     [rax+8], rbx
0x140084f83  mov     [r14], rbx
0x140084f86  mov     rcx, cs:WPP_GLOBAL_Control
0x140084f8d  lea     rax, WPP_GLOBAL_Control
0x140084f94  cmp     rcx, rax
0x140084f97  jz      short loc_140084FC0
0x140084f99  mov     eax, [rcx+2Ch]
0x140084f9c  test    al, 1
0x140084f9e  jz      short loc_140084FC0
0x140084fa0  cmp     byte ptr [rcx+29h], 1
0x140084fa4  jb      short loc_140084FC0
0x140084fa6  mov     rax, [r14+78h]
0x140084faa  mov     r9, rsi
0x140084fad  mov     rcx, [rcx+18h]
0x140084fb1  mov     [rsp+78h+var_48], rax
0x140084fb6  mov     [rsp+78h+var_50], r15
0x140084fbb  call    WPP_SF_qqZPd
0x140084fc0  test    ebp, ebp
0x140084fc2  jnz     short loc_140084FC8
0x140084fc4  test    edi, edi
0x140084fc6  jns     short loc_140084FE1
0x140084fc8  mov     rcx, [rsp+78h+AuthDataCopy]; AuthData
0x140084fd0  test    rcx, rcx
0x140084fd3  jz      short loc_140084FE1
0x140084fd5  call    cs:__imp_SspiFreeAuthIdentity
0x140084fdc  nop     dword ptr [rax+rax+00h]
0x140084fe1  mov     eax, edi
0x140084fe3  mov     rbx, [rsp+78h+arg_0]
0x140084feb  add     rsp, 50h
0x140084fef  pop     r15
0x140084ff1  pop     r14
0x140084ff3  pop     rdi
0x140084ff4  pop     rsi
0x140084ff5  pop     rbp
0x140084ff6  retn
```
