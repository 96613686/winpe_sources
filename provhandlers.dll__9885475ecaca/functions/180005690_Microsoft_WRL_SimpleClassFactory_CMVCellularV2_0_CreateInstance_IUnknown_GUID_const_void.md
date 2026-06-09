# Microsoft::WRL::SimpleClassFactory<CMVCellularV2,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005690`
- end: `0x180005747`
- name: `?CreateInstance@?$SimpleClassFactory@VCMVCellularV2@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800035ac`
- `0x180005690`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800056ba`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800056ba`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CMVCellularV2,0>::CreateInstance(
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
    v6 = Microsoft::WRL::Details::MakeAndInitialize<CMVCellularV2,IUnknown,>(&v10);
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
0x180005690  mov     [rsp+arg_0], rbx
0x180005695  mov     [rsp+arg_10], rsi
0x18000569a  push    rdi
0x18000569b  sub     rsp, 20h
0x18000569f  mov     rdi, r9
0x1800056a2  mov     rsi, r8
0x1800056a5  mov     qword ptr [r9], 0
0x1800056ac  test    rdx, rdx
0x1800056af  jz      short loc_1800056C2
0x1800056b1  xor     edx, edx
0x1800056b3  mov     ebx, 80040110h
0x1800056b8  mov     ecx, ebx
0x1800056ba  call    cs:__imp_RoOriginateError
0x1800056c0  jmp     short loc_180005735
0x1800056c2  mov     [rsp+28h+arg_8], 0
0x1800056cb  lea     rcx, [rsp+28h+arg_8]
0x1800056d0  call    ??$MakeAndInitialize@VCMVCellularV2@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMVCellularV2,IUnknown,>(IUnknown * *)
0x1800056d5  mov     ebx, eax
0x1800056d7  test    eax, eax
0x1800056d9  jns     short loc_1800056FD
0x1800056db  mov     rcx, [rsp+28h+arg_8]
0x1800056e0  test    rcx, rcx
0x1800056e3  jz      short loc_1800056FB
0x1800056e5  mov     [rsp+28h+arg_8], 0
0x1800056ee  mov     rdx, [rcx]
0x1800056f1  mov     rax, [rdx+10h]
0x1800056f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056fa  nop
0x1800056fb  jmp     short loc_180005735
0x1800056fd  mov     rcx, [rsp+28h+arg_8]
0x180005702  mov     rax, [rcx]
0x180005705  mov     r8, rdi
0x180005708  mov     rdx, rsi
0x18000570b  mov     rax, [rax]
0x18000570e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005713  mov     ebx, eax
0x180005715  mov     rcx, [rsp+28h+arg_8]
0x18000571a  test    rcx, rcx
0x18000571d  jz      short loc_180005735
0x18000571f  mov     [rsp+28h+arg_8], 0
0x180005728  mov     rdx, [rcx]
0x18000572b  mov     rax, [rdx+10h]
0x18000572f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005734  nop
0x180005735  mov     eax, ebx
0x180005737  mov     rbx, [rsp+28h+arg_0]
0x18000573c  mov     rsi, [rsp+28h+arg_10]
0x180005741  add     rsp, 20h
0x180005745  pop     rdi
0x180005746  retn
```
