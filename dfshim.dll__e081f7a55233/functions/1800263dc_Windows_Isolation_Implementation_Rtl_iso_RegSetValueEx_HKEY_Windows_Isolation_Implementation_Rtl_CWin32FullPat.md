# Windows::Isolation::Implementation::Rtl::iso_RegSetValueEx(HKEY__ *,Windows::Isolation::Implementation::Rtl::CWin32FullPath const *,ulong,ulong,uchar const *,ulong)

- ea: `0x1800263dc`
- end: `0x1800264bf`
- name: `?iso_RegSetValueEx@Rtl@Implementation@Isolation@Windows@@YAJPEAUHKEY__@@PEBVCWin32FullPath@1234@KKPEBEK@Z`
- size: `227`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *@<r8>, unsigned int@<r9d>, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180025ba0`

## callees

- `0x1800263dc`
- `0x1800b8a44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180026450`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180026450`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800264a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800264a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026428`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026481`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026428`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026481`

## pseudocode

```c
LSTATUS __fastcall Windows::Isolation::Implementation::Rtl::iso_RegSetValueEx(
        Windows::Isolation::Implementation::Rtl *hKey,
        _DWORD *a2,
        const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *a3,
        DWORD a4,
        BYTE *lpData,
        const unsigned __int8 *cbData)
{
  bool v9; // al
  const CHAR *v10; // rdx
  HKEY v11; // rbx
  HKEY v13; // rbx

  v9 = Windows::Isolation::Implementation::Rtl::CallAnsiApis(hKey);
  v10 = 0;
  if ( v9 )
  {
    if ( !a2 )
      return RegSetValueExA((HKEY)hKey, v10, 0, a4, lpData, (DWORD)cbData);
    if ( a2[14] == 1 )
    {
      v11 = (HKEY)(a2 + 12);
      if ( *(_QWORD *)v11 )
        goto LABEL_8;
    }
    else
    {
      v11 = (HKEY)(a2 + 12);
    }
    RaiseException(0xC00000E5, 1u, 0, 0);
LABEL_8:
    v10 = *(const CHAR **)(*(_QWORD *)v11 + 16LL);
    return RegSetValueExA((HKEY)hKey, v10, 0, a4, lpData, (DWORD)cbData);
  }
  if ( a2 )
  {
    if ( a2[14] == 2 )
    {
      v13 = (HKEY)(a2 + 12);
      if ( *(_QWORD *)v13 )
        goto LABEL_16;
    }
    else
    {
      v13 = (HKEY)(a2 + 12);
    }
    RaiseException(0xC00000E5, 1u, 0, 0);
LABEL_16:
    v10 = *(const CHAR **)(*(_QWORD *)v13 + 16LL);
  }
  return RegSetValueExW((HKEY)hKey, (LPCWSTR)v10, 0, a4, lpData, (DWORD)cbData);
}

```

## disassembly

```asm
0x1800263dc  mov     [rsp+arg_0], rbx
0x1800263e1  mov     [rsp+arg_8], rsi
0x1800263e6  push    rdi
0x1800263e7  sub     rsp, 30h
0x1800263eb  mov     edi, r9d
0x1800263ee  mov     rbx, rdx
0x1800263f1  mov     rsi, rcx
0x1800263f4  call    ?CallAnsiApis@Rtl@Implementation@Isolation@Windows@@YA_NXZ; Windows::Isolation::Implementation::Rtl::CallAnsiApis(void)
0x1800263f9  xor     edx, edx
0x1800263fb  test    al, al
0x1800263fd  jz      short loc_180026458
0x1800263ff  test    rbx, rbx
0x180026402  jz      short loc_180026435
0x180026404  cmp     dword ptr [rbx+38h], 1
0x180026408  jnz     short loc_180026415
0x18002640a  add     rbx, 30h ; '0'
0x18002640e  cmp     [rbx], rdx
0x180026411  jz      short loc_180026419
0x180026413  jmp     short loc_18002642E
0x180026415  add     rbx, 30h ; '0'
0x180026419  xor     r9d, r9d; lpArguments
0x18002641c  xor     r8d, r8d; nNumberOfArguments
0x18002641f  mov     ecx, 0C00000E5h; dwExceptionCode
0x180026424  lea     edx, [r9+1]; dwExceptionFlags
0x180026428  call    cs:__imp_RaiseException
0x18002642e  mov     rax, [rbx]
0x180026431  mov     rdx, [rax+10h]; lpValueName
0x180026435  mov     eax, [rsp+38h+arg_28]
0x180026439  mov     r9d, edi; dwType
0x18002643c  mov     [rsp+38h+cbData], eax; cbData
0x180026440  xor     r8d, r8d; Reserved
0x180026443  mov     rax, [rsp+38h+arg_20]
0x180026448  mov     rcx, rsi; hKey
0x18002644b  mov     [rsp+38h+lpData], rax; lpData
0x180026450  call    cs:__imp_RegSetValueExA
0x180026456  jmp     short loc_1800264AF
0x180026458  test    rbx, rbx
0x18002645b  jz      short loc_18002648E
0x18002645d  cmp     dword ptr [rbx+38h], 2
0x180026461  jnz     short loc_18002646E
0x180026463  add     rbx, 30h ; '0'
0x180026467  cmp     [rbx], rdx
0x18002646a  jz      short loc_180026472
0x18002646c  jmp     short loc_180026487
0x18002646e  add     rbx, 30h ; '0'
0x180026472  xor     r9d, r9d; lpArguments
0x180026475  xor     r8d, r8d; nNumberOfArguments
0x180026478  mov     ecx, 0C00000E5h; dwExceptionCode
0x18002647d  lea     edx, [r9+1]; dwExceptionFlags
0x180026481  call    cs:__imp_RaiseException
0x180026487  mov     rax, [rbx]
0x18002648a  mov     rdx, [rax+10h]; lpValueName
0x18002648e  mov     eax, [rsp+38h+arg_28]
0x180026492  mov     r9d, edi; dwType
0x180026495  mov     [rsp+38h+cbData], eax; cbData
0x180026499  xor     r8d, r8d; Reserved
0x18002649c  mov     rax, [rsp+38h+arg_20]
0x1800264a1  mov     rcx, rsi; hKey
0x1800264a4  mov     [rsp+38h+lpData], rax; lpData
0x1800264a9  call    cs:__imp_RegSetValueExW
0x1800264af  mov     rbx, [rsp+38h+arg_0]
0x1800264b4  mov     rsi, [rsp+38h+arg_8]
0x1800264b9  add     rsp, 30h
0x1800264bd  pop     rdi
0x1800264be  retn
```
