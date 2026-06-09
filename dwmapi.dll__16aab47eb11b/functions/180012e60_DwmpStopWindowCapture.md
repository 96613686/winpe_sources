# DwmpStopWindowCapture

- ea: `0x180012e60`
- end: `0x180012ed2`
- name: `DwmpStopWindowCapture`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x180012e60`

## string_xrefs

- `0x180012ea8`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpStopWindowCapture(CApiPortClient *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-28h]
  int v5; // [rsp+30h] [rbp-18h] BYREF
  CApiPortClient *v6; // [rsp+34h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v5 = 1073741957;
  v6 = a1;
  v8 = 0;
  v1 = CApiPortClient::SendRequest(a1, &v5, 12, &v8, 0, 0);
  if ( v1 < 0 )
  {
    v2 = 348;
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
    v2 = 349;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180012e60  mov     r11, rsp
0x180012e63  push    rbx
0x180012e64  sub     rsp, 40h
0x180012e68  xor     eax, eax
0x180012e6a  mov     [rsp+48h+var_18], 40000085h
0x180012e72  mov     [rsp+48h+var_20], ax; __int16
0x180012e77  lea     r9, [r11+8]; int *
0x180012e7b  lea     rdx, [r11-18h]; void *
0x180012e7f  mov     [r11-14h], rcx
0x180012e83  mov     [rsp+48h+arg_0], 0
0x180012e8b  lea     r8d, [rax+0Ch]; __int16
0x180012e8f  mov     [r11-28h], rax
0x180012e93  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180012e98  mov     ebx, eax
0x180012e9a  test    eax, eax
0x180012e9c  jns     short loc_180012EBB
0x180012e9e  mov     edx, 15Ch; void *
0x180012ea3  mov     rcx, [rsp+48h]; this
0x180012ea8  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012eaf  mov     r9d, ebx; char *
0x180012eb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012eb7  mov     eax, ebx
0x180012eb9  jmp     short loc_180012ECC
0x180012ebb  mov     ebx, [rsp+48h+arg_0]
0x180012ebf  test    ebx, ebx
0x180012ec1  jns     short loc_180012ECA
0x180012ec3  mov     edx, 15Dh
0x180012ec8  jmp     short loc_180012EA3
0x180012eca  xor     eax, eax
0x180012ecc  add     rsp, 40h
0x180012ed0  pop     rbx
0x180012ed1  retn
```
