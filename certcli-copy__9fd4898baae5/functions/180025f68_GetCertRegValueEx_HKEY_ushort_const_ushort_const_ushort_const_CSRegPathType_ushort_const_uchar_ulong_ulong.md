# _GetCertRegValueEx(HKEY__ *,ushort const *,ushort const *,ushort const *,CSRegPathType,ushort const *,uchar * *,ulong *,ulong *)

- ea: `0x180025f68`
- end: `0x18002605d`
- name: `?_GetCertRegValueEx@@YAJPEAUHKEY__@@PEBG11W4CSRegPathType@@1PEAPEAEPEAK4@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180026bac`

## callees

- `0x1800213f0`
- `0x180025f68`
- `0x180026810`
- `0x180026c1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025fcf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025fcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002604a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002604a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002603a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002603a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180025fa5`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180025fa5`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x180025fe8`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x180025fe8`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18002602f`
- `certca!__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z` at `0x18002602f`

## pseudocode

```c
__int64 __fastcall _GetCertRegValueEx(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        LPCWSTR lpValueName,
        unsigned __int8 **a7,
        unsigned int *a8,
        unsigned int *a9)
{
  int v9; // eax
  int v10; // ebx
  LSTATUS v11; // eax
  int Value; // eax
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp+20h]

  hKey = 0;
  lpSubKey = 0;
  v9 = myFormCertRegPath(a2);
  v10 = v9;
  if ( v9 )
  {
    CSPrintErrorLineFile(0x1F201B5u, v9);
  }
  else
  {
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
    v10 = v11;
    if ( v11 )
    {
      CSPrintErrorLineFile2(0x1FA01B5u, v11, 2);
    }
    else
    {
      Value = myRegQueryValueEx(hKey, lpValueName, a9, a7, a8);
      v10 = Value;
      if ( Value )
        CSPrintErrorLineFileData2(lpValueName, 0x20701B5u, Value, -2147024894);
    }
  }
  LocalFree((HLOCAL)lpSubKey);
  if ( hKey )
    RegCloseKey(hKey);
  return myHError(v10);
}

```

## disassembly

```asm
0x180025f68  mov     r11, rsp
0x180025f6b  mov     [r11+20h], r9
0x180025f6f  mov     [r11+18h], r8
0x180025f73  push    rbx
0x180025f74  sub     rsp, 30h
0x180025f78  lea     rax, [r11+20h]
0x180025f7c  mov     qword ptr [r11+18h], 0
0x180025f84  mov     rcx, rdx
0x180025f87  mov     [r11-18h], rax
0x180025f8b  mov     qword ptr [r11+20h], 0
0x180025f93  call    ?myFormCertRegPath@@YAJPEBG00W4CSRegPathType@@PEAPEAG@Z; myFormCertRegPath(ushort const *,ushort const *,ushort const *,CSRegPathType,ushort * *)
0x180025f98  mov     ebx, eax
0x180025f9a  test    eax, eax
0x180025f9c  jz      short loc_180025FB0
0x180025f9e  mov     edx, eax
0x180025fa0  mov     ecx, 1F201B5h
0x180025fa5  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180025fab  jmp     loc_180026035
0x180025fb0  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180025fb5  lea     rax, [rsp+38h+hKey]
0x180025fba  mov     r9d, 20019h; samDesired
0x180025fc0  mov     [rsp+38h+phkResult], rax; phkResult
0x180025fc5  xor     r8d, r8d; ulOptions
0x180025fc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025fcf  call    cs:__imp_RegOpenKeyExW
0x180025fd5  mov     ebx, eax
0x180025fd7  test    eax, eax
0x180025fd9  jz      short loc_180025FF0
0x180025fdb  mov     r8d, 2
0x180025fe1  mov     edx, eax
0x180025fe3  mov     ecx, 1FA01B5h
0x180025fe8  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x180025fee  jmp     short loc_180026035
0x180025ff0  mov     rax, [rsp+38h+arg_38]
0x180025ff5  mov     r9, [rsp+38h+arg_30]; unsigned __int8 **
0x180025ffa  mov     r8, [rsp+38h+arg_40]; unsigned int *
0x180026002  mov     rdx, [rsp+38h+lpValueName]; lpValueName
0x180026007  mov     rcx, [rsp+38h+hKey]; hKey
0x18002600c  mov     [rsp+38h+phkResult], rax; unsigned int *
0x180026011  call    ?myRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAPEAE2@Z; myRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar * *,ulong *)
0x180026016  mov     ebx, eax
0x180026018  test    eax, eax
0x18002601a  jz      short loc_180026035
0x18002601c  mov     rcx, [rsp+38h+lpValueName]
0x180026021  mov     r9d, 80070002h
0x180026027  mov     r8d, eax
0x18002602a  mov     edx, 20701B5h
0x18002602f  call    cs:__imp_?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180026035  mov     rcx, [rsp+38h+lpSubKey]; hMem
0x18002603a  call    cs:__imp_LocalFree
0x180026040  mov     rcx, [rsp+38h+hKey]; hKey
0x180026045  test    rcx, rcx
0x180026048  jz      short loc_180026050
0x18002604a  call    cs:__imp_RegCloseKey
0x180026050  mov     ecx, ebx; int
0x180026052  call    ?myHError@@YAJJ@Z; myHError(long)
0x180026057  add     rsp, 30h
0x18002605b  pop     rbx
0x18002605c  retn
```
