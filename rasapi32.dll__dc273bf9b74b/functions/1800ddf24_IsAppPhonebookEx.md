# IsAppPhonebookEx

- ea: `0x1800ddf24`
- end: `0x1800de072`
- name: `IsAppPhonebookEx`
- size: `334`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800de184`

## callees

- `0x18000b0f4`
- `0x18000ea58`
- `0x1800ddf24`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ddf7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ddf7a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ddff8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ddff8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800de04a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800de04a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800ddf46`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800ddf46`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800de01c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800de01c`

## string_xrefs

- `0x1800ddf5b`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`
- `0x1800ddf4c`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`

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
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
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
    Free0(v2);
  return v3;
}

```

## disassembly

```asm
0x1800ddf24  mov     [rsp+arg_0], rbx
0x1800ddf29  mov     [rsp+arg_18], rbp
0x1800ddf2e  push    rsi
0x1800ddf2f  push    rdi
0x1800ddf30  push    r14
0x1800ddf32  sub     rsp, 40h
0x1800ddf36  mov     r14, rcx
0x1800ddf39  mov     [rsp+58h+hKey], 0
0x1800ddf42  xor     ebx, ebx
0x1800ddf44  xor     ebp, ebp
0x1800ddf46  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800ddf4c  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800ddf53  mov     r9d, 20019h; samDesired
0x1800ddf59  test    al, al
0x1800ddf5b  lea     rdx, aOsdataSystemCu; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800ddf62  lea     rax, [rsp+58h+hKey]
0x1800ddf67  cmovz   rdx, rcx; lpSubKey
0x1800ddf6b  mov     [rsp+58h+phkResult], rax; phkResult
0x1800ddf70  xor     r8d, r8d; ulOptions
0x1800ddf73  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ddf7a  call    cs:__imp_RegOpenKeyExW
0x1800ddf80  test    eax, eax
0x1800ddf82  jnz     loc_1800DE040
0x1800ddf88  mov     esi, 8000h
0x1800ddf8d  mov     ecx, esi
0x1800ddf8f  call    DebugAlloc
0x1800ddf94  mov     rbx, rax
0x1800ddf97  test    rax, rax
0x1800ddf9a  jz      loc_1800DE040
0x1800ddfa0  xor     edi, edi
0x1800ddfa2  mov     r8d, esi; Size
0x1800ddfa5  xor     edx, edx; Val
0x1800ddfa7  mov     rcx, rax; void *
0x1800ddfaa  call    memset_0
0x1800ddfaf  xor     esi, esi
0x1800ddfb1  cmp     edi, 103h
0x1800ddfb7  jz      loc_1800DE040
0x1800ddfbd  mov     rcx, [rsp+58h+hKey]; hKey
0x1800ddfc2  lea     r9, [rsp+58h+cchValueName]; lpcchValueName
0x1800ddfc7  mov     [rsp+58h+lpcbData], 0; lpcbData
0x1800ddfd0  mov     r8, rbx; lpValueName
0x1800ddfd3  mov     [rsp+58h+lpData], 0; lpData
0x1800ddfdc  mov     edx, esi; dwIndex
0x1800ddfde  mov     [rsp+58h+lpType], 0; lpType
0x1800ddfe7  mov     [rsp+58h+phkResult], 0; lpReserved
0x1800ddff0  mov     [rsp+58h+cchValueName], 3FFFh
0x1800ddff8  call    cs:__imp_RegEnumValueW
0x1800ddffe  mov     edi, eax
0x1800de000  test    eax, eax
0x1800de002  jnz     short loc_1800DE035
0x1800de004  or      eax, 0FFFFFFFFh
0x1800de007  lea     edx, [rdi+1]; dwCmpFlags
0x1800de00a  mov     dword ptr [rsp+58h+lpType], eax; cchCount2
0x1800de00e  lea     ecx, [rdi+7Fh]; Locale
0x1800de011  mov     r9d, eax; cchCount1
0x1800de014  mov     [rsp+58h+phkResult], r14; lpString2
0x1800de019  mov     r8, rbx; lpString1
0x1800de01c  call    cs:__imp_CompareStringW
0x1800de022  cmp     eax, 2
0x1800de025  jz      short loc_1800DE02B
0x1800de027  inc     esi
0x1800de029  jmp     short loc_1800DDFBD
0x1800de02b  mov     ebp, 1
0x1800de030  jmp     loc_1800DDFAF
0x1800de035  cmp     eax, 103h
0x1800de03a  jnz     loc_1800DDFAF
0x1800de040  mov     rcx, [rsp+58h+hKey]; hKey
0x1800de045  test    rcx, rcx
0x1800de048  jz      short loc_1800DE050
0x1800de04a  call    cs:__imp_RegCloseKey
0x1800de050  test    rbx, rbx
0x1800de053  jz      short loc_1800DE05D
0x1800de055  mov     rcx, rbx
0x1800de058  call    Free0
0x1800de05d  mov     rbx, [rsp+58h+arg_0]
0x1800de062  mov     eax, ebp
0x1800de064  mov     rbp, [rsp+58h+arg_18]
0x1800de069  add     rsp, 40h
0x1800de06d  pop     r14
0x1800de06f  pop     rdi
0x1800de070  pop     rsi
0x1800de071  retn
```
