# DwmpUpdateFilteredDisplayCaptureBorder

- ea: `0x1800130c0`
- end: `0x180013136`
- name: `DwmpUpdateFilteredDisplayCaptureBorder`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x1800130c0`

## string_xrefs

- `0x18001310c`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpUpdateFilteredDisplayCaptureBorder(CApiPortClient *a1, int a2)
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
  v6 = 1073741966;
  v7 = a1;
  v10 = 0;
  v2 = CApiPortClient::SendRequest(a1, &v6, 16, &v10, 0, 0);
  if ( v2 < 0 )
  {
    v3 = 553;
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
    v3 = 554;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800130c0  mov     rax, rsp
0x1800130c3  push    rbx
0x1800130c4  sub     rsp, 40h
0x1800130c8  mov     [rax-0Ch], edx
0x1800130cb  lea     r9, [rsp+48h+arg_8]; int *
0x1800130d0  mov     dword ptr [rax-18h], 4000008Eh
0x1800130d7  lea     rdx, [rsp+48h+var_18]; void *
0x1800130dc  mov     [rax-14h], rcx
0x1800130e0  mov     dword ptr [rax+10h], 0
0x1800130e7  xor     eax, eax
0x1800130e9  mov     [rsp+48h+var_20], ax; __int16
0x1800130ee  mov     [rsp+48h+var_28], rax; int
0x1800130f3  lea     r8d, [rax+10h]; __int16
0x1800130f7  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x1800130fc  mov     ebx, eax
0x1800130fe  test    eax, eax
0x180013100  jns     short loc_18001311F
0x180013102  mov     edx, 229h; void *
0x180013107  mov     rcx, [rsp+48h]; this
0x18001310c  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180013113  mov     r9d, ebx; char *
0x180013116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001311b  mov     eax, ebx
0x18001311d  jmp     short loc_180013130
0x18001311f  mov     ebx, [rsp+48h+arg_8]
0x180013123  test    ebx, ebx
0x180013125  jns     short loc_18001312E
0x180013127  mov     edx, 22Ah
0x18001312c  jmp     short loc_180013107
0x18001312e  xor     eax, eax
0x180013130  add     rsp, 40h
0x180013134  pop     rbx
0x180013135  retn
```
