# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x180002960`
- end: `0x1800029a9`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `73`
- prototype: `void *__fastcall(PVOID P, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002960`
- `0x180005368`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002995`
- `ntdll!RtlFreeHeap` at `0x180002995`

## pseudocode

```c
ATL::CAtlModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CAtlModule *P, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)P = &ATL::CComModule::`vftable';
  ATL::CAtlModule::Term(P, a2);
  if ( (v2 & 1) != 0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return P;
}

```

## disassembly

```asm
0x180002960  mov     [rsp+arg_0], rbx
0x180002965  push    rdi
0x180002966  sub     rsp, 20h
0x18000296a  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x180002971  mov     ebx, edx
0x180002973  mov     [rcx], rax
0x180002976  mov     rdi, rcx
0x180002979  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000297e  test    bl, 1
0x180002981  jz      short loc_18000299B
0x180002983  mov     rcx, gs:60h
0x18000298c  mov     r8, rdi; P
0x18000298f  xor     edx, edx; Flags
0x180002991  mov     rcx, [rcx+30h]; HeapHandle
0x180002995  call    cs:__imp_RtlFreeHeap
0x18000299b  mov     rbx, [rsp+28h+arg_0]
0x1800029a0  mov     rax, rdi
0x1800029a3  add     rsp, 20h
0x1800029a7  pop     rdi
0x1800029a8  retn
```
