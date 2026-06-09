# WPP_SF_dsd

- ea: `0x18002c458`
- end: `0x18002c4d5`
- name: `WPP_SF_dsd`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800288c4`
- `0x1800289f8`
- `0x180028c08`

## callees

- `0x18002c458`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002c4c3`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002c4c3`

## string_xrefs

- `0x18002c461`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
ULONG WPP_SF_dsd(TRACEHANDLE a1, USHORT a2, __int64 a3, int a4, int a5, ...)
{
  __int64 v5; // rax
  int v7; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = a4;
  v5 = -1;
  do
    ++v5;
  while ( aDsSecurityProt[v5] );
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
           a2,
           &v7,
           4,
           "ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
           v5 + 1,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x18002c458  mov     [rsp+arg_18], r9d
0x18002c45d  sub     rsp, 68h
0x18002c461  lea     r10, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002c468  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c46c  inc     rax
0x18002c46f  cmp     byte ptr [r10+rax], 0
0x18002c474  jnz     short loc_18002C46C
0x18002c476  and     [rsp+68h+var_18], 0
0x18002c47c  lea     r8, [rsp+68h+arg_28]
0x18002c484  mov     r9d, 4
0x18002c48a  inc     rax
0x18002c48d  mov     [rsp+68h+var_20], r9
0x18002c492  mov     [rsp+68h+var_28], r8
0x18002c497  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids; MessageGuid
0x18002c49e  mov     [rsp+68h+var_30], rax
0x18002c4a3  lea     rax, [rsp+68h+arg_18]
0x18002c4ab  mov     [rsp+68h+var_38], r10
0x18002c4b0  mov     [rsp+68h+var_40], r9
0x18002c4b5  movzx   r9d, dx; MessageNumber
0x18002c4b9  mov     edx, 2Bh ; '+'; MessageFlags
0x18002c4be  mov     [rsp+68h+var_48], rax
0x18002c4c3  call    cs:__imp_TraceMessage
0x18002c4ca  nop     dword ptr [rax+rax+00h]
0x18002c4cf  add     rsp, 68h
0x18002c4d3  retn
```
