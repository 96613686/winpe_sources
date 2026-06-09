# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x14007c7a0`
- end: `0x14007c98f`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14007c708`

## callees

- `0x140027508`
- `0x14007c7a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007c7eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007c869`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007c7eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007c869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007c888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007c8d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007c939`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007c888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007c8d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007c939`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007c835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007c918`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007c835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14007c918`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14007c8be`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14007c901`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14007c8be`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14007c901`

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
  __int64 v10; // rdx
  DWORD v12; // r14d
  __int64 v13; // rsi
  DWORD v14; // eax
  DWORD v15; // ebp
  WCHAR *v16; // rax
  WCHAR *v17; // rsi
  __int64 v18; // rax
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
      v13 = ((unsigned int)cb >> 1) - 1;
      if ( Type[0] == 2 )
      {
        v14 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v15 = v14;
        if ( v14 )
        {
          v16 = (WCHAR *)CoTaskMemAlloc(2LL * v14);
          v17 = v16;
          if ( !v16 )
            goto LABEL_12;
          v12 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v16, v15);
          if ( !v12 || v12 > v15 )
          {
            v8 = -2147024774;
            CoTaskMemFree(v17);
            goto LABEL_11;
          }
          v8 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v17;
          v13 = v12 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v13] )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1, v10);
        if ( lpData )
        {
          v18 = (unsigned int)(v13 + 1);
          if ( (_DWORD)v13 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v18 - 1);
            a1[2] = (BYTE *)(unsigned int)v18;
            *(_WORD *)&lpData[2 * (unsigned int)v18 - 2] = 0;
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
0x14007c7a0  mov     r11, rsp
0x14007c7a3  mov     [r11+8], rbx
0x14007c7a7  mov     [r11+10h], rbp
0x14007c7ab  mov     [r11+20h], r9b
0x14007c7af  push    rsi
0x14007c7b0  push    rdi
0x14007c7b1  push    r12
0x14007c7b3  push    r14
0x14007c7b5  push    r15
0x14007c7b7  sub     rsp, 40h
0x14007c7bb  xor     r12d, r12d
0x14007c7be  lea     rax, [r11+20h]
0x14007c7c2  mov     rsi, r8
0x14007c7c5  mov     [r11-40h], rax
0x14007c7c9  mov     rbp, rdx
0x14007c7cc  mov     [r11-48h], r12
0x14007c7d0  mov     r15, rcx
0x14007c7d3  mov     [r11-38h], r12d
0x14007c7d7  mov     rdx, rsi; lpValueName
0x14007c7da  mov     [r11+20h], r12d
0x14007c7de  mov     rcx, rbp; hKey
0x14007c7e1  lea     r9, [r11-38h]; lpType
0x14007c7e5  xor     r8d, r8d; lpReserved
0x14007c7e8  mov     edi, r12d
0x14007c7eb  call    cs:__imp_RegQueryValueExW
0x14007c7f2  nop     dword ptr [rax+rax+00h]
0x14007c7f7  mov     ebx, eax
0x14007c7f9  mov     r14d, 80070000h
0x14007c7ff  test    eax, eax
0x14007c801  jle     short loc_14007C809
0x14007c803  movzx   ebx, ax
0x14007c806  or      ebx, r14d
0x14007c809  test    ebx, ebx
0x14007c80b  js      short loc_14007C885
0x14007c80d  mov     eax, [rsp+68h+Type]
0x14007c811  dec     eax
0x14007c813  cmp     eax, 1
0x14007c816  ja      loc_14007C985
0x14007c81c  mov     eax, dword ptr [rsp+68h+cb]
0x14007c823  test    eax, eax
0x14007c825  jz      loc_14007C985
0x14007c82b  test    al, 1
0x14007c82d  jnz     loc_14007C985
0x14007c833  mov     ecx, eax; cb
0x14007c835  call    cs:__imp_CoTaskMemAlloc
0x14007c83c  nop     dword ptr [rax+rax+00h]
0x14007c841  mov     rdi, rax
0x14007c844  test    rax, rax
0x14007c847  jz      short loc_14007C8AE
0x14007c849  lea     rax, [rsp+68h+cb]
0x14007c851  xor     r8d, r8d; lpReserved
0x14007c854  mov     [rsp+68h+lpcbData], rax; lpcbData
0x14007c859  lea     r9, [rsp+68h+Type]; lpType
0x14007c85e  mov     rdx, rsi; lpValueName
0x14007c861  mov     [rsp+68h+lpData], rdi; lpData
0x14007c866  mov     rcx, rbp; hKey
0x14007c869  call    cs:__imp_RegQueryValueExW
0x14007c870  nop     dword ptr [rax+rax+00h]
0x14007c875  mov     ebx, eax
0x14007c877  test    eax, eax
0x14007c879  jle     short loc_14007C881
0x14007c87b  movzx   ebx, ax
0x14007c87e  or      ebx, r14d
0x14007c881  test    ebx, ebx
0x14007c883  jns     short loc_14007C8E7
0x14007c885  mov     rcx, rdi; pv
0x14007c888  call    cs:__imp_CoTaskMemFree
0x14007c88f  nop     dword ptr [rax+rax+00h]
0x14007c894  mov     rbp, [rsp+68h+arg_8]
0x14007c899  mov     eax, ebx
0x14007c89b  mov     rbx, [rsp+68h+arg_0]
0x14007c8a0  add     rsp, 40h
0x14007c8a4  pop     r15
0x14007c8a6  pop     r14
0x14007c8a8  pop     r12
0x14007c8aa  pop     rdi
0x14007c8ab  pop     rsi
0x14007c8ac  retn
0x14007c8ae  mov     ebx, 8007000Eh
0x14007c8b3  jmp     short loc_14007C885
0x14007c8b5  mov     r8d, ebp; nSize
0x14007c8b8  mov     rdx, rsi; lpDst
0x14007c8bb  mov     rcx, rdi; lpSrc
0x14007c8be  call    cs:__imp_ExpandEnvironmentStringsW
0x14007c8c5  nop     dword ptr [rax+rax+00h]
0x14007c8ca  mov     r14d, eax
0x14007c8cd  test    eax, eax
0x14007c8cf  jnz     short loc_14007C92E
0x14007c8d1  mov     rcx, rsi; pv
0x14007c8d4  mov     ebx, 8007007Ah
0x14007c8d9  call    cs:__imp_CoTaskMemFree
0x14007c8e0  nop     dword ptr [rax+rax+00h]
0x14007c8e5  jmp     short loc_14007C885
0x14007c8e7  mov     esi, dword ptr [rsp+68h+cb]
0x14007c8ee  shr     esi, 1
0x14007c8f0  dec     esi
0x14007c8f2  cmp     [rsp+68h+Type], 2
0x14007c8f7  jnz     short loc_14007C94C
0x14007c8f9  xor     r8d, r8d; nSize
0x14007c8fc  xor     edx, edx; lpDst
0x14007c8fe  mov     rcx, rdi; lpSrc
0x14007c901  call    cs:__imp_ExpandEnvironmentStringsW
0x14007c908  nop     dword ptr [rax+rax+00h]
0x14007c90d  mov     ebp, eax
0x14007c90f  test    eax, eax
0x14007c911  jz      short loc_14007C94C
0x14007c913  mov     ecx, ebp
0x14007c915  add     rcx, rcx; cb
0x14007c918  call    cs:__imp_CoTaskMemAlloc
0x14007c91f  nop     dword ptr [rax+rax+00h]
0x14007c924  mov     rsi, rax
0x14007c927  test    rax, rax
0x14007c92a  jnz     short loc_14007C8B5
0x14007c92c  jmp     short loc_14007C8AE
0x14007c92e  cmp     r14d, ebp
0x14007c931  ja      short loc_14007C8D1
0x14007c933  mov     rcx, rdi; pv
0x14007c936  mov     ebx, r12d
0x14007c939  call    cs:__imp_CoTaskMemFree
0x14007c940  nop     dword ptr [rax+rax+00h]
0x14007c945  mov     rdi, rsi
0x14007c948  lea     esi, [r14-1]
0x14007c94c  cmp     [rdi+rsi*2], r12w
0x14007c951  jnz     short loc_14007C985
0x14007c953  mov     rcx, r15
0x14007c956  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14007c95b  test    rdi, rdi
0x14007c95e  jz      short loc_14007C97D
0x14007c960  lea     eax, [rsi+1]
0x14007c963  mov     ecx, eax
0x14007c965  test    eax, eax
0x14007c967  jz      short loc_14007C97D
0x14007c969  dec     rax
0x14007c96c  mov     [r15], rdi
0x14007c96f  mov     [r15+8], rax
0x14007c973  mov     [r15+10h], rcx
0x14007c977  mov     [rdi+rcx*2-2], r12w
0x14007c97d  mov     rdi, r12
0x14007c980  jmp     loc_14007C885
0x14007c985  mov     ebx, 8007000Dh
0x14007c98a  jmp     loc_14007C885
```
