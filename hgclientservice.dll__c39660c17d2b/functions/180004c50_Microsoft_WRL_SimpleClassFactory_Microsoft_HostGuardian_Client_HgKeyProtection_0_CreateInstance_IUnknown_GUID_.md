# Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgKeyProtection,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004c50`
- end: `0x180004d07`
- name: `?CreateInstance@?$SimpleClassFactory@VHgKeyProtection@Client@HostGuardian@Microsoft@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003190`
- `0x180004c50`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004c7a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004c7a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgKeyProtection,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v10)(_QWORD, __int64, _QWORD *); // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
  }
  else
  {
    v10 = 0;
    v6 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::HostGuardian::Client::HgKeyProtection,IUnknown,>(&v10);
    if ( v6 >= 0 )
    {
      v6 = (**v10)(v10, a3, a4);
      v8 = v10;
      if ( v10 )
      {
        v10 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v8)[2])(v8);
      }
    }
    else
    {
      v7 = v10;
      if ( v10 )
      {
        v10 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v7)[2])(v7);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004c50  mov     [rsp+arg_0], rbx
0x180004c55  mov     [rsp+arg_10], rsi
0x180004c5a  push    rdi
0x180004c5b  sub     rsp, 20h
0x180004c5f  mov     rdi, r9
0x180004c62  mov     rsi, r8
0x180004c65  mov     qword ptr [r9], 0
0x180004c6c  test    rdx, rdx
0x180004c6f  jz      short loc_180004C82
0x180004c71  xor     edx, edx
0x180004c73  mov     ebx, 80040110h
0x180004c78  mov     ecx, ebx
0x180004c7a  call    cs:__imp_RoOriginateError
0x180004c80  jmp     short loc_180004CF5
0x180004c82  mov     [rsp+28h+arg_8], 0
0x180004c8b  lea     rcx, [rsp+28h+arg_8]
0x180004c90  call    ??$MakeAndInitialize@VHgKeyProtection@Client@HostGuardian@Microsoft@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::HostGuardian::Client::HgKeyProtection,IUnknown,>(IUnknown * *)
0x180004c95  mov     ebx, eax
0x180004c97  test    eax, eax
0x180004c99  jns     short loc_180004CBD
0x180004c9b  mov     rcx, [rsp+28h+arg_8]
0x180004ca0  test    rcx, rcx
0x180004ca3  jz      short loc_180004CBB
0x180004ca5  mov     [rsp+28h+arg_8], 0
0x180004cae  mov     rdx, [rcx]
0x180004cb1  mov     rax, [rdx+10h]
0x180004cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cba  nop
0x180004cbb  jmp     short loc_180004CF5
0x180004cbd  mov     rcx, [rsp+28h+arg_8]
0x180004cc2  mov     rax, [rcx]
0x180004cc5  mov     r8, rdi
0x180004cc8  mov     rdx, rsi
0x180004ccb  mov     rax, [rax]
0x180004cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cd3  mov     ebx, eax
0x180004cd5  mov     rcx, [rsp+28h+arg_8]
0x180004cda  test    rcx, rcx
0x180004cdd  jz      short loc_180004CF5
0x180004cdf  mov     [rsp+28h+arg_8], 0
0x180004ce8  mov     rdx, [rcx]
0x180004ceb  mov     rax, [rdx+10h]
0x180004cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cf4  nop
0x180004cf5  mov     eax, ebx
0x180004cf7  mov     rbx, [rsp+28h+arg_0]
0x180004cfc  mov     rsi, [rsp+28h+arg_10]
0x180004d01  add     rsp, 20h
0x180004d05  pop     rdi
0x180004d06  retn
```
