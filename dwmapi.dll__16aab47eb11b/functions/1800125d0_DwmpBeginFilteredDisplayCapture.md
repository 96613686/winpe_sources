# DwmpBeginFilteredDisplayCapture

- ea: `0x1800125d0`
- end: `0x180012642`
- name: `DwmpBeginFilteredDisplayCapture`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x1800125d0`

## string_xrefs

- `0x180012618`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpBeginFilteredDisplayCapture(CApiPortClient *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-28h]
  int v5; // [rsp+30h] [rbp-18h] BYREF
  CApiPortClient *v6; // [rsp+34h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v5 = 1073741963;
  v6 = a1;
  v8 = 0;
  v1 = CApiPortClient::SendRequest(a1, &v5, 12, &v8, 0, 0);
  if ( v1 < 0 )
  {
    v2 = 504;
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
    v2 = 505;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800125d0  mov     r11, rsp
0x1800125d3  push    rbx
0x1800125d4  sub     rsp, 40h
0x1800125d8  xor     eax, eax
0x1800125da  mov     [rsp+48h+var_18], 4000008Bh
0x1800125e2  mov     [rsp+48h+var_20], ax; __int16
0x1800125e7  lea     r9, [r11+8]; int *
0x1800125eb  lea     rdx, [r11-18h]; void *
0x1800125ef  mov     [r11-14h], rcx
0x1800125f3  mov     [rsp+48h+arg_0], 0
0x1800125fb  lea     r8d, [rax+0Ch]; __int16
0x1800125ff  mov     [r11-28h], rax
0x180012603  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180012608  mov     ebx, eax
0x18001260a  test    eax, eax
0x18001260c  jns     short loc_18001262B
0x18001260e  mov     edx, 1F8h; void *
0x180012613  mov     rcx, [rsp+48h]; this
0x180012618  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x18001261f  mov     r9d, ebx; char *
0x180012622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012627  mov     eax, ebx
0x180012629  jmp     short loc_18001263C
0x18001262b  mov     ebx, [rsp+48h+arg_0]
0x18001262f  test    ebx, ebx
0x180012631  jns     short loc_18001263A
0x180012633  mov     edx, 1F9h
0x180012638  jmp     short loc_180012613
0x18001263a  xor     eax, eax
0x18001263c  add     rsp, 40h
0x180012640  pop     rbx
0x180012641  retn
```
