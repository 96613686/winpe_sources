# WPP_SF_DDsd

- ea: `0x18002bbdc`
- end: `0x18002bc75`
- name: `WPP_SF_DDsd`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800291e4`

## callees

- `0x18002bbdc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002bc60`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002bc60`

## string_xrefs

- `0x18002bbf0`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
ULONG WPP_SF_DDsd(TRACEHANDLE a1, __int64 a2, __int64 a3, int a4, ...)
{
  __int64 v4; // rax
  int v6[6]; // [rsp+70h] [rbp-18h] BYREF
  int v7; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+B0h] [rbp+28h] BYREF

  va_start(va, a4);
  v7 = a4;
  v6[0] = 1004;
  v4 = -1;
  do
    ++v4;
  while ( aDsSecurityProt[v4] );
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
           0x35u,
           &v7,
           4,
           va,
           4,
           "ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
           v4 + 1,
           v6,
           4,
           0);
}

```

## disassembly

```asm
0x18002bbdc  mov     [rsp+arg_18], r9d
0x18002bbe1  sub     rsp, 88h
0x18002bbe8  mov     [rsp+88h+var_18], 3ECh
0x18002bbf0  lea     r10, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002bbf7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bbfb  inc     rax
0x18002bbfe  cmp     byte ptr [r10+rax], 0
0x18002bc03  jnz     short loc_18002BBFB
0x18002bc05  and     [rsp+88h+var_28], 0
0x18002bc0b  lea     rdx, [rsp+88h+var_18]
0x18002bc10  inc     rax
0x18002bc13  mov     r9d, 35h ; '5'; MessageNumber
0x18002bc19  lea     r8d, [r9-31h]
0x18002bc1d  mov     [rsp+88h+var_30], r8
0x18002bc22  mov     [rsp+88h+var_38], rdx
0x18002bc27  lea     edx, [r9-0Ah]; MessageFlags
0x18002bc2b  mov     [rsp+88h+var_40], rax
0x18002bc30  lea     rax, [rsp+88h+arg_20]
0x18002bc38  mov     [rsp+88h+var_48], r10
0x18002bc3d  mov     [rsp+88h+var_50], r8
0x18002bc42  mov     [rsp+88h+var_58], rax
0x18002bc47  lea     rax, [rsp+88h+arg_18]
0x18002bc4f  mov     [rsp+88h+var_60], r8
0x18002bc54  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids; MessageGuid
0x18002bc5b  mov     [rsp+88h+var_68], rax
0x18002bc60  call    cs:__imp_TraceMessage
0x18002bc67  nop     dword ptr [rax+rax+00h]
0x18002bc6c  add     rsp, 88h
0x18002bc73  retn
```
