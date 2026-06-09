# IsNT4Domain(void)

- ea: `0x18002c738`
- end: `0x18002c82b`
- name: `?IsNT4Domain@@YAHXZ`
- size: `243`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a794`

## callees

- `0x180007f10`
- `0x18002c738`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002c80c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002c80c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002c78c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002c78c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002c7f7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002c7f7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18002c7ca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18002c7ca`

## string_xrefs

- `0x18002c7a2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
_BOOL8 IsNT4Domain(void)
{
  BOOL v0; // ebx
  NTSTATUS v1; // eax
  __int64 v2; // r9
  PVOID v3; // rcx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+60h] [rbp+10h] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp+18h] BYREF

  v0 = 0;
  PolicyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  Buffer = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v1 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v1 < 0 )
  {
    v2 = 5523;
LABEL_3:
    DebugTraceError((unsigned int)v1, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v2);
    v3 = Buffer;
    goto LABEL_8;
  }
  v1 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
  if ( v1 < 0 )
  {
    v2 = 5532;
    goto LABEL_3;
  }
  v3 = Buffer;
  if ( !Buffer )
    goto LABEL_10;
  v0 = *((_QWORD *)Buffer + 3) == 0;
LABEL_8:
  if ( v3 )
    LsaFreeMemory(v3);
LABEL_10:
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v0;
}

```

## disassembly

```asm
0x18002c738  mov     [rsp-8+arg_10], rbx
0x18002c73d  mov     [rsp-8+arg_18], rsi
0x18002c742  push    rbp
0x18002c743  mov     rbp, rsp
0x18002c746  sub     rsp, 50h
0x18002c74a  xor     ebx, ebx
0x18002c74c  mov     [rbp+PolicyHandle], 0
0x18002c754  xorps   xmm0, xmm0
0x18002c757  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002c75f  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18002c763  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18002c76b  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002c76f  mov     [rbp+Buffer], 0
0x18002c777  lea     esi, [rbx+1]
0x18002c77a  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18002c77e  mov     r8d, esi; DesiredAccess
0x18002c781  mov     [rbp+ObjectAttributes.ObjectName], rbx
0x18002c785  xor     ecx, ecx; SystemName
0x18002c787  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c78c  call    cs:__imp_LsaOpenPolicy
0x18002c793  nop     dword ptr [rax+rax+00h]
0x18002c798  test    eax, eax
0x18002c79a  jns     short loc_18002C7BD
0x18002c79c  mov     r9d, 1593h
0x18002c7a2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002c7a9  mov     ecx, eax
0x18002c7ab  lea     rdx, aStatus; "Status"
0x18002c7b2  call    DebugTraceError
0x18002c7b7  mov     rcx, [rbp+Buffer]
0x18002c7bb  jmp     short loc_18002C7F2
0x18002c7bd  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002c7c1  lea     r8, [rbp+Buffer]; Buffer
0x18002c7c5  mov     edx, 0Ch; InformationClass
0x18002c7ca  call    cs:__imp_LsaQueryInformationPolicy
0x18002c7d1  nop     dword ptr [rax+rax+00h]
0x18002c7d6  test    eax, eax
0x18002c7d8  jns     short loc_18002C7E2
0x18002c7da  mov     r9d, 159Ch
0x18002c7e0  jmp     short loc_18002C7A2
0x18002c7e2  mov     rcx, [rbp+Buffer]; Buffer
0x18002c7e6  test    rcx, rcx
0x18002c7e9  jz      short loc_18002C803
0x18002c7eb  cmp     [rcx+18h], rbx
0x18002c7ef  cmovz   ebx, esi
0x18002c7f2  test    rcx, rcx
0x18002c7f5  jz      short loc_18002C803
0x18002c7f7  call    cs:__imp_LsaFreeMemory
0x18002c7fe  nop     dword ptr [rax+rax+00h]
0x18002c803  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18002c807  test    rcx, rcx
0x18002c80a  jz      short loc_18002C818
0x18002c80c  call    cs:__imp_LsaClose
0x18002c813  nop     dword ptr [rax+rax+00h]
0x18002c818  mov     rsi, [rsp+50h+arg_18]
0x18002c81d  mov     eax, ebx
0x18002c81f  mov     rbx, [rsp+50h+arg_10]
0x18002c824  add     rsp, 50h
0x18002c828  pop     rbp
0x18002c829  retn
```
