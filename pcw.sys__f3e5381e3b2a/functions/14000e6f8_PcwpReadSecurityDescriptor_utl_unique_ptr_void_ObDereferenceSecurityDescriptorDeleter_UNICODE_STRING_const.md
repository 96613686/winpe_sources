# PcwpReadSecurityDescriptor(utl::unique_ptr<void,ObDereferenceSecurityDescriptorDeleter> *,_UNICODE_STRING const *)

- ea: `0x14000e6f8`
- end: `0x14000e8ba`
- name: `?PcwpReadSecurityDescriptor@@YAJPEAV?$unique_ptr@XUObDereferenceSecurityDescriptorDeleter@@@utl@@PEBU_UNICODE_STRING@@@Z`
- size: `450`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e4e8`
- `0x14000ed84`

## callees

- `0x140001370`
- `0x1400014c0`
- `0x1400017c0`
- `0x14000dcf0`
- `0x14000e648`
- `0x14000e6f8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000e76c`
- `ntoskrnl!ExAllocatePool2` at `0x14000e7f9`
- `ntoskrnl!ExAllocatePool2` at `0x14000e76c`
- `ntoskrnl!ExAllocatePool2` at `0x14000e7f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e785`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e867`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e884`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e785`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e867`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e884`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000e854`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x14000e854`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e7be`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e7be`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14000e829`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14000e829`

## pseudocode

```c
__int64 __fastcall PcwpReadSecurityDescriptor(__int64 a1, struct _UNICODE_STRING *a2)
{
  ULONG Length; // ebp
  int v5; // edi
  ULONG v6; // eax
  ULONG *Pool2; // rsi
  ULONG *v8; // rbx
  NTSTATUS ValueKey; // eax
  void *v10; // rax
  void *v11; // rbp
  __int64 v12; // rax
  ULONG ResultLength[4]; // [rsp+30h] [rbp-448h] BYREF
  _BYTE KeyValueInformation[1024]; // [rsp+40h] [rbp-438h] BYREF

  Length = 1024;
  memset(KeyValueInformation, 0, sizeof(KeyValueInformation));
  ResultLength[0] = 0;
  v5 = PcwpOpenSecurityKey();
  if ( v5 >= 0 )
  {
    v6 = 1024;
    Pool2 = (ULONG *)KeyValueInformation;
    ResultLength[0] = 1024;
    v8 = 0;
    while ( 1 )
    {
      if ( v6 > Length )
      {
        Pool2 = (ULONG *)ExAllocatePool2(256, v6, 1417110352);
        if ( v8 )
          ExFreePoolWithTag(v8, 0);
        if ( !Pool2 )
          return (unsigned int)-1073741801;
        Length = ResultLength[0];
        v8 = Pool2;
      }
      ValueKey = ZwQueryValueKey(PcwSecurityKey, a2, KeyValuePartialInformation, Pool2, Length, ResultLength);
      v5 = ValueKey;
      if ( ValueKey != -2147483643 )
        break;
      v6 = ResultLength[0];
    }
    if ( ValueKey >= 0 )
    {
      v10 = (void *)ExAllocatePool2(256, Pool2[2], 1417110352);
      v11 = v10;
      if ( v10 )
      {
        memmove(v10, Pool2 + 3, Pool2[2]);
        if ( RtlValidRelativeSecurityDescriptor(v11, Pool2[2], 3u) )
        {
          v12 = utl::replace<void,ObDereferenceSecurityDescriptorDeleter>(a1);
          v5 = ObLogSecurityDescriptor(v11, v12, 1);
        }
        else
        {
          v5 = -1073741703;
        }
        ExFreePoolWithTag(v11, 0);
      }
      else
      {
        v5 = -1073741801;
      }
    }
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000e6f8  mov     [rsp+arg_10], rbx
0x14000e6fd  push    rbp
0x14000e6fe  push    rsi
0x14000e6ff  push    rdi
0x14000e700  push    r14
0x14000e702  push    r15
0x14000e704  sub     rsp, 450h
0x14000e70b  mov     rax, cs:__security_cookie
0x14000e712  xor     rax, rsp
0x14000e715  mov     [rsp+478h+var_38], rax
0x14000e71d  mov     r14, rdx
0x14000e720  mov     r15, rcx
0x14000e723  mov     ebp, 400h
0x14000e728  lea     rcx, [rsp+478h+KeyValueInformation]; void *
0x14000e72d  mov     r8d, ebp; Size
0x14000e730  xor     edx, edx; Val
0x14000e732  call    memset
0x14000e737  mov     [rsp+478h+var_448], 0
0x14000e73f  call    ?PcwpOpenSecurityKey@@YAJXZ; PcwpOpenSecurityKey(void)
0x14000e744  mov     edi, eax
0x14000e746  test    eax, eax
0x14000e748  js      loc_14000E890
0x14000e74e  mov     eax, ebp
0x14000e750  lea     rsi, [rsp+478h+KeyValueInformation]
0x14000e755  mov     [rsp+478h+var_448], eax
0x14000e759  xor     ebx, ebx
0x14000e75b  cmp     eax, ebp
0x14000e75d  jbe     short loc_14000E79D
0x14000e75f  mov     edx, eax
0x14000e761  mov     ecx, 100h
0x14000e766  mov     r8d, 54776350h
0x14000e76c  call    cs:__imp_ExAllocatePool2
0x14000e773  nop     dword ptr [rax+rax+00h]
0x14000e778  mov     rsi, rax
0x14000e77b  test    rbx, rbx
0x14000e77e  jz      short loc_14000E791
0x14000e780  xor     edx, edx; Tag
0x14000e782  mov     rcx, rbx; P
0x14000e785  call    cs:__imp_ExFreePoolWithTag
0x14000e78c  nop     dword ptr [rax+rax+00h]
0x14000e791  test    rsi, rsi
0x14000e794  jz      short loc_14000E7D9
0x14000e796  mov     ebp, [rsp+478h+var_448]
0x14000e79a  mov     rbx, rsi
0x14000e79d  mov     rcx, cs:?PcwSecurityKey@@3PEAXEA; KeyHandle
0x14000e7a4  lea     rax, [rsp+478h+var_448]
0x14000e7a9  mov     [rsp+478h+ResultLength], rax; ResultLength
0x14000e7ae  mov     r9, rsi; KeyValueInformation
0x14000e7b1  mov     r8d, 2; KeyValueInformationClass
0x14000e7b7  mov     [rsp+478h+Length], ebp; Length
0x14000e7bb  mov     rdx, r14; ValueName
0x14000e7be  call    cs:__imp_ZwQueryValueKey
0x14000e7c5  nop     dword ptr [rax+rax+00h]
0x14000e7ca  mov     edi, eax
0x14000e7cc  cmp     eax, 80000005h
0x14000e7d1  jnz     short loc_14000E7E3
0x14000e7d3  mov     eax, [rsp+478h+var_448]
0x14000e7d7  jmp     short loc_14000E75B
0x14000e7d9  mov     edi, 0C0000017h
0x14000e7de  jmp     loc_14000E890
0x14000e7e3  test    eax, eax
0x14000e7e5  js      loc_14000E87A
0x14000e7eb  mov     edx, [rsi+8]
0x14000e7ee  mov     ecx, 100h
0x14000e7f3  mov     r8d, 54776350h
0x14000e7f9  call    cs:__imp_ExAllocatePool2
0x14000e800  nop     dword ptr [rax+rax+00h]
0x14000e805  mov     rbp, rax
0x14000e808  test    rax, rax
0x14000e80b  jz      short loc_14000E875
0x14000e80d  mov     r8d, [rsi+8]; Size
0x14000e811  lea     rdx, [rsi+0Ch]; Src
0x14000e815  mov     rcx, rax; void *
0x14000e818  call    memmove
0x14000e81d  mov     edx, [rsi+8]; SecurityDescriptorLength
0x14000e820  mov     r8d, 3; RequiredInformation
0x14000e826  mov     rcx, rbp; SecurityDescriptorInput
0x14000e829  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x14000e830  nop     dword ptr [rax+rax+00h]
0x14000e835  test    al, al
0x14000e837  jnz     short loc_14000E840
0x14000e839  mov     edi, 0C0000079h
0x14000e83e  jmp     short loc_14000E862
0x14000e840  mov     rcx, r15
0x14000e843  call    ??$replace@XUObDereferenceSecurityDescriptorDeleter@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XUObDereferenceSecurityDescriptorDeleter@@@0@@Z; utl::replace<void,ObDereferenceSecurityDescriptorDeleter>(utl::unique_ptr<void,ObDereferenceSecurityDescriptorDeleter> &)
0x14000e848  mov     r8d, 1
0x14000e84e  mov     rdx, rax
0x14000e851  mov     rcx, rbp
0x14000e854  call    cs:__imp_ObLogSecurityDescriptor
0x14000e85b  nop     dword ptr [rax+rax+00h]
0x14000e860  mov     edi, eax
0x14000e862  xor     edx, edx; Tag
0x14000e864  mov     rcx, rbp; P
0x14000e867  call    cs:__imp_ExFreePoolWithTag
0x14000e86e  nop     dword ptr [rax+rax+00h]
0x14000e873  jmp     short loc_14000E87A
0x14000e875  mov     edi, 0C0000017h
0x14000e87a  test    rbx, rbx
0x14000e87d  jz      short loc_14000E890
0x14000e87f  xor     edx, edx; Tag
0x14000e881  mov     rcx, rbx; P
0x14000e884  call    cs:__imp_ExFreePoolWithTag
0x14000e88b  nop     dword ptr [rax+rax+00h]
0x14000e890  mov     eax, edi
0x14000e892  mov     rcx, [rsp+478h+var_38]
0x14000e89a  xor     rcx, rsp; StackCookie
0x14000e89d  call    __security_check_cookie
0x14000e8a2  mov     rbx, [rsp+478h+arg_10]
0x14000e8aa  add     rsp, 450h
0x14000e8b1  pop     r15
0x14000e8b3  pop     r14
0x14000e8b5  pop     rdi
0x14000e8b6  pop     rsi
0x14000e8b7  pop     rbp
0x14000e8b8  retn
```
