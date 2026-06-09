# Microsoft::WRL::SimpleClassFactory<ProvOperations,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009300`
- end: `0x1800093f7`
- name: `?CreateInstance@?$SimpleClassFactory@VProvOperations@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `247`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003e78`
- `0x180009300`
- `0x18000ce70`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009324`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009324`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<ProvOperations,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  ProvOperations *v7; // rax
  int v8; // edi
  ProvOperations *v9; // rbx
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
  if ( v7 )
  {
    v9 = ProvOperations::ProvOperations(v7);
    v8 = (**(__int64 (__fastcall ***)(ProvOperations *, GUID *, _QWORD))v9)(
           v9,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v13);
    (*(void (__fastcall **)(ProvOperations *))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v8 >= 0 )
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
    v8 = -2147024882;
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v10)[2])(v10);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009300  push    rbx
0x180009302  push    rbp
0x180009303  push    rsi
0x180009304  push    rdi
0x180009305  sub     rsp, 28h
0x180009309  mov     rsi, r9
0x18000930c  mov     rbp, r8
0x18000930f  mov     qword ptr [r9], 0
0x180009316  test    rdx, rdx
0x180009319  jz      short loc_18000932F
0x18000931b  xor     edx, edx
0x18000931d  mov     ebx, 80040110h
0x180009322  mov     ecx, ebx
0x180009324  call    cs:__imp_RoOriginateError
0x18000932a  jmp     loc_1800093EC
0x18000932f  mov     [rsp+48h+arg_8], 0
0x180009338  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000933f  mov     ecx, 40h ; '@'; unsigned __int64
0x180009344  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009349  test    rax, rax
0x18000934c  jnz     short loc_180009355
0x18000934e  mov     edi, 8007000Eh
0x180009353  jmp     short loc_180009390
0x180009355  mov     rcx, rax; this
0x180009358  call    ??0ProvOperations@@QEAA@XZ; ProvOperations::ProvOperations(void)
0x18000935d  mov     rbx, rax
0x180009360  mov     rcx, [rax]
0x180009363  mov     rax, [rcx]
0x180009366  lea     r8, [rsp+48h+arg_8]
0x18000936b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009372  mov     rcx, rbx
0x180009375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000937a  mov     edi, eax
0x18000937c  mov     rax, [rbx]
0x18000937f  mov     rcx, rbx
0x180009382  mov     rax, [rax+10h]
0x180009386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000938b  nop
0x18000938c  test    edi, edi
0x18000938e  jns     short loc_1800093B4
0x180009390  mov     rcx, [rsp+48h+arg_8]
0x180009395  test    rcx, rcx
0x180009398  jz      short loc_1800093B0
0x18000939a  mov     [rsp+48h+arg_8], 0
0x1800093a3  mov     rdx, [rcx]
0x1800093a6  mov     rax, [rdx+10h]
0x1800093aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093af  nop
0x1800093b0  mov     eax, edi
0x1800093b2  jmp     short loc_1800093EE
0x1800093b4  mov     rcx, [rsp+48h+arg_8]
0x1800093b9  mov     rax, [rcx]
0x1800093bc  mov     r8, rsi
0x1800093bf  mov     rdx, rbp
0x1800093c2  mov     rax, [rax]
0x1800093c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093ca  mov     ebx, eax
0x1800093cc  mov     rcx, [rsp+48h+arg_8]
0x1800093d1  test    rcx, rcx
0x1800093d4  jz      short loc_1800093EC
0x1800093d6  mov     [rsp+48h+arg_8], 0
0x1800093df  mov     rdx, [rcx]
0x1800093e2  mov     rax, [rdx+10h]
0x1800093e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093eb  nop
0x1800093ec  mov     eax, ebx
0x1800093ee  add     rsp, 28h
0x1800093f2  pop     rdi
0x1800093f3  pop     rsi
0x1800093f4  pop     rbp
0x1800093f5  pop     rbx
0x1800093f6  retn
```
