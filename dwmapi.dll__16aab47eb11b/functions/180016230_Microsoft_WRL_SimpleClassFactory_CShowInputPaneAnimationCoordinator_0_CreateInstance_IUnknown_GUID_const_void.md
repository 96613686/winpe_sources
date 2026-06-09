# Microsoft::WRL::SimpleClassFactory<CShowInputPaneAnimationCoordinator,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180016230`
- end: `0x1800162c4`
- name: `?CreateInstance@?$SimpleClassFactory@VCShowInputPaneAnimationCoordinator@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180015c84`
- `0x180016230`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001625a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001625a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CShowInputPaneAnimationCoordinator,0>::CreateInstance(
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
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CShowInputPaneAnimationCoordinator,IUnknown,>(&v11);
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
0x180016230  mov     [rsp+arg_0], rbx
0x180016235  mov     [rsp+arg_10], rsi
0x18001623a  push    rdi
0x18001623b  sub     rsp, 20h
0x18001623f  mov     qword ptr [r9], 0
0x180016246  mov     rdi, r9
0x180016249  mov     rsi, r8
0x18001624c  test    rdx, rdx
0x18001624f  jz      short loc_180016262
0x180016251  mov     ebx, 80040110h
0x180016256  xor     edx, edx
0x180016258  mov     ecx, ebx
0x18001625a  call    cs:__imp_RoOriginateError
0x180016260  jmp     short loc_1800162B2
0x180016262  lea     rcx, [rsp+28h+arg_8]
0x180016267  mov     [rsp+28h+arg_8], 0
0x180016270  call    ??$MakeAndInitialize@VCShowInputPaneAnimationCoordinator@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CShowInputPaneAnimationCoordinator,IUnknown,>(IUnknown * *)
0x180016275  mov     rcx, [rsp+28h+arg_8]
0x18001627a  mov     ebx, eax
0x18001627c  test    eax, eax
0x18001627e  js      short loc_180016298
0x180016280  mov     rax, [rcx]
0x180016283  mov     r8, rdi
0x180016286  mov     rdx, rsi
0x180016289  mov     rax, [rax]
0x18001628c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016291  mov     rcx, [rsp+28h+arg_8]
0x180016296  mov     ebx, eax
0x180016298  test    rcx, rcx
0x18001629b  jz      short loc_1800162B2
0x18001629d  mov     [rsp+28h+arg_8], 0
0x1800162a6  mov     rdx, [rcx]
0x1800162a9  mov     rax, [rdx+10h]
0x1800162ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162b2  mov     rsi, [rsp+28h+arg_10]
0x1800162b7  mov     eax, ebx
0x1800162b9  mov     rbx, [rsp+28h+arg_0]
0x1800162be  add     rsp, 20h
0x1800162c2  pop     rdi
0x1800162c3  retn
```
