# Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180016190`
- end: `0x180016224`
- name: `?CreateInstance@?$SimpleClassFactory@VCHideInputPaneAnimationCoordinator@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180015bd8`
- `0x180016190`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800161ba`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800161ba`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CHideInputPaneAnimationCoordinator,0>::CreateInstance(
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
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CHideInputPaneAnimationCoordinator,IUnknown,>(&v11);
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
0x180016190  mov     [rsp+arg_0], rbx
0x180016195  mov     [rsp+arg_10], rsi
0x18001619a  push    rdi
0x18001619b  sub     rsp, 20h
0x18001619f  mov     qword ptr [r9], 0
0x1800161a6  mov     rdi, r9
0x1800161a9  mov     rsi, r8
0x1800161ac  test    rdx, rdx
0x1800161af  jz      short loc_1800161C2
0x1800161b1  mov     ebx, 80040110h
0x1800161b6  xor     edx, edx
0x1800161b8  mov     ecx, ebx
0x1800161ba  call    cs:__imp_RoOriginateError
0x1800161c0  jmp     short loc_180016212
0x1800161c2  lea     rcx, [rsp+28h+arg_8]
0x1800161c7  mov     [rsp+28h+arg_8], 0
0x1800161d0  call    ??$MakeAndInitialize@VCHideInputPaneAnimationCoordinator@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CHideInputPaneAnimationCoordinator,IUnknown,>(IUnknown * *)
0x1800161d5  mov     rcx, [rsp+28h+arg_8]
0x1800161da  mov     ebx, eax
0x1800161dc  test    eax, eax
0x1800161de  js      short loc_1800161F8
0x1800161e0  mov     rax, [rcx]
0x1800161e3  mov     r8, rdi
0x1800161e6  mov     rdx, rsi
0x1800161e9  mov     rax, [rax]
0x1800161ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161f1  mov     rcx, [rsp+28h+arg_8]
0x1800161f6  mov     ebx, eax
0x1800161f8  test    rcx, rcx
0x1800161fb  jz      short loc_180016212
0x1800161fd  mov     [rsp+28h+arg_8], 0
0x180016206  mov     rdx, [rcx]
0x180016209  mov     rax, [rdx+10h]
0x18001620d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016212  mov     rsi, [rsp+28h+arg_10]
0x180016217  mov     eax, ebx
0x180016219  mov     rbx, [rsp+28h+arg_0]
0x18001621e  add     rsp, 20h
0x180016222  pop     rdi
0x180016223  retn
```
