# ATL::CComObject<CDetectionAndSharing>::Release(void)

- ea: `0x1800023b0`
- end: `0x180002431`
- name: `?Release@?$CComObject@VCDetectionAndSharing@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800023b0`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDetectionAndSharing>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800023b0  mov     [rsp+arg_0], rbx
0x1800023b5  push    rdi
0x1800023b6  sub     rsp, 20h
0x1800023ba  mov     r8d, [rcx+8]
0x1800023be  mov     rbx, rcx
0x1800023c1  mov     ecx, 7FFFFFFFh
0x1800023c6  jmp     short loc_1800023DA
0x1800023c8  lea     edx, [r8-1]
0x1800023cc  mov     eax, r8d
0x1800023cf  lock cmpxchg [rbx+8], edx
0x1800023d4  jz      short loc_1800023DF
0x1800023d6  mov     r8d, [rbx+8]
0x1800023da  cmp     r8d, ecx
0x1800023dd  jnz     short loc_1800023C8
0x1800023df  lea     edi, [r8-1]
0x1800023e3  test    edi, edi
0x1800023e5  jnz     short loc_180002424
0x1800023e7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800023ee  mov     rax, [rcx]
0x1800023f1  mov     rax, [rax+8]
0x1800023f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023fa  test    rbx, rbx
0x1800023fd  jz      short loc_180002411
0x1800023ff  mov     rax, [rbx]
0x180002402  lea     edx, [rdi+1]
0x180002405  mov     rcx, rbx
0x180002408  mov     rax, [rax+40h]
0x18000240c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002411  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002418  mov     rdx, [rcx]
0x18000241b  mov     rax, [rdx+10h]
0x18000241f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002424  mov     rbx, [rsp+28h+arg_0]
0x180002429  mov     eax, edi
0x18000242b  add     rsp, 20h
0x18000242f  pop     rdi
0x180002430  retn
```
