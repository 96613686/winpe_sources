# DwmpUpdateWindowedSwapChainCaptureBorder

- ea: `0x1800131c0`
- end: `0x180013236`
- name: `DwmpUpdateWindowedSwapChainCaptureBorder`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x1800131c0`

## string_xrefs

- `0x18001320c`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpUpdateWindowedSwapChainCaptureBorder(CApiPortClient *a1, int a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-28h]
  int v6; // [rsp+30h] [rbp-18h] BYREF
  CApiPortClient *v7; // [rsp+34h] [rbp-14h]
  int v8; // [rsp+3Ch] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v10; // [rsp+58h] [rbp+10h] BYREF

  v8 = a2;
  v6 = 1073741970;
  v7 = a1;
  v10 = 0;
  v2 = CApiPortClient::SendRequest(a1, &v6, 16, &v10, 0, 0);
  if ( v2 < 0 )
  {
    v3 = 705;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v2,
      v5);
    return (unsigned int)v2;
  }
  v2 = v10;
  if ( v10 < 0 )
  {
    v3 = 706;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800131c0  mov     rax, rsp
0x1800131c3  push    rbx
0x1800131c4  sub     rsp, 40h
0x1800131c8  mov     [rax-0Ch], edx
0x1800131cb  lea     r9, [rsp+48h+arg_8]; int *
0x1800131d0  mov     dword ptr [rax-18h], 40000092h
0x1800131d7  lea     rdx, [rsp+48h+var_18]; void *
0x1800131dc  mov     [rax-14h], rcx
0x1800131e0  mov     dword ptr [rax+10h], 0
0x1800131e7  xor     eax, eax
0x1800131e9  mov     [rsp+48h+var_20], ax; __int16
0x1800131ee  mov     [rsp+48h+var_28], rax; int
0x1800131f3  lea     r8d, [rax+10h]; __int16
0x1800131f7  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x1800131fc  mov     ebx, eax
0x1800131fe  test    eax, eax
0x180013200  jns     short loc_18001321F
0x180013202  mov     edx, 2C1h; void *
0x180013207  mov     rcx, [rsp+48h]; this
0x18001320c  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180013213  mov     r9d, ebx; char *
0x180013216  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001321b  mov     eax, ebx
0x18001321d  jmp     short loc_180013230
0x18001321f  mov     ebx, [rsp+48h+arg_8]
0x180013223  test    ebx, ebx
0x180013225  jns     short loc_18001322E
0x180013227  mov     edx, 2C2h
0x18001322c  jmp     short loc_180013207
0x18001322e  xor     eax, eax
0x180013230  add     rsp, 40h
0x180013234  pop     rbx
0x180013235  retn
```
