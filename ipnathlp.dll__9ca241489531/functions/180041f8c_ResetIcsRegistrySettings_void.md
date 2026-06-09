# ResetIcsRegistrySettings(void)

- ea: `0x180041f8c`
- end: `0x180042156`
- name: `?ResetIcsRegistrySettings@@YAJXZ`
- size: `458`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006f33c`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180041f8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042005`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042005`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042085`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800420da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042085`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800420da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042114`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042114`

## string_xrefs

- `0x180041ff7`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

## pseudocode

```c
__int64 ResetIcsRegistrySettings(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  PVOID *v2; // rcx
  int Data; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 320, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  Data = -1;
  hKey = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess",
         0,
         0x20006u,
         &hKey);
  v1 = v0;
  if ( !v0 )
  {
    if ( RegSetValueExW(hKey, L"PublicIndex", 0, 4u, (const BYTE *)&Data, 4u)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, 0);
    }
    if ( RegSetValueExW(hKey, L"PrivateIndex", 0, 4u, (const BYTE *)&Data, 4u)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 323, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, 0);
    }
    RegCloseKey(hKey);
    v1 = 0;
    goto LABEL_24;
  }
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( (v1 & 0x80000000) == 0 )
  {
LABEL_24:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v1);
    goto LABEL_24;
  }
LABEL_25:
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x200) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 324, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180041f8c  mov     [rsp+arg_10], rbx
0x180041f91  push    rbp
0x180041f92  push    rsi
0x180041f93  push    rdi
0x180041f94  sub     rsp, 30h
0x180041f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f9f  lea     rsi, WPP_GLOBAL_Control
0x180041fa6  lea     rbp, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180041fad  mov     edi, 200h
0x180041fb2  cmp     rcx, rsi
0x180041fb5  jz      short loc_180041FD3
0x180041fb7  test    [rcx+1Ch], edi
0x180041fba  jz      short loc_180041FD3
0x180041fbc  cmp     byte ptr [rcx+19h], 6
0x180041fc0  jb      short loc_180041FD3
0x180041fc2  mov     rcx, [rcx+10h]
0x180041fc6  mov     edx, 140h
0x180041fcb  mov     r8, rbp
0x180041fce  call    WPP_SF_
0x180041fd3  lea     rax, [rsp+48h+hKey]
0x180041fd8  mov     [rsp+48h+Data], 0FFFFFFFFh
0x180041fe0  mov     r9d, 20006h; samDesired
0x180041fe6  mov     [rsp+48h+phkResult], rax; phkResult
0x180041feb  xor     r8d, r8d; ulOptions
0x180041fee  mov     [rsp+48h+hKey], 0
0x180041ff7  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180041ffe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042005  call    cs:__imp_RegOpenKeyExW
0x18004200b  mov     ebx, eax
0x18004200d  test    eax, eax
0x18004200f  jz      short loc_180042060
0x180042011  jle     short loc_18004201C
0x180042013  movzx   ebx, ax
0x180042016  or      ebx, 80070000h
0x18004201c  test    ebx, ebx
0x18004201e  jns     loc_18004211C
0x180042024  mov     rcx, cs:WPP_GLOBAL_Control
0x18004202b  cmp     rcx, rsi
0x18004202e  jz      loc_180042147
0x180042034  test    [rcx+1Ch], edi
0x180042037  jz      loc_180042123
0x18004203d  cmp     byte ptr [rcx+19h], 2
0x180042041  jb      loc_180042123
0x180042047  mov     rcx, [rcx+10h]
0x18004204b  mov     edx, 141h
0x180042050  mov     r9d, ebx
0x180042053  mov     r8, rbp
0x180042056  call    WPP_SF_d
0x18004205b  jmp     loc_18004211C
0x180042060  mov     rcx, [rsp+48h+hKey]; hKey
0x180042065  lea     rax, [rsp+48h+Data]
0x18004206a  mov     ebx, 4
0x18004206f  lea     rdx, aPublicindex; "PublicIndex"
0x180042076  mov     [rsp+48h+cbData], ebx; cbData
0x18004207a  mov     r9d, ebx; dwType
0x18004207d  xor     r8d, r8d; Reserved
0x180042080  mov     [rsp+48h+phkResult], rax; lpData
0x180042085  call    cs:__imp_RegSetValueExW
0x18004208b  test    eax, eax
0x18004208d  jz      short loc_1800420BA
0x18004208f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042096  cmp     rcx, rsi
0x180042099  jz      short loc_1800420BA
0x18004209b  test    [rcx+1Ch], edi
0x18004209e  jz      short loc_1800420BA
0x1800420a0  cmp     byte ptr [rcx+19h], 3
0x1800420a4  jb      short loc_1800420BA
0x1800420a6  mov     rcx, [rcx+10h]
0x1800420aa  mov     edx, 142h
0x1800420af  xor     r9d, r9d
0x1800420b2  mov     r8, rbp
0x1800420b5  call    WPP_SF_d
0x1800420ba  mov     rcx, [rsp+48h+hKey]; hKey
0x1800420bf  lea     rax, [rsp+48h+Data]
0x1800420c4  mov     [rsp+48h+cbData], ebx; cbData
0x1800420c8  lea     rdx, aPrivateindex; "PrivateIndex"
0x1800420cf  mov     r9d, ebx; dwType
0x1800420d2  mov     [rsp+48h+phkResult], rax; lpData
0x1800420d7  xor     r8d, r8d; Reserved
0x1800420da  call    cs:__imp_RegSetValueExW
0x1800420e0  test    eax, eax
0x1800420e2  jz      short loc_18004210F
0x1800420e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800420eb  cmp     rcx, rsi
0x1800420ee  jz      short loc_18004210F
0x1800420f0  test    [rcx+1Ch], edi
0x1800420f3  jz      short loc_18004210F
0x1800420f5  cmp     byte ptr [rcx+19h], 3
0x1800420f9  jb      short loc_18004210F
0x1800420fb  mov     rcx, [rcx+10h]
0x1800420ff  mov     edx, 143h
0x180042104  xor     r9d, r9d
0x180042107  mov     r8, rbp
0x18004210a  call    WPP_SF_d
0x18004210f  mov     rcx, [rsp+48h+hKey]; hKey
0x180042114  call    cs:__imp_RegCloseKey
0x18004211a  xor     ebx, ebx
0x18004211c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042123  cmp     rcx, rsi
0x180042126  jz      short loc_180042147
0x180042128  test    [rcx+1Ch], edi
0x18004212b  jz      short loc_180042147
0x18004212d  cmp     byte ptr [rcx+19h], 6
0x180042131  jb      short loc_180042147
0x180042133  mov     rcx, [rcx+10h]
0x180042137  mov     edx, 144h
0x18004213c  mov     r9d, ebx
0x18004213f  mov     r8, rbp
0x180042142  call    WPP_SF_d
0x180042147  mov     eax, ebx
0x180042149  mov     rbx, [rsp+48h+arg_10]
0x18004214e  add     rsp, 30h
0x180042152  pop     rdi
0x180042153  pop     rsi
0x180042154  pop     rbp
0x180042155  retn
```
