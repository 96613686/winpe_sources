# CxPlatStorageReadValue

- ea: `0x140033e30`
- end: `0x140033fdb`
- name: `CxPlatStorageReadValue`
- size: `427`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140024810`
- `0x140028728`
- `0x140028b3c`

## callees

- `0x14003383c`
- `0x140033e30`
- `0x14003cb00`
- `0x14003e928`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140033f91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033faf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033faf`
- `ntoskrnl!ZwQueryValueKey` at `0x140033e96`
- `ntoskrnl!ZwQueryValueKey` at `0x140033f40`
- `ntoskrnl!ZwQueryValueKey` at `0x140033e96`
- `ntoskrnl!ZwQueryValueKey` at `0x140033f40`
- `ntoskrnl!ExAllocatePool2` at `0x140033eff`
- `ntoskrnl!ExAllocatePool2` at `0x140033eff`

## pseudocode

```c
__int64 __fastcall CxPlatStorageReadValue(HANDLE *a1, const CHAR *a2, void *a3, _DWORD *a4)
{
  __int64 result; // rax
  HANDLE v8; // rcx
  NTSTATUS v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // ebx
  unsigned int *Pool2; // rax
  unsigned int *v14; // rdi
  NTSTATUS v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  ULONG ResultLength; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
  {
    result = CxPlatConvertUtf8ToUnicode(a2);
    if ( (int)result < 0 )
      return result;
    if ( a3 )
    {
      ResultLength = *a4 + 12;
      Pool2 = (unsigned int *)ExAllocatePool2(258, ResultLength, 942826321);
      v14 = Pool2;
      if ( Pool2 )
      {
        v15 = ZwQueryValueKey(*a1, 0, KeyValuePartialInformation, Pool2, ResultLength, &ResultLength);
        v12 = v15;
        if ( v15 < 0 )
        {
          if ( v15 != -1073741772 && (Microsoft_QuicEnableBits & 4) != 0 )
            McTemplateU0qs_EtwWriteTransfer(v17, v16, (unsigned int)v15, "ZwQueryValueKey failed");
        }
        else
        {
          memmove(a3, v14 + 3, v14[2]);
          *a4 = v14[2];
        }
        ExFreePoolWithTag(v14, 0x38326351u);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
      return v12;
    }
    v8 = *a1;
    ResultLength = 0;
    v9 = ZwQueryValueKey(v8, 0, KeyValuePartialInformation, 0, 0, &ResultLength);
    v12 = v9;
    if ( v9 == -2147483643 || v9 == -1073741789 )
    {
      v12 = 0;
    }
    else if ( v9 < 0 )
    {
      if ( (Microsoft_QuicEnableBits & 4) != 0 )
        McTemplateU0qs_EtwWriteTransfer(v11, v10, (unsigned int)v9, "ZwQueryValueKey (length) failed");
      return v12;
    }
    *a4 = ResultLength - 12;
    return v12;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140033e30  mov     rax, rsp
0x140033e33  mov     [rax+8], rbx
0x140033e37  mov     [rax+18h], rbp
0x140033e3b  mov     [rax+20h], rdi
0x140033e3f  push    r14
0x140033e41  sub     rsp, 40h
0x140033e45  and     qword ptr [rax-18h], 0
0x140033e4a  mov     r14, r9
0x140033e4d  mov     rbp, r8
0x140033e50  mov     rbx, rcx
0x140033e53  test    rdx, rdx
0x140033e56  jz      loc_140033FBF
0x140033e5c  lea     r8, [rax-18h]
0x140033e60  mov     rcx, rdx; UTF8StringSource
0x140033e63  call    CxPlatConvertUtf8ToUnicode
0x140033e68  test    eax, eax
0x140033e6a  js      loc_140033FC4
0x140033e70  test    rbp, rbp
0x140033e73  jnz     short loc_140033EE8
0x140033e75  mov     rdx, [rsp+48h+ValueName]; ValueName
0x140033e7a  lea     rax, [rsp+48h+arg_8]
0x140033e7f  mov     rcx, [rbx]; KeyHandle
0x140033e82  lea     r8d, [rbp+2]; KeyValueInformationClass
0x140033e86  and     [rsp+48h+arg_8], ebp
0x140033e8a  xor     r9d, r9d; KeyValueInformation
0x140033e8d  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140033e92  and     [rsp+48h+Length], ebp
0x140033e96  call    cs:__imp_ZwQueryValueKey
0x140033e9d  nop     dword ptr [rax+rax+00h]
0x140033ea2  mov     ebx, eax
0x140033ea4  cmp     eax, 80000005h
0x140033ea9  jz      short loc_140033ED7
0x140033eab  cmp     eax, 0C0000023h
0x140033eb0  jz      short loc_140033ED7
0x140033eb2  test    eax, eax
0x140033eb4  jns     short loc_140033ED9
0x140033eb6  test    cs:Microsoft_QuicEnableBits, 4
0x140033ebd  jz      loc_140033F9D
0x140033ec3  lea     r9, aZwqueryvalueke; "ZwQueryValueKey (length) failed"
0x140033eca  mov     r8d, eax
0x140033ecd  call    McTemplateU0qs_EtwWriteTransfer
0x140033ed2  jmp     loc_140033F9D
0x140033ed7  xor     ebx, ebx
0x140033ed9  mov     eax, [rsp+48h+arg_8]
0x140033edd  add     eax, 0FFFFFFF4h
0x140033ee0  mov     [r14], eax
0x140033ee3  jmp     loc_140033F9D
0x140033ee8  mov     eax, [r14]
0x140033eeb  mov     ecx, 102h
0x140033ef0  add     eax, 0Ch
0x140033ef3  mov     r8d, 38326351h
0x140033ef9  mov     edx, eax
0x140033efb  mov     [rsp+48h+arg_8], eax
0x140033eff  call    cs:__imp_ExAllocatePool2
0x140033f06  nop     dword ptr [rax+rax+00h]
0x140033f0b  mov     rdi, rax
0x140033f0e  test    rax, rax
0x140033f11  jnz     short loc_140033F1D
0x140033f13  mov     ebx, 0C0000017h
0x140033f18  jmp     loc_140033F9D
0x140033f1d  mov     rdx, [rsp+48h+ValueName]; ValueName
0x140033f22  lea     rax, [rsp+48h+arg_8]
0x140033f27  mov     rcx, [rbx]; KeyHandle
0x140033f2a  mov     r9, rdi; KeyValueInformation
0x140033f2d  mov     [rsp+48h+ResultLength], rax; ResultLength
0x140033f32  mov     r8d, 2; KeyValueInformationClass
0x140033f38  mov     eax, [rsp+48h+arg_8]
0x140033f3c  mov     [rsp+48h+Length], eax; Length
0x140033f40  call    cs:__imp_ZwQueryValueKey
0x140033f47  nop     dword ptr [rax+rax+00h]
0x140033f4c  mov     ebx, eax
0x140033f4e  test    eax, eax
0x140033f50  js      short loc_140033F6A
0x140033f52  mov     r8d, [rdi+8]; Size
0x140033f56  lea     rdx, [rdi+0Ch]; Src
0x140033f5a  mov     rcx, rbp; void *
0x140033f5d  call    memmove
0x140033f62  mov     eax, [rdi+8]
0x140033f65  mov     [r14], eax
0x140033f68  jmp     short loc_140033F89
0x140033f6a  cmp     eax, 0C0000034h
0x140033f6f  jz      short loc_140033F89
0x140033f71  test    cs:Microsoft_QuicEnableBits, 4
0x140033f78  jz      short loc_140033F89
0x140033f7a  lea     r9, aZwqueryvalueke_0; "ZwQueryValueKey failed"
0x140033f81  mov     r8d, eax
0x140033f84  call    McTemplateU0qs_EtwWriteTransfer
0x140033f89  mov     edx, 38326351h; Tag
0x140033f8e  mov     rcx, rdi; P
0x140033f91  call    cs:__imp_ExFreePoolWithTag
0x140033f98  nop     dword ptr [rax+rax+00h]
0x140033f9d  cmp     [rsp+48h+ValueName], 0
0x140033fa3  jz      short loc_140033FBB
0x140033fa5  mov     rcx, [rsp+48h+ValueName]; P
0x140033faa  mov     edx, 38326351h; Tag
0x140033faf  call    cs:__imp_ExFreePoolWithTag
0x140033fb6  nop     dword ptr [rax+rax+00h]
0x140033fbb  mov     eax, ebx
0x140033fbd  jmp     short loc_140033FC4
0x140033fbf  mov     eax, 0C000000Dh
0x140033fc4  mov     rbx, [rsp+48h+arg_0]
0x140033fc9  mov     rbp, [rsp+48h+arg_10]
0x140033fce  mov     rdi, [rsp+48h+arg_18]
0x140033fd3  add     rsp, 40h
0x140033fd7  pop     r14
0x140033fd9  retn
```
