# CNameResolver::_ResolveName(ushort const *,ushort const *,CDPA<CUserObject,CTContainer_PolicyUnOwned<CUserObject>> &)

- ea: `0x18006fbcc`
- end: `0x18006fd5b`
- name: `?_ResolveName@CNameResolver@@AEAAJPEBG0AEAV?$CDPA@VCUserObject@@V?$CTContainer_PolicyUnOwned@VCUserObject@@@@@@@Z`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006f048`

## callees

- `0x1800120e0`
- `0x180053fd4`
- `0x18006f368`
- `0x18006fbcc`

## import_xrefs

- `ntdll!RtlCreateUnicodeString` at `0x18006fbf6`
- `ntdll!RtlCreateUnicodeString` at `0x18006fc1f`
- `ntdll!RtlCreateUnicodeString` at `0x18006fbf6`
- `ntdll!RtlCreateUnicodeString` at `0x18006fc1f`
- `ntdll!RtlFreeUnicodeString` at `0x18006fd3c`
- `ntdll!RtlFreeUnicodeString` at `0x18006fd46`
- `ntdll!RtlFreeUnicodeString` at `0x18006fd3c`
- `ntdll!RtlFreeUnicodeString` at `0x18006fd46`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006fd2e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006fd2e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18006fc5a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18006fc5a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18006fc9e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18006fc9e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006fd15`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006fd24`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006fd15`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006fd24`

## pseudocode

```c
__int64 __fastcall CNameResolver::_ResolveName(
        struct _LSA_TRANSLATED_SID2 *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 a4)
{
  int appended; // ebx
  struct _LSA_UNICODE_STRING *v7; // rdi
  BOOLEAN v8; // al
  struct _UNICODE_STRING *v9; // rcx
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  PLSA_TRANSLATED_SID2 v12; // rcx
  PSID Sid; // rdx
  unsigned int v14; // edx
  CUserObject *v16; // [rsp+30h] [rbp-39h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-31h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING v20; // [rsp+58h] [rbp-11h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  PLSA_TRANSLATED_SID2 Sids; // [rsp+D0h] [rbp+67h] BYREF

  Sids = a1;
  DestinationString = 0;
  if ( RtlCreateUnicodeString(&DestinationString, a3) )
  {
    v7 = 0;
    v20 = 0;
    if ( a2 )
    {
      v8 = RtlCreateUnicodeString(&v20, a2);
      v9 = &v20;
      if ( !v8 )
        v9 = 0;
      v7 = (struct _LSA_UNICODE_STRING *)v9;
    }
    PolicyHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v10 = LsaOpenPolicy(v7, &ObjectAttributes, 0x800u, &PolicyHandle);
    appended = v10 | 0x10000000;
    if ( v10 >= 0 )
    {
      Sids = 0;
      ReferencedDomains = 0;
      v11 = LsaLookupNames2(PolicyHandle, 0, 1u, (PLSA_UNICODE_STRING)&DestinationString, &ReferencedDomains, &Sids);
      v12 = Sids;
      appended = v11 | 0x10000000;
      if ( v11 >= 0 )
      {
        if ( (unsigned int)(Sids->Use - 1) <= 1 || (unsigned int)(Sids->Use - 4) <= 1 )
        {
          Sid = Sids->Sid;
          v16 = 0;
          appended = CSidResolver::SingletonSidLookup((CSidResolver *)Sids, Sid, SHARE_ROLE_INVALID, &v16);
          if ( appended >= 0 )
          {
            appended = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(a4, v16);
            if ( appended < 0 )
            {
              if ( v16 )
                CUserObject::`scalar deleting destructor'(v16, v14);
            }
          }
          v12 = Sids;
        }
        else
        {
          appended = -2147467259;
        }
      }
      if ( v12 )
        LsaFreeMemory(v12);
      if ( ReferencedDomains )
        LsaFreeMemory(ReferencedDomains);
      LsaClose(PolicyHandle);
    }
    if ( v7 )
      RtlFreeUnicodeString((PUNICODE_STRING)v7);
    RtlFreeUnicodeString(&DestinationString);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18006fbcc  mov     [rsp-8+arg_0], rcx
0x18006fbd1  push    rbp
0x18006fbd2  push    rbx
0x18006fbd3  push    rdi
0x18006fbd4  push    r14
0x18006fbd6  lea     rbp, [rsp-3Fh]
0x18006fbdb  sub     rsp, 0A8h
0x18006fbe2  mov     rbx, rdx
0x18006fbe5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006fbe9  xorps   xmm0, xmm0
0x18006fbec  mov     rdx, r8; SourceString
0x18006fbef  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006fbf3  mov     r14, r9
0x18006fbf6  call    cs:__imp_RtlCreateUnicodeString
0x18006fbfc  test    al, al
0x18006fbfe  jnz     short loc_18006FC0A
0x18006fc00  mov     ebx, 8007000Eh
0x18006fc05  jmp     loc_18006FD4C
0x18006fc0a  xor     edi, edi
0x18006fc0c  xorps   xmm0, xmm0
0x18006fc0f  movups  xmmword ptr [rbp+57h+var_68.Length], xmm0
0x18006fc13  test    rbx, rbx
0x18006fc16  jz      short loc_18006FC32
0x18006fc18  mov     rdx, rbx; SourceString
0x18006fc1b  lea     rcx, [rbp+57h+var_68]; DestinationString
0x18006fc1f  call    cs:__imp_RtlCreateUnicodeString
0x18006fc25  test    al, al
0x18006fc27  lea     rcx, [rbp+57h+var_68]
0x18006fc2b  cmovz   rcx, rdi
0x18006fc2f  mov     rdi, rcx
0x18006fc32  xorps   xmm0, xmm0
0x18006fc35  mov     [rbp+57h+PolicyHandle], 0
0x18006fc3d  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18006fc41  mov     r8d, 800h; DesiredAccess
0x18006fc47  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006fc4b  mov     rcx, rdi; SystemName
0x18006fc4e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006fc52  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006fc56  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006fc5a  call    cs:__imp_LsaOpenPolicy
0x18006fc60  mov     ebx, eax
0x18006fc62  or      ebx, 10000000h
0x18006fc68  jl      loc_18006FD34
0x18006fc6e  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18006fc72  lea     rax, [rbp+57h+arg_0]
0x18006fc76  mov     [rsp+0C0h+Sids], rax; Sids
0x18006fc7b  lea     r9, [rbp+57h+DestinationString]; Names
0x18006fc7f  xor     edx, edx; Flags
0x18006fc81  mov     [rbp+57h+arg_0], 0
0x18006fc89  lea     rax, [rbp+57h+var_80]
0x18006fc8d  mov     [rbp+57h+var_80], 0
0x18006fc95  mov     [rsp+0C0h+ReferencedDomains], rax; ReferencedDomains
0x18006fc9a  lea     r8d, [rdx+1]; Count
0x18006fc9e  call    cs:__imp_LsaLookupNames2
0x18006fca4  mov     rcx, [rbp+57h+arg_0]; this
0x18006fca8  mov     ebx, eax
0x18006fcaa  or      ebx, 10000000h
0x18006fcb0  jl      short loc_18006FD10
0x18006fcb2  mov     edx, [rcx]
0x18006fcb4  lea     eax, [rdx-1]
0x18006fcb7  cmp     eax, 1
0x18006fcba  jbe     short loc_18006FCCB
0x18006fcbc  lea     eax, [rdx-4]
0x18006fcbf  cmp     eax, 1
0x18006fcc2  jbe     short loc_18006FCCB
0x18006fcc4  mov     ebx, 80004005h
0x18006fcc9  jmp     short loc_18006FD10
0x18006fccb  mov     rdx, [rcx+8]; void *
0x18006fccf  lea     r9, [rbp+57h+var_90]; struct CUserObject **
0x18006fcd3  or      r8d, 0FFFFFFFFh; enum SHARE_ROLE
0x18006fcd7  mov     [rbp+57h+var_90], 0
0x18006fcdf  call    ?SingletonSidLookup@CSidResolver@@QEAAJPEAXW4SHARE_ROLE@@PEAPEAVCUserObject@@@Z; CSidResolver::SingletonSidLookup(void *,SHARE_ROLE,CUserObject * *)
0x18006fce4  mov     ebx, eax
0x18006fce6  test    eax, eax
0x18006fce8  js      short loc_18006FD0C
0x18006fcea  mov     rdx, [rbp+57h+var_90]
0x18006fcee  mov     rcx, r14
0x18006fcf1  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x18006fcf6  mov     ebx, eax
0x18006fcf8  test    eax, eax
0x18006fcfa  jns     short loc_18006FD0C
0x18006fcfc  cmp     [rbp+57h+var_90], 0
0x18006fd01  jz      short loc_18006FD0C
0x18006fd03  mov     rcx, [rbp+57h+var_90]; this
0x18006fd07  call    ??_GCUserObject@@QEAAPEAXI@Z; CUserObject::`scalar deleting destructor'(uint)
0x18006fd0c  mov     rcx, [rbp+57h+arg_0]; Buffer
0x18006fd10  test    rcx, rcx
0x18006fd13  jz      short loc_18006FD1B
0x18006fd15  call    cs:__imp_LsaFreeMemory
0x18006fd1b  mov     rcx, [rbp+57h+var_80]; Buffer
0x18006fd1f  test    rcx, rcx
0x18006fd22  jz      short loc_18006FD2A
0x18006fd24  call    cs:__imp_LsaFreeMemory
0x18006fd2a  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18006fd2e  call    cs:__imp_LsaClose
0x18006fd34  test    rdi, rdi
0x18006fd37  jz      short loc_18006FD42
0x18006fd39  mov     rcx, rdi; UnicodeString
0x18006fd3c  call    cs:__imp_RtlFreeUnicodeString
0x18006fd42  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x18006fd46  call    cs:__imp_RtlFreeUnicodeString
0x18006fd4c  mov     eax, ebx
0x18006fd4e  add     rsp, 0A8h
0x18006fd55  pop     r14
0x18006fd57  pop     rdi
0x18006fd58  pop     rbx
0x18006fd59  pop     rbp
0x18006fd5a  retn
```
