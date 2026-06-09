# DwmpSetupWindowCapture

- ea: `0x180012c80`
- end: `0x180012d22`
- name: `DwmpSetupWindowCapture`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000a72c`
- `0x18000b92c`
- `0x180012c80`

## string_xrefs

- `0x180012cf1`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpSetupWindowCapture(__int64 a1, __int64 a2, union _LARGE_INTEGER *a3)
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
  v9[0] = 1073741953;
  *(_QWORD *)&v9[1] = a1;
  *(_QWORD *)&v9[3] = a2;
  CaptureToken = MakeCaptureToken();
  v10 = CaptureToken;
  v12 = 0;
  v6 = CApiPortClient::SendRequestValidate(v5, v9, 0x1Cu, &v12);
  if ( v6 < 0 )
  {
    v7 = 273;
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
    v7 = 274;
    goto LABEL_3;
  }
  *a3 = CaptureToken;
  return 0;
}

```

## disassembly

```asm
0x180012c80  push    rbx
0x180012c82  push    rsi
0x180012c83  push    rdi
0x180012c84  push    r14
0x180012c86  sub     rsp, 48h
0x180012c8a  xorps   xmm0, xmm0
0x180012c8d  xor     eax, eax
0x180012c8f  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180012c94  mov     r14, r8
0x180012c97  mov     rsi, rdx
0x180012c9a  movups  xmmword ptr [rsp+68h+var_48+0Ch], xmm0
0x180012c9f  mov     rdi, rcx
0x180012ca2  mov     [r8], rax
0x180012ca5  call    ?MakeCaptureToken@@YA?AT_LARGE_INTEGER@@XZ; MakeCaptureToken(void)
0x180012caa  lea     r9, [rsp+68h+arg_0]; int *
0x180012caf  mov     dword ptr [rsp+68h+var_48], 40000081h; int
0x180012cb7  mov     r8d, 1Ch; unsigned __int64
0x180012cbd  mov     qword ptr [rsp+68h+var_48+4], rdi
0x180012cc2  lea     rdx, [rsp+68h+var_48]; void *
0x180012cc7  mov     qword ptr [rsp+68h+var_48+0Ch], rsi
0x180012ccc  mov     rbx, rax
0x180012ccf  mov     [rsp+68h+var_34], rax
0x180012cd4  mov     [rsp+68h+arg_0], 0
0x180012cdc  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KPEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,long *)
0x180012ce1  mov     edi, eax
0x180012ce3  test    eax, eax
0x180012ce5  jns     short loc_180012D04
0x180012ce7  mov     edx, 111h; void *
0x180012cec  mov     rcx, [rsp+68h]; this
0x180012cf1  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012cf8  mov     r9d, edi; char *
0x180012cfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d00  mov     eax, edi
0x180012d02  jmp     short loc_180012D18
0x180012d04  mov     edi, [rsp+68h+arg_0]
0x180012d08  test    edi, edi
0x180012d0a  jns     short loc_180012D13
0x180012d0c  mov     edx, 112h
0x180012d11  jmp     short loc_180012CEC
0x180012d13  mov     [r14], rbx
0x180012d16  xor     eax, eax
0x180012d18  add     rsp, 48h
0x180012d1c  pop     r14
0x180012d1e  pop     rdi
0x180012d1f  pop     rsi
0x180012d20  pop     rbx
0x180012d21  retn
```
