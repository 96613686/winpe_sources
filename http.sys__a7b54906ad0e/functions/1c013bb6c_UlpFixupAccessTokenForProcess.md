# UlpFixupAccessTokenForProcess

- ea: `0x1c013bb6c`
- end: `0x1c013bdd7`
- name: `UlpFixupAccessTokenForProcess`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0139a20`

## callees

- `0x1c001a4b0`
- `0x1c00d5aa0`
- `0x1c00d5afc`
- `0x1c012d2e0`
- `0x1c012d4d0`
- `0x1c013bb6c`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1c013bc43`
- `ntoskrnl!SeExports` at `0x1c013bc91`
- `ntoskrnl!SeExports` at `0x1c013bcc9`
- `ntoskrnl!SeExports` at `0x1c013bced`
- `ntoskrnl!RtlEqualSid` at `0x1c013bc81`
- `ntoskrnl!RtlEqualSid` at `0x1c013bca5`
- `ntoskrnl!RtlEqualSid` at `0x1c013bcdd`
- `ntoskrnl!RtlEqualSid` at `0x1c013bd01`
- `ntoskrnl!RtlEqualSid` at `0x1c013bd17`
- `ntoskrnl!RtlEqualSid` at `0x1c013bc81`
- `ntoskrnl!RtlEqualSid` at `0x1c013bca5`
- `ntoskrnl!RtlEqualSid` at `0x1c013bcdd`
- `ntoskrnl!RtlEqualSid` at `0x1c013bd01`
- `ntoskrnl!RtlEqualSid` at `0x1c013bd17`
- `ntoskrnl!ZwSetSecurityObject` at `0x1c013bd62`
- `ntoskrnl!ZwSetSecurityObject` at `0x1c013bd62`
- `ntoskrnl!RtlValidSid` at `0x1c013bc18`
- `ntoskrnl!RtlValidSid` at `0x1c013bc2f`
- `ntoskrnl!RtlValidSid` at `0x1c013bc18`
- `ntoskrnl!RtlValidSid` at `0x1c013bc2f`
- `ntoskrnl!ZwClose` at `0x1c013bda8`
- `ntoskrnl!ZwClose` at `0x1c013bda8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c013bd94`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c013bd94`

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
  PSID v14; // rax
  __int64 v15; // rcx
  _OWORD SecurityDescriptor[2]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v17; // [rsp+50h] [rbp-49h]
  PSID v18; // [rsp+60h] [rbp-39h]
  int v19; // [rsp+68h] [rbp-31h]
  int v20; // [rsp+6Ch] [rbp-2Dh]
  PSID SeAliasAdminsSid; // [rsp+70h] [rbp-29h]
  int v22; // [rsp+78h] [rbp-21h]
  int v23; // [rsp+7Ch] [rbp-1Dh]
  __int64 v24; // [rsp+80h] [rbp-19h]
  int v25; // [rsp+88h] [rbp-11h]
  int v26; // [rsp+8Ch] [rbp-Dh]

  *a3 = 0;
  *a4 = 0;
  v5 = *(_QWORD *)(a1 + 48);
  v17 = 0;
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
      v20 = 0;
      v23 = 0;
      v19 = 983551;
      v22 = 983551;
      SeLocalSystemSid = SeExports->SeLocalSystemSid;
      SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
      v18 = SeLocalSystemSid;
      if ( !RtlEqualSid(MEMORY[0], SeLocalSystemSid) && !RtlEqualSid(MEMORY[0], SeExports->SeAliasAdminsSid) )
      {
        v12 = 3;
        v26 = 0;
        v24 = MEMORY[0];
        v25 = 983551;
      }
      if ( !RtlEqualSid(*a2, SeExports->SeLocalSystemSid)
        && !RtlEqualSid(*a2, SeExports->SeAliasAdminsSid)
        && !RtlEqualSid(*a2, MEMORY[0]) )
      {
        v14 = *a2;
        v15 = 2LL * v12;
        *(&v20 + 2 * v15) = 0;
        *(&v18 + v15) = v14;
        *(&v19 + 2 * v15) = 983551;
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
0x1c013bb6c  push    rbp
0x1c013bb6e  push    rbx
0x1c013bb6f  push    rsi
0x1c013bb70  push    rdi
0x1c013bb71  push    r12
0x1c013bb73  push    r13
0x1c013bb75  push    r14
0x1c013bb77  push    r15
0x1c013bb79  lea     rbp, [rsp-1Fh]
0x1c013bb7e  sub     rsp, 0B8h
0x1c013bb85  mov     rax, cs:__security_cookie
0x1c013bb8c  xor     rax, rsp
0x1c013bb8f  mov     [rbp+57h+var_50], rax
0x1c013bb93  xor     esi, esi
0x1c013bb95  xor     eax, eax
0x1c013bb97  mov     [r8], rsi
0x1c013bb9a  xorps   xmm0, xmm0
0x1c013bb9d  mov     [r9], sil
0x1c013bba0  mov     r12, r9
0x1c013bba3  mov     r14, [rcx+30h]
0x1c013bba7  mov     r13, r8
0x1c013bbaa  mov     [rbp+57h+var_A0], rax
0x1c013bbae  mov     r15, rdx
0x1c013bbb1  mov     [rbp+57h+P], rsi
0x1c013bbb5  mov     rbx, rcx
0x1c013bbb8  mov     [rbp+57h+Handle], rsi
0x1c013bbbc  mov     edi, esi
0x1c013bbbe  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1c013bbc2  movups  [rbp+57h+var_B0], xmm0
0x1c013bbc6  test    r14, r14
0x1c013bbc9  jz      short loc_1C013BBD1
0x1c013bbcb  mov     r14, [r14+40h]
0x1c013bbcf  jmp     short loc_1C013BBD5
0x1c013bbd1  mov     r14, [rcx+18h]
0x1c013bbd5  lea     r9, [rbp+57h+P]
0x1c013bbd9  mov     rcx, r14; TokenHandle
0x1c013bbdc  call    UlCaptureTokenUserByHandle
0x1c013bbe1  test    eax, eax
0x1c013bbe3  js      loc_1C013BDB6
0x1c013bbe9  mov     eax, [rbx]
0x1c013bbeb  mov     rsi, [rbp+57h+P]
0x1c013bbef  test    al, 20h
0x1c013bbf1  jz      short loc_1C013BC15
0x1c013bbf3  lea     rdx, [rbp+57h+Handle]
0x1c013bbf7  mov     rcx, r14; Handle
0x1c013bbfa  call    UlDuplicateToken
0x1c013bbff  mov     rdi, [rbp+57h+Handle]
0x1c013bc03  mov     ebx, eax
0x1c013bc05  test    eax, eax
0x1c013bc07  js      loc_1C013BD8A
0x1c013bc0d  mov     byte ptr [r12], 1
0x1c013bc12  mov     r14, rdi
0x1c013bc15  mov     rcx, [rsi]; Sid
0x1c013bc18  call    cs:__imp_RtlValidSid
0x1c013bc1f  nop     dword ptr [rax+rax+00h]
0x1c013bc24  test    al, al
0x1c013bc26  jz      loc_1C013BD85
0x1c013bc2c  mov     rcx, [r15]; Sid
0x1c013bc2f  call    cs:__imp_RtlValidSid
0x1c013bc36  nop     dword ptr [rax+rax+00h]
0x1c013bc3b  test    al, al
0x1c013bc3d  jz      loc_1C013BD85
0x1c013bc43  mov     rax, cs:__imp_SeExports
0x1c013bc4a  mov     r12d, 0F01FFh
0x1c013bc50  mov     rcx, [rsi]; Sid1
0x1c013bc53  mov     ebx, 2
0x1c013bc58  and     [rbp+57h+var_84], 0
0x1c013bc5c  and     [rbp+57h+var_74], 0
0x1c013bc60  mov     rax, [rax]
0x1c013bc63  mov     [rbp+57h+var_88], r12d
0x1c013bc67  mov     [rbp+57h+var_78], r12d
0x1c013bc6b  mov     rdx, [rax+108h]; Sid2
0x1c013bc72  mov     rax, [rax+110h]
0x1c013bc79  mov     [rbp+57h+var_80], rax
0x1c013bc7d  mov     [rbp+57h+var_90], rdx
0x1c013bc81  call    cs:__imp_RtlEqualSid
0x1c013bc88  nop     dword ptr [rax+rax+00h]
0x1c013bc8d  test    al, al
0x1c013bc8f  jnz     short loc_1C013BCC9
0x1c013bc91  mov     rax, cs:__imp_SeExports
0x1c013bc98  mov     rcx, [rsi]; Sid1
0x1c013bc9b  mov     rdx, [rax]
0x1c013bc9e  mov     rdx, [rdx+110h]; Sid2
0x1c013bca5  call    cs:__imp_RtlEqualSid
0x1c013bcac  nop     dword ptr [rax+rax+00h]
0x1c013bcb1  test    al, al
0x1c013bcb3  jnz     short loc_1C013BCC9
0x1c013bcb5  mov     rax, [rsi]
0x1c013bcb8  mov     ebx, 3
0x1c013bcbd  and     [rbp+57h+var_64], 0
0x1c013bcc1  mov     [rbp+57h+var_70], rax
0x1c013bcc5  mov     [rbp+57h+var_68], r12d
0x1c013bcc9  mov     rax, cs:__imp_SeExports
0x1c013bcd0  mov     rcx, [r15]; Sid1
0x1c013bcd3  mov     rdx, [rax]
0x1c013bcd6  mov     rdx, [rdx+108h]; Sid2
0x1c013bcdd  call    cs:__imp_RtlEqualSid
0x1c013bce4  nop     dword ptr [rax+rax+00h]
0x1c013bce9  test    al, al
0x1c013bceb  jnz     short loc_1C013BD40
0x1c013bced  mov     rax, cs:__imp_SeExports
0x1c013bcf4  mov     rcx, [r15]; Sid1
0x1c013bcf7  mov     rdx, [rax]
0x1c013bcfa  mov     rdx, [rdx+110h]; Sid2
0x1c013bd01  call    cs:__imp_RtlEqualSid
0x1c013bd08  nop     dword ptr [rax+rax+00h]
0x1c013bd0d  test    al, al
0x1c013bd0f  jnz     short loc_1C013BD40
0x1c013bd11  mov     rdx, [rsi]; Sid2
0x1c013bd14  mov     rcx, [r15]; Sid1
0x1c013bd17  call    cs:__imp_RtlEqualSid
0x1c013bd1e  nop     dword ptr [rax+rax+00h]
0x1c013bd23  test    al, al
0x1c013bd25  jnz     short loc_1C013BD40
0x1c013bd27  mov     rax, [r15]
0x1c013bd2a  mov     ecx, ebx
0x1c013bd2c  add     rcx, rcx
0x1c013bd2f  and     [rbp+rcx*8+57h+var_84], 0
0x1c013bd34  inc     ebx
0x1c013bd36  mov     [rbp+rcx*8+57h+var_90], rax
0x1c013bd3b  mov     [rbp+rcx*8+57h+var_88], r12d
0x1c013bd40  mov     r8d, ebx
0x1c013bd43  lea     rdx, [rbp+57h+var_90]
0x1c013bd47  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1c013bd4b  call    UlCreateSecurityDescriptor
0x1c013bd50  mov     ebx, eax
0x1c013bd52  test    eax, eax
0x1c013bd54  js      short loc_1C013BD8A
0x1c013bd56  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1c013bd5a  mov     edx, 4; SecurityInformation
0x1c013bd5f  mov     rcx, r14; Handle
0x1c013bd62  call    cs:__imp_ZwSetSecurityObject
0x1c013bd69  nop     dword ptr [rax+rax+00h]
0x1c013bd6e  mov     ebx, eax
0x1c013bd70  test    eax, eax
0x1c013bd72  js      short loc_1C013BD7A
0x1c013bd74  mov     [r13+0], r14
0x1c013bd78  xor     edi, edi
0x1c013bd7a  lea     rcx, [rbp+57h+SecurityDescriptor]
0x1c013bd7e  call    UlCleanupSecurityDescriptor
0x1c013bd83  jmp     short loc_1C013BD8A
0x1c013bd85  mov     ebx, 0C000000Dh
0x1c013bd8a  test    rsi, rsi
0x1c013bd8d  jz      short loc_1C013BDA0
0x1c013bd8f  xor     edx, edx; Tag
0x1c013bd91  mov     rcx, rsi; P
0x1c013bd94  call    cs:__imp_ExFreePoolWithTag
0x1c013bd9b  nop     dword ptr [rax+rax+00h]
0x1c013bda0  test    rdi, rdi
0x1c013bda3  jz      short loc_1C013BDB4
0x1c013bda5  mov     rcx, rdi; Handle
0x1c013bda8  call    cs:__imp_ZwClose
0x1c013bdaf  nop     dword ptr [rax+rax+00h]
0x1c013bdb4  mov     eax, ebx
0x1c013bdb6  mov     rcx, [rbp+57h+var_50]
0x1c013bdba  xor     rcx, rsp; StackCookie
0x1c013bdbd  call    __security_check_cookie
0x1c013bdc2  add     rsp, 0B8h
0x1c013bdc9  pop     r15
0x1c013bdcb  pop     r14
0x1c013bdcd  pop     r13
0x1c013bdcf  pop     r12
0x1c013bdd1  pop     rdi
0x1c013bdd2  pop     rsi
0x1c013bdd3  pop     rbx
0x1c013bdd4  pop     rbp
0x1c013bdd5  retn
```
