# IsAppPhonebookEx

- ea: `0x1800943b0`
- end: `0x180094524`
- name: `IsAppPhonebookEx`
- size: `372`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180094650`

## callees

- `0x180093ed8`
- `0x1800943b0`
- `0x1800e8e96`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800943d2`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800943d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009440c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009440c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180094490`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180094490`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800944ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800944ee`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180094502`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180094502`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800944ba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800944ba`

## string_xrefs

- `0x1800943de`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`
- `0x1800943ed`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`

## pseudocode

```c
__int64 __fastcall IsAppPhonebookEx(PCNZWCH lpString2)
{
  WCHAR *v2; // rbx
  unsigned int v3; // ebp
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  WCHAR *v6; // rax
  LSTATUS v7; // edi
  DWORD v8; // esi
  LSTATUS v9; // eax
  DWORD cchValueName; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v2 = 0;
  v3 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(lpString2);
  v5 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
  if ( !IsStateSeparationEnabled )
    v5 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey) )
  {
    v6 = (WCHAR *)DebugAlloc(0x8000);
    v2 = v6;
    if ( v6 )
    {
      v7 = 0;
      memset_0(v6, 0, 0x8000u);
      do
      {
LABEL_6:
        v8 = 0;
        if ( v7 == 259 )
          break;
        while ( 1 )
        {
          cchValueName = 0x3FFF;
          v9 = RegEnumValueW(hKey, v8, v2, &cchValueName, 0, 0, 0, 0);
          v7 = v9;
          if ( v9 )
            break;
          if ( CompareStringW(0x7Fu, 1u, v2, -1, lpString2, -1) == 2 )
          {
            v3 = 1;
            goto LABEL_6;
          }
          ++v8;
        }
      }
      while ( v9 != 259 );
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
    GlobalFree(v2);
  return v3;
}

```

## disassembly

```asm
0x1800943b0  mov     [rsp+arg_0], rbx
0x1800943b5  mov     [rsp+arg_18], rbp
0x1800943ba  push    rsi
0x1800943bb  push    rdi
0x1800943bc  push    r14
0x1800943be  sub     rsp, 40h
0x1800943c2  mov     r14, rcx
0x1800943c5  mov     [rsp+58h+hKey], 0
0x1800943ce  xor     ebx, ebx
0x1800943d0  xor     ebp, ebp
0x1800943d2  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800943d9  nop     dword ptr [rax+rax+00h]
0x1800943de  lea     rcx, aSystemCurrentc_13; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800943e5  mov     r9d, 20019h; samDesired
0x1800943eb  test    al, al
0x1800943ed  lea     rdx, aOsdataSystemCu; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800943f4  lea     rax, [rsp+58h+hKey]
0x1800943f9  cmovz   rdx, rcx; lpSubKey
0x1800943fd  mov     [rsp+58h+phkResult], rax; phkResult
0x180094402  xor     r8d, r8d; ulOptions
0x180094405  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009440c  call    cs:__imp_RegOpenKeyExW
0x180094413  nop     dword ptr [rax+rax+00h]
0x180094418  test    eax, eax
0x18009441a  jnz     loc_1800944E4
0x180094420  mov     esi, 8000h
0x180094425  mov     ecx, esi
0x180094427  call    DebugAlloc
0x18009442c  mov     rbx, rax
0x18009442f  test    rax, rax
0x180094432  jz      loc_1800944E4
0x180094438  xor     edi, edi
0x18009443a  mov     r8d, esi; Size
0x18009443d  xor     edx, edx; Val
0x18009443f  mov     rcx, rax; void *
0x180094442  call    memset_0
0x180094447  xor     esi, esi
0x180094449  cmp     edi, 103h
0x18009444f  jz      loc_1800944E4
0x180094455  mov     rcx, [rsp+58h+hKey]; hKey
0x18009445a  lea     r9, [rsp+58h+cchValueName]; lpcchValueName
0x18009445f  mov     [rsp+58h+lpcbData], 0; lpcbData
0x180094468  mov     r8, rbx; lpValueName
0x18009446b  mov     [rsp+58h+lpData], 0; lpData
0x180094474  mov     edx, esi; dwIndex
0x180094476  mov     [rsp+58h+lpType], 0; lpType
0x18009447f  mov     [rsp+58h+phkResult], 0; lpReserved
0x180094488  mov     [rsp+58h+cchValueName], 3FFFh
0x180094490  call    cs:__imp_RegEnumValueW
0x180094497  nop     dword ptr [rax+rax+00h]
0x18009449c  mov     edi, eax
0x18009449e  test    eax, eax
0x1800944a0  jnz     short loc_1800944D9
0x1800944a2  or      eax, 0FFFFFFFFh
0x1800944a5  lea     edx, [rdi+1]; dwCmpFlags
0x1800944a8  mov     dword ptr [rsp+58h+lpType], eax; cchCount2
0x1800944ac  lea     ecx, [rdi+7Fh]; Locale
0x1800944af  mov     r9d, eax; cchCount1
0x1800944b2  mov     [rsp+58h+phkResult], r14; lpString2
0x1800944b7  mov     r8, rbx; lpString1
0x1800944ba  call    cs:__imp_CompareStringW
0x1800944c1  nop     dword ptr [rax+rax+00h]
0x1800944c6  cmp     eax, 2
0x1800944c9  jz      short loc_1800944CF
0x1800944cb  inc     esi
0x1800944cd  jmp     short loc_180094455
0x1800944cf  mov     ebp, 1
0x1800944d4  jmp     loc_180094447
0x1800944d9  cmp     eax, 103h
0x1800944de  jnz     loc_180094447
0x1800944e4  mov     rcx, [rsp+58h+hKey]; hKey
0x1800944e9  test    rcx, rcx
0x1800944ec  jz      short loc_1800944FA
0x1800944ee  call    cs:__imp_RegCloseKey
0x1800944f5  nop     dword ptr [rax+rax+00h]
0x1800944fa  test    rbx, rbx
0x1800944fd  jz      short loc_18009450E
0x1800944ff  mov     rcx, rbx; hMem
0x180094502  call    cs:__imp_GlobalFree
0x180094509  nop     dword ptr [rax+rax+00h]
0x18009450e  mov     rbx, [rsp+58h+arg_0]
0x180094513  mov     eax, ebp
0x180094515  mov     rbp, [rsp+58h+arg_18]
0x18009451a  add     rsp, 40h
0x18009451e  pop     r14
0x180094520  pop     rdi
0x180094521  pop     rsi
0x180094522  retn
```
