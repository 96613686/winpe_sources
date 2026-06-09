# UlpFixupAccessTokenForProcess

- ea: `0x1401489b4`
- end: `0x140148bfe`
- name: `UlpFixupAccessTokenForProcess`
- size: `586`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140143e74`
- `0x1401444e4`
- `0x140144b84`

## callees

- `0x14012fca4`
- `0x14012fd5c`
- `0x14012fdbc`
- `0x140130448`
- `0x1401489b4`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x140148b95`
- `ntoskrnl!ZwSetSecurityObject` at `0x140148b95`
- `ntoskrnl!RtlValidSid` at `0x140148a52`
- `ntoskrnl!RtlValidSid` at `0x140148a69`
- `ntoskrnl!RtlValidSid` at `0x140148a52`
- `ntoskrnl!RtlValidSid` at `0x140148a69`
- `ntoskrnl!RtlEqualSid` at `0x140148ab5`
- `ntoskrnl!RtlEqualSid` at `0x140148ad9`
- `ntoskrnl!RtlEqualSid` at `0x140148b11`
- `ntoskrnl!RtlEqualSid` at `0x140148b35`
- `ntoskrnl!RtlEqualSid` at `0x140148b4b`
- `ntoskrnl!RtlEqualSid` at `0x140148ab5`
- `ntoskrnl!RtlEqualSid` at `0x140148ad9`
- `ntoskrnl!RtlEqualSid` at `0x140148b11`
- `ntoskrnl!RtlEqualSid` at `0x140148b35`
- `ntoskrnl!RtlEqualSid` at `0x140148b4b`
- `ntoskrnl!SeExports` at `0x140148a7d`
- `ntoskrnl!SeExports` at `0x140148ac5`
- `ntoskrnl!SeExports` at `0x140148afd`
- `ntoskrnl!SeExports` at `0x140148b21`
- `ntoskrnl!ZwClose` at `0x140148bdb`
- `ntoskrnl!ZwClose` at `0x140148bdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148bc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148bc7`

## pseudocode

```c
__int64 __fastcall UlpFixupAccessTokenForProcess(__int64 a1, PSID *a2, _QWORD *a3, _BYTE *a4)
{
  __int64 v5; // r14
  void *v9; // r14
  __int64 result; // rax
  NTSTATUS v11; // ebx
  unsigned int v12; // ebx
  PSID SeLocalSystemSid; // rdx
  __int64 v14; // rcx
  PSID v15; // [rsp+30h] [rbp-59h]
  _QWORD v16[7]; // [rsp+38h] [rbp-51h]
  _OWORD SecurityDescriptor[2]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v18; // [rsp+90h] [rbp+7h]

  *a3 = 0;
  *a4 = 0;
  v5 = *(_QWORD *)(a1 + 48);
  v18 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( v5 )
    v9 = *(void **)(v5 + 64);
  else
    v9 = *(void **)(a1 + 24);
  result = UlCaptureTokenUserByHandle(v9);
  if ( (int)result >= 0 )
  {
    if ( (*(_DWORD *)a1 & 0x20) != 0 )
    {
      v11 = UlDuplicateToken(v9);
      if ( v11 < 0 )
        return (unsigned int)v11;
      *a4 = 1;
      v9 = 0;
    }
    if ( RtlValidSid(MEMORY[0]) && RtlValidSid(*a2) )
    {
      v12 = 2;
      v16[0] = 983551;
      v16[2] = 983551;
      SeLocalSystemSid = SeExports->SeLocalSystemSid;
      v16[1] = SeExports->SeAliasAdminsSid;
      v15 = SeLocalSystemSid;
      if ( !RtlEqualSid(MEMORY[0], SeLocalSystemSid) && !RtlEqualSid(MEMORY[0], SeExports->SeAliasAdminsSid) )
      {
        v12 = 3;
        v16[3] = MEMORY[0];
        v16[4] = 983551;
      }
      if ( !RtlEqualSid(*a2, SeExports->SeLocalSystemSid)
        && !RtlEqualSid(*a2, SeExports->SeAliasAdminsSid)
        && !RtlEqualSid(*a2, MEMORY[0]) )
      {
        v14 = 2LL * v12;
        v16[v14 - 1] = *a2;
        v16[v14] = 983551;
      }
      v11 = UlCreateSecurityDescriptor(SecurityDescriptor);
      if ( v11 >= 0 )
      {
        v11 = ZwSetSecurityObject(v9, 4u, SecurityDescriptor);
        if ( v11 >= 0 )
          *a3 = v9;
        UlCleanupSecurityDescriptor(SecurityDescriptor);
      }
    }
    else
    {
      return (unsigned int)-1073741811;
    }
    return (unsigned int)v11;
  }
  return result;
}

```

## disassembly

```asm
0x1401489b4  push    rbp
0x1401489b6  push    rbx
0x1401489b7  push    rsi
0x1401489b8  push    rdi
0x1401489b9  push    r12
0x1401489bb  push    r13
0x1401489bd  push    r14
0x1401489bf  push    r15
0x1401489c1  lea     rbp, [rsp-1Fh]
0x1401489c6  sub     rsp, 0A8h
0x1401489cd  xor     esi, esi
0x1401489cf  xor     eax, eax
0x1401489d1  mov     [r8], rsi
0x1401489d4  xorps   xmm0, xmm0
0x1401489d7  mov     [r9], sil
0x1401489da  mov     r12, r9
0x1401489dd  mov     r14, [rcx+30h]
0x1401489e1  mov     r13, r8
0x1401489e4  mov     [rbp+57h+var_50], rax
0x1401489e8  mov     r15, rdx
0x1401489eb  mov     [rbp+57h+P], rsi
0x1401489ef  mov     rbx, rcx
0x1401489f2  mov     [rbp+57h+Handle], rsi
0x1401489f6  mov     edi, esi
0x1401489f8  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1401489fc  movups  [rbp+57h+var_60], xmm0
0x140148a00  test    r14, r14
0x140148a03  jz      short loc_140148A0B
0x140148a05  mov     r14, [r14+40h]
0x140148a09  jmp     short loc_140148A0F
0x140148a0b  mov     r14, [rcx+18h]
0x140148a0f  lea     r9, [rbp+57h+P]
0x140148a13  mov     rcx, r14; TokenHandle
0x140148a16  call    UlCaptureTokenUserByHandle
0x140148a1b  test    eax, eax
0x140148a1d  js      loc_140148BE9
0x140148a23  mov     eax, [rbx]
0x140148a25  mov     rsi, [rbp+57h+P]
0x140148a29  test    al, 20h
0x140148a2b  jz      short loc_140148A4F
0x140148a2d  lea     rdx, [rbp+57h+Handle]
0x140148a31  mov     rcx, r14; Handle
0x140148a34  call    UlDuplicateToken
0x140148a39  mov     rdi, [rbp+57h+Handle]
0x140148a3d  mov     ebx, eax
0x140148a3f  test    eax, eax
0x140148a41  js      loc_140148BBD
0x140148a47  mov     byte ptr [r12], 1
0x140148a4c  mov     r14, rdi
0x140148a4f  mov     rcx, [rsi]; Sid
0x140148a52  call    cs:__imp_RtlValidSid
0x140148a59  nop     dword ptr [rax+rax+00h]
0x140148a5e  test    al, al
0x140148a60  jz      loc_140148BB8
0x140148a66  mov     rcx, [r15]; Sid
0x140148a69  call    cs:__imp_RtlValidSid
0x140148a70  nop     dword ptr [rax+rax+00h]
0x140148a75  test    al, al
0x140148a77  jz      loc_140148BB8
0x140148a7d  mov     rax, cs:__imp_SeExports
0x140148a84  mov     ebx, 2
0x140148a89  mov     rcx, [rsi]; Sid1
0x140148a8c  mov     [rbp+57h+var_A8], 0F01FFh
0x140148a94  mov     [rbp+57h+var_98], 0F01FFh
0x140148a9c  mov     rax, [rax]
0x140148a9f  mov     rdx, [rax+108h]; Sid2
0x140148aa6  mov     rax, [rax+110h]
0x140148aad  mov     [rbp+57h+var_A0], rax
0x140148ab1  mov     [rbp+57h+var_B0], rdx
0x140148ab5  call    cs:__imp_RtlEqualSid
0x140148abc  nop     dword ptr [rax+rax+00h]
0x140148ac1  test    al, al
0x140148ac3  jnz     short loc_140148AFD
0x140148ac5  mov     rax, cs:__imp_SeExports
0x140148acc  mov     rcx, [rsi]; Sid1
0x140148acf  mov     rdx, [rax]
0x140148ad2  mov     rdx, [rdx+110h]; Sid2
0x140148ad9  call    cs:__imp_RtlEqualSid
0x140148ae0  nop     dword ptr [rax+rax+00h]
0x140148ae5  test    al, al
0x140148ae7  jnz     short loc_140148AFD
0x140148ae9  mov     rax, [rsi]
0x140148aec  mov     ebx, 3
0x140148af1  mov     [rbp+57h+var_90], rax
0x140148af5  mov     [rbp+57h+var_88], 0F01FFh
0x140148afd  mov     rax, cs:__imp_SeExports
0x140148b04  mov     rcx, [r15]; Sid1
0x140148b07  mov     rdx, [rax]
0x140148b0a  mov     rdx, [rdx+108h]; Sid2
0x140148b11  call    cs:__imp_RtlEqualSid
0x140148b18  nop     dword ptr [rax+rax+00h]
0x140148b1d  test    al, al
0x140148b1f  jnz     short loc_140148B73
0x140148b21  mov     rax, cs:__imp_SeExports
0x140148b28  mov     rcx, [r15]; Sid1
0x140148b2b  mov     rdx, [rax]
0x140148b2e  mov     rdx, [rdx+110h]; Sid2
0x140148b35  call    cs:__imp_RtlEqualSid
0x140148b3c  nop     dword ptr [rax+rax+00h]
0x140148b41  test    al, al
0x140148b43  jnz     short loc_140148B73
0x140148b45  mov     rdx, [rsi]; Sid2
0x140148b48  mov     rcx, [r15]; Sid1
0x140148b4b  call    cs:__imp_RtlEqualSid
0x140148b52  nop     dword ptr [rax+rax+00h]
0x140148b57  test    al, al
0x140148b59  jnz     short loc_140148B73
0x140148b5b  mov     rax, [r15]
0x140148b5e  mov     ecx, ebx
0x140148b60  add     rcx, rcx
0x140148b63  inc     ebx
0x140148b65  mov     [rbp+rcx*8+57h+var_B0], rax
0x140148b6a  mov     [rbp+rcx*8+57h+var_A8], 0F01FFh
0x140148b73  mov     r8d, ebx
0x140148b76  lea     rdx, [rbp+57h+var_B0]
0x140148b7a  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140148b7e  call    UlCreateSecurityDescriptor
0x140148b83  mov     ebx, eax
0x140148b85  test    eax, eax
0x140148b87  js      short loc_140148BBD
0x140148b89  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140148b8d  mov     edx, 4; SecurityInformation
0x140148b92  mov     rcx, r14; Handle
0x140148b95  call    cs:__imp_ZwSetSecurityObject
0x140148b9c  nop     dword ptr [rax+rax+00h]
0x140148ba1  mov     ebx, eax
0x140148ba3  test    eax, eax
0x140148ba5  js      short loc_140148BAD
0x140148ba7  mov     [r13+0], r14
0x140148bab  xor     edi, edi
0x140148bad  lea     rcx, [rbp+57h+SecurityDescriptor]
0x140148bb1  call    UlCleanupSecurityDescriptor
0x140148bb6  jmp     short loc_140148BBD
0x140148bb8  mov     ebx, 0C000000Dh
0x140148bbd  test    rsi, rsi
0x140148bc0  jz      short loc_140148BD3
0x140148bc2  xor     edx, edx; Tag
0x140148bc4  mov     rcx, rsi; P
0x140148bc7  call    cs:__imp_ExFreePoolWithTag
0x140148bce  nop     dword ptr [rax+rax+00h]
0x140148bd3  test    rdi, rdi
0x140148bd6  jz      short loc_140148BE7
0x140148bd8  mov     rcx, rdi; Handle
0x140148bdb  call    cs:__imp_ZwClose
0x140148be2  nop     dword ptr [rax+rax+00h]
0x140148be7  mov     eax, ebx
0x140148be9  add     rsp, 0A8h
0x140148bf0  pop     r15
0x140148bf2  pop     r14
0x140148bf4  pop     r13
0x140148bf6  pop     r12
0x140148bf8  pop     rdi
0x140148bf9  pop     rsi
0x140148bfa  pop     rbx
0x140148bfb  pop     rbp
0x140148bfc  retn
```
