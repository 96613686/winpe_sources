# IsolationAwareCreatePropertySheetPageW

- ea: `0x180008e8c`
- end: `0x180008f7d`
- name: `IsolationAwareCreatePropertySheetPageW`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005ab0`
- `0x1800075f0`
- `0x18001d134`

## callees

- `0x180008e8c`
- `0x18000911c`
- `0x180009220`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008f4e`
- `KERNEL32!GetLastError` at `0x1800229eb`
- `KERNEL32!GetLastError` at `0x180008f4e`
- `KERNEL32!GetLastError` at `0x1800229eb`
- `KERNEL32!SetLastError` at `0x180008f6f`
- `KERNEL32!SetLastError` at `0x180022a0b`
- `KERNEL32!SetLastError` at `0x180008f6f`
- `KERNEL32!SetLastError` at `0x180022a0b`
- `KERNEL32!DeactivateActCtx` at `0x180008f63`
- `KERNEL32!DeactivateActCtx` at `0x1800229ff`
- `KERNEL32!DeactivateActCtx` at `0x180008f63`
- `KERNEL32!DeactivateActCtx` at `0x1800229ff`

## string_xrefs

- `0x180008ee4`: `CreatePropertySheetPageW`

## pseudocode

```c
__int64 __fastcall IsolationAwareCreatePropertySheetPageW(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v5; // rax
  int v6; // eax
  int v7; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v3 = `IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( v3 )
    goto LABEL_8;
  v5 = PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("CreatePropertySheetPageW");
  if ( v5 )
  {
    `IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn = v5;
LABEL_8:
    v6 = *(_DWORD *)(a1 + 4);
    if ( (v6 & 0x4000) == 0 && *(_DWORD *)a1 >= 0x60u )
    {
      *(_DWORD *)(a1 + 4) = v6 | 0x4000;
      *(_QWORD *)(a1 + 88) = WinbaseIsolationAwarePrivateT_UnPgpgk;
    }
    v2 = ((__int64 (__fastcall *)(__int64))`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(a1);
  }
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v7 = 0;
      LastError = 0;
    }
    else
    {
      v7 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v7 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180008e8c  mov     rax, rsp
0x180008e8f  mov     [rax+10h], rbx
0x180008e93  mov     [rax+18h], rsi
0x180008e97  push    rdi
0x180008e98  sub     rsp, 30h
0x180008e9c  mov     rdi, rcx
0x180008e9f  xor     ebx, ebx
0x180008ea1  mov     [rax-18h], rbx
0x180008ea5  mov     rsi, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180008eac  mov     [rax+8], rbx
0x180008eb0  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, ebx
0x180008eb6  jnz     short loc_180008EDF
0x180008eb8  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x180008ebe  jnz     short loc_180008EDF
0x180008ec0  lea     rcx, [rax+8]; lpCookie
0x180008ec4  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180008ec9  test    eax, eax
0x180008ecb  jnz     short loc_180008EDF
0x180008ecd  xor     eax, eax
0x180008ecf  mov     rbx, [rsp+38h+arg_8]
0x180008ed4  mov     rsi, [rsp+38h+arg_10]
0x180008ed9  add     rsp, 30h
0x180008edd  pop     rdi
0x180008ede  retn
0x180008edf  test    rsi, rsi
0x180008ee2  jnz     short loc_180008EFC
0x180008ee4  lea     rcx, aCreateproperty; "CreatePropertySheetPageW"
0x180008eeb  call    PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180008ef0  test    rax, rax
0x180008ef3  jz      short loc_180008F34
0x180008ef5  mov     cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA, rax; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180008efc  mov     eax, [rdi+4]
0x180008eff  mov     ecx, 4000h
0x180008f04  test    ecx, eax
0x180008f06  jnz     short loc_180008F1D
0x180008f08  cmp     dword ptr [rdi], 60h ; '`'
0x180008f0b  jb      short loc_180008F1D
0x180008f0d  or      eax, ecx
0x180008f0f  mov     [rdi+4], eax
0x180008f12  mov     rax, cs:WinbaseIsolationAwarePrivateT_UnPgpgk
0x180008f19  mov     [rdi+58h], rax
0x180008f1d  mov     rcx, rdi
0x180008f20  mov     rax, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180008f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f2c  mov     rbx, rax
0x180008f2f  mov     [rsp+38h+var_18], rax
0x180008f34  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180008f3b  jz      short loc_180008F46
0x180008f3d  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180008f44  jnz     short loc_180008F75
0x180008f46  test    rbx, rbx
0x180008f49  jnz     short loc_180008F58
0x180008f4b  lea     esi, [rbx+1]
0x180008f4e  call    cs:__imp_GetLastError
0x180008f54  mov     edi, eax
0x180008f56  jmp     short loc_180008F5C
0x180008f58  xor     esi, esi
0x180008f5a  xor     edi, edi
0x180008f5c  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180008f61  xor     ecx, ecx; dwFlags
0x180008f63  call    cs:__imp_DeactivateActCtx
0x180008f69  test    esi, esi
0x180008f6b  jz      short loc_180008F75
0x180008f6d  mov     ecx, edi; dwErrCode
0x180008f6f  call    cs:__imp_SetLastError
0x180008f75  mov     rax, rbx
0x180008f78  jmp     loc_180008ECF
0x1800229c2  push    rbx
0x1800229c4  push    rbp
0x1800229c5  push    rdi
0x1800229c6  sub     rsp, 20h
0x1800229ca  mov     rbp, rdx
0x1800229cd  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800229d4  jz      short loc_1800229DF
0x1800229d6  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800229dd  jnz     short loc_180022A12
0x1800229df  cmp     qword ptr [rbp+20h], 0
0x1800229e4  jnz     short loc_1800229F5
0x1800229e6  mov     edi, 1
0x1800229eb  call    cs:__imp_GetLastError
0x1800229f1  mov     ebx, eax
0x1800229f3  jmp     short loc_1800229F9
0x1800229f5  xor     edi, edi
0x1800229f7  xor     ebx, ebx
0x1800229f9  mov     rdx, [rbp+40h]; ulCookie
0x1800229fd  xor     ecx, ecx; dwFlags
0x1800229ff  call    cs:__imp_DeactivateActCtx
0x180022a05  test    edi, edi
0x180022a07  jz      short loc_180022A12
0x180022a09  mov     ecx, ebx; dwErrCode
0x180022a0b  call    cs:__imp_SetLastError
0x180022a11  nop
0x180022a12  add     rsp, 20h
0x180022a16  pop     rdi
0x180022a17  pop     rbp
0x180022a18  pop     rbx
0x180022a19  retn
```
