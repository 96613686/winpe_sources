# DwmpSetupDisplayCapture

- ea: `0x180012b20`
- end: `0x180012bc2`
- name: `DwmpSetupDisplayCapture`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000a72c`
- `0x18000b92c`
- `0x180012b20`

## string_xrefs

- `0x180012b91`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpSetupDisplayCapture(__int64 a1, __int64 a2, union _LARGE_INTEGER *a3)
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
  v9[0] = 1073741955;
  *(_QWORD *)&v9[1] = a1;
  *(_QWORD *)&v9[3] = a2;
  CaptureToken = MakeCaptureToken();
  v10 = CaptureToken;
  v12 = 0;
  v6 = CApiPortClient::SendRequestValidate(v5, v9, 0x1Cu, &v12);
  if ( v6 < 0 )
  {
    v7 = 312;
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
    v7 = 313;
    goto LABEL_3;
  }
  *a3 = CaptureToken;
  return 0;
}

```

## disassembly

```asm
0x180012b20  push    rbx
0x180012b22  push    rsi
0x180012b23  push    rdi
0x180012b24  push    r14
0x180012b26  sub     rsp, 48h
0x180012b2a  xorps   xmm0, xmm0
0x180012b2d  xor     eax, eax
0x180012b2f  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180012b34  mov     r14, r8
0x180012b37  mov     rsi, rdx
0x180012b3a  movups  xmmword ptr [rsp+68h+var_48+0Ch], xmm0
0x180012b3f  mov     rdi, rcx
0x180012b42  mov     [r8], rax
0x180012b45  call    ?MakeCaptureToken@@YA?AT_LARGE_INTEGER@@XZ; MakeCaptureToken(void)
0x180012b4a  lea     r9, [rsp+68h+arg_0]; int *
0x180012b4f  mov     dword ptr [rsp+68h+var_48], 40000083h; int
0x180012b57  mov     r8d, 1Ch; unsigned __int64
0x180012b5d  mov     qword ptr [rsp+68h+var_48+4], rdi
0x180012b62  lea     rdx, [rsp+68h+var_48]; void *
0x180012b67  mov     qword ptr [rsp+68h+var_48+0Ch], rsi
0x180012b6c  mov     rbx, rax
0x180012b6f  mov     [rsp+68h+var_34], rax
0x180012b74  mov     [rsp+68h+arg_0], 0
0x180012b7c  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KPEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,long *)
0x180012b81  mov     edi, eax
0x180012b83  test    eax, eax
0x180012b85  jns     short loc_180012BA4
0x180012b87  mov     edx, 138h; void *
0x180012b8c  mov     rcx, [rsp+68h]; this
0x180012b91  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012b98  mov     r9d, edi; char *
0x180012b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ba0  mov     eax, edi
0x180012ba2  jmp     short loc_180012BB8
0x180012ba4  mov     edi, [rsp+68h+arg_0]
0x180012ba8  test    edi, edi
0x180012baa  jns     short loc_180012BB3
0x180012bac  mov     edx, 139h
0x180012bb1  jmp     short loc_180012B8C
0x180012bb3  mov     [r14], rbx
0x180012bb6  xor     eax, eax
0x180012bb8  add     rsp, 48h
0x180012bbc  pop     r14
0x180012bbe  pop     rdi
0x180012bbf  pop     rsi
0x180012bc0  pop     rbx
0x180012bc1  retn
```
