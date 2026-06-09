# ATL::CComObject<CMSMQCollection>::CreateInstance(ATL::CComObject<CMSMQCollection> * *)

- ea: `0x180025910`
- end: `0x1800259b2`
- name: `?CreateInstance@?$CComObject@VCMSMQCollection@@@ATL@@SAJPEAPEAV12@@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180025f18`

## callees

- `0x18000173c`
- `0x18000f34c`
- `0x180025528`
- `0x18002574c`
- `0x180025910`
- `0x180029010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x180025987`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180025987`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CMSMQCollection>::CreateInstance(LPUNKNOWN **a1)
{
  HRESULT FreeThreadedMarshaler; // ebx
  void *v4; // rax
  LPUNKNOWN *v5; // rdi
  IUnknown *v6; // rax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  FreeThreadedMarshaler = -2147024882;
  v4 = operator new(0x90u);
  if ( v4 )
    v5 = (LPUNKNOWN *)ATL::CComObject<CMSMQCollection>::CComObject<CMSMQCollection>(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    FreeThreadedMarshaler = ATL::CComAutoDeleteCriticalSection::Init((ATL::CComAutoDeleteCriticalSection *)(v5 + 3));
    if ( FreeThreadedMarshaler >= 0 )
    {
      v6 = (IUnknown *)((__int64 (__fastcall *)(LPUNKNOWN *))(*v5)[4].lpVtbl)(v5);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v6, v5 + 9);
    }
    if ( FreeThreadedMarshaler )
    {
      ATL::CComObject<CMSMQCollection>::`scalar deleting destructor'(v5);
      v5 = 0;
    }
  }
  *a1 = v5;
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x180025910  mov     [rsp+arg_8], rbx
0x180025915  mov     [rsp+arg_10], rsi
0x18002591a  push    rdi
0x18002591b  sub     rsp, 20h
0x18002591f  mov     rsi, rcx
0x180025922  test    rcx, rcx
0x180025925  jnz     short loc_18002592E
0x180025927  mov     eax, 80004003h
0x18002592c  jmp     short loc_1800259A2
0x18002592e  mov     qword ptr [rcx], 0
0x180025935  mov     ebx, 8007000Eh
0x18002593a  mov     ecx, 90h; Size
0x18002593f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025944  mov     [rsp+28h+arg_0], rax
0x180025949  test    rax, rax
0x18002594c  jz      short loc_18002595B
0x18002594e  mov     rcx, rax
0x180025951  call    ??0?$CComObject@VCMSMQCollection@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CMSMQCollection>::CComObject<CMSMQCollection>(void *)
0x180025956  mov     rdi, rax
0x180025959  jmp     short loc_18002595D
0x18002595b  xor     edi, edi
0x18002595d  test    rdi, rdi
0x180025960  jz      short loc_18002599D
0x180025962  lea     rcx, [rdi+18h]; this
0x180025966  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18002596b  mov     ebx, eax
0x18002596d  test    eax, eax
0x18002596f  js      short loc_18002598F
0x180025971  mov     rax, [rdi]
0x180025974  mov     rcx, rdi
0x180025977  mov     rax, [rax+20h]
0x18002597b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025980  mov     rcx, rax; punkOuter
0x180025983  lea     rdx, [rdi+48h]; ppunkMarshal
0x180025987  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18002598d  mov     ebx, eax
0x18002598f  test    ebx, ebx
0x180025991  jz      short loc_18002599D
0x180025993  mov     rcx, rdi; Block
0x180025996  call    ??_G?$CComObject@VCMSMQCollection@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQCollection>::`scalar deleting destructor'(uint)
0x18002599b  xor     edi, edi
0x18002599d  mov     [rsi], rdi
0x1800259a0  mov     eax, ebx
0x1800259a2  mov     rbx, [rsp+28h+arg_8]
0x1800259a7  mov     rsi, [rsp+28h+arg_10]
0x1800259ac  add     rsp, 20h
0x1800259b0  pop     rdi
0x1800259b1  retn
```
