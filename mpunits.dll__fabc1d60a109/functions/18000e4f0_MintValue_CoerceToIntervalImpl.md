# MintValue_CoerceToIntervalImpl

- ea: `0x18000e4f0`
- end: `0x18000e63e`
- name: `MintValue_CoerceToIntervalImpl`
- size: `334`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000bf10`
- `0x18000db80`
- `0x180017418`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000da24`
- `0x18000e4f0`
- `0x180010a50`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e545`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e5e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e545`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000e5e4`

## string_xrefs

- `0x18000e539`: `mpunits.dll`
- `0x18000e5da`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MintValue_CoerceToIntervalImpl(__int64 a1, __int64 a2)
{
  HMODULE ModuleHandleA; // rax
  __int64 TypeName; // rbx
  HMODULE v6; // rax
  __int64 String_LoadString; // rax
  const wchar_t *v8; // r8
  __int128 v9; // xmm0
  __int128 v11; // [rsp+30h] [rbp-18h] BYREF

  if ( *(_BYTE *)a2 == 15
    && (*(_DWORD *)a2 & 0x100) == 0
    && ((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 24LL)) )
  {
    v11 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v11 = Intlstr_GetString_LoadString(ModuleHandleA, 2066);
    BYTE8(v11) = 0;
    MI_ReportErrorDetails_ForCustomError(7, (int)L"MI", 0, 0);
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 254;
  }
  else
  {
    if ( (__CFSHR__(*(_DWORD *)a2, 9) || (unsigned __int8)(*(_BYTE *)a2 - 1) > 0xAu)
      && (*(_BYTE *)a2 != 13 || __CFSHR__(*(_DWORD *)a2, 9)) )
    {
      v11 = 0xFFu;
      v9 = 0xFFu;
    }
    else
    {
      TypeName = MintValue_GetTypeName(a2);
      v6 = GetModuleHandleA("mpunits.dll");
      String_LoadString = Intlstr_GetString_LoadString(v6, 2083);
      v8 = L"interval";
      if ( String_LoadString )
        v8 = (const wchar_t *)String_LoadString;
      v9 = *(_OWORD *)CoercionNotImplemented_Impl(&v11, TypeName, v8);
    }
    *(_OWORD *)a1 = v9;
  }
  return a1;
}

```

## disassembly

```asm
0x18000e4f0  mov     [rsp+arg_0], rbx
0x18000e4f5  push    rdi
0x18000e4f6  sub     rsp, 40h
0x18000e4fa  cmp     byte ptr [rdx], 0Fh
0x18000e4fd  mov     rbx, rdx
0x18000e500  mov     rdi, rcx
0x18000e503  jnz     loc_18000E5B6
0x18000e509  test    dword ptr [rdx], 100h
0x18000e50f  jnz     loc_18000E5B6
0x18000e515  mov     rcx, [rdx+8]
0x18000e519  mov     rax, cs:off_180047B90
0x18000e520  mov     rcx, [rcx+18h]
0x18000e524  mov     rax, [rax+8]
0x18000e528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e52d  test    rax, rax
0x18000e530  jz      loc_18000E5B6
0x18000e536  xorps   xmm0, xmm0
0x18000e539  lea     rcx, ModuleName; "mpunits.dll"
0x18000e540  movups  [rsp+48h+var_18], xmm0
0x18000e545  call    cs:__imp_GetModuleHandleA
0x18000e54b  mov     rcx, rax
0x18000e54e  mov     edx, 812h
0x18000e553  call    _Intlstr_GetString_LoadString
0x18000e558  mov     qword ptr [rsp+48h+var_18], rax
0x18000e55d  lea     r9, [rsp+48h+var_18]
0x18000e562  mov     byte ptr [rsp+48h+var_18+8], 0
0x18000e567  lea     rdx, aMi; "MI"
0x18000e56e  movaps  xmm0, [rsp+48h+var_18]
0x18000e573  mov     r8d, 0Bh
0x18000e579  mov     [rsp+48h+var_20], 0; __int64
0x18000e582  movdqa  [rsp+48h+var_18], xmm0
0x18000e588  mov     [rsp+48h+var_28], 0; __int64
0x18000e591  lea     ecx, [r8-4]; int
0x18000e595  call    MI_ReportErrorDetails_ForCustomError
0x18000e59a  xor     edx, edx
0x18000e59c  xor     ecx, ecx
0x18000e59e  mov     eax, 0FFh
0x18000e5a3  mov     [rdi+4], edx
0x18000e5a6  and     eax, 0FFFFFFFEh
0x18000e5a9  mov     [rdi+8], rcx
0x18000e5ad  or      eax, 0FEh
0x18000e5b2  mov     [rdi], eax
0x18000e5b4  jmp     short loc_18000E630
0x18000e5b6  mov     ecx, [rbx]
0x18000e5b8  shr     ecx, 9
0x18000e5bb  sbb     ecx, ecx
0x18000e5bd  test    ecx, ecx
0x18000e5bf  jnz     short loc_18000E5C9
0x18000e5c1  mov     al, [rbx]
0x18000e5c3  dec     al
0x18000e5c5  cmp     al, 0Ah
0x18000e5c7  jbe     short loc_18000E5D2
0x18000e5c9  cmp     byte ptr [rbx], 0Dh
0x18000e5cc  jnz     short loc_18000E617
0x18000e5ce  test    ecx, ecx
0x18000e5d0  jnz     short loc_18000E617
0x18000e5d2  mov     rcx, rbx
0x18000e5d5  call    MintValue_GetTypeName
0x18000e5da  lea     rcx, ModuleName; "mpunits.dll"
0x18000e5e1  mov     rbx, rax
0x18000e5e4  call    cs:__imp_GetModuleHandleA
0x18000e5ea  mov     rcx, rax
0x18000e5ed  mov     edx, 823h
0x18000e5f2  call    _Intlstr_GetString_LoadString
0x18000e5f7  test    rax, rax
0x18000e5fa  lea     r8, aInterval; "interval"
0x18000e601  mov     rdx, rbx
0x18000e604  lea     rcx, [rsp+48h+var_18]
0x18000e609  cmovnz  r8, rax
0x18000e60d  call    CoercionNotImplemented_Impl
0x18000e612  movups  xmm0, xmmword ptr [rax]
0x18000e615  jmp     short loc_18000E62C
0x18000e617  xor     eax, eax
0x18000e619  mov     qword ptr [rsp+48h+var_18], 0FFh
0x18000e622  mov     qword ptr [rsp+48h+var_18+8], rax
0x18000e627  movups  xmm0, [rsp+48h+var_18]
0x18000e62c  movdqu  xmmword ptr [rdi], xmm0
0x18000e630  mov     rbx, [rsp+48h+arg_0]
0x18000e635  mov     rax, rdi
0x18000e638  add     rsp, 40h
0x18000e63c  pop     rdi
0x18000e63d  retn
```
