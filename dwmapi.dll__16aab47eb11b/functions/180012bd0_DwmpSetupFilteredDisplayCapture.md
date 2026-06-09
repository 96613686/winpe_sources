# DwmpSetupFilteredDisplayCapture

- ea: `0x180012bd0`
- end: `0x180012c72`
- name: `DwmpSetupFilteredDisplayCapture`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000a72c`
- `0x18000b92c`
- `0x180012bd0`

## string_xrefs

- `0x180012c41`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpSetupFilteredDisplayCapture(__int64 a1, __int64 a2, union _LARGE_INTEGER *a3)
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
  v9[0] = 1073741962;
  *(_QWORD *)&v9[1] = a1;
  *(_QWORD *)&v9[3] = a2;
  CaptureToken = MakeCaptureToken();
  v10 = CaptureToken;
  v12 = 0;
  v6 = CApiPortClient::SendRequestValidate(v5, v9, 0x1Cu, &v12);
  if ( v6 < 0 )
  {
    v7 = 488;
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
    v7 = 489;
    goto LABEL_3;
  }
  *a3 = CaptureToken;
  return 0;
}

```

## disassembly

```asm
0x180012bd0  push    rbx
0x180012bd2  push    rsi
0x180012bd3  push    rdi
0x180012bd4  push    r14
0x180012bd6  sub     rsp, 48h
0x180012bda  xorps   xmm0, xmm0
0x180012bdd  xor     eax, eax
0x180012bdf  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180012be4  mov     r14, r8
0x180012be7  mov     rsi, rdx
0x180012bea  movups  xmmword ptr [rsp+68h+var_48+0Ch], xmm0
0x180012bef  mov     rdi, rcx
0x180012bf2  mov     [r8], rax
0x180012bf5  call    ?MakeCaptureToken@@YA?AT_LARGE_INTEGER@@XZ; MakeCaptureToken(void)
0x180012bfa  lea     r9, [rsp+68h+arg_0]; int *
0x180012bff  mov     dword ptr [rsp+68h+var_48], 4000008Ah; int
0x180012c07  mov     r8d, 1Ch; unsigned __int64
0x180012c0d  mov     qword ptr [rsp+68h+var_48+4], rdi
0x180012c12  lea     rdx, [rsp+68h+var_48]; void *
0x180012c17  mov     qword ptr [rsp+68h+var_48+0Ch], rsi
0x180012c1c  mov     rbx, rax
0x180012c1f  mov     [rsp+68h+var_34], rax
0x180012c24  mov     [rsp+68h+arg_0], 0
0x180012c2c  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KPEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,long *)
0x180012c31  mov     edi, eax
0x180012c33  test    eax, eax
0x180012c35  jns     short loc_180012C54
0x180012c37  mov     edx, 1E8h; void *
0x180012c3c  mov     rcx, [rsp+68h]; this
0x180012c41  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012c48  mov     r9d, edi; char *
0x180012c4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c50  mov     eax, edi
0x180012c52  jmp     short loc_180012C68
0x180012c54  mov     edi, [rsp+68h+arg_0]
0x180012c58  test    edi, edi
0x180012c5a  jns     short loc_180012C63
0x180012c5c  mov     edx, 1E9h
0x180012c61  jmp     short loc_180012C3C
0x180012c63  mov     [r14], rbx
0x180012c66  xor     eax, eax
0x180012c68  add     rsp, 48h
0x180012c6c  pop     r14
0x180012c6e  pop     rdi
0x180012c6f  pop     rsi
0x180012c70  pop     rbx
0x180012c71  retn
```
