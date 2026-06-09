# QueryAttributes

- ea: `0x180175eb8`
- end: `0x18017606e`
- name: `QueryAttributes`
- size: `438`
- prototype: `int __fastcall(_SUBJECT *Subject, unsigned int AttributesToQuery, _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **AttributesInBuf)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180176074`
- `0x1801760fc`

## callees

- `0x1800cada0`
- `0x1800cba94`
- `0x180175bd0`
- `0x180175bf0`
- `0x180175eb8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180175f13`
- `ntdll!RtlInitUnicodeString` at `0x180175f44`
- `ntdll!RtlInitUnicodeString` at `0x180175f6d`
- `ntdll!RtlInitUnicodeString` at `0x180175f93`
- `ntdll!RtlInitUnicodeString` at `0x180175fbc`
- `ntdll!RtlInitUnicodeString` at `0x180175f13`
- `ntdll!RtlInitUnicodeString` at `0x180175f44`
- `ntdll!RtlInitUnicodeString` at `0x180175f6d`
- `ntdll!RtlInitUnicodeString` at `0x180175f93`
- `ntdll!RtlInitUnicodeString` at `0x180175fbc`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180175ffc`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180175ffc`

## pseudocode

```c
__int64 __fastcall QueryAttributes(
        _SUBJECT *Subject,
        char AttributesToQuery,
        _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **AttributesInBuf)
{
  unsigned __int8 v6; // dl
  _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v7; // rbp
  unsigned int v8; // ebx
  unsigned int v9; // edi
  int SecurityAttributesToken; // eax
  unsigned int v11; // esi
  unsigned int AttributesBufferRequiredSize[4]; // [rsp+30h] [rbp-88h] BYREF
  _UNICODE_STRING AttributeNames[4]; // [rsp+40h] [rbp-78h] BYREF

  memset_0(AttributeNames, 0, sizeof(AttributeNames));
  v7 = 0;
  AttributesBufferRequiredSize[0] = 0;
  *AttributesInBuf = 0;
  if ( (AttributesToQuery & 1) != 0 )
  {
    v8 = 100;
    RtlInitUnicodeString(AttributeNames, POLICY_FLAGS_ATTRIBUTE_NAME);
    v9 = 1;
  }
  else
  {
    v9 = 0;
    v8 = 16;
  }
  if ( (AttributesToQuery & 2) != 0 )
  {
    v8 += 152;
    RtlInitUnicodeString(&AttributeNames[v9++], ENTERPRISE_IDS_ATTRIBUTE_NAME);
  }
  if ( (AttributesToQuery & 4) != 0 )
  {
    v8 += 152;
    RtlInitUnicodeString(&AttributeNames[v9++], INTENT_ENTERPRISE_ID_ATTRIBUTE_NAME);
  }
  if ( (AttributesToQuery & 8) != 0 )
  {
    v8 += 84;
    RtlInitUnicodeString(&AttributeNames[v9++], EVALUATION_FLAGS_ATTRIBUTE_NAME);
  }
  if ( (AttributesToQuery & 0x10) != 0 )
  {
    v8 += 152;
    RtlInitUnicodeString(&AttributeNames[v9++], EXEMPT_ENTERPRISE_IDS_ATTRIBUTE_NAME);
  }
  while ( 1 )
  {
    if ( v7 )
      EnterpriseContextLibMemFree(v7);
    v7 = (_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)EnterpriseContextLibMemAllocPaged(v8, v6);
    if ( !v7 )
      return (unsigned int)-1073741801;
    SecurityAttributesToken = NtQuerySecurityAttributesToken(
                                Subject->TokenHandle,
                                AttributeNames,
                                v9,
                                v7,
                                v8,
                                AttributesBufferRequiredSize);
    v11 = SecurityAttributesToken;
    if ( SecurityAttributesToken != -1073741789 )
    {
      if ( SecurityAttributesToken == -1073741275 )
      {
        EnterpriseContextLibMemFree(v7);
        v11 = 0;
        *AttributesInBuf = 0;
        return v11;
      }
      if ( SecurityAttributesToken >= 0 )
      {
        *AttributesInBuf = v7;
        return v11;
      }
LABEL_22:
      EnterpriseContextLibMemFree(v7);
      return v11;
    }
    if ( v8 >= AttributesBufferRequiredSize[0] )
      goto LABEL_22;
    v8 = AttributesBufferRequiredSize[0];
  }
}

```

## disassembly

```asm
0x180175eb8  mov     [rsp+arg_8], rbx
0x180175ebd  push    rbp
0x180175ebe  push    rsi
0x180175ebf  push    rdi
0x180175ec0  push    r14
0x180175ec2  push    r15
0x180175ec4  sub     rsp, 90h
0x180175ecb  mov     rax, cs:__security_cookie
0x180175ed2  xor     rax, rsp
0x180175ed5  mov     [rsp+0B8h+var_38], rax
0x180175edd  mov     esi, AttributesToQuery
0x180175edf  mov     r14, AttributesInBuf
0x180175ee2  xor     AttributesToQuery, AttributesToQuery; Val
0x180175ee4  mov     r15, Subject
0x180175ee7  lea     Subject, [rsp+0B8h+AttributeNames]; void *
0x180175eec  lea     r8d, [rdx+40h]; Size
0x180175ef0  call    memset_0
0x180175ef5  xor     ebp, ebp
0x180175ef7  mov     [rsp+0B8h+AttributesBufferRequiredSize], ebp
0x180175efb  mov     [r14], rbp
0x180175efe  test    sil, 1
0x180175f02  jz      short loc_180175F1E
0x180175f04  lea     rdx, POLICY_FLAGS_ATTRIBUTE_NAME; SourceString
0x180175f0b  lea     Subject, [rsp+0B8h+AttributeNames]; DestinationString
0x180175f10  lea     ebx, [rbp+64h]
0x180175f13  call    cs:__imp_RtlInitUnicodeString
0x180175f19  lea     edi, [rbp+1]
0x180175f1c  jmp     short loc_180175F23
0x180175f1e  xor     edi, edi
0x180175f20  lea     ebx, [rdi+10h]
0x180175f23  test    sil, 2
0x180175f27  jz      short loc_180175F4C
0x180175f29  mov     eax, edi
0x180175f2b  lea     Subject, [rsp+0B8h+AttributeNames]
0x180175f30  shl     rax, 4
0x180175f34  lea     rdx, ENTERPRISE_IDS_ATTRIBUTE_NAME; SourceString
0x180175f3b  add     Subject, rax; DestinationString
0x180175f3e  add     ebx, 98h
0x180175f44  call    cs:__imp_RtlInitUnicodeString
0x180175f4a  inc     edi
0x180175f4c  test    sil, 4
0x180175f50  jz      short loc_180175F75
0x180175f52  mov     eax, edi
0x180175f54  lea     Subject, [rsp+0B8h+AttributeNames]
0x180175f59  shl     rax, 4
0x180175f5d  lea     rdx, INTENT_ENTERPRISE_ID_ATTRIBUTE_NAME; SourceString
0x180175f64  add     Subject, rax; DestinationString
0x180175f67  add     ebx, 98h
0x180175f6d  call    cs:__imp_RtlInitUnicodeString
0x180175f73  inc     edi
0x180175f75  test    sil, 8
0x180175f79  jz      short loc_180175F9B
0x180175f7b  mov     eax, edi
0x180175f7d  lea     Subject, [rsp+0B8h+AttributeNames]
0x180175f82  shl     rax, 4
0x180175f86  lea     rdx, EVALUATION_FLAGS_ATTRIBUTE_NAME; SourceString
0x180175f8d  add     Subject, rax; DestinationString
0x180175f90  add     ebx, 54h ; 'T'
0x180175f93  call    cs:__imp_RtlInitUnicodeString
0x180175f99  inc     edi
0x180175f9b  test    sil, 10h
0x180175f9f  jz      short loc_180175FC4
0x180175fa1  mov     eax, edi
0x180175fa3  lea     Subject, [rsp+0B8h+AttributeNames]
0x180175fa8  shl     rax, 4
0x180175fac  lea     rdx, EXEMPT_ENTERPRISE_IDS_ATTRIBUTE_NAME; SourceString
0x180175fb3  add     Subject, rax; DestinationString
0x180175fb6  add     ebx, 98h
0x180175fbc  call    cs:__imp_RtlInitUnicodeString
0x180175fc2  inc     edi
0x180175fc4  test    rbp, rbp
0x180175fc7  jz      short loc_180175FD1
0x180175fc9  mov     Subject, rbp; Memory
0x180175fcc  call    EnterpriseContextLibMemFree
0x180175fd1  mov     ecx, ebx; NumberOfBytes
0x180175fd3  call    EnterpriseContextLibMemAllocPaged
0x180175fd8  mov     rbp, rax
0x180175fdb  test    rax, rax
0x180175fde  jz      short loc_180176040
0x180175fe0  mov     Subject, [r15]
0x180175fe3  lea     rax, [rsp+0B8h+AttributesBufferRequiredSize]
0x180175fe8  mov     [rsp+0B8h+var_90], rax
0x180175fed  lea     rdx, [rsp+0B8h+AttributeNames]
0x180175ff2  mov     r9, rbp
0x180175ff5  mov     [rsp+0B8h+var_98], ebx
0x180175ff9  mov     r8d, edi
0x180175ffc  call    cs:__imp_NtQuerySecurityAttributesToken
0x180176002  mov     esi, eax
0x180176004  cmp     eax, 0C0000023h
0x180176009  jnz     short loc_180176017
0x18017600b  cmp     ebx, [rsp+0B8h+AttributesBufferRequiredSize]
0x18017600f  jnb     short loc_180176036
0x180176011  mov     ebx, [rsp+0B8h+AttributesBufferRequiredSize]
0x180176015  jmp     short loc_180175FC4
0x180176017  cmp     eax, 0C0000225h
0x18017601c  jnz     short loc_18017602D
0x18017601e  mov     Subject, rbp; Memory
0x180176021  call    EnterpriseContextLibMemFree
0x180176026  xor     esi, esi
0x180176028  mov     [r14], rsi
0x18017602b  jmp     short loc_180176045
0x18017602d  test    eax, eax
0x18017602f  js      short loc_180176036
0x180176031  mov     [r14], rbp
0x180176034  jmp     short loc_180176045
0x180176036  mov     Subject, rbp; Memory
0x180176039  call    EnterpriseContextLibMemFree
0x18017603e  jmp     short loc_180176045
0x180176040  mov     esi, 0C0000017h
0x180176045  mov     eax, esi
0x180176047  mov     Subject, [rsp+0B8h+var_38]
0x18017604f  xor     Subject, rsp; StackCookie
0x180176052  call    __security_check_cookie
0x180176057  mov     rbx, [rsp+0B8h+arg_8]
0x18017605f  add     rsp, 90h
0x180176066  pop     r15
0x180176068  pop     r14
0x18017606a  pop     rdi
0x18017606b  pop     rsi
0x18017606c  pop     rbp
0x18017606d  retn
```
