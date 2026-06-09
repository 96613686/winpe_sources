# DirectoryServerUtil::GetObjectGuidUsingLdap(LdapServer *,ushort const *,ushort * *)

- ea: `0x18004b0c8`
- end: `0x18004b237`
- name: `?GetObjectGuidUsingLdap@DirectoryServerUtil@@CAJPEAVLdapServer@@PEBGPEAPEAG@Z`
- size: `367`
- prototype: `__int64 __fastcall(struct LdapServer *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004b240`

## callees

- `0x1800084f4`
- `0x18001d55c`
- `0x1800307c4`
- `0x180043ef8`
- `0x18004af2c`
- `0x18004b0c8`

## import_xrefs

- `WLDAP32!__imp_ldap_value_free_len` at `0x18004b221`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18004b221`

## string_xrefs

- `0x18004b0fa`: `DirectoryServerUtil::GetObjectGuidUsingLdap`
- `0x18004b114`: `DirectoryServerUtil::GetObjectGuidUsingLdap`
- `0x18004b136`: `DirectoryServerUtil::GetObjectGuidUsingLdap`
- `0x18004b163`: `DirectoryServerUtil::GetObjectGuidUsingLdap`
- `0x18004b1b2`: `DirectoryServerUtil::GetObjectGuidUsingLdap`
- `0x18004b1f4`: `DirectoryServerUtil::GetObjectGuidUsingLdap`
- `0x18004b12a`: `pcszComputerDn`
- `0x18004b149`: `pcszComputerDn`

## pseudocode

```c
__int64 __fastcall DirectoryServerUtil::GetObjectGuidUsingLdap(
        struct LdapServer *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rsi
  struct berval **v4; // rdi
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  int AttributeValues; // eax
  int GuidStringFromOctetString; // eax
  unsigned __int16 *v11; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+60h] [rbp+8h] BYREF
  struct berval **v13; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  v11 = 0;
  v13 = 0;
  v12 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetObjectGuidUsingLdap",
      L"pLdapServer");
    v7 = L"pLdapServer";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DirectoryServerUtil::GetObjectGuidUsingLdap", v7);
    goto LABEL_13;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetObjectGuidUsingLdap",
      L"pcszComputerDn");
    v7 = L"pcszComputerDn";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetObjectGuidUsingLdap",
      L"ppszObjectGuid");
    v7 = L"ppszObjectGuid";
    goto LABEL_3;
  }
  *a3 = 0;
  AttributeValues = LdapServer::GetAttributeValues(a1, a2, (const unsigned __int16 *)a3, L"objectGUID", &v12, &v13);
  v6 = AttributeValues;
  if ( AttributeValues >= 0 )
  {
    v4 = v13;
    GuidStringFromOctetString = DirectoryServerUtil::GetGuidStringFromOctetString((*v13)->bv_val, (*v13)->bv_len, &v11);
    v6 = GuidStringFromOctetString;
    if ( GuidStringFromOctetString >= 0 )
    {
      *a3 = v11;
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DirectoryServerUtil::GetObjectGuidUsingLdap",
        L"GetGuidStringFromOctetString",
        (unsigned int)GuidStringFromOctetString);
      v3 = v11;
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DirectoryServerUtil::GetObjectGuidUsingLdap",
      L"LdapServer::GetAttributeValues",
      (unsigned int)AttributeValues);
    v4 = v13;
  }
LABEL_13:
  operator delete(v3);
  ldap_value_free_len(v4);
  return v6;
}

```

## disassembly

```asm
0x18004b0c8  mov     rax, rsp
0x18004b0cb  mov     [rax+10h], rbx
0x18004b0cf  push    rsi
0x18004b0d0  push    rdi
0x18004b0d1  push    r14
0x18004b0d3  sub     rsp, 40h
0x18004b0d7  xor     esi, esi
0x18004b0d9  xor     edi, edi
0x18004b0db  mov     [rax-28h], rsi
0x18004b0df  mov     r14, r8
0x18004b0e2  mov     [rax+20h], rdi
0x18004b0e6  mov     [rax+8], esi
0x18004b0e9  test    rcx, rcx
0x18004b0ec  jnz     short loc_18004B125
0x18004b0ee  lea     r8, aPldapserver; "pLdapServer"
0x18004b0f5  mov     ebx, 80070057h
0x18004b0fa  lea     rdx, aDirectoryserve; "DirectoryServerUtil::GetObjectGuidUsing"...
0x18004b101  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004b108  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004b10d  lea     rdx, aPldapserver; "pLdapServer"
0x18004b114  lea     rcx, aDirectoryserve; "DirectoryServerUtil::GetObjectGuidUsing"...
0x18004b11b  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18004b120  jmp     loc_18004B216
0x18004b125  test    rdx, rdx
0x18004b128  jnz     short loc_18004B152
0x18004b12a  lea     r8, aPcszcomputerdn; "pcszComputerDn"
0x18004b131  mov     ebx, 80070057h
0x18004b136  lea     rdx, aDirectoryserve; "DirectoryServerUtil::GetObjectGuidUsing"...
0x18004b13d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004b144  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004b149  lea     rdx, aPcszcomputerdn; "pcszComputerDn"
0x18004b150  jmp     short loc_18004B114
0x18004b152  test    r14, r14
0x18004b155  jnz     short loc_18004B17F
0x18004b157  lea     r8, aPpszobjectguid; "ppszObjectGuid"
0x18004b15e  mov     ebx, 80070057h
0x18004b163  lea     rdx, aDirectoryserve; "DirectoryServerUtil::GetObjectGuidUsing"...
0x18004b16a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18004b171  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004b176  lea     rdx, aPpszobjectguid; "ppszObjectGuid"
0x18004b17d  jmp     short loc_18004B114
0x18004b17f  lea     rax, [rsp+58h+arg_18]
0x18004b184  mov     [r8], rsi
0x18004b187  mov     [rsp+58h+var_30], rax; struct berval ***
0x18004b18c  lea     r9, aObjectguid; "objectGUID"
0x18004b193  lea     rax, [rsp+58h+arg_0]
0x18004b198  mov     [rsp+58h+var_38], rax; unsigned int *
0x18004b19d  call    ?GetAttributeValues@LdapServer@@QEAAJPEBG00PEAKPEAPEAPEAUberval@@@Z; LdapServer::GetAttributeValues(ushort const *,ushort const *,ushort const *,ulong *,berval * * *)
0x18004b1a2  mov     ebx, eax
0x18004b1a4  test    eax, eax
0x18004b1a6  jns     short loc_18004B1CC
0x18004b1a8  mov     r9d, eax
0x18004b1ab  lea     r8, aLdapserverGeta; "LdapServer::GetAttributeValues"
0x18004b1b2  lea     rdx, aDirectoryserve; "DirectoryServerUtil::GetObjectGuidUsing"...
0x18004b1b9  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18004b1c0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004b1c5  mov     rdi, [rsp+58h+arg_18]
0x18004b1ca  jmp     short loc_18004B216
0x18004b1cc  mov     rdi, [rsp+58h+arg_18]
0x18004b1d1  lea     r8, [rsp+58h+var_28]; unsigned __int16 **
0x18004b1d6  mov     rcx, [rdi]
0x18004b1d9  mov     edx, [rcx]; Size
0x18004b1db  mov     rcx, [rcx+8]; Src
0x18004b1df  call    ?GetGuidStringFromOctetString@DirectoryServerUtil@@CAJPEBDKPEAPEAG@Z; DirectoryServerUtil::GetGuidStringFromOctetString(char const *,ulong,ushort * *)
0x18004b1e4  mov     ebx, eax
0x18004b1e6  test    eax, eax
0x18004b1e8  jns     short loc_18004B20E
0x18004b1ea  mov     r9d, eax
0x18004b1ed  lea     r8, aGetguidstringf; "GetGuidStringFromOctetString"
0x18004b1f4  lea     rdx, aDirectoryserve; "DirectoryServerUtil::GetObjectGuidUsing"...
0x18004b1fb  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18004b202  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004b207  mov     rsi, [rsp+58h+var_28]
0x18004b20c  jmp     short loc_18004B216
0x18004b20e  mov     rax, [rsp+58h+var_28]
0x18004b213  mov     [r14], rax
0x18004b216  mov     rcx, rsi; Block
0x18004b219  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b21e  mov     rcx, rdi; vals
0x18004b221  call    cs:__imp_ldap_value_free_len
0x18004b227  mov     eax, ebx
0x18004b229  mov     rbx, [rsp+58h+arg_8]
0x18004b22e  add     rsp, 40h
0x18004b232  pop     r14
0x18004b234  pop     rdi
0x18004b235  pop     rsi
0x18004b236  retn
```
