# UlpFixupAccessTokenForProcess

- ea: `0x140148aa4`
- end: `0x140148cee`
- name: `UlpFixupAccessTokenForProcess`
- size: `586`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140143f64`
- `0x1401445d4`
- `0x140144c74`

## callees

- `0x14012fd94`
- `0x14012fe4c`
- `0x14012feac`
- `0x140130538`
- `0x140148aa4`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x140148c85`
- `ntoskrnl!ZwSetSecurityObject` at `0x140148c85`
- `ntoskrnl!RtlValidSid` at `0x140148b42`
- `ntoskrnl!RtlValidSid` at `0x140148b59`
- `ntoskrnl!RtlValidSid` at `0x140148b42`
- `ntoskrnl!RtlValidSid` at `0x140148b59`
- `ntoskrnl!RtlEqualSid` at `0x140148ba5`
- `ntoskrnl!RtlEqualSid` at `0x140148bc9`
- `ntoskrnl!RtlEqualSid` at `0x140148c01`
- `ntoskrnl!RtlEqualSid` at `0x140148c25`
- `ntoskrnl!RtlEqualSid` at `0x140148c3b`
- `ntoskrnl!RtlEqualSid` at `0x140148ba5`
- `ntoskrnl!RtlEqualSid` at `0x140148bc9`
- `ntoskrnl!RtlEqualSid` at `0x140148c01`
- `ntoskrnl!RtlEqualSid` at `0x140148c25`
- `ntoskrnl!RtlEqualSid` at `0x140148c3b`
- `ntoskrnl!SeExports` at `0x140148b6d`
- `ntoskrnl!SeExports` at `0x140148bb5`
- `ntoskrnl!SeExports` at `0x140148bed`
- `ntoskrnl!SeExports` at `0x140148c11`
- `ntoskrnl!ZwClose` at `0x140148ccb`
- `ntoskrnl!ZwClose` at `0x140148ccb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148cb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148cb7`

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
0x140148aa4  push    rbp
0x140148aa6  push    rbx
0x140148aa7  push    rsi
0x140148aa8  push    rdi
0x140148aa9  push    r12
0x140148aab  push    r13
0x140148aad  push    r14
0x140148aaf  push    r15
0x140148ab1  lea     rbp, [rsp-1Fh]
0x140148ab6  sub     rsp, 0A8h
0x140148abd  xor     esi, esi
0x140148abf  xor     eax, eax
0x140148ac1  mov     [r8], rsi
0x140148ac4  xorps   xmm0, xmm0
0x140148ac7  mov     [r9], sil
0x140148aca  mov     r12, r9
0x140148acd  mov     r14, [rcx+30h]
0x140148ad1  mov     r13, r8
0x140148ad4  mov     [rbp+57h+var_50], rax
0x140148ad8  mov     r15, rdx
0x140148adb  mov     [rbp+57h+P], rsi
0x140148adf  mov     rbx, rcx
0x140148ae2  mov     [rbp+57h+Handle], rsi
0x140148ae6  mov     edi, esi
0x140148ae8  movups  [rbp+57h+SecurityDescriptor], xmm0
0x140148aec  movups  [rbp+57h+var_60], xmm0
0x140148af0  test    r14, r14
0x140148af3  jz      short loc_140148AFB
0x140148af5  mov     r14, [r14+40h]
0x140148af9  jmp     short loc_140148AFF
0x140148afb  mov     r14, [rcx+18h]
0x140148aff  lea     r9, [rbp+57h+P]
0x140148b03  mov     rcx, r14; TokenHandle
0x140148b06  call    UlCaptureTokenUserByHandle
0x140148b0b  test    eax, eax
0x140148b0d  js      loc_140148CD9
0x140148b13  mov     eax, [rbx]
0x140148b15  mov     rsi, [rbp+57h+P]
0x140148b19  test    al, 20h
0x140148b1b  jz      short loc_140148B3F
0x140148b1d  lea     rdx, [rbp+57h+Handle]
0x140148b21  mov     rcx, r14; Handle
0x140148b24  call    UlDuplicateToken
0x140148b29  mov     rdi, [rbp+57h+Handle]
0x140148b2d  mov     ebx, eax
0x140148b2f  test    eax, eax
0x140148b31  js      loc_140148CAD
0x140148b37  mov     byte ptr [r12], 1
0x140148b3c  mov     r14, rdi
0x140148b3f  mov     rcx, [rsi]; Sid
0x140148b42  call    cs:__imp_RtlValidSid
0x140148b49  nop     dword ptr [rax+rax+00h]
0x140148b4e  test    al, al
0x140148b50  jz      loc_140148CA8
0x140148b56  mov     rcx, [r15]; Sid
0x140148b59  call    cs:__imp_RtlValidSid
0x140148b60  nop     dword ptr [rax+rax+00h]
0x140148b65  test    al, al
0x140148b67  jz      loc_140148CA8
0x140148b6d  mov     rax, cs:__imp_SeExports
0x140148b74  mov     ebx, 2
0x140148b79  mov     rcx, [rsi]; Sid1
0x140148b7c  mov     [rbp+57h+var_A8], 0F01FFh
0x140148b84  mov     [rbp+57h+var_98], 0F01FFh
0x140148b8c  mov     rax, [rax]
0x140148b8f  mov     rdx, [rax+108h]; Sid2
0x140148b96  mov     rax, [rax+110h]
0x140148b9d  mov     [rbp+57h+var_A0], rax
0x140148ba1  mov     [rbp+57h+var_B0], rdx
0x140148ba5  call    cs:__imp_RtlEqualSid
0x140148bac  nop     dword ptr [rax+rax+00h]
0x140148bb1  test    al, al
0x140148bb3  jnz     short loc_140148BED
0x140148bb5  mov     rax, cs:__imp_SeExports
0x140148bbc  mov     rcx, [rsi]; Sid1
0x140148bbf  mov     rdx, [rax]
0x140148bc2  mov     rdx, [rdx+110h]; Sid2
0x140148bc9  call    cs:__imp_RtlEqualSid
0x140148bd0  nop     dword ptr [rax+rax+00h]
0x140148bd5  test    al, al
0x140148bd7  jnz     short loc_140148BED
0x140148bd9  mov     rax, [rsi]
0x140148bdc  mov     ebx, 3
0x140148be1  mov     [rbp+57h+var_90], rax
0x140148be5  mov     [rbp+57h+var_88], 0F01FFh
0x140148bed  mov     rax, cs:__imp_SeExports
0x140148bf4  mov     rcx, [r15]; Sid1
0x140148bf7  mov     rdx, [rax]
0x140148bfa  mov     rdx, [rdx+108h]; Sid2
0x140148c01  call    cs:__imp_RtlEqualSid
0x140148c08  nop     dword ptr [rax+rax+00h]
0x140148c0d  test    al, al
0x140148c0f  jnz     short loc_140148C63
0x140148c11  mov     rax, cs:__imp_SeExports
0x140148c18  mov     rcx, [r15]; Sid1
0x140148c1b  mov     rdx, [rax]
0x140148c1e  mov     rdx, [rdx+110h]; Sid2
0x140148c25  call    cs:__imp_RtlEqualSid
0x140148c2c  nop     dword ptr [rax+rax+00h]
0x140148c31  test    al, al
0x140148c33  jnz     short loc_140148C63
0x140148c35  mov     rdx, [rsi]; Sid2
0x140148c38  mov     rcx, [r15]; Sid1
0x140148c3b  call    cs:__imp_RtlEqualSid
0x140148c42  nop     dword ptr [rax+rax+00h]
0x140148c47  test    al, al
0x140148c49  jnz     short loc_140148C63
0x140148c4b  mov     rax, [r15]
0x140148c4e  mov     ecx, ebx
0x140148c50  add     rcx, rcx
0x140148c53  inc     ebx
0x140148c55  mov     [rbp+rcx*8+57h+var_B0], rax
0x140148c5a  mov     [rbp+rcx*8+57h+var_A8], 0F01FFh
0x140148c63  mov     r8d, ebx
0x140148c66  lea     rdx, [rbp+57h+var_B0]
0x140148c6a  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140148c6e  call    UlCreateSecurityDescriptor
0x140148c73  mov     ebx, eax
0x140148c75  test    eax, eax
0x140148c77  js      short loc_140148CAD
0x140148c79  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140148c7d  mov     edx, 4; SecurityInformation
0x140148c82  mov     rcx, r14; Handle
0x140148c85  call    cs:__imp_ZwSetSecurityObject
0x140148c8c  nop     dword ptr [rax+rax+00h]
0x140148c91  mov     ebx, eax
0x140148c93  test    eax, eax
0x140148c95  js      short loc_140148C9D
0x140148c97  mov     [r13+0], r14
0x140148c9b  xor     edi, edi
0x140148c9d  lea     rcx, [rbp+57h+SecurityDescriptor]
0x140148ca1  call    UlCleanupSecurityDescriptor
0x140148ca6  jmp     short loc_140148CAD
0x140148ca8  mov     ebx, 0C000000Dh
0x140148cad  test    rsi, rsi
0x140148cb0  jz      short loc_140148CC3
0x140148cb2  xor     edx, edx; Tag
0x140148cb4  mov     rcx, rsi; P
0x140148cb7  call    cs:__imp_ExFreePoolWithTag
0x140148cbe  nop     dword ptr [rax+rax+00h]
0x140148cc3  test    rdi, rdi
0x140148cc6  jz      short loc_140148CD7
0x140148cc8  mov     rcx, rdi; Handle
0x140148ccb  call    cs:__imp_ZwClose
0x140148cd2  nop     dword ptr [rax+rax+00h]
0x140148cd7  mov     eax, ebx
0x140148cd9  add     rsp, 0A8h
0x140148ce0  pop     r15
0x140148ce2  pop     r14
0x140148ce4  pop     r13
0x140148ce6  pop     r12
0x140148ce8  pop     rdi
0x140148ce9  pop     rsi
0x140148cea  pop     rbx
0x140148ceb  pop     rbp
0x140148cec  retn
```
