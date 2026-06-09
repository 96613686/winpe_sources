# IsolationAwareInitCommonControls

- ea: `0x180007af0`
- end: `0x180007b74`
- name: `IsolationAwareInitCommonControls`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006e80`

## callees

- `0x180005160`
- `0x1800075d0`
- `0x180007af0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007b68`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ece7`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007b68`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18003ece7`

## string_xrefs

- `0x180007b2b`: `InitCommonControls`

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
0x180007af0  push    rbx
0x180007af2  sub     rsp, 20h
0x180007af6  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControls@@9@4P6AXXZEA; void (*`IsolationAwareInitCommonControls'::`2'::s_pfn)(void)
0x180007afd  mov     [rsp+28h+ulCookie], 0
0x180007b06  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007b0d  jnz     short loc_180007B26
0x180007b0f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007b16  jnz     short loc_180007B26
0x180007b18  lea     rcx, [rsp+28h+ulCookie]; lpCookie
0x180007b1d  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180007b22  test    eax, eax
0x180007b24  jz      short loc_180007B6E
0x180007b26  test    rbx, rbx
0x180007b29  jnz     short loc_180007B46
0x180007b2b  lea     rcx, aInitcommoncont; "InitCommonControls"
0x180007b32  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180007b37  mov     rbx, rax
0x180007b3a  test    rax, rax
0x180007b3d  jz      short loc_180007B4F
0x180007b3f  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControls@@9@4P6AXXZEA, rax; void (*`IsolationAwareInitCommonControls'::`2'::s_pfn)(void)
0x180007b46  mov     rax, rbx
0x180007b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b4e  nop
0x180007b4f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007b56  jz      short loc_180007B61
0x180007b58  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007b5f  jnz     short loc_180007B6E
0x180007b61  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180007b66  xor     ecx, ecx; dwFlags
0x180007b68  call    cs:__imp_DeactivateActCtx
0x180007b6e  add     rsp, 20h
0x180007b72  pop     rbx
0x180007b73  retn
0x18003ecc6  push    rbp
0x18003ecc8  sub     rsp, 20h
0x18003eccc  mov     rbp, rdx
0x18003eccf  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003ecd6  jz      short loc_18003ECE1
0x18003ecd8  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003ecdf  jnz     short loc_18003ECEE
0x18003ece1  mov     rdx, [rbp+30h]; ulCookie
0x18003ece5  xor     ecx, ecx; dwFlags
0x18003ece7  call    cs:__imp_DeactivateActCtx
0x18003eced  nop
0x18003ecee  add     rsp, 20h
0x18003ecf2  pop     rbp
0x18003ecf3  retn
```
