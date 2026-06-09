# CSimpleTableDispenser::GetCatalogErrorLogger(ICatalogErrorLogger2 * *)

- ea: `0x1800031d0`
- end: `0x18000335f`
- name: `?GetCatalogErrorLogger@CSimpleTableDispenser@@UEAAJPEAPEAUICatalogErrorLogger2@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(CSimpleTableDispenser *__hidden this, struct ICatalogErrorLogger2 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001f70`
- `0x180002b20`
- `0x1800031d0`
- `0x1800117b4`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180003222`
- `ole32!CoTaskMemAlloc` at `0x180003291`
- `ole32!CoTaskMemAlloc` at `0x180003222`
- `ole32!CoTaskMemAlloc` at `0x180003291`

## pseudocode

```c
__int64 __fastcall CSimpleTableDispenser::GetCatalogErrorLogger(
        CSimpleTableDispenser *this,
        struct ICatalogErrorLogger2 **a2)
{
  int v3; // ebx
  _QWORD *v4; // r14
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  _DWORD *v7; // rsi
  __int64 v8; // rdx
  __int64 v10; // rdx
  int v11; // [rsp+20h] [rbp-28h] BYREF
  _RTL_CRITICAL_SECTION *v12; // [rsp+28h] [rbp-20h]
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 && !*a2 )
  {
    v3 = 0;
    v11 = 0;
    v4 = (_QWORD *)((char *)this + 2624);
    v12 = &g_csSADispenser;
    if ( *((_QWORD *)this + 328) )
      goto LABEL_9;
    v5 = CoTaskMemAlloc(0x38u);
    v6 = v5;
    if ( !v5 )
    {
      v3 = -2147024882;
LABEL_11:
      CSafeLock::~CSafeLock((CSafeLock *)&v11);
      return (unsigned int)v3;
    }
    v5[2] = 0x80000;
    *(_QWORD *)v5 = &TextFileLogger::`vftable';
    v5[3] = 4;
    *((_QWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 3) = -1;
    *((_QWORD *)v5 + 4) = 0;
    v5[10] = 0;
    *((_QWORD *)v5 + 6) = 0;
    v13 = 0;
    v3 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v5)(v5, &IID_ICatalogErrorLogger2, &v13);
    if ( v3 >= 0 )
    {
      v7 = CoTaskMemAlloc(0x18u);
      if ( v7 )
      {
        v8 = v13;
        *(_QWORD *)v7 = &EventLogger::`vftable';
        v7[2] = 0;
        ATL::CComPtr<ICatalogErrorLogger2>::CComPtr<ICatalogErrorLogger2>(v7 + 4, v8);
        v3 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v7)(v7, &IID_ICatalogErrorLogger2, v4);
        if ( v3 >= 0 )
        {
          ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v13);
LABEL_9:
          *a2 = (struct ICatalogErrorLogger2 *)*v4;
          if ( *v4 )
            (*(void (__fastcall **)(_QWORD, struct ICatalogErrorLogger2 **))(*(_QWORD *)*v4 + 8LL))(*v4, a2);
          goto LABEL_11;
        }
LABEL_14:
        ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v13);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v7 )
          (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 16LL))(v7, v10);
        goto LABEL_11;
      }
      v3 = -2147024882;
    }
    v7 = 0;
    goto LABEL_14;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800031d0  mov     [rsp+arg_0], rbx
0x1800031d5  mov     [rsp+arg_10], rsi
0x1800031da  push    rdi
0x1800031db  push    r14
0x1800031dd  push    r15
0x1800031df  sub     rsp, 30h
0x1800031e3  mov     r15, rdx
0x1800031e6  test    rdx, rdx
0x1800031e9  jz      loc_180003346
0x1800031ef  cmp     qword ptr [rdx], 0
0x1800031f3  jnz     loc_180003346
0x1800031f9  xor     ebx, ebx
0x1800031fb  mov     [rsp+48h+var_28], 0
0x180003203  lea     r14, [rcx+0A40h]
0x18000320a  lea     rax, ?g_csSADispenser@@3VCSafeAutoCriticalSection@@A; CSafeAutoCriticalSection g_csSADispenser
0x180003211  mov     [rsp+48h+var_20], rax
0x180003216  cmp     [r14], rbx
0x180003219  jnz     loc_1800032E6
0x18000321f  lea     ecx, [rbx+38h]; cb
0x180003222  call    cs:__imp_CoTaskMemAlloc
0x180003228  mov     rdi, rax
0x18000322b  test    rax, rax
0x18000322e  jz      loc_18000333F
0x180003234  mov     dword ptr [rdi+8], 80000h
0x18000323b  lea     rax, ??_7TextFileLogger@@6B@; const TextFileLogger::`vftable'
0x180003242  mov     [rdi], rax
0x180003245  lea     r8, [rsp+48h+arg_8]
0x18000324a  mov     dword ptr [rdi+0Ch], 4
0x180003251  lea     rdx, IID_ICatalogErrorLogger2
0x180003258  mov     [rdi+10h], rbx
0x18000325c  mov     rcx, rdi
0x18000325f  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x180003267  mov     [rdi+20h], rbx
0x18000326b  mov     [rdi+28h], ebx
0x18000326e  mov     [rdi+30h], rbx
0x180003272  mov     [rsp+48h+arg_8], rbx
0x180003277  mov     rax, [rdi]
0x18000327a  mov     rax, [rax]
0x18000327d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003282  mov     ebx, eax
0x180003284  test    eax, eax
0x180003286  js      loc_180003313
0x18000328c  mov     ecx, 18h; cb
0x180003291  call    cs:__imp_CoTaskMemAlloc
0x180003297  mov     rsi, rax
0x18000329a  test    rax, rax
0x18000329d  jz      short loc_18000330E
0x18000329f  mov     rdx, [rsp+48h+arg_8]
0x1800032a4  lea     rax, ??_7EventLogger@@6B@; const EventLogger::`vftable'
0x1800032ab  lea     rcx, [rsi+10h]
0x1800032af  mov     [rsi], rax
0x1800032b2  mov     dword ptr [rsi+8], 0
0x1800032b9  call    ??0?$CComPtr@UICatalogErrorLogger2@@@ATL@@QEAA@PEAUICatalogErrorLogger2@@@Z; ATL::CComPtr<ICatalogErrorLogger2>::CComPtr<ICatalogErrorLogger2>(ICatalogErrorLogger2 *)
0x1800032be  mov     rax, [rsi]
0x1800032c1  lea     rdx, IID_ICatalogErrorLogger2
0x1800032c8  mov     r8, r14
0x1800032cb  mov     rcx, rsi
0x1800032ce  mov     rax, [rax]
0x1800032d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d6  lea     rcx, [rsp+48h+arg_8]
0x1800032db  mov     ebx, eax
0x1800032dd  test    eax, eax
0x1800032df  js      short loc_18000331A
0x1800032e1  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800032e6  mov     rax, [r14]
0x1800032e9  mov     [r15], rax
0x1800032ec  mov     rcx, [r14]
0x1800032ef  test    rcx, rcx
0x1800032f2  jz      short loc_180003300
0x1800032f4  mov     rax, [rcx]
0x1800032f7  mov     rax, [rax+8]
0x1800032fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003300  lea     rcx, [rsp+48h+var_28]; this
0x180003305  call    ??1CSafeLock@@QEAA@XZ; CSafeLock::~CSafeLock(void)
0x18000330a  mov     eax, ebx
0x18000330c  jmp     short loc_18000334B
0x18000330e  mov     ebx, 8007000Eh
0x180003313  lea     rcx, [rsp+48h+arg_8]
0x180003318  xor     esi, esi
0x18000331a  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000331f  mov     rax, [rdi]
0x180003322  mov     rcx, rdi
0x180003325  mov     rax, [rax+10h]
0x180003329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000332e  test    rsi, rsi
0x180003331  jz      short loc_180003300
0x180003333  mov     rax, [rsi]
0x180003336  mov     rcx, rsi
0x180003339  mov     rax, [rax+10h]
0x18000333d  jmp     short loc_1800032FB
0x18000333f  mov     ebx, 8007000Eh
0x180003344  jmp     short loc_180003300
0x180003346  mov     eax, 80070057h
0x18000334b  mov     rbx, [rsp+48h+arg_0]
0x180003350  mov     rsi, [rsp+48h+arg_10]
0x180003355  add     rsp, 30h
0x180003359  pop     r15
0x18000335b  pop     r14
0x18000335d  pop     rdi
0x18000335e  retn
```
