# CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY

- ea: `0x180008d1c`
- end: `0x180008dc2`
- name: `CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY`
- size: `166`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008dc8`
- `0x180009050`
- `0x180021158`

## callees

- `0x180008d1c`
- `0x18000911c`
- `0x1800091a8`
- `0x180014868`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008d89`
- `KERNEL32!GetLastError` at `0x180008d89`
- `KERNEL32!SetLastError` at `0x180008da9`
- `KERNEL32!SetLastError` at `0x180008da9`
- `KERNEL32!DeactivateActCtx` at `0x180008d9c`
- `KERNEL32!DeactivateActCtx` at `0x180008d9c`

## pseudocode

```c
__int64 __fastcall CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY(__int64 a1)
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
           &`CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY'::`2'::c,
           &`CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY'::`2'::m,
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
0x180008d1c  mov     rax, rsp
0x180008d1f  mov     [rax+8], rbx
0x180008d23  mov     [rax+18h], rsi
0x180008d27  push    rdi
0x180008d28  sub     rsp, 30h
0x180008d2c  mov     rsi, rcx
0x180008d2f  xor     ebx, ebx
0x180008d31  mov     [rax-10h], rbx
0x180008d35  xor     edi, edi
0x180008d37  mov     [rax-18h], edi
0x180008d3a  mov     [rax+10h], rbx
0x180008d3e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180008d44  jnz     short loc_180008D59
0x180008d46  lea     rcx, [rax+10h]; lpCookie
0x180008d4a  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180008d4f  mov     edi, eax
0x180008d51  mov     [rsp+38h+var_18], eax
0x180008d55  test    eax, eax
0x180008d57  jz      short loc_180008D77
0x180008d59  mov     r8, rsi
0x180008d5c  lea     rdx, ?m@?1??CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY'::`2'::m
0x180008d63  lea     rcx, ?c@?1??CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY@@9@4UIsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB@@B; IsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB const `CommdlgIsolationAwarePrivatetRgCebPnQQeRff_pbZQYTQP_QYY'::`2'::c
0x180008d6a  call    IsolationAwarePrivatezltRgCebPnQQeRff
0x180008d6f  mov     rbx, rax
0x180008d72  mov     [rsp+38h+var_10], rax
0x180008d77  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180008d7e  jnz     short loc_180008DAF
0x180008d80  test    edi, edi
0x180008d82  jz      short loc_180008DAF
0x180008d84  test    rbx, rbx
0x180008d87  jnz     short loc_180008D93
0x180008d89  call    cs:__imp_GetLastError
0x180008d8f  mov     edi, eax
0x180008d91  jmp     short loc_180008D95
0x180008d93  xor     edi, edi
0x180008d95  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180008d9a  xor     ecx, ecx; dwFlags
0x180008d9c  call    cs:__imp_DeactivateActCtx
0x180008da2  test    rbx, rbx
0x180008da5  jnz     short loc_180008DAF
0x180008da7  mov     ecx, edi; dwErrCode
0x180008da9  call    cs:__imp_SetLastError
0x180008daf  mov     rax, rbx
0x180008db2  mov     rbx, [rsp+38h+arg_0]
0x180008db7  mov     rsi, [rsp+38h+arg_10]
0x180008dbc  add     rsp, 30h
0x180008dc0  pop     rdi
0x180008dc1  retn
0x18002290c  push    rbx
0x18002290e  push    rbp
0x18002290f  push    rdi
0x180022910  sub     rsp, 20h
0x180022914  mov     rbp, rdx
0x180022917  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002291e  jnz     short loc_180022955
0x180022920  cmp     dword ptr [rbp+20h], 0
0x180022924  jz      short loc_180022955
0x180022926  mov     rbx, [rbp+28h]
0x18002292a  test    rbx, rbx
0x18002292d  jnz     short loc_180022939
0x18002292f  call    cs:__imp_GetLastError
0x180022935  mov     edi, eax
0x180022937  jmp     short loc_18002293B
0x180022939  xor     edi, edi
0x18002293b  mov     rdx, [rbp+48h]; ulCookie
0x18002293f  xor     ecx, ecx; dwFlags
0x180022941  call    cs:__imp_DeactivateActCtx
0x180022947  test    rbx, rbx
0x18002294a  jnz     short loc_180022955
0x18002294c  mov     ecx, edi; dwErrCode
0x18002294e  call    cs:__imp_SetLastError
0x180022954  nop
0x180022955  add     rsp, 20h
0x180022959  pop     rdi
0x18002295a  pop     rbp
0x18002295b  pop     rbx
0x18002295c  retn
```
