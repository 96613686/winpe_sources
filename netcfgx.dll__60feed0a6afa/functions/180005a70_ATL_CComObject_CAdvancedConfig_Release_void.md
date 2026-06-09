# ATL::CComObject<CAdvancedConfig>::Release(void)

- ea: `0x180005a70`
- end: `0x180005af1`
- name: `?Release@?$CComObject@VCAdvancedConfig@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005a70`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAdvancedConfig>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005a70  mov     [rsp+arg_0], rbx
0x180005a75  push    rdi
0x180005a76  sub     rsp, 20h
0x180005a7a  mov     r8d, [rcx+8]
0x180005a7e  mov     rbx, rcx
0x180005a81  mov     ecx, 7FFFFFFFh
0x180005a86  jmp     short loc_180005A9A
0x180005a88  lea     edx, [r8-1]
0x180005a8c  mov     eax, r8d
0x180005a8f  lock cmpxchg [rbx+8], edx
0x180005a94  jz      short loc_180005A9F
0x180005a96  mov     r8d, [rbx+8]
0x180005a9a  cmp     r8d, ecx
0x180005a9d  jnz     short loc_180005A88
0x180005a9f  lea     edi, [r8-1]
0x180005aa3  test    edi, edi
0x180005aa5  jnz     short loc_180005AE4
0x180005aa7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005aae  mov     rax, [rcx]
0x180005ab1  mov     rax, [rax+8]
0x180005ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aba  test    rbx, rbx
0x180005abd  jz      short loc_180005AD1
0x180005abf  mov     rax, [rbx]
0x180005ac2  lea     edx, [rdi+1]
0x180005ac5  mov     rcx, rbx
0x180005ac8  mov     rax, [rax+20h]
0x180005acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005ad8  mov     rdx, [rcx]
0x180005adb  mov     rax, [rdx+10h]
0x180005adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae4  mov     rbx, [rsp+28h+arg_0]
0x180005ae9  mov     eax, edi
0x180005aeb  add     rsp, 20h
0x180005aef  pop     rdi
0x180005af0  retn
```
