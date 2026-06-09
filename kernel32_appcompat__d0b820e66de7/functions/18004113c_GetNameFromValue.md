# GetNameFromValue

- ea: `0x18004113c`
- end: `0x1800412eb`
- name: `GetNameFromValue`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18003c870`

## callees

- `0x18004113c`
- `0x180082751`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18004122d`
- `ntdll!NtQueryValueKey` at `0x18004122d`
- `ntdll!NtOpenKey` at `0x1800411dd`
- `ntdll!NtOpenKey` at `0x1800411dd`
- `ntdll!NtClose` at `0x180041240`
- `ntdll!NtClose` at `0x180041240`
- `ntdll!wcslen` at `0x1800412aa`
- `ntdll!wcslen` at `0x1800412aa`
- `ntdll!RtlInitUnicodeString` at `0x18004119a`
- `ntdll!RtlInitUnicodeString` at `0x1800411fe`
- `ntdll!RtlInitUnicodeString` at `0x18004119a`
- `ntdll!RtlInitUnicodeString` at `0x1800411fe`

## string_xrefs

- `0x1800411f3`: `ComputerName`

## pseudocode

```c
__int64 __fastcall GetNameFromValue(void *a1, const WCHAR *a2, char *a3, int *a4)
{
  NTSTATUS v7; // edi
  unsigned int v8; // ecx
  unsigned int v9; // eax
  __int64 v10; // rbx
  int v11; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE KeyValueInformation[8]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v19; // [rsp+98h] [rbp-68h]
  unsigned int v20; // [rsp+9Ch] [rbp-64h]

  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  KeyHandle = 0;
  DestinationString = 0;
  ResultLength = 0;
  ValueName = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  v7 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v7 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"ComputerName");
    v7 = NtQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, KeyValueInformation, 0x6Cu, &ResultLength);
    NtClose(KeyHandle);
    if ( v7 >= 0 )
    {
      if ( v20 < 2 )
      {
        return (unsigned int)-1073741772;
      }
      else
      {
        v8 = v20 & 0xFFFFFFFE;
        v20 &= ~1u;
        v9 = v20 - 2;
        if ( *(_WORD *)((char *)&ValueName.Buffer + v19 + (unsigned __int64)v20 + 6) )
          v9 = v8;
        else
          v20 -= 2;
        v10 = v9;
        if ( (unsigned int)*a4 < ((unsigned __int64)v9 >> 1) + 1 )
        {
          v7 = -2147483643;
          v11 = (v9 >> 1) + 1;
        }
        else
        {
          memcpy_0(a3, &KeyValueInformation[v19], v9);
          *(_WORD *)&a3[v10] = 0;
          v11 = wcslen((const wchar_t *)a3);
        }
        *a4 = v11;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004113c  push    rbp
0x18004113e  push    rbx
0x18004113f  push    rsi
0x180041140  push    rdi
0x180041141  push    r14
0x180041143  push    r15
0x180041145  lea     rbp, [rsp-18h]
0x18004114a  sub     rsp, 118h
0x180041151  mov     rax, cs:__security_cookie
0x180041158  xor     rax, rsp
0x18004115b  mov     [rbp+40h+var_40], rax
0x18004115f  xorps   xmm0, xmm0
0x180041162  mov     rbx, rcx
0x180041165  xorps   xmm1, xmm1
0x180041168  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x18004116d  xor     r15d, r15d
0x180041170  xor     eax, eax
0x180041172  movups  xmmword ptr [rsp+140h+ObjectAttributes.ObjectName], xmm0
0x180041177  mov     r14, r9
0x18004117a  mov     rsi, r8
0x18004117d  movups  xmmword ptr [rsp+140h+ObjectAttributes+1Ch], xmm0
0x180041182  mov     [rsp+140h+KeyHandle], r15
0x180041187  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x18004118c  mov     [rsp+140h+var_110], r15d
0x180041191  movups  xmmword ptr [rbp+40h+ValueName.Length], xmm1
0x180041195  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm0
0x18004119a  call    cs:__imp_RtlInitUnicodeString
0x1800411a1  nop     dword ptr [rax+rax+00h]
0x1800411a6  lea     rax, [rsp+140h+DestinationString]
0x1800411ab  mov     [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x1800411b3  xorps   xmm0, xmm0
0x1800411b6  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x1800411bb  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x1800411c0  mov     [rsp+140h+ObjectAttributes.RootDirectory], rbx
0x1800411c5  mov     edx, 20019h; DesiredAccess
0x1800411ca  mov     [rsp+140h+ObjectAttributes.Attributes], 40h ; '@'
0x1800411d2  lea     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x1800411d7  movdqu  xmmword ptr [rsp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800411dd  call    cs:__imp_NtOpenKey
0x1800411e4  nop     dword ptr [rax+rax+00h]
0x1800411e9  mov     edi, eax
0x1800411eb  test    eax, eax
0x1800411ed  js      loc_1800412B9
0x1800411f3  lea     rdx, aComputername; "ComputerName"
0x1800411fa  lea     rcx, [rbp+40h+ValueName]; DestinationString
0x1800411fe  call    cs:__imp_RtlInitUnicodeString
0x180041205  nop     dword ptr [rax+rax+00h]
0x18004120a  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x18004120f  lea     rax, [rsp+140h+var_110]
0x180041214  mov     [rsp+140h+ResultLength], rax; ResultLength
0x180041219  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x18004121d  lea     r8d, [r15+1]; KeyValueInformationClass
0x180041221  mov     [rsp+140h+Length], 6Ch ; 'l'; Length
0x180041229  lea     rdx, [rbp+40h+ValueName]; ValueName
0x18004122d  call    cs:__imp_NtQueryValueKey
0x180041234  nop     dword ptr [rax+rax+00h]
0x180041239  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x18004123e  mov     edi, eax
0x180041240  call    cs:__imp_NtClose
0x180041247  nop     dword ptr [rax+rax+00h]
0x18004124c  test    edi, edi
0x18004124e  js      short loc_1800412B9
0x180041250  mov     eax, [rbp+40h+var_A4]
0x180041253  cmp     eax, 2
0x180041256  jb      loc_1800412E4
0x18004125c  mov     r8d, [rbp+40h+var_A8]
0x180041260  and     eax, 0FFFFFFFEh
0x180041263  mov     ecx, eax
0x180041265  add     rax, r8
0x180041268  mov     [rbp+40h+var_A4], ecx
0x18004126b  movzx   edx, word ptr [rbp+rax+40h+ValueName.Buffer+6]
0x180041270  lea     eax, [rcx-2]
0x180041273  test    dx, dx
0x180041276  jnz     short loc_18004127B
0x180041278  mov     [rbp+40h+var_A4], eax
0x18004127b  cmovnz  eax, ecx
0x18004127e  mov     edx, eax
0x180041280  shr     rdx, 1
0x180041283  mov     ebx, eax
0x180041285  inc     rdx
0x180041288  mov     eax, [r14]
0x18004128b  cmp     rax, rdx
0x18004128e  jb      short loc_1800412D8
0x180041290  lea     rdx, [rbp+40h+KeyValueInformation]
0x180041294  mov     rcx, rsi; void *
0x180041297  add     rdx, r8; Src
0x18004129a  mov     r8d, ebx; Size
0x18004129d  call    memcpy_0
0x1800412a2  mov     rcx, rsi; String
0x1800412a5  mov     [rbx+rsi], r15w
0x1800412aa  call    cs:__imp_wcslen
0x1800412b1  nop     dword ptr [rax+rax+00h]
0x1800412b6  mov     [r14], eax
0x1800412b9  mov     eax, edi
0x1800412bb  mov     rcx, [rbp+40h+var_40]
0x1800412bf  xor     rcx, rsp; StackCookie
0x1800412c2  call    __security_check_cookie
0x1800412c7  add     rsp, 118h
0x1800412ce  pop     r15
0x1800412d0  pop     r14
0x1800412d2  pop     rdi
0x1800412d3  pop     rsi
0x1800412d4  pop     rbx
0x1800412d5  pop     rbp
0x1800412d6  retn
0x1800412d8  shr     ebx, 1
0x1800412da  mov     edi, 80000005h
0x1800412df  lea     eax, [rbx+1]
0x1800412e2  jmp     short loc_1800412B6
0x1800412e4  mov     edi, 0C0000034h
0x1800412e9  jmp     short loc_1800412B9
```
