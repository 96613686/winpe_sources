# ATL::CComObject<MapsIdleBackgroundCopyCallback>::CComObject<MapsIdleBackgroundCopyCallback>(void *)

- ea: `0x1800029c0`
- end: `0x180002a0a`
- name: `??0?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@QEAA@PEAX@Z`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002d28`
- `0x18000359c`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<MapsIdleBackgroundCopyCallback>::CComObject<MapsIdleBackgroundCopyCallback>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  *(_QWORD *)a1 = &ATL::CComObject<MapsIdleBackgroundCopyCallback>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return a1;
}

```

## disassembly

```asm
0x1800029c0  push    rbx
0x1800029c2  sub     rsp, 20h
0x1800029c6  mov     dword ptr [rcx+8], 0
0x1800029cd  xor     eax, eax
0x1800029cf  xorps   xmm0, xmm0
0x1800029d2  mov     rbx, rcx
0x1800029d5  movups  xmmword ptr [rcx+10h], xmm0
0x1800029d9  movups  xmmword ptr [rcx+20h], xmm0
0x1800029dd  mov     [rcx+30h], rax
0x1800029e1  mov     [rcx+38h], al
0x1800029e4  lea     rax, ??_7?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@6B@; const ATL::CComObject<MapsIdleBackgroundCopyCallback>::`vftable'
0x1800029eb  mov     [rcx], rax
0x1800029ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800029f5  mov     rax, [rcx]
0x1800029f8  mov     rax, [rax+8]
0x1800029fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a01  mov     rax, rbx
0x180002a04  add     rsp, 20h
0x180002a08  pop     rbx
0x180002a09  retn
```
