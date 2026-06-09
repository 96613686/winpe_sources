# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x18000f23c`
- end: `0x18000f2f1`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f328`

## callees

- `0x1800071a0`
- `0x18000886c`
- `0x18000f23c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f2d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001949b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f2d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001949b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019470`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000f2c3`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180019488`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000f2c3`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180019488`

## string_xrefs

- `0x18000f276`: `InitCommonControlsEx`

## pseudocode

```c
__int64 CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY()
{
  __int64 v0; // rbx
  int v1; // edi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  v1 = 0;
  ulCookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || (v1 = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie)) != 0 )
    v0 = IsolationAwarePrivatezltRgCebPnQQeRff(
           &`CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::c,
           &`CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m,
           "InitCommonControlsEx");
  if ( !IsolationAwarePrivateT_SqbjaYRiRY && v1 )
  {
    if ( v0 )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( !v0 )
      SetLastError(LastError);
  }
  return v0;
}

```

## disassembly

```asm
0x18000f23c  mov     rax, rsp
0x18000f23f  mov     [rax+10h], rbx
0x18000f243  mov     [rax+8], rcx
0x18000f247  push    rdi
0x18000f248  sub     rsp, 30h
0x18000f24c  xor     ebx, ebx
0x18000f24e  mov     [rax-10h], rbx
0x18000f252  xor     edi, edi
0x18000f254  mov     [rax-18h], edi
0x18000f257  mov     [rax+8], rbx
0x18000f25b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18000f261  jnz     short loc_18000F276
0x18000f263  lea     rcx, [rax+8]; lpCookie
0x18000f267  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000f26c  mov     edi, eax
0x18000f26e  mov     [rsp+38h+var_18], eax
0x18000f272  test    eax, eax
0x18000f274  jz      short loc_18000F298
0x18000f276  lea     r8, aInitcommoncont; "InitCommonControlsEx"
0x18000f27d  lea     rdx, ?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000f284  lea     rcx, ?c@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB@@B; IsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB const `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::c
0x18000f28b  call    IsolationAwarePrivatezltRgCebPnQQeRff
0x18000f290  mov     rbx, rax
0x18000f293  mov     [rsp+38h+var_10], rax
0x18000f298  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000f29f  jnz     short loc_18000F2E2
0x18000f2a1  test    edi, edi
0x18000f2a3  jz      short loc_18000F2E2
0x18000f2a5  test    rbx, rbx
0x18000f2a8  jnz     short loc_18000F2BA
0x18000f2aa  call    cs:__imp_GetLastError
0x18000f2b1  nop     dword ptr [rax+rax+00h]
0x18000f2b6  mov     edi, eax
0x18000f2b8  jmp     short loc_18000F2BC
0x18000f2ba  xor     edi, edi
0x18000f2bc  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000f2c1  xor     ecx, ecx; dwFlags
0x18000f2c3  call    cs:__imp_DeactivateActCtx
0x18000f2ca  nop     dword ptr [rax+rax+00h]
0x18000f2cf  test    rbx, rbx
0x18000f2d2  jnz     short loc_18000F2E2
0x18000f2d4  mov     ecx, edi; dwErrCode
0x18000f2d6  call    cs:__imp_SetLastError
0x18000f2dd  nop     dword ptr [rax+rax+00h]
0x18000f2e2  mov     rax, rbx
0x18000f2e5  mov     rbx, [rsp+38h+arg_8]
0x18000f2ea  add     rsp, 30h
0x18000f2ee  pop     rdi
0x18000f2ef  retn
0x18001944d  push    rbx
0x18001944f  push    rbp
0x180019450  push    rdi
0x180019451  sub     rsp, 20h
0x180019455  mov     rbp, rdx
0x180019458  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001945f  jnz     short loc_1800194A8
0x180019461  cmp     dword ptr [rbp+20h], 0
0x180019465  jz      short loc_1800194A8
0x180019467  mov     rbx, [rbp+28h]
0x18001946b  test    rbx, rbx
0x18001946e  jnz     short loc_180019480
0x180019470  call    cs:__imp_GetLastError
0x180019477  nop     dword ptr [rax+rax+00h]
0x18001947c  mov     edi, eax
0x18001947e  jmp     short loc_180019482
0x180019480  xor     edi, edi
0x180019482  mov     rdx, [rbp+40h]; ulCookie
0x180019486  xor     ecx, ecx; dwFlags
0x180019488  call    cs:__imp_DeactivateActCtx
0x18001948f  nop     dword ptr [rax+rax+00h]
0x180019494  test    rbx, rbx
0x180019497  jnz     short loc_1800194A8
0x180019499  mov     ecx, edi; dwErrCode
0x18001949b  call    cs:__imp_SetLastError
0x1800194a2  nop     dword ptr [rax+rax+00h]
0x1800194a7  nop
0x1800194a8  add     rsp, 20h
0x1800194ac  pop     rdi
0x1800194ad  pop     rbp
0x1800194ae  pop     rbx
0x1800194af  retn
```
