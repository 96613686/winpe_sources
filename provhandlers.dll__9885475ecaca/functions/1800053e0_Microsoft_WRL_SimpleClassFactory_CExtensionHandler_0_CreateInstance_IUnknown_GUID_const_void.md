# Microsoft::WRL::SimpleClassFactory<CExtensionHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800053e0`
- end: `0x1800054fe`
- name: `?CreateInstance@?$SimpleClassFactory@VCExtensionHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `286`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002558`
- `0x1800053e0`
- `0x18000ea0c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005404`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005404`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CExtensionHandler,0>::CreateInstance(
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
  v7 = (CHandlerBase *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    CHandlerBase::CHandlerBase(v7);
    *(_QWORD *)v8 = &CExtensionHandler::`vftable';
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 7) = 0;
    v9 = ((__int64 (__fastcall *)(CHandlerBase *, GUID *, _QWORD))CExtensionHandler::`vftable')(
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
0x1800053e0  push    rbx
0x1800053e2  push    rbp
0x1800053e3  push    rsi
0x1800053e4  push    rdi
0x1800053e5  sub     rsp, 28h
0x1800053e9  mov     rsi, r9
0x1800053ec  mov     rbp, r8
0x1800053ef  mov     qword ptr [r9], 0
0x1800053f6  test    rdx, rdx
0x1800053f9  jz      short loc_18000540F
0x1800053fb  xor     edx, edx
0x1800053fd  mov     ebx, 80040110h
0x180005402  mov     ecx, ebx
0x180005404  call    cs:__imp_RoOriginateError
0x18000540a  jmp     loc_1800054F3
0x18000540f  mov     [rsp+48h+arg_8], 0
0x180005418  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000541f  mov     ecx, 40h ; '@'; unsigned __int64
0x180005424  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005429  mov     rbx, rax
0x18000542c  test    rax, rax
0x18000542f  jnz     short loc_180005438
0x180005431  mov     edi, 8007000Eh
0x180005436  jmp     short loc_180005497
0x180005438  mov     rcx, rbx; this
0x18000543b  call    ??0CHandlerBase@@QEAA@XZ; CHandlerBase::CHandlerBase(void)
0x180005440  lea     rax, ??_7CExtensionHandler@@6B@; const CExtensionHandler::`vftable'
0x180005447  mov     [rbx], rax
0x18000544a  mov     qword ptr [rbx+20h], 0
0x180005452  mov     qword ptr [rbx+28h], 0
0x18000545a  mov     qword ptr [rbx+30h], 0
0x180005462  mov     qword ptr [rbx+38h], 0
0x18000546a  lea     r8, [rsp+48h+arg_8]
0x18000546f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005476  mov     rcx, rbx
0x180005479  mov     rax, [rax]
0x18000547c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005481  mov     edi, eax
0x180005483  mov     rax, [rbx]
0x180005486  mov     rcx, rbx
0x180005489  mov     rax, [rax+10h]
0x18000548d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005492  nop
0x180005493  test    edi, edi
0x180005495  jns     short loc_1800054BB
0x180005497  mov     rcx, [rsp+48h+arg_8]
0x18000549c  test    rcx, rcx
0x18000549f  jz      short loc_1800054B7
0x1800054a1  mov     [rsp+48h+arg_8], 0
0x1800054aa  mov     rdx, [rcx]
0x1800054ad  mov     rax, [rdx+10h]
0x1800054b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054b6  nop
0x1800054b7  mov     eax, edi
0x1800054b9  jmp     short loc_1800054F5
0x1800054bb  mov     rcx, [rsp+48h+arg_8]
0x1800054c0  mov     rax, [rcx]
0x1800054c3  mov     r8, rsi
0x1800054c6  mov     rdx, rbp
0x1800054c9  mov     rax, [rax]
0x1800054cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d1  mov     ebx, eax
0x1800054d3  mov     rcx, [rsp+48h+arg_8]
0x1800054d8  test    rcx, rcx
0x1800054db  jz      short loc_1800054F3
0x1800054dd  mov     [rsp+48h+arg_8], 0
0x1800054e6  mov     rdx, [rcx]
0x1800054e9  mov     rax, [rdx+10h]
0x1800054ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f2  nop
0x1800054f3  mov     eax, ebx
0x1800054f5  add     rsp, 28h
0x1800054f9  pop     rdi
0x1800054fa  pop     rsi
0x1800054fb  pop     rbp
0x1800054fc  pop     rbx
0x1800054fd  retn
```
