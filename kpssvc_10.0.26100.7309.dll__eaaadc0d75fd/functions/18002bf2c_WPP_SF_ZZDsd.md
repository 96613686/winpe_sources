# WPP_SF_ZZDsd

- ea: `0x18002bf2c`
- end: `0x18002c06b`
- name: `WPP_SF_ZZDsd`
- size: `319`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800280d8`

## callees

- `0x18002bf2c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002c040`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002c040`

## string_xrefs

- `0x18002bf50`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
ULONG WPP_SF_ZZDsd(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, const wchar_t *a4, unsigned __int16 *a5, ...)
{
  const wchar_t *v5; // rdx
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  const wchar_t *v10; // r10
  __int64 v11; // rax
  const wchar_t *v12; // r11
  bool v13; // zf
  int v15[4]; // [rsp+A0h] [rbp-18h] BYREF
  va_list va; // [rsp+E8h] [rbp+30h] BYREF

  va_start(va, a5);
  v5 = a5;
  v15[0] = 2111;
  v7 = -1;
  do
    ++v7;
  while ( aDsSecurityProt[v7] );
  v8 = v7 + 1;
  v9 = 8;
  v10 = L"NULL";
  if ( a5 )
  {
    v11 = *a5;
    if ( *a5 )
    {
      v12 = (const wchar_t *)*((_QWORD *)a5 + 1);
      goto LABEL_8;
    }
  }
  else
  {
    v11 = 8;
  }
  v12 = L"NULL";
LABEL_8:
  if ( !a5 )
    v5 = L"\b";
  v13 = a4 == 0;
  if ( a4 )
  {
    v9 = *a4;
    if ( *a4 )
      v10 = (const wchar_t *)*((_QWORD *)a4 + 1);
    v13 = a4 == 0;
  }
  if ( v13 )
    a4 = L"\b";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
           0x74u,
           a4,
           2,
           v10,
           v9,
           v5,
           2,
           v12,
           v11,
           va,
           4,
           "ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
           v8,
           v15,
           4,
           0);
}

```

## disassembly

```asm
0x18002bf2c  mov     rax, rsp
0x18002bf2f  mov     [rax+8], rbx
0x18002bf33  mov     [rax+10h], rbp
0x18002bf37  mov     [rax+18h], rsi
0x18002bf3b  mov     [rax+20h], rdi
0x18002bf3f  push    r14
0x18002bf41  sub     rsp, 0B0h
0x18002bf48  mov     rdx, [rsp+0B8h+arg_20]
0x18002bf50  lea     r14, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002bf57  mov     dword ptr [rax-18h], 83Fh
0x18002bf5e  mov     rdi, rcx
0x18002bf61  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bf65  xor     esi, esi
0x18002bf67  inc     rax
0x18002bf6a  cmp     [r14+rax], sil
0x18002bf6e  jnz     short loc_18002BF67
0x18002bf70  lea     rbx, [rax+1]
0x18002bf74  mov     ecx, 8
0x18002bf79  lea     r10, aNull_0; "NULL"
0x18002bf80  test    rdx, rdx
0x18002bf83  jz      short loc_18002BF93
0x18002bf85  movzx   eax, word ptr [rdx]
0x18002bf88  cmp     [rdx], si
0x18002bf8b  jz      short loc_18002BF96
0x18002bf8d  mov     r11, [rdx+8]
0x18002bf91  jmp     short loc_18002BF99
0x18002bf93  mov     rax, rcx
0x18002bf96  mov     r11, r10
0x18002bf99  test    rdx, rdx
0x18002bf9c  lea     rbp, asc_1800348B4; "\b"
0x18002bfa3  cmovz   rdx, rbp
0x18002bfa7  test    r9, r9
0x18002bfaa  jz      short loc_18002BFBD
0x18002bfac  movzx   ecx, word ptr [r9]
0x18002bfb0  cmp     [r9], si
0x18002bfb4  jz      short loc_18002BFBA
0x18002bfb6  mov     r10, [r9+8]
0x18002bfba  test    r9, r9
0x18002bfbd  mov     [rsp+0B8h+var_28], rsi
0x18002bfc5  lea     r8, [rsp+0B8h+var_18]
0x18002bfcd  cmovz   r9, rbp
0x18002bfd1  mov     ebp, 74h ; 't'
0x18002bfd6  lea     esi, [rbp-70h]
0x18002bfd9  mov     [rsp+0B8h+var_30], rsi
0x18002bfe1  mov     [rsp+0B8h+var_38], r8
0x18002bfe9  lea     r8, [rsp+0B8h+arg_28]
0x18002bff1  mov     [rsp+0B8h+var_40], rbx
0x18002bff6  mov     [rsp+0B8h+var_48], r14
0x18002bffb  mov     [rsp+0B8h+var_50], rsi
0x18002c000  mov     [rsp+0B8h+var_58], r8
0x18002c005  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids; MessageGuid
0x18002c00c  mov     [rsp+0B8h+var_60], rax
0x18002c011  lea     eax, [rbp-72h]
0x18002c014  mov     [rsp+0B8h+var_68], r11
0x18002c019  mov     [rsp+0B8h+var_70], rax
0x18002c01e  mov     [rsp+0B8h+var_78], rdx
0x18002c023  lea     edx, [rbp-49h]; MessageFlags
0x18002c026  mov     [rsp+0B8h+var_80], rcx
0x18002c02b  mov     rcx, rdi; LoggerHandle
0x18002c02e  mov     [rsp+0B8h+var_88], r10
0x18002c033  mov     [rsp+0B8h+var_90], rax
0x18002c038  mov     [rsp+0B8h+var_98], r9
0x18002c03d  mov     r9d, ebp; MessageNumber
0x18002c040  call    cs:__imp_TraceMessage
0x18002c047  nop     dword ptr [rax+rax+00h]
0x18002c04c  lea     r11, [rsp+0B8h+var_8]
0x18002c054  mov     rbx, [r11+10h]
0x18002c058  mov     rbp, [r11+18h]
0x18002c05c  mov     rsi, [r11+20h]
0x18002c060  mov     rdi, [r11+28h]
0x18002c064  mov     rsp, r11
0x18002c067  pop     r14
0x18002c069  retn
```
