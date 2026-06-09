# SockInitializeBufferKeyTable

- ea: `0x18002ad00`
- end: `0x18002adfa`
- name: `SockInitializeBufferKeyTable`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002ae00`

## callees

- `0x180022bd2`
- `0x18002ad00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002ad72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002ad72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002ad31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002ad31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ad9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ad9e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18002adc1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18002adc1`

## string_xrefs

- `0x18002ad23`: `System\CurrentControlSet\Services\Winsock\Parameters`

## pseudocode

```c
__int64 SockInitializeBufferKeyTable()
{
  __int64 v0; // rax
  __int64 result; // rax
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Winsock\\Parameters", 0, 1u, &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "AcceptExBufferTableSize", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v0 = Data;
      if ( Data < 0x7FF )
      {
        v0 = 2047;
        Data = 2047;
      }
      SockBufferKeyTableSize = v0;
    }
    RegCloseKey(hKey);
  }
  result = (__int64)VirtualAlloc(0, 8 * SockBufferKeyTableSize, 0x3000u, 4u);
  SockBufferKeyTable = (LPVOID)result;
  if ( result )
  {
    memset_0((void *)result, 0, 8 * SockBufferKeyTableSize);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18002ad00  push    rbp
0x18002ad02  mov     rbp, rsp
0x18002ad05  sub     rsp, 30h
0x18002ad09  lea     rax, [rbp+hKey]
0x18002ad0d  mov     [rbp+hKey], 0
0x18002ad15  mov     r9d, 1; samDesired
0x18002ad1b  mov     [rsp+30h+phkResult], rax; phkResult
0x18002ad20  xor     r8d, r8d; ulOptions
0x18002ad23  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Wi"...
0x18002ad2a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ad31  call    cs:__imp_RegOpenKeyExA
0x18002ad38  nop     dword ptr [rax+rax+00h]
0x18002ad3d  test    eax, eax
0x18002ad3f  jnz     short loc_18002ADAA
0x18002ad41  mov     rcx, [rbp+hKey]; hKey
0x18002ad45  lea     r9, [rbp+Type]; lpType
0x18002ad49  mov     [rbp+Type], eax
0x18002ad4c  lea     rdx, aAcceptexbuffer; "AcceptExBufferTableSize"
0x18002ad53  mov     [rbp+Data], eax
0x18002ad56  xor     r8d, r8d; lpReserved
0x18002ad59  lea     rax, [rbp+cbData]
0x18002ad5d  mov     [rbp+cbData], 4
0x18002ad64  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002ad69  lea     rax, [rbp+Data]
0x18002ad6d  mov     [rsp+30h+phkResult], rax; lpData
0x18002ad72  call    cs:__imp_RegQueryValueExA
0x18002ad79  nop     dword ptr [rax+rax+00h]
0x18002ad7e  test    eax, eax
0x18002ad80  jnz     short loc_18002AD9A
0x18002ad82  mov     eax, [rbp+Data]
0x18002ad85  mov     ecx, 7FFh
0x18002ad8a  cmp     eax, ecx
0x18002ad8c  jnb     short loc_18002AD93
0x18002ad8e  mov     eax, ecx
0x18002ad90  mov     [rbp+Data], eax
0x18002ad93  mov     cs:SockBufferKeyTableSize, rax
0x18002ad9a  mov     rcx, [rbp+hKey]; hKey
0x18002ad9e  call    cs:__imp_RegCloseKey
0x18002ada5  nop     dword ptr [rax+rax+00h]
0x18002adaa  mov     rdx, cs:SockBufferKeyTableSize
0x18002adb1  xor     ecx, ecx; lpAddress
0x18002adb3  shl     rdx, 3; dwSize
0x18002adb7  mov     r8d, 3000h; flAllocationType
0x18002adbd  lea     r9d, [rcx+4]; flProtect
0x18002adc1  call    cs:__imp_VirtualAlloc
0x18002adc8  nop     dword ptr [rax+rax+00h]
0x18002adcd  mov     cs:SockBufferKeyTable, rax
0x18002add4  test    rax, rax
0x18002add7  jz      short loc_18002ADF3
0x18002add9  mov     r8, cs:SockBufferKeyTableSize
0x18002ade0  xor     edx, edx; Val
0x18002ade2  shl     r8, 3; Size
0x18002ade6  mov     rcx, rax; void *
0x18002ade9  call    memset_0
0x18002adee  mov     eax, 1
0x18002adf3  add     rsp, 30h
0x18002adf7  pop     rbp
0x18002adf8  retn
```
