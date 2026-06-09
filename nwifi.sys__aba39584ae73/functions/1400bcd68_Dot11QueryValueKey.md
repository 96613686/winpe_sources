# Dot11QueryValueKey

- ea: `0x1400bcd68`
- end: `0x1400bcee1`
- name: `Dot11QueryValueKey`
- size: `377`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400bcee8`
- `0x1400bcfa4`

## callees

- `0x1400bcd68`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400bcd93`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bcd93`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400bcdf5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400bcdf5`
- `ntoskrnl!ExAllocatePool2` at `0x1400bce10`
- `ntoskrnl!ExAllocatePool2` at `0x1400bce10`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bce7f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bce7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bce93`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bce93`
- `ntoskrnl!ZwQueryValueKey` at `0x1400bce62`
- `ntoskrnl!ZwQueryValueKey` at `0x1400bce62`

## pseudocode

```c
__int64 __fastcall Dot11QueryValueKey(HANDLE KeyHandle, const WCHAR *a2, _QWORD *a3)
{
  ULONG v5; // eax
  void *v6; // rsi
  unsigned int v7; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  PNPAGED_LOOKASIDE_LIST *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v10; // rbx
  unsigned int v11; // edi
  __int64 result; // rax
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-28h] BYREF
  ULONG Length; // [rsp+70h] [rbp+18h] BYREF

  Length = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v5 = 240;
  Length = 240;
  while ( 1 )
  {
    v6 = 0;
    v7 = v5 + 16;
    if ( v7 < 0x10 )
      break;
    if ( v7 > 0x40 )
    {
      if ( v7 > 0x100 )
      {
        if ( v7 > 0x400 )
        {
          if ( v7 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (PNPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, v7, 1701409655);
            goto LABEL_13;
          }
          p_WaitListHead = &stru_1400B31C0;
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
    v10 = Pool2;
    if ( !Pool2 )
      break;
    v6 = Pool2 + 2;
    *Pool2 = p_WaitListHead;
    *((_DWORD *)Pool2 + 2) = 1701409655;
    if ( Pool2 == (PNPAGED_LOOKASIDE_LIST *)-16LL )
      break;
    v11 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, v6, Length, &Length);
    if ( v11 )
    {
      if ( *v10 )
        ExFreeToNPagedLookasideList(*v10, v10);
      else
        ExFreePoolWithTag(v10, *((_DWORD *)v10 + 2));
      v5 = Length;
      v6 = 0;
      if ( Length )
      {
        if ( v11 == -1073741789 || v11 == -2147483643 )
          continue;
      }
    }
    goto LABEL_24;
  }
  v11 = -1073741670;
LABEL_24:
  result = v11;
  *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x1400bcd68  mov     rax, rsp
0x1400bcd6b  mov     [rax+8], rbx
0x1400bcd6f  mov     [rax+10h], rbp
0x1400bcd73  push    rsi
0x1400bcd74  push    rdi
0x1400bcd75  push    r14
0x1400bcd77  sub     rsp, 40h
0x1400bcd7b  mov     rbp, rcx
0x1400bcd7e  mov     dword ptr [rax+18h], 0
0x1400bcd85  xorps   xmm0, xmm0
0x1400bcd88  lea     rcx, [rax-28h]; DestinationString
0x1400bcd8c  movups  xmmword ptr [rax-28h], xmm0
0x1400bcd90  mov     r14, r8
0x1400bcd93  call    cs:__imp_RtlInitUnicodeString
0x1400bcd9a  nop     dword ptr [rax+rax+00h]
0x1400bcd9f  mov     eax, 0F0h
0x1400bcda4  mov     [rsp+58h+arg_10], eax
0x1400bcda8  xor     esi, esi
0x1400bcdaa  add     eax, 10h
0x1400bcdad  cmp     eax, 10h
0x1400bcdb0  jb      loc_1400BCEC3
0x1400bcdb6  cmp     eax, 40h ; '@'
0x1400bcdb9  ja      short loc_1400BCDC4
0x1400bcdbb  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400bcdc2  jmp     short loc_1400BCDF2
0x1400bcdc4  cmp     eax, 100h
0x1400bcdc9  ja      short loc_1400BCDD4
0x1400bcdcb  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400bcdd2  jmp     short loc_1400BCDF2
0x1400bcdd4  cmp     eax, 400h
0x1400bcdd9  ja      short loc_1400BCDE4
0x1400bcddb  lea     rdi, Lookaside
0x1400bcde2  jmp     short loc_1400BCDF2
0x1400bcde4  cmp     eax, 800h
0x1400bcde9  ja      short loc_1400BCE03
0x1400bcdeb  lea     rdi, stru_1400B31C0
0x1400bcdf2  mov     rcx, rdi; Lookaside
0x1400bcdf5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400bcdfc  nop     dword ptr [rax+rax+00h]
0x1400bce01  jmp     short loc_1400BCE1C
0x1400bce03  xor     edi, edi
0x1400bce05  mov     edx, eax
0x1400bce07  mov     r8d, 65697377h
0x1400bce0d  lea     ecx, [rdi+40h]
0x1400bce10  call    cs:__imp_ExAllocatePool2
0x1400bce17  nop     dword ptr [rax+rax+00h]
0x1400bce1c  mov     rbx, rax
0x1400bce1f  test    rax, rax
0x1400bce22  jz      loc_1400BCEC3
0x1400bce28  lea     rsi, [rax+10h]
0x1400bce2c  mov     [rax], rdi
0x1400bce2f  mov     dword ptr [rax+8], 65697377h
0x1400bce36  test    rsi, rsi
0x1400bce39  jz      loc_1400BCEC3
0x1400bce3f  mov     eax, [rsp+58h+arg_10]
0x1400bce43  lea     rcx, [rsp+58h+arg_10]
0x1400bce48  mov     [rsp+58h+ResultLength], rcx; ResultLength
0x1400bce4d  lea     rdx, [rsp+58h+ValueName]; ValueName
0x1400bce52  mov     rcx, rbp; KeyHandle
0x1400bce55  mov     [rsp+58h+Length], eax; Length
0x1400bce59  mov     r9, rsi; KeyValueInformation
0x1400bce5c  mov     r8d, 1; KeyValueInformationClass
0x1400bce62  call    cs:__imp_ZwQueryValueKey
0x1400bce69  nop     dword ptr [rax+rax+00h]
0x1400bce6e  mov     edi, eax
0x1400bce70  test    eax, eax
0x1400bce72  jz      short loc_1400BCEC8
0x1400bce74  mov     rcx, [rbx]; Lookaside
0x1400bce77  test    rcx, rcx
0x1400bce7a  jz      short loc_1400BCE8D
0x1400bce7c  mov     rdx, rbx; Entry
0x1400bce7f  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400bce86  nop     dword ptr [rax+rax+00h]
0x1400bce8b  jmp     short loc_1400BCE9F
0x1400bce8d  mov     edx, [rbx+8]; Tag
0x1400bce90  mov     rcx, rbx; P
0x1400bce93  call    cs:__imp_ExFreePoolWithTag
0x1400bce9a  nop     dword ptr [rax+rax+00h]
0x1400bce9f  mov     eax, [rsp+58h+arg_10]
0x1400bcea3  xor     esi, esi
0x1400bcea5  test    eax, eax
0x1400bcea7  jz      short loc_1400BCEC8
0x1400bcea9  cmp     edi, 0C0000023h
0x1400bceaf  jz      loc_1400BCDA8
0x1400bceb5  cmp     edi, 80000005h
0x1400bcebb  jz      loc_1400BCDA8
0x1400bcec1  jmp     short loc_1400BCEC8
0x1400bcec3  mov     edi, 0C000009Ah
0x1400bcec8  mov     rbx, [rsp+58h+arg_0]
0x1400bcecd  mov     eax, edi
0x1400bcecf  mov     rbp, [rsp+58h+arg_8]
0x1400bced4  mov     [r14], rsi
0x1400bced7  add     rsp, 40h
0x1400bcedb  pop     r14
0x1400bcedd  pop     rdi
0x1400bcede  pop     rsi
0x1400bcedf  retn
```
