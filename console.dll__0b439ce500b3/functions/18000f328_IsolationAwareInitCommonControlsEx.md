# IsolationAwareInitCommonControlsEx

- ea: `0x18000f328`
- end: `0x18000f3f7`
- name: `IsolationAwareInitCommonControlsEx`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f100`

## callees

- `0x1800071a0`
- `0x18000f23c`
- `0x18000f328`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f3d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001950b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f3d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001950b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194df`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000f3c6`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800194f9`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000f3c6`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800194f9`

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
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY();
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
0x18000f328  mov     rax, rsp
0x18000f32b  mov     [rax+8], rbx
0x18000f32f  mov     [rax+18h], rsi
0x18000f333  push    rdi
0x18000f334  sub     rsp, 30h
0x18000f338  mov     rsi, rcx
0x18000f33b  xor     edi, edi
0x18000f33d  mov     [rax-18h], edi
0x18000f340  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18000f347  mov     [rax+10h], rdi
0x18000f34b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x18000f351  jnz     short loc_18000F368
0x18000f353  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18000f359  jnz     short loc_18000F368
0x18000f35b  lea     rcx, [rax+10h]; lpCookie
0x18000f35f  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000f364  test    eax, eax
0x18000f366  jz      short loc_18000F3E6
0x18000f368  test    rbx, rbx
0x18000f36b  jnz     short loc_18000F381
0x18000f36d  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000f372  mov     rbx, rax
0x18000f375  test    rax, rax
0x18000f378  jz      short loc_18000F392
0x18000f37a  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18000f381  mov     rcx, rsi
0x18000f384  mov     rax, rbx
0x18000f387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f38c  mov     edi, eax
0x18000f38e  mov     [rsp+38h+var_18], eax
0x18000f392  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000f399  jz      short loc_18000F3A4
0x18000f39b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000f3a2  jnz     short loc_18000F3E4
0x18000f3a4  test    edi, edi
0x18000f3a6  jnz     short loc_18000F3BB
0x18000f3a8  lea     esi, [rdi+1]
0x18000f3ab  call    cs:__imp_GetLastError
0x18000f3b2  nop     dword ptr [rax+rax+00h]
0x18000f3b7  mov     ebx, eax
0x18000f3b9  jmp     short loc_18000F3BF
0x18000f3bb  xor     esi, esi
0x18000f3bd  xor     ebx, ebx
0x18000f3bf  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000f3c4  xor     ecx, ecx; dwFlags
0x18000f3c6  call    cs:__imp_DeactivateActCtx
0x18000f3cd  nop     dword ptr [rax+rax+00h]
0x18000f3d2  test    esi, esi
0x18000f3d4  jz      short loc_18000F3E4
0x18000f3d6  mov     ecx, ebx; dwErrCode
0x18000f3d8  call    cs:__imp_SetLastError
0x18000f3df  nop     dword ptr [rax+rax+00h]
0x18000f3e4  mov     eax, edi
0x18000f3e6  mov     rbx, [rsp+38h+arg_0]
0x18000f3eb  mov     rsi, [rsp+38h+arg_10]
0x18000f3f0  add     rsp, 30h
0x18000f3f4  pop     rdi
0x18000f3f5  retn
0x1800194b7  push    rbx
0x1800194b9  push    rbp
0x1800194ba  push    rdi
0x1800194bb  sub     rsp, 20h
0x1800194bf  mov     rbp, rdx
0x1800194c2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800194c9  jz      short loc_1800194D4
0x1800194cb  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800194d2  jnz     short loc_180019518
0x1800194d4  cmp     dword ptr [rbp+20h], 0
0x1800194d8  jnz     short loc_1800194EF
0x1800194da  mov     edi, 1
0x1800194df  call    cs:__imp_GetLastError
0x1800194e6  nop     dword ptr [rax+rax+00h]
0x1800194eb  mov     ebx, eax
0x1800194ed  jmp     short loc_1800194F3
0x1800194ef  xor     edi, edi
0x1800194f1  xor     ebx, ebx
0x1800194f3  mov     rdx, [rbp+48h]; ulCookie
0x1800194f7  xor     ecx, ecx; dwFlags
0x1800194f9  call    cs:__imp_DeactivateActCtx
0x180019500  nop     dword ptr [rax+rax+00h]
0x180019505  test    edi, edi
0x180019507  jz      short loc_180019518
0x180019509  mov     ecx, ebx; dwErrCode
0x18001950b  call    cs:__imp_SetLastError
0x180019512  nop     dword ptr [rax+rax+00h]
0x180019517  nop
0x180019518  add     rsp, 20h
0x18001951c  pop     rdi
0x18001951d  pop     rbp
0x18001951e  pop     rbx
0x18001951f  retn
```
