# MirrorRegKeys(HKEY__ *,HKEY__ *)

- ea: `0x18004d930`
- end: `0x18004da62`
- name: `?MirrorRegKeys@@YAXPEAUHKEY__@@0@Z`
- size: `306`
- prototype: `void __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18004da68`

## callees

- `0x18004d7bc`
- `0x18004d894`
- `0x18004d930`
- `0x18004deb8`
- `0x18004def8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004d986`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004d986`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004d9ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004d9ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004da27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004da27`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MirrorRegKeys(HKEY hKey, HKEY a2)
{
  DWORD i; // ebx
  DWORD Type; // [rsp+68h] [rbp+7h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp+Bh] BYREF
  LPBYTE lpData[2]; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v8; // [rsp+80h] [rbp+1Fh]
  LPWSTR lpValueName[4]; // [rsp+88h] [rbp+27h] BYREF
  DWORD v10; // [rsp+D8h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+E0h] [rbp+7Fh] BYREF

  v10 = 0;
  if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &v10, 0, 0, 0, 0) )
  {
    std::vector<unsigned short>::vector<unsigned short>(lpValueName);
    for ( i = 0; i < v10; ++i )
    {
      cchValueName = 260;
      Type = 0;
      cbData = 260;
      *(_OWORD *)lpData = 0;
      v8 = 0;
      std::vector<unsigned char>::_Construct_n<>(lpData);
      if ( !RegEnumValueW(hKey, i, lpValueName[0], &cchValueName, 0, &Type, lpData[0], &cbData) )
        RegSetValueExW(a2, lpValueName[0], 0, Type, lpData[0], cbData);
      std::vector<unsigned char>::_Tidy(lpData);
    }
    std::vector<unsigned short>::_Tidy(lpValueName);
  }
}

```

## disassembly

```asm
0x18004d930  mov     r11, rsp
0x18004d933  mov     [r11+8], rbx
0x18004d937  mov     [r11+10h], rsi
0x18004d93b  push    rbp
0x18004d93c  push    rdi
0x18004d93d  push    r14
0x18004d93f  lea     rbp, [r11-5Fh]
0x18004d943  sub     rsp, 0A0h
0x18004d94a  mov     rsi, rdx
0x18004d94d  mov     rdi, rcx
0x18004d950  xor     r14d, r14d
0x18004d953  mov     [rbp+57h+arg_10], r14d
0x18004d957  mov     [r11-60h], r14
0x18004d95b  mov     [r11-68h], r14
0x18004d95f  mov     [r11-70h], r14
0x18004d963  mov     [r11-78h], r14
0x18004d967  lea     rax, [rbp+57h+arg_10]
0x18004d96b  mov     [r11-80h], rax
0x18004d96f  mov     [rsp+0B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18004d974  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18004d979  mov     [rsp+0B0h+lpcSubKeys], r14; lpcSubKeys
0x18004d97e  xor     r9d, r9d; lpReserved
0x18004d981  xor     r8d, r8d; lpcchClass
0x18004d984  xor     edx, edx; lpClass
0x18004d986  call    cs:__imp_RegQueryInfoKeyW
0x18004d98c  test    eax, eax
0x18004d98e  jnz     loc_18004DA4A
0x18004d994  lea     rcx, [rbp+57h+lpValueName]
0x18004d998  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18004d99d  nop
0x18004d99e  mov     ebx, r14d
0x18004d9a1  cmp     [rbp+57h+arg_10], r14d
0x18004d9a5  jbe     loc_18004DA41
0x18004d9ab  mov     [rbp+57h+cchValueName], 104h
0x18004d9b2  mov     [rbp+57h+Type], r14d
0x18004d9b6  mov     [rbp+57h+cbData], 104h
0x18004d9bd  xorps   xmm0, xmm0
0x18004d9c0  movdqu  xmmword ptr [rbp+57h+lpData], xmm0
0x18004d9c5  mov     [rbp+57h+var_38], r14
0x18004d9c9  lea     rcx, [rbp+57h+lpData]
0x18004d9cd  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x18004d9d2  mov     rax, [rbp+57h+lpData]
0x18004d9d6  lea     rcx, [rbp+57h+cbData]
0x18004d9da  mov     [rsp+0B0h+lpcbData], rcx; lpcbData
0x18004d9df  mov     [rsp+0B0h+lpcbMaxClassLen], rax; lpData
0x18004d9e4  lea     rax, [rbp+57h+Type]
0x18004d9e8  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpType
0x18004d9ed  mov     [rsp+0B0h+lpcSubKeys], r14; lpReserved
0x18004d9f2  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18004d9f6  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x18004d9fa  mov     edx, ebx; dwIndex
0x18004d9fc  mov     rcx, rdi; hKey
0x18004d9ff  call    cs:__imp_RegEnumValueW
0x18004da05  test    eax, eax
0x18004da07  jnz     short loc_18004DA2D
0x18004da09  mov     eax, [rbp+57h+cbData]
0x18004da0c  mov     dword ptr [rsp+0B0h+lpcbMaxSubKeyLen], eax; cbData
0x18004da10  mov     rax, [rbp+57h+lpData]
0x18004da14  mov     [rsp+0B0h+lpcSubKeys], rax; lpData
0x18004da19  mov     r9d, [rbp+57h+Type]; dwType
0x18004da1d  xor     r8d, r8d; Reserved
0x18004da20  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x18004da24  mov     rcx, rsi; hKey
0x18004da27  call    cs:__imp_RegSetValueExW
0x18004da2d  lea     rcx, [rbp+57h+lpData]
0x18004da31  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004da36  inc     ebx
0x18004da38  cmp     ebx, [rbp+57h+arg_10]
0x18004da3b  jb      loc_18004D9AB
0x18004da41  lea     rcx, [rbp+57h+lpValueName]
0x18004da45  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004da4a  lea     r11, [rsp+0B0h+var_10]
0x18004da52  mov     rbx, [r11+20h]
0x18004da56  mov     rsi, [r11+28h]
0x18004da5a  mov     rsp, r11
0x18004da5d  pop     r14
0x18004da5f  pop     rdi
0x18004da60  pop     rbp
0x18004da61  retn
```
