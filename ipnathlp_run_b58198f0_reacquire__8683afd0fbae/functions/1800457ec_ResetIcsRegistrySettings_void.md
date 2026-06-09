# ResetIcsRegistrySettings(void)

- ea: `0x1800457ec`
- end: `0x1800459cf`
- name: `?ResetIcsRegistrySettings@@YAJXZ`
- size: `483`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074c04`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800457ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045865`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045865`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800458eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045946`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800458eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045946`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045986`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045986`

## string_xrefs

- `0x180045857`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

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
0x1800457ec  mov     [rsp+arg_10], rbx
0x1800457f1  push    rbp
0x1800457f2  push    rsi
0x1800457f3  push    rdi
0x1800457f4  sub     rsp, 30h
0x1800457f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800457ff  lea     rsi, WPP_GLOBAL_Control
0x180045806  lea     rbp, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004580d  mov     edi, 200h
0x180045812  cmp     rcx, rsi
0x180045815  jz      short loc_180045833
0x180045817  test    [rcx+1Ch], edi
0x18004581a  jz      short loc_180045833
0x18004581c  cmp     byte ptr [rcx+19h], 6
0x180045820  jb      short loc_180045833
0x180045822  mov     rcx, [rcx+10h]
0x180045826  mov     edx, 140h
0x18004582b  mov     r8, rbp
0x18004582e  call    WPP_SF_
0x180045833  lea     rax, [rsp+48h+hKey]
0x180045838  mov     [rsp+48h+Data], 0FFFFFFFFh
0x180045840  mov     r9d, 20006h; samDesired
0x180045846  mov     [rsp+48h+phkResult], rax; phkResult
0x18004584b  xor     r8d, r8d; ulOptions
0x18004584e  mov     [rsp+48h+hKey], 0
0x180045857  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004585e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045865  call    cs:__imp_RegOpenKeyExW
0x18004586c  nop     dword ptr [rax+rax+00h]
0x180045871  mov     ebx, eax
0x180045873  test    eax, eax
0x180045875  jz      short loc_1800458C6
0x180045877  jle     short loc_180045882
0x180045879  movzx   ebx, ax
0x18004587c  or      ebx, 80070000h
0x180045882  test    ebx, ebx
0x180045884  jns     loc_180045994
0x18004588a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045891  cmp     rcx, rsi
0x180045894  jz      loc_1800459BF
0x18004589a  test    [rcx+1Ch], edi
0x18004589d  jz      loc_18004599B
0x1800458a3  cmp     byte ptr [rcx+19h], 2
0x1800458a7  jb      loc_18004599B
0x1800458ad  mov     rcx, [rcx+10h]
0x1800458b1  mov     edx, 141h
0x1800458b6  mov     r9d, ebx
0x1800458b9  mov     r8, rbp
0x1800458bc  call    WPP_SF_d
0x1800458c1  jmp     loc_180045994
0x1800458c6  mov     rcx, [rsp+48h+hKey]; hKey
0x1800458cb  lea     rax, [rsp+48h+Data]
0x1800458d0  mov     ebx, 4
0x1800458d5  lea     rdx, aPublicindex; "PublicIndex"
0x1800458dc  mov     [rsp+48h+cbData], ebx; cbData
0x1800458e0  mov     r9d, ebx; dwType
0x1800458e3  xor     r8d, r8d; Reserved
0x1800458e6  mov     [rsp+48h+phkResult], rax; lpData
0x1800458eb  call    cs:__imp_RegSetValueExW
0x1800458f2  nop     dword ptr [rax+rax+00h]
0x1800458f7  test    eax, eax
0x1800458f9  jz      short loc_180045926
0x1800458fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180045902  cmp     rcx, rsi
0x180045905  jz      short loc_180045926
0x180045907  test    [rcx+1Ch], edi
0x18004590a  jz      short loc_180045926
0x18004590c  cmp     byte ptr [rcx+19h], 3
0x180045910  jb      short loc_180045926
0x180045912  mov     rcx, [rcx+10h]
0x180045916  mov     edx, 142h
0x18004591b  xor     r9d, r9d
0x18004591e  mov     r8, rbp
0x180045921  call    WPP_SF_d
0x180045926  mov     rcx, [rsp+48h+hKey]; hKey
0x18004592b  lea     rax, [rsp+48h+Data]
0x180045930  mov     [rsp+48h+cbData], ebx; cbData
0x180045934  lea     rdx, aPrivateindex; "PrivateIndex"
0x18004593b  mov     r9d, ebx; dwType
0x18004593e  mov     [rsp+48h+phkResult], rax; lpData
0x180045943  xor     r8d, r8d; Reserved
0x180045946  call    cs:__imp_RegSetValueExW
0x18004594d  nop     dword ptr [rax+rax+00h]
0x180045952  test    eax, eax
0x180045954  jz      short loc_180045981
0x180045956  mov     rcx, cs:WPP_GLOBAL_Control
0x18004595d  cmp     rcx, rsi
0x180045960  jz      short loc_180045981
0x180045962  test    [rcx+1Ch], edi
0x180045965  jz      short loc_180045981
0x180045967  cmp     byte ptr [rcx+19h], 3
0x18004596b  jb      short loc_180045981
0x18004596d  mov     rcx, [rcx+10h]
0x180045971  mov     edx, 143h
0x180045976  xor     r9d, r9d
0x180045979  mov     r8, rbp
0x18004597c  call    WPP_SF_d
0x180045981  mov     rcx, [rsp+48h+hKey]; hKey
0x180045986  call    cs:__imp_RegCloseKey
0x18004598d  nop     dword ptr [rax+rax+00h]
0x180045992  xor     ebx, ebx
0x180045994  mov     rcx, cs:WPP_GLOBAL_Control
0x18004599b  cmp     rcx, rsi
0x18004599e  jz      short loc_1800459BF
0x1800459a0  test    [rcx+1Ch], edi
0x1800459a3  jz      short loc_1800459BF
0x1800459a5  cmp     byte ptr [rcx+19h], 6
0x1800459a9  jb      short loc_1800459BF
0x1800459ab  mov     rcx, [rcx+10h]
0x1800459af  mov     edx, 144h
0x1800459b4  mov     r9d, ebx
0x1800459b7  mov     r8, rbp
0x1800459ba  call    WPP_SF_d
0x1800459bf  mov     eax, ebx
0x1800459c1  mov     rbx, [rsp+48h+arg_10]
0x1800459c6  add     rsp, 30h
0x1800459ca  pop     rdi
0x1800459cb  pop     rsi
0x1800459cc  pop     rbp
0x1800459cd  retn
```
