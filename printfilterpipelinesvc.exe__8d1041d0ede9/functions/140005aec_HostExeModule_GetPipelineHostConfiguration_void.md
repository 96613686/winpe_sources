# HostExeModule::GetPipelineHostConfiguration(void)

- ea: `0x140005aec`
- end: `0x140005c74`
- name: `?GetPipelineHostConfiguration@HostExeModule@@AEAAJXZ`
- size: `392`
- prototype: `__int64 __fastcall(HostExeModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140007fb0`

## callees

- `0x140005aec`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140005c58`
- `ADVAPI32!RegCloseKey` at `0x140005c58`
- `ADVAPI32!RegOpenKeyExW` at `0x140005b22`
- `ADVAPI32!RegOpenKeyExW` at `0x140005b22`
- `ADVAPI32!RegQueryValueExW` at `0x140005b63`
- `ADVAPI32!RegQueryValueExW` at `0x140005baa`
- `ADVAPI32!RegQueryValueExW` at `0x140005bf3`
- `ADVAPI32!RegQueryValueExW` at `0x140005c3d`
- `ADVAPI32!RegQueryValueExW` at `0x140005b63`
- `ADVAPI32!RegQueryValueExW` at `0x140005baa`
- `ADVAPI32!RegQueryValueExW` at `0x140005bf3`
- `ADVAPI32!RegQueryValueExW` at `0x140005c3d`

## pseudocode

```c
__int64 __fastcall HostExeModule::GetPipelineHostConfiguration(HostExeModule *this)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  HostExeModule *Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  Data = this;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      return (unsigned __int16)v1 | 0x80070000;
  }
  else
  {
    LODWORD(Data) = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, (LPBYTE)&Data, &cbData) && !(_DWORD)Data )
      byte_140080E48 = 0;
    cbData = 4;
    LODWORD(Data) = 0;
    if ( !RegQueryValueExW(hKey, aPipelinehostti, 0, &Type, (LPBYTE)&Data, &cbData) && (_DWORD)Data )
      dwMilliseconds = (unsigned int)Data;
    cbData = 4;
    LODWORD(Data) = 0;
    if ( !RegQueryValueExW(hKey, aPipelinedebugl, 0, &Type, (LPBYTE)&Data, &cbData) && (_DWORD)Data )
      m_gbPipelineDebugLog = 1;
    cbData = 4;
    LODWORD(Data) = 0;
    if ( !RegQueryValueExW(hKey, aPipelinebuffer, 0, &Type, (LPBYTE)&Data, &cbData) && (_DWORD)Data )
      LODWORD(PrnSharedState::g_InternalBufferSize) = (_DWORD)Data;
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x140005aec  mov     [rsp-10h+Data], rcx
0x140005af1  push    rbp
0x140005af2  push    rbx
0x140005af3  mov     rbp, rsp
0x140005af6  sub     rsp, 38h
0x140005afa  lea     rax, [rbp+hKey]
0x140005afe  mov     [rbp+hKey], 0
0x140005b06  mov     r9d, 20019h; samDesired
0x140005b0c  mov     [rsp+38h+phkResult], rax; phkResult
0x140005b11  xor     r8d, r8d; ulOptions
0x140005b14  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Pri"...
0x140005b1b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005b22  call    cs:__imp_RegOpenKeyExW
0x140005b28  mov     ebx, eax
0x140005b2a  test    eax, eax
0x140005b2c  jnz     loc_140005C60
0x140005b32  mov     rcx, [rbp+hKey]; hKey
0x140005b36  lea     r9, [rbp+Type]; lpType
0x140005b3a  mov     dword ptr [rbp+Data], eax
0x140005b3d  lea     rdx, ValueName; "PipelineHostReuse"
0x140005b44  mov     [rbp+Type], eax
0x140005b47  xor     r8d, r8d; lpReserved
0x140005b4a  lea     rax, [rbp+cbData]
0x140005b4e  mov     [rbp+cbData], 4
0x140005b55  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140005b5a  lea     rax, [rbp+Data]
0x140005b5e  mov     [rsp+38h+phkResult], rax; lpData
0x140005b63  call    cs:__imp_RegQueryValueExW
0x140005b69  test    eax, eax
0x140005b6b  jnz     short loc_140005B78
0x140005b6d  cmp     dword ptr [rbp+Data], eax
0x140005b70  jnz     short loc_140005B78
0x140005b72  mov     cs:byte_140080E48, al
0x140005b78  mov     rcx, [rbp+hKey]; hKey
0x140005b7c  lea     rax, [rbp+cbData]
0x140005b80  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140005b85  lea     r9, [rbp+Type]; lpType
0x140005b89  lea     rax, [rbp+Data]
0x140005b8d  mov     [rbp+cbData], 4
0x140005b94  xor     r8d, r8d; lpReserved
0x140005b97  mov     [rsp+38h+phkResult], rax; lpData
0x140005b9c  lea     rdx, aPipelinehostti; "PipelineHostTimeout"
0x140005ba3  mov     dword ptr [rbp+Data], 0
0x140005baa  call    cs:__imp_RegQueryValueExW
0x140005bb0  test    eax, eax
0x140005bb2  jnz     short loc_140005BC1
0x140005bb4  mov     eax, dword ptr [rbp+Data]
0x140005bb7  test    eax, eax
0x140005bb9  jz      short loc_140005BC1
0x140005bbb  mov     cs:dwMilliseconds, eax
0x140005bc1  mov     rcx, [rbp+hKey]; hKey
0x140005bc5  lea     rax, [rbp+cbData]
0x140005bc9  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140005bce  lea     r9, [rbp+Type]; lpType
0x140005bd2  lea     rax, [rbp+Data]
0x140005bd6  mov     [rbp+cbData], 4
0x140005bdd  xor     r8d, r8d; lpReserved
0x140005be0  mov     [rsp+38h+phkResult], rax; lpData
0x140005be5  lea     rdx, aPipelinedebugl; "PipelineDebugLog"
0x140005bec  mov     dword ptr [rbp+Data], 0
0x140005bf3  call    cs:__imp_RegQueryValueExW
0x140005bf9  test    eax, eax
0x140005bfb  jnz     short loc_140005C0B
0x140005bfd  mov     eax, dword ptr [rbp+Data]
0x140005c00  test    eax, eax
0x140005c02  jz      short loc_140005C0B
0x140005c04  setnz   cs:?m_gbPipelineDebugLog@@3_NA; bool m_gbPipelineDebugLog
0x140005c0b  mov     rcx, [rbp+hKey]; hKey
0x140005c0f  lea     rax, [rbp+cbData]
0x140005c13  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140005c18  lea     r9, [rbp+Type]; lpType
0x140005c1c  lea     rax, [rbp+Data]
0x140005c20  mov     [rbp+cbData], 4
0x140005c27  xor     r8d, r8d; lpReserved
0x140005c2a  mov     [rsp+38h+phkResult], rax; lpData
0x140005c2f  lea     rdx, aPipelinebuffer; "PipelineBufferSize"
0x140005c36  mov     dword ptr [rbp+Data], 0
0x140005c3d  call    cs:__imp_RegQueryValueExW
0x140005c43  test    eax, eax
0x140005c45  jnz     short loc_140005C54
0x140005c47  mov     eax, dword ptr [rbp+Data]
0x140005c4a  test    eax, eax
0x140005c4c  jz      short loc_140005C54
0x140005c4e  mov     cs:?g_InternalBufferSize@PrnSharedState@@3KA, eax; ulong PrnSharedState::g_InternalBufferSize
0x140005c54  mov     rcx, [rbp+hKey]; hKey
0x140005c58  call    cs:__imp_RegCloseKey
0x140005c5e  jmp     short loc_140005C6B
0x140005c60  jle     short loc_140005C6B
0x140005c62  movzx   ebx, ax
0x140005c65  or      ebx, 80070000h
0x140005c6b  mov     eax, ebx
0x140005c6d  add     rsp, 38h
0x140005c71  pop     rbx
0x140005c72  pop     rbp
0x140005c73  retn
```
