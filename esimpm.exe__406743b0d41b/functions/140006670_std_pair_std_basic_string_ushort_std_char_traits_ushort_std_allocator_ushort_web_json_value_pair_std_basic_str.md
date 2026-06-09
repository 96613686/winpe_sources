# std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>::~pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>(void)

- ea: `0x140006670`
- end: `0x1400066a3`
- name: `??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@QEAA@XZ`
- size: `51`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14003be20`
- `0x14003be60`
- `0x14003be80`
- `0x14003bf40`

## callees

- `0x140006670`
- `0x140013df8`
- `0x14003e010`

## pseudocode

```c
__int64 __fastcall std::pair<std::wstring,web::json::value>::~pair<std::wstring,web::json::value>(__int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 32);
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 192LL))(v2, 1);
  return std::wstring::_Tidy_deallocate(a1);
}

```

## disassembly

```asm
0x140006670  push    rbx
0x140006672  sub     rsp, 20h
0x140006676  mov     rbx, rcx
0x140006679  mov     rcx, [rcx+20h]
0x14000667d  test    rcx, rcx
0x140006680  jz      short loc_140006696
0x140006682  mov     rax, [rcx]
0x140006685  mov     edx, 1
0x14000668a  mov     rax, [rax+0C0h]
0x140006691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006696  mov     rcx, rbx
0x140006699  add     rsp, 20h
0x14000669d  pop     rbx
0x14000669e  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
