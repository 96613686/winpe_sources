# DxgkIsGraphicsPartitionApplication

- ea: `0x1402588dc`
- end: `0x140258d1f`
- name: `DxgkIsGraphicsPartitionApplication`
- size: `1091`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1403b64d4`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1402588dc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140258cca`
- `ntoskrnl!ZwClose` at `0x140258cdb`
- `ntoskrnl!ZwClose` at `0x140258cca`
- `ntoskrnl!ZwClose` at `0x140258cdb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140258c30`
- `ntoskrnl!RtlInitUnicodeString` at `0x140258c30`
- `ntoskrnl!ZwOpenKey` at `0x140258c72`
- `ntoskrnl!ZwOpenKey` at `0x140258cb1`
- `ntoskrnl!ZwOpenKey` at `0x140258c72`
- `ntoskrnl!ZwOpenKey` at `0x140258cb1`
- `ntoskrnl!ExGetPreviousMode` at `0x14025890c`
- `ntoskrnl!ExGetPreviousMode` at `0x14025890c`
- `ntoskrnl!RtlCapabilityCheck` at `0x140258a91`
- `ntoskrnl!RtlCapabilityCheck` at `0x140258ab1`
- `ntoskrnl!RtlCapabilityCheck` at `0x140258a91`
- `ntoskrnl!RtlCapabilityCheck` at `0x140258ab1`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140258975`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140258afe`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140258975`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140258afe`
- `ntoskrnl!SeQueryInformationToken` at `0x140258991`
- `ntoskrnl!SeQueryInformationToken` at `0x140258991`
- `ntoskrnl!SeSecurityAttributePresent` at `0x1402589b9`
- `ntoskrnl!SeSecurityAttributePresent` at `0x1402589b9`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1402589f1`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1402589f1`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140258a09`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140258b3b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140258a09`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140258b3b`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140258b2a`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140258b2a`
- `watchdog!WdLogSingleEntry0` at `0x140258926`
- `watchdog!WdLogSingleEntry0` at `0x140258926`
- `watchdog!WdLogSingleEntry1` at `0x140258a21`
- `watchdog!WdLogSingleEntry1` at `0x140258a21`

## string_xrefs

- `0x140258c1f`: `\REGISTRY\MACHINE\OSDATA\Software\Microsoft\Durango\LiveSettings\HevcOverride`

## pseudocode

```c
char __fastcall DxgkIsGraphicsPartitionApplication(PEPROCESS Process)
{
  char v2; // si
  PACCESS_TOKEN v3; // rdi
  NTSTATUS v4; // eax
  int v5; // ebx
  char v6; // r12
  int v7; // r15d
  PACCESS_TOKEN v9; // rdi
  int v10; // ebx
  __int16 v11; // ax
  unsigned int v12; // r15d
  __int16 *v13; // rcx
  unsigned int v14; // r14d
  _WORD *i; // rdi
  char v16; // [rsp+50h] [rbp-B0h] BYREF
  char v17; // [rsp+51h] [rbp-AFh] BYREF
  _BYTE v18[6]; // [rsp+52h] [rbp-AEh] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v21; // [rsp+68h] [rbp-98h]
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  PVOID TokenInformation; // [rsp+78h] [rbp-88h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v26[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v27[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v28[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  _WORD Src[128]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v32[144]; // [rsp+200h] [rbp+100h] BYREF

  v2 = 1;
  if ( ExGetPreviousMode() != 1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1558;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"ExGetPreviousMode() == UserMode", 1558, 0, 0, 0, 0);
  }
  TokenInformation = 0;
  v3 = PsReferencePrimaryToken(Process);
  v4 = SeQueryInformationToken(v3, TokenIsAppContainer, &TokenInformation);
  v26[0] = 1441812;
  v5 = v4;
  v26[1] = L"WIN://BGKD";
  v6 = SeSecurityAttributePresent(v3, v26);
  v22 = 0;
  RtlQueryPackageClaims(v3, 0, 0, 0, 0, 0, &v22, 0);
  v7 = v22 & 5;
  PsDereferencePrimaryToken(v3);
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 1582;
    return 0;
  }
  if ( !TokenInformation && v7 != 5 || v6 == 1 )
    return 0;
  v27[0] = 1703960;
  v27[1] = L"hevcPlayback";
  v28[1] = L"expandedResources";
  v28[0] = 2359330;
  v16 = 0;
  v17 = 0;
  if ( v7 != 5 )
  {
    if ( (int)RtlCapabilityCheck(0, v27, &v16) < 0 )
      v16 = 0;
    if ( (int)RtlCapabilityCheck(0, v28, &v17) < 0 )
      v17 = 0;
  }
  if ( *((_BYTE *)DXGGLOBAL::GetGlobal() + 304896) )
  {
    if ( v16 )
      goto LABEL_33;
    if ( v17 )
      return 0;
    v24 = 256;
    v18[0] = 0;
    v9 = PsReferencePrimaryToken(Process);
    v10 = RtlQueryPackageIdentity(v9, Src, &v24, 0, 0, v18);
    PsDereferencePrimaryToken(v9);
    if ( v10 >= 0 && v18[0] )
    {
      v20 = 8519680;
      v21 = v32;
      v11 = Src[0];
      v12 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      if ( Src[0] != 95 )
      {
        v13 = Src;
        do
        {
          if ( !v11 )
            break;
          ++v13;
          v12 += 2;
          v11 = *v13;
        }
        while ( *v13 != 95 );
      }
      v14 = 0;
      for ( i = (_WORD *)((char *)&DestinationString.Buffer + v24 + 6); *i != 95 && i != Src; --i )
        v14 += 2;
      if ( (unsigned __int64)(v14 + v12) + 2 <= 0x82 )
      {
        KeyHandle = 0;
        DestinationString = 0;
        memmove(v32, Src, v12);
        memmove(&v21[v12], i, v14 + 2LL);
        LOWORD(v20) = v12 + v14;
        RtlInitUnicodeString(
          &DestinationString,
          L"\\REGISTRY\\MACHINE\\OSDATA\\Software\\Microsoft\\Durango\\LiveSettings\\HevcOverride");
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
        {
          ObjectAttributes.RootDirectory = KeyHandle;
          Handle = 0;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20;
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
          {
            v16 = 1;
            ZwClose(Handle);
          }
          ZwClose(KeyHandle);
        }
      }
    }
  }
  if ( !v16 )
    return 0;
LABEL_33:
  if ( v17 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x1402588dc  push    rbp
0x1402588de  push    rbx
0x1402588df  push    rsi
0x1402588e0  push    rdi
0x1402588e1  push    r12
0x1402588e3  push    r13
0x1402588e5  push    r14
0x1402588e7  push    r15
0x1402588e9  lea     rbp, [rsp-1A8h]
0x1402588f1  sub     rsp, 2A8h
0x1402588f8  mov     rax, cs:__security_cookie
0x1402588ff  xor     rax, rsp
0x140258902  mov     [rbp+1E0h+var_50], rax
0x140258909  mov     r14, rcx
0x14025890c  call    cs:__imp_ExGetPreviousMode
0x140258913  nop     dword ptr [rax+rax+00h]
0x140258918  xor     r13d, r13d
0x14025891b  lea     esi, [r13+1]
0x14025891f  cmp     al, sil
0x140258922  jz      short loc_14025896D
0x140258924  mov     ecx, esi
0x140258926  call    cs:__imp_WdLogSingleEntry0
0x14025892d  nop     dword ptr [rax+rax+00h]
0x140258932  mov     [rsp+2E0h+var_2A0], r13
0x140258937  lea     r9, aExgetpreviousm; "ExGetPreviousMode() == UserMode"
0x14025893e  mov     [rsp+2E0h+var_2A8], r13
0x140258943  mov     eax, 616h
0x140258948  mov     [rsp+2E0h+var_2B0], r13
0x14025894d  or      r8d, 0FFFFFFFFh
0x140258951  mov     [rsp+2E0h+var_2B8], r13
0x140258956  mov     edx, 40002h
0x14025895b  xor     ecx, ecx
0x14025895d  mov     [rsp+2E0h+var_2C0], rax
0x140258962  mov     cs:WdLogGlobalForLineNumber, eax
0x140258968  call    DxgkLogInternalTriageEvent
0x14025896d  mov     rcx, r14; Process
0x140258970  mov     [rsp+2E0h+TokenInformation], r13
0x140258975  call    cs:__imp_PsReferencePrimaryToken
0x14025897c  nop     dword ptr [rax+rax+00h]
0x140258981  lea     r8, [rsp+2E0h+TokenInformation]; TokenInformation
0x140258986  mov     edx, 1Dh; TokenInformationClass
0x14025898b  mov     rcx, rax; Token
0x14025898e  mov     rdi, rax
0x140258991  call    cs:__imp_SeQueryInformationToken
0x140258998  nop     dword ptr [rax+rax+00h]
0x14025899d  lea     rdx, [rbp+1E0h+var_250]
0x1402589a1  mov     [rbp+1E0h+var_250], 160014h
0x1402589a9  mov     ebx, eax
0x1402589ab  mov     rcx, rdi
0x1402589ae  lea     rax, aWinBgkd; "WIN://BGKD"
0x1402589b5  mov     [rbp+1E0h+var_248], rax
0x1402589b9  call    cs:__imp_SeSecurityAttributePresent
0x1402589c0  nop     dword ptr [rax+rax+00h]
0x1402589c5  mov     [rsp+2E0h+var_2A8], r13
0x1402589ca  xor     r9d, r9d
0x1402589cd  mov     r12b, al
0x1402589d0  mov     [rsp+2E0h+var_270], r13
0x1402589d5  lea     rax, [rsp+2E0h+var_270]
0x1402589da  xor     r8d, r8d
0x1402589dd  mov     [rsp+2E0h+var_2B0], rax
0x1402589e2  xor     edx, edx
0x1402589e4  mov     [rsp+2E0h+var_2B8], r13
0x1402589e9  mov     rcx, rdi
0x1402589ec  mov     [rsp+2E0h+var_2C0], r13
0x1402589f1  call    cs:__imp_RtlQueryPackageClaims
0x1402589f8  nop     dword ptr [rax+rax+00h]
0x1402589fd  mov     r15d, dword ptr [rsp+2E0h+var_270]
0x140258a02  mov     rcx, rdi; PrimaryToken
0x140258a05  and     r15d, 5
0x140258a09  call    cs:__imp_PsDereferencePrimaryToken
0x140258a10  nop     dword ptr [rax+rax+00h]
0x140258a15  test    ebx, ebx
0x140258a17  jns     short loc_140258A3E
0x140258a19  mov     rdx, r14
0x140258a1c  mov     ecx, 3
0x140258a21  call    cs:__imp_WdLogSingleEntry1
0x140258a28  nop     dword ptr [rax+rax+00h]
0x140258a2d  mov     cs:WdLogGlobalForLineNumber, 62Eh
0x140258a37  xor     al, al
0x140258a39  jmp     loc_140258CFB
0x140258a3e  cmp     [rsp+2E0h+TokenInformation], r13
0x140258a43  jnz     short loc_140258A4B
0x140258a45  cmp     r15d, 5
0x140258a49  jnz     short loc_140258A37
0x140258a4b  cmp     r12b, sil
0x140258a4e  jz      short loc_140258A37
0x140258a50  mov     [rbp+1E0h+var_240], 1A0018h
0x140258a58  lea     rax, aHevcplayback; "hevcPlayback"
0x140258a5f  mov     [rbp+1E0h+var_238], rax
0x140258a63  lea     rax, aExpandedresour; "expandedResources"
0x140258a6a  mov     [rbp+1E0h+var_228], rax
0x140258a6e  mov     [rbp+1E0h+var_230], 240022h
0x140258a76  mov     [rsp+2E0h+var_290], r13b
0x140258a7b  mov     [rsp+2E0h+var_28F], r13b
0x140258a80  cmp     r15d, 5
0x140258a84  jz      short loc_140258AC6
0x140258a86  lea     r8, [rsp+2E0h+var_290]
0x140258a8b  xor     ecx, ecx
0x140258a8d  lea     rdx, [rbp+1E0h+var_240]
0x140258a91  call    cs:__imp_RtlCapabilityCheck
0x140258a98  nop     dword ptr [rax+rax+00h]
0x140258a9d  test    eax, eax
0x140258a9f  jns     short loc_140258AA6
0x140258aa1  mov     [rsp+2E0h+var_290], r13b
0x140258aa6  lea     r8, [rsp+2E0h+var_28F]
0x140258aab  xor     ecx, ecx
0x140258aad  lea     rdx, [rbp+1E0h+var_230]
0x140258ab1  call    cs:__imp_RtlCapabilityCheck
0x140258ab8  nop     dword ptr [rax+rax+00h]
0x140258abd  test    eax, eax
0x140258abf  jns     short loc_140258AC6
0x140258ac1  mov     [rsp+2E0h+var_28F], r13b
0x140258ac6  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140258acb  cmp     [rax+4A700h], r13b
0x140258ad2  jz      loc_140258CE7
0x140258ad8  cmp     [rsp+2E0h+var_290], r13b
0x140258add  jnz     loc_140258CEE
0x140258ae3  cmp     [rsp+2E0h+var_28F], r13b
0x140258ae8  jnz     loc_140258CF5
0x140258aee  mov     rcx, r14; Process
0x140258af1  mov     [rbp+1E0h+var_260], 100h
0x140258af9  mov     [rsp+2E0h+var_28E], r13b
0x140258afe  call    cs:__imp_PsReferencePrimaryToken
0x140258b05  nop     dword ptr [rax+rax+00h]
0x140258b0a  xor     r9d, r9d
0x140258b0d  lea     r8, [rbp+1E0h+var_260]
0x140258b11  mov     rdi, rax
0x140258b14  lea     rdx, [rbp+1E0h+Src]
0x140258b18  lea     rax, [rsp+2E0h+var_28E]
0x140258b1d  mov     rcx, rdi
0x140258b20  mov     [rsp+2E0h+var_2B8], rax
0x140258b25  mov     [rsp+2E0h+var_2C0], r13
0x140258b2a  call    cs:__imp_RtlQueryPackageIdentity
0x140258b31  nop     dword ptr [rax+rax+00h]
0x140258b36  mov     rcx, rdi; PrimaryToken
0x140258b39  mov     ebx, eax
0x140258b3b  call    cs:__imp_PsDereferencePrimaryToken
0x140258b42  nop     dword ptr [rax+rax+00h]
0x140258b47  test    ebx, ebx
0x140258b49  js      loc_140258CE7
0x140258b4f  cmp     [rsp+2E0h+var_28E], r13b
0x140258b54  jz      loc_140258CE7
0x140258b5a  xorps   xmm0, xmm0
0x140258b5d  mov     [rsp+2E0h+var_280], 820000h
0x140258b66  lea     rax, [rbp+1E0h+var_E0]
0x140258b6d  mov     dx, 5Fh ; '_'
0x140258b71  mov     [rsp+2E0h+var_278], rax
0x140258b76  mov     r8d, 82h
0x140258b7c  movzx   eax, [rbp+1E0h+Src]
0x140258b80  mov     r15d, r13d
0x140258b83  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.Length], xmm0
0x140258b87  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.ObjectName], xmm0
0x140258b8b  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140258b8f  cmp     ax, dx
0x140258b92  jz      short loc_140258BAD
0x140258b94  lea     rcx, [rbp+1E0h+Src]
0x140258b98  test    ax, ax
0x140258b9b  jz      short loc_140258BAD
0x140258b9d  add     rcx, 2
0x140258ba1  add     r15d, 2
0x140258ba5  movzx   eax, word ptr [rcx]
0x140258ba8  cmp     ax, dx
0x140258bab  jnz     short loc_140258B98
0x140258bad  mov     rax, [rbp+1E0h+var_260]
0x140258bb1  mov     r14d, r13d
0x140258bb4  lea     rdi, [rbp+rax+1E0h+DestinationString.Buffer+6]
0x140258bb9  jmp     short loc_140258BCC
0x140258bbb  lea     rax, [rbp+1E0h+Src]
0x140258bbf  cmp     rdi, rax
0x140258bc2  jz      short loc_140258BD1
0x140258bc4  add     r14d, 2
0x140258bc8  sub     rdi, 2
0x140258bcc  cmp     [rdi], dx
0x140258bcf  jnz     short loc_140258BBB
0x140258bd1  lea     ecx, [r14+r15]
0x140258bd5  add     rcx, 2
0x140258bd9  cmp     rcx, r8
0x140258bdc  ja      loc_140258CE7
0x140258be2  xorps   xmm0, xmm0
0x140258be5  mov     r8d, r15d; Size
0x140258be8  lea     rdx, [rbp+1E0h+Src]; Src
0x140258bec  mov     [rsp+2E0h+KeyHandle], r13
0x140258bf1  lea     rcx, [rbp+1E0h+var_E0]; void *
0x140258bf8  mov     ebx, r15d
0x140258bfb  movups  xmmword ptr [rbp-10h], xmm0
0x140258bff  call    memmove
0x140258c04  mov     rcx, [rsp+2E0h+var_278]
0x140258c09  mov     rdx, rdi; Src
0x140258c0c  mov     r8d, r14d
0x140258c0f  add     rcx, rbx; void *
0x140258c12  add     r8, 2; Size
0x140258c16  call    memmove
0x140258c1b  add     r14w, r15w
0x140258c1f  lea     rdx, aRegistryMachin_10; "\\REGISTRY\\MACHINE\\OSDATA\\Software\\"...
0x140258c26  lea     rcx, [rbp+1E0h+DestinationString]; DestinationString
0x140258c2a  mov     word ptr [rsp+2E0h+var_280], r14w
0x140258c30  call    cs:__imp_RtlInitUnicodeString
0x140258c37  nop     dword ptr [rax+rax+00h]
0x140258c3c  lea     rax, [rbp+1E0h+DestinationString]
0x140258c40  mov     [rbp+1E0h+ObjectAttributes.RootDirectory], r13
0x140258c44  xorps   xmm0, xmm0
0x140258c47  mov     [rbp+1E0h+ObjectAttributes.ObjectName], rax
0x140258c4b  mov     r14d, 20019h
0x140258c51  lea     r8, [rbp+1E0h+ObjectAttributes]; ObjectAttributes
0x140258c55  mov     ebx, 30h ; '0'
0x140258c5a  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x140258c5f  mov     edi, 240h
0x140258c64  mov     [rbp+1E0h+ObjectAttributes.Length], ebx
0x140258c67  mov     edx, r14d; DesiredAccess
0x140258c6a  mov     [rbp+1E0h+ObjectAttributes.Attributes], edi
0x140258c6d  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140258c72  call    cs:__imp_ZwOpenKey
0x140258c79  nop     dword ptr [rax+rax+00h]
0x140258c7e  test    eax, eax
0x140258c80  js      short loc_140258CE7
0x140258c82  mov     rax, [rsp+2E0h+KeyHandle]
0x140258c87  lea     r8, [rbp+1E0h+ObjectAttributes]; ObjectAttributes
0x140258c8b  mov     [rbp+1E0h+ObjectAttributes.RootDirectory], rax
0x140258c8f  lea     rcx, [rbp+1E0h+Handle]; KeyHandle
0x140258c93  lea     rax, [rsp+2E0h+var_280]
0x140258c98  mov     [rbp+1E0h+Handle], r13
0x140258c9c  xorps   xmm0, xmm0
0x140258c9f  mov     [rbp+1E0h+ObjectAttributes.ObjectName], rax
0x140258ca3  mov     edx, r14d; DesiredAccess
0x140258ca6  mov     [rbp+1E0h+ObjectAttributes.Length], ebx
0x140258ca9  mov     [rbp+1E0h+ObjectAttributes.Attributes], edi
0x140258cac  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140258cb1  call    cs:__imp_ZwOpenKey
0x140258cb8  nop     dword ptr [rax+rax+00h]
0x140258cbd  test    eax, eax
0x140258cbf  js      short loc_140258CD6
0x140258cc1  mov     rcx, [rbp+1E0h+Handle]; Handle
0x140258cc5  mov     [rsp+2E0h+var_290], sil
0x140258cca  call    cs:__imp_ZwClose
0x140258cd1  nop     dword ptr [rax+rax+00h]
0x140258cd6  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x140258cdb  call    cs:__imp_ZwClose
0x140258ce2  nop     dword ptr [rax+rax+00h]
0x140258ce7  cmp     [rsp+2E0h+var_290], r13b
0x140258cec  jz      short loc_140258CF5
0x140258cee  cmp     [rsp+2E0h+var_28F], r13b
0x140258cf3  jz      short loc_140258CF8
0x140258cf5  mov     sil, r13b
0x140258cf8  mov     al, sil
0x140258cfb  mov     rcx, [rbp+1E0h+var_50]
0x140258d02  xor     rcx, rsp; StackCookie
0x140258d05  call    __security_check_cookie
0x140258d0a  add     rsp, 2A8h
0x140258d11  pop     r15
0x140258d13  pop     r14
0x140258d15  pop     r13
0x140258d17  pop     r12
0x140258d19  pop     rdi
0x140258d1a  pop     rsi
0x140258d1b  pop     rbx
0x140258d1c  pop     rbp
0x140258d1d  retn
```
