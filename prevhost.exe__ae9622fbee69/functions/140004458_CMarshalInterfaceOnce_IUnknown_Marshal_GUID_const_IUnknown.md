# CMarshalInterfaceOnce<IUnknown>::Marshal(_GUID const &,IUnknown *)

- ea: `0x140004458`
- end: `0x140004580`
- name: `?Marshal@?$CMarshalInterfaceOnce@UIUnknown@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(__int64 *, const IID *, IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005140`

## callees

- `0x140001494`
- `0x140004458`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004505`
- `KERNEL32!GetCurrentThreadId` at `0x140004505`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140004539`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140004539`

## pseudocode

```c
__int64 __fastcall CMarshalInterfaceOnce<IUnknown>::Marshal(__int64 *a1, const IID *a2, IUnknown *a3)
{
  __int64 v5; // rcx
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  HRESULT v9; // edi
  struct Microsoft::WRL::Details::ModuleBase *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax

  v5 = *a1;
  if ( v5 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  *a1 = 0;
  v7 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    v10 = Microsoft::WRL::Details::ModuleBase::module_;
    v7[3] = 1;
    *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
    if ( v10 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v10 + 8LL))(v10);
    v8[6] = 2;
    *(_QWORD *)v8 = &CMarshaledInterface::CMarshalStream::`vftable';
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 4) = 0;
    v8[10] = 0;
    v8[10] = GetCurrentThreadId();
    v8[6] = 1;
    v11 = *((_QWORD *)v8 + 2);
    if ( v11 )
    {
      *((_QWORD *)v8 + 2) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v9 = CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)v8 + 2);
    v12 = *(_QWORD *)v8;
    if ( v9 >= 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v12 + 8))(v8);
      *a1 = (__int64)v8;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
      return 0;
    }
    else
    {
      (*(void (__fastcall **)(_DWORD *))(v12 + 16))(v8);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140004458  push    rbx
0x14000445a  push    rbp
0x14000445b  push    rsi
0x14000445c  push    rdi
0x14000445d  push    r14
0x14000445f  sub     rsp, 20h
0x140004463  mov     rsi, rcx
0x140004466  mov     rbp, r8
0x140004469  mov     rcx, [rcx]
0x14000446c  mov     r14, rdx
0x14000446f  test    rcx, rcx
0x140004472  jz      short loc_140004487
0x140004474  mov     qword ptr [rsi], 0
0x14000447b  mov     rax, [rcx]
0x14000447e  mov     rax, [rax+10h]
0x140004482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004487  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000448e  mov     qword ptr [rsi], 0
0x140004495  mov     ecx, 30h ; '0'; unsigned __int64
0x14000449a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000449f  mov     rbx, rax
0x1400044a2  test    rax, rax
0x1400044a5  jnz     short loc_1400044B1
0x1400044a7  mov     edi, 8007000Eh
0x1400044ac  jmp     loc_140004573
0x1400044b1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400044b8  mov     dword ptr [rax+0Ch], 1
0x1400044bf  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x1400044c6  mov     [rbx], rax
0x1400044c9  test    rcx, rcx
0x1400044cc  jz      short loc_1400044DA
0x1400044ce  mov     rax, [rcx]
0x1400044d1  mov     rax, [rax+8]
0x1400044d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044da  lea     rax, ??_7CMarshalStream@CMarshaledInterface@@6B@; const CMarshaledInterface::CMarshalStream::`vftable'
0x1400044e1  mov     dword ptr [rbx+18h], 2
0x1400044e8  mov     [rbx], rax
0x1400044eb  lea     rdi, [rbx+10h]
0x1400044ef  mov     qword ptr [rdi], 0
0x1400044f6  mov     qword ptr [rbx+20h], 0
0x1400044fe  mov     dword ptr [rbx+28h], 0
0x140004505  call    cs:__imp_GetCurrentThreadId
0x14000450b  mov     [rbx+28h], eax
0x14000450e  mov     dword ptr [rbx+18h], 1
0x140004515  mov     rcx, [rdi]
0x140004518  test    rcx, rcx
0x14000451b  jz      short loc_140004530
0x14000451d  mov     qword ptr [rdi], 0
0x140004524  mov     rax, [rcx]
0x140004527  mov     rax, [rax+10h]
0x14000452b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004530  mov     r8, rdi; ppStm
0x140004533  mov     rdx, rbp; pUnk
0x140004536  mov     rcx, r14; riid
0x140004539  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x14000453f  mov     edi, eax
0x140004541  mov     rcx, rbx
0x140004544  mov     rax, [rbx]
0x140004547  test    edi, edi
0x140004549  jns     short loc_140004556
0x14000454b  mov     rax, [rax+10h]
0x14000454f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004554  jmp     short loc_140004573
0x140004556  mov     rax, [rax+8]
0x14000455a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000455f  mov     [rsi], rbx
0x140004562  mov     rcx, rbx
0x140004565  mov     rax, [rbx]
0x140004568  mov     rax, [rax+10h]
0x14000456c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004571  xor     edi, edi
0x140004573  mov     eax, edi
0x140004575  add     rsp, 20h
0x140004579  pop     r14
0x14000457b  pop     rdi
0x14000457c  pop     rsi
0x14000457d  pop     rbp
0x14000457e  pop     rbx
0x14000457f  retn
```
