# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180004328`
- end: `0x18000439a`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `114`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001fb0`
- `0x180002800`
- `0x180002f00`
- `0x180003cc0`
- `0x180005280`
- `0x180007080`

## callees

- `0x180004328`
- `0x1800043a0`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID a5,
        int *a6)
{
  unsigned int TI; // eax
  struct ITypeInfo *v9; // rdi
  unsigned int v10; // ebx
  struct ITypeInfo *v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = 0;
  TI = ATL::CComTypeInfoHolder::GetTI(this, a5, &v12);
  v9 = v12;
  v10 = TI;
  if ( v12 )
  {
    v10 = ((__int64 (__fastcall *)(struct ITypeInfo *, unsigned __int16 **, _QWORD, int *))v12->lpVtbl->GetIDsOfNames)(
            v12,
            a3,
            a4,
            a6);
    ((void (__fastcall *)(struct ITypeInfo *))v9->lpVtbl->Release)(v9);
  }
  return v10;
}

```

## disassembly

```asm
0x180004328  mov     [rsp+arg_8], rdx
0x18000432d  push    rbx
0x18000432e  push    rbp
0x18000432f  push    rsi
0x180004330  push    rdi
0x180004331  sub     rsp, 38h
0x180004335  mov     edx, [rsp+58h+arg_20]; unsigned int
0x18000433c  mov     rbp, r8
0x18000433f  lea     r8, [rsp+58h+arg_8]; struct ITypeInfo **
0x180004344  mov     [rsp+58h+arg_8], 0
0x18000434d  mov     esi, r9d
0x180004350  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)
0x180004355  mov     rdi, [rsp+58h+arg_8]
0x18000435a  mov     ebx, eax
0x18000435c  test    rdi, rdi
0x18000435f  jz      short loc_18000438F
0x180004361  mov     rax, [rdi]
0x180004364  mov     r8d, esi
0x180004367  mov     r9, [rsp+58h+arg_28]
0x18000436f  mov     rdx, rbp
0x180004372  mov     rcx, rdi
0x180004375  mov     rax, [rax+50h]
0x180004379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000437e  mov     rdx, [rdi]
0x180004381  mov     ebx, eax
0x180004383  mov     rcx, rdi
0x180004386  mov     rax, [rdx+10h]
0x18000438a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000438f  mov     eax, ebx
0x180004391  add     rsp, 38h
0x180004395  pop     rdi
0x180004396  pop     rsi
0x180004397  pop     rbp
0x180004398  pop     rbx
0x180004399  retn
```
