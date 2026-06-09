# DfsXForest::InitializeForestRootName(void)

- ea: `0x14003d6ac`
- end: `0x14003d838`
- name: `?InitializeForestRootName@DfsXForest@@AEAAKXZ`
- size: `396`
- prototype: `unsigned int __fastcall(DfsXForest *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003d500`

## callees

- `0x140005a94`
- `0x14003d6ac`
- `0x140058ce0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14003d6ca`
- `ntdll!RtlInitUnicodeString` at `0x14003d6ca`
- `ntdll!RtlNtStatusToDosError` at `0x14003d813`
- `ntdll!RtlNtStatusToDosError` at `0x14003d813`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14003d801`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x14003d801`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x14003d7f1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x14003d7f1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x14003d769`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x14003d769`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x14003d6f3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x14003d6f3`

## pseudocode

```c
__int64 __fastcall DfsXForest::InitializeForestRootName(struct _UNICODE_STRING *this)
{
  unsigned int UnicodeString; // edi
  unsigned int v3; // eax
  NTSTATUS v4; // ebx
  unsigned int v5; // eax
  _WORD v7[2]; // [rsp+20h] [rbp-40h] BYREF
  int v8; // [rsp+24h] [rbp-3Ch]
  __int64 v9; // [rsp+28h] [rbp-38h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+90h] [rbp+30h] BYREF
  PVOID PolicyHandle; // [rsp+98h] [rbp+38h] BYREF

  UnicodeString = 0;
  PolicyHandle = 0;
  RtlInitUnicodeString(this, 0);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  v4 = v3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (v3 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 13, WPP_5e4bfb9fc74e396487028932ae6e6e2a_Traceguids, v3);
  }
  if ( v4 < 0 )
    return RtlNtStatusToDosError(v4);
  Buffer = 0;
  v5 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
  v4 = v5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (v5 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 14, WPP_5e4bfb9fc74e396487028932ae6e6e2a_Traceguids, v5);
  }
  if ( v4 >= 0 )
  {
    v8 = 0;
    v9 = *((_QWORD *)Buffer + 5);
    v7[0] = *((_WORD *)Buffer + 16);
    v7[1] = *((_WORD *)Buffer + 17);
    UnicodeString = DfsCreateUnicodeString(this, v7);
    LsaFreeMemory(Buffer);
  }
  LsaClose(PolicyHandle);
  if ( v4 < 0 )
    return RtlNtStatusToDosError(v4);
  return UnicodeString;
}

```

## disassembly

```asm
0x14003d6ac  mov     [rsp-28h+arg_10], rbx
0x14003d6b1  push    rbp
0x14003d6b2  push    rsi
0x14003d6b3  push    rdi
0x14003d6b4  push    r12
0x14003d6b6  push    r14
0x14003d6b8  mov     rbp, rsp
0x14003d6bb  sub     rsp, 60h
0x14003d6bf  xor     edi, edi
0x14003d6c1  xor     edx, edx; SourceString
0x14003d6c3  and     [rbp+PolicyHandle], rdi
0x14003d6c7  mov     r14, rcx
0x14003d6ca  call    cs:__imp_RtlInitUnicodeString
0x14003d6d1  nop     dword ptr [rax+rax+00h]
0x14003d6d6  xorps   xmm0, xmm0
0x14003d6d9  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x14003d6dd  lea     r8d, [rdi+1]; DesiredAccess
0x14003d6e1  xor     ecx, ecx; SystemName
0x14003d6e3  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x14003d6e7  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003d6eb  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003d6ef  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003d6f3  call    cs:__imp_LsaOpenPolicy
0x14003d6fa  nop     dword ptr [rax+rax+00h]
0x14003d6ff  mov     ebx, eax
0x14003d701  lea     r12, WPP_GLOBAL_Control
0x14003d708  cmp     cs:WPP_GLOBAL_Control, r12
0x14003d70f  lea     esi, [rdi+20h]
0x14003d712  jz      short loc_14003D750
0x14003d714  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003d71b  test    rcx, rcx
0x14003d71e  jz      short loc_14003D750
0x14003d720  neg     eax
0x14003d722  mov     eax, esi
0x14003d724  sbb     edx, edx
0x14003d726  and     edx, 0FFFFFFECh
0x14003d729  add     edx, 1Fh
0x14003d72c  bts     eax, edx
0x14003d72f  test    [rcx+1Ch], eax
0x14003d732  jz      short loc_14003D750
0x14003d734  cmp     byte ptr [rcx+19h], 1
0x14003d738  jb      short loc_14003D750
0x14003d73a  mov     rcx, [rcx+10h]
0x14003d73e  lea     edx, [rdi+0Dh]
0x14003d741  mov     r9d, ebx
0x14003d744  lea     r8, WPP_5e4bfb9fc74e396487028932ae6e6e2a_Traceguids
0x14003d74b  call    WPP_SF_D
0x14003d750  test    ebx, ebx
0x14003d752  js      loc_14003D811
0x14003d758  and     [rbp+Buffer], rdi
0x14003d75c  lea     r8, [rbp+Buffer]; Buffer
0x14003d760  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x14003d764  mov     edx, 0Ch; InformationClass
0x14003d769  call    cs:__imp_LsaQueryInformationPolicy
0x14003d770  nop     dword ptr [rax+rax+00h]
0x14003d775  mov     ebx, eax
0x14003d777  cmp     cs:WPP_GLOBAL_Control, r12
0x14003d77e  jz      short loc_14003D7BC
0x14003d780  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003d787  test    rcx, rcx
0x14003d78a  jz      short loc_14003D7BC
0x14003d78c  neg     eax
0x14003d78e  sbb     edx, edx
0x14003d790  and     edx, 0FFFFFFECh
0x14003d793  add     edx, 1Fh
0x14003d796  bts     esi, edx
0x14003d799  test    [rcx+1Ch], esi
0x14003d79c  jz      short loc_14003D7BC
0x14003d79e  cmp     byte ptr [rcx+19h], 1
0x14003d7a2  jb      short loc_14003D7BC
0x14003d7a4  mov     rcx, [rcx+10h]
0x14003d7a8  lea     r8, WPP_5e4bfb9fc74e396487028932ae6e6e2a_Traceguids
0x14003d7af  mov     edx, 0Eh
0x14003d7b4  mov     r9d, ebx
0x14003d7b7  call    WPP_SF_D
0x14003d7bc  test    ebx, ebx
0x14003d7be  js      short loc_14003D7FD
0x14003d7c0  mov     rcx, [rbp+Buffer]
0x14003d7c4  lea     rdx, [rbp+var_40]
0x14003d7c8  and     [rbp+var_3C], edi
0x14003d7cb  mov     rax, [rcx+28h]
0x14003d7cf  mov     [rbp+var_38], rax
0x14003d7d3  movzx   eax, word ptr [rcx+20h]
0x14003d7d7  mov     [rbp+var_40], ax
0x14003d7db  movzx   eax, word ptr [rcx+22h]
0x14003d7df  mov     rcx, r14
0x14003d7e2  mov     [rbp+var_3E], ax
0x14003d7e6  call    DfsCreateUnicodeString
0x14003d7eb  mov     rcx, [rbp+Buffer]; Buffer
0x14003d7ef  mov     edi, eax
0x14003d7f1  call    cs:__imp_LsaFreeMemory
0x14003d7f8  nop     dword ptr [rax+rax+00h]
0x14003d7fd  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x14003d801  call    cs:__imp_LsaClose
0x14003d808  nop     dword ptr [rax+rax+00h]
0x14003d80d  test    ebx, ebx
0x14003d80f  jns     short loc_14003D821
0x14003d811  mov     ecx, ebx; Status
0x14003d813  call    cs:__imp_RtlNtStatusToDosError
0x14003d81a  nop     dword ptr [rax+rax+00h]
0x14003d81f  mov     edi, eax
0x14003d821  mov     rbx, [rsp+60h+arg_10]
0x14003d829  mov     eax, edi
0x14003d82b  add     rsp, 60h
0x14003d82f  pop     r14
0x14003d831  pop     r12
0x14003d833  pop     rdi
0x14003d834  pop     rsi
0x14003d835  pop     rbp
0x14003d836  retn
```
