# ActiveScriptError::FreeStackTrace(CallStack &)

- ea: `0x1801d4a70`
- end: `0x1801d4afb`
- name: `?FreeStackTrace@ActiveScriptError@@AEAAXAEAUCallStack@@@Z`
- size: `139`
- prototype: `void __fastcall(ActiveScriptError *__hidden this, struct CallStack *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1801d492c`

## callees

- `0x1801d4a70`
- `0x180364010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d4aba`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d4ad4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d4aba`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d4ad4`

## pseudocode

```c
void __fastcall ActiveScriptError::FreeStackTrace(ActiveScriptError *this, struct CallStack *a2)
{
  unsigned int v2; // esi
  LPVOID *i; // rbx
  __int64 v5; // rbp
  __int64 v6; // rcx

  v2 = 0;
  for ( i = (LPVOID *)((char *)a2 + 8); v2 < *(_DWORD *)a2; ++v2 )
  {
    v5 = 32LL * v2;
    v6 = *(_QWORD *)((char *)*i + v5 + 24);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    CoTaskMemFree(*(LPVOID *)((char *)*i + v5 + 8));
  }
  if ( *i )
    CoTaskMemFree(*i);
  *i = 0;
  *(_DWORD *)a2 = 0;
}

```

## disassembly

```asm
0x1801d4a70  mov     rax, rsp
0x1801d4a73  mov     [rax+18h], rbx
0x1801d4a77  mov     [rax+10h], rdx
0x1801d4a7b  mov     [rax+8], rcx
0x1801d4a7f  push    rbp
0x1801d4a80  push    rsi
0x1801d4a81  push    rdi
0x1801d4a82  sub     rsp, 20h
0x1801d4a86  xor     esi, esi
0x1801d4a88  lea     rbx, [rdx+8]
0x1801d4a8c  mov     rdi, rdx
0x1801d4a8f  cmp     [rdx], esi
0x1801d4a91  jbe     short loc_1801D4ACC
0x1801d4a93  mov     rax, [rbx]
0x1801d4a96  mov     ebp, esi
0x1801d4a98  shl     rbp, 5
0x1801d4a9c  mov     rcx, [rax+rbp+18h]
0x1801d4aa1  test    rcx, rcx
0x1801d4aa4  jz      short loc_1801D4AB2
0x1801d4aa6  mov     rax, [rcx]
0x1801d4aa9  mov     rax, [rax+10h]
0x1801d4aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d4ab2  mov     rcx, [rbx]
0x1801d4ab5  mov     rcx, [rcx+rbp+8]; pv
0x1801d4aba  call    cs:__imp_CoTaskMemFree
0x1801d4ac1  nop     dword ptr [rax+rax+00h]
0x1801d4ac6  inc     esi
0x1801d4ac8  cmp     esi, [rdi]
0x1801d4aca  jb      short loc_1801D4A93
0x1801d4acc  mov     rcx, [rbx]; pv
0x1801d4acf  test    rcx, rcx
0x1801d4ad2  jz      short loc_1801D4AE0
0x1801d4ad4  call    cs:__imp_CoTaskMemFree
0x1801d4adb  nop     dword ptr [rax+rax+00h]
0x1801d4ae0  mov     qword ptr [rbx], 0
0x1801d4ae7  mov     rbx, [rsp+38h+arg_10]
0x1801d4aec  mov     dword ptr [rdi], 0
0x1801d4af2  add     rsp, 20h
0x1801d4af6  pop     rdi
0x1801d4af7  pop     rsi
0x1801d4af8  pop     rbp
0x1801d4af9  retn
```
