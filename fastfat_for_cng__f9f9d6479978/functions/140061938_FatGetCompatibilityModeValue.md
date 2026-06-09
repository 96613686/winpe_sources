# FatGetCompatibilityModeValue

- ea: `0x140061938`
- end: `0x140061aff`
- name: `FatGetCompatibilityModeValue`
- size: `455`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140061078`

## callees

- `0x14000c230`
- `0x14000c680`
- `0x140061938`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400619be`
- `ntoskrnl!ZwOpenKey` at `0x1400619be`
- `ntoskrnl!ZwQueryValueKey` at `0x140061a63`
- `ntoskrnl!ZwQueryValueKey` at `0x140061a63`
- `ntoskrnl!ZwClose` at `0x140061a81`
- `ntoskrnl!ZwClose` at `0x140061aa7`
- `ntoskrnl!ZwClose` at `0x140061a81`
- `ntoskrnl!ZwClose` at `0x140061aa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400619ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061acd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400619ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061acd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140061a10`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140061a10`

## string_xrefs

- `0x14006195e`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`

## pseudocode

```c
NTSTATUS __fastcall FatGetCompatibilityModeValue(PUNICODE_STRING ValueName, _DWORD *a2)
{
  NTSTATUS result; // eax
  ULONG Length; // esi
  unsigned int *v6; // rbx
  _BYTE *i; // r9
  _BYTE *PoolWithTag; // rax
  _BYTE *v9; // rdi
  NTSTATUS v10; // edi
  ULONG ResultLength; // [rsp+30h] [rbp-89h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v13[2]; // [rsp+40h] [rbp-79h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-69h] BYREF
  _BYTE P[96]; // [rsp+80h] [rbp-39h] BYREF

  KeyHandle = 0;
  v13[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
  ResultLength = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v13;
  v13[0] = 8126586;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    Length = 92;
    v6 = (unsigned int *)P;
    for ( i = P; ; i = v9 )
    {
      v10 = ZwQueryValueKey(KeyHandle, ValueName, KeyValueFullInformation, i, Length, &ResultLength);
      if ( v10 != -2147483643 )
        break;
      if ( v6 != (unsigned int *)P )
        ExFreePoolWithTag(v6, 0);
      Length += 256;
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, Length, 0x20746146u);
      v9 = PoolWithTag;
      if ( ExPoolZeroingNativelySupported )
      {
        if ( !PoolWithTag )
        {
LABEL_14:
          ZwClose(KeyHandle);
          return -1073741801;
        }
      }
      else
      {
        if ( !PoolWithTag )
          goto LABEL_14;
        memset(PoolWithTag, 0, Length);
      }
      v6 = (unsigned int *)v9;
    }
    ZwClose(KeyHandle);
    if ( v10 >= 0 )
    {
      if ( v6[3] )
        *a2 = *(unsigned int *)((char *)v6 + v6[2]);
      else
        v10 = -1073741772;
    }
    if ( v6 != (unsigned int *)P )
      ExFreePoolWithTag(v6, 0);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x140061938  mov     [rsp-8+arg_10], rbx
0x14006193d  push    rbp
0x14006193e  push    rsi
0x14006193f  push    rdi
0x140061940  push    r14
0x140061942  push    r15
0x140061944  lea     rbp, [rsp-37h]
0x140061949  sub     rsp, 0F0h
0x140061950  mov     rax, cs:__security_cookie
0x140061957  xor     rax, rsp
0x14006195a  mov     [rbp+57h+var_30], rax
0x14006195e  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x140061965  mov     [rsp+110h+KeyHandle], 0
0x14006196e  mov     [rbp+57h+var_C8], rax
0x140061972  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140061976  lea     rax, [rbp+57h+var_D0]
0x14006197a  mov     [rsp+110h+var_E0], 0
0x140061982  mov     r15, rdx
0x140061985  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140061989  mov     r14, rcx
0x14006198c  mov     [rbp+57h+var_D0], 7C007Ah
0x140061994  xorps   xmm0, xmm0
0x140061997  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14006199f  mov     edx, 20019h; DesiredAccess
0x1400619a4  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1400619ac  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1400619b1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400619b9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400619be  call    cs:__imp_ZwOpenKey
0x1400619c5  nop     dword ptr [rax+rax+00h]
0x1400619ca  test    eax, eax
0x1400619cc  js      loc_140061ADB
0x1400619d2  mov     esi, 5Ch ; '\'
0x1400619d7  lea     rbx, [rbp+57h+P]
0x1400619db  lea     r9, [rbp+57h+P]
0x1400619df  jmp     short loc_140061A47
0x1400619e1  lea     rax, [rbp+57h+P]
0x1400619e5  cmp     rbx, rax
0x1400619e8  jz      short loc_1400619FB
0x1400619ea  xor     edx, edx; Tag
0x1400619ec  mov     rcx, rbx; P
0x1400619ef  call    cs:__imp_ExFreePoolWithTag
0x1400619f6  nop     dword ptr [rax+rax+00h]
0x1400619fb  add     esi, 100h
0x140061a01  mov     r8d, 20746146h; Tag
0x140061a07  mov     edx, esi; NumberOfBytes
0x140061a09  mov     ecx, 401h; PoolType
0x140061a0e  mov     ebx, esi
0x140061a10  call    cs:__imp_ExAllocatePoolWithTag
0x140061a17  nop     dword ptr [rax+rax+00h]
0x140061a1c  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140061a23  mov     rdi, rax
0x140061a26  jnz     short loc_140061A3C
0x140061a28  test    rax, rax
0x140061a2b  jz      short loc_140061AA2
0x140061a2d  mov     r8d, ebx; Size
0x140061a30  xor     edx, edx; Val
0x140061a32  mov     rcx, rax; void *
0x140061a35  call    memset
0x140061a3a  jmp     short loc_140061A41
0x140061a3c  test    rdi, rdi
0x140061a3f  jz      short loc_140061AA2
0x140061a41  mov     rbx, rdi
0x140061a44  mov     r9, rdi; KeyValueInformation
0x140061a47  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x140061a4c  lea     rax, [rsp+110h+var_E0]
0x140061a51  mov     [rsp+110h+ResultLength], rax; ResultLength
0x140061a56  mov     r8d, 1; KeyValueInformationClass
0x140061a5c  mov     rdx, r14; ValueName
0x140061a5f  mov     [rsp+110h+Length], esi; Length
0x140061a63  call    cs:__imp_ZwQueryValueKey
0x140061a6a  nop     dword ptr [rax+rax+00h]
0x140061a6f  mov     edi, eax
0x140061a71  cmp     eax, 80000005h
0x140061a76  jz      loc_1400619E1
0x140061a7c  mov     rcx, [rsp+110h+KeyHandle]; Handle
0x140061a81  call    cs:__imp_ZwClose
0x140061a88  nop     dword ptr [rax+rax+00h]
0x140061a8d  test    edi, edi
0x140061a8f  js      short loc_140061ABF
0x140061a91  cmp     dword ptr [rbx+0Ch], 0
0x140061a95  jz      short loc_140061ABA
0x140061a97  mov     eax, [rbx+8]
0x140061a9a  mov     ecx, [rax+rbx]
0x140061a9d  mov     [r15], ecx
0x140061aa0  jmp     short loc_140061ABF
0x140061aa2  mov     rcx, [rsp+110h+KeyHandle]; Handle
0x140061aa7  call    cs:__imp_ZwClose
0x140061aae  nop     dword ptr [rax+rax+00h]
0x140061ab3  mov     eax, 0C0000017h
0x140061ab8  jmp     short loc_140061ADB
0x140061aba  mov     edi, 0C0000034h
0x140061abf  lea     rax, [rbp+57h+P]
0x140061ac3  cmp     rbx, rax
0x140061ac6  jz      short loc_140061AD9
0x140061ac8  xor     edx, edx; Tag
0x140061aca  mov     rcx, rbx; P
0x140061acd  call    cs:__imp_ExFreePoolWithTag
0x140061ad4  nop     dword ptr [rax+rax+00h]
0x140061ad9  mov     eax, edi
0x140061adb  mov     rcx, [rbp+57h+var_30]
0x140061adf  xor     rcx, rsp; StackCookie
0x140061ae2  call    __security_check_cookie
0x140061ae7  mov     rbx, [rsp+110h+arg_10]
0x140061aef  add     rsp, 0F0h
0x140061af6  pop     r15
0x140061af8  pop     r14
0x140061afa  pop     rdi
0x140061afb  pop     rsi
0x140061afc  pop     rbp
0x140061afd  retn
```
