# _anonymous_namespace_::CreateCompressorOutputAvc_0

- ea: `0x18008d930`
- end: `0x18008dbb6`
- name: `_anonymous_namespace_::CreateCompressorOutputAvc_0`
- size: `646`
- prototype: `__int64 __fastcall(int, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008f990`

## callees

- `0x180033964`
- `0x180033da0`
- `0x180034970`
- `0x18008d930`
- `0x1800d8f18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008d9eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008da34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008da7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008dac9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008db15`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008d9eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008da34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008da7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008dac9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008db15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008db41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008db41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008d9a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008d9a4`

## string_xrefs

- `0x18008db0e`: `RecordPath`
- `0x18008d996`: `Software\Policies\Microsoft\Windows NT\Terminal Services\HevcEncoding`

## pseudocode

```c
OutputAvc *__fastcall anonymous_namespace_::CreateCompressorOutputAvc_0(int a1, int a2, int a3, int a4)
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
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\HevcEncoding",
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
  ++dword_1801BB510;
  if ( v24 && v8 && (v12 = (FILE **)operator new(0x88u)) != 0 )
    return OutputAvc::OutputAvc(v12, a1, a2, a3, a4, (struct RecordSettings *)v18, dword_1801BB510);
  else
    return 0;
}

```

## disassembly

```asm
0x18008d930  push    rbp
0x18008d932  push    rbx
0x18008d933  push    rsi
0x18008d934  push    rdi
0x18008d935  push    r13
0x18008d937  push    r14
0x18008d939  push    r15
0x18008d93b  lea     rbp, [rsp-1B0h]
0x18008d943  sub     rsp, 2B0h
0x18008d94a  mov     rax, cs:__security_cookie
0x18008d951  xor     rax, rsp
0x18008d954  mov     [rbp+1E0h+var_40], rax
0x18008d95b  mov     r15d, r8d
0x18008d95e  mov     [rsp+2E0h+hKey], 0
0x18008d967  mov     r14d, edx
0x18008d96a  mov     esi, ecx
0x18008d96c  xor     edx, edx; Val
0x18008d96e  lea     rcx, [rsp+2E0h+var_280]; void *
0x18008d973  mov     r8d, 240h; Size
0x18008d979  mov     edi, r9d
0x18008d97c  xor     ebx, ebx
0x18008d97e  call    memset_0
0x18008d983  lea     rax, [rsp+2E0h+hKey]
0x18008d988  mov     r9d, 20019h; samDesired
0x18008d98e  xor     r8d, r8d; ulOptions
0x18008d991  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18008d996  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18008d99d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008d9a4  call    cs:__imp_RegOpenKeyExW
0x18008d9aa  test    eax, eax
0x18008d9ac  jnz     loc_18008DB47
0x18008d9b2  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18008d9b7  lea     rax, [rsp+2E0h+cbData]
0x18008d9bc  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18008d9c1  lea     r13d, [rbx+4]
0x18008d9c5  lea     rax, [rsp+2E0h+Data]
0x18008d9ca  mov     dword ptr [rsp+2E0h+Data], ebx
0x18008d9ce  lea     r9, [rsp+2E0h+Type]; lpType
0x18008d9d3  mov     [rsp+2E0h+phkResult], rax; lpData
0x18008d9d8  xor     r8d, r8d; lpReserved
0x18008d9db  mov     [rsp+2E0h+Type], ebx
0x18008d9df  lea     rdx, aEnablerecordrg; "EnableRecordRGB"
0x18008d9e6  mov     [rsp+2E0h+cbData], r13d
0x18008d9eb  call    cs:__imp_RegQueryValueExW
0x18008d9f1  test    eax, eax
0x18008d9f3  jnz     short loc_18008DA07
0x18008d9f5  cmp     [rsp+2E0h+Type], r13d
0x18008d9fa  jnz     short loc_18008DA07
0x18008d9fc  cmp     dword ptr [rsp+2E0h+Data], ebx
0x18008da00  setnz   bl
0x18008da03  mov     [rsp+2E0h+var_274], ebx
0x18008da07  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18008da0c  lea     rax, [rsp+2E0h+cbData]
0x18008da11  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18008da16  lea     r9, [rsp+2E0h+Type]; lpType
0x18008da1b  lea     rax, [rsp+2E0h+Data]
0x18008da20  mov     [rsp+2E0h+cbData], r13d
0x18008da25  xor     r8d, r8d; lpReserved
0x18008da28  mov     [rsp+2E0h+phkResult], rax; lpData
0x18008da2d  lea     rdx, aEnablerecordrd; "EnableRecordRdp264"
0x18008da34  call    cs:__imp_RegQueryValueExW
0x18008da3a  test    eax, eax
0x18008da3c  jnz     short loc_18008DA52
0x18008da3e  cmp     [rsp+2E0h+Type], r13d
0x18008da43  jnz     short loc_18008DA52
0x18008da45  cmp     dword ptr [rsp+2E0h+Data], eax
0x18008da49  setnz   al
0x18008da4c  mov     [rsp+2E0h+var_268], eax
0x18008da50  or      ebx, eax
0x18008da52  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18008da57  lea     rax, [rsp+2E0h+cbData]
0x18008da5c  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18008da61  lea     r9, [rsp+2E0h+Type]; lpType
0x18008da66  lea     rax, [rsp+2E0h+Data]
0x18008da6b  mov     [rsp+2E0h+cbData], r13d
0x18008da70  xor     r8d, r8d; lpReserved
0x18008da73  mov     [rsp+2E0h+phkResult], rax; lpData
0x18008da78  lea     rdx, aEnablerecordfe; "EnableRecordFeatureMap"
0x18008da7f  call    cs:__imp_RegQueryValueExW
0x18008da85  test    eax, eax
0x18008da87  jnz     short loc_18008DA9C
0x18008da89  cmp     [rsp+2E0h+Type], r13d
0x18008da8e  jnz     short loc_18008DA9C
0x18008da90  cmp     dword ptr [rsp+2E0h+Data], eax
0x18008da94  setnz   al
0x18008da97  mov     [rbp+1E0h+var_258], eax
0x18008da9a  or      ebx, eax
0x18008da9c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18008daa1  lea     rax, [rsp+2E0h+cbData]
0x18008daa6  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18008daab  lea     r9, [rsp+2E0h+Type]; lpType
0x18008dab0  lea     rax, [rsp+2E0h+Data]
0x18008dab5  mov     [rsp+2E0h+cbData], r13d
0x18008daba  xor     r8d, r8d; lpReserved
0x18008dabd  mov     [rsp+2E0h+phkResult], rax; lpData
0x18008dac2  lea     rdx, aEnablerecordqp; "EnableRecordQPMap"
0x18008dac9  call    cs:__imp_RegQueryValueExW
0x18008dacf  test    eax, eax
0x18008dad1  jnz     short loc_18008DAE6
0x18008dad3  cmp     [rsp+2E0h+Type], r13d
0x18008dad8  jnz     short loc_18008DAE6
0x18008dada  cmp     dword ptr [rsp+2E0h+Data], eax
0x18008dade  setnz   al
0x18008dae1  mov     [rbp+1E0h+var_254], eax
0x18008dae4  or      ebx, eax
0x18008dae6  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18008daeb  lea     rax, [rsp+2E0h+cbData]
0x18008daf0  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18008daf5  lea     r9, [rsp+2E0h+Type]; lpType
0x18008dafa  lea     rax, [rbp+1E0h+var_24C]
0x18008dafe  mov     [rsp+2E0h+cbData], 208h
0x18008db06  xor     r8d, r8d; lpReserved
0x18008db09  mov     [rsp+2E0h+phkResult], rax; lpData
0x18008db0e  lea     rdx, aRecordpath; "RecordPath"
0x18008db15  call    cs:__imp_RegQueryValueExW
0x18008db1b  test    eax, eax
0x18008db1d  jnz     short loc_18008DB32
0x18008db1f  cmp     [rsp+2E0h+Type], 1
0x18008db24  jnz     short loc_18008DB32
0x18008db26  mov     eax, [rsp+2E0h+cbData]
0x18008db2a  mov     [rbp+1E0h+var_44], eax
0x18008db30  jmp     short loc_18008DB3C
0x18008db32  mov     [rbp+1E0h+var_44], 0
0x18008db3c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18008db41  call    cs:__imp_RegCloseKey
0x18008db47  inc     cs:dword_1801BB510
0x18008db4d  cmp     [rbp+1E0h+var_44], 0
0x18008db54  jz      short loc_18008DB93
0x18008db56  test    ebx, ebx
0x18008db58  jz      short loc_18008DB93
0x18008db5a  mov     ecx, 88h; Size
0x18008db5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008db64  test    rax, rax
0x18008db67  jz      short loc_18008DB93
0x18008db69  mov     ecx, cs:dword_1801BB510
0x18008db6f  mov     r9d, r15d; int
0x18008db72  mov     [rsp+2E0h+var_2B0], ecx; int
0x18008db76  mov     r8d, r14d; int
0x18008db79  lea     rcx, [rsp+2E0h+var_280]
0x18008db7e  mov     edx, esi; int
0x18008db80  mov     [rsp+2E0h+lpcbData], rcx; struct RecordSettings *
0x18008db85  mov     rcx, rax; Stream
0x18008db88  mov     dword ptr [rsp+2E0h+phkResult], edi; int
0x18008db8c  call    ??0OutputAvc@@QEAA@HHHHAEAURecordSettings@@H@Z; OutputAvc::OutputAvc(int,int,int,int,RecordSettings &,int)
0x18008db91  jmp     short loc_18008DB95
0x18008db93  xor     eax, eax
0x18008db95  mov     rcx, [rbp+1E0h+var_40]
0x18008db9c  xor     rcx, rsp; StackCookie
0x18008db9f  call    __security_check_cookie
0x18008dba4  add     rsp, 2B0h
0x18008dbab  pop     r15
0x18008dbad  pop     r14
0x18008dbaf  pop     r13
0x18008dbb1  pop     rdi
0x18008dbb2  pop     rsi
0x18008dbb3  pop     rbx
0x18008dbb4  pop     rbp
0x18008dbb5  retn
```
