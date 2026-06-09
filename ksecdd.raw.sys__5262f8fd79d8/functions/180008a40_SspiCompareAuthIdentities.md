# SspiCompareAuthIdentities

- ea: `0x180008a40`
- end: `0x180008ce4`
- name: `SspiCompareAuthIdentities`
- size: `676`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity1, PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity2, PBOOLEAN SameSuppliedUser, PBOOLEAN SameSuppliedIdentity)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004050`
- `0x180006830`
- `0x180007fc4`
- `0x1800081c4`
- `0x180008438`
- `0x1800088c4`
- `0x180008990`
- `0x180008a40`
- `0x1800092d0`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiCompareAuthIdentities(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity1,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity2,
        PBOOLEAN SameSuppliedUser,
        PBOOLEAN SameSuppliedIdentity)
{
  const WCHAR **v4; // rsi
  PCWSTR *v5; // rdi
  SECURITY_STATUS v10; // ebx
  const WCHAR *v11; // rcx
  const WCHAR *v12; // r8
  const WCHAR *v13; // rdx
  PVOID DataBuffer; // [rsp+20h] [rbp-30h] BYREF
  PVOID v16; // [rsp+28h] [rbp-28h] BYREF
  PCWSTR ppszDomainName; // [rsp+30h] [rbp-20h] BYREF
  PCWSTR v18; // [rsp+38h] [rbp-18h] BYREF
  PCWSTR ppszPackedCredentialsString; // [rsp+40h] [rbp-10h] BYREF
  PCWSTR v20; // [rsp+48h] [rbp-8h] BYREF
  int v21; // [rsp+90h] [rbp+40h] BYREF
  PCWSTR ppszUserName; // [rsp+A0h] [rbp+50h] BYREF
  PCWSTR v23; // [rsp+A8h] [rbp+58h] BYREF

  v4 = 0;
  ppszUserName = 0;
  v5 = 0;
  ppszDomainName = 0;
  ppszPackedCredentialsString = 0;
  v23 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  DataBuffer = 0;
  v16 = 0;
  if ( SameSuppliedUser )
    *SameSuppliedUser = 0;
  if ( SameSuppliedIdentity )
    *SameSuppliedIdentity = 0;
  if ( !AuthIdentity1
    || (v10 = SspiEncodeAuthIdentityAsStrings(
                AuthIdentity1,
                &ppszUserName,
                &ppszDomainName,
                &ppszPackedCredentialsString),
        v10 >= 0) )
  {
    if ( !AuthIdentity2 || (v10 = SspiEncodeAuthIdentityAsStrings(AuthIdentity2, &v23, &v18, &v20), v10 >= 0) )
    {
      if ( SspiHelperEqualStrings(ppszUserName, v23, 1u) && SspiHelperEqualStrings(ppszDomainName, v18, 1u) )
      {
        if ( SameSuppliedUser )
          *SameSuppliedUser = 1;
        if ( SameSuppliedIdentity
          && (SspiHelperEqualStrings(ppszPackedCredentialsString, v20, 0)
           || (unsigned int)SspiHelperEqualPackedCredentials(AuthIdentity1, AuthIdentity2)) )
        {
          *SameSuppliedIdentity = 1;
        }
        goto LABEL_39;
      }
      if ( SameSuppliedUser )
      {
        if ( ppszUserName && (unsigned int)LocalCredIsMarshaledCredentialW(ppszUserName) )
        {
          if ( LocalCredUnmarshalCredentialW(ppszUserName, (enum _CRED_MARSHAL_TYPE *)&v21, &DataBuffer) )
          {
            v4 = (const WCHAR **)DataBuffer;
            v10 = -1073741670;
            goto LABEL_40;
          }
          if ( ((v21 - 2) & 0xFFFFFFFD) != 0 )
            SspiLocalFree(DataBuffer);
          else
            v4 = (const WCHAR **)DataBuffer;
        }
        if ( v23 && (unsigned int)LocalCredIsMarshaledCredentialW(v23) )
        {
          if ( LocalCredUnmarshalCredentialW(v23, (enum _CRED_MARSHAL_TYPE *)&v21, &v16) )
          {
            v5 = (PCWSTR *)v16;
            v10 = -1073741670;
            goto LABEL_40;
          }
          if ( ((v21 - 2) & 0xFFFFFFFD) != 0 )
            SspiLocalFree(v16);
          else
            v5 = (PCWSTR *)v16;
        }
        if ( v4 )
        {
          v11 = *v4;
          if ( v5 )
          {
            *SameSuppliedUser = SspiHelperEqualStrings(v11, *v5, 1u);
            goto LABEL_39;
          }
          v12 = v18;
          v13 = v23;
        }
        else
        {
          if ( !v5 )
            goto LABEL_39;
          v12 = ppszDomainName;
          v13 = ppszUserName;
          v11 = *v5;
        }
        v10 = SspiHelperCompareUserNames(v11, v13, v12, SameSuppliedUser);
        if ( v10 < 0 )
          goto LABEL_40;
      }
LABEL_39:
      v10 = 0;
    }
  }
LABEL_40:
  if ( ppszUserName )
    SspiLocalFree((PVOID)ppszUserName);
  if ( ppszDomainName )
    SspiLocalFree((PVOID)ppszDomainName);
  if ( ppszPackedCredentialsString )
    SspiLocalFree((PVOID)ppszPackedCredentialsString);
  if ( v23 )
    SspiLocalFree((PVOID)v23);
  if ( v18 )
    SspiLocalFree((PVOID)v18);
  if ( v20 )
    SspiLocalFree((PVOID)v20);
  if ( v4 )
    SspiLocalFree(v4);
  if ( v5 )
    SspiLocalFree(v5);
  return SspNtStatusToSecStatus((unsigned int)v10);
}

```

## disassembly

```asm
0x180008a40  mov     [rsp-38h+arg_8], rbx
0x180008a45  push    rbp
0x180008a46  push    rsi
0x180008a47  push    rdi
0x180008a48  push    r12
0x180008a4a  push    r13
0x180008a4c  push    r14
0x180008a4e  push    r15
0x180008a50  mov     rbp, rsp
0x180008a53  sub     rsp, 50h
0x180008a57  xor     esi, esi
0x180008a59  mov     [rbp+ppszUserName], 0
0x180008a61  xor     edi, edi
0x180008a63  mov     [rbp+ppszDomainName], 0
0x180008a6b  mov     [rbp+ppszPackedCredentialsString], 0
0x180008a73  mov     r15, r9
0x180008a76  mov     [rbp+arg_18], 0
0x180008a7e  mov     r14, r8
0x180008a81  mov     [rbp+var_18], 0
0x180008a89  mov     r12, rdx
0x180008a8c  mov     [rbp+var_8], 0
0x180008a94  mov     r13, rcx
0x180008a97  mov     [rbp+arg_0], 0
0x180008a9e  mov     [rbp+DataBuffer], rsi
0x180008aa2  mov     [rbp+var_28], rdi
0x180008aa6  test    r8, r8
0x180008aa9  jz      short loc_180008AAE
0x180008aab  mov     [r8], sil
0x180008aae  test    r15, r15
0x180008ab1  jz      short loc_180008AB6
0x180008ab3  mov     [r9], sil
0x180008ab6  test    r13, r13
0x180008ab9  jz      short loc_180008AD6
0x180008abb  lea     r9, [rbp+ppszPackedCredentialsString]; ppszPackedCredentialsString
0x180008abf  lea     r8, [rbp+ppszDomainName]; ppszDomainName
0x180008ac3  lea     rdx, [rbp+ppszUserName]; ppszUserName
0x180008ac7  call    SspiEncodeAuthIdentityAsStrings
0x180008acc  mov     ebx, eax
0x180008ace  test    eax, eax
0x180008ad0  js      loc_180008C56
0x180008ad6  test    r12, r12
0x180008ad9  jz      short loc_180008AF9
0x180008adb  lea     r9, [rbp+var_8]; ppszPackedCredentialsString
0x180008adf  mov     rcx, r12; pAuthIdentity
0x180008ae2  lea     r8, [rbp+var_18]; ppszDomainName
0x180008ae6  lea     rdx, [rbp+arg_18]; ppszUserName
0x180008aea  call    SspiEncodeAuthIdentityAsStrings
0x180008aef  mov     ebx, eax
0x180008af1  test    eax, eax
0x180008af3  js      loc_180008C56
0x180008af9  mov     rdx, [rbp+arg_18]; PCWSTR
0x180008afd  mov     r8b, 1; CaseInSensitive
0x180008b00  mov     rcx, [rbp+ppszUserName]; SourceString
0x180008b04  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x180008b09  test    al, al
0x180008b0b  jz      short loc_180008B63
0x180008b0d  mov     rdx, [rbp+var_18]; PCWSTR
0x180008b11  mov     r8b, 1; CaseInSensitive
0x180008b14  mov     rcx, [rbp+ppszDomainName]; SourceString
0x180008b18  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x180008b1d  test    al, al
0x180008b1f  jz      short loc_180008B63
0x180008b21  test    r14, r14
0x180008b24  jz      short loc_180008B2A
0x180008b26  mov     byte ptr [r14], 1
0x180008b2a  test    r15, r15
0x180008b2d  jz      loc_180008C54
0x180008b33  mov     rdx, [rbp+var_8]; PCWSTR
0x180008b37  xor     r8d, r8d; CaseInSensitive
0x180008b3a  mov     rcx, [rbp+ppszPackedCredentialsString]; SourceString
0x180008b3e  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x180008b43  test    al, al
0x180008b45  jnz     short loc_180008B5A
0x180008b47  mov     rdx, r12; void *
0x180008b4a  mov     rcx, r13; void *
0x180008b4d  call    ?SspiHelperEqualPackedCredentials@@YAHPEAX0@Z; SspiHelperEqualPackedCredentials(void *,void *)
0x180008b52  test    eax, eax
0x180008b54  jz      loc_180008C54
0x180008b5a  mov     byte ptr [r15], 1
0x180008b5e  jmp     loc_180008C54
0x180008b63  test    r14, r14
0x180008b66  jz      loc_180008C54
0x180008b6c  mov     rcx, [rbp+ppszUserName]; unsigned __int16 *
0x180008b70  mov     ebx, 0FFFFFFFDh
0x180008b75  test    rcx, rcx
0x180008b78  jz      short loc_180008BBF
0x180008b7a  call    ?LocalCredIsMarshaledCredentialW@@YAHPEBG@Z; LocalCredIsMarshaledCredentialW(ushort const *)
0x180008b7f  test    eax, eax
0x180008b81  jz      short loc_180008BBF
0x180008b83  mov     rcx, [rbp+ppszUserName]; unsigned __int16 *
0x180008b87  lea     r8, [rbp+DataBuffer]; void **
0x180008b8b  lea     rdx, [rbp+arg_0]; enum _CRED_MARSHAL_TYPE *
0x180008b8f  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x180008b94  test    eax, eax
0x180008b96  jz      short loc_180008BA6
0x180008b98  mov     rsi, [rbp+DataBuffer]
0x180008b9c  mov     ebx, 0C000009Ah
0x180008ba1  jmp     loc_180008C56
0x180008ba6  mov     eax, [rbp+arg_0]
0x180008ba9  add     eax, 0FFFFFFFEh
0x180008bac  test    ebx, eax
0x180008bae  jz      short loc_180008BBB
0x180008bb0  mov     rcx, [rbp+DataBuffer]; DataBuffer
0x180008bb4  call    SspiLocalFree
0x180008bb9  jmp     short loc_180008BBF
0x180008bbb  mov     rsi, [rbp+DataBuffer]
0x180008bbf  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x180008bc3  test    rcx, rcx
0x180008bc6  jz      short loc_180008C0A
0x180008bc8  call    ?LocalCredIsMarshaledCredentialW@@YAHPEBG@Z; LocalCredIsMarshaledCredentialW(ushort const *)
0x180008bcd  test    eax, eax
0x180008bcf  jz      short loc_180008C0A
0x180008bd1  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x180008bd5  lea     r8, [rbp+var_28]; void **
0x180008bd9  lea     rdx, [rbp+arg_0]; enum _CRED_MARSHAL_TYPE *
0x180008bdd  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x180008be2  test    eax, eax
0x180008be4  jz      short loc_180008BF1
0x180008be6  mov     rdi, [rbp+var_28]
0x180008bea  mov     ebx, 0C000009Ah
0x180008bef  jmp     short loc_180008C56
0x180008bf1  mov     eax, [rbp+arg_0]
0x180008bf4  add     eax, 0FFFFFFFEh
0x180008bf7  test    ebx, eax
0x180008bf9  jz      short loc_180008C06
0x180008bfb  mov     rcx, [rbp+var_28]; DataBuffer
0x180008bff  call    SspiLocalFree
0x180008c04  jmp     short loc_180008C0A
0x180008c06  mov     rdi, [rbp+var_28]
0x180008c0a  test    rsi, rsi
0x180008c0d  jz      short loc_180008C31
0x180008c0f  mov     rcx, [rsi]; SourceString
0x180008c12  test    rdi, rdi
0x180008c15  jz      short loc_180008C27
0x180008c17  mov     rdx, [rdi]; PCWSTR
0x180008c1a  mov     r8b, 1; CaseInSensitive
0x180008c1d  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x180008c22  mov     [r14], al
0x180008c25  jmp     short loc_180008C54
0x180008c27  mov     r8, [rbp+var_18]
0x180008c2b  mov     rdx, [rbp+arg_18]
0x180008c2f  jmp     short loc_180008C46
0x180008c31  test    rdi, rdi
0x180008c34  jz      short loc_180008C54
0x180008c36  test    rsi, rsi
0x180008c39  jnz     short loc_180008C54
0x180008c3b  mov     r8, [rbp+ppszDomainName]; PCWSTR
0x180008c3f  mov     rdx, [rbp+ppszUserName]; SourceString
0x180008c43  mov     rcx, [rdi]; PCWSTR
0x180008c46  mov     r9, r14; unsigned __int8 *
0x180008c49  call    ?SspiHelperCompareUserNames@@YAJPEBG00PEAE@Z; SspiHelperCompareUserNames(ushort const *,ushort const *,ushort const *,uchar *)
0x180008c4e  mov     ebx, eax
0x180008c50  test    eax, eax
0x180008c52  js      short loc_180008C56
0x180008c54  xor     ebx, ebx
0x180008c56  mov     rcx, [rbp+ppszUserName]; DataBuffer
0x180008c5a  test    rcx, rcx
0x180008c5d  jz      short loc_180008C64
0x180008c5f  call    SspiLocalFree
0x180008c64  mov     rcx, [rbp+ppszDomainName]; DataBuffer
0x180008c68  test    rcx, rcx
0x180008c6b  jz      short loc_180008C72
0x180008c6d  call    SspiLocalFree
0x180008c72  mov     rcx, [rbp+ppszPackedCredentialsString]; DataBuffer
0x180008c76  test    rcx, rcx
0x180008c79  jz      short loc_180008C80
0x180008c7b  call    SspiLocalFree
0x180008c80  mov     rcx, [rbp+arg_18]; DataBuffer
0x180008c84  test    rcx, rcx
0x180008c87  jz      short loc_180008C8E
0x180008c89  call    SspiLocalFree
0x180008c8e  mov     rcx, [rbp+var_18]; DataBuffer
0x180008c92  test    rcx, rcx
0x180008c95  jz      short loc_180008C9C
0x180008c97  call    SspiLocalFree
0x180008c9c  mov     rcx, [rbp+var_8]; DataBuffer
0x180008ca0  test    rcx, rcx
0x180008ca3  jz      short loc_180008CAA
0x180008ca5  call    SspiLocalFree
0x180008caa  test    rsi, rsi
0x180008cad  jz      short loc_180008CB7
0x180008caf  mov     rcx, rsi; DataBuffer
0x180008cb2  call    SspiLocalFree
0x180008cb7  test    rdi, rdi
0x180008cba  jz      short loc_180008CC4
0x180008cbc  mov     rcx, rdi; DataBuffer
0x180008cbf  call    SspiLocalFree
0x180008cc4  mov     ecx, ebx
0x180008cc6  call    SspNtStatusToSecStatus
0x180008ccb  mov     rbx, [rsp+50h+arg_8]
0x180008cd3  add     rsp, 50h
0x180008cd7  pop     r15
0x180008cd9  pop     r14
0x180008cdb  pop     r13
0x180008cdd  pop     r12
0x180008cdf  pop     rdi
0x180008ce0  pop     rsi
0x180008ce1  pop     rbp
0x180008ce2  retn
```
