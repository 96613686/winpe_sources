# CBaseDlg::CreateSecurityFont(void *,HDC__ *,int,int)

- ea: `0x180012f38`
- end: `0x180012fbe`
- name: `?CreateSecurityFont@CBaseDlg@@IEAAPEAUHFONT__@@PEAXPEAUHDC__@@HH@Z`
- size: `134`
- prototype: `HFONT __fastcall(CBaseDlg *this, void *, HDC)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800130d0`
- `0x180013574`
- `0x180016214`
- `0x1800163b4`

## callees

- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x180012f97`
- `GDI32!CreateFontIndirectW` at `0x180012f97`
- `UxTheme!GetThemeFont` at `0x180012f8c`
- `UxTheme!GetThemeFont` at `0x180012f8c`

## pseudocode

```c
HFONT __fastcall CBaseDlg::CreateSecurityFont(CBaseDlg *this, void *a2, HDC a3)
{
  LOGFONTW lf; // [rsp+30h] [rbp-78h] BYREF

  memset_0(&lf, 0, sizeof(lf));
  GetThemeFont(a2, a3, 2, 0, 210, &lf);
  return CreateFontIndirectW(&lf);
}

```

## disassembly

```asm
0x180012f38  mov     [rsp+arg_0], rbx
0x180012f3d  push    rdi
0x180012f3e  sub     rsp, 0A0h
0x180012f45  mov     rax, cs:__security_cookie
0x180012f4c  xor     rax, rsp
0x180012f4f  mov     [rsp+0A8h+var_18], rax
0x180012f57  mov     rbx, rdx
0x180012f5a  lea     rcx, [rsp+0A8h+lf]; void *
0x180012f5f  xor     edx, edx; Val
0x180012f61  mov     rdi, r8
0x180012f64  lea     r8d, [rdx+5Ch]; Size
0x180012f68  call    memset_0
0x180012f6d  xor     r9d, r9d; iStateId
0x180012f70  lea     rax, [rsp+0A8h+lf]
0x180012f75  mov     [rsp+0A8h+pFont], rax; pFont
0x180012f7a  mov     rdx, rdi; hdc
0x180012f7d  mov     rcx, rbx; hTheme
0x180012f80  mov     [rsp+0A8h+iPropId], 0D2h; iPropId
0x180012f88  lea     r8d, [r9+2]; iPartId
0x180012f8c  call    cs:__imp_GetThemeFont
0x180012f92  lea     rcx, [rsp+0A8h+lf]; lplf
0x180012f97  call    cs:__imp_CreateFontIndirectW
0x180012f9d  mov     rcx, [rsp+0A8h+var_18]
0x180012fa5  xor     rcx, rsp; StackCookie
0x180012fa8  call    __security_check_cookie
0x180012fad  mov     rbx, [rsp+0A8h+arg_0]
0x180012fb5  add     rsp, 0A0h
0x180012fbc  pop     rdi
0x180012fbd  retn
```
