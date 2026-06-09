# HrRegQueryValueWithAlloc(HKEY__ *,wchar_t const *,ulong *,uchar * *,ulong *)

- ea: `0x1800355c0`
- end: `0x180035721`
- name: `?HrRegQueryValueWithAlloc@@YAJPEAUHKEY__@@PEB_WPEAKPEAPEAE2@Z`
- size: `353`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, LPDWORD lpType@<r8>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180089060`
- `0x1800e7c30`

## callees

- `0x1800355c0`
- `0x1800a88a0`
- `0x1800aba25`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035716`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035629`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800356f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035629`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800356f3`

## pseudocode

```c
__int64 __fastcall HrRegQueryValueWithAlloc(
        HKEY hKey,
        LPCWSTR lpValueName,
        LPDWORD lpType,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  LSTATUS Value; // eax
  unsigned int v10; // esi
  __int64 result; // rax
  BYTE *lpData; // rax
  unsigned __int8 *v13; // rbx
  unsigned int v14; // esi
  LSTATUS v15; // eax
  DWORD cbData[4]; // [rsp+30h] [rbp-138h] BYREF
  BYTE Data[208]; // [rsp+40h] [rbp-128h] BYREF

  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  cbData[0] = 200;
  Value = RegQueryValueExW(hKey, lpValueName, 0, lpType, Data, cbData);
  v10 = Value;
  if ( Value > 0 )
    v10 = (unsigned __int16)Value | 0x80070000;
  result = 0;
  if ( v10 != -2147024662 )
    result = v10;
  if ( !(_DWORD)result )
  {
    lpData = (BYTE *)CoTaskMemAlloc(cbData[0]);
    v13 = lpData;
    if ( !lpData )
      return 2147942414LL;
    if ( v10 == -2147024662 )
    {
      v15 = RegQueryValueExW(hKey, lpValueName, 0, lpType, lpData, cbData);
      v14 = v15;
      if ( v15 > 0 )
        v14 = (unsigned __int16)v15 | 0x80070000;
      if ( v14 )
        goto LABEL_13;
    }
    else
    {
      memcpy_0(lpData, Data, cbData[0]);
      v14 = 0;
    }
    *a4 = v13;
    v13 = 0;
    if ( a5 )
      *a5 = cbData[0];
LABEL_13:
    if ( v13 )
      CoTaskMemFree(v13);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x1800355c0  push    rbp
0x1800355c2  push    rsi
0x1800355c3  push    rdi
0x1800355c4  push    r12
0x1800355c6  push    r13
0x1800355c8  push    r14
0x1800355ca  push    r15
0x1800355cc  sub     rsp, 130h
0x1800355d3  mov     rax, cs:__security_cookie
0x1800355da  xor     rax, rsp
0x1800355dd  mov     [rsp+168h+var_58], rax
0x1800355e5  mov     rdi, [rsp+168h+arg_20]
0x1800355ed  xor     r13d, r13d
0x1800355f0  mov     [r9], r13
0x1800355f3  mov     r14, r9
0x1800355f6  mov     r12, r8
0x1800355f9  mov     r15, rdx
0x1800355fc  mov     rbp, rcx
0x1800355ff  test    rdi, rdi
0x180035602  jz      short loc_180035607
0x180035604  mov     [rdi], r13d
0x180035607  lea     rax, [rsp+168h+cbData]
0x18003560c  mov     [rsp+168h+cbData], 0C8h
0x180035614  mov     [rsp+168h+lpcbData], rax; lpcbData
0x180035619  mov     r9, r12; lpType
0x18003561c  lea     rax, [rsp+168h+Data]
0x180035621  xor     r8d, r8d; lpReserved
0x180035624  mov     [rsp+168h+lpData], rax; lpData
0x180035629  call    cs:__imp_RegQueryValueExW
0x18003562f  mov     esi, eax
0x180035631  test    eax, eax
0x180035633  jg      loc_1800356CA
0x180035639  cmp     esi, 800700EAh
0x18003563f  mov     eax, r13d
0x180035642  cmovnz  eax, esi
0x180035645  test    eax, eax
0x180035647  jnz     short loc_1800356A0
0x180035649  mov     ecx, [rsp+168h+cbData]; cb
0x18003564d  mov     [rsp+168h+var_40], rbx
0x180035655  call    cs:__imp_CoTaskMemAlloc
0x18003565b  mov     rbx, rax
0x18003565e  test    rax, rax
0x180035661  jz      short loc_1800356C3
0x180035663  cmp     esi, 800700EAh
0x180035669  jz      short loc_1800356D8
0x18003566b  mov     r8d, [rsp+168h+cbData]; Size
0x180035670  lea     rdx, [rsp+168h+Data]; Src
0x180035675  mov     rcx, rax; void *
0x180035678  call    memcpy_0
0x18003567d  mov     esi, r13d
0x180035680  mov     [r14], rbx
0x180035683  mov     rbx, r13
0x180035686  test    rdi, rdi
0x180035689  jz      short loc_180035691
0x18003568b  mov     eax, [rsp+168h+cbData]
0x18003568f  mov     [rdi], eax
0x180035691  test    rbx, rbx
0x180035694  jnz     short loc_180035713
0x180035696  mov     eax, esi
0x180035698  mov     rbx, [rsp+168h+var_40]
0x1800356a0  mov     rcx, [rsp+168h+var_58]
0x1800356a8  xor     rcx, rsp; StackCookie
0x1800356ab  call    __security_check_cookie
0x1800356b0  add     rsp, 130h
0x1800356b7  pop     r15
0x1800356b9  pop     r14
0x1800356bb  pop     r13
0x1800356bd  pop     r12
0x1800356bf  pop     rdi
0x1800356c0  pop     rsi
0x1800356c1  pop     rbp
0x1800356c2  retn
0x1800356c3  mov     eax, 8007000Eh
0x1800356c8  jmp     short loc_180035698
0x1800356ca  movzx   esi, ax
0x1800356cd  or      esi, 80070000h
0x1800356d3  jmp     loc_180035639
0x1800356d8  lea     rax, [rsp+168h+cbData]
0x1800356dd  mov     r9, r12; lpType
0x1800356e0  mov     [rsp+168h+lpcbData], rax; lpcbData
0x1800356e5  xor     r8d, r8d; lpReserved
0x1800356e8  mov     rdx, r15; lpValueName
0x1800356eb  mov     [rsp+168h+lpData], rbx; lpData
0x1800356f0  mov     rcx, rbp; hKey
0x1800356f3  call    cs:__imp_RegQueryValueExW
0x1800356f9  mov     esi, eax
0x1800356fb  test    eax, eax
0x1800356fd  jg      short loc_180035708
0x1800356ff  test    esi, esi
0x180035701  jnz     short loc_180035691
0x180035703  jmp     loc_180035680
0x180035708  movzx   esi, ax
0x18003570b  or      esi, 80070000h
0x180035711  jmp     short loc_1800356FF
0x180035713  mov     rcx, rbx; pv
0x180035716  call    cs:__imp_CoTaskMemFree
0x18003571c  jmp     loc_180035696
```
