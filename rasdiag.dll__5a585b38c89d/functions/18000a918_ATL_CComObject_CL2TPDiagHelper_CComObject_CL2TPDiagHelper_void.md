# ATL::CComObject<CL2TPDiagHelper>::CComObject<CL2TPDiagHelper>(void *)

- ea: `0x18000a918`
- end: `0x18000aa19`
- name: `??0?$CComObject@VCL2TPDiagHelper@@@ATL@@QEAA@PEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000aafc`

## callees

- `0x18000b824`
- `0x18000ded2`
- `0x18000df10`
- `0x18000f010`

## import_xrefs

- `WS2_32!__imp_WSAStartup` at `0x18000a9c8`
- `WS2_32!__imp_WSAStartup` at `0x18000a9c8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CL2TPDiagHelper>::CComObject<CL2TPDiagHelper>(__int64 a1)
{
  struct ATL::CAtlModule *v2; // rcx
  struct WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

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
  *(_DWORD *)(a1 + 1156) = -1;
  *(_BYTE *)(a1 + 1160) = 0;
  *(_DWORD *)(a1 + 1164) = 0;
  *(_QWORD *)(a1 + 1424) = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  WSAStartup(0x202u, &WSAData);
  v2 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CL2TPDiagHelper>::`vftable'{for `INetDiagHelper'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CL2TPDiagHelper>::`vftable'{for `INetDiagHelperInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x18000a918  push    rbx
0x18000a91a  sub     rsp, 1D0h
0x18000a921  mov     rax, cs:__security_cookie
0x18000a928  xor     rax, rsp
0x18000a92b  mov     [rsp+1D8h+var_18], rax
0x18000a933  mov     dword ptr [rcx+38h], 0
0x18000a93a  xor     eax, eax
0x18000a93c  xorps   xmm0, xmm0
0x18000a93f  mov     rbx, rcx
0x18000a942  movups  xmmword ptr [rcx+40h], xmm0
0x18000a946  movups  xmmword ptr [rcx+50h], xmm0
0x18000a94a  mov     [rcx+60h], rax
0x18000a94e  mov     [rcx+68h], al
0x18000a951  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelper@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'}
0x18000a958  mov     [rcx], rax
0x18000a95b  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelperInfo@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'}
0x18000a962  mov     [rcx+8], rax
0x18000a966  mov     qword ptr [rcx+20h], 0
0x18000a96e  mov     qword ptr [rcx+14h], 0
0x18000a976  mov     dword ptr [rcx+10h], 0
0x18000a97d  add     rcx, 70h ; 'p'; ppv
0x18000a981  call    ??0CRasLogger@@QEAA@XZ; CRasLogger::CRasLogger(void)
0x18000a986  xor     edx, edx; Val
0x18000a988  mov     dword ptr [rbx+484h], 0FFFFFFFFh
0x18000a992  mov     r8d, 198h; Size
0x18000a998  mov     byte ptr [rbx+488h], 0
0x18000a99f  lea     rcx, [rsp+1D8h+WSAData]; void *
0x18000a9a4  mov     dword ptr [rbx+48Ch], 0
0x18000a9ae  mov     qword ptr [rbx+590h], 0
0x18000a9b9  call    memset_0
0x18000a9be  mov     ecx, 202h; wVersionRequested
0x18000a9c3  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x18000a9c8  call    cs:__imp_WSAStartup
0x18000a9cf  nop     dword ptr [rax+rax+00h]
0x18000a9d4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a9db  lea     rax, ??_7?$CComObject@VCL2TPDiagHelper@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CL2TPDiagHelper>::`vftable'{for `INetDiagHelper'}
0x18000a9e2  mov     [rbx], rax
0x18000a9e5  lea     rax, ??_7?$CComObject@VCL2TPDiagHelper@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CL2TPDiagHelper>::`vftable'{for `INetDiagHelperInfo'}
0x18000a9ec  mov     [rbx+8], rax
0x18000a9f0  mov     rdx, [rcx]
0x18000a9f3  mov     rax, [rdx+8]
0x18000a9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9fc  mov     rax, rbx
0x18000a9ff  mov     rcx, [rsp+1D8h+var_18]
0x18000aa07  xor     rcx, rsp; StackCookie
0x18000aa0a  call    __security_check_cookie
0x18000aa0f  add     rsp, 1D0h
0x18000aa16  pop     rbx
0x18000aa17  retn
```
