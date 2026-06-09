# GameInputModule::GetSystemDirPath(ushort const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &,unsigned __int64 *)

- ea: `0x18006b4f8`
- end: `0x18006b673`
- name: `?GetSystemDirPath@GameInputModule@@CAJPEBGAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@PEA_K@Z`
- size: `379`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18006b278`
- `0x18006b374`

## callees

- `0x18002f9b4`
- `0x18006b4f8`
- `0x1800f089c`
- `0x1800f0a90`
- `0x1800f2478`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006b530`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006b5a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006b530`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006b5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b63c`

## pseudocode

```c
__int64 __fastcall GameInputModule::GetSystemDirPath(__int64 a1, const struct std::nothrow_t *a2, WCHAR *a3)
{
  void *v4; // rcx
  UINT SystemDirectoryW; // eax
  __int64 v7; // rbp
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  const struct std::nothrow_t *v14; // rdx
  unsigned __int64 v15; // rbx
  unsigned __int64 i; // rbp
  unsigned __int64 v17; // rbp
  void *v18; // rcx
  unsigned int v19; // ebx
  signed int LastError; // eax
  WCHAR *v21; // [rsp+60h] [rbp+18h] BYREF

  v21 = a3;
  v4 = *(void **)a2;
  *(_QWORD *)a2 = 0;
  if ( v4 )
    operator delete(v4, a2);
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v7 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    goto LABEL_28;
  if ( a1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a1 + 2 * v8) );
  }
  else
  {
    v8 = 0;
  }
  v9 = v8 + SystemDirectoryW + 1LL;
  if ( !a1 )
    v9 = SystemDirectoryW;
  v10 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v10 = -1;
  v11 = (WCHAR *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v11;
  v12 = v11;
  if ( !v11 )
    return 2147942414LL;
  v15 = GetSystemDirectoryW(v11, v9);
  if ( v15 == v7 - 1 )
  {
    for ( i = 0; i < v15; ++i )
      v12[i] = o_towlower_0(v12[i]);
    if ( a1 )
    {
      v12[v15] = 92;
      v17 = 0;
      ++v15;
      if ( v8 )
      {
        do
          v12[v15++] = o_towlower_0(*(unsigned __int16 *)(a1 + 2 * v17++));
        while ( v17 < v8 );
      }
    }
    v12[v15] = 0;
    v18 = *(void **)a2;
    v21 = 0;
    *(_QWORD *)a2 = v12;
    if ( v18 )
      operator delete(v18, v14);
    v19 = 0;
    goto LABEL_26;
  }
  if ( !v15 )
  {
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v21);
LABEL_28:
    LastError = GetLastError();
    v19 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147418113;
    }
    return v19;
  }
  v19 = -2147418113;
LABEL_26:
  VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v21);
  return v19;
}

```

## disassembly

```asm
0x18006b4f8  mov     [rsp+arg_0], rbx
0x18006b4fd  mov     [rsp+arg_8], rbp
0x18006b502  mov     [rsp+arg_10], r8
0x18006b507  push    rsi
0x18006b508  push    rdi
0x18006b509  push    r12
0x18006b50b  push    r14
0x18006b50d  push    r15
0x18006b50f  sub     rsp, 20h
0x18006b513  xor     r12d, r12d
0x18006b516  mov     r14, rcx
0x18006b519  mov     rcx, [rdx]; void *
0x18006b51c  mov     r15, rdx
0x18006b51f  mov     [rdx], r12
0x18006b522  test    rcx, rcx
0x18006b525  jz      short loc_18006B52C
0x18006b527  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b52c  xor     edx, edx; uSize
0x18006b52e  xor     ecx, ecx; lpBuffer
0x18006b530  call    cs:__imp_GetSystemDirectoryW
0x18006b536  mov     ebp, eax
0x18006b538  test    eax, eax
0x18006b53a  jz      loc_18006B63C
0x18006b540  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006b544  test    r14, r14
0x18006b547  jz      short loc_18006B558
0x18006b549  mov     rsi, rcx
0x18006b54c  inc     rsi
0x18006b54f  cmp     [r14+rsi*2], r12w
0x18006b554  jnz     short loc_18006B54C
0x18006b556  jmp     short loc_18006B55B
0x18006b558  mov     rsi, r12
0x18006b55b  lea     rbx, [rbp+1]
0x18006b55f  mov     eax, 2
0x18006b564  add     rbx, rsi
0x18006b567  test    r14, r14
0x18006b56a  cmovz   rbx, rbp
0x18006b56e  mul     rbx
0x18006b571  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006b578  cmovb   rax, rcx
0x18006b57c  mov     rcx, rax; unsigned __int64
0x18006b57f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006b584  mov     [rsp+48h+arg_10], rax
0x18006b589  mov     rdi, rax
0x18006b58c  test    rax, rax
0x18006b58f  jnz     short loc_18006B59B
0x18006b591  mov     eax, 8007000Eh
0x18006b596  jmp     loc_18006B65C
0x18006b59b  mov     edx, ebx; uSize
0x18006b59d  mov     rcx, rdi; lpBuffer
0x18006b5a0  call    cs:__imp_GetSystemDirectoryW
0x18006b5a6  mov     ebx, eax
0x18006b5a8  lea     rax, [rbp-1]
0x18006b5ac  cmp     rbx, rax
0x18006b5af  jnz     short loc_18006B61C
0x18006b5b1  mov     rbp, r12
0x18006b5b4  test    rbx, rbx
0x18006b5b7  jz      short loc_18006B5CE
0x18006b5b9  movzx   ecx, word ptr [rdi+rbp*2]
0x18006b5bd  call    _o_towlower_0
0x18006b5c2  mov     [rdi+rbp*2], ax
0x18006b5c6  inc     rbp
0x18006b5c9  cmp     rbp, rbx
0x18006b5cc  jb      short loc_18006B5B9
0x18006b5ce  test    r14, r14
0x18006b5d1  jz      short loc_18006B5FD
0x18006b5d3  mov     word ptr [rdi+rbx*2], 5Ch ; '\'
0x18006b5d9  mov     rbp, r12
0x18006b5dc  inc     rbx
0x18006b5df  test    rsi, rsi
0x18006b5e2  jz      short loc_18006B5FD
0x18006b5e4  movzx   ecx, word ptr [r14+rbp*2]
0x18006b5e9  call    _o_towlower_0
0x18006b5ee  mov     [rdi+rbx*2], ax
0x18006b5f2  inc     rbp
0x18006b5f5  inc     rbx
0x18006b5f8  cmp     rbp, rsi
0x18006b5fb  jb      short loc_18006B5E4
0x18006b5fd  mov     [rdi+rbx*2], r12w
0x18006b602  mov     rcx, [r15]; void *
0x18006b605  mov     [rsp+48h+arg_10], r12
0x18006b60a  mov     [r15], rdi
0x18006b60d  test    rcx, rcx
0x18006b610  jz      short loc_18006B617
0x18006b612  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b617  mov     ebx, r12d
0x18006b61a  jmp     short loc_18006B626
0x18006b61c  test    rbx, rbx
0x18006b61f  jz      short loc_18006B632
0x18006b621  mov     ebx, 8000FFFFh
0x18006b626  lea     rcx, [rsp+48h+arg_10]
0x18006b62b  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x18006b630  jmp     short loc_18006B65A
0x18006b632  lea     rcx, [rsp+48h+arg_10]
0x18006b637  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x18006b63c  call    cs:__imp_GetLastError
0x18006b642  mov     ebx, eax
0x18006b644  test    eax, eax
0x18006b646  jnz     short loc_18006B64F
0x18006b648  mov     ebx, 8000FFFFh
0x18006b64d  jmp     short loc_18006B65A
0x18006b64f  jle     short loc_18006B65A
0x18006b651  movzx   ebx, ax
0x18006b654  or      ebx, 80070000h
0x18006b65a  mov     eax, ebx
0x18006b65c  mov     rbx, [rsp+48h+arg_0]
0x18006b661  mov     rbp, [rsp+48h+arg_8]
0x18006b666  add     rsp, 20h
0x18006b66a  pop     r15
0x18006b66c  pop     r14
0x18006b66e  pop     r12
0x18006b670  pop     rdi
0x18006b671  pop     rsi
0x18006b672  retn
```
