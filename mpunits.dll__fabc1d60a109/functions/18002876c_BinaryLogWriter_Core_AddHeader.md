# BinaryLogWriter_Core_AddHeader

- ea: `0x18002876c`
- end: `0x18002884f`
- name: `BinaryLogWriter_Core_AddHeader`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180028948`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18002876c`

## import_xrefs

- `msvcrt!_write` at `0x1800287a4`
- `msvcrt!_write` at `0x1800287bb`
- `msvcrt!_write` at `0x1800287d2`
- `msvcrt!_write` at `0x1800287a4`
- `msvcrt!_write` at `0x1800287bb`
- `msvcrt!_write` at `0x1800287d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800287ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800287ef`

## string_xrefs

- `0x1800287e4`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall BinaryLogWriter_Core_AddHeader(__int64 a1)
{
  bool v1; // zf
  HMODULE ModuleHandleA; // rax
  char v5; // [rsp+50h] [rbp+10h] BYREF
  char v6; // [rsp+58h] [rbp+18h] BYREF
  __int16 Buf; // [rsp+60h] [rbp+20h] BYREF

  v1 = *(_QWORD *)(a1 + 64) == 0;
  Buf = -257;
  v5 = 16;
  v6 = 0;
  if ( !v1 )
    v5 = 32;
  if ( _write(*(_DWORD *)a1, &Buf, 2u) != -1
    && _write(*(_DWORD *)a1, &v5, 1u) != -1
    && _write(*(_DWORD *)a1, &v6, 1u) != -1 )
  {
    return 0;
  }
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_GetString_LoadString(ModuleHandleA, 2017);
  MI_ReportErrorDetails_ForCustomError(16, (int)L"BinaryLogger", 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18002876c  mov     [rsp-8+arg_18], rbx
0x180028771  push    rbp
0x180028772  mov     rbp, rsp
0x180028775  sub     rsp, 40h
0x180028779  cmp     qword ptr [rcx+40h], 0
0x18002877e  mov     eax, 0FEFFh
0x180028783  mov     [rbp+Buf], ax
0x180028787  mov     rbx, rcx
0x18002878a  mov     [rbp+arg_0], 10h
0x18002878e  mov     [rbp+arg_8], 0
0x180028792  jz      short loc_180028798
0x180028794  mov     [rbp+arg_0], 20h ; ' '
0x180028798  mov     ecx, [rcx]; FileHandle
0x18002879a  lea     rdx, [rbp+Buf]; Buf
0x18002879e  mov     r8d, 2; MaxCharCount
0x1800287a4  call    cs:__imp__write
0x1800287aa  cmp     eax, 0FFFFFFFFh
0x1800287ad  jz      short loc_1800287E1
0x1800287af  mov     ecx, [rbx]; FileHandle
0x1800287b1  lea     rdx, [rbp+arg_0]; Buf
0x1800287b5  mov     r8d, 1; MaxCharCount
0x1800287bb  call    cs:__imp__write
0x1800287c1  cmp     eax, 0FFFFFFFFh
0x1800287c4  jz      short loc_1800287E1
0x1800287c6  mov     ecx, [rbx]; FileHandle
0x1800287c8  lea     rdx, [rbp+arg_8]; Buf
0x1800287cc  mov     r8d, 1; MaxCharCount
0x1800287d2  call    cs:__imp__write
0x1800287d8  cmp     eax, 0FFFFFFFFh
0x1800287db  jz      short loc_1800287E1
0x1800287dd  xor     eax, eax
0x1800287df  jmp     short loc_180028844
0x1800287e1  xorps   xmm0, xmm0
0x1800287e4  lea     rcx, ModuleName; "mpunits.dll"
0x1800287eb  movups  [rbp+var_10], xmm0
0x1800287ef  call    cs:__imp_GetModuleHandleA
0x1800287f5  mov     rcx, rax
0x1800287f8  mov     edx, 7E1h
0x1800287fd  call    _Intlstr_GetString_LoadString
0x180028802  mov     qword ptr [rbp+var_10], rax
0x180028806  lea     r9, [rbp+var_10]
0x18002880a  mov     byte ptr [rbp+var_10+8], 0
0x18002880e  lea     rdx, aBinarylogger; "BinaryLogger"
0x180028815  movaps  xmm0, [rbp+var_10]
0x180028819  mov     r8d, 17h
0x18002881f  mov     [rsp+40h+var_18], 0; __int64
0x180028828  movdqa  [rbp+var_10], xmm0
0x18002882d  mov     [rsp+40h+var_20], 0; __int64
0x180028836  lea     ecx, [r8-7]; int
0x18002883a  call    MI_ReportErrorDetails_ForCustomError
0x18002883f  mov     eax, 1
0x180028844  mov     rbx, [rsp+40h+arg_18]
0x180028849  add     rsp, 40h
0x18002884d  pop     rbp
0x18002884e  retn
```
