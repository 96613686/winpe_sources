# CServiceCallback::GetTeredoReference(IUnknown * *)

- ea: `0x18000d0d0`
- end: `0x18000d210`
- name: `?GetTeredoReference@CServiceCallback@@EEBAJPEAPEAUIUnknown@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(CServiceCallback *this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800022cc`
- `0x180002ee4`
- `0x180005964`
- `0x18000d0d0`
- `0x18000e010`

## import_xrefs

- `ext-ms-win-networking-teredo-l1-1-0!TeredoExtAcquireTeredoConsumerHandle` at `0x18000d16a`
- `ext-ms-win-networking-teredo-l1-1-0!TeredoExtAcquireTeredoConsumerHandle` at `0x18000d16a`

## string_xrefs

- `0x18000d17e`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`

## pseudocode

```c
__int64 __fastcall CServiceCallback::GetTeredoReference(CServiceCallback *this, struct IUnknown **a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  int v5; // edi
  int v6; // eax
  struct IUnknown *v7; // rcx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct IUnknown *v11; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v11 = 0;
  v3 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( !v3 )
  {
    v5 = -2147024882;
    goto LABEL_11;
  }
  *((_DWORD *)v3 + 3) = 1;
  *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v4 = &CTeredoConsumer::`vftable';
  v4[2] = 0;
  if ( !(unsigned __int8)IsTeredoExtAcquireTeredoConsumerHandlePresent() )
  {
    v5 = -2147467263;
LABEL_9:
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    goto LABEL_11;
  }
  v6 = TeredoExtAcquireTeredoConsumerHandle(2, v4 + 2);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)(unsigned int)v6,
      v9);
    goto LABEL_9;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IUnknown **))*v4)(
         v4,
         &GUID_00000000_0000_0000_c000_000000000046,
         &v11);
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  if ( v5 >= 0 )
  {
    *a2 = v11;
    return 0;
  }
LABEL_11:
  v7 = v11;
  if ( v11 )
  {
    v11 = 0;
    ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d0d0  mov     [rsp+arg_0], rbx
0x18000d0d5  mov     [rsp+arg_10], rsi
0x18000d0da  push    rdi; int
0x18000d0db  sub     rsp, 20h
0x18000d0df  mov     rsi, rdx
0x18000d0e2  mov     qword ptr [rdx], 0
0x18000d0e9  mov     [rsp+28h+arg_8], 0
0x18000d0f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d0f9  mov     ecx, 18h; unsigned __int64
0x18000d0fe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d103  mov     rbx, rax
0x18000d106  test    rax, rax
0x18000d109  jnz     short loc_18000D115
0x18000d10b  mov     edi, 8007000Eh
0x18000d110  jmp     loc_18000D1D2
0x18000d115  mov     dword ptr [rax+0Ch], 1
0x18000d11c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x18000d123  mov     [rbx], rax
0x18000d126  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d12d  test    rcx, rcx
0x18000d130  jz      short loc_18000D13F
0x18000d132  mov     rax, [rcx]
0x18000d135  mov     rax, [rax+8]
0x18000d139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d13e  nop
0x18000d13f  lea     rax, ??_7CTeredoConsumer@@6B@; const CTeredoConsumer::`vftable'
0x18000d146  mov     [rbx], rax
0x18000d149  mov     qword ptr [rbx+10h], 0
0x18000d151  call    IsTeredoExtAcquireTeredoConsumerHandlePresent
0x18000d156  test    al, al
0x18000d158  jnz     short loc_18000D161
0x18000d15a  mov     edi, 80004001h
0x18000d15f  jmp     short loc_18000D190
0x18000d161  lea     rdx, [rbx+10h]
0x18000d165  mov     ecx, 2
0x18000d16a  call    cs:__imp_TeredoExtAcquireTeredoConsumerHandle
0x18000d170  mov     edi, eax
0x18000d172  test    eax, eax
0x18000d174  jns     short loc_18000D1A2
0x18000d176  mov     rcx, [rsp+28h]; this
0x18000d17b  mov     r9d, eax; char *
0x18000d17e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x18000d185  mov     edx, 0Fh; void *
0x18000d18a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d18f  nop
0x18000d190  mov     rax, [rbx]
0x18000d193  mov     rcx, rbx
0x18000d196  mov     rax, [rax+10h]
0x18000d19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19f  nop
0x18000d1a0  jmp     short loc_18000D1D2
0x18000d1a2  mov     rax, [rbx]
0x18000d1a5  lea     r8, [rsp+28h+arg_8]
0x18000d1aa  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000d1b1  mov     rcx, rbx
0x18000d1b4  mov     rax, [rax]
0x18000d1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1bc  mov     edi, eax
0x18000d1be  mov     rax, [rbx]
0x18000d1c1  mov     rcx, rbx
0x18000d1c4  mov     rax, [rax+10h]
0x18000d1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1cd  nop
0x18000d1ce  test    edi, edi
0x18000d1d0  jns     short loc_18000D1F6
0x18000d1d2  mov     rcx, [rsp+28h+arg_8]
0x18000d1d7  test    rcx, rcx
0x18000d1da  jz      short loc_18000D1F2
0x18000d1dc  mov     [rsp+28h+arg_8], 0
0x18000d1e5  mov     rdx, [rcx]
0x18000d1e8  mov     rax, [rdx+10h]
0x18000d1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1f1  nop
0x18000d1f2  mov     eax, edi
0x18000d1f4  jmp     short loc_18000D200
0x18000d1f6  mov     rax, [rsp+28h+arg_8]
0x18000d1fb  mov     [rsi], rax
0x18000d1fe  xor     eax, eax
0x18000d200  mov     rbx, [rsp+28h+arg_0]
0x18000d205  mov     rsi, [rsp+28h+arg_10]
0x18000d20a  add     rsp, 20h
0x18000d20e  pop     rdi
0x18000d20f  retn
```
