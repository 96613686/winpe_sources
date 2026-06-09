# Windows::Isolation::Implementation::Rtl::iso_RegOpenKeyEx(HKEY__ *,Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,ulong,ulong,HKEY__ * *)

- ea: `0x180026220`
- end: `0x1800262d9`
- name: `?iso_RegOpenKeyEx@Rtl@Implementation@Isolation@Windows@@YAJPEAUHKEY__@@AEBVCWin32FullPath@1234@KKPEAPEAU5@@Z`
- size: `185`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *@<r8>, unsigned int@<r9d>, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180024ed0`

## callees

- `0x180023cec`
- `0x180026220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800262ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800262ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180026277`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180026277`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026254`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026297`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026254`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026297`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::iso_RegOpenKeyEx(
        HKEY hKey,
        _DWORD *a2,
        const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *a3,
        int a4,
        HKEY *phkResult)
{
  int v5; // eax
  HKEY v6; // rbx
  REGSAM v8; // esi
  Windows::Isolation::Implementation::Rtl **v9; // rdi
  LSTATUS v10; // eax
  HKEY v11; // rdx
  unsigned int v12; // ebx

  v5 = a2[14];
  v6 = (HKEY)(a2 + 12);
  v8 = a4 | 1;
  if ( v5 == 1 )
  {
    if ( !*(_QWORD *)v6 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    v9 = (Windows::Isolation::Implementation::Rtl **)phkResult;
    v10 = RegOpenKeyExA(hKey, *(LPCSTR *)(*(_QWORD *)v6 + 16LL), 0, v8, phkResult);
  }
  else
  {
    if ( v5 != 2 || !*(_QWORD *)v6 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    v9 = (Windows::Isolation::Implementation::Rtl **)phkResult;
    v10 = RegOpenKeyExW(hKey, *(LPCWSTR *)(*(_QWORD *)v6 + 16LL), 0, v8, phkResult);
  }
  v12 = v10;
  if ( !v10 )
    Windows::Isolation::Implementation::Rtl::DisbaleWowReflection(*v9, v11);
  return v12;
}

```

## disassembly

```asm
0x180026220  push    rbx
0x180026222  push    rbp
0x180026223  push    rsi
0x180026224  push    rdi
0x180026225  sub     rsp, 38h
0x180026229  mov     eax, [rdx+38h]
0x18002622c  lea     rbx, [rdx+30h]
0x180026230  mov     rbp, rcx
0x180026233  mov     esi, r9d
0x180026236  mov     ecx, 1
0x18002623b  or      esi, ecx
0x18002623d  cmp     eax, ecx
0x18002623f  jnz     short loc_18002627F
0x180026241  cmp     qword ptr [rbx], 0
0x180026245  jnz     short loc_18002625A
0x180026247  mov     edx, ecx; dwExceptionFlags
0x180026249  xor     r9d, r9d; lpArguments
0x18002624c  mov     ecx, 0C00000E5h; dwExceptionCode
0x180026251  xor     r8d, r8d; nNumberOfArguments
0x180026254  call    cs:__imp_RaiseException
0x18002625a  mov     rdx, [rbx]
0x18002625d  mov     r9d, esi; samDesired
0x180026260  mov     rdi, [rsp+58h+arg_20]
0x180026268  xor     r8d, r8d; ulOptions
0x18002626b  mov     rcx, rbp; hKey
0x18002626e  mov     [rsp+58h+phkResult], rdi; phkResult
0x180026273  mov     rdx, [rdx+10h]; lpSubKey
0x180026277  call    cs:__imp_RegOpenKeyExA
0x18002627d  jmp     short loc_1800262C0
0x18002627f  cmp     eax, 2
0x180026282  jnz     short loc_18002628A
0x180026284  cmp     qword ptr [rbx], 0
0x180026288  jnz     short loc_18002629D
0x18002628a  mov     edx, ecx; dwExceptionFlags
0x18002628c  xor     r9d, r9d; lpArguments
0x18002628f  mov     ecx, 0C00000E5h; dwExceptionCode
0x180026294  xor     r8d, r8d; nNumberOfArguments
0x180026297  call    cs:__imp_RaiseException
0x18002629d  mov     rdx, [rbx]
0x1800262a0  mov     r9d, esi; samDesired
0x1800262a3  mov     rdi, [rsp+58h+arg_20]
0x1800262ab  xor     r8d, r8d; ulOptions
0x1800262ae  mov     rcx, rbp; hKey
0x1800262b1  mov     [rsp+58h+phkResult], rdi; phkResult
0x1800262b6  mov     rdx, [rdx+10h]; lpSubKey
0x1800262ba  call    cs:__imp_RegOpenKeyExW
0x1800262c0  mov     ebx, eax
0x1800262c2  test    eax, eax
0x1800262c4  jnz     short loc_1800262CE
0x1800262c6  mov     rcx, [rdi]; this
0x1800262c9  call    ?DisbaleWowReflection@Rtl@Implementation@Isolation@Windows@@YAJPEAUHKEY__@@@Z; Windows::Isolation::Implementation::Rtl::DisbaleWowReflection(HKEY__ *)
0x1800262ce  mov     eax, ebx
0x1800262d0  add     rsp, 38h
0x1800262d4  pop     rdi
0x1800262d5  pop     rsi
0x1800262d6  pop     rbp
0x1800262d7  pop     rbx
0x1800262d8  retn
```
