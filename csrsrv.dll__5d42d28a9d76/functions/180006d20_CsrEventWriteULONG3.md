# CsrEventWriteULONG3

- ea: `0x180006d20`
- end: `0x180006ddb`
- name: `CsrEventWriteULONG3`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006a80`

## callees

- `0x180006d20`
- `0x18000ab80`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180006d54`
- `ntdll!EtwEventEnabled` at `0x180006d54`
- `ntdll!EtwEventWrite` at `0x180006dbc`
- `ntdll!EtwEventWrite` at `0x180006dbc`

## pseudocode

```c
void __fastcall CsrEventWriteULONG3(__int64 a1, int a2, int a3, int a4)
{
  _QWORD v4[6]; // [rsp+20h] [rbp-48h] BYREF
  int v5; // [rsp+78h] [rbp+10h] BYREF
  int v6; // [rsp+80h] [rbp+18h] BYREF
  int v7; // [rsp+88h] [rbp+20h] BYREF

  v7 = a4;
  v6 = a3;
  v5 = a2;
  if ( CsrTraceHandle )
  {
    if ( EtwEventEnabled(CsrTraceHandle, &CsrEvt_ShutdownProcess_Start) )
    {
      v4[0] = &v5;
      v4[1] = 4;
      v4[2] = &v6;
      v4[3] = 4;
      v4[4] = &v7;
      v4[5] = 4;
      ((void (__fastcall *)(REGHANDLE, const EVENT_DESCRIPTOR *, __int64, _QWORD *))EtwEventWrite)(
        CsrTraceHandle,
        &CsrEvt_ShutdownProcess_Start,
        3,
        v4);
    }
  }
}

```

## disassembly

```asm
0x180006d20  mov     [rsp+arg_18], r9d
0x180006d25  mov     [rsp+arg_10], r8d
0x180006d2a  mov     [rsp+arg_8], edx
0x180006d2e  sub     rsp, 68h
0x180006d32  mov     rax, cs:__security_cookie
0x180006d39  xor     rax, rsp
0x180006d3c  mov     [rsp+68h+var_18], rax
0x180006d41  mov     rcx, cs:CsrTraceHandle; RegHandle
0x180006d48  test    rcx, rcx
0x180006d4b  jz      short loc_180006DC8
0x180006d4d  lea     rdx, CsrEvt_ShutdownProcess_Start; EventDescriptor
0x180006d54  call    cs:__imp_EtwEventEnabled
0x180006d5b  nop     dword ptr [rax+rax+00h]
0x180006d60  test    al, al
0x180006d62  jz      short loc_180006DC8
0x180006d64  mov     rcx, cs:CsrTraceHandle
0x180006d6b  lea     rax, [rsp+68h+arg_8]
0x180006d70  mov     [rsp+68h+var_48], rax
0x180006d75  lea     r9, [rsp+68h+var_48]
0x180006d7a  lea     rax, [rsp+68h+arg_10]
0x180006d82  mov     [rsp+68h+var_40], 4
0x180006d8b  mov     [rsp+68h+var_38], rax
0x180006d90  lea     rdx, CsrEvt_ShutdownProcess_Start
0x180006d97  lea     rax, [rsp+68h+arg_18]
0x180006d9f  mov     [rsp+68h+var_30], 4
0x180006da8  mov     r8d, 3
0x180006dae  mov     [rsp+68h+var_28], rax
0x180006db3  mov     [rsp+68h+var_20], 4
0x180006dbc  call    cs:__imp_EtwEventWrite
0x180006dc3  nop     dword ptr [rax+rax+00h]
0x180006dc8  mov     rcx, [rsp+68h+var_18]
0x180006dcd  xor     rcx, rsp; StackCookie
0x180006dd0  call    __security_check_cookie
0x180006dd5  add     rsp, 68h
0x180006dd9  retn
```
