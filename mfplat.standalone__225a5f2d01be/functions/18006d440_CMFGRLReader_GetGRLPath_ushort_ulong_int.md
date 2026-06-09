# CMFGRLReader::GetGRLPath(ushort *,ulong,int)

- ea: `0x18006d440`
- end: `0x18006d5bb`
- name: `?GetGRLPath@CMFGRLReader@@SAJPEAGKH@Z`
- size: `379`
- prototype: `__int64 __fastcall(wchar_t *Destination, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18006c988`

## callees

- `0x18006d440`
- `0x1801200d0`
- `0x180120470`
- `0x180120e9c`
- `0x180120ea8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d55c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d55c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d4b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d4b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006d4e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006d4e9`

## string_xrefs

- `0x18006d4a3`: `System\CurrentControlSet\Services\PEAuth`
- `0x18006d4db`: `DataPath`

## pseudocode

```c
__int64 __fastcall CMFGRLReader::GetGRLPath(wchar_t *Destination)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  unsigned __int64 v4; // rdx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  cbData = 520;
  Type = 0;
  if ( Destination )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\PEAuth", 0, 1u, &hKey) )
    {
      v2 = -1072875845;
    }
    else
    {
      v2 = 0;
      v3 = RegQueryValueExW(hKey, L"DataPath", 0, &Type, Data, &cbData);
      if ( v3 )
      {
        if ( v3 > 0 )
          v2 = (unsigned __int16)v3 | 0x80070000;
        else
          v2 = v3;
      }
      else if ( Type == 1 && cbData <= 0x206 )
      {
        v4 = cbData & 0xFFFFFFFE;
        if ( v4 >= 0x208 )
          _report_rangecheckfailure();
        *(_WORD *)&Data[v4] = 0;
        wcscpy_s(Destination, 0x104u, (const wchar_t *)Data);
        wcscat_s(Destination, 0x104u, L"\\Active.GRL");
      }
      else
      {
        v2 = -2147418113;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x18006d440  mov     [rsp-8+arg_8], rbx
0x18006d445  mov     [rsp-8+arg_10], rdi
0x18006d44a  push    rbp
0x18006d44b  lea     rbp, [rsp-160h]
0x18006d453  sub     rsp, 260h
0x18006d45a  mov     rax, cs:__security_cookie
0x18006d461  xor     rax, rsp
0x18006d464  mov     [rbp+160h+var_10], rax
0x18006d46b  mov     [rsp+260h+hKey], 0
0x18006d474  mov     rdi, rcx
0x18006d477  mov     [rsp+260h+cbData], 208h
0x18006d47f  mov     [rsp+260h+Type], 0
0x18006d487  test    rcx, rcx
0x18006d48a  jz      loc_18006D5A0
0x18006d490  lea     rax, [rsp+260h+hKey]
0x18006d495  mov     r9d, 1; samDesired
0x18006d49b  xor     r8d, r8d; ulOptions
0x18006d49e  mov     [rsp+260h+phkResult], rax; phkResult
0x18006d4a3  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\PE"...
0x18006d4aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006d4b1  call    cs:__imp_RegOpenKeyExW
0x18006d4b7  test    eax, eax
0x18006d4b9  jnz     loc_18006D5A7
0x18006d4bf  mov     rcx, [rsp+260h+hKey]; hKey
0x18006d4c4  lea     rax, [rsp+260h+cbData]
0x18006d4c9  mov     [rsp+260h+lpcbData], rax; lpcbData
0x18006d4ce  lea     r9, [rsp+260h+Type]; lpType
0x18006d4d3  lea     rax, [rsp+260h+Data]
0x18006d4d8  xor     r8d, r8d; lpReserved
0x18006d4db  lea     rdx, aDatapath; "DataPath"
0x18006d4e2  mov     [rsp+260h+phkResult], rax; lpData
0x18006d4e7  xor     ebx, ebx
0x18006d4e9  call    cs:__imp_RegQueryValueExW
0x18006d4ef  test    eax, eax
0x18006d4f1  jnz     loc_18006D588
0x18006d4f7  cmp     [rsp+260h+Type], 1
0x18006d4fc  jnz     loc_18006D5B4
0x18006d502  cmp     [rsp+260h+cbData], 206h
0x18006d50a  ja      loc_18006D5B4
0x18006d510  mov     edx, [rsp+260h+cbData]
0x18006d514  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18006d518  cmp     rdx, 208h
0x18006d51f  jnb     loc_18006D5AE
0x18006d525  xor     eax, eax
0x18006d527  lea     r8, [rsp+260h+Data]; Source
0x18006d52c  mov     word ptr [rsp+rdx+260h+Data], ax
0x18006d531  mov     rcx, rdi; Destination
0x18006d534  mov     edx, 104h; SizeInWords
0x18006d539  call    wcscpy_s
0x18006d53e  lea     r8, aActiveGrl; "\\Active.GRL"
0x18006d545  mov     edx, 104h; SizeInWords
0x18006d54a  mov     rcx, rdi; Destination
0x18006d54d  call    wcscat_s
0x18006d552  mov     rcx, [rsp+260h+hKey]; hKey
0x18006d557  test    rcx, rcx
0x18006d55a  jz      short loc_18006D562
0x18006d55c  call    cs:__imp_RegCloseKey
0x18006d562  mov     eax, ebx
0x18006d564  mov     rcx, [rbp+160h+var_10]
0x18006d56b  xor     rcx, rsp; StackCookie
0x18006d56e  call    __security_check_cookie
0x18006d573  lea     r11, [rsp+260h+var_s0]
0x18006d57b  mov     rbx, [r11+18h]
0x18006d57f  mov     rdi, [r11+20h]
0x18006d583  mov     rsp, r11
0x18006d586  pop     rbp
0x18006d587  retn
0x18006d588  jg      short loc_18006D595
0x18006d58a  mov     ebx, eax
0x18006d58c  test    ebx, ebx
0x18006d58e  js      short loc_18006D552
0x18006d590  jmp     loc_18006D4F7
0x18006d595  movzx   ebx, ax
0x18006d598  or      ebx, 80070000h
0x18006d59e  jmp     short loc_18006D58C
0x18006d5a0  mov     ebx, 80070057h
0x18006d5a5  jmp     short loc_18006D562
0x18006d5a7  mov     ebx, 0C00D36BBh
0x18006d5ac  jmp     short loc_18006D552
0x18006d5ae  call    __report_rangecheckfailure
0x18006d5b4  mov     ebx, 8000FFFFh
0x18006d5b9  jmp     short loc_18006D552
```
