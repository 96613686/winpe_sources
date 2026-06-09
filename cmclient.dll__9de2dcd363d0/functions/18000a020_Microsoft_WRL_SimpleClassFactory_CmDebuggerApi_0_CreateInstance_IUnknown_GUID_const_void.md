# Microsoft::WRL::SimpleClassFactory<CmDebuggerApi,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a020`
- end: `0x18000a144`
- name: `?CreateInstance@?$SimpleClassFactory@VCmDebuggerApi@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001574`
- `0x18000a020`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000a044`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000a044`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CmDebuggerApi,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // edi
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v13)(_QWORD, __int64, _QWORD *); // [rsp+58h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
    return v6;
  }
  v13 = 0;
  v7 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    v7[3] = 1;
    *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICmDebuggerApi>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v8 = &CmDebuggerApi::`vftable';
    v9 = ((__int64 (__fastcall *)(_DWORD *, GUID *, _QWORD))CmDebuggerApi::`vftable')(
           v8,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v13);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v9 >= 0 )
    {
      v6 = (**v13)(v13, a3, a4);
      v12 = v13;
      if ( v13 )
      {
        v13 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v12)[2])(v12);
      }
      return v6;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v10)[2])(v10);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a020  push    rbx
0x18000a022  push    rbp
0x18000a023  push    rsi
0x18000a024  push    rdi
0x18000a025  sub     rsp, 28h
0x18000a029  mov     rsi, r9
0x18000a02c  mov     rbp, r8
0x18000a02f  mov     qword ptr [r9], 0
0x18000a036  test    rdx, rdx
0x18000a039  jz      short loc_18000A04F
0x18000a03b  xor     edx, edx
0x18000a03d  mov     ebx, 80040110h
0x18000a042  mov     ecx, ebx
0x18000a044  call    cs:__imp_RoOriginateError
0x18000a04a  jmp     loc_18000A139
0x18000a04f  mov     [rsp+48h+arg_8], 0
0x18000a058  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a05f  mov     ecx, 10h; unsigned __int64
0x18000a064  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a069  mov     rbx, rax
0x18000a06c  test    rax, rax
0x18000a06f  jnz     short loc_18000A078
0x18000a071  mov     edi, 8007000Eh
0x18000a076  jmp     short loc_18000A0DD
0x18000a078  mov     dword ptr [rax+0Ch], 1
0x18000a07f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICmDebuggerApi@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICmDebuggerApi>::`vftable'
0x18000a086  mov     [rbx], rax
0x18000a089  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a090  test    rcx, rcx
0x18000a093  jz      short loc_18000A0A2
0x18000a095  mov     rax, [rcx]
0x18000a098  mov     rax, [rax+8]
0x18000a09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a1  nop
0x18000a0a2  lea     rax, ??_7CmDebuggerApi@@6B@; const CmDebuggerApi::`vftable'
0x18000a0a9  mov     [rbx], rax
0x18000a0ac  lea     r8, [rsp+48h+arg_8]
0x18000a0b1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000a0b8  mov     rcx, rbx
0x18000a0bb  mov     rax, cs:??_7CmDebuggerApi@@6B@; const CmDebuggerApi::`vftable'
0x18000a0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c7  mov     edi, eax
0x18000a0c9  mov     rax, [rbx]
0x18000a0cc  mov     rcx, rbx
0x18000a0cf  mov     rax, [rax+10h]
0x18000a0d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0d8  nop
0x18000a0d9  test    edi, edi
0x18000a0db  jns     short loc_18000A101
0x18000a0dd  mov     rcx, [rsp+48h+arg_8]
0x18000a0e2  test    rcx, rcx
0x18000a0e5  jz      short loc_18000A0FD
0x18000a0e7  mov     [rsp+48h+arg_8], 0
0x18000a0f0  mov     rdx, [rcx]
0x18000a0f3  mov     rax, [rdx+10h]
0x18000a0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0fc  nop
0x18000a0fd  mov     eax, edi
0x18000a0ff  jmp     short loc_18000A13B
0x18000a101  mov     rcx, [rsp+48h+arg_8]
0x18000a106  mov     rax, [rcx]
0x18000a109  mov     r8, rsi
0x18000a10c  mov     rdx, rbp
0x18000a10f  mov     rax, [rax]
0x18000a112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a117  mov     ebx, eax
0x18000a119  mov     rcx, [rsp+48h+arg_8]
0x18000a11e  test    rcx, rcx
0x18000a121  jz      short loc_18000A139
0x18000a123  mov     [rsp+48h+arg_8], 0
0x18000a12c  mov     rdx, [rcx]
0x18000a12f  mov     rax, [rdx+10h]
0x18000a133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a138  nop
0x18000a139  mov     eax, ebx
0x18000a13b  add     rsp, 28h
0x18000a13f  pop     rdi
0x18000a140  pop     rsi
0x18000a141  pop     rbp
0x18000a142  pop     rbx
0x18000a143  retn
```
