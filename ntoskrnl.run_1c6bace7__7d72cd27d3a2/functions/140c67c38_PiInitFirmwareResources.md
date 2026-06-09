# PiInitFirmwareResources

- ea: `0x140c67c38`
- end: `0x140c67eb1`
- name: `PiInitFirmwareResources`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140c669ac`

## callees

- `0x1406dd5c0`
- `0x1406ddfe0`
- `0x1409230b0`
- `0x14094b120`
- `0x140a95b68`
- `0x140c67c38`

## string_xrefs

- `0x140c67c7f`: `\Registry\Machine\HARDWARE\UEFI`
- `0x140c67e07`: `LastAttemptVersion`
- `0x140c67e3e`: `LastAttemptStatus`

## pseudocode

```c
__int64 __fastcall PiInitFirmwareResources(__int64 a1)
{
  int v1; // eax
  int v2; // edi
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
0x140c67c38  push    rbp
0x140c67c3a  push    rbx
0x140c67c3b  push    rsi
0x140c67c3c  push    rdi
0x140c67c3d  push    r12
0x140c67c3f  push    r13
0x140c67c41  push    r14
0x140c67c43  mov     rbp, rsp
0x140c67c46  sub     rsp, 50h
0x140c67c4a  mov     eax, [rcx+108h]
0x140c67c50  xor     ebx, ebx
0x140c67c52  mov     [rbp+arg_8], rbx
0x140c67c56  xorps   xmm0, xmm0
0x140c67c59  mov     [rbp+Handle], rbx
0x140c67c5d  mov     dword ptr [rbp+ValueName+4], ebx
0x140c67c60  mov     [rbp+KeyHandle], rbx
0x140c67c64  movups  xmmword ptr [rbp+GuidString.Length], xmm0
0x140c67c68  test    al, 1
0x140c67c6a  jnz     short loc_140C67C73
0x140c67c6c  mov     edi, ebx
0x140c67c6e  jmp     loc_140C67E9F
0x140c67c73  lea     rsi, [rcx+128h]
0x140c67c7a  cmp     [rsi], rsi
0x140c67c7d  jz      short loc_140C67C6C
0x140c67c7f  lea     rax, aRegistryMachin_114; "\\Registry\\Machine\\HARDWARE\\UEFI"
0x140c67c86  mov     qword ptr [rsp+50h+DataSize], rbx
0x140c67c8b  mov     r9d, 0F003Fh
0x140c67c91  mov     [rbp+ValueName.Buffer], rax
0x140c67c95  lea     r8, [rbp+ValueName]
0x140c67c99  mov     dword ptr [rbp+ValueName.Length], 40003Eh
0x140c67ca0  xor     edx, edx
0x140c67ca2  mov     dword ptr [rsp+50h+Data], ebx
0x140c67ca6  lea     rcx, [rbp+arg_8]
0x140c67caa  call    IopCreateRegistryKeyEx
0x140c67caf  mov     r14, [rbp+arg_8]
0x140c67cb3  mov     edi, eax
0x140c67cb5  test    eax, eax
0x140c67cb7  js      loc_140C67E92
0x140c67cbd  lea     rax, aEsrt; "ESRT"
0x140c67cc4  mov     qword ptr [rsp+50h+DataSize], rbx
0x140c67cc9  mov     r9d, 0F003Fh
0x140c67ccf  mov     [rbp+ValueName.Buffer], rax
0x140c67cd3  lea     r8, [rbp+ValueName]
0x140c67cd7  mov     dword ptr [rbp+ValueName.Length], 0A0008h
0x140c67cde  mov     rdx, r14
0x140c67ce1  mov     dword ptr [rsp+50h+Data], ebx
0x140c67ce5  lea     rcx, [rbp+Handle]
0x140c67ce9  call    IopCreateRegistryKeyEx
0x140c67cee  mov     edi, eax
0x140c67cf0  test    eax, eax
0x140c67cf2  js      loc_140C67E83
0x140c67cf8  mov     r12, [rsi]
0x140c67cfb  cmp     r12, rsi
0x140c67cfe  jz      loc_140C67E83
0x140c67d04  lea     rdx, [rbp+GuidString]; GuidString
0x140c67d08  lea     rcx, [r12+10h]; Guid
0x140c67d0d  call    RtlStringFromGUID
0x140c67d12  mov     edi, eax
0x140c67d14  test    eax, eax
0x140c67d16  js      loc_140C67E7F
0x140c67d1c  mov     rdx, [rbp+Handle]
0x140c67d20  lea     r8, [rbp+GuidString]
0x140c67d24  mov     qword ptr [rsp+50h+DataSize], rbx
0x140c67d29  lea     rcx, [rbp+KeyHandle]
0x140c67d2d  mov     r9d, 0F003Fh
0x140c67d33  mov     dword ptr [rsp+50h+Data], ebx
0x140c67d37  call    IopCreateRegistryKeyEx
0x140c67d3c  lea     rcx, [rbp+GuidString]; UnicodeString
0x140c67d40  mov     edi, eax
0x140c67d42  call    RtlFreeAnsiString
0x140c67d47  test    edi, edi
0x140c67d49  js      loc_140C67E7F
0x140c67d4f  mov     rbx, [rbp+KeyHandle]
0x140c67d53  lea     rax, aType_1; "Type"
0x140c67d5a  mov     [rbp+ValueName.Buffer], rax
0x140c67d5e  lea     rdx, [rbp+ValueName]; ValueName
0x140c67d62  mov     r9d, 4; Type
0x140c67d68  mov     dword ptr [rbp+ValueName.Length], 0A0008h
0x140c67d6f  lea     rax, [r12+20h]
0x140c67d74  mov     [rsp+50h+DataSize], r9d; DataSize
0x140c67d79  xor     r8d, r8d; TitleIndex
0x140c67d7c  mov     [rsp+50h+Data], rax; Data
0x140c67d81  mov     rcx, rbx; KeyHandle
0x140c67d84  call    ZwSetValueKey
0x140c67d89  mov     ecx, 4
0x140c67d8e  mov     dword ptr [rbp+ValueName.Length], 10000Eh
0x140c67d95  mov     [rsp+50h+DataSize], ecx; DataSize
0x140c67d99  lea     rax, aVersion_1; "Version"
0x140c67da0  mov     [rbp+ValueName.Buffer], rax
0x140c67da4  lea     rdx, [rbp+ValueName]; ValueName
0x140c67da8  lea     rax, [r12+24h]
0x140c67dad  mov     r9d, ecx; Type
0x140c67db0  xor     r8d, r8d; TitleIndex
0x140c67db3  mov     [rsp+50h+Data], rax; Data
0x140c67db8  mov     rcx, rbx; KeyHandle
0x140c67dbb  call    ZwSetValueKey
0x140c67dc0  mov     ecx, 4
0x140c67dc5  mov     dword ptr [rbp+ValueName.Length], 2E002Ch
0x140c67dcc  mov     [rsp+50h+DataSize], ecx; DataSize
0x140c67dd0  lea     rax, aLowestsupporte; "LowestSupportedVersion"
0x140c67dd7  mov     [rbp+ValueName.Buffer], rax
0x140c67ddb  lea     rdx, [rbp+ValueName]; ValueName
0x140c67ddf  lea     rax, [r12+28h]
0x140c67de4  mov     r9d, ecx; Type
0x140c67de7  xor     r8d, r8d; TitleIndex
0x140c67dea  mov     [rsp+50h+Data], rax; Data
0x140c67def  mov     rcx, rbx; KeyHandle
0x140c67df2  call    ZwSetValueKey
0x140c67df7  mov     ecx, 4
0x140c67dfc  mov     dword ptr [rbp+ValueName.Length], 260024h
0x140c67e03  mov     [rsp+50h+DataSize], ecx; DataSize
0x140c67e07  lea     rax, aLastattemptver; "LastAttemptVersion"
0x140c67e0e  mov     [rbp+ValueName.Buffer], rax
0x140c67e12  lea     rdx, [rbp+ValueName]; ValueName
0x140c67e16  lea     rax, [r12+30h]
0x140c67e1b  mov     r9d, ecx; Type
0x140c67e1e  xor     r8d, r8d; TitleIndex
0x140c67e21  mov     [rsp+50h+Data], rax; Data
0x140c67e26  mov     rcx, rbx; KeyHandle
0x140c67e29  call    ZwSetValueKey
0x140c67e2e  mov     ecx, 4
0x140c67e33  mov     dword ptr [rbp+ValueName.Length], 240022h
0x140c67e3a  mov     [rsp+50h+DataSize], ecx; DataSize
0x140c67e3e  lea     rax, aLastattemptsta; "LastAttemptStatus"
0x140c67e45  mov     [rbp+ValueName.Buffer], rax
0x140c67e49  lea     rdx, [rbp+ValueName]; ValueName
0x140c67e4d  lea     rax, [r12+34h]
0x140c67e52  mov     r9d, ecx; Type
0x140c67e55  xor     r8d, r8d; TitleIndex
0x140c67e58  mov     [rsp+50h+Data], rax; Data
0x140c67e5d  mov     rcx, rbx; KeyHandle
0x140c67e60  call    ZwSetValueKey
0x140c67e65  mov     rcx, rbx; Handle
0x140c67e68  call    ZwClose
0x140c67e6d  mov     r12, [r12]
0x140c67e71  mov     ebx, 0
0x140c67e76  cmp     r12, rsi
0x140c67e79  jnz     loc_140C67D04
0x140c67e7f  mov     r14, [rbp+arg_8]
0x140c67e83  cmp     [rbp+Handle], rbx
0x140c67e87  jz      short loc_140C67E92
0x140c67e89  mov     rcx, [rbp+Handle]; Handle
0x140c67e8d  call    ZwClose
0x140c67e92  test    r14, r14
0x140c67e95  jz      short loc_140C67E9F
0x140c67e97  mov     rcx, r14; Handle
0x140c67e9a  call    ZwClose
0x140c67e9f  mov     eax, edi
0x140c67ea1  add     rsp, 50h
0x140c67ea5  pop     r14
0x140c67ea7  pop     r13
0x140c67ea9  pop     r12
0x140c67eab  pop     rdi
0x140c67eac  pop     rsi
0x140c67ead  pop     rbx
0x140c67eae  pop     rbp
0x140c67eaf  retn
```
