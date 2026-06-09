# CAdvancedSettingsWriter_CreateInstance

- ea: `0x180015d10`
- end: `0x180015db2`
- name: `CAdvancedSettingsWriter_CreateInstance`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000766c`
- `0x180015d10`
- `0x18001a010`

## pseudocode

```c
__int64 __fastcall CAdvancedSettingsWriter_CreateInstance(__int64 a1, unsigned __int64 a2, _QWORD *a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // edi

  *a3 = 0;
  v5 = DirectUI::HAllocAndZero((DirectUI *)0x78, a2);
  v6 = v5;
  if ( v5 )
  {
    *((_DWORD *)v5 + 2) = 1;
    *v5 = &CAdvancedSettingsWriter::`vftable';
    _InterlockedIncrement(&g_cLocks);
    v7 = 0;
    v6[2] = 0;
    do
    {
      HIDWORD(v6[v7 + 3]) = -1;
      LODWORD(v6[v7++ + 3]) = -1;
    }
    while ( v7 != 12 );
    v8 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int64, _QWORD *))*v6)(v6, a2, a3);
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x180015d10  mov     [rsp+arg_0], rbx
0x180015d15  mov     [rsp+arg_8], rsi
0x180015d1a  push    rdi
0x180015d1b  sub     rsp, 20h
0x180015d1f  mov     ecx, 78h ; 'x'; this
0x180015d24  mov     qword ptr [r8], 0
0x180015d2b  mov     rdi, r8
0x180015d2e  mov     rsi, rdx
0x180015d31  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180015d36  mov     rbx, rax
0x180015d39  test    rax, rax
0x180015d3c  jz      short loc_180015D9B
0x180015d3e  lea     rax, ??_7CAdvancedSettingsWriter@@6B@; const CAdvancedSettingsWriter::`vftable'
0x180015d45  mov     dword ptr [rbx+8], 1
0x180015d4c  mov     [rbx], rax
0x180015d4f  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180015d56  xor     eax, eax
0x180015d58  mov     qword ptr [rbx+10h], 0
0x180015d60  or      ecx, 0FFFFFFFFh
0x180015d63  mov     [rbx+rax*8+1Ch], ecx
0x180015d67  mov     [rbx+rax*8+18h], ecx
0x180015d6b  inc     rax
0x180015d6e  cmp     rax, 0Ch
0x180015d72  jnz     short loc_180015D63
0x180015d74  mov     rax, [rbx]
0x180015d77  mov     r8, rdi
0x180015d7a  mov     rdx, rsi
0x180015d7d  mov     rcx, rbx
0x180015d80  mov     rax, [rax]
0x180015d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d88  mov     rcx, [rbx]
0x180015d8b  mov     edi, eax
0x180015d8d  mov     rax, [rcx+10h]
0x180015d91  mov     rcx, rbx
0x180015d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d99  jmp     short loc_180015DA0
0x180015d9b  mov     edi, 8007000Eh
0x180015da0  mov     rbx, [rsp+28h+arg_0]
0x180015da5  mov     eax, edi
0x180015da7  mov     rsi, [rsp+28h+arg_8]
0x180015dac  add     rsp, 20h
0x180015db0  pop     rdi
0x180015db1  retn
```
