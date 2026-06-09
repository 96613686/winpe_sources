# FveGetRegistryValue

- ea: `0x140097060`
- end: `0x1400971e2`
- name: `FveGetRegistryValue`
- size: `386`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400516f4`
- `0x14005edf8`
- `0x1400626c8`
- `0x140079638`
- `0x14008ab24`
- `0x14008b7fc`
- `0x14008d7f0`
- `0x140099944`
- `0x1400aca3c`

## callees

- `0x140021a00`
- `0x140097060`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400970af`
- `ntoskrnl!ZwOpenKey` at `0x1400970af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400971c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400971c0`
- `ntoskrnl!ZwClose` at `0x1400971d1`
- `ntoskrnl!ZwClose` at `0x1400971d1`
- `ntoskrnl!ExAllocatePool2` at `0x14009712c`
- `ntoskrnl!ExAllocatePool2` at `0x14009712c`
- `ntoskrnl!ZwQueryValueKey` at `0x1400970fd`
- `ntoskrnl!ZwQueryValueKey` at `0x14009716a`
- `ntoskrnl!ZwQueryValueKey` at `0x1400970fd`
- `ntoskrnl!ZwQueryValueKey` at `0x14009716a`

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
0x140097060  push    rbp
0x140097062  push    rbx
0x140097063  push    rsi
0x140097064  push    rdi
0x140097065  push    r14
0x140097067  push    r15
0x140097069  mov     rbp, rsp
0x14009706c  sub     rsp, 78h
0x140097070  xor     eax, eax
0x140097072  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140097076  mov     r14d, r8d
0x140097079  mov     [rbp+arg_0], eax
0x14009707c  mov     r15, rdx
0x14009707f  mov     [rbp+KeyHandle], rax
0x140097083  xorps   xmm0, xmm0
0x140097086  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14009708a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14009708e  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140097096  mov     edx, 20019h; DesiredAccess
0x14009709b  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400970a3  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400970a7  mov     rsi, r9
0x1400970aa  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400970af  call    cs:__imp_ZwOpenKey
0x1400970b6  nop     dword ptr [rax+rax+00h]
0x1400970bb  mov     ebx, eax
0x1400970bd  test    eax, eax
0x1400970bf  jns     short loc_1400970DE
0x1400970c1  mov     rcx, [rbp+KeyHandle]; Handle
0x1400970c5  test    rcx, rcx
0x1400970c8  jnz     loc_1400971D1
0x1400970ce  mov     eax, ebx
0x1400970d0  add     rsp, 78h
0x1400970d4  pop     r15
0x1400970d6  pop     r14
0x1400970d8  pop     rdi
0x1400970d9  pop     rsi
0x1400970da  pop     rbx
0x1400970db  pop     rbp
0x1400970dc  retn
0x1400970de  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400970e2  lea     rax, [rbp+arg_0]
0x1400970e6  xor     r9d, r9d; KeyValueInformation
0x1400970e9  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1400970ee  mov     rdx, r15; ValueName
0x1400970f1  mov     [rsp+78h+Length], 0; Length
0x1400970f9  lea     r8d, [r9+2]; KeyValueInformationClass
0x1400970fd  call    cs:__imp_ZwQueryValueKey
0x140097104  nop     dword ptr [rax+rax+00h]
0x140097109  mov     ecx, 80000000h
0x14009710e  mov     ebx, eax
0x140097110  add     eax, ecx
0x140097112  test    ecx, eax
0x140097114  jnz     short loc_14009711E
0x140097116  cmp     ebx, 0C0000023h
0x14009711c  jnz     short loc_1400970C1
0x14009711e  mov     edx, [rbp+arg_0]
0x140097121  mov     ecx, 100h
0x140097126  mov     r8d, 30455646h
0x14009712c  call    cs:__imp_ExAllocatePool2
0x140097133  nop     dword ptr [rax+rax+00h]
0x140097138  mov     rdi, rax
0x14009713b  test    rax, rax
0x14009713e  jnz     short loc_14009714A
0x140097140  mov     ebx, 0C000009Ah
0x140097145  jmp     loc_1400970C1
0x14009714a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14009714e  lea     rax, [rbp+arg_0]
0x140097152  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140097157  mov     r9, rdi; KeyValueInformation
0x14009715a  mov     eax, [rbp+arg_0]
0x14009715d  mov     r8d, 2; KeyValueInformationClass
0x140097163  mov     rdx, r15; ValueName
0x140097166  mov     [rsp+78h+Length], eax; Length
0x14009716a  call    cs:__imp_ZwQueryValueKey
0x140097171  nop     dword ptr [rax+rax+00h]
0x140097176  mov     ebx, eax
0x140097178  test    eax, eax
0x14009717a  js      short loc_1400971B8
0x14009717c  cmp     [rdi+4], r14d
0x140097180  jz      short loc_140097189
0x140097182  mov     ebx, 0C0000024h
0x140097187  jmp     short loc_1400971B8
0x140097189  mov     rcx, [rbp+arg_20]
0x14009718d  test    rsi, rsi
0x140097190  jz      short loc_1400971AE
0x140097192  mov     eax, [rdi+8]
0x140097195  cmp     [rcx], eax
0x140097197  jb      short loc_1400971AE
0x140097199  mov     [rcx], eax
0x14009719b  lea     rdx, [rdi+0Ch]; Src
0x14009719f  mov     rcx, rsi; void *
0x1400971a2  mov     r8d, eax; Size
0x1400971a5  call    memmove
0x1400971aa  xor     ebx, ebx
0x1400971ac  jmp     short loc_1400971B8
0x1400971ae  mov     eax, [rdi+8]
0x1400971b1  mov     ebx, 0C0000023h
0x1400971b6  mov     [rcx], eax
0x1400971b8  mov     edx, 30455646h; Tag
0x1400971bd  mov     rcx, rdi; P
0x1400971c0  call    cs:__imp_ExFreePoolWithTag
0x1400971c7  nop     dword ptr [rax+rax+00h]
0x1400971cc  jmp     loc_1400970C1
0x1400971d1  call    cs:__imp_ZwClose
0x1400971d8  nop     dword ptr [rax+rax+00h]
0x1400971dd  jmp     loc_1400970CE
```
