# GetPointersOfAttributesValues(x,x,x,x,x,x)

- ea: `0x1016b750`
- end: `0x1016b8b2`
- name: `_GetPointersOfAttributesValues@24`
- size: `354`
- prototype: `void __userpurge(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *Attributes@<ecx>, unsigned __int64 **EvaluationFlags@<edx>, unsigned __int64 **PolicyFlags, unsigned int *EnterpriseIdCount, _UNICODE_STRING **EnterpriseIds, _UNICODE_STRING **Attributes@<ecx>)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1016ba14`
- `0x1016ba74`

## callees

- `0x1016b750`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1016b7ee`
- `ntdll!RtlCompareMemory` at `0x1016b82f`
- `ntdll!RtlCompareMemory` at `0x1016b86b`
- `ntdll!RtlCompareMemory` at `0x1016b7ee`
- `ntdll!RtlCompareMemory` at `0x1016b82f`
- `ntdll!RtlCompareMemory` at `0x1016b86b`

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
0x1016b750  mov     edi, edi
0x1016b752  push    ebp
0x1016b753  mov     ebp, esp
0x1016b755  sub     esp, 0Ch
0x1016b758  mov     eax, [ebp+PolicyFlags]
0x1016b75b  push    ebx
0x1016b75c  push    esi
0x1016b75d  push    edi
0x1016b75e  mov     edi, Attributes
0x1016b760  mov     [ebp+var_8], EvaluationFlags
0x1016b763  xor     esi, esi
0x1016b765  mov     [ebp+var_4], edi
0x1016b768  test    eax, eax
0x1016b76a  jz      short loc_1016B76E
0x1016b76c  mov     [eax], esi
0x1016b76e  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b771  test    Attributes, Attributes
0x1016b773  jz      short loc_1016B777
0x1016b775  mov     [Attributes], esi
0x1016b777  mov     ebx, [ebp+EnterpriseIds]
0x1016b77a  test    ebx, ebx
0x1016b77c  jz      short loc_1016B780
0x1016b77e  mov     [ebx], esi
0x1016b780  test    EvaluationFlags, EvaluationFlags
0x1016b782  jz      short loc_1016B786
0x1016b784  mov     [EvaluationFlags], esi
0x1016b786  test    eax, eax
0x1016b788  jnz     short loc_1016B79A
0x1016b78a  test    Attributes, Attributes
0x1016b78c  jnz     short loc_1016B79A
0x1016b78e  test    ebx, ebx
0x1016b790  jnz     short loc_1016B79A
0x1016b792  test    EvaluationFlags, EvaluationFlags
0x1016b794  jz      loc_1016B8AB
0x1016b79a  test    edi, edi
0x1016b79c  jz      loc_1016B8AB
0x1016b7a2  mov     edi, esi
0x1016b7a4  mov     esi, [ebp+var_4]
0x1016b7a7  mov     [ebp+var_C], edi
0x1016b7aa  cmp     [esi+4], edi
0x1016b7ad  jbe     loc_1016B8AB
0x1016b7b3  imul    edi, 18h
0x1016b7b6  add     edi, [esi+8]
0x1016b7b9  cmp     dword ptr [edi+10h], 0
0x1016b7bd  jz      loc_1016B89B
0x1016b7c3  cmp     dword ptr [edi+14h], 0
0x1016b7c7  jz      loc_1016B89B
0x1016b7cd  test    eax, eax
0x1016b7cf  jz      short loc_1016B80E
0x1016b7d1  movzx   eax, word ptr [edi]
0x1016b7d4  and     eax, 0FFFEh
0x1016b7d9  cmp     ax, 22h ; '"'
0x1016b7dd  jnz     short loc_1016B80E
0x1016b7df  movzx   eax, word ptr [edi]
0x1016b7e2  movzx   esi, word ptr [edi]
0x1016b7e5  push    eax; Length
0x1016b7e6  push    offset POLICY_FLAGS_ATTRIBUTE_NAME; "EDP://PolicyFlags"
0x1016b7eb  push    dword ptr [edi+4]; Source1
0x1016b7ee  call    ds:__imp__RtlCompareMemory@12; RtlCompareMemory(x,x,x)
0x1016b7f4  mov     EvaluationFlags, [ebp+var_8]
0x1016b7f7  cmp     eax, esi
0x1016b7f9  jnz     short loc_1016B80B
0x1016b7fb  mov     Attributes, [ebp+PolicyFlags]
0x1016b7fe  mov     eax, [edi+14h]
0x1016b801  mov     [Attributes], eax
0x1016b803  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b806  jmp     loc_1016B895
0x1016b80b  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b80e  test    EvaluationFlags, EvaluationFlags
0x1016b810  jz      short loc_1016B846
0x1016b812  movzx   eax, word ptr [edi]
0x1016b815  and     eax, 0FFFEh
0x1016b81a  cmp     ax, 2Ah ; '*'
0x1016b81e  jnz     short loc_1016B846
0x1016b820  movzx   eax, word ptr [edi]
0x1016b823  movzx   esi, word ptr [edi]
0x1016b826  push    eax; Length
0x1016b827  push    offset EVALUATION_FLAGS_ATTRIBUTE_NAME; "EDP://EvaluationFlags"
0x1016b82c  push    dword ptr [edi+4]; Source1
0x1016b82f  call    ds:__imp__RtlCompareMemory@12; RtlCompareMemory(x,x,x)
0x1016b835  mov     EvaluationFlags, [ebp+var_8]
0x1016b838  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b83b  cmp     eax, esi
0x1016b83d  jnz     short loc_1016B846
0x1016b83f  mov     eax, [edi+14h]
0x1016b842  mov     [EvaluationFlags], eax
0x1016b844  jmp     short loc_1016B895
0x1016b846  test    Attributes, Attributes
0x1016b848  jnz     short loc_1016B84E
0x1016b84a  test    ebx, ebx
0x1016b84c  jz      short loc_1016B895
0x1016b84e  movzx   eax, word ptr [edi]
0x1016b851  and     eax, 0FFFEh
0x1016b856  cmp     ax, 26h ; '&'
0x1016b85a  jnz     short loc_1016B895
0x1016b85c  movzx   eax, word ptr [edi]
0x1016b85f  movzx   esi, word ptr [edi]
0x1016b862  push    eax; Length
0x1016b863  push    offset ENTERPRISE_IDS_ATTRIBUTE_NAME; "EDP://EnterpriseIds"
0x1016b868  push    dword ptr [edi+4]; Source1
0x1016b86b  call    ds:__imp__RtlCompareMemory@12; RtlCompareMemory(x,x,x)
0x1016b871  mov     Attributes, [ebp+EnterpriseIdCount]
0x1016b874  cmp     eax, esi
0x1016b876  jnz     short loc_1016B892
0x1016b878  test    Attributes, Attributes
0x1016b87a  jz      short loc_1016B881
0x1016b87c  mov     eax, [edi+10h]
0x1016b87f  mov     [Attributes], eax
0x1016b881  mov     EvaluationFlags, [ebp+var_8]
0x1016b884  mov     esi, [ebp+var_4]
0x1016b887  test    ebx, ebx
0x1016b889  jz      short loc_1016B898
0x1016b88b  mov     eax, [edi+14h]
0x1016b88e  mov     [ebx], eax
0x1016b890  jmp     short loc_1016B898
0x1016b892  mov     EvaluationFlags, [ebp+var_8]
0x1016b895  mov     esi, [ebp+var_4]
0x1016b898  mov     eax, [ebp+PolicyFlags]
0x1016b89b  mov     edi, [ebp+var_C]
0x1016b89e  inc     edi
0x1016b89f  mov     [ebp+var_C], edi
0x1016b8a2  cmp     edi, [esi+4]
0x1016b8a5  jb      loc_1016B7B3
0x1016b8ab  pop     edi
0x1016b8ac  pop     esi
0x1016b8ad  pop     ebx
0x1016b8ae  leave
0x1016b8af  retn    10h
```
