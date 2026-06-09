# BinaryLogReader_Core_ValidateHeader

- ea: `0x1800291a8`
- end: `0x1800292c6`
- name: `BinaryLogReader_Core_ValidateHeader`
- size: `286`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007020`
- `0x180025e90`
- `0x18002add0`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x1800291a8`

## import_xrefs

- `msvcrt!_read` at `0x1800291d0`
- `msvcrt!_read` at `0x1800291e8`
- `msvcrt!_read` at `0x180029200`
- `msvcrt!_read` at `0x1800291d0`
- `msvcrt!_read` at `0x1800291e8`
- `msvcrt!_read` at `0x180029200`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002924b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029266`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002924b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180029266`

## string_xrefs

- `0x180029240`: `mpunits.dll`
- `0x18002925b`: `mpunits.dll`
- `0x180029285`: `BinaryLogReader`

## pseudocode

```c
__int64 __fastcall BinaryLogReader_Core_ValidateHeader(__int64 a1)
{
  int v2; // ecx
  bool v3; // zf
  HMODULE ModuleHandleA; // rax
  __int64 v6; // rdx
  char v7; // [rsp+50h] [rbp+10h] BYREF
  char v8; // [rsp+58h] [rbp+18h] BYREF
  __int16 DstBuf; // [rsp+60h] [rbp+20h] BYREF

  v8 = -1;
  DstBuf = 0;
  v2 = *(_DWORD *)(a1 + 4);
  v7 = 0;
  if ( _read(v2, &DstBuf, 2u) == -1
    || _read(*(_DWORD *)(a1 + 4), &v7, 1u) == -1
    || _read(*(_DWORD *)(a1 + 4), &v8, 1u) == -1 )
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v6 = 2012;
    goto LABEL_13;
  }
  if ( DstBuf != -257 || ((v7 - 16) & 0xEF) != 0 || v8 )
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v6 = 2028;
LABEL_13:
    Intlstr_GetString_LoadString(ModuleHandleA, v6);
    MI_ReportErrorDetails_ForCustomError(11, (int)L"BinaryLogReader", 0, 0);
    return 1;
  }
  if ( v7 == 32 )
  {
    v3 = *(_DWORD *)(a1 + 96) == 0;
    *(_BYTE *)(a1 + 68) = 1;
    if ( v3 )
      *(_BYTE *)(a1 + 104) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800291a8  mov     [rsp-8+arg_18], rbx
0x1800291ad  push    rbp
0x1800291ae  mov     rbp, rsp
0x1800291b1  sub     rsp, 40h
0x1800291b5  xor     eax, eax
0x1800291b7  mov     [rbp+arg_8], 0FFh
0x1800291bb  mov     rbx, rcx
0x1800291be  mov     [rbp+DstBuf], ax
0x1800291c2  mov     ecx, [rcx+4]; FileHandle
0x1800291c5  lea     rdx, [rbp+DstBuf]; DstBuf
0x1800291c9  mov     [rbp+arg_0], al
0x1800291cc  lea     r8d, [rax+2]; MaxCharCount
0x1800291d0  call    cs:__imp__read
0x1800291d6  cmp     eax, 0FFFFFFFFh
0x1800291d9  jz      short loc_180029258
0x1800291db  mov     ecx, [rbx+4]; FileHandle
0x1800291de  lea     rdx, [rbp+arg_0]; DstBuf
0x1800291e2  mov     r8d, 1; MaxCharCount
0x1800291e8  call    cs:__imp__read
0x1800291ee  cmp     eax, 0FFFFFFFFh
0x1800291f1  jz      short loc_180029258
0x1800291f3  mov     ecx, [rbx+4]; FileHandle
0x1800291f6  lea     rdx, [rbp+arg_8]; DstBuf
0x1800291fa  mov     r8d, 1; MaxCharCount
0x180029200  call    cs:__imp__read
0x180029206  cmp     eax, 0FFFFFFFFh
0x180029209  jz      short loc_180029258
0x18002920b  mov     eax, 0FEFFh
0x180029210  cmp     [rbp+DstBuf], ax
0x180029214  jnz     short loc_18002923D
0x180029216  mov     al, [rbp+arg_0]
0x180029219  sub     al, 10h
0x18002921b  test    al, 0EFh
0x18002921d  jnz     short loc_18002923D
0x18002921f  cmp     [rbp+arg_8], 0
0x180029223  jnz     short loc_18002923D
0x180029225  cmp     [rbp+arg_0], 20h ; ' '
0x180029229  jnz     short loc_180029239
0x18002922b  cmp     dword ptr [rbx+60h], 0
0x18002922f  mov     byte ptr [rbx+44h], 1
0x180029233  jnz     short loc_180029239
0x180029235  mov     byte ptr [rbx+68h], 1
0x180029239  xor     eax, eax
0x18002923b  jmp     short loc_1800292BB
0x18002923d  xorps   xmm0, xmm0
0x180029240  lea     rcx, ModuleName; "mpunits.dll"
0x180029247  movups  [rbp+var_10], xmm0
0x18002924b  call    cs:__imp_GetModuleHandleA
0x180029251  mov     edx, 7ECh
0x180029256  jmp     short loc_180029271
0x180029258  xorps   xmm0, xmm0
0x18002925b  lea     rcx, ModuleName; "mpunits.dll"
0x180029262  movups  [rbp+var_10], xmm0
0x180029266  call    cs:__imp_GetModuleHandleA
0x18002926c  mov     edx, 7DCh
0x180029271  mov     rcx, rax
0x180029274  call    _Intlstr_GetString_LoadString
0x180029279  mov     qword ptr [rbp+var_10], rax
0x18002927d  lea     r9, [rbp+var_10]
0x180029281  mov     byte ptr [rbp+var_10+8], 0
0x180029285  lea     rdx, aBinarylogreade_1; "BinaryLogReader"
0x18002928c  movaps  xmm0, [rbp+var_10]
0x180029290  mov     r8d, 16h
0x180029296  mov     [rsp+40h+var_18], 0; __int64
0x18002929f  mov     [rsp+40h+var_20], 0; __int64
0x1800292a8  movdqa  [rbp+var_10], xmm0
0x1800292ad  lea     ecx, [r8-0Bh]; int
0x1800292b1  call    MI_ReportErrorDetails_ForCustomError
0x1800292b6  mov     eax, 1
0x1800292bb  mov     rbx, [rsp+40h+arg_18]
0x1800292c0  add     rsp, 40h
0x1800292c4  pop     rbp
0x1800292c5  retn
```
