# WPP_SF_DDDsd

- ea: `0x18002bb28`
- end: `0x18002bbd4`
- name: `WPP_SF_DDDsd`
- size: `172`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, char, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800285a0`
- `0x18002aae8`

## callees

- `0x18002bb28`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002bbbf`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002bbbf`

## string_xrefs

- `0x18002bb39`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
ULONG WPP_SF_DDDsd(TRACEHANDLE a1, USHORT a2, _DWORD a3, _DWORD a4, char a5, ...)
{
  __int64 v5; // rax
  int v7[6]; // [rsp+80h] [rbp-18h] BYREF
  __int64 v8; // [rsp+C8h] [rbp+30h] BYREF
  va_list va; // [rsp+C8h] [rbp+30h]
  __int64 v10; // [rsp+D0h] [rbp+38h]
  va_list va1; // [rsp+D8h] [rbp+40h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  v10 = va_arg(va1, _QWORD);
  v7[0] = 11;
  v5 = -1;
  do
    ++v5;
  while ( aDsSecurityProt[v5] );
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
           a2,
           v7,
           4,
           &a5,
           4,
           va,
           4,
           "ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
           v5 + 1,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18002bb28  mov     rax, rsp
0x18002bb2b  sub     rsp, 98h
0x18002bb32  mov     dword ptr [rax-18h], 0Bh
0x18002bb39  lea     r10, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002bb40  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bb44  inc     rax
0x18002bb47  cmp     byte ptr [r10+rax], 0
0x18002bb4c  jnz     short loc_18002BB44
0x18002bb4e  and     [rsp+98h+var_28], 0
0x18002bb54  lea     r8, [rsp+98h+arg_38]
0x18002bb5c  mov     r9d, 4
0x18002bb62  inc     rax
0x18002bb65  mov     [rsp+98h+var_30], r9
0x18002bb6a  mov     [rsp+98h+var_38], r8
0x18002bb6f  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids; MessageGuid
0x18002bb76  mov     [rsp+98h+var_40], rax
0x18002bb7b  lea     rax, [rsp+98h+arg_28]
0x18002bb83  mov     [rsp+98h+var_48], r10
0x18002bb88  mov     [rsp+98h+var_50], r9
0x18002bb8d  mov     [rsp+98h+var_58], rax
0x18002bb92  lea     rax, [rsp+98h+arg_20]
0x18002bb9a  mov     [rsp+98h+var_60], r9
0x18002bb9f  mov     [rsp+98h+var_68], rax
0x18002bba4  lea     rax, [rsp+98h+var_18]
0x18002bbac  mov     [rsp+98h+var_70], r9
0x18002bbb1  movzx   r9d, dx; MessageNumber
0x18002bbb5  mov     edx, 2Bh ; '+'; MessageFlags
0x18002bbba  mov     [rsp+98h+var_78], rax
0x18002bbbf  call    cs:__imp_TraceMessage
0x18002bbc6  nop     dword ptr [rax+rax+00h]
0x18002bbcb  add     rsp, 98h
0x18002bbd2  retn
```
