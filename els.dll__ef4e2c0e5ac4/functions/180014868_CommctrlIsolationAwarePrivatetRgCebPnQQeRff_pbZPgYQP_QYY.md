# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x180014868`
- end: `0x18001490e`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014914`
- `0x1800149a0`

## callees

- `0x18000911c`
- `0x1800091a8`
- `0x180014868`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800148d5`
- `KERNEL32!GetLastError` at `0x18002292f`
- `KERNEL32!GetLastError` at `0x1800148d5`
- `KERNEL32!GetLastError` at `0x18002292f`
- `KERNEL32!SetLastError` at `0x1800148f5`
- `KERNEL32!SetLastError` at `0x18002294e`
- `KERNEL32!SetLastError` at `0x1800148f5`
- `KERNEL32!SetLastError` at `0x18002294e`
- `KERNEL32!DeactivateActCtx` at `0x1800148e8`
- `KERNEL32!DeactivateActCtx` at `0x180022941`
- `KERNEL32!DeactivateActCtx` at `0x1800148e8`
- `KERNEL32!DeactivateActCtx` at `0x180022941`

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
0x180014868  mov     rax, rsp
0x18001486b  mov     [rax+8], rbx
0x18001486f  mov     [rax+18h], rsi
0x180014873  push    rdi
0x180014874  sub     rsp, 30h
0x180014878  mov     rsi, rcx
0x18001487b  xor     ebx, ebx
0x18001487d  mov     [rax-10h], rbx
0x180014881  xor     edi, edi
0x180014883  mov     [rax-18h], edi
0x180014886  mov     [rax+10h], rbx
0x18001488a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180014890  jnz     short loc_1800148A5
0x180014892  lea     rcx, [rax+10h]; lpCookie
0x180014896  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001489b  mov     edi, eax
0x18001489d  mov     [rsp+38h+var_18], eax
0x1800148a1  test    eax, eax
0x1800148a3  jz      short loc_1800148C3
0x1800148a5  mov     r8, rsi
0x1800148a8  lea     rdx, ?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x1800148af  lea     rcx, ?c@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB@@B; IsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB const `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::c
0x1800148b6  call    IsolationAwarePrivatezltRgCebPnQQeRff
0x1800148bb  mov     rbx, rax
0x1800148be  mov     [rsp+38h+var_10], rax
0x1800148c3  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800148ca  jnz     short loc_1800148FB
0x1800148cc  test    edi, edi
0x1800148ce  jz      short loc_1800148FB
0x1800148d0  test    rbx, rbx
0x1800148d3  jnz     short loc_1800148DF
0x1800148d5  call    cs:__imp_GetLastError
0x1800148db  mov     edi, eax
0x1800148dd  jmp     short loc_1800148E1
0x1800148df  xor     edi, edi
0x1800148e1  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800148e6  xor     ecx, ecx; dwFlags
0x1800148e8  call    cs:__imp_DeactivateActCtx
0x1800148ee  test    rbx, rbx
0x1800148f1  jnz     short loc_1800148FB
0x1800148f3  mov     ecx, edi; dwErrCode
0x1800148f5  call    cs:__imp_SetLastError
0x1800148fb  mov     rax, rbx
0x1800148fe  mov     rbx, [rsp+38h+arg_0]
0x180014903  mov     rsi, [rsp+38h+arg_10]
0x180014908  add     rsp, 30h
0x18001490c  pop     rdi
0x18001490d  retn
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
