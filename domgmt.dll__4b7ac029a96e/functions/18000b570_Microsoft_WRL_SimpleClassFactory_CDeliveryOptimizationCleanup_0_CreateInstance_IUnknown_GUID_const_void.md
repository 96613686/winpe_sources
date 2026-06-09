# Microsoft::WRL::SimpleClassFactory<CDeliveryOptimizationCleanup,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000b570`
- end: `0x18000b627`
- name: `?CreateInstance@?$SimpleClassFactory@VCDeliveryOptimizationCleanup@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b33c`
- `0x18000b570`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b59a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b59a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CDeliveryOptimizationCleanup,0>::CreateInstance(
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
    v6 = Microsoft::WRL::Details::MakeAndInitialize<CDeliveryOptimizationCleanup,IUnknown,>(&v10);
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
0x18000b570  mov     [rsp+arg_0], rbx
0x18000b575  mov     [rsp+arg_10], rsi
0x18000b57a  push    rdi
0x18000b57b  sub     rsp, 20h
0x18000b57f  mov     rdi, r9
0x18000b582  mov     rsi, r8
0x18000b585  mov     qword ptr [r9], 0
0x18000b58c  test    rdx, rdx
0x18000b58f  jz      short loc_18000B5A2
0x18000b591  xor     edx, edx
0x18000b593  mov     ebx, 80040110h
0x18000b598  mov     ecx, ebx
0x18000b59a  call    cs:__imp_RoOriginateError
0x18000b5a0  jmp     short loc_18000B615
0x18000b5a2  mov     [rsp+28h+arg_8], 0
0x18000b5ab  lea     rcx, [rsp+28h+arg_8]
0x18000b5b0  call    ??$MakeAndInitialize@VCDeliveryOptimizationCleanup@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CDeliveryOptimizationCleanup,IUnknown,>(IUnknown * *)
0x18000b5b5  mov     ebx, eax
0x18000b5b7  test    eax, eax
0x18000b5b9  jns     short loc_18000B5DD
0x18000b5bb  mov     rcx, [rsp+28h+arg_8]
0x18000b5c0  test    rcx, rcx
0x18000b5c3  jz      short loc_18000B5DB
0x18000b5c5  mov     [rsp+28h+arg_8], 0
0x18000b5ce  mov     rdx, [rcx]
0x18000b5d1  mov     rax, [rdx+10h]
0x18000b5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5da  nop
0x18000b5db  jmp     short loc_18000B615
0x18000b5dd  mov     rcx, [rsp+28h+arg_8]
0x18000b5e2  mov     rax, [rcx]
0x18000b5e5  mov     r8, rdi
0x18000b5e8  mov     rdx, rsi
0x18000b5eb  mov     rax, [rax]
0x18000b5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5f3  mov     ebx, eax
0x18000b5f5  mov     rcx, [rsp+28h+arg_8]
0x18000b5fa  test    rcx, rcx
0x18000b5fd  jz      short loc_18000B615
0x18000b5ff  mov     [rsp+28h+arg_8], 0
0x18000b608  mov     rdx, [rcx]
0x18000b60b  mov     rax, [rdx+10h]
0x18000b60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b614  nop
0x18000b615  mov     eax, ebx
0x18000b617  mov     rbx, [rsp+28h+arg_0]
0x18000b61c  mov     rsi, [rsp+28h+arg_10]
0x18000b621  add     rsp, 20h
0x18000b625  pop     rdi
0x18000b626  retn
```
