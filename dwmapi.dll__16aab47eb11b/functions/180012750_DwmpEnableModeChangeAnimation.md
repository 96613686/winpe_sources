# DwmpEnableModeChangeAnimation

- ea: `0x180012750`
- end: `0x1800127b3`
- name: `DwmpEnableModeChangeAnimation`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x180012750`

## string_xrefs

- `0x180012793`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpEnableModeChangeAnimation(CApiPortClient *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+4Ch] [rbp+14h]

  v7 = 1073741917;
  v6 = 0;
  v8 = (int)a1;
  v1 = CApiPortClient::SendRequest(a1, &v7, 8, &v6, 0, 0);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D2,
    (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180012750  mov     r11, rsp
0x180012753  push    rbx
0x180012754  sub     rsp, 30h
0x180012758  xor     eax, eax
0x18001275a  mov     qword ptr [r11+10h], 4000005Dh
0x180012762  mov     [rsp+38h+var_10], ax; __int16
0x180012767  lea     r9, [r11+8]; int *
0x18001276b  lea     rdx, [r11+10h]; void *
0x18001276f  mov     [rsp+38h+arg_0], 0
0x180012777  mov     [rsp+38h+arg_C], ecx
0x18001277b  lea     r8d, [rax+8]; __int16
0x18001277f  mov     [r11-18h], rax
0x180012783  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180012788  mov     ebx, eax
0x18001278a  test    eax, eax
0x18001278c  jns     short loc_1800127AB
0x18001278e  mov     rcx, [rsp+38h]; this
0x180012793  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x18001279a  mov     r9d, eax; char *
0x18001279d  mov     edx, 1D2h; void *
0x1800127a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800127a7  mov     eax, ebx
0x1800127a9  jmp     short loc_1800127AD
0x1800127ab  xor     eax, eax
0x1800127ad  add     rsp, 30h
0x1800127b1  pop     rbx
0x1800127b2  retn
```
