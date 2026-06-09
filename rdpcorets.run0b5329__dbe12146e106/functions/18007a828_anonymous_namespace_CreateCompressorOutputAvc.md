# _anonymous_namespace_::CreateCompressorOutputAvc

- ea: `0x18007a828`
- end: `0x18007aaae`
- name: `_anonymous_namespace_::CreateCompressorOutputAvc`
- size: `646`
- prototype: `__int64 __fastcall(int, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007d5a0`

## callees

- `0x180033964`
- `0x180033da0`
- `0x180034970`
- `0x18007a828`
- `0x1800d8f18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a8e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a92c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a977`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a9c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007aa0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a8e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a92c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a977`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a9c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007aa0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007aa39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007aa39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a89c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a89c`

## string_xrefs

- `0x18007a88e`: `Software\Policies\Microsoft\Windows NT\Terminal Services\H264Encoding`
- `0x18007aa06`: `RecordPath`

## pseudocode

```c
OutputAvc *__fastcall anonymous_namespace_::CreateCompressorOutputAvc(int a1, int a2, int a3, int a4)
{
  int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  FILE **v12; // rax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[12]; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+6Ch] [rbp-94h]
  LSTATUS v20; // [rsp+78h] [rbp-88h]
  LSTATUS v21; // [rsp+88h] [rbp-78h]
  LSTATUS v22; // [rsp+8Ch] [rbp-74h]
  BYTE v23[520]; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD v24; // [rsp+29Ch] [rbp+19Ch]

  hKey = 0;
  v8 = 0;
  memset_0(v18, 0, 0x240u);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\H264Encoding",
          0,
          0x20019u,
          &hKey) )
  {
    *(_DWORD *)Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableRecordRGB", 0, &Type, Data, &cbData) && Type == 4 )
    {
      LOBYTE(v8) = *(_DWORD *)Data != 0;
      v19 = v8;
    }
    cbData = 4;
    v9 = RegQueryValueExW(hKey, L"EnableRecordRdp264", 0, &Type, Data, &cbData);
    if ( !v9 && Type == 4 )
    {
      LOBYTE(v9) = *(_DWORD *)Data != 0;
      v20 = v9;
      v8 |= v9;
    }
    cbData = 4;
    v10 = RegQueryValueExW(hKey, L"EnableRecordFeatureMap", 0, &Type, Data, &cbData);
    if ( !v10 && Type == 4 )
    {
      LOBYTE(v10) = *(_DWORD *)Data != 0;
      v21 = v10;
      v8 |= v10;
    }
    cbData = 4;
    v11 = RegQueryValueExW(hKey, L"EnableRecordQPMap", 0, &Type, Data, &cbData);
    if ( !v11 && Type == 4 )
    {
      LOBYTE(v11) = *(_DWORD *)Data != 0;
      v22 = v11;
      v8 |= v11;
    }
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"RecordPath", 0, &Type, v23, &cbData) || Type != 1 )
      v24 = 0;
    else
      v24 = cbData;
    RegCloseKey(hKey);
  }
  ++dword_1801BB4F0;
  if ( v24 && v8 && (v12 = (FILE **)operator new(0x88u)) != 0 )
    return OutputAvc::OutputAvc(v12, a1, a2, a3, a4, (struct RecordSettings *)v18, dword_1801BB4F0);
  else
    return 0;
}

```

## disassembly

```asm
0x18007a828  push    rbp
0x18007a82a  push    rbx
0x18007a82b  push    rsi
0x18007a82c  push    rdi
0x18007a82d  push    r13
0x18007a82f  push    r14
0x18007a831  push    r15
0x18007a833  lea     rbp, [rsp-1B0h]
0x18007a83b  sub     rsp, 2B0h
0x18007a842  mov     rax, cs:__security_cookie
0x18007a849  xor     rax, rsp
0x18007a84c  mov     [rbp+1E0h+var_40], rax
0x18007a853  mov     r15d, r8d
0x18007a856  mov     [rsp+2E0h+hKey], 0
0x18007a85f  mov     r14d, edx
0x18007a862  mov     esi, ecx
0x18007a864  xor     edx, edx; Val
0x18007a866  lea     rcx, [rsp+2E0h+var_280]; void *
0x18007a86b  mov     r8d, 240h; Size
0x18007a871  mov     edi, r9d
0x18007a874  xor     ebx, ebx
0x18007a876  call    memset_0
0x18007a87b  lea     rax, [rsp+2E0h+hKey]
0x18007a880  mov     r9d, 20019h; samDesired
0x18007a886  xor     r8d, r8d; ulOptions
0x18007a889  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18007a88e  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows "...
0x18007a895  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007a89c  call    cs:__imp_RegOpenKeyExW
0x18007a8a2  test    eax, eax
0x18007a8a4  jnz     loc_18007AA3F
0x18007a8aa  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18007a8af  lea     rax, [rsp+2E0h+cbData]
0x18007a8b4  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18007a8b9  lea     r13d, [rbx+4]
0x18007a8bd  lea     rax, [rsp+2E0h+Data]
0x18007a8c2  mov     dword ptr [rsp+2E0h+Data], ebx
0x18007a8c6  lea     r9, [rsp+2E0h+Type]; lpType
0x18007a8cb  mov     [rsp+2E0h+phkResult], rax; lpData
0x18007a8d0  xor     r8d, r8d; lpReserved
0x18007a8d3  mov     [rsp+2E0h+Type], ebx
0x18007a8d7  lea     rdx, aEnablerecordrg; "EnableRecordRGB"
0x18007a8de  mov     [rsp+2E0h+cbData], r13d
0x18007a8e3  call    cs:__imp_RegQueryValueExW
0x18007a8e9  test    eax, eax
0x18007a8eb  jnz     short loc_18007A8FF
0x18007a8ed  cmp     [rsp+2E0h+Type], r13d
0x18007a8f2  jnz     short loc_18007A8FF
0x18007a8f4  cmp     dword ptr [rsp+2E0h+Data], ebx
0x18007a8f8  setnz   bl
0x18007a8fb  mov     [rsp+2E0h+var_274], ebx
0x18007a8ff  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18007a904  lea     rax, [rsp+2E0h+cbData]
0x18007a909  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18007a90e  lea     r9, [rsp+2E0h+Type]; lpType
0x18007a913  lea     rax, [rsp+2E0h+Data]
0x18007a918  mov     [rsp+2E0h+cbData], r13d
0x18007a91d  xor     r8d, r8d; lpReserved
0x18007a920  mov     [rsp+2E0h+phkResult], rax; lpData
0x18007a925  lea     rdx, aEnablerecordrd; "EnableRecordRdp264"
0x18007a92c  call    cs:__imp_RegQueryValueExW
0x18007a932  test    eax, eax
0x18007a934  jnz     short loc_18007A94A
0x18007a936  cmp     [rsp+2E0h+Type], r13d
0x18007a93b  jnz     short loc_18007A94A
0x18007a93d  cmp     dword ptr [rsp+2E0h+Data], eax
0x18007a941  setnz   al
0x18007a944  mov     [rsp+2E0h+var_268], eax
0x18007a948  or      ebx, eax
0x18007a94a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18007a94f  lea     rax, [rsp+2E0h+cbData]
0x18007a954  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18007a959  lea     r9, [rsp+2E0h+Type]; lpType
0x18007a95e  lea     rax, [rsp+2E0h+Data]
0x18007a963  mov     [rsp+2E0h+cbData], r13d
0x18007a968  xor     r8d, r8d; lpReserved
0x18007a96b  mov     [rsp+2E0h+phkResult], rax; lpData
0x18007a970  lea     rdx, aEnablerecordfe; "EnableRecordFeatureMap"
0x18007a977  call    cs:__imp_RegQueryValueExW
0x18007a97d  test    eax, eax
0x18007a97f  jnz     short loc_18007A994
0x18007a981  cmp     [rsp+2E0h+Type], r13d
0x18007a986  jnz     short loc_18007A994
0x18007a988  cmp     dword ptr [rsp+2E0h+Data], eax
0x18007a98c  setnz   al
0x18007a98f  mov     [rbp+1E0h+var_258], eax
0x18007a992  or      ebx, eax
0x18007a994  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18007a999  lea     rax, [rsp+2E0h+cbData]
0x18007a99e  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18007a9a3  lea     r9, [rsp+2E0h+Type]; lpType
0x18007a9a8  lea     rax, [rsp+2E0h+Data]
0x18007a9ad  mov     [rsp+2E0h+cbData], r13d
0x18007a9b2  xor     r8d, r8d; lpReserved
0x18007a9b5  mov     [rsp+2E0h+phkResult], rax; lpData
0x18007a9ba  lea     rdx, aEnablerecordqp; "EnableRecordQPMap"
0x18007a9c1  call    cs:__imp_RegQueryValueExW
0x18007a9c7  test    eax, eax
0x18007a9c9  jnz     short loc_18007A9DE
0x18007a9cb  cmp     [rsp+2E0h+Type], r13d
0x18007a9d0  jnz     short loc_18007A9DE
0x18007a9d2  cmp     dword ptr [rsp+2E0h+Data], eax
0x18007a9d6  setnz   al
0x18007a9d9  mov     [rbp+1E0h+var_254], eax
0x18007a9dc  or      ebx, eax
0x18007a9de  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18007a9e3  lea     rax, [rsp+2E0h+cbData]
0x18007a9e8  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18007a9ed  lea     r9, [rsp+2E0h+Type]; lpType
0x18007a9f2  lea     rax, [rbp+1E0h+var_24C]
0x18007a9f6  mov     [rsp+2E0h+cbData], 208h
0x18007a9fe  xor     r8d, r8d; lpReserved
0x18007aa01  mov     [rsp+2E0h+phkResult], rax; lpData
0x18007aa06  lea     rdx, aRecordpath; "RecordPath"
0x18007aa0d  call    cs:__imp_RegQueryValueExW
0x18007aa13  test    eax, eax
0x18007aa15  jnz     short loc_18007AA2A
0x18007aa17  cmp     [rsp+2E0h+Type], 1
0x18007aa1c  jnz     short loc_18007AA2A
0x18007aa1e  mov     eax, [rsp+2E0h+cbData]
0x18007aa22  mov     [rbp+1E0h+var_44], eax
0x18007aa28  jmp     short loc_18007AA34
0x18007aa2a  mov     [rbp+1E0h+var_44], 0
0x18007aa34  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18007aa39  call    cs:__imp_RegCloseKey
0x18007aa3f  inc     cs:dword_1801BB4F0
0x18007aa45  cmp     [rbp+1E0h+var_44], 0
0x18007aa4c  jz      short loc_18007AA8B
0x18007aa4e  test    ebx, ebx
0x18007aa50  jz      short loc_18007AA8B
0x18007aa52  mov     ecx, 88h; Size
0x18007aa57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007aa5c  test    rax, rax
0x18007aa5f  jz      short loc_18007AA8B
0x18007aa61  mov     ecx, cs:dword_1801BB4F0
0x18007aa67  mov     r9d, r15d; int
0x18007aa6a  mov     [rsp+2E0h+var_2B0], ecx; int
0x18007aa6e  mov     r8d, r14d; int
0x18007aa71  lea     rcx, [rsp+2E0h+var_280]
0x18007aa76  mov     edx, esi; int
0x18007aa78  mov     [rsp+2E0h+lpcbData], rcx; struct RecordSettings *
0x18007aa7d  mov     rcx, rax; Stream
0x18007aa80  mov     dword ptr [rsp+2E0h+phkResult], edi; int
0x18007aa84  call    ??0OutputAvc@@QEAA@HHHHAEAURecordSettings@@H@Z; OutputAvc::OutputAvc(int,int,int,int,RecordSettings &,int)
0x18007aa89  jmp     short loc_18007AA8D
0x18007aa8b  xor     eax, eax
0x18007aa8d  mov     rcx, [rbp+1E0h+var_40]
0x18007aa94  xor     rcx, rsp; StackCookie
0x18007aa97  call    __security_check_cookie
0x18007aa9c  add     rsp, 2B0h
0x18007aaa3  pop     r15
0x18007aaa5  pop     r14
0x18007aaa7  pop     r13
0x18007aaa9  pop     rdi
0x18007aaaa  pop     rsi
0x18007aaab  pop     rbx
0x18007aaac  pop     rbp
0x18007aaad  retn
```
