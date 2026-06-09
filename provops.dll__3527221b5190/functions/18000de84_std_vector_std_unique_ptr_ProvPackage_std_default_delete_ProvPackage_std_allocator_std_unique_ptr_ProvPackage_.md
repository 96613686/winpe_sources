# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::~vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>(void)

- ea: `0x18000de84`
- end: `0x18000def6`
- name: `??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(__int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f8d0`
- `0x180015f60`
- `0x180016840`
- `0x180023500`
- `0x180034a1e`
- `0x180034a66`
- `0x180034b50`
- `0x180034b74`
- `0x18003502a`
- `0x1800350e0`
- `0x1800361b4`

## callees

- `0x18000de84`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000dec9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dec9`

## pseudocode

```c
void __fastcall std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(__int64 a1)
{
  _QWORD *v1; // rdi
  _QWORD *v3; // rsi

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(_QWORD **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *v1 )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v1 + 64LL))(*v1, 1);
      ++v1;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000de84  mov     [rsp+arg_0], rbx
0x18000de89  mov     [rsp+arg_8], rsi
0x18000de8e  push    rdi
0x18000de8f  sub     rsp, 20h
0x18000de93  mov     rdi, [rcx]
0x18000de96  mov     rbx, rcx
0x18000de99  test    rdi, rdi
0x18000de9c  jz      short loc_18000DEE6
0x18000de9e  mov     rsi, [rcx+8]
0x18000dea2  jmp     short loc_18000DEC1
0x18000dea4  mov     rcx, [rdi]
0x18000dea7  test    rcx, rcx
0x18000deaa  jz      short loc_18000DEBD
0x18000deac  mov     rax, [rcx]
0x18000deaf  mov     edx, 1
0x18000deb4  mov     rax, [rax+40h]
0x18000deb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000debd  add     rdi, 8
0x18000dec1  cmp     rdi, rsi
0x18000dec4  jnz     short loc_18000DEA4
0x18000dec6  mov     rcx, [rbx]
0x18000dec9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000decf  mov     qword ptr [rbx], 0
0x18000ded6  mov     qword ptr [rbx+8], 0
0x18000dede  mov     qword ptr [rbx+10h], 0
0x18000dee6  mov     rbx, [rsp+28h+arg_0]
0x18000deeb  mov     rsi, [rsp+28h+arg_8]
0x18000def0  add     rsp, 20h
0x18000def4  pop     rdi
0x18000def5  retn
```
