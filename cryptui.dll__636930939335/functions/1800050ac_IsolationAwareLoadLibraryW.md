# IsolationAwareLoadLibraryW

- ea: `0x1800050ac`
- end: `0x180005157`
- name: `IsolationAwareLoadLibraryW`
- size: `171`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005464`
- `0x18000a2ac`
- `0x18001f020`

## callees

- `0x1800050ac`
- `0x180005160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000512b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ea3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000512b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ea3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000514c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ea5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000514c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ea5e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180005103`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180005103`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180005140`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ea52`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180005140`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ea52`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryW(LPCWSTR lpLibFileName)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rbx
  int v5; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  v4 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
    {
      v5 = 0;
      LastError = 0;
    }
    else
    {
      v5 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v5 )
      SetLastError(LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x1800050ac  mov     rax, rsp
0x1800050af  mov     [rax+8], rbx
0x1800050b3  mov     [rax+18h], rsi
0x1800050b7  push    rdi
0x1800050b8  sub     rsp, 30h
0x1800050bc  mov     rbx, rcx
0x1800050bf  mov     qword ptr [rax-18h], 0
0x1800050c7  mov     qword ptr [rax+10h], 0
0x1800050cf  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800050d6  jnz     short loc_180005100
0x1800050d8  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800050df  jnz     short loc_180005100
0x1800050e1  lea     rcx, [rax+10h]; lpCookie
0x1800050e5  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800050ea  test    eax, eax
0x1800050ec  jnz     short loc_180005100
0x1800050ee  xor     eax, eax
0x1800050f0  mov     rbx, [rsp+38h+arg_0]
0x1800050f5  mov     rsi, [rsp+38h+arg_10]
0x1800050fa  add     rsp, 30h
0x1800050fe  pop     rdi
0x1800050ff  retn
0x180005100  mov     rcx, rbx; lpLibFileName
0x180005103  call    cs:__imp_LoadLibraryW
0x180005109  mov     rbx, rax
0x18000510c  mov     [rsp+38h+var_18], rax
0x180005111  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180005118  jz      short loc_180005123
0x18000511a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180005121  jnz     short loc_180005152
0x180005123  test    rbx, rbx
0x180005126  jnz     short loc_180005135
0x180005128  lea     esi, [rbx+1]
0x18000512b  call    cs:__imp_GetLastError
0x180005131  mov     edi, eax
0x180005133  jmp     short loc_180005139
0x180005135  xor     esi, esi
0x180005137  xor     edi, edi
0x180005139  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000513e  xor     ecx, ecx; dwFlags
0x180005140  call    cs:__imp_DeactivateActCtx
0x180005146  test    esi, esi
0x180005148  jz      short loc_180005152
0x18000514a  mov     ecx, edi; dwErrCode
0x18000514c  call    cs:__imp_SetLastError
0x180005152  mov     rax, rbx
0x180005155  jmp     short loc_1800050F0
0x18003ea15  push    rbx
0x18003ea17  push    rbp
0x18003ea18  push    rdi
0x18003ea19  sub     rsp, 20h
0x18003ea1d  mov     rbp, rdx
0x18003ea20  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003ea27  jz      short loc_18003EA32
0x18003ea29  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003ea30  jnz     short loc_18003EA65
0x18003ea32  cmp     qword ptr [rbp+20h], 0
0x18003ea37  jnz     short loc_18003EA48
0x18003ea39  mov     edi, 1
0x18003ea3e  call    cs:__imp_GetLastError
0x18003ea44  mov     ebx, eax
0x18003ea46  jmp     short loc_18003EA4C
0x18003ea48  xor     edi, edi
0x18003ea4a  xor     ebx, ebx
0x18003ea4c  mov     rdx, [rbp+48h]; ulCookie
0x18003ea50  xor     ecx, ecx; dwFlags
0x18003ea52  call    cs:__imp_DeactivateActCtx
0x18003ea58  test    edi, edi
0x18003ea5a  jz      short loc_18003EA65
0x18003ea5c  mov     ecx, ebx; dwErrCode
0x18003ea5e  call    cs:__imp_SetLastError
0x18003ea64  nop
0x18003ea65  add     rsp, 20h
0x18003ea69  pop     rdi
0x18003ea6a  pop     rbp
0x18003ea6b  pop     rbx
0x18003ea6c  retn
```
