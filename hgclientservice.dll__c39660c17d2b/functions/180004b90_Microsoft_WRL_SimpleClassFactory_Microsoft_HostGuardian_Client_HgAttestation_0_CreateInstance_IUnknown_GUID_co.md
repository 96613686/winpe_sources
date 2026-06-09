# Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgAttestation,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004b90`
- end: `0x180004c47`
- name: `?CreateInstance@?$SimpleClassFactory@VHgAttestation@Client@HostGuardian@Microsoft@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800030bc`
- `0x180004b90`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004bba`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004bba`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<Microsoft::HostGuardian::Client::HgAttestation,0>::CreateInstance(
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
    v6 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::HostGuardian::Client::HgAttestation,IUnknown,>(&v10);
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
0x180004b90  mov     [rsp+arg_0], rbx
0x180004b95  mov     [rsp+arg_10], rsi
0x180004b9a  push    rdi
0x180004b9b  sub     rsp, 20h
0x180004b9f  mov     rdi, r9
0x180004ba2  mov     rsi, r8
0x180004ba5  mov     qword ptr [r9], 0
0x180004bac  test    rdx, rdx
0x180004baf  jz      short loc_180004BC2
0x180004bb1  xor     edx, edx
0x180004bb3  mov     ebx, 80040110h
0x180004bb8  mov     ecx, ebx
0x180004bba  call    cs:__imp_RoOriginateError
0x180004bc0  jmp     short loc_180004C35
0x180004bc2  mov     [rsp+28h+arg_8], 0
0x180004bcb  lea     rcx, [rsp+28h+arg_8]
0x180004bd0  call    ??$MakeAndInitialize@VHgAttestation@Client@HostGuardian@Microsoft@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::HostGuardian::Client::HgAttestation,IUnknown,>(IUnknown * *)
0x180004bd5  mov     ebx, eax
0x180004bd7  test    eax, eax
0x180004bd9  jns     short loc_180004BFD
0x180004bdb  mov     rcx, [rsp+28h+arg_8]
0x180004be0  test    rcx, rcx
0x180004be3  jz      short loc_180004BFB
0x180004be5  mov     [rsp+28h+arg_8], 0
0x180004bee  mov     rdx, [rcx]
0x180004bf1  mov     rax, [rdx+10h]
0x180004bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bfa  nop
0x180004bfb  jmp     short loc_180004C35
0x180004bfd  mov     rcx, [rsp+28h+arg_8]
0x180004c02  mov     rax, [rcx]
0x180004c05  mov     r8, rdi
0x180004c08  mov     rdx, rsi
0x180004c0b  mov     rax, [rax]
0x180004c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c13  mov     ebx, eax
0x180004c15  mov     rcx, [rsp+28h+arg_8]
0x180004c1a  test    rcx, rcx
0x180004c1d  jz      short loc_180004C35
0x180004c1f  mov     [rsp+28h+arg_8], 0
0x180004c28  mov     rdx, [rcx]
0x180004c2b  mov     rax, [rdx+10h]
0x180004c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c34  nop
0x180004c35  mov     eax, ebx
0x180004c37  mov     rbx, [rsp+28h+arg_0]
0x180004c3c  mov     rsi, [rsp+28h+arg_10]
0x180004c41  add     rsp, 20h
0x180004c45  pop     rdi
0x180004c46  retn
```
