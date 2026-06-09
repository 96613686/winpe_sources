# _RefreshCacheForUser

- ea: `0x18002b38c`
- end: `0x18002b703`
- name: `_RefreshCacheForUser`
- size: `887`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800747f0`
- `0x1800e03a0`

## callees

- `0x18002a790`
- `0x18002b38c`
- `0x18010cf84`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002b522`
- `ntdll!RtlInitUnicodeString` at `0x18002b61b`
- `ntdll!RtlInitUnicodeString` at `0x18002b522`
- `ntdll!RtlInitUnicodeString` at `0x18002b61b`
- `ntdll!NtOpenKey` at `0x18002b565`
- `ntdll!NtOpenKey` at `0x18002b65d`
- `ntdll!NtOpenKey` at `0x18002b565`
- `ntdll!NtOpenKey` at `0x18002b65d`
- `ntdll!RtlNtStatusToDosError` at `0x18002b402`
- `ntdll!RtlNtStatusToDosError` at `0x18002b402`
- `ntdll!NtEnumerateKey` at `0x18002b475`
- `ntdll!NtEnumerateKey` at `0x18002b5a7`
- `ntdll!NtEnumerateKey` at `0x18002b475`
- `ntdll!NtEnumerateKey` at `0x18002b5a7`
- `ntdll!NtDeleteKey` at `0x18002b68d`
- `ntdll!NtDeleteKey` at `0x18002b6be`
- `ntdll!NtDeleteKey` at `0x18002b68d`
- `ntdll!NtDeleteKey` at `0x18002b6be`
- `ntdll!NtClose` at `0x18002b435`
- `ntdll!NtClose` at `0x18002b4b5`
- `ntdll!NtClose` at `0x18002b6a8`
- `ntdll!NtClose` at `0x18002b6d1`
- `ntdll!NtClose` at `0x18002b6eb`
- `ntdll!NtClose` at `0x18002b435`
- `ntdll!NtClose` at `0x18002b4b5`
- `ntdll!NtClose` at `0x18002b6a8`
- `ntdll!NtClose` at `0x18002b6d1`
- `ntdll!NtClose` at `0x18002b6eb`

## pseudocode

```c
ULONG __fastcall RefreshCacheForUser(__int64 a1, WCHAR *a2)
{
  ULONG v3; // edi
  NTSTATUS v4; // ebx
  HANDLE v6; // rbx
  ULONG v7; // ebx
  NTSTATUS v8; // esi
  HANDLE v9; // r14
  ULONG v10; // r14d
  NTSTATUS v11; // eax
  ULONG v12; // ecx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v18; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v19; // [rsp+90h] [rbp-70h] BYREF
  _BYTE KeyInformation[12]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v21; // [rsp+ACh] [rbp-54h]
  WCHAR SourceString[122]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v23[6]; // [rsp+1A4h] [rbp+A4h] BYREF

  Handle = 0;
  v3 = 0;
  ResultLength = 0;
  v18 = 0;
  v4 = OpenRegKeyForUser(&Handle, (WCHAR *)&word_18029DECC, a2, 0xF003Fu, 2);
  if ( v4 >= 0 )
  {
    while ( 1 )
    {
      KeyHandle = 0;
      if ( NtEnumerateKey(Handle, v3, KeyBasicInformation, KeyInformation, 0x104u, &ResultLength) < 0 )
        break;
      if ( ResultLength >= 0x102 )
        goto LABEL_12;
      if ( (WCHAR *)((char *)SourceString + v21) >= v23 )
        goto LABEL_12;
      *(_OWORD *)&ObjectAttributes.ObjectName = 0;
      SourceString[(unsigned __int64)v21 >> 1] = 0;
      v6 = Handle;
      *(_OWORD *)&ObjectAttributes.Length = 0;
      *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
      DestinationString = 0;
      if ( !Handle )
        goto LABEL_12;
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = v6;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( !NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) )
      {
        v7 = 0;
        while ( 1 )
        {
          *(_QWORD *)&DestinationString.Length = 0;
          v8 = NtEnumerateKey(KeyHandle, v7, KeyBasicInformation, KeyInformation, 0x104u, &ResultLength);
          if ( v8 < 0 )
            break;
          if ( ResultLength >= 0x102 || (WCHAR *)((char *)SourceString + v21) >= v23 )
          {
            ++v7;
          }
          else
          {
            *(_OWORD *)&ObjectAttributes.ObjectName = 0;
            SourceString[(unsigned __int64)v21 >> 1] = 0;
            v9 = KeyHandle;
            *(_OWORD *)&ObjectAttributes.Length = 0;
            *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
            v19 = 0;
            if ( KeyHandle )
            {
              RtlInitUnicodeString(&v19, SourceString);
              ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = &v19;
              ObjectAttributes.RootDirectory = v9;
              ObjectAttributes.Attributes = 64;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              v10 = v7 + 1;
              if ( !NtOpenKey((PHANDLE)&DestinationString, 0xF003Fu, &ObjectAttributes) )
              {
                v8 = NtDeleteKey(*(HANDLE *)&DestinationString.Length);
                NtClose(*(HANDLE *)&DestinationString.Length);
                if ( v8 >= 0 )
                  v10 = v7;
              }
            }
            else
            {
              v10 = v7 + 1;
            }
            v7 = v10;
            if ( v8 == -2147483622 )
              break;
          }
        }
        if ( v8 != -2147483622 )
        {
          NtClose(KeyHandle);
          break;
        }
        v11 = NtDeleteKey(KeyHandle);
        v12 = v3 + 1;
        if ( v11 >= 0 )
          v12 = v3;
        v3 = v12;
        NtClose(KeyHandle);
      }
      else
      {
LABEL_12:
        ++v3;
      }
    }
    v4 = OpenSubKey(Handle, a1, 131078, 1, &v18);
    if ( v4 >= 0 )
      NtClose(v18);
  }
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  return RtlNtStatusToDosError(v4);
}

```

## disassembly

```asm
0x18002b38c  mov     [rsp-8+arg_10], rbx
0x18002b391  push    rbp
0x18002b392  push    rsi
0x18002b393  push    rdi
0x18002b394  push    r14
0x18002b396  push    r15
0x18002b398  lea     rbp, [rsp-0C0h]
0x18002b3a0  sub     rsp, 1C0h
0x18002b3a7  mov     rax, cs:__security_cookie
0x18002b3ae  xor     rax, rsp
0x18002b3b1  mov     [rbp+0E0h+var_30], rax
0x18002b3b8  mov     r15, rcx
0x18002b3bb  mov     [rsp+1E0h+Handle], 0
0x18002b3c4  xor     edi, edi
0x18002b3c6  mov     [rsp+1E0h+Length], 2; char
0x18002b3ce  mov     r8, rdx
0x18002b3d1  mov     [rsp+1E0h+var_1B0], edi
0x18002b3d5  lea     rdx, word_18029DECC
0x18002b3dc  mov     [rbp+0E0h+var_158], rdi
0x18002b3e0  lea     rcx, [rsp+1E0h+Handle]; KeyHandle
0x18002b3e5  mov     r9d, 0F003Fh
0x18002b3eb  call    OpenRegKeyForUser
0x18002b3f0  mov     ebx, eax
0x18002b3f2  test    eax, eax
0x18002b3f4  jns     short loc_18002B44C
0x18002b3f6  mov     rcx, [rsp+1E0h+Handle]; Handle
0x18002b3fb  test    rcx, rcx
0x18002b3fe  jnz     short loc_18002B435
0x18002b400  mov     ecx, ebx; Status
0x18002b402  call    cs:__imp_RtlNtStatusToDosError
0x18002b409  nop     dword ptr [rax+rax+00h]
0x18002b40e  mov     rcx, [rbp+0E0h+var_30]
0x18002b415  xor     rcx, rsp; StackCookie
0x18002b418  call    __security_check_cookie
0x18002b41d  mov     rbx, [rsp+1E0h+arg_10]
0x18002b425  add     rsp, 1C0h
0x18002b42c  pop     r15
0x18002b42e  pop     r14
0x18002b430  pop     rdi
0x18002b431  pop     rsi
0x18002b432  pop     rbp
0x18002b433  retn
0x18002b435  call    cs:__imp_NtClose
0x18002b43c  nop     dword ptr [rax+rax+00h]
0x18002b441  mov     [rsp+1E0h+Handle], 0
0x18002b44a  jmp     short loc_18002B400
0x18002b44c  mov     rcx, [rsp+1E0h+Handle]; KeyHandle
0x18002b451  lea     rax, [rsp+1E0h+var_1B0]
0x18002b456  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x18002b45b  lea     r9, [rbp+0E0h+KeyInformation]; KeyInformation
0x18002b45f  xor     r8d, r8d; KeyInformationClass
0x18002b462  mov     [rsp+1E0h+Length], 104h; Length
0x18002b46a  mov     edx, edi; Index
0x18002b46c  mov     [rsp+1E0h+KeyHandle], 0
0x18002b475  call    cs:__imp_NtEnumerateKey
0x18002b47c  nop     dword ptr [rax+rax+00h]
0x18002b481  test    eax, eax
0x18002b483  jns     short loc_18002B4C6
0x18002b485  mov     rcx, [rsp+1E0h+Handle]
0x18002b48a  lea     rax, [rbp+0E0h+var_158]
0x18002b48e  mov     r9d, 1
0x18002b494  mov     qword ptr [rsp+1E0h+Length], rax
0x18002b499  mov     r8d, 20006h
0x18002b49f  mov     rdx, r15
0x18002b4a2  call    _OpenSubKey
0x18002b4a7  mov     ebx, eax
0x18002b4a9  test    eax, eax
0x18002b4ab  js      loc_18002B3F6
0x18002b4b1  mov     rcx, [rbp+0E0h+var_158]; Handle
0x18002b4b5  call    cs:__imp_NtClose
0x18002b4bc  nop     dword ptr [rax+rax+00h]
0x18002b4c1  jmp     loc_18002B3F6
0x18002b4c6  cmp     [rsp+1E0h+var_1B0], 102h
0x18002b4ce  jnb     loc_18002B575
0x18002b4d4  mov     ecx, [rbp+0E0h+var_134]
0x18002b4d7  lea     rax, [rbp+0E0h+SourceString]
0x18002b4db  add     rax, rcx
0x18002b4de  lea     rdx, [rbp+0E0h+var_3C]
0x18002b4e5  cmp     rax, rdx
0x18002b4e8  jnb     loc_18002B575
0x18002b4ee  xorps   xmm0, xmm0
0x18002b4f1  shr     rcx, 1
0x18002b4f4  xor     eax, eax
0x18002b4f6  movups  xmmword ptr [rsp+1E0h+ObjectAttributes.ObjectName], xmm0
0x18002b4fb  mov     [rbp+rcx*2+0E0h+SourceString], ax
0x18002b500  mov     rbx, [rsp+1E0h+Handle]
0x18002b505  movups  xmmword ptr [rsp+1E0h+ObjectAttributes.Length], xmm0
0x18002b50a  movups  xmmword ptr [rsp+1E0h+ObjectAttributes+1Ch], xmm0
0x18002b50f  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x18002b514  test    rbx, rbx
0x18002b517  jz      short loc_18002B575
0x18002b519  lea     rdx, [rbp+0E0h+SourceString]; SourceString
0x18002b51d  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x18002b522  call    cs:__imp_RtlInitUnicodeString
0x18002b529  nop     dword ptr [rax+rax+00h]
0x18002b52e  lea     rax, [rsp+1E0h+DestinationString]
0x18002b533  mov     [rsp+1E0h+ObjectAttributes.Length], 30h ; '0'
0x18002b53b  xorps   xmm0, xmm0
0x18002b53e  mov     [rsp+1E0h+ObjectAttributes.ObjectName], rax
0x18002b543  lea     r8, [rsp+1E0h+ObjectAttributes]; ObjectAttributes
0x18002b548  mov     [rsp+1E0h+ObjectAttributes.RootDirectory], rbx
0x18002b54d  mov     edx, 0F003Fh; DesiredAccess
0x18002b552  mov     [rsp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18002b55a  lea     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x18002b55f  movdqu  xmmword ptr [rsp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002b565  call    cs:__imp_NtOpenKey
0x18002b56c  nop     dword ptr [rax+rax+00h]
0x18002b571  test    eax, eax
0x18002b573  jz      short loc_18002B57C
0x18002b575  inc     edi
0x18002b577  jmp     loc_18002B44C
0x18002b57c  xor     ebx, ebx
0x18002b57e  mov     rcx, [rsp+1E0h+KeyHandle]; KeyHandle
0x18002b583  lea     rax, [rsp+1E0h+var_1B0]
0x18002b588  mov     [rsp+1E0h+ResultLength], rax; ResultLength
0x18002b58d  lea     r9, [rbp+0E0h+KeyInformation]; KeyInformation
0x18002b591  xor     r8d, r8d; KeyInformationClass
0x18002b594  mov     [rsp+1E0h+Length], 104h; Length
0x18002b59c  mov     edx, ebx; Index
0x18002b59e  mov     qword ptr [rsp+1E0h+DestinationString.Length], 0
0x18002b5a7  call    cs:__imp_NtEnumerateKey
0x18002b5ae  nop     dword ptr [rax+rax+00h]
0x18002b5b3  mov     esi, eax
0x18002b5b5  test    eax, eax
0x18002b5b7  js      loc_18002B680
0x18002b5bd  cmp     [rsp+1E0h+var_1B0], 102h
0x18002b5c5  jnb     loc_18002B6FC
0x18002b5cb  mov     edx, [rbp+0E0h+var_134]
0x18002b5ce  lea     rcx, [rbp+0E0h+SourceString]
0x18002b5d2  add     rcx, rdx
0x18002b5d5  lea     rax, [rbp+0E0h+var_3C]
0x18002b5dc  cmp     rcx, rax
0x18002b5df  jnb     loc_18002B6FC
0x18002b5e5  xorps   xmm0, xmm0
0x18002b5e8  shr     rdx, 1
0x18002b5eb  xor     eax, eax
0x18002b5ed  movups  xmmword ptr [rsp+1E0h+ObjectAttributes.ObjectName], xmm0
0x18002b5f2  mov     [rbp+rdx*2+0E0h+SourceString], ax
0x18002b5f7  mov     r14, [rsp+1E0h+KeyHandle]
0x18002b5fc  movups  xmmword ptr [rsp+1E0h+ObjectAttributes.Length], xmm0
0x18002b601  movups  xmmword ptr [rsp+1E0h+ObjectAttributes+1Ch], xmm0
0x18002b606  movups  xmmword ptr [rbp+0E0h+var_150.Length], xmm0
0x18002b60a  test    r14, r14
0x18002b60d  jz      loc_18002B6E5
0x18002b613  lea     rdx, [rbp+0E0h+SourceString]; SourceString
0x18002b617  lea     rcx, [rbp+0E0h+var_150]; DestinationString
0x18002b61b  call    cs:__imp_RtlInitUnicodeString
0x18002b622  nop     dword ptr [rax+rax+00h]
0x18002b627  lea     rax, [rbp+0E0h+var_150]
0x18002b62b  mov     [rsp+1E0h+ObjectAttributes.Length], 30h ; '0'
0x18002b633  xorps   xmm0, xmm0
0x18002b636  mov     [rsp+1E0h+ObjectAttributes.ObjectName], rax
0x18002b63b  lea     r8, [rsp+1E0h+ObjectAttributes]; ObjectAttributes
0x18002b640  mov     [rsp+1E0h+ObjectAttributes.RootDirectory], r14
0x18002b645  mov     edx, 0F003Fh; DesiredAccess
0x18002b64a  mov     [rsp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18002b652  lea     rcx, [rsp+1E0h+DestinationString]; KeyHandle
0x18002b657  movdqu  xmmword ptr [rsp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002b65d  call    cs:__imp_NtOpenKey
0x18002b664  nop     dword ptr [rax+rax+00h]
0x18002b669  lea     r14d, [rbx+1]
0x18002b66d  test    eax, eax
0x18002b66f  jz      short loc_18002B6B9
0x18002b671  mov     ebx, r14d
0x18002b674  cmp     esi, 8000001Ah
0x18002b67a  jnz     loc_18002B57E
0x18002b680  mov     rcx, [rsp+1E0h+KeyHandle]; Handle
0x18002b685  cmp     esi, 8000001Ah
0x18002b68b  jnz     short loc_18002B6EB
0x18002b68d  call    cs:__imp_NtDeleteKey
0x18002b694  nop     dword ptr [rax+rax+00h]
0x18002b699  lea     ecx, [rdi+1]
0x18002b69c  test    eax, eax
0x18002b69e  cmovns  ecx, edi
0x18002b6a1  mov     edi, ecx
0x18002b6a3  mov     rcx, [rsp+1E0h+KeyHandle]; Handle
0x18002b6a8  call    cs:__imp_NtClose
0x18002b6af  nop     dword ptr [rax+rax+00h]
0x18002b6b4  jmp     loc_18002B44C
0x18002b6b9  mov     rcx, qword ptr [rsp+1E0h+DestinationString.Length]; KeyHandle
0x18002b6be  call    cs:__imp_NtDeleteKey
0x18002b6c5  nop     dword ptr [rax+rax+00h]
0x18002b6ca  mov     rcx, qword ptr [rsp+1E0h+DestinationString.Length]; Handle
0x18002b6cf  mov     esi, eax
0x18002b6d1  call    cs:__imp_NtClose
0x18002b6d8  nop     dword ptr [rax+rax+00h]
0x18002b6dd  test    esi, esi
0x18002b6df  cmovns  r14d, ebx
0x18002b6e3  jmp     short loc_18002B671
0x18002b6e5  lea     r14d, [rbx+1]
0x18002b6e9  jmp     short loc_18002B671
0x18002b6eb  call    cs:__imp_NtClose
0x18002b6f2  nop     dword ptr [rax+rax+00h]
0x18002b6f7  jmp     loc_18002B485
0x18002b6fc  inc     ebx
0x18002b6fe  jmp     loc_18002B57E
```
