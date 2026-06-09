# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(void *)

- ea: `0x180008c94`
- end: `0x180008d6a`
- name: `??0?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@QEAA@PEAX@Z`
- size: `214`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009e80`

## callees

- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(
        __int64 a1,
        __int64 a2)
{
  struct ATL::CAtlModule *v3; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = &ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  *(_DWORD *)(a1 + 136) = -1;
  *(_DWORD *)(a1 + 168) = -1;
  *(_DWORD *)(a1 + 104) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  if ( !a2 )
    a2 = a1;
  *(_QWORD *)(a1 + 152) = 0;
  *(_BYTE *)(a1 + 160) = 0;
  *(_DWORD *)(a1 + 164) = 0;
  *(_DWORD *)(a1 + 108) = 2;
  *(_DWORD *)(a1 + 112) = 50;
  *(_QWORD *)(a1 + 116) = 10;
  *(_WORD *)(a1 + 124) = 256;
  *(_DWORD *)(a1 + 132) = 7;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  v3 = ATL::_pAtlModule;
  *(_QWORD *)(a1 + 16) = &ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
  *(_QWORD *)(a1 + 24) = a2;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v3 + 8LL))(v3);
  return a1;
}

```

## disassembly

```asm
0x180008c94  push    rbx
0x180008c96  sub     rsp, 20h
0x180008c9a  mov     rbx, rcx
0x180008c9d  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180008ca4  xor     ecx, ecx
0x180008ca6  mov     [rbx+8], ecx
0x180008ca9  mov     [rbx], rax
0x180008cac  xor     eax, eax
0x180008cae  mov     [rbx+20h], ecx
0x180008cb1  mov     [rbx+28h], rcx
0x180008cb5  mov     [rbx+30h], rcx
0x180008cb9  mov     [rbx+38h], rcx
0x180008cbd  mov     [rbx+40h], rcx
0x180008cc1  mov     [rbx+48h], rax
0x180008cc5  or      eax, 0FFFFFFFFh
0x180008cc8  mov     [rbx+50h], rcx
0x180008ccc  mov     [rbx+58h], rcx
0x180008cd0  mov     [rbx+60h], ecx
0x180008cd3  mov     [rbx+88h], eax
0x180008cd9  mov     [rbx+0A8h], eax
0x180008cdf  xor     eax, eax
0x180008ce1  mov     [rbx+68h], ecx
0x180008ce4  test    rdx, rdx
0x180008ce7  mov     [rbx+80h], ecx
0x180008ced  mov     [rbx+90h], rcx
0x180008cf4  cmovz   rdx, rbx
0x180008cf8  mov     [rbx+98h], rcx
0x180008cff  mov     [rbx+0A0h], cl
0x180008d05  mov     [rbx+0A4h], ecx
0x180008d0b  mov     dword ptr [rbx+6Ch], 2
0x180008d12  mov     dword ptr [rbx+70h], 32h ; '2'
0x180008d19  mov     qword ptr [rbx+74h], 0Ah
0x180008d21  mov     word ptr [rbx+7Ch], 100h
0x180008d27  mov     dword ptr [rbx+84h], 7
0x180008d31  mov     [rbx+0B0h], rax
0x180008d38  lea     rax, ??_7?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180008d3f  mov     [rbx+0B8h], rcx
0x180008d46  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008d4d  mov     [rbx+10h], rax
0x180008d51  mov     [rbx+18h], rdx
0x180008d55  mov     rax, [rcx]
0x180008d58  mov     rax, [rax+8]
0x180008d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d61  mov     rax, rbx
0x180008d64  add     rsp, 20h
0x180008d68  pop     rbx
0x180008d69  retn
```
