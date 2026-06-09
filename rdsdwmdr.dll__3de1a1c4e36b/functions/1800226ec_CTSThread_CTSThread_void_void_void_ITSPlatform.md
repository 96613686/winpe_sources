# CTSThread::CTSThread(void (*)(void *),void *,ITSPlatform *)

- ea: `0x1800226ec`
- end: `0x180022858`
- name: `??0CTSThread@@QEAA@P6AXPEAX@Z0PEAVITSPlatform@@@Z`
- size: `364`
- prototype: `CTSThread *__fastcall(CTSThread *__hidden this, void (*)(void *), void *, struct ITSPlatform *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021cf0`

## callees

- `0x18000f08c`
- `0x180022698`
- `0x1800226ec`
- `0x1800228ec`
- `0x18002c010`

## string_xrefs

- `0x180022712`: `CTSThread`

## pseudocode

```c
CTSThread *__fastcall CTSThread::CTSThread(CTSThread *this, void (*a2)(void *), void *a3, struct ITSPlatform *a4)
{
  *(_QWORD *)this = &ITSThread::`vftable';
  *((_DWORD *)this + 8) = -607474739;
  *((_QWORD *)this + 3) = "CTSThread";
  *((_DWORD *)this + 9) = 1;
  *((_QWORD *)this + 1) = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 5) = (char *)this + 8;
  *(_QWORD *)this = &CTSThread::`vftable';
  *((_QWORD *)this + 1) = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 2) = &CTSThread::`vftable'{for `CTSObject'};
  *((_DWORD *)this + 20) = 1;
  *((_QWORD *)this + 11) = a2;
  *((_QWORD *)this + 12) = a3;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 17) = (char *)this + 128;
  *((_QWORD *)this + 16) = (char *)this + 128;
  *((_DWORD *)this + 30) = 0;
  CTSReaderWriterLock::CTSReaderWriterLock((CTSThread *)((char *)this + 148));
  CTSReaderWriterLock::CTSReaderWriterLock((CTSThread *)((char *)this + 164));
  *(_QWORD *)((char *)this + 180) = 0;
  *((_DWORD *)this + 47) = 0;
  *((_QWORD *)this + 24) = 0;
  CVPtrList::CVPtrList((CTSThread *)((char *)this + 200));
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_DWORD *)this + 174) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 92) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 88) = -1;
  if ( a4 != *((struct ITSPlatform **)this + 24) )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 192);
    *((_QWORD *)this + 24) = a4;
    if ( a4 )
      (*(void (__fastcall **)(struct ITSPlatform *))(*(_QWORD *)a4 + 8LL))(a4);
  }
  return this;
}

```

## disassembly

```asm
0x1800226ec  push    rbx
0x1800226ee  push    rbp
0x1800226ef  push    rsi
0x1800226f0  push    rdi
0x1800226f1  sub     rsp, 28h
0x1800226f5  mov     rbx, rcx
0x1800226f8  lea     rax, ??_7ITSThread@@6B@; const ITSThread::`vftable'
0x1800226ff  mov     [rcx], rax
0x180022702  xor     ebp, ebp
0x180022704  lea     rax, [rcx+8]
0x180022708  mov     rdi, r9
0x18002270b  mov     dword ptr [rax+18h], 0DBCAABCDh
0x180022712  lea     rcx, aCtsthread; "CTSThread"
0x180022719  mov     [rax+10h], rcx
0x18002271d  mov     r9d, 1
0x180022723  mov     [rax+1Ch], r9d
0x180022727  lea     rcx, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18002272e  mov     [rax], rcx
0x180022731  lea     rcx, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180022738  mov     [rax+8], rcx
0x18002273c  lea     rcx, ??_7CTSThread@@6B@; const CTSThread::`vftable'
0x180022743  mov     [rax+28h], ebp
0x180022746  mov     [rax+20h], rax
0x18002274a  mov     [rbx], rcx
0x18002274d  lea     rcx, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x180022754  mov     [rax], rcx
0x180022757  lea     rax, ??_7CTSThread@@6BCTSObject@@@; const CTSThread::`vftable'{for `CTSObject'}
0x18002275e  mov     [rbx+10h], rax
0x180022762  lea     rcx, [rbx+94h]; this
0x180022769  mov     [rbx+50h], r9d
0x18002276d  lea     rax, [rbx+80h]
0x180022774  mov     [rbx+58h], rdx
0x180022778  mov     [rbx+60h], r8
0x18002277c  mov     [rbx+70h], ebp
0x18002277f  mov     [rbx+68h], rbp
0x180022783  mov     [rbx+88h], rax
0x18002278a  mov     [rax], rax
0x18002278d  mov     [rbx+78h], ebp
0x180022790  call    ??0CTSReaderWriterLock@@QEAA@XZ; CTSReaderWriterLock::CTSReaderWriterLock(void)
0x180022795  lea     rcx, [rbx+0A4h]; this
0x18002279c  call    ??0CTSReaderWriterLock@@QEAA@XZ; CTSReaderWriterLock::CTSReaderWriterLock(void)
0x1800227a1  mov     [rbx+0B4h], rbp
0x1800227a8  lea     rsi, [rbx+0C0h]
0x1800227af  mov     [rbx+0BCh], ebp
0x1800227b5  lea     rcx, [rbx+0C8h]; this
0x1800227bc  mov     [rsi], rbp
0x1800227bf  call    ??0CVPtrList@@QEAA@XZ; CVPtrList::CVPtrList(void)
0x1800227c4  mov     [rbx+288h], rbp
0x1800227cb  mov     [rbx+290h], rbp
0x1800227d2  mov     [rbx+298h], rbp
0x1800227d9  mov     [rbx+2A0h], rbp
0x1800227e0  mov     [rbx+2B8h], ebp
0x1800227e6  mov     [rbx+2C8h], rbp
0x1800227ed  mov     [rbx+2D0h], rbp
0x1800227f4  mov     [rbx+2D8h], rbp
0x1800227fb  mov     [rbx+2E0h], rbp
0x180022802  xor     eax, eax
0x180022804  xorps   xmm0, xmm0
0x180022807  movups  xmmword ptr [rbx+38h], xmm0
0x18002280b  mov     [rbx+48h], rax
0x18002280f  mov     [rbx+2A8h], rbp
0x180022816  mov     [rbx+2B0h], rbp
0x18002281d  mov     qword ptr [rbx+2C0h], 0FFFFFFFFFFFFFFFFh
0x180022828  cmp     rdi, [rsi]
0x18002282b  jz      short loc_18002284C
0x18002282d  mov     rcx, rsi
0x180022830  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180022835  mov     [rsi], rdi
0x180022838  test    rdi, rdi
0x18002283b  jz      short loc_18002284C
0x18002283d  mov     rax, [rdi]
0x180022840  mov     rcx, rdi
0x180022843  mov     rax, [rax+8]
0x180022847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002284c  mov     rax, rbx
0x18002284f  add     rsp, 28h
0x180022853  pop     rdi
0x180022854  pop     rsi
0x180022855  pop     rbp
0x180022856  pop     rbx
0x180022857  retn
```
