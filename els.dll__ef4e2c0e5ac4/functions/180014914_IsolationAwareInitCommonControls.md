# IsolationAwareInitCommonControls

- ea: `0x180014914`
- end: `0x180014998`
- name: `IsolationAwareInitCommonControls`
- size: `132`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001435c`

## callees

- `0x18000911c`
- `0x180014868`
- `0x180014914`
- `0x180024010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18001498c`
- `KERNEL32!DeactivateActCtx` at `0x180023163`
- `KERNEL32!DeactivateActCtx` at `0x18001498c`
- `KERNEL32!DeactivateActCtx` at `0x180023163`

## string_xrefs

- `0x18001494f`: `InitCommonControls`

## pseudocode

```c
int IsolationAwareInitCommonControls()
{
  __int64 (*v0)(void); // rbx
  __int64 v1; // rax
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  v0 = (__int64 (*)(void))`IsolationAwareInitCommonControls'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    LODWORD(v1) = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)v1 )
      return v1;
  }
  if ( v0 )
    goto LABEL_7;
  v1 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("InitCommonControls");
  v0 = (__int64 (*)(void))v1;
  if ( v1 )
  {
    `IsolationAwareInitCommonControls'::`2'::s_pfn = v1;
LABEL_7:
    LODWORD(v1) = v0();
  }
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    LODWORD(v1) = DeactivateActCtx(0, ulCookie);
  return v1;
}

```

## disassembly

```asm
0x180014914  push    rbx
0x180014916  sub     rsp, 20h
0x18001491a  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControls@@9@4P6AXXZEA; void (*`IsolationAwareInitCommonControls'::`2'::s_pfn)(void)
0x180014921  mov     [rsp+28h+ulCookie], 0
0x18001492a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180014931  jnz     short loc_18001494A
0x180014933  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001493a  jnz     short loc_18001494A
0x18001493c  lea     rcx, [rsp+28h+ulCookie]; lpCookie
0x180014941  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180014946  test    eax, eax
0x180014948  jz      short loc_180014992
0x18001494a  test    rbx, rbx
0x18001494d  jnz     short loc_18001496A
0x18001494f  lea     rcx, aInitcommoncont; "InitCommonControls"
0x180014956  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18001495b  mov     rbx, rax
0x18001495e  test    rax, rax
0x180014961  jz      short loc_180014973
0x180014963  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControls@@9@4P6AXXZEA, rax; void (*`IsolationAwareInitCommonControls'::`2'::s_pfn)(void)
0x18001496a  mov     rax, rbx
0x18001496d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014972  nop
0x180014973  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001497a  jz      short loc_180014985
0x18001497c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180014983  jnz     short loc_180014992
0x180014985  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18001498a  xor     ecx, ecx; dwFlags
0x18001498c  call    cs:__imp_DeactivateActCtx
0x180014992  add     rsp, 20h
0x180014996  pop     rbx
0x180014997  retn
0x180023142  push    rbp
0x180023144  sub     rsp, 20h
0x180023148  mov     rbp, rdx
0x18002314b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180023152  jz      short loc_18002315D
0x180023154  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002315b  jnz     short loc_18002316A
0x18002315d  mov     rdx, [rbp+30h]; ulCookie
0x180023161  xor     ecx, ecx; dwFlags
0x180023163  call    cs:__imp_DeactivateActCtx
0x180023169  nop
0x18002316a  add     rsp, 20h
0x18002316e  pop     rbp
0x18002316f  retn
```
