# Microsoft::WRL::SimpleClassFactory<CEASConsentPopup,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180001f80`
- end: `0x180002014`
- name: `?CreateInstance@?$SimpleClassFactory@VCEASConsentPopup@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001c84`
- `0x180001f80`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180001faa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180001faa`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CEASConsentPopup,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  int v7; // eax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD *); // rcx
  unsigned int v9; // eax
  __int64 (__fastcall ***v11)(_QWORD, __int64, _QWORD *); // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
  }
  else
  {
    v11 = 0;
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CEASConsentPopup,IUnknown,>(&v11);
    v8 = v11;
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = (**v11)(v11, a3, a4);
      v8 = v11;
      v6 = v9;
    }
    if ( v8 )
    {
      v11 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v8)[2])(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180001f80  mov     [rsp+arg_0], rbx
0x180001f85  mov     [rsp+arg_10], rsi
0x180001f8a  push    rdi
0x180001f8b  sub     rsp, 20h
0x180001f8f  mov     qword ptr [r9], 0
0x180001f96  mov     rdi, r9
0x180001f99  mov     rsi, r8
0x180001f9c  test    rdx, rdx
0x180001f9f  jz      short loc_180001FB2
0x180001fa1  mov     ebx, 80040110h
0x180001fa6  xor     edx, edx
0x180001fa8  mov     ecx, ebx
0x180001faa  call    cs:__imp_RoOriginateError
0x180001fb0  jmp     short loc_180002002
0x180001fb2  lea     rcx, [rsp+28h+arg_8]
0x180001fb7  mov     [rsp+28h+arg_8], 0
0x180001fc0  call    ??$MakeAndInitialize@VCEASConsentPopup@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CEASConsentPopup,IUnknown,>(IUnknown * *)
0x180001fc5  mov     rcx, [rsp+28h+arg_8]
0x180001fca  mov     ebx, eax
0x180001fcc  test    eax, eax
0x180001fce  js      short loc_180001FE8
0x180001fd0  mov     rax, [rcx]
0x180001fd3  mov     r8, rdi
0x180001fd6  mov     rdx, rsi
0x180001fd9  mov     rax, [rax]
0x180001fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fe1  mov     rcx, [rsp+28h+arg_8]
0x180001fe6  mov     ebx, eax
0x180001fe8  test    rcx, rcx
0x180001feb  jz      short loc_180002002
0x180001fed  mov     [rsp+28h+arg_8], 0
0x180001ff6  mov     rdx, [rcx]
0x180001ff9  mov     rax, [rdx+10h]
0x180001ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002002  mov     rsi, [rsp+28h+arg_10]
0x180002007  mov     eax, ebx
0x180002009  mov     rbx, [rsp+28h+arg_0]
0x18000200e  add     rsp, 20h
0x180002012  pop     rdi
0x180002013  retn
```
