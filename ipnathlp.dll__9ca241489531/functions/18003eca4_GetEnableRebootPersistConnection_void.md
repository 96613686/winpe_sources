# GetEnableRebootPersistConnection(void)

- ea: `0x18003eca4`
- end: `0x18003ee54`
- name: `?GetEnableRebootPersistConnection@@YAHXZ`
- size: `432`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f0f8`
- `0x18006f33c`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000f250`
- `0x18003eb48`
- `0x18003eca4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ed9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ed9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ed23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ed23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003edc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003edc6`

## string_xrefs

- `0x18003ed0c`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`
- `0x18003ed59`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

## pseudocode

```c
__int64 GetEnableRebootPersistConnection(void)
{
  unsigned int v0; // edi
  LSTATUS v1; // eax
  signed int v2; // ebx
  PVOID *v3; // rcx
  PVOID v4; // rcx
  const char *v5; // r9
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 327, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  Data = 0;
  v0 = 0;
  cbData = 4;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess", 0, 1u, &hKey);
  v2 = v1;
  if ( !v1 )
  {
    v2 = 0;
    if ( !RegQueryValueExW(hKey, L"EnableRebootPersistConnection", 0, 0, (LPBYTE)&Data, &cbData) )
      LOBYTE(v0) = Data == 1;
    goto LABEL_15;
  }
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_15:
    v3 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      328,
      (unsigned int)&WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess",
      v2);
    goto LABEL_15;
  }
LABEL_16:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v3 = (PVOID *)WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( v3 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v3 + 7) & 0x200) != 0 && *((_BYTE *)v3 + 25) >= 4u )
    {
      v4 = v3[2];
      v5 = "TRUE";
      if ( !v0 )
        v5 = "FALSE";
      WPP_SF_s(v4, 329, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v5);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x200) != 0 && *((_BYTE *)v3 + 25) >= 6u )
      WPP_SF_d(v3[2], 330, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, (unsigned int)v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18003eca4  mov     [rsp+arg_18], rbx
0x18003eca9  push    rbp
0x18003ecaa  push    rdi
0x18003ecab  push    r14
0x18003ecad  sub     rsp, 30h
0x18003ecb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ecb8  lea     r14, WPP_GLOBAL_Control
0x18003ecbf  mov     ebp, 200h
0x18003ecc4  cmp     rcx, r14
0x18003ecc7  jz      short loc_18003ECE9
0x18003ecc9  test    [rcx+1Ch], ebp
0x18003eccc  jz      short loc_18003ECE9
0x18003ecce  cmp     byte ptr [rcx+19h], 6
0x18003ecd2  jb      short loc_18003ECE9
0x18003ecd4  mov     rcx, [rcx+10h]
0x18003ecd8  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003ecdf  mov     edx, 147h
0x18003ece4  call    WPP_SF_
0x18003ece9  lea     rax, [rsp+48h+hKey]
0x18003ecee  mov     [rsp+48h+Data], 0
0x18003ecf6  xor     edi, edi
0x18003ecf8  mov     [rsp+48h+cbData], 4
0x18003ed00  xor     r8d, r8d; ulOptions
0x18003ed03  mov     [rsp+48h+hKey], 0
0x18003ed0c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ed13  mov     [rsp+48h+phkResult], rax; phkResult
0x18003ed18  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ed1f  lea     r9d, [rdi+1]; samDesired
0x18003ed23  call    cs:__imp_RegOpenKeyExW
0x18003ed29  mov     ebx, eax
0x18003ed2b  test    eax, eax
0x18003ed2d  jz      short loc_18003ED77
0x18003ed2f  jle     short loc_18003ED3A
0x18003ed31  movzx   ebx, ax
0x18003ed34  or      ebx, 80070000h
0x18003ed3a  test    ebx, ebx
0x18003ed3c  jns     short loc_18003EDB2
0x18003ed3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ed45  cmp     rcx, r14
0x18003ed48  jz      short loc_18003EDB9
0x18003ed4a  test    [rcx+1Ch], ebp
0x18003ed4d  jz      short loc_18003EDB9
0x18003ed4f  cmp     byte ptr [rcx+19h], 2
0x18003ed53  jb      short loc_18003EDB9
0x18003ed55  mov     rcx, [rcx+10h]
0x18003ed59  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ed60  mov     edx, 148h
0x18003ed65  mov     dword ptr [rsp+48h+phkResult], ebx
0x18003ed69  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003ed70  call    WPP_SF_Sd
0x18003ed75  jmp     short loc_18003EDB2
0x18003ed77  mov     rcx, [rsp+48h+hKey]; hKey
0x18003ed7c  lea     rax, [rsp+48h+cbData]
0x18003ed81  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18003ed86  lea     rdx, aEnablerebootpe; "EnableRebootPersistConnection"
0x18003ed8d  lea     rax, [rsp+48h+Data]
0x18003ed92  xor     r9d, r9d; lpType
0x18003ed95  xor     r8d, r8d; lpReserved
0x18003ed98  mov     [rsp+48h+phkResult], rax; lpData
0x18003ed9d  xor     ebx, ebx
0x18003ed9f  call    cs:__imp_RegQueryValueExW
0x18003eda5  test    eax, eax
0x18003eda7  jnz     short loc_18003EDB2
0x18003eda9  cmp     [rsp+48h+Data], 1
0x18003edae  setz    dil
0x18003edb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003edb9  mov     rax, [rsp+48h+hKey]
0x18003edbe  test    rax, rax
0x18003edc1  jz      short loc_18003EDDC
0x18003edc3  mov     rcx, rax; hKey
0x18003edc6  call    cs:__imp_RegCloseKey
0x18003edcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003edd3  mov     [rsp+48h+hKey], 0
0x18003eddc  cmp     rcx, r14
0x18003eddf  jz      short loc_18003EE44
0x18003ede1  test    [rcx+1Ch], ebp
0x18003ede4  jz      short loc_18003EE1C
0x18003ede6  cmp     byte ptr [rcx+19h], 4
0x18003edea  jb      short loc_18003EE1C
0x18003edec  mov     rcx, [rcx+10h]
0x18003edf0  lea     rax, aFalse; "FALSE"
0x18003edf7  test    edi, edi
0x18003edf9  lea     r9, aTrue; "TRUE"
0x18003ee00  mov     edx, 149h
0x18003ee05  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003ee0c  cmovz   r9, rax
0x18003ee10  call    WPP_SF_s
0x18003ee15  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee1c  cmp     rcx, r14
0x18003ee1f  jz      short loc_18003EE44
0x18003ee21  test    [rcx+1Ch], ebp
0x18003ee24  jz      short loc_18003EE44
0x18003ee26  cmp     byte ptr [rcx+19h], 6
0x18003ee2a  jb      short loc_18003EE44
0x18003ee2c  mov     rcx, [rcx+10h]
0x18003ee30  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003ee37  mov     edx, 14Ah
0x18003ee3c  mov     r9d, ebx
0x18003ee3f  call    WPP_SF_d
0x18003ee44  mov     rbx, [rsp+48h+arg_18]
0x18003ee49  mov     eax, edi
0x18003ee4b  add     rsp, 30h
0x18003ee4f  pop     r14
0x18003ee51  pop     rdi
0x18003ee52  pop     rbp
0x18003ee53  retn
```
