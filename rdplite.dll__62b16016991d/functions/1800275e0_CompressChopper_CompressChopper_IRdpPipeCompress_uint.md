# CompressChopper::CompressChopper(IRdpPipeCompress *,uint)

- ea: `0x1800275e0`
- end: `0x180027698`
- name: `??0CompressChopper@@AEAA@PEAVIRdpPipeCompress@@I@Z`
- size: `184`
- prototype: `CompressChopper *__fastcall(CompressChopper *__hidden this, struct IRdpPipeCompress *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180026c84`

## callees

- `0x180027248`
- `0x1800275e0`
- `0x18002a010`

## string_xrefs

- `0x180027601`: `CompressChopper`

## pseudocode

```c
CompressChopper *__fastcall CompressChopper::CompressChopper(
        CompressChopper *this,
        struct IRdpPipeCompress *a2,
        int a3)
{
  _QWORD *v4; // rsi
  CompressChopper *result; // rax

  *(_QWORD *)this = &IRdpPipeCompress::`vftable';
  *((_DWORD *)this + 8) = -607474739;
  *((_QWORD *)this + 3) = "CompressChopper";
  *((_DWORD *)this + 9) = 1;
  v4 = (_QWORD *)((char *)this + 56);
  *((_QWORD *)this + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 5) = (char *)this + 8;
  *(_QWORD *)this = &CompressChopper::`vftable';
  *((_QWORD *)this + 1) = &CompressChopper::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 2) = &CompressChopper::`vftable'{for `CTSObject'};
  *((_QWORD *)this + 7) = 0;
  if ( a2 )
  {
    TCntPtr<IRdpPipeCompress>::SafeRelease(v4);
    *v4 = a2;
    (*(void (__fastcall **)(struct IRdpPipeCompress *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  *((_DWORD *)this + 16) = a3;
  result = this;
  *((_DWORD *)this + 17) = 0;
  return result;
}

```

## disassembly

```asm
0x1800275e0  push    rbx
0x1800275e2  push    rbp
0x1800275e3  push    rsi
0x1800275e4  push    rdi
0x1800275e5  sub     rsp, 28h
0x1800275e9  lea     rax, ??_7IRdpPipeCompress@@6B@; const IRdpPipeCompress::`vftable'
0x1800275f0  mov     rbx, rcx
0x1800275f3  mov     [rcx], rax
0x1800275f6  lea     rax, [rcx+8]
0x1800275fa  mov     dword ptr [rax+18h], 0DBCAABCDh
0x180027601  lea     rcx, aCompresschoppe; "CompressChopper"
0x180027608  mov     [rax+10h], rcx
0x18002760c  lea     rcx, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x180027613  mov     dword ptr [rax+1Ch], 1
0x18002761a  lea     rsi, [rbx+38h]
0x18002761e  mov     [rax], rcx
0x180027621  lea     rcx, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180027628  mov     [rax+8], rcx
0x18002762c  lea     rcx, ??_7CompressChopper@@6B@; const CompressChopper::`vftable'
0x180027633  mov     dword ptr [rax+28h], 0
0x18002763a  mov     ebp, r8d
0x18002763d  mov     [rax+20h], rax
0x180027641  mov     rdi, rdx
0x180027644  mov     [rbx], rcx
0x180027647  lea     rcx, ??_7CompressChopper@@6BINonDelegatingUnknown@@@; const CompressChopper::`vftable'{for `INonDelegatingUnknown'}
0x18002764e  mov     [rax], rcx
0x180027651  lea     rax, ??_7CompressChopper@@6BCTSObject@@@; const CompressChopper::`vftable'{for `CTSObject'}
0x180027658  mov     [rbx+10h], rax
0x18002765c  mov     qword ptr [rsi], 0
0x180027663  test    rdx, rdx
0x180027666  jz      short loc_180027682
0x180027668  mov     rcx, rsi
0x18002766b  call    ?SafeRelease@?$TCntPtr@VIRdpPipeCompress@@@@AEAAXXZ; TCntPtr<IRdpPipeCompress>::SafeRelease(void)
0x180027670  mov     [rsi], rdi
0x180027673  mov     rcx, rdi
0x180027676  mov     rax, [rdi]
0x180027679  mov     rax, [rax+8]
0x18002767d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027682  mov     [rbx+40h], ebp
0x180027685  mov     rax, rbx
0x180027688  mov     dword ptr [rbx+44h], 0
0x18002768f  add     rsp, 28h
0x180027693  pop     rdi
0x180027694  pop     rsi
0x180027695  pop     rbp
0x180027696  pop     rbx
0x180027697  retn
```
