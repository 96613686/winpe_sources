# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x1800075d0`
- end: `0x180007676`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `166`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000767c`
- `0x180007778`
- `0x180007844`
- `0x180007938`
- `0x180007a18`
- `0x180007af0`
- `0x180009624`
- `0x180015884`
- `0x18002cb3c`
- `0x18003342c`
- `0x1800378f4`
- `0x1800379dc`
- `0x180037abc`

## callees

- `0x180005160`
- `0x1800075d0`
- `0x180007b7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000763d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000763d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000765d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ead9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000765d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ead9`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007650`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003eacc`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007650`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003eacc`

## pseudocode

```c
__int64 __fastcall CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY(__int64 a1)
{
  __int64 v2; // rbx
  int v3; // edi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = 0;
  ulCookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || (v3 = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie)) != 0 )
    v2 = IsolationAwarePrivatezltRgCebPnQQeRff(
           &`CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::c,
           &`CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m,
           a1);
  if ( !IsolationAwarePrivateT_SqbjaYRiRY && v3 )
  {
    if ( v2 )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( !v2 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x1800075d0  mov     rax, rsp
0x1800075d3  mov     [rax+8], rbx
0x1800075d7  mov     [rax+18h], rsi
0x1800075db  push    rdi
0x1800075dc  sub     rsp, 30h
0x1800075e0  mov     rsi, rcx
0x1800075e3  xor     ebx, ebx
0x1800075e5  mov     [rax-10h], rbx
0x1800075e9  xor     edi, edi
0x1800075eb  mov     [rax-18h], edi
0x1800075ee  mov     [rax+10h], rbx
0x1800075f2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x1800075f8  jnz     short loc_18000760D
0x1800075fa  lea     rcx, [rax+10h]; lpCookie
0x1800075fe  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180007603  mov     edi, eax
0x180007605  mov     [rsp+38h+var_18], eax
0x180007609  test    eax, eax
0x18000760b  jz      short loc_18000762B
0x18000760d  mov     r8, rsi
0x180007610  lea     rdx, ?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x180007617  lea     rcx, ?c@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB@@B; IsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB const `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::c
0x18000761e  call    IsolationAwarePrivatezltRgCebPnQQeRff
0x180007623  mov     rbx, rax
0x180007626  mov     [rsp+38h+var_10], rax
0x18000762b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007632  jnz     short loc_180007663
0x180007634  test    edi, edi
0x180007636  jz      short loc_180007663
0x180007638  test    rbx, rbx
0x18000763b  jnz     short loc_180007647
0x18000763d  call    cs:__imp_GetLastError
0x180007643  mov     edi, eax
0x180007645  jmp     short loc_180007649
0x180007647  xor     edi, edi
0x180007649  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000764e  xor     ecx, ecx; dwFlags
0x180007650  call    cs:__imp_DeactivateActCtx
0x180007656  test    rbx, rbx
0x180007659  jnz     short loc_180007663
0x18000765b  mov     ecx, edi; dwErrCode
0x18000765d  call    cs:__imp_SetLastError
0x180007663  mov     rax, rbx
0x180007666  mov     rbx, [rsp+38h+arg_0]
0x18000766b  mov     rsi, [rsp+38h+arg_10]
0x180007670  add     rsp, 30h
0x180007674  pop     rdi
0x180007675  retn
0x18003ea97  push    rbx
0x18003ea99  push    rbp
0x18003ea9a  push    rdi
0x18003ea9b  sub     rsp, 20h
0x18003ea9f  mov     rbp, rdx
0x18003eaa2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003eaa9  jnz     short loc_18003EAE0
0x18003eaab  cmp     dword ptr [rbp+20h], 0
0x18003eaaf  jz      short loc_18003EAE0
0x18003eab1  mov     rbx, [rbp+28h]
0x18003eab5  test    rbx, rbx
0x18003eab8  jnz     short loc_18003EAC4
0x18003eaba  call    cs:__imp_GetLastError
0x18003eac0  mov     edi, eax
0x18003eac2  jmp     short loc_18003EAC6
0x18003eac4  xor     edi, edi
0x18003eac6  mov     rdx, [rbp+48h]; ulCookie
0x18003eaca  xor     ecx, ecx; dwFlags
0x18003eacc  call    cs:__imp_DeactivateActCtx
0x18003ead2  test    rbx, rbx
0x18003ead5  jnz     short loc_18003EAE0
0x18003ead7  mov     ecx, edi; dwErrCode
0x18003ead9  call    cs:__imp_SetLastError
0x18003eadf  nop
0x18003eae0  add     rsp, 20h
0x18003eae4  pop     rdi
0x18003eae5  pop     rbp
0x18003eae6  pop     rbx
0x18003eae7  retn
```
