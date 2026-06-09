# DwmpBeginDisplayCapture

- ea: `0x180012550`
- end: `0x1800125c2`
- name: `DwmpBeginDisplayCapture`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x180012550`

## string_xrefs

- `0x180012598`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpBeginDisplayCapture(CApiPortClient *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-28h]
  int v5; // [rsp+30h] [rbp-18h] BYREF
  CApiPortClient *v6; // [rsp+34h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v5 = 1073741956;
  v6 = a1;
  v8 = 0;
  v1 = CApiPortClient::SendRequest(a1, &v5, 12, &v8, 0, 0);
  if ( v1 < 0 )
  {
    v2 = 328;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v1,
      v4);
    return (unsigned int)v1;
  }
  v1 = v8;
  if ( v8 < 0 )
  {
    v2 = 329;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180012550  mov     r11, rsp
0x180012553  push    rbx
0x180012554  sub     rsp, 40h
0x180012558  xor     eax, eax
0x18001255a  mov     [rsp+48h+var_18], 40000084h
0x180012562  mov     [rsp+48h+var_20], ax; __int16
0x180012567  lea     r9, [r11+8]; int *
0x18001256b  lea     rdx, [r11-18h]; void *
0x18001256f  mov     [r11-14h], rcx
0x180012573  mov     [rsp+48h+arg_0], 0
0x18001257b  lea     r8d, [rax+0Ch]; __int16
0x18001257f  mov     [r11-28h], rax
0x180012583  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180012588  mov     ebx, eax
0x18001258a  test    eax, eax
0x18001258c  jns     short loc_1800125AB
0x18001258e  mov     edx, 148h; void *
0x180012593  mov     rcx, [rsp+48h]; this
0x180012598  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x18001259f  mov     r9d, ebx; char *
0x1800125a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800125a7  mov     eax, ebx
0x1800125a9  jmp     short loc_1800125BC
0x1800125ab  mov     ebx, [rsp+48h+arg_0]
0x1800125af  test    ebx, ebx
0x1800125b1  jns     short loc_1800125BA
0x1800125b3  mov     edx, 149h
0x1800125b8  jmp     short loc_180012593
0x1800125ba  xor     eax, eax
0x1800125bc  add     rsp, 40h
0x1800125c0  pop     rbx
0x1800125c1  retn
```
