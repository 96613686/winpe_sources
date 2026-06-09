# SecQueryBootRegistryKey

- ea: `0x14002a450`
- end: `0x14002a5de`
- name: `SecQueryBootRegistryKey`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140029fc8`

## callees

- `0x140009b80`
- `0x140011610`
- `0x140011650`
- `0x14002a450`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14002a4b5`
- `ntoskrnl!ZwOpenKey` at `0x14002a4b5`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a4ea`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a573`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a4ea`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a573`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a538`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a538`
- `ntoskrnl!ZwClose` at `0x14002a5b5`
- `ntoskrnl!ZwClose` at `0x14002a5b5`

## pseudocode

```c
__int64 __fastcall SecQueryBootRegistryKey(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, _QWORD *a3)
{
  NTSTATUS v5; // ebx
  NTSTATUS v6; // eax
  char *PoolWithTag; // rax
  char *v8; // rdi
  ULONG ResultLength; // [rsp+30h] [rbp-50h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-40h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v5 >= 0 )
  {
    v6 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    v5 = v6;
    if ( v6 == -1073741789 )
    {
      if ( qword_140020008 )
        PoolWithTag = (char *)qword_140020008(256, ResultLength, 1765958483);
      else
        PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, ResultLength, 0x69426353u);
      v8 = PoolWithTag;
      if ( PoolWithTag )
      {
        v5 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, PoolWithTag, ResultLength, &ResultLength);
        if ( v5 >= 0 )
        {
          if ( *((_DWORD *)v8 + 1) == 11 && *((_DWORD *)v8 + 2) == 8 )
            *a3 = *(_QWORD *)(v8 + 12);
          else
            v5 = -1073741788;
        }
        SecFreePool(v8, 0x69426353u);
      }
      else
      {
        v5 = -1073741670;
      }
    }
    else if ( v6 >= 0 )
    {
      v5 = -1073741595;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002a450  push    rbp
0x14002a452  push    rbx
0x14002a453  push    rsi
0x14002a454  push    rdi
0x14002a455  push    r14
0x14002a457  mov     rbp, rsp
0x14002a45a  sub     rsp, 80h
0x14002a461  mov     rax, cs:__security_cookie
0x14002a468  xor     rax, rsp
0x14002a46b  mov     [rbp+var_10], rax
0x14002a46f  mov     r14, r8
0x14002a472  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x14002a476  mov     rsi, rdx
0x14002a479  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002a481  xorps   xmm0, xmm0
0x14002a484  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14002a48c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002a490  mov     [rbp+KeyHandle], 0
0x14002a498  mov     edx, 20019h; DesiredAccess
0x14002a49d  mov     [rbp+var_50], 0
0x14002a4a4  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14002a4a8  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002a4b0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002a4b5  call    cs:__imp_ZwOpenKey
0x14002a4bc  nop     dword ptr [rax+rax+00h]
0x14002a4c1  mov     ebx, eax
0x14002a4c3  test    eax, eax
0x14002a4c5  js      loc_14002A5AC
0x14002a4cb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002a4cf  lea     rax, [rbp+var_50]
0x14002a4d3  xor     r9d, r9d; KeyValueInformation
0x14002a4d6  mov     [rsp+80h+ResultLength], rax; ResultLength
0x14002a4db  mov     rdx, rsi; ValueName
0x14002a4de  mov     [rsp+80h+Length], 0; Length
0x14002a4e6  lea     r8d, [r9+2]; KeyValueInformationClass
0x14002a4ea  call    cs:__imp_ZwQueryValueKey
0x14002a4f1  nop     dword ptr [rax+rax+00h]
0x14002a4f6  mov     ebx, eax
0x14002a4f8  cmp     eax, 0C0000023h
0x14002a4fd  jz      short loc_14002A511
0x14002a4ff  test    eax, eax
0x14002a501  js      loc_14002A5AC
0x14002a507  mov     ebx, 0C00000E5h
0x14002a50c  jmp     loc_14002A5AC
0x14002a511  mov     rax, cs:qword_140020008
0x14002a518  mov     r8d, 69426353h; Tag
0x14002a51e  mov     edx, [rbp+var_50]; NumberOfBytes
0x14002a521  test    rax, rax
0x14002a524  jz      short loc_14002A533
0x14002a526  mov     ecx, 100h
0x14002a52b  call    cs:__guard_dispatch_icall_fptr
0x14002a531  jmp     short loc_14002A544
0x14002a533  mov     ecx, 1; PoolType
0x14002a538  call    cs:__imp_ExAllocatePoolWithTag
0x14002a53f  nop     dword ptr [rax+rax+00h]
0x14002a544  mov     rdi, rax
0x14002a547  test    rax, rax
0x14002a54a  jnz     short loc_14002A553
0x14002a54c  mov     ebx, 0C000009Ah
0x14002a551  jmp     short loc_14002A5AC
0x14002a553  mov     eax, [rbp+var_50]
0x14002a556  lea     rcx, [rbp+var_50]
0x14002a55a  mov     [rsp+80h+ResultLength], rcx; ResultLength
0x14002a55f  mov     r9, rdi; KeyValueInformation
0x14002a562  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002a566  mov     r8d, 2; KeyValueInformationClass
0x14002a56c  mov     rdx, rsi; ValueName
0x14002a56f  mov     [rsp+80h+Length], eax; Length
0x14002a573  call    cs:__imp_ZwQueryValueKey
0x14002a57a  nop     dword ptr [rax+rax+00h]
0x14002a57f  mov     ebx, eax
0x14002a581  test    eax, eax
0x14002a583  js      short loc_14002A59F
0x14002a585  cmp     dword ptr [rdi+4], 0Bh
0x14002a589  jz      short loc_14002A592
0x14002a58b  mov     ebx, 0C0000024h
0x14002a590  jmp     short loc_14002A59F
0x14002a592  cmp     dword ptr [rdi+8], 8
0x14002a596  jnz     short loc_14002A58B
0x14002a598  mov     rax, [rdi+0Ch]
0x14002a59c  mov     [r14], rax
0x14002a59f  mov     edx, 69426353h; Tag
0x14002a5a4  mov     rcx, rdi; P
0x14002a5a7  call    SecFreePool
0x14002a5ac  mov     rcx, [rbp+KeyHandle]; Handle
0x14002a5b0  test    rcx, rcx
0x14002a5b3  jz      short loc_14002A5C1
0x14002a5b5  call    cs:__imp_ZwClose
0x14002a5bc  nop     dword ptr [rax+rax+00h]
0x14002a5c1  mov     eax, ebx
0x14002a5c3  mov     rcx, [rbp+var_10]
0x14002a5c7  xor     rcx, rsp; StackCookie
0x14002a5ca  call    __security_check_cookie
0x14002a5cf  add     rsp, 80h
0x14002a5d6  pop     r14
0x14002a5d8  pop     rdi
0x14002a5d9  pop     rsi
0x14002a5da  pop     rbx
0x14002a5db  pop     rbp
0x14002a5dc  retn
```
