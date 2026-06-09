# McTemplateU0suqqq_EtwEventWriteTransfer

- ea: `0x180012140`
- end: `0x1800121eb`
- name: `McTemplateU0suqqq_EtwEventWriteTransfer`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011ae0`

## callees

- `0x180002af0`
- `0x180009fe4`

## string_xrefs

- `0x180012160`: `Eap method DLL path name`

## pseudocode

```c
__int64 __fastcall McTemplateU0suqqq_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        char a5,
        char a6,
        char a7)
{
  _BYTE v8[16]; // [rsp+30h] [rbp-31h] BYREF
  const char *v9; // [rsp+40h] [rbp-21h]
  __int64 v10; // [rsp+48h] [rbp-19h]
  char *v11; // [rsp+50h] [rbp-11h]
  __int64 v12; // [rsp+58h] [rbp-9h]
  char *v13; // [rsp+60h] [rbp-1h]
  __int64 v14; // [rsp+68h] [rbp+7h]
  char *v15; // [rsp+70h] [rbp+Fh]
  __int64 v16; // [rsp+78h] [rbp+17h]
  char *v17; // [rsp+80h] [rbp+1Fh]
  __int64 v18; // [rsp+88h] [rbp+27h]
  char v19; // [rsp+C8h] [rbp+67h] BYREF

  v19 = a4;
  v10 = 25;
  v9 = "Eap method DLL path name";
  v12 = 1;
  v11 = &v19;
  v14 = 4;
  v13 = &a5;
  v16 = 4;
  v15 = &a6;
  v17 = &a7;
  v18 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(
           &eaphost_Context,
           (__int64)PeerPathNameValidationFailure,
           a3,
           6,
           (__int64)v8);
}

```

## disassembly

```asm
0x180012140  mov     [rsp-8+arg_18], r9b
0x180012145  push    rbp
0x180012146  lea     rbp, [rsp-3Fh]
0x18001214b  sub     rsp, 0A0h
0x180012152  mov     rax, cs:__security_cookie
0x180012159  xor     rax, rsp
0x18001215c  mov     [rbp+3Fh+var_10], rax
0x180012160  lea     rax, aEapMethodDllPa; "Eap method DLL path name"
0x180012167  mov     [rbp+3Fh+var_58], 19h
0x18001216f  mov     [rbp+3Fh+var_60], rax
0x180012173  lea     rdx, PeerPathNameValidationFailure
0x18001217a  lea     rax, [rbp+3Fh+arg_18]
0x18001217e  mov     [rbp+3Fh+var_48], 1
0x180012186  mov     [rbp+3Fh+var_50], rax
0x18001218a  lea     rcx, eaphost_Context
0x180012191  lea     rax, [rbp+3Fh+arg_20]
0x180012195  mov     [rbp+3Fh+var_38], 4
0x18001219d  mov     [rbp+3Fh+var_40], rax
0x1800121a1  mov     r9d, 6
0x1800121a7  lea     rax, [rbp+3Fh+arg_28]
0x1800121ab  mov     [rbp+3Fh+var_28], 4
0x1800121b3  mov     [rbp+3Fh+var_30], rax
0x1800121b7  lea     rax, [rbp+3Fh+arg_30]
0x1800121bb  mov     [rbp+3Fh+var_20], rax
0x1800121bf  lea     rax, [rbp+3Fh+var_70]
0x1800121c3  mov     [rsp+0A0h+var_80], rax
0x1800121c8  mov     [rbp+3Fh+var_18], 4
0x1800121d0  call    McGenEventWrite_EtwEventWriteTransfer
0x1800121d5  mov     rcx, [rbp+3Fh+var_10]
0x1800121d9  xor     rcx, rsp; StackCookie
0x1800121dc  call    __security_check_cookie
0x1800121e1  add     rsp, 0A0h
0x1800121e8  pop     rbp
0x1800121e9  retn
```
