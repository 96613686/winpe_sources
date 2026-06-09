# PiInitFirmwareResources

- ea: `0x140c62968`
- end: `0x140c62be1`
- name: `PiInitFirmwareResources`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140c616dc`

## callees

- `0x1406daa70`
- `0x1406db490`
- `0x14087b818`
- `0x1408eeff0`
- `0x14092af90`
- `0x140c62968`

## string_xrefs

- `0x140c629af`: `\Registry\Machine\HARDWARE\UEFI`
- `0x140c62b37`: `LastAttemptVersion`
- `0x140c62b6e`: `LastAttemptStatus`

## pseudocode

```c
__int64 __fastcall PiInitFirmwareResources(__int64 a1)
{
  int v1; // eax
  NTSTATUS v2; // edi
  const GUID **v3; // rsi
  int v4; // eax
  HANDLE v5; // r14
  const GUID *v6; // r12
  HANDLE v7; // rbx
  UNICODE_STRING ValueName; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING GuidString; // [rsp+40h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+40h] BYREF
  HANDLE v12; // [rsp+98h] [rbp+48h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp+50h] BYREF

  v1 = *(_DWORD *)(a1 + 264);
  v12 = 0;
  Handle = 0;
  *(_DWORD *)(&ValueName.MaximumLength + 1) = 0;
  KeyHandle = 0;
  GuidString = 0;
  if ( (v1 & 1) == 0 )
    return 0;
  v3 = (const GUID **)(a1 + 296);
  if ( *v3 == (const GUID *)v3 )
  {
    return 0;
  }
  else
  {
    ValueName.Buffer = L"\\Registry\\Machine\\HARDWARE\\UEFI";
    *(_DWORD *)&ValueName.Length = 4194366;
    v4 = IopCreateRegistryKeyEx(&v12, 0, &ValueName, 983103, 0, 0);
    v5 = v12;
    v2 = v4;
    if ( v4 >= 0 )
    {
      ValueName.Buffer = L"ESRT";
      *(_DWORD *)&ValueName.Length = 655368;
      v2 = IopCreateRegistryKeyEx(&Handle, v12, &ValueName, 983103, 0, 0);
      if ( v2 >= 0 )
      {
        v6 = *v3;
        if ( *v3 != (const GUID *)v3 )
        {
          do
          {
            v2 = RtlStringFromGUID(v6 + 1, &GuidString);
            if ( v2 < 0 )
              break;
            v2 = IopCreateRegistryKeyEx(&KeyHandle, Handle, &GuidString, 983103, 0, 0);
            RtlFreeAnsiString(&GuidString);
            if ( v2 < 0 )
              break;
            v7 = KeyHandle;
            ValueName.Buffer = (wchar_t *)L"Type";
            *(_DWORD *)&ValueName.Length = 655368;
            ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, (PVOID)&v6[2], 4u);
            *(_DWORD *)&ValueName.Length = 1048590;
            ValueName.Buffer = L"Version";
            ZwSetValueKey(v7, &ValueName, 0, 4u, &v6[2].Data2, 4u);
            *(_DWORD *)&ValueName.Length = 3014700;
            ValueName.Buffer = L"LowestSupportedVersion";
            ZwSetValueKey(v7, &ValueName, 0, 4u, v6[2].Data4, 4u);
            *(_DWORD *)&ValueName.Length = 2490404;
            ValueName.Buffer = (wchar_t *)L"LastAttemptVersion";
            ZwSetValueKey(v7, &ValueName, 0, 4u, (PVOID)&v6[3], 4u);
            *(_DWORD *)&ValueName.Length = 2359330;
            ValueName.Buffer = (wchar_t *)L"LastAttemptStatus";
            ZwSetValueKey(v7, &ValueName, 0, 4u, &v6[3].Data2, 4u);
            ZwClose(v7);
            v6 = *(const GUID **)&v6->Data1;
          }
          while ( v6 != (const GUID *)v3 );
          v5 = v12;
        }
      }
      if ( Handle )
        ZwClose(Handle);
    }
    if ( v5 )
      ZwClose(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140c62968  push    rbp
0x140c6296a  push    rbx
0x140c6296b  push    rsi
0x140c6296c  push    rdi
0x140c6296d  push    r12
0x140c6296f  push    r13
0x140c62971  push    r14
0x140c62973  mov     rbp, rsp
0x140c62976  sub     rsp, 50h
0x140c6297a  mov     eax, [rcx+108h]
0x140c62980  xor     ebx, ebx
0x140c62982  mov     [rbp+arg_8], rbx
0x140c62986  xorps   xmm0, xmm0
0x140c62989  mov     [rbp+Handle], rbx
0x140c6298d  mov     dword ptr [rbp+ValueName+4], ebx
0x140c62990  mov     [rbp+KeyHandle], rbx
0x140c62994  movups  xmmword ptr [rbp+GuidString.Length], xmm0
0x140c62998  test    al, 1
0x140c6299a  jnz     short loc_140C629A3
0x140c6299c  mov     edi, ebx
0x140c6299e  jmp     loc_140C62BCF
0x140c629a3  lea     rsi, [rcx+128h]
0x140c629aa  cmp     [rsi], rsi
0x140c629ad  jz      short loc_140C6299C
0x140c629af  lea     rax, aRegistryMachin_114; "\\Registry\\Machine\\HARDWARE\\UEFI"
0x140c629b6  mov     qword ptr [rsp+50h+DataSize], rbx
0x140c629bb  mov     r9d, 0F003Fh
0x140c629c1  mov     [rbp+ValueName.Buffer], rax
0x140c629c5  lea     r8, [rbp+ValueName]
0x140c629c9  mov     dword ptr [rbp+ValueName.Length], 40003Eh
0x140c629d0  xor     edx, edx
0x140c629d2  mov     dword ptr [rsp+50h+Data], ebx
0x140c629d6  lea     rcx, [rbp+arg_8]
0x140c629da  call    IopCreateRegistryKeyEx
0x140c629df  mov     r14, [rbp+arg_8]
0x140c629e3  mov     edi, eax
0x140c629e5  test    eax, eax
0x140c629e7  js      loc_140C62BC2
0x140c629ed  lea     rax, aEsrt; "ESRT"
0x140c629f4  mov     qword ptr [rsp+50h+DataSize], rbx
0x140c629f9  mov     r9d, 0F003Fh
0x140c629ff  mov     [rbp+ValueName.Buffer], rax
0x140c62a03  lea     r8, [rbp+ValueName]
0x140c62a07  mov     dword ptr [rbp+ValueName.Length], 0A0008h
0x140c62a0e  mov     rdx, r14
0x140c62a11  mov     dword ptr [rsp+50h+Data], ebx
0x140c62a15  lea     rcx, [rbp+Handle]
0x140c62a19  call    IopCreateRegistryKeyEx
0x140c62a1e  mov     edi, eax
0x140c62a20  test    eax, eax
0x140c62a22  js      loc_140C62BB3
0x140c62a28  mov     r12, [rsi]
0x140c62a2b  cmp     r12, rsi
0x140c62a2e  jz      loc_140C62BB3
0x140c62a34  lea     rdx, [rbp+GuidString]; GuidString
0x140c62a38  lea     rcx, [r12+10h]; Guid
0x140c62a3d  call    RtlStringFromGUID
0x140c62a42  mov     edi, eax
0x140c62a44  test    eax, eax
0x140c62a46  js      loc_140C62BAF
0x140c62a4c  mov     rdx, [rbp+Handle]
0x140c62a50  lea     r8, [rbp+GuidString]
0x140c62a54  mov     qword ptr [rsp+50h+DataSize], rbx
0x140c62a59  lea     rcx, [rbp+KeyHandle]
0x140c62a5d  mov     r9d, 0F003Fh
0x140c62a63  mov     dword ptr [rsp+50h+Data], ebx
0x140c62a67  call    IopCreateRegistryKeyEx
0x140c62a6c  lea     rcx, [rbp+GuidString]; UnicodeString
0x140c62a70  mov     edi, eax
0x140c62a72  call    RtlFreeAnsiString
0x140c62a77  test    edi, edi
0x140c62a79  js      loc_140C62BAF
0x140c62a7f  mov     rbx, [rbp+KeyHandle]
0x140c62a83  lea     rax, aType_1; "Type"
0x140c62a8a  mov     [rbp+ValueName.Buffer], rax
0x140c62a8e  lea     rdx, [rbp+ValueName]; ValueName
0x140c62a92  mov     r9d, 4; Type
0x140c62a98  mov     dword ptr [rbp+ValueName.Length], 0A0008h
0x140c62a9f  lea     rax, [r12+20h]
0x140c62aa4  mov     [rsp+50h+DataSize], r9d; DataSize
0x140c62aa9  xor     r8d, r8d; TitleIndex
0x140c62aac  mov     [rsp+50h+Data], rax; Data
0x140c62ab1  mov     rcx, rbx; KeyHandle
0x140c62ab4  call    ZwSetValueKey
0x140c62ab9  mov     ecx, 4
0x140c62abe  mov     dword ptr [rbp+ValueName.Length], 10000Eh
0x140c62ac5  mov     [rsp+50h+DataSize], ecx; DataSize
0x140c62ac9  lea     rax, aVersion_1; "Version"
0x140c62ad0  mov     [rbp+ValueName.Buffer], rax
0x140c62ad4  lea     rdx, [rbp+ValueName]; ValueName
0x140c62ad8  lea     rax, [r12+24h]
0x140c62add  mov     r9d, ecx; Type
0x140c62ae0  xor     r8d, r8d; TitleIndex
0x140c62ae3  mov     [rsp+50h+Data], rax; Data
0x140c62ae8  mov     rcx, rbx; KeyHandle
0x140c62aeb  call    ZwSetValueKey
0x140c62af0  mov     ecx, 4
0x140c62af5  mov     dword ptr [rbp+ValueName.Length], 2E002Ch
0x140c62afc  mov     [rsp+50h+DataSize], ecx; DataSize
0x140c62b00  lea     rax, aLowestsupporte; "LowestSupportedVersion"
0x140c62b07  mov     [rbp+ValueName.Buffer], rax
0x140c62b0b  lea     rdx, [rbp+ValueName]; ValueName
0x140c62b0f  lea     rax, [r12+28h]
0x140c62b14  mov     r9d, ecx; Type
0x140c62b17  xor     r8d, r8d; TitleIndex
0x140c62b1a  mov     [rsp+50h+Data], rax; Data
0x140c62b1f  mov     rcx, rbx; KeyHandle
0x140c62b22  call    ZwSetValueKey
0x140c62b27  mov     ecx, 4
0x140c62b2c  mov     dword ptr [rbp+ValueName.Length], 260024h
0x140c62b33  mov     [rsp+50h+DataSize], ecx; DataSize
0x140c62b37  lea     rax, aLastattemptver; "LastAttemptVersion"
0x140c62b3e  mov     [rbp+ValueName.Buffer], rax
0x140c62b42  lea     rdx, [rbp+ValueName]; ValueName
0x140c62b46  lea     rax, [r12+30h]
0x140c62b4b  mov     r9d, ecx; Type
0x140c62b4e  xor     r8d, r8d; TitleIndex
0x140c62b51  mov     [rsp+50h+Data], rax; Data
0x140c62b56  mov     rcx, rbx; KeyHandle
0x140c62b59  call    ZwSetValueKey
0x140c62b5e  mov     ecx, 4
0x140c62b63  mov     dword ptr [rbp+ValueName.Length], 240022h
0x140c62b6a  mov     [rsp+50h+DataSize], ecx; DataSize
0x140c62b6e  lea     rax, aLastattemptsta; "LastAttemptStatus"
0x140c62b75  mov     [rbp+ValueName.Buffer], rax
0x140c62b79  lea     rdx, [rbp+ValueName]; ValueName
0x140c62b7d  lea     rax, [r12+34h]
0x140c62b82  mov     r9d, ecx; Type
0x140c62b85  xor     r8d, r8d; TitleIndex
0x140c62b88  mov     [rsp+50h+Data], rax; Data
0x140c62b8d  mov     rcx, rbx; KeyHandle
0x140c62b90  call    ZwSetValueKey
0x140c62b95  mov     rcx, rbx; Handle
0x140c62b98  call    ZwClose
0x140c62b9d  mov     r12, [r12]
0x140c62ba1  mov     ebx, 0
0x140c62ba6  cmp     r12, rsi
0x140c62ba9  jnz     loc_140C62A34
0x140c62baf  mov     r14, [rbp+arg_8]
0x140c62bb3  cmp     [rbp+Handle], rbx
0x140c62bb7  jz      short loc_140C62BC2
0x140c62bb9  mov     rcx, [rbp+Handle]; Handle
0x140c62bbd  call    ZwClose
0x140c62bc2  test    r14, r14
0x140c62bc5  jz      short loc_140C62BCF
0x140c62bc7  mov     rcx, r14; Handle
0x140c62bca  call    ZwClose
0x140c62bcf  mov     eax, edi
0x140c62bd1  add     rsp, 50h
0x140c62bd5  pop     r14
0x140c62bd7  pop     r13
0x140c62bd9  pop     r12
0x140c62bdb  pop     rdi
0x140c62bdc  pop     rsi
0x140c62bdd  pop     rbx
0x140c62bde  pop     rbp
0x140c62bdf  retn
```
