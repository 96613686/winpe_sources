# DwmpStopFilteredDisplayCapture

- ea: `0x180012de0`
- end: `0x180012e52`
- name: `DwmpStopFilteredDisplayCapture`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x180012de0`

## string_xrefs

- `0x180012e28`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpStopFilteredDisplayCapture(CApiPortClient *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-28h]
  int v5; // [rsp+30h] [rbp-18h] BYREF
  CApiPortClient *v6; // [rsp+34h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v5 = 1073741964;
  v6 = a1;
  v8 = 0;
  v1 = CApiPortClient::SendRequest(a1, &v5, 12, &v8, 0, 0);
  if ( v1 < 0 )
  {
    v2 = 536;
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
    v2 = 537;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180012de0  mov     r11, rsp
0x180012de3  push    rbx
0x180012de4  sub     rsp, 40h
0x180012de8  xor     eax, eax
0x180012dea  mov     [rsp+48h+var_18], 4000008Ch
0x180012df2  mov     [rsp+48h+var_20], ax; __int16
0x180012df7  lea     r9, [r11+8]; int *
0x180012dfb  lea     rdx, [r11-18h]; void *
0x180012dff  mov     [r11-14h], rcx
0x180012e03  mov     [rsp+48h+arg_0], 0
0x180012e0b  lea     r8d, [rax+0Ch]; __int16
0x180012e0f  mov     [r11-28h], rax
0x180012e13  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180012e18  mov     ebx, eax
0x180012e1a  test    eax, eax
0x180012e1c  jns     short loc_180012E3B
0x180012e1e  mov     edx, 218h; void *
0x180012e23  mov     rcx, [rsp+48h]; this
0x180012e28  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012e2f  mov     r9d, ebx; char *
0x180012e32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e37  mov     eax, ebx
0x180012e39  jmp     short loc_180012E4C
0x180012e3b  mov     ebx, [rsp+48h+arg_0]
0x180012e3f  test    ebx, ebx
0x180012e41  jns     short loc_180012E4A
0x180012e43  mov     edx, 219h
0x180012e48  jmp     short loc_180012E23
0x180012e4a  xor     eax, eax
0x180012e4c  add     rsp, 40h
0x180012e50  pop     rbx
0x180012e51  retn
```
