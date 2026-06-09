# IsolationAwareInitCommonControlsEx

- ea: `0x18003342c`
- end: `0x1800334ef`
- name: `IsolationAwareInitCommonControlsEx`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800333f0`

## callees

- `0x180005160`
- `0x1800075d0`
- `0x18003342c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800334d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003eb96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800334d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003eb96`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800334cb`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003eb8a`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800334cb`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003eb8a`

## string_xrefs

- `0x180033471`: `InitCommonControlsEx`

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
0x18003342c  mov     rax, rsp
0x18003342f  mov     [rax+8], rbx
0x180033433  mov     [rax+18h], rsi
0x180033437  push    rdi
0x180033438  sub     rsp, 30h
0x18003343c  mov     rsi, rcx
0x18003343f  xor     edi, edi
0x180033441  mov     [rax-18h], edi
0x180033444  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18003344b  mov     [rax+10h], rdi
0x18003344f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180033455  jnz     short loc_18003346C
0x180033457  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18003345d  jnz     short loc_18003346C
0x18003345f  lea     rcx, [rax+10h]; lpCookie
0x180033463  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180033468  test    eax, eax
0x18003346a  jz      short loc_1800334DF
0x18003346c  test    rbx, rbx
0x18003346f  jnz     short loc_18003348C
0x180033471  lea     rcx, aInitcommoncont_0; "InitCommonControlsEx"
0x180033478  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18003347d  mov     rbx, rax
0x180033480  test    rax, rax
0x180033483  jz      short loc_18003349D
0x180033485  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18003348c  mov     rcx, rsi
0x18003348f  mov     rax, rbx
0x180033492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033497  mov     edi, eax
0x180033499  mov     [rsp+38h+var_18], eax
0x18003349d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800334a4  jz      short loc_1800334AF
0x1800334a6  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800334ad  jnz     short loc_1800334DD
0x1800334af  test    edi, edi
0x1800334b1  jnz     short loc_1800334C0
0x1800334b3  lea     esi, [rdi+1]
0x1800334b6  call    cs:__imp_GetLastError
0x1800334bc  mov     ebx, eax
0x1800334be  jmp     short loc_1800334C4
0x1800334c0  xor     esi, esi
0x1800334c2  xor     ebx, ebx
0x1800334c4  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800334c9  xor     ecx, ecx; dwFlags
0x1800334cb  call    cs:__imp_DeactivateActCtx
0x1800334d1  test    esi, esi
0x1800334d3  jz      short loc_1800334DD
0x1800334d5  mov     ecx, ebx; dwErrCode
0x1800334d7  call    cs:__imp_SetLastError
0x1800334dd  mov     eax, edi
0x1800334df  mov     rbx, [rsp+38h+arg_0]
0x1800334e4  mov     rsi, [rsp+38h+arg_10]
0x1800334e9  add     rsp, 30h
0x1800334ed  pop     rdi
0x1800334ee  retn
0x18003eb4e  push    rbx
0x18003eb50  push    rbp
0x18003eb51  push    rdi
0x18003eb52  sub     rsp, 20h
0x18003eb56  mov     rbp, rdx
0x18003eb59  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003eb60  jz      short loc_18003EB6B
0x18003eb62  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003eb69  jnz     short loc_18003EB9D
0x18003eb6b  cmp     dword ptr [rbp+20h], 0
0x18003eb6f  jnz     short loc_18003EB80
0x18003eb71  mov     edi, 1
0x18003eb76  call    cs:__imp_GetLastError
0x18003eb7c  mov     ebx, eax
0x18003eb7e  jmp     short loc_18003EB84
0x18003eb80  xor     edi, edi
0x18003eb82  xor     ebx, ebx
0x18003eb84  mov     rdx, [rbp+48h]; ulCookie
0x18003eb88  xor     ecx, ecx; dwFlags
0x18003eb8a  call    cs:__imp_DeactivateActCtx
0x18003eb90  test    edi, edi
0x18003eb92  jz      short loc_18003EB9D
0x18003eb94  mov     ecx, ebx; dwErrCode
0x18003eb96  call    cs:__imp_SetLastError
0x18003eb9c  nop
0x18003eb9d  add     rsp, 20h
0x18003eba1  pop     rdi
0x18003eba2  pop     rbp
0x18003eba3  pop     rbx
0x18003eba4  retn
```
