# CCmstpLua::QueryInterface(_GUID const &,void * *)

- ea: `0x180002020`
- end: `0x180002166`
- name: `?QueryInterface@CCmstpLua@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `326`
- prototype: `__int64 __fastcall(CCmstpLua *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002020`
- `0x1800021e8`
- `0x180003010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800020ff`
- `ole32!CoCreateInstance` at `0x1800020ff`

## pseudocode

```c
__int64 __fastcall CCmstpLua::QueryInterface(CCmstpLua *this, const struct _GUID *a2, void **a3)
{
  HRESULT Instance; // ebx
  LPVOID *ppv; // rsi
  CCmstpLua *v7; // rcx
  LPVOID v8; // rcx
  __int64 v9; // rax

  if ( *(_OWORD *)&IID_IUnknown != *(_OWORD *)a2
    && (*(_QWORD *)&IID_ICmstpLua.Data1 != *(_QWORD *)&a2->Data1
     || *(_QWORD *)IID_ICmstpLua.Data4 != *(_QWORD *)a2->Data4)
    && (*(_QWORD *)&IID_ICmstpLua2.Data1 != *(_QWORD *)&a2->Data1
     || *(_QWORD *)IID_ICmstpLua2.Data4 != *(_QWORD *)a2->Data4)
    && (*(_QWORD *)&IID_ICMLuaUtil.Data1 != *(_QWORD *)&a2->Data1
     || *(_QWORD *)IID_ICMLuaUtil.Data4 != *(_QWORD *)a2->Data4) )
  {
    Instance = -2147467262;
    goto LABEL_26;
  }
  if ( *(_QWORD *)&IID_ICmstpLua.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_ICmstpLua.Data4 == *(_QWORD *)a2->Data4
    || *(_QWORD *)&IID_ICmstpLua2.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_ICmstpLua2.Data4 == *(_QWORD *)a2->Data4 )
  {
    if ( !FIsUserAdmin() )
    {
LABEL_13:
      Instance = -2147024891;
LABEL_26:
      *a3 = 0;
      return (unsigned int)Instance;
    }
    goto LABEL_23;
  }
  if ( *(_QWORD *)&IID_ICMLuaUtil.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_ICMLuaUtil.Data4 == *(_QWORD *)a2->Data4 )
  {
    if ( !FIsUserAdmin() )
      goto LABEL_13;
    ppv = (LPVOID *)((char *)this + 16);
    v7 = (CCmstpLua *)*ppv;
    if ( *ppv )
    {
      *a3 = v7;
      v9 = *(_QWORD *)v7;
LABEL_24:
      (*(void (__fastcall **)(CCmstpLua *))(v9 + 8))(v7);
      return 0;
    }
    Instance = CoCreateInstance(&CLSID_CMLuaUtil, 0, 5u, &IID_ICMLuaUtil, ppv);
    if ( Instance >= 0 )
    {
      v8 = *ppv;
      *a3 = *ppv;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  else
  {
    Instance = -2147467262;
    if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)a2->Data4 )
    {
LABEL_23:
      *a3 = this;
      v7 = this;
      v9 = *(_QWORD *)this;
      goto LABEL_24;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180002020  push    rbx
0x180002022  push    rbp
0x180002023  push    rsi
0x180002024  push    rdi
0x180002025  push    r14
0x180002027  sub     rsp, 30h
0x18000202b  mov     r14, qword ptr cs:IID_IUnknown.Data1
0x180002032  mov     rdi, r8
0x180002035  mov     rsi, rcx
0x180002038  mov     r11, qword ptr cs:IID_ICMLuaUtil.Data4
0x18000203f  mov     r10, qword ptr cs:IID_ICMLuaUtil.Data1
0x180002046  mov     r9, qword ptr cs:IID_ICmstpLua2.Data4
0x18000204d  mov     r8, qword ptr cs:IID_ICmstpLua2.Data1
0x180002054  mov     rcx, qword ptr cs:IID_ICmstpLua.Data4
0x18000205b  mov     rax, qword ptr cs:IID_ICmstpLua.Data1
0x180002062  mov     rbp, qword ptr cs:IID_IUnknown.Data4
0x180002069  cmp     r14, [rdx]
0x18000206c  jnz     short loc_180002074
0x18000206e  cmp     rbp, [rdx+8]
0x180002072  jz      short loc_18000209D
0x180002074  cmp     rax, [rdx]
0x180002077  jnz     short loc_18000207F
0x180002079  cmp     rcx, [rdx+8]
0x18000207d  jz      short loc_18000209D
0x18000207f  cmp     r8, [rdx]
0x180002082  jnz     short loc_18000208A
0x180002084  cmp     r9, [rdx+8]
0x180002088  jz      short loc_18000209D
0x18000208a  cmp     r10, [rdx]
0x18000208d  jnz     loc_18000214D
0x180002093  cmp     r11, [rdx+8]
0x180002097  jnz     loc_18000214D
0x18000209d  cmp     rax, [rdx]
0x1800020a0  jnz     short loc_1800020A8
0x1800020a2  cmp     rcx, [rdx+8]
0x1800020a6  jz      short loc_1800020B3
0x1800020a8  cmp     r8, [rdx]
0x1800020ab  jnz     short loc_1800020C6
0x1800020ad  cmp     r9, [rdx+8]
0x1800020b1  jnz     short loc_1800020C6
0x1800020b3  call    FIsUserAdmin
0x1800020b8  test    eax, eax
0x1800020ba  jnz     short loc_180002137
0x1800020bc  mov     ebx, 80070005h
0x1800020c1  jmp     loc_180002152
0x1800020c6  cmp     r10, [rdx]
0x1800020c9  jnz     short loc_180002127
0x1800020cb  cmp     r11, [rdx+8]
0x1800020cf  jnz     short loc_180002127
0x1800020d1  call    FIsUserAdmin
0x1800020d6  test    eax, eax
0x1800020d8  jz      short loc_1800020BC
0x1800020da  add     rsi, 10h
0x1800020de  mov     rcx, [rsi]
0x1800020e1  test    rcx, rcx
0x1800020e4  jnz     short loc_18000211F
0x1800020e6  lea     r8d, [rcx+5]; dwClsContext
0x1800020ea  mov     [rsp+58h+ppv], rsi; ppv
0x1800020ef  lea     rcx, CLSID_CMLuaUtil; rclsid
0x1800020f6  xor     edx, edx; pUnkOuter
0x1800020f8  lea     r9, IID_ICMLuaUtil; riid
0x1800020ff  call    cs:__imp_CoCreateInstance
0x180002105  mov     ebx, eax
0x180002107  test    eax, eax
0x180002109  js      short loc_180002159
0x18000210b  mov     rcx, [rsi]
0x18000210e  mov     [rdi], rcx
0x180002111  mov     rdx, [rcx]
0x180002114  mov     rax, [rdx+8]
0x180002118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000211d  jmp     short loc_180002159
0x18000211f  mov     [rdi], rcx
0x180002122  mov     rax, [rcx]
0x180002125  jmp     short loc_180002140
0x180002127  mov     ebx, 80004002h
0x18000212c  cmp     r14, [rdx]
0x18000212f  jnz     short loc_180002159
0x180002131  cmp     rbp, [rdx+8]
0x180002135  jnz     short loc_180002159
0x180002137  mov     [rdi], rsi
0x18000213a  mov     rcx, rsi
0x18000213d  mov     rax, [rsi]
0x180002140  mov     rax, [rax+8]
0x180002144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002149  xor     ebx, ebx
0x18000214b  jmp     short loc_180002159
0x18000214d  mov     ebx, 80004002h
0x180002152  mov     qword ptr [rdi], 0
0x180002159  mov     eax, ebx
0x18000215b  add     rsp, 30h
0x18000215f  pop     r14
0x180002161  pop     rdi
0x180002162  pop     rsi
0x180002163  pop     rbp
0x180002164  pop     rbx
0x180002165  retn
```
