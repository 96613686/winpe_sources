# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(void *)

- ea: `0x1800090e0`
- end: `0x1800091b7`
- name: `??0?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@QEAA@PEAX@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a3e8`

## callees

- `0x180027010`

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
0x1800090e0  push    rbx
0x1800090e2  sub     rsp, 20h
0x1800090e6  mov     rbx, rcx
0x1800090e9  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x1800090f0  xor     ecx, ecx
0x1800090f2  mov     [rbx+8], ecx
0x1800090f5  mov     [rbx], rax
0x1800090f8  xor     eax, eax
0x1800090fa  mov     [rbx+20h], ecx
0x1800090fd  mov     [rbx+28h], rcx
0x180009101  mov     [rbx+30h], rcx
0x180009105  mov     [rbx+38h], rcx
0x180009109  mov     [rbx+40h], rcx
0x18000910d  mov     [rbx+48h], rax
0x180009111  or      eax, 0FFFFFFFFh
0x180009114  mov     [rbx+50h], rcx
0x180009118  mov     [rbx+58h], rcx
0x18000911c  mov     [rbx+60h], ecx
0x18000911f  mov     [rbx+88h], eax
0x180009125  mov     [rbx+0A8h], eax
0x18000912b  xor     eax, eax
0x18000912d  mov     [rbx+68h], ecx
0x180009130  test    rdx, rdx
0x180009133  mov     [rbx+80h], ecx
0x180009139  mov     [rbx+90h], rcx
0x180009140  cmovz   rdx, rbx
0x180009144  mov     [rbx+98h], rcx
0x18000914b  mov     [rbx+0A0h], cl
0x180009151  mov     [rbx+0A4h], ecx
0x180009157  mov     dword ptr [rbx+6Ch], 2
0x18000915e  mov     dword ptr [rbx+70h], 32h ; '2'
0x180009165  mov     qword ptr [rbx+74h], 0Ah
0x18000916d  mov     word ptr [rbx+7Ch], 100h
0x180009173  mov     dword ptr [rbx+84h], 7
0x18000917d  mov     [rbx+0B0h], rax
0x180009184  lea     rax, ??_7?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x18000918b  mov     [rbx+0B8h], rcx
0x180009192  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009199  mov     [rbx+10h], rax
0x18000919d  mov     [rbx+18h], rdx
0x1800091a1  mov     rax, [rcx]
0x1800091a4  mov     rax, [rax+8]
0x1800091a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ad  mov     rax, rbx
0x1800091b0  add     rsp, 20h
0x1800091b4  pop     rbx
0x1800091b5  retn
```
