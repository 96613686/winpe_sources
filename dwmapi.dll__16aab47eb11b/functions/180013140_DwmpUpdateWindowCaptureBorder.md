# DwmpUpdateWindowCaptureBorder

- ea: `0x180013140`
- end: `0x1800131b6`
- name: `DwmpUpdateWindowCaptureBorder`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x180013140`

## string_xrefs

- `0x18001318c`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpUpdateWindowCaptureBorder(CApiPortClient *a1, int a2)
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
  v6 = 1073741960;
  v7 = a1;
  v10 = 0;
  v2 = CApiPortClient::SendRequest(a1, &v6, 16, &v10, 0, 0);
  if ( v2 < 0 )
  {
    v3 = 395;
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
    v3 = 396;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180013140  mov     rax, rsp
0x180013143  push    rbx
0x180013144  sub     rsp, 40h
0x180013148  mov     [rax-0Ch], edx
0x18001314b  lea     r9, [rsp+48h+arg_8]; int *
0x180013150  mov     dword ptr [rax-18h], 40000088h
0x180013157  lea     rdx, [rsp+48h+var_18]; void *
0x18001315c  mov     [rax-14h], rcx
0x180013160  mov     dword ptr [rax+10h], 0
0x180013167  xor     eax, eax
0x180013169  mov     [rsp+48h+var_20], ax; __int16
0x18001316e  mov     [rsp+48h+var_28], rax; int
0x180013173  lea     r8d, [rax+10h]; __int16
0x180013177  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x18001317c  mov     ebx, eax
0x18001317e  test    eax, eax
0x180013180  jns     short loc_18001319F
0x180013182  mov     edx, 18Bh; void *
0x180013187  mov     rcx, [rsp+48h]; this
0x18001318c  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180013193  mov     r9d, ebx; char *
0x180013196  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001319b  mov     eax, ebx
0x18001319d  jmp     short loc_1800131B0
0x18001319f  mov     ebx, [rsp+48h+arg_8]
0x1800131a3  test    ebx, ebx
0x1800131a5  jns     short loc_1800131AE
0x1800131a7  mov     edx, 18Ch
0x1800131ac  jmp     short loc_180013187
0x1800131ae  xor     eax, eax
0x1800131b0  add     rsp, 40h
0x1800131b4  pop     rbx
0x1800131b5  retn
```
