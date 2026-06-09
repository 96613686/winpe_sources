# TcpipLocalSetService

- ea: `0x18002f9d0`
- end: `0x18002fb99`
- name: `TcpipLocalSetService`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18002f9d0`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002fa3a`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002fa3a`
- `ntdll!RtlInitAnsiString` at `0x18002fa23`
- `ntdll!RtlInitAnsiString` at `0x18002fa23`
- `ntdll!RtlFreeUnicodeString` at `0x18002fb47`
- `ntdll!RtlFreeUnicodeString` at `0x18002fb47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fb0e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fb0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fb5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fb71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fb5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fb71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fabd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fabd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18002fb1c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18002fb1c`

## string_xrefs

- `0x18002fa83`: `SYSTEM\CurrentControlSet\Control\ServiceProvider\ServiceTypes`

## pseudocode

```c
NTSTATUS __fastcall TcpipLocalSetService(int a1, __int64 a2, int a3, __int64 a4)
{
  NTSTATUS result; // eax
  unsigned int *v6; // rbx
  const WCHAR *Buffer; // rdi
  const char *v8; // rdx
  LSTATUS v9; // esi
  _DWORD *v10; // rdi
  unsigned int i; // r14d
  DWORD v12; // r9d
  const WCHAR *v13; // rdx
  LSTATUS v14; // eax
  const BYTE *phkResult; // [rsp+20h] [rbp-40h]
  DWORD cbData; // [rsp+28h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-28h] BYREF
  struct _STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  HKEY v20; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  v20 = 0;
  UnicodeString = 0;
  if ( a1 != 4 )
    return 0;
  v6 = *(unsigned int **)(a4 + 72);
  Buffer = (const WCHAR *)((char *)v6 + *v6);
  if ( !a3 )
  {
    v8 = (char *)v6 + *v6;
    DestinationString = 0;
    RtlInitAnsiString(&DestinationString, v8);
    result = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
    if ( result )
      return result;
    Buffer = UnicodeString.Buffer;
  }
  if ( *v6 && Buffer && *Buffer )
  {
    v9 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Control\\ServiceProvider\\ServiceTypes",
           0,
           0x2001Fu,
           &hKey);
    if ( !v9 )
    {
      v9 = RegOpenKeyExW(hKey, Buffer, 0, 0x2001Fu, &v20);
      if ( !v9 )
      {
        v10 = v6 + 2;
        for ( i = 0; i < v6[1]; v10 += 5 )
        {
          if ( (unsigned int)(*v10 - 10) <= 3 )
          {
            v12 = v10[1];
            v13 = (const WCHAR *)((char *)v6 + (unsigned int)v10[3]);
            cbData = v10[2];
            phkResult = (const BYTE *)v6 + (unsigned int)v10[4];
            if ( a3 )
              v14 = RegSetValueExW(v20, v13, 0, v12, phkResult, cbData);
            else
              v14 = RegSetValueExA(v20, (LPCSTR)v13, 0, v12, phkResult, cbData);
            v9 = v14;
          }
          ++i;
        }
      }
    }
  }
  else
  {
    v9 = 87;
  }
  if ( !a3 )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v20 )
    RegCloseKey(v20);
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x18002f9d0  mov     [rsp-28h+arg_0], rbx
0x18002f9d5  mov     [rsp-28h+arg_8], rsi
0x18002f9da  push    rbp
0x18002f9db  push    rdi
0x18002f9dc  push    r12
0x18002f9de  push    r14
0x18002f9e0  push    r15
0x18002f9e2  mov     rbp, rsp
0x18002f9e5  sub     rsp, 60h
0x18002f9e9  xor     r12d, r12d
0x18002f9ec  xorps   xmm0, xmm0
0x18002f9ef  mov     [rbp+hKey], r12
0x18002f9f3  mov     r15d, r8d
0x18002f9f6  mov     [rbp+arg_18], r12
0x18002f9fa  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18002f9fe  cmp     ecx, 4
0x18002fa01  jz      short loc_18002FA0A
0x18002fa03  xor     eax, eax
0x18002fa05  jmp     loc_18002FB7F
0x18002fa0a  mov     rbx, [r9+48h]
0x18002fa0e  mov     edi, [rbx]
0x18002fa10  add     rdi, rbx
0x18002fa13  test    r15d, r15d
0x18002fa16  jnz     short loc_18002FA52
0x18002fa18  mov     rdx, rdi; SourceString
0x18002fa1b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002fa1f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002fa23  call    cs:__imp_RtlInitAnsiString
0x18002fa2a  nop     dword ptr [rax+rax+00h]
0x18002fa2f  mov     r8b, 1; AllocateDestinationString
0x18002fa32  lea     rdx, [rbp+DestinationString]; SourceString
0x18002fa36  lea     rcx, [rbp+UnicodeString]; DestinationString
0x18002fa3a  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18002fa41  nop     dword ptr [rax+rax+00h]
0x18002fa46  test    eax, eax
0x18002fa48  jnz     loc_18002FB7F
0x18002fa4e  mov     rdi, [rbp+UnicodeString.Buffer]
0x18002fa52  cmp     [rbx], r12d
0x18002fa55  jz      loc_18002FB39
0x18002fa5b  test    rdi, rdi
0x18002fa5e  jz      loc_18002FB39
0x18002fa64  cmp     [rdi], r12w
0x18002fa68  jz      loc_18002FB39
0x18002fa6e  lea     rax, [rbp+hKey]
0x18002fa72  mov     r14d, 2001Fh
0x18002fa78  mov     r9d, r14d; samDesired
0x18002fa7b  mov     [rsp+60h+phkResult], rax; phkResult
0x18002fa80  xor     r8d, r8d; ulOptions
0x18002fa83  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Ser"...
0x18002fa8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fa91  call    cs:__imp_RegOpenKeyExW
0x18002fa98  nop     dword ptr [rax+rax+00h]
0x18002fa9d  mov     esi, eax
0x18002fa9f  test    eax, eax
0x18002faa1  jnz     loc_18002FB3E
0x18002faa7  mov     rcx, [rbp+hKey]; hKey
0x18002faab  lea     rax, [rbp+arg_18]
0x18002faaf  mov     r9d, r14d; samDesired
0x18002fab2  mov     [rsp+60h+phkResult], rax; phkResult
0x18002fab7  xor     r8d, r8d; ulOptions
0x18002faba  mov     rdx, rdi; lpSubKey
0x18002fabd  call    cs:__imp_RegOpenKeyExW
0x18002fac4  nop     dword ptr [rax+rax+00h]
0x18002fac9  mov     esi, eax
0x18002facb  test    eax, eax
0x18002facd  jnz     short loc_18002FB3E
0x18002facf  lea     rdi, [rbx+8]
0x18002fad3  mov     r14d, r12d
0x18002fad6  cmp     [rbx+4], r12d
0x18002fada  jbe     short loc_18002FB3E
0x18002fadc  mov     eax, [rdi]
0x18002fade  sub     eax, 0Ah
0x18002fae1  cmp     eax, 3
0x18002fae4  ja      short loc_18002FB2A
0x18002fae6  mov     ecx, [rdi+8]
0x18002fae9  xor     r8d, r8d; Reserved
0x18002faec  mov     eax, [rdi+10h]
0x18002faef  mov     edx, [rdi+0Ch]
0x18002faf2  add     rax, rbx
0x18002faf5  mov     r9d, [rdi+4]; dwType
0x18002faf9  add     rdx, rbx; lpValueName
0x18002fafc  mov     [rsp+60h+cbData], ecx; cbData
0x18002fb00  mov     rcx, [rbp+arg_18]; hKey
0x18002fb04  mov     [rsp+60h+phkResult], rax; lpData
0x18002fb09  test    r15d, r15d
0x18002fb0c  jz      short loc_18002FB1C
0x18002fb0e  call    cs:__imp_RegSetValueExW
0x18002fb15  nop     dword ptr [rax+rax+00h]
0x18002fb1a  jmp     short loc_18002FB28
0x18002fb1c  call    cs:__imp_RegSetValueExA
0x18002fb23  nop     dword ptr [rax+rax+00h]
0x18002fb28  mov     esi, eax
0x18002fb2a  inc     r14d
0x18002fb2d  add     rdi, 14h
0x18002fb31  cmp     r14d, [rbx+4]
0x18002fb35  jb      short loc_18002FADC
0x18002fb37  jmp     short loc_18002FB3E
0x18002fb39  mov     esi, 57h ; 'W'
0x18002fb3e  test    r15d, r15d
0x18002fb41  jnz     short loc_18002FB53
0x18002fb43  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18002fb47  call    cs:__imp_RtlFreeUnicodeString
0x18002fb4e  nop     dword ptr [rax+rax+00h]
0x18002fb53  mov     rcx, [rbp+arg_18]; hKey
0x18002fb57  test    rcx, rcx
0x18002fb5a  jz      short loc_18002FB68
0x18002fb5c  call    cs:__imp_RegCloseKey
0x18002fb63  nop     dword ptr [rax+rax+00h]
0x18002fb68  mov     rcx, [rbp+hKey]; hKey
0x18002fb6c  test    rcx, rcx
0x18002fb6f  jz      short loc_18002FB7D
0x18002fb71  call    cs:__imp_RegCloseKey
0x18002fb78  nop     dword ptr [rax+rax+00h]
0x18002fb7d  mov     eax, esi
0x18002fb7f  lea     r11, [rsp+60h+var_s0]
0x18002fb84  mov     rbx, [r11+30h]
0x18002fb88  mov     rsi, [r11+38h]
0x18002fb8c  mov     rsp, r11
0x18002fb8f  pop     r15
0x18002fb91  pop     r14
0x18002fb93  pop     r12
0x18002fb95  pop     rdi
0x18002fb96  pop     rbp
0x18002fb97  retn
```
