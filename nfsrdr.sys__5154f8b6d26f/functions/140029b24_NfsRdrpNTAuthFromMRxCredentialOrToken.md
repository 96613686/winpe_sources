# NfsRdrpNTAuthFromMRxCredentialOrToken

- ea: `0x140029b24`
- end: `0x140029df2`
- name: `NfsRdrpNTAuthFromMRxCredentialOrToken`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140025be0`

## callees

- `0x140018310`
- `0x14001db18`
- `0x140020fa8`
- `0x1400219e8`
- `0x140028f00`
- `0x140029104`
- `0x140029b24`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029c5a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029c91`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029c5a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140029c91`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029c77`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140029c77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029cdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029cdc`
- `ntoskrnl!ExAllocatePool2` at `0x140029c0a`
- `ntoskrnl!ExAllocatePool2` at `0x140029c0a`

## pseudocode

```c
__int64 __fastcall NfsRdrpNTAuthFromMRxCredentialOrToken(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        void **a5)
{
  __int16 *v9; // rax
  __int16 v10; // cx
  __int16 *v11; // rax
  __int16 v12; // ax
  int appended; // ebx
  _DWORD *v14; // r14
  char v15; // cl
  char v17; // [rsp+40h] [rbp-41h] BYREF
  _BYTE v18[3]; // [rsp+41h] [rbp-40h] BYREF
  int v19; // [rsp+44h] [rbp-3Dh] BYREF
  unsigned int v20; // [rsp+48h] [rbp-39h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-31h] BYREF
  char v22[40]; // [rsp+60h] [rbp-21h] BYREF

  strcpy(v22, "NfsRdrpNTAuthFromCredentialObject");
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids, v22);
  if ( a4
    && (v9 = *(__int16 **)(a4 + 16)) != 0
    && (v10 = *v9) != 0
    && (v11 = *(__int16 **)(a4 + 32)) != 0
    && (v12 = *v11) != 0 )
  {
    *(_QWORD *)&Destination.Length = 0;
    *(_DWORD *)&Destination.MaximumLength = (unsigned __int16)(v10 + 2 + v12);
    Destination.Buffer = (PWSTR)ExAllocatePool2(258, Destination.MaximumLength, 844260942);
    if ( Destination.Buffer )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, *(PCUNICODE_STRING *)(a4 + 32));
      if ( appended >= 0 )
      {
        appended = RtlAppendUnicodeToString(&Destination, L"\\");
        if ( appended >= 0 )
        {
          appended = RtlAppendUnicodeStringToString(&Destination, *(PCUNICODE_STRING *)(a4 + 16));
          if ( appended >= 0 )
          {
            appended = NfsRdrpGetUidGidFromPasswdGroup(a1, a4, a5, (__int64)(a3 + 9));
            if ( appended < 0 )
              appended = MapGetUnixCredsFromNTUserName(*(_QWORD *)(a2 + 32), (__int64)a3, &Destination, a3 + 9);
          }
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids, v22);
      appended = -1073741670;
    }
    if ( Destination.Buffer )
      ExFreePoolWithTag(Destination.Buffer, 0);
    v14 = a3 + 9;
  }
  else
  {
    v14 = a3 + 9;
    appended = NfsRdrpGetUidGidFromPasswdGroup(a1, a4, a5, (__int64)(a3 + 9));
    if ( appended >= 0 )
      goto LABEL_33;
    appended = MapGetUnixCredsFromSid(*(_QWORD *)(a2 + 32), (__int64)a3, *a5, a3 + 9);
  }
  if ( appended < 0 && (a3[44] & 1) != 0 )
  {
    v19 = 0;
    v20 = 0;
    v18[0] = 0;
    v17 = 0;
    a3[11] = 0;
    appended = NfsRdrpGetUidGidFromLdap(a1, (_QWORD *)a4, a5, (__int64)&v19, (__int64)&v20, (__int64)v18, (__int64)&v17);
    if ( appended >= 0 )
    {
      v15 = v17;
      if ( v18[0] )
      {
        *v14 = v19;
      }
      else if ( !v17 )
      {
        goto LABEL_33;
      }
      if ( v15 )
        a3[10] = v20;
    }
  }
LABEL_33:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_sD(
      WPP_GLOBAL_Control->AttachedDevice,
      76,
      (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
      (unsigned int)v22,
      appended);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140029b24  push    rbp
0x140029b26  push    rbx
0x140029b27  push    rsi
0x140029b28  push    rdi
0x140029b29  push    r12
0x140029b2b  push    r13
0x140029b2d  push    r14
0x140029b2f  push    r15
0x140029b31  lea     rbp, [rsp-17h]
0x140029b36  sub     rsp, 98h
0x140029b3d  mov     rax, cs:__security_cookie
0x140029b44  xor     rax, rsp
0x140029b47  mov     [rbp+4Fh+var_48], rax
0x140029b4b  movups  xmm0, xmmword ptr cs:aNfsrdrpntauthf; "NfsRdrpNTAuthFromCredentialObject"
0x140029b52  movzx   eax, word ptr cs:aNfsrdrpntauthf+20h; "t"
0x140029b59  mov     rdi, r9
0x140029b5c  movups  xmm1, xmmword ptr cs:aNfsrdrpntauthf+10h; "mCredentialObject"
0x140029b63  mov     r15, [rbp+4Fh+arg_20]
0x140029b67  mov     rsi, r8
0x140029b6a  movups  xmmword ptr [rbp+4Fh+var_70], xmm0
0x140029b6e  mov     r13, rdx
0x140029b71  mov     r12, rcx
0x140029b74  movups  xmmword ptr [rbp+4Fh+var_70+10h], xmm1
0x140029b78  mov     word ptr [rbp+4Fh+var_70+20h], ax
0x140029b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029b83  lea     rbx, WPP_GLOBAL_Control
0x140029b8a  cmp     rcx, rbx
0x140029b8d  jz      short loc_140029BAF
0x140029b8f  mov     eax, [rcx+2Ch]
0x140029b92  test    al, 8
0x140029b94  jz      short loc_140029BAF
0x140029b96  mov     rcx, [rcx+18h]
0x140029b9a  lea     r9, [rbp+4Fh+var_70]
0x140029b9e  mov     edx, 4Ah ; 'J'
0x140029ba3  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140029baa  call    WPP_SF_s
0x140029baf  test    rdi, rdi
0x140029bb2  jz      loc_140029CEE
0x140029bb8  mov     rax, [rdi+10h]
0x140029bbc  test    rax, rax
0x140029bbf  jz      loc_140029CEE
0x140029bc5  movzx   ecx, word ptr [rax]
0x140029bc8  test    cx, cx
0x140029bcb  jz      loc_140029CEE
0x140029bd1  mov     rax, [rdi+20h]
0x140029bd5  test    rax, rax
0x140029bd8  jz      loc_140029CEE
0x140029bde  movzx   eax, word ptr [rax]
0x140029be1  test    ax, ax
0x140029be4  jz      loc_140029CEE
0x140029bea  add     cx, 2
0x140029bee  xorps   xmm0, xmm0
0x140029bf1  add     ax, cx
0x140029bf4  mov     r8d, 3252664Eh
0x140029bfa  movzx   edx, ax
0x140029bfd  mov     ecx, 102h
0x140029c02  movups  xmmword ptr [rbp+4Fh+Destination.Length], xmm0
0x140029c06  mov     [rbp+4Fh+Destination.MaximumLength], dx
0x140029c0a  call    cs:__imp_ExAllocatePool2
0x140029c11  nop     dword ptr [rax+rax+00h]
0x140029c16  mov     [rbp+4Fh+Destination.Buffer], rax
0x140029c1a  test    rax, rax
0x140029c1d  jnz     short loc_140029C52
0x140029c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029c26  cmp     rcx, rbx
0x140029c29  jz      short loc_140029C4B
0x140029c2b  mov     eax, [rcx+2Ch]
0x140029c2e  test    al, 1
0x140029c30  jz      short loc_140029C4B
0x140029c32  mov     rcx, [rcx+18h]
0x140029c36  lea     r9, [rbp+4Fh+var_70]
0x140029c3a  mov     edx, 4Bh ; 'K'
0x140029c3f  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140029c46  call    WPP_SF_s
0x140029c4b  mov     ebx, 0C000009Ah
0x140029c50  jmp     short loc_140029CD1
0x140029c52  mov     rdx, [rdi+20h]; Source
0x140029c56  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140029c5a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140029c61  nop     dword ptr [rax+rax+00h]
0x140029c66  mov     ebx, eax
0x140029c68  test    eax, eax
0x140029c6a  js      short loc_140029CD1
0x140029c6c  lea     rdx, Source; "\\"
0x140029c73  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140029c77  call    cs:__imp_RtlAppendUnicodeToString
0x140029c7e  nop     dword ptr [rax+rax+00h]
0x140029c83  mov     ebx, eax
0x140029c85  test    eax, eax
0x140029c87  js      short loc_140029CD1
0x140029c89  mov     rdx, [rdi+10h]; Source
0x140029c8d  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140029c91  call    cs:__imp_RtlAppendUnicodeStringToString
0x140029c98  nop     dword ptr [rax+rax+00h]
0x140029c9d  mov     ebx, eax
0x140029c9f  test    eax, eax
0x140029ca1  js      short loc_140029CD1
0x140029ca3  lea     r9, [rsi+24h]
0x140029ca7  mov     r8, r15
0x140029caa  mov     rdx, rdi
0x140029cad  mov     rcx, r12
0x140029cb0  call    NfsRdrpGetUidGidFromPasswdGroup
0x140029cb5  mov     ebx, eax
0x140029cb7  test    eax, eax
0x140029cb9  jns     short loc_140029CD1
0x140029cbb  mov     rcx, [r13+20h]
0x140029cbf  lea     r9, [rsi+24h]
0x140029cc3  lea     r8, [rbp+4Fh+Destination]
0x140029cc7  mov     rdx, rsi
0x140029cca  call    MapGetUnixCredsFromNTUserName
0x140029ccf  mov     ebx, eax
0x140029cd1  mov     rcx, [rbp+4Fh+Destination.Buffer]; P
0x140029cd5  test    rcx, rcx
0x140029cd8  jz      short loc_140029CE8
0x140029cda  xor     edx, edx; Tag
0x140029cdc  call    cs:__imp_ExFreePoolWithTag
0x140029ce3  nop     dword ptr [rax+rax+00h]
0x140029ce8  lea     r14, [rsi+24h]
0x140029cec  jmp     short loc_140029D21
0x140029cee  lea     r14, [rsi+24h]
0x140029cf2  mov     r8, r15
0x140029cf5  mov     r9, r14
0x140029cf8  mov     rdx, rdi
0x140029cfb  mov     rcx, r12
0x140029cfe  call    NfsRdrpGetUidGidFromPasswdGroup
0x140029d03  mov     ebx, eax
0x140029d05  test    eax, eax
0x140029d07  jns     loc_140029D98
0x140029d0d  mov     r8, [r15]
0x140029d10  mov     r9, r14
0x140029d13  mov     rcx, [r13+20h]
0x140029d17  mov     rdx, rsi
0x140029d1a  call    MapGetUnixCredsFromSid
0x140029d1f  mov     ebx, eax
0x140029d21  xor     r13d, r13d
0x140029d24  test    ebx, ebx
0x140029d26  jns     short loc_140029D98
0x140029d28  mov     eax, [rsi+0B0h]
0x140029d2e  test    al, 1
0x140029d30  jz      short loc_140029D98
0x140029d32  lea     rax, [rbp+4Fh+var_90]
0x140029d36  mov     [rbp+4Fh+var_8C], r13d
0x140029d3a  mov     [rsp+0D0h+var_A0], rax
0x140029d3f  lea     r9, [rbp+4Fh+var_8C]
0x140029d43  lea     rax, [rbp+4Fh+var_8F]
0x140029d47  mov     [rbp+4Fh+var_88], r13d
0x140029d4b  mov     [rsp+0D0h+var_A8], rax
0x140029d50  mov     r8, r15
0x140029d53  lea     rax, [rbp+4Fh+var_88]
0x140029d57  mov     [rbp+4Fh+var_8F], r13b
0x140029d5b  mov     rdx, rdi
0x140029d5e  mov     [rsp+0D0h+var_B0], rax
0x140029d63  mov     rcx, r12
0x140029d66  mov     [rbp+4Fh+var_90], r13b
0x140029d6a  mov     [rsi+2Ch], r13d
0x140029d6e  call    NfsRdrpGetUidGidFromLdap
0x140029d73  mov     ebx, eax
0x140029d75  test    eax, eax
0x140029d77  js      short loc_140029D98
0x140029d79  mov     cl, [rbp+4Fh+var_90]
0x140029d7c  cmp     [rbp+4Fh+var_8F], r13b
0x140029d80  jnz     short loc_140029D88
0x140029d82  test    cl, cl
0x140029d84  jz      short loc_140029D98
0x140029d86  jmp     short loc_140029D8E
0x140029d88  mov     eax, [rbp+4Fh+var_8C]
0x140029d8b  mov     [r14], eax
0x140029d8e  test    cl, cl
0x140029d90  jz      short loc_140029D98
0x140029d92  mov     eax, [rbp+4Fh+var_88]
0x140029d95  mov     [rsi+28h], eax
0x140029d98  mov     rcx, cs:WPP_GLOBAL_Control
0x140029d9f  lea     rax, WPP_GLOBAL_Control
0x140029da6  cmp     rcx, rax
0x140029da9  jz      short loc_140029DCF
0x140029dab  mov     eax, [rcx+2Ch]
0x140029dae  test    al, 8
0x140029db0  jz      short loc_140029DCF
0x140029db2  mov     rcx, [rcx+18h]
0x140029db6  lea     r9, [rbp+4Fh+var_70]
0x140029dba  mov     edx, 4Ch ; 'L'
0x140029dbf  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x140029dc3  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140029dca  call    WPP_SF_sD
0x140029dcf  mov     eax, ebx
0x140029dd1  mov     rcx, [rbp+4Fh+var_48]
0x140029dd5  xor     rcx, rsp; StackCookie
0x140029dd8  call    __security_check_cookie
0x140029ddd  add     rsp, 98h
0x140029de4  pop     r15
0x140029de6  pop     r14
0x140029de8  pop     r13
0x140029dea  pop     r12
0x140029dec  pop     rdi
0x140029ded  pop     rsi
0x140029dee  pop     rbx
0x140029def  pop     rbp
0x140029df0  retn
```
