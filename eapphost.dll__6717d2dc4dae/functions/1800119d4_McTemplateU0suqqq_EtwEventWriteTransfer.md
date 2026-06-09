# McTemplateU0suqqq_EtwEventWriteTransfer

- ea: `0x1800119d4`
- end: `0x180011a7e`
- name: `McTemplateU0suqqq_EtwEventWriteTransfer`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800113a0`

## callees

- `0x180002a90`
- `0x180009b98`

## string_xrefs

- `0x1800119f4`: `Eap method DLL path name`

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
0x1800119d4  mov     [rsp-8+arg_18], r9b
0x1800119d9  push    rbp
0x1800119da  lea     rbp, [rsp-3Fh]
0x1800119df  sub     rsp, 0A0h
0x1800119e6  mov     rax, cs:__security_cookie
0x1800119ed  xor     rax, rsp
0x1800119f0  mov     [rbp+3Fh+var_10], rax
0x1800119f4  lea     rax, aEapMethodDllPa; "Eap method DLL path name"
0x1800119fb  mov     [rbp+3Fh+var_58], 19h
0x180011a03  mov     [rbp+3Fh+var_60], rax
0x180011a07  lea     rdx, PeerPathNameValidationFailure
0x180011a0e  lea     rax, [rbp+3Fh+arg_18]
0x180011a12  mov     [rbp+3Fh+var_48], 1
0x180011a1a  mov     [rbp+3Fh+var_50], rax
0x180011a1e  lea     rcx, eaphost_Context
0x180011a25  lea     rax, [rbp+3Fh+arg_20]
0x180011a29  mov     [rbp+3Fh+var_38], 4
0x180011a31  mov     [rbp+3Fh+var_40], rax
0x180011a35  mov     r9d, 6
0x180011a3b  lea     rax, [rbp+3Fh+arg_28]
0x180011a3f  mov     [rbp+3Fh+var_28], 4
0x180011a47  mov     [rbp+3Fh+var_30], rax
0x180011a4b  lea     rax, [rbp+3Fh+arg_30]
0x180011a4f  mov     [rbp+3Fh+var_20], rax
0x180011a53  lea     rax, [rbp+3Fh+var_70]
0x180011a57  mov     [rsp+0A0h+var_80], rax
0x180011a5c  mov     [rbp+3Fh+var_18], 4
0x180011a64  call    McGenEventWrite_EtwEventWriteTransfer
0x180011a69  mov     rcx, [rbp+3Fh+var_10]
0x180011a6d  xor     rcx, rsp; StackCookie
0x180011a70  call    __security_check_cookie
0x180011a75  add     rsp, 0A0h
0x180011a7c  pop     rbp
0x180011a7d  retn
```
