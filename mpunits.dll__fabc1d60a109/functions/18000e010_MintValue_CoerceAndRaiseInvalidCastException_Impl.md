# MintValue_CoerceAndRaiseInvalidCastException_Impl

- ea: `0x18000e010`
- end: `0x18000e0d7`
- name: `MintValue_CoerceAndRaiseInvalidCastException_Impl`
- size: `199`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000be30`
- `0x18000c454`
- `0x18000db80`
- `0x18000f3e0`
- `0x18000f580`
- `0x180011db4`
- `0x180017418`
- `0x1800178ec`
- `0x180018480`
- `0x180018600`
- `0x180018830`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18000e010`
- `0x180011160`
- `0x180013c54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e049`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e049`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000e0ab`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000e0ab`

## string_xrefs

- `0x18000e03a`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MintValue_CoerceAndRaiseInvalidCastException_Impl(__int64 a1, unsigned int *a2, unsigned int a3)
{
  _OWORD *v5; // rax
  void *v6; // rbp
  __int64 v7; // rbx
  HMODULE ModuleHandleA; // rax
  _OWORD v10[3]; // [rsp+40h] [rbp-38h] BYREF

  v5 = MintValue_ToErrorString(v10, a2);
  v6 = *(void **)v5;
  v7 = *((_QWORD *)v5 + 1);
  GetMintTypeName(a3);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2089, v6);
  MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
  if ( (_BYTE)v7 )
    LocalFree(v6);
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x18000e010  push    rbx
0x18000e012  push    rbp
0x18000e013  push    rsi
0x18000e014  push    rdi
0x18000e015  sub     rsp, 58h
0x18000e019  mov     rsi, rcx
0x18000e01c  mov     edi, r8d
0x18000e01f  lea     rcx, [rsp+78h+var_38]
0x18000e024  call    MintValue_ToErrorString
0x18000e029  mov     ecx, edi
0x18000e02b  mov     rbp, [rax]
0x18000e02e  mov     rbx, [rax+8]
0x18000e032  call    GetMintTypeName
0x18000e037  xorps   xmm0, xmm0
0x18000e03a  lea     rcx, ModuleName; "mpunits.dll"
0x18000e041  movups  [rsp+78h+var_48], xmm0
0x18000e046  mov     rdi, rax
0x18000e049  call    cs:__imp_GetModuleHandleA
0x18000e04f  mov     r9, rdi
0x18000e052  mov     r8, rbp
0x18000e055  mov     rcx, rax
0x18000e058  mov     edx, 829h
0x18000e05d  call    _Intlstr_FormatString_FormatMessage
0x18000e062  mov     qword ptr [rsp+78h+var_48], rax
0x18000e067  lea     r9, [rsp+78h+var_48]
0x18000e06c  mov     byte ptr [rsp+78h+var_48+8], 1
0x18000e071  lea     rdx, aMi; "MI"
0x18000e078  movaps  xmm0, [rsp+78h+var_48]
0x18000e07d  mov     r8d, 5
0x18000e083  mov     [rsp+78h+var_50], 0; __int64
0x18000e08c  movdqa  [rsp+78h+var_48], xmm0
0x18000e092  mov     [rsp+78h+var_58], 0; __int64
0x18000e09b  lea     ecx, [r8-1]; int
0x18000e09f  call    MI_ReportErrorDetails_ForCustomError
0x18000e0a4  test    bl, bl
0x18000e0a6  jz      short loc_18000E0B1
0x18000e0a8  mov     rcx, rbp; hMem
0x18000e0ab  call    cs:__imp_LocalFree
0x18000e0b1  mov     eax, 0FFh
0x18000e0b6  xor     edx, edx
0x18000e0b8  and     eax, 0FFFFFFFEh
0x18000e0bb  mov     [rsi+4], edx
0x18000e0be  xor     ecx, ecx
0x18000e0c0  or      eax, 0FEh
0x18000e0c5  mov     [rsi+8], rcx
0x18000e0c9  mov     [rsi], eax
0x18000e0cb  mov     rax, rsi
0x18000e0ce  add     rsp, 58h
0x18000e0d2  pop     rdi
0x18000e0d3  pop     rsi
0x18000e0d4  pop     rbp
0x18000e0d5  pop     rbx
0x18000e0d6  retn
```
