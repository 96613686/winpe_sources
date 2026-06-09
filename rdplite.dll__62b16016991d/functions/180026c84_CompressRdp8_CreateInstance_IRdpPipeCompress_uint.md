# CompressRdp8__CreateInstance(IRdpPipeCompress * *,uint)

- ea: `0x180026c84`
- end: `0x180026d9d`
- name: `?CompressRdp8__CreateInstance@@YAJPEAPEAVIRdpPipeCompress@@I@Z`
- size: `281`
- prototype: `__int64 __fastcall(struct IRdpPipeCompress **, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f698`

## callees

- `0x180003714`
- `0x180026c84`
- `0x180027248`
- `0x1800275e0`
- `0x18002a010`

## string_xrefs

- `0x180026cc1`: `CompressRdp8`

## pseudocode

```c
__int64 __fastcall CompressRdp8__CreateInstance(struct IRdpPipeCompress **a1)
{
  _DWORD *v2; // rbx
  __int64 v3; // rax
  unsigned int v4; // esi
  CompressChopper *v5; // rax
  struct IRdpPipeCompress *v6; // rax
  _DWORD *v8; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  v8 = 0;
  v2 = operator new(0x800A0u);
  *(_QWORD *)v2 = &IRdpPipeCompress::`vftable';
  v2[8] = -607474739;
  *((_QWORD *)v2 + 3) = "CompressRdp8";
  v2[9] = 1;
  *((_QWORD *)v2 + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v2 + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
  v2[12] = 0;
  *((_QWORD *)v2 + 5) = v2 + 2;
  *(_QWORD *)v2 = &CompressRdp8<4>::`vftable';
  *((_QWORD *)v2 + 1) = &CompressChopper::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v2 + 2) = &CompressRdp8<4>::`vftable'{for `CTSObject'};
  *((_QWORD *)v2 + 7) = 0;
  *((_QWORD *)v2 + 10) = 0;
  *((_BYTE *)v2 + 92) = 0;
  *((_QWORD *)v2 + 12) = 0;
  *((_QWORD *)v2 + 13) = 0;
  v2[22] = 0;
  *((_QWORD *)v2 + 15) = 0;
  *((_WORD *)v2 + 78) = 0;
  TCntPtr<IRdpPipeCompress>::SafeRelease(&v8);
  v3 = *(_QWORD *)v2;
  v8 = v2;
  (*(void (__fastcall **)(_DWORD *))(v3 + 8))(v2);
  *a1 = 0;
  v4 = -2147467259;
  v5 = (CompressChopper *)operator new(0x4F8u);
  v6 = CompressChopper::CompressChopper(v5, (struct IRdpPipeCompress *)v2, 0xFFFFu);
  *a1 = v6;
  if ( v6 )
  {
    (*(void (__fastcall **)(struct IRdpPipeCompress *))(*(_QWORD *)v6 + 8LL))(v6);
    v4 = 0;
  }
  TCntPtr<IRdpPipeCompress>::SafeRelease(&v8);
  return v4;
}

```

## disassembly

```asm
0x180026c84  push    rbx
0x180026c86  push    rbp
0x180026c87  push    rsi
0x180026c88  push    rdi
0x180026c89  sub     rsp, 28h
0x180026c8d  xor     ebp, ebp
0x180026c8f  mov     rdi, rcx
0x180026c92  mov     [rcx], rbp
0x180026c95  mov     ecx, 800A0h; Size
0x180026c9a  mov     [rsp+48h+arg_0], rbp
0x180026c9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026ca4  mov     rbx, rax
0x180026ca7  lea     rcx, [rsp+48h+arg_0]
0x180026cac  lea     rax, ??_7IRdpPipeCompress@@6B@; const IRdpPipeCompress::`vftable'
0x180026cb3  mov     [rbx], rax
0x180026cb6  lea     rdx, [rbx+8]
0x180026cba  mov     dword ptr [rdx+18h], 0DBCAABCDh
0x180026cc1  lea     rax, aCompressrdp8; "CompressRdp8"
0x180026cc8  mov     [rdx+10h], rax
0x180026ccc  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x180026cd3  mov     dword ptr [rdx+1Ch], 1
0x180026cda  mov     [rdx], rax
0x180026cdd  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180026ce4  mov     [rdx+8], rax
0x180026ce8  lea     rax, ??_7?$CompressRdp8@$03@@6B@; const CompressRdp8<4>::`vftable'
0x180026cef  mov     [rdx+28h], ebp
0x180026cf2  mov     [rdx+20h], rdx
0x180026cf6  mov     [rbx], rax
0x180026cf9  lea     rax, ??_7CompressChopper@@6BINonDelegatingUnknown@@@; const CompressChopper::`vftable'{for `INonDelegatingUnknown'}
0x180026d00  mov     [rdx], rax
0x180026d03  lea     rax, ??_7?$CompressRdp8@$03@@6BCTSObject@@@; const CompressRdp8<4>::`vftable'{for `CTSObject'}
0x180026d0a  mov     [rbx+10h], rax
0x180026d0e  mov     [rbx+38h], rbp
0x180026d12  mov     [rbx+50h], rbp
0x180026d16  mov     [rbx+5Ch], bpl
0x180026d1a  mov     [rbx+60h], rbp
0x180026d1e  mov     [rbx+68h], rbp
0x180026d22  mov     [rbx+58h], ebp
0x180026d25  mov     [rbx+78h], rbp
0x180026d29  mov     [rbx+9Ch], bp
0x180026d30  call    ?SafeRelease@?$TCntPtr@VIRdpPipeCompress@@@@AEAAXXZ; TCntPtr<IRdpPipeCompress>::SafeRelease(void)
0x180026d35  mov     rax, [rbx]
0x180026d38  mov     rcx, rbx
0x180026d3b  mov     [rsp+48h+arg_0], rbx
0x180026d40  mov     rax, [rax+8]
0x180026d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d49  mov     ecx, 4F8h; Size
0x180026d4e  mov     [rdi], rbp
0x180026d51  mov     esi, 80004005h
0x180026d56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026d5b  mov     r8d, 0FFFFh; unsigned int
0x180026d61  mov     rdx, rbx; struct IRdpPipeCompress *
0x180026d64  mov     rcx, rax; this
0x180026d67  call    ??0CompressChopper@@AEAA@PEAVIRdpPipeCompress@@I@Z; CompressChopper::CompressChopper(IRdpPipeCompress *,uint)
0x180026d6c  mov     [rdi], rax
0x180026d6f  mov     rdx, rax
0x180026d72  test    rax, rax
0x180026d75  jz      short loc_180026D88
0x180026d77  mov     rcx, [rax]
0x180026d7a  mov     rax, [rcx+8]
0x180026d7e  mov     rcx, rdx
0x180026d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d86  mov     esi, ebp
0x180026d88  lea     rcx, [rsp+48h+arg_0]
0x180026d8d  call    ?SafeRelease@?$TCntPtr@VIRdpPipeCompress@@@@AEAAXXZ; TCntPtr<IRdpPipeCompress>::SafeRelease(void)
0x180026d92  mov     eax, esi
0x180026d94  add     rsp, 28h
0x180026d98  pop     rdi
0x180026d99  pop     rsi
0x180026d9a  pop     rbp
0x180026d9b  pop     rbx
0x180026d9c  retn
```
