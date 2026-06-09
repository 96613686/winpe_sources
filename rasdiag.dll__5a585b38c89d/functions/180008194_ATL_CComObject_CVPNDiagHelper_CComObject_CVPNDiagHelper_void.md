# ATL::CComObject<CVPNDiagHelper>::CComObject<CVPNDiagHelper>(void *)

- ea: `0x180008194`
- end: `0x180008277`
- name: `??0?$CComObject@VCVPNDiagHelper@@@ATL@@QEAA@PEAX@Z`
- size: `227`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000837c`

## callees

- `0x18000b824`
- `0x18000ded2`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVPNDiagHelper>::CComObject<CVPNDiagHelper>(__int64 a1)
{
  struct ATL::CAtlModule *v2; // rcx

  *(_DWORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_BYTE *)(a1 + 104) = 0;
  *(_QWORD *)a1 = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'};
  *(_QWORD *)(a1 + 8) = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'};
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 20) = 0;
  *(_DWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 1148) = -1;
  *(_BYTE *)(a1 + 1152) = 0;
  CRasLogger::CRasLogger((LPVOID *)(a1 + 1416));
  *(_QWORD *)(a1 + 1424) = 0;
  *(_DWORD *)(a1 + 1432) = 0;
  memset_0((void *)(a1 + 112), 0, 0x202u);
  memset_0((void *)(a1 + 626), 0, 0x20Au);
  v2 = ATL::_pAtlModule;
  *(_OWORD *)(a1 + 1436) = 0;
  *(_QWORD *)a1 = &ATL::CComObject<CVPNDiagHelper>::`vftable'{for `INetDiagHelper'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CVPNDiagHelper>::`vftable'{for `INetDiagHelperInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180008194  push    rbx
0x180008196  sub     rsp, 20h
0x18000819a  mov     dword ptr [rcx+38h], 0
0x1800081a1  xor     eax, eax
0x1800081a3  xorps   xmm0, xmm0
0x1800081a6  mov     rbx, rcx
0x1800081a9  movups  xmmword ptr [rcx+40h], xmm0
0x1800081ad  movups  xmmword ptr [rcx+50h], xmm0
0x1800081b1  mov     [rcx+60h], rax
0x1800081b5  mov     [rcx+68h], al
0x1800081b8  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelper@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'}
0x1800081bf  mov     [rcx], rax
0x1800081c2  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelperInfo@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'}
0x1800081c9  mov     [rcx+8], rax
0x1800081cd  mov     qword ptr [rcx+20h], 0
0x1800081d5  mov     qword ptr [rcx+14h], 0
0x1800081dd  mov     dword ptr [rcx+10h], 0
0x1800081e4  mov     dword ptr [rcx+47Ch], 0FFFFFFFFh
0x1800081ee  mov     byte ptr [rcx+480h], 0
0x1800081f5  add     rcx, 588h; ppv
0x1800081fc  call    ??0CRasLogger@@QEAA@XZ; CRasLogger::CRasLogger(void)
0x180008201  lea     rcx, [rbx+70h]; void *
0x180008205  mov     qword ptr [rbx+590h], 0
0x180008210  xor     edx, edx; Val
0x180008212  mov     dword ptr [rbx+598h], 0
0x18000821c  mov     r8d, 202h; Size
0x180008222  call    memset_0
0x180008227  lea     rcx, [rbx+272h]; void *
0x18000822e  xor     edx, edx; Val
0x180008230  mov     r8d, 20Ah; Size
0x180008236  call    memset_0
0x18000823b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008242  lea     rax, ??_7?$CComObject@VCVPNDiagHelper@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CVPNDiagHelper>::`vftable'{for `INetDiagHelper'}
0x180008249  xorps   xmm0, xmm0
0x18000824c  movups  xmmword ptr [rbx+59Ch], xmm0
0x180008253  mov     [rbx], rax
0x180008256  lea     rax, ??_7?$CComObject@VCVPNDiagHelper@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CVPNDiagHelper>::`vftable'{for `INetDiagHelperInfo'}
0x18000825d  mov     [rbx+8], rax
0x180008261  mov     rax, [rcx]
0x180008264  mov     rax, [rax+8]
0x180008268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000826d  mov     rax, rbx
0x180008270  add     rsp, 20h
0x180008274  pop     rbx
0x180008275  retn
```
