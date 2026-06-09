# SetSelectDevParams

- ea: `0x180028ad4`
- end: `0x180028c17`
- name: `SetSelectDevParams`
- size: `323`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800148bc`
- `0x180027910`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180028ad4`

## import_xrefs

- `USER32!LoadStringW` at `0x180028b89`
- `USER32!LoadStringW` at `0x180028bad`
- `USER32!LoadStringW` at `0x180028bd1`
- `USER32!LoadStringW` at `0x180028b89`
- `USER32!LoadStringW` at `0x180028bad`
- `USER32!LoadStringW` at `0x180028bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b3f`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180028bec`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180028bec`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180028b35`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180028b35`

## pseudocode

```c
BOOL __fastcall SetSelectDevParams(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)
{
  struct _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+30h] [rbp-4D8h] BYREF
  WCHAR Buffer[60]; // [rsp+38h] [rbp-4D0h] BYREF
  WCHAR v7[256]; // [rsp+B0h] [rbp-458h] BYREF
  WCHAR v8[288]; // [rsp+2B0h] [rbp-258h] BYREF

  memset_0(&ClassInstallParams.InstallFunction, 0, 0x4B8u);
  ClassInstallParams.cbSize = 8;
  ClassInstallParams.InstallFunction = 1;
  if ( !SetupDiGetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, &ClassInstallParams, 0x4BCu, 0) )
  {
    if ( GetLastError() != -536870379 )
      return 0;
    memset_0(Buffer, 0, 0x4B4u);
    ClassInstallParams.cbSize = 8;
    ClassInstallParams.InstallFunction = 1;
  }
  if ( LoadStringW(ghInst, 0x3E9u, Buffer, 60)
    && LoadStringW(ghInst, 0x3EAu, v7, 256)
    && LoadStringW(ghInst, 0x3ECu, v8, 30) )
  {
    return SetupDiSetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, &ClassInstallParams, 0x4BCu);
  }
  return 0;
}

```

## disassembly

```asm
0x180028ad4  mov     [rsp+arg_10], rbx
0x180028ad9  push    rdi
0x180028ada  sub     rsp, 500h
0x180028ae1  mov     rax, cs:__security_cookie
0x180028ae8  xor     rax, rsp
0x180028aeb  mov     [rsp+508h+var_18], rax
0x180028af3  mov     rdi, rdx
0x180028af6  mov     rbx, rcx
0x180028af9  xor     edx, edx; Val
0x180028afb  lea     rcx, [rsp+508h+ClassInstallParams.InstallFunction]; void *
0x180028b00  mov     r8d, 4B8h; Size
0x180028b06  call    memset_0
0x180028b0b  mov     r9d, 4BCh; ClassInstallParamsSize
0x180028b11  mov     [rsp+508h+ClassInstallParams.cbSize], 8
0x180028b19  lea     r8, [rsp+508h+ClassInstallParams]; ClassInstallParams
0x180028b1e  mov     [rsp+508h+ClassInstallParams.InstallFunction], 1
0x180028b26  mov     rdx, rdi; DeviceInfoData
0x180028b29  mov     [rsp+508h+RequiredSize], 0; RequiredSize
0x180028b32  mov     rcx, rbx; DeviceInfoSet
0x180028b35  call    cs:__imp_SetupDiGetClassInstallParamsW
0x180028b3b  test    eax, eax
0x180028b3d  jnz     short loc_180028B72
0x180028b3f  call    cs:__imp_GetLastError
0x180028b45  cmp     eax, 0E0000215h
0x180028b4a  jnz     loc_180028BF4
0x180028b50  xor     edx, edx; Val
0x180028b52  lea     rcx, [rsp+508h+Buffer]; void *
0x180028b57  mov     r8d, 4B4h; Size
0x180028b5d  call    memset_0
0x180028b62  mov     [rsp+508h+ClassInstallParams.cbSize], 8
0x180028b6a  mov     [rsp+508h+ClassInstallParams.InstallFunction], 1
0x180028b72  mov     rcx, cs:ghInst; hInstance
0x180028b79  lea     r8, [rsp+508h+Buffer]; lpBuffer
0x180028b7e  mov     r9d, 3Ch ; '<'; cchBufferMax
0x180028b84  mov     edx, 3E9h; uID
0x180028b89  call    cs:__imp_LoadStringW
0x180028b8f  test    eax, eax
0x180028b91  jz      short loc_180028BF4
0x180028b93  mov     rcx, cs:ghInst; hInstance
0x180028b9a  lea     r8, [rsp+508h+var_458]; lpBuffer
0x180028ba2  mov     r9d, 100h; cchBufferMax
0x180028ba8  mov     edx, 3EAh; uID
0x180028bad  call    cs:__imp_LoadStringW
0x180028bb3  test    eax, eax
0x180028bb5  jz      short loc_180028BF4
0x180028bb7  mov     rcx, cs:ghInst; hInstance
0x180028bbe  lea     r8, [rsp+508h+var_258]; lpBuffer
0x180028bc6  mov     r9d, 1Eh; cchBufferMax
0x180028bcc  mov     edx, 3ECh; uID
0x180028bd1  call    cs:__imp_LoadStringW
0x180028bd7  test    eax, eax
0x180028bd9  jz      short loc_180028BF4
0x180028bdb  mov     r9d, 4BCh; ClassInstallParamsSize
0x180028be1  lea     r8, [rsp+508h+ClassInstallParams]; ClassInstallParams
0x180028be6  mov     rdx, rdi; DeviceInfoData
0x180028be9  mov     rcx, rbx; DeviceInfoSet
0x180028bec  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180028bf2  jmp     short loc_180028BF6
0x180028bf4  xor     eax, eax
0x180028bf6  mov     rcx, [rsp+508h+var_18]
0x180028bfe  xor     rcx, rsp; StackCookie
0x180028c01  call    __security_check_cookie
0x180028c06  mov     rbx, [rsp+508h+arg_10]
0x180028c0e  add     rsp, 500h
0x180028c15  pop     rdi
0x180028c16  retn
```
