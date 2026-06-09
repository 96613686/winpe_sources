# QueryAttributes(x,x,x)

- ea: `0x1016b8b8`
- end: `0x1016ba0e`
- name: `_QueryAttributes@12`
- size: `342`
- prototype: `int __userpurge@<eax>(_SUBJECT *Subject@<ecx>, unsigned int AttributesToQuery@<edx>, _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **AttributesInBuf)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1016ba14`
- `0x1016ba74`

## callees

- `0x1006b510`
- `0x1016b64e`
- `0x1016b667`
- `0x1016b8b8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1016b900`
- `ntdll!RtlInitUnicodeString` at `0x1016b91e`
- `ntdll!RtlInitUnicodeString` at `0x1016b93c`
- `ntdll!RtlInitUnicodeString` at `0x1016b95a`
- `ntdll!RtlInitUnicodeString` at `0x1016b978`
- `ntdll!RtlInitUnicodeString` at `0x1016b900`
- `ntdll!RtlInitUnicodeString` at `0x1016b91e`
- `ntdll!RtlInitUnicodeString` at `0x1016b93c`
- `ntdll!RtlInitUnicodeString` at `0x1016b95a`
- `ntdll!RtlInitUnicodeString` at `0x1016b978`
- `ntdll!NtQuerySecurityAttributesToken` at `0x1016b9a8`
- `ntdll!NtQuerySecurityAttributesToken` at `0x1016b9a8`

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
0x1016b8b8  mov     edi, edi
0x1016b8ba  push    ebp
0x1016b8bb  mov     ebp, esp
0x1016b8bd  sub     esp, 34h
0x1016b8c0  mov     eax, ___security_cookie
0x1016b8c5  xor     eax, ebp
0x1016b8c7  mov     [ebp+var_4], eax
0x1016b8ca  push    ebx
0x1016b8cb  push    esi
0x1016b8cc  mov     esi, [ebp+AttributesInBuf]
0x1016b8cf  xor     eax, eax
0x1016b8d1  push    edi
0x1016b8d2  push    8
0x1016b8d4  mov     [ebp+var_34], Subject
0x1016b8d7  lea     edi, [ebp+AttributeNames]
0x1016b8da  pop     Subject
0x1016b8db  mov     [ebp+var_30], esi
0x1016b8de  xor     ebx, ebx
0x1016b8e0  mov     [esi], eax
0x1016b8e2  xor     esi, esi
0x1016b8e4  mov     [ebp+Memory], AttributesToQuery
0x1016b8e7  mov     [ebp+AttributesBufferRequiredSize], eax
0x1016b8ea  rep stosd
0x1016b8ec  push    0Ch
0x1016b8ee  pop     edi
0x1016b8ef  test    dl, 1
0x1016b8f2  jz      short loc_1016B90A
0x1016b8f4  push    50h ; 'P'
0x1016b8f6  pop     edi
0x1016b8f7  push    offset POLICY_FLAGS_ATTRIBUTE_NAME; "EDP://PolicyFlags"
0x1016b8fc  lea     eax, [ebp+AttributeNames]
0x1016b8ff  push    eax; DestinationString
0x1016b900  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016b906  mov     AttributesToQuery, [ebp+Memory]
0x1016b909  inc     esi
0x1016b90a  test    dl, 2
0x1016b90d  jz      short loc_1016B928
0x1016b90f  lea     eax, [ebp+AttributeNames]
0x1016b912  sub     edi, 0FFFFFF80h
0x1016b915  push    offset ENTERPRISE_IDS_ATTRIBUTE_NAME; "EDP://EnterpriseIds"
0x1016b91a  lea     eax, [eax+esi*8]
0x1016b91d  push    eax; DestinationString
0x1016b91e  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016b924  mov     AttributesToQuery, [ebp+Memory]
0x1016b927  inc     esi
0x1016b928  test    dl, 4
0x1016b92b  jz      short loc_1016B946
0x1016b92d  lea     eax, [ebp+AttributeNames]
0x1016b930  sub     edi, 0FFFFFF80h
0x1016b933  push    offset INTENT_ENTERPRISE_ID_ATTRIBUTE_NAME; "PEDP://IntentEnterpriseId"
0x1016b938  lea     eax, [eax+esi*8]
0x1016b93b  push    eax; DestinationString
0x1016b93c  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016b942  mov     AttributesToQuery, [ebp+Memory]
0x1016b945  inc     esi
0x1016b946  test    dl, 8
0x1016b949  jz      short loc_1016B964
0x1016b94b  lea     eax, [ebp+AttributeNames]
0x1016b94e  add     edi, 44h ; 'D'
0x1016b951  push    offset EVALUATION_FLAGS_ATTRIBUTE_NAME; "EDP://EvaluationFlags"
0x1016b956  lea     eax, [eax+esi*8]
0x1016b959  push    eax; DestinationString
0x1016b95a  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016b960  mov     AttributesToQuery, [ebp+Memory]
0x1016b963  inc     esi
0x1016b964  test    dl, 10h
0x1016b967  jz      short loc_1016B97F
0x1016b969  lea     eax, [ebp+AttributeNames]
0x1016b96c  sub     edi, 0FFFFFF80h
0x1016b96f  push    offset EXEMPT_ENTERPRISE_IDS_ATTRIBUTE_NAME; "EDP://ExemptEnterpriseIds"
0x1016b974  lea     eax, [eax+esi*8]
0x1016b977  push    eax; DestinationString
0x1016b978  call    ds:__imp__RtlInitUnicodeString@8; RtlInitUnicodeString(x,x)
0x1016b97e  inc     esi
0x1016b97f  test    ebx, ebx
0x1016b981  jz      short loc_1016B98A
0x1016b983  mov     Subject, ebx; Memory
0x1016b985  call    _EnterpriseContextLibMemFree@4; EnterpriseContextLibMemFree(x)
0x1016b98a  mov     Subject, edi; NumberOfBytes
0x1016b98c  call    _EnterpriseContextLibMemAllocPaged@8; EnterpriseContextLibMemAllocPaged(x,x)
0x1016b991  mov     [ebp+Memory], eax
0x1016b994  test    eax, eax
0x1016b996  jz      short loc_1016B9F6
0x1016b998  lea     Subject, [ebp+AttributesBufferRequiredSize]
0x1016b99b  push    Subject
0x1016b99c  push    edi
0x1016b99d  push    eax
0x1016b99e  push    esi
0x1016b99f  lea     eax, [ebp+AttributeNames]
0x1016b9a2  push    eax
0x1016b9a3  mov     eax, [ebp+var_34]
0x1016b9a6  push    dword ptr [eax]
0x1016b9a8  call    ds:__imp__NtQuerySecurityAttributesToken@24; NtQuerySecurityAttributesToken(x,x,x,x,x,x)
0x1016b9ae  mov     ebx, eax
0x1016b9b0  cmp     ebx, 0C0000023h
0x1016b9b6  jnz     short loc_1016B9C5
0x1016b9b8  cmp     edi, [ebp+AttributesBufferRequiredSize]
0x1016b9bb  jnb     short loc_1016B9EC
0x1016b9bd  mov     edi, [ebp+AttributesBufferRequiredSize]
0x1016b9c0  mov     ebx, [ebp+Memory]
0x1016b9c3  jmp     short loc_1016B97F
0x1016b9c5  cmp     ebx, 0C0000225h
0x1016b9cb  jnz     short loc_1016B9DE
0x1016b9cd  mov     Subject, [ebp+Memory]; Memory
0x1016b9d0  call    _EnterpriseContextLibMemFree@4; EnterpriseContextLibMemFree(x)
0x1016b9d5  mov     eax, [ebp+var_30]
0x1016b9d8  xor     ebx, ebx
0x1016b9da  mov     [eax], ebx
0x1016b9dc  jmp     short loc_1016B9FB
0x1016b9de  test    ebx, ebx
0x1016b9e0  js      short loc_1016B9EC
0x1016b9e2  mov     eax, [ebp+var_30]
0x1016b9e5  mov     Subject, [ebp+Memory]
0x1016b9e8  mov     [eax], Subject
0x1016b9ea  jmp     short loc_1016B9FB
0x1016b9ec  mov     Subject, [ebp+Memory]; Memory
0x1016b9ef  call    _EnterpriseContextLibMemFree@4; EnterpriseContextLibMemFree(x)
0x1016b9f4  jmp     short loc_1016B9FB
0x1016b9f6  mov     ebx, 0C0000017h
0x1016b9fb  mov     Subject, [ebp+var_4]
0x1016b9fe  mov     eax, ebx
0x1016ba00  pop     edi
0x1016ba01  pop     esi
0x1016ba02  xor     Subject, ebp; cookie
0x1016ba04  pop     ebx
0x1016ba05  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1016ba0a  leave
0x1016ba0b  retn    4
```
