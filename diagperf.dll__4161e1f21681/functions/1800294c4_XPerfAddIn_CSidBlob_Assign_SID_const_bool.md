# XPerfAddIn::CSidBlob::_Assign(_SID const *,bool)

- ea: `0x1800294c4`
- end: `0x180029544`
- name: `?_Assign@CSidBlob@XPerfAddIn@@AEAAXPEBU_SID@@_N@Z`
- size: `128`
- prototype: `void(XPerfAddIn::CSidBlob *__hidden this, const struct _SID *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c2f8`

## callees

- `0x1800294c4`
- `0x180039bbc`

## import_xrefs

- `msvcrt!malloc` at `0x1800294eb`
- `msvcrt!malloc` at `0x1800294eb`
- `msvcrt!free` at `0x180029519`
- `msvcrt!free` at `0x180029519`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800294e1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800294e1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002950c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002950c`

## pseudocode

```c
void __fastcall XPerfAddIn::CSidBlob::_Assign(void **this, struct _SID *a2, char a3)
{
  DWORD LengthSid; // esi
  void *v6; // rax

  if ( a3 )
  {
    LengthSid = GetLengthSid(a2);
    v6 = malloc(LengthSid);
    *this = v6;
    if ( !v6 )
      ATL::AtlThrowImpl(-2147024882);
    if ( !CopySid(LengthSid, v6, a2) )
    {
      free(*this);
      *this = 0;
      ATL::AtlThrowImpl(-2147024882);
    }
  }
  else
  {
    *this = a2;
  }
}

```

## disassembly

```asm
0x1800294c4  mov     [rsp+arg_0], rbx
0x1800294c9  mov     [rsp+arg_8], rsi
0x1800294ce  push    rdi
0x1800294cf  sub     rsp, 20h
0x1800294d3  mov     rdi, rdx
0x1800294d6  mov     rbx, rcx
0x1800294d9  test    r8b, r8b
0x1800294dc  jz      short loc_180029531
0x1800294de  mov     rcx, rdx; pSid
0x1800294e1  call    cs:__imp_GetLengthSid
0x1800294e7  mov     ecx, eax; Size
0x1800294e9  mov     esi, eax
0x1800294eb  call    cs:__imp_malloc
0x1800294f1  mov     [rbx], rax
0x1800294f4  test    rax, rax
0x1800294f7  jnz     short loc_180029504
0x1800294f9  mov     ecx, 8007000Eh; int
0x1800294fe  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180029504  mov     r8, rdi; pSourceSid
0x180029507  mov     rdx, rax; pDestinationSid
0x18002950a  mov     ecx, esi; nDestinationSidLength
0x18002950c  call    cs:__imp_CopySid
0x180029512  test    eax, eax
0x180029514  jnz     short loc_180029534
0x180029516  mov     rcx, [rbx]; Block
0x180029519  call    cs:__imp_free
0x18002951f  mov     ecx, 8007000Eh; int
0x180029524  mov     qword ptr [rbx], 0
0x18002952b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180029531  mov     [rcx], rdi
0x180029534  mov     rbx, [rsp+28h+arg_0]
0x180029539  mov     rsi, [rsp+28h+arg_8]
0x18002953e  add     rsp, 20h
0x180029542  pop     rdi
0x180029543  retn
```
