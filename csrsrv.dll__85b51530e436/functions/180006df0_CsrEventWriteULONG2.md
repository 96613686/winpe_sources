# CsrEventWriteULONG2

- ea: `0x180006df0`
- end: `0x180006e8d`
- name: `CsrEventWriteULONG2`
- size: `157`
- prototype: `void __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006a80`

## callees

- `0x180006df0`
- `0x18000ab80`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180006e1f`
- `ntdll!EtwEventEnabled` at `0x180006e1f`
- `ntdll!EtwEventWrite` at `0x180006e6e`
- `ntdll!EtwEventWrite` at `0x180006e6e`

## pseudocode

```c
void __fastcall CsrEventWriteULONG2(__int64 a1, int a2, int a3)
{
  _QWORD v3[4]; // [rsp+20h] [rbp-38h] BYREF
  int v4; // [rsp+68h] [rbp+10h] BYREF
  int v5; // [rsp+70h] [rbp+18h] BYREF

  v5 = a3;
  v4 = a2;
  if ( CsrTraceHandle )
  {
    if ( EtwEventEnabled(CsrTraceHandle, &CsrEvt_ShutdownProcess_Stop) )
    {
      v3[0] = &v4;
      v3[1] = 4;
      v3[2] = &v5;
      v3[3] = 4;
      ((void (__fastcall *)(REGHANDLE, const EVENT_DESCRIPTOR *, __int64, _QWORD *))EtwEventWrite)(
        CsrTraceHandle,
        &CsrEvt_ShutdownProcess_Stop,
        2,
        v3);
    }
  }
}

```

## disassembly

```asm
0x180006df0  mov     [rsp+arg_10], r8d
0x180006df5  mov     [rsp+arg_8], edx
0x180006df9  sub     rsp, 58h
0x180006dfd  mov     rax, cs:__security_cookie
0x180006e04  xor     rax, rsp
0x180006e07  mov     [rsp+58h+var_18], rax
0x180006e0c  mov     rcx, cs:CsrTraceHandle; RegHandle
0x180006e13  test    rcx, rcx
0x180006e16  jz      short loc_180006E7A
0x180006e18  lea     rdx, CsrEvt_ShutdownProcess_Stop; EventDescriptor
0x180006e1f  call    cs:__imp_EtwEventEnabled
0x180006e26  nop     dword ptr [rax+rax+00h]
0x180006e2b  test    al, al
0x180006e2d  jz      short loc_180006E7A
0x180006e2f  mov     rcx, cs:CsrTraceHandle
0x180006e36  lea     rax, [rsp+58h+arg_8]
0x180006e3b  mov     [rsp+58h+var_38], rax
0x180006e40  lea     r9, [rsp+58h+var_38]
0x180006e45  lea     rax, [rsp+58h+arg_10]
0x180006e4a  mov     [rsp+58h+var_30], 4
0x180006e53  mov     r8d, 2
0x180006e59  mov     [rsp+58h+var_28], rax
0x180006e5e  lea     rdx, CsrEvt_ShutdownProcess_Stop
0x180006e65  mov     [rsp+58h+var_20], 4
0x180006e6e  call    cs:__imp_EtwEventWrite
0x180006e75  nop     dword ptr [rax+rax+00h]
0x180006e7a  mov     rcx, [rsp+58h+var_18]
0x180006e7f  xor     rcx, rsp; StackCookie
0x180006e82  call    __security_check_cookie
0x180006e87  add     rsp, 58h
0x180006e8b  retn
```
