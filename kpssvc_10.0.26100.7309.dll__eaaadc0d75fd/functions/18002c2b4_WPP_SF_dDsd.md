# WPP_SF_dDsd

- ea: `0x18002c2b4`
- end: `0x18002c352`
- name: `WPP_SF_dDsd`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800291e4`

## callees

- `0x18002c2b4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002c33d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002c33d`

## string_xrefs

- `0x18002c2c8`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
ULONG __fastcall WPP_SF_dDsd(TRACEHANDLE a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rax
  int v6; // [rsp+70h] [rbp-18h] BYREF
  int v7[4]; // [rsp+78h] [rbp-10h] BYREF
  int v8; // [rsp+A8h] [rbp+20h] BYREF

  v8 = a4;
  v6 = 779;
  v7[0] = 1359;
  v4 = -1;
  do
    ++v4;
  while ( aDsSecurityProt[v4] );
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
           0x2Cu,
           &v8,
           4,
           v7,
           4,
           "ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
           v4 + 1,
           &v6,
           4,
           0);
}

```

## disassembly

```asm
0x18002c2b4  mov     [rsp+arg_18], r9d
0x18002c2b9  sub     rsp, 88h
0x18002c2c0  mov     [rsp+88h+var_18], 30Bh
0x18002c2c8  lea     r10, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002c2cf  mov     [rsp+88h+var_10], 54Fh
0x18002c2d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c2db  inc     rax
0x18002c2de  cmp     byte ptr [r10+rax], 0
0x18002c2e3  jnz     short loc_18002C2DB
0x18002c2e5  and     [rsp+88h+var_28], 0
0x18002c2eb  lea     rdx, [rsp+88h+var_18]
0x18002c2f0  inc     rax
0x18002c2f3  mov     r9d, 2Ch ; ','; MessageNumber
0x18002c2f9  lea     r8d, [r9-28h]
0x18002c2fd  mov     [rsp+88h+var_30], r8
0x18002c302  mov     [rsp+88h+var_38], rdx
0x18002c307  lea     edx, [r9-1]; MessageFlags
0x18002c30b  mov     [rsp+88h+var_40], rax
0x18002c310  lea     rax, [rsp+88h+var_10]
0x18002c315  mov     [rsp+88h+var_48], r10
0x18002c31a  mov     [rsp+88h+var_50], r8
0x18002c31f  mov     [rsp+88h+var_58], rax
0x18002c324  lea     rax, [rsp+88h+arg_18]
0x18002c32c  mov     [rsp+88h+var_60], r8
0x18002c331  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids; MessageGuid
0x18002c338  mov     [rsp+88h+var_68], rax
0x18002c33d  call    cs:__imp_TraceMessage
0x18002c344  nop     dword ptr [rax+rax+00h]
0x18002c349  add     rsp, 88h
0x18002c350  retn
```
