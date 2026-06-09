# GetAccountDomain

- ea: `0x18002a59c`
- end: `0x18002a695`
- name: `GetAccountDomain`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a850`

## callees

- `0x18002a59c`
- `0x18005582e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a644`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18002a604`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18002a604`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002a614`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002a67d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002a614`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002a67d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002a673`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002a673`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002a5e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002a5e4`

## pseudocode

```c
int __fastcall GetAccountDomain(_QWORD *a1)
{
  NTSTATUS v2; // eax
  NTSTATUS v4; // ebx
  __int64 v5; // rdi
  _WORD *v6; // rax
  _WORD *v7; // rbx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+70h] [rbp+20h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp+28h] BYREF

  *a1 = 0;
  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v2 )
    return v2 | 0x10000000;
  v4 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  if ( v4 )
  {
    LsaClose(PolicyHandle);
    return v4 | 0x10000000;
  }
  else
  {
    v5 = *(unsigned __int16 *)Buffer >> 1;
    v6 = CoTaskMemAlloc(saturated_mul((unsigned int)(v5 + 1), 2u));
    v7 = v6;
    if ( v6 )
    {
      memcpy_0(v6, *((const void **)Buffer + 1), *(unsigned __int16 *)Buffer);
      *a1 = v7;
      v7[v5] = 0;
    }
    LsaFreeMemory(Buffer);
    LsaClose(PolicyHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x18002a59c  mov     [rsp-18h+arg_10], rbx
0x18002a5a1  push    rbp
0x18002a5a2  push    rsi
0x18002a5a3  push    rdi
0x18002a5a4  mov     rbp, rsp
0x18002a5a7  sub     rsp, 50h
0x18002a5ab  xorps   xmm0, xmm0
0x18002a5ae  mov     qword ptr [rcx], 0
0x18002a5b5  mov     rsi, rcx
0x18002a5b8  mov     [rbp+PolicyHandle], 0
0x18002a5c0  xor     ecx, ecx; SystemName
0x18002a5c2  mov     [rbp+Buffer], 0
0x18002a5ca  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18002a5ce  mov     r8d, 1; DesiredAccess
0x18002a5d4  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002a5d8  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002a5dc  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002a5e0  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002a5e4  call    cs:__imp_LsaOpenPolicy
0x18002a5ea  test    eax, eax
0x18002a5ec  jz      short loc_18002A5F7
0x18002a5ee  bts     eax, 1Ch
0x18002a5f2  jmp     loc_18002A685
0x18002a5f7  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002a5fb  lea     r8, [rbp+Buffer]; Buffer
0x18002a5ff  mov     edx, 5; InformationClass
0x18002a604  call    cs:__imp_LsaQueryInformationPolicy
0x18002a60a  mov     ebx, eax
0x18002a60c  test    eax, eax
0x18002a60e  jz      short loc_18002A622
0x18002a610  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18002a614  call    cs:__imp_LsaClose
0x18002a61a  bts     ebx, 1Ch
0x18002a61e  mov     eax, ebx
0x18002a620  jmp     short loc_18002A685
0x18002a622  mov     rax, [rbp+Buffer]
0x18002a626  movzx   edi, word ptr [rax]
0x18002a629  mov     eax, 2
0x18002a62e  shr     edi, 1
0x18002a630  lea     ecx, [rdi+1]
0x18002a633  mul     rcx
0x18002a636  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a63d  cmovb   rax, rcx
0x18002a641  mov     rcx, rax; cb
0x18002a644  call    cs:__imp_CoTaskMemAlloc
0x18002a64a  mov     rbx, rax
0x18002a64d  test    rax, rax
0x18002a650  jz      short loc_18002A66F
0x18002a652  mov     rdx, [rbp+Buffer]
0x18002a656  mov     rcx, rax; void *
0x18002a659  movzx   r8d, word ptr [rdx]; Size
0x18002a65d  mov     rdx, [rdx+8]; Src
0x18002a661  call    memcpy_0
0x18002a666  xor     ecx, ecx
0x18002a668  mov     [rsi], rbx
0x18002a66b  mov     [rbx+rdi*2], cx
0x18002a66f  mov     rcx, [rbp+Buffer]; Buffer
0x18002a673  call    cs:__imp_LsaFreeMemory
0x18002a679  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18002a67d  call    cs:__imp_LsaClose
0x18002a683  xor     eax, eax
0x18002a685  mov     rbx, [rsp+50h+arg_10]
0x18002a68d  add     rsp, 50h
0x18002a691  pop     rdi
0x18002a692  pop     rsi
0x18002a693  pop     rbp
0x18002a694  retn
```
