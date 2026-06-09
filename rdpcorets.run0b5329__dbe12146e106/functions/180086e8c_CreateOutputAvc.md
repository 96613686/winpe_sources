# CreateOutputAvc

- ea: `0x180086e8c`
- end: `0x1800871a3`
- name: `CreateOutputAvc`
- size: `791`
- prototype: `__int64 __fastcall(int, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180089330`

## callees

- `0x180033964`
- `0x180033da0`
- `0x180034970`
- `0x180086e8c`
- `0x1800d8f18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180086f47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180086f90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180086fdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087026`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087071`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800870b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087102`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180086f47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180086f90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180086fdb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087026`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087071`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800870b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087102`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008712e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008712e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086f00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086f00`

## string_xrefs

- `0x180086ef2`: `Software\Policies\Microsoft\Windows NT\Terminal Services\H264Encoding`
- `0x1800870fb`: `RecordPath`

## pseudocode

```c
OutputAvc *__fastcall CreateOutputAvc(int a1, int a2, int a3, int a4)
{
  int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  FILE **v14; // rax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+64h] [rbp-9Ch]
  LSTATUS v22; // [rsp+68h] [rbp-98h]
  LSTATUS v23; // [rsp+74h] [rbp-8Ch]
  LSTATUS v24; // [rsp+7Ch] [rbp-84h]
  LSTATUS v25; // [rsp+80h] [rbp-80h]
  LSTATUS v26; // [rsp+84h] [rbp-7Ch]
  BYTE v27[520]; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD v28; // [rsp+29Ch] [rbp+19Ch]

  hKey = 0;
  v8 = 0;
  memset_0(v20, 0, 0x240u);
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
    if ( !RegQueryValueExW(hKey, L"EnableRecord264", 0, &Type, Data, &cbData) && Type == 4 )
    {
      LOBYTE(v8) = *(_DWORD *)Data != 0;
      v21 = v8;
    }
    cbData = 4;
    v9 = RegQueryValueExW(hKey, L"EnableRecordYUV", 0, &Type, Data, &cbData);
    if ( !v9 && Type == 4 )
    {
      LOBYTE(v9) = *(_DWORD *)Data != 0;
      v22 = v9;
      v8 |= v9;
    }
    cbData = 4;
    v10 = RegQueryValueExW(hKey, L"Enable264Log", 0, &Type, Data, &cbData);
    if ( !v10 && Type == 4 )
    {
      LOBYTE(v10) = *(_DWORD *)Data != 0;
      v23 = v10;
      v8 |= v10;
    }
    cbData = 4;
    v11 = RegQueryValueExW(hKey, L"EnableAvcSourceDump", 0, &Type, Data, &cbData);
    if ( !v11 && Type == 4 )
    {
      LOBYTE(v11) = *(_DWORD *)Data != 0;
      v24 = v11;
      v8 |= v11;
    }
    cbData = 4;
    v12 = RegQueryValueExW(hKey, L"EnableAvcRefDump", 0, &Type, Data, &cbData);
    if ( !v12 && Type == 4 )
    {
      LOBYTE(v12) = *(_DWORD *)Data != 0;
      v25 = v12;
      v8 |= v12;
    }
    v13 = RegQueryValueExW(hKey, L"EnableAvcReconDump", 0, &Type, Data, &cbData);
    if ( !v13 && Type == 4 )
    {
      LOBYTE(v13) = *(_DWORD *)Data != 0;
      v26 = v13;
      v8 |= v13;
    }
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"RecordPath", 0, &Type, v27, &cbData) || Type != 1 )
      v28 = 0;
    else
      v28 = cbData;
    RegCloseKey(hKey);
  }
  ++g_idx;
  if ( v28 && v8 && (v14 = (FILE **)operator new(0x88u)) != 0 )
    return OutputAvc::OutputAvc(v14, a1, a2, a3, a4, (struct RecordSettings *)v20, g_idx);
  else
    return 0;
}

```

## disassembly

```asm
0x180086e8c  push    rbp
0x180086e8e  push    rbx
0x180086e8f  push    rsi
0x180086e90  push    rdi
0x180086e91  push    r13
0x180086e93  push    r14
0x180086e95  push    r15
0x180086e97  lea     rbp, [rsp-1B0h]
0x180086e9f  sub     rsp, 2B0h
0x180086ea6  mov     rax, cs:__security_cookie
0x180086ead  xor     rax, rsp
0x180086eb0  mov     [rbp+1E0h+var_40], rax
0x180086eb7  mov     r15d, r8d
0x180086eba  mov     [rsp+2E0h+hKey], 0
0x180086ec3  mov     r14d, edx
0x180086ec6  mov     esi, ecx
0x180086ec8  xor     edx, edx; Val
0x180086eca  lea     rcx, [rsp+2E0h+var_280]; void *
0x180086ecf  mov     r8d, 240h; Size
0x180086ed5  mov     edi, r9d
0x180086ed8  xor     ebx, ebx
0x180086eda  call    memset_0
0x180086edf  lea     rax, [rsp+2E0h+hKey]
0x180086ee4  mov     r9d, 20019h; samDesired
0x180086eea  xor     r8d, r8d; ulOptions
0x180086eed  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180086ef2  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows "...
0x180086ef9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180086f00  call    cs:__imp_RegOpenKeyExW
0x180086f06  test    eax, eax
0x180086f08  jnz     loc_180087134
0x180086f0e  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180086f13  lea     rax, [rsp+2E0h+cbData]
0x180086f18  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180086f1d  lea     r13d, [rbx+4]
0x180086f21  lea     rax, [rsp+2E0h+Data]
0x180086f26  mov     dword ptr [rsp+2E0h+Data], ebx
0x180086f2a  lea     r9, [rsp+2E0h+Type]; lpType
0x180086f2f  mov     [rsp+2E0h+phkResult], rax; lpData
0x180086f34  xor     r8d, r8d; lpReserved
0x180086f37  mov     [rsp+2E0h+Type], ebx
0x180086f3b  lea     rdx, aEnablerecord26; "EnableRecord264"
0x180086f42  mov     [rsp+2E0h+cbData], r13d
0x180086f47  call    cs:__imp_RegQueryValueExW
0x180086f4d  test    eax, eax
0x180086f4f  jnz     short loc_180086F63
0x180086f51  cmp     [rsp+2E0h+Type], r13d
0x180086f56  jnz     short loc_180086F63
0x180086f58  cmp     dword ptr [rsp+2E0h+Data], ebx
0x180086f5c  setnz   bl
0x180086f5f  mov     [rsp+2E0h+var_27C], ebx
0x180086f63  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180086f68  lea     rax, [rsp+2E0h+cbData]
0x180086f6d  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180086f72  lea     r9, [rsp+2E0h+Type]; lpType
0x180086f77  lea     rax, [rsp+2E0h+Data]
0x180086f7c  mov     [rsp+2E0h+cbData], r13d
0x180086f81  xor     r8d, r8d; lpReserved
0x180086f84  mov     [rsp+2E0h+phkResult], rax; lpData
0x180086f89  lea     rdx, aEnablerecordyu; "EnableRecordYUV"
0x180086f90  call    cs:__imp_RegQueryValueExW
0x180086f96  test    eax, eax
0x180086f98  jnz     short loc_180086FAE
0x180086f9a  cmp     [rsp+2E0h+Type], r13d
0x180086f9f  jnz     short loc_180086FAE
0x180086fa1  cmp     dword ptr [rsp+2E0h+Data], eax
0x180086fa5  setnz   al
0x180086fa8  mov     [rsp+2E0h+var_278], eax
0x180086fac  or      ebx, eax
0x180086fae  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180086fb3  lea     rax, [rsp+2E0h+cbData]
0x180086fb8  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180086fbd  lea     r9, [rsp+2E0h+Type]; lpType
0x180086fc2  lea     rax, [rsp+2E0h+Data]
0x180086fc7  mov     [rsp+2E0h+cbData], r13d
0x180086fcc  xor     r8d, r8d; lpReserved
0x180086fcf  mov     [rsp+2E0h+phkResult], rax; lpData
0x180086fd4  lea     rdx, aEnable264log; "Enable264Log"
0x180086fdb  call    cs:__imp_RegQueryValueExW
0x180086fe1  test    eax, eax
0x180086fe3  jnz     short loc_180086FF9
0x180086fe5  cmp     [rsp+2E0h+Type], r13d
0x180086fea  jnz     short loc_180086FF9
0x180086fec  cmp     dword ptr [rsp+2E0h+Data], eax
0x180086ff0  setnz   al
0x180086ff3  mov     [rsp+2E0h+var_26C], eax
0x180086ff7  or      ebx, eax
0x180086ff9  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180086ffe  lea     rax, [rsp+2E0h+cbData]
0x180087003  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180087008  lea     r9, [rsp+2E0h+Type]; lpType
0x18008700d  lea     rax, [rsp+2E0h+Data]
0x180087012  mov     [rsp+2E0h+cbData], r13d
0x180087017  xor     r8d, r8d; lpReserved
0x18008701a  mov     [rsp+2E0h+phkResult], rax; lpData
0x18008701f  lea     rdx, aEnableavcsourc; "EnableAvcSourceDump"
0x180087026  call    cs:__imp_RegQueryValueExW
0x18008702c  test    eax, eax
0x18008702e  jnz     short loc_180087044
0x180087030  cmp     [rsp+2E0h+Type], r13d
0x180087035  jnz     short loc_180087044
0x180087037  cmp     dword ptr [rsp+2E0h+Data], eax
0x18008703b  setnz   al
0x18008703e  mov     [rsp+2E0h+var_264], eax
0x180087042  or      ebx, eax
0x180087044  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180087049  lea     rax, [rsp+2E0h+cbData]
0x18008704e  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180087053  lea     r9, [rsp+2E0h+Type]; lpType
0x180087058  lea     rax, [rsp+2E0h+Data]
0x18008705d  mov     [rsp+2E0h+cbData], r13d
0x180087062  xor     r8d, r8d; lpReserved
0x180087065  mov     [rsp+2E0h+phkResult], rax; lpData
0x18008706a  lea     rdx, aEnableavcrefdu; "EnableAvcRefDump"
0x180087071  call    cs:__imp_RegQueryValueExW
0x180087077  test    eax, eax
0x180087079  jnz     short loc_18008708E
0x18008707b  cmp     [rsp+2E0h+Type], r13d
0x180087080  jnz     short loc_18008708E
0x180087082  cmp     dword ptr [rsp+2E0h+Data], eax
0x180087086  setnz   al
0x180087089  mov     [rbp+1E0h+var_260], eax
0x18008708c  or      ebx, eax
0x18008708e  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180087093  lea     rax, [rsp+2E0h+cbData]
0x180087098  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18008709d  lea     r9, [rsp+2E0h+Type]; lpType
0x1800870a2  lea     rax, [rsp+2E0h+Data]
0x1800870a7  xor     r8d, r8d; lpReserved
0x1800870aa  lea     rdx, aEnableavcrecon; "EnableAvcReconDump"
0x1800870b1  mov     [rsp+2E0h+phkResult], rax; lpData
0x1800870b6  call    cs:__imp_RegQueryValueExW
0x1800870bc  test    eax, eax
0x1800870be  jnz     short loc_1800870D3
0x1800870c0  cmp     [rsp+2E0h+Type], r13d
0x1800870c5  jnz     short loc_1800870D3
0x1800870c7  cmp     dword ptr [rsp+2E0h+Data], eax
0x1800870cb  setnz   al
0x1800870ce  mov     [rbp+1E0h+var_25C], eax
0x1800870d1  or      ebx, eax
0x1800870d3  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800870d8  lea     rax, [rsp+2E0h+cbData]
0x1800870dd  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800870e2  lea     r9, [rsp+2E0h+Type]; lpType
0x1800870e7  lea     rax, [rbp+1E0h+var_24C]
0x1800870eb  mov     [rsp+2E0h+cbData], 208h
0x1800870f3  xor     r8d, r8d; lpReserved
0x1800870f6  mov     [rsp+2E0h+phkResult], rax; lpData
0x1800870fb  lea     rdx, aRecordpath; "RecordPath"
0x180087102  call    cs:__imp_RegQueryValueExW
0x180087108  test    eax, eax
0x18008710a  jnz     short loc_18008711F
0x18008710c  cmp     [rsp+2E0h+Type], 1
0x180087111  jnz     short loc_18008711F
0x180087113  mov     eax, [rsp+2E0h+cbData]
0x180087117  mov     [rbp+1E0h+var_44], eax
0x18008711d  jmp     short loc_180087129
0x18008711f  mov     [rbp+1E0h+var_44], 0
0x180087129  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18008712e  call    cs:__imp_RegCloseKey
0x180087134  inc     cs:?g_idx@@3HA; int g_idx
0x18008713a  cmp     [rbp+1E0h+var_44], 0
0x180087141  jz      short loc_180087180
0x180087143  test    ebx, ebx
0x180087145  jz      short loc_180087180
0x180087147  mov     ecx, 88h; Size
0x18008714c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180087151  test    rax, rax
0x180087154  jz      short loc_180087180
0x180087156  mov     ecx, cs:?g_idx@@3HA; int g_idx
0x18008715c  mov     r9d, r15d; int
0x18008715f  mov     [rsp+2E0h+var_2B0], ecx; int
0x180087163  mov     r8d, r14d; int
0x180087166  lea     rcx, [rsp+2E0h+var_280]
0x18008716b  mov     edx, esi; int
0x18008716d  mov     [rsp+2E0h+lpcbData], rcx; struct RecordSettings *
0x180087172  mov     rcx, rax; Stream
0x180087175  mov     dword ptr [rsp+2E0h+phkResult], edi; int
0x180087179  call    ??0OutputAvc@@QEAA@HHHHAEAURecordSettings@@H@Z; OutputAvc::OutputAvc(int,int,int,int,RecordSettings &,int)
0x18008717e  jmp     short loc_180087182
0x180087180  xor     eax, eax
0x180087182  mov     rcx, [rbp+1E0h+var_40]
0x180087189  xor     rcx, rsp; StackCookie
0x18008718c  call    __security_check_cookie
0x180087191  add     rsp, 2B0h
0x180087198  pop     r15
0x18008719a  pop     r14
0x18008719c  pop     r13
0x18008719e  pop     rdi
0x18008719f  pop     rsi
0x1800871a0  pop     rbx
0x1800871a1  pop     rbp
0x1800871a2  retn
```
