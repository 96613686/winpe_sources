# SmbCeAllocateNewInvalidAuthEntry

- ea: `0x140084e14`
- end: `0x140085048`
- name: `SmbCeAllocateNewInvalidAuthEntry`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140090750`

## callees

- `0x140039fd8`
- `0x14004c720`
- `0x140084e14`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140084f4e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140084f4e`
- `ntoskrnl!RtlCopyLuid` at `0x140084f95`
- `ntoskrnl!RtlCopyLuid` at `0x140084faa`
- `ntoskrnl!RtlCopyLuid` at `0x140084f95`
- `ntoskrnl!RtlCopyLuid` at `0x140084faa`
- `ntoskrnl!ExAllocatePool2` at `0x140084f19`
- `ntoskrnl!ExAllocatePool2` at `0x140084f19`
- `ksecdd!SspiCopyAuthIdentity` at `0x140084e96`
- `ksecdd!SspiCopyAuthIdentity` at `0x140084e96`
- `ksecdd!MapSecurityError` at `0x140084eaa`
- `ksecdd!MapSecurityError` at `0x140084eaa`
- `ksecdd!SspiFreeAuthIdentity` at `0x140085025`
- `ksecdd!SspiFreeAuthIdentity` at `0x140085025`

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
0x140084e14  mov     rax, rsp
0x140084e17  mov     [rax+8], rbx
0x140084e1b  mov     [rax+18h], r8
0x140084e1f  push    rbp
0x140084e20  push    rsi
0x140084e21  push    rdi
0x140084e22  push    r14
0x140084e24  push    r15
0x140084e26  sub     rsp, 50h
0x140084e2a  mov     qword ptr [rax+18h], 0
0x140084e32  mov     r15, r9
0x140084e35  mov     qword ptr [rax-38h], 0
0x140084e3d  mov     rsi, rdx
0x140084e40  mov     qword ptr [rax+10h], 0
0x140084e48  mov     r14, rcx
0x140084e4b  test    rdx, rdx
0x140084e4e  jnz     short loc_140084E57
0x140084e50  xor     eax, eax
0x140084e52  jmp     loc_140085033
0x140084e57  mov     rax, [rdx+68h]
0x140084e5b  xor     ebp, ebp
0x140084e5d  mov     rcx, [rdx+80h]
0x140084e64  mov     rdi, [rdx+180h]
0x140084e6b  mov     qword ptr [rsp+78h+var_38.LowPart], rax
0x140084e70  mov     rax, [rdx+60h]
0x140084e74  mov     qword ptr [rsp+78h+SourceLuid.LowPart], rax
0x140084e7c  test    rcx, rcx
0x140084e7f  jz      loc_140084F06
0x140084e85  mov     rcx, [rcx+8]; AuthData
0x140084e89  test    rcx, rcx
0x140084e8c  jz      short loc_140084F06
0x140084e8e  lea     rdx, [rsp+78h+AuthDataCopy]; AuthDataCopy
0x140084e96  call    cs:__imp_SspiCopyAuthIdentity
0x140084e9d  nop     dword ptr [rax+rax+00h]
0x140084ea2  mov     ebp, eax
0x140084ea4  test    eax, eax
0x140084ea6  jz      short loc_140084F06
0x140084ea8  mov     ecx, eax; SecStatus
0x140084eaa  call    cs:__imp_MapSecurityError
0x140084eb1  nop     dword ptr [rax+rax+00h]
0x140084eb6  mov     edi, eax
0x140084eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140084ebf  lea     rax, WPP_GLOBAL_Control
0x140084ec6  cmp     rcx, rax
0x140084ec9  jz      loc_140085018
0x140084ecf  mov     edx, [rcx+2Ch]
0x140084ed2  test    dl, 1
0x140084ed5  jz      loc_140085018
0x140084edb  cmp     byte ptr [rcx+29h], 1
0x140084edf  jb      loc_140085018
0x140084ee5  mov     rcx, [rcx+18h]
0x140084ee9  lea     r8, WPP_48980f24b3dc39b8aaca68646dc5bd2a_Traceguids
0x140084ef0  mov     edx, 0Bh
0x140084ef5  mov     [rsp+78h+var_58], ebp
0x140084ef9  mov     r9d, edi
0x140084efc  call    WPP_SF_Dd
0x140084f01  jmp     loc_140085018
0x140084f06  movzx   edx, word ptr [r15]
0x140084f0a  mov     ecx, 102h
0x140084f0f  add     rdx, 50h ; 'P'
0x140084f13  mov     r8d, 6D536149h
0x140084f19  call    cs:__imp_ExAllocatePool2
0x140084f20  nop     dword ptr [rax+rax+00h]
0x140084f25  mov     rbx, rax
0x140084f28  test    rax, rax
0x140084f2b  jnz     short loc_140084F37
0x140084f2d  mov     edi, 0C000009Ah
0x140084f32  jmp     loc_140085010
0x140084f37  add     rax, 50h ; 'P'
0x140084f3b  lea     rcx, [rbx+10h]; DestinationString
0x140084f3f  mov     [rbx+18h], rax
0x140084f43  mov     rdx, r15; SourceString
0x140084f46  movzx   eax, word ptr [r15]
0x140084f4a  mov     [rbx+12h], ax
0x140084f4e  call    cs:__imp_RtlCopyUnicodeString
0x140084f55  nop     dword ptr [rax+rax+00h]
0x140084f5a  mov     eax, [rdi+48h]
0x140084f5d  lea     rcx, [rbx+40h]; DestinationLuid
0x140084f61  mov     [rbx+20h], eax
0x140084f64  lea     rdx, [rsp+78h+SourceLuid]; SourceLuid
0x140084f6c  mov     eax, [rsp+78h+arg_20]
0x140084f73  mov     [rbx+24h], eax
0x140084f76  mov     rax, [rsp+78h+arg_28]
0x140084f7e  mov     [rbx+30h], rax
0x140084f82  mov     dword ptr [rbx+28h], 1
0x140084f89  mov     rax, [rsp+78h+AuthDataCopy]
0x140084f91  mov     [rbx+38h], rax
0x140084f95  call    cs:__imp_RtlCopyLuid
0x140084f9c  nop     dword ptr [rax+rax+00h]
0x140084fa1  lea     rcx, [rbx+48h]; DestinationLuid
0x140084fa5  lea     rdx, [rsp+78h+var_38]; SourceLuid
0x140084faa  call    cs:__imp_RtlCopyLuid
0x140084fb1  nop     dword ptr [rax+rax+00h]
0x140084fb6  mov     rax, [r14]
0x140084fb9  cmp     [rax+8], r14
0x140084fbd  jz      short loc_140084FC6
0x140084fbf  mov     ecx, 3
0x140084fc4  int     29h; Win8: RtlFailFast(ecx)
0x140084fc6  mov     [rbx], rax
0x140084fc9  xor     edi, edi
0x140084fcb  mov     [rbx+8], r14
0x140084fcf  mov     [rax+8], rbx
0x140084fd3  mov     [r14], rbx
0x140084fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140084fdd  lea     rax, WPP_GLOBAL_Control
0x140084fe4  cmp     rcx, rax
0x140084fe7  jz      short loc_140085010
0x140084fe9  mov     eax, [rcx+2Ch]
0x140084fec  test    al, 1
0x140084fee  jz      short loc_140085010
0x140084ff0  cmp     byte ptr [rcx+29h], 1
0x140084ff4  jb      short loc_140085010
0x140084ff6  mov     rax, [r14+78h]
0x140084ffa  mov     r9, rsi
0x140084ffd  mov     rcx, [rcx+18h]
0x140085001  mov     [rsp+78h+var_48], rax
0x140085006  mov     [rsp+78h+var_50], r15
0x14008500b  call    WPP_SF_qqZPd
0x140085010  test    ebp, ebp
0x140085012  jnz     short loc_140085018
0x140085014  test    edi, edi
0x140085016  jns     short loc_140085031
0x140085018  mov     rcx, [rsp+78h+AuthDataCopy]; AuthData
0x140085020  test    rcx, rcx
0x140085023  jz      short loc_140085031
0x140085025  call    cs:__imp_SspiFreeAuthIdentity
0x14008502c  nop     dword ptr [rax+rax+00h]
0x140085031  mov     eax, edi
0x140085033  mov     rbx, [rsp+78h+arg_0]
0x14008503b  add     rsp, 50h
0x14008503f  pop     r15
0x140085041  pop     r14
0x140085043  pop     rdi
0x140085044  pop     rsi
0x140085045  pop     rbp
0x140085046  retn
```
