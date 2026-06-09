# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *)

- ea: `0x18001a67c`
- end: `0x18001a83e`
- name: `?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019cd0`

## callees

- `0x18001a67c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a70b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a77b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a70b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a77b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a81f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a81f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a6c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a73a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a6c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a73a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a76a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a79c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a76a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a79c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        __int64 a1,
        HKEY a2,
        __int64 a3)
{
  BYTE *lpData; // rdi
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  __int64 v9; // rsi
  DWORD v10; // eax
  DWORD v11; // ebp
  WCHAR *v12; // rax
  WCHAR *v13; // rsi
  DWORD v14; // eax
  DWORD v15; // r15d
  __int64 v16; // rax
  DWORD cb; // [rsp+70h] [rbp+18h] BYREF
  int cb_4; // [rsp+74h] [rbp+1Ch]
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  cb_4 = HIDWORD(a3);
  Type = 0;
  cb = 0;
  lpData = 0;
  v6 = RegQueryValueExW(a2, L"Name", 0, &Type, 0, &cb);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    if ( Type - 1 > 1 || !cb || (cb & 1) != 0 )
      goto LABEL_26;
    lpData = (BYTE *)CoTaskMemAlloc(cb);
    if ( !lpData )
    {
LABEL_14:
      v7 = -2147024882;
      goto LABEL_27;
    }
    v8 = RegQueryValueExW(a2, L"Name", 0, &Type, lpData, &cb);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 >= 0 )
    {
      v9 = (cb >> 1) - 1;
      if ( Type == 2 )
      {
        v10 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v11 = v10;
        if ( v10 )
        {
          v12 = (WCHAR *)CoTaskMemAlloc(2LL * v10);
          v13 = v12;
          if ( !v12 )
            goto LABEL_14;
          v14 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v12, v11);
          v15 = v14;
          if ( !v14 || v14 > v11 )
          {
            v7 = -2147024774;
            CoTaskMemFree(v13);
            goto LABEL_27;
          }
          v7 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v13;
          v9 = v15 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v9] )
      {
        if ( *(_QWORD *)a1 )
        {
          CoTaskMemFree(*(LPVOID *)a1);
          *(_QWORD *)a1 = 0;
        }
        *(_QWORD *)(a1 + 8) = 0;
        *(_QWORD *)(a1 + 16) = 0;
        if ( lpData )
        {
          v16 = (unsigned int)(v9 + 1);
          if ( (_DWORD)v9 != -1 )
          {
            *(_QWORD *)a1 = lpData;
            *(_QWORD *)(a1 + 8) = v16 - 1;
            *(_QWORD *)(a1 + 16) = (unsigned int)v16;
            *(_WORD *)&lpData[2 * (unsigned int)v16 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_27;
      }
LABEL_26:
      v7 = -2147024883;
    }
  }
LABEL_27:
  CoTaskMemFree(lpData);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a67c  mov     r11, rsp
0x18001a67f  mov     [r11+8], rbx
0x18001a683  mov     [r11+10h], rbp
0x18001a687  mov     [r11+18h], r8
0x18001a68b  push    rsi
0x18001a68c  push    rdi
0x18001a68d  push    r12
0x18001a68f  push    r14
0x18001a691  push    r15
0x18001a693  sub     rsp, 30h
0x18001a697  xor     r12d, r12d
0x18001a69a  lea     rax, [r11+18h]
0x18001a69e  mov     rsi, rdx
0x18001a6a1  mov     [r11-30h], rax
0x18001a6a5  mov     r14, rcx
0x18001a6a8  mov     [r11-38h], r12
0x18001a6ac  mov     rcx, rsi; hKey
0x18001a6af  mov     [r11+20h], r12d
0x18001a6b3  lea     r9, [r11+20h]; lpType
0x18001a6b7  mov     [r11+18h], r12d
0x18001a6bb  xor     r8d, r8d; lpReserved
0x18001a6be  lea     rdx, aName; "Name"
0x18001a6c5  mov     edi, r12d
0x18001a6c8  call    cs:__imp_RegQueryValueExW
0x18001a6ce  mov     ebx, eax
0x18001a6d0  mov     ebp, 80070000h
0x18001a6d5  test    eax, eax
0x18001a6d7  jle     short loc_18001A6DE
0x18001a6d9  movzx   ebx, ax
0x18001a6dc  or      ebx, ebp
0x18001a6de  test    ebx, ebx
0x18001a6e0  js      loc_18001A81C
0x18001a6e6  mov     eax, [rsp+58h+Type]
0x18001a6ea  dec     eax
0x18001a6ec  cmp     eax, 1
0x18001a6ef  ja      loc_18001A817
0x18001a6f5  mov     eax, dword ptr [rsp+58h+cb]
0x18001a6f9  test    eax, eax
0x18001a6fb  jz      loc_18001A817
0x18001a701  test    al, 1
0x18001a703  jnz     loc_18001A817
0x18001a709  mov     ecx, eax; cb
0x18001a70b  call    cs:__imp_CoTaskMemAlloc
0x18001a711  mov     rdi, rax
0x18001a714  test    rax, rax
0x18001a717  jz      short loc_18001A789
0x18001a719  lea     rax, [rsp+58h+cb]
0x18001a71e  xor     r8d, r8d; lpReserved
0x18001a721  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001a726  lea     r9, [rsp+58h+Type]; lpType
0x18001a72b  lea     rdx, aName; "Name"
0x18001a732  mov     [rsp+58h+lpData], rdi; lpData
0x18001a737  mov     rcx, rsi; hKey
0x18001a73a  call    cs:__imp_RegQueryValueExW
0x18001a740  mov     ebx, eax
0x18001a742  test    eax, eax
0x18001a744  jle     short loc_18001A74B
0x18001a746  movzx   ebx, ax
0x18001a749  or      ebx, ebp
0x18001a74b  test    ebx, ebx
0x18001a74d  js      loc_18001A81C
0x18001a753  mov     esi, dword ptr [rsp+58h+cb]
0x18001a757  shr     esi, 1
0x18001a759  dec     esi
0x18001a75b  cmp     [rsp+58h+Type], 2
0x18001a760  jnz     short loc_18001A7C0
0x18001a762  xor     r8d, r8d; nSize
0x18001a765  xor     edx, edx; lpDst
0x18001a767  mov     rcx, rdi; lpSrc
0x18001a76a  call    cs:__imp_ExpandEnvironmentStringsW
0x18001a770  mov     ebp, eax
0x18001a772  test    eax, eax
0x18001a774  jz      short loc_18001A7C0
0x18001a776  mov     ecx, ebp
0x18001a778  add     rcx, rcx; cb
0x18001a77b  call    cs:__imp_CoTaskMemAlloc
0x18001a781  mov     rsi, rax
0x18001a784  test    rax, rax
0x18001a787  jnz     short loc_18001A793
0x18001a789  mov     ebx, 8007000Eh
0x18001a78e  jmp     loc_18001A81C
0x18001a793  mov     r8d, ebp; nSize
0x18001a796  mov     rdx, rsi; lpDst
0x18001a799  mov     rcx, rdi; lpSrc
0x18001a79c  call    cs:__imp_ExpandEnvironmentStringsW
0x18001a7a2  mov     r15d, eax
0x18001a7a5  test    eax, eax
0x18001a7a7  jz      short loc_18001A807
0x18001a7a9  cmp     eax, ebp
0x18001a7ab  ja      short loc_18001A807
0x18001a7ad  mov     rcx, rdi; pv
0x18001a7b0  mov     ebx, r12d
0x18001a7b3  call    cs:__imp_CoTaskMemFree
0x18001a7b9  mov     rdi, rsi
0x18001a7bc  lea     esi, [r15-1]
0x18001a7c0  cmp     [rdi+rsi*2], r12w
0x18001a7c5  jnz     short loc_18001A817
0x18001a7c7  mov     rcx, [r14]; pv
0x18001a7ca  test    rcx, rcx
0x18001a7cd  jz      short loc_18001A7D8
0x18001a7cf  call    cs:__imp_CoTaskMemFree
0x18001a7d5  mov     [r14], r12
0x18001a7d8  mov     [r14+8], r12
0x18001a7dc  mov     [r14+10h], r12
0x18001a7e0  test    rdi, rdi
0x18001a7e3  jz      short loc_18001A802
0x18001a7e5  lea     eax, [rsi+1]
0x18001a7e8  mov     ecx, eax
0x18001a7ea  test    eax, eax
0x18001a7ec  jz      short loc_18001A802
0x18001a7ee  dec     rax
0x18001a7f1  mov     [r14], rdi
0x18001a7f4  mov     [r14+8], rax
0x18001a7f8  mov     [r14+10h], rcx
0x18001a7fc  mov     [rdi+rcx*2-2], r12w
0x18001a802  mov     rdi, r12
0x18001a805  jmp     short loc_18001A81C
0x18001a807  mov     rcx, rsi; pv
0x18001a80a  mov     ebx, 8007007Ah
0x18001a80f  call    cs:__imp_CoTaskMemFree
0x18001a815  jmp     short loc_18001A81C
0x18001a817  mov     ebx, 8007000Dh
0x18001a81c  mov     rcx, rdi; pv
0x18001a81f  call    cs:__imp_CoTaskMemFree
0x18001a825  mov     rbp, [rsp+58h+arg_8]
0x18001a82a  mov     eax, ebx
0x18001a82c  mov     rbx, [rsp+58h+arg_0]
0x18001a831  add     rsp, 30h
0x18001a835  pop     r15
0x18001a837  pop     r14
0x18001a839  pop     r12
0x18001a83b  pop     rdi
0x18001a83c  pop     rsi
0x18001a83d  retn
```
