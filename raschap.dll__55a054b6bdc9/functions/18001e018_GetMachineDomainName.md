# GetMachineDomainName

- ea: `0x18001e018`
- end: `0x18001e117`
- name: `GetMachineDomainName`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dbfc`

## callees

- `0x180014610`
- `0x18001e018`
- `0x180025efc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001e078`
- `ntdll!RtlNtStatusToDosError` at `0x18001e09f`
- `ntdll!RtlNtStatusToDosError` at `0x18001e078`
- `ntdll!RtlNtStatusToDosError` at `0x18001e09f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e0b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e0b9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001e0f0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001e0f0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001e0fa`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001e0fa`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001e070`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001e070`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001e097`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001e097`

## pseudocode

```c
__int64 __fastcall GetMachineDomainName(_QWORD *a1)
{
  NTSTATUS v2; // eax
  ULONG v3; // ebx
  NTSTATUS v4; // eax
  __int64 v5; // rsi
  HLOCAL v6; // rax
  void *v7; // rdi
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+78h] [rbp+28h] BYREF
  PVOID PolicyHandle; // [rsp+80h] [rbp+30h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  PolicyHandle = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  v3 = RtlNtStatusToDosError(v2);
  if ( !v3 )
  {
    Buffer = 0;
    v4 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
    v3 = RtlNtStatusToDosError(v4);
    if ( !v3 )
    {
      v5 = *(unsigned __int16 *)Buffer;
      v6 = LocalAlloc(0x40u, v5 + 2);
      v7 = v6;
      if ( v6 )
      {
        memset_0(v6, 0, v5 + 2);
        memcpy_0(v7, *((const void **)Buffer + 1), *(unsigned __int16 *)Buffer);
        *a1 = v7;
      }
      LsaFreeMemory(Buffer);
    }
    LsaClose(PolicyHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x18001e018  mov     [rsp-18h+arg_0], rbx
0x18001e01d  mov     [rsp-18h+arg_18], rsi
0x18001e022  push    rbp
0x18001e023  push    rdi
0x18001e024  push    r14
0x18001e026  mov     rbp, rsp
0x18001e029  sub     rsp, 50h
0x18001e02d  mov     r14, rcx
0x18001e030  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001e038  xorps   xmm0, xmm0
0x18001e03b  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18001e043  xor     ecx, ecx; SystemName
0x18001e045  mov     [rbp+PolicyHandle], 0
0x18001e04d  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18001e051  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001e059  mov     r8d, 1; DesiredAccess
0x18001e05f  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18001e067  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18001e06b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001e070  call    cs:__imp_LsaOpenPolicy
0x18001e076  mov     ecx, eax; Status
0x18001e078  call    cs:__imp_RtlNtStatusToDosError
0x18001e07e  mov     ebx, eax
0x18001e080  test    eax, eax
0x18001e082  jnz     short loc_18001E100
0x18001e084  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18001e088  lea     r8, [rbp+Buffer]; Buffer
0x18001e08c  lea     edx, [rax+3]; InformationClass
0x18001e08f  mov     [rbp+Buffer], 0
0x18001e097  call    cs:__imp_LsaQueryInformationPolicy
0x18001e09d  mov     ecx, eax; Status
0x18001e09f  call    cs:__imp_RtlNtStatusToDosError
0x18001e0a5  mov     ebx, eax
0x18001e0a7  test    eax, eax
0x18001e0a9  jnz     short loc_18001E0F6
0x18001e0ab  mov     rax, [rbp+Buffer]
0x18001e0af  lea     ecx, [rbx+40h]; uFlags
0x18001e0b2  movzx   esi, word ptr [rax]
0x18001e0b5  lea     rdx, [rsi+2]; uBytes
0x18001e0b9  call    cs:__imp_LocalAlloc
0x18001e0bf  mov     rdi, rax
0x18001e0c2  test    rax, rax
0x18001e0c5  jz      short loc_18001E0EC
0x18001e0c7  lea     r8, [rsi+2]; Size
0x18001e0cb  xor     edx, edx; Val
0x18001e0cd  mov     rcx, rax; void *
0x18001e0d0  call    memset_0
0x18001e0d5  mov     rdx, [rbp+Buffer]
0x18001e0d9  mov     rcx, rdi; void *
0x18001e0dc  movzx   r8d, word ptr [rdx]; Size
0x18001e0e0  mov     rdx, [rdx+8]; Src
0x18001e0e4  call    memcpy_0
0x18001e0e9  mov     [r14], rdi
0x18001e0ec  mov     rcx, [rbp+Buffer]; Buffer
0x18001e0f0  call    cs:__imp_LsaFreeMemory
0x18001e0f6  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18001e0fa  call    cs:__imp_LsaClose
0x18001e100  lea     r11, [rsp+50h+var_s0]
0x18001e105  mov     eax, ebx
0x18001e107  mov     rbx, [r11+20h]
0x18001e10b  mov     rsi, [r11+38h]
0x18001e10f  mov     rsp, r11
0x18001e112  pop     r14
0x18001e114  pop     rdi
0x18001e115  pop     rbp
0x18001e116  retn
```
