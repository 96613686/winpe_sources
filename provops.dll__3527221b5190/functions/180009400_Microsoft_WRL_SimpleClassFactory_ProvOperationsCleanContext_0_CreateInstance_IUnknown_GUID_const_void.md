# Microsoft::WRL::SimpleClassFactory<ProvOperationsCleanContext,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009400`
- end: `0x180009502`
- name: `?CreateInstance@?$SimpleClassFactory@VProvOperationsCleanContext@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003e78`
- `0x180009400`
- `0x18000ce70`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009424`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009424`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<ProvOperationsCleanContext,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  ProvOperations *v7; // rax
  ProvOperations *v8; // rbx
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
  v7 = (ProvOperations *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    ProvOperations::ProvOperations(v7);
    *(_QWORD *)v8 = &ProvOperationsCleanContext::`vftable';
    v9 = ((__int64 (__fastcall *)(ProvOperations *, GUID *, _QWORD))ProvOperationsCleanContext::`vftable')(
           v8,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v13);
    (*(void (__fastcall **)(ProvOperations *))(*(_QWORD *)v8 + 16LL))(v8);
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
0x180009400  push    rbx
0x180009402  push    rbp
0x180009403  push    rsi
0x180009404  push    rdi
0x180009405  sub     rsp, 28h
0x180009409  mov     rsi, r9
0x18000940c  mov     rbp, r8
0x18000940f  mov     qword ptr [r9], 0
0x180009416  test    rdx, rdx
0x180009419  jz      short loc_18000942F
0x18000941b  xor     edx, edx
0x18000941d  mov     ebx, 80040110h
0x180009422  mov     ecx, ebx
0x180009424  call    cs:__imp_RoOriginateError
0x18000942a  jmp     loc_1800094F7
0x18000942f  mov     [rsp+48h+arg_8], 0
0x180009438  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000943f  mov     ecx, 40h ; '@'; unsigned __int64
0x180009444  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009449  mov     rbx, rax
0x18000944c  test    rax, rax
0x18000944f  jnz     short loc_180009458
0x180009451  mov     edi, 8007000Eh
0x180009456  jmp     short loc_18000949B
0x180009458  mov     rcx, rbx; this
0x18000945b  call    ??0ProvOperations@@QEAA@XZ; ProvOperations::ProvOperations(void)
0x180009460  lea     rax, ??_7ProvOperationsCleanContext@@6B@; const ProvOperationsCleanContext::`vftable'
0x180009467  mov     [rbx], rax
0x18000946a  lea     r8, [rsp+48h+arg_8]
0x18000946f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009476  mov     rcx, rbx
0x180009479  mov     rax, cs:??_7ProvOperationsCleanContext@@6B@; const ProvOperationsCleanContext::`vftable'
0x180009480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009485  mov     edi, eax
0x180009487  mov     rax, [rbx]
0x18000948a  mov     rcx, rbx
0x18000948d  mov     rax, [rax+10h]
0x180009491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009496  nop
0x180009497  test    edi, edi
0x180009499  jns     short loc_1800094BF
0x18000949b  mov     rcx, [rsp+48h+arg_8]
0x1800094a0  test    rcx, rcx
0x1800094a3  jz      short loc_1800094BB
0x1800094a5  mov     [rsp+48h+arg_8], 0
0x1800094ae  mov     rdx, [rcx]
0x1800094b1  mov     rax, [rdx+10h]
0x1800094b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ba  nop
0x1800094bb  mov     eax, edi
0x1800094bd  jmp     short loc_1800094F9
0x1800094bf  mov     rcx, [rsp+48h+arg_8]
0x1800094c4  mov     rax, [rcx]
0x1800094c7  mov     r8, rsi
0x1800094ca  mov     rdx, rbp
0x1800094cd  mov     rax, [rax]
0x1800094d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d5  mov     ebx, eax
0x1800094d7  mov     rcx, [rsp+48h+arg_8]
0x1800094dc  test    rcx, rcx
0x1800094df  jz      short loc_1800094F7
0x1800094e1  mov     [rsp+48h+arg_8], 0
0x1800094ea  mov     rdx, [rcx]
0x1800094ed  mov     rax, [rdx+10h]
0x1800094f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f6  nop
0x1800094f7  mov     eax, ebx
0x1800094f9  add     rsp, 28h
0x1800094fd  pop     rdi
0x1800094fe  pop     rsi
0x1800094ff  pop     rbp
0x180009500  pop     rbx
0x180009501  retn
```
