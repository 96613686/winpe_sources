# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x180007918`
- end: `0x1800079da`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800079e0`
- `0x180007aac`
- `0x180007b88`
- `0x180009b58`

## callees

- `0x180006a44`
- `0x180007918`
- `0x180007c60`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007981`
- `KERNEL32!GetProcAddress` at `0x180007981`
- `KERNEL32!SetLastError` at `0x1800079c1`
- `KERNEL32!SetLastError` at `0x18000ac85`
- `KERNEL32!SetLastError` at `0x1800079c1`
- `KERNEL32!SetLastError` at `0x18000ac85`
- `KERNEL32!DeactivateActCtx` at `0x1800079b4`
- `KERNEL32!DeactivateActCtx` at `0x18000ac78`
- `KERNEL32!DeactivateActCtx` at `0x1800079b4`
- `KERNEL32!DeactivateActCtx` at `0x18000ac78`
- `KERNEL32!GetLastError` at `0x1800079a1`
- `KERNEL32!GetLastError` at `0x18000ac66`
- `KERNEL32!GetLastError` at `0x1800079a1`
- `KERNEL32!GetLastError` at `0x18000ac66`

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
0x180007918  mov     rax, rsp
0x18000791b  mov     [rax+8], rbx
0x18000791f  mov     [rax+18h], rsi
0x180007923  push    rdi
0x180007924  sub     rsp, 30h
0x180007928  mov     rsi, rcx
0x18000792b  xor     ebx, ebx
0x18000792d  mov     [rax-10h], rbx
0x180007931  xor     edi, edi
0x180007933  mov     [rax-18h], edi
0x180007936  mov     [rax+10h], rbx
0x18000793a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180007940  jnz     short loc_180007955
0x180007942  lea     rcx, [rax+10h]; lpCookie
0x180007946  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000794b  mov     edi, eax
0x18000794d  mov     [rsp+38h+var_18], eax
0x180007951  test    eax, eax
0x180007953  jz      short loc_18000798F
0x180007955  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000795c  test    rax, rax
0x18000795f  jnz     short loc_18000797B
0x180007961  xor     ebx, ebx
0x180007963  mov     rcx, cs:lpLibFileName; lpLibFileName
0x18000796a  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x18000796f  test    rax, rax
0x180007972  jz      short loc_18000798A
0x180007974  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000797b  mov     rdx, rsi; lpProcName
0x18000797e  mov     rcx, rax; hModule
0x180007981  call    cs:__imp_GetProcAddress
0x180007987  mov     rbx, rax
0x18000798a  mov     [rsp+38h+var_10], rbx
0x18000798f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007996  jnz     short loc_1800079C7
0x180007998  test    edi, edi
0x18000799a  jz      short loc_1800079C7
0x18000799c  test    rbx, rbx
0x18000799f  jnz     short loc_1800079AB
0x1800079a1  call    cs:__imp_GetLastError
0x1800079a7  mov     edi, eax
0x1800079a9  jmp     short loc_1800079AD
0x1800079ab  xor     edi, edi
0x1800079ad  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800079b2  xor     ecx, ecx; dwFlags
0x1800079b4  call    cs:__imp_DeactivateActCtx
0x1800079ba  test    rbx, rbx
0x1800079bd  jnz     short loc_1800079C7
0x1800079bf  mov     ecx, edi; dwErrCode
0x1800079c1  call    cs:__imp_SetLastError
0x1800079c7  mov     rax, rbx
0x1800079ca  mov     rbx, [rsp+38h+arg_0]
0x1800079cf  mov     rsi, [rsp+38h+arg_10]
0x1800079d4  add     rsp, 30h
0x1800079d8  pop     rdi
0x1800079d9  retn
0x18000ac43  push    rbx
0x18000ac45  push    rbp
0x18000ac46  push    rdi
0x18000ac47  sub     rsp, 20h
0x18000ac4b  mov     rbp, rdx
0x18000ac4e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ac55  jnz     short loc_18000AC8C
0x18000ac57  cmp     dword ptr [rbp+20h], 0
0x18000ac5b  jz      short loc_18000AC8C
0x18000ac5d  mov     rbx, [rbp+28h]
0x18000ac61  test    rbx, rbx
0x18000ac64  jnz     short loc_18000AC70
0x18000ac66  call    cs:__imp_GetLastError
0x18000ac6c  mov     edi, eax
0x18000ac6e  jmp     short loc_18000AC72
0x18000ac70  xor     edi, edi
0x18000ac72  mov     rdx, [rbp+48h]; ulCookie
0x18000ac76  xor     ecx, ecx; dwFlags
0x18000ac78  call    cs:__imp_DeactivateActCtx
0x18000ac7e  test    rbx, rbx
0x18000ac81  jnz     short loc_18000AC8C
0x18000ac83  mov     ecx, edi; dwErrCode
0x18000ac85  call    cs:__imp_SetLastError
0x18000ac8b  nop
0x18000ac8c  add     rsp, 20h
0x18000ac90  pop     rdi
0x18000ac91  pop     rbp
0x18000ac92  pop     rbx
0x18000ac93  retn
```
