# NetpGetDomainNameExExEx

- ea: `0x18008a93c`
- end: `0x18008ac15`
- name: `NetpGetDomainNameExExEx`
- size: `729`
- prototype: `__int64 __fastcall(LPVOID *Buffer, LPVOID *, LPVOID *, LPVOID *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016ad0`
- `0x18003b4b4`
- `0x18003b6c4`

## callees

- `0x18008a93c`
- `0x180090204`

## import_xrefs

- `ntdll!RtlCompareMemoryUlong` at `0x18008abc1`
- `ntdll!RtlCompareMemoryUlong` at `0x18008abc1`
- `netutils!NetApiBufferFree` at `0x18008a9e8`
- `netutils!NetApiBufferFree` at `0x18008aa04`
- `netutils!NetApiBufferFree` at `0x18008aa20`
- `netutils!NetApiBufferFree` at `0x18008aa3c`
- `netutils!NetApiBufferFree` at `0x18008a9e8`
- `netutils!NetApiBufferFree` at `0x18008aa04`
- `netutils!NetApiBufferFree` at `0x18008aa20`
- `netutils!NetApiBufferFree` at `0x18008aa3c`
- `netutils!NetApiBufferAllocate` at `0x18008aabf`
- `netutils!NetApiBufferAllocate` at `0x18008ab15`
- `netutils!NetApiBufferAllocate` at `0x18008ab6d`
- `netutils!NetApiBufferAllocate` at `0x18008abd7`
- `netutils!NetApiBufferAllocate` at `0x18008aabf`
- `netutils!NetApiBufferAllocate` at `0x18008ab15`
- `netutils!NetApiBufferAllocate` at `0x18008ab6d`
- `netutils!NetApiBufferAllocate` at `0x18008abd7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18008a9c7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18008a9c7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18008aa9e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18008aa9e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18008aa54`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18008aa54`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18008aa69`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18008aa69`

## pseudocode

```c
__int64 __fastcall NetpGetDomainNameExExEx(LPVOID *Buffer, LPVOID *a2, LPVOID *a3, LPVOID *a4, bool *a5)
{
  DWORD v10; // ebx
  PVOID PolicyHandle; // [rsp+20h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+28h] [rbp-38h] BYREF
  PVOID Buffera; // [rsp+90h] [rbp+30h] BYREF

  PolicyHandle = 0;
  Buffera = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( !Buffer )
    return 87;
  *Buffer = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle) < 0
    || LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffera) < 0 )
  {
    v10 = 2146;
    goto LABEL_11;
  }
  v10 = NetApiBufferAllocate(*(unsigned __int16 *)Buffera + 2, Buffer);
  if ( v10 )
    goto LABEL_11;
  memcpy_0(*Buffer, *((const void **)Buffera + 1), *(unsigned __int16 *)Buffera);
  *((_WORD *)*Buffer + ((unsigned __int64)*(unsigned __int16 *)Buffera >> 1)) = 0;
  if ( a2 && *((_WORD *)Buffera + 8) )
  {
    v10 = NetApiBufferAllocate(*((unsigned __int16 *)Buffera + 8) + 2, a2);
    if ( v10 )
      goto LABEL_11;
    memcpy_0(*a2, *((const void **)Buffera + 3), *((unsigned __int16 *)Buffera + 8));
    *((_WORD *)*a2 + ((unsigned __int64)*((unsigned __int16 *)Buffera + 8) >> 1)) = 0;
  }
  if ( a3 && *((_WORD *)Buffera + 16) )
  {
    v10 = NetApiBufferAllocate(*((unsigned __int16 *)Buffera + 16) + 2, a3);
    if ( v10 )
      goto LABEL_11;
    memcpy_0(*a3, *((const void **)Buffera + 5), *((unsigned __int16 *)Buffera + 16));
    *((_WORD *)*a3 + ((unsigned __int64)*((unsigned __int16 *)Buffera + 16) >> 1)) = 0;
  }
  if ( !a4 || RtlCompareMemoryUlong((char *)Buffera + 48, 0x10u, 0) == 16 )
    goto LABEL_41;
  v10 = NetApiBufferAllocate(0x10u, a4);
  if ( v10 )
  {
LABEL_11:
    if ( *Buffer )
    {
      NetApiBufferFree(*Buffer);
      *Buffer = 0;
    }
    if ( a2 && *a2 )
    {
      NetApiBufferFree(*a2);
      *a2 = 0;
    }
    if ( a3 && *a3 )
    {
      NetApiBufferFree(*a3);
      *a3 = 0;
    }
    if ( a4 && *a4 )
    {
      NetApiBufferFree(*a4);
      *a4 = 0;
    }
    goto LABEL_22;
  }
  *(_OWORD *)*a4 = *((_OWORD *)Buffera + 3);
LABEL_41:
  v10 = 0;
  *a5 = *((_QWORD *)Buffera + 8) == 0;
LABEL_22:
  if ( Buffera )
    LsaFreeMemory(Buffera);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v10;
}

```

## disassembly

```asm
0x18008a93c  mov     [rsp-28h+arg_8], rbx
0x18008a941  mov     [rsp-28h+arg_10], rsi
0x18008a946  push    rbp
0x18008a947  push    rdi
0x18008a948  push    r12
0x18008a94a  push    r14
0x18008a94c  push    r15
0x18008a94e  mov     rbp, rsp
0x18008a951  sub     rsp, 60h
0x18008a955  xor     r12d, r12d
0x18008a958  mov     rdi, r9
0x18008a95b  mov     [rbp+PolicyHandle], r12
0x18008a95f  mov     rsi, r8
0x18008a962  mov     [rbp+Buffer], r12
0x18008a966  mov     r14, rdx
0x18008a969  mov     dword ptr [rbp+ObjectAttributes+4], r12d
0x18008a96d  mov     r15, rcx
0x18008a970  mov     dword ptr [rbp+ObjectAttributes+1Ch], r12d
0x18008a974  test    rcx, rcx
0x18008a977  jnz     short loc_18008A981
0x18008a979  lea     eax, [rcx+57h]
0x18008a97c  jmp     loc_18008AA77
0x18008a981  mov     [rcx], r12
0x18008a984  test    r14, r14
0x18008a987  jz      short loc_18008A98C
0x18008a989  mov     [rdx], r12
0x18008a98c  test    rsi, rsi
0x18008a98f  jz      short loc_18008A994
0x18008a991  mov     [r8], r12
0x18008a994  test    rdi, rdi
0x18008a997  jz      short loc_18008A99C
0x18008a999  mov     [r9], r12
0x18008a99c  xorps   xmm0, xmm0
0x18008a99f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18008a9a6  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18008a9aa  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x18008a9ae  mov     r8d, 1; DesiredAccess
0x18008a9b4  mov     [rbp+ObjectAttributes.Attributes], r12d
0x18008a9b8  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18008a9bc  mov     [rbp+ObjectAttributes.ObjectName], r12
0x18008a9c0  xor     ecx, ecx; SystemName
0x18008a9c2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a9c7  call    cs:__imp_LsaOpenPolicy
0x18008a9ce  nop     dword ptr [rax+rax+00h]
0x18008a9d3  test    eax, eax
0x18008a9d5  jns     loc_18008AA91
0x18008a9db  mov     ebx, 862h
0x18008a9e0  mov     rcx, [r15]; Buffer
0x18008a9e3  test    rcx, rcx
0x18008a9e6  jz      short loc_18008A9F7
0x18008a9e8  call    cs:__imp_NetApiBufferFree
0x18008a9ef  nop     dword ptr [rax+rax+00h]
0x18008a9f4  mov     [r15], r12
0x18008a9f7  test    r14, r14
0x18008a9fa  jz      short loc_18008AA13
0x18008a9fc  mov     rcx, [r14]; Buffer
0x18008a9ff  test    rcx, rcx
0x18008aa02  jz      short loc_18008AA13
0x18008aa04  call    cs:__imp_NetApiBufferFree
0x18008aa0b  nop     dword ptr [rax+rax+00h]
0x18008aa10  mov     [r14], r12
0x18008aa13  test    rsi, rsi
0x18008aa16  jz      short loc_18008AA2F
0x18008aa18  mov     rcx, [rsi]; Buffer
0x18008aa1b  test    rcx, rcx
0x18008aa1e  jz      short loc_18008AA2F
0x18008aa20  call    cs:__imp_NetApiBufferFree
0x18008aa27  nop     dword ptr [rax+rax+00h]
0x18008aa2c  mov     [rsi], r12
0x18008aa2f  test    rdi, rdi
0x18008aa32  jz      short loc_18008AA4B
0x18008aa34  mov     rcx, [rdi]; Buffer
0x18008aa37  test    rcx, rcx
0x18008aa3a  jz      short loc_18008AA4B
0x18008aa3c  call    cs:__imp_NetApiBufferFree
0x18008aa43  nop     dword ptr [rax+rax+00h]
0x18008aa48  mov     [rdi], r12
0x18008aa4b  mov     rcx, [rbp+Buffer]; Buffer
0x18008aa4f  test    rcx, rcx
0x18008aa52  jz      short loc_18008AA60
0x18008aa54  call    cs:__imp_LsaFreeMemory
0x18008aa5b  nop     dword ptr [rax+rax+00h]
0x18008aa60  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18008aa64  test    rcx, rcx
0x18008aa67  jz      short loc_18008AA75
0x18008aa69  call    cs:__imp_LsaClose
0x18008aa70  nop     dword ptr [rax+rax+00h]
0x18008aa75  mov     eax, ebx
0x18008aa77  lea     r11, [rsp+60h+var_s0]
0x18008aa7c  mov     rbx, [r11+38h]
0x18008aa80  mov     rsi, [r11+40h]
0x18008aa84  mov     rsp, r11
0x18008aa87  pop     r15
0x18008aa89  pop     r14
0x18008aa8b  pop     r12
0x18008aa8d  pop     rdi
0x18008aa8e  pop     rbp
0x18008aa8f  retn
0x18008aa91  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18008aa95  lea     r8, [rbp+Buffer]; Buffer
0x18008aa99  mov     edx, 0Ch; InformationClass
0x18008aa9e  call    cs:__imp_LsaQueryInformationPolicy
0x18008aaa5  nop     dword ptr [rax+rax+00h]
0x18008aaaa  test    eax, eax
0x18008aaac  js      loc_18008A9DB
0x18008aab2  mov     rax, [rbp+Buffer]
0x18008aab6  mov     rdx, r15; Buffer
0x18008aab9  movzx   ecx, word ptr [rax]
0x18008aabc  add     ecx, 2; ByteCount
0x18008aabf  call    cs:__imp_NetApiBufferAllocate
0x18008aac6  nop     dword ptr [rax+rax+00h]
0x18008aacb  mov     ebx, eax
0x18008aacd  test    eax, eax
0x18008aacf  jnz     loc_18008A9E0
0x18008aad5  mov     rdx, [rbp+Buffer]
0x18008aad9  mov     rcx, [r15]; void *
0x18008aadc  movzx   r8d, word ptr [rdx]; Size
0x18008aae0  mov     rdx, [rdx+8]; Src
0x18008aae4  call    memcpy_0
0x18008aae9  mov     rax, [rbp+Buffer]
0x18008aaed  mov     rcx, [r15]
0x18008aaf0  movzx   edx, word ptr [rax]
0x18008aaf3  shr     rdx, 1
0x18008aaf6  mov     [rcx+rdx*2], r12w
0x18008aafb  test    r14, r14
0x18008aafe  jz      short loc_18008AB53
0x18008ab00  mov     rax, [rbp+Buffer]
0x18008ab04  cmp     [rax+10h], r12w
0x18008ab09  jz      short loc_18008AB53
0x18008ab0b  movzx   ecx, word ptr [rax+10h]
0x18008ab0f  mov     rdx, r14; Buffer
0x18008ab12  add     ecx, 2; ByteCount
0x18008ab15  call    cs:__imp_NetApiBufferAllocate
0x18008ab1c  nop     dword ptr [rax+rax+00h]
0x18008ab21  mov     ebx, eax
0x18008ab23  test    eax, eax
0x18008ab25  jnz     loc_18008A9E0
0x18008ab2b  mov     rdx, [rbp+Buffer]
0x18008ab2f  mov     rcx, [r14]; void *
0x18008ab32  movzx   r8d, word ptr [rdx+10h]; Size
0x18008ab37  mov     rdx, [rdx+18h]; Src
0x18008ab3b  call    memcpy_0
0x18008ab40  mov     rax, [rbp+Buffer]
0x18008ab44  mov     rcx, [r14]
0x18008ab47  movzx   edx, word ptr [rax+10h]
0x18008ab4b  shr     rdx, 1
0x18008ab4e  mov     [rcx+rdx*2], r12w
0x18008ab53  test    rsi, rsi
0x18008ab56  jz      short loc_18008ABAB
0x18008ab58  mov     rax, [rbp+Buffer]
0x18008ab5c  cmp     [rax+20h], r12w
0x18008ab61  jz      short loc_18008ABAB
0x18008ab63  movzx   ecx, word ptr [rax+20h]
0x18008ab67  mov     rdx, rsi; Buffer
0x18008ab6a  add     ecx, 2; ByteCount
0x18008ab6d  call    cs:__imp_NetApiBufferAllocate
0x18008ab74  nop     dword ptr [rax+rax+00h]
0x18008ab79  mov     ebx, eax
0x18008ab7b  test    eax, eax
0x18008ab7d  jnz     loc_18008A9E0
0x18008ab83  mov     rdx, [rbp+Buffer]
0x18008ab87  mov     rcx, [rsi]; void *
0x18008ab8a  movzx   r8d, word ptr [rdx+20h]; Size
0x18008ab8f  mov     rdx, [rdx+28h]; Src
0x18008ab93  call    memcpy_0
0x18008ab98  mov     rax, [rbp+Buffer]
0x18008ab9c  mov     rcx, [rsi]
0x18008ab9f  movzx   edx, word ptr [rax+20h]
0x18008aba3  shr     rdx, 1
0x18008aba6  mov     [rcx+rdx*2], r12w
0x18008abab  test    rdi, rdi
0x18008abae  jz      short loc_18008ABFC
0x18008abb0  mov     rcx, [rbp+Buffer]
0x18008abb4  xor     r8d, r8d; Pattern
0x18008abb7  add     rcx, 30h ; '0'; Source
0x18008abbb  lea     ebx, [r8+10h]
0x18008abbf  mov     edx, ebx; Length
0x18008abc1  call    cs:__imp_RtlCompareMemoryUlong
0x18008abc8  nop     dword ptr [rax+rax+00h]
0x18008abcd  cmp     rax, rbx
0x18008abd0  jz      short loc_18008ABFC
0x18008abd2  mov     rdx, rdi; Buffer
0x18008abd5  mov     ecx, ebx; ByteCount
0x18008abd7  call    cs:__imp_NetApiBufferAllocate
0x18008abde  nop     dword ptr [rax+rax+00h]
0x18008abe3  mov     ebx, eax
0x18008abe5  test    eax, eax
0x18008abe7  jnz     loc_18008A9E0
0x18008abed  mov     rax, [rbp+Buffer]
0x18008abf1  mov     rcx, [rdi]
0x18008abf4  movups  xmm0, xmmword ptr [rax+30h]
0x18008abf8  movdqu  xmmword ptr [rcx], xmm0
0x18008abfc  mov     rax, [rbp+Buffer]
0x18008ac00  mov     ebx, r12d
0x18008ac03  cmp     [rax+40h], r12
0x18008ac07  mov     rax, [rbp+arg_20]
0x18008ac0b  setz    cl
0x18008ac0e  mov     [rax], cl
0x18008ac10  jmp     loc_18008AA4B
```
