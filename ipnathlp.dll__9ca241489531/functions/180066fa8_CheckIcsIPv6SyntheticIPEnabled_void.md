# CheckIcsIPv6SyntheticIPEnabled(void)

- ea: `0x180066fa8`
- end: `0x18006710b`
- name: `?CheckIcsIPv6SyntheticIPEnabled@@YAXXZ`
- size: `355`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000c790`

## callees

- `0x18000c110`
- `0x180066fa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800670af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800670af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067052`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067052`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800670d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800670d2`

## string_xrefs

- `0x18006703f`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
void CheckIcsIPv6SyntheticIPEnabled(void)
{
  PVOID *v0; // rcx
  __int64 v1; // rdx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  hKey = 0;
  cbData = 4;
  if ( *(_DWORD *)&Data == -1 )
  {
    *(_DWORD *)&Data = 1;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters", 0, 1u, &hKey) )
    {
      v0 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v1 = 24;
        goto LABEL_23;
      }
    }
    else
    {
      if ( !RegQueryValueExW(hKey, L"EnableICSIPv6SyntheticPIP", 0, 0, &Data, &cbData) )
        *(_DWORD *)&Data = *(_DWORD *)&Data != 0;
      if ( hKey )
        RegCloseKey(hKey);
      v0 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v1 = 25;
        goto LABEL_23;
      }
    }
  }
  else if ( v0 != &WPP_GLOBAL_Control && *((char *)v0 + 28) < 0 && *((_BYTE *)v0 + 25) >= 6u )
  {
    v1 = 23;
LABEL_23:
    WPP_SF_(v0[2], v1, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
  }
}

```

## disassembly

```asm
0x180066fa8  push    rsi
0x180066faa  sub     rsp, 30h
0x180066fae  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fb5  lea     rsi, WPP_GLOBAL_Control
0x180066fbc  cmp     rcx, rsi
0x180066fbf  jz      short loc_180066FE9
0x180066fc1  test    byte ptr [rcx+1Ch], 80h
0x180066fc5  jz      short loc_180066FE9
0x180066fc7  cmp     byte ptr [rcx+19h], 6
0x180066fcb  jb      short loc_180066FE9
0x180066fcd  mov     rcx, [rcx+10h]
0x180066fd1  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180066fd8  mov     edx, 16h
0x180066fdd  call    WPP_SF_
0x180066fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fe9  cmp     cs:Data, 0FFFFFFFFh
0x180066ff0  mov     [rsp+38h+hKey], 0
0x180066ff9  mov     [rsp+38h+cbData], 4
0x180067001  jz      short loc_18006702A
0x180067003  cmp     rcx, rsi
0x180067006  jz      loc_180067105
0x18006700c  test    byte ptr [rcx+1Ch], 80h
0x180067010  jz      loc_180067105
0x180067016  cmp     byte ptr [rcx+19h], 6
0x18006701a  jb      loc_180067105
0x180067020  mov     edx, 17h
0x180067025  jmp     loc_1800670F5
0x18006702a  mov     r9d, 1; samDesired
0x180067030  lea     rax, [rsp+38h+hKey]
0x180067035  xor     r8d, r8d; ulOptions
0x180067038  mov     cs:Data, r9d
0x18006703f  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x180067046  mov     [rsp+38h+phkResult], rax; phkResult
0x18006704b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180067052  call    cs:__imp_RegOpenKeyExW
0x180067058  test    eax, eax
0x18006705a  jz      short loc_180067087
0x18006705c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067063  cmp     rcx, rsi
0x180067066  jz      loc_180067105
0x18006706c  test    byte ptr [rcx+1Ch], 80h
0x180067070  jz      loc_180067105
0x180067076  cmp     byte ptr [rcx+19h], 6
0x18006707a  jb      loc_180067105
0x180067080  mov     edx, 18h
0x180067085  jmp     short loc_1800670F5
0x180067087  mov     rcx, [rsp+38h+hKey]; hKey
0x18006708c  lea     rax, [rsp+38h+cbData]
0x180067091  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180067096  lea     rdx, aEnableicsipv6s; "EnableICSIPv6SyntheticPIP"
0x18006709d  lea     rax, Data
0x1800670a4  xor     r9d, r9d; lpType
0x1800670a7  xor     r8d, r8d; lpReserved
0x1800670aa  mov     [rsp+38h+phkResult], rax; lpData
0x1800670af  call    cs:__imp_RegQueryValueExW
0x1800670b5  test    eax, eax
0x1800670b7  jnz     short loc_1800670C8
0x1800670b9  cmp     cs:Data, eax
0x1800670bf  setnz   al
0x1800670c2  mov     cs:Data, eax
0x1800670c8  mov     rcx, [rsp+38h+hKey]; hKey
0x1800670cd  test    rcx, rcx
0x1800670d0  jz      short loc_1800670D8
0x1800670d2  call    cs:__imp_RegCloseKey
0x1800670d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800670df  cmp     rcx, rsi
0x1800670e2  jz      short loc_180067105
0x1800670e4  test    byte ptr [rcx+1Ch], 80h
0x1800670e8  jz      short loc_180067105
0x1800670ea  cmp     byte ptr [rcx+19h], 6
0x1800670ee  jb      short loc_180067105
0x1800670f0  mov     edx, 19h
0x1800670f5  mov     rcx, [rcx+10h]
0x1800670f9  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180067100  call    WPP_SF_
0x180067105  add     rsp, 30h
0x180067109  pop     rsi
0x18006710a  retn
```
