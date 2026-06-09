# AslRegistryGetKey

- ea: `0x18000e624`
- end: `0x18000e715`
- name: `AslRegistryGetKey`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800170fc`

## callees

- `0x18000e240`
- `0x18000e53c`
- `0x18000e624`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18000e6bd`
- `ntdll!ZwOpenKey` at `0x18000e6bd`
- `ntdll!RtlFreeHeap` at `0x18000e704`
- `ntdll!RtlFreeHeap` at `0x18000e704`

## string_xrefs

- `0x18000e661`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x18000e673`: `AslRegistryGetKey`
- `0x18000e6d0`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 v7; // r8
  PVOID P[2]; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+28h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  v4 = AslRegistryBuildMachinePath((PUNICODE_STRING)P, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = "AslRegistryBuildMachinePath failed %x for %ws";
    v7 = 1718;
LABEL_3:
    AslLogCallPrintf(1, "AslRegistryGetKey", v7, v6, v4, a2);
    goto LABEL_8;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v5 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
  }
  else if ( v4 != -1073741772 )
  {
    v6 = "NtOpenKey failed %x for %ws";
    v7 = 1761;
    goto LABEL_3;
  }
LABEL_8:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  return v5;
}

```

## disassembly

```asm
0x18000e624  push    rbp
0x18000e626  push    rbx
0x18000e627  push    rsi
0x18000e628  push    rdi
0x18000e629  mov     rbp, rsp
0x18000e62c  sub     rsp, 78h
0x18000e630  xorps   xmm0, xmm0
0x18000e633  xor     eax, eax
0x18000e635  mov     [rcx], rax
0x18000e638  mov     rsi, rcx
0x18000e63b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000e63f  lea     rcx, [rbp+P]; Destination
0x18000e643  mov     [rbp+KeyHandle], rax
0x18000e647  mov     rdi, rdx
0x18000e64a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000e64e  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18000e652  movups  xmmword ptr [rbp+P], xmm0
0x18000e656  call    AslRegistryBuildMachinePath
0x18000e65b  mov     ebx, eax
0x18000e65d  test    eax, eax
0x18000e65f  jns     short loc_18000E68A
0x18000e661  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x18000e668  mov     r8d, 6B6h
0x18000e66e  mov     [rsp+78h+var_50], rdi
0x18000e673  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x18000e67a  mov     ecx, 1
0x18000e67f  mov     [rsp+78h+var_58], eax
0x18000e683  call    AslLogCallPrintf
0x18000e688  jmp     short loc_18000E6EC
0x18000e68a  lea     rax, [rbp+P]
0x18000e68e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000e695  xorps   xmm0, xmm0
0x18000e698  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000e69c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000e6a0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000e6a8  mov     edx, 1; DesiredAccess
0x18000e6ad  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000e6b4  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18000e6b8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000e6bd  call    cs:__imp_ZwOpenKey
0x18000e6c3  mov     ebx, eax
0x18000e6c5  test    eax, eax
0x18000e6c7  jns     short loc_18000E6DF
0x18000e6c9  cmp     eax, 0C0000034h
0x18000e6ce  jz      short loc_18000E6EC
0x18000e6d0  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x18000e6d7  mov     r8d, 6E1h
0x18000e6dd  jmp     short loc_18000E66E
0x18000e6df  mov     rax, [rbp+KeyHandle]
0x18000e6e3  xor     ebx, ebx
0x18000e6e5  mov     [rsi], rax
0x18000e6e8  mov     [rbp+KeyHandle], rbx
0x18000e6ec  mov     r8, [rbp+P+8]; P
0x18000e6f0  test    r8, r8
0x18000e6f3  jz      short loc_18000E70A
0x18000e6f5  mov     rcx, gs:60h
0x18000e6fe  xor     edx, edx; Flags
0x18000e700  mov     rcx, [rcx+30h]; HeapHandle
0x18000e704  call    cs:__imp_RtlFreeHeap
0x18000e70a  mov     eax, ebx
0x18000e70c  add     rsp, 78h
0x18000e710  pop     rdi
0x18000e711  pop     rsi
0x18000e712  pop     rbx
0x18000e713  pop     rbp
0x18000e714  retn
```
