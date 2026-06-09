# FveGetRegistryValue

- ea: `0x140099114`
- end: `0x140099296`
- name: `FveGetRegistryValue`
- size: `386`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400536f4`
- `0x140060e78`
- `0x140064748`
- `0x14007b668`
- `0x14008cbc4`
- `0x14008d89c`
- `0x14008f8a0`
- `0x14009b9f4`
- `0x1400adcbc`

## callees

- `0x140022d40`
- `0x140099114`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140099163`
- `ntoskrnl!ZwOpenKey` at `0x140099163`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099274`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099274`
- `ntoskrnl!ZwClose` at `0x140099285`
- `ntoskrnl!ZwClose` at `0x140099285`
- `ntoskrnl!ExAllocatePool2` at `0x1400991e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400991e0`
- `ntoskrnl!ZwQueryValueKey` at `0x1400991b1`
- `ntoskrnl!ZwQueryValueKey` at `0x14009921e`
- `ntoskrnl!ZwQueryValueKey` at `0x1400991b1`
- `ntoskrnl!ZwQueryValueKey` at `0x14009921e`

## pseudocode

```c
__int64 __fastcall FveGetRegistryValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        void *a4,
        unsigned int *a5)
{
  NTSTATUS v8; // ebx
  _DWORD *Pool2; // rax
  _DWORD *v11; // rdi
  unsigned int v12; // eax
  void *KeyHandle; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+38h] BYREF

  ObjectAttributes.ObjectName = a1;
  ResultLength = 0;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    v8 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength, 809850438);
      v11 = Pool2;
      if ( Pool2 )
      {
        v8 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, Pool2, ResultLength, &ResultLength);
        if ( v8 >= 0 )
        {
          if ( v11[1] == a3 )
          {
            if ( a4 && (v12 = v11[2], *a5 >= v12) )
            {
              *a5 = v12;
              memmove(a4, v11 + 3, v12);
              v8 = 0;
            }
            else
            {
              v8 = -1073741789;
              *a5 = v11[2];
            }
          }
          else
          {
            v8 = -1073741788;
          }
        }
        ExFreePoolWithTag(v11, 0x30455646u);
      }
      else
      {
        v8 = -1073741670;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140099114  push    rbp
0x140099116  push    rbx
0x140099117  push    rsi
0x140099118  push    rdi
0x140099119  push    r14
0x14009911b  push    r15
0x14009911d  mov     rbp, rsp
0x140099120  sub     rsp, 78h
0x140099124  xor     eax, eax
0x140099126  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x14009912a  mov     r14d, r8d
0x14009912d  mov     [rbp+arg_0], eax
0x140099130  mov     r15, rdx
0x140099133  mov     [rbp+KeyHandle], rax
0x140099137  xorps   xmm0, xmm0
0x14009913a  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14009913e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140099142  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14009914a  mov     edx, 20019h; DesiredAccess
0x14009914f  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140099157  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14009915b  mov     rsi, r9
0x14009915e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140099163  call    cs:__imp_ZwOpenKey
0x14009916a  nop     dword ptr [rax+rax+00h]
0x14009916f  mov     ebx, eax
0x140099171  test    eax, eax
0x140099173  jns     short loc_140099192
0x140099175  mov     rcx, [rbp+KeyHandle]; Handle
0x140099179  test    rcx, rcx
0x14009917c  jnz     loc_140099285
0x140099182  mov     eax, ebx
0x140099184  add     rsp, 78h
0x140099188  pop     r15
0x14009918a  pop     r14
0x14009918c  pop     rdi
0x14009918d  pop     rsi
0x14009918e  pop     rbx
0x14009918f  pop     rbp
0x140099190  retn
0x140099192  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140099196  lea     rax, [rbp+arg_0]
0x14009919a  xor     r9d, r9d; KeyValueInformation
0x14009919d  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1400991a2  mov     rdx, r15; ValueName
0x1400991a5  mov     [rsp+78h+Length], 0; Length
0x1400991ad  lea     r8d, [r9+2]; KeyValueInformationClass
0x1400991b1  call    cs:__imp_ZwQueryValueKey
0x1400991b8  nop     dword ptr [rax+rax+00h]
0x1400991bd  mov     ecx, 80000000h
0x1400991c2  mov     ebx, eax
0x1400991c4  add     eax, ecx
0x1400991c6  test    ecx, eax
0x1400991c8  jnz     short loc_1400991D2
0x1400991ca  cmp     ebx, 0C0000023h
0x1400991d0  jnz     short loc_140099175
0x1400991d2  mov     edx, [rbp+arg_0]
0x1400991d5  mov     ecx, 100h
0x1400991da  mov     r8d, 30455646h
0x1400991e0  call    cs:__imp_ExAllocatePool2
0x1400991e7  nop     dword ptr [rax+rax+00h]
0x1400991ec  mov     rdi, rax
0x1400991ef  test    rax, rax
0x1400991f2  jnz     short loc_1400991FE
0x1400991f4  mov     ebx, 0C000009Ah
0x1400991f9  jmp     loc_140099175
0x1400991fe  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140099202  lea     rax, [rbp+arg_0]
0x140099206  mov     [rsp+78h+ResultLength], rax; ResultLength
0x14009920b  mov     r9, rdi; KeyValueInformation
0x14009920e  mov     eax, [rbp+arg_0]
0x140099211  mov     r8d, 2; KeyValueInformationClass
0x140099217  mov     rdx, r15; ValueName
0x14009921a  mov     [rsp+78h+Length], eax; Length
0x14009921e  call    cs:__imp_ZwQueryValueKey
0x140099225  nop     dword ptr [rax+rax+00h]
0x14009922a  mov     ebx, eax
0x14009922c  test    eax, eax
0x14009922e  js      short loc_14009926C
0x140099230  cmp     [rdi+4], r14d
0x140099234  jz      short loc_14009923D
0x140099236  mov     ebx, 0C0000024h
0x14009923b  jmp     short loc_14009926C
0x14009923d  mov     rcx, [rbp+arg_20]
0x140099241  test    rsi, rsi
0x140099244  jz      short loc_140099262
0x140099246  mov     eax, [rdi+8]
0x140099249  cmp     [rcx], eax
0x14009924b  jb      short loc_140099262
0x14009924d  mov     [rcx], eax
0x14009924f  lea     rdx, [rdi+0Ch]; Src
0x140099253  mov     rcx, rsi; void *
0x140099256  mov     r8d, eax; Size
0x140099259  call    memmove
0x14009925e  xor     ebx, ebx
0x140099260  jmp     short loc_14009926C
0x140099262  mov     eax, [rdi+8]
0x140099265  mov     ebx, 0C0000023h
0x14009926a  mov     [rcx], eax
0x14009926c  mov     edx, 30455646h; Tag
0x140099271  mov     rcx, rdi; P
0x140099274  call    cs:__imp_ExFreePoolWithTag
0x14009927b  nop     dword ptr [rax+rax+00h]
0x140099280  jmp     loc_140099175
0x140099285  call    cs:__imp_ZwClose
0x14009928c  nop     dword ptr [rax+rax+00h]
0x140099291  jmp     loc_140099182
```
