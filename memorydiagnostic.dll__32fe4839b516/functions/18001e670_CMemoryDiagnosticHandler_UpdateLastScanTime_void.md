# CMemoryDiagnosticHandler::UpdateLastScanTime(void)

- ea: `0x18001e670`
- end: `0x18001e7f6`
- name: `?UpdateLastScanTime@CMemoryDiagnosticHandler@@AEAAJXZ`
- size: `390`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ead0`

## callees

- `0x18001e670`
- `0x18001f594`
- `0x18001f5dc`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001e694`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001e694`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e6f0`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e6f0`
- `ADVAPI32!RegSetValueExW` at `0x18001e732`
- `ADVAPI32!RegSetValueExW` at `0x18001e732`
- `ADVAPI32!RegCloseKey` at `0x18001e7b5`
- `ADVAPI32!RegCloseKey` at `0x18001e7b5`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::UpdateLastScanTime(CMemoryDiagnosticHandler *this)
{
  unsigned int v1; // ebx
  __int64 v2; // r8
  LSTATUS v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  LSTATUS v6; // eax
  CMemoryDiagnosticHandler *v7; // rcx
  __int64 v8; // rdx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  struct _FILETIME v11; // [rsp+48h] [rbp+10h] BYREF
  struct _FILETIME Data; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v1 = 0;
  v11 = 0;
  Data.dwHighDateTime = 0;
  GetSystemTimeAsFileTime(&v11);
  Data = v11;
  if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_P)(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, v2, v11);
  }
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MemoryDiagnostic", 0, 2u, &hKey);
  v5 = (unsigned int)v3;
  if ( v3 )
  {
    if ( v3 > 0 )
    {
      v1 = (unsigned __int16)v3 | 0x80070000;
      goto LABEL_16;
    }
  }
  else if ( hKey )
  {
    v6 = RegSetValueExW(hKey, L"LastScanTime", 0, 0xBu, (const BYTE *)&Data, 8u);
    if ( !v6 )
    {
LABEL_20:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    if ( v6 > 0 )
      v1 = (unsigned __int16)v6 | 0x80070000;
    else
      v1 = v6;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 80;
      v5 = (unsigned int)v6;
LABEL_19:
      WPP_SF_D(*((_QWORD *)v7 + 2), v8, v4, v5);
      goto LABEL_20;
    }
    goto LABEL_21;
  }
  v1 = v3;
LABEL_16:
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 79;
    goto LABEL_19;
  }
LABEL_21:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (v1 & 0x80000000) != 0 && v7 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)v7 + 2), 10, v4, v1);
  return v1;
}

```

## disassembly

```asm
0x18001e670  mov     r11, rsp
0x18001e673  mov     [r11+20h], rbx
0x18001e677  mov     [r11+8], rcx
0x18001e67b  push    rdi
0x18001e67c  sub     rsp, 30h
0x18001e680  xor     eax, eax
0x18001e682  lea     rcx, [r11+10h]; lpSystemTimeAsFileTime
0x18001e686  and     [r11+8], rax
0x18001e68a  xor     ebx, ebx
0x18001e68c  and     [r11+10h], rbx
0x18001e690  mov     [rsp+38h+arg_14], eax
0x18001e694  call    cs:__imp_GetSystemTimeAsFileTime
0x18001e69b  nop     dword ptr [rax+rax+00h]
0x18001e6a0  mov     r9, [rsp+38h+arg_8]
0x18001e6a5  mov     [rsp+50h], r9
0x18001e6aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6b1  lea     rdi, WPP_GLOBAL_Control
0x18001e6b8  cmp     rcx, rdi
0x18001e6bb  jz      short loc_18001E6CF
0x18001e6bd  test    byte ptr [rcx+1Ch], 4
0x18001e6c1  jz      short loc_18001E6CF
0x18001e6c3  mov     rcx, [rcx+10h]
0x18001e6c7  lea     edx, [rbx+4Eh]
0x18001e6ca  call    WPP_SF_P
0x18001e6cf  lea     rax, [rsp+38h+hKey]
0x18001e6d4  mov     r9d, 2; samDesired
0x18001e6da  xor     r8d, r8d; ulOptions
0x18001e6dd  mov     [rsp+38h+phkResult], rax; phkResult
0x18001e6e2  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MemoryDiagnostic"
0x18001e6e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e6f0  call    cs:__imp_RegOpenKeyExW
0x18001e6f7  nop     dword ptr [rax+rax+00h]
0x18001e6fc  mov     r9d, eax
0x18001e6ff  test    eax, eax
0x18001e701  jnz     short loc_18001E76D
0x18001e703  mov     rax, [rsp+38h+hKey]
0x18001e708  test    rax, rax
0x18001e70b  jz      short loc_18001E772
0x18001e70d  lea     rcx, [rsp+38h+Data]
0x18001e712  mov     [rsp+38h+cbData], 8; cbData
0x18001e71a  mov     [rsp+38h+phkResult], rcx; lpData
0x18001e71f  lea     rdx, aLastscantime; "LastScanTime"
0x18001e726  mov     rcx, rax; hKey
0x18001e729  mov     r9d, 0Bh; dwType
0x18001e72f  xor     r8d, r8d; Reserved
0x18001e732  call    cs:__imp_RegSetValueExW
0x18001e739  nop     dword ptr [rax+rax+00h]
0x18001e73e  test    eax, eax
0x18001e740  jz      short loc_18001E7A1
0x18001e742  jg      short loc_18001E748
0x18001e744  mov     ebx, eax
0x18001e746  jmp     short loc_18001E751
0x18001e748  movzx   ebx, ax
0x18001e74b  or      ebx, 80070000h
0x18001e751  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e758  cmp     rcx, rdi
0x18001e75b  jz      short loc_18001E7A8
0x18001e75d  test    byte ptr [rcx+1Ch], 1
0x18001e761  jz      short loc_18001E7A8
0x18001e763  mov     edx, 50h ; 'P'
0x18001e768  mov     r9d, eax
0x18001e76b  jmp     short loc_18001E798
0x18001e76d  test    r9d, r9d
0x18001e770  jg      short loc_18001E777
0x18001e772  mov     ebx, r9d
0x18001e775  jmp     short loc_18001E781
0x18001e777  movzx   ebx, r9w
0x18001e77b  or      ebx, 80070000h
0x18001e781  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e788  cmp     rcx, rdi
0x18001e78b  jz      short loc_18001E7A8
0x18001e78d  test    byte ptr [rcx+1Ch], 1
0x18001e791  jz      short loc_18001E7A8
0x18001e793  mov     edx, 4Fh ; 'O'
0x18001e798  mov     rcx, [rcx+10h]
0x18001e79c  call    WPP_SF_D
0x18001e7a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7a8  mov     rax, [rsp+38h+hKey]
0x18001e7ad  test    rax, rax
0x18001e7b0  jz      short loc_18001E7C8
0x18001e7b2  mov     rcx, rax; hKey
0x18001e7b5  call    cs:__imp_RegCloseKey
0x18001e7bc  nop     dword ptr [rax+rax+00h]
0x18001e7c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7c8  test    ebx, ebx
0x18001e7ca  jns     short loc_18001E7E8
0x18001e7cc  cmp     rcx, rdi
0x18001e7cf  jz      short loc_18001E7E8
0x18001e7d1  test    byte ptr [rcx+1Ch], 1
0x18001e7d5  jz      short loc_18001E7E8
0x18001e7d7  mov     rcx, [rcx+10h]
0x18001e7db  mov     edx, 0Ah
0x18001e7e0  mov     r9d, ebx
0x18001e7e3  call    WPP_SF_D
0x18001e7e8  mov     eax, ebx
0x18001e7ea  mov     rbx, [rsp+38h+arg_18]
0x18001e7ef  add     rsp, 30h
0x18001e7f3  pop     rdi
0x18001e7f4  retn
```
