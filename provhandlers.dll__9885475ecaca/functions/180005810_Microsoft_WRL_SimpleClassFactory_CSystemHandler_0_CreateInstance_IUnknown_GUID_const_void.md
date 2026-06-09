# Microsoft::WRL::SimpleClassFactory<CSystemHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005810`
- end: `0x180005922`
- name: `?CreateInstance@?$SimpleClassFactory@VCSystemHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `274`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002558`
- `0x180005810`
- `0x18000ea0c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005834`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005834`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CSystemHandler,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  CHandlerBase *v7; // rax
  CHandlerBase *v8; // rbx
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
  v7 = (CHandlerBase *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    CHandlerBase::CHandlerBase(v7);
    *(_QWORD *)v8 = &CSystemHandler::`vftable';
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 5) = 0;
    v9 = ((__int64 (__fastcall *)(CHandlerBase *, GUID *, _QWORD))CSystemHandler::`vftable')(
           v8,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v13);
    (*(void (__fastcall **)(CHandlerBase *))(*(_QWORD *)v8 + 16LL))(v8);
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
0x180005810  push    rbx
0x180005812  push    rbp
0x180005813  push    rsi
0x180005814  push    rdi
0x180005815  sub     rsp, 28h
0x180005819  mov     rsi, r9
0x18000581c  mov     rbp, r8
0x18000581f  mov     qword ptr [r9], 0
0x180005826  test    rdx, rdx
0x180005829  jz      short loc_18000583F
0x18000582b  xor     edx, edx
0x18000582d  mov     ebx, 80040110h
0x180005832  mov     ecx, ebx
0x180005834  call    cs:__imp_RoOriginateError
0x18000583a  jmp     loc_180005917
0x18000583f  mov     [rsp+48h+arg_8], 0
0x180005848  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000584f  mov     ecx, 30h ; '0'; unsigned __int64
0x180005854  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005859  mov     rbx, rax
0x18000585c  test    rax, rax
0x18000585f  jnz     short loc_180005868
0x180005861  mov     edi, 8007000Eh
0x180005866  jmp     short loc_1800058BB
0x180005868  mov     rcx, rbx; this
0x18000586b  call    ??0CHandlerBase@@QEAA@XZ; CHandlerBase::CHandlerBase(void)
0x180005870  lea     rax, ??_7CSystemHandler@@6B@; const CSystemHandler::`vftable'
0x180005877  mov     [rbx], rax
0x18000587a  mov     qword ptr [rbx+20h], 0
0x180005882  mov     qword ptr [rbx+28h], 0
0x18000588a  lea     r8, [rsp+48h+arg_8]
0x18000588f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005896  mov     rcx, rbx
0x180005899  mov     rax, cs:??_7CSystemHandler@@6B@; const CSystemHandler::`vftable'
0x1800058a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a5  mov     edi, eax
0x1800058a7  mov     rax, [rbx]
0x1800058aa  mov     rcx, rbx
0x1800058ad  mov     rax, [rax+10h]
0x1800058b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b6  nop
0x1800058b7  test    edi, edi
0x1800058b9  jns     short loc_1800058DF
0x1800058bb  mov     rcx, [rsp+48h+arg_8]
0x1800058c0  test    rcx, rcx
0x1800058c3  jz      short loc_1800058DB
0x1800058c5  mov     [rsp+48h+arg_8], 0
0x1800058ce  mov     rdx, [rcx]
0x1800058d1  mov     rax, [rdx+10h]
0x1800058d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058da  nop
0x1800058db  mov     eax, edi
0x1800058dd  jmp     short loc_180005919
0x1800058df  mov     rcx, [rsp+48h+arg_8]
0x1800058e4  mov     rax, [rcx]
0x1800058e7  mov     r8, rsi
0x1800058ea  mov     rdx, rbp
0x1800058ed  mov     rax, [rax]
0x1800058f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f5  mov     ebx, eax
0x1800058f7  mov     rcx, [rsp+48h+arg_8]
0x1800058fc  test    rcx, rcx
0x1800058ff  jz      short loc_180005917
0x180005901  mov     [rsp+48h+arg_8], 0
0x18000590a  mov     rdx, [rcx]
0x18000590d  mov     rax, [rdx+10h]
0x180005911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005916  nop
0x180005917  mov     eax, ebx
0x180005919  add     rsp, 28h
0x18000591d  pop     rdi
0x18000591e  pop     rsi
0x18000591f  pop     rbp
0x180005920  pop     rbx
0x180005921  retn
```
