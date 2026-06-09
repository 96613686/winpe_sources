# DwmpSetupWindowedSwapChainCapture

- ea: `0x180012d30`
- end: `0x180012dd2`
- name: `DwmpSetupWindowedSwapChainCapture`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000a72c`
- `0x18000b92c`
- `0x180012d30`

## string_xrefs

- `0x180012da1`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpSetupWindowedSwapChainCapture(__int64 a1, __int64 a2, union _LARGE_INTEGER *a3)
{
  union _LARGE_INTEGER CaptureToken; // rbx
  CApiPortClient *v5; // rcx
  int v6; // edi
  __int64 v7; // rdx
  int v9[5]; // [rsp+20h] [rbp-48h] BYREF
  union _LARGE_INTEGER v10; // [rsp+34h] [rbp-34h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v12; // [rsp+70h] [rbp+8h] BYREF

  a3->QuadPart = 0;
  v9[0] = 1073741967;
  *(_QWORD *)&v9[1] = a1;
  *(_QWORD *)&v9[3] = a2;
  CaptureToken = MakeCaptureToken();
  v10 = CaptureToken;
  v12 = 0;
  v6 = CApiPortClient::SendRequestValidate(v5, v9, 0x1Cu, &v12);
  if ( v6 < 0 )
  {
    v7 = 659;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v6,
      v9[0]);
    return (unsigned int)v6;
  }
  v6 = v12;
  if ( v12 < 0 )
  {
    v7 = 660;
    goto LABEL_3;
  }
  *a3 = CaptureToken;
  return 0;
}

```

## disassembly

```asm
0x180012d30  push    rbx
0x180012d32  push    rsi
0x180012d33  push    rdi
0x180012d34  push    r14
0x180012d36  sub     rsp, 48h
0x180012d3a  xorps   xmm0, xmm0
0x180012d3d  xor     eax, eax
0x180012d3f  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180012d44  mov     r14, r8
0x180012d47  mov     rsi, rdx
0x180012d4a  movups  xmmword ptr [rsp+68h+var_48+0Ch], xmm0
0x180012d4f  mov     rdi, rcx
0x180012d52  mov     [r8], rax
0x180012d55  call    ?MakeCaptureToken@@YA?AT_LARGE_INTEGER@@XZ; MakeCaptureToken(void)
0x180012d5a  lea     r9, [rsp+68h+arg_0]; int *
0x180012d5f  mov     dword ptr [rsp+68h+var_48], 4000008Fh; int
0x180012d67  mov     r8d, 1Ch; unsigned __int64
0x180012d6d  mov     qword ptr [rsp+68h+var_48+4], rdi
0x180012d72  lea     rdx, [rsp+68h+var_48]; void *
0x180012d77  mov     qword ptr [rsp+68h+var_48+0Ch], rsi
0x180012d7c  mov     rbx, rax
0x180012d7f  mov     [rsp+68h+var_34], rax
0x180012d84  mov     [rsp+68h+arg_0], 0
0x180012d8c  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KPEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,long *)
0x180012d91  mov     edi, eax
0x180012d93  test    eax, eax
0x180012d95  jns     short loc_180012DB4
0x180012d97  mov     edx, 293h; void *
0x180012d9c  mov     rcx, [rsp+68h]; this
0x180012da1  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012da8  mov     r9d, edi; char *
0x180012dab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012db0  mov     eax, edi
0x180012db2  jmp     short loc_180012DC8
0x180012db4  mov     edi, [rsp+68h+arg_0]
0x180012db8  test    edi, edi
0x180012dba  jns     short loc_180012DC3
0x180012dbc  mov     edx, 294h
0x180012dc1  jmp     short loc_180012D9C
0x180012dc3  mov     [r14], rbx
0x180012dc6  xor     eax, eax
0x180012dc8  add     rsp, 48h
0x180012dcc  pop     r14
0x180012dce  pop     rdi
0x180012dcf  pop     rsi
0x180012dd0  pop     rbx
0x180012dd1  retn
```
