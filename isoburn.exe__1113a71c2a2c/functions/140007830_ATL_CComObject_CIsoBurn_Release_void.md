# ATL::CComObject<CIsoBurn>::Release(void)

- ea: `0x140007830`
- end: `0x1400078b1`
- name: `?Release@?$CComObject@VCIsoBurn@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400078c0`
- `0x1400078d0`

## callees

- `0x140007830`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurn>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 16);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 16, i - 1, i);
        i = *((_DWORD *)a1 + 16) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x140007830  mov     [rsp+arg_0], rbx
0x140007835  push    rdi
0x140007836  sub     rsp, 20h
0x14000783a  mov     r8d, [rcx+40h]
0x14000783e  mov     rbx, rcx
0x140007841  mov     ecx, 7FFFFFFFh
0x140007846  jmp     short loc_14000785A
0x140007848  lea     edx, [r8-1]
0x14000784c  mov     eax, r8d
0x14000784f  lock cmpxchg [rbx+40h], edx
0x140007854  jz      short loc_14000785F
0x140007856  mov     r8d, [rbx+40h]
0x14000785a  cmp     r8d, ecx
0x14000785d  jnz     short loc_140007848
0x14000785f  lea     edi, [r8-1]
0x140007863  test    edi, edi
0x140007865  jnz     short loc_1400078A4
0x140007867  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000786e  mov     rax, [rcx]
0x140007871  mov     rax, [rax+8]
0x140007875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000787a  test    rbx, rbx
0x14000787d  jz      short loc_140007891
0x14000787f  mov     rax, [rbx]
0x140007882  lea     edx, [rdi+1]
0x140007885  mov     rcx, rbx
0x140007888  mov     rax, [rax+40h]
0x14000788c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007891  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140007898  mov     rdx, [rcx]
0x14000789b  mov     rax, [rdx+10h]
0x14000789f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078a4  mov     rbx, [rsp+28h+arg_0]
0x1400078a9  mov     eax, edi
0x1400078ab  add     rsp, 20h
0x1400078af  pop     rdi
0x1400078b0  retn
```
