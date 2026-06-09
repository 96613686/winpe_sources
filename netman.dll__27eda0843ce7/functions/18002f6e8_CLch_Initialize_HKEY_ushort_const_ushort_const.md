# CLch::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18002f6e8`
- end: `0x18002f7f9`
- name: `?Initialize@CLch@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `273`
- prototype: `__int64 __fastcall(CLch *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002e97c`

## callees

- `0x18002f6e8`
- `0x18002f800`
- `0x18002fb4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f70a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f719`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f70a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f719`
- `ADVAPI32!RegQueryValueExW` at `0x18002f7b4`
- `ADVAPI32!RegQueryValueExW` at `0x18002f7b4`

## string_xrefs

- `0x18002f72c`: `DllName`

## pseudocode

```c
__int64 __fastcall CLch::Initialize(CLch *this, HKEY a2, const unsigned __int16 *a3, const unsigned __int16 *a4)
{
  _QWORD *v7; // rbx
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF

  _o_wcscpy_s(this, 40, a3);
  _o_wcscpy_s((char *)this + 80, 40, a4);
  RegQueryString(a2, L"DllName", (unsigned __int16 **)this + 20);
  RegQueryString(a2, L"FunctionEntryName", (unsigned __int16 **)this + 21);
  v7 = (_QWORD *)((char *)this + 176);
  RegQueryString(a2, L"ExeName", (unsigned __int16 **)this + 22);
  RegQueryString(a2, L"Arguments", (unsigned __int16 **)this + 23);
  cbData = 4;
  *((_DWORD *)this + 62) = 0;
  RegQueryValueExW(a2, L"Cardinality", 0, 0, (LPBYTE)this + 248, &cbData);
  if ( *((_QWORD *)this + 20) )
  {
    if ( *v7 || !*((_QWORD *)this + 21) )
      return 2147500037LL;
  }
  else if ( !*v7 )
  {
    return 2147500037LL;
  }
  CLch::InitializeConditions(this, a2);
  return 0;
}

```

## disassembly

```asm
0x18002f6e8  mov     [rsp+arg_8], rbx
0x18002f6ed  mov     [rsp+arg_10], rbp
0x18002f6f2  push    rsi
0x18002f6f3  push    rdi
0x18002f6f4  push    r14
0x18002f6f6  sub     rsp, 30h
0x18002f6fa  mov     rbp, rdx
0x18002f6fd  mov     edi, 28h ; '('
0x18002f702  mov     edx, edi
0x18002f704  mov     rbx, r9
0x18002f707  mov     rsi, rcx
0x18002f70a  call    cs:__imp__o_wcscpy_s
0x18002f710  lea     rcx, [rsi+50h]
0x18002f714  mov     r8, rbx
0x18002f717  mov     edx, edi
0x18002f719  call    cs:__imp__o_wcscpy_s
0x18002f71f  lea     rdi, [rsi+0A0h]
0x18002f726  mov     rcx, rbp; hKey
0x18002f729  mov     r8, rdi; unsigned __int16 **
0x18002f72c  lea     rdx, ?c_szLchDllName@@3QBGB; "DllName"
0x18002f733  call    ?RegQueryString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegQueryString(HKEY__ *,ushort const *,ushort * *)
0x18002f738  lea     r14, [rsi+0A8h]
0x18002f73f  mov     rcx, rbp; hKey
0x18002f742  mov     r8, r14; unsigned __int16 **
0x18002f745  lea     rdx, ?c_szLchFunctionEntryName@@3QBGB; "FunctionEntryName"
0x18002f74c  call    ?RegQueryString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegQueryString(HKEY__ *,ushort const *,ushort * *)
0x18002f751  lea     rbx, [rsi+0B0h]
0x18002f758  mov     rcx, rbp; hKey
0x18002f75b  mov     r8, rbx; unsigned __int16 **
0x18002f75e  lea     rdx, aExename; "ExeName"
0x18002f765  call    ?RegQueryString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegQueryString(HKEY__ *,ushort const *,ushort * *)
0x18002f76a  lea     r8, [rsi+0B8h]; unsigned __int16 **
0x18002f771  mov     rcx, rbp; hKey
0x18002f774  lea     rdx, aArguments; "Arguments"
0x18002f77b  call    ?RegQueryString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegQueryString(HKEY__ *,ushort const *,ushort * *)
0x18002f780  lea     rax, [rsi+0F8h]
0x18002f787  mov     [rsp+48h+cbData], 4
0x18002f78f  lea     rcx, [rsp+48h+cbData]
0x18002f794  mov     dword ptr [rax], 0
0x18002f79a  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x18002f79f  lea     rdx, ?c_szLchCardinality@@3QBGB; "Cardinality"
0x18002f7a6  mov     rcx, rbp; hKey
0x18002f7a9  mov     [rsp+48h+lpData], rax; lpData
0x18002f7ae  xor     r9d, r9d; lpType
0x18002f7b1  xor     r8d, r8d; lpReserved
0x18002f7b4  call    cs:__imp_RegQueryValueExW
0x18002f7ba  cmp     qword ptr [rdi], 0
0x18002f7be  jz      short loc_18002F7E4
0x18002f7c0  cmp     qword ptr [rbx], 0
0x18002f7c4  jnz     short loc_18002F7CC
0x18002f7c6  cmp     qword ptr [r14], 0
0x18002f7ca  jnz     short loc_18002F7EA
0x18002f7cc  mov     eax, 80004005h
0x18002f7d1  mov     rbx, [rsp+48h+arg_8]
0x18002f7d6  mov     rbp, [rsp+48h+arg_10]
0x18002f7db  add     rsp, 30h
0x18002f7df  pop     r14
0x18002f7e1  pop     rdi
0x18002f7e2  pop     rsi
0x18002f7e3  retn
0x18002f7e4  cmp     qword ptr [rbx], 0
0x18002f7e8  jz      short loc_18002F7CC
0x18002f7ea  mov     rdx, rbp; HKEY
0x18002f7ed  mov     rcx, rsi; this
0x18002f7f0  call    ?InitializeConditions@CLch@@AEAAJPEAUHKEY__@@@Z; CLch::InitializeConditions(HKEY__ *)
0x18002f7f5  xor     eax, eax
0x18002f7f7  jmp     short loc_18002F7D1
```
