# ATL::CComObject<CNDFHelperClassRegistry>::Release(void)

- ea: `0x180009a70`
- end: `0x180009af2`
- name: `?Release@?$CComObject@VCNDFHelperClassRegistry@@@ATL@@UEAAKXZ`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009a70`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CNDFHelperClassRegistry>::Release(volatile signed __int32 *a1)
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
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180009a70  mov     [rsp+arg_0], rbx
0x180009a75  push    rdi
0x180009a76  sub     rsp, 20h
0x180009a7a  mov     r8d, [rcx+8]
0x180009a7e  mov     rbx, rcx
0x180009a81  mov     ecx, 7FFFFFFFh
0x180009a86  jmp     short loc_180009A9A
0x180009a88  lea     edx, [r8-1]
0x180009a8c  mov     eax, r8d
0x180009a8f  lock cmpxchg [rbx+8], edx
0x180009a94  jz      short loc_180009A9F
0x180009a96  mov     r8d, [rbx+8]
0x180009a9a  cmp     r8d, ecx
0x180009a9d  jnz     short loc_180009A88
0x180009a9f  lea     edi, [r8-1]
0x180009aa3  test    edi, edi
0x180009aa5  jnz     short loc_180009AE4
0x180009aa7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009aae  mov     rax, [rcx]
0x180009ab1  mov     rax, [rax+8]
0x180009ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aba  test    rbx, rbx
0x180009abd  jz      short loc_180009AD1
0x180009abf  mov     rax, [rbx]
0x180009ac2  lea     edx, [rdi+1]
0x180009ac5  mov     rcx, rbx
0x180009ac8  mov     rax, [rax+48h]
0x180009acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ad1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009ad8  mov     rdx, [rcx]
0x180009adb  mov     rax, [rdx+10h]
0x180009adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae4  mov     rbx, [rsp+28h+arg_0]
0x180009ae9  mov     eax, edi
0x180009aeb  add     rsp, 20h
0x180009aef  pop     rdi
0x180009af0  retn
```
