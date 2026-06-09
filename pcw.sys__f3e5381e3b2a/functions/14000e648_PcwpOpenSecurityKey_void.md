# PcwpOpenSecurityKey(void)

- ea: `0x14000e648`
- end: `0x14000e6ef`
- name: `?PcwpOpenSecurityKey@@YAJXZ`
- size: `167`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ddf4`
- `0x14000e6f8`
- `0x14000e8c0`

## callees

- `0x14000e648`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14000e6b5`
- `ntoskrnl!ZwOpenKey` at `0x14000e6b5`
- `ntoskrnl!ZwClose` at `0x14000e6da`
- `ntoskrnl!ZwClose` at `0x14000e6da`

## string_xrefs

- `0x14000e651`: `\Registry\Machine\System\CurrentControlSet\Control\PCW\Security`

## pseudocode

```c
NTSTATUS PcwpOpenSecurityKey(void)
{
  NTSTATUS result; // eax
  _QWORD v1[2]; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  KeyHandle = 0;
  v1[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\PCW\\Security";
  v1[0] = 8388734;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( !PcwSecurityKey )
  {
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v1;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
    if ( result < 0 )
      return result;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&PcwSecurityKey, (signed __int64)KeyHandle, 0) )
      ZwClose(KeyHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x14000e648  push    rbp
0x14000e64a  mov     rbp, rsp
0x14000e64d  sub     rsp, 60h
0x14000e651  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000e658  mov     [rbp+KeyHandle], 0
0x14000e660  mov     [rbp+var_38], rax
0x14000e664  mov     rax, cs:?PcwSecurityKey@@3PEAXEA; void * PcwSecurityKey
0x14000e66b  mov     [rbp+var_40], 80007Eh
0x14000e673  mov     dword ptr [rbp+ObjectAttributes+4], 0
0x14000e67a  mov     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x14000e681  test    rax, rax
0x14000e684  jnz     short loc_14000E6E6
0x14000e686  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14000e68a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000e68e  lea     rax, [rbp+var_40]
0x14000e692  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000e699  xorps   xmm0, xmm0
0x14000e69c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000e6a0  mov     edx, 2001Fh; DesiredAccess
0x14000e6a5  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14000e6ac  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e6b0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e6b5  call    cs:__imp_ZwOpenKey
0x14000e6bc  nop     dword ptr [rax+rax+00h]
0x14000e6c1  test    eax, eax
0x14000e6c3  js      short loc_14000E6E8
0x14000e6c5  mov     rcx, [rbp+KeyHandle]
0x14000e6c9  xor     eax, eax
0x14000e6cb  lock cmpxchg cs:?PcwSecurityKey@@3PEAXEA, rcx; void * PcwSecurityKey
0x14000e6d4  jz      short loc_14000E6E6
0x14000e6d6  mov     rcx, [rbp+KeyHandle]; Handle
0x14000e6da  call    cs:__imp_ZwClose
0x14000e6e1  nop     dword ptr [rax+rax+00h]
0x14000e6e6  xor     eax, eax
0x14000e6e8  add     rsp, 60h
0x14000e6ec  pop     rbp
0x14000e6ed  retn
```
