# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x18002d7b8`
- end: `0x18002d876`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d920`

## callees

- `0x18002d7b8`
- `0x18002d87c`
- `0x18002d910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cf6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d862`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cf8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d862`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cf8b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d822`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d822`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002d855`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005cf7e`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18002d855`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005cf7e`

## string_xrefs

- `0x18002d818`: `TaskDialogIndirect`

## pseudocode

```c
FARPROC CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY()
{
  FARPROC ProcAddress; // rbx
  int v1; // edi
  HMODULE v2; // rax
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  ProcAddress = 0;
  v1 = 0;
  ulCookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || (v1 = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie)) != 0 )
  {
    v2 = `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m;
    if ( `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m )
    {
LABEL_6:
      ProcAddress = GetProcAddress(v2, "TaskDialogIndirect");
      goto LABEL_7;
    }
    ProcAddress = 0;
    v2 = IsolationAwarePrivatezlybNQyVOeNelJ(L"Comctl32.dll");
    if ( v2 )
    {
      `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m = v2;
      goto LABEL_6;
    }
  }
LABEL_7:
  if ( !IsolationAwarePrivateT_SqbjaYRiRY && v1 )
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
0x18002d7b8  mov     rax, rsp
0x18002d7bb  mov     [rax+10h], rbx
0x18002d7bf  mov     [rax+8], rcx
0x18002d7c3  push    rdi
0x18002d7c4  sub     rsp, 30h
0x18002d7c8  xor     ebx, ebx
0x18002d7ca  mov     [rax-10h], rbx
0x18002d7ce  xor     edi, edi
0x18002d7d0  mov     [rax-18h], edi
0x18002d7d3  mov     [rax+8], rbx
0x18002d7d7  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18002d7dd  jnz     short loc_18002D7F2
0x18002d7df  lea     rcx, [rax+8]; lpCookie
0x18002d7e3  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18002d7e8  mov     edi, eax
0x18002d7ea  mov     [rsp+38h+var_18], eax
0x18002d7ee  test    eax, eax
0x18002d7f0  jz      short loc_18002D830
0x18002d7f2  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18002d7f9  test    rax, rax
0x18002d7fc  jnz     short loc_18002D818
0x18002d7fe  xor     ebx, ebx
0x18002d800  mov     rcx, cs:lpLibFileName; lpLibFileName
0x18002d807  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x18002d80c  test    rax, rax
0x18002d80f  jz      short loc_18002D82B
0x18002d811  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18002d818  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x18002d81f  mov     rcx, rax; hModule
0x18002d822  call    cs:__imp_GetProcAddress
0x18002d828  mov     rbx, rax
0x18002d82b  mov     [rsp+38h+var_10], rbx
0x18002d830  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002d837  jnz     short loc_18002D868
0x18002d839  test    edi, edi
0x18002d83b  jz      short loc_18002D868
0x18002d83d  test    rbx, rbx
0x18002d840  jnz     short loc_18002D84C
0x18002d842  call    cs:__imp_GetLastError
0x18002d848  mov     edi, eax
0x18002d84a  jmp     short loc_18002D84E
0x18002d84c  xor     edi, edi
0x18002d84e  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18002d853  xor     ecx, ecx; dwFlags
0x18002d855  call    cs:__imp_DeactivateActCtx
0x18002d85b  test    rbx, rbx
0x18002d85e  jnz     short loc_18002D868
0x18002d860  mov     ecx, edi; dwErrCode
0x18002d862  call    cs:__imp_SetLastError
0x18002d868  mov     rax, rbx
0x18002d86b  mov     rbx, [rsp+38h+arg_8]
0x18002d870  add     rsp, 30h
0x18002d874  pop     rdi
0x18002d875  retn
0x18005cf49  push    rbx
0x18005cf4b  push    rbp
0x18005cf4c  push    rdi
0x18005cf4d  sub     rsp, 20h
0x18005cf51  mov     rbp, rdx
0x18005cf54  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18005cf5b  jnz     short loc_18005CF92
0x18005cf5d  cmp     dword ptr [rbp+20h], 0
0x18005cf61  jz      short loc_18005CF92
0x18005cf63  mov     rbx, [rbp+28h]
0x18005cf67  test    rbx, rbx
0x18005cf6a  jnz     short loc_18005CF76
0x18005cf6c  call    cs:__imp_GetLastError
0x18005cf72  mov     edi, eax
0x18005cf74  jmp     short loc_18005CF78
0x18005cf76  xor     edi, edi
0x18005cf78  mov     rdx, [rbp+40h]; ulCookie
0x18005cf7c  xor     ecx, ecx; dwFlags
0x18005cf7e  call    cs:__imp_DeactivateActCtx
0x18005cf84  test    rbx, rbx
0x18005cf87  jnz     short loc_18005CF92
0x18005cf89  mov     ecx, edi; dwErrCode
0x18005cf8b  call    cs:__imp_SetLastError
0x18005cf91  nop
0x18005cf92  add     rsp, 20h
0x18005cf96  pop     rdi
0x18005cf97  pop     rbp
0x18005cf98  pop     rbx
0x18005cf99  retn
```
