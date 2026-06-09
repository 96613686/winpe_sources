# IsolationAwareInitCommonControlsEx

- ea: `0x18000a900`
- end: `0x18000a9c3`
- name: `IsolationAwareInitCommonControlsEx`
- size: `195`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007630`

## callees

- `0x180002918`
- `0x1800029e0`
- `0x18000a900`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000a99f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000d1e2`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000a99f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000d1e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d1ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a98a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a98a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1ce`

## string_xrefs

- `0x18000a945`: `InitCommonControlsEx`

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
0x18000a900  mov     rax, rsp
0x18000a903  mov     [rax+8], rbx
0x18000a907  mov     [rax+18h], rsi
0x18000a90b  push    rdi
0x18000a90c  sub     rsp, 30h
0x18000a910  mov     rsi, rcx
0x18000a913  xor     edi, edi
0x18000a915  mov     [rax-18h], edi
0x18000a918  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18000a91f  mov     [rax+10h], rdi
0x18000a923  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x18000a929  jnz     short loc_18000A940
0x18000a92b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18000a931  jnz     short loc_18000A940
0x18000a933  lea     rcx, [rax+10h]; lpCookie
0x18000a937  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000a93c  test    eax, eax
0x18000a93e  jz      short loc_18000A9B3
0x18000a940  test    rbx, rbx
0x18000a943  jnz     short loc_18000A960
0x18000a945  lea     rcx, aInitcommoncont; "InitCommonControlsEx"
0x18000a94c  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000a951  mov     rbx, rax
0x18000a954  test    rax, rax
0x18000a957  jz      short loc_18000A971
0x18000a959  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18000a960  mov     rcx, rsi
0x18000a963  mov     rax, rbx
0x18000a966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a96b  mov     edi, eax
0x18000a96d  mov     [rsp+38h+var_18], eax
0x18000a971  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000a978  jz      short loc_18000A983
0x18000a97a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000a981  jnz     short loc_18000A9B1
0x18000a983  test    edi, edi
0x18000a985  jnz     short loc_18000A994
0x18000a987  lea     esi, [rdi+1]
0x18000a98a  call    cs:__imp_GetLastError
0x18000a990  mov     ebx, eax
0x18000a992  jmp     short loc_18000A998
0x18000a994  xor     esi, esi
0x18000a996  xor     ebx, ebx
0x18000a998  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000a99d  xor     ecx, ecx; dwFlags
0x18000a99f  call    cs:__imp_DeactivateActCtx
0x18000a9a5  test    esi, esi
0x18000a9a7  jz      short loc_18000A9B1
0x18000a9a9  mov     ecx, ebx; dwErrCode
0x18000a9ab  call    cs:__imp_SetLastError
0x18000a9b1  mov     eax, edi
0x18000a9b3  mov     rbx, [rsp+38h+arg_0]
0x18000a9b8  mov     rsi, [rsp+38h+arg_10]
0x18000a9bd  add     rsp, 30h
0x18000a9c1  pop     rdi
0x18000a9c2  retn
0x18000d1a6  push    rbx
0x18000d1a8  push    rbp
0x18000d1a9  push    rdi
0x18000d1aa  sub     rsp, 20h
0x18000d1ae  mov     rbp, rdx
0x18000d1b1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000d1b8  jz      short loc_18000D1C3
0x18000d1ba  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000d1c1  jnz     short loc_18000D1F5
0x18000d1c3  cmp     dword ptr [rbp+20h], 0
0x18000d1c7  jnz     short loc_18000D1D8
0x18000d1c9  mov     edi, 1
0x18000d1ce  call    cs:__imp_GetLastError
0x18000d1d4  mov     ebx, eax
0x18000d1d6  jmp     short loc_18000D1DC
0x18000d1d8  xor     edi, edi
0x18000d1da  xor     ebx, ebx
0x18000d1dc  mov     rdx, [rbp+48h]; ulCookie
0x18000d1e0  xor     ecx, ecx; dwFlags
0x18000d1e2  call    cs:__imp_DeactivateActCtx
0x18000d1e8  test    edi, edi
0x18000d1ea  jz      short loc_18000D1F5
0x18000d1ec  mov     ecx, ebx; dwErrCode
0x18000d1ee  call    cs:__imp_SetLastError
0x18000d1f4  nop
0x18000d1f5  add     rsp, 20h
0x18000d1f9  pop     rdi
0x18000d1fa  pop     rbp
0x18000d1fb  pop     rbx
0x18000d1fc  retn
```
