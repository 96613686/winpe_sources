# DevicesPage::GetBigFont(tagRECT const *)

- ea: `0x18000cc44`
- end: `0x18000ccba`
- name: `?GetBigFont@DevicesPage@@CAPEAUHFONT__@@PEBUtagRECT@@@Z`
- size: `118`
- prototype: `HFONT __fastcall(const struct tagRECT *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c770`
- `0x18000ca3c`

## callees

- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x18000cc9b`
- `GDI32!CreateFontIndirectW` at `0x18000cc9b`

## pseudocode

```c
HFONT __fastcall DevicesPage::GetBigFont(const struct tagRECT *a1)
{
  LOGFONTW lf; // [rsp+20h] [rbp-78h] BYREF

  memset_0(&lf, 0, sizeof(lf));
  lf.lfHeight = a1->bottom - a1->top;
  lf.lfWeight = 800;
  lf.lfWidth = 0;
  lf.lfPitchAndFamily = 32;
  lf.lfOutPrecision = 7;
  return CreateFontIndirectW(&lf);
}

```

## disassembly

```asm
0x18000cc44  push    rbx
0x18000cc46  sub     rsp, 90h
0x18000cc4d  mov     rax, cs:__security_cookie
0x18000cc54  xor     rax, rsp
0x18000cc57  mov     [rsp+98h+var_18], rax
0x18000cc5f  xor     edx, edx; Val
0x18000cc61  mov     rbx, rcx
0x18000cc64  lea     rcx, [rsp+98h+lf]; void *
0x18000cc69  lea     r8d, [rdx+5Ch]; Size
0x18000cc6d  call    memset_0
0x18000cc72  mov     eax, [rbx+0Ch]
0x18000cc75  lea     rcx, [rsp+98h+lf]; lplf
0x18000cc7a  sub     eax, [rbx+4]
0x18000cc7d  mov     [rsp+98h+lf.lfHeight], eax
0x18000cc81  mov     [rsp+98h+lf.lfWeight], 320h
0x18000cc89  mov     [rsp+98h+lf.lfWidth], 0
0x18000cc91  mov     [rsp+98h+lf.lfPitchAndFamily], 20h ; ' '
0x18000cc96  mov     [rsp+98h+lf.lfOutPrecision], 7
0x18000cc9b  call    cs:__imp_CreateFontIndirectW
0x18000cca1  mov     rcx, [rsp+98h+var_18]
0x18000cca9  xor     rcx, rsp; StackCookie
0x18000ccac  call    __security_check_cookie
0x18000ccb1  add     rsp, 90h
0x18000ccb8  pop     rbx
0x18000ccb9  retn
```
