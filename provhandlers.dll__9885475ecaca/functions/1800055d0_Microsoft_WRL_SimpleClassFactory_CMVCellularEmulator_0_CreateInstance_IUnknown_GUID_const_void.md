# Microsoft::WRL::SimpleClassFactory<CMVCellularEmulator,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800055d0`
- end: `0x180005687`
- name: `?CreateInstance@?$SimpleClassFactory@VCMVCellularEmulator@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800034fc`
- `0x1800055d0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800055fa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800055fa`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CMVCellularEmulator,0>::CreateInstance(
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
    v6 = Microsoft::WRL::Details::MakeAndInitialize<CMVCellularEmulator,IUnknown,>(&v10);
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
0x1800055d0  mov     [rsp+arg_0], rbx
0x1800055d5  mov     [rsp+arg_10], rsi
0x1800055da  push    rdi
0x1800055db  sub     rsp, 20h
0x1800055df  mov     rdi, r9
0x1800055e2  mov     rsi, r8
0x1800055e5  mov     qword ptr [r9], 0
0x1800055ec  test    rdx, rdx
0x1800055ef  jz      short loc_180005602
0x1800055f1  xor     edx, edx
0x1800055f3  mov     ebx, 80040110h
0x1800055f8  mov     ecx, ebx
0x1800055fa  call    cs:__imp_RoOriginateError
0x180005600  jmp     short loc_180005675
0x180005602  mov     [rsp+28h+arg_8], 0
0x18000560b  lea     rcx, [rsp+28h+arg_8]
0x180005610  call    ??$MakeAndInitialize@VCMVCellularEmulator@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMVCellularEmulator,IUnknown,>(IUnknown * *)
0x180005615  mov     ebx, eax
0x180005617  test    eax, eax
0x180005619  jns     short loc_18000563D
0x18000561b  mov     rcx, [rsp+28h+arg_8]
0x180005620  test    rcx, rcx
0x180005623  jz      short loc_18000563B
0x180005625  mov     [rsp+28h+arg_8], 0
0x18000562e  mov     rdx, [rcx]
0x180005631  mov     rax, [rdx+10h]
0x180005635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000563a  nop
0x18000563b  jmp     short loc_180005675
0x18000563d  mov     rcx, [rsp+28h+arg_8]
0x180005642  mov     rax, [rcx]
0x180005645  mov     r8, rdi
0x180005648  mov     rdx, rsi
0x18000564b  mov     rax, [rax]
0x18000564e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005653  mov     ebx, eax
0x180005655  mov     rcx, [rsp+28h+arg_8]
0x18000565a  test    rcx, rcx
0x18000565d  jz      short loc_180005675
0x18000565f  mov     [rsp+28h+arg_8], 0
0x180005668  mov     rdx, [rcx]
0x18000566b  mov     rax, [rdx+10h]
0x18000566f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005674  nop
0x180005675  mov     eax, ebx
0x180005677  mov     rbx, [rsp+28h+arg_0]
0x18000567c  mov     rsi, [rsp+28h+arg_10]
0x180005681  add     rsp, 20h
0x180005685  pop     rdi
0x180005686  retn
```
