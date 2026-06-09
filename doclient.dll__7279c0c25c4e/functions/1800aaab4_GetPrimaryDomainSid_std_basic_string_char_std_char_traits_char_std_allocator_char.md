# GetPrimaryDomainSid(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800aaab4`
- end: `0x1800aac14`
- name: `?GetPrimaryDomainSid@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800d68a8`

## callees

- `0x1800086a8`
- `0x1800087d4`
- `0x18000933c`
- `0x1800a1ea4`
- `0x1800aaa00`
- `0x1800aaab4`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800aabdc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800aabdc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800aabeb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800aabeb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800aab57`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800aab57`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800aab19`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800aab19`

## string_xrefs

- `0x1800aabb8`: `GetPrimaryDomainSid`

## pseudocode

```c
__int64 __fastcall GetPrimaryDomainSid(const char *a1)
{
  const char *v1; // rbx
  const char *v2; // rax
  NTSTATUS v3; // eax
  unsigned int v4; // edi
  NTSTATUS v5; // eax
  int v6; // edx
  int v7; // eax
  PVOID v8; // rcx
  int v10; // [rsp+20h] [rbp-60h]
  PVOID Buffer; // [rsp+30h] [rbp-50h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-48h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  *((_QWORD *)a1 + 2) = 0;
  v1 = a1;
  v2 = a1;
  if ( *((_QWORD *)a1 + 3) > 0xFu )
    v2 = *(const char **)a1;
  *v2 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v3 >= 0 )
  {
    Buffer = 0;
    v5 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
    if ( v5 >= 0 )
    {
      v7 = SidToStringSid(*((_QWORD *)Buffer + 2), v1);
      v4 = v7;
      if ( v7 >= 0 )
      {
        if ( *((_QWORD *)v1 + 3) > 0xFu )
          v1 = *(const char **)v1;
        LogMessage(5u, "GetPrimaryDomainSid", 0xBDu, "DomainId = %s", v1);
        v4 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBC,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
          (const char *)(unsigned int)v7,
          v10);
      }
    }
    else
    {
      v4 = wil::details::NtStatusToHr((wil::details *)(unsigned int)v5, v6);
    }
    v8 = Buffer;
    Buffer = 0;
    if ( v8 )
      LsaFreeMemory(v8);
  }
  else
  {
    v4 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0xB6,
           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
           (const char *)(unsigned int)v3,
           v10);
  }
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v4;
}

```

## disassembly

```asm
0x1800aaab4  mov     [rsp-8+arg_8], rbx
0x1800aaab9  mov     [rsp-8+arg_10], rdi
0x1800aaabe  push    rbp
0x1800aaabf  mov     rbp, rsp
0x1800aaac2  sub     rsp, 80h
0x1800aaac9  mov     rax, cs:__security_cookie
0x1800aaad0  xor     rax, rsp
0x1800aaad3  mov     [rbp+var_10], rax
0x1800aaad7  mov     qword ptr [rcx+10h], 0
0x1800aaadf  mov     rbx, rcx
0x1800aaae2  cmp     qword ptr [rcx+18h], 0Fh
0x1800aaae7  mov     rax, rcx
0x1800aaaea  jbe     short loc_1800AAAEF
0x1800aaaec  mov     rax, [rcx]
0x1800aaaef  mov     byte ptr [rax], 0
0x1800aaaf2  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800aaaf6  xorps   xmm0, xmm0
0x1800aaaf9  mov     [rbp+PolicyHandle], 0
0x1800aab01  mov     r8d, 1; DesiredAccess
0x1800aab07  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800aab0b  xor     ecx, ecx; SystemName
0x1800aab0d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800aab11  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800aab15  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800aab19  call    cs:__imp_LsaOpenPolicy
0x1800aab1f  test    eax, eax
0x1800aab21  jns     short loc_1800AAB42
0x1800aab23  mov     rcx, [rbp+8]; this
0x1800aab27  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800aab2e  mov     r9d, eax; char *
0x1800aab31  mov     edx, 0B6h; void *
0x1800aab36  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800aab3b  mov     edi, eax
0x1800aab3d  jmp     loc_1800AABE2
0x1800aab42  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800aab46  lea     r8, [rbp+Buffer]; Buffer
0x1800aab4a  mov     edx, 3; InformationClass
0x1800aab4f  mov     [rbp+Buffer], 0
0x1800aab57  call    cs:__imp_LsaQueryInformationPolicy
0x1800aab5d  test    eax, eax
0x1800aab5f  jns     short loc_1800AAB6C
0x1800aab61  mov     ecx, eax; this
0x1800aab63  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800aab68  mov     edi, eax
0x1800aab6a  jmp     short loc_1800AABCB
0x1800aab6c  mov     rcx, [rbp+Buffer]
0x1800aab70  mov     rdx, rbx
0x1800aab73  mov     rcx, [rcx+10h]
0x1800aab77  call    ?SidToStringSid@@YAJPEAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; SidToStringSid(void *,std::string &)
0x1800aab7c  mov     edi, eax
0x1800aab7e  test    eax, eax
0x1800aab80  jns     short loc_1800AAB9C
0x1800aab82  mov     rcx, [rbp+8]; this
0x1800aab86  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800aab8d  mov     r9d, eax; char *
0x1800aab90  mov     edx, 0BCh; void *
0x1800aab95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aab9a  jmp     short loc_1800AABCB
0x1800aab9c  cmp     qword ptr [rbx+18h], 0Fh
0x1800aaba1  jbe     short loc_1800AABA6
0x1800aaba3  mov     rbx, [rbx]
0x1800aaba6  lea     r9, aDomainidS; "DomainId = %s"
0x1800aabad  mov     qword ptr [rsp+80h+var_60], rbx
0x1800aabb2  mov     r8d, 0BDh; unsigned int
0x1800aabb8  lea     rdx, aGetprimarydoma; "GetPrimaryDomainSid"
0x1800aabbf  mov     ecx, 5; unsigned __int8
0x1800aabc4  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800aabc9  xor     edi, edi
0x1800aabcb  mov     rcx, [rbp+Buffer]; Buffer
0x1800aabcf  mov     [rbp+Buffer], 0
0x1800aabd7  test    rcx, rcx
0x1800aabda  jz      short loc_1800AABE2
0x1800aabdc  call    cs:__imp_LsaFreeMemory
0x1800aabe2  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800aabe6  test    rcx, rcx
0x1800aabe9  jz      short loc_1800AABF1
0x1800aabeb  call    cs:__imp_LsaClose
0x1800aabf1  mov     eax, edi
0x1800aabf3  mov     rcx, [rbp+var_10]
0x1800aabf7  xor     rcx, rsp; StackCookie
0x1800aabfa  call    __security_check_cookie
0x1800aabff  lea     r11, [rsp+80h+var_s0]
0x1800aac07  mov     rbx, [r11+18h]
0x1800aac0b  mov     rdi, [r11+20h]
0x1800aac0f  mov     rsp, r11
0x1800aac12  pop     rbp
0x1800aac13  retn
```
