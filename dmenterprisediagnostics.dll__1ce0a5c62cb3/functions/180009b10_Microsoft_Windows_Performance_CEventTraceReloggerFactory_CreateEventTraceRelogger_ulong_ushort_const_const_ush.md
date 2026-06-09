# Microsoft::Windows::Performance::CEventTraceReloggerFactory::CreateEventTraceRelogger(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *,IUnknown *,_GUID const &,void * *)

- ea: `0x180009b10`
- end: `0x180009bd2`
- name: `?CreateEventTraceRelogger@CEventTraceReloggerFactory@Performance@Windows@Microsoft@@UEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@PEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `194`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceReloggerFactory *this, unsigned int, const unsigned __int16 *const *, const unsigned __int16 *, struct IUnknown *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009b10`
- `0x180009e80`
- `0x18000a844`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceReloggerFactory::CreateEventTraceRelogger(
        Microsoft::Windows::Performance::CEventTraceReloggerFactory *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        const unsigned __int16 *a4,
        struct IUnknown *a5,
        struct IUnknown *a6,
        const struct _GUID *a7,
        void **a8)
{
  int Instance; // edi
  __int64 v13; // rbx
  _QWORD v14[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 && !a3 || !a4 )
    return 2147500035LL;
  v14[0] = 0;
  Instance = ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(a6, v14);
  if ( Instance >= 0 )
  {
    v13 = v14[0];
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 8LL))(v14[0]);
    Instance = Microsoft::Windows::Performance::CEventTraceRelogger::Init(
                 (Microsoft::Windows::Performance::CEventTraceRelogger *)(v13 + 16),
                 a2,
                 a3,
                 a4,
                 a5);
    if ( Instance >= 0 )
      Instance = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v13)(v13, a7, a8);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180009b10  push    rbx
0x180009b12  push    rbp
0x180009b13  push    rsi
0x180009b14  push    rdi
0x180009b15  push    r14
0x180009b17  sub     rsp, 40h
0x180009b1b  mov     rsi, r9
0x180009b1e  mov     rbp, r8
0x180009b21  mov     r14d, edx
0x180009b24  test    edx, edx
0x180009b26  jz      short loc_180009B2D
0x180009b28  test    r8, r8
0x180009b2b  jz      short loc_180009B32
0x180009b2d  test    rsi, rsi
0x180009b30  jnz     short loc_180009B3C
0x180009b32  mov     eax, 80004003h
0x180009b37  jmp     loc_180009BC7
0x180009b3c  mov     rcx, [rsp+68h+arg_28]
0x180009b44  lea     rdx, [rsp+68h+var_38]
0x180009b49  mov     [rsp+68h+var_38], 0
0x180009b52  call    ?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z; ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)
0x180009b57  mov     edi, eax
0x180009b59  test    eax, eax
0x180009b5b  js      short loc_180009BC5
0x180009b5d  mov     rbx, [rsp+68h+var_38]
0x180009b62  mov     rcx, rbx
0x180009b65  mov     rax, [rbx]
0x180009b68  mov     rax, [rax+8]
0x180009b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b71  mov     rax, [rsp+68h+arg_20]
0x180009b79  lea     rcx, [rbx+10h]; this
0x180009b7d  mov     r9, rsi; unsigned __int16 *
0x180009b80  mov     [rsp+68h+var_48], rax; struct IUnknown *
0x180009b85  mov     r8, rbp; unsigned __int16 **
0x180009b88  mov     edx, r14d; unsigned int
0x180009b8b  call    ?Init@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@@Z; Microsoft::Windows::Performance::CEventTraceRelogger::Init(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *)
0x180009b90  mov     edi, eax
0x180009b92  test    eax, eax
0x180009b94  js      short loc_180009BB6
0x180009b96  mov     rax, [rbx]
0x180009b99  mov     rcx, rbx
0x180009b9c  mov     r8, [rsp+68h+arg_38]
0x180009ba4  mov     rdx, [rsp+68h+arg_30]
0x180009bac  mov     rax, [rax]
0x180009baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb4  mov     edi, eax
0x180009bb6  mov     rax, [rbx]
0x180009bb9  mov     rcx, rbx
0x180009bbc  mov     rax, [rax+10h]
0x180009bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bc5  mov     eax, edi
0x180009bc7  add     rsp, 40h
0x180009bcb  pop     r14
0x180009bcd  pop     rdi
0x180009bce  pop     rsi
0x180009bcf  pop     rbp
0x180009bd0  pop     rbx
0x180009bd1  retn
```
