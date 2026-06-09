# GetPointersOfAttributesValues

- ea: `0x180175d08`
- end: `0x180175eb1`
- name: `GetPointersOfAttributesValues`
- size: `425`
- prototype: `void __fastcall(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *Attributes, unsigned __int64 **EvaluationFlags, unsigned __int64 **PolicyFlags, unsigned int *EnterpriseIdCount, _UNICODE_STRING **EnterpriseIds, _UNICODE_STRING **Attributes)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180176074`
- `0x1801760fc`

## callees

- `0x180175d08`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180175ddb`
- `ntdll!RtlCompareMemory` at `0x180175e1b`
- `ntdll!RtlCompareMemory` at `0x180175e86`
- `ntdll!RtlCompareMemory` at `0x180175ddb`
- `ntdll!RtlCompareMemory` at `0x180175e1b`
- `ntdll!RtlCompareMemory` at `0x180175e86`

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
0x180175d08  mov     [rsp+arg_0], Attributes
0x180175d0d  push    rbx
0x180175d0e  push    rbp
0x180175d0f  push    rsi
0x180175d10  push    rdi
0x180175d11  push    r12
0x180175d13  push    r13
0x180175d15  push    r14
0x180175d17  push    r15
0x180175d19  sub     rsp, 28h
0x180175d1d  mov     r15, EnterpriseIdCount
0x180175d20  mov     r12, PolicyFlags
0x180175d23  mov     rbp, EvaluationFlags
0x180175d26  mov     rsi, Attributes
0x180175d29  test    PolicyFlags, PolicyFlags
0x180175d2c  jz      short loc_180175D35
0x180175d2e  mov     qword ptr [PolicyFlags], 0
0x180175d35  test    r15, r15
0x180175d38  jz      short loc_180175D41
0x180175d3a  mov     dword ptr [EnterpriseIdCount], 0
0x180175d41  mov     r14, [rsp+68h+arg_20]
0x180175d49  test    r14, r14
0x180175d4c  jz      short loc_180175D55
0x180175d4e  mov     qword ptr [r14], 0
0x180175d55  test    rbp, rbp
0x180175d58  jz      short loc_180175D61
0x180175d5a  mov     qword ptr [EvaluationFlags], 0
0x180175d61  test    r12, r12
0x180175d64  jnz     short loc_180175D79
0x180175d66  test    r15, r15
0x180175d69  jnz     short loc_180175D79
0x180175d6b  test    r14, r14
0x180175d6e  jnz     short loc_180175D79
0x180175d70  test    rbp, rbp
0x180175d73  jz      loc_180175E46
0x180175d79  test    Attributes, Attributes
0x180175d7c  jz      loc_180175E46
0x180175d82  xor     r13d, r13d
0x180175d85  cmp     [Attributes+4], r13d
0x180175d89  jbe     loc_180175E46
0x180175d8f  mov     ecx, 0FFFEh
0x180175d94  mov     rsi, [rsi+8]
0x180175d98  lea     rdi, ds:0[r13*4]
0x180175da0  add     rdi, r13
0x180175da3  cmp     dword ptr [rsi+rdi*8+18h], 0
0x180175da8  jz      loc_180175E34
0x180175dae  cmp     qword ptr [rsi+rdi*8+20h], 0
0x180175db4  jz      short loc_180175E34
0x180175db6  test    r12, r12
0x180175db9  jz      short loc_180175DF6
0x180175dbb  movzx   eax, word ptr [rsi+rdi*8]
0x180175dbf  and     ax, cx
0x180175dc2  cmp     ax, 22h ; '"'
0x180175dc6  jnz     short loc_180175DF6
0x180175dc8  movzx   ebx, word ptr [rsi+rdi*8]
0x180175dcc  lea     EvaluationFlags, POLICY_FLAGS_ATTRIBUTE_NAME; Source2
0x180175dd3  mov     Attributes, [rsi+rdi*8+8]; Source1
0x180175dd8  mov     r8d, ebx; Length
0x180175ddb  call    cs:__imp_RtlCompareMemory
0x180175de1  mov     ecx, 0FFFEh
0x180175de6  cmp     rax, rbx
0x180175de9  jnz     short loc_180175DF6
0x180175deb  mov     rax, [rsi+rdi*8+20h]
0x180175df0  mov     [r12], rax
0x180175df4  jmp     short loc_180175E34
0x180175df6  test    rbp, rbp
0x180175df9  jz      short loc_180175E57
0x180175dfb  movzx   eax, word ptr [rsi+rdi*8]
0x180175dff  and     ax, cx
0x180175e02  cmp     ax, 2Ah ; '*'
0x180175e06  jnz     short loc_180175E57
0x180175e08  movzx   ebx, word ptr [rsi+rdi*8]
0x180175e0c  lea     EvaluationFlags, EVALUATION_FLAGS_ATTRIBUTE_NAME; Source2
0x180175e13  mov     Attributes, [rsi+rdi*8+8]; Source1
0x180175e18  mov     r8d, ebx; Length
0x180175e1b  call    cs:__imp_RtlCompareMemory
0x180175e21  cmp     rax, rbx
0x180175e24  jnz     short loc_180175E57
0x180175e26  mov     rax, [rsi+rdi*8+20h]
0x180175e2b  mov     [rbp+0], rax
0x180175e2f  mov     ecx, 0FFFEh
0x180175e34  mov     rsi, [rsp+68h+arg_0]
0x180175e39  inc     r13d
0x180175e3c  cmp     r13d, [rsi+4]
0x180175e40  jb      loc_180175D94
0x180175e46  add     rsp, 28h
0x180175e4a  pop     r15
0x180175e4c  pop     r14
0x180175e4e  pop     r13
0x180175e50  pop     r12
0x180175e52  pop     rdi
0x180175e53  pop     rsi
0x180175e54  pop     rbp
0x180175e55  pop     rbx
0x180175e56  retn
0x180175e57  test    r15, r15
0x180175e5a  jnz     short loc_180175E61
0x180175e5c  test    r14, r14
0x180175e5f  jz      short loc_180175E2F
0x180175e61  movzx   eax, word ptr [rsi+rdi*8]
0x180175e65  mov     ecx, 0FFFEh
0x180175e6a  and     ax, cx
0x180175e6d  cmp     ax, 26h ; '&'
0x180175e71  jnz     short loc_180175E34
0x180175e73  movzx   ebx, word ptr [rsi+rdi*8]
0x180175e77  lea     EvaluationFlags, ENTERPRISE_IDS_ATTRIBUTE_NAME; Source2
0x180175e7e  mov     Attributes, [rsi+rdi*8+8]; Source1
0x180175e83  mov     r8d, ebx; Length
0x180175e86  call    cs:__imp_RtlCompareMemory
0x180175e8c  cmp     rax, rbx
0x180175e8f  jnz     short loc_180175E2F
0x180175e91  test    r15, r15
0x180175e94  jz      short loc_180175E9D
0x180175e96  mov     eax, [rsi+rdi*8+18h]
0x180175e9a  mov     [r15], eax
0x180175e9d  mov     ecx, 0FFFEh
0x180175ea2  test    r14, r14
0x180175ea5  jz      short loc_180175E34
0x180175ea7  mov     rax, [rsi+rdi*8+20h]
0x180175eac  mov     [r14], rax
0x180175eaf  jmp     short loc_180175E34
```
