# Microsoft::WRL::SimpleClassFactory<CMVCellularEmulator2,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005510`
- end: `0x1800055c7`
- name: `?CreateInstance@?$SimpleClassFactory@VCMVCellularEmulator2@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000344c`
- `0x180005510`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000553a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000553a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CMVCellularEmulator2,0>::CreateInstance(
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
    v6 = Microsoft::WRL::Details::MakeAndInitialize<CMVCellularEmulator2,IUnknown,>(&v10);
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
0x180005510  mov     [rsp+arg_0], rbx
0x180005515  mov     [rsp+arg_10], rsi
0x18000551a  push    rdi
0x18000551b  sub     rsp, 20h
0x18000551f  mov     rdi, r9
0x180005522  mov     rsi, r8
0x180005525  mov     qword ptr [r9], 0
0x18000552c  test    rdx, rdx
0x18000552f  jz      short loc_180005542
0x180005531  xor     edx, edx
0x180005533  mov     ebx, 80040110h
0x180005538  mov     ecx, ebx
0x18000553a  call    cs:__imp_RoOriginateError
0x180005540  jmp     short loc_1800055B5
0x180005542  mov     [rsp+28h+arg_8], 0
0x18000554b  lea     rcx, [rsp+28h+arg_8]
0x180005550  call    ??$MakeAndInitialize@VCMVCellularEmulator2@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMVCellularEmulator2,IUnknown,>(IUnknown * *)
0x180005555  mov     ebx, eax
0x180005557  test    eax, eax
0x180005559  jns     short loc_18000557D
0x18000555b  mov     rcx, [rsp+28h+arg_8]
0x180005560  test    rcx, rcx
0x180005563  jz      short loc_18000557B
0x180005565  mov     [rsp+28h+arg_8], 0
0x18000556e  mov     rdx, [rcx]
0x180005571  mov     rax, [rdx+10h]
0x180005575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000557a  nop
0x18000557b  jmp     short loc_1800055B5
0x18000557d  mov     rcx, [rsp+28h+arg_8]
0x180005582  mov     rax, [rcx]
0x180005585  mov     r8, rdi
0x180005588  mov     rdx, rsi
0x18000558b  mov     rax, [rax]
0x18000558e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005593  mov     ebx, eax
0x180005595  mov     rcx, [rsp+28h+arg_8]
0x18000559a  test    rcx, rcx
0x18000559d  jz      short loc_1800055B5
0x18000559f  mov     [rsp+28h+arg_8], 0
0x1800055a8  mov     rdx, [rcx]
0x1800055ab  mov     rax, [rdx+10h]
0x1800055af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b4  nop
0x1800055b5  mov     eax, ebx
0x1800055b7  mov     rbx, [rsp+28h+arg_0]
0x1800055bc  mov     rsi, [rsp+28h+arg_10]
0x1800055c1  add     rsp, 20h
0x1800055c5  pop     rdi
0x1800055c6  retn
```
