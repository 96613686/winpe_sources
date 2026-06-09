# ATL::CComObject<CPPTPDiagHelper>::CComObject<CPPTPDiagHelper>(void *)

- ea: `0x180009924`
- end: `0x180009a63`
- name: `??0?$CComObject@VCPPTPDiagHelper@@@ATL@@QEAA@PEAX@Z`
- size: `319`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009b6c`

## callees

- `0x18000b824`
- `0x18000ded2`
- `0x18000df10`
- `0x18000f010`

## import_xrefs

- `WS2_32!__imp_WSAStartup` at `0x180009a0a`
- `WS2_32!__imp_WSAStartup` at `0x180009a0a`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPPTPDiagHelper>::CComObject<CPPTPDiagHelper>(__int64 a1)
{
  struct ATL::CAtlModule *v2; // rcx
  WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

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
  CRasLogger::CRasLogger((LPVOID *)(a1 + 112));
  *(_BYTE *)(a1 + 1160) = 0;
  *(_DWORD *)(a1 + 1164) = 0;
  *(_QWORD *)(a1 + 1424) = 0;
  *(_DWORD *)(a1 + 1156) = -1;
  memset_0((void *)(a1 + 1168), 0, 0x80u);
  memset_0((void *)(a1 + 1296), 0, 0x80u);
  memset_0((void *)(a1 + 120), 0, 0x202u);
  memset_0((void *)(a1 + 634), 0, 0x20Au);
  memset_0(&WSAData, 0, sizeof(WSAData));
  WSAStartup(0x202u, &WSAData);
  v2 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CPPTPDiagHelper>::`vftable'{for `INetDiagHelper'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CPPTPDiagHelper>::`vftable'{for `INetDiagHelperInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180009924  mov     [rsp+arg_8], rbx
0x180009929  push    rdi
0x18000992a  sub     rsp, 1D0h
0x180009931  mov     rax, cs:__security_cookie
0x180009938  xor     rax, rsp
0x18000993b  mov     [rsp+1D8h+var_18], rax
0x180009943  xor     edi, edi
0x180009945  xor     eax, eax
0x180009947  mov     [rcx+38h], edi
0x18000994a  xorps   xmm0, xmm0
0x18000994d  movups  xmmword ptr [rcx+40h], xmm0
0x180009951  mov     rbx, rcx
0x180009954  movups  xmmword ptr [rcx+50h], xmm0
0x180009958  mov     [rcx+60h], rax
0x18000995c  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelper@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'}
0x180009963  mov     [rcx+68h], dil
0x180009967  mov     [rcx], rax
0x18000996a  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelperInfo@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'}
0x180009971  mov     [rcx+8], rax
0x180009975  mov     [rcx+20h], rdi
0x180009979  mov     [rcx+14h], rdi
0x18000997d  mov     [rcx+10h], edi
0x180009980  add     rcx, 70h ; 'p'; ppv
0x180009984  call    ??0CRasLogger@@QEAA@XZ; CRasLogger::CRasLogger(void)
0x180009989  mov     [rbx+488h], dil
0x180009990  lea     rcx, [rbx+490h]; void *
0x180009997  mov     [rbx+48Ch], edi
0x18000999d  xor     edx, edx; Val
0x18000999f  mov     [rbx+590h], rdi
0x1800099a6  mov     edi, 80h
0x1800099ab  mov     r8d, edi; Size
0x1800099ae  mov     dword ptr [rbx+484h], 0FFFFFFFFh
0x1800099b8  call    memset_0
0x1800099bd  lea     rcx, [rbx+510h]; void *
0x1800099c4  mov     r8d, edi; Size
0x1800099c7  xor     edx, edx; Val
0x1800099c9  call    memset_0
0x1800099ce  mov     edi, 202h
0x1800099d3  lea     rcx, [rbx+78h]; void *
0x1800099d7  mov     r8d, edi; Size
0x1800099da  xor     edx, edx; Val
0x1800099dc  call    memset_0
0x1800099e1  lea     rcx, [rbx+27Ah]; void *
0x1800099e8  xor     edx, edx; Val
0x1800099ea  lea     r8d, [rdi+8]; Size
0x1800099ee  call    memset_0
0x1800099f3  xor     edx, edx; Val
0x1800099f5  lea     r8d, [rdi-6Ah]; Size
0x1800099f9  lea     rcx, [rsp+1D8h+WSAData]; void *
0x1800099fe  call    memset_0
0x180009a03  mov     ecx, edi; wVersionRequested
0x180009a05  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x180009a0a  call    cs:__imp_WSAStartup
0x180009a11  nop     dword ptr [rax+rax+00h]
0x180009a16  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009a1d  lea     rax, ??_7?$CComObject@VCPPTPDiagHelper@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CPPTPDiagHelper>::`vftable'{for `INetDiagHelper'}
0x180009a24  mov     [rbx], rax
0x180009a27  lea     rax, ??_7?$CComObject@VCPPTPDiagHelper@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CPPTPDiagHelper>::`vftable'{for `INetDiagHelperInfo'}
0x180009a2e  mov     [rbx+8], rax
0x180009a32  mov     rdx, [rcx]
0x180009a35  mov     rax, [rdx+8]
0x180009a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a3e  mov     rax, rbx
0x180009a41  mov     rcx, [rsp+1D8h+var_18]
0x180009a49  xor     rcx, rsp; StackCookie
0x180009a4c  call    __security_check_cookie
0x180009a51  mov     rbx, [rsp+1D8h+arg_8]
0x180009a59  add     rsp, 1D0h
0x180009a60  pop     rdi
0x180009a61  retn
```
