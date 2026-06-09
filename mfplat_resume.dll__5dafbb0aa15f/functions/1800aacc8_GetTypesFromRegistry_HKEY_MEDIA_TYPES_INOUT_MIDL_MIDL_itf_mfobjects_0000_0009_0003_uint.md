# GetTypesFromRegistry(HKEY__ *,_MEDIA_TYPES_INOUT,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 * *,uint *)

- ea: `0x1800aacc8`
- end: `0x1800aae4d`
- name: `?GetTypesFromRegistry@@YAJPEAUHKEY__@@W4_MEDIA_TYPES_INOUT@@PEAPEAU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAI@Z`
- size: `389`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056c20`
- `0x18005735c`
- `0x1800a8f20`

## callees

- `0x1800aacc8`
- `0x1801200d0`
- `0x180121581`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aad47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aadd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aad47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aadd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aad82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aad82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aad6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aadf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aad6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aadf4`

## pseudocode

```c
__int64 __fastcall GetTypesFromRegistry(HKEY a1, int a2, LPVOID *a3, DWORD *a4)
{
  const WCHAR *v6; // rsi
  LSTATUS v8; // eax
  signed int v9; // ebx
  BYTE *lpData; // rax
  LSTATUS v12; // eax
  void *v13; // rax
  DWORD cbData; // [rsp+30h] [rbp-89h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-85h] BYREF
  BYTE Data[160]; // [rsp+40h] [rbp-79h] BYREF

  *a3 = 0;
  *a4 = 0;
  Type[0] = 0;
  cbData = 160;
  v6 = L"InputTypes";
  if ( a2 )
    v6 = L"OutputTypes";
  v8 = RegQueryValueExW(a1, v6, 0, Type, Data, &cbData);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 == -2147024662 )
  {
    lpData = (BYTE *)CoTaskMemAlloc(cbData);
    *a3 = lpData;
    if ( !lpData )
    {
LABEL_7:
      v9 = -2147024882;
      goto LABEL_8;
    }
    v12 = RegQueryValueExW(a1, v6, 0, Type, lpData, &cbData);
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_8;
  }
  else
  {
    if ( v9 < 0 )
    {
      if ( v9 == -2147024894 )
        return 0;
      goto LABEL_8;
    }
    v13 = CoTaskMemAlloc(cbData);
    *a3 = v13;
    if ( !v13 )
      goto LABEL_7;
    memcpy_0(v13, Data, cbData);
  }
  if ( cbData >= 0x20 && Type[0] == 3 )
  {
    *a4 = cbData >> 5;
    return (unsigned int)v9;
  }
LABEL_8:
  CoTaskMemFree(*a3);
  *a3 = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800aacc8  mov     [rsp-8+arg_8], rbx
0x1800aaccd  push    rbp
0x1800aacce  push    rsi
0x1800aaccf  push    rdi
0x1800aacd0  push    r14
0x1800aacd2  push    r15
0x1800aacd4  lea     rbp, [rsp-37h]
0x1800aacd9  sub     rsp, 0F0h
0x1800aace0  mov     rax, cs:__security_cookie
0x1800aace7  xor     rax, rsp
0x1800aacea  mov     [rbp+57h+var_30], rax
0x1800aacee  test    edx, edx
0x1800aacf0  mov     qword ptr [r8], 0
0x1800aacf7  lea     rax, aOutputtypes; "OutputTypes"
0x1800aacfe  mov     dword ptr [r9], 0
0x1800aad05  mov     r14, r9
0x1800aad08  mov     [rsp+110h+Type], 0
0x1800aad10  mov     rdi, r8
0x1800aad13  mov     [rsp+110h+cbData], 0A0h
0x1800aad1b  lea     rsi, aInputtypes; "InputTypes"
0x1800aad22  mov     r15, rcx
0x1800aad25  cmovnz  rsi, rax
0x1800aad29  lea     r9, [rsp+110h+Type]; lpType
0x1800aad2e  lea     rax, [rsp+110h+cbData]
0x1800aad33  xor     r8d, r8d; lpReserved
0x1800aad36  mov     [rsp+110h+lpcbData], rax; lpcbData
0x1800aad3b  mov     rdx, rsi; lpValueName
0x1800aad3e  lea     rax, [rbp+57h+Data]
0x1800aad42  mov     [rsp+110h+lpData], rax; lpData
0x1800aad47  call    cs:__imp_RegQueryValueExW
0x1800aad4d  mov     ebx, eax
0x1800aad4f  test    eax, eax
0x1800aad51  jle     short loc_1800AAD5C
0x1800aad53  movzx   ebx, ax
0x1800aad56  or      ebx, 80070000h
0x1800aad5c  cmp     ebx, 800700EAh
0x1800aad62  jnz     loc_1800AADEC
0x1800aad68  mov     ecx, [rsp+110h+cbData]; cb
0x1800aad6c  call    cs:__imp_CoTaskMemAlloc
0x1800aad72  mov     [rdi], rax
0x1800aad75  test    rax, rax
0x1800aad78  jnz     short loc_1800AADB4
0x1800aad7a  mov     ebx, 8007000Eh
0x1800aad7f  mov     rcx, [rdi]; pv
0x1800aad82  call    cs:__imp_CoTaskMemFree
0x1800aad88  mov     qword ptr [rdi], 0
0x1800aad8f  mov     eax, ebx
0x1800aad91  mov     rcx, [rbp+57h+var_30]
0x1800aad95  xor     rcx, rsp; StackCookie
0x1800aad98  call    __security_check_cookie
0x1800aad9d  mov     rbx, [rsp+110h+arg_8]
0x1800aada5  add     rsp, 0F0h
0x1800aadac  pop     r15
0x1800aadae  pop     r14
0x1800aadb0  pop     rdi
0x1800aadb1  pop     rsi
0x1800aadb2  pop     rbp
0x1800aadb3  retn
0x1800aadb4  lea     rcx, [rsp+110h+cbData]
0x1800aadb9  xor     r8d, r8d; lpReserved
0x1800aadbc  mov     [rsp+110h+lpcbData], rcx; lpcbData
0x1800aadc1  lea     r9, [rsp+110h+Type]; lpType
0x1800aadc6  mov     rcx, r15; hKey
0x1800aadc9  mov     [rsp+110h+lpData], rax; lpData
0x1800aadce  mov     rdx, rsi; lpValueName
0x1800aadd1  call    cs:__imp_RegQueryValueExW
0x1800aadd7  mov     ebx, eax
0x1800aadd9  test    eax, eax
0x1800aaddb  jle     short loc_1800AADE6
0x1800aaddd  movzx   ebx, ax
0x1800aade0  or      ebx, 80070000h
0x1800aade6  test    ebx, ebx
0x1800aade8  js      short loc_1800AAD7F
0x1800aadea  jmp     short loc_1800AAE17
0x1800aadec  test    ebx, ebx
0x1800aadee  js      short loc_1800AAE3A
0x1800aadf0  mov     ecx, [rsp+110h+cbData]; cb
0x1800aadf4  call    cs:__imp_CoTaskMemAlloc
0x1800aadfa  mov     [rdi], rax
0x1800aadfd  test    rax, rax
0x1800aae00  jz      loc_1800AAD7A
0x1800aae06  mov     r8d, [rsp+110h+cbData]; Size
0x1800aae0b  lea     rdx, [rbp+57h+Data]; Src
0x1800aae0f  mov     rcx, rax; void *
0x1800aae12  call    memcpy_0
0x1800aae17  mov     eax, [rsp+110h+cbData]
0x1800aae1b  cmp     eax, 20h ; ' '
0x1800aae1e  jb      loc_1800AAD7F
0x1800aae24  cmp     [rsp+110h+Type], 3
0x1800aae29  jnz     loc_1800AAD7F
0x1800aae2f  shr     eax, 5
0x1800aae32  mov     [r14], eax
0x1800aae35  jmp     loc_1800AAD8F
0x1800aae3a  cmp     ebx, 80070002h
0x1800aae40  jnz     loc_1800AAD7F
0x1800aae46  xor     ebx, ebx
0x1800aae48  jmp     loc_1800AAD8F
```
