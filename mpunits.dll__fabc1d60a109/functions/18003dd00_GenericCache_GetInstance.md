# GenericCache_GetInstance

- ea: `0x18003dd00`
- end: `0x18003de3c`
- name: `GenericCache_GetInstance`
- size: `316`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18003e4e0`
- `0x18003e7b0`
- `0x18003e8d0`
- `0x18003eb70`
- `0x18003eca0`

## callees

- `0x180006e64`
- `0x18003dd00`
- `0x18003f000`
- `0x180042c5c`
- `0x180044698`
- `0x18004472c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003dda4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003dda4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18003ddf0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18003ddf0`

## string_xrefs

- `0x18003dd99`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall GenericCache_GetInstance(__int64 a1, __int64 a2, _WORD *a3)
{
  __int64 v5; // r9
  unsigned __int16 v6; // cx
  unsigned __int16 v7; // dx
  unsigned int v8; // r14d
  __int64 v9; // rbx
  HMODULE ModuleHandleA; // rax
  void *v11; // rdi
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  __int128 v14; // [rsp+38h] [rbp-40h]
  __int64 v15; // [rsp+48h] [rbp-30h]
  _WORD *v16; // [rsp+50h] [rbp-28h]
  __int128 v17; // [rsp+58h] [rbp-20h]
  __int64 v18; // [rsp+68h] [rbp-10h]
  MI_Instance *extendedError; // [rsp+B8h] [rbp+40h] BYREF

  v13 = 0;
  v18 = 0;
  v15 = 0;
  v16 = a3;
  v14 = 0;
  v5 = 2166136261LL;
  v17 = 0;
  while ( 1 )
  {
    v7 = *a3;
    if ( !*a3 )
      break;
    v6 = v7 + 32;
    ++a3;
    if ( (unsigned __int16)(v7 - 65) > 0x19u )
      v6 = v7;
    v5 = 16777619 * (v5 ^ v6);
  }
  v15 = v5;
  v8 = ThreadSafeHashMap_Fetch(a2, (__int64)&v13, (__int64 (__fastcall *)(__int64, _QWORD *))GetInstance_Callback, a1);
  if ( v8 == 6 )
  {
    v9 = *(_QWORD *)(a2 + 128);
    extendedError = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v11 = (void *)Intlstr_FormatString_FormatMessage(ModuleHandleA, 2134, v9);
    LODWORD(v9) = CreateOMIError_shared((int)v11, 6, (int)L"MI", 13, (__int64)&OMI_Error_rtti, &extendedError);
    LocalFree(v11);
    if ( (_DWORD)v9 )
    {
      PostResultOrAbortOnFailure(a1, 6);
    }
    else
    {
      PostCimErrorOrAbortOnFailure(a1, extendedError);
      if ( extendedError && extendedError->ft )
        ((void (*)(void))extendedError->ft->Delete)();
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18003dd00  push    rbp
0x18003dd02  push    rbx
0x18003dd03  push    rsi
0x18003dd04  push    rdi
0x18003dd05  push    r14
0x18003dd07  push    r15
0x18003dd09  mov     rbp, rsp
0x18003dd0c  sub     rsp, 78h
0x18003dd10  xor     r15d, r15d
0x18003dd13  xorps   xmm1, xmm1
0x18003dd16  xor     eax, eax
0x18003dd18  mov     [rbp+var_48], r15
0x18003dd1c  xorps   xmm0, xmm0
0x18003dd1f  mov     [rbp+var_10], rax
0x18003dd23  movups  [rbp+var_30], xmm1
0x18003dd27  mov     rdi, r8
0x18003dd2a  mov     qword ptr [rbp+var_30+8], r8
0x18003dd2e  mov     rbx, rdx
0x18003dd31  mov     rsi, rcx
0x18003dd34  movups  [rbp+var_40], xmm0
0x18003dd38  mov     r9d, 811C9DC5h
0x18003dd3e  movups  [rbp+var_20], xmm1
0x18003dd42  jmp     short loc_18003DD63
0x18003dd44  lea     eax, [rdx-41h]
0x18003dd47  cmp     ax, 19h
0x18003dd4b  lea     ecx, [rdx+20h]
0x18003dd4e  lea     r8, [r8+2]
0x18003dd52  cmova   cx, dx
0x18003dd56  movzx   eax, cx
0x18003dd59  xor     rax, r9
0x18003dd5c  imul    r9, rax, 1000193h
0x18003dd63  movzx   edx, word ptr [r8]
0x18003dd67  test    dx, dx
0x18003dd6a  jnz     short loc_18003DD44
0x18003dd6c  mov     qword ptr [rbp+var_30], r9
0x18003dd70  lea     r8, GetInstance_Callback
0x18003dd77  mov     r9, rsi
0x18003dd7a  lea     rdx, [rbp+var_48]
0x18003dd7e  mov     rcx, rbx
0x18003dd81  call    ThreadSafeHashMap_Fetch
0x18003dd86  mov     r14d, eax
0x18003dd89  cmp     eax, 6
0x18003dd8c  jnz     loc_18003DE2C
0x18003dd92  mov     rbx, [rbx+80h]
0x18003dd99  lea     rcx, ModuleName; "mpunits.dll"
0x18003dda0  mov     [rbp+arg_8], r15
0x18003dda4  call    cs:__imp_GetModuleHandleA
0x18003ddaa  mov     r9, rdi
0x18003ddad  mov     r8, rbx
0x18003ddb0  mov     rcx, rax
0x18003ddb3  mov     edx, 856h
0x18003ddb8  call    _Intlstr_FormatString_FormatMessage
0x18003ddbd  mov     rdi, rax
0x18003ddc0  lea     r9d, [r14+7]; int
0x18003ddc4  lea     rax, [rbp+arg_8]
0x18003ddc8  mov     edx, r14d; int
0x18003ddcb  mov     [rsp+78h+extendedError], rax; extendedError
0x18003ddd0  lea     r8, aMi; "MI"
0x18003ddd7  lea     rax, OMI_Error_rtti
0x18003ddde  mov     rcx, rdi; int
0x18003dde1  mov     [rsp+78h+var_58], rax; __int64
0x18003dde6  call    CreateOMIError_shared
0x18003ddeb  mov     rcx, rdi; hMem
0x18003ddee  mov     ebx, eax
0x18003ddf0  call    cs:__imp_LocalFree
0x18003ddf6  mov     rcx, rsi
0x18003ddf9  test    ebx, ebx
0x18003ddfb  jnz     short loc_18003DE22
0x18003ddfd  mov     rdx, [rbp+arg_8]
0x18003de01  call    PostCimErrorOrAbortOnFailure
0x18003de06  mov     rcx, [rbp+arg_8]
0x18003de0a  test    rcx, rcx
0x18003de0d  jz      short loc_18003DE2C
0x18003de0f  mov     rax, [rcx]
0x18003de12  test    rax, rax
0x18003de15  jz      short loc_18003DE2C
0x18003de17  mov     rax, [rax+10h]
0x18003de1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de20  jmp     short loc_18003DE2C
0x18003de22  mov     edx, 6
0x18003de27  call    PostResultOrAbortOnFailure
0x18003de2c  mov     eax, r14d
0x18003de2f  add     rsp, 78h
0x18003de33  pop     r15
0x18003de35  pop     r14
0x18003de37  pop     rdi
0x18003de38  pop     rsi
0x18003de39  pop     rbx
0x18003de3a  pop     rbp
0x18003de3b  retn
```
