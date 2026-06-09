# RetrieveKey

- ea: `0x180065280`
- end: `0x180065417`
- name: `RetrieveKey`
- size: `407`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18007edc0`
- `0x180080850`
- `0x180080d30`
- `0x180080d50`
- `0x180080d70`

## callees

- `0x180065280`

## import_xrefs

- `CRYPT32!CryptUnprotectData` at `0x1800653ad`
- `CRYPT32!CryptUnprotectData` at `0x1800653ad`
- `ADVAPI32!RegQueryValueExW` at `0x180065317`
- `ADVAPI32!RegQueryValueExW` at `0x180065372`
- `ADVAPI32!RegQueryValueExW` at `0x180065317`
- `ADVAPI32!RegQueryValueExW` at `0x180065372`
- `ADVAPI32!RegOpenKeyExW` at `0x1800652e6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800652e6`
- `ADVAPI32!RegCloseKey` at `0x1800653d3`
- `ADVAPI32!RegCloseKey` at `0x1800653d3`
- `KERNEL32!GetLastError` at `0x180065347`
- `KERNEL32!GetLastError` at `0x180065347`
- `KERNEL32!LocalAlloc` at `0x180065333`
- `KERNEL32!LocalAlloc` at `0x180065333`
- `KERNEL32!LocalFree` at `0x1800653e7`
- `KERNEL32!LocalFree` at `0x1800653e7`

## string_xrefs

- `0x1800652c3`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Data`

## pseudocode

```c
__int64 __fastcall RetrieveKey(__int64 a1, const WCHAR *a2, BYTE **a3, DWORD *a4)
{
  BYTE *lpData; // rdi
  DWORD Value; // ebx
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  DATA_BLOB pDataIn; // [rsp+48h] [rbp-28h] BYREF
  DATA_BLOB pDataOut; // [rsp+58h] [rbp-18h] BYREF
  __int64 cbData; // [rsp+90h] [rbp+20h] BYREF

  cbData = a1;
  if ( !a2 )
    return 87;
  hKey = 0;
  lpData = 0;
  LODWORD(cbData) = 0;
  pDataIn = 0;
  pDataOut = 0;
  Value = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Data",
            0,
            1u,
            &hKey);
  if ( !Value )
  {
    Value = RegQueryValueExW(hKey, a2, 0, 0, 0, (LPDWORD)&cbData);
    if ( !Value )
    {
      lpData = (BYTE *)LocalAlloc(0x40u, (unsigned int)cbData);
      if ( lpData )
      {
        Value = RegQueryValueExW(hKey, a2, 0, 0, lpData, (LPDWORD)&cbData);
        if ( Value )
          goto LABEL_9;
        pDataIn.cbData = cbData;
        pDataIn.pbData = lpData;
        if ( CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
        {
          *a4 = pDataOut.cbData;
          *a3 = pDataOut.pbData;
          goto LABEL_9;
        }
      }
      Value = GetLastError();
    }
  }
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpData )
    LocalFree(lpData);
  return Value;
}

```

## disassembly

```asm
0x180065280  mov     r11, rsp
0x180065283  mov     [r11+10h], rbx
0x180065287  mov     [r11+18h], rsi
0x18006528b  mov     [r11+20h], rdi
0x18006528f  mov     [r11+8], rcx
0x180065293  push    rbp
0x180065294  push    r14
0x180065296  push    r15
0x180065298  mov     rbp, rsp
0x18006529b  sub     rsp, 70h
0x18006529f  mov     r14, r9
0x1800652a2  mov     r15, r8
0x1800652a5  mov     rsi, rdx
0x1800652a8  test    rdx, rdx
0x1800652ab  jz      loc_1800653F7
0x1800652b1  and     [rbp+hKey], 0
0x1800652b6  lea     rax, [rbp+hKey]
0x1800652ba  xor     edi, edi
0x1800652bc  mov     [r11-68h], rax
0x1800652c0  and     dword ptr [rbp+cbData], edi
0x1800652c3  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x1800652ca  xorps   xmm0, xmm0
0x1800652cd  xorps   xmm1, xmm1
0x1800652d0  xor     r8d, r8d; ulOptions
0x1800652d3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800652da  lea     r9d, [rdi+1]; samDesired
0x1800652de  movups  xmmword ptr [rbp+pDataIn.cbData], xmm0
0x1800652e2  movups  xmmword ptr [rbp+var_18.cbData], xmm1
0x1800652e6  call    cs:__imp_RegOpenKeyExW
0x1800652ed  nop     dword ptr [rax+rax+00h]
0x1800652f2  mov     ebx, eax
0x1800652f4  test    eax, eax
0x1800652f6  jnz     loc_1800653CA
0x1800652fc  mov     rcx, [rbp+hKey]; hKey
0x180065300  lea     rax, [rbp+cbData]
0x180065304  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180065309  xor     r9d, r9d; lpType
0x18006530c  and     [rsp+70h+lpData], rdi
0x180065311  xor     r8d, r8d; lpReserved
0x180065314  mov     rdx, rsi; lpValueName
0x180065317  call    cs:__imp_RegQueryValueExW
0x18006531e  nop     dword ptr [rax+rax+00h]
0x180065323  mov     ebx, eax
0x180065325  test    eax, eax
0x180065327  jnz     loc_1800653CA
0x18006532d  mov     edx, dword ptr [rbp+cbData]; uBytes
0x180065330  lea     ecx, [rdi+40h]; uFlags
0x180065333  call    cs:__imp_LocalAlloc
0x18006533a  nop     dword ptr [rax+rax+00h]
0x18006533f  mov     rdi, rax
0x180065342  test    rax, rax
0x180065345  jnz     short loc_180065357
0x180065347  call    cs:__imp_GetLastError
0x18006534e  nop     dword ptr [rax+rax+00h]
0x180065353  mov     ebx, eax
0x180065355  jmp     short loc_1800653CA
0x180065357  mov     rcx, [rbp+hKey]; hKey
0x18006535b  lea     rax, [rbp+cbData]
0x18006535f  mov     [rsp+70h+lpcbData], rax; dwFlags
0x180065364  xor     r9d, r9d; lpType
0x180065367  xor     r8d, r8d; lpReserved
0x18006536a  mov     [rsp+70h+lpData], rdi; pPromptStruct
0x18006536f  mov     rdx, rsi; lpValueName
0x180065372  call    cs:__imp_RegQueryValueExW
0x180065379  nop     dword ptr [rax+rax+00h]
0x18006537e  mov     ebx, eax
0x180065380  test    eax, eax
0x180065382  jnz     short loc_1800653CA
0x180065384  mov     eax, dword ptr [rbp+cbData]
0x180065387  lea     rcx, [rbp+pDataIn]; pDataIn
0x18006538b  mov     [rbp+pDataIn.cbData], eax
0x18006538e  xor     r9d, r9d; pvReserved
0x180065391  lea     rax, [rbp+var_18]
0x180065395  mov     [rbp+pDataIn.pbData], rdi
0x180065399  mov     [rsp+70h+pDataOut], rax; pDataOut
0x18006539e  xor     r8d, r8d; pOptionalEntropy
0x1800653a1  and     dword ptr [rsp+70h+lpcbData], ebx
0x1800653a5  xor     edx, edx; ppszDataDescr
0x1800653a7  and     [rsp+70h+lpData], 0
0x1800653ad  call    cs:__imp_CryptUnprotectData
0x1800653b4  nop     dword ptr [rax+rax+00h]
0x1800653b9  test    eax, eax
0x1800653bb  jz      short loc_180065347
0x1800653bd  mov     eax, [rbp+var_18.cbData]
0x1800653c0  mov     [r14], eax
0x1800653c3  mov     rax, [rbp+var_18.pbData]
0x1800653c7  mov     [r15], rax
0x1800653ca  mov     rcx, [rbp+hKey]; hKey
0x1800653ce  test    rcx, rcx
0x1800653d1  jz      short loc_1800653DF
0x1800653d3  call    cs:__imp_RegCloseKey
0x1800653da  nop     dword ptr [rax+rax+00h]
0x1800653df  test    rdi, rdi
0x1800653e2  jz      short loc_1800653F3
0x1800653e4  mov     rcx, rdi; hMem
0x1800653e7  call    cs:__imp_LocalFree
0x1800653ee  nop     dword ptr [rax+rax+00h]
0x1800653f3  mov     eax, ebx
0x1800653f5  jmp     short loc_1800653FC
0x1800653f7  mov     eax, 57h ; 'W'
0x1800653fc  lea     r11, [rsp+70h+var_s0]
0x180065401  mov     rbx, [r11+28h]
0x180065405  mov     rsi, [r11+30h]
0x180065409  mov     rdi, [r11+38h]
0x18006540d  mov     rsp, r11
0x180065410  pop     r15
0x180065412  pop     r14
0x180065414  pop     rbp
0x180065415  retn
```
