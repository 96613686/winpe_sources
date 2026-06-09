# IsolationAwareInitCommonControlsEx

- ea: `0x1800bf624`
- end: `0x1800bf6e7`
- name: `IsolationAwareInitCommonControlsEx`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800be3fc`

## callees

- `0x1800bf468`
- `0x1800bf624`
- `0x1800bf6f0`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5381`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bf6cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d53a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bf6cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d53a1`
- `KERNEL32!DeactivateActCtx` at `0x1800bf6c3`
- `KERNEL32!DeactivateActCtx` at `0x1800d5395`
- `KERNEL32!DeactivateActCtx` at `0x1800bf6c3`
- `KERNEL32!DeactivateActCtx` at `0x1800d5395`

## string_xrefs

- `0x1800bf669`: `InitCommonControlsEx`

## pseudocode

```c
__int64 __fastcall IsolationAwareInitCommonControlsEx(__int64 a1)
{
  unsigned int v2; // edi
  __int64 (__fastcall *v3)(__int64); // rbx
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = (__int64 (__fastcall *)(__int64))`IsolationAwareInitCommonControlsEx'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    result = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)result )
      return result;
  }
  if ( !v3 )
  {
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("InitCommonControlsEx");
    v3 = (__int64 (__fastcall *)(__int64))v5;
    if ( !v5 )
      goto LABEL_8;
    `IsolationAwareInitCommonControlsEx'::`2'::s_pfn = v5;
  }
  v2 = v3(a1);
LABEL_8:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v6 = 0;
      LastError = 0;
    }
    else
    {
      v6 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v6 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x1800bf624  mov     rax, rsp
0x1800bf627  mov     [rax+8], rbx
0x1800bf62b  mov     [rax+18h], rsi
0x1800bf62f  push    rdi
0x1800bf630  sub     rsp, 30h
0x1800bf634  mov     rsi, rcx
0x1800bf637  xor     edi, edi
0x1800bf639  mov     [rax-18h], edi
0x1800bf63c  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x1800bf643  mov     [rax+10h], rdi
0x1800bf647  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x1800bf64d  jnz     short loc_1800BF664
0x1800bf64f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x1800bf655  jnz     short loc_1800BF664
0x1800bf657  lea     rcx, [rax+10h]; lpCookie
0x1800bf65b  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800bf660  test    eax, eax
0x1800bf662  jz      short loc_1800BF6D7
0x1800bf664  test    rbx, rbx
0x1800bf667  jnz     short loc_1800BF684
0x1800bf669  lea     rcx, aInitcommoncont; "InitCommonControlsEx"
0x1800bf670  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x1800bf675  mov     rbx, rax
0x1800bf678  test    rax, rax
0x1800bf67b  jz      short loc_1800BF695
0x1800bf67d  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x1800bf684  mov     rcx, rsi
0x1800bf687  mov     rax, rbx
0x1800bf68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf68f  mov     edi, eax
0x1800bf691  mov     [rsp+38h+var_18], eax
0x1800bf695  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800bf69c  jz      short loc_1800BF6A7
0x1800bf69e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800bf6a5  jnz     short loc_1800BF6D5
0x1800bf6a7  test    edi, edi
0x1800bf6a9  jnz     short loc_1800BF6B8
0x1800bf6ab  lea     esi, [rdi+1]
0x1800bf6ae  call    cs:__imp_GetLastError
0x1800bf6b4  mov     ebx, eax
0x1800bf6b6  jmp     short loc_1800BF6BC
0x1800bf6b8  xor     esi, esi
0x1800bf6ba  xor     ebx, ebx
0x1800bf6bc  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800bf6c1  xor     ecx, ecx; dwFlags
0x1800bf6c3  call    cs:__imp_DeactivateActCtx
0x1800bf6c9  test    esi, esi
0x1800bf6cb  jz      short loc_1800BF6D5
0x1800bf6cd  mov     ecx, ebx; dwErrCode
0x1800bf6cf  call    cs:__imp_SetLastError
0x1800bf6d5  mov     eax, edi
0x1800bf6d7  mov     rbx, [rsp+38h+arg_0]
0x1800bf6dc  mov     rsi, [rsp+38h+arg_10]
0x1800bf6e1  add     rsp, 30h
0x1800bf6e5  pop     rdi
0x1800bf6e6  retn
0x1800d5359  push    rbx
0x1800d535b  push    rbp
0x1800d535c  push    rdi
0x1800d535d  sub     rsp, 20h
0x1800d5361  mov     rbp, rdx
0x1800d5364  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800d536b  jz      short loc_1800D5376
0x1800d536d  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800d5374  jnz     short loc_1800D53A8
0x1800d5376  cmp     dword ptr [rbp+20h], 0
0x1800d537a  jnz     short loc_1800D538B
0x1800d537c  mov     edi, 1
0x1800d5381  call    cs:__imp_GetLastError
0x1800d5387  mov     ebx, eax
0x1800d5389  jmp     short loc_1800D538F
0x1800d538b  xor     edi, edi
0x1800d538d  xor     ebx, ebx
0x1800d538f  mov     rdx, [rbp+48h]; ulCookie
0x1800d5393  xor     ecx, ecx; dwFlags
0x1800d5395  call    cs:__imp_DeactivateActCtx
0x1800d539b  test    edi, edi
0x1800d539d  jz      short loc_1800D53A8
0x1800d539f  mov     ecx, ebx; dwErrCode
0x1800d53a1  call    cs:__imp_SetLastError
0x1800d53a7  nop
0x1800d53a8  add     rsp, 20h
0x1800d53ac  pop     rdi
0x1800d53ad  pop     rbp
0x1800d53ae  pop     rbx
0x1800d53af  retn
```
