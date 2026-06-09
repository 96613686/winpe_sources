# QueryAttributes

- ea: `0x180179b14`
- end: `0x180179cef`
- name: `QueryAttributes`
- size: `475`
- prototype: `int __fastcall(_SUBJECT *Subject, unsigned int AttributesToQuery, _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **AttributesInBuf)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180179cf8`
- `0x180179d80`

## callees

- `0x1800cc6c0`
- `0x1800cd3e4`
- `0x180179808`
- `0x18017982c`
- `0x180179b14`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180179b6f`
- `ntdll!RtlInitUnicodeString` at `0x180179ba6`
- `ntdll!RtlInitUnicodeString` at `0x180179bd5`
- `ntdll!RtlInitUnicodeString` at `0x180179c01`
- `ntdll!RtlInitUnicodeString` at `0x180179c30`
- `ntdll!RtlInitUnicodeString` at `0x180179b6f`
- `ntdll!RtlInitUnicodeString` at `0x180179ba6`
- `ntdll!RtlInitUnicodeString` at `0x180179bd5`
- `ntdll!RtlInitUnicodeString` at `0x180179c01`
- `ntdll!RtlInitUnicodeString` at `0x180179c30`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180179c76`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180179c76`

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
0x180179b14  mov     [rsp+arg_8], rbx
0x180179b19  push    rbp
0x180179b1a  push    rsi
0x180179b1b  push    rdi
0x180179b1c  push    r14
0x180179b1e  push    r15
0x180179b20  sub     rsp, 90h
0x180179b27  mov     rax, cs:__security_cookie
0x180179b2e  xor     rax, rsp
0x180179b31  mov     [rsp+0B8h+var_38], rax
0x180179b39  mov     esi, AttributesToQuery
0x180179b3b  mov     r14, AttributesInBuf
0x180179b3e  xor     AttributesToQuery, AttributesToQuery; Val
0x180179b40  mov     r15, Subject
0x180179b43  lea     Subject, [rsp+0B8h+AttributeNames]; void *
0x180179b48  lea     r8d, [rdx+40h]; Size
0x180179b4c  call    memset_0
0x180179b51  xor     ebp, ebp
0x180179b53  mov     [rsp+0B8h+AttributesBufferRequiredSize], ebp
0x180179b57  mov     [r14], rbp
0x180179b5a  test    sil, 1
0x180179b5e  jz      short loc_180179B80
0x180179b60  lea     rdx, POLICY_FLAGS_ATTRIBUTE_NAME; SourceString
0x180179b67  lea     Subject, [rsp+0B8h+AttributeNames]; DestinationString
0x180179b6c  lea     ebx, [rbp+64h]
0x180179b6f  call    cs:__imp_RtlInitUnicodeString
0x180179b76  nop     dword ptr [rax+rax+00h]
0x180179b7b  lea     edi, [rbp+1]
0x180179b7e  jmp     short loc_180179B85
0x180179b80  xor     edi, edi
0x180179b82  lea     ebx, [rdi+10h]
0x180179b85  test    sil, 2
0x180179b89  jz      short loc_180179BB4
0x180179b8b  mov     eax, edi
0x180179b8d  lea     Subject, [rsp+0B8h+AttributeNames]
0x180179b92  shl     rax, 4
0x180179b96  lea     rdx, ENTERPRISE_IDS_ATTRIBUTE_NAME; SourceString
0x180179b9d  add     Subject, rax; DestinationString
0x180179ba0  add     ebx, 98h
0x180179ba6  call    cs:__imp_RtlInitUnicodeString
0x180179bad  nop     dword ptr [rax+rax+00h]
0x180179bb2  inc     edi
0x180179bb4  test    sil, 4
0x180179bb8  jz      short loc_180179BE3
0x180179bba  mov     eax, edi
0x180179bbc  lea     Subject, [rsp+0B8h+AttributeNames]
0x180179bc1  shl     rax, 4
0x180179bc5  lea     rdx, INTENT_ENTERPRISE_ID_ATTRIBUTE_NAME; SourceString
0x180179bcc  add     Subject, rax; DestinationString
0x180179bcf  add     ebx, 98h
0x180179bd5  call    cs:__imp_RtlInitUnicodeString
0x180179bdc  nop     dword ptr [rax+rax+00h]
0x180179be1  inc     edi
0x180179be3  test    sil, 8
0x180179be7  jz      short loc_180179C0F
0x180179be9  mov     eax, edi
0x180179beb  lea     Subject, [rsp+0B8h+AttributeNames]
0x180179bf0  shl     rax, 4
0x180179bf4  lea     rdx, EVALUATION_FLAGS_ATTRIBUTE_NAME; SourceString
0x180179bfb  add     Subject, rax; DestinationString
0x180179bfe  add     ebx, 54h ; 'T'
0x180179c01  call    cs:__imp_RtlInitUnicodeString
0x180179c08  nop     dword ptr [rax+rax+00h]
0x180179c0d  inc     edi
0x180179c0f  test    sil, 10h
0x180179c13  jz      short loc_180179C3E
0x180179c15  mov     eax, edi
0x180179c17  lea     Subject, [rsp+0B8h+AttributeNames]
0x180179c1c  shl     rax, 4
0x180179c20  lea     rdx, EXEMPT_ENTERPRISE_IDS_ATTRIBUTE_NAME; SourceString
0x180179c27  add     Subject, rax; DestinationString
0x180179c2a  add     ebx, 98h
0x180179c30  call    cs:__imp_RtlInitUnicodeString
0x180179c37  nop     dword ptr [rax+rax+00h]
0x180179c3c  inc     edi
0x180179c3e  test    rbp, rbp
0x180179c41  jz      short loc_180179C4B
0x180179c43  mov     Subject, rbp; Memory
0x180179c46  call    EnterpriseContextLibMemFree
0x180179c4b  mov     ecx, ebx; NumberOfBytes
0x180179c4d  call    EnterpriseContextLibMemAllocPaged
0x180179c52  mov     rbp, rax
0x180179c55  test    rax, rax
0x180179c58  jz      short loc_180179CC0
0x180179c5a  mov     Subject, [r15]
0x180179c5d  lea     rax, [rsp+0B8h+AttributesBufferRequiredSize]
0x180179c62  mov     [rsp+0B8h+var_90], rax
0x180179c67  lea     rdx, [rsp+0B8h+AttributeNames]
0x180179c6c  mov     r9, rbp
0x180179c6f  mov     [rsp+0B8h+var_98], ebx
0x180179c73  mov     r8d, edi
0x180179c76  call    cs:__imp_NtQuerySecurityAttributesToken
0x180179c7d  nop     dword ptr [rax+rax+00h]
0x180179c82  mov     esi, eax
0x180179c84  cmp     eax, 0C0000023h
0x180179c89  jnz     short loc_180179C97
0x180179c8b  cmp     ebx, [rsp+0B8h+AttributesBufferRequiredSize]
0x180179c8f  jnb     short loc_180179CB6
0x180179c91  mov     ebx, [rsp+0B8h+AttributesBufferRequiredSize]
0x180179c95  jmp     short loc_180179C3E
0x180179c97  cmp     eax, 0C0000225h
0x180179c9c  jnz     short loc_180179CAD
0x180179c9e  mov     Subject, rbp; Memory
0x180179ca1  call    EnterpriseContextLibMemFree
0x180179ca6  xor     esi, esi
0x180179ca8  mov     [r14], rsi
0x180179cab  jmp     short loc_180179CC5
0x180179cad  test    eax, eax
0x180179caf  js      short loc_180179CB6
0x180179cb1  mov     [r14], rbp
0x180179cb4  jmp     short loc_180179CC5
0x180179cb6  mov     Subject, rbp; Memory
0x180179cb9  call    EnterpriseContextLibMemFree
0x180179cbe  jmp     short loc_180179CC5
0x180179cc0  mov     esi, 0C0000017h
0x180179cc5  mov     eax, esi
0x180179cc7  mov     Subject, [rsp+0B8h+var_38]
0x180179ccf  xor     Subject, rsp; StackCookie
0x180179cd2  call    __security_check_cookie
0x180179cd7  mov     rbx, [rsp+0B8h+arg_8]
0x180179cdf  add     rsp, 90h
0x180179ce6  pop     r15
0x180179ce8  pop     r14
0x180179cea  pop     rdi
0x180179ceb  pop     rsi
0x180179cec  pop     rbp
0x180179ced  retn
```
