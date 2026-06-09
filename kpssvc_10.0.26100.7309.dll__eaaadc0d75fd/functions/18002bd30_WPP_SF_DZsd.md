# WPP_SF_DZsd

- ea: `0x18002bd30`
- end: `0x18002be21`
- name: `WPP_SF_DZsd`
- size: `241`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800291e4`

## callees

- `0x18002bd30`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002be03`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002be03`

## string_xrefs

- `0x18002bd4b`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
ULONG __fastcall WPP_SF_DZsd(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, int a4, unsigned __int16 *a5)
{
  const wchar_t *v5; // rax
  __int64 v6; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  const wchar_t *v10; // rdx
  int v12[6]; // [rsp+80h] [rbp-18h] BYREF
  int v13; // [rsp+B8h] [rbp+20h] BYREF

  v13 = a4;
  v5 = a5;
  v6 = -1;
  v12[0] = 1047;
  do
    ++v6;
  while ( aDsSecurityProt[v6] );
  v8 = v6 + 1;
  if ( a5 )
  {
    v9 = *a5;
    if ( *a5 )
    {
      v10 = (const wchar_t *)*((_QWORD *)a5 + 1);
      goto LABEL_8;
    }
  }
  else
  {
    v9 = 8;
  }
  v10 = L"NULL";
LABEL_8:
  if ( !a5 )
    v5 = L"\b";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
           0x38u,
           &v13,
           4,
           v5,
           2,
           v10,
           v9,
           "ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
           v8,
           v12,
           4,
           0);
}

```

## disassembly

```asm
0x18002bd30  mov     r11, rsp
0x18002bd33  mov     [r11+8], rbx
0x18002bd37  mov     [r11+20h], r9d
0x18002bd3b  push    rdi
0x18002bd3c  sub     rsp, 90h
0x18002bd43  mov     rax, [rsp+98h+arg_20]
0x18002bd4b  lea     rdi, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002bd52  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002bd56  mov     dword ptr [r11-18h], 417h
0x18002bd5e  xor     r11d, r11d
0x18002bd61  mov     r10, rcx
0x18002bd64  inc     rdx
0x18002bd67  cmp     [rdi+rdx], r11b
0x18002bd6b  jnz     short loc_18002BD64
0x18002bd6d  lea     r8, [rdx+1]
0x18002bd71  test    rax, rax
0x18002bd74  jz      short loc_18002BD85
0x18002bd76  movzx   ecx, word ptr [rax]
0x18002bd79  cmp     [rax], r11w
0x18002bd7d  jz      short loc_18002BD8A
0x18002bd7f  mov     rdx, [rax+8]
0x18002bd83  jmp     short loc_18002BD91
0x18002bd85  mov     ecx, 8
0x18002bd8a  lea     rdx, aNull_0; "NULL"
0x18002bd91  mov     [rsp+98h+var_28], r11
0x18002bd96  lea     r9, asc_1800348B4; "\b"
0x18002bd9d  mov     ebx, 38h ; '8'
0x18002bda2  test    rax, rax
0x18002bda5  cmovz   rax, r9
0x18002bda9  lea     r9, [rsp+98h+var_18]
0x18002bdb1  lea     r11d, [rbx-34h]
0x18002bdb5  mov     [rsp+98h+var_30], r11
0x18002bdba  mov     [rsp+98h+var_38], r9
0x18002bdbf  mov     r9d, ebx; MessageNumber
0x18002bdc2  mov     [rsp+98h+var_40], r8
0x18002bdc7  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids; MessageGuid
0x18002bdce  mov     [rsp+98h+var_48], rdi
0x18002bdd3  mov     [rsp+98h+var_50], rcx
0x18002bdd8  mov     rcx, r10; LoggerHandle
0x18002bddb  mov     [rsp+98h+var_58], rdx
0x18002bde0  lea     edx, [rbx-0Dh]; MessageFlags
0x18002bde3  mov     [rsp+98h+var_60], 2
0x18002bdec  mov     [rsp+98h+var_68], rax
0x18002bdf1  lea     rax, [rsp+98h+arg_18]
0x18002bdf9  mov     [rsp+98h+var_70], r11
0x18002bdfe  mov     [rsp+98h+var_78], rax
0x18002be03  call    cs:__imp_TraceMessage
0x18002be0a  nop     dword ptr [rax+rax+00h]
0x18002be0f  mov     rbx, [rsp+98h+arg_0]
0x18002be17  add     rsp, 90h
0x18002be1e  pop     rdi
0x18002be1f  retn
```
