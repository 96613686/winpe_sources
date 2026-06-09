# KSRCachepGetPackageFullNameFromPackageDataId

- ea: `0x18008a518`
- end: `0x18008a6e7`
- name: `KSRCachepGetPackageFullNameFromPackageDataId`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180089b88`

## callees

- `0x18002bf20`
- `0x18002c080`
- `0x18008a518`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18008a644`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a644`
- `ntoskrnl!ZwClose` at `0x18008a6a0`
- `ntoskrnl!ZwClose` at `0x18008a6b6`
- `ntoskrnl!ZwClose` at `0x18008a6a0`
- `ntoskrnl!ZwClose` at `0x18008a6b6`
- `ntoskrnl!ZwOpenKey` at `0x18008a5bf`
- `ntoskrnl!ZwOpenKey` at `0x18008a60a`
- `ntoskrnl!ZwOpenKey` at `0x18008a5bf`
- `ntoskrnl!ZwOpenKey` at `0x18008a60a`

## string_xrefs

- `0x18008a55d`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Data`

## pseudocode

```c
__int64 __fastcall KSRCachepGetPackageFullNameFromPackageDataId(struct _UNICODE_STRING *a1, __int64 a2)
{
  NTSTATUS v4; // ebx
  ULONG Length; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v9[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v13; // [rsp+A4h] [rbp-5Ch]
  unsigned int v14; // [rsp+A8h] [rbp-58h]
  _BYTE Src[260]; // [rsp+ACh] [rbp-54h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  Handle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v9[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache\\Package\\Data";
  v9[0] = 13631694;
  ValueName.Buffer = L"PackageFullName";
  *(_QWORD *)&ValueName.Length = 2097182;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v9;
  Length = 272;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.ObjectName = a1;
    v4 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
    if ( v4 >= 0 )
    {
      v4 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, Length, &Length);
      if ( v4 >= 0 )
      {
        if ( v13 == 1 && v14 >= 2 )
        {
          if ( *(unsigned __int16 *)(a2 + 2) >= v14 )
          {
            memmove(*(void **)(a2 + 8), Src, v14 - 2LL);
            *(_WORD *)a2 = v14 - 2;
          }
          else
          {
            v4 = -1073741789;
          }
        }
        else
        {
          v4 = -1073741788;
        }
      }
    }
  }
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008a518  mov     [rsp-8+arg_10], rbx
0x18008a51d  push    rbp
0x18008a51e  push    rsi
0x18008a51f  push    rdi
0x18008a520  lea     rbp, [rsp-0C0h]
0x18008a528  sub     rsp, 1C0h
0x18008a52f  mov     rax, cs:__security_cookie
0x18008a536  xor     rax, rsp
0x18008a539  mov     [rbp+0D0h+var_20], rax
0x18008a540  xor     eax, eax
0x18008a542  mov     qword ptr [rsp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x18008a54b  mov     [rsp+1D0h+KeyHandle], rax
0x18008a550  lea     r8, [rsp+1D0h+ObjectAttributes]; ObjectAttributes
0x18008a555  mov     [rsp+1D0h+Handle], rax
0x18008a55a  mov     rdi, rdx
0x18008a55d  lea     rax, aRegistryMachin_23; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008a564  mov     qword ptr [rbp+0D0h+ObjectAttributes.Attributes], 240h
0x18008a56c  mov     [rsp+1D0h+var_180], rax
0x18008a571  mov     rsi, rcx
0x18008a574  lea     rax, aPackagefullnam; "PackageFullName"
0x18008a57b  mov     [rsp+1D0h+var_188], 0D000CEh
0x18008a584  mov     [rsp+1D0h+ValueName.Buffer], rax
0x18008a589  lea     rcx, [rsp+1D0h+KeyHandle]; KeyHandle
0x18008a58e  lea     rax, [rsp+1D0h+var_188]
0x18008a593  mov     qword ptr [rsp+1D0h+ValueName.Length], 20001Eh
0x18008a59c  xorps   xmm0, xmm0
0x18008a59f  mov     [rsp+1D0h+ObjectAttributes.ObjectName], rax
0x18008a5a4  mov     edx, 20019h; DesiredAccess
0x18008a5a9  mov     [rsp+1D0h+var_1A0], 110h
0x18008a5b1  mov     [rsp+1D0h+ObjectAttributes.RootDirectory], 0
0x18008a5ba  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a5bf  call    cs:__imp_ZwOpenKey
0x18008a5c6  nop     dword ptr [rax+rax+00h]
0x18008a5cb  mov     ebx, eax
0x18008a5cd  test    eax, eax
0x18008a5cf  js      loc_18008A696
0x18008a5d5  mov     rax, [rsp+1D0h+KeyHandle]
0x18008a5da  lea     r8, [rsp+1D0h+ObjectAttributes]; ObjectAttributes
0x18008a5df  xorps   xmm0, xmm0
0x18008a5e2  mov     [rsp+1D0h+ObjectAttributes.RootDirectory], rax
0x18008a5e7  mov     edx, 20019h; DesiredAccess
0x18008a5ec  mov     [rsp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x18008a5f4  lea     rcx, [rsp+1D0h+Handle]; KeyHandle
0x18008a5f9  mov     [rbp+0D0h+ObjectAttributes.Attributes], 240h
0x18008a600  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a605  mov     [rsp+1D0h+ObjectAttributes.ObjectName], rsi
0x18008a60a  call    cs:__imp_ZwOpenKey
0x18008a611  nop     dword ptr [rax+rax+00h]
0x18008a616  mov     ebx, eax
0x18008a618  test    eax, eax
0x18008a61a  js      short loc_18008A696
0x18008a61c  mov     rcx, [rsp+1D0h+Handle]; KeyHandle
0x18008a621  lea     rax, [rsp+1D0h+var_1A0]
0x18008a626  mov     [rsp+1D0h+ResultLength], rax; ResultLength
0x18008a62b  lea     r9, [rbp+0D0h+KeyValueInformation]; KeyValueInformation
0x18008a62f  mov     eax, [rsp+1D0h+var_1A0]
0x18008a633  lea     rdx, [rsp+1D0h+ValueName]; ValueName
0x18008a638  mov     esi, 2
0x18008a63d  mov     [rsp+1D0h+Length], eax; Length
0x18008a641  mov     r8d, esi; KeyValueInformationClass
0x18008a644  call    cs:__imp_ZwQueryValueKey
0x18008a64b  nop     dword ptr [rax+rax+00h]
0x18008a650  mov     ebx, eax
0x18008a652  test    eax, eax
0x18008a654  js      short loc_18008A696
0x18008a656  cmp     [rbp+0D0h+var_12C], 1
0x18008a65a  jnz     short loc_18008A691
0x18008a65c  mov     ecx, [rbp+0D0h+var_128]
0x18008a65f  cmp     ecx, esi
0x18008a661  jb      short loc_18008A691
0x18008a663  movzx   eax, word ptr [rdi+2]
0x18008a667  cmp     eax, ecx
0x18008a669  jnb     short loc_18008A672
0x18008a66b  mov     ebx, 0C0000023h
0x18008a670  jmp     short loc_18008A696
0x18008a672  mov     r8, rcx
0x18008a675  lea     rdx, [rbp+0D0h+Src]; Src
0x18008a679  mov     rcx, [rdi+8]; void *
0x18008a67d  sub     r8, rsi; Size
0x18008a680  call    memmove
0x18008a685  movzx   eax, word ptr [rbp+0D0h+var_128]
0x18008a689  sub     ax, si
0x18008a68c  mov     [rdi], ax
0x18008a68f  jmp     short loc_18008A696
0x18008a691  mov     ebx, 0C0000024h
0x18008a696  mov     rcx, [rsp+1D0h+Handle]; Handle
0x18008a69b  test    rcx, rcx
0x18008a69e  jz      short loc_18008A6AC
0x18008a6a0  call    cs:__imp_ZwClose
0x18008a6a7  nop     dword ptr [rax+rax+00h]
0x18008a6ac  mov     rcx, [rsp+1D0h+KeyHandle]; Handle
0x18008a6b1  test    rcx, rcx
0x18008a6b4  jz      short loc_18008A6C2
0x18008a6b6  call    cs:__imp_ZwClose
0x18008a6bd  nop     dword ptr [rax+rax+00h]
0x18008a6c2  mov     eax, ebx
0x18008a6c4  mov     rcx, [rbp+0D0h+var_20]
0x18008a6cb  xor     rcx, rsp; StackCookie
0x18008a6ce  call    __security_check_cookie
0x18008a6d3  mov     rbx, [rsp+1D0h+arg_10]
0x18008a6db  add     rsp, 1C0h
0x18008a6e2  pop     rdi
0x18008a6e3  pop     rsi
0x18008a6e4  pop     rbp
0x18008a6e5  retn
```
