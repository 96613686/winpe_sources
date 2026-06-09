# ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)

- ea: `0x1800043a0`
- end: `0x18000447f`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z`
- size: `223`
- prototype: `int(ATL::CComTypeInfoHolder *__hidden this, unsigned int, struct ITypeInfo **)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001fd0`
- `0x180002820`
- `0x180003160`
- `0x180003d20`
- `0x180004328`
- `0x180004488`
- `0x1800052a0`
- `0x1800070b0`

## callees

- `0x1800043a0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000446a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000446a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800043c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800043c7`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800043f7`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800043f7`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID a2, struct ITypeInfo **a3)
{
  HRESULT v6; // edi
  WORD v7; // r8
  WORD v8; // dx
  const GUID *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  ITypeLib *pptlib; // [rsp+50h] [rbp+8h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = -2147467259;
  EnterCriticalSection(&CriticalSection);
  if ( !*((_QWORD *)this + 3) )
  {
    v7 = *((_WORD *)this + 9);
    v8 = *((_WORD *)this + 8);
    v9 = (const GUID *)*((_QWORD *)this + 1);
    pptlib = 0;
    v6 = LoadRegTypeLib(v9, v8, v7, a2, &pptlib);
    if ( v6 >= 0 )
    {
      v10 = *(_QWORD *)this;
      v14 = 0;
      v6 = ((__int64 (__fastcall *)(ITypeLib *, __int64, __int64 *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
             pptlib,
             v10,
             &v14);
      if ( v6 >= 0 )
        *((_QWORD *)this + 3) = v14;
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
    }
  }
  *a3 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  v11 = *((_QWORD *)this + 3);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v6 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800043a0  mov     [rsp+arg_8], rbx
0x1800043a5  push    rbp
0x1800043a6  push    rsi
0x1800043a7  push    rdi
0x1800043a8  sub     rsp, 30h
0x1800043ac  mov     rbx, rcx
0x1800043af  mov     qword ptr [r8], 0
0x1800043b6  lea     rcx, CriticalSection; lpCriticalSection
0x1800043bd  mov     rsi, r8
0x1800043c0  mov     ebp, edx
0x1800043c2  mov     edi, 80004005h
0x1800043c7  call    cs:__imp_EnterCriticalSection
0x1800043cd  cmp     qword ptr [rbx+18h], 0
0x1800043d2  jnz     short loc_180004445
0x1800043d4  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x1800043d9  lea     rax, [rsp+48h+arg_0]
0x1800043de  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x1800043e2  mov     r9d, ebp; lcid
0x1800043e5  mov     rcx, [rbx+8]; rguid
0x1800043e9  mov     [rsp+48h+pptlib], rax; pptlib
0x1800043ee  mov     [rsp+48h+arg_0], 0
0x1800043f7  call    cs:__imp_LoadRegTypeLib
0x1800043fd  mov     edi, eax
0x1800043ff  test    eax, eax
0x180004401  js      short loc_180004445
0x180004403  mov     rcx, [rsp+48h+arg_0]
0x180004408  lea     r8, [rsp+48h+arg_10]
0x18000440d  mov     rdx, [rbx]
0x180004410  mov     [rsp+48h+arg_10], 0
0x180004419  mov     rax, [rcx]
0x18000441c  mov     rax, [rax+30h]
0x180004420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004425  mov     edi, eax
0x180004427  test    eax, eax
0x180004429  js      short loc_180004434
0x18000442b  mov     rax, [rsp+48h+arg_10]
0x180004430  mov     [rbx+18h], rax
0x180004434  mov     rcx, [rsp+48h+arg_0]
0x180004439  mov     rax, [rcx]
0x18000443c  mov     rax, [rax+10h]
0x180004440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004445  mov     rax, [rbx+18h]
0x180004449  mov     [rsi], rax
0x18000444c  mov     rcx, [rbx+18h]
0x180004450  test    rcx, rcx
0x180004453  jz      short loc_180004463
0x180004455  mov     rax, [rcx]
0x180004458  mov     rax, [rax+8]
0x18000445c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004461  xor     edi, edi
0x180004463  lea     rcx, CriticalSection; lpCriticalSection
0x18000446a  call    cs:__imp_LeaveCriticalSection
0x180004470  mov     rbx, [rsp+48h+arg_8]
0x180004475  mov     eax, edi
0x180004477  add     rsp, 30h
0x18000447b  pop     rdi
0x18000447c  pop     rsi
0x18000447d  pop     rbp
0x18000447e  retn
```
