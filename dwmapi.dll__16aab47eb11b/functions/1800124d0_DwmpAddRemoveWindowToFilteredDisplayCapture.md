# DwmpAddRemoveWindowToFilteredDisplayCapture

- ea: `0x1800124d0`
- end: `0x18001254a`
- name: `DwmpAddRemoveWindowToFilteredDisplayCapture`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000925c`
- `0x1800124d0`

## string_xrefs

- `0x180012520`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpAddRemoveWindowToFilteredDisplayCapture(CApiPortClient *a1, int a2, __int64 a3)
{
  int v3; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-38h]
  int v7; // [rsp+30h] [rbp-28h] BYREF
  CApiPortClient *v8; // [rsp+34h] [rbp-24h]
  int v9; // [rsp+3Ch] [rbp-1Ch]
  __int64 v10; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v12; // [rsp+68h] [rbp+10h] BYREF

  v9 = a2;
  v10 = a3;
  v7 = 1073741965;
  v8 = a1;
  v12 = 0;
  v3 = CApiPortClient::SendRequest(a1, &v7, 24, &v12, 0, 0);
  if ( v3 < 0 )
  {
    v4 = 523;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v3,
      v6);
    return (unsigned int)v3;
  }
  v3 = v12;
  if ( v12 < 0 )
  {
    v4 = 524;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800124d0  mov     rax, rsp
0x1800124d3  push    rbx
0x1800124d4  sub     rsp, 50h
0x1800124d8  mov     [rax-1Ch], edx
0x1800124db  lea     r9, [rsp+58h+arg_8]; int *
0x1800124e0  mov     [rax-18h], r8
0x1800124e4  lea     rdx, [rsp+58h+var_28]; void *
0x1800124e9  mov     dword ptr [rax-28h], 4000008Dh
0x1800124f0  mov     [rax-24h], rcx
0x1800124f4  mov     dword ptr [rax+10h], 0
0x1800124fb  xor     eax, eax
0x1800124fd  mov     [rsp+58h+var_30], ax; __int16
0x180012502  mov     [rsp+58h+var_38], rax; int
0x180012507  lea     r8d, [rax+18h]; __int16
0x18001250b  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x180012510  mov     ebx, eax
0x180012512  test    eax, eax
0x180012514  jns     short loc_180012533
0x180012516  mov     edx, 20Bh; void *
0x18001251b  mov     rcx, [rsp+58h]; this
0x180012520  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012527  mov     r9d, ebx; char *
0x18001252a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001252f  mov     eax, ebx
0x180012531  jmp     short loc_180012544
0x180012533  mov     ebx, [rsp+58h+arg_8]
0x180012537  test    ebx, ebx
0x180012539  jns     short loc_180012542
0x18001253b  mov     edx, 20Ch
0x180012540  jmp     short loc_18001251B
0x180012542  xor     eax, eax
0x180012544  add     rsp, 50h
0x180012548  pop     rbx
0x180012549  retn
```
