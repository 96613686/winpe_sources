# Microsoft::Windows::Performance::CEventTraceReloggerFactory::CreateEventTraceRelogger(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *,IUnknown *,_GUID const &,void * *)

- ea: `0x18000a070`
- end: `0x18000a133`
- name: `?CreateEventTraceRelogger@CEventTraceReloggerFactory@Performance@Windows@Microsoft@@UEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@PEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceReloggerFactory *__hidden this, unsigned int, const unsigned __int16 *const *, const unsigned __int16 *, struct Microsoft::Windows::Performance::IEventTraceExtender *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a070`
- `0x18000a3e8`
- `0x18000adcc`
- `0x180027010`

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
0x18000a070  push    rbx
0x18000a072  push    rbp
0x18000a073  push    rsi
0x18000a074  push    rdi
0x18000a075  push    r14
0x18000a077  sub     rsp, 40h
0x18000a07b  mov     rsi, r9
0x18000a07e  mov     rbp, r8
0x18000a081  mov     r14d, edx
0x18000a084  test    edx, edx
0x18000a086  jz      short loc_18000A08D
0x18000a088  test    r8, r8
0x18000a08b  jz      short loc_18000A092
0x18000a08d  test    rsi, rsi
0x18000a090  jnz     short loc_18000A09C
0x18000a092  mov     eax, 80004003h
0x18000a097  jmp     loc_18000A127
0x18000a09c  mov     rcx, [rsp+68h+arg_28]
0x18000a0a4  lea     rdx, [rsp+68h+var_38]
0x18000a0a9  mov     [rsp+68h+var_38], 0
0x18000a0b2  call    ?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z; ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)
0x18000a0b7  mov     edi, eax
0x18000a0b9  test    eax, eax
0x18000a0bb  js      short loc_18000A125
0x18000a0bd  mov     rbx, [rsp+68h+var_38]
0x18000a0c2  mov     rcx, rbx
0x18000a0c5  mov     rax, [rbx]
0x18000a0c8  mov     rax, [rax+8]
0x18000a0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0d1  mov     rax, [rsp+68h+arg_20]
0x18000a0d9  lea     rcx, [rbx+10h]; this
0x18000a0dd  mov     r9, rsi; unsigned __int16 *
0x18000a0e0  mov     [rsp+68h+var_48], rax; struct IUnknown *
0x18000a0e5  mov     r8, rbp; unsigned __int16 **
0x18000a0e8  mov     edx, r14d; unsigned int
0x18000a0eb  call    ?Init@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@@Z; Microsoft::Windows::Performance::CEventTraceRelogger::Init(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *)
0x18000a0f0  mov     edi, eax
0x18000a0f2  test    eax, eax
0x18000a0f4  js      short loc_18000A116
0x18000a0f6  mov     rax, [rbx]
0x18000a0f9  mov     rcx, rbx
0x18000a0fc  mov     r8, [rsp+68h+arg_38]
0x18000a104  mov     rdx, [rsp+68h+arg_30]
0x18000a10c  mov     rax, [rax]
0x18000a10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a114  mov     edi, eax
0x18000a116  mov     rax, [rbx]
0x18000a119  mov     rcx, rbx
0x18000a11c  mov     rax, [rax+10h]
0x18000a120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a125  mov     eax, edi
0x18000a127  add     rsp, 40h
0x18000a12b  pop     r14
0x18000a12d  pop     rdi
0x18000a12e  pop     rsi
0x18000a12f  pop     rbp
0x18000a130  pop     rbx
0x18000a131  retn
```
