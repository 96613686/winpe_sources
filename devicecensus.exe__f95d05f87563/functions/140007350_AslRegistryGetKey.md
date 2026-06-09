# AslRegistryGetKey

- ea: `0x140007350`
- end: `0x140007441`
- name: `AslRegistryGetKey`
- size: `241`
- prototype: `__int64 __fastcall(void **, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140005918`

## callees

- `0x140007074`
- `0x140007268`
- `0x140007350`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x1400073e9`
- `ntdll!ZwOpenKey` at `0x1400073e9`
- `ntdll!RtlFreeHeap` at `0x140007430`
- `ntdll!RtlFreeHeap` at `0x140007430`

## string_xrefs

- `0x14000738d`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x14000739f`: `AslRegistryGetKey`
- `0x1400073fc`: `NtOpenKey failed %x for %ws`

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
0x140007350  push    rbp
0x140007352  push    rbx
0x140007353  push    rsi
0x140007354  push    rdi
0x140007355  mov     rbp, rsp
0x140007358  sub     rsp, 78h
0x14000735c  xorps   xmm0, xmm0
0x14000735f  xor     eax, eax
0x140007361  mov     [rcx], rax
0x140007364  mov     rsi, rcx
0x140007367  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000736b  lea     rcx, [rbp+P]; Destination
0x14000736f  mov     [rbp+KeyHandle], rax
0x140007373  mov     rdi, rdx
0x140007376  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000737a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000737e  movups  xmmword ptr [rbp+P], xmm0
0x140007382  call    AslRegistryBuildMachinePath
0x140007387  mov     ebx, eax
0x140007389  test    eax, eax
0x14000738b  jns     short loc_1400073B6
0x14000738d  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x140007394  mov     r8d, 6B6h
0x14000739a  mov     [rsp+78h+var_50], rdi
0x14000739f  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x1400073a6  mov     ecx, 1
0x1400073ab  mov     [rsp+78h+var_58], eax
0x1400073af  call    AslLogCallPrintf
0x1400073b4  jmp     short loc_140007418
0x1400073b6  lea     rax, [rbp+P]
0x1400073ba  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400073c1  xorps   xmm0, xmm0
0x1400073c4  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400073c8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400073cc  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400073d4  mov     edx, 1; DesiredAccess
0x1400073d9  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1400073e0  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400073e4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400073e9  call    cs:__imp_ZwOpenKey
0x1400073ef  mov     ebx, eax
0x1400073f1  test    eax, eax
0x1400073f3  jns     short loc_14000740B
0x1400073f5  cmp     eax, 0C0000034h
0x1400073fa  jz      short loc_140007418
0x1400073fc  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x140007403  mov     r8d, 6E1h
0x140007409  jmp     short loc_14000739A
0x14000740b  mov     rax, [rbp+KeyHandle]
0x14000740f  xor     ebx, ebx
0x140007411  mov     [rsi], rax
0x140007414  mov     [rbp+KeyHandle], rbx
0x140007418  mov     r8, [rbp+P+8]; P
0x14000741c  test    r8, r8
0x14000741f  jz      short loc_140007436
0x140007421  mov     rcx, gs:60h
0x14000742a  xor     edx, edx; Flags
0x14000742c  mov     rcx, [rcx+30h]; HeapHandle
0x140007430  call    cs:__imp_RtlFreeHeap
0x140007436  mov     eax, ebx
0x140007438  add     rsp, 78h
0x14000743c  pop     rdi
0x14000743d  pop     rsi
0x14000743e  pop     rbx
0x14000743f  pop     rbp
0x140007440  retn
```
