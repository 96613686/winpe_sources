# AslRegistryGetKey

- ea: `0x180066ef4`
- end: `0x180066fe5`
- name: `AslRegistryGetKey`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006b25c`

## callees

- `0x180066c10`
- `0x180066e0c`
- `0x180066ef4`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x180066f8d`
- `ntdll!ZwOpenKey` at `0x180066f8d`
- `ntdll!RtlFreeHeap` at `0x180066fd4`
- `ntdll!RtlFreeHeap` at `0x180066fd4`

## string_xrefs

- `0x180066f31`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x180066f43`: `AslRegistryGetKey`
- `0x180066fa0`: `NtOpenKey failed %x for %ws`

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
0x180066ef4  push    rbp
0x180066ef6  push    rbx
0x180066ef7  push    rsi
0x180066ef8  push    rdi
0x180066ef9  mov     rbp, rsp
0x180066efc  sub     rsp, 78h
0x180066f00  xorps   xmm0, xmm0
0x180066f03  xor     eax, eax
0x180066f05  mov     [rcx], rax
0x180066f08  mov     rsi, rcx
0x180066f0b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180066f0f  lea     rcx, [rbp+P]; Destination
0x180066f13  mov     [rbp+KeyHandle], rax
0x180066f17  mov     rdi, rdx
0x180066f1a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180066f1e  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180066f22  movups  xmmword ptr [rbp+P], xmm0
0x180066f26  call    AslRegistryBuildMachinePath
0x180066f2b  mov     ebx, eax
0x180066f2d  test    eax, eax
0x180066f2f  jns     short loc_180066F5A
0x180066f31  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x180066f38  mov     r8d, 6B6h
0x180066f3e  mov     [rsp+78h+var_50], rdi
0x180066f43  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x180066f4a  mov     ecx, 1
0x180066f4f  mov     [rsp+78h+var_58], eax
0x180066f53  call    AslLogCallPrintf
0x180066f58  jmp     short loc_180066FBC
0x180066f5a  lea     rax, [rbp+P]
0x180066f5e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180066f65  xorps   xmm0, xmm0
0x180066f68  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180066f6c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180066f70  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180066f78  mov     edx, 1; DesiredAccess
0x180066f7d  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180066f84  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180066f88  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180066f8d  call    cs:__imp_ZwOpenKey
0x180066f93  mov     ebx, eax
0x180066f95  test    eax, eax
0x180066f97  jns     short loc_180066FAF
0x180066f99  cmp     eax, 0C0000034h
0x180066f9e  jz      short loc_180066FBC
0x180066fa0  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x180066fa7  mov     r8d, 6E1h
0x180066fad  jmp     short loc_180066F3E
0x180066faf  mov     rax, [rbp+KeyHandle]
0x180066fb3  xor     ebx, ebx
0x180066fb5  mov     [rsi], rax
0x180066fb8  mov     [rbp+KeyHandle], rbx
0x180066fbc  mov     r8, [rbp+P+8]; P
0x180066fc0  test    r8, r8
0x180066fc3  jz      short loc_180066FDA
0x180066fc5  mov     rcx, gs:60h
0x180066fce  xor     edx, edx; Flags
0x180066fd0  mov     rcx, [rcx+30h]; HeapHandle
0x180066fd4  call    cs:__imp_RtlFreeHeap
0x180066fda  mov     eax, ebx
0x180066fdc  add     rsp, 78h
0x180066fe0  pop     rdi
0x180066fe1  pop     rsi
0x180066fe2  pop     rbx
0x180066fe3  pop     rbp
0x180066fe4  retn
```
