# RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)

- ea: `0x180011cb4`
- end: `0x180011da3`
- name: `?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z`
- size: `239`
- prototype: `int(unsigned __int16 **, struct ATL::CRegKey *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d670`
- `0x18000e2a0`
- `0x18000ebf8`

## callees

- `0x180011cb4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180011cfd`
- `ADVAPI32!RegQueryValueExW` at `0x180011d53`
- `ADVAPI32!RegQueryValueExW` at `0x180011cfd`
- `ADVAPI32!RegQueryValueExW` at `0x180011d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011d22`

## pseudocode

```c
LSTATUS __fastcall RegUtilLoadStringWithAlloc(BYTE **a1, HKEY *a2, const unsigned __int16 *a3)
{
  LSTATUS v6; // ebx
  bool v7; // cc
  BYTE *lpData; // rdi
  LSTATUS result; // eax
  SIZE_T cb; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  Type = 1;
  LODWORD(cb) = 0;
  v6 = RegQueryValueExW(*a2, a3, 0, &Type, 0, (LPDWORD)&cb);
  if ( v6 != 234 )
  {
    v7 = v6 <= 0;
    if ( v6 )
    {
LABEL_8:
      if ( !v7 )
        return (unsigned __int16)v6 | 0x80070000;
      return v6;
    }
    if ( !(_DWORD)cb )
      return v6;
  }
  lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
  if ( lpData )
  {
    result = RegQueryValueExW(*a2, a3, 0, &Type, lpData, (LPDWORD)&cb);
    v6 = result;
    if ( !result )
    {
      *a1 = lpData;
      return result;
    }
    CoTaskMemFree(lpData);
    v7 = v6 <= 0;
    goto LABEL_8;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x180011cb4  mov     r11, rsp
0x180011cb7  mov     [r11+8], rbx
0x180011cbb  mov     [r11+18h], rbp
0x180011cbf  push    rsi
0x180011cc0  push    rdi
0x180011cc1  push    r14
0x180011cc3  sub     rsp, 30h
0x180011cc7  mov     r14, rdx
0x180011cca  mov     [rsp+48h+Type], 1
0x180011cd2  mov     rbp, r8
0x180011cd5  mov     dword ptr [rsp+48h+cb], 0
0x180011cdd  lea     rax, [r11+10h]
0x180011ce1  mov     rsi, rcx
0x180011ce4  mov     [r11-20h], rax
0x180011ce8  lea     r9, [r11+20h]; lpType
0x180011cec  mov     rcx, [r14]; hKey
0x180011cef  xor     r8d, r8d; lpReserved
0x180011cf2  mov     rdx, rbp; lpValueName
0x180011cf5  mov     qword ptr [r11-28h], 0
0x180011cfd  call    cs:__imp_RegQueryValueExW
0x180011d04  nop     dword ptr [rax+rax+00h]
0x180011d09  mov     ebx, eax
0x180011d0b  mov     eax, dword ptr [rsp+48h+cb]
0x180011d0f  cmp     ebx, 0EAh
0x180011d15  jz      short loc_180011D1F
0x180011d17  test    ebx, ebx
0x180011d19  jnz     short loc_180011D7B
0x180011d1b  test    eax, eax
0x180011d1d  jz      short loc_180011D86
0x180011d1f  mov     rcx, rax; cb
0x180011d22  call    cs:__imp_CoTaskMemAlloc
0x180011d29  nop     dword ptr [rax+rax+00h]
0x180011d2e  mov     rdi, rax
0x180011d31  test    rax, rax
0x180011d34  jz      short loc_180011D8A
0x180011d36  mov     rcx, [r14]; hKey
0x180011d39  lea     rax, [rsp+48h+cb]
0x180011d3e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180011d43  lea     r9, [rsp+48h+Type]; lpType
0x180011d48  xor     r8d, r8d; lpReserved
0x180011d4b  mov     [rsp+48h+lpData], rdi; lpData
0x180011d50  mov     rdx, rbp; lpValueName
0x180011d53  call    cs:__imp_RegQueryValueExW
0x180011d5a  nop     dword ptr [rax+rax+00h]
0x180011d5f  mov     ebx, eax
0x180011d61  test    eax, eax
0x180011d63  jnz     short loc_180011D6A
0x180011d65  mov     [rsi], rdi
0x180011d68  jmp     short loc_180011D8F
0x180011d6a  mov     rcx, rdi; pv
0x180011d6d  call    cs:__imp_CoTaskMemFree
0x180011d74  nop     dword ptr [rax+rax+00h]
0x180011d79  test    ebx, ebx
0x180011d7b  jle     short loc_180011D86
0x180011d7d  movzx   ebx, bx
0x180011d80  or      ebx, 80070000h
0x180011d86  mov     eax, ebx
0x180011d88  jmp     short loc_180011D8F
0x180011d8a  mov     eax, 8007000Eh
0x180011d8f  mov     rbx, [rsp+48h+arg_0]
0x180011d94  mov     rbp, [rsp+48h+arg_10]
0x180011d99  add     rsp, 30h
0x180011d9d  pop     r14
0x180011d9f  pop     rdi
0x180011da0  pop     rsi
0x180011da1  retn
```
