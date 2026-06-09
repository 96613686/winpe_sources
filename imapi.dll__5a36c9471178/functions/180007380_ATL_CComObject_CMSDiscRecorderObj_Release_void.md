# ATL::CComObject<CMSDiscRecorderObj>::Release(void)

- ea: `0x180007380`
- end: `0x180007401`
- name: `?Release@?$CComObject@VCMSDiscRecorderObj@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007410`

## callees

- `0x180007380`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscRecorderObj>::Release(volatile signed __int32 *a1)
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
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180007380  mov     [rsp+arg_0], rbx
0x180007385  push    rdi
0x180007386  sub     rsp, 20h
0x18000738a  mov     r8d, [rcx+10h]
0x18000738e  mov     rbx, rcx
0x180007391  mov     ecx, 7FFFFFFFh
0x180007396  jmp     short loc_1800073AA
0x180007398  lea     edx, [r8-1]
0x18000739c  mov     eax, r8d
0x18000739f  lock cmpxchg [rbx+10h], edx
0x1800073a4  jz      short loc_1800073AF
0x1800073a6  mov     r8d, [rbx+10h]
0x1800073aa  cmp     r8d, ecx
0x1800073ad  jnz     short loc_180007398
0x1800073af  lea     edi, [r8-1]
0x1800073b3  test    edi, edi
0x1800073b5  jnz     short loc_1800073F4
0x1800073b7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800073be  mov     rax, [rcx]
0x1800073c1  mov     rax, [rax+8]
0x1800073c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ca  test    rbx, rbx
0x1800073cd  jz      short loc_1800073E1
0x1800073cf  mov     rax, [rbx]
0x1800073d2  lea     edx, [rdi+1]
0x1800073d5  mov     rcx, rbx
0x1800073d8  mov     rax, [rax+20h]
0x1800073dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073e1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800073e8  mov     rdx, [rcx]
0x1800073eb  mov     rax, [rdx+10h]
0x1800073ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073f4  mov     rbx, [rsp+28h+arg_0]
0x1800073f9  mov     eax, edi
0x1800073fb  add     rsp, 20h
0x1800073ff  pop     rdi
0x180007400  retn
```
