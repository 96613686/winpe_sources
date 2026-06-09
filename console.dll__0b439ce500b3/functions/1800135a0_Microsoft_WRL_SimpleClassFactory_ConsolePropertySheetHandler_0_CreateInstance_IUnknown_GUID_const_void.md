# Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800135a0`
- end: `0x180013627`
- name: `?CreateInstance@?$SimpleClassFactory@VConsolePropertySheetHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004dcc`
- `0x180013080`
- `0x1800135a0`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800135ca`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800135ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<ConsolePropertySheetHandler,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 (__fastcall ***v8)(_QWORD, __int64, _QWORD *); // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
  }
  else
  {
    v8 = 0;
    v6 = Microsoft::WRL::Details::MakeAndInitialize<ConsolePropertySheetHandler,IUnknown,>(&v8);
    if ( v6 >= 0 )
      v6 = (**v8)(v8, a3, a4);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800135a0  mov     [rsp+arg_0], rbx
0x1800135a5  mov     [rsp+arg_10], rsi
0x1800135aa  push    rdi
0x1800135ab  sub     rsp, 20h
0x1800135af  mov     rdi, r9
0x1800135b2  mov     rsi, r8
0x1800135b5  mov     qword ptr [r9], 0
0x1800135bc  test    rdx, rdx
0x1800135bf  jz      short loc_1800135D8
0x1800135c1  xor     edx, edx
0x1800135c3  mov     ebx, 80040110h
0x1800135c8  mov     ecx, ebx
0x1800135ca  call    cs:__imp_RoOriginateError
0x1800135d1  nop     dword ptr [rax+rax+00h]
0x1800135d6  jmp     short loc_180013614
0x1800135d8  mov     [rsp+28h+arg_8], 0
0x1800135e1  lea     rcx, [rsp+28h+arg_8]
0x1800135e6  call    ??$MakeAndInitialize@VConsolePropertySheetHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ConsolePropertySheetHandler,IUnknown,>(IUnknown * *)
0x1800135eb  mov     ebx, eax
0x1800135ed  test    eax, eax
0x1800135ef  js      short loc_18001360A
0x1800135f1  mov     rcx, [rsp+28h+arg_8]
0x1800135f6  mov     rax, [rcx]
0x1800135f9  mov     r8, rdi
0x1800135fc  mov     rdx, rsi
0x1800135ff  mov     rax, [rax]
0x180013602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013607  nop
0x180013608  mov     ebx, eax
0x18001360a  lea     rcx, [rsp+28h+arg_8]
0x18001360f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013614  mov     eax, ebx
0x180013616  mov     rbx, [rsp+28h+arg_0]
0x18001361b  mov     rsi, [rsp+28h+arg_10]
0x180013620  add     rsp, 20h
0x180013624  pop     rdi
0x180013625  retn
```
