# DirectoryServerUtil::GetAutoSigningCertUsingLdap(LdapServer *,ushort const *,ushort const *,_BYTE_ARRAY *,unsigned __int64)

- ea: `0x18004acc8`
- end: `0x18004af26`
- name: `?GetAutoSigningCertUsingLdap@DirectoryServerUtil@@CAJPEAVLdapServer@@PEBG1PEAU_BYTE_ARRAY@@_K@Z`
- size: `606`
- prototype: `__int64 __fastcall(struct LdapServer *this, const unsigned __int16 *, const unsigned __int16 *, struct _BYTE_ARRAY *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004b240`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18001d55c`
- `0x1800307c4`
- `0x1800436a4`
- `0x180044d30`
- `0x18004acc8`
- `0x18005e314`

## import_xrefs

- `WLDAP32!__imp_ldap_value_free_len` at `0x18004af09`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18004af09`

## string_xrefs

- `0x18004aee4`: `CopyStringA`
- `0x18004ad23`: `DirectoryServerUtil::GetAutoSigningCertUsingLdap`
- `0x18004ad3d`: `DirectoryServerUtil::GetAutoSigningCertUsingLdap`
- `0x18004ad5f`: `DirectoryServerUtil::GetAutoSigningCertUsingLdap`
- `0x18004ad8c`: `DirectoryServerUtil::GetAutoSigningCertUsingLdap`
- `0x18004add1`: `DirectoryServerUtil::GetAutoSigningCertUsingLdap`
- `0x18004ae66`: `DirectoryServerUtil::GetAutoSigningCertUsingLdap`
- `0x18004aeeb`: `DirectoryServerUtil::GetAutoSigningCertUsingLdap`
- `0x18004ad53`: `pcszComputerDn`
- `0x18004ad72`: `pcszComputerDn`
- `0x18004ade1`: `%s: There was no auto join signing certificate found in the directory.`
- `0x18004ae07`: `%s: Found %lu user certificate(s) in the directory. Looking for subject name "%s" in them...`

## pseudocode

```c
__int64 __fastcall DirectoryServerUtil::GetAutoSigningCertUsingLdap(
        struct LdapServer *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _BYTE_ARRAY *a4)
{
  unsigned int v8; // ebx
  const unsigned __int16 *v9; // rdx
  int AttributeValues; // eax
  const unsigned __int16 *v11; // r8
  unsigned __int16 *v12; // r9
  unsigned int v13; // esi
  __int64 v14; // rdi
  unsigned int v15; // r14d
  struct berval **v16; // r13
  __int64 v17; // r12
  int IsValidDeviceJoinAutoSigningCert; // eax
  char **v19; // r15
  struct _CERT_CONTEXT **v21; // [rsp+20h] [rbp-48h]
  struct _CERT_CONTEXT *v22; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v23; // [rsp+80h] [rbp+18h]
  struct berval **vals; // [rsp+88h] [rbp+20h] BYREF

  v23 = a3;
  vals = 0;
  LODWORD(v22) = 0;
  if ( a4 )
    memset_0(a4, 0, 0xA0u);
  if ( !this )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetAutoSigningCertUsingLdap",
      L"pLdapServer");
    v9 = L"pLdapServer";
LABEL_5:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DirectoryServerUtil::GetAutoSigningCertUsingLdap", v9);
    goto LABEL_25;
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetAutoSigningCertUsingLdap",
      L"pcszComputerDn");
    v9 = L"pcszComputerDn";
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetAutoSigningCertUsingLdap",
      L"certArray");
    v9 = L"certArray";
    goto LABEL_5;
  }
  AttributeValues = LdapServer::GetAttributeValues(this, a2, a3, L"userCertificate", (unsigned int *)&v22, &vals);
  v8 = AttributeValues;
  if ( AttributeValues == -2145648512 )
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: There was no auto join signing certificate found in the directory.",
      L"DirectoryServerUtil::GetAutoSigningCertUsingLdap");
    v8 = 0;
  }
  else if ( AttributeValues >= 0 )
  {
    v12 = a3;
    v13 = (unsigned int)v22;
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Found %lu user certificate(s) in the directory. Looking for subject name \"%s\" in them...",
      L"DirectoryServerUtil::GetAutoSigningCertUsingLdap",
      (unsigned int)v22,
      v12);
    v14 = 0;
    v15 = 0;
    while ( (unsigned int)v14 < v13 && v15 < 0xAuLL )
    {
      v16 = vals;
      LODWORD(v22) = 0;
      v17 = (unsigned int)v14;
      IsValidDeviceJoinAutoSigningCert = RegistrationCertHelper::IsValidDeviceJoinAutoSigningCert(
                                           (BYTE *)vals[v14]->bv_val,
                                           vals[v14]->bv_len,
                                           v23,
                                           (int *)&v22,
                                           (const struct _CERT_CONTEXT **)v21);
      v14 = (unsigned int)(v14 + 1);
      v8 = IsValidDeviceJoinAutoSigningCert;
      if ( IsValidDeviceJoinAutoSigningCert >= 0 )
      {
        if ( (_DWORD)v22 )
        {
          Logger::TraceVerbose(
            (wchar_t *)L"%s: Found a valid auto signing cert. %lu of %lu cert(s).",
            L"DirectoryServerUtil::GetAutoSigningCertUsingLdap",
            (unsigned int)v14,
            v13);
          v19 = (char **)((char *)a4 + 16 * v15);
          AttributeValues = CopyStringA(v16[v17]->bv_val, v16[v17]->bv_len, v19);
          v8 = AttributeValues;
          if ( AttributeValues < 0 )
          {
            v11 = L"CopyStringA";
            goto LABEL_24;
          }
          ++v15;
          v19[1] = (char *)v16[v17]->bv_len;
        }
        else
        {
          Logger::TraceVerbose(
            (wchar_t *)L"%s: This user certificate is not a valid auto signing cert. %lu of %lu cert(s).",
            L"DirectoryServerUtil::GetAutoSigningCertUsingLdap",
            (unsigned int)v14,
            v13);
        }
      }
      else
      {
        LODWORD(v21) = IsValidDeviceJoinAutoSigningCert;
        Logger::TraceWarning(
          (wchar_t *)L"%s: Failed to check if the user cert is a valid auto signing cert. %lu of %lu cert(s). Registration"
                      "CertHelper::IsValidDeviceJoinAutoSigningCert failed with error code: 0x%08x.Ignoring this certificate.",
          L"DirectoryServerUtil::GetAutoSigningCertUsingLdap",
          (unsigned int)v14,
          v13);
        v8 = 0;
      }
    }
  }
  else
  {
    v11 = L"LdapServer::GetAttributeValues";
LABEL_24:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DirectoryServerUtil::GetAutoSigningCertUsingLdap",
      v11,
      (unsigned int)AttributeValues);
  }
LABEL_25:
  ldap_value_free_len(vals);
  return v8;
}

```

## disassembly

```asm
0x18004acc8  mov     rax, rsp
0x18004accb  mov     [rax+10h], rbx
0x18004accf  mov     [rax+18h], r8
0x18004acd3  push    rbp
0x18004acd4  push    rsi
0x18004acd5  push    rdi
0x18004acd6  push    r12
0x18004acd8  push    r13
0x18004acda  push    r14
0x18004acdc  push    r15
0x18004acde  sub     rsp, 30h
0x18004ace2  mov     qword ptr [rax+20h], 0
0x18004acea  mov     rbp, r9
0x18004aced  mov     dword ptr [rax+8], 0
0x18004acf4  mov     rsi, r8
0x18004acf7  mov     rbx, rdx
0x18004acfa  mov     rdi, rcx
0x18004acfd  test    r9, r9
0x18004ad00  jz      short loc_18004AD12
0x18004ad02  xor     edx, edx; Val
0x18004ad04  mov     r8d, 0A0h; Size
0x18004ad0a  mov     rcx, r9; void *
0x18004ad0d  call    memset_0
0x18004ad12  test    rdi, rdi
0x18004ad15  jnz     short loc_18004AD4E
0x18004ad17  lea     r8, aPldapserver; "pLdapServer"
0x18004ad1e  mov     ebx, 80070057h
0x18004ad23  lea     rdx, aDirectoryserve_2; "DirectoryServerUtil::GetAutoSigningCert"...
0x18004ad2a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004ad31  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004ad36  lea     rdx, aPldapserver; "pLdapServer"
0x18004ad3d  lea     rcx, aDirectoryserve_2; "DirectoryServerUtil::GetAutoSigningCert"...
0x18004ad44  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18004ad49  jmp     loc_18004AF01
0x18004ad4e  test    rbx, rbx
0x18004ad51  jnz     short loc_18004AD7B
0x18004ad53  lea     r8, aPcszcomputerdn; "pcszComputerDn"
0x18004ad5a  mov     ebx, 80070057h
0x18004ad5f  lea     rdx, aDirectoryserve_2; "DirectoryServerUtil::GetAutoSigningCert"...
0x18004ad66  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004ad6d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004ad72  lea     rdx, aPcszcomputerdn; "pcszComputerDn"
0x18004ad79  jmp     short loc_18004AD3D
0x18004ad7b  test    rbp, rbp
0x18004ad7e  jnz     short loc_18004ADA8
0x18004ad80  lea     r8, aCertarray; "certArray"
0x18004ad87  mov     ebx, 80070057h
0x18004ad8c  lea     rdx, aDirectoryserve_2; "DirectoryServerUtil::GetAutoSigningCert"...
0x18004ad93  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004ad9a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004ad9f  lea     rdx, aCertarray; "certArray"
0x18004ada6  jmp     short loc_18004AD3D
0x18004ada8  lea     rax, [rsp+68h+vals]
0x18004adb0  mov     rdx, rbx; unsigned __int16 *
0x18004adb3  mov     [rsp+68h+var_40], rax; struct berval ***
0x18004adb8  lea     r9, aUsercertificat; "userCertificate"
0x18004adbf  lea     rax, [rsp+68h+arg_0]
0x18004adc4  mov     rcx, rdi; this
0x18004adc7  mov     [rsp+68h+var_48], rax; struct _CERT_CONTEXT **
0x18004adcc  call    ?GetAttributeValues@LdapServer@@QEAAJPEBG00PEAKPEAPEAPEAUberval@@@Z; LdapServer::GetAttributeValues(ushort const *,ushort const *,ushort const *,ulong *,berval * * *)
0x18004add1  lea     rdx, aDirectoryserve_2; "DirectoryServerUtil::GetAutoSigningCert"...
0x18004add8  mov     ebx, eax
0x18004adda  cmp     eax, 801C0080h
0x18004addf  jnz     short loc_18004ADF4
0x18004ade1  lea     rcx, aSThereWasNoAut; "%s: There was no auto join signing cert"...
0x18004ade8  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004aded  xor     ebx, ebx
0x18004adef  jmp     loc_18004AF01
0x18004adf4  test    eax, eax
0x18004adf6  jns     short loc_18004AE04
0x18004adf8  lea     r8, aLdapserverGeta; "LdapServer::GetAttributeValues"
0x18004adff  jmp     loc_18004AEF2
0x18004ae04  mov     r9, rsi
0x18004ae07  lea     rcx, aSFoundLuUserCe; "%s: Found %lu user certificate(s) in th"...
0x18004ae0e  mov     esi, dword ptr [rsp+68h+arg_0]
0x18004ae12  mov     r8d, esi
0x18004ae15  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004ae1a  xor     edi, edi
0x18004ae1c  xor     r14d, r14d
0x18004ae1f  cmp     edi, esi
0x18004ae21  jnb     loc_18004AF01
0x18004ae27  mov     r15d, r14d
0x18004ae2a  cmp     r15, 0Ah
0x18004ae2e  jnb     loc_18004AF01
0x18004ae34  mov     r13, [rsp+68h+vals]
0x18004ae3c  lea     r9, [rsp+68h+arg_0]; int *
0x18004ae41  mov     r8, [rsp+68h+arg_10]; unsigned __int16 *
0x18004ae49  mov     dword ptr [rsp+68h+arg_0], 0
0x18004ae51  mov     r12d, edi
0x18004ae54  mov     rcx, [r13+rdi*8+0]
0x18004ae59  mov     edx, [rcx]; cbCertEncoded
0x18004ae5b  mov     rcx, [rcx+8]; pbCertEncoded
0x18004ae5f  call    ?IsValidDeviceJoinAutoSigningCert@RegistrationCertHelper@@SAJPEBEKPEBGPEAHPEAPEBU_CERT_CONTEXT@@@Z; RegistrationCertHelper::IsValidDeviceJoinAutoSigningCert(uchar const *,ulong,ushort const *,int *,_CERT_CONTEXT const * *)
0x18004ae64  inc     edi
0x18004ae66  lea     rdx, aDirectoryserve_2; "DirectoryServerUtil::GetAutoSigningCert"...
0x18004ae6d  mov     ebx, eax
0x18004ae6f  mov     r9d, esi
0x18004ae72  mov     r8d, edi
0x18004ae75  test    eax, eax
0x18004ae77  jns     short loc_18004AE8D
0x18004ae79  lea     rcx, aSFailedToCheck; "%s: Failed to check if the user cert is"...
0x18004ae80  mov     dword ptr [rsp+68h+var_48], eax
0x18004ae84  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18004ae89  xor     ebx, ebx
0x18004ae8b  jmp     short loc_18004AE1F
0x18004ae8d  cmp     dword ptr [rsp+68h+arg_0], 0
0x18004ae92  jz      short loc_18004AED3
0x18004ae94  lea     rcx, aSFoundAValidAu; "%s: Found a valid auto signing cert. %l"...
0x18004ae9b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004aea0  mov     rcx, [r13+r12*8+0]
0x18004aea5  shl     r15, 4
0x18004aea9  add     r15, rbp
0x18004aeac  mov     r8, r15; char **
0x18004aeaf  mov     edx, [rcx]; SourceSize
0x18004aeb1  mov     rcx, [rcx+8]; Source
0x18004aeb5  call    ?CopyStringA@@YAJPEBD_KPEAPEAD@Z; CopyStringA(char const *,unsigned __int64,char * *)
0x18004aeba  mov     ebx, eax
0x18004aebc  test    eax, eax
0x18004aebe  js      short loc_18004AEE4
0x18004aec0  mov     rax, [r13+r12*8+0]
0x18004aec5  inc     r14d
0x18004aec8  mov     ecx, [rax]
0x18004aeca  mov     [r15+8], rcx
0x18004aece  jmp     loc_18004AE1F
0x18004aed3  lea     rcx, aSThisUserCerti; "%s: This user certificate is not a vali"...
0x18004aeda  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004aedf  jmp     loc_18004AE1F
0x18004aee4  lea     r8, aCopystringa; "CopyStringA"
0x18004aeeb  lea     rdx, aDirectoryserve_2; "DirectoryServerUtil::GetAutoSigningCert"...
0x18004aef2  mov     r9d, eax
0x18004aef5  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18004aefc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004af01  mov     rcx, [rsp+68h+vals]; vals
0x18004af09  call    cs:__imp_ldap_value_free_len
0x18004af0f  mov     eax, ebx
0x18004af11  mov     rbx, [rsp+68h+arg_8]
0x18004af16  add     rsp, 30h
0x18004af1a  pop     r15
0x18004af1c  pop     r14
0x18004af1e  pop     r13
0x18004af20  pop     r12
0x18004af22  pop     rdi
0x18004af23  pop     rsi
0x18004af24  pop     rbp
0x18004af25  retn
```
