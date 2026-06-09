# SPSslFreeObject

- ea: `0x180045c90`
- end: `0x180045f2e`
- name: `SPSslFreeObject`
- size: `670`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006470`
- `0x1800082b0`
- `0x180035540`
- `0x180045c90`
- `0x180082324`
- `0x180083f94`
- `0x180084174`
- `0x180084550`
- `0x1800849e0`
- `0x180084e1c`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180045d83`
- `ntoskrnl!RtlInitUnicodeString` at `0x180045d83`
- `ntoskrnl!ZwQueryValueKey` at `0x180045db4`
- `ntoskrnl!ZwQueryValueKey` at `0x180045db4`
- `ntoskrnl!ZwClose` at `0x180045de6`
- `ntoskrnl!ZwClose` at `0x180045de6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180045cb8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180045cb8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180045ccd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180045ccd`
- `ntoskrnl!ExReleaseResourceLite` at `0x180045e40`
- `ntoskrnl!ExReleaseResourceLite` at `0x180045e40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180045e4c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180045e4c`
- `ntoskrnl!SkIsSecureKernel` at `0x180045cf8`
- `ntoskrnl!SkIsSecureKernel` at `0x180045cf8`

## string_xrefs

- `0x180045e99`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180045d3c`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider`

## pseudocode

```c
__int64 __fastcall SPSslFreeObject(unsigned int *P, int a2, int a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  BOOL v7; // esi
  HANDLE v8; // rbx
  void *v10; // rcx
  __int64 v11; // rcx
  _BYTE *v12; // rax
  __int64 v13; // rdx
  _BYTE *v14; // rax
  HANDLE KeyHandle; // [rsp+40h] [rbp-58h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-48h] BYREF
  int KeyValueInformation; // [rsp+60h] [rbp-38h] BYREF
  __int128 v19; // [rsp+64h] [rbp-34h]

  if ( !dword_1800CC0A4 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_1800CC0A4 )
    {
      LOBYTE(v6) = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
      {
        v6 = ((int)SkIsSecureKernel(v5, v4) >> 31) + 2;
        g_TrustedEnvironment = v6;
      }
      if ( (v6 & 2) == 0 )
      {
        KeyHandle = 0;
        v7 = 0;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol Provider",
                    0,
                    &KeyHandle) >= 0 )
        {
          v8 = KeyHandle;
          ResultLength = 0;
          KeyValueInformation = 0;
          DestinationString = 0;
          v19 = 0;
          RtlInitUnicodeString(
            &DestinationString,
            (PCWSTR)"E\x00n\x00a\x00b\x00l\x00e\x00T\x00l\x00s\x00E\x00x\x00t\x00e\x00r\x00n\x00a\x00l\x00A\x00l\x00g\x00o\x00r\x00i\x00t\x00h\x00m\x00s");
          if ( ZwQueryValueKey(
                 v8,
                 &DestinationString,
                 KeyValuePartialInformation,
                 &KeyValueInformation,
                 0x14u,
                 &ResultLength) >= 0
            && (_DWORD)v19 == 4 )
          {
            v7 = DWORD2(v19) == 1;
          }
        }
        if ( KeyHandle )
        {
          ZwClose(KeyHandle);
          KeyHandle = 0;
        }
        dword_1800CB7C4 = v7;
        if ( v7 )
        {
          GetExternalHashAlgorithms();
          GetExternalSignatureAlgorithms();
          GetExternalKeyExchangeAlgorithms();
          GetExternalCipherAlgorithms();
          GetExternalCipherSuites();
        }
      }
      dword_1800CC0A4 = 1;
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
  if ( !P )
    return 2148073511LL;
  if ( P[1] == 1936944177 )
  {
    v13 = 912;
    v14 = P;
    do
    {
      *v14++ = 0;
      --v13;
    }
    while ( v13 );
LABEL_31:
    MSCryptFree(P);
    return 0;
  }
  if ( P[1] == 1936944179 )
  {
    v10 = (void *)*((_QWORD *)P + 4);
    if ( v10 )
      BCryptDestroyKey(v10);
    v11 = *P;
    v12 = P;
    if ( *P )
    {
      do
      {
        *v12++ = 0;
        --v11;
      }
      while ( v11 );
    }
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      a2,
      a3,
      (unsigned int)"Status",
      2,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      44);
  return 3221225474LL;
}

```

## disassembly

```asm
0x180045c90  push    rdi
0x180045c92  sub     rsp, 90h
0x180045c99  mov     rax, cs:__security_cookie
0x180045ca0  xor     rax, rsp
0x180045ca3  mov     [rsp+98h+var_20], rax
0x180045ca8  cmp     cs:dword_1800CC0A4, 0
0x180045caf  mov     rdi, rcx
0x180045cb2  jnz     loc_180045E58
0x180045cb8  call    cs:__imp_KeEnterCriticalRegion
0x180045cbf  nop     dword ptr [rax+rax+00h]
0x180045cc4  mov     dl, 1; Wait
0x180045cc6  lea     rcx, Resource; Resource
0x180045ccd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180045cd4  nop     dword ptr [rax+rax+00h]
0x180045cd9  cmp     cs:dword_1800CC0A4, 0
0x180045ce0  jnz     loc_180045E39
0x180045ce6  mov     eax, cs:g_TrustedEnvironment
0x180045cec  mov     [rsp+98h+var_18], r14
0x180045cf4  test    eax, eax
0x180045cf6  jnz     short loc_180045D10
0x180045cf8  call    cs:__imp_SkIsSecureKernel
0x180045cff  nop     dword ptr [rax+rax+00h]
0x180045d04  sar     eax, 1Fh
0x180045d07  add     eax, 2
0x180045d0a  mov     cs:g_TrustedEnvironment, eax
0x180045d10  mov     r14d, 1
0x180045d16  test    al, 2
0x180045d18  jnz     loc_180045E2A
0x180045d1e  mov     [rsp+98h+arg_10], rbp
0x180045d26  lea     r8, [rsp+98h+KeyHandle]; KeyHandle
0x180045d2b  xor     ebp, ebp
0x180045d2d  mov     [rsp+98h+var_10], rsi
0x180045d35  xor     edx, edx; PCWSTR
0x180045d37  mov     [rsp+98h+KeyHandle], rbp
0x180045d3c  lea     rcx, aRegistryMachin_14; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180045d43  mov     esi, ebp
0x180045d45  call    TlsOpenRegKey
0x180045d4a  test    eax, eax
0x180045d4c  js      loc_180045DDC
0x180045d52  xorps   xmm0, xmm0
0x180045d55  mov     [rsp+98h+arg_8], rbx
0x180045d5d  mov     rbx, [rsp+98h+KeyHandle]
0x180045d62  lea     rdx, g_rgbPad1+30h; SourceString
0x180045d69  xorps   xmm1, xmm1
0x180045d6c  mov     [rsp+98h+var_50], ebp
0x180045d70  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x180045d75  mov     [rsp+98h+KeyValueInformation], ebp
0x180045d79  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x180045d7e  movups  [rsp+98h+var_34], xmm1
0x180045d83  call    cs:__imp_RtlInitUnicodeString
0x180045d8a  nop     dword ptr [rax+rax+00h]
0x180045d8f  lea     rax, [rsp+98h+var_50]
0x180045d94  mov     r8d, 2; KeyValueInformationClass
0x180045d9a  mov     [rsp+98h+ResultLength], rax; ResultLength
0x180045d9f  lea     r9, [rsp+98h+KeyValueInformation]; KeyValueInformation
0x180045da4  lea     rdx, [rsp+98h+DestinationString]; ValueName
0x180045da9  mov     [rsp+98h+Length], 14h; Length
0x180045db1  mov     rcx, rbx; KeyHandle
0x180045db4  call    cs:__imp_ZwQueryValueKey
0x180045dbb  nop     dword ptr [rax+rax+00h]
0x180045dc0  mov     rbx, [rsp+98h+arg_8]
0x180045dc8  test    eax, eax
0x180045dca  js      short loc_180045DDC
0x180045dcc  cmp     dword ptr [rsp+98h+var_34], 4
0x180045dd1  jnz     short loc_180045DDC
0x180045dd3  cmp     dword ptr [rsp+98h+var_34+8], r14d
0x180045dd8  cmovz   esi, r14d
0x180045ddc  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x180045de1  test    rcx, rcx
0x180045de4  jz      short loc_180045DF7
0x180045de6  call    cs:__imp_ZwClose
0x180045ded  nop     dword ptr [rax+rax+00h]
0x180045df2  mov     [rsp+98h+KeyHandle], rbp
0x180045df7  mov     rbp, [rsp+98h+arg_10]
0x180045dff  test    esi, esi
0x180045e01  mov     cs:dword_1800CB7C4, esi
0x180045e07  mov     rsi, [rsp+98h+var_10]
0x180045e0f  jz      short loc_180045E2A
0x180045e11  call    GetExternalHashAlgorithms
0x180045e16  call    GetExternalSignatureAlgorithms
0x180045e1b  call    GetExternalKeyExchangeAlgorithms
0x180045e20  call    GetExternalCipherAlgorithms
0x180045e25  call    GetExternalCipherSuites
0x180045e2a  mov     cs:dword_1800CC0A4, r14d
0x180045e31  mov     r14, [rsp+98h+var_18]
0x180045e39  lea     rcx, Resource; Resource
0x180045e40  call    cs:__imp_ExReleaseResourceLite
0x180045e47  nop     dword ptr [rax+rax+00h]
0x180045e4c  call    cs:__imp_KeLeaveCriticalRegion
0x180045e53  nop     dword ptr [rax+rax+00h]
0x180045e58  test    rdi, rdi
0x180045e5b  jnz     short loc_180045E67
0x180045e5d  mov     eax, 80090027h
0x180045e62  jmp     loc_180045F17
0x180045e67  mov     ecx, [rdi+4]
0x180045e6a  sub     ecx, 73736C31h
0x180045e70  jz      loc_180045EEF
0x180045e76  cmp     ecx, 2
0x180045e79  jz      short loc_180045EC8
0x180045e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e82  lea     rax, WPP_GLOBAL_Control
0x180045e89  cmp     rcx, rax
0x180045e8c  jz      short loc_180045EC1
0x180045e8e  mov     eax, [rcx+2Ch]
0x180045e91  test    al, 1
0x180045e93  jz      short loc_180045EC1
0x180045e95  mov     rcx, [rcx+18h]
0x180045e99  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045ea0  mov     [rsp+98h+var_68], 0A2Ch
0x180045ea8  lea     r9, aStatus; "Status"
0x180045eaf  mov     [rsp+98h+ResultLength], rax
0x180045eb4  mov     [rsp+98h+Length], 0C0000002h
0x180045ebc  call    WPP_SF_sDsd
0x180045ec1  mov     eax, 0C0000002h
0x180045ec6  jmp     short loc_180045F17
0x180045ec8  mov     rcx, [rdi+20h]; hKey
0x180045ecc  test    rcx, rcx
0x180045ecf  jz      short loc_180045ED6
0x180045ed1  call    BCryptDestroyKey
0x180045ed6  mov     ecx, [rdi]
0x180045ed8  mov     rax, rdi
0x180045edb  test    rcx, rcx
0x180045ede  jz      short loc_180045F0D
0x180045ee0  mov     byte ptr [rax], 0
0x180045ee3  lea     rax, [rax+1]
0x180045ee7  sub     rcx, 1
0x180045eeb  jnz     short loc_180045EE0
0x180045eed  jmp     short loc_180045F0D
0x180045eef  mov     edx, 390h
0x180045ef4  mov     rax, rdi
0x180045ef7  nop     word ptr [rax+rax+00000000h]
0x180045f00  mov     byte ptr [rax], 0
0x180045f03  lea     rax, [rax+1]
0x180045f07  sub     rdx, 1
0x180045f0b  jnz     short loc_180045F00
0x180045f0d  mov     rcx, rdi; P
0x180045f10  call    MSCryptFree
0x180045f15  xor     eax, eax
0x180045f17  mov     rcx, [rsp+98h+var_20]
0x180045f1c  xor     rcx, rsp; StackCookie
0x180045f1f  call    __security_check_cookie
0x180045f24  add     rsp, 90h
0x180045f2b  pop     rdi
0x180045f2c  retn
```
