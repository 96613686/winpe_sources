# CLRConfig::TrimWhiteSpace(ushort const *,ushort * *)

- ea: `0x14000a844`
- end: `0x14000a991`
- name: `?TrimWhiteSpace@CLRConfig@@CAJPEBGPEAPEAG@Z`
- size: `333`
- prototype: `__int64 __fastcall(wint_t *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x14000a610`

## callees

- `0x14000a0d4`
- `0x14000a10c`
- `0x14000a844`

## import_xrefs

- `ucrtbase_clr0400!iswspace` at `0x14000a89f`
- `ucrtbase_clr0400!iswspace` at `0x14000a8b7`
- `ucrtbase_clr0400!iswspace` at `0x14000a89f`
- `ucrtbase_clr0400!iswspace` at `0x14000a8b7`
- `ucrtbase_clr0400!wcsncpy_s` at `0x14000a93b`
- `ucrtbase_clr0400!wcsncpy_s` at `0x14000a93b`

## pseudocode

```c
__int64 __fastcall CLRConfig::TrimWhiteSpace(wint_t *a1, unsigned __int16 **a2)
{
  __int64 v4; // rsi
  unsigned int v5; // ebx
  wint_t *v7; // rdi
  wint_t *v8; // r15
  unsigned __int128 v9; // rax
  wchar_t *v10; // rax
  unsigned __int16 *v11; // rsi
  int v12; // ecx
  unsigned int v13; // ebx

  *a2 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v5 = v4;
  if ( v4 != (unsigned int)v4 )
    return 2148734230LL;
  v7 = a1;
  v8 = &a1[(unsigned int)(v4 - 1)];
  if ( !(_DWORD)v4 )
    goto LABEL_12;
  while ( iswspace(*v7) )
  {
    ++v7;
    if ( !--v5 )
      goto LABEL_11;
  }
  do
  {
    if ( !iswspace(*v8) )
      break;
    --v8;
    --v5;
  }
  while ( v5 );
LABEL_11:
  if ( a1 == v7 )
  {
LABEL_12:
    if ( v4 == v5 )
      return 0;
  }
  if ( !v5 )
    return 0;
  v9 = (v5 + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v5 + 1, 2u) )
    *(_QWORD *)&v9 = -1;
  v10 = (wchar_t *)operator new[](v9, *((const struct NoThrow **)&v9 + 1));
  v11 = v10;
  v12 = 0;
  if ( v10 )
  {
    if ( wcsncpy_s(v10, v5 + 1, v7, v5) )
    {
      v13 = -2147467259;
      v12 = 1;
    }
    else
    {
      *a2 = v11;
      v13 = 0;
      v12 = 0;
    }
  }
  else
  {
    v13 = -2147024882;
  }
  if ( v12 )
    operator delete(v11);
  return v13;
}

```

## disassembly

```asm
0x14000a844  mov     [rsp+arg_0], rbx
0x14000a849  mov     [rsp+arg_8], rbp
0x14000a84e  mov     [rsp+arg_10], rsi
0x14000a853  push    rdi
0x14000a854  push    r12
0x14000a856  push    r13
0x14000a858  push    r14
0x14000a85a  push    r15
0x14000a85c  sub     rsp, 30h
0x14000a860  mov     r12, rdx
0x14000a863  mov     r14, rcx
0x14000a866  xor     r13d, r13d
0x14000a869  mov     [rdx], r13
0x14000a86c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000a870  inc     rsi
0x14000a873  cmp     [rcx+rsi*2], r13w
0x14000a878  jnz     short loc_14000A870
0x14000a87a  mov     ebx, esi
0x14000a87c  cmp     rsi, rbx
0x14000a87f  jz      short loc_14000A88B
0x14000a881  mov     eax, 80131516h
0x14000a886  jmp     loc_14000A974
0x14000a88b  mov     rdi, r14
0x14000a88e  lea     eax, [rbx-1]
0x14000a891  lea     r15, [rcx+rax*2]
0x14000a895  test    esi, esi
0x14000a897  jz      short loc_14000A8CE
0x14000a899  or      ebp, 0FFFFFFFFh
0x14000a89c  movzx   ecx, word ptr [rdi]; C
0x14000a89f  call    cs:__imp_iswspace
0x14000a8a5  test    eax, eax
0x14000a8a7  jz      short loc_14000A8B3
0x14000a8a9  add     rdi, 2
0x14000a8ad  add     ebx, ebp
0x14000a8af  jnz     short loc_14000A89C
0x14000a8b1  jmp     short loc_14000A8C9
0x14000a8b3  movzx   ecx, word ptr [r15]; C
0x14000a8b7  call    cs:__imp_iswspace
0x14000a8bd  test    eax, eax
0x14000a8bf  jz      short loc_14000A8C9
0x14000a8c1  sub     r15, 2
0x14000a8c5  add     ebx, ebp
0x14000a8c7  jnz     short loc_14000A8B3
0x14000a8c9  cmp     r14, rdi
0x14000a8cc  jnz     short loc_14000A8D9
0x14000a8ce  mov     ecx, ebx
0x14000a8d0  cmp     rsi, rcx
0x14000a8d3  jz      loc_14000A972
0x14000a8d9  test    ebx, ebx
0x14000a8db  jz      loc_14000A972
0x14000a8e1  lea     r14d, [rbx+1]
0x14000a8e5  mov     eax, 2
0x14000a8ea  mul     r14
0x14000a8ed  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a8f4  cmovo   rax, rcx
0x14000a8f8  mov     rcx, rax; dwBytes
0x14000a8fb  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x14000a900  mov     rsi, rax
0x14000a903  mov     [rsp+58h+var_38], rax
0x14000a908  mov     [rsp+58h+var_30], r13d
0x14000a90d  mov     ecx, r13d
0x14000a910  mov     ebp, r13d
0x14000a913  test    rax, rax
0x14000a916  jz      short loc_14000A923
0x14000a918  mov     ecx, 1
0x14000a91d  mov     [rsp+58h+var_30], ecx
0x14000a921  mov     ebp, ecx
0x14000a923  test    rsi, rsi
0x14000a926  jnz     short loc_14000A92F
0x14000a928  mov     ebx, 8007000Eh
0x14000a92d  jmp     short loc_14000A95D
0x14000a92f  mov     r9d, ebx; MaxCount
0x14000a932  mov     r8, rdi; Source
0x14000a935  mov     rdx, r14; SizeInWords
0x14000a938  mov     rcx, rsi; Destination
0x14000a93b  call    cs:__imp_wcsncpy_s
0x14000a941  test    eax, eax
0x14000a943  jz      short loc_14000A94E
0x14000a945  mov     ebx, 80004005h
0x14000a94a  mov     ecx, ebp
0x14000a94c  jmp     short loc_14000A95D
0x14000a94e  mov     [rsp+58h+var_30], r13d
0x14000a953  mov     [r12], rsi
0x14000a957  mov     ebx, r13d
0x14000a95a  mov     ecx, r13d
0x14000a95d  test    ecx, ecx
0x14000a95f  jz      short loc_14000A96E
0x14000a961  mov     rcx, rsi; lpMem
0x14000a964  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a969  mov     [rsp+58h+var_30], r13d
0x14000a96e  mov     eax, ebx
0x14000a970  jmp     short loc_14000A974
0x14000a972  xor     eax, eax
0x14000a974  mov     rbx, [rsp+58h+arg_0]
0x14000a979  mov     rbp, [rsp+58h+arg_8]
0x14000a97e  mov     rsi, [rsp+58h+arg_10]
0x14000a983  add     rsp, 30h
0x14000a987  pop     r15
0x14000a989  pop     r14
0x14000a98b  pop     r13
0x14000a98d  pop     r12
0x14000a98f  pop     rdi
0x14000a990  retn
```
