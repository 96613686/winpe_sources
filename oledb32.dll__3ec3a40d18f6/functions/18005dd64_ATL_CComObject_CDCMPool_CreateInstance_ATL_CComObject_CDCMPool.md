# ATL::CComObject<CDCMPool>::CreateInstance(ATL::CComObject<CDCMPool> * *)

- ea: `0x18005dd64`
- end: `0x18005de44`
- name: `?CreateInstance@?$CComObject@VCDCMPool@@@ATL@@SAJPEAPEAV12@@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005de9c`

## callees

- `0x18005dc14`
- `0x18005dd64`
- `0x180063a94`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18005dda6`
- `MSDART!MpHeapAlloc` at `0x18005dda6`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18005de1e`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18005de1e`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDCMPool>::CreateInstance(CDCMPool **a1)
{
  unsigned int FreeThreadedMarshaler; // ebx
  CDCMPool *v4; // rax
  CDCMPool *v5; // rdi
  CDCMPool *v6; // r14
  IUnknown *v7; // rax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  FreeThreadedMarshaler = -2147024882;
  v4 = (CDCMPool *)MpHeapAlloc(g_hHeapHandle, 19922944, 272);
  v5 = v4;
  if ( v4 )
  {
    CDCMPool::CDCMPool(v4);
    *(_QWORD *)v5 = &ATL::CComObject<CDCMPool>::`vftable'{for `IPoolInfo'};
    *((_QWORD *)v5 + 1) = &ATL::CComObject<CDCMPool>::`vftable'{for `IDispenserDriver'};
    _InterlockedIncrement(&dword_1800BE368);
  }
  else
  {
    v5 = 0;
  }
  v6 = v5;
  if ( v5 )
  {
    v7 = (IUnknown *)(*(__int64 (__fastcall **)(CDCMPool *))(*(_QWORD *)v5 + 96LL))(v5);
    FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v7, (LPUNKNOWN *)v5 + 8);
    if ( FreeThreadedMarshaler )
    {
      ATL::CComObject<CDCMPool>::`scalar deleting destructor'(v5);
      v6 = 0;
    }
  }
  *a1 = v6;
  return FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x18005dd64  mov     [rsp+arg_0], rcx
0x18005dd69  push    rbx
0x18005dd6a  push    rsi
0x18005dd6b  push    rdi
0x18005dd6c  push    r14
0x18005dd6e  sub     rsp, 28h
0x18005dd72  mov     rsi, rcx
0x18005dd75  test    rcx, rcx
0x18005dd78  jnz     short loc_18005DD84
0x18005dd7a  mov     eax, 80004003h
0x18005dd7f  jmp     loc_18005DE3A
0x18005dd84  mov     qword ptr [rcx], 0
0x18005dd8b  mov     ebx, 8007000Eh
0x18005dd90  mov     [rsp+48h+arg_8], ebx
0x18005dd94  mov     edx, 1300000h
0x18005dd99  mov     r8d, 110h
0x18005dd9f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18005dda6  call    cs:__imp_MpHeapAlloc
0x18005ddac  mov     rdi, rax
0x18005ddaf  mov     [rsp+48h+arg_10], rax
0x18005ddb4  test    rax, rax
0x18005ddb7  jz      short loc_18005DDDF
0x18005ddb9  mov     rcx, rax; this
0x18005ddbc  call    ??0CDCMPool@@QEAA@XZ; CDCMPool::CDCMPool(void)
0x18005ddc1  lea     rax, ??_7?$CComObject@VCDCMPool@@@ATL@@6BIPoolInfo@@@; const ATL::CComObject<CDCMPool>::`vftable'{for `IPoolInfo'}
0x18005ddc8  mov     [rdi], rax
0x18005ddcb  lea     rax, ??_7?$CComObject@VCDCMPool@@@ATL@@6BIDispenserDriver@@@; const ATL::CComObject<CDCMPool>::`vftable'{for `IDispenserDriver'}
0x18005ddd2  mov     [rdi+8], rax
0x18005ddd6  lock inc cs:dword_1800BE368
0x18005dddd  jmp     short loc_18005DDE1
0x18005dddf  xor     edi, edi
0x18005dde1  mov     [rsp+48h+arg_10], rdi
0x18005dde6  mov     r14, rdi
0x18005dde9  mov     [rsp+48h+arg_18], rdi
0x18005ddee  jmp     short loc_18005DE03
0x18005ddf0  mov     rsi, [rsp+48h+arg_0]
0x18005ddf5  mov     ebx, [rsp+48h+arg_8]
0x18005ddf9  mov     r14, [rsp+48h+arg_18]
0x18005ddfe  mov     rdi, [rsp+48h+arg_10]
0x18005de03  test    rdi, rdi
0x18005de06  jz      short loc_18005DE35
0x18005de08  mov     rax, [rdi]
0x18005de0b  mov     rcx, rdi
0x18005de0e  mov     rax, [rax+60h]
0x18005de12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de17  mov     rcx, rax; punkOuter
0x18005de1a  lea     rdx, [rdi+40h]; ppunkMarshal
0x18005de1e  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18005de24  mov     ebx, eax
0x18005de26  test    eax, eax
0x18005de28  jz      short loc_18005DE35
0x18005de2a  mov     rcx, rdi; void *
0x18005de2d  call    ??_G?$CComObject@VCDCMPool@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CDCMPool>::`scalar deleting destructor'(uint)
0x18005de32  xor     r14d, r14d
0x18005de35  mov     [rsi], r14
0x18005de38  mov     eax, ebx
0x18005de3a  add     rsp, 28h
0x18005de3e  pop     r14
0x18005de40  pop     rdi
0x18005de41  pop     rsi
0x18005de42  pop     rbx
0x18005de43  retn
```
