# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x18004bcb0`
- end: `0x18004be65`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800432fc`
- `0x18007b228`

## callees

- `0x18004bb94`
- `0x18004bcb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bcfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bd71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bcfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bd71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bd43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bdb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bd43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bdb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bdeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004be36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004be46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bdeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004be36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004be46`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004bda5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004bdd4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004bda5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004bdd4`

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
  __int64 v10; // rsi
  DWORD v11; // eax
  DWORD v12; // ebp
  WCHAR *v13; // rax
  WCHAR *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // r14d
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
    if ( Type[0] - 1 > 1 || !(_DWORD)cb || (cb & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_25;
    }
    v9 = RegQueryValueExW(a2, a3, 0, Type, lpData, (LPDWORD)&cb);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      v10 = ((unsigned int)cb >> 1) - 1;
      if ( Type[0] == 2 )
      {
        v11 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = (WCHAR *)CoTaskMemAlloc(2LL * v11);
          v14 = v13;
          if ( !v13 )
            goto LABEL_14;
          v15 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v13, v12);
          v16 = v15;
          if ( !v15 || v15 > v12 )
          {
            v8 = -2147024774;
            CoTaskMemFree(v14);
            goto LABEL_25;
          }
          v8 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
        if ( lpData )
        {
          v17 = (unsigned int)(v10 + 1);
          if ( (_DWORD)v10 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v17 - 1);
            a1[2] = (BYTE *)(unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_25;
      }
LABEL_24:
      v8 = -2147024883;
    }
  }
LABEL_25:
  CoTaskMemFree(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004bcb0  mov     r11, rsp
0x18004bcb3  mov     [r11+8], rbx
0x18004bcb7  mov     [r11+10h], rbp
0x18004bcbb  mov     [r11+20h], r9b
0x18004bcbf  push    rsi
0x18004bcc0  push    rdi
0x18004bcc1  push    r12
0x18004bcc3  push    r14
0x18004bcc5  push    r15
0x18004bcc7  sub     rsp, 40h
0x18004bccb  xor     r12d, r12d
0x18004bcce  lea     rax, [r11+20h]
0x18004bcd2  mov     rsi, r8
0x18004bcd5  mov     [r11-40h], rax
0x18004bcd9  mov     rbp, rdx
0x18004bcdc  mov     [r11-48h], r12
0x18004bce0  mov     r15, rcx
0x18004bce3  mov     [r11-38h], r12d
0x18004bce7  mov     rdx, rsi; lpValueName
0x18004bcea  mov     [r11+20h], r12d
0x18004bcee  mov     rcx, rbp; hKey
0x18004bcf1  lea     r9, [r11-38h]; lpType
0x18004bcf5  xor     r8d, r8d; lpReserved
0x18004bcf8  mov     edi, r12d
0x18004bcfb  call    cs:__imp_RegQueryValueExW
0x18004bd01  mov     ebx, eax
0x18004bd03  mov     r14d, 80070000h
0x18004bd09  test    eax, eax
0x18004bd0b  jle     short loc_18004BD13
0x18004bd0d  movzx   ebx, ax
0x18004bd10  or      ebx, r14d
0x18004bd13  test    ebx, ebx
0x18004bd15  js      loc_18004BE43
0x18004bd1b  mov     eax, [rsp+68h+Type]
0x18004bd1f  dec     eax
0x18004bd21  cmp     eax, 1
0x18004bd24  ja      loc_18004BE3E
0x18004bd2a  mov     eax, dword ptr [rsp+68h+cb]
0x18004bd31  test    eax, eax
0x18004bd33  jz      loc_18004BE3E
0x18004bd39  test    al, 1
0x18004bd3b  jnz     loc_18004BE3E
0x18004bd41  mov     ecx, eax; cb
0x18004bd43  call    cs:__imp_CoTaskMemAlloc
0x18004bd49  mov     rdi, rax
0x18004bd4c  test    rax, rax
0x18004bd4f  jz      short loc_18004BDC4
0x18004bd51  lea     rax, [rsp+68h+cb]
0x18004bd59  xor     r8d, r8d; lpReserved
0x18004bd5c  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18004bd61  lea     r9, [rsp+68h+Type]; lpType
0x18004bd66  mov     rdx, rsi; lpValueName
0x18004bd69  mov     [rsp+68h+lpData], rdi; lpData
0x18004bd6e  mov     rcx, rbp; hKey
0x18004bd71  call    cs:__imp_RegQueryValueExW
0x18004bd77  mov     ebx, eax
0x18004bd79  test    eax, eax
0x18004bd7b  jle     short loc_18004BD83
0x18004bd7d  movzx   ebx, ax
0x18004bd80  or      ebx, r14d
0x18004bd83  test    ebx, ebx
0x18004bd85  js      loc_18004BE43
0x18004bd8b  mov     esi, dword ptr [rsp+68h+cb]
0x18004bd92  shr     esi, 1
0x18004bd94  dec     esi
0x18004bd96  cmp     [rsp+68h+Type], 2
0x18004bd9b  jnz     short loc_18004BDF8
0x18004bd9d  xor     r8d, r8d; nSize
0x18004bda0  xor     edx, edx; lpDst
0x18004bda2  mov     rcx, rdi; lpSrc
0x18004bda5  call    cs:__imp_ExpandEnvironmentStringsW
0x18004bdab  mov     ebp, eax
0x18004bdad  test    eax, eax
0x18004bdaf  jz      short loc_18004BDF8
0x18004bdb1  mov     ecx, ebp
0x18004bdb3  add     rcx, rcx; cb
0x18004bdb6  call    cs:__imp_CoTaskMemAlloc
0x18004bdbc  mov     rsi, rax
0x18004bdbf  test    rax, rax
0x18004bdc2  jnz     short loc_18004BDCB
0x18004bdc4  mov     ebx, 8007000Eh
0x18004bdc9  jmp     short loc_18004BE43
0x18004bdcb  mov     r8d, ebp; nSize
0x18004bdce  mov     rdx, rsi; lpDst
0x18004bdd1  mov     rcx, rdi; lpSrc
0x18004bdd4  call    cs:__imp_ExpandEnvironmentStringsW
0x18004bdda  mov     r14d, eax
0x18004bddd  test    eax, eax
0x18004bddf  jz      short loc_18004BE2E
0x18004bde1  cmp     eax, ebp
0x18004bde3  ja      short loc_18004BE2E
0x18004bde5  mov     rcx, rdi; pv
0x18004bde8  mov     ebx, r12d
0x18004bdeb  call    cs:__imp_CoTaskMemFree
0x18004bdf1  mov     rdi, rsi
0x18004bdf4  lea     esi, [r14-1]
0x18004bdf8  cmp     [rdi+rsi*2], r12w
0x18004bdfd  jnz     short loc_18004BE3E
0x18004bdff  mov     rcx, r15
0x18004be02  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004be07  test    rdi, rdi
0x18004be0a  jz      short loc_18004BE29
0x18004be0c  lea     eax, [rsi+1]
0x18004be0f  mov     ecx, eax
0x18004be11  test    eax, eax
0x18004be13  jz      short loc_18004BE29
0x18004be15  dec     rax
0x18004be18  mov     [r15], rdi
0x18004be1b  mov     [r15+8], rax
0x18004be1f  mov     [r15+10h], rcx
0x18004be23  mov     [rdi+rcx*2-2], r12w
0x18004be29  mov     rdi, r12
0x18004be2c  jmp     short loc_18004BE43
0x18004be2e  mov     rcx, rsi; pv
0x18004be31  mov     ebx, 8007007Ah
0x18004be36  call    cs:__imp_CoTaskMemFree
0x18004be3c  jmp     short loc_18004BE43
0x18004be3e  mov     ebx, 8007000Dh
0x18004be43  mov     rcx, rdi; pv
0x18004be46  call    cs:__imp_CoTaskMemFree
0x18004be4c  mov     rbp, [rsp+68h+arg_8]
0x18004be51  mov     eax, ebx
0x18004be53  mov     rbx, [rsp+68h+arg_0]
0x18004be58  add     rsp, 40h
0x18004be5c  pop     r15
0x18004be5e  pop     r14
0x18004be60  pop     r12
0x18004be62  pop     rdi
0x18004be63  pop     rsi
0x18004be64  retn
```
