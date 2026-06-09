# GetPointersOfAttributesValues(x,x,x,x,x,x)

- ea: `0x1016b840`
- end: `0x1016b9a2`
- name: `_GetPointersOfAttributesValues@24`
- size: `354`
- prototype: `void __userpurge(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *Attributes@<ecx>, unsigned __int64 **EvaluationFlags@<edx>, unsigned __int64 **PolicyFlags, unsigned int *EnterpriseIdCount, _UNICODE_STRING **EnterpriseIds, _UNICODE_STRING **Attributes@<ecx>)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1016bb04`
- `0x1016bb64`

## callees

- `0x1016b840`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1016b8de`
- `ntdll!RtlCompareMemory` at `0x1016b91f`
- `ntdll!RtlCompareMemory` at `0x1016b95b`
- `ntdll!RtlCompareMemory` at `0x1016b8de`
- `ntdll!RtlCompareMemory` at `0x1016b91f`
- `ntdll!RtlCompareMemory` at `0x1016b95b`

## pseudocode

```c
unsigned __int64 **__fastcall GetPointersOfAttributesValues(
        int a1,
        _DWORD *a2,
        unsigned __int64 **PolicyFlags,
        unsigned int *EnterpriseIdCount,
        _UNICODE_STRING **EnterpriseIds,
        int a6)
{
  unsigned __int64 **result; // eax
  unsigned int *v8; // ecx
  unsigned int v9; // edi
  int v10; // esi
  unsigned __int16 *v11; // edi
  SIZE_T v12; // esi
  SIZE_T v13; // eax
  SIZE_T v14; // esi
  SIZE_T v15; // eax
  SIZE_T v16; // esi
  SIZE_T v17; // eax
  unsigned int i; // [esp+Ch] [ebp-Ch]
  _DWORD *v19; // [esp+10h] [ebp-8h]

  result = PolicyFlags;
  v19 = a2;
  if ( PolicyFlags )
    *PolicyFlags = 0;
  v8 = EnterpriseIdCount;
  if ( EnterpriseIdCount )
    *EnterpriseIdCount = 0;
  if ( EnterpriseIds )
    *EnterpriseIds = 0;
  if ( a2 )
    *a2 = 0;
  if ( PolicyFlags || EnterpriseIdCount || EnterpriseIds || a2 )
  {
    if ( a1 )
    {
      v9 = 0;
      v10 = a1;
      for ( i = 0; v9 < *(_DWORD *)(v10 + 4); i = v9 )
      {
        v11 = (unsigned __int16 *)(*(_DWORD *)(v10 + 8) + 24 * v9);
        if ( !*((_DWORD *)v11 + 4) || !*((_DWORD *)v11 + 5) )
          goto LABEL_37;
        if ( result && (*v11 & 0xFFFE) == 0x22 )
        {
          v12 = *v11;
          v13 = RtlCompareMemory(*((const void **)v11 + 1), L"EDP://PolicyFlags", v12);
          a2 = v19;
          if ( v13 == v12 )
          {
            *PolicyFlags = (unsigned __int64 *)*((_DWORD *)v11 + 5);
            v8 = EnterpriseIdCount;
            goto LABEL_35;
          }
          v8 = EnterpriseIdCount;
        }
        if ( a2
          && (*v11 & 0xFFFE) == 0x2A
          && (v14 = *v11,
              v15 = RtlCompareMemory(*((const void **)v11 + 1), L"EDP://EvaluationFlags", v14),
              a2 = v19,
              v8 = EnterpriseIdCount,
              v15 == v14) )
        {
          *v19 = *((_DWORD *)v11 + 5);
        }
        else if ( (v8 || EnterpriseIds) && (*v11 & 0xFFFE) == 0x26 )
        {
          v16 = *v11;
          v17 = RtlCompareMemory(*((const void **)v11 + 1), L"EDP://EnterpriseIds", v16);
          v8 = EnterpriseIdCount;
          if ( v17 == v16 )
          {
            if ( EnterpriseIdCount )
              *EnterpriseIdCount = *((_DWORD *)v11 + 4);
            a2 = v19;
            v10 = a1;
            if ( EnterpriseIds )
              *EnterpriseIds = (_UNICODE_STRING *)*((_DWORD *)v11 + 5);
            goto LABEL_36;
          }
          a2 = v19;
        }
LABEL_35:
        v10 = a1;
LABEL_36:
        result = PolicyFlags;
LABEL_37:
        v9 = i + 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1016b840  mov     edi, edi
0x1016b842  push    ebp
0x1016b843  mov     ebp, esp
0x1016b845  sub     esp, 0Ch
0x1016b848  mov     eax, [ebp+PolicyFlags]
0x1016b84b  push    ebx
0x1016b84c  push    esi
0x1016b84d  push    edi
0x1016b84e  mov     edi, Attributes
0x1016b850  mov     [ebp+var_8], EvaluationFlags
0x1016b853  xor     esi, esi
0x1016b855  mov     [ebp+var_4], edi
0x1016b858  test    eax, eax
0x1016b85a  jz      short loc_1016B85E
0x1016b85c  mov     [eax], esi
0x1016b85e  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b861  test    Attributes, Attributes
0x1016b863  jz      short loc_1016B867
0x1016b865  mov     [Attributes], esi
0x1016b867  mov     ebx, [ebp+EnterpriseIds]
0x1016b86a  test    ebx, ebx
0x1016b86c  jz      short loc_1016B870
0x1016b86e  mov     [ebx], esi
0x1016b870  test    EvaluationFlags, EvaluationFlags
0x1016b872  jz      short loc_1016B876
0x1016b874  mov     [EvaluationFlags], esi
0x1016b876  test    eax, eax
0x1016b878  jnz     short loc_1016B88A
0x1016b87a  test    Attributes, Attributes
0x1016b87c  jnz     short loc_1016B88A
0x1016b87e  test    ebx, ebx
0x1016b880  jnz     short loc_1016B88A
0x1016b882  test    EvaluationFlags, EvaluationFlags
0x1016b884  jz      loc_1016B99B
0x1016b88a  test    edi, edi
0x1016b88c  jz      loc_1016B99B
0x1016b892  mov     edi, esi
0x1016b894  mov     esi, [ebp+var_4]
0x1016b897  mov     [ebp+var_C], edi
0x1016b89a  cmp     [esi+4], edi
0x1016b89d  jbe     loc_1016B99B
0x1016b8a3  imul    edi, 18h
0x1016b8a6  add     edi, [esi+8]
0x1016b8a9  cmp     dword ptr [edi+10h], 0
0x1016b8ad  jz      loc_1016B98B
0x1016b8b3  cmp     dword ptr [edi+14h], 0
0x1016b8b7  jz      loc_1016B98B
0x1016b8bd  test    eax, eax
0x1016b8bf  jz      short loc_1016B8FE
0x1016b8c1  movzx   eax, word ptr [edi]
0x1016b8c4  and     eax, 0FFFEh
0x1016b8c9  cmp     ax, 22h ; '"'
0x1016b8cd  jnz     short loc_1016B8FE
0x1016b8cf  movzx   eax, word ptr [edi]
0x1016b8d2  movzx   esi, word ptr [edi]
0x1016b8d5  push    eax; Length
0x1016b8d6  push    offset POLICY_FLAGS_ATTRIBUTE_NAME; "EDP://PolicyFlags"
0x1016b8db  push    dword ptr [edi+4]; Source1
0x1016b8de  call    ds:__imp__RtlCompareMemory@12; RtlCompareMemory(x,x,x)
0x1016b8e4  mov     EvaluationFlags, [ebp+var_8]
0x1016b8e7  cmp     eax, esi
0x1016b8e9  jnz     short loc_1016B8FB
0x1016b8eb  mov     Attributes, [ebp+PolicyFlags]
0x1016b8ee  mov     eax, [edi+14h]
0x1016b8f1  mov     [Attributes], eax
0x1016b8f3  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b8f6  jmp     loc_1016B985
0x1016b8fb  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b8fe  test    EvaluationFlags, EvaluationFlags
0x1016b900  jz      short loc_1016B936
0x1016b902  movzx   eax, word ptr [edi]
0x1016b905  and     eax, 0FFFEh
0x1016b90a  cmp     ax, 2Ah ; '*'
0x1016b90e  jnz     short loc_1016B936
0x1016b910  movzx   eax, word ptr [edi]
0x1016b913  movzx   esi, word ptr [edi]
0x1016b916  push    eax; Length
0x1016b917  push    offset EVALUATION_FLAGS_ATTRIBUTE_NAME; "EDP://EvaluationFlags"
0x1016b91c  push    dword ptr [edi+4]; Source1
0x1016b91f  call    ds:__imp__RtlCompareMemory@12; RtlCompareMemory(x,x,x)
0x1016b925  mov     EvaluationFlags, [ebp+var_8]
0x1016b928  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b92b  cmp     eax, esi
0x1016b92d  jnz     short loc_1016B936
0x1016b92f  mov     eax, [edi+14h]
0x1016b932  mov     [EvaluationFlags], eax
0x1016b934  jmp     short loc_1016B985
0x1016b936  test    Attributes, Attributes
0x1016b938  jnz     short loc_1016B93E
0x1016b93a  test    ebx, ebx
0x1016b93c  jz      short loc_1016B985
0x1016b93e  movzx   eax, word ptr [edi]
0x1016b941  and     eax, 0FFFEh
0x1016b946  cmp     ax, 26h ; '&'
0x1016b94a  jnz     short loc_1016B985
0x1016b94c  movzx   eax, word ptr [edi]
0x1016b94f  movzx   esi, word ptr [edi]
0x1016b952  push    eax; Length
0x1016b953  push    offset ENTERPRISE_IDS_ATTRIBUTE_NAME; "EDP://EnterpriseIds"
0x1016b958  push    dword ptr [edi+4]; Source1
0x1016b95b  call    ds:__imp__RtlCompareMemory@12; RtlCompareMemory(x,x,x)
0x1016b961  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b964  cmp     eax, esi
0x1016b966  jnz     short loc_1016B982
0x1016b968  test    Attributes, Attributes
0x1016b96a  jz      short loc_1016B971
0x1016b96c  mov     eax, [edi+10h]
0x1016b96f  mov     [Attributes], eax
0x1016b971  mov     EvaluationFlags, [ebp+var_8]
0x1016b974  mov     esi, [ebp+var_4]
0x1016b977  test    ebx, ebx
0x1016b979  jz      short loc_1016B988
0x1016b97b  mov     eax, [edi+14h]
0x1016b97e  mov     [ebx], eax
0x1016b980  jmp     short loc_1016B988
0x1016b982  mov     EvaluationFlags, [ebp+var_8]
0x1016b985  mov     esi, [ebp+var_4]
0x1016b988  mov     eax, [ebp+PolicyFlags]
0x1016b98b  mov     edi, [ebp+var_C]
0x1016b98e  inc     edi
0x1016b98f  mov     [ebp+var_C], edi
0x1016b992  cmp     edi, [esi+4]
0x1016b995  jb      loc_1016B8A3
0x1016b99b  pop     edi
0x1016b99c  pop     esi
0x1016b99d  pop     ebx
0x1016b99e  leave
0x1016b99f  retn    10h
```
