# TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)

- ea: `0x18001ddf0`
- end: `0x18001df78`
- name: `?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z`
- size: `392`
- prototype: `int(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dbf8`

## callees

- `0x18001ced4`
- `0x18001ddf0`
- `0x1800570b0`
- `0x180059010`

## import_xrefs

- `ntdll!NtClose` at `0x18001df5c`
- `ntdll!NtClose` at `0x18001df5c`
- `ntdll!ZwQueryValueKey` at `0x18001de86`
- `ntdll!ZwQueryValueKey` at `0x18001def7`
- `ntdll!ZwQueryValueKey` at `0x18001de86`
- `ntdll!ZwQueryValueKey` at `0x18001def7`
- `ntdll!ZwOpenKey` at `0x18001de51`
- `ntdll!ZwOpenKey` at `0x18001de51`

## pseudocode

```c
__int64 __fastcall TpmApiRegistryGetValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        void *a4,
        unsigned int *a5)
{
  NTSTATUS v8; // ebx
  _DWORD *v9; // rdi
  unsigned int v10; // eax
  PVOID KeyValueInformation; // [rsp+30h] [rbp-48h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+38h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ResultLength = 0;
  KeyHandle = 0;
  KeyValueInformation = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    v8 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      if ( qword_180072B30 )
        qword_180072B30(0, ResultLength, &KeyValueInformation);
      if ( KeyValueInformation )
      {
        v9 = KeyValueInformation;
        v8 = ZwQueryValueKey(
               KeyHandle,
               a2,
               KeyValuePartialInformation,
               KeyValueInformation,
               ResultLength,
               &ResultLength);
        if ( v8 >= 0 )
        {
          if ( v9[1] == a3 )
          {
            if ( a4 && (v10 = v9[2], *a5 >= v10) )
            {
              *a5 = v10;
              memcpy_0(a4, v9 + 3, v10);
              v8 = 0;
            }
            else
            {
              v8 = -1073741789;
              *a5 = v9[2];
            }
          }
          else
          {
            v8 = -1073741438;
          }
        }
      }
      else
      {
        v8 = -1073741801;
      }
    }
  }
  TpmApiCallbackFree(0, ResultLength);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ddf0  push    rbp
0x18001ddf2  push    rbx
0x18001ddf3  push    rsi
0x18001ddf4  push    rdi
0x18001ddf5  push    r14
0x18001ddf7  push    r15
0x18001ddf9  mov     rbp, rsp
0x18001ddfc  sub     rsp, 78h
0x18001de00  mov     r14d, r8d
0x18001de03  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x18001de07  mov     r15, rdx
0x18001de0a  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001de12  xorps   xmm0, xmm0
0x18001de15  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001de1d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001de21  mov     [rbp+arg_0], 0
0x18001de28  mov     edx, 20019h; DesiredAccess
0x18001de2d  mov     [rbp+KeyHandle], 0
0x18001de35  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18001de39  mov     [rbp+KeyValueInformation], 0
0x18001de41  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001de46  mov     rsi, r9
0x18001de49  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001de51  call    cs:__imp_ZwOpenKey
0x18001de58  nop     dword ptr [rax+rax+00h]
0x18001de5d  mov     ebx, eax
0x18001de5f  test    eax, eax
0x18001de61  js      loc_18001DF45
0x18001de67  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001de6b  lea     rax, [rbp+arg_0]
0x18001de6f  xor     r9d, r9d; KeyValueInformation
0x18001de72  mov     [rsp+78h+ResultLength], rax; ResultLength
0x18001de77  mov     rdx, r15; ValueName
0x18001de7a  mov     [rsp+78h+Length], 0; Length
0x18001de82  lea     r8d, [r9+2]; KeyValueInformationClass
0x18001de86  call    cs:__imp_ZwQueryValueKey
0x18001de8d  nop     dword ptr [rax+rax+00h]
0x18001de92  mov     ecx, 80000000h
0x18001de97  mov     ebx, eax
0x18001de99  add     eax, ecx
0x18001de9b  test    ecx, eax
0x18001de9d  jnz     short loc_18001DEAB
0x18001de9f  cmp     ebx, 0C0000023h
0x18001dea5  jnz     loc_18001DF45
0x18001deab  mov     rax, cs:qword_180072B30
0x18001deb2  test    rax, rax
0x18001deb5  jz      short loc_18001DEC5
0x18001deb7  mov     edx, [rbp+arg_0]
0x18001deba  lea     r8, [rbp+KeyValueInformation]
0x18001debe  xor     ecx, ecx
0x18001dec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dec5  cmp     [rbp+KeyValueInformation], 0
0x18001deca  jnz     short loc_18001DED3
0x18001decc  mov     ebx, 0C0000017h
0x18001ded1  jmp     short loc_18001DF45
0x18001ded3  mov     rdi, [rbp+KeyValueInformation]
0x18001ded7  lea     rax, [rbp+arg_0]
0x18001dedb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001dedf  mov     r9, rdi; KeyValueInformation
0x18001dee2  mov     [rsp+78h+ResultLength], rax; ResultLength
0x18001dee7  mov     r8d, 2; KeyValueInformationClass
0x18001deed  mov     eax, [rbp+arg_0]
0x18001def0  mov     rdx, r15; ValueName
0x18001def3  mov     [rsp+78h+Length], eax; Length
0x18001def7  call    cs:__imp_ZwQueryValueKey
0x18001defe  nop     dword ptr [rax+rax+00h]
0x18001df03  mov     ebx, eax
0x18001df05  test    eax, eax
0x18001df07  js      short loc_18001DF45
0x18001df09  cmp     [rdi+4], r14d
0x18001df0d  jz      short loc_18001DF16
0x18001df0f  mov     ebx, 0C0000182h
0x18001df14  jmp     short loc_18001DF45
0x18001df16  mov     rcx, [rbp+arg_20]
0x18001df1a  test    rsi, rsi
0x18001df1d  jz      short loc_18001DF3B
0x18001df1f  mov     eax, [rdi+8]
0x18001df22  cmp     [rcx], eax
0x18001df24  jb      short loc_18001DF3B
0x18001df26  mov     [rcx], eax
0x18001df28  lea     rdx, [rdi+0Ch]; Src
0x18001df2c  mov     rcx, rsi; void *
0x18001df2f  mov     r8d, eax; Size
0x18001df32  call    memcpy_0
0x18001df37  xor     ebx, ebx
0x18001df39  jmp     short loc_18001DF45
0x18001df3b  mov     eax, [rdi+8]
0x18001df3e  mov     ebx, 0C0000023h
0x18001df43  mov     [rcx], eax
0x18001df45  mov     r8, [rbp+KeyValueInformation]
0x18001df49  xor     ecx, ecx
0x18001df4b  mov     edx, [rbp+arg_0]
0x18001df4e  call    TpmApiCallbackFree
0x18001df53  mov     rcx, [rbp+KeyHandle]; Handle
0x18001df57  test    rcx, rcx
0x18001df5a  jz      short loc_18001DF68
0x18001df5c  call    cs:__imp_NtClose
0x18001df63  nop     dword ptr [rax+rax+00h]
0x18001df68  mov     eax, ebx
0x18001df6a  add     rsp, 78h
0x18001df6e  pop     r15
0x18001df70  pop     r14
0x18001df72  pop     rdi
0x18001df73  pop     rsi
0x18001df74  pop     rbx
0x18001df75  pop     rbp
0x18001df76  retn
```
