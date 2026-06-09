# ATL::CComObject<CMSDiscMasterObj>::Release(void)

- ea: `0x1800091e0`
- end: `0x18000926d`
- name: `?Release@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009280`
- `0x180009290`
- `0x1800092a0`
- `0x1800092b0`
- `0x1800092c0`

## callees

- `0x1800091e0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscMasterObj>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 32);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 32, i - 1, i);
        i = *((_DWORD *)a1 + 32) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 144LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800091e0  mov     [rsp+arg_0], rbx
0x1800091e5  push    rdi
0x1800091e6  sub     rsp, 20h
0x1800091ea  mov     r8d, [rcx+80h]
0x1800091f1  mov     rbx, rcx
0x1800091f4  mov     ecx, 7FFFFFFFh
0x1800091f9  jmp     short loc_180009213
0x1800091fb  lea     edx, [r8-1]
0x1800091ff  mov     eax, r8d
0x180009202  lock cmpxchg [rbx+80h], edx
0x18000920a  jz      short loc_180009218
0x18000920c  mov     r8d, [rbx+80h]
0x180009213  cmp     r8d, ecx
0x180009216  jnz     short loc_1800091FB
0x180009218  lea     edi, [r8-1]
0x18000921c  test    edi, edi
0x18000921e  jnz     short loc_180009260
0x180009220  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009227  mov     rax, [rcx]
0x18000922a  mov     rax, [rax+8]
0x18000922e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009233  test    rbx, rbx
0x180009236  jz      short loc_18000924D
0x180009238  mov     rax, [rbx]
0x18000923b  lea     edx, [rdi+1]
0x18000923e  mov     rcx, rbx
0x180009241  mov     rax, [rax+90h]
0x180009248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000924d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009254  mov     rdx, [rcx]
0x180009257  mov     rax, [rdx+10h]
0x18000925b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009260  mov     rbx, [rsp+28h+arg_0]
0x180009265  mov     eax, edi
0x180009267  add     rsp, 20h
0x18000926b  pop     rdi
0x18000926c  retn
```
