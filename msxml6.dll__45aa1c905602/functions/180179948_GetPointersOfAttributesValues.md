# GetPointersOfAttributesValues

- ea: `0x180179948`
- end: `0x180179b0b`
- name: `GetPointersOfAttributesValues`
- size: `451`
- prototype: `void __fastcall(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *Attributes, unsigned __int64 **EvaluationFlags, unsigned __int64 **PolicyFlags, unsigned int *EnterpriseIdCount, _UNICODE_STRING **EnterpriseIds, _UNICODE_STRING **Attributes)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180179cf8`
- `0x180179d80`

## callees

- `0x180179948`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180179a1f`
- `ntdll!RtlCompareMemory` at `0x180179a65`
- `ntdll!RtlCompareMemory` at `0x180179ad7`
- `ntdll!RtlCompareMemory` at `0x180179a1f`
- `ntdll!RtlCompareMemory` at `0x180179a65`
- `ntdll!RtlCompareMemory` at `0x180179ad7`

## pseudocode

```c
void __fastcall GetPointersOfAttributesValues(
        _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *Attributes,
        _TOKEN_SECURITY_ATTRIBUTE_V1::<unnamed_type_Values> *EvaluationFlags,
        _TOKEN_SECURITY_ATTRIBUTE_V1::<unnamed_type_Values> *PolicyFlags,
        unsigned int *EnterpriseIdCount,
        _TOKEN_SECURITY_ATTRIBUTE_V1::<unnamed_type_Values> *EnterpriseIds)
{
  _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v8; // rsi
  __int64 i; // r13
  _TOKEN_SECURITY_ATTRIBUTES_INFORMATION::<unnamed_type_Attribute> v10; // rsi
  SIZE_T v11; // rbx
  SIZE_T v12; // rbx
  SIZE_T Length; // rbx

  v8 = Attributes;
  if ( PolicyFlags )
    PolicyFlags->pInt64 = 0;
  if ( EnterpriseIdCount )
    *EnterpriseIdCount = 0;
  if ( EnterpriseIds )
    EnterpriseIds->pInt64 = 0;
  if ( EvaluationFlags )
    EvaluationFlags->pInt64 = 0;
  if ( PolicyFlags || EnterpriseIdCount || EnterpriseIds || EvaluationFlags )
  {
    if ( Attributes )
    {
      for ( i = 0; (unsigned int)i < Attributes->AttributeCount; i = (unsigned int)(i + 1) )
      {
        v10.pAttributeV1 = (_TOKEN_SECURITY_ATTRIBUTE_V1 *)v8->Attribute;
        if ( v10.pAttributeV1[i].ValueCount && v10.pAttributeV1[i].Values.pInt64 )
        {
          if ( PolicyFlags
            && (v10.pAttributeV1[i].Name.Length & 0xFFFE) == 0x22
            && (v11 = v10.pAttributeV1[i].Name.Length,
                RtlCompareMemory(v10.pAttributeV1[i].Name.Buffer, POLICY_FLAGS_ATTRIBUTE_NAME, v11) == v11) )
          {
            PolicyFlags->pInt64 = (__int64 *)v10.pAttributeV1[i].Values;
          }
          else if ( EvaluationFlags
                 && (v10.pAttributeV1[i].Name.Length & 0xFFFE) == 0x2A
                 && (v12 = v10.pAttributeV1[i].Name.Length,
                     RtlCompareMemory(v10.pAttributeV1[i].Name.Buffer, EVALUATION_FLAGS_ATTRIBUTE_NAME, v12) == v12) )
          {
            EvaluationFlags->pInt64 = (__int64 *)v10.pAttributeV1[i].Values;
          }
          else if ( (EnterpriseIdCount || EnterpriseIds) && (v10.pAttributeV1[i].Name.Length & 0xFFFE) == 0x26 )
          {
            Length = v10.pAttributeV1[i].Name.Length;
            if ( RtlCompareMemory(v10.pAttributeV1[i].Name.Buffer, ENTERPRISE_IDS_ATTRIBUTE_NAME, Length) == Length )
            {
              if ( EnterpriseIdCount )
                *EnterpriseIdCount = v10.pAttributeV1[i].ValueCount;
              if ( EnterpriseIds )
                EnterpriseIds->pInt64 = (__int64 *)v10.pAttributeV1[i].Values;
            }
          }
        }
        v8 = Attributes;
      }
    }
  }
}

```

## disassembly

```asm
0x180179948  mov     [rsp+arg_0], Attributes
0x18017994d  push    rbx
0x18017994e  push    rbp
0x18017994f  push    rsi
0x180179950  push    rdi
0x180179951  push    r12
0x180179953  push    r13
0x180179955  push    r14
0x180179957  push    r15
0x180179959  sub     rsp, 28h
0x18017995d  mov     r15, EnterpriseIdCount
0x180179960  mov     r12, PolicyFlags
0x180179963  mov     rbp, EvaluationFlags
0x180179966  mov     rsi, Attributes
0x180179969  test    PolicyFlags, PolicyFlags
0x18017996c  jz      short loc_180179975
0x18017996e  mov     qword ptr [PolicyFlags], 0
0x180179975  test    r15, r15
0x180179978  jz      short loc_180179981
0x18017997a  mov     dword ptr [EnterpriseIdCount], 0
0x180179981  mov     r14, [rsp+68h+arg_20]
0x180179989  test    r14, r14
0x18017998c  jz      short loc_180179995
0x18017998e  mov     qword ptr [r14], 0
0x180179995  test    rbp, rbp
0x180179998  jz      short loc_1801799A1
0x18017999a  mov     qword ptr [EvaluationFlags], 0
0x1801799a1  test    r12, r12
0x1801799a4  jnz     short loc_1801799B9
0x1801799a6  test    r15, r15
0x1801799a9  jnz     short loc_1801799B9
0x1801799ab  test    r14, r14
0x1801799ae  jnz     short loc_1801799B9
0x1801799b0  test    rbp, rbp
0x1801799b3  jz      loc_180179A96
0x1801799b9  test    Attributes, Attributes
0x1801799bc  jz      loc_180179A96
0x1801799c2  xor     r13d, r13d
0x1801799c5  cmp     [Attributes+4], r13d
0x1801799c9  jbe     loc_180179A96
0x1801799cf  mov     ecx, 0FFFEh
0x1801799d4  mov     rsi, [rsi+8]
0x1801799d8  lea     rdi, ds:0[r13*4]
0x1801799e0  add     rdi, r13
0x1801799e3  cmp     dword ptr [rsi+rdi*8+18h], 0
0x1801799e8  jz      loc_180179A84
0x1801799ee  cmp     qword ptr [rsi+rdi*8+20h], 0
0x1801799f4  jz      loc_180179A84
0x1801799fa  test    r12, r12
0x1801799fd  jz      short loc_180179A40
0x1801799ff  movzx   eax, word ptr [rsi+rdi*8]
0x180179a03  and     ax, cx
0x180179a06  cmp     ax, 22h ; '"'
0x180179a0a  jnz     short loc_180179A40
0x180179a0c  movzx   ebx, word ptr [rsi+rdi*8]
0x180179a10  lea     EvaluationFlags, POLICY_FLAGS_ATTRIBUTE_NAME; Source2
0x180179a17  mov     Attributes, [rsi+rdi*8+8]; Source1
0x180179a1c  mov     r8d, ebx; Length
0x180179a1f  call    cs:__imp_RtlCompareMemory
0x180179a26  nop     dword ptr [rax+rax+00h]
0x180179a2b  mov     ecx, 0FFFEh
0x180179a30  cmp     rax, rbx
0x180179a33  jnz     short loc_180179A40
0x180179a35  mov     rax, [rsi+rdi*8+20h]
0x180179a3a  mov     [r12], rax
0x180179a3e  jmp     short loc_180179A84
0x180179a40  test    rbp, rbp
0x180179a43  jz      short loc_180179AA8
0x180179a45  movzx   eax, word ptr [rsi+rdi*8]
0x180179a49  and     ax, cx
0x180179a4c  cmp     ax, 2Ah ; '*'
0x180179a50  jnz     short loc_180179AA8
0x180179a52  movzx   ebx, word ptr [rsi+rdi*8]
0x180179a56  lea     EvaluationFlags, EVALUATION_FLAGS_ATTRIBUTE_NAME; Source2
0x180179a5d  mov     Attributes, [rsi+rdi*8+8]; Source1
0x180179a62  mov     r8d, ebx; Length
0x180179a65  call    cs:__imp_RtlCompareMemory
0x180179a6c  nop     dword ptr [rax+rax+00h]
0x180179a71  cmp     rax, rbx
0x180179a74  jnz     short loc_180179AA8
0x180179a76  mov     rax, [rsi+rdi*8+20h]
0x180179a7b  mov     [rbp+0], rax
0x180179a7f  mov     ecx, 0FFFEh
0x180179a84  mov     rsi, [rsp+68h+arg_0]
0x180179a89  inc     r13d
0x180179a8c  cmp     r13d, [rsi+4]
0x180179a90  jb      loc_1801799D4
0x180179a96  add     rsp, 28h
0x180179a9a  pop     r15
0x180179a9c  pop     r14
0x180179a9e  pop     r13
0x180179aa0  pop     r12
0x180179aa2  pop     rdi
0x180179aa3  pop     rsi
0x180179aa4  pop     rbp
0x180179aa5  pop     rbx
0x180179aa6  retn
0x180179aa8  test    r15, r15
0x180179aab  jnz     short loc_180179AB2
0x180179aad  test    r14, r14
0x180179ab0  jz      short loc_180179A7F
0x180179ab2  movzx   eax, word ptr [rsi+rdi*8]
0x180179ab6  mov     ecx, 0FFFEh
0x180179abb  and     ax, cx
0x180179abe  cmp     ax, 26h ; '&'
0x180179ac2  jnz     short loc_180179A84
0x180179ac4  movzx   ebx, word ptr [rsi+rdi*8]
0x180179ac8  lea     EvaluationFlags, ENTERPRISE_IDS_ATTRIBUTE_NAME; Source2
0x180179acf  mov     Attributes, [rsi+rdi*8+8]; Source1
0x180179ad4  mov     r8d, ebx; Length
0x180179ad7  call    cs:__imp_RtlCompareMemory
0x180179ade  nop     dword ptr [rax+rax+00h]
0x180179ae3  cmp     rax, rbx
0x180179ae6  jnz     short loc_180179A7F
0x180179ae8  test    r15, r15
0x180179aeb  jz      short loc_180179AF4
0x180179aed  mov     eax, [rsi+rdi*8+18h]
0x180179af1  mov     [r15], eax
0x180179af4  mov     ecx, 0FFFEh
0x180179af9  test    r14, r14
0x180179afc  jz      short loc_180179A84
0x180179afe  mov     rax, [rsi+rdi*8+20h]
0x180179b03  mov     [r14], rax
0x180179b06  jmp     loc_180179A84
```
