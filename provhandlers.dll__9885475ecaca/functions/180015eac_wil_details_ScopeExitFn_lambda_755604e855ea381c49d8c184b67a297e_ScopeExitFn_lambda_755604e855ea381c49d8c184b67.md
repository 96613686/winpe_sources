# wil::details::ScopeExitFn__lambda_755604e855ea381c49d8c184b67a297e___::_ScopeExitFn__lambda_755604e855ea381c49d8c184b67a297e___

- ea: `0x180015eac`
- end: `0x180015f0a`
- name: `wil::details::ScopeExitFn__lambda_755604e855ea381c49d8c184b67a297e___::_ScopeExitFn__lambda_755604e855ea381c49d8c184b67a297e___`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003cb39`

## callees

- `0x180015eac`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015ef8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ScopeExitFn__lambda_755604e855ea381c49d8c184b67a297e___::_ScopeExitFn__lambda_755604e855ea381c49d8c184b67a297e___(
        __int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rcx

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    for ( i = 0; (unsigned int)i < **(_DWORD **)(a1 + 8); i = (unsigned int)(i + 1) )
    {
      v3 = *(_QWORD *)(**(_QWORD **)a1 + 8 * i);
      if ( v3 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
    CoTaskMemFree(**(LPVOID **)a1);
  }
}

```

## disassembly

```asm
0x180015eac  mov     [rsp+arg_0], rbx
0x180015eb1  push    rdi
0x180015eb2  sub     rsp, 20h
0x180015eb6  mov     rbx, rcx
0x180015eb9  cmp     byte ptr [rcx+10h], 0
0x180015ebd  jz      short loc_180015EFF
0x180015ebf  mov     byte ptr [rcx+10h], 0
0x180015ec3  xor     edi, edi
0x180015ec5  mov     rax, [rcx+8]
0x180015ec9  cmp     [rax], edi
0x180015ecb  jbe     short loc_180015EF2
0x180015ecd  mov     rax, [rbx]
0x180015ed0  mov     rcx, [rax]
0x180015ed3  mov     rcx, [rcx+rdi*8]
0x180015ed7  test    rcx, rcx
0x180015eda  jz      short loc_180015EE8
0x180015edc  mov     rax, [rcx]
0x180015edf  mov     rax, [rax+10h]
0x180015ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ee8  inc     edi
0x180015eea  mov     rax, [rbx+8]
0x180015eee  cmp     edi, [rax]
0x180015ef0  jb      short loc_180015ECD
0x180015ef2  mov     rcx, [rbx]
0x180015ef5  mov     rcx, [rcx]; pv
0x180015ef8  call    cs:__imp_CoTaskMemFree
0x180015efe  nop
0x180015eff  mov     rbx, [rsp+28h+arg_0]
0x180015f04  add     rsp, 20h
0x180015f08  pop     rdi
0x180015f09  retn
```
