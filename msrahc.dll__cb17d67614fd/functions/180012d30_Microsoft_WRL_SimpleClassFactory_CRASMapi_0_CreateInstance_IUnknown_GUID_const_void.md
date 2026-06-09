# Microsoft::WRL::SimpleClassFactory<CRASMapi,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180012d30`
- end: `0x180012de7`
- name: `?CreateInstance@?$SimpleClassFactory@VCRASMapi@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180012510`
- `0x180012d30`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012d5a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012d5a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CRASMapi,0>::CreateInstance(
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
    v6 = Microsoft::WRL::Details::MakeAndInitialize<CRASMapi,IUnknown,>(&v10);
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
0x180012d30  mov     [rsp+arg_0], rbx
0x180012d35  mov     [rsp+arg_10], rsi
0x180012d3a  push    rdi
0x180012d3b  sub     rsp, 20h
0x180012d3f  mov     rdi, r9
0x180012d42  mov     rsi, r8
0x180012d45  mov     qword ptr [r9], 0
0x180012d4c  test    rdx, rdx
0x180012d4f  jz      short loc_180012D62
0x180012d51  xor     edx, edx
0x180012d53  mov     ebx, 80040110h
0x180012d58  mov     ecx, ebx
0x180012d5a  call    cs:__imp_RoOriginateError
0x180012d60  jmp     short loc_180012DD5
0x180012d62  mov     [rsp+28h+arg_8], 0
0x180012d6b  lea     rcx, [rsp+28h+arg_8]
0x180012d70  call    ??$MakeAndInitialize@VCRASMapi@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CRASMapi,IUnknown,>(IUnknown * *)
0x180012d75  mov     ebx, eax
0x180012d77  test    eax, eax
0x180012d79  jns     short loc_180012D9D
0x180012d7b  mov     rcx, [rsp+28h+arg_8]
0x180012d80  test    rcx, rcx
0x180012d83  jz      short loc_180012D9B
0x180012d85  mov     [rsp+28h+arg_8], 0
0x180012d8e  mov     rdx, [rcx]
0x180012d91  mov     rax, [rdx+10h]
0x180012d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d9a  nop
0x180012d9b  jmp     short loc_180012DD5
0x180012d9d  mov     rcx, [rsp+28h+arg_8]
0x180012da2  mov     rax, [rcx]
0x180012da5  mov     r8, rdi
0x180012da8  mov     rdx, rsi
0x180012dab  mov     rax, [rax]
0x180012dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012db3  mov     ebx, eax
0x180012db5  mov     rcx, [rsp+28h+arg_8]
0x180012dba  test    rcx, rcx
0x180012dbd  jz      short loc_180012DD5
0x180012dbf  mov     [rsp+28h+arg_8], 0
0x180012dc8  mov     rdx, [rcx]
0x180012dcb  mov     rax, [rdx+10h]
0x180012dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dd4  nop
0x180012dd5  mov     eax, ebx
0x180012dd7  mov     rbx, [rsp+28h+arg_0]
0x180012ddc  mov     rsi, [rsp+28h+arg_10]
0x180012de1  add     rsp, 20h
0x180012de5  pop     rdi
0x180012de6  retn
```
