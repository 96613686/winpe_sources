# CopyPolicyServerContext(_CRYPTUI_POLICY_SERVER_CONTEXT const *,_CRYPTUI_POLICY_SERVER_CONTEXT * *)

- ea: `0x18002b79c`
- end: `0x18002b8bc`
- name: `?CopyPolicyServerContext@@YAHPEBU_CRYPTUI_POLICY_SERVER_CONTEXT@@PEAPEAU1@@Z`
- size: `288`
- prototype: `__int64 __fastcall(const struct _CRYPTUI_POLICY_SERVER_CONTEXT *, struct _CRYPTUI_POLICY_SERVER_CONTEXT **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002bb10`
- `0x18002c0f0`
- `0x18002c8b0`

## callees

- `0x1800059ec`
- `0x18002b79c`
- `0x18002b984`
- `0x18002b9e4`
- `0x18002c090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b8a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b8a7`

## pseudocode

```c
__int64 __fastcall CopyPolicyServerContext(
        const struct _CRYPTUI_POLICY_SERVER_CONTEXT *a1,
        struct _CRYPTUI_POLICY_SERVER_CONTEXT **a2)
{
  struct _CRYPTUI_POLICY_SERVER_CONTEXT *v4; // rax
  DWORD v5; // ecx
  char v6; // r14
  unsigned int v7; // edi
  unsigned __int16 *v8; // rcx
  unsigned __int16 *v9; // rcx
  char v10; // bp
  unsigned __int16 *v11; // rcx
  char v12; // al
  _DWORD *v13; // rcx

  if ( !a1 || !a2 )
  {
    SelDbgError(0x172u);
    v5 = -2147024809;
    goto LABEL_19;
  }
  *a2 = 0;
  v4 = (struct _CRYPTUI_POLICY_SERVER_CONTEXT *)SelDbgWizardAlloc(0x20u, 0x177u);
  *a2 = v4;
  if ( !v4 )
  {
    SelDbgError(0x17Bu);
    v5 = -2147024882;
LABEL_19:
    SetLastError(v5);
    return 0;
  }
  v6 = 0;
  *(_QWORD *)v4 = 0;
  v7 = 1;
  *(_DWORD *)*a2 = 8;
  v8 = (unsigned __int16 *)*((_QWORD *)a1 + 3);
  if ( v8 )
  {
    v6 = 1;
    *((_QWORD *)*a2 + 3) = LocalAllocAndCopyWStr(v8);
  }
  v9 = (unsigned __int16 *)*((_QWORD *)a1 + 2);
  v10 = 0;
  if ( v9 )
  {
    v10 = 1;
    *((_QWORD *)*a2 + 2) = LocalAllocAndCopyWStr(v9);
  }
  v11 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
  v12 = 0;
  if ( v11 )
  {
    *((_QWORD *)*a2 + 1) = LocalAllocAndCopyWStr(v11);
    v12 = 1;
  }
  if ( v6 && (v13 = *a2, !*((_QWORD *)*a2 + 3))
    || v10 && (v13 = *a2, !*((_QWORD *)*a2 + 2))
    || v12 && (v13 = *a2, !*((_QWORD *)*a2 + 1)) )
  {
    CryptUIDlgFreePolicyServerContext(v13);
    *a2 = 0;
    SelDbgError(0x1A1u);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18002b79c  push    rbx
0x18002b79e  push    rbp
0x18002b79f  push    rsi
0x18002b7a0  push    rdi
0x18002b7a1  push    r14
0x18002b7a3  sub     rsp, 20h
0x18002b7a7  mov     rbx, rdx
0x18002b7aa  mov     rsi, rcx
0x18002b7ad  test    rcx, rcx
0x18002b7b0  jz      loc_18002B898
0x18002b7b6  test    rdx, rdx
0x18002b7b9  jz      loc_18002B898
0x18002b7bf  mov     qword ptr [rdx], 0
0x18002b7c6  mov     ecx, 20h ; ' '; uBytes
0x18002b7cb  mov     edx, 177h; unsigned int
0x18002b7d0  call    ?SelDbgWizardAlloc@@YAPEAXKK@Z; SelDbgWizardAlloc(ulong,ulong)
0x18002b7d5  mov     [rbx], rax
0x18002b7d8  test    rax, rax
0x18002b7db  jnz     short loc_18002B7F1
0x18002b7dd  mov     ecx, 17Bh; unsigned int
0x18002b7e2  call    ?SelDbgError@@YAXK@Z; SelDbgError(ulong)
0x18002b7e7  mov     ecx, 8007000Eh
0x18002b7ec  jmp     loc_18002B8A7
0x18002b7f1  xor     ecx, ecx
0x18002b7f3  xor     r14b, r14b
0x18002b7f6  mov     [rax], rcx
0x18002b7f9  mov     edi, 1
0x18002b7fe  mov     rax, [rbx]
0x18002b801  mov     dword ptr [rax], 8
0x18002b807  mov     rcx, [rsi+18h]; Src
0x18002b80b  test    rcx, rcx
0x18002b80e  jz      short loc_18002B81F
0x18002b810  call    ?LocalAllocAndCopyWStr@@YAPEAGPEAG@Z; LocalAllocAndCopyWStr(ushort *)
0x18002b815  mov     rcx, [rbx]
0x18002b818  mov     r14b, dil
0x18002b81b  mov     [rcx+18h], rax
0x18002b81f  mov     rcx, [rsi+10h]; Src
0x18002b823  xor     bpl, bpl
0x18002b826  test    rcx, rcx
0x18002b829  jz      short loc_18002B83A
0x18002b82b  call    ?LocalAllocAndCopyWStr@@YAPEAGPEAG@Z; LocalAllocAndCopyWStr(ushort *)
0x18002b830  mov     rcx, [rbx]
0x18002b833  mov     bpl, dil
0x18002b836  mov     [rcx+10h], rax
0x18002b83a  mov     rcx, [rsi+8]; Src
0x18002b83e  xor     al, al
0x18002b840  test    rcx, rcx
0x18002b843  jz      short loc_18002B854
0x18002b845  call    ?LocalAllocAndCopyWStr@@YAPEAGPEAG@Z; LocalAllocAndCopyWStr(ushort *)
0x18002b84a  mov     rcx, [rbx]
0x18002b84d  mov     [rcx+8], rax
0x18002b851  mov     al, dil
0x18002b854  test    r14b, r14b
0x18002b857  jz      short loc_18002B863
0x18002b859  mov     rcx, [rbx]
0x18002b85c  cmp     qword ptr [rcx+18h], 0
0x18002b861  jz      short loc_18002B880
0x18002b863  test    bpl, bpl
0x18002b866  jz      short loc_18002B872
0x18002b868  mov     rcx, [rbx]
0x18002b86b  cmp     qword ptr [rcx+10h], 0
0x18002b870  jz      short loc_18002B880
0x18002b872  test    al, al
0x18002b874  jz      short loc_18002B8AF
0x18002b876  mov     rcx, [rbx]; hMem
0x18002b879  cmp     qword ptr [rcx+8], 0
0x18002b87e  jnz     short loc_18002B8AF
0x18002b880  call    CryptUIDlgFreePolicyServerContext
0x18002b885  mov     ecx, 1A1h; unsigned int
0x18002b88a  mov     qword ptr [rbx], 0
0x18002b891  call    ?SelDbgError@@YAXK@Z; SelDbgError(ulong)
0x18002b896  jmp     short loc_18002B8AD
0x18002b898  mov     ecx, 172h; unsigned int
0x18002b89d  call    ?SelDbgError@@YAXK@Z; SelDbgError(ulong)
0x18002b8a2  mov     ecx, 80070057h; dwErrCode
0x18002b8a7  call    cs:__imp_SetLastError
0x18002b8ad  xor     edi, edi
0x18002b8af  mov     eax, edi
0x18002b8b1  add     rsp, 20h
0x18002b8b5  pop     r14
0x18002b8b7  pop     rdi
0x18002b8b8  pop     rsi
0x18002b8b9  pop     rbp
0x18002b8ba  pop     rbx
0x18002b8bb  retn
```
