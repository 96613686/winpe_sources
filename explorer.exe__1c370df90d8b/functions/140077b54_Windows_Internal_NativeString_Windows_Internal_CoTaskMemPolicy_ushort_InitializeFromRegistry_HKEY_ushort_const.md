# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x140077b54`
- end: `0x140077d0c`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140077ac8`

## callees

- `0x140034d20`
- `0x140077b54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140077b9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140077c11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140077b9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140077c11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140077c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140077c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140077cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140077c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140077c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140077cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140077be3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140077ca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140077be3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140077ca1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140077c59`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140077c90`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140077c59`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140077c90`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        const WCHAR *a3)
{
  BYTE *lpData; // rdi
  LSTATUS Value; // eax
  signed int v8; // ebx
  LSTATUS v9; // eax
  DWORD v11; // r14d
  __int64 v12; // rsi
  DWORD v13; // eax
  DWORD v14; // ebp
  WCHAR *v15; // rax
  WCHAR *v16; // rsi
  __int64 v17; // rax
  DWORD Type[14]; // [rsp+30h] [rbp-38h] BYREF
  SIZE_T cb; // [rsp+88h] [rbp+20h] BYREF

  Type[0] = 0;
  LODWORD(cb) = 0;
  lpData = 0;
  Value = RegQueryValueExW(a2, a3, 0, Type, 0, (LPDWORD)&cb);
  v8 = Value;
  if ( Value > 0 )
    v8 = (unsigned __int16)Value | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( Type[0] - 1 <= 1 && (_DWORD)cb && (cb & 1) == 0 )
    {
      lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
      if ( !lpData )
      {
LABEL_12:
        v8 = -2147024882;
        goto LABEL_11;
      }
      v9 = RegQueryValueExW(a2, a3, 0, Type, lpData, (LPDWORD)&cb);
      v8 = v9;
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      if ( v8 < 0 )
        goto LABEL_11;
      v12 = ((unsigned int)cb >> 1) - 1;
      if ( Type[0] == 2 )
      {
        v13 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v14 = v13;
        if ( v13 )
        {
          v15 = (WCHAR *)CoTaskMemAlloc(2LL * v13);
          v16 = v15;
          if ( !v15 )
            goto LABEL_12;
          v11 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v15, v14);
          if ( !v11 || v11 > v14 )
          {
            v8 = -2147024774;
            CoTaskMemFree(v16);
            goto LABEL_11;
          }
          v8 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v16;
          v12 = v11 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v12] )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
        if ( lpData )
        {
          v17 = (unsigned int)(v12 + 1);
          if ( (_DWORD)v12 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v17 - 1);
            a1[2] = (BYTE *)(unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_11;
      }
    }
    v8 = -2147024883;
  }
LABEL_11:
  CoTaskMemFree(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140077b54  mov     r11, rsp
0x140077b57  mov     [r11+8], rbx
0x140077b5b  mov     [r11+10h], rbp
0x140077b5f  mov     [r11+20h], r9b
0x140077b63  push    rsi
0x140077b64  push    rdi
0x140077b65  push    r12
0x140077b67  push    r14
0x140077b69  push    r15
0x140077b6b  sub     rsp, 40h
0x140077b6f  xor     r12d, r12d
0x140077b72  lea     rax, [r11+20h]
0x140077b76  mov     rsi, r8
0x140077b79  mov     [r11-40h], rax
0x140077b7d  mov     rbp, rdx
0x140077b80  mov     [r11-48h], r12
0x140077b84  mov     r15, rcx
0x140077b87  mov     [r11-38h], r12d
0x140077b8b  mov     rdx, rsi; lpValueName
0x140077b8e  mov     [r11+20h], r12d
0x140077b92  mov     rcx, rbp; hKey
0x140077b95  lea     r9, [r11-38h]; lpType
0x140077b99  xor     r8d, r8d; lpReserved
0x140077b9c  mov     edi, r12d
0x140077b9f  call    cs:__imp_RegQueryValueExW
0x140077ba5  mov     ebx, eax
0x140077ba7  mov     r14d, 80070000h
0x140077bad  test    eax, eax
0x140077baf  jle     short loc_140077BB7
0x140077bb1  movzx   ebx, ax
0x140077bb4  or      ebx, r14d
0x140077bb7  test    ebx, ebx
0x140077bb9  js      short loc_140077C27
0x140077bbb  mov     eax, [rsp+68h+Type]
0x140077bbf  dec     eax
0x140077bc1  cmp     eax, 1
0x140077bc4  ja      loc_140077D02
0x140077bca  mov     eax, dword ptr [rsp+68h+cb]
0x140077bd1  test    eax, eax
0x140077bd3  jz      loc_140077D02
0x140077bd9  test    al, 1
0x140077bdb  jnz     loc_140077D02
0x140077be1  mov     ecx, eax; cb
0x140077be3  call    cs:__imp_CoTaskMemAlloc
0x140077be9  mov     rdi, rax
0x140077bec  test    rax, rax
0x140077bef  jz      short loc_140077C49
0x140077bf1  lea     rax, [rsp+68h+cb]
0x140077bf9  xor     r8d, r8d; lpReserved
0x140077bfc  mov     [rsp+68h+lpcbData], rax; lpcbData
0x140077c01  lea     r9, [rsp+68h+Type]; lpType
0x140077c06  mov     rdx, rsi; lpValueName
0x140077c09  mov     [rsp+68h+lpData], rdi; lpData
0x140077c0e  mov     rcx, rbp; hKey
0x140077c11  call    cs:__imp_RegQueryValueExW
0x140077c17  mov     ebx, eax
0x140077c19  test    eax, eax
0x140077c1b  jle     short loc_140077C23
0x140077c1d  movzx   ebx, ax
0x140077c20  or      ebx, r14d
0x140077c23  test    ebx, ebx
0x140077c25  jns     short loc_140077C76
0x140077c27  mov     rcx, rdi; pv
0x140077c2a  call    cs:__imp_CoTaskMemFree
0x140077c30  mov     rbp, [rsp+68h+arg_8]
0x140077c35  mov     eax, ebx
0x140077c37  mov     rbx, [rsp+68h+arg_0]
0x140077c3c  add     rsp, 40h
0x140077c40  pop     r15
0x140077c42  pop     r14
0x140077c44  pop     r12
0x140077c46  pop     rdi
0x140077c47  pop     rsi
0x140077c48  retn
0x140077c49  mov     ebx, 8007000Eh
0x140077c4e  jmp     short loc_140077C27
0x140077c50  mov     r8d, ebp; nSize
0x140077c53  mov     rdx, rsi; lpDst
0x140077c56  mov     rcx, rdi; lpSrc
0x140077c59  call    cs:__imp_ExpandEnvironmentStringsW
0x140077c5f  mov     r14d, eax
0x140077c62  test    eax, eax
0x140077c64  jnz     short loc_140077CB1
0x140077c66  mov     rcx, rsi; pv
0x140077c69  mov     ebx, 8007007Ah
0x140077c6e  call    cs:__imp_CoTaskMemFree
0x140077c74  jmp     short loc_140077C27
0x140077c76  mov     esi, dword ptr [rsp+68h+cb]
0x140077c7d  shr     esi, 1
0x140077c7f  dec     esi
0x140077c81  cmp     [rsp+68h+Type], 2
0x140077c86  jnz     short loc_140077CC9
0x140077c88  xor     r8d, r8d; nSize
0x140077c8b  xor     edx, edx; lpDst
0x140077c8d  mov     rcx, rdi; lpSrc
0x140077c90  call    cs:__imp_ExpandEnvironmentStringsW
0x140077c96  mov     ebp, eax
0x140077c98  test    eax, eax
0x140077c9a  jz      short loc_140077CC9
0x140077c9c  mov     ecx, ebp
0x140077c9e  add     rcx, rcx; cb
0x140077ca1  call    cs:__imp_CoTaskMemAlloc
0x140077ca7  mov     rsi, rax
0x140077caa  test    rax, rax
0x140077cad  jnz     short loc_140077C50
0x140077caf  jmp     short loc_140077C49
0x140077cb1  cmp     r14d, ebp
0x140077cb4  ja      short loc_140077C66
0x140077cb6  mov     rcx, rdi; pv
0x140077cb9  mov     ebx, r12d
0x140077cbc  call    cs:__imp_CoTaskMemFree
0x140077cc2  mov     rdi, rsi
0x140077cc5  lea     esi, [r14-1]
0x140077cc9  cmp     [rdi+rsi*2], r12w
0x140077cce  jnz     short loc_140077D02
0x140077cd0  mov     rcx, r15
0x140077cd3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x140077cd8  test    rdi, rdi
0x140077cdb  jz      short loc_140077CFA
0x140077cdd  lea     eax, [rsi+1]
0x140077ce0  mov     ecx, eax
0x140077ce2  test    eax, eax
0x140077ce4  jz      short loc_140077CFA
0x140077ce6  dec     rax
0x140077ce9  mov     [r15], rdi
0x140077cec  mov     [r15+8], rax
0x140077cf0  mov     [r15+10h], rcx
0x140077cf4  mov     [rdi+rcx*2-2], r12w
0x140077cfa  mov     rdi, r12
0x140077cfd  jmp     loc_140077C27
0x140077d02  mov     ebx, 8007000Dh
0x140077d07  jmp     loc_140077C27
```
