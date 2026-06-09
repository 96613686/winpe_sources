# CConfigurationSettings::LoadDisableSiteAwarenessSetting(CRegistry &)

- ea: `0x140006980`
- end: `0x140006aa9`
- name: `?LoadDisableSiteAwarenessSetting@CConfigurationSettings@@AEAAXAEAVCRegistry@@@Z`
- size: `297`
- prototype: `void(CConfigurationSettings *__hidden this, struct CRegistry *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140005fc8`

## callees

- `0x140005f74`
- `0x140006980`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140006a50`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140006a50`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140006a40`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x140006a40`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1400069e5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1400069e5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1400069c5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1400069c5`

## pseudocode

```c
void __fastcall CConfigurationSettings::LoadDisableSiteAwarenessSetting(
        CConfigurationSettings *this,
        struct CRegistry *a2)
{
  char v4; // bl
  PVOID PolicyHandle; // [rsp+30h] [rbp-40h] BYREF
  PVOID Buffer; // [rsp+38h] [rbp-38h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v8; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v9; // [rsp+A8h] [rbp+38h] BYREF

  Buffer = 0;
  PolicyHandle = 0;
  v4 = 1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle) < 0 )
    goto LABEL_17;
  if ( LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer) >= 0 )
  {
    if ( *((_DWORD *)Buffer + 12)
      || *((_WORD *)Buffer + 26)
      || *((_WORD *)Buffer + 27)
      || *((_BYTE *)Buffer + 56)
      || *((_BYTE *)Buffer + 57)
      || *((_BYTE *)Buffer + 58)
      || *((_BYTE *)Buffer + 59)
      || *((_BYTE *)Buffer + 60)
      || *((_BYTE *)Buffer + 61)
      || *((_BYTE *)Buffer + 62)
      || *((_BYTE *)Buffer + 63) )
    {
      v4 = 0;
    }
    LsaFreeMemory(Buffer);
  }
  LsaClose(PolicyHandle);
  if ( v4 )
  {
LABEL_17:
    v8 = *((unsigned __int8 *)this + 64);
    v9 = 1;
    DfspLoadDwordSetting(a2, L"DfsDisableSiteAwareness", 0, &v9, &v8);
    *((_BYTE *)this + 64) = v8;
  }
}

```

## disassembly

```asm
0x140006980  mov     [rsp-18h+arg_0], rbx
0x140006985  mov     [rsp-18h+arg_8], rsi
0x14000698a  push    rbp
0x14000698b  push    rdi
0x14000698c  push    r14
0x14000698e  mov     rbp, rsp
0x140006991  sub     rsp, 70h
0x140006995  xorps   xmm0, xmm0
0x140006998  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x14000699c  xor     r14d, r14d
0x14000699f  mov     rsi, rdx
0x1400069a2  mov     rdi, rcx
0x1400069a5  mov     [rbp+Buffer], r14
0x1400069a9  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1400069ad  mov     [rbp+PolicyHandle], r14
0x1400069b1  xor     ecx, ecx; SystemName
0x1400069b3  mov     bl, 1
0x1400069b5  lea     r8d, [r14+1]; DesiredAccess
0x1400069b9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400069bd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400069c1  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400069c5  call    cs:__imp_LsaOpenPolicy
0x1400069cc  nop     dword ptr [rax+rax+00h]
0x1400069d1  test    eax, eax
0x1400069d3  js      loc_140006A60
0x1400069d9  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1400069dd  lea     r8, [rbp+Buffer]; Buffer
0x1400069e1  lea     edx, [r14+0Ch]; InformationClass
0x1400069e5  call    cs:__imp_LsaQueryInformationPolicy
0x1400069ec  nop     dword ptr [rax+rax+00h]
0x1400069f1  test    eax, eax
0x1400069f3  js      short loc_140006A4C
0x1400069f5  mov     rcx, [rbp+Buffer]; Buffer
0x1400069f9  cmp     [rcx+30h], r14d
0x1400069fd  jnz     short loc_140006A3D
0x1400069ff  cmp     [rcx+34h], r14w
0x140006a04  jnz     short loc_140006A3D
0x140006a06  cmp     [rcx+36h], r14w
0x140006a0b  jnz     short loc_140006A3D
0x140006a0d  cmp     [rcx+38h], r14b
0x140006a11  jnz     short loc_140006A3D
0x140006a13  cmp     [rcx+39h], r14b
0x140006a17  jnz     short loc_140006A3D
0x140006a19  cmp     [rcx+3Ah], r14b
0x140006a1d  jnz     short loc_140006A3D
0x140006a1f  cmp     [rcx+3Bh], r14b
0x140006a23  jnz     short loc_140006A3D
0x140006a25  cmp     [rcx+3Ch], r14b
0x140006a29  jnz     short loc_140006A3D
0x140006a2b  cmp     [rcx+3Dh], r14b
0x140006a2f  jnz     short loc_140006A3D
0x140006a31  cmp     [rcx+3Eh], r14b
0x140006a35  jnz     short loc_140006A3D
0x140006a37  cmp     [rcx+3Fh], r14b
0x140006a3b  jz      short loc_140006A40
0x140006a3d  mov     bl, r14b
0x140006a40  call    cs:__imp_LsaFreeMemory
0x140006a47  nop     dword ptr [rax+rax+00h]
0x140006a4c  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x140006a50  call    cs:__imp_LsaClose
0x140006a57  nop     dword ptr [rax+rax+00h]
0x140006a5c  test    bl, bl
0x140006a5e  jz      short loc_140006A93
0x140006a60  movzx   eax, byte ptr [rdi+40h]
0x140006a64  lea     r9, [rbp+arg_18]; unsigned int *
0x140006a68  mov     [rbp+arg_10], eax
0x140006a6b  lea     rdx, aDfsdisablesite; "DfsDisableSiteAwareness"
0x140006a72  lea     rax, [rbp+arg_10]
0x140006a76  mov     [rbp+arg_18], 1
0x140006a7d  xor     r8d, r8d; unsigned int
0x140006a80  mov     [rsp+70h+var_50], rax; unsigned int *
0x140006a85  mov     rcx, rsi; struct CRegistry *
0x140006a88  call    ?DfspLoadDwordSetting@@YAXAEAVCRegistry@@PEBGKPEBKPEAK@Z; DfspLoadDwordSetting(CRegistry &,ushort const *,ulong,ulong const *,ulong *)
0x140006a8d  mov     al, byte ptr [rbp+arg_10]
0x140006a90  mov     [rdi+40h], al
0x140006a93  lea     r11, [rsp+70h+var_s0]
0x140006a98  mov     rbx, [r11+20h]
0x140006a9c  mov     rsi, [r11+28h]
0x140006aa0  mov     rsp, r11
0x140006aa3  pop     r14
0x140006aa5  pop     rdi
0x140006aa6  pop     rbp
0x140006aa7  retn
```
