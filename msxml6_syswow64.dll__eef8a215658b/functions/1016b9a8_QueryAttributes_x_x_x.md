# QueryAttributes(x,x,x)

- ea: `0x1016b9a8`
- end: `0x1016bafe`
- name: `_QueryAttributes@12`
- size: `342`
- prototype: `int __userpurge@<eax>(_SUBJECT *Subject@<ecx>, unsigned int AttributesToQuery@<edx>, _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **AttributesInBuf)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1016bb04`
- `0x1016bb64`

## callees

- `0x1006b470`
- `0x1016b73e`
- `0x1016b757`
- `0x1016b9a8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1016b9f0`
- `ntdll!RtlInitUnicodeString` at `0x1016ba0e`
- `ntdll!RtlInitUnicodeString` at `0x1016ba2c`
- `ntdll!RtlInitUnicodeString` at `0x1016ba4a`
- `ntdll!RtlInitUnicodeString` at `0x1016ba68`
- `ntdll!RtlInitUnicodeString` at `0x1016b9f0`
- `ntdll!RtlInitUnicodeString` at `0x1016ba0e`
- `ntdll!RtlInitUnicodeString` at `0x1016ba2c`
- `ntdll!RtlInitUnicodeString` at `0x1016ba4a`
- `ntdll!RtlInitUnicodeString` at `0x1016ba68`
- `ntdll!NtQuerySecurityAttributesToken` at `0x1016ba98`
- `ntdll!NtQuerySecurityAttributesToken` at `0x1016ba98`

## pseudocode

```c
int __fastcall QueryAttributes(
        _SUBJECT *Subject,
        void *AttributesToQuery,
        _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **AttributesInBuf)
{
  void *v3; // ebx
  int v4; // esi
  SIZE_T v5; // edi
  void *v6; // eax
  int v7; // eax
  int v8; // ebx
  unsigned int AttributesBufferRequiredSize; // [esp+14h] [ebp-2Ch] BYREF
  void *Memory; // [esp+18h] [ebp-28h]
  _UNICODE_STRING AttributeNames[4]; // [esp+1Ch] [ebp-24h] BYREF

  v3 = 0;
  *AttributesInBuf = 0;
  v4 = 0;
  Memory = AttributesToQuery;
  AttributesBufferRequiredSize = 0;
  memset(AttributeNames, 0, sizeof(AttributeNames));
  v5 = 12;
  if ( ((unsigned __int8)AttributesToQuery & 1) != 0 )
  {
    v5 = 80;
    RtlInitUnicodeString(AttributeNames, L"EDP://PolicyFlags");
    LOBYTE(AttributesToQuery) = (_BYTE)Memory;
    v4 = 1;
  }
  if ( ((unsigned __int8)AttributesToQuery & 2) != 0 )
  {
    v5 += 128;
    RtlInitUnicodeString(&AttributeNames[v4], L"EDP://EnterpriseIds");
    LOBYTE(AttributesToQuery) = (_BYTE)Memory;
    ++v4;
  }
  if ( ((unsigned __int8)AttributesToQuery & 4) != 0 )
  {
    v5 += 128;
    RtlInitUnicodeString(&AttributeNames[v4], L"PEDP://IntentEnterpriseId");
    LOBYTE(AttributesToQuery) = (_BYTE)Memory;
    ++v4;
  }
  if ( ((unsigned __int8)AttributesToQuery & 8) != 0 )
  {
    v5 += 68;
    RtlInitUnicodeString(&AttributeNames[v4], L"EDP://EvaluationFlags");
    LOBYTE(AttributesToQuery) = (_BYTE)Memory;
    ++v4;
  }
  if ( ((unsigned __int8)AttributesToQuery & 0x10) != 0 )
  {
    v5 += 128;
    RtlInitUnicodeString(&AttributeNames[v4++], L"EDP://ExemptEnterpriseIds");
  }
  while ( 1 )
  {
    if ( v3 )
      EnterpriseContextLibMemFree(v3);
    v6 = (void *)EnterpriseContextLibMemAllocPaged(v5);
    Memory = v6;
    if ( !v6 )
      return -1073741801;
    v7 = NtQuerySecurityAttributesToken(Subject->TokenHandle, AttributeNames, v4, v6, v5, &AttributesBufferRequiredSize);
    v8 = v7;
    if ( v7 != -1073741789 )
    {
      if ( v7 == -1073741275 )
      {
        EnterpriseContextLibMemFree(Memory);
        v8 = 0;
        *AttributesInBuf = 0;
        return v8;
      }
      if ( v7 >= 0 )
      {
        *AttributesInBuf = (_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)Memory;
        return v8;
      }
LABEL_21:
      EnterpriseContextLibMemFree(Memory);
      return v8;
    }
    if ( v5 >= AttributesBufferRequiredSize )
      goto LABEL_21;
    v5 = AttributesBufferRequiredSize;
    v3 = Memory;
  }
}

```

## disassembly

```asm
0x1016b9a8  mov     edi, edi
0x1016b9aa  push    ebp
0x1016b9ab  mov     ebp, esp
0x1016b9ad  sub     esp, 34h
0x1016b9b0  mov     eax, ___security_cookie
0x1016b9b5  xor     eax, ebp
0x1016b9b7  mov     [ebp+var_4], eax
0x1016b9ba  push    ebx
0x1016b9bb  push    esi
0x1016b9bc  mov     esi, [ebp+AttributesInBuf]
0x1016b9bf  xor     eax, eax
0x1016b9c1  push    edi
0x1016b9c2  push    8
0x1016b9c4  mov     [ebp+var_34], Subject
0x1016b9c7  lea     edi, [ebp+AttributeNames]
0x1016b9ca  pop     Subject
0x1016b9cb  mov     [ebp+var_30], esi
0x1016b9ce  xor     ebx, ebx
0x1016b9d0  mov     [esi], eax
0x1016b9d2  xor     esi, esi
0x1016b9d4  mov     [ebp+Memory], AttributesToQuery
0x1016b9d7  mov     [ebp+AttributesBufferRequiredSize], eax
0x1016b9da  rep stosd
0x1016b9dc  push    0Ch
0x1016b9de  pop     edi
0x1016b9df  test    dl, 1
0x1016b9e2  jz      short loc_1016B9FA
0x1016b9e4  push    50h ; 'P'
0x1016b9e6  pop     edi
0x1016b9e7  push    offset POLICY_FLAGS_ATTRIBUTE_NAME; "EDP://PolicyFlags"
0x1016b9ec  lea     eax, [ebp+AttributeNames]
0x1016b9ef  push    eax; DestinationString
0x1016b9f0  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016b9f6  mov     AttributesToQuery, [ebp+Memory]
0x1016b9f9  inc     esi
0x1016b9fa  test    dl, 2
0x1016b9fd  jz      short loc_1016BA18
0x1016b9ff  lea     eax, [ebp+AttributeNames]
0x1016ba02  sub     edi, 0FFFFFF80h
0x1016ba05  push    offset ENTERPRISE_IDS_ATTRIBUTE_NAME; "EDP://EnterpriseIds"
0x1016ba0a  lea     eax, [eax+esi*8]
0x1016ba0d  push    eax; DestinationString
0x1016ba0e  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016ba14  mov     AttributesToQuery, [ebp+Memory]
0x1016ba17  inc     esi
0x1016ba18  test    dl, 4
0x1016ba1b  jz      short loc_1016BA36
0x1016ba1d  lea     eax, [ebp+AttributeNames]
0x1016ba20  sub     edi, 0FFFFFF80h
0x1016ba23  push    offset INTENT_ENTERPRISE_ID_ATTRIBUTE_NAME; "PEDP://IntentEnterpriseId"
0x1016ba28  lea     eax, [eax+esi*8]
0x1016ba2b  push    eax; DestinationString
0x1016ba2c  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016ba32  mov     AttributesToQuery, [ebp+Memory]
0x1016ba35  inc     esi
0x1016ba36  test    dl, 8
0x1016ba39  jz      short loc_1016BA54
0x1016ba3b  lea     eax, [ebp+AttributeNames]
0x1016ba3e  add     edi, 44h ; 'D'
0x1016ba41  push    offset EVALUATION_FLAGS_ATTRIBUTE_NAME; "EDP://EvaluationFlags"
0x1016ba46  lea     eax, [eax+esi*8]
0x1016ba49  push    eax; DestinationString
0x1016ba4a  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016ba50  mov     AttributesToQuery, [ebp+Memory]
0x1016ba53  inc     esi
0x1016ba54  test    dl, 10h
0x1016ba57  jz      short loc_1016BA6F
0x1016ba59  lea     eax, [ebp+AttributeNames]
0x1016ba5c  sub     edi, 0FFFFFF80h
0x1016ba5f  push    offset EXEMPT_ENTERPRISE_IDS_ATTRIBUTE_NAME; "EDP://ExemptEnterpriseIds"
0x1016ba64  lea     eax, [eax+esi*8]
0x1016ba67  push    eax; DestinationString
0x1016ba68  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016ba6e  inc     esi
0x1016ba6f  test    ebx, ebx
0x1016ba71  jz      short loc_1016BA7A
0x1016ba73  mov     Subject, ebx; Memory
0x1016ba75  call    _EnterpriseContextLibMemFree@4; EnterpriseContextLibMemFree(x)
0x1016ba7a  mov     Subject, edi; NumberOfBytes
0x1016ba7c  call    _EnterpriseContextLibMemAllocPaged@8; EnterpriseContextLibMemAllocPaged(x,x)
0x1016ba81  mov     [ebp+Memory], eax
0x1016ba84  test    eax, eax
0x1016ba86  jz      short loc_1016BAE6
0x1016ba88  lea     Subject, [ebp+AttributesBufferRequiredSize]
0x1016ba8b  push    Subject
0x1016ba8c  push    edi
0x1016ba8d  push    eax
0x1016ba8e  push    esi
0x1016ba8f  lea     eax, [ebp+AttributeNames]
0x1016ba92  push    eax
0x1016ba93  mov     eax, [ebp+var_34]
0x1016ba96  push    dword ptr [eax]
0x1016ba98  call    ds:__imp__NtQuerySecurityAttributesToken@24; NtQuerySecurityAttributesToken(x,x,x,x,x,x)
0x1016ba9e  mov     ebx, eax
0x1016baa0  cmp     ebx, 0C0000023h
0x1016baa6  jnz     short loc_1016BAB5
0x1016baa8  cmp     edi, [ebp+AttributesBufferRequiredSize]
0x1016baab  jnb     short loc_1016BADC
0x1016baad  mov     edi, [ebp+AttributesBufferRequiredSize]
0x1016bab0  mov     ebx, [ebp+Memory]
0x1016bab3  jmp     short loc_1016BA6F
0x1016bab5  cmp     ebx, 0C0000225h
0x1016babb  jnz     short loc_1016BACE
0x1016babd  mov     Subject, [ebp+Memory]; Memory
0x1016bac0  call    _EnterpriseContextLibMemFree@4; EnterpriseContextLibMemFree(x)
0x1016bac5  mov     eax, [ebp+var_30]
0x1016bac8  xor     ebx, ebx
0x1016baca  mov     [eax], ebx
0x1016bacc  jmp     short loc_1016BAEB
0x1016bace  test    ebx, ebx
0x1016bad0  js      short loc_1016BADC
0x1016bad2  mov     eax, [ebp+var_30]
0x1016bad5  mov     Subject, [ebp+Memory]
0x1016bad8  mov     [eax], Subject
0x1016bada  jmp     short loc_1016BAEB
0x1016badc  mov     Subject, [ebp+Memory]; Memory
0x1016badf  call    _EnterpriseContextLibMemFree@4; EnterpriseContextLibMemFree(x)
0x1016bae4  jmp     short loc_1016BAEB
0x1016bae6  mov     ebx, 0C0000017h
0x1016baeb  mov     Subject, [ebp+var_4]
0x1016baee  mov     eax, ebx
0x1016baf0  pop     edi
0x1016baf1  pop     esi
0x1016baf2  xor     Subject, ebp; cookie
0x1016baf4  pop     ebx
0x1016baf5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1016bafa  leave
0x1016bafb  retn    4
```
