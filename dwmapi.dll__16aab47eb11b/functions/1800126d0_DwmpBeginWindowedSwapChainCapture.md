# DwmpBeginWindowedSwapChainCapture

- ea: `0x1800126d0`
- end: `0x180012742`
- name: `DwmpBeginWindowedSwapChainCapture`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x1800126d0`

## string_xrefs

- `0x180012718`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpBeginWindowedSwapChainCapture(CApiPortClient *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-28h]
  int v5; // [rsp+30h] [rbp-18h] BYREF
  CApiPortClient *v6; // [rsp+34h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v5 = 1073741968;
  v6 = a1;
  v8 = 0;
  v1 = CApiPortClient::SendRequest(a1, &v5, 12, &v8, 0, 0);
  if ( v1 < 0 )
  {
    v2 = 675;
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
    v2 = 676;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800126d0  mov     r11, rsp
0x1800126d3  push    rbx
0x1800126d4  sub     rsp, 40h
0x1800126d8  xor     eax, eax
0x1800126da  mov     [rsp+48h+var_18], 40000090h
0x1800126e2  mov     [rsp+48h+var_20], ax; __int16
0x1800126e7  lea     r9, [r11+8]; int *
0x1800126eb  lea     rdx, [r11-18h]; void *
0x1800126ef  mov     [r11-14h], rcx
0x1800126f3  mov     [rsp+48h+arg_0], 0
0x1800126fb  lea     r8d, [rax+0Ch]; __int16
0x1800126ff  mov     [r11-28h], rax
0x180012703  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180012708  mov     ebx, eax
0x18001270a  test    eax, eax
0x18001270c  jns     short loc_18001272B
0x18001270e  mov     edx, 2A3h; void *
0x180012713  mov     rcx, [rsp+48h]; this
0x180012718  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x18001271f  mov     r9d, ebx; char *
0x180012722  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012727  mov     eax, ebx
0x180012729  jmp     short loc_18001273C
0x18001272b  mov     ebx, [rsp+48h+arg_0]
0x18001272f  test    ebx, ebx
0x180012731  jns     short loc_18001273A
0x180012733  mov     edx, 2A4h
0x180012738  jmp     short loc_180012713
0x18001273a  xor     eax, eax
0x18001273c  add     rsp, 40h
0x180012740  pop     rbx
0x180012741  retn
```
