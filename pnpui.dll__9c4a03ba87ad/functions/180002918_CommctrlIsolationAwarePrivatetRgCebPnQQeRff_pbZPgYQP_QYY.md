# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x180002918`
- end: `0x1800029da`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002a80`
- `0x18000a900`

## callees

- `0x180002918`
- `0x1800029e0`
- `0x180002a70`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800029b4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000d12b`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800029b4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000d12b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d138`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d119`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002981`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002981`

## pseudocode

```c
FARPROC __fastcall CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY(LPCSTR lpProcName)
{
  FARPROC ProcAddress; // rbx
  int v3; // edi
  HMODULE v4; // rax
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ProcAddress = 0;
  v3 = 0;
  ulCookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || (v3 = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie)) != 0 )
  {
    v4 = `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m;
    if ( `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m )
    {
LABEL_6:
      ProcAddress = GetProcAddress(v4, lpProcName);
      goto LABEL_7;
    }
    ProcAddress = 0;
    v4 = IsolationAwarePrivatezlybNQyVOeNelJ(L"Comctl32.dll");
    if ( v4 )
    {
      `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m = v4;
      goto LABEL_6;
    }
  }
LABEL_7:
  if ( !IsolationAwarePrivateT_SqbjaYRiRY && v3 )
  {
    if ( ProcAddress )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( !ProcAddress )
      SetLastError(LastError);
  }
  return ProcAddress;
}

```

## disassembly

```asm
0x180002918  mov     rax, rsp
0x18000291b  mov     [rax+8], rbx
0x18000291f  mov     [rax+18h], rsi
0x180002923  push    rdi
0x180002924  sub     rsp, 30h
0x180002928  mov     rsi, rcx
0x18000292b  xor     ebx, ebx
0x18000292d  mov     [rax-10h], rbx
0x180002931  xor     edi, edi
0x180002933  mov     [rax-18h], edi
0x180002936  mov     [rax+10h], rbx
0x18000293a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180002940  jnz     short loc_180002955
0x180002942  lea     rcx, [rax+10h]; lpCookie
0x180002946  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000294b  mov     edi, eax
0x18000294d  mov     [rsp+38h+var_18], eax
0x180002951  test    eax, eax
0x180002953  jz      short loc_18000298F
0x180002955  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000295c  test    rax, rax
0x18000295f  jnz     short loc_18000297B
0x180002961  xor     ebx, ebx
0x180002963  mov     rcx, cs:lpLibFileName; lpLibFileName
0x18000296a  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x18000296f  test    rax, rax
0x180002972  jz      short loc_18000298A
0x180002974  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000297b  mov     rdx, rsi; lpProcName
0x18000297e  mov     rcx, rax; hModule
0x180002981  call    cs:__imp_GetProcAddress
0x180002987  mov     rbx, rax
0x18000298a  mov     [rsp+38h+var_10], rbx
0x18000298f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180002996  jnz     short loc_1800029C7
0x180002998  test    edi, edi
0x18000299a  jz      short loc_1800029C7
0x18000299c  test    rbx, rbx
0x18000299f  jnz     short loc_1800029AB
0x1800029a1  call    cs:__imp_GetLastError
0x1800029a7  mov     edi, eax
0x1800029a9  jmp     short loc_1800029AD
0x1800029ab  xor     edi, edi
0x1800029ad  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800029b2  xor     ecx, ecx; dwFlags
0x1800029b4  call    cs:__imp_DeactivateActCtx
0x1800029ba  test    rbx, rbx
0x1800029bd  jnz     short loc_1800029C7
0x1800029bf  mov     ecx, edi; dwErrCode
0x1800029c1  call    cs:__imp_SetLastError
0x1800029c7  mov     rax, rbx
0x1800029ca  mov     rbx, [rsp+38h+arg_0]
0x1800029cf  mov     rsi, [rsp+38h+arg_10]
0x1800029d4  add     rsp, 30h
0x1800029d8  pop     rdi
0x1800029d9  retn
0x18000d0f6  push    rbx
0x18000d0f8  push    rbp
0x18000d0f9  push    rdi
0x18000d0fa  sub     rsp, 20h
0x18000d0fe  mov     rbp, rdx
0x18000d101  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000d108  jnz     short loc_18000D13F
0x18000d10a  cmp     dword ptr [rbp+20h], 0
0x18000d10e  jz      short loc_18000D13F
0x18000d110  mov     rbx, [rbp+28h]
0x18000d114  test    rbx, rbx
0x18000d117  jnz     short loc_18000D123
0x18000d119  call    cs:__imp_GetLastError
0x18000d11f  mov     edi, eax
0x18000d121  jmp     short loc_18000D125
0x18000d123  xor     edi, edi
0x18000d125  mov     rdx, [rbp+48h]; ulCookie
0x18000d129  xor     ecx, ecx; dwFlags
0x18000d12b  call    cs:__imp_DeactivateActCtx
0x18000d131  test    rbx, rbx
0x18000d134  jnz     short loc_18000D13F
0x18000d136  mov     ecx, edi; dwErrCode
0x18000d138  call    cs:__imp_SetLastError
0x18000d13e  nop
0x18000d13f  add     rsp, 20h
0x18000d143  pop     rdi
0x18000d144  pop     rbp
0x18000d145  pop     rbx
0x18000d146  retn
```
