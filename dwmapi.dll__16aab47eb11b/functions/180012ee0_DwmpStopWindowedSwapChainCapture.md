# DwmpStopWindowedSwapChainCapture

- ea: `0x180012ee0`
- end: `0x180012f52`
- name: `DwmpStopWindowedSwapChainCapture`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x180012ee0`

## string_xrefs

- `0x180012f28`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpStopWindowedSwapChainCapture(CApiPortClient *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-28h]
  int v5; // [rsp+30h] [rbp-18h] BYREF
  CApiPortClient *v6; // [rsp+34h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v5 = 1073741969;
  v6 = a1;
  v8 = 0;
  v1 = CApiPortClient::SendRequest(a1, &v5, 12, &v8, 0, 0);
  if ( v1 < 0 )
  {
    v2 = 688;
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
    v2 = 689;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180012ee0  mov     r11, rsp
0x180012ee3  push    rbx
0x180012ee4  sub     rsp, 40h
0x180012ee8  xor     eax, eax
0x180012eea  mov     [rsp+48h+var_18], 40000091h
0x180012ef2  mov     [rsp+48h+var_20], ax; __int16
0x180012ef7  lea     r9, [r11+8]; int *
0x180012efb  lea     rdx, [r11-18h]; void *
0x180012eff  mov     [r11-14h], rcx
0x180012f03  mov     [rsp+48h+arg_0], 0
0x180012f0b  lea     r8d, [rax+0Ch]; __int16
0x180012f0f  mov     [r11-28h], rax
0x180012f13  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180012f18  mov     ebx, eax
0x180012f1a  test    eax, eax
0x180012f1c  jns     short loc_180012F3B
0x180012f1e  mov     edx, 2B0h; void *
0x180012f23  mov     rcx, [rsp+48h]; this
0x180012f28  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012f2f  mov     r9d, ebx; char *
0x180012f32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f37  mov     eax, ebx
0x180012f39  jmp     short loc_180012F4C
0x180012f3b  mov     ebx, [rsp+48h+arg_0]
0x180012f3f  test    ebx, ebx
0x180012f41  jns     short loc_180012F4A
0x180012f43  mov     edx, 2B1h
0x180012f48  jmp     short loc_180012F23
0x180012f4a  xor     eax, eax
0x180012f4c  add     rsp, 40h
0x180012f50  pop     rbx
0x180012f51  retn
```
