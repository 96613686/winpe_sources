# ATL::CComObject<CWFPClientsHelperClass>::Release(void)

- ea: `0x180009de0`
- end: `0x180009e61`
- name: `?Release@?$CComObject@VCWFPClientsHelperClass@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009e70`

## callees

- `0x180009de0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWFPClientsHelperClass>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 4);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 4, i - 1, i);
        i = *((_DWORD *)a1 + 4) )
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
0x180009de0  mov     [rsp+arg_0], rbx
0x180009de5  push    rdi
0x180009de6  sub     rsp, 20h
0x180009dea  mov     r8d, [rcx+10h]
0x180009dee  mov     rbx, rcx
0x180009df1  mov     ecx, 7FFFFFFFh
0x180009df6  jmp     short loc_180009E0A
0x180009df8  lea     edx, [r8-1]
0x180009dfc  mov     eax, r8d
0x180009dff  lock cmpxchg [rbx+10h], edx
0x180009e04  jz      short loc_180009E0F
0x180009e06  mov     r8d, [rbx+10h]
0x180009e0a  cmp     r8d, ecx
0x180009e0d  jnz     short loc_180009DF8
0x180009e0f  lea     edi, [r8-1]
0x180009e13  test    edi, edi
0x180009e15  jnz     short loc_180009E54
0x180009e17  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009e1e  mov     rax, [rcx]
0x180009e21  mov     rax, [rax+8]
0x180009e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e2a  test    rbx, rbx
0x180009e2d  jz      short loc_180009E41
0x180009e2f  mov     rax, [rbx]
0x180009e32  lea     edx, [rdi+1]
0x180009e35  mov     rcx, rbx
0x180009e38  mov     rax, [rax+20h]
0x180009e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e41  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009e48  mov     rdx, [rcx]
0x180009e4b  mov     rax, [rdx+10h]
0x180009e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e54  mov     rbx, [rsp+28h+arg_0]
0x180009e59  mov     eax, edi
0x180009e5b  add     rsp, 20h
0x180009e5f  pop     rdi
0x180009e60  retn
```
