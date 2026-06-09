# CRunBootOptimize::_SaveErrorInRegistry(ushort *,ushort *)

- ea: `0x180010c20`
- end: `0x180010d7a`
- name: `?_SaveErrorInRegistry@CRunBootOptimize@@AEAAJPEAG0@Z`
- size: `346`
- prototype: `__int64 __fastcall(CRunBootOptimize *this, BYTE *, BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e4e0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180010c20`
- `0x18004ea08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d55`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010ccd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010ccd`

## string_xrefs

- `0x180010c45`: `CRunBootOptimize::_SaveErrorInRegistry`
- `0x180010ce5`: `OptimizeComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRunBootOptimize::_SaveErrorInRegistry(CRunBootOptimize *this, BYTE *a2, BYTE *a3)
{
  HKEY v5; // rcx
  __int16 v6; // ax
  signed int v7; // ebx
  LSTATUS v8; // eax
  bool v9; // sf
  int v11; // [rsp+50h] [rbp-9h] BYREF
  __int16 v12; // [rsp+54h] [rbp-5h]
  __int16 v13; // [rsp+56h] [rbp-3h]
  HKEY hKey; // [rsp+C0h] [rbp+67h] BYREF

  hKey = (HKEY)this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "CRunBootOptimize::_SaveErrorInRegistry", 68, 1);
  v5 = 0;
  hKey = 0;
  v6 = 72;
  if ( !a2 || (v12 = 72, v6 = 73, !a3) )
  {
    v7 = -2147024809;
    v11 = -2147024809;
    goto LABEL_3;
  }
  v11 = 0;
  v12 = 73;
  v8 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Dfrg\\BootOptimizeFunction",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  v7 = v8;
  v5 = hKey;
  if ( v8 )
  {
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
  }
  else if ( hKey )
  {
    v7 = SxRegWriteString(hKey, L"OptimizeComplete", a2);
    v11 = v7;
    v5 = hKey;
    v6 = 96;
    if ( v7 >= 0 )
    {
      v12 = 96;
      v7 = SxRegWriteString(hKey, L"OptimizeError", a3);
      v11 = v7;
      v5 = hKey;
      v9 = v7 < 0;
      v6 = 97;
      goto LABEL_12;
    }
LABEL_3:
    v13 = v6;
    goto LABEL_14;
  }
  v11 = v7;
  v6 = 92;
  v9 = v7 < 0;
LABEL_12:
  if ( v9 )
    goto LABEL_3;
  v12 = v6;
LABEL_14:
  if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v5);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010c20  mov     [rsp-8+hKey], rcx
0x180010c25  push    rbp
0x180010c26  push    rbx
0x180010c27  push    rsi
0x180010c28  push    rdi
0x180010c29  lea     rbp, [rsp-3Fh]
0x180010c2e  sub     rsp, 98h
0x180010c35  mov     rdi, r8
0x180010c38  mov     rsi, rdx
0x180010c3b  mov     r9d, 1; unsigned __int16
0x180010c41  lea     r8d, [r9+43h]; unsigned __int16
0x180010c45  lea     rdx, aCrunbootoptimi_2; "CRunBootOptimize::_SaveErrorInRegistry"
0x180010c4c  lea     rcx, [rbp+57h+var_60]; this
0x180010c50  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180010c55  nop
0x180010c56  xor     ecx, ecx
0x180010c58  mov     [rbp+57h+hKey], rcx
0x180010c5c  lea     eax, [rcx+48h]
0x180010c5f  test    rsi, rsi
0x180010c62  jnz     short loc_180010C75
0x180010c64  mov     ebx, 80070057h
0x180010c69  mov     [rbp+57h+var_60], ebx
0x180010c6c  mov     [rbp+57h+var_5A], ax
0x180010c70  jmp     loc_180010D4B
0x180010c75  mov     [rbp+57h+var_5C], ax
0x180010c79  mov     eax, 49h ; 'I'
0x180010c7e  test    rdi, rdi
0x180010c81  jz      short loc_180010C64
0x180010c83  mov     [rbp+57h+var_60], 0
0x180010c8a  mov     [rbp+57h+var_5C], ax
0x180010c8e  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x180010c97  lea     rax, [rbp+57h+hKey]
0x180010c9b  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180010ca0  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010ca9  mov     [rsp+0B0h+samDesired], 20006h; samDesired
0x180010cb1  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x180010cb9  xor     r9d, r9d; lpClass
0x180010cbc  xor     r8d, r8d; Reserved
0x180010cbf  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Dfrg\\BootOptimize"...
0x180010cc6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010ccd  call    cs:__imp_RegCreateKeyExW
0x180010cd3  mov     ebx, eax
0x180010cd5  mov     rcx, [rbp+57h+hKey]; hKey
0x180010cd9  test    eax, eax
0x180010cdb  jnz     short loc_180010D2C
0x180010cdd  test    rcx, rcx
0x180010ce0  jz      short loc_180010D37
0x180010ce2  mov     r8, rsi; lpData
0x180010ce5  lea     rdx, aOptimizecomple; "OptimizeComplete"
0x180010cec  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x180010cf1  mov     ebx, eax
0x180010cf3  mov     [rbp+57h+var_60], eax
0x180010cf6  mov     rcx, [rbp+57h+hKey]; hKey
0x180010cfa  test    eax, eax
0x180010cfc  mov     eax, 60h ; '`'
0x180010d01  js      loc_180010C6C
0x180010d07  mov     [rbp+57h+var_5C], ax
0x180010d0b  mov     r8, rdi; lpData
0x180010d0e  lea     rdx, aOptimizeerror; "OptimizeError"
0x180010d15  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x180010d1a  mov     ebx, eax
0x180010d1c  mov     [rbp+57h+var_60], eax
0x180010d1f  mov     rcx, [rbp+57h+hKey]
0x180010d23  test    eax, eax
0x180010d25  mov     eax, 61h ; 'a'
0x180010d2a  jmp     short loc_180010D41
0x180010d2c  jle     short loc_180010D37
0x180010d2e  movzx   ebx, ax
0x180010d31  or      ebx, 80070000h
0x180010d37  mov     [rbp+57h+var_60], ebx
0x180010d3a  mov     eax, 5Ch ; '\'
0x180010d3f  test    ebx, ebx
0x180010d41  js      loc_180010C6C
0x180010d47  mov     [rbp+57h+var_5C], ax
0x180010d4b  lea     rdx, [rcx-1]
0x180010d4f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180010d53  ja      short loc_180010D63
0x180010d55  call    cs:__imp_RegCloseKey
0x180010d5b  mov     [rbp+57h+hKey], 0
0x180010d63  lea     rcx, [rbp+57h+var_60]; this
0x180010d67  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180010d6c  mov     eax, ebx
0x180010d6e  add     rsp, 98h
0x180010d75  pop     rdi
0x180010d76  pop     rsi
0x180010d77  pop     rbx
0x180010d78  pop     rbp
0x180010d79  retn
```
