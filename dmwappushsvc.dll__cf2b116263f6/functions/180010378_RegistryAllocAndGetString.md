# RegistryAllocAndGetString

- ea: `0x180010378`
- end: `0x180010445`
- name: `RegistryAllocAndGetString`
- size: `205`
- prototype: `LSTATUS __fastcall(HKEY hKey, __int64, BYTE **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010770`

## callees

- `0x180010378`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800103ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800103ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800103c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010423`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800103c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010423`

## pseudocode

```c
LSTATUS __fastcall RegistryAllocAndGetString(HKEY hKey, __int64 a2, BYTE **a3)
{
  LSTATUS result; // eax
  bool v6; // cc
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *lpData; // rax
  DWORD dwBytes; // [rsp+48h] [rbp+10h] BYREF
  int dwBytes_4; // [rsp+4Ch] [rbp+14h]
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF

  dwBytes_4 = HIDWORD(a2);
  Type = 0;
  dwBytes = 0;
  result = RegQueryValueExW(hKey, L"LastSoapErrorTraceId", 0, &Type, 0, &dwBytes);
  v6 = result <= 0;
  if ( !result )
  {
    if ( Type != 1 )
      return -2147024809;
    v7 = dwBytes;
    ProcessHeap = GetProcessHeap();
    lpData = (BYTE *)HeapAlloc(ProcessHeap, 8u, v7);
    *a3 = lpData;
    if ( !lpData )
      return -2147024882;
    result = RegQueryValueExW(hKey, L"LastSoapErrorTraceId", 0, &Type, lpData, &dwBytes);
    v6 = result <= 0;
  }
  if ( !v6 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180010378  mov     r11, rsp
0x18001037b  mov     [r11+8], rbx
0x18001037f  mov     [r11+18h], rsi
0x180010383  mov     [r11+10h], rdx
0x180010387  push    rdi
0x180010388  sub     rsp, 30h
0x18001038c  lea     rax, [r11+10h]
0x180010390  mov     [rsp+38h+Type], 0
0x180010398  mov     rsi, r8
0x18001039b  mov     [r11-10h], rax
0x18001039f  lea     r9, [r11+20h]; lpType
0x1800103a3  mov     qword ptr [r11-18h], 0
0x1800103ab  xor     r8d, r8d; lpReserved
0x1800103ae  mov     dword ptr [rsp+38h+dwBytes], 0
0x1800103b6  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x1800103bd  mov     rdi, rcx
0x1800103c0  call    cs:__imp_RegQueryValueExW
0x1800103c6  test    eax, eax
0x1800103c8  jnz     short loc_18001042B
0x1800103ca  cmp     [rsp+38h+Type], 1
0x1800103cf  jz      short loc_1800103D8
0x1800103d1  mov     eax, 80070057h
0x1800103d6  jmp     short loc_180010435
0x1800103d8  mov     ebx, dword ptr [rsp+38h+dwBytes]
0x1800103dc  call    cs:__imp_GetProcessHeap
0x1800103e2  mov     r8d, ebx; dwBytes
0x1800103e5  mov     edx, 8; dwFlags
0x1800103ea  mov     rcx, rax; hHeap
0x1800103ed  call    cs:__imp_HeapAlloc
0x1800103f3  mov     [rsi], rax
0x1800103f6  test    rax, rax
0x1800103f9  jnz     short loc_180010402
0x1800103fb  mov     eax, 8007000Eh
0x180010400  jmp     short loc_180010435
0x180010402  lea     rcx, [rsp+38h+dwBytes]
0x180010407  xor     r8d, r8d; lpReserved
0x18001040a  mov     [rsp+38h+lpcbData], rcx; lpcbData
0x18001040f  lea     r9, [rsp+38h+Type]; lpType
0x180010414  mov     rcx, rdi; hKey
0x180010417  mov     [rsp+38h+lpData], rax; lpData
0x18001041c  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x180010423  call    cs:__imp_RegQueryValueExW
0x180010429  test    eax, eax
0x18001042b  jle     short loc_180010435
0x18001042d  movzx   eax, ax
0x180010430  or      eax, 80070000h
0x180010435  mov     rbx, [rsp+38h+arg_0]
0x18001043a  mov     rsi, [rsp+38h+arg_10]
0x18001043f  add     rsp, 30h
0x180010443  pop     rdi
0x180010444  retn
```
