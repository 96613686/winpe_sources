# CDll<&ushort near * wDfDll>::LoadModule(void)

- ea: `0x18000eb00`
- end: `0x18000ebfb`
- name: `?LoadModule@?$CDll@$1?wDfDll@@3PAGA@@KAJXZ`
- size: `251`
- prototype: `signed int()`
- caller_count: `14`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e77c`
- `0x18000e860`
- `0x18000e99c`
- `0x18000ec30`
- `0x18000ed50`
- `0x18000eeb0`
- `0x18000ef60`
- `0x18000f29c`
- `0x18000f660`
- `0x18000fcb0`
- `0x180010910`
- `0x180010a40`
- `0x180010d90`
- `0x180011940`

## callees

- `0x18000eb00`
- `0x18000f1ec`
- `0x180127dc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ebcd`
- `KERNEL32!GetLastError` at `0x18000ebcd`
- `KERNEL32!LoadLibraryExW` at `0x18000ebbb`
- `KERNEL32!LoadLibraryExW` at `0x18000ebbb`
- `mscoree!GetRequestedRuntimeInfo` at `0x18000eb66`
- `mscoree!GetRequestedRuntimeInfo` at `0x18000eb66`

## string_xrefs

- `0x18000eb9b`: `dfdll.dll`

## pseudocode

```c
signed int CDll<&unsigned short near * wDfDll>::LoadModule()
{
  signed int result; // eax
  unsigned __int64 v1; // rdx
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // rdx
  WCHAR LibFileName[264]; // [rsp+60h] [rbp-438h] BYREF
  unsigned __int16 v5[264]; // [rsp+270h] [rbp-228h] BYREF

  result = GetRequestedRuntimeInfo(&dword_180140C2C, 0, 0, 0, 193, LibFileName, 261, 0, v5, 261, 0);
  if ( result >= 0 )
  {
    result = StringCchCatW(LibFileName, v1, v5);
    if ( result >= 0 )
    {
      result = StringCchCatW(LibFileName, v2, L"\\");
      if ( result >= 0 )
      {
        result = StringCchCatW(LibFileName, v3, wDfDll);
        if ( result >= 0 )
        {
          CDll<&unsigned short near * wDfDll>::_hModule = LoadLibraryExW(LibFileName, 0, 8u);
          if ( CDll<&unsigned short near * wDfDll>::_hModule )
          {
            return 0;
          }
          else
          {
            result = GetLastError();
            if ( result > 0 )
              return (unsigned __int16)result | 0x80070000;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000eb00  sub     rsp, 498h
0x18000eb07  mov     rax, cs:__security_cookie
0x18000eb0e  xor     rax, rsp
0x18000eb11  mov     [rsp+498h+var_18], rax
0x18000eb19  mov     [rsp+498h+var_448], 0
0x18000eb22  lea     rax, [rsp+498h+var_228]
0x18000eb2a  mov     ecx, 105h
0x18000eb2f  xor     r9d, r9d
0x18000eb32  mov     [rsp+498h+var_450], ecx
0x18000eb36  xor     r8d, r8d
0x18000eb39  mov     [rsp+498h+var_458], rax
0x18000eb3e  xor     edx, edx
0x18000eb40  mov     [rsp+498h+var_460], 0
0x18000eb49  lea     rax, [rsp+498h+LibFileName]
0x18000eb4e  mov     [rsp+498h+var_468], ecx
0x18000eb52  lea     rcx, dword_180140C2C
0x18000eb59  mov     [rsp+498h+var_470], rax
0x18000eb5e  mov     [rsp+498h+var_478], 0C1h
0x18000eb66  call    cs:__imp_GetRequestedRuntimeInfo
0x18000eb6c  test    eax, eax
0x18000eb6e  js      short loc_18000EBE3
0x18000eb70  lea     r8, [rsp+498h+var_228]; unsigned __int16 *
0x18000eb78  lea     rcx, [rsp+498h+LibFileName]; unsigned __int16 *
0x18000eb7d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000eb82  test    eax, eax
0x18000eb84  js      short loc_18000EBE3
0x18000eb86  lea     r8, SubBlock; "\\"
0x18000eb8d  lea     rcx, [rsp+498h+LibFileName]; unsigned __int16 *
0x18000eb92  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000eb97  test    eax, eax
0x18000eb99  js      short loc_18000EBE3
0x18000eb9b  lea     r8, ?wDfDll@@3PAGA; "dfdll.dll"
0x18000eba2  lea     rcx, [rsp+498h+LibFileName]; unsigned __int16 *
0x18000eba7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ebac  test    eax, eax
0x18000ebae  js      short loc_18000EBE3
0x18000ebb0  xor     edx, edx; hFile
0x18000ebb2  lea     rcx, [rsp+498h+LibFileName]; lpLibFileName
0x18000ebb7  lea     r8d, [rdx+8]; dwFlags
0x18000ebbb  call    cs:__imp_LoadLibraryExW
0x18000ebc1  mov     cs:?_hModule@?$CDll@$1?wDfDll@@3PAGA@@1PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CDll<&ushort near * wDfDll>::_hModule
0x18000ebc8  test    rax, rax
0x18000ebcb  jnz     short loc_18000EBE1
0x18000ebcd  call    cs:__imp_GetLastError
0x18000ebd3  test    eax, eax
0x18000ebd5  jle     short loc_18000EBE3
0x18000ebd7  movzx   eax, ax
0x18000ebda  or      eax, 80070000h
0x18000ebdf  jmp     short loc_18000EBE3
0x18000ebe1  xor     eax, eax
0x18000ebe3  mov     rcx, [rsp+498h+var_18]
0x18000ebeb  xor     rcx, rsp; StackCookie
0x18000ebee  call    __security_check_cookie
0x18000ebf3  add     rsp, 498h
0x18000ebfa  retn
```
