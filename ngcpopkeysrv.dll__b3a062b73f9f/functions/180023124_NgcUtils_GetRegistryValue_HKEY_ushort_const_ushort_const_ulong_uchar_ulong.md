# NgcUtils::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)

- ea: `0x180023124`
- end: `0x18002325d`
- name: `?GetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z`
- size: `313`
- prototype: `__int64 __fastcall(HKEY hkey, const WCHAR *lpSubKey, LPCWSTR lpValue, DWORD dwFlags, _QWORD *, unsigned __int8 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016f58`
- `0x180019424`
- `0x18001bc90`
- `0x18001e4f0`

## callees

- `0x18000b0fc`
- `0x180013270`
- `0x1800136b0`
- `0x180023124`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002322b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002322b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002315d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800231fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002315d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800231fe`

## string_xrefs

- `0x18002318b`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x1800231c7`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180023210`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::GetRegistryValue(
        HKEY hkey,
        const WCHAR *lpSubKey,
        LPCWSTR lpValue,
        DWORD dwFlags,
        _QWORD *a5,
        unsigned __int8 **a6)
{
  LSTATUS ValueW; // eax
  unsigned int v11; // ebx
  __int64 result; // rax
  PVOID v13; // rbx
  unsigned int v14; // eax
  unsigned int v15; // edi
  int pdwType; // [rsp+20h] [rbp-58h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-58h]
  DWORD pcbData; // [rsp+40h] [rbp-38h] BYREF
  PVOID hMem[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  pcbData = 0;
  ValueW = RegGetValueW(hkey, lpSubKey, lpValue, dwFlags, 0, 0, &pcbData);
  v11 = ValueW;
  if ( ValueW > 0 )
    v11 = (unsigned __int16)ValueW | 0x80070000;
  if ( (v11 & 0x80000000) != 0 )
  {
    result = 2147942402LL;
    if ( v11 == -2147024894 )
      return result;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)v11,
      pdwType);
    return v11;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(hMem, pcbData);
  v13 = hMem[0];
  if ( !hMem[0] )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)0x8007000ELL,
      pdwType);
    return v11;
  }
  v14 = RegGetValueW(hkey, lpSubKey, lpValue, dwFlags, 0, hMem[0], &pcbData);
  if ( !v14 )
  {
    *a5 = v13;
    *(_DWORD *)a6 = pcbData;
    return 0;
  }
  v15 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
          (const char *)v14,
          pdwTypea);
  if ( v13 )
    LocalFree(v13);
  return v15;
}

```

## disassembly

```asm
0x180023124  mov     r11, rsp
0x180023127  push    rbx
0x180023128  push    rbp
0x180023129  push    rsi
0x18002312a  push    rdi
0x18002312b  push    r14
0x18002312d  sub     rsp, 50h
0x180023131  mov     edi, r9d
0x180023134  mov     rsi, r8
0x180023137  mov     rbp, rdx
0x18002313a  mov     r14, rcx
0x18002313d  mov     [rsp+78h+var_38], 0
0x180023145  lea     rax, [r11-38h]
0x180023149  mov     [r11-48h], rax
0x18002314d  mov     qword ptr [r11-50h], 0
0x180023155  mov     qword ptr [r11-58h], 0
0x18002315d  call    cs:__imp_RegGetValueW
0x180023163  mov     ebx, eax
0x180023165  test    eax, eax
0x180023167  jle     short loc_180023172
0x180023169  movzx   ebx, ax
0x18002316c  or      ebx, 80070000h
0x180023172  test    ebx, ebx
0x180023174  jns     short loc_1800231A1
0x180023176  mov     eax, 80070002h
0x18002317b  cmp     ebx, eax
0x18002317d  jz      loc_180023252
0x180023183  mov     rcx, [rsp+78h]; this
0x180023188  mov     r9d, ebx; char *
0x18002318b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180023192  mov     edx, 26h ; '&'; void *
0x180023197  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002319c  jmp     loc_180023250
0x1800231a1  mov     edx, [rsp+78h+var_38]
0x1800231a5  lea     rcx, [rsp+78h+hMem]
0x1800231aa  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800231af  nop
0x1800231b0  mov     rbx, [rsp+78h+hMem]
0x1800231b5  test    rbx, rbx
0x1800231b8  jnz     short loc_1800231DA
0x1800231ba  mov     rcx, [rsp+78h]; this
0x1800231bf  mov     ebx, 8007000Eh
0x1800231c4  mov     r9d, ebx; char *
0x1800231c7  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800231ce  mov     edx, 2Ah ; '*'; void *
0x1800231d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800231d8  jmp     short loc_180023250
0x1800231da  lea     rax, [rsp+78h+var_38]
0x1800231df  mov     [rsp+78h+pcbData], rax; pcbData
0x1800231e4  mov     [rsp+78h+pvData], rbx; pvData
0x1800231e9  mov     [rsp+78h+pdwType], 0; unsigned int
0x1800231f2  mov     r9d, edi; dwFlags
0x1800231f5  mov     r8, rsi; lpValue
0x1800231f8  mov     rdx, rbp; lpSubKey
0x1800231fb  mov     rcx, r14; hkey
0x1800231fe  call    cs:__imp_RegGetValueW
0x180023204  test    eax, eax
0x180023206  jz      short loc_180023235
0x180023208  mov     rcx, [rsp+78h]; this
0x18002320d  mov     r9d, eax; char *
0x180023210  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180023217  mov     edx, 33h ; '3'; void *
0x18002321c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023221  mov     edi, eax
0x180023223  test    rbx, rbx
0x180023226  jz      short loc_180023231
0x180023228  mov     rcx, rbx; hMem
0x18002322b  call    cs:__imp_LocalFree
0x180023231  mov     eax, edi
0x180023233  jmp     short loc_180023252
0x180023235  mov     rax, [rsp+78h+arg_20]
0x18002323d  mov     [rax], rbx
0x180023240  mov     rcx, [rsp+78h+arg_28]
0x180023248  mov     eax, [rsp+78h+var_38]
0x18002324c  mov     [rcx], eax
0x18002324e  xor     ebx, ebx
0x180023250  mov     eax, ebx
0x180023252  add     rsp, 50h
0x180023256  pop     r14
0x180023258  pop     rdi
0x180023259  pop     rsi
0x18002325a  pop     rbp
0x18002325b  pop     rbx
0x18002325c  retn
```
