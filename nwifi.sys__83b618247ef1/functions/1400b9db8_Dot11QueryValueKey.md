# Dot11QueryValueKey

- ea: `0x1400b9db8`
- end: `0x1400b9f31`
- name: `Dot11QueryValueKey`
- size: `377`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400b9f38`
- `0x1400b9ff4`

## callees

- `0x1400b9db8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400b9de3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b9de3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400b9e45`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400b9e45`
- `ntoskrnl!ExAllocatePool2` at `0x1400b9e60`
- `ntoskrnl!ExAllocatePool2` at `0x1400b9e60`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9ecf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9ecf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9ee3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9ee3`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b9eb2`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b9eb2`

## pseudocode

```c
__int64 __fastcall Dot11QueryValueKey(HANDLE KeyHandle, const WCHAR *a2, _QWORD *a3)
{
  __int64 v5; // r9
  ULONG v6; // eax
  void *v7; // rsi
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  PNPAGED_LOOKASIDE_LIST *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v11; // rbx
  unsigned int v12; // edi
  __int64 result; // rax
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-28h] BYREF
  ULONG Length; // [rsp+70h] [rbp+18h] BYREF

  Length = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v6 = 240;
  Length = 240;
  while ( 1 )
  {
    v7 = 0;
    v8 = v6 + 16;
    if ( v8 < 0x10 )
      break;
    if ( v8 > 0x40 )
    {
      if ( v8 > 0x100 )
      {
        if ( v8 > 0x400 )
        {
          if ( v8 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (PNPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, v8, 1701409655, v5);
            goto LABEL_13;
          }
          p_WaitListHead = &stru_1400B0180;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = (PNPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_13:
    v11 = Pool2;
    if ( !Pool2 )
      break;
    v7 = Pool2 + 2;
    *Pool2 = p_WaitListHead;
    *((_DWORD *)Pool2 + 2) = 1701409655;
    if ( Pool2 == (PNPAGED_LOOKASIDE_LIST *)-16LL )
      break;
    v12 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, v7, Length, &Length);
    if ( v12 )
    {
      if ( *v11 )
        ExFreeToNPagedLookasideList(*v11, v11);
      else
        ExFreePoolWithTag(v11, *((_DWORD *)v11 + 2));
      v6 = Length;
      v7 = 0;
      if ( Length )
      {
        if ( v12 == -1073741789 || v12 == -2147483643 )
          continue;
      }
    }
    goto LABEL_24;
  }
  v12 = -1073741670;
LABEL_24:
  result = v12;
  *a3 = v7;
  return result;
}

```

## disassembly

```asm
0x1400b9db8  mov     rax, rsp
0x1400b9dbb  mov     [rax+8], rbx
0x1400b9dbf  mov     [rax+10h], rbp
0x1400b9dc3  push    rsi
0x1400b9dc4  push    rdi
0x1400b9dc5  push    r14
0x1400b9dc7  sub     rsp, 40h
0x1400b9dcb  mov     rbp, rcx
0x1400b9dce  mov     dword ptr [rax+18h], 0
0x1400b9dd5  xorps   xmm0, xmm0
0x1400b9dd8  lea     rcx, [rax-28h]; DestinationString
0x1400b9ddc  movups  xmmword ptr [rax-28h], xmm0
0x1400b9de0  mov     r14, r8
0x1400b9de3  call    cs:__imp_RtlInitUnicodeString
0x1400b9dea  nop     dword ptr [rax+rax+00h]
0x1400b9def  mov     eax, 0F0h
0x1400b9df4  mov     [rsp+58h+arg_10], eax
0x1400b9df8  xor     esi, esi
0x1400b9dfa  add     eax, 10h
0x1400b9dfd  cmp     eax, 10h
0x1400b9e00  jb      loc_1400B9F13
0x1400b9e06  cmp     eax, 40h ; '@'
0x1400b9e09  ja      short loc_1400B9E14
0x1400b9e0b  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400b9e12  jmp     short loc_1400B9E42
0x1400b9e14  cmp     eax, 100h
0x1400b9e19  ja      short loc_1400B9E24
0x1400b9e1b  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400b9e22  jmp     short loc_1400B9E42
0x1400b9e24  cmp     eax, 400h
0x1400b9e29  ja      short loc_1400B9E34
0x1400b9e2b  lea     rdi, Lookaside
0x1400b9e32  jmp     short loc_1400B9E42
0x1400b9e34  cmp     eax, 800h
0x1400b9e39  ja      short loc_1400B9E53
0x1400b9e3b  lea     rdi, stru_1400B0180
0x1400b9e42  mov     rcx, rdi; Lookaside
0x1400b9e45  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400b9e4c  nop     dword ptr [rax+rax+00h]
0x1400b9e51  jmp     short loc_1400B9E6C
0x1400b9e53  xor     edi, edi
0x1400b9e55  mov     edx, eax
0x1400b9e57  mov     r8d, 65697377h
0x1400b9e5d  lea     ecx, [rdi+40h]
0x1400b9e60  call    cs:__imp_ExAllocatePool2
0x1400b9e67  nop     dword ptr [rax+rax+00h]
0x1400b9e6c  mov     rbx, rax
0x1400b9e6f  test    rax, rax
0x1400b9e72  jz      loc_1400B9F13
0x1400b9e78  lea     rsi, [rax+10h]
0x1400b9e7c  mov     [rax], rdi
0x1400b9e7f  mov     dword ptr [rax+8], 65697377h
0x1400b9e86  test    rsi, rsi
0x1400b9e89  jz      loc_1400B9F13
0x1400b9e8f  mov     eax, [rsp+58h+arg_10]
0x1400b9e93  lea     rcx, [rsp+58h+arg_10]
0x1400b9e98  mov     [rsp+58h+ResultLength], rcx; ResultLength
0x1400b9e9d  lea     rdx, [rsp+58h+ValueName]; ValueName
0x1400b9ea2  mov     rcx, rbp; KeyHandle
0x1400b9ea5  mov     [rsp+58h+Length], eax; Length
0x1400b9ea9  mov     r9, rsi; KeyValueInformation
0x1400b9eac  mov     r8d, 1; KeyValueInformationClass
0x1400b9eb2  call    cs:__imp_ZwQueryValueKey
0x1400b9eb9  nop     dword ptr [rax+rax+00h]
0x1400b9ebe  mov     edi, eax
0x1400b9ec0  test    eax, eax
0x1400b9ec2  jz      short loc_1400B9F18
0x1400b9ec4  mov     rcx, [rbx]; Lookaside
0x1400b9ec7  test    rcx, rcx
0x1400b9eca  jz      short loc_1400B9EDD
0x1400b9ecc  mov     rdx, rbx; Entry
0x1400b9ecf  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b9ed6  nop     dword ptr [rax+rax+00h]
0x1400b9edb  jmp     short loc_1400B9EEF
0x1400b9edd  mov     edx, [rbx+8]; Tag
0x1400b9ee0  mov     rcx, rbx; P
0x1400b9ee3  call    cs:__imp_ExFreePoolWithTag
0x1400b9eea  nop     dword ptr [rax+rax+00h]
0x1400b9eef  mov     eax, [rsp+58h+arg_10]
0x1400b9ef3  xor     esi, esi
0x1400b9ef5  test    eax, eax
0x1400b9ef7  jz      short loc_1400B9F18
0x1400b9ef9  cmp     edi, 0C0000023h
0x1400b9eff  jz      loc_1400B9DF8
0x1400b9f05  cmp     edi, 80000005h
0x1400b9f0b  jz      loc_1400B9DF8
0x1400b9f11  jmp     short loc_1400B9F18
0x1400b9f13  mov     edi, 0C000009Ah
0x1400b9f18  mov     rbx, [rsp+58h+arg_0]
0x1400b9f1d  mov     eax, edi
0x1400b9f1f  mov     rbp, [rsp+58h+arg_8]
0x1400b9f24  mov     [r14], rsi
0x1400b9f27  add     rsp, 40h
0x1400b9f2b  pop     r14
0x1400b9f2d  pop     rdi
0x1400b9f2e  pop     rsi
0x1400b9f2f  retn
```
