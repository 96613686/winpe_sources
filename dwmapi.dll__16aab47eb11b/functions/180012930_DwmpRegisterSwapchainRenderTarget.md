# DwmpRegisterSwapchainRenderTarget

- ea: `0x180012930`
- end: `0x1800129a3`
- name: `DwmpRegisterSwapchainRenderTarget`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000b92c`
- `0x180012930`

## string_xrefs

- `0x180012979`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpRegisterSwapchainRenderTarget(CApiPortClient *a1, __int64 a2, __int64 a3, int a4)
{
  int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-28h] BYREF
  CApiPortClient *v8; // [rsp+24h] [rbp-24h]
  __int64 v9; // [rsp+2Ch] [rbp-1Ch]
  int v10; // [rsp+34h] [rbp-14h]
  __int64 v11; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v13; // [rsp+68h] [rbp+20h] BYREF

  v9 = a2;
  v10 = a4;
  v11 = a3;
  v7 = 1073741900;
  v8 = a1;
  v13 = 0;
  v4 = CApiPortClient::SendRequestValidate(a1, &v7, 0x20u, &v13);
  if ( v4 < 0 )
  {
    v5 = 158;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v4,
      v7);
    return (unsigned int)v4;
  }
  v4 = v13;
  if ( v13 < 0 )
  {
    v5 = 159;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180012930  mov     rax, rsp
0x180012933  push    rbx
0x180012934  sub     rsp, 40h
0x180012938  mov     [rax-1Ch], rdx
0x18001293c  lea     rdx, [rax-28h]; void *
0x180012940  mov     [rax-14h], r9d
0x180012944  lea     r9, [rax+20h]; int *
0x180012948  mov     [rax-10h], r8
0x18001294c  mov     r8d, 20h ; ' '; unsigned __int64
0x180012952  mov     dword ptr [rax-28h], 4000004Ch
0x180012959  mov     [rax-24h], rcx
0x18001295d  mov     dword ptr [rax+20h], 0
0x180012964  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KPEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,long *)
0x180012969  mov     ebx, eax
0x18001296b  test    eax, eax
0x18001296d  jns     short loc_18001298C
0x18001296f  mov     edx, 9Eh; void *
0x180012974  mov     rcx, [rsp+48h]; this
0x180012979  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012980  mov     r9d, ebx; char *
0x180012983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012988  mov     eax, ebx
0x18001298a  jmp     short loc_18001299D
0x18001298c  mov     ebx, [rsp+48h+arg_18]
0x180012990  test    ebx, ebx
0x180012992  jns     short loc_18001299B
0x180012994  mov     edx, 9Fh
0x180012999  jmp     short loc_180012974
0x18001299b  xor     eax, eax
0x18001299d  add     rsp, 40h
0x1800129a1  pop     rbx
0x1800129a2  retn
```
