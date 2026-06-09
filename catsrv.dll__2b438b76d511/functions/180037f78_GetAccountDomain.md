# GetAccountDomain

- ea: `0x180037f78`
- end: `0x180038071`
- name: `GetAccountDomain`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003821c`

## callees

- `0x180037f78`
- `0x18005550e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038020`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038020`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180037fc0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180037fc0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180037ff0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180038059`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180037ff0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180038059`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003804f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003804f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180037fe0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180037fe0`

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
0x180037f78  mov     [rsp-18h+arg_10], rbx
0x180037f7d  push    rbp
0x180037f7e  push    rsi
0x180037f7f  push    rdi
0x180037f80  mov     rbp, rsp
0x180037f83  sub     rsp, 50h
0x180037f87  xorps   xmm0, xmm0
0x180037f8a  mov     qword ptr [rcx], 0
0x180037f91  mov     rsi, rcx
0x180037f94  mov     [rbp+PolicyHandle], 0
0x180037f9c  xor     ecx, ecx; SystemName
0x180037f9e  mov     [rbp+Buffer], 0
0x180037fa6  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180037faa  mov     r8d, 1; DesiredAccess
0x180037fb0  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180037fb4  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180037fb8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180037fbc  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180037fc0  call    cs:__imp_LsaOpenPolicy
0x180037fc6  test    eax, eax
0x180037fc8  jz      short loc_180037FD3
0x180037fca  bts     eax, 1Ch
0x180037fce  jmp     loc_180038061
0x180037fd3  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180037fd7  lea     r8, [rbp+Buffer]; Buffer
0x180037fdb  mov     edx, 5; InformationClass
0x180037fe0  call    cs:__imp_LsaQueryInformationPolicy
0x180037fe6  mov     ebx, eax
0x180037fe8  test    eax, eax
0x180037fea  jz      short loc_180037FFE
0x180037fec  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180037ff0  call    cs:__imp_LsaClose
0x180037ff6  bts     ebx, 1Ch
0x180037ffa  mov     eax, ebx
0x180037ffc  jmp     short loc_180038061
0x180037ffe  mov     rax, [rbp+Buffer]
0x180038002  movzx   edi, word ptr [rax]
0x180038005  mov     eax, 2
0x18003800a  shr     edi, 1
0x18003800c  lea     ecx, [rdi+1]
0x18003800f  mul     rcx
0x180038012  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180038019  cmovb   rax, rcx
0x18003801d  mov     rcx, rax; cb
0x180038020  call    cs:__imp_CoTaskMemAlloc
0x180038026  mov     rbx, rax
0x180038029  test    rax, rax
0x18003802c  jz      short loc_18003804B
0x18003802e  mov     rdx, [rbp+Buffer]
0x180038032  mov     rcx, rax; void *
0x180038035  movzx   r8d, word ptr [rdx]; Size
0x180038039  mov     rdx, [rdx+8]; Src
0x18003803d  call    memcpy_0
0x180038042  xor     ecx, ecx
0x180038044  mov     [rsi], rbx
0x180038047  mov     [rbx+rdi*2], cx
0x18003804b  mov     rcx, [rbp+Buffer]; Buffer
0x18003804f  call    cs:__imp_LsaFreeMemory
0x180038055  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180038059  call    cs:__imp_LsaClose
0x18003805f  xor     eax, eax
0x180038061  mov     rbx, [rsp+50h+arg_10]
0x180038069  add     rsp, 50h
0x18003806d  pop     rdi
0x18003806e  pop     rsi
0x18003806f  pop     rbp
0x180038070  retn
```
