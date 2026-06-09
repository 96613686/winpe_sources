# ReadElement

- ea: `0x1400491a0`
- end: `0x1400493bb`
- name: `ReadElement`
- size: `539`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, PUNICODE_STRING ValueName)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140048db4`
- `0x14004902c`
- `0x1400493c4`

## callees

- `0x140030f40`
- `0x140031140`
- `0x140031440`
- `0x1400400a4`
- `0x1400491a0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400491ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004929a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400491ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004929a`
- `ntoskrnl!ZwQueryValueKey` at `0x140049217`
- `ntoskrnl!ZwQueryValueKey` at `0x140049361`
- `ntoskrnl!ZwQueryValueKey` at `0x140049217`
- `ntoskrnl!ZwQueryValueKey` at `0x140049361`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400493aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400493aa`
- `ntoskrnl!ExAllocatePool2` at `0x14004926a`
- `ntoskrnl!ExAllocatePool2` at `0x1400492f8`
- `ntoskrnl!ExAllocatePool2` at `0x14004926a`
- `ntoskrnl!ExAllocatePool2` at `0x1400492f8`

## pseudocode

```c
__int64 __fastcall ReadElement(HANDLE KeyHandle, PCWSTR SourceString, PUNICODE_STRING ValueName)
{
  NTSTATUS ValueKey; // ebx
  _DWORD *v7; // rdi
  unsigned int v8; // ecx
  WCHAR *v9; // rax
  const WCHAR *v10; // rsi
  _DWORD *Pool2; // rax
  ULONG ResultLength[4]; // [rsp+30h] [rbp-298h] BYREF
  _BYTE KeyValueInformation[608]; // [rsp+40h] [rbp-288h] BYREF

  memset(KeyValueInformation, 0, 0x258u);
  ResultLength[0] = 0;
  RtlInitUnicodeString(ValueName, SourceString);
  ValueKey = ZwQueryValueKey(KeyHandle, ValueName, KeyValueFullInformation, KeyValueInformation, 0x258u, ResultLength);
  if ( ValueKey == -2147483643 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(64, ResultLength[0], 892559950);
    v7 = Pool2;
    if ( !Pool2 )
    {
      if ( (xmmword_140038420 & 8) != 0 )
        WPP_SF_d(1027, 25, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, ResultLength[0]);
      goto LABEL_16;
    }
    ValueKey = ZwQueryValueKey(KeyHandle, ValueName, KeyValueFullInformation, Pool2, ResultLength[0], ResultLength);
  }
  else
  {
    v7 = KeyValueInformation;
  }
  if ( ValueKey >= 0 )
  {
    if ( !ResultLength[0] )
    {
      ValueKey = -1073741472;
      goto LABEL_11;
    }
    v8 = v7[3];
    if ( !v8 || (unsigned int)(v7[1] - 1) > 1 )
    {
      ValueKey = -1073741823;
      goto LABEL_11;
    }
    v9 = (WCHAR *)ExAllocatePool2(64, v8, 909337166);
    v10 = v9;
    if ( v9 )
    {
      memmove(v9, (char *)v7 + (unsigned int)v7[2], (unsigned int)v7[3]);
      RtlInitUnicodeString(ValueName, v10);
      goto LABEL_11;
    }
LABEL_16:
    ValueKey = -1073741670;
    goto LABEL_11;
  }
  if ( (xmmword_140038420 & 8) != 0 )
    WPP_SF_d(1027, 26, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, (unsigned int)ValueKey);
LABEL_11:
  if ( v7 != (_DWORD *)KeyValueInformation && v7 )
    ExFreePoolWithTag(v7, 0);
  return (unsigned int)ValueKey;
}

```

## disassembly

```asm
0x1400491a0  mov     [rsp+arg_18], rbx
0x1400491a5  push    rbp
0x1400491a6  push    rsi
0x1400491a7  push    rdi
0x1400491a8  sub     rsp, 2B0h
0x1400491af  mov     rax, cs:__security_cookie
0x1400491b6  xor     rax, rsp
0x1400491b9  mov     [rsp+2C8h+var_28], rax
0x1400491c1  mov     rbp, r8
0x1400491c4  mov     rbx, rdx
0x1400491c7  mov     rsi, rcx
0x1400491ca  mov     edi, 258h
0x1400491cf  mov     r8d, edi; Size
0x1400491d2  lea     rcx, [rsp+2C8h+KeyValueInformation]; void *
0x1400491d7  xor     edx, edx; Val
0x1400491d9  call    memset
0x1400491de  mov     rdx, rbx; SourceString
0x1400491e1  mov     [rsp+2C8h+var_298], 0
0x1400491e9  mov     rcx, rbp; DestinationString
0x1400491ec  call    cs:__imp_RtlInitUnicodeString
0x1400491f3  nop     dword ptr [rax+rax+00h]
0x1400491f8  lea     rax, [rsp+2C8h+var_298]
0x1400491fd  mov     r8d, 1; KeyValueInformationClass
0x140049203  mov     [rsp+2C8h+ResultLength], rax; ResultLength
0x140049208  lea     r9, [rsp+2C8h+KeyValueInformation]; KeyValueInformation
0x14004920d  mov     rdx, rbp; ValueName
0x140049210  mov     [rsp+2C8h+Length], edi; Length
0x140049214  mov     rcx, rsi; KeyHandle
0x140049217  call    cs:__imp_ZwQueryValueKey
0x14004921e  nop     dword ptr [rax+rax+00h]
0x140049223  mov     ebx, eax
0x140049225  cmp     eax, 80000005h
0x14004922a  jz      loc_1400492E9
0x140049230  lea     rdi, [rsp+2C8h+KeyValueInformation]
0x140049235  test    ebx, ebx
0x140049237  js      short loc_1400492A8
0x140049239  cmp     [rsp+2C8h+var_298], 0
0x14004923e  jz      loc_14004931C
0x140049244  mov     ecx, [rdi+0Ch]
0x140049247  test    ecx, ecx
0x140049249  jz      loc_140049392
0x14004924f  mov     eax, [rdi+4]
0x140049252  dec     eax
0x140049254  cmp     eax, 1
0x140049257  ja      loc_140049392
0x14004925d  mov     edx, ecx
0x14004925f  mov     r8d, 3633624Eh
0x140049265  mov     ecx, 40h ; '@'
0x14004926a  call    cs:__imp_ExAllocatePool2
0x140049271  nop     dword ptr [rax+rax+00h]
0x140049276  mov     rsi, rax
0x140049279  test    rax, rax
0x14004927c  jz      loc_140049315
0x140049282  mov     edx, [rdi+8]
0x140049285  mov     rcx, rax; void *
0x140049288  mov     r8d, [rdi+0Ch]; Size
0x14004928c  add     rdx, rdi; Src
0x14004928f  call    memmove
0x140049294  mov     rdx, rsi; SourceString
0x140049297  mov     rcx, rbp; DestinationString
0x14004929a  call    cs:__imp_RtlInitUnicodeString
0x1400492a1  nop     dword ptr [rax+rax+00h]
0x1400492a6  jmp     short loc_1400492B5
0x1400492a8  test    byte ptr cs:xmmword_140038420, 8
0x1400492af  jnz     loc_140049374
0x1400492b5  lea     rax, [rsp+2C8h+KeyValueInformation]
0x1400492ba  cmp     rdi, rax
0x1400492bd  jnz     loc_14004939C
0x1400492c3  mov     eax, ebx
0x1400492c5  mov     rcx, [rsp+2C8h+var_28]
0x1400492cd  xor     rcx, rsp; StackCookie
0x1400492d0  call    __security_check_cookie
0x1400492d5  mov     rbx, [rsp+2C8h+arg_18]
0x1400492dd  add     rsp, 2B0h
0x1400492e4  pop     rdi
0x1400492e5  pop     rsi
0x1400492e6  pop     rbp
0x1400492e7  retn
0x1400492e9  mov     edx, [rsp+2C8h+var_298]
0x1400492ed  mov     ecx, 40h ; '@'
0x1400492f2  mov     r8d, 3533624Eh
0x1400492f8  call    cs:__imp_ExAllocatePool2
0x1400492ff  nop     dword ptr [rax+rax+00h]
0x140049304  mov     rdi, rax
0x140049307  test    rax, rax
0x14004930a  jnz     short loc_140049340
0x14004930c  test    byte ptr cs:xmmword_140038420, 8
0x140049313  jnz     short loc_140049323
0x140049315  mov     ebx, 0C000009Ah
0x14004931a  jmp     short loc_1400492B5
0x14004931c  mov     ebx, 0C0000160h
0x140049321  jmp     short loc_1400492B5
0x140049323  mov     r9d, [rsp+2C8h+var_298]
0x140049328  lea     r8, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids
0x14004932f  mov     edx, 19h
0x140049334  mov     ecx, 403h
0x140049339  call    WPP_SF_d
0x14004933e  jmp     short loc_140049315
0x140049340  lea     rax, [rsp+2C8h+var_298]
0x140049345  mov     r9, rdi; KeyValueInformation
0x140049348  mov     [rsp+2C8h+ResultLength], rax; ResultLength
0x14004934d  mov     r8d, 1; KeyValueInformationClass
0x140049353  mov     eax, [rsp+2C8h+var_298]
0x140049357  mov     rdx, rbp; ValueName
0x14004935a  mov     rcx, rsi; KeyHandle
0x14004935d  mov     [rsp+2C8h+Length], eax; Length
0x140049361  call    cs:__imp_ZwQueryValueKey
0x140049368  nop     dword ptr [rax+rax+00h]
0x14004936d  mov     ebx, eax
0x14004936f  jmp     loc_140049235
0x140049374  mov     edx, 1Ah
0x140049379  lea     r8, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids
0x140049380  mov     ecx, 403h
0x140049385  mov     r9d, ebx
0x140049388  call    WPP_SF_d
0x14004938d  jmp     loc_1400492B5
0x140049392  mov     ebx, 0C0000001h
0x140049397  jmp     loc_1400492B5
0x14004939c  test    rdi, rdi
0x14004939f  jz      loc_1400492C3
0x1400493a5  xor     edx, edx; Tag
0x1400493a7  mov     rcx, rdi; P
0x1400493aa  call    cs:__imp_ExFreePoolWithTag
0x1400493b1  nop     dword ptr [rax+rax+00h]
0x1400493b6  jmp     loc_1400492C3
```
