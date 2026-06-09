# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x18000df94`
- end: `0x18000e056`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e05c`
- `0x18000e290`

## callees

- `0x18000df94`
- `0x18000e1e8`
- `0x18000e280`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18000e030`
- `KERNEL32!DeactivateActCtx` at `0x18002c65e`
- `KERNEL32!DeactivateActCtx` at `0x18000e030`
- `KERNEL32!DeactivateActCtx` at `0x18002c65e`
- `KERNEL32!SetLastError` at `0x18000e03d`
- `KERNEL32!SetLastError` at `0x18002c66b`
- `KERNEL32!SetLastError` at `0x18000e03d`
- `KERNEL32!SetLastError` at `0x18002c66b`
- `KERNEL32!GetProcAddress` at `0x18000dffd`
- `KERNEL32!GetProcAddress` at `0x18000dffd`
- `KERNEL32!GetLastError` at `0x18000e01d`
- `KERNEL32!GetLastError` at `0x18002c64c`
- `KERNEL32!GetLastError` at `0x18000e01d`
- `KERNEL32!GetLastError` at `0x18002c64c`

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
0x18000df94  mov     rax, rsp
0x18000df97  mov     [rax+8], rbx
0x18000df9b  mov     [rax+18h], rsi
0x18000df9f  push    rdi
0x18000dfa0  sub     rsp, 30h
0x18000dfa4  mov     rsi, rcx
0x18000dfa7  xor     ebx, ebx
0x18000dfa9  mov     [rax-10h], rbx
0x18000dfad  xor     edi, edi
0x18000dfaf  mov     [rax-18h], edi
0x18000dfb2  mov     [rax+10h], rbx
0x18000dfb6  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18000dfbc  jnz     short loc_18000DFD1
0x18000dfbe  lea     rcx, [rax+10h]; lpCookie
0x18000dfc2  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000dfc7  mov     edi, eax
0x18000dfc9  mov     [rsp+38h+var_18], eax
0x18000dfcd  test    eax, eax
0x18000dfcf  jz      short loc_18000E00B
0x18000dfd1  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000dfd8  test    rax, rax
0x18000dfdb  jnz     short loc_18000DFF7
0x18000dfdd  xor     ebx, ebx
0x18000dfdf  mov     rcx, cs:lpLibFileName; lpLibFileName
0x18000dfe6  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x18000dfeb  test    rax, rax
0x18000dfee  jz      short loc_18000E006
0x18000dff0  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18000dff7  mov     rdx, rsi; lpProcName
0x18000dffa  mov     rcx, rax; hModule
0x18000dffd  call    cs:__imp_GetProcAddress
0x18000e003  mov     rbx, rax
0x18000e006  mov     [rsp+38h+var_10], rbx
0x18000e00b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e012  jnz     short loc_18000E043
0x18000e014  test    edi, edi
0x18000e016  jz      short loc_18000E043
0x18000e018  test    rbx, rbx
0x18000e01b  jnz     short loc_18000E027
0x18000e01d  call    cs:__imp_GetLastError
0x18000e023  mov     edi, eax
0x18000e025  jmp     short loc_18000E029
0x18000e027  xor     edi, edi
0x18000e029  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000e02e  xor     ecx, ecx; dwFlags
0x18000e030  call    cs:__imp_DeactivateActCtx
0x18000e036  test    rbx, rbx
0x18000e039  jnz     short loc_18000E043
0x18000e03b  mov     ecx, edi; dwErrCode
0x18000e03d  call    cs:__imp_SetLastError
0x18000e043  mov     rax, rbx
0x18000e046  mov     rbx, [rsp+38h+arg_0]
0x18000e04b  mov     rsi, [rsp+38h+arg_10]
0x18000e050  add     rsp, 30h
0x18000e054  pop     rdi
0x18000e055  retn
0x18002c629  push    rbx
0x18002c62b  push    rbp
0x18002c62c  push    rdi
0x18002c62d  sub     rsp, 20h
0x18002c631  mov     rbp, rdx
0x18002c634  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002c63b  jnz     short loc_18002C672
0x18002c63d  cmp     dword ptr [rbp+20h], 0
0x18002c641  jz      short loc_18002C672
0x18002c643  mov     rbx, [rbp+28h]
0x18002c647  test    rbx, rbx
0x18002c64a  jnz     short loc_18002C656
0x18002c64c  call    cs:__imp_GetLastError
0x18002c652  mov     edi, eax
0x18002c654  jmp     short loc_18002C658
0x18002c656  xor     edi, edi
0x18002c658  mov     rdx, [rbp+48h]; ulCookie
0x18002c65c  xor     ecx, ecx; dwFlags
0x18002c65e  call    cs:__imp_DeactivateActCtx
0x18002c664  test    rbx, rbx
0x18002c667  jnz     short loc_18002C672
0x18002c669  mov     ecx, edi; dwErrCode
0x18002c66b  call    cs:__imp_SetLastError
0x18002c671  nop
0x18002c672  add     rsp, 20h
0x18002c676  pop     rdi
0x18002c677  pop     rbp
0x18002c678  pop     rbx
0x18002c679  retn
```
