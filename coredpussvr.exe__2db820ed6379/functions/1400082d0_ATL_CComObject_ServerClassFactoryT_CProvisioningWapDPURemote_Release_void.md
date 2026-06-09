# ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::Release(void)

- ea: `0x1400082d0`
- end: `0x140008352`
- name: `?Release@?$CComObject@V?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@@ATL@@UEAAKXZ`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400082d0`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::Release(
        volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1400082d0  mov     [rsp+arg_0], rbx
0x1400082d5  push    rdi
0x1400082d6  sub     rsp, 20h
0x1400082da  mov     r8d, [rcx+8]
0x1400082de  mov     rbx, rcx
0x1400082e1  mov     ecx, 7FFFFFFFh
0x1400082e6  jmp     short loc_1400082FA
0x1400082e8  lea     edx, [r8-1]
0x1400082ec  mov     eax, r8d
0x1400082ef  lock cmpxchg [rbx+8], edx
0x1400082f4  jz      short loc_1400082FF
0x1400082f6  mov     r8d, [rbx+8]
0x1400082fa  cmp     r8d, ecx
0x1400082fd  jnz     short loc_1400082E8
0x1400082ff  lea     edi, [r8-1]
0x140008303  test    edi, edi
0x140008305  jnz     short loc_140008344
0x140008307  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000830e  mov     rax, [rcx]
0x140008311  mov     rax, [rax+8]
0x140008315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000831a  test    rbx, rbx
0x14000831d  jz      short loc_140008331
0x14000831f  mov     rax, [rbx]
0x140008322  lea     edx, [rdi+1]
0x140008325  mov     rcx, rbx
0x140008328  mov     rax, [rax+28h]
0x14000832c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008331  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140008338  mov     rdx, [rcx]
0x14000833b  mov     rax, [rdx+10h]
0x14000833f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008344  mov     rbx, [rsp+28h+arg_0]
0x140008349  mov     eax, edi
0x14000834b  add     rsp, 20h
0x14000834f  pop     rdi
0x140008350  retn
```
